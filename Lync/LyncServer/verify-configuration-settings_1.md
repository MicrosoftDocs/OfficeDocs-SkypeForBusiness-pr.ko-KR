---
title: 구성 설정 확인
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48183997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc4d13f3bdd5af1a2c9b90e190775522ea6f11b8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738568"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a><span data-ttu-id="14296-102">구성 설정 확인</span><span class="sxs-lookup"><span data-stu-id="14296-102">Verify configuration settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14296-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="14296-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="14296-104">토폴로지를 병합 하 고 **CsLegacyConfiguration** cmdlet을 실행 한 후에는 Office Communications Server 2007 R2 정책 및 설정을 Lync Server 2013로 가져왔는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="14296-104">After you merge the topology and run the **Import-CsLegacyConfiguration** cmdlet, verify that your Office Communications Server 2007 R2 policies and settings were imported to Lync Server 2013.</span></span> <span data-ttu-id="14296-105">다음 표에는 확인 해야 하는 정책 및 설정이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14296-105">The following table lists the policies and settings that you should verify.</span></span>

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a><span data-ttu-id="14296-106">마이그레이션 후 확인할 정책 및 설정</span><span class="sxs-lookup"><span data-stu-id="14296-106">Policies and Settings to Verify after Migration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="14296-107">이 작업을 사용 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="14296-107">If you use this workload:</span></span></th>
<th><span data-ttu-id="14296-108">다음 정책 및 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="14296-108">Verify these policies and settings:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14296-109">인스턴트 메시지 (IM) 및 회의</span><span class="sxs-lookup"><span data-stu-id="14296-109">Instant messaging (IM) and conferencing</span></span></p></td>
<td><p><span data-ttu-id="14296-110">현재 상태 정책</span><span class="sxs-lookup"><span data-stu-id="14296-110">Presence policy</span></span></p>
<p><span data-ttu-id="14296-111">회의 정책</span><span class="sxs-lookup"><span data-stu-id="14296-111">Conferencing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14296-112">전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="14296-112">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="14296-113">전화 접속 액세스 번호</span><span class="sxs-lookup"><span data-stu-id="14296-113">Dial-in access numbers</span></span></p>
<p><span data-ttu-id="14296-114">다이얼 플랜</span><span class="sxs-lookup"><span data-stu-id="14296-114">Dial plans</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14296-115">Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="14296-115">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="14296-116">음성 정책</span><span class="sxs-lookup"><span data-stu-id="14296-116">Voice policy</span></span></p>
<p><span data-ttu-id="14296-117">음성 경로</span><span class="sxs-lookup"><span data-stu-id="14296-117">Voice routes</span></span></p>
<p><span data-ttu-id="14296-118">다이얼 플랜</span><span class="sxs-lookup"><span data-stu-id="14296-118">Dial plans</span></span></p>
<p><span data-ttu-id="14296-119">PSTN 사용 설정</span><span class="sxs-lookup"><span data-stu-id="14296-119">PSTN usage settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14296-120">Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="14296-120">Communicator Web Access</span></span></p></td>
<td><p><span data-ttu-id="14296-121">단순 URL</span><span class="sxs-lookup"><span data-stu-id="14296-121">Simple URLs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14296-122">외부 사용자</span><span class="sxs-lookup"><span data-stu-id="14296-122">External users</span></span></p></td>
<td><p><span data-ttu-id="14296-123">외부 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="14296-123">External access policies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14296-124">보관</span><span class="sxs-lookup"><span data-stu-id="14296-124">Archiving</span></span></p></td>
<td><p><span data-ttu-id="14296-125">보관 정책</span><span class="sxs-lookup"><span data-stu-id="14296-125">Archiving policy</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-verify-policies-and-settings"></a><span data-ttu-id="14296-126">정책 및 설정을 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="14296-126">To verify policies and settings</span></span>

1.  <span data-ttu-id="14296-127">Office Communications Server 2007 R2 환경에서 다이얼 플랜 이름 (이전의 위치 프로필)을 기록 하 고, 전화 접속 액세스 번호 (회의 수행자 액세스 전화 번호 및 지역), 음성 경로 및 아래에 나열 된 정책을 확인 합니다. Communicator Web Access에 사용 되는 Url 외에도 앞의 표</span><span class="sxs-lookup"><span data-stu-id="14296-127">In your Office Communications Server 2007 R2 environment, make note of the names of dial plans (formerly known as location profiles), dial-in access numbers (Conferencing Attendant access phone numbers and regions), voice routes, and the policies listed in the preceding table, in addition to the URLs used for Communicator Web Access.</span></span>

