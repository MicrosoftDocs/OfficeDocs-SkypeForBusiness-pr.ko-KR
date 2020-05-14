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
description: PSTN 통화에 대 한 통화 요금제의 알려진 문제 및이에 대해 수행할 수 있는 작업에 대해 알아봅니다.
ms.openlocfilehash: 3a97057f61c154ded83b85becbfcf53dc2b4bc78
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220738"
---
# <a name="calling-plans-known-issues"></a>통화 플랜 알려진 문제

통화 요금제는 비즈니스용 Skype Online에 있는 새로운 기능입니다. 다음은 추적 되 고 활발 하 게 조사 되는 최신 문제입니다. 이후 빌드에서 기능을 업데이트 하면 문제가 해결 될 수 있습니다.
  
## <a name="calling-plans-known-issues"></a>통화 플랜 알려진 문제

|**알려진 문제**|**설명**|
|:-----|:-----|
|기술 미리 보기 라이선스에서 통화 요금제의 프로덕션 라이선스로 전환 하면 라이선스가 자동으로 업데이트 되지 않습니다.  <br/> |새 라이선스를 먼저 구입 하 여 사용자에 게 할당할 수 있도록 준비 합니다. 사용자의 프로 모션 (기술 미리 보기) 라이선스를 제거 하 고 **즉시** 사용자에 게 새 **국내 통화 계획** 및/또는 **국내 및 국제 통화 요금제** 라이선스를 할당 합니다. <br/> 여러 사용자의 라이선스를 제거 하 고 추가 하는 경우 Windows PowerShell을 사용 하는 모든 사용자의 라이선스를 제거 하 고 **즉시** windows powershell을 사용 하는 모든 사용자에 대 한 라이선스를 할당 하는 것이 매우 중요 합니다. 이렇게 하면 대용량 사용자 라이선스 할당을 처리할 때 서비스가 중단 되지 않도록 할 수 있습니다. 샘플 PowerShell 스크립트는 [비즈니스용 Skype 및 Microsoft 팀 라이선스 할당](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)을 참조 하세요.  <br/> **참고:** 하이브리드 사용자에 대 한 온-프레미스 PSTN 연결을 사용 하는 경우에는 **전화 시스템** 라이선스 *만* 할당 해야 합니다. 음성 통화 **요금제도 지정 해서는 안 됩니다** . Microsoft 365 또는 Office 365에 있는 사용자에 대해 Microsoft 365 또는 Office 365에서 전화 플랜을 사용 하도록 설정 하는 경우에도 해당 사용자에 대해 **국내 통화 요금제** 또는 **국내 및 국제 통화 요금제** 라이선스를 할당 해야 합니다. [비즈니스용 Skype 및 Microsoft 팀 라이선스 할당](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)을 참조 하세요.

> [!NOTE]
> 이 보다 더 많은 전화 번호를 받으려면 [비즈니스 제품에 대 한 고객 지원에 문의-관리자 도움말](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) 을 참조 하세요.         |
   
## <a name="related-topics"></a>관련 항목
[전화 번호 전송 자주 묻는 질문](/microsoftteams/transferring-phone-numbers-common-questions)

[통화 요금제에 사용 되는 다른 종류의 전화 번호](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[조직의 전화 번호 관리](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[긴급 통화 사용 약관](/microsoftteams/emergency-calling-terms-and-conditions)

[비즈니스용 Skype Online: 비상 전화 부인 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
