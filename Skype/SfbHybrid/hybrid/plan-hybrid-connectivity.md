---
title: 하이브리드 연결 | 계획 비즈니스용 Skype 서버 및 Teams
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
description: 비즈니스용 Skype 하이브리드 모드를 구성하여 비즈니스용 Skype 서버 Teams 간에 하이브리드 연결을 구현할 계획입니다.
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: a73b14a3642a216ff9cbbe919b586979aabf6a81
ms.sourcegitcommit: 15ec17eff4ad4c962d00b8683513f9b269d82917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2022
ms.locfileid: "66695051"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>비즈니스용 Skype 서버 Teams 간의 하이브리드 연결 계획

> [!Important]
> 비즈니스용 Skype Online은 2021년부터 사용 중지되었지만 2019, 비즈니스용 Skype 서버 2015 및 Lync Server 2013을 비즈니스용 Skype 서버 온-프레미스 제품은 여전히 지원됩니다. 또한 Microsoft는 이러한 온-프레미스 제품과 Microsoft Teams 간의 하이브리드 환경을 지원합니다. 이렇게 하면 이러한 온-프레미스 배포를 사용하는 조직에서 사용자를 TeamsOnly로 마이그레이션할 수 있습니다.  마지막으로, 비즈니스용 Skype 서버 Cloud Connector Edition은 더 이상 지원되지 않습니다. 온-프레미스 PSTN 연결이 필요한 고객은 [직접 라우팅을](/MicrosoftTeams/direct-routing-landing-page) 사용해야 합니다.


비즈니스용 Skype 서버 또는 Lync Server 2013과 Teams 간의 하이브리드 연결을 계획하는 방법을 알아보려면 이 항목을 참조하세요. 하이브리드 연결을 설정하는 것은 온-프레미스 환경을 클라우드의 Microsoft Teams 전용 환경으로 전환하는 첫 번째 단계입니다.

비즈니스용 Skype 서버 온-프레미스 배포에서 비즈니스용 Skype 사용자는 Teams를 사용할 수도 있지만 온-프레미스 비즈니스용 Skype 서버 배포를 사용하도록 구성된 경우 이러한 사용자가 모든 Teams 기능을 사용할 수 있는 것은 아닙니다. 이러한 사용자는 온-프레미스에 "홈"이라고 하며, 이러한 사용자가 온-프레미스에 있는 동안에는 특정 Teams 기능을 사용할 수 없습니다. 예를 들면 다음과 같습니다.

- 다른 조직의 사용자와 사용자의 Teams 클라이언트를 통해 페더레이션된 통화 및 채팅을 사용할 수 없습니다.
- 비즈니스용 Skype 클라이언트를 사용하는 조직의 다른 사용자와 사용자의 Teams 클라이언트를 통한 Interop 통신
- PSTN 통화 기능(사용자에게 전화 시스템 라이선스가 할당된 경우).

전체 Teams 기능을 얻으려면 이러한 사용자를 비즈니스용 Skype 온-프레미스에서 클라우드로 이동해야 합니다. 이때 사용자는 TeamsOnly가 됩니다. 사용자를 온-프레미스에서 클라우드로 이동하는 작업은 사용자의 공존 모드를 TeamsOnly로 설정합니다. 사용자가 클라우드 및 TeamsOnly로 이동하면 들어오는 모든 채팅 및 통화가 Teams 클라이언트에 배치됩니다(Teams의 병렬 사용과는 달리).  자세한 내용은 [비즈니스용 Skype 함께 Teams를 사용하는 조직에 대한 비즈니스용 Skype 및 마이그레이션](/microsoftteams/coexistence-chat-calls-presence) 및 [상호 운용성 지침과 Teams](/microsoftteams/migration-interop-guidance-for-teams-with-skype) 공존을 참조하세요.

클라우드에서 온-프레미스와 TeamsOnly 간에 사용자를 이동하려면 비즈니스용 Skype 하이브리드 모드를 구성해야 합니다. 또한 온-프레미스 비즈니스용 Skype 배포를 해제하기 전에 모든 사용자를 온-프레미스에서 클라우드로 이동합니다.   하이브리드 연결을 설정하면 사용자를 일정에 따라 클라우드로 이동하도록 선택할 수 있습니다.  직접 라우팅을 사용하면 클라우드로 이동하는 동안과 마이그레이션이 완료된 후 온-프레미스 음성 인프라를 활용할 수 있습니다.

