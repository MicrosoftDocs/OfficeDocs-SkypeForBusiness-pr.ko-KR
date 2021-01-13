---
title: CQD 개발 샘플
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8ca9bf7a-2d6f-48d5-a821-531009726525
description: '요약: 통화 품질 대시보드에 대한 자습서 및 개발 예제를 검토합니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 193a03662d6f771b19c57017d909cc6574a755ef
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832728"
---
# <a name="cqd-development-samples"></a><span data-ttu-id="2bb60-104">CQD 개발 샘플</span><span class="sxs-lookup"><span data-stu-id="2bb60-104">CQD Development Samples</span></span>

<span data-ttu-id="2bb60-105">**요약:** 통화 품질 대시보드에 대한 자습서 및 개발 샘플을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-105">**Summary:** Review a tutorial and development samples for Call Quality Dashboard.</span></span> <span data-ttu-id="2bb60-106">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="2bb60-107">이 문서에서는 CQD(통화 품질 대시보드)에 대한 개발에 대한 자습서 및 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-107">This article provides a tutorial and samples on development for Call Quality Dashboard (CQD).</span></span>

## <a name="call-quality-dashboard-cqd-development-samples"></a><span data-ttu-id="2bb60-108">CQD(통화 품질 대시보드) 개발 샘플</span><span class="sxs-lookup"><span data-stu-id="2bb60-108">Call Quality Dashboard (CQD) Development Samples</span></span>

<span data-ttu-id="2bb60-109">자습서: CQD 데이터 서비스 및 리포지토리 서비스 API를 사용하여 사용자 지정된 보고서 프레젠테이션을 구축합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-109">Tutorial: Building Customized Report Presentation using the CQD Data Service and Repository Service API's.</span></span>

### <a name="introduction-to-cqd"></a><span data-ttu-id="2bb60-110">CQD 소개</span><span class="sxs-lookup"><span data-stu-id="2bb60-110">Introduction to CQD</span></span>

<span data-ttu-id="2bb60-111">CQD는 비즈니스용 Skype 서버 배포를 위해 집계된 통화 품질 정보에 빠르고 쉽게 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-111">CQD offers quick and easy access to aggregated call quality information for on-premise Skype for Business Server deployments.</span></span> <span data-ttu-id="2bb60-112">CQD는 QoE 보관 데이터베이스, 큐브 및 포털의 세 가지 구성 요소로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-112">CQD consists of three components: the QoE Archive database, the Cube, and the Portal.</span></span> <span data-ttu-id="2bb60-113">포털은 기본 프레젠테이션 계층으로, 다음 세 가지 구성 요소로 나뉘어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-113">The Portal is the main presentation layer and can be further divided into the following three components:</span></span>

1. <span data-ttu-id="2bb60-114">데이터 서비스 - 비즈니스용 Skype 서버의 [CQD(통화](data-api.md)품질 대시보드)에 대한 데이터 API를 통해 인증된 사용자가 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-114">Data Service, which is accessible for authenticated users through the [Data API for Call Quality Dashboard (CQD) in Skype for Business Server](data-api.md).</span></span>

2. <span data-ttu-id="2bb60-115">리포지토리 서비스는 비즈니스용 Skype 서버의 [CQD(통화](repository-api.md)품질 대시보드)에 대한 리포지토리 API를 통해 인증된 사용자가 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-115">Repository Service, which is accessible for authenticated users through the [Repository API for Call Quality Dashboard (CQD) in Skype for Business Server](repository-api.md).</span></span>

3. <span data-ttu-id="2bb60-116">웹 포털 - CQD 사용자가 보고 상호 작용하는 HTML5 기반 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-116">Web portal, which is the HTML5 based interface that CQD users see and interact with.</span></span> <span data-ttu-id="2bb60-117">인증된 사용자가 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-117">This is accessible for authenticated users.</span></span>

<span data-ttu-id="2bb60-118">웹 포털에 표시된 보고서는 "보고서 집합"으로 그룹화됩니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-118">The reports shown on the web portal are grouped into "report sets".</span></span> <span data-ttu-id="2bb60-119">그림에는 두 개의 보고서가 있는 보고서 집합이 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-119">The figure shows a report set with two reports.</span></span> <span data-ttu-id="2bb60-120">아래 대시보드의 각 보고서에는 다양한 필터가 적용된 몇 개월 동안의 양호한 통화 수, 불량 통화 및 불량 통화 비율에 대한 쿼리 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-120">Each report in this dashboard below shows query results on number of good calls, poor calls and poor call percentage for several months, with various filters applied.</span></span> 

![CQD 샘플 보고서](../../media/9e0723f7-f850-4d11-9ecd-7e8e013a8bed.png)

<span data-ttu-id="2bb60-122">CQD는 CQM(통화 품질 방법론)에 따라 만들어지기 때문에 기본 보고서 집합은 CQM에서 도입한 조사 흐름에 맞게 디자인됩니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-122">CQD is created following the Call Quality Methodology (CQM), so the default set of reports is designed to align with the investigation flow introduced by CQM.</span></span> <span data-ttu-id="2bb60-123">또한 사용자는 자신의 요구에 따라 사용자 지정 보고서를 편집하거나 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-123">Users also have the flexibility to edit or create custom reports to meet their needs.</span></span> <span data-ttu-id="2bb60-124">그러나 데이터를 시각화하는 방법이 여러 가지이기 때문에 CQD에서 제공하는 시각화가 모든 사용자의 요구를 완전히 충족하지는 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-124">However, since there are multiple ways to visualize the data, the visualization provided by CQD may not fully address the needs of every user.</span></span> <span data-ttu-id="2bb60-125">이러한 경우 사용자는 데이터 API 및 리포지토리 API를 활용하여 사용자 지정 보고서 페이지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-125">In such situations, a user can leverage the Data APIs and Repository APIs to create custom report pages.</span></span> <span data-ttu-id="2bb60-126">이 자습서에서는 일련의 예제를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-126">We will go through a series of examples in this tutorial.</span></span>

