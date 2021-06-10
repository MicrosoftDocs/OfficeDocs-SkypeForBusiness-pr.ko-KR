---
title: CQD Microsoft Teams 사용하여 Power BI 사용률 보기
ms.author: serdars
author: SerdarSoysal
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
description: 이 Teams 사용률 Power BI 보고서를 사용하여 Microsoft Teams 품질 대시보드(CQD) 데이터에 액세스하여 조직의 Microsoft Teams 추적합니다.
ms.openlocfilehash: 719f02ce7a5cd36e96ed7fd563c259c6e77764fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095042"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a><span data-ttu-id="00fa4-103">CQD Microsoft Teams 사용하여 Power BI 사용률 보기</span><span class="sxs-lookup"><span data-stu-id="00fa4-103">View Microsoft Teams utilization in Power BI using CQD data</span></span>

<span data-ttu-id="00fa4-104">2020년 3월에 [CQD에](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)대한 다운로드 가능한 Teams 쿼리 템플릿에 Power BI 사용률 보고서를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-104">New in March 2020, we've added a Teams Utilization report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 

<span data-ttu-id="00fa4-105">이 Teams 사용률 보고서를 통해 사용자가 CQD(통화 품질 대시보드) 데이터에 액세스하여 Microsoft Teams 방법(및 양)을 Teams 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-105">This new Teams Utilization reports lets you see how (and how much) your users are using Microsoft Teams by accessing Teams Call Quality Dashboard (CQD) data.</span></span> <span data-ttu-id="00fa4-106">이러한 보고서는 관리자와 비즈니스 리더가 이 데이터에 대해 빠르게 이동할 수 있는 중앙 집중식 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-106">These reports are intended to be a centralized location that both administrators and business leaders can quickly go to for this data.</span></span>

<span data-ttu-id="00fa4-107">Teams 사용률 Power BI 보고서는 통화 수 요약 및 오디오 **[](#call-count-summary-report)** 분 요약의 두 가지 기본 **[보고서로 구성됩니다.](#audio-minutes-summary-report)**</span><span class="sxs-lookup"><span data-stu-id="00fa4-107">The Teams Utilization Power BI report consists of two primary reports: **[Call Count Summary](#call-count-summary-report)** and **[Audio Minutes Summary](#audio-minutes-summary-report)**.</span></span> <span data-ttu-id="00fa4-108">사용자가 [](#daily-usage)아래 설명에 설명된 드릴다운 [](#user-list) 보고서를 활용할 때 일일 사용량, [지역](#regional-audio-details)오디오 세부 [정보,](#conference-details) 회의 세부 정보 및 사용자 목록 보고서가 재생됩니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-108">The [Daily Usage](#daily-usage), [Regional Audio Details](#regional-audio-details), [Conference Details](#conference-details) and [User List](#user-list) reports come into play when a user takes advantage of the drill-down reports, noted in the descriptions below.</span></span>

> [!NOTE]
> <span data-ttu-id="00fa4-109">지역 및 네트워크 필터링 기능을 제공하려면 구축 및 서브넷 데이터를 채워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-109">Building and subnet data must be populated to provide regional and network filtering capabilities.</span></span>

## <a name="call-count-summary-report"></a><span data-ttu-id="00fa4-110">통화 수 요약 보고서</span><span class="sxs-lookup"><span data-stu-id="00fa4-110">Call Count Summary Report</span></span>

<span data-ttu-id="00fa4-111">기본 페이지(통화 수 요약)는 섹션 제목에 설명된 지난 30일 및 90일 동안 오디오, 비디오 및 화면 공유 세션 수를 즉시 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-111">The main page (Call Count Summary) immediately provides the number of audio, video and screen sharing sessions over the last 30 and 90 days as noted in the section title.</span></span> <span data-ttu-id="00fa4-112">처음에 표시되는 데이터는 조직 전체에 대한 것이고 페이지의 왼쪽에 있는 슬라이서 드롭다운 옵션을 사용하여 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-112">The data initially displayed is for the organization as a whole and can be filtered using the slicer dropdown options on the left side of the page.</span></span>

![스크린샷: Teams 사용률 보고서](media/CQD-teams-utilization-report1.png)

1. <span data-ttu-id="00fa4-114">슬라이서 드롭다운의 오른쪽에서 미디어 유형별로 호출 수가 지난 30일 동안 내부/외부 보기로 세분화됩니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-114">To the right of the slicer dropdowns, the number of calls by media type is broken down to an internal/external view over the past thirty days.</span></span> <span data-ttu-id="00fa4-115">위의 스크린샷을 통해 외부 조직 위치에서 더 많은 호출이 발생하고 있는 것으로 볼 수 있습니다. 이는 현재 글로벌 환경을 고려하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-115">We can see through the above screenshot that there are more calls happening from outside organizational locations, which makes sense considering the current global environment.</span></span>
  <span data-ttu-id="00fa4-116">![스크린샷: Teams 사용률 보고서](media/CQD-teams-utilization-report2.png)</span><span class="sxs-lookup"><span data-stu-id="00fa4-116">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report2.png)</span></span>

