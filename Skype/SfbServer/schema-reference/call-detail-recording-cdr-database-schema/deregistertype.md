---
title: 비즈니스용 Skype 서버의 DeRegisterType 테이블
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
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: DeRegisterType 테이블은 'client initiated', 'registration expired' 또는 'client stopped responding'(클라이언트가 응답하지 않은 경우)을 등록을 끊을 수 있는 사용자 유형 목록을 저장하는 정적 테이블입니다.
ms.openlocfilehash: 388aebc1ac180e1298addd54859cff6759b28be0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816078"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="bb788-103">비즈니스용 Skype 서버의 DeRegisterType 테이블</span><span class="sxs-lookup"><span data-stu-id="bb788-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="bb788-104">DeRegisterType 테이블은 'client initiated', 'registration expired' 또는 'client stopped responding'(클라이언트가 응답하지 않은 경우)을 등록을 끊을 수 있는 사용자 유형 목록을 저장하는 정적 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="bb788-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="bb788-105">**열**</span><span class="sxs-lookup"><span data-stu-id="bb788-105">**Column**</span></span>|<span data-ttu-id="bb788-106">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="bb788-106">**Data Type**</span></span>|<span data-ttu-id="bb788-107">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="bb788-107">**Key/Index**</span></span>|<span data-ttu-id="bb788-108">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="bb788-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bb788-109">**DeRegisterTypeId**</span><span class="sxs-lookup"><span data-stu-id="bb788-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="bb788-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="bb788-110">tinyint</span></span>  <br/> |<span data-ttu-id="bb788-111">Primary</span><span class="sxs-lookup"><span data-stu-id="bb788-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="bb788-112">**DeRegisterReason**</span><span class="sxs-lookup"><span data-stu-id="bb788-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="bb788-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="bb788-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="bb788-114">허용되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bb788-114">Allowed values:</span></span> <br/>  <span data-ttu-id="bb788-115">0 - 알 수 없음</span><span class="sxs-lookup"><span data-stu-id="bb788-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="bb788-116">1 -- 클라이언트가 등록 취소 시작</span><span class="sxs-lookup"><span data-stu-id="bb788-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="bb788-117">2 -- 등록 만료</span><span class="sxs-lookup"><span data-stu-id="bb788-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="bb788-118">3 - 클라이언트 충돌</span><span class="sxs-lookup"><span data-stu-id="bb788-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="bb788-119">4 -- 사용자 특성 변경</span><span class="sxs-lookup"><span data-stu-id="bb788-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="bb788-120">5 - 기본 설정 등록자 변경</span><span class="sxs-lookup"><span data-stu-id="bb788-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="bb788-121">6 -- 레거시 클라이언트가 서바이벌 모드임</span><span class="sxs-lookup"><span data-stu-id="bb788-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   

