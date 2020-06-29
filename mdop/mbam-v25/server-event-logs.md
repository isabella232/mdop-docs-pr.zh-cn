---
title: 服务器事件日志
description: 服务器事件日志
author: dansimp
ms.assetid: 04e724d2-28cc-4fa8-86a1-0d4ab0234b11
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 269e9b4bc2644fae4dc5796652c7587bb0ef6076
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10803357"
---
# 服务器事件日志


本节中的表提供了有关 MBAM 服务器日志事件 Id 的信息。

## 配置


下表包含配置期间 MBAM 服务器上可能出现的事件 Id 的消息和疑难解答信息。

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">事件 ID</th>
<th align="left">来源</th>
<th align="left">活动符号</th>
<th align="left">消息</th>
<th align="left">疑难解答</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>103</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-服务器/运营</p></td>
<td align="left"><p>VssRegistrationException</p></td>
<td align="left"><p>VSS 注册期间引发了异常。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>104</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-服务器/运营</p></td>
<td align="left"><p>VssDeregistrationException</p></td>
<td align="left"><p>VSS 注销期间引发异常。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>300</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-服务器/Admin</p></td>
<td align="left"><p>CmdletError</p></td>
<td align="left"><p>删除文件夹失败。</p></td>
<td align="left"><p>指示在执行任务时发生终止错误。 检查日志中的其他事件消息，进一步诊断 MBAM 设置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>301</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-服务器/Admin</p></td>
<td align="left"><p>cmdletUnexpectedError</p></td>
<td align="left"><p>意外的 Cmdlet 错误。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>302</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-服务器/Admin</p></td>
<td align="left"><p>CmdletWarning</p></td>
<td align="left"><p>Cmdlet 警告。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>303</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-服务器/运营</p></td>
<td align="left"><p>CmdletInformation</p></td>
<td align="left"><p>Cmdlet 信息。</p></td>
<td align="left"><p>仅提供信息;无需进行故障排除。 该事件指示由 Cmdlet （如 enabling\disabling 功能或取消操作）所发生的任务。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>400</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-服务器/Admin</p></td>
<td align="left"><p>ConfiguratorError</p></td>
<td align="left"><p>配置器错误。</p></td>
<td align="left"><p>指示在启动 MBAM 配置器时出错。 确保用户具有足够的权限启动 MBAM 配置器。</p></td>
</tr>
<tr class="even">
<td align="left"><p>401</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-服务器/Admin</p></td>
<td align="left"><p>ConfiguratorUnexpectedError</p></td>
<td align="left"><p>意外的配置器错误。</p></td>
<td align="left"><p>指示在执行 MBAM 配置程序任务时发生终止错误。 错误消息将包含有关错误的更多详细信息。 检查事件日志中的其他错误消息，进一步诊断 MBAM 设置。 已知错误包括：</p>
<ul>
<li><p>无法检索或验证用户选择的证书</p></li>
<li><p>无法解析报表 URL</p></li>
<li><p>无法打开用户的事件日志</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>402</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-服务器/Admin</p></td>
<td align="left"><p>ConfiguratorWarning</p></td>
<td align="left"><p>配置器警告。</p></td>
<td align="left"><p>指示 MBAM 配置程序任务未按预期完成，但未完全失败。 已知任务包括在 web 应用程序功能中配置的 LocalMachine\My 存储中缺少证书，或者挂起任务的超时。</p></td>
</tr>
<tr class="even">
<td align="left"><p>410</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-服务器/运营</p></td>
<td align="left"><p>ConfiguratorInformation</p></td>
<td align="left"><p>配置器信息。</p></td>
<td align="left"><p>仅提供信息;无需进行故障排除。 该事件指示任务正由 MBAM 配置器调用。 已知任务包括：</p>
<ul>
<li><p>启动配置器</p></li>
<li><p>检查 MBAM 功能的软件先决条件</p></li>
<li><p>验证 MBAM 功能的参数</p></li>
<li><p>Enabling\disabling\committing MBAM 功能</p></li>
<li><p>从配置器生成 PowerShell 脚本</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>500</p></td>
<td align="left"><p>Microsoft_Windows_MBAM_Server_Admin</p></td>
<td align="left"><p>WebProviderUnexpectedError</p></td>
<td align="left"><p>Web 应用程序提供程序意外错误。</p></td>
<td align="left"><p>指示在 IIS 中启用和配置 MBAM 网站或 web 服务时出现错误。 已知错误包括：</p>
<ul>
<li><p>无法找到 IIS WWW 根文件夹</p></li>
<li><p>由于文件格式不正确或缺少设置，无法访问 web.config 中的 IIS 配置</p></li>
<li><p>无法创建或删除 web 应用程序</p></li>
<li><p>IIS 访问冲突</p></li>
</ul>
<p>如果 MBAM 无法访问 Active Directory （AD）以验证用户帐户，也会记录此错误。 验证 IIS 是否已安装、配置正确以及 IIS 服务是否正在运行。 验证所有 MBAM 软件必备项检查是否均已通过。 验证用户是否具有在 IIS 实例上创建 web 应用程序的正确权限。 验证用户是否有权读取 AD 中的用户帐户对象。</p></td>
</tr>
<tr class="even">
<td align="left"><p>501</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-服务器/Admin</p></td>
<td align="left"><p>WebProviderError</p></td>
<td align="left"><p>Web 应用程序提供程序意外错误。</p></td>
<td align="left"><p>指示在 IIS 中启用、禁用或配置 MBAM 网站或 web 服务时出错。 已知错误包括：</p>
<ul>
<li><p>无法从 IIS 读取基本或 WSHttp 绑定信息</p></li>
<li><p>IIS 配置文件中的标识部分缺少标识部分或 DNS 条目</p></li>
<li><p>无法打开注册表项 HKLM\SOFTWARE\Microsoft\InetStp</p></li>
<li><p>从注册表项 HKLM\SOFTWARE\Microsoft\InetStp 中读取值 PathWWWRoot 失败</p></li>
<li><p>用户正在尝试使用 MBAM 的保留名称指定虚拟目录名称</p></li>
</ul>
<p>验证是否已安装并正确配置了 IIS。 验证注册表项 HKLM\SOFTWARE\Microsoft\InetStp： PathWWWRoot 是否存在并且是否可访问。 验证 IIS 中的绑定信息是否未损坏。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>502</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-服务器/Admin</p></td>
<td align="left"><p>WebProviderWarning</p></td>
<td align="left"><p>Web 应用程序提供商警告。</p></td>
<td align="left"><p>指示在启用 MBAM 网站或 web 服务时出现非终止错误。 已知错误包括：</p>
<ul>
<li><p>无法访问 AD 以验证应用池帐户上的服务主体名称（SPN）</p></li>
<li><p>无法验证 SPN，因为它已分配给 AD 中的多个帐户</p></li>
<li><p>无法在 AD 中的应用程序池帐户上注册 SPN</p></li>
<li><p>SPN 在 AD 中的应用池之外的帐户上注册</p></li>
<li><p>在回滚操作期间从 AD 中的应用程序池帐户中删除 SPN 失败</p></li>
<li><p>无法检查是否已授予 IIS_IUSRS 组在 IIS 服务器上作为批处理权限登录</p></li>
</ul>
<p>事件消息将包含有关特定错误的详细信息。 验证是否可以从运行 MBAM 安装程序的服务器访问广告。 验证运行 MBAM 安装程序的用户对 AD 中的应用池帐户是否具有 "读取" 权限。 如果 SPN 已在 AD 中的应用程序池帐户上注册，请确保它未在其他帐户上注册。</p></td>
</tr>
<tr class="even">
<td align="left"><p>503</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-服务器/运营</p></td>
<td align="left"><p>WebProviderInformation</p></td>
<td align="left"><p>Web 应用程序提供商信息。 介绍</p></td>
<td align="left"><p>仅提供信息;无需进行故障排除。 该事件指示任务正在由 MBAM 设置调用。 已知任务包括获取诸如绑定信息和根网站之类的 IIS 配置以及配置服务主体名称（SPN）。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>600</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-服务器/Admin</p></td>
<td align="left"><p>SetupUnexpectedError</p></td>
<td align="left"><p>意外的设置错误。</p></td>
<td align="left"><p>指示在 enabling\disabling 或配置 MBAM 功能时发生终止错误。 已知错误包括：</p>
<ul>
<li><p>错误后回滚任务失败</p></li>
<li><p>无法从注册表中读取</p></li>
<li><p>无法在文件系统中创建或删除文件夹</p></li>
<li><p>无法读取 SQL 版本信息</p></li>
<li><p>无法在 SQL 中注册 VSS 编写器</p></li>
</ul>
<p>事件消息将包含有关特定错误的详细信息。 验证所有 MBAM 软件先决条件检查是否已通过。 请确保 MBAM 注册表路径（如果存在） HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\MBAM 服务器，并且所有子项均可读。 验证是否可以从运行 MBAM 安装程序的服务器访问广告。 验证运行 MBAM 安装程序的用户在 AD 中是否具有 "读取" 权限。</p>
<p>对于成功的 VSS 编写器注册，请验证是否已安装支持的 SQL 版本，以及运行 MBAM 安装程序的用户是否可以访问该实例。 如果禁用 MBAM 功能或卸载 MBAM，请验证所有文件（如日志文件和 web.config 文件）是否已关闭，以便 MBAM 可以删除其网站和 web 服务。</p></td>
</tr>
<tr class="even">
<td align="left"><p>601</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-服务器/Admin</p></td>
<td align="left"><p>SetupError</p></td>
<td align="left"><p>设置错误。</p></td>
<td align="left"><p>指示在 enabling\disabling 或配置 MBAM 功能时发生终止错误。 已知错误包括：</p>
<ul>
<li><p>在 IIS 中读取 MBAM 配置失败</p></li>
<li><p>IIS 配置中损坏的 appSettings 部分或设置不当的设置</p></li>
<li><p>无法验证主机名</p></li>
<li><p>无法读取 SQL 版本信息</p></li>
<li><p>无法在 SQL 中注册 VSS 编写器</p></li>
</ul>
<p>事件消息将包含有关特定错误的详细信息。 验证是否已正确安装和配置 IIS。 验证所有 MBAM 软件先决条件检查是否已通过。 对于成功的 VSS 编写器注册，请验证是否已安装支持的 SQL 版本，以及运行 MBAM 安装程序的用户是否可以访问该实例。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>602</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-服务器/Admin</p></td>
<td align="left"><p>SetupWarning</p></td>
<td align="left"><p>设置警告。</p></td>
<td align="left"><p>指示在 enabling\disabling 或配置 MBAM 功能（如配置管理器（CM）集成或 MBAM web 应用程序时发生了非终止错误。 已知错误包括：从 CM 中删除来自 SRS 角色点的 MBAM 报表失败，并且无法从域控制器解析主机名。 事件消息将包含有关特定错误的详细信息。</p>
<p>验证是否可以从运行 MBAM 安装程序的服务器访问广告。 验证运行 MBAM 安装程序的用户是否具有对在 CM 中配置为 SRS 角色点的 SSRS 实例的 "删除" 权限。</p></td>
</tr>
<tr class="even">
<td align="left"><p>603</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-服务器/运营</p></td>
<td align="left"><p>SetupInformation</p></td>
<td align="left"><p>设置信息。</p></td>
<td align="left"><p>仅提供信息;无需进行故障排除。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>605</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-服务器/Admin</p></td>
<td align="left"><p>WebProviderSoftwareCheckFailure</p></td>
<td align="left"><p>无法启用 Web 应用程序，因为未满足一个或多个软件依赖关系。</p></td>
<td align="left"><p>在 MBAM 网站/web 服务安装期间，MBAM 安装程序将验证必要的先决条件是否存在。 此消息指示 MBAM 无法安装请求的网站/web 服务，因为缺少必要的先决条件。 请参阅此消息前面的错误消息，获取有关缺少先决条件的详细信息。</p></td>
</tr>
<tr class="even">
<td align="left"><p>606</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-服务器/Admin</p></td>
<td align="left"><p>SetupParameterValidationFailure</p></td>
<td align="left"><p>启用服务器功能所需的参数未指定或未通过验证。</p></td>
<td align="left"><p>指示配置 MBAM 功能所需的参数未指定或未通过验证。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>607</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-服务器/Admin</p></td>
<td align="left"><p>SetupParameterValidationFailureWithError</p></td>
<td align="left"><p>尝试验证启用服务器功能所需的指定参数时遇到错误。</p></td>
<td align="left"><p>指示在尝试验证启用服务器功能所需的指定参数时遇到错误。</p></td>
</tr>
<tr class="even">
<td align="left"><p>700</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-服务器/Admin</p></td>
<td align="left"><p>DbProviderUnexpectedError</p></td>
<td align="left"><p>DB 访问接口意外错误。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>701</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-服务器/Admin</p></td>
<td align="left"><p>DbProviderError</p></td>
<td align="left"><p>DB 提供程序错误。</p></td>
<td align="left"><p>EventDetails 部分中包含的消息应提供有关实际错误的详细信息。 以下是要验证的一些区域：</p>
<ul>
<li><p>MBAM 安装程序无法使用提供的连接信息连接到数据库。 验证提供给 MBAM 设置的连接字符串详细信息。</p></li>
<li><p>MBAM 安装程序无法使用提供的域帐户凭据连接到给定的数据库。 验证域帐户用户名和密码是否有效。</p></li>
<li><p>MBAM 安装程序无法使用提供的域帐户凭据连接到给定的数据库。 验证所提供的域帐户是否具有连接到 MBAM 数据库所需的权限。</p></li>
<li><p>如果已安装较新版本的 MBAM 数据库，MBAM Dac pac 将失败。 验证给定 SQL server 上是否不存在新版本的 MBAM 的 SQL server。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>702</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-服务器/Admin</p></td>
<td align="left"><p>DbProviderWarning</p></td>
<td align="left"><p>DB 提供程序警告。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>703</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-服务器/运营</p></td>
<td align="left"><p>DbProviderInformation</p></td>
<td align="left"><p>DB 提供程序信息。</p></td>
<td align="left"><p>仅提供信息;无需进行故障排除。</p></td>
</tr>
<tr class="even">
<td align="left"><p>704</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-服务器/Admin</p></td>
<td align="left"><p>DbProviderDacError</p></td>
<td align="left"><p>部署数据层应用程序时出错。</p></td>
<td align="left"><p>MBAM 将其数据库打包为数据层应用程序，并尝试使用 DacServices 注册它们。 DAC 服务报告上下文中的错误消息。 该事件应包含有关导致它的原因的详细信息。 阅读错误消息中的信息以诊断和解决问题。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>705</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-服务器/Admin</p></td>
<td align="left"><p>DbProviderDacWarning</p></td>
<td align="left"><p>部署数据层应用程序时出现警告。</p></td>
<td align="left"><p>MBAM 将其数据库打包为数据层应用程序，并尝试使用 DacServices 注册它们。 DAC 服务报告上下文中的警告消息。 该事件应包含有关导致它的原因的详细信息。 阅读警告消息中的信息以诊断和解决问题。</p></td>
</tr>
<tr class="even">
<td align="left"><p>706</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-服务器/运营</p></td>
<td align="left"><p>DbProviderDacInformation</p></td>
<td align="left"><p>部署数据层应用程序时引发了一条消息。</p></td>
<td align="left"><p>仅提供信息;无需进行故障排除。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>800</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-服务器/Admin</p></td>
<td align="left"><p>ReportProviderUnexpectedError</p></td>
<td align="left"><p>报表提供程序意外错误。</p></td>
<td align="left"><p>报表提供程序意外错误。 介绍{exceptionDetails}下面是一些可能的异常详细信息：</p>
<p><strong>获取目录 &#39; 的名称时出错 {directoryName} &#39;</strong></p>
<p><strong>获取目录 &#39; 的文件时发生异常 {directoryName} &#39;</strong></p>
<p><strong>枚举目录 &#39; 中的目录时出现异常 {directoryName} &#39;</strong></p>
<p><strong>读取文件 &#39; {fileName} 的所有字节时发生异常 &#39;</strong></p>
<p>在 MBAM 安装期间，MBAM 安装程序将所有报告文件 unzips 到指定的安装路径。 作为报表安装的一部分，安装模块将尝试在安装路径中访问已解压缩的报表文件，并与 SQL Reporting services 进行通信以发布报表文件。 当 MBAM 无法在解压缩安装路径中访问文件/文件夹时，将发生上述错误。 以下是解决此问题的一些提示：</p>
<ul>
<li><p>验证是否已安装 MBAM。</p></li>
<li><p>验证 regkey HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\MBAM Server\InstallationPath 是否存在，并可供执行用户访问。</p></li>
<li><p>验证 MBAM InstallationPath 下报告文件的路径不超过248个字符。</p></li>
<li><p>验证 MBAM 安装文件夹或 MBAM 安装路径中包含的文件自安装后未被修改。</p></li>
<li><p>验证运行安装程序的用户是否有权读取/写入 MBAM 安装文件夹。</p></li>
</ul>
<p><strong>Reporting Services 连接失败。{exceptionDetails}</strong></p>
<p>在 MBAM 报表安装期间，模块将尝试与 SSRS web 服务通信以创建文件夹和发布报表。 上面的消息指示 MBAM 无法找到 SSRS web 服务或与 SSRS web 服务通信。 以下是解决此问题的一些提示：</p>
<ul>
<li><p>验证是否已在指定的计算机上安装了 SSRS。</p></li>
<li><p>使用 SSRS 控制台验证 SSRS 是否已启用且正在运行。</p></li>
<li><p>验证运行安装程序的用户是否有权访问 SSRS。</p></li>
</ul>
<p><strong>无法使用 Reporting Services 实例 URL &#39; {SSRSInstanceUrl} &#39; 删除 MBAM 报表。请确保 MBAM 报表所需的 SSRS 实例正在运行且配置正确。</strong></p>
<p>当 MBAM 安装失败或用户禁用 MBAM 报告功能时，安装程序模块将删除 SSRS 报告。 上面的消息指示 MBAM 无法删除 SSRS 报表。 以下是解决此问题的一些提示：</p>
<ul>
<li><p>验证是否已在指定的计算机上安装了 SSRS。</p></li>
<li><p>使用 SSRS 控制台验证 SSRS 是否已启用且正在运行。</p></li>
<li><p>验证运行安装程序的用户是否有权访问 SSRS。</p></li>
</ul>
<p><strong>发布报表时出错。{exceptionDetails}.</strong></p>
<p>在 MBAM 报表安装期间，模块将尝试与 SSRS web 服务通信以创建文件夹和发布报表。 上面的消息指示 SSRS web 服务在发布报表时报告和异常。 以下是解决此问题的一些提示：</p>
<ul>
<li><p>使用 SSRS 控制台验证 SSRS 是否已启用且正在运行。</p></li>
<li><p>验证运行安装程序的用户是否有权访问/将报表发布到 SSRS。</p></li>
</ul>
<p><strong>组用户名 &#39; {userName} &#39; 的策略已存在。 如果这不正确，请手动修改重复或无效策略的报告服务。</strong></p>
<p>发布 MBAM 报表后，MBAM 安装程序会尝试创建 MBAM 报表用户角色（如果尚未存在）并设置相应的用户策略。 上面的错误指示 SSRS web 服务在设置报表用户角色策略时引发了异常。 按照事件消息中的说明进行操作，然后参阅 &quot; <a href="https://www.microsoft.com/technet/support/ee/transform.aspx?ProdName=SQL+Server+Reporting+Services&amp;ProdVer=8.00&amp;EvtID=rsInvalidPolicyDefinition&amp;EvtSrc=Microsoft.ReportingServices.Diagnostics.ErrorStrings.resources.Strings&amp;LCID=1033&amp;quot" data-raw-source="https://www.microsoft.com/technet/support/ee/transform.aspx?ProdName=SQL+Server+Reporting+Services&amp;amp;ProdVer=8.00&amp;amp;EvtID=rsInvalidPolicyDefinition&amp;amp;EvtSrc=Microsoft.ReportingServices.Diagnostics.ErrorStrings.resources.Strings&amp;amp;LCID=1033&amp;quot"> https://www.microsoft.com/technet/support/ee/transform.aspx?ProdName=SQL+Server+Reporting+Services&amp 。ProdVer = 8.00 &amp; EvtID = rsInvalidPolicyDefinition &amp; EvtSrc =。字符串 &amp; LCID = 1033&q </a> ; 获取更多帮助。</p>
<p><strong>验证对 SSRS {exceptionDetails} 的访问时出错。</strong></p>
<p>作为先决条件检查的一部分，MBAM 安装程序将验证用户是否具有在 SSRS 下访问/创建文件夹的必要权限。 错误消息指示在验证对 SSRS 的访问时出现了异常。 有关调试提示，请参阅异常详细信息。</p>
<p><strong>检查 SSRS URL 时发生 SOAP 错误。{exceptionDetails}</strong></p>
<p><strong>检查 SSRS URL 时发生 web 错误。{exceptionDetails}</strong></p>
<p><strong>检查 SSRS URL 时发生 http/https 错误。{exceptionDetails}</strong></p>
<p><strong>检查 SSRS URL 时出错。{exceptionDetails}</strong></p>
<p>作为先决条件检查的一部分，MBAM 安装程序将检索与所提供的 SSRS 实例相关联的 Url，并尝试与 SSRS web 服务进行通信。 上述错误消息指示给定 URL 处的 SSRS web 服务引发了异常，有关详细信息，请参阅异常详细信息。 以下是解决 SSRS 通信问题的一些提示。</p>
<ul>
<li><p>验证是否已在指定的计算机上安装了 SSRS。</p></li>
<li><p>使用 SSRS 控制台验证 SSRS 是否已启用且正在运行。</p></li>
<li><p>验证运行安装程序的用户是否有权访问 SSRS。</p></li>
</ul>
<p><strong>检索 SSRS 版本时发生错误。 {exceptionDetails}</strong></p>
<p>作为先决条件检查的一部分，MBAM 安装程序查询 WMI 以检索与所提供的 SSRS 实例相关联的版本号。 上面的错误消息表示查询 WMI 时发生异常。 有关详细信息，请参阅 exceptionDetails。 以下是你可以执行的一些检查：</p>
<ul>
<li><p>验证指定的计算机上是否已安装具有给定实例名称的 SSRS。</p></li>
<li><p>使用 SSRS 控制台验证 SSRS 是否已启用且正在运行。</p></li>
<li><p>验证执行安装程序的用户是否有权在 WMI 命名空间下查询 SSRS 类。</p></li>
</ul>
<p><strong>当前用户无权访问 WMI 命名空间 &#39; {ssrsWMINamespace} &#39;。</strong></p>
<p><strong>枚举命名空间时出错 &#39; {ssrsWMINamespace} &#39;。 找不到本地主机上的 SSRS WMI 提供程序的 RPC 服务器。</strong></p>
<p><strong>枚举命名空间时出错 &#39; {ssrsNamespace} &#39;。 在本地主机上找不到 SSRS 实例。</strong></p>
<p><strong>访问 WMI 时出错。 找不到实例 &#39; {ssrsInstance} &#39; 的 RPC 服务器。</strong></p>
<p><strong>访问 WMI 时出错。 实例名称 &#39; {ssrsInstanceName} &#39; 不正确。</strong></p>
<p><strong>访问 WMI 时出错。 在本地主机上找不到 &#39; {ssrsInstanceName} &#39; 的实例。</strong></p>
<p>作为先决条件检查的一部分，MBAM 安装程序查询 WMI 以检索与给定实例相关联的 WMI 命名空间。 上面的错误消息指示在查询 WMI 时出现和异常。 有关详细信息，请参阅 exceptionDetails。 以下是你可以执行的一些检查：</p>
<ul>
<li><p>验证指定的计算机上是否已安装具有给定实例名称的 SSRS。</p></li>
<li><p>使用 SSRS 控制台验证 SSRS 是否已启用且正在运行。</p></li>
<li><p>验证运行安装程序的用户是否已授权访问/查询 WMI 命名空间下的 SSRS 类。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>801</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-服务器/Admin</p></td>
<td align="left"><p>ReportProviderError</p></td>
<td align="left"><p>报表提供程序意外错误。</p></td>
<td align="left"><p>给定 SQL server reporting services 实例名称，MBAM 尝试查找与报告实例对应的 WMI 命名空间并连接到该命名空间。 如果 MBAM 在 MBAM 搜索或尝试连接到 SSRS WMI 命名空间时遇到异常，则会出现此错误。 阅读在 MBAM 安装频道中记录的错误消息中的信息，以获取更多详细信息。 下面是您可以检查的一些事项：</p>
<ul>
<li><p>验证具有提供的实例名称的 SSRS 是否已启动并在运行</p></li>
<li><p>验证运行 MBAM 安装的用户帐户是否有必要的权限来查询/连接到 SSRS WMI 命名空间</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>802</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-服务器/Admin</p></td>
<td align="left"><p>ReportProviderWarning</p></td>
<td align="left"><p>报表提供程序警告。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>803</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-服务器/运营</p></td>
<td align="left"><p>ReportProviderInformation</p></td>
<td align="left"><p>报表提供程序信息。</p></td>
<td align="left"><p>仅提供信息;无需进行故障排除。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>900</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-服务器/Admin</p></td>
<td align="left"><p>CMProviderUnexpectedError</p></td>
<td align="left"><p>CM 提供程序意外错误。</p></td>
<td align="left"><p>指示在 MBAM 中 enabling\disabling 或配置配置管理器（CM）集成功能时发生了终止错误。 已知错误包括：</p>
<ul>
<li><p>无法通过 SMS 提供程序连接到 CM 网站服务器</p></li>
<li><p>无法从注册表中读取</p></li>
<li><p>无法在文件系统中创建或删除文件夹</p></li>
<li><p>无法在本地计算机上找到 Configuration Manager 控制台安装</p></li>
<li><p>检索配置为 SRS 角色点的 SSRS 实例的信息失败</p></li>
</ul>
<p>事件消息将包含有关特定错误的详细信息。 验证所有 MBAM 软件先决条件检查是否已通过。 验证 MBAM 注册表路径（如果存在），HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\MBAM 服务器以及所有子项是否可读。 验证 MBAM 是否与受支持的 Configuration Manager 版本集成。 验证配置管理器控制台是否已安装在正在调用 MBAM 安装程序的计算机上，以及是否可以使用该控制台连接到目标 CM 站点服务器。 验证有效的 SSRS 实例是否已配置为 CM 中的 SRS 角色点，并且运行 MBAM 安装程序的用户具有对 SSRS 实例的 read\write 权限。</p></td>
</tr>
<tr class="even">
<td align="left"><p>901</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-服务器/Admin</p></td>
<td align="left"><p>CMProviderError</p></td>
<td align="left"><p>CM 提供程序意外错误。</p></td>
<td align="left"><p>指示在 MBAM 中 enabling\disabling 或配置配置管理器（CM）集成功能时发生了终止错误。 已知错误包括：</p>
<ul>
<li><p>无法通过 SMS 提供程序连接到 CM 网站服务器</p></li>
<li><p>无法从注册表中读取</p></li>
<li><p>无法在文件系统中创建或删除文件夹</p></li>
<li><p>无法在本地计算机上找到 Configuration Manager 控制台安装</p></li>
<li><p>在 SSRS 中缺少 ConfigMgr 文件夹作为 SRS 角色点报告的根文件夹</p></li>
<li><p>SSRS 中缺少 ConfigMgr 共享数据源</p></li>
<li><p>在以 CM 形式配置为 SRS 角色点的 SSRS 实例中部署 SSRS 报表失败</p></li>
<li><p>无法在 CM 中创建配置项目和基线</p></li>
</ul>
<p>事件消息将包含有关特定错误的详细信息。 验证所有 MBAM 软件先决条件检查是否已通过。 验证 MBAM 注册表路径（如果存在），HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\MBAM 服务器以及所有子项是否可读。 验证 MBAM 是否与受支持的 Configuration Manager 版本集成。 验证配置管理器控制台是否已安装在正在调用 MBAM 安装程序的计算机上，以及是否可以使用该控制台连接到目标 CM 站点服务器。 验证用户是否具有在 CM 中创建配置项目、基线和集合的必需 read\write 权限。 验证有效的 SSRS 实例是否已配置为 CM 中的 SRS 角色点，并且运行 MBAM 安装程序的用户具有对 SSRS 实例的 read\write 权限。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>902</p></td>
<td align="left"><p>Microsoft_Windows_MBAM_Server_Admin</p></td>
<td align="left"><p>CMProviderWarning</p></td>
<td align="left"><p>CM 提供商警告。</p></td>
<td align="left"><p>指示在启用配置管理器（CM）集成功能时出现非终止错误。 已知错误包括：无法在 MBAM 支持的计算机集合中提交收集规则，以及与其他 SSRS 和网络相关的错误。</p>
<p>事件消息将包含有关特定错误的详细信息。 导致此警告的某些操作将在警告后停用。 如果多次重试后错误仍然存在，则 MBAM 可能会以实际错误结尾。 检查日志中的其他事件消息，进一步诊断 MBAM 设置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>903</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-服务器/运营</p></td>
<td align="left"><p>CMProviderInformation</p></td>
<td align="left"><p>CM 提供商信息。</p></td>
<td align="left"><p>仅提供信息;无需进行故障排除。</p></td>
</tr>
</tbody>
</table>

 

