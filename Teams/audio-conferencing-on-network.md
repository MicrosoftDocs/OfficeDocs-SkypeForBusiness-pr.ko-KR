---
title: 오디오 회의를 위한 네트워크 회의
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: oscarr
ms.topic: conceptual
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 다음은 오디오 회의를 위한 네트워크의 열기 미리 보기 기능에 대 한 설명입니다.
ms.openlocfilehash: 3b33c67cc79f79d36cf2a11213dc934103b026fb
ms.sourcegitcommit: 19662d4bc4070f6031084d93e8794e0e02decd2b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/01/2020
ms.locfileid: "47321809"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a><span data-ttu-id="f234f-103">오디오 회의를 위한 네트워크 회의 미리 보기 열기</span><span class="sxs-lookup"><span data-stu-id="f234f-103">Open Preview of On-network Conferencing for Audio Conferencing</span></span>

<span data-ttu-id="f234f-104">네트워크 회의의 열려 있는 미리 보기는 모든 고객에 게 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-104">The Open Preview of On-network Conferencing is available to all customers.</span></span> <span data-ttu-id="f234f-105">네트워크 회의를 통해 조직에서 직접 라우팅을 통해 Microsoft 전화 접속 번호로 인바운드 및 아웃 바운드 오디오 회의 전화를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-105">On-network Conferencing allows organizations to send inbound and outbound Audio Conferencing calls to Microsoft dial-in numbers through Direct Routing.</span></span> <span data-ttu-id="f234f-106">이 접근 권한 값은 타사 전화 접속 번호에 대 한 오디오 회의 지원을 확장 하기 위한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-106">This capability is not intended to extend the support of Audio Conferencing to third party dial-in numbers.</span></span> <span data-ttu-id="f234f-107">타사 전화 접속 전화 번호로 음성 회의 서비스에 대 한 인바운드 호출을 라우팅하는 데 사용 되는 네트워크 회의는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-107">On-network Conferencing is not supported if it is used to route inbound calls to the Audio Conferencing service through third party dial-in phone numbers.</span></span>

<span data-ttu-id="f234f-108">이 문서에서는 조직에 대 한 네트워크 회의를 사용 하도록 설정 하는 데 필요한 전제 조건 및 구성 단계에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-108">This article describes the prerequisites and configuration steps required to enable On-network Conferencing for your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f234f-109">인도에서 전화 접속 장비를 사용 하 여 네트워크 회의를 배포 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-109">On-network Conferencing must NOT be deployed with any telephony equipment in India.</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="f234f-110">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="f234f-110">Prerequisites</span></span>

<span data-ttu-id="f234f-111">네트워크 회의를 구성 하기 전에 조직이 다음 필수 조건을 충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-111">Before configuring On-network Conferencing, make sure your organization meets the following prerequisites:</span></span> 

- <span data-ttu-id="f234f-112">오디오 회의에 사용 하도록 설정 되어 있거나 사용할 수 있는 조직의 모든 사용자가 팀 전용 모드에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-112">Ensure that all users in your organization who are enabled, or will be enabled, for Audio Conferencing are in Teams Only mode.</span></span> <span data-ttu-id="f234f-113">네트워크 회의를 통한 인바운드 및 outboud 오디오 회의 호출은 팀 모임에 대해서만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-113">The routing of inbound and outboud Audio Conferencing calls through On-network Conferencing is only supported for Teams meetings.</span></span>

- <span data-ttu-id="f234f-114">네트워크 회의를 사용 하는 모든 사용자에 게 오디오 회의 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-114">Assign Audio Conferencing licenses to all users who will be using On-network Conferencing.</span></span>

- <span data-ttu-id="f234f-115">오디오 회의 서비스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-115">Set up the Audio Conferencing service.</span></span> <span data-ttu-id="f234f-116">자세한 내용은 [Microsoft 팀을 위한 오디오 회의 설정을](set-up-audio-conferencing-in-teams.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f234f-116">For additional information, see [Set up Audio Conferencing for Microsoft Teams](set-up-audio-conferencing-in-teams.md).</span></span>

