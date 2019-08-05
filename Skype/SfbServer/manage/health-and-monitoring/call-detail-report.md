---
title: 비즈니스용 Skype 서버의 통화 세부 정보 보고서
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38862e35-3fec-41b9-a035-0b301942d446
description: '요약: 비즈니스용 Skype 서버에서 사용 되는 통화 정보 보고서에 대해 알아봅니다.'
ms.openlocfilehash: 8ced1a93f32f5f62ad33563e295ec456303232fc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191412"
---
# <a name="call-detail-report-in-skype-for-business-server"></a><span data-ttu-id="0993b-103">비즈니스용 Skype 서버의 통화 세부 정보 보고서</span><span class="sxs-lookup"><span data-stu-id="0993b-103">Call Detail Report in Skype for Business Server</span></span>
 
<span data-ttu-id="0993b-104">**요약:** 비즈니스용 Skype 서버에서 사용 되는 통화 정보 보고서에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-104">**Summary:** Learn about the Call Detail Report used in Skype for Business Server.</span></span>
  
<span data-ttu-id="0993b-105">통화 정보 보고서는 개별 통화에 대 한 자세한 정보를 제공 합니다. 이 보고서에는 비즈니스용 Skype Server에서 수집한 경험 메트릭과 통계의 거의 모든 품질이 포함 되어 있으며, 다음과 같은 보고서 섹션으로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-105">The Call Detail Report provides a detailed look at an individual call; the report includes nearly all the Quality of Experience metrics and statistics collected by Skype for Business Server, divided into report sections such as:</span></span>
  
- <span data-ttu-id="0993b-106">통화 정보</span><span class="sxs-lookup"><span data-stu-id="0993b-106">Call Information</span></span> 
    
- <span data-ttu-id="0993b-107">발신자 장치 및 신호 메트릭</span><span class="sxs-lookup"><span data-stu-id="0993b-107">Caller Device and Signal Metrics</span></span>
    
- <span data-ttu-id="0993b-108">호출 수신자 장치 및 신호 메트릭</span><span class="sxs-lookup"><span data-stu-id="0993b-108">Callee Device and Signal metrics</span></span>
    
- <span data-ttu-id="0993b-109">발신자 클라이언트 이벤트</span><span class="sxs-lookup"><span data-stu-id="0993b-109">Caller Client Event</span></span>
    
- <span data-ttu-id="0993b-110">호출 수신자 클라이언트 이벤트</span><span class="sxs-lookup"><span data-stu-id="0993b-110">Callee Client Event</span></span>
    
- <span data-ttu-id="0993b-111">오디오 스트림 (호출자 to 피호출자)</span><span class="sxs-lookup"><span data-stu-id="0993b-111">Audio Stream (Caller to Callee)</span></span>
    
- <span data-ttu-id="0993b-112">비디오 스트림 (호출자 to 피호출자)</span><span class="sxs-lookup"><span data-stu-id="0993b-112">Video Stream (Caller to Callee)</span></span>
    
- <span data-ttu-id="0993b-113">오디오 스트림 (피호출자를 호출자로)</span><span class="sxs-lookup"><span data-stu-id="0993b-113">Audio Stream (Callee to Caller)</span></span>
    
- <span data-ttu-id="0993b-114">비디오 스트림 (호출자에 게 피호출자)</span><span class="sxs-lookup"><span data-stu-id="0993b-114">Video Stream (Callee to Caller)</span></span>
    
