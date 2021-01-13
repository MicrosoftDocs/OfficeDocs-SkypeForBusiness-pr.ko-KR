---
title: ProgressReport 보기
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
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: ProgressReport 보기에는 완료된 세션에 대한 정보가 저장됩니다. 진행률 보고서는 Lync Server 2013에서 진단 목적으로 유용할 수 있는 통화 및 세션에만 기록됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
ms.openlocfilehash: 6cc8295e73463fff9d4913efbf9d4844f9316149
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823188"
---
# <a name="progressreport-view"></a><span data-ttu-id="8bf13-105">ProgressReport 보기</span><span class="sxs-lookup"><span data-stu-id="8bf13-105">ProgressReport view</span></span>
 
<span data-ttu-id="8bf13-106">ProgressReport 보기에는 완료된 세션에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bf13-106">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="8bf13-107">진행률 보고서는 Lync Server 2013에서 진단 목적으로 유용할 수 있는 통화 및 세션에만 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bf13-107">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="8bf13-108">이 보기는 Microsoft Lync Server 2013에서 도입했습니다.</span><span class="sxs-lookup"><span data-stu-id="8bf13-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8bf13-109">ErrorTime, ErrorReportSeq 및 ProgressReportSeq 필드는 반드시 오류를 참조하는 것이 아니라 통화 또는 메시지의 상태를 나타내는 메시지에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="8bf13-109">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don't necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span> 
  
|<span data-ttu-id="8bf13-110">**열**</span><span class="sxs-lookup"><span data-stu-id="8bf13-110">**Column**</span></span>|<span data-ttu-id="8bf13-111">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="8bf13-111">**Data Type**</span></span>|<span data-ttu-id="8bf13-112">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="8bf13-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8bf13-113">**ErrorTime**</span><span class="sxs-lookup"><span data-stu-id="8bf13-113">**ErrorTime**</span></span> <br/> |<span data-ttu-id="8bf13-114">datetime</span><span class="sxs-lookup"><span data-stu-id="8bf13-114">datetime</span></span>  <br/> |<span data-ttu-id="8bf13-p103">오류가 발생한 시간입니다. ErrorReportSeq와 함께 오류를 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bf13-p103">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="8bf13-117">**ErrorReportSeq**</span><span class="sxs-lookup"><span data-stu-id="8bf13-117">**ErrorReportSeq**</span></span> <br/> |<span data-ttu-id="8bf13-118">int</span><span class="sxs-lookup"><span data-stu-id="8bf13-118">int</span></span>  <br/> |<span data-ttu-id="8bf13-p104">오류를 식별하기 위한 ID 번호입니다. ErrorTime과 함께 오류를 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bf13-p104">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="8bf13-121">**ProgressReportSeq**</span><span class="sxs-lookup"><span data-stu-id="8bf13-121">**ProgressReportSeq**</span></span> <br/> |<span data-ttu-id="8bf13-122">int</span><span class="sxs-lookup"><span data-stu-id="8bf13-122">int</span></span>  <br/> |<span data-ttu-id="8bf13-123">진행률 보고서를 식별하는 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8bf13-123">ID to identify the progress report.</span></span> <span data-ttu-id="8bf13-124">동일한 오류 보고서의 진행률 보고서를 구분하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bf13-124">Used to distinguish progress reports of the same error report.</span></span>  <br/> |
|<span data-ttu-id="8bf13-125">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="8bf13-125">**MsDiagId**</span></span> <br/> |<span data-ttu-id="8bf13-126">int</span><span class="sxs-lookup"><span data-stu-id="8bf13-126">int</span></span>  <br/> |<span data-ttu-id="8bf13-127">오류 보고서의 진단 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8bf13-127">Diagnostic ID for the error report.</span></span>  <br/> |
|<span data-ttu-id="8bf13-128">**원본**</span><span class="sxs-lookup"><span data-stu-id="8bf13-128">**Source**</span></span> <br/> |<span data-ttu-id="8bf13-129">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8bf13-129">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="8bf13-130">오류를 유발한 서버 이름입니다(보고서가 서버 구성 요소에서 전송된 경우).</span><span class="sxs-lookup"><span data-stu-id="8bf13-130">Name of server that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="8bf13-131">**응용 프로그램**</span><span class="sxs-lookup"><span data-stu-id="8bf13-131">**Application**</span></span> <br/> |<span data-ttu-id="8bf13-132">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8bf13-132">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="8bf13-133">오류를 유발한 응용 프로그램 이름입니다(보고서가 서버 구성 요소에서 전송된 경우).</span><span class="sxs-lookup"><span data-stu-id="8bf13-133">Name of application that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="8bf13-134">**TelemetryId**</span><span class="sxs-lookup"><span data-stu-id="8bf13-134">**TelemetryId**</span></span> <br/> |<span data-ttu-id="8bf13-135">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="8bf13-135">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="8bf13-136">회의에 포함된 서로 다른 구성 요소의 참가 시간 정보와 연결된 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8bf13-136">Unique identifier correlating join time information for the different components involved in a conference.</span></span>  <br/> |
|<span data-ttu-id="8bf13-137">**SessionSetupTime**</span><span class="sxs-lookup"><span data-stu-id="8bf13-137">**SessionSetupTime**</span></span> <br/> |<span data-ttu-id="8bf13-138">int</span><span class="sxs-lookup"><span data-stu-id="8bf13-138">int</span></span>  <br/> |<span data-ttu-id="8bf13-139">회의에 참가하는 특정 구성 요소에 필요한 시간(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="8bf13-139">Time (in milliseconds) required for a specific component to join a conference.</span></span>  <br/> |
|<span data-ttu-id="8bf13-140">**MsDiagHeader**</span><span class="sxs-lookup"><span data-stu-id="8bf13-140">**MsDiagHeader**</span></span> <br/> |<span data-ttu-id="8bf13-141">varchar(max)</span><span class="sxs-lookup"><span data-stu-id="8bf13-141">varchar(max)</span></span>  <br/> |<span data-ttu-id="8bf13-142">추가 오류 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="8bf13-142">Additional error information.</span></span>  <br/> |
   

