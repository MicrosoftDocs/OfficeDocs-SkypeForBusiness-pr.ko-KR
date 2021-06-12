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
- m365initiative-voice
ms.reviewer: roykuntz
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
description: Microsoft 통화 계획을 구성하고 다이렉트 라우팅 동적 전화 시스템 긴급 통화 기능을 구성하는 방법에 대해 자세히 알아보도록 합니다.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ee730c737d105572c9c34c6f329b04de4f8f8472
ms.sourcegitcommit: 2419348e964cfe97b72d533f267c5d7055d5366f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/12/2021
ms.locfileid: "52910050"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a><span data-ttu-id="4e7c3-103">동적인 긴급 전화 계획 및 구성</span><span class="sxs-lookup"><span data-stu-id="4e7c3-103">Plan and configure dynamic emergency calling</span></span> 

<span data-ttu-id="4e7c3-104">Microsoft 통화 계획 및 전화 시스템 직접 라우팅에 대한 동적 긴급 호출은 클라이언트의 현재 위치에 따라 긴급 통화를 구성하고 라우팅하고 보안 담당자에게 Teams 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-104">Dynamic emergency calling for Microsoft Calling Plans and Phone System Direct Routing provides the capability to configure and route emergency calls and notify security personnel based on the current location of the Teams client.</span></span>  

<span data-ttu-id="4e7c3-105">테넌트 관리자가 정의하는 네트워크 토폴로지에 따라 Teams 클라이언트는 LIS(위치 정보 서비스)에 대한 요청에서 네트워크 연결 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-105">Based on the network topology that the tenant administrator defines, the Teams client provides network connectivity information in a request to the Location Information Service (LIS).</span></span> <span data-ttu-id="4e7c3-106">일치가 있는 경우 LIS는 클라이언트에 위치를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-106">If there's a match, the LIS returns a location to the client.</span></span> <span data-ttu-id="4e7c3-107">이 위치 데이터는 클라이언트로 다시 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-107">This location data is transmitted back to the client.</span></span>  

<span data-ttu-id="4e7c3-108">Teams 클라이언트에는 긴급 호출의 일부로 위치 데이터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-108">The Teams client includes location data as part of an emergency call.</span></span> <span data-ttu-id="4e7c3-109">그런 다음, 이 데이터는 응급 서비스 공급자가 적절한 PSAP(공용 안전 응답 지점)를 결정하고 해당 PSAP로 호출을 라우팅하는 데 사용됩니다. 이는 PSAP 디스패치가 발신자 위치를 얻을 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-109">This data is then used by the emergency service provider to determine the appropriate Public Safety Answering Point (PSAP) and to route the call to that PSAP, which allows the PSAP dispatcher to obtain the caller's location.</span></span>  

<span data-ttu-id="4e7c3-110">동적 긴급 호출의 경우 다음이 발생해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-110">For dynamic emergency calling, the following must occur:</span></span>

1. <span data-ttu-id="4e7c3-111">네트워크 관리자는 네트워크 설정 및 LIS를 구성하여 네트워크/긴급 위치 맵을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-111">The network administrator configures network settings and the LIS to create a network/emergency location map.</span></span>

   <span data-ttu-id="4e7c3-112">직접 라우팅의 경우 긴급 호출을 라우팅하고 파트너 연결을 위해 추가 구성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-112">For Direct Routing, additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span> <span data-ttu-id="4e7c3-113">관리자는 ERS(긴급 라우팅 **서비스)** 공급자(미국)에 대한 연결을 구성하거나 ELIN(긴급 위치 식별 번호) 애플리케이션에 대한 세션 경계 컨트롤러(SBC)를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-113">The administrator must configure connection to an Emergency Routing Service (ERS) provider (United States) **OR** configure the Session Border Controller (SBC) for an Emergency Location Identification Number (ELIN) application.</span></span>

2. <span data-ttu-id="4e7c3-114">시작 및 주기적으로 또는 네트워크 연결이 변경되는 Teams 클라이언트는 네트워크 연결 정보가 포함된 위치 요청을 네트워크 설정 및 LIS로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-114">During startup and periodically afterwards, or when a network connection is changed, the Teams client sends a location request that contains its network connectivity information to the network settings and the LIS.</span></span>

   - <span data-ttu-id="4e7c3-115">네트워크 설정 사이트 일치가 있는 경우 - 긴급 호출 정책은 해당 Teams 클라이언트에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-115">If there's a network settings site match – emergency calling policies are returned to the Teams client from that site.</span></span> <span data-ttu-id="4e7c3-116">정책에 대한 자세한 내용은 긴급 정책 [구성을 참조하세요.](#configure-emergency-policies)</span><span class="sxs-lookup"><span data-stu-id="4e7c3-116">(For more information about policies, see [Configure emergency policies](#configure-emergency-policies)).</span></span>

   - <span data-ttu-id="4e7c3-117">LIS 일치가 있는 경우 - 네트워크 요소의 긴급 위치인 Teams 클라이언트가 Teams 클라이언트로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-117">If there's an LIS match – an emergency location from the network element the Teams client is connected to is returned to the Teams client.</span></span> <span data-ttu-id="4e7c3-118">일치는 첫 번째 일치 결과가 반환되는 순서대로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-118">The match is performed in the following order with the first matched result being returned:</span></span>
       - <span data-ttu-id="4e7c3-119">WAP</span><span class="sxs-lookup"><span data-stu-id="4e7c3-119">WAP</span></span>
       - <span data-ttu-id="4e7c3-120">이더넷 스위치/포트</span><span class="sxs-lookup"><span data-stu-id="4e7c3-120">Ethernet switch/port</span></span>
       - <span data-ttu-id="4e7c3-121">이더넷 스위치</span><span class="sxs-lookup"><span data-stu-id="4e7c3-121">Ethernet switch</span></span>
       - <span data-ttu-id="4e7c3-122">서브넷</span><span class="sxs-lookup"><span data-stu-id="4e7c3-122">Subnet</span></span>

