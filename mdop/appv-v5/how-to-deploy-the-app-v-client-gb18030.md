---
title: 如何部署 App-V Client
description: 如何部署 App-V Client
ms.author: dansimp
author: dansimp
ms.assetid: 9c4e67ae-ddaf-4e23-8c16-72d029a74a27
ms.reviewer: ''
manager: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/05/2018
ms.openlocfilehash: 4e246e13bf59f167eade77200afd866c6a3c41fe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798466"
---
# 如何部署 App-V Client


使用以下过程安装 Microsoft Application Virtualization （App-v）5.0 客户端和远程桌面服务客户端。 必须安装与目标计算机的操作系统匹配的客户端版本。

<a href="" id="bkmk-clt-install-prereqs"></a>**开始之前应执行的操作**

1. 查看和安装软件必备条件：

   安装与要安装的 App-v 版本对应的必备软件：

   - [关于 App-V 5.0 SP3](about-app-v-50-sp3.md)

   - App-v 5.0 SP1 和应用程序-V 5.0 SP2-这些版本中没有新的先决条件

   - [App-V 5.0 先决条件](app-v-50-prerequisites.md)

2. 查看适用于你的安装的客户端共存和不受支持的方案：


   |                                               |                                                                                                                            |
   |-----------------------------------------------|----------------------------------------------------------------------------------------------------------------------------|
   |      部署共存的应用程序-V 客户端       | [计划 App-V 5.0 Sequencer 和 Client 部署](planning-for-the-app-v-50-sequencer-and-client-deployment.md) |
   | 不受支持或受限的安装方案 |                         [App-V 5.0 支持的配置](app-v-50-supported-configurations.md)                         |

   ---

3. 查看客户端注册表、日志和疑难解答信息的位置：

#### 客户端注册信息
<ul><li>默认情况下，在安装 app-v 5.0 客户端之后，客户端信息将存储在注册表中的以下注册表项中：<p><p><code>HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\APPV\CLIENT</code></li><li>将虚拟化程序包部署到运行 App-v 客户端的计算机时，关联的程序包数据存储在以下位置：<p><p><code>C:\ProgramData\App-V</code><p><p>但是，你可以通过以下注册表项重新配置此位置：<p><p><code>HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\SOFTWARE\MICROSOFT\APPV\CLIENT\STREAMING\PACKAGEINSTALLATIONROOT</code></li></ul>

#### 客户端日志文件                  
<ul><li>对于与 App-v 5.0 客户端相关联的日志文件信息，请在以下日志中搜索：<p><p><code>Event logs/Applications and Services Logs/Microsoft/AppV</code></li><li>在 App-v 5.0 SP3 中，某些日志已合并并移动到以下位置：<p><p><code>Event logs/Applications and Services Logs/Microsoft/AppV/ServiceLog</code><p><p>有关已移动日志的列表，请参阅[关于 App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-event-logs-moved)。</li><li>当前存储在运行 App-v 5.0 客户端的计算机上的程序包将保存到以下位置：<p><p><code>C:\ProgramData\App-V\<<em>package id</em>>\<<em>version id</em>></code></li></ul>

#### 客户端安装疑难解答信息
- 请参阅 **% temp%** 文件夹中的错误日志。 
- 若要查看日志文件，请单击 "**开始**"，键入 **% temp%**，然后查找 " **appv_ 日志**"。 

## 安装 app-v 5.0 客户端

1. 将 app-v 5.0 客户端安装文件复制到将在其上安装的计算机。<p><p>从以下客户端类型中进行选择：


   |                  客户端类型                  |          要使用的文件          |
   |-----------------------------------------------|-------------------------------|
   |        客户端的标准版本         |   **appv_client_setup.exe**   |
   | 客户端的远程桌面服务版本 | **appv_client_setup_rds.exe** |

   ---

2. 双击安装文件，然后单击 "**安装**"。 安装开始之前，安装程序会检查计算机上是否缺少任何缺少[的 app-v 5.0 先决条件](app-v-50-prerequisites.md)。

3. 查看并接受软件许可条款，选择是否使用 Microsoft 更新以及是否参与 Microsoft 客户体验改善计划，并单击 "**安装**"。

4. 在 "**安装成功完成**" 页面上，单击 "**关闭**"。

   安装过程将在**程序**中为 app-v 客户端创建以下条目：

   -   **.exe**

   -   **.msi**

   -   **语言包**

   >[!NOTE]
   >安装后，仅可卸载 .exe 文件。


## 使用脚本安装 app-v 5.0 客户端

