---
title: CQD 데이터를 사용 하 여 Power BI에서 Microsoft 팀 사용률 보기
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: 팀 활용 Power BI 보고서를 사용 하 여 조직의 Microsoft 팀 사용량을 추적 합니다.
ms.openlocfilehash: 7eb39d043fafae0464ac52aa1e328c24b22d73f3
ms.sourcegitcommit: 86366b66b15870fe83cbb76e1ae7aa1ce9b3bfe1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2020
ms.locfileid: "42858763"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a><span data-ttu-id="a67eb-103">CQD 데이터를 사용 하 여 Power BI에서 Microsoft 팀 사용률 보기</span><span class="sxs-lookup"><span data-stu-id="a67eb-103">View Microsoft Teams utilization in Power BI using CQD data</span></span>

<span data-ttu-id="a67eb-104">2020 년 3 월에 새로 추가 된, [CQD 용으로 다운로드할 수 있는 POWER BI 쿼리 서식 파일](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)에 팀 사용률 보고서가 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-104">New in March 2020, we've added a Teams Utilization report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 

<span data-ttu-id="a67eb-105">이 새로운 팀 사용률 보고서를 사용 하 여 사용자가 Microsoft 팀을 사용 하는 방법과 그 정도를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-105">This new Teams Utilization reports lets you see how (and how much) your users are using Microsoft Teams.</span></span> <span data-ttu-id="a67eb-106">이러한 보고서는 관리자와 비즈니스 리더가 모두이 데이터로 빠르게 이동할 수 있는 중앙 집중화 된 위치를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-106">These reports are intended to be a centralized location that both administrators and business leaders can quickly go to for this data.</span></span>

<span data-ttu-id="a67eb-107">팀 활용 Power BI 보고서는 두 가지 기본 보고서 ( **[통화 수 요약](#call-count-summary-report)** 및 **[오디오 시간 요약)](#audio-minutes-summary-report)** 로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-107">The Teams Utilization Power BI report consists of two primary reports: **[Call Count Summary](#call-count-summary-report)** and **[Audio Minutes Summary](#audio-minutes-summary-report)**.</span></span> <span data-ttu-id="a67eb-108">사용자가 아래 설명에 명시 된 드릴 다운 보고서를 활용할 때 [일일 사용량](#daily-usage) 및 [지역 오디오 세부 정보](#regional-audio-details) 보고서가 재생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-108">The [Daily Usage](#daily-usage) and [Regional Audio Details](#regional-audio-details) reports come into play when a user takes advantage of the drill-down reports, noted in the descriptions below.</span></span>

> [!NOTE]
> <span data-ttu-id="a67eb-109">지역 및 네트워크 필터링 기능을 제공 하려면 빌드 및 서브넷 데이터를 채워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-109">Building and subnet data must be populated to provide regional and network filtering capabilities.</span></span>

## <a name="call-count-summary-report"></a><span data-ttu-id="a67eb-110">통화 수 요약 보고서</span><span class="sxs-lookup"><span data-stu-id="a67eb-110">Call Count Summary Report</span></span>

<span data-ttu-id="a67eb-111">기본 페이지 (통화 수 요약)는 섹션 제목에 명시 된 대로 지난 30 일과 90 일 동안 오디오, 비디오 및 화면 공유 세션의 수를 즉시 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-111">The main page (Call Count Summary) immediately provides the number of audio, video and screen sharing sessions over the last 30 and 90 days as noted in the section title.</span></span> <span data-ttu-id="a67eb-112">처음에는 조직에 대 한 데이터가 전체적으로 표시 되며 페이지의 왼쪽에 있는 슬라이서 드롭다운 옵션을 사용 하 여 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-112">The data initially displayed is for the organization as a whole and can be filtered using the slicer dropdown options on the left side of the page.</span></span>

![스크린샷: 전화 국가 요약 보고서](media/CQD-teams-utilization-report1.png)

1. <span data-ttu-id="a67eb-114">슬라이서 드롭다운의 오른쪽에 미디어 유형별 통화 수가 지난 30 일 동안 내부/외부 보기로 분류 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-114">To the right of the slicer dropdowns, the number of calls by media type is broken down to an internal/external view over the past thirty days.</span></span> <span data-ttu-id="a67eb-115">현재 전역 환경을 고려 하 여 외부 조직 위치에서 발생 하는 더 많은 호출을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-115">We can see through the above screenshot that there are more calls happening from outside organizational locations, which makes sense considering the current global environment.</span></span>
  <span data-ttu-id="a67eb-116">![스크린샷: 전화 국가 요약 보고서](media/CQD-teams-utilization-report2.png)</span><span class="sxs-lookup"><span data-stu-id="a67eb-116">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report2.png)</span></span>

1. <span data-ttu-id="a67eb-117">미디어 유형 개수 상자 오른쪽에는 지난 90 일간의 미디어 유형별로 월간 통화 수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-117">To the right of the media type count box, we have the Monthly Call Count by Media Type for the last 90 days.</span></span> <span data-ttu-id="a67eb-118">각 열과 미디어 유형을 마우스로 가리키면 사용 추세 정보를 제공 하 여 이전 월 또는 현재 달의 수를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-118">Each column and media type can be hovered over to display the count for a previous month or the current month to date, providing usage trend information.</span></span>
  <span data-ttu-id="a67eb-119">![스크린샷: 전화 국가 요약 보고서](media/CQD-teams-utilization-report3.png)</span><span class="sxs-lookup"><span data-stu-id="a67eb-119">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report3.png)</span></span>

