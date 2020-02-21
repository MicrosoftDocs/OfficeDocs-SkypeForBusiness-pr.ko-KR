---
title: 'Lync Server 2013: Config.xml을 사용 하 여 설치 작업 수행'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Config.xml to perform installation tasks
ms:assetid: 0813184a-ab40-417c-b3a3-c2090766b831
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204651(v=OCS.15)
ms:contentKeyID: 48183332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2933da3fc52cc6a5c23f74806ff3a4e81dcb2ba
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-configxml-to-perform-installation-tasks-in-lync-server-2013"></a><span data-ttu-id="2347b-102">Config.xml을 사용 하 여 Lync Server 2013에서 설치 작업 수행</span><span class="sxs-lookup"><span data-stu-id="2347b-102">Using Config.xml to perform installation tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2347b-103">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="2347b-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="2347b-p101">사용자 지정 설치에는 기본적으로 OCT(Office 사용자 지정 도구)가 사용되기는 하지만, 관리자는 Config.xml 파일을 사용하여 OCT에서 사용할 수 없는 추가 설치 지침을 지정할 수 있습니다. Config.xml 파일을 통해서만 수행할 수 있는 사용자 지정 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2347b-p101">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT. The following customizations can only be made by using the Config.xml file:</span></span>

  - <span data-ttu-id="2347b-106">네트워크 설치 지점 경로 지정</span><span class="sxs-lookup"><span data-stu-id="2347b-106">Specify the path of the network installation point.</span></span>

  - <span data-ttu-id="2347b-107">설치할 제품 선택</span><span class="sxs-lookup"><span data-stu-id="2347b-107">Select the products to install.</span></span>

  - <span data-ttu-id="2347b-108">설치 사용자 지정 파일 및 소프트웨어 업데이트의 위치와 로깅 구성</span><span class="sxs-lookup"><span data-stu-id="2347b-108">Configure logging and the location of the Setup customization file and software updates.</span></span>

  - <span data-ttu-id="2347b-109">사용자 이름 등의 설치 옵션 지정</span><span class="sxs-lookup"><span data-stu-id="2347b-109">Specify installation options, such as user name.</span></span>

  - <span data-ttu-id="2347b-110">Office를 설치하지 않고 사용자 컴퓨터에 LIS(로컬 설치 원본) 복사</span><span class="sxs-lookup"><span data-stu-id="2347b-110">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>

  - <span data-ttu-id="2347b-111">설치에서 언어 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="2347b-111">Add or remove languages from the installation.</span></span>

<span data-ttu-id="2347b-112">Config.xml 파일을 사용 하 여 Lync 2013 자동 설치를 구성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2347b-112">We recommend that you use the Config.xml file to configure Lync 2013 silent installation.</span></span>

<span data-ttu-id="2347b-113">기본적으로 핵심 제품 폴더에 저장 된 Config.xml 파일 (예: \\product) WW) 설치 프로그램에 해당 제품을 설치 하도록 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2347b-113">By default, the Config.xml file that is stored in the core product folder (for example, \\product.WW) directs Setup to install that product.</span></span> <span data-ttu-id="2347b-114">예를 들어 다음 폴더의 Config.xml 파일은 Lync 2013을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2347b-114">For example, the Config.xml file in the following folder installs Lync 2013:</span></span>

  - <span data-ttu-id="2347b-115">\\\\서버\\공유\\lync15.admx가\\ \\</span><span class="sxs-lookup"><span data-stu-id="2347b-115">\\\\server\\share\\Lync15\\Lync.WW \\Config.xml</span></span>

<span data-ttu-id="2347b-116">Lync 2013 설치에 가장 일반적으로 사용 되는 Config.xml 요소는 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2347b-116">The Config.xml elements most commonly used for Lync 2013 installation are listed in the following table.</span></span>

