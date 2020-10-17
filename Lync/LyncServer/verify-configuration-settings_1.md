---
title: 구성 설정 확인
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48183997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e1ad498f25656e01507e55c41d98ff4bb9143b4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508415"
---
# <a name="verify-configuration-settings"></a><span data-ttu-id="3867f-102">구성 설정 확인</span><span class="sxs-lookup"><span data-stu-id="3867f-102">Verify configuration settings</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3867f-103">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="3867f-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="3867f-104">토폴로지를 병합 하 고 **import-cslegacyconfiguration** cmdlet을 실행 한 후에는 Office Communications Server 2007 R2 정책 및 설정을 Lync Server 2013로 가져왔는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3867f-104">After you merge the topology and run the **Import-CsLegacyConfiguration** cmdlet, verify that your Office Communications Server 2007 R2 policies and settings were imported to Lync Server 2013.</span></span> <span data-ttu-id="3867f-105">다음 표에서는 확인해야 하는 정책 및 설정을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="3867f-105">The following table lists the policies and settings that you should verify.</span></span>

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a><span data-ttu-id="3867f-106">마이그레이션 이후 확인할 정책 및 설정</span><span class="sxs-lookup"><span data-stu-id="3867f-106">Policies and Settings to Verify after Migration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3867f-107">이 작업을 사용하는 경우:</span><span class="sxs-lookup"><span data-stu-id="3867f-107">If you use this workload:</span></span></th>
<th><span data-ttu-id="3867f-108">정책 및 설정 확인:</span><span class="sxs-lookup"><span data-stu-id="3867f-108">Verify these policies and settings:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3867f-109">IM(인스턴트 메시징) 및 회의</span><span class="sxs-lookup"><span data-stu-id="3867f-109">Instant messaging (IM) and conferencing</span></span></p></td>
<td><p><span data-ttu-id="3867f-110">현재 상태 정책</span><span class="sxs-lookup"><span data-stu-id="3867f-110">Presence policy</span></span></p>
<p><span data-ttu-id="3867f-111">회의 정책</span><span class="sxs-lookup"><span data-stu-id="3867f-111">Conferencing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3867f-112">전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="3867f-112">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="3867f-113">전화 접속 액세스 번호</span><span class="sxs-lookup"><span data-stu-id="3867f-113">Dial-in access numbers</span></span></p>
<p><span data-ttu-id="3867f-114">다이얼 플랜</span><span class="sxs-lookup"><span data-stu-id="3867f-114">Dial plans</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3867f-115">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="3867f-115">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="3867f-116">음성 정책</span><span class="sxs-lookup"><span data-stu-id="3867f-116">Voice policy</span></span></p>
<p><span data-ttu-id="3867f-117">음성 경로</span><span class="sxs-lookup"><span data-stu-id="3867f-117">Voice routes</span></span></p>
<p><span data-ttu-id="3867f-118">다이얼 플랜</span><span class="sxs-lookup"><span data-stu-id="3867f-118">Dial plans</span></span></p>
<p><span data-ttu-id="3867f-119">PSTN 사용 설정</span><span class="sxs-lookup"><span data-stu-id="3867f-119">PSTN usage settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3867f-120">Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="3867f-120">Communicator Web Access</span></span></p></td>
<td><p><span data-ttu-id="3867f-121">단순 URL</span><span class="sxs-lookup"><span data-stu-id="3867f-121">Simple URLs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3867f-122">외부 사용자</span><span class="sxs-lookup"><span data-stu-id="3867f-122">External users</span></span></p></td>
<td><p><span data-ttu-id="3867f-123">외부 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="3867f-123">External access policies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3867f-124">보관</span><span class="sxs-lookup"><span data-stu-id="3867f-124">Archiving</span></span></p></td>
<td><p><span data-ttu-id="3867f-125">보관 정책</span><span class="sxs-lookup"><span data-stu-id="3867f-125">Archiving policy</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-verify-policies-and-settings"></a><span data-ttu-id="3867f-126">정책 및 설정을 확인하려면</span><span class="sxs-lookup"><span data-stu-id="3867f-126">To verify policies and settings</span></span>

