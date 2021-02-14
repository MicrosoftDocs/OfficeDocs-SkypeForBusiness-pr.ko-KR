---
title: 비즈니스용 Skype 서버의 P2P 요약 하위 보고서
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
ms.assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
description: '요약: 비즈니스용 Skype 서버의 P2P 요약 하위 보고서에 대해 자세히 알아보습니다.'
ms.openlocfilehash: 518047fbca3c46cdc9b99299b8222d4f4fbd48ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816818"
---
# <a name="p2p-summary-subreport-in-skype-for-business-server"></a><span data-ttu-id="05f88-103">비즈니스용 Skype 서버의 P2P 요약 하위 보고서</span><span class="sxs-lookup"><span data-stu-id="05f88-103">P2P Summary Subreport in Skype for Business Server</span></span>
 
<span data-ttu-id="05f88-104">**요약:** 비즈니스용 Skype 서버의 P2P 요약 하위 보고서에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="05f88-104">**Summary:** Learn about the P2P Summary Subreport in Skype for Business Server.</span></span>
  
<span data-ttu-id="05f88-105">P2P 요약 하위 보고서는 실패한 피어 투 피어 통신 세션에 대한 전체 보기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="05f88-105">The P2P Summary Subreport provides an overall view of your failed peer-to-peer communication sessions.</span></span>
  
## <a name="filters"></a><span data-ttu-id="05f88-106">필터</span><span class="sxs-lookup"><span data-stu-id="05f88-106">Filters</span></span>

<span data-ttu-id="05f88-p101">필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 다음 표에는 P2P 요약 하위 보고서에 사용할 수 있는 필터가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05f88-p101">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the P2P Summary Subreport.</span></span>
  
<span data-ttu-id="05f88-109">**P2P 요약 하위 보고서 필터**</span><span class="sxs-lookup"><span data-stu-id="05f88-109">**P2P Summary Subreport Filters**</span></span>

|<span data-ttu-id="05f88-110">**이름**</span><span class="sxs-lookup"><span data-stu-id="05f88-110">**Name**</span></span>|<span data-ttu-id="05f88-111">**설명**</span><span class="sxs-lookup"><span data-stu-id="05f88-111">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="05f88-112">**시작**</span><span class="sxs-lookup"><span data-stu-id="05f88-112">**From**</span></span> <br/> |<span data-ttu-id="05f88-p102">시간 범위의 시작 날짜 및 시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜와 시간을 모두 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="05f88-p102">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span>  <br/> <span data-ttu-id="05f88-115">2015/7/7 오후 1:00</span><span class="sxs-lookup"><span data-stu-id="05f88-115">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="05f88-p103">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="05f88-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="05f88-118">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="05f88-118">7/7/2015</span></span>  <br/> <span data-ttu-id="05f88-119">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05f88-119">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="05f88-120">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="05f88-120">7/3/2015</span></span>  <br/> <span data-ttu-id="05f88-121">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="05f88-121">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="05f88-122">**To**</span><span class="sxs-lookup"><span data-stu-id="05f88-122">**To**</span></span> <br/> |<span data-ttu-id="05f88-p104">시간 범위의 종료 날짜 및 시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="05f88-p104">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span>  <br/> <span data-ttu-id="05f88-125">2015/7/7 오후 1:00</span><span class="sxs-lookup"><span data-stu-id="05f88-125">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="05f88-p105">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="05f88-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="05f88-128">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="05f88-128">7/7/2015</span></span>  <br/> <span data-ttu-id="05f88-129">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05f88-129">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="05f88-130">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="05f88-130">7/3/2015</span></span>  <br/> <span data-ttu-id="05f88-131">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="05f88-131">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
|<span data-ttu-id="05f88-132">**풀**</span><span class="sxs-lookup"><span data-stu-id="05f88-132">**Pool**</span></span> <br/> |<span data-ttu-id="05f88-p106">등록자 풀 또는 에지 서버의 FQDN(정규화된 도메인 이름)입니다. 개별 풀을 선택하거나 **[모두]** 를 클릭하여 모든 풀에 대한 데이터를 봅니다. 이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="05f88-p106">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click **[All]** to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database. </span></span><br/> |
   
## <a name="metrics"></a><span data-ttu-id="05f88-136">메트릭</span><span class="sxs-lookup"><span data-stu-id="05f88-136">Metrics</span></span>

<span data-ttu-id="05f88-137">다음 표에는 P2P 요약 하위 보고서에 제공된 정보가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05f88-137">The following table lists the information provided in the P2P Summary Subreport.</span></span>
  
<span data-ttu-id="05f88-138">**P2P 요약 하위 보고서 메트릭**</span><span class="sxs-lookup"><span data-stu-id="05f88-138">**P2P Summary Subreport Metrics**</span></span>

|<span data-ttu-id="05f88-139">**이름**</span><span class="sxs-lookup"><span data-stu-id="05f88-139">**Name**</span></span>|<span data-ttu-id="05f88-140">**이 항목에 대한 정렬 가능 여부**</span><span class="sxs-lookup"><span data-stu-id="05f88-140">**Can you sort on this item?**</span></span>|<span data-ttu-id="05f88-141">**설명**</span><span class="sxs-lookup"><span data-stu-id="05f88-141">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="05f88-142">**총 세션**</span><span class="sxs-lookup"><span data-stu-id="05f88-142">**Total sessions**</span></span> <br/> |<span data-ttu-id="05f88-143">아니요</span><span class="sxs-lookup"><span data-stu-id="05f88-143">No</span></span>  <br/> |<span data-ttu-id="05f88-144">성공한 세션, 실패한 세션(예상 오류 및 예기치 않은 오류 모두) 및 분류되지 않은 세션을 포함한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="05f88-144">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span>  <br/> |
|<span data-ttu-id="05f88-145">**실패율**</span><span class="sxs-lookup"><span data-stu-id="05f88-145">**Failure rate**</span></span> <br/> |<span data-ttu-id="05f88-146">아니요</span><span class="sxs-lookup"><span data-stu-id="05f88-146">No</span></span>  <br/> |<span data-ttu-id="05f88-147">실패한 피어 투 피어 세션의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="05f88-147">Percentage of peer-to-peer sessions that failed.</span></span>  <br/> |
|<span data-ttu-id="05f88-148">**형식별 세션(Sessions by Modality)**</span><span class="sxs-lookup"><span data-stu-id="05f88-148">**Sessions by Modality**</span></span> <br/> |<span data-ttu-id="05f88-149">아니요</span><span class="sxs-lookup"><span data-stu-id="05f88-149">No</span></span>  <br/> |<span data-ttu-id="05f88-150">형식(예: 인스턴트 메시징)별로 그룹화된 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="05f88-150">Total number of sessions grouped by modality (for example, instant messaging).</span></span>  <br/> |
|<span data-ttu-id="05f88-151">**형식별 실패율(Failure rate by modality)**</span><span class="sxs-lookup"><span data-stu-id="05f88-151">**Failure rate by modality**</span></span> <br/> |<span data-ttu-id="05f88-152">아니요</span><span class="sxs-lookup"><span data-stu-id="05f88-152">No</span></span>  <br/> |<span data-ttu-id="05f88-153">형식(예: 인스턴트 메시징)별로 그룹화된 총 실패 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="05f88-153">Total number of failed sessions grouped by modality (for example, instant messaging).</span></span>  <br/> |
   

