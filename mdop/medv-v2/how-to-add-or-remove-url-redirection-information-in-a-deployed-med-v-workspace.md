---
title: 如何在已部署的 MED-V 工作区中添加或删除 URL 重定向信息
description: 如何在已部署的 MED-V 工作区中添加或删除 URL 重定向信息
author: dansimp
ms.assetid: bf55848d-bf77-452e-aaa5-4dd4868ff5bd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: f0892b16bfc10e6b3f28fe99c51c2c5cedb73d7f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803969"
---
# 如何在已部署的 MED-V 工作区中添加或删除 URL 重定向信息


若要在已部署的 MED-V 工作区中编辑 URL 重定向信息，建议使用组策略更新系统注册表。 虽然我们不建议这样做，但你也可以通过更新的 URL 重定向信息来重建和重新部署 MED-V 工作区。

该注册表项通常位于：

Computer\\HKEY\ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\MEDV\\v2\\UserExperience

必须存在以下多字符串值： `RedirectUrls`

的值数据 `RedirectUrls` 是在使用**Med-v 工作区包装**程序构建 med-v 工作区程序包时为重定向指定的所有 url 的列表。 有关详细信息，请参阅[创建 Med-v 工作区程序包](create-a-med-v-workspace-package.md)。

可以通过执行以下任务之一来添加和删除 URL 重定向信息：

-   [编辑 URL 重定向注册表项并使用组策略进行部署](#bkmk-editreg)

-   [编辑 URL 重定向文本文件并重建 MED-V 工作区](#bkmk-edittext)

<a href="" id="bkmk-editreg"></a>**使用组策略更新 URL 重定向信息**

1.  编辑名为的注册表项多字符串值 `RedirectUrls` 。 此值通常位于：

    Computer\\HKEY\ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\MEDV\\v2\\UserExperience

    如果你要将 Url 添加到注册表项，请每行输入一个 Url，在你构建 MED-V 工作区程序包时是必需的。 有关详细信息，请参阅[创建 Med-v 工作区程序包](create-a-med-v-workspace-package.md)。

2.  使用组策略部署更新的注册表项。 有关如何使用组策略的详细信息，请参阅[组策略软件安装](https://go.microsoft.com/fwlink/?LinkId=195931)（ https://go.microsoft.com/fwlink/?LinkId=195931) 。

**注意** 这种编辑 URL 重定向信息的方法是一种 MED-V 最佳做法。

 

<a href="" id="bkmk-edittext"></a>**使用更新的 URL 文本文件重建 MED-V 工作区**

-   从重定向列表中添加和删除 Url 的另一种方法是更新 URL 重定向文本文件，然后使用该文件构建新的 MED-V 工作区。 然后，你可以通过使用你的标准部署过程（如 ESD 系统）来重新部署 MED-V 工作区。

    **重要提示** 我们不建议此方法来编辑 URL 重定向信息。 此外，每当你重新部署 MED-V 工作区到你的企业时，第一次必须再次运行安装程序，并且虚拟机中保存的所有数据都将丢失。

     

## 相关主题


[如何测试 URL 重定向](how-to-test-url-redirection.md)

[管理部署到 MED-V 工作区的应用程序](managing-applications-deployed-to-med-v-workspaces.md)

[创建 MED-V 工作区程序包](create-a-med-v-workspace-package.md)

 

 





