---
title: Dialog 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: Dialog 테이블은 각 레코드가 하나의 SIP(Session Initiation Protocol) 대화를 나타내는 지원 테이블입니다.
ms.openlocfilehash: 05d9519c9aef20b8c82d904a9d5718a4de8c092c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815848"
---
# <a name="dialog-table"></a><span data-ttu-id="8b4d3-103">Dialog 테이블</span><span class="sxs-lookup"><span data-stu-id="8b4d3-103">Dialog table</span></span>
 
<span data-ttu-id="8b4d3-104">Dialog 테이블은 각 레코드가 하나의 SIP(Session Initiation Protocol) 대화를 나타내는 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="8b4d3-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="8b4d3-105">**열**</span><span class="sxs-lookup"><span data-stu-id="8b4d3-105">**Column**</span></span>|<span data-ttu-id="8b4d3-106">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="8b4d3-106">**Data Type**</span></span>|<span data-ttu-id="8b4d3-107">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="8b4d3-107">**Key/Index**</span></span>|<span data-ttu-id="8b4d3-108">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="8b4d3-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8b4d3-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="8b4d3-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="8b4d3-110">datetime</span><span class="sxs-lookup"><span data-stu-id="8b4d3-110">datetime</span></span>  <br/> |<span data-ttu-id="8b4d3-111">Primary</span><span class="sxs-lookup"><span data-stu-id="8b4d3-111">Primary</span></span>  <br/> |<span data-ttu-id="8b4d3-p101">QoE(체감 품질) 에이전트가 발신자 또는 수신자로부터 첫 번째 보고서를 받는 시간입니다. SessionSeq와 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b4d3-p101">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee. Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="8b4d3-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="8b4d3-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="8b4d3-115">int</span><span class="sxs-lookup"><span data-stu-id="8b4d3-115">int</span></span>  <br/> |<span data-ttu-id="8b4d3-116">Primary</span><span class="sxs-lookup"><span data-stu-id="8b4d3-116">Primary</span></span>  <br/> |<span data-ttu-id="8b4d3-117">ConferenceDateTime이 동일할 때 세션을 구분하기 위한 시퀀스 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="8b4d3-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="8b4d3-118">**DialogID**</span><span class="sxs-lookup"><span data-stu-id="8b4d3-118">**DialogID**</span></span> <br/> |<span data-ttu-id="8b4d3-119">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="8b4d3-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="8b4d3-120">전역으로 고유한 대화 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8b4d3-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="8b4d3-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="8b4d3-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="8b4d3-122">int</span><span class="sxs-lookup"><span data-stu-id="8b4d3-122">int</span></span>  <br/> |<span data-ttu-id="8b4d3-123">index</span><span class="sxs-lookup"><span data-stu-id="8b4d3-123">index</span></span>  <br/> |<span data-ttu-id="8b4d3-124">대화 ID의 체크섬입니다.</span><span class="sxs-lookup"><span data-stu-id="8b4d3-124">Checksum of the Dialog ID.</span></span>  <br/> |
   

