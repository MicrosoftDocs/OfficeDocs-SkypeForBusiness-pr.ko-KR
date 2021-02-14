---
title: 긴급 통화 계획 및 관리
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
- m365initiative-voice
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
description: 긴급 주소, 긴급 통화 라우팅 및 동적 긴급 통화에 대한 정보를 포함하여 긴급 통화에 대해 자세히 배워야 합니다.
ms.openlocfilehash: 4f2ef86d05537a147a459fd6bc121f0680b534bd
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031604"
---
# <a name="manage-emergency-calling"></a><span data-ttu-id="1cefb-103">긴급 통화 관리</span><span class="sxs-lookup"><span data-stu-id="1cefb-103">Manage emergency calling</span></span>

<span data-ttu-id="1cefb-104">이 문서에서는 긴급 통화를 관리하기 위해 알아야 할 개념에 대해 설명하며 긴급 주소, 동적 긴급 주소 및 긴급 통화 라우팅에 대한 &mdash; 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-104">This article describes concepts you'll need to know to manage emergency calling&mdash;it includes information about emergency addresses, dynamic emergency addresses, and emergency call routing.</span></span> <span data-ttu-id="1cefb-105">이 문서에서는 다음 용어를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-105">This article uses the following terminology:</span></span>

- <span data-ttu-id="1cefb-106">**긴급 주소** - 조직에 대한 사업장의 실제 주소 또는 주소입니다. &mdash;</span><span class="sxs-lookup"><span data-stu-id="1cefb-106">**Emergency address** - A civic address&mdash;the physical or street address of a place of business for your organization.</span></span>

  <span data-ttu-id="1cefb-107">예를 들어 주소  *12345 North Main Street, Redmond, WA 98052는* 긴급 통화를 적절한 디스패치 기관에 라우팅하고 긴급 발신자 찾기를 지원하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-107">For example, the address  *12345 North Main Street, Redmond, WA 98052* is used to route emergency calls to the appropriate dispatch authorities and to assist in locating the emergency caller.</span></span>

- <span data-ttu-id="1cefb-108">**장소** - 일반적으로 층, 건물, 날개 또는 사무실 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-108">**Place** - Typically a floor, building, wing, or office number.</span></span> <span data-ttu-id="1cefb-109">장소는 건물 내에서 더 정확한 위치를 제공하기 위해 긴급 주소와 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-109">Place is associated with an emergency address to give a more exact location within a building.</span></span> <span data-ttu-id="1cefb-110">긴급 주소와 연결된 장소는 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-110">You can have an unlimited number of places associated with an emergency address.</span></span> <span data-ttu-id="1cefb-111">예를 들어 조직에 여러 건물이 있는 경우 각 건물 및 각 건물 내의 모든 층에 대한 장소 정보를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-111">For example, if your organization has multiple buildings, you might want to include place information for each building and for every floor within each building.</span></span>  

- <span data-ttu-id="1cefb-112">**긴급 위치** - 위치는 선택적 장소가 있는 &mdash; 지역 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-112">**Emergency location** - A location is a civic address&mdash;with an optional place.</span></span> <span data-ttu-id="1cefb-113">비즈니스에 두 개 이상의 물리적 위치가 있는 경우 두 개 이상의 긴급 위치가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-113">If your business has more than one physical location, it's likely that you'll need more than one emergency location.</span></span> 

  <span data-ttu-id="1cefb-114">긴급 주소를 만들면 이 주소에 대해 고유한 위치 ID가 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-114">When you create an emergency address, a unique location ID is automatically created for this address.</span></span>  <span data-ttu-id="1cefb-115">예를 들어 긴급 주소에 장소를 추가하는 경우 건물 주소에 층을 추가하면 긴급 주소와 장소 조합에 대한 위치 &mdash; &mdash; ID가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-115">If you add a place to an emergency address&mdash;for example, if you add a floor to a building address&mdash;a location ID is created for the combination of the emergency address and place.</span></span>  <span data-ttu-id="1cefb-116">이 예제에는 지역 주소에 대한 두 개의 위치 IP가 있습니다. 하나는 조인된 지민 주소 및 연결된 장소에 대한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-116">In this example, there will be two location IDs: one for the civic address; one for the joined civic address and associated place.</span></span>

  <span data-ttu-id="1cefb-117">사용자 또는 사이트에 긴급 위치를 할당하는 경우 사용자 또는 사이트와 연결된 이 고유한 위치 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-117">When you assign an emergency location to a user or site, it's this unique location ID that's associated with the user or site.</span></span>

