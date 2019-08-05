---
title: 클라우드로 마이그레이션을 완료 하기 위해 하이브리드을 사용 하지 않도록 설정
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
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 이 부록에는 비즈니스용 Skype를 위한 클라우드 통합의 일부로 하이브리드을 사용 하지 않도록 설정 하는 단계에 대 한 자세한 단계가 포함 되어 있습니다.
ms.openlocfilehash: 805010aa16ca8159b5e274847ca7ca2b296f214d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185505"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>클라우드로 마이그레이션을 완료 하기 위해 하이브리드을 사용 하지 않도록 설정

모든 사용자를 온-프레미스에서 클라우드로 이동한 후에는 온-프레미스 Skype 비즈니스 배포를 해제할 수 있습니다. 하드웨어를 제거 하는 것 외에도, 하이브리드을 사용 하지 않도록 설정 하 여 Office 365에서 온-프레미스 배포를 논리적으로 구분 하는 것이 중요 합니다. 하이브리드을 사용 하지 않도록 설정 하는 단계는 3 단계로 이루어집니다.

1. Office 365를 가리키도록 DNS 레코드를 업데이트 합니다.
2. Office 365 테 넌 트에서 도메인 분할을 사용 하지 않도록 설정 합니다.
3. Office 365와 통신 하기 위해 프레미스의 기능을 사용 하지 않도록 설정 합니다.


이러한 단계는 하나의 단위로 함께 수행 해야 합니다. 세부 정보는 아래에서 제공 합니다.

> [!Note] 
> 드문 경우이 든 조직에서 DNS를 가리키는 Office 365를 사용 하 여 다른 조직이 페더레이션 구성을 업데이트할 때까지 다른 조직과 페더레이션 하는 것을 중지 시킬 수 있습니다.<ul><li>
이전 직접 페더레이션 모델 (허용 된 파트너 서버 라고도 함)을 사용 하는 모든 페더레이션 조직에서는 해당 조직에 대해 허용 된 도메인 항목을 업데이트 하 여 프록시 FQDN을 제거 해야 합니다. 이 레거시 페더레이션 모델은 DNS SRV 레코드를 기반으로 하지 않으므로 이러한 구성은 조직이 클라우드로 이동 하 고 나면 오래 된 것이 됩니다. </li><li>Sipfed에 대해 사용 하도록 설정 된 호스팅 공급자가 없는 모든 페더레이션 조직입니다. <span>이 기능을 사용 하도록 설정 하려면 com에서 구성을 업데이트 해야 합니다. 이 상황은 페더레이션 조직이 전적으로 구내이 고 하이브리드 또는 온라인 테 넌 트와 페더레이션 되지 않은 경우에만 가능 합니다. 이러한 경우 이러한 조직과의 페더레이션이 호스팅 공급자를 사용 하도록 설정 해야 작동 합니다.</li></ul>페더레이션 파트너가 직접 페더레이션 또는 온라인 또는 하이브리드 조직과 페더레이션 할 수 있다고 의심 되는 경우 클라우드로의 마이그레이션을 완료 하기 위해 해당 사용자에 게이에 대 한 통신을 보내는 것이 좋습니다.

1.  *Office 365를 가리키도록 DNS를 업데이트 합니다.*
온-프레미스 조직에 대 한 조직의 외부 DNS는 온-프레미스 배포 대신 Office 365를 가리키도록 비즈니스용 Skype 레코드를 업데이트 해야 합니다. 개발

    |레코드 종류|이름|TTL|값|
    |---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100 1 5061 sipfed. 온라인. i a a. <span>com|
    |SRV|_ sip. tls|3600|100 1 443 sipdir. 온라인. i a a. <span>com|
    |CNAME| lyncdiscover|   3600|   webdir. 온라인. i a lync. <span>com|
    |CNAME| sip|    3600|   sipdir. 온라인. i a a. <span>com|
    |CNAME| 시켜|   3600|   webdir. 온라인. i a lync. <span>com|
    |CNAME| 전화 접속  |3600|  webdir. 온라인. i a lync. <span>com|

2.  *Office 365 테 넌 트에서 공유 SIP 주소 공간을 사용 하지 않도록 설정 합니다.*
아래 명령은 비즈니스용 Skype Online PowerShell 창에서 수행 해야 합니다.

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  *Office 365와 통신 하기 위해 프레미스의 기능을 사용 하지 않도록 설정 합니다.*  
아래 명령은 온-프레미스 PowerShell 창에서 수행 해야 합니다.  이전에 비즈니스용 Skype Online 세션을 가져온 적이 있는 경우 새 비즈니스용 Skype PowerShell 세션을 시작 합니다.

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

## <a name="see-also"></a>참고 항목

[팀 및 비즈니스용 Skype에 대 한 클라우드 통합](cloud-consolidation.md)