이 항목에서는 기존 온-프레미스 비즈니스용 Skype 서버 배포와 Teams 간의 하이브리드 연결을 구성하는 데 필요한 인프라 및 시스템 요구 사항에 대해 설명합니다.

이 항목을 읽고 하이브리드 연결을 구성할 준비가 되면 [비즈니스용 Skype 서버 Teams 간의 하이브리드 연결 구성](configure-hybrid-connectivity.md)을 참조하세요. 구성 항목에서는 온-프레미스 배포와 Teams 간의 하이브리드 연결을 설정하기 위한 단계별 지침을 제공합니다.


## <a name="implications-of-the-retirement-of-skype-for-business-online"></a>비즈니스용 Skype Online의 사용 중지의 의미
비즈니스용 Skype Online의 사용 중지 전후에 비즈니스용 Skype 서버 온-프레미스에 있는 사용자는 Teams를 사용할 수 있지만 TeamsOnly일 수는 없다는 점을 기억해야 합니다. (온-프레미스 사용자는 기본적으로 아일랜드 모드에 있으며 TeamsOnly 이외의 모드에 할당됩니다.) 사용자는 TeamsOnly 모드에 있으면 Teams, 특히 페더레이션, PSTN 지원 및 모든 인바운드 채팅 및 통화가 Teams에 있다는 보장의 모든 혜택을 경험할 수 있습니다. 

비즈니스용 Skype Online의 사용 중지는 비즈니스용 Skype 서버 또는 Lync Server 2013의 기존 지원 수명 주기에 영향을 주지 않습니다.  그러나 비즈니스용 Skype Online의 사용 중지는 사용자가 클라우드로 전환하고 기존 하이브리드 조직을 포함하여 온-프레미스 비즈니스용 Skype 서버 또는 Lync Server 2013을 사용하는 조직에서 *TeamsOnly가 되는* **방법** 의 특정 측면에 영향을 미쳤습니다. 하이브리드를 필수 구성으로 사용하여 온-프레미스에서 클라우드로 전환(예: TeamsOnly)은 변경되지 않습니다.

비즈니스용 Skype Online이 사용 중지되기 전에 하이브리드 조직은 다음 세 가지 기본 유형의 사용자로 구성됩니다. 
- 온-프레미스 사용자(Teams를 사용하거나 사용하지 않을 수 있지만 Teams 전용 모드에서는 사용할 수 없음) 
- TeamsOnly 이외의 공존 모드를 가진 온라인 사용자
- TeamsOnly 사용자.

그러나 비즈니스용 Skype Online이 사용 중지된 후 하이브리드 조직은 다음 두 가지 기본 유형의 사용자로만 구성됩니다. 
- 온-프레미스 사용자(Teams를 사용할 수도 있거나 사용하지 않을 수도 있지만 TeamsOnly 모드에서는 사용할 수 없음)
- Teams 사용자만. 

조직에서 비즈니스용 Skype 서버 또는 Lync Server 2013에서 Teams로 이동하려면 *사용 중지 전* 과 똑같은 도구 집합을 사용하여 하이브리드를 설정하고 구성해야 합니다. 사용자를 온-프레미스에서 TeamsOnly로 이동하는 경우 더 이상 스위치`Move-CsUser`를 `-MoveToTeams` 지정할 필요가 없습니다. 이전에는 이 스위치를 지정하지 않은 경우 사용자가 비즈니스용 Skype 서버 온-프레미스에서 비즈니스용 Skype Online으로 전환되었으며 해당 모드는 변경되지 않았습니다. 그러나 Skype Business Online이 사용 중지되었으므로 사용자를 온-프레미스에서 클라우드로 `Move-CsUser` 이동하면 전환이 지정되었는지 여부에 `-MoveToTeams` 관계없이 TeamsOnly 모드를 *자동으로* 할당하고 모임을 온-프레미스에서 Teams 모임으로 변환하기 시작합니다. 이는 또한 전환이 없었던 `MoveToTeams` Lync Server 2013을 사용하는 조직에서 사용자를 온-프레미스에서 TeamsOnly로 직접 이동할 수 있습니다. 

