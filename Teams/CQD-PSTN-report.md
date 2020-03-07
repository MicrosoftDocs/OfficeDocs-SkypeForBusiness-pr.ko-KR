---
title: CQD PSTN 다이렉트 라우팅 보고서 사용
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: siunies
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
description: CQD PSTN 다이렉트 라우팅 보고서를 사용 하 여 Microsoft 팀에서 PSTN 통화를 모니터링 하 고 문제를 해결 하세요.
ms.openlocfilehash: 32d91d56e51c5706c3e460029312f3b6bb6948c3
ms.sourcegitcommit: 98fcfc03c55917d0aca48b7bd97988f81e8930c1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42559616"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a><span data-ttu-id="13d4a-103">CQD PSTN 다이렉트 라우팅 보고서 사용</span><span class="sxs-lookup"><span data-stu-id="13d4a-103">Using the CQD PSTN Direct Routing Report</span></span>

<span data-ttu-id="13d4a-104">2 월 2020 새 [cqd에 대 한 다운로드 가능한 POWER BI 쿼리 서식 파일](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)에 CQD PSTN 다이렉트 라우팅 보고서가 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-104">New in March 2020, we've added a CQD PSTN Direct Routing Report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


<span data-ttu-id="13d4a-105">CQD PSTN 다이렉트 라우팅 보고서는 사용자가 SBC, 전화 통신 서비스, 네트워크 매개 변수 및 네트워크 효율성 수준에 대 한 정보를 모니터 하는 데 도움이 되는 사용 패턴 및 품질에 대해 이해 하 고 있습니다. services.</span><span class="sxs-lookup"><span data-stu-id="13d4a-105">The CQD PSTN Direct Routing Report helps customers to understand the usage patterns and quality of their PSTN services monitor information about your SBC, the telephony service, the network parameters, and Network Effectiveness Ratio details and usage of the service.</span></span> <span data-ttu-id="13d4a-106">이 정보는 통화 제거 사유를 포함 하 여 문제를 식별 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-106">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="13d4a-107">예를 들어 볼륨을 언제까지 언제 얼마나 표시 되는지 알 수 있으며, 그 이유 때문에 발생 하는 통화 수는 얼마 입니까?</span><span class="sxs-lookup"><span data-stu-id="13d4a-107">For example, you will be able to know when volume drops, how many calls get affected by what reason.</span></span>

