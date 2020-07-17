---
title: CQD (통화 품질 대시보드의 데이터 및 보고서)
ms.author: lolaj
author: LolaJacobsen
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
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Microsoft 통화 품질 대시보드 (CQD)에서 사용할 수 있는 데이터 및 보고서에 대해 알아봅니다.
ms.openlocfilehash: 02acff8cd423901c8959e94af664ffe4d43c0e51
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086051"
---
# <a name="data-and-reports-in-call-quality-dashboard-cqd"></a><span data-ttu-id="9c1d8-103">CQD (통화 품질 대시보드의 데이터 및 보고서)</span><span class="sxs-lookup"><span data-stu-id="9c1d8-103">Data and reports in Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="9c1d8-104">CQD (Microsoft 통화 품질 대시보드)는 NRT (근거리 실시간) 데이터 피드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-104">Microsoft Call Quality Dashboard (CQD) uses a near-real-time (NRT) data feed.</span></span> <span data-ttu-id="9c1d8-105">통화 기록은 통화 종료 시간 30 분 이내에 CQD에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-105">Call records are available in CQD within 30 minutes of the end of a call.</span></span> <span data-ttu-id="9c1d8-106">NRT 파이프라인의 통화 레코드는 일부 달에만 사용할 수 있으며 데이터 집합에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-106">Call records from the NRT pipeline are only available for a few months before they are removed from the data set.</span></span> 


> [!NOTE]
> <span data-ttu-id="9c1d8-107">Advanced CQD (11 월의 새로운 2019)는 이전 CQD 파이프라인 (고급 CQD 파이프라인의 NRT 데이터를 사용 하 여 약 24 시간 동안 사용할 수 있는 통화 레코드)의 데이터를 병합 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-107">Advanced CQD (new in November 2019) merges data from the older CQD pipeline (which made call records available in about 24 hours) with NRT data from the Advanced CQD pipeline.</span></span> <span data-ttu-id="9c1d8-108">보관 기간의 데이터에 대 한 이전 및 고급 포털 쿼리는 동일한 결과를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-108">Queries on the older and Advanced portals for the data from the Archival period produce the same results.</span></span> <span data-ttu-id="9c1d8-109">N RT 데이터와 NRT 데이터 + EUII 기간에 대 한 포털의 쿼리는 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-109">Queries on either portal for the NRT Data and NRT Data + EUII periods will be different.</span></span>

## <a name="many-ways-to-access-cqd-data"></a><span data-ttu-id="9c1d8-110">CQD 데이터에 액세스 하는 다양 한 방법</span><span class="sxs-lookup"><span data-stu-id="9c1d8-110">Many ways to access CQD data</span></span>

<span data-ttu-id="9c1d8-111">여러 다른 수단으로 CQD 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-111">You can access CQD data by several different avenues.</span></span> <span data-ttu-id="9c1d8-112">요구 사항에 가장 적합 한 항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-112">Pick the one that best meets your needs:</span></span>

