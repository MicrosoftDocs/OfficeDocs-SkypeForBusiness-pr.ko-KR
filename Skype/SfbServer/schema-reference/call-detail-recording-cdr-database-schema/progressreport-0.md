---
title: ProgressReport 보기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: ProgressReport 보기는 완료 된 세션에 대 한 정보를 저장 합니다. 진행률 보고서는 Lync Server 2013이 진단 목적에 유용할 수 있는 통화 및 세션에 대해서만 기록 됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: c07b9db8ebd9f898ab9d8feb5b07c4723209522c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814986"
---
# <a name="progressreport-view"></a><span data-ttu-id="0680b-105">ProgressReport 보기</span><span class="sxs-lookup"><span data-stu-id="0680b-105">ProgressReport view</span></span>
 
<span data-ttu-id="0680b-106">ProgressReport 보기는 완료 된 세션에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="0680b-106">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="0680b-107">진행률 보고서는 Lync Server 2013이 진단 목적에 유용할 수 있는 통화 및 세션에 대해서만 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0680b-107">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="0680b-108">이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0680b-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0680b-109">ErrorTime, ErrorReportSeq 및 ProgressReportSeq 필드는 반드시 오류를 의미 하지는 않으며 호출 상태를 나타내는 메시지에만 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0680b-109">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don't necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span> 
  
|<span data-ttu-id="0680b-110">**열**</span><span class="sxs-lookup"><span data-stu-id="0680b-110">**Column**</span></span>|<span data-ttu-id="0680b-111">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="0680b-111">**Data Type**</span></span>|<span data-ttu-id="0680b-112">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="0680b-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0680b-113">**ErrorTime**</span><span class="sxs-lookup"><span data-stu-id="0680b-113">**ErrorTime**</span></span> <br/> |<span data-ttu-id="0680b-114">dmtf</span><span class="sxs-lookup"><span data-stu-id="0680b-114">datetime</span></span>  <br/> |<span data-ttu-id="0680b-115">오류가 발생 한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="0680b-115">Time of error occurred.</span></span> <span data-ttu-id="0680b-116">오류를 고유 하 게 식별 하는 ErrorReportSeq와 함께 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0680b-116">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="0680b-117">**ErrorReportSeq**</span><span class="sxs-lookup"><span data-stu-id="0680b-117">**ErrorReportSeq**</span></span> <br/> |<span data-ttu-id="0680b-118">int</span><span class="sxs-lookup"><span data-stu-id="0680b-118">int</span></span>  <br/> |<span data-ttu-id="0680b-119">오류를 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="0680b-119">ID number to identify the error.</span></span> <span data-ttu-id="0680b-120">오류를 고유 하 게 식별 하는 ErrorTime과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0680b-120">Used in conjunction with ErrorTime to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="0680b-121">**ProgressReportSeq**</span><span class="sxs-lookup"><span data-stu-id="0680b-121">**ProgressReportSeq**</span></span> <br/> |<span data-ttu-id="0680b-122">int</span><span class="sxs-lookup"><span data-stu-id="0680b-122">int</span></span>  <br/> |<span data-ttu-id="0680b-123">진행률 보고서를 식별 하는 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0680b-123">ID to identify the progress report.</span></span> <span data-ttu-id="0680b-124">같은 오류 보고서의 진행률 보고서를 구분 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0680b-124">Used to distinguish progress reports of the same error report.</span></span>  <br/> |
|<span data-ttu-id="0680b-125">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="0680b-125">**MsDiagId**</span></span> <br/> |<span data-ttu-id="0680b-126">int</span><span class="sxs-lookup"><span data-stu-id="0680b-126">int</span></span>  <br/> |<span data-ttu-id="0680b-127">오류 보고서의 진단 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0680b-127">Diagnostic ID for the error report.</span></span>  <br/> |
|<span data-ttu-id="0680b-128">**Source**</span><span class="sxs-lookup"><span data-stu-id="0680b-128">**Source**</span></span> <br/> |<span data-ttu-id="0680b-129">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0680b-129">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0680b-130">오류를 발생 시킨 서버의 이름입니다 (보고서가 서버 구성 요소에서 전송 된 경우).</span><span class="sxs-lookup"><span data-stu-id="0680b-130">Name of server that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="0680b-131">**응용 프로그램**</span><span class="sxs-lookup"><span data-stu-id="0680b-131">**Application**</span></span> <br/> |<span data-ttu-id="0680b-132">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0680b-132">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0680b-133">오류를 발생 시킨 응용 프로그램의 이름입니다 (보고서가 서버 구성 요소에서 전송 된 경우).</span><span class="sxs-lookup"><span data-stu-id="0680b-133">Name of application that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="0680b-134">**TelemetryId**</span><span class="sxs-lookup"><span data-stu-id="0680b-134">**TelemetryId**</span></span> <br/> |<span data-ttu-id="0680b-135">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="0680b-135">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="0680b-136">고유한 식별자는 회의에 관련 된 다양 한 구성 요소에 대 한 조인 시간 정보를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="0680b-136">Unique identifier correlating join time information for the different components involved in a conference.</span></span>  <br/> |
|<span data-ttu-id="0680b-137">**SessionSetupTime 시간**</span><span class="sxs-lookup"><span data-stu-id="0680b-137">**SessionSetupTime**</span></span> <br/> |<span data-ttu-id="0680b-138">int</span><span class="sxs-lookup"><span data-stu-id="0680b-138">int</span></span>  <br/> |<span data-ttu-id="0680b-139">특정 구성 요소가 컨퍼런스에 참가 하는 데 필요한 시간 (밀리초 단위)입니다.</span><span class="sxs-lookup"><span data-stu-id="0680b-139">Time (in milliseconds) required for a specific component to join a conference.</span></span>  <br/> |
|<span data-ttu-id="0680b-140">**MsDiagHeader**</span><span class="sxs-lookup"><span data-stu-id="0680b-140">**MsDiagHeader**</span></span> <br/> |<span data-ttu-id="0680b-141">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="0680b-141">varchar(max)</span></span>  <br/> |<span data-ttu-id="0680b-142">추가 오류 정보.</span><span class="sxs-lookup"><span data-stu-id="0680b-142">Additional error information.</span></span>  <br/> |
   