1. <span data-ttu-id="00fa4-117">미디어 유형 수 상자 오른쪽에 지난 90일 동안 미디어 유형별 월별 통화 수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-117">To the right of the media type count box, we have the Monthly Call Count by Media Type for the last 90 days.</span></span> <span data-ttu-id="00fa4-118">각 열 및 미디어 유형을 마우스로 마우스로 아서 이전 월 또는 현재 월의 수를 표시하여 사용량 추세 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-118">Each column and media type can be hovered over to display the count for a previous month or the current month to date, providing usage trend information.</span></span>
  <span data-ttu-id="00fa4-119">![스크린샷: Teams 사용률 보고서](media/CQD-teams-utilization-report3.png)</span><span class="sxs-lookup"><span data-stu-id="00fa4-119">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report3.png)</span></span>
 

1. <span data-ttu-id="00fa4-120">중간 그래프는 90일 그래프와 같은 기능을 하지만 지난 30일 동안 매일 사용 현황 보기를 제공하며 사용자가 마우스 오른쪽 단추로 클릭하고 특정 일에 대한 세부 정보를 드릴다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-120">The middle graph functions as the 90-day graph does, however it provides a daily usage view for the past 30 days and allows a user to right click and drill down into details for a specific day.</span></span>
  <span data-ttu-id="00fa4-121">![스크린샷: Teams 사용률 보고서](media/CQD-teams-utilization-report4.png)</span><span class="sxs-lookup"><span data-stu-id="00fa4-121">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report4.png)</span></span>

<span data-ttu-id="00fa4-122">페이지의 왼쪽 아래 섹션에는 지난 1년 동안 각 미디어 유형에 대한 총 값을 제공하는 표가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-122">On the bottom left section of the page, you'll find a table providing total values for each media type over the past year.</span></span> 
    <span data-ttu-id="00fa4-123">![스크린샷: Teams 사용률 보고서 ](media/CQD-teams-utilization-report5.png) ![ 스크린샷: Teams 사용률 보고서](media/CQD-teams-utilization-report6.png)</span><span class="sxs-lookup"><span data-stu-id="00fa4-123">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report5.png) ![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report6.png)</span></span>   

<span data-ttu-id="00fa4-124">표 오른쪽에 있는 막대형 차트에는 지난 30일 동안 가장 많이 사용하는 클라이언트(호출/스트림)가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-124">To the right of the table, a bar chart shows clients with the most use (calls/streams) for the past 30 days.</span></span>
   <span data-ttu-id="00fa4-125">![스크린샷: Teams 사용률 보고서](media/CQD-teams-utilization-report7.png)</span><span class="sxs-lookup"><span data-stu-id="00fa4-125">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report7.png)</span></span>

<span data-ttu-id="00fa4-126">이 페이지의 마지막 차트 집합은 각 미디어 유형을 개별적으로 보여 주며, 회의 및 P2P 사용량을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-126">The last set of charts for this page show each media type individually, with a breakdown showing conference and P2P usage.</span></span> <span data-ttu-id="00fa4-127">아래 차트는 P2P에 비해 회의 사용량이 훨씬 더 높게 나타났습니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-127">The charts below show that there is a significantly higher number of conference usage as compared to P2P.</span></span>
  <span data-ttu-id="00fa4-128">![스크린샷: Teams 사용률 보고서](media/CQD-teams-utilization-report8.png)</span><span class="sxs-lookup"><span data-stu-id="00fa4-128">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report8.png)</span></span>

