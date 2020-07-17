---
title: 팀 음성 Contoso 사례 연구
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
description: 여러 국가의 기업에 대 한 팀 음성 사례 연구
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7431515d40550a3f731c34f97ed8c10586424901
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786099"
---
# <a name="contoso-case-study-phone-system"></a><span data-ttu-id="9cec5-103">Contoso 사례 연구: 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="9cec5-103">Contoso case study: Phone System</span></span>

<span data-ttu-id="9cec5-104">지리적 위치 및 기타 요인에 따라 Contoso는 다음 전화 통신 솔루션을 사용 하는 사무실을 보유 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-104">Depending on geographic location and other factors, Contoso had offices using the following telephony solutions:</span></span>

- <span data-ttu-id="9cec5-105">사이트 종류 A: 비즈니스용 Skype Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="9cec5-105">Site Type A: Skype for Business Enterprise Voice</span></span>

- <span data-ttu-id="9cec5-106">사이트 유형 B: 기존 레거시 전화 통신 시스템</span><span class="sxs-lookup"><span data-stu-id="9cec5-106">Site Type B: Traditional legacy telephony systems</span></span>

- <span data-ttu-id="9cec5-107">사이트 종류 C: 비즈니스용 Skype Enterprise Voice와 기존 기존 전화 통신 시스템의 조합</span><span class="sxs-lookup"><span data-stu-id="9cec5-107">Site Type C: A combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>


<span data-ttu-id="9cec5-108">전체 조직에 대 한 Microsoft 전화 시스템 솔루션을 구현 하기 위해 Contoso는 &mdash; &mdash; 다음 옵션 중 전화 시스템에 사용 하 여 PSTN (공공 교환 전화 네트워크)에 연결 하도록 각 사이트 유형을 결정 해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-108">To implement a Microsoft Phone System solution for their entire organization, Contoso had to determine&mdash;for each site type&mdash;which of the following options would be used with Phone System to connect to the Public Switched Telephone Network (PSTN):</span></span>

- <span data-ttu-id="9cec5-109">통화 요금제가 포함 되어 있는 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="9cec5-109">Phone System with Calling Plan</span></span> 

- <span data-ttu-id="9cec5-110">직접 라우팅을 통한 자체 PSTN 캐리어가 있는 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="9cec5-110">Phone System with own PSTN carrier through Direct Routing</span></span> 

- <span data-ttu-id="9cec5-111">직접 라우팅을 통해 자체 PSTN 캐리어가 있는 통화 요금제 및 전화 시스템의 조합</span><span class="sxs-lookup"><span data-stu-id="9cec5-111">Combination of Phone System with Calling Plan and Phone System with own PSTN carrier through Direct Routing</span></span>
 
<span data-ttu-id="9cec5-112">조직의 올바른 솔루션을 확인 하기 위해 Contoso는 microsoft [전화 통신 솔루션](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) 및 [Microsoft 팀에서](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions)Ignite 2019 세션 통화를 사용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-112">To determine the right solution for their organization, Contoso used [Microsoft telephony solutions](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) and the Ignite 2019 session [Calling in Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).</span></span>  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a><span data-ttu-id="9cec5-113">사이트 종류 A: 비즈니스용 Skype Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="9cec5-113">Site Type A: Skype for Business Enterprise Voice</span></span> 

<span data-ttu-id="9cec5-114">Contoso 비즈니스용 Skype Enterprise Voice는 허브 및 스포크로 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-114">Contoso Skype for Business Enterprise Voice was set up as a hub and spoke.</span></span> <span data-ttu-id="9cec5-115">국가별 비즈니스용 Skype Enterprise 사용자 용 PSTN에 대 한 연결을 제공 하는 지역에서 PSTN 게이트웨이를 유지 관리 하는 중앙 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-115">There was a central location that maintained the PSTN gateway in the region that provided the connection to the PSTN for the Skype for Business Enterprise Voice users in country.</span></span> <span data-ttu-id="9cec5-116">일반적으로 이러한 위성 사무실에는 고유한 인터넷 송신이 설치 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-116">Often these satellite offices did not have their own Internet egress.</span></span> <span data-ttu-id="9cec5-117">이러한 사용자의 번호는 기존 SBC에 연결 된 SIP 트렁크에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-117">The numbers for these users resided on the SIP trunk connecting to an existing SBC.</span></span> 