- <span data-ttu-id="f234f-117">직접 라우팅에 대 한 SBC (세션 경계 컨트롤러)를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-117">Set up your Session Border Controller (SBC) for Direct Routing.</span></span> <span data-ttu-id="f234f-118">자세한 내용은 [직접 라우팅 계획](direct-routing-plan.md) 및 [직접 라우팅 구성을](direct-routing-configure.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f234f-118">For additional information, see [Plan Direct Routing](direct-routing-plan.md) and [Configure Direct Routing](direct-routing-configure.md).</span></span> 

  <span data-ttu-id="f234f-119">오디오 회의 목적 으로만 직접 라우팅을 설정 하는 경우에는 네트워크 회의에 대 한 "1 단계: SBC 연결"만 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-119">If you are setting up Direct Routing only for the purposes of Audio Conferencing, then you need only complete “Step 1: Connect your SBC” for On-network Conferencing.</span></span>
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a><span data-ttu-id="f234f-120">다이렉트 라우팅을 통해 Microsoft 오디오 회의로 전화 접속 통화를 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-120">Enable the routing of dial-in calls to Microsoft Audio Conferencing through Direct Routing</span></span> 

<span data-ttu-id="f234f-121">온-프레미스 사용자가 직접 라우팅을 통해 음성 회의 서비스에 대 한 전화 접속 통화를 라우팅 하려면 사용자의 SBCs 및 개인 분기 교환 (Pbx)에 적절 한 라우팅 규칙을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-121">To route dial-in calls made by your on-premises users to the Audio Conferencing service through Direct Routing, you need to configure appropriate routing rules for your SBCs and Private Branch Exchange(s) (PBXs).</span></span>

<span data-ttu-id="f234f-122">직접 라우팅 트렁크를 통해 조직의 컨퍼런스 서비스 번호로 통화를 라우팅하도록 사이트의 전화 통신 장비를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-122">You need to configure the telephony equipment of your sites to route calls to any service number of the conference bridge of your organization through a Direct Routing trunk.</span></span>

