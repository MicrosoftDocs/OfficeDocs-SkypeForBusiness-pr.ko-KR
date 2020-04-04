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
description: 전화 번호 유형 및 보유 한 라이선스 수에 따라 Microsoft 팀에서 얻을 수 있는 전화번호의 개수에 대해 알아봅니다.
ms.openlocfilehash: b8c6c8a2e1fa2b1b882a4fc2ddbbb5e904e5f6f7
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141111"
---
# <a name="how-many-phone-numbers-can-you-get"></a>몇 개의 전화 번호를 받을 수 있나요?

조직의 전화 번호를 찾고 가져올 때 라이선스를 할당 한 것 보다 더 많은 전화 번호를 받을 수 있습니다. 그러나이는 구입 하 여 할당 한 전화 번호의 종류와 라이선스 종류에 따라 다릅니다. [통화 요금제에 사용 되는 다른 종류의 전화 번호](different-kinds-of-phone-numbers-used-for-calling-plans.md) 를 클릭 하 여 Microsoft 팀에 사용 되는 다양 한 전화 번호를 확인할 수 있습니다.
  
Microsoft 팀 관리 센터의 **전화 번호 가져오기** 페이지에서 가져올 수 있는 전화 번호의 수를 확인 하거나 [CsOnlineTelephoneNumberAvailableCount](https://technet.microsoft.com/library/mt634605.aspx) cmdlet을 실행할 수 있습니다.
  
> [!IMPORTANT]
> 아래의 제한 사항에는 사용자가 구입한 또는 Microsoft에 전송한 전화 번호가 포함 되지 않습니다. 
  
## <a name="how-many-phone-numbers-you-can-get"></a>받을 수 있는 전화번호는 몇 개입니까?

||||
|:-----|:-----|:-----|
|**전화 번호 유형은 다음과 같습니다.** <br/> |**총 전화 번호는 어떻게 얻을 수 있나요?** <br/> |**예제는 다음과 같습니다.** <br/> |
|사용자 (구독자) 번호  <br/> |전화 번호의 수는 **국내 통화 요금제** 및/또는 **국내 및 국제 통화 요금제** 라이선스의 총 수에 1.1 + 10 개의 추가 전화 번호를 곱한 값과 같습니다. <br/> |국내 통화 요금제 및/또는 국내 및 국제 통화 요금제에 50 사용자가 있는 경우 **65** 전화 번호 **(50 x 1.1 + 10)** 를 얻을 수 있습니다. <br/> |
|유료 서비스 번호  <br/> | 전화 번호의 수는 총 **전화 시스템** 및 **오디오 회의** 라이선스 수와 같으며 다음을 사용 합니다. <br/>  **1-25 라이선스가** 있는 경우 **5 개의** 전화 번호를 제공 합니다. <br/>  **26-49 라이선스가** 있는 경우 **10 개의** 전화 번호를 제공 합니다. <br/>  **50-99 라이선스가** 있는 경우 **20 개의** 전화 번호를 제공 합니다. <br/>  **100-149 라이선스가** 있으면 **30** 개의 전화 번호가 제공 됩니다. <br/>  **150-199 라이선스가** 있으면 **40** 전화 번호가 제공 됩니다. <br/>  **200-499 라이선스가** 있으면 **65** 전화 번호가 제공 됩니다. <br/>  **500-749 라이선스가** 있으면 **90** 전화 번호가 제공 됩니다. <br/>  **750-999 라이선스가** 있으면 **110** 전화 번호가 제공 됩니다. <br/>  **1249 라이선스가 1000** 개 있는 경우 **125** 전화 번호가 제공 됩니다. <br/>  **1499 라이선스가** 있는 경우 **135** 전화 번호가 제공 됩니다. <br/>  1500 개 이상의 **라이선스가** 있는 경우 **160** 전화 번호가 제공 됩니다. <br/>  **2999 라이선스가** 있는 경우 **210** 전화 번호가 제공 됩니다. <br/>  **3000 6999 라이선스가** 있는 경우 **420** 전화 번호가 제공 됩니다. <br/>  **7000-9999 개 라이선스가** 있는 경우 **500** 전화 번호가 제공 됩니다. <br/>  **10000 개 14999 라이선스가** 있으면 **600** 전화 번호가 제공 됩니다. <br/>  **15000 19999 라이선스가** 있는 경우 **700** 전화 번호가 제공 됩니다. <br/>  **49999 라이선스가** 있는 경우 **1000** 전화 번호가 제공 됩니다. <br/>  **50000 + 라이선스가** 있으면 **1500** 전화 번호가 제공 됩니다. <br/> |총 **51** **전화 시스템** 및 **오디오 회의** 라이선스가 있는 경우 **20 개의** 유료 서비스 번호를 받을 수 있습니다. <br/> |
|무료 서비스 번호  <br/> | 전화 번호의 수는 총 **전화 시스템** 및 **오디오 회의** 라이선스 수와 같으며 다음을 사용 합니다. <br/>  **1-25 라이선스가** 있는 경우 **5 개의** 전화 번호를 제공 합니다. <br/>  **26-49 라이선스가** 있는 경우 **10 개의** 전화 번호를 제공 합니다. <br/>  **50-99 라이선스가** 있는 경우 **20 개의** 전화 번호를 제공 합니다. <br/>  **100-149 라이선스가** 있으면 **30** 개의 전화 번호가 제공 됩니다. <br/>  **150-199 라이선스가** 있으면 **40** 전화 번호가 제공 됩니다. <br/>  **200-499 라이선스가** 있으면 **65** 전화 번호가 제공 됩니다. <br/>  **500-749 라이선스가** 있으면 **90** 전화 번호가 제공 됩니다. <br/>  **750-999 라이선스가** 있으면 **110** 전화 번호가 제공 됩니다. <br/>  **1249 라이선스가 1000** 개 있는 경우 **125** 전화 번호가 제공 됩니다. <br/>  **1499 라이선스가** 있는 경우 **135** 전화 번호가 제공 됩니다. <br/>  1500 개 이상의 **라이선스가** 있는 경우 **160** 전화 번호가 제공 됩니다. <br/>  **2999 라이선스가** 있는 경우 **210** 전화 번호가 제공 됩니다. <br/>  **3000 6999 라이선스가** 있는 경우 **420** 전화 번호가 제공 됩니다. <br/>  **7000-9999 개 라이선스가** 있는 경우 **500** 전화 번호가 제공 됩니다. <br/>  **10000 개 14999 라이선스가** 있으면 **600** 전화 번호가 제공 됩니다. <br/>  **15000 19999 라이선스가** 있는 경우 **700** 전화 번호가 제공 됩니다. <br/>  **49999 라이선스가** 있는 경우 **1000** 전화 번호가 제공 됩니다. <br/>  **50000 + 라이선스가** 있으면 **1500** 전화 번호가 제공 됩니다. <br/> |총 **1001** **전화 시스템** 및 **오디오 회의** 라이선스가 있는 경우 **125** 무료 서비스 번호를 받을 수 있습니다. <br/> <br/> **중요:** 무료 전화 번호를 예약 하 고 사용 하려면 [통신 크레딧 청구가](set-up-communications-credits-for-your-organization.md) 필요 합니다.          |
   
> [!NOTE]
> 이 보다 더 많은 전화 번호를 받으려면 [비즈니스 제품에 대 한 고객 지원에 문의-관리자 도움말](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) 을 참조 하세요.
  
## <a name="related-topics"></a>관련 항목
[전화 번호 전송 자주 묻는 질문](transferring-phone-numbers-common-questions.md)

[통화 요금제에 사용 되는 다른 종류의 전화 번호](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[조직의 전화 번호 관리](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[긴급 통화 사용 약관](emergency-calling-terms-and-conditions.md)

[비상 전화 고 지 사항 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 