---
title: 如何配置映像预暂存
description: 如何配置映像预暂存
author: dansimp
ms.assetid: 92781b5a-208f-45a4-a078-ee90cf9efd9d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 38ddb7a69845aa4dbcb9cbd16b84dedc04438732
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803962"
---
# 如何配置映像预暂存


**注意** 映像预转储仅适用于初始图像下载。 不支持图像更新。

 

## 如何配置映像预暂存


**配置映像预暂存**

1.  在客户端计算机上的 "映像存储目录" 下，为预暂存的映像创建一个文件夹，并将其命名为 " *Med-v 图像*"。

    **注意** 此文件夹必须称为 " *med-v" 图像*。

     

2.  在 "MED-V 图像" 文件夹中，创建一个子文件夹并将其命名为 " *PrestagedImages*"。

    **注意** 此文件夹必须名为*PrestagedImages*。

     

3.  若要将访问控制列表（ACL）安全性应用到*Med-v 图像*文件夹，请设置以下 ACL：

    **NT AUTHORITY\\Authenticated 用户：（OI）（CI）（特殊访问权限：）**

                                             **READ\_CONTROL**

                                    **SYNCHRONIZE**

                                    **FILE\_GENERIC\_READ**

                                    **FILE\_READ\_DATA**

    **                                 文件 \ _APPEND \ _DATA**

                                    **FILE\_READ\_EA**

                                    **FILE\_READ\_ATTRIBUTES**

    **NT AUTHORITY\\SYSTEM：（OI）（CI） F**

    **BUILTIN\\Administrators：（OI）（CI） F**

    **注意** 建议将 ACL 安全性应用到 " *Med-v 图像*" 文件夹。

     

4.  若要将 ACL 安全性应用于*PrestagedImages*文件夹，请设置以下 ACL：

    **NT AUTHORITY\\Authenticated 用户：（OI）（CI）（特殊访问权限：）**

    **READ \ _CONTROL**

    **同步**

    **文件 \ _GENERIC \ _READ**

    **文件 \ _READ \ _DATA**

    **文件 \ _READ \ _EA**

    **文件 \ _READ \ _ATTRIBUTES**

    **NT AUTHORITY\\SYSTEM：（OI）（CI） F**

    **BUILTIN\\Administrators：（OI）（CI） F**

    **注意** 建议将 ACL 安全性应用到*PrestagedImages*文件夹。

     

5.  将图像文件（CKM 和索引文件）推送到*PrestagedImages*文件夹。

    **注意** 将图像文件推送到 "预调试" 文件夹后，建议运行数据完整性检查并将文件标记为只读。

     

6.  在 MED-V 客户端安装中包括以下参数： *Client.MSI VMSFOLDER = "C:\\MED-V Images"*。

## 如何更新前阶段位置


**更新前阶段位置**

1.  注册表项*PrestagedImagesPath*指向默认图像位置。 它位于以下目录中：

    -   在 x86- `KEY_LOCAL_MACHINE\SOFTWARE\Kidaro`

    -   在 x64 `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432node`

2.  如果图像位于其他位置，请更改路径。

 

 





