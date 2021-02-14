---
title: Microsoft 365 Government - GCC 배포
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: 미국 정부 규정이 적용된 데이터를 처리하는 엔터티에서 Microsoft 365 배포를 구동하기 위한 IT 프로에 대한 지침
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: e40f511aedfed2423e04ece74a9c2c7f370acb74
ms.sourcegitcommit: b282acc1633c2d62bbff0ea77b6b647775ae6dfe
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49085612"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a><span data-ttu-id="63711-103">Microsoft 365 Government 계획 - GCC 배포</span><span class="sxs-lookup"><span data-stu-id="63711-103">Plan for Microsoft 365 Government - GCC deployments</span></span>

<span data-ttu-id="63711-104">이 지침은 미국 연방, 주, 지방, 부족 또는 지방 정부 기관 또는 정부 규정 및 요구 사항이 적용된 데이터를 처리하는 기타 엔터티에서 Microsoft 365 배포를 구동하는 IT 프로를 위한 것입니다. 여기서 Microsoft 365 Government - GCC를 사용하는 것이 이러한 요구 사항을 충족하는 데 적절합니다.</span><span class="sxs-lookup"><span data-stu-id="63711-104">This guidance is for IT pros who are driving deployments of Microsoft 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Microsoft 365 Government - GCC is appropriate to meet these requirements.</span></span> <span data-ttu-id="63711-105">새 2020년 3월 26일: [GCC용](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)다운로드 가능한 빠른 시작 가이드를 놓치지 마세요.</span><span class="sxs-lookup"><span data-stu-id="63711-105">New March 26, 2020: Don't miss our downloadable [Quick Start guide for GCC](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="63711-106">Microsoft Teams는 코로나바이러스(COVID-19) 패닉으로 인해 온라인 통화 및 오디오/비디오 회의가 급격히 증가하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63711-106">Microsoft Teams is experiencing a tremendous spike in online calls and audio/video conferencing due to the coronavirus (COVID-19) pandemic.</span></span><br/>
> 
><span data-ttu-id="63711-107">전례 없는 통화 증가에 대응하고, 연속성 및 가용성을 보장하기 위해 Microsoft는 Microsoft Teams GCC 오디오/비디오 서버가 Microsoft의 상용 데이터 센터 및 정부 데이터 센터에서 처리 용량을 활용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="63711-107">In response to the unprecedented increase in calls, and to ensure continuity and availability, Microsoft is allowing Microsoft Teams GCC audio/video servers to leverage processing capacity in our commercial datacenters, as well as in our government datacenters.</span></span><br/>
> 
><span data-ttu-id="63711-108">이러한 오디오/비디오 서버는 미국의 Microsoft Azure FedRAMP High 공인 경계 서버 내에 있으며 고객 콘텐츠를 저장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="63711-108">These audio/video servers reside within the Microsoft Azure FedRAMP High accreditation boundary servers in the United States and do not store any customer content.</span></span> <span data-ttu-id="63711-109">그러나 이러한 서버는 통화 및 회의에 대한 오디오 및 비디오를 처리하고 있으며 이 중간 기간 동안 상용 직원을 통해 운영됩니다.</span><span class="sxs-lookup"><span data-stu-id="63711-109">However, these servers are processing audio and video for calls and conferences and are operating under our commercial staff during this interim period.</span></span><br/>
> 
><span data-ttu-id="63711-110">자격을 갖춘 선발된 담당자는 이러한 서버에 대한 대화형 로그온을 검토하여 이러한 서버를 모니터링하여 고객 데이터에 대한 잠재적인 액세스를 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="63711-110">Qualified, screened personnel are monitoring these servers for potential access to customer data by reviewing any interactive log-ons to these servers.</span></span> <span data-ttu-id="63711-111">자격이 있는 직원은 고객 콘텐츠에 액세스하기 위한 GCC 요구 사항을 충족합니다.</span><span class="sxs-lookup"><span data-stu-id="63711-111">Qualified personnel meet GCC requirements for access to customer content.</span></span> <span data-ttu-id="63711-112">화면 요구 사항에 대한 자세한 내용은 GCC 서비스 [설명을 참조하세요.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)</span><span class="sxs-lookup"><span data-stu-id="63711-112">For details about screening requirements, see the [GCC service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).</span></span><br/>
> 
><span data-ttu-id="63711-113">이러한 특별한 상황에서 서비스를 사용할 수 있고 신뢰할 수 있도록 하는 단계를 수행하면 귀하의 지원에 감사드립니다.</span><span class="sxs-lookup"><span data-stu-id="63711-113">Thank you for your support as we take steps to ensure that our services remain available and reliable in these extraordinary times.</span></span><br/>


