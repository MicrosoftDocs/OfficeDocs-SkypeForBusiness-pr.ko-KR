---
title: CQD (통화 품질 대시보드) 설정
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
description: 통화 품질 대시보드를 켜고 사용 하는 방법과 통화 품질에 대 한 요약 보고서를 받는 방법을 알아봅니다.
ms.openlocfilehash: 9a864b0ad0f48e3a0bd8665b8dfeb917e67f4062
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48918640"
---
# <a name="set-up-call-quality-dashboard-cqd"></a><span data-ttu-id="4b2bd-103">CQD (통화 품질 대시보드) 설정</span><span class="sxs-lookup"><span data-stu-id="4b2bd-103">Set up Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="4b2bd-104">[https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com)(관리자 자격 증명으로 로그인)에서 CQD (Microsoft 통화 품질 대시보드)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4b2bd-104">Open the Microsoft Call Quality Dashboard (CQD) at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (sign in with your admin credentials).</span></span> <span data-ttu-id="4b2bd-105">또는 팀 관리 센터로 이동 하 여 **통화 품질 대시보드** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2bd-105">Or go to the Teams admin center and select **Call Quality Dashboard**.</span></span> 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="팀 관리 센터의 통화 품질 대시보드 단추 스크린샷":::

<span data-ttu-id="4b2bd-107">열리는 페이지에서 **로그인** 을 클릭 하 고 전역 관리자 계정 또는 Microsoft 팀 서비스 관리자 계정 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2bd-107">On the page that opens, click **Sign in** and enter your Global Administrator account or Microsoft Teams Service Admin account information.</span></span> <span data-ttu-id="4b2bd-108">처음 로그인 하면 CQD가 데이터 수집과 처리를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2bd-108">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="4b2bd-109">보고서에 의미 있는 결과를 표시 하기에 충분 한 데이터를 처리 하는 데 시간이 한 시간 이상 걸릴 수 있다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="4b2bd-109">Keep in mind that it may take one or more hours to process enough data to display meaningful results in the reports.</span></span>

