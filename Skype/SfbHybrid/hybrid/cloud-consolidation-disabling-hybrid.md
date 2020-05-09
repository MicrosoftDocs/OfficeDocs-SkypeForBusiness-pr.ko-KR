---
title: 클라우드로의 마이그레이션을 완료하기 위해 하이브리드를 비활성화
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
description: 이 부록에는 팀 및 비즈니스용 Skype에 대 한 클라우드 통합의 일부로 서 하이브리드를 사용 하지 않도록 설정 하는 자세한 단계가 포함 되어 있습니다.
ms.openlocfilehash: c6d042095298f6cab8d9474a521b9362ece13e0d
ms.sourcegitcommit: 0dda90122769385529f78f70b0467848da97e5ec
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/09/2020
ms.locfileid: "44173974"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>클라우드로의 마이그레이션을 완료하기 위해 하이브리드를 비활성화

모든 사용자를 온-프레미스에서 클라우드로 이동한 후에는 온-프레미스 비즈니스용 Skype 배포를 해제할 수 있습니다. 하드웨어를 제거하는 것 외에 중요한 단계는 하이브리드를 비활성화하여 Office 365에서 온-프레미스 배포를 논리적으로 분리하는 것입니다. 하이브리드를 사용 하지 않도록 설정 하는 단계는 3 단계로 구성 됩니다.

- Office 365를 가리키도록 DNS 레코드를 업데이트합니다.
- Office 365 조 직에서 도메인 분할을 사용 하지 않도록 설정 합니다.
- 온-프레미스에서 Office 365와 통신 하는 기능을 사용 하지 않도록 설정 합니다.

이러한 단계는 하나의 단위로 함께 수행 해야 합니다. 세부 정보는 아래에 나와 있습니다. 또한 온-프레미스 배포의 연결이 끊어지면 마이그레이션된 사용자의 전화 번호를 관리 하기 위한 지침이 제공 됩니다.

> [!Important] 
>Azure AD를 통해 Active Directory sync의 Msrtcsip-gateways 특성을 Azure AD에 연결 하는 작업을 계속 수행 해야 합니다.  이 기능을 지원 하지 않으면 이러한 특성을 지우지 않습니다.  온-프레미스 환경에서 사용 안 함-CsUser를 실행 하지 마십시오. 사용자의 SIP 주소를 수정 해야 하는 경우 온-프레미스 Active Directory에서이 작업을 수행 하 고 아래 설명 된 대로 Azure ad를 통해 Azure AD를 통해이 변경 내용을 동기화 하도록 합니다. 마찬가지로 전화 번호를 변경 해야 하는 경우 사용자의 LineURI가 이미 온-프레미스에 정의 되어 있는 경우 온-프레미스 Active Directory에서이를 수정 해야 합니다.
>온-프레미스에서 마이그레이션한 후 온-프레미스 Msrtcsip-gateways 특성을 지우면 사용자에 대 한 서비스가 손실 될 수 있습니다.



