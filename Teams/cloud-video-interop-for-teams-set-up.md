---
title: Microsoft 팀을 위한 클라우드 비디오 Interop 설정
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
description: 이 문서에서는 조직의 사용자를 위해 클라우드 비디오 Interop를 계획 하 고 설정 하는 방법에 대해 설명 합니다.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e91b0e25a7844634577083b26d74a48c788bc45b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237055"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a><span data-ttu-id="756bd-103">Microsoft 팀을 위한 클라우드 비디오 Interop 설정</span><span class="sxs-lookup"><span data-stu-id="756bd-103">Set up Cloud Video Interop for Microsoft Teams</span></span>

<span data-ttu-id="756bd-104">[클라우드 비디오 Interop 파트너를 선택한](cloud-video-interop.md)후에는 배포를 계획 하 고, 프로 비전 세부 정보 및 파트너 테 넌 트 키를 사용 하 여 설정 하 고, 조직의 비디오 Interop 앱에 동의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-104">After you have [chosen on your Cloud Video Interop partner(s)](cloud-video-interop.md), you will need to plan your deployment, get set up with provisioning details and partner tenant key, and consent to the video interop app in your organization.</span></span> <span data-ttu-id="756bd-105">다음 다이어그램은 프로세스를 대략적으로 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-105">The following diagram outlines the process.</span></span> 

![조직에 CVI 배포](media/deploying-cvi.png)

## <a name="plan"></a><span data-ttu-id="756bd-107">계획</span><span class="sxs-lookup"><span data-stu-id="756bd-107">Plan</span></span>

