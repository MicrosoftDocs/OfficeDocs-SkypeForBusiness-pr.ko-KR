---
title: CQD(통화 품질 대시보드)의 데이터 및 보고서
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
description: Microsoft 통화 품질 대시보드(CQD)에서 사용할 수 있는 데이터 및 보고서에 대해 자세히 알아보습니다.
ms.openlocfilehash: 47fce642bf90b1be9285a11cf19a5e6421aa262b
ms.sourcegitcommit: 5a738cbb96f09edd8c3779f9385bc9ed126e3001
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2021
ms.locfileid: "52212201"
---
# <a name="data-and-reports-in-call-quality-dashboard-cqd"></a><span data-ttu-id="283d1-103">CQD(통화 품질 대시보드)의 데이터 및 보고서</span><span class="sxs-lookup"><span data-stu-id="283d1-103">Data and reports in Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="283d1-104">CQD(Microsoft Call Quality 대시보드)는 거의 실시간(NRT) 데이터 피드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-104">Microsoft Call Quality Dashboard (CQD) uses a near-real-time (NRT) data feed.</span></span> <span data-ttu-id="283d1-105">통화 레코드는 통화가 종료된 후 30분 이내에 CQD에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-105">Call records are available in CQD within 30 minutes of the end of a call.</span></span> <span data-ttu-id="283d1-106">NRT 파이프라인의 호출 레코드는 데이터 집합에서 제거되기 몇 개월 동안만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-106">Call records from the NRT pipeline are only available for a few months before they are removed from the data set.</span></span> 


## <a name="many-ways-to-access-cqd-data"></a><span data-ttu-id="283d1-107">CQD 데이터에 액세스하는 여러 가지 방법</span><span class="sxs-lookup"><span data-stu-id="283d1-107">Many ways to access CQD data</span></span>

<span data-ttu-id="283d1-108">여러 다른 방법으로 CQD 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-108">You can access CQD data by several different avenues.</span></span> <span data-ttu-id="283d1-109">요구 사항을 가장 잘 충족하는 것을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="283d1-109">Pick the one that best meets your needs:</span></span>

