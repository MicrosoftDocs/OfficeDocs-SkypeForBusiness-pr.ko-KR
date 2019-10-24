---
title: 동적 비상 전화 구성
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: roykuntz
localization_priority: Normal
search.appverid: MET150
description: 동적 비상 전화 구성
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b166c93bb213fab6e8025a1837ef67baa65c884
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "37639361"
---
# <a name="plan-and-configure-dynamic-emergency-calling-for-calling-plans"></a><span data-ttu-id="0cf3d-103">통화 요금제에 대 한 동적 비상 전화 계획 및 구성</span><span class="sxs-lookup"><span data-stu-id="0cf3d-103">Plan and configure dynamic emergency calling for Calling Plans</span></span>
<span data-ttu-id="0cf3d-104">Microsoft 호출 요금제에 대 한 동적 비상 통화는 팀 클라이언트의 현재 위치를 기반으로 비상 전화를 구성 하 고 라우팅할 수 있는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-104">Dynamic emergency calling for Microsoft Calling Plans provides the capability to configure and route emergency calls based on the current location of the Teams client.</span></span>  <span data-ttu-id="0cf3d-105">적절 한 공개 안전 응답 시점 (PSAP)으로 자동 라우팅 하거나 보안 데스크 직원에 게 알리는 기능은 팀 사용자의 사용 국가에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-105">The ability to do automatic routing to the appropriate Public Safety Answering Point (PSAP) or to notify security desk personnel varies depending on the country of usage of the Teams user.</span></span>  

> [!Note] 
> <span data-ttu-id="0cf3d-106">현재 동적 비상 전화는 미국 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-106">Dynamic emergency calling is currently available only in the United States.</span></span> <span data-ttu-id="0cf3d-107">그러나 보안 데스크 알림은 국가 경계에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-107">Security desk notification, however, is supported across country boundaries.</span></span>

<span data-ttu-id="0cf3d-108">**미국 내에서**동적 긴급 전화 라우팅을 다음과 같이 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-108">**Within the United States**, you can configure dynamic emergency call routing as follows:</span></span>
  
- <span data-ttu-id="0cf3d-109">팀 클라이언트가 테 넌 트 정의 동적인 긴급 위치에 있는 경우 해당 클라이언트의 비상 호출은 해당 지리적 위치를 처리 하는 PSAP에 자동으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-109">If a Teams client is located at a tenant-defined dynamic emergency location, emergency calls from that client are automatically routed to the PSAP serving that geographic location.</span></span>  

- <span data-ttu-id="0cf3d-110">팀 클라이언트가 테 넌 트로 정의 된 동적 비상 위치에 없으면 해당 클라이언트의 비상 전화를 국가 콜 센터에서 확인 하 여 해당 지리적 위치를 처리 하는 PSAP로 호출을 전달 하기 전에 해당 전화를 통해 발신자의 위치를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-110">If a Teams client is not located at a tenant-defined dynamic emergency location, emergency calls from that client are screened by a national call center to determine the location of the caller before transferring the call to the PSAP serving that geographic location.</span></span>

<span data-ttu-id="0cf3d-111">다음과 같이 보안 데스크 알림을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-111">You can configure security desk notification as follows:</span></span>

- <span data-ttu-id="0cf3d-112">팀 클라이언트가 테 넌 트로 정의 된 네트워크 사이트에 있는 경우 해당 사이트에 대해 구성 된 보안 그룹 구성원에 게 알림이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-112">If a Teams client is located at a tenant-defined network site, the security group members configured for that site will be notified.</span></span>

- <span data-ttu-id="0cf3d-113">팀 클라이언트가 테 넌 트로 정의 된 네트워크 사이트에 없으면 사용자에 대해 구성 된 보안 그룹 구성원에 게 알림이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-113">If a Teams client is not located at a tenant-defined network site, the security group members configured for the user will be notified.</span></span>

