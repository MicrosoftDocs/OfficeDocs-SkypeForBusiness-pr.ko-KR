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
ms.openlocfilehash: 37ed8be52827f56b14c52f1bddd950ab39883cdf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="319f0-102">Lync Server 2013에서 CDR 구성 설정 모음 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="319f0-102">Create or modify a collection of CDR configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="319f0-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="319f0-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="319f0-104">CDR (통화 정보 기록)를 사용 하면 피어 투 피어 인스턴트 메시지 세션, VoIP (Voice over 인터넷 프로토콜) 전화 통화, 회의 통화 등의 사용 현황을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-104">Call detail recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls.</span></span> <span data-ttu-id="319f0-105">이 사용 현황 데이터에는 누가 누구에 게, 그들이 통화 되었는지, 그리고 그에 얼마나 오랜 시간에 대 한 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-105">This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="319f0-106">Microsoft Lync Server 2013을 설치할 때 CDR 구성 설정의 단일 전역 컬렉션이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-106">When you install Microsoft Lync Server 2013 a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="319f0-107">또한 관리자는 사이트 범위에서 사용자 지정 설정을 만드는 옵션도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-107">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="319f0-108">이러한 사이트 범위 설정이 사용 될 때마다 전역 설정 보다 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-108">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="319f0-109">예를 들어 Redmond 사이트에 대 한 사이트 범위 설정을 만드는 경우 전역 설정이 아닌 해당 설정이 Redmond에서 CDR를 관리 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-109">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage CDR in Redmond.</span></span>