마찬가지로 새 사용자가 온-프레미스가 아닌 Microsoft 365에서 직접 만들어진 경우 해당 사용자는 테넌트 모드에 관계없이 자동으로 Teams 전용 모드를 갖게 됩니다. 온-프레미스 사용자가 하나 이상 있는 하이브리드 조직에서는 새 사용자를 클라우드 사용자로 만들려는 경우에도 온-프레미스 사용자가 새 사용자로 라우팅할 수 있도록 Microsoft 365에서 사용자를 직접 만드는 대신 온-프레미스 Active Directory(그런 다음 Microsoft 365로 동기화)에 *새 사용자를* 만들어야 합니다. 온-프레미스 디렉터리에서 만든 후에는 이러한 새 사용자를 *온-프레미스* 비즈니스용 Skype 배포에서 sip-enabled한 다음, 원하는 경우 TeamsOnly가 되도록 클라우드로 이동해야 합니다. 

비즈니스용 Skype Online의 사용 중지 후에도 공존 모드가 계속 존재합니다. 이전과 마찬가지로 비즈니스용 Skype 서버 온-프레미스에 계정이 있는 사용자는 TeamsOnly를 제외한 모든 공존 모드를 할당할 수 있습니다. 그러나 사용 중지 후에는 온라인 사용자만 TeamsOnly가 될 수 있습니다. 온라인 홈이 있는 사용자에게 TeamsOnly 이외의 모드를 더 이상 할당할 수 없습니다.


> [!Important]
> TeamsOnly가 아닌 비즈니스용 Skype Online에 사용자가 있는 기존 하이브리드 조직은 가능한 한 빨리 이러한 사용자를 Teams 전용 모드로 업그레이드하는 데 집중해야 합니다. 조직에 여전히 TeamsOnly가 아닌 비즈니스용 Skype *Online* 에 사용자가 있는 경우 Microsoft 지원 업그레이드를 예약하여 이러한 사용자를 TeamsOnly로 전환합니다. **Microsoft 지원 업그레이드는 비즈니스용 Skype 서버 온-프레미스에 있는 사용자에게 영향을 주지 않습니다.** 예약 알림은 온라인이 아닌 TeamsOnly 사용자가 Teams로 업그레이드되기 전에 비즈니스용 Skype Online에 사용자가 있는 하이브리드 고객에게 미리 전송됩니다.

## <a name="about-shared-sip-address-space-functionality"></a>공유 SIP 주소 공간 기능 정보

<a name="BKMK_Overview"> </a>

비즈니스용 Skype 서버 및 Teams의 온-프레미스 배포 간에 하이브리드 연결이 설정되면 일부 사용자가 온-프레미스에 홈으로 배치되고 일부 사용자가 온라인 상태로 전환할 수 있습니다.

이 유형의 구성은 공유 SIP 주소 공간 기능을 사용하며 때로는 "분할 도메인"이라고도 합니다. 즉, contoso.com 같은 도메인 사용자는 다음 다이어그램과 같이 온-프레미스와 Teams에서 비즈니스용 Skype 서버 사용하여 분할됩니다.

