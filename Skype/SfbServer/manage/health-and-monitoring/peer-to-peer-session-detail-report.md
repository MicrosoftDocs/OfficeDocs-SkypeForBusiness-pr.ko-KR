---
title: 비즈니스용 Skype 서버의 피어 투 피어 세션 세부 정보 보고서
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
ms.assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
description: '요약: 비즈니스용 Skype 서버의 피어 투 피어 세션 세부 정보 보고서에 대해 자세히 알아보습니다.'
ms.openlocfilehash: 4dfa2b87b1fbba72282b52fa2ca58ca0f1e70630
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816768"
---
# <a name="peer-to-peer-session-detail-report-in-skype-for-business-server"></a><span data-ttu-id="2d9aa-103">비즈니스용 Skype 서버의 피어 투 피어 세션 세부 정보 보고서</span><span class="sxs-lookup"><span data-stu-id="2d9aa-103">Peer-to-Peer Session Detail Report in Skype for Business Server</span></span>
 
<span data-ttu-id="2d9aa-104">**요약:** 비즈니스용 Skype 서버의 피어 투 피어 세션 세부 정보 보고서에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-104">**Summary:** Learn about the Peer-to-Peer Session Detail Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="2d9aa-105">피어 투 피어 세션 세부 정보 보고서는 피어 투 피어 세션에 대한 자세한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-105">The Peer-to-Peer Session Detail Report returns detailed information about a peer-to-peer session.</span></span> <span data-ttu-id="2d9aa-106">예를 들어 인스턴트 메시징 세션을 선택하면 보고서에 세션의 두 사용자가 각각 보낸 메시지 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-106">For example, if you select an instant messaging session, the report will tell you the number of messages sent by each of the two users in the session.</span></span>
  
## <a name="accessing-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="2d9aa-107">피어 투 피어 세션 세부 정보 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="2d9aa-107">Accessing the Peer-to-Peer Session Detail Report</span></span>

<span data-ttu-id="2d9aa-108">피어 투 피어 세션 세부 정보 보고서는 다음 보고서(모니터링 보고서 홈 페이지에서 모두 액세스할 수 있는 보고서)에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-108">The Peer-to-Peer Session Detail Report can be accessed from any of the following reports (all of which can be accessed from the Monitoring Reports home page):</span></span>
  
- <span data-ttu-id="2d9aa-109">IP 전화 인벤토리 보고서</span><span class="sxs-lookup"><span data-stu-id="2d9aa-109">IP Phone Inventory Report</span></span>
    
- <span data-ttu-id="2d9aa-110">사용자 작업 보고서</span><span class="sxs-lookup"><span data-stu-id="2d9aa-110">User Activity Report</span></span>
    
- <span data-ttu-id="2d9aa-111">통화 허용 컨트롤 보고서</span><span class="sxs-lookup"><span data-stu-id="2d9aa-111">Call Admission Control Report</span></span>
    
- <span data-ttu-id="2d9aa-112">오류 목록 보고서</span><span class="sxs-lookup"><span data-stu-id="2d9aa-112">Failure List Report</span></span> 
    
<span data-ttu-id="2d9aa-113">피어 투 피어 세션 세부 정보 보고서 내에서 진단 보고서(세부 정보) 메트릭을 클릭하여 비즈니스용 [Skype](diagnostic-report.md) 서버의 진단 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-113">From within the Peer-to-Peer Session Detail Report you can access the [Diagnostic Report in Skype for Business Server](diagnostic-report.md) by clicking the Diagnostic Report (Details) metric.</span></span> <span data-ttu-id="2d9aa-114">다음 두 메트릭 중 하나를 클릭하여 Top Failures Report에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-114">You can also access the Top Failures Report by clicking either of these two metrics:</span></span>
  
- <span data-ttu-id="2d9aa-115">응답</span><span class="sxs-lookup"><span data-stu-id="2d9aa-115">Response</span></span>
    
