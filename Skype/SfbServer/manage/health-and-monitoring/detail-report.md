---
title: 비즈니스용 Skype 서버의 전화 회의 정보 보고서
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
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: '요약: 비즈니스용 Skype 서버에서 사용되는 전화 회의 정보 보고서에 대해 자세히 알아보습니다.'
ms.openlocfilehash: 245691fcb304a872942be4d5a9aabe8183b4db14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816908"
---
# <a name="conference-detail-report-in-skype-for-business-server"></a><span data-ttu-id="492ed-103">비즈니스용 Skype 서버의 전화 회의 정보 보고서</span><span class="sxs-lookup"><span data-stu-id="492ed-103">Conference Detail Report in Skype for Business Server</span></span>

<span data-ttu-id="492ed-104">**요약:** 비즈니스용 Skype 서버에서 사용되는 전화 회의 정보 보고서에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="492ed-104">**Summary:** Learn about the Conference Detail Report used in Skype for Business Server.</span></span>

<span data-ttu-id="492ed-p101">전화 회의 정보 보고서에서는 전화 회의에 참가한 모든 사용자에 대한 자세한 정보를 제공합니다. 예를 들어 사용자가 전화 회의에 참가한 날짜/시간, 사용자가 전화 회의에서 나간 날짜/시간, 그리고 해당 사용자를 전화 회의에 연결하는 데 사용된 끝점의 사용자 에이전트와 같은 정보를 확인할 수 있습니다. 각 전화 회의에서 사용자의 역할(예: 발표자, 참석자) 관련 정보도 볼 수 있습니다. 그러나 가장 중요한 기능은 전화 회의에 정상적으로 참가하여 전화 회의를 완료한 사용자가 그렇지 않은 사용자를 빠르게 확인할 수 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="492ed-p101">The Conference Detail Report provides detailed information about all the users who participated in a conference. For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference. You can also see information the user's role in each conference (for example, Presenter or Attendee). Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="492ed-109">전화 회의 정보 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="492ed-109">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="492ed-110">다음 보고서에서 전화 회의 정보 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492ed-110">The Conference Detail Report can be accessed from the following reports:</span></span>

