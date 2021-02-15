---
title: 비즈니스용 Skype에서 통화 파크에 대한 정규화 규칙 확인
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 비즈니스용 Skype 서버 2016의 통화 파크에 대한 정규화 Enterprise Voice.
ms.openlocfilehash: d1bcd6817b1f59f73a8c4ef1562e90253a99bd30
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830578"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a><span data-ttu-id="f173a-103">비즈니스용 Skype에서 통화 파크에 대한 정규화 규칙 확인</span><span class="sxs-lookup"><span data-stu-id="f173a-103">Verify normalization rules for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="f173a-104">비즈니스용 Skype 서버 2016의 통화 파크에 대한 정규화 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="f173a-104">Learn about normalization rules for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="f173a-105">통화 파크 궤도는 정규화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f173a-105">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="f173a-106">다이얼 플랜에서 궤도 번호가 정규화되지 않은지 확인</span><span class="sxs-lookup"><span data-stu-id="f173a-106">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="f173a-107">궤도가 정규화되지 않도록 추가 정규화 규칙을 만들어야 하는 경우, 비즈니스용 [Skype](dial-plans.md) 서버에서 다이얼 플랜 만들기 또는 수정 절차에 따라 새 정규화 규칙을  정의합니다. 그러면 **패턴이** 궤도 범위를 식별하고 변환 패턴이 **$1입니다.**</span><span class="sxs-lookup"><span data-stu-id="f173a-107">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="f173a-108">예를 들어 통화 파크 궤도 범위가 7000 -7999이면 일치할 **패턴은**  **^(7\d {3} )$** 및 변환 **패턴은 $1입니다.**</span><span class="sxs-lookup"><span data-stu-id="f173a-108">For example, if your Call Park orbit range is 7000 - 7999, the **Pattern to match** is **^(7\d{3})$** and **Translation pattern** is **$1**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f173a-109">다이얼 플랜의 기본 정규화 규칙에 **^(\d)가 \*** 포함되어 있지 않은지 확인</span><span class="sxs-lookup"><span data-stu-id="f173a-109">Be sure that the default normalization rule in your dial plans does not contain **^(\d\*)**.</span></span> <span data-ttu-id="f173a-110">그렇지 않으면 통화 파크 정규화 규칙이 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f173a-110">Otherwise, your Call Park normalization rule will never run.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f173a-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f173a-111">See also</span></span>

[<span data-ttu-id="f173a-112">비즈니스용 Skype 서버에서 다이얼 플랜 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="f173a-112">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

