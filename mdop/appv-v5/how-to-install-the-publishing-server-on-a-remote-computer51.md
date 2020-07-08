---
title: 如何在远程计算机上安装发布服务器
description: 如何在远程计算机上安装发布服务器
author: dansimp
ms.assetid: 1c903f78-0558-458d-a149-d5f6fb55aefb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1a085d68305057538228599e35dd9500957342ba
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798431"
---
# 如何在远程计算机上安装发布服务器


使用以下过程在单独的计算机上安装发布服务器。 在执行以下过程之前，请确保数据库和管理服务器可用。

**在单独的计算机上安装发布服务器**

1. 将 app-v 5.1 服务器安装文件复制到要在其上安装它的计算机上。 若要启动 app-v 5.1 服务器安装，请右键单击并以管理员身份运行**appv\_server\_setup.exe** 。 单击**安装**。

2. 在 "**入门**" 页面上，查看并接受许可条款，然后单击 "**下一步**"。

3. 在 "**使用 Microsoft 更新" 帮助保持计算机的安全和最新**页面上，若要启用 Microsoft 更新，请选择 "**当我检查更新时使用 Microsoft 更新" （推荐）。** 若要禁用 Microsoft 更新，请选择 "**我不想使用 Microsoft 更新**"。 单击“下一步”****。

4. 在**功能选择**页面上，选择 "**发布服务器**" 复选框，然后单击 "**下一步**"。

5. 在 "**安装位置**" 页面上，接受默认位置，然后单击 "**下一步**"。

6. 在 "**配置发布服务器配置**" 页面上，指定以下项目：

   -   发布服务器将连接到的管理服务的 URL。 例如， **http://ManagementServerName:12345** 。

   -   指定要用于发布服务的网站名称。 如果您没有自定义名称，请接受默认值。

   -   对于**端口绑定**，请指定将由 app-v 5.1 使用的唯一端口号（例如**54321**）。

7. 在 "**准备安装**" 页面上，单击 "**安装**"。

8. 安装完成后，发布服务器必须注册到管理服务器。 在 App-v 5.1 管理控制台中，使用以下步骤注册服务器：

   1.  打开 app-v 5.1 管理服务器控制台。

   2.  在左窗格中，选择 "**服务器**"，然后选择 "**注册新服务器**"。

   3.  键入此服务器的名称和说明（如果需要），然后单击 "**添加**"。

9. 若要验证发布服务器是否正常运行，应将程序包导入管理服务器、将程序包 entitle 到 AD 组并发布程序包。 使用 internet 浏览器打开以下 URL： <strong> http://publishingserver:pubport </strong> 。 如果服务器运行的信息与以下内容类似，将显示：

   ```xml
   <Publishing Protocol="1.0">
     <Packages>
       <Package PackageId="28115343-06e2-44dc-a327-3a0b9b868bda" VersionId="5d03c08f-51dc-4026-8cf9-15ebe3d65a72" PackageUrl="\\server\share\file.appv" />
     </Packages>
     <NoGroup>
       <Package PackageId="28115343-06e2-44dc-a327-3a0b9b868bda" />
     </NoGroup>
   </Publishing>
   ```

   已**获得有关 app-v 的建议**？ 在[此处](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)添加或投票建议。 **遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题


[部署 App-V 5.1](deploying-app-v-51.md)

 

 





