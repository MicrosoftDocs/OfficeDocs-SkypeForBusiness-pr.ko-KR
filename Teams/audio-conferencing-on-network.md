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
- m365initiative-meetings
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 다음은 오디오 회의용 네트워크의 Open Preview 기능에 대해 설명합니다.
ms.openlocfilehash: d6df81cc077c69fdeb4246d682797d2ebb26b875
ms.sourcegitcommit: 950387da2a2c094b7580bcf81ae5d8b6dfba0d6b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2021
ms.locfileid: "51637840"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a><span data-ttu-id="1565b-103">오디오 회의를 위한 네트워크 회의의 미리 보기 열기</span><span class="sxs-lookup"><span data-stu-id="1565b-103">Open Preview of On-network Conferencing for Audio Conferencing</span></span>

<span data-ttu-id="1565b-104">네트워크 회의의 열기 미리 보기는 모든 고객이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-104">The Open Preview of On-network Conferencing is available to all customers.</span></span> <span data-ttu-id="1565b-105">조직은 네트워크 회의를 통해 직접 라우팅을 통해 Microsoft 전화 접속 번호로 인바운드 및 아웃바운드 오디오 회의 호출을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-105">On-network Conferencing allows organizations to send inbound and outbound Audio Conferencing calls to Microsoft dial-in numbers through Direct Routing.</span></span> <span data-ttu-id="1565b-106">이 기능은 오디오 회의의 지원을 타사 전화 접속 번호로 확장하기 위한 것이 아니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-106">This capability is not intended to extend the support of Audio Conferencing to third party dial-in numbers.</span></span> <span data-ttu-id="1565b-107">타사 전화 접속 전화 번호 또는 Microsoft Audio Conferencing Bridge에서 PSTN에 대한 아웃바운드 호출을 통해 오디오 회의 서비스에 인바운드 호출을 라우팅하는 데 사용되는 경우 네트워크 회의는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-107">On-network Conferencing is not supported if it is used to route inbound calls to the Audio Conferencing service through third party dial-in phone numbers or outbound calls to the PSTN from Microsoft Audio Conferencing Bridge.</span></span> 

<span data-ttu-id="1565b-108">이 문서에서는 조직에 대한 네트워크 회의를 사용하도록 설정하는 데 필요한 필수 구성 단계 및 구성 단계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-108">This article describes the prerequisites and configuration steps required to enable On-network Conferencing for your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1565b-109">인도의 전화 통신 장비와 함께 네트워크 회의를 배포하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-109">On-network Conferencing must NOT be deployed with any telephony equipment in India.</span></span>
  
## <a name="prerequisites"></a><span data-ttu-id="1565b-110">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="1565b-110">Prerequisites</span></span>

<span data-ttu-id="1565b-111">네트워크 회의를 구성하기 전에 조직이 다음 요구 사항을 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-111">Before configuring On-network Conferencing, make sure your organization meets the following prerequisites:</span></span> 

- <span data-ttu-id="1565b-112">오디오 회의에서 사용하도록 설정되어 있는 조직의 모든 사용자가 모든 모임에 대해 Teams 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-112">Ensure that all users in your organization who are enabled, or will be enabled, for Audio Conferencing are using Teams for all Meetings.</span></span> <span data-ttu-id="1565b-113">네트워크 회의를 통한 인바운드 및 아웃바운드 오디오 회의 호출의 라우팅은 Teams 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-113">The routing of inbound and outbound Audio Conferencing calls through On-network Conferencing is only supported for Teams meetings.</span></span>

- <span data-ttu-id="1565b-114">네트워크 회의를 사용할 모든 사용자에게 오디오 회의 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-114">Assign Audio Conferencing licenses to all users who will be using On-network Conferencing.</span></span>

- <span data-ttu-id="1565b-115">오디오 회의 서비스를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-115">Set up the Audio Conferencing service.</span></span> <span data-ttu-id="1565b-116">자세한 내용은 에 대한 오디오 회의 [설정 을 Microsoft Teams.](set-up-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="1565b-116">For additional information, see [Set up Audio Conferencing for Microsoft Teams](set-up-audio-conferencing-in-teams.md).</span></span>

