---
title: 设计 MED-V 映像存储库
description: 设计 MED-V 映像存储库
author: dansimp
ms.assetid: e153154d-2751-4990-b94d-a2d76242c15f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e0c59a0dd2d1b3a78bd211c6a6353a86c77d8fc2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803403"
---
# <span data-ttu-id="0eaee-103">设计 MED-V 映像存储库</span><span class="sxs-lookup"><span data-stu-id="0eaee-103">Design the MED-V Image Repositories</span></span>


<span data-ttu-id="0eaee-104">创建并打包 MED-V 图像后，它们可以存储在任何位置的文件服务器上。</span><span class="sxs-lookup"><span data-stu-id="0eaee-104">After MED-V images are created and packed, they can be stored on a file server in any location.</span></span> <span data-ttu-id="0eaee-105">文件可能由一个或多个 IIS 服务器通过 HTTP 或 HTTPS 发送。</span><span class="sxs-lookup"><span data-stu-id="0eaee-105">The files may be sent over HTTP or HTTPS by one or more IIS servers.</span></span> <span data-ttu-id="0eaee-106">图像存储库可由多个 MED-V 实例共享。</span><span class="sxs-lookup"><span data-stu-id="0eaee-106">The image repository can be shared by multiple MED-V instances.</span></span>

<span data-ttu-id="0eaee-107">若要设计图像存储库，必须首先确定如何将映像部署到每个客户端，以及该客户端是否需要本地映像存储库。</span><span class="sxs-lookup"><span data-stu-id="0eaee-107">To design the image repositories, you must first decide how the images will be deployed to each client and then whether that client requires a local image repository.</span></span> <span data-ttu-id="0eaee-108">然后，设计和放置每个存储库及其随附的 IIS 服务器。</span><span class="sxs-lookup"><span data-stu-id="0eaee-108">Each repository is then designed and placed, along with its accompanying IIS server.</span></span>

## <span data-ttu-id="0eaee-109">确定映像的部署方式</span><span class="sxs-lookup"><span data-stu-id="0eaee-109">Determine How Images Will Be Deployed</span></span>


<span data-ttu-id="0eaee-110">对于每个 MED-V 工作区，确定如何计划将 MED-V 映像部署到客户端。</span><span class="sxs-lookup"><span data-stu-id="0eaee-110">For each MED-V workspace, decide how you plan to deploy MED-V images to the client.</span></span> <span data-ttu-id="0eaee-111">这对于确定存储打包的图像所需的存储库（将放置这些资料库），然后设计这些存储库很重要。</span><span class="sxs-lookup"><span data-stu-id="0eaee-111">This is important in determining how many repositories are necessary to store the packed images, where those repositories will be placed, and then to design those repositories.</span></span>

<span data-ttu-id="0eaee-112">打包的图像可以通过以下方式进行部署：</span><span class="sxs-lookup"><span data-stu-id="0eaee-112">Packed images can be deployed in the following ways:</span></span>

-   <span data-ttu-id="0eaee-113">通过网络从包含文件服务器和 IIS 服务器的映像分发服务器下载。</span><span class="sxs-lookup"><span data-stu-id="0eaee-113">Downloaded over the network from an image distribution server, which comprises a file server and IIS server.</span></span>

-   <span data-ttu-id="0eaee-114">在可移动媒体（如 USB 驱动器或 DVD）上。</span><span class="sxs-lookup"><span data-stu-id="0eaee-114">On removable media, such as a USB drive or DVD.</span></span>

-   <span data-ttu-id="0eaee-115">使用企业软件分发中心预暂存到映像存储在客户端计算机上的目录。</span><span class="sxs-lookup"><span data-stu-id="0eaee-115">Pre-staged to an image store directory on the client computer using an enterprise software distribution center.</span></span>

<span data-ttu-id="0eaee-116">确定将使用哪种方法或方法将 MED-V 映像部署到每个客户端，以及该位置是否需要映像存储库。</span><span class="sxs-lookup"><span data-stu-id="0eaee-116">Decide which method, or methods, will be used to deploy MED-V images to each of the clients and whether the location will require an image repository.</span></span>

## <span data-ttu-id="0eaee-117">确定图像存储库的数量</span><span class="sxs-lookup"><span data-stu-id="0eaee-117">Determine the Number of Image Repositories</span></span>


