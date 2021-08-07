---
title: 통화 플랜 알려진 문제
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Calling Plans
description: PSTN 호출 계획에 대한 알려진 문제 및 해당 호출에 대해 할 수 있는 작업을 알아보습니다.
ms.openlocfilehash: 239a0c83a12ae7d5d7b0be2fcbf81bf8825dd85d8a0dcb7a880bc53ad8b8e477
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306111"
---
# <a name="calling-plans-known-issues"></a>통화 플랜 알려진 문제

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

전화 요금제는 온라인에서 찾을 수 있는 비즈니스용 Skype 기능입니다. 다음은 추적되고 적극적으로 조사되는 현재 문제입니다. 이 기능은 향후 빌드에서 업데이트될 때 잠재적으로 해결됩니다.
  
## <a name="calling-plans-known-issues"></a>통화 플랜 알려진 문제

|**알려진 문제**|**설명**|
|:-----|:-----|
|통화 계획에 대한 프로덕션 라이선스로 기술 미리 보기 라이선스에서 프로덕션 라이선스로 전환하는 것이 라이선스를 자동으로 업데이트하지는 않습니다.  <br/> |새 라이선스를 먼저 구입하여 사용자에게 할당할 준비가 됩니다. 사용자로부터 프로모션(Tech Preview) 라이선스를 제거한 다음 새  국내 통화 계획  및/또는 국내 및 국제 통화 계획 라이선스를 사용자에게 즉시 할당합니다.  <br/> 여러 사용자에 대한 라이선스를 제거하고 추가하는 경우 라이선스를 사용하여 모든 사용자에서 라이선스를 제거한  다음 Windows PowerShell 라이선스를 사용하여 모든 사용자에 대한 라이선스를 즉시 할당하는 것이 Windows PowerShell. 이렇게 하면 대량의 사용자 라이선스 할당을 처리할 때 서비스 중단이 없습니다. 샘플 PowerShell 스크립트는 비즈니스용 Skype 및 Microsoft Teams [할당을 참조합니다.](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)  <br/> **참고:** 하이브리드 사용자에 대해 프레미스 PSTN 연결을  사용하는 경우 라이선스를 전화 시스템 **합니다.** 음성 **통화 요금제도** 할당하지 말아야 합니다. 그러나 통화 요금제에 Microsoft 365 Office 365 또는 Microsoft 365 Office 365 사용자에 대해 통화 요금제 또는 국내 및 국제 통화 요금제 라이선스를 할당해야 합니다.   라이선스 [비즈니스용 Skype 및 Microsoft Teams 할당을 참조합니다.](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)

> [!NOTE]
> 이보다 더 많은 전화 번호가 필요한 경우 비즈니스 제품에 대한 지원에 [문의하세요 - 관리자 도움말](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>관련 항목
[전화 번호 전송 자주 묻는 질문](/microsoftteams/transferring-phone-numbers-common-questions)

[통화 계획에 사용되는 다양한 종류의 전화 번호](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[조직의 전화 번호 관리](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[긴급 통화 사용 약관](/microsoftteams/emergency-calling-terms-and-conditions)

[비즈니스용 Skype 온라인: 긴급 통화 고지 사항 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
