---
title: 'Lync Server 2013: 모니터링 대시보드 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Monitoring Dashboard
ms:assetid: e00e5783-116f-481f-ad17-3af847d6769a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721905(v=OCS.15)
ms:contentKeyID: 49733839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50c5a435baf9ef6b2ef24e235270326507b68789
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985305"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-monitoring-dashboard-in-lync-server-2013"></a><span data-ttu-id="d72d4-102">Lync Server 2013에서 모니터링 대시보드 사용</span><span class="sxs-lookup"><span data-stu-id="d72d4-102">Using the Monitoring Dashboard in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d72d4-103">_**마지막으로 수정한 주제:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="d72d4-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="d72d4-104">모니터링 대시보드는 관리자에 게 Microsoft Lync Server 2013 시스템 상태 및 시스템 사용량에 대 한 간략 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-104">The Monitoring Dashboard provides administrators with a quick overview of their Microsoft Lync Server 2013 system health and system usage.</span></span> <span data-ttu-id="d72d4-105">대시보드는 주요 시스템 메트릭의 집계 보기를 표시 하 고 다음 중 하나를 표시 하 여 수행 하도록 디자인 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-105">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>

  - <span data-ttu-id="d72d4-106">현재 날짜의 합계입니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-106">Totals for the current day.</span></span> <span data-ttu-id="d72d4-107">현재 날짜에 표시 되는 값은 현재 시간까지 자정에서 기록 된 데이터를 나타냅니다 (보고 서버의 현지 시간 기준).</span><span class="sxs-lookup"><span data-stu-id="d72d4-107">Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server).</span></span> <span data-ttu-id="d72d4-108">즉, 사용자는 일반적으로 하루 종일 데이터를 볼 수 있으며, 24 시간 동안은 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-108">That means that you will typically be viewing data for a partial day and not for a 24-hour period.</span></span> <span data-ttu-id="d72d4-109">예를 들어 서버의 현지 시간이 오전 8:00이 고 오전 8:00 AM의 현재 시간인 8 시간이 있으므로 8 시간 분량의 데이터가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-109">For example, if the local time of the server is 8:00 AM, you see eight hours’ worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>

  - <span data-ttu-id="d72d4-110">주 및 지난 6 주에 대 한 총 추세 합계</span><span class="sxs-lookup"><span data-stu-id="d72d4-110">Totals for the week, and trend totals for the past six weeks.</span></span>

  - <span data-ttu-id="d72d4-111">월의 합계 및 지난 6 개월 동안의 추세 합계 (시스템 사용에만 해당)</span><span class="sxs-lookup"><span data-stu-id="d72d4-111">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>

<span data-ttu-id="d72d4-112">[CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) cmdlet을 사용 하 여 Lync Server 2013 모니터링 보고서에 액세스 하는 데 사용 되는 URL을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-112">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) cmdlet to return the URL used for accessing Lync Server 2013 Monitoring Reports:</span></span>

    Get-CsReportingConfiguration

<span data-ttu-id="d72d4-113">기본적으로 모니터링 대시보드에는 현재 주와 지난 6 주에 대 한 추세 합계에 대 한 다음 메트릭에 대 한 데이터가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-113">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>

<div>

## <a name="system-usage-metrics"></a><span data-ttu-id="d72d4-114">시스템 사용 메트릭</span><span class="sxs-lookup"><span data-stu-id="d72d4-114">System Usage Metrics</span></span>

<span data-ttu-id="d72d4-115">**등록**</span><span class="sxs-lookup"><span data-stu-id="d72d4-115">**Registration**</span></span>

  - <span data-ttu-id="d72d4-116">고유한 사용자 로그온</span><span class="sxs-lookup"><span data-stu-id="d72d4-116">Unique user logons</span></span>

<span data-ttu-id="d72d4-117">**피어 투 피어**</span><span class="sxs-lookup"><span data-stu-id="d72d4-117">**Peer-to-peer**</span></span>

  - <span data-ttu-id="d72d4-118">총 세션</span><span class="sxs-lookup"><span data-stu-id="d72d4-118">Total sessions</span></span>

  - <span data-ttu-id="d72d4-119">메신저 세션</span><span class="sxs-lookup"><span data-stu-id="d72d4-119">IM sessions</span></span>

  - <span data-ttu-id="d72d4-120">오디오 세션</span><span class="sxs-lookup"><span data-stu-id="d72d4-120">Audio sessions</span></span>

  - <span data-ttu-id="d72d4-121">비디오 세션</span><span class="sxs-lookup"><span data-stu-id="d72d4-121">Video sessions</span></span>

  - <span data-ttu-id="d72d4-122">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="d72d4-122">Application sharing</span></span>

  - <span data-ttu-id="d72d4-123">총 오디오 세션 시간 (분)</span><span class="sxs-lookup"><span data-stu-id="d72d4-123">Total audio session minutes</span></span>

  - <span data-ttu-id="d72d4-124">평균 오디오 세션 시간 (분)</span><span class="sxs-lookup"><span data-stu-id="d72d4-124">Avg. audio session minutes</span></span>

