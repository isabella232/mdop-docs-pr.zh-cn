---
title: 配置 AGPM 的电子邮件安全性
description: 配置 AGPM 的电子邮件安全性
author: dansimp
ms.assetid: 4850ed8e-a1c6-43f0-95c5-853aa66a94ae
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3694662fd0ed81edacd16cf55ac9760b1be2ba97
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802036"
---
# <span data-ttu-id="de19b-103">配置 AGPM 的电子邮件安全性</span><span class="sxs-lookup"><span data-stu-id="de19b-103">Configure E-Mail Security for AGPM</span></span>


<span data-ttu-id="de19b-104">默认情况下，由于高级组策略管理（AGPM）中的操作未加密，并且通过 SMTP 端口25发送电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="de19b-104">By default, e-mail notifications sent because of actions in Advanced Group Policy Management (AGPM) are not encrypted and are sent through SMTP port 25.</span></span> <span data-ttu-id="de19b-105">但是，你可以通过使用注册表设置指定是否使用安全套接字层（SSL）加密和要使用的 SMTP 端口来配置 AGPM 的电子邮件安全性。</span><span class="sxs-lookup"><span data-stu-id="de19b-105">However, you can configure e-mail security for AGPM by using registry settings to specify whether to use Secure Sockets Layer (SSL) encryption and which SMTP port to use.</span></span>

<span data-ttu-id="de19b-106">通过加密 AGPM 电子邮件通知，你可以更好地保护可能会泄漏有关组织安全的敏感信息的用户。</span><span class="sxs-lookup"><span data-stu-id="de19b-106">By encrypting AGPM e-mail notifications, you can better protect those that could reveal sensitive information about your organization’s security.</span></span> <span data-ttu-id="de19b-107">如果通过远程邮件服务器中继电子邮件通知，并且可能需要某些合规性规章，则建议使用加密电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="de19b-107">Encrypting e-mail notifications is recommended when they are being relayed through remote mail servers, and may be required by some compliance regulations.</span></span>

<span data-ttu-id="de19b-108">**小心** 错误地编辑注册表可能会严重损坏你的系统。</span><span class="sxs-lookup"><span data-stu-id="de19b-108">**Caution** Incorrectly editing the registry may severely damage your system.</span></span> <span data-ttu-id="de19b-109">在对注册表进行更改之前，应备份计算机上的任何重要数据。</span><span class="sxs-lookup"><span data-stu-id="de19b-109">Before making changes to the registry, you should back up any valued data on the computer.</span></span>

 

<span data-ttu-id="de19b-110">具有 AGPM 管理员（完全控制）角色的用户帐户、创建在这些过程中使用的组策略对象（GPO）的审批者的用户帐户，或者需要使用 AGPM 中的必需权限的用户帐户才能完成这些过程。</span><span class="sxs-lookup"><span data-stu-id="de19b-110">A user account that has the AGPM Administrator (Full Control) role, the user account of the Approver who created the Group Policy Object (GPO) used in these procedures, or a user account that has the necessary permissions in AGPM is required to complete these procedures.</span></span> <span data-ttu-id="de19b-111">查看本主题中 "其他注意事项" 中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="de19b-111">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="de19b-112">使用组策略首选项配置 AGPM 的电子邮件安全性</span><span class="sxs-lookup"><span data-stu-id="de19b-112">To configure e-mail security for AGPM by using Group Policy preferences</span></span>**

1.  <span data-ttu-id="de19b-113">在**组策略管理控制台**树中，编辑应用到要为其配置电子邮件安全的所有 AGPM 服务器的 GPO。</span><span class="sxs-lookup"><span data-stu-id="de19b-113">In the **Group Policy Management Console** tree, edit a GPO that is applied to all AGPM Servers for which you want to configure e-mail security.</span></span> <span data-ttu-id="de19b-114">（有关详细信息，请参阅[编辑 GPO](editing-a-gpo-agpm30ops.md)。）</span><span class="sxs-lookup"><span data-stu-id="de19b-114">(For more information, see [Editing a GPO](editing-a-gpo-agpm30ops.md).)</span></span>

