---
title: 비즈니스용 Skype 서버의 진단 보고서
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
description: '요약: 비즈니스용 Skype 서버의 진단 보고서에 대해 알아보세요.'
ms.openlocfilehash: d71906f2407a0daadc04417ab60a23c86f5eeb52
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197640"
---
# <a name="diagnostic-report-in-skype-for-business-server"></a><span data-ttu-id="d0042-103">비즈니스용 Skype 서버의 진단 보고서</span><span class="sxs-lookup"><span data-stu-id="d0042-103">Diagnostic Report in Skype for Business Server</span></span>
 
<span data-ttu-id="d0042-104">**요약:** 비즈니스용 Skype 서버의 진단 보고서에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="d0042-104">**Summary:** Learn about the Diagnostic Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="d0042-105">진단 보고서는 실패 한 세션에 대 한 진단 및 문제 해결 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0042-105">The Diagnostic Report provides diagnostic and troubleshooting information for a failed session.</span></span> <span data-ttu-id="d0042-106">이 정보에는 진단 ID와 세션에 실패 했을 때 보고 된 진단 헤더가 모두 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0042-106">This information includes both the Diagnostic ID and the Diagnostic header that were reported when the session failed.</span></span> <span data-ttu-id="d0042-107">진단 ID는 SIP 메시지에 연결 되는 고유 식별자 (ms-진단 헤더 형식) 이며 진단 헤더는 진단 ID에 대해 함께 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0042-107">The Diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) that gets attached to a SIP message, while the Diagnostic header provides an accompanying description for the Diagnostic ID.</span></span> <span data-ttu-id="d0042-108">보고 구성 요소에서 인식 하는 중요 한 문제 해결 세부 정보를 보고서에 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0042-108">The report might also contain valuable troubleshooting details that are known by the reporting component.</span></span> <span data-ttu-id="d0042-109">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d0042-109">For example:</span></span>
  
- <span data-ttu-id="d0042-110">오류를 생성 한 PSTN 게이트웨이에서 제공 하는 원인 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="d0042-110">The cause code provided by the PSTN gateway that generated the failure.</span></span> <span data-ttu-id="d0042-111">PSTN 네트워크에서 발신 통화가 실패 하면, ISDN 사용자 파트 (ISUP)가 자동으로 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0042-111">When an outgoing call fails on the PSTN network, an ISDN User Part (ISUP) cause code is automatically generated.</span></span> <span data-ttu-id="d0042-112">예를 들어 PSTN 게이트웨이에서는 통화를 완료 하는 데 사용할 수 있는 회로 또는 채널이 없음을 나타내기 위해 코드 34를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0042-112">For example, a PSTN gateway might send cause code 34 to indicate that no circuit or channel was available for completing the call.</span></span>
    
- <span data-ttu-id="d0042-113">연결 오류에 대 한 피어 FQDN, 포트 및 Winsock 오류.</span><span class="sxs-lookup"><span data-stu-id="d0042-113">Peer FQDN, port, and Winsock errors for connectivity failures.</span></span>
    
- <span data-ttu-id="d0042-114">DNS 확인 실패를 조회 하는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d0042-114">Names being looked up for DNS resolution failures.</span></span> <span data-ttu-id="d0042-115">DNS 확인은 클라이언트가 이름 서버에 접속 하 고 지정 된 디바이스 이름에 해당 하는 IP 주소를 요청 하는 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0042-115">DNS resolution takes place any time a client contacts a name server and requests the IP address that corresponds to specified device name.</span></span>
    
## <a name="accessing-the-diagnostic-report"></a><span data-ttu-id="d0042-116">진단 보고서에 액세스</span><span class="sxs-lookup"><span data-stu-id="d0042-116">Accessing the Diagnostic Report</span></span>

<span data-ttu-id="d0042-117">[비즈니스용 Skype 서버의 피어 투 피어 세션 세부 정보 보고서](peer-to-peer-session-detail-report.md) 또는 회의 세부 정보 보고서에서 진단 보고서 (세부 정보) 메트릭을 클릭 하 여 진단 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0042-117">The Diagnostic Report can be accessed by clicking the Diagnostic Report (Detail) metric on either the [Peer-to-Peer Session Detail Report in Skype for Business Server](peer-to-peer-session-detail-report.md) or the Conference Detail Report.</span></span>
  
