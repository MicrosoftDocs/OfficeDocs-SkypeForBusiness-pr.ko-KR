---
title: 직접 라우팅, GCCH 및 DoD를 통해 오디오 회의
author: cichur
ms.author: v-cichur
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
description: 관리자는 GCCH 및 DoD 환경에서 직접 라우팅을 사용하여 오디오 회의를 사용하는 방법에 대해 배울 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4daea8636ce99ed711d7fd982cd42eb9aa8c6b93
ms.sourcegitcommit: b39bd1de0219a9e3a3b0c97fc485c9578ddb643c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2021
ms.locfileid: "53230585"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="a59c4-103">GCC High 및 DoD를 위해 직접 라우팅으로 오디오 회의</span><span class="sxs-lookup"><span data-stu-id="a59c4-103">Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="a59c4-104">High 및 DoD에 대한 직접 라우팅을 사용하는 오디오 회의를 통해 GCC 디바이스를 사용하여 참가자가 Teams 또는 DoD 조직에서 GCC 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-104">Audio Conferencing with Direct Routing for GCC High and DoD enables participants to join Teams meetings in your GCC High or DoD organization by using a phone device.</span></span> <span data-ttu-id="a59c4-105">모임 참가자는 전화 장치를 사용하여 인터넷 연결이 제한되거나 사용자가 도로에 Teams 액세스 권한이 없는 경우와 같은 시나리오에서 Teams.</span><span class="sxs-lookup"><span data-stu-id="a59c4-105">Meeting participants might prefer to use a phone device to join Teams meetings in scenarios such as when internet connectivity is limited or when users are on the road and don't have access to Teams.</span></span> <span data-ttu-id="a59c4-106">참가자는 조직의 전화 접속 전화 번호에 전화를 걸거나 모임이 휴대폰 디바이스에 전화 접속하여 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-106">Participants can choose to join meetings by either dialing in to a dial-in phone number for your organization or by having the meeting dial out to their phone device.</span></span>

<span data-ttu-id="a59c4-107">High 및 DoD에 대한 직접 라우팅을 사용하는 오디오 회의를 사용하여 조직에서 자체 GCC 전화 접속 전화 번호로 사용하며 전화 디바이스에 대한 모든 모임 전화 접속은 직접 라우팅을 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-107">With Audio Conferencing with Direct Routing for GCC High and DoD, your organization uses its own numbers as dial-in phone numbers and all meeting dial-outs to phone devices are routed via Direct Routing.</span></span> <span data-ttu-id="a59c4-108">서비스를 사용하도록 설정하려면 조직에서 직접 라우팅을 설정하고 전화 접속 전화 번호로 사용할 수 있는 전화 번호를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-108">To enable the service, organizations need to set up Direct Routing and configure phone numbers that can be used as dial-in phone numbers.</span></span> <span data-ttu-id="a59c4-109">직접 라우팅을 사용해야 하는 요구 사항은 Microsoft에서 전화 접속 전화 번호를 제공하는 비도우급 높음 및 비도드 조직에 제공되는 GCC 오디오 회의 서비스와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-109">The requirement to use Direct Routing is different from the Audio Conferencing service that's offered to non-GCC High and non-DoD organizations where the dial-in phone numbers are provided by Microsoft.</span></span>

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="a59c4-110">High 및 DoD에 대한 직접 라우팅을 GCC 오디오 회의 배포</span><span class="sxs-lookup"><span data-stu-id="a59c4-110">Deploy Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a><span data-ttu-id="a59c4-111">1단계: 하이 또는 DoD 라이선스에 대한 직접 라우팅을 GCC 오디오 회의하기</span><span class="sxs-lookup"><span data-stu-id="a59c4-111">Step 1: Get Audio Conferencing with Direct Routing for GCC High or DoD licenses</span></span> 

<span data-ttu-id="a59c4-112">높음 GCC 또는 doD에서 오디오 회의를 사용하려면 조직 및 조직의 사용자가 직접 라우팅 라이선스가 할당된 오디오 회의를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-112">To use Audio Conferencing in GCC High or DoD, your organization and the users in your organization need to have an Audio Conferencing with Direct Routing license assigned.</span></span> <span data-ttu-id="a59c4-113">다음은 하이 또는 DoD에 대한 직접 라우팅을 사용하여 오디오 회의를 사용하도록 설정하는 데 GCC 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-113">Here are the licenses you need to enable Audio Conferencing with Direct Routing for GCC High or DoD.</span></span>

