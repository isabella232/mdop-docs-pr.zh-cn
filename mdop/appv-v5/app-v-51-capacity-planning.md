---
title: App-V 5.1 容量计划
description: App-V 5.1 容量计划
author: dansimp
ms.assetid: 7a98062f-5a60-49d6-ab40-dc6057e1dd5a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b152536b3c61e47f3fda84489b1e102c285e01c6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798632"
---
# App-V 5.1 容量计划


以下建议可用作基线，以帮助确定适合你的组织的 app-v 5.1 基础结构的容量计划信息。

**重要提示** 仅将本部分中的信息用作规划 app-v 5.1 部署的常规指南。 你的系统容量要求取决于你的硬件和应用程序环境的具体详细信息。 此外，本文档中显示的性能数字是示例，你的结果可能会有所不同。

 

## 确定项目范围


在设计 app-v 5.1 基础结构之前，必须确定项目的范围。 范围包括确定哪些应用程序将在哪些应用程序中可用，还包括确定目标用户及其位置。 此信息将帮助确定应实现哪种类型的 App-v 5.1 基础结构。 有关项目范围的决策必须基于你的组织的特定需求。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">任务</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>确定应用程序范围</p></td>
<td align="left"><p>根据要虚拟化的应用程序，可以采用不同的方式设置 app-v 5.1 基础结构。 第一个任务是定义要虚拟化的应用程序。</p></td>
</tr>
<tr class="even">
<td align="left"><p>确定位置范围</p></td>
<td align="left"><p>"位置范围" 指的是你计划运行虚拟化应用程序的物理位置（例如，企业范围或特定地理位置）。 它还可以指将运行虚拟应用程序的用户群体（例如单个部门）。 你应该获得一个网络图，其中包括连接路径以及每个位置的可用带宽以及使用虚拟化应用程序的用户数和 WAN 链接速度。</p></td>
</tr>
</tbody>
</table>

 

## 确定所需的 App-v 5.1 基础结构


**重要提示** 以下两个模型都需要在计划运行虚拟应用程序的计算机上安装 app-v 5.1 客户端。

你还可以使用电子软件分发（ESD）解决方案（如 Microsoft 系统中心配置管理器）管理你的 App-v 5.1 环境。 有关详细信息，请参阅[如何使用电子软件分发部署 app-v 5.1 程序包](how-to-deploy-app-v-51-packages-using-electronic-software-distribution.md)。

 

-   **独立模型**-独立模型允许虚拟应用程序支持 Windows 安装程序，可在不进行流式处理的情况下分发。 独立模式下的 app-v 5.1 包括排序器和客户端;不需要其他组件。 使用名为 "排序" 的过程为虚拟化准备了应用程序。 有关详细信息，请参阅[规划 app-v 5.1 Sequencer 和客户端部署](planning-for-the-app-v-51-sequencer-and-client-deployment.md)。 建议在以下情况下使用独立模型：

    -   通过断开连接的远程用户无法连接到 app-v 5.1 基础结构。

    -   运行软件管理系统（如 Configuration Manager 2012）时。

    -   当网络带宽限制抑制电子软件分发时。

-   **完整基础结构模型**-完整的基础结构模型提供软件分发、管理和报告功能;它还包括跨网络的应用程序流。 App-v 5.1 完整基础结构模型由一个或多个 App-v 5.1 管理服务器组成。 管理服务器可用于将应用程序发布到所有客户端。 发布过程将虚拟应用程序图标和快捷方式放在目标计算机上。 它还可以将应用程序流式传输到本地用户。 有关安装管理服务器的详细信息，请参阅[规划 app-v 5.1 服务器部署](planning-for-the-app-v-51-server-deployment.md)。 建议在以下情况下使用完整的基础结构模型：

    **重要提示** App-v 5.1 完整基础结构模型要求 Microsoft SQL Server 存储配置数据。 有关详细信息，请参阅[应用 V 5.1 支持的配置](app-v-51-supported-configurations.md)。

     

    -   希望使用管理服务器将应用程序发布到目标计算机时。

    -   快速调配目标计算机的应用程序。

    -   希望使用 app-v 5.1 报告时。

