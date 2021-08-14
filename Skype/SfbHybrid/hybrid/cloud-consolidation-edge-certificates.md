---
title: 에지 인증서 업데이트
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
description: 이 부록에는 에지 인증서를 클라우드 통합의 일부로 업데이트하기 위한 자세한 단계가 Teams 비즈니스용 Skype.
ms.openlocfilehash: 7370fe6949c471a6aad9b45ee246f1565b43bdb465eba2110a03f53afa69fe28
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54330632"
---
# <a name="update-the-edge-certificate"></a>에지 인증서 업데이트

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


에지 인증서를 업데이트하는 것은 SipDomain1이 있는 프레미스 환경이 SipDomain2를 사용하여 클라우드 환경에 가입하고 두 SIP 도메인의 공유 주소 공간 환경에서 적절한 라우팅을 보장하기 위한 핵심 단계입니다. 이 단계를 수행할 [](cloud-consolidation.md) 수 있는 컨텍스트는 Teams 및 비즈니스용 Skype 클라우드 통합의 14단계를 참조합니다. 이 예제에서 SipDomain1은 AcquiredCompany입니다. <span> com 및 SipDomain2는 OriginalCompany입니다. <span> com.

모든 onmicrosoft를 제외한 순수 온라인 테넌트에 있는 모든 SIP 도메인을 포함하려면 사내 환경의 모든 에지 서버에 있는 인증서의 SAN(주체 대체 이름)을 업데이트해야 합니다. <span> com 도메인)을(를) "sip. \<domain> ".  이 예제에서는 sip입니다. OriginalCompany. <span> com. 이 단계는 사용자를 클라우드로 마이그레이션하기 전에 먼저 해야 합니다.

**단계:**

1.  클라우드 환경의 모든 SIP 도메인(*.onmicrosoft.com 도메인 제외)에 대한 SAN의 모든 기존 항목이 있는 에지의 새 외부 에지 인증서를 "sip. <DomainName> ".
2.  인증서를 각 에지 서버에 로컬로 설치하고 각 에지 Skype 에지 서비스에 할당합니다.  자세한 단계는 [Deploy Edge Service in 비즈니스용 Skype 서버 2015의 "외부 에지 인터페이스 인증서" 섹션을 참조하십시오.](../../SfbServer/deploy/deploy-edge-server/deploy-edge-servers.md)
3.  각 에지 서버에서 에지 서비스를 다시 시작합니다. 다음 PowerShell 명령을 사용하여 단일 상자에 대해 이 작업을 할 수 있습니다.

    ```PowerShell
    Stop-CsWindowsService
    Start-CsWindowsService
    ```

## <a name="see-also"></a>참고 항목

[비즈니스 및 Teams 클라우드 비즈니스용 Skype](cloud-consolidation.md)