3. <span data-ttu-id="4e7c3-123">클라이언트가 Teams 호출하면 긴급 위치가 PSTN 네트워크로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-123">When the Teams client makes an emergency call, the emergency location is conveyed to the PSTN network.</span></span>

   <span data-ttu-id="4e7c3-124">직접 라우팅의 경우 관리자는 SBC를 구성하여 ERS 공급자에 긴급 호출을 보내거나 SBC ELIN 애플리케이션을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-124">For Direct Routing, the administrator must configure the SBC to send emergency calls to the ERS provider or configure the SBC ELIN application.</span></span>

<span data-ttu-id="4e7c3-125">이 문서에는 다음 섹션이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-125">This article contains the following sections.</span></span>

- [<span data-ttu-id="4e7c3-126">긴급 주소 구성</span><span class="sxs-lookup"><span data-stu-id="4e7c3-126">Configure emergency addresses</span></span>](#assign-emergency-addresses)
- [<span data-ttu-id="4e7c3-127">네트워크 설정 구성</span><span class="sxs-lookup"><span data-stu-id="4e7c3-127">Configure network settings</span></span>](#configure-network-settings)
- [<span data-ttu-id="4e7c3-128">위치 정보 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="4e7c3-128">Configure Location Information Service</span></span>](#configure-location-information-service)
- [<span data-ttu-id="4e7c3-129">긴급 정책 구성</span><span class="sxs-lookup"><span data-stu-id="4e7c3-129">Configure emergency policies</span></span>](#configure-emergency-policies)
- [<span data-ttu-id="4e7c3-130">사용자 및 사이트 사용</span><span class="sxs-lookup"><span data-stu-id="4e7c3-130">Enable users and sites</span></span>](#enable-users-and-sites)
- [<span data-ttu-id="4e7c3-131">긴급 호출 테스트</span><span class="sxs-lookup"><span data-stu-id="4e7c3-131">Test emergency calling</span></span>](#test-emergency-calling)

<span data-ttu-id="4e7c3-132">적절한 PSAP(공공 안전 응답 지점)에 대한 자동 라우팅을 할 수 있는 능력은 사용자의 사용 국가에 따라 Teams 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-132">The ability to do automatic routing to the appropriate Public Safety Answering Point (PSAP) varies depending on the country of usage of the Teams user.</span></span>

<span data-ttu-id="4e7c3-133">응급 주소 및 긴급 통화 라우팅에 대한 정보, 국가별 정보 및 네트워크 설정 및 네트워크 토폴로지에 대한 정보를 비롯한 긴급 통화에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-133">For more information about emergency calling, including information about emergency addresses and emergency call routing, information specific to countries, and information about network settings and network topology, see the following:</span></span>

- [<span data-ttu-id="4e7c3-134">긴급 통화 관리</span><span class="sxs-lookup"><span data-stu-id="4e7c3-134">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="4e7c3-135">클라우드 음성 기능에 대한 네트워크 설정 관리</span><span class="sxs-lookup"><span data-stu-id="4e7c3-135">Manage network settings for cloud voice features</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="4e7c3-136">클라우드 음성 기능에 대한 네트워크 토폴로지 관리</span><span class="sxs-lookup"><span data-stu-id="4e7c3-136">Manage your network topology for cloud voice features</span></span>](manage-your-network-topology.md)

<span data-ttu-id="4e7c3-137">정부 클라우드에서 사용할 수 있는 기능에 대한 자세한 내용은 이 문서의 끝부분에 있는 [정부](#government-support) 지원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-137">For more information about which features are available in the government clouds, see [Government support](#government-support) at the end of this article.</span></span>


## <a name="supported-clients"></a><span data-ttu-id="4e7c3-138">지원되는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="4e7c3-138">Supported clients</span></span>

<span data-ttu-id="4e7c3-139">다음 클라이언트는 현재 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-139">The following clients are currently supported.</span></span>  <span data-ttu-id="4e7c3-140">이 목록에 대한 업데이트를 확인한 후 자주 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-140">Check back often to see updates to this list.</span></span>

- <span data-ttu-id="4e7c3-141">Teams용 데스크톱 클라이언트 Windows</span><span class="sxs-lookup"><span data-stu-id="4e7c3-141">Teams desktop client for Microsoft Windows</span></span>
- <span data-ttu-id="4e7c3-142">Teams macOS용 데스크톱 클라이언트</span><span class="sxs-lookup"><span data-stu-id="4e7c3-142">Teams desktop client for Apple macOS</span></span>
- <span data-ttu-id="4e7c3-143">Teams iOS 클라이언트 버전 1.0.92.2019121004 및 App Store 버전 1.0.92 이상용 모바일 클라이언트</span><span class="sxs-lookup"><span data-stu-id="4e7c3-143">Teams mobile client for Apple iOS client version 1.0.92.2019121004 and App Store version 1.0.92 and greater</span></span>
- <span data-ttu-id="4e7c3-144">Teams 및 Google Play 스토어 버전 1416/1.0.2019121201 이상용 모바일 클라이언트</span><span class="sxs-lookup"><span data-stu-id="4e7c3-144">Teams mobile client for Android client and Google Play store version 1416/1.0.0.2019121201 and greater</span></span>
- <span data-ttu-id="4e7c3-145">Teams 버전 1449/1.0.94.2019110802 이상</span><span class="sxs-lookup"><span data-stu-id="4e7c3-145">Teams phone version 1449/1.0.94.2019110802 and greater</span></span>
- <span data-ttu-id="4e7c3-146">Teams 룸 버전 4.4.25.0 이상</span><span class="sxs-lookup"><span data-stu-id="4e7c3-146">Teams Rooms version 4.4.25.0 and greater</span></span>

> [!NOTE]
> <span data-ttu-id="4e7c3-147">보안 데스크 알림을 비롯한 동적 긴급 호출은 웹 클라이언트에서 지원되지 Teams 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-147">Dynamic emergency calling, including security desk notification, isn't supported on the Teams web client.</span></span> <span data-ttu-id="4e7c3-148">사용자가 PSTN Teams 웹 클라이언트를 사용하여 PSTN 번호를 호출하지 못하도록 Teams 호출 정책을 설정하고 웹 **PSTN** 호출 허용 설정을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-148">To prevent users from using the Teams web client to call PSTN numbers, you can set a Teams calling policy and turn off the **Allow web PSTN calling** setting.</span></span> <span data-ttu-id="4e7c3-149">자세한 내용은 [CsTeamsCallingPolicy 및 set-CsTeamsCallingPolicy의](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)Teams 참조 [](teams-calling-policy.md)</span><span class="sxs-lookup"><span data-stu-id="4e7c3-149">To learn more, see [Calling policies in Teams](teams-calling-policy.md) and [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> 

> [!NOTE]
> <span data-ttu-id="4e7c3-150">서브넷 및 WiFi 기반 위치는 모든 클라이언트에서 지원 Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-150">Subnet and WiFi-based locations are supported on all Teams clients.</span></span> <br>
> <span data-ttu-id="4e7c3-151">LLDP(이더넷/스위치)는 현재 Windows 버전 Windows 버전에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-151">Ethernet/Switch (LLDP) is only supported on Windows and only on Windows versions 8.1 and later at this time.</span></span>

## <a name="assign-emergency-addresses"></a><span data-ttu-id="4e7c3-152">긴급 주소 할당</span><span class="sxs-lookup"><span data-stu-id="4e7c3-152">Assign emergency addresses</span></span>

<span data-ttu-id="4e7c3-153">호출 계획 사용자와 위치를 동적으로 획득하는 데 필요한 네트워크 식별자 모두에 긴급 주소를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-153">You can assign emergency addresses to both Calling Plan users and to the network identifiers that are required for dynamically obtaining a location.</span></span> <span data-ttu-id="4e7c3-154">(서브넷 및 WiFi AP가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-154">(Subnet and WiFi AP are supported.</span></span> <span data-ttu-id="4e7c3-155">이더넷 스위치/포트는 현재 Windows 8.1 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-155">Ethernet switch/port is supported on Windows 8.1 and later at this time).</span></span>

<span data-ttu-id="4e7c3-156">미국 내에서 긴급 통화의 자동화된 라우팅을 지원하려면 네트워크 식별자에 할당된 긴급 위치에 연결된 지역 코드가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-156">To support automated routing of emergency calls within the United States, you must ensure that the emergency locations that are assigned to network identifiers include the associated geo codes.</span></span> <span data-ttu-id="4e7c3-157">(지역 코드가 없는 긴급 주소는 동적 위치에 필요한 네트워크 식별자에 할당할 수 없습니다.)</span><span class="sxs-lookup"><span data-stu-id="4e7c3-157">(Emergency addresses without geo codes can't be assigned to the network identifiers that are required for dynamic locations.)</span></span>

<span data-ttu-id="4e7c3-158">Azure 지도 기반 서비스에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-158">Azure Maps is used for location-based services.</span></span>  <span data-ttu-id="4e7c3-159">관리 센터를 사용하여 긴급 주소를 Microsoft Teams 경우 Teams Azure 지도 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-159">When you enter an emergency address by using the Microsoft Teams admin center, Teams checks Azure Maps for the address:</span></span>

- <span data-ttu-id="4e7c3-160">일치가 발견된 경우 지역 코드가 자동으로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-160">If a match is found, the geo codes are automatically included.</span></span>

- <span data-ttu-id="4e7c3-161">일치를 찾을 수 없는 경우 긴급 주소를 수동으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-161">If a match isn't found, you will have the opportunity to manually create an emergency address.</span></span> <span data-ttu-id="4e7c3-162">PIN 드롭 기능을 사용하여 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-162">You can use the PIN drop feature to do this.</span></span> 

<span data-ttu-id="4e7c3-163">즉, 호출 계획 사용자에게 할당하기 위해 만들어진 기존 긴급 위치가 동적 위치를 위한 경우 지역 코드를 포함하도록 동일한 주소를 다시 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-163">This means that if an existing emergency location that is created for assigning to Calling Plan users is intended for a dynamic location, the same address needs to be re-created to include the geo codes.</span></span> <span data-ttu-id="4e7c3-164">두 위치를 구분하기 위해 다른 설명을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-164">To distinguish between the two locations, you should include a different description.</span></span> <span data-ttu-id="4e7c3-165">새 비상 위치는 이전 위치가 있는 사용자에게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-165">The new emergency location can be assigned to the users who have the old location.</span></span> <span data-ttu-id="4e7c3-166">완전히 마이그레이션되면 이전 위치를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-166">When fully migrated, the old location can be deleted.</span></span>

<span data-ttu-id="4e7c3-167">관리 센터 또는 PowerShell을 사용하여 Microsoft Teams 비상 주소를 추가하고 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-167">You add and assign emergency addresses in the Microsoft Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="4e7c3-168">자세한 내용은 [조직의](add-change-remove-emergency-location-organization.md) 긴급 위치 추가 및 사용자에 대한 긴급 위치 [할당을 참조하세요.](assign-change-emergency-location-user.md)</span><span class="sxs-lookup"><span data-stu-id="4e7c3-168">For more information, see [Add an emergency location for your organization](add-change-remove-emergency-location-organization.md) and [Assign an emergency location for a user](assign-change-emergency-location-user.md).</span></span>

## <a name="configure-network-settings"></a><span data-ttu-id="4e7c3-169">네트워크 설정 구성</span><span class="sxs-lookup"><span data-stu-id="4e7c3-169">Configure network settings</span></span>

<span data-ttu-id="4e7c3-170">네트워크 설정은 클라이언트의 위치를 결정하고, Teams 응급 호출 정책 및 긴급 위치를 동적으로 얻는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-170">Network settings are used to determine the location of a Teams client, and to dynamically obtain emergency calling policies and an emergency location.</span></span> <span data-ttu-id="4e7c3-171">조직에서 긴급 호출 기능을 원하는 방법에 따라 네트워크 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-171">You can configure network settings according to how your organization wants emergency calling to function.</span></span>

<span data-ttu-id="4e7c3-172">네트워크 설정에는 서브넷 컬렉션이 포함된 사이트가 포함되어 있으며 이러한 사이트는 사용자에게 동적 정책 할당에 독점적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-172">Network settings include sites that include a collection of subnets and these are used exclusively for dynamic policy assignment to users.</span></span> <span data-ttu-id="4e7c3-173">예를 들어, 긴급 통화 정책 및 긴급 통화 라우팅 정책은 "Redmond 사이트"에 할당되어 집이나 다른 Microsoft 위치에서 로밍하는 모든 사용자가 Redmond 관련 긴급 번호, 라우팅 및 보안 데스크로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-173">For example, an emergency calling policy and an emergency call routing policy might be assigned to the "Redmond site" so that any user that roams from home or another Microsoft location is configured with emergency numbers, routing, and security desk specific to Redmond.</span></span>  

>[!Note]
><span data-ttu-id="4e7c3-174">또한 서브넷은 LIS에서 정의할 수 있으며 응급 위치와 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-174">Subnets can also be defined in LIS and can be associated with an emergency location.</span></span>  <span data-ttu-id="4e7c3-175">LIS 서브넷은 클라이언트에 할당된 서브넷 IP 범위와 일치하는 네트워크 ID로 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-175">LIS subnets must be defined by the Network ID matching the subnet IP range assigned to clients.</span></span> <span data-ttu-id="4e7c3-176">예를 들어 10.10.10.150/25의 클라이언트 IP/마스크에 대한 네트워크 ID는 **10.10.10.128입니다.**</span><span class="sxs-lookup"><span data-stu-id="4e7c3-176">For example, the network ID for a client IP/mask of 10.10.10.150/25 is **10.10.10.128**.</span></span> <span data-ttu-id="4e7c3-177">자세한 내용은 [TCP/IP](/troubleshoot/windows-client/networking/tcpip-addressing-and-subnetting)주소 및 하위 내기 기본 이해를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-177">For more information, see [Understand TCP/IP addressing and subnetting basics](/troubleshoot/windows-client/networking/tcpip-addressing-and-subnetting).</span></span>

<span data-ttu-id="4e7c3-178">다음 정의를 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-178">Keep the following definitions in mind.</span></span> <span data-ttu-id="4e7c3-179">자세한 내용은 클라우드 음성 기능에 [대한 네트워크 설정을 참조하세요.](cloud-voice-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="4e7c3-179">For more information, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

- <span data-ttu-id="4e7c3-180">신뢰할 수 있는 IP 주소는 엔터프라이즈 네트워크의 인터넷 외부 IP 주소 컬렉션을 포함하며 사용자의 엔드포인트가 회사 네트워크 내부에 있는지 확인하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-180">Trusted IP addresses contain a collection of the internet external IP addresses of the enterprise network and are used to determine if the user's endpoint is inside the corporate network.</span></span> <span data-ttu-id="4e7c3-181">동적 정책 또는 위치를 얻기 위한 시도는 사용자의 외부 IP 주소가 신뢰할 수 있는 IP 주소의 IP 주소와 일치하는 경우만 이행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-181">An attempt to obtain a dynamic policy or location will only be made if the user's external IP address matches an IP address in the trusted IP address.</span></span> <span data-ttu-id="4e7c3-182">IPv4 또는 IPv6 IP 주소에 대해 일치할 수 있으며 네트워크 설정으로 전송되는 IP 패킷의 형식에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-182">A match can be made against either IPv4 or IPv6 IP addresses and is dependent upon the format of the IP packet sent to the network settings.</span></span>  <span data-ttu-id="4e7c3-183">공용 IP 주소에 IPv4 및 IPv6이 모두 있는 경우 둘 다 신뢰할 수 있는 IP 주소로 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-183">(If a public IP address has both IPv4 and IPv6, you need to add both as trusted IP addresses.)</span></span>

- <span data-ttu-id="4e7c3-184">네트워크 지역에는 네트워크 사이트 모음이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-184">A network region contains a collection of network sites.</span></span> 

- <span data-ttu-id="4e7c3-185">네트워크 사이트는 조직에 사무실, 건물 집합 또는 캠퍼스와 같은 물리적 값이 있는 위치를 나타내고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-185">A network site represents a location where your organization has a physical value, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="4e7c3-186">이러한 사이트는 IP 서브넷의 컬렉션으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-186">These sites are defined as a collection of IP subnets.</span></span>

- <span data-ttu-id="4e7c3-187">네트워크 서브넷을 특정 네트워크 사이트와 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-187">A network subnet must be associated with a specific network site.</span></span> <span data-ttu-id="4e7c3-188">클라이언트의 위치는 네트워크 서브넷 및 연결된 네트워크 사이트에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-188">A client's location is determined based on the network subnet and the associated network site.</span></span>  

<span data-ttu-id="4e7c3-189">관리 센터에서 또는 PowerShell을 사용하여 Microsoft Teams 네트워크 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-189">You configure network settings in the Microsoft Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="4e7c3-190">자세한 내용은 클라우드 음성 기능에 대한 네트워크 [토폴로지 관리를 참조합니다.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="4e7c3-190">To learn more, see [Manage your network topology for cloud voice features](manage-your-network-topology.md).</span></span>

<span data-ttu-id="4e7c3-191">네트워크 설정(예: 새 주소, 네트워크 식별자 등)을 변경하여 클라이언트에서 전파하고 사용할 수 Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-191">Note that it can take some time (up to a couple of hours) for some changes to network settings (such as a new address, network identifier, and so on) to propagate and be available to Teams clients.</span></span>  

<span data-ttu-id="4e7c3-192">**요금제 사용자를 호출하는 경우:**</span><span class="sxs-lookup"><span data-stu-id="4e7c3-192">**For Calling Plan users:**</span></span>

- <span data-ttu-id="4e7c3-193">보안 데스크 알림의 동적 구성이 필요한 경우 신뢰할 수 있는 IP 주소와 네트워크 사이트를 모두 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-193">If dynamic configuration of security desk notification is required, you must configure both trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="4e7c3-194">동적 위치만 필요한 경우 신뢰할 수 있는 IP 주소만 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-194">If only dynamic locations are required, you must configure only trusted IP addresses.</span></span>

- <span data-ttu-id="4e7c3-195">둘 다 필요하지 않은 경우 네트워크 설정을 구성할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-195">If neither are required, configuring network settings isn't required.</span></span> 

<span data-ttu-id="4e7c3-196">**직접 라우팅 사용자의 경우:**</span><span class="sxs-lookup"><span data-stu-id="4e7c3-196">**For Direct Routing users:**</span></span>

- <span data-ttu-id="4e7c3-197">긴급 통화 또는 보안 데스크 알림의 동적 구성이 필요한 경우 신뢰할 수 있는 IP 주소와 네트워크 사이트를 모두 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-197">If dynamic enablement of emergency calling or dynamic configuration of security desk notification is required, then you must configure both Trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="4e7c3-198">동적 위치만 필요한 경우 신뢰할 수 있는 IP 주소만 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-198">If only dynamic locations are required, you must configure only trusted IP addresses.</span></span>

- <span data-ttu-id="4e7c3-199">둘 다 필요하지 않은 경우 네트워크 설정을 구성할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-199">If neither are required, configuring network settings isn't required.</span></span>


## <a name="configure-location-information-service"></a><span data-ttu-id="4e7c3-200">위치 정보 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="4e7c3-200">Configure Location Information Service</span></span>

<span data-ttu-id="4e7c3-201">Teams 클라이언트는 다른 네트워크 식별자와 연결된 위치에서 긴급 주소를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-201">A Teams client obtains emergency addresses from the locations associated with different network identifiers.</span></span> <span data-ttu-id="4e7c3-202">서브넷 및 무선 액세스 지점(WAP)이 모두 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-202">Both subnets and wireless access points (WAPs) are supported.</span></span> <span data-ttu-id="4e7c3-203">이더넷 스위치/포트는 현재 Windows 8.1 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-203">Ethernet switch/port is supported on Windows 8.1 and later at this time.</span></span>

<span data-ttu-id="4e7c3-204">클라이언트가 위치를 얻게 하려면 LIS를 네트워크 식별자(서브넷, WAP, 스위치, 포트) 및 긴급 위치로 채워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-204">For a client to obtain a location, you must populate the LIS with network identifiers (subnets, WAPs, switches, ports) and emergency locations.</span></span> <span data-ttu-id="4e7c3-205">관리 센터에서 또는 PowerShell을 사용하여 Microsoft Teams 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-205">You can do this in the Microsoft Teams admin center or by using PowerShell.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="4e7c3-206">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="4e7c3-206">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="4e7c3-207">왼쪽 탐색에서 위치 네트워크 &  >  **로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="4e7c3-207">In the left navigation, go to **Locations** > **Networks & locations**.</span></span>
2. <span data-ttu-id="4e7c3-208">추가할 네트워크 식별자를 나타내는 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-208">Click the tab that represents the network identifier that you want to add.</span></span> <span data-ttu-id="4e7c3-209">예를 들어 **서브넷,** **Wi-Fi 액세스 포인트,** **스위치** 또는 **포트를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4e7c3-209">For example, click **Subnets**, **Wi-Fi access points**, **Switches**, or **Ports**.</span></span> <span data-ttu-id="4e7c3-210">그런 다음 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4e7c3-210">Then click **Add**.</span></span>
3. <span data-ttu-id="4e7c3-211">필드를 완료하고 긴급 위치를 추가한 다음 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4e7c3-211">Complete the fields, add an emergency location, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="4e7c3-212">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="4e7c3-212">Using PowerShell</span></span>

<span data-ttu-id="4e7c3-213">다음 cmdlet을 사용하여 LIS에 포트, 스위치, 서브넷 및 WAP를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-213">Use the following cmdlets to add ports, switches, subnets, and WAPs to the LIS.</span></span>

- <span data-ttu-id="4e7c3-214">[Get](/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelissubnet?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet</span><span class="sxs-lookup"><span data-stu-id="4e7c3-214">[Get](/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelissubnet?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet</span></span>
- <span data-ttu-id="4e7c3-215">[Get](/powershell/module/skype/get-csonlinelisport?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelisport?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort</span><span class="sxs-lookup"><span data-stu-id="4e7c3-215">[Get](/powershell/module/skype/get-csonlinelisport?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelisport?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort</span></span>
- <span data-ttu-id="4e7c3-216">[Get](/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [Set](/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint</span><span class="sxs-lookup"><span data-stu-id="4e7c3-216">[Get](/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [Set](/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint</span></span>
- <span data-ttu-id="4e7c3-217">[Get](/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelisswitch?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch</span><span class="sxs-lookup"><span data-stu-id="4e7c3-217">[Get](/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelisswitch?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch</span></span>

>[!Important]
><span data-ttu-id="4e7c3-218">서브넷을 네트워크 사이트의 일부로 사용하는 경우 동적 위치를 렌더링하려면 위치 정보 서비스에서 다시 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-218">If subnets are being used as part of network sites, they must be redefined in the Location Information Service to render dynamic locations.</span></span>

## <a name="configure-emergency-policies"></a><span data-ttu-id="4e7c3-219">긴급 정책 구성</span><span class="sxs-lookup"><span data-stu-id="4e7c3-219">Configure emergency policies</span></span>

<span data-ttu-id="4e7c3-220">다음 정책을 사용하여 긴급 호출을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-220">Use the following policies to configure emergency calling.</span></span> <span data-ttu-id="4e7c3-221">관리 센터에서 또는 PowerShell을 사용하여 Microsoft Teams 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-221">You can manage these policies in the Microsoft Teams admin center or by using PowerShell.</span></span>

- <span data-ttu-id="4e7c3-222">**긴급 통화 라우팅** 정책 - 직접 라우팅에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-222">**Emergency call routing policy** – Applies only to Direct Routing.</span></span> <span data-ttu-id="4e7c3-223">이 정책은 긴급 번호, 원하는 경우 숫자당 마스크 및 숫자당 PSTN 경로를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-223">This policy configures the emergency numbers, masks per number if desired, and the PSTN route per number.</span></span>  <span data-ttu-id="4e7c3-224">이 정책을 사용자, 네트워크 사이트 또는 둘 다에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-224">You can assign this policy to users, to network sites, or to both.</span></span> <span data-ttu-id="4e7c3-225">(Teams 전화 요금제 클라이언트는 해당 Microsoft 365 사용 위치에 따라 국가의 응급 Microsoft 365 Office 365 활성화됩니다.)  자세한 내용은 직접 라우팅에 대한 긴급 통화 라우팅 정책 [관리를 참조합니다.](manage-emergency-call-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="4e7c3-225">(Calling Plans Teams clients are automatically enabled for emergency calling with the emergency numbers from the country based upon their Microsoft 365 or Office 365 usage location.)  To  learn more, see [Manage emergency call routing policies for Direct Routing](manage-emergency-call-routing-policies.md).</span></span>

- <span data-ttu-id="4e7c3-226">**긴급 통화 정책** - 통화 계획 및 직접 라우팅에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-226">**Emergency calling policy** - Applies to Calling Plans and Direct Routing.</span></span> <span data-ttu-id="4e7c3-227">이 정책은 긴급 통화를 할 때 보안 데스크 알림 환경을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-227">This policy configures the security desk notification experience when an emergency call is made.</span></span> <span data-ttu-id="4e7c3-228">누구에게 알릴지와 알림을 어떻게 알릴지 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-228">You can set who to notify and how they are notified.</span></span> <span data-ttu-id="4e7c3-229">예를 들어 조직의 보안 데스크에 자동으로 알리고 긴급 통화 시 수신을 듣도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-229">For example, to automatically notify your organization's security desk and have them listen in on emergency calls.</span></span>  <span data-ttu-id="4e7c3-230">이 정책은 사용자 또는 네트워크 사이트 또는 둘 다에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-230">This policy can either be assigned to users or network sites or both.</span></span> <span data-ttu-id="4e7c3-231">자세한 내용은 에서 긴급 [통화 정책 관리를 Teams.](manage-emergency-calling-policies.md)</span><span class="sxs-lookup"><span data-stu-id="4e7c3-231">To learn more, see [Manage emergency calling policies in Teams](manage-emergency-calling-policies.md).</span></span>

## <a name="enable-users-and-sites"></a><span data-ttu-id="4e7c3-232">사용자 및 사이트 사용</span><span class="sxs-lookup"><span data-stu-id="4e7c3-232">Enable users and sites</span></span>

<span data-ttu-id="4e7c3-233">사용자 및 사이트에 긴급 통화 라우팅 정책 및 긴급 호출 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-233">You can assign emergency call routing policies and emergency calling policies to users and to sites.</span></span> <span data-ttu-id="4e7c3-234">긴급 통화 라우팅 정책은 Direct 라우팅에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-234">Keep in mind that emergency call routing policies apply to Direct Routing only.</span></span> <span data-ttu-id="4e7c3-235">(호출 계획 사용자에게 이 정책을 할당할 수 있습니다. 정책은 영향을주지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="4e7c3-235">(Although it's possible to assign this policy to a Calling Plan user, the policy will have no effect.)</span></span>

<span data-ttu-id="4e7c3-236">관리 센터에서 또는 PowerShell을 Microsoft Teams 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-236">You assign policies in the Microsoft Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="4e7c3-237">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-237">To learn more, see:</span></span>

- [<span data-ttu-id="4e7c3-238">직접 라우팅에 대한 긴급 통화 라우팅 정책 관리</span><span class="sxs-lookup"><span data-stu-id="4e7c3-238">Manage emergency call routing policies for Direct Routing</span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="4e7c3-239">긴급 통화 정책 관리 Teams</span><span class="sxs-lookup"><span data-stu-id="4e7c3-239">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)

<span data-ttu-id="4e7c3-240">다음은 PowerShell 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-240">Here's some PowerShell examples.</span></span>

<span data-ttu-id="4e7c3-241">보안 데스크 알림을 위해 특정 사용자를 사용하도록 설정하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-241">To enable a specific user for security desk notification, use the following command:</span></span>

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

<span data-ttu-id="4e7c3-242">사이트 1에 "Contoso 긴급 통화 정책 1"이라는 정책을 할당하기 위해 다음 명령을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-242">To assign a policy called "Contoso Emergency Calling Policy 1" to Site 1, use the following command:</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

<span data-ttu-id="4e7c3-243">긴급 통화에 대해 특정 Direct 라우팅 사용자를 사용하도록 설정하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-243">To enable a specific Direct Routing user for emergency calling, use the following command:</span></span>

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

<span data-ttu-id="4e7c3-244">Site 1에 "Contoso 뉴욕 긴급 통화 라우팅"이라는 정책을 할당하기 위해 다음 명령을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-244">To assign a policy called "Contoso New York Emergency Call Routing" to Site 1, use the following command:</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

<span data-ttu-id="4e7c3-245">네트워크 사이트 및 사용자에게 긴급 호출 정책을 할당하고 해당 사용자가 해당 네트워크 사이트에 있는 경우 네트워크 사이트에 할당된 정책이 사용자에게 할당된 정책을 재지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-245">If you assigned an emergency calling policy to a network site and to a user, and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="test-emergency-calling"></a><span data-ttu-id="4e7c3-246">긴급 호출 테스트</span><span class="sxs-lookup"><span data-stu-id="4e7c3-246">Test emergency calling</span></span>

<span data-ttu-id="4e7c3-247">미국의 ERSP(긴급 라우팅 서비스 공급자)는 긴급 호출 테스트 봇을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-247">Some Emergency Routing Service Providers (ERSPs) in the United States offer an emergency calling test bot.</span></span>

- <span data-ttu-id="4e7c3-248">**미국의 계획** 사용자를 호출하면 미리 정의된 테스트 긴급 번호 933을 사용하여 긴급 호출 구성의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-248">**Calling Plan users in the United States** can use the predefined test emergency number 933 to validate their emergency calling configuration.</span></span> <span data-ttu-id="4e7c3-249">이 번호는 봇으로 라우팅됩니다. 그러면 발신자 전화 번호(전화선 ID), 긴급 주소 또는 위치, 호출이 PSAP로 자동으로 라우팅되거나 먼저 화면이 선택될지 여부를 에코합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-249">This number is routed to a bot, which then echoes back the caller phone number (calling line ID), emergency address or location, and whether the call would be automatically routed to the PSAP or screened first.</span></span>

- <span data-ttu-id="4e7c3-250">**미국의 직접** 라우팅 고객은 테스트 서비스를 위해 ERSP와 조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-250">**Direct Routing customers in the United States** should coordinate with their ERSP for a test service.</span></span>

## <a name="government-support"></a><span data-ttu-id="4e7c3-251">정부 지원</span><span class="sxs-lookup"><span data-stu-id="4e7c3-251">Government support</span></span>

<span data-ttu-id="4e7c3-252">다음 표에서는 정부 클라우드에서 동적 긴급 호출에 대한 지원을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="4e7c3-252">The following table shows support for dynamic emergency calling in the government clouds:</span></span>

| <span data-ttu-id="4e7c3-253">클라우드</span><span class="sxs-lookup"><span data-stu-id="4e7c3-253">Cloud</span></span> | <span data-ttu-id="4e7c3-254">가용성</span><span class="sxs-lookup"><span data-stu-id="4e7c3-254">Availability</span></span> |
| :------------|:-------|
| <span data-ttu-id="4e7c3-255">World Wide Multi 테넌트</span><span class="sxs-lookup"><span data-stu-id="4e7c3-255">World Wide Multi Tenant</span></span> | <span data-ttu-id="4e7c3-256">모든 클라이언트에서 Teams 사용 가능</span><span class="sxs-lookup"><span data-stu-id="4e7c3-256">Available on all Teams clients</span></span> |
| <span data-ttu-id="4e7c3-257">GCC</span><span class="sxs-lookup"><span data-stu-id="4e7c3-257">GCC</span></span> | <span data-ttu-id="4e7c3-258">모든 클라이언트에서 Teams 사용 가능</span><span class="sxs-lookup"><span data-stu-id="4e7c3-258">Available on all Teams clients</span></span> |
| <span data-ttu-id="4e7c3-259">GCCH</span><span class="sxs-lookup"><span data-stu-id="4e7c3-259">GCCH</span></span> | <span data-ttu-id="4e7c3-260">데스크톱에서 Teams 사용 가능</span><span class="sxs-lookup"><span data-stu-id="4e7c3-260">Available on Teams desktop</span></span> |
| <span data-ttu-id="4e7c3-261">DoD</span><span class="sxs-lookup"><span data-stu-id="4e7c3-261">DoD</span></span> | <span data-ttu-id="4e7c3-262">보류 중</span><span class="sxs-lookup"><span data-stu-id="4e7c3-262">Pending</span></span> |

 ## <a name="related-topics"></a><span data-ttu-id="4e7c3-263">관련 항목</span><span class="sxs-lookup"><span data-stu-id="4e7c3-263">Related topics</span></span>

- [<span data-ttu-id="4e7c3-264">긴급 통화 관리</span><span class="sxs-lookup"><span data-stu-id="4e7c3-264">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="4e7c3-265">긴급 전화 정책 관리</span><span class="sxs-lookup"><span data-stu-id="4e7c3-265">Manage emergency calling policies</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="4e7c3-266">긴급 통화 라우팅 정책 관리 </span><span class="sxs-lookup"><span data-stu-id="4e7c3-266">Manage emergency call routing policies </span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="4e7c3-267">조직의 응급 위치 추가, 변경 또는 제거</span><span class="sxs-lookup"><span data-stu-id="4e7c3-267">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="4e7c3-268">사용자에 대한 긴급 위치 할당 또는 변경</span><span class="sxs-lookup"><span data-stu-id="4e7c3-268">Assign or change an emergency location for your user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="4e7c3-269">클라우드 음성 기능에 대한 네트워크 설정</span><span class="sxs-lookup"><span data-stu-id="4e7c3-269">Network settings for cloud voice features</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="4e7c3-270">클라우드 음성 기능에 대한 네트워크 토폴로지 관리</span><span class="sxs-lookup"><span data-stu-id="4e7c3-270">Manage your network topology for cloud voice features</span></span>](manage-your-network-topology.md)
