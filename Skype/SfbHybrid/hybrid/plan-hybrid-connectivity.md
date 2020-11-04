---
title: 하이브리드 연결 계획 | 비즈니스용 Skype 서버 2019 및 Microsoft 365 또는 Office 365 통합
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
description: 비즈니스용 skype 하이브리드 모드를 구성 하 여 비즈니스용 Skype 서버와 팀 간 또는 비즈니스용 Skype Online 간에 하이브리드 연결을 구현 하는 방법을 계획 합니다.
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 856172d5fba3df96b2456f0ceca1c661120e84e4
ms.sourcegitcommit: 43dc627e9fef31a2508f54acf741000551ff68b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48878582"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-microsoft-365-or-office-365"></a>비즈니스용 Skype 서버와 Microsoft 365 또는 Office 365의 하이브리드 연결 계획

비즈니스용 Skype 서버 및 팀과 비즈니스용 Skype Online 간의 하이브리드 연결을 계획 하는 방법을 알아보려면이 항목을 읽어 보십시오. 하이브리드 연결을 설정하는 것은 온-프레미스 환경을 클라우드로 이동하는 첫 번째 단계입니다.

Teams를 함께 사용하는 온-프레미스 비즈니스용 Skype 사용자가 있는 경우 해당 사용자는 Teams 클라이언트에서 비즈니스용 Skype 사용자와 상호 작용하거나 연합 조직의 사용자와 의사 소통을 할 수 없습니다. Teams에서 이 기능을 가능하게 하려면 이러한 사용자를 비즈니스용 Skype 온-프레미스에서 클라우드로 이동해야 하고, 이를 위해서는 비즈니스용 Skype 하이브리드 모드를 구성해야 합니다. 또한 이러한 사용자는 팀 전용 모드를 사용 하 여 사용자의 팀 클라이언트에 있는 모든 수신 통화와 채팅을 수행할 수 있도록 합니다.

온-프레미스 비즈니스용 Skype 배포를 해제하기 전에 하이브리드 연결을 설정하고 모든 사용자를 클라우드로 이동해야 합니다.  하이브리드 연결을 설정하면 사용자를 일정에 따라 클라우드로 이동하도록 선택할 수 있습니다. 직접 라우팅을 사용하면 클라우드로 이동하는 동안과 마이그레이션이 완료된 후 온-프레미스 음성 인프라를 활용할 수 있습니다.

이 항목에서는 기존 온-프레미스 비즈니스용 Skype 서버 배포와 팀 또는 비즈니스용 Skype Online 간에 하이브리드 연결을 구성 하는 데 필요한 인프라 및 시스템 요구 사항에 대해 설명 합니다.

이 항목을 읽은 후 하이브리드 연결을 구성할 준비가 되 면 [비즈니스용 Skype 서버 및 Microsoft 365 또는 Office 365 간의 하이브리드 연결 구성을](configure-hybrid-connectivity.md)참조 하세요. 구성 항목에서는 온-프레미스 배포와 팀 또는 비즈니스용 Skype Online 간에 하이브리드 연결을 설정 하기 위한 단계별 지침을 제공 합니다.

> [!Important]
> 비즈니스용 Skype Online은 서비스에 더 이상 액세스할 수 없게 되 고, 2021 년 7 월 31 일에 만료 됩니다.  또한 비즈니스용 Skype 서버 또는 클라우드 Connector Edition과 비즈니스용 Skype Online을 통해 온-프레미스 환경 간의 PSTN 연결이 더 이상 지원 되지 않습니다.  [직접 라우팅을](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)사용 하 여 팀에 온-프레미스 전화 통신 네트워크를 연결 하는 방법을 알아봅니다.

## <a name="about-shared-sip-address-space-functionality"></a>공유 SIP 주소 공간 기능 정보

<a name="BKMK_Overview"> </a>

 하이브리드 연결이 온-프레미스 비즈니스용 Skype 서버 및 팀 또는 비즈니스용 Skype Online 사이에 설정 된 경우 일부 사용자가 온-프레미스에 있고 일부 사용자는 온라인으로 로그인 할 수 있습니다.