|  |  |
|---------|---------|
|<span data-ttu-id="283d1-110">Teams 관리 [센터() https://admin.teams.microsoft.com) ](https://admin.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="283d1-110">Teams admin center [(https://admin.teams.microsoft.com)](https://admin.teams.microsoft.com)</span></span>    | <span data-ttu-id="283d1-111">CQD 데이터는 읽기  쉬운 Teams 가장 일반적인 데이터를 보여 주며 관리 센터의 사용자 페이지에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-111">CQD data is included on the **Users** page in the Teams admin center, showing the most common data you need in an easy-to-read format.</span></span> <span data-ttu-id="283d1-112">사용자 에서 찾은 CQD 데이터를 사용자 지정할 수 **없습니다.**</span><span class="sxs-lookup"><span data-stu-id="283d1-112">You can't customize CQD data that you find under **Users**.</span></span>  |
|<span data-ttu-id="283d1-113">CQD 포털 [( https://cqd.teams.microsoft.com) ](https://cqd.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="283d1-113">CQD portal [(https://cqd.teams.microsoft.com)](https://cqd.teams.microsoft.com)</span></span>     | <span data-ttu-id="283d1-114">드릴스루 필터링을 통해 대부분의 요구 사항을 충족하는 강력한 요약 및 세부 보고서.</span><span class="sxs-lookup"><span data-stu-id="283d1-114">Robust summary and detailed reports that meet most needs, with drill-through filtering.</span></span> <span data-ttu-id="283d1-115">CQD 포털에서 보고서를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-115">You can also customize reports in the CQD portal.</span></span> <br><br><span data-ttu-id="283d1-116">[CQD 포털에서](#import-the-cqd-report-templates) 데이터를 분석하는 데 도움이 되는 두 개의 CQD 보고서 템플릿을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-116">Get two [CQD report templates](#import-the-cqd-report-templates) to help you analyze data in the CQD portal.</span></span>       |
|<span data-ttu-id="283d1-117">Power BI</span><span class="sxs-lookup"><span data-stu-id="283d1-117">Power BI</span></span>     | <span data-ttu-id="283d1-118">직접 쿼리를 사용하여 사용자 지정 가능한 템플릿을 사용하여 Power BI CQD 데이터를 Power BI [있습니다.](CQD-Power-BI-query-templates.md)</span><span class="sxs-lookup"><span data-stu-id="283d1-118">Use direct queries to view your CQD data in Power BI using [customizable Power BI templates](CQD-Power-BI-query-templates.md).</span></span> <span data-ttu-id="283d1-119">[CQD에 Power BI 쿼리 템플릿을 다운로드합니다.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="283d1-119">[Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span><br><br><span data-ttu-id="283d1-120">REST API를 사용하여 데이터를 통해 [CQD](/skypeforbusiness/management-tools/call-quality-dashboard/data-api) 데이터에 액세스할 Power BI.</span><span class="sxs-lookup"><span data-stu-id="283d1-120">You can also [use the REST API to access CQD data](/skypeforbusiness/management-tools/call-quality-dashboard/data-api) through Power BI.</span></span> <span data-ttu-id="283d1-121">오프라인으로 작업할 수 있도록 CQD 데이터를 다운로드하려는 경우 이 방법을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-121">Use this method if you want to download your CQD data so you can work on it offline.</span></span> <span data-ttu-id="283d1-122">이 메서드를 사용하면 성능이 향상됩니다. 특히 온라인에 있는 경우 Power BI 큰 데이터 집합에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-122">The benefit of using this method is better performance, especially useful for large data sets that bog down in Power BI when you're online.</span></span>       |
|<span data-ttu-id="283d1-123">그래프 API</span><span class="sxs-lookup"><span data-stu-id="283d1-123">Graph API</span></span>     | <span data-ttu-id="283d1-124">를 사용하여 통화 품질 [데이터에 직접 Graph 합니다.](/graph/api/resources/callrecords-api-overview?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="283d1-124">Access call quality data yourself using the [Graph API](/graph/api/resources/callrecords-api-overview?view=graph-rest-beta).</span></span> <span data-ttu-id="283d1-125">가장 복잡한 방법이지만 통화 품질 데이터를 분석하는 데 가장 많은 제어 및 유연성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-125">This is the most complex method, but it gives you the most control and flexibility in analyzing your call quality data.</span></span> <span data-ttu-id="283d1-126">예를 들어 조직의 다른 데이터와 조인해야 하는 경우 데이터 모델을 만들고 통화 품질 데이터를 통합하는 데 Graph API를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-126">For example, if you need to join it with other data for your organization, you can use the Graph API to create a data model and incorporate call quality data.</span></span>        |

## <a name="import-the-cqd-report-templates"></a><span data-ttu-id="283d1-127">CQD 보고서 템플릿 가져오기</span><span class="sxs-lookup"><span data-stu-id="283d1-127">Import the CQD report templates</span></span>

<span data-ttu-id="283d1-128">CQD를 사용하여 빠르게 속도를 향상할 수 있도록 큐레이터된 두 개의 [CQD](https://aka.ms/qertemplates) 보고서 템플릿(모든 네트워크 및 관리 네트워크)을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-128">Download [two curated CQD report templates](https://aka.ms/qertemplates) (All Networks and Managed Networks) to help you get up to speed quickly with CQD.</span></span> <span data-ttu-id="283d1-129">건물 데이터 파일로 작업하도록 최적화된 모든 네트워크 템플릿은 다음 섹션에서 설명한 바와 같이 건물 정보를 CQD로 수집하고 업로드하는 동안 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-129">The All Networks template, though optimized to work with a building data file, can be used while you work toward collecting and uploading building information into CQD, as described in the next section.</span></span>

<span data-ttu-id="283d1-130">**템플릿을 가져오기(). CQDX)를 CQD로**</span><span class="sxs-lookup"><span data-stu-id="283d1-130">**To import the templates (.CQDX) into CQD**</span></span>

1. <span data-ttu-id="283d1-131">CQD에서 **페이지** 맨 위에 있는 메뉴에서 세부 보고서를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-131">In CQD, select **Detailed Reports** from the menu at the top of the page.</span></span>

2. <span data-ttu-id="283d1-132">왼쪽 패널에서 가져오기 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="283d1-132">In the left panel, select **Import**.</span></span> <span data-ttu-id="283d1-133">첫 번째 CQDX 템플릿으로 찾아 **열기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="283d1-133">Browse to the first CQDX template and select **Open**.</span></span>

3. <span data-ttu-id="283d1-134">템플릿이 업로드된 후 팝업 창에 "보고서 가져오기 성공"이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-134">After the template is uploaded, a pop-up window will display the message "Report import was successful."</span></span> 

4. <span data-ttu-id="283d1-135">두 번째 CQD 템플릿에 대해 2단계와 3단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-135">Repeat steps 2 and 3 for the second CQD template.</span></span>

   > [!NOTE]
   > <span data-ttu-id="283d1-136">각 사용자는 CQD 템플릿을 CQD 인스턴스로 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-136">Each user must import the CQD templates into their CQD instance.</span></span> 



## <a name="euii-data"></a><span data-ttu-id="283d1-137">EUII 데이터</span><span class="sxs-lookup"><span data-stu-id="283d1-137">EUII data</span></span>

<span data-ttu-id="283d1-138">규정 준수 이유로 최종 사용자 식별 정보(EUII) 데이터(개인 식별 정보 또는 PII라고도 하는)는 28일 동안만 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-138">For compliance reasons, end-user identifiable information (EUII) data (also known as personally-identifiable information or PII) is only kept for 28 days.</span></span> <span data-ttu-id="283d1-139">NRT 데이터가 28일 마크를 교차하면 EUII를 포함하는 필드가 지워지기 때문에 EUII가 없는 NRT 데이터가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-139">As NRT data crosses the 28-day mark, fields that contain EUII are cleared, resulting in EUII-free NRT data.</span></span> <span data-ttu-id="283d1-140">EUII 데이터가 포함된 필드는:</span><span class="sxs-lookup"><span data-stu-id="283d1-140">Fields that contain EUII data are:</span></span>

- <span data-ttu-id="283d1-141">전체 IP 주소</span><span class="sxs-lookup"><span data-stu-id="283d1-141">Full IP address</span></span>
- <span data-ttu-id="283d1-142">MAC(미디어 액세스 제어) 주소</span><span class="sxs-lookup"><span data-stu-id="283d1-142">Media Access Control (MAC) Address</span></span>
- <span data-ttu-id="283d1-143">기본 서비스 집합 식별자(BSSID)</span><span class="sxs-lookup"><span data-stu-id="283d1-143">Basic Service Set identifier (BSSID)</span></span>
- <span data-ttu-id="283d1-144">SIP(세션 시작 프로토콜) URI(비즈니스용 Skype만 해당)</span><span class="sxs-lookup"><span data-stu-id="283d1-144">Session Initiation Protocol (SIP) URI (Skype for Business only)</span></span>
- <span data-ttu-id="283d1-145">사용자 주체 이름(UPN)</span><span class="sxs-lookup"><span data-stu-id="283d1-145">User Principal Name (UPN)</span></span>
- <span data-ttu-id="283d1-146">컴퓨터 엔드포인트 이름</span><span class="sxs-lookup"><span data-stu-id="283d1-146">Machine Endpoint Name</span></span>
- <span data-ttu-id="283d1-147">사용자 Verbatim 피드백</span><span class="sxs-lookup"><span data-stu-id="283d1-147">User Verbatim Feedback</span></span>
- <span data-ttu-id="283d1-148">개체 ID(엔드포인트 사용자의 Active Directory 개체 ID)</span><span class="sxs-lookup"><span data-stu-id="283d1-148">Object ID (the Active Directory object ID of the endpoint's user)</span></span>

### <a name="admin-roles-with-and-without-euii-access"></a><span data-ttu-id="283d1-149">EUII 액세스 권한이 없는 관리자 역할</span><span class="sxs-lookup"><span data-stu-id="283d1-149">Admin roles with and without EUII access</span></span>

<span data-ttu-id="283d1-150">이러한 [RBAC](/azure/role-based-access-control/overview) 역할 **DO에는** EUII 액세스 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-150">These [RBAC](/azure/role-based-access-control/overview) roles **DO** have EUII access:</span></span>
- <span data-ttu-id="283d1-151">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="283d1-151">Global Admin</span></span>
- <span data-ttu-id="283d1-152">Teams 서비스 관리자</span><span class="sxs-lookup"><span data-stu-id="283d1-152">Teams Service Admin</span></span>
- <span data-ttu-id="283d1-153">Teams 통신 관리자</span><span class="sxs-lookup"><span data-stu-id="283d1-153">Teams Communications Admin</span></span>
- <span data-ttu-id="283d1-154">Teams 커뮤니케이션 지원 엔지니어</span><span class="sxs-lookup"><span data-stu-id="283d1-154">Teams Communications Support Engineer</span></span>
- <span data-ttu-id="283d1-155">전역 읽기</span><span class="sxs-lookup"><span data-stu-id="283d1-155">Global Reader</span></span>
- <span data-ttu-id="283d1-156">비즈니스용 Skype 관리자</span><span class="sxs-lookup"><span data-stu-id="283d1-156">Skype for Business Admin</span></span>

<span data-ttu-id="283d1-157">이러한 RBAC  역할에는 EUII 액세스 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-157">These RBAC roles **DON'T** have EUII access:</span></span>
- <span data-ttu-id="283d1-158">보고서 읽기</span><span class="sxs-lookup"><span data-stu-id="283d1-158">Reports Reader</span></span>
- <span data-ttu-id="283d1-159">Teams 통신 지원 전문가</span><span class="sxs-lookup"><span data-stu-id="283d1-159">Teams Communications Support Specialist</span></span>


## <a name="date-controls"></a><span data-ttu-id="283d1-160">날짜 컨트롤</span><span class="sxs-lookup"><span data-stu-id="283d1-160">Date controls</span></span>

<span data-ttu-id="283d1-161">CQD는 다음과 같은 롤링 추세 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-161">CQD supports the following Rolling Trend types:</span></span>

- <span data-ttu-id="283d1-162">5일</span><span class="sxs-lookup"><span data-stu-id="283d1-162">5-day</span></span>
- <span data-ttu-id="283d1-163">7일</span><span class="sxs-lookup"><span data-stu-id="283d1-163">7-day</span></span>
- <span data-ttu-id="283d1-164">30일</span><span class="sxs-lookup"><span data-stu-id="283d1-164">30-day</span></span>
- <span data-ttu-id="283d1-165">60일</span><span class="sxs-lookup"><span data-stu-id="283d1-165">60-day</span></span>
- <span data-ttu-id="283d1-166">90일</span><span class="sxs-lookup"><span data-stu-id="283d1-166">90-day</span></span>

<span data-ttu-id="283d1-167">URL 날짜 매개 변수는 Day 필드를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-167">The URL Date parameter accepts a Day field.</span></span> <span data-ttu-id="283d1-168">롤링 데이 보고서는 YYYY-MM-DD 형식으로 지정된 날짜를 추세의 마지막 날로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-168">Rolling-day reports use dates specified in the YYYY-MM-DD format as the last day of the trend.</span></span> <span data-ttu-id="283d1-169">URL 날짜 매개 변수 "00"은 "today"를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-169">The URL Date parameter “00”  indicates “today”.</span></span>

|<span data-ttu-id="283d1-170">URL</span><span class="sxs-lookup"><span data-stu-id="283d1-170">URL</span></span>| <span data-ttu-id="283d1-171">롤링 데이의 종료 추세</span><span class="sxs-lookup"><span data-stu-id="283d1-171">End date of Rolling Day Trend</span></span>|
|:---|:---|
|<span data-ttu-id="283d1-172"><span><cqdv3>https:// /spd/#/Dashboard/ <reportid> /2019-02/</span></span><span class="sxs-lookup"><span data-stu-id="283d1-172"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/2019-02/</span></span></span>   |<span data-ttu-id="283d1-173">2019년 2월 현재의 날</span><span class="sxs-lookup"><span data-stu-id="283d1-173">Current Day of Feb 2019</span></span>|
|<span data-ttu-id="283d1-174"><span><cqdv3>https:// /spd/#/Dashboard/ <reportid> /2019-02-15/</span></span><span class="sxs-lookup"><span data-stu-id="283d1-174"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/2019-02-15/</span></span></span>|<span data-ttu-id="283d1-175">2019년 2월 15일</span><span class="sxs-lookup"><span data-stu-id="283d1-175">Feb 15, 2019</span></span>|
|<span data-ttu-id="283d1-176"><span><cqdv3>https:// /spd/#/Dashboard/ <reportid> /00/</span></span><span class="sxs-lookup"><span data-stu-id="283d1-176"><span>https://<cqdv3>/spd/#/Dashboard/<reportid>/00/</span></span></span>        |<span data-ttu-id="283d1-177">현재 일</span><span class="sxs-lookup"><span data-stu-id="283d1-177">Current Day</span></span>|
|||

<span data-ttu-id="283d1-178">기본적으로 월의 현재 날은 롤링 데이의 마지막 날로 추세.</span><span class="sxs-lookup"><span data-stu-id="283d1-178">By default, the current day of the month is used as the last day of the Rolling Day Trend.</span></span>


## <a name="data-available-in-cqd-reports"></a><span data-ttu-id="283d1-179">CQD 보고서에서 사용할 수 있는 데이터</span><span class="sxs-lookup"><span data-stu-id="283d1-179">Data available in CQD reports</span></span>

<span data-ttu-id="283d1-180">기본 요약 및 자세한 CQD 보고서는 구성에 대한 통화 품질을 관리하는 데 필요한 모든 것일 수 있습니다. 필요한 경우 사용자 지정 보고서를 [만들 수 있습니다.](#create-custom-detailed-reports)</span><span class="sxs-lookup"><span data-stu-id="283d1-180">The default summary and detailed CQD reports may be all you need to manage call quality for your org. If you need to, you can [create custom reports](#create-custom-detailed-reports).</span></span> 

<span data-ttu-id="283d1-181">데이터를 사용하여 CQD Power BI 분석하려는 경우 Power BI 를 사용하여 [CQD](CQD-Power-BI-query-templates.md)데이터를 분석할 Teams.</span><span class="sxs-lookup"><span data-stu-id="283d1-181">If you want to use Power BI to analyze your CQD data, read [Use Power BI to analyze CQD data for Teams](CQD-Power-BI-query-templates.md).</span></span>

|<span data-ttu-id="283d1-182">기능</span><span class="sxs-lookup"><span data-stu-id="283d1-182">Feature</span></span>|<span data-ttu-id="283d1-183">요약 보고서</span><span class="sxs-lookup"><span data-stu-id="283d1-183">Summary Reports</span></span>|<span data-ttu-id="283d1-184">자세한 보고서</span><span class="sxs-lookup"><span data-stu-id="283d1-184">Detailed Reports</span></span>|
|:--- |:--- |:--- |
|<span data-ttu-id="283d1-185">애플리케이션 공유 메트릭</span><span class="sxs-lookup"><span data-stu-id="283d1-185">Application sharing metric</span></span> | <span data-ttu-id="283d1-186">아니요</span><span class="sxs-lookup"><span data-stu-id="283d1-186">No</span></span> | <span data-ttu-id="283d1-187">예</span><span class="sxs-lookup"><span data-stu-id="283d1-187">Yes</span></span> |
|<span data-ttu-id="283d1-188">고객 빌딩 정보 지원</span><span class="sxs-lookup"><span data-stu-id="283d1-188">Customer building information support</span></span> | <span data-ttu-id="283d1-189">예</span><span class="sxs-lookup"><span data-stu-id="283d1-189">Yes</span></span> | <span data-ttu-id="283d1-190">예</span><span class="sxs-lookup"><span data-stu-id="283d1-190">Yes</span></span> |
|<span data-ttu-id="283d1-191">고객 엔드포인트 정보 지원</span><span class="sxs-lookup"><span data-stu-id="283d1-191">Customer endpoint information support</span></span> | <span data-ttu-id="283d1-192">오직 <span> cqd.teams.microsoft.com<span/></span><span class="sxs-lookup"><span data-stu-id="283d1-192">Only in <span>cqd.teams.microsoft.com<span/></span></span> | <span data-ttu-id="283d1-193">오직 <span> cqd.teams.microsoft.com<span/></span><span class="sxs-lookup"><span data-stu-id="283d1-193">Only in <span>cqd.teams.microsoft.com<span/></span></span> |
|<span data-ttu-id="283d1-194">드릴다운 분석 지원</span><span class="sxs-lookup"><span data-stu-id="283d1-194">Drill down analysis support</span></span>   | <span data-ttu-id="283d1-195">아니요</span><span class="sxs-lookup"><span data-stu-id="283d1-195">No</span></span>   | <span data-ttu-id="283d1-196">예</span><span class="sxs-lookup"><span data-stu-id="283d1-196">Yes</span></span>   |
|<span data-ttu-id="283d1-197">미디어 안정성 메트릭</span><span class="sxs-lookup"><span data-stu-id="283d1-197">Media reliability metrics</span></span>   | <span data-ttu-id="283d1-198">아니요</span><span class="sxs-lookup"><span data-stu-id="283d1-198">No</span></span>   | <span data-ttu-id="283d1-199">예</span><span class="sxs-lookup"><span data-stu-id="283d1-199">Yes</span></span>   |
|<span data-ttu-id="283d1-200">사용 안 함 보고서</span><span class="sxs-lookup"><span data-stu-id="283d1-200">Out-of-the-box reports</span></span>   | <span data-ttu-id="283d1-201">예</span><span class="sxs-lookup"><span data-stu-id="283d1-201">Yes</span></span>   | <span data-ttu-id="283d1-202">예</span><span class="sxs-lookup"><span data-stu-id="283d1-202">Yes</span></span>   |
|<span data-ttu-id="283d1-203">개요 보고서</span><span class="sxs-lookup"><span data-stu-id="283d1-203">Overview reports</span></span>   | <span data-ttu-id="283d1-204">예</span><span class="sxs-lookup"><span data-stu-id="283d1-204">Yes</span></span>   | <span data-ttu-id="283d1-205">예</span><span class="sxs-lookup"><span data-stu-id="283d1-205">Yes</span></span>   |
|<span data-ttu-id="283d1-206">사용자당 보고서 집합</span><span class="sxs-lookup"><span data-stu-id="283d1-206">Per-user report set</span></span>   | <span data-ttu-id="283d1-207">아니요</span><span class="sxs-lookup"><span data-stu-id="283d1-207">No</span></span>   | <span data-ttu-id="283d1-208">예</span><span class="sxs-lookup"><span data-stu-id="283d1-208">Yes</span></span>   |
|<span data-ttu-id="283d1-209">보고서 집합 사용자 지정(보고서 추가, 삭제, 수정)</span><span class="sxs-lookup"><span data-stu-id="283d1-209">Report set customization (add, delete, modify reports)</span></span>   | <span data-ttu-id="283d1-210">아니요</span><span class="sxs-lookup"><span data-stu-id="283d1-210">No</span></span>   | <span data-ttu-id="283d1-211">예</span><span class="sxs-lookup"><span data-stu-id="283d1-211">Yes</span></span>   |
|<span data-ttu-id="283d1-212">비디오 기반 화면 공유 메트릭</span><span class="sxs-lookup"><span data-stu-id="283d1-212">Video-based screen sharing metrics</span></span>   | <span data-ttu-id="283d1-213">아니요</span><span class="sxs-lookup"><span data-stu-id="283d1-213">No</span></span>   | <span data-ttu-id="283d1-214">예</span><span class="sxs-lookup"><span data-stu-id="283d1-214">Yes</span></span>   |
|<span data-ttu-id="283d1-215">비디오 메트릭</span><span class="sxs-lookup"><span data-stu-id="283d1-215">Video metrics</span></span>   | <span data-ttu-id="283d1-216">아니요</span><span class="sxs-lookup"><span data-stu-id="283d1-216">No</span></span>   | <span data-ttu-id="283d1-217">예</span><span class="sxs-lookup"><span data-stu-id="283d1-217">Yes</span></span>   |
|<span data-ttu-id="283d1-218">사용 가능한 데이터 양</span><span class="sxs-lookup"><span data-stu-id="283d1-218">Amount of data available</span></span>   | <span data-ttu-id="283d1-219">지난 12개월</span><span class="sxs-lookup"><span data-stu-id="283d1-219">Last 12 months</span></span>   | <span data-ttu-id="283d1-220">지난 12개월</span><span class="sxs-lookup"><span data-stu-id="283d1-220">Last 12 months</span></span>   |
|<span data-ttu-id="283d1-221">Microsoft Teams 데이터</span><span class="sxs-lookup"><span data-stu-id="283d1-221">Microsoft Teams data</span></span>   | <span data-ttu-id="283d1-222">예</span><span class="sxs-lookup"><span data-stu-id="283d1-222">Yes</span></span>   | <span data-ttu-id="283d1-223">예</span><span class="sxs-lookup"><span data-stu-id="283d1-223">Yes</span></span>   |
| | | |


 
### <a name="select-product-data-to-see-in-reports"></a><span data-ttu-id="283d1-224">보고서에서 볼 제품 데이터 선택</span><span class="sxs-lookup"><span data-stu-id="283d1-224">Select product data to see in reports</span></span>

<span data-ttu-id="283d1-225">요약 및 Location-Enhanced 보고서에서 제품 필터 드롭다운을 사용하여 모든 제품 데이터, Microsoft Teams 데이터만 표시하거나 온라인 비즈니스용 Skype 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="283d1-225">In the Summary and Location-Enhanced Reports, you can use the **Product Filter** drop-down to show all product data, only Microsoft Teams data, or only Skype for Business Online data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="283d1-226">![스크린샷: 제품 필터 제어 옵션을 보여줍니다.](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)</span><span class="sxs-lookup"><span data-stu-id="283d1-226">![Screenshot: shows the Product Filter control options](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)</span></span>
  
<span data-ttu-id="283d1-227">자세한 보고서에서 Is **Teams** 차원을 사용하여 온라인 데이터를 Microsoft Teams 비즈니스용 Skype 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-227">In Detailed reports, you can use the **Is Teams** dimension to filter the data to Microsoft Teams or Skype for Business Online data.</span></span>

## <a name="summary-reports"></a><span data-ttu-id="283d1-228">요약 보고서</span><span class="sxs-lookup"><span data-stu-id="283d1-228">Summary Reports</span></span>

<span data-ttu-id="283d1-229">CQD에 처음 로그인할 때 CQD 대시보드에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-229">These are the reports that you'll see on the CQD Dashboard when you first sign in to CQD.</span></span> <span data-ttu-id="283d1-230">품질이 좋지 않은 서브넷 식별을 지원하기 위해 매일, 월별 및 표 보고서를 사용하여 품질 추세를 한눈에 살펴볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-230">They give you an at-a-glance look at quality trends with daily, monthly, and table reports to assist with identifying subnets that have poor quality.</span></span> 

| <span data-ttu-id="283d1-231">탭</span><span class="sxs-lookup"><span data-stu-id="283d1-231">Tab</span></span> | <span data-ttu-id="283d1-232">설명</span><span class="sxs-lookup"><span data-stu-id="283d1-232">Description</span></span> |
|---------|---------|
|<span data-ttu-id="283d1-233">전체 통화 품질</span><span class="sxs-lookup"><span data-stu-id="283d1-233">Overall Call Quality</span></span>     | <span data-ttu-id="283d1-234">다른 3개 탭의 집계입니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-234">Aggregate of the other 3 tabs.</span></span>       |
|<span data-ttu-id="283d1-235">Server—Client</span><span class="sxs-lookup"><span data-stu-id="283d1-235">Server—Client</span></span>     |<span data-ttu-id="283d1-236">서버와 클라이언트 엔드포인트 간의 스트림에 대한 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-236">Details of the streams between server and client endpoints.</span></span>        |
|<span data-ttu-id="283d1-237">Client—Client</span><span class="sxs-lookup"><span data-stu-id="283d1-237">Client—Client</span></span>     |<span data-ttu-id="283d1-238">두 클라이언트 엔드포인트 간의 스트림에 대한 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-238">Details of the streams between two client endpoints.</span></span>        |
|<span data-ttu-id="283d1-239">음성 품질 SLA</span><span class="sxs-lookup"><span data-stu-id="283d1-239">Voice Quality SLA</span></span>     |<span data-ttu-id="283d1-240">음성 품질 SLA에 포함된 호출에 비즈니스용 Skype [정보입니다.](https://go.microsoft.com/fwlink/p/?linkid=846252)</span><span class="sxs-lookup"><span data-stu-id="283d1-240">Info about calls included in the Skype for Business voice quality [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).</span></span>        |

### <a name="overall-call-quality-tab"></a><span data-ttu-id="283d1-241">전체 통화 품질 탭</span><span class="sxs-lookup"><span data-stu-id="283d1-241">Overall Call Quality tab</span></span>

<span data-ttu-id="283d1-242">이 탭의 데이터를 사용하여 스트림 수 및 가난한 백분율을 기준으로 통화 품질 상태 및 추세를 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-242">Use the data on this tab to evaluate call quality status and trends based on stream counts and poor percentages.</span></span> <span data-ttu-id="283d1-243">오른쪽 위 모서리의 범례에는 이러한 메트릭을 나타내는 색 및 시각적 요소가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-243">The legend in the upper-right corner shows which color and visual elements represent these metrics.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="283d1-244">![스크린샷: 통화 품질 탭 표시](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)</span><span class="sxs-lookup"><span data-stu-id="283d1-244">![Screenshot: show the Call Quality tab](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)</span></span>
  
<span data-ttu-id="283d1-245">스트림 그룹은 좋음, 불량 및 분류되지 않은 세 그룹으로 분류됩니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-245">Streams are classified in three groups: Good, Poor, and Unclassified.</span></span> <span data-ttu-id="283d1-246">또한 불량으로 분류된 스트림의 비율을 총  분류된 스트림 수에 대한 비율을 주는 계산된 가난한 % 값도 있습니다. </span><span class="sxs-lookup"><span data-stu-id="283d1-246">There are also calculated  *Poor %*  values that give you the ratio of streams classified as *Poor*  to the total classified stream count.</span></span> <span data-ttu-id="283d1-247">*빈약한 % = 불량 스트림/ (불량 스트림+ 양호한 스트림) \* 100이기* 때문에 불량 %는 여러 개의 비분류된 스트림의 존재에 영향을 받지  *않습니다.*</span><span class="sxs-lookup"><span data-stu-id="283d1-247">Since *Poor % = Poor streams/ (Poor streams+ Good streams) \* 100*, the *Poor %*  is unaffected by the presence of multiple *Unclassified*  streams.</span></span> <span data-ttu-id="283d1-248">스트림을 가난하거나 양호로 분류하는 것을 보기 위해 통화 품질 대시보드의 [스트림 분류를 참조하세요.](stream-classification-in-call-quality-dashboard.md)</span><span class="sxs-lookup"><span data-stu-id="283d1-248">To see what classifies a stream as poor or good, refer to [Stream Classification in Call Quality Dashboard](stream-classification-in-call-quality-dashboard.md).</span></span>
  
<span data-ttu-id="283d1-249">왼쪽의 배율을 사용하여 스트림 수 값을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-249">Use the scale on the left to measure the stream count values.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="283d1-250">![스크린샷: 스트림 수 값을 보여줍니다.](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)</span><span class="sxs-lookup"><span data-stu-id="283d1-250">![Screenshot: shows stream count values](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)</span></span>
  
<span data-ttu-id="283d1-251">오른쪽의 배율을 사용하여 가난한 % 값을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-251">Use the scale on the right to measure the Poor % values.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="283d1-252">![스크린샷: 가난한 % 값을 보여줍니다.](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)</span><span class="sxs-lookup"><span data-stu-id="283d1-252">![Screenshot: shows poor % values](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)</span></span>
  
<span data-ttu-id="283d1-253">마우스를 막대 위에 마우스로 이동하여 실제 숫자 값을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-253">You can also obtain the actual numerical values by hovering the mouse over a bar.</span></span>
  
> [!NOTE]
> <span data-ttu-id="283d1-254">다음 예제는 매우 작은 샘플 데이터 집합의 예제로, 실제 배포에 대한 값은 현실적이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-254">The following example is from a very small sample data set, and the values aren't realistic for an actual deployment.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="283d1-255">![스크린샷: 데이터에 액세스하는 데 사용되는 마우스 표시](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)</span><span class="sxs-lookup"><span data-stu-id="283d1-255">![Screenshot: shows mouse used to access data](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)</span></span>
  
<span data-ttu-id="283d1-256">전체 스트림 볼륨은 계산된 불량 백분율의 관련성 여부를 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-256">The overall stream volume helps determine how relevant the calculated Poor percentages are.</span></span> <span data-ttu-id="283d1-257">전체 스트림의 볼륨이 작을수록 보고된 불량 백분율 값이 덜 안정적입니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-257">The smaller the volume of overall streams, the less reliable the reported Poor percentage values are.</span></span>
  
### <a name="server-client-tab-and-client-client-tabs"></a><span data-ttu-id="283d1-258">Server-Client 탭 및 Client-Client 탭</span><span class="sxs-lookup"><span data-stu-id="283d1-258">Server-Client tab and Client-Client tabs</span></span>

<span data-ttu-id="283d1-259">이 두 탭은 엔드포인트 대 엔드포인트 시나리오에서 이루어진 스트림에 대한 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-259">These two tabs provide details for the streams that took place in their endpoint-to-endpoint scenarios.</span></span> <span data-ttu-id="283d1-260">Server-Client 탭에는 미디어 스트림이 흐르는 4개의 시나리오를 나타내는 4개의 축소할 수 있는 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-260">The Server-Client tab has four collapsible sections that represent four scenarios under which media streams would flow.</span></span>
  
- <span data-ttu-id="283d1-261">Wired Inside</span><span class="sxs-lookup"><span data-stu-id="283d1-261">Wired Inside</span></span>
- <span data-ttu-id="283d1-262">외부에 유선</span><span class="sxs-lookup"><span data-stu-id="283d1-262">Wired Outside</span></span>
- <span data-ttu-id="283d1-263">WiFi Inside</span><span class="sxs-lookup"><span data-stu-id="283d1-263">WiFi Inside</span></span>
- <span data-ttu-id="283d1-264">WiFi 외부</span><span class="sxs-lookup"><span data-stu-id="283d1-264">WiFi Outside</span></span>

<span data-ttu-id="283d1-265">마찬가지로, Client-Client 탭에는 5개의 축소할 수 있는 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-265">Similarly, the Client-Client tab has five collapsible sections:</span></span>

- <span data-ttu-id="283d1-266">Wired Inside — Wired Inside</span><span class="sxs-lookup"><span data-stu-id="283d1-266">Wired Inside — Wired Inside</span></span>
- <span data-ttu-id="283d1-267">유선 내부 - 외부에 유선</span><span class="sxs-lookup"><span data-stu-id="283d1-267">Wired Inside — Wired Outside</span></span>
- <span data-ttu-id="283d1-268">유선 외부 - 외부 유선</span><span class="sxs-lookup"><span data-stu-id="283d1-268">Wired Outside — Wired Outside</span></span>
- <span data-ttu-id="283d1-269">Wired Inside — WiFi Inside</span><span class="sxs-lookup"><span data-stu-id="283d1-269">Wired Inside — WiFi Inside</span></span>
- <span data-ttu-id="283d1-270">Wired Inside — WiFi Outside</span><span class="sxs-lookup"><span data-stu-id="283d1-270">Wired Inside — WiFi Outside</span></span>

#### <a name="inside-versus-outside"></a><span data-ttu-id="283d1-271">내부 및 외부</span><span class="sxs-lookup"><span data-stu-id="283d1-271">Inside versus Outside</span></span>

<span data-ttu-id="283d1-272">CQD는 스트림이 있는  경우  건물 정보를 사용하여 스트림을 내부 또는 외부로 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-272">CQD classifies a stream as  *Inside*  or *Outside*  using Building information, if it exists.</span></span> <span data-ttu-id="283d1-273">각 스트림의 엔드포인트는 서브넷 주소와 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-273">Endpoints of each stream are associated with a subnet address.</span></span> <span data-ttu-id="283d1-274">서브넷이 업로드된 건물 정보에서 InsideCorp로 표시된 서브넷 목록에 있는 경우 내부로 *간주됩니다.*</span><span class="sxs-lookup"><span data-stu-id="283d1-274">If the subnet is in the list of the subnets marked InsideCorp in the uploaded Building information, then it is considered *Inside*.</span></span> <span data-ttu-id="283d1-275">건물 정보가 아직 업로드되지 않은 경우 내부 테스트에서는 항상 스트림을 외부로 *분류합니다.*</span><span class="sxs-lookup"><span data-stu-id="283d1-275">If Building information has not yet been uploaded, then Inside Test always classifies the streams as *Outside*.</span></span> 

<span data-ttu-id="283d1-276">테스트에 대한 내부 Server-Client 클라이언트 엔드포인트만 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-276">The Inside Test for a Server-Client scenario only considers the client endpoint.</span></span> <span data-ttu-id="283d1-277">서버는 항상 사용자의 관점에서 외부에 있기 때문에 테스트에서 고려되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-277">Because servers are always outside from a user's perspective, this isn't accounted for in the test.</span></span>
  
#### <a name="wired-versus-wifi"></a><span data-ttu-id="283d1-278">WiFi와 유선 연결</span><span class="sxs-lookup"><span data-stu-id="283d1-278">Wired versus WiFi</span></span>

<span data-ttu-id="283d1-279">이름이 표시한 것 처럼 분류 조건은 클라이언트 연결의 유형을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-279">As the names indicate, the classification criteria is based on the type of client connections.</span></span> <span data-ttu-id="283d1-280">서버는 항상 유선으로 연결됩니다. 이 서버는 계산에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-280">Server is always wired and it isn't included in the calculation.</span></span> <span data-ttu-id="283d1-281">주어진 스트림에서 두 엔드포인트 중 하나가 WiFi 네트워크에 연결된 경우 CQD는 WiFi로 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-281">In a given stream, if one of the two endpoints is connected to a WiFi network, then CQD classifies it as WiFi.</span></span>

> [!NOTE]
> <span data-ttu-id="283d1-282">스트림이 제공되면 두 엔드포인트 중 하나가 WiFi 네트워크에 연결되어 있는 경우 CQD에서 WiFi로 분류됩니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-282">Given a stream, if one of the two endpoints is connected to a WiFi network, then it is classified as WiFi in CQD.</span></span>
  
  
## <a name="tenant-data-information"></a><span data-ttu-id="283d1-283">테넌트 데이터 정보</span><span class="sxs-lookup"><span data-stu-id="283d1-283">Tenant Data information</span></span>

<span data-ttu-id="283d1-284">CQD 요약 보고서 **대시보드에는** 테넌트 데이터 업로드 페이지가 포함되어 있습니다. 오른쪽 **위** 모서리의 설정 메뉴에서 업로드 테넌트 데이터 데이터를 선택하여 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-284">The CQD Summary Reports dashboard includes a **Tenant Data Upload** page, accessed by selecting **Tenant Data Upload** from the settings menu in the top-right corner.</span></span> <span data-ttu-id="283d1-285">이 페이지는 관리자가 다음과 같은 자신의 정보를 업로드하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-285">This page is used for admins to upload their own information, such as:</span></span>

- <span data-ttu-id="283d1-286">IP 주소 및 지리적 정보의 지도입니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-286">A map of IP address and geographical information.</span></span>
- <span data-ttu-id="283d1-287">각 무선 AP 및 해당 MAC 주소의 지도입니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-287">A map of each wireless AP and its MAC address.</span></span>
- <span data-ttu-id="283d1-288">엔드포인트 메이드/모델/유형 등에 대한 엔드포인트 맵</span><span class="sxs-lookup"><span data-stu-id="283d1-288">A map of Endpoint to Endpoint Make/Model/Type, etc.</span></span>
  
<span data-ttu-id="283d1-289">CQD가 보고서에 이 정보를 포함할 수 있도록 테넌트, 건물 및 위치 데이터를 업로드하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-289">We recommend that you upload your tenant, building, and location data so CQD can include this information in your reports.</span></span> <span data-ttu-id="283d1-290">이 데이터를 아직 업로드하지 않은 경우 [테넌트 및 업로드 를 읽습니다.](CQD-upload-tenant-building-data.md)</span><span class="sxs-lookup"><span data-stu-id="283d1-290">If you haven't already uploaded this data, read [Upload tenant and building data](CQD-upload-tenant-building-data.md).</span></span> 


## <a name="detailed-reports"></a><span data-ttu-id="283d1-291">자세한 보고서</span><span class="sxs-lookup"><span data-stu-id="283d1-291">Detailed reports</span></span>

| <span data-ttu-id="283d1-292">이름</span><span class="sxs-lookup"><span data-stu-id="283d1-292">Name</span></span> | <span data-ttu-id="283d1-293">설명</span><span class="sxs-lookup"><span data-stu-id="283d1-293">Description</span></span> |
|---------|---------|
|<span data-ttu-id="283d1-294">Location-Enhanced 보고서</span><span class="sxs-lookup"><span data-stu-id="283d1-294">Location-Enhanced Reports</span></span>     |<span data-ttu-id="283d1-295">위치 정보를 기반으로 품질 추세를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-295">Shows quality trends based on location information.</span></span> <span data-ttu-id="283d1-296">이 보고서는 테넌트 데이터를 업로드한 [경우만 표시됩니다.](CQD-upload-tenant-building-data.md)</span><span class="sxs-lookup"><span data-stu-id="283d1-296">This report appears only if you've [uploaded your tenant data](CQD-upload-tenant-building-data.md).</span></span>        |
|<span data-ttu-id="283d1-297">안정성 보고서</span><span class="sxs-lookup"><span data-stu-id="283d1-297">Reliability Reports</span></span>     |<span data-ttu-id="283d1-298">오디오, 비디오, VBSS(비디오 기반 화면 공유) 및 앱 공유 보고서를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-298">Includes audio, video, video-based screen sharing (VBSS), and app sharing reports.</span></span>        |
|<span data-ttu-id="283d1-299">환경 품질 보고서</span><span class="sxs-lookup"><span data-stu-id="283d1-299">Quality of Experience Reports</span></span>     |<span data-ttu-id="283d1-300">회의실을 비롯한 모든 클라이언트 및 디바이스에 대한 오디오 품질 및 안정성</span><span class="sxs-lookup"><span data-stu-id="283d1-300">Audio quality and reliability for all clients and devices, including meeting rooms.</span></span> <span data-ttu-id="283d1-301">이러한 보고서는 다운로드 가능한 [CQD](https://aka.ms/QERtemplates)템플릿의 "슬림 다운" 버전으로, 오디오 품질 및 안정성을 분석하기 위한 주요 영역에 중점을 두고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-301">These reports are a “slimmed-down” version of the downloadable [CQD templates](https://aka.ms/QERtemplates), focusing on key areas for analyzing audio quality and reliability.</span></span>         |
|<span data-ttu-id="283d1-302">품질 드릴다운 보고서</span><span class="sxs-lookup"><span data-stu-id="283d1-302">Quality Drill Down Reports</span></span>     | <span data-ttu-id="283d1-303">드릴다운: 지역, 위치, 서브넷, 시간 및 사용자별로 날짜를 정합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-303">Drill downs: Date by region, locations, subnets, hour, and users.</span></span>        |
|<span data-ttu-id="283d1-304">오류 드릴다운 보고서</span><span class="sxs-lookup"><span data-stu-id="283d1-304">Failure Drill Down Reports</span></span>     | <span data-ttu-id="283d1-305">드릴다운: 지역, 위치, 서브넷, 시간 및 사용자별로 날짜를 정합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-305">Drill downs: Date by region, locations, subnets, hour, and users.</span></span>        |
|<span data-ttu-id="283d1-306">내 통화 보고서 평가</span><span class="sxs-lookup"><span data-stu-id="283d1-306">Rate My Call Reports</span></span>     |<span data-ttu-id="283d1-307">지역, 위치 또는 사용자별로 사용자 통화 등급을 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-307">Analyze user call ratings by region, location, or by user.</span></span> <span data-ttu-id="283d1-308">구두 피드백을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-308">Includes verbatim feedback.</span></span>         |
|<span data-ttu-id="283d1-309">도움말 데스크 보고서</span><span class="sxs-lookup"><span data-stu-id="283d1-309">Help Desk Reports</span></span>     |<span data-ttu-id="283d1-310">Help Desk 보고서는 개별 사용자, 사용자 그룹 또는 모든 사용자에 대한 통화 및 모임 데이터를 살펴 니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-310">Help Desk Reports look at call and meeting data for individual users, groups of users, or everyone.</span></span> <span data-ttu-id="283d1-311">이러한 보고서는 건물 및 EUII 데이터를 통합하여 네트워크 위치, 회의 세부 정보, 디바이스 또는 펌웨어를 기반으로 가능한 시스템 문제를 식별하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-311">Incorporating building and EUII data, these reports help identify possible system issues based on network location, conference details, devices, or firmware.</span></span>         |
|<span data-ttu-id="283d1-312">클라이언트 버전 보고서</span><span class="sxs-lookup"><span data-stu-id="283d1-312">Client Version Reports</span></span>     |<span data-ttu-id="283d1-313">클라이언트 버전 요약: 각 클라이언트 앱 버전에 대한 세션 및 사용자 수 보기</span><span class="sxs-lookup"><span data-stu-id="283d1-313">Client Version Summary: View the Sessions and Users counts for each client app version</span></span><br><br><span data-ttu-id="283d1-314">사용자별로 클라이언트 버전: 각 클라이언트 앱 버전에 대한 사용자 이름 보기</span><span class="sxs-lookup"><span data-stu-id="283d1-314">Client Version by User: View user names for each client app version</span></span> <br><br><span data-ttu-id="283d1-315">제품 및 클라이언트 유형에 대한 미리 구축된 필터를 사용하면 버전을 특정 클라이언트에 집중하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-315">Pre-built filters for Product and Client Type help focus the versions to specific clients.</span></span>         |
|<span data-ttu-id="283d1-316">엔드포인트 보고서</span><span class="sxs-lookup"><span data-stu-id="283d1-316">Endpoint Reports</span></span>     |<span data-ttu-id="283d1-317">컴퓨터 엔드포인트(컴퓨터 만들기 및 모델)에 따라 호출 품질을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-317">Shows call quality by machine endpoints (computer make and model).</span></span> <span data-ttu-id="283d1-318">이러한 보고서에는 업로드한 경우 데이터 작성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-318">These reports include building data, if you've uploaded it.</span></span>         |


## <a name="create-custom-detailed-reports"></a><span data-ttu-id="283d1-319">사용자 지정 세부 보고서 만들기</span><span class="sxs-lookup"><span data-stu-id="283d1-319">Create custom detailed reports</span></span>

<span data-ttu-id="283d1-320">기본 CQD 보고서가 요구 사항을 충족하지 않는 경우 다음 지침을 사용하여 사용자 지정 보고서를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-320">If the default CQD reports don't meet your needs, use these instructions to create a custom report.</span></span> <span data-ttu-id="283d1-321">또는(2020년 1월) [CQD ](cqd-power-bi-query-templates.md)보고서에 Power BI 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="283d1-321">Or (as of January 2020) [Use Power BI for CQD reports ](cqd-power-bi-query-templates.md)instead.</span></span>

<span data-ttu-id="283d1-322">로그인에 표시되는 화면 맨 위에 있는 보고서의 풀다운 목록에서 요약 보고서 화면에서 세부 보고서 선택 및 새 \(  \) 를 **선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="283d1-322">From the pull-down list of reports at the top of the screen displayed at login \(the **Summary Reports** screen\) Select **Detailed Reports**  and then **New**.</span></span> <span data-ttu-id="283d1-323">**보고서에서** 편집을 클릭하여 쿼리 편집기를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-323">Click **Edit** in a report to see the Query Editor.</span></span> <span data-ttu-id="283d1-324">각 보고서는 큐브에 대한 쿼리에 의해 백업됩니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-324">Each report is backed by a query into the cube.</span></span> <span data-ttu-id="283d1-325">보고서는 쿼리에서 반환된 데이터의 시각화입니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-325">A report is a visualization of the data returned by its query.</span></span> <span data-ttu-id="283d1-326">쿼리 편집기를 사용하면 이러한 쿼리 및 보고서의 표시 옵션을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-326">The Query Editor helps you edit these queries and the display options of the report.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="283d1-327">네트워크 범위는 슈퍼넷을 나타내는 데 사용할 수 있습니다(단일 라우팅 연결 연결과 여러 서브넷의 조합).</span><span class="sxs-lookup"><span data-stu-id="283d1-327">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix).</span></span> <span data-ttu-id="283d1-328">모든 새 건물 업로드는 겹치는 범위에 대해 검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-328">All new building uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="283d1-329">이전에 건물 파일을 업로드한 경우 현재 파일을 다운로드하고 다시 업로드하여 중복을 식별하고 문제를 해결한 후 다시 업로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-329">If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again.</span></span> <span data-ttu-id="283d1-330">이전에 업로드된 파일의 겹치는 경우 보고서의 건물에 서브넷이 잘못 매핑될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-330">Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports.</span></span> <span data-ttu-id="283d1-331">특정 VPN 구현은 서브넷 정보를 정확하게 보고하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-331">Certain VPN implementations do not accurately report the subnet information.</span></span> <span data-ttu-id="283d1-332">서브넷에 대한 하나의 항목 대신 건물 파일에 VPN 서브넷을 추가할 때 별도의 32비트 네트워크로 VPN 서브넷의 각 주소에 대해 별도의 항목이 추가되는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-332">It is recommended that when adding a VPN subnet to the building file, instead of one entry for the subnet, separate entries are added for each address in the VPN subnet as a separate 32-bit network.</span></span> <span data-ttu-id="283d1-333">각 행에는 동일한 건물 메타데이터가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-333">Each row can have the same building metadata.</span></span> <span data-ttu-id="283d1-334">예를 들어 172.16.18.0/24에 대한 행 하나 대신 256개 행을 포함해야 합니다. 각 주소의 행은 172.16.18.255/32 사이입니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-334">For example, instead of one row for 172.16.18.0/24, you should have 256 rows, with one row for each address between 172.16.18.0/32 and 172.16.18.255/32, inclusive.</span></span>
>
> <span data-ttu-id="283d1-335">VPN 열은 선택 사항이며 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-335">The VPN column is optional and will default to 0.</span></span>  <span data-ttu-id="283d1-336">VPN 열 값이 1로 설정되어 있는 경우 해당 행으로 나타내는 서브넷이 서브넷 내의 모든 IP 주소와 일치하게 완전히 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-336">If the VPN column's value is set to 1, the subnet represented by that row will be fully expanded to match all IP addresses within the subnet.</span></span>  <span data-ttu-id="283d1-337">이러한 서브넷을 완전히 확장하면 데이터 작성과 관련된 쿼리에 대한 쿼리 타임에 부정적인 영향을 미치기 때문에 VPN 서브넷에만 이 기능을 꼭 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="283d1-337">Please use this sparingly and only for VPN subnets since fully expanding these subnets will have a negative impact on query times for queries involving building data.</span></span>

<span data-ttu-id="283d1-338">자세한 값을 표시하기 위해 보고서의 막대형 차트 및 추세선을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-338">Point to bar charts and trend lines in the report to display detailed values.</span></span> <span data-ttu-id="283d1-339">포커스가 있는 보고서에는 작업 메뉴가 표시됩니다. **편집,** **복제,** **삭제,** **다운로드** 및 보고서 **트리 내보내기.**</span><span class="sxs-lookup"><span data-stu-id="283d1-339">The report that has focus will show the action menu: **Edit**, **Clone**, **Delete**, **Download**, and **Export Report Tree**.</span></span>



## <a name="query-filters"></a><span data-ttu-id="283d1-340">쿼리 필터</span><span class="sxs-lookup"><span data-stu-id="283d1-340">Query filters</span></span>

<span data-ttu-id="283d1-341">쿼리 필터는 CQD의 쿼리 편집기를 사용하여 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-341">Query filters are implemented by using the Query Editor in CQD.</span></span> <span data-ttu-id="283d1-342">이러한 필터는 CQD에서 반환하는 레코드 수를 줄이는 데 사용 하여 보고서의 전체 크기 및 쿼리 시간을 최소화합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-342">These filters are used to reduce the number of records returned by CQD, thus minimizing the report’s overall size and query times.</span></span> <span data-ttu-id="283d1-343">관리되지 않는 네트워크를 필터링하는 데 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-343">This is especially useful for filtering out unmanaged networks.</span></span> <span data-ttu-id="283d1-344">다음 표에 나열된 필터는 정규식(RegEx)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-344">The filters listed in the following table use regular expressions (RegEx).</span></span>


| <span data-ttu-id="283d1-345">Filter</span><span class="sxs-lookup"><span data-stu-id="283d1-345">Filter</span></span>         | <span data-ttu-id="283d1-346">설명</span><span class="sxs-lookup"><span data-stu-id="283d1-346">Description</span></span>          | <span data-ttu-id="283d1-347">CQD 쿼리 필터 예제</span><span class="sxs-lookup"><span data-stu-id="283d1-347">CQD query filter example</span></span>      |
|----------------|----------------------|-------------------------------|
| <span data-ttu-id="283d1-348">빈 값 없음</span><span class="sxs-lookup"><span data-stu-id="283d1-348">No blank values</span></span>   | <span data-ttu-id="283d1-349">일부 필터에는 빈 값을 필터링하는 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-349">Some filters don’t have the option to filter for blank values.</span></span> <span data-ttu-id="283d1-350">빈 값을 수동으로 필터링하려면 빈 식을 사용하여 요구에 따라 필터를 같음 또는 같지 않은 것으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-350">To filter blank values manually, use the blank expression and set the filter to Equals or Not Equals, depending on your needs.</span></span>      | <span data-ttu-id="283d1-351">두 번째 건물 이름 \<\> \^ \\ s\*\$</span><span class="sxs-lookup"><span data-stu-id="283d1-351">Second Building Name \<\> \^\\s\*\$</span></span>                       |
| <span data-ttu-id="283d1-352">일반적인 서브넷 제외</span><span class="sxs-lookup"><span data-stu-id="283d1-352">Exclude common subnets</span></span> | <span data-ttu-id="283d1-353">관리되지 않는 네트워크와 구분하기 위해 유효한 건물 파일이 없는 경우 홈 네트워크가 보고서에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-353">Without a valid building file to separate managed from unmanaged networks, home networks will be included in the reports.</span></span> <span data-ttu-id="283d1-354">이러한 홈 서브넷은 IT 제어의 범위를 벗어날 수 있으며 보고서에서 신속하게 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-354">These home subnets are outside the scope of IT’s control and can be quickly excluded from a report.</span></span> <span data-ttu-id="283d1-355">이 가이드에 정의된 일반적인 서브넷은 10.0.0.0, 192.168.1.0 및 192.168.0.0입니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-355">Common subnets, as defined in this guide, are 10.0.0.0, 192.168.1.0 and 192.168.0.0.</span></span> | <span data-ttu-id="283d1-356">두 번째 서브넷 \<\> 10.0.0 \| 192.168.0.0 \| 192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="283d1-356">Second Subnet \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0</span></span> |
| <span data-ttu-id="283d1-357">내부 보기만</span><span class="sxs-lookup"><span data-stu-id="283d1-357">View inside only</span></span>  | <span data-ttu-id="283d1-358">관리(내부) 또는 관리되지 않는(외부)에 대한 보고서를 필터링하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-358">Used to filter a report for managed (inside) or unmanaged (outside).</span></span> <span data-ttu-id="283d1-359">관리되는 CQD 템플릿은 이미 이러한 필터로 미리 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-359">The managed CQD template is already preconfigured with these filters.</span></span>       | <span data-ttu-id="283d1-360">두 번째 내부 Corp = 내부</span><span class="sxs-lookup"><span data-stu-id="283d1-360">Second Inside Corp = Inside</span></span>        |

## <a name="report-filters"></a><span data-ttu-id="283d1-361">보고서 필터</span><span class="sxs-lookup"><span data-stu-id="283d1-361">Report filters</span></span>

<span data-ttu-id="283d1-362">CQD 보고서 필터를 사용하여 조사의 포커스를 좁힐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-362">Use CQD report filters to narrow the focus of your investigations.</span></span> <span data-ttu-id="283d1-363">쿼리 편집기 또는 보고서에서 직접 렌더링된 보고서에 필터를 추가하여 보고서 필터를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-363">Use report filters by adding a filter to the rendered report either in the Query Editor or directly in the report.</span></span> <span data-ttu-id="283d1-364">다음 보고서 필터는 [CQD](https://aka.ms/QERtemplates)템플릿 전체에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-364">The following report filters are used throughout the [CQD templates](https://aka.ms/QERtemplates).</span></span>


| <span data-ttu-id="283d1-365">Filter</span><span class="sxs-lookup"><span data-stu-id="283d1-365">Filter</span></span>     | <span data-ttu-id="283d1-366">설명</span><span class="sxs-lookup"><span data-stu-id="283d1-366">Description</span></span>                            | <span data-ttu-id="283d1-367">CQD 보고서 필터 예제</span><span class="sxs-lookup"><span data-stu-id="283d1-367">CQD report filter example</span></span>         |
|------------|----------------------------------------|-----------------------------------|
| <span data-ttu-id="283d1-368">월</span><span class="sxs-lookup"><span data-stu-id="283d1-368">Month</span></span>      | <span data-ttu-id="283d1-369">첫 번째 연도, 월로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-369">Start with the year first, then month.</span></span> | <span data-ttu-id="283d1-370">2017-10</span><span class="sxs-lookup"><span data-stu-id="283d1-370">2017-10</span></span>                           |
| <span data-ttu-id="283d1-371">알파벳</span><span class="sxs-lookup"><span data-stu-id="283d1-371">Alphabetic</span></span> | <span data-ttu-id="283d1-372">영문자에 대한 필터입니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-372">Filters for any alphabetic characters.</span></span> | <span data-ttu-id="283d1-373">[a-z]</span><span class="sxs-lookup"><span data-stu-id="283d1-373">[a-z]</span></span>                             |
| <span data-ttu-id="283d1-374">숫자</span><span class="sxs-lookup"><span data-stu-id="283d1-374">Numeric</span></span>    | <span data-ttu-id="283d1-375">숫자 문자에 대한 필터입니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-375">Filters for any numeric characters.</span></span>    | <span data-ttu-id="283d1-376">[0-9]</span><span class="sxs-lookup"><span data-stu-id="283d1-376">[0-9]</span></span>                             |
| <span data-ttu-id="283d1-377">백분율</span><span class="sxs-lookup"><span data-stu-id="283d1-377">Percentage</span></span> | <span data-ttu-id="283d1-378">백분율에 대한 필터입니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-378">Filters for a percentage.</span></span>              | <span data-ttu-id="283d1-379">([3-9] \\ .) \| ([3-9]) \| ([1-9][0-9])</span><span class="sxs-lookup"><span data-stu-id="283d1-379">([3-9]\\.)\|([3-9])\|([1-9][0-9])</span></span> |


### <a name="drill-down-filters"></a><span data-ttu-id="283d1-380">드릴다운 필터</span><span class="sxs-lookup"><span data-stu-id="283d1-380">Drill-down filters</span></span>

<span data-ttu-id="283d1-381">CQD 보고서에는 통화 품질 조사의 포커스를 좁히는 강력한 도구인 몇 가지 드릴다운 필터가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-381">CQD reports feature several drill-down filters, which are powerful tools for narrowing the focus of your call-quality investigations.</span></span> <span data-ttu-id="283d1-382">드릴다운 필드를 선택하면 보고서가 자동으로 적절한 탭을 열고 선택한 값에 대한 필터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-382">If you select a drill-down field, the report automatically opens the appropriate tab and filters on the selected value.</span></span> <span data-ttu-id="283d1-383">해당 탭에 자체 드릴다운 필드가 있으며 하나의 필드가 선택된 경우 두 필터 집합이 모두 적용되어 결과 데이터 집합이 점진적으로 좁아지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-383">If that tab has its own drill-down fields and one is selected, both sets of filters are applied, progressively narrowing the resulting data set.</span></span>

![드릴다운 보고서 흐름을 설명하는 다이어그램](media/qerguide-image-drillthrureportflow.png)


#### <a name="adding-and-editing-drill-down-fields"></a><span data-ttu-id="283d1-385">드릴다운 필드 추가 및 편집</span><span class="sxs-lookup"><span data-stu-id="283d1-385">Adding and editing drill-down fields</span></span>

<span data-ttu-id="283d1-386">보고서를 편집할 때 쿼리 편집기를 사용하여 사용자 자신의 드릴다운 필드를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-386">When editing a report, you have the option to specify drill-down fields of your own using the Query Editor.</span></span>

<span data-ttu-id="283d1-387">를 클릭하여 **시작하세요.**</span><span class="sxs-lookup"><span data-stu-id="283d1-387">Start by clicking **…**</span></span> <span data-ttu-id="283d1-388">편집하려는 보고서의 경우 편집을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="283d1-388">for the report you want to edit, then select **Edit**.</span></span>

![드릴다운 필드 편집 스크린샷](media/qerguide-image-addeditdrilldownfields.png)

<span data-ttu-id="283d1-390">쿼리 편집기 왼쪽의 목록에서 차원을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-390">Select a Dimension from the list on the left side of the Query Editor.</span></span> <span data-ttu-id="283d1-391">그런 다음 탐색 레이블 아래의 드롭다운을 **클릭하고** 해당 차원을 드릴링할 탭 및 확장기 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-391">Then click on the dropdown below the **Navigate To** label and select the tab and expander group that you want that Dimension to drill through to.</span></span> <span data-ttu-id="283d1-392">참고: 현재 드릴다운 기능은 다른 탭으로 이동하여만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-392">Note: Presently, drill-down functionality only works by navigating to different tabs.</span></span> <span data-ttu-id="283d1-393">특정 확장기에 드릴링에 대한 지원은 나중에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-393">Support for drilling through to a specific expander will be added later.</span></span> <span data-ttu-id="283d1-394">마지막으로 닫기를 **클릭하여** 변경 내용을 차원에 저장한 다음 저장을 클릭하여 쿼리 편집기를 저장하고 닫습니다. </span><span class="sxs-lookup"><span data-stu-id="283d1-394">Finally, click **Close** to save your changes to the Dimension, then click **Save** to save and close the Query Editor.</span></span>

![쿼리 편집기에서 차원 선택 스크린샷](media/qerguide-image-selectquerydimension.png)

### <a name="multi-select-filters"></a><span data-ttu-id="283d1-396">다중 선택 필터</span><span class="sxs-lookup"><span data-stu-id="283d1-396">Multi-select filters</span></span>

<span data-ttu-id="283d1-397">드릴다운 기능 외에도 CQD는 여러 값(OR 필터)이 있는 필터 지정도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-397">In addition to drill-down functionality, CQD also supports specifying Filters with multiple values (OR filters).</span></span>

<span data-ttu-id="283d1-398">여러 필터 값을 선택하려면 먼저 보고서에 새 필터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-398">In order to select multiple filter values, begin by adding a new filter to the report.</span></span> <span data-ttu-id="283d1-399">필터 레이블 옆을 클릭하고 사용할 차원의 이름을 입력하고 **+** 추가를 **클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="283d1-399">Click **+** beside the **Filters** label, enter the name of the Dimension you want to use, and click **Add**.</span></span>

![다중 선택 필터를 추가하는 스크린샷](media/qerguide-image-addmultiselectfilter.png)

<span data-ttu-id="283d1-401">그런 다음 **검색(새** 필터 옆에 있는 돋보기 아이콘)을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-401">Then, click **Search** (a magnifying glass icon next to the new filter).</span></span> <span data-ttu-id="283d1-402">텍스트 필드와 모두 선택 및 반전을  비롯한 다양한 **옵션이 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="283d1-402">You'll see a text field, and a number of options, including **Select All** and **Invert**.</span></span> <span data-ttu-id="283d1-403">값을 입력하고 해당 필드 **옆에** 있는 검색을 클릭하여 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-403">Enter a value,  and click **Search** next to that field to search.</span></span> <span data-ttu-id="283d1-404">또는 텍스트 필드를 비워두고 **검색을** 클릭하여 처음 100개 옵션까지 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-404">Alternatively, leave the text field empty and click **Search** to view up to the first 100 options.</span></span>

```powershell
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

<span data-ttu-id="283d1-405">예제:</span><span class="sxs-lookup"><span data-stu-id="283d1-405">Example:</span></span>  

![쿼리 필터를 추가하는 스크린샷](media/qerguide-image-addfilter.png)

### <a name="dashboard-level-filters"></a><span data-ttu-id="283d1-407">대시보드 수준 필터</span><span class="sxs-lookup"><span data-stu-id="283d1-407">Dashboard level filters</span></span>
<span data-ttu-id="283d1-408">특정 CQD 보고서에는 대시보드 수준 필터가 추가되어 일반적인 매개 변수를 통해 쉽게 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-408">Certain CQD reports have dashboard-level filters added to them, making it easy to filter by common parameters.</span></span> <span data-ttu-id="283d1-409">이러한 필터는 일반 보고서 탭 외부 및 제품 필터 바로 아래에 나타나며 대시보드의 모든 필터에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-409">These filters appear outside the regular report tabs and directly beneath the Product filter, and they apply to all filters in the Dashboard.</span></span>

![대시보드 필터 스크린샷](media/qerguide-image-dashboardfilters.png)
```powershell
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

### <a name="url-filters"></a><span data-ttu-id="283d1-411">URL 필터</span><span class="sxs-lookup"><span data-stu-id="283d1-411">URL filters</span></span>

<span data-ttu-id="283d1-412">CQD는 URL에 필터 추가를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-412">CQD supports adding filters to the URL.</span></span> <span data-ttu-id="283d1-413">이렇게 하면 CQD 쿼리를 쉽게 공유하거나 책갈피를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-413">This makes it easy to share or bookmark a CQD query.</span></span> <span data-ttu-id="283d1-414">URL에서 추세 월, 테넌트 ID 또는 언어와 같은 매개 변수를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-414">You can define parameters in the URL, such as Trending Month, tenant ID, or language.</span></span> <span data-ttu-id="283d1-415">URL에 제품 또는 대시보드 수준 필터를 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-415">You can also add Product or Dashboard level filters to the URL.</span></span>
<span data-ttu-id="283d1-416">CQD 보고서에서 페더링된 데이터를 제외하면 페더링된 엔드포인트가 보고서에 영향을 줄 수 있는 관리되는 건물 또는 네트워크를 수정하는 경우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-416">Excluding federated data from CQD reports is useful when you're remediating managed buildings or networks where federated endpoints might influence your reports.</span></span>

<span data-ttu-id="283d1-417">필터를 추가하고 URL 끝에 다음을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-417">To add a filter, append the following to the end of the URL:</span></span>

```console
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

<span data-ttu-id="283d1-418">예제:</span><span class="sxs-lookup"><span data-stu-id="283d1-418">Example:</span></span>  

`https://cqd.teams.microsoft.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]`

<span data-ttu-id="283d1-419">URL에 대시보드 수준 필터를 추가하려면 해당 필터가 제품 또는 대시보드 수준 필터로 CQD에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-419">To add a Dashboard-level filter to a URL, that filter must exist in CQD as either a Product or Dashboard level filter.</span></span> <span data-ttu-id="283d1-420">추세 월 이후 및 URL 매개 변수 앞에 다음 필터를 URL에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-420">Add these filters to the URL after the Trending Month and before the URL parameters:</span></span>

`filter/DATA_MODEL_NAME|VALUE`

<span data-ttu-id="283d1-421">예를 들어 제품 필터 값을 Microsoft Teams 다음을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-421">For example, to apply a Product filter value of Microsoft Teams, you'd add the following:</span></span>

`filter/[AllStreams].[Is%20Teams]|[True]`

<span data-ttu-id="283d1-422">전체 URL은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-422">Your entire URL would look something like this:</span></span>

`https://cqd.teams.microsoft.com/spd/#/Dashboard/2624085/2018-9/filter/[AllStreams].[Is%20Teams]|[True]`

<span data-ttu-id="283d1-423">다중 선택 값으로 URL 필터를 적용하려면 파이프(|) 문자로 | 합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-423">To apply URL filters with multi-select values, separate each value with a pipe ( | ) character.</span></span> <span data-ttu-id="283d1-424">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-424">For example:</span></span>

`filter/[AllStreams].[Media%20Type]|[Video]|[Audio]|[VBSS]`

<span data-ttu-id="283d1-425">잘못된 이름 또는 값을 지정하면 URL 필터가 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-425">If you specify an invalid name or value, the URL filter won't be applied.</span></span>


<span data-ttu-id="283d1-426">URL 필터를 사용하여 특정 차원에 대한 모든 보고서를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-426">You can use a URL filter to filter every report for a specific dimension.</span></span> <span data-ttu-id="283d1-427">가장 일반적인 URL 필터는 보고서를 필터링하여 페더리된 참가자 원격 분석은 제외하거나 온라인 또는 온라인에서만 Teams 비즈니스용 Skype 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-427">The most common URL filters are used to filter reports to exclude federated participant telemetry, or focus on only Teams or Skype for Business Online.</span></span> <span data-ttu-id="283d1-428">CQD 보고서에서 페더링된 데이터를 제외하면 페더링된 엔드포인트가 보고서에 영향을 줄 수 있는 관리되는 건물 또는 네트워크를 수정하는 경우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-428">Excluding federated data from CQD reports is useful when you're remediating managed buildings or networks where federated endpoints might influence your reports.</span></span>

| <span data-ttu-id="283d1-429">Filter</span><span class="sxs-lookup"><span data-stu-id="283d1-429">Filter</span></span>         | <span data-ttu-id="283d1-430">설명</span><span class="sxs-lookup"><span data-stu-id="283d1-430">Description</span></span>          | <span data-ttu-id="283d1-431">CQD 쿼리 필터 예제</span><span class="sxs-lookup"><span data-stu-id="283d1-431">CQD query filter example</span></span>      |
|----------------|----------------------|-------------------------------|
| <span data-ttu-id="283d1-432">빈 값 없음</span><span class="sxs-lookup"><span data-stu-id="283d1-432">No blank values</span></span>   | <span data-ttu-id="283d1-433">일부 필터에는 빈 값을 필터링하는 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-433">Some filters don't have the option to filter for blank values.</span></span> <span data-ttu-id="283d1-434">빈 값을 수동으로 필터링하려면 빈 식을 사용하여 요구에 따라 필터를 같음 또는 같지 않은 것으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-434">To filter blank values manually, use the blank expression and set the filter to Equals or Not Equals, depending on your needs.</span></span>      | <span data-ttu-id="283d1-435">두 번째 건물 이름 \<\> \^ \\ s\*\$</span><span class="sxs-lookup"><span data-stu-id="283d1-435">Second Building Name \<\> \^\\s\*\$</span></span>                       |
| <span data-ttu-id="283d1-436">일반적인 서브넷 제외</span><span class="sxs-lookup"><span data-stu-id="283d1-436">Exclude common subnets</span></span> | <span data-ttu-id="283d1-437">관리되지 않는 네트워크와 구분하기 위해 유효한 건물 파일이 없는 경우 홈 네트워크가 보고서에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-437">Without a valid building file to separate managed from unmanaged networks, home networks will be included in the reports.</span></span> <span data-ttu-id="283d1-438">이러한 홈 서브넷은 IT 제어의 범위를 벗어날 수 있으며 보고서에서 신속하게 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-438">These home subnets are outside the scope of IT's control and can be quickly excluded from a report.</span></span> <span data-ttu-id="283d1-439">이 문서에 정의된 일반적인 서브넷은 10.0.0.0, 192.168.1.0 및 192.168.0.0입니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-439">Common subnets, as defined in this article, are 10.0.0.0, 192.168.1.0 and 192.168.0.0.</span></span> | <span data-ttu-id="283d1-440">두 번째 서브넷 \<\> 10.0.0 \| 192.168.0.0 \| 192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="283d1-440">Second Subnet \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0</span></span> |
| <span data-ttu-id="283d1-441">내부 보기만</span><span class="sxs-lookup"><span data-stu-id="283d1-441">View inside only</span></span>  | <span data-ttu-id="283d1-442">관리(내부) 또는 관리되지 않는(외부)에 대한 보고서를 필터링하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-442">Used to filter a report for managed (inside) or unmanaged (outside).</span></span> <span data-ttu-id="283d1-443">관리되는 CQD 템플릿은 이미 이러한 필터로 미리 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-443">The managed CQD template is already preconfigured with these filters.</span></span>       | <span data-ttu-id="283d1-444">두 번째 내부 Corp = 내부</span><span class="sxs-lookup"><span data-stu-id="283d1-444">Second Inside Corp = Inside</span></span>        |


#### <a name="how-to-find-your-tenant-id"></a><span data-ttu-id="283d1-445">테넌트 ID를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="283d1-445">How to find your tenant ID</span></span>

<span data-ttu-id="283d1-446">CQD의 테넌트 ID는 Azure의 디렉터리 ID에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-446">The tenant ID in CQD corresponds to the Directory ID in Azure.</span></span> <span data-ttu-id="283d1-447">디렉터리 ID를 모르는 경우 Azure Portal에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-447">If you don't know your Directory ID, you can find it in the Azure portal:</span></span>

1.  <span data-ttu-id="283d1-448">포털에 Microsoft Azure:<https://portal.azure.com></span><span class="sxs-lookup"><span data-stu-id="283d1-448">Sign in to the Microsoft Azure portal: <https://portal.azure.com></span></span>

2.  <span data-ttu-id="283d1-449">를 **Azure Active Directory** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-449">Select **Azure Active Directory**.</span></span>

3.  <span data-ttu-id="283d1-450">**관리에서** 속성을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="283d1-450">Under **Manage**, select **Properties**.</span></span> <span data-ttu-id="283d1-451">테넌트 ID는 **디렉터리 ID 상자에** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-451">Your tenant ID is in the **Directory ID** box.</span></span>

<span data-ttu-id="283d1-452">PowerShell을 사용하여 테넌트 ID를 찾을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-452">You can also find your tenant ID by using PowerShell:</span></span> 

```powershell
Login-AzureRmAccount
```

## <a name="comparing-teams-and-skype-for-business-cqd-data"></a><span data-ttu-id="283d1-453">CQD Teams 및 비즈니스용 Skype 비교</span><span class="sxs-lookup"><span data-stu-id="283d1-453">Comparing Teams and Skype for Business CQD data</span></span>

<span data-ttu-id="283d1-454">데이터를 검토할 때 데이터와 데이터 간에 데이터가 Teams 비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="283d1-454">When reviewing your data, you may see differences in data between Teams and Skype for Business.</span></span> <span data-ttu-id="283d1-455">몇 가지 이유:</span><span class="sxs-lookup"><span data-stu-id="283d1-455">Some reasons:</span></span>
- <span data-ttu-id="283d1-456">성능 및 안정성을 보장하기 위한 메커니즘의 차이점:</span><span class="sxs-lookup"><span data-stu-id="283d1-456">Differences in the mechanisms for ensuring performance and reliability:</span></span>
  - <span data-ttu-id="283d1-457">Teams 자동 다시 연결 및 빠른 로밍이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-457">Teams has auto-reconnect and fast roaming.</span></span> <span data-ttu-id="283d1-458">비즈니스용 Skype 않습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-458">Skype for Business doesn't.</span></span>
  - <span data-ttu-id="283d1-459">Teams 대역폭 관리가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-459">Teams has dynamic bandwidth management.</span></span> <span data-ttu-id="283d1-460">비즈니스용 Skype 않습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-460">Skype for Business doesn't.</span></span>
- <span data-ttu-id="283d1-461">IP 주소 [범위의 차이는](Office-365-URLs-IP-address-ranges.md) Teams 비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="283d1-461">Differences in [IP address ranges](Office-365-URLs-IP-address-ranges.md) between Teams and Skype for Business.</span></span> <span data-ttu-id="283d1-462">Teams IP 범위가 더 새로 추가되어 방화벽에서 연결 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-462">The Teams IP ranges are newer, which could cause connectivity problems at the firewall.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="283d1-463">2020년 7월 1일부로, 레거시 버전의 CQD(cqd.lync.com)는 새 CQD(의 데이터에 액세스하며, 더 이상 구축 및 보고 데이터를 내보낼 수 https://CQD.teams.microsoft.com) 없습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-463">As of July 1, 2020, the legacy version of CQD (cqd.lync.com) accesses data from the new CQD (https://CQD.teams.microsoft.com), and you can no longer export building and report data.</span></span> <span data-ttu-id="283d1-464">2021년 7월 31일이 온라인 사용 중지와 비즈니스용 Skype 레거시 CQD가 해제되어 더 이상 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="283d1-464">Effective July 31, 2021, coinciding with the retirement of Skype for Business Online, we'll turn off legacy CQD and you'll no longer be able to access it.</span></span>


## <a name="related-topics"></a><span data-ttu-id="283d1-465">관련 주제</span><span class="sxs-lookup"><span data-stu-id="283d1-465">Related topics</span></span>

[<span data-ttu-id="283d1-466">통화 품질 향상 및 모니터링 Teams</span><span class="sxs-lookup"><span data-stu-id="283d1-466">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="283d1-467">CQD란?</span><span class="sxs-lookup"><span data-stu-id="283d1-467">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="283d1-468">CQD(통화 품질 대시보드) 설정</span><span class="sxs-lookup"><span data-stu-id="283d1-468">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="283d1-469">업로드 데이터 구축</span><span class="sxs-lookup"><span data-stu-id="283d1-469">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="283d1-470">CQD를 사용하여 통화 및 모임 품질 관리</span><span class="sxs-lookup"><span data-stu-id="283d1-470">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="283d1-471">CQD에서 사용할 수 있는 차원 및 측정값</span><span class="sxs-lookup"><span data-stu-id="283d1-471">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="283d1-472">CQD의 스트림 분류</span><span class="sxs-lookup"><span data-stu-id="283d1-472">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="283d1-473">CQD Power BI 분석하는 데 Power BI 사용</span><span class="sxs-lookup"><span data-stu-id="283d1-473">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)
