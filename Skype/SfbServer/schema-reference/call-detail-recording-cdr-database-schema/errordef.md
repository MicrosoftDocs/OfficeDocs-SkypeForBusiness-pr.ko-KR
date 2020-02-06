---
title: 비즈니스용 Skype 서버 2015의 ErrorDef 테이블
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
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: ErrorDef 테이블에는 발생할 수 있는 각 유형의 오류에 대 한 정보가 저장 됩니다. 각 레코드는 오류 유형 중 하나입니다.
ms.openlocfilehash: f686692bee334c0927b6e8342cfb7152b3e54f0c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815236"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="7f12e-104">비즈니스용 Skype 서버 2015의 ErrorDef 테이블</span><span class="sxs-lookup"><span data-stu-id="7f12e-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7f12e-105">ErrorDef 테이블에는 발생할 수 있는 각 유형의 오류에 대 한 정보가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f12e-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="7f12e-106">각 레코드는 오류 유형 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="7f12e-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="7f12e-107">**열**</span><span class="sxs-lookup"><span data-stu-id="7f12e-107">**Column**</span></span>|<span data-ttu-id="7f12e-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="7f12e-108">**Data Type**</span></span>|<span data-ttu-id="7f12e-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="7f12e-109">**Key/Index**</span></span>|<span data-ttu-id="7f12e-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="7f12e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7f12e-111">**ErrorId**</span><span class="sxs-lookup"><span data-stu-id="7f12e-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="7f12e-112">int</span><span class="sxs-lookup"><span data-stu-id="7f12e-112">int</span></span>  <br/> |<span data-ttu-id="7f12e-113">주요한</span><span class="sxs-lookup"><span data-stu-id="7f12e-113">Primary</span></span>  <br/> |<span data-ttu-id="7f12e-114">이 유형의 오류를 식별 하는 고유 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="7f12e-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="7f12e-115">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="7f12e-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="7f12e-116">int</span><span class="sxs-lookup"><span data-stu-id="7f12e-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="7f12e-117">이 오류와 연결 된 표준 SIP 응답 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="7f12e-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="7f12e-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="7f12e-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="7f12e-119">int</span><span class="sxs-lookup"><span data-stu-id="7f12e-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="7f12e-120">Microsoft 진단 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7f12e-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="7f12e-121">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="7f12e-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="7f12e-122">Int</span><span class="sxs-lookup"><span data-stu-id="7f12e-122">Int</span></span>  <br/> |<span data-ttu-id="7f12e-123">외부</span><span class="sxs-lookup"><span data-stu-id="7f12e-123">Foreign</span></span>  <br/> |<span data-ttu-id="7f12e-124">통화의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="7f12e-124">Type of the call.</span></span> <span data-ttu-id="7f12e-125">자세한 내용은 [비즈니스용 Skype 서버 2015의 Calltype 테이블](calltype.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7f12e-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="7f12e-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="7f12e-126">**RequestType**</span></span> <br/> |<span data-ttu-id="7f12e-127">varbinary (33)</span><span class="sxs-lookup"><span data-stu-id="7f12e-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="7f12e-128">실패 한 요청의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="7f12e-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="7f12e-129">이 구문을 사용 하 여이 데이터를 텍스트 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f12e-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="7f12e-130">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="7f12e-130">**ContentType**</span></span> <br/> |<span data-ttu-id="7f12e-131">varbinary (257)</span><span class="sxs-lookup"><span data-stu-id="7f12e-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="7f12e-132">실패 한 요청의 콘텐츠 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7f12e-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="7f12e-133">이 데이터는이 syntaxt를 사용 하 여 텍스트 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f12e-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

