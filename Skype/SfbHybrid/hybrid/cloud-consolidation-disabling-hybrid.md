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
description: 이 부록에는 Teams 및 비즈니스용 Skype에 대한 클라우드 통합의 일부로 하이브리드를 사용 안 하게 하는 자세한 단계가 포함되어 있습니다.
ms.openlocfilehash: 93aad1ea230d9edbb81673a3ddabc7088b06d422
ms.sourcegitcommit: a28232f16bfefe6414d1f5a54d5f8c8665eb0e23
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277252"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a>클라우드로의 마이그레이션을 완료하기 위해 하이브리드를 비활성화

모든 사용자를 온-프레미스에서 클라우드로 이동한 후에는 온-프레미스 비즈니스용 Skype 배포를 해제할 수 있습니다. 하드웨어를 제거하는 것 외에도 중요한 단계는 하이브리드를 사용 안 하여 Microsoft 365 또는 Office 365에서 논리적으로 이를 분리하는 것입니다. 하이브리드를 비우는 단계는 다음 3단계로 구성됩니다.

1. Microsoft 365 또는 Office 365를 지점으로 DNS 레코드를 업데이트합니다.

2. Microsoft 365 또는 Office 365 조직에서 분할 도메인을 사용하지 않도록 설정

3. Microsoft 365 또는 Office 365와 통신하는 데 사용할 수 있는 기능을 On-프레미스에서 사용하지 않도록 설정

이러한 단계는 한 단위로 함께 수행해야 합니다. 자세한 내용은 아래를 참조하십시오. 또한 마이그레이션된 사용자의 전화 번호를 관리하는 데 대한 지침도 제공됩니다.

이러한 단계가 완료되면 더 이상 비즈니스용 Skype 서버가 사용되지 않습니다. 이러한 서버를 다시 이미지화할 수 있습니다.

> [!Important] 
>Azure AD Connect를 통해 Active Directory의 msRTCSIP 특성이 Azure AD에 동기화될 수 있습니다.  지원이 지시하지 않는 한 이러한 특성을 지우지 않습니다.  모든 Disable-CsUser 환경에서는 실행하지 않습니다. 사용자의 SIP 주소를 수정해야 하는 경우, 이 작업을 On-premises Active Directory에서 이행하고 아래 설명된 Azure AD Connect를 통해 Azure AD에 이 변경이 동기화될 수 있도록 합니다. 마찬가지로 전화 번호를 변경해야 하는 경우 사용자의 LineURI가 이미 On-premises에 정의되어 있는 경우 이 변경을 On-premises Active Directory에서 수정해야 합니다.
>사용자가온-프레미스에서 마이그레이션한 후 해당 특성을 지우면 사용자에 대한 서비스가 손실될 수 있습니다.


1.  *Microsoft 365 또는 Office 365를 지점으로 DNS를 업데이트합니다.*
비즈니스용 Skype 레코드가 Microsoft 365 또는 Office 365 대신 Microsoft 365를 지원할 수 있도록 조직에 대한 조직의 외부 DNS를 업데이트해야 합니다. 특히 다음 사항에 유의합니다.

    |레코드 유형|이름|TTL|값|
    |---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100 1 5061 sipfed.online.lync. <span> com|
    |SRV|_sip._tls|3600|100 1 443 sipdir.online.lync. <span> com|
    |CNAME| lyncdiscover|   3600|   webdir.online.lync. <span> com|
    |CNAME| sip|    3600|   sipdir.online.lync. <span> com|
    |CNAME| meet|   3600|   webdir.online.lync. <span> com|
    |CNAME| dialin  |3600|  webdir.online.lync. <span> com|

    또한 meet 또는 dialin(있는 경우)에 대한 CNAME 레코드를 삭제할 수 있습니다. 마지막으로 내부 네트워크에서 비즈니스용 Skype에 대한 DNS 레코드를 제거해야 합니다.

    > [!Note] 
    > 드물지만 DNS를 조직에 대한 Office 365를 설정하는 데 DNS를 변경하면 다른 조직이 페더링 구성을 업데이트할 때까지 일부 다른 조직과의 페더링이 중지될 수 있습니다.
    >
    > - 이전 Direct Federation 모델(허용 파트너 서버라고도 알려지음)을 사용하는 페더타 조직은 해당 조직에 대해 허용되는 도메인 항목을 업데이트하여 프록시 FQDN을 제거해야 합니다. 이 레거시 페더ation 모델은 DNS SRV 레코드를 기반으로 하지 않습니다. 따라서 조직이 클라우드로 이동하면 이러한 구성이 최신이 됩니다.
    > 
    > - sipfed.online.lync에 <span> 대해 호스팅 공급자를 사용하도록 설정하지 않은 페더링된 조직 com에서 구성을 업데이트하여 사용하도록 설정해야 합니다. 이 상황은 페더러이트 조직이 전적으로 하이브리드 또는 온라인 테넌트와 페더러이트된 적이 없는 경우만 가능합니다. 이러한 경우 호스팅 공급자를 사용하도록 설정해야 이러한 조직과의 페더링이 작동하지 않습니다.
    >
    > 페더러이트 파트너 중 어느 한 명도 직접 페더ation을 사용 중일 수 있는 것으로 의심되거나 온라인 또는 하이브리드 조직과 페더전되지 않은 것으로 의심되는 경우 클라우드로의 마이그레이션을 완료할 준비를 할 때 이에 대한 커뮤니케이션을 해당 파트너에게 보낼 것을 제안합니다.