1.  <span data-ttu-id="3867f-127">Office Communications Server 2007 R2 환경에서 다이얼 플랜의 이름 (이전에는 위치 프로필), 전화 접속 액세스 번호 (회의 수행자 액세스 전화 번호 및 지역), 음성 경로, Communicator Web Access에 사용 된 Url을 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="3867f-127">In your Office Communications Server 2007 R2 environment, make note of the names of dial plans (formerly known as location profiles), dial-in access numbers (Conferencing Attendant access phone numbers and regions), voice routes, and the policies listed in the preceding table, in addition to the URLs used for Communicator Web Access.</span></span>

2.  <span data-ttu-id="3867f-128">Lync Server 2013 프런트 엔드 서버에서 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3867f-128">On the Lync Server 2013 Front End server, open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="3867f-129">가져온 회의 정책을 확인 하려면 왼쪽 창에서 **회의**를 클릭 하 고 **회의 정책을**클릭 한 후에 Office Communications Server 2007 R2 환경의 모든 회의 정책이 목록에 포함 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3867f-129">To verify imported conferencing policies, in the left pane, click **Conferencing**, click **Conferencing Policy**, and then verify that all the conferencing policies in your Office Communications Server 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3867f-130">이전 버전의 Office Communications Server의 <STRONG>모임</STRONG> 정책은 이제 Lync Server 2013의 회의 정책 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3867f-130">The <STRONG>Meeting</STRONG> policy from previous versions of Office Communications Server is now known as the conferencing policy in Lync Server 2013.</span></span> <span data-ttu-id="3867f-131">또한 이전 버전의 Office Communications Server에서 <STRONG>익명 Particpants</STRONG> 설정은 이제 Lync Server 2013 회의 정책의 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="3867f-131">Additionally, the <STRONG>Anonymous Particpants</STRONG> setting from previous versions of Office Communications Server is now a setting in the Lync Server 2013 conferencing policy.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3867f-132">Office Communications Server 2007 r 2에서 회의 정책이 <STRONG>사용자 당 사용</STRONG>으로 설정 되어 있지 않으면 전역 정책 설정만 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3867f-132">In Office Communications Server 2007 R2, if the conferencing policy is not set to <STRONG>use per user</STRONG>, only global policy settings are imported.</span></span> <span data-ttu-id="3867f-133">이 경우에 다른 회의 정책은 가져오지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3867f-133">No other conference policies are imported in this situation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3867f-134"><STRONG>익명 참가자</STRONG> 가 Office Communications Server 2007 R2 회의 정책에서 <STRONG>사용자별</STRONG> 로 설정 된 경우 마이그레이션 중에 두 회의 정책이 만들어집니다 ( <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> 이 <STRONG>True</STRONG> 로 설정 되 고 1은 <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> 이 <STRONG>False</STRONG>로 설정 됨).</span><span class="sxs-lookup"><span data-stu-id="3867f-134">If <STRONG>Anonymous Participants</STRONG> is set to <STRONG>Enforce per user</STRONG> in your Office Communications Server 2007 R2 conferencing policy, two conferencing policies are created during migration: one with <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> set to <STRONG>True</STRONG> and one with <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> set to <STRONG>False</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="3867f-135">가져온 다이얼 플랜을 확인하려면 **음성 라우팅**, **다이얼 플랜**을 차례로 클릭한 후 Office Communicator 2007 R2 환경의 모든 다이얼 플랜이 목록에 포함되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3867f-135">To verify imported dial plans, click **Voice Routing**, click **Dial Plan**, and then verify that all the dial plans in your Office Communicator 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3867f-136">Lync Server 2013에서는 이제 <STRONG>위치 프로필</STRONG> 을 <STRONG>다이얼 플랜</STRONG>이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3867f-136">In Lync Server 2013, <STRONG>location profiles</STRONG> are now referred to as <STRONG>dial-plans</STRONG>.</span></span>

    
    </div>

