---
title: CQD(통화 품질 대시보드) 설정
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: 통화 품질 대시보드를 켜고 사용하는 방법을 알아보고 통화 품질에 대한 요약 보고서를 얻을 수 있습니다.
ms.openlocfilehash: 60363ed86e4e073b7ca5a752261ac806188900b1
ms.sourcegitcommit: ac73536f790f83a61eeb2eb8c6b71662f7bd26fc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50112842"
---
# <a name="set-up-call-quality-dashboard-cqd"></a><span data-ttu-id="362b9-103">CQD(통화 품질 대시보드) 설정</span><span class="sxs-lookup"><span data-stu-id="362b9-103">Set up Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="362b9-104">(관리자 자격 증명으로 로그인)에서 Microsoft CQD(통화 품질 대시보드)를 [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="362b9-104">Open the Microsoft Call Quality Dashboard (CQD) at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (sign in with your admin credentials).</span></span> <span data-ttu-id="362b9-105">또는 Teams 관리 센터로 이동하여 통화 품질 **대시보드를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="362b9-105">Or go to the Teams admin center and select **Call Quality Dashboard**.</span></span> 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Teams 관리 센터의 통화 품질 대시보드 단추 스크린샷":::

<span data-ttu-id="362b9-107">열리면 로그인을 **클릭하고** 전역 관리자 계정 또는 Microsoft Teams 서비스 관리자 계정 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="362b9-107">On the page that opens, click **Sign in** and enter your Global Administrator account or Microsoft Teams Service Administrator account information.</span></span> <span data-ttu-id="362b9-108">처음 로그인하면 CQD가 데이터 수집 및 처리를 시작하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="362b9-108">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="362b9-109">보고서에 의미 있는 결과를 표시하기에 충분한 데이터를 처리하기까지 한 시간 이상이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="362b9-109">Keep in mind that it may take one or more hours to process enough data to display meaningful results in the reports.</span></span>

<span data-ttu-id="362b9-110">CQD는 Microsoft Teams, 비즈니스용 Skype Online 및 비즈니스용 Skype Server 2019에 대한 전체 수준에서 통화 및 모임 품질을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="362b9-110">CQD shows call and meeting quality, at an org-wide level, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="362b9-111">비즈니스용 Skype Server 2019에서 CQD를 사용하기 위해 통화 데이터 커넥터를 [구성해야 합니다.](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector)</span><span class="sxs-lookup"><span data-stu-id="362b9-111">To use CQD with Skype for Business Server 2019, you'll have to [Configure Call Data Connector](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector).</span></span> <span data-ttu-id="362b9-112">시작하기 [전에 계획 호출 데이터 커넥터를](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="362b9-112">See [Plan Call Data Connector](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) before you start.</span></span>


## <a name="assign-admin-roles-for-access-to-cqd"></a><span data-ttu-id="362b9-113">CQD에 대한 액세스에 대한 관리자 역할 할당</span><span class="sxs-lookup"><span data-stu-id="362b9-113">Assign admin roles for access to CQD</span></span>

