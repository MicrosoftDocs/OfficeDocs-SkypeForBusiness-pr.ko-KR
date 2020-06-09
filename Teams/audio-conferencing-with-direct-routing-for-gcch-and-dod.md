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
ms.openlocfilehash: 17b928dc62cb6e4da0a88fd868ff0e599705d89a
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "44610257"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="84ae0-103">GCC High 및 DoD를 위해 직접 라우팅으로 오디오 회의</span><span class="sxs-lookup"><span data-stu-id="84ae0-103">Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="84ae0-104">GCC High 및 DoD에 대 한 직접 라우팅이 있는 오디오 회의는 참가자가 휴대폰 장치를 사용 하 여 GCC High 또는 DoD 조직의 팀 모임에 참가할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ae0-104">Audio Conferencing with Direct Routing for GCC High and DoD enables participants to join Teams meetings in your GCC High or DoD organization by using a phone device.</span></span> <span data-ttu-id="84ae0-105">모임 참가자는 전화 장치를 사용 하 여 인터넷 연결이 제한 되어 있거나 사용자가 이동 중이 고 팀에 액세스할 수 없는 경우와 같은 시나리오에서 팀 모임에 참가 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="84ae0-105">Meeting participants might prefer to use a phone device to join Teams meetings in scenarios such as when internet connectivity is limited or when users are on the road and don't have access to Teams.</span></span> <span data-ttu-id="84ae0-106">참가자는 조직의 전화 접속 전화 번호로 전화를 걸고 전화 장치에 모임 전화를 걸도록 하 여 모임에 참가 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84ae0-106">Participants can choose to join meetings by either dialing in to a dial-in phone number for your organization or by having the meeting dial out to their phone device.</span></span>

<span data-ttu-id="84ae0-107">GCC High 및 DoD에 대 한 직접 라우팅이 있는 오디오 회의를 사용 하는 경우 조직에서 전화 접속 전화 번호로 자체 번호를 사용 하 고 전화 장치에 대 한 모든 모임 전화 접속은 직접 라우팅을 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="84ae0-107">With Audio Conferencing with Direct Routing for GCC High and DoD, your organization uses its own numbers as dial-in phone numbers and all meeting dial-outs to phone devices are routed via Direct Routing.</span></span> <span data-ttu-id="84ae0-108">서비스를 사용 하도록 설정 하려면 조직에서 직접 라우팅과 전화 접속 전화 번호로 사용할 수 있는 전화 번호를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ae0-108">To enable the service, organizations need to set up Direct Routing and configure phone numbers that can be used as dial-in phone numbers.</span></span> <span data-ttu-id="84ae0-109">직접 라우팅을 사용 해야 하는 요구 사항은 Microsoft에서 전화 접속 전화 번호를 제공 하는 비 GCC 높음이나 비 DoD 조직에 제공 되는 오디오 회의 서비스와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="84ae0-109">The requirement to use Direct Routing is different from the Audio Conferencing service that's offered to non-GCC High and non-DoD organizations where the dial-in phone numbers are provided by Microsoft.</span></span>

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="84ae0-110">GCC High 및 DoD에 대 한 직접 라우팅을 사용 하 여 오디오 회의 배포</span><span class="sxs-lookup"><span data-stu-id="84ae0-110">Deploy Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a><span data-ttu-id="84ae0-111">1 단계: GCC High 또는 DoD 라이선스에 대 한 직접 라우팅이 있는 오디오 회의를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="84ae0-111">Step 1: Get Audio Conferencing with Direct Routing for GCC High or DoD licenses</span></span> 

<span data-ttu-id="84ae0-112">GCC High 또는 DoD에서 오디오 회의를 사용 하려면 조직 및 조직의 사용자가 직접 라우팅 라이선스를 할당 한 오디오 회의를 거쳐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ae0-112">To use Audio Conferencing in GCC High or DoD, your organization and the users in your organization need to have an Audio Conferencing with Direct Routing license assigned.</span></span> <span data-ttu-id="84ae0-113">다음은 GCC High 또는 DoD에 대 한 직접 라우팅이 오디오 회의를 사용 하도록 설정 하는 데 필요한 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="84ae0-113">Here are the licenses you need to enable Audio Conferencing with Direct Routing for GCC High or DoD.</span></span>