- <span data-ttu-id="1565b-117">직접 라우팅을 위해 SBC(세션 테두리 컨트롤러)를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-117">Set up your Session Border Controller (SBC) for Direct Routing.</span></span> <span data-ttu-id="1565b-118">자세한 내용은 [직접](direct-routing-plan.md) 라우팅 계획 및 직접 라우팅 [구성을 참조하세요.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="1565b-118">For additional information, see [Plan Direct Routing](direct-routing-plan.md) and [Configure Direct Routing](direct-routing-configure.md).</span></span> 

  <span data-ttu-id="1565b-119">오디오 회의 목적으로만 직접 라우팅을 설정하는 경우 네트워크 회의에 대해 "1단계: SBC 커넥트"만 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-119">If you are setting up Direct Routing only for the purposes of Audio Conferencing, then you need only complete “Step 1: Connect your SBC” for On-network Conferencing.</span></span>
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a><span data-ttu-id="1565b-120">직접 라우팅을 통해 Microsoft 오디오 회의에 대한 전화 접속 통화 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="1565b-120">Enable the routing of dial-in calls to Microsoft Audio Conferencing through Direct Routing</span></span> 

<span data-ttu-id="1565b-121">직접 라우팅을 통해 프레미스 사용자가 만든 전화 접속 통화를 직접 라우팅을 통해 오디오 회의 서비스에 라우팅하려면 SBC 및 개인 분기 Exchange(PBX)에 대한 적절한 라우팅 규칙을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-121">To route dial-in calls made by your on-premises users to the Audio Conferencing service through Direct Routing, you need to configure appropriate routing rules for your SBCs and Private Branch Exchange(s) (PBXs).</span></span>

<span data-ttu-id="1565b-122">직접 라우팅 트렁크를 통해 조직의 전화 회의 브리지의 모든 서비스 번호로 호출을 라우팅하도록 사이트의 전화 통신 장비를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-122">You need to configure the telephony equipment of your sites to route calls to any service number of the conference bridge of your organization through a Direct Routing trunk.</span></span>

<span data-ttu-id="1565b-123">모임 **> -Teams** 회의 브리지에서 또는 비즈니스용 Skype Online PowerShell cmdlet Get-CsOnlineDialInConferencingBridge를 사용하여 관리 센터에서 서비스 번호를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-123">You can find the service numbers in Teams admin center under **Meetings -> Conferencing Bridges** or by using the Skype for Business Online PowerShell cmdlet Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="1565b-124">자세한 내용은 의 오디오 회의 번호 목록을 [Microsoft Teams.](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="1565b-124">For additional information, see a list of [Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1565b-125">분당 유료 오디오 회의 라이선스가 있는 사용자는 이 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-125">This feature is not available to users with the pay-per-minute Audio Conferencing license.</span></span>

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a><span data-ttu-id="1565b-126">직접 라우팅을 통해 Teams 전화 접속 통화의 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="1565b-126">Enable the routing of Teams meeting dial-out calls through Direct Routing</span></span>

<span data-ttu-id="1565b-127">Teams 전화 걸기 통화는 조직의 모임 내에서 PSTN 번호로 시작하며, 새 참가자를 모임에 데려오는 전화 통화 및 통화를 포함하여 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-127">Teams meeting dial-out calls are initiated from within a meeting in your organization to PSTN numbers, including call-me-at calls and calls to bring new participants to a meeting.</span></span> 

<span data-ttu-id="1565b-128">직접 라우팅을 통해 Teams 전화 접속 라우팅을 활성화하려면 "OnlineAudioConferencingRoutingPolicy"라는 오디오 회의 라우팅 정책을 만들고 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-128">To enable Teams meeting dial-out routing through Direct Routing to on-network users, you need to create and assign an Audio Conferencing routing policy called “OnlineAudioConferencingRoutingPolicy”.</span></span> 

