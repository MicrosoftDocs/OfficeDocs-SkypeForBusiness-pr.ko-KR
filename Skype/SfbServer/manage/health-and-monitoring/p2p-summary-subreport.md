---
title: 비즈니스용 Skype 서버의 P2P 요약 하위 보고서
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
ms.assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
description: '요약: 비즈니스용 Skype 서버의 P2P 요약 하위 보고서에 대해 알아보세요.'
ms.openlocfilehash: 31e17aaff8d449c49a7c51d3dba484e7fab48d55
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817797"
---
# <a name="p2p-summary-subreport-in-skype-for-business-server"></a><span data-ttu-id="8f702-103">비즈니스용 Skype 서버의 P2P 요약 하위 보고서</span><span class="sxs-lookup"><span data-stu-id="8f702-103">P2P Summary Subreport in Skype for Business Server</span></span>
 
<span data-ttu-id="8f702-104">**요약:** 비즈니스용 Skype 서버의 P2P 요약 하위 보고서에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="8f702-104">**Summary:** Learn about the P2P Summary Subreport in Skype for Business Server.</span></span>
  
<span data-ttu-id="8f702-105">P2P 요약 하위 보고서는 실패 한 피어 투 피어 통신 세션에 대 한 전체적인 보기를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f702-105">The P2P Summary Subreport provides an overall view of your failed peer-to-peer communication sessions.</span></span>
  
## <a name="filters"></a><span data-ttu-id="8f702-106">필터가</span><span class="sxs-lookup"><span data-stu-id="8f702-106">Filters</span></span>

<span data-ttu-id="8f702-107">필터는 더욱 세밀 하 게 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f702-107">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="8f702-108">다음 표에는 P2P 요약 하위 보고서에 사용할 수 있는 필터가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f702-108">The following table lists the filters that you can use with the P2P Summary Subreport.</span></span>
  
<span data-ttu-id="8f702-109">**P2P 요약 하위 보고서 필터**</span><span class="sxs-lookup"><span data-stu-id="8f702-109">**P2P Summary Subreport Filters**</span></span>

|<span data-ttu-id="8f702-110">**이름**</span><span class="sxs-lookup"><span data-stu-id="8f702-110">**Name**</span></span>|<span data-ttu-id="8f702-111">**설명**</span><span class="sxs-lookup"><span data-stu-id="8f702-111">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8f702-112">**보낸 사람**</span><span class="sxs-lookup"><span data-stu-id="8f702-112">**From**</span></span> <br/> |<span data-ttu-id="8f702-113">시간 범위에 대 한 시작 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="8f702-113">Start date and time for the time range.</span></span> <span data-ttu-id="8f702-114">시간별로 데이터를 보려면 시작 날짜와 시간을 모두 다음과 같이 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f702-114">To view data by hours, enter both the start date and time as follows:</span></span>  <br/> <span data-ttu-id="8f702-115">오후 7/7/2015 1:00</span><span class="sxs-lookup"><span data-stu-id="8f702-115">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="8f702-116">시작 시간을 입력 하지 않으면 지정한 날짜에 오전 12:00부터 보고서가 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f702-116">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="8f702-117">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f702-117">To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="8f702-118">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="8f702-118">7/7/2015</span></span>  <br/> <span data-ttu-id="8f702-119">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="8f702-119">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="8f702-120">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="8f702-120">7/3/2015</span></span>  <br/> <span data-ttu-id="8f702-121">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f702-121">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="8f702-122">**받는 사람**</span><span class="sxs-lookup"><span data-stu-id="8f702-122">**To**</span></span> <br/> |<span data-ttu-id="8f702-123">시간 범위의 종료 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="8f702-123">End date and time for the time range.</span></span> <span data-ttu-id="8f702-124">시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f702-124">To view data by hours, enter both the end date and time as follows:</span></span>  <br/> <span data-ttu-id="8f702-125">오후 7/7/2015 1:00</span><span class="sxs-lookup"><span data-stu-id="8f702-125">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="8f702-126">종료 시간을 입력 하지 않으면 지정한 날짜에 12:00 오전에 보고서가 자동으로 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f702-126">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="8f702-127">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f702-127">To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="8f702-128">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="8f702-128">7/7/2015</span></span>  <br/> <span data-ttu-id="8f702-129">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="8f702-129">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="8f702-130">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="8f702-130">7/3/2015</span></span>  <br/> <span data-ttu-id="8f702-131">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f702-131">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="8f702-132">**풀**</span><span class="sxs-lookup"><span data-stu-id="8f702-132">**Pool**</span></span> <br/> |<span data-ttu-id="8f702-133">등록자 풀 또는 Edge 서버의 FQDN (정규화 된 도메인 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="8f702-133">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="8f702-134">개별 풀을 선택 하거나 **[모두]** 를 클릭 하 여 모든 풀에 대 한 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f702-134">You can either select an individual pool or click **[All]** to view data for all the pools.</span></span> <span data-ttu-id="8f702-135">이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="8f702-135">This drop-down list is automatically populated for you based on the records in the database.</span></span> <br/> |
   