1. 在目标计算机上安装所有必需的必备软件。 [在开始之前，请查看要执行的操作](#bkmk-clt-install-prereqs)。 如果使用 .msi 文件安装客户端，则如果缺少任何先决条件，安装将失败。

2. 若要使用脚本安装 App-v 5.0 客户端，请将以下参数与**appv\_client\_setup.exe**结合使用。

   >[!NOTE]
   >除了 **/log**参数外，客户端 Windows Installer （.msi）支持相同的开关集。

   |                                  |                                                                                                                                                                                                                                                                                                                                                                                                                                     |
   |----------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |           /INSTALLDIR            |                                                                                                                                                               指定安装目录。 示例用法：<p><p>**/INSTALLDIR = C:\Program Files\AppV 客户端**                                                                                                                                                                |
   |            /CEIPOPTIN            |                                                                                                                                                          允许参与客户体验改善计划。 示例用法：<p><p>**/CEIPOPTIN = [0 \ | 1 \]**                                                                                                                                                           |
   |             /MUOPTIN             |                                                                                                                                                                                 启用 Microsoft 更新。 示例用法：<p><p>**/MUOPTIN = [0 \ | 1 \]**                                                                                                                                                                                  |
   |     /PACKAGEINSTALLATIONROOT     |                                                                                                                                         指定要在其中安装所有新应用程序和更新的目录。 示例用法： <p><p>**/PACKAGEINSTALLATIONROOT = "C:\App-V 程序包"**                                                                                                                                         |
   |        /PACKAGESOURCEROOT        |                                                                                                                                                  替代用于下载软件包内容的源位置。 示例用法：<p><p>**/PACKAGESOURCEROOT = ' <http://packageStore> '**                                                                                                                                                  |
   |            /AUTOLOAD             |                                                                                           指定在特定计算机上由 app-v 5.0 加载新程序包的方式。 启用以下选项： [1];自动加载所有程序包 [2];或自动加载 "无程序包" [0]。 示例用法：<p><p>**/AUTOLOAD = [0 \ | 1 \ | 2 \]**                                                                                           |
   |     /SHAREDCONTENTSTOREMODE      |                                                                                                                                           指定流式处理的程序包内容将不会保存到本地硬盘。 示例用法： <p><p>**/SHAREDCONTENTSTOREMODE = [0 \ | 1 \]**                                                                                                                                            |
   |          /MIGRATIONMODE          |                                                                                                                     允许 App-v 5.0 客户端修改与使用早期版本创建的程序包相关联的快捷方式和 FTAs。 示例用法：<p><p>**/MIGRATIONMODE = [0 \ | 1 \]**                                                                                                                     |
   |      /ENABLEPACKAGESCRIPTS       |                                                                                                                                   启用应运行的程序包清单文件或配置文件中定义的脚本。 示例用法：<p><p>**/ENABLEPACKAGESCRIPTS = [0 \ | 1 \]**                                                                                                                                   |
   |    /ROAMINGREGISTRYEXCLUSIONS    |                                                                                                                                      指定将不随用户配置文件漫游的注册表路径。 示例用法：<p><p>**/ROAMINGREGISTRYEXCLUSIONS = software\classes; software\clients**                                                                                                                                      |
   |      /ROAMINGFILEEXCLUSIONS      |                                                                                                                                  指定相对于% userprofile% 的文件路径，不要与用户的配置文件一起漫游。 示例用法： <p><p>**/ROAMINGFILEEXCLUSIONS ' 桌面; 我的图片 '**                                                                                                                                   |
   |   /S [1-5] PUBLISHINGSERVERNAME    |                                                                                                                                                           显示发布服务器的名称。 示例用法：<p><p>**/S2PUBLISHINGSERVERNAME = MyPublishingServer**                                                                                                                                                            |
   |    /S [1-5] PUBLISHINGSERVERURL    |                                                                                                                                                                显示发布服务器的 URL。 示例用法：<p><p>**/S2PUBLISHINGSERVERURL = \\pubserver**                                                                                                                                                                |
   |   /S [1-5] GLOBALREFRESHENABLED    |                                                                                                                                                                    启用全局发布刷新。 示例用法：<p><p>**/S2GLOBALREFRESHENABLED = [0 \ | 1 \]**                                                                                                                                                                     |
   |   /S [1-5] GLOBALREFRESHONLOGON    |                                                                                                                                                             当用户登录时启动全局发布刷新。 示例用法：<p><p>**/S2LOGONREFRESH = [0 \ | 1 \]**                                                                                                                                                              |
   |   /S [1-5] GLOBALREFRESHINTERVAL   |                                                                                                                                         指定发布刷新间隔，其中**0**表示不定期刷新。 示例用法： **/S2PERIODICREFRESHINTERVAL = [0-744]**                                                                                                                                         |
   | /S [1-5] GLOBALREFRESHINTERVALUNIT |                                                                                                                                                            指定间隔单位（小时 [0]，天 [1]）。 示例用法：<p><p>**/S2GLOBALREFRESHINTERVALUNIT = [0 \ | 1 \]**                                                                                                                                                            |
   |    /S [1-5] USERREFRESHENABLED     |                                                                                                                                                                          启用用户发布刷新。 示例用法： **/S2USERREFRESHENABLED = [0 \ | 1 \]**                                                                                                                                                                          |
   |    /S [1-5] USERREFRESHONLOGON     |                                                                                                                                                              用户登录时启动用户发布刷新。 示例用法：<p><p>**/S2LOGONREFRESH = [0 \ | 1 \]**                                                                                                                                                               |
   |    /S [1-5] USERREFRESHINTERVAL    |                                                                                                                                         指定发布刷新间隔，其中**0**表示不定期刷新。 示例用法： **/S2PERIODICREFRESHINTERVAL = [0-744]**                                                                                                                                         |
   |  /S [1-5] USERREFRESHINTERVALUNIT  |                                                                                                                                                             指定间隔单位（小时 [0]，天 [1]）。 示例用法：<p><p>**/S2USERREFRESHINTERVALUNIT = [0 \ | 1 \]**                                                                                                                                                             |
   |               /Log               |                                                                                                                                                指定保存日志信息的位置。 默认位置为% Temp%。 示例用法：<p><p>**/log C:\logs\log.log**                                                                                                                                                |
   |                /q                |                                                                                                                                                                                                指定无人参与安装。                                                                                                                                                                                                |
   |             /REPAIR              |                                                                                                                                                                                               修复以前的客户端安装。                                                                                                                                                                                               |
   |            /NORESTART            | 阻止计算机在客户端安装后重新启动。<p><p>该参数可防止最终用户计算机在安装每个更新后重新启动，并允许你在方便时计划重启。 例如，你可以安装 app-v 5.0 SPX，然后安装修补程序包 Y，而无需在安装 Service Pack 后重新启动。 安装完成后，必须重新启动才能开始使用 app-v。 |
   |            /UNINSTALL            |                                                                                                                                                                                                       卸载客户端。                                                                                                                                                                                                        |
   |           /ACCEPTEULA            |                                                                                                                                              接受许可协议。 这是无人参与安装所必需的。 示例用法：<p><p>**/ACCEPTEULA**或 **/ACCEPTEULA = 1**                                                                                                                                               |
   |             /LAYOUT              |                                                                                                                               指定关联的布局操作。 它还将 Windows Installer （.msi）和脚本文件提取到文件夹中，但不安装 app-v 5.0。 不应为任何值。                                                                                                                                |
   |            /LAYOUTDIR            |                                                                                                                                                 指定布局目录。 需要字符串值。 示例用法：<p><p>**/LAYOUTDIR = "C:\Application Virtualization 客户端"**                                                                                                                                                  |
   |          /？、/h、/help           |                                                                                                                                                                                      请求有关以前的安装参数的帮助。                                                                                                                                                                                      |

   ---

## 使用 Windows Installer （.msi）文件安装 App-v 5.0 客户端

1. 在目标计算机上安装所需的先决条件。 [在开始之前，请查看要执行的操作](#bkmk-clt-install-prereqs)。 如果未满足任何先决条件，安装将失败。

2. 在使用 App-v 5.0 Windows Installer （.msi）文件安装客户端之前，请确保目标计算机没有任何挂起的重启。 Windows Installer 文件不会标记待重启。

3. 将以下 Windows Installer 文件之一部署到目标计算机。 你指定的文件必须与目标计算机的配置相匹配。


   |                       部署类型                        |      部署此文件       |
   |-----------------------------------------------------------------|-----------------------------|
   | 计算机运行的是32位 Microsoft Windows 操作系统 |   appv_client_MSI_x86.msi   |
   | 计算机运行的是64位 Microsoft Windows 操作系统 |   appv_client_MSI_x64.msi   |
   | 你正在部署 app-v 5.0 远程桌面服务客户端  | appv_client_rds_MSI_x64.msi |

   ---

4. 使用下表中的信息，根据目标计算机所需的语言选择要安装的相应语言包 **。** 表中的**xxxx**指语言包的目标区域设置。

   **开始之前应了解的事项：** 

   -  标准 App-v 5.0 客户端和 app-v 5.0 客户端的远程桌面服务版本均共有语言包。

   -  如果您使用 **.exe**安装 app-v 5.0 客户端，安装程序将仅部署与目标计算机上运行的操作系统匹配的语言包。

   -  若要在目标计算机上部署其他语言包，请使用**Windows Installer （.msi）文件中的步骤安装 app-v 5.0 客户端**。

   |                       部署类型                        |       部署此文件       |
   |-----------------------------------------------------------------|------------------------------|
   | 计算机运行的是32位 Microsoft Windows 操作系统 | appv_client_LP_xxxx_ x86.msi |
   | 计算机运行的是64位 Microsoft Windows 操作系统 | appv_client_LP_xxxx_ x64.msi |

   ---

   已**获得有关 app-v 的建议**？ 添加或投票[建议](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)。 <p><p>**遇到了 app-v 问题？** 使用 app-v [TechNet 论坛](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相关主题


[部署 App-V 5.0](deploying-app-v-50.md)

[关于 Client 配置设置](about-client-configuration-settings.md)

[如何卸载 App-V 5.0 Client](how-to-uninstall-the-app-v-50-client.md)
