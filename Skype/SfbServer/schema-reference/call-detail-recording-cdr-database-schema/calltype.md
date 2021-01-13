---
title: 비즈니스용 Skype 서버의 CallType 테이블
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
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: CallType 테이블은 사용 가능한 통화 유형 목록이 저장된 정적 테이블입니다.
ms.openlocfilehash: 89f29a2c826f4aef12cc0332e40df0fb421c3932
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813368"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="e28a7-103">비즈니스용 Skype 서버의 CallType 테이블</span><span class="sxs-lookup"><span data-stu-id="e28a7-103">CallType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e28a7-104">CallType 테이블은 사용 가능한 통화 유형 목록이 저장된 정적 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="e28a7-104">The CallType table is a static table that stores the list of possible call types.</span></span>
  
|<span data-ttu-id="e28a7-105">**열**</span><span class="sxs-lookup"><span data-stu-id="e28a7-105">**Column**</span></span>|<span data-ttu-id="e28a7-106">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="e28a7-106">**Data Type**</span></span>|<span data-ttu-id="e28a7-107">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="e28a7-107">**Key/Index**</span></span>|<span data-ttu-id="e28a7-108">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="e28a7-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e28a7-109">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="e28a7-109">**CallTypeId**</span></span> <br/> |<span data-ttu-id="e28a7-110">int</span><span class="sxs-lookup"><span data-stu-id="e28a7-110">int</span></span>  <br/> |<span data-ttu-id="e28a7-111">Primary</span><span class="sxs-lookup"><span data-stu-id="e28a7-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="e28a7-112">**CallType**</span><span class="sxs-lookup"><span data-stu-id="e28a7-112">**CallType**</span></span> <br/> |<span data-ttu-id="e28a7-113">nvarchar</span><span class="sxs-lookup"><span data-stu-id="e28a7-113">nvarchar</span></span>  <br/> || <span data-ttu-id="e28a7-114">허용되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e28a7-114">Allowed values:</span></span> <br/>  <span data-ttu-id="e28a7-115">0 -- 알 수 없음</span><span class="sxs-lookup"><span data-stu-id="e28a7-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="e28a7-116">1 - 인스턴트 메시징</span><span class="sxs-lookup"><span data-stu-id="e28a7-116">1 - Instant Messaging</span></span> <br/>  <span data-ttu-id="e28a7-117">2 -- 응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="e28a7-117">2 -- Application Sharing</span></span> <br/>  <span data-ttu-id="e28a7-118">3 -- 오디오</span><span class="sxs-lookup"><span data-stu-id="e28a7-118">3 -- Audio</span></span> <br/>  <span data-ttu-id="e28a7-119">4 - 오디오 및 비디오</span><span class="sxs-lookup"><span data-stu-id="e28a7-119">4 - Audio and Video</span></span> <br/>  <span data-ttu-id="e28a7-120">5 - 파일 전송</span><span class="sxs-lookup"><span data-stu-id="e28a7-120">5 - File Transfer</span></span> <br/> |
   

