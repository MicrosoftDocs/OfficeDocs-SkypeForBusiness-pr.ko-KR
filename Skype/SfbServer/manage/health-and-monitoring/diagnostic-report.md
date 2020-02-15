---
title: 비즈니스용 Skype 서버의 진단 보고서
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
ms.assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
description: '요약: 비즈니스용 Skype 서버의 진단 보고서에 대해 알아봅니다.'
ms.openlocfilehash: f1a8d9a0c027019708f2be75fec14634197c4e2b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041995"
---
# <a name="diagnostic-report-in-skype-for-business-server"></a><span data-ttu-id="f4682-103">비즈니스용 Skype 서버의 진단 보고서</span><span class="sxs-lookup"><span data-stu-id="f4682-103">Diagnostic Report in Skype for Business Server</span></span>
 
<span data-ttu-id="f4682-104">**요약:** 비즈니스용 Skype 서버의 진단 보고서에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="f4682-104">**Summary:** Learn about the Diagnostic Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="f4682-105">진단 보고서에서는 실패한 세션에 대한 진단 및 문제 해결 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f4682-105">The Diagnostic Report provides diagnostic and troubleshooting information for a failed session.</span></span> <span data-ttu-id="f4682-106">이 정보에는 세션이 실패할 때 보고된 진단 ID와 진단 헤더가 모두 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4682-106">This information includes both the Diagnostic ID and the Diagnostic header that were reported when the session failed.</span></span> <span data-ttu-id="f4682-107">진단 ID는 SIP 메시지에 연결된 고유 식별자(ms-diagnostics 헤더 형식)이며, 진단 헤더는 진단 ID에 대해 함께 표시할 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f4682-107">The Diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) that gets attached to a SIP message, while the Diagnostic header provides an accompanying description for the Diagnostic ID.</span></span> <span data-ttu-id="f4682-108">또한 이 보고서에는 보고 구성 요소에서 인식된 유용한 문제 해결 정보가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4682-108">The report might also contain valuable troubleshooting details that are known by the reporting component.</span></span> <span data-ttu-id="f4682-109">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f4682-109">For example:</span></span>
  
- <span data-ttu-id="f4682-p102">오류를 일으킨 PSTN 게이트웨이에서 제공되는 이유 코드. PSTN 네트워크에서 발신 전화에 실패하면 ISUP(ISDN User Part) 이유 코드가 자동으로 생성됩니다. 예를 들어 PSTN 게이트웨이에서 전화를 완료하는 데 사용 가능한 회로 또는 채널이 없음을 나타내는 이유 코드 34를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4682-p102">The cause code provided by the PSTN gateway that generated the failure. When an outgoing call fails on the PSTN network, an ISDN User Part (ISUP) cause code is automatically generated. For example, a PSTN gateway might send cause code 34 to indicate that no circuit or channel was available for completing the call.</span></span>
    
- <span data-ttu-id="f4682-113">연결 오류를 해결하기 위한 피어 FQDN, 포트 및 Winsock 오류</span><span class="sxs-lookup"><span data-stu-id="f4682-113">Peer FQDN, port, and Winsock errors for connectivity failures.</span></span>
    
- <span data-ttu-id="f4682-p103">DNS 확인 오류를 해결하기 위한 조회 대상 이름. DNS 확인은 클라이언트가 네임 서버에 연결하여 지정된 장치 이름에 해당하는 IP 주소를 요청할 때마다 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4682-p103">Names being looked up for DNS resolution failures. DNS resolution takes place any time a client contacts a name server and requests the IP address that corresponds to specified device name.</span></span>
    
## <a name="accessing-the-diagnostic-report"></a><span data-ttu-id="f4682-116">진단 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="f4682-116">Accessing the Diagnostic Report</span></span>

<span data-ttu-id="f4682-117">[비즈니스용 Skype 서버의 피어 투 피어 세션 정보 보고서](peer-to-peer-session-detail-report.md) 또는 전화 회의 정보 보고서에서 진단 보고서 (세부 정보) 메트릭을 클릭 하 여 진단 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4682-117">The Diagnostic Report can be accessed by clicking the Diagnostic Report (Detail) metric on either the [Peer-to-Peer Session Detail Report in Skype for Business Server](peer-to-peer-session-detail-report.md) or the Conference Detail Report.</span></span>
  
