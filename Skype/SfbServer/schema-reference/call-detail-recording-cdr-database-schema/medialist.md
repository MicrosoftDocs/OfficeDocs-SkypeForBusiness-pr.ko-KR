---
title: MediaList 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: MediaList 테이블은 다양 한 미디어 유형의 목록을 저장 하는 정적 테이블입니다.
ms.openlocfilehash: 308a9eee57089a02b8e3ff9924e0d9d34162f33e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196715"
---
# <a name="medialist-table"></a><span data-ttu-id="327d3-103">MediaList 테이블</span><span class="sxs-lookup"><span data-stu-id="327d3-103">MediaList table</span></span>
 
<span data-ttu-id="327d3-104">MediaList 테이블은 다양 한 미디어 유형의 목록을 저장 하는 정적 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="327d3-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="327d3-105">**열**</span><span class="sxs-lookup"><span data-stu-id="327d3-105">**Column**</span></span>|<span data-ttu-id="327d3-106">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="327d3-106">**Data Type**</span></span>|<span data-ttu-id="327d3-107">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="327d3-107">**Key/Index**</span></span>|<span data-ttu-id="327d3-108">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="327d3-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="327d3-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="327d3-109">**MediaId**</span></span> <br/> |<span data-ttu-id="327d3-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="327d3-110">tinyint</span></span>  <br/> |<span data-ttu-id="327d3-111">주요한</span><span class="sxs-lookup"><span data-stu-id="327d3-111">Primary</span></span>  <br/> |<span data-ttu-id="327d3-112">값: 1-7</span><span class="sxs-lookup"><span data-stu-id="327d3-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="327d3-113">**미디어**</span><span class="sxs-lookup"><span data-stu-id="327d3-113">**Media**</span></span> <br/> |<span data-ttu-id="327d3-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="327d3-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="327d3-115">MediaID 및 Media 값의 정적 매핑:</span><span class="sxs-lookup"><span data-stu-id="327d3-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="327d3-116">1--메신저 대화</span><span class="sxs-lookup"><span data-stu-id="327d3-116">1 -- IM</span></span> <br/>  <span data-ttu-id="327d3-117">2-파일 전송</span><span class="sxs-lookup"><span data-stu-id="327d3-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="327d3-118">3-원격 지원</span><span class="sxs-lookup"><span data-stu-id="327d3-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="327d3-119">4-응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="327d3-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="327d3-120">5--오디오</span><span class="sxs-lookup"><span data-stu-id="327d3-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="327d3-121">6--영상</span><span class="sxs-lookup"><span data-stu-id="327d3-121">6 -- Video</span></span> <br/>  <span data-ttu-id="327d3-122">7-앱 초대</span><span class="sxs-lookup"><span data-stu-id="327d3-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="327d3-123">LcsCDR에서 MediaTypes의 값에 대 한 형식 지정을 확인 하려는 경우 다음 조인 조각을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="327d3-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
