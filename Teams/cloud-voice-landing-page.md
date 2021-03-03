---
title: Microsoft Teams에서 음성 솔루션 계획
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/29/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: Microsoft Teams 클라우드 음성 기능 및 조직에 대해 내릴 배포 결정에 대해 자세히 설명합니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: fcd7ebfd4542c38bd56900c1e414dadec09bf246
ms.sourcegitcommit: 54140f6f8f2279a0eaf2e9c79699d6cff306791c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/03/2021
ms.locfileid: "50408194"
---
# <a name="plan-your-teams-voice-solution"></a><span data-ttu-id="3c5a1-103">Teams 음성 솔루션 계획</span><span class="sxs-lookup"><span data-stu-id="3c5a1-103">Plan your Teams voice solution</span></span> 

<span data-ttu-id="3c5a1-104">이 문서에서는 조직에 적합한 Microsoft 음성 솔루션을 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-104">This article helps you decide which Microsoft voice solution is right for your organization.</span></span> <span data-ttu-id="3c5a1-105">결정한 후 이 문서에서는 선택한 솔루션을 구현할 수 있도록 콘텐츠에 대한 로드맵을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-105">After you've decided, the article provides a roadmap to content that will enable you to implement your chosen solution.</span></span>

> [!NOTE]
> <span data-ttu-id="3c5a1-106">비즈니스용 Skype 서버의 Teams로 업그레이드하기 위한 전체 계획의 일부로 Teams 음성 솔루션을 계획하는 방법에 대한 지침은 비즈니스용 Skype에서 Teams로 업그레이드하기 위한 PSTN 고려 사항을 [참조하세요.](upgrade-to-teams-on-prem-pstn-considerations.md)</span><span class="sxs-lookup"><span data-stu-id="3c5a1-106">For guidance on planning a Teams voice solution as part as your overall plan to upgrade to Teams from Skype for Business Server, see [PSTN considerations for upgrading to Teams from Skype for Business on-premises](upgrade-to-teams-on-prem-pstn-considerations.md).</span></span>

<span data-ttu-id="3c5a1-107">통화 계획을 통해 가장 간단한 솔루션 &mdash; 전화 시스템을 원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-107">You might want the simplest solution&mdash;Phone System with Calling Plan.</span></span> <span data-ttu-id="3c5a1-108">다음 다이어그램과 같이 PBX(Private Branch Exchange) 기능을 제공하고 PSTN(공용 전환 전화 네트워크)에 대한 호출을 제공하는 Microsoft의 올인 더 클라우드 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-108">This is Microsoft's all-in-the-cloud solution that provides Private Branch Exchange (PBX) functionality and calls to the Public Switched Telephone Network (PSTN), as shown in the following diagram.</span></span> <span data-ttu-id="3c5a1-109">이 솔루션을 통해 Microsoft는 PSTN 통신업체입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-109">With this solution, Microsoft is your PSTN carrier.</span></span>

![다이어그램 1은 통화 계획이 있는 전화 시스템을 보여줍니다.](media/voice-solutions-simple.png)

<span data-ttu-id="3c5a1-111">다음에 예로 대답하면 전화 요금제가 있는 전화 시스템이 적합한 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-111">If you answer yes to the following, then Phone System with Calling Plan is the right solution for you:</span></span>

- <span data-ttu-id="3c5a1-112">통화 요금제는 지역에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-112">Calling Plan is available in your region.</span></span>
- <span data-ttu-id="3c5a1-113">현재 PSTN 캐리어를 유지할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-113">You do not need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="3c5a1-114">PSTN에 대한 Microsoft 관리 액세스를 사용하려는 경우</span><span class="sxs-lookup"><span data-stu-id="3c5a1-114">You want to use Microsoft-managed access to the PSTN.</span></span>

<span data-ttu-id="3c5a1-115">그러나 상황은 더 복잡할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-115">However, your situation might be more complex.</span></span> <span data-ttu-id="3c5a1-116">예를 들어 통화 계획을 사용할 수 없는 위치에 사무실이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-116">For example, you might have offices in locations where Calling Plan isn't available.</span></span> <span data-ttu-id="3c5a1-117">또는 여러 지리적 위치에 대한 다양한 요구 사항과 함께 복잡하고 다국적 배포를 지원하는 조합 솔루션이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-117">Or you might need a combination solution that supports a complex, multi-national deployment, with different requirements for different geographic locations.</span></span> <span data-ttu-id="3c5a1-118">Microsoft는 솔루션의 조합을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-118">Microsoft supports a combination of solutions:</span></span> 

- <span data-ttu-id="3c5a1-119">통화 계획이 있는 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="3c5a1-119">Phone System with Calling Plan</span></span>
- <span data-ttu-id="3c5a1-120">직접 라우팅을 통해 사용자만의 PSTN 통신사가 있는 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="3c5a1-120">Phone System with your own PSTN carrier with Direct Routing</span></span>
- <span data-ttu-id="3c5a1-121">직접 라우팅을 사용하여 전화 시스템과 통화 계획 및 전화 시스템을 모두 사용하는 조합 솔루션</span><span class="sxs-lookup"><span data-stu-id="3c5a1-121">A combination solution that uses both Phone System with Calling Plan and Phone System with Direct Routing</span></span>

## <a name="what-do-you-need-to-read"></a><span data-ttu-id="3c5a1-122">무엇을 읽어야 하나요?</span><span class="sxs-lookup"><span data-stu-id="3c5a1-122">What do you need to read?</span></span>

<span data-ttu-id="3c5a1-123">**모두에 필요합니다.**</span><span class="sxs-lookup"><span data-stu-id="3c5a1-123">**Required for all.**</span></span> <span data-ttu-id="3c5a1-124">이 문서의 일부 섹션은 모든 조직과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-124">Some of the sections in this article pertain to all organizations.</span></span> <span data-ttu-id="3c5a1-125">예를 들어 모든 사람이 전화 시스템에 대해 읽고 PSTN(공용 전환 전화 네트워크)에 연결하는 옵션을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-125">For example, everyone should read about Phone System and understand the options for connecting to the Public Switched Telephone Network (PSTN).</span></span> 