- <span data-ttu-id="1cefb-118">**등록된 주소** - 각 통화 계획 사용자에게 할당된 긴급 주소 이를 정적 긴급 주소 또는 레코드의 주소라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-118">**Registered address** - An emergency address that is assigned to each Calling Plan user; it is sometimes referred to as a static emergency address or address of record.</span></span>  <span data-ttu-id="1cefb-119">(직접 라우팅 사용자에게는 등록된 주소가 적용되지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="1cefb-119">(Registered addresses do not apply to Direct Routing users.)</span></span>

<span data-ttu-id="1cefb-120">Teams 관리 센터를 사용하여 요금제 사용자에 대한 긴급 주소를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-120">You create emergency addresses for Calling Plan users by using the Teams admin center.</span></span>  

>[!Note]
><span data-ttu-id="1cefb-121">PSTN 연결에 전화 시스템 통화 요금제 또는 전화 시스템 직접 라우팅을 사용하는지 여부에 따라 긴급 통화를 관리하는 방법에는 몇 가지 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-121">There are some differences in how you manage emergency calling depending on whether you are using Phone System Calling Plans or Phone System Direct Routing for your PSTN connectivity.</span></span> <span data-ttu-id="1cefb-122">이러한 고려 사항은 이 문서 전체에서 설명됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-122">These considerations are described throughout this article.</span></span>

## <a name="emergency-address-validation"></a><span data-ttu-id="1cefb-123">긴급 주소 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="1cefb-123">Emergency address validation</span></span>

<span data-ttu-id="1cefb-124">사용자 또는 네트워크 식별자에 긴급 주소를 할당하려면 긴급 주소가 "유효성 검사"로 표시되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-124">To assign an emergency address to a user or to a network identifier, you must ensure that the emergency address is marked as "validated."</span></span>  <span data-ttu-id="1cefb-125">주소 유효성 검사는 주소가 합법적으로 지정되어 있으며 주소가 할당된 후 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-125">Address validation ensures that the address is legitimate, and that it cannot be modified after it is assigned.</span></span> 

<span data-ttu-id="1cefb-126">Teams 관리 센터에서 주소 맵 검색 기능을 사용하여 긴급 주소를 정의하면 주소가 자동으로 유효성 검사로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-126">If you define an emergency address by using the address map search feature in the Teams admin center, the address is automatically marked as validated.</span></span> <span data-ttu-id="1cefb-127">확인된 긴급 주소는 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-127">You cannot modify a validated emergency address.</span></span> <span data-ttu-id="1cefb-128">따라서 주소의 형식 또는 표현이 변경되는 경우 업데이트된 형식으로 새 주소를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-128">Therefore, if the format or representation of the address changes, you must create a new address with the updated format.</span></span>


## <a name="emergency-address-geo-codes"></a><span data-ttu-id="1cefb-129">긴급 주소 지역 코드</span><span class="sxs-lookup"><span data-stu-id="1cefb-129">Emergency address geo codes</span></span>

<span data-ttu-id="1cefb-130">각 긴급 주소에는 지역 코드(위도 및 위도)가 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-130">Each emergency address can have a geo code (latitude and longitude) associated with it.</span></span> <span data-ttu-id="1cefb-131">이러한 지역 코드는 일부 국가에서 동적 위치로 긴급 통화를 라우팅하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-131">These geo codes are used in some countries to assist in routing emergency calls with dynamic locations.</span></span> 

<span data-ttu-id="1cefb-132">Teams 관리 센터에서 주소 맵 검색 기능을 사용하여 긴급 주소를 정의하면 지역 코드가 긴급 주소와 자동으로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-132">If you define an emergency address by using the address map search feature in the Teams admin center, the geo code is automatically associated with an emergency address.</span></span> <span data-ttu-id="1cefb-133">PowerShell을 사용하여 주소를 정의하는 경우 지역 코드를 주소와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-133">You can also associate geo codes with an address if you define the address by using PowerShell.</span></span> <span data-ttu-id="1cefb-134">그러나 Teams 관리 센터에서 지도 검색 기능을 사용하여 통화 계획에 대한 긴급 주소를 만드는 것이 좋습니다. 그러면 주소의 서식이 지정되어 유효성이 검사되어 적절한 지역 코드가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-134">However, Microsoft recommends that you create emergency addresses for Calling Plan by using the map search feature in Teams admin center, which will ensure that the addresses are formatted, validated, and have the appropriate geo codes.</span></span>  

