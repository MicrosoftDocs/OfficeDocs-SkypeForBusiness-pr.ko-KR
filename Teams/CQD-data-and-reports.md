---
title: CQD (통화 품질 대시보드의 데이터 및 보고서)
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
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Microsoft 통화 품질 대시보드 (CQD)에서 사용할 수 있는 데이터 및 보고서에 대해 알아봅니다.
ms.openlocfilehash: ec9714e0eae187bc82edf01809b50d8512d04e01
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583095"
---
# <a name="data-and-reports-in-call-quality-dashboard-cqd"></a><span data-ttu-id="96761-103">CQD (통화 품질 대시보드의 데이터 및 보고서)</span><span class="sxs-lookup"><span data-stu-id="96761-103">Data and reports in Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="96761-104">CQD (Microsoft 통화 품질 대시보드)는 NRT (근거리 실시간) 데이터 피드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-104">Microsoft Call Quality Dashboard (CQD) uses a near-real-time (NRT) data feed.</span></span> <span data-ttu-id="96761-105">통화 기록은 통화 종료 시간 30 분 이내에 CQD에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-105">Call records are available in CQD within 30 minutes of the end of a call.</span></span> <span data-ttu-id="96761-106">NRT 파이프라인의 통화 레코드는 일부 달에만 사용할 수 있으며 데이터 집합에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-106">Call records from the NRT pipeline are only available for a few months before they are removed from the data set.</span></span> 


## <a name="many-ways-to-access-cqd-data"></a><span data-ttu-id="96761-107">CQD 데이터에 액세스 하는 다양 한 방법</span><span class="sxs-lookup"><span data-stu-id="96761-107">Many ways to access CQD data</span></span>

<span data-ttu-id="96761-108">여러 다른 수단으로 CQD 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-108">You can access CQD data by several different avenues.</span></span> <span data-ttu-id="96761-109">요구 사항에 가장 적합 한 항목을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-109">Pick the one that best meets your needs:</span></span>

