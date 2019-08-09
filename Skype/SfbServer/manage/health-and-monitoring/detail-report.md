---
title: 비즈니스용 Skype 서버의 컨퍼런스 세부 정보 보고서
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: '요약: 비즈니스용 Skype 서버에서 사용 되는 회의 세부 정보 보고서에 대해 알아보세요.'
ms.openlocfilehash: 17337624c955dfa174f7b98772fdd836e82891d0
ms.sourcegitcommit: 6cbdcb8606044ad7ab49a4e3c828c2dc3d50fcc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "36271401"
---
# <a name="conference-detail-report-in-skype-for-business-server"></a><span data-ttu-id="36b47-103">비즈니스용 Skype 서버의 컨퍼런스 세부 정보 보고서</span><span class="sxs-lookup"><span data-stu-id="36b47-103">Conference Detail Report in Skype for Business Server</span></span>

<span data-ttu-id="36b47-104">**요약:** 비즈니스용 Skype 서버에서 사용 되는 회의 세부 정보 보고서에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="36b47-104">**Summary:** Learn about the Conference Detail Report used in Skype for Business Server.</span></span>

<span data-ttu-id="36b47-105">회의 정보 보고서는 회의에 참가 한 모든 사용자에 대 한 자세한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="36b47-105">The Conference Detail Report provides detailed information about all the users who participated in a conference.</span></span> <span data-ttu-id="36b47-106">예를 들어 사용자가 회의에 참가 한 날짜 및 시간과 사용자가 회의를 남긴 날짜 및 시간, 해당 사용자를 회의에 연결 하는 데 사용 된 끝점의 사용자 에이전트 등의 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36b47-106">For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference.</span></span> <span data-ttu-id="36b47-107">각 회의에서 사용자의 역할에 대 한 정보를 볼 수도 있습니다 (예: 발표자 또는 참석자).</span><span class="sxs-lookup"><span data-stu-id="36b47-107">You can also see information the user's role in each conference (for example, Presenter or Attendee).</span></span> <span data-ttu-id="36b47-108">가장 중요 한 점은 회의를 성공적으로 참가 하 고 완료 하는 사용자와 회의를 성공적으로 참가 및 완료할 수 없었던 사용자를 빠르게 확인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="36b47-108">Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="36b47-109">회의 세부 정보 보고서에 액세스</span><span class="sxs-lookup"><span data-stu-id="36b47-109">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="36b47-110">회의 세부 정보 보고서는 다음 보고서에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36b47-110">The Conference Detail Report can be accessed from the following reports:</span></span>

