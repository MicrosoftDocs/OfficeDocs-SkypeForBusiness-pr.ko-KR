---
title: 번역 규칙 정규식을 입력 합니다.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceRuleRegexEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5ee83724-b399-4f8d-8f6d-4b53a26296b4
description: 이 패턴에 일치 필드에서 번역할 숫자와 일치 시키는 데 사용할 패턴을 지정 합니다. 번역 규칙 필드에서 번역 된 숫자의 형식에 대 한 패턴을 지정 합니다. 예를 들어이 패턴 일치 필드\+에 ^{9}(\d \d +) $를 입력 하 고 번역 규칙 필드에 011 $1을 입력할 경우 규칙은 + 441235551010을 011441235551010로 변환 합니다.
ms.openlocfilehash: b2797d8c37e666d86eb3b25cdcd43f069eb25498
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821940"
---
# <a name="translation-rule-type-a-regular-expression"></a><span data-ttu-id="e0834-105">번역 규칙: 정규식을 입력</span><span class="sxs-lookup"><span data-stu-id="e0834-105">Translation Rule: Type a Regular Expression</span></span>
 
<span data-ttu-id="e0834-106">**이 패턴에 일치** 필드에서 번역할 숫자와 일치 시키는 데 사용할 패턴을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0834-106">In the **Match this pattern** field, specify the pattern that will be used to match the numbers to be translated.</span></span> <span data-ttu-id="e0834-107">**번역 규칙** 필드에서 번역 된 숫자의 형식에 대 한 패턴을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0834-107">In the **Translation rule** field, specify a pattern for the format of translated numbers.</span></span> <span data-ttu-id="e0834-108">예를 들어 **이 패턴 일치** 필드\+에 ^{9}(\d \d +) $를 입력 하 고 **번역 규칙** 필드에 011 $1을 입력할 경우 규칙은 + 441235551010을 011441235551010로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0834-108">For example, if you enter ^\+(\d{9}\d+)$ in the **Match this pattern** field and 011$1 in the **Translation rule** field, the rule will translate +441235551010 to 011441235551010.</span></span>
  
<span data-ttu-id="e0834-109">비즈니스용 Skype 서버 제어판을 사용 하 여 수행할 수 있는 다양 한 절차에 대 한 자세한 내용은 비즈니스용 [Skype 서버 2015 관리](../../manage/manage.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e0834-109">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>
  