<span data-ttu-id="0eaee-118">既然你已确定所需的最小存储库数，请在以下任一条件适用时添加更多：</span><span class="sxs-lookup"><span data-stu-id="0eaee-118">Now that you have determined the minimum number of repositories you need, add more if any of the following criteria apply:</span></span>

-   <span data-ttu-id="0eaee-119">用于分离 MED-V 映像的组织或监管理由，某些 MED-V 图像可能无法在同一存储库中共存。</span><span class="sxs-lookup"><span data-stu-id="0eaee-119">Organizational or regulatory reasons to separate the MED-V images—some MED-V images may not be able to coexist in the same repository.</span></span> <span data-ttu-id="0eaee-120">例如，敏感的个人数据可能需要服务器上的存储，该服务器仅适用于需要访问数据的有限的一组员工。</span><span class="sxs-lookup"><span data-stu-id="0eaee-120">For example, sensitive personal data may require storage on a server that is only available to a limited set of employees who need access to the data.</span></span>

-   <span data-ttu-id="0eaee-121">隔离网络中的客户端-如果将通过网络部署图像，请确定是否已隔离任何网络，并且需要单独的存储库。</span><span class="sxs-lookup"><span data-stu-id="0eaee-121">Clients in isolated networks—if images will be deployed over the network, determine whether any networks are isolated and require a separate repository.</span></span> <span data-ttu-id="0eaee-122">例如，组织通常将实验室网络与生产网络隔离。</span><span class="sxs-lookup"><span data-stu-id="0eaee-122">For example, organizations often isolate lab networks from production networks.</span></span>

-   <span data-ttu-id="0eaee-123">远程网络中的客户端-如果图像将通过网络部署，则某些客户端计算机可能会通过带宽不足的网络链接与存储库分开，以便在客户端加载 MED-V 工作区时提供充足的体验。</span><span class="sxs-lookup"><span data-stu-id="0eaee-123">Clients in remote networks—if images will be deployed over the network, some client machines may be separated from the repository by network links that have insufficient bandwidth to provide an adequate experience when a client loads a MED-V workspace.</span></span> <span data-ttu-id="0eaee-124">如有必要，可设计其他 MED-V 实例来满足此需求。</span><span class="sxs-lookup"><span data-stu-id="0eaee-124">If necessary, design additional MED-V instances to address this need.</span></span>

<span data-ttu-id="0eaee-125">将这些资料库添加到设计中。</span><span class="sxs-lookup"><span data-stu-id="0eaee-125">Add these repositories to the design.</span></span> <span data-ttu-id="0eaee-126">确定每个存储库的名称以及设计它的原因。</span><span class="sxs-lookup"><span data-stu-id="0eaee-126">Decide on a name for each repository and the reason for designing it.</span></span> <span data-ttu-id="0eaee-127">确定存储库将保留哪些 MED-V 映像以及哪些 MED-V 客户端将通过存储库中的图像加载 MED-V 工作区。</span><span class="sxs-lookup"><span data-stu-id="0eaee-127">Decide which MED-V images the repositories will hold and which MED-V clients will load MED-V workspaces with images from the repository.</span></span>

## <span data-ttu-id="0eaee-128">设计和放置图像存储库</span><span class="sxs-lookup"><span data-stu-id="0eaee-128">Design and Place the Image Repositories</span></span>


<span data-ttu-id="0eaee-129">当新图像可供客户端使用时，客户端将开始下载映像，这可能会同时开始。</span><span class="sxs-lookup"><span data-stu-id="0eaee-129">When a new image is available to clients, clients begin downloading the image, possibly simultaneously.</span></span> <span data-ttu-id="0eaee-130">这将为存储库创建高需求，并且必须在设计图像存储库时考虑。</span><span class="sxs-lookup"><span data-stu-id="0eaee-130">This creates a high demand on the repository and must be taken into account when designing the image repository.</span></span>

