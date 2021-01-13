---
title: SIPResponseMetaData 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: SIPResponseMetaDataTable에는 SIP 응답 코드 목록과 이러한 각 코드의 분류 및 정의가 포함되어 있습니다. 이러한 코드는 SIP 장치 및 SIP 통신 세션에 영향을 주는 이벤트에 응답하여 생성됩니다. 예를 들어 응답 코드 403은 SIP 장치가 요청을 할 때 생성되지만 서버는 해당 요청을 수락하지 않습니다.
ms.openlocfilehash: 3d6714e9c5b5c154d19381fad33821b02ec8a73e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809928"
---
# <a name="sipresponsemetadata-table"></a><span data-ttu-id="f8acb-104">SIPResponseMetaData 테이블</span><span class="sxs-lookup"><span data-stu-id="f8acb-104">SIPResponseMetaData table</span></span>
 
<span data-ttu-id="f8acb-105">SIPResponseMetaDataTable에는 SIP 응답 코드 목록과 이러한 각 코드의 분류 및 정의가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8acb-105">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="f8acb-106">이러한 코드는 SIP 장치 및 SIP 통신 세션에 영향을 주는 이벤트에 응답하여 생성됩니다. 예를 들어 응답 코드 403은 SIP 장치가 요청을 할 때 생성되지만 서버는 해당 요청을 수락하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f8acb-106">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>
  
<span data-ttu-id="f8acb-107">이 표는 비즈니스용 Skype 서버 2015에서 도입된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f8acb-107">This table was introduced in Skype for Business Server 2015.</span></span>
  
|<span data-ttu-id="f8acb-108">**열**</span><span class="sxs-lookup"><span data-stu-id="f8acb-108">**Column**</span></span>|<span data-ttu-id="f8acb-109">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="f8acb-109">**Data Type**</span></span>|<span data-ttu-id="f8acb-110">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="f8acb-110">**Key/Index**</span></span>|<span data-ttu-id="f8acb-111">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="f8acb-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f8acb-112">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="f8acb-112">**ResponseCode**</span></span> <br/> |<span data-ttu-id="f8acb-113">int</span><span class="sxs-lookup"><span data-stu-id="f8acb-113">int</span></span>  <br/> |<span data-ttu-id="f8acb-114">Primary</span><span class="sxs-lookup"><span data-stu-id="f8acb-114">Primary</span></span>  <br/> |<span data-ttu-id="f8acb-115">SIP 응답 코드를 나타내는 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f8acb-115">Numeric value that represents the SIP response code.</span></span>  <br/> |
|<span data-ttu-id="f8acb-116">**클래스**</span><span class="sxs-lookup"><span data-stu-id="f8acb-116">**Class**</span></span> <br/> |<span data-ttu-id="f8acb-117">int</span><span class="sxs-lookup"><span data-stu-id="f8acb-117">int</span></span>  <br/> || <span data-ttu-id="f8acb-118">응답 코드에 대한 일반 분류입니다.</span><span class="sxs-lookup"><span data-stu-id="f8acb-118">General classification for the response code.</span></span> <span data-ttu-id="f8acb-119">분류에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8acb-119">Classifications include:</span></span> <br/>  <span data-ttu-id="f8acb-120">1 - 정보 응답</span><span class="sxs-lookup"><span data-stu-id="f8acb-120">1 - Informational Responses</span></span> <br/>  <span data-ttu-id="f8acb-121">2 - 성공적인 응답</span><span class="sxs-lookup"><span data-stu-id="f8acb-121">2 - Successful Responses</span></span> <br/>  <span data-ttu-id="f8acb-122">3 - 리디렉션 응답</span><span class="sxs-lookup"><span data-stu-id="f8acb-122">3 - Redirection Responses</span></span> <br/>  <span data-ttu-id="f8acb-123">4 - 클라이언트 오류 응답</span><span class="sxs-lookup"><span data-stu-id="f8acb-123">4 - Client Failure Responses</span></span> <br/>  <span data-ttu-id="f8acb-124">5 -- 서버 오류 응답</span><span class="sxs-lookup"><span data-stu-id="f8acb-124">5 -- Server Failure Responses</span></span> <br/>  <span data-ttu-id="f8acb-125">6 - 전역 오류 응답</span><span class="sxs-lookup"><span data-stu-id="f8acb-125">6 - Global Failure Response</span></span> <br/> |
|<span data-ttu-id="f8acb-126">**설명**</span><span class="sxs-lookup"><span data-stu-id="f8acb-126">**Description**</span></span> <br/> |<span data-ttu-id="f8acb-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f8acb-127">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="f8acb-128">SIP 응답 코드에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="f8acb-128">Description of the SIP response code.</span></span> <span data-ttu-id="f8acb-129">예를 들어 응답 코드 181에는 다음 설명이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8acb-129">For example, response code 181 has the following description:</span></span>  <br/> <span data-ttu-id="f8acb-130">통화가 전달되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8acb-130">Call Is Being Forwarded</span></span>  <br/> |
   

