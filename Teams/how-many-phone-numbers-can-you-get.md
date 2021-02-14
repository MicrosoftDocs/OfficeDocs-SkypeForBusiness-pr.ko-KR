---
title: 몇 개의 전화 번호를 받을 수 있나요?
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: conceptual
ms.assetid: 61dfb27c-5bfa-4481-a930-9c026e73ff3a
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.phonenumbers.searchacquire.tooltip.quantity
- seo-marvel-mar2020
description: 번호의 유형과 라이선스 수에 따라 Microsoft Teams에서 얻을 수 있는 전화 번호 수에 대해 자세히 배워야 합니다.
ms.openlocfilehash: b8c6c8a2e1fa2b1b882a4fc2ddbbb5e904e5f6f7
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141111"
---
# <a name="how-many-phone-numbers-can-you-get"></a>몇 개의 전화 번호를 받을 수 있나요?

조직에 대한 전화 번호를 찾고 받을 때 라이선스를 할당한 것보다 더 많은 전화 번호를 얻을 수 있습니다. 하지만 구입하여 할당한 전화 번호의 유형과 라이선스 유형에 따라 달라 습니다. 통화 [요금제에](different-kinds-of-phone-numbers-used-for-calling-plans.md) 사용되는 다양한 전화 번호를 클릭하여 Microsoft Teams에서 사용되는 다양한 전화 번호를 찾을 수 있습니다.
  