<span data-ttu-id="0993b-115">지정 된 보고서에 표시 되는 범주와 메트릭은 세션의 종류와 세션에 사용 되는 끝점의 형식에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-115">Keep in mind that the categories and the metrics you see on a given report depend on two things: the type of session and the type of endpoints used in the session.</span></span> <span data-ttu-id="0993b-116">예를 들어 오디오 전용 통화는 비디오 스트림에 대 한 메트릭을 보고 하지 않습니다. 이는 통화에 비디오 스트림이 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-116">For example, an audio-only call will not report metrics for video streams; that's because the call didn't have a video stream.</span></span> <span data-ttu-id="0993b-117">마찬가지로 호출자 통계는 포함 되지만 호출 수신자 통계는 나열 되지 않는 보고서가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-117">Likewise, you might have a report that lists caller statistics but not callee statistics.</span></span> <span data-ttu-id="0993b-118">이는 일반적으로 호출 수신자가 SIP 호환 장치를 사용 하지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-118">That's typically because the callee was not using a SIP-compliant device.</span></span> <span data-ttu-id="0993b-119">끝점은 통화 종료 시 통계 보고를 담당 합니다. 그러나 휴대폰 (SIP 또는 SIP 통계에 대 한 자세한 내용은 없음)은 해당 정보를 보고할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-119">Endpoints are responsible for reporting statistics at the end of a call; however, a cell phone (which knows nothing about SIP or SIP statistics) is unable to report that kind of information.</span></span> <span data-ttu-id="0993b-120">다른 사람에 게 전화를 걸어 휴대폰으로 전화를 받은 경우 통화가 종료 되 면 해당 휴대폰에서 보고서를 가져오지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-120">If you call someone and they answer you on their cell phone, you will not get a report from that cell phone when the call ends.</span></span>
  
<span data-ttu-id="0993b-121">통화 정보 보고서는 특정 통화에 미디어 품질 문제가 발생 한 이유를 정확히 확인 하려는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-121">The Call Detail Report is most useful when you are trying to determine exactly why a given call experienced media quality problems.</span></span>
  
## <a name="accessing-the-call-detail-report"></a><span data-ttu-id="0993b-122">통화 정보 보고서에 액세스</span><span class="sxs-lookup"><span data-stu-id="0993b-122">Accessing the Call Detail Report</span></span>

<span data-ttu-id="0993b-123">다음 보고서에서 통화 정보 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-123">The Call Detail Report can be accessed from any of the following reports:</span></span>
  
