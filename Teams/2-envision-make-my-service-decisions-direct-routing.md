---
title: 전화 시스템 다이렉트 라우팅 서비스 결정-Microsoft 팀
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 07/09/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 직접 라우팅, 라이선스 및 의사 결정에 대해 알아봅니다.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fa92fcf7c30ecd8dfcecb84c3463f70ba13ee7ef
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240810"
---
# <a name="make-my-service-decisions"></a><span data-ttu-id="9e29c-103">내 서비스 결정 하기</span><span class="sxs-lookup"><span data-stu-id="9e29c-103">Make my service decisions</span></span>

<span data-ttu-id="9e29c-104">전화 시스템 다이렉트 라우팅의 기술 구현 ("직접 라우팅")을 계획 하려면 사용자가 정의한 비즈니스 요구 사항에 맞는 솔루션을 구현할 수 있도록 조직 준비를 더 잘 하는 일련의 서비스 의사 결정을 미리 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-104">To plan for the technical implementation of Phone System Direct Routing (“Direct Routing”), you must make a series of service decisions ahead of time to better prepare your organization to implement a solution that meets the business requirements you’ve defined.</span></span>

## <a name="calling-in-teams"></a><span data-ttu-id="9e29c-105">팀에서 통화</span><span class="sxs-lookup"><span data-stu-id="9e29c-105">Calling in Teams</span></span>

<span data-ttu-id="9e29c-106">Microsoft 팀을 통해 사용자는 PSTN (공개 교환 전화 네트워크)에 전화를 걸거나 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-106">With Microsoft Teams, your users can place and receive phone calls to or from the public switched telephone network (PSTN).</span></span> <span data-ttu-id="9e29c-107">사용자는 팀 클라이언트 응용 프로그램에서 국내 및 국제 전화 통화 (보이스 메일 포함)를 설정 하 고 수신 하는 데 고유한 전용 전화 번호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-107">Your users can use their own dedicated phone numbers for placing and receiving domestic and international phone calls (including voicemail) from the Teams client application.</span></span>

## <a name="direct-routing"></a><span data-ttu-id="9e29c-108">직접 라우팅</span><span class="sxs-lookup"><span data-stu-id="9e29c-108">Direct Routing</span></span>

<span data-ttu-id="9e29c-109">팀 사용자가 PSTN 통화를 배치 하 고 수신할 수 있으려면 Office 365의 기능인 전화 시스템을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-109">For Teams users to be able to place and receive PSTN calls, they need to be enabled for Phone System, a feature in Office 365.</span></span>

<span data-ttu-id="9e29c-110">PSTN에 대 한 연결을 가능 하 게 하려면 직접 라우팅을 사용 하 여 조직의 사용자에 게 PSTN을 통해 조직 외부에서 전화를 걸고 받을 수 있는 능력을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-110">To enable connectivity to the PSTN, you can use Direct Routing to give people in your organization the ability to make and receive phone calls outside of the organization over the PSTN.</span></span>

<span data-ttu-id="9e29c-111">직접적인 라우팅에서는 타사 공급자가 PSTN 연결을 촉진 하 여 PSTN 서비스 공급자가 제공 하는 기존 PSTN trunks를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-111">With Direct Routing, PSTN connectivity is facilitated by a third-party provider, giving you the ability to continue using your existing PSTN trunks provided by your PSTN service provider.</span></span> <span data-ttu-id="9e29c-112">이는 전화 시스템에 통화 요금제 ("통화 요금제")를 사용할 수 없거나 기존 PSTN 서비스 공급자 계약을 유지 관리 해야 하거나 특정 온-프레미스 시스템과 상호 운용 되는 배포 환경에서 배포할 수 있습니다. 필수.</span><span class="sxs-lookup"><span data-stu-id="9e29c-112">This allows for deployment in countries where Phone System with Calling Plans (“Calling Plans”) aren’t available, or in deployments where an existing PSTN service provider contract needs to be maintained or interoperability with certain on-premises systems is required.</span></span>

<!--ENDOFSECTION-->

## <a name="availability-of-direct-routing"></a><span data-ttu-id="9e29c-113">직접 라우팅의 가용성</span><span class="sxs-lookup"><span data-stu-id="9e29c-113">Availability of Direct Routing</span></span>

