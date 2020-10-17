---
title: 'Lync Server 2013: CDR 구성 설정 모음 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of CDR configuration settings
ms:assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721878(v=OCS.15)
ms:contentKeyID: 49733812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 582df13f3bcd7c1d25e8bf15ce1534992ba6aeeb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514795"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="d14b2-102">Lync Server 2013에서 CDR 구성 설정 모음 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="d14b2-102">Create or modify a collection of CDR configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d14b2-103">_**마지막으로 수정 된 항목:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d14b2-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d14b2-p101">CDR(통화 정보 기록)을 사용하면 피어 투 피어 메신저 대화 세션, VoIP(Voice over Internet Protocol) 전화 통화, 전화 회의 통화 등의 사용 현황을 추적할 수 있습니다. 이러한 사용 내역 데이터에는 누가 누구에게 전화를 걸었는지, 언제 전화를 걸었는지 및 얼마나 오래 통화했는지에 대한 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d14b2-p101">Call detail recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="d14b2-106">Microsoft Lync Server 2013를 설치할 때 CDR 구성 설정에 대 한 단일 전역 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d14b2-106">When you install Microsoft Lync Server 2013 a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="d14b2-107">관리자에게는 또한 사이트 범위에서 사용자 지정 설정을 만드는 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d14b2-107">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="d14b2-108">이러한 사이트 범위의 설정은 사용될 때마다 전역 설정보다 높은 우선 순위를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="d14b2-108">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="d14b2-109">예를 들어 레드몬드 사이트에 사이트 범위의 설정을 만들면 전역 설정이 아닌 해당 설정이 레드몬드의 CDR 관리에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d14b2-109">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage CDR in Redmond.</span></span>

