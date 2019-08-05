---
title: Phones 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: 전화 테이블은 지원 테이블입니다. 표의 각 레코드에는 데이터베이스의 레코드를 포함 하는 VoIP 통화와 관련 된 하나의 전화 번호에 대 한 정보가 저장 됩니다.
ms.openlocfilehash: 684586f21b16c785bcc75458e5330c42aad2ccb4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196709"
---
# <a name="phones-table"></a><span data-ttu-id="49c4b-104">Phones 테이블</span><span class="sxs-lookup"><span data-stu-id="49c4b-104">Phones table</span></span>
 
<span data-ttu-id="49c4b-105">전화 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="49c4b-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="49c4b-106">표의 각 레코드에는 데이터베이스의 레코드를 포함 하는 VoIP 통화와 관련 된 하나의 전화 번호에 대 한 정보가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49c4b-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="49c4b-107">**열**</span><span class="sxs-lookup"><span data-stu-id="49c4b-107">**Column**</span></span>|<span data-ttu-id="49c4b-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="49c4b-108">**Data Type**</span></span>|<span data-ttu-id="49c4b-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="49c4b-109">**Key/Index**</span></span>|<span data-ttu-id="49c4b-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="49c4b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="49c4b-111">**PhoneId**</span><span class="sxs-lookup"><span data-stu-id="49c4b-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="49c4b-112">int</span><span class="sxs-lookup"><span data-stu-id="49c4b-112">int</span></span>  <br/> |<span data-ttu-id="49c4b-113">주요한</span><span class="sxs-lookup"><span data-stu-id="49c4b-113">Primary</span></span>  <br/> |<span data-ttu-id="49c4b-114">이 전화를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="49c4b-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="49c4b-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="49c4b-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="49c4b-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="49c4b-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="49c4b-117">전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="49c4b-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="49c4b-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="49c4b-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="49c4b-119">Dmtf</span><span class="sxs-lookup"><span data-stu-id="49c4b-119">dateTime</span></span>  <br/> ||<span data-ttu-id="49c4b-120">타임 스탬프 (내부용).</span><span class="sxs-lookup"><span data-stu-id="49c4b-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="49c4b-121">이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="49c4b-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

