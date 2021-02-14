---
title: Teams 음성 Contoso 사례 연구
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
description: 다국적 기업에 대한 Teams 음성 사례 연구
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7431515d40550a3f731c34f97ed8c10586424901
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786099"
---
# <a name="contoso-case-study-phone-system"></a><span data-ttu-id="dcc0b-103">Contoso 사례 연구: 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="dcc0b-103">Contoso case study: Phone System</span></span>

<span data-ttu-id="dcc0b-104">지리적 위치 및 기타 요인에 따라 Contoso에는 다음 전화 통신 솔루션을 사용하는 사무실이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-104">Depending on geographic location and other factors, Contoso had offices using the following telephony solutions:</span></span>

- <span data-ttu-id="dcc0b-105">사이트 유형 A: 비즈니스용 Skype Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="dcc0b-105">Site Type A: Skype for Business Enterprise Voice</span></span>

- <span data-ttu-id="dcc0b-106">사이트 유형 B: 기존 레거시 전화 통신 시스템</span><span class="sxs-lookup"><span data-stu-id="dcc0b-106">Site Type B: Traditional legacy telephony systems</span></span>

- <span data-ttu-id="dcc0b-107">사이트 유형 C: 비즈니스용 Skype Enterprise Voice 기존 전화 통신 시스템 조합</span><span class="sxs-lookup"><span data-stu-id="dcc0b-107">Site Type C: A combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>


<span data-ttu-id="dcc0b-108">전체 조직에 대해 Microsoft Phone System 솔루션을 구현하기 위해 Contoso는 &mdash; PSTN(공용 전화망)에 연결하는 데 전화 시스템과 함께 사용할 다음 옵션 중 어떤 것이 사용되는지 각 사이트 유형에 대해 결정해야 합니다. &mdash;</span><span class="sxs-lookup"><span data-stu-id="dcc0b-108">To implement a Microsoft Phone System solution for their entire organization, Contoso had to determine&mdash;for each site type&mdash;which of the following options would be used with Phone System to connect to the Public Switched Telephone Network (PSTN):</span></span>

- <span data-ttu-id="dcc0b-109">통화 요금제가 있는 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="dcc0b-109">Phone System with Calling Plan</span></span> 

- <span data-ttu-id="dcc0b-110">직접 라우팅을 통해 자체 PSTN 통신업체가 있는 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="dcc0b-110">Phone System with own PSTN carrier through Direct Routing</span></span> 

- <span data-ttu-id="dcc0b-111">직접 라우팅을 통해 전화 시스템과 통화 요금제 및 전화 시스템 조합</span><span class="sxs-lookup"><span data-stu-id="dcc0b-111">Combination of Phone System with Calling Plan and Phone System with own PSTN carrier through Direct Routing</span></span>
 
<span data-ttu-id="dcc0b-112">Contoso는 조직에 적합한 솔루션을 결정하기 위해 Microsoft Teams에서 [Microsoft](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) 전화 통신 솔루션과 Ignite 2019 세션 [통화를 사용했습니다.](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions)</span><span class="sxs-lookup"><span data-stu-id="dcc0b-112">To determine the right solution for their organization, Contoso used [Microsoft telephony solutions](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) and the Ignite 2019 session [Calling in Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).</span></span>  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a><span data-ttu-id="dcc0b-113">사이트 유형 A: 비즈니스용 Skype Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="dcc0b-113">Site Type A: Skype for Business Enterprise Voice</span></span> 

<span data-ttu-id="dcc0b-114">Contoso 비즈니스용 Skype Enterprise Voice 허브 및 스포크로 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-114">Contoso Skype for Business Enterprise Voice was set up as a hub and spoke.</span></span> <span data-ttu-id="dcc0b-115">해당 지역에서 PSTN 게이트웨이를 유지 관리하는 중앙 위치가 있습니다. 이 지역에서 비즈니스용 Skype 사용자용 PSTN에 Enterprise Voice 위치가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-115">There was a central location that maintained the PSTN gateway in the region that provided the connection to the PSTN for the Skype for Business Enterprise Voice users in country.</span></span> <span data-ttu-id="dcc0b-116">종종 이러한 위성 사무실에는 자체 인터넷 수신이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-116">Often these satellite offices did not have their own Internet egress.</span></span> <span data-ttu-id="dcc0b-117">이러한 사용자의 번호는 기존 SBC에 연결하는 SIP 트렁크에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-117">The numbers for these users resided on the SIP trunk connecting to an existing SBC.</span></span> 

