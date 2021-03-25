---
title: Microsoft 365 Government - GCC 높은 배포
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: daro
description: IT 프로가 미국 정부 규정에 따라 데이터를 처리하는 엔터티에서 Office 365 배포를 구동하기 위한 지침입니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c5533b6d5c2e08cb79ec8dd2052d761d86546b05
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117846"
---
# <a name="plan-for-office-365-government---gcc-high-deployments"></a><span data-ttu-id="1c7d4-103">Office 365 정부 계획 - GCC 높은 배포</span><span class="sxs-lookup"><span data-stu-id="1c7d4-103">Plan for Office 365 Government - GCC High deployments</span></span>

<span data-ttu-id="1c7d4-104">이 지침은 미국 연방 정부 기관 또는 정부 규정 및 요구 사항에 따라 데이터를 처리하는 다른 엔터티에서 Office 365 배포를 구동하는 IT 프로를 위한 것입니다. 여기서 Office 365 정부 – GCC High를 사용하는 것이 이러한 요구 사항을 충족하는 데 적합한 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="1c7d4-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Office 365 Government – GCC High is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="1c7d4-105">조직에서 이미 Office 365 정부 – GCC 높은 자격 요구 사항을 충족하고 프로그램에 적용되고 수락된 경우 1단계 및 2단계를 건너뛰고 3단계로 바로 이동하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c7d4-105">If your organization has already met the Office 365 Government – GCC High eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span>

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---gcc-high-and-meets-eligibility-requirements"></a><span data-ttu-id="1c7d4-106">1단계.</span><span class="sxs-lookup"><span data-stu-id="1c7d4-106">Step 1.</span></span> <span data-ttu-id="1c7d4-107">조직에서 Office 365 Government - GCC High가 필요하고 자격 요건을 충족하는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7d4-107">Determine whether your organization needs Office 365 Government - GCC High and meets eligibility requirements.</span></span> 

<span data-ttu-id="1c7d4-108">Office 365 Government - GCC High 환경은 클라우드 서비스에 대한 미국 정부 요구 사항을 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7d4-108">The Office 365 Government - GCC  High environment provides compliance with US government requirements for cloud services.</span></span> <span data-ttu-id="1c7d4-109">Office 365의 기능 및 기능을 즐길 뿐만 아니라 조직에서는 Office 365 Government - GCC High에 고유한 다음과 같은 기능의 이점을 누리게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c7d4-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Office 365 Government – GCC High:</span></span>

