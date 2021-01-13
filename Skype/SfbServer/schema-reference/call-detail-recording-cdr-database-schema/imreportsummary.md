---
title: 비즈니스용 Skype 서버의 IMReportSummary 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: IMReportSummaryTable은 조직에서 진행하는 인스턴트 메시징 세션에 대한 전체 보고서를 제공합니다. 이 표는 Microsoft Lync Server 2013에서 도입된 것입니다.
ms.openlocfilehash: 6a80918376440c13d60e059744d88c09c2705853
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821528"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="49407-104">비즈니스용 Skype 서버의 IMReportSummary 테이블</span><span class="sxs-lookup"><span data-stu-id="49407-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="49407-105">IMReportSummaryTable은 조직에서 진행하는 인스턴트 메시징 세션에 대한 전체 보고서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="49407-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="49407-106">이 표는 Microsoft Lync Server 2013에서 도입된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="49407-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="49407-107">**열**</span><span class="sxs-lookup"><span data-stu-id="49407-107">**Column**</span></span>|<span data-ttu-id="49407-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="49407-108">**Data Type**</span></span>|<span data-ttu-id="49407-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="49407-109">**Key/Index**</span></span>|<span data-ttu-id="49407-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="49407-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="49407-111">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="49407-111">**StartTime**</span></span> <br/> |<span data-ttu-id="49407-112">datetime</span><span class="sxs-lookup"><span data-stu-id="49407-112">datetime</span></span>  <br/> |<span data-ttu-id="49407-113">Primary</span><span class="sxs-lookup"><span data-stu-id="49407-113">Primary</span></span>  <br/> |<span data-ttu-id="49407-114">인스턴트 메시징 세션이 시작된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="49407-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="49407-115">**TimePeriod**</span><span class="sxs-lookup"><span data-stu-id="49407-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="49407-116">char(1)</span><span class="sxs-lookup"><span data-stu-id="49407-116">char(1)</span></span>  <br/> |<span data-ttu-id="49407-117">Primary</span><span class="sxs-lookup"><span data-stu-id="49407-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="49407-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="49407-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="49407-119">nvarchar(257)</span><span class="sxs-lookup"><span data-stu-id="49407-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="49407-120">Primary</span><span class="sxs-lookup"><span data-stu-id="49407-120">Primary</span></span>  <br/> |<span data-ttu-id="49407-121">세션을 호스팅하는 풀의 정규화된 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="49407-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="49407-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="49407-122">**AuthType**</span></span> <br/> |<span data-ttu-id="49407-123">int</span><span class="sxs-lookup"><span data-stu-id="49407-123">int</span></span>  <br/> |<span data-ttu-id="49407-124">Primary</span><span class="sxs-lookup"><span data-stu-id="49407-124">Primary</span></span>  <br/> |<span data-ttu-id="49407-125">통화의 우선 순위(예: 긴급, 일반)입니다.</span><span class="sxs-lookup"><span data-stu-id="49407-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="49407-126">우선 순위 정보는 비즈니스용 Skype 서버 [2015의 CallPriorities](callpriorities.md)테이블에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="49407-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="49407-127">**SessionCount**</span><span class="sxs-lookup"><span data-stu-id="49407-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="49407-128">bigint</span><span class="sxs-lookup"><span data-stu-id="49407-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="49407-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="49407-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="49407-130">bigint</span><span class="sxs-lookup"><span data-stu-id="49407-130">bigint</span></span>  <br/> ||<span data-ttu-id="49407-131">세션 중 교환된 총 인스턴트 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="49407-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