### <a name="configxml-elements"></a><span data-ttu-id="2347b-117">Config.xml 요소</span><span class="sxs-lookup"><span data-stu-id="2347b-117">Config.xml elements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2347b-118">요소</span><span class="sxs-lookup"><span data-stu-id="2347b-118">Element</span></span></th>
<th><span data-ttu-id="2347b-119">설명</span><span class="sxs-lookup"><span data-stu-id="2347b-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2347b-120">구성</span><span class="sxs-lookup"><span data-stu-id="2347b-120">Configuration</span></span></p></td>
<td><p><span data-ttu-id="2347b-p103">최상위 요소(필수)입니다. Product=Lync 등의 Product 특성을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2347b-p103">Top-level element (required). Contains the Product attribute, for example: Product=Lync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2347b-123">OptionState</span><span class="sxs-lookup"><span data-stu-id="2347b-123">OptionState</span></span></p></td>
<td><p><span data-ttu-id="2347b-124">특정 제품 기능이 설치 중에 처리되는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2347b-124">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="2347b-125">다음 특성을 사용 하 여 Outlook 2010을 방해 하는 공유 구성 요소를 포함 하는 Business Connectivity Services의 설치를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="2347b-125">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook 2010:</span></span></p>
<ul>
<li><p><span data-ttu-id="2347b-126">Id =&quot;주 번호&quot;</span><span class="sxs-lookup"><span data-stu-id="2347b-126">Id=&quot;LOBiMain&quot;</span></span></p></li>
<li><p><span data-ttu-id="2347b-127">State =&quot;없음&quot;</span><span class="sxs-lookup"><span data-stu-id="2347b-127">State=&quot;Absent&quot;</span></span></p></li>
<li><p><span data-ttu-id="2347b-128">Children =&quot;Force&quot;</span><span class="sxs-lookup"><span data-stu-id="2347b-128">Children=&quot;Force&quot;</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2347b-129">디스플레이</span><span class="sxs-lookup"><span data-stu-id="2347b-129">Display</span></span></p></td>
<td><p><span data-ttu-id="2347b-p105">설치 프로그램에서 사용자에게 표시하는 UI의 수준입니다. 일반적인 특성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2347b-p105">The level of UI that Setup displays to the user. Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2347b-132">고 지 사항&quot;=&quot; | &quot;예&quot;아니요 (기본값)</span><span class="sxs-lookup"><span data-stu-id="2347b-132">CompletionNotice=&quot;Yes&quot; | &quot;No&quot;(default)</span></span></p></li>
<li><p><span data-ttu-id="2347b-133">AcceptEula =&quot;Yes&quot; | &quot;No&quot;(기본값)</span><span class="sxs-lookup"><span data-stu-id="2347b-133">AcceptEula=&quot;Yes&quot; | &quot;No&quot;(default)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2347b-134">기록을</span><span class="sxs-lookup"><span data-stu-id="2347b-134">Logging</span></span></p></td>
<td><p><span data-ttu-id="2347b-p106">설치 프로그램이 수행하는 로깅 종류에 대한 옵션입니다. 일반적인 특성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2347b-p106">Options for the kind of logging that Setup performs. Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2347b-137">Type =&quot;Off&quot; | &quot;Standard&quot;(기본값) | &quot;자세한 정보 표시&quot;</span><span class="sxs-lookup"><span data-stu-id="2347b-137">Type =&quot;Off&quot; | &quot;Standard&quot;(default) | &quot;Verbose&quot;</span></span></p></li>
<li><p><span data-ttu-id="2347b-138">Template=”파일 이름.txt”(로그 파일의 이름)</span><span class="sxs-lookup"><span data-stu-id="2347b-138">Template=”filename.txt” (the name of the log file)</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2347b-139">설정</span><span class="sxs-lookup"><span data-stu-id="2347b-139">Setting</span></span></p></td>
<td><p><span data-ttu-id="2347b-p107">Windows Installer 속성의 값을 지정합니다. 일반적인 특성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2347b-p107">Specifies values for Windows Installer properties. Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2347b-142">설정 Id =&quot;이름&quot; (Windows Installer 속성의 이름)</span><span class="sxs-lookup"><span data-stu-id="2347b-142">Setting Id=&quot;name&quot; (the name of the Windows Installer property)</span></span></p></li>
<li><p><span data-ttu-id="2347b-143">Value =&quot;value&quot; (속성에 할당할 값)</span><span class="sxs-lookup"><span data-stu-id="2347b-143">Value=&quot;value&quot; (the value to assign to the property)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2347b-144">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="2347b-144">DistributionPoint</span></span></p></td>
<td><p><span data-ttu-id="2347b-p108">설치를 실행할 네트워크 설치 지점의 정규화된 경로입니다. Location 특성을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2347b-p108">The fully qualified path of the network installation point from which the installation is to run. Includes the Location attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="2347b-147">Location = "path"</span><span class="sxs-lookup"><span data-stu-id="2347b-147">Location=”path”</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2347b-148">다음 예제에서는 Lync 2013의 일반적인 자동 설치를 위한 Config.xml 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2347b-148">The following example shows a Config.xml file for a typical silent installation of Lync 2013.</span></span>

    <Configuration Product="Lync">
      <OptionState Id="LOBiMain" State="Absent" Children="Force" />
      <Display Level="None" CompletionNotice="No" AcceptEula="Yes" />
      <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
      <Setting Id="SETUP_REBOOT" Value="Never" />
      <DistributionPoint Location="\\server\share\Lync15" />
    </Configuration>

<span data-ttu-id="2347b-149">Config.xml 파일을 사용 하 여 Office 설치 및 유지 관리 작업을 수행 하는 방법에 대 <https://go.microsoft.com/fwlink/p/?linkid=267514>한 자세한 내용은를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2347b-149">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at <https://go.microsoft.com/fwlink/p/?linkid=267514>.</span></span>

<div>

## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="2347b-150">Config.xml 파일을 사용자 지정하려면</span><span class="sxs-lookup"><span data-stu-id="2347b-150">To customize the Config.xml file</span></span>

1.  <span data-ttu-id="2347b-151">메모장과 같은 텍스트 편집기 도구를 사용하여 Config.xml 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2347b-151">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>

2.  <span data-ttu-id="2347b-152">변경할 요소가 포함된 줄을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="2347b-152">Locate the lines that contain the elements you want to change.</span></span>

3.  <span data-ttu-id="2347b-153">요소 항목을 사용하려는 자동 옵션으로 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="2347b-153">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="2347b-154">주석 구분 기호 "\<\!--" 및 "--\>"를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2347b-154">Make sure that you remove the comment delimiters, "\<\!--" and "--\>".</span></span> <span data-ttu-id="2347b-155">예를 들어 다음과 같은 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2347b-155">For example, use the following syntax:</span></span>
    
        < DistributionPoint Location="\\server\share\Lync15" />

4.  <span data-ttu-id="2347b-156">Config.xml 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="2347b-156">Save the Config.xml file.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