## 端到端服务器规模调整指南


以下部分提供了有关端到端应用-V 5.1 规模调整和规划的信息。 有关更多特定信息，请参阅后续部分。

**注意** 客户端上的往返行程响应时间是运行 App-v 5.1 客户端以接收来自发布服务器成功通知的计算机所用的时间。 发布服务器上的往返行程响应时间是计算机运行发布服务器以接收来自管理服务器的成功程序包元数据更新所用的时间。

 

-   20000客户端可以面向单个发布服务器，以便在可接受的往返行程时间内进行程序包刷新。 （ &lt; 3 秒）

-   单个管理服务器最多可支持50发布服务器，以便在可接受的往返行程时间内更新软件包元数据。 （ &lt; 5 秒）

## <a href="" id="---------app-v-5-1-management-server-capacity-planning-recommendations"></a> App-v 5.1 管理服务器容量规划建议


App-v 5.1 发布服务器需要管理服务器才能进行程序包刷新请求和程序包刷新响应。 然后，管理服务器将信息发送到管理数据库以检索信息。 有关 App-V 5.1 管理服务器支持的配置的详细信息，请参阅[app-v 5.1 支持的配置](app-v-51-supported-configurations.md)。

**注意** App-v 5.1 发布服务器上的默认刷新时间是十分钟。

 

当多个同时发布服务器与单个管理服务器联系以进行软件包元数据刷新时，以下三个因素会影响发布服务器上的往返行程响应时间：

1.  同时请求的发布服务器数。

2.  管理服务器上配置的连接组的数量。

3.  管理服务器上配置的访问组数。

下表显示了影响往返行程时间的每个因素的详细信息。

**注意** 往返行程响应时间是计算机运行 app-v 5.1 发布服务器以接收来自管理服务器的成功程序包元数据更新所用的时间。

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">影响往返行程响应时间的因素</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>同时请求软件包元数据刷新的发布服务器数。</p></td>
<td align="left"><p></p>
<ul>
<li><p>单个管理服务器最多可以响应同时请求发布元数据的320发布服务器。</p></li>
<li><p>320 pub 服务器的往返行程响应时间为 ~ 40 秒。</p></li>
<li><p>对于 &lt; 50 同时请求元数据的发布服务器，往返行程响应时间为 &lt; 5 秒。</p></li>
<li><p>从50到320发布服务器，响应时间将线性增加（大约2x）。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>管理服务器上配置的连接组数。</p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p>对于最多100个连接组，发布服务器上的往返行程响应时间没有显著更改。</p></li>
<li><p>对于 100-400 连接组，"往返行程" 响应时间中有较小的线性增加。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>管理服务器上配置的访问组数。</p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p>对于最多40访问组，发布服务器上的往返行程响应时间有一个线性（大约3倍）的增加。</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