<span data-ttu-id="0eaee-131">对于每个存储库，确定它将存储的数据量。</span><span class="sxs-lookup"><span data-stu-id="0eaee-131">For each repository, determine the amount of data it will store.</span></span> <span data-ttu-id="0eaee-132">将存储在存储库中的图像的大小相加。</span><span class="sxs-lookup"><span data-stu-id="0eaee-132">Sum the sizes of images that will be stored in the repository.</span></span> <span data-ttu-id="0eaee-133">这是文件服务器上所需的磁盘空间的值。</span><span class="sxs-lookup"><span data-stu-id="0eaee-133">This is the value of the disk space required on the file server.</span></span>

<span data-ttu-id="0eaee-134">接下来，添加可从存储库下载 MED-V 映像的客户端数。</span><span class="sxs-lookup"><span data-stu-id="0eaee-134">Next, add up the number of clients that may download MED-V images from the repository.</span></span> <span data-ttu-id="0eaee-135">这是在将新的 MED-V 图像加载到存储库时可能出现的最大并发下载数。</span><span class="sxs-lookup"><span data-stu-id="0eaee-135">This is the maximum number of concurrent downloads that can occur when a new MED-V image is loaded into the repository.</span></span> <span data-ttu-id="0eaee-136">文件服务器必须设计有可满足此将创建的 IO 要求的磁盘子系统。</span><span class="sxs-lookup"><span data-stu-id="0eaee-136">The file server must be designed with a disk subsystem that can meet the IO demands this will create.</span></span>

<span data-ttu-id="0eaee-137">图像存储库可以与 MED-V 服务器和运行 SQL Server 的服务器或远程文件共享上的系统驻留在同一系统上。</span><span class="sxs-lookup"><span data-stu-id="0eaee-137">The image repository can reside on the same system as the MED-V server and the server running SQL Server, or on a remote file share.</span></span> <span data-ttu-id="0eaee-138">你还可以在 Windows Server2008 Hyper-v VM 中运行它。</span><span class="sxs-lookup"><span data-stu-id="0eaee-138">You can also run it in a Windows Server2008 Hyper-V VM.</span></span> <span data-ttu-id="0eaee-139">检查映像存储库将提供服务的客户端的网络位置，并将存储库放在具有足够带宽的网络位置，以满足这些客户端的服务级别期望值。</span><span class="sxs-lookup"><span data-stu-id="0eaee-139">Check the network location of the clients that the image repository will service, and place the repository in a network location where it will have sufficient bandwidth to meet the service level expectations of those clients.</span></span>

### <span data-ttu-id="0eaee-140">容错</span><span class="sxs-lookup"><span data-stu-id="0eaee-140">Fault Tolerance</span></span>

