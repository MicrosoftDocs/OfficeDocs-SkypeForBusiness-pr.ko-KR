---
title: Phones 테이블
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
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: Phones 테이블은 지원 테이블입니다. 테이블의 각 레코드에는 데이터베이스에 레코드가 있는 VoIP 호출에 관련된 하나의 전화 번호에 대한 정보가 저장됩니다.
ms.openlocfilehash: 12825423b9a03bff93e0d70705a4083bb8c881c9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823268"
---
# <a name="phones-table"></a><span data-ttu-id="fd0ba-104">Phones 테이블</span><span class="sxs-lookup"><span data-stu-id="fd0ba-104">Phones table</span></span>
 
<span data-ttu-id="fd0ba-105">Phones 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="fd0ba-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="fd0ba-106">테이블의 각 레코드에는 데이터베이스에 레코드가 있는 VoIP 호출에 관련된 하나의 전화 번호에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd0ba-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="fd0ba-107">**열**</span><span class="sxs-lookup"><span data-stu-id="fd0ba-107">**Column**</span></span>|<span data-ttu-id="fd0ba-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="fd0ba-108">**Data Type**</span></span>|<span data-ttu-id="fd0ba-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="fd0ba-109">**Key/Index**</span></span>|<span data-ttu-id="fd0ba-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="fd0ba-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fd0ba-111">**PhoneId**</span><span class="sxs-lookup"><span data-stu-id="fd0ba-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="fd0ba-112">int</span><span class="sxs-lookup"><span data-stu-id="fd0ba-112">int</span></span>  <br/> |<span data-ttu-id="fd0ba-113">Primary</span><span class="sxs-lookup"><span data-stu-id="fd0ba-113">Primary</span></span>  <br/> |<span data-ttu-id="fd0ba-114">이 전화를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="fd0ba-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="fd0ba-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="fd0ba-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="fd0ba-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="fd0ba-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="fd0ba-117">전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="fd0ba-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="fd0ba-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="fd0ba-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="fd0ba-119">dateTime</span><span class="sxs-lookup"><span data-stu-id="fd0ba-119">dateTime</span></span>  <br/> ||<span data-ttu-id="fd0ba-120">타임스탬프(내부 전용)</span><span class="sxs-lookup"><span data-stu-id="fd0ba-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="fd0ba-121">이 필드는 Microsoft Lync Server 2013에서 도입했습니다.</span><span class="sxs-lookup"><span data-stu-id="fd0ba-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

