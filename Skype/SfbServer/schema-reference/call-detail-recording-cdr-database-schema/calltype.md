---
title: 비즈니스용 Skype 서버 2015의 CallType 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: CallType 테이블은 가능한 통화 형식 목록을 저장 하는 정적 테이블입니다.
ms.openlocfilehash: 992e5682aedf7a0b9063960992197970146c8cfc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196795"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="9d38e-103">비즈니스용 Skype 서버 2015의 CallType 테이블</span><span class="sxs-lookup"><span data-stu-id="9d38e-103">CallType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9d38e-104">CallType 테이블은 가능한 통화 형식 목록을 저장 하는 정적 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="9d38e-104">The CallType table is a static table that stores the list of possible call types.</span></span>
  
|<span data-ttu-id="9d38e-105">**열**</span><span class="sxs-lookup"><span data-stu-id="9d38e-105">**Column**</span></span>|<span data-ttu-id="9d38e-106">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="9d38e-106">**Data Type**</span></span>|<span data-ttu-id="9d38e-107">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="9d38e-107">**Key/Index**</span></span>|<span data-ttu-id="9d38e-108">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="9d38e-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9d38e-109">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="9d38e-109">**CallTypeId**</span></span> <br/> |<span data-ttu-id="9d38e-110">int</span><span class="sxs-lookup"><span data-stu-id="9d38e-110">int</span></span>  <br/> |<span data-ttu-id="9d38e-111">주요한</span><span class="sxs-lookup"><span data-stu-id="9d38e-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="9d38e-112">**CallType**</span><span class="sxs-lookup"><span data-stu-id="9d38e-112">**CallType**</span></span> <br/> |<span data-ttu-id="9d38e-113">varchar</span><span class="sxs-lookup"><span data-stu-id="9d38e-113">nvarchar</span></span>  <br/> || <span data-ttu-id="9d38e-114">허용 되는 값:</span><span class="sxs-lookup"><span data-stu-id="9d38e-114">Allowed values:</span></span> <br/>  <span data-ttu-id="9d38e-115">0--알 수 없음</span><span class="sxs-lookup"><span data-stu-id="9d38e-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="9d38e-116">1-인스턴트 메시지</span><span class="sxs-lookup"><span data-stu-id="9d38e-116">1 - Instant Messaging</span></span> <br/>  <span data-ttu-id="9d38e-117">2--응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="9d38e-117">2 -- Application Sharing</span></span> <br/>  <span data-ttu-id="9d38e-118">3--오디오</span><span class="sxs-lookup"><span data-stu-id="9d38e-118">3 -- Audio</span></span> <br/>  <span data-ttu-id="9d38e-119">4-오디오 및 비디오</span><span class="sxs-lookup"><span data-stu-id="9d38e-119">4 - Audio and Video</span></span> <br/>  <span data-ttu-id="9d38e-120">5-파일 전송</span><span class="sxs-lookup"><span data-stu-id="9d38e-120">5 - File Transfer</span></span> <br/> |
   