### <a name="how-the-dashboard-consumes-the-data-service"></a><span data-ttu-id="2bb60-127">대시보드에서 데이터 서비스를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="2bb60-127">How the dashboard consumes the data service</span></span>

<span data-ttu-id="2bb60-128">CQD 홈페이지(예: 인증된 사용자 및 권한이 부여된 사용자에 대한 보고서 집합 및 해당 보고서)를 검색할 때 리포지토리 서비스에서 http://localhost/cqd) 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-128">When navigating to the CQD homepage (e.g. http://localhost/cqd), the report set and corresponding reports for an authenticated and authorized user will be retrieved from the Repository Service.</span></span> <span data-ttu-id="2bb60-129">전체 URL은 보고서 집합 ID와 연도-월에서 생성됩니다. 보고서 집합 ID는 URL에서 '/#/' 섹션 다음에 오는 정수 번호로, 기본적으로 슬래시 후 보고서 집합 ID의 끝에 현재 연도-월이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-129">A full URL will be constructed from the report-set ID and the year-month (report-set ID is the integer number after '/#/' section in URL, and by default the current year-month is appended at the end of the report-set ID after the slash).</span></span> <span data-ttu-id="2bb60-130">보고서 정의는 JSON 형식으로 저장되고 리포지토리 서비스에서 검색되면 데이터 서비스에 대한 입력으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-130">The report definitions are stored in JSON format and when retrieved from the Repository Service, will then be used as input to the Data Service.</span></span> <span data-ttu-id="2bb60-131">데이터 서비스는 입력을 기반으로 MDX(Multi-Dimension expressions) 쿼리를 생성한 다음 큐브에 대해 이러한 MDX 쿼리를 실행하여 각 보고서의 데이터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-131">The Data Service generates Multi-Dimension expressions (MDX) queries based on the input and then run these MDX queries against the Cube to retrieve data for each report.</span></span> 

### <a name="building-customized-reports"></a><span data-ttu-id="2bb60-132">사용자 지정된 보고서 작성</span><span class="sxs-lookup"><span data-stu-id="2bb60-132">Building customized reports</span></span>

<span data-ttu-id="2bb60-133">CQD는 이미 보고서를 사용자 지정하는 데 많은 유연성이 있지만 사용자가 CQD에서 만든 여러 보고서에서 데이터를 집계해야 하는 상황이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-133">CQD already has a lot of flexibility in customizing reports, but there could be situations where users may want to aggregate data across multiple reports created in CQD.</span></span> <span data-ttu-id="2bb60-134">예를 들어 테이블에서 가능한 모든 유선 통화 조합의 불량 통화 비율(그림과 같은 결과)을 표시하는 보고서를 만들어야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-134">For example, there could be a need to create a report that shows the poor call percentages of all possible combinations of wired calls in a table (a result like the figure):</span></span>

![CQD 테이블](../../media/ef19d535-5da6-44a9-91f6-1ed3f30b96f1.png)

<span data-ttu-id="2bb60-136">CQD에서 제공하는 포털을 사용하여 사용자는 여러 보고서로 이동하여 각 보고서에 대한 불량 통화율을 추출하고 기록해야 하며, 수집해야 하는 데이터 포인트가 많은 경우 번거로우면 번거로우게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-136">Using the Portal provided by CQD, a user would have to navigate to multiple reports to extract and record the poor call % for each one, which can be laborious if there are many data points that need to be collected.</span></span> <span data-ttu-id="2bb60-137">데이터 API는 데이터 서비스(예: AJAX 호출을 통해)에서 데이터를 검색하여 이 작업을 프로그래밍 방식으로 수행할 수 있는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-137">The Data APIs provide users with a programmatic way to accomplish this, by retrieving data from the Data Service (e.g. via AJAX calls).</span></span> 

 <span data-ttu-id="2bb60-138">**예제 1: 간단한 보고서 샘플**</span><span class="sxs-lookup"><span data-stu-id="2bb60-138">**Example 1: Simple report sample**</span></span>

<span data-ttu-id="2bb60-139">먼저 간단한 예를 들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-139">Let us take a simple example first.</span></span> <span data-ttu-id="2bb60-140">HTML 페이지에 2015년 2월의 오디오 양호한 스트림과 오디오 불량 스트림 수를 그림과 같이 표시하려면</span><span class="sxs-lookup"><span data-stu-id="2bb60-140">If we want to show the Audio Good Stream and the Audio Bad stream count of February 2015 on an HTML page like the figure:</span></span>

![CQD 예제 보고서](../../media/f0e4e61f-1fa5-4d69-b192-f19e9612bf1c.png)

<span data-ttu-id="2bb60-142">적절한 매개 변수를 사용하여 데이터 서비스에 호출을 보내고 쿼리 결과를 HTML 테이블에 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-142">What we need is to send a call to the Data Service with the proper parameters, and show the query results in an HTML table.</span></span> <span data-ttu-id="2bb60-143">다음은 JavaScript 코드의 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-143">The following is a sample of the JavaScript code:</span></span>

```javascript        
$($.fn.freeFormReport = function (queries, urlApi, presentation) {
            var query = {
                Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                Filters: [{
                    DataModelName: '[StartDate].[Month]',
                    Value: '[2015-02-01T00:00:00]',
                    Operand: 0
                }],
                Measurements:
                    [{ DataModelName: '[Measures].[Audio Good Streams JPDR Count]' },
                     { DataModelName: '[Measures].[Audio Poor Streams JPDR Count]' },]
            };            

            $.ajax({
                url: 'http://localhost/QoEDataService/RunQuery',
                data: JSON.stringify(query),
                type: 'POST',
                async: true,
                contentType: 'application/json;charset=utf-8',
                success: function (data) {
                    //This is the jQuery syntax for document.GetElementById()
                    $('#AudioGoodStreamsJPDRCount').html(data.DataResult[0][1]);
                    $('#AudioPoorStreamsJPDRCount').html(data.DataResult[0][2]);
                }
                error: function (error) {
                    alert('Error getting data, check that the data service is running and that the URL is correct.');
           }
            });
        });
```

