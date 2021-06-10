---
title: Teams Contoso 사례 연구
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams 기업에 대한 음성 사례 연구
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4503576df8d8e9f3d332cda45eb235d8162cf53
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786102"
---
# <a name="contoso-case-study-emergency-calling"></a><span data-ttu-id="5bdc5-103">Contoso 사례 연구: 긴급 통화</span><span class="sxs-lookup"><span data-stu-id="5bdc5-103">Contoso case study: Emergency calling</span></span>

<span data-ttu-id="5bdc5-104">긴급 통화 주소, 장소, 긴급 위치 및 등록된 주소와 관련된 긴급 통화 및 용어의 가용성을 이해하기 위해 Contoso는 긴급 통화 관리 및 계획 및 동적 긴급 통화 구성을 &mdash; &mdash; [검토했습니다.](configure-dynamic-emergency-calling.md) [](what-are-emergency-locations-addresses-and-call-routing.md)</span><span class="sxs-lookup"><span data-stu-id="5bdc5-104">To understand the availability of emergency calling and terminology related to emergency calling&mdash;Emergency Address, Place, Emergency Location, and Registered address&mdash;Contoso reviewed [Manage emergency calling](what-are-emergency-locations-addresses-and-call-routing.md) and [Plan and configure dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span>

<span data-ttu-id="5bdc5-105">Office 365 계획 사용자가 긴급 통화에 대해 자동으로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bdc5-105">In Office 365, a Calling Plan user is automatically enabled for emergency calling.</span></span> <span data-ttu-id="5bdc5-106">그러나 미국 내 통화 계획 사용자만 긴급 통화 라우팅에 동적 위치를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdc5-106">But only Calling Plan users in the United States can use dynamic locations for routing emergency calls.</span></span> 

<span data-ttu-id="5bdc5-107">직접 라우팅의 경우 Contoso는 긴급 호출을 라우팅하고 파트너 연결을 위해 추가 구성이 필요하다는 것을 배웠습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdc5-107">For Direct Routing, Contoso learned that additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span> <span data-ttu-id="5bdc5-108">관리자는 ERSP(긴급 라우팅 서비스 공급자)에 대한 연결을 구성하거나 ELIN(긴급 위치 식별 번호) 애플리케이션에 대해 SBC(세션 경계 컨트롤러)를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bdc5-108">The administrator must configure connection to an Emergency Routing Service Provider (ERSP) (United States) OR configure the Session Border Controller (SBC) for an Emergency Location Identification Number (ELIN) application.</span></span>

<span data-ttu-id="5bdc5-109">Contoso에는 미국 및 미국 외부에 사무실이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdc5-109">Contoso has offices in the United States and outside of the United States:</span></span>

- <span data-ttu-id="5bdc5-110">미국의 Contoso Calling Plan 사용자는 동적 위치를 사용하여 긴급 통화를 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdc5-110">In the United States, Contoso Calling Plan users can use dynamic locations for routing emergency calls.</span></span> 

- <span data-ttu-id="5bdc5-111">미국 외의 Contoso에는 통화 요금제를 사용하는 사이트와 직접 라우팅을 통해 전화 시스템 사이트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdc5-111">Outside of the United States, Contoso has some sites that use Calling Plans and some sites that are connected to Phone System through Direct Routing.</span></span>

## <a name="emergency-calling-use-cases"></a><span data-ttu-id="5bdc5-112">긴급 통화 사용 사례</span><span class="sxs-lookup"><span data-stu-id="5bdc5-112">Emergency calling use cases</span></span>

<span data-ttu-id="5bdc5-113">Contoso가 시스템에 연결하는 방법을 결정한 전화 Contoso는 다음 긴급 호출 사용 사례를 식별했습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdc5-113">After deciding how Contoso will connect to Phone system, Contoso identified the following Emergency calling use cases:</span></span> 

- [<span data-ttu-id="5bdc5-114">미국의 요금제 사용자 호출</span><span class="sxs-lookup"><span data-stu-id="5bdc5-114">Calling Plan user in the United States</span></span>](#calling-plan-user-in-the-united-states) 

- [<span data-ttu-id="5bdc5-115">미국 외부의 계획 사용자 호출</span><span class="sxs-lookup"><span data-stu-id="5bdc5-115">Calling Plan user outside of the United States</span></span>](#calling-plan-user-outside-of-the-united-states)

- [<span data-ttu-id="5bdc5-116">직접 라우팅을 통해 전화 시스템 사용자</span><span class="sxs-lookup"><span data-stu-id="5bdc5-116">User who connects to Phone System through Direct Routing</span></span>](#user-who-connects-to-phone-system-through-direct-routing )


### <a name="calling-plan-user-in-the-united-states"></a><span data-ttu-id="5bdc5-117">미국의 요금제 사용자 호출</span><span class="sxs-lookup"><span data-stu-id="5bdc5-117">Calling Plan user in the United States</span></span>  

<span data-ttu-id="5bdc5-118">전화 번호를 긴급 위치와 연결해야 하는 경우의 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdc5-118">There are requirements for when the phone number needs to be associated with an emergency location.</span></span> <span data-ttu-id="5bdc5-119">이러한 요구 사항을 이해하기 위해 Contoso는 통화 계획에 대한 고려 [사항을 검토했습니다.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="5bdc5-119">To understand these requirements, Contoso reviewed [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> 

<span data-ttu-id="5bdc5-120">이러한 요구 사항에 따라 Contoso는 미국의 사용자에게 번호가 할당될 때 위치를 전화 번호와 연결하기로 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdc5-120">Based on these requirements, Contoso decided to associate the location with the telephone number when a number is assigned to a user in the United States.</span></span>

### <a name="calling-plan-user-outside-of-the-united-states"></a><span data-ttu-id="5bdc5-121">미국 외부의 계획 사용자 호출</span><span class="sxs-lookup"><span data-stu-id="5bdc5-121">Calling Plan user outside of the United States</span></span> 

<span data-ttu-id="5bdc5-122">전화 번호를 긴급 위치와 연결해야 하는 경우를 이해하기 위해 Contoso는 통화 계획에 대한 고려 사항을 [검토했습니다.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="5bdc5-122">To understand when a phone number needs to be associated with an emergency location, Contoso reviewed  [Considerations for Calling Plans](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans).</span></span> <span data-ttu-id="5bdc5-123">Contoso는 요구 사항에 따라 다음을 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdc5-123">Based on the requirements, Contoso decided the following:</span></span>  

-  <span data-ttu-id="5bdc5-124">Contoso는 캐나다의 사용자에게 번호가 할당될 때 위치를 전화 번호와 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="5bdc5-124">Contoso will associate the location with the telephone number when a number is assigned to a user in Canada.</span></span> 

- <span data-ttu-id="5bdc5-125">Contoso는 전화 번호를 Office 365 다른 서비스 공급자 또는 통신사에서 번호가 전송될 때 긴급 위치를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="5bdc5-125">Contoso will assign an emergency location when the phone number is acquired from Office 365 or when a number is transferred from another service provider or carrier.</span></span> 

### <a name="user-who-connects-to-phone-system-through-direct-routing"></a><span data-ttu-id="5bdc5-126">직접 라우팅을 통해 전화 시스템 사용자</span><span class="sxs-lookup"><span data-stu-id="5bdc5-126">User who connects to Phone System through Direct Routing</span></span> 

<span data-ttu-id="5bdc5-127">이 사용 사례에 대한 긴급 라우팅을 계획하기 위해 Contoso는 직접 라우팅에 대한 고려 [사항을 검토했습니다.](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="5bdc5-127">To plan for emergency routing for this use case, Contoso reviewed [Considerations for Direct Routing](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing).</span></span> <span data-ttu-id="5bdc5-128">직접 라우팅 사용자는 통화 계획 사용자와 동일한 방식으로 긴급 전화를 받지 못하기 때문에 Contoso는 긴급 통화를 제공하는 방법을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bdc5-128">Because Direct Routing users do not receive emergency calling in the same manner as Calling Plan users, Contoso had to decide on how to provide emergency calling.</span></span> <span data-ttu-id="5bdc5-129">ERSP(긴급 라우팅 서비스 공급자)에 직접 라우팅을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdc5-129">Direct Routing can be connected to an Emergency Routing Service Provider (ERSP).</span></span> <span data-ttu-id="5bdc5-130">직접 라우팅에는 ELIN(긴급 위치 식별 번호)이 포함된 SBC가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdc5-130">Direct Routing can also have an SBC that includes an Emergency Location Identification Number (ELIN).</span></span>   

#### <a name="emergency-routing-service-provider-ersp-considerations"></a><span data-ttu-id="5bdc5-131">ERSP(긴급 라우팅 서비스 공급자) 고려 사항</span><span class="sxs-lookup"><span data-stu-id="5bdc5-131">Emergency Routing Service Provider (ERSP) considerations</span></span>

<span data-ttu-id="5bdc5-132">ERSP(긴급 라우팅 서비스 공급자)는 호출자 위치에 따라 긴급 호출을 자동으로 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdc5-132">The Emergency Routing Service Providers (ERSPs) can automatically route emergency calls based upon the location of the caller.</span></span>  

- <span data-ttu-id="5bdc5-133">긴급 라우팅 서비스 공급자가 직접 라우팅 배포에 통합된 경우 동적으로 획득된 위치가 있는 긴급 호출은 해당 위치를 제공하는 PSAP(공용 안전 응답 지점)로 자동으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bdc5-133">If an Emergency Routing Service Provider is integrated into a Direct Routing deployment, emergency calls with a dynamically acquired location will be automatically routed to the Public Safety Answering Point (PSAP) serving that location.</span></span> 

- <span data-ttu-id="5bdc5-134">동적으로 획득된 위치가 없는 긴급 호출은 먼저 업데이트된 위치에 따라 적절한 디스패치 센터에 호출을 연결하기 전에 사용자의 현재 위치를 확인하도록 심사됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bdc5-134">Emergency calls without a dynamically acquired location are first screened to determine the current location of the user before connecting the call to the appropriate dispatch center based upon the updated location.</span></span> 


#### <a name="elin-considerations"></a><span data-ttu-id="5bdc5-135">ELIN 고려 사항</span><span class="sxs-lookup"><span data-stu-id="5bdc5-135">ELIN considerations</span></span>

<span data-ttu-id="5bdc5-136">SBC ELIN 애플리케이션이 직접 라우팅 배포에 통합된 경우 긴급 주소를 전화 번호와 연결하려면 추가 구성 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bdc5-136">If an SBC ELIN application is integrated into a Direct Routing deployment, additional configuration steps need to occur to associate the emergency addresses with telephone numbers.</span></span>  

<span data-ttu-id="5bdc5-137">Contoso는 ELIN(긴급 위치 식별 번호) 애플리케이션이 포함된 세션 테두리 컨트롤러를 사용하기로 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdc5-137">Contoso decided to use Session Border Controllers that include Emergency Location Identification Number (ELIN) applications.</span></span>  

## <a name="security-desk-notification"></a><span data-ttu-id="5bdc5-138">보안 데스크 알림</span><span class="sxs-lookup"><span data-stu-id="5bdc5-138">Security desk notification</span></span>

<span data-ttu-id="5bdc5-139">긴급 통화가 배치된 경우 보안 데스크에 알리는 기능을 Microsoft 통화 요금제 및 직접 라우팅에 전화 시스템 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdc5-139">The ability to notify the security desk when an emergency call is placed is available for both Microsoft Calling Plans and Phone System Direct Routing.</span></span> <span data-ttu-id="5bdc5-140">Contoso는 보안 데스크 알림의 세부 정보를 검토하여 해당 사무실에서 구성해야 하는지 확인했습니다.</span><span class="sxs-lookup"><span data-stu-id="5bdc5-140">Contoso reviewed the details in the Security desk notification to determine if this should be configured at their offices</span></span>  

<span data-ttu-id="5bdc5-141">Contoso는 보안 데스크 알림을 사용하기로 결정했다.</span><span class="sxs-lookup"><span data-stu-id="5bdc5-141">Contoso decided to use security desk notification.</span></span>

## <a name="configuration"></a><span data-ttu-id="5bdc5-142">구성</span><span class="sxs-lookup"><span data-stu-id="5bdc5-142">Configuration</span></span> 

<span data-ttu-id="5bdc5-143">Contoso는 다음에 대한 동적 긴급 호출 [구성의 단계를](configure-dynamic-emergency-calling.md) 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="5bdc5-143">Contoso followed the steps in [Configure dynamic emergency calling](configure-dynamic-emergency-calling.md) to:</span></span> 

- <span data-ttu-id="5bdc5-144">긴급 주소 할당</span><span class="sxs-lookup"><span data-stu-id="5bdc5-144">Assign emergency addresses</span></span> 

- <span data-ttu-id="5bdc5-145">네트워크 설정 구성</span><span class="sxs-lookup"><span data-stu-id="5bdc5-145">Configure network settings</span></span> 

- <span data-ttu-id="5bdc5-146">위치 정보 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="5bdc5-146">Configure Location Information Service</span></span> 

- <span data-ttu-id="5bdc5-147">긴급 정책 구성</span><span class="sxs-lookup"><span data-stu-id="5bdc5-147">Configure emergency policies</span></span> 

- <span data-ttu-id="5bdc5-148">사용자 및 사이트 사용</span><span class="sxs-lookup"><span data-stu-id="5bdc5-148">Enable users and sites</span></span> 

- <span data-ttu-id="5bdc5-149">긴급 호출 테스트</span><span class="sxs-lookup"><span data-stu-id="5bdc5-149">Test emergency calling</span></span> 

<span data-ttu-id="5bdc5-150">동적 긴급 호출을 구성한 후 Contoso는 해당 사용자에게 위치를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bdc5-150">After dynamic emergency calling is configured, Contoso needed to assign the location to the appropriate user.</span></span>  

- <span data-ttu-id="5bdc5-151">조직의 응급 위치를 추가, 변경 또는 제거하려면 Contoso가 조직의 응급 위치 추가, 변경 또는 제거의 단계를 [따릅니다.](add-change-remove-emergency-location-organization.md)</span><span class="sxs-lookup"><span data-stu-id="5bdc5-151">To add, change, or remove an emergency location for your organization, Contoso followed the steps in [Add, change, or remove an emergency location for your organization](add-change-remove-emergency-location-organization.md)</span></span>

- <span data-ttu-id="5bdc5-152">건물, 바닥 및 사무실에 대한 장소를 만들기 위해 Contoso는 응급 위치에 대한 장소 추가, 변경 또는 제거의 단계를 [수행했습니다.](add-change-remove-emergency-place-organization.md)</span><span class="sxs-lookup"><span data-stu-id="5bdc5-152">To create places for buildings, floors, and offices, Contoso followed the steps in [Add, change, or remove a place for an emergency location](add-change-remove-emergency-place-organization.md) .</span></span> 

- <span data-ttu-id="5bdc5-153">Contoso는 긴급 위치를 할당하기 위해 사용자에 대한 긴급 위치를 할당하거나 변경하는 단계를 [따릅니다.](assign-change-emergency-location-user.md)</span><span class="sxs-lookup"><span data-stu-id="5bdc5-153">To assign an emergency location, Contoso followed the steps in [Assign or change an emergency location for a user](assign-change-emergency-location-user.md).</span></span> 

 