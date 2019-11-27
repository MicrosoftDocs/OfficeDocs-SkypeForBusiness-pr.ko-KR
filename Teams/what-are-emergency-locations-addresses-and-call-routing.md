---
title: 비상 전화, 긴급 주소, 긴급 통화 라우팅, 동적 비상 전화 계획
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
f1keywords:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
- Direct Routing
description: 긴급 주소, 긴급 통화 라우팅, 동적 비상 전화에 대 한 정보를 포함 하 여 비상 전화에 대해 알아봅니다.
ms.openlocfilehash: b97a14310014ea2e8271ee54f3bd6e777afa4d57
ms.sourcegitcommit: 021c86bf579e315f15815dcddf232a0c651cbf6b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2019
ms.locfileid: "39615838"
---
# <a name="manage-emergency-calling"></a><span data-ttu-id="adca2-103">긴급 통화 관리</span><span class="sxs-lookup"><span data-stu-id="adca2-103">Manage emergency calling</span></span>

<span data-ttu-id="adca2-104">이 문서에서는 긴급 전화 관리를 위해 알아야 할 개념에 대해 설명 하 고 긴급 주소, 동적 긴급 주소, 긴급 통화 라우팅에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-104">This article describes concepts you'll need to know to manage emergency calling--it includes information about emergency addresses, dynamic emergency addresses, and emergency call routing.</span></span> <span data-ttu-id="adca2-105">이 문서에서는 다음 용어를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-105">This article uses the following terminology:</span></span>

- <span data-ttu-id="adca2-106">**긴급 주소** -도심 주소--조직의 비즈니스 장소에 대 한 실제 또는 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-106">**Emergency Address** - A civic address--the physical or street address of a place of business for your organization.</span></span>

  <span data-ttu-id="adca2-107">예를 들어 주소 *12345 북쪽 주 주소, Redmond, WA 98052* 을 사용 하 여 긴급 통화를 적절 한 디스패치 기관으로 라우팅하고 긴급 전화 발신자를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-107">For example, the address  *12345 North Main Street, Redmond, WA 98052* is used to route emergency calls to the appropriate dispatch authorities and to assist in locating the emergency caller.</span></span>

- <span data-ttu-id="adca2-108">**장소** -일반적으로 바닥, 건물, 윙 또는 사무실 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-108">**Place** - Typically a floor, building, wing, or office number.</span></span> <span data-ttu-id="adca2-109">위치는 비상 주소와 연결 되어 건물 내에서 더 정확한 위치를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-109">Place is associated with an emergency address to give a more exact location within a building.</span></span> <span data-ttu-id="adca2-110">비상 주소와 연결 된 장소를 무제한으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-110">You can have an unlimited number of places associated with an emergency address.</span></span> <span data-ttu-id="adca2-111">예를 들어 조직에 여러 건물을 보유 하 고 있는 경우 각 건물에 각 건물에 대 한 배치 정보를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-111">For example, if your organization has multiple buildings, you might want to include place information for each building and for every floor within each building.</span></span>  

- <span data-ttu-id="adca2-112">**비상 위치** -위치는 선택 사항인 위치를 포함 하는 도심 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-112">**Emergency Location** - A location is a civic address--with an optional place.</span></span> <span data-ttu-id="adca2-113">회사에 둘 이상의 실제 위치가 있는 경우 두 개 이상의 긴급 위치가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-113">If your business has more than one physical location, it's likely that you'll need more than one emergency location.</span></span> 

  <span data-ttu-id="adca2-114">긴급 주소를 만들면이 주소에 대 한 고유한 위치 ID가 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-114">When you create an emergency address, a unique location ID is automatically created for this address.</span></span>  <span data-ttu-id="adca2-115">긴급 주소에 위치를 추가 하는 경우 (예: 건물 주소에 층을 추가 하는 경우), 긴급 주소와 장소 조합에 대 한 위치 ID가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-115">If you add a place to an emergency address--for example, if you add a floor to a building address--a location ID is created for the combination of the emergency address and place.</span></span>  <span data-ttu-id="adca2-116">이 예제에는 도심 주소에 대 한 두 개의 위치 Id가 있습니다. 하나는 연결 된 도심 주소와 관련 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-116">In this example, there will be two location IDs: one for the civic address; one for the joined civic address and associated place.</span></span>

  <span data-ttu-id="adca2-117">사용자 또는 사이트에 응급 위치를 할당 하는 경우 사용자 또는 사이트와 연결 되는 고유한 위치 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-117">When you assign an emergency location to a user or site, it's this unique location ID that's associated with the user or site.</span></span>