<span data-ttu-id="d72d4-125">**회의**</span><span class="sxs-lookup"><span data-stu-id="d72d4-125">**Conference**</span></span>

  - <span data-ttu-id="d72d4-126">총 컨퍼런스</span><span class="sxs-lookup"><span data-stu-id="d72d4-126">Total conferences</span></span>

  - <span data-ttu-id="d72d4-127">메신저 대화 회의</span><span class="sxs-lookup"><span data-stu-id="d72d4-127">IM conferences</span></span>

  - <span data-ttu-id="d72d4-128">A/V 회의</span><span class="sxs-lookup"><span data-stu-id="d72d4-128">A/V conferences</span></span>

  - <span data-ttu-id="d72d4-129">응용 프로그램 공유 회의</span><span class="sxs-lookup"><span data-stu-id="d72d4-129">Application sharing conferences</span></span>

  - <span data-ttu-id="d72d4-130">웹 회의</span><span class="sxs-lookup"><span data-stu-id="d72d4-130">Web conferences</span></span>

  - <span data-ttu-id="d72d4-131">총 이끌이</span><span class="sxs-lookup"><span data-stu-id="d72d4-131">Total organizers</span></span>

  - <span data-ttu-id="d72d4-132">총 A/V 회의 시간 (분)</span><span class="sxs-lookup"><span data-stu-id="d72d4-132">Total A/V conference minutes</span></span>

  - <span data-ttu-id="d72d4-133">Avg. A/V 회의 시간 (분)</span><span class="sxs-lookup"><span data-stu-id="d72d4-133">Avg. A/V conference minutes</span></span>

  - <span data-ttu-id="d72d4-134">총 PSTN 컨퍼런스</span><span class="sxs-lookup"><span data-stu-id="d72d4-134">Total PSTN conferences</span></span>

  - <span data-ttu-id="d72d4-135">총 PSTN 참가자</span><span class="sxs-lookup"><span data-stu-id="d72d4-135">Total PSTN participants</span></span>

  - <span data-ttu-id="d72d4-136">총 PSTN 참가 시간 (분)</span><span class="sxs-lookup"><span data-stu-id="d72d4-136">Total PSTN participant minutes</span></span>

<span data-ttu-id="d72d4-137">시스템 사용 메트릭 외에도, 다음 메트릭은 지난 6 일간의 총 합계 ( **주간 보기**를 선택 하는 경우) 또는 현재 주와 지난 6 주 동안 **월간 보기**를 선택 하 여 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-137">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>

</div>

<div>

## <a name="per-user-call-diagnostics"></a><span data-ttu-id="d72d4-138">사용자 단위 통화 진단</span><span class="sxs-lookup"><span data-stu-id="d72d4-138">Per-User Call Diagnostics</span></span>

<span data-ttu-id="d72d4-139">**통화에 실패 한 사용자**</span><span class="sxs-lookup"><span data-stu-id="d72d4-139">**Users with call failures**</span></span>

  - <span data-ttu-id="d72d4-140">통화에 실패 한 총 사용자 수</span><span class="sxs-lookup"><span data-stu-id="d72d4-140">Total users with call failures</span></span>

  - <span data-ttu-id="d72d4-141">통화 장애가 있는 컨퍼런스 이끌이</span><span class="sxs-lookup"><span data-stu-id="d72d4-141">Conference organizers with call failures</span></span>

<span data-ttu-id="d72d4-142">**저품질 통화가 있는 사용자**</span><span class="sxs-lookup"><span data-stu-id="d72d4-142">**Users with poor quality calls**</span></span>

  - <span data-ttu-id="d72d4-143">저품질 통화가 있는 총 사용자 수</span><span class="sxs-lookup"><span data-stu-id="d72d4-143">Total users with poor quality calls</span></span>

</div>

<div>

