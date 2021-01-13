---
title: 비즈니스용 Skype 서버의 Mcus 테이블
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
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Mcus 테이블은 지원 테이블입니다. 각 레코드에는 하나의 회의 서비스에 대한 정보가 저장됩니다. 여기에는 IM 회의 서비스 및 전화 통신 회의 서비스(프런트 엔드 서버에서 프로세스로 실행) 및 웹 회의 서비스 및 A/V 회의 서비스가 포함됩니다.
ms.openlocfilehash: fe43bfc747cd08febe00a68925ad520b6add5846
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821428"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="94ac5-105">비즈니스용 Skype 서버의 Mcus 테이블</span><span class="sxs-lookup"><span data-stu-id="94ac5-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="94ac5-106">Mcus 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="94ac5-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="94ac5-107">각 레코드에는 하나의 회의 서비스에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="94ac5-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="94ac5-108">여기에는 IM 회의 서비스 및 전화 통신 회의 서비스(프런트 엔드 서버에서 프로세스로 실행) 및 웹 회의 서비스 및 A/V 회의 서비스가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="94ac5-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="94ac5-109">**열**</span><span class="sxs-lookup"><span data-stu-id="94ac5-109">**Column**</span></span>|<span data-ttu-id="94ac5-110">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="94ac5-110">**Data Type**</span></span>|<span data-ttu-id="94ac5-111">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="94ac5-111">**Key/Index**</span></span>|<span data-ttu-id="94ac5-112">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="94ac5-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="94ac5-113">**McuId**</span><span class="sxs-lookup"><span data-stu-id="94ac5-113">**McuId**</span></span> <br/> |<span data-ttu-id="94ac5-114">int</span><span class="sxs-lookup"><span data-stu-id="94ac5-114">int</span></span>  <br/> |<span data-ttu-id="94ac5-115">Primary</span><span class="sxs-lookup"><span data-stu-id="94ac5-115">Primary</span></span>  <br/> |<span data-ttu-id="94ac5-116">이 회의 서버를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="94ac5-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="94ac5-117">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="94ac5-117">**McuUri**</span></span> <br/> |<span data-ttu-id="94ac5-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="94ac5-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="94ac5-119">**McuTypeId**</span><span class="sxs-lookup"><span data-stu-id="94ac5-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="94ac5-120">inyint</span><span class="sxs-lookup"><span data-stu-id="94ac5-120">inyint</span></span>  <br/> | <span data-ttu-id="94ac5-121">외계인</span><span class="sxs-lookup"><span data-stu-id="94ac5-121">Foreign</span></span> <br/> |<span data-ttu-id="94ac5-122">회의 서버 유형(예: conf:chat(IM용) 또는 conf:audio-video)</span><span class="sxs-lookup"><span data-stu-id="94ac5-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="94ac5-123">자세한 내용은 [UriTypes 테이블을](uritypes.md) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="94ac5-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

