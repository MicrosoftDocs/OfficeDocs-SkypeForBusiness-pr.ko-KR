---
title: 직접 라우팅이 있는 오디오 회의, GCCH 및 DoD
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
description: 관리자는 GCCH 및 DoD 환경에서 직접 라우팅이 있는 오디오 회의를 사용 하는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 34fcb84ee0e5126188f47a4ccc231c04ffd093b2
ms.sourcegitcommit: 8924cd77923ca321de72edc3fed04425a4b13044
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "48262495"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="a1c3c-103">GCC High 및 DoD를 위해 직접 라우팅으로 오디오 회의</span><span class="sxs-lookup"><span data-stu-id="a1c3c-103">Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="a1c3c-104">GCC High 및 DoD에 대 한 직접 라우팅이 있는 오디오 회의는 참가자가 휴대폰 장치를 사용 하 여 GCC High 또는 DoD 조직의 팀 모임에 참가할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-104">Audio Conferencing with Direct Routing for GCC High and DoD enables participants to join Teams meetings in your GCC High or DoD organization by using a phone device.</span></span> <span data-ttu-id="a1c3c-105">모임 참가자는 전화 장치를 사용 하 여 인터넷 연결이 제한 되어 있거나 사용자가 이동 중이 고 팀에 액세스할 수 없는 경우와 같은 시나리오에서 팀 모임에 참가 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-105">Meeting participants might prefer to use a phone device to join Teams meetings in scenarios such as when internet connectivity is limited or when users are on the road and don't have access to Teams.</span></span> <span data-ttu-id="a1c3c-106">참가자는 조직의 전화 접속 전화 번호로 전화를 걸고 전화 장치에 모임 전화를 걸도록 하 여 모임에 참가 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-106">Participants can choose to join meetings by either dialing in to a dial-in phone number for your organization or by having the meeting dial out to their phone device.</span></span>

<span data-ttu-id="a1c3c-107">GCC High 및 DoD에 대 한 직접 라우팅이 있는 오디오 회의를 사용 하는 경우 조직에서 전화 접속 전화 번호로 자체 번호를 사용 하 고 전화 장치에 대 한 모든 모임 전화 접속은 직접 라우팅을 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-107">With Audio Conferencing with Direct Routing for GCC High and DoD, your organization uses its own numbers as dial-in phone numbers and all meeting dial-outs to phone devices are routed via Direct Routing.</span></span> <span data-ttu-id="a1c3c-108">서비스를 사용 하도록 설정 하려면 조직에서 직접 라우팅과 전화 접속 전화 번호로 사용할 수 있는 전화 번호를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-108">To enable the service, organizations need to set up Direct Routing and configure phone numbers that can be used as dial-in phone numbers.</span></span> <span data-ttu-id="a1c3c-109">직접 라우팅을 사용 해야 하는 요구 사항은 Microsoft에서 전화 접속 전화 번호를 제공 하는 비 GCC 높음이나 비 DoD 조직에 제공 되는 오디오 회의 서비스와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-109">The requirement to use Direct Routing is different from the Audio Conferencing service that's offered to non-GCC High and non-DoD organizations where the dial-in phone numbers are provided by Microsoft.</span></span>

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="a1c3c-110">GCC High 및 DoD에 대 한 직접 라우팅을 사용 하 여 오디오 회의 배포</span><span class="sxs-lookup"><span data-stu-id="a1c3c-110">Deploy Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a><span data-ttu-id="a1c3c-111">1 단계: GCC High 또는 DoD 라이선스에 대 한 직접 라우팅이 있는 오디오 회의를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-111">Step 1: Get Audio Conferencing with Direct Routing for GCC High or DoD licenses</span></span> 

<span data-ttu-id="a1c3c-112">GCC High 또는 DoD에서 오디오 회의를 사용 하려면 조직 및 조직의 사용자가 직접 라우팅 라이선스를 할당 한 오디오 회의를 거쳐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-112">To use Audio Conferencing in GCC High or DoD, your organization and the users in your organization need to have an Audio Conferencing with Direct Routing license assigned.</span></span> <span data-ttu-id="a1c3c-113">다음은 GCC High 또는 DoD에 대 한 직접 라우팅이 오디오 회의를 사용 하도록 설정 하는 데 필요한 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-113">Here are the licenses you need to enable Audio Conferencing with Direct Routing for GCC High or DoD.</span></span>