2.  <span data-ttu-id="de19b-115">在 "**组策略管理编辑器**" 窗口中，展开 "**计算机配置**"、"**首选项**"、" **Windows 设置**" 和 "**注册表**文件夹"。</span><span class="sxs-lookup"><span data-stu-id="de19b-115">In the **Group Policy Management Editor** window, expand the **Computer Configuration**, **Preferences**, **Windows Settings**, and **Registry** folders.</span></span>

3.  <span data-ttu-id="de19b-116">在控制台树中，右键单击 "**注册表**"，指向 "**新建**"，单击 "**收集项目**"，然后键入 " **AGPM 电子邮件安全性**"。</span><span class="sxs-lookup"><span data-stu-id="de19b-116">In the console tree, right-click **Registry**, point to **New**, click **Collection Item**, and type **AGPM e-mail security**.</span></span>

4.  <span data-ttu-id="de19b-117">创建一个注册表首选项以打开加密：</span><span class="sxs-lookup"><span data-stu-id="de19b-117">Create a Registry preference item to turn on encryption:</span></span>

    1.  <span data-ttu-id="de19b-118">在控制台树中，右键单击 " **AGPM 电子邮件安全性**"，指向 "**新建**"，然后单击 "**注册表项**"。</span><span class="sxs-lookup"><span data-stu-id="de19b-118">In the console tree, right-click **AGPM e-mail security**, point to **New**, and then click **Registry Item**.</span></span>

    2.  <span data-ttu-id="de19b-119">在 "**新建注册表属性**" 对话框中，选择 "**更新**" 操作。</span><span class="sxs-lookup"><span data-stu-id="de19b-119">In the **New Registry Properties** dialog box, select the **Update** action.</span></span>

    3.  <span data-ttu-id="de19b-120">对于**配置单元**，请选择 " **HKEY \ _LOCAL \ _MACHINE**"。</span><span class="sxs-lookup"><span data-stu-id="de19b-120">For **Hive**, select **HKEY\_LOCAL\_MACHINE**.</span></span>

    4.  <span data-ttu-id="de19b-121">对于 "**密钥路径**"，请键入**SOFTWARE\\Microsoft\\AGPM**。</span><span class="sxs-lookup"><span data-stu-id="de19b-121">For **Key Path**, type **SOFTWARE\\Microsoft\\AGPM**.</span></span>

    5.  <span data-ttu-id="de19b-122">对于 "**值名称**"，请键入**EncryptSmtp**。</span><span class="sxs-lookup"><span data-stu-id="de19b-122">For **Value name**, type **EncryptSmtp**.</span></span>

    6.  <span data-ttu-id="de19b-123">对于 "**值类型**"，请选择 " **REG \ _DWORD**"。</span><span class="sxs-lookup"><span data-stu-id="de19b-123">For **Value type**, select **REG\_DWORD**.</span></span>

    7.  <span data-ttu-id="de19b-124">对于 "**基本**"，选择 "**小数**"，对于 "**数值数据**"，键入**1**以使用 SSL 加密，或键入 " **0** " 以使用 SSL 加密</span><span class="sxs-lookup"><span data-stu-id="de19b-124">For **Base**, select **Decimal**, and for **Value data**, type **1** to use SSL encryption, or **0** to let e-mail to be sent without encryption.</span></span> <span data-ttu-id="de19b-125">默认情况下，发送电子邮件时不加密。</span><span class="sxs-lookup"><span data-stu-id="de19b-125">By default, e-mail is sent without encryption.</span></span>

    8.  <span data-ttu-id="de19b-126">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="de19b-126">Click **OK**.</span></span>