下表显示了上述每个因素的示例值。 在每个变体中，120程序包从 App-v 5.1 管理服务器刷新。

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">情形</th>
<th align="left">变体</th>
<th align="left">连接组数</th>
<th align="left">访问组数</th>
<th align="left">发布服务器数</th>
<th align="left">网络连接类型发布服务器/管理服务器</th>
<th align="left">发布服务器上的往返行程响应时间（以秒为单位）</th>
<th align="left">管理服务器上的 CPU 使用率</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>同时发布服务器，同时联系管理服务器以发布元数据。</p></td>
<td align="left"><p>发布服务器数</p></td>
<td align="left"><p></p>
<ul>
<li><p>0</p></li>
<li><p>0</p></li>
<li><p>0</p></li>
<li><p>0</p></li>
<li><p>0</p></li>
<li><p>0</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>raid-1</p></li>
<li><p>raid-1</p></li>
<li><p>raid-1</p></li>
<li><p>raid-1</p></li>
<li><p>raid-1</p></li>
<li><p>raid-1</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>50</p></li>
<li><p>100</p></li>
<li><p>200</p></li>
<li><p>300</p></li>
<li><p>315</p></li>
<li><p>320</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>级</p></li>
<li><p>10</p></li>
<li><p>19</p></li>
<li><p>32</p></li>
<li><p>大约</p></li>
<li><p>37</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>17</p></li>
<li><p>17</p></li>
<li><p>17</p></li>
<li><p>岁</p></li>
<li><p>17</p></li>
<li><p>岁</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>发布元数据包含连接组</p></td>
<td align="left"><p>连接组数</p></td>
<td align="left"><p></p>
<ul>
<li><p>10</p></li>
<li><p>50</p></li>
<li><p>100</p></li>
<li><p>150</p></li>
<li><p>300</p></li>
<li><p>400</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>raid-1</p></li>
<li><p>raid-1</p></li>
<li><p>raid-1</p></li>
<li><p>raid-1</p></li>
<li><p>raid-1</p></li>
<li><p>raid-1</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>100</p></li>
<li><p>100</p></li>
<li><p>100</p></li>
<li><p>100</p></li>
<li><p>100</p></li>
<li><p>100</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>10</p></li>
<li><p>11</p></li>
<li><p>11</p></li>
<li><p>utf-16</p></li>
<li><p>22</p></li>
<li><p>二十五</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>17</p></li>
<li><p>19</p></li>
<li><p>22</p></li>
<li><p>19</p></li>
<li><p>名</p></li>
<li><p>名</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>发布元数据包含访问组</p></td>
<td align="left"><p>访问组数</p></td>
<td align="left"><p></p>
<ul>
<li><p>0</p></li>
<li><p>0</p></li>
<li><p>0</p></li>
<li><p>0</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>raid-1</p></li>
<li><p>10</p></li>
<li><p>名</p></li>
<li><p>40</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>100</p></li>
<li><p>100</p></li>
<li><p>100</p></li>
<li><p>100</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>10</p></li>
<li><p>43</p></li>
<li><p>153</p></li>
<li><p>535</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>17</p></li>
<li><p>个</p></li>
<li><p>全</p></li>
<li><p>全</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

运行管理服务器的计算机的 CPU 使用率约为25%，与面向目标的发布服务器的数量无关。 Microsoft SQL Server 数据库事务/秒、批处理请求/秒和用户连接与发布服务器的数量无关。 例如：交易/秒是 ~ 30、批处理请求 ~ 200 和用户连接 ~ 6。

使用地理位置分散的部署，在这种情况下，管理服务器 & 发布服务器在其之间使用慢速链接网络，发布服务器上的往返行程响应时间在可接受的时间限制（ &lt; 5 秒）内，即使100同时请求同一台管理服务器也是如此。

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">情形</th>
<th align="left">变体</th>
<th align="left">连接组数</th>
<th align="left">访问组数</th>
<th align="left">发布服务器数</th>
<th align="left">网络连接类型发布服务器/管理服务器</th>
<th align="left">发布服务器上的往返行程响应时间（以秒为单位）</th>
<th align="left">管理服务器上的 CPU 使用率</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>发布服务器和管理服务器之间的网络连接</p></td>
<td align="left"><p>1.5 Mbps 慢速链接网络</p></td>
<td align="left"><p></p>
<ul>
<li><p>0</p></li>
<li><p>0</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>raid-1</p></li>
<li><p>raid-1</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>50</p></li>
<li><p>100</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>1.5 mbps 电缆 DSL</p></li>
<li><p>1.5 mbps 电缆 DSL</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>第</p></li>
<li><p>级</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>raid-1</p></li>
<li><p>ppls-2</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>发布服务器和管理服务器之间的网络连接</p></td>
<td align="left"><p>局域网/WIFI 网络</p></td>
<td align="left"><p></p>
<ul>
<li><p>0</p></li>
<li><p>0</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>raid-1</p></li>
<li><p>raid-1</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>100</p></li>
<li><p>200</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>Wifi</p></li>
<li><p>Wifi</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>11</p></li>
<li><p>名</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>岁</p></li>
<li><p>17</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

无论管理服务器和发布服务器通过慢速链接网络连接还是高速网络，管理服务器都可以在30分钟内处理大约15000程序包刷新请求。