- <span data-ttu-id="a1c3c-114">GCC 최고: 사용자의 조직 및 오디오 회의-gcc 상위 라이선스에 대 한 오디오 회의-GCC 고용량 테 넌 트 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-114">GCC High: An Audio Conferencing - GCC High Tenant license for your organization and Audio Conferencing - GCC High licenses for your users.</span></span>

- <span data-ttu-id="a1c3c-115">DoD: 조직 및 오디오 회의용 사용자의 DoD 라이선스에 대 한 오디오 회의-DoD 테 넌 트 라이선스</span><span class="sxs-lookup"><span data-stu-id="a1c3c-115">DoD: An Audio Conferencing - DoD Tenant license for your organization and Audio Conferencing - DoD licenses for your users.</span></span>

<span data-ttu-id="a1c3c-116">서비스를 사용 하도록 설정 하려면 테 넌 트 라이선스 및 하나 이상의 사용자 라이선스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-116">A tenant license and at least one user license are required to enable the service.</span></span> <span data-ttu-id="a1c3c-117">테 넌 트 라이선스 또는 사용자 라이선스만 사용 하 여 서비스를 사용 하도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-117">You can't enable the service with only the tenant license or with only user licenses.</span></span> <span data-ttu-id="a1c3c-118">테 넌 트 및 조직의 사용자에 대 한 서비스 라이선스를 가져오려면 계정 팀에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-118">To get service licenses for your tenant and the users in your organization, contact your account team.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a1c3c-119">전화 접속 전화 번호가 설정 될 때까지 직접 라우팅이 있는 오디오 회의는 사용자가 활성화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-119">Users can't be enabled for Audio Conferencing with Direct Routing until dial-in phone numbers are set up.</span></span> <span data-ttu-id="a1c3c-120">이 문서에 설명 된 대로 전화 접속 전화 번호를 설정할 때까지 사용자에 게 GCC High 또는 DoD 라이선스에 대 한 직접 라우팅이 있는 오디오 회의를 할당 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-120">We recommend that you not assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to users until you set up dial-in phone numbers as outlined in this article.</span></span>

### <a name="step-2-set-up-direct-routing"></a><span data-ttu-id="a1c3c-121">2 단계: 직접 라우팅 설정</span><span class="sxs-lookup"><span data-stu-id="a1c3c-121">Step 2: Set up Direct Routing</span></span>

<span data-ttu-id="a1c3c-122">직접 라우팅을 설정 하려면 다음 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-122">To set up Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="a1c3c-123">직접 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="a1c3c-123">Plan Direct Routing</span></span>](direct-routing-plan.md)

- [<span data-ttu-id="a1c3c-124">직접 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="a1c3c-124">Configure Direct Routing</span></span>](direct-routing-configure.md)

> [!NOTE]
> <span data-ttu-id="a1c3c-125">직접 라우팅을 설정할 때는이 두 문서에서 설명 하는 GCC High 또는 DoD 관련 Fqdn 및 포트를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-125">When you set up Direct Routing, remember to use the GCC High or DoD-specific FQDNs and ports that are described in these two articles.</span></span>

### <a name="step-3-set-up-dial-in-phone-numbers"></a><span data-ttu-id="a1c3c-126">3 단계: 전화 접속 전화 번호 설정</span><span class="sxs-lookup"><span data-stu-id="a1c3c-126">Step 3: Set up dial-in phone numbers</span></span>

<span data-ttu-id="a1c3c-127">전화 접속 전화 번호는 오디오 회의 브리지에 연결 된 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-127">Dial-in phone numbers are the phone numbers that are associated to your Audio Conferencing bridge.</span></span> <span data-ttu-id="a1c3c-128">이러한 번호는 참가자가 조직의 사용자가 예약한 모임에 참가 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-128">These numbers are used by participants to join meetings scheduled by users in your organization.</span></span> <span data-ttu-id="a1c3c-129">이러한 번호는 조직의 모임을 예약 하는 사용자와 "로컬 번호 찾기" 페이지의 모임 초대에도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-129">These numbers are also included in the meeting invites of the users who schedule meetings in your organization and on the "Find a local number" page.</span></span>