> [!NOTE]
> <span data-ttu-id="63711-114">조직에서 이미 Microsoft 365 Government - GCC 자격 요구 사항을 충족하고 프로그램에 적용되어 프로그램에 수락된 경우 1단계와 2단계를 건너뛰고 3단계로 바로 이동하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="63711-114">If your organization has already met the Microsoft 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="63711-115">1단계.</span><span class="sxs-lookup"><span data-stu-id="63711-115">Step 1.</span></span> <span data-ttu-id="63711-116">조직에 Microsoft 365 Government - GCC가 필요하고 자격 요구 사항을 충족하는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="63711-116">Determine whether your organization needs Microsoft 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="63711-117">Microsoft 365 Government - GCC 환경은 FedRAMP Moderate를 포함한 클라우드 서비스에 대한 미국 정부 요구 사항 및 범죄 사법 및 연방 세금 정보 시스템(CJI 및 FTI 데이터 형식)에 대한 요구 사항을 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="63711-117">The Microsoft 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="63711-118">조직은 Microsoft 365의 기능과 기능을 즐기는 것 외에도 Microsoft 365 Government - GCC에 고유한 다음과 같은 기능을 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="63711-118">In addition to enjoying the features and capabilities of Microsoft 365, organizations benefit from the following features that are unique to Microsoft 365 Government - GCC:</span></span>