## <a name="audio-minutes-summary-report"></a><span data-ttu-id="00fa4-129">오디오 분 요약 보고서</span><span class="sxs-lookup"><span data-stu-id="00fa4-129">Audio Minutes Summary Report</span></span>

<span data-ttu-id="00fa4-130">오디오 분 사용 보고서에서 총 분 사용량은 몇 가지 다른 보기를 통해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-130">On the Audio Minutes usage report, the total minute usage is provided through a few different views.</span></span> 

<span data-ttu-id="00fa4-131">텍스트 상자를 쉽게 사용할 수 있도록 슬라이서 옆에 30일 사용 요약이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-131">We have the thirty-day usage summary shown next to the slicers as easy to consume text boxes.</span></span> <span data-ttu-id="00fa4-132">맨 위 숫자는 30일 합계를 보여 주며, 내부 및 외부 분석은 아래와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-132">The top number shows the thirty-day total, with internal and external breakdowns below that.</span></span>

![스크린샷: Teams 사용률 보고서](media/CQD-teams-utilization-report9.png)

<span data-ttu-id="00fa4-134">오른쪽 상단 막대 그래프는 회의 오디오 사용량에 대한 연도 보기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-134">The top right bar graph provides a yearlong view of conference audio usage.</span></span> <span data-ttu-id="00fa4-135">한 달 동안 마우스를 오버하여 회의 오디오 분을 보여 니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-135">Hover over the month to show the conference audio minutes.</span></span>

<span data-ttu-id="00fa4-136">P2P 및 컨퍼런스 오디오의 차이를 표시하기 위해 왼쪽 아래 차트는 지난 1년 동안 모든 오디오를 사용하며 두 형식 간에 나타났습니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-136">To show the difference in P2P and conference audio, the bottom left chart takes all audio for the past year and breaks it up between the two types.</span></span>

![스크린샷: Teams 사용률 보고서](media/CQD-teams-utilization-report10.png)

<span data-ttu-id="00fa4-138">오디오 분 페이지의 마지막 차트에는 전역 맵 오버레이에서 오디오 분 사용량이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-138">The last chart for the Audio minutes page shows audio minute usage on a global map overlay.</span></span> <span data-ttu-id="00fa4-139">이 차트는 테넌트에 구축 및 서브넷 데이터가 업로드되는 경우만 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-139">This chart will only work if building and subnet data is uploaded to the tenant.</span></span> <span data-ttu-id="00fa4-140">맵의 파이 차트 오버레이를 드릴링하여 나중에 지역 오디오 사용량을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-140">The pie chart overlay on the map can be drilled into, subsequently providing regional audio usage.</span></span>