- <span data-ttu-id="2d9aa-116">진단 ID</span><span class="sxs-lookup"><span data-stu-id="2d9aa-116">Diagnostic ID</span></span>
    
## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="2d9aa-117">피어 투 피어 세션 세부 정보 보고서를 가장 잘 활용</span><span class="sxs-lookup"><span data-stu-id="2d9aa-117">Making the Best Use of the Peer-to-Peer session Detail Report</span></span>

<span data-ttu-id="2d9aa-118">피어 투 피어 세션 세부 정보 보고서에는 많은 메트릭이 포함되어 있습니다. 이 중 다수는 시스템 관리자에게 익숙하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-118">The Peer-to-Peer Session Detail Report includes a large number of metrics, many of which might not be familiar to system administrators.</span></span> <span data-ttu-id="2d9aa-119">그러나 종종 메트릭 레이블 위에 마우스를 놓기만 하여 해당 메트릭에 대한 간단한 설명을 제공하는 도구 설명을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-119">Often-times, however, you can view a tooltip that offers a brief description of that metric simply by holding your mouse over the metric label.</span></span>
  
<span data-ttu-id="2d9aa-120">특정 보고서에 표시되는 실제 메트릭은 선택한 피어 투 피어 세션의 유형에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-120">Note that the actual metrics shown on a given report will depend on the type of peer-to-peer session you selected.</span></span> <span data-ttu-id="2d9aa-121">오디오/비디오 세션은 인스턴트 메시징 세션과 다른 메트릭 집합을 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-121">An audio/video session will report a different set of metrics than an instant messaging session.</span></span>
  
<span data-ttu-id="2d9aa-122">이러한 값에 대한 설명을 얻기 위해 응답 코드 및 진단 ID 메트릭 위에 마우스를 놓을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-122">You can also hold your mouse over the Response code and Diagnostic ID metrics in order to obtain a description of those values:</span></span>
  
## <a name="filters"></a><span data-ttu-id="2d9aa-123">필터</span><span class="sxs-lookup"><span data-stu-id="2d9aa-123">Filters</span></span>

<span data-ttu-id="2d9aa-124">없음</span><span class="sxs-lookup"><span data-stu-id="2d9aa-124">None.</span></span> <span data-ttu-id="2d9aa-125">피어 투 피어 세션 세부 정보 보고서는 필터링할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-125">You cannot filter the Peer-to-Peer Session Detail Report.</span></span>
  
## <a name="session-information-metrics"></a><span data-ttu-id="2d9aa-126">세션 정보 메트릭</span><span class="sxs-lookup"><span data-stu-id="2d9aa-126">Session Information Metrics</span></span>

<span data-ttu-id="2d9aa-127">다음 표에는 각 세션에 대한 피어 투 피어 세션 세부 정보 보고서에 제공된 정보가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-127">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session.</span></span>
  
<span data-ttu-id="2d9aa-128">**세션 정보 메트릭**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-128">**Session Information Metrics**</span></span>