|  |  |
|---------|---------|
|<span data-ttu-id="9c1d8-113">팀 관리 센터 [( https://admin.teams.microsoft.com) ](https://admin.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="9c1d8-113">Teams admin center [(https://admin.teams.microsoft.com)](https://admin.teams.microsoft.com)</span></span>    | <span data-ttu-id="9c1d8-114">CQD 데이터는 팀 관리 센터의 **사용자** 페이지에 포함 되어 있으며, 읽기 쉬운 형식으로 필요한 가장 일반적인 데이터를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-114">CQD data is included on the **Users** page in the Teams admin center, showing the most common data you need in an easy-to-read format.</span></span> <span data-ttu-id="9c1d8-115">**사용자가**찾은 CQD 데이터는 사용자 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-115">You can't customize CQD data that you find under **Users**.</span></span>  |
|<span data-ttu-id="9c1d8-116">CQD 포털 [( https://cqd.teams.microsoft.com) ](https://cqd.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="9c1d8-116">CQD portal [(https://cqd.teams.microsoft.com)](https://cqd.teams.microsoft.com)</span></span>     | <span data-ttu-id="9c1d8-117">드릴스루 필터링을 사용 하 여 대부분의 요구를 충족 하는 강력한 요약 및 상세 보고서.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-117">Robust summary and detailed reports that meet most needs, with drill-through filtering.</span></span> <span data-ttu-id="9c1d8-118">CQD 포털에서 보고서를 사용자 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-118">You can also customize reports in the CQD portal.</span></span> <br><br><span data-ttu-id="9c1d8-119">CQD 포털에서 데이터를 분석 하는 데 도움이 되는 두 개의 [cqd 보고서 서식 파일](#import-the-cqd-report-templates) 을 다운로드 하세요.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-119">Get two [CQD report templates](#import-the-cqd-report-templates) to help you analyze data in the CQD portal.</span></span>       |
|<span data-ttu-id="9c1d8-120">Power BI</span><span class="sxs-lookup"><span data-stu-id="9c1d8-120">Power BI</span></span>     | <span data-ttu-id="9c1d8-121">직접 쿼리를 사용 하 여 Power BI에서 [사용자 지정 가능한 POWER bi 서식 파일](CQD-Power-BI-query-templates.md)을 사용 하 여 CQD 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-121">Use direct queries to view your CQD data in Power BI using [customizable Power BI templates](CQD-Power-BI-query-templates.md).</span></span> <span data-ttu-id="9c1d8-122">[CQD 용 POWER BI 쿼리 서식 파일을 다운로드](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-122">[Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span><br><br><span data-ttu-id="9c1d8-123">또한 REST API를 사용 하 여 Power BI를 통해 [CQD 데이터에 액세스할](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/data-api) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-123">You can also [use the REST API to access CQD data](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/data-api) through Power BI.</span></span> <span data-ttu-id="9c1d8-124">이 방법을 사용 하 여 오프 라인으로 작업할 수 있도록 CQD 데이터를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-124">Use this method if you want to download your CQD data so you can work on it offline.</span></span> <span data-ttu-id="9c1d8-125">이 방법을 사용 하면 성능이 향상 되는 데, 특히 온라인 상태일 때 Power BI에서 bog 하는 대규모 데이터 집합에 유용 하 게 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-125">The benefit of using this method is better performance, especially useful for large data sets that bog down in Power BI when you're online.</span></span>       |
|<span data-ttu-id="9c1d8-126">Graph API</span><span class="sxs-lookup"><span data-stu-id="9c1d8-126">Graph API</span></span>     | <span data-ttu-id="9c1d8-127">[GRAPH API](https://docs.microsoft.com/graph/api/resources/callrecords-api-overview?view=graph-rest-beta)를 사용 하 여 직접 통화 품질 데이터에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-127">Access call quality data yourself using the [Graph API](https://docs.microsoft.com/graph/api/resources/callrecords-api-overview?view=graph-rest-beta).</span></span> <span data-ttu-id="9c1d8-128">가장 복잡 한 방법 이지만, 통화 품질 데이터를 분석 하는 것은 대부분의 제어 및 유연성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-128">This is the most complex method, but it gives you the most control and flexibility in analyzing your call quality data.</span></span> <span data-ttu-id="9c1d8-129">예를 들어 조직의 다른 데이터와 조인 해야 하는 경우 그래프 API를 사용 하 여 데이터 모델을 만들고 통화 품질 데이터를 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-129">For example, if you need to join it with other data for your organization, you can use the Graph API to create a data model and incorporate call quality data.</span></span>        |

## <a name="import-the-cqd-report-templates"></a><span data-ttu-id="9c1d8-130">CQD 보고서 서식 파일 가져오기</span><span class="sxs-lookup"><span data-stu-id="9c1d8-130">Import the CQD report templates</span></span>

<span data-ttu-id="9c1d8-131">CQD를 사용 하 여 신속 하 게 속도를 높일 수 있도록 [두 개의 큐 레이 팅 CQD 보고서 서식 파일](https://aka.ms/qertemplates) (모든 네트워크 및 관리 되는 네트워크)을 다운로드 하세요.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-131">Download [two curated CQD report templates](https://aka.ms/qertemplates) (All Networks and Managed Networks) to help you get up to speed quickly with CQD.</span></span> <span data-ttu-id="9c1d8-132">모든 네트워크 템플릿은 빌드 데이터 파일을 사용 하 여 작업 하도록 최적화 되었지만 다음 섹션에서 설명 하는 대로 CQD에 빌드 정보를 수집 하 고 업로드 하는 데 사용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-132">The All Networks template, though optimized to work with a building data file, can be used while you work toward collecting and uploading building information into CQD, as described in the next section.</span></span>

<span data-ttu-id="9c1d8-133">**템플릿을 가져오려면 (. CQDX)를 CQDX에**</span><span class="sxs-lookup"><span data-stu-id="9c1d8-133">**To import the templates (.CQDX) into CQD**</span></span>

1. <span data-ttu-id="9c1d8-134">CQD의 경우 페이지 맨 위에 있는 메뉴에서 **상세 보고서** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-134">In CQD, select **Detailed Reports** from the menu at the top of the page.</span></span>

2. <span data-ttu-id="9c1d8-135">왼쪽 패널에서 **가져오기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-135">In the left panel, select **Import**.</span></span> <span data-ttu-id="9c1d8-136">첫 번째 CQDX 서식 파일을 찾아 **열기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-136">Browse to the first CQDX template and select **Open**.</span></span>

3. <span data-ttu-id="9c1d8-137">서식 파일을 업로드 한 후 팝업 창에 "보고서를 성공적으로 가져오기 했습니다." 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-137">After the template is uploaded, a pop-up window will display the message "Report import was successful."</span></span> 

4. <span data-ttu-id="9c1d8-138">두 번째 CQD 템플릿에 대해 2 ~ 3 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-138">Repeat steps 2 and 3 for the second CQD template.</span></span>

> [!NOTE]
> <span data-ttu-id="9c1d8-139">각 사용자는 CQD 템플릿을 해당 CQD 인스턴스로 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-139">Each user must import the CQD templates into their CQD instance.</span></span> 



## <a name="euii-data"></a><span data-ttu-id="9c1d8-140">EUII 데이터</span><span class="sxs-lookup"><span data-stu-id="9c1d8-140">EUII data</span></span>

<span data-ttu-id="9c1d8-141">준수 상의 이유로 최종 사용자 식별 가능 정보 (EUII) 데이터 (개인 식별이 가능한 정보 또는 PII 라고도 함)는 30 일간만 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-141">For compliance reasons, end-user identifiable information (EUII) data (also known as personally-identifiable information or PII) is only kept for 30 days.</span></span> <span data-ttu-id="9c1d8-142">NRT 데이터가 30 일 표시에 교차 하면 EUII를 포함 하는 필드는 지워지고 EUII-free NRT 데이터가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-142">As NRT data crosses the 30-day mark, fields that contain EUII are cleared, resulting in EUII-free NRT data.</span></span> <span data-ttu-id="9c1d8-143">EUII 데이터를 포함 하는 필드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-143">Fields that contain EUII data are:</span></span>

- <span data-ttu-id="9c1d8-144">전체 IP 주소</span><span class="sxs-lookup"><span data-stu-id="9c1d8-144">Full IP address</span></span>
- <span data-ttu-id="9c1d8-145">MAC (미디어 액세스 제어) 주소</span><span class="sxs-lookup"><span data-stu-id="9c1d8-145">Media Access Control (MAC) Address</span></span>
- <span data-ttu-id="9c1d8-146">기본 BSSID (서비스 집합 id)</span><span class="sxs-lookup"><span data-stu-id="9c1d8-146">Basic Service Set identifier (BSSID)</span></span>
- <span data-ttu-id="9c1d8-147">SIP (세션 초기화 프로토콜) URI (비즈니스용 Skype에만 해당)</span><span class="sxs-lookup"><span data-stu-id="9c1d8-147">Session Initiation Protocol (SIP) URI (Skype for Business only)</span></span>
- <span data-ttu-id="9c1d8-148">UPN (사용자 계정 이름)</span><span class="sxs-lookup"><span data-stu-id="9c1d8-148">User Principal Name (UPN)</span></span>
- <span data-ttu-id="9c1d8-149">컴퓨터 끝점 이름</span><span class="sxs-lookup"><span data-stu-id="9c1d8-149">Machine Endpoint Name</span></span>
- <span data-ttu-id="9c1d8-150">사용자 약어 피드백</span><span class="sxs-lookup"><span data-stu-id="9c1d8-150">User Verbatim Feedback</span></span>
- <span data-ttu-id="9c1d8-151">개체 ID (끝점 사용자의 Active Directory 개체 ID)</span><span class="sxs-lookup"><span data-stu-id="9c1d8-151">Object ID (the Active Directory object ID of the endpoint's user)</span></span>

### <a name="admin-roles-with-and-without-euii-access"></a><span data-ttu-id="9c1d8-152">EUII 액세스를 포함 하거나 사용 하지 않고 관리 역할</span><span class="sxs-lookup"><span data-stu-id="9c1d8-152">Admin roles with and without EUII access</span></span>

<span data-ttu-id="9c1d8-153">다음 [RBAC](https://docs.microsoft.com/azure/role-based-access-control/overview) 역할에는 EUII 액세스 **권한이 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="9c1d8-153">These [RBAC](https://docs.microsoft.com/azure/role-based-access-control/overview) roles **DO** have EUII access:</span></span>
- <span data-ttu-id="9c1d8-154">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="9c1d8-154">Global Admin</span></span>
- <span data-ttu-id="9c1d8-155">팀 서비스 관리자</span><span class="sxs-lookup"><span data-stu-id="9c1d8-155">Teams Service Admin</span></span>
- <span data-ttu-id="9c1d8-156">팀 의사 소통 관리자</span><span class="sxs-lookup"><span data-stu-id="9c1d8-156">Teams Communications Admin</span></span>
- <span data-ttu-id="9c1d8-157">Teams 커뮤니케이션 지원 엔지니어</span><span class="sxs-lookup"><span data-stu-id="9c1d8-157">Teams Communications Support Engineer</span></span>
- <span data-ttu-id="9c1d8-158">전역 읽기 프로그램</span><span class="sxs-lookup"><span data-stu-id="9c1d8-158">Global Reader</span></span>
- <span data-ttu-id="9c1d8-159">비즈니스용 Skype 관리자</span><span class="sxs-lookup"><span data-stu-id="9c1d8-159">Skype for Business Admin</span></span>

<span data-ttu-id="9c1d8-160">이 RBAC 역할에는 EUII 액세스 **권한이 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="9c1d8-160">These RBAC roles **DON'T** have EUII access:</span></span>
- <span data-ttu-id="9c1d8-161">보고서 읽기 프로그램</span><span class="sxs-lookup"><span data-stu-id="9c1d8-161">Reports Reader</span></span>
- <span data-ttu-id="9c1d8-162">팀 의사 소통 지원 전문가</span><span class="sxs-lookup"><span data-stu-id="9c1d8-162">Teams Communications Support Specialist</span></span>


## <a name="date-controls"></a><span data-ttu-id="9c1d8-163">날짜 컨트롤</span><span class="sxs-lookup"><span data-stu-id="9c1d8-163">Date controls</span></span>

<span data-ttu-id="9c1d8-164">CQD는 다음 롤링 추세 유형을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-164">CQD supports the following Rolling Trend types:</span></span>

- <span data-ttu-id="9c1d8-165">5 일</span><span class="sxs-lookup"><span data-stu-id="9c1d8-165">5-day</span></span>
- <span data-ttu-id="9c1d8-166">7 일</span><span class="sxs-lookup"><span data-stu-id="9c1d8-166">7-day</span></span>
- <span data-ttu-id="9c1d8-167">30 일</span><span class="sxs-lookup"><span data-stu-id="9c1d8-167">30-day</span></span>
- <span data-ttu-id="9c1d8-168">60-일</span><span class="sxs-lookup"><span data-stu-id="9c1d8-168">60-day</span></span>
- <span data-ttu-id="9c1d8-169">90-일</span><span class="sxs-lookup"><span data-stu-id="9c1d8-169">90-day</span></span>

<span data-ttu-id="9c1d8-170">URL 날짜 매개 변수는 Day 필드를 받아들입니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-170">The URL Date parameter accepts a Day field.</span></span> <span data-ttu-id="9c1d8-171">일 단위 보고서는 해당 추세의 마지막 날로 YYYY-MM-DD 형식으로 지정 된 날짜를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-171">Rolling-day reports use dates specified in the YYYY-MM-DD format as the last day of the trend.</span></span> <span data-ttu-id="9c1d8-172">URL 날짜 매개 변수 "00"은 "오늘"을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-172">The URL Date parameter “00”  indicates “today”.</span></span>

|<span data-ttu-id="9c1d8-173">URL</span><span class="sxs-lookup"><span data-stu-id="9c1d8-173">URL</span></span>| <span data-ttu-id="9c1d8-174">롤링 일 추세의 종료 날짜</span><span class="sxs-lookup"><span data-stu-id="9c1d8-174">End date of Rolling Day Trend</span></span>|
|:---|:---|
|<span data-ttu-id="9c1d8-175"><span>https:// <cqdv3> /spd/#/쇄선/ <reportid> /2019-02/</span></span><span class="sxs-lookup"><span data-stu-id="9c1d8-175"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/2019-02/</span></span></span>   |<span data-ttu-id="9c1d8-176">현재 날짜 2 월 2019</span><span class="sxs-lookup"><span data-stu-id="9c1d8-176">Current Day of Feb 2019</span></span>|
|<span data-ttu-id="9c1d8-177"><span>https:// <cqdv3> /spd/#/쇄선/ <reportid> /2019-02-15/</span></span><span class="sxs-lookup"><span data-stu-id="9c1d8-177"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/2019-02-15/</span></span></span>|<span data-ttu-id="9c1d8-178">2 월 15 일 2019</span><span class="sxs-lookup"><span data-stu-id="9c1d8-178">Feb 15, 2019</span></span>|
|<span data-ttu-id="9c1d8-179"><span>https:// <cqdv3> /spd/#/쇄선/ <reportid> /00/</span></span><span class="sxs-lookup"><span data-stu-id="9c1d8-179"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/00/</span></span></span>        |<span data-ttu-id="9c1d8-180">현재 일</span><span class="sxs-lookup"><span data-stu-id="9c1d8-180">Current Day</span></span>|
|||

<span data-ttu-id="9c1d8-181">기본적으로 현재 날짜는 이동 하는 일 추세의 마지막 날로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-181">By default, the current day of the month is used as the last day of the Rolling Day Trend.</span></span>


## <a name="data-available-in-cqd-reports"></a><span data-ttu-id="9c1d8-182">CQD 보고서에서 사용할 수 있는 데이터</span><span class="sxs-lookup"><span data-stu-id="9c1d8-182">Data available in CQD reports</span></span>

<span data-ttu-id="9c1d8-183">기본 요약 및 세부 CQD 보고서는 조직의 통화 품질을 관리 하는 데 필요할 수 있습니다. 필요한 경우 [사용자 지정 보고서를 만들](#create-custom-detailed-reports)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-183">The default summary and detailed CQD reports may be all you need to manage call quality for your org. If you need to, you can [create custom reports](#create-custom-detailed-reports).</span></span> 

<span data-ttu-id="9c1d8-184">Power BI를 사용 하 여 CQD 데이터를 분석 하려면 [POWER bi를 사용 하 여 팀에 대 한 CQD 데이터 분석](CQD-Power-BI-query-templates.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-184">If you want to use Power BI to analyze your CQD data, read [Use Power BI to analyze CQD data for Teams](CQD-Power-BI-query-templates.md).</span></span>

|<span data-ttu-id="9c1d8-185">기능</span><span class="sxs-lookup"><span data-stu-id="9c1d8-185">Feature</span></span>|<span data-ttu-id="9c1d8-186">요약 보고서</span><span class="sxs-lookup"><span data-stu-id="9c1d8-186">Summary Reports</span></span>|<span data-ttu-id="9c1d8-187">자세한 보고서</span><span class="sxs-lookup"><span data-stu-id="9c1d8-187">Detailed Reports</span></span>|
|:--- |:--- |:--- |
|<span data-ttu-id="9c1d8-188">응용 프로그램 공유 메트릭</span><span class="sxs-lookup"><span data-stu-id="9c1d8-188">Application sharing metric</span></span> | <span data-ttu-id="9c1d8-189">아니요</span><span class="sxs-lookup"><span data-stu-id="9c1d8-189">No</span></span> | <span data-ttu-id="9c1d8-190">예</span><span class="sxs-lookup"><span data-stu-id="9c1d8-190">Yes</span></span> |
|<span data-ttu-id="9c1d8-191">고객 건물 정보 지원</span><span class="sxs-lookup"><span data-stu-id="9c1d8-191">Customer building information support</span></span> | <span data-ttu-id="9c1d8-192">예</span><span class="sxs-lookup"><span data-stu-id="9c1d8-192">Yes</span></span> | <span data-ttu-id="9c1d8-193">예</span><span class="sxs-lookup"><span data-stu-id="9c1d8-193">Yes</span></span> |
|<span data-ttu-id="9c1d8-194">고객 끝점 정보 지원</span><span class="sxs-lookup"><span data-stu-id="9c1d8-194">Customer endpoint information support</span></span> | <span data-ttu-id="9c1d8-195">Cqd.teams.microsoft.com 에서만 <span><span/></span><span class="sxs-lookup"><span data-stu-id="9c1d8-195">Only in <span>cqd.teams.microsoft.com<span/></span></span> | <span data-ttu-id="9c1d8-196">Cqd.teams.microsoft.com 에서만 <span><span/></span><span class="sxs-lookup"><span data-stu-id="9c1d8-196">Only in <span>cqd.teams.microsoft.com<span/></span></span> |
|<span data-ttu-id="9c1d8-197">드릴 다운 분석 지원</span><span class="sxs-lookup"><span data-stu-id="9c1d8-197">Drill down analysis support</span></span>   | <span data-ttu-id="9c1d8-198">아니요</span><span class="sxs-lookup"><span data-stu-id="9c1d8-198">No</span></span>   | <span data-ttu-id="9c1d8-199">예</span><span class="sxs-lookup"><span data-stu-id="9c1d8-199">Yes</span></span>   |
|<span data-ttu-id="9c1d8-200">미디어 안정성 메트릭</span><span class="sxs-lookup"><span data-stu-id="9c1d8-200">Media reliability metrics</span></span>   | <span data-ttu-id="9c1d8-201">아니요</span><span class="sxs-lookup"><span data-stu-id="9c1d8-201">No</span></span>   | <span data-ttu-id="9c1d8-202">예</span><span class="sxs-lookup"><span data-stu-id="9c1d8-202">Yes</span></span>   |
|<span data-ttu-id="9c1d8-203">오래 된 보고서</span><span class="sxs-lookup"><span data-stu-id="9c1d8-203">Out-of-the-box reports</span></span>   | <span data-ttu-id="9c1d8-204">예</span><span class="sxs-lookup"><span data-stu-id="9c1d8-204">Yes</span></span>   | <span data-ttu-id="9c1d8-205">예</span><span class="sxs-lookup"><span data-stu-id="9c1d8-205">Yes</span></span>   |
|<span data-ttu-id="9c1d8-206">개요 보고서</span><span class="sxs-lookup"><span data-stu-id="9c1d8-206">Overview reports</span></span>   | <span data-ttu-id="9c1d8-207">예</span><span class="sxs-lookup"><span data-stu-id="9c1d8-207">Yes</span></span>   | <span data-ttu-id="9c1d8-208">예</span><span class="sxs-lookup"><span data-stu-id="9c1d8-208">Yes</span></span>   |
|<span data-ttu-id="9c1d8-209">사용자 단위 보고서 집합</span><span class="sxs-lookup"><span data-stu-id="9c1d8-209">Per-user report set</span></span>   | <span data-ttu-id="9c1d8-210">아니요</span><span class="sxs-lookup"><span data-stu-id="9c1d8-210">No</span></span>   | <span data-ttu-id="9c1d8-211">예</span><span class="sxs-lookup"><span data-stu-id="9c1d8-211">Yes</span></span>   |
|<span data-ttu-id="9c1d8-212">보고서 집합 사용자 지정 (보고서 추가, 삭제, 수정)</span><span class="sxs-lookup"><span data-stu-id="9c1d8-212">Report set customization (add, delete, modify reports)</span></span>   | <span data-ttu-id="9c1d8-213">아니요</span><span class="sxs-lookup"><span data-stu-id="9c1d8-213">No</span></span>   | <span data-ttu-id="9c1d8-214">예</span><span class="sxs-lookup"><span data-stu-id="9c1d8-214">Yes</span></span>   |
|<span data-ttu-id="9c1d8-215">비디오 기반 화면 공유 메트릭</span><span class="sxs-lookup"><span data-stu-id="9c1d8-215">Video-based screen sharing metrics</span></span>   | <span data-ttu-id="9c1d8-216">아니요</span><span class="sxs-lookup"><span data-stu-id="9c1d8-216">No</span></span>   | <span data-ttu-id="9c1d8-217">예</span><span class="sxs-lookup"><span data-stu-id="9c1d8-217">Yes</span></span>   |
|<span data-ttu-id="9c1d8-218">비디오 메트릭</span><span class="sxs-lookup"><span data-stu-id="9c1d8-218">Video metrics</span></span>   | <span data-ttu-id="9c1d8-219">아니요</span><span class="sxs-lookup"><span data-stu-id="9c1d8-219">No</span></span>   | <span data-ttu-id="9c1d8-220">예</span><span class="sxs-lookup"><span data-stu-id="9c1d8-220">Yes</span></span>   |
|<span data-ttu-id="9c1d8-221">사용할 수 있는 데이터 양</span><span class="sxs-lookup"><span data-stu-id="9c1d8-221">Amount of data available</span></span>   | <span data-ttu-id="9c1d8-222">지난 12 개월</span><span class="sxs-lookup"><span data-stu-id="9c1d8-222">Last 12 months</span></span>   | <span data-ttu-id="9c1d8-223">지난 12 개월</span><span class="sxs-lookup"><span data-stu-id="9c1d8-223">Last 12 months</span></span>   |
|<span data-ttu-id="9c1d8-224">Microsoft 팀 데이터</span><span class="sxs-lookup"><span data-stu-id="9c1d8-224">Microsoft Teams data</span></span>   | <span data-ttu-id="9c1d8-225">예</span><span class="sxs-lookup"><span data-stu-id="9c1d8-225">Yes</span></span>   | <span data-ttu-id="9c1d8-226">예</span><span class="sxs-lookup"><span data-stu-id="9c1d8-226">Yes</span></span>   |
| | | |


 
### <a name="select-product-data-to-see-in-reports"></a><span data-ttu-id="9c1d8-227">보고서에 표시할 제품 데이터 선택</span><span class="sxs-lookup"><span data-stu-id="9c1d8-227">Select product data to see in reports</span></span>

<span data-ttu-id="9c1d8-228">요약 및 위치 향상 보고서에서 **제품 필터** 드롭다운을 사용 하 여 모든 제품 데이터, Microsoft 팀 데이터만 표시 하거나 비즈니스용 Skype Online 데이터만 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-228">In the Summary and Location-Enhanced Reports, you can use the **Product Filter** drop-down to show all product data, only Microsoft Teams data, or only Skype for Business Online data.</span></span>
  
![스크린샷: 제품 필터 컨트롤 옵션을 표시 합니다.](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
<span data-ttu-id="9c1d8-230">자세한 보고서에서는 **Is 팀** 차원을 사용 하 여 데이터를 Microsoft 팀 또는 비즈니스용 Skype Online 데이터로 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-230">In Detailed reports, you can use the **Is Teams** dimension to filter the data to Microsoft Teams or Skype for Business Online data.</span></span>

## <a name="summary-reports"></a><span data-ttu-id="9c1d8-231">요약 보고서</span><span class="sxs-lookup"><span data-stu-id="9c1d8-231">Summary Reports</span></span>

<span data-ttu-id="9c1d8-232">다음은 CQD에 처음 로그인 할 때 CQD 대시보드에 표시 되는 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-232">These are the reports that you'll see on the CQD Dashboard when you first sign in to CQD.</span></span> <span data-ttu-id="9c1d8-233">이를 통해 일일, 월간 및 테이블 보고서를 사용 하 여 품질이 나쁜 서브넷을 식별 하는 데 도움이 되는 품질 추세를 한눈에 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-233">They give you an at-a-glance look at quality trends with daily, monthly, and table reports to assist with identifying subnets that have poor quality.</span></span> 

|<span data-ttu-id="9c1d8-234">탭</span><span class="sxs-lookup"><span data-stu-id="9c1d8-234">Tab</span></span>  |  |
|---------|---------|
|<span data-ttu-id="9c1d8-235">전체 통화 음질</span><span class="sxs-lookup"><span data-stu-id="9c1d8-235">Overall Call Quality</span></span>     | <span data-ttu-id="9c1d8-236">다른 3 개의 탭 집계</span><span class="sxs-lookup"><span data-stu-id="9c1d8-236">Aggregate of the other 3 tabs</span></span>        |
|<span data-ttu-id="9c1d8-237">Server-클라이언트</span><span class="sxs-lookup"><span data-stu-id="9c1d8-237">Server—Client</span></span>     |<span data-ttu-id="9c1d8-238">서버 및 클라이언트 끝점 간 스트림에 대 한 세부 정보</span><span class="sxs-lookup"><span data-stu-id="9c1d8-238">Details of the streams between server and client endpoints</span></span>         |
|<span data-ttu-id="9c1d8-239">클라이언트-클라이언트</span><span class="sxs-lookup"><span data-stu-id="9c1d8-239">Client—Client</span></span>     |<span data-ttu-id="9c1d8-240">두 클라이언트 끝점 간 스트림의 세부 정보</span><span class="sxs-lookup"><span data-stu-id="9c1d8-240">Details of the streams between two client endpoints</span></span>         |
|<span data-ttu-id="9c1d8-241">음성 품질 SLA</span><span class="sxs-lookup"><span data-stu-id="9c1d8-241">Voice Quality SLA</span></span>     |<span data-ttu-id="9c1d8-242">비즈니스용 Skype 음성 품질 [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252) 에 포함 된 통화에 대 한 정보</span><span class="sxs-lookup"><span data-stu-id="9c1d8-242">Info about calls included in the Skype for Business voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)</span></span>         |

### <a name="overall-call-quality-tab"></a><span data-ttu-id="9c1d8-243">전체 통화 음질 탭</span><span class="sxs-lookup"><span data-stu-id="9c1d8-243">Overall Call Quality tab</span></span>

<span data-ttu-id="9c1d8-244">이 탭의 데이터를 사용 하 여 통화 품질 상태와 스트림 개수 및 낮은 백분율을 기준으로 추세를 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-244">Use the data on this tab to evaluate call quality status and trends based on stream counts and poor percentages.</span></span> <span data-ttu-id="9c1d8-245">오른쪽 위 모서리에 있는 범례는 이러한 메트릭을 나타내는 색 및 시각적 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-245">The legend in the upper-right corner shows which color and visual elements represent these metrics.</span></span>
  
![스크린샷: 통화 품질 탭 표시](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
<span data-ttu-id="9c1d8-247">스트림은 세 가지 그룹 (좋음, 나쁨, 미분류)으로 분류 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-247">Streams are classified in three groups: Good, Poor, and Unclassified.</span></span> <span data-ttu-id="9c1d8-248">또한 총 분류 스트림 개수에 *좋지* 않은 스트림의 비율을 제공 하는 *불량%* 값이 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-248">There are also calculated  *Poor %*  values that give you the ratio of streams classified as *Poor*  to the total classified stream count.</span></span> <span data-ttu-id="9c1d8-249">*불량% = 불량 스트림/(불량 스트림 + 양호한 스트림) \* 100*의 경우 *잘못 된%* 가 여러 개의 *분류* 되지 않은 스트림의 존재 여부에 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-249">Since *Poor % = Poor streams/ (Poor streams+ Good streams) \* 100*, the *Poor %*  is unaffected by the presence of multiple *Unclassified*  streams.</span></span> <span data-ttu-id="9c1d8-250">스트림이 불량 또는 양호한 것으로 분류 하는 것을 확인 하려면 [통화 품질 대시보드의 스트림 분류](stream-classification-in-call-quality-dashboard.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-250">To see what classifies a stream as poor or good, refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md).</span></span>
  
<span data-ttu-id="9c1d8-251">왼쪽의 배율을 사용 하 여 스트림 개수 값을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-251">Use the scale on the left to measure the stream count values.</span></span>
  
![스크린샷: 스트림 개수 값 표시](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
<span data-ttu-id="9c1d8-253">오른쪽의 배율을 사용 하 여 불량% 값을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-253">Use the scale on the right to measure the Poor % values.</span></span>
  
![스크린샷: 불량% 값 표시](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
<span data-ttu-id="9c1d8-255">막대 위로 마우스를 가져가면 실제 숫자 값을 구할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-255">You can also obtain the actual numerical values by hovering the mouse over a bar.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9c1d8-256">다음 예제는 매우 작은 샘플 데이터 집합에서 가져온 것 이며, 실제 배포에 대해 값이 사실적이 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-256">The following example is from a very small sample data set, and the values aren't realistic for an actual deployment.</span></span>
  
![스크린샷: 데이터에 액세스 하는 데 사용 되는 마우스 표시](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
<span data-ttu-id="9c1d8-258">전체 스트림 볼륨은 계산 된 낮은 백분율이 얼마나 적절 하지 않을 지 결정 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-258">The overall stream volume helps determine how relevant the calculated Poor percentages are.</span></span> <span data-ttu-id="9c1d8-259">전체 스트림의 볼륨이 작을수록 낮은 신뢰 값이 신고 된 것으로 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-259">The smaller the volume of overall streams, the less reliable the reported Poor percentage values are.</span></span>
  
### <a name="server-client-tab-and-client-client-tabs"></a><span data-ttu-id="9c1d8-260">서버-클라이언트 탭 및 클라이언트 클라이언트 탭</span><span class="sxs-lookup"><span data-stu-id="9c1d8-260">Server-Client tab and Client-Client tabs</span></span>

<span data-ttu-id="9c1d8-261">이러한 두 탭은 끝점 대 끝점 시나리오에서 발생 한 스트림에 대 한 세부 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-261">These two tabs provide details for the streams that took place in their endpoint-to-endpoint scenarios.</span></span> <span data-ttu-id="9c1d8-262">서버 클라이언트 탭에는 미디어 스트림이 흐르는 네 가지 시나리오를 나타내는 4 개의 축소할 수 있는 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-262">The Server-Client tab has four collapsible sections that represent four scenarios under which media streams would flow.</span></span>
  
- <span data-ttu-id="9c1d8-263">유선 내부</span><span class="sxs-lookup"><span data-stu-id="9c1d8-263">Wired Inside</span></span>
- <span data-ttu-id="9c1d8-264">유선 외부</span><span class="sxs-lookup"><span data-stu-id="9c1d8-264">Wired Outside</span></span>
- <span data-ttu-id="9c1d8-265">WiFi 내부</span><span class="sxs-lookup"><span data-stu-id="9c1d8-265">WiFi Inside</span></span>
- <span data-ttu-id="9c1d8-266">WiFi 외부</span><span class="sxs-lookup"><span data-stu-id="9c1d8-266">WiFi Outside</span></span>

<span data-ttu-id="9c1d8-267">마찬가지로, 클라이언트-클라이언트 탭에는 다음과 같은 5 개의 축소 가능 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-267">Similarly, the Client-Client tab has five collapsible sections:</span></span>

- <span data-ttu-id="9c1d8-268">유선 내부-유선 내부</span><span class="sxs-lookup"><span data-stu-id="9c1d8-268">Wired Inside — Wired Inside</span></span>
- <span data-ttu-id="9c1d8-269">유선 내부-유선 외부</span><span class="sxs-lookup"><span data-stu-id="9c1d8-269">Wired Inside — Wired Outside</span></span>
- <span data-ttu-id="9c1d8-270">유선 외부-유선 외부</span><span class="sxs-lookup"><span data-stu-id="9c1d8-270">Wired Outside — Wired Outside</span></span>
- <span data-ttu-id="9c1d8-271">유선 내부-WiFi 내부</span><span class="sxs-lookup"><span data-stu-id="9c1d8-271">Wired Inside — WiFi Inside</span></span>
- <span data-ttu-id="9c1d8-272">유선 내부-WiFi 외부</span><span class="sxs-lookup"><span data-stu-id="9c1d8-272">Wired Inside — WiFi Outside</span></span>

#### <a name="inside-versus-outside"></a><span data-ttu-id="9c1d8-273">내부 및 외부</span><span class="sxs-lookup"><span data-stu-id="9c1d8-273">Inside versus Outside</span></span>

<span data-ttu-id="9c1d8-274">CQD는 스트림을 빌드 정보 (있는 경우)를 사용 하 여 *내부* 또는 *외부로* 분류 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-274">CQD classifies a stream as  *Inside*  or *Outside*  using Building information, if it exists.</span></span> <span data-ttu-id="9c1d8-275">각 스트림의 끝점은 서브넷 주소와 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-275">Endpoints of each stream are associated with a subnet address.</span></span> <span data-ttu-id="9c1d8-276">서브넷이 업로드 된 빌드 정보에서 InsideCorp로 표시 된 서브넷 목록에 있는 경우 *내부*로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-276">If the subnet is in the list of the subnets marked InsideCorp in the uploaded Building information, then it is considered *Inside*.</span></span> <span data-ttu-id="9c1d8-277">@ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ *Outside*@ @ @ @ @ @ @ @ @ @ @ Test</span><span class="sxs-lookup"><span data-stu-id="9c1d8-277">If Building information has not yet been uploaded, then Inside Test always classifies the streams as *Outside*.</span></span> 

<span data-ttu-id="9c1d8-278">서버 클라이언트 시나리오의 내부 테스트에서는 클라이언트 끝점만 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-278">The Inside Test for a Server-Client scenario only considers the client endpoint.</span></span> <span data-ttu-id="9c1d8-279">서버는 항상 사용자의 관점에서 벗어나므로이는 테스트에서 고려 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-279">Because servers are always outside from a user's perspective, this isn't accounted for in the test.</span></span>
  
#### <a name="wired-versus-wifi"></a><span data-ttu-id="9c1d8-280">유선 및 WiFi</span><span class="sxs-lookup"><span data-stu-id="9c1d8-280">Wired versus WiFi</span></span>

<span data-ttu-id="9c1d8-281">이름이 나타내는 대로 분류 조건은 클라이언트 연결 유형을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-281">As the names indicate, the classification criteria is based on the type of client connections.</span></span> <span data-ttu-id="9c1d8-282">서버는 항상 유선 이며 계산에 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-282">Server is always wired and it isn't included in the calculation.</span></span> <span data-ttu-id="9c1d8-283">지정 된 스트림에서 두 끝점 중 하나가 WiFi 네트워크에 연결 되어 있는 경우 CQD는이를 WiFi로 분류 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-283">In a given stream, if one of the two endpoints is connected to a WiFi network, then CQD classifies it as WiFi.</span></span>
> [!NOTE]
> <span data-ttu-id="9c1d8-284">두 끝점 중 하나가 WiFi 네트워크에 연결 되어 있는 경우 스트림이 제공 되 면 CQD에서 WiFi로 분류 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-284">Given a stream, if one of the two endpoints is connected to a WiFi network, then it is classified as WiFi in CQD.</span></span>
  
  
## <a name="tenant-data-information"></a><span data-ttu-id="9c1d8-285">테 넌 트 데이터 정보</span><span class="sxs-lookup"><span data-stu-id="9c1d8-285">Tenant Data information</span></span>

<span data-ttu-id="9c1d8-286">CQD 요약 보고서 대시보드의 오른쪽 위 모서리에 있는 설정 메뉴에서 **테 넌 트 데이터 업로드** 를 선택 하 여 액세스 하는 **테 넌 트 데이터 업로드** 페이지가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-286">The CQD Summary Reports dashboard includes a **Tenant Data Upload** page, accessed by selecting **Tenant Data Upload** from the settings menu in the top-right corner.</span></span> <span data-ttu-id="9c1d8-287">이 페이지는 관리자가 다음과 같은 자신의 정보를 업로드 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-287">This page is used for admins to upload their own information, such as:</span></span>

- <span data-ttu-id="9c1d8-288">IP 주소 및 지리 정보의 지도</span><span class="sxs-lookup"><span data-stu-id="9c1d8-288">A map of IP address and geographical information</span></span>
- <span data-ttu-id="9c1d8-289">각 무선 AP 및 MAC 주소의 지도</span><span class="sxs-lookup"><span data-stu-id="9c1d8-289">A map of each wireless AP and its MAC address</span></span>
- <span data-ttu-id="9c1d8-290">끝점을 끝점으로 설정/모델/형식 등으로 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-290">A map of Endpoint to Endpoint Make/Model/Type, etc.</span></span>
  
<span data-ttu-id="9c1d8-291">테 넌 트, 빌드 및 위치 데이터를 업로드 하는 것이 좋으며,이 정보는 CQD가 보고서에 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-291">We recommend that you upload your tenant, building, and location data so CQD can include this information in your reports.</span></span> <span data-ttu-id="9c1d8-292">이 데이터를 아직 업로드 하지 않은 경우에는 [테 넌 트 업로드 및 데이터 작성](CQD-upload-tenant-building-data.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-292">If you haven't already uploaded this data, read [Upload tenant and building data](CQD-upload-tenant-building-data.md).</span></span> 


## <a name="detailed-reports"></a><span data-ttu-id="9c1d8-293">자세한 보고서</span><span class="sxs-lookup"><span data-stu-id="9c1d8-293">Detailed reports</span></span>

|<span data-ttu-id="9c1d8-294">이름</span><span class="sxs-lookup"><span data-stu-id="9c1d8-294">Name</span></span>  |  |
|---------|---------|
|<span data-ttu-id="9c1d8-295">위치 향상 보고서</span><span class="sxs-lookup"><span data-stu-id="9c1d8-295">Location-Enhanced Reports</span></span>     |<span data-ttu-id="9c1d8-296">위치 정보를 기준으로 품질 추세를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-296">Shows quality trends based on location information.</span></span> <span data-ttu-id="9c1d8-297">이 보고서는 [테 넌 트 데이터를 업로드](CQD-upload-tenant-building-data.md)한 경우에만 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-297">This report appears only if you've [uploaded your tenant data](CQD-upload-tenant-building-data.md).</span></span>        |
|<span data-ttu-id="9c1d8-298">안정성 보고서</span><span class="sxs-lookup"><span data-stu-id="9c1d8-298">Reliability Reports</span></span>     |<span data-ttu-id="9c1d8-299">오디오, 비디오, 비디오 기반 화면 공유 (VBSS), 앱 공유 보고서가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-299">Includes audio, video, video-based screen sharing (VBSS), and app sharing reports</span></span>         |
|<span data-ttu-id="9c1d8-300">경력 보고서의 품질</span><span class="sxs-lookup"><span data-stu-id="9c1d8-300">Quality of Experience Reports</span></span>     |<span data-ttu-id="9c1d8-301">회의실을 비롯 한 모든 클라이언트 및 장치에 대 한 오디오 품질 및 안정성</span><span class="sxs-lookup"><span data-stu-id="9c1d8-301">Audio quality and reliability for all clients and devices, including meeting rooms.</span></span> <span data-ttu-id="9c1d8-302">이러한 보고서는 다운로드 가능한 [Cqd 템플릿의](https://aka.ms/QERtemplates)"slimmed" 버전으로, 오디오 품질 및 안정성 분석을 위한 주요 영역에 중점을 두는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-302">These reports are a “slimmed-down” version of the downloadable [CQD templates](https://aka.ms/QERtemplates), focusing on key areas for analyzing audio quality and reliability.</span></span>         |
|<span data-ttu-id="9c1d8-303">품질 드릴 다운 보고서</span><span class="sxs-lookup"><span data-stu-id="9c1d8-303">Quality Drill Down Reports</span></span>     | <span data-ttu-id="9c1d8-304">드릴 다운: 지역, 위치, 서브넷, 시간 및 사용자 기준 날짜</span><span class="sxs-lookup"><span data-stu-id="9c1d8-304">Drill downs: Date by region, locations, subnets, hour, and users</span></span>         |
|<span data-ttu-id="9c1d8-305">오류 드릴 다운 보고서</span><span class="sxs-lookup"><span data-stu-id="9c1d8-305">Failure Drill Down Reports</span></span>     | <span data-ttu-id="9c1d8-306">드릴 다운: 지역, 위치, 서브넷, 시간 및 사용자 기준 날짜</span><span class="sxs-lookup"><span data-stu-id="9c1d8-306">Drill downs: Date by region, locations, subnets, hour, and users</span></span>        |
|<span data-ttu-id="9c1d8-307">내 통화 보고서 평가</span><span class="sxs-lookup"><span data-stu-id="9c1d8-307">Rate My Call Reports</span></span>     |<span data-ttu-id="9c1d8-308">지역, 위치 또는 사용자별로 사용자 통화 등급을 분석 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-308">Analyze user call ratings by region, location, or by user.</span></span> <span data-ttu-id="9c1d8-309">약어에 대 한 피드백을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-309">Includes verbatim feedback.</span></span>         |
|<span data-ttu-id="9c1d8-310">지원 센터 보고서</span><span class="sxs-lookup"><span data-stu-id="9c1d8-310">Help Desk Reports</span></span>     |<span data-ttu-id="9c1d8-311">지원 센터 보고서는 개별 사용자, 사용자 그룹 또는 모두에 대 한 통화 및 모임 데이터를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-311">Help Desk Reports look at call and meeting data for individual users, groups of users, or everyone.</span></span> <span data-ttu-id="9c1d8-312">이 보고서는 데이터 작성 및 EUII 통합 되어 네트워크 위치, 회의 세부 정보, 장치 또는 펌웨어에 따라 시스템 문제를 식별 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-312">Incorporating building and EUII data, these reports help identify possible system issues based on network location, conference details, devices, or firmware.</span></span>         |
|<span data-ttu-id="9c1d8-313">클라이언트 버전 보고서</span><span class="sxs-lookup"><span data-stu-id="9c1d8-313">Client Version Reports</span></span>     |<span data-ttu-id="9c1d8-314">클라이언트 버전 요약: 각 클라이언트 앱 버전의 세션 및 사용자 수를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-314">Client Version Summary: View the Sessions and Users counts for each client app version</span></span><br><br><span data-ttu-id="9c1d8-315">사용자별 클라이언트 버전: 각 클라이언트 앱 버전에 대 한 사용자 이름 보기</span><span class="sxs-lookup"><span data-stu-id="9c1d8-315">Client Version by User: View user names for each client app version</span></span> <br><br><span data-ttu-id="9c1d8-316">제품 및 클라이언트 종류에 대 한 미리 작성 된 필터는 특정 클라이언트에 버전을 집중 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-316">Pre-built filters for Product and Client Type help focus the versions to specific clients.</span></span>         |
|<span data-ttu-id="9c1d8-317">끝점 보고서</span><span class="sxs-lookup"><span data-stu-id="9c1d8-317">Endpoint Reports</span></span>     |<span data-ttu-id="9c1d8-318">컴퓨터 끝점을 기준으로 통화 음질을 표시 합니다 (컴퓨터 제조업체 및 모델).</span><span class="sxs-lookup"><span data-stu-id="9c1d8-318">Shows call quality by machine endpoints (computer make and model).</span></span> <span data-ttu-id="9c1d8-319">이러한 보고서에는 데이터를 업로드 한 경우이에 대 한 빌드가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-319">These reports include building data, if you've uploaded it.</span></span>         |


## <a name="create-custom-detailed-reports"></a><span data-ttu-id="9c1d8-320">사용자 지정 상세 보고서 만들기</span><span class="sxs-lookup"><span data-stu-id="9c1d8-320">Create custom detailed reports</span></span>

<span data-ttu-id="9c1d8-321">기본 CQD 보고서가 요구 사항에 맞지 않는 경우 다음 지침을 사용 하 여 사용자 지정 보고서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-321">If the default CQD reports don't meet your needs, use these instructions to create a custom report.</span></span> <span data-ttu-id="9c1d8-322">또는 (2020 년 1 월), 대신 [CQD 보고서 용 POWER BI를 사용 ](cqd-power-bi-query-templates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-322">Or (as of January 2020) [Use Power BI for CQD reports ](cqd-power-bi-query-templates.md)instead.</span></span>

<span data-ttu-id="9c1d8-323">요약 보고서 화면에서 로그인 할 때 표시 되는 화면 위쪽에 있는 보고서의 풀 다운 목록에서 \( **Summary Reports** \) **자세한 보고서** 와 **새로 만들기**를 차례로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-323">From the pull-down list of reports at the top of the screen displayed at login \(the **Summary Reports** screen\) Select **Detailed Reports**  and then **New**.</span></span> <span data-ttu-id="9c1d8-324">보고서에서 **편집** 을 클릭 하 여 쿼리 편집기를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-324">Click **Edit** in a report to see the Query Editor.</span></span> <span data-ttu-id="9c1d8-325">각 보고서는 큐브로 쿼리를 통해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-325">Each report is backed by a query into the cube.</span></span> <span data-ttu-id="9c1d8-326">보고서는 해당 쿼리에서 반환 된 데이터를 시각화 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-326">A report is a visualization of the data returned by its query.</span></span> <span data-ttu-id="9c1d8-327">쿼리 편집기를 사용 하 여 이러한 쿼리 및 보고서의 표시 옵션을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-327">The Query Editor helps you edit these queries and the display options of the report.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="9c1d8-328">네트워크 범위를 사용 하 여 수퍼 네트 (단일 라우팅 접두사가 있는 여러 서브넷의 조합)를 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-328">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix).</span></span> <span data-ttu-id="9c1d8-329">모든 새 건물 업로드가 겹치는 범위에 대해 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-329">All new building uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="9c1d8-330">문서 파일을 이전에 업로드 한 경우에는 현재 파일을 다운로드 한 후 다시 업로드 하 여 겹치는 내용을 식별 하 고 문제를 해결 한 후 다시 업로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-330">If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again.</span></span> <span data-ttu-id="9c1d8-331">이전에 업로드 한 파일의 겹치기로 인해 보고서의 건물에 대해 잘못 된 서브넷 매핑이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-331">Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports.</span></span> <span data-ttu-id="9c1d8-332">특정 VPN 구현에서는 서브넷 정보가 정확 하 게 보고 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-332">Certain VPN implementations do not accurately report the subnet information.</span></span> <span data-ttu-id="9c1d8-333">VPN 서브넷을 건물 파일에 추가할 때 서브넷에 대 한 하나의 항목이 아닌 별도의 32 비트 네트워크로 VPN 서브넷의 각 주소에 대해 개별 항목이 추가 되는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-333">It is recommended that when adding a VPN subnet to the building file, instead of one entry for the subnet, separate entries are added for each address in the VPN subnet as a separate 32-bit network.</span></span> <span data-ttu-id="9c1d8-334">각 행은 동일한 빌드 메타 데이터를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-334">Each row can have the same building metadata.</span></span> <span data-ttu-id="9c1d8-335">예를 들어 172.16.18.0/24에 대 한 한 행이 아닌 256 행이 172.16.18.0/32 및 172.16.18.255/32 (포함) 사이에 있는 각 주소에 대해 한 행이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-335">For example, instead of one row for 172.16.18.0/24, you should have 256 rows, with one row for each address between 172.16.18.0/32 and 172.16.18.255/32, inclusive.</span></span>
>
> <span data-ttu-id="9c1d8-336">VPN 열은 선택 사항이 며 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-336">The VPN column is optional and will default to 0.</span></span>  <span data-ttu-id="9c1d8-337">VPN 열의 값이 1로 설정 되 면 해당 행이 표시 하는 서브넷이 서브넷 내의 모든 IP 주소와 일치 하도록 완전히 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-337">If the VPN column's value is set to 1, the subnet represented by that row will be fully expanded to match all IP addresses within the subnet.</span></span>  <span data-ttu-id="9c1d8-338">이러한 서브넷을 완전히 확장 하면 데이터 작성이 포함 된 쿼리에 대 한 쿼리 시간에 부정적인 영향을 주므로이를 사용 하 여 VPN 서브넷에 대해서만이 방법을 사용해 주십시오.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-338">Please use this sparingly and only for VPN subnets since fully expanding these subnets will have a negative impact on query times for queries involving building data.</span></span>

<span data-ttu-id="9c1d8-339">보고서의 막대형 차트 및 추세 선을 가리키면 세부 값이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-339">Point to bar charts and trend lines in the report to display detailed values.</span></span> <span data-ttu-id="9c1d8-340">포커스가 있는 보고서에는 **보고서 트리** **편집**, **복제**, **삭제**, **다운로드**, 내보내기 등의 작업 메뉴가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-340">The report that has focus will show the action menu: **Edit**, **Clone**, **Delete**, **Download**, and **Export Report Tree**.</span></span>



## <a name="query-filters"></a><span data-ttu-id="9c1d8-341">쿼리 필터</span><span class="sxs-lookup"><span data-stu-id="9c1d8-341">Query filters</span></span>

<span data-ttu-id="9c1d8-342">쿼리 필터는 CQD의 쿼리 편집기를 사용 하 여 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-342">Query filters are implemented by using the Query Editor in CQD.</span></span> <span data-ttu-id="9c1d8-343">이러한 필터는 CQD에서 반환 되는 레코드 수를 줄여 보고서의 전체 크기와 쿼리 시간을 최소화 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-343">These filters are used to reduce the number of records returned by CQD, thus minimizing the report’s overall size and query times.</span></span> <span data-ttu-id="9c1d8-344">이는 관리 되지 않는 네트워크를 필터링 하는 데 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-344">This is especially useful for filtering out unmanaged networks.</span></span> <span data-ttu-id="9c1d8-345">다음 표에 나열 된 필터는 정규식 (RegEx)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-345">The filters listed in the following table use regular expressions (RegEx).</span></span>


| <span data-ttu-id="9c1d8-346">Filter</span><span class="sxs-lookup"><span data-stu-id="9c1d8-346">Filter</span></span>         | <span data-ttu-id="9c1d8-347">설명</span><span class="sxs-lookup"><span data-stu-id="9c1d8-347">Description</span></span>          | <span data-ttu-id="9c1d8-348">CQD 쿼리 필터 예제</span><span class="sxs-lookup"><span data-stu-id="9c1d8-348">CQD query filter example</span></span>      |
|----------------|----------------------|-------------------------------|
| <span data-ttu-id="9c1d8-349">빈 값 없음</span><span class="sxs-lookup"><span data-stu-id="9c1d8-349">No blank values</span></span>   | <span data-ttu-id="9c1d8-350">일부 필터에는 빈 값을 필터링 하는 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-350">Some filters don’t have the option to filter for blank values.</span></span> <span data-ttu-id="9c1d8-351">빈 값을 수동으로 필터링 하려면 필요에 따라 빈 식을 사용 하 고 필터를 같음 또는 같지 않음으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-351">To filter blank values manually, use the blank expression and set the filter to Equals or Not Equals, depending on your needs.</span></span>      | <span data-ttu-id="9c1d8-352">두 번째 건물 이름 \<\> \^ \\ s\*\$</span><span class="sxs-lookup"><span data-stu-id="9c1d8-352">Second Building Name \<\> \^\\s\*\$</span></span>                       |
| <span data-ttu-id="9c1d8-353">공용 서브넷 제외</span><span class="sxs-lookup"><span data-stu-id="9c1d8-353">Exclude common subnets</span></span> | <span data-ttu-id="9c1d8-354">관리 되지 않는 네트워크를 구분 하기 위해 올바른 빌드 파일이 없는 경우 홈 네트워크는 보고서에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-354">Without a valid building file to separate managed from unmanaged networks, home networks will be included in the reports.</span></span> <span data-ttu-id="9c1d8-355">이러한 홈 서브넷은 해당 컨트롤의 범위를 벗어나므로 보고서에서 빠르게 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-355">These home subnets are outside the scope of IT’s control and can be quickly excluded from a report.</span></span> <span data-ttu-id="9c1d8-356">이 가이드에 정의 된 대로 일반적인 서브넷은 10.0.0.0, 192.168.1.0, 192.168.0.0입니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-356">Common subnets, as defined in this guide, are 10.0.0.0, 192.168.1.0 and 192.168.0.0.</span></span> | <span data-ttu-id="9c1d8-357">두 번째 서브넷 \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="9c1d8-357">Second Subnet \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0</span></span> |
| <span data-ttu-id="9c1d8-358">안쪽만 보기</span><span class="sxs-lookup"><span data-stu-id="9c1d8-358">View inside only</span></span>  | <span data-ttu-id="9c1d8-359">관리 (내부) 또는 비관리형 (외부)에 대 한 보고서를 필터링 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-359">Used to filter a report for managed (inside) or unmanaged (outside).</span></span> <span data-ttu-id="9c1d8-360">관리 되는 CQD 템플릿은이 필터를 사용 하 여 이미 미리 구성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-360">The managed CQD template is already preconfigured with these filters.</span></span>       | <span data-ttu-id="9c1d8-361">두 번째 내부의 Corp = 인사이드</span><span class="sxs-lookup"><span data-stu-id="9c1d8-361">Second Inside Corp = Inside</span></span>        |

## <a name="report-filters"></a><span data-ttu-id="9c1d8-362">보고서 필터</span><span class="sxs-lookup"><span data-stu-id="9c1d8-362">Report filters</span></span>

<span data-ttu-id="9c1d8-363">CQD 보고서 필터를 사용 하 여 조사의 초점을 좁힐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-363">Use CQD report filters to narrow the focus of your investigations.</span></span> <span data-ttu-id="9c1d8-364">보고서 필터는 쿼리 편집기에서 렌더링 된 보고서에 필터를 추가 하거나 보고서에서 바로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-364">Use report filters by adding a filter to the rendered report either in the Query Editor or directly in the report.</span></span> <span data-ttu-id="9c1d8-365">다음 보고서 필터는 [Cqd 서식 파일](https://aka.ms/QERtemplates)에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-365">The following report filters are used throughout the [CQD templates](https://aka.ms/QERtemplates).</span></span>


| <span data-ttu-id="9c1d8-366">Filter</span><span class="sxs-lookup"><span data-stu-id="9c1d8-366">Filter</span></span>     | <span data-ttu-id="9c1d8-367">설명</span><span class="sxs-lookup"><span data-stu-id="9c1d8-367">Description</span></span>                            | <span data-ttu-id="9c1d8-368">CQD 보고서 필터 예제</span><span class="sxs-lookup"><span data-stu-id="9c1d8-368">CQD report filter example</span></span>         |
|------------|----------------------------------------|-----------------------------------|
| <span data-ttu-id="9c1d8-369">달은</span><span class="sxs-lookup"><span data-stu-id="9c1d8-369">Month</span></span>      | <span data-ttu-id="9c1d8-370">먼저 1 년부터 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-370">Start with the year first, then month.</span></span> | <span data-ttu-id="9c1d8-371">2017-10</span><span class="sxs-lookup"><span data-stu-id="9c1d8-371">2017-10</span></span>                           |
| <span data-ttu-id="9c1d8-372">가</span><span class="sxs-lookup"><span data-stu-id="9c1d8-372">Alphabetic</span></span> | <span data-ttu-id="9c1d8-373">모든 알파벳 문자에 대 한 필터입니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-373">Filters for any alphabetic characters.</span></span> | <span data-ttu-id="9c1d8-374">[a-z]</span><span class="sxs-lookup"><span data-stu-id="9c1d8-374">[a-z]</span></span>                             |
| <span data-ttu-id="9c1d8-375">번호</span><span class="sxs-lookup"><span data-stu-id="9c1d8-375">Numeric</span></span>    | <span data-ttu-id="9c1d8-376">임의의 숫자 문자에 대 한 필터입니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-376">Filters for any numeric characters.</span></span>    | <span data-ttu-id="9c1d8-377">[0-9]</span><span class="sxs-lookup"><span data-stu-id="9c1d8-377">[0-9]</span></span>                             |
| <span data-ttu-id="9c1d8-378">많은</span><span class="sxs-lookup"><span data-stu-id="9c1d8-378">Percentage</span></span> | <span data-ttu-id="9c1d8-379">백분율에 대 한 필터입니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-379">Filters for a percentage.</span></span>              | <span data-ttu-id="9c1d8-380">([3-9] \\ ) \| . ([3-9]) \| ([1-9] [0-9])</span><span class="sxs-lookup"><span data-stu-id="9c1d8-380">([3-9]\\.)\|([3-9])\|([1-9][0-9])</span></span> |


### <a name="drill-down-filters"></a><span data-ttu-id="9c1d8-381">드릴 다운 필터</span><span class="sxs-lookup"><span data-stu-id="9c1d8-381">Drill-down filters</span></span>

<span data-ttu-id="9c1d8-382">CQD 보고서는 여러 드릴 다운 필터 기능을가지고 있으며,이는 통화 품질 조사에 초점을 좁히는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-382">CQD reports feature several drill-down filters, which are powerful tools for narrowing the focus of your call-quality investigations.</span></span> <span data-ttu-id="9c1d8-383">드릴 다운 필드를 선택 하면 보고서가 자동으로 해당 탭과 선택한 값에 대 한 필터를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-383">If you select a drill-down field, the report automatically opens the appropriate tab and filters on the selected value.</span></span> <span data-ttu-id="9c1d8-384">해당 탭에 고유한 드릴 다운 필드가 있고 하나를 선택 하면 두 필터 집합을 적용 하 여 결과 데이터 집합을 점차적으로 축소 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-384">If that tab has its own drill-down fields and one is selected, both sets of filters are applied, progressively narrowing the resulting data set.</span></span>

![드릴 다운 보고서 흐름을 보여 주는 다이어그램](media/qerguide-image-drillthrureportflow.png)


#### <a name="adding-and-editing-drill-down-fields"></a><span data-ttu-id="9c1d8-386">드릴 다운 필드 추가 및 편집</span><span class="sxs-lookup"><span data-stu-id="9c1d8-386">Adding and editing drill-down fields</span></span>

<span data-ttu-id="9c1d8-387">보고서를 편집할 때 쿼리 편집기를 사용 하 여 고유한 드릴 다운 필드를 지정 하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-387">When editing a report, you have the option to specify drill-down fields of your own using the Query Editor.</span></span>

<span data-ttu-id="9c1d8-388">먼저 **을 클릭 하** 여 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-388">Start by clicking **…**</span></span> <span data-ttu-id="9c1d8-389">편집 하려는 보고서의 경우 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-389">for the report you want to edit, then select **Edit**.</span></span>

![드릴 다운 필드 편집 스크린샷](media/qerguide-image-addeditdrilldownfields.png)

<span data-ttu-id="9c1d8-391">쿼리 편집기의 왼쪽에 있는 목록에서 차원을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-391">Select a Dimension from the list on the left side of the Query Editor.</span></span> <span data-ttu-id="9c1d8-392">그런 다음 **이동** 레이블 아래의 드롭다운을 클릭 하 고 해당 차원을 드릴스루할 탭 및 확장 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-392">Then click on the dropdown below the **Navigate To** label and select the tab and expander group that you want that Dimension to drill through to.</span></span> <span data-ttu-id="9c1d8-393">참고: 현재 드릴 다운 기능은 다른 탭으로 이동할 때만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-393">Note: Presently, drill-down functionality only works by navigating to different tabs.</span></span> <span data-ttu-id="9c1d8-394">특정 확장기로 드릴 다운에 대 한 지원은 나중에 추가 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-394">Support for drilling through to a specific expander will be added later.</span></span> <span data-ttu-id="9c1d8-395">마지막으로, **닫기를** 클릭 하 여 차원에 대 한 변경 내용을 저장 한 다음 **저장** 을 클릭 하 여 쿼리 편집기를 저장 하 고 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-395">Finally, click **Close** to save your changes to the Dimension, then click **Save** to save and close the Query Editor.</span></span>

![쿼리 편집기에서 차원을 선택 하는 스크린샷](media/qerguide-image-selectquerydimension.png)

### <a name="multi-select-filters"></a><span data-ttu-id="9c1d8-397">다중 선택 필터</span><span class="sxs-lookup"><span data-stu-id="9c1d8-397">Multi-select filters</span></span>

<span data-ttu-id="9c1d8-398">' 드릴 다운 ' 기능 외에도 CQD는 여러 값 또는 필터를 갖는 필터 지정을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-398">In addition to drill-down functionality, CQD also supports specifying Filters with multiple values (OR filters).</span></span>

<span data-ttu-id="9c1d8-399">여러 필터 값을 선택 하려면 먼저 보고서에 새 필터를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-399">In order to select multiple filter values, begin by adding a new filter to the report.</span></span> <span data-ttu-id="9c1d8-400">**+** **필터** 레이블 옆을 클릭 하 고 사용 하려는 차원의 이름을 입력 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-400">Click **+** beside the **Filters** label, enter the name of the Dimension you want to use, and click **Add**.</span></span>

![다중 선택 필터 추가 스크린샷](media/qerguide-image-addmultiselectfilter.png)

<span data-ttu-id="9c1d8-402">그런 다음 **검색** (새 필터 옆에 있는 돋보기 아이콘)을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-402">Then, click **Search** (a magnifying glass icon next to the new filter).</span></span> <span data-ttu-id="9c1d8-403">텍스트 필드와 **모두 선택** 및 **반전**을 비롯 한 여러 옵션이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-403">You'll see a text field, and a number of options, including **Select All** and **Invert**.</span></span> <span data-ttu-id="9c1d8-404">값을 입력 하 고 해당 필드 옆에 있는 **검색** 을 클릭 하 여 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-404">Enter a value,  and click **Search** next to that field to search.</span></span> <span data-ttu-id="9c1d8-405">또는 텍스트 필드를 비워 두고 **검색** 을 클릭 하 여 첫 번째 100 옵션을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-405">Alternatively, leave the text field empty and click **Search** to view up to the first 100 options.</span></span>

```PowerShell
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

<span data-ttu-id="9c1d8-406">예</span><span class="sxs-lookup"><span data-stu-id="9c1d8-406">Example:</span></span>  

![쿼리 필터 추가 스크린샷](media/qerguide-image-addfilter.png)

### <a name="dashboard-level-filters"></a><span data-ttu-id="9c1d8-408">대시보드 수준 필터</span><span class="sxs-lookup"><span data-stu-id="9c1d8-408">Dashboard level filters</span></span>
<span data-ttu-id="9c1d8-409">특정 CQD 보고서에는 대시보드 수준의 필터가 추가 되어 공통 매개 변수에 따라 쉽게 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-409">Certain CQD reports have dashboard-level filters added to them, making it easy to filter by common parameters.</span></span> <span data-ttu-id="9c1d8-410">이러한 필터는 일반 보고서 탭 외부와 제품 필터 바로 아래에 표시 되며 대시보드의 모든 필터에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-410">These filters appear outside the regular report tabs and directly beneath the Product filter, and they apply to all filters in the Dashboard.</span></span>

![대시보드 필터 스크린샷](media/qerguide-image-dashboardfilters.png)
```PowerShell
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

### <a name="url-filters"></a><span data-ttu-id="9c1d8-412">URL 필터</span><span class="sxs-lookup"><span data-stu-id="9c1d8-412">URL filters</span></span>

<span data-ttu-id="9c1d8-413">CQD는 URL에 필터를 추가 하는 것을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-413">CQD supports adding filters to the URL.</span></span> <span data-ttu-id="9c1d8-414">이렇게 하면 CQD 쿼리를 쉽게 공유 하거나 책갈피로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-414">This makes it easy to share or bookmark a CQD query.</span></span> <span data-ttu-id="9c1d8-415">URL에서 추세 월, 테 넌 트 ID 또는 언어와 같은 매개 변수를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-415">You can define parameters in the URL, such as Trending Month, tenant ID, or language.</span></span> <span data-ttu-id="9c1d8-416">URL에 제품 또는 대시보드 수준 필터를 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-416">You can also add Product or Dashboard level filters to the URL.</span></span>
<span data-ttu-id="9c1d8-417">페더레이션된 끝점이 보고서에 영향을 줄 수 있는 관리 되는 건물이 나 네트워크를 수정 하는 경우 CQD 보고서의 페더레이션된 데이터를 제외 하는 것이 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-417">Excluding federated data from CQD reports is useful when you're remediating managed buildings or networks where federated endpoints might influence your reports.</span></span>

<span data-ttu-id="9c1d8-418">필터를 추가 하려면 URL의 끝에 다음을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-418">To add a filter, append the following to the end of the URL:</span></span>

```
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

<span data-ttu-id="9c1d8-419">예</span><span class="sxs-lookup"><span data-stu-id="9c1d8-419">Example:</span></span>  

```https://cqd.teams.microsoft.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]```

<span data-ttu-id="9c1d8-420">URL에 대시보드 수준 필터를 추가 하려면 해당 필터가 CQD에 제품 또는 대시보드 수준 필터로 존재 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-420">To add a Dashboard-level filter to a URL, that filter must exist in CQD as either a Product or Dashboard level filter.</span></span> <span data-ttu-id="9c1d8-421">다음 필터를 추세 월 및 URL 매개 변수 앞의 URL에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-421">Add these filters to the URL after the Trending Month and before the URL parameters:</span></span>

```filter/DATA_MODEL_NAME|VALUE```

<span data-ttu-id="9c1d8-422">예를 들어 Microsoft 팀의 제품 필터 값을 적용 하려면 다음을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-422">For example, to apply a Product filter value of Microsoft Teams, you'd add the following:</span></span>

```filter/[AllStreams].[Is%20Teams]|[True]```

<span data-ttu-id="9c1d8-423">전체 URL이 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-423">Your entire URL would look something like this:</span></span>

```https://cqd.teams.microsoft.com/spd/#/Dashboard/2624085/2018-9/filter/[AllStreams].[Is%20Teams]|[True]```

<span data-ttu-id="9c1d8-424">다중 선택 값을 사용 하 여 URL 필터를 적용 하려면 각 값을 파이프 (|) 문자로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-424">To apply URL filters with multi-select values, separate each value with a pipe ( | ) character.</span></span> <span data-ttu-id="9c1d8-425">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-425">For example:</span></span>

```filter/[AllStreams].[Media%20Type]|[Video]|[Audio]|[VBSS]```

<span data-ttu-id="9c1d8-426">잘못 된 이름 또는 값을 지정 하면 URL 필터가 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-426">If you specify an invalid name or value, the URL filter won't be applied.</span></span>


<span data-ttu-id="9c1d8-427">URL 필터를 사용 하 여 특정 차원에 대 한 모든 보고서를 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-427">You can use a URL filter to filter every report for a specific dimension.</span></span> <span data-ttu-id="9c1d8-428">가장 일반적인 URL 필터는 페더레이션 참가자 원격 분석을 제외 하도록 보고서를 필터링 하거나, 팀 또는 비즈니스용 Skype Online 에서만 포커스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-428">The most common URL filters are used to filter reports to exclude federated participant telemetry, or focus on only Teams or Skype for Business Online.</span></span> <span data-ttu-id="9c1d8-429">페더레이션된 끝점이 보고서에 영향을 줄 수 있는 관리 되는 건물이 나 네트워크를 수정 하는 경우 CQD 보고서의 페더레이션된 데이터를 제외 하는 것이 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-429">Excluding federated data from CQD reports is useful when you're remediating managed buildings or networks where federated endpoints might influence your reports.</span></span>

| <span data-ttu-id="9c1d8-430">Filter</span><span class="sxs-lookup"><span data-stu-id="9c1d8-430">Filter</span></span>         | <span data-ttu-id="9c1d8-431">설명</span><span class="sxs-lookup"><span data-stu-id="9c1d8-431">Description</span></span>          | <span data-ttu-id="9c1d8-432">CQD 쿼리 필터 예제</span><span class="sxs-lookup"><span data-stu-id="9c1d8-432">CQD query filter example</span></span>      |
|----------------|----------------------|-------------------------------|
| <span data-ttu-id="9c1d8-433">빈 값 없음</span><span class="sxs-lookup"><span data-stu-id="9c1d8-433">No blank values</span></span>   | <span data-ttu-id="9c1d8-434">일부 필터에는 빈 값을 필터링 하는 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-434">Some filters don't have the option to filter for blank values.</span></span> <span data-ttu-id="9c1d8-435">빈 값을 수동으로 필터링 하려면 필요에 따라 빈 식을 사용 하 고 필터를 같음 또는 같지 않음으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-435">To filter blank values manually, use the blank expression and set the filter to Equals or Not Equals, depending on your needs.</span></span>      | <span data-ttu-id="9c1d8-436">두 번째 건물 이름 \<\> \^ \\ s\*\$</span><span class="sxs-lookup"><span data-stu-id="9c1d8-436">Second Building Name \<\> \^\\s\*\$</span></span>                       |
| <span data-ttu-id="9c1d8-437">공용 서브넷 제외</span><span class="sxs-lookup"><span data-stu-id="9c1d8-437">Exclude common subnets</span></span> | <span data-ttu-id="9c1d8-438">관리 되지 않는 네트워크를 구분 하기 위해 올바른 빌드 파일이 없는 경우 홈 네트워크는 보고서에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-438">Without a valid building file to separate managed from unmanaged networks, home networks will be included in the reports.</span></span> <span data-ttu-id="9c1d8-439">이러한 홈 서브넷은 해당 컨트롤의 범위를 벗어나므로 보고서에서 빠르게 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-439">These home subnets are outside the scope of IT's control and can be quickly excluded from a report.</span></span> <span data-ttu-id="9c1d8-440">이 문서에 정의 된 대로 공용 서브넷은 10.0.0.0, 192.168.1.0, 192.168.0.0입니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-440">Common subnets, as defined in this article, are 10.0.0.0, 192.168.1.0 and 192.168.0.0.</span></span> | <span data-ttu-id="9c1d8-441">두 번째 서브넷 \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="9c1d8-441">Second Subnet \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0</span></span> |
| <span data-ttu-id="9c1d8-442">안쪽만 보기</span><span class="sxs-lookup"><span data-stu-id="9c1d8-442">View inside only</span></span>  | <span data-ttu-id="9c1d8-443">관리 (내부) 또는 비관리형 (외부)에 대 한 보고서를 필터링 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-443">Used to filter a report for managed (inside) or unmanaged (outside).</span></span> <span data-ttu-id="9c1d8-444">관리 되는 CQD 템플릿은이 필터를 사용 하 여 이미 미리 구성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-444">The managed CQD template is already preconfigured with these filters.</span></span>       | <span data-ttu-id="9c1d8-445">두 번째 내부의 Corp = 인사이드</span><span class="sxs-lookup"><span data-stu-id="9c1d8-445">Second Inside Corp = Inside</span></span>        |


#### <a name="how-to-find-your-tenant-id"></a><span data-ttu-id="9c1d8-446">테 넌 트 ID를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="9c1d8-446">How to find your tenant ID</span></span>

<span data-ttu-id="9c1d8-447">CQD의 테 넌 트 ID는 Azure의 디렉터리 ID에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-447">The tenant ID in CQD corresponds to the Directory ID in Azure.</span></span> <span data-ttu-id="9c1d8-448">디렉터리 ID를 모르는 경우 Azure 포털에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-448">If you don't know your Directory ID, you can find it in the Azure portal:</span></span>

1.  <span data-ttu-id="9c1d8-449">Microsoft Azure 포털에 로그인 합니다.<https://portal.azure.com></span><span class="sxs-lookup"><span data-stu-id="9c1d8-449">Sign in to the Microsoft Azure portal: <https://portal.azure.com></span></span>

2.  <span data-ttu-id="9c1d8-450">**Azure Active Directory**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-450">Select **Azure Active Directory**.</span></span>

3.  <span data-ttu-id="9c1d8-451">**관리**에서 **속성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-451">Under **Manage**, select **Properties**.</span></span> <span data-ttu-id="9c1d8-452">테 넌 트 ID는 **디렉터리 ID** 상자에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-452">Your tenant ID is in the **Directory ID** box.</span></span>

<span data-ttu-id="9c1d8-453">PowerShell을 사용 하 여 테 넌 트 ID를 찾을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-453">You can also find your tenant ID by using PowerShell:</span></span> 
  ```
  Login-AzureRmAccount
  ```



## <a name="comparing-teams-and-skype-for-business-cqd-data"></a><span data-ttu-id="9c1d8-454">팀과 비즈니스용 Skype CQD 데이터 비교</span><span class="sxs-lookup"><span data-stu-id="9c1d8-454">Comparing Teams and Skype for Business CQD data</span></span>

<span data-ttu-id="9c1d8-455">최신 CQD (cqd.teams.microsoft.com) 내에도 팀과 비즈니스용 Skype 간의 데이터 차이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-455">Even within the latest CQD (cqd.teams.microsoft.com), you'll see differences in data between Teams and Skype for Business.</span></span> <span data-ttu-id="9c1d8-456">몇 가지 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-456">Some reasons:</span></span>
- <span data-ttu-id="9c1d8-457">성능 및 안정성을 보장 하는 메커니즘의 차이점</span><span class="sxs-lookup"><span data-stu-id="9c1d8-457">Differences in the mechanisms for ensuring performance and reliability</span></span>
  - <span data-ttu-id="9c1d8-458">팀에 자동 다시 연결 및 빠른 로밍이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-458">Teams has auto-reconnect and fast roaming.</span></span> <span data-ttu-id="9c1d8-459">비즈니스용 Skype는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-459">Skype for Business doesn't.</span></span>
  - <span data-ttu-id="9c1d8-460">팀은 동적 대역폭 관리를가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-460">Teams has dynamic bandwidth management.</span></span> <span data-ttu-id="9c1d8-461">비즈니스용 Skype는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-461">Skype for Business doesn't.</span></span>
- <span data-ttu-id="9c1d8-462">팀과 비즈니스용 Skype 간의 [IP 주소 범위](Office-365-URLs-IP-address-ranges.md) 차이</span><span class="sxs-lookup"><span data-stu-id="9c1d8-462">Differences in [IP address ranges](Office-365-URLs-IP-address-ranges.md) between Teams and Skype for Business.</span></span> <span data-ttu-id="9c1d8-463">팀 IP 범위는 더 최신 버전 이므로 방화벽에서 연결 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-463">The Teams IP ranges are newer, which could cause connectivity problems at the firewall.</span></span>

## <a name="open-cqd-from-the-skype-for-business-legacy-portal"></a><span data-ttu-id="9c1d8-464">비즈니스용 Skype 레거시 포털에서 CQD 열기</span><span class="sxs-lookup"><span data-stu-id="9c1d8-464">Open CQD from the Skype for Business legacy portal</span></span>

<span data-ttu-id="9c1d8-465">![비즈니스용 skype ](media/sfb-logo-30x30.png) **레거시 포털을 사용 하** 는 비즈니스용 skype 로고 아이콘</span><span class="sxs-lookup"><span data-stu-id="9c1d8-465">![An icon of the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business legacy portal**</span></span>

1. <span data-ttu-id="9c1d8-466">관리자 계정을 사용 하 여 Office 365 조직에 로그인 한 다음 관리 타일을 선택 **하 여 관리** 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-466">Sign in to your Office 365 organization using an admin account, and then select the **Admin** tile to open the Admin center.</span></span>
2. <span data-ttu-id="9c1d8-467">왼쪽 창의 **관리 센터**에서 **Microsoft 팀** 을 선택 하 여 팀 관리 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-467">In the left pane, under **Admin centers**, select **Microsoft Teams** to open the Teams admin center.</span></span>
3. <span data-ttu-id="9c1d8-468">팀 관리 센터의 왼쪽 창에서 **레거시 포털** 을 선택 하 고 **도구**를 선택한 다음 비즈니스용 **Skype Online 통화 품질 대시보드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-468">In the Teams admin center, select **Legacy Portal** in the left pane, select **Tools**, and then select **Skype for Business Online Call Quality Dashboard**.</span></span>

     ![스크린샷: 통화 품질 대시보드를 선택 합니다.](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)

4. <span data-ttu-id="9c1d8-470">열리는 페이지에서 전역 관리자 계정으로 로그인 한 다음 메시지가 표시 되 면 계정에 대 한 자격 증명을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-470">On the page that opens, sign in with your Global Administrator account, and then provide the credentials for the account when prompted.</span></span>

<span data-ttu-id="9c1d8-471">처음 로그인 하면 CQD가 데이터 수집과 처리를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-471">After the first time you sign in, CQD will begin collecting and processing data.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="9c1d8-472">2019 년 12 월 이전에는 레거시 포털에서 최신 CQD (cqd.teams.microsoft.com)에 대 한 링크를 제공 하지만이 경우에도 cqd.lync.com (c)의 오래 된 버전에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-472">As of December 2019, you can still access the older version of CQD (cqd.lync.com), although the legacy portal gives you a link to the latest CQD (cqd.teams.microsoft.com).</span></span> <span data-ttu-id="9c1d8-473">결과적으로 CQD의 이전 버전이 서비스 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-473">Eventually, the older version of CQD will be decommissioned.</span></span> <span data-ttu-id="9c1d8-474">7 월 1 2020 일 (으)로 이전 버전의 CQD는 새 CQD의 데이터에 액세스 https://CQD.teams.microsoft.com) 하며, 더 이상 빌드 및 보고서 데이터를 내보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-474">As of July 1, 2020, the older version of CQD accesses data from the new CQD (https://CQD.teams.microsoft.com), and you can no longer export building and report data.</span></span> <span data-ttu-id="9c1d8-475">2020 후반에는 이전 CQD를 해제 하 고 더 이상 액세스할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c1d8-475">Sometime in late 2020, we'll turn off the old CQD and you'll no longer be able to access it.</span></span>


## <a name="related-topics"></a><span data-ttu-id="9c1d8-476">관련 항목</span><span class="sxs-lookup"><span data-stu-id="9c1d8-476">Related topics</span></span>

[<span data-ttu-id="9c1d8-477">팀의 통화 품질 개선 및 모니터링</span><span class="sxs-lookup"><span data-stu-id="9c1d8-477">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="9c1d8-478">CQD 란 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="9c1d8-478">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="9c1d8-479">CQD (통화 품질 대시보드) 설정</span><span class="sxs-lookup"><span data-stu-id="9c1d8-479">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="9c1d8-480">테 넌 트 업로드 및 데이터 빌드</span><span class="sxs-lookup"><span data-stu-id="9c1d8-480">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="9c1d8-481">CQD를 사용 하 여 통화 및 모임 품질 관리</span><span class="sxs-lookup"><span data-stu-id="9c1d8-481">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="9c1d8-482">CQD에서 사용할 수 있는 차원과 측정값</span><span class="sxs-lookup"><span data-stu-id="9c1d8-482">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="9c1d8-483">CQD의 스트림 분류</span><span class="sxs-lookup"><span data-stu-id="9c1d8-483">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="9c1d8-484">Power BI를 사용 하 여 CQD 데이터 분석</span><span class="sxs-lookup"><span data-stu-id="9c1d8-484">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)
