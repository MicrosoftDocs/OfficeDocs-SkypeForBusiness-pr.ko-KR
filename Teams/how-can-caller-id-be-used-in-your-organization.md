---
title: 조직에서 발신자 ID를 사용하는 방법
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
ms.service: msteams
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.callerid.overview
description: CallingLineIdentity라는 정책을 사용하여 전화 시스템 사용자에 대한 인바운드 및 아웃바운드 호출에 대해 호출자 ID를 제어할 수 있습니다.
ms.openlocfilehash: 43d3d6633ca46485aa111a7d97b9bd37b0547818
ms.sourcegitcommit: 02e243d6c58eab463a00ed45dadd80112087006e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2021
ms.locfileid: "52723549"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="118de-103">조직에서 발신자 ID를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="118de-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="118de-104">발신자 ID는 두 개의 사용자 식별 가능한 정보로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="118de-104">Caller ID consists of two user-facing identifiable pieces of information:</span></span>

- <span data-ttu-id="118de-105">전화 번호(일반적으로 CLID 또는 전화 회선 ID라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="118de-105">A phone number (typically referred to as CLID or calling line ID).</span></span> <span data-ttu-id="118de-106">발신자 식별으로 제시된 PSTN(공용 전환 전화 번호)입니다.</span><span class="sxs-lookup"><span data-stu-id="118de-106">This is the Public Switched Telephone Number (PSTN) presented as the identification of the caller.</span></span>

- <span data-ttu-id="118de-107">호출 파티 이름(일반적으로 CNAM이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="118de-107">A Calling party name (typically referred to as CNAM).</span></span> 
  
<span data-ttu-id="118de-108">발신자 ID 기능은 PSTN 연결 옵션에 전화 시스템 모든 사용자가 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="118de-108">The caller ID functionality is available to all Phone System users regardless of PSTN connectivity option:</span></span>

- <span data-ttu-id="118de-109">Microsoft 통화 계획</span><span class="sxs-lookup"><span data-stu-id="118de-109">Microsoft Calling Plans</span></span> 

- <span data-ttu-id="118de-110">전화 시스템 직접 라우팅</span><span class="sxs-lookup"><span data-stu-id="118de-110">Phone System Direct Routing</span></span> 
  
<span data-ttu-id="118de-111">CallingLineIdentity라는 정책을 사용하여 인바운드 및 아웃바운드 호출에 대해 호출자 ID를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="118de-111">You can control Caller ID for both inbound and outbound calls by using a policy called CallingLineIdentity.</span></span> <span data-ttu-id="118de-112">자세한 내용은 전화선 ID 및 통화 파티 이름에 대한 [자세한 정보를 참조하세요.](more-about-calling-line-id-and-calling-party-name.md)</span><span class="sxs-lookup"><span data-stu-id="118de-112">For more information, see [More about Calling Line ID and Calling Party Name](more-about-calling-line-id-and-calling-party-name.md).</span></span>

  
## <a name="outbound-pstn-caller-id"></a><span data-ttu-id="118de-113">아웃바운드 PSTN 호출자 ID</span><span class="sxs-lookup"><span data-stu-id="118de-113">Outbound PSTN caller ID</span></span>

<span data-ttu-id="118de-114">아웃바운드 PSTN 호출자 ID의 경우 다음 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="118de-114">For the outbound PSTN caller ID, the following options are available.</span></span> 
  
- <span data-ttu-id="118de-115">사용자에게 할당된 전화 번호(기본값)입니다.</span><span class="sxs-lookup"><span data-stu-id="118de-115">The telephone number assigned to the user, which is the default.</span></span>

- <span data-ttu-id="118de-116">사용자의 PSTN 번호의 프레젠테이션을 제거하여 사용할 수 있는 익명입니다.</span><span class="sxs-lookup"><span data-stu-id="118de-116">Anonymous, which is available by removing the presentation of the user’s PSTN number.</span></span> 

- <span data-ttu-id="118de-117">대체 전화 번호( 다음이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="118de-117">A substitute phone number, which can be:</span></span>

  - <span data-ttu-id="118de-118">전화 요금제 전화 번호 인벤토리에서 서비스 및 무료 번호로 분류되는 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="118de-118">A telephone number that is classified as a service and toll-free number in your Calling Plans telephone number inventory.</span></span> <span data-ttu-id="118de-119">일반적으로 큐 또는 Teams 자동 전화 교환 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="118de-119">It is usually assigned to a Teams Auto Attendant or Call Queue.</span></span>

  - <span data-ttu-id="118de-120">전화 큐 또는 전화 큐에서 사용하는 리소스 계정에 할당된 직접 라우팅을 통한 Teams 자동 전화 교환 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="118de-120">An on-premises telephone number through Direct Routing that is assigned to a resource account used by a Teams Auto Attendant or Call Queue.</span></span> 

- <span data-ttu-id="118de-121">아웃바운드 PSTN 호출에 설정된 호출 파티 이름 또는 CNAM입니다.</span><span class="sxs-lookup"><span data-stu-id="118de-121">The Calling Party Name or CNAM set on the outbound PSTN call.</span></span>  
    
<span data-ttu-id="118de-122">자세한 내용은 사용자의 [발신자 ID 설정 을 참조하세요.](./set-the-caller-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="118de-122">For more information, see [Set the Caller ID for a user](./set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="118de-123">아웃바운드 호출자 ID의 최종 사용자 제어</span><span class="sxs-lookup"><span data-stu-id="118de-123">End user control of outbound caller ID</span></span>

<span data-ttu-id="118de-124">사용자는 EnableUserOverride  특성을 설정하여 발신자 ID 설정을 익명으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="118de-124">Users can change their caller ID setting to **Anonymous** by setting the EnableUserOverride attribute.</span></span> 

<span data-ttu-id="118de-125">아웃바운드 호출자 ID가 익명으로 설정되어 있는 경우 EnableUserOverride에는 효과가 없습니다. 호출자 ID는 항상 익명으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="118de-125">If the outbound caller ID is set to Anonymous, the EnableUserOverride has no effect and the caller ID is always set to Anonymous.</span></span> <span data-ttu-id="118de-126">EnableUserOverride의 기본값은 False입니다.</span><span class="sxs-lookup"><span data-stu-id="118de-126">The default value of EnableUserOverride is False.</span></span>

<span data-ttu-id="118de-127">최종 사용자는 통화를 호출할 수 설정 > 익명으로 설정한 다음 발신자 **ID에서** 모든 통화에 대한 내 전화 번호 **및** 프로필 정보 숨기기 를 선택할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="118de-127">Your end users can set their caller ID to Anonymous by going to **Settings > Calls**, and then under **Caller ID**, select **Hide my phone number and profile information for all calls**.</span></span>

### <a name="notes"></a><span data-ttu-id="118de-128">참고</span><span class="sxs-lookup"><span data-stu-id="118de-128">Notes</span></span>

<span data-ttu-id="118de-129">다음을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="118de-129">Keep the following in mind:</span></span>

- <span data-ttu-id="118de-130">아웃바운드 호출자 ID에 대해 다음 유형의 전화 번호를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="118de-130">You can't assign the following types of phone numbers for the outbound caller ID:</span></span>

  - <span data-ttu-id="118de-131">통화 계획 전화 번호 인벤토리의 사용자로 분류되는 모든 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="118de-131">Any phone numbers that are classified as a user in your Calling Plans telephone number inventory.</span></span>

  - <span data-ttu-id="118de-132">사용자에게 할당된 직접 라우팅을 통한 모든 프레미스 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="118de-132">Any on-premises telephone number via Direct Routing that is assigned to a user.</span></span>

  - <span data-ttu-id="118de-133">비즈니스용 Skype 서버 전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="118de-133">A Skype for Business Server on-premises telephone number.</span></span>

- <span data-ttu-id="118de-134">리소스 계정 전화 번호 대치의 사용은 사용자에 Teams 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="118de-134">The use of resource account phone number substitution only works for Teams users.</span></span> <span data-ttu-id="118de-135">서비스 전화 번호의 대치는 온라인 사용자 및 비즈니스용 Skype 사용자 모두에 Teams 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="118de-135">The substitution of service phone number works for both Skype for Business Online and Teams users.</span></span>

- <span data-ttu-id="118de-136">발신자 이름은 발신자 ID가 LineUri, 서비스 또는 리소스 계정 전화 번호로 대체되는 통화 및 발신자인 경우만 Teams 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="118de-136">Calling Party Name is only sent on calls where the caller ID is substituted with LineUri, a service or resource account phone number and when the caller is a Teams user.</span></span>

- <span data-ttu-id="118de-137">파티 이름을 호출하면 최대 200자까지 있을 수 있지만 다운스트림 시스템은 더 적은 수의 문자를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="118de-137">Calling Party Name can have a maximum of 200 characters, but downstream systems might support fewer characters.</span></span>

- <span data-ttu-id="118de-138">직접 라우팅의 경우 전화 번호 대칭 및 통화 파티 이름이 FROM SIP 헤더에 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="118de-138">For Direct Routing, the phone number substitution and the Calling Party Name is sent in the FROM SIP header.</span></span> <span data-ttu-id="118de-139">해당 OnlinePstnGateway가 ForwardPai = True로 구성된 경우 P-ASSERTED-IDENTITY SIP 헤더에는 실제 호출 사용자가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="118de-139">If the corresponding OnlinePstnGateway is configured with ForwardPai = True, the P-ASSERTED-IDENTITY SIP header will contain the real calling user.</span></span>

- <span data-ttu-id="118de-140">EnableUserOverride는 대용을 익명으로 설정하지 않는 한 정책의 다른 설정보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="118de-140">EnableUserOverride has precedence over other settings in the policy--unless substitution is set to Anonymous.</span></span> <span data-ttu-id="118de-141">예를 들어 정책 인스턴스에 리소스 계정을 사용하여 대치가 있으며 EnableUserOverride가 설정되어 사용자가 사용하도록 설정되어 있는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="118de-141">For example, assume policy instance has substitution using a resource account and EnableUserOverride is set and enabled by the user.</span></span> <span data-ttu-id="118de-142">이 경우 아웃바운드 호출자 ID가 차단됩니다. 익명이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="118de-142">In this case, the outbound caller ID will be blocked and Anonymous will be used.</span></span> <span data-ttu-id="118de-143">정책 인스턴스에 익명으로 대치가 설정되어 있으며 EnableUserOverride가 설정되어 있는 경우 아웃바운드 호출자 ID는 최종 사용자 설정에 관계없이 항상 익명이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="118de-143">If a policy instance has substitution set to Anonymous and EnableUserOverride is set, then the outbound caller ID will always be Anonymous, regardless of the end user setting.</span></span>

   
## <a name="inbound-caller-id"></a><span data-ttu-id="118de-144">인바운드 호출자 ID</span><span class="sxs-lookup"><span data-stu-id="118de-144">Inbound caller ID</span></span>

<span data-ttu-id="118de-145">전화 시스템 외부 전화 번호를 호출자 ID로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="118de-145">Phone System will show the incoming external phone number as the caller ID.</span></span> <span data-ttu-id="118de-146">번호가 Azure AD 또는 개인 연락처의 사용자 또는 연락처와 연결된 경우 해당 비즈니스용 Skype Teams 클라이언트에 해당 정보에 따라 발신자 ID가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="118de-146">If the number is associated with a user or contact in Azure AD or a personal contact, the Skype for Business and Teams clients will show the caller ID based on that information.</span></span> <span data-ttu-id="118de-147">전화 번호가 Azure AD 또는 개인 연락처에 없는 경우 사용할 수 있는 경우 전화로 제공된 표시 이름이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="118de-147">If the phone number is not in Azure AD or a personal contact, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="118de-148">BlockIncomingCallerID 특성은 들어오는 PSTN 호출에서 호출자 ID를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="118de-148">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="118de-149">이 특성을 설정할 수 있지만 사용자 설정 페이지에서 최종 사용자가 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="118de-149">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="118de-150">이 설정을 사용하도록 설정하면 들어오는 PSTN 호출자는 익명에서 오는 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="118de-150">When this setting is enabled the incoming PSTN caller will be displayed as coming from Anonymous.</span></span>
  
<span data-ttu-id="118de-151">인바운드 호출자 ID를 차단하는 경우 사용자의 [발신자 ID 설정 을 참조합니다.](./set-the-caller-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="118de-151">To block the inbound caller ID, see [Set the Caller ID for a user](./set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="118de-152">관련 항목</span><span class="sxs-lookup"><span data-stu-id="118de-152">Related topics</span></span>
[<span data-ttu-id="118de-153">전화 번호 전송 자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="118de-153">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="118de-154">통화 계획에 사용되는 다양한 종류의 전화 번호</span><span class="sxs-lookup"><span data-stu-id="118de-154">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="118de-155">조직의 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="118de-155">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="118de-156">긴급 통화 사용 약관</span><span class="sxs-lookup"><span data-stu-id="118de-156">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)

<span data-ttu-id="118de-157">[비즈니스용 Skype 온라인: 긴급 통화 고지 사항 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="118de-157">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
