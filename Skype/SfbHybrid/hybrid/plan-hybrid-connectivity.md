---
title: 하이브리드 연결 | 비즈니스용 Skype 서버 Teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
description: 하이브리드 모드를 구성하여 비즈니스용 Skype 서버 Teams 하이브리드 연결을 비즈니스용 Skype 계획합니다.
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 242e365e190dcd915f7cc9f8e0989b7fc54a9206
ms.sourcegitcommit: c7b95254dec4420ba0a697fd49d11b448364c919
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2022
ms.locfileid: "63442474"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>비즈니스용 Skype 서버 하이브리드 연결 Teams

> [!Important]
> 비즈니스용 Skype Online은 2021년 이후로 사용 중지되어 온-프레미스 제품이 비즈니스용 Skype 서버 2019, 비즈니스용 Skype 서버 2015 및 Lync Server 2013도 계속 지원됩니다. 또한 Microsoft는 이러한 사내 제품과 프레미스 제품 간에 하이브리드 환경을 Microsoft Teams. 이를 통해 이러한 사내 배포가 있는 조직은 사용자를 TeamsOnly로 마이그레이션할 수 있습니다.  마지막으로 클라우드 커넥터 버전 비즈니스용 Skype 서버 더 이상 지원되지 않습니다. 사내 PSTN 연결이 필요한 고객은 [직접 라우팅을 사용해야 합니다](/MicrosoftTeams/direct-routing-landing-page).


이 항목을 통해 비즈니스용 Skype 서버 Lync Server 2013과 Lync Server 2013 간의 하이브리드 연결을 계획하는 Teams. 하이브리드 연결을 설정하는 것은 프레미스 환경을 하이브리드 환경으로 이동하는 첫 Microsoft Teams.

비즈니스용 Skype(나란히)를 이미 사용하고 있는 비즈니스용 Skype Teams 사용자가 있는 경우 해당 사용자는 비즈니스용 Skype 클라이언트의 Teams 사용자와 상호 작업을 할 수 없으며, Teams 클라이언트에서 페더러 조직의 사용자와 통신할 Teams 없습니다. Teams 기능을 사용하려면 이러한 사용자를 TeamsOnly 사용자가 되기 위해 비즈니스용 Skype 프레미스에서 클라우드로 이동해야 합니다. 이렇게 하려면 하이브리드 비즈니스용 Skype 구성해야 합니다. 사용자와 함께 사용할 Teams TeamsOnly 모드에 있는 경우 모든 사용자의 모든 수신 전화 및 채팅은 사용자의 Teams 클라이언트에 연결됩니다.

온-프레미스 비즈니스용 Skype 배포를 해제하기 전에 하이브리드 연결을 설정하고 모든 사용자를 클라우드로 이동해야 합니다.  하이브리드 연결을 설정하면 사용자를 일정에 따라 클라우드로 이동하도록 선택할 수 있습니다. 직접 라우팅을 사용하면 클라우드로 이동하는 동안과 마이그레이션이 완료된 후 온-프레미스 음성 인프라를 활용할 수 있습니다.

이 항목에서는 기존 사내 배포 및 배포 환경 간에 하이브리드 연결을 구성하는 데 필요한 인프라 및 시스템 요구 비즈니스용 Skype 서버 Teams.

이 항목을 읽고 하이브리드 연결을 구성할 준비가 되면 Configure [hybrid connectivity between 비즈니스용 Skype 서버 and Teams](configure-hybrid-connectivity.md). 구성 항목에서는 프레미스 배포와 프레미스 배포 간에 하이브리드 연결을 설정하기 위한 단계별 지침을 Teams.


## <a name="implications-of-the-retirement-of-skype-for-business-online"></a>온라인 서비스 사용 중지의 비즈니스용 Skype 의미
비즈니스용 Skype Online이 사용 중지되기 전과 후에 모두 비즈니스용 Skype 서버 사내에 있는 사용자는 Teams 사용할 수 있지만 TeamsOnly가 될 수 없습니다. (기본적으로 사내 사용자는 아일랜드 모드에 있습니다.) 사용자는 모든 인바운드 채팅 및 통화가 TeamsOnly 모드에 있는 경우 Teams, 특히 페더전, PSTN 지원 및 보장의 모든 Teams 경험할 수 있습니다. 

