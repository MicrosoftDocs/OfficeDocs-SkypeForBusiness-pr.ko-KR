---
title: 비즈니스용 Skype 서버에서 모니터링 대시보드 사용
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
ms.assetid: e00e5783-116f-481f-ad17-3af847d6769a
description: '요약: 비즈니스용 Skype 서버의 모니터링 대시보드에 대해 자세히 알아보습니다.'
ms.openlocfilehash: 98a96b8a513bad485a25aff76a69d787fb3079b0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827788"
---
# <a name="using-the-monitoring-dashboard-in-skype-for-business-server"></a><span data-ttu-id="ec184-103">비즈니스용 Skype 서버에서 모니터링 대시보드 사용</span><span class="sxs-lookup"><span data-stu-id="ec184-103">Using the Monitoring Dashboard in Skype for Business Server</span></span>
 
<span data-ttu-id="ec184-104">**요약:** 비즈니스용 Skype 서버의 모니터링 대시보드에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="ec184-104">**Summary:** Learn about the Monitoring Dashboard in Skype for Business Server.</span></span>
  
<span data-ttu-id="ec184-105">모니터링 대시보드는 관리자에게 비즈니스용 Skype 서버 시스템 상태 및 시스템 사용 현황에 대한 간략한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ec184-105">The Monitoring Dashboard provides administrators with a quick overview of their Skype for Business Server system health and system usage.</span></span> <span data-ttu-id="ec184-106">이 대시보드는 다음 중 하나를 표시하여 주요 시스템 메트릭을 요약하여 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ec184-106">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>
  
- <span data-ttu-id="ec184-107">현재 날짜의 요약.</span><span class="sxs-lookup"><span data-stu-id="ec184-107">Totals for the current day.</span></span> <span data-ttu-id="ec184-108">현재 날짜에 대해 표시되는 값은 현재 시간(보고 서버의 현지 시간 기준)까지 자정부터 기록된 데이터를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ec184-108">Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server).</span></span> <span data-ttu-id="ec184-109">다시 말해서 일반적으로 하루 중 24시간이 아니라 몇 시간 동안의 데이터를 보게 된다는 뜻입니다.</span><span class="sxs-lookup"><span data-stu-id="ec184-109">That means that you will typically be viewing data for a partial day and not for a 24-hour period.</span></span> <span data-ttu-id="ec184-110">예를 들어 서버의 로컬 시간이 오전 8:00이면 자정과 현재 오전 8시 사이에 8시간이 있기 때문에 8시간의 데이터가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ec184-110">For example, if the local time of the server is 8:00 AM, you see eight hours' worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>
    
- <span data-ttu-id="ec184-111">일주일의 요약과 지난 6주의 추세 요약</span><span class="sxs-lookup"><span data-stu-id="ec184-111">Totals for the week, and trend totals for the past six weeks.</span></span>
    
- <span data-ttu-id="ec184-112">현재 달의 요약과 지난 6개월의 추세 요약(시스템 사용에만 해당)</span><span class="sxs-lookup"><span data-stu-id="ec184-112">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>
    
<span data-ttu-id="ec184-113">[Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) cmdlet을 사용하여 비즈니스용 Skype 서버 모니터링 보고서에 액세스하는 데 사용되는 URL을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec184-113">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) cmdlet to return the URL used for accessing Skype for Business Server Monitoring Reports:</span></span>
  
```PowerShell
Get-CsReportingConfiguration
```

<span data-ttu-id="ec184-114">기본적으로 모니터링 대시보드는 현재 주에 대한 다음 메트릭 데이터와 지난 6주의 추세 요약을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ec184-114">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>
  
## <a name="system-usage-metrics"></a><span data-ttu-id="ec184-115">시스템 사용 메트릭</span><span class="sxs-lookup"><span data-stu-id="ec184-115">System Usage Metrics</span></span>

 <span data-ttu-id="ec184-116">**등록**</span><span class="sxs-lookup"><span data-stu-id="ec184-116">**Registration**</span></span>
  
- <span data-ttu-id="ec184-117">고유 사용자 로그온</span><span class="sxs-lookup"><span data-stu-id="ec184-117">Unique user logons</span></span>
    
  <span data-ttu-id="ec184-118">**피어 투 피어**</span><span class="sxs-lookup"><span data-stu-id="ec184-118">**Peer-to-peer**</span></span>
  