<span data-ttu-id="756bd-108">조직에서 사용할 파트너 또는 파트너를 식별 하는 방법에 대 한 자세한 내용은 [Microsoft 팀의 클라우드 비디오 Interop](cloud-video-interop.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="756bd-108">See [Cloud Video Interop for Microsoft Teams](cloud-video-interop.md) for information about identifying a partner or partners to use in your organization.</span></span> 

<span data-ttu-id="756bd-109">사용자 기반/동시/사이트 전체 사용을 계획 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-109">To plan for user based/concurrent/site wide enablement:</span></span> 

- <span data-ttu-id="756bd-110">사용할 배포 모델/호스팅 모델 선택</span><span class="sxs-lookup"><span data-stu-id="756bd-110">Pick a deployment model/hosted model for your use</span></span>
- <span data-ttu-id="756bd-111">조직에 가장 적합 한 라이선스 계획을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-111">Select the license plan ideal for your organization.</span></span> 
- <span data-ttu-id="756bd-112">Vm 용량에 대 한 계획은 비디오 인프라를 호스트 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-112">Plan for capacity of VMs is you are hosting your video infrastructure.</span></span>

## <a name="configure"></a><span data-ttu-id="756bd-113">구성할</span><span class="sxs-lookup"><span data-stu-id="756bd-113">Configure</span></span> 

<span data-ttu-id="756bd-114">클라우드 비디오 Interop를 구성 하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-114">To configure Cloud Video Interop, follow these steps.</span></span> 

1. <span data-ttu-id="756bd-115">선택한 파트너/파트너 (테 넌 트 키, appIds)에서 구성 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-115">Obtain configuration info from the partner/partners you have chosen (tenant key, appIds…).</span></span> <span data-ttu-id="756bd-116">조직에서 하나 이상의 비디오 interop 파트너를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-116">You can use one or more video interop partners in your organization</span></span> 

2. <span data-ttu-id="756bd-117">네트워크가 올바르게 구성 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-117">Ensure that your network is configured correctly.</span></span> <span data-ttu-id="756bd-118">경계 네트워크 순회 지원에 맞게 표준 기반 비디오 방화벽을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-118">Configure your standards-based video firewall for perimeter network traversal to support.</span></span> <span data-ttu-id="756bd-119">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-119">For example:</span></span> 
    - <span data-ttu-id="756bd-120">Cisco VCS-e</span><span class="sxs-lookup"><span data-stu-id="756bd-120">Cisco VCS-e</span></span>                  
    - <span data-ttu-id="756bd-121">Polycom RPAD</span><span class="sxs-lookup"><span data-stu-id="756bd-121">Polycom RPAD</span></span>

3. <span data-ttu-id="756bd-122">Exchange 및 기타 d를 사용 하 여 통합 채팅방을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-122">Configure integrated rooms with exchange and OTD.</span></span> <span data-ttu-id="756bd-123">대부분의 경우에는 환경에서 추가 릴레이가 설정 및 구성 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-123">In most cases, additional relay would need to be set up and configured in your environment.</span></span>


## <a name="provision"></a><span data-ttu-id="756bd-124">공급</span><span class="sxs-lookup"><span data-stu-id="756bd-124">Provision</span></span>
 
<span data-ttu-id="756bd-125">테 넌 트 키는 파트너 서비스에 대 한 전화 접속으로 보내집니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-125">The tenant key will be the dial out to the partner service.</span></span> <span data-ttu-id="756bd-126">다음 예제에서 813878896@t.plcm.vc는 테 넌 트 키입니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-126">In the following example, 813878896@t.plcm.vc is the tenant key.</span></span> 

![테 넌 트 키 예제](media/tenant-key-example.png) 

<span data-ttu-id="756bd-128">테 넌 트 키를 프로 비전 하려면 다음 cmdlet을 실행 해야 하며 사용자 또는 전체 조직을 선택 하 여 비디오 interop 좌표가 있는 모임을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-128">You will need to execute the following cmdlets to provision the tenant key, and also enable select users or your whole organization to create meetings with video interop coordinates.</span></span>

 
- <span data-ttu-id="756bd-129">\*\* [Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):\*\* Microsoft는 지원 되는 각 파트너에 대해 미리 구성 된 정책을 제공 하 여 클라우드 비디오 interop에 사용할 파트너를 지정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-129">**[Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft provides pre-constructed policies for each of our supported partners that allow you to designate which partner(s) to use for cloud video interop.</span></span>

    <span data-ttu-id="756bd-130">이 cmdlet을 사용 하 여 조직에서 사용할 수 있는 미리 구성 된 정책을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-130">This cmdlet allows you to identify the pre-constructed policies that you can use in your organization.</span></span> <span data-ttu-id="756bd-131">CsTeamsVideoInteropServicePolicy cmdlet을 활용 하는 하나 이상의 사용자에 게이 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-131">You can assign this policy to one or more of your users leveraging the Grant-CsTeamsVideoInteropServicePolicy cmdlet.</span></span>
 
- <span data-ttu-id="756bd-132">\*\* [허가-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):\*\* CsTeamsVideoInteropServicePolicy cmdlet을 사용 하 여 조직에서 사용할 미리 생성 된 정책을 할당 하거나 특정 사용자에 게 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-132">**[Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** The Grant-CsTeamsVideoInteropServicePolicy cmdlet allows you to assign a pre-constructed policy for use in your organization or assign the policy to specific users.</span></span>
 
- <span data-ttu-id="756bd-133">\*\* [New-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):\*\* CsVideoInteropServiceProvider를 사용 하 여 조직에서 사용 하려는 지원 되는 CVI 파트너에 대 한 정보를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-133">**[New-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):** Use the New-CsVideoInteropServiceProvider to specify information about a supported CVI partner your organization would like to use.</span></span>
 
- <span data-ttu-id="756bd-134">\*\* [Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):\*\* CsVideoInteropServiceProvider를 사용 하 여 조직에서 사용 하는 지원 되는 CVI 파트너에 대 한 정보를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-134">**[Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):** Use the Set-CsVideoInteropServiceProvider to update information about a supported CVI partner your organization uses.</span></span>
 
- <span data-ttu-id="756bd-135">\*\* [Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):\*\* 조직 내에서 사용 하도록 구성 된 모든 공급자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-135">**[Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):** Get all of the providers that have been configured for use within the organization.</span></span>
 
- <span data-ttu-id="756bd-136">\*\* [제거-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):\*\* CsVideoInteropServiceProvider를 사용 하 여 조직에서 더 이상 사용 하지 않는 공급자에 대 한 모든 공급자 정보를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-136">**[Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider to remove all provider information about a provider that your organization no longer uses.</span></span>  
 
## <a name="consent"></a><span data-ttu-id="756bd-137">서명</span><span class="sxs-lookup"><span data-stu-id="756bd-137">Consent</span></span>

<span data-ttu-id="756bd-138">파트너 서비스를 통해 조직 모임에 참가 하려면 VTCs (비디오 teleconferencing 장치)에 대 한 사용 권한 동의를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-138">You will need to provide permission consent for the video teleconferencing devices (VTCs) to join your organizations meetings via the partner service.</span></span> <span data-ttu-id="756bd-139">이 동의 링크는 파트너도 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-139">This consent link will also be provided by your partner.</span></span>  
 
<span data-ttu-id="756bd-140">이러한 단계가 완료 되 면 위의 부여 cmdlet을 통해 개별적으로 사용 하도록 설정 된 사용자 또는 테 넌 트가 설정 된 경우 조직의 모든 사용자가 예약 하는 모든 팀 모임에서 VTC 좌표를 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-140">When these steps are complete, the users who are individually enabled via the Grant cmdlet above, or all of the users in the organization if the tenant is enabled, will have VTC coordinates in all the Teams meetings that they schedule.</span></span> <span data-ttu-id="756bd-141">모든 VTC는 이러한 좌표를 통해 이러한 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-141">Any VTC can join these meetings via those coordinates.</span></span>


|<span data-ttu-id="756bd-142">이름</span><span class="sxs-lookup"><span data-stu-id="756bd-142">Name</span></span>|<span data-ttu-id="756bd-143">응용 프로그램 권한 간단한 설명</span><span class="sxs-lookup"><span data-stu-id="756bd-143">Application Permission Short Description</span></span>| <span data-ttu-id="756bd-144">설명</span><span class="sxs-lookup"><span data-stu-id="756bd-144">Description</span></span>|
|--|--|---|
|<span data-ttu-id="756bd-145">-JoinGroupCall을 호출 합니다. 모든</span><span class="sxs-lookup"><span data-stu-id="756bd-145">Calls.JoinGroupCall.All</span></span>|<span data-ttu-id="756bd-146">그룹 통화 및 모임을 앱으로 참가 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="756bd-146">Join Group Calls and Meetings as an app (preview)</span></span>|<span data-ttu-id="756bd-147">앱이 로그인 한 사용자 없이 조직의 그룹 통화 및 예약 된 모임을 참가할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-147">Allows the app to join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="756bd-148">앱이 테 넌 트에서 모임에 대 한 디렉터리 사용자의 권한과 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-148">The app will be joined with the privileges of a directory user to meetings in your tenant.</span></span>|
|<span data-ttu-id="756bd-149">JoinGroupCallasGuest를 호출 합니다. 모든</span><span class="sxs-lookup"><span data-stu-id="756bd-149">Calls.JoinGroupCallasGuest.All</span></span>|<span data-ttu-id="756bd-150">게스트 사용자로 그룹 통화 및 모임 참가 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="756bd-150">Join Group Calls and Meetings as a guest user (preview)</span></span>|<span data-ttu-id="756bd-151">앱이 로그인 한 사용자 없이 조직의 그룹 통화 및 예약 된 모임을 익명으로 참가할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-151">Allows the app to anonymously join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="756bd-152">앱이 테 넌 트에서 모임에 게스트로 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-152">The app will be joined as a guest to meetings in your tenant.</span></span>|
|<span data-ttu-id="756bd-153">AccessMedia를 호출 합니다. 모든</span><span class="sxs-lookup"><span data-stu-id="756bd-153">Calls.AccessMedia.All</span></span>|<span data-ttu-id="756bd-154">앱으로 호출에서 미디어 스트림 액세스 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="756bd-154">Access media streams in a call as an app (preview)</span></span>|<span data-ttu-id="756bd-155">앱에서 로그인 한 사용자 없이 호출의 미디어 스트림에 직접 액세스할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-155">Allows the app to get direct access to media streams in a call, without a signed-in user.</span></span>|
|<span data-ttu-id="756bd-156">OnlineMeetings를 참조 하세요. 모든</span><span class="sxs-lookup"><span data-stu-id="756bd-156">OnlineMeetings.Read.All</span></span>|<span data-ttu-id="756bd-157">온라인 모임 세부 정보 읽기 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="756bd-157">Read Online Meeting details (preview)</span></span>|<span data-ttu-id="756bd-158">앱에서 로그인 한 사용자 없이 조직의 온라인 모임 세부 정보를 읽을 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-158">Allows the app to read Online Meeting details in your organization, without a signed-in user.</span></span>|

## <a name="schedule"></a><span data-ttu-id="756bd-159">따라</span><span class="sxs-lookup"><span data-stu-id="756bd-159">Schedule</span></span>

<span data-ttu-id="756bd-160">다음으로, 비디오 interop 좌표로 팀 모임을 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-160">Next, schedule Teams meeting with video interop coordinates.</span></span> <span data-ttu-id="756bd-161">사용 하도록 설정 된 사용자는 다음을 통해 팀의 모임을 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-161">The enabled user can schedule teams meetings via:</span></span>
- [<span data-ttu-id="756bd-162">Outlook 용 팀 모임 추가 기능</span><span class="sxs-lookup"><span data-stu-id="756bd-162">Teams Meeting add-in for Outlook</span></span>](teams-add-in-for-outlook.md)
- <span data-ttu-id="756bd-163">팀 클라이언트 데스크톱 및 모바일</span><span class="sxs-lookup"><span data-stu-id="756bd-163">Teams client desktop and mobile</span></span>


## <a name="join"></a><span data-ttu-id="756bd-164">합류</span><span class="sxs-lookup"><span data-stu-id="756bd-164">Join</span></span>

<span data-ttu-id="756bd-165">다음과 같은 방법으로 팀 모임에 VTC 장치를 사용 하 여 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-165">You can join Teams meetings with your VTC devices in the following ways:</span></span>
 
- <span data-ttu-id="756bd-166">IVR (대화형 음성 응답)</span><span class="sxs-lookup"><span data-stu-id="756bd-166">IVR (Interactive voice Response)</span></span>
    - <span data-ttu-id="756bd-167">Tenantkey @ domain을 사용 하 여 파트너의 IVR에 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-167">You can dial in to the partner's IVR using the tenantkey@domain.</span></span> 
    - <span data-ttu-id="756bd-168">파트너 IVR에 속한 경우 VTC conferenceId을 입력 하 라는 메시지가 표시 되 고 팀 회의에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-168">Once you are in the partner IVR, you will be prompted to enter the VTC conferenceId, which will then connect you to the Teams meeting.</span></span>
- <span data-ttu-id="756bd-169">다이렉트 전화 접속</span><span class="sxs-lookup"><span data-stu-id="756bd-169">Direct dial</span></span>
    - <span data-ttu-id="756bd-170">Tenantkey의 전체 문자열을 사용 하 여 직접 전화 접속 기능을 사용 하 여 파트너의 IVR과 상호 작용 하지 않고 팀 모임에 직접 전화를 걸 수 있습니다. VTC ConferenceId @ domain.</span><span class="sxs-lookup"><span data-stu-id="756bd-170">You can directly dial into the Teams meeting without interacting with the partner’s IVR by using the direct dial feature using the full string of tenantkey.VTC ConferenceId@domain.</span></span>
- <span data-ttu-id="756bd-171">한 번 터치 다이얼</span><span class="sxs-lookup"><span data-stu-id="756bd-171">One-touch dial</span></span>
    - <span data-ttu-id="756bd-172">통합 된 팀 객실이 있는 경우에는 해당 파트너가 제공 하는 원터치 전화 접속 기능을 사용할 수 있습니다 (다이얼 문자열을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="756bd-172">If you have an integrated Teams room, you can use the one-touch dial capabilities offered by your partner (without needing to type any dial string).</span></span>

<span data-ttu-id="756bd-173">마지막으로, 오디오, 비디오, 콘텐츠 공유를 사용 하 여 모임에서 팀 사용자에 게 참여 합니다.</span><span class="sxs-lookup"><span data-stu-id="756bd-173">Finally, engage with Teams users in your meetings using audio, video, and content sharing.</span></span> 