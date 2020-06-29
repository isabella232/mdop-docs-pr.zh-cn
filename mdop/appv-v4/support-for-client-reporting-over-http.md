---
title: 支持通过 HTTP 进行客户端报告
description: 支持通过 HTTP 进行客户端报告
author: dansimp
ms.assetid: 4a26ac80-1fb5-4c05-83de-4d06793f7bf2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4e1759bb4df39ac403e2837c4083275a8b3436f5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798741"
---
# <span data-ttu-id="31f0e-103">支持通过 HTTP 进行客户端报告</span><span class="sxs-lookup"><span data-stu-id="31f0e-103">Support for Client Reporting over HTTP</span></span>


<span data-ttu-id="31f0e-104">App-v 客户端的版本4.6 现在支持在将客户端报告数据发送到发布服务器时使用 HTTP 通信。</span><span class="sxs-lookup"><span data-stu-id="31f0e-104">Version 4.6 of the App-V client now supports the use of HTTP communication when sending client reporting data to the publishing server.</span></span> <span data-ttu-id="31f0e-105">此功能支持以下情形：客户已实现一个自定义 HTTP （S）发布服务器，该服务器配置为收集和处理客户端数据。</span><span class="sxs-lookup"><span data-stu-id="31f0e-105">This feature supports scenarios where a customer has implemented a custom HTTP(S) publishing server that is configured to collect and process client data.</span></span>

<span data-ttu-id="31f0e-106">有关 HTTP 发布服务器的详细信息，请参阅</span><span class="sxs-lookup"><span data-stu-id="31f0e-106">For more information on HTTP publishing servers, see</span></span> <https://go.microsoft.com/fwlink/?LinkId=157426>

## <span data-ttu-id="31f0e-107">通过 HTTP 客户端报告</span><span class="sxs-lookup"><span data-stu-id="31f0e-107">Client Reporting over HTTP</span></span>


<span data-ttu-id="31f0e-108">在发布服务器的发布刷新响应 XML 中接收 "REPORTING =" TRUE "属性时，客户端开始收集数据。</span><span class="sxs-lookup"><span data-stu-id="31f0e-108">The client starts collecting data when it receives a “REPORTING=”TRUE””attribute in the publishing refresh response XML from the publishing server.</span></span> <span data-ttu-id="31f0e-109">收到此属性时，客户端会将任何累积的数据发送到发送发布刷新的发布服务器。</span><span class="sxs-lookup"><span data-stu-id="31f0e-109">When this attribute is received, the client sends any accumulated data to the publishing server that sent the publishing refresh.</span></span> <span data-ttu-id="31f0e-110">此过程的详细信息如下所示：</span><span class="sxs-lookup"><span data-stu-id="31f0e-110">The details of this process are as follows:</span></span>

-   <span data-ttu-id="31f0e-111">客户端将 HTTP GET 请求发送到发布服务器以进行发布刷新。</span><span class="sxs-lookup"><span data-stu-id="31f0e-111">The client sends an HTTP GET request to the publishing server for a publishing refresh.</span></span> <span data-ttu-id="31f0e-112">此消息的标题包含 "AppV-Op： Refresh" 自定义标头，自定义 HTTP （S）发布服务器使用该标头来标识消息类型。</span><span class="sxs-lookup"><span data-stu-id="31f0e-112">The header of this message contains an “AppV-Op:Refresh” custom header that the custom HTTP(S) publishing server uses to identify the message type.</span></span>

-   <span data-ttu-id="31f0e-113">然后，发布服务器将发送包含 "汇报 =" TRUE "" 值的发布刷新响应 XML。</span><span class="sxs-lookup"><span data-stu-id="31f0e-113">The publishing server then sends the publishing refresh response XML that contains a “REPORTING=”TRUE”” value.</span></span>

-   <span data-ttu-id="31f0e-114">然后，客户端将向发布服务器发送一个 HTTP POST 请求以及自上次刷新后收集的报告数据。</span><span class="sxs-lookup"><span data-stu-id="31f0e-114">The client then sends an HTTP POST request to the publishing server along with the reporting data that has been gathered since the previous refresh.</span></span> <span data-ttu-id="31f0e-115">此消息的标题包含 "AppV-Op： Report" 自定义标头，自定义 HTTP （S）发布服务器使用该标头来标识消息类型。</span><span class="sxs-lookup"><span data-stu-id="31f0e-115">The header of this message contains an “AppV-Op:Report” custom header that the custom HTTP(S) publishing server uses to identify the message type.</span></span>

<span data-ttu-id="31f0e-116">以下架构提供发送到服务器的程序包和应用程序数据的特定详细信息。</span><span class="sxs-lookup"><span data-stu-id="31f0e-116">The following schema gives specific details of the package and the application data that is sent to the server.</span></span>

```xml
<?xml version="1.0"?>
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">

    <xs:element name="CLIENT_DATA">
        <xs:complexType>
            <xs:all>
                <xs:element ref="PKG_LIST" minOccurs="1" maxOccurs="1"/>
                <xs:element ref="APP_RECORDS" minOccurs="1" maxOccurs="1"/>
            </xs:all>
            <!-- no regex for Ver because we want to allow tags like "Beta" -->
            <xs:attribute name="Ver" type="xs:normalizedString" use="required"/>
            <xs:attribute name="Host" type="xs:token" use="required"/>
            <xs:attribute name="CacheSize" type="xs:nonNegativeInteger" use="required"/>
            <xs:attribute name="CacheUsed" type="xs:nonNegativeInteger" use="required"/>
        </xs:complexType>
    </xs:element>

    <xs:element name="PKG_LIST">
        <xs:complexType>
            <xs:choice>
                <xs:element ref="PKG_DATA" minOccurs="0" maxOccurs="unbounded"/>
            </xs:choice>
        </xs:complexType>
    </xs:element>

    <xs:element name="PKG_DATA">
        <xs:complexType>
            <xs:attribute name="Name" type="xs:normalizedString" use="required"/>
            <xs:attribute name="Guid" type="xs:token" use="required"/>
            <xs:attribute name="Ver" type="xs:normalizedString" use="required"/>
            <xs:attribute name="VerGuid" type="xs:token" use="required"/>
            <xs:attribute name="Source" type="xs:normalizedString" use="required"/>
            <xs:attribute name="PctCached" use="required">
                <xs:simpleType>
                    <xs:restriction base="xs:nonNegativeInteger">
                        <xs:minInclusive value="0"/>
                        <xs:maxInclusive value="100"/>
                    </xs:restriction>
                </xs:simpleType>
            </xs:attribute>
        </xs:complexType>
    </xs:element>

    <xs:element name="APP_RECORDS">
         <xs:complexType>
            <xs:choice>
                <xs:element ref="APP_RECORD" minOccurs="0" maxOccurs="unbounded"/>
            </xs:choice>
        </xs:complexType>
   </xs:element>

    <xs:element name="APP_RECORD">
            <xs:attribute name="Name" type="xs:normalizedString" use="required"/>
            <xs:attribute name="Ver" type="xs:normalizedString" use="required"/>
            <xs:attribute name="Server" type="xs:normalizedString" use="required"/>
            <xs:attribute name="User" type="xs:normalizedString" use="required"/>
            <xs:attribute name="Launched" type="xs:dateTime" use="required"/>
            <xs:attribute name="Shutdown" type="xs:dateTime" use="optional"/>
    </xs:element>

</xs:schema>
```

 

 





