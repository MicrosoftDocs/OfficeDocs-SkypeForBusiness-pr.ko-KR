---
title: Teams 전용으로의 마이그레이션을 완료하기 위해 하이브리드 비활성화
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
ms.localizationpriority: medium
description: 이 문서에는 클라우드 통합 및 클라우드 통합의 일부로 하이브리드를 Teams 비즈니스용 Skype.
ms.openlocfilehash: 06d8980a14944004b22fbacc0aecef453d49123e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619314"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-teams-only"></a>하이브리드 구성을 사용하지 않도록 설정하여 하이브리드 구성만 Teams 완료 

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


이 문서에서는 하이브리드 구성을 해제하기 전에 하이브리드 구성을 사용하지 않도록 설정하는 비즈니스용 Skype 설명되어 있습니다. 이 단계는 다음 단계 중 2단계로, 프레미스 환경을 해제합니다.

- 1단계. 필요한 모든 사용자를 프레미스에서 [온라인으로 이동](decommission-move-on-prem-users.md)

- **2단계. 하이브리드 구성을 사용하지 않도록 설정** (이 문서)

- 3단계. [하이브리드 응용 프로그램 끝점을](decommission-move-on-prem-endpoints.md)온라인 프레미스에서 온라인으로 마이그레이션합니다.

- 4단계. [배포 에서 프레미스 비즈니스용 Skype 제거합니다.](decommission-remove-on-prem.md)

> [!NOTE]
> 2단계와 3단계 완료 사이에 기존 하이브리드 응용 프로그램 끝점을 검색할 수 없는 것이기 때문에 2단계와 3단계는 동일한 유지 관리 기간에서 수행해야 합니다.


## <a name="summary"></a>요약

모든 사용자를 비즈니스용 Skype 프레미스에서 Teams Microsoft 365 배포를 해제할 비즈니스용 Skype 있습니다.

하이브리드 배포를 해제하고 비즈니스용 Skype 배포를 해제하고 하드웨어를 제거하기 전에 하이브리드를 해제하여 Microsoft 365 배포와 논리적으로 구분해야 합니다. 하이브리드를 비동기화하는 단계는 다음 네 단계로 구성됩니다.

1. [을(를) 지점으로 하여 DNS 레코드를 Microsoft 365.](#update-dns-to-point-to-microsoft-365)

2. 조직의 동시 사용 모드를 을 로 [Teams 변경합니다.](#change-the-coexistence-mode-for-your-organization-to-teams-only)

3. 조직에서 공유 sip 주소 공간("분할 [도메인"이라고도 하는)을 사용하지 Microsoft 365 합니다.](#disable-shared-sip-address-space-in-microsoft-365-organization)

4. [프레미스 및 프레미스 간의 통신을 사용하지 않도록 Microsoft 365](#disable-communication-between-on-premises-and-microsoft-365)

이러한 단계는 온-프레미스 배포를 논리적으로 비즈니스용 Skype 서버 Microsoft 365 조직이 완전히 Teams 전용이 되도록 합니다. 이러한 단계를 완료한 후 를 해제한 후 특성을 관리하는 방법 결정에 참조된 두 가지 방법 중 하나를 사용하여 비즈니스용 Skype 배포를 해제할 수 [있습니다.](cloud-consolidation-managing-attributes.md)

> [!Important] 
> 이 논리적 분리가 완료되면, 사내 Active Directory의 msRTCSIP 특성은 여전히 값을 가지며 Azure AD 계정을 통해 Azure AD로 커넥트 계속 동기화합니다. 사내 환경을 해제하는 방법은 이러한 특성을 그대로 두는지 아니면 먼저 해당 특성을 On-프레미스 Active Directory에서 지우는지 여부에 따라 결정됩니다. 사내에서 마이그레이션한 후 사내 msRTCSIP 특성을 지우면 사용자에 대한 서비스가 손실될 수 있습니다. 두 가지 해제 방법의 세부 정보 및 장단점은 해지 후 특성을 관리하는 방법 결정에 [설명되어 있습니다.](cloud-consolidation-managing-attributes.md)

## <a name="update-dns-to-point-to-microsoft-365"></a>DNS를 업데이트하여 Microsoft 365

비즈니스용 Skype 레코드가 Microsoft 365 대신 조직의 외부 DNS를 업데이트해야 합니다. 

또한 meet 또는 dialin(있는 경우)에 대한 CNAME 레코드를 삭제할 수 있습니다. 마지막으로 내부 네트워크에서 비즈니스용 Skype DNS 레코드를 제거해야 합니다.

DNS 레코드 업데이트에 대한 자세한 내용은 [Update DNS entries to enable your organization to be all Teams.](decommission-manage-dns-entries.md)

## <a name="change-the-coexistence-mode-for-your-organization-to-teams-only"></a>조직의 동시 사용 모드를 2016만 Teams 변경

이 단계를 통해 조직의 새 사용자가 항상 사용자 전용 사용자로 Teams 있습니다. 

테넌트 모드를 Teams 1단계에서 누락된 모든 사내 DNS 레코드가 존재하는지 자동으로 확인하고 출력에서 이러한 레코드를 식별합니다. 테넌트 모드를 Teams 조직의 모든 DNS 레코드가 업데이트될 때까지만 성공하지 않습니다. 

테넌트 모드를 Teams PowerShell 창에서만 Teams 실행합니다.

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
```

또는 "Teams 설정" -> "업그레이드" 아래에서 Teams 관리 센터를 사용하여 테넌트 공존 모드를 TeamsOnly로 변경할 Teams 수 있습니다.    

## <a name="disable-shared-sip-address-space-in-microsoft-365-organization"></a>조직에서 공유 sip 주소 Microsoft 365 사용하지 않도록 설정
    
공유 sip 주소 공간을 사용하지 않도록 설정하기 위해 PowerShell 창의 Teams 실행합니다.

```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
```
 
## <a name="disable-communication-between-on-premises-and-microsoft-365"></a>프레미스 및 프레미스 간의 통신을 사용하지 않도록 Microsoft 365

On-premises environment and Microsoft 365, run the following command from an on-premises PowerShell window:

```PowerShell
Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
```


## <a name="see-also"></a>참고 항목

- [비즈니스 및 Teams 클라우드 비즈니스용 Skype](cloud-consolidation.md)

- [온-프레미스 비즈니스용 Skype 환경 해제](decommission-on-prem-overview.md)