#### <a name="define-service-phone-numbers-in-your-tenant"></a><span data-ttu-id="a1c3c-130">테 넌 트에서 서비스 전화 번호 정의</span><span class="sxs-lookup"><span data-stu-id="a1c3c-130">Define service phone numbers in your tenant</span></span>

<span data-ttu-id="a1c3c-131">CsHybridTelephoneNumber PowerShell cmdlet을 사용 하 여 테 넌 트에서 직접 라우팅을 통해 오디오 회의 서비스에 대 한 통화를 라우팅하는 데 사용할 수 있는 서비스 전화 번호를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-131">You can use the New-csHybridTelephoneNumber PowerShell cmdlet to define service phone numbers in your tenant that can be used to route calls to the Audio Conferencing service via Direct Routing.</span></span> 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

<span data-ttu-id="a1c3c-132">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-132">For example:</span></span>
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="a1c3c-133">조직의 오디오 회의 브리지에 서비스 전화 번호 할당</span><span class="sxs-lookup"><span data-stu-id="a1c3c-133">Assign the service phone numbers to the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="a1c3c-134">CsOnlineDialInConferencingServiceNumber PowerShell cmdlet을 사용 하 여 조직의 오디오 회의 브리지에 서비스 전화 번호를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-134">You can assign service phone numbers to the Audio Conferencing bridge of your organization by using the Register-csOnlineDialInConferencingServiceNumber PowerShell cmdlet.</span></span>

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

<span data-ttu-id="a1c3c-135">CsOnlineDialInConferencingBridge를 사용 하 여 오디오 회의 브리지의 ID를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-135">You can see the ID of your Audio Conferencing Bridge using Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="a1c3c-136">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-136">For example:</span></span>

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a><span data-ttu-id="a1c3c-137">4 단계: 모임에서 나가는 호출을 라우팅할 수 있도록 하는 전역 음성 라우팅 정책 정의</span><span class="sxs-lookup"><span data-stu-id="a1c3c-137">Step 4: Define a global voice routing policy to enable the routing of outbound calls from meetings</span></span>

<span data-ttu-id="a1c3c-138">조직의 사용자가 구성한 모임에서 PSTN에 대 한 아웃 바운드 통화 라우팅은 조직의 전역 음성 라우팅 정책에 의해 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-138">The routing of outbound calls that are made to the PSTN from meetings organized by users in your organization is defined by the global voice routing policy of your organization.</span></span> <span data-ttu-id="a1c3c-139">조직에 전역 음성 라우팅 정책이 정의 되어 있는 경우 전역 음성 라우팅 정책이 조직의 사용자가 구성한 모임에서 시작 될 것으로 예상 되는 PSTN에 대 한 아웃 바운드 호출을 허용 하는지 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-139">If your organization has a global voice routing policy defined, please verify that the global voice routing policy allows the outbound calls to the PSTN that are expected to be initiated from meetings organized by users in your organization.</span></span> <span data-ttu-id="a1c3c-140">조직에 전역 음성 라우팅 정책이 정의 되어 있지 않은 경우 조직의 사용자가 구성한 모임에서 PSTN으로의 아웃 바운드 호출 라우팅이 가능 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-140">If your organization doesn’t have a global voice routing policy defined, you will need to define one to enable the routing of outbound calls to the PSTN from meetings organized by users in your organization.</span></span> <span data-ttu-id="a1c3c-141">조직의 글로벌 음성 라우팅 정책은 조직의 사용자가 PSTN으로 하는 일대일 통화에도 적용 된다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-141">Please note that the global voice routing policy of your organization also applies to one-to-one calls made to the PSTN by users in your organization.</span></span> <span data-ttu-id="a1c3c-142">조직의 사용자가 PSTN에 대 한 일대일 통화를 사용할 수 있도록 설정 되어 있는 경우 전역 음성 라우팅 정책이 두 가지 유형의 호출에 대해 조직의 요구 사항을 충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-142">If one-to-one calls to the PSTN are enabled for users in your organization, make sure that the global voice routing policy meets the needs of your organization for both types of calls.</span></span> 

