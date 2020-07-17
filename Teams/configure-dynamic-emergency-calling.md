---
title: 동적인 긴급 전화 구성
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
f1.keywords:
- NOCSH
description: Microsoft 통화 계획 및 전화 시스템을 구성 하는 방법에 대 한 자세한 내용은 동적 긴급 통화 호출 기능을 라우팅 하세요.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 27ee8dd17b3948d373b5a6c13a210d298ee10d8c
ms.sourcegitcommit: a22a7b7e4bf556ee3e5e2e51c6f9f1c865a0724a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083158"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a><span data-ttu-id="87ade-103">동적인 긴급 전화 계획 및 구성</span><span class="sxs-lookup"><span data-stu-id="87ade-103">Plan and configure dynamic emergency calling</span></span> 

<span data-ttu-id="87ade-104">Microsoft 통화 요금제 및 전화 시스템 다이렉트 라우팅을 위한 동적 긴급 통화는 팀 클라이언트의 현재 위치에 따라 긴급 전화를 구성 하 고 라우팅하고 보안 사용자에 게 알릴 수 있는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-104">Dynamic emergency calling for Microsoft Calling Plans and Phone System Direct Routing provides the capability to configure and route emergency calls and notify security personnel based on the current location of the Teams client.</span></span>  

<span data-ttu-id="87ade-105">테 넌 트 관리자가 정의한 네트워크 토폴로지에 따라 팀 클라이언트는 LIS (위치 정보 서비스)에 대 한 요청에 네트워크 연결 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-105">Based on the network topology that the tenant administrator defines, the Teams client provides network connectivity information in a request to the Location Information Service (LIS).</span></span> <span data-ttu-id="87ade-106">일치 하는 항목이 있으면 LIS가 클라이언트에 대 한 위치를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-106">If there's a match, the LIS returns a location to the client.</span></span> <span data-ttu-id="87ade-107">이 위치 데이터는 다시 클라이언트로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-107">This location data is transmitted back to the client.</span></span>  

<span data-ttu-id="87ade-108">팀 클라이언트는 비상 전화의 일부로 위치 데이터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-108">The Teams client includes location data as part of an emergency call.</span></span> <span data-ttu-id="87ade-109">그런 다음 응급 서비스 공급자가이 데이터를 사용 하 여 적절 한 공공 안전 응답 시점 (PSAP)을 확인 하 고, PSAP 디스패처가 호출자의 위치를 가져올 수 있도록 해당 PSAP에 대 한 통화 경로를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-109">This data is then used by the emergency service provider to determine the appropriate Public Safety Answering Point (PSAP) and to route the call to that PSAP, which allows the PSAP dispatcher to obtain the caller's location.</span></span>  

<span data-ttu-id="87ade-110">동적 비상 전화의 경우 다음이 발생 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-110">For dynamic emergency calling, the following must occur:</span></span>

1. <span data-ttu-id="87ade-111">네트워크 관리자는 네트워크 설정 및 LIS를 구성 하 여 네트워크/비상 위치 맵을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-111">The network administrator configures network settings and the LIS to create a network/emergency location map.</span></span>

   <span data-ttu-id="87ade-112">직접 라우팅의 경우 비상 전화 라우팅과 파트너 연결에 대 한 추가 구성이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-112">For Direct Routing, additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span> <span data-ttu-id="87ade-113">관리자는 긴급 한 위치 Id 번호 (ELIN) 응용 프로그램에 대 한 SBC (세션 경계 컨트롤러)를 구성 **하거나** (미국) 긴급 라우팅 서비스 (영어)에 대 한 연결을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-113">The administrator must configure connection to an Emergency Routing Service (ERS) provider (United States) **OR** configure the Session Border Controller (SBC) for an Emergency Location Identification Number (ELIN) application.</span></span>

