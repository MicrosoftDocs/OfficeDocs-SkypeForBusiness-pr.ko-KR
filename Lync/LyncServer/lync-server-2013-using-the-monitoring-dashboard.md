---
title: 'Lync Server 2013: 모니터링 대시보드 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Monitoring Dashboard
ms:assetid: e00e5783-116f-481f-ad17-3af847d6769a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721905(v=OCS.15)
ms:contentKeyID: 49733839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 697023ef7c93191cbe13aa0abf4c175240e70ae9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212564"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-monitoring-dashboard-in-lync-server-2013"></a><span data-ttu-id="41a7e-102">Lync Server 2013에서 모니터링 대시보드 사용</span><span class="sxs-lookup"><span data-stu-id="41a7e-102">Using the Monitoring Dashboard in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41a7e-103">_**마지막으로 수정 된 항목:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="41a7e-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="41a7e-104">모니터링 대시보드는 관리자에 게 Microsoft Lync Server 2013 시스템 상태 및 시스템 사용에 대 한 간략 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="41a7e-104">The Monitoring Dashboard provides administrators with a quick overview of their Microsoft Lync Server 2013 system health and system usage.</span></span> <span data-ttu-id="41a7e-105">이 대시보드는 다음 중 하나를 표시하여 주요 시스템 메트릭을 요약하여 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="41a7e-105">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>

  - <span data-ttu-id="41a7e-p102">현재 날짜의 요약. 현재 날짜에 대해 표시되는 값은 현재 시간(보고 서버의 현지 시간 기준)까지 자정부터 기록된 데이터를 나타냅니다. 다시 말해서 일반적으로 하루 중 24시간이 아니라 몇 시간 동안의 데이터를 보게 된다는 뜻입니다. 예를 들어 서버의 현지 시간이 오전 8:00인 경우 자정과 현재 시간인 오전 8:00의 시간차는 8시간이므로 8시간 동안의 데이터를 보게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41a7e-p102">Totals for the current day. Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server). That means that you will typically be viewing data for a partial day and not for a 24-hour period. For example, if the local time of the server is 8:00 AM, you see eight hours’ worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>

  - <span data-ttu-id="41a7e-110">일주일의 요약과 지난 6주의 추세 요약</span><span class="sxs-lookup"><span data-stu-id="41a7e-110">Totals for the week, and trend totals for the past six weeks.</span></span>

  - <span data-ttu-id="41a7e-111">현재 달의 요약과 지난 6개월의 추세 요약(시스템 사용에만 해당)</span><span class="sxs-lookup"><span data-stu-id="41a7e-111">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>

<span data-ttu-id="41a7e-112">[Get-csreportingconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) cmdlet을 사용 하 여 Lync Server 2013 모니터링 보고서에 액세스 하는 데 사용 되는 URL을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41a7e-112">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) cmdlet to return the URL used for accessing Lync Server 2013 Monitoring Reports:</span></span>

    Get-CsReportingConfiguration

<span data-ttu-id="41a7e-113">기본적으로 모니터링 대시보드는 현재 주에 대한 다음 메트릭 데이터와 지난 6주의 추세 요약을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="41a7e-113">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>

<div>

## <a name="system-usage-metrics"></a><span data-ttu-id="41a7e-114">시스템 사용 메트릭</span><span class="sxs-lookup"><span data-stu-id="41a7e-114">System Usage Metrics</span></span>

<span data-ttu-id="41a7e-115">**등록**</span><span class="sxs-lookup"><span data-stu-id="41a7e-115">**Registration**</span></span>

  - <span data-ttu-id="41a7e-116">고유 사용자 로그온</span><span class="sxs-lookup"><span data-stu-id="41a7e-116">Unique user logons</span></span>

