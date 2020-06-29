---
title: MBAM 国际版本中的已知问题
description: MBAM 国际版本中的已知问题
author: dansimp
ms.assetid: bbf888dc-93c1-4323-b43c-0ded098e9b93
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: af32551135ff297d25930f94b40bf04c0fcaaafe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803838"
---
# <span data-ttu-id="8ce4d-103">MBAM 国际版本中的已知问题</span><span class="sxs-lookup"><span data-stu-id="8ce4d-103">Known Issues in the MBAM International Release</span></span>

<span data-ttu-id="8ce4d-104">本部分包含 Microsoft BitLocker 管理和监视（MBAM）国际版的已知问题。</span><span class="sxs-lookup"><span data-stu-id="8ce4d-104">This section contains known issues for Microsoft BitLocker Administration and Monitoring (MBAM) International Release.</span></span>

## <span data-ttu-id="8ce4d-105">MBAM 国际版本中的已知问题</span><span class="sxs-lookup"><span data-stu-id="8ce4d-105">Known Issues in the MBAM International Release</span></span>

### <span data-ttu-id="8ce4d-106">安装过程未指定更新</span><span class="sxs-lookup"><span data-stu-id="8ce4d-106">The Installation Process Does Not Specify Update</span></span>

<span data-ttu-id="8ce4d-107">更新 Microsoft BitLocker 管理和监视服务器或服务器时，安装程序不会声明正在安装更新。</span><span class="sxs-lookup"><span data-stu-id="8ce4d-107">Upon updating the Microsoft BitLocker Administration and Monitoring server or servers, the Setup program does not state that an update is being installed.</span></span>

<span data-ttu-id="8ce4d-108">**解决方法**：无。</span><span class="sxs-lookup"><span data-stu-id="8ce4d-108">**Workaround**: None.</span></span>

### <span data-ttu-id="8ce4d-109">用于管理和监视服务器角色的证书</span><span class="sxs-lookup"><span data-stu-id="8ce4d-109">Certificates Used for the Administration and Monitoring Server Role</span></span>

<span data-ttu-id="8ce4d-110">如果在 MBAM 服务器之间使用证书进行身份验证，则在更新 MBAM 管理和监视服务器之后，必须确保该证书有效且未被吊销或已过期。</span><span class="sxs-lookup"><span data-stu-id="8ce4d-110">If you are using a certificate for authentication between MBAM servers, after updating the MBAM Administration and Monitoring server you must ensure that the certificate is valid and not revoked or expired.</span></span>

<span data-ttu-id="8ce4d-111">**解决方法**：无。</span><span class="sxs-lookup"><span data-stu-id="8ce4d-111">**Workaround**: None.</span></span>

### <span data-ttu-id="8ce4d-112">MBAM Svclog 文件填充磁盘空间</span><span class="sxs-lookup"><span data-stu-id="8ce4d-112">MBAM Svclog File Filling Disk Space</span></span>

<span data-ttu-id="8ce4d-113">如果你已关注[知识库文章 2668170](https://go.microsoft.com/fwlink/?LinkID=247277)，则可能需要在安装此更新后重复 KB 步骤。</span><span class="sxs-lookup"><span data-stu-id="8ce4d-113">If you have followed [Knowledge Base article 2668170](https://go.microsoft.com/fwlink/?LinkID=247277), you might have to repeat the KB steps after you install this update.</span></span>

<span data-ttu-id="8ce4d-114">**解决方法**：无。</span><span class="sxs-lookup"><span data-stu-id="8ce4d-114">**Workaround**: None.</span></span>

## <span data-ttu-id="8ce4d-115">相关主题</span><span class="sxs-lookup"><span data-stu-id="8ce4d-115">Related topics</span></span>

[<span data-ttu-id="8ce4d-116">部署 MBAM 1.0 语言版本更新</span><span class="sxs-lookup"><span data-stu-id="8ce4d-116">Deploying the MBAM 1.0 Language Release Update</span></span>](deploying-the-mbam-10-language-release-update.md)

 

 





