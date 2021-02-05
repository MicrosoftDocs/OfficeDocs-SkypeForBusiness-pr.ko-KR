---
title: CQD(통화 품질 대시보드) FAQ(질문과 대답)
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
description: Microsoft Teams 통화 품질 대시보드(CQD)에 대한 FAQ(질문과 대답)를 읽습니다.
ms.openlocfilehash: f622d197900faf632d94d659dae0a5b6eeaee2db
ms.sourcegitcommit: ac73536f790f83a61eeb2eb8c6b71662f7bd26fc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50110261"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a><span data-ttu-id="76590-103">CQD(통화 품질 대시보드) FAQ(질문과 대답)</span><span class="sxs-lookup"><span data-stu-id="76590-103">Call Quality Dashboard (CQD) Frequently asked questions (FAQ)</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="76590-104">자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="76590-104">Frequently asked questions</span></span>

[<span data-ttu-id="76590-105">한명 이상의 모임 참가자가 환경이 좋지 않은 경우 CQD에서 통화를 "양호"로 표시하는 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="76590-105">Why does CQD mark a call as "Good" if one or more meeting participants had a poor experience?</span></span>](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[<span data-ttu-id="76590-106">측정값에 대해 통화 및 사용자 수 값이 최대 0.2% 차이를 표시하는 이유는 무엇일까요? 가장 정확한 볼륨을 얻을 수 있는 방법 </span><span class="sxs-lookup"><span data-stu-id="76590-106">Why do I see up to 0.2% difference in call and user count values on measures and how to get most accurate volumes? </span></span>](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[<span data-ttu-id="76590-107">비즈니스용 Skype의 CQD 데이터가 Teams의 CQD 데이터와 다른 이유는 무엇입니까? </span><span class="sxs-lookup"><span data-stu-id="76590-107">Why is CQD data from Skype for Business different than CQD data from Teams? </span></span>](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[<span data-ttu-id="76590-108">CQD에서 EUII를 볼 수 없는 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="76590-108">Why can't I see EUII in CQD?</span></span>](#why-cant-i-see-euii-in-cqd)

[<span data-ttu-id="76590-109">Teams로만 필터링한 경우 CQD에 비즈니스용 Skype 정보가 표시되는 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="76590-109">Why am I seeing Skype for Business information in CQD when I've filtered for Teams only?</span></span>](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[<span data-ttu-id="76590-110">내 사용자 지정 보고서가 더 많은 항목이 있을 때 최대 10,000개 행만 반환하는 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="76590-110">Why do my custom reports only return a maximum of 10,000 rows when I know there should be more entries?</span></span>](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a><span data-ttu-id="76590-111">한명 이상의 모임 참가자가 환경이 좋지 않은 경우 CQD에서 통화를 "양호"로 표시하는 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="76590-111">Why does CQD mark a call as "Good" if one or more meeting participants had a poor experience?</span></span>

<span data-ttu-id="76590-112">스트림 분류에 CQD가 사용하는 [규칙을 확인해 1.](stream-classification-in-call-quality-dashboard.md)</span><span class="sxs-lookup"><span data-stu-id="76590-112">Check out the rules CQD uses for [stream classification](stream-classification-in-call-quality-dashboard.md).</span></span>
 
<span data-ttu-id="76590-113">오디오 스트림의 경우 호출 길이에 따라 평균으로 계산되는 5개 분류자 중 모두 "양호한" 매개 변수 내에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76590-113">For audio streams, any of the 5 classifiers, which are calculated for the average based on the length of the call, could all be within "good" parameters.</span></span> <span data-ttu-id="76590-114">사용자가 오디오 드롭아웃, 정적 또는 글리차에 기여한 것을 경험하지 않은 것은 아니며,</span><span class="sxs-lookup"><span data-stu-id="76590-114">It doesn't mean the users didn't experience something that contributed to an audio drop out, static, or glitch.</span></span> 

<span data-ttu-id="76590-115">네트워크 문제인지 확인하려면 세션의 평균 값과 최대 값 사이의 델타를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="76590-115">To determine if it was a network problem, look at the delta between the average values for the session and the max values.</span></span> <span data-ttu-id="76590-116">최대 값은 세션 중에 검색되고 보고되는 최대값입니다.</span><span class="sxs-lookup"><span data-stu-id="76590-116">Max values are the maximum detected and reported during the session.</span></span>
 
<span data-ttu-id="76590-117">이 문제를 해결하는 방법의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="76590-117">Here's an example of how to troubleshoot this situation.</span></span> <span data-ttu-id="76590-118">호출 중에 네트워크 추적을 하고 처음 20분 동안 패킷 손실이 없지만 패킷 간격이 1.5초인 다음 나머지 호출에 대해 양호한 경우를 예를 들어보세요.</span><span class="sxs-lookup"><span data-stu-id="76590-118">Let's say you take a network trace during a call and the first 20 minutes there are no lost packets but then you have a gap of 1.5 seconds of packets and then good for the remainder of the call.</span></span> <span data-ttu-id="76590-119">Wireshark 추적 RTP <패킷 손실이 10%(0.1)로 평균됩니다.</span><span class="sxs-lookup"><span data-stu-id="76590-119">The average is going to be <10% (0.1) Packet loss even in a Wireshark trace RTP analysis.</span></span> <span data-ttu-id="76590-120">최대 패킷 손실은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="76590-120">What was the Max Packet Loss?</span></span> <span data-ttu-id="76590-121">5초 기간의 1.5초는 30%(0.3)입니다.</span><span class="sxs-lookup"><span data-stu-id="76590-121">1.5 Seconds in a 5-second period would be 30% (0.3).</span></span> <span data-ttu-id="76590-122">5초 샘플링 기간 내에 발생했나요(샘플링 기간 동안 분할될 수 있나요)</span><span class="sxs-lookup"><span data-stu-id="76590-122">Did that occur within the five second sampling period (maybe or it could be split over the sampling period)?</span></span>
 
<span data-ttu-id="76590-123">네트워크 메트릭이 평균 및 최대 값에서 양호한 경우 다른 원격 분석 데이터를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="76590-123">If network metrics look good in the averages and max values, then look to other telemetry data:</span></span> 
- <span data-ttu-id="76590-124">CPU 부족 이벤트 비율을 확인하여 사용 가능한 검색된 CPU 리소스가 부족하고 품질이 좋지 않은지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76590-124">Check CPU Insufficient Event Ratio to see if the detected CPU resources available were insufficient and caused poor quality.</span></span> 
- <span data-ttu-id="76590-125">스피커에 가까운 마이크로 인한 피드백을 방지하기 위해 오디오 장치가 반이중 모드인가요?</span><span class="sxs-lookup"><span data-stu-id="76590-125">Was the audio device in Half Duplex mode to prevent feedback due to microphones that are to close to speakers?</span></span> 
- <span data-ttu-id="76590-126">디바이스 반이중 AEC 이벤트 비율을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="76590-126">Check the Device Half Duplex AEC Event Ratio.</span></span> <span data-ttu-id="76590-127">허브 또는 도킹 스테이션에 연결할 때 USB 오디오 드롭아웃으로 인해 디바이스가 떨어지거나 마이크가 떨어질 때 노이즈 또는 정적이 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="76590-127">Was the device glitching or the microphone glitching introducing noise or static due to USB Audio Drop outs when plugged into a Hub or Docking Station:</span></span>  
- <span data-ttu-id="76590-128">디바이스 글리치 및 마이크의 이벤트 비율을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="76590-128">Check the Device Glitches and Microphone glitches event ratios.</span></span> <span data-ttu-id="76590-129">디바이스 자체가 제대로 작동하나요?</span><span class="sxs-lookup"><span data-stu-id="76590-129">Was the device itself functioning properly?</span></span>  
- <span data-ttu-id="76590-130">캡처 및 렌더링 디바이스가 작동하지 않는 이벤트 비율을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="76590-130">Check the Capture and Render Device Not Functioning Event Ratios.</span></span>


<span data-ttu-id="76590-131">CQD 원격 분석에서 사용할 수 있는 차원 및 측정값에 대한 자세한 내용은 통화 품질 대시보드에서 사용할 수 있는 차원 및 [측정값을 읽습니다.](dimensions-and-measures-available-in-call-quality-dashboard.md)</span><span class="sxs-lookup"><span data-stu-id="76590-131">For more on dimensions and measures available in CQD telemetry, read [Dimensions and measurements available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>

<span data-ttu-id="76590-132">배경 소음의 경우 음소거 이벤트 비율을 확인하여 참가자가 음소거된 시간의 길이를 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76590-132">For background noise, check mute event ratio to see the length of time participants were muted.</span></span>
 
<span data-ttu-id="76590-133">CQD에서 자세한 보고서를 만들고 모임 ID를 필터링하여 모임의 모든 사용자와 스트림을 살펴보고 관심 있는 필드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="76590-133">Create detailed reports in CQD and filter on Meeting ID to look at all users and streams in a meeting and add the fields you are interested in.</span></span> <span data-ttu-id="76590-134">문제를 보고하는 사용자가 문제가 있는 사용자가 아될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76590-134">A user reporting the issue may not be the one that was having the issue.</span></span> <span data-ttu-id="76590-135">단지 환경을 보고하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76590-135">They are just reporting the experience.</span></span>
 
<span data-ttu-id="76590-136">원격 분석이 반드시 문제를 호출하는 것은 아니며 의사 결정을 보고 알릴 위치를 더 잘 이해하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76590-136">The telemetry will not necessarily call out the issue, but it can help you better understand where to look and inform your decisions.</span></span> <span data-ttu-id="76590-137">네트워크, 디바이스, 드라이버 또는 펌웨어 업데이트, 사용량 또는 사용자인가요?</span><span class="sxs-lookup"><span data-stu-id="76590-137">Is it network, device, driver or firmware updates, usage, or user?</span></span>

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a><span data-ttu-id="76590-138">측정값에 대해 통화 및 사용자 수 값이 최대 0.2% 차이를 표시하는 이유는 무엇일까요? 가장 정확한 볼륨을 얻을 수 있는 방법</span><span class="sxs-lookup"><span data-stu-id="76590-138">Why do I see up to 0.2% difference in call and user count values on measures and how to get most accurate volumes?</span></span> 
<span data-ttu-id="76590-139">호출 수 및 사용자 수 측정값을 계산하기 위해 데이터 집합의 호출 또는 사용자 식별자에 대해 고유한 countif 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="76590-139">To compute call count and user count measures, a distinct countif operation is performed against the call or user identifiers in the data set.</span></span> <span data-ttu-id="76590-140">큰 데이터 집합에서는 고유 countif 연산에 내재된 최대 0.2% 오류가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76590-140">On large data sets, there is an up to 0.2% error inherent with the distinct countif operation.</span></span> <span data-ttu-id="76590-141">가장 정확한 볼륨의 경우 이 고유 countif 작업에는 사용되지 않는 스트림 수 측정값을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76590-141">For the most accurate volume, you should rely on stream count measures since they do not rely on this distinct countif operation.</span></span> <span data-ttu-id="76590-142">데이터 볼륨을 줄이기 위해 필터링하면 오류가 감소할 수 있지만 고유한 호출 및 사용자 수에서 이 오류 원본을 제거하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76590-142">Filtering to reduce the data volume may reduce the error but may not eliminate this source of error in distinct call and user counts.</span></span> <span data-ttu-id="76590-143">[측정값이 영향을](dimensions-and-measures-available-in-call-quality-dashboard.md) 미치는 통화 품질 대시보드에서 사용할 수 있는 차원 및 측정값을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76590-143">Refer to [Dimensions and measurements available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md) for which measures are impacted.</span></span>


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a><span data-ttu-id="76590-144">비즈니스용 Skype의 CQD 데이터가 Teams의 CQD 데이터와 다른 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="76590-144">Why is CQD data from Skype for Business different than CQD data from Teams?</span></span> 


> [!IMPORTANT]
> <span data-ttu-id="76590-145">2020년 7월 1일을 기점으로 이전 CQD(CQD.lync.com)는 최신 CQD(CQD)의 데이터를 사용하게 됩니다. Teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="76590-145">As of July 1, 2020, the older CQD (CQD.lync.com) uses data from the latest CQD (CQD.Teams.microsoft.com).</span></span> <span data-ttu-id="76590-146">이전 CQD 데이터를 더 이상 사용할 수 없습니다. 건물 또는 보고서 데이터를 내보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76590-146">The older CQD data is no longer available, and you can't export your building or report data.</span></span> <span data-ttu-id="76590-147">비즈니스용 Skype 관리 CQD.lync.com 사용 가능)을 계속 사용할 수 있지만, CQD로 이동해야 CQD.lync.com 수 있습니다. Teams.microsoft.com 아직 수행하지 않은 경우 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76590-147">You can still use CQD.lync.com (available from the Skype for Business admin center), but we'll turn off access to CQD.lync.com soon, so you should move to CQD.Teams.microsoft.com if you haven't already done so.</span></span>


<span data-ttu-id="76590-148">비즈니스용 Skype 레거시 포털(cqd.lync.com)의 이전 CQD와 Teams 관리 센터(cqd.teams.microsoft.com)의 최신 CQD 간에 데이터를 비교하려는 경우 데이터가 일치하지 않는 것을 빠르게 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76590-148">If you're trying to compare data between the older CQD from the Skype for Business legacy portal (cqd.lync.com) and the latest CQD from the Teams admin center (cqd.teams.microsoft.com), you'll quickly notice that the data doesn't match.</span></span> <span data-ttu-id="76590-149">이는 최신 CQD가 많은 추가 호출 시나리오를 보고하기 때문에입니다.</span><span class="sxs-lookup"><span data-stu-id="76590-149">That's because the latest CQD reports on many additional calling scenarios.</span></span> <span data-ttu-id="76590-150">이전 CQD의 보고서를 계속 사용 중이면 비즈니스용 Skype 서버용 통화 품질 대시보드와 같은 보고서를 해석할 수 있도록 이 [문서를 사용하세요.](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard)</span><span class="sxs-lookup"><span data-stu-id="76590-150">If you're still using reports from the older CQD, use this article to help you interpret those reports: [Call Quality Dashboard for Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard).</span></span>


  
### <a name="why-cant-i-see-euii-in-cqd"></a><span data-ttu-id="76590-151">CQD에서 EUII를 볼 수 없는 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="76590-151">Why can't I see EUII in CQD?</span></span>

<span data-ttu-id="76590-152">이러한 관리자 역할은 CQD에 액세스할 수 있지만 EUII(최종 사용자 식별 정보)를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76590-152">These admin roles can access CQD, but they can't view EUII (end-user identifiable information):</span></span>
- <span data-ttu-id="76590-153">Microsoft 365 보고서 읽기 읽기</span><span class="sxs-lookup"><span data-stu-id="76590-153">Microsoft 365 Reports Reader</span></span>
- <span data-ttu-id="76590-154">Teams Communications 지원 전문가</span><span class="sxs-lookup"><span data-stu-id="76590-154">Teams Communications Support Specialist</span></span>

<span data-ttu-id="76590-155">EUII를 포함하여 CQD에 액세스할 수 있는 역할에 대한 자세한 내용은 CQD에 액세스하기 위한 역할 [할당을 읽어 읽습니다.](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)</span><span class="sxs-lookup"><span data-stu-id="76590-155">To learn more about roles that can access CQD - including EUII - read [Assign roles for accessing CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).</span></span>

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a><span data-ttu-id="76590-156">Teams로만 필터링한 경우 CQD에 비즈니스용 Skype 정보가 표시되는 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="76590-156">Why am I seeing Skype for Business information in CQD when I've filtered for Teams only?</span></span>

<span data-ttu-id="76590-157">CQD 보고서(isTeams = 1)에서만 Teams를 필터링하는 경우 첫 번째 엔드포인트가 Teams인 모든 *호출을* 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="76590-157">When you filter for Teams only in CQD reports (isTeams = 1), you're filtering for all calls where the *first endpoint* is Teams.</span></span> <span data-ttu-id="76590-158">두 *번째 엔드포인트가* 비즈니스용 Skype인 경우 해당 정보가 CQD 보고서에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76590-158">If the *second endpoint* is Skype for Business, that information will show up in your CQD report.</span></span>

<span data-ttu-id="76590-159">CQDv3에는 CQDv2가 없는 새로운 시나리오가 있을 것이기 때문에 CQDv2 및 CQDv3의 총 수는 항상 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="76590-159">CQDv2 and CQDv3 will always have different total counts since CQDv3 will have new scenarios that CQDv2 will not have.</span></span> <span data-ttu-id="76590-160">이 때문에 필터가 없는 요약 합계 또는 집계된 모든 숫자를 비교하면 이러한 예상된 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76590-160">That’s why comparing Summary Total or Aggregated all-up numbers with no filters will have these expected differences.</span></span>  

<span data-ttu-id="76590-161">고객의 시나리오에 따라 CQDv3에는 SFB 2019의 프레미스 호출(SFB 2019가 데이터 커넥터와 함께 사용되는 경우), Skype 봇 호출(AA, CVI, VDI), 라이브 이벤트 및 PSTN 통화가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="76590-161">Depending on Customers’ scenario, CQDv3 will include SFB 2019 on-premises calls (if SFB 2019 is used with a data connector), Skype Bot calls (AA, CVI, VDI), Live Events and PSTN calls.</span></span> <span data-ttu-id="76590-162">고객이 사용할 수 있지만 해당 데이터가 CQD V2에 없는 시나리오/기능입니다.</span><span class="sxs-lookup"><span data-stu-id="76590-162">Scenarios/Features which are available for the customers, but their data are not in CQD V2.</span></span>

<span data-ttu-id="76590-163">예를 들어 CQD V2 요약 보고서에서 5,000개 오류가 있는 200,000개 오디오 스트림이 고객에게 표시될 것으로 예상됩니다. CQD V3의 5500개 오류(2019년 온-프레미스 호출, CVI 호출, PSTN 호출 등에서 발생)가 있는 300,000개 오디오 스트림과 반대입니다.</span><span class="sxs-lookup"><span data-stu-id="76590-163">For instance, it is expected that your customers and you will see 200,000 audio streams, with 5000 failures in CQD V2 Summary Report; versus 300,000 audio streams with 5500 failures (coming from 2019 on-prem calls, CVI calls, PSTN calls etc) in CQD V3.</span></span>

<span data-ttu-id="76590-164">예기치 않은 차이가 있는지 확인하려면 전체 데이터의 다양한 분석 데이터를 살펴봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76590-164">In order to determine, if there are any unexpected differences, you must look at various breakdowns of the overall data.</span></span>  <span data-ttu-id="76590-165">의도와 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="76590-165">Compare with intent.</span></span>  <span data-ttu-id="76590-166">사용자 에이전트 범주 쌍별로 데이터를 구분하는 것이 가장 먼저 권장되는 항목 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="76590-166">Slicing the data by User Agent Category Pair is one of the first things we recommend.</span></span>  <span data-ttu-id="76590-167">*첫 번째 제품* 및 *두 번째 제품도* 좋은 슬라이서입니다.</span><span class="sxs-lookup"><span data-stu-id="76590-167">*First Product* and *Second Product* are also good slicers.</span></span>  

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a><span data-ttu-id="76590-168">내 사용자 지정 보고서가 더 많은 항목이 있을 때 최대 10,000개 행만 반환하는 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="76590-168">Why do my custom reports only return a maximum of 10,000 rows when I know there should be more entries?</span></span>

<span data-ttu-id="76590-169">CQD는 요약된 데이터 쿼리용으로 설계됐고 데이터 내보내기용으로 설계되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76590-169">CQD is designed for summarized data queries, and is not designed for data export.</span></span> <span data-ttu-id="76590-170">가능한 경우 10,000행 제한을 초과하지 않도록 보고서를 재구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="76590-170">We recommend restructuring your reports, where possible, to prevent the 10,000 row limit from being exceeded.</span></span> <span data-ttu-id="76590-171">월, 연도, 날짜, 지역, 국가 등 더 넓은 카디널리티 차원을 사용하여 KP를 확인하여 시작할 수 있습니다. 거기에서 점점 더 높은 카디널리티 차원으로 드릴다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76590-171">Start by looking at your KPIs using broader, lower-cardinality dimensions, such as Month, Year, Date, Region, Country, etc. From there, you can drill down into increasingly higher-cardinality dimensions.</span></span> <span data-ttu-id="76590-172">Helpdesk 및 Location-Enhanced 보고서는 모두 이 드릴다운 워크플로의 좋은 예를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="76590-172">The Helpdesk and Location-Enhanced Reports both provide good examples of this drill down workflow.</span></span>

## <a name="related-topics"></a><span data-ttu-id="76590-173">관련 항목</span><span class="sxs-lookup"><span data-stu-id="76590-173">Related topics</span></span>

[<span data-ttu-id="76590-174">Teams의 통화 품질 개선 및 모니터링</span><span class="sxs-lookup"><span data-stu-id="76590-174">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="76590-175">CQD란?</span><span class="sxs-lookup"><span data-stu-id="76590-175">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="76590-176">CQD(통화 품질 대시보드) 설정</span><span class="sxs-lookup"><span data-stu-id="76590-176">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="76590-177">테넌트 업로드 및 데이터 구축</span><span class="sxs-lookup"><span data-stu-id="76590-177">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="76590-178">CQD 데이터 및 보고서</span><span class="sxs-lookup"><span data-stu-id="76590-178">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="76590-179">CQD를 사용하여 통화 및 모임 품질 관리</span><span class="sxs-lookup"><span data-stu-id="76590-179">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="76590-180">CQD에서 사용할 수 있는 차원 및 측정값</span><span class="sxs-lookup"><span data-stu-id="76590-180">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="76590-181">CQD의 스트림 분류</span><span class="sxs-lookup"><span data-stu-id="76590-181">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="76590-182">Power BI를 사용하여 CQD 데이터 분석</span><span class="sxs-lookup"><span data-stu-id="76590-182">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)

[<span data-ttu-id="76590-183">Teams 문제 해결</span><span class="sxs-lookup"><span data-stu-id="76590-183">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
