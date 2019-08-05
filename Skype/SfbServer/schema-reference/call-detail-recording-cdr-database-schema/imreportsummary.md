---
title: 비즈니스용 Skype 서버 2015의 IMReportSummary 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: Imreport요약 테이블은 조직에 보관 된 인스턴트 메시징 세션에 대 한 전반적인 보고서를 제공 합니다. 이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: 647b8dc3e48e56d126a65f524de90954b7aeca8f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196736"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="90afc-104">비즈니스용 Skype 서버 2015의 IMReportSummary 테이블</span><span class="sxs-lookup"><span data-stu-id="90afc-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="90afc-105">Imreport요약 테이블은 조직에 보관 된 인스턴트 메시징 세션에 대 한 전반적인 보고서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="90afc-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="90afc-106">이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="90afc-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="90afc-107">**열**</span><span class="sxs-lookup"><span data-stu-id="90afc-107">**Column**</span></span>|<span data-ttu-id="90afc-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="90afc-108">**Data Type**</span></span>|<span data-ttu-id="90afc-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="90afc-109">**Key/Index**</span></span>|<span data-ttu-id="90afc-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="90afc-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="90afc-111">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="90afc-111">**StartTime**</span></span> <br/> |<span data-ttu-id="90afc-112">dmtf</span><span class="sxs-lookup"><span data-stu-id="90afc-112">datetime</span></span>  <br/> |<span data-ttu-id="90afc-113">주요한</span><span class="sxs-lookup"><span data-stu-id="90afc-113">Primary</span></span>  <br/> |<span data-ttu-id="90afc-114">인스턴트 메시징 세션이 시작 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="90afc-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="90afc-115">**TimePeriod**</span><span class="sxs-lookup"><span data-stu-id="90afc-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="90afc-116">char (1)</span><span class="sxs-lookup"><span data-stu-id="90afc-116">char(1)</span></span>  <br/> |<span data-ttu-id="90afc-117">주요한</span><span class="sxs-lookup"><span data-stu-id="90afc-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="90afc-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="90afc-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="90afc-119">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="90afc-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="90afc-120">주요한</span><span class="sxs-lookup"><span data-stu-id="90afc-120">Primary</span></span>  <br/> |<span data-ttu-id="90afc-121">세션을 호스트 하는 풀의 정규화 된 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="90afc-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="90afc-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="90afc-122">**AuthType**</span></span> <br/> |<span data-ttu-id="90afc-123">int</span><span class="sxs-lookup"><span data-stu-id="90afc-123">int</span></span>  <br/> |<span data-ttu-id="90afc-124">주요한</span><span class="sxs-lookup"><span data-stu-id="90afc-124">Primary</span></span>  <br/> |<span data-ttu-id="90afc-125">우선 순위 (예: 긴급 또는 비 긴급 통화)</span><span class="sxs-lookup"><span data-stu-id="90afc-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="90afc-126">우선 순위 정보는 비즈니스용 [Skype 서버 2015의 callpriorities 테이블](callpriorities.md)에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="90afc-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="90afc-127">**SessionCount**</span><span class="sxs-lookup"><span data-stu-id="90afc-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="90afc-128">bigint</span><span class="sxs-lookup"><span data-stu-id="90afc-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="90afc-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="90afc-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="90afc-130">bigint</span><span class="sxs-lookup"><span data-stu-id="90afc-130">bigint</span></span>  <br/> ||<span data-ttu-id="90afc-131">세션 중에 교환 된 총 인스턴트 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="90afc-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

