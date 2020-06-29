---
title: 如何配置用户权限
description: 如何配置用户权限
author: dansimp
ms.assetid: 54e69f46-b028-4ad1-9b80-f06ef5c8f559
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 3c2581a9f9dddcbc63682d356c777a24222dd62f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801535"
---
# <span data-ttu-id="ac163-103">如何配置用户权限</span><span class="sxs-lookup"><span data-stu-id="ac163-103">How to Configure User Permissions</span></span>


<span data-ttu-id="ac163-104">你可以通过编辑**权限**注册表项（HKEY \ _LOCAL \ _MACHINE \\software\\microsoft\\softgrid\\4.5\\client\\permissions）下的键值，为没有管理权限的用户启用和禁用某些操作。</span><span class="sxs-lookup"><span data-stu-id="ac163-104">You can enable and disable some actions for users who do not have administrative rights by editing the key values under the **Permissions** registry key (HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Permissions).</span></span> <span data-ttu-id="ac163-105">此密钥主要用于帮助防止用户犯错误，而不是为了提供任何特殊安全性，因为具有管理权限的用户可以编辑这些键值中的任何一个值。</span><span class="sxs-lookup"><span data-stu-id="ac163-105">This key is primarily designed to help prevent users from making mistakes rather than to provide any special security, because users with administrative rights can edit any of these key values.</span></span> <span data-ttu-id="ac163-106">以下过程是有关如何更改键值的示例。</span><span class="sxs-lookup"><span data-stu-id="ac163-106">The following procedures are examples of how to change the key values.</span></span> <span data-ttu-id="ac163-107">有关应用程序虚拟化（app-v）客户端注册表项和值的详细信息，请参阅 <https://go.microsoft.com/fwlink/?LinkId=121528> 。</span><span class="sxs-lookup"><span data-stu-id="ac163-107">For more information about the Application Virtualization (App-V) Client registry keys and values, see <https://go.microsoft.com/fwlink/?LinkId=121528>.</span></span>

**<span data-ttu-id="ac163-108">更改用户权限</span><span class="sxs-lookup"><span data-stu-id="ac163-108">To change user permissions</span></span>**

1.  <span data-ttu-id="ac163-109">若要使用户可以选择在脱机模式下运行客户端，请将以下键值设置为1：</span><span class="sxs-lookup"><span data-stu-id="ac163-109">To enable the users to choose to run the client in offline mode, set the following key value to 1:</span></span>

    <span data-ttu-id="ac163-110">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Permissions\\ToggleOfflineMode</span><span class="sxs-lookup"><span data-stu-id="ac163-110">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Permissions\\ToggleOfflineMode</span></span>

2.  <span data-ttu-id="ac163-111">若要使用户能够通过用户界面查看所有应用程序，请将以下项值设置为1。</span><span class="sxs-lookup"><span data-stu-id="ac163-111">To enable the users to view all applications through the user interface, set the following key value to 1.</span></span> <span data-ttu-id="ac163-112">将该值设置为0（零）允许用户仅查看可用的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ac163-112">Setting the value to 0 (zero) allows the users to see only the applications that are available to them.</span></span>

    <span data-ttu-id="ac163-113">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Permissions\\ViewAllApplications</span><span class="sxs-lookup"><span data-stu-id="ac163-113">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Permissions\\ViewAllApplications</span></span>

## <span data-ttu-id="ac163-114">相关主题</span><span class="sxs-lookup"><span data-stu-id="ac163-114">Related topics</span></span>


[<span data-ttu-id="ac163-115">如何使用命令行配置 App-V Client 注册表设置</span><span class="sxs-lookup"><span data-stu-id="ac163-115">How to Configure the App-V Client Registry Settings by Using the Command Line</span></span>](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

[<span data-ttu-id="ac163-116">Application Virtualization Client 中的用户访问权限</span><span class="sxs-lookup"><span data-stu-id="ac163-116">User Access Permissions in Application Virtualization Client</span></span>](user-access-permissions-in-application-virtualization-client.md)

 

 