![스크린샷: Teams 사용률 보고서](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a><span data-ttu-id="00fa4-142">드릴스루 기능</span><span class="sxs-lookup"><span data-stu-id="00fa4-142">Drill-through capabilities</span></span>

<span data-ttu-id="00fa4-143">이전에 언급했듯이 사용자는 일일 및 지역별 사용 보고서를 드릴링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-143">As previously noted, users can drill into the daily and regional usage reports.</span></span>

### <a name="daily-usage"></a><span data-ttu-id="00fa4-144">일일 사용량</span><span class="sxs-lookup"><span data-stu-id="00fa4-144">Daily Usage</span></span>

<span data-ttu-id="00fa4-145">관리자는 일일 사용량 보고서를 통해 하루 동안 사용량이 가장 많은 기간을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-145">The Daily Usage report allows an administrator to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="00fa4-146">사용량 외에도 해당 일에 대한 전반적인 사용자 정서와 피드백을 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-146">In addition to usage, we are also able to capture overall user sentiment and feedback for that day.</span></span>

![스크린샷: Teams 사용률 보고서](media/CQD-teams-utilization-report12.png)

<span data-ttu-id="00fa4-148">일별 사용 보고서는 내부 및 외부 연결을 차별화하는 추가 기능을 통해 선택한 날의 오디오, 비디오 및 화면 공유 수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-148">The Daily usage report displays the number of Audio, Video and Screen shares for the selected day with the added ability to differentiate between internal and external connectivity.</span></span> <span data-ttu-id="00fa4-149">회의 및 피어 투 피어 분석은 모달리티 합계 상자의 바로 오른쪽에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-149">A Conference and Peer to Peer breakdown is to the immediate right of the modality total box.</span></span> <span data-ttu-id="00fa4-150">보고서의 오른쪽 상단에는 관련 ID와 참가자가 있는 회의 목록이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-150">The top right of the report provides a list of conferences with their associated ID and participants for the day.</span></span> <span data-ttu-id="00fa4-151">회의 목록은 회의 세부 정보 보고서에 대한 추가 드릴다운도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-151">The conference list provides an additional drill down to the Conference Details report as well.</span></span> <span data-ttu-id="00fa4-152">그래픽 바꾸기</span><span class="sxs-lookup"><span data-stu-id="00fa4-152">REPLACE GRAPHIC</span></span>

![스크린샷: Teams 사용률 보고서](media/CQD-teams-utilization-report13.png)

<span data-ttu-id="00fa4-154">중앙 영역의 막대 그래프를 사용하면 사용자가 하루 동안 최대 사용량 기간을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-154">The bar graph in the center area allows the user to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="00fa4-155">사용자는 한 시간 동안 사용자 목록 보고서를 표시하는 그래프에 나타내는 시간으로 드릴다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-155">Users may drill down into the hour represented on the graph which will present the User List report for the hour.</span></span>

<span data-ttu-id="00fa4-156">막대 그래프 오른쪽에 사용자 피드백이 시각적 형식으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-156">To the right of the bar graph, User Feedback is presented in a visual format.</span></span> <span data-ttu-id="00fa4-157">사용자 감정은 주관적일 수 있는 반면 잠재적인 문제를 식별하는 데 사용할 수 있는 인사이트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-157">While user sentiment can be subjective, it does provide insight that can be used to identify potential issues.</span></span>

<span data-ttu-id="00fa4-158">아래쪽 표는 일에 대한 메트릭 범위를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-158">The bottom table provides a range of metrics for the day.</span></span> <span data-ttu-id="00fa4-159">오류율과 함께 백분율이 좋지 않은 경우 관리자에게 잠재적인 개선 영역을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-159">Poor percentages along with failure rates can provide an administrator with potential areas of improvement.</span></span> <span data-ttu-id="00fa4-160">아래와 같이 각 시간을 개별적으로 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-160">Each hour can also be selected individually as shown below.</span></span>

<span data-ttu-id="00fa4-161">이 데이터는 사용량이 가장 많은 시간 동안 문제가 있는 지역을 식별하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-161">This data can be used to identify regions having problems during peak consumption times.</span></span>


<span data-ttu-id="00fa4-162">해당 시간의 열을 클릭하여 해당 시간의 메트릭을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-162">Click on the column for that day to display metrics for that hour.</span></span>
<span data-ttu-id="00fa4-163">![스크린샷: Teams 사용률 보고서](media/CQD-teams-utilization-report14.png)</span><span class="sxs-lookup"><span data-stu-id="00fa4-163">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report14.png)</span></span>
  
  1.  <span data-ttu-id="00fa4-164">차트 아래의 표에는 해당 시간의 메트릭이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-164">The table below the chart will display the metrics for that hour.</span></span> <span data-ttu-id="00fa4-165">열 헤더로 정렬할 수 있습니다. 그러나 문제가 있는 영역을 찾는 데 관심이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-165">This can be sorted by any column header; however, we would be interested in finding problematic areas.</span></span>  
    ![스크린샷: Teams 사용률 보고서](media/CQD-teams-utilization-report15.png)
    
  2.  <span data-ttu-id="00fa4-167">이 기간 동안 IND 지역이 회의에서 비디오 성능이 좋지 않은 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-167">We see that the IND region is experiencing poor video performance in conferences during this time frame.</span></span> <span data-ttu-id="00fa4-168">그 후 CQD QER Microsoft 보고서를 사용하여 지역 및 시간 프레임이 식별되면 문제가 있는 위치를 좁힐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-168">Subsequently, the CQD QER Microsoft reports can be used to narrow down the problematic location as the region and time frame has been identified.</span></span>