5.  <span data-ttu-id="de19b-127">创建一个注册表首选项以指定 SMTP 端口：</span><span class="sxs-lookup"><span data-stu-id="de19b-127">Create a Registry preference item to specify the SMTP port:</span></span>

    1.  <span data-ttu-id="de19b-128">在控制台树中，右键单击 " **AGPM 电子邮件安全性**"，指向 "**新建**"，然后单击 "**注册表项**"。</span><span class="sxs-lookup"><span data-stu-id="de19b-128">In the console tree, right-click **AGPM E-mail security**, point to **New**, and then click **Registry Item**.</span></span>

    2.  <span data-ttu-id="de19b-129">在 "**新建注册表属性**" 对话框中，选择 "**更新**" 操作。</span><span class="sxs-lookup"><span data-stu-id="de19b-129">In the **New Registry Properties** dialog box, select the **Update** action.</span></span>

    3.  <span data-ttu-id="de19b-130">对于**配置单元**，请选择 " **HKEY \ _LOCAL \ _MACHINE**"。</span><span class="sxs-lookup"><span data-stu-id="de19b-130">For **Hive**, select **HKEY\_LOCAL\_MACHINE**.</span></span>

    4.  <span data-ttu-id="de19b-131">在 "**密钥路径**" 对话框中，键入**SOFTWARE\\Microsoft\\AGPM**。</span><span class="sxs-lookup"><span data-stu-id="de19b-131">For **Key Path** dialog box, type **SOFTWARE\\Microsoft\\AGPM**.</span></span>

    5.  <span data-ttu-id="de19b-132">对于 "**值名称**"，请键入**SmtpPort**。</span><span class="sxs-lookup"><span data-stu-id="de19b-132">For **Value name**, type **SmtpPort**.</span></span>

    6.  <span data-ttu-id="de19b-133">对于 "**值类型**"，请选择 " **REG \ _DWORD**"。</span><span class="sxs-lookup"><span data-stu-id="de19b-133">For **Value type**, select **REG\_DWORD**.</span></span>

    7.  <span data-ttu-id="de19b-134">对于 "**基本**"，选择 "**小数**"，对于 "**数值数据**"，键入 SMTP 端口的端口号。</span><span class="sxs-lookup"><span data-stu-id="de19b-134">For **Base**, select **Decimal**, and for **Value data**, type a port number for the SMTP port.</span></span> <span data-ttu-id="de19b-135">默认情况下，如果未启用加密，则 SMTP 端口为端口25，如果启用了 SSL 加密，则为端口587。</span><span class="sxs-lookup"><span data-stu-id="de19b-135">By default, the SMTP port is port 25 if encryption is not enabled or port 587 if SSL encryption is enabled.</span></span>

    8.  <span data-ttu-id="de19b-136">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="de19b-136">Click **OK**.</span></span>

6.  <span data-ttu-id="de19b-137">关闭 "**组策略管理编辑器**" 窗口，然后签入并部署该 GPO。</span><span class="sxs-lookup"><span data-stu-id="de19b-137">Close the **Group Policy Management Editor** window, and then check in and deploy the GPO.</span></span> <span data-ttu-id="de19b-138">有关详细信息，请参阅[部署 GPO](deploy-a-gpo-agpm30ops.md)。</span><span class="sxs-lookup"><span data-stu-id="de19b-138">For more information, see [Deploy a GPO](deploy-a-gpo-agpm30ops.md).</span></span>

### <span data-ttu-id="de19b-139">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="de19b-139">Additional considerations</span></span>

-   <span data-ttu-id="de19b-140">你必须能够编辑和部署 GPO，才能使用组策略首选项配置注册表设置。</span><span class="sxs-lookup"><span data-stu-id="de19b-140">You must be able to edit and deploy a GPO to configure registry settings by using Group Policy Preferences.</span></span> <span data-ttu-id="de19b-141">有关其他详细信息，请参阅[编辑 gpo](editing-a-gpo-agpm30ops.md)和[部署 gpo](deploy-a-gpo-agpm30ops.md) 。</span><span class="sxs-lookup"><span data-stu-id="de19b-141">See [Editing a GPO](editing-a-gpo-agpm30ops.md) and [Deploy a GPO](deploy-a-gpo-agpm30ops.md) for additional detail.</span></span>

### <span data-ttu-id="de19b-142">其他参考资料</span><span class="sxs-lookup"><span data-stu-id="de19b-142">Additional references</span></span>

-   [<span data-ttu-id="de19b-143">配置高级组策略管理</span><span class="sxs-lookup"><span data-stu-id="de19b-143">Configuring Advanced Group Policy Management</span></span>](configuring-advanced-group-policy-management.md)

 

 





