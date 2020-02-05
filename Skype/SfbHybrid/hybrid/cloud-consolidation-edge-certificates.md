---
title: 에 지 인증서 업데이트
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 이 부록에는 팀 및 비즈니스용 Skype에 대 한 클라우드 통합의 일환으로에 지 인증서를 업데이트 하기 위한 세부 단계가 포함 되어 있습니다.
ms.openlocfilehash: c4339eec5fa303429fdf8f42a7273c8f20f94e5b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762856"
---
# <a name="update-the-edge-certificate"></a>에 지 인증서 업데이트

에 지 인증서 업데이트는 SipDomain1을 사용 하는 온-프레미스 환경에서 SipDomain2를 사용 하 여 클라우드 환경에 참가 하 고 두 SIP 도메인 간에 공유 주소 공간 환경에 적절 한 라우팅을 보장할 수 있도록 하는 주요 단계입니다. 이 단계를 수행할 수 있는 컨텍스트는 [팀 및 비즈니스용 Skype에 대 한 클라우드 통합](cloud-consolidation.md) 의 14 단계를 참조 하세요. 이 예제에서 SipDomain1는 AcquiredCompany입니다. <span>Com 및 SipDomain2는 originalcompany입니다. <span>com

온-프레미스 환경의 모든에 지 서버에 있는 인증서의 SAN (주체 대체 이름)은 onmicrosoft를 제외 하 고 순수한 온라인 테 넌 트에 있는 모든 SIP 도메인을 포함 하도록 업데이트 해야 합니다<span> . com 도메인) ("sip. \<도메인> "입니다.  이 예제에서는 sip입니다. OriginalCompany <span>com 사용자를 클라우드로 마이그레이션하기 전에이 단계를 수행 하는 것이 중요 합니다.

**단계**

1.  모든 기존 항목과 클라우드 환경의 모든 SIP 도메인 (onmicrosoft.com 도메인 제외)에 대 한 SAN의 추가 항목을 포함 하는 Edge에 대 한 새 외부에 지 인증서를 가져옵니다 ("SIP. <DomainName>"입니다.
2.  각에 지 서버에 로컬로 인증서를 설치 하 고 각에 지 서비스에서 Skype에 지 서비스에 할당 합니다.  자세한 단계는 [비즈니스용 Skype 서버 2015의 배포에 지 서비스](https://technet.microsoft.com/library/dn951368.aspx)의 "외부에 지 인터페이스 인증서" 섹션을 참조 하세요.
3.  각에 지 서버에서에 지 서비스를 다시 시작 합니다. 다음 PowerShell 명령을 사용 하 여 단일 상자에 대해이 작업을 수행할 수 있습니다.

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>참고 항목

[팀 및 비즈니스용 Skype에 대 한 클라우드 통합](cloud-consolidation.md)