<span data-ttu-id="362b9-114">CQD에 액세스하기 위한 역할을 사용해야 하는 사용자에게 할당합니다. [](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="362b9-114">Assign [roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) for accessing CQD to the people who need to use it.</span></span>

<span data-ttu-id="362b9-115">관리자가 아닌 사용자(예: 지원 엔지니어 및 기술 지원 팀 에이전트)가 통화 품질 대시보드를 사용하려면 해당 사용자에게 다음 역할 중 하나를 할당하여 CQD에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="362b9-115">If you want non-admin users (such as support engineers and helpdesk agents) to use Call Quality Dashboard, you can assign those users one of the following roles, which gives access to CQD.</span></span> 


|  |<span data-ttu-id="362b9-116">보고서 보기</span><span class="sxs-lookup"><span data-stu-id="362b9-116">View reports</span></span>  |<span data-ttu-id="362b9-117">EUII 필드 보기</span><span class="sxs-lookup"><span data-stu-id="362b9-117">View EUII fields</span></span>  |<span data-ttu-id="362b9-118">보고서 만들기</span><span class="sxs-lookup"><span data-stu-id="362b9-118">Create reports</span></span>  |<span data-ttu-id="362b9-119">건물 데이터 업로드</span><span class="sxs-lookup"><span data-stu-id="362b9-119">Upload building data</span></span>  |
|---------|:-------:|:-------:|:-------:|:-------:|
|<span data-ttu-id="362b9-120">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="362b9-120">Global Administrator</span></span>     |<span data-ttu-id="362b9-121">예</span><span class="sxs-lookup"><span data-stu-id="362b9-121">Yes</span></span>         |<span data-ttu-id="362b9-122">예</span><span class="sxs-lookup"><span data-stu-id="362b9-122">Yes</span></span>         |<span data-ttu-id="362b9-123">예</span><span class="sxs-lookup"><span data-stu-id="362b9-123">Yes</span></span>         |<span data-ttu-id="362b9-124">예</span><span class="sxs-lookup"><span data-stu-id="362b9-124">Yes</span></span>         |
|<span data-ttu-id="362b9-125">Teams 서비스 관리자</span><span class="sxs-lookup"><span data-stu-id="362b9-125">Teams Service Administrator</span></span>     |<span data-ttu-id="362b9-126">예</span><span class="sxs-lookup"><span data-stu-id="362b9-126">Yes</span></span>         |<span data-ttu-id="362b9-127">예</span><span class="sxs-lookup"><span data-stu-id="362b9-127">Yes</span></span>         |<span data-ttu-id="362b9-128">예</span><span class="sxs-lookup"><span data-stu-id="362b9-128">Yes</span></span>         |<span data-ttu-id="362b9-129">예</span><span class="sxs-lookup"><span data-stu-id="362b9-129">Yes</span></span>         |
|<span data-ttu-id="362b9-130">Teams 커뮤니케이션 관리자</span><span class="sxs-lookup"><span data-stu-id="362b9-130">Teams Communications Administrator</span></span>     |<span data-ttu-id="362b9-131">예</span><span class="sxs-lookup"><span data-stu-id="362b9-131">Yes</span></span>         |<span data-ttu-id="362b9-132">예</span><span class="sxs-lookup"><span data-stu-id="362b9-132">Yes</span></span>         |<span data-ttu-id="362b9-133">예</span><span class="sxs-lookup"><span data-stu-id="362b9-133">Yes</span></span>         |<span data-ttu-id="362b9-134">예</span><span class="sxs-lookup"><span data-stu-id="362b9-134">Yes</span></span>         |
|<span data-ttu-id="362b9-135">Teams 커뮤니케이션 지원 엔지니어</span><span class="sxs-lookup"><span data-stu-id="362b9-135">Teams Communications Support Engineer</span></span>     |<span data-ttu-id="362b9-136">예</span><span class="sxs-lookup"><span data-stu-id="362b9-136">Yes</span></span>         |<span data-ttu-id="362b9-137">예</span><span class="sxs-lookup"><span data-stu-id="362b9-137">Yes</span></span>         |<span data-ttu-id="362b9-138">예</span><span class="sxs-lookup"><span data-stu-id="362b9-138">Yes</span></span>         |<span data-ttu-id="362b9-139">아니요</span><span class="sxs-lookup"><span data-stu-id="362b9-139">No</span></span>         |
|<span data-ttu-id="362b9-140">Teams Communications 지원 전문가</span><span class="sxs-lookup"><span data-stu-id="362b9-140">Teams Communications Support Specialist</span></span>     |<span data-ttu-id="362b9-141">예</span><span class="sxs-lookup"><span data-stu-id="362b9-141">Yes</span></span>         |<span data-ttu-id="362b9-142">아니요</span><span class="sxs-lookup"><span data-stu-id="362b9-142">No</span></span>         |<span data-ttu-id="362b9-143">예</span><span class="sxs-lookup"><span data-stu-id="362b9-143">Yes</span></span>         |<span data-ttu-id="362b9-144">아니요</span><span class="sxs-lookup"><span data-stu-id="362b9-144">No</span></span>         |
|<span data-ttu-id="362b9-145">비즈니스용 Skype 관리자</span><span class="sxs-lookup"><span data-stu-id="362b9-145">Skype for Business Administrator</span></span>     |<span data-ttu-id="362b9-146">예</span><span class="sxs-lookup"><span data-stu-id="362b9-146">Yes</span></span>         |<span data-ttu-id="362b9-147">예</span><span class="sxs-lookup"><span data-stu-id="362b9-147">Yes</span></span>         |<span data-ttu-id="362b9-148">예</span><span class="sxs-lookup"><span data-stu-id="362b9-148">Yes</span></span>         |<span data-ttu-id="362b9-149">예</span><span class="sxs-lookup"><span data-stu-id="362b9-149">Yes</span></span>         |
|<span data-ttu-id="362b9-150">글로벌 판독기</span><span class="sxs-lookup"><span data-stu-id="362b9-150">Global Reader</span></span> |<span data-ttu-id="362b9-151">예</span><span class="sxs-lookup"><span data-stu-id="362b9-151">Yes</span></span>         |<span data-ttu-id="362b9-152">예</span><span class="sxs-lookup"><span data-stu-id="362b9-152">Yes</span></span>         |<span data-ttu-id="362b9-153">예</span><span class="sxs-lookup"><span data-stu-id="362b9-153">Yes</span></span>         |<span data-ttu-id="362b9-154">아니요</span><span class="sxs-lookup"><span data-stu-id="362b9-154">No</span></span>         |
|<span data-ttu-id="362b9-155">보고서 읽기<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="362b9-155">Reports Reader<sup>1</sup></span></span>     |<span data-ttu-id="362b9-156">예</span><span class="sxs-lookup"><span data-stu-id="362b9-156">Yes</span></span>         |<span data-ttu-id="362b9-157">아니요</span><span class="sxs-lookup"><span data-stu-id="362b9-157">No</span></span>         |<span data-ttu-id="362b9-158">예</span><span class="sxs-lookup"><span data-stu-id="362b9-158">Yes</span></span>         |<span data-ttu-id="362b9-159">아니요</span><span class="sxs-lookup"><span data-stu-id="362b9-159">No</span></span>         |

<span data-ttu-id="362b9-160"><sup>1</sup> 보고서 읽기는 CQD 보고서를 읽는 것 [](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) 외에도 관리 센터의 모든 활동 보고서와 [Microsoft 365](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)채택 콘텐츠 팩의 모든 보고서를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="362b9-160"><sup>1</sup> In addition to reading CQD reports, the Reports Reader can view all the [activity reports](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) in the admin center and any reports from the [Microsoft 365 Adoption content pack](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).</span></span>

> [!NOTE]
> <span data-ttu-id="362b9-161">[EUII(최종](CQD-data-and-reports.md#euii-data) 사용자 식별 정보)가 표시되지 않는 경우 이 정보를 볼 수 있는 역할 중 하나만 있는 경우 CQD는 28일 동안 EUII만 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="362b9-161">If you're not seeing [EUII (end-user identifiable information)](CQD-data-and-reports.md#euii-data) and you have one of the roles that's permitted to see this information, keep in mind that CQD only keeps EUII for 28 days.</span></span> <span data-ttu-id="362b9-162">28일이 지난 모든 것은 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="362b9-162">Anything older than 28 days is deleted.</span></span>

<span data-ttu-id="362b9-163">이러한 역할에 대한 자세한 내용은 [Office 365 관리자](/office365/admin/add-users/about-admin-roles)역할 정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="362b9-163">For more information about these roles, see [About Office 365 admin roles](/office365/admin/add-users/about-admin-roles).</span></span>


<span data-ttu-id="362b9-164">처음 로그인하면 CQD가 데이터 수집 및 처리를 시작하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="362b9-164">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="362b9-165">2019년 12월을 현재 레거시 포털에서 최신 CQD(cqd.teams.microsoft.com)에 대한 링크를 제공하긴 하지만 이전 버전의 CQD(cqd.lync.com)에 계속 액세스할 수 cqd.teams.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="362b9-165">As of December 2019, you can still access the older version of CQD (cqd.lync.com), although the legacy portal gives you a link to the latest CQD (cqd.teams.microsoft.com).</span></span> <span data-ttu-id="362b9-166">결국 이전 버전의 CQD는 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="362b9-166">Eventually, the older version of CQD will be decommissioned.</span></span> <span data-ttu-id="362b9-167">2020년 7월 1일 현재 이전 버전의 CQD는 최신 CQD의 데이터에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="362b9-167">As of July 1, 2020, the older version of CQD accesses data from the latest CQD.</span></span>


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a><span data-ttu-id="362b9-168">이전 버전의 CQD에서 건물 데이터 및 보고서 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="362b9-168">Migrate building data and reports from previous version of CQD</span></span>

> [!IMPORTANT]
> <span data-ttu-id="362b9-169">2020년 7월 1일을 기점으로 이전 CQD(. https://CQD.lync.com)</span><span class="sxs-lookup"><span data-stu-id="362b9-169">As of July 1, 2020, you can no longer migrate building data and reports from the old CQD (https://CQD.lync.com).</span></span> 



## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="362b9-170">Power BI를 사용하여 CQD 데이터 분석</span><span class="sxs-lookup"><span data-stu-id="362b9-170">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="362b9-171">2020년 1월의 새로운 사항: [CQD용 Power BI 쿼리 템플릿을 다운로드합니다.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="362b9-171">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="362b9-172">CQD 데이터를 분석하고 보고하는 데 사용할 수 있는 사용자 지정 가능한 Power BI 템플릿</span><span class="sxs-lookup"><span data-stu-id="362b9-172">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="362b9-173">Power [BI를 사용하여 CQD 데이터를](CQD-Power-BI-query-templates.md) 분석하여 자세히 알아보는 방법을 읽어 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="362b9-173">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>


## <a name="related-topics"></a><span data-ttu-id="362b9-174">관련 항목</span><span class="sxs-lookup"><span data-stu-id="362b9-174">Related topics</span></span>

[<span data-ttu-id="362b9-175">Teams의 통화 품질 개선 및 모니터링</span><span class="sxs-lookup"><span data-stu-id="362b9-175">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="362b9-176">CQD란?</span><span class="sxs-lookup"><span data-stu-id="362b9-176">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="362b9-177">테넌트 업로드 및 데이터 구축</span><span class="sxs-lookup"><span data-stu-id="362b9-177">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="362b9-178">CQD 데이터 및 보고서</span><span class="sxs-lookup"><span data-stu-id="362b9-178">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="362b9-179">CQD를 사용하여 통화 및 모임 품질 관리</span><span class="sxs-lookup"><span data-stu-id="362b9-179">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="362b9-180">CQD에서 사용할 수 있는 차원 및 측정값</span><span class="sxs-lookup"><span data-stu-id="362b9-180">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="362b9-181">CQD의 스트림 분류</span><span class="sxs-lookup"><span data-stu-id="362b9-181">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="362b9-182">Power BI를 사용하여 CQD 데이터 분석</span><span class="sxs-lookup"><span data-stu-id="362b9-182">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)
