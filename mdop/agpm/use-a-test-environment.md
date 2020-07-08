---
title: 使用测试环境
description: 使用测试环境
author: dansimp
ms.assetid: b8d7b3ee-030a-4b5b-8223-4a3276fd47a7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2299fb6eaf7c75f6841056f67a05fe025ea19bb7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801735"
---
# 使用测试环境


如果在部署到生产环境之前使用测试组织单位（OU）测试组策略对象（Gpo），则必须具有访问测试 OU 所需的权限。 测试 OU 的使用是可选的。

**使用测试 OU**

1.  当已签出 GPO 进行编辑时，请在**组策略管理控制台**中单击要在其中管理 gpo 的林和域中的 "**组策略" 对象**。

2.  单击要测试的 GPO 的签出副本。 名称前面将显示**\ [AGPM \]**。 （如果未列出，请单击 "**操作**"，然后单击 "**刷新**"。 按字母顺序对名称进行排序， **\ [AGPM \]** gpo 通常会显示在列表顶部。）

3.  将 GPO 拖放到测试 OU。

4.  在对话框中单击 **"确定"** ，询问是否在测试 OU 中创建指向 GPO 的链接。

### 其他注意事项

-   测试完成后，在 GPO 中签入将自动删除指向已签出 GPO 的已签出副本的链接。

### 其他参考资料

-   [编辑 GPO](editing-a-gpo.md)

 

 





