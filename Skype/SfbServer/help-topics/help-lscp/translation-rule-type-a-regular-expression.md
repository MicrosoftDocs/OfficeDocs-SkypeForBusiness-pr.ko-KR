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
- ms.lync.lscp.VoiceRuleRegexEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5ee83724-b399-4f8d-8f6d-4b53a26296b4
description: 이 패턴에 일치 필드에서 번역할 숫자와 일치 시키는 데 사용할 패턴을 지정 합니다. 번역 규칙 필드에서 번역 된 숫자의 형식에 대 한 패턴을 지정 합니다. 예를 들어이 패턴 일치 필드\+에 ^{9}(\d \d +) $를 입력 하 고 번역 규칙 필드에 011 $1을 입력할 경우 규칙은 + 441235551010을 011441235551010로 변환 합니다.
ms.openlocfilehash: 98a04d3c7346557bcb095e7187a13f2e93646075
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41699353"
---
# <a name="translation-rule-type-a-regular-expression"></a><span data-ttu-id="643c4-105">번역 규칙: 정규식을 입력</span><span class="sxs-lookup"><span data-stu-id="643c4-105">Translation Rule: Type a Regular Expression</span></span>
 
<span data-ttu-id="643c4-106">**이 패턴에 일치** 필드에서 번역할 숫자와 일치 시키는 데 사용할 패턴을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="643c4-106">In the **Match this pattern** field, specify the pattern that will be used to match the numbers to be translated.</span></span> <span data-ttu-id="643c4-107">**번역 규칙** 필드에서 번역 된 숫자의 형식에 대 한 패턴을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="643c4-107">In the **Translation rule** field, specify a pattern for the format of translated numbers.</span></span> <span data-ttu-id="643c4-108">예를 들어 **이 패턴 일치** 필드\+에 ^{9}(\d \d +) $를 입력 하 고 **번역 규칙** 필드에 011 $1을 입력할 경우 규칙은 + 441235551010을 011441235551010로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="643c4-108">For example, if you enter ^\+(\d{9}\d+)$ in the **Match this pattern** field and 011$1 in the **Translation rule** field, the rule will translate +441235551010 to 011441235551010.</span></span>
  
<span data-ttu-id="643c4-109">비즈니스용 Skype 서버 제어판을 사용 하 여 수행할 수 있는 다양 한 절차에 대 한 자세한 내용은 비즈니스용 [Skype 서버 2015 관리](../../manage/manage.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="643c4-109">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../manage/manage.md).</span></span>
  

