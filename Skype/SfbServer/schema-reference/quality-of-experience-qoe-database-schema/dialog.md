---
title: Dialog 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: 대화 상자 테이블은 지원 테이블입니다. 각 레코드는 하나의 SIP (세션 초기화 프로토콜) 대화 상자를 나타냅니다.
ms.openlocfilehash: e6bbaa3c40ebf53c5fd9fc410acca7779128bf39
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196568"
---
# <a name="dialog-table"></a><span data-ttu-id="3c469-103">Dialog 테이블</span><span class="sxs-lookup"><span data-stu-id="3c469-103">Dialog table</span></span>
 
<span data-ttu-id="3c469-104">대화 상자 테이블은 지원 테이블입니다. 각 레코드는 하나의 SIP (세션 초기화 프로토콜) 대화 상자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3c469-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="3c469-105">**열**</span><span class="sxs-lookup"><span data-stu-id="3c469-105">**Column**</span></span>|<span data-ttu-id="3c469-106">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="3c469-106">**Data Type**</span></span>|<span data-ttu-id="3c469-107">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="3c469-107">**Key/Index**</span></span>|<span data-ttu-id="3c469-108">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="3c469-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3c469-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="3c469-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="3c469-110">dmtf</span><span class="sxs-lookup"><span data-stu-id="3c469-110">datetime</span></span>  <br/> |<span data-ttu-id="3c469-111">주요한</span><span class="sxs-lookup"><span data-stu-id="3c469-111">Primary</span></span>  <br/> |<span data-ttu-id="3c469-112">체감 품질 (고급 품질) 에이전트가 호출자 또는 호출 수신자 중 첫 번째 보고서를 받는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="3c469-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="3c469-113">세션을 고유 하 게 식별 하는 SessionSeq와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c469-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="3c469-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="3c469-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="3c469-115">int</span><span class="sxs-lookup"><span data-stu-id="3c469-115">int</span></span>  <br/> |<span data-ttu-id="3c469-116">주요한</span><span class="sxs-lookup"><span data-stu-id="3c469-116">Primary</span></span>  <br/> |<span data-ttu-id="3c469-117">동일한 ConferenceDateTime 있을 때 세션을 구분 하는 시퀀스 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="3c469-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="3c469-118">**DialogID**</span><span class="sxs-lookup"><span data-stu-id="3c469-118">**DialogID**</span></span> <br/> |<span data-ttu-id="3c469-119">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="3c469-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="3c469-120">전역으로 고유한 대화 상자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3c469-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="3c469-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="3c469-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="3c469-122">int</span><span class="sxs-lookup"><span data-stu-id="3c469-122">int</span></span>  <br/> |<span data-ttu-id="3c469-123">색인</span><span class="sxs-lookup"><span data-stu-id="3c469-123">index</span></span>  <br/> |<span data-ttu-id="3c469-124">대화 상자 ID의 체크섬입니다.</span><span class="sxs-lookup"><span data-stu-id="3c469-124">Checksum of the Dialog ID.</span></span>  <br/> |
   