<span data-ttu-id="1565b-129">OnlineAudioConferencingRoutingPolicy 정책은 직접 라우팅을 통해 1:1 PSTN 호출에 대해 CsOnlineVoiceRoutingPolicy와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-129">The OnlineAudioConferencingRoutingPolicy policy is equivalent to the CsOnlineVoiceRoutingPolicy for 1:1 PSTN calls via Direct Routing.</span></span> <span data-ttu-id="1565b-130">OnlineAudioConferencingRoutingPolicy 정책은 다음 cmdlet을 사용하여 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-130">The OnlineAudioConferencingRoutingPolicy policy can be managed by using the following cmdlets:</span></span>

-   <span data-ttu-id="1565b-131">New-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="1565b-131">New-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="1565b-132">Set-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="1565b-132">Set-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="1565b-133">Get-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="1565b-133">Get-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="1565b-134">Grant-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="1565b-134">Grant-CsOnlineAudioConferencingRoutingPolicy</span></span>
- <span data-ttu-id="1565b-135">Remove-CsOnlineAudioConferencingRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="1565b-135">Remove-CsOnlineAudioConferencingRoutingPolicy</span></span>

<span data-ttu-id="1565b-136">직접 라우팅에 대한 라우팅에 대한 자세한 내용은 직접 라우팅에 대한 음성 라우팅 [구성을 참조하세요.](direct-routing-voice-routing.md)</span><span class="sxs-lookup"><span data-stu-id="1565b-136">For more information about routing for Direct Routing, see [Configure voice routing for Direct Routing](direct-routing-voice-routing.md).</span></span>


<span data-ttu-id="1565b-137">직접 라우팅을 통해 모임 전화 접속 통화의 라우팅을 사용하도록 설정하려면 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-137">To enable the routing of meeting dial-out calls through Direct Routing, you need to:</span></span> 

- <span data-ttu-id="1565b-138">오디오 회의 라우팅 정책 구성</span><span class="sxs-lookup"><span data-stu-id="1565b-138">Configure Audio Conferencing routing policies</span></span>
- <span data-ttu-id="1565b-139">조직의 전화 통신 장비에서 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="1565b-139">Configure the routing on the telephony equipment of your organization</span></span>
- <span data-ttu-id="1565b-140">(선택 사항) 전화 걸기 계획 구성</span><span class="sxs-lookup"><span data-stu-id="1565b-140">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="1565b-141">전화 접속 Teams 전화 회의 브리지의 기본 서비스 번호에서 오는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-141">Dial-out calls from Teams meetings are coming from the default service number on the conference bridge.</span></span> <span data-ttu-id="1565b-142">오디오 회의 브리지의 기본 서비스 번호에 대한 자세한 내용은 오디오 회의 브리지의 전화 번호 변경을 [참조하세요.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)</span><span class="sxs-lookup"><span data-stu-id="1565b-142">For additional information on the default service number of your Audio Conferencing bridge, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

### <a name="configure-audio-conferencing-routing-policies"></a><span data-ttu-id="1565b-143">오디오 회의 라우팅 정책 구성</span><span class="sxs-lookup"><span data-stu-id="1565b-143">Configure Audio Conferencing routing policies</span></span>

<span data-ttu-id="1565b-144">오디오 회의 라우팅 정책 OnlineAudioConferencingRoutingPolicy는 직접 라우팅 트렁크로 라우팅되는 모임 전화 접속 호출을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-144">The Audio Conferencing routing policy OnlineAudioConferencingRoutingPolicy determines which meeting dial-out calls are routed to Direct Routing trunks.</span></span> <span data-ttu-id="1565b-145">CsOnlineVoiceRoutingPolicy 정책을 잘 알고 있는 경우 이 정책은 매우 유사한 방식으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-145">If you are familiar with the CsOnlineVoiceRoutingPolicy policy, this policy works in a very similar way.</span></span>

