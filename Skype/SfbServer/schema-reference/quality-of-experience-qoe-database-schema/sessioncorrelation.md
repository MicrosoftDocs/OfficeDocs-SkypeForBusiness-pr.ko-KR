---
title: SessionCorrelation 테이블
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
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: SessionCorrelation 관계 테이블은 지원 테이블입니다. 각 레코드는 여러 세션을 연결 하는 데 사용 되는 CorrelationID 하나를 나타냅니다.
ms.openlocfilehash: cd9f477ad71b836fb204aab651aceb7bbb5832f8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805746"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="768b4-104">SessionCorrelation 테이블</span><span class="sxs-lookup"><span data-stu-id="768b4-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="768b4-105">SessionCorrelation 관계 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="768b4-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="768b4-106">각 레코드는 여러 세션을 연결 하는 데 사용 되는 CorrelationID 하나를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="768b4-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="768b4-107">**열**</span><span class="sxs-lookup"><span data-stu-id="768b4-107">**Column**</span></span>|<span data-ttu-id="768b4-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="768b4-108">**Data Type**</span></span>|<span data-ttu-id="768b4-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="768b4-109">**Key/Index**</span></span>|<span data-ttu-id="768b4-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="768b4-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="768b4-111">**검사**</span><span class="sxs-lookup"><span data-stu-id="768b4-111">**Checksum**</span></span> <br/> |<span data-ttu-id="768b4-112">int</span><span class="sxs-lookup"><span data-stu-id="768b4-112">int</span></span>  <br/> |||
|<span data-ttu-id="768b4-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="768b4-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="768b4-114">int</span><span class="sxs-lookup"><span data-stu-id="768b4-114">int</span></span>  <br/> |<span data-ttu-id="768b4-115">주요한</span><span class="sxs-lookup"><span data-stu-id="768b4-115">Primary</span></span>  <br/> |<span data-ttu-id="768b4-116">이 A/V 회의 서버를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="768b4-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="768b4-117">**Legredir**</span><span class="sxs-lookup"><span data-stu-id="768b4-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="768b4-118">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="768b4-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="768b4-119">독특한</span><span class="sxs-lookup"><span data-stu-id="768b4-119">Unique</span></span>  <br/> |<span data-ttu-id="768b4-120">상호 관련 된 세션은 동일한 상관 관계 ID를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="768b4-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="768b4-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="768b4-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="768b4-122">dmtf</span><span class="sxs-lookup"><span data-stu-id="768b4-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="768b4-123">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="768b4-123">For internal use only.</span></span>  <br/> |
   

