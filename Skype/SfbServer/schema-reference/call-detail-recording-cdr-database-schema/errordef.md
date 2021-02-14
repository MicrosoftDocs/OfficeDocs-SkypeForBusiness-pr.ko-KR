---
title: 비즈니스용 Skype 서버의 ErrorDef 테이블
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
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: ErrorDef 테이블에는 발생할 수 있는 각 오류 유형에 대한 정보가 저장됩니다. 각 레코드는 하나의 오류 유형입니다.
ms.openlocfilehash: 50d7b76e1fc7edb53fbe0b299673b7281a394463
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821728"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="97e16-104">비즈니스용 Skype 서버의 ErrorDef 테이블</span><span class="sxs-lookup"><span data-stu-id="97e16-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="97e16-105">ErrorDef 테이블에는 발생할 수 있는 각 오류 유형에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="97e16-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="97e16-106">각 레코드는 하나의 오류 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="97e16-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="97e16-107">**열**</span><span class="sxs-lookup"><span data-stu-id="97e16-107">**Column**</span></span>|<span data-ttu-id="97e16-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="97e16-108">**Data Type**</span></span>|<span data-ttu-id="97e16-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="97e16-109">**Key/Index**</span></span>|<span data-ttu-id="97e16-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="97e16-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="97e16-111">**ErrorId**</span><span class="sxs-lookup"><span data-stu-id="97e16-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="97e16-112">int</span><span class="sxs-lookup"><span data-stu-id="97e16-112">int</span></span>  <br/> |<span data-ttu-id="97e16-113">Primary</span><span class="sxs-lookup"><span data-stu-id="97e16-113">Primary</span></span>  <br/> |<span data-ttu-id="97e16-114">이 유형의 오류를 식별하는 고유 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="97e16-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="97e16-115">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="97e16-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="97e16-116">int</span><span class="sxs-lookup"><span data-stu-id="97e16-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="97e16-117">이 오류와 관련된 표준 SIP 응답 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="97e16-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="97e16-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="97e16-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="97e16-119">int</span><span class="sxs-lookup"><span data-stu-id="97e16-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="97e16-120">Microsoft 진단 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="97e16-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="97e16-121">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="97e16-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="97e16-122">임계값</span><span class="sxs-lookup"><span data-stu-id="97e16-122">Int</span></span>  <br/> |<span data-ttu-id="97e16-123">외계인</span><span class="sxs-lookup"><span data-stu-id="97e16-123">Foreign</span></span>  <br/> |<span data-ttu-id="97e16-124">통화 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="97e16-124">Type of the call.</span></span> <span data-ttu-id="97e16-125">자세한 내용은 [비즈니스용 Skype 서버 2015의 CallType](calltype.md) 테이블을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97e16-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="97e16-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="97e16-126">**RequestType**</span></span> <br/> |<span data-ttu-id="97e16-127">varbinary(33)</span><span class="sxs-lookup"><span data-stu-id="97e16-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="97e16-128">실패한 요청 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="97e16-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="97e16-129">이 데이터는 다음 구문을 사용하여 텍스트 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97e16-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="97e16-130">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="97e16-130">**ContentType**</span></span> <br/> |<span data-ttu-id="97e16-131">varbinary(257)</span><span class="sxs-lookup"><span data-stu-id="97e16-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="97e16-132">실패한 요청의 콘텐츠 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="97e16-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="97e16-133">이 데이터는 다음 구문을 사용하여 텍스트 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97e16-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

