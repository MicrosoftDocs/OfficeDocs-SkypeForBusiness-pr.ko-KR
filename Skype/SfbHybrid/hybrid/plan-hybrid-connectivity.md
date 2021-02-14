---
title: 하이브리드 연결 | 비즈니스용 Skype 서버 2019 및 Microsoft 365 또는 Office 365 통합
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 비즈니스용 Skype 하이브리드 모드를 구성하여 비즈니스용 Skype 서버와 Teams 또는 비즈니스용 Skype Online 간에 하이브리드 연결을 구현합니다.
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 856172d5fba3df96b2456f0ceca1c661120e84e4
ms.sourcegitcommit: 43dc627e9fef31a2508f54acf741000551ff68b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48878582"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-microsoft-365-or-office-365"></a>비즈니스용 Skype 서버와 Microsoft 365 또는 Office 365 간의 하이브리드 연결 계획

이 항목을 읽고 비즈니스용 Skype 서버와 Teams 또는 비즈니스용 Skype Online 간의 하이브리드 연결을 계획하는 방법을 배워야 합니다. 하이브리드 연결을 설정하는 것은 온-프레미스 환경을 클라우드로 이동하는 첫 번째 단계입니다.

Teams를 함께 사용하는 온-프레미스 비즈니스용 Skype 사용자가 있는 경우 해당 사용자는 Teams 클라이언트에서 비즈니스용 Skype 사용자와 상호 작용하거나 연합 조직의 사용자와 의사 소통을 할 수 없습니다. Teams에서 이 기능을 가능하게 하려면 이러한 사용자를 비즈니스용 Skype 온-프레미스에서 클라우드로 이동해야 하고, 이를 위해서는 비즈니스용 Skype 하이브리드 모드를 구성해야 합니다. 또한 최상의 환경을 위해 이러한 사용자는 모든 사용자의 Teams 클라이언트에 연결되는 모든 수신 전화 및 채팅을 보장하는 Teams 전용 모드에 있습니다.

온-프레미스 비즈니스용 Skype 배포를 해제하기 전에 하이브리드 연결을 설정하고 모든 사용자를 클라우드로 이동해야 합니다.  하이브리드 연결을 설정하면 사용자를 일정에 따라 클라우드로 이동하도록 선택할 수 있습니다. 직접 라우팅을 사용하면 클라우드로 이동하는 동안과 마이그레이션이 완료된 후 온-프레미스 음성 인프라를 활용할 수 있습니다.

이 항목에서는 기존 비즈니스용 Skype 서버 배포와 Teams 또는 비즈니스용 Skype Online 간에 하이브리드 연결을 구성하는 데 필요한 인프라 및 시스템 요구 사항에 대해 설명합니다.

이 항목을 읽고 하이브리드 연결을 구성할 준비가 된 후 비즈니스용 [Skype 서버와 Microsoft 365 또는 Office 365](configure-hybrid-connectivity.md)간에 하이브리드 연결 구성을 참조하세요. 구성 항목에서는 프레미스 배포와 Teams 또는 비즈니스용 Skype Online 간의 하이브리드 연결을 설정하기 위한 단계별 지침을 제공합니다.

