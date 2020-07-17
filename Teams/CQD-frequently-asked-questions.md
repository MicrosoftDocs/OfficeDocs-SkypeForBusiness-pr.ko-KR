---
title: 통화 품질 대시보드 (CQD) 자주 묻는 질문 사항 (FAQ)
ms.author: lolaj
author: LolaJacobsen
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
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Microsoft 팀 통화 품질 대시보드 (CQD)에 대 한 질문과 대답 (FAQ) 및 답변을 읽으십시오.
ms.openlocfilehash: f33d66d9c8abb465c6680bacbbd2ff200cf930c6
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086174"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a><span data-ttu-id="c6598-103">통화 품질 대시보드 (CQD) 자주 묻는 질문 사항 (FAQ)</span><span class="sxs-lookup"><span data-stu-id="c6598-103">Call Quality Dashboard (CQD) Frequently asked questions (FAQ)</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="c6598-104">자주하는 질문</span><span class="sxs-lookup"><span data-stu-id="c6598-104">Frequently asked questions</span></span>

[<span data-ttu-id="c6598-105">하나 이상의 모임 참가자에 게 좋지 않은 경험이 있는 경우 CQD 님이 "좋은" 것으로 표시 되는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="c6598-105">Why does CQD mark a call as "Good" if one or more meeting participants had a poor experience?</span></span>](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[<span data-ttu-id="c6598-106">측정에 대 한 통화 및 사용자 개수 값이 최대 0.2% 차이를 표시 하는 이유는 무엇 이며, 가장 정확한 볼륨을 얻는 방법은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="c6598-106">Why do I see up to 0.2% difference in call and user count values on measures and how to get most accurate volumes? </span></span>](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[<span data-ttu-id="c6598-107">CQD v2 보고서 데이터가 CQD v3 보고서 데이터와 다르게 보이는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="c6598-107">Why does my CQD v2 report data look different than the CQD v3 report data? </span></span>](#why-does-my-cqd-v2-report-data-look-different-than-the-cqd-v3-report-data)

[<span data-ttu-id="c6598-108">비즈니스용 Skype 데이터가 팀의 CQD 데이터와 다른 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="c6598-108">Why is CQD data from Skype for Business different than CQD data from Teams? </span></span>](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[<span data-ttu-id="c6598-109">CQD에 EUII이 표시 되지 않는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="c6598-109">Why can't I see EUII in CQD?</span></span>](#why-cant-i-see-euii-in-cqd)

[<span data-ttu-id="c6598-110">팀만 필터링 했을 때 CQD에 비즈니스용 Skype 정보가 표시 되는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="c6598-110">Why am I seeing Skype for Business information in CQD when I've filtered for Teams only?</span></span>](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a><span data-ttu-id="c6598-111">하나 이상의 모임 참가자에 게 좋지 않은 경험이 있는 경우 CQD 님이 "좋은" 것으로 표시 되는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="c6598-111">Why does CQD mark a call as "Good" if one or more meeting participants had a poor experience?</span></span>

<span data-ttu-id="c6598-112">[스트림 분류](stream-classification-in-call-quality-dashboard.md)에 대 한 CQD 사용 규칙을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="c6598-112">Check out the rules CQD uses for [stream classification](stream-classification-in-call-quality-dashboard.md).</span></span>
 
<span data-ttu-id="c6598-113">오디오 스트림의 경우 통화 길이를 기준으로 평균을 계산 하는 5 개의 분류자는 모두 "우수한" 매개 변수 내에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-113">For audio streams, any of the 5 classifiers, which are calculated for the average based on the length of the call, could all be within "good" parameters.</span></span> <span data-ttu-id="c6598-114">이는 사용자가 오디오 드롭, 정적 또는 결함에 기여 하지 않았음을 의미 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-114">It doesn't mean the users didn't experience something that contributed to an audio drop out, static, or glitch.</span></span> 

<span data-ttu-id="c6598-115">네트워크 문제 인지 확인 하려면 세션의 평균 값과 최대값 사이의 델타를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-115">To determine if it was a network problem, look at the delta between the average values for the session and the max values.</span></span> <span data-ttu-id="c6598-116">최대값은 세션 중에 검색 되 고 보고 된 최대 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-116">Max values are the maximum detected and reported during the session.</span></span>
 
<span data-ttu-id="c6598-117">이 문제를 해결 하는 방법의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-117">Here's an example of how to troubleshoot this situation.</span></span> <span data-ttu-id="c6598-118">통화 중에 네트워크 추적을 취하고, 손실 된 패킷이 없기 때문에 패킷 1 개가 1.5 초와 나머지 통화에 좋은 경우를 예로 들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-118">Let's say you take a network trace during a call and the first 20 minutes there are no lost packets but then you have a gap of 1.5 seconds of packets and then good for the remainder of the call.</span></span> <span data-ttu-id="c6598-119">평균은 Wireshark 추적 RTP 분석 에서도 10% (0.1) 패킷 손실로 진행 <됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-119">The average is going to be <10% (0.1) Packet loss even in a Wireshark trace RTP analysis.</span></span> <span data-ttu-id="c6598-120">최대 패킷 손실에는 어떤 것이 있나요?</span><span class="sxs-lookup"><span data-stu-id="c6598-120">What was the Max Packet Loss?</span></span> <span data-ttu-id="c6598-121">5 초 기간의 1.5 초는 30% (0.3)입니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-121">1.5 Seconds in a 5-second period would be 30% (0.3).</span></span> <span data-ttu-id="c6598-122">5 두 번째 샘플 기간 내에 발생 한 경우 (또는 샘플링 기간 동안 분할 될 수 있음)</span><span class="sxs-lookup"><span data-stu-id="c6598-122">Did that occur within the five second sampling period (maybe or it could be split over the sampling period)?</span></span>
 
<span data-ttu-id="c6598-123">네트워크 메트릭이 평균 및 최대 값에 적합 한 경우 다른 원격 분석 데이터로 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-123">If network metrics look good in the averages and max values, then look to other telemetry data:</span></span> 
- <span data-ttu-id="c6598-124">CPU 불충분 이벤트 비율을 확인 하 여 감지 된 CPU 리소스를 사용할 수 있는지, 그리고 품질이 저하 되었는지 확인해 보세요.</span><span class="sxs-lookup"><span data-stu-id="c6598-124">Check CPU Insufficient Event Ratio to see if the detected CPU resources available were insufficient and caused poor quality.</span></span> 
- <span data-ttu-id="c6598-125">스피커로 가까이 있는 마이크 때문에 피드백을 방지 하기 위해 반이중 모드의 오디오 장치는?</span><span class="sxs-lookup"><span data-stu-id="c6598-125">Was the audio device in Half Duplex mode to prevent feedback due to microphones that are to close to speakers?</span></span> 
- <span data-ttu-id="c6598-126">Device 반이중 AEC 이벤트 비율을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-126">Check the Device Half Duplex AEC Event Ratio.</span></span> <span data-ttu-id="c6598-127">허브 또는 도킹 스테이션에 연결 되었을 때 USB 오디오 낙하 때문에 장치 결함 또는 마이크 결함 소음 또는 정전기가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-127">Was the device glitching or the microphone glitching introducing noise or static due to USB Audio Drop outs when plugged into a Hub or Docking Station:</span></span>  
- <span data-ttu-id="c6598-128">장치 결함 및 마이크 결함 이벤트 비율을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-128">Check the Device Glitches and Microphone glitches event ratios.</span></span> <span data-ttu-id="c6598-129">장치 자체가 제대로 작동 했습니까?</span><span class="sxs-lookup"><span data-stu-id="c6598-129">Was the device itself functioning properly?</span></span>  
- <span data-ttu-id="c6598-130">캡처를 확인 하 고 작동 하지 않는 이벤트 비율이 장치를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-130">Check the Capture and Render Device Not Functioning Event Ratios.</span></span>


<span data-ttu-id="c6598-131">CQD 원격 분석에서 사용할 수 있는 차원과 측정값에 대 한 자세한 내용은 [통화 품질 대시보드에서 사용할 수 있는 차원과](dimensions-and-measures-available-in-call-quality-dashboard.md)측정값을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c6598-131">For more on dimensions and measures available in CQD telemetry, read [Dimensions and measurements available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>

<span data-ttu-id="c6598-132">배경 잡음을 위해 참가자가 음소거 된 시간을 보려면 음소거 이벤트 비율을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="c6598-132">For background noise, check mute event ratio to see the length of time participants were muted.</span></span>
 
<span data-ttu-id="c6598-133">CQD에서 자세한 보고서를 만들고 모임 ID를 필터링 하 여 모임에서 모든 사용자와 스트림을 보고 관심 있는 필드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-133">Create detailed reports in CQD and filter on Meeting ID to look at all users and streams in a meeting and add the fields you are interested in.</span></span> <span data-ttu-id="c6598-134">문제를 보고 하는 사용자가 문제가 발생 한 것이 아닐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-134">A user reporting the issue may not be the one that was having the issue.</span></span> <span data-ttu-id="c6598-135">귀하는 환경을 보고만 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-135">They are just reporting the experience.</span></span>
 
<span data-ttu-id="c6598-136">원격 분석은 반드시 문제를 해결 하는 것은 아니지만, 의사 결정을 확인 하 고 알리는 위치를 보다 잘 파악 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-136">The telemetry will not necessarily call out the issue, but it can help you better understand where to look and inform your decisions.</span></span> <span data-ttu-id="c6598-137">네트워크, 장치, 드라이버 또는 펌웨어 업데이트, 사용 또는 사용자 인가요?</span><span class="sxs-lookup"><span data-stu-id="c6598-137">Is it network, device, driver or firmware updates, usage, or user?</span></span>

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a><span data-ttu-id="c6598-138">측정에 대 한 통화 및 사용자 개수 값이 최대 0.2% 차이를 표시 하는 이유는 무엇 이며, 가장 정확한 볼륨을 얻는 방법은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="c6598-138">Why do I see up to 0.2% difference in call and user count values on measures and how to get most accurate volumes?</span></span> 
<span data-ttu-id="c6598-139">통화 수 및 사용자 수 측정값을 계산 하려면 데이터 집합의 호출 또는 사용자 식별자에 대해 distinct countif 연산을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-139">To compute call count and user count measures, a distinct countif operation is performed against the call or user identifiers in the data set.</span></span> <span data-ttu-id="c6598-140">대규모 데이터 집합에는 distinct countif 연산에 기본적으로 0.2% 오류가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-140">On large data sets, there is an up to 0.2% error inherent with the distinct countif operation.</span></span> <span data-ttu-id="c6598-141">가장 정확한 볼륨에서는 이러한 distinct countif 연산에 의존 하지 않으므로 스트림 개수 측정값을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-141">For the most accurate volume, you should rely on stream count measures since they do not rely on this distinct countif operation.</span></span> <span data-ttu-id="c6598-142">데이터 볼륨을 줄이기 위해 필터링 하면 오류를 줄일 수 있지만, 별도의 통화 및 사용자 수에서이 오류 원인을 제거 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-142">Filtering to reduce the data volume may reduce the error but may not eliminate this source of error in distinct call and user counts.</span></span> <span data-ttu-id="c6598-143">영향을 받는 측정값에 대 한 [통화 품질 대시보드에서 사용할 수 있는 차원과 측정값](dimensions-and-measures-available-in-call-quality-dashboard.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c6598-143">Refer to [Dimensions and measurements available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md) for which measures are impacted.</span></span>

### <a name="why-does-my-cqd-v2-report-data-look-different-than-the-cqd-v3-report-data"></a><span data-ttu-id="c6598-144">CQD v2 보고서 데이터가 CQD v3 보고서 데이터와 다르게 보이는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="c6598-144">Why does my CQD v2 report data look different than the CQD v3 report data?</span></span> 

<span data-ttu-id="c6598-145">CQD v2와 v3 간에 데이터 차이점이 표시 되는 경우, 집계 수준이 아닌 ' 사과 대 인 ' 및 좁은 수준에 대 한 데이터 비교가 나 유효성 검사가 수행 되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-145">If you see data differences between CQD v2 and v3, make sure that data comparison or validation is done on an 'apples-to-apples'  and narrow level, not an aggregated level.</span></span> <span data-ttu-id="c6598-146">예를 들어, MSIT ' 건물 30 ' WiFi 팀 데스크톱 클라이언트 데이터에 대 한 보고서를 모두 필터링 하는 경우 낮은 품질의 백분율이 v2 및 v3에서 동일 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-146">For example, if you filter both reports for MSIT 'Building 30' WiFi Teams Desktop client data, the Percentage of Poor Quality should be the same between v2 and v3.</span></span>

<span data-ttu-id="c6598-147">CQDv2 분류는 "오디오" 모달 인 경우에만 가능 하며,이 분류는 모든 모달 (오디오, 비디오 및 Appsharing)에 대해 발생 하며 해당 하는 각 모달 스트림에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-147">CQDv2 classification for CallSetup failure is only considered for "Audio" modality, in CQDv3 this classification happens for every modality (Audio, Video and Appsharing) and is represented in the respective modality stream.</span></span> 

<span data-ttu-id="c6598-148">CQDv2 팀의 경우 모든 형식을 CQDv3에 동일한 사용자 의견을 적용 하 고 팀의 모달에 대 한 의견 기반을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-148">For Teams, CQDv2 applies the same user feedback to all modalities CQDv3 applies feedback base on modality for Teams.</span></span>

<span data-ttu-id="c6598-149">CQD V3 포함</span><span class="sxs-lookup"><span data-stu-id="c6598-149">CQD V3 includes</span></span> 
1. <span data-ttu-id="c6598-150">비즈니스용 Skype 서버 2019 통화</span><span class="sxs-lookup"><span data-stu-id="c6598-150">Skype for Business Server 2019 calls,</span></span> 
2. <span data-ttu-id="c6598-151">Skype 봇 통화: 자동 전화 교환, 통화 대기열, 회의 알림 서비스</span><span class="sxs-lookup"><span data-stu-id="c6598-151">Skype Bot calls, such as:auto attendant, call queue, conference announcement service,</span></span> 
3. <span data-ttu-id="c6598-152">가상 데스크톱 인터페이스를</span><span class="sxs-lookup"><span data-stu-id="c6598-152">Virtual Desktop Interface,</span></span>
4. <span data-ttu-id="c6598-153">컨퍼런스 비디오 Interop</span><span class="sxs-lookup"><span data-stu-id="c6598-153">Conference Video Interop,</span></span>
3. <span data-ttu-id="c6598-154">라이브 이벤트 게시자 및 발표자 통화</span><span class="sxs-lookup"><span data-stu-id="c6598-154">Live Events Publisher and Presenter calls, and</span></span> 
4. <span data-ttu-id="c6598-155">PSTN 통화.</span><span class="sxs-lookup"><span data-stu-id="c6598-155">PSTN calls.</span></span> 

<span data-ttu-id="c6598-156">이러한 Power BI 서식 파일을 사용 하 여 CQD 데이터를 분석 하 고 보고 하는 방법을 알아보려면 [cqd 보고서에 대 한 POWER BI 사용](cqd-power-bi-query-templates.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c6598-156">To learn how to use these Power BI templates to analyze and report your CQD data, read [Use Power BI for CQD reports](cqd-power-bi-query-templates.md).</span></span>


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a><span data-ttu-id="c6598-157">비즈니스용 Skype 데이터가 팀의 CQD 데이터와 다른 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="c6598-157">Why is CQD data from Skype for Business different than CQD data from Teams?</span></span> 


> [!IMPORTANT]
> <span data-ttu-id="c6598-158">2020 년 7 월 1 일부 터 이전 CQD는 최신 CQD의 데이터에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-158">As of July 1, 2020, the older CQD accesses data from the latest CQD.</span></span> <span data-ttu-id="c6598-159">이전의 CQD 데이터는 더 이상 사용할 수 없으며, 문서 또는 보고서 데이터를 내보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-159">The older CQD data is no longer available, and you can't export your building or report data.</span></span>


<span data-ttu-id="c6598-160">이전 CQD를 비즈니스용 Skype 레거시 포털 (cqd.lync.com)과 팀 관리 센터 (cqd.teams.microsoft.com)에서 최신 CQD ()와 비교 하려고 하면 데이터가 일치 하지 않는다는 것을 빠르게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-160">If you're trying to compare data between the older CQD from the Skype for Business legacy portal (cqd.lync.com) and the latest CQD from the Teams admin center (cqd.teams.microsoft.com), you'll quickly notice that the data doesn't match.</span></span> <span data-ttu-id="c6598-161">최신 CQD는 여러 추가 통화 시나리오에 대 한 보고를 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-161">That's because the latest CQD reports on many additional calling scenarios.</span></span> <span data-ttu-id="c6598-162">이전 CQD의 보고서를 계속 사용 하는 경우이 문서를 사용 하 여 [비즈니스용 Skype 서버용 통화 품질 대시보드](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard)를 통해 해당 보고서를 해석 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-162">If you're still using reports from the older CQD, use this article to help you interpret those reports: [Call Quality Dashboard for Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard).</span></span>



<span data-ttu-id="c6598-163">다음은 CQD v2 및 CQD 데이터를 비교 하는 특정 필터를 적용 하는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-163">Here's an example of applying specific filters to compare CQD v2 and CQD v3 data:</span></span>

1. <span data-ttu-id="c6598-164">체감 품질 Record 사용 가능 = True</span><span class="sxs-lookup"><span data-stu-id="c6598-164">QoE Record Available = True</span></span>

2. <span data-ttu-id="c6598-165">다음 값을 사용 하 여 서버 쌍 필터 추가: 클라이언트: 클라이언트 및 클라이언트: 서버.</span><span class="sxs-lookup"><span data-stu-id="c6598-165">Add Is Server Pair filter with value: Client:Client and Client:Server.</span></span> <span data-ttu-id="c6598-166">대부분의 테 넌 트는 서버 호출을 제외 하는 것을 선호 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-166">Most tenants prefer to exclude Server:Server calls.</span></span>

3. <span data-ttu-id="c6598-167">사용자 에이전트 범주에 대 한 필터를 추가 하 고 자동 전화 교환, 통화 대기열, 봇, 방 시스템, MediationServer, 컨퍼런스 알림 서비스, VDI 등을 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-167">Add a filter for User Agent Category and filter out Auto Attendant, Call Queue, Bot, Room system, MediationServer, Conference Announcement service, VDI, etc.</span></span>

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard1.png" alt-text="CQD v3에서 특정 필터를 적용 하는 스크린샷":::

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard2.png" alt-text="CQD v2에서 특정 필터를 적용 하는 스크린샷":::

#### <a name="other-expected-differences-between-cqd-v2-and-cqd-v3"></a><span data-ttu-id="c6598-170">CQD v2와 CQD v3 간의 다른 예상 차이점</span><span class="sxs-lookup"><span data-stu-id="c6598-170">Other expected differences between CQD v2 and CQD v3</span></span>

<span data-ttu-id="c6598-171">이전 버전과 최신 CQD 간의 차이점에 대 한 자세한 내용은 2019 년 11 월 5 일에 [고급 통화 품질 대시보드 블로그 소개](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Introducing-the-Advanced-Call-Quality-Dashboard/ba-p/972586) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c6598-171">To learn more about the differences between the older and latest CQD, read the [Introducing the Advanced Call Quality Dashboard](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Introducing-the-Advanced-Call-Quality-Dashboard/ba-p/972586) blog, from November 5, 2019.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="c6598-172">2020 년 7 월 1 일부 터 이전 CQD는 최신 CQD의 데이터에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-172">As of July 1, 2020, the older CQD accesses data from the latest CQD.</span></span> <span data-ttu-id="c6598-173">이전의 CQD 데이터는 더 이상 사용할 수 없으며, 문서 또는 보고서 데이터를 내보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-173">The older CQD data is no longer available, and you can't export your building or report data.</span></span>

<span data-ttu-id="c6598-174">집계 또는 요약 수준의 이전 및 최신 CQD 보고서 사이에 더 많은 데이터 차이가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-174">You’ll likely see more data differences between your older and newer CQD reports at the aggregated or summary level.</span></span> <span data-ttu-id="c6598-175">보다 세부적인 수준에서 데이터를 비교 하는 경우 "사과 투-사과" 비교가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-175">If you compare data at a more granular level, you’ll get an “apples-to-apples” comparison.</span></span> <span data-ttu-id="c6598-176">예를 들어 개별 건물에 대 한 데이터를 보고 있는 경우 이전 및 새 CQD 보고서 모두에서 낮은 품질의 백분율이 동일 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-176">For example, if you’re looking at data for an individual building, the Percentage of Poor Quality should be the same between both the older and new CQD reports.</span></span>

- <span data-ttu-id="c6598-177">기업 유선 연결, Windows 데스크톱 또는 단일 지역 또는 건물과 같은 밀접 한 초점으로 시나리오를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-177">Pick a scenario with a tight focus, such as corporate wired connections, Windows Desktops, or a single region or building.</span></span>
- <span data-ttu-id="c6598-178">팀의 MR, TR 또는 MP IP 범위를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-178">Check the Teams MR, TR, or MP IP ranges.</span></span> <span data-ttu-id="c6598-179">팀의 범위는 비즈니스용 Skype Online 보다 최신 이며, 방화벽과 관련 된 연결 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-179">The Teams ranges are newer than Skype for Business Online, and that can cause connectivity issues involving firewalls.</span></span>
- <span data-ttu-id="c6598-180">요약 또는 상위 수준 번호를 비교 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-180">Don't compare summary or top-level numbers.</span></span> <span data-ttu-id="c6598-181">이러한 비교를 통해 회사 유선 연결에서 비즈니스용 Skype Online 통화의 대규모 통화 볼륨을 LTE 또는 사설 네트워크의 소규모 팀 통화와 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-181">These comparisons will lead you to compare a large call volume of Skype for Business Online calls on a corporate wired connection to a small volume of Teams calls on an LTE or private network.</span></span>
- <span data-ttu-id="c6598-182">위치 편향 및 인구 차이에 대 한 주의: 매우 다양 한 비교 기능을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-182">Beware of location bias and population differences: There are many comparisons that are too dissimilar to be useful:</span></span>
  - <span data-ttu-id="c6598-183">NOAM: APAC</span><span class="sxs-lookup"><span data-stu-id="c6598-183">NOAM : APAC</span></span>
  - <span data-ttu-id="c6598-184">대 중: Goa</span><span class="sxs-lookup"><span data-stu-id="c6598-184">NY : Goa</span></span>
  - <span data-ttu-id="c6598-185">유선: wifi</span><span class="sxs-lookup"><span data-stu-id="c6598-185">Wired : wifi</span></span>
  - <span data-ttu-id="c6598-186">회사 네트워크: 홈 네트워크</span><span class="sxs-lookup"><span data-stu-id="c6598-186">Corporate network : home network</span></span>
  
### <a name="why-cant-i-see-euii-in-cqd"></a><span data-ttu-id="c6598-187">CQD에 EUII이 표시 되지 않는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="c6598-187">Why can't I see EUII in CQD?</span></span>

<span data-ttu-id="c6598-188">이러한 관리자 역할은 CQD에 액세스할 수 있지만, EUII (최종 사용자 식별 가능 정보)는 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-188">These admin roles can access CQD, but they can't view EUII (end-user identifiable information):</span></span>
- <span data-ttu-id="c6598-189">Microsoft 365 보고서 읽기 프로그램</span><span class="sxs-lookup"><span data-stu-id="c6598-189">Microsoft 365 Reports Reader</span></span>
- <span data-ttu-id="c6598-190">팀 의사 소통 지원 전문가</span><span class="sxs-lookup"><span data-stu-id="c6598-190">Teams Communications Support Specialist</span></span>

<span data-ttu-id="c6598-191">EUII를 포함 하 여 CQD에 액세스할 수 있는 역할에 대 한 자세한 내용은 [CQD에 액세스 하기 위한 역할 할당](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c6598-191">To learn more about roles that can access CQD - including EUII - read [Assign roles for accessing CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).</span></span>

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a><span data-ttu-id="c6598-192">팀만 필터링 했을 때 CQD에 비즈니스용 Skype 정보가 표시 되는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="c6598-192">Why am I seeing Skype for Business information in CQD when I've filtered for Teams only?</span></span>

<span data-ttu-id="c6598-193">CQD 보고서 (isTeams = 1) 에서만 팀을 필터링 하는 경우 *첫 번째 끝점이* 팀 인 모든 통화에 대해 필터링 하 고 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-193">When you filter for Teams only in CQD reports (isTeams = 1), you're filtering for all calls where the *first endpoint* is Teams.</span></span> <span data-ttu-id="c6598-194">*두 번째 종점이* 비즈니스용 Skype 인 경우 해당 정보는 CQD 보고서에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-194">If the *second endpoint* is Skype for Business, that information will show up in your CQD report.</span></span>

<span data-ttu-id="c6598-195">CQDv3에는 CQDv2에는 없는 새로운 시나리오가 포함 되어 있기 때문에 CQDv2 및 CQDv3에는 항상 다른 총 카운트가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-195">CQDv2 and CQDv3 will always have different total counts since CQDv3 will have new scenarios that CQDv2 will not have.</span></span> <span data-ttu-id="c6598-196">이 때문에 필터 없이 요약 합계 또는 집계 된 모든 번호를 비교 하면 이러한 예상 차이점이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-196">That’s why comparing Summary Total or Aggregated all-up numbers with no filters will have these expected differences.</span></span>  

<span data-ttu-id="c6598-197">고객의 시나리오에 따라 CQDv3에는 SFB 2019 온-프레미스 통화 (SFB 2019이 데이터 커넥터와 함께 사용 되는 경우), Skype Bot 통화 (AA, CVI, VDI), Live 이벤트 및 PSTN 통화가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-197">Depending on Customers’ scenario, CQDv3 will include SFB 2019 on-premises calls (if SFB 2019 is used with a data connector), Skype Bot calls (AA, CVI, VDI), Live Events and PSTN calls.</span></span> <span data-ttu-id="c6598-198">고객에 게 제공 되는 시나리오/기능 이지만 해당 데이터는 CQD V2에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-198">Scenarios/Features which are available for the customers, but their data are not in CQD V2.</span></span>

<span data-ttu-id="c6598-199">예를 들어, 고객에 게 20만 오디오 스트림을 표시 하 고 CQD V2 요약 보고서에서 5000 오류가 발생 하는 것으로 예상 됩니다. 5500 오류와 30만 오디오 스트림 (2019 온-프레미스 통화, CVI 통화, PSTN 통화 등) 및 CQD V3</span><span class="sxs-lookup"><span data-stu-id="c6598-199">For instance, it is expected that your customers and you will see 200,000 audio streams, with 5000 failures in CQD V2 Summary Report; versus 300,000 audio streams with 5500 failures (coming from 2019 on-prem calls, CVI calls, PSTN calls etc) in CQD V3.</span></span>

<span data-ttu-id="c6598-200">예기치 않은 차이점이 있는 경우에는 전체 데이터의 다양 한 분석를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-200">In order to determine, if there are any unexpected differences, you must look at various breakdowns of the overall data.</span></span>  <span data-ttu-id="c6598-201">의도와 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-201">Compare with intent.</span></span>  <span data-ttu-id="c6598-202">사용자 에이전트 범주 쌍으로 데이터를 분리 하는 것이 권장 되는 첫 번째 항목 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-202">Slicing the data by User Agent Category Pair is one of the first things we recommend.</span></span>  <span data-ttu-id="c6598-203">*첫 번째 제품과* *두 번째 제품은* 훌륭한 슬라이서 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6598-203">*First Product* and *Second Product* are also good slicers.</span></span>  


## <a name="related-topics"></a><span data-ttu-id="c6598-204">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c6598-204">Related topics</span></span>

[<span data-ttu-id="c6598-205">팀의 통화 품질 개선 및 모니터링</span><span class="sxs-lookup"><span data-stu-id="c6598-205">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="c6598-206">CQD 란 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="c6598-206">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="c6598-207">CQD (통화 품질 대시보드) 설정</span><span class="sxs-lookup"><span data-stu-id="c6598-207">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="c6598-208">테 넌 트 업로드 및 데이터 빌드</span><span class="sxs-lookup"><span data-stu-id="c6598-208">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="c6598-209">CQD 데이터 및 보고서</span><span class="sxs-lookup"><span data-stu-id="c6598-209">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="c6598-210">CQD를 사용 하 여 통화 및 모임 품질 관리</span><span class="sxs-lookup"><span data-stu-id="c6598-210">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="c6598-211">CQD에서 사용할 수 있는 차원과 측정값</span><span class="sxs-lookup"><span data-stu-id="c6598-211">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="c6598-212">CQD의 스트림 분류</span><span class="sxs-lookup"><span data-stu-id="c6598-212">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="c6598-213">Power BI를 사용 하 여 CQD 데이터 분석</span><span class="sxs-lookup"><span data-stu-id="c6598-213">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)

[<span data-ttu-id="c6598-214">Teams 문제 해결</span><span class="sxs-lookup"><span data-stu-id="c6598-214">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)