<span data-ttu-id="d14b2-110">Lync Server 제어판 또는 [get-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet을 사용 하 여 CDR 구성 설정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14b2-110">You can create CDR configuration settings by using either Lync Server Control Panel or the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet.</span></span> <span data-ttu-id="d14b2-111">Lync Server 제어판 또는 [get-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet을 사용 하 여 기존 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14b2-111">You can use Lync Server Control Panel or the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet to modify existing settings.</span></span> <span data-ttu-id="d14b2-112">Lync Server 제어판을 사용 하 여 설정을 만들거나 수정 하는 경우에는 다음 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14b2-112">If you are using Lync Server Control Panel to create or modify settings, the following options will be available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d14b2-113">UI 설정</span><span class="sxs-lookup"><span data-stu-id="d14b2-113">UI Setting</span></span></th>
<th><span data-ttu-id="d14b2-114">PowerShell 매개 변수</span><span class="sxs-lookup"><span data-stu-id="d14b2-114">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="d14b2-115">설명</span><span class="sxs-lookup"><span data-stu-id="d14b2-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d14b2-116">이름</span><span class="sxs-lookup"><span data-stu-id="d14b2-116">Name</span></span></p></td>
<td><p><span data-ttu-id="d14b2-117">ID</span><span class="sxs-lookup"><span data-stu-id="d14b2-117">Identity</span></span></p></td>
<td><p><span data-ttu-id="d14b2-p104">CDR 구성 설정에 대한 고유 ID가 만들어집니다. 이러한 설정은 사이트 범위에서만 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14b2-p104">Unique identifier for the CDR configuration settings being created. These settings can only be created at the site scope.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d14b2-120">CDR 모니터링 사용</span><span class="sxs-lookup"><span data-stu-id="d14b2-120">Enable monitoring of CDRs</span></span></p></td>
<td><p><span data-ttu-id="d14b2-121">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="d14b2-121">EnableCDR</span></span></p></td>
<td><p><span data-ttu-id="d14b2-122">CDR을 사용할 수 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d14b2-122">Indicates whether or not CDR is enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d14b2-123">CDR 삭제 사용</span><span class="sxs-lookup"><span data-stu-id="d14b2-123">Enable purging of CDRs</span></span></p></td>
<td><p><span data-ttu-id="d14b2-124">은 enablepurging 설정한</span><span class="sxs-lookup"><span data-stu-id="d14b2-124">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="d14b2-125">CDR을 CDR 데이터베이스에서 주기적으로 삭제할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d14b2-125">Indicates whether or not CDR records will periodically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d14b2-126">최대 기간(일) 동안 CDR 유지</span><span class="sxs-lookup"><span data-stu-id="d14b2-126">Keep CDRs for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="d14b2-127">Keepcalldetailfordays는</span><span class="sxs-lookup"><span data-stu-id="d14b2-127">KeepCallDetailForDays</span></span></p></td>
<td><p><span data-ttu-id="d14b2-p105">CDR 기록을 CDR 데이터베이스에 유지할 일 수를 나타냅니다. 지정된 일 수보다 오래된 기록은 모두 자동으로 삭제됩니다. 삭제는 삭제를 사용하도록 설정한 경우에만 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d14b2-p105">Indicates the number of days that CDR records will be kept in the CDR database. Any records older than the specified number of days will automatically be deleted. (Note that purging will take only place if purging has been enabled.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d14b2-131">최대 기간(일) 동안 오류 보고서 데이터 유지</span><span class="sxs-lookup"><span data-stu-id="d14b2-131">Keep error report data for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="d14b2-132">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="d14b2-132">KeepErrorReportForDays</span></span></p></td>
<td><p><span data-ttu-id="d14b2-p106">CDR 오류 보고서를 유지할 일 수를 나타냅니다. 지정된 일 수보다 오래된 보고서는 모두 자동으로 삭제됩니다. CDR 오류 보고서는 클라이언트 응용 프로그램에서 업로드하는 진단 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="d14b2-p106">Indicates the number of days that CDR error reports are kept. Any reports older than the specified number of days will automatically be deleted. CDR error reports are diagnostic reports uploaded by client applications.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="d14b2-136">New-CsCdrConfiguration 및 Set-CsCdrConfiguration cmdlet에는 Lync Server 제어판에서 사용할 수 없는 추가 옵션이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14b2-136">The New-CsCdrConfiguration and Set-CsCdrConfiguration cmdlets include additional options not available in Lync Server Control Panel.</span></span> <span data-ttu-id="d14b2-137">자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">get-cscdrconfiguration</A> 및 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">get-cscdrconfiguration</A> 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d14b2-137">See the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</A> and the <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Set-CsCdrConfiguration</A> help topics for more information.</span></span>



</div>

<div>

## <a name="to-create-cdr-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="d14b2-138">Lync Server 제어판을 사용 하 여 CDR 구성 설정을 만들려면</span><span class="sxs-lookup"><span data-stu-id="d14b2-138">To create CDR configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d14b2-139">Lync Server 제어판에서 **모니터링 및 보관**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d14b2-139">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="d14b2-140">**통화 정보 기록** 탭에서 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d14b2-140">On the **Call Detail Recording** tab, click **New**.</span></span>

3.  <span data-ttu-id="d14b2-p108">**사이트 선택** 대화 상자에서 새 구성 설정을 만들 사이트를 선택합니다. 대화 상자가 빈 상태이면 이미 사이트가 모두 CDR 구성 설정 컬렉션에 할당되었다는 의미입니다. 각 사이트는 단일 CDR 컬렉션으로 제한됩니다. 따라서 설정을 삭제한 후 다시 만들거나, 간단히 기존 설정을 수정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d14b2-p108">In the **Select a Site** dialog box, select the site where the new configuration settings are to be created. If the dialog box is empty, that means all of your sites have already been assigned a collection of CDR configuration settings. Each site is limited to a single such collection. In that case you can either delete and then re-create the settings, or simply modify the existing settings.</span></span>

4.  <span data-ttu-id="d14b2-145">**새 통화 정보 기록 설정 만들기** 대화 상자에서 원하는 항목을 선택한 다음 **커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d14b2-145">In the **New Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-existing-cdr-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="d14b2-146">Lync Server 제어판을 사용 하 여 기존 CDR 구성 설정을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="d14b2-146">To modify existing CDR configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="d14b2-147">Lync Server 제어판에서 **모니터링 및 보관**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d14b2-147">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="d14b2-148">수정할 설정 컬렉션을 두 번 클릭하거나 컬렉션을 선택하고 **편집**을 클릭한 다음 **자세한 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d14b2-148">Double-click the collection of settings to be modified, or select the collection, click **Edit**, and then click **Show Details**.</span></span> <span data-ttu-id="d14b2-149">한 번에 한 컬렉션만 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14b2-149">Note that you can only modify a single collection at a time.</span></span> <span data-ttu-id="d14b2-150">여러 컬렉션을 동일 하 게 변경 하려면 Lync Server 관리 셸을 대신 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d14b2-150">To make the same changes to multiple collections, use the Lync Server Management Shell instead.</span></span>

3.  <span data-ttu-id="d14b2-151">**통화 정보 기록 설정 편집** 대화 상자에서 원하는 항목을 선택한 다음 **커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d14b2-151">In the **Edit Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>

</div>

<div>

## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d14b2-152">Windows PowerShell Cmdlet을 사용 하 여 CDR 구성 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="d14b2-152">Creating CDR Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d14b2-153">또한 Windows PowerShell 및 **get-cscdrconfiguration** cmdlet을 사용 하 여 CDR 구성 설정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14b2-153">You can create CDR configuration settings can also be created by using Windows PowerShell and the **New-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="d14b2-154">Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14b2-154">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d14b2-155">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.</span><span class="sxs-lookup"><span data-stu-id="d14b2-155">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="d14b2-156">새 CDR 구성 설정 컬렉션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="d14b2-156">To create a new collection of CDR configuration settings</span></span>

  - <span data-ttu-id="d14b2-157">다음 명령을 실행하면 레드몬드 사이트에 적용되는 새 CDR 구성 설정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14b2-157">This command creates a new collection of CDR configuration settings applied to the Redmond site:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="d14b2-158">CDR(통화 정보 기록)을 사용하지 않도록 설정하는 CDR 구성 설정 컬렉션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="d14b2-158">To create a collection of CDR configuration settings that disable call detail recording</span></span>

  - <span data-ttu-id="d14b2-p111">이전 명령에서 필수 Identity 매개 변수를 제외하고는 지정된 매개 변수가 없으므로 새 구성 설정 컬렉션에는 모든 속성의 기본값이 사용됩니다. 다른 속성 값을 사용하는 설정을 만들려면 간단히 적합한 매개 변수와 매개 변수 값을 포함하면 됩니다. 예를 들어 CDR(통화 정보 기록)을 기본적으로 사용하지 않도록 설정하는 CDR 구성 설정 컬렉션을 만들려면 다음과 같은 명령을 실행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d14b2-p111">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of Call Detail configuration settings that, by default, allow disable Call Detail recording use a command like this:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="d14b2-162">새 CDR 구성 설정 컬렉션을 만들 때 여러 속성 값을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="d14b2-162">To specify multiple property values when creating a new collection of CDR configuration settings</span></span>

  - <span data-ttu-id="d14b2-p112">여러 매개 변수를 포함하여 여러 속성 값을 수정할 수 있습니다. 예를 들어 다음 명령을 실행하면 CDR(통화 정보 기록)을 30일 동안, 오류 보고서를 90일 동안 보관하는 새 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d14b2-p112">You can modify multiple property values by including multiple parameters. For example, this command configures the new settings to keep Call Detail records for 30 days and error reports for 90 days:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

</div>

<span data-ttu-id="d14b2-165">자세한 내용은 [get-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet에 대 한 도움말 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d14b2-165">For more information, see the help topic for the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