1.  *Office 365를 가리키도록 DNS를 업데이트 합니다.*
비즈니스용 Skype 레코드가 온-프레미스 배포 대신 Office 365를 가리키도록 온-프레미스 조직에 대 한 조직의 기존 외부 DNS 레코드를 업데이트 해야 합니다. 특히 다음 사항에 유의합니다.

    |레코드 유형|이름|TTL|값|용도|
    |---|---|---|---|---|
    |SRV|_sipfederationtls _tcp|3600|100 1 5061 sipfed.online.lync.com>. <span>com|페더레이션을 사용 하도록 설정|
    |SRV|_sip _tls|3600|100 1 443 sipdir.online.lync.com>. <span>com|비즈니스용 Skype 사용자에 게 필요 합니다.|
    |CNAME| lyncdiscover|   3600|   webdir. s e t. <span>com|비즈니스용 Skype 사용자에 게 필요 합니다.|
    |CNAME| sip|    3600|   sipdir.online.lync.com>. <span>com|이전 레거시 SIP 전화에만 필요 합니다.|

    또한 모임 또는 전화 걸기 (있는 경우)에 대 한 CNAME 레코드를 삭제할 수 있습니다.

    > [!Note] 
    > 드문 경우에는 조직에 대해 온-프레미스에서 Office 365로 DNS를 변경 하면 다른 조직이 페더레이션 구성을 업데이트할 때까지 다른 조직과의 페더레이션이 작동 하지 않을 수 있습니다.
    >
    > - 이전 직접 페더레이션 모델 (허용 된 파트너 서버 라고도 함)을 사용 하는 모든 페더레이션 조직에서는 프록시 FQDN을 제거 하기 위해 조직에 대해 허용 되는 도메인 항목을 업데이트 해야 합니다. 이 레거시 페더레이션 모델은 DNS SRV 레코드를 기반으로 하지 않으므로 이러한 구성은 조직이 클라우드로 이동한 후에 최신 상태가 되지 않게 됩니다.
    > 
    > - Sipfed.online.lync.com>에 대해 호스팅 공급자가 사용 하도록 설정 되지 않은 페더레이션 조직입니다. <span>com은 해당 구성을 사용 하도록 구성 해야 합니다. 이 상황은 페더레이션 조직이 전적으로 온-프레미스이 고 하이브리드 또는 온라인 테 넌 트와도 페더레이션 되지 않은 경우에만 가능 합니다. 이러한 경우 이러한 조직과의 페더레이션은 호스팅 공급자를 사용 하도록 설정할 때까지 작동 하지 않습니다.
    >
    > 페더레이션 파트너가 직접 페더레이션을 사용 하 고 있거나 온라인 또는 하이브리드 조직과 페더레이션 되지 않은 것으로 의심 되는 경우 클라우드로의 마이그레이션을 완료 하기 위해 준비 하는 것과 관련 하 여이에 대 한 정보를 보내 드릴 것을 권장 합니다.

2.  *Office 365 조 직에서 공유 SIP 주소 공간을 사용 하지 않도록 설정 합니다.*
아래 명령은 비즈니스용 Skype Online PowerShell 창에서 수행 해야 합니다.

    ```PowerShell
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  *온-프레미스에서 Office 365와 통신 하는 기능을 사용 하지 않도록 설정 합니다.*  
아래 명령은 온-프레미스 PowerShell 창에서 수행 해야 합니다.

    ```PowerShell
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
    ```

### <a name="manage-sip-addresses-and-phone-numbers-for-users-who-were-migrated-from-on-premises"></a>온-프레미스에서 마이그레이션된 사용자에 대 한 sip 주소 및 전화 번호 관리

관리자는 온-프레미스 배포를 해제 한 후에도 이전에 비즈니스용 Skype 서버에서 클라우드로 이동한 사용자를 관리할 수 있습니다. 사용자의 SIP 주소 또는 사용자의 회선 URI를 변경 하거나, SIP 주소 또는 줄 URI가 온-프레미스 Active Directory에 이미 정의 되어 있는 경우 온-프레미스 Active Directory에서이 작업을 수행 하 고 값이 Azure AD로 흐르도록 해야 합니다. 여기에는 온-프레미스 비즈니스용 Skype 서버가 필요 하지 않습니다. 대신, Active Directory 사용자 및 컴퓨터 MMC 스냅인을 사용 하거나 PowerShell을 사용 하 여 온-프레미스 Active Directory에서 직접 이러한 특성을 수정할 수 있습니다. MMC 스냅인을 사용 하는 경우 사용자의 속성 페이지를 열고 특성 편집기 탭을 클릭 한 다음 수정할 적절 한 특성을 찾습니다.

- 사용자의 SIP 주소를 수정 하려면를 `msRTCSIP-PrimaryUserAddress`수정 합니다. 또한 특성에 `ProxyAddresses` sip 값이 포함 되어 있으면의 `msRTCSIP-PrimaryUserAddress`새 값과 일치 하도록 sip 값을 업데이트 합니다. SIP 값이 포함 되어 있지 않은 경우에는 비워 둘 수 있습니다.

- 사용자의 전화 번호를 수정 하려면 `msRTCSIP-Line` *이미 값이 있는 경우*수정 합니다.

  ![Active Directory 사용자 및 컴퓨터 도구](../media/disable-hybrid-1.png)
  
이전에 사용자가 이동 하기 전에 온-프레미스 `LineURI` 에 대 한 값을 갖고 있지 않은 경우 비즈니스용 Skype Online PowerShell 모듈에서-`onpremLineUri` [csuser cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) 의-Parameter를 사용 하 여 lineuri를 수정할 수 있습니다.


## <a name="see-also"></a>참고 항목

[팀 및 비즈니스용 Skype에 대 한 클라우드 통합](cloud-consolidation.md)