<span data-ttu-id="13d4a-108">CQD PSTN 다이렉트 라우팅 보고서에는 다음과 같은 네 가지 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-108">The CQD PSTN Direct Routing Report has four sections:</span></span>

  - [<span data-ttu-id="13d4a-109">PSTN 개요</span><span class="sxs-lookup"><span data-stu-id="13d4a-109">PSTN Overview</span></span>](#pstn-overview)

  - [<span data-ttu-id="13d4a-110">서비스 세부 정보</span><span class="sxs-lookup"><span data-stu-id="13d4a-110">Service Details</span></span>](#service-details)

  - [<span data-ttu-id="13d4a-111">네트워크 효율성 비율</span><span class="sxs-lookup"><span data-stu-id="13d4a-111">Network Effectiveness Ratio</span></span>](#network-effectiveness-ratio)

  - [<span data-ttu-id="13d4a-112">네트워크 매개 변수</span><span class="sxs-lookup"><span data-stu-id="13d4a-112">Network Parameters</span></span>](#network-parameters)

## <a name="pstn-overview"></a><span data-ttu-id="13d4a-113">PSTN 개요</span><span class="sxs-lookup"><span data-stu-id="13d4a-113">PSTN Overview</span></span>

<span data-ttu-id="13d4a-114">CQD PSTN 다이렉트 라우팅 보고서는 지난 180 일간 서비스의 전체 상태와 관련 된 다음과 같은 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-114">The CQD PSTN Direct Routing Report provides the following information related to overall health of the service for the past 180 days.</span></span>
<span data-ttu-id="13d4a-115">![스크린샷: PSTN CQD 보고서](media/CQD-PSTN-report1.png)</span><span class="sxs-lookup"><span data-stu-id="13d4a-115">![Screenshot: PSTN CQD report](media/CQD-PSTN-report1.png)</span></span>

<span data-ttu-id="13d4a-116">예를 들어 내부 국가를 미국으로 사용 하 여 SBC abc.bca.adatum.biz를 통과 하는 모든 인바운드 통화에 대 한 전반적인 사용 및 상태에 대해 관심이 있는 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-116">For example, if you are interested in the overall usage and health about all inbound calls going through SBC abc.bca.adatum.biz with US as the internal country:</span></span>

| <span data-ttu-id="13d4a-117">**전화 걸기**</span><span class="sxs-lookup"><span data-stu-id="13d4a-117">**Call Out**</span></span> | <span data-ttu-id="13d4a-118">**설명**</span><span class="sxs-lookup"><span data-stu-id="13d4a-118">**Description**</span></span>                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="13d4a-119">1</span><span class="sxs-lookup"><span data-stu-id="13d4a-119">1</span></span>            | <span data-ttu-id="13d4a-120">위쪽에 있는 필터를 사용 하 여 드릴 다운 하 고 통화 유형으로 In (abc.bca.contoso.com as 세션 Boarder 컨트롤러)을 선택 하 고 미국 내부 국가를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-120">You can use the filters at the top to drill down and select ByotIn as call type, abc.bca.contoso.com as Session Boarder Controller, and US as internal country.</span></span> |
| <span data-ttu-id="13d4a-121">2</span><span class="sxs-lookup"><span data-stu-id="13d4a-121">2</span></span>            | <span data-ttu-id="13d4a-122">지난 180 일간의 사용량 추세입니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-122">Usage trend for the past 180 days.</span></span> <span data-ttu-id="13d4a-123">서비스 세부 정보 페이지에 대 한 사용 세부 정보 보고서를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-123">You can find usage detail report on Service Detail page.</span></span>                                                                     |
| <span data-ttu-id="13d4a-124">3</span><span class="sxs-lookup"><span data-stu-id="13d4a-124">3</span></span>            | <span data-ttu-id="13d4a-125">지난 180 일간 전화 걸기 지연, 대기 시간, 지터, 패킷 손실 추세를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-125">Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days.</span></span> <span data-ttu-id="13d4a-126">네트워크 매개 변수 페이지에 대 한 상세 보고서를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-126">You can find detail report on Network Parameters page.</span></span>                           |
| <span data-ttu-id="13d4a-127">4(tcp/ipv4)</span><span class="sxs-lookup"><span data-stu-id="13d4a-127">4</span></span>            | <span data-ttu-id="13d4a-128">지난 180 일간 동시 통화 및 일일 활성 사용자 추이.</span><span class="sxs-lookup"><span data-stu-id="13d4a-128">Concurrent Call and Daily Active User trend for the past 180 days.</span></span> <span data-ttu-id="13d4a-129">이 차트는 서비스의 최대 볼륨을 이해 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-129">This chart can help you understand the max volume of the service.</span></span>                            |
| <span data-ttu-id="13d4a-130">5mb</span><span class="sxs-lookup"><span data-stu-id="13d4a-130">5</span></span>            | <span data-ttu-id="13d4a-131">지난 180 일간 서비스 품질에 영향을 주는 최고 통화 종료 이유.</span><span class="sxs-lookup"><span data-stu-id="13d4a-131">Top Call End Reason affected service quality for the past 180 days.</span></span> <span data-ttu-id="13d4a-132">NER (네트워크 유효 비율) 페이지에서 서비스 상태 세부 정보를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-132">You can find service health detail on Network Effective Ratio(NER) page.</span></span>                    |

## <a name="service-details"></a><span data-ttu-id="13d4a-133">서비스 세부 정보</span><span class="sxs-lookup"><span data-stu-id="13d4a-133">Service Details</span></span>

<span data-ttu-id="13d4a-134">이 페이지는 일일 서비스 사용 추세와 사용자 피드백 분석을 지역별로 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-134">This page provides service usage trends per day and user feedback breakdown by geographic.</span></span>

  - <span data-ttu-id="13d4a-135">**총 시도 통화 –** 해당 시간 범위 내에서 성공 및 실패 통화를 비롯 한 총 시도 통화</span><span class="sxs-lookup"><span data-stu-id="13d4a-135">**Total Attempt Calls –** Total attempt calls in that time range, including both success and failed calls</span></span>

  - <span data-ttu-id="13d4a-136">**총 연결 된 통화-** 해당 시간 범위의 총 연결 된 통화</span><span class="sxs-lookup"><span data-stu-id="13d4a-136">**Total Connected Calls -** Total connected calls in that time range</span></span>

  - <span data-ttu-id="13d4a-137">**총 통화 시간 –** 해당 시간 범위의 총 분 사용량</span><span class="sxs-lookup"><span data-stu-id="13d4a-137">**Total Minutes –** Total minute usage in that time range</span></span>

  - <span data-ttu-id="13d4a-138">**DAU (일일 활성 사용자)-** 해당 일에 하나 이상의 연결 된 통화를 만든 일일 활성 사용자 수</span><span class="sxs-lookup"><span data-stu-id="13d4a-138">**Daily Active Users(DAU) –** Count of daily active user who made at least one connected call in that day</span></span>

  - <span data-ttu-id="13d4a-139">**동시 통화-** 1 분 내에 동시 활성 통화 최대</span><span class="sxs-lookup"><span data-stu-id="13d4a-139">**Concurrent Calls –** Max of simultaneous active calls in a minute</span></span>

  - <span data-ttu-id="13d4a-140">**사용자 의견-** "내 통화 요금" 점수가 사용자에 게 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-140">**User Feedback –** "Rate My Call" score comes from the user.</span></span> <span data-ttu-id="13d4a-141">3-5는 좋은 통화로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-141">3-5 is considered as a good call.</span></span> <span data-ttu-id="13d4a-142">1-2는 불량 통화로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-142">1-2 is considered as a bad call.</span></span>

![스크린샷: PSTN CQD 보고서](media/CQD-PSTN-report2.png)

<span data-ttu-id="13d4a-144">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-144">For example:</span></span>

1.  <span data-ttu-id="13d4a-145">02/14/2020에서 평균 통화 시간이 0으로 떨어지면 먼저 통화 볼륨이 정상적으로 표시 되는지 확인 하 고 총 연결 통화와 총 시도 통화 사이에 큰 차이가 없는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-145">If you see average call duration drops to 0 at 02/14/2020, you can first check if the call volume looks normal and see if there is a big discrepancy between total connect calls and total attempt calls.</span></span> <span data-ttu-id="13d4a-146">그런 다음 네트워크 효율성 비율 페이지로 이동 하 여 통화 실패 원인에 투자 하세요.</span><span class="sxs-lookup"><span data-stu-id="13d4a-146">Then go to Network Effectiveness Ratio page to invest on call failure reasons.</span></span>

2.  <span data-ttu-id="13d4a-147">사용자 의견 지도에 빨간색 점이 더 표시 되는 경우 네트워크 효율성 비율 페이지 및 네트워크 매개 변수를 사용 하 여 문제가 있는지 확인 하 고 MS 서비스 데스크에서 티켓을 발생 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-147">If you see increasing red spots on the user feedback map, you could go to Network Effectiveness Ratio page and Network Parameter to see if there are any anomalies and you could raise a ticket using MS Service Desk.</span></span>

## <a name="network-effectiveness-ratio"></a><span data-ttu-id="13d4a-148">네트워크 효율성 비율</span><span class="sxs-lookup"><span data-stu-id="13d4a-148">Network Effectiveness Ratio</span></span>

<span data-ttu-id="13d4a-149">이 메트릭은 전체 상태 대시보드에 표시 되는 것과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-149">This is the same metric that appears on the Overall Health dashboard.</span></span> <span data-ttu-id="13d4a-150">매시간 네트워크 효율성 비율 및 통화 종료 이유 도표에 대 한 통화 지침 (인바운드/아웃 바운드)에 대 한 정보를 사용 하 여 매시간 NER 번호를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-150">You can check hourly NER number with affected calls detail for both call directions (inbound/outbound) on the Hourly network effectiveness ratio and call ending reason chart below.</span></span>

  - <span data-ttu-id="13d4a-151">**NER** -능력 (%) 수신자에 게 전달 되는 통화 수를 측정 하 여 전화를 전달 하는 네트워크의 경우</span><span class="sxs-lookup"><span data-stu-id="13d4a-151">**NER** - The ability (%) of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>

  - <span data-ttu-id="13d4a-152">**SIP 응답 코드**-3 자리 정수 응답 코드에는 통화 상태가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-152">**SIP response code**- A three-digit integer response code shows the call status.</span></span>

  - <span data-ttu-id="13d4a-153">**Microsoft 응답 코드**-microsoft component에서 전송 된 응답 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-153">**Microsoft response code**-A response code sent out from Microsoft component.</span></span>

  - <span data-ttu-id="13d4a-154">**설명** – SIP 응답 코드 및 Microsoft 응답 코드에 해당 하는 이유 단계</span><span class="sxs-lookup"><span data-stu-id="13d4a-154">**Description** – The reason phase that corresponding to the SIP response code and Microsoft response code.</span></span>

  - <span data-ttu-id="13d4a-155">**영향을 받는 통화 수** – 선택한 시간 범위 동안 영향을 받은 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-155">**Number of calls affected** – The total number of calls got affected during the selected time range.</span></span>

> ![스크린샷: PSTN CQD 보고서](media/CQD-PSTN-report3.png)
> 
<span data-ttu-id="13d4a-157">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-157">For example:</span></span>

![스크린샷: PSTN CQD 보고서](media/CQD-PSTN-report4.png)

<span data-ttu-id="13d4a-159">일일 NER에 02/05/2020의 dip가 있는 경우 해당 날짜를 클릭 하면 다른 차트가 해당 특정 날짜로 확대/축소 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-159">If Daily NER has a dip on 02/05/2020, you can click on the date and other charts will zoom to that specific date.</span></span>

![스크린샷: PSTN CQD 보고서](media/CQD-PSTN-report5.png)

<span data-ttu-id="13d4a-161">NER는 시간 기준 추세에 따라 21:00에서 dip가 발생 하는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-161">From the NER Good Percentage Hourly Trend, you can find the dip happens around 21:00.</span></span> <span data-ttu-id="13d4a-162">그런 다음 다시 클릭 하 여 21 시간으로 확대/축소 하 고 해당 시간에 실패 한 통화 수와 통화 종료 이유를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-162">Then click again to zoom to hour 21 and check Effected Call Details to see how many calls failed in that hour and what are the call end reasons.</span></span> <span data-ttu-id="13d4a-163">SBC 문제에 대 한 자체 문제 해결을 시작 하거나 문제가 SBC와 관련이 없는 경우 서비스 데스크에 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-163">You can start with self-trouble shooting on any SBC problems or report to Service Desk if the problem is not related to SBC.</span></span>

## <a name="network-parameters"></a><span data-ttu-id="13d4a-164">네트워크 매개 변수</span><span class="sxs-lookup"><span data-stu-id="13d4a-164">Network Parameters</span></span>

<span data-ttu-id="13d4a-165">모든 네트워크 매개 변수는 직접 라우팅 인터페이스에서 세션 경계 컨트롤러로 측정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-165">All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="13d4a-166">권장 값에 대 한 자세한 내용은 [Microsoft 팀 용 조직의 네트워크 준비](prepare-network.md)를 참조 하 고 고객 Edge에서 microsoft edge 추천 값을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="13d4a-166">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

  - <span data-ttu-id="13d4a-167">**지터** – RTCP (RTP 컨트롤 프로토콜)를 사용 하 여 두 끝점 간에 계산 된 네트워크 전파 지연 시간 변동의 밀리초 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-167">**Jitter** – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

  - <span data-ttu-id="13d4a-168">**패킷 손실** – 도착 하지 못한 패킷의 척도입니다. 두 끝점 간에 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-168">**Packet Loss** – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

  - <span data-ttu-id="13d4a-169">**지연** (라운드트립 시간이 라고도 함)은 신호가 전송 되는 데 걸리는 시간과 해당 신호를 수신 하는 데 걸리는 시간을 합한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-169">**Latency** - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="13d4a-170">이 시간 지연은 신호의 두 점 사이의 전파 시간으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-170">This time delay consists of the propagation times between the two points of a signal.</span></span>

> ![스크린샷: PSTN CQD 보고서](media/CQD-PSTN-report6.png)

<span data-ttu-id="13d4a-172">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-172">For example:</span></span>

<span data-ttu-id="13d4a-173">특정 날짜에 대 한 4 개의 차트 (대기 시간, 지터, 패키지 손실 속도, 전화 걸기 지연)에 스파이크가 표시 되는 경우 (예: 02/14/2020의 지연 시간)에는 날짜 지점을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-173">If you see a spike on any of the four charts (Latency, Jitter, Package Loss Rate, Post Dial Delay) for a specific date, for example, Latency on 02/14/2020, click on the date point.</span></span> <span data-ttu-id="13d4a-174">아래쪽에 있는 시간별 추세 도표를 새로 고치면 시간별 번호가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-174">And the hourly trend chart at the bottom will refresh to show the hourly number.</span></span> <span data-ttu-id="13d4a-175">MS 서비스 데스크를 사용 하 여 SBCs를 확인 하거나 티켓을 올릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13d4a-175">You can check the SBCs or raise a ticket with MS Service Desk.</span></span>

![스크린샷: PSTN CQD 보고서](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a><span data-ttu-id="13d4a-177">관련 항목</span><span class="sxs-lookup"><span data-stu-id="13d4a-177">Related topics</span></span>

[<span data-ttu-id="13d4a-178">Power BI를 사용 하 여 Microsoft 팀에 대 한 CQD 데이터 분석</span><span class="sxs-lookup"><span data-stu-id="13d4a-178">Use Power BI to analyze CQD data for Microsoft Teams</span></span>](CQD-PSTN-report.md)