<span data-ttu-id="41a7e-117">**피어-투-피어**</span><span class="sxs-lookup"><span data-stu-id="41a7e-117">**Peer-to-peer**</span></span>

  - <span data-ttu-id="41a7e-118">총 세션</span><span class="sxs-lookup"><span data-stu-id="41a7e-118">Total sessions</span></span>

  - <span data-ttu-id="41a7e-119">IM 세션</span><span class="sxs-lookup"><span data-stu-id="41a7e-119">IM sessions</span></span>

  - <span data-ttu-id="41a7e-120">오디오 세션</span><span class="sxs-lookup"><span data-stu-id="41a7e-120">Audio sessions</span></span>

  - <span data-ttu-id="41a7e-121">비디오 세션</span><span class="sxs-lookup"><span data-stu-id="41a7e-121">Video sessions</span></span>

  - <span data-ttu-id="41a7e-122">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="41a7e-122">Application sharing</span></span>

  - <span data-ttu-id="41a7e-123">총 오디오 세션 시간(분)</span><span class="sxs-lookup"><span data-stu-id="41a7e-123">Total audio session minutes</span></span>

  - <span data-ttu-id="41a7e-124">평균 오디오 세션 시간(분)</span><span class="sxs-lookup"><span data-stu-id="41a7e-124">Avg. audio session minutes</span></span>

<span data-ttu-id="41a7e-125">**전화**</span><span class="sxs-lookup"><span data-stu-id="41a7e-125">**Conference**</span></span>

  - <span data-ttu-id="41a7e-126">총 전화 회의</span><span class="sxs-lookup"><span data-stu-id="41a7e-126">Total conferences</span></span>

  - <span data-ttu-id="41a7e-127">IM 전화 회의</span><span class="sxs-lookup"><span data-stu-id="41a7e-127">IM conferences</span></span>

  - <span data-ttu-id="41a7e-128">A/V 회의</span><span class="sxs-lookup"><span data-stu-id="41a7e-128">A/V conferences</span></span>

  - <span data-ttu-id="41a7e-129">응용 프로그램 공유 전화 회의</span><span class="sxs-lookup"><span data-stu-id="41a7e-129">Application sharing conferences</span></span>

  - <span data-ttu-id="41a7e-130">웹 회의</span><span class="sxs-lookup"><span data-stu-id="41a7e-130">Web conferences</span></span>

  - <span data-ttu-id="41a7e-131">총 이끌이 수</span><span class="sxs-lookup"><span data-stu-id="41a7e-131">Total organizers</span></span>

  - <span data-ttu-id="41a7e-132">총 A/V 회의 시간(분)</span><span class="sxs-lookup"><span data-stu-id="41a7e-132">Total A/V conference minutes</span></span>

  - <span data-ttu-id="41a7e-133">평균 A/V 회의 시간(분)</span><span class="sxs-lookup"><span data-stu-id="41a7e-133">Avg. A/V conference minutes</span></span>

  - <span data-ttu-id="41a7e-134">총 PSTN 전화 회의</span><span class="sxs-lookup"><span data-stu-id="41a7e-134">Total PSTN conferences</span></span>

  - <span data-ttu-id="41a7e-135">총 PSTN 참가자</span><span class="sxs-lookup"><span data-stu-id="41a7e-135">Total PSTN participants</span></span>

  - <span data-ttu-id="41a7e-136">총 PSTN 참가 시간(분)</span><span class="sxs-lookup"><span data-stu-id="41a7e-136">Total PSTN participant minutes</span></span>

<span data-ttu-id="41a7e-137">시스템 사용 메트릭 외에도, 다음 메트릭이 현재 날짜와 지난 6일(**주별 보기**를 선택한 경우) 또는 현재 주와 지난 6주(**월별 보기**를 선택한 경우)의 요약을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="41a7e-137">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>

</div>

<div>

## <a name="per-user-call-diagnostics"></a><span data-ttu-id="41a7e-138">사용자당 통화 진단</span><span class="sxs-lookup"><span data-stu-id="41a7e-138">Per-User Call Diagnostics</span></span>

<span data-ttu-id="41a7e-139">**통화 실패 사용자**</span><span class="sxs-lookup"><span data-stu-id="41a7e-139">**Users with call failures**</span></span>

  - <span data-ttu-id="41a7e-140">총 통화 실패 사용자</span><span class="sxs-lookup"><span data-stu-id="41a7e-140">Total users with call failures</span></span>

  - <span data-ttu-id="41a7e-141">통화 실패 전화 회의 이끌이</span><span class="sxs-lookup"><span data-stu-id="41a7e-141">Conference organizers with call failures</span></span>

<span data-ttu-id="41a7e-142">**저품질 통화 사용자**</span><span class="sxs-lookup"><span data-stu-id="41a7e-142">**Users with poor quality calls**</span></span>

  - <span data-ttu-id="41a7e-143">총 저품질 통화 사용자</span><span class="sxs-lookup"><span data-stu-id="41a7e-143">Total users with poor quality calls</span></span>

