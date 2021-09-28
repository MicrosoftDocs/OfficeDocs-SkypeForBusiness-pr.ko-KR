---
title: 직접 라우팅 계획
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: 시스템 Microsoft 전화 라우팅을 통해 지원되는 SBC(고객 제공 세션 테두리 컨트롤러)를 시스템 시스템에 연결하는 방법을 Microsoft 전화 알아보는 것이 가장 좋은 Microsoft 전화 있습니다.
ms.openlocfilehash: a747879a0e95ab524e1a45cf12a366f0bd7e4fe4
ms.sourcegitcommit: 84706d0b3b93c1bc72baac830fefd3f0a87c5ad1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/27/2021
ms.locfileid: "59942383"
---
# <a name="plan-direct-routing"></a>직접 라우팅 계획

> [!Tip]
> 다음 세션에서 직접 라우팅의 이점, 계획을 세우는 방법 및 배포하는 방법에 대해 [자세히 알아보는 세션을 Microsoft Teams](https://aka.ms/teams-direct-routing)

Microsoft 전화 시스템 직접 라우팅을 사용하면 지원되는 SBC(고객 제공 세션 테두리 컨트롤러)를 시스템 시스템에 Microsoft 전화 있습니다.  예를 들어 이 기능을 사용하면 다음 다이어그램과 같이 클라이언트에서 PSTN(공용 전환 전화 네트워크) Microsoft Teams 구성할 수 있습니다. 

![프레미스 PSTN 연결 구성을 보여주는 다이어그램입니다.](media/PlanDirectRouting1-PSTNwithTeams.png "클라이언트와의 프레미스 PSTN 연결 Microsoft Teams 구성")

  > [!NOTE]
  > 비즈니스용 Skype 온라인을 사용하면 고객이 제공한 SBC를 페어링할 수 있지만 SBC와 Microsoft Cloud 간에 비즈니스용 Skype 서버 배포 또는 클라우드 커넥터라는 비즈니스용 Skype 특별 버전이 필요합니다. 이 시나리오를 하이브리드 음성으로 알려져 있습니다. 반면 직접 라우팅을 사용하면 지원되는 SBC와 Microsoft Cloud 간에 직접 연결을 허용합니다.

> [!Important]
> Cloud Connector Edition은 온라인과 함께 2021년 7월 31일 비즈니스용 Skype 사용 중지됩니다. 조직이 로 업그레이드된 Teams 직접 라우팅을 사용하여 프레미스 전화 통신 네트워크를 Teams [방법을 알아보습니다.](direct-routing-landing-page.md) 

직접 라우팅을 사용하면 SBC를 거의 모든 전화 통신 트렁크에 연결하거나 타사 PSTN 장비와 상호 연결할 수 있습니다. 직접 라우팅을 사용하면 다음을 할 수 있습니다. 

- 시스템과 거의 모든 PSTN 트렁크를 Microsoft 전화 있습니다. 
- 타사 PBX(개인 분기 교환), 아날로그 디바이스 및 시스템과 같은 고객 소유의 전화 통신 장비 간에 상호 Microsoft 전화 구성합니다.

또한 Microsoft는 호출 계획과 같은 모든 클라우드 음성 솔루션을 제공합니다. 그러나 다음이 있는 경우 하이브리드 음성 솔루션이 조직에 가장 적합한 것일 수 있습니다. 

- Microsoft 통화 요금제는 사용자 국가에서 사용할 수 없습니다. 
- 조직에서 타사 아날로그 디바이스, 콜 센터에 연결해야 합니다. 
- 조직에 PSTN 통신사와 기존 계약이 있습니다.

또한 직접 라우팅은 Microsoft 통화 계획에 대한 추가 라이선스가 있는 사용자를 지원합니다. 자세한 내용은 전화 시스템 및 통화 [계획을 참조하세요.](calling-plan-landing-page.md) 

직접 라우팅을 사용하여 사용자가 예약된 회의에 참가할 때 Microsoft Audio Conferencing 서비스에 의해 전화 접속 번호가 제공됩니다. 이 경우 적절한 라이선스가 필요합니다.  전화를 걸 때 Microsoft Audio Conferencing 서비스는 적절한 라이선스가 필요한 온라인 통화 기능을 사용하여 전화를 걸 수 있습니다. (사용자가 Microsoft 오디오 회의 라이선스가 없는 경우 직접 라우팅을 통해 호출 경로가 설정됩니다.) 자세한 내용은 를 통해 [온라인 모임을 Teams.](https://products.office.com/microsoft-teams/online-meeting-solutions) 
 
직접 라우팅 배포를 계획하는 것이 성공적인 구현의 핵심입니다. 이 문서에서는 인프라 및 라이선스 요구 사항을 설명하고 SBC 연결에 대한 정보를 제공합니다. 

- [인프라 요구 사항](#infrastructure-requirements)
- [라이선스 및 기타 요구 사항](#licensing-and-other-requirements)
- [SBC 도메인 이름](#sbc-domain-names)
- [SBC에 대한 공용 신뢰할 수 있는 인증서](#public-trusted-certificate-for-the-sbc)
- [SIP 신호: FQDNS](#sip-signaling-fqdns)
- [SIP 신호: 포트](#sip-signaling-ports)
- [미디어 트래픽: 포트 범위](#media-traffic-port-ranges)
- [지원되는 세션 테두리 컨트롤러(SBC)](#supported-session-border-controllers-sbcs)

직접 라우팅 구성에 대한 자세한 내용은 직접 라우팅 [구성 을 참조하세요.](direct-routing-configure.md)

## <a name="infrastructure-requirements"></a>인프라 요구 사항
Direct 라우팅을 배포하기 위해 지원되는 SBC, 도메인 및 기타 네트워크 연결 요구 사항에 대한 인프라 요구 사항은 다음 표에 나열되어 있습니다.  

|인프라 요구 사항|다음이 필요합니다.|
|:--- |:--- |
|SBC(세션 테두리 컨트롤러)|지원되는 SBC. 자세한 내용은 지원되는 [SBC 를 참조하세요.](#supported-session-border-controllers-sbcs)|
|SBC에 연결된 전화 통신 트렁크|SBC에 연결된 하나 이상의 전화 통신 트렁크. 한 엔드에서 SBC는 직접 라우팅을 통해 Microsoft 전화 시스템에 연결합니다. 또한 SBC는 타사 전화 통신 엔터티(예: PBX, 아날로그 전화 통신 어댑터 등)에 연결할 수도 있습니다. SBC에 연결된 모든 PSTN 연결 옵션이 작동됩니다. (SBC에 대한 PSTN 트렁크 구성은 SBC 공급 업체 또는 트렁크 공급자를 참조하시기 바랍니다.)|
|Microsoft 365 또는 Office 365 조직|Microsoft 365 Office 365 사용자 및 SBC에 대한 구성 및 Microsoft Teams 가정하는 데 사용하는 조직 또는 조직입니다.|
|사용자 등록 기관|사용자는 홈에 Microsoft 365 Office 365.<br/>회사에 온-프레미스 비즈니스용 Skype 또는 Lync 환경에 하이브리드 연결로 Microsoft 365 Office 365 온-프레미스에 있는 사용자에 대해 음성을 Teams 수 없습니다.<br/><br/>사용자의 등록 기관을 확인하기 위해 다음 비즈니스용 Skype PowerShell cmdlet을 사용하세요.<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>cmdlet의 출력은 다음을 표시해야 합니다.<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|도메인|사용자 또는 조직에 하나 이상의 도메인이 Microsoft 365 Office 365 있습니다.<br/><br/>테넌트에 대해 자동으로 생성되는 \* 기본 도메인인 .onmicrosoft.com 사용할 수 없습니다.<br/><br/>도메인을 확인하려면 다음 온라인 PowerShell cmdlet을 비즈니스용 Skype 수 있습니다.<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>도메인 및 Microsoft 365 또는 Office 365 대한 자세한 내용은 [Domains FAQ 를 참조하세요.](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)|
|SBC에 대한 공용 IP 주소|SBC에 연결하는 데 사용할 수 있는 공용 IP 주소입니다. SBC 유형에 따라 SBC는 NAT를 사용할 수 있습니다.|
|SBC에 대한 FQDN(완전 자격을 갖춘 도메인 이름)|SBC의 FQDN은 FQDN의 도메인 부분이 사용자 또는 조직에서 등록된 Microsoft 365 Office 365 있습니다. 자세한 내용은 [SBC 도메인 이름 을 참조하세요.](#sbc-domain-names)|
|SBC에 대한 공용 DNS 항목 |SBC FQDN을 공용 IP 주소에 매핑하는 공용 DNS 항목입니다. |
|SBC에 대한 공용 신뢰할 수 있는 인증서 |직접 라우팅과의 모든 통신에 사용할 SBC에 대한 인증서입니다. 자세한 내용은 SBC에 대한 공용 신뢰할 수 [있는 인증서를 참조하세요.](#public-trusted-certificate-for-the-sbc)|
|직접 라우팅에 대한 연결 지점 |직접 라우팅의 연결 지점은 다음 세 가지 FQDNS입니다.<br/><br/>`sip.pstnhub.microsoft.com` – 전역 FQDN을 먼저 시도해야 합니다.<br/>`sip2.pstnhub.microsoft.com` – 보조 FQDN은 지리적으로 두 번째 우선 순위 지역에 매핑됩니다.<br/>`sip3.pstnhub.microsoft.com` – Tertiary FQDN은 지리적으로 세 번째 우선 순위 지역에 매핑됩니다.<br/><br/>구성 요구 사항에 대한 자세한 내용은 [SIP Signaling: FQDNs를 참조하세요.](#sip-signaling-fqdns)|
|직접 라우팅 미디어에 대한 방화벽 IP 주소 및 포트 |SBC는 클라우드에서 다음 서비스에 통신합니다.<br/><br/>신호를 처리하는 SIP 프록시<br/>Media Bypass가 있는 경우를 제외하고 미디어를 처리하는 Media Processor<br/><br/>이러한 두 서비스에는 Microsoft Cloud에 별도의 IP 주소가 있습니다. 이 문서의 나중에 설명되어 있습니다.<br/><br/>자세한 내용은 URL 및 [IP 주소 범위의](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) Microsoft Teams [섹션을 참조하세요.](/office365/enterprise/urls-and-ip-address-ranges) |
|미디어 전송 프로필|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
미디어에 대한 방화벽 IP 주소 및 Microsoft Teams 포트 |자세한 내용은 URL 및 [IP 주소 범위를 참조하세요.](/office365/enterprise/urls-and-ip-address-ranges) |
|||

## <a name="licensing-and-other-requirements"></a>라이선스 및 기타 요구 사항 

직접 라우팅 사용자는 다음 라이선스를 Microsoft 365 Office 365. 

- Microsoft 전화 시스템. 
- Microsoft Teams + 비즈니스용 Skype 계획 2(라이선스에 포함된 경우)입니다.
- Microsoft 오디오 회의(라이선스가 필요한 경우의 특정 예제는 아래 노트 및 단락을 참조하세요.

> [!NOTE]
> 비즈니스용 Skype 계획이 포함된 라이선스 계약에서 계획을 제거하면 안 됩니다. 
> 
> [!IMPORTANT]
> GCC 높음 및 DoD 사용자는 G5에 포함된 오디오 회의 라이선스를 사용하지 않도록 설정하고 직접 라우팅이 완전히 구성될 때까지 오디오 회의를 사용하도록 대기해야 합니다. 사용자는 오디오 회의 라이선스를 사용하도록 설정하기 전에 전화 접속 전화 번호와 작동 다이얼 패드를 구성해야 합니다. 자세한 내용은 High 및 [DoD에](./audio-conferencing-with-direct-routing-for-gcch-and-dod.md) 대한 직접 라우팅을 GCC 오디오 회의를 참조합니다.


> [!IMPORTANT]
>  외부 참가자를 예약된 모임에 추가하려면 전화 접속 번호를 제공하거나 전화 접속 번호를 제공하여 오디오 회의 라이선스가 필요합니다.
> 높은 GCC DoD의 경우 G5 사용자에 대한 오디오 회의 라이선스를 할당하지 않습니다.  G3 사용자의 경우 직접 라우팅이 완전히 구성되어 사용자가 작업 다이얼 패드를 사용할 때까지 오디오 회의 라이선스를 할당하지 않습니다.


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>Ad Hoc Call 에스컬레이터 및 오디오 회의 라이선스

사용자 Teams PSTN에 일대일 Teams 시작하거나 PSTN Teams Teams PSTN 참가자를 추가할 수 있습니다. 이 시나리오를 추가 회의라고 합니다. 호출이 걸리는 경로는 호출을 에스컬레이터하는 사용자가 Microsoft 오디오 회의 라이선스가 할당되어 있는지 여부에 따라 결정됩니다.

- 호출을 Teams 사용자에게 Microsoft 오디오 회의 라이선스가 할당된 경우 에스컬레이터는 Microsoft 오디오 회의 서비스를 통해 발생합니다. 기존 호출에 초대된 원격 PSTN 참가자는 들어오는 호출에 대한 알림을 받고 에스컬레이터를 시작한 사용자에 할당된 Microsoft Teams 수를 볼 수 있습니다.
- 호출을 Teams 사용자에게 Microsoft 오디오 회의 라이선스가 할당되지 않은 경우, 직접 라우팅 인터페이스에 연결된 세션 테두리 컨트롤러를 통해 에스컬레이터가 발생합니다. 통화에 초대된 원격 PSTN 참가자는 들어오는 호출에 대한 알림을 받고 에스컬레이터를 Teams 사용자의 수를 볼 수 있습니다. 에스컬레이터에 사용되는 특정 SBC는 사용자의 라우팅 정책에 의해 정의됩니다. 


또한 다음을 확인해야 합니다.
 
- CsOnlineVoiceRoutingPolicy는 사용자에게 할당됩니다. 
- 개인 호출 허용은 테넌트 수준에서 Microsoft Teams. 

또한 직접 라우팅은 Microsoft 통화 계획에 대해 라이선스가 부여된 사용자를 지원합니다. Microsoft 전화 호출 계획이 있는 시스템은 직접 라우팅 인터페이스를 사용하여 일부 호출을 라우팅할 수 있습니다. 그러나 사용자의 전화 번호는 온라인에서 획득하거나 Microsoft로 이식해야 합니다.  

동일한 사용자에 대한 통화 계획 및 직접 라우팅 연결 혼합은 선택 사항이지만 유용할 수 있습니다(예: 사용자가 Microsoft 통화 요금제가 할당되지만 SBC를 사용하여 일부 호출을 라우팅하려는 경우). 가장 일반적인 시나리오 중 하나는 타사 PBX에 대한 호출입니다.  타사 PBX를 사용하는 경우, 타사 PBX에 연결된 휴대폰에 대한 호출을 제외한 모든 호출은 Microsoft 통화 요금제로 라우팅되지만 타사 PBX에 연결된 휴대폰에 대한 호출은 SBC로 이동하므로 PSTN이 아닌 엔터프라이즈 네트워크 내에서 유지됩니다. 

라이선스에 대한 전화 시스템 자세한 내용은 Office [](https://products.office.com/compare-all-microsoft-office-products?tab=2) 옵션을 [참조하세요.](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options) 

라이선스에 대한 전화 시스템 자세한 내용은 추가 Microsoft Teams 라이선스 [를 참조하세요.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) 

## <a name="supported-end-points"></a>지원되는 엔드포인트 

끝점으로 사용할 수 있습니다.

- 모든 Teams 클라이언트입니다. 
- 공용 영역 전화. 에 대한 공용 영역 전화 [라이선스 Microsoft Teams.](./set-up-common-area-phones.md) 직접 라우팅을 사용하여 공용 영역 전화 계획 라이선스가 필요하지 않습니다.
- 비즈니스용 Skype 3PIP 휴대폰을 사용할 수 있습니다. 전화 [비즈니스용 Skype(3PIP)](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351) 지원 및 Microsoft Teams


## <a name="sbc-domain-names"></a>SBC 도메인 이름

SBC 도메인 이름은 테넌트의 도메인에 등록된 이름 중 하나에 있어야 합니다. \*SBC의 FQDN onmicrosoft.com .onmicrosoft.com 테넌트는 사용할 수 없습니다.

다음 표에서는 테넌트에 등록된 DNS 이름의 예제, SBC에 대한 FQDN으로 사용할 수 있는지 여부 및 유효한 FQDN 이름의 예제를 보여 주며,

|DNS 이름|SBC FQDN에 사용할 수 있습니다.|FQDN 이름의 예|
|:--- |:--- |:--- |
contoso.com|예|**유효한 이름:**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|아니요|*.onmicrosoft.com 도메인 사용은 SBC 이름에 지원되지 않습니다.

새 도메인 이름을 사용하려는 경우를 가정합니다. 예를 들어 테넌트는 테넌트에 contoso.com 도메인 이름으로 등록되어 있으며, 이 도메인을 sbc1.sip.contoso.com. SBC를 이름과 페어링하려면 sbc1.sip.contoso.com 도메인 이름과 sip.contoso.com 도메인 이름을 등록해야 합니다. 도메인 이름을 등록하기 sbc1.sip.contoso.com SBC와 페어링을 시도하는 경우 다음 오류가 발생합니다. "이 테넌트에 대해 구성되지 않은 "sbc1.sip.contoso.com" 도메인을 사용할 수 없습니다."
도메인 이름을 추가한 후 UPN 계정으로 사용자를 만들고 user@sip.contoso.com 라이선스를 Teams 합니다. 테넌트의 도메인에 도메인 이름을 추가하고 새 이름이 있는 사용자가 만들어지며 라이선스가 사용자에게 할당된 후 도메인 이름을 완전히 프로비전하는 데 최대 24시간이 걸릴 수 있습니다. 

회사에 하나의 테넌트에 여러 개의 SIP 주소 공간이 있을 수 있습니다. 예를 들어 회사에서 SIP 주소 contoso.com 공간으로 사용할 수 fabrikam.com 두 번째 SIP 주소 공간으로 사용할 수 있습니다. 일부 사용자는 주소가 user@contoso.com 있으며 일부 사용자는 주소가 user@fabrikam.com. 

SBC에는 하나의 FQDN만 필요하며 페어링된 테넌트의 주소 공간에서 사용자를 서비스할 수 있습니다. 예를 들어 이름이 sbc1.contoso.com SBC는 동일한 테넌트에 등록된 경우 주소가 user@contoso.com user@fabrikam.com 사용자에 대한 PSTN 트래픽을 받고 보낼 수 있습니다.  

## <a name="public-trusted-certificate-for-the-sbc"></a>SBC에 대한 공용 신뢰할 수 있는 인증서

CSR(인증 서명 요청)을 생성하여 SBC에 대한 인증서를 요청하는 것이 좋습니다. SBC에 대한 CSR을 생성하는 방법에 대한 특정 지침은 SBC 공급업체에서 제공하는 상호 연결 지침 또는 설명서를 참조하세요. 

  > [!NOTE]
  > 대부분의 CAS(인증서 기관)는 개인 키 크기를 2048 이상으로 요구합니다. CSR을 생성하는 경우 이 사실에 유의해야 합니다.

인증서에는 SBC FQDN을 공통 이름(CN) 또는 주체 대체 이름(SAN) 필드로 지정해야 합니다. 인증서는 중간 공급자가 아닌 인증 기관에서 직접 발급해야 합니다.

또는 직접 라우팅은 CN 및/또는 SAN의 와일드카드를 지원하며 와일드카드는 표준 [RFC HTTP Over TLS](https://tools.ietf.org/html/rfc2818#section-3.1)를 준수해야 합니다. SBC \* FQDN contoso.com .sbc.contoso.com .sbc.test.contoso.com.

인증서는 다음 루트 인증서 기관 중 하나에서 생성해야 합니다.

- AffirmTrust
- AddTrust External CA Root
- Baltimore CyberTrust Root*
- Buypass
- 사이버 보안
- 클래스 3 공용 주 인증 기관
- Comodo Secure Root CA
- Deutsche Telekom 
- DigiCert Global Root CA
- DigiCert High Assurance EV Root CA
- 트러스트
- GlobalSign
- Go Daddy
- GeoTrust
- Verisign, Inc. 
- SSL.com
- 스타필드
- 시만텍 Enterprise 모바일 루트 
- SwissSign
- 타임스탬프 CA 해동
- Trustwave
- TeliaSonera 
- T-Systems International GmbH(Deutsche Telekom)
- QuoVadis
- USERTrust RSA 인증 기관
- Hongkong Post Root CA 1,2,3
- Sectigo Root CA

GCCH Office 365 DoD 환경에서 직접 라우팅의 경우 다음 루트 인증서 기관 중 하나에서 인증서를 생성해야 합니다.
- DigiCert Global Root CA
- DigiCert High Assurance EV Root CA

> [!NOTE]
> *상호 TLS(상호 TLS) 지원이 SBC의 Teams 연결에 대해 사용하도록 설정된 경우 TLS 컨텍스트의 SBC 신뢰할 수 있는 루트 저장소에 Baltimore CyberTrust 루트 인증서를 Teams 설치해야 합니다. (Microsoft 서비스 인증서가 Baltimore 루트 인증서를 사용하기 때문에입니다.) Baltimore 루트 인증서를 다운로드하려면 암호화 [Office 365 참조하세요.](/microsoft-365/compliance/encryption-office-365-certificate-chains)

Microsoft는 고객 요청에 따라 인증 기관을 추가하는 작업을 하고 있습니다. 

## <a name="sip-signaling-fqdns"></a>SIP 신호: FQDNS 

직접 라우팅은 다음 환경에서 제공됩니다.
- Microsoft 365 또는 Office 365
- Office 365 GCC
- Office 365 GCC 높음
- Office 365 DoD

Office 365, [](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) 고가 및 DoD와 같은 GCC GCC 미국 정부 환경에 대해 자세히 알아보십시오.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365, Office 365 및 Office 365 GCC 환경

직접 라우팅의 연결 지점은 다음 세 가지 FQDNS입니다.

- **sip.pstnhub.microsoft.com** FQDN - 먼저 시도해야 합니다. SBC에서 이 이름을 확인하기 위한 요청을 보내면 SBC에 Microsoft Azure 기본 Azure 데이터 센터를 지적하는 IP 주소를 반환합니다. 할당은 데이터 센터의 성능 메트릭 및 SBC에 대한 지리적 근접성을 기반으로 합니다. 반환된 IP 주소는 기본 FQDN에 해당합니다.
- **sip2.pstnhub.microsoft.com** - 보조 FQDN – 지리적으로 두 번째 우선 순위 지역에 매핑됩니다.
- **sip3.pstnhub.microsoft.com** - Tertiary FQDN – 지리적으로 세 번째 우선 순위 지역에 매핑됩니다.

다음 세 가지 FQDNS를 순서대로 배치해야 합니다.

- 최적의 환경을 제공합니다(로드가 적고 첫 번째 FQDN을 쿼리하여 할당된 SBC 데이터 센터에 가장 가깝습니다).
- SBC에서 임시 문제가 발생하는 데이터 센터에 연결될 때 장애 조치(failover)를 제공합니다. 자세한 내용은 아래 [장애 조치 메커니즘을](#failover-mechanism-for-sip-signaling) 참조하세요.  

FQDNs(sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com 및 sip3.pstnhub.microsoft.com)는 다음 서브넷의 IP 주소로 해결됩니다.

- 52.112.0.0/14
- 52.120.0.0/14

신호에 대한 주소와 수신 트래픽을 허용하려면 방화벽에서 이러한 모든 IP 주소 범위에 대한 포트를 열면 됩니다.  방화벽이 DNS 이름을 지원하는 경우 FQDN  sip-all.pstnhub.microsoft.com 모든 IP 서브넷으로 확인됩니다. 

### <a name="office-gcc-dod-environment"></a>Office GCC DoD 환경

직접 라우팅의 연결 지점은 다음 FQDN입니다.

**sip.pstnhub.dod.teams.microsoft.us** - 글로벌 FQDN입니다. DoD Office 365 미국 데이터 센터에만 존재하기 때문에 보조 및 세로 FQDNS가 없습니다.

FQDN sip.pstnhub.dod.teams.microsoft.us 다음 서브넷의 IP 주소로 해결됩니다.

- 52.127.64.0/21

신호에 대한 주소와 수신 트래픽을 허용하려면 방화벽에서 이러한 모든 IP 주소에 대한 포트를 열면 됩니다.

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC 환경

직접 라우팅의 연결 지점은 다음 FQDN입니다.

**sip.pstnhub.gov.teams.microsoft.us** – 글로벌 FQDN입니다. 높은 GCC 미국 데이터 센터에만 존재하기 때문에 보조 및 세로 FQDNS가 없습니다.

FQDN sip.pstnhub.gov.teams.microsoft.us 다음 서브넷의 IP 주소로 해결됩니다.

- 52.127.88.0/21

신호에 대한 주소와 수신 트래픽을 허용하려면 방화벽에서 이러한 모든 IP 주소에 대한 포트를 열면 됩니다. 방화벽이 DNS 이름을 지원하는 경우 FQDN  sip-all.pstnhub.gov.teams.microsoft.us 모든 IP 주소로 확인됩니다. 이 FQDN은 인바운드 호출 분류를 위해 페더리드 FQDN으로도 사용할 수 있습니다.

## <a name="sip-signaling-ports"></a>SIP 신호: 포트

직접 라우팅이 제공되는 Microsoft 365 Office 365 경우 다음 포트를 사용해야 합니다.
- Microsoft 365 또는 Office 365
- Office 365 GCC
- Office 365 GCC 높음
- Office 365 DoD

|트래픽|보낸 사람|받는 사람|원본 포트|대상 포트|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP 프록시|SBC|1024 – 65535|SBC에 정의되어 있습니다(하이/doD Office 365 GCC 포트 5061만 사용되어야 합니다.|
SIP/TLS|SBC|SIP 프록시|SBC에 정의|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>SIP 신호에 대한 장애 조치 메커니즘

SBC는 DNS 쿼리를 사용하여 문제를 sip.pstnhub.microsoft.com. SBC 위치 및 데이터 센터 성능 메트릭에 따라 기본 데이터 센터가 선택됩니다. 주 데이터 센터에서 문제가 있는 경우 SBC는 두 번째 할당된 sip2.pstnhub.microsoft.com 해결되는 데이터 센터를 시도하고, 두 지역의 데이터 센터를 사용할 수 없는 드문 경우 SBC는 세 가지 데이터 센터 IP를 제공하는 마지막 FQDN(sip3.pstnhub.microsoft.com)을 다시 시도합니다.

아래 표에서는 기본 데이터 센터, 보조 데이터 센터 및 세 가지 데이터 센터 간의 관계를 요약합니다.

|기본 데이터 센터가|EMEA|NOAM|아시아|
|:--- |:--- |:--- |:--- |
|보조 데이터 센터(sip2.pstnhub.microsoft.com)|미국|EU|미국|
|3차원 데이터 센터(sip3.pstnhub.microsoft.com)|아시아|아시아|EU|
|||||

## <a name="media-traffic-port-ranges"></a>미디어 트래픽: 포트 범위
미디어 우회 없이 직접 라우팅을 배포하려는 경우 아래 요구 사항이 적용됩니다. Media Bypass에 대한 방화벽 요구 사항은 직접 라우팅을 통해 미디어 우회 계획 [을 참조하세요.](./direct-routing-plan-media-bypass.md)



미디어 트래픽은 Microsoft Cloud의 별도 서비스로 및 부터 흐르고 있습니다. 미디어 트래픽의 IP 주소 범위는 다음과 같습니다.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365, Office 365 및 Office 365 GCC 환경

- 52.112.0.0/14(IP 주소는 52.112.0.1에서 52.115.255.254)입니다.
- 52.120.0.0/14(IP 주소는 52.120.0.1에서 52.123.255.254)입니다.

### <a name="office-365-dod-environment"></a>Office 365 DoD 환경

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC 환경

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>포트 범위(모든 환경에 적용 가능)
Media Processor의 포트 범위는 다음 표에 표시됩니다. 

|트래픽|보낸 사람|받는 사람|원본 포트|대상 포트|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|미디어 프로세서|SBC|3478-3481 및 49152 - 53247|SBC에 정의|
|UDP/SRTP|SBC|미디어 프로세서|SBC에 정의|3478-3481 및 49152 - 53247|

  > [!NOTE]
  > Microsoft는 SBC에서 동시 호출당 두 개 이상의 포트를 권장합니다.


## <a name="media-traffic-media-processors-geography"></a>미디어 트래픽: 미디어 프로세서 지리

미디어 트래픽은 미디어 프로세서라는 구성 요소를 통해 흐름합니다. 미디어 프로세서는 SIP proxies와 동일한 데이터 센터에 배치됩니다.

- 미국(미국 서부 및 미국 동부 데이터 센터의 2개)
- 유럽(암스테르담 및 더블린 데이터 센터)
- 아시아(싱가포르 데이터 센터)
- 일본(JP 동부 및 서부 데이터 센터)
- 오스트레일리아(AU 동부 및 남동부 데이터 센터)

## <a name="media-traffic-codecs"></a>미디어 트래픽: 코덱

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>SBC와 클라우드 미디어 프로세서 또는 클라이언트 Microsoft Teams 다리입니다.
미디어 우회 사례 및 비우회 사례 모두에 적용됩니다.

세션 테두리 컨트롤러와 클라우드 미디어 프로세서(미디어 우회 없이) 또는 Teams 클라이언트와 SBC 간의 직접 라우팅 인터페이스는 다음 코덱을 사용할 수 있습니다.

- 비미디어 우회(SBC에서 클라우드 미디어 프로세서): SILK, G.711, G.722, G.729
- 미디어 우회(SBC에서 클라이언트로 Teams): SILK, G.711, G.722, G.729

제품에서 바람직하지 않은 코덱을 제외하여 세션 테두리 컨트롤러에서 특정 코덱을 강제로 사용할 수 있습니다.

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>클라이언트와 Microsoft Teams 미디어 프로세서 간의 다리
비미디어 우회 사례에만 적용됩니다. Media Bypass를 통해 미디어는 클라이언트와 SBC Teams 직접 흐름합니다.

Cloud Media Processor와 클라이언트 Microsoft Teams SILK 또는 G.722가 사용됩니다. 이 다리의 코덱 선택은 여러 매개 변수를 고려하는 Microsoft 알고리즘을 기반으로 합니다. 


## <a name="supported-session-border-controllers-sbcs"></a>지원되는 세션 테두리 컨트롤러(SBC)

Microsoft는 직접 라우팅과 쌍을 이루기 위해 인증된 SBC만 지원합니다. 비즈니스 Enterprise Voice 중요하기 때문에 Microsoft는 선택한 SBC를 사용하는 집약적인 테스트를 실행하고 SBC 공급업체와 협력하여 두 시스템이 호환되도록 합니다. 

유효성이 검사된 디바이스는 직접 라우팅에 Teams 인증으로 나열됩니다. 인증된 디바이스는 모든 시나리오에서 작동할 수 있습니다. 

지원되는 SBC에 대한 자세한 내용은 직접 라우팅에 대해 인증된 세션 테두리 컨트롤러 목록을 [참조하세요.](direct-routing-border-controllers.md)

 
## <a name="see-also"></a>참고 항목

[직접 라우팅 구성](direct-routing-configure.md)
