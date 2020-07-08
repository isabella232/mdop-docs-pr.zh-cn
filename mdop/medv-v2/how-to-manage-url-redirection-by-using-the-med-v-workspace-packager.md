---
title: 如何通过使用 MED-V 工作区包装程序管理 URL 重定向
description: 如何通过使用 MED-V 工作区包装程序管理 URL 重定向
author: dansimp
ms.assetid: 1a8d25af-479f-42d3-bf5f-c7fd974bbf8c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 88167923e3bd47f2a3b0b3ada5e818715740dbe3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803644"
---
# 如何通过使用 MED-V 工作区包装程序管理 URL 重定向


你可以使用 MED-V 工作区包装程序管理 MED-V 工作区中的 URL 重定向。

**在 MED-V 工作区中管理 web 地址重定向**

1.  若要打开**Med-v 工作区包装程序**，请依次单击 "**开始**"、"**所有程序**"、" **Microsoft 企业桌面虚拟化**"，然后单击 " **med-v 工作区包装程序**"。

2.  在**Med-v 工作区包装**程序主面板上，单击 "**管理 Web 重定向**"。

3.  在 "**管理 Web 重定向**" 窗口中，可以键入、粘贴或导入在 med-v 工作区中重定向到 Internet Explorer 的 url 的列表。

    **注意**  
    MED-V 中的 URL 重定向仅支持 HTTP 和 HTTPS 协议。 MED-V 不提供对 FTP 或任何其他协议的支持。



~~~
Enter each web address on a single line, for example:

http://www.contoso.com/webapps/webapp1

http://www.contoso.com/webapps/webapp2

http://\*.contoso.com

http://www.contoso.com/webapps/\*

**Important**  
If you import a text file that includes a URL that uses special characters (such as ~ ! @ \# and so on), make sure that you specify UTF-8 encoding when you save the text file. Special characters do not import correctly into the MED-V Workspace Packager if the text file was saved using the default ANSI encoding.
~~~



4. 单击 "**另存为 ...** " 将更新后的 URL 重定向文件保存在指定文件夹中。 MED-V 将创建一个包含更新的 URL 重定向信息的注册表文件。 使用组策略部署更新的注册表项。 有关如何使用组策略的详细信息，请参阅[组策略软件安装](https://go.microsoft.com/fwlink/?LinkId=195931)（ https://go.microsoft.com/fwlink/?LinkId=195931) 。

   MED-V 还会在指定文件夹中创建可用于重新创建更新的 MED-V 工作区程序包的 Windows PowerShell 脚本。

## 相关主题


[如何在已部署的 MED-V 工作区中添加或删除 URL 重定向信息](how-to-add-or-remove-url-redirection-information-in-a-deployed-med-v-workspace.md)

[管理 MED-V URL 重定向](manage-med-v-url-redirection.md)









