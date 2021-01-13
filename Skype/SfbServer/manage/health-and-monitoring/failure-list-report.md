---
title: 비즈니스용 Skype 서버의 오류 목록 보고서
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
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: '요약: 비즈니스용 Skype 서버의 오류 목록 보고서에 대해 자세히 알아보습니다.'
ms.openlocfilehash: 48654ee827f0d7efcb50bcccc4e1d2f3fdb5422e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816848"
---
# <a name="failure-list-report-in-skype-for-business-server"></a><span data-ttu-id="c93ad-103">비즈니스용 Skype 서버의 오류 목록 보고서</span><span class="sxs-lookup"><span data-stu-id="c93ad-103">Failure List Report in Skype for Business Server</span></span> 
 
<span data-ttu-id="c93ad-104">**요약:** 비즈니스용 Skype 서버의 오류 목록 보고서에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="c93ad-104">**Summary:** Learn about the Failure List Report in Skype for Business Server.</span></span>
  
<span data-ttu-id="c93ad-p101">오류 목록 보고서에서는 실패한 피어 투 피어 또는 회의 세션에 참가한 개별 참가자에 대한 정보를 제공합니다. 이 정보에는 문제를 경험한 사용자의 URI와 실패와 관련된 SIP 응답 코드 및 진단 ID가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c93ad-p101">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session. This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span></span>
  
## <a name="accessing-the-failure-list-report"></a><span data-ttu-id="c93ad-107">오류 목록 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="c93ad-107">Accessing the Failure List Report</span></span>

<span data-ttu-id="c93ad-108">오류 목록 보고서는 비즈니스용 Skype 서버의 실패 분포 보고서에서 다음 메트릭 중 원하는 항목 중 한 가지를 클릭하여 [액세스합니다.](failure-distribution-report.md)</span><span class="sxs-lookup"><span data-stu-id="c93ad-108">The Failure List Report is accessed by clicking any of the following metrics on the [Failure Distribution Report in Skype for Business Server](failure-distribution-report.md):</span></span>
  
- <span data-ttu-id="c93ad-109">상위 진단 이유(세션)</span><span class="sxs-lookup"><span data-stu-id="c93ad-109">Top diagnostic reasons (sessions)</span></span>
    
- <span data-ttu-id="c93ad-110">상위 형식(세션)</span><span class="sxs-lookup"><span data-stu-id="c93ad-110">Top modalities (sessions)</span></span>
    
- <span data-ttu-id="c93ad-111">상위 풀(세션)</span><span class="sxs-lookup"><span data-stu-id="c93ad-111">Top pools (sessions)</span></span>
    
- <span data-ttu-id="c93ad-112">상위 원본(세션)</span><span class="sxs-lookup"><span data-stu-id="c93ad-112">Top sources (sessions)</span></span>
    
- <span data-ttu-id="c93ad-113">상위 구성 요소(세션)</span><span class="sxs-lookup"><span data-stu-id="c93ad-113">Top components (sessions)</span></span>
    
- <span data-ttu-id="c93ad-114">상위 출처 사용자(세션)</span><span class="sxs-lookup"><span data-stu-id="c93ad-114">Top from users (sessions)</span></span>
    
- <span data-ttu-id="c93ad-115">상위 대상 사용자(세션)</span><span class="sxs-lookup"><span data-stu-id="c93ad-115">Top to users (sessions)</span></span>
    
- <span data-ttu-id="c93ad-116">상위 출처 사용자 에이전트(세션)</span><span class="sxs-lookup"><span data-stu-id="c93ad-116">Top from user agents (sessions)</span></span>
    
<span data-ttu-id="c93ad-117">오류 목록 보고서에서 피어 투 피어 세션에 대한 세션 세부 정보 메트릭을 클릭하여 비즈니스용 [Skype](peer-to-peer-session-detail-report.md) 서버의 피어 투 피어 세션 세부 정보 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c93ad-117">From the Failure List Report you can access the [Peer-to-Peer Session Detail Report in Skype for Business Server](peer-to-peer-session-detail-report.md) by clicking the Session detail metric for a peer-to-peer session.</span></span> <span data-ttu-id="c93ad-118">또한 전화 회의에 대한 전화 회의 메트릭을 클릭하여 전화 회의 정보 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c93ad-118">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span></span>
  
