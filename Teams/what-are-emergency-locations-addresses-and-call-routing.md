---
title: 비상 전화 계획 및 관리
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
- Calling Plans
- Direct Routing
- seo-marvel-mar2020
description: 긴급 주소, 긴급 통화 라우팅, 동적 비상 전화에 대 한 정보를 포함 하 여 비상 전화에 대해 알아봅니다.
ms.openlocfilehash: 889446ca08289ccb15128bee8ca6b6170398c599
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539495"
---
# <a name="manage-emergency-calling"></a><span data-ttu-id="14c79-103">긴급 통화 관리</span><span class="sxs-lookup"><span data-stu-id="14c79-103">Manage emergency calling</span></span>

<span data-ttu-id="14c79-104">이 문서에서는 긴급 전화 관리를 위해 알아야 할 개념에 대해 설명 합니다 &mdash; . 긴급 주소, 동적 긴급 주소, 긴급 통화 라우팅에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-104">This article describes concepts you'll need to know to manage emergency calling&mdash;it includes information about emergency addresses, dynamic emergency addresses, and emergency call routing.</span></span> <span data-ttu-id="14c79-105">이 문서에서는 다음 용어를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-105">This article uses the following terminology:</span></span>

- <span data-ttu-id="14c79-106">**긴급 주소** -도심 주소는 &mdash; 조직의 비즈니스 장소에 대 한 실제 또는 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-106">**Emergency address** - A civic address&mdash;the physical or street address of a place of business for your organization.</span></span>

  <span data-ttu-id="14c79-107">예를 들어 주소 *12345 북쪽 주 주소, Redmond, WA 98052* 을 사용 하 여 긴급 통화를 적절 한 디스패치 기관으로 라우팅하고 긴급 전화 발신자를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-107">For example, the address  *12345 North Main Street, Redmond, WA 98052* is used to route emergency calls to the appropriate dispatch authorities and to assist in locating the emergency caller.</span></span>

- <span data-ttu-id="14c79-108">**장소** -일반적으로 바닥, 건물, 윙 또는 사무실 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-108">**Place** - Typically a floor, building, wing, or office number.</span></span> <span data-ttu-id="14c79-109">위치는 비상 주소와 연결 되어 건물 내에서 더 정확한 위치를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-109">Place is associated with an emergency address to give a more exact location within a building.</span></span> <span data-ttu-id="14c79-110">비상 주소와 연결 된 장소를 무제한으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-110">You can have an unlimited number of places associated with an emergency address.</span></span> <span data-ttu-id="14c79-111">예를 들어 조직에 여러 건물을 보유 하 고 있는 경우 각 건물에 각 건물에 대 한 배치 정보를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-111">For example, if your organization has multiple buildings, you might want to include place information for each building and for every floor within each building.</span></span>  

- <span data-ttu-id="14c79-112">**비상 장소** -위치는 선택적 위치로 이동 하는 도심 주소입니다 &mdash; .</span><span class="sxs-lookup"><span data-stu-id="14c79-112">**Emergency location** - A location is a civic address&mdash;with an optional place.</span></span> <span data-ttu-id="14c79-113">회사에 둘 이상의 실제 위치가 있는 경우 두 개 이상의 긴급 위치가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-113">If your business has more than one physical location, it's likely that you'll need more than one emergency location.</span></span> 

  <span data-ttu-id="14c79-114">긴급 주소를 만들면이 주소에 대 한 고유한 위치 ID가 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-114">When you create an emergency address, a unique location ID is automatically created for this address.</span></span>  <span data-ttu-id="14c79-115">긴급 주소에 위치를 추가 하는 경우 &mdash; 예를 들어 건물 주소에 층을 추가 하는 경우 &mdash; 긴급 주소와 장소 조합에 대해 위치 ID가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-115">If you add a place to an emergency address&mdash;for example, if you add a floor to a building address&mdash;a location ID is created for the combination of the emergency address and place.</span></span>  <span data-ttu-id="14c79-116">이 예제에는 도심 주소에 대 한 두 개의 위치 Id가 있습니다. 하나는 연결 된 도심 주소와 관련 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-116">In this example, there will be two location IDs: one for the civic address; one for the joined civic address and associated place.</span></span>

  <span data-ttu-id="14c79-117">사용자 또는 사이트에 응급 위치를 할당 하는 경우 사용자 또는 사이트와 연결 되는 고유한 위치 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-117">When you assign an emergency location to a user or site, it's this unique location ID that's associated with the user or site.</span></span>

