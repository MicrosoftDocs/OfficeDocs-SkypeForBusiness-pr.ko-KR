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
description: Microsoft 통화 요금제 및 전화 시스템 직접 라우팅 동적 긴급 통화 기능을 구성하는 방법을 배워야 합니다.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 06153eccd343ef8731af38ff4e3b45cea334fcb2
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031014"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a><span data-ttu-id="f0ea4-103">동적인 긴급 전화 계획 및 구성</span><span class="sxs-lookup"><span data-stu-id="f0ea4-103">Plan and configure dynamic emergency calling</span></span> 

<span data-ttu-id="f0ea4-104">Microsoft 통화 요금제 및 전화 시스템 직접 라우팅에 대한 동적 긴급 통화는 Teams 클라이언트의 현재 위치를 기반으로 긴급 통화를 구성 및 라우팅하고 보안 담당자에게 알리는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-104">Dynamic emergency calling for Microsoft Calling Plans and Phone System Direct Routing provides the capability to configure and route emergency calls and notify security personnel based on the current location of the Teams client.</span></span>  

<span data-ttu-id="f0ea4-105">테넌트 관리자가 정의한 네트워크 토폴로지에 따라 Teams 클라이언트는 LIS(위치 정보 서비스)에 대한 요청에 네트워크 연결 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-105">Based on the network topology that the tenant administrator defines, the Teams client provides network connectivity information in a request to the Location Information Service (LIS).</span></span> <span data-ttu-id="f0ea4-106">일치가 있는 경우 LIS는 클라이언트에 위치를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-106">If there's a match, the LIS returns a location to the client.</span></span> <span data-ttu-id="f0ea4-107">이 위치 데이터는 클라이언트로 다시 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-107">This location data is transmitted back to the client.</span></span>  

<span data-ttu-id="f0ea4-108">Teams 클라이언트는 긴급 통화의 일부로 위치 데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-108">The Teams client includes location data as part of an emergency call.</span></span> <span data-ttu-id="f0ea4-109">그런 다음, 이 데이터는 응급 서비스 공급자가 적절한 PSAP(Public Safety Answering Point)를 결정하고 해당 PSAP로 호출을 라우팅하는 데 사용됩니다. 그러면 PSAP 디스패치가 발신자 위치를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-109">This data is then used by the emergency service provider to determine the appropriate Public Safety Answering Point (PSAP) and to route the call to that PSAP, which allows the PSAP dispatcher to obtain the caller's location.</span></span>  

<span data-ttu-id="f0ea4-110">동적 긴급 통화의 경우 다음이 발생해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-110">For dynamic emergency calling, the following must occur:</span></span>

1. <span data-ttu-id="f0ea4-111">네트워크 관리자는 네트워크 설정 및 LIS를 구성하여 네트워크/긴급 위치 맵을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-111">The network administrator configures network settings and the LIS to create a network/emergency location map.</span></span>

   <span data-ttu-id="f0ea4-112">직접 라우팅의 경우 긴급 통화 라우팅 및 파트너 연결에 대한 추가 구성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-112">For Direct Routing, additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span> <span data-ttu-id="f0ea4-113">관리자는 ERS(긴급 라우팅 **서비스)** 공급자(미국)에 대한 연결을 구성하거나 ELIN(긴급 위치 식별 번호) 애플리케이션에 대해 SBC(세션 테두리 컨트롤러)를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-113">The administrator must configure connection to an Emergency Routing Service (ERS) provider (United States) **OR** configure the Session Border Controller (SBC) for an Emergency Location Identification Number (ELIN) application.</span></span>

2. <span data-ttu-id="f0ea4-114">시작 중 및 주기적으로 또는 네트워크 연결이 변경될 때 Teams 클라이언트는 네트워크 연결 정보가 포함된 위치 요청을 네트워크 설정 및 LIS로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-114">During startup and periodically afterwards, or when a network connection is changed, the Teams client sends a location request that contains its network connectivity information to the network settings and the LIS.</span></span>

   - <span data-ttu-id="f0ea4-115">네트워크 설정 사이트 일치가 있는 경우 긴급 통화 정책은 해당 사이트에서 Teams 클라이언트로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-115">If there's a network settings site match – emergency calling policies are returned to the Teams client from that site.</span></span> <span data-ttu-id="f0ea4-116">정책에 대한 자세한 내용은 긴급 정책 [구성을 참조하세요.](#configure-emergency-policies)</span><span class="sxs-lookup"><span data-stu-id="f0ea4-116">(For more information about policies, see [Configure emergency policies](#configure-emergency-policies)).</span></span>

   - <span data-ttu-id="f0ea4-117">LIS 일치가 있는 경우 Teams 클라이언트가 연결된 네트워크 요소의 긴급 위치가 Teams 클라이언트로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-117">If there's an LIS match – an emergency location from the network element the Teams client is connected to is returned to the Teams client.</span></span> <span data-ttu-id="f0ea4-118">일치는 첫 번째 일치 결과가 반환되는 순서대로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-118">The match is performed in the following order with the first matched result being returned:</span></span>
       - <span data-ttu-id="f0ea4-119">WAP</span><span class="sxs-lookup"><span data-stu-id="f0ea4-119">WAP</span></span>
       - <span data-ttu-id="f0ea4-120">이더넷 스위치/포트</span><span class="sxs-lookup"><span data-stu-id="f0ea4-120">Ethernet switch/port</span></span>
       - <span data-ttu-id="f0ea4-121">이더넷 스위치</span><span class="sxs-lookup"><span data-stu-id="f0ea4-121">Ethernet switch</span></span>
       - <span data-ttu-id="f0ea4-122">서브넷</span><span class="sxs-lookup"><span data-stu-id="f0ea4-122">Subnet</span></span>