|<span data-ttu-id="2d9aa-129">**이름**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-129">**Name**</span></span>|<span data-ttu-id="2d9aa-130">**설명**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2d9aa-131">**풀 FQDN**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-131">**Pool FQDN**</span></span> <br/> |<span data-ttu-id="2d9aa-132">세션에 관련된 등록자 풀 또는 에지 서버의 FQDN(FQDN)입니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-132">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server involved in the session.</span></span>  <br/> |
|<span data-ttu-id="2d9aa-133">**초대 시간**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-133">**Invite time**</span></span> <br/> |<span data-ttu-id="2d9aa-134">세션 초대가 처음 전송된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-134">Date and time the session invitation was originally sent.</span></span>  <br/> |
|<span data-ttu-id="2d9aa-135">**응답 시간**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-135">**Response time**</span></span> <br/> |<span data-ttu-id="2d9aa-136">초대 수락을 받은 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-136">Date and time that the invitation acceptance was received.</span></span>  <br/> |
|<span data-ttu-id="2d9aa-137">**시작 사용자**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-137">**From user**</span></span> <br/> |<span data-ttu-id="2d9aa-138">세션을 시작한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-138">SIP address of the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="2d9aa-139">**출처 사용자 에이전트**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-139">**From user agent**</span></span> <br/> |<span data-ttu-id="2d9aa-140">세션을 시작한 사용자의 끝점에 사용된 소프트웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-140">Software used by the endpoint of the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="2d9aa-141">**Is From user internal**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-141">**Is From user internal**</span></span> <br/> |<span data-ttu-id="2d9aa-142">세션을 시작한 사용자가 내부 네트워크에 로그온되어 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-142">Indicates whether the user who initiated the session was logged on to the internal network.</span></span>  <br/> |
|<span data-ttu-id="2d9aa-143">**사용자가 책상 전화와 통합된 사용자인 경우**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-143">**Is From user integrated with desk phone**</span></span> <br/> |<span data-ttu-id="2d9aa-144">세션을 시작한 사용자가 사용한 끝점이 자신의 데스크톱 전화와 통합되어 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-144">Indicates whether the endpoint used by the user who initiated the session is integrated with his or her desktop phone.</span></span>  <br/> |
|<span data-ttu-id="2d9aa-145">**세션 우선 순위**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-145">**Session Priority**</span></span> <br/> |<span data-ttu-id="2d9aa-146">세션에 할당된 우선 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-146">Priority assigned to the session.</span></span> <span data-ttu-id="2d9aa-147">유효한 우선 순위는 알 수 없음입니다. 긴급하지 않은; 보통; 긴급한 경우 및 긴급.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-147">Valid priorities are: Unknown; Non-Urgent; Normal; Urgent; and Emergency.</span></span>  <br/> |
|<span data-ttu-id="2d9aa-148">**응답 코드**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-148">**Response code**</span></span> <br/> |<span data-ttu-id="2d9aa-149">세션이 실패했을 때 전송된 SIP 응답 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-149">SIP response code sent when the session failed.</span></span>  <br/> |
|<span data-ttu-id="2d9aa-150">**프런트 엔드**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-150">**Front end**</span></span> <br/> |<span data-ttu-id="2d9aa-151">회의에 사용된 프런트 엔드 서버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-151">Name of the Front End Server used in the conference.</span></span>  <br/> |
|<span data-ttu-id="2d9aa-152">**캡처 시간**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-152">**Capture time**</span></span> <br/> |<span data-ttu-id="2d9aa-153">세션 정보가 기록된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-153">Date and time that the session information was recorded.</span></span>  <br/> |
|<span data-ttu-id="2d9aa-154">**종료 시간**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-154">**End time**</span></span> <br/> |<span data-ttu-id="2d9aa-155">세션이 종료된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-155">Date and time the session ended.</span></span>  <br/> |
|<span data-ttu-id="2d9aa-156">**대상 사용자**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-156">**To user**</span></span> <br/> |<span data-ttu-id="2d9aa-157">세션에 초대된 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-157">SIP address of the user who was invited to the session.</span></span>  <br/> |
|<span data-ttu-id="2d9aa-158">**사용자 에이전트에게**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-158">**To user agent**</span></span> <br/> |<span data-ttu-id="2d9aa-159">세션에 초대된 사용자의 끝점에서 사용하는 소프트웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-159">Software used by the endpoint of the user who was invited to the session.</span></span>  <br/> |
|<span data-ttu-id="2d9aa-160">**사용자 내부에 대한 것**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-160">**Is To user internal**</span></span> <br/> |<span data-ttu-id="2d9aa-161">세션에 초대된 사용자가 내부 네트워크에 로그온되어 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-161">Indicates whether the user who was invited to the session was logged on to the internal network.</span></span>  <br/> |
|<span data-ttu-id="2d9aa-162">**사용자가 책상 전화와 통합된 경우**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-162">**Is To user integrated with desk phone**</span></span> <br/> |<span data-ttu-id="2d9aa-163">세션에 초대된 사용자가 사용한 끝점이 자신의 데스크톱 전화와 통합되어 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-163">Indicates whether the endpoint used by the user who was invited to the session is integrated with his or her desktop phone.</span></span>  <br/> |
|<span data-ttu-id="2d9aa-164">**세션을 다시 시작한 경우**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-164">**Is retried session**</span></span> <br/> |<span data-ttu-id="2d9aa-165">세션이 이전에 실패한 세션을 다시 시도하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-165">Indicates whether the session is an attempt to retry a session that previously failed.</span></span>  <br/> |
|<span data-ttu-id="2d9aa-166">**진단 ID**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-166">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="2d9aa-167">오류 문제를 해결할 때 종종 유용한 정보를 제공하는 SIP 메시지에 연결된 고유 식별자(ms-diagnostics 헤더 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-167">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span> <span data-ttu-id="2d9aa-168">ID 번호 위에 마우스를 놓고 해당 ID에 대한 추가 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-168">Hold the mouse over the ID number to view additional information about that ID.</span></span>  <br/> |
   
