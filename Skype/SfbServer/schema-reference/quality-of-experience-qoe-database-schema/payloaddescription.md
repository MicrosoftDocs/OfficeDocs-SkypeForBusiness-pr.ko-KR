---
title: PayloadDescription 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: PayloadDescription 테이블은 지원 테이블입니다. 각 레코드는 오디오 또는 비디오 세션에 사용 되는 하나의 코덱을 나타냅니다.
ms.openlocfilehash: 3a5719d7fbfe23eb8c1457565a36df0a02617fde
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807496"
---
# <a name="payloaddescription-table"></a><span data-ttu-id="db5c6-104">PayloadDescription 테이블</span><span class="sxs-lookup"><span data-stu-id="db5c6-104">PayloadDescription table</span></span>
 
<span data-ttu-id="db5c6-105">PayloadDescription 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="db5c6-105">The PayloadDescription table is a supporting table.</span></span> <span data-ttu-id="db5c6-106">각 레코드는 오디오 또는 비디오 세션에 사용 되는 하나의 코덱을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="db5c6-106">Each record represents one Codec, which is used in an audio or video session.</span></span>
  
|<span data-ttu-id="db5c6-107">**열**</span><span class="sxs-lookup"><span data-stu-id="db5c6-107">**Column**</span></span>|<span data-ttu-id="db5c6-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="db5c6-108">**Data Type**</span></span>|<span data-ttu-id="db5c6-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="db5c6-109">**Key/Index**</span></span>|<span data-ttu-id="db5c6-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="db5c6-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="db5c6-111">**PayloadDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="db5c6-111">**PayloadDescriptionKey**</span></span> <br/> |<span data-ttu-id="db5c6-112">int</span><span class="sxs-lookup"><span data-stu-id="db5c6-112">int</span></span>  <br/> |<span data-ttu-id="db5c6-113">주요한</span><span class="sxs-lookup"><span data-stu-id="db5c6-113">Primary</span></span>  <br/> |<span data-ttu-id="db5c6-114">코덱을 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="db5c6-114">Unique number identifying the Codec.</span></span>  <br/> |
|<span data-ttu-id="db5c6-115">**PayloadDescription**</span><span class="sxs-lookup"><span data-stu-id="db5c6-115">**PayloadDescription**</span></span> <br/> |<span data-ttu-id="db5c6-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="db5c6-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="db5c6-117">독특한</span><span class="sxs-lookup"><span data-stu-id="db5c6-117">Unique</span></span>  <br/> |<span data-ttu-id="db5c6-118">코덱 이름.</span><span class="sxs-lookup"><span data-stu-id="db5c6-118">Codec name.</span></span>  <br/> |
   

