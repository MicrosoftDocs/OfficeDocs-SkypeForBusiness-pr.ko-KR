---
title: PSTN 연결 옵션
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 07/08/2021
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
description: PSTN Teams(PSTN 연결) 옵션 및 조직에 대해 결정해야 하는 결정에 대해 자세히 알아보습니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b1b06178b269529b1d0227ff02d529c91ba1480
ms.sourcegitcommit: 5720fa12bdabdfc2988bf835c8cf95e4d64fa54e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "53354524"
---
# <a name="pstn-connectivity-options"></a><span data-ttu-id="4bbe1-103">PSTN 연결 옵션</span><span class="sxs-lookup"><span data-stu-id="4bbe1-103">PSTN connectivity options</span></span>

<span data-ttu-id="4bbe1-104">Microsoft는 조직에 대한 PBX(Exchange)의 완전한 개인 분기 전화 시스템.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-104">Microsoft provides complete Private Branch Exchange (PBX) capabilities for your organization through Phone System.</span></span> <span data-ttu-id="4bbe1-105">그러나 사용자가 조직 외부에서 전화를 걸 수 있도록 설정하려면 PSTN(공용 전화 시스템 전화 네트워크)에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-105">However, to enable users to make calls outside your organization, you need to connect Phone System to the Public Switched Telephone Network (PSTN).</span></span>

