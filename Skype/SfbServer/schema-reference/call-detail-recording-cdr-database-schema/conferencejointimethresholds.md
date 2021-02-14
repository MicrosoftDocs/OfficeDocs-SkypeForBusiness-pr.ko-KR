---
title: 비즈니스용 Skype 서버의 ConferenceJoinTimeThresholds 테이블
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
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: ConferenceJoinTimeThresholds 테이블에는 회의 참가 시간 요약 보고서에서 사용하는 분류 경계가 포함됩니다. 회의 참가 시간 요약 보고서에는 사용자가 회의에 정상적으로 참가하는 데 걸리는 시간이 요약되어 있습니다. 이러한 시간 값은 평균 및 다음 범주 중 하나로 보고됩니다.
ms.openlocfilehash: dfa7293307376b5fb5c86cec6f7504d363b005f5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813308"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a><span data-ttu-id="21eaf-104">비즈니스용 Skype 서버의 ConferenceJoinTimeThresholds 테이블</span><span class="sxs-lookup"><span data-stu-id="21eaf-104">ConferenceJoinTimeThresholds table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="21eaf-p102">ConferenceJoinTimeThresholds 테이블에는 회의 참가 시간 요약 보고서에서 사용하는 분류 경계가 포함됩니다. 회의 참가 시간 요약 보고서에는 사용자가 회의에 정상적으로 참가하는 데 걸리는 시간이 요약되어 있습니다. 이러한 시간 값은 평균 및 다음 범주 중 하나로 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="21eaf-p102">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report. The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>
  
- <span data-ttu-id="21eaf-107">2초 미만</span><span class="sxs-lookup"><span data-stu-id="21eaf-107">Less than 2 seconds.</span></span>
    
- <span data-ttu-id="21eaf-108">2~5초</span><span class="sxs-lookup"><span data-stu-id="21eaf-108">Between 2 second and 5 seconds.</span></span>
    
- <span data-ttu-id="21eaf-109">5~10초</span><span class="sxs-lookup"><span data-stu-id="21eaf-109">Between 5 seconds and 10 seconds.</span></span>
    
- <span data-ttu-id="21eaf-110">10초 초과</span><span class="sxs-lookup"><span data-stu-id="21eaf-110">More than 10 seconds.</span></span>
    
<span data-ttu-id="21eaf-111">ConferenceJoinTimeThresholds 테이블에는 분류 값 2초, 5초, 10초가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="21eaf-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>
  
<span data-ttu-id="21eaf-112">이 표는 Microsoft Lync Server 2013에서 도입된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="21eaf-112">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="21eaf-113">**열**</span><span class="sxs-lookup"><span data-stu-id="21eaf-113">**Column**</span></span>|<span data-ttu-id="21eaf-114">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="21eaf-114">**Data Type**</span></span>|<span data-ttu-id="21eaf-115">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="21eaf-115">**Key/Index**</span></span>|<span data-ttu-id="21eaf-116">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="21eaf-116">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="21eaf-117">**ThresholdId**</span><span class="sxs-lookup"><span data-stu-id="21eaf-117">**ThresholdId**</span></span> <br/> |<span data-ttu-id="21eaf-118">int</span><span class="sxs-lookup"><span data-stu-id="21eaf-118">int</span></span>  <br/> |<span data-ttu-id="21eaf-119">Primary</span><span class="sxs-lookup"><span data-stu-id="21eaf-119">Primary</span></span>  <br/> |<span data-ttu-id="21eaf-120">분류의 고유한 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="21eaf-120">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="21eaf-121">**ThresholdValue**</span><span class="sxs-lookup"><span data-stu-id="21eaf-121">**ThresholdValue**</span></span> <br/> |<span data-ttu-id="21eaf-122">int</span><span class="sxs-lookup"><span data-stu-id="21eaf-122">int</span></span>  <br/> || <span data-ttu-id="21eaf-p103">분류의 상한입니다. 허용되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="21eaf-p103">Upper limit for the classification. Allowed values are:</span></span> <br/>  <span data-ttu-id="21eaf-125">2 </span><span class="sxs-lookup"><span data-stu-id="21eaf-125">2</span></span> <br/>  <span data-ttu-id="21eaf-126">5 </span><span class="sxs-lookup"><span data-stu-id="21eaf-126">5</span></span> <br/>  <span data-ttu-id="21eaf-127">10  </span><span class="sxs-lookup"><span data-stu-id="21eaf-127">10</span></span> <br/> |
   