### <a name="conference-details"></a><span data-ttu-id="00fa4-169">회의 세부 정보</span><span class="sxs-lookup"><span data-stu-id="00fa4-169">Conference Details</span></span>

<span data-ttu-id="00fa4-170">컨퍼런스 세부 정보 보고서는 참석자 목록에서 세션 중에 사용되는 미디어 유형에 대한 모임에 대한 추가 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-170">The Conference Details report provides additional insight for meetings, from an attendee list, to the media types used during the session.</span></span>

<span data-ttu-id="00fa4-171">일일 사용 페이지의 회의 ID 차트에서 회의 참가자 표시줄을 마우스 오른쪽 단추로 클릭하여 회의 세부 정보를 드릴다운합니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-171">Right click a conference the participant bar in the conference ID chart on the Daily usage page to drill down into the conference details.</span></span>

![스크린샷: Teams 사용률 보고서](media/CQD-teams-utilization-report24.png)

![스크린샷: Teams 사용률 보고서](media/CQD-teams-utilization-report25.png)
  

<span data-ttu-id="00fa4-174">아래 표에서 잠재적인 문제 해결 노력을 지원하기 위해 회의 참가자뿐만 아니라 패킷 손실 및 지터까지 모든 관련 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-174">We can see the participants in the conference as well as all the pertinent information down to packet loss and jitter to assist with potential troubleshooting efforts in the bottom table.</span></span>

![스크린샷: Teams 사용률 보고서](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a><span data-ttu-id="00fa4-176">지역 오디오 세부 정보</span><span class="sxs-lookup"><span data-stu-id="00fa4-176">Regional Audio Details</span></span>

<span data-ttu-id="00fa4-177">지역 오디오 세부 정보 드릴다운은 특히 선택한 지역에 대한 오디오 분 사용량을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-177">The Regional Audio Details drill down specifically shows the audio minute usage for the selected region.</span></span> <span data-ttu-id="00fa4-178">CQD에 대한 액세스 권한이 있는 사용자는 선택한 지역 내에서 P2P 및 컨퍼런스 오디오 모두에 대한 사용 추세를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-178">Users with access to CQD can see usage trends for both P2P and conference audio within the selected region.</span></span>

1.  <span data-ttu-id="00fa4-179">호출 개수 요약 페이지에서 표를 통해 특정 지역으로 드릴스루합니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-179">On the Call Count Summary page, drill-through to as specific region through the table.</span></span>
  <span data-ttu-id="00fa4-180">![스크린샷: Teams 사용률 보고서](media/CQD-teams-utilization-report16.png)</span><span class="sxs-lookup"><span data-stu-id="00fa4-180">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report16.png)</span></span>

2.  <span data-ttu-id="00fa4-181">필요한 지역 추가 정보가 필요한 행을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-181">Select the row with the region additional information is needed for.</span></span>
  <span data-ttu-id="00fa4-182">![스크린샷: Teams 사용률 보고서](media/CQD-teams-utilization-report17.png)</span><span class="sxs-lookup"><span data-stu-id="00fa4-182">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report17.png)</span></span>

3.  <span data-ttu-id="00fa4-183">데이터 추세는 내부 네트워크에서 사용되는 상당한 수의 분을 보여 주며 회의는 P2P 사용을 훨씬 능가합니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-183">The data trends show a significant number of minutes being used on the internal network, with conferencing far surpassing P2P use.</span></span>
  <span data-ttu-id="00fa4-184">![스크린샷: Teams 사용률 보고서](media/CQD-teams-utilization-report18.png)</span><span class="sxs-lookup"><span data-stu-id="00fa4-184">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report18.png)</span></span>

