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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: MediaList 테이블은 다양 한 미디어 유형의 목록을 저장 하는 정적 테이블입니다.
ms.openlocfilehash: e7d739b27bf45b5f5a21183c30bd5b07108b4a9d
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888517"
---
# <a name="medialist-table"></a><span data-ttu-id="52ae4-103">MediaList 테이블</span><span class="sxs-lookup"><span data-stu-id="52ae4-103">MediaList table</span></span>
 
<span data-ttu-id="52ae4-104">MediaList 테이블은 다양 한 미디어 유형의 목록을 저장 하는 정적 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="52ae4-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="52ae4-105">**열**</span><span class="sxs-lookup"><span data-stu-id="52ae4-105">**Column**</span></span>|<span data-ttu-id="52ae4-106">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="52ae4-106">**Data Type**</span></span>|<span data-ttu-id="52ae4-107">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="52ae4-107">**Key/Index**</span></span>|<span data-ttu-id="52ae4-108">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="52ae4-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="52ae4-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="52ae4-109">**MediaId**</span></span> <br/> |<span data-ttu-id="52ae4-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="52ae4-110">tinyint</span></span>  <br/> |<span data-ttu-id="52ae4-111">주요한</span><span class="sxs-lookup"><span data-stu-id="52ae4-111">Primary</span></span>  <br/> |<span data-ttu-id="52ae4-112">값: 1-7</span><span class="sxs-lookup"><span data-stu-id="52ae4-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="52ae4-113">**미디어**</span><span class="sxs-lookup"><span data-stu-id="52ae4-113">**Media**</span></span> <br/> |<span data-ttu-id="52ae4-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="52ae4-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="52ae4-115">MediaID 및 Media 값의 정적 매핑:</span><span class="sxs-lookup"><span data-stu-id="52ae4-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="52ae4-116">1--메신저 대화</span><span class="sxs-lookup"><span data-stu-id="52ae4-116">1 -- IM</span></span> <br/>  <span data-ttu-id="52ae4-117">2-파일 전송</span><span class="sxs-lookup"><span data-stu-id="52ae4-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="52ae4-118">3-원격 지원</span><span class="sxs-lookup"><span data-stu-id="52ae4-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="52ae4-119">4-응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="52ae4-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="52ae4-120">5--오디오</span><span class="sxs-lookup"><span data-stu-id="52ae4-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="52ae4-121">6--영상</span><span class="sxs-lookup"><span data-stu-id="52ae4-121">6 -- Video</span></span> <br/>  <span data-ttu-id="52ae4-122">7-앱 초대</span><span class="sxs-lookup"><span data-stu-id="52ae4-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="52ae4-123">LcsCDR에서 MediaTypes의 값에 대 한 형식 지정을 확인 하려는 경우 다음 조인 조각을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ae4-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```SQL
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
