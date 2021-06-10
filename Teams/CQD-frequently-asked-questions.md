---
title: CQD(품질 대시보드) 자주 묻는 질문(FAQ)
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
description: 자주 묻는 질문(FAQ) 및 CQD(전화 Microsoft Teams 품질 대시보드)에 대한 답변을 읽습니다.
ms.openlocfilehash: ad718df893b69b333dd63d224663238879fda8c7
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2021
ms.locfileid: "52718009"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a><span data-ttu-id="bdd94-103">CQD(품질 대시보드) 자주 묻는 질문(FAQ)</span><span class="sxs-lookup"><span data-stu-id="bdd94-103">Call Quality Dashboard (CQD) Frequently asked questions (FAQ)</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="bdd94-104">자주 묻는 질문</span><span class="sxs-lookup"><span data-stu-id="bdd94-104">Frequently asked questions</span></span>

[<span data-ttu-id="bdd94-105">하나 이상의 모임 참가자가 좋지 않은 경우 CQD에서 호출을 "Good"로 표시하는 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="bdd94-105">Why does CQD mark a call as "Good" if one or more meeting participants had a poor experience?</span></span>](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[<span data-ttu-id="bdd94-106">측정값에 대한 통화 및 사용자 수 값에 최대 0.2%의 차이를 표시하는 이유는 무엇일까요? </span><span class="sxs-lookup"><span data-stu-id="bdd94-106">Why do I see up to 0.2% difference in call and user count values on measures and how to get most accurate volumes? </span></span>](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[<span data-ttu-id="bdd94-107">CQD 데이터가 비즈니스용 Skype CQD 데이터와 다른 Teams?</span><span class="sxs-lookup"><span data-stu-id="bdd94-107">Why is CQD data from Skype for Business different than CQD data from Teams? </span></span>](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[<span data-ttu-id="bdd94-108">CQD에서 EUII를 볼 수 없는 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="bdd94-108">Why can't I see EUII in CQD?</span></span>](#why-cant-i-see-euii-in-cqd)

[<span data-ttu-id="bdd94-109">데이터만 필터링한 비즈니스용 Skype CQD에 Teams 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="bdd94-109">Why am I seeing Skype for Business information in CQD when I've filtered for Teams only?</span></span>](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[<span data-ttu-id="bdd94-110">내 사용자 지정 보고서는 더 많은 항목이 있는 경우 최대 10,000개 행만 반환하는 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="bdd94-110">Why do my custom reports only return a maximum of 10,000 rows when I know there should be more entries?</span></span>](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

[<span data-ttu-id="bdd94-111">WiFi VPN 연결이 WiFi 대신 Wired로 표시된 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="bdd94-111">Why do WiFi VPN connections show as Wired instead of WiFi?</span></span>](#why-do-wifi-vpn-connections-show-as-wired-instead-of-wifi)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a><span data-ttu-id="bdd94-112">하나 이상의 모임 참가자가 좋지 않은 경우 CQD에서 호출을 "Good"로 표시하는 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="bdd94-112">Why does CQD mark a call as "Good" if one or more meeting participants had a poor experience?</span></span>

<span data-ttu-id="bdd94-113">CQD가 스트림 분류에 사용하는 [규칙을 체크 아웃합니다.](stream-classification-in-call-quality-dashboard.md)</span><span class="sxs-lookup"><span data-stu-id="bdd94-113">Check out the rules CQD uses for [stream classification](stream-classification-in-call-quality-dashboard.md).</span></span>
 
<span data-ttu-id="bdd94-114">오디오 스트림의 경우 호출 길이에 따라 평균으로 계산되는 5개의 분류자 중 어느 것이든 "양호" 매개 변수 내에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-114">For audio streams, any of the five classifiers, which are calculated for the average based on the length of the call, could all be within "good" parameters.</span></span> <span data-ttu-id="bdd94-115">사용자가 오디오 드롭아웃, 정적 또는 글리치에 기여한 것을 경험하지 않았다는 것을 의미하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-115">It doesn't mean the users didn't experience something that contributed to an audio drop out, static, or glitch.</span></span> 

<span data-ttu-id="bdd94-116">네트워크 문제가 있는지 확인하려면 세션의 평균 값과 최대 값 사이의 델타를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-116">To determine if it was a network problem, look at the delta between the average values for the session and the max values.</span></span> <span data-ttu-id="bdd94-117">최대 값은 세션 중에 검색되고 보고되는 최대값입니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-117">Max values are the maximum detected and reported during the session.</span></span>
 
<span data-ttu-id="bdd94-118">이 문제를 해결하는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-118">Here's an example of how to troubleshoot this situation.</span></span> <span data-ttu-id="bdd94-119">호출하는 동안 네트워크 추적을 취하고 처음 20분 동안 패킷 손실은 없지만 1.5초의 패킷 간격이 있으며 나머지 호출에 대해 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-119">Let's say you take a network trace during a call and the first 20 minutes there are no lost packets but then you have a gap of 1.5 seconds of packets and then good for the remainder of the call.</span></span> <span data-ttu-id="bdd94-120">Wireshark 추적 RTP 분석에서도 <10%(0.1) 패킷 손실이 평균적으로 감소합니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-120">The average is going to be <10% (0.1) Packet loss even in a Wireshark trace RTP analysis.</span></span> <span data-ttu-id="bdd94-121">최대 패킷 손실이란?</span><span class="sxs-lookup"><span data-stu-id="bdd94-121">What was the Max Packet Loss?</span></span> <span data-ttu-id="bdd94-122">5초 동안 1.5초는 30%(0.3)입니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-122">1.5 Seconds in a 5-second period would be 30% (0.3).</span></span> <span data-ttu-id="bdd94-123">5초 샘플링 기간 내에 발생했나요(샘플링 기간으로 분할될 수도 있습니다)?</span><span class="sxs-lookup"><span data-stu-id="bdd94-123">Did that occur within the 5-second sampling period (maybe or it could be split over the sampling period)?</span></span>
 
<span data-ttu-id="bdd94-124">네트워크 메트릭이 평균 및 최대 값에서 양호한 경우 다른 원격 분석 데이터를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-124">If network metrics look good in the averages and max values, then look to other telemetry data:</span></span> 
- <span data-ttu-id="bdd94-125">CPU 부족 이벤트 비율을 확인하여 사용 가능한 검색된 CPU 리소스가 부족하고 품질이 좋지 않은지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-125">Check CPU Insufficient Event Ratio to see if the detected CPU resources available were insufficient and caused poor quality.</span></span> 
- <span data-ttu-id="bdd94-126">스피커에 가까운 마이크로 인한 피드백을 방지하기 위해 오디오 디바이스가 반이중 모드인가요?</span><span class="sxs-lookup"><span data-stu-id="bdd94-126">Was the audio device in Half Duplex mode to prevent feedback due to microphones that are to close to speakers?</span></span> 
- <span data-ttu-id="bdd94-127">디바이스 절반 듀플렉스 AEC 이벤트 비율을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-127">Check the Device Half Duplex AEC Event Ratio.</span></span> <span data-ttu-id="bdd94-128">허브 또는 도킹 스테이션에 연결할 때 USB 오디오 드롭아웃으로 인해 디바이스가 글리치 또는 마이크 글리치가 발생하여 소음이나 정적이 발생하나요?</span><span class="sxs-lookup"><span data-stu-id="bdd94-128">Was the device glitching or the microphone glitching introducing noise or static due to USB Audio Drop outs when plugged into a Hub or Docking Station?</span></span>  
- <span data-ttu-id="bdd94-129">디바이스 글리치 및 마이크 글리치 이벤트 비율을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-129">Check the Device Glitches and Microphone glitches event ratios.</span></span> <span data-ttu-id="bdd94-130">디바이스 자체가 제대로 작동하나요?</span><span class="sxs-lookup"><span data-stu-id="bdd94-130">Was the device itself functioning properly?</span></span>  
- <span data-ttu-id="bdd94-131">이벤트 비율이 작동하지 않는 캡처 및 렌더링 디바이스를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-131">Check the Capture and Render Device Not Functioning Event Ratios.</span></span>


<span data-ttu-id="bdd94-132">CQD 원격 분석에서 사용할 수 있는 차원 및 측정값에 대한 자세한 내용은 통화 품질 대시보드에서 사용할 수 있는 크기 및 [측정값을 읽어보아야 합니다.](dimensions-and-measures-available-in-call-quality-dashboard.md)</span><span class="sxs-lookup"><span data-stu-id="bdd94-132">For more on dimensions and measures available in CQD telemetry, read [Dimensions and measurements available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).</span></span>

<span data-ttu-id="bdd94-133">배경 소음의 경우 음소거 이벤트 비율을 확인하여 참가자가 음소거된 시간의 길이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-133">For background noise, check mute event ratio to see the length of time participants were muted.</span></span>
 
<span data-ttu-id="bdd94-134">CQD에서 자세한 보고서를 만들고 모임 ID를 필터링하여 모임의 모든 사용자 및 스트림을 보고 관심 있는 필드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-134">Create detailed reports in CQD and filter on Meeting ID to look at all users and streams in a meeting and add the fields you are interested in.</span></span> <span data-ttu-id="bdd94-135">문제를 보고하는 사용자가 문제가 있는 사용자일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-135">A user reporting the issue may not be the one that was having the issue.</span></span> <span data-ttu-id="bdd94-136">그들은 단지 환경을 보고하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-136">They are just reporting the experience.</span></span>
 
<span data-ttu-id="bdd94-137">원격 분석은 반드시 문제를 호출하지는 않지만 결정을 보고 알릴 위치를 더 잘 이해하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-137">The telemetry will not necessarily call out the issue, but it can help you better understand where to look and inform your decisions.</span></span> <span data-ttu-id="bdd94-138">네트워크, 디바이스, 드라이버 또는 펌웨어 업데이트, 사용량 또는 사용자인가요?</span><span class="sxs-lookup"><span data-stu-id="bdd94-138">Is it network, device, driver or firmware updates, usage, or user?</span></span>

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a><span data-ttu-id="bdd94-139">측정값에 대한 통화 및 사용자 수 값에 최대 0.2%의 차이를 표시하는 이유는 무엇일까요?</span><span class="sxs-lookup"><span data-stu-id="bdd94-139">Why do I see up to 0.2% difference in call and user count values on measures and how to get most accurate volumes?</span></span> 
<span data-ttu-id="bdd94-140">호출 수 및 사용자 수 측정값을 계산하기 위해 데이터 집합의 호출 또는 사용자 식별자에 대해 고유한 카운트프 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-140">To compute call count and user count measures, a distinct countif operation is performed against the call or user identifiers in the data set.</span></span> <span data-ttu-id="bdd94-141">큰 데이터 집합에서 고유 카운트프 연산에 내재된 최대 0.2%의 오류가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-141">On large data sets, there is an up to 0.2% error inherent with the distinct countif operation.</span></span> <span data-ttu-id="bdd94-142">가장 정확한 볼륨의 경우 이 고유한 countif 작업에는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-142">For the most accurate volume, you should rely on stream count measures since they do not rely on this distinct countif operation.</span></span> <span data-ttu-id="bdd94-143">데이터 볼륨을 줄이기 위해 필터링하면 오류를 줄일 수 있지만 고유한 호출 및 사용자 수에서 이 오류 원본을 제거하지는 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-143">Filtering to reduce the data volume may reduce the error but may not eliminate this source of error in distinct call and user counts.</span></span> <span data-ttu-id="bdd94-144">측정값이 영향을 미치는 [통화](dimensions-and-measures-available-in-call-quality-dashboard.md) 품질 대시보드에서 사용할 수 있는 크기 및 측정값을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bdd94-144">Refer to [Dimensions and measurements available in Call Quality Dashboard](dimensions-and-measures-available-in-call-quality-dashboard.md) for which measures are impacted.</span></span>


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a><span data-ttu-id="bdd94-145">CQD 데이터가 비즈니스용 Skype CQD 데이터와 다른 Teams?</span><span class="sxs-lookup"><span data-stu-id="bdd94-145">Why is CQD data from Skype for Business different than CQD data from Teams?</span></span> 


> [!IMPORTANT]
> <span data-ttu-id="bdd94-146">2020년 7월 1일부로 이전 CQD(CQD.lync.com)는 최신 CQD(CQD.Teams.microsoft.com)의 데이터를 microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="bdd94-146">As of July 1, 2020, the older CQD (CQD.lync.com) uses data from the latest CQD (CQD.Teams.microsoft.com).</span></span> <span data-ttu-id="bdd94-147">이전 CQD 데이터를 더 이상 사용할 수 없습니다. 건물 또는 보고서 데이터를 내보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-147">The older CQD data is no longer available, and you can't export your building or report data.</span></span> <span data-ttu-id="bdd94-148">여전히 CQD.lync.com(비즈니스용 Skype 관리 센터에서 사용 가능)를 사용할 수 있지만 곧 CQD.lync.com 끄기 때문에 CQD로 이동해야 합니다. Teams.microsoft.com 완료하지 않은 경우.</span><span class="sxs-lookup"><span data-stu-id="bdd94-148">You can still use CQD.lync.com (available from the Skype for Business admin center), but we'll turn off access to CQD.lync.com soon, so you should move to CQD.Teams.microsoft.com if you haven't already done so.</span></span>


<span data-ttu-id="bdd94-149">이전 레거시 포털(비즈니스용 Skype)의 이전 CQD(cqd.lync.com)와 Teams 관리 센터(cqd.teams.microsoft.com)의 최신 CQD 간에 데이터를 비교하려는 경우 데이터가 일치하지 않는 것을 빠르게 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-149">If you're trying to compare data between the older CQD from the Skype for Business legacy portal (cqd.lync.com) and the latest CQD from the Teams admin center (cqd.teams.microsoft.com), you'll quickly notice that the data doesn't match.</span></span> <span data-ttu-id="bdd94-150">최신 CQD가 여러 추가 호출 시나리오에 대해 보고하기 때문에입니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-150">That's because the latest CQD reports on many additional calling scenarios.</span></span> <span data-ttu-id="bdd94-151">이전 CQD의 보고서를 계속 사용 중이면 이 문서를 사용하여 해당 보고서를 해석하는 [데 도움이 비즈니스용 Skype 서버.](/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard)</span><span class="sxs-lookup"><span data-stu-id="bdd94-151">If you're still using reports from the older CQD, use this article to help you interpret those reports: [Call Quality Dashboard for Skype for Business Server](/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard).</span></span>


  
### <a name="why-cant-i-see-euii-in-cqd"></a><span data-ttu-id="bdd94-152">CQD에서 EUII를 볼 수 없는 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="bdd94-152">Why can't I see EUII in CQD?</span></span>

<span data-ttu-id="bdd94-153">이러한 관리자 역할은 CQD에 액세스할 수 있지만 EUII(최종 사용자 식별 정보)를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-153">These admin roles can access CQD, but they can't view EUII (end-user identifiable information):</span></span>
- <span data-ttu-id="bdd94-154">Microsoft 365 보고서 읽기</span><span class="sxs-lookup"><span data-stu-id="bdd94-154">Microsoft 365 Reports Reader</span></span>
- <span data-ttu-id="bdd94-155">Teams 통신 지원 전문가</span><span class="sxs-lookup"><span data-stu-id="bdd94-155">Teams Communications Support Specialist</span></span>

<span data-ttu-id="bdd94-156">EUII를 포함하여 CQD에 액세스할 수 있는 역할에 대한 자세한 내용은 CQD에 액세스하기 위한 역할 [할당 을 읽어보아야 합니다.](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)</span><span class="sxs-lookup"><span data-stu-id="bdd94-156">To learn more about roles that can access CQD - including EUII - read [Assign roles for accessing CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).</span></span>

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a><span data-ttu-id="bdd94-157">데이터만 필터링한 비즈니스용 Skype CQD에 Teams 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="bdd94-157">Why am I seeing Skype for Business information in CQD when I've filtered for Teams only?</span></span>

<span data-ttu-id="bdd94-158">CQD Teams(isTeams = 1)에서만 필터링하면 첫 번째 엔드포인트가 Teams. </span><span class="sxs-lookup"><span data-stu-id="bdd94-158">When you filter for Teams only in CQD reports (isTeams = 1), you're filtering for all calls where the *first endpoint* is Teams.</span></span> <span data-ttu-id="bdd94-159">두 *번째 엔드포인트가* 비즈니스용 Skype CQD 보고서에 해당 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-159">If the *second endpoint* is Skype for Business, that information will show up in your CQD report.</span></span>

<span data-ttu-id="bdd94-160">CQDv2 및 CQDv3에는 CQDv2가 없는 새 시나리오가 있을 것이기 때문에 항상 총 수가 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-160">CQDv2 and CQDv3 will always have different total counts since CQDv3 will have new scenarios that CQDv2 will not have.</span></span> <span data-ttu-id="bdd94-161">이 때문에 필터가 없는 요약 합계 또는 집계된 올업 번호를 비교하면 이러한 예상되는 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-161">That’s why comparing Summary Total or Aggregated all-up numbers with no filters will have these expected differences.</span></span>  

<span data-ttu-id="bdd94-162">고객의 시나리오에 따라 CQDv3에는 SFB 2019-프레미스 호출(SFB 2019가 데이터 커넥터와 함께 사용되는 경우), 봇 호출(AA, CVI, VDI Skype), 라이브 이벤트 및 PSTN 호출이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-162">Depending on Customers’ scenario, CQDv3 will include SFB 2019 on-premises calls (if SFB 2019 is used with a data connector), Skype Bot calls (AA, CVI, VDI), Live Events and PSTN calls.</span></span> <span data-ttu-id="bdd94-163">고객이 사용할 수 있지만 해당 데이터는 CQD V2에 없는 시나리오/기능입니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-163">Scenarios/Features which are available for the customers, but their data are not in CQD V2.</span></span>

<span data-ttu-id="bdd94-164">예를 들어 CQD V2 요약 보고서에 5000개 오류가 있는 200,000개 오디오 스트림이 고객과 함께 표시될 것으로 예상됩니다. CQD V3에서 5500개 오류(2019 온-프레미스 호출, CVI 호출, PSTN 호출 등)가 있는 오디오 스트림 수 300,000개와 대합니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-164">For instance, it is expected that your customers and you will see 200,000 audio streams, with 5000 failures in CQD V2 Summary Report; versus 300,000 audio streams with 5500 failures (coming from 2019 on-prem calls, CVI calls, PSTN calls, etc.) in CQD V3.</span></span>

<span data-ttu-id="bdd94-165">예기치 않은 차이점이 있는지 확인하려면 전체 데이터의 다양한 분석 데이터를 살펴봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-165">In order to determine, if there are any unexpected differences, you must look at various breakdowns of the overall data.</span></span>  <span data-ttu-id="bdd94-166">의도와 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-166">Compare with intent.</span></span>  <span data-ttu-id="bdd94-167">사용자 에이전트 범주 쌍별로 데이터를 구분하는 것이 가장 먼저 권장되는 항목 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-167">Slicing the data by User Agent Category Pair is one of the first things we recommend.</span></span>  <span data-ttu-id="bdd94-168">*첫 번째 제품* 및 *두 번째 제품도* 좋은 슬라이서입니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-168">*First Product* and *Second Product* are also good slicers.</span></span>  

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a><span data-ttu-id="bdd94-169">내 사용자 지정 보고서는 더 많은 항목이 있는 경우 최대 10,000개 행만 반환하는 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="bdd94-169">Why do my custom reports only return a maximum of 10,000 rows when I know there should be more entries?</span></span>

<span data-ttu-id="bdd94-170">CQD는 요약된 데이터 쿼리를 위해 설계됐고 데이터 내보내기용으로 설계되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-170">CQD is designed for summarized data queries, and is not designed for data export.</span></span> <span data-ttu-id="bdd94-171">가능한 경우 10,000개 행 제한을 초과하지 않도록 보고서를 다시 구조화하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-171">We recommend restructuring your reports, where possible, to prevent the 10,000 row limit from being exceeded.</span></span> <span data-ttu-id="bdd94-172">월, 연도, 날짜, 지역, 국가 등 더 광범위하고 낮은 카디널리티 차원을 사용하여 KPIS를 확인하여 시작 거기에서 점점 더 높은 카디널리티 차원으로 드릴다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-172">Start by looking at your KPIs using broader, lower-cardinality dimensions, such as Month, Year, Date, Region, Country, etc. From there, you can drill down into increasingly higher-cardinality dimensions.</span></span> <span data-ttu-id="bdd94-173">헬프데스크 및 Location-Enhanced 보고서는 모두 이 드릴다운 워크플로의 좋은 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-173">The Helpdesk and Location-Enhanced Reports both provide good examples of this drill down workflow.</span></span>

### <a name="why-do-wifi-vpn-connections-show-as-wired-instead-of-wifi"></a><span data-ttu-id="bdd94-174">WiFi VPN 연결이 WiFi 대신 Wired로 표시된 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="bdd94-174">Why do WiFi VPN connections show as Wired instead of WiFi?</span></span>

<span data-ttu-id="bdd94-175">예상된 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-175">This is expected.</span></span> <span data-ttu-id="bdd94-176">VPN 공급 업체는 유선 연결처럼 처리되는 가상 이더넷 어댑터를 만들었다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-176">The VPN vendor created a virtual ethernet adapter which is treated like a wired connection.</span></span> <span data-ttu-id="bdd94-177">제대로 레이블이 지정되지 않은 운영 체제는 WiFi 연결인지 모르고 유선으로 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="bdd94-177">Since it's not properly labeled, the operating system doesn't know it's a WiFi connection and reports it as wired.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bdd94-178">관련 항목</span><span class="sxs-lookup"><span data-stu-id="bdd94-178">Related topics</span></span>

[<span data-ttu-id="bdd94-179">통화 품질 향상 및 모니터링 Teams</span><span class="sxs-lookup"><span data-stu-id="bdd94-179">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="bdd94-180">CQD란?</span><span class="sxs-lookup"><span data-stu-id="bdd94-180">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="bdd94-181">CQD(통화 품질 대시보드) 설정</span><span class="sxs-lookup"><span data-stu-id="bdd94-181">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="bdd94-182">업로드 데이터 구축</span><span class="sxs-lookup"><span data-stu-id="bdd94-182">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="bdd94-183">CQD 데이터 및 보고서</span><span class="sxs-lookup"><span data-stu-id="bdd94-183">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="bdd94-184">CQD를 사용하여 통화 및 모임 품질 관리</span><span class="sxs-lookup"><span data-stu-id="bdd94-184">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="bdd94-185">CQD에서 사용할 수 있는 차원 및 측정값</span><span class="sxs-lookup"><span data-stu-id="bdd94-185">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="bdd94-186">CQD의 스트림 분류</span><span class="sxs-lookup"><span data-stu-id="bdd94-186">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="bdd94-187">CQD Power BI 분석하는 데 Power BI 사용</span><span class="sxs-lookup"><span data-stu-id="bdd94-187">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)

[<span data-ttu-id="bdd94-188">Teams 문제 해결</span><span class="sxs-lookup"><span data-stu-id="bdd94-188">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
