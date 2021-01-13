---
title: PayloadDescription 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: PayloadDescription 테이블은 지원 테이블입니다. 각 레코드는 오디오 및 비디오 세션에 사용되는 하나의 코덱을 나타냅니다.
ms.openlocfilehash: c9476aea28993a053096a095469d2d4e13251581
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806298"
---
# <a name="payloaddescription-table"></a><span data-ttu-id="a2ab9-104">PayloadDescription 테이블</span><span class="sxs-lookup"><span data-stu-id="a2ab9-104">PayloadDescription table</span></span>
 
<span data-ttu-id="a2ab9-p102">PayloadDescription 테이블은 지원 테이블입니다. 각 레코드는 오디오 및 비디오 세션에 사용되는 하나의 코덱을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a2ab9-p102">The PayloadDescription table is a supporting table. Each record represents one Codec, which is used in an audio or video session.</span></span>
  
|<span data-ttu-id="a2ab9-107">**열**</span><span class="sxs-lookup"><span data-stu-id="a2ab9-107">**Column**</span></span>|<span data-ttu-id="a2ab9-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="a2ab9-108">**Data Type**</span></span>|<span data-ttu-id="a2ab9-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="a2ab9-109">**Key/Index**</span></span>|<span data-ttu-id="a2ab9-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="a2ab9-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a2ab9-111">**PayloadDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="a2ab9-111">**PayloadDescriptionKey**</span></span> <br/> |<span data-ttu-id="a2ab9-112">int</span><span class="sxs-lookup"><span data-stu-id="a2ab9-112">int</span></span>  <br/> |<span data-ttu-id="a2ab9-113">Primary</span><span class="sxs-lookup"><span data-stu-id="a2ab9-113">Primary</span></span>  <br/> |<span data-ttu-id="a2ab9-114">코덱을 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="a2ab9-114">Unique number identifying the Codec.</span></span>  <br/> |
|<span data-ttu-id="a2ab9-115">**PayloadDescription**</span><span class="sxs-lookup"><span data-stu-id="a2ab9-115">**PayloadDescription**</span></span> <br/> |<span data-ttu-id="a2ab9-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a2ab9-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a2ab9-117">고유</span><span class="sxs-lookup"><span data-stu-id="a2ab9-117">Unique</span></span>  <br/> |<span data-ttu-id="a2ab9-118">코덱 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a2ab9-118">Codec name.</span></span>  <br/> |
   

