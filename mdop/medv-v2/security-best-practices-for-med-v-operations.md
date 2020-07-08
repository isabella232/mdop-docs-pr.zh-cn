---
title: MED-V 操作的安全最佳方案
description: MED-V 操作的安全最佳方案
author: dansimp
ms.assetid: 231e2b9a-8b49-42fe-93b5-2ef12fe17bac
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4353a15c756dba8cf44f530c2077546e3f9288cd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803760"
---
# MED-V 操作的安全最佳方案


作为授权的管理员，您负责保护用户的信息，并在部署 MED-V 工作区期间和之后维护组织的安全。 特别是，请考虑以下问题。

**在 med-v 工作区中自定义 Internet Explorer**。 较早版本的 Windows 操作系统和 Internet Explorer 不如当前版本安全。 因此，MED-V 工作区中的 Internet Explorer 配置为阻止浏览和其他可能带来安全风险的活动。 此外，MED-V 工作区中 Internet Explorer 的 Internet 安全区域设置将设置为最高级别。 默认情况下，当你创建 MED-V 工作区程序包时，将在 MED-V 工作区包装器中设置这两个配置。

通过使用 Internet Explorer 管理工具包（IEAK）或通过更改 MED-V 工作区包装程序中的默认设置，你可以在 MED-V 工作区中自定义 Internet Explorer。 但是，请注意，如果在 MED-V 工作区中自定义 Internet Explorer 的方式使其不太安全，则可以将组织暴露给较早版本的 Internet Explorer 中提供的安全风险。

从安全角度来看，在 MED-V 工作区中管理 Internet Explorer 的最佳做法如下所示：

-   创建 MED-V 工作区程序包时，保留默认设置，以便将 MED-V 工作区中的 Internet Explorer 配置为阻止浏览和其他可能带来安全风险的活动。

-   创建 MED-V 工作区程序包时，保留默认设置，以便 Internet 安全区域的安全设置保持在最高级别。

-   配置企业代理或 Internet Explorer 内容顾问以阻止位于公司 intranet 外部的域。

**为共享计算机上的所有用户配置 MED-V 工作区。** 将 MED-V 工作区配置为可供共享计算机上的所有用户访问时，请注意将来宾虚拟机（VHD）放入一个位置，该位置将向该系统上的所有用户提供读写访问权限。

**配置用于加入域的代理帐户。** 配置用于将虚拟机加入域的代理帐户时，必须知道最终用户可以获取代理帐户凭据。 因此，必须采取必要的预防措施（如限制帐户用户权限），以防止最终用户使用凭据造成危害。

**Sysprep 配置。** 尽管 Sysprep.inf 文件在默认情况下已加密，但其内容可由任何已确定的最终用户（可成功登录到虚拟机）进行解密和读取。 这将引发安全问题，因为除了 Windows 产品密钥之外，Sysprep.inf 文件还可以包含凭据。

你可以通过设置受限帐户将虚拟机加入域并在配置 Sysprep 时指定该帐户的凭据来减少此风险。 或者，你也可以配置 Sysprep 和首次设置以在**参与**模式下运行，并要求最终用户提供其凭据以将虚拟机加入到域。

MED-V 最佳做法是指定在通过远程桌面连接（RDC）客户端通过远程桌面连接（RDC）客户端连接到来宾的帐户下运行 FtsCompletion.exe。

**最终用户身份验证。** 启用最终用户凭据的缓存可提供 MED-V 的最佳用户体验，但会带来可能会导致某人获得对最终用户凭据的访问权限的可能性。 减少这种风险的唯一方法是在不存储最终用户凭据的**Med-v 工作区包装**上指定。 有关最终用户身份验证的详细信息，请参阅[Med-v 最终用户的身份验证](authentication-of-med-v-end-users.md)。

## 相关主题


[操作疑难解答](operations-troubleshooting-medv2.md)

[Microsoft 企业版桌面虚拟化2。0](index.md)

 

 