<span data-ttu-id="2bb60-144">이 예제는 다음 세 단계로 추가로 해체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-144">This example can be further deconstructed into three steps:</span></span>

1. <span data-ttu-id="2bb60-145">쿼리를 생성합니다(예제에서는 'query' 변수에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-145">Construct the query (in the example this is defined in the variable 'query').</span></span> <span data-ttu-id="2bb60-146">쿼리는 다음 데이터를 포함하는 JSON 개체로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-146">The query is defined as a JSON object, which includes the following data:</span></span>

   <span data-ttu-id="2bb60-147">a.</span><span class="sxs-lookup"><span data-stu-id="2bb60-147">a.</span></span> <span data-ttu-id="2bb60-148">0개 이상의 차원</span><span class="sxs-lookup"><span data-stu-id="2bb60-148">Zero or more dimensions.</span></span> <span data-ttu-id="2bb60-149">각 차원은 DataModelName으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-149">Each dimension is indicated by a DataModelName.</span></span>

   <span data-ttu-id="2bb60-150">b.</span><span class="sxs-lookup"><span data-stu-id="2bb60-150">b.</span></span> <span data-ttu-id="2bb60-151">필터가 0개 이상입니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-151">Zero or more filters.</span></span> <span data-ttu-id="2bb60-152">각 필터에는</span><span class="sxs-lookup"><span data-stu-id="2bb60-152">Each filter has:</span></span>

   - <span data-ttu-id="2bb60-153">DataModelName(필터 집합을 사용할 차원)</span><span class="sxs-lookup"><span data-stu-id="2bb60-153">DataModelName (the dimension that will have the filter set).</span></span>

   - <span data-ttu-id="2bb60-154">값(피연산자에 의해 비교될 값)</span><span class="sxs-lookup"><span data-stu-id="2bb60-154">Value (the value that will be compared by the operand).</span></span>

   - <span data-ttu-id="2bb60-155">피연산자(비교 유형, 0은 "같음"을 의미)</span><span class="sxs-lookup"><span data-stu-id="2bb60-155">Operand (comparison type, 0 means "Equal").</span></span>

     <span data-ttu-id="2bb60-156">c.</span><span class="sxs-lookup"><span data-stu-id="2bb60-156">c.</span></span> <span data-ttu-id="2bb60-157">하나 이상의 측정값입니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-157">One or more measurements.</span></span>

2. <span data-ttu-id="2bb60-158">AJAX 호출을 통해 데이터 서비스에 쿼리를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-158">Send the query to Data Service via AJAX call.</span></span> <span data-ttu-id="2bb60-159">다음 요청 매개 변수를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-159">The following request parameters need to be provided:</span></span>

   <span data-ttu-id="2bb60-160">a.</span><span class="sxs-lookup"><span data-stu-id="2bb60-160">a.</span></span> <span data-ttu-id="2bb60-161">url(http://[ServerName]/QoEDataService/RunQuery)입니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-161">url (which should be http://[ServerName]/QoEDataService/RunQuery).</span></span>

   <span data-ttu-id="2bb60-162">b.</span><span class="sxs-lookup"><span data-stu-id="2bb60-162">b.</span></span> <span data-ttu-id="2bb60-163">데이터('query' 변수에 정의된 JSON 개체의 문자열 표현)입니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-163">data (this is the string representation of the JSON object defined in the 'query' variable).</span></span> <span data-ttu-id="2bb60-164">데이터 서비스는 쿼리 결과를 성공을 위해 콜백 함수의 매개 변수로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-164">Data Service will return the query results as a parameter of the call back function for success.</span></span>

   <span data-ttu-id="2bb60-165">c.</span><span class="sxs-lookup"><span data-stu-id="2bb60-165">c.</span></span> <span data-ttu-id="2bb60-166">type(QoEDataService의 경우 RunQuery는 'POST' 요청만 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-166">type (for QoEDataService, RunQuery only accepts 'POST' requests).</span></span>

   <span data-ttu-id="2bb60-167">d.</span><span class="sxs-lookup"><span data-stu-id="2bb60-167">d.</span></span> <span data-ttu-id="2bb60-168">비동기(AJAX 호출이 동기인지 비동기인지를 나타내는 플래그)</span><span class="sxs-lookup"><span data-stu-id="2bb60-168">async (a flag indicating whether the AJAX call should be synchronous or asynchronous).</span></span>

   <span data-ttu-id="2bb60-169">e.</span><span class="sxs-lookup"><span data-stu-id="2bb60-169">e.</span></span> <span data-ttu-id="2bb60-170">contentType("application/json"으로 해야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="2bb60-170">contentType (should be "application/json").</span></span>

   <span data-ttu-id="2bb60-171">f.</span><span class="sxs-lookup"><span data-stu-id="2bb60-171">f.</span></span> <span data-ttu-id="2bb60-172">success(AJAX 호출이 성공적으로 완료된 경우의 콜백 함수)입니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-172">success (call-back function for when the AJAX call finishes successfully).</span></span>

   <span data-ttu-id="2bb60-173">g.</span><span class="sxs-lookup"><span data-stu-id="2bb60-173">g.</span></span> <span data-ttu-id="2bb60-174">error(AJAX 호출이 실패할 때의 오류 처리 함수)입니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-174">error (error handling function for when AJAX call fails).</span></span>

3. <span data-ttu-id="2bb60-175">데이터를 HTML의 div 요소에 넣습니다(코드의 예제에서는 AJAX 요청이 성공적으로 완료된 후 익명 함수 호출을 통해 이 작업을 수행).</span><span class="sxs-lookup"><span data-stu-id="2bb60-175">Put data into div elements in the HTML (in the example in the code, this is done via the anonymous function call after the AJAX request is completed successfully).</span></span>

<span data-ttu-id="2bb60-176">JavaScript 코드를 HTML 페이지로 묶면 페이지에 그림에 표시된 보고서와 같은 보고서가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-176">Enclosing the JavaScript code into an HTML page, and the page will show a report like the one shown in the figure.</span></span> <span data-ttu-id="2bb60-177">전체 html은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-177">The full html is as follows:</span></span>

```javascript
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
</head>
<body>
    <script src="OpenSourceSoftware/Scripts/jquery-2.1.1.js"></script>

    <script>
        $($.fn.freeFormReport = function (queries, urlApi, presentation) {

            var query = {
                Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                Filters: [{
                    DataModelName: '[StartDate].[Month]',
                    Value: '[2015-02-01T00:00:00]',
                    Operand: 0
                }],
                Measurements:
                    [{ DataModelName: '[Measures].[Audio Good Streams JPDR Count]' },
                     { DataModelName: '[Measures].[Audio Poor Streams JPDR Count]' },]
            };            

            $.ajax({
                url: 'http://localhost/QoEDataService/RunQuery',
                data: JSON.stringify(query),
                type: 'POST',
                async: true,
                contentType: 'application/json;charset=utf-8',
                success: function (data) {
                    //This is the jQuery syntax for document.GetElementById()
                    $('#AudioGoodStreamsJPDRCount').html(data.DataResult[0][1]);
                    $('#AudioPoorStreamsJPDRCount').html(data.DataResult[0][2]);
                }
                error: function (error) {
                    alert('Error getting data, check that the data service is running and that the URL is correct.');
           }

            });
        });
    </script>
    <table border="1">
        <tr>
            <td></td>
            <td><div>Audio Good Streams JPDR Count</div></td>
            <td><div>Audio Poor Streams JPDR Count</div></td>
        </tr>
        <tr>
            <td>February</td>
            <td><div id="AudioGoodStreamsJPDRCount"></div></td>
            <td><div id="AudioPoorStreamsJPDRCount"></div></td>
        </tr>
    </table>
</body>
</html>
```

<span data-ttu-id="2bb60-178">지금까지 보고서는 매우 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-178">So far, the report is still very simple.</span></span> <span data-ttu-id="2bb60-179">사용자는 측정값, 차원 또는 필터를 더 추가하여 보고서를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-179">The user can add more measurements, dimensions, or filters to customize the report.</span></span> <span data-ttu-id="2bb60-180">예를 들어 AppSharing 불량 통화 비율을 표시하려는 경우 AppSharing과 관련한 새 측정값을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-180">For example, if you want to show AppSharing poor call percentage, then a new measurement regarding AppSharing needs to be added.</span></span> <span data-ttu-id="2bb60-181">모든 TCP 호출 v.s를 표시하려는 경우</span><span class="sxs-lookup"><span data-stu-id="2bb60-181">If you want to show all TCP calls v.s.</span></span> <span data-ttu-id="2bb60-182">UDP 통화는 교통 유형과 관련하여 새로운 차원을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-182">UDP calls, a new dimension regarding transportation type should be added.</span></span> <span data-ttu-id="2bb60-183">특정 건물 내의 불량 통화 수를 표시하려면 새 필터를 추가하여 해당 건물과의 통화를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-183">If you want to show the number of poor calls within a specific building, then a new filter should be added to select the calls to and from that building.</span></span>

 <span data-ttu-id="2bb60-184">**예제 2: 보고서 정의 샘플**</span><span class="sxs-lookup"><span data-stu-id="2bb60-184">**Example 2: Report definition sample**</span></span>

<span data-ttu-id="2bb60-185">사용자가 쿼리를 작성할 때 측정/차원/필터의 전체 목록과 해당 값을 작성하는 방법을 알아내기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-185">It might be difficult for someone to figure out how to write the full list of measurements/dimensions/filters and their corresponding values when constructing a query.</span></span> <span data-ttu-id="2bb60-186">이 경우 포털로 이동하여 보고서 편집기를 사용하여 보고서를 작성한 다음 보고서 정의의 JSON 문자열을 본 다음 정의를 사용자 지정 보고서에 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-186">In this case, you can go to the Portal, build a report using the report editor, and view the JSON string of the report definition, and then copy the definition into a custom report.</span></span> 

<span data-ttu-id="2bb60-187">이 예제에서는 사용자가 기존 보고서 집합(또는 보고서)의 ID를 입력하고 웹 페이지에 보고서 집합 또는 보고서의 정의를 표시하는 그림에 표시된 웹 페이지와 같은 웹 페이지를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-187">In this example, we will create a web page like the one shown in the figure where a user can enter the ID of any existing report set (or report) and show the definition of the report set or report on the web page.</span></span> <span data-ttu-id="2bb60-188">그런 다음 사용자는 예제 1에 표시된 JSON 문자열과 유사한 코드에 각 보고서의 JSON 문자열을 연결하고 사용자가 원하는 사용자 지정 보고서를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-188">The user can then plug the JSON string of each report into code similar to the one shown in Example 1 and construct any customized report the user desires.</span></span> 

![CQD 예제](../../media/01c45c23-c4d2-47b8-819f-0888cf71260f.png)

<span data-ttu-id="2bb60-190">보고서 정의 뷰어 도구를 만들하려면 원하는 모든 보고서 집합의 정의에 대한 JSON 문자열 표현을 검색하기 위해 리포지토리 서비스에 호출을 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-190">To create the report definition viewer tool, we need to send calls to Repository Service to retrieve the JSON string representations of the definitions of every report-set we want.</span></span> <span data-ttu-id="2bb60-191">리포지토리 API는 주어진 보고서 집합 ID에 따라 보고서 집합 정의를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-191">The Repository API will return report-set definition based on a given report set ID.</span></span> 

<span data-ttu-id="2bb60-192">빠른 예제는 다음과 같습니다. 코드에는 리포지토리 서비스에 쿼리를 전송하여 해당 식별자를 기반으로 리포지토리 항목의 내용을 구하는 간단한 예제인 블록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-192">A quick example is as follows, the code contains a block that is a simple example to send a query to the Repository service to get the contents of a repository item based on its identifier.</span></span> <span data-ttu-id="2bb60-193">또한 코드의 다음 부분(processReportSetData 메서드)은 AJAX 호출을 전송하여 보고서 집합 내의 각 보고서에 대한 정의를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-193">And the next portion of code (processReportSetData method) is sending AJAX calls to get the definition of each report within that report set.</span></span> <span data-ttu-id="2bb60-194">CQD 웹 포털의 ID는 보고서 집합의 ID이기 때문에 AJAX 호출은 보고서 집합 항목을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-194">Since the ID in the CQD web portal is the ID of a report set, the AJAX call will return a report set item.</span></span> <span data-ttu-id="2bb60-195">리포지토리 API 및 특히 GetItems에 대한 자세한 내용은 항목 항목에서 [찾을 수 있습니다.](get-items.md)</span><span class="sxs-lookup"><span data-stu-id="2bb60-195">More detail on the Repository API and specifically, GetItems, can be found in the [Get Items](get-items.md).</span></span> 

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <meta http-equiv='cache-control' content='no-cache'>
    <meta http-equiv='expires' content='0'>
    <meta http-equiv='pragma' content='no-cache'>
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta http-equiv="x-content-type-options" content="nosniff">
    <title>CQD Report definition viewer</title>
</head>
<body>    
    <div style="font-size:32pt">CQD Report definition viewer</div>
        <p>ReportSet Id: <input id="reportSetId" /></p>
        <button onclick='loadReportSet()'>Load</button>
        <div id="Report"></div>
    <!-- Third party Libraries -->
    <script src="OpenSourceSoftware/Scripts/jquery-2.1.1.js"></script>

    <script>
        var urlRepositoryApi = 'http://localhost/QoERepositoryService/repository/item/';

        var loadReportSet = function ()
        {
            var reportSetId = document.getElementById('reportSetId').value;

            $.ajax({
                url: urlRepositoryApi + reportSetId,
                data: '',
                type: 'GET',
                async: false,
                contentType: 'application/json;charset=utf-8',
                success: function (data) {
                    var reportSetDiv = document.getElementById('Report');
                    reportSetDiv.innerHTML = '';
                    processReportSetData(reportSetDiv, data);
                },
                error: function (error) {
                    alert('Error getting Report, check that the qoe data service is running and url is correct.');
                }
            });
        };

        var processReportSetData = function (divReportSet, reportSetDef) {
             //show the report set definition like Title, Description, etc
            showReportSetDefinition(divReportSet, reportSetDef);

            //for each Report in the Reportset, get the Report definition from the Repository Service
            for (var i = 0; i < reportSetDef.subItemIds.length; i++)
            {
                //the reportId is in the subItemIds array.  This is not shown in the CQD UI at all
                var reportId = reportSetDef.subItemIds[i];

                var divReport = document.createElement('div');
                divReport.style.margin = '12px';                
                divReportSet.appendChild(divReport);

                //retrieve the report definition with the reportId
                $.ajax({
                    url: urlRepositoryApi + reportId,
                    data: '',
                    type: 'GET',
                    async: false,
                    contentType: 'application/json;charset=utf-8',
                    success: function (reportData) {
                        processReportData(divReport, reportData, reportId);
                    },
                    error: function (error) {
                        alert('Error getting Report ' + reportId.toString() + ', check that the qoe data service is running and url is correct.');
                    }
                });
            }
        };

        //helper function to render the ReportSet definition
        var showReportSetDefinition = function (divReportSet, reportSetDef) {
            var div = document.createElement('div');
            ReportSetDefinition = reportSetDef.content;
            txt = document.createTextNode(ReportSetDefinition);
            div.style.margin = '12px';
            div.appendChild(txt);
            divReportSet.appendChild(div);
        };

        //show the report definition
        var processReportData = function (divReport, reportData, itemId) {
            if (divReport != undefined &amp;&amp; reportData.content != undefined) {
                var Report = JSON.parse(reportData.content);

                var divReportId = document.createElement('div');
                var subItemId = reportData.subItemIds.length > 0 ? reportData.subItemIds[0].toString() : 'none';
                divReportId.innerHTML = 'ItemId: ' + itemId.toString() + ' (' + Report.Title + ') [subItemId:' + subItemId + ']';
                divReport.appendChild(divReportId);

                var divReportDef = document.createElement('div');
                txt = document.createTextNode(JSON.stringify(Report));
                divReportDef.style.margin = '12px';
                divReportDef.appendChild(txt);                            
                divReport.appendChild(divReportDef);
            }
        };
    </script>
</body>
</html>
```

<span data-ttu-id="2bb60-196">위의 결과로 초기 방문 시 보고서 정의가 없는 그림과 같은 웹 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-196">The above will result in a web page like the one in the figure (without the report definition upon initial visit).</span></span> <span data-ttu-id="2bb60-197">CQD 포털에서 보고서 집합 ID를 다운로드합니다(예: CQD 포털 URL에서 '/#/' 로그인 후).</span><span class="sxs-lookup"><span data-stu-id="2bb60-197">Get the report set ID from CQD portal (it is after '/#/' sign in CQD portal URL (E.g.</span></span> <span data-ttu-id="2bb60-198">첫 번째 그림에서 보고서 집합 ID는 3024입니다. 이 보고서 집합 ID를 이 웹 페이지의 입력 섹션에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-198">in the first figure the report set ID is 3024), and put this report set ID into the input section of this web page.</span></span> <span data-ttu-id="2bb60-199">"로드" 단추를 누르고 보고서 집합의 전체 정의(측정값, 차원, 필터 목록)를 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-199">Press the "load" button and see the full definition (measurements, dimensions, filters lists) of the report set.</span></span>

<span data-ttu-id="2bb60-200">요약하면 보고서/보고서 집합의 전체 정의를 빠르게 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-200">In summary, in order to quickly get the full definition of a report/report set.</span></span> <span data-ttu-id="2bb60-201">그 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-201">The steps are:</span></span>

1. <span data-ttu-id="2bb60-202">포털로 이동한 후 쿼리 편집기를 사용하여 보고서를 사용자 지정합니다(보고서 위에 있는 "편집" 단추를 클릭하여 측정값/차원/필터를 편집, 추가, 제거한 다음 보고서를 저장).</span><span class="sxs-lookup"><span data-stu-id="2bb60-202">Go to the Portal and use the query editor to customize a report (click the "Edit" button above a report to edit, add, remove measurements/dimensions/filters, and then save the report).</span></span>

2. <span data-ttu-id="2bb60-203">URL에서 보고서 집합 ID('/#/' 로그인 후의 정수)를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-203">Get the report set ID from URL (the integer after '/#/' sign in URL).</span></span>

3. <span data-ttu-id="2bb60-204">예제 2에서 만든 이 보고서 정의 웹 페이지를 시작하고 보고서 집합 ID를 입력하고 데이터 API 호출에 사용할 보고서 집합의 전체 정의를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-204">Launch this Report Definition web page created in Example 2, and enter the report set ID and retrieve the full definition of a report set (to use in Data API calls).</span></span>

   <span data-ttu-id="2bb60-205">**예제 3: Scorecard 샘플**</span><span class="sxs-lookup"><span data-stu-id="2bb60-205">**Example 3: Scorecard sample**</span></span>

<span data-ttu-id="2bb60-206">좀 더 복잡한 작업에 대한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-206">Time for a more complicated task.</span></span> <span data-ttu-id="2bb60-207">그림과 같은 웹 페이지를 만들면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="2bb60-207">What if we want to create a web page like the figure?</span></span> <span data-ttu-id="2bb60-208">많은 양의 데이터를 처리할 수 있도록 예제 1(예제 2에서 생성된 웹 페이지를 사용하여 보고서의 전체 정의를 검색)을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-208">We need to update Example 1, (with the help of the web page generated in Example 2 to retrieve the full definition of any report) so that we can handle larger amount of data.</span></span>

<span data-ttu-id="2bb60-209">이 경우 측정값 및 차원 목록을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-209">In this case, we need to update the measurement and dimension list.</span></span> <span data-ttu-id="2bb60-210">측정값 및/또는 차원을 추가/편집하는 방법을 알아낼 수 있는 방법은 예제 2의 지침을 따르고 전체 측정값 및 차원 목록을 포함하여 전체 보고서 정의를 검색하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-210">The way to figure out how to add/edit a measurement and/or a dimension is to follow the instructions in Example 2, and retrieve the full report definition, including the full measurement and dimension lists.</span></span> <span data-ttu-id="2bb60-211">전체 보고서 정의를 예제 코드에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-211">Plug the full report definition into the sample code.</span></span> 

<span data-ttu-id="2bb60-212">예제 1에 제공된 예제에서 그림의 점수 기록표 페이지로 이동하는 자세한 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-212">Here are the detailed steps to get to the scorecard page in the figure from the sample provided in Example 1:</span></span>

1. <span data-ttu-id="2bb60-213">'query' 변수의 측정값을 다음 변수에서  `[Measures].[Audio Good Streams JPDR Count]` `[Measures].[Audio Poor Streams JPDR Count]` `[Measures].[AudioPoorJPDRPercentage]` 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-213">Update Measurements in the 'query' variable from  `[Measures].[Audio Good Streams JPDR Count]` and `[Measures].[Audio Poor Streams JPDR Count]` to `[Measures].[AudioPoorJPDRPercentage]`.</span></span> 

2. <span data-ttu-id="2bb60-214">필터를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-214">Update the filters.</span></span> <span data-ttu-id="2bb60-215">예제 1의 필터에 대한 JSON 데이터에는 차원에 설정된 필터가 하나  `[StartDate].[Month]` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-215">The JSON data for Filters in Example 1 has one filter, which is set on the dimension  `[StartDate].[Month]`.</span></span> <span data-ttu-id="2bb60-216">Filters는 JSON 배열이기 때문에 필터 목록에 차원을 더 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-216">Since Filters is a JSON array, additional dimensions can be added to the list of filters.</span></span> <span data-ttu-id="2bb60-217">예를 들어 "currentMonth"에 대한 유선 호출 내부에서 서버 클라이언트를 얻습니다. 다음과 같은 필터가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-217">For example, to get the server-client inside wired calls for the "currentMonth", we should have the following filters:</span></span>

   ```javascript
   Filters: [
     { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
    {
        "DataModelName": "[Scenarios].[ScenarioPair]",
         "Caption": " Server-Inside-wired,Client-Inside-wired",
         "Value": "[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
         "Operand": 0,
         "UnionGroup": ""
     },

     { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
   ],
   ```

   <span data-ttu-id="2bb60-218">여기서  `[Scenarios].[ScenarioPair]` 차원은 다음과 같게 `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-218">Here the dimension  `[Scenarios].[ScenarioPair]` is set to equal `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`.</span></span> <span data-ttu-id="2bb60-219">보고서 만들기를 단순화하기 위해 만든 특수  `[Scenario.][ScenarioPair]` 차원입니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-219">The  `[Scenario.][ScenarioPair]` is a special dimension created to simplify report creation.</span></span> <span data-ttu-id="2bb60-220">에 해당하는 6개의 값이 `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-220">It has six values corresponding to `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]`.</span></span> <span data-ttu-id="2bb60-221">따라서 6개 필터를 조합하여 시나리오를 정의하는 대신 필터 1개만 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-221">So instead of using a combination of 6 filters to define a scenario, we only need to use 1 filter.</span></span> <span data-ttu-id="2bb60-222">이 예제에서 값은  `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` "Server-Client-Inside Wired"의 정확한 정의인 서버, 두 번째는 서버가 아니고, 첫 번째는 내부, 두 번째 연결 유형은 내부, 두 번째 연결 유형은 유선인 시나리오로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-222">In our example, the value  `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` translates to the scenario where: first is server, second is not server, first is inside, second is inside, first connection type is wired, and second connection type is wired, which is the exact definition of "Server-Client-Inside Wired".</span></span>

3. <span data-ttu-id="2bb60-223">시나리오당 하나의 필터 집합을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-223">Create one filter set per scenario.</span></span> <span data-ttu-id="2bb60-224">그림에서 각 행은 다른 필터가 될 다른 시나리오를 나타내며 차원과 측정값은 동일하게 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-224">Each row in the scorecard, in the figure, represents a different scenario, which will be a different filter (while the dimensions and measurements stay the same).</span></span> 

4. <span data-ttu-id="2bb60-225">AJAX 호출의 결과를 구문 분석하여 테이블의 올바른 위치에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-225">Parse the results from the AJAX calls and place them in the correct position of the table.</span></span> <span data-ttu-id="2bb60-226">이는 대부분 HTML 및 JavaScript 조작이기 때문에 여기에서는 세부 정보로 이동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-226">Since this is mostly HTML and JavaScript manipulation, we will not go into the details here.</span></span> <span data-ttu-id="2bb60-227">대신 부록 A에 코드가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-227">Instead, the code is provided in Appendix A.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="2bb60-228">CORS(Origin Cross-Origin Resource Sharing)를 사용하도록 설정하면 요청된 리소스에 "'액세스 제어-허용-원점' 헤더가 없는 경우" 같은 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-228">If Cross-Origin Resource Sharing (CORS) is enabled, users may encounter errors like "No 'Access-Control-Allow-Origin' header is present on the requested resource.</span></span> <span data-ttu-id="2bb60-229">따라서 원점 'null'은 액세스가 허용되지 않습니다."</span><span class="sxs-lookup"><span data-stu-id="2bb60-229">Origin 'null' is therefore not allowed access".</span></span> <span data-ttu-id="2bb60-230">이 문제를 해결하려면 HTML 파일을 포털이 설치된 폴더 아래에 배치합니다(기본적으로 . `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)`</span><span class="sxs-lookup"><span data-stu-id="2bb60-230">To resolve the issue, place the HTML file under the folder where the Portal is installed (by default, it should be `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)`.</span></span> <span data-ttu-id="2bb60-231">그런 다음 URL을 사용하여 모든 브라우저를 통해 html에  `http://<servername>/cqd/<html_file_name>` 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="2bb60-231">Then access the html through any browser with the URL  `http://<servername>/cqd/<html_file_name>`.</span></span> <span data-ttu-id="2bb60-232">(로컬 CQD 대시보드의 기본 URL은  `http://<servername>/cqd.` )</span><span class="sxs-lookup"><span data-stu-id="2bb60-232">(The default URL for local CQD dashboard is  `http://<servername>/cqd.`)</span></span> 

### <a name="appendix-a"></a><span data-ttu-id="2bb60-233">부록 A</span><span class="sxs-lookup"><span data-stu-id="2bb60-233">Appendix A</span></span>

<span data-ttu-id="2bb60-234">예제 3에 대한 HTML 코드(Scorecard 샘플):</span><span class="sxs-lookup"><span data-stu-id="2bb60-234">HTML code for Example 3 (Scorecard sample):</span></span>

```html
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
    <meta charset="utf-8" />
    <meta http-equiv='cache-control' content='no-cache'>
    <meta http-equiv='expires' content='0'>
    <meta http-equiv='pragma' content='no-cache'>
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <title>Scoreboard Sample</title>

    <style>
        .row {
            margin-right: -15px;
            margin-left: -15px;
            display: table-row;
        }
        .col-md-3 {
            width: 25%;
            display: table-cell;
        }
        .col-md-2 {
            width: 16.66666667%;
            display: table-cell;
        }
        .col-md-1 {
            width: 8.33333333%;
            display: table-cell;
        }

    </style>
</head>
<body>    

    <!-- Third party Libraries -->
    <script src="OpenSourceSoftware/Scripts/jquery-2.1.1.js"></script>

    <table id="ScoreCardTable" style="margin:100px">
        <tr>
            <td width="250px" style="text-align: center; font-size: 24px; font-family: 'Segoe UI'; font-weight: lighter; color: white; background-color: #505050">
                <div style="margin:10px">Scoreboard Sample</div>
            </td>
            <td width="1200px">
                <div style="margin:10px;background-color:#D9D9D9" >
                    <div class="row" id="Header" style="font-size:24px;font-family:'Segoe UI';font-weight:lighter;color:white;background-color:#505050">
                        <div class="col-md-3">Poor Call %</div>
                        <div class="col-md-1">Month1</div>
                        <div class="col-md-1">Month2</div>
                        <div class="col-md-1">Month3</div>
                        <div class="col-md-1">Month4</div>
                        <div class="col-md-1">Month5</div>
                        <div class="col-md-1">Month6</div>
                    </div>                    
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Wired</div></div>
                    <div class="row" id="SS"><div class="col-md-3">Server-Server</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SWI"><div class="col-md-3">Server-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SWO"><div class="col-md-3">Server-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WWI"><div class="col-md-3">Client-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WIWO"><div class="col-md-3">Client-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Wireless</div></div>
                    <div class="row" id="SWFI"><div class="col-md-3">Server-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SWFO"><div class="col-md-3">Server-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WFIWFI"><div class="col-md-3">Client-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WFOWFO"><div class="col-md-3">Client-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Mobile/Broadband</div></div>
                    <div class="row" id="SMP"><div class="col-md-3">Server-MobilePhone</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SMBB"><div class="col-md-3">Server-MobileBroadBand</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Lync Web App</div></div>
                    <div class="row" id="SLWA"><div class="col-md-3">Server-Client (inside &amp; outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                </div>
            </td>
        </tr>
        <tr>
            <td><br /></td>
        </tr>
    </table>

    <script>

        $(function () {
            var month_names_short = ['NAM', 'Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'];
            var currentMonth = '2015-3';

            //update the header with the month names
            var row = document.getElementById('Header');
            var numMonthsToShow = 6;
            for (var m = numMonthsToShow-1; m >= 0; m--) {
                var dateSplit = currentMonth.split('-');
                var monthInt = parseInt(dateSplit[1]);
                var yearInt = parseInt(dateSplit[0]);
                monthInt = monthInt - m;
                if (monthInt < 1)
                {
                    monthInt += 12;
                    yearInt--;
                }
                row.children[numMonthsToShow-m].innerHTML = month_names_short[monthInt];
            }

            var queries = [
            {
                Label: "Server-Server",
                ID: "SS",
                Query:
                {
                  Dimensions: [{ DataModelName: '[StartDate].[Month]'}],
                  Filters: [
                      {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": " Server-Inside-wired,Server-Inside-wired",
                          "Value": "[1]&amp;[1]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                      },
                      { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                      { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: ""}
                  ],
                  Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]'}],
                  Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                 }
            },
            {
                Label: "Server-Client (inside)",
                ID: "SWI",
                Query:
                {
                  Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                  Filters: [
                      {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": " Server-Inside-wired,Client-Inside-wired",
                          "Value": "[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                      },
                      { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                      { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                  ],
                  Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                  Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-Client (outside)",
                ID: "SWO",
                Query:
                {
                  Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                  Filters: [
                      {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": " Server-Inside-wired,Client-Outside-wired",
                          "Value": "[1]&amp;[0]&amp;[1]&amp;[0]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                      },
                      { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                      { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                  ],
                  Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                  Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                 }
            },
            {
                Label: "Client-Client (inside)",
                ID: "WWI",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                            "DataModelName": "[Scenarios].[ScenarioPair]",
                            "Caption": " Client-Inside-wired,Client-Inside-wired",
                            "Value": "[0]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
                            "Operand": 0,
                            "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            }
            ,
            {
                Label: "Client-Client (outside)",
                ID: "WIWO",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": "Client-Outside-Wired,Client-Outside-Wired",
                          "Value": "[0]&amp;[0]&amp;[0]&amp;[0]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-Client (inside)",
                ID: "SWFI",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                            "DataModelName": "[Scenarios].[ScenarioPair]",
                            "Caption": " Server-Inside-wired,Client-Inside-wifi",
                            "Value": "[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wifi]",
                            "Operand": 0,
                            "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-Client (outside)",
                ID: "SWFO",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                         {
                             "DataModelName": "[Scenarios].[ScenarioPair]",
                             "Caption": " Server-Inside-wired,Client-Outside-wifi",
                             "Value": "[1]&amp;[0]&amp;[1]&amp;[0]&amp;[Wired]&amp;[Wifi]",
                             "Operand": 0,
                             "UnionGroup": ""
                         },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Client-Client (inside)",
                ID: "WFIWFI",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                            "DataModelName": "[Scenarios].[ScenarioPair]",
                            "Caption": " Client-Inside-Wifi,Client-Inside-Wifi",
                            "Value": "[0]&amp;[0]&amp;[1]&amp;[1]&amp;[Wifi]&amp;[Wifi]",
                            "Operand": 0,
                            "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Client-Client (outside)",
                ID: "WFOWFO",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": "Client-Outside-Wifi,Client-Outside-Wifi",
                          "Value": "[0]&amp;[0]&amp;[0]&amp;[0]&amp;[Wifi]&amp;[Wifi]",
                          "Operand": 0,
                          "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-MobilePhone",
                ID: "SMP",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {"DataModelName": "[First Is Server].[Agent]","Caption": "Server","Value": "[1]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[Second User Agent].[User Agent Type]","Caption": "AndroidLync | iPhoneLync | WPLync","Value": "[AndroidLync],[iPhoneLync],[WPLync]","Operand": 0,"UnionGroup": ""},
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-MobileBroadBand",
                ID: "SMBB",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {"DataModelName": "[Second Network Connection Type].[Network Connection Detail]","Caption": "MobileBB","Value": "[MobileBB]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[First Is Server].[Agent]","Caption": "Server","Value": "[1]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[Second Is Server].[Agent]","Caption": "Client ","Value": "[0]","Operand": 0,"UnionGroup": ""},
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 }                       
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-LWA",
                ID: "SLWA",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {"DataModelName": "[First Is Server].[Agent]","Caption": "Server","Value": "[1]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[Second User Agent].[User Agent Type]","Caption": "LWA","Value": "[LWA]","Operand": 0,"UnionGroup": ""},
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 }                       
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            }

            ];

            //get the overall corpnet data
            for (var i = 0; i < queries.length; i++) {
                $.ajax({

                    url: 'http://localhost/QoEDataService/RunQuery',
                    data: JSON.stringify(queries[i].Query),
                    type: 'POST',
                    async: false,
                    withCredentials: true,
                    contentType: 'application/json;charset=utf-8',
                    success: function (data) {

                        //find the table row corresponding to the name of this query
                        var row = document.getElementById(queries[i].ID);

                        //update the values for each month
                        for (var m = 0; m < data.DataResult.length; m++)
                        {
                            row.children[m + 1].innerHTML = data.DataResult[m][1].toFixed(2).toString();
                        }

                    },
                    error: function (error) {
                        var row = document.getElementById(queries[i].ID);
                        row.children[1].innerHTML = 'error';
                    }
                });
            }
        });
    </script>
</body>
</html>
```
