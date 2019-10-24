---
title: 통화 계획의 알려진 문제
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
f1keywords: None
ms.custom:
- Calling Plans
description: 'Office 365 (PSTN 통화)에 대 한 통화 요금제의 알려진 문제점 및 이러한 문제에 대해 수행할 수 있는 작업에 대해 알아봅니다. '
ms.openlocfilehash: 9a6f97a93aa6c7b4e847ba1cb3280a21c473db0c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "37642935"
---
# <a name="calling-plans-known-issues"></a>통화 계획의 알려진 문제

Office 365의 통화 요금제는 비즈니스용 Skype Online에서 찾을 수 있는 새로운 기능입니다. 다음은 추적 되 고 활발 하 게 조사 되는 최신 문제입니다. Office 365 및 비즈니스용 Skype Online의 이후 빌드에서 기능이 업데이트 될 때 문제가 발생할 수 있습니다.
  
## <a name="calling-plans-known-issues"></a>통화 계획의 알려진 문제

|**알려진 문제**|**메모**|
|:-----|:-----|
|기술 미리 보기 라이선스에서 통화 요금제의 프로덕션 라이선스로 전환 하면 라이선스가 자동으로 업데이트 되지 않습니다.  <br/> |새 라이선스를 먼저 구입 하 여 사용자에 게 할당할 수 있도록 준비 합니다. 사용자의 프로 모션 (기술 미리 보기) 라이선스를 제거 하 고 **즉시** 사용자에 게 새 **국내 통화 계획** 및/또는 **국내 및 국제 통화 요금제** 라이선스를 할당 합니다. <br/> 여러 사용자의 라이선스를 제거 하 고 추가 하는 경우 Windows PowerShell을 사용 하는 모든 사용자의 라이선스를 제거 하 고 **즉시** windows powershell을 사용 하는 모든 사용자에 대 한 라이선스를 할당 하는 것이 매우 중요 합니다. 이렇게 하면 대용량 사용자 라이선스 할당을 처리할 때 서비스가 중단 되지 않도록 할 수 있습니다. 샘플 PowerShell 스크립트는 [비즈니스용 Skype 및 Microsoft 팀 라이선스 할당](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)을 참조 하세요.  <br/> **참고:** 하이브리드 사용자에 대 한 온-프레미스 PSTN 연결을 사용 하는 경우에는 **전화 시스템** 라이선스 *만* 할당 해야 합니다. 음성 통화 **요금제도 지정 해서는 안 됩니다** . 그러나 office 365에 있는 사용자에 대해 Office 365에서 통화 계획을 사용 하도록 설정 하는 경우에도 해당 사용자에 대 한 국내 **통화 요금제** 또는 **국내 및 국제 통화 요금제** 라이선스를 할당 해야 합니다. [비즈니스용 Skype 및 Microsoft 팀 라이선스 할당](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)을 참조 하세요.

> [!NOTE]
> 이 보다 더 많은 전화 번호를 받으려면 [비즈니스 제품에 대 한 고객 지원에 문의-관리자 도움말](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) 을 참조 하세요.         |
   
## <a name="related-topics"></a>관련 항목
[전화 번호 전송 일반적인 질문](/microsoftteams/transferring-phone-numbers-common-questions)

[통화 요금제에 사용 되는 다른 종류의 전화 번호](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[조직의 전화 번호 관리](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[비상 통화 약관](/microsoftteams/emergency-calling-terms-and-conditions)

[비즈니스용 Skype Online: 비상 전화 부인 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 