2.  *Microsoft 365 또는 Office 365 조직에서 공유 SIP 주소 공간을 사용하지 않도록 설정*
아래 명령은 비즈니스용 Skype Online PowerShell 창에서 수행해야 합니다.

    ```PowerShell
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  *Microsoft 365 또는 Office 365와 통신하는 데 사용할 수 있는 기능을 On-프레미스에서 사용하지 않도록 설정*  
아래 명령은 다음을 수행해야 합니다.

    ```PowerShell
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
    ```

### <a name="manage-sip-addresses-and-phone-numbers-for-users-who-were-migrated-from-on-premises"></a>On-premises에서 마이그레이션된 사용자의 sip 주소 및 전화 번호 관리

관리자는 이전의 비즈니스용 Skype 서버에서 클라우드로 이동한 사용자를 관리할 수 있습니다. 이 경우, 이 경우, 해당 사용자는 프레미스 배포가 해제된 후에도 관리할 수 있습니다. 사용자의 SIP 주소 또는 사용자의 줄 URI를 변경하려는 경우(그리고 SIP 주소 또는 줄 URI가 이미 On-프레미스 Active Directory에 정의되어 있는 경우) 이 작업을 통해 값이 Azure AD로 흐르게 해야 합니다. 이 서버에는 비즈니스용 Skype 서버가 필요하지 않습니다. 대신 Active Directory 사용자 및 컴퓨터 MMC 스냅인을 사용하거나 PowerShell을 사용하여 이러한 특성을 직접 On-프레미스 Active Directory에서 수정할 수 있습니다. MMC 스냅인을 사용하는 경우 사용자의 속성 페이지를 열고 특성 편집기 탭을 클릭한 다음 수정할 적절한 특성을 찾아야 합니다.

- 사용자의 SIP 주소를 수정하려면 `msRTCSIP-PrimaryUserAddress` . 또한 특성에 SIP 값이 포함되어 있는 경우 해당 SIP 값을 새 값과 일치하게 `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` 업데이트합니다. SIP 값이 포함되어 있지 않은 경우 비워 두면 됩니다.

- 사용자의 전화 번호를 수정하려면 값이 이미 `msRTCSIP-Line` *있는 경우 수정합니다.*

  ![Active Directory 사용자 및 컴퓨터 도구](../media/disable-hybrid-1.png)
  
사용자가 이동하기 전에 원래의 값이 없는 경우 비즈니스용 Skype Online PowerShell 모듈의 `LineURI` `onpremLineUri` [Set-CsUser cmdlet에서](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) - 매개 변수를 사용하여 LineURI를 수정할 수 있습니다.


## <a name="see-also"></a>참고 항목

[Teams 및 비즈니스용 Skype를 위한 클라우드 통합](cloud-consolidation.md)
