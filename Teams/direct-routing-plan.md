---
title: 직접 라우팅 계획
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Microsoft Phone 시스템 직접 라우트를 통해 지원되는 SBC(Session Border Controller)를 Microsoft Phone System에 연결하는 방법에 대해 알아봅니다.
ms.openlocfilehash: bb711b72fb200ceec9d2c50c86f6f977436c9c02
ms.sourcegitcommit: cd16ff6007e0a798493e2fa469c6681993380420
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/23/2020
ms.locfileid: "46860809"
---
# <a name="plan-direct-routing"></a>직접 라우팅 계획

> [!Tip]
> 다음 세션을 시영하여 직접 라우트로 의한 이점, 계획 방법 및 배포 방법을 알아보세요. [Microsoft Teams에서 직접 라우아웃](https://aka.ms/teams-direct-routing)

Microsoft Phone 시스템 직접 라우터를 사용하여 지원되는 SBC(고객이 제공하는 SBC)를 Microsoft Phone 시스템에 연결할 수 있습니다.  예를 들어 다음 다이어그램과 같이 Microsoft Teams 클라이언트와의 전화 접미사 PSTN(공중 전화 교차 네트워크) 연결을 구성할 수 있습니다. 

![SharePoint Online 이제 비즈니스용-프레미스 PSTN 연결 구성을 보여 주는 다이어그램](media/PlanDirectRouting1-PSTNwithTeams.png "Microsoft Teams 클라이언트와 의해")

  > [!NOTE]
  > 비즈니스용 Skype Online에서는 고객이 제공한 SBC를 페어변경할 수도 있지만, 이를 사용하려면 SBC와 Microsoft 클라우드 사이에 클라우드 커넥터라고 하는 특별한 버전의 비즈니스용 Skype 서버 배포 또는 특수 버전의 비즈니스용 Skype가 필요합니다. 이 시나리오는 하이브리드 음성이라고 합니다. 반면, 직접 라우아웃하면 지원되는 SBC와 Microsoft 클라우드 간에 직접 연결할 수 있습니다. 

직접 라우트를 통해 SBC를 연결하여 거의 모든 통신 트리크 크게 또는 타사 PSTN 장비와 상호 연결할 수 있습니다. 직접 라우트를 사용하면 다음을 수행할 수 있습니다. 

- Microsoft 휴대폰 시스템에서 가상으로 사용 
- PBX(Private PBX), 아침 장치, Microsoft Phone 시스템과 같은 고객이 소유한 전화기 장치 간의 상호 운용성을 구성합니다.

또한 Microsoft는 통화 요금제와 같은 클라우드 내 음성 솔루션도 제공합니다. 그러나 다음과 같은 경우 하이브리드 음성 솔루션이 조직에 가장 적합할 수 있습니다. 

- 해당 국가에서는 Microsoft 통화 플랜을 사용할 수 없습니다. 
- 조직에는 타사 아동로그 장치, 통화 센터 등에 대한 연결이 필요합니다. 
- 조직에 PSTN 통신 사업자와 기존 계급업체가 있습니다.

직접 라우터는 또한 Microsoft 통화 요금제에 대한 추가 라이선스를 보유한 사용자도 지원합니다. 자세한 내용은 전화 [시스템 및 통화 플랜을 참조하세요.](calling-plan-landing-page.md) 

직접 라우트를 사용할 경우 사용자가 예약된 회의에 참여할 경우 Microsoft 오디오 회의 서비스에서 전화 접속 번호를 제공하며 적절한 라이선스가 필요합니다.  전화를 걸 때 Microsoft 오디오 회의 서비스에서 온라인 통화 기능을 사용하여 통화를 배치한 다음 에 우선적으로 라이선스가 필요합니다. (사용자에게 Microsoft 오디오 회의 라이선스가 없는 경우 직접 라우팅을 통한 통화 라우팅을 통한 통화 라우팅을 통한 통화 라우팅) 자세한 내용은 [Teams를 사용하는 온라인 모임을 참조하세요.](https://products.office.com/microsoft-teams/online-meeting-solutions) 
 
직접 라우트 는 성공적인 구현을 위한 중요한 구성 배포의 계획입니다. 이 문서에서는 인프라 및 라이선스 요구 사항에 대해 설명하고 SBC 연결에 대한 정보를 제공합니다. 

- [인프라 요구 사항](#infrastructure-requirements)
- [라이선스 라이선스 및 기타 요구 사항](#licensing-and-other-requirements)
- [SBC 도메인 이름](#sbc-domain-names)
- [SBC에 대해 신뢰할 수 있는 인증서](#public-trusted-certificate-for-the-sbc)
- [SIP 신호: FQDN](#sip-signaling-fqdns)
- [SIP 신호: 포트](#sip-signaling-ports)
- [미디어 트래오: 포트 범위](#media-traffic-port-ranges)
- [지원되는 세션 테두리 컨트롤러(SBC)](#supported-session-border-controllers-sbcs)

직접 라우터를 구성하는 방법에 대한 자세한 내용은 직접 [라우트 구성을 참조하세요.](direct-routing-configure.md)

## <a name="infrastructure-requirements"></a>인프라 요구 사항
지원되는 SBC, 도메인 및 기타 네트워크 연결 요구 사항에 대한 인프라 요구 사항은 다음 표에 나와 있습니다.  

|인프라 요구 사항|필요한 사항은 다음과 같습니다.|
|:--- |:--- |
|SBC(Session Border Controller)|지원되는 SBC. 자세한 내용은 [지원되는 SBC를 참조하세요.](#supported-session-border-controllers-sbcs)|
|SBC에 연결된 Telephony 트리크|SBC에 연결된 하나 이상의 라이트 트리키트 한쪽 끝에서, SBC는 직접 라우아웃을 통해 Microsoft Phone 시스템에 연결합니다. SBC는 PBX, Analog Telephony Adapters 등의 타사 Telephony 에타트에도 연결할 수 있습니다. SBC에 연결된 모든 PSTN 연결 옵션이 작동합니다. PSTN 트리버의 구성의 경우 SBC 공급업계 또는 트리스트 공급자를 참조하세요.|
|Microsoft 365 또는 Office 365 조직|Microsoft Teams 사용자와 구성 및 SBC에 연결하는 용도로 사용하는 Microsoft 365 또는 Office 365 조직|
|사용자 제공|사용자는 Microsoft 365 또는 Office 365에서 가정되어야 합니다.<br/>회사에 Microsoft 365 또는 Office 365에 대한 하이브리드 연결을 사용하는 비즈니스용 Skype 또는 Lync 환경이 있는 경우, 가정용으로 가정된 사용자에 대해 Teams에서 Teams를 사용하도록 설정할 수 없습니다.<br/><br/>사용자를 보유하고 있는지 확인하려면 다음의 비즈니스용 Skype Online PowerShell cmdlet을 사용하세요.<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>cmdlet의 출력은 다음과 같이 표시됩니다.<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|도메인|Microsoft 365 또는 Office 365 조직에 추가된 하나 이상의 도메인<br/><br/>테넌트에 대해 자동으로 만들어지는 기본 도메인 \* (.onmicrosoft.com)을 사용할 수 없습니다.<br/><br/>도메인을 보려면 다음의 비즈니스용 Skype Online PowerShell cmdlet을 사용하면 됩니다.<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>도메인 및 Microsoft 365 또는 Office 365 조직에 대한 자세한 내용은 도메인 [FAQ를 참조하세요.](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)|
|SBC용 공용 IP 주소|SBC에 연결하는 데 사용할 수 있는 공용 IP 주소입니다. SBC의 유형에 따라 SBC에서 NAT를 사용할 수 있습니다.|
|SBC의 FQDN(정규화된 도메인 이름)입니다.|FQDN의 FQDN은 Microsoft 365 또는 Office 365 조직의 등록된 도메인 중 하나입니다. 자세한 내용은 [SBC 도메인 이름을 참조하세요.](#sbc-domain-names)|
|SBC에 대한 공용 DNS 항목 |공용 IP 주소에 SBC FQDN을 매핑하는 공용 DNS 항목입니다. |
|SBC에 대해 신뢰할 수 있는 인증서 |SBC에 대한 인증서는 모든 직접 라우트와의 통신에 사용되는 인증서입니다. 자세한 내용은 [SBC에 대한 공용 신뢰할 수 있는 인증서를 참조하세요.](#public-trusted-certificate-for-the-sbc)|
|직접 라우아웃을 위한 연결점 |Direct 라우로 라우로 라우트의 연결점은 다음 세 가지 FQDN 세 가지입니다.<br/><br/>`sip.pstnhub.microsoft.com` - 전역 FQDN에서는 먼저 시도해야 합니다.<br/>`sip2.pstnhub.microsoft.com` – 보조 FQDN, 지리적으로 두 번째 우선 순위 영역에 매핑됩니다.<br/>`sip3.pstnhub.microsoft.com` – 터티태시 FQDN, 지리적으로 세 번째 우선 순위 지역에 매핑됩니다.<br/><br/>구성 요구 사항에 대한 자세한 내용은 [SIP 신호를 참조하세요. FQDN](#sip-signaling-fqdns)|
|방화벽 IP 주소 및 직접 라우트 라우트 미디어의 포트 |SBC는 클라우드에서 다음 서비스에 통신합니다.<br/><br/>신호를 핸드리는 SIP 프록시<br/>미디어 바이어스가 있는 경우를 제외하고 미디어 를 처리하는 미디어 프로세서<br/><br/>이러한 두 서비스에는 이 문서의 뒷부분에 설명된 Microsoft 클라우드에 설명되어 있습니다.<br/><br/>자세한 내용은 URL 및 IP 주소 범위의 [Microsoft Teams](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) [섹션을 참조하세요.](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) |
|미디어 전송 프로필|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Microsoft Teams 미디어용 방화벽 IP 주소 및 포트 |자세한 내용은 [URL 및 IP 주소 범위를 참고하세요.](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) |
|||

## <a name="licensing-and-other-requirements"></a>라이선스 라이선스 및 기타 요구 사항 

Direct 라우로이하는 사용자는 Microsoft 365 또는 Office 365에 다음 라이선스가 할당되어 있어야 합니다. 

- Microsoft 휴대폰 시스템. 
- 라이선스에 포함된 경우 Microsoft Teams + 비즈니스용 Skype 요금제 2
- Microsoft 오디오 회의(라이선스가 필요한 경우에 대한 구체적인 예를 보려면 아래의 노트와 단락을 읽어보세요.

> [!NOTE]
> 비즈니스용 Skype 요금제를 포함한 모든 라이선언 계약에서 제거해서는 안 됩니다. 


> [!IMPORTANT]
>  예약된 모임에 전화를 걸거나 전화 접속 번호를 제공하여 예약된 모임에 외부 참가자를 추가하려는 경우에는 오디오 회의 라이선스가 필요합니다.


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>임시 통화 이메일 및 오디오 회의 라이선스

Teams 사용자는 1:1 Teams를 PSTN 또는 Teams에서 통화로 시작하고 이 사용자에게 PSTN 참가자를 추가할 수 있습니다. 이 시나리오를 임시 전화 회의라고 합니다. 통화가 수행되는 경로는 사용자에게 Microsoft 오디오 회의 라이선스가 할당되어 있는지 여부에 따라 다를 수 있습니다.

- 통화를 에스처하는 팀 사용자가 Microsoft 오디오 회의 라이선스가 할당된 경우 Microsoft 오디오 회의 서비스를 통해 이스al이 수행됩니다. 기존 전화에 초대를 받은 원격 PSTN 참가자는 수신 전화에 대한 알림을 받고 이들에 에스크아인을 시작한 Teams 사용자에게 할당한 Microsoft 브리지의 번호가 표시됩니다.
- 통화를 에스처하는 Teams 사용자가 Microsoft 오디오 회의 라이선스가 할당되어 있지 않은 경우, 직접 라우트 라우트 인터페이스에 연결된 세션 테두리 컨트롤러를 통해 에스테이션이 진행됩니다. 전화에 초대된 원격 PSTN 참가자는 수신 전화에 대한 알림을 받고 에스크래걸이션을 시작한 Teams 사용자의 번호를 보게 됩니다. 에스크라인에 사용되는 특정 SBC는 사용자의 라우버로 정책에 의해 정의됩니다. 


또한 다음 사항을 확인해야 합니다.
 
- CsOnlineVoiceRoutingPolicy이 사용자에게 할당됩니다. 
- Microsoft Teams의 테넌트 수준에서 비공개 통화 허용을 사용할 수 있습니다. 

직접 라우는 Microsoft 통화 요금제에 대한 라이선스가 있는 사용자도 지원합니다. 통화 플랜을 사용하는 Microsoft Phone 시스템에서는 일부 통화에 직접 라우팅 인터페이스를 사용해 라우팅할 수 있습니다. 하지만 사용자의 전화 번호는 Microsoft에 연결하거나 Microsoft로 포인트해야 합니다.  

같은 사용자에 대한 전화 걸기 플랜 및 직접 라우팅 연결을 혼합하는 것은 선택 사항이지만(예: 사용자에게 Microsoft 통화 요금제를 할당하지만 SBC를 사용하여 일부 통화를 라우팅하려는 경우) 유용할 수 있습니다. 가장 일반적인 시나리오 중 하나는 타사 PBX에 호출됩니다.  타사 PBX를 사용하는 경우, 해당 PBX에 연결된 전화를 제외한 모든 통화는 Microsoft 통화 요금제를 통해 라우팅되지만, 타사 PBX에 연결된 전화기로 통화를 하며, 이때 PSTN이 아닌 엔터프라이즈 네트워크 내에서 유지됩니다. 

전화 시스템 라이선스에 대한 자세한 내용은 Office 및 [계획 옵션을](https://products.office.com/compare-all-microsoft-office-products?tab=2) [참조하세요.](https://technet.microsoft.com/library/office-365-plan-options.aspx) 

전화 시스템 라이선스에 대한 자세한 내용은 [Microsoft Teams 추가 기능 라이선스를 참조하세요.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) 

## <a name="supported-end-points"></a>지원되는 끝점 

끝점으로 사용할 수 있습니다.

- 모든 Teams 클라이언트. 
- 일반적인 영역 전화입니다. [Microsoft Teams의 공통 영역 전화 라이선스를 설정합니다.](https://docs.microsoft.com/microsoftteams/set-up-common-area-phones) 직접 라우트가 포함된 공식 영역 전화를 설정할 때는 통화 플랜 라이선스가 필요하지 않습니다.
- 비즈니스용 Skype 3PIP 휴대폰. [Microsoft Teams에서 비즈니스용 Skype 전화(3PIP) 지원 참조](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)


## <a name="sbc-domain-names"></a>SBC 도메인 이름

SBC 도메인 이름은 테넌트의 도메인에 등록된 이름 중 하나여야 합니다. \*SBC의 FQDN onmicrosoft.com 테넌트는 .mant로 사용할 수 없습니다.

다음 표에서는 테넌트에 대해 등록된 DNS 이름의 예, 이름을 SBC에 대한 FQDN으로 사용할 수 있는지 여부 및 유효한 FQDN 이름 예제를 보여 줍니다.

|DNS 이름|SBC FQDN에 사용할 수 있음|FQDN 이름의 예|
|:--- |:--- |:--- |
contoso.com|예|**유효한 이름:**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|아니요|*.onmicrosoft.com 도메인 사용이 SBC 이름에 대해 지원되지 않음

새 도메인 이름을 사용하려 한다고 가정합니다. 예를 들어 테넌트에 contoso.com 도메인 이름으로 등록되어 있는 경우 이 사용을 sbc1.sip.contoso.com. SBC를 이름 과로 sbc1.sip.contoso.com sip.contoso.com 테넌트의 도메인에 도메인 이름 셀을 등록해야 합니다. 도메인 이름을 등록하기 전에 sbc1.sip.contoso.com SBC를 페어백해 보려고 하면 다음과 같은 오류가 표시됩니다. "이 테넌트에 구성되지 않은 "sbc1.sip.contoso.com" 도메인을 사용할 수 없습니다.
도메인 이름을 추가한 후에도 UPN 인증을 사용하여 사용자를 user@sip.contoso.com Teams 라이선스를 할당해야 합니다. 테넌트의 도메인에 도메인 이름을 추가한 후 도메인 이름을 완전히 프로비전하는 데 최대 24시간이 걸릴 수 있고, 새 이름이 있는 사용자가 생성및 사용자에게 라이선스가 할당됩니다. 

한 테넌트에 여러 SIP 주소 공간이 있을 수 있습니다. 예를 들어 회사에서 SIP contoso.com SIP 주소 공간으로 사용하며 두 번째 fabrikam.com 이름으로 사용할 수 있습니다. 일부 사용자는 주소를 user@contoso.com 주소를 가지고 있고 일부 사용자는 주소를 user@fabrikam.com. 

SBC는 FQDN만 필요하고 해당 테넌트의 주소 공간에서 사용자를 서비스할 수 있습니다. 예를 들어 동일한 테넌트에 sbc1.contoso.com 사용자의 이름이 포함된 SBC는 주소를 가진 user@contoso.com 사용자의 PSTN user@fabrikam.com 트래스를 받고 보낼 수 있습니다. 이러한 SIP 주소 공간이 동일한 테넌트에 등록된 경우 주소를 가진 사용자의 PSTN 트래래래를 받고 보낼 수 있습니다.  

## <a name="public-trusted-certificate-for-the-sbc"></a>SBC에 대해 신뢰할 수 있는 인증서

Microsoft는 CSR(인증 서명 요청)을 생성하여 SBC에 대한 인증서를 요청하는 것을 권장합니다. SBC용 CSR을 생성하는 구체적인 지침은 SBC 공급업체에서 제공하는 상호 연결 지침 또는 설명서를 참조하세요. 

  > [!NOTE]
  > 대부분의 CA(인증 기관)에서는 2048 이상이어야 합니다. CSR을 생성할 때 유의해야 합니다.

인증서는 제목 필드에 CN(일반 이름)으로SBC FQDN을 가져와야 합니다.

또는, 직접 라우트는 SAN에서 와일드카드를 지원하며, 와일드카드를 [TLS에 따라 표준 RFC HTTP에 따라 준수해야 합니다.](https://tools.ietf.org/html/rfc2818#section-3.1) 예를 들어 \* SAN에서 .contoso.com 사용하여 SBC FQDN sbc.contoso.com 일치하지만 과일하지 sbc.test.contoso.com.

인증서는 다음과 같은 루트 인증 기기 중 하나에 의해 생성되어야 합니다.

- AffirmTrust
- AddTrust External CA Root
- Baltimore CyberTrust 루트*
- Buypass
- 사이버 트러스트
- 클래스 3 공개 인증 기부
- 확보 사용자 루트 CA
- Deutsche Telekom 
- DigiCert Global Root CA
- DigiCert High Assurance EV 루트 CA
- Entrust
- GlobalSign
- Go Daddy
- GeoTrust
- Verisign, Inc. 
- SSL.com
- Starfield
- Microsoft용 Symantec Enterprise Mobile 루트 
- SwissSign
- 태그 타임스탬프
- Trustwave
- TeliaSonera 
- T-Systems International GmbH(Deutsche Telekom)
- QuoVadis



> [!NOTE]
> *SBC에서 Teams 연결에 MTLS(Mutual TLS) 지원을 사용하도록 설정한 경우 Teams TLS 콘텐츠의 SBC 신뢰할 수 있는 루트 저장소에 Baltimore CyberTrust 루트 인증서를 설치해야 합니다. (Microsoft 서비스 인증서에서 Baltimore 루트 인증서를 사용사용기 때문입니다.) Baltimore 루트 인증서를 다운로드하려면 [Office 365 암호화 체인을 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/encryption-office-365-certificate-chains)

Microsoft는 고객 요청에 따라 다른 인증 기관 추가 작업을 기대하기하기하기 작업 중입니다. 

## <a name="sip-signaling-fqdns"></a>SIP 신호: FQDN 

직접 라우트는 다음과 같은 환경에서 제공됩니다.
- Microsoft 365 또는 Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

GCC, GCC High 및 DoD 같은 [Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) 및 미국 정부 환경에 대해 자세히 알아보세요.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365, Office 365 및 Office 365 GCC 환경

Direct 라우로 라우로 라우트의 연결점은 다음 세 가지 FQDN 세 가지입니다.

- **sip.pstnhub.microsoft.com** - 전역 FQDN –를 먼저 시도해야 합니다. SBC가 이 이름을 확인하기 위한 요청을 보내면 Microsoft Azure DNS 서버가 SBC에 할당된 기본 Azure 데이터 센터를 가리키는 IP 주소를 반환합니다. 배정은 데이터 센터의 성능 메트릭및 SBC와지의 지리적 회전을 기준으로 합니다. 반환된 IP 주소는 기본 FQDN에 해당합니다.
- **sip2.pstnhub.microsoft.com** - 보조 FQDN – 일반 우선 순위 영역에 지리적으로 매핑됩니다.
- **sip3.pstnhub.microsoft.com** - 터키 FQDN – 지리적으로 세 번째 우선 순위 지역에 지도됩니다.

이 세 개의 FQDN을 순서대로 배치해야 합니다.

- 최적의 환경을 제공합니다(첫 번째 FQDN을 쿼리하여 할당된 SBC 데이터 센터에 는 적합한 단일 로드 및 가까운 경우).
- SBC의 연결이 임시 문제가 발생한 데이터 센터에 설정된 경우 장애 조치를 제공합니다. 자세한 내용은 [아래와 장애 해결 방법을](#failover-mechanism-for-sip-signaling) 참조하세요.  

FQDN – sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com sip3.pstnhub.microsoft.com+ 다음 IP 주소 중 하나로 해결됩니다.

- 52.114.148.0
- 52.114.132.46 
- 52.114.75.24 
- 52.114.76.76 
- 52.114.7.24 
- 52.114.14.70
- 52.114.16.74
- 52.114.20.29

수신 및 전송 트래프가 신호를 위한 주소에서 전송 송신 또는 전송되는 트래츠를 허용하려면 방화벽에 있는 모든 IP 주소에 대한 포트를 열어해야 합니다.  방화벽이 DNS 이름을 지원하는 경우 FQDN sip-all.pstnhub.microsoft.com 이 모든 IP 주소를 확인합니다. 


### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC 문서 환경

Direct 라우로아웃을 위한 연결점은 다음 FQDN입니다.

**sip.pstnhub.dod.teams.microsoft.us** - 글로버 FQDN. Office 365 DoD 환경은 미국 데이터 센터에만 존재하며 보조 FQDN은 없습니다.

FQDN sip.pstnhub.dod.teams.microsoft.us 다음 IP 주소 중 하나로 해결됩니다.

- 52.127.64.33
- 52.127.68.34

수신 및 전송 트래프가 신호를 위한 주소에서 전송 송신 또는 전송되는 트래츠를 허용하려면 방화벽에 있는 모든 IP 주소에 대한 포트를 열어해야 합니다.

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High 환경

Direct 라우로아웃을 위한 연결점은 다음 FQDN입니다.

**sip.pstnhub.gov.teams.microsoft.us** - 글로버 FQDN. GCC High 환경은 미국 데이터 센터에만 존재하며 보조 FQDN은 없습니다.

FQDN sip.pstnhub.gov.teams.microsoft.us 다음 IP 주소 중 하나로 해결됩니다.

- 52.127.88.59
- 52.127.92.64

수신 및 전송 트래프가 신호를 위한 주소에서 전송 송신 또는 전송되는 트래츠를 허용하려면 방화벽에 있는 모든 IP 주소에 대한 포트를 열어해야 합니다.

## <a name="sip-signaling-ports"></a>SIP 신호: 포트

직접 라우터가 제공되는 Microsoft 365 또는 Office 365 환경용 포트를 사용해야 합니다.
- Microsoft 365 또는 Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

|교대|보낸 사람|받는 사람|원본 포트|대상 포트|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP 프록시|SBC|1024 – 65535|SBC에 지정됨(Office 365 GCC High/DoD 전용 포트 5061이어야 합니다).|
SIP/TLS|SBC|SIP 프록시|SBC에 정의됨|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>SIP 신호를 위한 장애 조치 메커니바

SBC는 DNS 쿼리를 사용하여 전자 메일을 sip.pstnhub.microsoft.com. SBC 위치 및 데이터 센터 성능 메트릭을 기반으로 기본 데이터 센터가 선택되어 있습니다. 기본 데이터 센터에서 문제가 발생하는 경우 SBC가 sip2.pstnhub.microsoft.com 지정된 두 번째 데이터 센터에서 확인하나가 되어 야기도 하며, 두 지역의 데이터 센터를 사용할 수 없는 경우 SBC에서는 최상의 FQDN(sip3.pstnhub.microsoft.com)을 검색하여 세번째 데이터 센터 IP를 제공합니다.

아래 테이블에는 기본 데이터 센터, 보조, 용어 데이터 센터 사이의 관계가 요약되어 있습니다.

|기본 데이터 센터|EMEA|NOAM|ASIA|
|:--- |:--- |:--- |:--- |
|보조 데이터 센터(sip2.pstnhub.microsoft.com)|US|EU|US|
|Tertiary 데이터 센터(sip3.pstnhub.microsoft.com)|ASIA|ASIA|EU|
|||||

## <a name="media-traffic-port-ranges"></a>미디어 트래오: 포트 범위
미디어 바이패스 없이 직접 라우트를 배포하려는 경우 아래 요구 사항이 적용됩니다. 미디어 바이퍼스를 위한 방화벽 요구 사항은 직접 라우트가 있는 [미디어 바이어스 계획을 참조하세요.](https://docs.microsoft.com/microsoftteams/direct-routing-plan-media-bypass)



미디어 트래프는 Microsoft 클라우드의 별도의 서비스로/이동됩니다. 미디어 트래퍼의 IP 주소 범위는 다음과 같습니다.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365, Office 365 및 Office 365 GCC 환경

- 52.112.0.0/14(52.112.0.1에서 52.115.255.254 사이의 IP 주소)
- 52.120.0.0/14(52.120.0.1에서 52.123.255.254 사이의 IP 주소)

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC 문서 환경

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High 환경

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>포트 범위(모든 환경에 적합)
미디어 프로세서의 포트 범위는 다음 표에 나와 있습니다. 

|교대|보낸 사람|받는 사람|원본 포트|대상 포트|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|미디어 프로세서|SBC|3478-3481 및 49152 – 53247|SBC에 정의됨|
|UDP/SRTP|SBC|미디어 프로세서|SBC에 정의됨|3478-3481 및 49152 – 53247|

  > [!NOTE]
  > Microsoft는 SBC에서 동시 통화당 두 개 이상의 포트를 권장합니다.


## <a name="media-traffic-media-processors-geography"></a>미디어 트래치: 미디어 프로세서 지리적

미디어 트래프는 미디어 프로세서라는 구성 요소를 전달합니다. 미디어 프로세서는 SIP 프록시와 동일한 데이터 센터에 배치됩니다. 미디어 흐름을 최적화할 수 있는 추가적인 미디어 프로세서도 있습니다. 예를 들어 지금까지 호주에 SIP 프록시 구성 요소가 없지만 오스트레일리아에서 SIP 프록시 구성 요소가 있습니다. 미디어 프로세서의 필요성은 오스트레일리아에서 Singapore 또는 Hong Kong와 같은 트래스 장기까지 연장합니다. 오스트레일리아에서 Hong Kong 또는 Singapore로부터 Hong Kong 또는 Singapore로 인한 지연 시간은 SIP 트래스를 예약하는 데 시간이 부정적인 상태를 유지할 수 있습니다.

미디어 프로세서의 위치:

SIP 프록시 및 미디어 프로세서 구성 요소를 모두 배포하는 위치:
- 미국(미국 및 미국 동아시데이터 센터 둘)
- 유로(아버드, Dublin 데이터 센터)
- 아시아(Singapore 및 Hong Kong 데이터 센터)

미디어 프로세서만 배포되는 위치(위에 나열된 가장 가까운 데이터 센터를 사용한 SIP 흐름)
- 일본(JP East 및 West 데이터 센터)
- 호주(AU 동아시아 및 동대한 및 유사 데이터 센터)




## <a name="media-traffic-codecs"></a>미디어 트래계정: 코스

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>SBC와 클라우드 미디어 프로세서 또는 Microsoft Teams 클라이언트 간에 레지그합니다.
대/소문자를 바이스 대/소문자 모두에 적용합니다.

세션 테두리 컨트롤러와 클라우드 미디어 프로세서(미디어 바이패스 없음) 사이의 레그라우 라우터나 Teams 클라이언트와 SBC(미디어 바이패스가 사용됨) 사이의 레그라우 로그 인터페이스는 다음 코멘트를 사용할 수 있습니다.

- 비 미디어 바이패스(SBC-클라우드 미디어 프로세서): SILK, G.711, G.722, G.729
- 미디어 바이패스(SBC- Teams 클라이언트): SILK, G.711, G.722, G.729

제안에서 원하는 코어를 제외하고 세션 테두리 컨트롤러의 특정 코스를 사용할 수 있습니다.

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Microsoft Teams 클라이언트와 클라우드 미디어 프로세서 간의 레이전
사례 미디어 가속을 중지하지 않음에만 적용합니다. 미디어 바이스를 사용하여 미디어가 Teams 클라이언트와 SBC 사이에서 직접 이동합니다.

클라우드 미디어 프로세서와 Microsoft Teams 클라이언트 간의 이전 단계에서 SILK 또는 G.722가 사용됩니다. 이 레그의 코코어 선택은 여러 매개 변수를 고려할 수 있는 Microsoft 알고리미드를 기반으로 합니다. 


## <a name="supported-session-border-controllers-sbcs"></a>지원되는 세션 테두리 컨트롤러(SBC)

Microsoft는 인증된 SBCs와 직접 라우아웃을 통한 통합된 SBC만 지원합니다. 이는 Enterprise Voice 비즈니스에 중요하므로, Microsoft는 선택한 SBC를 사용하여 크게 테스트를 실행하고 SBC 공급업체와 호환하여 두 시스템이 호환되게 합니다. 

유효성 검사가 수행된 디바이스는 Teams 직접 라우트에 대한 인증된 값으로 나열됩니다. 인증된 장치는 모든 시나리오에서 작동하라고 보장됩니다. 

지원되는 SBC에 대한 자세한 내용은 직접 라우트로 제공된 [세션 테두리 컨트롤러 목록을 참조하세요.](direct-routing-border-controllers.md)

 
## <a name="see-also"></a>참고 항목

[직접 라우팅 구성](direct-routing-configure.md)