- <span data-ttu-id="adca2-118">**등록 된 주소** -각 통화 계획 사용자에 게 지정 된 긴급 주소입니다. 때로는 정적 긴급 주소 또는 레코드 주소 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-118">**Registered address** - An emergency address that is assigned to each Calling Plan user; it is sometimes referred to as a static emergency address or address of record.</span></span>  <span data-ttu-id="adca2-119">(직접 라우팅 사용자에 게 등록 된 주소가 적용 되지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="adca2-119">(Registered addresses do not apply to Direct Routing users.)</span></span>

<span data-ttu-id="adca2-120">팀 관리 센터를 사용 하 여 요금제 사용자에 대 한 긴급 주소를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-120">You create emergency addresses for Calling Plan users by using the Teams admin center.</span></span>  

>[!Note]
><span data-ttu-id="adca2-121">PSTN 연결을 위해 전화 시스템의 통화 요금제 또는 전화 시스템 다이렉트 라우팅을 사용 하는지에 따라 긴급 통화를 관리 하는 방법이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-121">There are some differences in how you manage emergency calling depending on whether you are using Phone System Calling Plans or Phone System Direct Routing for your PSTN connectivity.</span></span> <span data-ttu-id="adca2-122">이러한 고려 사항은이 문서 전체에서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-122">These considerations are described throughout this article.</span></span>

## <a name="emergency-address-validation"></a><span data-ttu-id="adca2-123">긴급 주소 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="adca2-123">Emergency address validation</span></span>

<span data-ttu-id="adca2-124">사용자 또는 네트워크 식별자에 긴급 주소를 할당 하려면 긴급 주소가 "확인 됨"으로 표시 되어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-124">To assign an emergency address to a user or to a network identifier, you must ensure that the emergency address is marked as “validated.”</span></span>  <span data-ttu-id="adca2-125">주소 유효성 검사는 주소가 유효한 지 확인 하 고, 할당 된 후에는 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-125">Address validation ensures that the address is legitimate, and that it cannot be modified after it is assigned.</span></span> 

<span data-ttu-id="adca2-126">팀 관리 센터에서 주소 맵 검색 기능을 사용 하 여 긴급 주소를 정의 하는 경우 주소가 자동으로 유효성이 검사 된 것으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-126">If you define an emergency address by using the address map search feature in the Teams admin center, the address is automatically marked as validated.</span></span> <span data-ttu-id="adca2-127">유효한 긴급 주소는 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-127">You cannot modify a validated emergency address.</span></span> <span data-ttu-id="adca2-128">따라서 주소의 형식 또는 표현이 변경 되 면 업데이트 된 형식으로 새 주소를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-128">Therefore, if the format or representation of the address changes, you must create a new address with the updated format.</span></span>


## <a name="emergency-address-geo-codes"></a><span data-ttu-id="adca2-129">긴급 주소 지역 코드</span><span class="sxs-lookup"><span data-stu-id="adca2-129">Emergency address geo codes</span></span>

<span data-ttu-id="adca2-130">각 긴급 주소에는 지역 코드 (위도 및 경도)가 연결 되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-130">Each emergency address can have a geo code (latitude and longitude) associated with it.</span></span> <span data-ttu-id="adca2-131">이러한 지역 코드는 일부 국가에서 동적 위치로 비상 통화를 라우팅하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-131">These geo codes are used in some countries to assist in routing emergency calls with dynamic locations.</span></span> 

<span data-ttu-id="adca2-132">팀 관리 센터에서 주소 맵 검색 기능을 사용 하 여 긴급 주소를 정의 하는 경우 지역 코드가 긴급 주소에 자동으로 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-132">If you define an emergency address by using the address map search feature in the Teams admin center, the geo code is automatically associated with an emergency address.</span></span> <span data-ttu-id="adca2-133">PowerShell을 사용 하 여 주소를 정의 하는 경우 지역 코드를 주소와 연결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-133">You can also associate geo codes with an address if you define the address by using PowerShell.</span></span> <span data-ttu-id="adca2-134">그러나 팀 관리 센터의 지도 검색 기능을 사용 하 여 전화 요금제에 대 한 긴급 주소를 만드는 것이 좋으며,이는 주소가 서식 지정 되 고 유효성을 검사 하 고 해당 지역 코드를가지고 있는지 확인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-134">However, Microsoft recommends that you create emergency addresses for Calling Plan by using the map search feature in Teams admin center, which will ensure that the addresses are formatted, validated, and have the appropriate geo codes.</span></span>  