<span data-ttu-id="319f0-110">Lync Server 제어판 또는 [New CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet 중 하나를 사용 하 여 CDR 구성 설정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-110">You can create CDR configuration settings by using either Lync Server Control Panel or the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet.</span></span> <span data-ttu-id="319f0-111">Lync Server 제어판 또는 [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet을 사용 하 여 기존 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-111">You can use Lync Server Control Panel or the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet to modify existing settings.</span></span> <span data-ttu-id="319f0-112">Lync Server 제어판을 사용 하 여 설정을 만들거나 수정 하는 경우 다음 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-112">If you are using Lync Server Control Panel to create or modify settings, the following options will be available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="319f0-113">UI 설정</span><span class="sxs-lookup"><span data-stu-id="319f0-113">UI Setting</span></span></th>
<th><span data-ttu-id="319f0-114">PowerShell 매개 변수</span><span class="sxs-lookup"><span data-stu-id="319f0-114">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="319f0-115">설명</span><span class="sxs-lookup"><span data-stu-id="319f0-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="319f0-116">이름</span><span class="sxs-lookup"><span data-stu-id="319f0-116">Name</span></span></p></td>
<td><p><span data-ttu-id="319f0-117">Identity</span><span class="sxs-lookup"><span data-stu-id="319f0-117">Identity</span></span></p></td>
<td><p><span data-ttu-id="319f0-118">생성 되는 CDR 구성 설정의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-118">Unique identifier for the CDR configuration settings being created.</span></span> <span data-ttu-id="319f0-119">이러한 설정은 사이트 범위 에서만 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-119">These settings can only be created at the site scope.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="319f0-120">CDRs의 모니터링 사용</span><span class="sxs-lookup"><span data-stu-id="319f0-120">Enable monitoring of CDRs</span></span></p></td>
<td><p><span data-ttu-id="319f0-121">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="319f0-121">EnableCDR</span></span></p></td>
<td><p><span data-ttu-id="319f0-122">CDR를 사용할 수 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-122">Indicates whether or not CDR is enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="319f0-123">CDRs를 제거 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="319f0-123">Enable purging of CDRs</span></span></p></td>
<td><p><span data-ttu-id="319f0-124">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="319f0-124">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="319f0-125">Cdr 레코드가 CDR 데이터베이스에서 정기적으로 삭제 되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-125">Indicates whether or not CDR records will periodically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="319f0-126">최대 기간 (일) 동안 CDRs 유지</span><span class="sxs-lookup"><span data-stu-id="319f0-126">Keep CDRs for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="319f0-127">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="319f0-127">KeepCallDetailForDays</span></span></p></td>
<td><p><span data-ttu-id="319f0-128">Cdr 레코드가 CDR 데이터베이스에 유지 되는 일 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-128">Indicates the number of days that CDR records will be kept in the CDR database.</span></span> <span data-ttu-id="319f0-129">지정 된 일 수 보다 오래 된 레코드는 자동으로 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-129">Any records older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="319f0-130">(제거는 제거를 사용 하는 경우에만 사용할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="319f0-130">(Note that purging will take only place if purging has been enabled.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="319f0-131">최대 기간 동안 오류 보고서 데이터 유지 (일)</span><span class="sxs-lookup"><span data-stu-id="319f0-131">Keep error report data for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="319f0-132">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="319f0-132">KeepErrorReportForDays</span></span></p></td>
<td><p><span data-ttu-id="319f0-133">CDR 오류 보고서가 유지 되는 일 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-133">Indicates the number of days that CDR error reports are kept.</span></span> <span data-ttu-id="319f0-134">지정 된 일 수 보다 오래 된 보고서는 자동으로 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-134">Any reports older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="319f0-135">CDR 오류 보고서는 클라이언트 응용 프로그램에서 업로드 하는 진단 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-135">CDR error reports are diagnostic reports uploaded by client applications.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="319f0-136">새로운 CsCdrConfiguration 및 CsCdrConfiguration cmdlet에는 Lync Server 제어판에서 사용할 수 없는 추가 옵션이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-136">The New-CsCdrConfiguration and Set-CsCdrConfiguration cmdlets include additional options not available in Lync Server Control Panel.</span></span> <span data-ttu-id="319f0-137">자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">CsCdrConfiguration</A> 및 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Set-CsCdrConfiguration</A> 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="319f0-137">See the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</A> and the <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Set-CsCdrConfiguration</A> help topics for more information.</span></span>



</div>

<div>

## <a name="to-create-cdr-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="319f0-138">Lync Server 제어판을 사용 하 여 CDR 구성 설정을 만들려면</span><span class="sxs-lookup"><span data-stu-id="319f0-138">To create CDR configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="319f0-139">Lync Server 제어판에서 **모니터링 및 보관**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-139">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="319f0-140">**통화 정보 기록** 탭에서 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-140">On the **Call Detail Recording** tab, click **New**.</span></span>

3.  <span data-ttu-id="319f0-141">**사이트 선택** 대화 상자에서 새 구성 설정을 만들 사이트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-141">In the **Select a Site** dialog box, select the site where the new configuration settings are to be created.</span></span> <span data-ttu-id="319f0-142">대화 상자가 비어 있으면 모든 사이트에 CDR 구성 설정 컬렉션이 이미 할당 되었음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-142">If the dialog box is empty, that means all of your sites have already been assigned a collection of CDR configuration settings.</span></span> <span data-ttu-id="319f0-143">각 사이트는 해당 컬렉션 하나로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-143">Each site is limited to a single such collection.</span></span> <span data-ttu-id="319f0-144">이 경우 설정을 삭제 하 고 다시 만들거나 기존 설정을 수정 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-144">In that case you can either delete and then re-create the settings, or simply modify the existing settings.</span></span>

4.  <span data-ttu-id="319f0-145">**새 CDR (통화 정보 기록) 설정** 대화 상자에서 원하는 항목을 선택한 다음 **커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-145">In the **New Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-existing-cdr-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="319f0-146">Lync Server 제어판을 사용 하 여 기존 CDR 구성 설정을 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="319f0-146">To modify existing CDR configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="319f0-147">Lync Server 제어판에서 **모니터링 및 보관**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-147">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="319f0-148">수정할 설정 모음을 두 번 클릭 하거나 모음을 선택 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-148">Double-click the collection of settings to be modified, or select the collection, click **Edit**, and then click **Show Details**.</span></span> <span data-ttu-id="319f0-149">한 번에 하나의 컬렉션만 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-149">Note that you can only modify a single collection at a time.</span></span> <span data-ttu-id="319f0-150">여러 컬렉션을 동일 하 게 변경 하려면 Lync Server 관리 셸을 대신 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-150">To make the same changes to multiple collections, use the Lync Server Management Shell instead.</span></span>

3.  <span data-ttu-id="319f0-151">**CDR (통화 정보 기록 편집) 설정** 대화 상자에서 원하는 항목을 선택한 다음 **커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-151">In the **Edit Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>

</div>

<div>

## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="319f0-152">Windows PowerShell Cmdlet을 사용 하 여 CDR 구성 설정 만들기</span><span class="sxs-lookup"><span data-stu-id="319f0-152">Creating CDR Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="319f0-153">Windows PowerShell 및 **새 CsCdrConfiguration** cmdlet을 사용 하 여 CDR 구성 설정을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-153">You can create CDR configuration settings can also be created by using Windows PowerShell and the **New-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="319f0-154">Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-154">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="319f0-155">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="319f0-155">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="319f0-156">CDR 구성 설정의 새 컬렉션을 만들려면</span><span class="sxs-lookup"><span data-stu-id="319f0-156">To create a new collection of CDR configuration settings</span></span>

  - <span data-ttu-id="319f0-157">이 명령은 Redmond 사이트에 적용 되는 새 CDR 구성 설정 모음을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-157">This command creates a new collection of CDR configuration settings applied to the Redmond site:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="319f0-158">통화 정보 기록을 사용 하지 않도록 설정 하는 CDR 구성 설정 모음을 만들려면</span><span class="sxs-lookup"><span data-stu-id="319f0-158">To create a collection of CDR configuration settings that disable call detail recording</span></span>

  - <span data-ttu-id="319f0-159">앞의 명령에서 필수 Id 매개 변수 이외의 매개 변수를 지정 하지 않았으므로 새 구성 설정 모음에는 해당 속성에 대 한 기본값이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-159">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> <span data-ttu-id="319f0-160">다른 속성 값을 사용 하는 설정을 만들려면 간단히 적절 한 매개 변수와 매개 변수 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-160">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="319f0-161">예를 들어 기본적으로 통화 정보를 사용 하지 않도록 설정 허용에 대 한 컬렉션을 만들려면 다음과 같은 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-161">For example, to create a collection of Call Detail configuration settings that, by default, allow disable Call Detail recording use a command like this:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="319f0-162">CDR 구성 설정의 새 컬렉션을 만들 때 여러 속성 값을 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="319f0-162">To specify multiple property values when creating a new collection of CDR configuration settings</span></span>

  - <span data-ttu-id="319f0-163">여러 매개 변수를 포함 하 여 여러 속성 값을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-163">You can modify multiple property values by including multiple parameters.</span></span> <span data-ttu-id="319f0-164">예를 들어이 명령은 90 일간 30 일간 오류 보고서에 대 한 통화 세부 정보 기록을 유지 하도록 새로운 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="319f0-164">For example, this command configures the new settings to keep Call Detail records for 30 days and error reports for 90 days:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

</div>

<span data-ttu-id="319f0-165">자세한 내용은 [새 CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="319f0-165">For more information, see the help topic for the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