-   <span data-ttu-id="63711-119">조직의 고객 콘텐츠는 Microsoft의 상용 Microsoft 365 서비스의 고객 콘텐츠와 논리적으로 나타났습니다.</span><span class="sxs-lookup"><span data-stu-id="63711-119">Your organization's customer content is logically segregated from customer content in the commercial Microsoft 365 services from Microsoft.</span></span>
-   <span data-ttu-id="63711-120">조직의 고객 콘텐츠는 미국 내에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="63711-120">Your organization's customer content is stored within the United States.</span></span>
-   <span data-ttu-id="63711-121">조직의 고객 콘텐츠에 대한 액세스는 선고된 Microsoft 담당자로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="63711-121">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="63711-122">Microsoft 365 Government - GCC는 미국 공공 부문 고객에게 필요한 인증 및 인증을 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="63711-122">Microsoft 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="63711-123">자격 요구 사항을 포함하여 Microsoft 365 Government 요금제에서 미국 정부 고객을 위한 [Microsoft 365 Government](https://products.office.com/government/compare-office-365-government-plans)- GCC 제안에 대한 자세한 정보를 찾을 수 [있습니다.](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)</span><span class="sxs-lookup"><span data-stu-id="63711-123">You can find more information about the Microsoft 365 Government - GCC offering for US Government customers at [Microsoft 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="63711-124">[Microsoft 365 미국 정부](https://technet.microsoft.com/library/mt774581.aspx) 서비스 설명은 미국 내의 규정 준수 요구 사항을 충족하는 데 중심을 두는 플랫폼의 이점에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63711-124">The [Microsoft 365 US Government service description](https://technet.microsoft.com/library/mt774581.aspx) describes the platform's benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="63711-125">서비스 설명의 정보 테이블을 Excel 통합 문서로 전송하고 조직 **Y/N과** 관련이 있으며 조직의 요구 사항을 충족하는 두 개의 열을 추가할 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="63711-125">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="63711-126">그런 다음 동료와 함께 이 목록을 검토하여 이 서비스가 조직의 요구 사항을 충족하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63711-126">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>

|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/><span data-ttu-id="63711-128">의사 결정 지점</span><span class="sxs-lookup"><span data-stu-id="63711-128">Decision points</span></span>|<ul><li><span data-ttu-id="63711-129">Microsoft 365 Government - GCC가 조직에 적합한지 여부를 판단합니다.</span><span class="sxs-lookup"><span data-stu-id="63711-129">Decide whether Microsoft 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="63711-130">조직이 자격 요구 사항을 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="63711-130">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="63711-131">Microsoft 365 Government - GCC는 미국에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63711-131">Microsoft 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="63711-132">미국 정부 이 아닌 고객은 다양한 [Microsoft 365 Government](https://products.office.com/en/government/compare-office-365-government-plans)요금제에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63711-132">Non–US Government customers can choose from a number of [Microsoft 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a><span data-ttu-id="63711-133">2단계.</span><span class="sxs-lookup"><span data-stu-id="63711-133">Step 2.</span></span> <span data-ttu-id="63711-134">Microsoft 365 Government에 적용 - GCC</span><span class="sxs-lookup"><span data-stu-id="63711-134">Apply for Microsoft 365 Government - GCC</span></span>

<span data-ttu-id="63711-135">이 서비스가 조직에 적합한 것으로 결정한 후 여기에서 이 서비스에 [적용하는 프로세스를 시작하세요.](https://products.office.com/government/eligibility-validation)</span><span class="sxs-lookup"><span data-stu-id="63711-135">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a><span data-ttu-id="63711-136">3단계.</span><span class="sxs-lookup"><span data-stu-id="63711-136">Step 3.</span></span> <span data-ttu-id="63711-137">Microsoft 365 Government - GCC 기본 보안 설정을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="63711-137">Understand Microsoft 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="63711-138">수정하기 전에 관리자 및 보안 [](enable-features-office-365.md) 설정을 신중하게 검토하고 기본 보안 설정을 변경하기 전에 규정 준수에 미치는 영향을 고려하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="63711-138">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/><span data-ttu-id="63711-140">의사 결정 지점</span><span class="sxs-lookup"><span data-stu-id="63711-140">Decision point</span></span>|<ul><li><span data-ttu-id="63711-141">기본 Microsoft 365 Government - GCC 보안 설정을 수정할지 여부를 결정하여 변경 내용이 미치는 영향을 먼저 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="63711-141">Decide whether you'll modify any of the default Microsoft 365 Government - GCC security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="63711-142">4단계.</span><span class="sxs-lookup"><span data-stu-id="63711-142">Step 4.</span></span> <span data-ttu-id="63711-143">기본적으로 현재 사용할 수 없거나 사용할 수 없는 기능을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="63711-143">Understand which capabilities are currently unavailable or disabled by default.</span></span>

<span data-ttu-id="63711-144">정부 클라우드 고객의 요구 사항을 수용하기 위해 Microsoft 365 Government - GCC 및 엔터프라이즈 계획 간에 몇 가지 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63711-144">To accommodate the requirements of our government cloud customers, there are some differences between Microsoft 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="63711-145">다음 표를 참조하여 사용할 수 있는 기능을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="63711-145">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="63711-146">Microsoft Teams 서비스 설명</span><span class="sxs-lookup"><span data-stu-id="63711-146">Microsoft Teams service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

> [!Note]
> <span data-ttu-id="63711-147">GCC 클라우드에서 다른 워크로드를 완전히 사용할 수 있는 경우 모든 추가 통합 작업을 완료하면 Teams에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63711-147">Once other workloads are fully available in the GCC cloud, then they will become available in Teams when all additional  integration work is completed.</span></span>


|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/><span data-ttu-id="63711-149">의사 결정 지점</span><span class="sxs-lookup"><span data-stu-id="63711-149">Decision point</span></span>|<ul><li><span data-ttu-id="63711-150">Teams 기능 집합이 조직의 요구 사항을 충족하는지 여부를 판단합니다.</span><span class="sxs-lookup"><span data-stu-id="63711-150">Decide whether the Teams feature set meets your organization's needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="63711-151">5단계.</span><span class="sxs-lookup"><span data-stu-id="63711-151">Step 5.</span></span> <span data-ttu-id="63711-152">거버넌스 계획</span><span class="sxs-lookup"><span data-stu-id="63711-152">Plan for governance</span></span>

<span data-ttu-id="63711-153">거버넌스에 대한 요구 사항과 거버넌스 요구 사항을 충족하는 방법을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="63711-153">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="63711-154">자세한 내용은 [Teams의 거버넌스 계획으로](plan-teams-governance.md) 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="63711-154">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/><span data-ttu-id="63711-156">의사 결정 지점</span><span class="sxs-lookup"><span data-stu-id="63711-156">Decision point</span></span>|<ul><li><span data-ttu-id="63711-157">Teams 거버넌스 계획의 지침에 따라 거버넌스 요구 사항을 [결정하고 문서화합니다.](plan-teams-governance.md)</span><span class="sxs-lookup"><span data-stu-id="63711-157">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span></li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="63711-158">6단계.</span><span class="sxs-lookup"><span data-stu-id="63711-158">Step 6.</span></span> <span data-ttu-id="63711-159">공동 작업을 위한 Teams 배포</span><span class="sxs-lookup"><span data-stu-id="63711-159">Deploy Teams for collaboration</span></span>

<span data-ttu-id="63711-160">Microsoft 365 Government – GCC에 온보드된 후 Microsoft Teams를 롤아웃하는 방법에 설명된 권장 배포 [경로를 따르는 것이 좋습니다.](How-to-roll-out-teams.md)</span><span class="sxs-lookup"><span data-stu-id="63711-160">After you've been onboarded to Microsoft 365 Government – GCC, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="63711-161">채택 및 변경 관리 팀 및 Teams 챔피언에 참여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63711-161">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="63711-162">[FastTrack](https://www.microsoft.com/fasttrack) 또는 선택한 파트너와 협력하여 서비스를 온보드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63711-162">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="63711-163">7단계.</span><span class="sxs-lookup"><span data-stu-id="63711-163">Step 7.</span></span> <span data-ttu-id="63711-164">모임 및 음성을 위한 Teams 배포</span><span class="sxs-lookup"><span data-stu-id="63711-164">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="63711-165">또한 더 광범위한 관련자 그룹과 Teams를 사용하여 모임 및 클라우드 음성 기능을 롤아웃하기 위한 계획을 시작할 [수 있는 좋은 시기입니다.](cloud-voice-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="63711-165">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](cloud-voice-deployment.md).</span></span>