>[!Important]
><span data-ttu-id="1cefb-135">동적 긴급 통화를 위해 네트워크 식별자에 긴급 위치를 할당하려면 긴급 주소에 적절한 지역 코드가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-135">To assign an emergency location to a network identifier for dynamic emergency calling, the emergency address must contain an appropriate geo code.</span></span>


## <a name="considerations-for-calling-plans"></a><span data-ttu-id="1cefb-136">통화 요금제에 대한 고려 사항</span><span class="sxs-lookup"><span data-stu-id="1cefb-136">Considerations for Calling Plans</span></span>

<span data-ttu-id="1cefb-137">해당 지역에서 통화 플랜을 사용할 수 있는지 여부를 확인한 다음 통화 요금제에 대한 국가 및 지역 [가용성을 참조합니다.](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="1cefb-137">To find out whether Calling Plans is available in your area, see [Country and region availability for Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span>


### <a name="emergency-call-enablement"></a><span data-ttu-id="1cefb-138">긴급 통화 사용</span><span class="sxs-lookup"><span data-stu-id="1cefb-138">Emergency call enablement</span></span>

<span data-ttu-id="1cefb-139">각 통화 요금제 사용자는 긴급 통화를 자동으로 사용하도록 설정되며, 지정된 전화 번호와 연결된 등록된 긴급 주소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-139">Each Calling Plan user is automatically enabled for emergency calling and is required to have a registered emergency address associated with their assigned telephone number.</span></span> 

<span data-ttu-id="1cefb-140">위치가 전화 번호에 연결되어야 하는 경우 국가/지역에 따라 달라 습니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-140">When the location must be associated to the telephone number depends on the country/region:</span></span>

- <span data-ttu-id="1cefb-141">예를 들어 미국 및 캐나다에서는 사용자에게 번호가 할당될 때 긴급 위치가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-141">In the United States and Canada, for example, an emergency location is required when a number is assigned to a user.</span></span>

- <span data-ttu-id="1cefb-142">유럽, 중동 및 아프리카(EMEA)와 같은 다른 국가의 경우 Microsoft 365 또는 Office 365에서 전화 번호를 옮기거나 다른 서비스 공급자 또는 통신 사업자로부터 이전할 때 긴급 위치가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-142">For other countries--such as in Europe, the Middle East, and Africa (EMEA)--an emergency location is required when you get the phone number from Microsoft 365 or Office 365, or when it's transferred from another service provider or carrier.</span></span>

### <a name="dynamic-emergency-calling"></a><span data-ttu-id="1cefb-143">동적 긴급 통화</span><span class="sxs-lookup"><span data-stu-id="1cefb-143">Dynamic emergency calling</span></span>

<span data-ttu-id="1cefb-144">Microsoft 통화 플랜에 대한 동적 긴급 통화는 Teams 클라이언트의 현재 위치를 기반으로 긴급 통화를 구성하고 라우팅하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-144">Dynamic emergency calling for Microsoft Calling Plans provides the capability to configure and route emergency calls based on the current location of the Teams client.</span></span> <span data-ttu-id="1cefb-145">적절한 PSAP(Public Safety Answering Point)로 자동 라우팅을 수행하거나 보안 데스크 담당자에게 알리는 능력은 Teams 사용자의 사용 국가에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-145">The ability to do automatic routing to the appropriate Public Safety Answering Point (PSAP) or to notify security desk personnel varies depending on the country of usage of the Teams user.</span></span>  

<span data-ttu-id="1cefb-146">통화 요금제 사용자의 경우 긴급 통화를 라우팅하기 위한 동적 위치는 다음과 같이 미국에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-146">For Calling Plan users, dynamic location for routing emergency calls is only supported in the United States as follows.</span></span> <span data-ttu-id="1cefb-147">(동적 긴급 통화 및 직접 라우팅에 대한 자세한 내용은 직접 라우팅에 대한 [고려 사항을 참조하세요.](#considerations-for-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="1cefb-147">(For information about dynamic emergency calling and Direct Routing, see [Considerations for Direct Routing](#considerations-for-direct-routing).</span></span>

- <span data-ttu-id="1cefb-148">미국 통화 요금제 사용자의 Teams 클라이언트가 미국 내 긴급 주소를 동적으로 획득하는 경우 해당 주소는 등록된 주소 대신 긴급 라우팅에 사용되며, 해당 주소의 서비스 영역에 있는 PSAP로 통화가 자동으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-148">If a Teams client for a United States Calling Plan user dynamically acquires an emergency address within the United States, that address is used for emergency routing instead of the registered address, and the call will be automatically routed to the PSAP in the serving area of the address.</span></span>

- <span data-ttu-id="1cefb-149">미국 통화 요금제 사용자의 Teams 클라이언트가 미국 내 긴급 주소를 동적으로 획득하지 않는 경우 등록된 긴급 주소가 통화를 화면으로 표시하고 라우팅하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-149">If a Teams client for a United States Calling Plan user doesn't dynamically acquire an emergency address within the United States, then the registered emergency address is used to help screen and route the call.</span></span> <span data-ttu-id="1cefb-150">그러나 호출자는 적절한 PSAP에 연결하기 전에 업데이트된 주소가 필요한지 여부를 결정하기 위해 호출이 화면으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-150">However, the call will be screened to determine if an updated address is required before connecting the caller to the appropriate PSAP.</span></span>

<span data-ttu-id="1cefb-151">미국에서는 네트워크 식별자에 할당된 긴급 위치의 일부인 지역 주소를 구성하고 관련 지역 코드를 &mdash; 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-151">In the United States, you must configure the civic address that is part of the emergency locations that are assigned to network identifiers&mdash;and include the associated geo codes.</span></span> <span data-ttu-id="1cefb-152">자세한 내용은 동적 긴급 통화 계획 및 [구성을 참조하세요.](configure-dynamic-emergency-calling.md)</span><span class="sxs-lookup"><span data-stu-id="1cefb-152">For more information, see [Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>


### <a name="emergency-call-routing"></a><span data-ttu-id="1cefb-153">긴급 통화 라우팅</span><span class="sxs-lookup"><span data-stu-id="1cefb-153">Emergency call routing</span></span>

<span data-ttu-id="1cefb-154">Teams 통화 요금제 사용자가 긴급 번호로 전화를 걸면 통화가 PSAP로 라우팅되는 방식은 다음에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-154">When a Teams Calling Plan user dials an emergency number, how the call is routed to the PSAP depends on the following:</span></span>

- <span data-ttu-id="1cefb-155">긴급 주소가 Teams 클라이언트에 의해 동적으로 결정될지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-155">Whether the emergency address is dynamically determined by the Teams client.</span></span>

- <span data-ttu-id="1cefb-156">긴급 주소가 사용자의 전화 번호와 연결된 등록된 주소인지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-156">Whether the emergency address is the registered address associated with the user's phone number.</span></span>

- <span data-ttu-id="1cefb-157">이 국가의 긴급 통화 네트워크입니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-157">The emergency calling network of that country.</span></span>

  <span data-ttu-id="1cefb-158">**미국:**</span><span class="sxs-lookup"><span data-stu-id="1cefb-158">**In the United States:**</span></span>

  - <span data-ttu-id="1cefb-159">Teams 클라이언트가 테넌트 정의 동적 긴급 위치에 있는 경우 해당 클라이언트의 긴급 전화가 해당 지리적 위치에 있는 PSAP로 자동으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-159">If a Teams client is located at a tenant-defined dynamic emergency location, emergency calls from that client are automatically routed to the PSAP serving that geographic location.</span></span> 

  - <span data-ttu-id="1cefb-160">Teams 클라이언트가 테넌트에서 정의한 동적 긴급 위치에 있지 않은 경우 해당 클라이언트의 응급 전화는 해당 지리적 위치에 있는 PSAP로 통화를 전송하기 전에 발신자 위치를 결정하기 위해 해당 클라이언트의 긴급 통화를 국가 콜 센터에서 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-160">If a Teams client is not located at a tenant-defined dynamic emergency location, emergency calls from that client are screened by a national call center to determine the location of the caller before transferring the call to the PSAP serving that geographic location.</span></span>

  - <span data-ttu-id="1cefb-161">긴급 발신자는 긴급 위치를 화면 센터로 업데이트할 수 없는 경우 발신자 등록 주소를 제공하는 PSAP로 통화가 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-161">If an emergency caller is unable to update their emergency location to the screening center, the call will be transferred to the PSAP serving the caller's registered address.</span></span>

  <span data-ttu-id="1cefb-162">**캐나다, 아일랜드 및** 영국에서는 통화를 적절한 디스패치 센터에 연결하기 전에 사용자의 현재 위치를 결정하기 위해 긴급 통화가 먼저 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-162">**In Canada, Ireland, and the United Kingdom**, emergency calls are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center.</span></span> 

  <span data-ttu-id="1cefb-163">**프랑스, 독일 및** 스페인에서 긴급 통화는 발신자 위치에 관계없이 번호와 연결된 긴급 주소를 제공하는 PSAP로 직접 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-163">**In France, Germany, and Spain**, emergency calls are routed directly to the PSAP serving the emergency address associated with the number regardless of the location of the caller.</span></span>

  <span data-ttu-id="1cefb-164">**네덜란드에서** 긴급 통화는 발신자 위치에 관계없이 번호의 로컬 지역 번호에 대한 PSAP로 직접 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-164">**In the Netherlands**, emergency calls are routed directly to the PSAP for the local area code of the number regardless of the location of the caller.</span></span>

  <span data-ttu-id="1cefb-165">**오스트레일리아에서는** 긴급 주소가 통신사 파트너에 의해 구성 및 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-165">**In Australia**, emergency addresses are configured and routed by the carrier partner.</span></span>

  <span data-ttu-id="1cefb-166">**일본에서는** 긴급 통화가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-166">**In Japan**, emergency calling is not supported.</span></span>


<span data-ttu-id="1cefb-167">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1cefb-167">For more information, see:</span></span>

- [<span data-ttu-id="1cefb-168">통화 플랜</span><span class="sxs-lookup"><span data-stu-id="1cefb-168">Calling Plans</span></span>](calling-plan-landing-page.md)

- [<span data-ttu-id="1cefb-169">통화 요금제에 사용되는 다양한 종류의 전화 번호</span><span class="sxs-lookup"><span data-stu-id="1cefb-169">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

- [<span data-ttu-id="1cefb-170">긴급 통화 사용 약관</span><span class="sxs-lookup"><span data-stu-id="1cefb-170">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-direct-routing"></a><span data-ttu-id="1cefb-171">직접 라우팅에 대한 고려 사항</span><span class="sxs-lookup"><span data-stu-id="1cefb-171">Considerations for Direct Routing</span></span>

<span data-ttu-id="1cefb-172">통화 요금제가 해당 지역에서 사용할 수 없는 경우 또는 기존 통신업체를 유지하려는 경우 [직접 라우팅을 고려합니다.](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="1cefb-172">If Calling Plans are not available in your area or you want to keep your existing carrier, consider [Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="1cefb-173">자세한 내용은 직접 [](direct-routing-configure.md) 라우팅 구성 및 긴급 통화 라우팅 [정책 관리를 참조하세요.](manage-emergency-call-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="1cefb-173">For more information, see [Configure Direct Routing](direct-routing-configure.md) and [Manage emergency call routing policies](manage-emergency-call-routing-policies.md).</span></span>

### <a name="emergency-call-enablement-and-configuration"></a><span data-ttu-id="1cefb-174">긴급 통화 사용 및 구성</span><span class="sxs-lookup"><span data-stu-id="1cefb-174">Emergency call enablement and configuration</span></span>

<span data-ttu-id="1cefb-175">Teams 긴급 통화 라우팅 정책(TeamsEmergencyCallRoutingPolicy)을 사용하여 긴급 번호 및 관련 라우팅 대상을 정의하여 직접 라우팅 사용자에 대한 긴급 통화 정책을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-175">You must define emergency calling policies for Direct Routing users by using a Teams emergency call routing policy (TeamsEmergencyCallRoutingPolicy) to define emergency numbers and their associated routing destination.</span></span> <span data-ttu-id="1cefb-176">(직접 라우팅 사용자에 대해 등록된 긴급 위치는 지원되지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="1cefb-176">(Note that registered emergency locations are not supported for Direct Routing users.)</span></span>

<span data-ttu-id="1cefb-177">Teams 직접 라우팅 사용자 계정, 네트워크 사이트 또는 둘 다에 긴급 통화 라우팅 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-177">You can assign an emergency call routing policy  to a Teams Direct Routing user account, a network site, or both.</span></span> <span data-ttu-id="1cefb-178">Teams 클라이언트가 네트워크 연결을 시작하거나 변경하면 Teams는 클라이언트가 있는 네트워크 사이트의 정보를 다음과 같이 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-178">When a Teams client starts or changes a network connection, Teams performs a lookup of the network site where the client is located as follows:</span></span>

- <span data-ttu-id="1cefb-179">긴급 통화 라우팅 정책이 사이트와 연결된 경우 사이트 정책은 긴급 통화를 구성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-179">If an emergency call routing policy is associated with the site, then the site policy is used to configure emergency calling.</span></span>

- <span data-ttu-id="1cefb-180">사이트와 연결된 긴급 통화 라우팅 정책이 없는 경우 또는 클라이언트가 정의되지 않은 사이트에서 연결되어 있는 경우 사용자 계정과 연결된 긴급 통화 라우팅 정책을 사용하여 긴급 통화를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-180">If there is no emergency call routing policy associated with the site, or if the client is connected at an undefined site, then the emergency call routing policy associated with the user account is used to configure emergency calling.</span></span> 

- <span data-ttu-id="1cefb-181">Teams 클라이언트가 긴급 통화 라우팅 정책을 받을 수 없는 경우 사용자는 긴급 통화를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-181">If the Teams client is unable to obtain an emergency call routing policy, then the user is not enabled for emergency calling.</span></span>

### <a name="dynamic-emergency-calling"></a><span data-ttu-id="1cefb-182">동적 긴급 통화</span><span class="sxs-lookup"><span data-stu-id="1cefb-182">Dynamic emergency calling</span></span>

<span data-ttu-id="1cefb-183">직접 라우팅 사용자를 위한 Teams 클라이언트는 발신자 위치에 따라 호출을 동적으로 라우팅하는 데 사용할 수 있는 동적 긴급 주소를 획득할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-183">Teams clients for Direct Routing users can acquire a dynamic emergency address, which can be used to dynamically route calls based upon the location of the caller.</span></span> <span data-ttu-id="1cefb-184">자세한 내용은 동적 긴급 통화 [구성을 참조하세요.](configure-dynamic-emergency-calling.md)</span><span class="sxs-lookup"><span data-stu-id="1cefb-184">For more information, see [Configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>

### <a name="emergency-call-routing"></a><span data-ttu-id="1cefb-185">긴급 통화 라우팅</span><span class="sxs-lookup"><span data-stu-id="1cefb-185">Emergency call routing</span></span>

<span data-ttu-id="1cefb-186">긴급 통화 라우팅 정책은 온라인 PSTN 사용량을 참조합니다. 이 경우 긴급 통화를 적절한 PSTN 게이트웨이로 올바르게 라우팅하기 위한 적절한 직접 라우팅 구성이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-186">The emergency call routing policy references an online PSTN usage, which must have the appropriate Direct Routing configuration to properly route the emergency calls to the appropriate PSTN gateway(s).</span></span> <span data-ttu-id="1cefb-187">특히 응급 전화 문자열에 대한 OnlineVoiceRoute가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-187">In particular, you must ensure that there is an OnlineVoiceRoute for the emergency dial string.</span></span> <span data-ttu-id="1cefb-188">자세한 내용은 직접 라우팅 [구성을 참조하세요.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="1cefb-188">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span> 

<span data-ttu-id="1cefb-189">(참고: Teams 클라이언트는 비즈니스용 Skype 클라이언트와 비슷한 방식으로 긴급 번호 앞에 "+" 기호를 추가합니다. 즉, +911).</span><span class="sxs-lookup"><span data-stu-id="1cefb-189">(Note: Teams clients prepend the "+" sign in front of emergency numbers in a similar manner that Skype for Business client does; that is, +911.</span></span> <span data-ttu-id="1cefb-190">이 동작은 Teams 비상 전화가 번호 앞에 더 이상 "+"를 보내지 못하도록 다음 달에 수정될 것입니다. 즉, 911입니다.)</span><span class="sxs-lookup"><span data-stu-id="1cefb-190">This behavior will be modified in the coming months so that Teams emergency calls will no longer be sending a "+" preceding the number; that is, 911.)</span></span>

<span data-ttu-id="1cefb-191">직접 라우팅 사용자에 대한 긴급 통화를 동적으로 라우팅하는 능력은 특정 국가 내의 긴급 통화 네트워크에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-191">The ability to dynamically route emergency calls for Direct Routing users varies depending on the emergency calling network within a given country.</span></span> <span data-ttu-id="1cefb-192">두 가지 솔루션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-192">There are two solutions available:</span></span>

- <span data-ttu-id="1cefb-193">긴급 라우팅 서비스 공급자(미국에만 해당)</span><span class="sxs-lookup"><span data-stu-id="1cefb-193">Emergency Routing Service Providers (US only)</span></span> 
- <span data-ttu-id="1cefb-194">ELIN(긴급 위치 식별 번호) 게이트웨이 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="1cefb-194">Emergency Location Identification Number (ELIN) gateway applications</span></span>

#### <a name="emergency-routing-service-providers"></a><span data-ttu-id="1cefb-195">응급 라우팅 서비스 공급자</span><span class="sxs-lookup"><span data-stu-id="1cefb-195">Emergency Routing Service Providers</span></span>

<span data-ttu-id="1cefb-196">미국에는 발신자 위치에 따라 긴급 통화를 자동으로 라우팅할 수 있는 수많은 인증된 ERSP(긴급 라우팅 서비스 공급자)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-196">In the United States, there are numerous certified Emergency Routing Service Providers (ERSPs) that can automatically route emergency calls based upon the location of the caller.</span></span>

- <span data-ttu-id="1cefb-197">응급 라우팅 서비스 공급자가 직접 라우팅 배포에 통합된 경우 동적으로 획득한 위치가 있는 응급 전화는 해당 위치를 제공하는 PSAP(Public Safety Answering Point)로 자동으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-197">If an Emergency Routing Service Provider is integrated into a Direct Routing deployment, emergency calls with a dynamically acquired location will be automatically routed to the Public Safety Answering Point (PSAP) serving that location.</span></span>

-  <span data-ttu-id="1cefb-198">동적으로 획득한 위치가 없는 긴급 통화는 업데이트된 위치에 따라 적절한 디스패치 센터에 통화를 연결하기 전에 사용자의 현재 위치를 결정하기 위해 먼저 화면이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-198">Emergency calls without a dynamically acquired location are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center based upon the updated location.</span></span>

<span data-ttu-id="1cefb-199">자세한 내용은 직접 라우팅에 대해 인증된 세션 [테두리 컨트롤러를 참조하세요.](direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="1cefb-199">For more information, see [Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>


#### <a name="emergency-location-identification-number-elin-applications"></a><span data-ttu-id="1cefb-200">ELIN(긴급 위치 식별 번호) 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="1cefb-200">Emergency Location Identification Number (ELIN) applications</span></span>

<span data-ttu-id="1cefb-201">SBC(세션 테두리 컨트롤러)는 ELIN(긴급 위치 식별 번호) 애플리케이션을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-201">Session Border Controllers (SBCs) can include Emergency Location Identification Number (ELIN) applications.</span></span> <span data-ttu-id="1cefb-202">SBC ELIN 애플리케이션이 직접 라우팅 배포에 통합된 경우 ELIN 애플리케이션에서 긴급 주소 및 관련 전화 번호를 구성한 다음, 해당 PSTN의 긴급 통화 데이터베이스에 ELIN 레코드를 업로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-202">If an SBC ELIN application is integrated into a Direct Routing deployment, you must configure the emergency addresses and associated telephone numbers in the ELIN application, and then upload the ELIN records to the emergency calling database in the respective PSTN.</span></span>  <span data-ttu-id="1cefb-203">ELIN 식별자가 있는 Teams 긴급 위치는 ELIN 애플리케이션 내의 긴급 위치와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-203">Teams emergency locations with an ELIN identifier must match those within the ELIN application.</span></span>

<span data-ttu-id="1cefb-204">동적으로 획득한 위치가 있는 긴급 호출이 적절한 SBC로 라우팅된 경우 ELIN 애플리케이션은 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-204">When an emergency call with a dynamically acquired location is routed to the appropriate SBC, the ELIN application:</span></span>

- <span data-ttu-id="1cefb-205">발신자 긴급 위치를 구문 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-205">Parses the emergency location of the caller.</span></span>
- <span data-ttu-id="1cefb-206">위치를 ELIN 레코드와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-206">Matches the location to an ELIN record.</span></span>
- <span data-ttu-id="1cefb-207">긴급 발신자 번호를 ELIN 전화 번호로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-207">Substitutes the emergency caller's number with the ELIN phone number.</span></span>
- <span data-ttu-id="1cefb-208">호출을 해당 위치에 제공하는 PSAP로 라우팅한 다음 디스패치는 업로드된 ELIN 레코드에서 위치를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-208">Routes the call to the PSAP serving that location, and then the dispatchers obtain the location from the uploaded ELIN record.</span></span>

<span data-ttu-id="1cefb-209">긴급 번호로 다시 전화를 걸면 ELIN 애플리케이션에서 원래 긴급 발신자 번호로의 역방향 번호 대용을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-209">Upon a call back to the emergency number, the ELIN application will do the reverse called number substitution to that of the original emergency caller.</span></span> 

<span data-ttu-id="1cefb-210">자세한 내용은 직접 라우팅에 대해 인증된 세션 [테두리 컨트롤러를 참조하세요.](direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="1cefb-210">For more information, see [Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>


## <a name="security-desk-notification"></a><span data-ttu-id="1cefb-211">보안 데스크 알림</span><span class="sxs-lookup"><span data-stu-id="1cefb-211">Security desk notification</span></span>

<span data-ttu-id="1cefb-212">보안 데스크 알림은 Microsoft 통화 요금제와 전화 시스템 직접 라우팅 모두에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-212">Security desk notification is available with both Microsoft Calling Plans and Phone System Direct Routing.</span></span>

<span data-ttu-id="1cefb-213">Teams 긴급 통화 정책(TeamsEmergencyCallingPolicy)을 사용하여 긴급 통화 중에 알림을 해야 하는 사용자와 알림을 어떻게 하도록 구성할 수 있습니다. 채팅 전용, 전화 회의 및 음소거 또는 전화 회의 및 음소거 기능입니다. 단, 음소거를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-213">You use a Teams emergency calling policy (TeamsEmergencyCallingPolicy) to configure who should be notified during an emergency call and how they are notified: chat only, conferenced in and muted, or conferenced in and muted but with the ability to unmute.</span></span>  <span data-ttu-id="1cefb-214">긴급 통화에 참가할 사용자 또는 그룹의 외부 PSTN 번호를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-214">You can also specify an external PSTN number of a user or group to call and join the emergency call.</span></span> 

<span data-ttu-id="1cefb-215">Teams 사용자 계정에 응급 통화 정책을 부여하거나 네트워크 사이트에 할당하거나 둘 다에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-215">An emergency calling policy can be granted to a Teams user account, assigned to a network site, or both.</span></span>  <span data-ttu-id="1cefb-216">Teams 클라이언트가 시작되거나 네트워크 연결을 변경하면 Teams에서 클라이언트가 있는 네트워크 사이트의 보기를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-216">When a Teams client starts or changes a network connection, Teams performs a lookup of the network site where the client is located:</span></span>

- <span data-ttu-id="1cefb-217">긴급 통화 정책이 네트워크 사이트와 연결된 경우 사이트 정책은 보안 데스크 알림을 구성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-217">If an emergency calling policy is associated with a network site, then the site policy is used to configure security desk notification.</span></span>

- <span data-ttu-id="1cefb-218">사이트와 연결된 긴급 통화 정책이 없는 경우 또는 클라이언트가 정의되지 않은 사이트에서 연결되어 있는 경우 사용자 계정과 연결된 긴급 통화 정책을 사용하여 보안 데스크 알림을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-218">If there is no emergency calling policy associated with the site, or if the client is connected at an undefined site, then the emergency calling policy associated with the user account is used to configure security desk notification.</span></span>  

- <span data-ttu-id="1cefb-219">Teams 클라이언트가 긴급 통화 정책을 받을 수 없는 경우 사용자는 보안 데스크 알림을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-219">If the Teams client is unable to obtain an emergency calling policy, then the user is not enabled for security desk notification.</span></span>

<span data-ttu-id="1cefb-220">긴급 통화 중에는 보안 데스크가 전화로 회의를 진행하며, 보안 데스크 사용자의 환경은 Teams 긴급 통화 정책에 따라 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-220">During an emergency call, a security desk is conferenced into the call and the experience of the security desk user is controlled based upon the Teams emergency calling policy.</span></span> <span data-ttu-id="1cefb-221">각 보안 데스크 구성원과 그룹 채팅이 시작되는데, 긴급 발신자 위치는 중요한 메시지 알림을 통해 공유됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-221">A group chat is started with each security desk member, and the location of the emergency caller is shared via an important message notification.</span></span>  <span data-ttu-id="1cefb-222">정책의 일부로 회의 옵션이 구성된 경우 각 보안 데스크 사용자는 회의의 일부로 추가적으로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cefb-222">If a conference option is configured as part of the policy, each security desk user is additionally called as part of the conference.</span></span>

    
## <a name="related-topics"></a><span data-ttu-id="1cefb-223">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1cefb-223">Related topics</span></span>

- [<span data-ttu-id="1cefb-224">긴급 전화 정책 관리</span><span class="sxs-lookup"><span data-stu-id="1cefb-224">Manage emergency calling policies</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="1cefb-225">긴급 통화 라우팅 정책 관리 </span><span class="sxs-lookup"><span data-stu-id="1cefb-225">Manage emergency call routing policies </span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="1cefb-226">조직의 응급 위치 추가, 변경 또는 제거</span><span class="sxs-lookup"><span data-stu-id="1cefb-226">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="1cefb-227">사용자의 긴급 위치 지정 또는 변경</span><span class="sxs-lookup"><span data-stu-id="1cefb-227">Assign or change an emergency location for your user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="1cefb-228">동적인 긴급 전화 계획 및 구성</span><span class="sxs-lookup"><span data-stu-id="1cefb-228">Plan and configure dynamic emergency calling</span></span>](configure-dynamic-emergency-calling.md)