|  |  |
|---------|---------|
|<span data-ttu-id="96761-110">팀 관리 센터 [( https://admin.teams.microsoft.com) ](https://admin.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="96761-110">Teams admin center [(https://admin.teams.microsoft.com)](https://admin.teams.microsoft.com)</span></span>    | <span data-ttu-id="96761-111">CQD 데이터는 팀 관리 센터의 **사용자** 페이지에 포함 되어 있으며, 읽기 쉬운 형식으로 필요한 가장 일반적인 데이터를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-111">CQD data is included on the **Users** page in the Teams admin center, showing the most common data you need in an easy-to-read format.</span></span> <span data-ttu-id="96761-112">**사용자가**찾은 CQD 데이터는 사용자 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-112">You can't customize CQD data that you find under **Users**.</span></span>  |
|<span data-ttu-id="96761-113">CQD 포털 [( https://cqd.teams.microsoft.com) ](https://cqd.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="96761-113">CQD portal [(https://cqd.teams.microsoft.com)](https://cqd.teams.microsoft.com)</span></span>     | <span data-ttu-id="96761-114">드릴스루 필터링을 사용 하 여 대부분의 요구를 충족 하는 강력한 요약 및 상세 보고서.</span><span class="sxs-lookup"><span data-stu-id="96761-114">Robust summary and detailed reports that meet most needs, with drill-through filtering.</span></span> <span data-ttu-id="96761-115">CQD 포털에서 보고서를 사용자 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-115">You can also customize reports in the CQD portal.</span></span> <br><br><span data-ttu-id="96761-116">CQD 포털에서 데이터를 분석 하는 데 도움이 되는 두 개의 [cqd 보고서 서식 파일](#import-the-cqd-report-templates) 을 다운로드 하세요.</span><span class="sxs-lookup"><span data-stu-id="96761-116">Get two [CQD report templates](#import-the-cqd-report-templates) to help you analyze data in the CQD portal.</span></span>       |
|<span data-ttu-id="96761-117">Power BI</span><span class="sxs-lookup"><span data-stu-id="96761-117">Power BI</span></span>     | <span data-ttu-id="96761-118">직접 쿼리를 사용 하 여 Power BI에서 [사용자 지정 가능한 POWER bi 서식 파일](CQD-Power-BI-query-templates.md)을 사용 하 여 CQD 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-118">Use direct queries to view your CQD data in Power BI using [customizable Power BI templates](CQD-Power-BI-query-templates.md).</span></span> <span data-ttu-id="96761-119">[CQD 용 POWER BI 쿼리 서식 파일을 다운로드](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-119">[Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span><br><br><span data-ttu-id="96761-120">또한 REST API를 사용 하 여 Power BI를 통해 [CQD 데이터에 액세스할](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/data-api) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-120">You can also [use the REST API to access CQD data](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/data-api) through Power BI.</span></span> <span data-ttu-id="96761-121">이 방법을 사용 하 여 오프 라인으로 작업할 수 있도록 CQD 데이터를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-121">Use this method if you want to download your CQD data so you can work on it offline.</span></span> <span data-ttu-id="96761-122">이 방법을 사용 하면 성능이 향상 되는 데, 특히 온라인 상태일 때 Power BI에서 bog 하는 대규모 데이터 집합에 유용 하 게 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-122">The benefit of using this method is better performance, especially useful for large data sets that bog down in Power BI when you're online.</span></span>       |
|<span data-ttu-id="96761-123">그래프 API</span><span class="sxs-lookup"><span data-stu-id="96761-123">Graph API</span></span>     | <span data-ttu-id="96761-124">[GRAPH API](https://docs.microsoft.com/graph/api/resources/callrecords-api-overview?view=graph-rest-beta)를 사용 하 여 직접 통화 품질 데이터에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-124">Access call quality data yourself using the [Graph API](https://docs.microsoft.com/graph/api/resources/callrecords-api-overview?view=graph-rest-beta).</span></span> <span data-ttu-id="96761-125">가장 복잡 한 방법 이지만, 통화 품질 데이터를 분석 하는 것은 대부분의 제어 및 유연성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-125">This is the most complex method, but it gives you the most control and flexibility in analyzing your call quality data.</span></span> <span data-ttu-id="96761-126">예를 들어 조직의 다른 데이터와 조인 해야 하는 경우 그래프 API를 사용 하 여 데이터 모델을 만들고 통화 품질 데이터를 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-126">For example, if you need to join it with other data for your organization, you can use the Graph API to create a data model and incorporate call quality data.</span></span>        |

## <a name="import-the-cqd-report-templates"></a><span data-ttu-id="96761-127">CQD 보고서 서식 파일 가져오기</span><span class="sxs-lookup"><span data-stu-id="96761-127">Import the CQD report templates</span></span>

<span data-ttu-id="96761-128">CQD를 사용 하 여 신속 하 게 속도를 높일 수 있도록 [두 개의 큐 레이 팅 CQD 보고서 서식 파일](https://aka.ms/qertemplates) (모든 네트워크 및 관리 되는 네트워크)을 다운로드 하세요.</span><span class="sxs-lookup"><span data-stu-id="96761-128">Download [two curated CQD report templates](https://aka.ms/qertemplates) (All Networks and Managed Networks) to help you get up to speed quickly with CQD.</span></span> <span data-ttu-id="96761-129">모든 네트워크 템플릿은 빌드 데이터 파일을 사용 하 여 작업 하도록 최적화 되었지만 다음 섹션에서 설명 하는 대로 CQD에 빌드 정보를 수집 하 고 업로드 하는 데 사용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-129">The All Networks template, though optimized to work with a building data file, can be used while you work toward collecting and uploading building information into CQD, as described in the next section.</span></span>

<span data-ttu-id="96761-130">**템플릿을 가져오려면 (. CQDX)를 CQDX에**</span><span class="sxs-lookup"><span data-stu-id="96761-130">**To import the templates (.CQDX) into CQD**</span></span>

1. <span data-ttu-id="96761-131">CQD의 경우 페이지 맨 위에 있는 메뉴에서 **상세 보고서** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-131">In CQD, select **Detailed Reports** from the menu at the top of the page.</span></span>

2. <span data-ttu-id="96761-132">왼쪽 패널에서 **가져오기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-132">In the left panel, select **Import**.</span></span> <span data-ttu-id="96761-133">첫 번째 CQDX 서식 파일을 찾아 **열기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-133">Browse to the first CQDX template and select **Open**.</span></span>

3. <span data-ttu-id="96761-134">서식 파일을 업로드 한 후 팝업 창에 "보고서를 성공적으로 가져오기 했습니다." 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-134">After the template is uploaded, a pop-up window will display the message "Report import was successful."</span></span> 

4. <span data-ttu-id="96761-135">두 번째 CQD 템플릿에 대해 2 ~ 3 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-135">Repeat steps 2 and 3 for the second CQD template.</span></span>

> [!NOTE]
> <span data-ttu-id="96761-136">각 사용자는 CQD 템플릿을 해당 CQD 인스턴스로 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-136">Each user must import the CQD templates into their CQD instance.</span></span> 



## <a name="euii-data"></a><span data-ttu-id="96761-137">EUII 데이터</span><span class="sxs-lookup"><span data-stu-id="96761-137">EUII data</span></span>

<span data-ttu-id="96761-138">준수 상의 이유로 최종 사용자 식별 가능 정보 (EUII) 데이터 (개인 식별이 가능한 정보 또는 PII 라고도 함)는 30 일간만 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-138">For compliance reasons, end-user identifiable information (EUII) data (also known as personally-identifiable information or PII) is only kept for 30 days.</span></span> <span data-ttu-id="96761-139">NRT 데이터가 30 일 표시에 교차 하면 EUII를 포함 하는 필드는 지워지고 EUII-free NRT 데이터가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-139">As NRT data crosses the 30-day mark, fields that contain EUII are cleared, resulting in EUII-free NRT data.</span></span> <span data-ttu-id="96761-140">EUII 데이터를 포함 하는 필드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-140">Fields that contain EUII data are:</span></span>

- <span data-ttu-id="96761-141">전체 IP 주소</span><span class="sxs-lookup"><span data-stu-id="96761-141">Full IP address</span></span>
- <span data-ttu-id="96761-142">MAC (미디어 액세스 제어) 주소</span><span class="sxs-lookup"><span data-stu-id="96761-142">Media Access Control (MAC) Address</span></span>
- <span data-ttu-id="96761-143">기본 BSSID (서비스 집합 id)</span><span class="sxs-lookup"><span data-stu-id="96761-143">Basic Service Set identifier (BSSID)</span></span>
- <span data-ttu-id="96761-144">SIP (세션 초기화 프로토콜) URI (비즈니스용 Skype에만 해당)</span><span class="sxs-lookup"><span data-stu-id="96761-144">Session Initiation Protocol (SIP) URI (Skype for Business only)</span></span>
- <span data-ttu-id="96761-145">UPN (사용자 계정 이름)</span><span class="sxs-lookup"><span data-stu-id="96761-145">User Principal Name (UPN)</span></span>
- <span data-ttu-id="96761-146">컴퓨터 끝점 이름</span><span class="sxs-lookup"><span data-stu-id="96761-146">Machine Endpoint Name</span></span>
- <span data-ttu-id="96761-147">사용자 약어 피드백</span><span class="sxs-lookup"><span data-stu-id="96761-147">User Verbatim Feedback</span></span>
- <span data-ttu-id="96761-148">개체 ID (끝점 사용자의 Active Directory 개체 ID)</span><span class="sxs-lookup"><span data-stu-id="96761-148">Object ID (the Active Directory object ID of the endpoint's user)</span></span>

### <a name="admin-roles-with-and-without-euii-access"></a><span data-ttu-id="96761-149">EUII 액세스를 포함 하거나 사용 하지 않고 관리 역할</span><span class="sxs-lookup"><span data-stu-id="96761-149">Admin roles with and without EUII access</span></span>

<span data-ttu-id="96761-150">다음 [RBAC](https://docs.microsoft.com/azure/role-based-access-control/overview) 역할에는 EUII 액세스 **권한이 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="96761-150">These [RBAC](https://docs.microsoft.com/azure/role-based-access-control/overview) roles **DO** have EUII access:</span></span>
- <span data-ttu-id="96761-151">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="96761-151">Global Admin</span></span>
- <span data-ttu-id="96761-152">팀 서비스 관리자</span><span class="sxs-lookup"><span data-stu-id="96761-152">Teams Service Admin</span></span>
- <span data-ttu-id="96761-153">팀 의사 소통 관리자</span><span class="sxs-lookup"><span data-stu-id="96761-153">Teams Communications Admin</span></span>
- <span data-ttu-id="96761-154">Teams 커뮤니케이션 지원 엔지니어</span><span class="sxs-lookup"><span data-stu-id="96761-154">Teams Communications Support Engineer</span></span>
- <span data-ttu-id="96761-155">전역 읽기 프로그램</span><span class="sxs-lookup"><span data-stu-id="96761-155">Global Reader</span></span>
- <span data-ttu-id="96761-156">비즈니스용 Skype 관리자</span><span class="sxs-lookup"><span data-stu-id="96761-156">Skype for Business Admin</span></span>

<span data-ttu-id="96761-157">이 RBAC 역할에는 EUII 액세스 **권한이 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="96761-157">These RBAC roles **DON'T** have EUII access:</span></span>
- <span data-ttu-id="96761-158">보고서 읽기 프로그램</span><span class="sxs-lookup"><span data-stu-id="96761-158">Reports Reader</span></span>
- <span data-ttu-id="96761-159">팀 의사 소통 지원 전문가</span><span class="sxs-lookup"><span data-stu-id="96761-159">Teams Communications Support Specialist</span></span>


## <a name="date-controls"></a><span data-ttu-id="96761-160">날짜 컨트롤</span><span class="sxs-lookup"><span data-stu-id="96761-160">Date controls</span></span>

<span data-ttu-id="96761-161">CQD는 다음 롤링 추세 유형을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-161">CQD supports the following Rolling Trend types:</span></span>

- <span data-ttu-id="96761-162">5 일</span><span class="sxs-lookup"><span data-stu-id="96761-162">5-day</span></span>
- <span data-ttu-id="96761-163">7 일</span><span class="sxs-lookup"><span data-stu-id="96761-163">7-day</span></span>
- <span data-ttu-id="96761-164">30 일</span><span class="sxs-lookup"><span data-stu-id="96761-164">30-day</span></span>
- <span data-ttu-id="96761-165">60-일</span><span class="sxs-lookup"><span data-stu-id="96761-165">60-day</span></span>
- <span data-ttu-id="96761-166">90-일</span><span class="sxs-lookup"><span data-stu-id="96761-166">90-day</span></span>

<span data-ttu-id="96761-167">URL 날짜 매개 변수는 Day 필드를 받아들입니다.</span><span class="sxs-lookup"><span data-stu-id="96761-167">The URL Date parameter accepts a Day field.</span></span> <span data-ttu-id="96761-168">일 단위 보고서는 해당 추세의 마지막 날로 YYYY-MM-DD 형식으로 지정 된 날짜를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-168">Rolling-day reports use dates specified in the YYYY-MM-DD format as the last day of the trend.</span></span> <span data-ttu-id="96761-169">URL 날짜 매개 변수 "00"은 "오늘"을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="96761-169">The URL Date parameter “00”  indicates “today”.</span></span>

|<span data-ttu-id="96761-170">URL</span><span class="sxs-lookup"><span data-stu-id="96761-170">URL</span></span>| <span data-ttu-id="96761-171">롤링 일 추세의 종료 날짜</span><span class="sxs-lookup"><span data-stu-id="96761-171">End date of Rolling Day Trend</span></span>|
|:---|:---|
|<span data-ttu-id="96761-172"><span>https:// <cqdv3> /spd/#/쇄선/ <reportid> /2019-02/</span></span><span class="sxs-lookup"><span data-stu-id="96761-172"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/2019-02/</span></span></span>   |<span data-ttu-id="96761-173">현재 날짜 2 월 2019</span><span class="sxs-lookup"><span data-stu-id="96761-173">Current Day of Feb 2019</span></span>|
|<span data-ttu-id="96761-174"><span>https:// <cqdv3> /spd/#/쇄선/ <reportid> /2019-02-15/</span></span><span class="sxs-lookup"><span data-stu-id="96761-174"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/2019-02-15/</span></span></span>|<span data-ttu-id="96761-175">2 월 15 일 2019</span><span class="sxs-lookup"><span data-stu-id="96761-175">Feb 15, 2019</span></span>|
|<span data-ttu-id="96761-176"><span>https:// <cqdv3> /spd/#/쇄선/ <reportid> /00/</span></span><span class="sxs-lookup"><span data-stu-id="96761-176"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/00/</span></span></span>        |<span data-ttu-id="96761-177">현재 일</span><span class="sxs-lookup"><span data-stu-id="96761-177">Current Day</span></span>|
|||

<span data-ttu-id="96761-178">기본적으로 현재 날짜는 이동 하는 일 추세의 마지막 날로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-178">By default, the current day of the month is used as the last day of the Rolling Day Trend.</span></span>


## <a name="data-available-in-cqd-reports"></a><span data-ttu-id="96761-179">CQD 보고서에서 사용할 수 있는 데이터</span><span class="sxs-lookup"><span data-stu-id="96761-179">Data available in CQD reports</span></span>

<span data-ttu-id="96761-180">기본 요약 및 세부 CQD 보고서는 조직의 통화 품질을 관리 하는 데 필요할 수 있습니다. 필요한 경우 [사용자 지정 보고서를 만들](#create-custom-detailed-reports)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-180">The default summary and detailed CQD reports may be all you need to manage call quality for your org. If you need to, you can [create custom reports](#create-custom-detailed-reports).</span></span> 

<span data-ttu-id="96761-181">Power BI를 사용 하 여 CQD 데이터를 분석 하려면 [POWER bi를 사용 하 여 팀에 대 한 CQD 데이터 분석](CQD-Power-BI-query-templates.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96761-181">If you want to use Power BI to analyze your CQD data, read [Use Power BI to analyze CQD data for Teams](CQD-Power-BI-query-templates.md).</span></span>

|<span data-ttu-id="96761-182">기능</span><span class="sxs-lookup"><span data-stu-id="96761-182">Feature</span></span>|<span data-ttu-id="96761-183">요약 보고서</span><span class="sxs-lookup"><span data-stu-id="96761-183">Summary Reports</span></span>|<span data-ttu-id="96761-184">자세한 보고서</span><span class="sxs-lookup"><span data-stu-id="96761-184">Detailed Reports</span></span>|
|:--- |:--- |:--- |
|<span data-ttu-id="96761-185">응용 프로그램 공유 메트릭</span><span class="sxs-lookup"><span data-stu-id="96761-185">Application sharing metric</span></span> | <span data-ttu-id="96761-186">아니요</span><span class="sxs-lookup"><span data-stu-id="96761-186">No</span></span> | <span data-ttu-id="96761-187">예</span><span class="sxs-lookup"><span data-stu-id="96761-187">Yes</span></span> |
|<span data-ttu-id="96761-188">고객 건물 정보 지원</span><span class="sxs-lookup"><span data-stu-id="96761-188">Customer building information support</span></span> | <span data-ttu-id="96761-189">예</span><span class="sxs-lookup"><span data-stu-id="96761-189">Yes</span></span> | <span data-ttu-id="96761-190">예</span><span class="sxs-lookup"><span data-stu-id="96761-190">Yes</span></span> |
|<span data-ttu-id="96761-191">고객 끝점 정보 지원</span><span class="sxs-lookup"><span data-stu-id="96761-191">Customer endpoint information support</span></span> | <span data-ttu-id="96761-192">Cqd.teams.microsoft.com 에서만 <span><span/></span><span class="sxs-lookup"><span data-stu-id="96761-192">Only in <span>cqd.teams.microsoft.com<span/></span></span> | <span data-ttu-id="96761-193">Cqd.teams.microsoft.com 에서만 <span><span/></span><span class="sxs-lookup"><span data-stu-id="96761-193">Only in <span>cqd.teams.microsoft.com<span/></span></span> |
|<span data-ttu-id="96761-194">드릴 다운 분석 지원</span><span class="sxs-lookup"><span data-stu-id="96761-194">Drill down analysis support</span></span>   | <span data-ttu-id="96761-195">아니요</span><span class="sxs-lookup"><span data-stu-id="96761-195">No</span></span>   | <span data-ttu-id="96761-196">예</span><span class="sxs-lookup"><span data-stu-id="96761-196">Yes</span></span>   |
|<span data-ttu-id="96761-197">미디어 안정성 메트릭</span><span class="sxs-lookup"><span data-stu-id="96761-197">Media reliability metrics</span></span>   | <span data-ttu-id="96761-198">아니요</span><span class="sxs-lookup"><span data-stu-id="96761-198">No</span></span>   | <span data-ttu-id="96761-199">예</span><span class="sxs-lookup"><span data-stu-id="96761-199">Yes</span></span>   |
|<span data-ttu-id="96761-200">오래 된 보고서</span><span class="sxs-lookup"><span data-stu-id="96761-200">Out-of-the-box reports</span></span>   | <span data-ttu-id="96761-201">예</span><span class="sxs-lookup"><span data-stu-id="96761-201">Yes</span></span>   | <span data-ttu-id="96761-202">예</span><span class="sxs-lookup"><span data-stu-id="96761-202">Yes</span></span>   |
|<span data-ttu-id="96761-203">개요 보고서</span><span class="sxs-lookup"><span data-stu-id="96761-203">Overview reports</span></span>   | <span data-ttu-id="96761-204">예</span><span class="sxs-lookup"><span data-stu-id="96761-204">Yes</span></span>   | <span data-ttu-id="96761-205">예</span><span class="sxs-lookup"><span data-stu-id="96761-205">Yes</span></span>   |
|<span data-ttu-id="96761-206">사용자 단위 보고서 집합</span><span class="sxs-lookup"><span data-stu-id="96761-206">Per-user report set</span></span>   | <span data-ttu-id="96761-207">아니요</span><span class="sxs-lookup"><span data-stu-id="96761-207">No</span></span>   | <span data-ttu-id="96761-208">예</span><span class="sxs-lookup"><span data-stu-id="96761-208">Yes</span></span>   |
|<span data-ttu-id="96761-209">보고서 집합 사용자 지정 (보고서 추가, 삭제, 수정)</span><span class="sxs-lookup"><span data-stu-id="96761-209">Report set customization (add, delete, modify reports)</span></span>   | <span data-ttu-id="96761-210">아니요</span><span class="sxs-lookup"><span data-stu-id="96761-210">No</span></span>   | <span data-ttu-id="96761-211">예</span><span class="sxs-lookup"><span data-stu-id="96761-211">Yes</span></span>   |
|<span data-ttu-id="96761-212">비디오 기반 화면 공유 메트릭</span><span class="sxs-lookup"><span data-stu-id="96761-212">Video-based screen sharing metrics</span></span>   | <span data-ttu-id="96761-213">아니요</span><span class="sxs-lookup"><span data-stu-id="96761-213">No</span></span>   | <span data-ttu-id="96761-214">예</span><span class="sxs-lookup"><span data-stu-id="96761-214">Yes</span></span>   |
|<span data-ttu-id="96761-215">비디오 메트릭</span><span class="sxs-lookup"><span data-stu-id="96761-215">Video metrics</span></span>   | <span data-ttu-id="96761-216">아니요</span><span class="sxs-lookup"><span data-stu-id="96761-216">No</span></span>   | <span data-ttu-id="96761-217">예</span><span class="sxs-lookup"><span data-stu-id="96761-217">Yes</span></span>   |
|<span data-ttu-id="96761-218">사용할 수 있는 데이터 양</span><span class="sxs-lookup"><span data-stu-id="96761-218">Amount of data available</span></span>   | <span data-ttu-id="96761-219">지난 12 개월</span><span class="sxs-lookup"><span data-stu-id="96761-219">Last 12 months</span></span>   | <span data-ttu-id="96761-220">지난 12 개월</span><span class="sxs-lookup"><span data-stu-id="96761-220">Last 12 months</span></span>   |
|<span data-ttu-id="96761-221">Microsoft 팀 데이터</span><span class="sxs-lookup"><span data-stu-id="96761-221">Microsoft Teams data</span></span>   | <span data-ttu-id="96761-222">예</span><span class="sxs-lookup"><span data-stu-id="96761-222">Yes</span></span>   | <span data-ttu-id="96761-223">예</span><span class="sxs-lookup"><span data-stu-id="96761-223">Yes</span></span>   |
| | | |


 
### <a name="select-product-data-to-see-in-reports"></a><span data-ttu-id="96761-224">보고서에 표시할 제품 데이터 선택</span><span class="sxs-lookup"><span data-stu-id="96761-224">Select product data to see in reports</span></span>

<span data-ttu-id="96761-225">요약 및 위치 향상 보고서에서 **제품 필터** 드롭다운을 사용 하 여 모든 제품 데이터, Microsoft 팀 데이터만 표시 하거나 비즈니스용 Skype Online 데이터만 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-225">In the Summary and Location-Enhanced Reports, you can use the **Product Filter** drop-down to show all product data, only Microsoft Teams data, or only Skype for Business Online data.</span></span>
  
![스크린샷: 제품 필터 컨트롤 옵션을 표시 합니다.](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
<span data-ttu-id="96761-227">자세한 보고서에서는 **Is 팀** 차원을 사용 하 여 데이터를 Microsoft 팀 또는 비즈니스용 Skype Online 데이터로 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-227">In Detailed reports, you can use the **Is Teams** dimension to filter the data to Microsoft Teams or Skype for Business Online data.</span></span>

## <a name="summary-reports"></a><span data-ttu-id="96761-228">요약 보고서</span><span class="sxs-lookup"><span data-stu-id="96761-228">Summary Reports</span></span>

<span data-ttu-id="96761-229">다음은 CQD에 처음 로그인 할 때 CQD 대시보드에 표시 되는 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="96761-229">These are the reports that you'll see on the CQD Dashboard when you first sign in to CQD.</span></span> <span data-ttu-id="96761-230">이를 통해 일일, 월간 및 테이블 보고서를 사용 하 여 품질이 나쁜 서브넷을 식별 하는 데 도움이 되는 품질 추세를 한눈에 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-230">They give you an at-a-glance look at quality trends with daily, monthly, and table reports to assist with identifying subnets that have poor quality.</span></span> 

|<span data-ttu-id="96761-231">탭</span><span class="sxs-lookup"><span data-stu-id="96761-231">Tab</span></span>  |  |
|---------|---------|
|<span data-ttu-id="96761-232">전체 통화 음질</span><span class="sxs-lookup"><span data-stu-id="96761-232">Overall Call Quality</span></span>     | <span data-ttu-id="96761-233">다른 3 개의 탭 집계</span><span class="sxs-lookup"><span data-stu-id="96761-233">Aggregate of the other 3 tabs</span></span>        |
|<span data-ttu-id="96761-234">Server-클라이언트</span><span class="sxs-lookup"><span data-stu-id="96761-234">Server—Client</span></span>     |<span data-ttu-id="96761-235">서버 및 클라이언트 끝점 간 스트림에 대 한 세부 정보</span><span class="sxs-lookup"><span data-stu-id="96761-235">Details of the streams between server and client endpoints</span></span>         |
|<span data-ttu-id="96761-236">클라이언트-클라이언트</span><span class="sxs-lookup"><span data-stu-id="96761-236">Client—Client</span></span>     |<span data-ttu-id="96761-237">두 클라이언트 끝점 간 스트림의 세부 정보</span><span class="sxs-lookup"><span data-stu-id="96761-237">Details of the streams between two client endpoints</span></span>         |
|<span data-ttu-id="96761-238">음성 품질 SLA</span><span class="sxs-lookup"><span data-stu-id="96761-238">Voice Quality SLA</span></span>     |<span data-ttu-id="96761-239">비즈니스용 Skype 음성 품질 [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252) 에 포함 된 통화에 대 한 정보</span><span class="sxs-lookup"><span data-stu-id="96761-239">Info about calls included in the Skype for Business voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)</span></span>         |

### <a name="overall-call-quality-tab"></a><span data-ttu-id="96761-240">전체 통화 음질 탭</span><span class="sxs-lookup"><span data-stu-id="96761-240">Overall Call Quality tab</span></span>

<span data-ttu-id="96761-241">이 탭의 데이터를 사용 하 여 통화 품질 상태와 스트림 개수 및 낮은 백분율을 기준으로 추세를 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-241">Use the data on this tab to evaluate call quality status and trends based on stream counts and poor percentages.</span></span> <span data-ttu-id="96761-242">오른쪽 위 모서리에 있는 범례는 이러한 메트릭을 나타내는 색 및 시각적 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="96761-242">The legend in the upper-right corner shows which color and visual elements represent these metrics.</span></span>
  
![스크린샷: 통화 품질 탭 표시](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
<span data-ttu-id="96761-244">스트림은 세 가지 그룹 (좋음, 나쁨, 미분류)으로 분류 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-244">Streams are classified in three groups: Good, Poor, and Unclassified.</span></span> <span data-ttu-id="96761-245">또한 총 분류 스트림 개수에 *좋지* 않은 스트림의 비율을 제공 하는 *불량%* 값이 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-245">There are also calculated  *Poor %*  values that give you the ratio of streams classified as *Poor*  to the total classified stream count.</span></span> <span data-ttu-id="96761-246">*불량% = 불량 스트림/(불량 스트림 + 양호한 스트림) \* 100*의 경우 *잘못 된%* 가 여러 개의 *분류* 되지 않은 스트림의 존재 여부에 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-246">Since *Poor % = Poor streams/ (Poor streams+ Good streams) \* 100*, the *Poor %*  is unaffected by the presence of multiple *Unclassified*  streams.</span></span> <span data-ttu-id="96761-247">스트림이 불량 또는 양호한 것으로 분류 하는 것을 확인 하려면 [통화 품질 대시보드의 스트림 분류](stream-classification-in-call-quality-dashboard.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96761-247">To see what classifies a stream as poor or good, refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md).</span></span>
  
<span data-ttu-id="96761-248">왼쪽의 배율을 사용 하 여 스트림 개수 값을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-248">Use the scale on the left to measure the stream count values.</span></span>
  
![스크린샷: 스트림 개수 값 표시](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
<span data-ttu-id="96761-250">오른쪽의 배율을 사용 하 여 불량% 값을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-250">Use the scale on the right to measure the Poor % values.</span></span>
  
![스크린샷: 불량% 값 표시](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
<span data-ttu-id="96761-252">막대 위로 마우스를 가져가면 실제 숫자 값을 구할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-252">You can also obtain the actual numerical values by hovering the mouse over a bar.</span></span>
  
> [!NOTE]
> <span data-ttu-id="96761-253">다음 예제는 매우 작은 샘플 데이터 집합에서 가져온 것 이며, 실제 배포에 대해 값이 사실적이 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-253">The following example is from a very small sample data set, and the values aren't realistic for an actual deployment.</span></span>
  
![스크린샷: 데이터에 액세스 하는 데 사용 되는 마우스 표시](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
<span data-ttu-id="96761-255">전체 스트림 볼륨은 계산 된 낮은 백분율이 얼마나 적절 하지 않을 지 결정 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-255">The overall stream volume helps determine how relevant the calculated Poor percentages are.</span></span> <span data-ttu-id="96761-256">전체 스트림의 볼륨이 작을수록 낮은 신뢰 값이 신고 된 것으로 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-256">The smaller the volume of overall streams, the less reliable the reported Poor percentage values are.</span></span>
  
### <a name="server-client-tab-and-client-client-tabs"></a><span data-ttu-id="96761-257">서버-클라이언트 탭 및 클라이언트 클라이언트 탭</span><span class="sxs-lookup"><span data-stu-id="96761-257">Server-Client tab and Client-Client tabs</span></span>

<span data-ttu-id="96761-258">이러한 두 탭은 끝점 대 끝점 시나리오에서 발생 한 스트림에 대 한 세부 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-258">These two tabs provide details for the streams that took place in their endpoint-to-endpoint scenarios.</span></span> <span data-ttu-id="96761-259">서버 클라이언트 탭에는 미디어 스트림이 흐르는 네 가지 시나리오를 나타내는 4 개의 축소할 수 있는 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-259">The Server-Client tab has four collapsible sections that represent four scenarios under which media streams would flow.</span></span>
  
- <span data-ttu-id="96761-260">유선 내부</span><span class="sxs-lookup"><span data-stu-id="96761-260">Wired Inside</span></span>
- <span data-ttu-id="96761-261">유선 외부</span><span class="sxs-lookup"><span data-stu-id="96761-261">Wired Outside</span></span>
- <span data-ttu-id="96761-262">WiFi 내부</span><span class="sxs-lookup"><span data-stu-id="96761-262">WiFi Inside</span></span>
- <span data-ttu-id="96761-263">WiFi 외부</span><span class="sxs-lookup"><span data-stu-id="96761-263">WiFi Outside</span></span>

<span data-ttu-id="96761-264">마찬가지로, 클라이언트-클라이언트 탭에는 다음과 같은 5 개의 축소 가능 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-264">Similarly, the Client-Client tab has five collapsible sections:</span></span>

- <span data-ttu-id="96761-265">유선 내부-유선 내부</span><span class="sxs-lookup"><span data-stu-id="96761-265">Wired Inside — Wired Inside</span></span>
- <span data-ttu-id="96761-266">유선 내부-유선 외부</span><span class="sxs-lookup"><span data-stu-id="96761-266">Wired Inside — Wired Outside</span></span>
- <span data-ttu-id="96761-267">유선 외부-유선 외부</span><span class="sxs-lookup"><span data-stu-id="96761-267">Wired Outside — Wired Outside</span></span>
- <span data-ttu-id="96761-268">유선 내부-WiFi 내부</span><span class="sxs-lookup"><span data-stu-id="96761-268">Wired Inside — WiFi Inside</span></span>
- <span data-ttu-id="96761-269">유선 내부-WiFi 외부</span><span class="sxs-lookup"><span data-stu-id="96761-269">Wired Inside — WiFi Outside</span></span>

#### <a name="inside-versus-outside"></a><span data-ttu-id="96761-270">내부 및 외부</span><span class="sxs-lookup"><span data-stu-id="96761-270">Inside versus Outside</span></span>

<span data-ttu-id="96761-271">CQD는 스트림을 빌드 정보 (있는 경우)를 사용 하 여 *내부* 또는 *외부로* 분류 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-271">CQD classifies a stream as  *Inside*  or *Outside*  using Building information, if it exists.</span></span> <span data-ttu-id="96761-272">각 스트림의 끝점은 서브넷 주소와 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-272">Endpoints of each stream are associated with a subnet address.</span></span> <span data-ttu-id="96761-273">서브넷이 업로드 된 빌드 정보에서 InsideCorp로 표시 된 서브넷 목록에 있는 경우 *내부*로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-273">If the subnet is in the list of the subnets marked InsideCorp in the uploaded Building information, then it is considered *Inside*.</span></span> <span data-ttu-id="96761-274">@ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ *Outside*@ @ @ @ @ @ @ @ @ @ @ Test</span><span class="sxs-lookup"><span data-stu-id="96761-274">If Building information has not yet been uploaded, then Inside Test always classifies the streams as *Outside*.</span></span> 

<span data-ttu-id="96761-275">서버 클라이언트 시나리오의 내부 테스트에서는 클라이언트 끝점만 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-275">The Inside Test for a Server-Client scenario only considers the client endpoint.</span></span> <span data-ttu-id="96761-276">서버는 항상 사용자의 관점에서 벗어나므로이는 테스트에서 고려 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-276">Because servers are always outside from a user's perspective, this isn't accounted for in the test.</span></span>
  
#### <a name="wired-versus-wifi"></a><span data-ttu-id="96761-277">유선 및 WiFi</span><span class="sxs-lookup"><span data-stu-id="96761-277">Wired versus WiFi</span></span>

<span data-ttu-id="96761-278">이름이 나타내는 대로 분류 조건은 클라이언트 연결 유형을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-278">As the names indicate, the classification criteria is based on the type of client connections.</span></span> <span data-ttu-id="96761-279">서버는 항상 유선 이며 계산에 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-279">Server is always wired and it isn't included in the calculation.</span></span> <span data-ttu-id="96761-280">지정 된 스트림에서 두 끝점 중 하나가 WiFi 네트워크에 연결 되어 있는 경우 CQD는이를 WiFi로 분류 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-280">In a given stream, if one of the two endpoints is connected to a WiFi network, then CQD classifies it as WiFi.</span></span>
> [!NOTE]
> <span data-ttu-id="96761-281">두 끝점 중 하나가 WiFi 네트워크에 연결 되어 있는 경우 스트림이 제공 되 면 CQD에서 WiFi로 분류 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-281">Given a stream, if one of the two endpoints is connected to a WiFi network, then it is classified as WiFi in CQD.</span></span>
  
  
## <a name="tenant-data-information"></a><span data-ttu-id="96761-282">테 넌 트 데이터 정보</span><span class="sxs-lookup"><span data-stu-id="96761-282">Tenant Data information</span></span>

<span data-ttu-id="96761-283">CQD 요약 보고서 대시보드의 오른쪽 위 모서리에 있는 설정 메뉴에서 **테 넌 트 데이터 업로드** 를 선택 하 여 액세스 하는 **테 넌 트 데이터 업로드** 페이지가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-283">The CQD Summary Reports dashboard includes a **Tenant Data Upload** page, accessed by selecting **Tenant Data Upload** from the settings menu in the top-right corner.</span></span> <span data-ttu-id="96761-284">이 페이지는 관리자가 다음과 같은 자신의 정보를 업로드 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-284">This page is used for admins to upload their own information, such as:</span></span>

- <span data-ttu-id="96761-285">IP 주소 및 지리 정보의 지도</span><span class="sxs-lookup"><span data-stu-id="96761-285">A map of IP address and geographical information</span></span>
- <span data-ttu-id="96761-286">각 무선 AP 및 MAC 주소의 지도</span><span class="sxs-lookup"><span data-stu-id="96761-286">A map of each wireless AP and its MAC address</span></span>
- <span data-ttu-id="96761-287">끝점을 끝점으로 설정/모델/형식 등으로 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-287">A map of Endpoint to Endpoint Make/Model/Type, etc.</span></span>
  
<span data-ttu-id="96761-288">테 넌 트, 빌드 및 위치 데이터를 업로드 하는 것이 좋으며,이 정보는 CQD가 보고서에 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-288">We recommend that you upload your tenant, building, and location data so CQD can include this information in your reports.</span></span> <span data-ttu-id="96761-289">이 데이터를 아직 업로드 하지 않은 경우에는 [테 넌 트 업로드 및 데이터 작성](CQD-upload-tenant-building-data.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96761-289">If you haven't already uploaded this data, read [Upload tenant and building data](CQD-upload-tenant-building-data.md).</span></span> 


## <a name="detailed-reports"></a><span data-ttu-id="96761-290">자세한 보고서</span><span class="sxs-lookup"><span data-stu-id="96761-290">Detailed reports</span></span>

|<span data-ttu-id="96761-291">이름</span><span class="sxs-lookup"><span data-stu-id="96761-291">Name</span></span>  |  |
|---------|---------|
|<span data-ttu-id="96761-292">위치 향상 보고서</span><span class="sxs-lookup"><span data-stu-id="96761-292">Location-Enhanced Reports</span></span>     |<span data-ttu-id="96761-293">위치 정보를 기준으로 품질 추세를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-293">Shows quality trends based on location information.</span></span> <span data-ttu-id="96761-294">이 보고서는 [테 넌 트 데이터를 업로드](CQD-upload-tenant-building-data.md)한 경우에만 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="96761-294">This report appears only if you've [uploaded your tenant data](CQD-upload-tenant-building-data.md).</span></span>        |
|<span data-ttu-id="96761-295">안정성 보고서</span><span class="sxs-lookup"><span data-stu-id="96761-295">Reliability Reports</span></span>     |<span data-ttu-id="96761-296">오디오, 비디오, 비디오 기반 화면 공유 (VBSS), 앱 공유 보고서가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-296">Includes audio, video, video-based screen sharing (VBSS), and app sharing reports</span></span>         |
|<span data-ttu-id="96761-297">경력 보고서의 품질</span><span class="sxs-lookup"><span data-stu-id="96761-297">Quality of Experience Reports</span></span>     |<span data-ttu-id="96761-298">회의실을 비롯 한 모든 클라이언트 및 장치에 대 한 오디오 품질 및 안정성</span><span class="sxs-lookup"><span data-stu-id="96761-298">Audio quality and reliability for all clients and devices, including meeting rooms.</span></span> <span data-ttu-id="96761-299">이러한 보고서는 다운로드 가능한 [Cqd 템플릿의](https://aka.ms/QERtemplates)"slimmed" 버전으로, 오디오 품질 및 안정성 분석을 위한 주요 영역에 중점을 두는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="96761-299">These reports are a “slimmed-down” version of the downloadable [CQD templates](https://aka.ms/QERtemplates), focusing on key areas for analyzing audio quality and reliability.</span></span>         |
|<span data-ttu-id="96761-300">품질 드릴 다운 보고서</span><span class="sxs-lookup"><span data-stu-id="96761-300">Quality Drill Down Reports</span></span>     | <span data-ttu-id="96761-301">드릴 다운: 지역, 위치, 서브넷, 시간 및 사용자 기준 날짜</span><span class="sxs-lookup"><span data-stu-id="96761-301">Drill downs: Date by region, locations, subnets, hour, and users</span></span>         |
|<span data-ttu-id="96761-302">오류 드릴 다운 보고서</span><span class="sxs-lookup"><span data-stu-id="96761-302">Failure Drill Down Reports</span></span>     | <span data-ttu-id="96761-303">드릴 다운: 지역, 위치, 서브넷, 시간 및 사용자 기준 날짜</span><span class="sxs-lookup"><span data-stu-id="96761-303">Drill downs: Date by region, locations, subnets, hour, and users</span></span>        |
|<span data-ttu-id="96761-304">내 통화 보고서 평가</span><span class="sxs-lookup"><span data-stu-id="96761-304">Rate My Call Reports</span></span>     |<span data-ttu-id="96761-305">지역, 위치 또는 사용자별로 사용자 통화 등급을 분석 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-305">Analyze user call ratings by region, location, or by user.</span></span> <span data-ttu-id="96761-306">약어에 대 한 피드백을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-306">Includes verbatim feedback.</span></span>         |
|<span data-ttu-id="96761-307">지원 센터 보고서</span><span class="sxs-lookup"><span data-stu-id="96761-307">Help Desk Reports</span></span>     |<span data-ttu-id="96761-308">지원 센터 보고서는 개별 사용자, 사용자 그룹 또는 모두에 대 한 통화 및 모임 데이터를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="96761-308">Help Desk Reports look at call and meeting data for individual users, groups of users, or everyone.</span></span> <span data-ttu-id="96761-309">이 보고서는 데이터 작성 및 EUII 통합 되어 네트워크 위치, 회의 세부 정보, 장치 또는 펌웨어에 따라 시스템 문제를 식별 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-309">Incorporating building and EUII data, these reports help identify possible system issues based on network location, conference details, devices, or firmware.</span></span>         |
|<span data-ttu-id="96761-310">클라이언트 버전 보고서</span><span class="sxs-lookup"><span data-stu-id="96761-310">Client Version Reports</span></span>     |<span data-ttu-id="96761-311">클라이언트 버전 요약: 각 클라이언트 앱 버전의 세션 및 사용자 수를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-311">Client Version Summary: View the Sessions and Users counts for each client app version</span></span><br><br><span data-ttu-id="96761-312">사용자별 클라이언트 버전: 각 클라이언트 앱 버전에 대 한 사용자 이름 보기</span><span class="sxs-lookup"><span data-stu-id="96761-312">Client Version by User: View user names for each client app version</span></span> <br><br><span data-ttu-id="96761-313">제품 및 클라이언트 종류에 대 한 미리 작성 된 필터는 특정 클라이언트에 버전을 집중 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-313">Pre-built filters for Product and Client Type help focus the versions to specific clients.</span></span>         |
|<span data-ttu-id="96761-314">끝점 보고서</span><span class="sxs-lookup"><span data-stu-id="96761-314">Endpoint Reports</span></span>     |<span data-ttu-id="96761-315">컴퓨터 끝점을 기준으로 통화 음질을 표시 합니다 (컴퓨터 제조업체 및 모델).</span><span class="sxs-lookup"><span data-stu-id="96761-315">Shows call quality by machine endpoints (computer make and model).</span></span> <span data-ttu-id="96761-316">이러한 보고서에는 데이터를 업로드 한 경우이에 대 한 빌드가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-316">These reports include building data, if you've uploaded it.</span></span>         |


## <a name="create-custom-detailed-reports"></a><span data-ttu-id="96761-317">사용자 지정 상세 보고서 만들기</span><span class="sxs-lookup"><span data-stu-id="96761-317">Create custom detailed reports</span></span>

<span data-ttu-id="96761-318">기본 CQD 보고서가 요구 사항에 맞지 않는 경우 다음 지침을 사용 하 여 사용자 지정 보고서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="96761-318">If the default CQD reports don't meet your needs, use these instructions to create a custom report.</span></span> <span data-ttu-id="96761-319">또는 (2020 년 1 월), 대신 [CQD 보고서 용 POWER BI를 사용 ](cqd-power-bi-query-templates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-319">Or (as of January 2020) [Use Power BI for CQD reports ](cqd-power-bi-query-templates.md)instead.</span></span>

<span data-ttu-id="96761-320">요약 보고서 화면에서 로그인 할 때 표시 되는 화면 위쪽에 있는 보고서의 풀 다운 목록에서 \( **Summary Reports** \) **자세한 보고서** 와 **새로 만들기**를 차례로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-320">From the pull-down list of reports at the top of the screen displayed at login \(the **Summary Reports** screen\) Select **Detailed Reports**  and then **New**.</span></span> <span data-ttu-id="96761-321">보고서에서 **편집** 을 클릭 하 여 쿼리 편집기를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-321">Click **Edit** in a report to see the Query Editor.</span></span> <span data-ttu-id="96761-322">각 보고서는 큐브로 쿼리를 통해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-322">Each report is backed by a query into the cube.</span></span> <span data-ttu-id="96761-323">보고서는 해당 쿼리에서 반환 된 데이터를 시각화 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="96761-323">A report is a visualization of the data returned by its query.</span></span> <span data-ttu-id="96761-324">쿼리 편집기를 사용 하 여 이러한 쿼리 및 보고서의 표시 옵션을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-324">The Query Editor helps you edit these queries and the display options of the report.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="96761-325">네트워크 범위를 사용 하 여 수퍼 네트 (단일 라우팅 접두사가 있는 여러 서브넷의 조합)를 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-325">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix).</span></span> <span data-ttu-id="96761-326">모든 새 건물 업로드가 겹치는 범위에 대해 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-326">All new building uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="96761-327">문서 파일을 이전에 업로드 한 경우에는 현재 파일을 다운로드 한 후 다시 업로드 하 여 겹치는 내용을 식별 하 고 문제를 해결 한 후 다시 업로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-327">If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again.</span></span> <span data-ttu-id="96761-328">이전에 업로드 한 파일의 겹치기로 인해 보고서의 건물에 대해 잘못 된 서브넷 매핑이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-328">Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports.</span></span> <span data-ttu-id="96761-329">특정 VPN 구현에서는 서브넷 정보가 정확 하 게 보고 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-329">Certain VPN implementations do not accurately report the subnet information.</span></span> <span data-ttu-id="96761-330">VPN 서브넷을 건물 파일에 추가할 때 서브넷에 대 한 하나의 항목이 아닌 별도의 32 비트 네트워크로 VPN 서브넷의 각 주소에 대해 개별 항목이 추가 되는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-330">It is recommended that when adding a VPN subnet to the building file, instead of one entry for the subnet, separate entries are added for each address in the VPN subnet as a separate 32-bit network.</span></span> <span data-ttu-id="96761-331">각 행은 동일한 빌드 메타 데이터를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-331">Each row can have the same building metadata.</span></span> <span data-ttu-id="96761-332">예를 들어 172.16.18.0/24에 대 한 한 행이 아닌 256 행이 172.16.18.0/32 및 172.16.18.255/32 (포함) 사이에 있는 각 주소에 대해 한 행이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-332">For example, instead of one row for 172.16.18.0/24, you should have 256 rows, with one row for each address between 172.16.18.0/32 and 172.16.18.255/32, inclusive.</span></span>
>
> <span data-ttu-id="96761-333">VPN 열은 선택 사항이 며 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="96761-333">The VPN column is optional and will default to 0.</span></span>  <span data-ttu-id="96761-334">VPN 열의 값이 1로 설정 되 면 해당 행이 표시 하는 서브넷이 서브넷 내의 모든 IP 주소와 일치 하도록 완전히 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-334">If the VPN column's value is set to 1, the subnet represented by that row will be fully expanded to match all IP addresses within the subnet.</span></span>  <span data-ttu-id="96761-335">이러한 서브넷을 완전히 확장 하면 데이터 작성이 포함 된 쿼리에 대 한 쿼리 시간에 부정적인 영향을 주므로이를 사용 하 여 VPN 서브넷에 대해서만이 방법을 사용해 주십시오.</span><span class="sxs-lookup"><span data-stu-id="96761-335">Please use this sparingly and only for VPN subnets since fully expanding these subnets will have a negative impact on query times for queries involving building data.</span></span>

<span data-ttu-id="96761-336">보고서의 막대형 차트 및 추세 선을 가리키면 세부 값이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-336">Point to bar charts and trend lines in the report to display detailed values.</span></span> <span data-ttu-id="96761-337">포커스가 있는 보고서에는 **보고서 트리** **편집**, **복제**, **삭제**, **다운로드**, 내보내기 등의 작업 메뉴가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-337">The report that has focus will show the action menu: **Edit**, **Clone**, **Delete**, **Download**, and **Export Report Tree**.</span></span>



## <a name="query-filters"></a><span data-ttu-id="96761-338">쿼리 필터</span><span class="sxs-lookup"><span data-stu-id="96761-338">Query filters</span></span>

<span data-ttu-id="96761-339">쿼리 필터는 CQD의 쿼리 편집기를 사용 하 여 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-339">Query filters are implemented by using the Query Editor in CQD.</span></span> <span data-ttu-id="96761-340">이러한 필터는 CQD에서 반환 되는 레코드 수를 줄여 보고서의 전체 크기와 쿼리 시간을 최소화 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-340">These filters are used to reduce the number of records returned by CQD, thus minimizing the report’s overall size and query times.</span></span> <span data-ttu-id="96761-341">이는 관리 되지 않는 네트워크를 필터링 하는 데 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-341">This is especially useful for filtering out unmanaged networks.</span></span> <span data-ttu-id="96761-342">다음 표에 나열 된 필터는 정규식 (RegEx)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-342">The filters listed in the following table use regular expressions (RegEx).</span></span>


| <span data-ttu-id="96761-343">Filter</span><span class="sxs-lookup"><span data-stu-id="96761-343">Filter</span></span>         | <span data-ttu-id="96761-344">설명</span><span class="sxs-lookup"><span data-stu-id="96761-344">Description</span></span>          | <span data-ttu-id="96761-345">CQD 쿼리 필터 예제</span><span class="sxs-lookup"><span data-stu-id="96761-345">CQD query filter example</span></span>      |
|----------------|----------------------|-------------------------------|
| <span data-ttu-id="96761-346">빈 값 없음</span><span class="sxs-lookup"><span data-stu-id="96761-346">No blank values</span></span>   | <span data-ttu-id="96761-347">일부 필터에는 빈 값을 필터링 하는 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-347">Some filters don’t have the option to filter for blank values.</span></span> <span data-ttu-id="96761-348">빈 값을 수동으로 필터링 하려면 필요에 따라 빈 식을 사용 하 고 필터를 같음 또는 같지 않음으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-348">To filter blank values manually, use the blank expression and set the filter to Equals or Not Equals, depending on your needs.</span></span>      | <span data-ttu-id="96761-349">두 번째 건물 이름 \<\> \^ \\ s\*\$</span><span class="sxs-lookup"><span data-stu-id="96761-349">Second Building Name \<\> \^\\s\*\$</span></span>                       |
| <span data-ttu-id="96761-350">공용 서브넷 제외</span><span class="sxs-lookup"><span data-stu-id="96761-350">Exclude common subnets</span></span> | <span data-ttu-id="96761-351">관리 되지 않는 네트워크를 구분 하기 위해 올바른 빌드 파일이 없는 경우 홈 네트워크는 보고서에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-351">Without a valid building file to separate managed from unmanaged networks, home networks will be included in the reports.</span></span> <span data-ttu-id="96761-352">이러한 홈 서브넷은 해당 컨트롤의 범위를 벗어나므로 보고서에서 빠르게 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-352">These home subnets are outside the scope of IT’s control and can be quickly excluded from a report.</span></span> <span data-ttu-id="96761-353">이 가이드에 정의 된 대로 일반적인 서브넷은 10.0.0.0, 192.168.1.0, 192.168.0.0입니다.</span><span class="sxs-lookup"><span data-stu-id="96761-353">Common subnets, as defined in this guide, are 10.0.0.0, 192.168.1.0 and 192.168.0.0.</span></span> | <span data-ttu-id="96761-354">두 번째 서브넷 \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="96761-354">Second Subnet \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0</span></span> |
| <span data-ttu-id="96761-355">안쪽만 보기</span><span class="sxs-lookup"><span data-stu-id="96761-355">View inside only</span></span>  | <span data-ttu-id="96761-356">관리 (내부) 또는 비관리형 (외부)에 대 한 보고서를 필터링 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-356">Used to filter a report for managed (inside) or unmanaged (outside).</span></span> <span data-ttu-id="96761-357">관리 되는 CQD 템플릿은이 필터를 사용 하 여 이미 미리 구성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-357">The managed CQD template is already preconfigured with these filters.</span></span>       | <span data-ttu-id="96761-358">두 번째 내부의 Corp = 인사이드</span><span class="sxs-lookup"><span data-stu-id="96761-358">Second Inside Corp = Inside</span></span>        |

## <a name="report-filters"></a><span data-ttu-id="96761-359">보고서 필터</span><span class="sxs-lookup"><span data-stu-id="96761-359">Report filters</span></span>

<span data-ttu-id="96761-360">CQD 보고서 필터를 사용 하 여 조사의 초점을 좁힐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-360">Use CQD report filters to narrow the focus of your investigations.</span></span> <span data-ttu-id="96761-361">보고서 필터는 쿼리 편집기에서 렌더링 된 보고서에 필터를 추가 하거나 보고서에서 바로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-361">Use report filters by adding a filter to the rendered report either in the Query Editor or directly in the report.</span></span> <span data-ttu-id="96761-362">다음 보고서 필터는 [Cqd 서식 파일](https://aka.ms/QERtemplates)에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-362">The following report filters are used throughout the [CQD templates](https://aka.ms/QERtemplates).</span></span>


| <span data-ttu-id="96761-363">Filter</span><span class="sxs-lookup"><span data-stu-id="96761-363">Filter</span></span>     | <span data-ttu-id="96761-364">설명</span><span class="sxs-lookup"><span data-stu-id="96761-364">Description</span></span>                            | <span data-ttu-id="96761-365">CQD 보고서 필터 예제</span><span class="sxs-lookup"><span data-stu-id="96761-365">CQD report filter example</span></span>         |
|------------|----------------------------------------|-----------------------------------|
| <span data-ttu-id="96761-366">달은</span><span class="sxs-lookup"><span data-stu-id="96761-366">Month</span></span>      | <span data-ttu-id="96761-367">먼저 1 년부터 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-367">Start with the year first, then month.</span></span> | <span data-ttu-id="96761-368">2017-10</span><span class="sxs-lookup"><span data-stu-id="96761-368">2017-10</span></span>                           |
| <span data-ttu-id="96761-369">가</span><span class="sxs-lookup"><span data-stu-id="96761-369">Alphabetic</span></span> | <span data-ttu-id="96761-370">모든 알파벳 문자에 대 한 필터입니다.</span><span class="sxs-lookup"><span data-stu-id="96761-370">Filters for any alphabetic characters.</span></span> | <span data-ttu-id="96761-371">[a-z]</span><span class="sxs-lookup"><span data-stu-id="96761-371">[a-z]</span></span>                             |
| <span data-ttu-id="96761-372">번호</span><span class="sxs-lookup"><span data-stu-id="96761-372">Numeric</span></span>    | <span data-ttu-id="96761-373">임의의 숫자 문자에 대 한 필터입니다.</span><span class="sxs-lookup"><span data-stu-id="96761-373">Filters for any numeric characters.</span></span>    | <span data-ttu-id="96761-374">[0-9]</span><span class="sxs-lookup"><span data-stu-id="96761-374">[0-9]</span></span>                             |
| <span data-ttu-id="96761-375">많은</span><span class="sxs-lookup"><span data-stu-id="96761-375">Percentage</span></span> | <span data-ttu-id="96761-376">백분율에 대 한 필터입니다.</span><span class="sxs-lookup"><span data-stu-id="96761-376">Filters for a percentage.</span></span>              | <span data-ttu-id="96761-377">([3-9] \\ ) \| . ([3-9]) \| ([1-9] [0-9])</span><span class="sxs-lookup"><span data-stu-id="96761-377">([3-9]\\.)\|([3-9])\|([1-9][0-9])</span></span> |


### <a name="drill-down-filters"></a><span data-ttu-id="96761-378">드릴 다운 필터</span><span class="sxs-lookup"><span data-stu-id="96761-378">Drill-down filters</span></span>

<span data-ttu-id="96761-379">CQD 보고서는 여러 드릴 다운 필터 기능을가지고 있으며,이는 통화 품질 조사에 초점을 좁히는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="96761-379">CQD reports feature several drill-down filters, which are powerful tools for narrowing the focus of your call-quality investigations.</span></span> <span data-ttu-id="96761-380">드릴 다운 필드를 선택 하면 보고서가 자동으로 해당 탭과 선택한 값에 대 한 필터를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-380">If you select a drill-down field, the report automatically opens the appropriate tab and filters on the selected value.</span></span> <span data-ttu-id="96761-381">해당 탭에 고유한 드릴 다운 필드가 있고 하나를 선택 하면 두 필터 집합을 적용 하 여 결과 데이터 집합을 점차적으로 축소 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-381">If that tab has its own drill-down fields and one is selected, both sets of filters are applied, progressively narrowing the resulting data set.</span></span>

![드릴 다운 보고서 흐름을 보여 주는 다이어그램](media/qerguide-image-drillthrureportflow.png)


#### <a name="adding-and-editing-drill-down-fields"></a><span data-ttu-id="96761-383">드릴 다운 필드 추가 및 편집</span><span class="sxs-lookup"><span data-stu-id="96761-383">Adding and editing drill-down fields</span></span>

<span data-ttu-id="96761-384">보고서를 편집할 때 쿼리 편집기를 사용 하 여 고유한 드릴 다운 필드를 지정 하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-384">When editing a report, you have the option to specify drill-down fields of your own using the Query Editor.</span></span>

<span data-ttu-id="96761-385">먼저 **을 클릭 하** 여 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-385">Start by clicking **…**</span></span> <span data-ttu-id="96761-386">편집 하려는 보고서의 경우 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-386">for the report you want to edit, then select **Edit**.</span></span>

![드릴 다운 필드 편집 스크린샷](media/qerguide-image-addeditdrilldownfields.png)

<span data-ttu-id="96761-388">쿼리 편집기의 왼쪽에 있는 목록에서 차원을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-388">Select a Dimension from the list on the left side of the Query Editor.</span></span> <span data-ttu-id="96761-389">그런 다음 **이동** 레이블 아래의 드롭다운을 클릭 하 고 해당 차원을 드릴스루할 탭 및 확장 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-389">Then click on the dropdown below the **Navigate To** label and select the tab and expander group that you want that Dimension to drill through to.</span></span> <span data-ttu-id="96761-390">참고: 현재 드릴 다운 기능은 다른 탭으로 이동할 때만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-390">Note: Presently, drill-down functionality only works by navigating to different tabs.</span></span> <span data-ttu-id="96761-391">특정 확장기로 드릴 다운에 대 한 지원은 나중에 추가 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="96761-391">Support for drilling through to a specific expander will be added later.</span></span> <span data-ttu-id="96761-392">마지막으로, **닫기를** 클릭 하 여 차원에 대 한 변경 내용을 저장 한 다음 **저장** 을 클릭 하 여 쿼리 편집기를 저장 하 고 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-392">Finally, click **Close** to save your changes to the Dimension, then click **Save** to save and close the Query Editor.</span></span>

![쿼리 편집기에서 차원을 선택 하는 스크린샷](media/qerguide-image-selectquerydimension.png)

### <a name="multi-select-filters"></a><span data-ttu-id="96761-394">다중 선택 필터</span><span class="sxs-lookup"><span data-stu-id="96761-394">Multi-select filters</span></span>

<span data-ttu-id="96761-395">' 드릴 다운 ' 기능 외에도 CQD는 여러 값 또는 필터를 갖는 필터 지정을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-395">In addition to drill-down functionality, CQD also supports specifying Filters with multiple values (OR filters).</span></span>

<span data-ttu-id="96761-396">여러 필터 값을 선택 하려면 먼저 보고서에 새 필터를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-396">In order to select multiple filter values, begin by adding a new filter to the report.</span></span> <span data-ttu-id="96761-397">**+** **필터** 레이블 옆을 클릭 하 고 사용 하려는 차원의 이름을 입력 한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-397">Click **+** beside the **Filters** label, enter the name of the Dimension you want to use, and click **Add**.</span></span>

![다중 선택 필터 추가 스크린샷](media/qerguide-image-addmultiselectfilter.png)

<span data-ttu-id="96761-399">그런 다음 **검색** (새 필터 옆에 있는 돋보기 아이콘)을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-399">Then, click **Search** (a magnifying glass icon next to the new filter).</span></span> <span data-ttu-id="96761-400">텍스트 필드와 **모두 선택** 및 **반전**을 비롯 한 여러 옵션이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-400">You'll see a text field, and a number of options, including **Select All** and **Invert**.</span></span> <span data-ttu-id="96761-401">값을 입력 하 고 해당 필드 옆에 있는 **검색** 을 클릭 하 여 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-401">Enter a value,  and click **Search** next to that field to search.</span></span> <span data-ttu-id="96761-402">또는 텍스트 필드를 비워 두고 **검색** 을 클릭 하 여 첫 번째 100 옵션을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-402">Alternatively, leave the text field empty and click **Search** to view up to the first 100 options.</span></span>

```PowerShell
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

<span data-ttu-id="96761-403">예</span><span class="sxs-lookup"><span data-stu-id="96761-403">Example:</span></span>  

![쿼리 필터 추가 스크린샷](media/qerguide-image-addfilter.png)

### <a name="dashboard-level-filters"></a><span data-ttu-id="96761-405">대시보드 수준 필터</span><span class="sxs-lookup"><span data-stu-id="96761-405">Dashboard level filters</span></span>
<span data-ttu-id="96761-406">특정 CQD 보고서에는 대시보드 수준의 필터가 추가 되어 공통 매개 변수에 따라 쉽게 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-406">Certain CQD reports have dashboard-level filters added to them, making it easy to filter by common parameters.</span></span> <span data-ttu-id="96761-407">이러한 필터는 일반 보고서 탭 외부와 제품 필터 바로 아래에 표시 되며 대시보드의 모든 필터에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-407">These filters appear outside the regular report tabs and directly beneath the Product filter, and they apply to all filters in the Dashboard.</span></span>

![대시보드 필터 스크린샷](media/qerguide-image-dashboardfilters.png)
```PowerShell
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

### <a name="url-filters"></a><span data-ttu-id="96761-409">URL 필터</span><span class="sxs-lookup"><span data-stu-id="96761-409">URL filters</span></span>

<span data-ttu-id="96761-410">CQD는 URL에 필터를 추가 하는 것을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-410">CQD supports adding filters to the URL.</span></span> <span data-ttu-id="96761-411">이렇게 하면 CQD 쿼리를 쉽게 공유 하거나 책갈피로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-411">This makes it easy to share or bookmark a CQD query.</span></span> <span data-ttu-id="96761-412">URL에서 추세 월, 테 넌 트 ID 또는 언어와 같은 매개 변수를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-412">You can define parameters in the URL, such as Trending Month, tenant ID, or language.</span></span> <span data-ttu-id="96761-413">URL에 제품 또는 대시보드 수준 필터를 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-413">You can also add Product or Dashboard level filters to the URL.</span></span>
<span data-ttu-id="96761-414">페더레이션된 끝점이 보고서에 영향을 줄 수 있는 관리 되는 건물이 나 네트워크를 수정 하는 경우 CQD 보고서의 페더레이션된 데이터를 제외 하는 것이 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-414">Excluding federated data from CQD reports is useful when you're remediating managed buildings or networks where federated endpoints might influence your reports.</span></span>

<span data-ttu-id="96761-415">필터를 추가 하려면 URL의 끝에 다음을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-415">To add a filter, append the following to the end of the URL:</span></span>

```
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

<span data-ttu-id="96761-416">예</span><span class="sxs-lookup"><span data-stu-id="96761-416">Example:</span></span>  

```https://cqd.teams.microsoft.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]```

<span data-ttu-id="96761-417">URL에 대시보드 수준 필터를 추가 하려면 해당 필터가 CQD에 제품 또는 대시보드 수준 필터로 존재 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-417">To add a Dashboard-level filter to a URL, that filter must exist in CQD as either a Product or Dashboard level filter.</span></span> <span data-ttu-id="96761-418">다음 필터를 추세 월 및 URL 매개 변수 앞의 URL에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-418">Add these filters to the URL after the Trending Month and before the URL parameters:</span></span>

```filter/DATA_MODEL_NAME|VALUE```

<span data-ttu-id="96761-419">예를 들어 Microsoft 팀의 제품 필터 값을 적용 하려면 다음을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-419">For example, to apply a Product filter value of Microsoft Teams, you'd add the following:</span></span>

```filter/[AllStreams].[Is%20Teams]|[True]```

<span data-ttu-id="96761-420">전체 URL이 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-420">Your entire URL would look something like this:</span></span>

```https://cqd.teams.microsoft.com/spd/#/Dashboard/2624085/2018-9/filter/[AllStreams].[Is%20Teams]|[True]```

<span data-ttu-id="96761-421">다중 선택 값을 사용 하 여 URL 필터를 적용 하려면 각 값을 파이프 (|) 문자로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-421">To apply URL filters with multi-select values, separate each value with a pipe ( | ) character.</span></span> <span data-ttu-id="96761-422">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-422">For example:</span></span>

```filter/[AllStreams].[Media%20Type]|[Video]|[Audio]|[VBSS]```

<span data-ttu-id="96761-423">잘못 된 이름 또는 값을 지정 하면 URL 필터가 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-423">If you specify an invalid name or value, the URL filter won't be applied.</span></span>


<span data-ttu-id="96761-424">URL 필터를 사용 하 여 특정 차원에 대 한 모든 보고서를 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-424">You can use a URL filter to filter every report for a specific dimension.</span></span> <span data-ttu-id="96761-425">가장 일반적인 URL 필터는 페더레이션 참가자 원격 분석을 제외 하도록 보고서를 필터링 하거나, 팀 또는 비즈니스용 Skype Online 에서만 포커스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-425">The most common URL filters are used to filter reports to exclude federated participant telemetry, or focus on only Teams or Skype for Business Online.</span></span> <span data-ttu-id="96761-426">페더레이션된 끝점이 보고서에 영향을 줄 수 있는 관리 되는 건물이 나 네트워크를 수정 하는 경우 CQD 보고서의 페더레이션된 데이터를 제외 하는 것이 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-426">Excluding federated data from CQD reports is useful when you're remediating managed buildings or networks where federated endpoints might influence your reports.</span></span>

| <span data-ttu-id="96761-427">Filter</span><span class="sxs-lookup"><span data-stu-id="96761-427">Filter</span></span>         | <span data-ttu-id="96761-428">설명</span><span class="sxs-lookup"><span data-stu-id="96761-428">Description</span></span>          | <span data-ttu-id="96761-429">CQD 쿼리 필터 예제</span><span class="sxs-lookup"><span data-stu-id="96761-429">CQD query filter example</span></span>      |
|----------------|----------------------|-------------------------------|
| <span data-ttu-id="96761-430">빈 값 없음</span><span class="sxs-lookup"><span data-stu-id="96761-430">No blank values</span></span>   | <span data-ttu-id="96761-431">일부 필터에는 빈 값을 필터링 하는 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-431">Some filters don't have the option to filter for blank values.</span></span> <span data-ttu-id="96761-432">빈 값을 수동으로 필터링 하려면 필요에 따라 빈 식을 사용 하 고 필터를 같음 또는 같지 않음으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-432">To filter blank values manually, use the blank expression and set the filter to Equals or Not Equals, depending on your needs.</span></span>      | <span data-ttu-id="96761-433">두 번째 건물 이름 \<\> \^ \\ s\*\$</span><span class="sxs-lookup"><span data-stu-id="96761-433">Second Building Name \<\> \^\\s\*\$</span></span>                       |
| <span data-ttu-id="96761-434">공용 서브넷 제외</span><span class="sxs-lookup"><span data-stu-id="96761-434">Exclude common subnets</span></span> | <span data-ttu-id="96761-435">관리 되지 않는 네트워크를 구분 하기 위해 올바른 빌드 파일이 없는 경우 홈 네트워크는 보고서에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-435">Without a valid building file to separate managed from unmanaged networks, home networks will be included in the reports.</span></span> <span data-ttu-id="96761-436">이러한 홈 서브넷은 해당 컨트롤의 범위를 벗어나므로 보고서에서 빠르게 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-436">These home subnets are outside the scope of IT's control and can be quickly excluded from a report.</span></span> <span data-ttu-id="96761-437">이 문서에 정의 된 대로 공용 서브넷은 10.0.0.0, 192.168.1.0, 192.168.0.0입니다.</span><span class="sxs-lookup"><span data-stu-id="96761-437">Common subnets, as defined in this article, are 10.0.0.0, 192.168.1.0 and 192.168.0.0.</span></span> | <span data-ttu-id="96761-438">두 번째 서브넷 \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="96761-438">Second Subnet \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0</span></span> |
| <span data-ttu-id="96761-439">안쪽만 보기</span><span class="sxs-lookup"><span data-stu-id="96761-439">View inside only</span></span>  | <span data-ttu-id="96761-440">관리 (내부) 또는 비관리형 (외부)에 대 한 보고서를 필터링 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-440">Used to filter a report for managed (inside) or unmanaged (outside).</span></span> <span data-ttu-id="96761-441">관리 되는 CQD 템플릿은이 필터를 사용 하 여 이미 미리 구성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-441">The managed CQD template is already preconfigured with these filters.</span></span>       | <span data-ttu-id="96761-442">두 번째 내부의 Corp = 인사이드</span><span class="sxs-lookup"><span data-stu-id="96761-442">Second Inside Corp = Inside</span></span>        |


#### <a name="how-to-find-your-tenant-id"></a><span data-ttu-id="96761-443">테 넌 트 ID를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="96761-443">How to find your tenant ID</span></span>

<span data-ttu-id="96761-444">CQD의 테 넌 트 ID는 Azure의 디렉터리 ID에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-444">The tenant ID in CQD corresponds to the Directory ID in Azure.</span></span> <span data-ttu-id="96761-445">디렉터리 ID를 모르는 경우 Azure 포털에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-445">If you don't know your Directory ID, you can find it in the Azure portal:</span></span>

1.  <span data-ttu-id="96761-446">Microsoft Azure 포털에 로그인 합니다.<https://portal.azure.com></span><span class="sxs-lookup"><span data-stu-id="96761-446">Sign in to the Microsoft Azure portal: <https://portal.azure.com></span></span>

2.  <span data-ttu-id="96761-447">**Azure Active Directory**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-447">Select **Azure Active Directory**.</span></span>

3.  <span data-ttu-id="96761-448">**관리**에서 **속성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-448">Under **Manage**, select **Properties**.</span></span> <span data-ttu-id="96761-449">테 넌 트 ID는 **디렉터리 ID** 상자에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-449">Your tenant ID is in the **Directory ID** box.</span></span>

<span data-ttu-id="96761-450">PowerShell을 사용 하 여 테 넌 트 ID를 찾을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-450">You can also find your tenant ID by using PowerShell:</span></span> 
  ```
  Login-AzureRmAccount
  ```



## <a name="comparing-teams-and-skype-for-business-cqd-data"></a><span data-ttu-id="96761-451">팀과 비즈니스용 Skype CQD 데이터 비교</span><span class="sxs-lookup"><span data-stu-id="96761-451">Comparing Teams and Skype for Business CQD data</span></span>

<span data-ttu-id="96761-452">최신 CQD (cqd.teams.microsoft.com) 내에도 팀과 비즈니스용 Skype 간의 데이터 차이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-452">Even within the latest CQD (cqd.teams.microsoft.com), you'll see differences in data between Teams and Skype for Business.</span></span> <span data-ttu-id="96761-453">몇 가지 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-453">Some reasons:</span></span>
- <span data-ttu-id="96761-454">성능 및 안정성을 보장 하는 메커니즘의 차이점</span><span class="sxs-lookup"><span data-stu-id="96761-454">Differences in the mechanisms for ensuring performance and reliability</span></span>
  - <span data-ttu-id="96761-455">팀에 자동 다시 연결 및 빠른 로밍이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-455">Teams has auto-reconnect and fast roaming.</span></span> <span data-ttu-id="96761-456">비즈니스용 Skype는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-456">Skype for Business doesn't.</span></span>
  - <span data-ttu-id="96761-457">팀은 동적 대역폭 관리를가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-457">Teams has dynamic bandwidth management.</span></span> <span data-ttu-id="96761-458">비즈니스용 Skype는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-458">Skype for Business doesn't.</span></span>
- <span data-ttu-id="96761-459">팀과 비즈니스용 Skype 간의 [IP 주소 범위](Office-365-URLs-IP-address-ranges.md) 차이</span><span class="sxs-lookup"><span data-stu-id="96761-459">Differences in [IP address ranges](Office-365-URLs-IP-address-ranges.md) between Teams and Skype for Business.</span></span> <span data-ttu-id="96761-460">팀 IP 범위는 더 최신 버전 이므로 방화벽에서 연결 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-460">The Teams IP ranges are newer, which could cause connectivity problems at the firewall.</span></span>

## <a name="open-cqd-from-the-skype-for-business-legacy-portal"></a><span data-ttu-id="96761-461">비즈니스용 Skype 레거시 포털에서 CQD 열기</span><span class="sxs-lookup"><span data-stu-id="96761-461">Open CQD from the Skype for Business legacy portal</span></span>

<span data-ttu-id="96761-462">![비즈니스용 skype ](media/sfb-logo-30x30.png) **레거시 포털을 사용 하** 는 비즈니스용 skype 로고 아이콘</span><span class="sxs-lookup"><span data-stu-id="96761-462">![An icon of the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business legacy portal**</span></span>

1. <span data-ttu-id="96761-463">관리자 계정을 사용 하 여 Office 365 조직에 로그인 한 다음 관리 타일을 선택 **하 여 관리** 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="96761-463">Sign in to your Office 365 organization using an admin account, and then select the **Admin** tile to open the Admin center.</span></span>
2. <span data-ttu-id="96761-464">왼쪽 창의 **관리 센터**에서 **Microsoft 팀** 을 선택 하 여 팀 관리 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="96761-464">In the left pane, under **Admin centers**, select **Microsoft Teams** to open the Teams admin center.</span></span>
3. <span data-ttu-id="96761-465">팀 관리 센터의 왼쪽 창에서 **레거시 포털** 을 선택 하 고 **도구**를 선택한 다음 비즈니스용 **Skype Online 통화 품질 대시보드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-465">In the Teams admin center, select **Legacy Portal** in the left pane, select **Tools**, and then select **Skype for Business Online Call Quality Dashboard**.</span></span>

     ![스크린샷: 통화 품질 대시보드를 선택 합니다.](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)

4. <span data-ttu-id="96761-467">열리는 페이지에서 전역 관리자 계정으로 로그인 한 다음 메시지가 표시 되 면 계정에 대 한 자격 증명을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-467">On the page that opens, sign in with your Global Administrator account, and then provide the credentials for the account when prompted.</span></span>

<span data-ttu-id="96761-468">처음 로그인 하면 CQD가 데이터 수집과 처리를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="96761-468">After the first time you sign in, CQD will begin collecting and processing data.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="96761-469">2019 년 12 월 이전에는 레거시 포털에서 최신 CQD (cqd.teams.microsoft.com)에 대 한 링크를 제공 하지만이 경우에도 cqd.lync.com (c)의 오래 된 버전에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-469">As of December 2019, you can still access the older version of CQD (cqd.lync.com), although the legacy portal gives you a link to the latest CQD (cqd.teams.microsoft.com).</span></span> <span data-ttu-id="96761-470">결과적으로 CQD의 이전 버전이 서비스 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-470">Eventually, the older version of CQD will be decommissioned.</span></span> <span data-ttu-id="96761-471">7 월 1 2020 일 (으)로 이전 버전의 CQD는 새 CQD의 데이터에 액세스 https://CQD.teams.microsoft.com) 하며, 더 이상 빌드 및 보고서 데이터를 내보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96761-471">As of July 1, 2020, the older version of CQD accesses data from the new CQD (https://CQD.teams.microsoft.com), and you can no longer export building and report data.</span></span> <span data-ttu-id="96761-472">2020 후반에는 이전 CQD를 해제 하 고 더 이상 액세스할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96761-472">Sometime in late 2020, we'll turn off the old CQD and you'll no longer be able to access it.</span></span>


## <a name="related-topics"></a><span data-ttu-id="96761-473">관련 항목</span><span class="sxs-lookup"><span data-stu-id="96761-473">Related topics</span></span>

[<span data-ttu-id="96761-474">팀의 통화 품질 개선 및 모니터링</span><span class="sxs-lookup"><span data-stu-id="96761-474">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="96761-475">CQD 란 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="96761-475">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="96761-476">CQD (통화 품질 대시보드) 설정</span><span class="sxs-lookup"><span data-stu-id="96761-476">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="96761-477">테 넌 트 업로드 및 데이터 빌드</span><span class="sxs-lookup"><span data-stu-id="96761-477">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="96761-478">CQD를 사용 하 여 통화 및 모임 품질 관리</span><span class="sxs-lookup"><span data-stu-id="96761-478">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="96761-479">CQD에서 사용할 수 있는 차원과 측정값</span><span class="sxs-lookup"><span data-stu-id="96761-479">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="96761-480">CQD의 스트림 분류</span><span class="sxs-lookup"><span data-stu-id="96761-480">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="96761-481">Power BI를 사용 하 여 CQD 데이터 분석</span><span class="sxs-lookup"><span data-stu-id="96761-481">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)