2. <span data-ttu-id="87ade-114">시작 하는 동안 주기적으로 또는 네트워크 연결이 변경 되 면 팀 클라이언트는 네트워크 연결 정보를 포함 하는 위치 요청을 네트워크 설정 및 LIS에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-114">During startup and periodically afterwards, or when a network connection is changed, the Teams client sends a location request that contains its network connectivity information to the network settings and the LIS.</span></span>

   - <span data-ttu-id="87ade-115">네트워크 설정 사이트가 일치 하는 경우-긴급 통화 정책이 해당 사이트에서 팀 클라이언트로 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-115">If there's a network settings site match – emergency calling policies are returned to the Teams client from that site.</span></span> <span data-ttu-id="87ade-116">(정책에 대 한 자세한 내용은 [응급 정책 구성을](#configure-emergency-policies)참조 하세요.)</span><span class="sxs-lookup"><span data-stu-id="87ade-116">(For more information about policies, see [Configure emergency policies](#configure-emergency-policies)).</span></span>

   - <span data-ttu-id="87ade-117">LIS가 일치 하는 경우-팀 클라이언트가 연결 된 네트워크 요소의 긴급 위치가 팀 클라이언트에 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-117">If there's an LIS match – an emergency location from the network element the Teams client is connected to is returned to the Teams client.</span></span>

3. <span data-ttu-id="87ade-118">팀 클라이언트에서 비상 전화를 받으면 긴급 위치가 PSTN 네트워크로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-118">When the Teams client makes an emergency call, the emergency location is conveyed to the PSTN network.</span></span>

   <span data-ttu-id="87ade-119">직접 라우팅의 경우 관리자는 해당 공급자에 대 한 비상 전화를 보내거나 응용 프로그램에서 SBC ELIN 구성 하도록 SBC를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-119">For Direct Routing, the administrator must configure the SBC to send emergency calls to the ERS provider or configure the SBC ELIN application.</span></span>

<span data-ttu-id="87ade-120">이 문서에는 다음 섹션이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-120">This article contains the following sections.</span></span>