## <a name="metrics"></a><span data-ttu-id="8f702-136">매트릭스</span><span class="sxs-lookup"><span data-stu-id="8f702-136">Metrics</span></span>

<span data-ttu-id="8f702-137">다음 표에는 P2P 요약 하위 보고서에 제공 되는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f702-137">The following table lists the information provided in the P2P Summary Subreport.</span></span>
  
<span data-ttu-id="8f702-138">**P2P 요약 하위 보고서 메트릭**</span><span class="sxs-lookup"><span data-stu-id="8f702-138">**P2P Summary Subreport Metrics**</span></span>

|<span data-ttu-id="8f702-139">**이름**</span><span class="sxs-lookup"><span data-stu-id="8f702-139">**Name**</span></span>|<span data-ttu-id="8f702-140">**이 항목을 정렬할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="8f702-140">**Can you sort on this item?**</span></span>|<span data-ttu-id="8f702-141">**설명**</span><span class="sxs-lookup"><span data-stu-id="8f702-141">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8f702-142">**총 세션**</span><span class="sxs-lookup"><span data-stu-id="8f702-142">**Total sessions**</span></span> <br/> |<span data-ttu-id="8f702-143">아니요</span><span class="sxs-lookup"><span data-stu-id="8f702-143">No</span></span>  <br/> |<span data-ttu-id="8f702-144">성공한 세션, 실패 한 세션 (예상 되는 실패 및 예기치 못한 실패), 범주화 되지 않은 세션 등의 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8f702-144">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span>  <br/> |
|<span data-ttu-id="8f702-145">**실패 율**</span><span class="sxs-lookup"><span data-stu-id="8f702-145">**Failure rate**</span></span> <br/> |<span data-ttu-id="8f702-146">아니요</span><span class="sxs-lookup"><span data-stu-id="8f702-146">No</span></span>  <br/> |<span data-ttu-id="8f702-147">실패 한 피어 투 피어 세션의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="8f702-147">Percentage of peer-to-peer sessions that failed.</span></span>  <br/> |
|<span data-ttu-id="8f702-148">**모달의 세션**</span><span class="sxs-lookup"><span data-stu-id="8f702-148">**Sessions by Modality**</span></span> <br/> |<span data-ttu-id="8f702-149">아니요</span><span class="sxs-lookup"><span data-stu-id="8f702-149">No</span></span>  <br/> |<span data-ttu-id="8f702-150">모달 (예: 인스턴트 메시지)에 의해 그룹화 된 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8f702-150">Total number of sessions grouped by modality (for example, instant messaging).</span></span>  <br/> |
|<span data-ttu-id="8f702-151">**모달의 실패 비율**</span><span class="sxs-lookup"><span data-stu-id="8f702-151">**Failure rate by modality**</span></span> <br/> |<span data-ttu-id="8f702-152">아니요</span><span class="sxs-lookup"><span data-stu-id="8f702-152">No</span></span>  <br/> |<span data-ttu-id="8f702-153">모달 (예: 인스턴트 메시지)로 그룹화 된 실패 한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8f702-153">Total number of failed sessions grouped by modality (for example, instant messaging).</span></span>  <br/> |
   

