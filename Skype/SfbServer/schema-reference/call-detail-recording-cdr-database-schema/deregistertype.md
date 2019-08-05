---
title: 비즈니스용 Skype 서버 2015의 DeRegisterType 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: DeRegisterType 테이블은 ' 클라이언트 시작 ', ' 등록 만료 ' 또는 ' 클라이언트가 응답을 중지 했습니다. ' 등 사용 가능한 사용자의 등록 취소 형식 목록을 저장 하는 정적 테이블입니다.
ms.openlocfilehash: 794f8f98ffe20cd69b63fd2084fee38ed055d40f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196767"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="82a0b-103">비즈니스용 Skype 서버 2015의 DeRegisterType 테이블</span><span class="sxs-lookup"><span data-stu-id="82a0b-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="82a0b-104">DeRegisterType 테이블은 ' 클라이언트 시작 ', ' 등록 만료 ' 또는 ' 클라이언트가 응답을 중지 했습니다. ' 등 사용 가능한 사용자의 등록 취소 형식 목록을 저장 하는 정적 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="82a0b-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="82a0b-105">**열**</span><span class="sxs-lookup"><span data-stu-id="82a0b-105">**Column**</span></span>|<span data-ttu-id="82a0b-106">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="82a0b-106">**Data Type**</span></span>|<span data-ttu-id="82a0b-107">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="82a0b-107">**Key/Index**</span></span>|<span data-ttu-id="82a0b-108">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="82a0b-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="82a0b-109">**DeRegisterTypeId**</span><span class="sxs-lookup"><span data-stu-id="82a0b-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="82a0b-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="82a0b-110">tinyint</span></span>  <br/> |<span data-ttu-id="82a0b-111">주요한</span><span class="sxs-lookup"><span data-stu-id="82a0b-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="82a0b-112">**DeRegisterReason**</span><span class="sxs-lookup"><span data-stu-id="82a0b-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="82a0b-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="82a0b-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="82a0b-114">허용 되는 값:</span><span class="sxs-lookup"><span data-stu-id="82a0b-114">Allowed values:</span></span> <br/>  <span data-ttu-id="82a0b-115">0--알 수 없음</span><span class="sxs-lookup"><span data-stu-id="82a0b-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="82a0b-116">1--클라이언트에서 초기화 된 등록 취소</span><span class="sxs-lookup"><span data-stu-id="82a0b-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="82a0b-117">2--등록이 만료 됨</span><span class="sxs-lookup"><span data-stu-id="82a0b-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="82a0b-118">3-클라이언트가 충돌 합니다.</span><span class="sxs-lookup"><span data-stu-id="82a0b-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="82a0b-119">4--사용자 특성이 변경 됨</span><span class="sxs-lookup"><span data-stu-id="82a0b-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="82a0b-120">5-기본 등록 기관 변경</span><span class="sxs-lookup"><span data-stu-id="82a0b-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="82a0b-121">6--생존 모드의 레거시 클라이언트</span><span class="sxs-lookup"><span data-stu-id="82a0b-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   