5.  <span data-ttu-id="3867f-137">가져온 음성 정책을 확인하려면 **음성 라우팅**, **음성 정책**을 차례로 클릭한 후 Office Communicator 2007 R2 환경의 모든 음성 정책이 목록에 포함되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3867f-137">To verify imported voice policies, click **Voice Routing**, click **Voice Policy**, and then verify that all the voice policies in your Office Communicator 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3867f-138">음성 정책이 Office Communications Server 2007 R2 환경에서 <STRONG>사용자 단위로 사용</STRONG> 하도록 설정 되어 있지 않으면 글로벌 정책 설정만 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3867f-138">If voice policy is not set to <STRONG>use per user</STRONG> in your Office Communications Server 2007 R2 environment, only global policy settings are imported.</span></span> <span data-ttu-id="3867f-139">이 경우에 다른 음성 정책은 가져오지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3867f-139">No other voice policies are imported in this situation.</span></span>

    
    </div>

6.  <span data-ttu-id="3867f-140">가져온 음성 경로를 확인하려면 **음성 라우팅**, **경로**를 차례로 클릭한 후 Office Communicator 2007 R2 환경의 모든 음성 경로가 목록에 포함되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3867f-140">To verify imported voice routes, click **Voice Routing**, click **Route**, and then verify that all the voice routes in your Office Communicator 2007 R2 environment are included in the list.</span></span>

7.  <span data-ttu-id="3867f-141">가져온 PSTN 사용 설정을 확인하려면 **음성 라우팅**, **PSTN 사용**을 차례로 클릭한 후 Office Communicator 2007 R2 환경의 PSTN 사용 설정이 목록에 포함되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3867f-141">To verify imported PSTN usage settings, click **Voice Routing**, click **PSTN Usage**, and then verify that the PSTN Usage settings from your Office Communicator 2007 R2 environment are included in the list.</span></span>

8.  <span data-ttu-id="3867f-142">가져온 외부 액세스 정책을 확인하려면 **페더레이션 및 외부 액세스**, **외부 액세스 정책**을 차례로 클릭한 후 Office Communicator 2007 R2 환경의 모든 외부 액세스 정책이 목록에 포함되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3867f-142">To verify imported external access policies, click **Federation and External Access**, click **External Access Policy**, and then verify that all the external access policies in your Office Communicator 2007 R2 environment are included in the list.</span></span>

9.  <span data-ttu-id="3867f-143">보관 정책을 확인 하려면 **모니터링 및 보관**을 클릭 하 고 **보관 정책을**클릭 한 후에 Office Communications Server 2007 R2 환경의 모든 보관 정책이 목록에 포함 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3867f-143">To verify archiving policies, click **Monitoring and Archiving**, click **Archiving Policy**, and then verify that all the archiving policies in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

10. <span data-ttu-id="3867f-144">Lync Server 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3867f-144">Open the Lync Server Management Shell.</span></span>

11. <span data-ttu-id="3867f-145">현재 상태 정책을 확인하려면 명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3867f-145">To verify presence policies, at the command line, type the following:</span></span>
    
        Get-CsPresencePolicy
    
    <span data-ttu-id="3867f-146">**Identity** 매개 변수에 있는 이름을 살펴보면 Office Communications Server 2007 R2 환경의 모든 현재 상태 정책을 가져왔는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3867f-146">By looking at the name in the **Identity** parameter, verify that all the presence policies in your Office Communications Server 2007 R2 environment were imported.</span></span>

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a><span data-ttu-id="3867f-147">cmdlet을 사용하여 정책 및 설정을 확인하려면</span><span class="sxs-lookup"><span data-stu-id="3867f-147">To verify policies and settings by using cmdlets</span></span>

1.  <span data-ttu-id="3867f-148">Lync Server 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3867f-148">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="3867f-149">다음 표의 cmdlet을 실행하여 정책 및 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3867f-149">Run the cmdlets in the following table to verify policies and settings.</span></span>
    
    <span data-ttu-id="3867f-150">이러한 cmdlet의 구문은 다음 예와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3867f-150">The syntax of these cmdlets is like the following example:</span></span>
    
        Get-CsConferencingPolicy
    
    <span data-ttu-id="3867f-151">이러한 cmdlet에 대한 자세한 내용을 보려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3867f-151">For details about these cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3867f-152">이 정책 또는 설정에 대해:</span><span class="sxs-lookup"><span data-stu-id="3867f-152">For this policy or setting:</span></span></th>
