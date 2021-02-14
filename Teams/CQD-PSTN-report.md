---
title: CQD PSTN 직접 라우팅 보고서 사용
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: siunies, fan.fan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Microsoft Teams CQD(통화 품질 대시보드) PSTN 직접 라우팅 보고서를 사용하여 Microsoft Teams에서 PSTN 통화를 모니터링하고 문제를 해결합니다.
ms.openlocfilehash: e4662d80dbba88c1049c7ef98569dae408ca9ba0
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583105"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a><span data-ttu-id="2335e-103">CQD PSTN 직접 라우팅 보고서 사용</span><span class="sxs-lookup"><span data-stu-id="2335e-103">Using the CQD PSTN Direct Routing report</span></span>

<span data-ttu-id="2335e-104">2020년 3월에 Microsoft Teams CQD(통화 품질 대시보드) PSTN 직접 라우팅 보고서가 다운로드 가능한 [CQD용 Power BI](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)쿼리 템플릿에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-104">New in March 2020, we've added a Microsoft Teams Call Quality Dashboard (CQD) PSTN Direct Routing report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


<span data-ttu-id="2335e-105">CQD PSTN 직접 라우팅 보고서(CQD PSTN 직접 라우팅 Report.pbit)는 PSTN 서비스의 사용 패턴 및 품질을 이해하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-105">The CQD PSTN Direct Routing report (CQD PSTN Direct Routing Report.pbit) helps you understand the usage patterns and quality of your PSTN services.</span></span> <span data-ttu-id="2335e-106">이 보고서를 사용하여 서비스 사용량, SBC(세션 테두리 컨트롤러), 전화 통신 서비스, 네트워크 매개 변수 및 네트워크 효율성 비율 세부 정보를 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-106">Use this report to monitor service usage, information about your Session Border Controller (SBC), the telephony service, network parameters, and Network Effectiveness Ratio details.</span></span> <span data-ttu-id="2335e-107">이 정보는 호출이 떨어진 이유를 포함하여 문제를 식별하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-107">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="2335e-108">예를 들어 볼륨이 떨어질 때 또는 영향을 받는 호출 수와 그 이유를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-108">For example, you'll be able to see when volume drops, or how many calls get affected and for what reason.</span></span>


