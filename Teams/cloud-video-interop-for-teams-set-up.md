---
title: Microsoft Teams용 Cloud Video Interop 설정
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
f1.keywords:
- NOCSH
description: 이 문서에서는 조직의 사용자를 위해 Cloud Video Interop을 계획하고 설정할 수 있는 방법을 설명합니다.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 64d790e775ac0d76de48a71de8d165656f2e6927
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102604"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a><span data-ttu-id="116cb-103">Microsoft Teams용 Cloud Video Interop 설정</span><span class="sxs-lookup"><span data-stu-id="116cb-103">Set up Cloud Video Interop for Microsoft Teams</span></span>

<span data-ttu-id="116cb-104">[Cloud Video Interop](cloud-video-interop.md)파트너를 선택한 후 배포를 계획하고, 프로비전 세부 정보 및 파트너 테넌트 키를 설정하고 조직의 비디오 인터프 앱에 동의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-104">After you have [chosen your Cloud Video Interop partner(s)](cloud-video-interop.md), you will need to plan your deployment, get set up with provisioning details and partner tenant key, and consent to the video interop app in your organization.</span></span> <span data-ttu-id="116cb-105">다음 다이어그램에서는 프로세스를 간략하게 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-105">The following diagram outlines the process.</span></span> 

![조직에서 CVI 배포](media/deploying-cvi.png)

## <a name="plan"></a><span data-ttu-id="116cb-107">계획</span><span class="sxs-lookup"><span data-stu-id="116cb-107">Plan</span></span>

