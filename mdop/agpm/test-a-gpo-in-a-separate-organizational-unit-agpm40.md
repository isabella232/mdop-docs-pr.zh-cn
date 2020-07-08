---
title: 在单独的组织单位中测试 GPO
description: 在单独的组织单位中测试 GPO
author: dansimp
ms.assetid: 9a9e6d22-74e6-41d8-ac2f-12a1b76ad5a0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 509721fdd775c8669399549f6dcc29cb9ebaea2f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801744"
---
# 在单独的组织单位中测试 GPO


如果在部署到生产环境之前使用测试组织单位（OU）测试同一域内的组策略对象（Gpo），则必须具有访问测试 OU 所需的权限。 使用测试 OU 是可选的。

**使用测试 OU**

1.  虽然已签出 GPO 进行编辑，但在**组策略管理控制台**中，单击要在其中管理 gpo 的林和域中的 "**组策略" 对象**。

2.  单击要测试的 GPO 的签出副本。 名称前面将显示**\ [AGPM \]**。 （如果未列出，请单击 "**操作**"，然后单击 "**刷新**"。 按字母顺序对名称进行排序， **\ [AGPM \]** gpo 通常会显示在列表顶部。）

3.  将 GPO 拖动到测试 OU。

4.  在询问是否在测试 OU 中创建 GPO 链接的对话框中单击 **"确定"** 。

### 其他注意事项

-   测试完成后，在 GPO 中签入将自动删除指向已签出 GPO 的已签出副本的链接。

### 其他参考资料

-   [使用测试环境](using-a-test-environment.md)

 

 