<span data-ttu-id="9e29c-114">직접 라우팅은 Office 365를 사용할 수 있는 모든 국가에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-114">Direct Routing is available in any country where Office 365 is available.</span></span> <span data-ttu-id="9e29c-115">이러한 국가 목록은 [국제 가용성](https://products.office.com/business/international-availability) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9e29c-115">See [International availability](https://products.office.com/business/international-availability) for a list of these countries.</span></span>

<span data-ttu-id="9e29c-116">조직에서 전화 시스템 기능을 구할 수 있는지 확인 한 후에는 사용 가능한 국가 및 지역 목록에 따라 전화 시스템을 구현할 사용자 위치 또는 사무실 목록을 컴파일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-116">After confirming that your organization can obtain the Phone System feature, compile the list of user locations or offices where you’ll be implementing Phone System, based on the list of available countries and regions.</span></span> <span data-ttu-id="9e29c-117">또한 사용 중인 각 위치에 대 한 플랜 또는 직접 라우팅에 대 한 통화를 수행할 사용자를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-117">Also identify the users who you are going to enable Calling Plans or Direct Routing for each location you have.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="9e29c-118">결정 사항</span><span class="sxs-lookup"><span data-stu-id="9e29c-118">Decision points</span></span>|<ul><li><span data-ttu-id="9e29c-119">전화 시스템을 구현할 사용자 위치 또는 사무실을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-119">Identify the user locations or offices in which you’ll implement Phone System.</span></span><li><span data-ttu-id="9e29c-120">사용할 각 위치에 대 한 요금제 또는 직접 라우팅을 사용 하도록 설정할 사용자를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-120">Identify the users who you are going to enable Calling Plans or Direct Routing for each location you have.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="9e29c-121">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9e29c-121">Next steps</span></span>|<ul><li><span data-ttu-id="9e29c-122">전화 시스템에 사용할 사용자 위치 또는 사무실을 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-122">Document the user locations or offices to be enabled for Phone System.</span></span><li><span data-ttu-id="9e29c-123">사용할 각 위치에 대 한 요금제 또는 직접 라우팅을 사용 하도록 설정할 사용자 목록을 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-123">Document the list of users who you are going to enable Calling Plans or Direct Routing for each location you have</span></span></ul>|

> [!TIP]
> <span data-ttu-id="9e29c-124">다음은 다이렉트 라우팅 사이트 활용 목록의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-124">Below is an example of a Direct Routing site enablement list.</span></span>
> 
> | <span data-ttu-id="9e29c-125">**지사**</span><span class="sxs-lookup"><span data-stu-id="9e29c-125">**Office**</span></span>                     | <span data-ttu-id="9e29c-126">**위치**</span><span class="sxs-lookup"><span data-stu-id="9e29c-126">**Location**</span></span>   | <span data-ttu-id="9e29c-127">**전화 시스템 서비스**</span><span class="sxs-lookup"><span data-stu-id="9e29c-127">**Phone System service**</span></span> |
> |--------------------------------|----------------|--------------------------|
> | <span data-ttu-id="9e29c-128">하나의 Epping도로</span><span class="sxs-lookup"><span data-stu-id="9e29c-128">One Epping Road</span></span>                | <span data-ttu-id="9e29c-129">오스트레일리아</span><span class="sxs-lookup"><span data-stu-id="9e29c-129">Australia</span></span>      | <span data-ttu-id="9e29c-130">레거시 PSTN 서비스</span><span class="sxs-lookup"><span data-stu-id="9e29c-130">Legacy PSTN service</span></span> |
> | <span data-ttu-id="9e29c-131">100 Cyberport도로</span><span class="sxs-lookup"><span data-stu-id="9e29c-131">100 Cyberport Road</span></span>             | <span data-ttu-id="9e29c-132">홍콩 특별 행정구</span><span class="sxs-lookup"><span data-stu-id="9e29c-132">Hong Kong SAR</span></span>  | <span data-ttu-id="9e29c-133">전화 시스템 직접 라우팅</span><span class="sxs-lookup"><span data-stu-id="9e29c-133">Phone System Direct Routing</span></span> |
> | <span data-ttu-id="9e29c-134">One Marina Royal</span><span class="sxs-lookup"><span data-stu-id="9e29c-134">One Marina Boulevard</span></span>           | <span data-ttu-id="9e29c-135">싱가포르</span><span class="sxs-lookup"><span data-stu-id="9e29c-135">Singapore</span></span>      | <span data-ttu-id="9e29c-136">전화 시스템 직접 라우팅</span><span class="sxs-lookup"><span data-stu-id="9e29c-136">Phone System Direct Routing</span></span> |
> | <span data-ttu-id="9e29c-137">32 런던 다리의 거리</span><span class="sxs-lookup"><span data-stu-id="9e29c-137">32 London Bridge Street</span></span>        | <span data-ttu-id="9e29c-138">영국</span><span class="sxs-lookup"><span data-stu-id="9e29c-138">United Kingdom</span></span> | <span data-ttu-id="9e29c-139">통화 요금제가 포함 되어 있는 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="9e29c-139">Phone System with Calling Plans</span></span> |
> | <span data-ttu-id="9e29c-140">39 Roosevelt Président du</span><span class="sxs-lookup"><span data-stu-id="9e29c-140">39 quai du Président Roosevelt</span></span> | <span data-ttu-id="9e29c-141">프랑스</span><span class="sxs-lookup"><span data-stu-id="9e29c-141">France</span></span>         | <span data-ttu-id="9e29c-142">통화 요금제가 포함 되어 있는 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="9e29c-142">Phone System with Calling Plans</span></span> |

<!--ENDOFSECTION-->

## <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="9e29c-143">전화 번호 및 비상 위치</span><span class="sxs-lookup"><span data-stu-id="9e29c-143">Phone numbers and emergency locations</span></span>

<span data-ttu-id="9e29c-144">전화 시스템에는 조직의 모든 사용자가 고유한 직접 안쪽 전화 걸기 (a) 전화 번호를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-144">Phone System requires every user in your organization to have a unique direct inward dialing (DID) phone number.</span></span> <span data-ttu-id="9e29c-145">다이렉트 라우팅과 함께 PSTN 서비스 공급자가 전화 번호와 응급 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-145">With Direct Routing, the phone numbers and the emergency services are provided by your PSTN service provider.</span></span>

> [!NOTE]
> <span data-ttu-id="9e29c-146">직접 라우팅의 경우 사용자는 PSTN 서비스 공급자가 제공 하는 자신의 전화 번호를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-146">With Direct Routing, your users can continue using their own phone numbers, provided by the PSTN service provider.</span></span>
> 
> [!TIP]
> <span data-ttu-id="9e29c-147">다음 서식 파일을 사용 하 여 전화 번호에 대 한 정보를 문서화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-147">You can use the following template to document the phone numbers details.</span></span>
> 
> |<span data-ttu-id="9e29c-148">클릭할</span><span class="sxs-lookup"><span data-stu-id="9e29c-148">User</span></span> |<span data-ttu-id="9e29c-149">전화 번호</span><span class="sxs-lookup"><span data-stu-id="9e29c-149">Phone number</span></span> |
> |-----|-------------|
> |<span data-ttu-id="9e29c-150">Emily Braun</span><span class="sxs-lookup"><span data-stu-id="9e29c-150">Emily Braun</span></span> | <span data-ttu-id="9e29c-151">+ 44 23 4567 8901</span><span class="sxs-lookup"><span data-stu-id="9e29c-151">+44 23 4567 8901</span></span> |
> |<span data-ttu-id="9e29c-152">Lidia Holloway</span><span class="sxs-lookup"><span data-stu-id="9e29c-152">Lidia Holloway</span></span> | <span data-ttu-id="9e29c-153">+ 44 23 4567 89112</span><span class="sxs-lookup"><span data-stu-id="9e29c-153">+44 23 4567 89112</span></span> |
> |<span data-ttu-id="9e29c-154">세인트루이스의 Lahr</span><span class="sxs-lookup"><span data-stu-id="9e29c-154">Louis Lahr</span></span> | <span data-ttu-id="9e29c-155">+ 44 23 4567 8921</span><span class="sxs-lookup"><span data-stu-id="9e29c-155">+44 23 4567 8921</span></span> |
> |<span data-ttu-id="9e29c-156">Marcel Beauchamp</span><span class="sxs-lookup"><span data-stu-id="9e29c-156">Marcel Beauchamp</span></span> | <span data-ttu-id="9e29c-157">TBA</span><span class="sxs-lookup"><span data-stu-id="9e29c-157">TBA</span></span> |
> |<span data-ttu-id="9e29c-158">Rachelle Cormier</span><span class="sxs-lookup"><span data-stu-id="9e29c-158">Rachelle Cormier</span></span> | <span data-ttu-id="9e29c-159">TBA</span><span class="sxs-lookup"><span data-stu-id="9e29c-159">TBA</span></span> |
> |<span data-ttu-id="9e29c-160">Isabell Potvin</span><span class="sxs-lookup"><span data-stu-id="9e29c-160">Isabell Potvin</span></span> | <span data-ttu-id="9e29c-161">TBA</span><span class="sxs-lookup"><span data-stu-id="9e29c-161">TBA</span></span> |

<!--ENDOFSECTION-->

## <a name="voicemail"></a><span data-ttu-id="9e29c-162">보이스 메일</span><span class="sxs-lookup"><span data-stu-id="9e29c-162">Voicemail</span></span>

<span data-ttu-id="9e29c-163">Azure 보이스 메일 서비스를 통해 제공 되는 클라우드 보이스 메일은 Exchange 사서함에 대 한 보이스 메일 저축과 지원 하며 타사 전자 메일 시스템을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-163">Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only and doesn’t support third-party email systems.</span></span>

<span data-ttu-id="9e29c-164">클라우드 보이스 메일에는 조직의 모든 사용자가 기본적으로 사용 하도록 설정 된 음성 메일의 내용이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-164">Cloud Voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="9e29c-165">비즈니스 요구에 따라 특정 사용자 또는 조직 전체에 대 한 보이스 메일을 사용 하지 않도록 설정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-165">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span> <span data-ttu-id="9e29c-166">조직에서 음성 메일 기록을 사용 하기로 결정 한 경우에는 보이스 메일 보관 함 표시를 사용 해야 하는지 여부도 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-166">If your organization decided to keep voicemail transcription enabled, you need to also consider whether voicemail transcription profanity masking needs to be enabled.</span></span> <span data-ttu-id="9e29c-167">자세한 내용은 [조직의 보이스 메일 정책 설정을](set-up-phone-system-voicemail.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9e29c-167">See [Setting voicemail policies in your organization](set-up-phone-system-voicemail.md) for more details.</span></span>

<span data-ttu-id="9e29c-168">전화 시스템 구현에서 보이스 메일에 대 한 자세한 내용은 [클라우드 보이스 메일 설정을](set-up-phone-system-voicemail.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9e29c-168">For more information about voicemail in a Phone System implementation, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="9e29c-169">결정 사항</span><span class="sxs-lookup"><span data-stu-id="9e29c-169">Decision points</span></span>|<ul><li><span data-ttu-id="9e29c-170">다이렉트 라우팅 구현에서 클라우드 보이스 메일을 사용할지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-170">Decide whether you’ll enable Cloud Voicemail in your Direct Routing implementation.</span></span><li><span data-ttu-id="9e29c-171">조직 전체 또는 특정 사용자에 대 한 보이스 메일 기록 및 음성 메일 기록 사용 금지 마스크를 사용할지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-171">Decide whether you’ll enable or disable voicemail transcription and voicemail transcription profanity masking throughout the organization or for specific users.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="9e29c-172">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9e29c-172">Next steps</span></span>|<ul><li><span data-ttu-id="9e29c-173">해당 하는 경우 클라우드 보이스 메일을 지원 하기 위한 결정 지점을 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-173">If applicable, document the decision points to support Cloud Voicemail.</span></span><li><span data-ttu-id="9e29c-174">음성 메일, 음성 메일, 음성 메일을 사용 하거나 사용 하지 않도록 설정 하는 경우 특정 사용자에 대해서만 해당 사용자 목록을 문서화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-174">If you’ll enable or disable voicemail, voicemail transcription, and voicemail transcription profanity masking only for specific users, document that list of users.</span></span></ul>|

> [!TIP]
> <span data-ttu-id="9e29c-175">호출 계획 구현에 대 한 구름 보이스 메일 정보는 다음 표에 나와 있는 것 처럼 문서화 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-175">Cloud Voicemail details for the Calling Plans implementation can be documented as in the following table.</span></span>
> 
> | <span data-ttu-id="9e29c-176">**클릭할**</span><span class="sxs-lookup"><span data-stu-id="9e29c-176">**User**</span></span>         | <span data-ttu-id="9e29c-177">**Exchange 사서함**</span><span class="sxs-lookup"><span data-stu-id="9e29c-177">**Exchange mailbox**</span></span> | <span data-ttu-id="9e29c-178">**보이스 메일을 가능 하 게 하 시겠습니까?**</span><span class="sxs-lookup"><span data-stu-id="9e29c-178">**Enable voicemail?**</span></span> | <span data-ttu-id="9e29c-179">**보이스 메일**</span><span class="sxs-lookup"><span data-stu-id="9e29c-179">**Voicemail transcription**</span></span> | <span data-ttu-id="9e29c-180">**보이스 메일 기록 불경 마스크**</span><span class="sxs-lookup"><span data-stu-id="9e29c-180">**Voicemail transcription profanity masking**</span></span> |
> |------------------|----------------------|-----------------------|-----------------------------|-----------------------------------------------|
> | <span data-ttu-id="9e29c-181">Emily Braun</span><span class="sxs-lookup"><span data-stu-id="9e29c-181">Emily Braun</span></span>      | <span data-ttu-id="9e29c-182">온라인</span><span class="sxs-lookup"><span data-stu-id="9e29c-182">Online</span></span>               | <span data-ttu-id="9e29c-183">'</span><span class="sxs-lookup"><span data-stu-id="9e29c-183">Yes</span></span>                   | <span data-ttu-id="9e29c-184">수</span><span class="sxs-lookup"><span data-stu-id="9e29c-184">Enabled</span></span>                     | <span data-ttu-id="9e29c-185">수</span><span class="sxs-lookup"><span data-stu-id="9e29c-185">Enabled</span></span>                                       |
> | <span data-ttu-id="9e29c-186">Lidia Holloway</span><span class="sxs-lookup"><span data-stu-id="9e29c-186">Lidia Holloway</span></span>   | <span data-ttu-id="9e29c-187">온라인</span><span class="sxs-lookup"><span data-stu-id="9e29c-187">Online</span></span>               | <span data-ttu-id="9e29c-188">'</span><span class="sxs-lookup"><span data-stu-id="9e29c-188">Yes</span></span>                   | <span data-ttu-id="9e29c-189">수</span><span class="sxs-lookup"><span data-stu-id="9e29c-189">Enabled</span></span>                     | <span data-ttu-id="9e29c-190">비활성화</span><span class="sxs-lookup"><span data-stu-id="9e29c-190">Disabled</span></span>                                      |
> | <span data-ttu-id="9e29c-191">세인트루이스의 Lahr</span><span class="sxs-lookup"><span data-stu-id="9e29c-191">Louis Lahr</span></span>       | <span data-ttu-id="9e29c-192">온-프레미스</span><span class="sxs-lookup"><span data-stu-id="9e29c-192">On-premises</span></span>          | <span data-ttu-id="9e29c-193">'</span><span class="sxs-lookup"><span data-stu-id="9e29c-193">Yes</span></span>                   | <span data-ttu-id="9e29c-194">수</span><span class="sxs-lookup"><span data-stu-id="9e29c-194">Enabled</span></span>                     | <span data-ttu-id="9e29c-195">수</span><span class="sxs-lookup"><span data-stu-id="9e29c-195">Enabled</span></span>                                       |
> | <span data-ttu-id="9e29c-196">Marcel Beauchamp</span><span class="sxs-lookup"><span data-stu-id="9e29c-196">Marcel Beauchamp</span></span> | <span data-ttu-id="9e29c-197">온-프레미스</span><span class="sxs-lookup"><span data-stu-id="9e29c-197">On-premises</span></span>          | <span data-ttu-id="9e29c-198">'</span><span class="sxs-lookup"><span data-stu-id="9e29c-198">Yes</span></span>                   | <span data-ttu-id="9e29c-199">비활성화</span><span class="sxs-lookup"><span data-stu-id="9e29c-199">Disabled</span></span>                    | <span data-ttu-id="9e29c-200">해당 없음</span><span class="sxs-lookup"><span data-stu-id="9e29c-200">N/A</span></span>                                           |
> | <span data-ttu-id="9e29c-201">Rachelle Cormier</span><span class="sxs-lookup"><span data-stu-id="9e29c-201">Rachelle Cormier</span></span> | <span data-ttu-id="9e29c-202">온라인</span><span class="sxs-lookup"><span data-stu-id="9e29c-202">Online</span></span>               | <span data-ttu-id="9e29c-203">'</span><span class="sxs-lookup"><span data-stu-id="9e29c-203">Yes</span></span>                   | <span data-ttu-id="9e29c-204">비활성화</span><span class="sxs-lookup"><span data-stu-id="9e29c-204">Disabled</span></span>                    | <span data-ttu-id="9e29c-205">해당 없음</span><span class="sxs-lookup"><span data-stu-id="9e29c-205">N/A</span></span>                                           |
> | <span data-ttu-id="9e29c-206">Isabell Potvin</span><span class="sxs-lookup"><span data-stu-id="9e29c-206">Isabell Potvin</span></span>   | <span data-ttu-id="9e29c-207">온-프레미스</span><span class="sxs-lookup"><span data-stu-id="9e29c-207">On-premises</span></span>          | <span data-ttu-id="9e29c-208">'</span><span class="sxs-lookup"><span data-stu-id="9e29c-208">Yes</span></span>                   | <span data-ttu-id="9e29c-209">비활성화</span><span class="sxs-lookup"><span data-stu-id="9e29c-209">Disabled</span></span>                    | <span data-ttu-id="9e29c-210">해당 없음</span><span class="sxs-lookup"><span data-stu-id="9e29c-210">N/A</span></span>                                           |
> 
> [!NOTE]
> <span data-ttu-id="9e29c-211">팀과 보이스 메일을 사용 하려면 사용자에 게 Exchange 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-211">To use Teams and voicemail, your users must have Exchange mailboxes.</span></span> <span data-ttu-id="9e29c-212">자세한 내용은 [Exchange 및 Microsoft 팀의 상호 작용](exchange-teams-interact.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9e29c-212">See [How Exchange and Microsoft Teams interact](exchange-teams-interact.md) for more details.</span></span>

<!--ENDOFSECTION-->

## <a name="licensing-for-direct-routing"></a><span data-ttu-id="9e29c-213">직접 라우팅 라이선스</span><span class="sxs-lookup"><span data-stu-id="9e29c-213">Licensing for Direct Routing</span></span>

<span data-ttu-id="9e29c-214">조직에서 직접 라우팅을 사용 하려는 경우 필요한 라이선스를 얻어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-214">If your organization intends to use Direct Routing, you need to obtain required licenses.</span></span> <span data-ttu-id="9e29c-215">직접 라우팅 사용자에 게는 Office 365에 할당 된 다음 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-215">Users of Direct Routing must have the following licenses assigned in Office 365:</span></span>

-   <span data-ttu-id="9e29c-216">Microsoft 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="9e29c-216">Microsoft Phone System</span></span>

-   <span data-ttu-id="9e29c-217">Microsoft 팀</span><span class="sxs-lookup"><span data-stu-id="9e29c-217">Microsoft Teams</span></span>

-   <span data-ttu-id="9e29c-218">오디오 회의</span><span class="sxs-lookup"><span data-stu-id="9e29c-218">Audio Conferencing</span></span>

<span data-ttu-id="9e29c-219">오디오 회의 라이선스는 외부 참가자에 게 전화를 거 나 전화 접속 번호를 제공 하는 방법으로 예약 된 모임을 추가 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-219">Audio Conferencing license is required for adding external participants to scheduled meetings, either by dialing out to them or by providing the dial-in number.</span></span> <span data-ttu-id="9e29c-220">외부 참가자에 게 전화를 거는 경우 오디오 회의 서비스에서 온라인 통화 기능을 사용 하 여 통화를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-220">When an external participant is dialed out to, the Audio Conferencing service places the call by using online calling capabilities.</span></span> <span data-ttu-id="9e29c-221">오디오 회의 라이선스는 선택 사항이 며 오디오 회의를 포함 하는 팀 회의를 구성 하는 사용자 에게만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-221">Audio Conferencing license is optional, and only required for users who will be organizing Teams conferences that include Audio Conferencing.</span></span>


> [!NOTE]
> <span data-ttu-id="9e29c-222">무료 회의 브리지 전화 번호를 제공 하 고 국제 전화 번호로 회의 전화 걸기를 지원 하려면 조직의 [통신 크레딧을](what-are-communications-credits.md) 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-222">To provide toll-free conference bridge phone numbers and to support conferencing dial-out to international phone numbers, you should set up [Communications Credits](what-are-communications-credits.md) for your organization.</span></span>

<span data-ttu-id="9e29c-223">오디오 회의 및 전화 시스템은 Office 365 E3 또는 E1 구독 계획을 보유 하 고 있는 기존 고객을 위한 추가 기능 서비스와 별도로 라이선스가 부여 될 수 있습니다. 이미 Office 365 E5 구독 계획의 일부로 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-223">Audio Conferencing and Phone System can be licensed separately as add-on services for existing customers who have Office 365 E3 or E1 subscription plans; they’re already included as part of the Office 365 E5 subscription plan.</span></span>

> [!TIP]
> <span data-ttu-id="9e29c-224">타사 Pbx로 전화를 라우팅할 때 통화 계획을 사용할 수 있는 사용자에 게 직접 라우팅을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-224">You can also use Direct Routing for the users who are enabled for Calling Plans when routing their calls to third-party PBXs.</span></span> <span data-ttu-id="9e29c-225">자세한 내용은 [라이선스 및 직접 라우팅의 기타 요구 사항을](direct-routing-plan.md#licensing-and-other-requirements)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9e29c-225">For more details, see [Licensing and other requirements of Direct Routing](direct-routing-plan.md#licensing-and-other-requirements).</span></span>


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="9e29c-226">결정 사항</span><span class="sxs-lookup"><span data-stu-id="9e29c-226">Decision points</span></span>|<ul><li><span data-ttu-id="9e29c-227">조직에 필요한 전화 시스템 라이선스가 없는 경우 기존 Office 365 구독을 단계별로 진행 하거나 전화 시스템 추가 기능 서비스를 획득 하 여 전화 시스템 라이선스를 확보할 것인지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-227">If your organization doesn’t have the required Phone System license, decide whether you’ll acquire the Phone System license by stepping up your existing Office 365 subscriptions or by acquiring the Phone System add-on service.</span></span><li><span data-ttu-id="9e29c-228">다이렉트 라우팅 구현에 통신 크레딧이 필요한 지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-228">Decide whether you’ll need Communications Credits for your Direct Routing implementation.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="9e29c-229">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9e29c-229">Next steps</span></span>|<ul><li><span data-ttu-id="9e29c-230">전화 시스템 라이선스를 할당할 디비전, 부서, 사무실 또는 사용자 그룹을 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-230">Document the division, department, office, or user groups you’ll assign a Phone System license.</span></span><li><span data-ttu-id="9e29c-231">무료 번호를 사용 하는 오디오 회의가 범위 내에 있는 경우 통신 크레딧을 사용할 수 있는 부서, 부서, 사무실 또는 사용자 그룹을 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-231">If Audio Conferencing with toll-free numbers is in scope, document the division, department, office, or user groups you’ll enable Communications Credits.</span></span></ul>|

<!--ENDOFSECTION-->

## <a name="office-365-considerations"></a><span data-ttu-id="9e29c-232">Office 365 고려 사항</span><span class="sxs-lookup"><span data-stu-id="9e29c-232">Office 365 considerations</span></span>

<span data-ttu-id="9e29c-233">직접 라우팅을 사용할 수 있는 모든 사용자는 Office 365에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-233">Any user who will be enabled for Direct Routing must be homed in Office 365.</span></span> <span data-ttu-id="9e29c-234">온-프레미스 비즈니스용 Skype Server 또는 Lync Server를 사용 하는 하이브리드 배포의 경우 팀과의 다이렉트 라우팅을 사용 하도록 구성 하기 전에 비즈니스용 Skype Online으로 사용자를 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-234">For hybrid deployments with on-premises Skype for Business Server or Lync Server, you need to move users to Skype for Business Online before configuring them to use Direct Routing with Teams.</span></span>

<span data-ttu-id="9e29c-235">직접 라우팅 구현 범위에 있는 모든 사용자를 팀에서 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-235">All users who are in scope of Direct Routing implementations must be enabled for Teams.</span></span>

<span data-ttu-id="9e29c-236">Onmicrosoft.com 도메인은 \*직접 라우팅과 함께 사용할 수 없으므로 하나 이상의 도메인에서 Office 365 테 넌 트를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-236">Your Office 365 tenant must be enabled with one or more domains, because the default \*.onmicrosoft.com domain can’t be used with Direct Routing.</span></span> <span data-ttu-id="9e29c-237">도메인 및 Office 365 테 넌 트에 대 한 자세한 내용은 [도메인 FAQ](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9e29c-237">For more information about domains and Office 365 tenants, see [Domains FAQ](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="9e29c-238">결정 사항</span><span class="sxs-lookup"><span data-stu-id="9e29c-238">Decision points</span></span>|<ul><li><span data-ttu-id="9e29c-239">직접 라우팅을 지원 하려면 비즈니스용 Skype Online으로 마이그레이션해야 할 사용자가 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-239">Decide whether any users need to be migrated to Skype for Business Online to support Direct Routing.</span></span><li><span data-ttu-id="9e29c-240">팀에 대해 사용 하도록 설정 해야 하는 사용자를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-240">Identify the users who need to be enabled for Teams.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="9e29c-241">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9e29c-241">Next steps</span></span>|<ul><li><span data-ttu-id="9e29c-242">비즈니스용 Skype Online으로 이동 하 고 팀에 대해 사용 하도록 설정 해야 하는 사용자 목록을 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-242">Document the list of users who need to move to Skype for Business Online and be enabled for Teams.</span></span></ul>|

<!--ENDOFSECTION-->

## <a name="sbc-considerations"></a><span data-ttu-id="9e29c-243">SBC 고려 사항</span><span class="sxs-lookup"><span data-stu-id="9e29c-243">SBC considerations</span></span>

<span data-ttu-id="9e29c-244">사용자에 게 PSTN 연결을 제공 하기 위해 직접 라우팅 서비스와 쌍을 두어야 하는 인증 된 또는 지원 되는 세션 경계 컨트롤러 (SBCs)를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-244">You need to use certified and supported session border controllers (SBCs) that need to be paired to the Direct Routing service to provide PSTN connectivity for your users.</span></span> <span data-ttu-id="9e29c-245">인증 된 SBCs 목록은 [지원 되는 세션 경계 컨트롤러](direct-routing-plan.md#supported-session-border-controllers-sbcs)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9e29c-245">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-plan.md#supported-session-border-controllers-sbcs).</span></span>

<span data-ttu-id="9e29c-246">환경, 위치 수, 음성 라우팅 요구 사항에 따라 사용자 기반을 지원 하기 위해 여러 개의 SBCs를 배포 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-246">Depending on your environment, number of locations, and voice routing requirements, you might need to deploy multiple SBCs to support your user base.</span></span>

### <a name="sbc-domain-names"></a><span data-ttu-id="9e29c-247">SBC 도메인 이름</span><span class="sxs-lookup"><span data-stu-id="9e29c-247">SBC domain names</span></span>

<span data-ttu-id="9e29c-248">직접 라우팅과 쌍을 두는 각 SBC에는 고유한 DNS 이름이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-248">Each SBC that you pair with Direct Routing must have a unique DNS name.</span></span> <span data-ttu-id="9e29c-249">SBC DNS 이름은 Office 365 테 넌 트에 등록 된 도메인 이름 중 하나 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-249">The SBC DNS names must be from one of the domain names registered in the Office 365 tenant.</span></span> <span data-ttu-id="9e29c-250">테 넌 트에서 여러 도메인 이름을 할당 한 경우에는 SBCs의 DNS 이름을 계획할 때 이러한 도메인 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-250">If your tenant has been assigned multiple domain names, you can use any of these domain names when planning for your SBCs’ DNS names.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e29c-251">SBC DNS 이름에는 \*. onmicrosoft.com을 사용 하는 것이 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-251">The use of \*.onmicrosoft.com for the SBC DNS name is not allowed.</span></span>

### <a name="certificates"></a><span data-ttu-id="9e29c-252">인증</span><span class="sxs-lookup"><span data-stu-id="9e29c-252">Certificates</span></span>

<span data-ttu-id="9e29c-253">직접 라우팅으로 배포 된 각 SBC에는 지원 되는 인증 기관 목록에서 받은 인증서가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-253">Each SBC deployed with Direct Routing requires a certificate obtained from a list of supported certification authorities.</span></span> <span data-ttu-id="9e29c-254">인증서는 주체, 주체 대체 이름 또는 일반 이름 필드에 SBC DNS 이름을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-254">The certificate must include the SBC DNS name in the subject, subject alternate name, or common name fields.</span></span>

> [!NOTE]
> <span data-ttu-id="9e29c-255">SBCs와 함께 와일드 카드 인증서를 사용 하는 방법도 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-255">The use of wildcard certificates with SBCs is also supported.</span></span>

<span data-ttu-id="9e29c-256">지원 되는 인증 기관 목록 및 자세한 내용은 [SBC에 대 한 신뢰할 수 있는 공개 인증서](direct-routing-plan.md#public-trusted-certificate-for-the-sbc)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9e29c-256">For more information and a list of supported certification authorities, see [Public trusted certificate for the SBC](direct-routing-plan.md#public-trusted-certificate-for-the-sbc).</span></span>


### <a name="sbc-ip-addresses-and-ports"></a><span data-ttu-id="9e29c-257">SBC IP 주소 및 포트</span><span class="sxs-lookup"><span data-stu-id="9e29c-257">SBC IP addresses and ports</span></span>

<span data-ttu-id="9e29c-258">각 SBC는 Office 365 데이터 센터에서 액세스할 수 있는 공용 IP 주소를 사용 하 여 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-258">Each SBC must be configured by using a public IP address accessible from Office 365 datacenters.</span></span> <span data-ttu-id="9e29c-259">NAT (network address translation)를 구성 하 여 Office 365 데이터 센터에 SBCs를 게시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-259">You can also configure network address translation (NAT) to publish your SBCs to Office 365 datacenters.</span></span>

<span data-ttu-id="9e29c-260">SBCs는 신호 및 미디어에 대 한 클라우드 서비스와 통신 하기 위해 양방향 연결을 요구 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-260">SBCs require bidirectional connectivity to communicate with the cloud services for signaling and media.</span></span> <span data-ttu-id="9e29c-261">신호는 *SIP 프록시*라는 구성 요소에 의해 처리 되며 미디어 *프로세서*에서 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-261">Signaling is handled by the component named *SIP Proxy*, and the media is handled by the *Media Processors*.</span></span>

<span data-ttu-id="9e29c-262">각 SBC에서 SIP 신호 및 미디어에 대 한 특정 포트 번호를 정의 하 고 이러한 포트와 연결 된 IP 주소에 대 한 양방향 트래픽을 허용 하도록 방화벽을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-262">You need to define specific port numbers on each SBC for SIP signaling and media, and configure your firewalls to allow bidirectional traffic to these ports and their associated IP addresses.</span></span>

<span data-ttu-id="9e29c-263">자세한 내용은 [SIP 신호: fqdn 및 방화벽 포트](direct-routing-plan.md#sip-signaling-fqdns-and-firewall-ports) 및 [미디어 트래픽: 포트 범위](direct-routing-plan.md#media-traffic-port-ranges)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9e29c-263">For more details, see [SIP Signaling: FQDNs and firewall ports](direct-routing-plan.md#sip-signaling-fqdns-and-firewall-ports) and [Media traffic: Port ranges](direct-routing-plan.md#media-traffic-port-ranges).</span></span>


> [!NOTE]
> <span data-ttu-id="9e29c-264">SBC 모델을 기반으로 각 SBC에 대해 최대 동시 세션 제한을 설정할 것을 적극 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-264">We highly recommend setting a maximum concurrent session limit for each SBC, based on the SBC model.</span></span> <span data-ttu-id="9e29c-265">그러면 해당 용량에 따라 SBC이 실행 되는 동안에도 알림이 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-265">That limit would then trigger a notification when the SBC is running at or near its capacity.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="9e29c-266">결정 사항</span><span class="sxs-lookup"><span data-stu-id="9e29c-266">Decision points</span></span>|<ul><li><span data-ttu-id="9e29c-267">SBCs를 배포할 위치를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-267">Decide at which locations you’ll deploy SBCs.</span></span><li><span data-ttu-id="9e29c-268">배포 하려고 하는 각 SBC에 대 한 DNS 이름을 결정 하세요.</span><span class="sxs-lookup"><span data-stu-id="9e29c-268">Decide a DNS name for each SBC you’re planning to deploy.</span></span><li><span data-ttu-id="9e29c-269">SBC 도메인 이름 결정에 따라 배포에 있는 모든 SBCs를 지원 하기 위해 와일드 카드 인증서를 사용할지 SBC 당 전용 인증서를 사용할지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-269">Based on the SBC domain name decision, decide whether you’re going to use a wildcard certificate to support all SBCs in your deployment or a dedicated certificate per SBC.</span></span><li><span data-ttu-id="9e29c-270">사용자의 SBCs에 대 한 인증서를 얻을 공용 인증 기관을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-270">Decide which public certificate authority you’ll obtain the certificates for your SBCs from.</span></span><li><span data-ttu-id="9e29c-271">배포할 각 SBC에 대해 공용 IP 주소/포트 쌍을 정의 하 고 공용 IP 주소를 SBCs에 할당 하거나 NAT를 사용할지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-271">Define a public IP address/port pair for each SBC you’ll deploy, and decide whether you’ll assign the public IP addresses to the SBCs or use NAT.</span></span><li><span data-ttu-id="9e29c-272">각 SBC가 지원 하거나 처리할 수 있는 최대 동시 세션 수를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-272">Identify the maximum number of concurrent sessions each SBC supports or can handle.</span></span><li><span data-ttu-id="9e29c-273">미디어 바이패스를 사용 하 여 구성할 SBCs를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-273">Decide which SBCs will be configured by using Media Bypass.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="9e29c-274">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9e29c-274">Next steps</span></span>|<ul><li><span data-ttu-id="9e29c-275">다음 예제 표를 사용 하 여 SBCs에 대 한 각 결정을 문서로 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-275">Document each decision being made for the SBCs by using the following example table.</span></span></ul>|


> [!TIP]
> <span data-ttu-id="9e29c-276">직접 라우팅 배포에 대 한 SBC 세부 정보를 문서화 하려면 다음 서식 파일을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-276">Use the following template to document the SBC details for your Direct Routing deployment.</span></span>
> 
> | <span data-ttu-id="9e29c-277">**SBC DNS 이름 (FQDN)**</span><span class="sxs-lookup"><span data-stu-id="9e29c-277">**SBC DNS Name (FQDN)**</span></span> | <span data-ttu-id="9e29c-278">**SBC 만들기 및 모델**</span><span class="sxs-lookup"><span data-stu-id="9e29c-278">**SBC make and model**</span></span> | <span data-ttu-id="9e29c-279">**인증**</span><span class="sxs-lookup"><span data-stu-id="9e29c-279">**Certificate**</span></span> | <span data-ttu-id="9e29c-280">**위치**</span><span class="sxs-lookup"><span data-stu-id="9e29c-280">**Location**</span></span>  | <span data-ttu-id="9e29c-281">**IP 주소**</span><span class="sxs-lookup"><span data-stu-id="9e29c-281">**IP address**</span></span> | <span data-ttu-id="9e29c-282">**SIP 신호 포트**</span><span class="sxs-lookup"><span data-stu-id="9e29c-282">**SIP signaling port**</span></span> | <span data-ttu-id="9e29c-283">**A?**</span><span class="sxs-lookup"><span data-stu-id="9e29c-283">**NAT?**</span></span> | <span data-ttu-id="9e29c-284">**최대 동시 세션**</span><span class="sxs-lookup"><span data-stu-id="9e29c-284">**Max concurrent sessions**</span></span> | <span data-ttu-id="9e29c-285">**미디어 바이패스 사용 가능 여부**</span><span class="sxs-lookup"><span data-stu-id="9e29c-285">**Media bypass enabled?**</span></span> |
> |-------------------------|------------------------|-----------------|---------------|----------------|------------------------|----------|-----------------------------|---------------------------|
> | <span data-ttu-id="9e29c-286">SBC-Europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e29c-286">SBC-Europe.contoso.com</span></span> | <span data-ttu-id="9e29c-287">TBD</span><span class="sxs-lookup"><span data-stu-id="9e29c-287">TBD</span></span> | <span data-ttu-id="9e29c-288">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e29c-288">\*.contoso.com</span></span> | <span data-ttu-id="9e29c-289">암스테르담</span><span class="sxs-lookup"><span data-stu-id="9e29c-289">Amsterdam</span></span> | <span data-ttu-id="9e29c-290">TBD</span><span class="sxs-lookup"><span data-stu-id="9e29c-290">TBD</span></span> | <span data-ttu-id="9e29c-291">TBD</span><span class="sxs-lookup"><span data-stu-id="9e29c-291">TBD</span></span> | <span data-ttu-id="9e29c-292">'</span><span class="sxs-lookup"><span data-stu-id="9e29c-292">Yes</span></span> | <span data-ttu-id="9e29c-293">TBD</span><span class="sxs-lookup"><span data-stu-id="9e29c-293">TBD</span></span> | <span data-ttu-id="9e29c-294">아니요</span><span class="sxs-lookup"><span data-stu-id="9e29c-294">No</span></span> |
> | <span data-ttu-id="9e29c-295">SBC-Asia.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e29c-295">SBC-Asia.contoso.com</span></span> | <span data-ttu-id="9e29c-296">TBD</span><span class="sxs-lookup"><span data-stu-id="9e29c-296">TBD</span></span> | <span data-ttu-id="9e29c-297">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e29c-297">\*.contoso.com</span></span> | <span data-ttu-id="9e29c-298">홍콩 특별 행정구</span><span class="sxs-lookup"><span data-stu-id="9e29c-298">Hong Kong SAR</span></span> | <span data-ttu-id="9e29c-299">TBD</span><span class="sxs-lookup"><span data-stu-id="9e29c-299">TBD</span></span> | <span data-ttu-id="9e29c-300">TBD</span><span class="sxs-lookup"><span data-stu-id="9e29c-300">TBD</span></span> | <span data-ttu-id="9e29c-301">아니요</span><span class="sxs-lookup"><span data-stu-id="9e29c-301">No</span></span> | <span data-ttu-id="9e29c-302">TBD</span><span class="sxs-lookup"><span data-stu-id="9e29c-302">TBD</span></span> | <span data-ttu-id="9e29c-303">'</span><span class="sxs-lookup"><span data-stu-id="9e29c-303">Yes</span></span> |
> | <span data-ttu-id="9e29c-304">SBC-Africa.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e29c-304">SBC-Africa.contoso.com</span></span> | <span data-ttu-id="9e29c-305">TBD</span><span class="sxs-lookup"><span data-stu-id="9e29c-305">TBD</span></span> | <span data-ttu-id="9e29c-306">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e29c-306">\*.contoso.com</span></span> | <span data-ttu-id="9e29c-307">요하네스버그</span><span class="sxs-lookup"><span data-stu-id="9e29c-307">Johannesburg</span></span> | <span data-ttu-id="9e29c-308">TBD</span><span class="sxs-lookup"><span data-stu-id="9e29c-308">TBD</span></span> | <span data-ttu-id="9e29c-309">TBD</span><span class="sxs-lookup"><span data-stu-id="9e29c-309">TBD</span></span> | <span data-ttu-id="9e29c-310">'</span><span class="sxs-lookup"><span data-stu-id="9e29c-310">Yes</span></span> | <span data-ttu-id="9e29c-311">TBD</span><span class="sxs-lookup"><span data-stu-id="9e29c-311">TBD</span></span> | <span data-ttu-id="9e29c-312">'</span><span class="sxs-lookup"><span data-stu-id="9e29c-312">Yes</span></span> |

<!--ENDOFSECTION-->

## <a name="voice-routing"></a><span data-ttu-id="9e29c-313">음성 라우팅</span><span class="sxs-lookup"><span data-stu-id="9e29c-313">Voice routing</span></span>

<span data-ttu-id="9e29c-314">직접 라우팅에 대 한 통화를 특정 SBCs로 라우팅하려면 Microsoft 전화 시스템을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-314">You need to configure Microsoft Phone System to route the calls to the specific SBCs for Direct Routing.</span></span> <span data-ttu-id="9e29c-315">다음을 기준으로 음성 경로를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-315">You can configure voice routes based on:</span></span>

-   <span data-ttu-id="9e29c-316">번호 패턴 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-316">Called number pattern.</span></span>

-   <span data-ttu-id="9e29c-317">번호 패턴 + 통화를 하는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-317">Called number pattern + the user who makes the call.</span></span>


<span data-ttu-id="9e29c-318">통화 라우팅은 다음 요소로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-318">Call routing is made up of the following elements:</span></span>

-   <span data-ttu-id="9e29c-319">음성 라우팅 정책 – PSTN 사용을 위한 컨테이너 사용자 또는 여러 사용자에 게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-319">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span>

-   <span data-ttu-id="9e29c-320">PSTN 사용 – 음성 경로 및 PSTN 사용량을 위한 컨테이너 다른 음성 라우팅 정책에서 공유 가능</span><span class="sxs-lookup"><span data-stu-id="9e29c-320">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span>

-   <span data-ttu-id="9e29c-321">음성 경로 – 전화 번호 패턴과 패턴과 일치 하는 통화에 사용할 온라인 PSTN 게이트웨이 집합</span><span class="sxs-lookup"><span data-stu-id="9e29c-321">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where the calling number matches the pattern</span></span>

-   <span data-ttu-id="9e29c-322">SBC의 온라인 PSTN 게이트웨이 포인터에는 호출이 호출 될 때 적용 되는 구성 (예: 정방향 P-어설션된-Id (PAI) 또는 기본 설정 코덱)이 저장 됩니다. 음성 경로에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-322">Online PSTN Gateway - pointer at SBC, also stores the configuration that’s applied when a call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span>

<span data-ttu-id="9e29c-323">전화 요금제와 함께 직접 라우팅이 가능 하도록 음성 경로를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-323">You can configure your voice routes with Direct Routing to coexist with Calling Plans.</span></span> <span data-ttu-id="9e29c-324">이 구성을 통해 착신 지를 사용 하 여 전화 요금제가 특정 SBCs에 대 한 일부 통화를 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-324">That configuration allows Calling Plans to route some of the calls to the specific SBCs by using Direct Routing.</span></span>

> [!TIP]
> <span data-ttu-id="9e29c-325">SBCs는 *활성* 및 *백업*으로 지정 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-325">SBCs can be designated as *active* and *backup*.</span></span> <span data-ttu-id="9e29c-326">즉,이 번호 패턴에 대해 활성화로 구성 된 SBC 또는 숫자 패턴 + 특정 사용자를 사용할 수 없는 경우에는 통화가 백업 SBC로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-326">That means when the SBC that’s configured as active for this number pattern — or number pattern + specific user—isn’t available, the calls will be routed to a backup SBC.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="9e29c-327">결정 사항</span><span class="sxs-lookup"><span data-stu-id="9e29c-327">Decision points</span></span>|<ul><li><span data-ttu-id="9e29c-328">직접 라우팅 구현 범위에서 사용자 위치 또는 사무실을 지원 하기 위해 만들 음성 라우팅 정책, PSTN 용도, 음성 경로를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-328">Decide the voice routing policies, PSTN usages, and voice routes that you’ll create to support user locations or offices in scope for the Direct Routing implementation.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="9e29c-329">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9e29c-329">Next steps</span></span>|<ul><li><span data-ttu-id="9e29c-330">조직의 음성 라우팅 정책, PSTN 용도, 음성 경로를 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-330">Document voice routing policies, PSTN usages, and voice routes  for your organization.</span></span><li><span data-ttu-id="9e29c-331">정의한 각 음성 라우팅 정책에 할당할 사용자를 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-331">Document the users to be assigned for each voice routing policy you define.</span></span></ul>|

> [!TIP]
> <span data-ttu-id="9e29c-332">다음 서식 파일을 사용 하 여 다이렉트 라우팅 배포에 대 한 음성 정책을 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-332">Use the following template to document the voice policies for your Direct Routing deployment.</span></span>
> 
> | <span data-ttu-id="9e29c-333">**PSTN 사용**</span><span class="sxs-lookup"><span data-stu-id="9e29c-333">**PSTN usage**</span></span> | <span data-ttu-id="9e29c-334">**음성 경로**</span><span class="sxs-lookup"><span data-stu-id="9e29c-334">**Voice route**</span></span> | <span data-ttu-id="9e29c-335">**번호 패턴**</span><span class="sxs-lookup"><span data-stu-id="9e29c-335">**Number pattern**</span></span> | <span data-ttu-id="9e29c-336">**중요도**</span><span class="sxs-lookup"><span data-stu-id="9e29c-336">**Priority**</span></span> | <span data-ttu-id="9e29c-337">**하더라도**</span><span class="sxs-lookup"><span data-stu-id="9e29c-337">**SBC**</span></span> | <span data-ttu-id="9e29c-338">**설명**</span><span class="sxs-lookup"><span data-stu-id="9e29c-338">**Description**</span></span> |
> |----------------|-----------------|----------------------------|--------------|-----------------------------------|-----------------------------------------------------------------------------------------|
> | <span data-ttu-id="9e29c-339">미국만</span><span class="sxs-lookup"><span data-stu-id="9e29c-339">US only</span></span> | <span data-ttu-id="9e29c-340">"Redmond 1"</span><span class="sxs-lookup"><span data-stu-id="9e29c-340">“Redmond 1”</span></span> | <span data-ttu-id="9e29c-341">\^\\+ 1 (425\|206) (\\d{7})\$</span><span class="sxs-lookup"><span data-stu-id="9e29c-341">\^\\+1(425\|206)(\\d{7})\$</span></span> | <span data-ttu-id="9e29c-342">raid-1</span><span class="sxs-lookup"><span data-stu-id="9e29c-342">1</span></span> | <span data-ttu-id="9e29c-343">sbc1.contoso.com sbc2.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e29c-343">sbc1.contoso.com sbc2.contoso.com</span></span> | <span data-ttu-id="9e29c-344">호출 되는 번호 + 1 425 XXX XX XX 또는 + 1 206 XXX XX XX의 활성 경로</span><span class="sxs-lookup"><span data-stu-id="9e29c-344">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span> |
> | <span data-ttu-id="9e29c-345">미국만</span><span class="sxs-lookup"><span data-stu-id="9e29c-345">US only</span></span> | <span data-ttu-id="9e29c-346">"Redmond 2"</span><span class="sxs-lookup"><span data-stu-id="9e29c-346">“Redmond 2”</span></span> | <span data-ttu-id="9e29c-347">\^\\+ 1 (425\|206) (\\d{7})\$</span><span class="sxs-lookup"><span data-stu-id="9e29c-347">\^\\+1(425\|206)(\\d{7})\$</span></span> | <span data-ttu-id="9e29c-348">2</span><span class="sxs-lookup"><span data-stu-id="9e29c-348">2</span></span> | <span data-ttu-id="9e29c-349">sbc3.contoso.com sbc4.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e29c-349">sbc3.contoso.com sbc4.contoso.com</span></span> | <span data-ttu-id="9e29c-350">호출 되는 번호에 대 한 백업 경로 + 1 425 XXX XX XX 또는 + 1 206 XXX XX XX</span><span class="sxs-lookup"><span data-stu-id="9e29c-350">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span> |
> | <span data-ttu-id="9e29c-351">미국만</span><span class="sxs-lookup"><span data-stu-id="9e29c-351">US only</span></span> | <span data-ttu-id="9e29c-352">"기타 + 1"</span><span class="sxs-lookup"><span data-stu-id="9e29c-352">"Other +1”</span></span> | <span data-ttu-id="9e29c-353">\^\\+ 1 (\\d{10})\$</span><span class="sxs-lookup"><span data-stu-id="9e29c-353">\^\\+1(\\d{10})\$</span></span> | <span data-ttu-id="9e29c-354">3-4</span><span class="sxs-lookup"><span data-stu-id="9e29c-354">3</span></span> | <span data-ttu-id="9e29c-355">sbc5.contoso.com sbc6.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e29c-355">sbc5.contoso.com sbc6.contoso.com</span></span> | <span data-ttu-id="9e29c-356">호출 되는 번호에 대 한 경로 + 1 XXX XXX XX XX (+ 1 425 XXX xx xx 또는 + 1 206 XXX XX xx 제외)</span><span class="sxs-lookup"><span data-stu-id="9e29c-356">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span> |
> | <span data-ttu-id="9e29c-357">국제화</span><span class="sxs-lookup"><span data-stu-id="9e29c-357">International</span></span> | <span data-ttu-id="9e29c-358">국제화</span><span class="sxs-lookup"><span data-stu-id="9e29c-358">International</span></span> | <span data-ttu-id="9e29c-359">\\d +</span><span class="sxs-lookup"><span data-stu-id="9e29c-359">\\d+</span></span> | <span data-ttu-id="9e29c-360">4(tcp/ipv4)</span><span class="sxs-lookup"><span data-stu-id="9e29c-360">4</span></span> | <span data-ttu-id="9e29c-361">sbc2.contoso.com sbc5.contoso.com</span><span class="sxs-lookup"><span data-stu-id="9e29c-361">sbc2.contoso.com sbc5.contoso.com</span></span> | <span data-ttu-id="9e29c-362">임의의 숫자 패턴에 대 한 라우팅</span><span class="sxs-lookup"><span data-stu-id="9e29c-362">Route for any number pattern</span></span> |
> 
> [!IMPORTANT]
> <span data-ttu-id="9e29c-363">음성 라우팅 정책의 PSTN 사용은 순서 대로 적용 되며, 첫 번째 사용에서 일치 하는 항목을 찾은 경우 다른 용도는 평가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-363">The PSTN Usages in Voice Routing Policies are applied in order, and if a match is found in the first usage, other usages are never evaluated.</span></span>

<!--ENDOFSECTION-->

## <a name="calling-and-interop-policies"></a><span data-ttu-id="9e29c-364">통화 및 Interop 정책</span><span class="sxs-lookup"><span data-stu-id="9e29c-364">Calling and Interop policies</span></span>

<span data-ttu-id="9e29c-365">직접 라우팅은 Microsoft 팀 에서만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-365">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="9e29c-366">직접 라우팅을 통해 PSTN 전화를 걸거나 받으려면 팀에서 수신 전화를 받을 수 있도록 필요한 정책을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-366">To place or receive PSTN calls through Direct Routing, you need to configure the necessary policies to ensure incoming calls are received in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="9e29c-367">직접 라우팅이 가능 하도록 설정 된 사용자는 비즈니스용 Skype를 사용 하 여 다이렉트 라우팅 전화를 걸거나 받을 수 없으므로 팀 클라이언트에 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-367">Users who are enabled for Direct Routing can’t place or receive Direct Routing calls by using Skype for Business, and therefore must be deployed the Teams client.</span></span>

<span data-ttu-id="9e29c-368">다음 두 가지 방법 중 하나를 호출 하 여 팀을 기본 클라이언트로 설정 하도록 사용자를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-368">You can configure your users to set Teams as their preferred client for calls by one of the following two methods:</span></span>

-   <span data-ttu-id="9e29c-369">팀 전용 모드로 사용자 구성</span><span class="sxs-lookup"><span data-stu-id="9e29c-369">Configure the user for Teams-only mode</span></span>

-   <span data-ttu-id="9e29c-370">TeamsCallingPolicy 및 TeamsInteropPolicy를 할당 하 여 팀을 기본 호출 클라이언트로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-370">Configure Teams as the preferred calling client by assigning the TeamsCallingPolicy and the TeamsInteropPolicy.</span></span>

<span data-ttu-id="9e29c-371">자세한 내용은 [Microsoft 팀을 사용자를 위한 기본 호출 클라이언트로 설정을](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9e29c-371">For more details, see [Set Microsoft Teams as the preferred calling client for users](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).</span></span>


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|<span data-ttu-id="9e29c-372">결정 사항</span><span class="sxs-lookup"><span data-stu-id="9e29c-372">Decision points</span></span>|<ul><li><span data-ttu-id="9e29c-373">통화에 대 한 기본 클라이언트로 팀을 설정 하는 데 사용할 방법을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-373">Decide which approach you’ll use to set Teams as the preferred client for calls.</span></span></ul>|
|<img src="media/audio_conferencing_image9.png" />|<span data-ttu-id="9e29c-374">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9e29c-374">Next steps</span></span>|<ul><li><span data-ttu-id="9e29c-375">Interop 및 호출 정책을 사용 하 여 구성할 사용자를 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-375">Document the users to be configured with Interop and Calling policies.</span></span></ul>|

> [!IMPORTANT]
> <span data-ttu-id="9e29c-376">사용자가 팀 전용 모드로 구성 된 경우이 사용자는 더 이상 비즈니스용 Skype에 로그인 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-376">When a user is configured for Teams-only mode, this user can no longer sign in to Skype for Business.</span></span>

<span data-ttu-id="9e29c-377">팀 클라이언트에서 사용자에 게 통화 탭이 표시 되도록 하려면 테 넌 트에 대 한 조직 수준에서 비공개 호출을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-377">To have your users see the Calls tab in the Teams client, you need to enable private calling at an organizational level for the tenant.</span></span> <span data-ttu-id="9e29c-378">개인 통화를 설정 하는 방법에 대 한 자세한 내용은 [Microsoft 팀에 대 한 통화 사용](direct-routing-configure.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9e29c-378">See [Enable Calling for Microsoft Teams](direct-routing-configure.md) for more details on how to enable private calls.</span></span>


<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a><span data-ttu-id="9e29c-379">문서 서비스 결정</span><span class="sxs-lookup"><span data-stu-id="9e29c-379">Document service decisions</span></span>

<span data-ttu-id="9e29c-380">이 문서의 이전 섹션에 나와 있는 정보를 사용 하 여 서비스 의사 결정을 문서화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-380">Use the information from the previous sections of this article to document your service decisions.</span></span> <span data-ttu-id="9e29c-381">일반적으로이 설명서에는 다음과 같은 주요 섹션이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e29c-381">In general, this documentation will contain the following main sections:</span></span>

-   <span data-ttu-id="9e29c-382">통화 요금제 사이트 사용 목록을 포함 하는 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="9e29c-382">Phone System with Calling Plans site enablement list</span></span>

-   <span data-ttu-id="9e29c-383">보이스 메일 구성 세부 정보</span><span class="sxs-lookup"><span data-stu-id="9e29c-383">Voicemail configuration details</span></span>

-   <span data-ttu-id="9e29c-384">전화 시스템 다이렉트 라우팅 사용자에 대 한 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="9e29c-384">License assignment for Phone System Direct Routing users</span></span>

-   <span data-ttu-id="9e29c-385">SBC 구성 세부 정보</span><span class="sxs-lookup"><span data-stu-id="9e29c-385">SBC configuration details</span></span>

-   <span data-ttu-id="9e29c-386">음성 라우팅 정책 및 라우팅 세부 정보</span><span class="sxs-lookup"><span data-stu-id="9e29c-386">Voice routing policy and routing details</span></span>

-   <span data-ttu-id="9e29c-387">Interop 및 호출 정책 세부 정보</span><span class="sxs-lookup"><span data-stu-id="9e29c-387">Interop and calling policy details</span></span>

<!--ENDOFSECTION-->