1. <span data-ttu-id="a67eb-120">90 일 그래프에서는 가운데 그래프가 작동 하지만 지난 30 일간의 일일 사용량 보기를 제공 하 고 사용자가 특정 날짜에 대 한 세부 정보를 마우스 오른쪽 단추로 클릭 하 고 드릴 다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-120">The middle graph functions as the 90-day graph does, however it provides a daily usage view for the past 30 days and allows a user to right click and drill down into details for a specific day.</span></span>
  <span data-ttu-id="a67eb-121">![스크린샷: 전화 국가 요약 보고서](media/CQD-teams-utilization-report4.png)</span><span class="sxs-lookup"><span data-stu-id="a67eb-121">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report4.png)</span></span>

<span data-ttu-id="a67eb-122">페이지의 왼쪽 아래 섹션에서 지난 해의 각 미디어 유형에 대 한 총 값을 제공 하는 테이블을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-122">On the bottom left section of the page, you'll find a table providing total values for each media type over the past year.</span></span> 
    <span data-ttu-id="a67eb-123">![스크린샷: 전화 국가 요약 보고서](media/CQD-teams-utilization-report5.png)</span><span class="sxs-lookup"><span data-stu-id="a67eb-123">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report5.png)</span></span>
  
<span data-ttu-id="a67eb-124">이 표에는 국가별 데이터 분석 결과를 볼 수 있는 드릴 다운도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-124">The table also has an available drill down where you can see a regional data breakdown.</span></span>
    <span data-ttu-id="a67eb-125">![스크린샷: 전화 국가 요약 보고서](media/CQD-teams-utilization-report6.png)</span><span class="sxs-lookup"><span data-stu-id="a67eb-125">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report6.png)</span></span>

<span data-ttu-id="a67eb-126">가로 막대형 차트는 지난 30 일간의 사용 (호출/스트림)이 가장 많은 클라이언트를 표 오른쪽에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-126">To the right of the table, a bar chart shows clients with the most use (calls/streams) for the past 30 days.</span></span>
   <span data-ttu-id="a67eb-127">![스크린샷: 전화 국가 요약 보고서](media/CQD-teams-utilization-report7.png)</span><span class="sxs-lookup"><span data-stu-id="a67eb-127">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report7.png)</span></span>


<span data-ttu-id="a67eb-128">이 페이지의 마지막 차트 집합은 각 미디어 유형을 개별적으로 표시 하며, 회의 및 P2P 사용을 보여 주는 분석을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-128">The last set of charts for this page show each media type individually, with a breakdown showing conference and P2P usage.</span></span> <span data-ttu-id="a67eb-129">아래 차트는 P2P에 비해 회의 사용량 수가 매우 높다는 것을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-129">The charts below show that there is a significantly higher number of conference usage as compared to P2P.</span></span>
  <span data-ttu-id="a67eb-130">![스크린샷: 전화 국가 요약 보고서](media/CQD-teams-utilization-report8.png)</span><span class="sxs-lookup"><span data-stu-id="a67eb-130">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report8.png)</span></span>

## <a name="audio-minutes-summary-report"></a><span data-ttu-id="a67eb-131">오디오 의사록 요약 보고서</span><span class="sxs-lookup"><span data-stu-id="a67eb-131">Audio Minutes Summary Report</span></span>

<span data-ttu-id="a67eb-132">오디오 의사록 사용 보고서에서 몇 가지 다른 보기를 통해 총 통화 시간 사용을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-132">On the Audio Minutes usage report, the total minute usage is provided through a few different views.</span></span> 

<span data-ttu-id="a67eb-133">텍스트 상자를 사용 하기 쉽도록 슬라이서 옆에 30 일 사용 현황 요약이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-133">We have the thirty-day usage summary shown next to the slicers as easy to consume text boxes.</span></span> <span data-ttu-id="a67eb-134">맨 위 번호에는 30 일의 합계가 표시 되 고 그 아래에는 내부 및 외부 분석.</span><span class="sxs-lookup"><span data-stu-id="a67eb-134">The top number shows the thirty-day total, with internal and external breakdowns below that.</span></span>