| <span data-ttu-id="3c5a1-126">모두에 필수</span><span class="sxs-lookup"><span data-stu-id="3c5a1-126">Required for all</span></span> | <span data-ttu-id="3c5a1-127">설명</span><span class="sxs-lookup"><span data-stu-id="3c5a1-127">Description</span></span> |
| :------------|:-------|
| [<span data-ttu-id="3c5a1-128">**전화 시스템**</span><span class="sxs-lookup"><span data-stu-id="3c5a1-128">**Phone System**</span></span>](#phone-system) | <span data-ttu-id="3c5a1-129">Microsoft Teams를 사용하여 Microsoft 365 클라우드에서 통화 제어 및 PBX(Private Branch Exchange) 기능을 사용하도록 설정하는 Microsoft의 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-129">Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Microsoft 365 cloud with Microsoft Teams.</span></span> |
| [<span data-ttu-id="3c5a1-130">**PSTN(공용 전환 전화 네트워크) 연결 옵션**</span><span class="sxs-lookup"><span data-stu-id="3c5a1-130">**Public Switched Telephone Network (PSTN) connectivity options**</span></span>](#public-switched-telephone-network-connectivity-options) | <span data-ttu-id="3c5a1-131">Microsoft를 전화 통신 사업자로 사용하거나 직접 라우팅을 사용하여 사용자 자신의 전화 통신 통신업체를 Microsoft Teams에 연결하는 중 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-131">A choice between using Microsoft as your telephony carrier or connecting your own telephony carrier to Microsoft Teams by using Direct Routing.</span></span> <span data-ttu-id="3c5a1-132">전화 시스템과 결합된 PSTN 연결 옵션을 사용하면 사용자가 전 세계에 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-132">Combined with Phone System, PSTN connectivity options enable your users to make phone calls all over the world.</span></span>|

<span data-ttu-id="3c5a1-133">**요구 사항에 따라 다릅니다.**</span><span class="sxs-lookup"><span data-stu-id="3c5a1-133">**Depending on your requirements.**</span></span> <span data-ttu-id="3c5a1-134">이 문서의 일부 섹션은 기존 배포 및 요구 사항에 따라 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-134">Some of the sections in this article are pertinent depending on your existing deployment and requirements.</span></span> <span data-ttu-id="3c5a1-135">예를 들어 Location-Based 우회를 허용하지 않는 지리적 위치에 있는 직접 라우팅 고객에게만 이러한 라우팅이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-135">For example, Location-Based Routing is only required for Direct Routing customers in geographic locations that do not allow toll bypass.</span></span>

<span data-ttu-id="3c5a1-136">다음 추가 구성 중 어느 것이 필요할지 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-136">Consider which of these additional configurations you might need:</span></span>

![다이어그램 2에서는 Microsoft의 전화 번호, 전화 걸기 계획 및 통화 라우팅과 같은 추가 음성 구성 요소를 보여줍니다.](media/voice-consider-additional-components.png)

| <span data-ttu-id="3c5a1-138">요구 사항에 따라</span><span class="sxs-lookup"><span data-stu-id="3c5a1-138">Depending on your requirements</span></span> | <span data-ttu-id="3c5a1-139">설명</span><span class="sxs-lookup"><span data-stu-id="3c5a1-139">Description</span></span> |
| :------------|:-------|
| [<span data-ttu-id="3c5a1-140">**Microsoft의 전화 번호**</span><span class="sxs-lookup"><span data-stu-id="3c5a1-140">**Phone numbers from Microsoft**</span></span>](#phone-numbers-from-microsoft) | <span data-ttu-id="3c5a1-141">Microsoft에서 전화 번호를 얻고 관리하는 방법 및 기존 번호를 Microsoft로 전송하는 방법.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-141">How to get and manage phone numbers from Microsoft, and how to transfer existing numbers to Microsoft.</span></span> <span data-ttu-id="3c5a1-142">Microsoft 통화 요금제에 대한 전화 번호를 획득하고 기존 번호를 전송하고, 서비스 번호를 확보해야 하는 경우 이 정보를 읽어 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-142">Read this if you need to obtain phone numbers for Microsoft Calling Plan, transfer existing numbers, obtain service numbers, and so on.</span></span> |
| [<span data-ttu-id="3c5a1-143">**전화 걸기 계획 및 통화 라우팅**</span><span class="sxs-lookup"><span data-stu-id="3c5a1-143">**Dial plans and call routing**</span></span>](#dial-plans-and-call-routing) | <span data-ttu-id="3c5a1-144">통화 권한 부여 및 통화 라우팅을 위해 전화 걸기 전화 번호를 대체 형식으로 변환하는 전화 요금제(일반적으로 E.164 형식)를 구성하고 관리하는 방법.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-144">How to configure and manage dial plans that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span> <span data-ttu-id="3c5a1-145">전화 걸기 계획의 대상과 조직의 전화 걸기 계획을 지정해야 하는지 이해해야 하는 경우 이 내용을 읽어 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-145">Read this if you need to understand what dial plans are and  whether you need to specify dial plans for your organization.</span></span>|
| [<span data-ttu-id="3c5a1-146">**긴급 통화**</span><span class="sxs-lookup"><span data-stu-id="3c5a1-146">**Emergency calling**</span></span>](#emergency-calling) | <span data-ttu-id="3c5a1-147">PSTN 연결 옵션에 따라 긴급 통화를 &mdash; 관리하고 구성하는 방법.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-147">How to manage and configure emergency calling&mdash;depending on your PSTN connectivity option.</span></span> <span data-ttu-id="3c5a1-148">Microsoft 통화 계획 또는 직접 라우팅을 사용하는 경우 조직에 대한 긴급 통화를 관리하는 방법을 이해해야 하는 경우 이 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-148">Read this section if you are using Microsoft Calling Plan or Direct Routing and need to understand how to manage emergency calling for your organization.</span></span> |
| [<span data-ttu-id="3c5a1-149">**직접 라우팅에 대한 위치 기반 라우팅**</span><span class="sxs-lookup"><span data-stu-id="3c5a1-149">**Location-Based Routing for Direct Routing**</span></span>](#location-based-routing-for-direct-routing) |<span data-ttu-id="3c5a1-150">LBR(Location-Based 라우팅)을 사용하여 해당 지리적 위치에 따라 Microsoft Teams 사용자에 대한 대금 우회를 제한하는 방법</span><span class="sxs-lookup"><span data-stu-id="3c5a1-150">How to use Location-Based Routing (LBR) to restrict toll bypass for Microsoft Teams users based on their geographic location.</span></span> <span data-ttu-id="3c5a1-151">조직에서 우회를 허용하지 않는 위치에서 직접 라우팅을 사용하는 경우 이 섹션을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-151">Read this section if your organization is using Direct Routing at a location that does not allow toll bypass.</span></span>
| [<span data-ttu-id="3c5a1-152">**클라우드 음성 기능에 대한 네트워크 토폴로지**</span><span class="sxs-lookup"><span data-stu-id="3c5a1-152">**Network topology for cloud voice features**</span></span>](#network-topology-for-voice-features) | <span data-ttu-id="3c5a1-153">조직에서 직접 라우팅 또는 동적 Location-Based LBR(라우팅)을 배포하는 경우 Microsoft Teams에서 이러한 기능과 함께 사용하도록 네트워크 설정을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-153">If your organization is deploying Location-Based Routing (LBR) for Direct Routing or dynamic emergency calling, you must configure network settings for use with these features in Microsoft Teams.</span></span> <span data-ttu-id="3c5a1-154">직접 라우팅에 대한 LBR을 구현하는 경우 또는 통화 계획 또는 직접 라우팅을 통해 동적 긴급 호출을 구현하는 경우 이 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-154">Read this section if you are implementing LBR for Direct Routing, or if you are implementing dynamic emergency calling with Calling Plan or Direct Routing.</span></span> |
| [<span data-ttu-id="3c5a1-155">**기존 음성 솔루션 마이그레이션**</span><span class="sxs-lookup"><span data-stu-id="3c5a1-155">**Migrate your existing voice solution**</span></span>](#migrate-your-existing-voice-solution-to-teams) | <span data-ttu-id="3c5a1-156">음성 솔루션을 Teams로 마이그레이션할 때 생각해야 할 일입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-156">What you need to think about when migrating your voice solution to Teams.</span></span>  <span data-ttu-id="3c5a1-157">기존 음성 솔루션에서 Teams로 마이그레이션하는 경우 이 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-157">Read this section if you are migrating from an existing voice solution to Teams.</span></span> 



> [!Important]
> <span data-ttu-id="3c5a1-158">이 문서에서는 Microsoft Teams를 사용할 수 있는 음성 솔루션에 중점을</span><span class="sxs-lookup"><span data-stu-id="3c5a1-158">This article focuses on voice solutions with Microsoft Teams.</span></span> <span data-ttu-id="3c5a1-159">비즈니스용 Skype Online 솔루션을 여전히 사용할 수 있는 [반면(Microsoft](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)전화 통신 솔루션에 설명된 바와 같이) 비즈니스용 Skype Online이 2021년 7월 31일 사용 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-159">While solutions with Skype for Business Online are still available (as described in [Microsoft telephony solutions](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)), it's important to understand that Skype for Business Online will be retired on July 31, 2021.</span></span>  <span data-ttu-id="3c5a1-160">이 날짜 이후에는 비즈니스용 Skype Online 서비스에 더 이상 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-160">After that date, the Skype for Business Online service will no longer be accessible.</span></span> <span data-ttu-id="3c5a1-161">또한 비즈니스용 Skype 서버 또는 Cloud Connector Edition 및 비즈니스용 Skype Online을 통해 더 이상 지원되지 않는 모든 온라인 환경 간에 PSTN 연결은 지원되지 &mdash; &mdash; 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-161">In addition, PSTN connectivity between your on-premises environment&mdash;whether through Skype for Business Server or Cloud Connector Edition&mdash;and Skype for Business Online will no longer be supported.</span></span> <span data-ttu-id="3c5a1-162">이 문서에서는 Teams 음성 솔루션과 필요한 경우 직접 라우팅을 사용하여 Teams에 On-프레미스 전화 통신 네트워크를 연결할 수 있는 방법을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-162">This article introduces Teams voice solutions and how you can connect your on-premises telephony network, if necessary, to Teams by using Direct Routing.</span></span>


## <a name="phone-system"></a><span data-ttu-id="3c5a1-163">전화 시스템</span><span class="sxs-lookup"><span data-stu-id="3c5a1-163">Phone System</span></span>

<span data-ttu-id="3c5a1-164">전화 시스템은 Microsoft 365 또는 Office 365 클라우드에서 Microsoft Teams에서 통화 제어 및 PBX(Private Branch Exchange) 기능을 사용하도록 설정하는 Microsoft의 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-164">Phone System is Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Microsoft 365 or Office 365 cloud with Microsoft Teams.</span></span>

<span data-ttu-id="3c5a1-165">Phone System은 Teams 또는 Skype for Business 클라이언트 및 인증된 디바이스와 함께 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-165">Phone System works with Teams or Skype for Business clients and certified devices.</span></span> <span data-ttu-id="3c5a1-166">전화 시스템을 사용하면 기존 PBX 시스템을 Microsoft 365 또는 Office 365에서 직접 배달하는 기능 집합으로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-166">Phone System allows you to replace your existing PBX system with a set of features directly delivered from Microsoft 365 or Office 365.</span></span> 

<span data-ttu-id="3c5a1-167">조직의 사용자 간 통화는 전화 시스템 내에서 내부적으로 처리하며 PSTN(공용 전환 전화 네트워크)으로 이동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-167">Calls between users in your organization are handled internally within Phone System, and never go to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="3c5a1-168">이는 다른 지리적 영역에 있는 조직의 사용자 간 통화에 적용되어 이러한 내부 호출에 대한 장거리 비용이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-168">This applies to calls between users in your organization located in different geographical areas, removing long-distance costs on these internal calls.</span></span>

<span data-ttu-id="3c5a1-169">이 문서에서는 다음 Phone System 주요 기능 및 기능을 소개하고, 고려해야 할 배포 결정을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-169">This article introduces the following Phone System key features and functionality, and the deployment decisions you'll need to consider:</span></span>

- [<span data-ttu-id="3c5a1-170">자동 전화 교환 및 통화 큐</span><span class="sxs-lookup"><span data-stu-id="3c5a1-170">Auto attendants and call queues</span></span>](#auto-attendants-and-call-queues)
- [<span data-ttu-id="3c5a1-171">클라우드 음성 메일</span><span class="sxs-lookup"><span data-stu-id="3c5a1-171">Cloud Voicemail</span></span>](#cloud-voicemail)
- [<span data-ttu-id="3c5a1-172">ID 호출</span><span class="sxs-lookup"><span data-stu-id="3c5a1-172">Calling identity</span></span>](#calling-identity)

![다이어그램 3에서는 전화 시스템에 자동 참석자 및 호출 쿼리, 클라우드 음성 문서 및 통화 ID가 포함되어 있습니다.](media/phone-system-contains.png)

<span data-ttu-id="3c5a1-174">모든 전화 시스템 기능 및 전화 시스템을 설정하는 방법에 대한 자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-174">For information about all Phone System features, and how to set up Phone System, see the following articles:</span></span>

- [<span data-ttu-id="3c5a1-175">다음은 통화 시스템 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-175">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)
- [<span data-ttu-id="3c5a1-176">조직에서 전화 시스템 설정</span><span class="sxs-lookup"><span data-stu-id="3c5a1-176">Set up Phone System in your organization</span></span>](setting-up-your-phone-system.md)<br>
  <span data-ttu-id="3c5a1-177">전화 시스템 라이선스를 구입하고 할당하고, 전화 번호를 관리하고, 무료 번호에 대한 통신 크레딧을 설정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-177">Describes how to buy and assign Phone System licenses, manage phone numbers, and set up communication credits for toll-free numbers.</span></span> 

<span data-ttu-id="3c5a1-178">지원되는 디바이스 관리에 대한 자세한 내용은 [Microsoft Teams](devices/device-management.md) 및 Teams Marketplace에서 디바이스 [관리를 참조하세요.](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)</span><span class="sxs-lookup"><span data-stu-id="3c5a1-178">For information about managing supported devices, see [Manage your devices in Microsoft Teams](devices/device-management.md) and [Teams Marketplace](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span>


### <a name="auto-attendants-and-call-queues"></a><span data-ttu-id="3c5a1-179">자동 참석자 및 통화 큐</span><span class="sxs-lookup"><span data-stu-id="3c5a1-179">Auto attendants and Call queues</span></span>

<span data-ttu-id="3c5a1-180">자동 참석자는 발신자 입력에 따라 호출을 라우팅하도록 메뉴 옵션을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-180">Auto attendants allow you to set up menu options to route calls based on caller input.</span></span> <span data-ttu-id="3c5a1-181">호출 큐는 발신자 대기 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-181">Call queues are waiting areas for callers.</span></span> <span data-ttu-id="3c5a1-182">함께 사용되는 자동 참석자 및 통화 큐는 조직의 적절한 사람 또는 부서로 발신자 라우팅을 쉽게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-182">Used together, auto attendants and call queues can easily route callers to the appropriate person or department in your organization.</span></span>

<span data-ttu-id="3c5a1-183">자동 참석자 및 호출 큐에 대한 자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-183">For information about auto attendants and call queues, see the following articles:</span></span>

- [<span data-ttu-id="3c5a1-184">Teams 자동 참석자 및 호출 큐 계획</span><span class="sxs-lookup"><span data-stu-id="3c5a1-184">Plan for Teams auto attendants and call queues</span></span>](plan-auto-attendant-call-queue.md)
- [<span data-ttu-id="3c5a1-185">자동 참석자 설정</span><span class="sxs-lookup"><span data-stu-id="3c5a1-185">Set up an auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
- [<span data-ttu-id="3c5a1-186">통화 큐 만들기</span><span class="sxs-lookup"><span data-stu-id="3c5a1-186">Create a call queue</span></span>](create-a-phone-system-call-queue.md) 
- [<span data-ttu-id="3c5a1-187">Contoso 사례 연구: 자동 참석자 및 통화 큐</span><span class="sxs-lookup"><span data-stu-id="3c5a1-187">Contoso case study: Auto attendants and call queues</span></span>](voice-case-study-call-queues.md)<br>
  <span data-ttu-id="3c5a1-188">소설적 다국적 기업 Contoso가 음성 솔루션에 대한 자동 참석자 및 호출 큐를 구현하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-188">Describes how a fictional multi-national corporation, Contoso, implemented auto attendants and call queues for their voice solution.</span></span>

### <a name="cloud-voicemail"></a><span data-ttu-id="3c5a1-189">클라우드 음성 메일</span><span class="sxs-lookup"><span data-stu-id="3c5a1-189">Cloud Voicemail</span></span>

<span data-ttu-id="3c5a1-190">Azure Voicemail 서비스에서 제공하는 Cloud Voicemail은 Exchange 사서함에만 음성 메일 예금을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-190">Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only.</span></span> <span data-ttu-id="3c5a1-191">타사 전자 메일 시스템을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-191">It doesn't support third-party email systems.</span></span> 

<span data-ttu-id="3c5a1-192">클라우드 음성 사서함에는 기본적으로 조직의 모든 사용자가 사용할 수 있는 음성 메일 기록이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-192">Cloud Voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="3c5a1-193">비즈니스 요구에 따라 조직 전체의 특정 사용자 또는 모든 사용자에 대한 음성사본 전사 기능을 사용하지 않도록 설정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-193">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span>

<span data-ttu-id="3c5a1-194">온라인 전용 사용자의 경우 전화 시스템 라이선스가 할당된 후에 Cloud Voicemail이 자동으로 설정되고 프로비전됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-194">For online only users, Cloud Voicemail is automatically set up and provisioned for users after they are assigned a Phone System license.</span></span> <span data-ttu-id="3c5a1-195">Exchange 사서함이 있는 Phone System 사용자의 경우 추가 구성 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-195">For Phone System users with an Exchange mailbox, you will need to perform extra configuration steps.</span></span> 

<span data-ttu-id="3c5a1-196">Cloud Voicemail 및 해당 구성에 대한 자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-196">For more information about Cloud Voicemail and its configuration, see the following articles:</span></span>

- [<span data-ttu-id="3c5a1-197">클라우드 음성 메일 설정</span><span class="sxs-lookup"><span data-stu-id="3c5a1-197">Set up Cloud Voicemail</span></span>](set-up-phone-system-voicemail.md)
- [<span data-ttu-id="3c5a1-198">조직의 음성메일 정책 설정</span><span class="sxs-lookup"><span data-stu-id="3c5a1-198">Set voicemail policies in your organization</span></span>](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)


### <a name="calling-identity"></a><span data-ttu-id="3c5a1-199">ID 호출</span><span class="sxs-lookup"><span data-stu-id="3c5a1-199">Calling identity</span></span>

<span data-ttu-id="3c5a1-200">기본적으로 모든 아웃바운드 호출은 할당된 전화 번호를 호출 ID(발신자 ID)로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-200">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="3c5a1-201">전화 수신자는 발신자를 빠르게 확인하고 통화를 수락할지 거부할지를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-201">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span> <span data-ttu-id="3c5a1-202">발신자 ID를 구성하거나 발신자 ID를 변경하거나 차단하는 데 대한 자세한 내용은 사용자에 대한 [발신자 ID 설정을 참조하세요.](set-the-caller-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="3c5a1-202">For information about configuring caller ID or to change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> 

## <a name="public-switched-telephone-network-connectivity-options"></a><span data-ttu-id="3c5a1-203">공용 전환된 전화 네트워크 연결 옵션</span><span class="sxs-lookup"><span data-stu-id="3c5a1-203">Public Switched Telephone Network connectivity options</span></span>

<span data-ttu-id="3c5a1-204">Phone System은 조직에 대한 완전한 PBX 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-204">Phone System provides complete PBX capabilities for your organization.</span></span> <span data-ttu-id="3c5a1-205">그러나 사용자가 조직 외부에서 전화를 걸 수 있도록 설정하려면 전화 시스템을 PSTN(공용 전환 전화 네트워크)에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-205">However, to enable users to make calls outside your organization, you need to connect Phone System to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="3c5a1-206">전화 시스템을 PSTN에 연결하기 위해 다음 옵션 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-206">To connect Phone System to the PSTN, you can choose one of the following options:</span></span>

- <span data-ttu-id="3c5a1-207">[**통화 계획이 있는 전화 시스템.**](#phone-system-with-calling-plan)</span><span class="sxs-lookup"><span data-stu-id="3c5a1-207">[**Phone System with Calling Plan**](#phone-system-with-calling-plan).</span></span> <span data-ttu-id="3c5a1-208">PSTN 통신사로 Microsoft를 사용할 수 있는 올인원 클라우드 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-208">An all-in-the-cloud solution with Microsoft as your PSTN carrier.</span></span>

- <span data-ttu-id="3c5a1-209">직접 라우팅을 사용하여 자체 [**PSTN**](#phone-system-with-own-pstn-carrier-with-direct-routing) 통신사와 전화 시스템으로 프레미스 환경을 Teams에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-209">[**Phone System with your own PSTN carrier**](#phone-system-with-own-pstn-carrier-with-direct-routing) by using Direct Routing to connect your on-premises environment to Teams.</span></span>

<span data-ttu-id="3c5a1-210">복잡한 환경에 대한 솔루션을 디자인하거나 다단계 마이그레이션을 관리할 수 있는 옵션의 조합을 선택할 수도 있습니다(나중에 마이그레이션에 대한 자세한 내용은).</span><span class="sxs-lookup"><span data-stu-id="3c5a1-210">You can also choose a combination of options, which enables you to design a solution for a complex environment, or manage a multi-step migration (more about migration later).</span></span>

### <a name="phone-system-with-calling-plan"></a><span data-ttu-id="3c5a1-211">통화 계획이 있는 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="3c5a1-211">Phone System with Calling Plan</span></span> 

<span data-ttu-id="3c5a1-212">이 문서의 앞부분에서 설명한 대로 통화 계획이 있는 전화 시스템은 Teams 사용자를 위한 Microsoft의 올인원 클라우드 음성 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-212">As described earlier in this article, Phone System with Calling Plan is Microsoft's all-in-the-cloud voice solution for Teams users.</span></span> <span data-ttu-id="3c5a1-213">전 세계 유선 전화 및 휴대폰에 대한 통화를 사용하도록 설정하기 위해 PSTN(공용 전환 전화 네트워크)에 Microsoft Phone System을 연결하는 가장 간단한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-213">This is the simplest option that connects Microsoft Phone System to the Public Switched Telephone Network (PSTN) to enable calls to landlines and mobile phones around the world.</span></span> <span data-ttu-id="3c5a1-214">이 옵션을 사용하면 Microsoft는 조직에 대한 PBX(Private Branch Exchange) 기능을 제공하며 다음 다이어그램과 같이 PSTN 통신 사업자 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-214">With this option, Microsoft provides Private Branch Exchange (PBX) functionality for your organization and acts as your PSTN carrier, as shown in the following diagram:</span></span>

![다이어그램 4에서는 자동 전화 시스템, 전화 큐, 발신자 ID 등 PSTN 통신사로 Microsoft를 보여줍니다.](media/voice-solution-microsoft-complete.png)

<span data-ttu-id="3c5a1-216">다음에 예로 대답하면 전화 요금제가 있는 전화 시스템이 적합한 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-216">If you answer yes to the following, then Phone System with Calling Plan is the right solution for you:</span></span>

- <span data-ttu-id="3c5a1-217">통화 요금제는 지역에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-217">Calling Plan is available in your region.</span></span>
- <span data-ttu-id="3c5a1-218">현재 PSTN 캐리어를 유지할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-218">You do not need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="3c5a1-219">PSTN에 대한 Microsoft 관리 액세스를 사용하려는 경우</span><span class="sxs-lookup"><span data-stu-id="3c5a1-219">You want to use Microsoft-managed access to the PSTN.</span></span>

<span data-ttu-id="3c5a1-220">이 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-220">With this option:</span></span> 

- <span data-ttu-id="3c5a1-221">전 세계 휴대폰에 전화를 걸 수 있는 추가 국내 또는 국제 전화 요금제가 있는 Microsoft Phone System을 사용할 수 있습니다(라이선스가 부여되는 서비스 수준에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-221">You get Microsoft Phone System with added Domestic or International Calling Plans that enable calling to phones around the world (depending on the level of service being licensed).</span></span>

- <span data-ttu-id="3c5a1-222">호출 계획은 &mdash; Microsoft 365 또는 Office 365에서 작동하기 때문에 프레미스 배포의 배포 또는 유지 관리가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-222">You do not require deployment or maintenance of an on-premises deployment&mdash;because Calling Plan operates out of Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="3c5a1-223">참고: 필요한 경우 SBC에서 지원하는 타사 PBX, 아날로그 디바이스 및 기타 타사 전화 통신 장비와 상호 연동성을 위해 직접 라우팅을 통해 지원되는 SBC(세션 경계 컨트롤러)를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-223">Note: If necessary, you can choose to connect a supported Session Border Controller (SBC) through Direct Routing for interoperability with third-party PBXs, analog devices, and other third-party telephony equipment supported by the SBC.</span></span>

<span data-ttu-id="3c5a1-224">이 옵션은 Microsoft 365 또는 Office 365에 대한 끊임 없는 연결이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-224">This option requires uninterrupted connection to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="3c5a1-225">통화 계획에 대한 자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-225">For more information about Calling Plan, see the following articles:</span></span>

- [<span data-ttu-id="3c5a1-226">사용자에게 적합한 통화 플랜은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="3c5a1-226">Which Calling Plan is right for you?</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="3c5a1-227">통화 플랜을 구입하는 방법</span><span class="sxs-lookup"><span data-stu-id="3c5a1-227">How to buy a Calling Plan</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="3c5a1-228">통화 플랜의 국가 및 지역 가용성</span><span class="sxs-lookup"><span data-stu-id="3c5a1-228">Country and region availability for Calling Plan</span></span>](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
- [<span data-ttu-id="3c5a1-229">통화 계획 설정</span><span class="sxs-lookup"><span data-stu-id="3c5a1-229">Set up Calling Plan</span></span>](set-up-calling-plans.md)


### <a name="phone-system-with-own-pstn-carrier-with-direct-routing"></a><span data-ttu-id="3c5a1-230">직접 라우팅이 있는 자체 PSTN 통신사가 있는 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="3c5a1-230">Phone System with own PSTN carrier with Direct Routing</span></span>

<span data-ttu-id="3c5a1-231">이 옵션은 다음 다이어그램과 같이 직접 라우팅을 사용하여 Microsoft Phone System을 전화 통신 네트워크에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-231">This option connects Microsoft Phone System to your telephony network by using Direct Routing, as shown in the following diagram:</span></span> 

![다이어그램 5에서는 직접 라우팅이 있는 전화 시스템 표시](media/voice-solution-with-direct-routing.png)

<span data-ttu-id="3c5a1-233">다음 질문에 예로 대답하면 직접 라우팅이 있는 전화 시스템이 적합한 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-233">If you answer yes to the following questions, then Phone System with Direct Routing is the right solution for you:</span></span>

- <span data-ttu-id="3c5a1-234">Teams를 전화 시스템과 함께 사용하려는 경우</span><span class="sxs-lookup"><span data-stu-id="3c5a1-234">You want to use Teams with Phone System.</span></span>
- <span data-ttu-id="3c5a1-235">현재 PSTN 캐리어를 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-235">You need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="3c5a1-236">라우팅을 혼합하고, 일부 호출은 통신사를 통해 통화 계획을 통해 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-236">You want to mix routing, with some calls going through Calling Plan, some through your carrier.</span></span>
- <span data-ttu-id="3c5a1-237">타사 PBX 및/또는 오버헤드 페이지, 아날로그 디바이스 등의 장비와 상호 협력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-237">You need to interoperate with third-party PBXs and/or equipment such us overhead pagers, analog devices, and so on.</span></span>

<span data-ttu-id="3c5a1-238">이 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-238">With this option:</span></span>

- <span data-ttu-id="3c5a1-239">추가 프레미스 소프트웨어 없이도 지원되는 SBC를 Microsoft Phone System에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-239">You connect your own supported SBC to Microsoft Phone System without the need for additional on-premises software.</span></span>

- <span data-ttu-id="3c5a1-240">Microsoft Phone System에서 거의 모든 전화 통신 통신을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-240">You can use virtually any telephony carrier with Microsoft Phone System.</span></span>

- <span data-ttu-id="3c5a1-241">이 옵션을 구성하고 관리하도록 선택하거나 이동통신사 또는 파트너가 구성하고 관리할 수 있습니다(이동통신사 또는 파트너가 이 옵션을 제공하는지 묻는 질문).</span><span class="sxs-lookup"><span data-stu-id="3c5a1-241">You can choose to configure and manage this option, or it can be configured and managed by your carrier or partner (ask if your carrier or partner provides this option).</span></span>

- <span data-ttu-id="3c5a1-242">타사 PBX와 아날로그 디바이스 및 Microsoft Phone System과 같은 전화 통신 장비 간에 상호 &mdash; &mdash; 운영성을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-242">You can configure interoperability between your telephony equipment&mdash;such as a third-party PBX and analog devices&mdash;and Microsoft Phone System.</span></span>


<span data-ttu-id="3c5a1-243">이 옵션에는 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-243">This option requires the following:</span></span>

- <span data-ttu-id="3c5a1-244">Microsoft 365 또는 Office 365에 대한 끊임 없는 연결.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-244">Uninterrupted connection to Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="3c5a1-245">지원되는 SBC를 배포하고 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-245">Deploying and maintaining a supported SBC.</span></span>

- <span data-ttu-id="3c5a1-246">타사 통신사와의 계약입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-246">A contract with a third-party carrier.</span></span>
  <span data-ttu-id="3c5a1-247">(통화 요금제가 있는 전화 시스템에 있는 사용자를 위해 타사 PBX, 아날로그 디바이스 또는 기타 전화 통신 장비에 대한 연결을 제공하는 옵션으로 배포되지 않는 한).)</span><span class="sxs-lookup"><span data-stu-id="3c5a1-247">(Unless deployed as an option to provide connection to third-party PBX, analog devices, or other telephony equipment for users who are on Phone System with Calling Plan.)</span></span>

<span data-ttu-id="3c5a1-248">직접 라우팅에 대한 자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-248">For more information about Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="3c5a1-249">전화 시스템 직접 라우팅</span><span class="sxs-lookup"><span data-stu-id="3c5a1-249">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)
- [<span data-ttu-id="3c5a1-250">직접 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="3c5a1-250">Plan Direct Routing</span></span>](direct-routing-plan.md)
- [<span data-ttu-id="3c5a1-251">직접 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="3c5a1-251">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="3c5a1-252">직접 라우팅에서 사용할 음성 라우팅 정책 관리</span><span class="sxs-lookup"><span data-stu-id="3c5a1-252">Manage voice routing policies for use with Direct Routing</span></span>](manage-voice-routing-policies.md)
- [<span data-ttu-id="3c5a1-253">직접 라우팅으로 전달되는 위치 기반 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="3c5a1-253">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="3c5a1-254">직접 라우팅으로 인증된 SBC(Session Border Controller) 목록</span><span class="sxs-lookup"><span data-stu-id="3c5a1-254">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)

## <a name="phone-numbers-from-microsoft"></a><span data-ttu-id="3c5a1-255">Microsoft의 전화 번호</span><span class="sxs-lookup"><span data-stu-id="3c5a1-255">Phone numbers from Microsoft</span></span>

<span data-ttu-id="3c5a1-256">Microsoft에는 구독자(사용자)  번호와 조직의 사용자에게 할당할 수 있는 전화 번호와  무료 서비스 번호로 사용할 수 있는 서비스 번호의 두 가지 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-256">Microsoft has two types of telephone numbers available: *subscriber* (user) numbers, which can be assigned to users in your organization, and *service* numbers, available as toll and toll-free service numbers.</span></span> <span data-ttu-id="3c5a1-257">서비스 번호는 구독자 번호보다 동시 호출 용량이 높고 오디오 회의, 자동 참석자 또는 통화 큐와 같은 서비스에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-257">Service numbers have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

<span data-ttu-id="3c5a1-258">다음을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-258">You will need to decide:</span></span>

- <span data-ttu-id="3c5a1-259">Microsoft에서 새 전화 번호가 필요한 사용자 위치는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="3c5a1-259">Which user locations need new phone numbers from Microsoft?</span></span>
- <span data-ttu-id="3c5a1-260">어떤 유형의 전화 번호(구독자 또는 서비스)가 필요한가요?</span><span class="sxs-lookup"><span data-stu-id="3c5a1-260">Which type of telephone number (subscriber or service) do I need?</span></span> 
- <span data-ttu-id="3c5a1-261">기존 전화 번호를 Teams에 이식하는 방법</span><span class="sxs-lookup"><span data-stu-id="3c5a1-261">How do I port existing phone numbers to Teams?</span></span>

<span data-ttu-id="3c5a1-262">새 번호 또는 나가는 번호 전송을 포함하여 조직의 전화 번호 관리에 대한 자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-262">For more information about managing phone numbers in your organization, including getting new numbers or transferring exiting numbers, see the following articles:</span></span>

- [<span data-ttu-id="3c5a1-263">조직의 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="3c5a1-263">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 
- [<span data-ttu-id="3c5a1-264">통화 계획에 사용되는 다양한 종류의 전화 번호</span><span class="sxs-lookup"><span data-stu-id="3c5a1-264">Different kinds of phone numbers used for Calling Plan</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="3c5a1-265">사용자의 전화 번호 가져오기</span><span class="sxs-lookup"><span data-stu-id="3c5a1-265">Getting phone numbers for your users</span></span>](getting-phone-numbers-for-your-users.md)
- [<span data-ttu-id="3c5a1-266">Microsoft Teams로 전화 번호 전송</span><span class="sxs-lookup"><span data-stu-id="3c5a1-266">Transfer phone numbers to Microsoft Teams</span></span>](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="dial-plans-and-call-routing"></a><span data-ttu-id="3c5a1-267">전화 걸기 계획 및 통화 라우팅</span><span class="sxs-lookup"><span data-stu-id="3c5a1-267">Dial plans and call routing</span></span>

<span data-ttu-id="3c5a1-268">다이얼 플랜은 통화 권한 부여 및 통화 라우팅을 위해 전화 걸기 전화 번호를 대체 형식(일반적으로 E.164 형식)으로 변환하는 정규화 규칙 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-268">A dial plan is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="3c5a1-269">다음을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-269">You will need to decide the following:</span></span> 

- <span data-ttu-id="3c5a1-270">조직에 사용자 지정 다이얼 플랜이 필요한가요?</span><span class="sxs-lookup"><span data-stu-id="3c5a1-270">Does my organization need a customized dial plan?</span></span>
- <span data-ttu-id="3c5a1-271">사용자 지정 다이얼 플랜이 필요한 사용자는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="3c5a1-271">Which users require a customized dial plan?</span></span>
- <span data-ttu-id="3c5a1-272">각 사용자에게 어떤 테넌트 다이얼 플랜을 할당해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="3c5a1-272">Which tenant dial plan should be assigned to each user?</span></span>

<span data-ttu-id="3c5a1-273">자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-273">For more information, see the following articles:</span></span> 

- [<span data-ttu-id="3c5a1-274">다이얼 플랜이 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="3c5a1-274">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="3c5a1-275">테넌트 다이얼 계획</span><span class="sxs-lookup"><span data-stu-id="3c5a1-275">Plan for tenant dial plans</span></span>](what-are-dial-plans.md#planning-for-tenant-dial-plans)
- [<span data-ttu-id="3c5a1-276">다이얼 플랜 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="3c5a1-276">Create and manage dial plans</span></span>](create-and-manage-dial-plans.md)

## <a name="emergency-calling"></a><span data-ttu-id="3c5a1-277">비상 전화</span><span class="sxs-lookup"><span data-stu-id="3c5a1-277">Emergency calling</span></span>

<span data-ttu-id="3c5a1-278">긴급 통화를 구성하는 방법은 PSTN 연결 옵션인 Microsoft 통화 계획 또는 직접 라우팅에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-278">How you configure emergency calling differs depending on your PSTN connectivity option: Microsoft Calling Plan or Direct Routing.</span></span> <span data-ttu-id="3c5a1-279">Microsoft 통화 계획 및 전화 시스템 직접 라우팅에 대한 동적 긴급 호출은 Teams 클라이언트의 현재 위치에 따라 긴급 통화를 구성하고 라우팅하고 보안 담당자에게 알릴 수 있는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-279">Dynamic emergency calling for Microsoft Calling Plan and Phone System Direct Routing provides the capability to configure and route emergency calls and notify security personnel based on the current location of the Teams client.</span></span> <span data-ttu-id="3c5a1-280">긴급 호출 개념 및 용어 및 동적 긴급 호출을 구성하는 방법에 대한 자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-280">For more information about emergency calling concepts and terminology, and how to configure dynamic emergency calling, see the following articles:</span></span>

- [<span data-ttu-id="3c5a1-281">긴급 통화 관리</span><span class="sxs-lookup"><span data-stu-id="3c5a1-281">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="3c5a1-282">동적인 긴급 전화 계획 및 구성</span><span class="sxs-lookup"><span data-stu-id="3c5a1-282">Plan and configure dynamic emergency calling</span></span>](configure-dynamic-emergency-calling.md)
- [<span data-ttu-id="3c5a1-283">Contoso 사례 연구: 긴급 통화</span><span class="sxs-lookup"><span data-stu-id="3c5a1-283">Contoso case study: Emergency calling</span></span>](voice-case-study-emergency-calling.md)<br>
  <span data-ttu-id="3c5a1-284">소설적 다국적 기업 Contoso가 조직에 대한 긴급 호출을 구현하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-284">Describes how a fictional multi-national corporation, Contoso, implemented emergency calling for their organization.</span></span>

## <a name="location-based-routing-for-direct-routing"></a><span data-ttu-id="3c5a1-285">Location-Based 라우팅에 대한 Location-Based 라우팅</span><span class="sxs-lookup"><span data-stu-id="3c5a1-285">Location-Based Routing for Direct Routing</span></span>

<span data-ttu-id="3c5a1-286">일부 국가 및 지역에서는 PSTN(공용 전환 전화 네트워크) 공급자를 우회하여 장거리 통화 비용을 절감하는 것이 불법입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-286">In some countries and regions, it's illegal to bypass the Public Switched Telephone Network (PSTN) provider to decrease long-distance calling costs.</span></span> <span data-ttu-id="3c5a1-287">Location-Based 라우팅을 사용하면 해당 지리적 위치에 따라 Microsoft Teams 사용자에 대한 대금 우회를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-287">Location-Based Routing for Direct Routing enables you to restrict toll bypass for Microsoft Teams users based on their geographic location.</span></span> <span data-ttu-id="3c5a1-288">LBR(라우팅)을 계획하고 Location-Based 방법에 대한 자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-288">For more information about how to plan and configure Location-Based Routing (LBR), see the following articles:</span></span>

- [<span data-ttu-id="3c5a1-289">직접 라우팅으로 전달되는 위치 기반 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="3c5a1-289">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="3c5a1-290">위치 기반 라우팅의 네트워크 설정 구성</span><span class="sxs-lookup"><span data-stu-id="3c5a1-290">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="3c5a1-291">직접 라우팅에 위치 기반 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="3c5a1-291">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)
- [<span data-ttu-id="3c5a1-292">Contoso 사례 연구: Location-Based 라우팅</span><span class="sxs-lookup"><span data-stu-id="3c5a1-292">Contoso case study: Location-Based Routing</span></span>](voice-case-study-location-based-routing.md)<br>
  <span data-ttu-id="3c5a1-293">소설 다국적 기업인 Contoso가 조직에 대한 라우팅을 Location-Based 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-293">Describes how a fictional multi-national corporation, Contoso, implemented Location-Based Routing for their organization.</span></span>

## <a name="network-topology-for-voice-features"></a><span data-ttu-id="3c5a1-294">음성 기능에 대한 네트워크 토폴로지</span><span class="sxs-lookup"><span data-stu-id="3c5a1-294">Network topology for voice features</span></span>

<span data-ttu-id="3c5a1-295">동적 긴급 통화를 배포하거나 직접 라우팅에 Location-Based 라우팅을 배포하는 경우 Microsoft Teams에서 이러한 기능과 함께 사용하도록 네트워크 설정을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-295">If you are deploying dynamic emergency calling or Location-Based Routing for Direct Routing, you must configure network settings for use with these features in Microsoft Teams.</span></span> <span data-ttu-id="3c5a1-296">네트워크 지역, 네트워크 사이트, 네트워크 서브넷 및 신뢰할 수 있는 IP 주소에 대한 네트워크 설정을 구성하는 방법에 대한 자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-296">To learn how to configure network settings for network regions, network sites, network subnets, and trusted IP addresses, see the following articles:</span></span>

- [<span data-ttu-id="3c5a1-297">Microsoft Teams의 클라우드 음성 기능에 대한 네트워크 설정 - 개념 및 용어</span><span class="sxs-lookup"><span data-stu-id="3c5a1-297">Network settings for cloud voice features in Microsoft Teams - Concepts and terminology</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="3c5a1-298">Microsoft Teams에서 클라우드 음성 기능에 대한 네트워크 토폴로지 관리</span><span class="sxs-lookup"><span data-stu-id="3c5a1-298">Manage your network topology for cloud voice features in Microsoft Teams</span></span>](manage-your-network-topology.md)

## <a name="migrate-your-existing-voice-solution-to-teams"></a><span data-ttu-id="3c5a1-299">기존 음성 솔루션을 Teams로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="3c5a1-299">Migrate your existing voice solution to Teams</span></span>

<span data-ttu-id="3c5a1-300">Teams로 업그레이드하는 조직의 경우 궁극적인 목표는 모든 사용자를 TeamsOnly 모드로 이동하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-300">For an organization that is upgrading to Teams, the ultimate goal is to move all users to TeamsOnly mode.</span></span> <span data-ttu-id="3c5a1-301">Teams와 전화 시스템 사용은 사용자가 TeamsOnly 모드일 때만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-301">Using Phone System with Teams is only supported when the user is in TeamsOnly mode.</span></span> <span data-ttu-id="3c5a1-302">Teams로 업그레이드하는 데 대한 기본 정보가 필요한 경우 여기에서 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-302">If you need basic information about upgrading to Teams, start here:</span></span>

- [<span data-ttu-id="3c5a1-303">Microsoft Teams 업그레이드 시작하기</span><span class="sxs-lookup"><span data-stu-id="3c5a1-303">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="3c5a1-304">업그레이드 프레임워크 정보</span><span class="sxs-lookup"><span data-stu-id="3c5a1-304">About the upgrade framework</span></span>](upgrade-framework.md)
- [<span data-ttu-id="3c5a1-305">IT 관리자를 위한 업그레이드 전략</span><span class="sxs-lookup"><span data-stu-id="3c5a1-305">Upgrade strategies for IT administrators</span></span>](upgrade-to-teams-on-prem-implement.md)

<span data-ttu-id="3c5a1-306">음성 솔루션을 마이그레이션할 때 TeamsOnly 모드로 전환할 때 다음과 같은 4개의 가능한 호출 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-306">When migrating your voice solution, there are four possible calling scenarios when moving to TeamsOnly mode:</span></span>

- <span data-ttu-id="3c5a1-307">Microsoft 통화 계획이 있는 [**비즈니스용 Skype Online의 사용자입니다.**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="3c5a1-307">[**A user in Skype for Business Online, with a Microsoft Calling Plan**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).</span></span> <span data-ttu-id="3c5a1-308">업그레이드 시 이 사용자는 Microsoft 통화 계획을 계속 하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-308">Upon upgrade, this user will continue to have a Microsoft Calling Plan.</span></span>

- <span data-ttu-id="3c5a1-309">**[비즈니스용 Skype Online의 사용자로,](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)** 비즈니스용 Skype-프레미스 또는 클라우드 커넥터 버전 을 통해 프레미스 음성 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-309">**[A user in Skype for Business Online, with on-premises voice functionality](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice) through Skype for Business on-premises or Cloud Connector Edition**.</span></span> <span data-ttu-id="3c5a1-310">Teams로의 사용자의 업그레이드는 TeamsOnly 사용자에게 PSTN 기능을 보장하기 위해 사용자를 직접 라우팅으로 마이그레이션하는 방법을 조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-310">The user’s upgrade to Teams needs to be coordinated with migration of the user to Direct Routing to ensure the TeamsOnly user has PSTN functionality.</span></span>

- <span data-ttu-id="3c5a1-311">온라인으로 이동하고 Enterprise Voice PSTN 연결을 유지하는 비즈니스용 **[Skype온-프레미스](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)** 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-311">**[A user in Skype for Business on-premises with Enterprise Voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), who will be moving to online and keeping on-premises PSTN connectivity**.</span></span> <span data-ttu-id="3c5a1-312">이 사용자를 Teams로 마이그레이션하려면 사용자의 비즈니스용 Skype 계정을 클라우드로 이동하고, 사용자의 마이그레이션을 통해 직접 라우팅으로 이동하는 조정이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-312">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with migration of the user to Direct Routing.</span></span> 

- <span data-ttu-id="3c5a1-313">**[비즈니스용 Skype온-Enterprise Voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)사용자가** 온라인으로 이동하고 Microsoft 통화 요금제 를 사용할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-313">**[A user in Skype for Business on-premises with Enterprise Voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), who will be moving to online and using a Microsoft Calling plan**.</span></span>  <span data-ttu-id="3c5a1-314">이 사용자를 Teams로 마이그레이션하려면 사용자의 비즈니스용 Skype 계정을 클라우드로 이동하고 A) 해당 사용자의 전화 번호 포트를 Microsoft 통화 계획 또는 B로 이동하도록 조정해야 합니다. 사용 가능한 지역에서 새 구독자 번호를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-314">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with either A) the port of that user’s phone number to a Microsoft Calling Plan or B) assigning a new subscriber number from available regions.</span></span>

<span data-ttu-id="3c5a1-315">하이브리드 연결을 설정해야 하는 경우와 직접 라우팅으로 사용자를 마이그레이션하는 방법에 대한 정보를 포함하여 이러한 각 시나리오에 대한 음성 마이그레이션을 구현하는 방법에 대한 자세한 내용은 다음 문서를 &mdash; &mdash; 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-315">For more information about how to implement your voice migration for each of these scenarios&mdash;including information about when you need to set up hybrid connectivity and how to migrate users with on-premises voice functionality to Direct Routing&mdash;see the following articles:</span></span>

- [<span data-ttu-id="3c5a1-316">IT 관리자를 위해 Teams로 업그레이드할 때 PSTN 고려 사항</span><span class="sxs-lookup"><span data-stu-id="3c5a1-316">PSTN considerations when upgrading to Teams — for IT administrators</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

- [<span data-ttu-id="3c5a1-317">Contoso 음성 마이그레이션 사례 연구</span><span class="sxs-lookup"><span data-stu-id="3c5a1-317">Contoso voice migration case study</span></span>](voice-case-study-overview.md)<br>
  <span data-ttu-id="3c5a1-318">사례 연구에서는 다국적 기업인 Contoso가 조직에 대해 Teams 음성 솔루션을 구현하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-318">The case study describes how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span> <span data-ttu-id="3c5a1-319">이 문서에는 다음 문서가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5a1-319">It contains the following articles:</span></span>

  - [<span data-ttu-id="3c5a1-320">팀 업그레이드 계획</span><span class="sxs-lookup"><span data-stu-id="3c5a1-320">Teams upgrade plan</span></span>](voice-case-study-migration-plan.md)
  - [<span data-ttu-id="3c5a1-321">전화 시스템 및 PSTN 연결 옵션</span><span class="sxs-lookup"><span data-stu-id="3c5a1-321">Phone System and PSTN connectivity options</span></span>](voice-case-study-phone-system.md)
  - [<span data-ttu-id="3c5a1-322">위치 기반 라우팅 구현</span><span class="sxs-lookup"><span data-stu-id="3c5a1-322">Location-Based Routing implementation</span></span>](voice-case-study-location-based-routing.md)
  - [<span data-ttu-id="3c5a1-323">긴급 통화</span><span class="sxs-lookup"><span data-stu-id="3c5a1-323">Emergency calling</span></span>](voice-case-study-emergency-calling.md)
  - [<span data-ttu-id="3c5a1-324">자동 전화 교환 및 통화 큐</span><span class="sxs-lookup"><span data-stu-id="3c5a1-324">Auto attendants and call queues</span></span>](voice-case-study-call-queues.md)
  - [<span data-ttu-id="3c5a1-325">오디오 회의</span><span class="sxs-lookup"><span data-stu-id="3c5a1-325">Audio Conferencing</span></span>](voice-case-study-audio-conferencing.md)