- <span data-ttu-id="a59c4-114">GCC 높음: 오디오 회의 - GCC 높은 테넌트 라이선스 및 오디오 회의에 대한 높은 테넌트 라이선스 - GCC 높은 라이선스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-114">GCC High: An Audio Conferencing - GCC High Tenant license for your organization and Audio Conferencing - GCC High licenses for your users.</span></span>

- <span data-ttu-id="a59c4-115">DoD: 오디오 회의 - 조직 및 오디오 회의에 대한 DoD 테넌트 라이선스 - 사용자에 대한 DoD 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-115">DoD: An Audio Conferencing - DoD Tenant license for your organization and Audio Conferencing - DoD licenses for your users.</span></span>

<span data-ttu-id="a59c4-116">서비스를 사용하도록 설정하려면 테넌트 라이선스 및 하나 이상의 사용자 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-116">A tenant license and at least one user license are required to enable the service.</span></span> <span data-ttu-id="a59c4-117">테넌트 라이선스 또는 사용자 라이선스만 사용하여 서비스를 사용하도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-117">You can't enable the service with only the tenant license or with only user licenses.</span></span> <span data-ttu-id="a59c4-118">테넌트 및 조직의 사용자에 대한 서비스 라이선스를 얻하려면 계정 팀에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="a59c4-118">To get service licenses for your tenant and the users in your organization, contact your account team.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a59c4-119">전화 접속 전화 번호가 설정될 때까지 직접 라우팅을 사용하여 오디오 회의를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-119">Users can't be enabled for Audio Conferencing with Direct Routing until dial-in phone numbers are set up.</span></span> <span data-ttu-id="a59c4-120">이 문서에 설명된 GCC 전화 접속 전화 번호를 설정하기 전까지는 하이 또는 DoD 라이선스에 대한 직접 라우팅을 사용하여 오디오 회의를 할당하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-120">We recommend that you do not assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to users until you set up dial-in phone numbers as outlined in this article.</span></span>  <span data-ttu-id="a59c4-121">이 지침을 따르지 않을 경우 클라이언트에서 다이얼 패드가 Teams 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-121">Failure to follow this guidance may cause the dial pad to be completely missing in the Teams client.</span></span>

### <a name="step-2-set-up-direct-routing"></a><span data-ttu-id="a59c4-122">2단계: 직접 라우팅 설정</span><span class="sxs-lookup"><span data-stu-id="a59c4-122">Step 2: Set up Direct Routing</span></span>

<span data-ttu-id="a59c4-123">직접 라우팅을 설정하는 경우 다음 문서를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-123">To set up Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="a59c4-124">직접 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="a59c4-124">Plan Direct Routing</span></span>](direct-routing-plan.md)

- [<span data-ttu-id="a59c4-125">직접 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="a59c4-125">Configure Direct Routing</span></span>](direct-routing-configure.md)

> [!NOTE]
> <span data-ttu-id="a59c4-126">직접 라우팅을 설정할 때 다음 두 문서에 설명된 GCC 높은 또는 DoD 관련 FQDNs 및 포트를 사용하는 것이 잊지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-126">When you set up Direct Routing, remember to use the GCC High or DoD-specific FQDNs and ports that are described in these two articles.</span></span>

### <a name="step-3-set-up-dial-in-phone-numbers"></a><span data-ttu-id="a59c4-127">3단계: 전화 접속 전화 번호 설정</span><span class="sxs-lookup"><span data-stu-id="a59c4-127">Step 3: Set up dial-in phone numbers</span></span>

<span data-ttu-id="a59c4-128">전화 접속 전화 번호는 오디오 회의 브리지에 연결된 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-128">Dial-in phone numbers are the phone numbers that are associated to your Audio Conferencing bridge.</span></span> <span data-ttu-id="a59c4-129">이러한 숫자는 참가자가 조직의 사용자가 예약한 모임에 참가하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-129">These numbers are used by participants to join meetings scheduled by users in your organization.</span></span> <span data-ttu-id="a59c4-130">이러한 번호는 조직의 모임을 예약하는 사용자의 모임 초대 및 "로컬 번호 찾기" 페이지에도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-130">These numbers are also included in the meeting invites of the users who schedule meetings in your organization and on the "Find a local number" page.</span></span>