<span data-ttu-id="1565b-146">오디오 회의 라우팅 정책을 설정하는 데는 다음 단계가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-146">The following steps are needed to set up Audio Conferencing routing policies:</span></span>
1.  <span data-ttu-id="1565b-147">PSTN 사용량 만들기</span><span class="sxs-lookup"><span data-stu-id="1565b-147">Create PSTN usages</span></span>
2.  <span data-ttu-id="1565b-148">음성 경로 구성</span><span class="sxs-lookup"><span data-stu-id="1565b-148">Configure voice routes</span></span>
3.  <span data-ttu-id="1565b-149">오디오 회의 음성 라우팅 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="1565b-149">Create Audio Conferencing voice routing policies</span></span>
4.  <span data-ttu-id="1565b-150">사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="1565b-150">Assign a policy to your users</span></span>


#### <a name="create-pstn-usages"></a><span data-ttu-id="1565b-151">PSTN 사용량 만들기</span><span class="sxs-lookup"><span data-stu-id="1565b-151">Create PSTN usages</span></span>

<span data-ttu-id="1565b-152">PSTN 사용량은 음성 경로의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-152">PSTN usages are collections of voice routes.</span></span> <span data-ttu-id="1565b-153">특정 이끌이의 모임에서 전화 접속 통화가 시작될 때 음성 경로는 사용자의 음성 라우팅 정책을 통해 사용자에게 연결된 PSTN 사용량에 따라 통화의 라우팅 경로를 결정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-153">When a dial-out call is initiated from the meeting of a given organizer, voice routes will be used to determine the routing path of the call based on the PSTN usages that are associated to the user via the user’s voice routing policy.</span></span>

<span data-ttu-id="1565b-154">"Set-CsOnlinePstnUsage" cmdlet을 사용하여 PSTN 사용을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-154">You can create a PSTN usage by using the “Set-CsOnlinePstnUsage” cmdlet.</span></span> <span data-ttu-id="1565b-155">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="1565b-155">For Example:</span></span>

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a><span data-ttu-id="1565b-156">음성 경로 구성</span><span class="sxs-lookup"><span data-stu-id="1565b-156">Configure voice routes</span></span>

<span data-ttu-id="1565b-157">음성 경로는 모임에서 전화를 걸 수 있는 전화 번호를 기반으로 통화를 라우팅하는 데 사용할 PSTN Teams 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-157">Voice routes determine the PSTN gateway that should be used to route a call based on the phone number that is dialed from a Teams meeting.</span></span> <span data-ttu-id="1565b-158">음성 경로는 모임에서 전화한 전화 번호를 regex 패턴으로 Teams 특정 통화를 라우팅하는 데 사용할 PSTN 게이트웨이를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-158">Voice routes determine the PSTN gateway that should be used to route a given call by matching the phone number dialed from a Teams meeting with a regex pattern.</span></span> <span data-ttu-id="1565b-159">음성 경로를 만들 때 경로가 하나 이상의 PSTN 사용량에 연결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-159">When creating a voice route, the route must be associated to one or more PSTN usages.</span></span>

<span data-ttu-id="1565b-160">"New-CsOnlineVoiceRoute" cmdlet을 사용하여 음성 경로를 만들고 음성 경로와 연결될 regex 및 게이트웨이를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-160">You can create a voice route and define the regex and gateways to be associated with the voice route by using the “New-CsOnlineVoiceRoute” cmdlet.</span></span> <span data-ttu-id="1565b-161">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="1565b-161">For Example:</span></span>

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a><span data-ttu-id="1565b-162">오디오 회의 음성 라우팅 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="1565b-162">Create Audio Conferencing voice routing policies</span></span>

<span data-ttu-id="1565b-163">오디오 회의 음성 라우팅 정책은 모임 전화 접속 통화의 대상 전화 번호에 따라 이끌이의 모임에서 시작된 통화를 라우팅하는 데 사용할 수 있는 가능한 경로를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-163">Audio Conferencing voice routing policies determine the possible routes that can be used to route a call originating from the meetings of an organizer based on the target phone number of the meeting dial-out call.</span></span> <span data-ttu-id="1565b-164">오디오 회의 음성 라우팅 정책은 하나 이상의 PSTN 사용량에 연결됩니다. 이 정책에 연결된 이끌이의 모임 전화 접속 호출에 사용할 가능한 경로를 차례로 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-164">Audio Conferencing voice routing policies are associated to one or more PSTN usages, which in turn, determine the possible routes that will be attempted to be used for the meeting dial-out calls of the organizers associated to the policy.</span></span>