> [!NOTE]
> <span data-ttu-id="a1c3c-143">Microsoft 365 정부 커뮤니티 클라우드 (GCC) 높음 또는 DoD 배포에서는 위치 기반 라우팅을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-143">Location-Based Routing isn't available in Microsoft 365 Government Community Cloud (GCC) High or DoD deployments.</span></span> <span data-ttu-id="a1c3c-144">오디오 회의를 사용 하도록 설정 하는 경우 GCC 상위 또는 DoD 환경에서 오디오 회의 사용자가 위치 기반 라우팅에 대해 사용 하도록 설정 되어 있지 않은지 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-144">When enabling Audio Conferencing, please verify that no Audio Conferencing users in the GCC High or the DoD environments are enabled for Location-Based Routing.</span></span>

#### <a name="defining-a-global-voice-routing-policy"></a><span data-ttu-id="a1c3c-145">전역 음성 라우팅 정책 정의</span><span class="sxs-lookup"><span data-stu-id="a1c3c-145">Defining a global voice routing policy</span></span>

<span data-ttu-id="a1c3c-146">전역 음성 라우팅 정책은 PSTN 사용, 음성 경로, 음성 라우팅 정책, 새로운 음성 라우팅 정책을 조직의 전역 음성 라우팅 정책으로 할당 하 여 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-146">A global voice routing policy can be defined by defining a PSTN usage, a voice route, a voice routing policy, and assigning the new voice routing policy as the global voice routing policy of your organization.</span></span>

<span data-ttu-id="a1c3c-147">다음 단계에서는 조직을 사용 하지 않고 새 전역 음성 라우팅 정책을 정의 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-147">The following steps describe how to define a new global voice routing policy for an organization without one.</span></span> <span data-ttu-id="a1c3c-148">조직에 이미 음성 라우팅 정책이 정의 되어 있는 경우 다음 구성이 조직의 기존 음성 라우팅 정책과 충돌 하지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-148">If your organization already has voice routing policies defined, verify that the following configuration doesn’t conflict with the existing voice routing policies of your organization.</span></span>

<span data-ttu-id="a1c3c-149">비즈니스용 Skype Online에서 원격 PowerShell 세션에 새 PSTN 사용량을 만들려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-149">To create a new PSTN usage in a remote PowerShell session in Skype for Business Online, use the following command:</span></span>

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