#### <a name="define-service-phone-numbers-in-your-tenant"></a><span data-ttu-id="a59c4-131">테넌트에서 서비스 전화 번호 정의</span><span class="sxs-lookup"><span data-stu-id="a59c4-131">Define service phone numbers in your tenant</span></span>

<span data-ttu-id="a59c4-132">New-csHybridTelephoneNumber PowerShell cmdlet을 사용하여 직접 라우팅을 통해 오디오 회의 서비스에 대한 호출을 라우팅하는 데 사용할 수 있는 테넌트에서 서비스 전화 번호를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-132">You can use the New-csHybridTelephoneNumber PowerShell cmdlet to define service phone numbers in your tenant that can be used to route calls to the Audio Conferencing service via Direct Routing.</span></span> 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

<span data-ttu-id="a59c4-133">예제:</span><span class="sxs-lookup"><span data-stu-id="a59c4-133">For example:</span></span>
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="a59c4-134">조직의 오디오 회의 브리지에 서비스 전화 번호 할당</span><span class="sxs-lookup"><span data-stu-id="a59c4-134">Assign the service phone numbers to the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="a59c4-135">Register-csOnlineDialInConferencingServiceNumber PowerShell cmdlet을 사용하여 조직의 오디오 회의 브리지에 서비스 전화 번호를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-135">You can assign service phone numbers to the Audio Conferencing bridge of your organization by using the Register-csOnlineDialInConferencingServiceNumber PowerShell cmdlet.</span></span>

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

<span data-ttu-id="a59c4-136">Get-CsOnlineDialInConferencingBridge를 사용하여 오디오 회의 브리지의 ID를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-136">You can see the ID of your Audio Conferencing Bridge using Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="a59c4-137">예제:</span><span class="sxs-lookup"><span data-stu-id="a59c4-137">For example:</span></span>

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a><span data-ttu-id="a59c4-138">4단계: 모임에서 아웃바운드 호출 라우팅을 사용하도록 전역 음성 라우팅 정책 정의</span><span class="sxs-lookup"><span data-stu-id="a59c4-138">Step 4: Define a global voice routing policy to enable the routing of outbound calls from meetings</span></span>

<span data-ttu-id="a59c4-139">조직의 사용자가 구성한 모임에서 PSTN에 대한 아웃바운드 호출 라우팅은 조직의 글로벌 음성 라우팅 정책에 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-139">The routing of outbound calls that are made to the PSTN from meetings organized by users in your organization is defined by the global voice routing policy of your organization.</span></span> <span data-ttu-id="a59c4-140">조직에 글로벌 음성 라우팅 정책이 정의되어 있는 경우 글로벌 음성 라우팅 정책이 조직의 사용자가 조직한 모임에서 시작될 것으로 예상되는 PSTN에 대한 아웃바운드 호출을 허용하는지 확인하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-140">If your organization has a global voice routing policy defined, please verify that the global voice routing policy allows the outbound calls to the PSTN that are expected to be initiated from meetings organized by users in your organization.</span></span> <span data-ttu-id="a59c4-141">조직에 글로벌 음성 라우팅 정책이 정의되지 않은 경우 조직의 사용자가 구성한 모임에서 PSTN에 대한 아웃바운드 호출의 라우팅을 사용하도록 설정하도록 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-141">If your organization doesn’t have a global voice routing policy defined, you will need to define one to enable the routing of outbound calls to the PSTN from meetings organized by users in your organization.</span></span> <span data-ttu-id="a59c4-142">조직의 글로벌 음성 라우팅 정책은 조직의 사용자가 PSTN에 대한 일대일 통화에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-142">Please note that the global voice routing policy of your organization also applies to one-to-one calls made to the PSTN by users in your organization.</span></span> <span data-ttu-id="a59c4-143">조직의 사용자가 PSTN에 대한 일대일 호출을 사용하도록 설정되어 있는 경우 글로벌 음성 라우팅 정책이 두 유형의 호출에 대한 조직의 요구 사항을 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-143">If one-to-one calls to the PSTN are enabled for users in your organization, make sure that the global voice routing policy meets the needs of your organization for both types of calls.</span></span> 