<span data-ttu-id="0cf3d-114">**미국 이외의 지역**에서 비상 전화는 사용자에 게 할당 된 전화 번호로 매핑되는 psap로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-114">**Outside of the United States**, emergency calls are routed to the PSAP that is mapped to the phone number assigned to the user.</span></span>  <span data-ttu-id="0cf3d-115">멋진 영국 및 캐나다와 같은 일부 국가에서는 호출자를 적절 한 PSAP로 이전 하기 전에 전화 국내를, 다른 사용자는 현재 위치에 관계 없이 PSAP로 직접 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-115">Some countries, such as the Great Britain and Canada, screen the calls nationally before transferring the caller to the appropriate PSAP, while others route directly to the PSAP regardless of where the user is currently located.</span></span> 

<span data-ttu-id="0cf3d-116">모든 통화 계획 사용자에 대해 동적 보안 데스크 알림을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-116">Note that you can configure dynamic security desk notification for all Calling Plan users.</span></span>


## <a name="supported-clients"></a><span data-ttu-id="0cf3d-117">지원 되는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="0cf3d-117">Supported clients</span></span>

<span data-ttu-id="0cf3d-118">현재 지원 되는 클라이언트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-118">The following clients are currently supported.</span></span>  <span data-ttu-id="0cf3d-119">자주 확인 하 여이 목록에 대 한 업데이트를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-119">Check back often to see updates to this list.</span></span>

- <span data-ttu-id="0cf3d-120">Windows 용 팀 데스크톱 클라이언트</span><span class="sxs-lookup"><span data-stu-id="0cf3d-120">Teams desktop client for Windows</span></span>
- <span data-ttu-id="0cf3d-121">Mac 용 팀 데스크톱 클라이언트</span><span class="sxs-lookup"><span data-stu-id="0cf3d-121">Teams desktop client for Mac</span></span>

## <a name="configure-dynamic-emergency-calling"></a><span data-ttu-id="0cf3d-122">동적 비상 전화 구성</span><span class="sxs-lookup"><span data-stu-id="0cf3d-122">Configure dynamic emergency calling</span></span>

<span data-ttu-id="0cf3d-123">동적 비상 전화를 구성 하려면 다음 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-123">To configure dynamic emergency calling, you need to perform the following tasks:</span></span>

