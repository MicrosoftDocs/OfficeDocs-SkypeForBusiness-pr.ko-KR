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
description: Microsoft Teams 통화 품질 대시보드(CQD) PSTN 직접 라우팅 보고서를 사용하여 Microsoft Teams에서 PSTN 호출을 모니터링하고 문제를 해결합니다.
ms.openlocfilehash: f2b63f991f42aa4de9e0e4474137f7f992f95c53
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094982"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a><span data-ttu-id="8714b-103">CQD PSTN 직접 라우팅 보고서 사용</span><span class="sxs-lookup"><span data-stu-id="8714b-103">Using the CQD PSTN Direct Routing report</span></span>

<span data-ttu-id="8714b-104">2020년 3월에 Microsoft Teams 호출 품질 대시보드(CQD) PSTN 직접 라우팅 보고서가 다운로드 가능한 [CQD용 Power BI](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)쿼리 템플릿에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-104">New in March 2020, we've added a Microsoft Teams Call Quality Dashboard (CQD) PSTN Direct Routing report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


<span data-ttu-id="8714b-105">CQD PSTN 직접 라우팅 보고서(CQD PSTN 직접 라우팅 보고서.pbit)는 PSTN 서비스의 사용 패턴 및 품질을 이해하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-105">The CQD PSTN Direct Routing report (CQD PSTN Direct Routing Report.pbit) helps you understand the usage patterns and quality of your PSTN services.</span></span> <span data-ttu-id="8714b-106">이 보고서를 사용하여 서비스 사용량, SBC(세션 경계 컨트롤러), 전화 통신 서비스, 네트워크 매개 변수 및 네트워크 효과 비율 세부 정보를 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-106">Use this report to monitor service usage, information about your Session Border Controller (SBC), the telephony service, network parameters, and Network Effectiveness Ratio details.</span></span> <span data-ttu-id="8714b-107">이 정보는 호출이 삭제된 이유를 포함하여 문제를 식별하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-107">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="8714b-108">예를 들어 볼륨이 떨어지는 경우 또는 영향을 받는 호출 수 및 그 이유에 대해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-108">For example, you'll be able to see when volume drops, or how many calls get affected and for what reason.</span></span>