비즈니스용 Skype Online의 사용 중지는 비즈니스용 Skype 서버 또는 Lync Server 2013의 기존 지원 수명 주기에 영향을 미치지 않습니다.  그러나 비즈니스용 Skype Online의 사용 중지는 기존 하이브리드 조직을 포함하여 온-프레미스 비즈니스용 Skype 서버 또는 Lync Server 2013을 사용중인 고객이 클라우드로 전환하는 방법의 특정 측면에 영향을 주었다. 하이브리드를 사내에서 클라우드(예: TeamsOnly)로 전환하는 수단으로 하이브리드를 사용하는 것은 비즈니스용 Skype Online의 사용 중지의 영향을 비즈니스용 Skype.

비즈니스용 Skype Online이 사용 중지하기 전에 하이브리드 조직은 다음과 같은 세 가지 기본 유형의 사용자로 구성될 수 있습니다. 
- On-premises users (who may or not use Teams, but not in Teams Only mode) 
- TeamsOnly 외의 공존 모드가 있는 온라인 사용자
- TeamsOnly 사용자.

그러나 비즈니스용 Skype Online이 중지된 후 하이브리드 조직은 두 가지 기본 유형의 사용자로만 구성될 수 있습니다. 
- On-premises users (Who may use Teams, but not in TeamsOnly mode)
- Teams 사용자만 사용할 수 있습니다. 

조직이 비즈니스용 Skype 서버 또는 Lync Server 2013에서 Teams 이동하려면 사용 중지 전과 동일한 도구 집합을 사용하여 하이브리드를 설정하고 구성 *해야 합니다*. 사용자를 프레미스에서 TeamsOnly로 이동하는 경우 더 이상 에서 스위치를 지정할 `-MoveToTeams` 필요는 없습니다 `Move-CsUser`. 이전에는 이 스위치를 지정하지 않은 경우 사용자가 비즈니스용 Skype 서버 Online으로 전환한 비즈니스용 Skype 모드는 변경되지 않았습니다. 그러나 Skype Business Online `Move-CsUser` 이 사용 중지된 이후로 사용자를 클라우드로 이동하면 전환이 지정되어 있는지 여부에 관계없이 TeamsOnly  모드가 자동으로 할당되고 모임이 Teams 모임으로 변환됩니다.`-MoveToTeams` 이는 전환한 적이 없는 Lync Server 2013 `MoveToTeams` 이 있는 조직이 온-프레미스에서 TeamsOnly로 직접 사용자를 이동할 수 있는 것입니다. 

마찬가지로 새 사용자를 새 사용자가 Microsoft 365 아니라 Teams 모드에 관계없이 자동으로 전용 모드로 설정됩니다. 하이브리드 조직에서는 새 사용자를 Microsoft 365 사용자가 새 사용자로 라우팅할 수 있도록 새 사용자를 만들지 않고 Microsoft 365 Active Directory에 새 사용자를 만들어야 합니다.

온라인에서 사용 중지된 공존 모드는 비즈니스용 Skype 있습니다. 이전과 프레미스에 있는 계정이 있는 비즈니스용 Skype 서버 TeamsOnly를 제외한 모든 공존 모드를 할당할 수 있습니다. 그러나 사용 중지 후 온라인에 있는 사용자는 TeamsOnly만 될 수 있습니다(비즈니스용 Skype 온라인 사용자는 어떤 모드일 수도 있는 현재와 달리). 온라인에 있는 사용자에게 TeamsOnly 외의 모드를 더 이상 할당할 수 없습니다.