<span data-ttu-id="1565b-165">"New- CsOnlineAudioConferencingRoutingPolicy" cmdlet을 사용하여 오디오 회의 음성 라우팅 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-165">You can create an Audio Conferencing voice routing policy by using the “New- CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="1565b-166">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="1565b-166">For Example:</span></span>

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="1565b-167">정책이 사용자에게 할당된 후 사용자의 모임 중 하나에서 모임 전화 접속 통화를 시작하면 사용자의 음성 라우팅 정책을 통해 이끌이에 연결된 PSTN 사용량의 음성 경로가 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-167">After the policy is assigned to a user, and when a meeting dial-out call is initiated from one of the user's meetings, the voice routes in the PSTN usages that are associated to the organizer through the user's voice routing policy will be evaluated.</span></span> <span data-ttu-id="1565b-168">모임 전화 접속 통화 대상이 이끌이에 연결된 음성 경로 중 하나에서 regex와 일치하는 경우 모임 전화 접속 통화는 음성 경로에 정의된 PSTN 게이트웨이로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-168">If the meeting dial-out call destination matches a regex in one of the voice routes that are associated to the organizer, the meeting dial-out call will be routed to the PSTN gateway defined in the voice route.</span></span> <span data-ttu-id="1565b-169">모임 전화 접속 통화 대상이 이끌이에 연결된 음성 경로와 일치하지 않는 경우 모임 전화 접속 통화는 Microsoft에서 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-169">If the meeting dial-out call destination does not match any of the voice routes associated to the organizer, the meeting dial-out call will be routed by Microsoft.</span></span>

#### <a name="assign-a-policy-to-your-users"></a><span data-ttu-id="1565b-170">사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="1565b-170">Assign a policy to your users</span></span>

<span data-ttu-id="1565b-171">오디오 회의 라우팅 정책이 정의된 후에 사용자에게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-171">After the Audio Conferencing routing policies are defined, you can now assign them to users.</span></span> <span data-ttu-id="1565b-172">정책이 할당된 후 모임 전화 접속 호출은 해당 라우팅 경로를 결정하기 위해 해당 정책에 대해 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-172">After policies are assigned to them, the meeting dial-out calls will be evaluated against it to determine their routing path.</span></span> <span data-ttu-id="1565b-173">오디오 회의 라우팅 정책은 항상 모임 전화 접속 통화를 시작하는 모임의 사용자와 독립적으로 모임 이끌이에 따라 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-173">Audio Conferencing routing policies are always evaluated based on the organizer of the meeting, independently from the user in the meeting that initiates a meeting dial-out call.</span></span>

<span data-ttu-id="1565b-174">"Grant-CsOnlineAudioConferencingRoutingPolicy" cmdlet을 사용하여 사용자에게 오디오 회의 음성 라우팅 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-174">You can assign an Audio Conferencing voice routing policy to a user by using the “Grant-CsOnlineAudioConferencingRoutingPolicy” cmdlet.</span></span> <span data-ttu-id="1565b-175">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-175">For example:</span></span>

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a><span data-ttu-id="1565b-176">조직의 전화 통신 장비에서 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="1565b-176">Configure routing on the telephony equipment of your organization</span></span>

<span data-ttu-id="1565b-177">조직의 전화 통신 장비에서 직접 라우팅을 통해 라우팅된 모임 전화 접속 통화가 의도한 네트워크 대상로 라우팅되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-177">On the telephony equipment of your organization, you need to ensure that the meeting dial-out calls routed through Direct Routing are routed to the intended on-network destination.</span></span>


### <a name="optional-configure-a-dial-plan"></a><span data-ttu-id="1565b-178">(선택 사항) 전화 걸기 계획 구성</span><span class="sxs-lookup"><span data-stu-id="1565b-178">(Optional) Configure a dial plan</span></span>