## <a name="metrics-for-modalities"></a><span data-ttu-id="2d9aa-169">Modalities에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="2d9aa-169">Metrics for Modalities</span></span>

<span data-ttu-id="2d9aa-170">다음 표에는 각 세션의 성에 대한 피어 투 피어 세션 세부 정보 보고서에 제공된 정보가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-170">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session modality.</span></span>
  
<span data-ttu-id="2d9aa-171">**Modalities에 대한 메트릭**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-171">**Metrics for Modalities**</span></span>

|<span data-ttu-id="2d9aa-172">**이름**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-172">**Name**</span></span>|<span data-ttu-id="2d9aa-173">**이 항목에 대한 정렬 가능 여부**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-173">**Can you sort on this item?**</span></span>|<span data-ttu-id="2d9aa-174">**설명**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-174">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2d9aa-175">**Modalities**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-175">**Modalities**</span></span> <br/> |<span data-ttu-id="2d9aa-176">아니요</span><span class="sxs-lookup"><span data-stu-id="2d9aa-176">No</span></span>  <br/> |<span data-ttu-id="2d9aa-177">세션에 사용된 모달입니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-177">Modalities used in the session.</span></span> <span data-ttu-id="2d9aa-178">예를 들어 IM(인스턴트 메시징) 또는 파일 전송이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-178">For example, instant messaging (IM) or file transfer.</span></span>  <br/> |
|<span data-ttu-id="2d9aa-179">**보낸 사용자 메시지**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-179">**From user messages**</span></span> <br/> |<span data-ttu-id="2d9aa-180">아니요</span><span class="sxs-lookup"><span data-stu-id="2d9aa-180">No</span></span>  <br/> |<span data-ttu-id="2d9aa-181">세션을 시작한 사용자가 보낸 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-181">Number of messages sent by the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="2d9aa-182">**사용자 메시지**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-182">**To user messages**</span></span> <br/> |<span data-ttu-id="2d9aa-183">아니요</span><span class="sxs-lookup"><span data-stu-id="2d9aa-183">No</span></span>  <br/> |<span data-ttu-id="2d9aa-184">세션에 참가하도록 초대된 사용자가 보낸 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-184">Number of messages sent by the user who was invited to join the session.</span></span>  <br/> |
   
## <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="2d9aa-185">진단 보고서에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="2d9aa-185">Metrics for Diagnostic Reports</span></span>

<span data-ttu-id="2d9aa-186">다음 표에서는 각 진단 보고서에 대해 피어 투 피어 세션 세부 정보 보고서에 제공된 정보를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-186">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each diagnostic report.</span></span>
  