> [!Important]
> TeamsOnly가 아닌 사용자가 비즈니스용 Skype Online에 있는 기존 하이브리드 조직은 이러한 사용자를 가능한 한 Teams 모드로 업그레이드하는 데 집중해야 합니다. 조직에 여전히 TeamsOnly가 아닌 사용자가 비즈니스용 Skype *Online* 에 있는 경우 이러한 사용자를 TeamsOnly로 전환하기 위한 Microsoft 지원 업그레이드를 예약할 수 있습니다. **Microsoft 보조 업그레이드는 모든 사용자에게 영향을 비즈니스용 Skype 서버 않습니다.** 예약 알림은 TeamsOnly가 아닌 사용자가 온라인에서 업그레이드되기 전에 비즈니스용 Skype Online에 있는 하이브리드 고객에게 미리 Teams.

## <a name="about-shared-sip-address-space-functionality"></a>공유 SIP 주소 공간 기능

<a name="BKMK_Overview"> </a>

비즈니스용 Skype 서버 및 Teams 배포 간에 하이브리드 연결을 설정하면 일부 사용자가 온라인에 있는 Teams 수 있습니다.

이러한 유형의 구성은 공유 SIP 주소 공간 기능을 사용하며, 다음 다이어그램과 같이 contoso.com 와 같은 도메인의 사용자를 "분할 도메인"이라고도 하는 비즈니스용 Skype 서버 비즈니스용 Skype 서버 및 Teams 사용으로 분할됩니다.