## <a name="call-diagnostics"></a><span data-ttu-id="d72d4-144">전화 진단</span><span class="sxs-lookup"><span data-stu-id="d72d4-144">Call Diagnostics</span></span>

<span data-ttu-id="d72d4-145">피어 투 피어</span><span class="sxs-lookup"><span data-stu-id="d72d4-145">Peer-to-peer</span></span>

  - <span data-ttu-id="d72d4-146">총 오류</span><span class="sxs-lookup"><span data-stu-id="d72d4-146">Total failures</span></span>

  - <span data-ttu-id="d72d4-147">전체 실패 율</span><span class="sxs-lookup"><span data-stu-id="d72d4-147">Overall failure rate</span></span>

  - <span data-ttu-id="d72d4-148">메신저 대화 오류 비율</span><span class="sxs-lookup"><span data-stu-id="d72d4-148">IM failure rate</span></span>

  - <span data-ttu-id="d72d4-149">오디오 결함 율</span><span class="sxs-lookup"><span data-stu-id="d72d4-149">Audio failure rate</span></span>

  - <span data-ttu-id="d72d4-150">응용 프로그램 공유 실패 비율</span><span class="sxs-lookup"><span data-stu-id="d72d4-150">Application sharing failure rate</span></span>

<span data-ttu-id="d72d4-151">회의</span><span class="sxs-lookup"><span data-stu-id="d72d4-151">Conference</span></span>

  - <span data-ttu-id="d72d4-152">총 오류</span><span class="sxs-lookup"><span data-stu-id="d72d4-152">Total failures</span></span>

  - <span data-ttu-id="d72d4-153">전체 실패 율</span><span class="sxs-lookup"><span data-stu-id="d72d4-153">Overall failure rate</span></span>

  - <span data-ttu-id="d72d4-154">메신저 대화 오류 비율</span><span class="sxs-lookup"><span data-stu-id="d72d4-154">IM failure rate</span></span>

  - <span data-ttu-id="d72d4-155">A/V 오류 비율</span><span class="sxs-lookup"><span data-stu-id="d72d4-155">A/V failure rate</span></span>

  - <span data-ttu-id="d72d4-156">응용 프로그램 공유 실패 비율</span><span class="sxs-lookup"><span data-stu-id="d72d4-156">Application sharing failure rate</span></span>

<span data-ttu-id="d72d4-157">실패 한 세션 별 상위 5 개 서버</span><span class="sxs-lookup"><span data-stu-id="d72d4-157">Top five servers by failed sessions</span></span>

</div>

<div>

## <a name="media-quality-diagnostics"></a><span data-ttu-id="d72d4-158">미디어 품질 진단</span><span class="sxs-lookup"><span data-stu-id="d72d4-158">Media Quality Diagnostics</span></span>

<span data-ttu-id="d72d4-159">피어 투 피어</span><span class="sxs-lookup"><span data-stu-id="d72d4-159">Peer-to-peer</span></span>

  - <span data-ttu-id="d72d4-160">낮은 품질의 총 통화</span><span class="sxs-lookup"><span data-stu-id="d72d4-160">Total poor quality calls</span></span>

  - <span data-ttu-id="d72d4-161">저품질 통화 백분율</span><span class="sxs-lookup"><span data-stu-id="d72d4-161">Poor quality call percentage</span></span>

  - <span data-ttu-id="d72d4-162">품질이 좋지 않은 PSTN 통화</span><span class="sxs-lookup"><span data-stu-id="d72d4-162">PSTN calls with poor quality</span></span>

<span data-ttu-id="d72d4-163">회의</span><span class="sxs-lookup"><span data-stu-id="d72d4-163">Conference</span></span>

  - <span data-ttu-id="d72d4-164">낮은 품질의 총 통화</span><span class="sxs-lookup"><span data-stu-id="d72d4-164">Total poor quality calls</span></span>

  - <span data-ttu-id="d72d4-165">저품질 통화 백분율</span><span class="sxs-lookup"><span data-stu-id="d72d4-165">Poor quality call percentage</span></span>

  - <span data-ttu-id="d72d4-166">품질이 좋지 않은 PSTN 통화</span><span class="sxs-lookup"><span data-stu-id="d72d4-166">PSTN calls with poor quality</span></span>

<span data-ttu-id="d72d4-167">저품질 통화 백분율을 통한 최고 최악의 서버</span><span class="sxs-lookup"><span data-stu-id="d72d4-167">Top worst servers by poor quality call percentage</span></span>

</div>

<div>

## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="d72d4-168">모니터링 대시보드 작업</span><span class="sxs-lookup"><span data-stu-id="d72d4-168">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="d72d4-169">참고로, 현재 주에는 기본적으로 합계가 표시 되 고 지난 6 주 동안 추세 값이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-169">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks.</span></span> <span data-ttu-id="d72d4-170">현재 월의 합계 및 지난 6 개월의 추세 값을 확인 하려면 대시보드의 오른쪽 위 모서리에 있는 **월 보기** 링크를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-170">If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard.</span></span> <span data-ttu-id="d72d4-171">월 합계를 표시 하기로 결정 한 경우 링크 텍스트는 **주별 보기로**변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-171">If you decide to view monthly totals, the link text will change to **Weekly View**.</span></span> <span data-ttu-id="d72d4-172">해당 링크를 클릭 하 여 주 보기로 다시 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-172">You can switch back to the weekly view by clicking that link.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="d72d4-173">모니터링 대시보드는 지난 6 주 (또는 월)에 대 한 현재 주 (또는 월) 및 추세 값에 대 한 합계를 볼 수 있도록 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-173">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months).</span></span> <span data-ttu-id="d72d4-174">이러한 날짜와 시간은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-174">You cannot change these dates and times.</span></span> <span data-ttu-id="d72d4-175">예를 들어 대시보드를 사용 하 여 9 개월 전에 시작 되는 기간의 보고서 합계를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-175">For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span>



</div>

<span data-ttu-id="d72d4-176">이번 **주**, **이번 달**또는 **오늘** 열에 표시 되는 값은 항목에 대 한 자세한 정보를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-176">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item.</span></span> <span data-ttu-id="d72d4-177">열 이름과 해당 열에 표시 되는 값은 선택한 메트릭에 따라, 주 보기 또는 월 단위 보기를 선택 했는지에 따라 다를 수 있다는 것에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="d72d4-177">Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view.</span></span> <span data-ttu-id="d72d4-178">예를 들어 **고유한 사용자 로그온** 메트릭에 대해 표시 된 요약을 클릭 하면 지정 된 기간에 대 한 **사용자 등록 보고서** 가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-178">For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period.</span></span> <span data-ttu-id="d72d4-179">**대시보드**를 클릭 하 여 언제 든 지 모니터링 대시보드로 돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-179">You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="d72d4-180">대시보드의 오른쪽 위 모서리에 있는 <STRONG>보고서</STRONG> 링크를 클릭 하 여 모니터링 서버 보고서 홈 페이지에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-180">You can also access the Monitoring Server Reports home page by clicking the <STRONG>Reports</STRONG> link in the upper right corner of the Dashboard.</span></span>



</div>

<span data-ttu-id="d72d4-181">**추세** 열에는 지난 6 주 (또는 메트릭과 시간 간격, 지난 6 일간 또는 지난 6 개월)에 대 한 합계를 보여 주는 간단한 꺾은선형 그래프가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-181">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months).</span></span> <span data-ttu-id="d72d4-182">이러한 간단한 선 그래프는 각 기간에 대해 레이블이 지정 되지 않은 데이터 요소 (예: 지난 6 주 각각에 대해 레이블이 지정 되지 않은 데이터 요소 한 개)를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-182">These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks).</span></span> <span data-ttu-id="d72d4-183">그러나 그래프 위에 마우스 포인터를 놓으면 이러한 그래프의 실제 값을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-183">However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph.</span></span> <span data-ttu-id="d72d4-184">이 경우 도구 설명에는 그래프의 최대값 및 최소값을 보여 주는 값이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-184">In that case, a tooltip shows you the maximum and minimum values in the graph.</span></span>

</div>

<div>

## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="d72d4-185">모니터링 대시보드에서 데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="d72d4-185">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="d72d4-186">모니터링 대시보드는 현재 대시보드 보기를 내보낼 수 있는 여러 가지 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-186">The Monitoring Dashboard provides a number of ways to export the current dashboard view.</span></span> <span data-ttu-id="d72d4-187">대시보드 도구 모음에 녹색 화살표가 연결 된 플로피 디스크 모양의 아이콘이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-187">On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it.</span></span> <span data-ttu-id="d72d4-188">이 아이콘을 클릭 하면 다음과 같은 데이터 내보내기 형식을 제공 하는 드롭다운 목록이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-188">If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>

  - <span data-ttu-id="d72d4-189">보고서 데이터를 포함 하는 XML 파일</span><span class="sxs-lookup"><span data-stu-id="d72d4-189">XML file with report data</span></span>

  - <span data-ttu-id="d72d4-190">CSV (쉼표로 분리)</span><span class="sxs-lookup"><span data-stu-id="d72d4-190">CSV (comma delimited)</span></span>

  - <span data-ttu-id="d72d4-191">PDF</span><span class="sxs-lookup"><span data-stu-id="d72d4-191">PDF</span></span>

  - <span data-ttu-id="d72d4-192">MHTML (웹 보관)</span><span class="sxs-lookup"><span data-stu-id="d72d4-192">MHTML (web archive)</span></span>

  - <span data-ttu-id="d72d4-193">0:excel}</span><span class="sxs-lookup"><span data-stu-id="d72d4-193">Excel</span></span>

  - <span data-ttu-id="d72d4-194">TIFF 파일</span><span class="sxs-lookup"><span data-stu-id="d72d4-194">TIFF file</span></span>

  - <span data-ttu-id="d72d4-195">이면</span><span class="sxs-lookup"><span data-stu-id="d72d4-195">Word</span></span>

<span data-ttu-id="d72d4-196">현재 대시보드 보기 (및 해당 값)를 내보내려면 원하는 내보내기 옵션을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-196">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="d72d4-197">Lync Server 2013은 지정 된 형식으로 보고서를 생성 한 다음 해당 보고서를 열거나 저장 하는 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-197">Lync Server 2013 generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="d72d4-198">기본적으로 Lync Server에는 보고서 **모니터링 대시보드의** 제목이 있으며 다운로드 폴더에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-198">Note that, by default, Lync Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="d72d4-199">보고서에 다른 이름을 지정 하거나 다른 폴더에 저장 하려면 **저장** 단추 옆에 있는 화살표를 클릭 한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-199">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="d72d4-200">이름 **모니터링 대시보드에** 대해 잘 알고 있고 보고서가 다운로드 폴더에 저장 되어 있는 경우 **저장** 단추를 클릭 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-200">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>

<span data-ttu-id="d72d4-201">대시보드 데이터를 내보내려고 하면 "현재 설정이이 파일을 다운로드 하도록 허용 하지 않습니다." 라는 메시지와 함께 **보안 알림** 대화 상자가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-201">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded."</span></span> <span data-ttu-id="d72d4-202">이런 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-202">If that occurs, do the following:</span></span>

  - <span data-ttu-id="d72d4-203">Internet Explorer에서 **인터넷 옵션**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-203">In Internet Explorer, select **Internet Options**.</span></span>

  - <span data-ttu-id="d72d4-204">**인터넷 옵션** 대화 상자의 **보안** 탭에서 **신뢰할 수 있는 사이트** 를 클릭 한 다음 **사이트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-204">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>

  - <span data-ttu-id="d72d4-205">신뢰할 수 **있는 사이트** 대화 상자에서 **추가** 를 클릭 하 여 lync server 2013 보고서를 실행 하는 lync server 2013을 신뢰할 수 있는 웹 사이트 모음에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-205">In the **Trusted sites** dialog box, click **Add** to add the Lync Server 2013 that is running Lync Server 2013 Reports to the collections of trusted websites.</span></span>

  - <span data-ttu-id="d72d4-206">**닫기를** 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-206">Click **Close** and then click **OK**.</span></span>

<span data-ttu-id="d72d4-207">변경 내용을 적용 하려면 모니터링 대시보드를 새로 고쳐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-207">You will then need to refresh the Monitoring Dashboard before the changes take effect.</span></span> <span data-ttu-id="d72d4-208">이렇게 하려면 F5 키를 누르거나 대시보드 도구 모음에서 **새로 고침** 아이콘을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-208">To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar.</span></span> <span data-ttu-id="d72d4-209">**새로 고침** 아이콘은 녹색 화살표가 있는 원입니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-209">(The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>

<span data-ttu-id="d72d4-210">최신 모니터링 대시보드 데이터에 대 한 링크를 포함 하는 라이브 데이터 피드를 포함 하는 Excel 스프레드시트를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-210">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data.</span></span> <span data-ttu-id="d72d4-211">라이브 데이터 피드 파일을 만들려면 도구 모음에서 주황색 **으로 내보내기 데이터 피드** 아이콘을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-211">To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>

<span data-ttu-id="d72d4-212">현재 대시보드를 인쇄 하려면 도구 모음에서 프린터 아이콘을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d72d4-212">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