- <span data-ttu-id="0993b-124">[비즈니스용 Skype Server (location-report.md)의 [위치 보고서] (통화 볼륨 또는 잘못 된 통화 백분율 메트릭 클릭)</span><span class="sxs-lookup"><span data-stu-id="0993b-124">The [Location Report in Skype for Business Server (location-report.md) (by clicking either the Call volume or the Poor call percentage metric)</span></span>
    
- <span data-ttu-id="0993b-125">[비즈니스용 Skype Server (summary.md)의 [미디어 품질 요약 보고서] (통화 볼륨 또는 잘못 된 통화 백분율 메트릭 클릭)</span><span class="sxs-lookup"><span data-stu-id="0993b-125">The [Media Quality Summary Report in Skype for Business Server (summary.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>
    
- <span data-ttu-id="0993b-126">비즈니스용 skype [서버의 미디어 품질 비교 보고서](comparison.md) (비즈니스용 [Skype 서버에서 통화 목록 보고서](call-list-report-0.md) 를 클릭 한 다음 세부 정보 메트릭 클릭)</span><span class="sxs-lookup"><span data-stu-id="0993b-126">The [Media Quality Comparison Report in Skype for Business Server](comparison.md) (by clicking the [Call List Report in Skype for Business Server](call-list-report-0.md) and then clicking the Detail metric).</span></span>
    
- <span data-ttu-id="0993b-127">[비즈니스용 Skype 서버의 서버 성능 보고서](server-performance.md) (통화 볼륨 또는 잘못 된 통화 백분율 메트릭을 클릭 하 여)</span><span class="sxs-lookup"><span data-stu-id="0993b-127">The [Server Performance Report in Skype for Business Server](server-performance.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>
    
- <span data-ttu-id="0993b-128">[비즈니스용 Skype 서버의 통화 목록 보고서](call-list-report-0.md) (세부 메트릭 클릭)</span><span class="sxs-lookup"><span data-stu-id="0993b-128">The [Call List Report in Skype for Business Server](call-list-report-0.md) (by clicking the Detail metric)</span></span>
    
<span data-ttu-id="0993b-129">통화 세부 정보 보고서 내에서 다음 메트릭 중 하나를 클릭 하 여 [비즈니스용 Skype 서버에서 장치 보고서](device-report.md) 에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-129">From within the Call Detail Report you can access the [Device Report in Skype for Business Server](device-report.md) by clicking either of the following metrics:</span></span>
  
- <span data-ttu-id="0993b-130">캡처 장치</span><span class="sxs-lookup"><span data-stu-id="0993b-130">Capture device</span></span>
    
- <span data-ttu-id="0993b-131">렌더링 장치</span><span class="sxs-lookup"><span data-stu-id="0993b-131">Render device</span></span>
    
<span data-ttu-id="0993b-132">A/V edge 서버 메트릭을 클릭 하 여 서버 미디어 품질 추세 보고서에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-132">You can also access the Server Media Quality Trend Report by clicking the A/V edge server metric.</span></span>
  
## <a name="making-the-best-use-of-the-call-detail-report"></a><span data-ttu-id="0993b-133">통화 정보 보고서를 최대한 활용 하기</span><span class="sxs-lookup"><span data-stu-id="0993b-133">Making the Best Use of the Call Detail Report</span></span>

<span data-ttu-id="0993b-134">일반적으로 통화 세부 정보 보고서에는 마이크 타임 스탬프 드리프트, 낮은 우선 r 시간, 가까운 끝, 에코 시간 등의 항목을 포함 하 여 250의 다른 메트릭이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-134">The Call Detail Report typically includes over 250 different metrics, including such items as Microphone timestamp drift, Low SNR time, and Near end to echo time.</span></span> <span data-ttu-id="0993b-135">이러한 모든 메트릭이 실제로 측정 하는 것을 잊어버린 경우에는 미터법 레이블 위에 마우스를 누른 채 보세요. 종종 해당 메트릭에 대해 설명 하는 도구 설명이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-135">If you can't remember what all of these metrics actually measure, try holding your mouse over the metric label; often-times, a tooltip will appear describing that metric.</span></span>
  
<span data-ttu-id="0993b-136">메트릭을 찾는 데 문제가 있는 경우 검색 상자에 메트릭 레이블의 일부를 입력 한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-136">If you have problems locating a metric, type part of the metric label in the search box, and then click **Find**.</span></span> <span data-ttu-id="0993b-137">예를 들어 낮은 SNR 시간 메트릭을 찾을 수 없는 경우 검색 상자에 SNR을 입력 한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-137">For example, if you can't find the Low SNR time metric, type SNR in the search box, and then click **Find**.</span></span>
  
<span data-ttu-id="0993b-138">보고서는 통화에 대 한 정보만 추적 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="0993b-138">Note that the report only tracks information about a call.</span></span> <span data-ttu-id="0993b-139">통화 자체는 기록 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-139">The call itself is not recorded.</span></span>
  
## <a name="filters"></a><span data-ttu-id="0993b-140">필터가</span><span class="sxs-lookup"><span data-stu-id="0993b-140">Filters</span></span>

<span data-ttu-id="0993b-141">없음.</span><span class="sxs-lookup"><span data-stu-id="0993b-141">None.</span></span> <span data-ttu-id="0993b-142">통화 정보 보고서는 필터링 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-142">You cannot filter the Call Detail Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="0993b-143">매트릭스</span><span class="sxs-lookup"><span data-stu-id="0993b-143">Metrics</span></span>

<span data-ttu-id="0993b-144">다음 표에는 각 통화에 대 한 통화 정보 보고서에서 제공 하는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-144">The following table lists the information provided in the Call Detail Report for each call.</span></span>
  
<span data-ttu-id="0993b-145">**통화 세부 정보 보고서 메트릭**</span><span class="sxs-lookup"><span data-stu-id="0993b-145">**Call Detail Report Metrics**</span></span>

|<span data-ttu-id="0993b-146">**이름**</span><span class="sxs-lookup"><span data-stu-id="0993b-146">**Name**</span></span>|<span data-ttu-id="0993b-147">**이 항목을 정렬할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="0993b-147">**Can you sort on this item?**</span></span>|<span data-ttu-id="0993b-148">**설명**</span><span class="sxs-lookup"><span data-stu-id="0993b-148">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0993b-149">**발신자 PAI**</span><span class="sxs-lookup"><span data-stu-id="0993b-149">**Caller PAI**</span></span> <br/> |<span data-ttu-id="0993b-150">아니요</span><span class="sxs-lookup"><span data-stu-id="0993b-150">No</span></span>  <br/> |<span data-ttu-id="0993b-151">P-어설션 됨-통화를 시작한 사용자의 Id입니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-151">P-Asserted-Identity of the user who initiated the call.</span></span> <span data-ttu-id="0993b-152">P-어설션된-Id는 신뢰할 수 있는 네트워크 내에서 사용자의 증명 된 id를 전달 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-152">The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span>  <br/> |
|<span data-ttu-id="0993b-153">**발신자 URI**</span><span class="sxs-lookup"><span data-stu-id="0993b-153">**Caller URI**</span></span> <br/> |<span data-ttu-id="0993b-154">아니요</span><span class="sxs-lookup"><span data-stu-id="0993b-154">No</span></span>  <br/> |<span data-ttu-id="0993b-155">통화를 시작한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-155">SIP address of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="0993b-156">**발신자 끝점**</span><span class="sxs-lookup"><span data-stu-id="0993b-156">**Caller endpoint**</span></span> <br/> |<span data-ttu-id="0993b-157">아니요</span><span class="sxs-lookup"><span data-stu-id="0993b-157">No</span></span>  <br/> |<span data-ttu-id="0993b-158">전화를 걸 때 사용 하는 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-158">Device used to make the call.</span></span>  <br/> |
|<span data-ttu-id="0993b-159">**발신자 사용자 에이전트**</span><span class="sxs-lookup"><span data-stu-id="0993b-159">**Caller user agent**</span></span> <br/> |<span data-ttu-id="0993b-160">아니요</span><span class="sxs-lookup"><span data-stu-id="0993b-160">No</span></span>  <br/> |<span data-ttu-id="0993b-161">통화를 한 장치에서 사용 하는 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="0993b-161">Software used on the device that made the call.</span></span>  <br/> |
|<span data-ttu-id="0993b-162">**통화 시작**</span><span class="sxs-lookup"><span data-stu-id="0993b-162">**Call start**</span></span> <br/> |<span data-ttu-id="0993b-163">아니요</span><span class="sxs-lookup"><span data-stu-id="0993b-163">No</span></span>  <br/> |<span data-ttu-id="0993b-164">통화가 처음에 배치 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-164">Date and time that the call was initially placed.</span></span>  <br/> |
|<span data-ttu-id="0993b-165">**중재 서버 바이패스 통화**</span><span class="sxs-lookup"><span data-stu-id="0993b-165">**Mediation Server bypass call**</span></span> <br/> |<span data-ttu-id="0993b-166">아니요</span><span class="sxs-lookup"><span data-stu-id="0993b-166">No</span></span>  <br/> |<span data-ttu-id="0993b-167">호출이 중재 서버를 통과 하지 않고 PSTN 음성 게이트웨이 또는 정식 IP PBX에 연결 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-167">Indicates whether the call connected to a PSTN voice gateway or qualified IP-PBX without passing through the Mediation Server.</span></span>  <br/> |
|<span data-ttu-id="0993b-168">**발신자 OS**</span><span class="sxs-lookup"><span data-stu-id="0993b-168">**Caller OS**</span></span> <br/> |<span data-ttu-id="0993b-169">아니요</span><span class="sxs-lookup"><span data-stu-id="0993b-169">No</span></span>  <br/> |<span data-ttu-id="0993b-170">전화 걸기 컴퓨터의 운영 체제입니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-170">Operating system of the caller's computer.</span></span>  <br/> |
|<span data-ttu-id="0993b-171">**호출자 CPU**</span><span class="sxs-lookup"><span data-stu-id="0993b-171">**Caller CPU**</span></span> <br/> |<span data-ttu-id="0993b-172">아니요</span><span class="sxs-lookup"><span data-stu-id="0993b-172">No</span></span>  <br/> |<span data-ttu-id="0993b-173">통화를 시작한 사용자의 컴퓨터에 설치 된 CPU입니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-173">CPU installed in the computer of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="0993b-174">**발신자 CPU 코어 번호**</span><span class="sxs-lookup"><span data-stu-id="0993b-174">**Caller CPU core number**</span></span> <br/> |<span data-ttu-id="0993b-175">아니요</span><span class="sxs-lookup"><span data-stu-id="0993b-175">No</span></span>  <br/> |<span data-ttu-id="0993b-176">통화를 시작한 사람이 사용 하는 컴퓨터의 프로세서 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-176">Processor number in the computer used by the person who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="0993b-177">**발신자 CPU 속도**</span><span class="sxs-lookup"><span data-stu-id="0993b-177">**Caller CPU speed**</span></span> <br/> |<span data-ttu-id="0993b-178">아니요</span><span class="sxs-lookup"><span data-stu-id="0993b-178">No</span></span>  <br/> |<span data-ttu-id="0993b-179">통화를 시작한 사람이 사용 하는 컴퓨터의 CPU 클록 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-179">Clock speed of the CPU of the computer used by the person who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="0993b-180">**발신자 CPU 가상화**</span><span class="sxs-lookup"><span data-stu-id="0993b-180">**Caller CPU virtualization**</span></span> <br/> |<span data-ttu-id="0993b-181">아니요</span><span class="sxs-lookup"><span data-stu-id="0993b-181">No</span></span>  <br/> |<span data-ttu-id="0993b-182">통화를 시작한 사람이 사용 하는 컴퓨터에서 사용 되는 가상화 (있는 경우)</span><span class="sxs-lookup"><span data-stu-id="0993b-182">Virtualization (if any) used on the computer used by the person who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="0993b-183">**호출 수신자 PAI**</span><span class="sxs-lookup"><span data-stu-id="0993b-183">**Callee PAI**</span></span> <br/> |<span data-ttu-id="0993b-184">아니요</span><span class="sxs-lookup"><span data-stu-id="0993b-184">No</span></span>  <br/> |<span data-ttu-id="0993b-185">P-어설션 됨-통화에 참가 하도록 초대 받은 사용자의 Id입니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-185">P-Asserted-Identity of the user who was invited to join the call.</span></span> <span data-ttu-id="0993b-186">P-어설션된-Id는 신뢰할 수 있는 네트워크 내에서 사용자의 증명 된 id를 전달 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-186">The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span>  <br/> |
|<span data-ttu-id="0993b-187">**호출 수신자 URI**</span><span class="sxs-lookup"><span data-stu-id="0993b-187">**Callee URI**</span></span> <br/> |<span data-ttu-id="0993b-188">아니요</span><span class="sxs-lookup"><span data-stu-id="0993b-188">No</span></span>  <br/> |<span data-ttu-id="0993b-189">호출 된 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-189">SIP address of the user who was called.</span></span>  <br/> |
|<span data-ttu-id="0993b-190">**호출 수신자 끝점**</span><span class="sxs-lookup"><span data-stu-id="0993b-190">**Callee endpoint**</span></span> <br/> |<span data-ttu-id="0993b-191">아니요</span><span class="sxs-lookup"><span data-stu-id="0993b-191">No</span></span>  <br/> |<span data-ttu-id="0993b-192">통화를 수신 하는 데 사용 되는 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-192">Device used to receive the call.</span></span>  <br/> |
|<span data-ttu-id="0993b-193">**호출 수신자 사용자 에이전트**</span><span class="sxs-lookup"><span data-stu-id="0993b-193">**Callee user agent**</span></span> <br/> |<span data-ttu-id="0993b-194">아니요</span><span class="sxs-lookup"><span data-stu-id="0993b-194">No</span></span>  <br/> |<span data-ttu-id="0993b-195">통화를 받은 장치에 사용 되는 소프트웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-195">Software used on the device that received the call.</span></span>  <br/> |
|<span data-ttu-id="0993b-196">**시간이**</span><span class="sxs-lookup"><span data-stu-id="0993b-196">**Duration**</span></span> <br/> |<span data-ttu-id="0993b-197">아니요</span><span class="sxs-lookup"><span data-stu-id="0993b-197">No</span></span>  <br/> |<span data-ttu-id="0993b-198">통화 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-198">Length of time for the call.</span></span>  <br/> |
|<span data-ttu-id="0993b-199">**미디어 바이패스 경고 플래그**</span><span class="sxs-lookup"><span data-stu-id="0993b-199">**Media bypass warning flag**</span></span> <br/> |<span data-ttu-id="0993b-200">아니요</span><span class="sxs-lookup"><span data-stu-id="0993b-200">No</span></span>  <br/> |<span data-ttu-id="0993b-201">중재 서버를 우회 했을 때 발급 되는 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-201">Warning issued when the Mediation Server was bypassed.</span></span>  <br/> |
|<span data-ttu-id="0993b-202">**호출 수신자 OS**</span><span class="sxs-lookup"><span data-stu-id="0993b-202">**Callee OS**</span></span> <br/> |<span data-ttu-id="0993b-203">아니요</span><span class="sxs-lookup"><span data-stu-id="0993b-203">No</span></span>  <br/> |<span data-ttu-id="0993b-204">호출 된 사용자에 대 한 컴퓨터의 운영 체제입니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-204">Operating system of the computer for the user who was called.</span></span>  <br/> |
|<span data-ttu-id="0993b-205">**호출 수신자 CPU**</span><span class="sxs-lookup"><span data-stu-id="0993b-205">**Callee CPU**</span></span> <br/> |<span data-ttu-id="0993b-206">아니요</span><span class="sxs-lookup"><span data-stu-id="0993b-206">No</span></span>  <br/> |<span data-ttu-id="0993b-207">호출한 사용자의 컴퓨터에 설치 된 CPU입니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-207">CPU installed in the computer of the user who was called.</span></span>  <br/> |
|<span data-ttu-id="0993b-208">**호출 수신자 핵심 번호**</span><span class="sxs-lookup"><span data-stu-id="0993b-208">**Callee core number**</span></span> <br/> |<span data-ttu-id="0993b-209">아니요</span><span class="sxs-lookup"><span data-stu-id="0993b-209">No</span></span>  <br/> |<span data-ttu-id="0993b-210">호출 된 사용자가 사용 하는 컴퓨터의 프로세서 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-210">Processor number in the computer used by the person who was called.</span></span>  <br/> |
|<span data-ttu-id="0993b-211">**호출 수신자 CPU 속도**</span><span class="sxs-lookup"><span data-stu-id="0993b-211">**Callee CPU speed**</span></span> <br/> |<span data-ttu-id="0993b-212">아니요</span><span class="sxs-lookup"><span data-stu-id="0993b-212">No</span></span>  <br/> |<span data-ttu-id="0993b-213">호출 된 사용자가 사용 하는 컴퓨터의 CPU 클록 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-213">Clock speed of the CPU of the computer used by the person who was called.</span></span>  <br/> |
|<span data-ttu-id="0993b-214">**호출 수신자 CPU 가상화**</span><span class="sxs-lookup"><span data-stu-id="0993b-214">**Callee CPU virtualization**</span></span> <br/> |<span data-ttu-id="0993b-215">아니요</span><span class="sxs-lookup"><span data-stu-id="0993b-215">No</span></span>  <br/> |<span data-ttu-id="0993b-216">호출 된 사용자가 사용 하는 컴퓨터에서 가상화 (있는 경우)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0993b-216">Virtualization (if any) used on the computer used by the person who was called.</span></span>  <br/> |
   

