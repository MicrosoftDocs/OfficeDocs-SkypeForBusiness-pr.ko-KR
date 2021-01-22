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
- m365initiative-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Microsoft Phone System 직접 라우팅을 통해 지원되는 고객이 제공한 SBC(세션 테두리 컨트롤러)를 Microsoft Phone System에 연결하는 방법을 배워야 합니다.
ms.openlocfilehash: 77757cf76215dbed0b3ec572b5f1f57120551d86
ms.sourcegitcommit: b12ec4703b164c545d17b02815edd6ee28d40bed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49923830"
---
# <a name="plan-direct-routing"></a>직접 라우팅 계획

> [!Tip]
> 다음 세션에서 직접 라우팅의 이점, 계획 방법 및 배포 방법: Microsoft Teams의 직접 라우팅에 대해 자세히 알아보는 방법을 [시청합니다.](https://aka.ms/teams-direct-routing)

Microsoft Phone System 직접 라우팅을 사용하면 지원되는 고객이 제공한 SBC(세션 테두리 컨트롤러)를 Microsoft Phone System에 연결할 수 있습니다.  예를 들어 이 기능을 사용하면 다음 다이어그램과 같이 Microsoft Teams 클라이언트와의 PSTN(Public Switched Telephone Network) 연결을 구성할 수 있습니다. 

![프레미스 PSTN 연결의 구성을 보여주는 다이어그램](media/PlanDirectRouting1-PSTNwithTeams.png "Microsoft Teams 클라이언트와의 프레미스 PSTN 연결 구성")

  > [!NOTE]
  > 비즈니스용 Skype Online을 사용하면 고객이 제공한 SBC를 페어링할 수도 있지만, SBC와 Microsoft 클라우드 사이에는 비즈니스용 Skype 서버 배포 또는 클라우드 커넥터라는 특수한 비즈니스용 Skype 버전이 필요합니다. 이 시나리오를 하이브리드 음성으로 알려져 있습니다. 반면, 직접 라우팅을 사용하면 지원되는 SBC와 Microsoft 클라우드 간에 직접 연결을 허용합니다.

> [!Important]
> Cloud Connector Edition은 비즈니스용 Skype Online과 함께 2021년 7월 31일 사용이 중지됩니다. 조직이 Teams로 업그레이드한 후 직접 라우팅을 사용하여 팀에온-프레미스 전화 통신 네트워크를 연결하는 [방법을 배워야 합니다.](direct-routing-landing-page.md) 

직접 라우팅을 사용하면 거의 모든 전화 통신 트렁크에 SBC를 연결하거나 타사 PSTN 장비와 상호 연결할 수 있습니다. 직접 라우팅을 사용하면 다음을 할 수 있습니다. 

- Microsoft Phone System에서 거의 모든 PSTN 트렁크를 사용할 수 있습니다. 
- 타사 PBX(개인 분기 교환), 아날로그 디바이스 및 Microsoft Phone System과 같은 고객 소유의 원격 통신 장비 간에 상호 운영성을 구성합니다.

또한 Microsoft는 통화 요금제와 같은 클라우드의 모든 음성 솔루션도 제공합니다. 그러나 다음의 경우 조직에 하이브리드 음성 솔루션이 가장 적합한 것일 수 있습니다. 

- 귀하의 국가에서는 Microsoft 통화 플랜을 사용할 수 없습니다. 
- 조직에서 타사 아날로그 디바이스, 콜 센터에 연결해야 합니다. 
- 조직에는 PSTN 통신 사업자와 기존 계약이 있습니다.

직접 라우팅은 Microsoft 통화 요금제에 대한 추가 라이선스가 있는 사용자도 지원됩니다. 자세한 내용은 전화 시스템 및 통화 [요금제 를 참조하세요.](calling-plan-landing-page.md) 

직접 라우팅을 사용하여 사용자가 예약된 회의에 참가할 때 Microsoft 오디오 회의 서비스에서 전화 접속 번호를 제공하면 적절한 라이선스가 필요합니다.  전화 걸기를 할 때 Microsoft 오디오 회의 서비스는 적절한 라이선스가 필요한 온라인 통화 기능을 사용하여 통화를 합니다. (사용자에게 Microsoft 오디오 회의 라이선스가 없는 경우 직접 라우팅을 통해 호출이 라우팅됩니다.) 자세한 내용은 [Teams를 통해 온라인 모임을 참조하세요.](https://products.office.com/microsoft-teams/online-meeting-solutions) 
 
직접 라우팅 배포 계획은 성공적인 구현의 핵심입니다. 이 문서에서는 인프라 및 라이선스 요구 사항을 설명하고 SBC 연결에 대한 정보를 제공합니다. 

- [인프라 요구 사항](#infrastructure-requirements)
- [라이선스 및 기타 요구 사항](#licensing-and-other-requirements)
- [SBC 도메인 이름](#sbc-domain-names)
- [SBC에 대한 공용 신뢰할 수 있는 인증서](#public-trusted-certificate-for-the-sbc)
- [SIP 신호: FQDNs](#sip-signaling-fqdns)
- [SIP 신호: 포트](#sip-signaling-ports)
- [미디어 트래픽: 포트 범위](#media-traffic-port-ranges)
- [지원되는 SBC(세션 테두리 컨트롤러)](#supported-session-border-controllers-sbcs)

직접 라우팅 구성에 대한 자세한 내용은 직접 라우팅 [구성을 참조하세요.](direct-routing-configure.md)

## <a name="infrastructure-requirements"></a>인프라 요구 사항
직접 라우팅을 배포하기 위해 지원되는 SBC, 도메인 및 기타 네트워크 연결 요구 사항에 대한 인프라 요구 사항은 다음 표에 나와 있습니다.  

|인프라 요구 사항|다음이 필요합니다.|
|:--- |:--- |
|SBC(세션 테두리 컨트롤러)|지원되는 SBC. 자세한 내용은 지원되는 [SBC를 참조하세요.](#supported-session-border-controllers-sbcs)|
|SBC에 연결된 전화 통신 트렁크|SBC에 연결된 하나 이상의 전화 통신 트렁크입니다. 한 엔드에서 SBC는 직접 라우팅을 통해 Microsoft Phone System에 연결합니다. 또한 SBC는 PBX, 아날로그 Telephony 어댑터 등의 타사 전화 통신 엔터티에 연결할 수도 있습니다. SBC에 연결된 모든 PSTN 연결 옵션이 작동됩니다. (SBC에 대한 PSTN 트렁크 구성은 SBC 공급업체 또는 트렁크 공급자를 참조합니다.)|
|Microsoft 365 또는 Office 365 조직|Microsoft Teams 사용자 및 SBC에 대한 구성 및 연결을 가정하는 데 사용하는 Microsoft 365 또는 Office 365 조직입니다.|
|사용자 등록 기관|사용자는 Microsoft 365 또는 Office 365에 있어야 합니다.<br/>회사에 Microsoft 365 또는 Office 365에 하이브리드 연결이 있는 온-프레미스 비즈니스용 Skype 또는 Lync 환경이 있는 경우 온-프레미스에 있는 사용자에 대해 Teams에서 음성을 사용하도록 설정할 수 없습니다.<br/><br/>사용자의 등록 기관을 확인한 후 다음 비즈니스용 Skype Online PowerShell cmdlet을 사용하세요.<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>cmdlet의 출력은 다음을 표시해야 합니다.<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|도메인|Microsoft 365 또는 Office 365 조직에 하나 이상의 도메인이 추가되었습니다.<br/><br/>테넌트에 대해 자동으로 생성되는 \* 기본 도메인인 .onmicrosoft.com 사용할 수 없습니다.<br/><br/>도메인을 확인하려면 다음 비즈니스용 Skype Online PowerShell cmdlet을 사용할 수 있습니다.<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>도메인 및 Microsoft 365 또는 Office 365 조직에 대한 자세한 내용은 [도메인 FAQ를 참조하세요.](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)|
|SBC에 대한 공용 IP 주소|SBC에 연결하는 데 사용할 수 있는 공용 IP 주소입니다. SBC 유형에 따라 SBC는 NAT를 사용할 수 있습니다.|
|SBC에 대한 FQDN(Fully Qualified Domain Name)|SBC용 FQDN입니다. 여기서 FQDN의 도메인 부분은 Microsoft 365 또는 Office 365 조직의 등록된 도메인 중 하나입니다. 자세한 내용은 SBC 도메인 [이름을 참조하세요.](#sbc-domain-names)|
|SBC에 대한 공용 DNS 항목 |SBC FQDN을 공용 IP 주소에 매핑하는 공용 DNS 항목입니다. |
|SBC에 대한 공용 신뢰할 수 있는 인증서 |직접 라우팅과의 모든 통신에 사용할 SBC에 대한 인증서입니다. 자세한 내용은 [SBC에 대한 공용 신뢰할 수 있는 인증서를 참조하세요.](#public-trusted-certificate-for-the-sbc)|
|직접 라우팅에 대한 연결점 |직접 라우팅에 대한 연결점은 다음 세 가지 FQDNS입니다.<br/><br/>`sip.pstnhub.microsoft.com` – 전역 FQDN을 먼저 시도해야 합니다.<br/>`sip2.pstnhub.microsoft.com` – 보조 FQDN은 지리적으로 두 번째 우선 순위 지역에 매핑됩니다.<br/>`sip3.pstnhub.microsoft.com` – 3차 FQDN은 지리적으로 세 번째 우선 순위 지역에 매핑됩니다.<br/><br/>구성 요구 사항에 대한 자세한 내용은 [SIP 신호: FQDNs를 참조하세요.](#sip-signaling-fqdns)|
|직접 라우팅 미디어에 대한 방화벽 IP 주소 및 포트 |SBC는 클라우드에서 다음 서비스와 통신합니다.<br/><br/>신호를 처리하는 SIP 프록시<br/>미디어 우회가 있는 경우를 제외하고 미디어를 처리하는 미디어 프로세서<br/><br/>이 두 서비스에는 Microsoft Cloud에 별도의 IP 주소가 있습니다. 이 문서의 측에서 설명하고 있습니다.<br/><br/>자세한 내용은 URL 및 IP 주소 범위의 [Microsoft Teams](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) [섹션을 참조하세요.](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) |
|미디어 전송 프로필|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Microsoft Teams 미디어에 대한 방화벽 IP 주소 및 포트 |자세한 내용은 URL 및 IP 주소 [범위를 참조하세요.](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) |
|||

## <a name="licensing-and-other-requirements"></a>라이선스 및 기타 요구 사항 

직접 라우팅 사용자는 Microsoft 365 또는 Office 365에 할당된 다음 라이선스가 있어야 합니다. 

- Microsoft Phone System. 
- 라이선스에 포함된 경우 Microsoft Teams + 비즈니스용 Skype 계획 2.
- Microsoft 오디오 회의(라이선스가 필요한 경우의 특정 예제는 아래 참고 사항 및 단락을 읽어 보세요.)

> [!NOTE]
> 비즈니스용 Skype 요금제는 포함된 라이선스 계약에서 제거되지 말아야 합니다. 


> [!IMPORTANT]
>  외부 참가자에게 전화를 걸거나 전화 접속 번호를 제공하여 예약된 모임에 외부 참가자를 추가하려면 오디오 회의 라이선스가 필요합니다.


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>전화 에스컬링 및 오디오 회의 라이선스

Teams 사용자는 일대일 Teams에서 PSTN으로 시작하거나 Teams에서 Teams로 통화를 시작하고 PSTN 참가자를 추가할 수 있습니다. 이 시나리오를 애드워크 회의라고 합니다. 호출이 걸리는 경로는 통화를 에스컬링하는 사용자에게 Microsoft 오디오 회의 라이선스가 할당되어 있는지 여부에 따라 결정됩니다.

- 통화를 에스컬링하는 Teams 사용자에게 Microsoft 오디오 회의 라이선스가 할당된 경우 에스컬링은 Microsoft 오디오 회의 서비스를 통해 발생합니다. 기존 통화에 초대된 원격 PSTN 참가자는 수신 전화에 대한 알림을 받고 에스컬레이터를 시작한 Teams 사용자에게 할당된 Microsoft 브리지 수를 볼 수 있습니다.
- 통화를 에스컬링하는 Teams 사용자에게 Microsoft 오디오 회의 라이선스가 할당되지 않은 경우 에스컬링은 직접 라우팅 인터페이스에 연결된 세션 테두리 컨트롤러를 통해 발생합니다. 통화에 초대된 원격 PSTN 참가자는 수신 전화에 대한 알림을 받고 에스컬레이터를 시작한 Teams 사용자의 수를 볼 수 있습니다. 에스컬링에 사용되는 특정 SBC는 사용자의 라우팅 정책에 의해 정의됩니다. 


또한 다음을 보장해야 합니다.
 
- CsOnlineVoiceRoutingPolicy가 사용자에게 할당됩니다. 
- 개인 통화 허용은 Microsoft Teams의 테넌트 수준에서 활성화됩니다. 

직접 라우팅은 Microsoft 통화 요금제에 대한 라이선스가 있는 사용자도 지원됩니다. 통화 계획이 있는 Microsoft Phone System은 직접 라우팅 인터페이스를 사용하여 일부 호출을 라우팅할 수 있습니다. 그러나 사용자의 전화 번호는 온라인으로 획득하거나 Microsoft로 이식해야 합니다.  

동일한 사용자에 대한 통화 계획 및 직접 라우팅 연결 혼합은 선택 사항이지만 유용할 수 있습니다(예: 사용자에게 Microsoft 통화 요금제가 할당되어 있지만 SBC를 사용하여 일부 호출을 라우팅하려는 경우). 가장 일반적인 시나리오 중 하나는 타사 PBX에 대한 호출입니다.  타사 PBX를 사용하는 경우, 타사 PBX에 연결된 전화 통화를 제외한 모든 통화는 Microsoft 통화 요금제로 라우팅되지만 타사 PBX에 연결된 전화 통화는 SBC로 이동하므로 PSTN이 아닌 엔터프라이즈 네트워크 내에 있습니다. 

전화 시스템 라이선스에 대한 자세한 내용은 Office 및 [](https://technet.microsoft.com/library/office-365-plan-options.aspx)요금제 [옵션에서](https://products.office.com/compare-all-microsoft-office-products?tab=2) 가장 많이 사용하세요. 

전화 시스템 라이선스에 대한 자세한 내용은 Microsoft Teams 추가 [기능 라이선스를 참조하세요.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) 

## <a name="supported-end-points"></a>지원되는 끝점 

끝점으로 사용할 수 있습니다.

- 모든 Teams 클라이언트. 
- 공용 영역 전화기. Microsoft Teams에 대한 공용 영역 전화 [라이선스 설정을 참조합니다.](https://docs.microsoft.com/microsoftteams/set-up-common-area-phones) 직접 라우팅을 사용하여 공용 영역 전화 설정을 할 때 통화 요금제 라이선스가 필요하지 않습니다.
- 비즈니스용 Skype 3PIP 휴대폰. Microsoft Teams를 통해 [비즈니스용 Skype 3PIP(전화기) 지원 참조](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)


## <a name="sbc-domain-names"></a>SBC 도메인 이름

SBC 도메인 이름은 테넌트의 도메인에 등록된 이름 중 하나에서 시작해야 합니다. \*SBC의 FQDN onmicrosoft.com .onmicrosoft.com 테넌트는 사용할 수 없습니다.

다음 표에서는 테넌트에 등록된 DNS 이름의 예, SBC에 대한 FQDN으로 사용할 수 있는지 여부 및 유효한 FQDN 이름의 예제를 보여줍니다.

|DNS 이름|SBC FQDN에 사용할 수 있습니다.|FQDN 이름의 예|
|:--- |:--- |:--- |
contoso.com|예|**유효한 이름:**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|아니요|*.onmicrosoft.com 도메인은 SBC 이름에 지원되지 않습니다.

새 도메인 이름을 사용하려는 경우를 가정합니다. 예를 들어 테넌트에 contoso.com 도메인 이름으로 등록되어 있으며 테넌트에 도메인 이름을 sbc1.sip.contoso.com. SBC를 이름과 페어링하려면 sbc1.sip.contoso.com 도메인 이름을 테넌트의 도메인에 sip.contoso.com 등록해야 합니다. 도메인 이름을 등록하기 sbc1.sip.contoso.com SBC와 페어링을 시도하면 "이 테넌트에 대해 구성되지 않은 "sbc1.sip.contoso.com" 도메인을 사용할 수 없습니다."라는 오류가 표시됩니다.
도메인 이름을 추가한 후에 UPN 계정으로 사용자를 만들고 Teams 라이선스를 user@sip.contoso.com 합니다. 도메인 이름이 테넌트의 도메인에 추가된 후 도메인 이름을 완전히 프로비전하고, 새 이름이 있는 사용자가 만들어지며, 라이선스가 사용자에게 할당된 후 최대 24시간이 걸릴 수 있습니다. 

회사에 하나의 테넌트에 여러 개의 SIP 주소 공간이 있을 수 있습니다. 예를 들어 회사에서 SIP 주소 contoso.com 두 번째 SIP 주소 공간으로 fabrikam.com 수 있습니다. 일부 사용자는 주소 user@contoso.com 일부 사용자는 주소가 user@fabrikam.com. 

SBC에는 하나의 FQDN만 필요하며 페어링된 테넌트의 주소 공간에서 사용자를 서비스할 수 있습니다. 예를 들어 이름이 sbc1.contoso.com SBC는 동일한 테넌트에 등록된 경우 주소가 user@contoso.com user@fabrikam.com 사용자에 대한 PSTN 트래픽을 수신하고 보낼 수 있습니다.  

## <a name="public-trusted-certificate-for-the-sbc"></a>SBC에 대한 공용 신뢰할 수 있는 인증서

CSR(인증 서명 요청)을 생성하여 SBC에 대한 인증서를 요청하는 것이 좋습니다. SBC에 대한 CSR 생성에 대한 특정 지침은 SBC 공급업체에서 제공하는 상호 연결 지침 또는 설명서를 참조하세요. 

  > [!NOTE]
  > 대부분의 CAS(인증 기관)는 개인 키 크기를 2048 이상으로 요구합니다. CSR을 생성하는 경우 이 사실에 유의해야 합니다.

인증서에는 일반 이름(CN) 또는 SAN(주체 대체 이름) 필드로 SBC FQDN이 필요합니다. 인증서는 중간 공급자가 아닌 인증 기관에서 직접 발급해야 합니다.

또는 직접 라우팅은 CN 및/또는 SAN에서 와일드카드를 지원하며 와일드카드는 TLS를 통해 표준 [RFC HTTP를 준수해야 합니다.](https://tools.ietf.org/html/rfc2818#section-3.1) 예를 들어 \* SBC FQDN contoso.com SBC FQDN과 일치하지만 sbc.contoso.com .sbc.test.contoso.com.

인증서는 다음 루트 인증 기관 중 하나에서 생성해야 합니다.

- AffirmTrust
- AddTrust 외부 CA 루트
- Baltimore CyberTrust Root*
- Buypass
- 사이버 트러스트
- Class 3 Public Primary Certification Authority
- Comodo Secure Root CA
- Deutsche Telekom 
- DigiCert Global Root CA
- DigiCert High Assurance EV Root CA
- Entrust
- GlobalSign
- Go Daddy
- GeoTrust
- Verisign, Inc. 
- SSL.com
- 스타필드
- Microsoft용 Symantec Enterprise Mobile Root 
- SwissSign
- Thawte Timestamping CA
- Trustwave
- TeliaSonera 
- T-Systems International GmbH(Deutsche Telekom)
- QuoVadis

Office 365 GCCH 및 DoD 환경에서 직접 라우팅의 경우 다음 루트 인증 기관 중 하나에서 인증서를 생성해야 합니다.
- DigiCert Global Root CA
- DigiCert High Assurance EV Root CA

> [!NOTE]
> *SBC에서 Teams 연결에 MTLS(상호 TLS) 지원을 사용하도록 설정한 경우 Teams TLS 컨텍스트의 SBC 신뢰할 수 있는 루트 저장소에 Baltimore CyberTrust 루트 인증서를 설치해야 합니다. (Microsoft 서비스 인증서가 Baltimore 루트 인증서를 사용하기 때문에입니다.) Baltimore 루트 인증서를 다운로드하려면 [Office 365 암호화 체인을 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/encryption-office-365-certificate-chains)

Microsoft는 고객 요청에 따라 인증 기관을 추가하기 위해 작업 중입니다. 

## <a name="sip-signaling-fqdns"></a>SIP 신호: FQDNs 

직접 라우팅은 다음 환경에서 제공됩니다.
- Microsoft 365 또는 Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

GCC, GCC High 및 DoD와 같은 [Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) 및 미국 정부 환경에 대해 자세히 알아보십시오.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365, Office 365 및 Office 365 GCC 환경

직접 라우팅에 대한 연결점은 다음 세 가지 FQDNS입니다.

- **sip.pstnhub.microsoft.com** - 전역 FQDN을 먼저 시도해야 합니다. SBC에서 이 이름을 확인하기 위한 요청을 보내면 Microsoft Azure DNS 서버는 SBC에 할당된 기본 Azure 데이터 센터를 알려주는 IP 주소를 반환합니다. 할당은 데이터 센터의 성능 메트릭 및 SBC에 대한 지리적 근접성을 기반으로 합니다. 반환된 IP 주소는 기본 FQDN에 해당합니다.
- **sip2.pstnhub.microsoft.com** - 보조 FQDN – 지리적으로 두 번째 우선 순위 지역에 매핑됩니다.
- **sip3.pstnhub.microsoft.com** - 3차 FQDN – 지리적으로 세 번째 우선 순위 지역에 매핑됩니다.

다음 세 가지 FQDNS를 순서대로 배치해야 합니다.

- 최적의 환경을 제공합니다(로드가 적고 첫 번째 FQDN을 쿼리하여 할당된 SBC 데이터 센터에 가장 가깝습니다).
- SBC에서 일시적인 문제가 발생하는 데이터 센터에 연결될 때 장애 조치(failover)를 제공합니다. 자세한 내용은 아래 [장애 조치 메커니즘을 참조하세요.](#failover-mechanism-for-sip-signaling)  

FQDNs(sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com 및 sip3.pstnhub.microsoft.com)는 다음 IP 주소 중 하나에 확인됩니다.

- 52.114.148.0
- 52.114.132.46 
- 52.114.75.24 
- 52.114.76.76 
- 52.114.7.24 
- 52.114.14.70
- 52.114.16.74
- 52.114.20.29

신호 전송을 위해 주소에서 수신 및 전송되는 트래픽을 허용하려면 방화벽에서 이러한 모든 IP 주소에 대한 포트를 열 필요가 있습니다.  방화벽이 DNS 이름을 지원하는 경우 FQDN  sip-all.pstnhub.microsoft.com 모든 IP 주소로 확인됩니다. 

> [!IMPORTANT]
>  Teams 직접 라우팅 확장 및 서비스 개선의 일환으로 오스트레일리아에 직접 라우팅 인프라의 새 인스턴스를 배포했습니다. 이는 오스트레일리아 고객의 경우 다음 FQDN(sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com 및 sip3.pstnhub.microsoft.com)에 두 개의 추가 IP 주소(52.114.16.74 및 52.114.20.29)에 반영됩니다. 이러한 두 IP 주소(52.114.16.74 및 52.114.20.29)를 IP ACL(액세스 제어 목록)에 추가하고 방화벽에서 이러한 모든 IP 주소에 대한 포트를 열어 신호 전달을 위해 주소에서 들어오는 트래픽과 발신 트래픽을 허용해야 합니다.

### <a name="office-365-gcch-and-dod-environment"></a>Office 365 GCCH 및 DoD 환경

직접 라우팅에 대한 연결점은 다음과 같은 FQDN입니다.

**sip.pstnhub.dod.teams.microsoft.us** - 글로벌 FQDN입니다. Office 365 DoD 환경은 미국 데이터 센터에만 존재하기에 보조 및 3차 FQDNS는 없습니다.

FQDN sip.pstnhub.dod.teams.microsoft.us 다음 IP 주소 중 하나로 확인됩니다.

- 52.127.64.33
- 52.127.68.34

신호 전송을 위해 주소에서 수신 및 전송되는 트래픽을 허용하려면 방화벽에서 이러한 모든 IP 주소에 대한 포트를 열 필요가 있습니다.

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High 환경

직접 라우팅에 대한 연결점은 다음과 같은 FQDN입니다.

**sip.pstnhub.gov.teams.microsoft.us** - 글로벌 FQDN입니다. GCC High 환경은 미국 데이터 센터에만 존재하기에 보조 및 3차 FQDNS가 없습니다.

FQDN sip.pstnhub.gov.teams.microsoft.us 다음 IP 주소 중 하나로 확인됩니다.

- 52.127.88.59
- 52.127.92.64

신호 전송을 위해 주소에서 수신 및 전송되는 트래픽을 허용하려면 방화벽에서 이러한 모든 IP 주소에 대한 포트를 열 필요가 있습니다. 방화벽이 DNS 이름을 지원하는 경우 FQDN  sip-all.pstnhub.gov.teams.microsoft.us 모든 IP 주소로 확인됩니다. 이 FQDN은 인바운드 호출 분류를 위해 페더화 FQDN으로 사용할 수도 있습니다.

## <a name="sip-signaling-ports"></a>SIP 신호: 포트

직접 라우팅이 제공되는 Microsoft 365 또는 Office 365 환경에 다음 포트를 사용해야 합니다.
- Microsoft 365 또는 Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

|트래픽|보낸 사람|받는 사람|원본 포트|대상 포트|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP 프록시|SBC|1024 – 65535|SBC에 정의되어 있습니다(Office 365 GCC High/DoD의 경우 포트 5061만 사용)|
SIP/TLS|SBC|SIP 프록시|SBC에 정의|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>SIP 신호에 대한 장애 조치 메커니즘

SBC는 DNS 쿼리를 수행하여 sip.pstnhub.microsoft.com. SBC 위치 및 데이터 센터 성능 메트릭에 따라 기본 데이터 센터가 선택됩니다. 기본 데이터 센터에 문제가 있는 경우 SBC는 두 번째 sip2.pstnhub.microsoft.com 데이터 센터로 확인되는 데이터 센터를 시도하고, 드물게 두 지역의 데이터 센터를 사용할 수 없는 경우 SBC는 3차 데이터 센터 IP를 제공하는 마지막 FQDN(sip3.pstnhub.microsoft.com)을 다시 시도합니다.

아래 표에는 기본, 보조 및 3차 데이터 센터 간의 관계가 요약됩니다.

|기본 데이터 센터가|EMEA|NOAM|아시아|
|:--- |:--- |:--- |:--- |
|보조 데이터 센터(sip2.pstnhub.microsoft.com)|미국|EU|미국|
|3차 데이터 센터(sip3.pstnhub.microsoft.com)|아시아|아시아|EU|
|||||

## <a name="media-traffic-port-ranges"></a>미디어 트래픽: 포트 범위
미디어 우회 없이 직접 라우팅을 배포하려는 경우 아래 요구 사항이 적용됩니다. 미디어 우회에 대한 방화벽 요구 사항은 직접 라우팅을 통해 미디어 [우회에 대한 계획을 참조하세요.](https://docs.microsoft.com/microsoftteams/direct-routing-plan-media-bypass)



미디어 트래픽은 Microsoft 클라우드의 별도 서비스에서 흐르고 있습니다. 미디어 트래픽의 IP 주소 범위는 다음과 같습니다.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365, Office 365 및 Office 365 GCC 환경

- 52.112.0.0/14(52.112.0.1에서 52.115.255.254까지의 IP 주소).
- 52.120.0.0/14(52.120.0.1에서 52.123.255.254까지의 IP 주소).

### <a name="office-365-dod-environment"></a>Office 365 DoD 환경

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High 환경

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>포트 범위(모든 환경에 적용 가능)
미디어 프로세서의 포트 범위는 다음 표에 나와 있습니다. 

|트래픽|보낸 사람|받는 사람|원본 포트|대상 포트|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|미디어 프로세서|SBC|3478-3481 및 49152 – 53247|SBC에 정의|
|UDP/SRTP|SBC|미디어 프로세서|SBC에 정의|3478-3481 및 49152 – 53247|

  > [!NOTE]
  > Microsoft는 SBC에서 동시 호출당 두 개 이상의 포트를 권장합니다.


## <a name="media-traffic-media-processors-geography"></a>미디어 트래픽: 미디어 프로세서 지리

미디어 트래픽은 미디어 프로세서라는 구성 요소를 통해 흐르게 됩니다. 미디어 프로세서는 SIP proxies와 동일한 데이터 센터에 배치됩니다. 또한 미디어 흐름을 최적화하기 위한 추가 미디어 프로세서가 있습니다. 예를 들어 현재 오스트레일리아에 SIP 프록시 구성 요소가 없지만(싱가포르 또는 홍콩을 통한 SIP 흐름) 오스트레일리아에 로컬로 미디어 프로세서가 있습니다. 미디어 프로세서에 대한 로컬의 필요성은 오스트레일리아에서 싱가포르 또는 홍콩으로 장거리 트래픽을 전송하여 경험하는 대기 시간에 따라 다를 수 있습니다. 오스트레일리아에서 홍콩 또는 싱가포르로 흐르는 트래픽의 예에서 대기 시간은 SIP 트래픽에 대한 양호한 통화 품질을 보존하는 것이 허용되는 반면, 실시간 미디어 트래픽의 경우 대기 시간은 허용되지 않습니다.

미디어 프로세서의 위치:

SIP 프록시 및 미디어 프로세서 구성 요소가 배포된 위치:
- 미국(미국 서부 및 미국 동부 데이터 센터의 2개)
- 유럽(암스테르담 및 더블린 데이터 센터)
- 아시아(싱가포르 및 홍콩 데이터 센터)

미디어 프로세서만 배포되는 위치(위에 나열된 가장 가까운 데이터 센터를 통한 SIP 흐름):
- 일본(JP 동부 및 서부 데이터 센터)
- 오스트레일리아(오스트레일리아 동부 및 동남 데이터 센터)




## <a name="media-traffic-codecs"></a>미디어 트래픽: 코덱

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>SBC와 클라우드 미디어 프로세서 또는 Microsoft Teams 클라이언트 간의 레그입니다.
미디어 우회 사례와 비 우회 사례 모두에 적용됩니다.

세션 테두리 컨트롤러와 클라우드 미디어 프로세서(미디어 우회 없이) 또는 Teams 클라이언트와 SBC(미디어 우회가 활성화된 경우) 간의 레그에 있는 직접 라우팅 인터페이스는 다음 코덱을 사용할 수 있습니다.

- 비-미디어 우회(SBC-클라우드 미디어 프로세서): SILK, G.711, G.722, G.729
- 미디어 우회(SBC-Teams 클라이언트): SILK, G.711, G.722, G.729

제안에서 바람직하지 않은 코덱을 제외하여 세션 테두리 컨트롤러에서 특정 코덱을 강제로 사용할 수 있습니다.

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Microsoft Teams 클라이언트와 클라우드 미디어 프로세서 간 레그
미디어가 아닌 우회 사례에만 적용됩니다. 미디어 우회를 통해 미디어는 Teams 클라이언트와 SBC 간에 직접 흐르게 됩니다.

클라우드 미디어 프로세서와 Microsoft Teams 클라이언트 사이에 SILK 또는 G.722가 사용됩니다. 이 레그의 코덱 선택은 여러 매개 변수를 고려하는 Microsoft 알고리즘을 기반으로 합니다. 


## <a name="supported-session-border-controllers-sbcs"></a>지원되는 SBC(세션 테두리 컨트롤러)

Microsoft는 직접 라우팅과 쌍을 이루는 인증된 SBC만 지원됩니다. 비즈니스 Enterprise Voice 중요하기 때문에 Microsoft는 선택한 SBC를 통해 집약적인 테스트를 실행하고 SBC 공급업체와 협력하여 두 시스템이 호환되는지를 보장합니다. 

유효성이 검사된 디바이스는 Teams 직접 라우팅을 위한 인증된 장치로 나열됩니다. 인증된 디바이스는 모든 시나리오에서 작동할 수 있습니다. 

지원되는 SBC에 대한 자세한 내용은 직접 라우팅에 대해 인증된 세션 테두리 컨트롤러 목록을 [참조하세요.](direct-routing-border-controllers.md)

 
## <a name="see-also"></a>참고 항목

[직접 라우팅 구성](direct-routing-configure.md)
