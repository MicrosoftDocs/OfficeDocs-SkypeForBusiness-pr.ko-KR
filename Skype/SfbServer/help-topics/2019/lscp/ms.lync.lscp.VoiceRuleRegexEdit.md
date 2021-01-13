---
title: 변환 규칙 형식 정규식
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceRuleRegexEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 5ee83724-b399-4f8d-8f6d-4b53a26296b4
ROBOTS: NOINDEX, NOFOLLOW
description: '다음 패턴과 일치시킴 필드에 변환할 숫자와 일치시키는 데 사용할 패턴을 지정합니다. 변환 규칙 필드에 변환된 숫자 형식의 패턴을 지정합니다. '
ms.openlocfilehash: a1e04cc94c004b520c077816ae535ca4154047ee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819988"
---
# <a name="translation-rule-type-a-regular-expression"></a><span data-ttu-id="24281-104">변환 규칙: 정규식 입력</span><span class="sxs-lookup"><span data-stu-id="24281-104">Translation Rule: Type a Regular Expression</span></span>
 
<span data-ttu-id="24281-105">**다음 패턴과 일치시킴** 필드에 변환할 숫자와 일치시키는 데 사용할 패턴을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="24281-105">In the **Match this pattern** field, specify the pattern that will be used to match the numbers to be translated.</span></span> <span data-ttu-id="24281-106">**변환 규칙** 필드에 변환된 숫자 형식의 패턴을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="24281-106">In the **Translation rule** field, specify a pattern for the format of translated numbers.</span></span> <span data-ttu-id="24281-107">예를 들어 이 패턴 일치 필드에 ^ (\d \d+)$을 입력하고 변환 규칙 필드에 \+ {9} 011$1을 입력하면 규칙은 +441235551010을 011441235551010으로 변환합니다.  </span><span class="sxs-lookup"><span data-stu-id="24281-107">For example, if you enter ^\+(\d{9}\d+)$ in the **Match this pattern** field and 011$1 in the **Translation rule** field, the rule will translate +441235551010 to 011441235551010.</span></span> 
  
 
  

