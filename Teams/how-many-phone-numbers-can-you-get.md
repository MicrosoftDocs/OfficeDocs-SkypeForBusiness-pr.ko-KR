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
description: 번호의 유형과 라이선스 수에 따라 Microsoft Teams 수 있는 전화 번호 수에 대해 자세히 알아보아야 합니다.
ms.openlocfilehash: ecd3eacc978d81bddc67b64b9e2480bba950aa1f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092226"
---
# <a name="how-many-phone-numbers-can-you-get"></a>몇 개의 전화 번호를 받을 수 있나요?

조직에 대한 전화 번호를 찾고 받을 때 라이선스를 할당한 것보다 더 많은 전화 번호를 얻을 수 있습니다. 그러나 이는 구입하고 할당한 라이선스의 유형과 전화 번호 유형에 따라 달라 습니다. 통화 [요금제에](different-kinds-of-phone-numbers-used-for-calling-plans.md) 사용되는 다양한 전화 번호를 클릭하여 통화에 사용되는 다양한 전화 번호에 대해 Microsoft Teams.
  
전화 번호 보기 페이지에서 전화 번호 수를 볼 수 Microsoft Teams 관리 센터에서 [Get-CsOnlineTelephoneNumberAvailableCount](/powershell/module/skype/Get-CsOnlineTelephoneNumberAvailableCount) cmdlet을 실행할 수 있습니다. 
  
> [!IMPORTANT]
> 아래 제한에는 Microsoft로 이식하거나 전송한 전화 번호가 포함되어 없습니다. 
  
## <a name="how-many-phone-numbers-you-can-get"></a>받을 수 있는 전화 번호는 몇 개인가요?