- <span data-ttu-id="ec184-119">총 세션</span><span class="sxs-lookup"><span data-stu-id="ec184-119">Total sessions</span></span>
    
- <span data-ttu-id="ec184-120">IM 세션</span><span class="sxs-lookup"><span data-stu-id="ec184-120">IM sessions</span></span>
    
- <span data-ttu-id="ec184-121">오디오 세션</span><span class="sxs-lookup"><span data-stu-id="ec184-121">Audio sessions</span></span>
    
- <span data-ttu-id="ec184-122">비디오 세션</span><span class="sxs-lookup"><span data-stu-id="ec184-122">Video sessions</span></span>
    
- <span data-ttu-id="ec184-123">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="ec184-123">Application sharing</span></span>
    
- <span data-ttu-id="ec184-124">총 오디오 세션 시간(분)</span><span class="sxs-lookup"><span data-stu-id="ec184-124">Total audio session minutes</span></span>
    
- <span data-ttu-id="ec184-125">평균 오디오 세션 시간(분)</span><span class="sxs-lookup"><span data-stu-id="ec184-125">Avg. audio session minutes</span></span>
    
  <span data-ttu-id="ec184-126">**회의**</span><span class="sxs-lookup"><span data-stu-id="ec184-126">**Conference**</span></span>
  
- <span data-ttu-id="ec184-127">총 전화 회의</span><span class="sxs-lookup"><span data-stu-id="ec184-127">Total conferences</span></span>
    
- <span data-ttu-id="ec184-128">IM 전화 회의</span><span class="sxs-lookup"><span data-stu-id="ec184-128">IM conferences</span></span>
    
- <span data-ttu-id="ec184-129">A/V 회의</span><span class="sxs-lookup"><span data-stu-id="ec184-129">A/V conferences</span></span>
    
- <span data-ttu-id="ec184-130">응용 프로그램 공유 전화 회의</span><span class="sxs-lookup"><span data-stu-id="ec184-130">Application sharing conferences</span></span>
    
- <span data-ttu-id="ec184-131">웹 회의</span><span class="sxs-lookup"><span data-stu-id="ec184-131">Web conferences</span></span>
    
- <span data-ttu-id="ec184-132">총 이끌이 수</span><span class="sxs-lookup"><span data-stu-id="ec184-132">Total organizers</span></span>
    
- <span data-ttu-id="ec184-133">총 A/V 회의 시간(분)</span><span class="sxs-lookup"><span data-stu-id="ec184-133">Total A/V conference minutes</span></span>
    
- <span data-ttu-id="ec184-134">평균 A/V 회의 시간(분)</span><span class="sxs-lookup"><span data-stu-id="ec184-134">Avg. A/V conference minutes</span></span>
    
- <span data-ttu-id="ec184-135">총 PSTN 전화 회의</span><span class="sxs-lookup"><span data-stu-id="ec184-135">Total PSTN conferences</span></span>
    
- <span data-ttu-id="ec184-136">총 PSTN 참가자</span><span class="sxs-lookup"><span data-stu-id="ec184-136">Total PSTN participants</span></span>
    
- <span data-ttu-id="ec184-137">총 PSTN 참가 시간(분)</span><span class="sxs-lookup"><span data-stu-id="ec184-137">Total PSTN participant minutes</span></span>
    
<span data-ttu-id="ec184-138">시스템 사용 메트릭 외에도, 다음 메트릭이 현재 날짜와 지난 6일(**주별 보기** 를 선택한 경우) 또는 현재 주와 지난 6주(**월별 보기** 를 선택한 경우)의 요약을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ec184-138">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>
  
## <a name="per-user-call-diagnostics"></a><span data-ttu-id="ec184-139">사용자당 통화 진단</span><span class="sxs-lookup"><span data-stu-id="ec184-139">Per-User Call Diagnostics</span></span>

 <span data-ttu-id="ec184-140">**통화 실패 사용자**</span><span class="sxs-lookup"><span data-stu-id="ec184-140">**Users with call failures**</span></span>
  
- <span data-ttu-id="ec184-141">총 통화 실패 사용자</span><span class="sxs-lookup"><span data-stu-id="ec184-141">Total users with call failures</span></span>
    
