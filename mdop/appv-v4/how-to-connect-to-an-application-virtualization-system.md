---
title: 如何连接到 Application Virtualization System
description: 如何连接到 Application Virtualization System
author: dansimp
ms.assetid: ac38216c-5464-4c0b-a4d3-3949ba6358ac
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 30d60e187e1b7595fd0dce6641fa027a1df68f3d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801527"
---
# <span data-ttu-id="9bd46-103">如何连接到 Application Virtualization System</span><span class="sxs-lookup"><span data-stu-id="9bd46-103">How to Connect to an Application Virtualization System</span></span>


<span data-ttu-id="9bd46-104">必须先将应用程序虚拟化服务器管理控制台连接到应用程序虚拟化系统，然后才能使用管理控制台管理应用程序、文件类型关联、程序包、应用程序许可证、服务器组、提供程序策略和管理员。</span><span class="sxs-lookup"><span data-stu-id="9bd46-104">You must connect the Application Virtualization Server Management Console to an Application Virtualization System before you can use the management console to manage applications, file type associations, packages, application licenses, server groups, provider policies and administrators.</span></span> <span data-ttu-id="9bd46-105">以下过程概述了将控制台连接到应用程序虚拟化系统时必须遵循的步骤。</span><span class="sxs-lookup"><span data-stu-id="9bd46-105">The following procedure outlines the steps you must follow to connect the console to an Application Virtualization System.</span></span>

**<span data-ttu-id="9bd46-106">连接到应用程序虚拟化系统</span><span class="sxs-lookup"><span data-stu-id="9bd46-106">To connect to an Application Virtualization System</span></span>**