<span data-ttu-id="2335e-109">CQD PSTN 직접 라우팅 보고서에는 다음 네 가지 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-109">The CQD PSTN Direct Routing Report has four sections:</span></span>

  - [<span data-ttu-id="2335e-110">PSTN 개요</span><span class="sxs-lookup"><span data-stu-id="2335e-110">PSTN Overview</span></span>](#pstn-overview)

  - [<span data-ttu-id="2335e-111">서비스 세부 정보</span><span class="sxs-lookup"><span data-stu-id="2335e-111">Service Details</span></span>](#service-details)

  - [<span data-ttu-id="2335e-112">네트워크 효과 비율</span><span class="sxs-lookup"><span data-stu-id="2335e-112">Network Effectiveness Ratio</span></span>](#network-effectiveness-ratio)

  - [<span data-ttu-id="2335e-113">네트워크 매개 변수</span><span class="sxs-lookup"><span data-stu-id="2335e-113">Network Parameters</span></span>](#network-parameters)

## <a name="highlights"></a><span data-ttu-id="2335e-114">주요</span><span class="sxs-lookup"><span data-stu-id="2335e-114">Highlights</span></span>

1. <span data-ttu-id="2335e-115">통화 유형, SBC, 발신자 및 발신자 국가별로 분석</span><span class="sxs-lookup"><span data-stu-id="2335e-115">Analyze by call type, SBC, caller and callee country</span></span>

   <span data-ttu-id="2335e-116">CQD PSTN 직접 라우팅 보고서는 지난 7, 30 또는 180일(6개월) 동안 테넌트의 모든 SBC에 대한 안정성 및 사용 메트릭을 집계합니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-116">The CQD PSTN Direct Routing report aggregates reliability and usage metrics for all SBCs on your tenant for the last 7, 30, or 180 days (6 months).</span></span> <span data-ttu-id="2335e-117">통화 유형, SBC, 발신자 및 발신자 국가별로 데이터를 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-117">You can analyze data by call type, SBC, caller and callee country.</span></span> <span data-ttu-id="2335e-118">특정 SBC 또는 국가에 관심이 있는 경우 선택한 시간 범위에 대한 추세 변경 내용을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-118">If you're interested in a particular SBC or country, you'll be able to identify changes in trends over the selected time range.</span></span>
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="CQD PSTN 직접 라우팅 보고서에서 사용할 수 있는 필터 스크린샷":::
   
2. <span data-ttu-id="2335e-120">추세 추적</span><span class="sxs-lookup"><span data-stu-id="2335e-120">Track trends</span></span>

    <span data-ttu-id="2335e-121">추세 분석은 서비스 사용 및 안정성을 이해하려고 할 때 필수적입니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-121">Trends analysis is essential when trying to understand service usage and reliability.</span></span> <span data-ttu-id="2335e-122">시간별 추세는 실시간 인시던트 식별에 도움이 되는 일별 성능을 밀밀하게 살펴 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-122">Hourly trends provide a close look at daily performance, which helps identify real-time incidents.</span></span> <span data-ttu-id="2335e-123">일별 추세를 통해 장기적인 관점에서 서비스 상태도 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-123">Daily trends let you see your service health from a long-term perspective.</span></span> <span data-ttu-id="2335e-124">적절한 데이터 세분성으로 이러한 두 모드 간에 전환할 수 있는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-124">It's important to be able to shift between those two modes with appropriate data granularity.</span></span> <span data-ttu-id="2335e-125">CQD PSTN 직접 라우팅 보고서는 각 수준에서 성능을 분석할 수 있도록 6개월 추세 개요, 7일 및 30일간의 일별 추세 및 시간별 추세를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-125">The CQD PSTN Direct Routing report provides 6-month trends overview, 7- and 30-day daily trends, and hourly trends so you can analyze performance at each level.</span></span>
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="CQD PSTN 직접 라우팅 보고서의 추세 그래프 스크린샷":::

3. <span data-ttu-id="2335e-127">SBC 또는 사용자 수준으로 드릴스루</span><span class="sxs-lookup"><span data-stu-id="2335e-127">Drill through to SBC or user level</span></span>

   <span data-ttu-id="2335e-128">CQD의 많은 데이터 범주에 대한 드릴스루 기능을 구축하여 SBC 또는 사용자 수준에서 사용 또는 안정성 배포를 빠르게 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-128">We've been building in drill-through capability on many data categories in CQD, which lets you quickly understand usage or reliability distribution at the SBC or user level.</span></span> <span data-ttu-id="2335e-129">드릴스루를 사용하여 문제를 신속하게 파악하고 실제 사용자 영향을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-129">By using drill through, you can quickly poinpoint issues and understand real user impact.</span></span> <span data-ttu-id="2335e-130">CQD PSTN 직접 라우팅 보고서 기능은 서비스 세부 정보 및 네트워크 효율성 비율 메트릭을 자세히 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-130">The CQD PSTN Direct Routing report features drill through on the Service Detail and Network Effectiveness Ratio metrics.</span></span> <span data-ttu-id="2335e-131">관심 있는 데이터 지점을 클릭하여 SBC 또는 사용자 수준 세부 정보로 드릴스루합니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-131">Click the data point you're interested in to drill through to SBC- or user-level details.</span></span>
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="데이터 지점의 드릴스루 기능을 보여주는 스크린샷":::


## <a name="pstn-overview"></a><span data-ttu-id="2335e-133">PSTN 개요</span><span class="sxs-lookup"><span data-stu-id="2335e-133">PSTN Overview</span></span>

<span data-ttu-id="2335e-134">CQD PSTN 직접 라우팅 보고서는 지난 180일 동안의 서비스의 전반적인 상태와 관련된 다음 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-134">The CQD PSTN Direct Routing Report provides the following information related to overall health of the service for the past 180 days.</span></span>
<span data-ttu-id="2335e-135">![스크린샷: PSTN CQD 보고서](media/CQD-PSTN-report1.png)</span><span class="sxs-lookup"><span data-stu-id="2335e-135">![Screenshot: PSTN CQD report](media/CQD-PSTN-report1.png)</span></span>

<span data-ttu-id="2335e-136">예를 들어 SBC abc.bca.adatum.biz 통해 진행되는 모든 인바운드 호출에 대한 전반적인 사용량 및 상태는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-136">For example, if you are interested in the overall usage and health about all inbound calls going through SBC abc.bca.adatum.biz with US as the internal country:</span></span>

| <span data-ttu-id="2335e-137">**통화**</span><span class="sxs-lookup"><span data-stu-id="2335e-137">**Call Out**</span></span> | <span data-ttu-id="2335e-138">**설명**</span><span class="sxs-lookup"><span data-stu-id="2335e-138">**Description**</span></span>                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="2335e-139">1</span><span class="sxs-lookup"><span data-stu-id="2335e-139">1</span></span>            | <span data-ttu-id="2335e-140">맨 위에 있는 필터를 사용하여 ByotIn을 호출 유형으로 드릴다운하고, 세션 abc.bca.contoso.com 컨트롤러로, 미국을 내부 국가로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-140">You can use the filters at the top to drill down and select ByotIn as call type, abc.bca.contoso.com as Session Boarder Controller, and US as internal country.</span></span> |
| <span data-ttu-id="2335e-141">2</span><span class="sxs-lookup"><span data-stu-id="2335e-141">2</span></span>            | <span data-ttu-id="2335e-142">지난 180일 동안의 사용량 추세입니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-142">Usage trend for the past 180 days.</span></span> <span data-ttu-id="2335e-143">서비스 세부 정보 페이지에서 사용량 세부 정보 보고서를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-143">You can find usage detail report on Service Detail page.</span></span>                                                                     |
| <span data-ttu-id="2335e-144">3</span><span class="sxs-lookup"><span data-stu-id="2335e-144">3</span></span>            | <span data-ttu-id="2335e-145">지난 180일 동안의 사후 다이얼 지연, 대기 시간, 지터 및 패킷 손실 추세입니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-145">Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days.</span></span> <span data-ttu-id="2335e-146">네트워크 매개 변수 페이지에서 세부 정보 보고서를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-146">You can find detail report on Network Parameters page.</span></span>                           |
| <span data-ttu-id="2335e-147">4</span><span class="sxs-lookup"><span data-stu-id="2335e-147">4</span></span>            | <span data-ttu-id="2335e-148">지난 180일 동안의 동시 통화 및 일일 활성 사용자 추세입니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-148">Concurrent Call and Daily Active User trend for the past 180 days.</span></span> <span data-ttu-id="2335e-149">이 차트는 서비스의 최대 볼륨을 이해하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-149">This chart can help you understand the max volume of the service.</span></span>                            |
| <span data-ttu-id="2335e-150">5</span><span class="sxs-lookup"><span data-stu-id="2335e-150">5</span></span>            | <span data-ttu-id="2335e-151">지난 180일 동안 서비스 품질에 영향을 주는 상위 호출 종료 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-151">Top Call End Reason affected service quality for the past 180 days.</span></span> <span data-ttu-id="2335e-152">NER(네트워크 유효 비율) 페이지에서 서비스 상태 세부 정보를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-152">You can find service health detail on Network Effective Ratio(NER) page.</span></span>                    |

## <a name="service-details"></a><span data-ttu-id="2335e-153">서비스 세부 정보</span><span class="sxs-lookup"><span data-stu-id="2335e-153">Service Details</span></span>

<span data-ttu-id="2335e-154">이 페이지는 일별 서비스 사용량 추세 및 지리적으로 사용자 피드백 분석 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-154">This page provides service usage trends per day and user feedback breakdown by geographic.</span></span>

  - <span data-ttu-id="2335e-155">**총 시도 호출 –** 성공 및 실패 호출을 모두 포함하여 해당 시간 범위의 총 시도 호출</span><span class="sxs-lookup"><span data-stu-id="2335e-155">**Total Attempt Calls –** Total attempt calls in that time range, including both success and failed calls</span></span>

  - <span data-ttu-id="2335e-156">**연결된 총 통화 -** 이 시간 범위에 연결된 총 통화 수</span><span class="sxs-lookup"><span data-stu-id="2335e-156">**Total Connected Calls -** Total connected calls in that time range</span></span>

  - <span data-ttu-id="2335e-157">**총 시간(분) –** 이 시간 범위의 총 분 사용량</span><span class="sxs-lookup"><span data-stu-id="2335e-157">**Total Minutes –** Total minute usage in that time range</span></span>

  - <span data-ttu-id="2335e-158">**일일 활성 사용자(DAU) –** 해당 날에 하나 이상의 연결된 통화를 한 일별 활성 사용자 수</span><span class="sxs-lookup"><span data-stu-id="2335e-158">**Daily Active Users(DAU) –** Count of daily active user who made at least one connected call in that day</span></span>

  - <span data-ttu-id="2335e-159">**동시 호출 –** 1분에 최대 동시 활성 통화 수</span><span class="sxs-lookup"><span data-stu-id="2335e-159">**Concurrent Calls –** Max of simultaneous active calls in a minute</span></span>

  - <span data-ttu-id="2335e-160">**사용자 피드백 –** "내 통화 평가" 점수는 사용자가 제공한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-160">**User Feedback –** "Rate My Call" score comes from the user.</span></span> <span data-ttu-id="2335e-161">3-5는 좋은 호출로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-161">3-5 is considered as a good call.</span></span> <span data-ttu-id="2335e-162">1-2는 잘못된 호출로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-162">1-2 is considered as a bad call.</span></span>

![스크린샷: PSTN CQD 보고서](media/CQD-PSTN-report2.png)

<span data-ttu-id="2335e-164">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-164">For example:</span></span>

1.  <span data-ttu-id="2335e-165">2020년 2월 14일 02-14에 평균 통화 기간이 0으로 감소하는 경우 먼저 통화 볼륨이 정상으로 보이는지 확인하고 총 연결 호출과 총 시도 통화 간에 큰 불일치가 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-165">If you see average call duration drops to 0 at 02/14/2020, you can first check if the call volume looks normal and see if there is a big discrepancy between total connect calls and total attempt calls.</span></span> <span data-ttu-id="2335e-166">그런 다음, 네트워크 효율성 비율 페이지로 이동하여 호출 실패 이유에 투자합니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-166">Then go to Network Effectiveness Ratio page to invest on call failure reasons.</span></span>

2.  <span data-ttu-id="2335e-167">사용자 피드백 맵에 빨간색 지점이 증가하는 경우 네트워크 효과 비율 페이지 및 네트워크 매개 변수로 이동하여 문제가 발생하고 MS Service Desk를 사용하여 티켓을 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-167">If you see increasing red spots on the user feedback map, you could go to Network Effectiveness Ratio page and Network Parameter to see if there are any anomalies and you could raise a ticket using MS Service Desk.</span></span>

## <a name="network-effectiveness-ratio"></a><span data-ttu-id="2335e-168">네트워크 효과 비율</span><span class="sxs-lookup"><span data-stu-id="2335e-168">Network Effectiveness Ratio</span></span>

<span data-ttu-id="2335e-169">이는 전체 상태 대시보드에 나타나는 메트릭과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-169">This is the same metric that appears on the Overall Health dashboard.</span></span> <span data-ttu-id="2335e-170">아래의 시간당 네트워크 효과 비율 및 통화 종료 이유 차트에서 호출 방향(인바운드/아웃바운드)에 대한 영향을 받는 호출 세부 정보가 있는 시간당 NER 번호를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-170">You can check hourly NER number with affected calls detail for both call directions (inbound/outbound) on the Hourly network effectiveness ratio and call ending reason chart below.</span></span>

  - <span data-ttu-id="2335e-171">**NER** - 능력(%) 받는 사람에게 전달된 통화 수와 전송된 통화 수를 측정하여 전화를 배달할 네트워크의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-171">**NER** - The ability (%) of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>

  - <span data-ttu-id="2335e-172">**SIP 응답 코드**- 3자리 정수 응답 코드는 호출 상태를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-172">**SIP response code**- A three-digit integer response code shows the call status.</span></span>

  - <span data-ttu-id="2335e-173">**Microsoft 응답 코드**-Microsoft 구성 요소에서 보낸 응답 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-173">**Microsoft response code**-A response code sent out from Microsoft component.</span></span>

  - <span data-ttu-id="2335e-174">**설명** - SIP 응답 코드 및 Microsoft 응답 코드에 해당하는 이유 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-174">**Description** – The reason phase that corresponding to the SIP response code and Microsoft response code.</span></span>

  - <span data-ttu-id="2335e-175">**영향을 받는 호출** 수 - 선택한 시간 범위 동안 영향을 받은 총 호출 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-175">**Number of calls affected** – The total number of calls got affected during the selected time range.</span></span>

> ![스크린샷: PSTN CQD 보고서](media/CQD-PSTN-report3.png)
> 
<span data-ttu-id="2335e-177">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-177">For example:</span></span>

![스크린샷: PSTN CQD 보고서](media/CQD-PSTN-report4.png)

<span data-ttu-id="2335e-179">Daily NER에 2020/02/05의 하한이 있는 경우 날짜를 클릭하면 다른 차트가 해당 특정 날짜로 확대/축소됩니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-179">If Daily NER has a dip on 02/05/2020, you can click on the date and other charts will zoom to that specific date.</span></span>

![스크린샷: PSTN CQD 보고서](media/CQD-PSTN-report5.png)

<span data-ttu-id="2335e-181">NER 양호한 백분율 시간 추세에서 21:00 정도의 하향이 발생하는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-181">From the NER Good Percentage Hourly Trend, you can find the dip happens around 21:00.</span></span> <span data-ttu-id="2335e-182">그런 다음 다시 클릭하여 21시간으로 확대하고 적용된 통화 세부 정보를 확인하여 해당 시간 동안 실패한 호출 수와 통화 종료 이유가 어떻게 됐는가를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-182">Then click again to zoom to hour 21 and check Effected Call Details to see how many calls failed in that hour and what are the call end reasons.</span></span> <span data-ttu-id="2335e-183">문제가 SBC와 관련이 없는 경우 SBC 문제에 대해 자체 문제 해결을 시작하거나 Service Desk에 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-183">You can start with self-trouble shooting on any SBC problems or report to Service Desk if the problem is not related to SBC.</span></span>

## <a name="network-parameters"></a><span data-ttu-id="2335e-184">네트워크 매개 변수</span><span class="sxs-lookup"><span data-stu-id="2335e-184">Network Parameters</span></span>

<span data-ttu-id="2335e-185">모든 네트워크 매개 변수는 직접 라우팅 인터페이스에서 세션 테두리 컨트롤러로 측정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-185">All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="2335e-186">권장 값에 대한 자세한 내용은 [Microsoft Teams에](prepare-network.md)대한 조직의 네트워크 준비를 참조하고 고객 에지에서 Microsoft Edge로 권장되는 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-186">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

  - <span data-ttu-id="2335e-187">**Jitter** – RTCP(RTP 제어 프로토콜)를 사용하여 두 엔드포인트 간에 계산된 네트워크 전파 지연 시간의 변형을 밀리초 측정한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-187">**Jitter** – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

  - <span data-ttu-id="2335e-188">**패킷 손실** – 도착하지 못한 패킷의 측정값입니다. 두 엔드포인트 간에 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-188">**Packet Loss** – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

  - <span data-ttu-id="2335e-189">**대기 시간** -(왕복 시간)은 신호가 전송되는 데 걸리는 시간과 해당 신호의 수신을 수신하는 데 걸리는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-189">**Latency** - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="2335e-190">이 시간 지연은 신호의 두 지점 사이의 전파 시간으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-190">This time delay consists of the propagation times between the two points of a signal.</span></span>

> ![스크린샷: PSTN CQD 보고서](media/CQD-PSTN-report6.png)

<span data-ttu-id="2335e-192">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-192">For example:</span></span>

<span data-ttu-id="2335e-193">특정 날짜(예: 2020년 2월 14일의 대기 시간)에 대해 4개의 차트(대기 시간, 지터, 패키지 손실률, 사후 다이얼 지연)가 표시될 경우 날짜 지점을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-193">If you see a spike on any of the four charts (Latency, Jitter, Package Loss Rate, Post Dial Delay) for a specific date, for example, Latency on 02/14/2020, click on the date point.</span></span> <span data-ttu-id="2335e-194">아래쪽의 시간 추세 차트가 새로 고쳐지며 시간당 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-194">And the hourly trend chart at the bottom will refresh to show the hourly number.</span></span> <span data-ttu-id="2335e-195">SBC를 확인하거나 MS Service Desk를 사용하여 티켓을 제기할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2335e-195">You can check the SBCs or raise a ticket with MS Service Desk.</span></span>

![스크린샷: PSTN CQD 보고서](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a><span data-ttu-id="2335e-197">관련 항목</span><span class="sxs-lookup"><span data-stu-id="2335e-197">Related topics</span></span>

[<span data-ttu-id="2335e-198">Power BI를 사용하여 Microsoft Teams에 대한 CQD 데이터 분석</span><span class="sxs-lookup"><span data-stu-id="2335e-198">Use Power BI to analyze CQD data for Microsoft Teams</span></span>](CQD-PSTN-report.md)

[<span data-ttu-id="2335e-199">Teams 문제 해결</span><span class="sxs-lookup"><span data-stu-id="2335e-199">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)