- <span data-ttu-id="84ae0-114">GCC 최고: 사용자의 조직 및 오디오 회의-gcc 상위 라이선스에 대 한 오디오 회의-GCC 고용량 테 넌 트 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="84ae0-114">GCC High: An Audio Conferencing - GCC High Tenant license for your organization and Audio Conferencing - GCC High licenses for your users.</span></span>

- <span data-ttu-id="84ae0-115">DoD: 조직 및 오디오 회의용 사용자의 DoD 라이선스에 대 한 오디오 회의-DoD 테 넌 트 라이선스</span><span class="sxs-lookup"><span data-stu-id="84ae0-115">DoD: An Audio Conferencing - DoD Tenant license for your organization and Audio Conferencing - DoD licenses for your users.</span></span>

<span data-ttu-id="84ae0-116">서비스를 사용 하도록 설정 하려면 테 넌 트 라이선스 및 하나 이상의 사용자 라이선스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ae0-116">A tenant license and at least one user license are required to enable the service.</span></span> <span data-ttu-id="84ae0-117">테 넌 트 라이선스 또는 사용자 라이선스만 사용 하 여 서비스를 사용 하도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84ae0-117">You can't enable the service with only the tenant license or with only user licenses.</span></span> <span data-ttu-id="84ae0-118">테 넌 트 및 조직의 사용자에 대 한 서비스 라이선스를 가져오려면 계정 팀에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="84ae0-118">To get service licenses for your tenant and the users in your organization, contact your account team.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="84ae0-119">전화 접속 전화 번호가 설정 될 때까지 직접 라우팅이 있는 오디오 회의는 사용자가 활성화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84ae0-119">Users can't be enabled for Audio Conferencing with Direct Routing until dial-in phone numbers are set up.</span></span> <span data-ttu-id="84ae0-120">이 문서에 설명 된 대로 전화 접속 전화 번호를 설정할 때까지 사용자에 게 GCC High 또는 DoD 라이선스에 대 한 직접 라우팅이 있는 오디오 회의를 할당 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="84ae0-120">We recommend that you not assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to users until you set up dial-in phone numbers as outlined in this article.</span></span>

### <a name="step-2-set-up-direct-routing"></a><span data-ttu-id="84ae0-121">2 단계: 직접 라우팅 설정</span><span class="sxs-lookup"><span data-stu-id="84ae0-121">Step 2: Set up Direct Routing</span></span>

<span data-ttu-id="84ae0-122">직접 라우팅을 설정 하려면 다음 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="84ae0-122">To set up Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="84ae0-123">직접 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="84ae0-123">Plan Direct Routing</span></span>](direct-routing-plan.md)

- [<span data-ttu-id="84ae0-124">직접 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="84ae0-124">Configure Direct Routing</span></span>](direct-routing-configure.md)

> [!NOTE]
> <span data-ttu-id="84ae0-125">직접 라우팅을 설정할 때는이 두 문서에서 설명 하는 GCC High 또는 DoD 관련 Fqdn 및 포트를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ae0-125">When you set up Direct Routing, remember to use the GCC High or DoD-specific FQDNs and ports that are described in these two articles.</span></span>

### <a name="step-3-set-up-dial-in-phone-numbers"></a><span data-ttu-id="84ae0-126">3 단계: 전화 접속 전화 번호 설정</span><span class="sxs-lookup"><span data-stu-id="84ae0-126">Step 3: Set up dial-in phone numbers</span></span>

<span data-ttu-id="84ae0-127">전화 접속 전화 번호는 오디오 회의 브리지에 연결 된 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="84ae0-127">Dial-in phone numbers are the phone numbers that are associated to your Audio Conferencing bridge.</span></span> <span data-ttu-id="84ae0-128">이러한 번호는 참가자가 조직의 사용자가 예약한 모임에 참가 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84ae0-128">These numbers are used by participants to join meetings scheduled by users in your organization.</span></span> <span data-ttu-id="84ae0-129">이러한 번호는 조직의 모임을 예약 하는 사용자와 "로컬 번호 찾기" 페이지의 모임 초대에도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84ae0-129">These numbers are also included in the meeting invites of the users who schedule meetings in your organization and on the "Find a local number" page.</span></span>

