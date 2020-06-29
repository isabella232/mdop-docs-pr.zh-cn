---
title: 通过使用 MED-V 工作区包装程序管理 MED-V 工作区设置
description: 通过使用 MED-V 工作区包装程序管理 MED-V 工作区设置
author: dansimp
ms.assetid: e4b2c516-b9f8-44f9-9eae-caac6c2af3e7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9905c8da0f1f0678cce9587296526e8f04493c20
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803905"
---
# 通过使用 MED-V 工作区包装程序管理 MED-V 工作区设置


你可以使用 MED-V 工作区包装程序来管理 MED-V 工作区中的某些设置。

**管理 MED-V 工作区中的设置**

1. 若要打开**Med-v 工作区包装程序**，请依次单击 "**开始**"、"**所有程序**"、" **Microsoft 企业桌面虚拟化**"，然后单击 " **med-v 工作区包装程序**"。

2. 在**Med-v 工作区包装**主面板上，单击 "**管理设置**"。

3. 在 "**管理设置**" 窗口中，您可以配置以下 med-v 工作区设置：

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong>启动 MED-V-V 工作区</strong></p></td>
   <td align="left"><p>选择是在用户登录时启动 MED-V 工作区还是首次使用，或者让最终用户决定 MED-V 工作区何时启动。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p></p></td>
   <td align="left"><p>MED-V 工作区通过以下两种方式之一启动：最终用户登录时或首次执行需要 MED-V 的操作时，例如打开已发布的应用程序或输入需要重定向的 URL。</p>
   <p>你可以为最终用户定义此设置，也可以让最终用户控制 MED-V 的启动方式。</p>
   <div class="alert">
   <strong>注意</strong><br/><p>如果你指定最终用户决定，其体验的默认行为是 MED-V 工作区在登录时启动。 用户可以通过右键单击通知区域中的 MED-V 图标并选择 "Med-v 用户设置" 来更改默认值 <strong> </strong> 。 如果为最终用户定义此设置，则不能更改 MED-V 的启动方式。</p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>网络</strong></p></td>
   <td align="left"><p><strong> </strong> <strong> </strong> 为您的网络设置选择 "共享" 或 "桥接"。 默认值为 " <strong> 共享" </strong> 。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p></p></td>
   <td align="left"><p><strong>共享 </strong> - 的 med-v 工作区使用网络地址转换（NAT）将主机&#39;s IP 用于传出通信。</p>
   <p><strong>已桥接 </strong> - med-v 工作区有自己的网络地址，通常通过 DHCP 获得。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>存储凭据</strong></p></td>
   <td align="left"><p>选择是否要存储最终用户凭据。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p></p></td>
   <td align="left"><p>默认行为是禁用凭据存储，以便最终用户必须在每次登录时进行身份验证。</p>
   <div class="alert">
   <strong>重要提示</strong><br/><p>即使缓存最终用户的凭据可提供最佳用户体验，你也应该知道所涉及的风险。</p>
   <p>最终用户的域凭据以一种可还原的格式存储在 Windows 凭据管理器中。 攻击者可以编写一个程序来检索密码，从而获取用户凭据的访问权限。 您只能通过禁用存储最终用户凭据来减少此风险。</p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



4. 单击 "**另存为 ...** " 将更新的配置设置保存到指定文件夹中。 MED-V 将创建一个包含已更新设置的注册表文件。 使用组策略部署更新的注册表文件。 有关如何使用组策略的详细信息，请参阅[组策略软件安装](https://go.microsoft.com/fwlink/?LinkId=195931)（ https://go.microsoft.com/fwlink/?LinkId=195931) 。

   MED-V 还会在指定文件夹中创建可用于重新创建此更新的注册表文件的 Windows PowerShell 脚本。

## 相关主题


[管理 MED-V 工作区配置设置](managing-med-v-workspace-configuration-settings.md)

[管理 MED-V 工作区设置](manage-med-v-workspace-settings.md)









