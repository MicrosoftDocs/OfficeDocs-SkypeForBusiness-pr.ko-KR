---
title: 비즈니스용 Skype 서버의 피어 투 피어 세션 세부 정보 보고서
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
description: '요약: 비즈니스용 Skype 서버의 피어 투 피어 세션 세부 정보 보고서에 대해 알아보세요.'
ms.openlocfilehash: 4c6b05e6e4e4110a43c21dbdbbc7f190ecae98ac
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817777"
---
# <a name="peer-to-peer-session-detail-report-in-skype-for-business-server"></a><span data-ttu-id="1a43b-103">비즈니스용 Skype 서버의 피어 투 피어 세션 세부 정보 보고서</span><span class="sxs-lookup"><span data-stu-id="1a43b-103">Peer-to-Peer Session Detail Report in Skype for Business Server</span></span>
 
<span data-ttu-id="1a43b-104">**요약:** 비즈니스용 Skype 서버의 피어 투 피어 세션 세부 정보 보고서에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="1a43b-104">**Summary:** Learn about the Peer-to-Peer Session Detail Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="1a43b-105">피어 투 피어 세션 정보 보고서는 피어 투 피어 세션에 대 한 자세한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-105">The Peer-to-Peer Session Detail Report returns detailed information about a peer-to-peer session.</span></span> <span data-ttu-id="1a43b-106">예를 들어 메신저 대화를 선택 하면 보고서에서 세션의 두 사용자 각각에 게 보낸 메시지 수를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-106">For example, if you select an instant messaging session, the report will tell you the number of messages sent by each of the two users in the session.</span></span>
  
## <a name="accessing-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="1a43b-107">피어 투 피어 세션 세부 정보 보고서에 액세스</span><span class="sxs-lookup"><span data-stu-id="1a43b-107">Accessing the Peer-to-Peer Session Detail Report</span></span>