<span data-ttu-id="8714b-109">CQD PSTN 직접 라우팅 보고서에는 다음 네 가지 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-109">The CQD PSTN Direct Routing Report has four sections:</span></span>

  - [<span data-ttu-id="8714b-110">PSTN 개요</span><span class="sxs-lookup"><span data-stu-id="8714b-110">PSTN Overview</span></span>](#pstn-overview)

  - [<span data-ttu-id="8714b-111">서비스 세부 정보</span><span class="sxs-lookup"><span data-stu-id="8714b-111">Service Details</span></span>](#service-details)

  - [<span data-ttu-id="8714b-112">네트워크 효과 비율</span><span class="sxs-lookup"><span data-stu-id="8714b-112">Network Effectiveness Ratio</span></span>](#network-effectiveness-ratio)

  - [<span data-ttu-id="8714b-113">네트워크 매개 변수</span><span class="sxs-lookup"><span data-stu-id="8714b-113">Network Parameters</span></span>](#network-parameters)

## <a name="highlights"></a><span data-ttu-id="8714b-114">주요 특징</span><span class="sxs-lookup"><span data-stu-id="8714b-114">Highlights</span></span>

1. <span data-ttu-id="8714b-115">통화 유형, SBC, 발신자 및 발신자 국가별로 분석</span><span class="sxs-lookup"><span data-stu-id="8714b-115">Analyze by call type, SBC, caller and callee country</span></span>

   <span data-ttu-id="8714b-116">CQD PSTN 직접 라우팅 보고서는 지난 7, 30일 또는 180일(6개월) 동안 테넌트의 모든 SBC에 대한 안정성 및 사용 메트릭을 집계합니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-116">The CQD PSTN Direct Routing report aggregates reliability and usage metrics for all SBCs on your tenant for the last 7, 30, or 180 days (6 months).</span></span> <span data-ttu-id="8714b-117">통화 유형, SBC, 발신자 및 발신자 국가별로 데이터를 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-117">You can analyze data by call type, SBC, caller and callee country.</span></span> <span data-ttu-id="8714b-118">특정 SBC 또는 국가에 관심이 있는 경우 선택한 시간 범위에 대한 추세 변화를 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-118">If you're interested in a particular SBC or country, you'll be able to identify changes in trends over the selected time range.</span></span>
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="CQD PSTN 직접 라우팅 보고서에서 사용할 수 있는 필터 스크린샷":::
   
2. <span data-ttu-id="8714b-120">추세 추적</span><span class="sxs-lookup"><span data-stu-id="8714b-120">Track trends</span></span>

    <span data-ttu-id="8714b-121">서비스 사용 현황 및 안정성을 이해하려는 경우 추세 분석이 필수적입니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-121">Trends analysis is essential when trying to understand service usage and reliability.</span></span> <span data-ttu-id="8714b-122">시간별 추세는 실시간 인시던트 식별에 도움이 되는 일일 성능에 대해 잘 살펴 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-122">Hourly trends provide a close look at daily performance, which helps identify real-time incidents.</span></span> <span data-ttu-id="8714b-123">매일 추세를 통해 장기적인 관점에서 서비스 상태가 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-123">Daily trends let you see your service health from a long-term perspective.</span></span> <span data-ttu-id="8714b-124">적절한 데이터 세분성을 사용하여 두 모드 간에 전환할 수 있는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-124">It's important to be able to shift between those two modes with appropriate data granularity.</span></span> <span data-ttu-id="8714b-125">CQD PSTN 직접 라우팅 보고서는 각 수준에서 성능을 분석할 수 있도록 6개월 추세 개요, 7일 및 30일 일일 추세 및 시간별 추세를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-125">The CQD PSTN Direct Routing report provides 6-month trends overview, 7- and 30-day daily trends, and hourly trends so you can analyze performance at each level.</span></span>
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="CQD PSTN 직접 라우팅 보고서의 추세 그래프 스크린샷":::

3. <span data-ttu-id="8714b-127">SBC 또는 사용자 수준으로 드릴스루</span><span class="sxs-lookup"><span data-stu-id="8714b-127">Drill through to SBC or user level</span></span>

   <span data-ttu-id="8714b-128">CQD의 많은 데이터 범주에 대해 드릴스루 기능을 구축하여 SBC 또는 사용자 수준에서 사용 또는 안정성 배포를 빠르게 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-128">We've been building in drill-through capability on many data categories in CQD, which lets you quickly understand usage or reliability distribution at the SBC or user level.</span></span> <span data-ttu-id="8714b-129">드릴 스루를 사용하면 문제를 신속하게 포인포인트하고 실제 사용자 영향을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-129">By using drill through, you can quickly poinpoint issues and understand real user impact.</span></span> <span data-ttu-id="8714b-130">CQD PSTN 직접 라우팅 보고서는 서비스 세부 정보 및 네트워크 효과 비율 메트릭을 자세히 설명하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-130">The CQD PSTN Direct Routing report features drill through on the Service Detail and Network Effectiveness Ratio metrics.</span></span> <span data-ttu-id="8714b-131">관심 있는 데이터 지점을 클릭하여 SBC 또는 사용자 수준 세부 정보를 드릴링합니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-131">Click the data point you're interested in to drill through to SBC- or user-level details.</span></span>
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="데이터 지점에서 드릴스루 기능을 보여주는 스크린샷":::


## <a name="pstn-overview"></a><span data-ttu-id="8714b-133">PSTN 개요</span><span class="sxs-lookup"><span data-stu-id="8714b-133">PSTN Overview</span></span>

<span data-ttu-id="8714b-134">CQD PSTN 직접 라우팅 보고서는 지난 180일 동안 서비스의 전반적인 상태와 관련된 다음 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-134">The CQD PSTN Direct Routing Report provides the following information related to overall health of the service for the past 180 days.</span></span>
<span data-ttu-id="8714b-135">![스크린샷: PSTN CQD 보고서](media/CQD-PSTN-report1.png)</span><span class="sxs-lookup"><span data-stu-id="8714b-135">![Screenshot: PSTN CQD report](media/CQD-PSTN-report1.png)</span></span>

<span data-ttu-id="8714b-136">예를 들어 SBC를 통해 진행되는 모든 인바운드 호출에 대한 전체 사용 현황 및 상태에 관심이 abc.bca.adatum.biz 국가는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-136">For example, if you are interested in the overall usage and health about all inbound calls going through SBC abc.bca.adatum.biz with US as the internal country:</span></span>

| <span data-ttu-id="8714b-137">**통화**</span><span class="sxs-lookup"><span data-stu-id="8714b-137">**Call Out**</span></span> | <span data-ttu-id="8714b-138">**설명**</span><span class="sxs-lookup"><span data-stu-id="8714b-138">**Description**</span></span>                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="8714b-139">1</span><span class="sxs-lookup"><span data-stu-id="8714b-139">1</span></span>            | <span data-ttu-id="8714b-140">맨 위에 있는 필터를 사용하여 ByotIn을 호출 유형으로 드릴다운하고 선택할 수 있으며, 세션 abc.bca.contoso.com 컨트롤러로, 미국을 내부 국가로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-140">You can use the filters at the top to drill down and select ByotIn as call type, abc.bca.contoso.com as Session Boarder Controller, and US as internal country.</span></span> |
| <span data-ttu-id="8714b-141">2</span><span class="sxs-lookup"><span data-stu-id="8714b-141">2</span></span>            | <span data-ttu-id="8714b-142">지난 180일 동안의 사용량 추세입니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-142">Usage trend for the past 180 days.</span></span> <span data-ttu-id="8714b-143">서비스 세부 정보 페이지에서 사용 현황 세부 정보를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-143">You can find usage detail report on Service Detail page.</span></span>                                                                     |
| <span data-ttu-id="8714b-144">3</span><span class="sxs-lookup"><span data-stu-id="8714b-144">3</span></span>            | <span data-ttu-id="8714b-145">지난 180일 동안 전화 걸기 지연, 대기 시간, 지터 및 패킷 손실 추세를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-145">Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days.</span></span> <span data-ttu-id="8714b-146">네트워크 매개 변수 페이지에서 자세한 보고서를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-146">You can find detail report on Network Parameters page.</span></span>                           |
| <span data-ttu-id="8714b-147">4</span><span class="sxs-lookup"><span data-stu-id="8714b-147">4</span></span>            | <span data-ttu-id="8714b-148">지난 180일 동안 동시 통화 및 일일 활성 사용자 추세입니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-148">Concurrent Call and Daily Active User trend for the past 180 days.</span></span> <span data-ttu-id="8714b-149">이 차트는 서비스의 최대 볼륨을 이해하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-149">This chart can help you understand the max volume of the service.</span></span>                            |
| <span data-ttu-id="8714b-150">5</span><span class="sxs-lookup"><span data-stu-id="8714b-150">5</span></span>            | <span data-ttu-id="8714b-151">지난 180일 동안의 통화 종료 이유가 서비스 품질에 영향을 미쳤습니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-151">Top Call End Reason affected service quality for the past 180 days.</span></span> <span data-ttu-id="8714b-152">네트워크 유효 비율(NER) 페이지에서 서비스 상태 세부 정보를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-152">You can find service health detail on Network Effective Ratio(NER) page.</span></span>                    |

## <a name="service-details"></a><span data-ttu-id="8714b-153">서비스 세부 정보</span><span class="sxs-lookup"><span data-stu-id="8714b-153">Service Details</span></span>

<span data-ttu-id="8714b-154">이 페이지에서는 일별 서비스 사용량 추세 및 지리적으로 사용자 피드백 분석 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-154">This page provides service usage trends per day and user feedback breakdown by geographic.</span></span>

  - <span data-ttu-id="8714b-155">**총 시도 호출 –** 성공 및 실패한 호출을 포함하여 해당 시간 범위의 총 시도 호출</span><span class="sxs-lookup"><span data-stu-id="8714b-155">**Total Attempt Calls –** Total attempt calls in that time range, including both success and failed calls</span></span>

  - <span data-ttu-id="8714b-156">**총 연결된 통화 -** 이 시간 범위에서 연결된 총 통화</span><span class="sxs-lookup"><span data-stu-id="8714b-156">**Total Connected Calls -** Total connected calls in that time range</span></span>

  - <span data-ttu-id="8714b-157">**총 분 –** 이 시간 범위의 총 분 사용량</span><span class="sxs-lookup"><span data-stu-id="8714b-157">**Total Minutes –** Total minute usage in that time range</span></span>

  - <span data-ttu-id="8714b-158">**일일 활성 사용자(DAU) –** 해당 날에 하나 이상의 연결된 통화를 한 일별 활성 사용자 수</span><span class="sxs-lookup"><span data-stu-id="8714b-158">**Daily Active Users(DAU) –** Count of daily active user who made at least one connected call in that day</span></span>

  - <span data-ttu-id="8714b-159">**동시 통화 –** 1분에 최대 동시 활성 호출</span><span class="sxs-lookup"><span data-stu-id="8714b-159">**Concurrent Calls –** Max of simultaneous active calls in a minute</span></span>

  - <span data-ttu-id="8714b-160">**사용자 피드백 –** "내 통화 평가" 점수는 사용자가 제공한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-160">**User Feedback –** "Rate My Call" score comes from the user.</span></span> <span data-ttu-id="8714b-161">3-5는 좋은 호출로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-161">3-5 is considered as a good call.</span></span> <span data-ttu-id="8714b-162">1-2는 잘못된 호출로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-162">1-2 is considered as a bad call.</span></span>

![스크린샷: PSTN CQD 보고서](media/CQD-PSTN-report2.png)

<span data-ttu-id="8714b-164">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-164">For example:</span></span>

1.  <span data-ttu-id="8714b-165">평균 통화 시간이 02/14/2020에서 0으로 떨어지는 경우 먼저 통화 볼륨이 정상으로 보이는지 확인하고 총 연결 호출과 총 시도 호출 간에 큰 불일치가 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-165">If you see average call duration drops to 0 at 02/14/2020, you can first check if the call volume looks normal and see if there is a big discrepancy between total connect calls and total attempt calls.</span></span> <span data-ttu-id="8714b-166">그런 다음 네트워크 효과 비율 페이지로 이동하여 호출 실패 이유에 투자합니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-166">Then go to Network Effectiveness Ratio page to invest on call failure reasons.</span></span>

2.  <span data-ttu-id="8714b-167">사용자 피드백 맵에서 빨간색 반점 증가가 표시될 경우 네트워크 효과 비율 페이지 및 네트워크 매개 변수로 이동하여 문제가 발생하고 MS Service Desk를 사용하여 티켓을 올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-167">If you see increasing red spots on the user feedback map, you could go to Network Effectiveness Ratio page and Network Parameter to see if there are any anomalies and you could raise a ticket using MS Service Desk.</span></span>

## <a name="network-effectiveness-ratio"></a><span data-ttu-id="8714b-168">네트워크 효과 비율</span><span class="sxs-lookup"><span data-stu-id="8714b-168">Network Effectiveness Ratio</span></span>

<span data-ttu-id="8714b-169">이는 전체 상태 대시보드에 나타나는 메트릭과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-169">This is the same metric that appears on the Overall Health dashboard.</span></span> <span data-ttu-id="8714b-170">시간당 네트워크 효과 비율 및 아래 통화 종료 이유 차트에서 통화 방향(인바운드/아웃바운드)에 대한 영향을 받는 호출 세부 정보를 사용하여 시간당 NER 번호를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-170">You can check hourly NER number with affected calls detail for both call directions (inbound/outbound) on the Hourly network effectiveness ratio and call ending reason chart below.</span></span>

  - <span data-ttu-id="8714b-171">**NER** - 능력(%) 받는 사람에게 전달된 호출 수와 전송된 호출 수를 측정하여 호출을 배달하는 네트워크의 수를 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-171">**NER** - The ability (%) of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>

  - <span data-ttu-id="8714b-172">**SIP 응답 코드**- 3자리 정수 응답 코드에 호출 상태가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-172">**SIP response code**- A three-digit integer response code shows the call status.</span></span>

  - <span data-ttu-id="8714b-173">**Microsoft 응답 코드**-Microsoft 구성 요소에서 보낸 응답 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-173">**Microsoft response code**-A response code sent out from Microsoft component.</span></span>

  - <span data-ttu-id="8714b-174">**설명** - SIP 응답 코드 및 Microsoft 응답 코드에 해당하는 이유 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-174">**Description** – The reason phase that corresponding to the SIP response code and Microsoft response code.</span></span>

  - <span data-ttu-id="8714b-175">**영향을 받는 호출** 수 - 선택한 시간 범위 동안 총 호출 수가 영향을 미쳤습니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-175">**Number of calls affected** – The total number of calls got affected during the selected time range.</span></span>

> ![스크린샷: PSTN CQD 보고서](media/CQD-PSTN-report3.png)
> 
<span data-ttu-id="8714b-177">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-177">For example:</span></span>

![스크린샷: PSTN CQD 보고서](media/CQD-PSTN-report4.png)

<span data-ttu-id="8714b-179">Daily NER에 02/05/2020에 대한 축소가 있는 경우 날짜를 클릭할 수 있으며 다른 차트는 해당 특정 날짜로 확대됩니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-179">If Daily NER has a dip on 02/05/2020, you can click on the date and other charts will zoom to that specific date.</span></span>

![스크린샷: PSTN CQD 보고서](media/CQD-PSTN-report5.png)

<span data-ttu-id="8714b-181">NER 양호한 시간당 추세에서 21:00 정도의 디프가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-181">From the NER Good Percentage Hourly Trend, you can find the dip happens around 21:00.</span></span> <span data-ttu-id="8714b-182">그런 다음 다시 클릭하여 21시간으로 확대하고 적용된 통화 세부 정보를 확인하여 해당 시간에서 실패한 호출 수와 통화 종료 이유가 무엇인지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-182">Then click again to zoom to hour 21 and check Effected Call Details to see how many calls failed in that hour and what are the call end reasons.</span></span> <span data-ttu-id="8714b-183">문제가 SBC와 관련이 없는 경우 SBC 문제에서 자체 문제 촬영을 시작하거나 Service Desk에 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-183">You can start with self-trouble shooting on any SBC problems or report to Service Desk if the problem is not related to SBC.</span></span>

## <a name="network-parameters"></a><span data-ttu-id="8714b-184">네트워크 매개 변수</span><span class="sxs-lookup"><span data-stu-id="8714b-184">Network Parameters</span></span>

<span data-ttu-id="8714b-185">모든 네트워크 매개 변수는 직접 라우팅 인터페이스에서 세션 테두리 컨트롤러로 측정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-185">All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="8714b-186">권장 값에 대한 자세한 내용은 [Microsoft Teams에](prepare-network.md)대한 조직의 네트워크 준비를 참조하고 Microsoft Edge에 고객 Edge 권장 값을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-186">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

  - <span data-ttu-id="8714b-187">**Jitter** – RTCP(RTP 제어 프로토콜)를 사용하여 두 엔드포인트 간에 계산된 네트워크 전파 지연 시간의 변동을 밀리초 측정한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-187">**Jitter** – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

  - <span data-ttu-id="8714b-188">**패킷 손실** - 도착하지 못한 패킷의 측정값입니다. 두 엔드포인트 간에 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-188">**Packet Loss** – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

  - <span data-ttu-id="8714b-189">**대기 시간** - (왕복 시간으로도 알려져 있습니다)는 신호가 전송되는 데 걸리는 시간과 해당 신호의 수신을 위해 걸리는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-189">**Latency** - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="8714b-190">이 시간 지연은 신호의 두 지점 간의 전파 시간으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-190">This time delay consists of the propagation times between the two points of a signal.</span></span>

> ![스크린샷: PSTN CQD 보고서](media/CQD-PSTN-report6.png)

<span data-ttu-id="8714b-192">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-192">For example:</span></span>

<span data-ttu-id="8714b-193">특정 날짜(예: 2020/02/14의 대기 시간)에 대한 4개 차트(대기 시간, 지터, 패키지 손실율, 후 다이얼 지연)에 대한 스파이크가 표시될 경우 날짜 지점을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-193">If you see a spike on any of the four charts (Latency, Jitter, Package Loss Rate, Post Dial Delay) for a specific date, for example, Latency on 02/14/2020, click on the date point.</span></span> <span data-ttu-id="8714b-194">아래쪽의 시간당 추세 차트가 새로 고쳐지며 시간당 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-194">And the hourly trend chart at the bottom will refresh to show the hourly number.</span></span> <span data-ttu-id="8714b-195">SBC를 확인하거나 MS Service Desk를 사용하여 티켓을 인상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8714b-195">You can check the SBCs or raise a ticket with MS Service Desk.</span></span>

![스크린샷: PSTN CQD 보고서](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a><span data-ttu-id="8714b-197">관련 항목</span><span class="sxs-lookup"><span data-stu-id="8714b-197">Related topics</span></span>

[<span data-ttu-id="8714b-198">Power BI를 사용하여 Microsoft Teams에 대한 CQD 데이터 분석</span><span class="sxs-lookup"><span data-stu-id="8714b-198">Use Power BI to analyze CQD data for Microsoft Teams</span></span>](CQD-PSTN-report.md)

[<span data-ttu-id="8714b-199">Teams 문제 해결</span><span class="sxs-lookup"><span data-stu-id="8714b-199">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)