## <a href="" id="---------app-v-5-1-reporting-server-capacity-planning-recommendations"></a> App-v 5.1 报告服务器容量规划建议


App-v 5.1 客户端将报告数据发送到报告服务器。 然后，报告服务器将在 Microsoft SQL Server 数据库中记录信息，并将成功的通知返回到运行 App-v 5.1 客户端的计算机上。 有关应用-V 5.1 报告服务器支持的配置的详细信息，请参阅[app-v 5.1 支持的配置](app-v-51-supported-configurations.md)。

**注意** 往返行程响应时间是运行 App-v 5.1 客户端以将报告信息发送到报告服务器并从报告服务器接收成功通知所用的时间。

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">情形</th>
<th align="left">摘要</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>多个 App-v 5.1 客户端同时向报告服务器发送报告信息。</p></td>
<td align="left"><p></p>
<ul>
<li><p>来自报告服务器的往返行程响应时间为500客户端的2.6 秒。</p></li>
<li><p>来自报告服务器的往返行程响应时间为1000客户端的5.65 秒。</p></li>
<li><p>往返行程响应时间根据客户数量线性增加。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>报告服务器每秒处理的请求数。</p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p>单个报告服务器和单个数据库最多可处理每秒139请求。 平均值为每秒121请求。</p></li>
<li><p>将两个报表服务器与同一 Microsoft SQL Server 数据库一起使用时，平均请求/秒类似于单个报表服务器 = ~ 127，每秒最多为278请求。</p></li>
<li><p>单个报告服务器可以处理500并发/活动连接。</p></li>
<li><p>单个报告服务器可以处理最大1500并发连接。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>报告数据库。</p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p>运行 Microsoft SQL Server 的计算机上的锁定争用是请求/秒的限制因素。</p></li>
<li><p>吞吐量和响应时间与数据库大小无关。</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

**计算随机延迟**：

随机延迟指定将数据发送到报告服务器的最大延迟（以分钟为单位）。 当计划任务启动时，客户端会在**0**和**ReportingRandomDelay**之间生成一个随机延迟，并在发送数据之前等待指定的持续时间。

随机延迟 = 4 \ * 客户端数/每秒平均请求数。

示例：对于500客户端，每秒120个请求，随机延迟是，4 \ * 500/120 = ~ 17 分钟。

## <a href="" id="---------app-v-5-1-publishing-server-capacity-planning-recommendations"></a> App-v 5.1 发布服务器容量规划建议


运行 App-V 5.1 客户端的计算机连接到 app-v 5.1 发布服务器以发送发布刷新请求和接收响应。 在运行 App-v 5.1 客户端的计算机上测量往返行程响应时间。 在发布服务器上测量处理器时间。 有关应用-V 5.1 发布服务器支持的配置的详细信息，请参阅[app-v 5.1 支持的配置](app-v-51-supported-configurations.md)。

**重要提示** 下表显示了设置 App-v 5.1 发布服务器时要考虑的主要因素：

-   同时连接到单个发布服务器的客户端数。

-   每次刷新中的程序包数。

-   客户端和 app-v 5.1 发布服务器之间的环境中的可用网络带宽。

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">情形</th>
<th align="left">摘要</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>多个应用程序-V 5.1 客户端同时连接到一个发布服务器。</p></td>
<td align="left"><p></p>
<ul>
<li><p>运行双核处理器的发布服务器最多可以响应同时请求刷新的5000客户端。</p></li>
<li><p>对于5000-10000 客户端，发布服务器需要最低的四核。</p></li>
<li><p>对于10000-20000 客户端，发布服务器应具有两个四核，以便更高效地响应时间。</p></li>
<li><p>带有四核的发布服务器最多可以在3秒内刷新10000程序包。 （支持10000同时进行的客户端）</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>每次刷新中的程序包数。</p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p>增加的程序包数量将使响应时间增加 ~ 40% （最多1000个程序包）。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v 5.1 客户端和发布服务器之间的网络。</p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p>通过慢速网络（1.5 Mbps 带宽），响应时间比局域网（最多可达1000用户）增加了97%。</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