- [<span data-ttu-id="87ade-121">긴급 주소 구성</span><span class="sxs-lookup"><span data-stu-id="87ade-121">Configure emergency addresses</span></span>](#assign-emergency-addresses)
- [<span data-ttu-id="87ade-122">네트워크 설정 구성</span><span class="sxs-lookup"><span data-stu-id="87ade-122">Configure network settings</span></span>](#configure-network-settings)
- [<span data-ttu-id="87ade-123">위치 정보 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="87ade-123">Configure Location Information Service</span></span>](#configure-location-information-service)
- [<span data-ttu-id="87ade-124">응급 정책 구성</span><span class="sxs-lookup"><span data-stu-id="87ade-124">Configure emergency policies</span></span>](#configure-emergency-policies)
- [<span data-ttu-id="87ade-125">사용자 및 사이트 사용</span><span class="sxs-lookup"><span data-stu-id="87ade-125">Enable users and sites</span></span>](#enable-users-and-sites)
- [<span data-ttu-id="87ade-126">비상 통화 테스트</span><span class="sxs-lookup"><span data-stu-id="87ade-126">Test emergency calling</span></span>](#test-emergency-calling)

<span data-ttu-id="87ade-127">적절 한 공개 안전 응답 시점 (PSAP)으로 자동 라우팅 하는 기능은 팀 사용자의 사용 국가에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-127">The ability to do automatic routing to the appropriate Public Safety Answering Point (PSAP) varies depending on the country of usage of the Teams user.</span></span>

<span data-ttu-id="87ade-128">긴급 주소 및 긴급 통화 라우팅, 국가별 정보, 네트워크 설정 및 네트워크 토폴로지에 대 한 정보를 포함 하 여 긴급 통화에 대 한 자세한 내용은 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="87ade-128">For more information about emergency calling, including information about emergency addresses and emergency call routing, information specific to countries, and information about network settings and network topology, see the following:</span></span>

- [<span data-ttu-id="87ade-129">긴급 통화 관리</span><span class="sxs-lookup"><span data-stu-id="87ade-129">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="87ade-130">클라우드 음성 기능에 대 한 네트워크 설정 관리</span><span class="sxs-lookup"><span data-stu-id="87ade-130">Manage network settings for cloud voice features</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="87ade-131">클라우드 음성 기능에 대한 네트워크 토폴로지 관리</span><span class="sxs-lookup"><span data-stu-id="87ade-131">Manage your network topology for cloud voice features</span></span>](manage-your-network-topology.md)

## <a name="supported-clients"></a><span data-ttu-id="87ade-132">지원 되는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="87ade-132">Supported clients</span></span>

<span data-ttu-id="87ade-133">현재 지원 되는 클라이언트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-133">The following clients are currently supported.</span></span>  <span data-ttu-id="87ade-134">자주 확인 하 여이 목록에 대 한 업데이트를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="87ade-134">Check back often to see updates to this list.</span></span>

- <span data-ttu-id="87ade-135">Microsoft Windows 용 팀 데스크톱 클라이언트</span><span class="sxs-lookup"><span data-stu-id="87ade-135">Teams desktop client for Microsoft Windows</span></span>
- <span data-ttu-id="87ade-136">Apple macOS 용 팀 데스크톱 클라이언트</span><span class="sxs-lookup"><span data-stu-id="87ade-136">Teams desktop client for Apple macOS</span></span>
- <span data-ttu-id="87ade-137">Apple iOS 클라이언트 버전 1.0.92.2019121004 및 App Store 버전 1.0.92 이상에 대 한 팀 모바일 클라이언트</span><span class="sxs-lookup"><span data-stu-id="87ade-137">Teams mobile client for Apple iOS client version 1.0.92.2019121004 and App Store version 1.0.92 and greater</span></span>
- <span data-ttu-id="87ade-138">Android 클라이언트 및 Google Play 스토어 버전 1416/1.0.0.2019121201 이상에 대 한 팀 모바일 클라이언트</span><span class="sxs-lookup"><span data-stu-id="87ade-138">Teams mobile client for Android client and Google Play store version 1416/1.0.0.2019121201 and greater</span></span>
- <span data-ttu-id="87ade-139">팀 전화 버전 1449/1.0.94.2019110802 이상</span><span class="sxs-lookup"><span data-stu-id="87ade-139">Teams phone version 1449/1.0.94.2019110802 and greater</span></span>
- <span data-ttu-id="87ade-140">팀 대화방 버전 4.4.25.0 이상</span><span class="sxs-lookup"><span data-stu-id="87ade-140">Teams Rooms version 4.4.25.0 and greater</span></span>

## <a name="assign-emergency-addresses"></a><span data-ttu-id="87ade-141">긴급 주소 할당</span><span class="sxs-lookup"><span data-stu-id="87ade-141">Assign emergency addresses</span></span>

<span data-ttu-id="87ade-142">호출 계획 사용자와 위치를 동적으로 가져오는 데 필요한 네트워크 식별자에 모두 긴급 주소를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-142">You can assign emergency addresses to both Calling Plan users and to the network identifiers that are required for dynamically obtaining a location.</span></span> <span data-ttu-id="87ade-143">(서브넷 및 WiFi AP가 지원 됨, 이더넷 스위치/포트에 대 한 지원이 보류 중입니다).</span><span class="sxs-lookup"><span data-stu-id="87ade-143">(Subnet and WiFi AP are supported; support for Ethernet switch/port is pending).</span></span>

<span data-ttu-id="87ade-144">미국 내에서 긴급 통화를 자동으로 라우팅하는 것을 지원 하려면 네트워크 식별자에 할당 된 비상 위치에 연결 된 지역 코드가 포함 되어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-144">To support automated routing of emergency calls within the United States, you must ensure that the emergency locations that are assigned to network identifiers include the associated geo codes.</span></span> <span data-ttu-id="87ade-145">(지역 코드가 없는 긴급 주소는 동적 위치에 필요한 네트워크 식별자에 할당할 수 없습니다.)</span><span class="sxs-lookup"><span data-stu-id="87ade-145">(Emergency addresses without geo codes can't be assigned to the network identifiers that are required for dynamic locations.)</span></span>

<span data-ttu-id="87ade-146">Azure 맵은 위치 기반 서비스에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-146">Azure Maps is used for location-based services.</span></span>  <span data-ttu-id="87ade-147">Microsoft 팀 관리 센터를 사용 하 여 긴급 주소를 입력 하면 팀에서 Azure 지도에서 주소를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-147">When you enter an emergency address by using the Microsoft Teams admin center, Teams checks Azure Maps for the address:</span></span>

- <span data-ttu-id="87ade-148">일치 하는 항목이 발견 되 면 지역 코드도 자동으로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-148">If a match is found, the geo codes are automatically included.</span></span>

- <span data-ttu-id="87ade-149">일치 하는 항목이 없는 경우 긴급 주소를 수동으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-149">If a match isn't found, you will have the opportunity to manually create an emergency address.</span></span> <span data-ttu-id="87ade-150">핀 드롭 기능을 사용 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-150">You can use the PIN drop feature to do this.</span></span> 

<span data-ttu-id="87ade-151">즉, 호출 계획 사용자에 게 할당 하기 위해 만든 기존 긴급 위치가 동적 위치를 대상으로 할 경우 지역 코드를 포함 하도록 동일한 주소를 다시 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-151">This means that if an existing emergency location that is created for assigning to Calling Plan users is intended for a dynamic location, the same address needs to be re-created to include the geo codes.</span></span> <span data-ttu-id="87ade-152">두 위치를 구분 하려면 다른 설명을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-152">To distinguish between the two locations, you should include a different description.</span></span> <span data-ttu-id="87ade-153">새 비상 위치는 이전 위치에 있는 사용자에 게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-153">The new emergency location can be assigned to the users who have the old location.</span></span> <span data-ttu-id="87ade-154">완전히 마이그레이션된 경우 이전 위치를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-154">When fully migrated, the old location can be deleted.</span></span>

<span data-ttu-id="87ade-155">Microsoft 팀 관리 센터에서 또는 PowerShell을 사용 하 여 긴급 주소를 추가 하 고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-155">You add and assign emergency addresses in the Microsoft Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="87ade-156">자세한 내용은 [조직의 긴급 위치 추가](add-change-remove-emergency-location-organization.md) 및 [사용자에 대 한 긴급 위치 지정](assign-change-emergency-location-user.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="87ade-156">For more information, see [Add an emergency location for your organization](add-change-remove-emergency-location-organization.md) and [Assign an emergency location for a user](assign-change-emergency-location-user.md).</span></span>

## <a name="configure-network-settings"></a><span data-ttu-id="87ade-157">네트워크 설정 구성</span><span class="sxs-lookup"><span data-stu-id="87ade-157">Configure network settings</span></span>

<span data-ttu-id="87ade-158">네트워크 설정은 팀 클라이언트의 위치를 결정 하는 데 사용 되며, 긴급 통화 정책 및 긴급 한 위치를 동적으로 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-158">Network settings are used to determine the location of a Teams client, and to dynamically obtain emergency calling policies and an emergency location.</span></span> <span data-ttu-id="87ade-159">조직에서 응급 통화 기능을 원하는 방식에 따라 네트워크 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-159">You can configure network settings according to how your organization wants emergency calling to function.</span></span>

<span data-ttu-id="87ade-160">네트워크 설정에는 서브넷 컬렉션을 포함 하는 사이트가 포함 되며,이는 사용자에 대 한 동적 정책 할당에 독점적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-160">Network settings include sites that include a collection of subnets and these are used exclusively for dynamic policy assignment to users.</span></span> <span data-ttu-id="87ade-161">예를 들어, 비상 전화 정책 및 긴급 통화 라우팅 정책은 "Redmond 사이트"에 할당 되어 집 또는 다른 Microsoft 위치에서 로밍 하는 모든 사용자가 레드먼드에 대 한 긴급 전화 번호, 라우팅 및 보안 데스크를 사용 하 여 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-161">For example, an emergency calling policy and an emergency call routing policy might be assigned to the "Redmond site" so that any user that roams from home or another Microsoft location is configured with emergency numbers, routing, and security desk specific to Redmond.</span></span>  

>[!Note]
><span data-ttu-id="87ade-162">서브넷은 LIS에도 정의할 수 있으며 비상 위치에 연결 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-162">Subnets can also be defined in LIS and can be associated with an emergency location.</span></span>  

<span data-ttu-id="87ade-163">다음 정의를 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-163">Keep the following definitions in mind.</span></span> <span data-ttu-id="87ade-164">자세한 내용은 [클라우드 음성 기능에 대 한 네트워크 설정을](cloud-voice-network-settings.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="87ade-164">For more information, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

- <span data-ttu-id="87ade-165">신뢰할 수 있는 IP 주소에는 엔터프라이즈 네트워크의 인터넷 외부 IP 주소 컬렉션이 포함 되며, 사용자의 끝점이 회사 네트워크 내에 있는지 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-165">Trusted IP addresses contain a collection of the internet external IP addresses of the enterprise network and are used to determine if the user's endpoint is inside the corporate network.</span></span> <span data-ttu-id="87ade-166">사용자의 외부 IP 주소가 신뢰할 수 있는 IP 주소의 IP 주소와 일치 하는 경우에만 동적 정책 또는 위치를 가져오려고 시도 하는 것이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-166">An attempt to obtain a dynamic policy or location will only be made if the user's external IP address matches an IP address in the trusted IP address.</span></span> <span data-ttu-id="87ade-167">IPv4 또는 IPv6 IP 주소에 대해 일치가 이루어질 수 있으며, 네트워크 설정으로 전송 되는 IP 패킷의 형식에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-167">A match can be made against either IPv4 or IPv6 IP addresses and is dependent upon the format of the IP packet sent to the network settings.</span></span>  <span data-ttu-id="87ade-168">공용 IP 주소에 IPv4와 IPv6이 모두 있는 경우에는 둘 다 신뢰할 수 있는 IP 주소로 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-168">(If a public IP address has both IPv4 and IPv6, you need to add both as trusted IP addresses.)</span></span>

- <span data-ttu-id="87ade-169">네트워크 지역에는 네트워크 사이트 컬렉션이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-169">A network region contains a collection of network sites.</span></span> 

- <span data-ttu-id="87ade-170">네트워크 사이트는 사무실, 건물 집합, 캠퍼스 등의 실제 가치를 가진 조직이 있는 위치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-170">A network site represents a location where your organization has a physical value, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="87ade-171">이러한 사이트는 IP 서브넷의 모음으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-171">These sites are defined as a collection of IP subnets.</span></span>

- <span data-ttu-id="87ade-172">네트워크 서브넷은 특정 네트워크 사이트와 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-172">A network subnet must be associated with a specific network site.</span></span> <span data-ttu-id="87ade-173">클라이언트의 위치는 네트워크 서브넷 및 연결 된 네트워크 사이트를 기준으로 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-173">A client's location is determined based on the network subnet and the associated network site.</span></span>  

<span data-ttu-id="87ade-174">Microsoft 팀 관리 센터에서 또는 PowerShell을 사용 하 여 네트워크 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-174">You configure network settings in the Microsoft Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="87ade-175">자세한 내용은 [클라우드 음성 기능에 대 한 네트워크 토폴로지 관리](manage-your-network-topology.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="87ade-175">To learn more, see [Manage your network topology for cloud voice features](manage-your-network-topology.md).</span></span>

<span data-ttu-id="87ade-176">네트워크 설정 (예: 새 주소, 네트워크 식별자 등)에 대 한 일부 변경 사항이 팀 클라이언트에 게 전파 되 고 사용 가능 하도록 하는 데는 몇 시간 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-176">Note that it can take some time (up to a couple of hours) for some changes to network settings (such as a new address, network identifier, and so on) to propagate and be available to Teams clients.</span></span>  

<span data-ttu-id="87ade-177">**통화 요금제 사용자:**</span><span class="sxs-lookup"><span data-stu-id="87ade-177">**For Calling Plan users:**</span></span>

- <span data-ttu-id="87ade-178">보안 데스크 알림의 동적 구성이 필요한 경우에는 신뢰할 수 있는 IP 주소와 네트워크 사이트를 모두 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-178">If dynamic configuration of security desk notification is required, you must configure both trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="87ade-179">동적 위치만 필요한 경우에는 신뢰할 수 있는 IP 주소만 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-179">If only dynamic locations are required, you must configure only trusted IP addresses.</span></span>

- <span data-ttu-id="87ade-180">둘 다 필요 하지 않은 경우 네트워크 설정 구성이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-180">If neither are required, configuring network settings isn't required.</span></span> 

<span data-ttu-id="87ade-181">**직접 라우팅 사용자의 경우:**</span><span class="sxs-lookup"><span data-stu-id="87ade-181">**For Direct Routing users:**</span></span>

- <span data-ttu-id="87ade-182">보안 데스크 알림의 긴급 통화 또는 동적 구성을 동적으로 사용할 필요가 있는 경우에는 신뢰할 수 있는 IP 주소와 네트워크 사이트를 모두 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-182">If dynamic enablement of emergency calling or dynamic configuration of security desk notification is required, then you must configure both Trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="87ade-183">동적 위치만 필요한 경우에는 신뢰할 수 있는 IP 주소만 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-183">If only dynamic locations are required, you must configure only trusted IP addresses.</span></span>

- <span data-ttu-id="87ade-184">둘 다 필요 하지 않은 경우 네트워크 설정 구성이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-184">If neither are required, configuring network settings isn't required.</span></span>


## <a name="configure-location-information-service"></a><span data-ttu-id="87ade-185">위치 정보 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="87ade-185">Configure Location Information Service</span></span>

<span data-ttu-id="87ade-186">팀 클라이언트는 여러 네트워크 식별자와 연결 된 위치에서 긴급 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-186">A Teams client obtains emergency addresses from the locations associated with different network identifiers.</span></span> <span data-ttu-id="87ade-187">서브넷과 WAPs (무선 액세스 지점)가 모두 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-187">Both subnets and wireless access points (WAPs) are supported.</span></span> <span data-ttu-id="87ade-188">(이더넷 스위치/포트에 대 한 지원이 보류 중입니다.)</span><span class="sxs-lookup"><span data-stu-id="87ade-188">(Support for Ethernet switch/port is pending.)</span></span>

<span data-ttu-id="87ade-189">클라이언트가 위치를 가져오려면 네트워크 식별자 (서브넷, WAPs, 스위치, 포트), 긴급 위치로 LIS를 채워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-189">For a client to obtain a location, you must populate the LIS with network identifiers (subnets, WAPs, switches, ports) and emergency locations.</span></span> <span data-ttu-id="87ade-190">Microsoft 팀 관리 센터에서 또는 PowerShell을 사용 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-190">You can do this in the Microsoft Teams admin center or by using PowerShell.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="87ade-191">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="87ade-191">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="87ade-192">왼쪽 탐색 창에서 **지역**  >  **네트워크 & 위치로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-192">In the left navigation, go to **Locations** > **Networks & locations**.</span></span>
2. <span data-ttu-id="87ade-193">추가 하려는 네트워크 식별자를 나타내는 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-193">Click the tab that represents the network identifier that you want to add.</span></span> <span data-ttu-id="87ade-194">예를 들어 **서브넷**, **wi-fi 액세스 지점**, **스위치**또는 **포트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-194">For example, click **Subnets**, **Wi-Fi access points**, **Switches**, or **Ports**.</span></span> <span data-ttu-id="87ade-195">그런 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-195">Then click **Add**.</span></span>
3. <span data-ttu-id="87ade-196">필드를 완성 하 고 긴급 위치를 추가한 다음 **적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-196">Complete the fields, add an emergency location, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="87ade-197">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="87ade-197">Using PowerShell</span></span>

<span data-ttu-id="87ade-198">다음 cmdlet을 사용 하 여 포트, 스위치, 서브넷 및 WAPs를 LIS에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-198">Use the following cmdlets to add ports, switches, subnets, and WAPs to the LIS.</span></span>

- <span data-ttu-id="87ade-199">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelissubnet?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet</span><span class="sxs-lookup"><span data-stu-id="87ade-199">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelissubnet?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet</span></span>
- <span data-ttu-id="87ade-200">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisport?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisport?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort</span><span class="sxs-lookup"><span data-stu-id="87ade-200">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisport?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisport?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort</span></span>
- <span data-ttu-id="87ade-201">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint</span><span class="sxs-lookup"><span data-stu-id="87ade-201">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint</span></span>
- <span data-ttu-id="87ade-202">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisswitch?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch</span><span class="sxs-lookup"><span data-stu-id="87ade-202">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisswitch?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch</span></span>

>[!Important]
><span data-ttu-id="87ade-203">네트워크 사이트의 일부로 서브넷을 사용 하는 경우 동적 위치를 렌더링 하기 위해 위치 정보 서비스에서 다시 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-203">If subnets are being used as part of network sites, they must be redefined in the Location Information Service to render dynamic locations.</span></span>

## <a name="configure-emergency-policies"></a><span data-ttu-id="87ade-204">응급 정책 구성</span><span class="sxs-lookup"><span data-stu-id="87ade-204">Configure emergency policies</span></span>

<span data-ttu-id="87ade-205">다음 정책을 사용 하 여 비상 전화를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-205">Use the following policies to configure emergency calling.</span></span> <span data-ttu-id="87ade-206">Microsoft 팀 관리 센터에서 또는 PowerShell을 사용 하 여 이러한 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-206">You can manage these policies in the Microsoft Teams admin center or by using PowerShell.</span></span>

- <span data-ttu-id="87ade-207">**긴급 통화 라우팅 정책** – 직접 라우팅에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-207">**Emergency call routing policy** – Applies only to Direct Routing.</span></span> <span data-ttu-id="87ade-208">이 정책은 긴급 전화 번호, 필요한 경우에는 마스크, 숫자 당 PSTN 경로를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-208">This policy configures the emergency numbers, masks per number if desired, and the PSTN route per number.</span></span>  <span data-ttu-id="87ade-209">이 정책을 사용자, 네트워크 사이트 또는 둘 다에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-209">You can assign this policy to users, to network sites, or to both.</span></span> <span data-ttu-id="87ade-210">(통화 계획 팀 클라이언트는 Microsoft 365 또는 Office 365 사용 위치를 기반으로 국가의 비상 전화를 사용 하 여 응급 통화로 자동으로 활성화 됩니다.)  자세한 내용은 [직접 라우팅에 대 한 긴급 통화 라우팅 정책 관리](manage-emergency-call-routing-policies.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="87ade-210">(Calling Plans Teams clients are automatically enabled for emergency calling with the emergency numbers from the country based upon their Microsoft 365 or Office 365 usage location.)  To  learn more, see [Manage emergency call routing policies for Direct Routing](manage-emergency-call-routing-policies.md).</span></span>

- <span data-ttu-id="87ade-211">**비상 통화 정책** -통화 요금제 및 직접 라우팅에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-211">**Emergency calling policy** - Applies to Calling Plans and Direct Routing.</span></span> <span data-ttu-id="87ade-212">이 정책은 비상 통화가 이루어질 때 보안 데스크 알림 환경을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-212">This policy configures the security desk notification experience when an emergency call is made.</span></span> <span data-ttu-id="87ade-213">알림을 받을 사람과 알리는 방법을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-213">You can set who to notify and how they are notified.</span></span> <span data-ttu-id="87ade-214">예를 들어 조직의 보안 지원팀에 자동으로 알리고 긴급 통화를 수신 대기 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-214">For example, to automatically notify your organization's security desk and have them listen in on emergency calls.</span></span>  <span data-ttu-id="87ade-215">이 정책은 사용자 또는 네트워크 사이트에 할당 하거나 둘 다에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-215">This policy can either be assigned to users or network sites or both.</span></span> <span data-ttu-id="87ade-216">자세히 알아보려면 [팀에서 긴급 통화 정책 관리](manage-emergency-calling-policies.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="87ade-216">To learn more, see [Manage emergency calling policies in Teams](manage-emergency-calling-policies.md).</span></span>

## <a name="enable-users-and-sites"></a><span data-ttu-id="87ade-217">사용자 및 사이트 사용</span><span class="sxs-lookup"><span data-stu-id="87ade-217">Enable users and sites</span></span>

<span data-ttu-id="87ade-218">긴급 통화 라우팅 정책 및 비상 전화 정책을 사용자 및 사이트에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-218">You can assign emergency call routing policies and emergency calling policies to users and to sites.</span></span> <span data-ttu-id="87ade-219">긴급 통화 라우팅 정책은 직접 라우팅에만 적용 된다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="87ade-219">Keep in mind that emergency call routing policies apply to Direct Routing only.</span></span> <span data-ttu-id="87ade-220">(이 정책을 호출 계획 사용자에 게 할당 하는 것이 가능 하지만, 정책은 아무런 영향을 주지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="87ade-220">(Although it's possible to assign this policy to a Calling Plan user, the policy will have no effect.)</span></span>

<span data-ttu-id="87ade-221">Microsoft 팀 관리 센터에서 또는 PowerShell을 사용 하 여 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-221">You assign policies in the Microsoft Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="87ade-222">자세히 알아보려면 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="87ade-222">To learn more, see:</span></span>

- [<span data-ttu-id="87ade-223">직접 라우팅에 대 한 긴급 통화 라우팅 정책 관리</span><span class="sxs-lookup"><span data-stu-id="87ade-223">Manage emergency call routing policies for Direct Routing</span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="87ade-224">팀에서 긴급 통화 정책 관리</span><span class="sxs-lookup"><span data-stu-id="87ade-224">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)

<span data-ttu-id="87ade-225">다음은 PowerShell의 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-225">Here's some PowerShell examples.</span></span>

<span data-ttu-id="87ade-226">특정 사용자에 게 보안 데스크 알림을 사용 하도록 설정 하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-226">To enable a specific user for security desk notification, use the following command:</span></span>

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

<span data-ttu-id="87ade-227">"Contoso 비상 통화 정책 1" 이라는 정책을 사이트 1에 할당 하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-227">To assign a policy called "Contoso Emergency Calling Policy 1" to Site 1, use the following command:</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

<span data-ttu-id="87ade-228">특정 직접 라우팅 사용자에 게 긴급 통화를 사용 하도록 설정 하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-228">To enable a specific Direct Routing user for emergency calling, use the following command:</span></span>

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

<span data-ttu-id="87ade-229">사이트 1에 "Contoso 뉴욕 긴급 통화 라우팅" 이라는 정책을 할당 하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-229">To assign a policy called "Contoso New York Emergency Call Routing" to Site 1, use the following command:</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

<span data-ttu-id="87ade-230">긴급 통화 정책을 네트워크 사이트 및 사용자에 게 할당 하 고 해당 사용자가 해당 네트워크 사이트에 있는 경우 네트워크 사이트에 할당 된 정책이 사용자에 게 할당 된 정책 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-230">If you assigned an emergency calling policy to a network site and to a user, and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="test-emergency-calling"></a><span data-ttu-id="87ade-231">비상 통화 테스트</span><span class="sxs-lookup"><span data-stu-id="87ade-231">Test emergency calling</span></span>

<span data-ttu-id="87ade-232">미국에서 일부 응급 라우팅 서비스 공급자 (ERSPs)는 비상 전화 테스트 봇을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-232">Some Emergency Routing Service Providers (ERSPs) in the United States offer an emergency calling test bot.</span></span>

- <span data-ttu-id="87ade-233">**통화 요금제 미국 내 사용자** 는 미리 정의 된 긴급 전화 번호 933를 사용 하 여 긴급 통화 구성의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-233">**Calling Plan users in the United States** can use the predefined test emergency number 933 to validate their emergency calling configuration.</span></span> <span data-ttu-id="87ade-234">이 번호는 봇으로 라우팅되며 다음으로 발신자 전화 번호 (통화 라인 ID), 긴급 주소 또는 위치, 통화가 자동으로 PSAP 또는 차단 됨에 의해 전환 되는지 여부를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-234">This number is routed to a bot, which then echoes back the caller phone number (calling line ID), emergency address or location, and whether the call would be automatically routed to the PSAP or screened first.</span></span>

- <span data-ttu-id="87ade-235">**직접 라우팅 미국 내 고객은** 테스트 서비스를 위해 해당 ersp와 조화 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87ade-235">**Direct Routing customers in the United States** should coordinate with their ERSP for a test service.</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="87ade-236">관련 항목</span><span class="sxs-lookup"><span data-stu-id="87ade-236">Related topics</span></span>

- [<span data-ttu-id="87ade-237">긴급 통화 관리</span><span class="sxs-lookup"><span data-stu-id="87ade-237">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="87ade-238">긴급 전화 정책 관리</span><span class="sxs-lookup"><span data-stu-id="87ade-238">Manage emergency calling policies</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="87ade-239">긴급 통화 라우팅 정책 관리</span><span class="sxs-lookup"><span data-stu-id="87ade-239">Manage emergency call routing policies </span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="87ade-240">조직의 응급 위치 추가, 변경 또는 제거</span><span class="sxs-lookup"><span data-stu-id="87ade-240">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="87ade-241">사용자의 긴급 위치 지정 또는 변경</span><span class="sxs-lookup"><span data-stu-id="87ade-241">Assign or change an emergency location for your user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="87ade-242">클라우드 음성 기능에 대한 네트워크 설정</span><span class="sxs-lookup"><span data-stu-id="87ade-242">Network settings for cloud voice features</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="87ade-243">클라우드 음성 기능에 대한 네트워크 토폴로지 관리</span><span class="sxs-lookup"><span data-stu-id="87ade-243">Manage your network topology for cloud voice features</span></span>](manage-your-network-topology.md)