<span data-ttu-id="9cec5-118">이미 배포 된 SBC이 직접 라우팅과 미디어 바이패스에 대해 인증 되었는지 확인 하기 위해 Contoso는 [직접 라우팅에 대해 인증 된 세션 경계 컨트롤러 목록을](direct-routing-border-controllers.md)확인 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-118">To determine if the SBC already deployed is certified for Direct Routing and Media Bypass, Contoso checked the [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>  

<span data-ttu-id="9cec5-119">사용자의 전화 걸기 습관은 사용자가 피어 투 피어 오디오에 사용할 수 있는 비즈니스용 Skype 클라이언트를 보유 하 고 있는 경우에도 확장을 사용 하 여 레거시 전화 통신 시스템에서 사용자에 게 전화를 거는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-119">The user's dialing habits were to dial a user on the legacy telephony system using an extension, even when the user has a Skype for Business client available for peer-to-peer audio.</span></span> 

<span data-ttu-id="9cec5-120">Contoso는 다음 질문에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-120">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="9cec5-121">Q&a.</span><span class="sxs-lookup"><span data-stu-id="9cec5-121">Q.</span></span> <span data-ttu-id="9cec5-122">온-프레미스 배포에서 제공 하는 기능을 유지 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="9cec5-122">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="9cec5-123">에서.</span><span class="sxs-lookup"><span data-stu-id="9cec5-123">A.</span></span> <span data-ttu-id="9cec5-124">아니요</span><span class="sxs-lookup"><span data-stu-id="9cec5-124">No</span></span> 

- <span data-ttu-id="9cec5-125">Q&a.</span><span class="sxs-lookup"><span data-stu-id="9cec5-125">Q.</span></span> <span data-ttu-id="9cec5-126">타사 PBX 시스템 및 기타 전화 장비와 상호 작용 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="9cec5-126">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br>
  <span data-ttu-id="9cec5-127">에서.</span><span class="sxs-lookup"><span data-stu-id="9cec5-127">A.</span></span> <span data-ttu-id="9cec5-128">아니요</span><span class="sxs-lookup"><span data-stu-id="9cec5-128">No</span></span> 

- <span data-ttu-id="9cec5-129">Q&a.</span><span class="sxs-lookup"><span data-stu-id="9cec5-129">Q.</span></span> <span data-ttu-id="9cec5-130">현재 제 3 자 캐리어가 유지 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="9cec5-130">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="9cec5-131">A. 예 (규정 국가) 및 아니요</span><span class="sxs-lookup"><span data-stu-id="9cec5-131">A. Yes (regulated countries) and No</span></span> 

- <span data-ttu-id="9cec5-132">Q&a.</span><span class="sxs-lookup"><span data-stu-id="9cec5-132">Q.</span></span> <span data-ttu-id="9cec5-133">SBCs의 ROI를 배포 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="9cec5-133">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="9cec5-134">A. 예 및 아니요</span><span class="sxs-lookup"><span data-stu-id="9cec5-134">A. Yes and No</span></span>  

- <span data-ttu-id="9cec5-135">Q&a.</span><span class="sxs-lookup"><span data-stu-id="9cec5-135">Q.</span></span> <span data-ttu-id="9cec5-136">이 지역에서 Microsoft PSTN 통화 요금제를 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="9cec5-136">Is Microsoft PSTN Calling Plans available in this region?</span></span><br> <span data-ttu-id="9cec5-137">A. 예 및 아니요</span><span class="sxs-lookup"><span data-stu-id="9cec5-137">A. Yes and No</span></span> 

<span data-ttu-id="9cec5-138">Contoso는 질문에 대 한 답변을 토대로 다음을 결정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-138">Based on the answers to their questions, Contoso decided to:</span></span>