<span data-ttu-id="f234f-123">**모임 > 회의 브리지** 또는 비즈니스용 Skype Online PowerShell cmdlet CsOnlineDialInConferencingBridge을 사용 하 여 팀 관리 센터에서 서비스 번호를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-123">You can find the service numbers in Teams admin center under **Meetings -> Conferencing Bridges** or by using the Skype for Business Online PowerShell cmdlet Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="f234f-124">자세한 내용은 [Microsoft 팀의 오디오 회의 번호](see-a-list-of-audio-conferencing-numbers-in-teams.md)목록을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f234f-124">For additional information, see a list of [Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>


## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a><span data-ttu-id="f234f-125">다이렉트 라우팅을 통해 팀의 모임 전화 접속 통화 회람 사용</span><span class="sxs-lookup"><span data-stu-id="f234f-125">Enable the routing of Teams meeting dial-out calls through Direct Routing</span></span>

<span data-ttu-id="f234f-126">팀 모임 전화 접속 통화는 조직의 모임 내에서 전화 통화 및 통화를 포함 하 여 새 참가자를 모임에 가져오는 등의 PSTN 번호로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-126">Teams meeting dial-out calls are initiated from within a meeting in your organization to PSTN numbers, including call-me-at calls and calls to bring new participants to a meeting.</span></span> 

<span data-ttu-id="f234f-127">다이렉트 라우팅을 통해 팀 모임 다이얼 아웃 라우팅을 사용 하도록 설정 하려면 "OnlineAudioConferencingRoutingPolicy" 이라는 오디오 회의 라우팅 정책을 만들어 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-127">To enable Teams meeting dial-out routing through Direct Routing, you need to create and assign an Audio Conferencing routing policy called “OnlineAudioConferencingRoutingPolicy”.</span></span> 

<span data-ttu-id="f234f-128">OnlineAudioConferencingRoutingPolicy 정책은 직접 라우팅을 통한 1:1 PSTN 통화에 대 한 CsOnlineVoiceRoutingPolicy와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-128">The OnlineAudioConferencingRoutingPolicy policy is equivalent to the CsOnlineVoiceRoutingPolicy for 1:1 PSTN calls via Direct Routing.</span></span> <span data-ttu-id="f234f-129">OnlineAudioConferencingRoutingPolicy 정책은 다음 cmdlet을 사용 하 여 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-129">The OnlineAudioConferencingRoutingPolicy policy can be managed by using the following cmdlets:</span></span>

-   <span data-ttu-id="f234f-130">새로운 CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="f234f-130">New-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="f234f-131">Set-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="f234f-131">Set-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="f234f-132">Get-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="f234f-132">Get-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="f234f-133">부여-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="f234f-133">Grant-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="f234f-134">제거-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="f234f-134">Remove-CsOnlineAudioConferencingRoutingPolicy</span></span>

<span data-ttu-id="f234f-135">직접 라우팅을 위한 라우팅에 대 한 자세한 내용은 [직접 라우팅에 대 한 음성 라우팅 구성을](direct-routing-voice-routing.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f234f-135">For more information about routing for Direct Routing, see [Configure voice routing for Direct Routing](direct-routing-voice-routing.md).</span></span>


<span data-ttu-id="f234f-136">다이렉트 라우팅을 통해 모임 전화 접속 통화를 회람할 수 있도록 설정 하려면 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-136">To enable the routing of meeting dial-out calls through Direct Routing, you need to:</span></span> 

- <span data-ttu-id="f234f-137">오디오 회의 라우팅 정책 구성</span><span class="sxs-lookup"><span data-stu-id="f234f-137">Configure Audio Conferencing routing policies</span></span>
- <span data-ttu-id="f234f-138">조직의 전화 통신 장비에서 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="f234f-138">Configure the routing on the telephony equipment of your organization</span></span>
- <span data-ttu-id="f234f-139">) 다이얼 플랜 구성</span><span class="sxs-lookup"><span data-stu-id="f234f-139">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="f234f-140">팀 회의의 전화 접속 통화는 회의 브리지의 기본 서비스 번호에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-140">Dial-out calls from Teams meetings are coming from the default service number on the conference bridge.</span></span> <span data-ttu-id="f234f-141">오디오 회의 브리지의 기본 서비스 번호에 대 한 자세한 내용은 [오디오 회의 브리지에서 전화 번호 변경을](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f234f-141">For additional information on the default service number of your Audio Conferencing bridge, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

### <a name="configure-audio-conferencing-routing-policies"></a><span data-ttu-id="f234f-142">오디오 회의 라우팅 정책 구성</span><span class="sxs-lookup"><span data-stu-id="f234f-142">Configure Audio Conferencing routing policies</span></span>

<span data-ttu-id="f234f-143">오디오 회의 라우팅 정책 OnlineAudioConferencingRoutingPolicy는 직접 라우팅 trunks 라우팅되는 모임 전화 접속 통화를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-143">The Audio Conferencing routing policy OnlineAudioConferencingRoutingPolicy determines which meeting dial-out calls are routed to Direct Routing trunks.</span></span> <span data-ttu-id="f234f-144">CsOnlineVoiceRoutingPolicy 정책에 익숙한 경우이 정책은 매우 비슷한 방식으로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-144">If you are familiar with the CsOnlineVoiceRoutingPolicy policy, this policy works in a very similar way.</span></span>

<span data-ttu-id="f234f-145">오디오 회의 라우팅 정책을 설정 하려면 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-145">The following steps are needed to set up Audio Conferencing routing policies:</span></span>
1.  <span data-ttu-id="f234f-146">PSTN 용도 만들기</span><span class="sxs-lookup"><span data-stu-id="f234f-146">Create PSTN usages</span></span>
2.  <span data-ttu-id="f234f-147">음성 경로 구성</span><span class="sxs-lookup"><span data-stu-id="f234f-147">Configure voice routes</span></span>
3.  <span data-ttu-id="f234f-148">오디오 회의 음성 라우팅 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="f234f-148">Create Audio Conferencing voice routing policies</span></span>
4.  <span data-ttu-id="f234f-149">사용자에 게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="f234f-149">Assign a policy to your users</span></span>


#### <a name="create-pstn-usages"></a><span data-ttu-id="f234f-150">PSTN 용도 만들기</span><span class="sxs-lookup"><span data-stu-id="f234f-150">Create PSTN usages</span></span>

<span data-ttu-id="f234f-151">PSTN 용도는 음성 경로의 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-151">PSTN usages are collections of voice routes.</span></span> <span data-ttu-id="f234f-152">특정 이끌이의 모임에서 전화를 걸거나 받을 때 음성 경로는 사용자의 음성 라우팅 정책을 통해 사용자와 연결 된 PSTN 용도에 따라 통화의 라우팅 경로를 결정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-152">When a dial-out call is initiated from the meeting of a given organizer, voice routes will be used to determine the routing path of the call based on the PSTN usages that are associated to the user via the user’s voice routing policy.</span></span>

<span data-ttu-id="f234f-153">"Set-CsOnlinePstnUsage" cmdlet을 사용 하 여 PSTN 사용을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-153">You can create a PSTN usage by using the “Set-CsOnlinePstnUsage” cmdlet.</span></span> <span data-ttu-id="f234f-154">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="f234f-154">For Example:</span></span>

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a><span data-ttu-id="f234f-155">음성 경로 구성</span><span class="sxs-lookup"><span data-stu-id="f234f-155">Configure voice routes</span></span>

<span data-ttu-id="f234f-156">음성 경로는 팀 모임에서 전화를 거는 전화 번호를 기준으로 통화를 라우팅하는 데 사용 되는 PSTN 게이트웨이를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-156">Voice routes determine the PSTN gateway that should be used to route a call based on the phone number that is dialed from a Teams meeting.</span></span> <span data-ttu-id="f234f-157">음성 경로는 팀 모임에서 보낸 전화 번호를 regex 패턴으로 사용 하 여 지정 된 통화를 라우팅하는 데 사용 되는 PSTN 게이트웨이를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-157">Voice routes determine the PSTN gateway that should be used to route a given call by matching the phone number dialed from a Teams meeting with a regex pattern.</span></span> <span data-ttu-id="f234f-158">음성 경로를 만들 때 경로는 하나 이상의 PSTN 용도에 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-158">When creating a voice route, the route must be associated to one or more PSTN usages.</span></span>

<span data-ttu-id="f234f-159">"CsOnlineVoiceRoute" cmdlet을 사용 하 여 음성 경로를 만들고 음성 경로와 연결할 regex 및 게이트웨이를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-159">You can create a voice route and define the regex and gateways to be associated with the voice route by using the “New-CsOnlineVoiceRoute” cmdlet.</span></span> <span data-ttu-id="f234f-160">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="f234f-160">For Example:</span></span>

```
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a><span data-ttu-id="f234f-161">오디오 회의 음성 라우팅 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="f234f-161">Create Audio Conferencing voice routing policies</span></span>

<span data-ttu-id="f234f-162">오디오 회의 음성 라우팅 정책은 모임 전화 접속 통화의 대상 전화 번호를 기준으로 이끌이의 모임에서 발생 하는 통화를 라우팅하는 데 사용할 수 있는 경로를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-162">Audio Conferencing voice routing policies determine the possible routes that can be used to route a call originating from the meetings of an organizer based on the target phone number of the meeting dial-out call.</span></span> <span data-ttu-id="f234f-163">오디오 회의 음성 라우팅 정책은 하나 이상의 PSTN 용도에 연결 되며, 그에 따라 정책에 연결 된 이끌이의 모임 전화 접속 통화에 사용할 가능한 경로를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-163">Audio Conferencing voice routing policies are associated to one or more PSTN usages, which in turn, determine the possible routes that will be attempted to be used for the meeting dial-out calls of the organizers associated to the policy.</span></span>

<span data-ttu-id="f234f-164">"New-CsOnlineAudioConferencingRoutingPolicy" cmdlet을 사용 하 여 오디오 회의 음성 라우팅 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-164">You can create an Audio Conferencing voice routing policy by using the “New- CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="f234f-165">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="f234f-165">For Example:</span></span>

```
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="f234f-166">정책이 사용자에 게 할당 되 고 사용자의 모임 중 하나에서 모임 전화 접속 통화가 시작 되 면 사용자의 음성 라우팅 정책을 통해 구성 도우미에 연결 된 PSTN 사용의 음성 경로가 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-166">After the policy is assigned to a user, and when a meeting dial-out call is initiated from one of the user's meetings, the voice routes in the PSTN usages that are associated to the organizer through the user's voice routing policy will be evaluated.</span></span> <span data-ttu-id="f234f-167">모임 전화 접속 통화 대상이 이끌이와 연결 된 음성 경로 중 하나에서 regex와 일치 하는 경우 모임 전화 접속 전화는 음성 경로에 정의 된 PSTN 게이트웨이로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-167">If the meeting dial-out call destination matches a regex in one of the voice routes that are associated to the organizer, the meeting dial-out call will be routed to the PSTN gateway defined in the voice route.</span></span> <span data-ttu-id="f234f-168">모임 전화 접속 통화 대상이 이끌이에 연결 된 음성 경로와 일치 하지 않는 경우 모임 전화 접속 통화는 Microsoft에서 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-168">If the meeting dial-out call destination does not match any of the voice routes associated to the organizer, the meeting dial-out call will be routed by Microsoft.</span></span>

#### <a name="assign-a-policy-to-your-users"></a><span data-ttu-id="f234f-169">사용자에 게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="f234f-169">Assign a policy to your users</span></span>

<span data-ttu-id="f234f-170">오디오 회의 라우팅 정책이 정의 되 면 이제 사용자에 게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-170">After the Audio Conferencing routing policies are defined, you can now assign them to users.</span></span> <span data-ttu-id="f234f-171">정책이 할당 되 면 해당 라우팅 경로를 결정 하기 위해 모임 전화 접속 호출이 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-171">After policies are assigned to them, the meeting dial-out calls will be evaluated against it to determine their routing path.</span></span> <span data-ttu-id="f234f-172">오디오 회의 라우팅 정책은 모임 전화 접속 통화를 시작 하는 모임 사용자와 별개로 모임 이끌이를 기준으로 항상 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-172">Audio Conferencing routing policies are always evaluated based on the organizer of the meeting, independently from the user in the meeting that initiates a meeting dial-out call.</span></span>

<span data-ttu-id="f234f-173">"CsOnlineAudioConferencingRoutingPolicy" cmdlet을 사용 하 여 사용자에 게 오디오 회의 음성 라우팅 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-173">You can assign an Audio Conferencing voice routing policy to a user by using the “Grant-CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="f234f-174">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-174">For example:</span></span>

```
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a><span data-ttu-id="f234f-175">조직의 전화 통신 장비에 대 한 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="f234f-175">Configure routing on the telephony equipment of your organization</span></span>

<span data-ttu-id="f234f-176">조직의 전화 통신 장비에서 직접 라우팅을 통해 라우팅되는 모임 전화 접속 호출이 의도 하는 대상에 회람 되는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-176">On the telephony equipment of your organization, you need to ensure that the meeting dial-out calls routed through Direct Routing are routed to the intended destination.</span></span>


### <a name="optional-configure-a-dial-plan"></a><span data-ttu-id="f234f-177">) 다이얼 플랜 구성</span><span class="sxs-lookup"><span data-stu-id="f234f-177">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="f234f-178">다이얼 플랜은 통화 권한 부여 및 통화 라우팅과 같은 목적으로 개별 사용자가 사용 하는 전화 번호를 대체 형식 (일반적으로 E-164)으로 변환 하는 정규화 규칙 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-178">A dial plan is a set of normalization rules that translate dialed phone numbers by an individual user into an alternate format (typically E.164) for purposes of call authorization and call routing.</span></span>

<span data-ttu-id="f234f-179">기본적으로 팀 사용자는 E-164 형식의 PSTN 번호에 전화를 걸 수 있으며, 즉 + \<country code\> \<number\> .</span><span class="sxs-lookup"><span data-stu-id="f234f-179">By default, Teams users can dial-out to PSTN numbers in E.164 format, that is, +\<country code\>\<number\>.</span></span> <span data-ttu-id="f234f-180">그러나 전화 걸기 계획을 사용 하 여 사용자가 다른 형식의 전화 번호 (예를 들어, 4 자리 확장명)로 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-180">However, dial plans can be used to allow users to dial phone numbers in other formats, for instance 4-digit extensions.</span></span>

<span data-ttu-id="f234f-181">네트워크 회의를 통해 내선 번호로 전화를 걸 수 있도록 하려면 다이얼 플랜을 조직의 전화 번호 범위에 맞게 내선 번호 지정으로 설정 하는 것이 좋을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-181">If you would like to enable extension-based dialing through On-network conferencing, you can set up dial plans to match the extension dialing pattern to the phone number ranges of the phone number of your organization.</span></span> <span data-ttu-id="f234f-182">다이얼 플랜을 설정 하려면 [다이얼 플랜 만들기 및 관리](create-and-manage-dial-plans.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f234f-182">To set up dial plans, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span>


## <a name="known-issues-in-open-preview"></a><span data-ttu-id="f234f-183">열려 있는 미리 보기의 알려진 문제점</span><span class="sxs-lookup"><span data-stu-id="f234f-183">Known issues in Open Preview</span></span>

<span data-ttu-id="f234f-184">다음은 현재 네트워크 회의의 열려 있는 Preview 릴리스에 표시 된 알려진 문제 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-184">The following is a list of known issues that are currently present in the Open Preview release of On-network conferencing.</span></span> <span data-ttu-id="f234f-185">Microsoft는 이러한 문제를 해결 하기 위해 노력 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-185">Microsoft is working on addressing these issues.</span></span>

| <span data-ttu-id="f234f-186">문제</span><span class="sxs-lookup"><span data-stu-id="f234f-186">Issue</span></span> | <span data-ttu-id="f234f-187">방법을</span><span class="sxs-lookup"><span data-stu-id="f234f-187">Workaround</span></span> |
| :--- | :--- |
| <span data-ttu-id="f234f-188">네트워크 회의를 통해 라우팅되는 익명/숨김 발신자 Id를 사용 하는 전화 접속 통화는 모임에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-188">Dial-in calls with anonymous/hidden caller IDs that are routed through On-network conferencing cannot be connected to the meeting.</span></span> | <span data-ttu-id="f234f-189">가능 하다 면 PBX 또는 SBC에서 구성을 설정 하 여 항상 네트워크 회의를 통해 라우팅된 통화에 대 한 발신자 ID를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-189">If possible, set a configuration in your PBX or SBC to always send a caller ID for calls routed via On-network conferencing.</span></span>|
| <span data-ttu-id="f234f-190">경우에 따라 서비스에 전화 접속을 할 때 사용자에 게 재생 되는 시작 메시지 ("오디오 회의 서비스 시작 ...")가 잘리고 사용자가 "시작" 단어를 듣지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-190">In some cases, the welcome message that is played to users when they dial in to the service (“Welcome to the Audio Conferencing service…”) is truncated and users do not hear the “Welcome” word.</span></span>| <span data-ttu-id="f234f-191">현재이 문제에 대 한 해결 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f234f-191">There are no workarounds for this issue at the moment.</span></span> |




## <a name="related-topics"></a><span data-ttu-id="f234f-192">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f234f-192">Related topics</span></span>


