---
title: 使用 App-V 部署 Microsoft Office 2013
description: 使用 App-V 部署 Microsoft Office 2013
author: dansimp
ms.assetid: 9a7be05e-2a7a-4874-af25-09c0f5037876
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: f6a54cadce79ff3680fd69206eba8ac3fbe83a68
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10798593"
---
# 使用 App-V 部署 Microsoft Office 2013


使用本文中的信息可使用 Microsoft Application Virtualization （App-v）5.1 或更高版本将 Microsoft Office 2013 作为虚拟化的应用程序提供给组织中的计算机。 有关使用 app-v 交付 Office 2010 的信息，请参阅[使用 App-v 部署 Microsoft Office 2010](deploying-microsoft-office-2010-by-using-app-v51.md)。 若要通过 App-v 成功部署 Office 2013，你需要熟悉 Office 2013 和 App-v。

本主题包含以下各节：

-   [开始之前需要了解的内容](#bkmk-before-you-start)

-   [使用 Office 部署工具为 App-v 创建 Office 2013 程序包](#bkmk-create-office-pkg)

-   [发布 app-v 5.1 的 Office 程序包](#bkmk-pub-pkg-office)

-   [自定义和管理 Office App-v 程序包](#bkmk-custmz-manage-office-pkgs)

## <a href="" id="bkmk-before-you-start"></a>开始之前需要了解的内容


通过使用 App-v 部署 Office 2013 之前，请查看以下计划信息。

### <a href="" id="bkmk-supp-vers-coexist"></a>支持的 Office 版本和 Office 共存

使用下表获取有关受支持的 Office 版本的信息，以及有关运行版本更共存的 Office 的信息。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">要查看的信息</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="planning-for-using-app-v-with-office51.md#bkmk-office-vers-supp-appv" data-raw-source="[Planning for Using App-V with Office](planning-for-using-app-v-with-office51.md#bkmk-office-vers-supp-appv)">计划将 App-V 与 Office 结合使用</a></p></td>
<td align="left"><ul>
<li><p>支持的 Office 版本</p></li>
<li><p>支持的部署类型（例如，桌面、个人虚拟桌面基础结构（VDI）、共用 VDI）</p></li>
<li><p>Office 授权选项</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><a href="planning-for-using-app-v-with-office51.md#bkmk-plan-coexisting" data-raw-source="[Planning for Using App-V with Office](planning-for-using-app-v-with-office51.md#bkmk-plan-coexisting)">计划将 App-V 与 Office 结合使用</a></p></td>
<td align="left"><p>在同一台计算机上安装不同版本的 Office 时的注意事项</p></td>
</tr>
</tbody>
</table>


### <a href="" id="bkmk-pkg-pub-reqs"></a>打包、发布和部署要求

通过使用 App-v 部署 Office 之前，请查看以下要求。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">任务</th>
<th align="left">要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>包装</p></td>
<td align="left"><ul>
<li><p>要部署到用户的所有 Office 应用程序都必须位于单个程序包中。</p></li>
<li><p>在 app-v 5.1 和更高版本中，必须使用 Office 部署工具创建程序包。 不能使用 Sequencer。</p></li>
<li><p>如果要在 Office 中部署 Microsoft Visio 2013 和 Microsoft Project 2013，则必须将它们包含在与 Office 相同的程序包中。 有关详细信息，请参阅 <a href="#bkmk-deploy-visio-project" data-raw-source="[Deploying Visio 2013 and Project 2013 with Office](#bkmk-deploy-visio-project)"> 通过 Office 部署 Visio 2013 和 Project 2013 </a> 。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>发布</p></td>
<td align="left"><ul>
<li><p>您只能将一个 Office 程序包发布到每台客户端计算机。</p></li>
<li><p>您必须全局发布 Office 程序包。 您不能发布给用户。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>通过使用远程桌面服务将以下任何产品部署到共享计算机：</p>
<ul>
<li><p>适用于企业的 Microsoft 365 应用</p></li>
<li><p>Visio Pro for Office 365</p></li>
<li><p>Project Pro for Office 365</p></li>
</ul></td>
<td align="left"><p>您必须启用 <a href="https://technet.microsoft.com/library/dn782860.aspx" data-raw-source="[shared computer activation](https://technet.microsoft.com/library/dn782860.aspx)"> 共享计算机激活 </a> 。</p>
<p>如果你要部署批量许可产品，则不使用共享计算机激活，例如：</p>
<ul>
<li><p>Office 专业增强版2013</p></li>
<li><p>Visio Professional 2013</p></li>
<li><p>Project Professional 2013</p></li>
</ul></td>
</tr>
</tbody>
</table>



### 从程序包中排除 Office 应用程序

下表介绍了从程序包中排除特定 Office 应用程序的推荐方法。

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
<td align="left"><p>使用 <strong> </strong> Office 部署工具创建程序包时，请使用 ExcludeApp 设置。</p></td>
<td align="left"><ul>
<li><p>使你能够在 Office 部署工具创建程序包时从程序包中排除特定的 Office 应用程序。 例如，你可以使用此设置创建仅包含 Microsoft Word 的程序包。</p></li>
<li><p>有关详细信息，请参阅 <a href="https://technet.microsoft.com/library/jj219426.aspx#bkmk-excludeappelement" data-raw-source="[ExcludeApp element](https://technet.microsoft.com/library/jj219426.aspx#bkmk-excludeappelement)"> ExcludeApp 元素 </a> 。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>修改 DeploymentConfig.xml 文件</p></td>
<td align="left"><ul>
<li><p>创建程序包后修改 DeploymentConfig.xml 文件。 此文件包含运行 App-V 客户端的计算机上所有用户的默认程序包设置。</p></li>
<li><p>有关详细信息，请参阅 <a href="#bkmk-disable-office-apps" data-raw-source="[Disabling Office 2013 applications](#bkmk-disable-office-apps)"> 禁用 Office 2013 应用程序 </a> 。</p></li>
</ul></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-create-office-pkg"></a>使用 Office 部署工具为 App-v 创建 Office 2013 程序包


完成以下步骤，为 App-v 5.1 或更高版本创建 Office 2013 程序包。

**重要提示**  
在 app-v 5.1 和更高版本中，你必须使用 Office 部署工具来创建程序包。 不能使用 Sequencer 创建程序包。



### 查看使用 Office 部署工具的先决条件

安装 Office 部署工具的计算机必须具有：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必备</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>必备软件</p></td>
<td align="left"><p>.Net Framework 4</p></td>
</tr>
<tr class="even">
<td align="left"><p>支持的操作系统</p></td>
<td align="left"><ul>
<li><p>64位版本的 Windows 8 或更高版本</p></li>
<li><p>64位版本的 Windows 7</p></li>
</ul></td>
</tr>
</tbody>
</table>



**注意**  
在本主题中，术语 "Office 2013 App-v 程序包" 是指订阅许可和批量许可。



### 使用 Office 部署工具创建 Office 2013 App-v 程序包

使用 Office 部署工具创建 Office 2013 App-v 程序包。 以下说明介绍了如何使用批量许可或订阅授权创建 Office 2013 App-v 程序包。

在64位 Windows 计算机上创建 Office 2013 App-v 包。 创建后，Office 2013 App-v 包将在32位和64位 Windows 7、Windows 8.1 和 Windows 10 计算机上运行。

### 下载 Office 部署工具

Office 2013 App-v 程序包是使用 Office 部署工具创建的，该工具生成 Office 2013 App-v 包。 无法通过 App-v sequencer 创建或修改程序包。 要开始创建软件包，请执行以下操作：

1.  下载[Office 部署工具以进行即点](https://www.microsoft.com/download/details.aspx?id=36778)即用。

2.  运行 .exe 文件，并将其功能提取到所需位置。 若要使此过程更简单，您可以创建将保存功能的共享网络文件夹。

    示例： \\\\Server\\Office2013

3.  检查 setup.exe 和 configuration.xml 文件是否存在以及是否位于指定的位置。

### 下载 Office 2013 应用程序

下载 Office 部署工具后，您可以使用它来获取最新的 Office 2013 应用程序。 获取 Office 应用程序后，创建 Office 2013 App-v 包。

Office 部署工具中包含的 XML 文件指定产品详细信息，如所含语言和 Office 应用程序。

1.  **自定义示例 XML 配置文件：** 使用您使用 Office 部署工具下载的示例 XML 配置文件自定义 Office 应用程序：

    1.  在记事本或你喜爱的文本编辑器中打开示例 XML 文件。

    2.  示例 configuration.xml 文件打开并准备好进行编辑后，您可以指定产品、语言和保存 Office 2013 应用程序的路径。 下面是 configuration.xml 文件的基本示例：

        ```xml
        <Configuration>
           <Add SourcePath= ”\\Server\Office2013” OfficeClientEdition="32" >
            <Product ID="O365ProPlusRetail ">
              <Language ID="en-us" />
            </Product>
            <Product ID="VisioProRetail">
              <Language ID="en-us" />
            </Product>
          </Add>
        </Configuration>
        ```

        **注意**  
        配置 XML 是一个示例 XML 文件。 该文件包含注释掉的行。你可以 "取消注释" 这些行以自定义文件的其他设置。



~~~
    The above XML configuration file specifies that Office 2013 ProPlus 32-bit edition, including Visio ProPlus, will be downloaded in English to the \\\\server\\Office 2013, which is the location where Office applications will be saved to. Note that the Product ID of the applications will not affect the final licensing of Office. Office 2013 App-V packages with various licensing can be created from the same applications through specifying licensing in a later stage. The table below summarizes the customizable attributes and elements of XML file:

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">Input</th>
    <th align="left">Description</th>
    <th align="left">Example</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>Add element</p></td>
    <td align="left"><p>Specifies the products and languages to include in the package.</p></td>
    <td align="left"><p>N/A</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>OfficeClientEdition (attribute of Add element)</p></td>
    <td align="left"><p>Specifies the edition of Office 2013 product to use: 32-bit or 64-bit. The operation fails if <strong>OfficeClientEdition</strong> is not set to a valid value.</p></td>
    <td align="left"><p><strong>OfficeClientEdition</strong>=&quot;32&quot;</p>
    <p><strong>OfficeClientEdition</strong>=&quot;64&quot;</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Product element</p></td>
    <td align="left"><p>Specifies the application. Project 2013 and Visio 2013 must be specified here as an added product to be included in the applications.</p></td>
    <td align="left"><p><code>Product ID =&quot;O365ProPlusRetail &quot;</code></p>
    <p><code>Product ID =&quot;VisioProRetail&quot;</code></p>
    <p><code>Product ID =&quot;ProjectProRetail&quot;</code></p>
    <p><code>Product ID =&quot;ProPlusVolume&quot;</code></p>
    <p><code>Product ID =&quot;VisioProVolume&quot;</code></p>
    <p><code>Product ID = &quot;ProjectProVolume&quot;</code></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Language element</p></td>
    <td align="left"><p>Specifies the language supported in the applications</p></td>
    <td align="left"><p><code>Language ID=&quot;en-us&quot;</code></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Version (attribute of Add element)</p></td>
    <td align="left"><p>Optional. Specifies a build to use for the package</p>
    <p>Defaults to latest advertised build (as defined in v32.CAB at the Office source).</p></td>
    <td align="left"><p><code>15.1.2.3</code></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>SourcePath (attribute of Add element)</p></td>
    <td align="left"><p>Specifies the location in which the applications will be saved to.</p></td>
    <td align="left"><p><code>Sourcepath = &quot;\\Server\Office2013”</code></p></td>
    </tr>
    </tbody>
    </table>



    After editing the configuration.xml file to specify the desired product, languages, and also the location which the Office 2013 applications will be saved onto, you can save the configuration file, for example, as Customconfig.xml.
~~~

2. 将**应用程序下载到指定位置：** 使用提升的命令提示符和64位操作系统下载稍后将转换为 App-v 包的 Office 2013 应用程序。 下面是包含详细信息说明的示例命令：

   ``` syntax
   \\server\Office2013\setup.exe /download \\server\Office2013\Customconfig.xml
   ```

   在示例中：

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong>\server\Office2013</strong></p></td>
   <td align="left"><p>是包含 Office 部署工具和自定义 Configuration.xml 文件的网络共享位置 Customconfig.xml。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>Setup.exe</strong></p></td>
   <td align="left"><p>是 Office 部署工具。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>/download</strong></p></td>
   <td align="left"><p>下载在 customConfig.xml 文件中指定的 Office 2013 应用程序。 这些位可以在使用批量许可的 Office 2013 App-v 包中转换。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>\server\Office2013\Customconfig.xml</strong></p></td>
   <td align="left"><p>传递完成下载过程所需的 XML 配置文件，在本示例中 customconfig.xml。 使用 "下载" 命令后，应在配置 xml 文件中指定的位置找到 Office 应用程序，本例中为 \Server\Office2013。</p></td>
   </tr>
   </tbody>
   </table>



### 将 Office 应用程序转换为 App-v 包

通过 Office 部署工具下载 Office 2013 应用程序后，请使用 Office 部署工具将它们转换为 Office 2013 App-v 包。 完成与你的许可模型对应的步骤。

**需要执行的操作摘要：**

-   在64位 Windows 计算机上创建 Office 2013 App-v 包。 但是，该包将在32位和64位 Windows 7、Windows 8 和 Windows 10 计算机上运行。

-   使用 Office 部署工具为订阅授权包或批量许可证创建 Office App-v 程序包，然后修改 CustomConfig.xml 配置文件。

    下表汇总了您所使用的授权模型的 CustomConfig.xml 文件中需要输入的值。 表格后面的部分中的步骤将指定所需的确切条目。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">产品 ID</th>
<th align="left">批量许可</th>
<th align="left">订阅许可</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Office 2013</strong></p></td>
<td align="left"><p>ProPlusVolume</p></td>
<td align="left"><p>O365proplusretail 用作</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Office 2013 与 Visio 2013</strong></p></td>
<td align="left"><p>ProPlusVolume</p>
<p>VisioProVolume</p></td>
<td align="left"><p>O365proplusretail 用作</p>
<p>VisioProRetail</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Office 2013 与 Visio 2013 和 Project 2013</strong></p></td>
<td align="left"><p>ProPlusVolume</p>
<p>VisioProVolume</p>
<p>ProjectProVolume</p></td>
<td align="left"><p>O365proplusretail 用作</p>
<p>VisioProRetail</p>
<p>ProjectProRetail</p></td>
</tr>
</tbody>
</table>



**如何将 Office 应用程序转换为 App-v 包**

1. 在记事本中，重新打开 CustomConfig.xml 文件，然后对文件进行以下更改：

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">参数</th>
   <th align="left">将值更改为</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>SourcePath</p></td>
   <td align="left"><p>指向之前下载的 Office 应用程序。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>ProductID</p></td>
   <td align="left"><p>指定许可类型，如以下示例所示：</p>
   <ul>
   <li><p>订阅许可</p>
   <pre class="syntax" space="preserve"><code>&lt;Configuration&gt;
      &lt;Add SourcePath= &quot;\server\Office 2013&quot; OfficeClientEdition=&quot;32&quot; &gt;
       &lt;Product ID=&quot;O365ProPlusRetail&quot;&gt;
         &lt;Language ID=&quot;en-us&quot; /&gt;
       &lt;/Product&gt;
       &lt;Product ID=&quot;VisioProRetail&quot;&gt;
         &lt;Language ID=&quot;en-us&quot; /&gt;
       &lt;/Product&gt;
     &lt;/Add&gt;
   &lt;/Configuration&gt; </code></pre>
   <p>在此示例中，创建带有订阅授权的程序包的以下更改：</p>
   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong>SourcePath</strong></p></td>
   <td align="left"><p>路径，该路径已更改为指向之前下载的 Office 应用程序。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>产品 ID</strong></p></td>
   <td align="left"><p>for Office 已更改为 <code>O365ProPlusRetail</code> 。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>产品 ID</strong></p></td>
   <td align="left"><p>Visio 的已更改为 <code>VisioProRetail</code> 。</p></td>
   </tr>
   </tbody>
   </table>
   <p> </p>
   <p></p></li>
   <li><p>批量许可</p>
   <pre class="syntax" space="preserve"><code>&lt;Configuration&gt;
      &lt;Add SourcePath= &quot;\Server\Office2013&quot; OfficeClientEdition=&quot;32&quot; &gt;
       &lt;Product ID=&quot;ProPlusVolume&quot;&gt;
         &lt;Language ID=&quot;en-us&quot; /&gt;
       &lt;/Product&gt;
       &lt;Product ID=&quot;VisioProVolume&quot;&gt;
         &lt;Language ID=&quot;en-us&quot; /&gt;
       &lt;/Product&gt;
     &lt;/Add&gt;
   &lt;/Configuration&gt;</code></pre>
   <p>在此示例中，已进行以下更改：创建具有批量许可的程序包：</p>
   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong>SourcePath</strong></p></td>
   <td align="left"><p>路径，该路径已更改为指向之前下载的 Office 应用程序。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>产品 ID</strong></p></td>
   <td align="left"><p>for Office 已更改为 <code>ProPlusVolume</code> 。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>产品 ID</strong></p></td>
   <td align="left"><p>Visio 的已更改为 <code>VisioProVolume</code> 。</p></td>
   </tr>
   </tbody>
   </table>
   <p> </p>
   <p></p></li>
   </ul></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>ExcludeApp （可选）</p></td>
   <td align="left"><p>允许你指定不希望包含在 Office 部署工具创建的 App-v 程序包中的 Office 程序。 例如，您可以排除 Access 和 InfoPath。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>PACKAGEGUID （可选）</p></td>
   <td align="left"><p>默认情况下，Office 部署工具创建的所有 app-v 程序包共享相同的 App-v 包 ID。 你可以使用 PACKAGEGUID 为每个程序包指定不同的程序包 ID，从而允许你发布由 Office 部署工具创建的多个 App-v 程序包，并使用 App-v 服务器对其进行管理。</p>
   <p>使用此参数的一个示例是为不同用户创建不同的程序包。 例如，你可以为某些用户创建一个仅包含 Office 2013 的程序包，并使用 Office 2013 和 Visio 2013 为另一组用户创建另一个程序包。</p>
   <div class="alert">
   <strong>注意</strong><br/><p>即使你使用的是唯一的程序包 Id，你仍然可以将仅一个 App-v 包部署到单个设备。</p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



2. 使用/packager 命令可将 Office 应用程序转换为 Office 2013 App-v 包。

   例如：

   ``` syntax
   \\server\Office2013\setup.exe /packager \\server\Office2013\Customconfig.xml  \\server\share\Office2013AppV
   ```

   在示例中：

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong>\server\Office2013</strong></p></td>
   <td align="left"><p>是包含 Office 部署工具和自定义 Configuration.xml 文件的网络共享位置 Customconfig.xml。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>Setup.exe</strong></p></td>
   <td align="left"><p>是 Office 部署工具。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>/packager</strong></p></td>
   <td align="left"><p>按照 customConfig.xml 文件中的指定，创建具有批量许可的 Office 2013 App-v 程序包。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>\server\Office2013\Customconfig.xml</strong></p></td>
   <td align="left"><p>传递已针对打包阶段准备的配置 XML 文件（在本例中为 customConfig）。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>\server\share\Office 2013AppV</strong></p></td>
   <td align="left"><p>指定新创建的 Office App-v 包的位置。</p></td>
   </tr>
   </tbody>
   </table>



~~~
After you run the **/packager** command, the following folders appear up in the directory where you specified the package should be saved:

-   **App-V Packages** – contains an Office 2013 App-V package and two deployment configuration files.

-   **WorkingDir**

**Note**  
To troubleshoot any issues, see the log files in the %temp% directory (default).
~~~



3. 验证 Office 2013 App-v 程序包是否正常工作：

   1.  将你全局创建的 Office 2013 App-v 包发布到测试计算机，并验证是否显示 Office 2013 快捷方式。

   2.  启动一些 Office 2013 应用程序（如 Excel 或 Word），以确保程序包按预期工作。

## <a href="" id="bkmk-pub-pkg-office"></a>发布 app-v 5.1 的 Office 程序包


使用以下信息发布 Office 程序包。

### 用于发布 Office App-v 程序包的方法

使用用于任何其他程序包的相同方法部署 Office 2013 的 app-v 程序包：

-   System Center Configuration Manager

-   App-v 服务器

-   通过 PowerShell 命令独立运行

### 发布先决条件和要求

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">先决条件或要求</th>
<th align="left">详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>在 App-v 客户端上启用 PowerShell 脚本</p></td>
<td align="left"><p>若要发布 Office 2013 程序包，必须运行脚本。</p>
<p>默认情况下，在 App-v 客户端上禁用程序包脚本。 若要启用脚本，请运行以下 PowerShell 命令：</p>
<pre class="syntax" space="preserve"><code>Set-AppvClientConfiguration –EnablePackageScripts 1</code></pre></td>
</tr>
<tr class="even">
<td align="left"><p>全局发布 Office 2013 程序包</p></td>
<td align="left"><p>Office App-v 程序包中的扩展点需要在计算机级别安装。</p>
<p>当您在计算机级别发布时，不需要任何先决条件操作或可再发行组件，并且 Office 2013 程序包全局使其应用程序可以像本地安装的 Office 一样工作，从而消除了管理员自定义程序包的需要。</p></td>
</tr>
</tbody>
</table>



### 如何发布 Office 程序包

运行以下命令以在全球范围内发布 Office 程序包：

-   `Add-AppvClientPackage <Path_to_AppV_Package> | Publish-AppvClientPackage –global`

-   从 App-v Server 上的 Web 管理控制台中，你可以向一组计算机（而不是用户组）添加权限，以使程序包能够在相应组中全局发布到计算机。

## <a href="" id="bkmk-custmz-manage-office-pkgs"></a>自定义和管理 Office App-v 程序包


若要管理 Office App-v 程序包，请使用与任何其他程序包相同的操作，但有一些例外，如下部分所述。

-   [使用连接组启用 Office 插件](#bkmk-enable-office-plugins)

-   [禁用 Office 2013 应用程序](#bkmk-disable-office-apps)

-   [禁用 Office 2013 快捷方式](#bkmk-disable-shortcuts)

-   [管理 Office 2013 程序包升级](#bkmk-manage-office-pkg-upgrd)

-   [管理 Office 2013 许可升级](#bkmk-manage-office-lic-upgrd)

-   [通过 Office 部署 Visio 2013 和 Project 2013](#bkmk-deploy-visio-project)

### <a href="" id="bkmk-enable-office-plugins"></a>使用连接组启用 Office 插件

使用此部分中的步骤，通过 Office 程序包启用 Office 插件。 若要使用 Office 插件，必须使用 App-v Sequencer 创建单独的程序包，该程序包只包含插件。不能使用 Office 部署工具创建插件程序包。 然后，创建包含 Office 程序包和插件程序包的连接组，如以下步骤所述。

**为 Office App-v 程序包启用插件**

1.  通过 App-v Server、System Center Configuration Manager 或 PowerShell cmdlet 添加连接组。

2.  使用 app-v 5.1 Sequencer 对插件进行排序。 确保在用于对插件进行排序的计算机上安装了 Office 2013。 在序列化 Office 2013 插件时，建议使用排序计算机上的 Microsoft 365 应用 for enterprise （非虚拟）。

3.  创建包含所需插件的 app-v 5.1 程序包。

4.  通过 App-v server、System Center Configuration Manager 或 PowerShell cmdlet 添加连接组。

5.  将 Office 2013 App-v 包和已排序的插件包添加到你创建的连接组。

    **重要提示**  
    连接组中的程序包顺序决定了程序包内容的合并顺序。 在连接组描述符文件中，首先添加 Office 2013 App-v 包，然后添加插件 App-v 包。



6.  请确保将两个程序包都发布到目标计算机，并对该插件程序包进行全局发布，以匹配已发布的 Office 2013 App-v 程序包的全局设置。

7.  验证插件程序包的部署配置文件是否具有 Office 2013 App-v 程序包所具有的相同设置。

    由于 Office 2013 App-v 程序包与操作系统集成，因此插件程序包设置应匹配。 你可以搜索 "COM 模式" 的部署配置文件，并确保插件程序包的值设置为 "集成"，并且 "InProcessEnabled" 和 "OutOfProcessEnabled" 与你发布的 Office 2013 App-v 包的设置相匹配。

8.  打开部署配置文件，并将**对象**的值设置为 " **false**"。

9.  如果在排序后对部署配置文件进行了任何更改，请确保插件程序包已与文件一起发布。

10. 确保你创建的连接组已启用到你所需的计算机。 如果启用了连接组，在使用 Office 2013 App-v 包时，创建的连接组可能会 "挂起"。 如果出现这种情况，您必须重新启动才能成功启用连接组。

11. 成功发布这两个程序包并启用连接组后，启动目标 Office 2013 应用程序，并验证你发布并添加到连接组的插件是否按预期工作。

### <a href="" id="bkmk-disable-office-apps"></a>禁用 Office 2013 应用程序

你可能希望在 Office App-v 包中禁用特定应用程序。 例如，您可以禁用 Access，但仍可使用所有其他 Office 应用程序。 禁用应用程序时，最终用户将不再看到该应用程序的快捷方式。 不必重新对应用程序进行排序。 当你在发布 Office 2013 App-v 包后更改部署配置文件时，你将保存所做的更改，添加 Office 2013 App-v 程序包，然后使用新的部署配置文件重新发布它，以将新设置应用到 Office 2013 App-v 程序包应用程序。

**注意**  
若要在使用 Office 部署工具创建 App-v 包时排除特定的 Office 应用程序（例如，Access 和 InfoPath），请使用**ExcludeApp**设置。 有关详细信息，请参阅[configuration.xml 文件的即点即用参考](https://technet.microsoft.com/library/jj219426.aspx)。



**禁用 Office 2013 应用程序**

1.  使用文本编辑器（如**记事本**）打开部署配置文件，然后搜索 "应用程序"。

2.  搜索要禁用的 Office 应用程序，例如 Access 2013。

3.  将 "Enabled" 的值从 "true" 更改为 "false"。

4.  保存部署配置文件。

5.  将 Office 2013 App-v 包添加到新的部署配置文件。

    ```xml
    <Application Id="[{AppVPackageRoot)]\officefl5\INFOPATH.EXE" Enabled="true">
      <VisualElements>
        <Name>InfoPath Filler 2013</Name>
        <Icon />
        <Description />
      </VisualElements>
    </Application>
    <Application Id="[{AppVPackageRoot}]\office15\lync.exe" Enabled="true">
      <VisualElements>
        <Name>Lync 2013</Name>
        <Icon />
        <Description />
      </VisualElements>
    </Application>
    <Application Id="[(AppVPackageRoot}]\office15\MSACCESS.EXE" Enabled="true">
      <VisualElements>
        <Name>Access 2013</Name>
        <Icon />
        <Description />
      </VisualElements>
    </Application>
    ```

6.  重新添加 Office 2013 App-v 程序包，然后使用新的部署配置文件重新添加它，以将新设置应用于 Office 2013 App-v 程序包应用程序。

### <a href="" id="bkmk-disable-shortcuts"></a>禁用 Office 2013 快捷方式

你可能希望禁用某些 Office 应用程序的快捷方式，而不是取消发布或删除程序包。 以下示例显示了如何禁用 Microsoft Access 的快捷方式。

**禁用 Office 2013 应用程序的快捷方式**

1.  在记事本中打开部署配置文件，然后搜索 "快捷方式"。

2.  若要禁用某些快捷方式，请删除或注释掉不需要的特定快捷方式。 必须保持子系统存在且已启用。 例如，在下面的示例中，删除 Microsoft Access 快捷方式，让子系统 &lt; 快捷方式保持 &gt; &lt; 原样/shortcut， &gt; 以禁用 Microsoft Access 快捷方式。

    ``` syntax
    Shortcuts

    -->
     <Shortcuts Enabled="true">
      <Extensions>
        <Extension Category="AppV.Shortcut">
          <Shortcut>
           <File>[{Common Programs}]\Microsoft Office 2013\Access 2013.lnk</File>
           <Target>[{AppvPackageRoot}])office15\MSACCESS.EXE</Target>
           <Icon>[{Windows}]\Installer\{90150000-000F-0000-0000-000000FF1CE)\accicons.exe.Ø.ico</Icon>
           <Arguments />
           <WorkingDirectory />
           <AppuserModelId>Microsoft.Office.MSACCESS.EXE.15</AppUserModelId>
           <AppUserModelExcludeFromShowInNewInstall>true</AppUserModelExcludeFromShowInNewInstall>
           <Description>Build a professional app quickly to manage data.</Description>
           <ShowCommand>l</ShowCommand>
           <ApplicationId>[{AppVPackageRoot}]\office15\MSACCESS.EXE</ApplicationId>
        </Shortcut>
    ```

3.  保存部署配置文件。

4.  通过新的部署配置文件重新发布 Office 2013 App-v 程序包。

通过修改 app-v 程序包的部署配置（例如文件类型关联、虚拟文件系统等），可以更改许多其他设置。 有关如何使用部署配置文件更改 App-v 程序包设置的其他信息，请参阅本文档末尾的 "其他资源" 部分。

### <a href="" id="bkmk-manage-office-pkg-upgrd"></a>管理 Office 2013 程序包升级

若要升级 Office 2013 程序包，请使用 Office 部署工具。 若要升级以前部署的 Office 2013 程序包，请执行以下步骤。

**如何升级以前部署的 Office 2013 程序包**

1.  通过 Office 部署工具创建新的 Office 2013 程序包，该工具使用最新的 Office 2013 应用程序软件。 最新的 Office 2013 位始终可以通过创建 Office 2013 App-v 程序包的下载阶段获取。 新创建的 Office 2013 程序包将具有最新的更新和新的版本 ID。 使用 Office 部署工具创建的所有程序包都具有相同的沿袭。

    **注意**  
    Office App-V 程序包具有两个版本 Id：

    -   Office 2013 App-V 程序包版本 ID 在使用 Office 部署工具创建的所有程序包中都是唯一的。

    -   第二个 App-v 包版本 ID，例如，在 AppX 清单中，仅当存在新版本的 Office 时才会更改。 例如，如果有新的支持升级的 Office 2013 版本，并且通过 Office 部署工具创建了一个程序包以合并这些升级，则 X.x.x.x 版本 ID 将会更改，以反映 Office 版本本身是否已更改。 App-v 服务器将使用 X.x.x.x 版本 ID 来区分此程序包，并识别它是否包含以前发布的程序包的新升级，因此，将其发布为现有 Office 2013 程序包的升级。



2.  将新创建的 Office 2013 App-v 包全局发布到要应用新更新的计算机上。 由于新的程序包具有较旧的 Office 2013 App-v 程序包的沿袭，因此发布包含更新的新程序包将仅对旧程序包应用新的更改，因此速度将很快。

3.  将采用与任何全局发布的 App-v 程序包相同的方式应用升级。 由于应用程序可能正在使用，升级可能会延迟，直到重新启动计算机。

### <a href="" id="bkmk-manage-office-lic-upgrd"></a>管理 Office 2013 许可升级

如果新的 Office 2013 App-v 包的许可证与当前部署的 Office 2013 App-v 包不同。 例如，部署的 Office 2013 程序包是基于订阅的 Office 2013，而新的 Office 2013 程序包是基于批量许可的，请按照以下说明进行操作，以确保升级的流畅授权升级：

**如何升级 Office 2013 许可证**

1.  取消发布已部署的 Office 2013 订阅授权 App-v 程序包。

2.  删除未发布的 Office 2013 订阅许可证 App-v 包。

3.  重新启动计算机。

4.  添加新的 Office 2013 应用程序-V 程序包批量许可。

5.  通过批量许可发布添加的 Office 2013 App-v 程序包。

将成功部署使用所选授权的 Office 2013 App-v 程序包。

### <a href="" id="bkmk-deploy-visio-project"></a>通过 Office 部署 Visio 2013 和 Project 2013

下表介绍了通过 Office 部署 Visio 2013 和 Project 2013 的要求和选项。

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
<td align="left"><p>如何将 Visio 2013 和 Project 2013 打包并发布到 Office？</p></td>
<td align="left"><p>您必须在同一程序包中包含 Visio 2013 和 Project 2013 和 Office。</p>
<p>如果不部署 Office，则可以创建一个包含 Visio 和/或项目的程序包，前提是 <a href="../appv-v5/deploying-microsoft-office-2010-by-using-app-v.md" data-raw-source="[Deploying Microsoft Office 2010 by Using App-V](../appv-v5/deploying-microsoft-office-2010-by-using-app-v.md)"> 使用 App-v 部署 Microsoft Office 2010 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>如何将 Visio 2013 和 Project 2013 部署到特定用户？</p></td>
<td align="left"><p>使用以下方法之一：</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">如果需要 .。。</th>
<th align="left">...然后使用此方法</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>创建两个不同的程序包，并将每个程序包部署到不同组的用户</p></td>
<td align="left"><p>创建和部署以下程序包：</p>
<ul>
<li><p>仅包含 Office 部署到用户仅需要 Office 的计算机的程序包。</p></li>
<li><p>包含 Office、Visio 和 Project-部署到用户需要所有三个应用程序的计算机的程序包。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>如果您只需要整个组织的一个程序包，或者如果您有共享计算机的用户，请执行以下操作：</p></td>
<td align="left"><p>按照以下步骤操作：</p>
<ol>
<li><p>创建包含 Office、Visio 和 Project 的程序包。</p></li>
<li><p>将程序包部署到所有用户。</p></li>
<li><p>使用 <a href="https://technet.microsoft.com/library/dd723678.aspx" data-raw-source="[Microsoft AppLocker](https://technet.microsoft.com/library/dd723678.aspx)"> Microsoft AppLocker </a> 阻止特定用户使用 Visio 和 Project。</p></li>
</ol></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>



## 其他资源


**Office 2013 App-v 程序包其他资源**

[Office 部署工具，用于即点即用](https://go.microsoft.com/fwlink/p/?LinkID=330672)

[将 Microsoft Office 部署为顺序式 App-v 程序包所支持的方案](https://go.microsoft.com/fwlink/p/?LinkId=330680)

**Office 2010 应用程序-V 程序包**

[Microsoft Application Virtualization 5.0 的 microsoft Office 2010 排序包](https://go.microsoft.com/fwlink/p/?LinkId=330681)

[创建或使用 app-v 5.0 Office 2010 程序包时的已知问题](https://go.microsoft.com/fwlink/p/?LinkId=330682)

[如何在 Microsoft Application Virtualization 5.0 中对 Microsoft Office 2010 进行排序](https://go.microsoft.com/fwlink/p/?LinkId=330676)

**连接组**

[在 Microsoft App 中部署连接组-V v5](https://go.microsoft.com/fwlink/p/?LinkId=330683)

[管理连接组](managing-connection-groups51.md)

**动态配置**

[关于 App-V 5.1 动态配置](about-app-v-51-dynamic-configuration.md)














