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
# 支持通过 HTTP 进行客户端报告


App-v 客户端的版本4.6 现在支持在将客户端报告数据发送到发布服务器时使用 HTTP 通信。 此功能支持以下情形：客户已实现一个自定义 HTTP （S）发布服务器，该服务器配置为收集和处理客户端数据。

有关 HTTP 发布服务器的详细信息，请参阅 <https://go.microsoft.com/fwlink/?LinkId=157426>

## 通过 HTTP 客户端报告


在发布服务器的发布刷新响应 XML 中接收 "REPORTING =" TRUE "属性时，客户端开始收集数据。 收到此属性时，客户端会将任何累积的数据发送到发送发布刷新的发布服务器。 此过程的详细信息如下所示：

-   客户端将 HTTP GET 请求发送到发布服务器以进行发布刷新。 此消息的标题包含 "AppV-Op： Refresh" 自定义标头，自定义 HTTP （S）发布服务器使用该标头来标识消息类型。

-   然后，发布服务器将发送包含 "汇报 =" TRUE "" 值的发布刷新响应 XML。

-   然后，客户端将向发布服务器发送一个 HTTP POST 请求以及自上次刷新后收集的报告数据。 此消息的标题包含 "AppV-Op： Report" 自定义标头，自定义 HTTP （S）发布服务器使用该标头来标识消息类型。

以下架构提供发送到服务器的程序包和应用程序数据的特定详细信息。

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

 

 