<span data-ttu-id="1565b-179">다이얼 플랜은 통화 권한 부여 및 통화 라우팅을 위해 개별 사용자가 전화 걸기 전화 번호를 대체 형식(일반적으로 E.164)으로 변환하는 정규화 규칙 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-179">A dial plan is a set of normalization rules that translate dialed phone numbers by an individual user into an alternate format (typically E.164) for purposes of call authorization and call routing.</span></span>

<span data-ttu-id="1565b-180">기본적으로 Teams E.164 형식으로 PSTN 번호에 전화 접속할 수 있습니다. 즉, \<country code\> \<number\> +입니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-180">By default, Teams users can dial-out to PSTN numbers in E.164 format, that is, +\<country code\>\<number\>.</span></span> <span data-ttu-id="1565b-181">그러나 전화 걸기 요금제는 사용자가 다른 형식(예: 4자리 확장)으로 전화 번호를 걸 수 있도록 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-181">However, dial plans can be used to allow users to dial phone numbers in other formats, for instance 4-digit extensions.</span></span>

<span data-ttu-id="1565b-182">네트워크 회의를 통해 확장 기반 전화 걸기를 사용하도록 설정하려면 조직의 전화 번호 범위에 확장 전화 걸기 패턴과 일치하도록 전화 걸기 계획을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-182">If you would like to enable extension-based dialing through On-network conferencing, you can set up dial plans to match the extension dialing pattern to the phone number ranges of the phone number of your organization.</span></span> <span data-ttu-id="1565b-183">다이얼 요금제 설정은 전화 걸기 계획 만들기 [및 관리를 참조합니다.](create-and-manage-dial-plans.md)</span><span class="sxs-lookup"><span data-stu-id="1565b-183">To set up dial plans, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span>


## <a name="known-issues-in-open-preview"></a><span data-ttu-id="1565b-184">미리 보기에서 알려진 문제</span><span class="sxs-lookup"><span data-stu-id="1565b-184">Known issues in Open Preview</span></span>

<span data-ttu-id="1565b-185">다음은 현재 네트워크 회의의 오픈 미리 보기 릴리스에 있는 알려진 문제 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-185">The following is a list of known issues that are currently present in the Open Preview release of On-network conferencing.</span></span> <span data-ttu-id="1565b-186">Microsoft는 이러한 문제를 해결하기 위해 작업 중입니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-186">Microsoft is working on addressing these issues.</span></span>

| <span data-ttu-id="1565b-187">문제</span><span class="sxs-lookup"><span data-stu-id="1565b-187">Issue</span></span> | <span data-ttu-id="1565b-188">해결사</span><span class="sxs-lookup"><span data-stu-id="1565b-188">Workaround</span></span> |
| :--- | :--- |
| <span data-ttu-id="1565b-189">네트워크 회의를 통해 라우팅되는 익명/숨겨진 발신자 ID를 사용하여 전화 접속 통화는 모임에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-189">Dial-in calls with anonymous/hidden caller IDs that are routed through On-network conferencing cannot be connected to the meeting.</span></span> | <span data-ttu-id="1565b-190">가능하면 PBX 또는 SBC에서 구성을 설정하여 항상 네트워크 회의를 통해 라우팅된 호출에 대한 발신자 ID를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-190">If possible, set a configuration in your PBX or SBC to always send a caller ID for calls routed via On-network conferencing.</span></span>|
| <span data-ttu-id="1565b-191">경우에 따라 서비스에 전화 접속할 때 사용자에게 재생된 환영 메시지("오디오 회의 서비스에 오신 것을 환영합니다...")가 잘리며 사용자가 "시작" 단어가 들리지 않는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-191">In some cases, the welcome message that is played to users when they dial in to the service (“Welcome to the Audio Conferencing service…”) is truncated and users do not hear the “Welcome” word.</span></span>| <span data-ttu-id="1565b-192">현재 이 문제의 해결방안은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1565b-192">There are no workarounds for this issue at the moment.</span></span> |




## <a name="related-topics"></a><span data-ttu-id="1565b-193">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1565b-193">Related topics</span></span>