![비즈니스 하이브리드용 Skype 연결 - 도메인 분할](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

공유 SIP 주소 공간이 구성된 경우:

- Azure Active Directory Connect는 온-프레미스 디렉터리를 Microsoft 365와 동기화하는 데 사용됩니다.
- 온-프레미스에 있는 사용자는 온-프레미스 비즈니스용 Skype 서버와 상호 작용합니다.
- 온라인 홈인 사용자는 Teams와 상호 작용합니다.
- 두 환경의 사용자는 서로 통신할 수 있습니다.
- 온-프레미스 Active Directory 신뢰할 수 있습니다. 모든 사용자를 먼저 온-프레미스 Active Directory 만든 다음 Azure AD 동기화해야 합니다. 사용자가 온라인으로 홈을 설정하려는 경우에도 먼저 온-프레미스 환경에서 사용자를 만든 다음 사용자를 온라인으로 이동하여 온-프레미스 사용자가 사용자를 검색할 수 있도록 해야 합니다.

사용자를 온라인으로 이동하려면 먼저 Teams 라이선스와 비즈니스용 Skype Online(플랜 2)을 할당받아야 합니다. **비즈니스용 Skype Online 사용 중지 후에도 비즈니스용 Skype Online 라이선스를 할당해야 합니다.** 사용자가 오디오 회의 또는 전화 시스템과 같은 추가 온라인 기능을 활용하려는 경우 Microsoft 365에서 적절한 라이선스를 할당해야 합니다.

## <a name="hybrid-connectivity-infrastructure-requirements"></a>하이브리드 연결 인프라 요구 사항

<a name="BKMK_Infrastructure"> </a>

온-프레미스 환경과 Microsoft 365 통신 서비스 간의 하이브리드 연결을 구현하려면 다음 인프라 요구 사항을 충족해야 합니다.

- 지원되는 토폴로지에서 배포되는 비즈니스용 Skype 서버 또는 Lync Server의 단일 온-프레미스 배포입니다. 이 항목의 [토폴로지 요구 사항을](plan-hybrid-connectivity.md#BKMK_Topology) 참조하세요.

- Teams를 사용하는 Microsoft 365 조직.
    > [!NOTE]
    > 온-프레미스 배포에서 하이브리드 구성에 단일 테넌트만 사용할 수 있습니다.
    
- Azure Active Directory Connect를 사용하여 온-프레미스 디렉터리를 Microsoft 365와 동기화합니다. 자세한 내용은 [Azure AD Connect: 계정 및 사용 권한](/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions)을 참조하세요.

- 관리 도구를 비즈니스용 Skype 서버. 사용자를 온-프레미스에서 클라우드로 이동하는 데 필요합니다. 이러한 도구는 온-프레미스 배포 및 인터넷에 모두 액세스할 수 있는 서버에 설치해야 합니다.
- 온라인 관리 도구. Teams 관리 센터 또는 Windows PowerShell 사용하여 Teams를 관리할 수 있습니다. PowerShell을 사용하여 Teams를 관리하려면 Teams PowerShell 모듈을 다운로드하여 설치합니다. (비즈니스용 Skype Online 커넥터가 사용 중지되었습니다.)
- 공유 SIP 주소 공간을 사용하도록 설정해야 하며 Microsoft 365를 호스팅 공급자로 사용하도록 온-프레미스 배포를 구성해야 합니다. 하이브리드 연결을 구성하는 데 필요한 단계에 대한 자세한 내용은 [하이브리드 연결 구성](configure-hybrid-connectivity.md)을 참조하세요.

하이브리드 연결을 구성한 후 사용자를 Teams로 이동할 수 있습니다. 자세한 내용은 [온-프레미스에서 Teams로 사용자 이동을 참조하세요](move-users-from-on-premises-to-teams.md).

## <a name="server-version-requirements"></a>서버 버전 요구 사항

<a name="BKMK_Topology"> </a>

**Teams** 를 사용하여 하이브리드에 대한 배포를 구성하려면 지원되는 다음 토폴로지 중 하나가 있어야 합니다.

- 비즈니스용 Skype 서버 2019 배포 - 모든 서버에서 비즈니스용 Skype 서버 2019 실행
- 비즈니스용 Skype 서버 2015 배포 - 모든 서버에서 비즈니스용 Skype 서버 2015 실행
- 모든 서버가 Lync Server 2013을 실행하는 Lync Server 2013 배포  그러나 하이브리드 음성 연결이 필요한 경우 아래에 설명된 대로 혼합 버전 토폴로지를 사용해야 합니다.
- 아래 나열된 대로 최대 2개의 다른 서버 버전이 있는 배포:
  - 비즈니스용 Skype 서버 2015 및 비즈니스용 Skype 2019
  - Lync Server 2013 및 비즈니스용 Skype 서버 2019
  - Lync Server 2013 및 비즈니스용 Skype 서버 2015
- 2022년 7월 31일부터 온-프레미스 배포와 클라우드 간에 사용자를 이동하려면 다음 최소 버전의 비즈니스용 Skype 서버 또는 Lync Server를 사용해야 합니다.
</br>

|온-프레미스 제품|필수 최소 버전|필요한 최소 빌드|
|---|---|---|
|비즈니스용 Skype Server 2019| CU6 |7.0.2046.385|
|비즈니스용 Skype Server 2015| CU12|6.0.9319.619|
|Lync Server 2013| CU10 핫픽스 7|5.0.8308.1182|

</br>

> [!NOTE] 
> Lync Server 2010은 Teams에서 지원되지 않습니다.


## <a name="multi-forest-support"></a>다중 포리스트 지원

<a name="BKMK_MultiForest"> </a>

Microsoft는 다음과 같은 유형의 다중 포리스트 하이브리드 시나리오를 지원합니다.

- **리소스 포리스트 토폴로지.** 이러한 종류의 토폴로지에서는 비즈니스용 Skype 서버(리소스 포리스트)를 호스트하는 포리스트가 하나 이상 있으며, 계정 ID를 호스트하는 하나 이상의 추가 포리스트가 있습니다. 이 포리스트는 리소스 포리스트의 비즈니스용 Skype 서버 액세스합니다. 일반적으로 사용자는 다음 요구 사항이 충족되면 다른 포리스트에서 비즈니스용 Skype 기능에 액세스할 수 있습니다.
  - 사용자는 비즈니스용 Skype를 호스팅하는 포리스트에 올바르게 동기화됩니다. 하이브리드 구성에서는 사용자가 비활성화된 사용자 개체로 동기화되어야 합니다.
  - 비즈니스용 Skype를 호스팅하는 포리스트는 사용자를 포함하는 포리스트를 신뢰해야 합니다.
    리소스 포리스트 하이브리드 시나리오에 대한 자세한 내용은 [하이브리드 비즈니스용 Skype 대한 리소스 포리스트 토폴로지 배포를](configure-a-multi-forest-environment-for-hybrid.md) 참조하세요.

- **여러 포리스트에 여러 비즈니스용 Skype 서버를 배포** 이 구성은 합병 및 인수 시나리오의 결과로 발생할 수 있으며 더 복잡한 기업에서도 발생할 수 있습니다. 다음과 같은 주요 요구 사항을 충족하는 경우 여러 비즈니스용 Skype 배포를 사용하는 모든 조직에 대해 온-프레미스에서 클라우드로의 모든 사용자를 단일 Microsoft 365 조직에서 통합할 수 있습니다.
  - 최대 하나의 Microsoft 365 조직이 관련되어 있어야 합니다. 둘 이상의 조직을 사용하는 시나리오의 통합은 지원되지 않습니다.
  - 언제든지 하나의 온-프레미스 비즈니스용 Skype 포리스트만 하이브리드 모드(공유 SIP 주소 공간)에 있을 수 있습니다. 다른 모든 온-프레미스 비즈니스용 Skype 포리스트는 온-프레미스에 완전히 남아 있어야 합니다(아마도 서로 페더레이션됨). 이러한 다른 온-프레미스 조직은 2018년 12월 현재 사용할 수 있는 [온라인 SIP 도메인을 사용하지 않도록 설정하는 새로운 기능을](/powershell/module/skype/disable-csonlinesipdomain) 원하는 경우 AAD와 동기화할 수 있습니다.

    여러 포리스트에 비즈니스용 Skype 배포하는 고객은 분할 도메인(공유 SIP 주소 공간) 기능을 사용하여 각 비즈니스용 Skype 포리스트를 Microsoft 365 조직으로 개별적으로 완전히 마이그레이션해야 합니다. 포리스트 마이그레이션이 완료되면 고객은 다음 온-프레미스 비즈니스용 Skype 배포를 마이그레이션하기 전에 온-프레미스 배포에서 하이브리드를 사용하지 않도록 설정해야 합니다. 또한 클라우드로 마이그레이션하기 전에 온-프레미스 사용자는 동일한 사용자의 온-프레미스 디렉터리에 표시되지 않는 사용자와 페더레이션된 상태로 유지됩니다. 자세한 내용은 [Teams 및 비즈니스용 Skype 대한 클라우드 통합](cloud-consolidation.md)을 참조하세요.

## <a name="federation-requirements"></a>페더레이션 요구 사항

<a name="BKMK_Federation"> </a>

비즈니스용 Skype 하이브리드 모드를 구성할 때 온-프레미스 및 온라인 환경이 서로 페더레이션될 수 있는지 확인해야 합니다.  온라인 환경에는 기본적으로 열린 페더레이션이 있습니다. 온-프레미스 환경에는 기본적으로 페더레이션이 닫혀 있는 경우가 많습니다.  

하이브리드 배포를 성공적으로 구성하려면 다음 요구 사항을 충족해야 합니다.

- 도메인 일치는 온-프레미스 배포 및 Microsoft 365 조직에 대해 동일하게 구성되어야 합니다. 온-프레미스 배포에서 파트너 검색을 사용하도록 설정한 경우 온라인 조직에 대해 열린 페더레이션을 구성해야 합니다. 파트너 검색을 사용하도록 설정하지 않은 경우 온라인 조직에 대해 닫힌 페더레이션을 구성해야 합니다.
- 온-프레미스 배포의 차단된 도메인 목록은 온라인 테넌트에 대한 차단된 도메인 목록과 정확히 일치해야 합니다.
- 온-프레미스 배포의 허용된 도메인 목록은 온라인 테넌트에 대해 허용된 도메인 목록과 정확히 일치해야 합니다.
- 온라인 테넌트에 대한 외부 통신에 대해 페더레이션을 사용하도록 설정해야 합니다.

## <a name="network-considerations"></a>네트워크 고려 사항

다음 섹션에서는 다음에 대한 고려 사항을 설명합니다.

- DNS 설정
- 방화벽 고려 사항

### <a name="dns-settings-for-hybrid-deployments"></a>하이브리드 배포에 대한 DNS 설정

<a name="BKMK_DNS"> </a>

하이브리드 배포를 위한 DNS 레코드를 만들 때 모든 비즈니스용 Skype 외부 DNS 레코드는 온-프레미스 인프라를 가리켜야 합니다. 필요한 DNS 레코드에 대한 자세한 내용은 [비즈니스용 Skype 서버 대한 DNS 요구 사항을](../../sfbserver/plan-your-deployment/network-requirements/dns.md) 참조하세요.

또한 다음 표에 설명된 DNS 확인이 온-프레미스 배포에서 작동하는지 확인해야 합니다. (온-프레미스에 대한 페더레이션을 이미 구성했다면 이미 구성했을 가능성이 큽니다.)

|DNS 레코드  <br/> |해결 가능  <br/> |DNS 요구 사항  <br/> |
|:-----|:-----|:-----|
|_sipfederationtls._tcp에 대한 DNS SRV 레코드입니다.\<sipdomain.com\> Access Edge 외부 IP로 확인되는 지원되는 모든 SIP 도메인에 대해  <br/> |에지 서버  <br/> |하이브리드 구성에서 연합 통신을 활성화하세요. 에지 서버는 온-프레미스와 온라인 간에 분할된 SIP 도메인에 대해 페더레이션된 트래픽을 라우팅할 위치를 알고 있어야 합니다.  <br/> 사용자 이름과 SRV 레코드의 도메인 간에 엄격한 DNS 이름 일치를 사용해야 합니다.  <br/> |
|Edge 웹 회의 서비스 FQDN에 대한 DNS A 레코드(예: 웹 회의 Edge 외부 IP로 webcon.contoso.com 확인)  <br/> |내부 기업 네트워크 연결 사용자 컴퓨터  <br/> |온라인 사용자가 온-프레미스 호스팅 모임에서 콘텐츠를 발표하거나 볼 수 있도록 합니다. 콘텐츠에는 PowerPoint 파일, 화이트보드, 설문조사 및 공유 메모가 포함됩니다.  <br/> |

조직에서 DNS가 구성된 방식에 따라 해당 SIP 도메인의 내부 호스팅 DNS 영역에 이러한 레코드를 추가하여 이러한 레코드에 내부 DNS 확인을 제공해야 할 수 있습니다.

### <a name="firewall-considerations-for-hybrid-deployments"></a>하이브리드 배포에 대한 방화벽 고려 사항

<a name="BKMK_Firewall"> </a>

네트워크의 컴퓨터는 표준 인터넷 DNS 조회를 수행할 수 있어야 합니다. 이러한 컴퓨터에서 표준 인터넷 사이트에 연결할 수 있으면 네트워크가 이 요구 사항을 충족하는 것입니다.

Microsoft Online Services 데이터 센터의 위치에 따라 와일드카드 도메인 이름(예: .outlook.com 모든 트래픽 \*)에 따라 연결을 허용하도록 네트워크 방화벽 디바이스도 구성해야 합니다. 조직의 방화벽이 와일드카드 이름 구성을 지원하지 않는 경우 허용할 IP 주소 범위와 지정된 포트를 수동으로 결정해야 합니다.

포트 및 프로토콜 요구 사항에 대한 세부 정보를 포함하여 자세한 내용은 [Microsoft 365 URL 및 IP 주소 범위를 참조하세요](/microsoft-365/enterprise/urls-and-ip-address-ranges).