- <span data-ttu-id="1c7d4-110">조직의 고객 콘텐츠는 Microsoft의 상용 Office 365 서비스의 고객 콘텐츠와 논리적으로 나타났습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7d4-110">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
- <span data-ttu-id="1c7d4-111">조직의 고객 콘텐츠는 미국 내에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c7d4-111">Your organization's customer content is stored within the United States.</span></span>
- <span data-ttu-id="1c7d4-112">조직의 고객 콘텐츠에 대한 액세스는 심사된 Microsoft 직원으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c7d4-112">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
- <span data-ttu-id="1c7d4-113">Office 365 Government – GCC High는 미국 공공 부문 고객에게 필요한 인증 및 인증을 준수합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7d4-113">Office 365 Government – GCC High complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="1c7d4-114">자격 요건을 포함하여 Office 365 정부 계획에서 미국 정부 고객을 위한 [Office 365](https://products.office.com/government/compare-office-365-government-plans)Government – GCC High 제품에 대한 자세한 정보를 찾을 [수 있습니다.](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)</span><span class="sxs-lookup"><span data-stu-id="1c7d4-114">You can find more information about the Office 365 Government – GCC High offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="1c7d4-115">[Office 365 미국](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) 정부 서비스 설명은 미국 내 규정 준수 요구 사항을 충족하는 데 중심이 있는 플랫폼의 이점을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7d4-115">The [Office 365 US Government service description](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered on meeting compliance requirements within the United States.</span></span>


> [!Tip]
> <span data-ttu-id="1c7d4-116">서비스 설명의 정보 테이블을 Excel 통합 문서로 전송하고 내 조직 **Y/N에** 대한 관련성 및 내 조직의 요구 사항을 충족하는 두 개의 열을 추가할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="1c7d4-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="1c7d4-117">그런 다음 동료와 함께 이 목록을 검토하여 이 서비스가 조직의 요구 사항을 충족하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7d4-117">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>


|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/><span data-ttu-id="1c7d4-119">의사 결정 지점</span><span class="sxs-lookup"><span data-stu-id="1c7d4-119">Decision points</span></span>|<ul><li><span data-ttu-id="1c7d4-120">Office 365 Government - GCC High가 조직에 적합한지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7d4-120">Decide whether Office 365 Government - GCC High is appropriate for your organization.</span></span></li><li><span data-ttu-id="1c7d4-121">조직이 자격 요건을 충족하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7d4-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="1c7d4-122">Office 365 Government - GCC High는 미국에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7d4-122">Office 365 Government - GCC High is only available in the United States.</span></span> <span data-ttu-id="1c7d4-123">미국 정부가 아닌 고객은 여러 [Office 365 정부 계획에서 선택할 수 있습니다.](https://products.office.com/en/government/compare-office-365-government-plans)</span><span class="sxs-lookup"><span data-stu-id="1c7d4-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-apply-for-office-365-government---gcc-high"></a><span data-ttu-id="1c7d4-124">2단계.</span><span class="sxs-lookup"><span data-stu-id="1c7d4-124">Step 2.</span></span> <span data-ttu-id="1c7d4-125">Office 365 정부 신청 - GCC High</span><span class="sxs-lookup"><span data-stu-id="1c7d4-125">Apply for Office 365 Government - GCC High</span></span>

<span data-ttu-id="1c7d4-126">이 서비스가 조직에 적합한지 확인한 후 이 서비스에 대한 신청 [프로세스를 시작합니다.](https://products.office.com/government/eligibility-validation)</span><span class="sxs-lookup"><span data-stu-id="1c7d4-126">Having decided that this service is right for your organization, start the process of [applying for this service](https://products.office.com/government/eligibility-validation).</span></span>


## <a name="step-3-understand-office-365-government---gcc-high-default-security-settings"></a><span data-ttu-id="1c7d4-127">3단계.</span><span class="sxs-lookup"><span data-stu-id="1c7d4-127">Step 3.</span></span> <span data-ttu-id="1c7d4-128">Office 365 Government - GCC 높은 기본 보안 설정을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7d4-128">Understand Office 365 Government - GCC High default security settings.</span></span>

<span data-ttu-id="1c7d4-129">수정하기 전에 관리자 및 보안 [](enable-features-office-365.md) 설정을 신중하게 검토하고 기본 보안 설정을 변경하기 전에 규정 준수에 미치는 영향을 고려하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7d4-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/><span data-ttu-id="1c7d4-131">결정 지점</span><span class="sxs-lookup"><span data-stu-id="1c7d4-131">Decision point</span></span>|<ul><li><span data-ttu-id="1c7d4-132">기본 Office 365 Government - GCC 높은 보안 설정 중 어느 것을 수정해야 하는지 여부를 결정하여 변경 내용이 미치는 영향을 먼저 이해하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7d4-132">Decide whether you'll need to modify any of the default Office 365 Government - GCC High security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-office-365-government---gcc-high"></a><span data-ttu-id="1c7d4-133">4단계.</span><span class="sxs-lookup"><span data-stu-id="1c7d4-133">Step 4.</span></span> <span data-ttu-id="1c7d4-134">현재 Office 365 정부에서 사용할 수 있는 Teams 기능 이해 - GCC High</span><span class="sxs-lookup"><span data-stu-id="1c7d4-134">Understand which Teams capabilities are currently available in Office 365 Government - GCC High</span></span>

<span data-ttu-id="1c7d4-135">정부 클라우드 고객의 요구 사항을 수용하기 위해 Office 365 정부의 Teams - GCC High 및 Enterprise 계획의 Teams 간에 몇 가지 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7d4-135">To accommodate the requirements of our government cloud customers, there are some differences between Teams in Office 365 Government - GCC High and Teams in the Enterprise plans.</span></span> <span data-ttu-id="1c7d4-136">사용할 수 있는 기능을 보기 위해 다음 표를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7d4-136">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="1c7d4-137">Microsoft Teams 서비스 설명</span><span class="sxs-lookup"><span data-stu-id="1c7d4-137">Microsoft Teams service description</span></span>](/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="1c7d4-138">5단계.</span><span class="sxs-lookup"><span data-stu-id="1c7d4-138">Step 5.</span></span> <span data-ttu-id="1c7d4-139">거버넌스 계획</span><span class="sxs-lookup"><span data-stu-id="1c7d4-139">Plan for governance</span></span>

<span data-ttu-id="1c7d4-140">거버넌스에 대한 요구 사항 및 이러한 요구 사항을 충족하는 방법을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7d4-140">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="1c7d4-141">자세한 내용은 [Teams의 거버넌스 계획으로](plan-teams-governance.md) 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="1c7d4-141">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/>|<span data-ttu-id="1c7d4-142">결정 지점</span><span class="sxs-lookup"><span data-stu-id="1c7d4-142">Decision point</span></span> |<ul><li><span data-ttu-id="1c7d4-143">Teams의 거버넌스 계획의 지침에 따라 거버넌스 요구 사항을 [결정하고 문서화합니다.](plan-teams-governance.md)</span><span class="sxs-lookup"><span data-stu-id="1c7d4-143">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span> </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="1c7d4-144">6단계.</span><span class="sxs-lookup"><span data-stu-id="1c7d4-144">Step 6.</span></span> <span data-ttu-id="1c7d4-145">공동 작업을 위한 Teams 배포</span><span class="sxs-lookup"><span data-stu-id="1c7d4-145">Deploy Teams for collaboration</span></span>

<span data-ttu-id="1c7d4-146">Office 365 Government - GCC High에 온보디드된 후 Microsoft Teams를 롤아웃하는 방법 에 설명된 권장 배포 경로를 [따르고 있습니다.](./deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="1c7d4-146">After you've been onboarded to Office 365 Government – GCC High, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](./deploy-overview.md).</span></span> <span data-ttu-id="1c7d4-147">채택 및 변경 관리 팀 및 Teams 챔피언과 함께 참여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c7d4-147">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="1c7d4-148">[FastTrack](https://www.microsoft.com/fasttrack) 또는 선택한 파트너와 협력하여 서비스를 온보드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7d4-148">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

> [!NOTE]
> <span data-ttu-id="1c7d4-149">GCCH 환경에 대한 Mac Teams 클라이언트는 아직 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c7d4-149">The Mac Teams client for GCCH environments is not yet supported.</span></span>