<th><span data-ttu-id="3867f-153">이 cmdlet 사용:</span><span class="sxs-lookup"><span data-stu-id="3867f-153">Use this cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3867f-154">현재 상태 정책</span><span class="sxs-lookup"><span data-stu-id="3867f-154">Presence policy</span></span></p></td>
<td><p><span data-ttu-id="3867f-155"><strong>Get-cspresencepolicy</strong></span><span class="sxs-lookup"><span data-stu-id="3867f-155"><strong>Get-CsPresencePolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3867f-156">회의 정책</span><span class="sxs-lookup"><span data-stu-id="3867f-156">Conferencing policy</span></span></p></td>
<td><p><span data-ttu-id="3867f-157"><strong>Get-csconferencingpolicy</strong></span><span class="sxs-lookup"><span data-stu-id="3867f-157"><strong>Get-CsConferencingPolicy</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3867f-158">전화 접속 액세스 번호</span><span class="sxs-lookup"><span data-stu-id="3867f-158">Dial-in access numbers</span></span></p></td>
<td><p><span data-ttu-id="3867f-159"><strong>Get-csdialinconferencingaccessnumber</strong></span><span class="sxs-lookup"><span data-stu-id="3867f-159"><strong>Get-CsDialInConferencingAccessNumber</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3867f-160">다이얼 플랜</span><span class="sxs-lookup"><span data-stu-id="3867f-160">Dial plans</span></span></p></td>
<td><p><span data-ttu-id="3867f-161"><strong>Get-CsDialPlan 플랜</strong></span><span class="sxs-lookup"><span data-stu-id="3867f-161"><strong>Get-CsDialPlan</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3867f-162">음성 정책</span><span class="sxs-lookup"><span data-stu-id="3867f-162">Voice policy</span></span></p></td>
<td><p><span data-ttu-id="3867f-163"><strong>Set-csvoicepolicy</strong></span><span class="sxs-lookup"><span data-stu-id="3867f-163"><strong>Get-CsVoicePolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3867f-164">음성 경로</span><span class="sxs-lookup"><span data-stu-id="3867f-164">Voice routes</span></span></p></td>
<td><p><span data-ttu-id="3867f-165"><strong>Get-csvoiceroute</strong></span><span class="sxs-lookup"><span data-stu-id="3867f-165"><strong>Get-CsVoiceRoute</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3867f-166">PSTN 사용</span><span class="sxs-lookup"><span data-stu-id="3867f-166">PSTN Usage</span></span></p></td>
<td><p><span data-ttu-id="3867f-167"><strong>G-CsPstnUsage 사용</strong></span><span class="sxs-lookup"><span data-stu-id="3867f-167"><strong>Get-CsPstnUsage</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3867f-168">URL</span><span class="sxs-lookup"><span data-stu-id="3867f-168">URLs</span></span></p></td>
<td><p><span data-ttu-id="3867f-169"><strong>Get-cssimpleurlconfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="3867f-169"><strong>Get-CsSimpleUrlConfiguration</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3867f-170">외부 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="3867f-170">External access policies</span></span></p></td>
<td><p><span data-ttu-id="3867f-171"><strong>Get-csexternalaccesspolicy</strong></span><span class="sxs-lookup"><span data-stu-id="3867f-171"><strong>Get-CsExternalAccessPolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3867f-172">보관 정책</span><span class="sxs-lookup"><span data-stu-id="3867f-172">Archiving policy</span></span></p></td>
<td><p><span data-ttu-id="3867f-173"><strong>Grant-csarchivingpolicy</strong></span><span class="sxs-lookup"><span data-stu-id="3867f-173"><strong>Get-CsArchivingPolicy</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