> [!Important]
> 비즈니스용 Skype Online은 2021년 7월 31에 서비스가 더 이상 액세스할 수 없습니다.  또한 비즈니스용 Skype 서버 또는 클라우드 커넥터 버전과 비즈니스용 Skype Online을 통해 더 이상 지원되지 않는 모든 비즈니스용 Skype 환경 간의 PSTN 연결도 지원되지 않습니다.  직접 라우팅을 사용하여 프레미스 전화 통신 네트워크를 Teams에 연결하는 [방법을 학습합니다.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

## <a name="about-shared-sip-address-space-functionality"></a>공유 SIP 주소 공간 기능

<a name="BKMK_Overview"> </a>

 비즈니스용 Skype 서버와 Teams 또는 비즈니스용 Skype Online의 On-프레미스 배포 간에 하이브리드 연결을 설정하면 일부 사용자가 온라인에 있는 일부 사용자와 온라인에 있는 사용자도 있습니다.

이러한 유형의 구성은 공유 SIP 주소 공간 기능을 사용하며, 다음 다이어그램과 같이 비즈니스용 Skype 서버와 Teams 또는 비즈니스용 Skype Online을 사용하여 contoso.com와 같은 도메인의 사용자를 "분할 도메인"으로 지칭하기도 합니다.

![비즈니스용 Skype 하이브리드 연결 - 분할 도메인](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

공유 SIP 주소 공간이 구성된 경우:

- Azure Active Directory Connect는 Microsoft 365 또는 Office 365와 해당 디렉터리를 동기화하는 데 사용됩니다.
- 홈에 있는 사용자는 비즈니스용 Skype 서버와 상호 작용합니다.
- 온라인에 있는 사용자는 비즈니스용 Skype Online 또는 Teams 서비스와 상호 작용할 수 있습니다.
- 두 환경의 사용자가 서로 통신할 수 있습니다.
- On-premises Active Directory is authoritative. 모든 사용자를 먼저 On-프레미스 Active Directory에서 만든 다음 Azure AD와 동기화해야 합니다. 사용자가 온라인에 있도록 하려는 경우에도 먼저 해당 사용자를온-프레미스 환경에서 만든 다음 사용자를 온라인으로 이동하여 사용자가 온라인에서 검색되도록 해야 합니다.

사용자를 온라인으로 이동하려면 사용자에게 비즈니스용 Skype Online(계획 2) 라이선스가 할당되어야 합니다. 사용자가 Teams를 사용할 경우 사용자에게 Teams 라이선스도 할당되어야 합니다(비즈니스용 Skype 라이선스는 사용 가능한 상태로 유지해야 합니다). 사용자가 오디오 회의 또는 전화 시스템과 같은 추가 온라인 기능을 활용하려면 Microsoft 365 또는 Office 365에서 적절한 라이선스를 할당해야 합니다.

## <a name="hybrid-connectivity-infrastructure-requirements"></a>하이브리드 연결 인프라 요구 사항

<a name="BKMK_Infrastructure"> </a>

On-premises 환경과 Microsoft 365 또는 Office 365 통신 서비스 간에 하이브리드 연결을 구현하려면 다음 인프라 요구 사항을 충족해야 합니다.

- 지원되는 토폴로지에서 배포되는 비즈니스용 Skype 서버 또는 Lync Server의 단일 온-프레미스 배포 이 [항목의 토폴로지](plan-hybrid-connectivity.md#BKMK_Topology) 요구 사항을 참조하세요.

- 비즈니스용 Skype Online이 사용하도록 설정된 Microsoft 365 또는 Office 365 조직
    > [!NOTE]
    > 하이브리드 구성에 대해 단일 테넌트만 사용할 수 있습니다.프레미스 배포에서 하이브리드 구성을 사용할 수 있습니다.
    
- Azure Active Directory Connect를 사용하여 Microsoft 365 또는 Office 365와의 동기화를 제공합니다. 자세한 내용은 [Azure AD Connect: 계정 및 사용 권한을 참조하세요.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions)

- 비즈니스용 Skype 서버 관리 도구. 이러한 요구는 사용자를 프레미스에서 클라우드로 이동하는 데 필요합니다. 이러한 도구는 서버에 설치해야 합니다. 이 도구는 모든 서버에 설치해야 합니다.
- 온라인 관리 도구. Teams 관리 센터 또는 비즈니스용 Skype Windows PowerShell 관리할 수 있습니다. PowerShell을 사용하여 Teams 또는 비즈니스용 Skype Online을 관리하려면 비즈니스용 Skype Online 커넥터를 다운로드하여 설치합니다.
- 공유 SIP 주소 공간을 사용하도록 설정해야 합니다. 또한 Microsoft 365 또는 Office 365를 호스팅 공급자로 사용하도록 프레미스 배포를 구성해야 합니다. 하이브리드 연결을 구성하는 데 필요한 단계에 대한 자세한 내용은 하이브리드 연결 [구성을 참조하십시오.](configure-hybrid-connectivity.md)

하이브리드 연결을 구성한 후 사용자를 Teams 또는 비즈니스용 Skype Online으로 이동할 수 있습니다. 자세한 내용은 사용자를온-프레미스에서 [Teams로](move-users-from-on-premises-to-teams.md) 이동하고 사용자를 프레미스에서 비즈니스용 [Skype Online으로 이동을 참조하세요.](move-users-from-on-premises-to-skype-for-business-online.md)

## <a name="server-version-requirements"></a>서버 버전 요구 사항

<a name="BKMK_Topology"> </a>

Teams 또는 비즈니스용 **Skype Online을** 통해 하이브리드 배포를 구성하려면 다음 지원 토폴로지 중 하나를 설정해야 합니다.

- 비즈니스용 Skype 서버 2019 배포 - 모든 서버에서 비즈니스용 Skype 서버 2019 실행
- 비즈니스용 Skype 서버 2015 배포 - 모든 서버에서 비즈니스용 Skype 서버 2015 실행
- Lync Server 2013을 실행하는 모든 서버가 있는 Lync Server 2013 배포  그러나 하이브리드 음성 연결이 필요한 경우 아래 설명된 혼합 버전 토폴로지가 필요합니다.
- 아래 나열된 최대 2개 서버 버전이 있는 배포:
  - 비즈니스용 Skype 서버 2015 및 비즈니스용 Skype 서버 2019
  - Lync Server 2013 및 비즈니스용 Skype 서버 2019
  - Lync Server 2013 및 비즈니스용 Skype 서버 2015

모든 토폴로지에서 하이브리드 음성이 필요한 경우 페더임 에지로 지정된 에지 서버와 SIP 페더전과 연결된 풀이 모두 비즈니스용 Skype 2015 이상을 실행하고 있어야 합니다. 사용자가 있는 경우 Lync 2013 풀에 남아 있을 수 있습니다. 자세한 내용은 비즈니스용 Skype 서버에서 PSTN 연결을 통해 전화 시스템 [계획(PSTN 연결)을 참조하세요.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)

**Lync Server 2010을** 포함 하는 다음 토폴로지 인스턴트 메시징 및 모임에 대 한 비즈니스용 Skype Online에서 지원 됩니다. **Lync Server 2010이** 포함된 토폴로지는 하이브리드 음성이나 Teams에서 지원되지 않습니다.

- 혼합된 Lync Server 2010 및 비즈니스용 Skype 서버 2015 배포
- 혼합 Lync Server 2010 및 Lync Server 2013 배포
- 최신 누적 업데이트가 있는 Lync Server 2010을 실행하는 모든 서버가 있는 Lync Server 2010 배포

페더ation 에지 서버 및 페더ation 에지 서버의 다음 홉 서버는 최신 누적 업데이트와 함께 Lync Server 2010을 실행하고 있어야 합니다. 비즈니스용 Skype 서버 2015 또는 Lync Server 2013 관리 도구는 하나 이상의 서버 또는 관리 Workstation에 설치해야 합니다.

## <a name="multi-forest-support"></a>다중 포리스트 지원

<a name="BKMK_MultiForest"> </a>

Microsoft는 다음과 같은 유형의 다중 포리스트 하이브리드 시나리오를 지원합니다.

- **리소스 포리스트 토폴로지.** 이러한 유형의 토폴로지에는 비즈니스용 Skype 서버(리소스 포리스트)를 호스팅하는 포리스트가 하나 있으며, 리소스 포리스트의 비즈니스용 Skype 서버에 액세스하는 계정 ID를 호스트하는 하나 이상의 추가 포리스트가 있습니다. 일반적으로 사용자는 다음 요구 사항이 충족될 경우 다른 포리스트의 비즈니스용 Skype 기능에 액세스할 수 있습니다.
  - 사용자가 비즈니스용 Skype를 호스팅하는 포리스트에 제대로 동기화됩니다. 하이브리드 구성에서 이는 사용자를 사용하지 않도록 설정한 사용자 개체로 동기화해야 하다는 의미입니다.
  - 비즈니스용 Skype를 호스팅하는 포리스트는 사용자를 포함하는 포리스트를 신뢰해야 합니다.
    리소스 포리스트 하이브리드 시나리오에 대한 자세한 내용은 하이브리드 비즈니스용 Skype에 대한 리소스 포리스트 토폴로지 [배포를 참조하세요.](configure-a-multi-forest-environment-for-hybrid.md)

- **여러 포리스트에 여러 비즈니스용 Skype 서버를 배포** 이 구성은 합병 및 인수 시나리오의 결과로 발생할 수 있으며 더 복잡한 기업에서 발생할 수 있습니다. 다음 주요 요구 사항이 충족될 경우 여러 비즈니스용 Skype 배포를 사용하는 모든 조직에 대해 단일 Microsoft 365 또는 Office 365 조직에서 모든 사용자를 단일 Microsoft 프레미스에서 클라우드로 통합할 수 있습니다.
  - 관련된 Microsoft 365 또는 Office 365 조직이 하나 이상 있어야 합니다. 조직이 두 개 이상인 시나리오에서는 통합이 지원되지 않습니다.
  - 어떤 경우든 하나의 비즈니스용 Skype 포리스트만 하이브리드 모드(공유 SIP 주소 공간)에 있을 수 있습니다. 다른 모든 온-프레미스 비즈니스용 Skype 포리스트는 완전히 온-프레미스로 유지되어야 합니다(서로 페더화되어 있어야 합니다). 이러한 다른 온라인 프레미스 조직은 2018년 12월을 현재 사용할 수 있는 온라인 [SIP](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain) 도메인을 사용하지 않도록 설정하는 새로운 기능과 함께 원하는 경우 AAD에 동기화할 수 있습니다.

    여러 포리스트에 비즈니스용 Skype를 배포하는 고객은 분할 도메인(공유 SIP 주소 공간) 기능을 사용하여 각 비즈니스용 Skype 포리스트를 Microsoft 365 또는 Office 365 조직으로 개별적으로 완전히 마이그레이션한 다음 온-프레미스 배포와 하이브리드를 사용하지 않도록 설정한 후 다음 온-프레미스 비즈니스용 Skype 배포를 마이그레이션해야 합니다. 또한 클라우드로 마이그레이션하기 전에, 모든 사용자와 같은 사용자의온-프레미스 디렉터리에 표현되지 않은 모든 사용자와의 페더전된 상태로 남아 있습니다. 자세한 내용은 Teams 및 비즈니스용 Skype에 대한 [클라우드 통합을 참조하세요.](cloud-consolidation.md)

## <a name="federation-requirements"></a>페더전 요구 사항

<a name="BKMK_Federation"> </a>

비즈니스용 Skype 하이브리드 모드를 구성할 때에는 프레미스 및 온라인 환경이 서로 페더링할 수 있도록 해야 합니다.  온라인 환경에는 기본적으로 열려 있는 페더임이 있습니다. 기본적으로는 기본적으로 닫힌 페더인이 있는 경우가 프레미스 환경입니다.  

하이브리드 배포를 성공적으로 구성하려면 다음 요구 사항을 충족해야 합니다.

- 도메인 일치는 Microsoft 365 또는 Office 365 조직과 동일하게 구성해야 합니다. 파트너 검색이온-프레미스 배포에서 사용하도록 설정된 경우 온라인 조직에 대해 열려 있는 페더ation을 구성해야 합니다. 파트너 검색을 사용하도록 설정하지 않은 경우 온라인 조직에 대해 닫힌 페더ation을 구성해야 합니다.
- On-premises 배포의 차단된 도메인 목록은 온라인 테넌트의 차단된 도메인 목록과 정확히 일치해야 합니다.
- On-premises 배포의 허용 도메인 목록은 온라인 테넌트의 허용 도메인 목록과 정확히 일치해야 합니다.
- 온라인 테넌트의 외부 통신에 대해 페더전을 사용하도록 설정해야 합니다.

## <a name="network-considerations"></a>네트워크 고려 사항

다음 섹션에서는 다음에 대한 고려 사항을 설명합니다.

- DNS 설정
- 방화벽 고려 사항

### <a name="dns-settings-for-hybrid-deployments"></a>하이브리드 배포에 대한 DNS 설정

<a name="BKMK_DNS"> </a>

하이브리드 배포에 대한 DNS 레코드를 만들 때 모든 비즈니스용 Skype 외부 DNS 레코드는 On-premises 인프라를 지정해야 합니다. 필요한 DNS 레코드에 대한 자세한 내용은 비즈니스용 Skype 서버의 DNS 요구 [사항을 참조하세요.](../../sfbserver/plan-your-deployment/network-requirements/dns.md)

또한 다음 표에 설명된 DNS 확인이 On-premises 배포에서 작동하는지도 확인해야 합니다. (이미 On-premises에 대한 페더미스를 구성한 경우 이러한 페더미스가 이미 있는 것일 수 있습니다.)

|DNS 레코드  <br/> |해할 수 있는 경우  <br/> |DNS 요구 사항  <br/> |
|:-----|:-----|:-----|
|_sipfederationtls._tcp에 대한 DNS SRV 레코드입니다.\<sipdomain.com\> 액세스 에지 외부 IP로 확인되는 지원되는 모든 SIP 도메인의 경우  <br/> |에지 서버  <br/> |하이브리드 구성에서 페더타 통신을 사용하도록 설정 에지 서버는 SIP 도메인에 대한 페더전된 트래픽을 라우팅할 위치를 알아야 합니다.  <br/> 사용자 이름의 도메인과 SRV 레코드 간에 엄격한 DNS 이름 일치를 사용해야 합니다.  <br/> |
|에지 웹 회의 서비스 FQDN에 대한 DNS A 레코드(예webcon.contoso.com 웹 회의 에지 외부 IP로의 확인할 수 있습니다.  <br/> |내부 회사 네트워크 연결 사용자 컴퓨터  <br/> |온라인 사용자가온-프레미스 호스팅 모임에서 콘텐츠를 보거나 발표할 수 있도록 합니다. 콘텐츠에는 PowerPoint 파일, 화이트보드, 설문 조사 및 공유 메모가 포함됩니다.  <br/> |

조직에서 DNS가 구성된 방식에 따라 이러한 레코드를 해당 SIP 도메인의 내부 호스팅 DNS 영역으로 추가하여 이러한 레코드에 내부 DNS 확인을 제공해야 할 수 있습니다.

### <a name="firewall-considerations-for-hybrid-deployments"></a>하이브리드 배포에 대한 방화벽 고려 사항

<a name="BKMK_Firewall"> </a>

네트워크의 컴퓨터는 표준 인터넷 DNS 검색을 수행할 수 있어야 합니다. 이러한 컴퓨터에서 표준 인터넷 사이트에 연결할 수 있으면 네트워크가 이 요구 사항을 충족하는 것입니다.

데이터 센터의 Microsoft Online Services 와일드카드 도메인 이름(예: .outlook.com의 모든 트래픽)을 기반으로 연결을 수락하도록 네트워크 방화벽 장치를 구성해야 \* 합니다. 조직의 방화벽에서 와일드카드 이름 구성을 지원하지 않는 경우 허용할 IP 주소 범위와 지정된 포트를 수동으로 결정해야 합니다.

포트 및 프로토콜 요구 사항에 대한 세부 정보를 비롯한 자세한 내용은 [Microsoft 365 및 Office 365 URL](https://go.microsoft.com/fwlink/p/?LinkId=252942)및 IP 주소 범위를 참조하세요.