**注意** 在需要处理同时请求的时间间隔（ &gt; 在大多数情况下为90%），发布服务器 CPU 使用率始终很高。 发布服务器可以在1秒内处理 ~ 1500 客户端请求。

 

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">情形</th>
<th align="left">变体</th>
<th align="left">App-v 5.1 客户端数</th>
<th align="left">程序包数</th>
<th align="left">发布服务器上的处理器配置</th>
<th align="left">网络连接类型发布服务器/App-v 5.1 客户端</th>
<th align="left">App-v 5.1 客户端上的往返行程时间（以秒为单位）</th>
<th align="left">发布服务器上的 CPU 使用率（以% 为百分比）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v 5.1 客户端发送发布刷新请求 &amp; 接收响应，每个包含120程序包的请求</p></td>
<td align="left"><p>客户端数</p></td>
<td align="left"><p></p>
<ul>
<li><p>100</p></li>
<li><p>1000</p></li>
<li><p>5000</p></li>
<li><p>10000</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>120</p></li>
<li><p>120</p></li>
<li><p>120</p></li>
<li><p>120</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>双核</p></li>
<li><p>双核</p></li>
<li><p>四核</p></li>
<li><p>四核</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>raid-1</p></li>
<li><p>ppls-2</p></li>
<li><p>ppls-2</p></li>
<li><p>三维空间</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>100</p></li>
<li><p>99</p></li>
<li><p>89</p></li>
<li><p>77</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>每次刷新中的多个程序包</p></td>
<td align="left"><p>程序包数</p></td>
<td align="left"><p></p>
<ul>
<li><p>1000</p></li>
<li><p>1000</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>500</p></li>
<li><p>1000</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>四核</p></li>
<li><p>四核</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>ppls-2</p></li>
<li><p>三维空间</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>92</p></li>
<li><p>91</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>客户端和发布服务器之间的网络</p></td>
<td align="left"><p>1.5 Mbps 慢速链接网络</p></td>
<td align="left"><p></p>
<ul>
<li><p>100</p></li>
<li><p>500</p></li>
<li><p>1000</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>120</p></li>
<li><p>120</p></li>
<li><p>120</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>四核</p></li>
<li><p>四核</p></li>
<li><p>四核</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>1.5 Mbps 的大陆内网络</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>三维空间</p></li>
<li><p>10（0.2% 故障率）</p></li>
<li><p>17（有1% 的故障率）</p></li>
</ul></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="---------app-v-5-1-streaming-capacity-planning-recommendations"></a> App-v 5.1 流容量规划建议


运行 App-v 5.1 客户端的计算机从流服务器流出虚拟应用程序包。 往返行程响应时间在运行 App-v 5.1 客户端的计算机上测量，并且是流式处理整个程序包所花的时间。

**重要提示** 下表列出了设置 App-v 5.1 流服务器时要考虑的主要因素：

-   从单个流式处理服务器同时处理流应用程序包的客户端数。

-   正在进行流处理的包的大小。

-   客户端和流服务器之间的环境中的可用网络带宽。

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">情形</th>
<th align="left">摘要</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>多个 App-v 5.1 客户端从单个流服务器同时流处理应用程序。</p></td>
<td align="left"><p></p>
<ul>
<li><p>如果同时从同一服务器同时流式处理的客户端数量增加，则会有与程序包下载/流时间有关的线性关系。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>正在进行流处理的包的大小。</p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p>程序包大小对大小约为1GB 的较大程序包的流处理/下载时间有重大影响。 对于从 3 MB 到 100 MB 的程序包大小，流时间的范围从20秒到100秒，同时提供100个客户端。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v 5.1 客户端和流式服务器之间的网络。</p>
<p></p></td>
<td align="left"><p></p>
<ul>
<li><p>通过慢速网络（1.5 Mbps 带宽），响应时间比局域网（最多可达100用户）增加了70-80%。</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