- <span data-ttu-id="14c79-118">**등록 된 주소** -각 통화 계획 사용자에 게 지정 된 긴급 주소입니다. 때로는 정적 긴급 주소 또는 레코드 주소 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-118">**Registered address** - An emergency address that is assigned to each Calling Plan user; it is sometimes referred to as a static emergency address or address of record.</span></span>  <span data-ttu-id="14c79-119">(직접 라우팅 사용자에 게 등록 된 주소가 적용 되지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="14c79-119">(Registered addresses do not apply to Direct Routing users.)</span></span>

<span data-ttu-id="14c79-120">팀 관리 센터를 사용 하 여 요금제 사용자에 대 한 긴급 주소를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-120">You create emergency addresses for Calling Plan users by using the Teams admin center.</span></span>  

>[!Note]
><span data-ttu-id="14c79-121">PSTN 연결을 위해 전화 시스템의 통화 요금제 또는 전화 시스템 다이렉트 라우팅을 사용 하는지에 따라 긴급 통화를 관리 하는 방법이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-121">There are some differences in how you manage emergency calling depending on whether you are using Phone System Calling Plans or Phone System Direct Routing for your PSTN connectivity.</span></span> <span data-ttu-id="14c79-122">이러한 고려 사항은이 문서 전체에서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-122">These considerations are described throughout this article.</span></span>

## <a name="emergency-address-validation"></a><span data-ttu-id="14c79-123">긴급 주소 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="14c79-123">Emergency address validation</span></span>

<span data-ttu-id="14c79-124">사용자 또는 네트워크 식별자에 긴급 주소를 할당 하려면 긴급 주소가 "확인 됨"으로 표시 되어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-124">To assign an emergency address to a user or to a network identifier, you must ensure that the emergency address is marked as "validated."</span></span>  <span data-ttu-id="14c79-125">주소 유효성 검사는 주소가 유효한 지 확인 하 고, 할당 된 후에는 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-125">Address validation ensures that the address is legitimate, and that it cannot be modified after it is assigned.</span></span> 

<span data-ttu-id="14c79-126">팀 관리 센터에서 주소 맵 검색 기능을 사용 하 여 긴급 주소를 정의 하는 경우 주소가 자동으로 유효성이 검사 된 것으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-126">If you define an emergency address by using the address map search feature in the Teams admin center, the address is automatically marked as validated.</span></span> <span data-ttu-id="14c79-127">유효한 긴급 주소는 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-127">You cannot modify a validated emergency address.</span></span> <span data-ttu-id="14c79-128">따라서 주소의 형식 또는 표현이 변경 되 면 업데이트 된 형식으로 새 주소를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-128">Therefore, if the format or representation of the address changes, you must create a new address with the updated format.</span></span>


## <a name="emergency-address-geo-codes"></a><span data-ttu-id="14c79-129">긴급 주소 지역 코드</span><span class="sxs-lookup"><span data-stu-id="14c79-129">Emergency address geo codes</span></span>

<span data-ttu-id="14c79-130">각 긴급 주소에는 지역 코드 (위도 및 경도)가 연결 되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-130">Each emergency address can have a geo code (latitude and longitude) associated with it.</span></span> <span data-ttu-id="14c79-131">이러한 지역 코드는 일부 국가에서 동적 위치로 비상 통화를 라우팅하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-131">These geo codes are used in some countries to assist in routing emergency calls with dynamic locations.</span></span> 

<span data-ttu-id="14c79-132">팀 관리 센터에서 주소 맵 검색 기능을 사용 하 여 긴급 주소를 정의 하는 경우 지역 코드가 긴급 주소에 자동으로 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-132">If you define an emergency address by using the address map search feature in the Teams admin center, the geo code is automatically associated with an emergency address.</span></span> <span data-ttu-id="14c79-133">PowerShell을 사용 하 여 주소를 정의 하는 경우 지역 코드를 주소와 연결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-133">You can also associate geo codes with an address if you define the address by using PowerShell.</span></span> <span data-ttu-id="14c79-134">그러나 팀 관리 센터의 지도 검색 기능을 사용 하 여 전화 요금제에 대 한 긴급 주소를 만드는 것이 좋으며,이는 주소가 서식 지정 되 고 유효성을 검사 하 고 해당 지역 코드를가지고 있는지 확인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-134">However, Microsoft recommends that you create emergency addresses for Calling Plan by using the map search feature in Teams admin center, which will ensure that the addresses are formatted, validated, and have the appropriate geo codes.</span></span>  