- <span data-ttu-id="ec184-142">통화 실패 전화 회의 이끌이</span><span class="sxs-lookup"><span data-stu-id="ec184-142">Conference organizers with call failures</span></span>
    
  <span data-ttu-id="ec184-143">**저품질 통화 사용자**</span><span class="sxs-lookup"><span data-stu-id="ec184-143">**Users with poor quality calls**</span></span>
  
- <span data-ttu-id="ec184-144">총 저품질 통화 사용자</span><span class="sxs-lookup"><span data-stu-id="ec184-144">Total users with poor quality calls</span></span>
    
## <a name="call-diagnostics"></a><span data-ttu-id="ec184-145">통화 진단</span><span class="sxs-lookup"><span data-stu-id="ec184-145">Call Diagnostics</span></span>

<span data-ttu-id="ec184-146">피어 투 피어</span><span class="sxs-lookup"><span data-stu-id="ec184-146">Peer-to-peer</span></span>
  
- <span data-ttu-id="ec184-147">총 실패</span><span class="sxs-lookup"><span data-stu-id="ec184-147">Total failures</span></span>
    
- <span data-ttu-id="ec184-148">전체 실패율</span><span class="sxs-lookup"><span data-stu-id="ec184-148">Overall failure rate</span></span>
    
- <span data-ttu-id="ec184-149">IM 실패율</span><span class="sxs-lookup"><span data-stu-id="ec184-149">IM failure rate</span></span>
    
- <span data-ttu-id="ec184-150">오디오 실패율</span><span class="sxs-lookup"><span data-stu-id="ec184-150">Audio failure rate</span></span>
    
- <span data-ttu-id="ec184-151">응용 프로그램 공유 실패율</span><span class="sxs-lookup"><span data-stu-id="ec184-151">Application sharing failure rate</span></span>
    
<span data-ttu-id="ec184-152">회의</span><span class="sxs-lookup"><span data-stu-id="ec184-152">Conference</span></span>
  
- <span data-ttu-id="ec184-153">총 실패</span><span class="sxs-lookup"><span data-stu-id="ec184-153">Total failures</span></span>
    
- <span data-ttu-id="ec184-154">전체 실패율</span><span class="sxs-lookup"><span data-stu-id="ec184-154">Overall failure rate</span></span>
    
- <span data-ttu-id="ec184-155">IM 실패율</span><span class="sxs-lookup"><span data-stu-id="ec184-155">IM failure rate</span></span>
    
- <span data-ttu-id="ec184-156">A/V 실패율</span><span class="sxs-lookup"><span data-stu-id="ec184-156">A/V failure rate</span></span>
    
- <span data-ttu-id="ec184-157">응용 프로그램 공유 실패율</span><span class="sxs-lookup"><span data-stu-id="ec184-157">Application sharing failure rate</span></span>
    
<span data-ttu-id="ec184-158">실패 세션 기준의 상위 상위 5 서버</span><span class="sxs-lookup"><span data-stu-id="ec184-158">Top five servers by failed sessions</span></span>
  
## <a name="media-quality-diagnostics"></a><span data-ttu-id="ec184-159">미디어 품질 진단</span><span class="sxs-lookup"><span data-stu-id="ec184-159">Media Quality Diagnostics</span></span>

<span data-ttu-id="ec184-160">피어 투 피어</span><span class="sxs-lookup"><span data-stu-id="ec184-160">Peer-to-peer</span></span>
  
- <span data-ttu-id="ec184-161">총 저품질 통화</span><span class="sxs-lookup"><span data-stu-id="ec184-161">Total poor quality calls</span></span>
    
- <span data-ttu-id="ec184-162">저품질 통화율</span><span class="sxs-lookup"><span data-stu-id="ec184-162">Poor quality call percentage</span></span>
    
- <span data-ttu-id="ec184-163">저품질 PSTN 통화</span><span class="sxs-lookup"><span data-stu-id="ec184-163">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="ec184-164">회의</span><span class="sxs-lookup"><span data-stu-id="ec184-164">Conference</span></span>
  
- <span data-ttu-id="ec184-165">총 저품질 통화</span><span class="sxs-lookup"><span data-stu-id="ec184-165">Total poor quality calls</span></span>
    
- <span data-ttu-id="ec184-166">저품질 통화율</span><span class="sxs-lookup"><span data-stu-id="ec184-166">Poor quality call percentage</span></span>
    
