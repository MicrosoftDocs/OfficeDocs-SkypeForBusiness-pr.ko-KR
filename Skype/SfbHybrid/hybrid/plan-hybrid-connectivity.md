---
title: 하이브리드 연결 계획 | 비즈니스용 Skype 서버 2019 Office 365 통합
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 비즈니스용 Skype 서버와 비즈니스용 Skype Online 또는 팀 간의 하이브리드 연결을 구현 하기 위한 계획 고려 사항입니다.
ms.openlocfilehash: 2cca98740aeb991923683ce80b3b33a6ac49fbc6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185436"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>비즈니스용 Skype 서버와 Office 365 하이브리드 연결 계획

## <a name="overview"></a>개요

비즈니스용 Skype 서버와 팀 또는 비즈니스용 Skype Online 간의 하이브리드 연결을 계획 하는 방법을 알아보려면이 항목을 참조 하세요. 하이브리드 연결 설정은 온-프레미스 환경을 클라우드로 이동 하는 첫 번째 단계입니다.

팀 (나란히 나란히)을 사용 하는 온-프레미스 Skype 사용자가 있는 경우 해당 사용자에 게 팀 클라이언트의 비즈니스용 Skype 사용자와 상호 작용 하거나 페더레이션 조직의 사용자와 통신 하는 기능이 없습니다. 팀 클라이언트. 팀에서이 기능을 얻으려면 비즈니스용 Skype 온-프레미스에서 클라우드로 이동 해야 하며,이는 비즈니스용 Skype 하이브리드 모드를 구성 해야 합니다. 또한 최상의 환경을 위해 이러한 사용자는 팀 전용 모드에 있으므로 사용자의 팀 클라이언트에 있는 모든 사용자의 수신 통화와 채팅을 보장 합니다.

하이브리드 연결을 설정 하 고 모든 사용자를 클라우드로 이동 하는 작업은 온-프레미스 비즈니스용 Skype 배포를 해제 하기 전에 필요 합니다.  하이브리드 연결을 설정 하는 경우 사용자의 일정과 비즈니스 요구 사항에 따라 사용자를 클라우드로 이동 하도록 선택할 수 있습니다. 직접 라우팅 기능을 사용 하면 클라우드로 이동 하 고 마이그레이션이 완료 된 후 온-프레미스 음성 인프라를 활용할 수 있습니다.

이 항목에서는 기존 온-프레미스 비즈니스용 Skype 서버 배포와 팀 또는 비즈니스용 Skype Online 간에 하이브리드 연결을 구성 하는 데 필요한 인프라 및 시스템 요구 사항에 대해 설명 합니다.

이 항목을 읽은 후 하이브리드 연결을 구성할 준비가 되 면 비즈니스용 [Skype 서버 및 Office 365 하이브리드 연결 구성을](configure-hybrid-connectivity.md)참조 하세요. 구성 항목에는 온-프레미스 배포와 팀 간 하이브리드 연결 설정에 대 한 단계별 지침 (비즈니스용 Skype Online)이 제공 됩니다.

## <a name="about-shared-sip-address-space-functionality"></a>공유 SIP 주소 공간 기능 정보

<a name="BKMK_Overview"> </a>

 하이브리드 연결이 비즈니스용 Skype 서버와 팀 또는 비즈니스용 Skype Online에 설정 되어 있는 경우, 일부 사용자에 게 온-프레미스와 일부 사용자가 온라인 상태가 되도록 할 수 있습니다.

이 유형의 구성은 공유 SIP 주소 공간 기능을 기반으로 하며, "도메인 분할"이 라고도 하는 경우에 따라 contoso.com와 같은 도메인 사용자는 온-프레미스 및 비즈니스용 Skype Server for 비즈니스용 Skype를 사용 하는 것을 의미 합니다. 다음 다이어그램과 같이 온라인 상태입니다.

