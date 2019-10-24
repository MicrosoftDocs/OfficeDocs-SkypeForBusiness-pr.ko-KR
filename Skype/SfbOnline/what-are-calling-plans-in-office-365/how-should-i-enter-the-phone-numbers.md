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
# <a name="how-should-i-enter-the-phone-numbers"></a>전화 번호를 어떻게 입력 해야 하나요?

전화 번호를 이식할 때는 올바른 형식으로 입력 해야 합니다. 
  
> [!NOTE]
> 각 전화 번호 또는 전화 번호 범위를 각 줄에 별도로 입력 해야 합니다. 
  
- 단일 전화 번호를 입력 하는 경우:
    
  - 대시 "-"를 포함 하 여 모든 특수 문자를 무시 합니다. 예를 들면 다음과 같습니다.
    
  - 10 자리 숫자의 경우: ** &amp; \*(425\*()\*&amp;&amp;\*(4 ()) (\*250649** 는 **+ 14255550649**로 수정 됩니다.
    
  - 11 자리 숫자의 경우: **1\*(\*&amp;) (&amp;\*42 (\*&amp;** ) (55550649는 **+ 14255550649**로 수정 됩니다.
    
  - 10 개 또는 11 개의 숫자가 있으면 모든 태그가 무시 됩니다. 예를 ** \<들어 div> 4255551234\</div>** 는 **+ 14255551234**입니다.
    
  - "-", 공백 및 괄호는 무시 됩니다. 예를 들면 다음과 같습니다.
    
  - 10 자리 숫자의 경우 **(425) 555-6776** 는 **+ 14255556776**로 수정 됩니다.
    
  - 11 자리 숫자의 경우: **1 (425) 555-6776** 는 **+ 14255556776**로 수정 됩니다.
    
  - 모든 문자는 특수 문자로 처리 되 고 10 자리 또는 11 자리 전화 번호가 있으면 무시 됩니다. 예를 들면 다음과 같습니다.
    
  - 10 자리 숫자의 경우: **14jaosia2reoij05jof55506ajfoj49isdjf** 는 **+ 14255550649**으로 수정 됩니다.
    
  - 11 자리 숫자의 경우 **1ade4jaoda2rfoij05ojof55506dsfoj49if** 는 **+ 14255550649**으로 수정 됩니다.
    
  - 다른 언어 에서도 특수 문자의 조합이 수정 됩니다. 예를 들면 다음과 같습니다. 
    
  - 10 자리 숫자의 경우:**中 文 4 中文2ajj5\*() (\*(5 () 551345** 는 **+ 14555551345**로 수정 됩니다.
    
  - 11 자리 숫자의 경우:**中 文 4 中 文 2\*$ a5 () (\*((5) (() 55 (1345** 는 **+ 14555551345**으로 수정 됩니다.
    
  - 숫자가 10 자리 미만 이거나 11 자리 보다 많으면 사용자가 수정할 수 있도록 강조 표시 됩니다.
    
  - \*\*5551245\* \* 는 강조 표시 되며 수정 해야 합니다.
    
  - **1234567891011** 는 강조 표시 되며 수정 해야 합니다.
    
  - 10 자리 보다 작거나 11 자리 보다 작은 숫자 (특수 문자)가 자동으로 수정 되지 않고 강조 표시 됩니다.
    
  - 입력 한 특수 문자 없이 7 자리 숫자의 경우 **123456abcdefg7** 가 강조 표시 되며 수정 해야 하지만 문자는 무시 되지 않습니다.
    
  - 입력 한 특수 문자를 사용 하는 7 자리 숫자: **12345! @ #&amp;\*$% ^ ()--@ # $% ^&amp;\*** () 7이 수정 됨으로 강조 표시 됩니다. 특수 문자는 무시 되지 않습니다.
    
- 전화 번호 범위를 입력 하는 경우
    
  - 두 개의 전화 번호만 허용 됩니다. 작은 수는 범위에서 첫 번째 숫자 여야 합니다.
    
  - 대시 "-"를 제외한 모든 특수 문자는 단일 숫자와 동일 하 게 처리 됩니다. 예를 들어 **(425) 555 0&amp;\*(123-(1425) 5557899nm** 은 **+ 14255550123-+ 13202040659**로 수정 됩니다.
    
  - "-"는 두 숫자를 구분 하는 데만 사용 됩니다. 숫자 범위에 여러 "-"를 포함 하는 것은 지원 되지 않습니다. 예를 들어 **(425) 555-0649-(425) 555-1115** 는 **(425) 5550649-(425) 5551115**로 입력 해야 합니다.
    
  **자세한 단계별 지침은 [Office 365으로 전화 번호 전송을](/microsoftteams/transfer-phone-numbers-to-office-365)참조 하세요.**

  > [!NOTE]
  > 이 보다 더 많은 전화 번호를 받으려면 [비즈니스 제품에 대 한 고객 지원에 문의-관리자 도움말](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) 을 참조 하세요.

  
## <a name="related-topics"></a>관련 항목
[전화 번호 전송 일반적인 질문](/microsoftteams/transferring-phone-numbers-common-questions)

[통화 요금제에 사용 되는 다른 종류의 전화 번호](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[조직의 전화 번호 관리](/microsoftteams/manage-phone-numbers-for-your-organization)

[비상 통화 약관](/microsoftteams/emergency-calling-terms-and-conditions)

[비즈니스용 Skype Online: 비상 전화 부인 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 