- <span data-ttu-id="ec184-167">저품질 PSTN 통화</span><span class="sxs-lookup"><span data-stu-id="ec184-167">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="ec184-168">저품질 통화율 기준의 최하위 서버</span><span class="sxs-lookup"><span data-stu-id="ec184-168">Top worst servers by poor quality call percentage</span></span>
  
## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="ec184-169">모니터링 대시보드 작업</span><span class="sxs-lookup"><span data-stu-id="ec184-169">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="ec184-p103">앞에서 설명했듯이 기본적으로는 현재 주의 요약과 지난 6주의 추세 값이 표시됩니다. 현재 달의 요약과 지난 6주의 추세 값을 보려는 경우 대시보드의 오른쪽 위에 있는 **월별 보기** 링크를 클릭합니다. 월별 요약을 보기로 결정하면 링크 텍스트가 **주별 보기** 로 바뀝니다. 이 링크를 클릭하여 주별 보기로 다시 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec184-p103">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks. If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard. If you decide to view monthly totals, the link text will change to **Weekly View**. You can switch back to the weekly view by clicking that link.</span></span>
  
> [!TIP]
> <span data-ttu-id="ec184-p104">모니터링 대시보드에서는 현재 주 또는 월의 요약과 지난 6주 또는 개월의 추세 값만 볼 수 있으며 이러한 날짜 및 시간을 변경할 수는 없습니다. 예를 들어 대시보드를 사용하여 9개월 전부터 시작하는 기간에 대한 보고서 요약을 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec184-p104">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months). You cannot change these dates and times. For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span> 
  
<span data-ttu-id="ec184-p105">**이번 주**, **이 달** 또는 **오늘** 열에 표시된 값은 해당 항목에 대한 자세한 정보에 연결됩니다. 열 이름과 해당 열에 표시되는 값은 대개 선택한 메트릭과 주별 보기를 선택했는지 아니면 월별 보기를 선택했는지에 따라 달라집니다. 예를 들어 **고유 사용자 로그온** 메트릭에 대해 표시된 요약을 클릭하면 지정된 기간에 대한 **사용자 등록 보고서** 가 표시됩니다. 언제라도 **대시보드** 를 클릭하여 모니터링 대시보드로 돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec184-p105">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item. Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view. For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period. You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>
  
> [!TIP]
> <span data-ttu-id="ec184-181">대시보드의 오른쪽 위 모서리에 있는 보고서 링크를  클릭하여 모니터링 서버 보고서 홈 페이지에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec184-181">You can also access the Monitoring Server Reports home page by clicking the **Reports** link in the upper right corner of the Dashboard.</span></span>
  
<span data-ttu-id="ec184-182">**추세** 열에는 지난 6주(또는 메트릭과 시간 간격에 따라 지난 6일 또는 지난 6개월)의 요약이 표시되는 한 줄 그래프가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec184-182">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months).</span></span> <span data-ttu-id="ec184-183">이 한 줄 그래프에는 각 기간에 대한 레이블이 없는 데이터 요소(예: 지난 6주의 각 주에 대한 레이블이 없는 데이터 요소)이 하나씩 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec184-183">These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks).</span></span> <span data-ttu-id="ec184-184">그러나 그래프를 마우스 포인터로 가리켜서 그래프에 대한 실제 값을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec184-184">However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph.</span></span> <span data-ttu-id="ec184-185">이 경우 도구 팁에는 그래프의 최대값과 최소값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec184-185">In that case, a tool tip shows you the maximum and minimum values in the graph.</span></span>
  
## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="ec184-186">모니터링 대시보드에서 데이터 내보내기</span><span class="sxs-lookup"><span data-stu-id="ec184-186">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="ec184-p107">모니터링 대시보드는 현재 대시보드 보기를 내보내는 다양한 방법을 제공합니다. 대시보드 도구 모음에는 녹색 화살표가 붙은 플로피 디스크처럼 보이는 아이콘이 있습니다. 이 아이콘을 클릭하면 다음과 같은 데이터 내보내기 형식을 제공하는 드롭다운 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec184-p107">The Monitoring Dashboard provides a number of ways to export the current dashboard view. On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it. If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>
  
- <span data-ttu-id="ec184-190">보고서 데이터를 포함하는 XML 파일</span><span class="sxs-lookup"><span data-stu-id="ec184-190">XML file with report data</span></span>
    