## <a name="filters"></a><span data-ttu-id="f4682-118">필터</span><span class="sxs-lookup"><span data-stu-id="f4682-118">Filters</span></span>

<span data-ttu-id="f4682-p104">없음. 진단 보고서는 필터링할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f4682-p104">None. You cannot filter the Diagnostic Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="f4682-121">선별한</span><span class="sxs-lookup"><span data-stu-id="f4682-121">Metrics</span></span>

<span data-ttu-id="f4682-122">다음 표에서는 각 세션에 대해 진단 보고서에 제공된 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f4682-122">The following table lists the information provided in the Diagnostic Report for each session.</span></span>
  
<span data-ttu-id="f4682-123">**진단 보고서 메트릭**</span><span class="sxs-lookup"><span data-stu-id="f4682-123">**Diagnostic Report Metrics**</span></span>

|<span data-ttu-id="f4682-124">**이름**</span><span class="sxs-lookup"><span data-stu-id="f4682-124">**Name**</span></span>|<span data-ttu-id="f4682-125">**이 항목에 대한 정렬 가능 여부**</span><span class="sxs-lookup"><span data-stu-id="f4682-125">**Can you sort on this item?**</span></span>|<span data-ttu-id="f4682-126">**설명**</span><span class="sxs-lookup"><span data-stu-id="f4682-126">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f4682-127">**보고 시간**</span><span class="sxs-lookup"><span data-stu-id="f4682-127">**Report time**</span></span> <br/> |<span data-ttu-id="f4682-128">아니요</span><span class="sxs-lookup"><span data-stu-id="f4682-128">No</span></span>  <br/> |<span data-ttu-id="f4682-129">보고서가 기록된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="f4682-129">Date and time that the report was recorded.</span></span>  <br/> |
|<span data-ttu-id="f4682-130">**응답 코드**</span><span class="sxs-lookup"><span data-stu-id="f4682-130">**Response code**</span></span> <br/> |<span data-ttu-id="f4682-131">아니요</span><span class="sxs-lookup"><span data-stu-id="f4682-131">No</span></span>  <br/> |<span data-ttu-id="f4682-132">세션이 실패했을 때 전송된 SIP 응답 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="f4682-132">SIP response code sent when the session failed.</span></span>  <br/> |
|<span data-ttu-id="f4682-133">**요청 유형**</span><span class="sxs-lookup"><span data-stu-id="f4682-133">**Request type**</span></span> <br/> |<span data-ttu-id="f4682-134">아니요</span><span class="sxs-lookup"><span data-stu-id="f4682-134">No</span></span>  <br/> |<span data-ttu-id="f4682-p105">실패한 SIP 요청 유형입니다. 예: INVITE, BYE 또는 SERVICE</span><span class="sxs-lookup"><span data-stu-id="f4682-p105">SIP request type that failed. For example, INVITE, BYE, or SERVICE.</span></span>  <br/> |
|<span data-ttu-id="f4682-137">**원본**</span><span class="sxs-lookup"><span data-stu-id="f4682-137">**Source**</span></span> <br/> |<span data-ttu-id="f4682-138">아니요</span><span class="sxs-lookup"><span data-stu-id="f4682-138">No</span></span>  <br/> |<span data-ttu-id="f4682-139">오류 원본입니다.</span><span class="sxs-lookup"><span data-stu-id="f4682-139">Source of the error.</span></span>  <br/> |
|<span data-ttu-id="f4682-140">**보낸 사용자 URI**</span><span class="sxs-lookup"><span data-stu-id="f4682-140">**From user URI**</span></span> <br/> |<span data-ttu-id="f4682-141">아니요</span><span class="sxs-lookup"><span data-stu-id="f4682-141">No</span></span>  <br/> |<span data-ttu-id="f4682-142">세션을 시작한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="f4682-142">SIP address of the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="f4682-143">**출처 사용자 에이전트**</span><span class="sxs-lookup"><span data-stu-id="f4682-143">**From user agent**</span></span> <br/> |<span data-ttu-id="f4682-144">아니요</span><span class="sxs-lookup"><span data-stu-id="f4682-144">No</span></span>  <br/> |<span data-ttu-id="f4682-145">세션을 시작한 사용자의 끝점에 사용된 소프트웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="f4682-145">Software used by the endpoint of the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="f4682-146">**진단 ID**</span><span class="sxs-lookup"><span data-stu-id="f4682-146">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="f4682-147">아니요</span><span class="sxs-lookup"><span data-stu-id="f4682-147">No</span></span>  <br/> |<span data-ttu-id="f4682-148">오류 문제를 해결할 때 종종 유용한 정보를 제공하는 SIP 메시지에 연결된 고유 식별자(ms-diagnostics 헤더 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="f4682-148">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="f4682-149">**콘텐츠 형식**</span><span class="sxs-lookup"><span data-stu-id="f4682-149">**Content type**</span></span> <br/> |<span data-ttu-id="f4682-150">아니요</span><span class="sxs-lookup"><span data-stu-id="f4682-150">No</span></span>  <br/> |<span data-ttu-id="f4682-p106">실패한 미디어 콘텐츠 형식입니다. 예를 들어 공통 콘텐츠 형식은 Application/sdp입니다. SDP(Session Description Protocol)는 세션 알림, 세션 초대 및 멀티 미디어 세션 초대의 다른 형식에 사용된 표준 인터넷 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="f4682-p106">Type of media content that failed. For example, a common content type is Application/sdp. Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span>  <br/> |
|<span data-ttu-id="f4682-154">**응용 프로그램**</span><span class="sxs-lookup"><span data-stu-id="f4682-154">**Application**</span></span> <br/> |<span data-ttu-id="f4682-155">아니요</span><span class="sxs-lookup"><span data-stu-id="f4682-155">No</span></span>  <br/> |<span data-ttu-id="f4682-156">오류와 관련된 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="f4682-156">Application involved in the error.</span></span>  <br/> |
|<span data-ttu-id="f4682-157">**대상 사용자 URI**</span><span class="sxs-lookup"><span data-stu-id="f4682-157">**To user URI**</span></span> <br/> |<span data-ttu-id="f4682-158">아니요</span><span class="sxs-lookup"><span data-stu-id="f4682-158">No</span></span>  <br/> |<span data-ttu-id="f4682-159">세션에 초대된 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="f4682-159">SIP address of the user who was invited to the session.</span></span>  <br/> |
|<span data-ttu-id="f4682-160">**전화 회의 참가 시간(밀리초)**</span><span class="sxs-lookup"><span data-stu-id="f4682-160">**Conference join times (ms)**</span></span> <br/> |<span data-ttu-id="f4682-161">아니요</span><span class="sxs-lookup"><span data-stu-id="f4682-161">No</span></span>  <br/> |<span data-ttu-id="f4682-162">사용자가 전화 회의에 참가하기까지 소요된 시간(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="f4682-162">Amount of time (in milliseconds) it took for the user to join the conference.</span></span>  <br/> |
|<span data-ttu-id="f4682-163">**진단 헤더**</span><span class="sxs-lookup"><span data-stu-id="f4682-163">**Diagnostic header**</span></span> <br/> |<span data-ttu-id="f4682-164">아니요</span><span class="sxs-lookup"><span data-stu-id="f4682-164">No</span></span>  <br/> |<span data-ttu-id="f4682-165">진단 ID 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="f4682-165">Diagnostic ID description.</span></span>  <br/> |
   
<span data-ttu-id="f4682-166">진단 오류 목록은 [Ms-진단 헤더 페이지](https://msdn.microsoft.com/library/gg132446%28v=office.12%29.aspx)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4682-166">A list of diagnostic errors can be found on the [Ms-Diagnostics Header page](https://msdn.microsoft.com/library/gg132446%28v=office.12%29.aspx).</span></span>
  