下表显示了上一列表中每个因素的示例值：

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">情形</th>
<th align="left">变体</th>
<th align="left">App-v 5.1 客户端数</th>
<th align="left">每个程序包的大小</th>
<th align="left">网络连接类型流式处理服务器/App-v 5.1 客户端</th>
<th align="left">App-v 5.1 客户端上的往返行程时间（以秒为单位）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>多个 App-v 5.1 客户端从流式处理服务器流式处理虚拟应用程序包。</p></td>
<td align="left"><p>客户端数。</p></td>
<td align="left"><p></p>
<ul>
<li><p>100</p></li>
<li><p>200</p></li>
<li><p>1000</p></li>
<li><p></p></li>
<li><p>100</p></li>
<li><p>200</p></li>
<li><p>1000</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>3.5 MB</p></li>
<li><p>3.5 MB</p></li>
<li><p>3.5 MB</p></li>
<li><p></p></li>
<li><p>5 MB</p></li>
<li><p>5 MB</p></li>
<li><p>5 MB</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p></p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>29</p></li>
<li><p>39</p></li>
<li><p>391</p></li>
<li><p></p></li>
<li><p>35</p></li>
<li><p>68</p></li>
<li><p>461</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>正在进行数据流处理的每个程序包的大小。</p></td>
<td align="left"><p>每个程序包的大小。</p></td>
<td align="left"><p></p>
<ul>
<li><p>100</p></li>
<li><p>200</p></li>
<li><p></p></li>
<li><p>100</p></li>
<li><p>200</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>21 MB</p></li>
<li><p>21 MB</p></li>
<li><p></p></li>
<li><p>109</p></li>
<li><p>109</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
<li><p></p></li>
<li><p>LAN</p></li>
<li><p>LAN</p></li>
</ul></td>
<td align="left"><p></p>
<p>33</p>
<p>83</p>
<p></p>
<p>100</p>
<p>160</p></td>
</tr>
<tr class="odd">
<td align="left"><p>客户端和 App-v 5.1 流服务器之间的网络连接。</p></td>
<td align="left"><p>1.5 Mbps 慢速链接网络。</p></td>
<td align="left"><p></p>
<ul>
<li><p>100</p></li>
<li><p></p></li>
<li><p>100</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>3.5 MB</p></li>
<li><p></p></li>
<li><p>5 MB</p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p>1.5 Mbps 的大陆内网络</p></li>
</ul></td>
<td align="left"><p></p>
<p>102</p>
<p></p>
<p>121</p></td>
</tr>
</tbody>
</table>

 

每个 App-v 5.1 流服务器都应该能够处理同时流式处理的虚拟化应用程序中最少的200个客户端。

**注意** 流的实际时间将主要由同时流的客户端数、程序包数、程序包大小、服务器的网络活动和网络条件决定。

 

例如，当100同时进行来自服务器的流处理时，一般用户可以在2分钟内流出 100 MB 程序包。 但是，一个大小为 1 GB 的程序包可能最多需要30分钟。 在大多数真实环境中，流请求不是均匀分布的，你需要了解你的环境中存在的近似的峰值流要求，以便正确地调整所需流式处理服务器的数量。

如果你预缓存了你的应用程序，可显著增加流服务器支持的客户端数和峰值流需求。 您还可以通过使用点播流式传递和流优化程序包来增加流服务器可以支持的客户端数量。

## 结合 app-v 5.1 服务器角色


折扣比例和容错要求，连接到 Active Directory 的位置所需的最少服务器数是一个。 此服务器将托管管理服务器、管理服务器服务和 Microsoft SQL Server 角色。 因此，服务器角色可以按所需的任何组合进行排列，因为它们不会相互冲突。

忽略缩放要求，提供容错实现所需的最少服务器数是4。 管理服务器和 Microsoft SQL Server 角色支持被置于容错配置中。 管理服务器服务可以与任何角色结合使用，但仍会出现单点故障。

虽然有许多可用的容错策略和技术，但并非所有这些都适用于给定的服务。 此外，如果结合使用 app-v 5.1 角色，则某些容错选项可能不再适用，因为不兼容。






## 相关主题


[App-V 5.1 支持的配置](app-v-51-supported-configurations.md)

[计划 App-V 5.1 的高可用性](planning-for-high-availability-with-app-v-51.md)

[计划部署 App-V](planning-to-deploy-app-v51.md)

 

 