> [!NOTE]
> <span data-ttu-id="a59c4-144">Location-Based(Microsoft 365 정부 커뮤니티 클라우드) 높거나 DoD 배포에서 Microsoft 365 정부 커뮤니티 클라우드(GCC) 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-144">Location-Based Routing isn't available in Microsoft 365 Government Community Cloud (GCC) High or DoD deployments.</span></span> <span data-ttu-id="a59c4-145">오디오 회의를 사용하도록 설정하는 경우 하이 또는 DoD 환경의 오디오 회의 사용자가 GCC 라우팅에 사용하도록 설정되어 Location-Based 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-145">When enabling Audio Conferencing, please verify that no Audio Conferencing users in the GCC High or the DoD environments are enabled for Location-Based Routing.</span></span>

#### <a name="defining-a-global-voice-routing-policy"></a><span data-ttu-id="a59c4-146">글로벌 음성 라우팅 정책 정의</span><span class="sxs-lookup"><span data-stu-id="a59c4-146">Defining a global voice routing policy</span></span>

<span data-ttu-id="a59c4-147">글로벌 음성 라우팅 정책은 PSTN 사용량, 음성 경로, 음성 라우팅 정책을 정의하고 조직의 글로벌 음성 라우팅 정책으로 새 음성 라우팅 정책을 할당하여 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-147">A global voice routing policy can be defined by defining a PSTN usage, a voice route, a voice routing policy, and assigning the new voice routing policy as the global voice routing policy of your organization.</span></span>

<span data-ttu-id="a59c4-148">다음 단계에서는 하나 없이 조직에 대한 새 전역 음성 라우팅 정책을 정의하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-148">The following steps describe how to define a new global voice routing policy for an organization without one.</span></span> <span data-ttu-id="a59c4-149">조직에 이미 음성 라우팅 정책이 정의되어 있는 경우 다음 구성이 조직의 기존 음성 라우팅 정책과 충돌하지 않는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-149">If your organization already has voice routing policies defined, verify that the following configuration doesn’t conflict with the existing voice routing policies of your organization.</span></span>

<span data-ttu-id="a59c4-150">온라인에서 원격 PowerShell 세션에서 새 PSTN 비즈니스용 Skype 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-150">To create a new PSTN usage in a remote PowerShell session in Skype for Business Online, use the following command:</span></span>

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

<span data-ttu-id="a59c4-151">자세한 내용은 [Set-CsOnlinePstnUsage 를 참조하세요.](/powershell/module/skype/set-csonlinepstnusage)</span><span class="sxs-lookup"><span data-stu-id="a59c4-151">For additional information, see [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage).</span></span>

<span data-ttu-id="a59c4-152">새 음성 경로를 만들 경우 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-152">To create a new voice route, use the following command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

<span data-ttu-id="a59c4-153">조직에 대한 새 음성 경로를 정의할 때 직접 라우팅 구성 중에 조직에 대해 정의된 PSTN 온라인 PSTN 게이트웨이 중 하나 또는 여러 개를 지정하세요.</span><span class="sxs-lookup"><span data-stu-id="a59c4-153">When defining a new voice route for your organization, please specify one or multiple of the PSTN online PSTN gateways that have been defined for your organization during the configuration of Direct Routing.</span></span> 

<span data-ttu-id="a59c4-154">번호 패턴은 호출의 대상 전화 번호를 기반으로 지정된 게이트웨이 목록을 통해 라우팅될 호출을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-154">The number pattern specifies which calls will be routed through the specified list of gateways based on the destination phone number of the call.</span></span> <span data-ttu-id="a59c4-155">위의 예제에서는 전 세계 모든 대상에 대한 호출이 음성 경로와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-155">In the example above, calls to any destinations in the world will match the voice route.</span></span> <span data-ttu-id="a59c4-156">조직의 사용자 모임에서 전화를 걸 수 있는 전화 번호를 제한하고자 하는 경우 음성 경로가 허용되는 대상의 숫자 패턴만 일치하도록 번호 패턴을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-156">If you would like to restrict the phone numbers that can be dialed from the meetings of users in your organization, you can change the number pattern to have the voice route match only the number patterns of the destinations allowed.</span></span> <span data-ttu-id="a59c4-157">특정 통화의 대상 전화 번호의 번호 패턴과 일치하는 음성 경로가 없는 경우 통화가 라우팅되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-157">Please note that if there are no voice routes that match the number pattern of the destination phone number of a given call, the call will not be routed.</span></span>