<span data-ttu-id="2d9aa-187">**진단 보고서에 대한 메트릭**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-187">**Metrics for Diagnostic Reports**</span></span>

|<span data-ttu-id="2d9aa-188">**이름**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-188">**Name**</span></span>|<span data-ttu-id="2d9aa-189">**이 항목에 대한 정렬 가능 여부**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-189">**Can you sort on this item?**</span></span>|<span data-ttu-id="2d9aa-190">**설명**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-190">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2d9aa-191">**자세한 정보**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-191">**Detail**</span></span> <br/> |<span data-ttu-id="2d9aa-192">아니요</span><span class="sxs-lookup"><span data-stu-id="2d9aa-192">No</span></span>  <br/> |<span data-ttu-id="2d9aa-193">이 항목을 클릭하면 보고서에 세션의 진단 보고서가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-193">When you click this item, the report shows the Diagnostic Report for the session.</span></span>  <br/> |
|<span data-ttu-id="2d9aa-194">**보고 시간**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-194">**Report time**</span></span> <br/> |<span data-ttu-id="2d9aa-195">아니요</span><span class="sxs-lookup"><span data-stu-id="2d9aa-195">No</span></span>  <br/> |<span data-ttu-id="2d9aa-196">보고서가 기록된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-196">Date and time the report was recorded.</span></span>  <br/> |
|<span data-ttu-id="2d9aa-197">**요청**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-197">**Request**</span></span> <br/> |<span data-ttu-id="2d9aa-198">아니요</span><span class="sxs-lookup"><span data-stu-id="2d9aa-198">No</span></span>  <br/> |<span data-ttu-id="2d9aa-199">SIP 요청 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-199">SIP request type.</span></span> <span data-ttu-id="2d9aa-200">예: INVITE 또는 BYE</span><span class="sxs-lookup"><span data-stu-id="2d9aa-200">For example, INVITE or BYE.</span></span>  <br/> |
|<span data-ttu-id="2d9aa-201">**진단 ID**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-201">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="2d9aa-202">아니요</span><span class="sxs-lookup"><span data-stu-id="2d9aa-202">No</span></span>  <br/> |<span data-ttu-id="2d9aa-203">오류 문제를 해결할 때 종종 유용한 정보를 제공하는 SIP 메시지에 연결된 고유 식별자(ms-diagnostics 헤더 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-203">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="2d9aa-204">**콘텐츠 형식**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-204">**Content type**</span></span> <br/> |<span data-ttu-id="2d9aa-205">아니요</span><span class="sxs-lookup"><span data-stu-id="2d9aa-205">No</span></span>  <br/> |<span data-ttu-id="2d9aa-206">회의에 사용되는 미디어 콘텐츠의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-206">Type of media content used in the conference.</span></span> <span data-ttu-id="2d9aa-207">예를 들어 공통 콘텐츠 형식은 Application/sdp입니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-207">For example, a common content type is Application/sdp.</span></span> <span data-ttu-id="2d9aa-208">SDP(Session Description Protocol)는 세션 알림, 세션 초대 및 멀티 미디어 세션 초대의 다른 형식에 사용된 표준 인터넷 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-208">Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span>  <br/> |
|<span data-ttu-id="2d9aa-209">**보고한**</span><span class="sxs-lookup"><span data-stu-id="2d9aa-209">**Reported by**</span></span> <br/> |<span data-ttu-id="2d9aa-210">아니요</span><span class="sxs-lookup"><span data-stu-id="2d9aa-210">No</span></span>  <br/> |<span data-ttu-id="2d9aa-211">문제를 보고한 컴퓨터(클라이언트 또는 서버)입니다.</span><span class="sxs-lookup"><span data-stu-id="2d9aa-211">Computer (that is, client or server) that reported the problem.</span></span>  <br/> |
   