>[!Important]
><span data-ttu-id="adca2-135">동적 비상 전화에 대 한 네트워크 식별자에 비상 위치를 할당 하려면 긴급 주소에는 적절 한 지역 코드가 포함 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-135">To assign an emergency location to a network identifier for dynamic emergency calling, the emergency address must contain an appropriate geo code.</span></span>


## <a name="considerations-for-calling-plans"></a><span data-ttu-id="adca2-136">통화 요금제에 대 한 고려 사항</span><span class="sxs-lookup"><span data-stu-id="adca2-136">Considerations for Calling Plans</span></span>

<span data-ttu-id="adca2-137">해당 지역에서 통화 요금제를 사용할 수 있는지 여부를 확인 하려면 [전화 요금제에 대 한 국가 및 지역 사용 가능성](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="adca2-137">To find out whether Calling Plans is available in your area, see [Country and region availability for Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span>


### <a name="emergency-call-enablement"></a><span data-ttu-id="adca2-138">비상 전화를 통한 통화</span><span class="sxs-lookup"><span data-stu-id="adca2-138">Emergency call enablement</span></span>

<span data-ttu-id="adca2-139">각 통화 계획 사용자는 비상 전화에 대해 자동으로 사용 하도록 설정 되며 지정 된 전화 번호와 연결 된 긴급 주소가 등록 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-139">Each Calling Plan user is automatically enabled for emergency calling and is required to have a registered emergency address associated with their assigned telephone number.</span></span> 

<span data-ttu-id="adca2-140">전화 번호에 연결 되어 있어야 하는 위치는 국가/지역에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-140">When the location must be associated to the telephone number depends on the country/region:</span></span>

- <span data-ttu-id="adca2-141">예를 들어 미국 및 캐나다의 경우 사용자에 게 번호를 할당 하면 비상 위치가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-141">In the United States and Canada, for example, an emergency location is required when a number is assigned to a user.</span></span>

- <span data-ttu-id="adca2-142">다른 국가의 경우 (예: 유럽, 중동, 아프리카 (EMEA)), Office 365에서 전화 번호를 받을 때 또는 다른 서비스 공급자나 통신 업체에서 전송 되는 경우 긴급 위치가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-142">For other countries--such as in Europe, the Middle East, and Africa (EMEA)--an emergency location is required when you get the phone number from Office 365 or when it's transferred from another service provider or carrier.</span></span>

### <a name="dynamic-emergency-calling"></a><span data-ttu-id="adca2-143">동적 비상 전화</span><span class="sxs-lookup"><span data-stu-id="adca2-143">Dynamic emergency calling</span></span>

<span data-ttu-id="adca2-144">Microsoft 호출 요금제에 대 한 동적 비상 통화는 팀 클라이언트의 현재 위치를 기반으로 비상 전화를 구성 하 고 라우팅할 수 있는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-144">Dynamic emergency calling for Microsoft Calling Plans provides the capability to configure and route emergency calls based on the current location of the Teams client.</span></span> <span data-ttu-id="adca2-145">적절 한 공개 안전 응답 시점 (PSAP)으로 자동 라우팅 하거나 보안 데스크 직원에 게 알리는 기능은 팀 사용자의 사용 국가에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-145">The ability to do automatic routing to the appropriate Public Safety Answering Point (PSAP) or to notify security desk personnel varies depending on the country of usage of the Teams user.</span></span>  

<span data-ttu-id="adca2-146">이번에는 미국에서 전화 요금제 사용자만 동적 위치를 활용 하 여 다음과 같이 비상 전화를 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-146">At this time, only Calling Plan users in the United States can leverage dynamic locations for routing emergency calls as follows:</span></span>

- <span data-ttu-id="adca2-147">미국 내 전화 플랜 사용자가 동적으로 미국 내의 긴급 주소를 획득 하는 경우, 해당 주소는 등록 된 주소 대신 긴급 라우팅에 사용 되며, 통화가 자동으로 PSAP에 연결 됩니다. 주소 영역을 처리 하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-147">If a Teams client for a United States Calling Plan user dynamically acquires an emergency address within the United States, that address is used for emergency routing instead of the registered address, and the call will be automatically routed to the PSAP in the serving area of the address.</span></span>

- <span data-ttu-id="adca2-148">미국 전화 플랜 사용자를 위한 팀 클라이언트가 미국 내에서 긴급 주소를 동적으로 획득 하지 않은 경우, 등록 된 긴급 주소를 사용 하 여 화면을 통해 통화를 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-148">If a Teams client for a United States Calling Plan user doesn’t dynamically acquire an emergency address within the United States, then the registered emergency address is used to help screen and route the call.</span></span> <span data-ttu-id="adca2-149">그러나 호출자를 적절 한 PSAP에 연결 하기 전에 업데이트 된 주소가 필요한 지 확인 하기 위해 통화가 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-149">However, the call will be screened to determine if an updated address is required before connecting the caller to the appropriate PSAP.</span></span>

<span data-ttu-id="adca2-150">미국에서는 네트워크 식별자에 할당 된 비상 위치에 속하는 도심 주소를 구성 하 고 관련 지역 코드를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-150">In the United States, you must configure the civic address that is part of the emergency locations that are assigned to network identifiers--and include the associated geo codes.</span></span> <span data-ttu-id="adca2-151">자세한 내용은 [동적 비상 전화 계획 및 구성을](configure-dynamic-emergency-calling.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="adca2-151">For more information, see [Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>


### <a name="emergency-call-routing"></a><span data-ttu-id="adca2-152">긴급 통화 라우팅</span><span class="sxs-lookup"><span data-stu-id="adca2-152">Emergency call routing</span></span>

<span data-ttu-id="adca2-153">팀에서 계획 사용자가 긴급 전화 번호로 전화를 거는 경우, 통화가 PSAP로 라우팅되는 방법은 다음에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-153">When a Teams Calling Plan user dials an emergency number, how the call is routed to the PSAP depends on the following:</span></span>

- <span data-ttu-id="adca2-154">팀 클라이언트에서 긴급 주소를 동적으로 결정 하는지 여부</span><span class="sxs-lookup"><span data-stu-id="adca2-154">Whether the emergency address is dynamically determined by the Teams client.</span></span>

- <span data-ttu-id="adca2-155">긴급 주소가 사용자의 전화 번호와 연결 된 등록 된 주소인 지 여부</span><span class="sxs-lookup"><span data-stu-id="adca2-155">Whether the emergency address is the registered address associated with the user's phone number.</span></span>

- <span data-ttu-id="adca2-156">해당 국가의 비상 전화 네트워크입니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-156">The emergency calling network of that country.</span></span>

  <span data-ttu-id="adca2-157">**미국에서:**</span><span class="sxs-lookup"><span data-stu-id="adca2-157">**In the United States:**</span></span>

  - <span data-ttu-id="adca2-158">팀 클라이언트가 테 넌 트 정의 동적인 긴급 위치에 있는 경우 해당 클라이언트의 비상 호출은 해당 지리적 위치를 처리 하는 PSAP에 자동으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-158">If a Teams client is located at a tenant-defined dynamic emergency location, emergency calls from that client are automatically routed to the PSAP serving that geographic location.</span></span> 

  - <span data-ttu-id="adca2-159">팀 클라이언트가 테 넌 트로 정의 된 동적 비상 위치에 없으면 해당 클라이언트의 비상 전화를 국가 콜 센터에서 확인 하 여 해당 지리적 위치를 처리 하는 PSAP로 호출을 전달 하기 전에 해당 전화를 통해 발신자의 위치를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-159">If a Teams client is not located at a tenant-defined dynamic emergency location, emergency calls from that client are screened by a national call center to determine the location of the caller before transferring the call to the PSAP serving that geographic location.</span></span>

  - <span data-ttu-id="adca2-160">응급 발신자가 비상 위치를 차단 센터로 업데이트할 수 없는 경우 통화는 등록 된 주소를 처리 하는 PSAP로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-160">If an emergency caller is unable to update their emergency location to the screening center, the call will be transferred to the PSAP serving the caller's registered address.</span></span>

  <span data-ttu-id="adca2-161">**캐나다, 아일랜드, 영국에**는 통화를 적절 한 디스패치 센터에 연결 하기 전에 사용자의 현재 위치를 확인 하기 위해 먼저 긴급 통화가 차단 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-161">**In Canada, Ireland, and the United Kingdom**, emergency calls are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center.</span></span> 

  <span data-ttu-id="adca2-162">**프랑스, 독일, 스페인에서**비상 전화는 호출자의 위치에 관계 없이 해당 번호와 연결 된 비상 주소로 서비스를 제공 하는 psap로 직접 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-162">**In France, Germany, and Spain**, emergency calls are routed directly to the PSAP serving the emergency address associated with the number regardless of the location of the caller.</span></span>

  <span data-ttu-id="adca2-163">**네덜란드에서**비상 전화는 호출자의 위치에 관계 없이 해당 번호의 지역 코드에 대 한 psap로 직접 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-163">**In the Netherlands**, emergency calls are routed directly to the PSAP for the local area code of the number regardless of the location of the caller.</span></span>

  <span data-ttu-id="adca2-164">**오스트레일리아에서는**통신 회사 파트너가 긴급 주소를 구성 하 고 라우트 합니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-164">**In Australia**, emergency addresses are configured and routed by the carrier partner.</span></span>

  <span data-ttu-id="adca2-165">**일본에서는**비상 통화가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-165">**In Japan**, emergency calling is not supported.</span></span>


<span data-ttu-id="adca2-166">자세한 내용은 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="adca2-166">For more information, see:</span></span>

- [<span data-ttu-id="adca2-167">통화 플랜</span><span class="sxs-lookup"><span data-stu-id="adca2-167">Calling Plans</span></span>](calling-plan-landing-page.md)

- [<span data-ttu-id="adca2-168">통화 요금제에 사용 되는 다른 종류의 전화 번호</span><span class="sxs-lookup"><span data-stu-id="adca2-168">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

- [<span data-ttu-id="adca2-169">긴급 통화 사용 약관</span><span class="sxs-lookup"><span data-stu-id="adca2-169">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-direct-routing"></a><span data-ttu-id="adca2-170">직접 라우팅에 대 한 고려 사항</span><span class="sxs-lookup"><span data-stu-id="adca2-170">Considerations for Direct Routing</span></span>

<span data-ttu-id="adca2-171">해당 지역에서 통화 요금제를 사용할 수 없거나 기존 통신 회사를 유지 하려는 경우 [다이렉트 라우팅을](direct-routing-landing-page.md)고려 하세요.</span><span class="sxs-lookup"><span data-stu-id="adca2-171">If Calling Plans are not available in your area or you want to keep your existing carrier, consider [Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="adca2-172">자세한 내용은 [직접 라우팅 구성](direct-routing-configure.md) 및 [긴급 통화 라우팅 정책 관리](manage-emergency-call-routing-policies.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="adca2-172">For more information, see [Configure Direct Routing](direct-routing-configure.md) and [Manage emergency call routing policies](manage-emergency-call-routing-policies.md).</span></span>

### <a name="emergency-call-enablement-and-configuration"></a><span data-ttu-id="adca2-173">응급 통화 설정 및 구성</span><span class="sxs-lookup"><span data-stu-id="adca2-173">Emergency call enablement and configuration</span></span>

<span data-ttu-id="adca2-174">TeamsEmergencyCallRoutingPolicy를 사용 하 여 긴급 전화 번호 및 연결 된 라우팅 대상을 정의 하 여 다이렉트 라우팅 사용자에 대 한 긴급 통화 정책을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-174">You must define emergency calling policies for Direct Routing users by using the TeamsEmergencyCallRoutingPolicy to define emergency numbers and their associated routing destination.</span></span> <span data-ttu-id="adca2-175">(등록 된 비상 위치는 다이렉트 라우팅 사용자에 게 지원 되지 않음에 유의 하세요.)</span><span class="sxs-lookup"><span data-stu-id="adca2-175">(Note that registered emergency locations are not supported for Direct Routing users.)</span></span>

<span data-ttu-id="adca2-176">팀 직접 라우팅 사용자 계정, 네트워크 사이트 또는 둘 다에 TeamsEmergencyCallRoutingPolicy를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-176">You can assign a TeamsEmergencyCallRoutingPolicy to a Teams Direct Routing user account, a network site, or both.</span></span> <span data-ttu-id="adca2-177">팀 클라이언트가 네트워크 연결을 시작 하거나 변경 하는 경우 팀은 다음과 같이 클라이언트가 있는 네트워크 사이트의 조회를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-177">When a Teams client starts or changes a network connection, Teams performs a lookup of the network site where the client is located as follows:</span></span>

- <span data-ttu-id="adca2-178">TeamsEmergencyCallRoutingPolicy가 사이트와 연결 되어 있는 경우 사이트 정책은 긴급 통화를 구성 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-178">If a TeamsEmergencyCallRoutingPolicy is associated with the site, then the site policy is used to configure emergency calling.</span></span>

- <span data-ttu-id="adca2-179">사이트와 연결 된 TeamsEmergencyCallRoutingPolicy 없거나 클라이언트가 정의 되지 않은 사이트에 연결 된 경우에는 사용자 계정과 연결 된 TeamsEmergencyCallRoutingPolicy를 사용 하 여 비상 통화를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-179">If there is no TeamsEmergencyCallRoutingPolicy associated with the site, or if the client is connected at an undefined site, then the TeamsEmergencyCallRoutingPolicy associated with the user account is used to configure emergency calling.</span></span> 

- <span data-ttu-id="adca2-180">팀 클라이언트가 TeamsEmergencyCallRoutingPolicy를 가져올 수 없는 경우 사용자는 비상 전화를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-180">If the Teams client is unable to obtain an TeamsEmergencyCallRoutingPolicy, then the user is not enabled for emergency calling.</span></span>

### <a name="dynamic-emergency-calling"></a><span data-ttu-id="adca2-181">동적 비상 전화</span><span class="sxs-lookup"><span data-stu-id="adca2-181">Dynamic emergency calling</span></span>

<span data-ttu-id="adca2-182">다이렉트 라우팅 사용자 용 팀 클라이언트는 동적 긴급 주소를 얻을 수 있으며,이는 호출자의 위치에 따라 동적으로 호출을 라우팅하는 데 사용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-182">Teams clients for Direct Routing users can acquire a dynamic emergency address, which can be used to dynamically route calls based upon the location of the caller.</span></span> <span data-ttu-id="adca2-183">자세한 내용은 [동적 긴급 통화 구성을](configure-dynamic-emergency-calling.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="adca2-183">For more information, see [Configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>

### <a name="emergency-call-routing"></a><span data-ttu-id="adca2-184">긴급 통화 라우팅</span><span class="sxs-lookup"><span data-stu-id="adca2-184">Emergency call routing</span></span>

<span data-ttu-id="adca2-185">TeamsEmergencyCallRoutingPolicy는 온라인 PSTN 사용을 참조 하며, 적절 한 PSTN 게이트웨이로 긴급 통화를 제대로 라우팅하도록 적절 한 직접 라우팅 구성이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-185">The TeamsEmergencyCallRoutingPolicy references an online PSTN Usage, which must have the appropriate Direct Routing configuration to properly route the emergency calls to the appropriate PSTN gateway(s).</span></span> <span data-ttu-id="adca2-186">특히 긴급 전화 접속 문자열에 대 한 OnlineVoiceRoute 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-186">In particular, you must ensure that there is an OnlineVoiceRoute for the emergency dial string.</span></span> <span data-ttu-id="adca2-187">자세한 내용은 [직접 라우팅 구성을](direct-routing-configure.md#configure-voice-routing)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="adca2-187">For more information, see [Configure Direct Routing](direct-routing-configure.md#configure-voice-routing).</span></span> 

<span data-ttu-id="adca2-188">(참고: 비즈니스용 Skype 서버에서 긴급 전화 번호 앞에 "+ 911"과 일치 하도록 음성 경로를 정의 해야 하는 "+"가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-188">(Note: In Skype for Business Server, the emergency number was prefixed with a “+” which required a voice route to be defined to match “+911” for instance.</span></span> <span data-ttu-id="adca2-189">팀 클라이언트는 긴급 전화 번호 앞에 "+"를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-189">Teams clients do not prepend the “+” with emergency numbers.)</span></span>

<span data-ttu-id="adca2-190">직접 라우팅 사용자를 위해 긴급 통화를 동적으로 라우팅하는 기능은 해당 국가 내의 비상 전화 네트워크에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-190">The ability to dynamically route emergency calls for Direct Routing users varies depending on the emergency calling network within a given country.</span></span> <span data-ttu-id="adca2-191">두 가지 해결 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-191">There are two solutions available:</span></span>

- <span data-ttu-id="adca2-192">긴급 라우팅 서비스 공급자 (미국 전용)</span><span class="sxs-lookup"><span data-stu-id="adca2-192">Emergency Routing Service Providers (US only)</span></span> 
- <span data-ttu-id="adca2-193">비상 위치 Id 번호 (ELIN) 게이트웨이 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="adca2-193">Emergency Location Identification Number (ELIN) gateway applications</span></span>

#### <a name="emergency-routing-service-providers"></a><span data-ttu-id="adca2-194">응급 라우팅 서비스 공급자</span><span class="sxs-lookup"><span data-stu-id="adca2-194">Emergency Routing Service Providers</span></span>

<span data-ttu-id="adca2-195">미국에는 발신자의 위치에 따라 긴급 통화를 자동으로 라우팅할 수 있는 여러 개의 인증 된 ERSPs (응급 라우팅 서비스 공급자)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-195">In the United States, there are numerous certified Emergency Routing Service Providers (ERSPs) that can automatically route emergency calls based upon the location of the caller.</span></span>

- <span data-ttu-id="adca2-196">긴급 라우팅 서비스 공급자가 직접 라우팅 배포에 통합 되어 있는 경우 동적으로 구입한 위치가 있는 비상 통화가 해당 위치를 처리 하는 PSAP (공개 안전 응답 시점)로 자동으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-196">If an Emergency Routing Service Provider is integrated into a Direct Routing deployment, emergency calls with a dynamically acquired location will be automatically routed to the Public Safety Answering Point (PSAP) serving that location.</span></span>

-  <span data-ttu-id="adca2-197">업데이트 된 위치에 따라 적절 한 디스패치 센터에 전화를 연결 하기 전에 동적으로 구입 위치 없이 긴급 통화를 먼저 차단 하 여 사용자의 현재 위치를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-197">Emergency calls without a dynamically acquired location are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center based upon the updated location.</span></span>

<span data-ttu-id="adca2-198">자세한 내용은 [직접 라우팅을 위해 인증 된 세션 경계 컨트롤러](direct-routing-border-controllers.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="adca2-198">For more information, see [Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>


#### <a name="emergency-location-identification-number-elin-applications"></a><span data-ttu-id="adca2-199">비상 위치 Id 번호 (ELIN) 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="adca2-199">Emergency Location Identification Number (ELIN) applications</span></span>

<span data-ttu-id="adca2-200">SBCs (세션 경계 컨트롤러)는 비상 위치 Id 번호 (ELIN) 응용 프로그램을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-200">Session Border Controllers (SBCs) can include Emergency Location Identification Number (ELIN) applications.</span></span> <span data-ttu-id="adca2-201">응용 프로그램의 SBC ELIN을 직접 라우팅 배포에 통합 하는 경우에는 응용 프로그램의 ELIN 긴급 주소 및 연결 된 전화 번호를 구성한 다음 해당 PSTN의 비상 전화 데이터베이스에 레코드의 ELIN 업로드 해야 합니다. .</span><span class="sxs-lookup"><span data-stu-id="adca2-201">If an SBC ELIN application is integrated into a Direct Routing deployment, you must configure the emergency addresses and associated telephone numbers in the ELIN application, and then upload the ELIN records to the emergency calling database in the respective PSTN.</span></span>  <span data-ttu-id="adca2-202">식별자가 ELIN 인 팀의 비상 위치는 응용 프로그램의 ELIN 내에서와 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-202">Teams emergency locations with an ELIN identifier must match those within the ELIN application.</span></span>

<span data-ttu-id="adca2-203">동적으로 취득 하는 위치가 포함 된 비상 통화가 해당 SBC, 즉 응용 프로그램의 ELIN 같이 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-203">When an emergency call with a dynamically acquired location is routed to the appropriate SBC, the ELIN application:</span></span>

- <span data-ttu-id="adca2-204">호출자의 긴급 위치를 구문 분석 합니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-204">Parses the emergency location of the caller.</span></span>
- <span data-ttu-id="adca2-205">위치를 레코드의 ELIN와 일치 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-205">Matches the location to an ELIN record.</span></span>
- <span data-ttu-id="adca2-206">비상 연락망의 번호를 전화 번호의 ELIN으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-206">Substitutes the emergency caller's number with the ELIN phone number.</span></span>
- <span data-ttu-id="adca2-207">해당 위치를 처리 하는 PSAP에 대 한 통화를 라우팅하고, 발송자는 업로드 된 ELIN record에서 위치를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-207">Routes the call to the PSAP serving that location, and then the dispatchers obtain the location from the uploaded ELIN record.</span></span>

<span data-ttu-id="adca2-208">비상 번호로 다시 전화를 받으면, 응용 프로그램의 ELIN는 원래 비상 전화 번호로 대체 하는 역 번호를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-208">Upon a call back to the emergency number, the ELIN application will do the reverse called number substitution to that of the original emergency caller.</span></span> 

<span data-ttu-id="adca2-209">자세한 내용은 [직접 라우팅을 위해 인증 된 세션 경계 컨트롤러](direct-routing-border-controllers.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="adca2-209">For more information, see [Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>


## <a name="security-desk-notification"></a><span data-ttu-id="adca2-210">보안 데스크 알림</span><span class="sxs-lookup"><span data-stu-id="adca2-210">Security desk notification</span></span>

<span data-ttu-id="adca2-211">Microsoft 통화 요금제와 전화 시스템 직접 라우팅 모두에서 보안 데스크 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-211">Security desk notification is available with both Microsoft Calling Plans and Phone System Direct Routing.</span></span>

<span data-ttu-id="adca2-212">TeamsEmergencyCallingPolicy를 사용 하 여 긴급 통화 중에 알림을 받을 사람과 알림을 받는 방법 (채팅 전용, conferenced 인 및 음소거)을 구성 하 고, 음소거를 해제 하 고, 음소거를 해제 하는 등의 기능을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-212">You use the TeamsEmergencyCallingPolicy to configure who should be notified during an emergency call and how they are notified: chat only, conferenced in and muted, or conferenced in and muted but with the ability to unmute.</span></span>  <span data-ttu-id="adca2-213">또한 사용자 또는 그룹의 외부 PSTN 번호를 지정 하 여 비상 전화를 걸고 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-213">You can also specify an external PSTN number of a user or group to call and join the emergency call.</span></span> 

<span data-ttu-id="adca2-214">TeamsEmergencyCallingPolicy는 팀 사용자 계정에 게 부여 하거나, 네트워크 사이트에 할당 하거나, 둘 다에 게 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-214">A TeamsEmergencyCallingPolicy can be granted to a Teams user account, assigned to a network site, or both.</span></span>  <span data-ttu-id="adca2-215">팀 클라이언트가 네트워크 연결을 시작 하거나 변경 하는 경우 팀은 클라이언트가 있는 네트워크 사이트의 조회를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-215">When a Teams client starts or changes a network connection, Teams performs a lookup of the network site where the client is located:</span></span>

- <span data-ttu-id="adca2-216">TeamsEmergencyCallingPolicy 네트워크 사이트와 연결 된 경우 사이트 정책은 보안 데스크 알림을 구성 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-216">If a TeamsEmergencyCallingPolicy is associated with a network site, then the site policy is used to configure security desk notification.</span></span>

- <span data-ttu-id="adca2-217">사이트와 연결 된 TeamsEmergencyCallingPolicy 없거나 클라이언트가 정의 되지 않은 사이트에 연결 되어 있는 경우 사용자 계정과 연결 된 TeamsEmergencyCallingPolicy는 보안 데스크 알림을 구성 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-217">If there is no TeamsEmergencyCallingPolicy associated with the site, or if the client is connected at an undefined site, then the TeamsEmergencyCallingPolicy associated with the user account is used to configure security desk notification.</span></span>  

- <span data-ttu-id="adca2-218">팀 클라이언트가 TeamsEmergencyCallingPolicy를 가져올 수 없는 경우 사용자는 보안 데스크 알림을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-218">If the Teams client is unable to obtain an TeamsEmergencyCallingPolicy, then the user is not enabled for security desk notification.</span></span>

<span data-ttu-id="adca2-219">비상 전화 시, 보안 데스크는 통화에 conferenced, 보안 데스크 사용자의 경험은 TeamsEmergencyCallingPolicy에 따라 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-219">During an emergency call, a security desk is conferenced into the call and the experience of the security desk user is controlled based upon the TeamsEmergencyCallingPolicy.</span></span> <span data-ttu-id="adca2-220">그룹 채팅은 각 보안 데스크 구성원에 게 시작 되며, 긴급 전화 발신자의 위치는 중요 한 메시지 알림을 통해 공유 됩니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-220">A group chat is started with each security desk member, and the location of the emergency caller is shared via an important message notification.</span></span>  <span data-ttu-id="adca2-221">회의 옵션이 정책의 일부로 구성 되어 있으면 각 보안 데스크 사용자가 회의의 일부로 추가로 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="adca2-221">If a conference option is configured as part of the policy, each security desk user is additionally called as part of the conference.</span></span>

    
## <a name="related-topics"></a><span data-ttu-id="adca2-222">관련 항목</span><span class="sxs-lookup"><span data-stu-id="adca2-222">Related topics</span></span>

- [<span data-ttu-id="adca2-223">긴급 전화 정책 관리</span><span class="sxs-lookup"><span data-stu-id="adca2-223">Manage emergency calling policies</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="adca2-224">긴급 통화 라우팅 정책 관리</span><span class="sxs-lookup"><span data-stu-id="adca2-224">Manage emergency call routing policies </span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="adca2-225">조직의 응급 위치 추가, 변경 또는 제거</span><span class="sxs-lookup"><span data-stu-id="adca2-225">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="adca2-226">사용자의 긴급 위치 지정 또는 변경</span><span class="sxs-lookup"><span data-stu-id="adca2-226">Assign or change an emergency location for your user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="adca2-227">동적인 긴급 전화 계획 및 구성</span><span class="sxs-lookup"><span data-stu-id="adca2-227">Plan and configure dynamic emergency calling</span></span>](configure-dynamic-emergency-calling.md)