<span data-ttu-id="a59c4-158">자세한 내용은 [New-CsOnlineVoiceRoute 를 참조하세요.](/powershell/module/skype/new-csonlinevoiceroute)</span><span class="sxs-lookup"><span data-stu-id="a59c4-158">For additional information, see [New-CsOnlineVoiceRoute](/powershell/module/skype/new-csonlinevoiceroute).</span></span>

<span data-ttu-id="a59c4-159">새 음성 라우팅 정책을 만들 경우 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-159">To create a new voice routing policy, use the following command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

<span data-ttu-id="a59c4-160">음성 라우팅 정책에서 여러 PSTN 사용량을 정의하는 경우 정의되는 순서대로 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-160">If multiple PSTN usages are being defined in the voice routing policy, they will be evaluated in the order in which they are defined.</span></span> <span data-ttu-id="a59c4-161">PSTN 사용량은 PSTN 사용과 연결된 음성 경로의 숫자 패턴 측면에서 가장 일반적인 순서로 정의하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-161">It is recommended that the PSTN usages are defined in the order of the most specific to the more generic in terms of the number patterns of the voice routes associated with the PSTN usages.</span></span> <span data-ttu-id="a59c4-162">예를 들어 미국으로의 호출을 라우팅하기 위해 PSTN 사용량이 정의되고 다른 PSTN 사용량이 전 세계의 다른 위치로 호출을 라우팅하기 위해 정의된 경우 미국에 대한 호출에 대한 PSTN 사용량은 전 세계의 다른 위치로 호출을 라우팅하기 위해 PSTN 사용 앞의 음성 라우팅 정책에 나열해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-162">For example, if a PSTN usage was defined to route calls to the United States, and another PSTN usage was defined to route calls to any other location in the world, the PSTN usage for calls to the United States should be listed in the voice routing policy ahead of the PSTN usage to route calls to any other location in the world.</span></span>

