---
title: 통화 품질 대시보드 (CQD) 자주 묻는 질문 사항 (FAQ)
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: 8ad0a1745799194ec11284f8f7aaabd76bd30d05
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46584027"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a><span data-ttu-id="f96c7-103">통화 품질 대시보드 (CQD) 자주 묻는 질문 사항 (FAQ)</span><span class="sxs-lookup"><span data-stu-id="f96c7-103">Call Quality Dashboard (CQD) Frequently asked questions (FAQ)</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="f96c7-104">자주하는 질문</span><span class="sxs-lookup"><span data-stu-id="f96c7-104">Frequently asked questions</span></span>

[<span data-ttu-id="f96c7-105">하나 이상의 모임 참가자에 게 좋지 않은 경험이 있는 경우 CQD 님이 "좋은" 것으로 표시 되는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="f96c7-105">Why does CQD mark a call as "Good" if one or more meeting participants had a poor experience?</span></span>](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[<span data-ttu-id="f96c7-106">측정에 대 한 통화 및 사용자 개수 값이 최대 0.2% 차이를 표시 하는 이유는 무엇 이며, 가장 정확한 볼륨을 얻는 방법은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="f96c7-106">Why do I see up to 0.2% difference in call and user count values on measures and how to get most accurate volumes? </span></span>](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[<span data-ttu-id="f96c7-107">비즈니스용 Skype 데이터가 팀의 CQD 데이터와 다른 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="f96c7-107">Why is CQD data from Skype for Business different than CQD data from Teams? </span></span>](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[<span data-ttu-id="f96c7-108">CQD에 EUII이 표시 되지 않는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="f96c7-108">Why can't I see EUII in CQD?</span></span>](#why-cant-i-see-euii-in-cqd)

[<span data-ttu-id="f96c7-109">팀만 필터링 했을 때 CQD에 비즈니스용 Skype 정보가 표시 되는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="f96c7-109">Why am I seeing Skype for Business information in CQD when I've filtered for Teams only?</span></span>](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a><span data-ttu-id="f96c7-110">하나 이상의 모임 참가자에 게 좋지 않은 경험이 있는 경우 CQD 님이 "좋은" 것으로 표시 되는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="f96c7-110">Why does CQD mark a call as "Good" if one or more meeting participants had a poor experience?</span></span>

<span data-ttu-id="f96c7-111">[스트림 분류](stream-classification-in-call-quality-dashboard.md)에 대 한 CQD 사용 규칙을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="f96c7-111">Check out the rules CQD uses for [stream classification](stream-classification-in-call-quality-dashboard.md).</span></span>
 
<span data-ttu-id="f96c7-112">오디오 스트림의 경우 통화 길이를 기준으로 평균을 계산 하는 5 개의 분류자는 모두 "우수한" 매개 변수 내에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-112">For audio streams, any of the 5 classifiers, which are calculated for the average based on the length of the call, could all be within "good" parameters.</span></span> <span data-ttu-id="f96c7-113">이는 사용자가 오디오 드롭, 정적 또는 결함에 기여 하지 않았음을 의미 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-113">It doesn't mean the users didn't experience something that contributed to an audio drop out, static, or glitch.</span></span> 

<span data-ttu-id="f96c7-114">네트워크 문제 인지 확인 하려면 세션의 평균 값과 최대값 사이의 델타를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-114">To determine if it was a network problem, look at the delta between the average values for the session and the max values.</span></span> <span data-ttu-id="f96c7-115">최대값은 세션 중에 검색 되 고 보고 된 최대 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-115">Max values are the maximum detected and reported during the session.</span></span>
 
<span data-ttu-id="f96c7-116">이 문제를 해결 하는 방법의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-116">Here's an example of how to troubleshoot this situation.</span></span> <span data-ttu-id="f96c7-117">통화 중에 네트워크 추적을 취하고, 손실 된 패킷이 없기 때문에 패킷 1 개가 1.5 초와 나머지 통화에 좋은 경우를 예로 들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-117">Let's say you take a network trace during a call and the first 20 minutes there are no lost packets but then you have a gap of 1.5 seconds of packets and then good for the remainder of the call.</span></span> <span data-ttu-id="f96c7-118">평균은 Wireshark 추적 RTP 분석 에서도 10% (0.1) 패킷 손실로 진행 <됩니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-118">The average is going to be <10% (0.1) Packet loss even in a Wireshark trace RTP analysis.</span></span> <span data-ttu-id="f96c7-119">최대 패킷 손실에는 어떤 것이 있나요?</span><span class="sxs-lookup"><span data-stu-id="f96c7-119">What was the Max Packet Loss?</span></span> <span data-ttu-id="f96c7-120">5 초 기간의 1.5 초는 30% (0.3)입니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-120">1.5 Seconds in a 5-second period would be 30% (0.3).</span></span> <span data-ttu-id="f96c7-121">5 두 번째 샘플 기간 내에 발생 한 경우 (또는 샘플링 기간 동안 분할 될 수 있음)</span><span class="sxs-lookup"><span data-stu-id="f96c7-121">Did that occur within the five second sampling period (maybe or it could be split over the sampling period)?</span></span>
 
<span data-ttu-id="f96c7-122">네트워크 메트릭이 평균 및 최대 값에 적합 한 경우 다른 원격 분석 데이터로 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-122">If network metrics look good in the averages and max values, then look to other telemetry data:</span></span> 
- <span data-ttu-id="f96c7-123">CPU 불충분 이벤트 비율을 확인 하 여 감지 된 CPU 리소스를 사용할 수 있는지, 그리고 품질이 저하 되었는지 확인해 보세요.</span><span class="sxs-lookup"><span data-stu-id="f96c7-123">Check CPU Insufficient Event Ratio to see if the detected CPU resources available were insufficient and caused poor quality.</span></span> 
- <span data-ttu-id="f96c7-124">스피커로 가까이 있는 마이크 때문에 피드백을 방지 하기 위해 반이중 모드의 오디오 장치는?</span><span class="sxs-lookup"><span data-stu-id="f96c7-124">Was the audio device in Half Duplex mode to prevent feedback due to microphones that are to close to speakers?</span></span> 
- <span data-ttu-id="f96c7-125">Device 반이중 AEC 이벤트 비율을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-125">Check the Device Half Duplex AEC Event Ratio.</span></span> <span data-ttu-id="f96c7-126">허브 또는 도킹 스테이션에 연결 되었을 때 USB 오디오 낙하 때문에 장치 결함 또는 마이크 결함 소음 또는 정전기가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-126">Was the device glitching or the microphone glitching introducing noise or static due to USB Audio Drop outs when plugged into a Hub or Docking Station:</span></span>  
- <span data-ttu-id="f96c7-127">장치 결함 및 마이크 결함 이벤트 비율을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-127">Check the Device Glitches and Microphone glitches event ratios.</span></span> <span data-ttu-id="f96c7-128">장치 자체가 제대로 작동 했습니까?</span><span class="sxs-lookup"><span data-stu-id="f96c7-128">Was the device itself functioning properly?</span></span>  
- <span data-ttu-id="f96c7-129">캡처를 확인 하 고 작동 하지 않는 이벤트 비율이 장치를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-129">Check the Capture and Render Device Not Functioning Event Ratios.</span></span>


<span data-ttu-id="f96c7-130">CQD 원격 분석에서 사용할 수 있는 차원과 측정값에 대 한 자세한 내용은 [통화 품질 대시보드에서 사용할 수 있는 차원과](dimensions-and-measures-available-in-call-quality-dashboard.md)측정값을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f96c7-130">For more on dimensions and measures available in CQD telemetry, read [Dimensions and measurements available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>

<span data-ttu-id="f96c7-131">배경 잡음을 위해 참가자가 음소거 된 시간을 보려면 음소거 이벤트 비율을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="f96c7-131">For background noise, check mute event ratio to see the length of time participants were muted.</span></span>
 
<span data-ttu-id="f96c7-132">CQD에서 자세한 보고서를 만들고 모임 ID를 필터링 하 여 모임에서 모든 사용자와 스트림을 보고 관심 있는 필드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-132">Create detailed reports in CQD and filter on Meeting ID to look at all users and streams in a meeting and add the fields you are interested in.</span></span> <span data-ttu-id="f96c7-133">문제를 보고 하는 사용자가 문제가 발생 한 것이 아닐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-133">A user reporting the issue may not be the one that was having the issue.</span></span> <span data-ttu-id="f96c7-134">귀하는 환경을 보고만 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-134">They are just reporting the experience.</span></span>
 
<span data-ttu-id="f96c7-135">원격 분석은 반드시 문제를 해결 하는 것은 아니지만, 의사 결정을 확인 하 고 알리는 위치를 보다 잘 파악 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-135">The telemetry will not necessarily call out the issue, but it can help you better understand where to look and inform your decisions.</span></span> <span data-ttu-id="f96c7-136">네트워크, 장치, 드라이버 또는 펌웨어 업데이트, 사용 또는 사용자 인가요?</span><span class="sxs-lookup"><span data-stu-id="f96c7-136">Is it network, device, driver or firmware updates, usage, or user?</span></span>

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a><span data-ttu-id="f96c7-137">측정에 대 한 통화 및 사용자 개수 값이 최대 0.2% 차이를 표시 하는 이유는 무엇 이며, 가장 정확한 볼륨을 얻는 방법은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="f96c7-137">Why do I see up to 0.2% difference in call and user count values on measures and how to get most accurate volumes?</span></span> 
<span data-ttu-id="f96c7-138">통화 수 및 사용자 수 측정값을 계산 하려면 데이터 집합의 호출 또는 사용자 식별자에 대해 distinct countif 연산을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-138">To compute call count and user count measures, a distinct countif operation is performed against the call or user identifiers in the data set.</span></span> <span data-ttu-id="f96c7-139">대규모 데이터 집합에는 distinct countif 연산에 기본적으로 0.2% 오류가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-139">On large data sets, there is an up to 0.2% error inherent with the distinct countif operation.</span></span> <span data-ttu-id="f96c7-140">가장 정확한 볼륨에서는 이러한 distinct countif 연산에 의존 하지 않으므로 스트림 개수 측정값을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-140">For the most accurate volume, you should rely on stream count measures since they do not rely on this distinct countif operation.</span></span> <span data-ttu-id="f96c7-141">데이터 볼륨을 줄이기 위해 필터링 하면 오류를 줄일 수 있지만, 별도의 통화 및 사용자 수에서이 오류 원인을 제거 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-141">Filtering to reduce the data volume may reduce the error but may not eliminate this source of error in distinct call and user counts.</span></span> <span data-ttu-id="f96c7-142">영향을 받는 측정값에 대 한 [통화 품질 대시보드에서 사용할 수 있는 차원과 측정값](dimensions-and-measures-available-in-call-quality-dashboard.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f96c7-142">Refer to [Dimensions and measurements available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md) for which measures are impacted.</span></span>


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a><span data-ttu-id="f96c7-143">비즈니스용 Skype 데이터가 팀의 CQD 데이터와 다른 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="f96c7-143">Why is CQD data from Skype for Business different than CQD data from Teams?</span></span> 


> [!IMPORTANT]
> <span data-ttu-id="f96c7-144">2020 년 7 월 1 일부 터 이전의 CQD (CQD.lync.com)는 최신 CQD (CQD)의 데이터를 사용 합니다. Teams.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="f96c7-144">As of July 1, 2020, the older CQD (CQD.lync.com) uses data from the latest CQD (CQD.Teams.microsoft.com).</span></span> <span data-ttu-id="f96c7-145">이전의 CQD 데이터는 더 이상 사용할 수 없으며, 문서 또는 보고서 데이터를 내보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-145">The older CQD data is no longer available, and you can't export your building or report data.</span></span> <span data-ttu-id="f96c7-146">CQD.lync.com (비즈니스용 Skype 관리 센터에서 사용 가능)를 계속 사용할 수 있지만, 곧 CQD.lync.com에 대 한 액세스를 해제 하 여 CQD로 이동 해야 합니다. 아직 수행 하지 않은 경우 Teams.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="f96c7-146">You can still use CQD.lync.com (available from the Skype for Business admin center), but we'll turn off access to CQD.lync.com soon, so you should move to CQD.Teams.microsoft.com if you haven't already done so.</span></span>


<span data-ttu-id="f96c7-147">이전 CQD를 비즈니스용 Skype 레거시 포털 (cqd.lync.com)과 팀 관리 센터 (cqd.teams.microsoft.com)에서 최신 CQD ()와 비교 하려고 하면 데이터가 일치 하지 않는다는 것을 빠르게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-147">If you're trying to compare data between the older CQD from the Skype for Business legacy portal (cqd.lync.com) and the latest CQD from the Teams admin center (cqd.teams.microsoft.com), you'll quickly notice that the data doesn't match.</span></span> <span data-ttu-id="f96c7-148">최신 CQD는 여러 추가 통화 시나리오에 대 한 보고를 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-148">That's because the latest CQD reports on many additional calling scenarios.</span></span> <span data-ttu-id="f96c7-149">이전 CQD의 보고서를 계속 사용 하는 경우이 문서를 사용 하 여 [비즈니스용 Skype 서버용 통화 품질 대시보드](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard)를 통해 해당 보고서를 해석 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-149">If you're still using reports from the older CQD, use this article to help you interpret those reports: [Call Quality Dashboard for Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard).</span></span>


  
### <a name="why-cant-i-see-euii-in-cqd"></a><span data-ttu-id="f96c7-150">CQD에 EUII이 표시 되지 않는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="f96c7-150">Why can't I see EUII in CQD?</span></span>

<span data-ttu-id="f96c7-151">이러한 관리자 역할은 CQD에 액세스할 수 있지만, EUII (최종 사용자 식별 가능 정보)는 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-151">These admin roles can access CQD, but they can't view EUII (end-user identifiable information):</span></span>
- <span data-ttu-id="f96c7-152">Microsoft 365 보고서 읽기 프로그램</span><span class="sxs-lookup"><span data-stu-id="f96c7-152">Microsoft 365 Reports Reader</span></span>
- <span data-ttu-id="f96c7-153">팀 의사 소통 지원 전문가</span><span class="sxs-lookup"><span data-stu-id="f96c7-153">Teams Communications Support Specialist</span></span>

<span data-ttu-id="f96c7-154">EUII를 포함 하 여 CQD에 액세스할 수 있는 역할에 대 한 자세한 내용은 [CQD에 액세스 하기 위한 역할 할당](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f96c7-154">To learn more about roles that can access CQD - including EUII - read [Assign roles for accessing CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).</span></span>

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a><span data-ttu-id="f96c7-155">팀만 필터링 했을 때 CQD에 비즈니스용 Skype 정보가 표시 되는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="f96c7-155">Why am I seeing Skype for Business information in CQD when I've filtered for Teams only?</span></span>

<span data-ttu-id="f96c7-156">CQD 보고서 (isTeams = 1) 에서만 팀을 필터링 하는 경우 *첫 번째 끝점이* 팀 인 모든 통화에 대해 필터링 하 고 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-156">When you filter for Teams only in CQD reports (isTeams = 1), you're filtering for all calls where the *first endpoint* is Teams.</span></span> <span data-ttu-id="f96c7-157">*두 번째 종점이* 비즈니스용 Skype 인 경우 해당 정보는 CQD 보고서에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-157">If the *second endpoint* is Skype for Business, that information will show up in your CQD report.</span></span>

<span data-ttu-id="f96c7-158">CQDv3에는 CQDv2에는 없는 새로운 시나리오가 포함 되어 있기 때문에 CQDv2 및 CQDv3에는 항상 다른 총 카운트가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-158">CQDv2 and CQDv3 will always have different total counts since CQDv3 will have new scenarios that CQDv2 will not have.</span></span> <span data-ttu-id="f96c7-159">이 때문에 필터 없이 요약 합계 또는 집계 된 모든 번호를 비교 하면 이러한 예상 차이점이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-159">That’s why comparing Summary Total or Aggregated all-up numbers with no filters will have these expected differences.</span></span>  

<span data-ttu-id="f96c7-160">고객의 시나리오에 따라 CQDv3에는 SFB 2019 온-프레미스 통화 (SFB 2019이 데이터 커넥터와 함께 사용 되는 경우), Skype Bot 통화 (AA, CVI, VDI), Live 이벤트 및 PSTN 통화가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-160">Depending on Customers’ scenario, CQDv3 will include SFB 2019 on-premises calls (if SFB 2019 is used with a data connector), Skype Bot calls (AA, CVI, VDI), Live Events and PSTN calls.</span></span> <span data-ttu-id="f96c7-161">고객에 게 제공 되는 시나리오/기능 이지만 해당 데이터는 CQD V2에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-161">Scenarios/Features which are available for the customers, but their data are not in CQD V2.</span></span>

<span data-ttu-id="f96c7-162">예를 들어, 고객에 게 20만 오디오 스트림을 표시 하 고 CQD V2 요약 보고서에서 5000 오류가 발생 하는 것으로 예상 됩니다. 5500 오류와 30만 오디오 스트림 (2019 온-프레미스 통화, CVI 통화, PSTN 통화 등) 및 CQD V3</span><span class="sxs-lookup"><span data-stu-id="f96c7-162">For instance, it is expected that your customers and you will see 200,000 audio streams, with 5000 failures in CQD V2 Summary Report; versus 300,000 audio streams with 5500 failures (coming from 2019 on-prem calls, CVI calls, PSTN calls etc) in CQD V3.</span></span>

<span data-ttu-id="f96c7-163">예기치 않은 차이점이 있는 경우에는 전체 데이터의 다양 한 분석를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-163">In order to determine, if there are any unexpected differences, you must look at various breakdowns of the overall data.</span></span>  <span data-ttu-id="f96c7-164">의도와 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-164">Compare with intent.</span></span>  <span data-ttu-id="f96c7-165">사용자 에이전트 범주 쌍으로 데이터를 분리 하는 것이 권장 되는 첫 번째 항목 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-165">Slicing the data by User Agent Category Pair is one of the first things we recommend.</span></span>  <span data-ttu-id="f96c7-166">*첫 번째 제품과* *두 번째 제품은* 훌륭한 슬라이서 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="f96c7-166">*First Product* and *Second Product* are also good slicers.</span></span>  


## <a name="related-topics"></a><span data-ttu-id="f96c7-167">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f96c7-167">Related topics</span></span>

[<span data-ttu-id="f96c7-168">팀의 통화 품질 개선 및 모니터링</span><span class="sxs-lookup"><span data-stu-id="f96c7-168">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="f96c7-169">CQD 란 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="f96c7-169">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="f96c7-170">CQD (통화 품질 대시보드) 설정</span><span class="sxs-lookup"><span data-stu-id="f96c7-170">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="f96c7-171">테 넌 트 업로드 및 데이터 빌드</span><span class="sxs-lookup"><span data-stu-id="f96c7-171">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="f96c7-172">CQD 데이터 및 보고서</span><span class="sxs-lookup"><span data-stu-id="f96c7-172">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="f96c7-173">CQD를 사용 하 여 통화 및 모임 품질 관리</span><span class="sxs-lookup"><span data-stu-id="f96c7-173">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="f96c7-174">CQD에서 사용할 수 있는 차원과 측정값</span><span class="sxs-lookup"><span data-stu-id="f96c7-174">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="f96c7-175">CQD의 스트림 분류</span><span class="sxs-lookup"><span data-stu-id="f96c7-175">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="f96c7-176">Power BI를 사용 하 여 CQD 데이터 분석</span><span class="sxs-lookup"><span data-stu-id="f96c7-176">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)

[<span data-ttu-id="f96c7-177">Teams 문제 해결</span><span class="sxs-lookup"><span data-stu-id="f96c7-177">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)