<span data-ttu-id="dcc0b-118">이미 배포된 SBC가 직접 라우팅 및 미디어 우회에 대해 인증되어 있는지 확인하기 위해 Contoso는 직접 라우팅에 대해 인증된 세션 테두리 컨트롤러 목록을 [확인했습니다.](direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="dcc0b-118">To determine if the SBC already deployed is certified for Direct Routing and Media Bypass, Contoso checked the [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>  

<span data-ttu-id="dcc0b-119">사용자의 전화 걸기 습관은 사용자가 피어 투 피어 오디오에 사용할 수 있는 비즈니스용 Skype 클라이언트가 있는 경우에도 확장을 사용하여 레거시 전화 통신 시스템에서 사용자를 전화하는 것이었다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-119">The user's dialing habits were to dial a user on the legacy telephony system using an extension, even when the user has a Skype for Business client available for peer-to-peer audio.</span></span> 

<span data-ttu-id="dcc0b-120">Contoso는 다음 질문에 대한 결정을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-120">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="dcc0b-121">Q.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-121">Q.</span></span> <span data-ttu-id="dcc0b-122">이 배포에서 제공하는 기능을 유지해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="dcc0b-122">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="dcc0b-123">A.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-123">A.</span></span> <span data-ttu-id="dcc0b-124">아니요</span><span class="sxs-lookup"><span data-stu-id="dcc0b-124">No</span></span> 

- <span data-ttu-id="dcc0b-125">Q.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-125">Q.</span></span> <span data-ttu-id="dcc0b-126">타사 PBX 시스템 및 기타 전화 통신 장비와 상호 협력해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="dcc0b-126">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br>
  <span data-ttu-id="dcc0b-127">A.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-127">A.</span></span> <span data-ttu-id="dcc0b-128">아니요</span><span class="sxs-lookup"><span data-stu-id="dcc0b-128">No</span></span> 

- <span data-ttu-id="dcc0b-129">Q.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-129">Q.</span></span> <span data-ttu-id="dcc0b-130">현재 타사 통신업체를 유지해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="dcc0b-130">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="dcc0b-131">A. 예(규제된 국가) 및 아니요</span><span class="sxs-lookup"><span data-stu-id="dcc0b-131">A. Yes (regulated countries) and No</span></span> 

- <span data-ttu-id="dcc0b-132">Q.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-132">Q.</span></span> <span data-ttu-id="dcc0b-133">배포된 SBC에서 ROI를 얻을 필요가 있나요?</span><span class="sxs-lookup"><span data-stu-id="dcc0b-133">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="dcc0b-134">A. 그렇기도 하고 그렇지 않기도 하고</span><span class="sxs-lookup"><span data-stu-id="dcc0b-134">A. Yes and No</span></span>  

- <span data-ttu-id="dcc0b-135">Q.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-135">Q.</span></span> <span data-ttu-id="dcc0b-136">이 지역에서 Microsoft PSTN 통화 플랜을 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="dcc0b-136">Is Microsoft PSTN Calling Plans available in this region?</span></span><br> <span data-ttu-id="dcc0b-137">A. 그렇기도 하고 그렇지 않기도 하고</span><span class="sxs-lookup"><span data-stu-id="dcc0b-137">A. Yes and No</span></span> 

<span data-ttu-id="dcc0b-138">Contoso는 질문에 대한 답변에 따라 다음을 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-138">Based on the answers to their questions, Contoso decided to:</span></span>

- <span data-ttu-id="dcc0b-139">통화 요금제가 있는 전화 시스템에서 PSTN 통화 계획을 사용할 수 있는 지역에 있는 사용자를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-139">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="dcc0b-140">PSTN 통화 요금제가 사용 가능한 지역에 있지 않은 사용자, SBC의 ROI가 아직 충족되지 않은 사이트에 있는 사용자, 직접 라우팅을 통해 전화 시스템에 전화 통신 규정이 있는 국가에 상주하는 사용자를 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-140">Move the users that are not located in a region where PSTN calling plans is available, users located in a site where the ROI on the SBCs have yet to be met, and users that resided in a country that has telephony regulations to Phone System with Direct Routing.</span></span> 

<span data-ttu-id="dcc0b-141">다음 다이어그램은 초기 비즈니스용 Skype Enterprise Voice 배포 및 이 배포가 Microsoft 통화 계획 및 직접 라우팅으로 마이그레이션된 방법을 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="dcc0b-141">The following diagram shows the initial Skype for Business Enterprise Voice deployment and how this deployment was migrated to both Microsoft Calling Plans and Direct Routing:</span></span>

![상태 전후를 보여주는 다이어그램](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a><span data-ttu-id="dcc0b-143">사이트 유형 B: 기존 레거시 전화 통신 시스템</span><span class="sxs-lookup"><span data-stu-id="dcc0b-143">Site Type B: Traditional legacy telephony systems</span></span>

<span data-ttu-id="dcc0b-144">Contoso에는 레거시 전화 통신 시스템을 활용하는 많은 사무실이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-144">Contoso had many offices that leveraged legacy telephony systems.</span></span> <span data-ttu-id="dcc0b-145">E1.64 전화 번호가 있는 사용자 하위 집합이 있는 반면 다른 사용자의 경우 내선 번호만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-145">There were a subset of users that had an E1.64 phone number while others only had an extension.</span></span> <span data-ttu-id="dcc0b-146">이러한 숫자는 PSTN 게이트웨이에 대한 TDM 트렁크에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-146">These numbers resided on the TDM trunk to the PSTN gateway.</span></span> <span data-ttu-id="dcc0b-147">사이트 내 전화 걸기에서는 내선 번호 앞에 사이트 코드를 사용하여 통화를 라우팅할 위치를 결정하여 구성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-147">Intra-site dialing was configured by leveraging a site code in front of the extension to determine where to route the call.</span></span> <span data-ttu-id="dcc0b-148">사용자의 전화 걸기 습관은 내선 번호로 전화를 걸기입니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-148">The users' dialing habits were to dial by extension.</span></span>   

<span data-ttu-id="dcc0b-149">Contoso는 다음 질문에 대한 결정을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-149">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="dcc0b-150">Q.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-150">Q.</span></span> <span data-ttu-id="dcc0b-151">이 배포에서 제공하는 기능을 유지해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="dcc0b-151">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="dcc0b-152">A.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-152">A.</span></span> <span data-ttu-id="dcc0b-153">아니요</span><span class="sxs-lookup"><span data-stu-id="dcc0b-153">No</span></span> 

- <span data-ttu-id="dcc0b-154">Q.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-154">Q.</span></span> <span data-ttu-id="dcc0b-155">타사 PBX 시스템 및 기타 전화 통신 장비와 상호 협력해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="dcc0b-155">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="dcc0b-156">A. 예</span><span class="sxs-lookup"><span data-stu-id="dcc0b-156">A. Yes</span></span>

- <span data-ttu-id="dcc0b-157">Q.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-157">Q.</span></span> <span data-ttu-id="dcc0b-158">현재 타사 통신업체를 유지해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="dcc0b-158">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="dcc0b-159">A. 아니요</span><span class="sxs-lookup"><span data-stu-id="dcc0b-159">A. No</span></span> 

- <span data-ttu-id="dcc0b-160">Q.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-160">Q.</span></span> <span data-ttu-id="dcc0b-161">Microsoft PSTN의 통화 요금제는 지역에서 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="dcc0b-161">Is Microsoft PSTN's Calling Plan available in our region?</span></span><br> <span data-ttu-id="dcc0b-162">A. 그렇기도 하고 그렇지 않기도 하고</span><span class="sxs-lookup"><span data-stu-id="dcc0b-162">A. Yes and No</span></span> 

<span data-ttu-id="dcc0b-163">Contoso는 질문에 대한 답변에 따라 다음을 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-163">Based on the answers to their questions, Contoso decided to:</span></span> 

- <span data-ttu-id="dcc0b-164">통화 요금제가 있는 전화 시스템에서 PSTN 통화 계획을 사용할 수 있는 지역에 있는 사용자를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-164">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="dcc0b-165">직접 라우팅을 통해 전화 시스템에서 PSTN 통화 계획을 사용할 수 있는 지역에 있지 않은 사용자를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-165">Move the users that are not located in a region where PSTN calling plans is available to Phone System with Direct Routing.</span></span> 

- <span data-ttu-id="dcc0b-166">중요 비즈니스용 아날로그 디바이스에 대한 PSTN 연결을 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-166">Maintain a PSTN connection to business critical analog devices.</span></span>

<span data-ttu-id="dcc0b-167">다음 다이어그램에서는 원격 사이트를 사용하는 원래 레거시 시스템 배포와 로컬 미디어 최적화를 사용하여 직접 라우팅 배포로 마이그레이션하는 방법을 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="dcc0b-167">The following diagrams show the original legacy system deployment with remote sites and the migration to a Direct Routing deployment with Local Media Optimization:</span></span>

<span data-ttu-id="dcc0b-168">**원래 레거시 배포**  
 ![ 상태 전후를 보여주는 다이어그램](media/voice-case-study-2.png)</span><span class="sxs-lookup"><span data-stu-id="dcc0b-168">**Original legacy deployment** 
![Diagram showing before and after states](media/voice-case-study-2.png)</span></span>


<span data-ttu-id="dcc0b-169">**직접 라우팅을 통해 배포**</span><span class="sxs-lookup"><span data-stu-id="dcc0b-169">**Deployment with Direct Routing**</span></span>

![상태 전후를 보여주는 다이어그램](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a><span data-ttu-id="dcc0b-171">사이트 유형 C: 비즈니스용 Skype Enterprise Voice 기존 전화 통신 시스템 조합</span><span class="sxs-lookup"><span data-stu-id="dcc0b-171">Site Type C: Combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>

<span data-ttu-id="dcc0b-172">Contoso 비즈니스용 Skype Enterprise Voice 사용자의 번호는 SIP 트렁크에 상주하여 통신 사업자로부터 SBC에 상주합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-172">Contoso Skype for Business Enterprise Voice users' numbers reside on the SIP trunk to the SBC from the carrier.</span></span> <span data-ttu-id="dcc0b-173">기존 전화 통신 시스템의 번호는 PSTN 게이트웨이에 대한 TDM 트렁크에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-173">The numbers for the traditional telephony systems resided on the TDM trunk to the PSTN gateway.</span></span>   

<span data-ttu-id="dcc0b-174">Contoso는 다음 질문에 대한 결정을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-174">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="dcc0b-175">Q.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-175">Q.</span></span> <span data-ttu-id="dcc0b-176">이 배포에서 제공하는 기능을 유지해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="dcc0b-176">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="dcc0b-177">A.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-177">A.</span></span> <span data-ttu-id="dcc0b-178">아니요</span><span class="sxs-lookup"><span data-stu-id="dcc0b-178">No</span></span> 

- <span data-ttu-id="dcc0b-179">Q.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-179">Q.</span></span> <span data-ttu-id="dcc0b-180">타사 PBX 시스템 및 기타 전화 통신 장비와 상호 협력해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="dcc0b-180">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="dcc0b-181">A. 아니요</span><span class="sxs-lookup"><span data-stu-id="dcc0b-181">A. No</span></span> 

- <span data-ttu-id="dcc0b-182">Q.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-182">Q.</span></span> <span data-ttu-id="dcc0b-183">현재 타사 통신업체를 유지해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="dcc0b-183">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="dcc0b-184">A. 아니요</span><span class="sxs-lookup"><span data-stu-id="dcc0b-184">A. No</span></span> 

- <span data-ttu-id="dcc0b-185">Q.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-185">Q.</span></span> <span data-ttu-id="dcc0b-186">배포된 SBC에서 ROI를 얻을 필요가 있나요?</span><span class="sxs-lookup"><span data-stu-id="dcc0b-186">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="dcc0b-187">A. 그렇기도 하고 그렇지 않기도 하고</span><span class="sxs-lookup"><span data-stu-id="dcc0b-187">A. Yes and No</span></span>  

- <span data-ttu-id="dcc0b-188">Q.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-188">Q.</span></span> <span data-ttu-id="dcc0b-189">이 지역에서 Microsoft의 PSTN 통화 플랜을 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="dcc0b-189">Is Microsoft's PSTN Calling Plan available in this region?</span></span><br> <span data-ttu-id="dcc0b-190">A. 아니요</span><span class="sxs-lookup"><span data-stu-id="dcc0b-190">A. No</span></span> 

<span data-ttu-id="dcc0b-191">Contoso는 질문에 대한 답변에 따라 다음을 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-191">Based on the answers to their questions, Contoso decided on the following:</span></span> 

- <span data-ttu-id="dcc0b-192">직접 라우팅에 사용할 레거시 전화 통신 사용자의 경우 Contoso는 TDM 트렁크에서 SBC의 SIP 트렁크로 번호를 포팅했습니다. SBC는 직접 라우팅에 대해 인증을 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-192">For the legacy telephony users that will be enabled for Direct Routing, Contoso ported the numbers from the TDM trunk to the SIP Trunk for the SBC, since the SBC is certified for Direct Routing.</span></span> 

- <span data-ttu-id="dcc0b-193">전화 시스템으로 이동하는 사용자의 하위 집합을 지원하고 레거시 시스템을 통해 계속 라우팅할 수 있도록 레거시 전화 통신 시스템이 SBC의 다음 홉으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-193">To support a subset of users moving to Phone System and to allow continued routing through the legacy system, the legacy telephony system was set up as the next hop to the SBC.</span></span>   

- <span data-ttu-id="dcc0b-194">또한 Contoso는 사용자 행동 변경을 장려하고 사이트 간 확장 전화 걸기에 대한 종속성 제거를 위해 모든 내부 통화에 Teams를 사용하기 위한 지침을 제공했습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-194">In addition, to encourage user behavior change and remove the dependency on inter- and intra-site extension dialing, Contoso provided guidance to use Teams for all internal calls.</span></span>  

<span data-ttu-id="dcc0b-195">다음 다이어그램은 원래 비즈니스용 Skype Enterprise Voice 및 레거시 전화 통신 시스템 배포와 직접 라우팅을 사용하여 혼합 배포로 마이그레이션하는 방법을 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="dcc0b-195">The following diagrams show the original Skype for Business Enterprise Voice and legacy telephony system deployment and the migration to a mixed deployment using Direct Routing:</span></span>

<span data-ttu-id="dcc0b-196">**원래 혼합 배포** 
 ![ 이전 상태를 보여주는 다이어그램](media/voice-case-study-4.png)</span><span class="sxs-lookup"><span data-stu-id="dcc0b-196">**Original mixed deployment**
![Diagram showing before state](media/voice-case-study-4.png)</span></span>

<span data-ttu-id="dcc0b-197">**직접 라우팅과 혼합 배포** 
 ![ 이전 상태를 보여주는 다이어그램](media/voice-case-study-4a.png)</span><span class="sxs-lookup"><span data-stu-id="dcc0b-197">**Mixed deployment with Direct Routing**
![Diagram showing before state](media/voice-case-study-4a.png)</span></span>


## <a name="calling-plans"></a><span data-ttu-id="dcc0b-198">통화 플랜</span><span class="sxs-lookup"><span data-stu-id="dcc0b-198">Calling Plans</span></span>

<span data-ttu-id="dcc0b-199">Contoso는 통화 계획에 대한 구성 요구 사항을 결정하기 위해 통화 계획 핵심 배포 [결정을 검토했습니다.](calling-plan-landing-page.md#core-deployment-decisions)</span><span class="sxs-lookup"><span data-stu-id="dcc0b-199">To determine the configuration requirements for Calling Plans, Contoso reviewed the [Calling Plan core deployment decisions](calling-plan-landing-page.md#core-deployment-decisions).</span></span> <span data-ttu-id="dcc0b-200">결과로 결정된 결정은 다음이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-200">The resulting decisions were made:</span></span> 

- <span data-ttu-id="dcc0b-201">Q.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-201">Q.</span></span> <span data-ttu-id="dcc0b-202">내 사용자에게 국제 통화가 필요한가요?</span><span class="sxs-lookup"><span data-stu-id="dcc0b-202">Do my users need international calling?</span></span><br> <span data-ttu-id="dcc0b-203">A. 예</span><span class="sxs-lookup"><span data-stu-id="dcc0b-203">A. Yes</span></span> 

- <span data-ttu-id="dcc0b-204">Q.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-204">Q.</span></span> <span data-ttu-id="dcc0b-205">내 사용자에게 각각 직접 전화 번호가 있나요?</span><span class="sxs-lookup"><span data-stu-id="dcc0b-205">Do my users each have a direct inward DID phone number?</span></span><br> <span data-ttu-id="dcc0b-206">A. 오늘은 아니요.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-206">A. Not today.</span></span> <span data-ttu-id="dcc0b-207">사용하도록 설정된 모든 사용자는 DID을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-207">All users enabled will receive a DID.</span></span> 

- <span data-ttu-id="dcc0b-208">Q.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-208">Q.</span></span> <span data-ttu-id="dcc0b-209">호출자 ID를 마스킹하거나 사용하지 않도록 설정하나요?</span><span class="sxs-lookup"><span data-stu-id="dcc0b-209">Do I want to mask or disable caller ID?</span></span><br> <span data-ttu-id="dcc0b-210">A. 사용자의 호출자 ID는 Contoso의 로컬 번호로 마스킹됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-210">A. The caller ID for a user will be masked to the local number for Contoso.</span></span> 


## <a name="direct-routing"></a><span data-ttu-id="dcc0b-211">직접 라우팅</span><span class="sxs-lookup"><span data-stu-id="dcc0b-211">Direct Routing</span></span>

<span data-ttu-id="dcc0b-212">Contoso는 전화 시스템 및 직접 라우팅에서 사용할 수 있는 기능을 포함하여 Office 365 기능을 최신으로 유지하기 위해 Ignite에 참석했습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-212">Contoso attended Ignite to stay current on Office 365 features including those available with Phone system and Direct Routing.</span></span> <span data-ttu-id="dcc0b-213">기술 리더와 설계자는 Ignite 2019 중에 제공된 지침을 사용하여 방향을 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-213">Technical leadership and architects used the guidance provided during the Ignite 2019 to determine their direction.</span></span>  <span data-ttu-id="dcc0b-214">사용된 키 세션:</span><span class="sxs-lookup"><span data-stu-id="dcc0b-214">Key sessions that were used:</span></span> 

- [<span data-ttu-id="dcc0b-215">Microsoft Teams 직접 라우팅의 성공 계획</span><span class="sxs-lookup"><span data-stu-id="dcc0b-215">Plan for success with Microsoft Teams Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [<span data-ttu-id="dcc0b-216">직접 라우팅에 대한 업데이트</span><span class="sxs-lookup"><span data-stu-id="dcc0b-216">Updates for Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a><span data-ttu-id="dcc0b-217">구성</span><span class="sxs-lookup"><span data-stu-id="dcc0b-217">Configuration</span></span>

### <a name="calling-plans-sites"></a><span data-ttu-id="dcc0b-218">요금제 사이트 호출</span><span class="sxs-lookup"><span data-stu-id="dcc0b-218">Calling Plans sites</span></span>

<span data-ttu-id="dcc0b-219">Contoso는 라이선스를 획득하고 사용자에게 전화 번호를 할당하기 위해 통화 계획 설정의 [단계를 수행했습니다.](set-up-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="dcc0b-219">To obtain licenses and assign phone numbers to users, Contoso followed the steps in [Set up Calling Plans](set-up-calling-plans.md).</span></span> 

<span data-ttu-id="dcc0b-220">전화 번호를 할당해야 하는 사용자 수로 인해 Contoso는 PowerShell을 사용하여 전화 번호를 할당하기로 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-220">Due to the number of users that needed to be assigned phone numbers, Contoso decided to use PowerShell to assign the phone numbers.</span></span> <span data-ttu-id="dcc0b-221">Contoso에서 Teams PowerShell 개요를 사용한 다른 설정 외에도 PowerShell을 사용하여 번호를 &mdash; &mdash; [할당하는 방법을 알아보기 위해](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="dcc0b-221">To learn how to assign numbers by using PowerShell&mdash;in addition to other settings&mdash;Contoso used the [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>  

### <a name="direct-routing-sites"></a><span data-ttu-id="dcc0b-222">직접 라우팅 사이트</span><span class="sxs-lookup"><span data-stu-id="dcc0b-222">Direct Routing sites</span></span>

<span data-ttu-id="dcc0b-223">Contoso의 On-Premises Telephony 인프라를 Microsoft Teams에 연결하기 위해 Contoso의 관리자는 직접 라우팅 구성의 단계를 따르고 [Microsoft Teams에서](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) 비디오 직접 라우팅을 검토하여 지침을 검토했습니다. [](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="dcc0b-223">To connect Contoso's on-premises telephony infrastructure to Microsoft Teams, Contoso's administrator followed the steps in [Configure Direct Routing](direct-routing-configure.md) and reviewed the video [Direct Routing in Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) for guidance.</span></span>  <span data-ttu-id="dcc0b-224">Contoso는 인증된 SBC 공급업체에서 직접 라우팅 배포 설명서를 참조했습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-224">Contoso also referred to the Direct routing deployment documentation by the certified SBC vendor.</span></span> 

<span data-ttu-id="dcc0b-225">SBC와 Microsoft Phone System 간에 직접 라우팅을 구성한 후 Contoso에서 구성을 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-225">Once Direct Routing was configured between the SBC and Microsoft Phone System, it was necessary for Contoso to test the configuration.</span></span> <span data-ttu-id="dcc0b-226">이를 위해 Contoso 관리자는 [Ignite 2019의](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions)직접 라우팅에 대한 업데이트 세션에서 설명한 SIP 테스터 클라이언트를 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-226">To do this, Contoso administrators used the SIP Tester client that was discussed in the [Updates for Direct Routing session at Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions).</span></span> <span data-ttu-id="dcc0b-227">직접 라우팅 세션 테두리 컨트롤러 연결을 테스트하기 위해 PowerShell 스크립트에서 SIP 테스터 클라이언트 스크립트 및 설명서를 다운로드했습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-227">The SIP Tester client script and documentation was downloaded from the PowerShell script to test Direct Routing Session Border Controller connections.</span></span>   


### <a name="local-media-optimization"></a><span data-ttu-id="dcc0b-228">로컬 미디어 최적화</span><span class="sxs-lookup"><span data-stu-id="dcc0b-228">Local Media Optimization</span></span>

<span data-ttu-id="dcc0b-229">Contoso는 전 세계 여러 지역에서 로컬 미디어 최적화를 활용할 수 있는 기회를 보게 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-229">Contoso saw the opportunity to leverage Local Media Optimization in the different regions across the globe.</span></span> <span data-ttu-id="dcc0b-230">Contoso에 지원되는 시나리오는 직접 라우팅에 대한 [로컬 미디어 최적화에 설명되어 있습니다.](direct-routing-media-optimization.md)</span><span class="sxs-lookup"><span data-stu-id="dcc0b-230">The supported scenarios for Contoso are described in [Local Media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span> <span data-ttu-id="dcc0b-231">로컬 미디어 최적화 구성은 SBC 공급업체와 Microsoft의 지침에 따라 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-231">The configuration of the local media optimization was completed by following guidance from both the SBC vendor and Microsoft.</span></span> <span data-ttu-id="dcc0b-232">로컬 미디어 최적화에 대한 구성 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-232">The configuration steps for Local Media Optimization include:</span></span> 

- <span data-ttu-id="dcc0b-233">사용자 및 SBC 사이트 구성</span><span class="sxs-lookup"><span data-stu-id="dcc0b-233">Configure the user and SBC sites</span></span> 

- <span data-ttu-id="dcc0b-234">SBC 공급업체 사양에 따라 SBC를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-234">Configure the SBC  according to the SBC vendor specification,</span></span> 

- <span data-ttu-id="dcc0b-235">로컬 미디어 최적화에 사용되는 각 사이트에 외부 신뢰할 수 있는 IP 주소 추가</span><span class="sxs-lookup"><span data-stu-id="dcc0b-235">Add external trusted IP addresses to each site used for Local Media Optimization</span></span>    

- <span data-ttu-id="dcc0b-236">네트워크 토폴로지 정의</span><span class="sxs-lookup"><span data-stu-id="dcc0b-236">Define the network topology</span></span> 

- <span data-ttu-id="dcc0b-237">가상 네트워크 토폴로지 정의</span><span class="sxs-lookup"><span data-stu-id="dcc0b-237">Define the virtual network topology</span></span> 

- <span data-ttu-id="dcc0b-238">모드 결정: 로컬 사용자에 대한 항상 무시 또는 전용</span><span class="sxs-lookup"><span data-stu-id="dcc0b-238">Determine the mode: Always Bypass or Only for local users</span></span> 

## <a name="networking-considerations"></a><span data-ttu-id="dcc0b-239">네트워킹 고려 사항</span><span class="sxs-lookup"><span data-stu-id="dcc0b-239">Networking considerations</span></span>

<span data-ttu-id="dcc0b-240">Contoso에는 전화 시스템에 대해 활성화된 후 장시간 원격으로 작업해야 하는 여러 사용자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-240">Contoso had a number of users who needed to work remotely for an extended period of time after they were enabled for Phone System.</span></span> <span data-ttu-id="dcc0b-241">사용자는 VPN을 사용하여 특정 사업부 애플리케이션에 액세스했습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-241">The users used VPN to access certain Line of Business applications.</span></span> <span data-ttu-id="dcc0b-242">VPN을 사용하는 동안 전화 시스템 사용자는 통화 품질 저하를 경험했습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-242">While on VPN, the Phone System users experienced a degradation of call quality.</span></span> 

<span data-ttu-id="dcc0b-243">품질 문제를 해결하기 위해 Contoso는 내부 앱에 대한 연결이 VPN에 남아 있는 동안 Office 365 트래픽이 인터넷을 트래버스하도록 허용하는 VPN 분할 터널링을 구현했습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-243">To resolve the quality issue, Contoso implemented VPN split tunneling, which allowed their Office 365 traffic to traverse the Internet while the connection to the internal apps remained on the VPN.</span></span> <span data-ttu-id="dcc0b-244">Contoso는 VPN 분할 터널링을 구현하기 위해 [Office 365에 대한 VPN 분할 터널링](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel)구현 지침을 따랐습니다.</span><span class="sxs-lookup"><span data-stu-id="dcc0b-244">To implement VPN split tunneling, Contoso followed the guidance in [Implementing VPN split tunneling for Office 365](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel).</span></span>  

 