이 구성 유형은 공유 SIP 주소 공간 기능을 사용 하며, contoso.com와 같은 도메인 사용자는 다음 다이어그램에 나와 있는 것 처럼 비즈니스용 Skype 서버에서 온-프레미스 및 팀 또는 비즈니스용 Skype Online을 사용할 수 있습니다.

![비즈니스용 Skype 하이브리드 연결-분할 도메인](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

공유 SIP 주소 공간이 구성 된 경우:

- Azure Active Directory Connect는 온-프레미스 디렉터리를 Microsoft 365 또는 Office 365과 동기화 하는 데 사용 됩니다.
- 온-프레미스 사용자가 온-프레미스 비즈니스용 Skype 서버와 상호 작용 합니다.
- 홈 온라인 상태인 사용자는 비즈니스용 Skype Online 또는 팀 서비스와 상호 작용할 수 있습니다.
- 두 환경의 사용자가 서로 통신할 수 있습니다.
- 온-프레미스 Active Directory를 신뢰할 수 있습니다. 모든 사용자는 먼저 온-프레미스 Active Directory에 만든 다음 Azure AD와 동기화 해야 합니다. 사용자를 온라인으로 설정 하려는 경우에도 먼저 온-프레미스 환경에서 사용자를 만든 다음 사용자를 온라인으로 이동 하 여 사용자가 온-프레미스 사용자가 검색할 수 있도록 해야 합니다.

사용자를 온라인으로 이동 하려면 사용자에 게 비즈니스용 Skype Online (요금제 2) 라이선스를 할당 해야 합니다. 사용자가 팀을 사용 하는 경우에는 사용자에 게 팀 라이선스도 할당 되어 있어야 하며 비즈니스용 Skype 라이선스가 사용 하도록 설정 되어 있어야 합니다. 사용자가 오디오 회의 또는 전화 시스템과 같은 추가 온라인 기능을 사용 하려는 경우 Microsoft 365 또는 Office 365에서 해당 하는 라이선스를 할당 해야 합니다.

## <a name="hybrid-connectivity-infrastructure-requirements"></a>하이브리드 연결 인프라 요구 사항

<a name="BKMK_Infrastructure"> </a>

온-프레미스 환경과 Microsoft 365 또는 Office 365 통신 서비스 간에 하이브리드 연결을 구현 하려면 다음 인프라 요구 사항을 충족 해야 합니다.

- 지원 되는 토폴로지에서 배포 되는 비즈니스용 Skype 서버 또는 Lync Server의 단일 온-프레미스 배포 이 항목의 [토폴로지 요구 사항](plan-hybrid-connectivity.md#BKMK_Topology) 참조

- 비즈니스용 Skype Online을 사용 하는 Microsoft 365 또는 Office 365 조직
    > [!NOTE]
    > 온-프레미스 배포의 경우 단일 테 넌 트만 하이브리드 구성에 사용할 수 있습니다.
    
- Azure Active Directory Connect 온-프레미스 디렉터리를 Microsoft 365 또는 Office 365와 동기화 합니다. 자세한 내용은 [AZURE AD Connect: 계정 및 사용 권한을](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions)참조 하세요.

- 비즈니스용 Skype 서버 관리 도구입니다. 사용자를 온-프레미스에서 클라우드로 이동 하는 데 필요 합니다. 이러한 도구는 온-프레미스 배포와 인터넷 모두에 대 한 액세스 권한이 있는 서버에 설치 되어 있어야 합니다.
- 온라인 관리 도구 팀 관리 센터 또는 Windows PowerShell을 사용 하 여 팀 및 비즈니스용 Skype Online을 관리할 수 있습니다. PowerShell을 사용 하 여 팀 또는 비즈니스용 Skype Online을 관리 하려면 비즈니스용 Skype Online 커넥터를 다운로드 하 여 설치 합니다.
- 공유 SIP 주소 공간을 사용 하도록 설정 해야 하며, 호스팅 공급자로 Microsoft 365 또는 Office 365을 사용 하도록 온-프레미스 배포를 구성 해야 합니다. 하이브리드 연결을 구성 하는 데 필요한 단계에 대 한 자세한 내용은 [configure 하이브리드 connectivity](configure-hybrid-connectivity.md)을 참조 하십시오.

하이브리드 연결을 구성한 후에는 사용자를 팀 이나 비즈니스용 Skype Online으로 이동할 수 있습니다. 자세한 내용은 [사용자를 온-프레미스에서 팀으로 이동](move-users-from-on-premises-to-teams.md) 및 사용자를 온-프레미스에서 [비즈니스용 Skype Online으로 이동을](move-users-from-on-premises-to-skype-for-business-online.md)참조 하세요.

## <a name="server-version-requirements"></a>서버 버전 요구 사항

<a name="BKMK_Topology"> </a>

**팀 또는 비즈니스용 Skype Online** 을 사용 하 여 하이브리드 배포를 구성 하려면 다음의 지원 되는 토폴로지 중 하나가 있어야 합니다.

- 비즈니스용 Skype 서버 2019 배포 - 모든 서버에서 비즈니스용 Skype 서버 2019 실행
- 비즈니스용 Skype 서버 2015 배포 - 모든 서버에서 비즈니스용 Skype 서버 2015 실행
- Lync server 2013 배포 시 모든 서버 2013을 실행 합니다.  그러나 하이브리드 음성 연결이 필요한 경우 아래에 나와 있는 혼합 버전 토폴로지를 사용 해야 합니다.
- 아래에 나열 된 것과 같은 최대 2 개의 서로 다른 서버 버전을 사용 하는 배포:
  - 비즈니스용 skype 서버 2015 및 비즈니스용 Skype 서버 2019
  - Lync Server 2013 및 비즈니스용 Skype 서버 2019
  - Lync Server 2013 및 비즈니스용 Skype 서버 2015

*하이브리드 음성이 어떤 토폴로지에서 든 지 원하는 경우* 에는 페더레이션 모서리로 지정 되는 edge 서버와 SIP 페더레이션과 연결 된 풀 모두에서 비즈니스용 Skype 2015 이상을 실행 해야 합니다. 사용자는 Lync 2013 풀 (있는 경우)에 남아 있을 수 있습니다. 자세한 내용은 [비즈니스용 Skype 서버의 전화 시스템에 PSTN 연결을 계획](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)합니다 .를 참조 하세요.

Lync Server 2010이 포함 된 다음과 같은 토폴로지가 인스턴트 메시징과 모임을 위해 **비즈니스용 Skype Online에서 지원 됩니다** . **Lync Server 2010이 포함 된 토폴로지는 하이브리드 음성 및 팀에서 지원 되지 않습니다**.

- 혼합 Lync Server 2010 및 비즈니스용 Skype 서버 2015 배포
- 혼합 Lync Server 2010 및 Lync Server 2013 배포
- Lync server 2010 배포-최신 누적 업데이트를 사용 하는 모든 서버 2010을 실행 합니다.

페더레이션에 지 서버의 페더레이션에 지 서버 및 다음 홉 서버는 최신 누적 업데이트를 사용 하 여 Lync Server 2010을 실행 중 이어야 합니다. 비즈니스용 Skype 서버 2015 또는 Lync Server 2013 관리 도구를 하나 이상의 서버 또는 관리 워크스테이션에 설치 해야 합니다.

## <a name="multi-forest-support"></a>다중 포리스트 지원

<a name="BKMK_MultiForest"> </a>

Microsoft는 다음과 같은 유형의 다중 포리스트 하이브리드 시나리오를 지원 합니다.

- **리소스 포리스트 토폴로지** 이러한 유형의 토폴로지에서는 비즈니스용 Skype 서버 (리소스 포리스트)를 호스트 하는 포리스트 하나가 있고, 리소스 포리스트의 비즈니스용 Skype 서버에 액세스 하는 계정 id를 호스트 하는 추가 포리스트가 하나 이상 있습니다. 일반적으로 사용자는 다음 요구 사항이 충족 되는 경우 다른 포리스트에서 비즈니스용 Skype 기능에 액세스할 수 있습니다.
  - 사용자가 비즈니스용 Skype를 호스트 하는 포리스트에서 제대로 동기화 됩니다. 하이브리드 구성에서이는 사용자를 사용 하지 않도록 설정 된 사용자 개체로 동기화 해야 함을 의미 합니다.
  - 비즈니스용 Skype를 호스트 하는 포리스트에서 사용자를 포함 하는 포리스트를 신뢰 해야 합니다.
    리소스 포리스트 하이브리드 시나리오에 대 한 자세한 내용은 [하이브리드 a resource forest topology for Hybrid 비즈니스용 Skype](configure-a-multi-forest-environment-for-hybrid.md)를 참조 하세요.

- **여러 포리스트에 여러 비즈니스용 Skype 서버를 배포** 이러한 구성은 합병 및 인식 시나리오의 결과로, 보다 복잡 한 엔터프라이즈에서 발생할 수 있습니다. 다음과 같은 주요 요구 사항을 충족 하는 경우 비즈니스용 Skype 배포가 여러 개인 조직에 대해 온-프레미스에서 365 365 클라우드로 모든 사용자를 통합 하는 방법을 사용할 수 있습니다.
  - Microsoft 365 또는 Office 365 조 직은 최대 1 개까지 포함 되어야 합니다. 두 개 이상의 조직이 있는 시나리오의 통합은 지원 되지 않습니다.
  - 주어진 시간에 한 번에 온-프레미스 비즈니스용 Skype 포리스트가 하이브리드 모드 (공유 SIP 주소 공간) 일 수 있습니다. 다른 모든 온-프레미스 비즈니스용 Skype 포리스트는 완전히 온-프레미스에 유지 되 고 서로 연결 되어 있어야 합니다. [새로운 기능을 사용 하 여 온라인 SIP 도메인](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain) 을 12 월 2018 일 때 사용할 수 없도록 설정 하는 경우 이러한 다른 온-프레미스 조직은 AAD와 동기화 할 수 있습니다.

    여러 포리스트에서 비즈니스용 Skype를 배포 하는 고객은 분할 도메인 (공유 SIP 주소 공간) 기능을 사용 하 여 각 비즈니스용 Skype 포리스트를 Microsoft 365 또는 Office 365 조 직으로 개별적으로 마이그레이션한 다음 온-프레미스 배포와 하이브리드를 사용 하지 않도록 설정 해야 하며, 다음 온-프레미스 비즈니스용 Skype 배포를 마이그레이션합니다. 또한 클라우드로 마이그레이션 되기 전에 온-프레미스 사용자는 동일한 사용자의 온-프레미스 디렉터리에 표시 되지 않는 모든 사용자와의 페더레이션 상태로 유지 됩니다. 자세한 내용은 [팀 및 비즈니스용 Skype에 대 한 클라우드 통합](cloud-consolidation.md)을 참조 하세요.

## <a name="federation-requirements"></a>페더레이션 요구 사항

<a name="BKMK_Federation"> </a>

비즈니스용 Skype 하이브리드 모드를 구성할 때 온-프레미스 및 온라인 환경이 서로 페더레이션 할 수 있는지 확인 해야 합니다.  온라인 환경에는 기본적으로 오픈 페더레이션이 있습니다. 일반적으로 온-프레미스 환경에는 기본적으로 닫힌 페더레이션이 있습니다.  

하이브리드 배포를 성공적으로 구성 하려면 다음 요구 사항을 충족 해야 합니다.

- 도메인 일치는 온-프레미스 배포와 Microsoft 365 또는 Office 365 조 직에 대해 동일 하 게 구성 해야 합니다. 온-프레미스 배포에서 파트너 검색을 사용 하도록 설정한 경우에는 온라인 조직에 대해 open 페더레이션을 구성 해야 합니다. 파트너 검색을 사용 하도록 설정 하지 않은 경우에는 온라인 조직에 대해 닫힌 페더레이션을 구성 해야 합니다.
- 온-프레미스 배포의 차단 된 도메인 목록은 온라인 테 넌 트에 대 한 차단 된 도메인 목록과 정확히 일치 해야 합니다.
- 온-프레미스 배포의 허용 도메인 목록은 온라인 테 넌 트에 대해 허용 되는 도메인 목록과 정확히 일치 해야 합니다.
- 온라인 테 넌 트에 대 한 외부 통신에 대해 페더레이션을 사용 하도록 설정 해야 합니다.

## <a name="network-considerations"></a>네트워크 고려 사항

다음 섹션에서는 다음에 대 한 고려 사항을 설명 합니다.

- DNS 설정
- 방화벽 고려 사항

### <a name="dns-settings-for-hybrid-deployments"></a>하이브리드 배포에 대 한 DNS 설정

<a name="BKMK_DNS"> </a>

하이브리드 배포에 대 한 DNS 레코드를 만들 때 비즈니스용 Skype 외부 DNS 레코드는 모두 온-프레미스 인프라를 가리켜야 합니다. 필수 DNS 레코드에 대 한 자세한 내용은 [비즈니스용 Skype 서버에 대 한 DNS 요구 사항을](../../sfbserver/plan-your-deployment/network-requirements/dns.md)참조 하세요.

또한 온-프레미스 배포에서 다음 표에 설명 된 DNS 확인이 작동 하는지 확인 해야 합니다. 온-프레미스에 대 한 페더레이션이 이미 구성 되어 있는 경우에는 대개이를 이미 사용 하 고 있을 가능성이 높습니다.

|DNS 레코드  <br/> |확인할 사람  <br/> |DNS 요구 사항  <br/> |
|:-----|:-----|:-----|
|_Tcp에 대 한 DNS SRV 레코드를 _sipfederationtls 합니다.\<sipdomain.com\> 액세스를 대상으로 하는 모든 지원 SIP 도메인에 대해에 지 외부 IP  <br/> |에 지 서버  <br/> |하이브리드 구성에서 페더레이션 통신을 사용 하도록 설정 합니다. 에 지 서버는 온-프레미스와 온라인 간에 분할 된 SIP 도메인에 대 한 페더레이션 트래픽을 라우팅할 위치를 알아야 합니다.  <br/> 사용자 이름 및 SRV 레코드에 있는 도메인 간에 엄격한 DNS 이름 일치를 사용 해야 합니다.  <br/> |
|Edge 웹 회의 서비스 FQDN에 대 한 DNS A 레코드 (예: 웹 회의에 지 외부 IP에 대 한 webcon.contoso.com 확인)  <br/> |내부 회사 네트워크에 연결 된 사용자 컴퓨터  <br/> |온라인 사용자가 온-프레미스 호스트 모임에서 콘텐츠를 표시 하거나 볼 수 있도록 설정 합니다. 콘텐츠에는 PowerPoint 파일, 화이트 보드, 설문 및 공유 메모가 포함 됩니다.  <br/> |

조직에서 DNS가 구성 된 방식에 따라 이러한 레코드에 내부 DNS 확인을 제공 하기 위해 해당 SIP 도메인의 내부 호스트 DNS 영역에 이러한 레코드를 추가 해야 할 수 있습니다.

### <a name="firewall-considerations-for-hybrid-deployments"></a>하이브리드 배포에 대 한 방화벽 고려 사항

<a name="BKMK_Firewall"> </a>

네트워크의 컴퓨터는 표준 인터넷 DNS 조회를 수행할 수 있어야 합니다. 이러한 컴퓨터에서 표준 인터넷 사이트에 연결할 수 있으면 네트워크가 이 요구 사항을 충족하는 것입니다.

Microsoft Online Services 데이터 센터의 위치에 따라 와일드 카드 도메인 이름 (예: outlook.com의 모든 트래픽)을 기반으로 연결을 허용 하도록 네트워크 방화벽 장치를 구성 해야 합니다. \* 조직의 방화벽이 와일드 카드 이름 구성을 지원 하지 않는 경우 허용할 IP 주소 범위 및 지정 된 포트를 수동으로 결정 해야 합니다.

포트 및 프로토콜 요구 사항에 대 한 자세한 내용은 [Microsoft 365 및 Office 365 url 및 IP 주소 범위](https://go.microsoft.com/fwlink/p/?LinkId=252942)를 참조 하세요.
