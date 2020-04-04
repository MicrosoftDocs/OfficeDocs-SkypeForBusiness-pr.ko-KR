---
title: Microsoft 365 정부-GCC 상위 배포
author: lolajacobsen
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: daro
description: US 정부 규정에 대 한 데이터를 처리 하는 엔터티에서 Office 365 배포를 구동 하는 IT 전문가를 위한 지침입니다.
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
ms.openlocfilehash: 0b5111e61f6c545a7311280fa865c762e8498b86
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137818"
---
# <a name="plan-for-microsoft-365-government---gcc-high-deployments"></a><span data-ttu-id="40916-103">Microsoft 365 정부 및 GCC 고급 배포 계획</span><span class="sxs-lookup"><span data-stu-id="40916-103">Plan for Microsoft 365 Government - GCC High deployments</span></span>

<span data-ttu-id="40916-104">본 가이드는 미국 연방 정부 기관에서 Office 365의 배포를 주도하는 IT 전문가를 위한 것 이며, Microsoft 365 정부-GCC High를 사용 하는 것이 이러한 요구 사항을 충족 하는 데 적절 하 게 적용 되는 데이터를 처리 하는 기타 엔터티에서 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="40916-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Microsoft 365 Government – GCC High is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="40916-105">조직이 Microsoft 365 정부 (GCC High 자격 요구 사항)을 이미 충족 하 고이를 프로그램에 적용 한 경우에는 1 ~ 2 단계를 건너뛰고 3 단계로 바로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40916-105">If your organization has already met the Microsoft 365 Government – GCC High eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span>

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-high-and-meets-eligibility-requirements"></a><span data-ttu-id="40916-106">1 단계.</span><span class="sxs-lookup"><span data-stu-id="40916-106">Step 1.</span></span> <span data-ttu-id="40916-107">조직에 Microsoft 365 정부-GCC 이상이 필요 하며 자격 요건을 충족 하는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="40916-107">Determine whether your organization needs Microsoft 365 Government - GCC High and meets eligibility requirements.</span></span> 

<span data-ttu-id="40916-108">Microsoft 365 정부-GCC 상위 환경은 클라우드 서비스에 대 한 미국 정부의 요구 사항을 준수 합니다.</span><span class="sxs-lookup"><span data-stu-id="40916-108">The Microsoft 365 Government - GCC  High environment provides compliance with US government requirements for cloud services.</span></span> <span data-ttu-id="40916-109">Office 365의 기능과 기능을 활용할 수 있을 뿐만 아니라, Microsoft 365 정부에 고유 하 게 제공 되는 다음과 같은 기능을 통해 조직에서 다음과 같은 혜택을 누릴 수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40916-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Microsoft 365 Government – GCC High:</span></span>