![스크린샷: 전화 국가 요약 보고서](media/CQD-teams-utilization-report9.png)

<span data-ttu-id="a67eb-136">오른쪽 위 막대 그래프는 회의 오디오 사용에 대 한 yearlong 보기를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-136">The top right bar graph provides a yearlong view of conference audio usage.</span></span> <span data-ttu-id="a67eb-137">월을 마우스로 가리켜 회의 오디오 의사록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-137">Hover over the month to show the conference audio minutes.</span></span>

<span data-ttu-id="a67eb-138">P2P 및 컨퍼런스 오디오의 차이를 표시 하기 위해 아래쪽 왼쪽 차트는 지난 해의 모든 오디오를 가져와 두 형식 사이에서 분리 합니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-138">To show the difference in P2P and conference audio, the bottom left chart takes all audio for the past year and breaks it up between the two types.</span></span>

<span data-ttu-id="a67eb-139">![스크린샷: 전화 통화 페이지의](media/CQD-teams-utilization-report10.png) 마지막 차트에는 전역 지도 오버레이에 대 한 오디오 분 사용량이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-139">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report10.png) The last chart for the Audio minutes page shows audio minute usage on a global map overlay.</span></span> <span data-ttu-id="a67eb-140">이 차트는 빌드 및 서브넷 데이터를 테 넌 트에 업로드 하는 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-140">This chart will only work if building and subnet data is uploaded to the tenant.</span></span> <span data-ttu-id="a67eb-141">지도에 있는 원형 차트 오버레이는 드릴 다운할 수 있으며 그 후에는 국가별 오디오 사용을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-141">The pie chart overlay on the map can be drilled into, subsequently providing regional audio usage.</span></span>

![스크린샷: 전화 국가 요약 보고서](media/CQD-teams-utilization-report11.png)

## <a name="drill-through-capabilities"></a><span data-ttu-id="a67eb-143">드릴스루 기능</span><span class="sxs-lookup"><span data-stu-id="a67eb-143">Drill-through capabilities</span></span>

<span data-ttu-id="a67eb-144">앞에서 언급 한 것 처럼 사용자가 매일 및 지역별 사용 현황 보고서에 드릴스루할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-144">As previously noted, users can drill into the daily and regional usage reports.</span></span>

### <a name="daily-usage"></a><span data-ttu-id="a67eb-145">일일 사용량</span><span class="sxs-lookup"><span data-stu-id="a67eb-145">Daily Usage</span></span>

<span data-ttu-id="a67eb-146">일일 사용량 보고서를 사용 하면 관리자가 하루 중의 기간을 통해 피크 사용량을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-146">The Daily Usage report allows an administrator to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="a67eb-147">사용 외에도, 그 날에 대 한 전반적인 사용자 정서 및 피드백을 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-147">In addition to usage, we are also able to capture overall user sentiment and feedback for that day.</span></span>

![스크린샷: 전화 국가 요약 보고서](media/CQD-teams-utilization-report12.png)

<span data-ttu-id="a67eb-149">이 데이터를 사용 하 여 사용량이 많은 시간에 문제가 있는 영역을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-149">This data can be used to identify regions having problems during peak consumption times.</span></span>

1.  <span data-ttu-id="a67eb-150">호출 횟수 요약 페이지에서 특정 날짜에 대 한 드릴 진행</span><span class="sxs-lookup"><span data-stu-id="a67eb-150">On the Call Count Summary page, drill-through on a specific date.</span></span> <span data-ttu-id="a67eb-151">일일 시간 추이를 확인 하 여 피크 사용량을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-151">Look at the hourly trend that day to find the peak utilization.</span></span>
  <span data-ttu-id="a67eb-152">![스크린샷: 전화 국가 요약 보고서](media/CQD-teams-utilization-report13.png)</span><span class="sxs-lookup"><span data-stu-id="a67eb-152">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report13.png)</span></span>