## <a name="filters"></a><span data-ttu-id="d0042-118">필터가</span><span class="sxs-lookup"><span data-stu-id="d0042-118">Filters</span></span>

<span data-ttu-id="d0042-119">없음.</span><span class="sxs-lookup"><span data-stu-id="d0042-119">None.</span></span> <span data-ttu-id="d0042-120">진단 보고서는 필터링 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d0042-120">You cannot filter the Diagnostic Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="d0042-121">매트릭스</span><span class="sxs-lookup"><span data-stu-id="d0042-121">Metrics</span></span>

<span data-ttu-id="d0042-122">다음 표에는 진단 보고서에서 각 세션에 대해 제공 하는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0042-122">The following table lists the information provided in the Diagnostic Report for each session.</span></span>
  
<span data-ttu-id="d0042-123">**진단 보고서 메트릭**</span><span class="sxs-lookup"><span data-stu-id="d0042-123">**Diagnostic Report Metrics**</span></span>

|<span data-ttu-id="d0042-124">**이름**</span><span class="sxs-lookup"><span data-stu-id="d0042-124">**Name**</span></span>|<span data-ttu-id="d0042-125">**이 항목을 정렬할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="d0042-125">**Can you sort on this item?**</span></span>|<span data-ttu-id="d0042-126">**설명**</span><span class="sxs-lookup"><span data-stu-id="d0042-126">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d0042-127">**보고서 시간**</span><span class="sxs-lookup"><span data-stu-id="d0042-127">**Report time**</span></span> <br/> |<span data-ttu-id="d0042-128">아니요</span><span class="sxs-lookup"><span data-stu-id="d0042-128">No</span></span>  <br/> |<span data-ttu-id="d0042-129">보고서가 기록 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="d0042-129">Date and time that the report was recorded.</span></span>  <br/> |
|<span data-ttu-id="d0042-130">**응답 코드**</span><span class="sxs-lookup"><span data-stu-id="d0042-130">**Response code**</span></span> <br/> |<span data-ttu-id="d0042-131">아니요</span><span class="sxs-lookup"><span data-stu-id="d0042-131">No</span></span>  <br/> |<span data-ttu-id="d0042-132">세션이 실패 했을 때 전송 된 SIP 응답 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="d0042-132">SIP response code sent when the session failed.</span></span>  <br/> |
|<span data-ttu-id="d0042-133">**요청 형식**</span><span class="sxs-lookup"><span data-stu-id="d0042-133">**Request type**</span></span> <br/> |<span data-ttu-id="d0042-134">아니요</span><span class="sxs-lookup"><span data-stu-id="d0042-134">No</span></span>  <br/> |<span data-ttu-id="d0042-135">실패 한 SIP 요청 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="d0042-135">SIP request type that failed.</span></span> <span data-ttu-id="d0042-136">예를 들어 초대, BYE, 서비스 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0042-136">For example, INVITE, BYE, or SERVICE.</span></span>  <br/> |
|<span data-ttu-id="d0042-137">**Source**</span><span class="sxs-lookup"><span data-stu-id="d0042-137">**Source**</span></span> <br/> |<span data-ttu-id="d0042-138">아니요</span><span class="sxs-lookup"><span data-stu-id="d0042-138">No</span></span>  <br/> |<span data-ttu-id="d0042-139">오류의 원본입니다.</span><span class="sxs-lookup"><span data-stu-id="d0042-139">Source of the error.</span></span>  <br/> |
|<span data-ttu-id="d0042-140">**사용자 URI에서**</span><span class="sxs-lookup"><span data-stu-id="d0042-140">**From user URI**</span></span> <br/> |<span data-ttu-id="d0042-141">아니요</span><span class="sxs-lookup"><span data-stu-id="d0042-141">No</span></span>  <br/> |<span data-ttu-id="d0042-142">세션을 시작한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d0042-142">SIP address of the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="d0042-143">**사용자 에이전트에서**</span><span class="sxs-lookup"><span data-stu-id="d0042-143">**From user agent**</span></span> <br/> |<span data-ttu-id="d0042-144">아니요</span><span class="sxs-lookup"><span data-stu-id="d0042-144">No</span></span>  <br/> |<span data-ttu-id="d0042-145">세션을 시작한 사용자의 끝점에 사용 되는 소프트웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="d0042-145">Software used by the endpoint of the user who initiated the session.</span></span>  <br/> |
|<span data-ttu-id="d0042-146">**진단 ID**</span><span class="sxs-lookup"><span data-stu-id="d0042-146">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="d0042-147">아니요</span><span class="sxs-lookup"><span data-stu-id="d0042-147">No</span></span>  <br/> |<span data-ttu-id="d0042-148">오류 문제 해결에 유용한 정보를 자주 제공 하는 SIP 메시지에 첨부 된 고유 식별자 (ms-진단 헤더 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="d0042-148">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="d0042-149">**콘텐츠 형식**</span><span class="sxs-lookup"><span data-stu-id="d0042-149">**Content type**</span></span> <br/> |<span data-ttu-id="d0042-150">아니요</span><span class="sxs-lookup"><span data-stu-id="d0042-150">No</span></span>  <br/> |<span data-ttu-id="d0042-151">실패 한 미디어 콘텐츠의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="d0042-151">Type of media content that failed.</span></span> <span data-ttu-id="d0042-152">예를 들어 공용 콘텐츠 형식은 Application/sdp입니다.</span><span class="sxs-lookup"><span data-stu-id="d0042-152">For example, a common content type is Application/sdp.</span></span> <span data-ttu-id="d0042-153">SDP (세션 설명 프로토콜)는 세션 공지 사항, 세션 초대 및 다른 형식의 멀티미디어 세션 초기화에 사용 되는 표준 인터넷 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="d0042-153">Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span>  <br/> |
|<span data-ttu-id="d0042-154">**프로그램**</span><span class="sxs-lookup"><span data-stu-id="d0042-154">**Application**</span></span> <br/> |<span data-ttu-id="d0042-155">아니요</span><span class="sxs-lookup"><span data-stu-id="d0042-155">No</span></span>  <br/> |<span data-ttu-id="d0042-156">오류와 관련 된 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="d0042-156">Application involved in the error.</span></span>  <br/> |
|<span data-ttu-id="d0042-157">**사용자 URI로**</span><span class="sxs-lookup"><span data-stu-id="d0042-157">**To user URI**</span></span> <br/> |<span data-ttu-id="d0042-158">아니요</span><span class="sxs-lookup"><span data-stu-id="d0042-158">No</span></span>  <br/> |<span data-ttu-id="d0042-159">세션에 초대 된 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d0042-159">SIP address of the user who was invited to the session.</span></span>  <br/> |
|<span data-ttu-id="d0042-160">**컨퍼런스 참가 시간 (ms)**</span><span class="sxs-lookup"><span data-stu-id="d0042-160">**Conference join times (ms)**</span></span> <br/> |<span data-ttu-id="d0042-161">아니요</span><span class="sxs-lookup"><span data-stu-id="d0042-161">No</span></span>  <br/> |<span data-ttu-id="d0042-162">사용자가 회의에 참가 하는 데 걸린 시간 (밀리초 단위)입니다.</span><span class="sxs-lookup"><span data-stu-id="d0042-162">Amount of time (in milliseconds) it took for the user to join the conference.</span></span>  <br/> |
|<span data-ttu-id="d0042-163">**진단 헤더**</span><span class="sxs-lookup"><span data-stu-id="d0042-163">**Diagnostic header**</span></span> <br/> |<span data-ttu-id="d0042-164">아니요</span><span class="sxs-lookup"><span data-stu-id="d0042-164">No</span></span>  <br/> |<span data-ttu-id="d0042-165">진단 ID 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="d0042-165">Diagnostic ID description.</span></span>  <br/> |
   
<span data-ttu-id="d0042-166">진단 오류 목록은 [Ms-진단 헤더 페이지](https://msdn.microsoft.com/en-us/library/gg132446%28v=office.12%29.aspx)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0042-166">A list of diagnostic errors can be found on the [Ms-Diagnostics Header page](https://msdn.microsoft.com/en-us/library/gg132446%28v=office.12%29.aspx).</span></span>
  

