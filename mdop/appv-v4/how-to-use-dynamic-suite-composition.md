---
title: 如何使用动态套件合成
description: 如何使用动态套件合成
author: dansimp
ms.assetid: 24147feb-a0a8-4791-a8e5-cbe5fe13c762
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3bff4c9721352785cf6db5c497234ceaa3c5e448
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798967"
---
# 如何使用动态套件合成


应用程序虚拟化中的动态套件合成使你能够将应用程序定义为依赖于另一个应用程序，如中间件或插件。 这使应用程序能够与虚拟环境中的中间件或插件交互，这通常会被阻止。 这很有用，因为辅助应用程序包可以与多个其他应用程序一起使用，这两个应用程序称为*主要应用*程序，这使每个主应用程序都可以引用同一辅助程序包。

当序列应用程序依赖于插件（如 ActiveX 控件）或依赖中间件（如 OLE DB 或 Java 运行时环境（JRE））的应用程序时，可以使用动态套件合成。 如果使用这些依赖组件的每个应用程序都需要排序（包括组件），则对这些组件的更新需要重新对所有主应用程序进行排序。 如果对不带组件的主要应用程序进行排序，然后将中间件或插件序列化为辅助包，则只有辅助包必须更新。

此方法的一个优点是减小了主要程序包的大小。 另一个优点是，它使您能够更好地控制辅助应用程序的访问权限。 请注意，辅助应用程序可以按常规方式进行流处理，无需完全缓存即可运行。

主程序包可以有多个辅助程序包。 但是，仅支持一个依赖级别，因此不能将辅助程序包定义为依赖于另一个辅助程序包。 辅助应用程序也只能是中间件或插件，不能是另一个完整软件产品。

如果你计划使几个主要应用程序依赖于单个中间件产品，请确保在部署之前测试此配置以确定对系统性能的潜在影响。

**重要提示** 程序包依赖项可指定为主应用程序的强制。 如果辅助程序包已标记为必需，并且由于某些原因加载时无法访问它，则辅助程序包的加载将失败。 此外，当用户尝试启动时，主应用程序将失败。

 

你可以使用以下过程来创建辅助包（对于插件或中间件组件），然后可以使用最终过程来定义辅助程序包的 OSD 文件中的依赖关系。

**使用动态套件合成创建插件的辅助程序包**

1.  在使用干净映像设置的先后顺序计算机上，安装 Application Virtualization Sequencer 并保存计算机状态。

2.  序列化主应用程序，并将程序包保存到服务器上的内容文件夹。

3.  将顺序计算机从步骤1还原到其保存的状态。

4.  在排序计算机上本地安装和配置主应用程序。

    **重要提示** 必须为辅助程序包指定新的程序包根。

     

5.  启动 sequencer 监视阶段。

6.  在序列化计算机上安装插件，并根据需要进行配置。

7.  打开主应用程序，并确认插件是否正常工作。

8.  在 sequencer 控制台中，创建一个虚拟应用程序来表示将包含该插件的辅助程序包，并选择一个图标。

9.  将程序包保存到服务器上的内容文件夹。

    **注意** 为了帮助管理辅助程序包，建议程序包名称包括术语 "辅助程序包"，以强调这是一个不充当独立应用程序的程序包，例如**\ [插入 name \] 辅助程序包**。

     

**使用动态套件合成创建中间件的辅助程序包**

1.  在使用干净映像设置的先后顺序计算机上，安装 Application Virtualization Sequencer 并保存计算机状态。

2.  在排序计算机上本地安装中间件，并对其进行配置。

3.  序列化主应用程序，并将程序包保存到服务器上的内容文件夹。

4.  将顺序计算机从步骤1还原到其保存的状态。

5.  启动 sequencer 以创建新的程序包。

6.  启动 sequencer 监视阶段。

7.  在排序计算机上安装中间件应用程序，并将其配置为在典型安装中使用。

8.  完成排序过程。

9.  将程序包保存到服务器上的内容文件夹。

    **注意** 为了帮助管理辅助程序包，建议程序包名称包括术语 "辅助程序包"，以强调这是一个不充当独立应用程序的程序包，例如**\ [中间件名称 \] 辅助包**。

     

**在主程序包中定义相关性**

1. 在服务器上，打开辅助程序包的 OSD 文件进行编辑。 （最好使用 XML 编辑器对 OSD 文件进行更改; 但是，你可以使用记事本作为替代项。）

2. 从该文件复制**基本代码 HREF**行。

3. 打开主要程序包的 OSD 文件进行编辑。

4. <strong> &lt; &gt; </strong> 在** &lt; VIRTUALENV &gt; **节末尾的** &lt; /ENVLIST &gt; **标记后面的 " ** &lt; /VIRTUALENV &gt; ** " 标记前插入 "相关性" 标记。

5. 在刚刚创建的** &lt; 依赖项 &gt; **标记之后，在辅助包中粘贴**基本代码 HREF**行。

6. 如果辅助程序包是必需的程序包，这意味着必须在启动主程序包之前启动它，请在**CODEBASE**标记内添加**强制 = "TRUE"** 属性。 如果不是必需的，则可以省略该属性。

7. 插入以下内容以关闭 " ** &lt; 相关性 &gt; ** " 标记：

   **&lt;/DEPENDENCIES&gt;**

8. 查看你对 OSD 文件所做的更改，然后保存并关闭该文件。 以下示例显示了添加的分区应如何显示。 此处显示的标记值仅适用于示例。

   **&lt;VIRTUALENV&gt;**

        **&lt;ENVLIST&gt;**

   **…**

        **&lt;/ENVLIST&gt;**

        **&lt;DEPENDENCIES&gt;**

             **&lt;CODEBASE HREF="rtsp://virt\_apps/package.1/package.1.sft" GUID="D54C80FA-9DFF-459D-AA33-DD852C9FBFBA" SYSGUARDFILE="package.1\\osguard.cp"/&gt;**

             **&lt;CODEBASE HREF="rtsp://sample\_apps/package.2/sample.sft" GUID="D54C80FA-9DFF-459D-AA33-DD852C9FBFBA" SYSGUARDFILE="package.2\\osguard.cp" MANDATORY="TRUE" /&gt;**

        **&lt;/DEPENDENCIES&gt;**

   **&lt;/VIRTUALENV&gt;**

9. 如果辅助程序包在 OSD 文件的** &lt; ENVLIST &gt; **部分中有任何条目，则必须将这些条目复制到主程序包的同一节中。

## 相关主题


[如何使用 App-v Sequencer 创建或升级虚拟应用程序](how-to-create-or-upgrade-virtual-applications-using--the-app-v-sequencer.md)

 

 





