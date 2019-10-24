---
title: 전화 번호를 어떻게 입력 해야 하나요?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 28aa24b4-8c81-4327-9752-989ea7540db2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: ms.lync.lac.PortOrderNumbers
ms.custom:
- Calling Plans
description: '비즈니스용 Skype로 전화를 걸 때 전화번호를 설정 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: df9d82a6e785954a95a455f0e43aa0e077f40bcf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "37642153"
---
# <a name="how-should-i-enter-the-phone-numbers"></a><span data-ttu-id="e191c-103">전화 번호를 어떻게 입력 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="e191c-103">How should I enter the phone numbers?</span></span>

<span data-ttu-id="e191c-104">전화 번호를 이식할 때는 올바른 형식으로 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e191c-104">When you are porting phone numbers, you must enter them in the correct format.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e191c-105">각 전화 번호 또는 전화 번호 범위를 각 줄에 별도로 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e191c-105">Each phone number or range of phone number must be entered separately on each line.</span></span> 
  
- <span data-ttu-id="e191c-106">단일 전화 번호를 입력 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="e191c-106">When you are entering single phone numbers:</span></span>
    
  - <span data-ttu-id="e191c-107">대시 "-"를 포함 하 여 모든 특수 문자를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e191c-107">All special characters will be ignored (including dash "-").</span></span> <span data-ttu-id="e191c-108">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e191c-108">For example:</span></span>
    
  - <span data-ttu-id="e191c-109">10 자리 숫자의 경우: \*\* &amp; \*(425\*()\*&amp;&amp;\*(4 ()) (\*250649\*\* 는 **+ 14255550649**로 수정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e191c-109">For a 10-digit number: **&amp;\*(425\*()(\*&amp;4&amp;\*())(\*250649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="e191c-110">11 자리 숫자의 경우: **1\*(\*&amp;) (&amp;\*42 (\*&amp;** ) (55550649는 **+ 14255550649**로 수정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e191c-110">For an 11-digit number: **1\*()(\*&amp;42&amp;\*()(\*&amp;55550649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="e191c-111">10 개 또는 11 개의 숫자가 있으면 모든 태그가 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e191c-111">All tags will be ignored if there are 10 or 11 digits.</span></span> <span data-ttu-id="e191c-112">예를 \*\* \<들어 div> 4255551234\</div>\*\* 는 **+ 14255551234**입니다.</span><span class="sxs-lookup"><span data-stu-id="e191c-112">For example, **\<div> 4255551234\</div>** will be **+14255551234**.</span></span>
    
  - <span data-ttu-id="e191c-113">"-", 공백 및 괄호는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e191c-113">"-", space, and parenthesis will be ignored.</span></span> <span data-ttu-id="e191c-114">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e191c-114">For example:</span></span>
    
  - <span data-ttu-id="e191c-115">10 자리 숫자의 경우 **(425) 555-6776** 는 **+ 14255556776**로 수정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e191c-115">For a 10-digit number: **(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="e191c-116">11 자리 숫자의 경우: **1 (425) 555-6776** 는 **+ 14255556776**로 수정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e191c-116">For an 11-digit number: **1(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="e191c-117">모든 문자는 특수 문자로 처리 되 고 10 자리 또는 11 자리 전화 번호가 있으면 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e191c-117">All letters will be treated as special characters and ignored if there is a 10-digit or 11-digit phone number.</span></span> <span data-ttu-id="e191c-118">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e191c-118">For example:</span></span>
    
  - <span data-ttu-id="e191c-119">10 자리 숫자의 경우: **14jaosia2reoij05jof55506ajfoj49isdjf** 는 **+ 14255550649**으로 수정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e191c-119">For a 10-digit number: **14jaosia2reoij05jof55506ajfoj49isdjf** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="e191c-120">11 자리 숫자의 경우 **1ade4jaoda2rfoij05ojof55506dsfoj49if** 는 **+ 14255550649**으로 수정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e191c-120">For an 11-digit number: **1ade4jaoda2rfoij05ojof55506dsfoj49if** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="e191c-121">다른 언어 에서도 특수 문자의 조합이 수정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e191c-121">Any combination of special characters, even in other languages, will be corrected.</span></span> <span data-ttu-id="e191c-122">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e191c-122">For example:</span></span> 
    
  - <span data-ttu-id="e191c-123">10 자리 숫자의 경우:**中 文 4 中文2ajj5\*() (\*(5 () 551345** 는 **+ 14555551345**로 수정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e191c-123">For a 10-digit number: **中文4中文2ajj5\*（）（\*（5()...551345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="e191c-124">11 자리 숫자의 경우:**中 文 4 中 文 2\*$ a5 () (\*((5) (() 55 (1345** 는 **+ 14555551345**으로 수정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e191c-124">For an 11-digit number: **中文4中文2$a5\*（）（\*（5()...55(.1345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="e191c-125">숫자가 10 자리 미만 이거나 11 자리 보다 많으면 사용자가 수정할 수 있도록 강조 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e191c-125">If any numbers contain fewer than 10 digits or more than 11 digits, they will be highlighted for the user to correct:</span></span>
    
  - <span data-ttu-id="e191c-126">\*\*5551245\* \* 는 강조 표시 되며 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e191c-126">\*\*5551245\*\* will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="e191c-127">**1234567891011** 는 강조 표시 되며 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e191c-127">**1234567891011** will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="e191c-128">10 자리 보다 작거나 11 자리 보다 작은 숫자 (특수 문자)가 자동으로 수정 되지 않고 강조 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e191c-128">Any numbers that are fewer than 10 digits or more than 11 digits, with any special characters, will be highlighted without being automatically corrected.</span></span>
    
  - <span data-ttu-id="e191c-129">입력 한 특수 문자 없이 7 자리 숫자의 경우 **123456abcdefg7** 가 강조 표시 되며 수정 해야 하지만 문자는 무시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e191c-129">For a 7-digit number without special characters that is entered: **123456abcdefg7** will be highlighted and need to be corrected, but the letters won't be ignored.</span></span>
    
  - <span data-ttu-id="e191c-130">입력 한 특수 문자를 사용 하는 7 자리 숫자: **12345! @ #&amp;\*$% ^ ()--@ # $% ^&amp;\*** () 7이 수정 됨으로 강조 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e191c-130">For a 7-digit number with special characters that is entered: **12345!@#$%^&amp;\*()--@#$%^&amp;\*()7** will be highlighted to be corrected.</span></span> <span data-ttu-id="e191c-131">특수 문자는 무시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e191c-131">The special characters won't be ignored.</span></span>
    
- <span data-ttu-id="e191c-132">전화 번호 범위를 입력 하는 경우</span><span class="sxs-lookup"><span data-stu-id="e191c-132">When you are entering a range of phone numbers.</span></span>
    
  - <span data-ttu-id="e191c-133">두 개의 전화 번호만 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e191c-133">Only two phone numbers are allowed.</span></span> <span data-ttu-id="e191c-134">작은 수는 범위에서 첫 번째 숫자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e191c-134">The smaller number must be the first number in the range.</span></span>
    
  - <span data-ttu-id="e191c-135">대시 "-"를 제외한 모든 특수 문자는 단일 숫자와 동일 하 게 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e191c-135">All special characters (except for the dash "-") are treated the same as single numbers.</span></span> <span data-ttu-id="e191c-136">예를 들어 **(425) 555 0&amp;\*(123-(1425) 5557899nm** 은 **+ 14255550123-+ 13202040659**로 수정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e191c-136">For example, **(425)555 0&amp;\*(123-(1425)5557899nm** will be corrected to **+14255550123 -+13202040659**.</span></span>
    
  - <span data-ttu-id="e191c-137">"-"는 두 숫자를 구분 하는 데만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e191c-137">The "-" is used for only separating the two numbers.</span></span> <span data-ttu-id="e191c-138">숫자 범위에 여러 "-"를 포함 하는 것은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e191c-138">It isn't supported to include multiple "-" in the number range.</span></span> <span data-ttu-id="e191c-139">예를 들어 **(425) 555-0649-(425) 555-1115** 는 **(425) 5550649-(425) 5551115**로 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e191c-139">For example, **(425) 555-0649 - (425) 555-1115** should be entered as **(425) 5550649 - (425) 5551115**.</span></span>
    
  <span data-ttu-id="e191c-140">**자세한 단계별 지침은 [Office 365으로 전화 번호 전송을](/microsoftteams/transfer-phone-numbers-to-office-365)참조 하세요.**</span><span class="sxs-lookup"><span data-stu-id="e191c-140">**For complete step-by-step instructions, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).**</span></span>

  > [!NOTE]
  > <span data-ttu-id="e191c-141">이 보다 더 많은 전화 번호를 받으려면 [비즈니스 제품에 대 한 고객 지원에 문의-관리자 도움말](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e191c-141">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="e191c-142">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e191c-142">Related topics</span></span>
[<span data-ttu-id="e191c-143">전화 번호 전송 일반적인 질문</span><span class="sxs-lookup"><span data-stu-id="e191c-143">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="e191c-144">통화 요금제에 사용 되는 다른 종류의 전화 번호</span><span class="sxs-lookup"><span data-stu-id="e191c-144">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="e191c-145">조직의 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="e191c-145">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="e191c-146">비상 통화 약관</span><span class="sxs-lookup"><span data-stu-id="e191c-146">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="e191c-147">[비즈니스용 Skype Online: 비상 전화 부인 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="e191c-147">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 