</div>

<div>

## <a name="call-diagnostics"></a><span data-ttu-id="41a7e-144">통화 진단</span><span class="sxs-lookup"><span data-stu-id="41a7e-144">Call Diagnostics</span></span>

<span data-ttu-id="41a7e-145">피어-투-피어</span><span class="sxs-lookup"><span data-stu-id="41a7e-145">Peer-to-peer</span></span>

  - <span data-ttu-id="41a7e-146">총 실패</span><span class="sxs-lookup"><span data-stu-id="41a7e-146">Total failures</span></span>

  - <span data-ttu-id="41a7e-147">전체 실패율</span><span class="sxs-lookup"><span data-stu-id="41a7e-147">Overall failure rate</span></span>

  - <span data-ttu-id="41a7e-148">IM 실패율</span><span class="sxs-lookup"><span data-stu-id="41a7e-148">IM failure rate</span></span>

  - <span data-ttu-id="41a7e-149">오디오 실패율</span><span class="sxs-lookup"><span data-stu-id="41a7e-149">Audio failure rate</span></span>

  - <span data-ttu-id="41a7e-150">응용 프로그램 공유 실패율</span><span class="sxs-lookup"><span data-stu-id="41a7e-150">Application sharing failure rate</span></span>

<span data-ttu-id="41a7e-151">전화</span><span class="sxs-lookup"><span data-stu-id="41a7e-151">Conference</span></span>

  - <span data-ttu-id="41a7e-152">총 실패</span><span class="sxs-lookup"><span data-stu-id="41a7e-152">Total failures</span></span>

  - <span data-ttu-id="41a7e-153">전체 실패율</span><span class="sxs-lookup"><span data-stu-id="41a7e-153">Overall failure rate</span></span>

  - <span data-ttu-id="41a7e-154">IM 실패율</span><span class="sxs-lookup"><span data-stu-id="41a7e-154">IM failure rate</span></span>

  - <span data-ttu-id="41a7e-155">A/V 실패율</span><span class="sxs-lookup"><span data-stu-id="41a7e-155">A/V failure rate</span></span>

  - <span data-ttu-id="41a7e-156">응용 프로그램 공유 실패율</span><span class="sxs-lookup"><span data-stu-id="41a7e-156">Application sharing failure rate</span></span>

<span data-ttu-id="41a7e-157">실패 세션 기준의 상위 상위 5 서버</span><span class="sxs-lookup"><span data-stu-id="41a7e-157">Top five servers by failed sessions</span></span>

</div>

<div>

## <a name="media-quality-diagnostics"></a><span data-ttu-id="41a7e-158">미디어 품질 진단</span><span class="sxs-lookup"><span data-stu-id="41a7e-158">Media Quality Diagnostics</span></span>

<span data-ttu-id="41a7e-159">피어-투-피어</span><span class="sxs-lookup"><span data-stu-id="41a7e-159">Peer-to-peer</span></span>

  - <span data-ttu-id="41a7e-160">총 저품질 통화</span><span class="sxs-lookup"><span data-stu-id="41a7e-160">Total poor quality calls</span></span>

  - <span data-ttu-id="41a7e-161">저품질 통화율</span><span class="sxs-lookup"><span data-stu-id="41a7e-161">Poor quality call percentage</span></span>

  - <span data-ttu-id="41a7e-162">저품질 PSTN 통화</span><span class="sxs-lookup"><span data-stu-id="41a7e-162">PSTN calls with poor quality</span></span>

<span data-ttu-id="41a7e-163">전화</span><span class="sxs-lookup"><span data-stu-id="41a7e-163">Conference</span></span>

  - <span data-ttu-id="41a7e-164">총 저품질 통화</span><span class="sxs-lookup"><span data-stu-id="41a7e-164">Total poor quality calls</span></span>

  - <span data-ttu-id="41a7e-165">저품질 통화율</span><span class="sxs-lookup"><span data-stu-id="41a7e-165">Poor quality call percentage</span></span>

  - <span data-ttu-id="41a7e-166">저품질 PSTN 통화</span><span class="sxs-lookup"><span data-stu-id="41a7e-166">PSTN calls with poor quality</span></span>