- <span data-ttu-id="ec184-191">CSV(쉼표로 구분됨)</span><span class="sxs-lookup"><span data-stu-id="ec184-191">CSV (comma delimited)</span></span>
    
- <span data-ttu-id="ec184-192">PDF</span><span class="sxs-lookup"><span data-stu-id="ec184-192">PDF</span></span>
    
- <span data-ttu-id="ec184-193">MHTML(웹 보관)</span><span class="sxs-lookup"><span data-stu-id="ec184-193">MHTML (web archive)</span></span>
    
- <span data-ttu-id="ec184-194">Excel</span><span class="sxs-lookup"><span data-stu-id="ec184-194">Excel</span></span>
    
- <span data-ttu-id="ec184-195">TIFF 파일</span><span class="sxs-lookup"><span data-stu-id="ec184-195">TIFF file</span></span>
    
- <span data-ttu-id="ec184-196">Word</span><span class="sxs-lookup"><span data-stu-id="ec184-196">Word</span></span>
    
<span data-ttu-id="ec184-197">현재 대시보드 보기와 해당 값을 내보내려면 원하는 내보내기 옵션을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ec184-197">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="ec184-198">비즈니스용 Skype 서버는 지정된 형식으로 보고서를 생성한 다음 해당 보고서를 열거나 저장하는 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ec184-198">Skype for Business Server generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="ec184-199">기본적으로 비즈니스용 Skype 서버는 보고서 모니터링  대시보드의 제목을 지정하고 다운로드 폴더에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="ec184-199">Note that, by default, Skype for Business Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="ec184-200">보고서를 다른 이름으로 지정하거나 다른 폴더에 저장하려면 **저장** 단추 옆의 화살표를 클릭하고 **다른 이름으로 저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ec184-200">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="ec184-201">**모니터링 대시보드** 라는 이름을 그대로 사용하고 다운로드 폴더에 보고서를 저장하려면 **저장** 단추를 누르기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec184-201">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>
  
<span data-ttu-id="ec184-p109">대시보드 데이터를 내보내려고 할 때 **보안 경고** 대화 상자에 "현재의 보안 설정 때문에 이 파일을 다운로드할 수 없습니다."라는 메시지가 표시됩니다. 이 경우 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ec184-p109">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded." If that occurs, do the following:</span></span>
  
- <span data-ttu-id="ec184-204">Internet Explorer에서 **인터넷 옵션** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ec184-204">In Internet Explorer, select **Internet Options**.</span></span>
    
- <span data-ttu-id="ec184-205">**인터넷 옵션** 대화 상자의 **보안** 탭에서 **신뢰할 수 있는 사이트** 를 클릭하고 **사이트** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ec184-205">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>
    
- <span data-ttu-id="ec184-206">신뢰할 **수** 있는 사이트  대화 상자에서 추가를 클릭하여 비즈니스용 Skype 서버 보고서를 실행하는 비즈니스용 Skype 서버를 신뢰할 수 있는 웹 사이트 모음에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ec184-206">In the **Trusted sites** dialog box, click **Add** to add the Skype for Business Server that is running Skype for Business Server Reports to the collections of trusted websites.</span></span>
    
- <span data-ttu-id="ec184-207">**닫기** 를 클릭하고 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ec184-207">Click **Close** and then click **OK**.</span></span>
    
<span data-ttu-id="ec184-p110">그런 다음 F5 키를 누르거나 대시보드 도구 모음에서 **새로 고침** 아이콘을 클릭하여 모니터링 대시보드를 새로 고쳐야 변경 내용이 적용됩니다. **새로 고침** 아이콘은 한 쌍의 녹색 화살표가 있는 원 모양입니다.</span><span class="sxs-lookup"><span data-stu-id="ec184-p110">You will then need to refresh the Monitoring Dashboard before the changes take effect. To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar. (The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>
  
<span data-ttu-id="ec184-p111">라이브 데이터 피드를 포함하는 Excel 스프레드시트를 만들 수도 있습니다. 여기에는 최신 모니터링 대시보드 데이터에 대한 링크도 포함됩니다. 라이브 데이터 피드 파일을 만들려면 도구 모음에서 주황색의 **데이터 피드로 내보내기** 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ec184-p111">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data. To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>
  
<span data-ttu-id="ec184-213">현재 대시보드를 인쇄하려면 도구 모음에서 프린터 아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ec184-213">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>
  