- <span data-ttu-id="9cec5-139">통화 요금제를 사용 하 여 PSTN 통화 요금제를 사용할 수 있는 지역에 있는 사용자를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-139">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="9cec5-140">PSTN 통화 요금제를 사용할 수 있는 지역에 있지 않은 사용자, SBCs의 ROI가 아직 충족 되지 않은 사이트에 위치한 사용자, 직접 라우팅이 있는 전화 시스템에 전화 접속 규정이 있는 국가 내 사용자를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-140">Move the users that are not located in a region where PSTN calling plans is available, users located in a site where the ROI on the SBCs have yet to be met, and users that resided in a country that has telephony regulations to Phone System with Direct Routing.</span></span> 

<span data-ttu-id="9cec5-141">다음 다이어그램은 초기 비즈니스용 Skype Enterprise Voice 배포와이 배포를 Microsoft 호출 계획 및 직접 라우팅 둘 다로 마이그레이션하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-141">The following diagram shows the initial Skype for Business Enterprise Voice deployment and how this deployment was migrated to both Microsoft Calling Plans and Direct Routing:</span></span>

![이전 및 이후 상태를 보여 주는 다이어그램](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a><span data-ttu-id="9cec5-143">사이트 유형 B: 기존 레거시 전화 통신 시스템</span><span class="sxs-lookup"><span data-stu-id="9cec5-143">Site Type B: Traditional legacy telephony systems</span></span>

<span data-ttu-id="9cec5-144">Contoso는 레거시 전화 통신 시스템을 이용 하는 많은 사무실을 보유 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-144">Contoso had many offices that leveraged legacy telephony systems.</span></span> <span data-ttu-id="9cec5-145">일부 사용자는 E 1.64 전화 번호를가지고 있고 다른 사람들은 확장명만 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-145">There were a subset of users that had an E1.64 phone number while others only had an extension.</span></span> <span data-ttu-id="9cec5-146">이러한 번호는 PSTN 게이트웨이에 대 한 TDM 트렁크에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-146">These numbers resided on the TDM trunk to the PSTN gateway.</span></span> <span data-ttu-id="9cec5-147">내부에서 전화를 거는 위치를 결정 하기 위해 확장 앞에 사이트 코드를 활용 하 여 사이트 내 다이얼 인을 구성 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-147">Intra-site dialing was configured by leveraging a site code in front of the extension to determine where to route the call.</span></span> <span data-ttu-id="9cec5-148">사용자의 전화 걸기 습관은 내선 번호를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-148">The users' dialing habits were to dial by extension.</span></span>   

<span data-ttu-id="9cec5-149">Contoso는 다음 질문에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-149">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="9cec5-150">Q&a.</span><span class="sxs-lookup"><span data-stu-id="9cec5-150">Q.</span></span> <span data-ttu-id="9cec5-151">온-프레미스 배포에서 제공 하는 기능을 유지 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="9cec5-151">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="9cec5-152">에서.</span><span class="sxs-lookup"><span data-stu-id="9cec5-152">A.</span></span> <span data-ttu-id="9cec5-153">아니요</span><span class="sxs-lookup"><span data-stu-id="9cec5-153">No</span></span> 

- <span data-ttu-id="9cec5-154">Q&a.</span><span class="sxs-lookup"><span data-stu-id="9cec5-154">Q.</span></span> <span data-ttu-id="9cec5-155">타사 PBX 시스템 및 기타 전화 장비와 상호 작용 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="9cec5-155">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="9cec5-156">A. 예</span><span class="sxs-lookup"><span data-stu-id="9cec5-156">A. Yes</span></span>

- <span data-ttu-id="9cec5-157">Q&a.</span><span class="sxs-lookup"><span data-stu-id="9cec5-157">Q.</span></span> <span data-ttu-id="9cec5-158">현재 제 3 자 캐리어가 유지 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="9cec5-158">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="9cec5-159">A. 아니요</span><span class="sxs-lookup"><span data-stu-id="9cec5-159">A. No</span></span> 

- <span data-ttu-id="9cec5-160">Q&a.</span><span class="sxs-lookup"><span data-stu-id="9cec5-160">Q.</span></span> <span data-ttu-id="9cec5-161">Microsoft PSTN의 통화 요금제는이 지역에서 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="9cec5-161">Is Microsoft PSTN's Calling Plan available in our region?</span></span><br> <span data-ttu-id="9cec5-162">A. 예 및 아니요</span><span class="sxs-lookup"><span data-stu-id="9cec5-162">A. Yes and No</span></span> 

<span data-ttu-id="9cec5-163">Contoso는 질문에 대 한 답변을 토대로 다음을 결정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-163">Based on the answers to their questions, Contoso decided to:</span></span> 

- <span data-ttu-id="9cec5-164">통화 요금제를 사용 하 여 PSTN 통화 요금제를 사용할 수 있는 지역에 있는 사용자를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-164">Move the users that are located in a region where PSTN calling plans is available to Phone System with Calling Plans.</span></span> 

- <span data-ttu-id="9cec5-165">다이렉트 라우팅이 있는 휴대폰 시스템에서 PSTN 통화 요금제를 사용할 수 있는 지역에 없는 사용자를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-165">Move the users that are not located in a region where PSTN calling plans is available to Phone System with Direct Routing.</span></span> 

- <span data-ttu-id="9cec5-166">비즈니스에 중요 한 아날로그 장치에 대 한 PSTN 연결을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-166">Maintain a PSTN connection to business critical analog devices.</span></span>

<span data-ttu-id="9cec5-167">다음 다이어그램은 원격 사이트와의 원래 레거시 시스템 배포와 로컬 미디어 최적화를 사용 하 여 직접 라우팅 배포로의 마이그레이션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-167">The following diagrams show the original legacy system deployment with remote sites and the migration to a Direct Routing deployment with Local Media Optimization:</span></span>

<span data-ttu-id="9cec5-168">**원본 레거시 배포**  
 ![ 이전 및 이후 상태를 보여 주는 다이어그램](media/voice-case-study-2.png)</span><span class="sxs-lookup"><span data-stu-id="9cec5-168">**Original legacy deployment** 
![Diagram showing before and after states](media/voice-case-study-2.png)</span></span>


<span data-ttu-id="9cec5-169">**직접 라우팅으로 배포**</span><span class="sxs-lookup"><span data-stu-id="9cec5-169">**Deployment with Direct Routing**</span></span>

![이전 및 이후 상태를 보여 주는 다이어그램](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a><span data-ttu-id="9cec5-171">사이트 종류 C: 비즈니스용 Skype Enterprise Voice 및 전통적인 레거시 전화 통신 시스템의 조합</span><span class="sxs-lookup"><span data-stu-id="9cec5-171">Site Type C: Combination of Skype for Business Enterprise Voice and traditional legacy telephony systems</span></span>

<span data-ttu-id="9cec5-172">Contoso 비즈니스용 Skype Enterprise Voice 사용자의 번호는 통신 회사의 SBC에 대 한 SIP 트렁크에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-172">Contoso Skype for Business Enterprise Voice users' numbers reside on the SIP trunk to the SBC from the carrier.</span></span> <span data-ttu-id="9cec5-173">기존 전화 통신 시스템의 숫자가 PSTN 게이트웨이에 대 한 TDM 트렁크에 상주 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-173">The numbers for the traditional telephony systems resided on the TDM trunk to the PSTN gateway.</span></span>   

<span data-ttu-id="9cec5-174">Contoso는 다음 질문에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-174">Contoso based their decision on the following questions:</span></span>

- <span data-ttu-id="9cec5-175">Q&a.</span><span class="sxs-lookup"><span data-stu-id="9cec5-175">Q.</span></span> <span data-ttu-id="9cec5-176">온-프레미스 배포에서 제공 하는 기능을 유지 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="9cec5-176">Do we need to retain functionality provided by our on-premises deployment?</span></span><br>
  <span data-ttu-id="9cec5-177">에서.</span><span class="sxs-lookup"><span data-stu-id="9cec5-177">A.</span></span> <span data-ttu-id="9cec5-178">아니요</span><span class="sxs-lookup"><span data-stu-id="9cec5-178">No</span></span> 

- <span data-ttu-id="9cec5-179">Q&a.</span><span class="sxs-lookup"><span data-stu-id="9cec5-179">Q.</span></span> <span data-ttu-id="9cec5-180">타사 PBX 시스템 및 기타 전화 장비와 상호 작용 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="9cec5-180">Do we need to interoperate with third-party PBX systems and other telephony equipment?</span></span><br> <span data-ttu-id="9cec5-181">A. 아니요</span><span class="sxs-lookup"><span data-stu-id="9cec5-181">A. No</span></span> 

- <span data-ttu-id="9cec5-182">Q&a.</span><span class="sxs-lookup"><span data-stu-id="9cec5-182">Q.</span></span> <span data-ttu-id="9cec5-183">현재 제 3 자 캐리어가 유지 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="9cec5-183">Do we need to retain our current third-party carrier?</span></span><br> <span data-ttu-id="9cec5-184">A. 아니요</span><span class="sxs-lookup"><span data-stu-id="9cec5-184">A. No</span></span> 

- <span data-ttu-id="9cec5-185">Q&a.</span><span class="sxs-lookup"><span data-stu-id="9cec5-185">Q.</span></span> <span data-ttu-id="9cec5-186">SBCs의 ROI를 배포 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="9cec5-186">Do we need to get the ROI on SBCs deployed?</span></span><br> <span data-ttu-id="9cec5-187">A. 예 및 아니요</span><span class="sxs-lookup"><span data-stu-id="9cec5-187">A. Yes and No</span></span>  

- <span data-ttu-id="9cec5-188">Q&a.</span><span class="sxs-lookup"><span data-stu-id="9cec5-188">Q.</span></span> <span data-ttu-id="9cec5-189">이 지역에서 Microsoft의 PSTN 통화 요금제를 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="9cec5-189">Is Microsoft's PSTN Calling Plan available in this region?</span></span><br> <span data-ttu-id="9cec5-190">A. 아니요</span><span class="sxs-lookup"><span data-stu-id="9cec5-190">A. No</span></span> 

<span data-ttu-id="9cec5-191">Contoso는 질문에 대 한 답변을 바탕으로 다음을 결정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-191">Based on the answers to their questions, Contoso decided on the following:</span></span> 

- <span data-ttu-id="9cec5-192">직접적인 라우팅에 사용 되는 레거시 전화 통신 사용자의 경우,이 SBC는 직접 라우팅에 대 한 자격을가지고 있기 때문에 Contoso는 TDM 트렁크에서 SBC의 SIP 트렁크로 번호를 이식 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-192">For the legacy telephony users that will be enabled for Direct Routing, Contoso ported the numbers from the TDM trunk to the SIP Trunk for the SBC, since the SBC is certified for Direct Routing.</span></span> 

- <span data-ttu-id="9cec5-193">전화 시스템으로 이동 하는 사용자의 하위 집합을 지원 하 고 레거시 시스템을 통한 지속적인 라우팅이 가능 하도록 하기 위해 기존 전화 통신 시스템을 SBC에 대 한 다음 홉으로 설정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-193">To support a subset of users moving to Phone System and to allow continued routing through the legacy system, the legacy telephony system was set up as the next hop to the SBC.</span></span>   

- <span data-ttu-id="9cec5-194">또한 사용자 동작이 변경 되 고 사이트 내 확장 전화 접속에 대 한 종속성을 제거 하기 위해 Contoso는 모든 내부 통화를 위해 팀을 사용할 수 있는 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-194">In addition, to encourage user behavior change and remove the dependency on inter- and intra-site extension dialing, Contoso provided guidance to use Teams for all internal calls.</span></span>  

<span data-ttu-id="9cec5-195">다음 다이어그램은 원본 비즈니스용 Skype Enterprise Voice와 레거시 전화 통신 시스템 배포 및 직접 라우팅을 사용 하는 혼합 배포로의 마이그레이션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-195">The following diagrams show the original Skype for Business Enterprise Voice and legacy telephony system deployment and the migration to a mixed deployment using Direct Routing:</span></span>

<span data-ttu-id="9cec5-196">**원본 혼합 배포** 
 ![ 이전 상태를 보여 주는 다이어그램](media/voice-case-study-4.png)</span><span class="sxs-lookup"><span data-stu-id="9cec5-196">**Original mixed deployment**
![Diagram showing before state](media/voice-case-study-4.png)</span></span>

<span data-ttu-id="9cec5-197">**직접 라우팅이** 
 ![ 포함 되는 혼합 배포 이전 상태를 보여 주는 다이어그램](media/voice-case-study-4a.png)</span><span class="sxs-lookup"><span data-stu-id="9cec5-197">**Mixed deployment with Direct Routing**
![Diagram showing before state](media/voice-case-study-4a.png)</span></span>


## <a name="calling-plans"></a><span data-ttu-id="9cec5-198">통화 플랜</span><span class="sxs-lookup"><span data-stu-id="9cec5-198">Calling Plans</span></span>

<span data-ttu-id="9cec5-199">통화 요금제에 대 한 구성 요구 사항을 결정 하기 위해 Contoso는 [호출 계획 핵심 배포 결정](calling-plan-landing-page.md#core-deployment-decisions)을 검토 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-199">To determine the configuration requirements for Calling Plans, Contoso reviewed the [Calling Plan core deployment decisions](calling-plan-landing-page.md#core-deployment-decisions).</span></span> <span data-ttu-id="9cec5-200">그 결과 결정을 수행 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-200">The resulting decisions were made:</span></span> 

- <span data-ttu-id="9cec5-201">Q&a.</span><span class="sxs-lookup"><span data-stu-id="9cec5-201">Q.</span></span> <span data-ttu-id="9cec5-202">사용자에 게 국제 통화가 필요 한가요?</span><span class="sxs-lookup"><span data-stu-id="9cec5-202">Do my users need international calling?</span></span><br> <span data-ttu-id="9cec5-203">A. 예</span><span class="sxs-lookup"><span data-stu-id="9cec5-203">A. Yes</span></span> 

- <span data-ttu-id="9cec5-204">Q&a.</span><span class="sxs-lookup"><span data-stu-id="9cec5-204">Q.</span></span> <span data-ttu-id="9cec5-205">내 사용자에 게 직접 안쪽으로 전달 된 전화 번호가 있습니까?</span><span class="sxs-lookup"><span data-stu-id="9cec5-205">Do my users each have a direct inward DID phone number?</span></span><br> <span data-ttu-id="9cec5-206">A. 오늘이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-206">A. Not today.</span></span> <span data-ttu-id="9cec5-207">모든 사용자가을 (를) 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-207">All users enabled will receive a DID.</span></span> 

- <span data-ttu-id="9cec5-208">Q&a.</span><span class="sxs-lookup"><span data-stu-id="9cec5-208">Q.</span></span> <span data-ttu-id="9cec5-209">발신자 ID를 마스킹 또는 사용 하지 않도록 설정 하 시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="9cec5-209">Do I want to mask or disable caller ID?</span></span><br> <span data-ttu-id="9cec5-210">A. 사용자의 발신자 ID는 Contoso의 지역 번호로 마스킹된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-210">A. The caller ID for a user will be masked to the local number for Contoso.</span></span> 


## <a name="direct-routing"></a><span data-ttu-id="9cec5-211">직접 라우팅</span><span class="sxs-lookup"><span data-stu-id="9cec5-211">Direct Routing</span></span>

<span data-ttu-id="9cec5-212">Contoso는 전화 시스템 및 다이렉트 라우팅과 함께 제공 되는 Office 365 기능을 최신 상태로 유지할 수 있도록 Ignite을 유인 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-212">Contoso attended Ignite to stay current on Office 365 features including those available with Phone system and Direct Routing.</span></span> <span data-ttu-id="9cec5-213">기술 리더십 및 설계자는 Ignite 2019 중 제공 된 지침을 사용 하 여 방향을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-213">Technical leadership and architects used the guidance provided during the Ignite 2019 to determine their direction.</span></span>  <span data-ttu-id="9cec5-214">사용 된 키 세션:</span><span class="sxs-lookup"><span data-stu-id="9cec5-214">Key sessions that were used:</span></span> 

- [<span data-ttu-id="9cec5-215">Microsoft 팀의 성공 계획 직접 라우팅</span><span class="sxs-lookup"><span data-stu-id="9cec5-215">Plan for success with Microsoft Teams Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [<span data-ttu-id="9cec5-216">직접 라우팅에 대 한 업데이트</span><span class="sxs-lookup"><span data-stu-id="9cec5-216">Updates for Direct Routing</span></span>](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a><span data-ttu-id="9cec5-217">구성</span><span class="sxs-lookup"><span data-stu-id="9cec5-217">Configuration</span></span>

### <a name="calling-plans-sites"></a><span data-ttu-id="9cec5-218">통화 계획 사이트</span><span class="sxs-lookup"><span data-stu-id="9cec5-218">Calling Plans sites</span></span>

<span data-ttu-id="9cec5-219">라이선스를 얻고 전화 번호를 사용자에 게 할당 하기 위해 Contoso는 [통화 계획 설정](set-up-calling-plans.md)의 단계를 팔 로우 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-219">To obtain licenses and assign phone numbers to users, Contoso followed the steps in [Set up Calling Plans](set-up-calling-plans.md).</span></span> 

<span data-ttu-id="9cec5-220">전화 번호를 할당 해야 하는 사용자 수 때문에 Contoso는 PowerShell을 사용 하 여 전화 번호를 할당 하기로 결정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-220">Due to the number of users that needed to be assigned phone numbers, Contoso decided to use PowerShell to assign the phone numbers.</span></span> <span data-ttu-id="9cec5-221">&mdash; &mdash; [팀 powershell 개요](teams-powershell-overview.md)를 사용 하는 다른 설정 외에 PowerShell을 사용 하 여 번호를 할당 하는 방법에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="9cec5-221">To learn how to assign numbers by using PowerShell&mdash;in addition to other settings&mdash;Contoso used the [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>  

### <a name="direct-routing-sites"></a><span data-ttu-id="9cec5-222">다이렉트 라우팅 사이트</span><span class="sxs-lookup"><span data-stu-id="9cec5-222">Direct Routing sites</span></span>

<span data-ttu-id="9cec5-223">Contoso의 온-프레미스 전화 통신 인프라를 Microsoft 팀에 연결 하기 위해 Contoso의 관리자는 [직접 라우팅 구성](direct-routing-configure.md) 단계를 따라 [Microsoft 팀의 비디오 다이렉트 라우팅을](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) 검토 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-223">To connect Contoso's on-premises telephony infrastructure to Microsoft Teams, Contoso's administrator followed the steps in [Configure Direct Routing](direct-routing-configure.md) and reviewed the video [Direct Routing in Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) for guidance.</span></span>  <span data-ttu-id="9cec5-224">Contoso는 또한 인증 된 SBC 공급 업체의 직접적인 라우팅 배포 문서 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-224">Contoso also referred to the Direct routing deployment documentation by the certified SBC vendor.</span></span> 

<span data-ttu-id="9cec5-225">SBC 및 Microsoft 전화 시스템 간에 직접 라우팅이 구성 된 후에는 Contoso가 구성을 테스트 해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-225">Once Direct Routing was configured between the SBC and Microsoft Phone System, it was necessary for Contoso to test the configuration.</span></span> <span data-ttu-id="9cec5-226">이를 위해 Contoso 관리자는 [Ignite 2019에서 다이렉트 라우팅 세션에 대 한 업데이트](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions)에서 설명한 SIP 테스터 클라이언트를 사용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-226">To do this, Contoso administrators used the SIP Tester client that was discussed in the [Updates for Direct Routing session at Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions).</span></span> <span data-ttu-id="9cec5-227">직접 라우팅 세션 경계 컨트롤러 연결을 테스트 하기 위해 SIP 테스터 클라이언트 스크립트와 문서가 PowerShell 스크립트에서 다운로드 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-227">The SIP Tester client script and documentation was downloaded from the PowerShell script to test Direct Routing Session Border Controller connections.</span></span>   


### <a name="local-media-optimization"></a><span data-ttu-id="9cec5-228">로컬 미디어 최적화</span><span class="sxs-lookup"><span data-stu-id="9cec5-228">Local Media Optimization</span></span>

<span data-ttu-id="9cec5-229">Contoso는 전세계 여러 지역에서 로컬 미디어 최적화를 활용할 수 있는 기회를 보았습니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-229">Contoso saw the opportunity to leverage Local Media Optimization in the different regions across the globe.</span></span> <span data-ttu-id="9cec5-230">Contoso에 대해 지원 되는 시나리오는 [직접적인 라우팅에 대 한 로컬 미디어 최적화](direct-routing-media-optimization.md)에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-230">The supported scenarios for Contoso are described in [Local Media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span> <span data-ttu-id="9cec5-231">SBC 공급 업체와 Microsoft가 제공 하는 지침에 따라 로컬 미디어 최적화의 구성을 완료 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-231">The configuration of the local media optimization was completed by following guidance from both the SBC vendor and Microsoft.</span></span> <span data-ttu-id="9cec5-232">로컬 미디어 최적화를 위한 구성 단계에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-232">The configuration steps for Local Media Optimization include:</span></span> 

- <span data-ttu-id="9cec5-233">사용자 및 SBC 사이트 구성</span><span class="sxs-lookup"><span data-stu-id="9cec5-233">Configure the user and SBC sites</span></span> 

- <span data-ttu-id="9cec5-234">SBC 공급 업체 사양에 따라 SBC를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-234">Configure the SBC  according to the SBC vendor specification,</span></span> 

- <span data-ttu-id="9cec5-235">로컬 미디어 최적화에 사용 되는 각 사이트에 외부의 신뢰할 수 있는 IP 주소 추가</span><span class="sxs-lookup"><span data-stu-id="9cec5-235">Add external trusted IP addresses to each site used for Local Media Optimization</span></span>    

- <span data-ttu-id="9cec5-236">네트워크 토폴로지 정의</span><span class="sxs-lookup"><span data-stu-id="9cec5-236">Define the network topology</span></span> 

- <span data-ttu-id="9cec5-237">가상 네트워크 토폴로지 정의</span><span class="sxs-lookup"><span data-stu-id="9cec5-237">Define the virtual network topology</span></span> 

- <span data-ttu-id="9cec5-238">모드 결정: 항상 무시 하거나 로컬 사용자만</span><span class="sxs-lookup"><span data-stu-id="9cec5-238">Determine the mode: Always Bypass or Only for local users</span></span> 

## <a name="networking-considerations"></a><span data-ttu-id="9cec5-239">네트워킹 고려 사항</span><span class="sxs-lookup"><span data-stu-id="9cec5-239">Networking considerations</span></span>

<span data-ttu-id="9cec5-240">Contoso에는 전화 시스템을 사용 하도록 설정한 후 오랜 시간 동안 원격으로 작업 해야 하는 많은 사용자가 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-240">Contoso had a number of users who needed to work remotely for an extended period of time after they were enabled for Phone System.</span></span> <span data-ttu-id="9cec5-241">사용자가 VPN을 사용 하 여 특정 lob 응용 프로그램에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-241">The users used VPN to access certain Line of Business applications.</span></span> <span data-ttu-id="9cec5-242">VPN을 진행 하는 동안 전화 시스템 사용자는 통화 품질의 저하를 경험 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-242">While on VPN, the Phone System users experienced a degradation of call quality.</span></span> 

<span data-ttu-id="9cec5-243">품질 문제를 해결 하기 위해 Contoso는 VPN 분할 터널링을 구현 하 여 내부 앱에 대 한 연결이 VPN에 남아 있는 동안 해당 Office 365 트래픽이 인터넷을 통과할 수 있도록 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-243">To resolve the quality issue, Contoso implemented VPN split tunneling, which allowed their Office 365 traffic to traverse the Internet while the connection to the internal apps remained on the VPN.</span></span> <span data-ttu-id="9cec5-244">VPN 분할 터널링을 구현 하기 위해 Contoso는 [Office 365 vpn 분할 터널링을 구현](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel)하는 지침을 팔 로우 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cec5-244">To implement VPN split tunneling, Contoso followed the guidance in [Implementing VPN split tunneling for Office 365](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel).</span></span>  

 