Microsoft Teams 관리 센터의 전화 번호  다운로드 페이지에서 얻을 수 있는 전화 번호 수를 확인하거나 [Get-CsOnlineTelephoneNumberAvailableCount](https://technet.microsoft.com/library/mt634605.aspx) cmdlet을 실행할 수 있습니다.
  
> [!IMPORTANT]
> 아래 제한에는 Microsoft로 이식하거나 이전한 전화 번호가 포함되어 있습니다. 
  
## <a name="how-many-phone-numbers-you-can-get"></a>받을 수 있는 전화 번호는 몇 개입니까?

||||
|:-----|:-----|:-----|
|**다음은 전화 번호의 유형입니다.** <br/> |**총 전화 번호는 어떻게 얻을 수 있나요?** <br/> |**예제는 다음과 같습니다.** <br/> |
|사용자(구독자) 번호  <br/> |전화 번호 수는 국내 통화 요금제  및/또는 국내  및 국제 통화 요금제 라이선스의 총 수와 1.1+ 10개 추가 전화 번호를 곱한 수입니다. <br/> |국내 통화 요금제 및/또는 국내 및 국제 통화 요금제에 총 50명이 있는 경우 **65개** 전화 **번호(50 x 1.1 + 10)를** 획득할 수 있습니다. <br/> |
|서비스 번호  <br/> | 전화 번호 수는 총 전화 시스템  및 오디오  회의 라이선스 수와 같고 다음을 사용 합니다. <br/>  **1-25개 라이선스가 있는** 경우 **5개** 전화 번호가 부여됩니다. <br/>  **26-49개 라이선스가 있는** 경우 **10개** 전화 번호가 부여됩니다. <br/>  **50-99개 라이선스가** 있는 경우 **20개** 전화 번호가 부여됩니다. <br/>  **100-149개** 라이선스가 있는 경우 **30개** 전화 번호가 부여됩니다. <br/>  **150-199개** 라이선스가 있는 경우 **40개** 전화 번호가 부여됩니다. <br/>  **200-499개** 라이선스가 있는 경우 **65개** 전화 번호가 부여됩니다. <br/>  **500-749 라이선스가** 있는 경우 **90개** 전화 번호가 부여됩니다. <br/>  **750-999 라이선스가** 있는 경우 **110개** 전화 번호가 부여됩니다. <br/>  **1,000-1,249개** 라이선스가 있는 경우 **125개** 전화 번호가 부여됩니다. <br/>  **1,250-1,499개** 라이선스가 있는 경우 **135개** 전화 번호가 부여됩니다. <br/>  **1,500-1,999개** 라이선스가 있는 경우 **160개 전화** 번호가 부여됩니다. <br/>  **2,000-2,999개** 라이선스가 있는 경우 **210개** 전화 번호가 부여됩니다. <br/>  **3,000-6,999개** 라이선스가 있는 경우 **420개** 전화 번호가 부여됩니다. <br/>  **7,000-9,999개** 라이선스가 있는 경우 **500개** 전화 번호가 부여됩니다. <br/>  **10,000-14,999개** 라이선스가 있는 경우 **600개** 전화 번호가 부여됩니다. <br/>  **15,000-19,999개** 라이선스가 있는 경우 **700개** 전화 번호가 부여됩니다. <br/>  **20,000-49,999개** 라이선스가 있는 경우 **1000개 전화** 번호가 부여됩니다. <br/>  **50,000개 이상의** 라이선스가 있는 경우 **1500개** 전화 번호가 부여됩니다. <br/> |총 **51대의**  전화 시스템  및 오디오 회의 라이선스가 있는 경우 **20개의** 서비스 번호를 얻을 수 있습니다. <br/> |
|무료 서비스 번호  <br/> | 전화 번호 수는 총 전화 시스템  및 오디오  회의 라이선스 수와 같고 다음을 사용 합니다. <br/>  **1-25개 라이선스가 있는** 경우 **5개** 전화 번호가 부여됩니다. <br/>  **26-49개 라이선스가 있는** 경우 **10개** 전화 번호가 부여됩니다. <br/>  **50-99개 라이선스가** 있는 경우 **20개** 전화 번호가 부여됩니다. <br/>  **100-149개** 라이선스가 있는 경우 **30개** 전화 번호가 부여됩니다. <br/>  **150-199개** 라이선스가 있는 경우 **40개** 전화 번호가 부여됩니다. <br/>  **200-499개** 라이선스가 있는 경우 **65개** 전화 번호가 부여됩니다. <br/>  **500-749 라이선스가** 있는 경우 **90개** 전화 번호가 부여됩니다. <br/>  **750-999 라이선스가** 있는 경우 **110개** 전화 번호가 부여됩니다. <br/>  **1,000-1,249개** 라이선스가 있는 경우 **125개** 전화 번호가 부여됩니다. <br/>  **1,250-1,499개** 라이선스가 있는 경우 **135개** 전화 번호가 부여됩니다. <br/>  **1,500-1,999개** 라이선스가 있는 경우 **160개 전화** 번호가 부여됩니다. <br/>  **2,000-2,999개** 라이선스가 있는 경우 **210개** 전화 번호가 부여됩니다. <br/>  **3,000-6,999개** 라이선스가 있는 경우 **420개** 전화 번호가 부여됩니다. <br/>  **7,000-9,999개** 라이선스가 있는 경우 **500개** 전화 번호가 부여됩니다. <br/>  **10,000-14,999개** 라이선스가 있는 경우 **600개** 전화 번호가 부여됩니다. <br/>  **15,000-19,999개** 라이선스가 있는 경우 **700개** 전화 번호가 부여됩니다. <br/>  **20,000-49,999개** 라이선스가 있는 경우 **1000개 전화** 번호가 부여됩니다. <br/>  **50,000개 이상의** 라이선스가 있는 경우 **1500개** 전화 번호가 부여됩니다. <br/> |총 **1,001대의**  전화  시스템 및 오디오 회의 라이선스가 있는 경우 **125개** 무료 서비스 번호를 얻을 수 있습니다. <br/> <br/> **중요:** [무료](set-up-communications-credits-for-your-organization.md) 전화 번호를 예약하고 사용하려면 통신 크레딧 청구가 필요합니다.          |
   
> [!NOTE]
> 이 번호보다 많은 전화 번호를 필요로 하는 경우 비즈니스 제품에 대한 지원에 [문의하세요. 관리자 도움말](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)
  
## <a name="related-topics"></a>관련 항목
[전화 번호 전송 자주 묻는 질문](transferring-phone-numbers-common-questions.md)

[통화 요금제에 사용되는 다양한 종류의 전화 번호](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[조직의 전화 번호 관리](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[긴급 통화 사용 약관](emergency-calling-terms-and-conditions.md)

[긴급 통화 고지 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 