2.  <span data-ttu-id="a67eb-153">해당 날짜의 열을 클릭 하 여 해당 시간에 대 한 메트릭을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-153">Click on the column for that day to display metrics for that hour.</span></span>
  <span data-ttu-id="a67eb-154">![스크린샷: 전화 국가 요약 보고서](media/CQD-teams-utilization-report14.png)</span><span class="sxs-lookup"><span data-stu-id="a67eb-154">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report14.png)</span></span>
    
    1.  <span data-ttu-id="a67eb-155">차트 아래 표에 해당 시간에 대 한 메트릭이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-155">The table below the chart will display the metrics for that hour.</span></span> <span data-ttu-id="a67eb-156">열 머리글을 기준으로 정렬할 수 있습니다. 그러나, 문제가 있는 영역을 찾는 데 관심이 있을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-156">This can be sorted by any column header; however, we would be interested in finding problematic areas.</span></span>  
        ![스크린샷: 전화 국가 요약 보고서](media/CQD-teams-utilization-report15.png)
    
    2.  <span data-ttu-id="a67eb-158">이 기간 동안에는 해당 IND 지역에서 비디오 성능이 저하 되는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-158">We see that the IND region is experiencing poor video performance in conferences during this time frame.</span></span> <span data-ttu-id="a67eb-159">결과적으로, 지역 및 시간 프레임이 식별 됨에 따라 CQD QER Microsoft 보고서를 사용 하 여 문제가 있는 위치를 좁힐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-159">Subsequently, the CQD QER Microsoft reports can be used to narrow down the problematic location as the region and time frame has been identified.</span></span>

### <a name="regional-audio-details"></a><span data-ttu-id="a67eb-160">지역별 오디오 정보</span><span class="sxs-lookup"><span data-stu-id="a67eb-160">Regional Audio Details</span></span>

<span data-ttu-id="a67eb-161">지역 오디오 세부 정보 드릴 다운은 선택 된 지역의 오디오 통화 시간 사용량을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-161">The Regional Audio Details drill down specifically shows the audio minute usage for the selected region.</span></span> <span data-ttu-id="a67eb-162">CQD에 대 한 액세스 권한이 있는 사용자는 선택한 지역 내에서 P2P와 컨퍼런스 오디오 모두에 대 한 사용 추세를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-162">Users with access to CQD can see usage trends for both P2P and conference audio within the selected region.</span></span>

1.  <span data-ttu-id="a67eb-163">호출 횟수 요약 페이지에서 표를 통해 특정 영역으로 드릴 다운 합니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-163">On the Call Count Summary page, drill-through to as specific region through the table.</span></span>
  <span data-ttu-id="a67eb-164">![스크린샷: 전화 국가 요약 보고서](media/CQD-teams-utilization-report16.png)</span><span class="sxs-lookup"><span data-stu-id="a67eb-164">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report16.png)</span></span>

2.  <span data-ttu-id="a67eb-165">영역이 있는 행을 선택 하면 추가 정보가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-165">Select the row with the region additional information is needed for.</span></span>
  <span data-ttu-id="a67eb-166">![스크린샷: 전화 국가 요약 보고서](media/CQD-teams-utilization-report17.png)</span><span class="sxs-lookup"><span data-stu-id="a67eb-166">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report17.png)</span></span>

3.  <span data-ttu-id="a67eb-167">데이터 경향에는 현재 네트워크에서 사용 되는 중요 한 분 수가 표시 되며,이는 회의가 surpassing P2P를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-167">The data trends show a significant number of minutes being used on the internal network, with conferencing far surpassing P2P use.</span></span>
  <span data-ttu-id="a67eb-168">![스크린샷: 전화 국가 요약 보고서](media/CQD-teams-utilization-report18.png)</span><span class="sxs-lookup"><span data-stu-id="a67eb-168">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report18.png)</span></span>

<span data-ttu-id="a67eb-169">지역 오디오 추세는 전세계의 외부 영향에 따라 사용자에 게 영향을 주는 방식을 표시 하는 데 사용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-169">The regional audio trend can be used to show how users are impacted by external influences in the world.</span></span> <span data-ttu-id="a67eb-170">특히, 원격으로 작업 해야 하는 사람들을 위해 EMEA 및 APAC 지역에 대 한 외부 사용량을 확인할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a67eb-170">Specifically, right now, we would expect to see the external usage for the EMEA and APAC regions to increase with people being asked to work remotely.</span></span>



## <a name="related-topics"></a><span data-ttu-id="a67eb-171">관련 항목</span><span class="sxs-lookup"><span data-stu-id="a67eb-171">Related topics</span></span>

[<span data-ttu-id="a67eb-172">통화 품질 대시보드에서 사용할 수 있는 차원 및 측정값</span><span class="sxs-lookup"><span data-stu-id="a67eb-172">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="a67eb-173">통화 품질 대시보드의 분류 간소화</span><span class="sxs-lookup"><span data-stu-id="a67eb-173">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="a67eb-174">비즈니스용 Skype 통화 분석 설정</span><span class="sxs-lookup"><span data-stu-id="a67eb-174">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="a67eb-175">통화 분석을 사용하여 통화 품질 저하 문제 해결</span><span class="sxs-lookup"><span data-stu-id="a67eb-175">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="a67eb-176">통화 분석 및 통화 품질 대시보드</span><span class="sxs-lookup"><span data-stu-id="a67eb-176">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)
 