![SfB 하이브리드 연결-도메인 분할](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

공유 SIP 주소 공간을 구성 하는 경우:

- Azure Active Directory Connect는 온-프레미스 디렉터리를 Office 365와 동기화 하는 데 사용 됩니다.
- 온-프레미스 비즈니스용 사용자가 비즈니스용 Skype 서버와 상호 작용 합니다.
- 홈 online 인 사용자는 비즈니스용 Skype Online 또는 팀 서비스와 상호 작용할 수 있습니다.
- 두 환경의 사용자는 서로 통신할 수 있습니다.
- 온-프레미스 Active Directory에 권한이 있습니다. 모든 사용자는 먼저 온-프레미스 Active Directory에 만든 다음 Azure AD와 동기화 해야 합니다. 사용자를 온라인으로 설정 하려는 경우에도 온-프레미스 환경에서 사용자를 만든 다음 사용자를 온라인으로 이동 하 여 사용자가 온-프레미스 사용자가 검색할 수 있도록 해야 합니다.

사용자가 온라인으로 이동할 수 있으려면 먼저 사용자에 게 비즈니스용 Skype Online (요금제 2) 라이선스를 할당 해야 합니다. 사용자가 팀을 사용 하는 경우에는 사용자에 게 팀 라이선스도 할당 되어 있어야 하며 비즈니스용 Skype 라이선스가 설정 된 상태를 유지 해야 합니다. 사용자가 오디오 회의 또는 전화 시스템 등의 추가 온라인 기능을 활용 하려는 경우 Office 365의 적절 한 라이선스를 할당 해야 합니다.

## <a name="infrastructure-requirements"></a>인프라 요구 사항

<a name="BKMK_Infrastructure"> </a>

온-프레미스 환경과 Office 365 통신 서비스 간에 하이브리드 연결을 구현 하려면 다음 인프라 요구 사항을 충족 해야 합니다.

- 지원 되는 토폴로지에서 배포 된 비즈니스용 Skype Server 또는 Lync Server의 단일 온-프레미스 배포입니다. 이 항목의 [토폴로지 요구 사항을](plan-hybrid-connectivity.md#BKMK_Topology) 참조 하세요.
- 비즈니스용 Skype Online이 활성화 된 Microsoft Office 365 테 넌 트
    > [!NOTE]
    > 온-프레미스 배포의 경우 단일 테 넌 트만 하이브리드 구성에 사용할 수 있습니다.
- Azure Active Directory Connect 온-프레미스 디렉터리를 Office 365와 동기화 합니다. 자세한 내용은 [AZURE AD Connect: 계정 및 사용 권한을](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions)참조 하세요.
- 비즈니스용 Skype 서버 관리 도구.  이는 사용자를 온-프레미스에서 클라우드로 이동 하는 데 필요 합니다. 이러한 도구는 온-프레미스 배포와 인터넷 모두에 대 한 액세스 권한이 있는 서버에 설치 되어 있어야 합니다.
- 온라인 관리 도구  팀 관리 센터 또는 Windows PowerShell을 사용 하 여 팀과 비즈니스용 Skype Online을 관리할 수 있습니다. PowerShell을 사용 하 여 팀 또는 비즈니스용 Skype Online을 관리 하려면 비즈니스용 Skype Online Connector를 다운로드 하 여 설치 합니다.
- 공유 SIP 주소 공간을 사용 하도록 설정 하 고 Office 365를 호스팅 공급자로 사용 하도록 온-프레미스 배포를 구성 해야 합니다. 하이브리드 연결을 구성 하는 데 필요한 단계에 대 한 자세한 내용은 [하이브리드 연결 구성을](configure-hybrid-connectivity.md)참조 하세요.

하이브리드 연결을 구성한 후에는 사용자를 팀 또는 비즈니스용 Skype Online으로 이동할 수 있습니다. 자세한 내용은 온 [-프레미스에서 팀으로 사용자 이동을](move-users-from-on-premises-to-teams.md) 시작 하 고 [온-프레미스에서 비즈니스용 Skype Online으로 이동](move-users-from-on-premises-to-skype-for-business-online.md)을 참조 하세요.

## <a name="server-version-requirements"></a>서버 버전 요구 사항

<a name="BKMK_Topology"> </a>

팀과 하이브리드 **또는 비즈니스용 Skype Online**으로 배포를 구성 하려면 다음 지원 토폴로지 중 하나가 있어야 합니다.

- 비즈니스용 skype server 2019를 실행 하는 모든 서버와의 비즈니스용 Skype 서버 2019 배포
- 비즈니스용 skype server 2015를 실행 하는 모든 서버와의 비즈니스용 Skype 서버 2015 배포
- Lync server 2013를 실행 하는 모든 서버에 2013 배포  그러나 하이브리드 음성 연결이 필요한 경우 아래에 명시 된 혼합 버전 토폴로지를 사용 해야 합니다.
- 아래에 나열 된 것과 같이 최대 2 개의 다른 서버 버전이 있는 배포:
  - 비즈니스용 skype 서버 2015 및 비즈니스용 Skype 서버 2019
  - Lync Server 2013 및 비즈니스용 Skype Server 2019
  - Lync Server 2013 및 비즈니스용 Skype Server 2015

*모든 토폴로지에서 하이브리드 음성이 필요한 경우*에는 페더레이션 가장자리로 지정 되는 edge 서버와 SIP 페더레이션과 연결 된 풀 모두에서 비즈니스용 Skype 2015 이상을 실행 해야 합니다. 사용자는 Lync 2013 풀 (있는 경우)에 남아 있을 수 있습니다. 자세한 내용은 [비즈니스용 Skype 서버에서 PSTN 연결을 사용 하 여 전화 시스템 계획](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)을 참조 하세요.

Lync Server 2010를 포함 하는 다음 토폴로지가 인스턴트 메시징 및 모임을 위해 **비즈니스용 Skype Online에서 지원 됩니다** .  Lync Server 2010을 포함 하는 토폴로지가 **하이브리드 음성 또는 팀에서 지원 되지 않습니다**.

- 혼합 Lync Server 2010 및 비즈니스용 Skype Server 2015 배포
- 혼합 Lync Server 2010 및 Lync Server 2013 배포
- Lync server 2010는 최신 누적 업데이트로 Lync Server 2010를 실행 하는 모든 서버에 배포 됩니다.

페더레이션 edge 서버의 페더레이션 Edge 서버와 다음 홉 서버는 최신 누적 업데이트로 Lync Server 2010을 실행 해야 합니다. 비즈니스용 Skype 서버 2015 또는 Lync Server 2013 관리 도구는 하나 이상의 서버 또는 관리 워크스테이션에 설치 되어 있어야 합니다.

## <a name="multi-forest-support"></a>다중 포리스트 지원

<a name="BKMK_MultiForest"> </a>

Microsoft는 다음과 같은 유형의 다중 포리스트 하이브리드 시나리오를 지원 합니다.

- **리소스 포리스트 토폴로지.** 이러한 종류의 토폴로지에서는 비즈니스용 Skype 서버 (리소스 포리스트)를 호스팅하는 포리스트 하나가 있으며, 리소스 포리스트의 비즈니스용 Skype 서버에 액세스 하는 계정 id를 호스트 하는 하나 이상의 추가 포리스트가 있습니다. 일반적으로 사용자는 다음 요구 사항이 충족 되는 경우 다른 포리스트의 비즈니스용 Skype 기능에 액세스할 수 있습니다.
  - 사용자는 비즈니스용 Skype를 호스트 하는 포리스트로 적절 하 게 동기화 됩니다. 하이브리드 구성에서이는 사용자가 사용 하지 않는 사용자 개체로 동기화 되어야 함을 의미 합니다.
  - 비즈니스용 Skype를 호스트 하는 포리스트는 사용자를 포함 하는 포리스트를 신뢰 해야 합니다.
    리소스 포리스트 하이브리드 시나리오에 대 한 자세한 내용은 [하이브리드 비즈니스용의 리소스 포리스트 토폴로지 배포](configure-a-multi-forest-environment-for-hybrid.md)를 참조 하세요.
- **여러 포리스트에 비즈니스용 Skype 서버를 여러 개 배포 했습니다.** 이러한 구성은 합병 및 인식 시나리오의 결과로, 그리고 복잡 한 기업에서는 발생할 수 있습니다.  단일 Office 365 테 넌 트에 대 한 모든 사용자의 통합을 여러 비즈니스용 Skype 배포를 사용 하는 모든 조직에 대해 다음 주요 요구 사항이 충족 되는 경우이를 구현할 수 있습니다.

  - Office 365 테 넌 트가 하나 이상 포함 되어 있어야 합니다. 두 개 이상의 Office 365 테 넌 트가 있는 시나리오의 통합은 지원 되지 않습니다.
  - 언제 든 지 하이브리드 모드 (공유 SIP 주소 공간) 인 경우에는 온-프레미스 비즈니스용 Skype forest 하나만 사용할 수 있습니다. 다른 모든 온-프레미스 비즈니스용 Skype 포리스트는 구내에 완전히 남아 있어야 합니다 (동시에 서로 페더레이션). 이러한 다른 온-프레미스 조직은 새 기능을 사용 하 여 12 월 2018 [온라인 SIP 도메인을 사용 하지 않도록 설정 하](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain) 는 경우 AAD와 동기화 할 수 있습니다.

    여러 포리스트에 비즈니스용 Skype를 배포 하는 고객은 분할 도메인 (공유 SIP 주소 공간) 기능을 사용 하 여 각 비즈니스용 Skype 포리스트를 Office 365 테 넌 트로 개별적 마이그레이션한 다음 하이브리드을 사용 하지 않도록 설정 해야 합니다. 온-프레미스 배포로 이동 하기 전에 비즈니스용 Skype 배포에 대해 다음에 시작 합니다. 또한 클라우드로 마이그레이션하기 전에 온-프레미스 사용자는 동일한 사용자의 온-프레미스 디렉터리에 표시 되지 않는 사용자와의 페더레이션 상태로 유지 됩니다. 자세한 내용은 [팀 및 비즈니스용 Skype에 대 한 클라우드 통합](cloud-consolidation.md)을 참조 하세요.

## <a name="federation-requirements"></a>페더레이션 요구 사항

<a name="BKMK_Federation"> </a>

하이브리드을 구성할 때 온-프레미스 및 온라인 환경이 서로 페더레이션 할 수 있는지 확인 해야 합니다.  온라인 환경에 기본적으로 열려 있는 페더레이션이 있습니다. 온-프레미스 환경에는 대개 기본적으로 닫혀 있는 페더레이션이 있습니다.  

하이브리드 배포를 성공적으로 구성 하려면 다음 요구 사항을 충족 해야 합니다.

- 도메인 일치는 온-프레미스 배포 및 Office 365 테 넌 트에 대해 동일 하 게 구성 되어야 합니다. 온-프레미스 배포에서 파트너 검색을 사용 하도록 설정한 경우 온라인 테 넌 트에 대해 open federation를 구성 해야 합니다. 파트너 검색을 사용할 수 없는 경우에는 사용자의 온라인 테 넌 트에 대해 닫힌 페더레이션이 구성 되어야 합니다.
- 온-프레미스 배포의 차단 된 도메인 목록이 온라인 테 넌 트에 대 한 차단 된 도메인 목록과 정확히 일치 해야 합니다.
- 온-프레미스 배포의 허용 도메인 목록이 온라인 테 넌 트에 대해 허용 된 도메인 목록과 정확히 일치 해야 합니다.
- 온라인 테 넌 트에 대 한 외부 통신에 대해 페더레이션을 사용 하도록 설정 해야 합니다.

## <a name="network-considerations"></a>네트워크 고려 사항

다음 섹션에서는 다음에 대 한 고려 사항에 대해 설명 합니다.

- DNS 설정
- 방화벽 고려 사항

### <a name="dns-settings"></a>DNS 설정

<a name="BKMK_DNS"> </a>

하이브리드 배포에 대 한 DNS 레코드를 만들 때 모든 비즈니스용 Skype 외부 DNS 레코드는 온-프레미스 인프라를 가리켜야 합니다. 필수 DNS 레코드에 대 한 자세한 내용은 [비즈니스용 Skype 서버에 대 한 DNS 요구 사항](../../sfbserver/plan-your-deployment/network-requirements/dns.md)을 참조 하세요.

또한 다음 표에 설명 된 DNS 해결 방법이 온-프레미스 배포에서 작동 하는지 확인 해야 합니다. (온-프레미스에 대해 페더레이션이 이미 구성 되어 있는 경우에는 이미이를 포함 하 고 있을 수 있습니다.)

|DNS 레코드  <br/> |확인할 사람  <br/> |DNS 요구 사항  <br/> |
|:-----|:-----|:-----|
|_Tcp에 대 한 DNS SRV 레코드 _sipfederationtls. \<EDGE\> 외부 IP에 액세스 하기 위해 지원 되는 모든 SIP 도메인이 sipdomain.com.  <br/> |Edge 서버 (s)  <br/> |하이브리드 구성에서 페더레이션된 통신을 사용 하도록 설정 합니다. Edge 서버는 온-프레미스와 온라인 간에 분할 된 SIP 도메인의 페더레이션 트래픽을 라우팅하는 위치를 알고 있어야 합니다.  <br/> 사용자 이름 및 SRV 레코드의 도메인 간에 엄격한 DNS 이름 일치를 사용 해야 합니다.  <br/> |
|DNS A Edge 웹 회의 서비스의 FQDN (예: 웹 회의에 대 한 webcon.contoso.com 해결) 외부 IP에 대 한 i d A A  <br/> |내부 회사 네트워크에 연결 된 사용자 컴퓨터  <br/> |온라인 사용자가 온-프레미스 호스트 모임에서 콘텐츠를 프레젠테이션 하거나 볼 수 있도록 설정 합니다. 콘텐츠에는 PowerPoint 파일, 화이트 보드, 설문 조사 및 공유 메모가 포함 됩니다.  <br/> |

조직에서 DNS를 구성 하는 방법에 따라 해당 SIP 도메인에 대 한 내부 호스팅 DNS 영역에 이러한 레코드를 추가 하 여 해당 레코드에 대 한 내부 DNS 확인을 제공 해야 할 수 있습니다.

### <a name="firewall-considerations"></a>방화벽 고려 사항

<a name="BKMK_Firewall"> </a>

네트워크의 컴퓨터는 표준 인터넷 DNS 조회를 수행할 수 있어야 합니다. 이러한 컴퓨터가 표준 인터넷 사이트에 도달할 수 있는 경우 네트워크는이 요구 사항을 충족 합니다.

Microsoft Online Services 데이터 센터의 위치에 따라 와일드 카드 도메인 이름 (예: outlook.com의 \*모든 트래픽)을 기준으로 연결을 허용 하도록 네트워크 방화벽 장치를 구성 해야 합니다. 조직의 방화벽이 와일드 카드 이름 구성을 지원 하지 않는 경우 허용 하려는 IP 주소 범위 및 지정 된 포트를 수동으로 확인 해야 합니다.

포트 및 프로토콜 요구 사항에 대 한 세부 정보를 비롯 한 자세한 내용은 [Office 365 url 및 IP 주소 범위](https://go.microsoft.com/fwlink/p/?LinkId=252942)를 참조 하세요.
