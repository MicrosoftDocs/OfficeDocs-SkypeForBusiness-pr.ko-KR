---
title: Office 365 정부-GCC 배포
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: 미국 정부의 규정에 따라 데이터를 처리 하는 엔터티에서 Office 365 배포를 구동 하는 IT 전문가를 위한 지침
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
ms.openlocfilehash: 2fb916b30a26694debf8d699fc05cc3fcc8c8c77
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581249"
---
# <a name="plan-for-office-365-government---gcc-deployments"></a><span data-ttu-id="f7acd-103">Office 365 정부의 GCC 배포 계획</span><span class="sxs-lookup"><span data-stu-id="f7acd-103">Plan for Office 365 Government - GCC deployments</span></span>

<span data-ttu-id="f7acd-104">이 지침은 office 365의 배포를 미국 연방, 주, tribal 또는 territorial 정부 기관에 제공 하는 IT 전문가를 위한 것 이며 365, 정부 규정 및 요구 사항을 준수 하는 데이터를 처리 하는 기타 엔터티에서 이러한 요구 사항을 충족 하는 데 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Office 365 Government - GCC is appropriate to meet these requirements.</span></span> <span data-ttu-id="f7acd-105">신규 3 월 26 일: 다운로드 가능한 [GCC 용 빠른 시작 가이드](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)2020를 놓치지 마세요.</span><span class="sxs-lookup"><span data-stu-id="f7acd-105">New March 26, 2020: Don't miss our downloadable [Quick Start guide for GCC](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f7acd-106">Microsoft 팀은 coronavirus (COVID-19) pandemic으로 인해 온라인 통화 및 오디오/비디오 회의에서 스파이크가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-106">Microsoft Teams is experiencing a tremendous spike in online calls and audio/video conferencing due to the coronavirus (COVID-19) pandemic.</span></span><br/>
> 
><span data-ttu-id="f7acd-107">Microsoft는 microsoft 팀의 GCC 오디오/비디오 서버를 사용 하 여 향상 된 통화를 개선 하 고 현재 정부 데이터 센터와 함께 상업용 데이터 센터에서 처리 용량을 활용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-107">In response to the unprecedented increase in calls, and to ensure continuity and availability, Microsoft is allowing Microsoft Teams GCC audio/video servers to leverage processing capacity in our commercial datacenters, as well as in our government datacenters.</span></span><br/>
> 
><span data-ttu-id="f7acd-108">이러한 오디오/비디오 서버는 미국 내 Microsoft Azure FedRAMP High 인정 경계 서버 내에 있으며 고객 콘텐츠를 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-108">These audio/video servers reside within the Microsoft Azure FedRAMP High accreditation boundary servers in the United States and do not store any customer content.</span></span> <span data-ttu-id="f7acd-109">그러나 이러한 서버는 통화와 회의에 대 한 오디오 및 비디오를 처리 하 고 있으며,이 중간 기간 동안 상업적 담당자에 게 서 작동 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-109">However, these servers are processing audio and video for calls and conferences and are operating under our commercial staff during this interim period.</span></span><br/>
> 
><span data-ttu-id="f7acd-110">선별 된 직원은 이러한 서버에 대 한 모든 대화형 로그 기능을 검토 하 여 고객 데이터에 대 한 잠재적인 액세스를 위해 이러한 서버를 모니터링 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-110">Qualified, screened personnel are monitoring these servers for potential access to customer data by reviewing any interactive log-ons to these servers.</span></span> <span data-ttu-id="f7acd-111">고객의 콘텐츠에 대 한 액세스를 위한 GCC 요구 사항을 충족 하는 자격을 갖춘 사람.</span><span class="sxs-lookup"><span data-stu-id="f7acd-111">Qualified personnel meet GCC requirements for access to customer content.</span></span> <span data-ttu-id="f7acd-112">차단 요구 사항에 대 한 자세한 내용은 [GCC 서비스 설명을](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f7acd-112">For details about screening requirements, see the [GCC service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).</span></span><br/>
> 
><span data-ttu-id="f7acd-113">이 특별 시간에 서비스가 사용 가능 하 고 안정적으로 유지 되도록 조치를 취할 때의 지원을 요청 해 주셔서 감사 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-113">Thank you for your support as we take steps to ensure that our services remain available and reliable in these extraordinary times.</span></span><br/>