- [<span data-ttu-id="0cf3d-124">긴급 주소 구성</span><span class="sxs-lookup"><span data-stu-id="0cf3d-124">Configure emergency addresses</span></span>](#configure-emergency-addresses)
- [<span data-ttu-id="0cf3d-125">네트워크 설정 구성</span><span class="sxs-lookup"><span data-stu-id="0cf3d-125">Configure network settings</span></span>](#configure-network-settings)
- [<span data-ttu-id="0cf3d-126">위치 정보 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="0cf3d-126">Configure Location Information Service</span></span>](#configure-location-information-service)
- [<span data-ttu-id="0cf3d-127">응급 정책 구성</span><span class="sxs-lookup"><span data-stu-id="0cf3d-127">Configure emergency policies</span></span>](#configure-emergency-policies)
- [<span data-ttu-id="0cf3d-128">사용자 및 사이트 사용</span><span class="sxs-lookup"><span data-stu-id="0cf3d-128">Enable users and sites</span></span>](#enable-users-and-sites)
- [<span data-ttu-id="0cf3d-129">비상 통화 테스트</span><span class="sxs-lookup"><span data-stu-id="0cf3d-129">Test emergency calling</span></span>](#test-emergency-calling)


### <a name="configure-emergency-addresses"></a><span data-ttu-id="0cf3d-130">긴급 주소 구성</span><span class="sxs-lookup"><span data-stu-id="0cf3d-130">Configure emergency addresses</span></span>

<span data-ttu-id="0cf3d-131">미국 내에서 자동 라우팅을 지원 하려면 네트워크 식별자에 할당 된 비상 위치에 속하는 도심 주소를 완전히 구성 하 고 관련 지역 코드를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-131">To support automated routing within the United States, you must fully configure the civic address that is part of the emergency locations that are assigned to network identifiers--and include the associated geo codes.</span></span> <span data-ttu-id="0cf3d-132">(지역 코드가 없는 긴급 주소는 동적 위치에 필요한 네트워크 식별자에 할당할 수 없습니다.)</span><span class="sxs-lookup"><span data-stu-id="0cf3d-132">(Emergency addresses without geo-codes cannot be assigned to the network identifiers that are required for dynamic locations.)</span></span>

- <span data-ttu-id="0cf3d-133">Microsoft 팀 관리 센터를 통해 긴급 주소를 입력 하는 경우 일치 하는 항목이 발견 되 면 지역 코드가 자동으로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-133">If you enter an emergency address via the Microsoft Teams admin center, the geo codes are automatically included if a match is found.</span></span>

- <span data-ttu-id="0cf3d-134">일치 하는 항목이 자동으로 발견 되지 않으면 긴급 주소를 수동으로 만들 수 있는 기회가 생깁니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-134">If a match is not automatically found, you will have the opportunity to manually create an emergency address.</span></span>  

<span data-ttu-id="0cf3d-135">즉, 긴급 통화를 위해 기존 긴급 주소를 구성한 경우 지역 코드를 포함 하려면 같은 주소를 다시 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-135">This means that if an existing emergency address is configured for emergency calling, the same address needs to be re-created to include the geo codes.</span></span>  <span data-ttu-id="0cf3d-136">두 주소를 구분 하려면 다른 설명을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-136">To distinguish between the two addresses, you should include a different description.</span></span> <span data-ttu-id="0cf3d-137">이전 주소를 가진 사용자에 게 새로운 긴급 주소를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-137">The new emergency address can be assigned to the users who have the old address.</span></span> <span data-ttu-id="0cf3d-138">완전히 마이그레이션한 경우 이전 주소를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-138">When fully migrated, the old address can be deleted.</span></span> 

<span data-ttu-id="0cf3d-139">긴급 주소를 구성 하는 방법에 대 한 자세한 내용은 [긴급 위치, 장소 및 통화 라우팅 이란?](what-are-emergency-locations-addresses-and-call-routing.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-139">For more information about configuring emergency addresses, see [What are emergency locations, places, and call routing?](what-are-emergency-locations-addresses-and-call-routing.md).</span></span>

### <a name="configure-network-settings"></a><span data-ttu-id="0cf3d-140">네트워크 설정 구성</span><span class="sxs-lookup"><span data-stu-id="0cf3d-140">Configure network settings</span></span>

<span data-ttu-id="0cf3d-141">비상 전화를 라우팅하는 데 사용 되는 긴급 위치를 동적으로 획득 하도록 네트워크 설정을 구성 해야 하며, 선택적으로 보안 데스크 알림의 동적 구성을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-141">You need to configure network settings to dynamically obtain an emergency location used for routing emergency calls and, optionally, to provide dynamic configuration of security desk notifications.</span></span> <span data-ttu-id="0cf3d-142">필요한 응급 통화 환경에 따라 구성 해야 할 네트워크 설정이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-142">The emergency calling experience desired will dictate which network settings need to be configured.</span></span> 

<span data-ttu-id="0cf3d-143">다음 정의를 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-143">Keep the following definitions in mind:</span></span>

- <span data-ttu-id="0cf3d-144">신뢰할 수 있는 IP에는 엔터프라이즈 네트워크의 인터넷 외부 Ip 컬렉션이 포함 되며 사용자의 끝점이 회사 네트워크 내에 있는지 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-144">Trusted IP’s contain a collection of the Internet external IPs of the enterprise network and are used to determine if the user’s endpoint is inside the corporate network.</span></span> <span data-ttu-id="0cf3d-145">동적 위치는 사용자의 외부 IP가 신뢰할 수 있는 IP 컬렉션의 IP와 일치 하는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-145">Dynamic locations will only be enabled if the user’s external IP matches an IP in the Trusted IP collection.</span></span>  <span data-ttu-id="0cf3d-146">IPv4 또는 IPv6 IP 주소에 대해 일치가 이루어질 수 있으며, 네트워크 설정으로 전송 되는 IP 패킷의 형식에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-146">A match can be made against either IPv4 or IPv6 IP addresses and is dependent upon the format of the IP packet sent to the network settings.</span></span>

- <span data-ttu-id="0cf3d-147">네트워크 지역에는 네트워크 사이트 컬렉션이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-147">A network region contains a collection of network sites.</span></span> 

- <span data-ttu-id="0cf3d-148">네트워크 사이트는 사무실, 건물 집합, 캠퍼스 등의 실제 가치를 가진 조직이 있는 위치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-148">A network site represents a location where your organization has a physical value, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="0cf3d-149">이러한 사이트는 IP 서브넷의 모음으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-149">These sites are defined as a collection of IP subnets.</span></span>

- <span data-ttu-id="0cf3d-150">네트워크 서브넷은 특정 네트워크 사이트와 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-150">A network subnet must be associated with a specific network site.</span></span> <span data-ttu-id="0cf3d-151">클라이언트의 위치는 네트워크 서브넷 및 연결 된 네트워크 사이트를 기준으로 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-151">A client's location is determined based on the network subnet and the associated network site.</span></span>  


<span data-ttu-id="0cf3d-152">통화 요금제 사용자:</span><span class="sxs-lookup"><span data-stu-id="0cf3d-152">For Calling Plan users:</span></span>

- <span data-ttu-id="0cf3d-153">보안 데스크 알림의 동적 구성이 필요한 경우에는 신뢰할 수 있는 IP 주소와 네트워크 사이트를 모두 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-153">If dynamic configuration of security desk notification is required, then you must configure both Trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="0cf3d-154">동적 위치만 필요한 경우에는 신뢰할 수 있는 IP 주소만 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-154">If only dynamic locations are required, then you must configure only Trusted IP addresses.</span></span> 

- <span data-ttu-id="0cf3d-155">둘 다 필요 하지 않은 경우 네트워크 설정 구성이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-155">If neither are required, then configuration of network settings is not required.</span></span> 

<span data-ttu-id="0cf3d-156">자세한 내용은 네트워크 설정을 구성 하는 방법을 설명 하는 [위치 기반 라우팅에 대 한 네트워크 설정 구성을](location-based-routing-configure-network-settings.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-156">For more information, see [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md), which describes how to configure network settings.</span></span> <span data-ttu-id="0cf3d-157">(이 문서의 정보는 호출 계획과 직접 라우팅 모두에 적용 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="0cf3d-157">(The information in this article applies to both Calling Plans and Direct Routing.)</span></span>


### <a name="configure-location-information-service"></a><span data-ttu-id="0cf3d-158">위치 정보 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="0cf3d-158">Configure Location Information Service</span></span>

<span data-ttu-id="0cf3d-159">팀 클라이언트는 다양 한 네트워크 식별자와 연결 된 비상 위치에서 긴급 주소를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-159">A Teams client obtains emergency addresses from the emergency locations associated with different network identifiers.</span></span>  <span data-ttu-id="0cf3d-160">서브넷 및 무선 액세스 지점은 모두 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-160">Subnets and Wireless Access Points are both supported.</span></span> <span data-ttu-id="0cf3d-161">(이더넷 스위치/포트에 대 한 지원이 보류 중입니다.)</span><span class="sxs-lookup"><span data-stu-id="0cf3d-161">(Support for Ethernet switch/port is pending.)</span></span>

<span data-ttu-id="0cf3d-162">네트워크 식별자 및 비상 위치를 사용 하 여 LIS (위치 정보 서비스)를 구성 하려면 다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-162">To configure the Location Information Service (LIS) with network identifiers and emergency locations, use the following cmdlets:</span></span>

- <span data-ttu-id="0cf3d-163">Get, Set, Remove-CsOnlineLisPort</span><span class="sxs-lookup"><span data-stu-id="0cf3d-163">Get, Set, Remove -CsOnlineLisPort</span></span>
- <span data-ttu-id="0cf3d-164">Get, Set, Remove-CsOnlineLisSwitch</span><span class="sxs-lookup"><span data-stu-id="0cf3d-164">Get, Set, Remove -CsOnlineLisSwitch</span></span>
- <span data-ttu-id="0cf3d-165">Get, Set, Remove-CsOnlineLisSubnet</span><span class="sxs-lookup"><span data-stu-id="0cf3d-165">Get, Set, Remove -CsOnlineLisSubnet</span></span>
- <span data-ttu-id="0cf3d-166">Get, Set, Remove-CsOnlineLisWirelessAccessPoint</span><span class="sxs-lookup"><span data-stu-id="0cf3d-166">Get, Set, Remove -CsOnlineLisWirelessAccessPoint</span></span> 

> [!Important] 
> <span data-ttu-id="0cf3d-167">네트워크 사이트의 일부로 서브넷을 사용 하는 경우 동적 위치를 렌더링 하기 위해 위치 정보 서비스에서 다시 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-167">If subnets are being used as part of network sites, they must be redefined in the Location Information Service to render dynamic locations.</span></span>


### <a name="configure-emergency-policies"></a><span data-ttu-id="0cf3d-168">응급 정책 구성</span><span class="sxs-lookup"><span data-stu-id="0cf3d-168">Configure emergency policies</span></span>

<span data-ttu-id="0cf3d-169">응급 정책은 조직의 사용자가 긴급 통화를 할 때 어떤 일이 발생 하는지 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-169">Emergency policies determine what happens when a user in your organization makes an emergency call.</span></span>  <span data-ttu-id="0cf3d-170">사용자가 응급 서비스를 호출할 때 알림을 받을 사람과 알림 방법을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-170">You can set who to notify and how they are notified when a user calls emergency services.</span></span> <span data-ttu-id="0cf3d-171">예를 들어 조직의 보안 데스크에 자동으로 알리기 위해 정책 설정을 구성 하 고 긴급 통화를 수신 대기 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-171">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in on emergency calls.</span></span>

<span data-ttu-id="0cf3d-172">새로운, 설정 및 부여-CsTeamsEmergencyCalling 정책 cmdlet을 사용 하 여 긴급 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-172">You manage emergency policies by using the New-, Set- and Grant-CsTeamsEmergencyCalling Policy cmdlets.</span></span>  <span data-ttu-id="0cf3d-173">자세한 내용은 [팀에서 긴급 통화 정책 관리](manage-emergency-calling-policies.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-173">For more information, see [Manage emergency calling policies in Teams](manage-emergency-calling-policies.md).</span></span>


### <a name="enable-users-and-sites"></a><span data-ttu-id="0cf3d-174">사용자 및 사이트 사용</span><span class="sxs-lookup"><span data-stu-id="0cf3d-174">Enable users and sites</span></span>

<span data-ttu-id="0cf3d-175">통화 계획 사용자는 비상 전화에 대해 자동으로 사용 하도록 설정 되지만 다음 예제에 표시 된 대로 긴급 통화 정책을 구성 하 여 사용자에 게 보안 데스크 알림을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-175">While Calling Plan users are automatically enabled for emergency calling, you must enable users for security desk notification by configuring the emergency calling policy as shown in the following example:</span></span>


```
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

<span data-ttu-id="0cf3d-176">"Contoso 비상 전화 정책 1" 이라는 정책을 사이트 1에 할당 하는 다음 예와 같이 네트워크 사이트에 비상 통화 정책을 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-176">You can also assign the emergency calling policy to a network site as shown in the following example, which assigns a policy called "Contoso Emergency Calling Policy 1" to Site 1:</span></span>

```
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

<span data-ttu-id="0cf3d-177">긴급 통화 정책을 네트워크 사이트 및 사용자에 게 할당 하 고 해당 사용자가 해당 네트워크 사이트에 있는 경우 네트워크 사이트에 할당 된 정책이 사용자에 게 할당 된 정책 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-177">If you assigned an emergency calling policy to a network site and to a user, and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>


### <a name="test-emergency-calling"></a><span data-ttu-id="0cf3d-178">비상 통화 테스트</span><span class="sxs-lookup"><span data-stu-id="0cf3d-178">Test emergency calling</span></span>

<span data-ttu-id="0cf3d-179">미국에서 비상 전화를 테스트 하려면 미리 정의 된 긴급 테스트 비상 번호 933를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-179">To test emergency calling in the United States, use the predefined test emergency number 933.</span></span>  <span data-ttu-id="0cf3d-180">이 번호는 봇으로 라우팅되며 다음으로 발신자 전화 번호 (통화 라인 ID), 긴급 주소 또는 위치, 통화가 자동으로 PSAP에 라우팅되도록 또는 스크린 먼저 표시 되는지 여부 등으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="0cf3d-180">This number is routed to a bot, which then echoes back the caller phone number (calling line ID), emergency address or location, and whether the call is automatically routed to the PSAP or screened first.</span></span>  