2.  <span data-ttu-id="14296-128">Lync Server 2013 프런트 엔드 서버에서 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="14296-128">On the Lync Server 2013 Front End server, open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="14296-129">가져온 회의 정책을 확인 하려면 왼쪽 창에서 **회의**를 클릭 하 고 **회의 정책을**클릭 한 다음 Office Communications Server 2007 R2 환경의 모든 회의 정책이 목록에 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="14296-129">To verify imported conferencing policies, in the left pane, click **Conferencing**, click **Conferencing Policy**, and then verify that all the conferencing policies in your Office Communications Server 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="14296-130">이전 버전의 Office Communications Server의 <STRONG>모임</STRONG> 정책은 이제 Lync Server 2013의 회의 정책으로 알려져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14296-130">The <STRONG>Meeting</STRONG> policy from previous versions of Office Communications Server is now known as the conferencing policy in Lync Server 2013.</span></span> <span data-ttu-id="14296-131">또한 이전 버전의 Office Communications Server의 <STRONG>익명 Particpants</STRONG> 설정은 이제 Lync Server 2013 회의 정책에서 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14296-131">Additionally, the <STRONG>Anonymous Particpants</STRONG> setting from previous versions of Office Communications Server is now a setting in the Lync Server 2013 conferencing policy.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="14296-132">Office Communications Server 2007 R2에서 회의 정책이 <STRONG>사용자 당 사용</STRONG>으로 설정 되지 않은 경우 전역 정책 설정만 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="14296-132">In Office Communications Server 2007 R2, if the conferencing policy is not set to <STRONG>use per user</STRONG>, only global policy settings are imported.</span></span> <span data-ttu-id="14296-133">이 상황에서는 다른 회의 정책을 가져오지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14296-133">No other conference policies are imported in this situation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="14296-134"><STRONG>익명 참가자</STRONG> 가 Office Communications Server 2007 R2 회의 정책에서 <STRONG>사용자 당 적용</STRONG> 하도록 설정 된 경우 마이그레이션 중에 두 회의 정책이 생성 됩니다 ( <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> 가 <STRONG>True</STRONG> 로 설정 되 고 하나는 <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> <STRONG>False</STRONG>로 설정 된 경우).</span><span class="sxs-lookup"><span data-stu-id="14296-134">If <STRONG>Anonymous Participants</STRONG> is set to <STRONG>Enforce per user</STRONG> in your Office Communications Server 2007 R2 conferencing policy, two conferencing policies are created during migration: one with <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> set to <STRONG>True</STRONG> and one with <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> set to <STRONG>False</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="14296-135">가져온 다이얼 플랜을 확인 하려면 **음성 라우팅을**클릭 하 고 **다이얼 플랜**을 클릭 한 다음 Office Communicator 2007 R2 환경의 모든 다이얼 플랜이 목록에 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="14296-135">To verify imported dial plans, click **Voice Routing**, click **Dial Plan**, and then verify that all the dial plans in your Office Communicator 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="14296-136">Lync Server 2013에서 현재 <STRONG>위치 프로필</STRONG> 을 <STRONG>다이얼 플랜</STRONG>이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="14296-136">In Lync Server 2013, <STRONG>location profiles</STRONG> are now referred to as <STRONG>dial-plans</STRONG>.</span></span>

    
    </div>

5.  <span data-ttu-id="14296-137">가져온 음성 정책을 확인 하려면 **음성 라우팅을**클릭 하 고 **음성 정책을**클릭 한 다음 Office Communicator 2007 R2 환경의 모든 음성 정책이 목록에 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="14296-137">To verify imported voice policies, click **Voice Routing**, click **Voice Policy**, and then verify that all the voice policies in your Office Communicator 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="14296-138">Office Communications Server 2007 R2 환경에서 <STRONG>사용자 단위</STRONG> 에 대 한 음성 정책이 설정 되어 있지 않으면 글로벌 정책 설정만 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="14296-138">If voice policy is not set to <STRONG>use per user</STRONG> in your Office Communications Server 2007 R2 environment, only global policy settings are imported.</span></span> <span data-ttu-id="14296-139">다른 음성 정책은이 상황에서 가져오지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14296-139">No other voice policies are imported in this situation.</span></span>

    
    </div>

6.  <span data-ttu-id="14296-140">가져온 음성 경로를 확인 하려면 **음성 라우팅을**클릭 하 고 **경로**를 클릭 한 다음 Office Communicator 2007 R2 환경의 모든 음성 경로가 목록에 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="14296-140">To verify imported voice routes, click **Voice Routing**, click **Route**, and then verify that all the voice routes in your Office Communicator 2007 R2 environment are included in the list.</span></span>

7.  <span data-ttu-id="14296-141">가져온 PSTN 사용 설정을 확인 하려면 **음성 라우팅을**클릭 하 고 **PSTN 사용**을 클릭 한 다음 Office COMMUNICATOR 2007 R2 환경의 PSTN 사용 설정이 목록에 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="14296-141">To verify imported PSTN usage settings, click **Voice Routing**, click **PSTN Usage**, and then verify that the PSTN Usage settings from your Office Communicator 2007 R2 environment are included in the list.</span></span>

8.  <span data-ttu-id="14296-142">가져온 외부 액세스 정책을 확인 하려면 **페더레이션 및 외부 액세스**를 클릭 하 고 **외부 액세스 정책을**클릭 한 다음 Office Communicator 2007 R2 환경의 모든 외부 액세스 정책이 목록에 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="14296-142">To verify imported external access policies, click **Federation and External Access**, click **External Access Policy**, and then verify that all the external access policies in your Office Communicator 2007 R2 environment are included in the list.</span></span>

