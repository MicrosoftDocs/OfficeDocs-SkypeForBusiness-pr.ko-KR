---
title: 클라우드로의 마이그레이션을 완료 하기 위해 하이브리드를 사용 하지 않도록 설정
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
description: 이 부록에는 팀 및 비즈니스용 Skype에 대 한 클라우드 통합의 일부로 서 하이브리드를 사용 하지 않도록 설정 하는 자세한 단계가 포함 되어 있습니다.
ms.openlocfilehash: f78c5a5cb792ecdb39125292c531097219dc58e3
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "37924969"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>클라우드로의 마이그레이션을 완료 하기 위해 하이브리드를 사용 하지 않도록 설정

모든 사용자를 온-프레미스에서 클라우드로 이동한 후 온-프레미스 비즈니스용 Skype 배포를 해제할 수 있습니다. 하드웨어를 제거 하는 것 외에도 하이브리드를 사용 하지 않도록 설정 하 여 온-프레미스 배포를 Office 365에서 논리적으로 구분 하는 것이 중요 합니다. 하이브리드를 사용 하지 않도록 설정 하는 단계는 3 단계로 구성 됩니다.

1. Office 365를 가리키도록 DNS 레코드를 업데이트 합니다.
2. Office 365 테 넌 트에서 split 도메인을 사용 하지 않도록 설정 합니다.
3. 프레미스의 Office 365 통신 기능을 사용 하지 않도록 설정 합니다.


이러한 단계는 하나의 단위로 함께 수행 해야 합니다. 세부 정보는 아래에 나와 있습니다. 또한 온-프레미스 배포의 연결이 끊어지면 마이그레이션된 사용자의 전화 번호를 관리 하기 위한 지침이 제공 됩니다.

> [!Note] 
> 드문 경우에는 조직에 대해 온-프레미스에서 Office 365로 DNS를 변경 하면 다른 조직이 페더레이션 구성을 업데이트할 때까지 다른 조직과의 페더레이션이 작동 하지 않을 수 있습니다.<ul><li>
이전 직접 페더레이션 모델 (허용 된 파트너 서버 라고도 함)을 사용 하는 모든 페더레이션 조직에서는 프록시 FQDN을 제거 하기 위해 조직에 대해 허용 되는 도메인 항목을 업데이트 해야 합니다. 이 레거시 페더레이션 모델은 DNS SRV 레코드를 기반으로 하지 않으므로 이러한 구성은 조직이 클라우드로 이동한 후에 최신 상태가 되지 않게 됩니다. </li><li>Sipfed.online.lync.com>에 대해 호스팅 공급자가 사용 하도록 설정 되지 않은 페더레이션 조직입니다. <span>com은 해당 구성을 사용 하도록 구성 해야 합니다. 이 상황은 페더레이션 조직이 전적으로 온 적이 있고 하이브리드 또는 온라인 테 넌 트와도 페더레이션 되지 않은 경우에만 가능 합니다. 이러한 경우 이러한 조직과의 페더레이션은 호스팅 공급자를 사용 하도록 설정할 때까지 작동 하지 않습니다.</li></ul>페더레이션 파트너가 직접 페더레이션을 사용 하거나 온라인 또는 하이브리드 조직과 페더레이션 되어 있다고 생각 되는 경우 클라우드로의 마이그레이션을 완료 하기 위해 준비할 때 이러한 정보를이에 대 한 통신으로 보내는 것이 좋습니다.

1.  *Office 365를 가리키도록 DNS를 업데이트 합니다.*
비즈니스용 Skype 레코드가 온-프레미스 배포 대신 Office 365를 가리키도록 온-프레미스 조직에 대 한 조직의 외부 DNS를 업데이트 해야 합니다. 특히 다음 사항에 유의합니다.

    |레코드 유형|Name|TTL|값|
    |---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100 1 5061 sipfed.online.lync.com>. <span>com|
    |SRV|_cm_tls|3600|100 1 443 sipdir.online.lync.com>. <span>com|
    |CNAME| lyncdiscover|   3600|   webdir. s e t. <span>com|
    |CNAME| sip|    3600|   sipdir.online.lync.com>. <span>com|
    |CNAME| 조건|   3600|   webdir. s e t. <span>com|
    |CNAME| dialin  |3600|  webdir. s e t. <span>com|

2.  *Office 365 테 넌 트에서 공유 SIP 주소 공간을 사용 하지 않도록 설정 합니다.*
아래 명령은 비즈니스용 Skype Online PowerShell 창에서 수행 해야 합니다.

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  *프레미스의 Office 365 통신 기능을 사용 하지 않도록 설정 합니다.*  
아래 명령은 온-프레미스 PowerShell 창에서 수행 해야 합니다.  이전에 비즈니스용 Skype Online 세션을 가져온 적이 있는 경우 비즈니스용 Skype PowerShell 세션을 새로 시작 합니다.

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

### <a name="managing-phone-numbers-for-users-who-were-migrated-from-on-premises"></a>온-프레미스에서 마이그레이션된 사용자에 대 한 전화 번호 관리

관리자는 온-프레미스 배포가 해제 된 후에도 이전에 온-프레미스 비즈니스용 Skype 서버에서 클라우드로 옮겨진 사용자를 관리할 수 있습니다. 다음과 같은 두 가지 가능성이 있습니다.
1.  이동 하기 전에 사용자에 게 온-프레미스 (사용자가 Enterprise Voice를 사용할 수 있도록 설정 되어 있음)에 대 한 on-premises Uri가 있는 경우, lineURI를 변경 하려면 온-프레미스 AD에서이 작업을 수행 하 고 값이 AAD로 흐르도록 해야 합니다. 여기에는 온-프레미스 비즈니스용 Skype 서버가 필요 하지 않습니다. 대신이 특성을 온-프레미스 Active Directory에서 직접 편집 하려면 Active Directory 사용자 및 컴퓨터 MMC 스냅인을 사용 하거나 PowerShell을 통해 Msrtcsip-gateways을 수행 합니다. MMC 스냅인을 사용 하는 경우 사용자의 속성 페이지로 열고 특성 편집기 탭을 클릭 한 다음 Msrtcsip-gateways을 찾습니다.

2.  사용자가 이동 하기 전에 lineURI 온-프레미스에 대 한 값이 없는 경우 비즈니스용 Skype Online Powershell 모듈의-csuser cmdlet에서-onpremLineUri 매개 변수를 사용 하 여 LineURI를 수정할 수 있습니다.

## <a name="see-also"></a>참고 항목

[팀 및 비즈니스용 Skype에 대 한 클라우드 통합](cloud-consolidation.md)