<span data-ttu-id="41a7e-167">저품질 통화율 기준의 최하위 서버</span><span class="sxs-lookup"><span data-stu-id="41a7e-167">Top worst servers by poor quality call percentage</span></span>

</div>

<div>

## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="41a7e-168">모니터링 대시보드 작업</span><span class="sxs-lookup"><span data-stu-id="41a7e-168">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="41a7e-p103">앞에서 설명했듯이 기본적으로는 현재 주의 요약과 지난 6주의 추세 값이 표시됩니다. 현재 달의 요약과 지난 6주의 추세 값을 보려는 경우 대시보드의 오른쪽 위에 있는 **월별 보기** 링크를 클릭합니다. 월별 요약을 보기로 결정하면 링크 텍스트가 **주별 보기**로 바뀝니다. 이 링크를 클릭하여 주별 보기로 다시 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41a7e-p103">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks. If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard. If you decide to view monthly totals, the link text will change to **Weekly View**. You can switch back to the weekly view by clicking that link.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="41a7e-p104">모니터링 대시보드에서는 현재 주 또는 월의 요약과 지난 6주 또는 개월의 추세 값만 볼 수 있으며 이러한 날짜 및 시간을 변경할 수는 없습니다. 예를 들어 대시보드를 사용하여 9개월 전부터 시작하는 기간에 대한 보고서 요약을 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41a7e-p104">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months). You cannot change these dates and times. For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span>



</div>

<span data-ttu-id="41a7e-p105">**이번 주**, **이 달** 또는 **오늘** 열에 표시된 값은 해당 항목에 대한 자세한 정보에 연결됩니다. 열 이름과 해당 열에 표시되는 값은 대개 선택한 메트릭과 주별 보기를 선택했는지 아니면 월별 보기를 선택했는지에 따라 달라집니다. 예를 들어 **고유 사용자 로그온** 메트릭에 대해 표시된 요약을 클릭하면 지정된 기간에 대한 **사용자 등록 보고서**가 표시됩니다. 언제라도 **대시보드**를 클릭하여 모니터링 대시보드로 돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41a7e-p105">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item. Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view. For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period. You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="41a7e-180">대시보드의 오른쪽 위 모서리에 있는 <STRONG>Reports (보고서</STRONG> ) 링크를 클릭 하 여 모니터링 서버 보고서 홈 페이지에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41a7e-180">You can also access the Monitoring Server Reports home page by clicking the <STRONG>Reports</STRONG> link in the upper right corner of the Dashboard.</span></span>



</div>

<span data-ttu-id="41a7e-p106">**추세** 열에는 지난 6주(또는 메트릭과 시간 간격에 따라 지난 6일 또는 지난 6개월)의 요약이 표시되는 한 줄 그래프가 표시됩니다. 이 한 줄 그래프에는 각 기간에 대한 레이블이 없는 데이터 요소(예: 지난 6주의 각 주에 대한 레이블이 없는 데이터 요소)이 하나씩 표시됩니다. 그러나 그래프를 마우스 포인터로 가리켜서 그래프에 대한 실제 값을 검색할 수 있습니다. 이 경우 도구 설명에 그래프의 최소값과 최대값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="41a7e-p106">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months). These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks). However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph. In that case, a tooltip shows you the maximum and minimum values in the graph.</span></span>

</div>

<div>

## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="41a7e-185">모니터링 대시보드에서 데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="41a7e-185">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="41a7e-p107">모니터링 대시보드는 현재 대시보드 보기를 내보내는 다양한 방법을 제공합니다. 대시보드 도구 모음에는 녹색 화살표가 붙은 플로피 디스크처럼 보이는 아이콘이 있습니다. 이 아이콘을 클릭하면 다음과 같은 데이터 내보내기 형식을 제공하는 드롭다운 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="41a7e-p107">The Monitoring Dashboard provides a number of ways to export the current dashboard view. On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it. If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>

  - <span data-ttu-id="41a7e-189">보고서 데이터를 포함하는 XML 파일</span><span class="sxs-lookup"><span data-stu-id="41a7e-189">XML file with report data</span></span>

  - <span data-ttu-id="41a7e-190">CSV(쉼표로 구분됨)</span><span class="sxs-lookup"><span data-stu-id="41a7e-190">CSV (comma delimited)</span></span>

  - <span data-ttu-id="41a7e-191">PDF</span><span class="sxs-lookup"><span data-stu-id="41a7e-191">PDF</span></span>

  - <span data-ttu-id="41a7e-192">MHTML(웹 보관)</span><span class="sxs-lookup"><span data-stu-id="41a7e-192">MHTML (web archive)</span></span>

  - <span data-ttu-id="41a7e-193">Excel</span><span class="sxs-lookup"><span data-stu-id="41a7e-193">Excel</span></span>

  - <span data-ttu-id="41a7e-194">TIFF 파일</span><span class="sxs-lookup"><span data-stu-id="41a7e-194">TIFF file</span></span>

  - <span data-ttu-id="41a7e-195">Word</span><span class="sxs-lookup"><span data-stu-id="41a7e-195">Word</span></span>

<span data-ttu-id="41a7e-196">현재 대시보드 보기와 해당 값을 내보내려면 원하는 내보내기 옵션을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="41a7e-196">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="41a7e-197">Lync Server 2013 지정 된 형식으로 보고서를 생성 한 다음 해당 보고서를 열거나 저장 하는 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="41a7e-197">Lync Server 2013 generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="41a7e-198">기본적으로 Lync Server에는 보고서 **모니터링 대시보드의** 제목이 며 다운로드 폴더에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41a7e-198">Note that, by default, Lync Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="41a7e-199">보고서를 다른 이름으로 지정하거나 다른 폴더에 저장하려면 **저장** 단추 옆의 화살표를 클릭하고 **다른 이름으로 저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="41a7e-199">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="41a7e-200">**모니터링 대시보드**라는 이름을 그대로 사용하고 다운로드 폴더에 보고서를 저장하려면 **저장** 단추를 누르기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41a7e-200">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>

<span data-ttu-id="41a7e-p109">대시보드 데이터를 내보내려고 할 때 **보안 경고** 대화 상자에 "현재의 보안 설정 때문에 이 파일을 다운로드할 수 없습니다."라는 메시지가 표시됩니다. 이 경우 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="41a7e-p109">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded." If that occurs, do the following:</span></span>

  - <span data-ttu-id="41a7e-203">Internet Explorer에서 **인터넷 옵션**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="41a7e-203">In Internet Explorer, select **Internet Options**.</span></span>

  - <span data-ttu-id="41a7e-204">**인터넷 옵션** 대화 상자의 **보안** 탭에서 **신뢰할 수 있는 사이트**를 클릭하고 **사이트**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="41a7e-204">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>

  - <span data-ttu-id="41a7e-205">**신뢰할 수 있는 사이트** 대화 상자에서 **추가** 를 클릭 하 여 lync server 2013 보고서를 실행 하는 lync server 2013을 신뢰할 수 있는 웹 사이트 모음에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="41a7e-205">In the **Trusted sites** dialog box, click **Add** to add the Lync Server 2013 that is running Lync Server 2013 Reports to the collections of trusted websites.</span></span>

  - <span data-ttu-id="41a7e-206">**닫기**를 클릭하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="41a7e-206">Click **Close** and then click **OK**.</span></span>

<span data-ttu-id="41a7e-p110">그런 다음 F5 키를 누르거나 대시보드 도구 모음에서 **새로 고침** 아이콘을 클릭하여 모니터링 대시보드를 새로 고쳐야 변경 내용이 적용됩니다. **새로 고침** 아이콘은 한 쌍의 녹색 화살표가 있는 원 모양입니다.</span><span class="sxs-lookup"><span data-stu-id="41a7e-p110">You will then need to refresh the Monitoring Dashboard before the changes take effect. To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar. (The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>

<span data-ttu-id="41a7e-p111">라이브 데이터 피드를 포함하는 Excel 스프레드시트를 만들 수도 있습니다. 여기에는 최신 모니터링 대시보드 데이터에 대한 링크도 포함됩니다. 라이브 데이터 피드 파일을 만들려면 도구 모음에서 주황색의 **데이터 피드로 내보내기** 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="41a7e-p111">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data. To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>

<span data-ttu-id="41a7e-212">현재 대시보드를 인쇄하려면 도구 모음에서 프린터 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="41a7e-212">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