>[!Important]
><span data-ttu-id="14c79-135">동적 비상 전화에 대 한 네트워크 식별자에 비상 위치를 할당 하려면 긴급 주소에는 적절 한 지역 코드가 포함 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-135">To assign an emergency location to a network identifier for dynamic emergency calling, the emergency address must contain an appropriate geo code.</span></span>


## <a name="considerations-for-calling-plans"></a><span data-ttu-id="14c79-136">통화 요금제에 대 한 고려 사항</span><span class="sxs-lookup"><span data-stu-id="14c79-136">Considerations for Calling Plans</span></span>

<span data-ttu-id="14c79-137">해당 지역에서 통화 요금제를 사용할 수 있는지 여부를 확인 하려면 [전화 요금제에 대 한 국가 및 지역 사용 가능성](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="14c79-137">To find out whether Calling Plans is available in your area, see [Country and region availability for Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span>


### <a name="emergency-call-enablement"></a><span data-ttu-id="14c79-138">비상 전화를 통한 통화</span><span class="sxs-lookup"><span data-stu-id="14c79-138">Emergency call enablement</span></span>

<span data-ttu-id="14c79-139">각 통화 계획 사용자는 비상 전화에 대해 자동으로 사용 하도록 설정 되며 지정 된 전화 번호와 연결 된 긴급 주소가 등록 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-139">Each Calling Plan user is automatically enabled for emergency calling and is required to have a registered emergency address associated with their assigned telephone number.</span></span> 

<span data-ttu-id="14c79-140">전화 번호에 연결 되어 있어야 하는 위치는 국가/지역에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-140">When the location must be associated to the telephone number depends on the country/region:</span></span>

- <span data-ttu-id="14c79-141">예를 들어 미국 및 캐나다의 경우 사용자에 게 번호를 할당 하면 비상 위치가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-141">In the United States and Canada, for example, an emergency location is required when a number is assigned to a user.</span></span>

- <span data-ttu-id="14c79-142">&mdash;유럽, 중동, 아프리카 (EMEA) 등의 다른 국가에서는 &mdash; Office 365에서 전화 번호를 받을 때 또는 다른 서비스 공급자 또는 통신 업체에서 전송 되는 경우 긴급 위치가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-142">For other countries&mdash;such as in Europe, the Middle East, and Africa (EMEA)&mdash;an emergency location is required when you get the phone number from Office 365 or when it's transferred from another service provider or carrier.</span></span>

### <a name="dynamic-emergency-calling"></a><span data-ttu-id="14c79-143">동적 비상 전화</span><span class="sxs-lookup"><span data-stu-id="14c79-143">Dynamic emergency calling</span></span>

<span data-ttu-id="14c79-144">Microsoft 호출 요금제에 대 한 동적 비상 통화는 팀 클라이언트의 현재 위치를 기반으로 비상 전화를 구성 하 고 라우팅할 수 있는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-144">Dynamic emergency calling for Microsoft Calling Plans provides the capability to configure and route emergency calls based on the current location of the Teams client.</span></span> <span data-ttu-id="14c79-145">적절 한 공개 안전 응답 시점 (PSAP)으로 자동 라우팅 하거나 보안 데스크 직원에 게 알리는 기능은 팀 사용자의 사용 국가에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-145">The ability to do automatic routing to the appropriate Public Safety Answering Point (PSAP) or to notify security desk personnel varies depending on the country of usage of the Teams user.</span></span>  

<span data-ttu-id="14c79-146">통화 요금제 사용자의 경우 긴급 전화 라우팅을 위한 동적 위치는 미국 에서만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-146">For Calling Plan users, dynamic location for routing emergency calls is only supported in the United States as follows.</span></span> <span data-ttu-id="14c79-147">(동적 비상 통화 및 직접 라우팅에 대 한 자세한 내용은 [직접 라우팅에 대 한 고려 사항을](#considerations-for-direct-routing)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="14c79-147">(For information about dynamic emergency calling and Direct Routing, see [Considerations for Direct Routing](#considerations-for-direct-routing).</span></span>

- <span data-ttu-id="14c79-148">미국 내에 있는 팀 클라이언트에서 미국 내의 긴급 주소를 동적으로 획득 하는 경우, 해당 주소는 등록 된 주소 대신 긴급 라우팅에 사용 되며, 주소가 처리 되는 영역에서 PSAP로 자동 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-148">If a Teams client for a United States Calling Plan user dynamically acquires an emergency address within the United States, that address is used for emergency routing instead of the registered address, and the call will be automatically routed to the PSAP in the serving area of the address.</span></span>

- <span data-ttu-id="14c79-149">미국 전화 플랜 사용자를 위한 팀 클라이언트가 미국 내에서 긴급 주소를 동적으로 획득 하지 않은 경우, 등록 된 긴급 주소를 사용 하 여 화면을 통해 통화를 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-149">If a Teams client for a United States Calling Plan user doesn't dynamically acquire an emergency address within the United States, then the registered emergency address is used to help screen and route the call.</span></span> <span data-ttu-id="14c79-150">그러나 호출자를 적절 한 PSAP에 연결 하기 전에 업데이트 된 주소가 필요한 지 확인 하기 위해 통화가 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-150">However, the call will be screened to determine if an updated address is required before connecting the caller to the appropriate PSAP.</span></span>

<span data-ttu-id="14c79-151">미국에서는 네트워크 식별자에 할당 된 비상 위치에 해당 하는 도심 주소를 구성 &mdash; 하 고 연결 된 지역 코드를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-151">In the United States, you must configure the civic address that is part of the emergency locations that are assigned to network identifiers&mdash;and include the associated geo codes.</span></span> <span data-ttu-id="14c79-152">자세한 내용은 [동적 비상 전화 계획 및 구성을](configure-dynamic-emergency-calling.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="14c79-152">For more information, see [Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>


### <a name="emergency-call-routing"></a><span data-ttu-id="14c79-153">긴급 통화 라우팅</span><span class="sxs-lookup"><span data-stu-id="14c79-153">Emergency call routing</span></span>

<span data-ttu-id="14c79-154">팀에서 계획 사용자가 긴급 전화 번호로 전화를 거는 경우, 통화가 PSAP로 라우팅되는 방법은 다음에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-154">When a Teams Calling Plan user dials an emergency number, how the call is routed to the PSAP depends on the following:</span></span>

- <span data-ttu-id="14c79-155">팀 클라이언트에서 긴급 주소를 동적으로 결정 하는지 여부</span><span class="sxs-lookup"><span data-stu-id="14c79-155">Whether the emergency address is dynamically determined by the Teams client.</span></span>

- <span data-ttu-id="14c79-156">긴급 주소가 사용자의 전화 번호와 연결 된 등록 된 주소인 지 여부</span><span class="sxs-lookup"><span data-stu-id="14c79-156">Whether the emergency address is the registered address associated with the user's phone number.</span></span>

- <span data-ttu-id="14c79-157">해당 국가의 비상 전화 네트워크입니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-157">The emergency calling network of that country.</span></span>

  <span data-ttu-id="14c79-158">**미국에서:**</span><span class="sxs-lookup"><span data-stu-id="14c79-158">**In the United States:**</span></span>

  - <span data-ttu-id="14c79-159">팀 클라이언트가 테 넌 트 정의 동적인 긴급 위치에 있는 경우 해당 클라이언트의 비상 호출은 해당 지리적 위치를 처리 하는 PSAP에 자동으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-159">If a Teams client is located at a tenant-defined dynamic emergency location, emergency calls from that client are automatically routed to the PSAP serving that geographic location.</span></span> 

  - <span data-ttu-id="14c79-160">팀 클라이언트가 테 넌 트로 정의 된 동적 비상 위치에 없으면 해당 클라이언트의 비상 전화를 국가 콜 센터에서 확인 하 여 해당 지리적 위치를 처리 하는 PSAP로 호출을 전달 하기 전에 해당 전화를 통해 발신자의 위치를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-160">If a Teams client is not located at a tenant-defined dynamic emergency location, emergency calls from that client are screened by a national call center to determine the location of the caller before transferring the call to the PSAP serving that geographic location.</span></span>

  - <span data-ttu-id="14c79-161">응급 발신자가 비상 위치를 차단 센터로 업데이트할 수 없는 경우 통화는 등록 된 주소를 처리 하는 PSAP로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-161">If an emergency caller is unable to update their emergency location to the screening center, the call will be transferred to the PSAP serving the caller's registered address.</span></span>

  <span data-ttu-id="14c79-162">**캐나다, 아일랜드, 영국에**는 통화를 적절 한 디스패치 센터에 연결 하기 전에 사용자의 현재 위치를 확인 하기 위해 먼저 긴급 통화가 차단 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-162">**In Canada, Ireland, and the United Kingdom**, emergency calls are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center.</span></span> 

  <span data-ttu-id="14c79-163">**프랑스, 독일, 스페인에서**비상 전화는 호출자의 위치에 관계 없이 해당 번호와 연결 된 비상 주소로 서비스를 제공 하는 psap로 직접 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-163">**In France, Germany, and Spain**, emergency calls are routed directly to the PSAP serving the emergency address associated with the number regardless of the location of the caller.</span></span>

  <span data-ttu-id="14c79-164">**네덜란드에서**비상 전화는 호출자의 위치에 관계 없이 해당 번호의 지역 코드에 대 한 psap로 직접 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-164">**In the Netherlands**, emergency calls are routed directly to the PSAP for the local area code of the number regardless of the location of the caller.</span></span>

  <span data-ttu-id="14c79-165">**오스트레일리아에서는**통신 회사 파트너가 긴급 주소를 구성 하 고 라우트 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-165">**In Australia**, emergency addresses are configured and routed by the carrier partner.</span></span>

  <span data-ttu-id="14c79-166">**일본에서는**비상 통화가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-166">**In Japan**, emergency calling is not supported.</span></span>


<span data-ttu-id="14c79-167">자세한 내용은 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="14c79-167">For more information, see:</span></span>

- [<span data-ttu-id="14c79-168">통화 플랜</span><span class="sxs-lookup"><span data-stu-id="14c79-168">Calling Plans</span></span>](calling-plan-landing-page.md)

- [<span data-ttu-id="14c79-169">통화 요금제에 사용 되는 다른 종류의 전화 번호</span><span class="sxs-lookup"><span data-stu-id="14c79-169">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

- [<span data-ttu-id="14c79-170">긴급 통화 사용 약관</span><span class="sxs-lookup"><span data-stu-id="14c79-170">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-direct-routing"></a><span data-ttu-id="14c79-171">직접 라우팅에 대 한 고려 사항</span><span class="sxs-lookup"><span data-stu-id="14c79-171">Considerations for Direct Routing</span></span>

<span data-ttu-id="14c79-172">해당 지역에서 통화 요금제를 사용할 수 없거나 기존 통신 회사를 유지 하려는 경우 [다이렉트 라우팅을](direct-routing-landing-page.md)고려 하세요.</span><span class="sxs-lookup"><span data-stu-id="14c79-172">If Calling Plans are not available in your area or you want to keep your existing carrier, consider [Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="14c79-173">자세한 내용은 [직접 라우팅 구성](direct-routing-configure.md) 및 [긴급 통화 라우팅 정책 관리](manage-emergency-call-routing-policies.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="14c79-173">For more information, see [Configure Direct Routing](direct-routing-configure.md) and [Manage emergency call routing policies](manage-emergency-call-routing-policies.md).</span></span>

### <a name="emergency-call-enablement-and-configuration"></a><span data-ttu-id="14c79-174">응급 통화 설정 및 구성</span><span class="sxs-lookup"><span data-stu-id="14c79-174">Emergency call enablement and configuration</span></span>

<span data-ttu-id="14c79-175">팀 TeamsEmergencyCallRoutingPolicy (응급 통화 라우팅 정책)를 사용 하 여 긴급 전화 번호 및 연결 된 라우팅 대상을 정의 하 여 다이렉트 라우팅 사용자에 대 한 긴급 통화 정책을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-175">You must define emergency calling policies for Direct Routing users by using a Teams emergency call routing policy (TeamsEmergencyCallRoutingPolicy) to define emergency numbers and their associated routing destination.</span></span> <span data-ttu-id="14c79-176">(등록 된 비상 위치는 다이렉트 라우팅 사용자에 게 지원 되지 않음에 유의 하세요.)</span><span class="sxs-lookup"><span data-stu-id="14c79-176">(Note that registered emergency locations are not supported for Direct Routing users.)</span></span>

<span data-ttu-id="14c79-177">긴급 통화 라우팅 정책을 팀 직접 라우팅 사용자 계정, 네트워크 사이트 또는 둘 다에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-177">You can assign an emergency call routing policy  to a Teams Direct Routing user account, a network site, or both.</span></span> <span data-ttu-id="14c79-178">팀 클라이언트가 네트워크 연결을 시작 하거나 변경 하는 경우 팀은 다음과 같이 클라이언트가 있는 네트워크 사이트의 조회를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-178">When a Teams client starts or changes a network connection, Teams performs a lookup of the network site where the client is located as follows:</span></span>

- <span data-ttu-id="14c79-179">긴급 통화 라우팅 정책이 사이트와 연결 된 경우에는 사이트 정책을 사용 하 여 비상 전화를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-179">If an emergency call routing policy is associated with the site, then the site policy is used to configure emergency calling.</span></span>

- <span data-ttu-id="14c79-180">사이트와 연결 된 비상 통화 라우팅 정책이 없거나 클라이언트가 정의 되지 않은 사이트에 연결 된 경우에는 사용자 계정과 연결 된 비상 전화 라우팅 정책이 비상 전화를 구성 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-180">If there is no emergency call routing policy associated with the site, or if the client is connected at an undefined site, then the emergency call routing policy associated with the user account is used to configure emergency calling.</span></span> 

- <span data-ttu-id="14c79-181">팀 클라이언트가 긴급 통화 라우팅 정책을 가져올 수 없는 경우 사용자는 비상 전화를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-181">If the Teams client is unable to obtain an emergency call routing policy, then the user is not enabled for emergency calling.</span></span>

### <a name="dynamic-emergency-calling"></a><span data-ttu-id="14c79-182">동적 비상 전화</span><span class="sxs-lookup"><span data-stu-id="14c79-182">Dynamic emergency calling</span></span>

<span data-ttu-id="14c79-183">다이렉트 라우팅 사용자 용 팀 클라이언트는 동적 긴급 주소를 얻을 수 있으며,이는 호출자의 위치에 따라 동적으로 호출을 라우팅하는 데 사용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-183">Teams clients for Direct Routing users can acquire a dynamic emergency address, which can be used to dynamically route calls based upon the location of the caller.</span></span> <span data-ttu-id="14c79-184">자세한 내용은 [동적 긴급 통화 구성을](configure-dynamic-emergency-calling.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="14c79-184">For more information, see [Configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>

### <a name="emergency-call-routing"></a><span data-ttu-id="14c79-185">긴급 통화 라우팅</span><span class="sxs-lookup"><span data-stu-id="14c79-185">Emergency call routing</span></span>

<span data-ttu-id="14c79-186">긴급 통화 라우팅 정책은 온라인 PSTN 사용을 참조 하며, 적절 한 PSTN 게이트웨이로 긴급 통화를 제대로 라우팅하도록 적절 한 직접 라우팅 구성이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-186">The emergency call routing policy references an online PSTN usage, which must have the appropriate Direct Routing configuration to properly route the emergency calls to the appropriate PSTN gateway(s).</span></span> <span data-ttu-id="14c79-187">특히 긴급 전화 접속 문자열에 대 한 OnlineVoiceRoute 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-187">In particular, you must ensure that there is an OnlineVoiceRoute for the emergency dial string.</span></span> <span data-ttu-id="14c79-188">자세한 내용은 [직접 라우팅 구성을](direct-routing-configure.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="14c79-188">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span> 

<span data-ttu-id="14c79-189">(참고: 팀 클라이언트 앞에는 비즈니스용 Skype 클라이언트와 비슷한 방식으로 긴급 전화 번호 앞에 "+" 기호가 있습니다 (즉, + 911).</span><span class="sxs-lookup"><span data-stu-id="14c79-189">(Note: Teams clients prepend the "+" sign in front of emergency numbers in a similar manner that Skype for Business client does; that is, +911.</span></span> <span data-ttu-id="14c79-190">이 동작은 팀 비상 통화가 더 이상 번호 앞에 있는 "+"를 보낼 수 없도록 향후 달에 수정 될 예정입니다. 즉, 911.)</span><span class="sxs-lookup"><span data-stu-id="14c79-190">This behavior will be modified in the coming months so that Teams emergency calls will no longer be sending a "+" preceding the number; that is, 911.)</span></span>

<span data-ttu-id="14c79-191">직접 라우팅 사용자를 위해 긴급 통화를 동적으로 라우팅하는 기능은 해당 국가 내의 비상 전화 네트워크에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-191">The ability to dynamically route emergency calls for Direct Routing users varies depending on the emergency calling network within a given country.</span></span> <span data-ttu-id="14c79-192">두 가지 해결 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-192">There are two solutions available:</span></span>

- <span data-ttu-id="14c79-193">긴급 라우팅 서비스 공급자 (미국 전용)</span><span class="sxs-lookup"><span data-stu-id="14c79-193">Emergency Routing Service Providers (US only)</span></span> 
- <span data-ttu-id="14c79-194">비상 위치 Id 번호 (ELIN) 게이트웨이 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="14c79-194">Emergency Location Identification Number (ELIN) gateway applications</span></span>

#### <a name="emergency-routing-service-providers"></a><span data-ttu-id="14c79-195">응급 라우팅 서비스 공급자</span><span class="sxs-lookup"><span data-stu-id="14c79-195">Emergency Routing Service Providers</span></span>

<span data-ttu-id="14c79-196">미국에는 발신자의 위치에 따라 긴급 통화를 자동으로 라우팅할 수 있는 여러 개의 인증 된 ERSPs (응급 라우팅 서비스 공급자)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-196">In the United States, there are numerous certified Emergency Routing Service Providers (ERSPs) that can automatically route emergency calls based upon the location of the caller.</span></span>

- <span data-ttu-id="14c79-197">긴급 라우팅 서비스 공급자가 직접 라우팅 배포에 통합 되어 있는 경우 동적으로 구입한 위치가 있는 비상 통화가 해당 위치를 처리 하는 PSAP (공개 안전 응답 시점)로 자동으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-197">If an Emergency Routing Service Provider is integrated into a Direct Routing deployment, emergency calls with a dynamically acquired location will be automatically routed to the Public Safety Answering Point (PSAP) serving that location.</span></span>

-  <span data-ttu-id="14c79-198">업데이트 된 위치에 따라 적절 한 디스패치 센터에 전화를 연결 하기 전에 동적으로 구입 위치 없이 긴급 통화를 먼저 차단 하 여 사용자의 현재 위치를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-198">Emergency calls without a dynamically acquired location are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center based upon the updated location.</span></span>

<span data-ttu-id="14c79-199">자세한 내용은 [직접 라우팅을 위해 인증 된 세션 경계 컨트롤러](direct-routing-border-controllers.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="14c79-199">For more information, see [Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>


#### <a name="emergency-location-identification-number-elin-applications"></a><span data-ttu-id="14c79-200">비상 위치 Id 번호 (ELIN) 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="14c79-200">Emergency Location Identification Number (ELIN) applications</span></span>

<span data-ttu-id="14c79-201">SBCs (세션 경계 컨트롤러)는 비상 위치 Id 번호 (ELIN) 응용 프로그램을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-201">Session Border Controllers (SBCs) can include Emergency Location Identification Number (ELIN) applications.</span></span> <span data-ttu-id="14c79-202">응용 프로그램의 SBC ELIN 직접 라우팅 배포에 통합 되어 있는 경우 응용 프로그램의 ELIN 긴급 주소 및 연결 된 전화 번호를 구성한 다음 해당 PSTN의 비상 전화 데이터베이스에 레코드의 ELIN 업로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-202">If an SBC ELIN application is integrated into a Direct Routing deployment, you must configure the emergency addresses and associated telephone numbers in the ELIN application, and then upload the ELIN records to the emergency calling database in the respective PSTN.</span></span>  <span data-ttu-id="14c79-203">식별자가 ELIN 인 팀의 비상 위치는 응용 프로그램의 ELIN 내에서와 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-203">Teams emergency locations with an ELIN identifier must match those within the ELIN application.</span></span>

<span data-ttu-id="14c79-204">동적으로 취득 하는 위치가 포함 된 비상 통화가 해당 SBC, 즉 응용 프로그램의 ELIN 같이 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-204">When an emergency call with a dynamically acquired location is routed to the appropriate SBC, the ELIN application:</span></span>

- <span data-ttu-id="14c79-205">호출자의 긴급 위치를 구문 분석 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-205">Parses the emergency location of the caller.</span></span>
- <span data-ttu-id="14c79-206">위치를 레코드의 ELIN와 일치 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-206">Matches the location to an ELIN record.</span></span>
- <span data-ttu-id="14c79-207">비상 연락망의 번호를 전화 번호의 ELIN으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-207">Substitutes the emergency caller's number with the ELIN phone number.</span></span>
- <span data-ttu-id="14c79-208">해당 위치를 처리 하는 PSAP에 대 한 통화를 라우팅하고, 발송자는 업로드 된 ELIN record에서 위치를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-208">Routes the call to the PSAP serving that location, and then the dispatchers obtain the location from the uploaded ELIN record.</span></span>

<span data-ttu-id="14c79-209">비상 번호로 다시 전화를 받으면, 응용 프로그램의 ELIN는 원래 비상 전화 번호로 대체 하는 역 번호를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-209">Upon a call back to the emergency number, the ELIN application will do the reverse called number substitution to that of the original emergency caller.</span></span> 

<span data-ttu-id="14c79-210">자세한 내용은 [직접 라우팅을 위해 인증 된 세션 경계 컨트롤러](direct-routing-border-controllers.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="14c79-210">For more information, see [Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>


## <a name="security-desk-notification"></a><span data-ttu-id="14c79-211">보안 데스크 알림</span><span class="sxs-lookup"><span data-stu-id="14c79-211">Security desk notification</span></span>

<span data-ttu-id="14c79-212">Microsoft 통화 요금제와 전화 시스템 직접 라우팅 모두에서 보안 데스크 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-212">Security desk notification is available with both Microsoft Calling Plans and Phone System Direct Routing.</span></span>

<span data-ttu-id="14c79-213">팀 TeamsEmergencyCallingPolicy (비상 통화 정책)를 사용 하 여 비상 전화 중에 알림을 받을 사용자를 구성 하 고, 채팅 전용, conferenced, 음소거 또는 conferenced, 음소거 해제 등을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-213">You use a Teams emergency calling policy (TeamsEmergencyCallingPolicy) to configure who should be notified during an emergency call and how they are notified: chat only, conferenced in and muted, or conferenced in and muted but with the ability to unmute.</span></span>  <span data-ttu-id="14c79-214">또한 사용자 또는 그룹의 외부 PSTN 번호를 지정 하 여 비상 전화를 걸고 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-214">You can also specify an external PSTN number of a user or group to call and join the emergency call.</span></span> 

<span data-ttu-id="14c79-215">긴급 통화 정책은 팀 사용자 계정에 부여 하거나, 네트워크 사이트에 할당 하거나, 둘 다에 게 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-215">An emergency calling policy can be granted to a Teams user account, assigned to a network site, or both.</span></span>  <span data-ttu-id="14c79-216">팀 클라이언트가 네트워크 연결을 시작 하거나 변경 하는 경우 팀은 클라이언트가 있는 네트워크 사이트의 조회를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-216">When a Teams client starts or changes a network connection, Teams performs a lookup of the network site where the client is located:</span></span>

- <span data-ttu-id="14c79-217">긴급 통화 정책이 네트워크 사이트와 연결 된 경우에는 사이트 정책이 보안 데스크 알림을 구성 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-217">If an emergency calling policy is associated with a network site, then the site policy is used to configure security desk notification.</span></span>

- <span data-ttu-id="14c79-218">사이트와 연결 된 비상 전화 정책이 없거나 클라이언트가 정의 되지 않은 사이트에 연결 된 경우에는 사용자 계정과 연결 된 비상 전화 정책이 보안 데스크 알림을 구성 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-218">If there is no emergency calling policy associated with the site, or if the client is connected at an undefined site, then the emergency calling policy associated with the user account is used to configure security desk notification.</span></span>  

- <span data-ttu-id="14c79-219">팀 클라이언트가 긴급 통화 정책을 얻을 수 없으면 사용자는 보안 데스크 알림을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-219">If the Teams client is unable to obtain an emergency calling policy, then the user is not enabled for security desk notification.</span></span>

<span data-ttu-id="14c79-220">비상 전화 시, 보안 데스크는 통화에 conferenced, 보안 데스크 사용자의 경험은 팀의 비상 전화 정책에 따라 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-220">During an emergency call, a security desk is conferenced into the call and the experience of the security desk user is controlled based upon the Teams emergency calling policy.</span></span> <span data-ttu-id="14c79-221">그룹 채팅은 각 보안 데스크 구성원에 게 시작 되며, 긴급 전화 발신자의 위치는 중요 한 메시지 알림을 통해 공유 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-221">A group chat is started with each security desk member, and the location of the emergency caller is shared via an important message notification.</span></span>  <span data-ttu-id="14c79-222">회의 옵션이 정책의 일부로 구성 되어 있으면 각 보안 데스크 사용자가 회의의 일부로 추가로 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c79-222">If a conference option is configured as part of the policy, each security desk user is additionally called as part of the conference.</span></span>

    
## <a name="related-topics"></a><span data-ttu-id="14c79-223">관련 항목</span><span class="sxs-lookup"><span data-stu-id="14c79-223">Related topics</span></span>

- [<span data-ttu-id="14c79-224">긴급 전화 정책 관리</span><span class="sxs-lookup"><span data-stu-id="14c79-224">Manage emergency calling policies</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="14c79-225">긴급 통화 라우팅 정책 관리</span><span class="sxs-lookup"><span data-stu-id="14c79-225">Manage emergency call routing policies </span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="14c79-226">조직의 응급 위치 추가, 변경 또는 제거</span><span class="sxs-lookup"><span data-stu-id="14c79-226">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="14c79-227">사용자의 긴급 위치 지정 또는 변경</span><span class="sxs-lookup"><span data-stu-id="14c79-227">Assign or change an emergency location for your user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="14c79-228">동적인 긴급 전화 계획 및 구성</span><span class="sxs-lookup"><span data-stu-id="14c79-228">Plan and configure dynamic emergency calling</span></span>](configure-dynamic-emergency-calling.md)