<span data-ttu-id="a1c3c-150">자세한 내용은 [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-150">For additional information, see [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage).</span></span>

<span data-ttu-id="a1c3c-151">새 음성 경로를 만들려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-151">To create a new voice route, use the following command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

<span data-ttu-id="a1c3c-152">조직의 새 음성 경로를 정의할 때 직접 라우팅을 구성 하는 동안 조직에 대해 정의 된 PSTN 온라인 PSTN 게이트웨이의 하나 또는 여러 개를 지정 하세요.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-152">When defining a new voice route for your organization, please specify one or multiple of the PSTN online PSTN gateways that have been defined for your organization during the configuration of Direct Routing.</span></span> 

<span data-ttu-id="a1c3c-153">숫자 패턴은 통화의 대상 전화 번호를 기준으로 지정 된 게이트웨이 목록을 통해 라우팅되는 호출을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-153">The number pattern specifies which calls will be routed through the specified list of gateways based on the destination phone number of the call.</span></span> <span data-ttu-id="a1c3c-154">위 예제에서 전 세계의 모든 목적지로 거는 호출은 음성 경로와 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-154">In the example above, calls to any destinations in the world will match the voice route.</span></span> <span data-ttu-id="a1c3c-155">조직의 사용자 모임에서 전화를 걸 수 있는 전화 번호를 제한 하려면 번호 패턴을 변경 하 여 허용 되는 대상의 숫자 패턴에만 음성 경로가 일치 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-155">If you would like to restrict the phone numbers that can be dialed from the meetings of users in your organization, you can change the number pattern to have the voice route match only the number patterns of the destinations allowed.</span></span> <span data-ttu-id="a1c3c-156">지정 된 통화에 대 한 대상 전화 번호 패턴과 일치 하는 음성 경로가 없는 경우 통화는 라우팅되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-156">Please note that if there are no voice routes that match the number pattern of the destination phone number of a given call, the call will not be routed.</span></span>

<span data-ttu-id="a1c3c-157">자세한 내용은 [New-CsOnlineVoiceRoute](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroute)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-157">For additional information, see [New-CsOnlineVoiceRoute](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroute).</span></span>

<span data-ttu-id="a1c3c-158">새 음성 라우팅 정책을 만들려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-158">To create a new voice routing policy, use the following command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

<span data-ttu-id="a1c3c-159">음성 라우팅 정책에 여러 PSTN 사용을 정의 하는 경우 해당 사용자는 정의 된 순서 대로 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-159">If multiple PSTN usages are being defined in the voice routing policy, they will be evaluated in the order in which they are defined.</span></span> <span data-ttu-id="a1c3c-160">Pstn 용도는 PSTN 사용과 연결 된 음성 경로의 숫자 패턴 측면에서 일반적인 항목의 순서에 따라 정의 되는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-160">It is recommended that the PSTN usages are defined in the order of the most specific to the more generic in terms of the number patterns of the voice routes associated with the PSTN usages.</span></span> <span data-ttu-id="a1c3c-161">예를 들어 미국에 대 한 라우팅 통화를 위해 PSTN 사용이 정의 되었고 다른 PSTN 사용이 전세계 다른 위치로 호출 하도록 정의 되어 있는 경우 미국에 대 한 호출에 대 한 PSTN 사용이 PSTN 사용 앞의 음성 라우팅 정책에 나열 되어 전세계 다른 위치로 통화를 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-161">For example, if a PSTN usage was defined to route calls to the United States, and another PSTN usage was defined to route calls to any other location in the world, the PSTN usage for calls to the United States should be listed in the voice routing policy ahead of the PSTN usage to route calls to any other location in the world.</span></span>

<span data-ttu-id="a1c3c-162">자세한 내용은 [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-162">For additional information, see [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

<span data-ttu-id="a1c3c-163">조직의 전역 음성 라우팅 정책에 새 음성 경로를 할당 하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-163">To assign the new voice route to the global voice routing policy of your organization, use the following command:</span></span>

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

<span data-ttu-id="a1c3c-164">자세한 내용은 [허용-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-164">For additional information, see [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

<span data-ttu-id="a1c3c-165">전역 음성 라우팅 정책이 정의 되 면 조직의 사용자가 구성한 모임에서 발생 한 모든 아웃 바운드 호출은 전역 음성 라우팅 정책의 PSTN 사용에 연결 된 음성 경로에 대해 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-165">Once the global voice routing policy has been defined, any outbound calls made from meetings organized by users in your organization will be evaluated against the voice routes associated to the PSTN usages of the global voice routing policy.</span></span> <span data-ttu-id="a1c3c-166">발신 전화 번호의 번호 패턴과 일치 하는 첫 번째 음성 경로에 따라 수신 통화가 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-166">The outbound calls will be routed according to the first voice route that matches the number pattern of the dialed phone number.</span></span>

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a><span data-ttu-id="a1c3c-167">5 단계: 사용자에 게 GCC High 또는 DoD 라이선스에 대 한 직접 라우팅이 있는 오디오 회의 할당</span><span class="sxs-lookup"><span data-stu-id="a1c3c-167">Step 5: Assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your users</span></span>

<span data-ttu-id="a1c3c-168">사용자에 게 GCC High 또는 DoD 라이선스에 대 한 직접 라우팅이 있는 오디오 회의를 할당 하려면 [사용자에 게 라이선스 할당](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-168">To assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your user, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a><span data-ttu-id="a1c3c-169">6 단계: (선택 사항) 팀의 오디오 회의 번호 목록 보기</span><span class="sxs-lookup"><span data-stu-id="a1c3c-169">Step 6: (Optional) See a list of Audio Conferencing numbers in Teams</span></span>

<span data-ttu-id="a1c3c-170">조직의 오디오 회의 번호 목록을 보려면 [Microsoft 팀의 오디오 회의 번호 목록 보기를 참조](see-a-list-of-audio-conferencing-numbers-in-teams.md)하세요.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-170">To see the list of Audio Conferencing numbers of your organization, go to [See a list of Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a><span data-ttu-id="a1c3c-171">7 단계: (선택 사항) 사용자 조직의 오디오 회의 전화 접속 번호에 대 한 자동 전화 교환 언어 설정</span><span class="sxs-lookup"><span data-stu-id="a1c3c-171">Step 7: (Optional) Set auto attendant languages for the Audio Conferencing dial-in numbers of you organization</span></span>

<span data-ttu-id="a1c3c-172">조직의 오디오 회의 전화 접속 번호 언어를 변경 하려면 [Microsoft 팀에서 오디오 회의를 위한 자동 전화 교환 언어 설정을](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-172">To change the languages of the Audio Conferencing dial-in numbers of your organization, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="a1c3c-173">8 단계: (선택 사항) 조직의 오디오 회의 브리지에 대 한 설정 변경</span><span class="sxs-lookup"><span data-stu-id="a1c3c-173">Step 8: (Optional) Change the settings of the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="a1c3c-174">조직의 오디오 회의 브리지 설정을 변경 하려면 [오디오 회의 브리지에 대 한 설정 변경을](change-the-settings-for-an-audio-conferencing-bridge.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-174">To change the settings of the Audio Conferencing bridge of your organization, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a><span data-ttu-id="a1c3c-175">9 단계: (선택 사항) 조직의 사용자에 대 한 모임 초대에 포함 된 전화 번호 설정</span><span class="sxs-lookup"><span data-stu-id="a1c3c-175">Step 9: (Optional) Set the phone numbers included in the meeting invites of the users in your organization</span></span>

<span data-ttu-id="a1c3c-176">사용자의 모임 초대에 포함 된 전화 번호 집합을 변경 하려면 [Microsoft 팀의 초대에 포함 된 전화 번호 설정을](set-the-phone-numbers-included-on-invites-in-teams.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-176">To change the set of phone numbers that are included in the meeting invites of the users is your organization, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="a1c3c-177">GCC High 및 DoD에 대 한 직접 라우팅이 있는 오디오 회의에서는 오디오 회의 기능이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-177">Audio Conferencing capabilities not supported in Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="a1c3c-178">다음은 GCC High 및 DoD에 대 한 직접 라우팅이 오디오 회의에서 지원 되지 않는 오디오 회의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-178">The following are Audio Conferencing capabilities that are not supported in Audio Conferencing with Direct Routing for GCC High and DoD:</span></span>

- <span data-ttu-id="a1c3c-179">이름 기록을 사용 하 여 입력 및 종료 알림</span><span class="sxs-lookup"><span data-stu-id="a1c3c-179">Entry and exit notifications using name recording.</span></span> <span data-ttu-id="a1c3c-180">직접 라우팅이 있는 오디오 회의의 경우 입력 및 종료 알림이 모임에서 톤으로 재생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-180">For Audio Conferencing with Direct Routing, entry and exit notifications are played in the meeting as tones.</span></span>

- <span data-ttu-id="a1c3c-181">오디오 회의에 대 한 아웃 바운드 통화 제한 정책</span><span class="sxs-lookup"><span data-stu-id="a1c3c-181">Outbound calling restriction policies for Audio Conferencing.</span></span> <span data-ttu-id="a1c3c-182">아웃 바운드 통화를 제한 하는 사용자 수준 컨트롤은 직접 라우팅을 통해 라우팅되는 모임 전화 접속 통화에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-182">User-level controls to restrict outbound calls aren't applicable to meeting dial-out calls routed via Direct Routing.</span></span>

- <span data-ttu-id="a1c3c-183">특정 모임 이끌이가 사용할 수 있는 무료 전화 번호를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-183">Disable the usage of toll-free numbers for the meetings specific organizer.</span></span> <span data-ttu-id="a1c3c-184">무료 번호 사용을 조직의 모임에 참가 하도록 제한 하는 사용자 수준 컨트롤은 직접 라우팅을 통해 라우팅되는 통화에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-184">User-level controls to restrict the usage of toll-free numbers to join the meetings of your organization aren't applicable to calls routed via Direct Routing.</span></span>

- <span data-ttu-id="a1c3c-185">설정이 변경 될 때 알림 전자 메일을 사용자에 게 보내기</span><span class="sxs-lookup"><span data-stu-id="a1c3c-185">Sending notification emails to users when their settings change.</span></span> <span data-ttu-id="a1c3c-186">오디오 회의 알림 전자 메일은 GCC High 및 DoD에 대 한 직접 라우팅이 있는 오디오 회의에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c3c-186">Audio Conferencing notification emails aren't supported for Audio Conferencing with Direct Routing for GCC High and DoD.</span></span>
