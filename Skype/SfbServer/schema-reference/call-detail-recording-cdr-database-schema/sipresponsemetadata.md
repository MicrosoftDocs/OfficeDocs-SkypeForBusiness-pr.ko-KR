---
title: SIPResponseMetaData 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: SIPResponseMetaDataTable에는 SIP 응답 코드 목록과 각 코드의 분류 및 정의가 포함 되어 있습니다. 이러한 코드는 SIP 장치 및 SIP 통신 세션에 영향을 주는 이벤트에 대 한 응답으로 생성 됩니다. 예를 들어 응답 코드 403는 SIP 장치가 요청할 때 생성 되지만 서버는 해당 요청을 처리 하는 것을 거절 합니다.
ms.openlocfilehash: eecd8397315b93ebce9e5fad973f1274a6eb763a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196686"
---
# <a name="sipresponsemetadata-table"></a><span data-ttu-id="b9b32-104">SIPResponseMetaData 테이블</span><span class="sxs-lookup"><span data-stu-id="b9b32-104">SIPResponseMetaData table</span></span>
 
<span data-ttu-id="b9b32-105">SIPResponseMetaDataTable에는 SIP 응답 코드 목록과 각 코드의 분류 및 정의가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9b32-105">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="b9b32-106">이러한 코드는 SIP 장치 및 SIP 통신 세션에 영향을 주는 이벤트에 대 한 응답으로 생성 됩니다. 예를 들어 응답 코드 403는 SIP 장치가 요청할 때 생성 되지만 서버는 해당 요청을 처리 하는 것을 거절 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9b32-106">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>
  
<span data-ttu-id="b9b32-107">이 표는 비즈니스용 Skype 서버 2015에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b9b32-107">This table was introduced in Skype for Business Server 2015.</span></span>
  
|<span data-ttu-id="b9b32-108">**열**</span><span class="sxs-lookup"><span data-stu-id="b9b32-108">**Column**</span></span>|<span data-ttu-id="b9b32-109">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="b9b32-109">**Data Type**</span></span>|<span data-ttu-id="b9b32-110">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="b9b32-110">**Key/Index**</span></span>|<span data-ttu-id="b9b32-111">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="b9b32-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b9b32-112">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="b9b32-112">**ResponseCode**</span></span> <br/> |<span data-ttu-id="b9b32-113">int</span><span class="sxs-lookup"><span data-stu-id="b9b32-113">int</span></span>  <br/> |<span data-ttu-id="b9b32-114">주요한</span><span class="sxs-lookup"><span data-stu-id="b9b32-114">Primary</span></span>  <br/> |<span data-ttu-id="b9b32-115">SIP 응답 코드를 나타내는 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b32-115">Numeric value that represents the SIP response code.</span></span>  <br/> |
|<span data-ttu-id="b9b32-116">**클래스만**</span><span class="sxs-lookup"><span data-stu-id="b9b32-116">**Class**</span></span> <br/> |<span data-ttu-id="b9b32-117">int</span><span class="sxs-lookup"><span data-stu-id="b9b32-117">int</span></span>  <br/> || <span data-ttu-id="b9b32-118">응답 코드에 대 한 일반 분류입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b32-118">General classification for the response code.</span></span> <span data-ttu-id="b9b32-119">분류에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9b32-119">Classifications include:</span></span> <br/>  <span data-ttu-id="b9b32-120">1-정보 응답</span><span class="sxs-lookup"><span data-stu-id="b9b32-120">1 - Informational Responses</span></span> <br/>  <span data-ttu-id="b9b32-121">2-성공 응답</span><span class="sxs-lookup"><span data-stu-id="b9b32-121">2 - Successful Responses</span></span> <br/>  <span data-ttu-id="b9b32-122">3-리디렉션 응답</span><span class="sxs-lookup"><span data-stu-id="b9b32-122">3 - Redirection Responses</span></span> <br/>  <span data-ttu-id="b9b32-123">4-클라이언트 오류 응답</span><span class="sxs-lookup"><span data-stu-id="b9b32-123">4 - Client Failure Responses</span></span> <br/>  <span data-ttu-id="b9b32-124">5--서버 실패 응답</span><span class="sxs-lookup"><span data-stu-id="b9b32-124">5 -- Server Failure Responses</span></span> <br/>  <span data-ttu-id="b9b32-125">6-전역 실패 응답</span><span class="sxs-lookup"><span data-stu-id="b9b32-125">6 - Global Failure Response</span></span> <br/> |
|<span data-ttu-id="b9b32-126">**설명**</span><span class="sxs-lookup"><span data-stu-id="b9b32-126">**Description**</span></span> <br/> |<span data-ttu-id="b9b32-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b9b32-127">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="b9b32-128">SIP 응답 코드에 대 한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b32-128">Description of the SIP response code.</span></span> <span data-ttu-id="b9b32-129">예를 들어, 응답 코드 181에는 다음 설명이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9b32-129">For example, response code 181 has the following description:</span></span>  <br/> <span data-ttu-id="b9b32-130">착신 통화 전달 중</span><span class="sxs-lookup"><span data-stu-id="b9b32-130">Call Is Being Forwarded</span></span>  <br/> |
   

