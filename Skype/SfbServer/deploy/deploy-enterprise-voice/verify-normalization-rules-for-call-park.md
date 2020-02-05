---
title: 비즈니스용 Skype에서 통화 공원에 대 한 정규화 규칙 확인
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: 비즈니스용 Skype Server Enterprise Voice의 통화 공원에 대 한 정규화 규칙에 대해 알아보세요.
ms.openlocfilehash: 769d9f9becccf4df24a33a11e8814350cfb091e8
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766891"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a><span data-ttu-id="53544-103">비즈니스용 Skype에서 통화 공원에 대 한 정규화 규칙 확인</span><span class="sxs-lookup"><span data-stu-id="53544-103">Verify normalization rules for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="53544-104">비즈니스용 Skype Server Enterprise Voice의 통화 공원에 대 한 정규화 규칙에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="53544-104">Learn about normalization rules for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="53544-105">통화 공원 orbits는 정규화 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53544-105">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="53544-106">전화 걸기 계획을 검사 하 여 궤도 번호가 정규화 되지 않았는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="53544-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="53544-107">Orbits 정규화 되지 않도록 추가 정규화 규칙을 만들어야 하는 경우 비즈니스용 [Skype 서버에서 다이얼 플랜 만들기 또는 수정](dial-plans.md) 의 절차에 따라 새 정규화 규칙을 정의 하 여 **일치 시킬 패턴이** 궤도 범위와 **번역 패턴** **$1**을 식별 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="53544-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="53544-108">예를 들어 통화 공원 궤도 범위가 7000-7999 이면 **일치 하는 패턴** 은 **^{3}(7 \ d) $** 이 고 **번역 패턴** 은 **$1**입니다.</span><span class="sxs-lookup"><span data-stu-id="53544-108">For example, if your Call Park orbit range is 7000 - 7999, the **Pattern to match** is **^(7\d{3})$** and **Translation pattern** is **$1**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="53544-109">다이얼 플랜의 기본 정규화 규칙에 **^ (\d\*)** 이 포함 되어 있지 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="53544-109">Be sure that the default normalization rule in your dial plans does not contain **^(\d\*)**.</span></span> <span data-ttu-id="53544-110">그렇지 않으면 통화 공원 표준화 규칙이 실행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="53544-110">Otherwise, your Call Park normalization rule will never run.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="53544-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="53544-111">See also</span></span>

[<span data-ttu-id="53544-112">비즈니스용 Skype 서버에서 다이얼 플랜 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="53544-112">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