<span data-ttu-id="00fa4-185">지역 오디오 추세를 사용하여 사용자가 전 세계의 외부 영향에 어떻게 영향을 미치는지 보여 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-185">The regional audio trend can be used to show how users are impacted by external influences in the world.</span></span> <span data-ttu-id="00fa4-186">특히 현재 EMEA 및 APAC 지역에 대한 외부 사용량이 원격으로 작업해야 하는 사용자와 함께 증가하는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-186">Specifically, right now, we would expect to see the external usage for the EMEA and APAC regions to increase with people being asked to work remotely.</span></span>


### <a name="user-list"></a><span data-ttu-id="00fa4-187">사용자 목록</span><span class="sxs-lookup"><span data-stu-id="00fa4-187">User List</span></span>

<span data-ttu-id="00fa4-188">사용자 목록 드릴다운에서는 보고서를 보는 사용자가 선택한 특정 시간의 사용자 특정 정보를 예상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-188">The User List drill down provides, as one might expect, user specific information for a specific hour selected by the person viewing the report.</span></span> <span data-ttu-id="00fa4-189">사용자 목록 보고서는 일일 사용량 보고서의 시간별 추세 그래프의 드릴다운을 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-189">The User List report is accessible through a drill down in the Hourly Trends graph on the Daily Usage report.</span></span> <span data-ttu-id="00fa4-190">아래와 같이 필요한 시간 추가 정보를 마우스 오른쪽 단추로 클릭하고 드릴스루 및 사용자 목록을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-190">Right click on the hour additional information is needed for and select Drill through and User List, as shown below.</span></span>

![스크린샷: Teams 사용률 보고서](media/CQD-teams-utilization-report19.png)

<span data-ttu-id="00fa4-192">사용자 목록 보고서는 페이지의 위쪽 가운데에 있는 도넛형 차트를 통해 내부/외부 연결을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-192">The User List report shows internal/external connectivity through the doughnut chart in the top center of the page.</span></span> <span data-ttu-id="00fa4-193">아래 이미지에서 회사 네트워크 외부에서 많은 양의 참여가 있는 것으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-193">We can see that there is a large amount of participation from Outside the corporate network in the below image.</span></span>

<span data-ttu-id="00fa4-194">그래프의 오른쪽 위에는 해당 시간 내에 각 사용자가 호출한 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-194">The top right of the graph shows the number of calls made by each user within that hour.</span></span>

![스크린샷: Teams 사용률 보고서](media/CQD-teams-utilization-report20.png)

<span data-ttu-id="00fa4-196">아래쪽 표에서는 해당 시간 동안 각 사용자가 참여한 세션에 대한 자세한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-196">The bottom table provides detailed information for the sessions each user participated in during that hour.</span></span> <span data-ttu-id="00fa4-197">실패 유형 열은 호출이 삭제되는 원인을 결정하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-197">The Failure Type column is useful in determining what caused a call to drop.</span></span> <span data-ttu-id="00fa4-198">캡처 및 렌더링 디바이스 열은 호출이 품질이 좋지 않은 것으로 보고된 이유를 식별하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="00fa4-198">The Capture and Render Device columns are useful in identifying why a call was reported having poor quality.</span></span>


## <a name="related-topics"></a><span data-ttu-id="00fa4-199">관련 항목</span><span class="sxs-lookup"><span data-stu-id="00fa4-199">Related topics</span></span>

[<span data-ttu-id="00fa4-200">통화 품질 대시보드에서 사용할 수 있는 차원 및 측정값</span><span class="sxs-lookup"><span data-stu-id="00fa4-200">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="00fa4-201">통화 품질 대시보드의 분류 간소화</span><span class="sxs-lookup"><span data-stu-id="00fa4-201">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="00fa4-202">비즈니스용 Skype 통화 분석 설정</span><span class="sxs-lookup"><span data-stu-id="00fa4-202">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="00fa4-203">통화 분석을 사용하여 통화 품질 저하 문제 해결</span><span class="sxs-lookup"><span data-stu-id="00fa4-203">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="00fa4-204">통화 분석 및 통화 품질 대시보드</span><span class="sxs-lookup"><span data-stu-id="00fa4-204">Call Analytics and Call Quality Dashboard</span></span>](./monitor-call-quality-qos.md)

[<span data-ttu-id="00fa4-205">Teams 문제 해결</span><span class="sxs-lookup"><span data-stu-id="00fa4-205">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