<span data-ttu-id="a59c4-163">자세한 내용은 [New-CsOnlineVoiceRoutingPolicy 를 참조하세요.](/powershell/module/skype/new-csonlinevoiceroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="a59c4-163">For additional information, see [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

<span data-ttu-id="a59c4-164">조직의 글로벌 음성 라우팅 정책에 새 음성 경로를 할당하기 위해 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-164">To assign the new voice route to the global voice routing policy of your organization, use the following command:</span></span>

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

<span data-ttu-id="a59c4-165">자세한 내용은 [Grant-CsOnlineVoiceRoutingPolicy 를 참조하세요.](/powershell/module/skype/grant-csonlinevoiceroutingpolicy)</span><span class="sxs-lookup"><span data-stu-id="a59c4-165">For additional information, see [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

<span data-ttu-id="a59c4-166">글로벌 음성 라우팅 정책이 정의된 후 조직의 사용자가 구성한 모임에서 만든 아웃바운드 호출은 글로벌 음성 라우팅 정책의 PSTN 사용과 연결된 음성 경로에 대해 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-166">Once the global voice routing policy has been defined, any outbound calls made from meetings organized by users in your organization will be evaluated against the voice routes associated to the PSTN usages of the global voice routing policy.</span></span> <span data-ttu-id="a59c4-167">아웃바운드 호출은 전화 걸기 전화 번호의 번호 패턴과 일치하는 첫 번째 음성 경로에 따라 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-167">The outbound calls will be routed according to the first voice route that matches the number pattern of the dialed phone number.</span></span>

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a><span data-ttu-id="a59c4-168">5단계: 사용자에게 높은 또는 DoD 라이선스에 대한 직접 라우팅을 GCC 오디오 회의 할당</span><span class="sxs-lookup"><span data-stu-id="a59c4-168">Step 5: Assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your users</span></span>

<span data-ttu-id="a59c4-169">사용자에 대한 직접 라우팅을 통해 오디오 회의를 GCC 또는 DoD 라이선스를 사용자에게 할당하는 경우 사용자에게 라이선스 할당을 [참조합니다.](/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="a59c4-169">To assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your user, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a><span data-ttu-id="a59c4-170">6단계: (선택 사항) 오디오 회의 번호 목록을 Teams</span><span class="sxs-lookup"><span data-stu-id="a59c4-170">Step 6: (Optional) See a list of Audio Conferencing numbers in Teams</span></span>

<span data-ttu-id="a59c4-171">조직의 오디오 회의 번호 목록을 확인한 다음 에서 오디오 회의 번호 [목록 보기로 Microsoft Teams.](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="a59c4-171">To see the list of Audio Conferencing numbers of your organization, go to [See a list of Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md).</span></span>

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a><span data-ttu-id="a59c4-172">7단계: (선택 사항) 조직의 오디오 회의 전화 접속 번호에 대한 자동 참석 언어 설정</span><span class="sxs-lookup"><span data-stu-id="a59c4-172">Step 7: (Optional) Set auto attendant languages for the Audio Conferencing dial-in numbers of you organization</span></span>

<span data-ttu-id="a59c4-173">조직의 오디오 회의 전화 접속 번호의 언어를 변경하는 경우 에서 오디오 회의에 대한 자동 참석 언어 설정 을 [Microsoft Teams.](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="a59c4-173">To change the languages of the Audio Conferencing dial-in numbers of your organization, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).</span></span>

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="a59c4-174">8단계: (선택 사항) 조직의 오디오 회의 브리지 설정 변경</span><span class="sxs-lookup"><span data-stu-id="a59c4-174">Step 8: (Optional) Change the settings of the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="a59c4-175">조직의 오디오 회의 브리지 설정을 변경하려면 오디오 회의 브리지의 설정 변경을 [참조하세요.](change-the-settings-for-an-audio-conferencing-bridge.md)</span><span class="sxs-lookup"><span data-stu-id="a59c4-175">To change the settings of the Audio Conferencing bridge of your organization, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a><span data-ttu-id="a59c4-176">9단계: (선택 사항) 조직의 사용자의 모임 초대에 포함된 전화 번호 설정</span><span class="sxs-lookup"><span data-stu-id="a59c4-176">Step 9: (Optional) Set the phone numbers included in the meeting invites of the users in your organization</span></span>

<span data-ttu-id="a59c4-177">사용자의 모임 초대에 포함된 전화 번호 집합을 변경하는 것은 조직입니다. 의 초대에 포함된 전화 번호 [집합을](set-the-phone-numbers-included-on-invites-in-teams.md)Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a59c4-177">To change the set of phone numbers that are included in the meeting invites of the users is your organization, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).</span></span>

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="a59c4-178">High 및 DoD에 대한 직접 라우팅을 통해 오디오 회의에서 지원되지 GCC 오디오 회의 기능</span><span class="sxs-lookup"><span data-stu-id="a59c4-178">Audio Conferencing capabilities not supported in Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="a59c4-179">다음은 하이 및 DoD에 대한 직접 라우팅을 통해 오디오 회의에서 지원되지 GCC 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-179">The following are Audio Conferencing capabilities that are not supported in Audio Conferencing with Direct Routing for GCC High and DoD:</span></span>

- <span data-ttu-id="a59c4-180">이름 기록을 사용하여 알림 입력 및 종료</span><span class="sxs-lookup"><span data-stu-id="a59c4-180">Entry and exit notifications using name recording.</span></span> <span data-ttu-id="a59c4-181">직접 라우팅을 사용하여 오디오 회의의 경우 입력 및 종료 알림이 모임에서 톤으로 재생됩니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-181">For Audio Conferencing with Direct Routing, entry and exit notifications are played in the meeting as tones.</span></span>

- <span data-ttu-id="a59c4-182">모임 특정 이끌이에 대한 무료 전화 번호 사용을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-182">Disable the usage of toll-free numbers for the meetings specific organizer.</span></span> <span data-ttu-id="a59c4-183">조직의 모임에 참가하기 위해 무료 번호 사용을 제한하는 사용자 수준 제어는 직접 라우팅을 통해 라우팅된 호출에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-183">User-level controls to restrict the usage of toll-free numbers to join the meetings of your organization aren't applicable to calls routed via Direct Routing.</span></span>

- <span data-ttu-id="a59c4-184">설정이 변경될 때 사용자에게 알림 전자 메일을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-184">Sending notification emails to users when their settings change.</span></span> <span data-ttu-id="a59c4-185">오디오 회의 알림 전자 메일은 하이 및 DoD에 대한 직접 라우팅을 사용하여 오디오 회의에 GCC 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a59c4-185">Audio Conferencing notification emails aren't supported for Audio Conferencing with Direct Routing for GCC High and DoD.</span></span>