![비즈니스 하이브리드용 Skype - 분할 도메인.](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

공유 SIP 주소 공간이 구성된 경우:

- Azure Active Directory 커넥트 프레미스 디렉터리와 동기화하는 데 Microsoft 365.
- 프레미스에 있는 사용자는 프레미스 서버와 비즈니스용 Skype 상호 작용합니다.
- 온라인에 있는 사용자는 사용자와 상호 작용을 Teams.
- 두 환경의 사용자가 서로 통신할 수 있습니다.
- On-premises Active Directory is authoritative. 모든 사용자를 먼저 On-premises Active Directory에서 만든 다음 Azure AD와 동기화해야 합니다. 사용자가 온라인에 있도록 하려는 경우에도 먼저 사용자를 만든 다음 사용자를 온라인으로 이동하여 사용자가 온라인에서 검색되도록 해야 합니다.

사용자를 온라인으로 이동하려면 사용자에게 Teams 라이선스와 비즈니스용 Skype(계획 2)를 할당해야 합니다. **온라인 비즈니스용 Skype 사용이 중지된 후에도 비즈니스용 Skype 필요합니다.** 사용자가 오디오 회의 또는 오디오 회의와 같은 추가 온라인 기능을 활용하려면 전화 시스템 라이선스를 할당해야 Microsoft 365.

## <a name="hybrid-connectivity-infrastructure-requirements"></a>하이브리드 연결 인프라 요구 사항

<a name="BKMK_Infrastructure"> </a>

사내 환경과 Microsoft 365 통신 서비스 간에 하이브리드 연결을 구현하려면 다음 인프라 요구 사항을 충족해야 합니다.

- 지원되는 토폴로지에서 비즈니스용 Skype 서버 또는 Lync Server의 단일 온-프레미스 배포 이 [항목의 토폴로](plan-hybrid-connectivity.md#BKMK_Topology) 지 요구 사항을 참조하세요.

- 사용자 Microsoft 365 있는 Teams.
    > [!NOTE]
    > 하이브리드 구성에 대해 단일 테넌트만 사용하여 하이브리드 배포를 사용할 수 있습니다.
    
- Azure Active Directory 커넥트 디렉터리와 동기화할 수 Microsoft 365. 자세한 내용은 [Azure AD 커넥트: 계정 및 권한을 참조하세요](/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions).

- 비즈니스용 Skype 서버 도구가 필요합니다. 이는 사용자를 사내에서 클라우드로 이동하는 데 필요합니다. 이러한 도구는 사내 배포와 인터넷에 모두 액세스할 수 있는 서버에 설치해야 합니다.
- 온라인 관리 도구. 관리 센터 또는 Teams 사용하여 Windows PowerShell 관리할 수 Teams. PowerShell을 사용하여 Teams PowerShell 모듈을 다운로드하여 Teams 설치합니다. (비즈니스용 Skype Online Connector가 사용 중지된 경우).
- 공유 SIP 주소 공간을 사용하도록 설정하고, 호스팅 공급자로 사용할 수 있도록 Microsoft 365 배포를 구성해야 합니다. 하이브리드 연결을 구성하는 데 필요한 단계에 대한 자세한 내용은 하이브리드 연결 구성 [을 참조하세요](configure-hybrid-connectivity.md).

하이브리드 연결을 구성한 후 사용자를 하이브리드 연결로 Teams. 자세한 내용은 [Move users from on-premises to Teams](move-users-from-on-premises-to-teams.md).

## <a name="server-version-requirements"></a>서버 버전 요구 사항

<a name="BKMK_Topology"> </a>

하이브리드 토폴로지와 함께 하이브리드 배포를 **Teams 지원되는** 다음 토폴로지 중 하나를 설정해야 합니다.

- 비즈니스용 Skype 서버 2019 배포 - 모든 서버에서 비즈니스용 Skype 서버 2019 실행
- 비즈니스용 Skype 서버 2015 배포 - 모든 서버에서 비즈니스용 Skype 서버 2015 실행
- Lync Server 2013을 실행하는 모든 서버가 있는 Lync Server 2013 배포  그러나 하이브리드 음성 연결이 필요한 경우 아래 설명된 혼합 버전 토폴로지 를 사용해야 합니다.
- 아래 나열된 최대 2개 서버 버전이 있는 배포:
  - 비즈니스용 Skype 서버 2015 및 비즈니스용 Skype 서버 2019
  - Lync Server 2013 및 비즈니스용 Skype 서버 2019
  - Lync Server 2013 및 비즈니스용 Skype 서버 2015

모든 토폴로지에서 하이브리드 음성이 필요한 경우 페더전 에지로 지정된 에지 서버와 SIP 페더러에 연결된 풀을 모두 2015 이상에서 실행해야 비즈니스용 Skype 합니다. 사용자가 있는 경우 Lync 2013 풀에 남아 있을 수 있습니다. 자세한 내용은 [Plan your voice solution을 참조합니다](/MicrosoftTeams/cloud-voice-landing-page).

> [!NOTE]
> - 이제는 사용자와 사용자 간의 Teams OAuth 인증 프로토콜이 필요합니다. 이전에는 OAuth가 권장되지만 필수는 아닙니다. 비즈니스용 Skype 서버 2019 및 비즈니스용 Skype 서버 2015 CU12(KB 3061064)에는 이미 OAuth가 필요 합니다. CU8에서 CU11까지 비즈니스용 Skype 서버 2015를 사용하는 경우 -UseOAuth 스위치를 전달해야 합니다. -UseOAuth 스위치는 OAuth를 사용하여 인증하거나 CU12로 업그레이드하는 것이 되도록 합니다. CU8 이전의 비즈니스용 Skype 서버 2015 버전을 사용하는 경우 CU12 이상으로 업그레이드해야 합니다. Lync Server 2013을 사용하는 경우 먼저 Lync Server 2013 누적 업데이트 10 핫픽스 5(KB 2809243) 이상으로 업그레이드해야 합니다.
> - Lync Server 2010은 Lync Server 2010에서 지원되지 Teams.


## <a name="multi-forest-support"></a>다중 포리스트 지원

<a name="BKMK_MultiForest"> </a>

Microsoft는 다음과 같은 유형의 다중 포리스트 하이브리드 시나리오를 지원합니다.

- **리소스 포리스트 토폴로지.** 이러한 유형의 토폴로지에는 비즈니스용 Skype 서버(리소스 포리스트)를 호스팅하는 포리스트가 하나 있으며, 리소스 포리스트의 비즈니스용 Skype 서버 액세스하는 하나 이상의 추가 포리스트가 있습니다. 일반적으로 사용자는 다음 요구 사항을 비즈니스용 Skype 다른 포리스트의 여러 기능에 액세스할 수 있습니다.
  - 사용자가 해당 포리스트를 호스트하는 포리스트에 제대로 비즈니스용 Skype. 하이브리드 구성에서 이는 사용자가 비활성화된 사용자 개체로 동기화되어야 하다는 의미입니다.
  - 포리스트 호스팅 비즈니스용 Skype 포함하는 포리스트를 신뢰해야 합니다.
    리소스 포리스트 하이브리드 시나리오에 대한 자세한 내용은 [Deploy a resource forest topology for hybrid forest 비즈니스용 Skype](configure-a-multi-forest-environment-for-hybrid.md).

- **여러 포리스트에 비즈니스용 Skype 서버 배포** 이 구성은 합병 및 인수 시나리오의 결과로 발생할 수 있으며 보다 복잡한 기업에서 발생할 수 있습니다. 다음 주요 요구 사항이 충족되는 경우 여러 비즈니스용 Skype 배포를 사용하는 모든 조직에 대해 단일 Microsoft 365 조직의 모든 사용자를 클라우드로 통합할 수 있습니다.
  - 조직에 관련된 조직은 Microsoft 365 있어야 합니다. 조직이 두 개 이상인 시나리오에서는 통합이 지원되지 않습니다.
  - 포리스트는 한 번만 하이브리드 모드(공유 SIP 주소 비즈니스용 Skype)에 있을 수 있습니다. 다른 모든 온-프레미스 비즈니스용 Skype 포리스트는 완전히 온-프레미스로 유지되어야 합니다(서로 페더러이트된 상태일 수 있습니다). 이러한 다른 프레미스 조직은 2018년 12월을 AAD 온라인 [SIP](/powershell/module/skype/disable-csonlinesipdomain) 도메인을 사용하지 않도록 설정하는 새로운 기능과 함께 원할 경우 동기화할 수 있습니다.

    여러 포리스트에 비즈니스용 Skype 배포하는 고객은 분할 도메인(공유 SIP 주소 공간) 기능을 사용하여 각 비즈니스용 Skype 포리스트를 Microsoft 365 조직으로 완전히 마이그레이션해야 합니다. 포리스트 마이그레이션이 완료된 후 고객은 다음에 있는 프레미스 배포를 마이그레이션하기 전에 하이브리드와의 하이브리드를 비즈니스용 Skype 합니다. 또한 클라우드로 마이그레이션하기 전에, 모든 사용자와 동일한 사용자의 On-premises 디렉터리에 표현되지 않은 사용자와의 페더전 상태로 남아 있습니다. 자세한 내용은 클라우드 통합 및 Teams [비즈니스용 Skype](cloud-consolidation.md).

## <a name="federation-requirements"></a>페더전 요구 사항

<a name="BKMK_Federation"> </a>

하이브리드 비즈니스용 Skype 구성할 때에는 사내 환경과 온라인 환경이 서로 페더링될 수 있어야 합니다.  온라인 환경에는 기본적으로 열려 있는 페더임이 있습니다. 기본적으로는 사내 환경이 닫힌 페더ation이 있는 경우가 종종 있습니다.  

하이브리드 배포를 성공적으로 구성하려면 다음 요구 사항을 충족해야 합니다.

- 도메인 일치는 도메인 일치 조직과 사용자 조직에 대해 동일하게 Microsoft 365 합니다. 파트너 검색이온-프레미스 배포에서 사용하도록 설정된 경우 온라인 조직에 대해 열려 있는 페더ation을 구성해야 합니다. 파트너 검색을 사용하도록 설정하지 않은 경우 온라인 조직에 대해 닫힌 페더ation을 구성해야 합니다.
- On-premises deployment의 차단된 도메인 목록은 온라인 테넌트의 차단된 도메인 목록과 정확히 일치해야 합니다.
- On-premises deployment의 허용 도메인 목록은 온라인 테넌트의 허용 도메인 목록과 정확히 일치해야 합니다.
- 온라인 테넌트의 외부 통신에 대해 페더전을 사용하도록 설정해야 합니다.

## <a name="network-considerations"></a>네트워크 고려 사항

다음 섹션에서는 다음에 대한 고려 사항을 설명합니다.

- DNS 설정
- 방화벽 고려 사항

### <a name="dns-settings-for-hybrid-deployments"></a>하이브리드 배포에 대한 DNS 설정

<a name="BKMK_DNS"> </a>

하이브리드 배포에 대한 DNS 레코드를 만들 때 모든 비즈니스용 Skype DNS 레코드는 모두 비즈니스용 Skype 인프라를 지정해야 합니다. 필요한 DNS 레코드에 대한 자세한 내용은 DNS 요구 사항을 [비즈니스용 Skype 서버.](../../sfbserver/plan-your-deployment/network-requirements/dns.md)

또한 다음 표에 설명된 DNS 확인이 사내 배포에서 작동하는지 확인해야 합니다. (이미 On-premises에 대해 페더미스를 구성한 경우 이러한 연결은 이미 있는 것입니다.)

|DNS 레코드  <br/> |가해할 수 있는 경우  <br/> |DNS 요구 사항  <br/> |
|:-----|:-----|:-----|
|_sipfederationtls._tcp에 대한 DNS SRV 레코드입니다.\<sipdomain.com\> 액세스 에지 외부 IP로 확인되는 지원되는 모든 SIP 도메인에 대해  <br/> |에지 서버  <br/> |하이브리드 구성에서 페더전된 통신을 사용하도록 설정 에지 서버는 프레미스와 온라인 간에 분할된 SIP 도메인의 페더전된 트래픽을 라우팅할 위치를 알아야 합니다.  <br/> 사용자 이름의 도메인과 SRV 레코드 간에 엄격한 DNS 이름을 일치해야 합니다.  <br/> |
|에지 웹 회의 서비스 FQDN에 대한 DNS A 레코드(예: webcon.contoso.com 에지 외부 IP로의 확인할 수 있는 경우)  <br/> |내부 회사 네트워크 연결된 사용자 컴퓨터  <br/> |온라인 사용자가 사내 호스팅 모임에서 콘텐츠를 발표하거나 볼 수 있도록 합니다. 콘텐츠에는 PowerPoint, 화이트보드, 설문 조사 및 공유 메모가 포함됩니다.  <br/> |

조직에서 DNS를 구성하는 방법에 따라 해당 SIP 도메인의 내부 호스팅 DNS 영역으로 이러한 레코드를 추가하여 이러한 레코드에 내부 DNS 확인을 제공해야 할 수 있습니다.

### <a name="firewall-considerations-for-hybrid-deployments"></a>하이브리드 배포에 대한 방화벽 고려 사항

<a name="BKMK_Firewall"> </a>

네트워크의 컴퓨터에서 표준 인터넷 DNS 검색을 수행할 수 있어야 합니다. 이러한 컴퓨터에서 표준 인터넷 사이트에 연결할 수 있으면 네트워크가 이 요구 사항을 충족하는 것입니다.

Microsoft Online Services 데이터 센터의 위치에 따라 와일드카드 도메인 이름(예: \*.outlook.com 의 모든 트래픽)을 기반으로 연결을 수락하도록 네트워크 방화벽 장치를 구성해야 합니다. 조직의 방화벽에서 와일드카드 이름 구성을 지원하지 않는 경우 허용할 IP 주소 범위와 지정된 포트를 수동으로 결정해야 합니다.

포트 및 프로토콜 요구 사항에 대한 세부 정보를 포함하여 자세한 내용은 Microsoft 365 [URL 및 IP 주소 범위를 참조하세요](/microsoft-365/enterprise/urls-and-ip-address-ranges).