## 操作


下表包含在 MBAM 运行时可能出现的事件 Id 的消息和疑难解答信息。

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">事件 ID</th>
<th align="left">来源</th>
<th align="left">活动符号</th>
<th align="left">消息</th>
<th align="left">疑难解答</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>raid-1</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/管理员</p></td>
<td align="left"><p>WebAppSpnError</p></td>
<td align="left"><p>应用程序： {SiteName} {VirtualDirectory} 缺少以下服务主体名称（Spn）： {ListOfSpns} 在帐户上注册所需的 Spn： {ExecutionAccount}。</p></td>
<td align="left"><p>若要使集成的 Windows 身份验证成功，需要具备必要的 Spn。 此消息指示未正确配置 MBAM 应用程序所需的 SPN。 此事件中包含的详细信息应提供详细信息。</p>
<p>有关详细信息，请参阅 MBAM 2.5 服务器中的 "服务主体名称（SPN）" <a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md#bkmk-prereqsams" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md#bkmk-prereqsams)"> 独立和 Configuration Manager 集成拓扑的先决条件 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>第</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/运营</p></td>
<td align="left"><p>PerformanceCounterError</p></td>
<td align="left"><p>检索性能计数器时出错。</p>
<p>消息： {EventMessage} 类别： {CategoryOfPerformanceCounter} 性能计数器： {NameOfPerformanceCounter} Instance： {性能计数器类别实例的名称} 异常： {ExceptionThrown}</p>
<p>跟踪消息将包含实际异常消息，其中一些解释如下：</p>
<p><strong>ArgumentNullException </strong> ：如果所请求的性能计数器的类别、计数器或实例无效，则会引发此异常。</p>
<p><strong>InvalidOperationException： " </strong> 类别名称" 为空字符串（ &quot; &quot; ）。-或-counterName 为空字符串（ &quot; &quot; ）。</p>
<p>-或-请求的读/写权限设置对此计数器无效。</p>
<p>-或-指定的类别不存在（如果为 readOnly，则为 true）。</p>
<p>-或-指定的类别不是 .NET Framework 自定义类别（如果为 readOnly）。</p>
<p>-或-指定的类别被标记为多实例，并且需要使用实例名称创建性能计数器。</p>
<p>-或-instanceName 的长度超过127个字符。</p>
<p>-或-类别和 counterName 已本地化为不同语言。</p>
<p><strong>ComponentModel </strong> ：访问系统 API 时发生错误。</p>
<p><strong>PlatformNotSupportedException </strong> ：平台是 windows 98 或 Windows Millennium Edition （ME），它不支持性能计数器。</p>
<p><strong>UnauthorizedAccessException </strong> ：在没有管理权限的情况下执行的代码尝试读取性能计数器。</p></td>
<td align="left"><p>事件中包含的消息将提供有关引发的异常的更多详细信息。 如果引发了 UnauthorizedAccessException，请验证 MBAM 执行帐户（应用池）是否具有对性能计数器 Api 的访问权限。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>100</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/管理员</p></td>
<td align="left"><p>AdminServiceRecoveryDbError</p></td>
<td align="left"><p><strong>GetMachineUsers </strong> ：获取数据库中的用户信息时发生错误。 消息： {message}-或-</p>
<p><strong>GetRecoveryKey </strong> ：从数据库获取恢复密钥时发生错误。 消息： {message}-或-</p>
<p><strong>GetRecoveryKey </strong> ：获取数据库中的用户信息时发生错误。 消息： {message}-或-</p>
<p><strong>GetRecoveryKeyIds </strong> ：获取数据库中的恢复密钥 id 时出错。 消息： {message}-或-</p>
<p><strong>GetTpmHashForUser </strong> ：获取恢复数据库中的 TPM 哈希数据时发生错误。 消息： {message}-或-</p>
<p><strong>GetTpmHashForUser </strong> ：获取恢复数据库中的 TPM 哈希数据时发生错误。 消息： {message}-或-</p>
<p><strong>QueryDriveRecoveryData </strong> ：从数据库获取驱动器恢复数据时发生错误。 消息： {message}-或-</p>
<p><strong>QueryRecoveryKeyIdsForUser </strong> ：获取数据库中的恢复密钥 id 时出错。 消息： {message}-或-</p>
<p><strong>QueryVolumeUsers </strong> ：获取数据库中的用户信息时发生错误。</p></td>
<td align="left"><p>当与 MBAM 恢复数据库通信时出现异常时，将记录此消息。 阅读跟踪中包含的信息，获取有关异常的特定详细信息。</p>
<p>有关详细的疑难解答步骤，请参阅 TechNet 文章 <a href="https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx" data-raw-source="[How to Troubleshoot Connecting to the SQL Server Database Engine](https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx)"> 如何解决连接到 SQL Server 数据库引擎的问题 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>101</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/管理员</p></td>
<td align="left"><p>AdminServiceComplianceDbError</p></td>
<td align="left"><p><strong>GetRecoveryKey </strong> ：将审核事件记录到合规性数据库时出错。 消息： {message}-或-</p>
<p><strong>GetRecoveryKeyIds </strong> ：将审核事件记录到合规性数据库时出错。 消息： {message}-或-</p>
<p><strong>GetTpmHashForUser </strong> ：将审核事件记录到合规性数据库时出错。 消息： {message}-或-</p>
<p><strong>QueryRecoveryKeyIdsForUser </strong> ：将审核事件记录到合规性数据库时出错。 消息： {message}-或-</p>
<p><strong>QueryDriveRecoveryData </strong> ：将审核事件记录到合规性数据库时出错。 消息： {message}</p></td>
<td align="left"><p>当通信 MBAM 合规性数据库时出现异常时，将记录此消息。 阅读跟踪中包含的信息，获取有关异常的特定详细信息。</p>
<p>有关详细的疑难解答步骤，请参阅 TechNet 文章 <a href="https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx" data-raw-source="[How to Troubleshoot Connecting to the SQL Server Database Engine](https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx)"> 如何解决连接到 SQL Server 数据库引擎的问题 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>102</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/管理员</p></td>
<td align="left"><p>AgentServiceRecoveryDbError</p></td>
<td align="left"><p></p></td>
<td align="left"><p>此消息指示 MBAM 代理服务尝试与恢复数据库通信时出现异常。 阅读事件中包含的消息，获取有关异常的特定信息。</p>
<p>请参阅 TechNet 文章 <a href="https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx" data-raw-source="[How to Troubleshoot Connecting to the SQL Server Database Engine](https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx)"> 如何解决连接到 SQL Server 数据库引擎的问题 </a> ，以验证 MBAM 应用池帐户是否具有在 MBAM 恢复数据库上进行连接或执行的必需权限。</p></td>
</tr>
<tr class="even">
<td align="left"><p>103</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/管理员</p></td>
<td align="left"><p>AgentServiceError</p></td>
<td align="left"><p>无法检测客户端计算机帐户或数据迁移用户帐户。 - 或者 -</p>
<p>呼叫方标识的帐户验证失败。</p></td>
<td align="left"><p>每当调用 &quot; &quot; &quot; MBAM 代理服务上的 PostKeyRecoveryInfo、IsRecoveryKeyResetRequired &quot; 、 &quot; CommitRecoveryKeyRest &quot; 或 &quot; GetTpmHash &quot; web 方法时，它都将检索呼叫者上下文以获取呼叫方凭据。 如果调用方上下文为 null 或为空，则 MBAM 代理服务日志 &quot; 无法检测客户端计算机帐户或数据迁移用户帐户。&quot;</p>
<p>&quot; &quot; 如果 web 方法期望呼叫方使用的是计算机帐户且呼叫方不是计算机帐户，或者 web 方法 excepting 调用方是用户帐户，并且调用方不是数据迁移组帐户的用户帐户或成员，则会记录呼叫者身份的邮件帐户验证失败。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>104</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/管理员</p></td>
<td align="left"><p>StatusServiceComplianceDbConfigError</p></td>
<td align="left"><p>&quot;注册表中的合规性数据库连接字符串为空。&quot;</p></td>
<td align="left"><p>当合规性 db 连接字符串无效时，将记录此消息。</p>
<p>验证注册表项 HKLM\Software\Microsoft\MBAM Server\Web\ComplianceDBConnectionString 中的值</p></td>
</tr>
<tr class="even">
<td align="left"><p>105</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/管理员</p></td>
<td align="left"><p>StatusServiceComplianceDbError</p></td>
<td align="left"><p></p></td>
<td align="left"><p>此错误表示 MBAM 网站/web 服务无法连接到 MBAMCompliance 数据库。</p>
<p>有关 <a href="https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx" data-raw-source="[How to Troubleshoot Connecting to the SQL Server Database Engine](https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx)"> 连接到 SQL Server 数据库引擎 </a> 以验证 IIS 应用池帐户是否可以连接到 MBAM 合规性数据库的问题，请参阅 TechNet 文章。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>106</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/管理员</p></td>
<td align="left"><p>HelpdeskError</p></td>
<td align="left"><p>对 URL {URL} 的请求导致内部错误。 - 或者 -</p>
<p>获取执行上下文信息时发生错误。 无法验证服务主体名称（SPN）注册。 - 或者 -</p>
<p>验证服务主体名称（SPN）注册时出错。</p></td>
<td align="left"><p>指示帮助应用程序中引发了未处理的异常。 查看 MBAM 管理员操作通道中的日志条目以查找特定异常。 或</p>
<p>在初始技术支持网站的加载操作期间，执行 SPN 检查。 若要验证 SPN，帮助台需要执行帐户信息、IIS Sitename 以及对应于支持人员网站的 ApplicationVirtualPath。 如果这些错误消息中的一个或多个无效或丢失，则会记录此错误消息。 或</p>
<p>此消息表示执行 SPN 验证时引发安全异常。 请参阅事件详细信息部分中包含的异常。</p></td>
</tr>
<tr class="even">
<td align="left"><p>107</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/管理员</p></td>
<td align="left"><p>SelfServicePortalError</p></td>
<td align="left"><p>获取用户的恢复密钥时发生错误。 EventDetails： {ExceptionMessage}-或-</p>
<p>获取执行上下文信息时发生错误。 无法验证服务主体名称（SPN）注册。 EventDetails：用户： {username Identity} 应用程序： {SiteName\ApplicationVirtualPath}-或-</p>
<p>验证服务主体名称（SPN）注册时出错。 EventDetails:{ExceptionMessage}</p></td>
<td align="left"><p>指示在请求检索恢复密钥时引发意外异常。 请参阅事件详细信息部分中包含的异常消息。 如果 MBAM 支持人员上启用了跟踪功能，请参阅跟踪数据以获取详细的异常消息。 或</p>
<p>在初始加载操作期间，自助服务门户（SSP）检索与自助服务网站对应的执行帐户信息、IIS Sitename 和 ApplicationVirtualPath，以验证 SPN。 当这些错误消息中的一个或多个无效时，将记录此错误消息。 或</p>
<p>此消息表示执行 SPN 验证时引发了安全异常。 请参阅事件详细信息部分中包含的异常。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>108</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/管理员</p></td>
<td align="left"><p>DomainControllerError</p></td>
<td align="left"><p>解析域名时出错 {DomainName}，发生内存分配故障。 - 或者 -</p>
<p>无法调用 DsGetDcName 方法。 EventDetails:{ExceptionMessage}</p></td>
<td align="left"><p>为了解析域名，MBAM 利用 &quot; DsGetDcName &quot; windows API。 当 &quot; DsGetDcName &quot; 返回 &quot; ERROR_NOT_ENOUGH_MEMORY &quot; 指示内存分配失败时，将记录此消息。 或</p>
<p>此消息表示 &quot; DsGetDcName &quot; API 方法在托管系统上不可用。</p></td>
</tr>
<tr class="even">
<td align="left"><p>109</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/管理员</p></td>
<td align="left"><p>WebAppRecoveryDbError</p></td>
<td align="left"><p>读取恢复数据库的配置时发生错误。 未配置恢复数据库的连接字符串。 消息： {message}-或-</p>
<p><strong>DoesUserHaveMatchingRecoveryKey </strong> ：获取用户的恢复密钥 id 时出错。 消息： {message}-或-</p>
<p><strong>QueryDriveRecoveryData </strong> ：获取驱动器恢复数据时发生错误。 消息： {message}-或-</p>
<p><strong>QueryRecoveryKeyIdsForUser </strong> ：获取用户的恢复密钥 id 时出错。 消息： {message}-或-</p>
<p>从恢复数据库获取 TPM 密码哈希时出错。 EventDetails:{ExceptionMessage}</p></td>
<td align="left"><p>此消息表示 HKLM\Software\Microsoft\MBAM Server\Web\RecoveryDBConnectionString 上的恢复数据库连接字符串信息 &quot; &quot; 无效。 验证给定的注册表项值。 或</p>
<p>如果记录了任何剩余消息，请参阅 TechNet 文章中列出的疑难解答步骤，以 <a href="https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx" data-raw-source="[How to Troubleshoot Connecting to the SQL Server Database Engine](https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx)"> 验证连接到 SQL Server 数据库引擎时 </a> 是否可以使用应用池凭据验证是否可以使用 IIS 服务器中的 MBAM 恢复数据库建立连接。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>110</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/管理员</p></td>
<td align="left"><p>WebAppComplianceDbError</p></td>
<td align="left"><p>读取合规性数据库的配置时发生错误。 未配置合规性数据库的连接字符串。 - 或者 -</p>
<p><strong>GetRecoveryKeyForCurrentUser </strong> ：将审核事件记录到合规性数据库时出错。 消息： {message}-或-</p>
<p><strong>QueryRecoveryKeyIdsForUser </strong> ：将审核事件记录到合规性数据库时出错。 消息： {message}-或-</p>
<p><strong>QueryRecoveryKeyIdsForUser </strong> ：将审核事件记录到合规性数据库时出错。 消息： {message}</p></td>
<td align="left"><p>此消息表示 HKLM\Software\Microsoft\MBAM Server\Web\ComplianceDBConnectionString 上的合规性 db 连接字符串信息 &quot; &quot; 无效。 验证与上面的注册表项对应的值。 或</p>
<p>如果记录了任何剩余消息，请参阅 TechNet 文章中列出的疑难解答步骤，以 <a href="https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx" data-raw-source="[How to Troubleshoot Connecting to the SQL Server Database Engine](https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx)"> 验证连接到 SQL Server 数据库引擎时 </a> 是否可以使用应用池凭据验证是否可以使用 IIS 服务器中的 MBAM 合规性数据库建立连接。</p></td>
</tr>
<tr class="even">
<td align="left"><p>111</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/管理员</p></td>
<td align="left"><p>WebAppDbError</p></td>
<td align="left"><p></p></td>
<td align="left"><p>这些错误指示以下两种情况之一</p>
<ul>
<li><p>MBAM 网站/webservices 无法连接到 MBAMCompliance 或 MBAMRecovery 数据库</p></li>
<li><p>MBAM 网站/webservices 执行帐户（应用池帐户）无法在 MBAMCompliance 或 MBAMRecovery 数据库上运行 GetVersion 存储过程</p></li>
</ul>
<p>事件中包含的消息将提供有关异常的更多详细信息。</p>
<p>请参阅 TechNet 文章中列出的疑难解答步骤， <a href="https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx" data-raw-source="[How to Troubleshoot Connecting to the SQL Server Database Engine](https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx)"> 了解如何解决连接到 SQL Server 数据库引擎的问题， </a> 以验证 MBAM 执行帐户（应用池帐户）是否可以连接到 MBAM 合规性/恢复数据库，以及它是否具有执行 GetVersion 存储过程的权限。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>112</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/管理员</p></td>
<td align="left"><p>WebAppError</p></td>
<td align="left"><p>验证服务主体名称（SPN）注册时出错。 EventDetails:{ExceptionMessage}</p></td>
<td align="left"><p>若要执行 SPN 验证，MBAM 查询 Active Directory 以检索映射的执行帐户的 Spn 列表。 MBAM 还会查询 &quot;ApplicationHost.config&quot; 以获取 MBAM 网站绑定。 此错误消息指示 MBAM 无法与 Active Directory 通信，或者它无法加载 applicationHost.config 文件。</p>
<p>验证执行帐户（应用池帐户）是否有权查询广告或 ApplicationHost.config 文件。 同时验证 ApplicationHost.config 文件中的网站绑定条目。</p></td>
</tr>
<tr class="even">
<td align="left"><p>200</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/运营</p></td>
<td align="left"><p>HelpDeskInformation</p></td>
<td align="left"><p>管理网站应用程序已成功找到并连接到受支持的恢复数据库版本。 - 或者 -</p>
<p>管理网站应用程序已成功找到并连接到受支持的合规性数据库版本。</p></td>
<td align="left"><p>指示与 MBAM 帮助台网站中的恢复/合规性数据库的连接成功。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>201</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/运营</p></td>
<td align="left"><p>SelfServicePortalInformation</p></td>
<td align="left"><p>自助服务门户应用程序已成功找到并连接到受支持的恢复数据库版本。 - 或者 -</p>
<p>自助服务门户应用程序已成功找到并连接到受支持的合规性数据库版本。</p></td>
<td align="left"><p>指示与 MBAM 自助服务门户的恢复/合规性数据库的连接成功。</p></td>
</tr>
<tr class="even">
<td align="left"><p>202</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/运营</p></td>
<td align="left"><p>WebAppInformation</p></td>
<td align="left"><p>已正确注册应用程序的 Spn。</p></td>
<td align="left"><p>指示 MBAM 支持人员网站所需的 Spn 已正确注册到正在执行的帐户。</p></td>
</tr>
</tbody>
</table>

 


## 相关主题


[MBAM 2.5 的技术参考](technical-reference-for-mbam-25.md)

[客户端事件日志](client-event-logs.md)

 
## 已获得 MBAM 的建议？
- 在[此处](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)添加或投票建议。
- 对于 MBAM 问题，请使用[MBAM TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。
 