- <span data-ttu-id="36b47-111">[전화 허용 컨트롤 보고서](call-admission-control-report.md) (컨퍼런스에 대 한 세부 정보 메트릭 클릭)</span><span class="sxs-lookup"><span data-stu-id="36b47-111">The [Call Admission Control Report](call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

- <span data-ttu-id="36b47-112">[실패 목록 보고서](failure-list-report.md) (회의 메트릭 클릭)</span><span class="sxs-lookup"><span data-stu-id="36b47-112">The [Failure List Report](failure-list-report.md) (by clicking the Conference metric)</span></span>

- <span data-ttu-id="36b47-113">[사용자 활동 보고서](call-diagnostic-reports-per-user.md) (컨퍼런스 URI 메트릭 클릭)</span><span class="sxs-lookup"><span data-stu-id="36b47-113">The [User Activity Report](call-diagnostic-reports-per-user.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="36b47-114">회의 정보 보고서에서 진단 보고서 (세부 정보) 메트릭을 클릭 하 여 [진단 보고서](diagnostic-report.md) 에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36b47-114">From the Conference Detail Report you can access the [Diagnostic Report](diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

## <a name="filters"></a><span data-ttu-id="36b47-115">필터가</span><span class="sxs-lookup"><span data-stu-id="36b47-115">Filters</span></span>

<span data-ttu-id="36b47-116">없음.</span><span class="sxs-lookup"><span data-stu-id="36b47-116">None.</span></span> <span data-ttu-id="36b47-117">회의 세부 정보 보고서에서 필터링 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36b47-117">You cannot filter on the Conference Detail Report.</span></span>

## <a name="metrics"></a><span data-ttu-id="36b47-118">매트릭스</span><span class="sxs-lookup"><span data-stu-id="36b47-118">Metrics</span></span>

<span data-ttu-id="36b47-119">다음 표에는 회의 세부 정보 보고서의 컨퍼런스 Information 섹션에서 제공 하는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36b47-119">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

<span data-ttu-id="36b47-120">**컨퍼런스 정보 메트릭**</span><span class="sxs-lookup"><span data-stu-id="36b47-120">**Conference Information Metrics**</span></span>


| <span data-ttu-id="36b47-121">**이름**</span><span class="sxs-lookup"><span data-stu-id="36b47-121">**Name**</span></span>                 | <span data-ttu-id="36b47-122">**설명**</span><span class="sxs-lookup"><span data-stu-id="36b47-122">**Description**</span></span>                                                                                                            |
|:-------------------------|:---------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="36b47-123">**컨퍼런스 URI**</span><span class="sxs-lookup"><span data-stu-id="36b47-123">**Conference URI**</span></span> <br/> | <span data-ttu-id="36b47-124">회의에 할당 된 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="36b47-124">URI assigned to the conference.</span></span> <span data-ttu-id="36b47-125">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="36b47-125">For example:</span></span>  <br/> <span data-ttu-id="36b47-126">sip: kmyer@litwareinc.com, gruu, 불투명 = app: 회의: 포커스: id: drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="36b47-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span>  <br/> |
| <span data-ttu-id="36b47-127">**풀 FQDN**</span><span class="sxs-lookup"><span data-stu-id="36b47-127">**Pool FQDN**</span></span> <br/>      | <span data-ttu-id="36b47-128">세션에 포함 된 레지스트라 풀 또는 Edge 서버의 정규화 된 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="36b47-128">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span>  <br/>                             |
| <span data-ttu-id="36b47-129">**시작 시간**</span><span class="sxs-lookup"><span data-stu-id="36b47-129">**Start time**</span></span> <br/>     | <span data-ttu-id="36b47-130">회의가 시작 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="36b47-130">Date and time that the conference started.</span></span>  <br/>                                                                          |
| <span data-ttu-id="36b47-131">**구성 도우미**</span><span class="sxs-lookup"><span data-stu-id="36b47-131">**Organizer**</span></span> <br/>      | <span data-ttu-id="36b47-132">회의를 구성한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="36b47-132">SIP address of the user who organized the conference.</span></span>  <br/>                                                               |
| <span data-ttu-id="36b47-133">**종료 시간**</span><span class="sxs-lookup"><span data-stu-id="36b47-133">**End time**</span></span> <br/>       | <span data-ttu-id="36b47-134">회의가 종료 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="36b47-134">Date and time that the conference ended.</span></span>  <br/>                                                                            |

<span data-ttu-id="36b47-135">다음 표에는 회의 세부 정보 보고서의 회의 참여 섹션에서 제공 하는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36b47-135">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

<span data-ttu-id="36b47-136">**회의 참여 메트릭**</span><span class="sxs-lookup"><span data-stu-id="36b47-136">**Conference Participation Metrics**</span></span>

|<span data-ttu-id="36b47-137">**이름**</span><span class="sxs-lookup"><span data-stu-id="36b47-137">**Name**</span></span>|<span data-ttu-id="36b47-138">**설명**</span><span class="sxs-lookup"><span data-stu-id="36b47-138">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="36b47-139">**클릭할**</span><span class="sxs-lookup"><span data-stu-id="36b47-139">**User**</span></span> <br/> |<span data-ttu-id="36b47-140">회의에 참가 한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="36b47-140">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="36b47-141">**역할인**</span><span class="sxs-lookup"><span data-stu-id="36b47-141">**Role**</span></span> <br/> |<span data-ttu-id="36b47-142">회의 참가자가 재생 한 역할 (예: 발표자)입니다.</span><span class="sxs-lookup"><span data-stu-id="36b47-142">Role (for example, Presenter) played by the conference participant.</span></span>  <br/> |
|<span data-ttu-id="36b47-143">**연결성**</span><span class="sxs-lookup"><span data-stu-id="36b47-143">**Connectivity**</span></span> <br/> |<span data-ttu-id="36b47-144">참가자의 네트워크 연결 (일반적으로 내부 또는 외부에서)</span><span class="sxs-lookup"><span data-stu-id="36b47-144">Network connectivity (typically From Internal or From External) for the participant.</span></span>  <br/> |
|<span data-ttu-id="36b47-145">**참가 시간**</span><span class="sxs-lookup"><span data-stu-id="36b47-145">**Join time**</span></span> <br/> |<span data-ttu-id="36b47-146">참가자가 회의에 참가 한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="36b47-146">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="36b47-147">**휴가 시간**</span><span class="sxs-lookup"><span data-stu-id="36b47-147">**Leave time**</span></span> <br/> |<span data-ttu-id="36b47-148">참가자가 회의를 남겨진 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="36b47-148">Date and time that the participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="36b47-149">**사용자 에이전트**</span><span class="sxs-lookup"><span data-stu-id="36b47-149">**User agent**</span></span> <br/> |<span data-ttu-id="36b47-150">참가자의 끝점에 사용 되는 소프트웨어의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="36b47-150">Identifier for the software used by the participant's endpoint.</span></span>  <br/> |
|<span data-ttu-id="36b47-151">**진단 보고서**</span><span class="sxs-lookup"><span data-stu-id="36b47-151">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="36b47-152">진단 및 문제 해결 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="36b47-152">Provides diagnostic and troubleshooting information.</span></span> <span data-ttu-id="36b47-153">실패 한 세션에 대 한 SIP 응답 코드, 진단 헤더, 컨퍼런스 참가 시간, 진단 Id 등이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36b47-153">Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |

<span data-ttu-id="36b47-154">다음 표에는 회의 세부 정보 보고서의 컨퍼런스 형식을 섹션에서 제공 하는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36b47-154">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

<span data-ttu-id="36b47-155">**컨퍼런스 형식을 메트릭**</span><span class="sxs-lookup"><span data-stu-id="36b47-155">**Conference Modalities Metrics**</span></span>

|<span data-ttu-id="36b47-156">**이름**</span><span class="sxs-lookup"><span data-stu-id="36b47-156">**Name**</span></span>|<span data-ttu-id="36b47-157">**설명**</span><span class="sxs-lookup"><span data-stu-id="36b47-157">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="36b47-158">**클릭할**</span><span class="sxs-lookup"><span data-stu-id="36b47-158">**User**</span></span> <br/> |<span data-ttu-id="36b47-159">회의에 참가 한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="36b47-159">SIP address of the user who participated in the conference.</span></span>  <br/> |
|<span data-ttu-id="36b47-160">**참가 시간**</span><span class="sxs-lookup"><span data-stu-id="36b47-160">**Join time**</span></span> <br/> |<span data-ttu-id="36b47-161">참가자가 회의에 참가 한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="36b47-161">Date and time that the participant joined the conference.</span></span>  <br/> |
|<span data-ttu-id="36b47-162">**휴가 시간**</span><span class="sxs-lookup"><span data-stu-id="36b47-162">**Leave time**</span></span> <br/> |<span data-ttu-id="36b47-163">참가자가 회의를 남겨진 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="36b47-163">Date and time that a participant left the conference.</span></span>  <br/> |
|<span data-ttu-id="36b47-164">**회의 서버 URI**</span><span class="sxs-lookup"><span data-stu-id="36b47-164">**Conferencing server URI**</span></span> <br/> |<span data-ttu-id="36b47-165">회의에 사용 되는 회의 서버의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="36b47-165">URI for the Conferencing server used in the conference.</span></span>  <br/> |
|<span data-ttu-id="36b47-166">**진단 보고서**</span><span class="sxs-lookup"><span data-stu-id="36b47-166">**Diagnostic reports**</span></span> <br/> |<span data-ttu-id="36b47-167">진단 및 문제 해결 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="36b47-167">Provides diagnostic and troubleshooting information.</span></span> <span data-ttu-id="36b47-168">실패 한 세션에 대 한 SIP 응답 코드, 진단 헤더, 컨퍼런스 참가 시간, 진단 Id 등이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36b47-168">Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span>  <br/> |