1. <span data-ttu-id="9bd46-107">右键单击 "**范围**" 窗格中的 "应用程序虚拟化系统" 节点，然后从弹出菜单中选择 "**连接到应用程序虚拟化系统**"。</span><span class="sxs-lookup"><span data-stu-id="9bd46-107">Right-click the Application Virtualization System node in the **Scope** pane, and select **Connect to Application Virtualization System** from the pop-up menu.</span></span>

   **<span data-ttu-id="9bd46-108">注意</span><span class="sxs-lookup"><span data-stu-id="9bd46-108">Note</span></span>**  
   <span data-ttu-id="9bd46-109">应用程序虚拟化服务器管理有三个组件：应用程序虚拟化管理控制台、管理 Web 服务和 SQL 数据存储。</span><span class="sxs-lookup"><span data-stu-id="9bd46-109">There are three components to Application Virtualization server management: the Application Virtualization Management Console, the Management Web Service, and the SQL Datastore.</span></span> <span data-ttu-id="9bd46-110">如果这些组件分布在不同的物理计算机上，则必须正确配置组件的安全性才能在系统之间进行通信。</span><span class="sxs-lookup"><span data-stu-id="9bd46-110">If these components are distributed across different physical machines, you must configure security properly for the components to communicate across the system.</span></span> <span data-ttu-id="9bd46-111">有关详细信息，请参阅以下手册和文章：</span><span class="sxs-lookup"><span data-stu-id="9bd46-111">For more information, see the following manuals and articles:</span></span>

   <span data-ttu-id="9bd46-112">[如何将服务器配置为受信任的委派](https://go.microsoft.com/fwlink/?LinkID=166682)（https://go.microsoft.com/fwlink/?LinkID=166682)</span><span class="sxs-lookup"><span data-stu-id="9bd46-112">[How to Configure the Server to be Trusted for Delegation](https://go.microsoft.com/fwlink/?LinkID=166682) (https://go.microsoft.com/fwlink/?LinkID=166682)</span></span>

   <span data-ttu-id="9bd46-113">[应用程序虚拟化系统的规划和部署指南](https://go.microsoft.com/fwlink/?LinkID=122063)（https://go.microsoft.com/fwlink/?LinkID=122063)</span><span class="sxs-lookup"><span data-stu-id="9bd46-113">[Planning and Deployment Guide for the Application Virtualization System](https://go.microsoft.com/fwlink/?LinkID=122063) (https://go.microsoft.com/fwlink/?LinkID=122063)</span></span>

   <span data-ttu-id="9bd46-114">[应用程序虚拟化系统的操作指南](https://go.microsoft.com/fwlink/?LinkID=133129)（https://go.microsoft.com/fwlink/?LinkID=133129)</span><span class="sxs-lookup"><span data-stu-id="9bd46-114">[Operations Guide for the Application Virtualization System](https://go.microsoft.com/fwlink/?LinkID=133129) (https://go.microsoft.com/fwlink/?LinkID=133129)</span></span>

   <span data-ttu-id="9bd46-115">Microsoft 知识库中的[文章 930472](https://go.microsoft.com/fwlink/?LinkId=114647) （https://go.microsoft.com/fwlink/?LinkId=114647)</span><span class="sxs-lookup"><span data-stu-id="9bd46-115">[Article 930472](https://go.microsoft.com/fwlink/?LinkId=114647) in the Microsoft Knowledge Base (https://go.microsoft.com/fwlink/?LinkId=114647)</span></span>

   <span data-ttu-id="9bd46-116">Microsoft 知识库中的[文章 930565](https://go.microsoft.com/fwlink/?LinkId=114648) （https://go.microsoft.com/fwlink/?LinkId=114648)</span><span class="sxs-lookup"><span data-stu-id="9bd46-116">[Article 930565](https://go.microsoft.com/fwlink/?LinkId=114648) in the Microsoft Knowledge Base (https://go.microsoft.com/fwlink/?LinkId=114648)</span></span>

     

2. <span data-ttu-id="9bd46-117">填写 "**连接到应用程序虚拟化系统**" 对话框中的字段：</span><span class="sxs-lookup"><span data-stu-id="9bd46-117">Complete the fields in the **Connect to Application Virtualization System** dialog box:</span></span>

   1. <span data-ttu-id="9bd46-118">**Web 服务主机名**—输入要连接到的应用程序虚拟化系统的名称，或输入**localhost**以连接到本地服务器。</span><span class="sxs-lookup"><span data-stu-id="9bd46-118">**Web Service Host Name**—Enter the name of the Application Virtualization System to which you want to connect, or enter **localhost** to connect to the local server.</span></span>

   2. <span data-ttu-id="9bd46-119">**使用安全连接**-如果要使用安全连接连接到服务器，请选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="9bd46-119">**Use Secure Connection**—Select this check box if you want to connect to the server with a secure connection.</span></span>

   3. <span data-ttu-id="9bd46-120">**Port**-输入要用于连接的端口号。</span><span class="sxs-lookup"><span data-stu-id="9bd46-120">**Port**—Enter the port number you want to use for the connection.</span></span> <span data-ttu-id="9bd46-121">**80**是默认的常规端口号， **443**是安全端口号。</span><span class="sxs-lookup"><span data-stu-id="9bd46-121">**80** is the default regular port number, and **443** is the secure-port number.</span></span>

   4. <span data-ttu-id="9bd46-122">**使用当前 Windows 帐户**-选择此单选按钮以使用当前的 windows 帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="9bd46-122">**Use Current Windows Account**—Select this radio button to use the current Windows account credentials.</span></span>

   5. <span data-ttu-id="9bd46-123">**指定 Windows 帐户**-如果你希望以其他用户身份连接到服务器，请选择此单选按钮。</span><span class="sxs-lookup"><span data-stu-id="9bd46-123">**Specify Windows Account**—Select this radio button when you want to connect to the server as a different user.</span></span>

   6. <span data-ttu-id="9bd46-124">**名称**-使用*DOMAIN\\username*或 username@domain 格式输入新用户的名称 <em> </em> 。</span><span class="sxs-lookup"><span data-stu-id="9bd46-124">**Name**—Enter the name of the new user by using either the *DOMAIN\\username* or the <em>username@domain</em> format.</span></span>

   7. <span data-ttu-id="9bd46-125">**密码**—输入与新用户对应的密码。</span><span class="sxs-lookup"><span data-stu-id="9bd46-125">**Password**—Enter the password that corresponds to the new user.</span></span>

3. <span data-ttu-id="9bd46-126">单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9bd46-126">Click **OK**.</span></span>

## <span data-ttu-id="9bd46-127">相关主题</span><span class="sxs-lookup"><span data-stu-id="9bd46-127">Related topics</span></span>


[<span data-ttu-id="9bd46-128">如何在 Application Virtualization Server Management Console 中执行管理任务</span><span class="sxs-lookup"><span data-stu-id="9bd46-128">How to Perform Administrative Tasks in the Application Virtualization Server Management Console</span></span>](how-to-perform-administrative-tasks-in-the-application-virtualization-server-management-console.md)

 

 