<span data-ttu-id="4bbe1-106">이 문서에서는 PSTN 연결 옵션에 중점을</span><span class="sxs-lookup"><span data-stu-id="4bbe1-106">This article focuses on PSTN connectivity options.</span></span> <span data-ttu-id="4bbe1-107">Microsoft 음성 솔루션에 대한 자세한 내용은 음성 솔루션의 전화 시스템 세부 정보를 Teams [참조하세요.](cloud-voice-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="4bbe1-107">For more information about Microsoft voice solutions, incuding details about Phone System features, see [Plan your Teams voice solution](cloud-voice-landing-page.md).</span></span>

<span data-ttu-id="4bbe1-108">PSTN에 전화 시스템 다음 옵션에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-108">To connect Phone System to the PSTN, you can choose from the following options:</span></span>

- <span data-ttu-id="4bbe1-109">[**요금제 호출 입니다.**](#phone-system-with-calling-plan)</span><span class="sxs-lookup"><span data-stu-id="4bbe1-109">[**Calling Plan**](#phone-system-with-calling-plan).</span></span> <span data-ttu-id="4bbe1-110">PSTN 통신사로 Microsoft를 사용할 수 있는 올인원 클라우드 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-110">An all-in-the-cloud solution with Microsoft as your PSTN carrier.</span></span>

- <span data-ttu-id="4bbe1-111">[**SBC(세션**](#phone-system-with-direct-routing)테두리 컨트롤러)를 연결하여 사용자 자신의 PSTN 캐리어를 사용할 수 있는 직접 라우팅을 전화 시스템.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-111">[**Direct Routing**](#phone-system-with-direct-routing), which enables you to use your own PSTN carrier by connecting your Session Border Controller(s) (SBC) to Phone System.</span></span>

- <span data-ttu-id="4bbe1-112">[**연산자 커넥트**](#phone-system-with-operator-connect)현재 공개 미리 보기에서만 사용할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="4bbe1-112">[**Operator Connect**](#phone-system-with-operator-connect), which is currently available only in **public preview.**</span></span>  <span data-ttu-id="4bbe1-113">연산자 커넥트 경우 기존 통신사가 Microsoft 연산자 커넥트 프로그램에 참여하는 경우 PSTN 호출 및 SBC(세션 테두리 컨트롤러)를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-113">With Operator Connect, if your existing carrier is a participant in the Microsoft Operator Connect program, they can manage PSTN calling and Session Border Controllers (SBCs).</span></span> 

<span data-ttu-id="4bbe1-114">복잡한 환경에 대한 솔루션을 디자인하거나 다단계 마이그레이션을 관리할 수 있는 옵션 조합을 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-114">You can also choose a combination of options, which enables you to design a solution for a complex environment, or manage a multi-step migration.</span></span>

<span data-ttu-id="4bbe1-115">선택한 옵션 또는 옵션은 일부 기능 구성 방식에 전화 시스템 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-115">Be aware that the option or options you choose affect how some Phone System features are configured.</span></span> <span data-ttu-id="4bbe1-116">자세한 내용은 이 문서의 나중에 [구성](#configuration-considerations) 고려 사항을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-116">For more information, see [Configuration considerations](#configuration-considerations) later in this article.</span></span>


## <a name="phone-system-with-calling-plan"></a><span data-ttu-id="4bbe1-117">전화 시스템 계획과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-117">Phone System with Calling Plan</span></span> 

<span data-ttu-id="4bbe1-118">전화 시스템 요금제는 Microsoft의 모든 클라우드 음성 솔루션으로 사용자에 Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-118">Phone System with Calling Plan is Microsoft's all-in-the-cloud voice solution for Teams users.</span></span> <span data-ttu-id="4bbe1-119">이 옵션은 PSTN에 전화 시스템 가장 간단한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-119">This is the simplest option that connects Phone System to the PSTN.</span></span> <span data-ttu-id="4bbe1-120">이 옵션을 사용하면 다음 다이어그램과 같이 Microsoft는 PSTN 통신 사업자 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-120">With this option, Microsoft acts as your PSTN carrier, as shown in the following diagram:</span></span>

![다이어그램 1은 전화 시스템 계획과 함께 표시](media/voice-solutions-simple.png)

<span data-ttu-id="4bbe1-122">다음에 대한 예에 대답하면 전화 시스템 계획이 적합한 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-122">If you answer yes to the following, then Phone System with Calling Plan is the right solution for you:</span></span>

- <span data-ttu-id="4bbe1-123">통화 요금제는 지역에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-123">Calling Plan is available in your region.</span></span>
- <span data-ttu-id="4bbe1-124">현재 PSTN 캐리어를 유지할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-124">You do not need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="4bbe1-125">PSTN에 대한 Microsoft 관리 액세스를 사용하려는 경우</span><span class="sxs-lookup"><span data-stu-id="4bbe1-125">You want to use Microsoft-managed access to the PSTN.</span></span>

<span data-ttu-id="4bbe1-126">이 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-126">With this option:</span></span> 

- <span data-ttu-id="4bbe1-127">전 세계 Microsoft 전화 전화로 전화를 걸 수 있는 추가된 국내 또는 국제 통화 요금제가 있는 시스템(라이선스가 부여되는 서비스 수준에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-127">You get Microsoft Phone System with added Domestic or International Calling Plans that enable calling to phones around the world (depending on the level of service being licensed).</span></span>

- <span data-ttu-id="4bbe1-128">호출 계획이 프레미스에서 작동하기 때문에 프레미스 배포의 배포 또는 유지 관리가 &mdash; Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-128">You do not require deployment or maintenance of an on-premises deployment&mdash;because Calling Plan operates out of Microsoft 365.</span></span>

- <span data-ttu-id="4bbe1-129">참고: 필요한 경우 SBC에서 지원하는 타사 PBX, 아날로그 디바이스 및 기타 타사 전화 통신 장비와 상호 연동성을 위해 직접 라우팅을 통해 지원되는 SBC(세션 경계 컨트롤러)를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-129">Note: If necessary, you can choose to connect a supported Session Border Controller (SBC) through Direct Routing for interoperability with third-party PBXs, analog devices, and other third-party telephony equipment supported by the SBC.</span></span>

<span data-ttu-id="4bbe1-130">이 옵션을 사용하려면 연결에 끊기지 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-130">This option requires uninterrupted connection to Microsoft 365.</span></span>

<span data-ttu-id="4bbe1-131">통화 계획에 대한 자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-131">For more information about Calling Plan, see the following articles:</span></span>

- [<span data-ttu-id="4bbe1-132">사용자에게 적합한 통화 플랜은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="4bbe1-132">Which Calling Plan is right for you?</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="4bbe1-133">통화 플랜을 구입하는 방법</span><span class="sxs-lookup"><span data-stu-id="4bbe1-133">How to buy a Calling Plan</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="4bbe1-134">통화 플랜의 국가 및 지역 가용성</span><span class="sxs-lookup"><span data-stu-id="4bbe1-134">Country and region availability for Calling Plan</span></span>](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [<span data-ttu-id="4bbe1-135">통화 계획 설정</span><span class="sxs-lookup"><span data-stu-id="4bbe1-135">Set up Calling Plan</span></span>](set-up-calling-plans.md)


## <a name="phone-system-with-direct-routing"></a><span data-ttu-id="4bbe1-136">전화 시스템 라우팅을 통해 연결</span><span class="sxs-lookup"><span data-stu-id="4bbe1-136">Phone System with Direct Routing</span></span>

<span data-ttu-id="4bbe1-137">이 옵션은 전화 시스템 다이어그램과 같이 직접 라우팅을 사용하여 전화 통신 네트워크에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-137">This option connects Phone System to your telephony network by using Direct Routing, as shown in the following diagram:</span></span> 

![다이어그램 5에서는 직접 전화 시스템 사용하여 전화 시스템 표시](media/voice-solution-with-direct-routing.png)

<span data-ttu-id="4bbe1-139">다음 질문에 예로 대답하면 직접 전화 시스템 올바른 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-139">If you answer yes to the following questions, then Phone System with Direct Routing is the right solution for you:</span></span>

- <span data-ttu-id="4bbe1-140">사용자와 함께 Teams 전화 시스템.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-140">You want to use Teams with Phone System.</span></span>
- <span data-ttu-id="4bbe1-141">현재 PSTN 캐리어를 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-141">You need to retain your current PSTN carrier.</span></span>
- <span data-ttu-id="4bbe1-142">라우팅을 혼합하고, 일부 호출은 통신사를 통해 통화 계획을 통해 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-142">You want to mix routing, with some calls going through Calling Plan, some through your carrier.</span></span>
- <span data-ttu-id="4bbe1-143">타사 PBX 및/또는 오버헤드 페이지, 아날로그 디바이스 등의 장비와 상호 협력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-143">You need to interoperate with third-party PBXs and/or equipment such us overhead pagers, analog devices, and so on.</span></span>

<span data-ttu-id="4bbe1-144">이 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-144">With this option:</span></span>

- <span data-ttu-id="4bbe1-145">추가 프레미스 소프트웨어 없이도 지원되는 SBC(세션 전화 시스템 컨트롤러)를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-145">You connect your own supported Session Border Controller (SBC) to Phone System without the need for additional on-premises software.</span></span>

- <span data-ttu-id="4bbe1-146">가상으로 모든 전화 통신 통신을 사용할 수 전화 시스템.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-146">You can use virtually any telephony carrier with Phone System.</span></span>

- <span data-ttu-id="4bbe1-147">이 옵션을 구성하고 관리하도록 선택하거나 이동통신사 또는 파트너가 구성하고 관리할 수 있습니다(이동통신사 또는 파트너가 이 옵션을 제공하는지 묻는 질문).</span><span class="sxs-lookup"><span data-stu-id="4bbe1-147">You can choose to configure and manage this option, or it can be configured and managed by your carrier or partner (ask if your carrier or partner provides this option).</span></span>

- <span data-ttu-id="4bbe1-148">타사 PBX와 아날로그 디바이스와 같은 전화 통신 장비와 아날로그 장치 간에 상호 &mdash; &mdash; 전화 시스템.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-148">You can configure interoperability between your telephony equipment&mdash;such as a third-party PBX and analog devices&mdash;and Phone System.</span></span>

<span data-ttu-id="4bbe1-149">이 옵션에는 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-149">This option requires the following:</span></span>

- <span data-ttu-id="4bbe1-150">연결에 대한 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-150">Uninterrupted connection to Microsoft 365.</span></span>

- <span data-ttu-id="4bbe1-151">지원되는 SBC를 배포하고 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-151">Deploying and maintaining a supported SBC.</span></span>

- <span data-ttu-id="4bbe1-152">타사 통신사와의 계약입니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-152">A contract with a third-party carrier.</span></span>
  <span data-ttu-id="4bbe1-153">(타사 PBX, 아날로그 디바이스 또는 기타 전화 통신 장비에 대한 연결을 제공하는 옵션으로 배포되지 않는 한, 통화 계획에 전화 시스템 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="4bbe1-153">(Unless deployed as an option to provide connection to third-party PBX, analog devices, or other telephony equipment for users who are on Phone System with Calling Plan.)</span></span>

<span data-ttu-id="4bbe1-154">직접 라우팅에 대한 자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-154">For more information about Direct Routing, see the following articles:</span></span>

- [<span data-ttu-id="4bbe1-155">직접 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="4bbe1-155">Plan Direct Routing</span></span>](direct-routing-plan.md)
- [<span data-ttu-id="4bbe1-156">직접 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="4bbe1-156">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="4bbe1-157">직접 라우팅에서 사용할 음성 라우팅 정책 관리</span><span class="sxs-lookup"><span data-stu-id="4bbe1-157">Manage voice routing policies for use with Direct Routing</span></span>](manage-voice-routing-policies.md)
- [<span data-ttu-id="4bbe1-158">직접 라우팅으로 전달되는 위치 기반 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="4bbe1-158">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="4bbe1-159">직접 라우팅으로 인증된 SBC(Session Border Controller) 목록</span><span class="sxs-lookup"><span data-stu-id="4bbe1-159">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)


## <a name="phone-system-with-operator-connect"></a><span data-ttu-id="4bbe1-160">전화 시스템 커넥트</span><span class="sxs-lookup"><span data-stu-id="4bbe1-160">Phone System with Operator Connect</span></span>

<span data-ttu-id="4bbe1-161">연산자 커넥트 현재 공개 미리 보기에서 기존 통신업체가 Microsoft Operator 커넥트 프로그램에 참여하는 경우 PSTN 호출을 사용자에 가져오기 위한 서비스를 관리할 수 Teams.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-161">With Operator Connect, currently in public preview, if your existing carrier is a participant in the Microsoft Operator Connect program, they can manage the service for bringing PSTN calling to Teams.</span></span> <span data-ttu-id="4bbe1-162">통신사는 PSTN 호출 서비스 및 SBC(세션 테두리 컨트롤러)를 관리하므로 하드웨어 구매 및 관리를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-162">Your carrier manages the PSTN calling services and Session Border Controllers (SBCs), allowing you to save on hardware purchase and management.</span></span>

<span data-ttu-id="4bbe1-163">운영자는 커넥트 경우 조직에 적합한 솔루션일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-163">Operator Connect might be the right solution for your organization if:</span></span>

- <span data-ttu-id="4bbe1-164">Microsoft 통화 요금제는 지리적 위치에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-164">Microsoft Calling Plan isn't available in your geographic location.</span></span>
- <span data-ttu-id="4bbe1-165">선호하는 통신사는 Microsoft Operator 커넥트 참여자입니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-165">Your preferred carrier is a participant in the Microsoft Operator Connect program.</span></span>
- <span data-ttu-id="4bbe1-166">새 통신사에서 통화를 사용하도록 설정하려는 Teams.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-166">You want to find a new carrier to enable calling in Teams.</span></span>

<span data-ttu-id="4bbe1-167">운영자의 혜택 및 요구 사항에 대한 커넥트 이 프로그램에 참여하는 항공사 목록에 대한 자세한 내용은 [요금제 운영자](operator-connect-plan.md)커넥트.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-167">For information on the benefits and requirements of Operator Connect, and for a list of carriers participating in this program, see [Plan Operator Connect](operator-connect-plan.md).</span></span> <span data-ttu-id="4bbe1-168">연산자를 구성하는 방법에 대한 자세한 내용은 연산자 커넥트 [구성을 커넥트.](operator-connect-configure.md)</span><span class="sxs-lookup"><span data-stu-id="4bbe1-168">For information on how to configure Operator Connect, see [Configure Operator Connect](operator-connect-configure.md).</span></span>

## <a name="configuration-considerations"></a><span data-ttu-id="4bbe1-169">구성 고려 사항</span><span class="sxs-lookup"><span data-stu-id="4bbe1-169">Configuration considerations</span></span>

<span data-ttu-id="4bbe1-170">대부분의 전화 시스템 기능은 선택한 PSTN 연결 옵션에 관계없이 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-170">Most Phone System features are the same regardless of the PSTN connectivity option you choose.</span></span> <span data-ttu-id="4bbe1-171">예를 들어 통화가 지원되지 않는 및 전달 설정, 통화 전송, 사용자 지정 음악 보류, 통화 공원, 공유 줄 및 음성 앱을 모두 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-171">For example, call unanswered and forwarding settings, call transfer, custom music on hold, call park, shared line, and voice apps are all available.</span></span> <span data-ttu-id="4bbe1-172">전체 기능 목록은 전화 시스템 [전화 시스템](here-s-what-you-get-with-phone-system.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-172">For a complete list of Phone System features, see [Here's what you get with Phone System](here-s-what-you-get-with-phone-system.md).</span></span>

<span data-ttu-id="4bbe1-173">그러나 기능에는 몇 가지 차이점이 있습니다. 그러나 특정 기능을 구성하는 방법에 전화 시스템 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-173">There are some differences in functionality, however, that affect how you configure certain Phone System features.</span></span> <span data-ttu-id="4bbe1-174">예를 들어 직접 라우팅에는 호출 라우팅을 구성하는 추가 단계가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-174">For example, Direct Routing requires additional steps to configure call routing.</span></span> <span data-ttu-id="4bbe1-175">또 다른 예로, 직접 라우팅은 LBR(Location-Based-Routing)을 제공하여 허용되지 않는 특정 지리적 위치에서 무료 우회를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-175">As another example, Direct Routing provides Location-Based-Routing (LBR)--so that you can restrict toll bypass in certain geographic locations where it is not allowed.</span></span> 


### <a name="phone-number-management"></a><span data-ttu-id="4bbe1-176">전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="4bbe1-176">Phone number management</span></span>

<span data-ttu-id="4bbe1-177">Microsoft에는 구독자(사용자) 번호와 조직의 사용자에게 할당할 수 있는 전화 번호와 무료 서비스 번호로 사용할 수 있는 서비스 번호의 두 가지 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-177">Microsoft has two types of telephone numbers available: subscriber (user) numbers, which can be assigned to users in your organization, and service numbers, available as toll and toll-free service numbers.</span></span> <span data-ttu-id="4bbe1-178">서비스 번호는 구독자 번호보다 동시 호출 용량이 높고 오디오 회의, 자동 참석자 또는 통화 큐와 같은 서비스에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-178">Service numbers have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

<span data-ttu-id="4bbe1-179">다음을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-179">You will need to decide:</span></span>

- <span data-ttu-id="4bbe1-180">Microsoft에서 새 전화 번호가 필요한 사용자 위치는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="4bbe1-180">Which user locations need new phone numbers from Microsoft?</span></span>
- <span data-ttu-id="4bbe1-181">어떤 유형의 전화 번호(구독자 또는 서비스)가 필요한가요?</span><span class="sxs-lookup"><span data-stu-id="4bbe1-181">Which type of telephone number (subscriber or service) do I need?</span></span>
- <span data-ttu-id="4bbe1-182">기존 전화 번호를 이식하기 위해 어떻게 Teams?</span><span class="sxs-lookup"><span data-stu-id="4bbe1-182">How do I port existing phone numbers to Teams?</span></span>

<span data-ttu-id="4bbe1-183">전화 번호를 획득하고 관리하는 방법은 PSTN 연결 옵션에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-183">How you acquire and manage phone numbers differs depending on your PSTN connectivity option.</span></span>

- <span data-ttu-id="4bbe1-184">전화 요금제에 대한 전화 번호 관리에 대한 자세한 내용은 조직의 전화 번호 [관리를 참조하세요.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="4bbe1-184">For information about managing phone numbers for Calling Plan, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

- <span data-ttu-id="4bbe1-185">직접 라우팅에 대한 전화 번호 관리에 대한 자세한 내용은 전화 번호 구성 및 엔터프라이즈 음성 및 음성 을 사용하도록 설정 을 [참조하세요.](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online)</span><span class="sxs-lookup"><span data-stu-id="4bbe1-185">For information about managing phone numbers for Direct Routing, see [Configure the phone number and enable enterprise voice and voicemail](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online).</span></span>

- <span data-ttu-id="4bbe1-186">연산자를 통해 전화 번호 관리에 대한 자세한 내용은 커넥트 로 전화 번호 설정 을 [커넥트.](operator-connect-configure.md#set-up-phone-numbers)</span><span class="sxs-lookup"><span data-stu-id="4bbe1-186">For information about managing phone numbers with Operator Connect, see [Set up phone numbers with Operator Connect](operator-connect-configure.md#set-up-phone-numbers).</span></span>


### <a name="call-routing-and-dial-plans"></a><span data-ttu-id="4bbe1-187">통화 라우팅 및 전화 걸기 계획</span><span class="sxs-lookup"><span data-stu-id="4bbe1-187">Call routing and dial plans</span></span>

<span data-ttu-id="4bbe1-188">호출 라우팅을 구성하는 방법은 PSTN 연결 옵션에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-188">How you configure call routing differs depending on your PSTN connectivity option.</span></span>  

- <span data-ttu-id="4bbe1-189">호출 요금제의 경우 대부분의 통화 라우팅은 Microsoft Calling Plan 인프라에서 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-189">For Calling Plans, most of call routing is handled by the Microsoft Calling Plan infrastructure.</span></span> <span data-ttu-id="4bbe1-190">통화 권한 부여 및 통화 라우팅을 위해 번호 변환을 위해 사용자 다이얼 계획을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-190">You configure user dial plans for purposes of number translation for call authorization and call routing.</span></span> <span data-ttu-id="4bbe1-191">자세한 내용은 전화 [요금제란?](what-are-dial-plans.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-191">For more information, see [What are dial plans?](what-are-dial-plans.md).</span></span>

- <span data-ttu-id="4bbe1-192">직접 라우팅의 경우 음성 경로를 지정하고 사용자에게 음성 라우팅 정책을 할당하여 통화 라우팅을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-192">For Direct Routing, you must configure call routing by specifying the voice routes and assigning voice routing policies to users.</span></span> <span data-ttu-id="4bbe1-193">SBC(Session Border Controller)와의 상호 연동성을 보장하기 위해 트렁크 수준에서 번호 변환을 위한 다이얼 플랜을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-193">You can configure dial plans for number translation at the trunk level to ensure interoperability with Session Border Controllers (SBCs).</span></span> <span data-ttu-id="4bbe1-194">자세한 내용은 [직접](direct-routing-voice-routing.md)라우팅에 대한 음성 라우팅 [구성,](manage-voice-routing-policies.md) 음성 라우팅 정책 관리 및 전화 [번호 번역을 참조하세요.](direct-routing-translate-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="4bbe1-194">For more information, see [Configure voice routing for Direct Routing](direct-routing-voice-routing.md), [Manage voice routing policies](manage-voice-routing-policies.md) and [Translate phone numbers](direct-routing-translate-numbers.md).</span></span> 

- <span data-ttu-id="4bbe1-195">연산자 커넥트 대부분의 호출 라우팅은 통신사가 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-195">For Operator Connect, most of call routing is managed by the carrier.</span></span>  <span data-ttu-id="4bbe1-196">통화 권한 부여 및 통화 라우팅을 위해 번호 변환을 위해 사용자 다이얼 계획을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-196">You configure user dial plans for purposes of number translation for call authorization and call routing.</span></span> <span data-ttu-id="4bbe1-197">자세한 내용은 전화 [요금제란?](what-are-dial-plans.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-197">For more information, see [What are dial plans?](what-are-dial-plans.md).</span></span>


### <a name="location-based-routing-for-direct-routing"></a><span data-ttu-id="4bbe1-198">Location-Based 라우팅에 대한 Location-Based 라우팅</span><span class="sxs-lookup"><span data-stu-id="4bbe1-198">Location-Based Routing for Direct Routing</span></span>

<span data-ttu-id="4bbe1-199">일부 국가 및 지역에서는 PSTN 통신업체를 우회하여 장거리 통화 비용을 절감하는 것이 불법입니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-199">In some countries and regions, it's illegal to bypass the PSTN carrier to decrease long-distance calling costs.</span></span> <span data-ttu-id="4bbe1-200">Location-Based LBR(직접 라우팅)을 사용하면 해당 지리적 위치에 따라 사용자에 대한 Teams 우회를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-200">Location-Based Routing (LBR) for Direct Routing enables you to restrict toll bypass for Teams users based on their geographic location.</span></span> <span data-ttu-id="4bbe1-201">LBR을 계획하고 구성하는 방법에 대한 자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-201">For more information about how to plan and configure LBR, see the following articles:</span></span>

- [<span data-ttu-id="4bbe1-202">직접 라우팅으로 전달되는 위치 기반 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="4bbe1-202">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="4bbe1-203">위치 기반 라우팅의 네트워크 설정 구성</span><span class="sxs-lookup"><span data-stu-id="4bbe1-203">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="4bbe1-204">직접 라우팅에 위치 기반 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="4bbe1-204">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)
- [<span data-ttu-id="4bbe1-205">Contoso 사례 연구: Location-Based 라우팅</span><span class="sxs-lookup"><span data-stu-id="4bbe1-205">Contoso case study: Location-Based Routing</span></span>](voice-case-study-location-based-routing.md)<br>
  <span data-ttu-id="4bbe1-206">소설 다국적 기업인 Contoso가 조직에 대한 라우팅을 Location-Based 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-206">Describes how a fictional multi-national corporation, Contoso, implemented Location-Based Routing for their organization.</span></span>


### <a name="emergency-calling"></a><span data-ttu-id="4bbe1-207">비상 전화</span><span class="sxs-lookup"><span data-stu-id="4bbe1-207">Emergency calling</span></span>

<span data-ttu-id="4bbe1-208">긴급 호출을 구성하는 방법은 PSTN 연결 옵션에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-208">How you configure emergency calling differs depending on your PSTN connectivity option.</span></span>

- <span data-ttu-id="4bbe1-209">통화 요금제의 경우 각 사용자가 긴급 통화를 위해 자동으로 사용하도록 설정되며, 지정된 전화 번호와 연결된 등록된 긴급 주소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-209">For Calling Plan, each user is automatically enabled for emergency calling and is required to have a registered emergency address associated with their assigned telephone number.</span></span> <span data-ttu-id="4bbe1-210">동적 긴급 호출(클라이언트의 위치에 Teams)이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-210">Dynamic emergency calling (based on the location of the Teams client) is supported.</span></span>  

- <span data-ttu-id="4bbe1-211">직접 라우팅 Teams의 경우 긴급 통화 라우팅 정책(TeamsEmergencyCallRoutingPolicy)을 사용하여 긴급 번호 및 관련 라우팅 대상을 정의하여 사용자에 대한 긴급 호출 정책을 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-211">For Direct Routing, you must define emergency calling policies for users by using a Teams emergency call routing policy (TeamsEmergencyCallRoutingPolicy) to define emergency numbers and their associated routing destination.</span></span> <span data-ttu-id="4bbe1-212">등록된 긴급 위치는 직접 라우팅 사용자에 대해 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-212">Registered emergency locations are not supported for Direct Routing users.</span></span> <span data-ttu-id="4bbe1-213">동적 긴급 호출의 경우 긴급 통화 라우팅 및 파트너 연결에 대한 추가 구성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-213">For dynamic emergency calling, additional configuration is required for routing emergency calls and possibly for partner connectivity.</span></span>

- <span data-ttu-id="4bbe1-214">연산자 커넥트 경우 각 사용자가 긴급 통화를 위해 자동으로 사용하도록 설정되며, 등록된 긴급 주소가 할당된 전화 번호와 연결된 데 필요하지만 통신사 파트너에서만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-214">For Operator Connect, each user is automatically enabled for emergency calling and is required to have a registered emergency address associated with their assigned telephone number but can only be set by the carrier partner.</span></span> <span data-ttu-id="4bbe1-215">동적 긴급 호출(클라이언트의 위치에 Teams)이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-215">Dynamic emergency calling (based on the location of the Teams client) is supported.</span></span>

<span data-ttu-id="4bbe1-216">긴급 호출 개념 및 용어에 대한 자세한 내용 및 긴급 호출 및 동적 긴급 호출을 구성하는 방법에 대한 자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-216">For more information about emergency calling concepts and terminology, and how to configure emergency calling and dynamic emergency calling, see the following articles:</span></span>

- [<span data-ttu-id="4bbe1-217">긴급 통화 관리</span><span class="sxs-lookup"><span data-stu-id="4bbe1-217">Manage emergency calling</span></span>](what-are-emergency-locations-addresses-and-call-routing.md)
- [<span data-ttu-id="4bbe1-218">동적인 긴급 전화 계획 및 구성</span><span class="sxs-lookup"><span data-stu-id="4bbe1-218">Plan and configure dynamic emergency calling</span></span>](configure-dynamic-emergency-calling.md)
- [<span data-ttu-id="4bbe1-219">긴급 전화 정책 관리</span><span class="sxs-lookup"><span data-stu-id="4bbe1-219">Manage emergency calling policies</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="4bbe1-220">직접 라우팅에 대한 긴급 통화 라우팅 정책 관리</span><span class="sxs-lookup"><span data-stu-id="4bbe1-220">Manage emergency call routing policies for Direct Routing</span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="4bbe1-221">Contoso 사례 연구: 긴급 통화</span><span class="sxs-lookup"><span data-stu-id="4bbe1-221">Contoso case study: Emergency calling</span></span>](voice-case-study-emergency-calling.md)<br>
  <span data-ttu-id="4bbe1-222">소설적 다국적 기업 Contoso가 조직에 대한 긴급 호출을 구현하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-222">Describes how a fictional multi-national corporation, Contoso, implemented emergency calling for their organization.</span></span>


### <a name="network-topology-for-voice-features"></a><span data-ttu-id="4bbe1-223">음성 기능에 대한 네트워크 토폴로지</span><span class="sxs-lookup"><span data-stu-id="4bbe1-223">Network topology for voice features</span></span>

<span data-ttu-id="4bbe1-224">동적 긴급 통화를 배포하거나 직접 라우팅에 대한 Location-Based 라우팅을 배포하는 경우 이러한 기능을 사용할 네트워크 설정을 구성해야 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-224">If you are deploying dynamic emergency calling or Location-Based Routing for Direct Routing, you must configure network settings for use with these features in Microsoft Teams.</span></span> <span data-ttu-id="4bbe1-225">네트워크 지역, 네트워크 사이트, 네트워크 서브넷 및 신뢰할 수 있는 IP 주소에 대한 네트워크 설정을 구성하는 방법에 대한 자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4bbe1-225">To learn how to configure network settings for network regions, network sites, network subnets, and trusted IP addresses, see the following articles:</span></span>

- [<span data-ttu-id="4bbe1-226">클라우드의 클라우드 음성 기능에 대한 네트워크 Microsoft Teams - 개념 및 용어</span><span class="sxs-lookup"><span data-stu-id="4bbe1-226">Network settings for cloud voice features in Microsoft Teams - Concepts and terminology</span></span>](cloud-voice-network-settings.md)
- [<span data-ttu-id="4bbe1-227">클라우드 음성 기능에 대한 네트워크 토폴로지 관리 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4bbe1-227">Manage your network topology for cloud voice features in Microsoft Teams</span></span>](manage-your-network-topology.md)