<span data-ttu-id="1a43b-108">피어 투 피어 세션 세부 정보 보고서는 다음 보고서 중 하나에서 액세스할 수 있습니다 (모두 모니터링 보고서 홈 페이지에서 액세스할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="1a43b-108">The Peer-to-Peer Session Detail Report can be accessed from any of the following reports (all of which can be accessed from the Monitoring Reports home page):</span></span>
  
- <span data-ttu-id="1a43b-109">IP 전화 인벤토리 보고서</span><span class="sxs-lookup"><span data-stu-id="1a43b-109">IP Phone Inventory Report</span></span>
    
- <span data-ttu-id="1a43b-110">사용자 활동 보고서</span><span class="sxs-lookup"><span data-stu-id="1a43b-110">User Activity Report</span></span>
    
- <span data-ttu-id="1a43b-111">통화 허용 제어 보고서</span><span class="sxs-lookup"><span data-stu-id="1a43b-111">Call Admission Control Report</span></span>
    
- <span data-ttu-id="1a43b-112">오류 목록 보고서</span><span class="sxs-lookup"><span data-stu-id="1a43b-112">Failure List Report</span></span> 
    
<span data-ttu-id="1a43b-113">피어 투 피어 세션 세부 정보 보고서 내에서 진단 보고서 (세부 정보) 메트릭을 클릭 하 여 [비즈니스용 Skype 서버에서 진단 보고서](diagnostic-report.md) 에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-113">From within the Peer-to-Peer Session Detail Report you can access the [Diagnostic Report in Skype for Business Server](diagnostic-report.md) by clicking the Diagnostic Report (Details) metric.</span></span> <span data-ttu-id="1a43b-114">다음 두 가지 메트릭 중 하나를 클릭 하 여 상위 오류 보고서에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-114">You can also access the Top Failures Report by clicking either of these two metrics:</span></span>
  
- <span data-ttu-id="1a43b-115">응답</span><span class="sxs-lookup"><span data-stu-id="1a43b-115">Response</span></span>
    
- <span data-ttu-id="1a43b-116">진단 ID</span><span class="sxs-lookup"><span data-stu-id="1a43b-116">Diagnostic ID</span></span>
    
## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="1a43b-117">피어 투 피어 세션 세부 정보 보고서를 최대한 활용 하기</span><span class="sxs-lookup"><span data-stu-id="1a43b-117">Making the Best Use of the Peer-to-Peer session Detail Report</span></span>

<span data-ttu-id="1a43b-118">피어 투 피어 세션 세부 정보 보고서에는 다 수의 메트릭이 포함 되어 있으며,이 중 상당수는 시스템 관리자에 게 익숙하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-118">The Peer-to-Peer Session Detail Report includes a large number of metrics, many of which might not be familiar to system administrators.</span></span> <span data-ttu-id="1a43b-119">그러나 종종 미터법 레이블을 마우스로 눌러 해당 메트릭의 간략 한 설명을 제공 하는 도구 설명을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-119">Often-times, however, you can view a tooltip that offers a brief description of that metric simply by holding your mouse over the metric label.</span></span>
  
<span data-ttu-id="1a43b-120">지정 된 보고서에 표시 되는 실제 메트릭은 선택한 피어 투 피어 세션의 유형에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-120">Note that the actual metrics shown on a given report will depend on the type of peer-to-peer session you selected.</span></span> <span data-ttu-id="1a43b-121">오디오/비디오 세션은 인스턴트 메시지 세션 보다 다른 메트릭 집합을 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-121">An audio/video session will report a different set of metrics than an instant messaging session.</span></span>
  
<span data-ttu-id="1a43b-122">이러한 값에 대 한 설명을 얻으려면 응답 코드 및 진단 ID 메트릭스 위에 마우스를 놓고 있어야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-122">You can also hold your mouse over the Response code and Diagnostic ID metrics in order to obtain a description of those values:</span></span>
  
## <a name="filters"></a><span data-ttu-id="1a43b-123">필터가</span><span class="sxs-lookup"><span data-stu-id="1a43b-123">Filters</span></span>

<span data-ttu-id="1a43b-124">없음.</span><span class="sxs-lookup"><span data-stu-id="1a43b-124">None.</span></span> <span data-ttu-id="1a43b-125">피어 투 피어 세션 세부 정보 보고서를 필터링 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-125">You cannot filter the Peer-to-Peer Session Detail Report.</span></span>
  
## <a name="session-information-metrics"></a><span data-ttu-id="1a43b-126">세션 정보 메트릭</span><span class="sxs-lookup"><span data-stu-id="1a43b-126">Session Information Metrics</span></span>

<span data-ttu-id="1a43b-127">다음 표에는 각 세션에 대 한 피어 투 피어 세션 세부 정보 보고서에 제공 되는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-127">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session.</span></span>
  
<span data-ttu-id="1a43b-128">**세션 정보 메트릭**</span><span class="sxs-lookup"><span data-stu-id="1a43b-128">**Session Information Metrics**</span></span>

|<span data-ttu-id="1a43b-129">**이름**</span><span class="sxs-lookup"><span data-stu-id="1a43b-129">**Name**</span></span>|<span data-ttu-id="1a43b-130">**설명**</span><span class="sxs-lookup"><span data-stu-id="1a43b-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1a43b-131">**풀 FQDN**</span><span class="sxs-lookup"><span data-stu-id="1a43b-131">**Pool FQDN**</span></span> <br/> |<span data-ttu-id="1a43b-132">세션과 관련 된 등록자 풀 또는 Edge 서버의 FQDN (정규화 된 도메인 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-132">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server involved in the session.</span></span>  <br/> |
|<span data-ttu-id="1a43b-133">**초대 시간**</span><span class="sxs-lookup"><span data-stu-id="1a43b-133">**Invite time**</span></span> <br/> |<span data-ttu-id="1a43b-134">세션 초대를 원래 보낸 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-134">Date and time the session invitation was originally sent.</span></span>  <br/> |
|<span data-ttu-id="1a43b-135">**응답 시간**</span><span class="sxs-lookup"><span data-stu-id="1a43b-135">**Response time**</span></span> <br/> |<span data-ttu-id="1a43b-136">초대 수락을 받은 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-136">Date and time that the invitation acceptance was received.</span></span>  <br/> |
|<span data-ttu-id="1a43b-137">**사용자의**</span><span class="sxs-lookup"><span data-stu-id="1a43b-137">**From user**</span></span> <br/> |<span data-ttu-id="1a43b-138">세션을 시작한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-138">SIP address of the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="1a43b-139">**사용자 에이전트에서**</span><span class="sxs-lookup"><span data-stu-id="1a43b-139">**From user agent**</span></span> <br/> |<span data-ttu-id="1a43b-140">세션을 시작한 사용자의 끝점에 사용 되는 소프트웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-140">Software used by the endpoint of the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="1a43b-141">**사용자의 내부용입니다.**</span><span class="sxs-lookup"><span data-stu-id="1a43b-141">**Is From user internal**</span></span> <br/> |<span data-ttu-id="1a43b-142">세션을 시작한 사용자가 내부 네트워크에 로그온 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-142">Indicates whether the user who initiated the session was logged on to the internal network.</span></span>  <br/> |
|<span data-ttu-id="1a43b-143">**일반 전화기와 통합 된 사용자 인 경우**</span><span class="sxs-lookup"><span data-stu-id="1a43b-143">**Is From user integrated with desk phone**</span></span> <br/> |<span data-ttu-id="1a43b-144">세션을 시작한 사용자가 사용 하는 끝점이 해당 데스크톱 전화기와 통합 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-144">Indicates whether the endpoint used by the user who initiated the session is integrated with his or her desktop phone.</span></span>  <br/> |
|<span data-ttu-id="1a43b-145">**세션 우선 순위**</span><span class="sxs-lookup"><span data-stu-id="1a43b-145">**Session Priority**</span></span> <br/> |<span data-ttu-id="1a43b-146">세션에 할당 된 우선 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-146">Priority assigned to the session.</span></span> <span data-ttu-id="1a43b-147">유효한 우선 순위: 알 수 없음 비 긴급 크기로 받기 및 비상.</span><span class="sxs-lookup"><span data-stu-id="1a43b-147">Valid priorities are: Unknown; Non-Urgent; Normal; Urgent; and Emergency.</span></span>  <br/> |
|<span data-ttu-id="1a43b-148">**응답 코드**</span><span class="sxs-lookup"><span data-stu-id="1a43b-148">**Response code**</span></span> <br/> |<span data-ttu-id="1a43b-149">세션이 실패 했을 때 전송 된 SIP 응답 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-149">SIP response code sent when the session failed.</span></span>  <br/> |
|<span data-ttu-id="1a43b-150">**프론트 엔드**</span><span class="sxs-lookup"><span data-stu-id="1a43b-150">**Front end**</span></span> <br/> |<span data-ttu-id="1a43b-151">회의에 사용 되는 프런트 엔드 서버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-151">Name of the Front End Server used in the conference.</span></span>  <br/> |
|<span data-ttu-id="1a43b-152">**캡처 시간**</span><span class="sxs-lookup"><span data-stu-id="1a43b-152">**Capture time**</span></span> <br/> |<span data-ttu-id="1a43b-153">세션 정보가 기록 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-153">Date and time that the session information was recorded.</span></span>  <br/> |
|<span data-ttu-id="1a43b-154">**종료 시간**</span><span class="sxs-lookup"><span data-stu-id="1a43b-154">**End time**</span></span> <br/> |<span data-ttu-id="1a43b-155">세션이 종료 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-155">Date and time the session ended.</span></span>  <br/> |
|<span data-ttu-id="1a43b-156">**사용자에 게**</span><span class="sxs-lookup"><span data-stu-id="1a43b-156">**To user**</span></span> <br/> |<span data-ttu-id="1a43b-157">세션에 초대 된 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-157">SIP address of the user who was invited to the session.</span></span>  <br/> |
|<span data-ttu-id="1a43b-158">**사용자 에이전트에**</span><span class="sxs-lookup"><span data-stu-id="1a43b-158">**To user agent**</span></span> <br/> |<span data-ttu-id="1a43b-159">세션에 초대 된 사용자의 끝점에서 사용 하는 소프트웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-159">Software used by the endpoint of the user who was invited to the session.</span></span>  <br/> |
|<span data-ttu-id="1a43b-160">**사용자 내부용**</span><span class="sxs-lookup"><span data-stu-id="1a43b-160">**Is To user internal**</span></span> <br/> |<span data-ttu-id="1a43b-161">세션에 초대 된 사용자가 내부 네트워크에 로그온 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-161">Indicates whether the user who was invited to the session was logged on to the internal network.</span></span>  <br/> |
|<span data-ttu-id="1a43b-162">**일반 전화기와 사용자 통합**</span><span class="sxs-lookup"><span data-stu-id="1a43b-162">**Is To user integrated with desk phone**</span></span> <br/> |<span data-ttu-id="1a43b-163">세션에 초대 된 사용자가 사용 하는 끝점이 해당 데스크톱 전화기와 통합 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-163">Indicates whether the endpoint used by the user who was invited to the session is integrated with his or her desktop phone.</span></span>  <br/> |
|<span data-ttu-id="1a43b-164">**다시 시도 세션**</span><span class="sxs-lookup"><span data-stu-id="1a43b-164">**Is retried session**</span></span> <br/> |<span data-ttu-id="1a43b-165">세션이 이전에 실패 한 세션을 다시 시도 하려고 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-165">Indicates whether the session is an attempt to retry a session that previously failed.</span></span>  <br/> |
|<span data-ttu-id="1a43b-166">**진단 ID**</span><span class="sxs-lookup"><span data-stu-id="1a43b-166">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="1a43b-167">오류 문제 해결에 유용한 정보를 자주 제공 하는 SIP 메시지에 첨부 된 고유 식별자 (ms-진단 헤더 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-167">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span> <span data-ttu-id="1a43b-168">ID 번호 위에 마우스를 놓으면 해당 ID에 대 한 추가 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-168">Hold the mouse over the ID number to view additional information about that ID.</span></span>  <br/> |
   
## <a name="metrics-for-modalities"></a><span data-ttu-id="1a43b-169">형식을에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="1a43b-169">Metrics for Modalities</span></span>

<span data-ttu-id="1a43b-170">다음 표에는 각 세션에 대 한 피어 투 피어 세션 세부 정보 보고서에 제공 되는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-170">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session modality.</span></span>
  
<span data-ttu-id="1a43b-171">**형식을에 대 한 메트릭**</span><span class="sxs-lookup"><span data-stu-id="1a43b-171">**Metrics for Modalities**</span></span>

|<span data-ttu-id="1a43b-172">**이름**</span><span class="sxs-lookup"><span data-stu-id="1a43b-172">**Name**</span></span>|<span data-ttu-id="1a43b-173">**이 항목을 정렬할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="1a43b-173">**Can you sort on this item?**</span></span>|<span data-ttu-id="1a43b-174">**설명**</span><span class="sxs-lookup"><span data-stu-id="1a43b-174">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1a43b-175">**형식을**</span><span class="sxs-lookup"><span data-stu-id="1a43b-175">**Modalities**</span></span> <br/> |<span data-ttu-id="1a43b-176">아니요</span><span class="sxs-lookup"><span data-stu-id="1a43b-176">No</span></span>  <br/> |<span data-ttu-id="1a43b-177">세션에 사용 되는 형식을.</span><span class="sxs-lookup"><span data-stu-id="1a43b-177">Modalities used in the session.</span></span> <span data-ttu-id="1a43b-178">예를 들어 인스턴트 메시지 (IM) 또는 파일 전송</span><span class="sxs-lookup"><span data-stu-id="1a43b-178">For example, instant messaging (IM) or file transfer.</span></span>  <br/> |
|<span data-ttu-id="1a43b-179">**사용자 메시지**</span><span class="sxs-lookup"><span data-stu-id="1a43b-179">**From user messages**</span></span> <br/> |<span data-ttu-id="1a43b-180">아니요</span><span class="sxs-lookup"><span data-stu-id="1a43b-180">No</span></span>  <br/> |<span data-ttu-id="1a43b-181">세션을 시작한 사용자가 보낸 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-181">Number of messages sent by the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="1a43b-182">**사용자 메시지**</span><span class="sxs-lookup"><span data-stu-id="1a43b-182">**To user messages**</span></span> <br/> |<span data-ttu-id="1a43b-183">아니요</span><span class="sxs-lookup"><span data-stu-id="1a43b-183">No</span></span>  <br/> |<span data-ttu-id="1a43b-184">세션에 참가 하도록 초대 된 사용자가 보낸 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-184">Number of messages sent by the user who was invited to join the session.</span></span>  <br/> |
   
## <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="1a43b-185">진단 보고서에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="1a43b-185">Metrics for Diagnostic Reports</span></span>

<span data-ttu-id="1a43b-186">다음 표에는 각 진단 보고서에 대 한 피어 투 피어 세션 세부 정보 보고서에 제공 되는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-186">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each diagnostic report.</span></span>
  
<span data-ttu-id="1a43b-187">**진단 보고서에 대 한 메트릭**</span><span class="sxs-lookup"><span data-stu-id="1a43b-187">**Metrics for Diagnostic Reports**</span></span>

|<span data-ttu-id="1a43b-188">**이름**</span><span class="sxs-lookup"><span data-stu-id="1a43b-188">**Name**</span></span>|<span data-ttu-id="1a43b-189">**이 항목을 정렬할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="1a43b-189">**Can you sort on this item?**</span></span>|<span data-ttu-id="1a43b-190">**설명**</span><span class="sxs-lookup"><span data-stu-id="1a43b-190">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1a43b-191">**도**</span><span class="sxs-lookup"><span data-stu-id="1a43b-191">**Detail**</span></span> <br/> |<span data-ttu-id="1a43b-192">아니요</span><span class="sxs-lookup"><span data-stu-id="1a43b-192">No</span></span>  <br/> |<span data-ttu-id="1a43b-193">이 항목을 클릭 하면 보고서에는 세션에 대 한 진단 보고서가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-193">When you click this item, the report shows the Diagnostic Report for the session.</span></span>  <br/> |
|<span data-ttu-id="1a43b-194">**보고서 시간**</span><span class="sxs-lookup"><span data-stu-id="1a43b-194">**Report time**</span></span> <br/> |<span data-ttu-id="1a43b-195">아니요</span><span class="sxs-lookup"><span data-stu-id="1a43b-195">No</span></span>  <br/> |<span data-ttu-id="1a43b-196">보고서가 기록 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-196">Date and time the report was recorded.</span></span>  <br/> |
|<span data-ttu-id="1a43b-197">**요청당**</span><span class="sxs-lookup"><span data-stu-id="1a43b-197">**Request**</span></span> <br/> |<span data-ttu-id="1a43b-198">아니요</span><span class="sxs-lookup"><span data-stu-id="1a43b-198">No</span></span>  <br/> |<span data-ttu-id="1a43b-199">SIP 요청 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-199">SIP request type.</span></span> <span data-ttu-id="1a43b-200">예를 들어 초대 또는 BYE.</span><span class="sxs-lookup"><span data-stu-id="1a43b-200">For example, INVITE or BYE.</span></span>  <br/> |
|<span data-ttu-id="1a43b-201">**진단 ID**</span><span class="sxs-lookup"><span data-stu-id="1a43b-201">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="1a43b-202">아니요</span><span class="sxs-lookup"><span data-stu-id="1a43b-202">No</span></span>  <br/> |<span data-ttu-id="1a43b-203">오류 문제 해결에 유용한 정보를 자주 제공 하는 SIP 메시지에 첨부 된 고유 식별자 (ms-진단 헤더 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-203">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="1a43b-204">**콘텐츠 형식**</span><span class="sxs-lookup"><span data-stu-id="1a43b-204">**Content type**</span></span> <br/> |<span data-ttu-id="1a43b-205">아니요</span><span class="sxs-lookup"><span data-stu-id="1a43b-205">No</span></span>  <br/> |<span data-ttu-id="1a43b-206">회의에 사용 되는 미디어 콘텐츠의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-206">Type of media content used in the conference.</span></span> <span data-ttu-id="1a43b-207">예를 들어 공용 콘텐츠 형식은 Application/sdp입니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-207">For example, a common content type is Application/sdp.</span></span> <span data-ttu-id="1a43b-208">SDP (세션 설명 프로토콜)는 세션 공지 사항, 세션 초대 및 다른 형식의 멀티미디어 세션 초기화에 사용 되는 표준 인터넷 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-208">Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span>  <br/> |
|<span data-ttu-id="1a43b-209">**보고 한 사람**</span><span class="sxs-lookup"><span data-stu-id="1a43b-209">**Reported by**</span></span> <br/> |<span data-ttu-id="1a43b-210">아니요</span><span class="sxs-lookup"><span data-stu-id="1a43b-210">No</span></span>  <br/> |<span data-ttu-id="1a43b-211">컴퓨터 (즉, 클라이언트 또는 서버)에서 문제를 보고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1a43b-211">Computer (that is, client or server) that reported the problem.</span></span>  <br/> |
   