> [!NOTE]
> <span data-ttu-id="f7acd-114">조직이 이미 Office 365 정부 자격 요건을 충족 하 여 프로그램에 적용 한 경우 1 ~ 2 단계를 건너뛰고 3 단계로 바로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-114">If your organization has already met the Office 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="f7acd-115">1 단계.</span><span class="sxs-lookup"><span data-stu-id="f7acd-115">Step 1.</span></span> <span data-ttu-id="f7acd-116">조직에 Office 365 정부-GCC가 필요 하며 자격 요건을 충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-116">Determine whether your organization needs Office 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="f7acd-117">Office 365 정부-GCC 환경은 FedRAMP 중간을 포함 하 여 클라우드 서비스에 대 한 미국 정부 요구 사항과 범죄 규정 및 납세 정보 시스템 (CJI 및 FTI 데이터 형식)에 대 한 요구 사항을 준수 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-117">The Office 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="f7acd-118">Office 365의 기능과 기능을 활용할 수 있을 뿐만 아니라 Office 365 정부-GCC에 고유 하 게 제공 되는 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-118">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Office 365 Government - GCC:</span></span>

-   <span data-ttu-id="f7acd-119">조직의 고객 콘텐츠는 Microsoft의 상업용 Office 365 서비스에 있는 고객 콘텐츠에서 논리적으로 분리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-119">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
-   <span data-ttu-id="f7acd-120">조직의 고객 콘텐츠는 미국 내에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-120">Your organization's customer content is stored within the United States.</span></span>
-   <span data-ttu-id="f7acd-121">조직의 고객 콘텐츠에 대 한 액세스는 차단 된 Microsoft 담당자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-121">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="f7acd-122">Office 365 정부-GCC는 미국 공공 부문 고객에 게 필요한 인증 및 accreditations을 준수 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-122">Office 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="f7acd-123">[자격 요건](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)을 포함 하 여 [Office 365 정부 기관](https://products.office.com/government/compare-office-365-government-plans)에서 미국 정부의 고객을 위한 OFFICE 365 정부-GCC 제공에 대 한 자세한 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-123">You can find more information about the Office 365 Government - GCC offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="f7acd-124">[Office 365 미국 정부의 서비스 설명은](https://technet.microsoft.com/library/mt774581.aspx) 미국 내의 모임 준수 요구 사항을 중심으로 하는 플랫폼의 이점에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-124">The [Office 365 US Government service description](https://technet.microsoft.com/library/mt774581.aspx) describes the platform's benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="f7acd-125">서비스 설명의 정보 테이블을 Excel 통합 문서로 전송 하 고 **조직 y/n과 관련** 된 두 개의 열을 추가 하 고 **조직 y/n의 요구를 충족 하는**것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-125">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="f7acd-126">그런 다음 동료와이 목록을 검토 하 여이 서비스가 조직의 요구 사항에 맞는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-126">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>

|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/><span data-ttu-id="f7acd-128">의사 결정 지점</span><span class="sxs-lookup"><span data-stu-id="f7acd-128">Decision points</span></span>|<ul><li><span data-ttu-id="f7acd-129">Office 365 정부-GCC가 조직에 적합 한지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-129">Decide whether Office 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="f7acd-130">조직이 자격 요건을 충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-130">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="f7acd-131">Office 365 정부-GCC는 미국 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-131">Office 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="f7acd-132">미국 정부의 고객이 아닌 사용자는 다양 한 [Office 365 정부 계획](https://products.office.com/en/government/compare-office-365-government-plans)중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-132">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>


## <a name="step-2-apply-for-office-365-government---gcc"></a><span data-ttu-id="f7acd-133">2 단계.</span><span class="sxs-lookup"><span data-stu-id="f7acd-133">Step 2.</span></span> <span data-ttu-id="f7acd-134">Office 365 정부-GCC 용 적용</span><span class="sxs-lookup"><span data-stu-id="f7acd-134">Apply for Office 365 Government - GCC</span></span>

<span data-ttu-id="f7acd-135">이 서비스가 조직에 적합 하다 고 결정 한 경우 [여기에서이 서비스에 적용](https://products.office.com/government/eligibility-validation)하는 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-135">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-3-understand-office-365-government---gcc-default-security-settings"></a><span data-ttu-id="f7acd-136">3 단계.</span><span class="sxs-lookup"><span data-stu-id="f7acd-136">Step 3.</span></span> <span data-ttu-id="f7acd-137">Office 365 정부 및 GCC 기본 보안 설정에 대해 이해 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-137">Understand Office 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="f7acd-138">[관리 및 보안 설정을](enable-features-office-365.md) 수정 하기 전에 신중 하 게 검토 하 고 기본 보안 설정을 변경 하기 전에 준수에 영향을 주는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-138">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/><span data-ttu-id="f7acd-140">판단 요점</span><span class="sxs-lookup"><span data-stu-id="f7acd-140">Decision point</span></span>|<ul><li><span data-ttu-id="f7acd-141">기본 Office 365 정부 보안 설정을 수정 하 고, 먼저 변경 사항에 대 한 영향을 확인 하기 위해 해결 하도록 할 것인지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-141">Decide whether you'll modify any of the default Office 365 Government - GCC security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="f7acd-142">4 단계.</span><span class="sxs-lookup"><span data-stu-id="f7acd-142">Step 4.</span></span> <span data-ttu-id="f7acd-143">기본적으로 현재 사용할 수 없거나 사용 불가능 한 기능을 파악 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-143">Understand which capabilities are currently unavailable or disabled by default.</span></span>

<span data-ttu-id="f7acd-144">귀하의 정부 클라우드 고객의 요구 사항을 충족 하기 위해 Office 365 정부-GCC와 엔터프라이즈 요금제에는 몇 가지 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-144">To accommodate the requirements of our government cloud customers, there are some differences between Office 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="f7acd-145">사용할 수 있는 기능을 확인 하려면 다음 표를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f7acd-145">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="f7acd-146">Microsoft 팀 서비스 설명</span><span class="sxs-lookup"><span data-stu-id="f7acd-146">Microsoft Teams service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

> [!Note]
> <span data-ttu-id="f7acd-147">다른 작업을 GCC 클라우드에서 완전히 사용할 수 있게 되 면 모든 추가 통합 작업이 완료 되 면 팀에서 사용할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-147">Once other workloads are fully available in the GCC cloud, then they will become available in Teams when all additional  integration work is completed.</span></span>


|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/><span data-ttu-id="f7acd-149">판단 요점</span><span class="sxs-lookup"><span data-stu-id="f7acd-149">Decision point</span></span>|<ul><li><span data-ttu-id="f7acd-150">팀 기능 집합이 조직의 요구 사항에 맞는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-150">Decide whether the Teams feature set meets your organization's needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="f7acd-151">5 단계.</span><span class="sxs-lookup"><span data-stu-id="f7acd-151">Step 5.</span></span> <span data-ttu-id="f7acd-152">관리 계획</span><span class="sxs-lookup"><span data-stu-id="f7acd-152">Plan for governance</span></span>

<span data-ttu-id="f7acd-153">관리에 대 한 요구 사항과이를 충족 하는 방법을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-153">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="f7acd-154">자세한 내용은 [팀의 관리 계획](plan-teams-governance.md) 으로 이동 하세요.</span><span class="sxs-lookup"><span data-stu-id="f7acd-154">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/><span data-ttu-id="f7acd-156">판단 요점</span><span class="sxs-lookup"><span data-stu-id="f7acd-156">Decision point</span></span>|<ul><li><span data-ttu-id="f7acd-157">[팀의 관리 계획에 대 한](plan-teams-governance.md)지침에 따라 관리 요구 사항을 결정 하 고 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-157">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span></li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="f7acd-158">6 단계.</span><span class="sxs-lookup"><span data-stu-id="f7acd-158">Step 6.</span></span> <span data-ttu-id="f7acd-159">공동 작업을 위해 팀 배포</span><span class="sxs-lookup"><span data-stu-id="f7acd-159">Deploy Teams for collaboration</span></span>

<span data-ttu-id="f7acd-160">Office 365 정부-GCC에 onboarded 한 후에 Microsoft 팀을 배포 하 [는 방법](How-to-roll-out-teams.md)에 대해 설명 하는 권장 구축 경로를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="f7acd-160">After you've been onboarded to Office 365 Government – GCC, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="f7acd-161">채택 및 변경 관리 팀과 팀이 챔피언을 사용 하 여 참여 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-161">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="f7acd-162">[Fasttrack](https://www.microsoft.com/fasttrack) 또는 선택한 파트너를 통해 서비스를 온보드 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-162">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="f7acd-163">7 단계.</span><span class="sxs-lookup"><span data-stu-id="f7acd-163">Step 7.</span></span> <span data-ttu-id="f7acd-164">모임 및 음성 용 팀 배포</span><span class="sxs-lookup"><span data-stu-id="f7acd-164">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="f7acd-165">또한 더 광범위 한 관련자 그룹의 팀을 사용 하 여 모임 및 [클라우드 음성 기능](cloud-voice-deployment.md)롤아웃 계획을 시작 하는 데는 상당한 시간이 소요 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7acd-165">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](cloud-voice-deployment.md).</span></span>