9.  <span data-ttu-id="14296-143">보관 정책을 확인 하려면 **모니터링 및 보관**을 클릭 하 고 **보관 정책을**클릭 한 다음 Office Communications Server 2007 R2 환경의 모든 보관 정책이 목록에 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="14296-143">To verify archiving policies, click **Monitoring and Archiving**, click **Archiving Policy**, and then verify that all the archiving policies in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

10. <span data-ttu-id="14296-144">Lync Server 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="14296-144">Open the Lync Server Management Shell.</span></span>

11. <span data-ttu-id="14296-145">현재 상태 정책을 확인 하려면 명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="14296-145">To verify presence policies, at the command line, type the following:</span></span>
    
        Get-CsPresencePolicy
    
    <span data-ttu-id="14296-146">**Id** 매개 변수에 있는 이름을 확인 하 여 Office Communications Server 2007 R2 환경의 현재 상태 정책을 모두 가져왔는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="14296-146">By looking at the name in the **Identity** parameter, verify that all the presence policies in your Office Communications Server 2007 R2 environment were imported.</span></span>

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a><span data-ttu-id="14296-147">Cmdlet을 사용 하 여 정책 및 설정을 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="14296-147">To verify policies and settings by using cmdlets</span></span>

1.  <span data-ttu-id="14296-148">Lync Server 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="14296-148">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="14296-149">다음 표에 나와 있는 cmdlet을 실행 하 여 정책과 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="14296-149">Run the cmdlets in the following table to verify policies and settings.</span></span>
    
    <span data-ttu-id="14296-150">이러한 cmdlet의 구문은 다음 예제와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="14296-150">The syntax of these cmdlets is like the following example:</span></span>
    
        Get-CsConferencingPolicy
    
    <span data-ttu-id="14296-151">이러한 cmdlet에 대 한 자세한 내용을 보려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="14296-151">For details about these cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="14296-152">이 정책 또는 설정에 대해 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="14296-152">For this policy or setting:</span></span></th>
<th><span data-ttu-id="14296-153">이 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="14296-153">Use this cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14296-154">현재 상태 정책</span><span class="sxs-lookup"><span data-stu-id="14296-154">Presence policy</span></span></p></td>
<td><p><span data-ttu-id="14296-155"><strong>Get-CsPresencePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="14296-155"><strong>Get-CsPresencePolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14296-156">회의 정책</span><span class="sxs-lookup"><span data-stu-id="14296-156">Conferencing policy</span></span></p></td>
<td><p><span data-ttu-id="14296-157"><strong>Get-CsConferencingPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="14296-157"><strong>Get-CsConferencingPolicy</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14296-158">전화 접속 액세스 번호</span><span class="sxs-lookup"><span data-stu-id="14296-158">Dial-in access numbers</span></span></p></td>
<td><p><span data-ttu-id="14296-159"><strong>Get-CsDialInConferencingAccessNumber</strong></span><span class="sxs-lookup"><span data-stu-id="14296-159"><strong>Get-CsDialInConferencingAccessNumber</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14296-160">다이얼 플랜</span><span class="sxs-lookup"><span data-stu-id="14296-160">Dial plans</span></span></p></td>
<td><p><span data-ttu-id="14296-161"><strong>가져오기-CsDialPlan 플랜</strong></span><span class="sxs-lookup"><span data-stu-id="14296-161"><strong>Get-CsDialPlan</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14296-162">음성 정책</span><span class="sxs-lookup"><span data-stu-id="14296-162">Voice policy</span></span></p></td>
<td><p><span data-ttu-id="14296-163"><strong>Get-CsVoicePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="14296-163"><strong>Get-CsVoicePolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14296-164">음성 경로</span><span class="sxs-lookup"><span data-stu-id="14296-164">Voice routes</span></span></p></td>
<td><p><span data-ttu-id="14296-165"><strong>Get-CsVoiceRoute</strong></span><span class="sxs-lookup"><span data-stu-id="14296-165"><strong>Get-CsVoiceRoute</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14296-166">PSTN 사용 현황</span><span class="sxs-lookup"><span data-stu-id="14296-166">PSTN Usage</span></span></p></td>
<td><p><span data-ttu-id="14296-167"><strong>다운로드-CsPstnUsage</strong></span><span class="sxs-lookup"><span data-stu-id="14296-167"><strong>Get-CsPstnUsage</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14296-168">Url</span><span class="sxs-lookup"><span data-stu-id="14296-168">URLs</span></span></p></td>
<td><p><span data-ttu-id="14296-169"><strong>Get-CsSimpleUrlConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="14296-169"><strong>Get-CsSimpleUrlConfiguration</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14296-170">외부 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="14296-170">External access policies</span></span></p></td>
<td><p><span data-ttu-id="14296-171"><strong>Get-CsExternalAccessPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="14296-171"><strong>Get-CsExternalAccessPolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14296-172">보관 정책</span><span class="sxs-lookup"><span data-stu-id="14296-172">Archiving policy</span></span></p></td>
<td><p><span data-ttu-id="14296-173"><strong>Get-CsArchivingPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="14296-173"><strong>Get-CsArchivingPolicy</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

