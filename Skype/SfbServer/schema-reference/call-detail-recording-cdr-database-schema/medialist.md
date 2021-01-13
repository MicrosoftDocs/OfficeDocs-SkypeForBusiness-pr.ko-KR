---
title: MediaList 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: MediaList 테이블은 다양한 미디어 유형 목록이 저장된 정적 테이블입니다.
ms.openlocfilehash: 6f593876a1b42163b6f2e75dbe44c1eb26b2ff16
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813138"
---
# <a name="medialist-table"></a><span data-ttu-id="8e6a6-103">MediaList 테이블</span><span class="sxs-lookup"><span data-stu-id="8e6a6-103">MediaList table</span></span>
 
<span data-ttu-id="8e6a6-104">MediaList 테이블은 다양한 미디어 유형 목록이 저장된 정적 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="8e6a6-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="8e6a6-105">**열**</span><span class="sxs-lookup"><span data-stu-id="8e6a6-105">**Column**</span></span>|<span data-ttu-id="8e6a6-106">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="8e6a6-106">**Data Type**</span></span>|<span data-ttu-id="8e6a6-107">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="8e6a6-107">**Key/Index**</span></span>|<span data-ttu-id="8e6a6-108">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="8e6a6-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8e6a6-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="8e6a6-109">**MediaId**</span></span> <br/> |<span data-ttu-id="8e6a6-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="8e6a6-110">tinyint</span></span>  <br/> |<span data-ttu-id="8e6a6-111">Primary</span><span class="sxs-lookup"><span data-stu-id="8e6a6-111">Primary</span></span>  <br/> |<span data-ttu-id="8e6a6-112">값: 1-7</span><span class="sxs-lookup"><span data-stu-id="8e6a6-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="8e6a6-113">**미디어**</span><span class="sxs-lookup"><span data-stu-id="8e6a6-113">**Media**</span></span> <br/> |<span data-ttu-id="8e6a6-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8e6a6-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="8e6a6-115">MediaID 및 미디어 값의 정적 매핑:</span><span class="sxs-lookup"><span data-stu-id="8e6a6-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="8e6a6-116">1 -- IM</span><span class="sxs-lookup"><span data-stu-id="8e6a6-116">1 -- IM</span></span> <br/>  <span data-ttu-id="8e6a6-117">2 - 파일 전송</span><span class="sxs-lookup"><span data-stu-id="8e6a6-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="8e6a6-118">3 - 원격 지원</span><span class="sxs-lookup"><span data-stu-id="8e6a6-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="8e6a6-119">4 - 응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="8e6a6-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="8e6a6-120">5 -- 오디오</span><span class="sxs-lookup"><span data-stu-id="8e6a6-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="8e6a6-121">6 -- 비디오</span><span class="sxs-lookup"><span data-stu-id="8e6a6-121">6 -- Video</span></span> <br/>  <span data-ttu-id="8e6a6-122">7 - 앱 초대</span><span class="sxs-lookup"><span data-stu-id="8e6a6-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="8e6a6-123">LcsCDR.SessionDetailsView.MediaTypes의 값에 대한 형식 형식을 확인하려는 경우 다음 조인 코드문을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6a6-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```SQL
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