<span data-ttu-id="116cb-108">조직에서 사용할 파트너 또는 파트너를 식별하는 데 대한 자세한 내용은 [Microsoft Teams용 Cloud Video Interop을](cloud-video-interop.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="116cb-108">See [Cloud Video Interop for Microsoft Teams](cloud-video-interop.md) for information about identifying a partner or partners to use in your organization.</span></span> 

<span data-ttu-id="116cb-109">사용자 기반/동시/사이트 전체 사용에 대해 계획하려면:</span><span class="sxs-lookup"><span data-stu-id="116cb-109">To plan for user based/concurrent/site wide enablement:</span></span> 

- <span data-ttu-id="116cb-110">사용에 대한 배포 모델/호스팅 모델 선택</span><span class="sxs-lookup"><span data-stu-id="116cb-110">Pick a deployment model/hosted model for your use</span></span>
- <span data-ttu-id="116cb-111">조직에 적합한 라이선스 계획을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-111">Select the license plan ideal for your organization.</span></span> 
- <span data-ttu-id="116cb-112">VM 용량 계획은 비디오 인프라를 호스팅하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-112">Plan for capacity of VMs is you are hosting your video infrastructure.</span></span>

## <a name="configure"></a><span data-ttu-id="116cb-113">구성</span><span class="sxs-lookup"><span data-stu-id="116cb-113">Configure</span></span> 

<span data-ttu-id="116cb-114">Cloud Video Interop을 구성하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-114">To configure Cloud Video Interop, follow these steps.</span></span> 

1. <span data-ttu-id="116cb-115">선택한 파트너/파트너(테넌트 키, appIds...)에서 구성 정보를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-115">Obtain configuration info from the partner/partners you have chosen (tenant key, appIds…).</span></span> <span data-ttu-id="116cb-116">조직에서 하나 이상의 비디오 인터프 파트너를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-116">You can use one or more video interop partners in your organization</span></span> 

2. <span data-ttu-id="116cb-117">네트워크가 올바르게 구성되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-117">Ensure that your network is configured correctly.</span></span> <span data-ttu-id="116cb-118">지원할 경계 네트워크 트래버스에 대한 표준 기반 비디오 방화벽을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-118">Configure your standards-based video firewall for perimeter network traversal to support.</span></span> <span data-ttu-id="116cb-119">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-119">For example:</span></span> 
    - <span data-ttu-id="116cb-120">Cisco VCS-e</span><span class="sxs-lookup"><span data-stu-id="116cb-120">Cisco VCS-e</span></span>                  
    - <span data-ttu-id="116cb-121">Polycom RPAD</span><span class="sxs-lookup"><span data-stu-id="116cb-121">Polycom RPAD</span></span>

3. <span data-ttu-id="116cb-122">Exchange 및 OTD를 통해 통합된 회의실을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-122">Configure integrated rooms with exchange and OTD.</span></span> <span data-ttu-id="116cb-123">대부분의 경우 환경에서 추가 릴레이를 설정하고 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-123">In most cases, additional relay would need to be set up and configured in your environment.</span></span>


## <a name="provision"></a><span data-ttu-id="116cb-124">프로비전</span><span class="sxs-lookup"><span data-stu-id="116cb-124">Provision</span></span>
 
<span data-ttu-id="116cb-125">테넌트 키는 파트너 서비스에 대한 전화 접속입니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-125">The tenant key will be the dial out to the partner service.</span></span> <span data-ttu-id="116cb-126">다음 예제에서는 813878896@t.plcm.vc 키입니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-126">In the following example, 813878896@t.plcm.vc is the tenant key.</span></span> 

![테넌트 키 예제](media/tenant-key-example.png) 

<span data-ttu-id="116cb-128">테넌트 키를 프로비전하려면 다음 cmdlet을 실행하고, 선택한 사용자 또는 조직 전체를 사용하여 비디오 인터팝 좌표를 사용하여 모임을 만들 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-128">You will need to execute the following cmdlets to provision the tenant key, and also enable select users or your whole organization to create meetings with video interop coordinates.</span></span>

 
- <span data-ttu-id="116cb-129">**[Get-CsTeamsVideoInteropServicepolicy](/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft는 클라우드 비디오 Interop에 사용할 파트너를 지정할 수 있도록 지원되는 각 파트너에 대해 미리 생성된 정책을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-129">**[Get-CsTeamsVideoInteropServicepolicy](/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft provides pre-constructed policies for each of our supported partners that allow you to designate which partner(s) to use for cloud video interop.</span></span>

    <span data-ttu-id="116cb-130">이 cmdlet을 사용하면 조직에서 사용할 수 있는 미리 생성된 정책을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-130">This cmdlet allows you to identify the pre-constructed policies that you can use in your organization.</span></span> <span data-ttu-id="116cb-131">cmdlet을 활용하는 하나 이상의 사용자에게 이 정책을 할당할 Grant-CsTeamsVideoInteropServicePolicy 있습니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-131">You can assign this policy to one or more of your users leveraging the Grant-CsTeamsVideoInteropServicePolicy cmdlet.</span></span>
 
- <span data-ttu-id="116cb-132">**[Grant-CsTeamsVideoInteropServicePolicy](/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** Grant-CsTeamsVideoInteropServicePolicy cmdlet을 사용하면 조직에서 사용할 미리 생성된 정책을 할당하거나 특정 사용자에게 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-132">**[Grant-CsTeamsVideoInteropServicePolicy](/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** The Grant-CsTeamsVideoInteropServicePolicy cmdlet allows you to assign a pre-constructed policy for use in your organization or assign the policy to specific users.</span></span>
 
- <span data-ttu-id="116cb-133">**[New-CsVideoInteropServiceProvider:](/powershell/module/skype/new-csvideointeropserviceprovider)** 조직에서 New-CsVideoInteropServiceProvider 지원되는 CVI 파트너에 대한 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-133">**[New-CsVideoInteropServiceProvider](/powershell/module/skype/new-csvideointeropserviceprovider):** Use the New-CsVideoInteropServiceProvider to specify information about a supported CVI partner your organization would like to use.</span></span>
 
- <span data-ttu-id="116cb-134">**[Set-CsVideoInteropServiceProvider:](/powershell/module/skype/set-csvideointeropserviceprovider)** 이 Set-CsVideoInteropServiceProvider 사용하여 조직에서 사용하는 지원되는 CVI 파트너에 대한 정보를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-134">**[Set-CsVideoInteropServiceProvider](/powershell/module/skype/set-csvideointeropserviceprovider):** Use the Set-CsVideoInteropServiceProvider to update information about a supported CVI partner your organization uses.</span></span>
 
- <span data-ttu-id="116cb-135">**[Get-CsVideoInteropServiceProvider](/powershell/module/skype/get-csvideointeropserviceprovider):** 조직 내에서 사용하도록 구성된 모든 공급자를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-135">**[Get-CsVideoInteropServiceProvider](/powershell/module/skype/get-csvideointeropserviceprovider):** Get all of the providers that have been configured for use within the organization.</span></span>
 
- <span data-ttu-id="116cb-136">**[Remove-CsVideoInteropServiceProvider:](/powershell/module/skype/remove-csvideointeropserviceprovider)** 더 Remove-CsVideoInteropServiceProvider 더 이상 사용하지 않습니다 공급자에 대한 모든 공급자 정보를 제거하려면 이 기능을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-136">**[Remove-CsVideoInteropServiceProvider](/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider to remove all provider information about a provider that your organization no longer uses.</span></span>  
 
## <a name="consent"></a><span data-ttu-id="116cb-137">동의</span><span class="sxs-lookup"><span data-stu-id="116cb-137">Consent</span></span>

<span data-ttu-id="116cb-138">파트너 서비스를 통해 조직 모임에 참가하려면 VTC(비디오 원격 회의 디바이스)에 대한 사용 권한 동의를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-138">You will need to provide permission consent for the video teleconferencing devices (VTCs) to join your organizations meetings via the partner service.</span></span> <span data-ttu-id="116cb-139">이 동의 링크는 파트너가 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-139">This consent link will also be provided by your partner.</span></span>  
 
<span data-ttu-id="116cb-140">이러한 단계가 완료되면 위의 권한 부여 cmdlet을 통해 개별적으로 사용하도록 설정된 사용자 또는 테넌트가 활성화된 경우 조직의 모든 사용자가 예약하는 모든 Teams 모임에서 VTC 좌표를 하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-140">When these steps are complete, the users who are individually enabled via the Grant cmdlet above, or all of the users in the organization if the tenant is enabled, will have VTC coordinates in all the Teams meetings that they schedule.</span></span> <span data-ttu-id="116cb-141">모든 VTC는 해당 좌표를 통해 이러한 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-141">Any VTC can join these meetings via those coordinates.</span></span>


|<span data-ttu-id="116cb-142">이름</span><span class="sxs-lookup"><span data-stu-id="116cb-142">Name</span></span>|<span data-ttu-id="116cb-143">애플리케이션 사용 권한 간략한 설명</span><span class="sxs-lookup"><span data-stu-id="116cb-143">Application Permission Short Description</span></span>| <span data-ttu-id="116cb-144">설명</span><span class="sxs-lookup"><span data-stu-id="116cb-144">Description</span></span>|
|--|--|---|
|<span data-ttu-id="116cb-145">Calls.JoinGroupCall.All</span><span class="sxs-lookup"><span data-stu-id="116cb-145">Calls.JoinGroupCall.All</span></span>|<span data-ttu-id="116cb-146">그룹 통화 및 모임에 앱으로 참가(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="116cb-146">Join Group Calls and Meetings as an app (preview)</span></span>|<span data-ttu-id="116cb-147">앱에서 로그인한 사용자 없이 조직에서 그룹 호출 및 예약된 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-147">Allows the app to join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="116cb-148">앱이 테넌트의 모임에 디렉터리 사용자의 권한과 조인됩니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-148">The app will be joined with the privileges of a directory user to meetings in your tenant.</span></span>|
|<span data-ttu-id="116cb-149">Calls.JoinGroupCallasGuest.All</span><span class="sxs-lookup"><span data-stu-id="116cb-149">Calls.JoinGroupCallasGuest.All</span></span>|<span data-ttu-id="116cb-150">게스트 사용자로 그룹 통화 및 모임 참가(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="116cb-150">Join Group Calls and Meetings as a guest user (preview)</span></span>|<span data-ttu-id="116cb-151">앱에서 로그인한 사용자 없이 조직에서 그룹 통화 및 예약된 모임에 익명으로 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-151">Allows the app to anonymously join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="116cb-152">앱이 테넌트의 모임에 게스트로 참가됩니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-152">The app will be joined as a guest to meetings in your tenant.</span></span>|
|<span data-ttu-id="116cb-153">Calls.AccessMedia.All</span><span class="sxs-lookup"><span data-stu-id="116cb-153">Calls.AccessMedia.All</span></span>|<span data-ttu-id="116cb-154">앱으로 통화에서 미디어 스트림에 액세스(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="116cb-154">Access media streams in a call as an app (preview)</span></span>|<span data-ttu-id="116cb-155">앱에서 로그인한 사용자 없이 통화에서 미디어 스트림에 직접 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-155">Allows the app to get direct access to media streams in a call, without a signed-in user.</span></span>|
|<span data-ttu-id="116cb-156">OnlineMeetings.Read.All</span><span class="sxs-lookup"><span data-stu-id="116cb-156">OnlineMeetings.Read.All</span></span>|<span data-ttu-id="116cb-157">온라인 모임 세부 정보 읽기(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="116cb-157">Read Online Meeting details (preview)</span></span>|<span data-ttu-id="116cb-158">앱에서 로그인한 사용자 없이 조직에서 온라인 모임 세부 정보를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-158">Allows the app to read Online Meeting details in your organization, without a signed-in user.</span></span>|

## <a name="schedule"></a><span data-ttu-id="116cb-159">일정</span><span class="sxs-lookup"><span data-stu-id="116cb-159">Schedule</span></span>

<span data-ttu-id="116cb-160">다음으로, 비디오 인터프 좌표를 통해 Teams 모임을 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-160">Next, schedule Teams meeting with video interop coordinates.</span></span> <span data-ttu-id="116cb-161">사용 가능한 사용자는 다음을 통해 팀 모임을 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-161">The enabled user can schedule teams meetings via:</span></span>
- [<span data-ttu-id="116cb-162">Outlook용 Teams 모임 추가 기능</span><span class="sxs-lookup"><span data-stu-id="116cb-162">Teams Meeting add-in for Outlook</span></span>](teams-add-in-for-outlook.md)
- <span data-ttu-id="116cb-163">Teams 클라이언트 데스크톱 및 모바일</span><span class="sxs-lookup"><span data-stu-id="116cb-163">Teams client desktop and mobile</span></span>


## <a name="join"></a><span data-ttu-id="116cb-164">조인</span><span class="sxs-lookup"><span data-stu-id="116cb-164">Join</span></span>

<span data-ttu-id="116cb-165">다음 방법으로 VTC 디바이스와 Teams 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-165">You can join Teams meetings with your VTC devices in the following ways:</span></span>
 
- <span data-ttu-id="116cb-166">IVR(대화형 음성 응답)</span><span class="sxs-lookup"><span data-stu-id="116cb-166">IVR (Interactive voice Response)</span></span>
    - <span data-ttu-id="116cb-167">파트너의 IVR에 전화 접속할 수 tenantkey@domain.</span><span class="sxs-lookup"><span data-stu-id="116cb-167">You can dial in to the partner's IVR using the tenantkey@domain.</span></span> 
    - <span data-ttu-id="116cb-168">파트너 IVR에 있는 경우 VTC conferenceId에 입력하라는 메시지가 표시됩니다. 그러면 Teams 모임에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-168">Once you are in the partner IVR, you will be prompted to enter the VTC conferenceId, which will then connect you to the Teams meeting.</span></span>
- <span data-ttu-id="116cb-169">직접 다이얼</span><span class="sxs-lookup"><span data-stu-id="116cb-169">Direct dial</span></span>
    - <span data-ttu-id="116cb-170">전체 테넌트키 문자열을 사용하여 직접 다이얼 기능을 사용하여 파트너의 IVR과 상호 작용하지 않고 Teams 모임에 직접 전화를 걸 수 있습니다. VTC ConferenceId@domain.</span><span class="sxs-lookup"><span data-stu-id="116cb-170">You can directly dial into the Teams meeting without interacting with the partner’s IVR by using the direct dial feature using the full string of tenantkey.VTC ConferenceId@domain.</span></span>
- <span data-ttu-id="116cb-171">원터치 다이얼</span><span class="sxs-lookup"><span data-stu-id="116cb-171">One-touch dial</span></span>
    - <span data-ttu-id="116cb-172">통합 Teams 룸이 있는 경우 파트너가 제공하는 원터치 다이얼 기능을 사용할 수 있습니다(다이얼 문자열을 입력할 필요 없이).</span><span class="sxs-lookup"><span data-stu-id="116cb-172">If you have an integrated Teams room, you can use the one-touch dial capabilities offered by your partner (without needing to type any dial string).</span></span>

<span data-ttu-id="116cb-173">마지막으로 오디오, 비디오 및 콘텐츠 공유를 사용하여 모임에서 Teams 사용자와 참여합니다.</span><span class="sxs-lookup"><span data-stu-id="116cb-173">Finally, engage with Teams users in your meetings using audio, video, and content sharing.</span></span>