- <span data-ttu-id="40916-110">조직의 고객 콘텐츠는 Microsoft의 상업용 Office 365 서비스에 있는 고객 콘텐츠에서 논리적으로 분리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40916-110">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
- <span data-ttu-id="40916-111">조직의 고객 콘텐츠는 미국 내에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40916-111">Your organization's customer content is stored within the United States.</span></span>
- <span data-ttu-id="40916-112">조직의 고객 콘텐츠에 대 한 액세스는 차단 된 Microsoft 담당자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40916-112">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
- <span data-ttu-id="40916-113">Microsoft 365 정부-GCC High는 미국 공공 부문 고객에 게 필요한 인증 및 accreditations을 준수 합니다.</span><span class="sxs-lookup"><span data-stu-id="40916-113">Microsoft 365 Government – GCC High complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="40916-114">[자격 요건](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)을 포함 하 여 [Office 365 정부 기관](https://products.office.com/government/compare-office-365-government-plans)에서 미국 정부의 고객을 위한 MICROSOFT 365 정부-GCC High 제공에 대 한 자세한 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40916-114">You can find more information about the Microsoft 365 Government – GCC High offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="40916-115">[Office 365 미국 정부의 서비스 설명은](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) 미국 내의 모임 준수 요구 사항을 중심으로 하는 플랫폼의 이점에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="40916-115">The [Office 365 US Government service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered on meeting compliance requirements within the United States.</span></span>


> [!Tip]
> <span data-ttu-id="40916-116">서비스 설명의 정보 테이블을 Excel 통합 문서로 전송 하 고 **조직 y/n과 관련** 된 두 개의 열을 추가 하 고 **조직 y/n의 요구를 충족 하는**것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="40916-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="40916-117">그런 다음 동료와이 목록을 검토 하 여이 서비스가 조직의 요구 사항에 맞는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40916-117">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>


|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/><span data-ttu-id="40916-119">의사 결정 지점</span><span class="sxs-lookup"><span data-stu-id="40916-119">Decision points</span></span>|<ul><li><span data-ttu-id="40916-120">Microsoft 365 정부-GCC 높음으로 조직에 적합 한지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="40916-120">Decide whether Microsoft 365 Government - GCC High is appropriate for your organization.</span></span></li><li><span data-ttu-id="40916-121">조직이 자격 요건을 충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="40916-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="40916-122">Microsoft 365 정부-GCC High는 미국 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40916-122">Microsoft 365 Government - GCC High is only available in the United States.</span></span> <span data-ttu-id="40916-123">미국 정부의 고객이 아닌 사용자는 다양 한 [Office 365 정부 계획](https://products.office.com/en/government/compare-office-365-government-plans)중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40916-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-apply-for-microsoft-365-government---gcc-high"></a><span data-ttu-id="40916-124">2 단계.</span><span class="sxs-lookup"><span data-stu-id="40916-124">Step 2.</span></span> <span data-ttu-id="40916-125">Microsoft 365 정부-GCC 높음으로 적용</span><span class="sxs-lookup"><span data-stu-id="40916-125">Apply for Microsoft 365 Government - GCC High</span></span>

<span data-ttu-id="40916-126">이 서비스가 조직에 적합 하다 고 결정 한 경우 [이 서비스에 대 한 적용](https://products.office.com/government/eligibility-validation)프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="40916-126">Having decided that this service is right for your organization, start the process of [applying for this service](https://products.office.com/government/eligibility-validation).</span></span>


## <a name="step-3-understand-microsoft-365-government---gcc-high-default-security-settings"></a><span data-ttu-id="40916-127">3 단계.</span><span class="sxs-lookup"><span data-stu-id="40916-127">Step 3.</span></span> <span data-ttu-id="40916-128">Microsoft 365 정부 및 GCC 고급 기본 보안 설정에 대해 이해 합니다.</span><span class="sxs-lookup"><span data-stu-id="40916-128">Understand Microsoft 365 Government - GCC High default security settings.</span></span>

<span data-ttu-id="40916-129">[관리 및 보안 설정을](enable-features-office-365.md) 수정 하기 전에 신중 하 게 검토 하 고 기본 보안 설정을 변경 하기 전에 준수에 영향을 주는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="40916-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![의사 결정 지점을 묘사하는 아이콘](media/audio_conferencing_image7.png) <br/><span data-ttu-id="40916-131">판단 요점</span><span class="sxs-lookup"><span data-stu-id="40916-131">Decision point</span></span>|<ul><li><span data-ttu-id="40916-132">기본 Microsoft 365 정부-GCC 고급 보안 설정을 수정 해야 하는지 여부를 결정 하 고, 먼저 변경할 수 있는 영향을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="40916-132">Decide whether you'll need to modify any of the default Microsoft 365 Government - GCC High security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-microsoft-365-government---gcc-high"></a><span data-ttu-id="40916-133">4 단계.</span><span class="sxs-lookup"><span data-stu-id="40916-133">Step 4.</span></span> <span data-ttu-id="40916-134">현재 Microsoft 365 정부에서 사용할 수 있는 팀 기능 이해-GCC 최고</span><span class="sxs-lookup"><span data-stu-id="40916-134">Understand which Teams capabilities are currently available in Microsoft 365 Government - GCC High</span></span>

<span data-ttu-id="40916-135">귀하의 정부 클라우드 고객의 요구 사항을 충족 하기 위해 Microsoft 365 정부-GCC 높음 팀과 엔터프라이즈 계획의 팀 간에 몇 가지 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40916-135">To accommodate the requirements of our government cloud customers, there are some differences between Teams in Microsoft 365 Government - GCC High and Teams in the Enterprise plans.</span></span> <span data-ttu-id="40916-136">사용할 수 있는 기능을 확인 하려면 다음 표를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="40916-136">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="40916-137">Microsoft 팀 서비스 설명</span><span class="sxs-lookup"><span data-stu-id="40916-137">Microsoft Teams service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="40916-138">5 단계.</span><span class="sxs-lookup"><span data-stu-id="40916-138">Step 5.</span></span> <span data-ttu-id="40916-139">관리 계획</span><span class="sxs-lookup"><span data-stu-id="40916-139">Plan for governance</span></span>

<span data-ttu-id="40916-140">관리에 대 한 요구 사항과이를 충족 하는 방법을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="40916-140">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="40916-141">자세한 내용은 [팀의 관리 계획](plan-teams-governance.md) 으로 이동 하세요.</span><span class="sxs-lookup"><span data-stu-id="40916-141">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/>|<span data-ttu-id="40916-142">판단 요점</span><span class="sxs-lookup"><span data-stu-id="40916-142">Decision point</span></span> |<ul><li><span data-ttu-id="40916-143">[팀의 관리 계획에 대 한](plan-teams-governance.md)지침에 따라 관리 요구 사항을 결정 하 고 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="40916-143">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span> </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="40916-144">6 단계.</span><span class="sxs-lookup"><span data-stu-id="40916-144">Step 6.</span></span> <span data-ttu-id="40916-145">공동 작업을 위해 팀 배포</span><span class="sxs-lookup"><span data-stu-id="40916-145">Deploy Teams for collaboration</span></span>

<span data-ttu-id="40916-146">Microsoft 365 정부-GCC High를 onboarded 후에는 [Microsoft 팀을 배포 하는 방법](How-to-roll-out-teams.md)에 대해 설명 하는 권장 되는 배포 경로를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="40916-146">After you've been onboarded to Microsoft 365 Government – GCC High, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="40916-147">채택 및 변경 관리 팀과 팀이 챔피언을 사용 하 여 참여 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40916-147">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="40916-148">[Fasttrack](https://www.microsoft.com/fasttrack) 또는 선택한 파트너를 통해 서비스를 온보드 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40916-148">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