||||
|:-----|:-----|:-----|
|**전화 번호의 유형은 다음과 같은 것입니다.** <br/> |**총 전화 번호를 어떻게 얻나요?** <br/> |**다음은 예제입니다.** <br/> |
|사용자(구독자) 번호  <br/> |전화 번호 수는 국내 통화 계획  및/또는 국내 및  국제 통화 요금제 라이선스의 총 수와 같고 1.1 + 10 추가 전화 번호가 곱해 곱합니다. <br/> |국내 통화 요금제 및/또는 국내 및 국제 통화 계획으로 총 50명이 있는 경우 **65개** 전화 **번호(50 x 1.1 + 10)를** 획득할 수 있습니다. <br/> |
|서비스 번호  <br/> | 전화 번호 수는 총 전화 번호 및 오디오 **회의** 전화 시스템 수와 같고 다음을 사용 합니다.  <br/>  라이선스가 **1-25개인** 경우 **5개** 전화 번호가 부여됩니다. <br/>  **26-49개 라이선스가 있는** 경우 **10개** 전화 번호가 부여됩니다. <br/>  **라이선스가 50-99개인** 경우 **20개** 전화 번호가 부여됩니다. <br/>  **라이선스가 100-149개인** 경우 **30개** 전화 번호가 부여됩니다. <br/>  **150-199개** 라이선스가 있는 경우 **40개** 전화 번호가 부여됩니다. <br/>  **200-499** 라이선스가 있는 경우 **65개** 전화 번호가 부여됩니다. <br/>  **500-749** 라이선스가 있는 경우 **90개** 전화 번호가 부여됩니다. <br/>  **750-999** 라이선스가 있는 경우 **110개** 전화 번호가 부여됩니다. <br/>  **1,000-1,249개** 라이선스가 있는 경우 **125개** 전화 번호가 부여됩니다. <br/>  **1,250-1,499개** 라이선스가 있는 경우 **135개** 전화 번호가 부여됩니다. <br/>  **1,500-1,999개** 라이선스가 있는 경우 **160개** 전화 번호가 부여됩니다. <br/>  **2,000-2,999개** 라이선스가 있는 경우 **210개** 전화 번호가 부여됩니다. <br/>  **3,000-6,999개** 라이선스가 있는 경우 **420개** 전화 번호가 부여됩니다. <br/>  **7,000-9,999개** 라이선스가 있는 경우 **500개** 전화 번호가 부여됩니다. <br/>  **10,000-14,999개** 라이선스가 있는 경우 **600개** 전화 번호가 부여됩니다. <br/>  **15,000-19,999개** 라이선스가 있는 경우 **700개** 전화 번호가 부여됩니다. <br/>  **20,000-49,999개** 라이선스가 있는 경우 **1000개** 전화 번호가 부여됩니다. <br/>  **50,000개 이상의** 라이선스가 있는 경우 **1500개** 전화 번호가 부여됩니다. <br/> |총 **51개**  전화 시스템 오디오 회의 라이선스가 있는 경우 **20개** 전화 서비스 번호를 얻을 수 있습니다.  <br/> |
|무료 서비스 번호  <br/> | 전화 번호 수는 총 전화 번호 및 오디오 **회의** 전화 시스템 수와 같고 다음을 사용 합니다.  <br/>  라이선스가 **1-25개인** 경우 **5개** 전화 번호가 부여됩니다. <br/>  **26-49개 라이선스가 있는** 경우 **10개** 전화 번호가 부여됩니다. <br/>  **라이선스가 50-99개인** 경우 **20개** 전화 번호가 부여됩니다. <br/>  **라이선스가 100-149개인** 경우 **30개** 전화 번호가 부여됩니다. <br/>  **150-199개** 라이선스가 있는 경우 **40개** 전화 번호가 부여됩니다. <br/>  **200-499** 라이선스가 있는 경우 **65개** 전화 번호가 부여됩니다. <br/>  **500-749** 라이선스가 있는 경우 **90개** 전화 번호가 부여됩니다. <br/>  **750-999** 라이선스가 있는 경우 **110개** 전화 번호가 부여됩니다. <br/>  **1,000-1,249개** 라이선스가 있는 경우 **125개** 전화 번호가 부여됩니다. <br/>  **1,250-1,499개** 라이선스가 있는 경우 **135개** 전화 번호가 부여됩니다. <br/>  **1,500-1,999개** 라이선스가 있는 경우 **160개** 전화 번호가 부여됩니다. <br/>  **2,000-2,999개** 라이선스가 있는 경우 **210개** 전화 번호가 부여됩니다. <br/>  **3,000-6,999개** 라이선스가 있는 경우 **420개** 전화 번호가 부여됩니다. <br/>  **7,000-9,999개** 라이선스가 있는 경우 **500개** 전화 번호가 부여됩니다. <br/>  **10,000-14,999개** 라이선스가 있는 경우 **600개** 전화 번호가 부여됩니다. <br/>  **15,000-19,999개** 라이선스가 있는 경우 **700개** 전화 번호가 부여됩니다. <br/>  **20,000-49,999개** 라이선스가 있는 경우 **1000개** 전화 번호가 부여됩니다. <br/>  **50,000개 이상의** 라이선스가 있는 경우 **1500개** 전화 번호가 부여됩니다. <br/> |총 **1001개**  전화 시스템 오디오 회의 라이선스가 있는 경우 **125개** 무료 서비스 번호를 얻을 수 있습니다.  <br/> <br/> **중요:** 무료 전화 번호를 예약하고 사용하려면 [Communications Credits](set-up-communications-credits-for-your-organization.md) 청구가 필요합니다.          |
   
> [!NOTE]
> 이보다 더 많은 전화 번호가 필요한 경우 비즈니스 제품에 대한 지원에 [문의하세요 - 관리자 도움말](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)
  
## <a name="related-topics"></a>관련 항목
[전화 번호 전송 자주 묻는 질문](./phone-number-calling-plans/port-order-overview.md)

[통화 계획에 사용되는 다양한 종류의 전화 번호](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[조직의 전화 번호 관리](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[긴급 통화 사용 약관](emergency-calling-terms-and-conditions.md)

[긴급 통화 고지 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