## <a name="making-the-best-use-of-the-failure-list-report"></a><span data-ttu-id="c93ad-119">오류 목록 보고서의 효과적인 활용</span><span class="sxs-lookup"><span data-stu-id="c93ad-119">Making the Best Use of the Failure List Report</span></span>

<span data-ttu-id="c93ad-p103">오류 목록 보고서에서는 각 응답 코드 또는 각 진단 ID 위에 마우스를 놓기만 하면 해당 값에 대한 설명을 볼 수 있습니다. 예를 들어 진단 ID 7025 위에 마우스를 놓으면 도구 설명에 다음이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c93ad-p103">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value. For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span></span>
  
<span data-ttu-id="c93ad-122">사용자를 위한 미디어를 만드는 동안 내부 서버 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="c93ad-122">Internal server error creating media for user.</span></span>
  
<span data-ttu-id="c93ad-p104">오류 목록 보고서는 하나 이상의 실패한 세션에 참가한 모든 사용자의 목록을 직접 검색하는 간편한 방법이나 실패한 세션에서 가장 자주 참여한 사용자를 파악하는 방법을 제공하지 않습니다. 우선 한 가지 이유는 오류 목록 보고서에 필터링 기능이 없기 때문입니다. 그러나 데이터를 내보낸 후에 쉼표로 구분된 값 파일로 변환할 경우 Windows PowerShell을 사용하여 이러한 사항을 찾을 수 있습니다. 예를 들어 데이터를 C:\Data\Failure_List.csv라는 이름의 .CSV 파일로 저장한 경우 다음 명령을 사용하면 이 파일에 저장된 데이터를 기반으로 하나 이상의 실패한 세션에 참여한 모든 사용자가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="c93ad-p104">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session. (For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those. For example, suppose you save the data to a .CSV file named C:\Data\Failure_List.csv. Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span></span> 
  
```PowerShell
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

<span data-ttu-id="c93ad-127">그러면 다음과 같은 목록이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="c93ad-127">That command will return a list similar to this:</span></span>
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

<span data-ttu-id="c93ad-128">다음 두 명령은 각 사용자가 참가한 실패한 총 세션 수를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="c93ad-128">These two commands report back the total number of failed sessions that each user was involved in:</span></span>
  
```PowerShell
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

<span data-ttu-id="c93ad-129">그러면 다음과 같은 데이터가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="c93ad-129">That will return data similar to this:</span></span>
  
<pre>
Count    Name
 -----    ----
    20    Pilar.Ackerman@litwareinc.com
    20    David.Ahs@litwareinc.com
    16    Gilead.Amosnino@litwareinc.com
    16    Ken.Myero@litwareinc.com
    14    Henrik.Jensen@litwareinc.com
</pre>

## <a name="filters"></a><span data-ttu-id="c93ad-130">필터</span><span class="sxs-lookup"><span data-stu-id="c93ad-130">Filters</span></span>

<span data-ttu-id="c93ad-p105">없음. 오류 목록 보고서는 필터링할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c93ad-p105">None. You cannot filter the Failure List Report.</span></span>
  
## <a name="metrics"></a><span data-ttu-id="c93ad-133">메트릭</span><span class="sxs-lookup"><span data-stu-id="c93ad-133">Metrics</span></span>

<span data-ttu-id="c93ad-134">다음 표에서는 각 실패한 통화에 대해 오류 목록 보고서에 제공된 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c93ad-134">The following table lists the information provided in the Failure List Report for each failed call.</span></span>
  
<span data-ttu-id="c93ad-135">**오류 목록 보고서 메트릭**</span><span class="sxs-lookup"><span data-stu-id="c93ad-135">**Failure List Report Metrics**</span></span>

|<span data-ttu-id="c93ad-136">**이름**</span><span class="sxs-lookup"><span data-stu-id="c93ad-136">**Name**</span></span>|<span data-ttu-id="c93ad-137">**이 항목에 대한 정렬 가능 여부**</span><span class="sxs-lookup"><span data-stu-id="c93ad-137">**Can you sort on this item?**</span></span>|<span data-ttu-id="c93ad-138">**설명**</span><span class="sxs-lookup"><span data-stu-id="c93ad-138">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c93ad-139">**보고된 시간**</span><span class="sxs-lookup"><span data-stu-id="c93ad-139">**Reported time**</span></span> <br/> |<span data-ttu-id="c93ad-140">아니요</span><span class="sxs-lookup"><span data-stu-id="c93ad-140">No</span></span>  <br/> |<span data-ttu-id="c93ad-141">보고서가 기록된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="c93ad-141">Date and time the report was recorded.</span></span>  <br/> |
|<span data-ttu-id="c93ad-142">**요청**</span><span class="sxs-lookup"><span data-stu-id="c93ad-142">**Request**</span></span> <br/> |<span data-ttu-id="c93ad-143">아니요</span><span class="sxs-lookup"><span data-stu-id="c93ad-143">No</span></span>  <br/> |<span data-ttu-id="c93ad-p106">실패한 SIP 요청 유형입니다. 예: INVITE 또는 BYE</span><span class="sxs-lookup"><span data-stu-id="c93ad-p106">SIP request type that failed. For example, INVITE or BYE.</span></span>  <br/> |
|<span data-ttu-id="c93ad-146">**응답 코드**</span><span class="sxs-lookup"><span data-stu-id="c93ad-146">**Response code**</span></span> <br/> |<span data-ttu-id="c93ad-147">아니요</span><span class="sxs-lookup"><span data-stu-id="c93ad-147">No</span></span>  <br/> |<span data-ttu-id="c93ad-148">회의가 실패했을 때 전송된 SIP 응답 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c93ad-148">SIP response code sent when the conference failed.</span></span>  <br/> |
|<span data-ttu-id="c93ad-149">**진단 ID**</span><span class="sxs-lookup"><span data-stu-id="c93ad-149">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="c93ad-150">아니요</span><span class="sxs-lookup"><span data-stu-id="c93ad-150">No</span></span>  <br/> |<span data-ttu-id="c93ad-151">오류 문제를 해결할 때 종종 유용한 정보를 제공하는 SIP 메시지에 연결된 고유 식별자(ms-diagnostics 헤더 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="c93ad-151">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |
|<span data-ttu-id="c93ad-152">**참가 소요 시간(밀리초)**</span><span class="sxs-lookup"><span data-stu-id="c93ad-152">**Join cost time (ms)**</span></span> <br/> |<span data-ttu-id="c93ad-153">아니요</span><span class="sxs-lookup"><span data-stu-id="c93ad-153">No</span></span>  <br/> |<span data-ttu-id="c93ad-154">사용자가 전화 회의에 참가하기까지 소요된 시간(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="c93ad-154">Amount of time (in milliseconds) required for the user to join the conference.</span></span>  <br/> |
|<span data-ttu-id="c93ad-155">**시작 사용자**</span><span class="sxs-lookup"><span data-stu-id="c93ad-155">**From user**</span></span> <br/> |<span data-ttu-id="c93ad-156">아니요</span><span class="sxs-lookup"><span data-stu-id="c93ad-156">No</span></span>  <br/> |<span data-ttu-id="c93ad-157">통화를 시작한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c93ad-157">SIP address of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="c93ad-158">**출처 사용자 에이전트**</span><span class="sxs-lookup"><span data-stu-id="c93ad-158">**From user agent**</span></span> <br/> |<span data-ttu-id="c93ad-159">아니요</span><span class="sxs-lookup"><span data-stu-id="c93ad-159">No</span></span>  <br/> |<span data-ttu-id="c93ad-160">통화를 시작한 사용자의 끝점에 사용된 소프트웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="c93ad-160">Software used by the endpoint of the user who initiated the call.</span></span>  <br/> |
|<span data-ttu-id="c93ad-161">**대상 사용자**</span><span class="sxs-lookup"><span data-stu-id="c93ad-161">**To user**</span></span> <br/> |<span data-ttu-id="c93ad-162">아니요</span><span class="sxs-lookup"><span data-stu-id="c93ad-162">No</span></span>  <br/> |<span data-ttu-id="c93ad-163">통화를 받고 있는 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c93ad-163">SIP address of the user who was being called.</span></span>  <br/> |
   