<span data-ttu-id="0eaee-141">如果图像存储库不可用，客户端将无法下载新的或更新的 MED-V 映像。</span><span class="sxs-lookup"><span data-stu-id="0eaee-141">If the image repository is unavailable, clients will not be able to download new or updated MED-V images.</span></span> <span data-ttu-id="0eaee-142">若要为文件服务器和容错磁盘设计容错选项，请参阅[基础结构规划和设计 MICROSOFT SQL server 2008](https://go.microsoft.com/fwlink/?LinkId=163302)指南。</span><span class="sxs-lookup"><span data-stu-id="0eaee-142">To design fault-tolerance options for the file server and fault-tolerant disks, see the [Infrastructure Planning and Design Microsoft SQL Server 2008](https://go.microsoft.com/fwlink/?LinkId=163302) guide.</span></span>

## <span data-ttu-id="0eaee-143">设计和放置 IIS 服务器</span><span class="sxs-lookup"><span data-stu-id="0eaee-143">Design and Place the IIS Servers</span></span>


<span data-ttu-id="0eaee-144">仅当客户使用 HTTP 或 HTTPS 通过网络下载图像文件时，此部分才会相关。</span><span class="sxs-lookup"><span data-stu-id="0eaee-144">This section is only relevant if clients will download image files over the network using HTTP or HTTPS.</span></span>

<span data-ttu-id="0eaee-145">IIS 服务器可以与 MED-V 服务器所在的同一系统和运行 SQL Server 的服务器共存。</span><span class="sxs-lookup"><span data-stu-id="0eaee-145">The IIS server can coexist on the same system as the MED-V server and the server running SQL Server.</span></span> <span data-ttu-id="0eaee-146">它还可以在 Windows Server2008 Hyper-v VM 中运行。</span><span class="sxs-lookup"><span data-stu-id="0eaee-146">It can also run in a Windows Server2008 Hyper-V VM.</span></span> <span data-ttu-id="0eaee-147">IIS 服务器基础结构必须具有足够的吞吐量，才能将图像提供给组织的服务级别预期内的客户端。</span><span class="sxs-lookup"><span data-stu-id="0eaee-147">The IIS server infrastructure must have sufficient throughput to deliver images to clients within the service level expectations of the organization.</span></span> <span data-ttu-id="0eaee-148">它必须设计有可满足此创建的 IO 要求的磁盘子系统。</span><span class="sxs-lookup"><span data-stu-id="0eaee-148">It must be designed with a disk subsystem that can meet the IO demands this creates.</span></span>

<span data-ttu-id="0eaee-149">对于每个映像存储库，对可以使用 IIS 下载 MED-V 映像的客户端数进行求和。</span><span class="sxs-lookup"><span data-stu-id="0eaee-149">For each image repository, sum the number of clients that may download MED-V images using IIS.</span></span> <span data-ttu-id="0eaee-150">这是在将图像加载到存储库时可能出现的最大并发下载数。</span><span class="sxs-lookup"><span data-stu-id="0eaee-150">This is the maximum number of concurrent downloads that can occur when an image is loaded into the repository.</span></span> <span data-ttu-id="0eaee-151">使用吞吐量和的服务级别期望值确定[了定义项目范围](define-the-project-scope.md)以规划 IIS 服务器基础结构的设计，并确定为存储库分配适当的带宽量。</span><span class="sxs-lookup"><span data-stu-id="0eaee-151">Use the throughput sum and the service level expectations determined in [Define the Project Scope](define-the-project-scope.md) to plan the design of the IIS server infrastructure and to determine the appropriate amount of bandwidth to allocate for the repository.</span></span>

<span data-ttu-id="0eaee-152">若要设计 IIS 基础结构，请参阅[基础结构规划和设计 Microsoft Internet 信息服务](https://go.microsoft.com/fwlink/?LinkId=160826)指南。</span><span class="sxs-lookup"><span data-stu-id="0eaee-152">To design the IIS infrastructure, see the [Infrastructure Planning and Design Microsoft Internet Information Services](https://go.microsoft.com/fwlink/?LinkId=160826) guide.</span></span>

### <span data-ttu-id="0eaee-153">容错</span><span class="sxs-lookup"><span data-stu-id="0eaee-153">Fault Tolerance</span></span>

<span data-ttu-id="0eaee-154">如果 IIS 服务器基础结构不可用，客户端将无法下载新的或更新的映像。</span><span class="sxs-lookup"><span data-stu-id="0eaee-154">If the IIS server infrastructure is unavailable, clients will not be able to download new or updated images.</span></span> <span data-ttu-id="0eaee-155">若要配置容错，基于 Windows Server2008 的 IIS 服务器可以放置在故障转移群集中。</span><span class="sxs-lookup"><span data-stu-id="0eaee-155">To configure fault tolerance, the Windows Server2008-based IIS server can be placed in a failover cluster.</span></span> <span data-ttu-id="0eaee-156">若要为 IIS 服务器基础结构设计容错，请参阅[基础结构规划和设计 Microsoft Internet 信息服务](https://go.microsoft.com/fwlink/?LinkId=160826)指南。</span><span class="sxs-lookup"><span data-stu-id="0eaee-156">To design the fault tolerance for the IIS server infrastructure, see the [Infrastructure Planning and Design Microsoft Internet Information Services](https://go.microsoft.com/fwlink/?LinkId=160826) guide.</span></span>

## <span data-ttu-id="0eaee-157">相关主题</span><span class="sxs-lookup"><span data-stu-id="0eaee-157">Related topics</span></span>


[<span data-ttu-id="0eaee-158">使用企业软件分发系统部署 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="0eaee-158">Deploying a MED-V Workspace Using an Enterprise Software Distribution System</span></span>](deploying-a-med-v-workspace-using-an-enterprise-software-distribution-system.md)

[<span data-ttu-id="0eaee-159">使用部署包部署 MED-V 工作区</span><span class="sxs-lookup"><span data-stu-id="0eaee-159">Deploying a MED-V Workspace Using a Deployment Package</span></span>](deploying-a-med-v-workspace-using-a-deployment-package.md)

 

 