- <span data-ttu-id="492ed-111">[Call Admission Control Report](call-admission-control-report.md)(전화 회의의 정보 메트릭 클릭)</span><span class="sxs-lookup"><span data-stu-id="492ed-111">The [Call Admission Control Report](call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

- <span data-ttu-id="492ed-112">[Failure List Report](failure-list-report.md)(전화 회의 메트릭 클릭)</span><span class="sxs-lookup"><span data-stu-id="492ed-112">The [Failure List Report](failure-list-report.md) (by clicking the Conference metric)</span></span>

- <span data-ttu-id="492ed-113">[User Activity Report](call-diagnostic-reports-per-user.md)(전화 회의 URI 메트릭 클릭)</span><span class="sxs-lookup"><span data-stu-id="492ed-113">The [User Activity Report](call-diagnostic-reports-per-user.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="492ed-114">전화 회의 정보 보고서에서 진단 보고서(정보) 메트릭을 클릭하면 [Diagnostic Report](diagnostic-report.md)에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="492ed-114">From the Conference Detail Report you can access the [Diagnostic Report](diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

## <a name="filters"></a><span data-ttu-id="492ed-115">필터</span><span class="sxs-lookup"><span data-stu-id="492ed-115">Filters</span></span>

<span data-ttu-id="492ed-p102">없음. 전화 회의 정보 보고서는 필터링할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="492ed-p102">None. You cannot filter on the Conference Detail Report.</span></span>

## <a name="metrics"></a><span data-ttu-id="492ed-118">메트릭</span><span class="sxs-lookup"><span data-stu-id="492ed-118">Metrics</span></span>

<span data-ttu-id="492ed-119">다음 표에서는 전화 회의 정보 보고서의 전화 회의 정보 섹션에서 제공되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="492ed-119">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

<span data-ttu-id="492ed-120">**전화 회의 정보 메트릭**</span><span class="sxs-lookup"><span data-stu-id="492ed-120">**Conference Information Metrics**</span></span>


| <span data-ttu-id="492ed-121">**이름**</span><span class="sxs-lookup"><span data-stu-id="492ed-121">**Name**</span></span>                 | <span data-ttu-id="492ed-122">**설명**</span><span class="sxs-lookup"><span data-stu-id="492ed-122">**Description**</span></span>                                                                                                            |
|:-------------------------|:---------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="492ed-123">**전화 회의 URI**</span><span class="sxs-lookup"><span data-stu-id="492ed-123">**Conference URI**</span></span> <br/> | <span data-ttu-id="492ed-p103">전화 회의에 할당된 URI입니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="492ed-p103">URI assigned to the conference. For example:</span></span>  <br/> <span data-ttu-id="492ed-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="492ed-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span>  <br/> |
| <span data-ttu-id="492ed-127">**풀 FQDN**</span><span class="sxs-lookup"><span data-stu-id="492ed-127">**Pool FQDN**</span></span> <br/>      | <span data-ttu-id="492ed-128">세션에 포함된 등록자 풀 또는 에지 서버의 정규화된 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="492ed-128">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span>  <br/>                             |
| <span data-ttu-id="492ed-129">**시작 시간**</span><span class="sxs-lookup"><span data-stu-id="492ed-129">**Start time**</span></span> <br/>     | <span data-ttu-id="492ed-130">전화 회의가 시작된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="492ed-130">Date and time that the conference started.</span></span>  <br/>                                                                          |
| <span data-ttu-id="492ed-131">**이끌이**</span><span class="sxs-lookup"><span data-stu-id="492ed-131">**Organizer**</span></span> <br/>      | <span data-ttu-id="492ed-132">전화 회의를 구성한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="492ed-132">SIP address of the user who organized the conference.</span></span>  <br/>                                                               |
| <span data-ttu-id="492ed-133">**종료 시간**</span><span class="sxs-lookup"><span data-stu-id="492ed-133">**End time**</span></span> <br/>       | <span data-ttu-id="492ed-134">전화 회의가 종료된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="492ed-134">Date and time that the conference ended.</span></span>  <br/>                                                                            |

<span data-ttu-id="492ed-135">다음 표에서는 전화 회의 정보 보고서의 전화 회의 참가 섹션에서 제공되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="492ed-135">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

<span data-ttu-id="492ed-136">**전화 회의 참가 메트릭**</span><span class="sxs-lookup"><span data-stu-id="492ed-136">**Conference Participation Metrics**</span></span>

|<span data-ttu-id="492ed-137">**이름**</span><span class="sxs-lookup"><span data-stu-id="492ed-137">**Name**</span></span>|<span data-ttu-id="492ed-138">**설명**</span><span class="sxs-lookup"><span data-stu-id="492ed-138">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="492ed-139">**사용자**</span><span class="sxs-lookup"><span data-stu-id="492ed-139">**User**</span></span> <br/> |<span data-ttu-id="492ed-140">전화 회의에 참가한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="492ed-140">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="492ed-141">**역할**</span><span class="sxs-lookup"><span data-stu-id="492ed-141">**Role**</span></span> <br/> |<span data-ttu-id="492ed-142">전화 회의 참가자가 수행하는 역할(예: 발표자)입니다.</span><span class="sxs-lookup"><span data-stu-id="492ed-142">Role (for example, Presenter) played by the conference participant.</span></span>  <br/> |
|<span data-ttu-id="492ed-143">**연결**</span><span class="sxs-lookup"><span data-stu-id="492ed-143">**Connectivity**</span></span> <br/> |<span data-ttu-id="492ed-144">참가자의 네트워크 연결(일반적으로 내부 발신 또는 외부 발신)입니다.</span><span class="sxs-lookup"><span data-stu-id="492ed-144">Network connectivity (typically From Internal or From External) for the participant.</span></span>  <br/> |
|<span data-ttu-id="492ed-145">**참가 시간**</span><span class="sxs-lookup"><span data-stu-id="492ed-145">**Join time**</span></span> <br/> |<span data-ttu-id="492ed-146">참가자가 전화 회의에 참가한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="492ed-146">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="492ed-147">**나간 시간**</span><span class="sxs-lookup"><span data-stu-id="492ed-147">**Leave time**</span></span> <br/> |<span data-ttu-id="492ed-148">참가자가 전화 회의에서 나간 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="492ed-148">Date and time that the participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="492ed-149">**사용자 에이전트**</span><span class="sxs-lookup"><span data-stu-id="492ed-149">**User agent**</span></span> <br/> |<span data-ttu-id="492ed-150">참가자의 끝점에서 사용하는 소프트웨어의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="492ed-150">Identifier for the software used by the participant's endpoint.</span></span>  <br/> |
|<span data-ttu-id="492ed-151">**진단 보고서**</span><span class="sxs-lookup"><span data-stu-id="492ed-151">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="492ed-p104">진단 및 문제 해결 정보를 제공합니다. 여기에는 실패한 세션에 대한 SIP 응답 코드, 진단 헤더, 전화 회의 참가 시간 및 진단 ID가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="492ed-p104">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |

<span data-ttu-id="492ed-154">다음 표에는 회의 정보 보고서의 회의 부호 섹션에 제공된 정보가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="492ed-154">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

<span data-ttu-id="492ed-155">**전화 회의 형식 메트릭**</span><span class="sxs-lookup"><span data-stu-id="492ed-155">**Conference Modalities Metrics**</span></span>

|<span data-ttu-id="492ed-156">**이름**</span><span class="sxs-lookup"><span data-stu-id="492ed-156">**Name**</span></span>|<span data-ttu-id="492ed-157">**설명**</span><span class="sxs-lookup"><span data-stu-id="492ed-157">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="492ed-158">**사용자**</span><span class="sxs-lookup"><span data-stu-id="492ed-158">**User**</span></span> <br/> |<span data-ttu-id="492ed-159">전화 회의에 참가한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="492ed-159">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="492ed-160">**참가 시간**</span><span class="sxs-lookup"><span data-stu-id="492ed-160">**Join time**</span></span> <br/> |<span data-ttu-id="492ed-161">참가자가 전화 회의에 참가한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="492ed-161">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="492ed-162">**나간 시간**</span><span class="sxs-lookup"><span data-stu-id="492ed-162">**Leave time**</span></span> <br/> |<span data-ttu-id="492ed-163">참가자가 전화 회의에서 나간 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="492ed-163">Date and time that a participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="492ed-164">**전화 회의 서버**</span><span class="sxs-lookup"><span data-stu-id="492ed-164">**Conferencing server URI**</span></span> <br/> |<span data-ttu-id="492ed-165">전화 회의에 사용된 전화 회의 서버의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="492ed-165">URI for the Conferencing server used in the conference.</span></span>  <br/> |
|<span data-ttu-id="492ed-166">**진단 보고서**</span><span class="sxs-lookup"><span data-stu-id="492ed-166">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="492ed-p105">진단 및 문제 해결 정보를 제공합니다. 여기에는 실패한 세션에 대한 SIP 응답 코드, 진단 헤더, 전화 회의 참가 시간 및 진단 ID가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="492ed-p105">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |


