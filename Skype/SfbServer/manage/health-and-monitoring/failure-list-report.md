---
title: 비즈니스용 Skype 서버의 오류 목록 보고서
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: '요약: 비즈니스용 Skype 서버의 오류 목록 보고서에 대해 자세히 알아보세요.'
ms.openlocfilehash: d0ba76974d99b123c99e3df40a6850736423ab73
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992825"
---
# <a name="failure-list-report-in-skype-for-business-server"></a><span data-ttu-id="17d97-103">비즈니스용 Skype 서버의 오류 목록 보고서</span><span class="sxs-lookup"><span data-stu-id="17d97-103">Failure List Report in Skype for Business Server</span></span> 
 
<span data-ttu-id="17d97-104">**요약:** 비즈니스용 Skype 서버의 오류 목록 보고서에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="17d97-104">**Summary:** Learn about the Failure List Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="17d97-105">실패 목록 보고서는 실패 한 피어 투 피어 또는 회의 세션에서 참여 한 개별 참가자에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="17d97-105">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session.</span></span> <span data-ttu-id="17d97-106">이 정보에는 문제가 발생 한 사용자의 URI와 실패와 연결 된 SIP 응답 코드 및 진단 ID가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="17d97-106">This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span></span>
  
## <a name="accessing-the-failure-list-report"></a><span data-ttu-id="17d97-107">실패 목록 보고서에 액세스</span><span class="sxs-lookup"><span data-stu-id="17d97-107">Accessing the Failure List Report</span></span>

<span data-ttu-id="17d97-108">실패 목록 보고서는 [비즈니스용 Skype 서버의 실패 한 배포 보고서](failure-distribution-report.md)에서 다음 메트릭 중 하나를 클릭 하 여 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17d97-108">The Failure List Report is accessed by clicking any of the following metrics on the [Failure Distribution Report in Skype for Business Server](failure-distribution-report.md):</span></span>
  
- <span data-ttu-id="17d97-109">주요 진단 이유 (세션)</span><span class="sxs-lookup"><span data-stu-id="17d97-109">Top diagnostic reasons (sessions)</span></span>
    
- <span data-ttu-id="17d97-110">최상위 형식을 (세션)</span><span class="sxs-lookup"><span data-stu-id="17d97-110">Top modalities (sessions)</span></span>
    
- <span data-ttu-id="17d97-111">상위 풀 (세션)</span><span class="sxs-lookup"><span data-stu-id="17d97-111">Top pools (sessions)</span></span>
    
- <span data-ttu-id="17d97-112">상위 원본 (세션)</span><span class="sxs-lookup"><span data-stu-id="17d97-112">Top sources (sessions)</span></span>
    
- <span data-ttu-id="17d97-113">상위 구성 요소 (세션)</span><span class="sxs-lookup"><span data-stu-id="17d97-113">Top components (sessions)</span></span>
    
- <span data-ttu-id="17d97-114">사용자 (세션)의 상위</span><span class="sxs-lookup"><span data-stu-id="17d97-114">Top from users (sessions)</span></span>
    
- <span data-ttu-id="17d97-115">상위 사용자 (세션)</span><span class="sxs-lookup"><span data-stu-id="17d97-115">Top to users (sessions)</span></span>
    
- <span data-ttu-id="17d97-116">사용자 에이전트 (세션)에서 맨 위로</span><span class="sxs-lookup"><span data-stu-id="17d97-116">Top from user agents (sessions)</span></span>
    
<span data-ttu-id="17d97-117">실패 목록 보고서에서 피어 투 피어 세션에 대 한 세션 세부 정보 메트릭을 클릭 하 여 비즈니스용 [Skype 서버의 피어 투 피어 세션 세부 정보 보고서](peer-to-peer-session-detail-report.md) 에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17d97-117">From the Failure List Report you can access the [Peer-to-Peer Session Detail Report in Skype for Business Server](peer-to-peer-session-detail-report.md) by clicking the Session detail metric for a peer-to-peer session.</span></span> <span data-ttu-id="17d97-118">회의에 대 한 회의 메트릭을 클릭 하 여 회의 세부 정보 보고서에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17d97-118">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span></span>
  
## <a name="making-the-best-use-of-the-failure-list-report"></a><span data-ttu-id="17d97-119">실패 목록 보고서를 최대한 활용 하기</span><span class="sxs-lookup"><span data-stu-id="17d97-119">Making the Best Use of the Failure List Report</span></span>

<span data-ttu-id="17d97-120">실패 목록 보고서에서 해당 값 위에 마우스를 놓으면 각 응답 코드 또는 각 진단 ID에 대 한 설명을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17d97-120">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value.</span></span> <span data-ttu-id="17d97-121">예를 들어 마우스를 진단 ID 7025에 포함 하면 도구 설명에 다음이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="17d97-121">For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span></span>
  
<span data-ttu-id="17d97-122">사용자의 미디어를 만드는 동안 내부 서버 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="17d97-122">Internal server error creating media for user.</span></span>
  
<span data-ttu-id="17d97-123">실패 목록 보고서에는 실패 한 하나 이상의 세션에 참가 한 모든 사용자의 목록을 직접 검색 하는 간단한 방법이 나와 있지 않으며, 실패 한 사용자에 게 가장 자주 관여 하는 사람을 확인 하는 방법이 제공 되지 않는다는 점에 유의 해야 합니다. 세션만.</span><span class="sxs-lookup"><span data-stu-id="17d97-123">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session.</span></span> <span data-ttu-id="17d97-124">한 가지 방법으로 실패 목록 보고서에는 필터링 기능이 없습니다. 그러나 데이터를 내보낸 다음 쉼표로 구분 된 값 파일로 변환 하는 경우 Windows PowerShell을 사용 하 여 이와 같은 질문에 대 한 답변을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17d97-124">(For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those.</span></span> <span data-ttu-id="17d97-125">예를 들어 데이터를에 저장 한다고 가정 합니다. CSV 파일 이름 \ Failure_List.</span><span class="sxs-lookup"><span data-stu-id="17d97-125">For example, suppose you save the data to a .CSV file named C:\Data\Failure_List.csv.</span></span> <span data-ttu-id="17d97-126">이 명령은 해당 파일에 저장 된 데이터를 기반으로 하나 이상의 실패 한 세션에 참가 한 모든 사용자를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="17d97-126">Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span></span> 
  
```PowerShell
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

<span data-ttu-id="17d97-127">이 명령은 다음과 같은 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="17d97-127">That command will return a list similar to this:</span></span>
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

<span data-ttu-id="17d97-128">다음 두 명령은 각 사용자가 참여 한 실패 한 총 세션 수를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="17d97-128">These two commands report back the total number of failed sessions that each user was involved in:</span></span>
  
```PowerShell
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

<span data-ttu-id="17d97-129">이는 다음과 같은 데이터를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="17d97-129">That will return data similar to this:</span></span>
  
<pre>
Count    Name
 -----    ----
    20    Pilar.Ackerman@litwareinc.com
    20    David.Ahs@litwareinc.com
    16    Gilead.Amosnino@litwareinc.com
    16    Ken.Myero@litwareinc.com
    14    Henrik.Jensen@litwareinc.com
</pre>

## <a name="filters"></a><span data-ttu-id="17d97-130">필터가</span><span class="sxs-lookup"><span data-stu-id="17d97-130">Filters</span></span>

<span data-ttu-id="17d97-131">없음.</span><span class="sxs-lookup"><span data-stu-id="17d97-131">None.</span></span> <span data-ttu-id="17d97-132">실패 목록 보고서는 필터링 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="17d97-132">You cannot filter the Failure List Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="17d97-133">매트릭스</span><span class="sxs-lookup"><span data-stu-id="17d97-133">Metrics</span></span>

<span data-ttu-id="17d97-134">다음 표에는 실패 목록 보고서에 제공 된 각 통화에 대 한 정보가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17d97-134">The following table lists the information provided in the Failure List Report for each failed call.</span></span>
  
<span data-ttu-id="17d97-135">**실패 목록 보고서 메트릭**</span><span class="sxs-lookup"><span data-stu-id="17d97-135">**Failure List Report Metrics**</span></span>

|<span data-ttu-id="17d97-136">**이름**</span><span class="sxs-lookup"><span data-stu-id="17d97-136">**Name**</span></span>|<span data-ttu-id="17d97-137">**이 항목을 정렬할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="17d97-137">**Can you sort on this item?**</span></span>|<span data-ttu-id="17d97-138">**설명**</span><span class="sxs-lookup"><span data-stu-id="17d97-138">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="17d97-139">**보고 시간**</span><span class="sxs-lookup"><span data-stu-id="17d97-139">**Reported time**</span></span> <br/> |<span data-ttu-id="17d97-140">아니요</span><span class="sxs-lookup"><span data-stu-id="17d97-140">No</span></span>  <br/> |<span data-ttu-id="17d97-141">보고서가 기록 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="17d97-141">Date and time the report was recorded.</span></span>  <br/> |
|<span data-ttu-id="17d97-142">**요청당**</span><span class="sxs-lookup"><span data-stu-id="17d97-142">**Request**</span></span> <br/> |<span data-ttu-id="17d97-143">아니요</span><span class="sxs-lookup"><span data-stu-id="17d97-143">No</span></span>  <br/> |<span data-ttu-id="17d97-144">실패 한 SIP 요청 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="17d97-144">SIP request type that failed.</span></span> <span data-ttu-id="17d97-145">예를 들어 초대 또는 BYE.</span><span class="sxs-lookup"><span data-stu-id="17d97-145">For example, INVITE or BYE.</span></span>  <br/> |
|<span data-ttu-id="17d97-146">**응답 코드**</span><span class="sxs-lookup"><span data-stu-id="17d97-146">**Response code**</span></span> <br/> |<span data-ttu-id="17d97-147">아니요</span><span class="sxs-lookup"><span data-stu-id="17d97-147">No</span></span>  <br/> |<span data-ttu-id="17d97-148">회의에 실패 한 경우 SIP 응답 코드가 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="17d97-148">SIP response code sent when the conference failed.</span></span>  <br/> |
|<span data-ttu-id="17d97-149">**진단 ID**</span><span class="sxs-lookup"><span data-stu-id="17d97-149">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="17d97-150">아니요</span><span class="sxs-lookup"><span data-stu-id="17d97-150">No</span></span>  <br/> |<span data-ttu-id="17d97-151">오류 문제 해결에 유용한 정보를 자주 제공 하는 SIP 메시지에 첨부 된 고유 식별자 (ms-진단 헤더 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="17d97-151">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="17d97-152">**참가 비용 시간 (밀리초)**</span><span class="sxs-lookup"><span data-stu-id="17d97-152">**Join cost time (ms)**</span></span> <br/> |<span data-ttu-id="17d97-153">아니요</span><span class="sxs-lookup"><span data-stu-id="17d97-153">No</span></span>  <br/> |<span data-ttu-id="17d97-154">사용자가 회의에 참가 하는 데 필요한 시간 (밀리초 단위)입니다.</span><span class="sxs-lookup"><span data-stu-id="17d97-154">Amount of time (in milliseconds) required for the user to join the conference.</span></span>  <br/> |
|<span data-ttu-id="17d97-155">**사용자의**</span><span class="sxs-lookup"><span data-stu-id="17d97-155">**From user**</span></span> <br/> |<span data-ttu-id="17d97-156">아니요</span><span class="sxs-lookup"><span data-stu-id="17d97-156">No</span></span>  <br/> |<span data-ttu-id="17d97-157">통화를 시작한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="17d97-157">SIP address of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="17d97-158">**사용자 에이전트에서**</span><span class="sxs-lookup"><span data-stu-id="17d97-158">**From user agent**</span></span> <br/> |<span data-ttu-id="17d97-159">아니요</span><span class="sxs-lookup"><span data-stu-id="17d97-159">No</span></span>  <br/> |<span data-ttu-id="17d97-160">통화를 시작한 사용자의 끝점에서 사용 하는 소프트웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="17d97-160">Software used by the endpoint of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="17d97-161">**사용자에 게**</span><span class="sxs-lookup"><span data-stu-id="17d97-161">**To user**</span></span> <br/> |<span data-ttu-id="17d97-162">아니요</span><span class="sxs-lookup"><span data-stu-id="17d97-162">No</span></span>  <br/> |<span data-ttu-id="17d97-163">호출 되는 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="17d97-163">SIP address of the user who was being called.</span></span>  <br/> |
   