#### <a name="define-service-phone-numbers-in-your-tenant"></a><span data-ttu-id="84ae0-130">테 넌 트에서 서비스 전화 번호 정의</span><span class="sxs-lookup"><span data-stu-id="84ae0-130">Define service phone numbers in your tenant</span></span>

<span data-ttu-id="84ae0-131">CsHybridTelephoneNumber PowerShell cmdlet을 사용 하 여 테 넌 트에서 직접 라우팅을 통해 오디오 회의 서비스에 대 한 통화를 라우팅하는 데 사용할 수 있는 서비스 전화 번호를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84ae0-131">You can use the New-csHybridTelephoneNumber PowerShell cmdlet to define service phone numbers in your tenant that can be used to route calls to the Audio Conferencing service via Direct Routing.</span></span> 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

<span data-ttu-id="84ae0-132">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="84ae0-132">For example:</span></span>
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="84ae0-133">조직의 오디오 회의 브리지에 서비스 전화 번호 할당</span><span class="sxs-lookup"><span data-stu-id="84ae0-133">Assign the service phone numbers to the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="84ae0-134">CsOnlineDialInConferencingServiceNumber PowerShell cmdlet을 사용 하 여 조직의 오디오 회의 브리지에 서비스 전화 번호를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84ae0-134">You can assign service phone numbers to the Audio Conferencing bridge of your organization by using the Register-csOnlineDialInConferencingServiceNumber PowerShell cmdlet.</span></span>

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

<span data-ttu-id="84ae0-135">CsOnlineDialInConferencingBridge를 사용 하 여 오디오 회의 브리지의 ID를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84ae0-135">You can see the ID of your Audio Conferencing Bridge using Get-CsOnlineDialInConferencingBridge.</span></span> <span data-ttu-id="84ae0-136">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="84ae0-136">For example:</span></span>

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```

### <a name="step-4-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a><span data-ttu-id="84ae0-137">4 단계: 사용자에 게 GCC High 또는 DoD 라이선스에 대 한 직접 라우팅이 있는 오디오 회의 할당</span><span class="sxs-lookup"><span data-stu-id="84ae0-137">Step 4: Assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your users</span></span>

<span data-ttu-id="84ae0-138">사용자에 게 GCC High 또는 DoD 라이선스에 대 한 직접 라우팅이 있는 오디오 회의를 할당 하려면 [개별적으로 또는 대량으로 사용자 추가](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="84ae0-138">To assign Audio Conferencing with Direct Routing for GCC High or DoD licenses to your user, see [Add users individually or in bulk](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users).</span></span>

### <a name="step-5-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a><span data-ttu-id="84ae0-139">5 단계: (선택 사항) 팀의 오디오 회의 번호 목록 보기</span><span class="sxs-lookup"><span data-stu-id="84ae0-139">Step 5: (Optional) See a list of Audio Conferencing numbers in Teams</span></span>

<span data-ttu-id="84ae0-140">조직의 오디오 회의 번호 목록을 보려면 [Microsoft 팀에서 오디오 회의 번호 목록 보기를 참조](see-a-list-of-audio-conferencing-numbers-in-teams.md) 하세요.</span><span class="sxs-lookup"><span data-stu-id="84ae0-140">To see the list of Audio Conferencing numbers of your organization, go to [See a list of Audio Conferencing numbers in Microsoft Teams](see-a-list-of-audio-conferencing-numbers-in-teams.md)</span></span>

### <a name="step-6-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a><span data-ttu-id="84ae0-141">6 단계: (선택 사항) 사용자 조직의 오디오 회의 전화 접속 번호에 대 한 자동 전화 교환 언어 설정</span><span class="sxs-lookup"><span data-stu-id="84ae0-141">Step 6: (Optional) Set auto attendant languages for the Audio Conferencing dial-in numbers of you organization</span></span>

<span data-ttu-id="84ae0-142">조직의 오디오 회의 전화 접속 번호 언어를 변경 하려면 [Microsoft 팀에서 오디오 회의를 위한 자동 전화 교환 언어 설정을](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="84ae0-142">To change the languages of the Audio Conferencing dial-in numbers of your organization, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)</span></span>

### <a name="step-7-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a><span data-ttu-id="84ae0-143">7 단계: (선택 사항) 조직의 오디오 회의 브리지에 대 한 설정 변경</span><span class="sxs-lookup"><span data-stu-id="84ae0-143">Step 7: (Optional) Change the settings of the Audio Conferencing bridge of your organization</span></span>

<span data-ttu-id="84ae0-144">조직의 오디오 회의 브리지 설정을 변경 하려면 [오디오 회의 브리지에 대 한 설정 변경을](change-the-settings-for-an-audio-conferencing-bridge.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="84ae0-144">To change the settings of the Audio Conferencing bridge of your organization, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md)</span></span>

### <a name="step-8-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a><span data-ttu-id="84ae0-145">8 단계: (선택 사항) 조직의 사용자에 대 한 모임 초대에 포함 된 전화 번호 설정</span><span class="sxs-lookup"><span data-stu-id="84ae0-145">Step 8: (Optional) Set the phone numbers included in the meeting invites of the users in your organization</span></span>

<span data-ttu-id="84ae0-146">사용자의 모임 초대에 포함 되는 전화 번호 집합을 변경 하려면 [Microsoft 팀의 초대에 포함 된 전화 번호 설정을](set-the-phone-numbers-included-on-invites-in-teams.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="84ae0-146">To change the set of phone numbers that are included in the meeting invites of the users is your organization, see [Set the phone numbers included on invites in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md)</span></span>

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a><span data-ttu-id="84ae0-147">GCC High 및 DoD에 대 한 직접 라우팅이 있는 오디오 회의에서는 오디오 회의 기능이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84ae0-147">Audio Conferencing capabilities not supported in Audio Conferencing with Direct Routing for GCC High and DoD</span></span>

<span data-ttu-id="84ae0-148">다음은 GCC High 및 DoD에 대 한 직접 라우팅이 오디오 회의에서 지원 되지 않는 오디오 회의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="84ae0-148">The following are Audio Conferencing capabilities that are not supported in Audio Conferencing with Direct Routing for GCC High and DoD:</span></span>

- <span data-ttu-id="84ae0-149">이름 기록을 사용 하 여 입력 및 종료 알림</span><span class="sxs-lookup"><span data-stu-id="84ae0-149">Entry and exit notifications using name recording.</span></span> <span data-ttu-id="84ae0-150">직접 라우팅이 있는 오디오 회의의 경우 입력 및 종료 알림이 모임에서 톤으로 재생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84ae0-150">For Audio Conferencing with Direct Routing, entry and exit notifications are played in the meeting as tones.</span></span>

- <span data-ttu-id="84ae0-151">오디오 회의에 대 한 아웃 바운드 통화 제한 정책</span><span class="sxs-lookup"><span data-stu-id="84ae0-151">Outbound calling restriction policies for Audio Conferencing.</span></span> <span data-ttu-id="84ae0-152">아웃 바운드 통화를 제한 하는 사용자 수준 컨트롤은 직접 라우팅을 통해 라우팅되는 모임 전화 접속 통화에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84ae0-152">User-level controls to restrict outbound calls aren't applicable to meeting dial-out calls routed via Direct Routing.</span></span>

- <span data-ttu-id="84ae0-153">특정 모임 이끌이가 사용할 수 있는 무료 전화 번호를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ae0-153">Disable the usage of toll-free numbers for the meetings specific organizer.</span></span> <span data-ttu-id="84ae0-154">무료 번호 사용을 조직의 모임에 참가 하도록 제한 하는 사용자 수준 컨트롤은 직접 라우팅을 통해 라우팅되는 통화에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84ae0-154">User-level controls to restrict the usage of toll-free numbers to join the meetings of your organization aren't applicable to calls routed via Direct Routing.</span></span>

- <span data-ttu-id="84ae0-155">설정이 변경 될 때 알림 전자 메일을 사용자에 게 보내기</span><span class="sxs-lookup"><span data-stu-id="84ae0-155">Sending notification emails to users when their settings change.</span></span> <span data-ttu-id="84ae0-156">오디오 회의 알림 전자 메일은 GCC High 및 DoD에 대 한 직접 라우팅이 있는 오디오 회의에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84ae0-156">Audio Conferencing notification emails aren't supported for Audio Conferencing with Direct Routing for GCC High and DoD.</span></span>