3. <span data-ttu-id="f0ea4-123">Teams 클라이언트가 긴급 전화를 걸면 긴급 위치가 PSTN 네트워크로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-123">When the Teams client makes an emergency call, the emergency location is conveyed to the PSTN network.</span></span>

   <span data-ttu-id="f0ea4-124">직접 라우팅의 경우 관리자는 ERS 공급자에게 긴급 전화를 보내거나 SBC ELIN 애플리케이션을 구성하도록 SBC를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-124">For Direct Routing, the administrator must configure the SBC to send emergency calls to the ERS provider or configure the SBC ELIN application.</span></span>

<span data-ttu-id="f0ea4-125">이 문서에는 다음 섹션이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-125">This article contains the following sections.</span></span>

- [<span data-ttu-id="f0ea4-126">긴급 주소 구성</span><span class="sxs-lookup"><span data-stu-id="f0ea4-126">Configure emergency addresses</span></span>](#assign-emergency-addresses)
- [<span data-ttu-id="f0ea4-127">네트워크 설정 구성</span><span class="sxs-lookup"><span data-stu-id="f0ea4-127">Configure network settings</span></span>](#configure-network-settings)
- [<span data-ttu-id="f0ea4-128">위치 정보 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="f0ea4-128">Configure Location Information Service</span></span>](#configure-location-information-service)
- [<span data-ttu-id="f0ea4-129">긴급 정책 구성</span><span class="sxs-lookup"><span data-stu-id="f0ea4-129">Configure emergency policies</span></span>](#configure-emergency-policies)
- [<span data-ttu-id="f0ea4-130">사용자 및 사이트 사용</span><span class="sxs-lookup"><span data-stu-id="f0ea4-130">Enable users and sites</span></span>](#enable-users-and-sites)
- [<span data-ttu-id="f0ea4-131">긴급 통화 테스트</span><span class="sxs-lookup"><span data-stu-id="f0ea4-131">Test emergency calling</span></span>](#test-emergency-calling)

<span data-ttu-id="f0ea4-132">적절한 PSAP(Public Safety Answering Point)로 자동 라우팅을 하는 능력은 Teams 사용자의 사용 국가에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-132">The ability to do automatic routing to the appropriate Public Safety Answering Point (PSAP) varies depending on the country of usage of the Teams user.</span></span>

<span data-ttu-id="f0ea4-133">긴급 주소 및 긴급 통화 라우팅에 대한 정보, 국가별 정보, 네트워크 설정 및 네트워크 토폴로지에 대한 정보를 비롯한 긴급 통화에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-133">For more information about emergency calling, including information about emergency addresses and emergency call routing, information specific to countries, and information about network settings and network topology, see the following:</span></span>

- [<span data-ttu-id="f0ea4-134">긴급 통화 관리</span><span class="sxs-lookup"><span data-stu-id="f0ea4-134">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="f0ea4-135">클라우드 음성 기능에 대한 네트워크 설정 관리</span><span class="sxs-lookup"><span data-stu-id="f0ea4-135">Manage network settings for cloud voice features</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="f0ea4-136">클라우드 음성 기능에 대한 네트워크 토폴로지 관리</span><span class="sxs-lookup"><span data-stu-id="f0ea4-136">Manage your network topology for cloud voice features</span></span>](manage-your-network-topology.md)

## <a name="supported-clients"></a><span data-ttu-id="f0ea4-137">지원되는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="f0ea4-137">Supported clients</span></span>

<span data-ttu-id="f0ea4-138">다음 클라이언트는 현재 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-138">The following clients are currently supported.</span></span>  <span data-ttu-id="f0ea4-139">자주 다시 확인하여 이 목록에 대한 업데이트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-139">Check back often to see updates to this list.</span></span>

- <span data-ttu-id="f0ea4-140">Microsoft Windows용 Teams 데스크톱 클라이언트</span><span class="sxs-lookup"><span data-stu-id="f0ea4-140">Teams desktop client for Microsoft Windows</span></span>
- <span data-ttu-id="f0ea4-141">Apple macOS용 Teams 데스크톱 클라이언트</span><span class="sxs-lookup"><span data-stu-id="f0ea4-141">Teams desktop client for Apple macOS</span></span>
- <span data-ttu-id="f0ea4-142">Apple iOS 클라이언트 버전 1.0.92.2019121004 및 App Store 버전 1.0.92 이상용 Teams 모바일 클라이언트</span><span class="sxs-lookup"><span data-stu-id="f0ea4-142">Teams mobile client for Apple iOS client version 1.0.92.2019121004 and App Store version 1.0.92 and greater</span></span>
- <span data-ttu-id="f0ea4-143">Android 클라이언트용 Teams 모바일 클라이언트 및 Google Play 스토어 버전 1416/1.0.0.2019121201 이상</span><span class="sxs-lookup"><span data-stu-id="f0ea4-143">Teams mobile client for Android client and Google Play store version 1416/1.0.0.2019121201 and greater</span></span>
- <span data-ttu-id="f0ea4-144">Teams 전화 버전 1449/1.0.94.2019110802 이상</span><span class="sxs-lookup"><span data-stu-id="f0ea4-144">Teams phone version 1449/1.0.94.2019110802 and greater</span></span>
- <span data-ttu-id="f0ea4-145">Teams 회의실 버전 4.4.25.0 이상</span><span class="sxs-lookup"><span data-stu-id="f0ea4-145">Teams Rooms version 4.4.25.0 and greater</span></span>

> [!NOTE]
> <span data-ttu-id="f0ea4-146">보안 데스크 알림을 포함한 동적 긴급 통화는 Teams 웹 클라이언트에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-146">Dynamic emergency calling including security desk notification isn't supported on the Teams web client.</span></span> <span data-ttu-id="f0ea4-147">사용자가 Teams 웹 클라이언트를 사용하여 PSTN 번호를 호출하지 못하도록 방지하기 위해 Teams 통화 정책을 설정하고 웹 **PSTN** 통화 허용 설정을 해제하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-147">To prevent users from using the Teams web client to call PSTN numbers, you can set a Teams calling policy and turn off the **Allow web PSTN calling** setting.</span></span> <span data-ttu-id="f0ea4-148">자세한 내용은 [Teams](teams-calling-policy.md) 및 [Set-CsTeamsCallingPolicy의](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)통화 정책을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-148">To learn more, see [Calling policies in Teams](teams-calling-policy.md) and [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span>

## <a name="assign-emergency-addresses"></a><span data-ttu-id="f0ea4-149">긴급 주소 할당</span><span class="sxs-lookup"><span data-stu-id="f0ea4-149">Assign emergency addresses</span></span>

<span data-ttu-id="f0ea4-150">통화 계획 사용자와 위치를 동적으로 얻는 데 필요한 네트워크 식별자 둘 다에 긴급 주소를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-150">You can assign emergency addresses to both Calling Plan users and to the network identifiers that are required for dynamically obtaining a location.</span></span> <span data-ttu-id="f0ea4-151">(서브넷 및 WiFi AP가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-151">(Subnet and WiFi AP are supported.</span></span> <span data-ttu-id="f0ea4-152">이더넷 스위치/포트는 현재 Windows 8.1 이상에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-152">Ethernet switch/port is supported on Windows 8.1 and later at this time).</span></span>

<span data-ttu-id="f0ea4-153">미국 내에서 긴급 통화의 자동 라우팅을 지원하려면 네트워크 식별자에 할당된 긴급 위치에 연결된 지역 코드가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-153">To support automated routing of emergency calls within the United States, you must ensure that the emergency locations that are assigned to network identifiers include the associated geo codes.</span></span> <span data-ttu-id="f0ea4-154">(지역 코드가 없는 긴급 주소는 동적 위치에 필요한 네트워크 식별자에 할당할 수 없습니다.)</span><span class="sxs-lookup"><span data-stu-id="f0ea4-154">(Emergency addresses without geo codes can't be assigned to the network identifiers that are required for dynamic locations.)</span></span>

<span data-ttu-id="f0ea4-155">Azure Maps는 위치 기반 서비스에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-155">Azure Maps is used for location-based services.</span></span>  <span data-ttu-id="f0ea4-156">Microsoft Teams 관리 센터를 사용하여 긴급 주소를 입력하면 Teams에서 Azure Maps에서 해당 주소를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-156">When you enter an emergency address by using the Microsoft Teams admin center, Teams checks Azure Maps for the address:</span></span>

- <span data-ttu-id="f0ea4-157">일치가 발견되는 경우 지역 코드가 자동으로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-157">If a match is found, the geo codes are automatically included.</span></span>

- <span data-ttu-id="f0ea4-158">매치가 없는 경우 긴급 주소를 수동으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-158">If a match isn't found, you will have the opportunity to manually create an emergency address.</span></span> <span data-ttu-id="f0ea4-159">PIN 삭제 기능을 사용하여 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-159">You can use the PIN drop feature to do this.</span></span> 

<span data-ttu-id="f0ea4-160">즉, 통화 계획 사용자에게 할당하기 위해 만들어진 기존 긴급 위치가 동적 위치를 위한 경우 지역 코드를 포함하도록 동일한 주소를 다시 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-160">This means that if an existing emergency location that is created for assigning to Calling Plan users is intended for a dynamic location, the same address needs to be re-created to include the geo codes.</span></span> <span data-ttu-id="f0ea4-161">두 위치를 구분하기 위해 다른 설명을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-161">To distinguish between the two locations, you should include a different description.</span></span> <span data-ttu-id="f0ea4-162">새 긴급 위치를 이전 위치가 있는 사용자에게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-162">The new emergency location can be assigned to the users who have the old location.</span></span> <span data-ttu-id="f0ea4-163">완전히 마이그레이션되면 이전 위치를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-163">When fully migrated, the old location can be deleted.</span></span>

<span data-ttu-id="f0ea4-164">Microsoft Teams 관리 센터에서 또는 PowerShell을 사용하여 긴급 주소를 추가하고 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-164">You add and assign emergency addresses in the Microsoft Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="f0ea4-165">자세한 내용은 [조직의](add-change-remove-emergency-location-organization.md) 긴급 위치 추가 및 사용자에 대한 긴급 위치 [할당을 참조하세요.](assign-change-emergency-location-user.md)</span><span class="sxs-lookup"><span data-stu-id="f0ea4-165">For more information, see [Add an emergency location for your organization](add-change-remove-emergency-location-organization.md) and [Assign an emergency location for a user](assign-change-emergency-location-user.md).</span></span>

## <a name="configure-network-settings"></a><span data-ttu-id="f0ea4-166">네트워크 설정 구성</span><span class="sxs-lookup"><span data-stu-id="f0ea4-166">Configure network settings</span></span>

<span data-ttu-id="f0ea4-167">네트워크 설정은 Teams 클라이언트의 위치를 결정하고 긴급 통화 정책 및 긴급 위치를 동적으로 얻는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-167">Network settings are used to determine the location of a Teams client, and to dynamically obtain emergency calling policies and an emergency location.</span></span> <span data-ttu-id="f0ea4-168">조직에서 긴급 통화 기능을 원하는 방식에 따라 네트워크 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-168">You can configure network settings according to how your organization wants emergency calling to function.</span></span>

<span data-ttu-id="f0ea4-169">네트워크 설정에는 서브넷 컬렉션을 포함하며 이러한 사이트는 사용자에게 동적 정책 할당에 독점적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-169">Network settings include sites that include a collection of subnets and these are used exclusively for dynamic policy assignment to users.</span></span> <span data-ttu-id="f0ea4-170">예를 들어 긴급 통화 정책 및 긴급 통화 라우팅 정책이 "Redmond 사이트"에 할당되어 집 또는 다른 Microsoft 위치에서 로밍하는 모든 사용자가 Redmond와 관련한 긴급 번호, 라우팅 및 보안 데스크로 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-170">For example, an emergency calling policy and an emergency call routing policy might be assigned to the "Redmond site" so that any user that roams from home or another Microsoft location is configured with emergency numbers, routing, and security desk specific to Redmond.</span></span>  

>[!Note]
><span data-ttu-id="f0ea4-171">또한 서브넷은 LIS에서 정의할 수 있으며 긴급 위치에 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-171">Subnets can also be defined in LIS and can be associated with an emergency location.</span></span>  

<span data-ttu-id="f0ea4-172">다음 정의를 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-172">Keep the following definitions in mind.</span></span> <span data-ttu-id="f0ea4-173">자세한 내용은 클라우드 음성 기능에 [대한 네트워크 설정을 참조하세요.](cloud-voice-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f0ea4-173">For more information, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

- <span data-ttu-id="f0ea4-174">신뢰할 수 있는 IP 주소는 엔터프라이즈 네트워크의 인터넷 외부 IP 주소 컬렉션을 포함하며 사용자의 엔드포인트가 회사 네트워크 내부에 있는지 확인하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-174">Trusted IP addresses contain a collection of the internet external IP addresses of the enterprise network and are used to determine if the user's endpoint is inside the corporate network.</span></span> <span data-ttu-id="f0ea4-175">사용자의 외부 IP 주소가 신뢰할 수 있는 IP 주소의 IP 주소와 일치하는 경우 동적 정책 또는 위치를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-175">An attempt to obtain a dynamic policy or location will only be made if the user's external IP address matches an IP address in the trusted IP address.</span></span> <span data-ttu-id="f0ea4-176">IPv4 또는 IPv6 IP 주소에 대해 일치할 수 있으며 네트워크 설정으로 전송되는 IP 패킷의 형식에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-176">A match can be made against either IPv4 or IPv6 IP addresses and is dependent upon the format of the IP packet sent to the network settings.</span></span>  <span data-ttu-id="f0ea4-177">(공용 IP 주소에 IPv4 및 IPv6이 모두 있는 경우 둘 다 신뢰할 수 있는 IP 주소로 추가해야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="f0ea4-177">(If a public IP address has both IPv4 and IPv6, you need to add both as trusted IP addresses.)</span></span>

- <span data-ttu-id="f0ea4-178">네트워크 지역에는 네트워크 사이트 모음이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-178">A network region contains a collection of network sites.</span></span> 

- <span data-ttu-id="f0ea4-179">네트워크 사이트는 조직에 사무실, 건물 집합 또는 캠퍼스와 같은 물리적 값이 있는 위치를 나타 내는 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-179">A network site represents a location where your organization has a physical value, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="f0ea4-180">이러한 사이트는 IP 서브넷의 컬렉션으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-180">These sites are defined as a collection of IP subnets.</span></span>

- <span data-ttu-id="f0ea4-181">네트워크 서브넷은 특정 네트워크 사이트와 연결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-181">A network subnet must be associated with a specific network site.</span></span> <span data-ttu-id="f0ea4-182">클라이언트의 위치는 네트워크 서브넷 및 연결된 네트워크 사이트에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-182">A client's location is determined based on the network subnet and the associated network site.</span></span>  

<span data-ttu-id="f0ea4-183">Microsoft Teams 관리 센터에서 또는 PowerShell을 사용하여 네트워크 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-183">You configure network settings in the Microsoft Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="f0ea4-184">자세한 내용은 클라우드 음성 기능에 대한 네트워크 [토폴로지 관리를 참조합니다.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="f0ea4-184">To learn more, see [Manage your network topology for cloud voice features](manage-your-network-topology.md).</span></span>

<span data-ttu-id="f0ea4-185">네트워크 설정(예: 새 주소, 네트워크 식별자 등)을 변경하여 Teams 클라이언트에 전파하고 사용할 수 있는 데 다소 시간이 걸릴 수 있습니다(최대 몇 시간).</span><span class="sxs-lookup"><span data-stu-id="f0ea4-185">Note that it can take some time (up to a couple of hours) for some changes to network settings (such as a new address, network identifier, and so on) to propagate and be available to Teams clients.</span></span>  

<span data-ttu-id="f0ea4-186">**통화 요금제 사용자의 경우:**</span><span class="sxs-lookup"><span data-stu-id="f0ea4-186">**For Calling Plan users:**</span></span>

- <span data-ttu-id="f0ea4-187">보안 데스크 알림의 동적 구성이 필요한 경우 신뢰할 수 있는 IP 주소와 네트워크 사이트를 모두 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-187">If dynamic configuration of security desk notification is required, you must configure both trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="f0ea4-188">동적 위치만 필요한 경우 신뢰할 수 있는 IP 주소만 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-188">If only dynamic locations are required, you must configure only trusted IP addresses.</span></span>

- <span data-ttu-id="f0ea4-189">둘 다 필요하지 않은 경우 네트워크 설정을 구성할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-189">If neither are required, configuring network settings isn't required.</span></span> 

<span data-ttu-id="f0ea4-190">**직접 라우팅 사용자의 경우:**</span><span class="sxs-lookup"><span data-stu-id="f0ea4-190">**For Direct Routing users:**</span></span>

- <span data-ttu-id="f0ea4-191">긴급 통화 또는 보안 데스크 알림의 동적 구성이 필요한 경우 신뢰할 수 있는 IP 주소와 네트워크 사이트를 모두 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-191">If dynamic enablement of emergency calling or dynamic configuration of security desk notification is required, then you must configure both Trusted IP addresses and network sites.</span></span>

- <span data-ttu-id="f0ea4-192">동적 위치만 필요한 경우 신뢰할 수 있는 IP 주소만 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-192">If only dynamic locations are required, you must configure only trusted IP addresses.</span></span>

- <span data-ttu-id="f0ea4-193">둘 다 필요하지 않은 경우 네트워크 설정을 구성할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-193">If neither are required, configuring network settings isn't required.</span></span>


## <a name="configure-location-information-service"></a><span data-ttu-id="f0ea4-194">위치 정보 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="f0ea4-194">Configure Location Information Service</span></span>

<span data-ttu-id="f0ea4-195">Teams 클라이언트는 다른 네트워크 식별자와 연결된 위치에서 긴급 주소를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-195">A Teams client obtains emergency addresses from the locations associated with different network identifiers.</span></span> <span data-ttu-id="f0ea4-196">서브넷과 WAP(무선 액세스 지점)가 모두 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-196">Both subnets and wireless access points (WAPs) are supported.</span></span> <span data-ttu-id="f0ea4-197">이더넷 스위치/포트는 현재 Windows 8.1 이상에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-197">Ethernet switch/port is supported on Windows 8.1 and later at this time.</span></span>

<span data-ttu-id="f0ea4-198">클라이언트가 위치를 얻게 하려면 LIS를 네트워크 식별자(서브넷, WAP, 스위치, 포트) 및 긴급 위치로 채워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-198">For a client to obtain a location, you must populate the LIS with network identifiers (subnets, WAPs, switches, ports) and emergency locations.</span></span> <span data-ttu-id="f0ea4-199">Microsoft Teams 관리 센터에서 또는 PowerShell을 사용하여 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-199">You can do this in the Microsoft Teams admin center or by using PowerShell.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="f0ea4-200">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="f0ea4-200">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="f0ea4-201">왼쪽 탐색에서 **위치** 네트워크 위치로  >  **&.**</span><span class="sxs-lookup"><span data-stu-id="f0ea4-201">In the left navigation, go to **Locations** > **Networks & locations**.</span></span>
2. <span data-ttu-id="f0ea4-202">추가할 네트워크 식별자를 나타내는 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-202">Click the tab that represents the network identifier that you want to add.</span></span> <span data-ttu-id="f0ea4-203">예를 들어 **서브넷,** **Wi-Fi 액세스 지점,** **스위치** 또는 **포트를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f0ea4-203">For example, click **Subnets**, **Wi-Fi access points**, **Switches**, or **Ports**.</span></span> <span data-ttu-id="f0ea4-204">그런 다음 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f0ea4-204">Then click **Add**.</span></span>
3. <span data-ttu-id="f0ea4-205">필드를 완료하고 긴급 위치를 추가한 다음 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f0ea4-205">Complete the fields, add an emergency location, and then click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="f0ea4-206">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="f0ea4-206">Using PowerShell</span></span>

<span data-ttu-id="f0ea4-207">다음 cmdlet을 사용하여 LIS에 포트, 스위치, 서브넷 및 WAP를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-207">Use the following cmdlets to add ports, switches, subnets, and WAPs to the LIS.</span></span>

- <span data-ttu-id="f0ea4-208">[Get,](https://docs.microsoft.com/powershell/module/skype/get-csonlinelissubnet?view=skype-ps) [Set,](https://docs.microsoft.com/powershell/module/skype/set-csonlinelissubnet?view=skype-ps) [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet</span><span class="sxs-lookup"><span data-stu-id="f0ea4-208">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelissubnet?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet</span></span>
- <span data-ttu-id="f0ea4-209">[Get,](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisport?view=skype-ps) [Set,](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisport?view=skype-ps) [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort</span><span class="sxs-lookup"><span data-stu-id="f0ea4-209">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisport?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisport?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort</span></span>
- <span data-ttu-id="f0ea4-210">[Get,](https://docs.microsoft.com/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps) [Set,](https://docs.microsoft.com/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps) [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint</span><span class="sxs-lookup"><span data-stu-id="f0ea4-210">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint</span></span>
- <span data-ttu-id="f0ea4-211">[Get,](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisswitch?view=skype-ps) [Set,](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisswitch?view=skype-ps) [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch</span><span class="sxs-lookup"><span data-stu-id="f0ea4-211">[Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisswitch?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch</span></span>

>[!Important]
><span data-ttu-id="f0ea4-212">서브넷을 네트워크 사이트의 일부로 사용하는 경우 동적 위치를 렌더링하려면 위치 정보 서비스에서 다시 정의되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-212">If subnets are being used as part of network sites, they must be redefined in the Location Information Service to render dynamic locations.</span></span>

## <a name="configure-emergency-policies"></a><span data-ttu-id="f0ea4-213">긴급 정책 구성</span><span class="sxs-lookup"><span data-stu-id="f0ea4-213">Configure emergency policies</span></span>

<span data-ttu-id="f0ea4-214">다음 정책을 사용하여 긴급 통화를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-214">Use the following policies to configure emergency calling.</span></span> <span data-ttu-id="f0ea4-215">Microsoft Teams 관리 센터에서 또는 PowerShell을 사용하여 이러한 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-215">You can manage these policies in the Microsoft Teams admin center or by using PowerShell.</span></span>

- <span data-ttu-id="f0ea4-216">**긴급 통화 라우팅 정책** – 직접 라우팅에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-216">**Emergency call routing policy** – Applies only to Direct Routing.</span></span> <span data-ttu-id="f0ea4-217">이 정책은 긴급 번호, 원하는 경우 숫자당 마스크 및 번호당 PSTN 경로를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-217">This policy configures the emergency numbers, masks per number if desired, and the PSTN route per number.</span></span>  <span data-ttu-id="f0ea4-218">이 정책을 사용자, 네트워크 사이트 또는 둘 다에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-218">You can assign this policy to users, to network sites, or to both.</span></span> <span data-ttu-id="f0ea4-219">(요금제 Teams 클라이언트 호출은 해당 Microsoft 365 또는 Office 365 사용 위치에 따라 국가의 긴급 번호로 긴급 통화를 할 수 있도록 자동으로 설정됩니다.)  자세한 내용은 직접 라우팅에 대한 긴급 통화 라우팅 정책 관리를 [참조합니다.](manage-emergency-call-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="f0ea4-219">(Calling Plans Teams clients are automatically enabled for emergency calling with the emergency numbers from the country based upon their Microsoft 365 or Office 365 usage location.)  To  learn more, see [Manage emergency call routing policies for Direct Routing](manage-emergency-call-routing-policies.md).</span></span>

- <span data-ttu-id="f0ea4-220">**긴급 통화 정책** - 통화 요금제 및 직접 라우팅에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-220">**Emergency calling policy** - Applies to Calling Plans and Direct Routing.</span></span> <span data-ttu-id="f0ea4-221">이 정책은 응급 전화를 걸 때 보안 데스크 알림 환경을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-221">This policy configures the security desk notification experience when an emergency call is made.</span></span> <span data-ttu-id="f0ea4-222">알림을 할 사용자 및 알림을 어떻게 알릴지 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-222">You can set who to notify and how they are notified.</span></span> <span data-ttu-id="f0ea4-223">예를 들어 조직의 보안 센터에 자동으로 알리고 긴급 통화를 듣도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-223">For example, to automatically notify your organization's security desk and have them listen in on emergency calls.</span></span>  <span data-ttu-id="f0ea4-224">이 정책은 사용자 또는 네트워크 사이트 또는 둘 다에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-224">This policy can either be assigned to users or network sites or both.</span></span> <span data-ttu-id="f0ea4-225">자세한 내용은 Teams에서 긴급 통화 정책 [관리를 참조합니다.](manage-emergency-calling-policies.md)</span><span class="sxs-lookup"><span data-stu-id="f0ea4-225">To learn more, see [Manage emergency calling policies in Teams](manage-emergency-calling-policies.md).</span></span>

## <a name="enable-users-and-sites"></a><span data-ttu-id="f0ea4-226">사용자 및 사이트 사용</span><span class="sxs-lookup"><span data-stu-id="f0ea4-226">Enable users and sites</span></span>

<span data-ttu-id="f0ea4-227">사용자 및 사이트에 긴급 통화 라우팅 정책 및 긴급 통화 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-227">You can assign emergency call routing policies and emergency calling policies to users and to sites.</span></span> <span data-ttu-id="f0ea4-228">긴급 통화 라우팅 정책은 직접 라우팅에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-228">Keep in mind that emergency call routing policies apply to Direct Routing only.</span></span> <span data-ttu-id="f0ea4-229">(호출 계획 사용자에게 이 정책을 할당할 수 있는 경우 정책은 영향을 주지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="f0ea4-229">(Although it's possible to assign this policy to a Calling Plan user, the policy will have no effect.)</span></span>

<span data-ttu-id="f0ea4-230">Microsoft Teams 관리 센터에서 또는 PowerShell을 사용하여 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-230">You assign policies in the Microsoft Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="f0ea4-231">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-231">To learn more, see:</span></span>

- [<span data-ttu-id="f0ea4-232">직접 라우팅에 대한 긴급 통화 라우팅 정책 관리</span><span class="sxs-lookup"><span data-stu-id="f0ea4-232">Manage emergency call routing policies for Direct Routing</span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="f0ea4-233">Teams에서 긴급 통화 정책 관리</span><span class="sxs-lookup"><span data-stu-id="f0ea4-233">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)

<span data-ttu-id="f0ea4-234">다음은 몇 가지 PowerShell 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-234">Here's some PowerShell examples.</span></span>

<span data-ttu-id="f0ea4-235">보안 데스크 알림에 특정 사용자를 사용하도록 설정하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-235">To enable a specific user for security desk notification, use the following command:</span></span>

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

<span data-ttu-id="f0ea4-236">사이트 1에 "Contoso 긴급 통화 정책 1"이라는 정책을 할당하기 위해 다음 명령을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-236">To assign a policy called "Contoso Emergency Calling Policy 1" to Site 1, use the following command:</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

<span data-ttu-id="f0ea4-237">긴급 통화에 특정 직접 라우팅 사용자를 사용하도록 설정하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-237">To enable a specific Direct Routing user for emergency calling, use the following command:</span></span>

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

<span data-ttu-id="f0ea4-238">사이트 1에 "Contoso 뉴욕 긴급 통화 라우팅"이라는 정책을 할당하기 위해 다음 명령을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-238">To assign a policy called "Contoso New York Emergency Call Routing" to Site 1, use the following command:</span></span>

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

<span data-ttu-id="f0ea4-239">네트워크 사이트와 사용자에게 긴급 통화 정책을 할당한 경우 해당 사용자가 해당 네트워크 사이트에 있는 경우 네트워크 사이트에 할당된 정책이 사용자에게 할당된 정책을 다시 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-239">If you assigned an emergency calling policy to a network site and to a user, and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="test-emergency-calling"></a><span data-ttu-id="f0ea4-240">긴급 통화 테스트</span><span class="sxs-lookup"><span data-stu-id="f0ea4-240">Test emergency calling</span></span>

<span data-ttu-id="f0ea4-241">미국의 일부 긴급 라우팅 서비스 공급자(ERSP)는 긴급 통화 테스트 봇을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-241">Some Emergency Routing Service Providers (ERSPs) in the United States offer an emergency calling test bot.</span></span>

- <span data-ttu-id="f0ea4-242">**미국의 통화** 계획 사용자는 미리 정의한 테스트 긴급 번호 933을 사용하여 긴급 통화 구성의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-242">**Calling Plan users in the United States** can use the predefined test emergency number 933 to validate their emergency calling configuration.</span></span> <span data-ttu-id="f0ea4-243">이 번호는 봇으로 라우팅됩니다. 그러면 발신자 전화 번호(전화 번호), 긴급 주소 또는 위치, 통화가 PSAP로 자동으로 라우팅될지 또는 먼저 화면이 선택될지 여부를 다시 에코합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-243">This number is routed to a bot, which then echoes back the caller phone number (calling line ID), emergency address or location, and whether the call would be automatically routed to the PSAP or screened first.</span></span>

- <span data-ttu-id="f0ea4-244">**미국의 직접** 라우팅 고객은 테스트 서비스를 위해 ERSP와 조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ea4-244">**Direct Routing customers in the United States** should coordinate with their ERSP for a test service.</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="f0ea4-245">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f0ea4-245">Related topics</span></span>

- [<span data-ttu-id="f0ea4-246">긴급 통화 관리</span><span class="sxs-lookup"><span data-stu-id="f0ea4-246">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="f0ea4-247">긴급 전화 정책 관리</span><span class="sxs-lookup"><span data-stu-id="f0ea4-247">Manage emergency calling policies</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="f0ea4-248">긴급 통화 라우팅 정책 관리 </span><span class="sxs-lookup"><span data-stu-id="f0ea4-248">Manage emergency call routing policies </span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="f0ea4-249">조직의 응급 위치 추가, 변경 또는 제거</span><span class="sxs-lookup"><span data-stu-id="f0ea4-249">Add, change, or remove an emergency location for your organization</span></span>](add-change-remove-emergency-location-organization.md)
- [<span data-ttu-id="f0ea4-250">사용자의 긴급 위치 지정 또는 변경</span><span class="sxs-lookup"><span data-stu-id="f0ea4-250">Assign or change an emergency location for your user</span></span>](assign-change-emergency-location-user.md)
- [<span data-ttu-id="f0ea4-251">클라우드 음성 기능에 대한 네트워크 설정</span><span class="sxs-lookup"><span data-stu-id="f0ea4-251">Network settings for cloud voice features</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="f0ea4-252">클라우드 음성 기능에 대한 네트워크 토폴로지 관리</span><span class="sxs-lookup"><span data-stu-id="f0ea4-252">Manage your network topology for cloud voice features</span></span>](manage-your-network-topology.md)