<span data-ttu-id="4b2bd-110">CQD는 조직 전체 수준, Microsoft 팀, 비즈니스용 Skype Online, 비즈니스용 Skype 서버 2019 등의 통화 및 모임 품질을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="4b2bd-110">CQD shows call and meeting quality, at an org-wide level, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="4b2bd-111">비즈니스용 Skype 서버 2019에서 CQD를 사용 하려면 [Call Data Connector를 구성](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2bd-111">To use CQD with Skype for Business Server 2019, you'll have to [Configure Call Data Connector](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector).</span></span> <span data-ttu-id="4b2bd-112">시작 하기 전에 [요금제 호출 데이터 커넥터](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4b2bd-112">See [Plan Call Data Connector](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) before you start.</span></span>


## <a name="assign-admin-roles-for-access-to-cqd"></a><span data-ttu-id="4b2bd-113">CQD에 대 한 액세스 관리자 역할 할당</span><span class="sxs-lookup"><span data-stu-id="4b2bd-113">Assign admin roles for access to CQD</span></span>

<span data-ttu-id="4b2bd-114">사용 해야 하는 사용자에 게 CQD에 액세스 하기 위한 [역할](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) 을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2bd-114">Assign [roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) for accessing CQD to the people who need to use it.</span></span>

<span data-ttu-id="4b2bd-115">관리자가 아닌 사용자 (예: 지원 엔지니어 및 헬프데스크 에이전트)가 통화 품질 대시보드를 사용 하 게 하려면 다음 역할 중 하나를 할당 하 여 CQD에 대 한 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2bd-115">If you want non-admin users (such as support engineers and helpdesk agents) to use Call Quality Dashboard, you can assign those users one of the following roles, which gives access to CQD.</span></span> 


|  |<span data-ttu-id="4b2bd-116">보고서 보기</span><span class="sxs-lookup"><span data-stu-id="4b2bd-116">View reports</span></span>  |<span data-ttu-id="4b2bd-117">EUII 필드 보기</span><span class="sxs-lookup"><span data-stu-id="4b2bd-117">View EUII fields</span></span>  |<span data-ttu-id="4b2bd-118">보고서 만들기</span><span class="sxs-lookup"><span data-stu-id="4b2bd-118">Create reports</span></span>  |<span data-ttu-id="4b2bd-119">빌드 데이터 업로드</span><span class="sxs-lookup"><span data-stu-id="4b2bd-119">Upload building data</span></span>  |
|---------|:-------:|:-------:|:-------:|:-------:|
|<span data-ttu-id="4b2bd-120">Office 365 전역 관리자</span><span class="sxs-lookup"><span data-stu-id="4b2bd-120">Office 365 Global Administrator</span></span>     |<span data-ttu-id="4b2bd-121">예</span><span class="sxs-lookup"><span data-stu-id="4b2bd-121">Yes</span></span>         |<span data-ttu-id="4b2bd-122">예</span><span class="sxs-lookup"><span data-stu-id="4b2bd-122">Yes</span></span>         |<span data-ttu-id="4b2bd-123">예</span><span class="sxs-lookup"><span data-stu-id="4b2bd-123">Yes</span></span>         |<span data-ttu-id="4b2bd-124">예</span><span class="sxs-lookup"><span data-stu-id="4b2bd-124">Yes</span></span>         |
|<span data-ttu-id="4b2bd-125">Teams 서비스 관리자</span><span class="sxs-lookup"><span data-stu-id="4b2bd-125">Teams Service Administrator</span></span>     |<span data-ttu-id="4b2bd-126">예</span><span class="sxs-lookup"><span data-stu-id="4b2bd-126">Yes</span></span>         |<span data-ttu-id="4b2bd-127">예</span><span class="sxs-lookup"><span data-stu-id="4b2bd-127">Yes</span></span>         |<span data-ttu-id="4b2bd-128">예</span><span class="sxs-lookup"><span data-stu-id="4b2bd-128">Yes</span></span>         |<span data-ttu-id="4b2bd-129">예</span><span class="sxs-lookup"><span data-stu-id="4b2bd-129">Yes</span></span>         |
|<span data-ttu-id="4b2bd-130">Teams 커뮤니케이션 관리자</span><span class="sxs-lookup"><span data-stu-id="4b2bd-130">Teams Communications Administrator</span></span>     |<span data-ttu-id="4b2bd-131">예</span><span class="sxs-lookup"><span data-stu-id="4b2bd-131">Yes</span></span>         |<span data-ttu-id="4b2bd-132">예</span><span class="sxs-lookup"><span data-stu-id="4b2bd-132">Yes</span></span>         |<span data-ttu-id="4b2bd-133">예</span><span class="sxs-lookup"><span data-stu-id="4b2bd-133">Yes</span></span>         |<span data-ttu-id="4b2bd-134">예</span><span class="sxs-lookup"><span data-stu-id="4b2bd-134">Yes</span></span>         |
|<span data-ttu-id="4b2bd-135">Teams 커뮤니케이션 지원 엔지니어</span><span class="sxs-lookup"><span data-stu-id="4b2bd-135">Teams Communications Support Engineer</span></span>     |<span data-ttu-id="4b2bd-136">예</span><span class="sxs-lookup"><span data-stu-id="4b2bd-136">Yes</span></span>         |<span data-ttu-id="4b2bd-137">예</span><span class="sxs-lookup"><span data-stu-id="4b2bd-137">Yes</span></span>         |<span data-ttu-id="4b2bd-138">예</span><span class="sxs-lookup"><span data-stu-id="4b2bd-138">Yes</span></span>         |<span data-ttu-id="4b2bd-139">아니요</span><span class="sxs-lookup"><span data-stu-id="4b2bd-139">No</span></span>         |
|<span data-ttu-id="4b2bd-140">팀 의사 소통 지원 전문가</span><span class="sxs-lookup"><span data-stu-id="4b2bd-140">Teams Communications Support Specialist</span></span>     |<span data-ttu-id="4b2bd-141">예</span><span class="sxs-lookup"><span data-stu-id="4b2bd-141">Yes</span></span>         |<span data-ttu-id="4b2bd-142">아니요</span><span class="sxs-lookup"><span data-stu-id="4b2bd-142">No</span></span>         |<span data-ttu-id="4b2bd-143">예</span><span class="sxs-lookup"><span data-stu-id="4b2bd-143">Yes</span></span>         |<span data-ttu-id="4b2bd-144">아니요</span><span class="sxs-lookup"><span data-stu-id="4b2bd-144">No</span></span>         |
|<span data-ttu-id="4b2bd-145">비즈니스용 Skype 관리자</span><span class="sxs-lookup"><span data-stu-id="4b2bd-145">Skype for Business Administrator</span></span>     |<span data-ttu-id="4b2bd-146">예</span><span class="sxs-lookup"><span data-stu-id="4b2bd-146">Yes</span></span>         |<span data-ttu-id="4b2bd-147">예</span><span class="sxs-lookup"><span data-stu-id="4b2bd-147">Yes</span></span>         |<span data-ttu-id="4b2bd-148">예</span><span class="sxs-lookup"><span data-stu-id="4b2bd-148">Yes</span></span>         |<span data-ttu-id="4b2bd-149">예</span><span class="sxs-lookup"><span data-stu-id="4b2bd-149">Yes</span></span>         |
|<span data-ttu-id="4b2bd-150">Azure AD 전역 읽기 프로그램</span><span class="sxs-lookup"><span data-stu-id="4b2bd-150">Azure AD Global Reader</span></span> |<span data-ttu-id="4b2bd-151">예</span><span class="sxs-lookup"><span data-stu-id="4b2bd-151">Yes</span></span>         |<span data-ttu-id="4b2bd-152">예</span><span class="sxs-lookup"><span data-stu-id="4b2bd-152">Yes</span></span>         |<span data-ttu-id="4b2bd-153">예</span><span class="sxs-lookup"><span data-stu-id="4b2bd-153">Yes</span></span>         |<span data-ttu-id="4b2bd-154">아니요</span><span class="sxs-lookup"><span data-stu-id="4b2bd-154">No</span></span>         |
|<span data-ttu-id="4b2bd-155">Office 365 보고서 리더기<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4b2bd-155">Office 365 Reports Reader<sup>1</sup></span></span>     |<span data-ttu-id="4b2bd-156">예</span><span class="sxs-lookup"><span data-stu-id="4b2bd-156">Yes</span></span>         |<span data-ttu-id="4b2bd-157">아니요</span><span class="sxs-lookup"><span data-stu-id="4b2bd-157">No</span></span>         |<span data-ttu-id="4b2bd-158">예</span><span class="sxs-lookup"><span data-stu-id="4b2bd-158">Yes</span></span>         |<span data-ttu-id="4b2bd-159">아니요</span><span class="sxs-lookup"><span data-stu-id="4b2bd-159">No</span></span>         |

<span data-ttu-id="4b2bd-160"><sup>1</sup> CQD 보고서 읽기 외에도, Office 365 보고서 구독자는 관리 센터의 모든 [활동 보고서](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) 와 [Microsoft 365 채택 콘텐츠 팩](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)의 모든 보고서를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2bd-160"><sup>1</sup> In addition to reading CQD reports, the Office 365 Reports Reader can view all the [activity reports](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) in the admin center and any reports from the [Microsoft 365 Adoption content pack](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).</span></span>

> [!NOTE]
> <span data-ttu-id="4b2bd-161">[EUII (최종 사용자 식별 가능 정보)](CQD-data-and-reports.md#euii-data) 가 표시 되지 않고 이러한 정보를 볼 수 있는 역할 중 하나가 있는 경우 CQD는 28 일간 EUII을 유지 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="4b2bd-161">If you're not seeing [EUII (end-user identifiable information)](CQD-data-and-reports.md#euii-data) and you have one of the roles that's permitted to see this information, keep in mind that CQD only keeps EUII for 28 days.</span></span> <span data-ttu-id="4b2bd-162">28 일이 지난 모든 항목은 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b2bd-162">Anything older than 28 days is deleted.</span></span>

<span data-ttu-id="4b2bd-163">이러한 역할에 대 한 자세한 내용은 [Office 365 관리자 역할](/office365/admin/add-users/about-admin-roles)정보를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4b2bd-163">For more information about these roles, see [About Office 365 admin roles](/office365/admin/add-users/about-admin-roles).</span></span>


<span data-ttu-id="4b2bd-164">처음 로그인 하면 CQD가 데이터 수집과 처리를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2bd-164">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="4b2bd-165">2019 년 12 월 이전에는 레거시 포털에서 최신 CQD (cqd.teams.microsoft.com)에 대 한 링크를 제공 하지만이 경우에도 cqd.lync.com (c)의 오래 된 버전에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2bd-165">As of December 2019, you can still access the older version of CQD (cqd.lync.com), although the legacy portal gives you a link to the latest CQD (cqd.teams.microsoft.com).</span></span> <span data-ttu-id="4b2bd-166">결과적으로 CQD의 이전 버전이 서비스 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b2bd-166">Eventually, the older version of CQD will be decommissioned.</span></span> <span data-ttu-id="4b2bd-167">2020 년 7 월 1 일부 터, 이전 버전의 CQD는 최신 CQD의 데이터에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2bd-167">As of July 1, 2020, the older version of CQD accesses data from the latest CQD.</span></span>


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a><span data-ttu-id="4b2bd-168">이전 버전의 CQD에서 데이터 및 보고서 작성 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="4b2bd-168">Migrate building data and reports from previous version of CQD</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4b2bd-169">2020 년 7 월 1 일 현재 이전 CQD ()의 데이터 및 보고서 빌드를 더 이상 마이그레이션할 수 없습니다 https://CQD.lync.com) .</span><span class="sxs-lookup"><span data-stu-id="4b2bd-169">As of July 1, 2020, you can no longer migrate building data and reports from the old CQD (https://CQD.lync.com).</span></span> 



## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="4b2bd-170">Power BI를 사용 하 여 CQD 데이터 분석</span><span class="sxs-lookup"><span data-stu-id="4b2bd-170">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="4b2bd-171">T e 2020의 새로운 [기능: CQD 용 POWER BI 쿼리 서식 파일을 다운로드](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2bd-171">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="4b2bd-172">CQD 데이터를 분석 하 고 보고 하는 데 사용할 수 있는 사용자 지정 가능한 Power BI 서식 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="4b2bd-172">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="4b2bd-173">자세한 내용은 [POWER BI를 사용 하 여 CQD 데이터 분석을](CQD-Power-BI-query-templates.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4b2bd-173">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>


## <a name="related-topics"></a><span data-ttu-id="4b2bd-174">관련 항목</span><span class="sxs-lookup"><span data-stu-id="4b2bd-174">Related topics</span></span>

[<span data-ttu-id="4b2bd-175">팀의 통화 품질 개선 및 모니터링</span><span class="sxs-lookup"><span data-stu-id="4b2bd-175">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="4b2bd-176">CQD 란 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="4b2bd-176">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="4b2bd-177">테 넌 트 업로드 및 데이터 빌드</span><span class="sxs-lookup"><span data-stu-id="4b2bd-177">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="4b2bd-178">CQD 데이터 및 보고서</span><span class="sxs-lookup"><span data-stu-id="4b2bd-178">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="4b2bd-179">CQD를 사용 하 여 통화 및 모임 품질 관리</span><span class="sxs-lookup"><span data-stu-id="4b2bd-179">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="4b2bd-180">CQD에서 사용할 수 있는 차원과 측정값</span><span class="sxs-lookup"><span data-stu-id="4b2bd-180">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="4b2bd-181">CQD의 스트림 분류</span><span class="sxs-lookup"><span data-stu-id="4b2bd-181">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="4b2bd-182">Power BI를 사용 하 여 CQD 데이터 분석</span><span class="sxs-lookup"><span data-stu-id="4b2bd-182">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)
