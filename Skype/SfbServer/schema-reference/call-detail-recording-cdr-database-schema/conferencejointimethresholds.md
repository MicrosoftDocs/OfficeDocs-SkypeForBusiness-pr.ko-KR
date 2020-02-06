---
title: 비즈니스용 Skype 서버 2015의 ConferenceJoinTimeThresholds 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: ConferenceJoinTimeThresholds 테이블에는 컨퍼런스 참가 시간 요약 보고서에 사용 되는 분류 경계가 포함 되어 있습니다. 컨퍼런스 참가 시간 요약 보고서에는 사용자가 회의에 참가 하는 데 필요한 시간 시간이 요약 되어 있습니다. 이러한 시간 값은 다음 범주 중 하 나와 평균으로 보고 됩니다.
ms.openlocfilehash: 1874a94448be5957079b1c53944bc127df761e5e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815396"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="d3281-104">비즈니스용 Skype 서버 2015의 ConferenceJoinTimeThresholds 테이블</span><span class="sxs-lookup"><span data-stu-id="d3281-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d3281-105">ConferenceJoinTimeThresholds 테이블에는 컨퍼런스 참가 시간 요약 보고서에 사용 되는 분류 경계가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3281-105">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="d3281-106">컨퍼런스 참가 시간 요약 보고서에는 사용자가 회의에 참가 하는 데 필요한 시간 시간이 요약 되어 있습니다. 이러한 시간 값은 다음 범주 중 하 나와 평균으로 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3281-106">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="d3281-107">2 초 미만.</span><span class="sxs-lookup"><span data-stu-id="d3281-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="d3281-108">2 초에서 5 초 사이입니다.</span><span class="sxs-lookup"><span data-stu-id="d3281-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="d3281-109">5 초에서 10 초 사이입니다.</span><span class="sxs-lookup"><span data-stu-id="d3281-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="d3281-110">10 초 이상</span><span class="sxs-lookup"><span data-stu-id="d3281-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="d3281-111">ConferenceJoinTimeThresholds 테이블에는 2 초, 5 초 및 10 초의 분류 값이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3281-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="d3281-112">이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d3281-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="d3281-113">**열**</span><span class="sxs-lookup"><span data-stu-id="d3281-113">**Column**</span></span>|<span data-ttu-id="d3281-114">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="d3281-114">**Data Type**</span></span>|<span data-ttu-id="d3281-115">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="d3281-115">**Key/Index**</span></span>|<span data-ttu-id="d3281-116">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="d3281-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d3281-117">**ThresholdId**</span><span class="sxs-lookup"><span data-stu-id="d3281-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="d3281-118">int</span><span class="sxs-lookup"><span data-stu-id="d3281-118">int</span></span>  <br/> |<span data-ttu-id="d3281-119">주요한</span><span class="sxs-lookup"><span data-stu-id="d3281-119">Primary</span></span>  <br/> |<span data-ttu-id="d3281-120">분류의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="d3281-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="d3281-121">**ThresholdValue**</span><span class="sxs-lookup"><span data-stu-id="d3281-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="d3281-122">int</span><span class="sxs-lookup"><span data-stu-id="d3281-122">int</span></span>  <br/> || <span data-ttu-id="d3281-123">분류에 대 한 상한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d3281-123">Upper limit for the classification.</span></span> <span data-ttu-id="d3281-124">사용 가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d3281-124">Allowed values are:</span></span> <br/>  <span data-ttu-id="d3281-125">2</span><span class="sxs-lookup"><span data-stu-id="d3281-125">2</span></span> <br/>  <span data-ttu-id="d3281-126">5mb</span><span class="sxs-lookup"><span data-stu-id="d3281-126">5</span></span> <br/>  <span data-ttu-id="d3281-127">1천만</span><span class="sxs-lookup"><span data-stu-id="d3281-127">10</span></span> <br/> |
   

