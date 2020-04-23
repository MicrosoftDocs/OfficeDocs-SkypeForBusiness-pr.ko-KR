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
description: Microsoft 전화 시스템 다이렉트 라우팅이 지원 되는 고객 제공 세션 경계 컨트롤러 (SBC)를 Microsoft 전화 시스템에 연결할 수 있는 방법을 알아보세요.
ms.openlocfilehash: 7d5a69ff3b0533d17d6582489fad6e156d8df1c7
ms.sourcegitcommit: 6fbaab29076e16fe18f8faeb7e012a0815c2369d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43785941"
---
# <a name="plan-direct-routing"></a>직접 라우팅 계획

> [!Tip]
> 직접적인 라우팅, 계획 방법 및 배포 방법에 대 한 자세한 내용은 다음 세션을 시청 하세요. [Microsoft 팀의 직접 라우팅](https://aka.ms/teams-direct-routing)

Microsoft 전화 시스템 다이렉트 라우팅이 지원 되는 고객 제공 세션 경계 컨트롤러 (SBC)를 Microsoft 전화 시스템에 연결할 수 있습니다.  예를 들어이 접근 권한 값을 사용 하면 다음 다이어그램에 표시 된 것 처럼 Microsoft 팀 클라이언트를 통해 온-프레미스 공개 통신 네트워크 (PSTN) 연결을 구성할 수 있습니다. 

![온-프레미스 PSTN 연결 구성을 보여주는 다이어그램](media/PlanDirectRouting1-PSTNwithTeams.png "Microsoft 팀 클라이언트를 사용 하 여 온-프레미스 PSTN 연결 구성")

  > [!NOTE]
  > 비즈니스용 skype Online을 통해 고객 제공 SBC를 쌍으로 할 수 있지만,이를 위해서는 온-프레미스 비즈니스용 Skype Server 배포 또는 SBC와 Microsoft 클라우드 간에 클라우드 커넥터 라는 특별 한 버전의 비즈니스용 Skype가 필요 합니다. 이 시나리오를 하이브리드 음성 이라고 합니다. 반대로 직접 라우팅은 지원 되는 SBC 및 Microsoft 클라우드 간 직접 연결을 허용 합니다. 

직접 라우팅 기능을 사용 하 여 SBC를 타사 PSTN 장비와 거의 모든 통신 트렁크 또는 interconnect에 연결할 수 있습니다. 직접 라우팅으로 다음을 수행할 수 있습니다. 

- Microsoft 전화 시스템을 사용 하 여 거의 모든 PSTN 트렁크를 사용 합니다. 
- 타사 PBX (사설 branch exchange), 아날로그 장치, Microsoft 전화 시스템 등의 고객 소유 전화 통신 장비 간 상호 운용성을 구성 합니다.

Microsoft는 또한 통화 계획과 같은 모든 클라우드 음성 솔루션을 제공 합니다. 그러나 하이브리드 음성 솔루션은 조직에 가장 적합 한 경우 다음과 같은 작업을 할 수 있습니다. 

- Microsoft 통화 요금제는 귀하의 국가에서 사용할 수 없습니다. 
- 조직에는 타사 아날로그 장치, 통화 센터 등에 대 한 연결이 필요 합니다. 
- 조직에 PSTN 통신 업체와의 기존 계약이 있습니다.

또한 직접 라우팅은 Microsoft 통화 요금제에 대 한 추가 라이선스를 보유 한 사용자를 지원 합니다. 자세한 내용은 [전화 시스템 및 통화 계획](calling-plan-landing-page.md)을 참조 하세요. 

직접 라우팅에서 사용자가 예약 된 회의에 참가할 때 전화 접속 번호는 적절 한 라이선스가 필요한 Microsoft 오디오 회의 서비스에서 제공 합니다.  전화를 걸 때 Microsoft 오디오 회의 서비스는 올바른 라이선스를 필요로 하는 온라인 통화 기능을 사용 하 여 전화를 보냅니다. (전화 걸기는 직접 라우팅을 통해 라우팅되지 않습니다.) 자세한 내용은 [팀과 온라인 모임](https://products.office.com/microsoft-teams/online-meeting-solutions)을 참조 하세요. 
 
성공적인 구현에 대 한 직접 라우팅 배포 계획을 수립 하는 것이 중요 합니다. 이 문서에서는 인프라 및 라이선스 요구 사항에 대해 설명 하 고 SBC 연결에 대 한 정보를 제공 합니다. 

- [인프라 요구 사항](#infrastructure-requirements)
- [라이선스 및 기타 요구 사항](#licensing-and-other-requirements)
- [SBC 도메인 이름](#sbc-domain-names)
- [SBC에 대해 신뢰할 수 있는 공용 인증서](#public-trusted-certificate-for-the-sbc)
- [SIP 신호: Fqdn](#sip-signaling-fqdns)
- [SIP 신호: 포트](#sip-signaling-ports)
- [미디어 트래픽: 포트 범위](#media-traffic-port-ranges)
- [지원 되는 SBCs (세션 경계 컨트롤러)](#supported-session-border-controllers-sbcs)

직접 라우팅 구성에 대 한 자세한 내용은 [직접 라우팅 구성을](direct-routing-configure.md)참조 하세요.

## <a name="infrastructure-requirements"></a>인프라 요구 사항
직접 라우팅을 배포 하기 위해 지원 되는 SBCs, 도메인 및 기타 네트워크 연결 요구 사항에 대 한 인프라 요구 사항이 다음 표에 나열 되어 있습니다.  

|**인프라 요구 사항**|**다음이 필요 합니다.**|
|:--- |:--- |
|SBC (세션 경계 컨트롤러)|지원 되는 SBC입니다. 자세한 내용은 [지원 되는 SBCs](#supported-session-border-controllers-sbcs)를 참조 하세요.|
|SBC에 연결 된 전화 통신 trunks|SBC에 연결 된 하나 이상의 전화 접속 trunks. 한 쪽 끝에서 SBC는 직접 라우팅을 통해 Microsoft 전화 시스템에 연결 됩니다. 또한 SBC는 Pbx, 아날로그 전화 통신 어댑터 등과 같은 타사 전화 통신 엔티티와 연결 될 수 있습니다. SBC에 연결 된 모든 PSTN 연결 옵션은 작동 합니다. SBC에 대 한 PSTN trunks 구성의 경우 SBC 공급 업체 또는 트렁크 공급자에 게 문의 하세요.|
|Office 365 조직|Microsoft 팀 사용자를 홈으로 설정 하 고 SBC에 대 한 구성 및 연결을 하는 데 사용 하는 Office 365 조직입니다.|
|사용자 등록자|사용자는 Office 365에서 가져와야 합니다.<br/>회사에서 Office 365에 하이브리드 연결을 사용 하는 온-프레미스 비즈니스용 Skype 또는 Lync 환경을 보유 하 고 있는 경우 온-프레미스 사용자의 팀에서 음성을 사용할 수 없습니다.<br/><br/>사용자의 등록자를 확인 하려면 다음 비즈니스용 Skype Online PowerShell cmdlet을 사용 합니다.<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>Cmdlet의 출력은 다음과 같이 표시 되어야 합니다.<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|도메인용|하나 이상의 도메인이 Office 365 조직에 추가 되었습니다.<br/><br/>테 넌 트에 대해 자동으로 만들어지는 기본 \*도메인 onmicrosoft.com는 사용할 수 없습니다.<br/><br/>다음 비즈니스용 Skype Online PowerShell cmdlet을 사용 하 여 도메인을 볼 수 있습니다.<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>도메인 및 Office 365 조직에 대 한 자세한 내용은 [도메인 FAQ](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)를 참조 하세요.|
|SBC의 공용 IP 주소|SBC에 연결 하는 데 사용할 수 있는 공용 IP 주소입니다. Sbc의 유형에 따라 SBC에서 NAT를 사용할 수 있습니다.|
|SBC에 대 한 FQDN (정규화 된 도메인 이름)|SBC에 대 한 FQDN으로, 여기서 FQDN의 도메인 부분은 Office 365 조직의 등록 된 도메인 중 하나입니다. 자세한 내용은 [SBC 도메인 이름을](#sbc-domain-names)참조 하세요.|
|SBC에 대 한 공용 DNS 항목 |공용 DNS 항목이 SBC FQDN을 공용 IP 주소에 매핑하는 것입니다. |
|SBC에 대해 신뢰할 수 있는 공용 인증서 |직접 라우팅과 관련 된 모든 통신에 사용할 SBC에 대 한 인증서입니다. 자세한 내용은 [SBC에 대해 신뢰할 수 있는 공개 인증서](#public-trusted-certificate-for-the-sbc)를 참조 하세요.|
|직접 라우팅 연결 지점 |직접 라우팅의 연결 지점은 다음 세 가지 Fqdn입니다.<br/><br/>`sip.pstnhub.microsoft.com`-전역 FQDN을 먼저 시도해 야 합니다.<br/>`sip2.pstnhub.microsoft.com`-보조 FQDN, 지리적으로 두 번째 우선 순위 영역에 매핑됩니다.<br/>`sip3.pstnhub.microsoft.com`– 3 차 FQDN, 지리적으로 세 번째 우선 순위 영역에 매핑됩니다.<br/><br/>구성 요구 사항에 대 한 자세한 내용은 [SIP 신호: fqdn](#sip-signaling-fqdns)을 참조 하세요.|
|다이렉트 라우팅 미디어에 대 한 방화벽 IP 주소 및 포트 |SBC는 클라우드의 다음 서비스와 통신 합니다.<br/><br/>신호를 처리 하는 SIP 프록시<br/>미디어를 처리 하는 미디어 프로세서-매체 바이패스를 사용 하는 경우를 제외 하 고<br/><br/>이 두 서비스에는 Microsoft 클라우드에서이 문서의 뒷부분에 설명 된 별도의 IP 주소가 있습니다.<br/><br/>자세한 내용은 [Office 365 url 및 IP 주소 범위](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)에서 [Microsoft 팀 섹션](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) 을 참조 하세요. |
|미디어 전송 프로필|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Microsoft 팀 미디어에 대 한 방화벽 IP 주소 및 포트 |자세한 내용은 [Office 365 url 및 IP 주소 범위](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)를 참조 하세요. |
|||

## <a name="licensing-and-other-requirements"></a>라이선스 및 기타 요구 사항 

직접 라우팅 사용자에 게는 Office 365에 할당 된 다음 라이선스가 있어야 합니다. 

- Microsoft 전화 시스템. 
- Microsoft 팀 + 비즈니스용 Skype 요금제 2 (라이선스에 포함 된 경우)
- Microsoft 오디오 회의 (노트 및 아래 단락에서 라이선스가 필요한 경우에 대 한 구체적인 예)를 참조 하세요.

> [!NOTE]
> 비즈니스용 Skype 요금제가 포함 된 경우 라이선스 계약에서 제거할 수 없습니다. 


> [!IMPORTANT]
>  외부 참가자를 전화를 걸고 전화 접속 번호를 제공 하 여 예약 된 모임에 추가 하려는 경우에는 오디오 회의 라이선스가 필요 합니다.


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>임시 통화 에스컬레이션 및 오디오 회의 라이선스

팀 사용자는 PSTN 또는 팀에 게 일대일 팀을 시작 하 고 PSTN 참가자를 팀에 추가할 수 있습니다. 이 시나리오를 임시 회의 라고 합니다. 통화를 안내 하는 사용자에 게 Microsoft 오디오 회의 라이선스가 지정 되었는지 여부에 따라 호출이 실행 되는 경로가 달라 집니다.

- 전화를 거는 팀 사용자가 Microsoft 오디오 회의 라이선스를 할당 한 경우에는 Microsoft 오디오 회의 서비스를 통해 에스컬레이션이 수행 됩니다. 기존 통화에 초대 된 원격 PSTN 참가자는 수신 전화에 대 한 알림을 받으며 에스컬레이션을 시작한 팀 사용자에 게 할당 된 Microsoft bridge의 번호를 표시 합니다.
- 통화를 담당 하는 팀 사용자에 게 Microsoft 오디오 회의 라이선스가 할당 되어 있지 않으면 직접 라우팅 인터페이스에 연결 된 세션 경계 컨트롤러를 통해 에스컬레이션이 발생 합니다. 통화에 초대 된 원격 PSTN 참가자는 수신 전화에 대 한 알림을 받으며 에스컬레이션을 시작한 팀 사용자의 번호를 표시 합니다. 에스컬레이션에 사용 되는 특정 SBC는 사용자의 라우팅 정책에 의해 정의 됩니다. 


또한 다음을 확인 해야 합니다.
 
- CsOnlineVoiceRoutingPolicy 사용자에 게 할당 됩니다. 
- Microsoft 팀의 테 넌 트 수준에서 비공개 통화 허용이 활성화 되어 있습니다. 

또한 직접 라우팅은 Microsoft 통화 요금제에 대 한 라이선스를 가진 사용자를 지원 합니다. 통화 요금제가 포함 된 Microsoft 전화 시스템은 직접 라우팅 인터페이스를 사용 하 여 일부 통화를 라우팅할 수 있습니다. 그러나 사용자의 전화 번호는 온라인으로 구입 하거나 Microsoft로 이식할 수 있어야 합니다.  

동일한 사용자에 대 한 통화 계획과 직접 라우팅 연결을 혼합 하는 기능은 선택 사항 이지만, 사용자에 게 Microsoft 호출 계획을 할당 했지만 SBC를 사용 하 여 일부 통화를 라우팅해야 하는 경우와 같이 유용할 수 있습니다. 가장 일반적인 시나리오 중 하나는 타사 Pbx에 대 한 통화입니다.  타사 Pbx를 사용 하는 경우 해당 Pbx에 연결 된 전화에 대 한 호출을 제외한 모든 통화는 Microsoft 통화 계획을 사용 하 여 라우팅되며, 타사 Pbx에 연결 된 전화기로의 통화는 SBC로 이동 하므로 PSTN이 아닌 엔터프라이즈 네트워크 내에서 유지 됩니다. 

전화 시스템 라이선스에 대 한 자세한 내용은 office 365 및 [office 365 계획 옵션](https://technet.microsoft.com/library/office-365-plan-options.aspx)을 [사용 하 여 Office에서 최대한 활용](https://products.office.com/compare-all-microsoft-office-products?tab=2) 을 참조 하세요. 

전화 시스템 라이선스에 대 한 자세한 내용은 [Microsoft 팀 추가 기능 라이선스](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)를 참조 하세요. 

## <a name="supported-end-points"></a>지원 되는 끝점 

끝 점으로 사용할 수 있습니다.

- 모든 팀 클라이언트. 
- 일반적인 지역 전화. [Microsoft 팀을 위한 일반적인 지역 전화 라이선스 설정을](https://docs.microsoft.com/microsoftteams/set-up-common-area-phones)참조 하세요. 참고 다이렉트 라우팅이 있는 공통 지역 전화를 설정할 때에는 통화 요금제 라이선스가 필요 하지 않습니다.
- 비즈니스용 Skype 3PIP 전화. [Microsoft 팀에서 비즈니스용 Skype 휴대폰용 (3PIP) 지원을](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351) 참조 하세요.


## <a name="sbc-domain-names"></a>SBC 도메인 이름

SBC 도메인 이름은 테 넌 트의 도메인에 등록 된 이름 중 하나 여야 합니다. SBC의 FQDN 이름 \*에는 onmicrosoft.com 테 넌 트를 사용할 수 없습니다.

다음 표에서는 테 넌 트에 대해 등록 된 DNS 이름 (이름을 SBC의 FQDN으로 사용할 수 있는지 여부)과 올바른 FQDN 이름의 예를 보여 줍니다.

|**DNS 이름**|**SBC FQDN에 사용할 수 있습니다.**|**FQDN 이름 예제**|
|:--- |:--- |:--- |
contoso.com|예|**유효한 이름:**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|아니요|Onmicrosoft.com 도메인 사용은 SBC 이름에 대해 지원 되지 않습니다.

새 도메인 이름을 사용 하 려 한다고 가정 합니다. 예를 들어 테 넌 트가 테 넌 트에 등록 된 도메인 이름으로 contoso.com sbc1.sip.contoso.com를 사용 하려고 합니다. 이름 sbc1.sip.contoso.com를 사용 하 여 SBC를 쌍으로 만들려면 먼저 테 넌 트의 도메인 이름 sip.contoso.com을 등록 해야 합니다. 도메인 이름을 등록 하기 전에 sbc1.sip.contoso.com를 사용 하 여 SBC를 연결 하려고 하면 "sbc1.sip.contoso.com" 도메인이이 테 넌 트에 대해 구성 되지 않았으므로 사용할 수 없습니다. "라는 오류 메시지가 표시 됩니다.
도메인 이름을 추가한 후에는 UPN user@sip.contoso.com를 사용 하 여 사용자를 만들고 팀 라이선스를 할당 해야 합니다. 도메인 이름을 테 넌 트의 도메인에 추가한 후 완전 하 게 프로 비전 하는 데 최대 24 시간이 소요 될 수 있으며, 새 이름을 가진 사용자가 만들어지고 라이선스가 사용자에 게 할당 됩니다. 

회사의 한 테 넌 트에 여러 개의 SIP 주소 공간이 있을 수 있습니다. 예를 들어 회사는 SIP 주소 공간으로 contoso.com 하 고 두 번째 SIP 주소 공간으로 fabrikam.com 수 있습니다. 일부 사용자에 게는 주소 user@contoso.com 있고 일부 사용자에 게는 주소 user@fabrikam.com 있습니다. 

SBC에는 하나의 FQDN만 필요 하며 쌍으로 된 테 넌 트의 주소 공간에서 사용자에 게 서비스를 할 수 있습니다. 예를 들어 이름이 sbc1.contoso.com 인 SBC는 이러한 SIP 주소 공간이 동일한 테 넌 트에 등록 되어 있는 경우 주소 user@contoso.com 및 user@fabrikam.com 사용자에 대 한 PSTN 트래픽을 주고 받을 수 있습니다.  

## <a name="public-trusted-certificate-for-the-sbc"></a>SBC에 대해 신뢰할 수 있는 공용 인증서

CSR (인증 서명 요청)을 생성 하 여 SBC에 대 한 인증서를 요청 하는 것이 좋습니다. SBC에 대 한 CSR을 생성 하는 방법에 대 한 자세한 내용은 SBC 공급 업체에서 제공 하는 상호 관련 지침 또는 설명서를 참조 하세요. 

  > [!NOTE]
  > 대부분의 Ca (인증 기관)는 개인 키 크기가 최소 2048 이어야 합니다. CSR을 생성할 때이 점에 유의 하세요.

인증서의 제목, 일반 이름 또는 주체 대체 이름 필드에 SBC FQDN이 있어야 합니다.

또는 직접 라우팅은 SAN에서 와일드 카드를 지원 하 고, 와일드 카드는 [TLS를 통해 표준 RFC HTTP](https://tools.ietf.org/html/rfc2818#section-3.1)를 준수 해야 합니다. 예를 들어, contoso.com \*는 SBC FQDN sbc.contoso.com 일치 하지만 sbc.test.contoso.com와는 일치 하지 않는 SAN에서 사용 합니다.

다음 루트 인증 기관 중 하나에서 인증서를 생성 해야 합니다.

- AffirmTrust
- 외부 CA 루트 AddTrust
- Baltimore CyberTrust Root
- Buypass
- Cybertrust
- Class 3 공개 기본 인증 기관
- Comodo 루트 CA
- Deutsche Telekom 
- DigiCert 전역 루트 CA
- DigiCert High 보증할 EV 루트 CA
- Entrust
- GlobalSign
- 아빠 이동
- GeoTrust
- Verisign, Inc. 
- SSL.com
- Starfield
- Microsoft 용 Symantec 엔터프라이즈 모바일 루트 
- SwissSign
- CA의 타임 스탬프
- Trustwave
- TeliaSonera 
- T-시스템 국제 GmbH (Deutsche Telekom)
- QuoVadis

Microsoft는 고객 요청에 따라 추가 인증 기관을 추가 하기 위해 노력 하 고 있습니다. 

## <a name="sip-signaling-fqdns"></a>SIP 신호: Fqdn 

직접 라우팅은 다음과 같은 Office 365 환경에서 제공 됩니다.
- Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

GCC, GCC High, DoD 등의 [Office 365 및 US 정부 환경](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) 에 대해 자세히 알아보세요.

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365 및 Office 365 GCC 환경

직접 라우팅에 대 한 연결 지점은 다음 세 가지 Fqdn입니다.

- **sip.pstnhub.microsoft.com** – 전역 FQDN – 먼저 시도해 야 합니다. SBC에서이 이름을 확인 하는 요청을 보낼 때 Microsoft Azure DNS 서버는 SBC에 할당 된 기본 Azure 데이터 센터를 가리키는 IP 주소를 반환 합니다. 과제는 데이터 센터의 성과 메트릭과 SBC에 대 한 지리적 근접성을 기준으로 합니다. 반환 되는 IP 주소는 기본 FQDN에 해당 합니다.
- **sip2.pstnhub.microsoft.com** – 보조 FQDN – 지리적으로 두 번째 우선 순위 영역으로 매핑됩니다.
- **sip3.pstnhub.microsoft.com** – 세 번째 FQDN – 지리적으로 세번째 우선 순위 영역을 매핑합니다.

이러한 세 가지 Fqdn을 순서 대로 배치 하는 데는 다음이 필요 합니다.

- 최적의 환경을 제공 합니다 (첫 번째 FQDN을 쿼리하면 지정 된 SBC 데이터 센터에 가장 가깝습니다).
- SBC의 연결이 일시적인 문제가 발생 하는 데이터 센터에 설정 된 경우 장애 조치를 제공 합니다. 자세한 내용은 아래의 [장애 조치 메커니즘](#failover-mechanism-for-sip-signaling) 을 참조 하세요.  

Fqdn – sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com 및 sip3.pstnhub.microsoft.com – 다음 IP 주소 중 하나로 확인 됩니다.

- 52.114.148.0
- 52.114.132.46 
- 52.114.75.24 
- 52.114.76.76 
- 52.114.7.24 
- 52.114.14.70

수신 및 송신 트래픽을 주소에서 주고 받을 수 있도록 방화벽에서 이러한 모든 IP 주소에 대해 포트를 열어야 합니다.  방화벽이 DNS 이름을 지 원하는 경우 FQDN sip-all.pstnhub.microsoft.com 이러한 모든 IP 주소를 확인 합니다. 


### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 환경

직접 라우팅의 연결 지점은 다음 FQDN입니다.

**sip.pstnhub.dod.teams.microsoft.us** – 전역 FQDN. Office 365 DoD 환경은 미국 데이터 센터에만 있으므로 2 차 및 3 차 Fqdn이 없습니다.

FQDN sip.pstnhub.dod.teams.microsoft.us 다음 IP 주소 중 하나로 확인 됩니다.

- 52.127.64.33
- 52.127.68.34

수신 및 송신 트래픽을 주소에서 주고 받을 수 있도록 방화벽에서 이러한 모든 IP 주소에 대해 포트를 열어야 합니다.  방화벽이 DNS 이름을 지 원하는 경우 FQDN sip.pstnhub.dod.teams.microsoft.us 이러한 모든 IP 주소를 확인 합니다. 

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High 환경

직접 라우팅의 연결 지점은 다음 FQDN입니다.

**sip.pstnhub.gov.teams.microsoft.us** – 전역 FQDN. GCC High 환경은 US 데이터 센터에만 존재 하므로 2 차 및 3 차 Fqdn이 없습니다.

FQDN sip.pstnhub.gov.teams.microsoft.us 다음 IP 주소 중 하나로 확인 됩니다.

- 52.127.88.59
- 52.127.92.64

수신 및 송신 트래픽을 주소에서 주고 받을 수 있도록 방화벽에서 이러한 모든 IP 주소에 대해 포트를 열어야 합니다.  방화벽이 DNS 이름을 지 원하는 경우 FQDN sip.pstnhub.gov.teams.microsoft.us 이러한 모든 IP 주소를 확인 합니다. 

## <a name="sip-signaling-ports"></a>SIP 신호: 포트

직접 라우팅이 제공 되는 Office 365 환경에 대해 다음 포트를 사용 해야 합니다.
- Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

|**통신량**|**보낸 사람**|**받는 사람**|**원본 포트**|**대상 포트**|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP 프록시|하더라도|1024 – 65535|SBC에 정의 된 경우 (Office 365 GCC High/DoD 전용 포트 5061를 사용 해야 합니다.)|
SIP/TLS|하더라도|SIP 프록시|SBC에 정의 됨|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>SIP 신호에 대 한 장애 조치 메커니즘

SBC는 DNS 쿼리를 사용 하 여 sip.pstnhub.microsoft.com를 해결 합니다. SBC 위치 및 데이터 센터 성능 메트릭에 기반 하 여 기본 데이터 센터를 선택 합니다. 기본 데이터 센터에 문제가 발생 하는 경우 SBC는 두 번째 할당 된 데이터 센터로 확인 되는 sip2.pstnhub.microsoft.com를 시도 하 고, 드문 경우 지만 두 지역의 데이터 센터를 사용할 수 없는 경우에는 SBC가 마지막 FQDN (sip3.pstnhub.microsoft.com)을 다시 시도 하 여 세 번째 데이터 센터 IP를 제공 합니다.

아래 표에는 기본, 보조 및 세 번째 데이터 센터 간의 관계가 요약 되어 있습니다.

|**주 데이터 센터가**|**슈팅**|**NOAM**|**북아시아**|
|:--- |:--- |:--- |:--- |
|보조 데이터 센터 (sip2.pstnhub.microsoft.com)|보세요|EU|보세요|
|3 차 데이터 센터 (sip3.pstnhub.microsoft.com)|북아시아|북아시아|EU|
|||||

## <a name="media-traffic-port-ranges"></a>미디어 트래픽: 포트 범위
미디어 바이패스 없이 직접 라우팅을 배포 하려는 경우 아래 요구 사항이 적용 됩니다. 미디어 바이패스에 대 한 방화벽 요구 사항에 대해서는 [직접 라우팅의 미디어 바이패스 계획](https://docs.microsoft.com/microsoftteams/direct-routing-plan-media-bypass)을 참조 하세요.



미디어 소통량이 Microsoft 클라우드의 별도 서비스에 전달 됩니다. 미디어 트래픽 IP 범위는 다음과 같습니다.

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365 및 Office 365 GCC 환경

- 52.112.0.0/14 (IP 주소는 52.112.0.1에서 52.115.255.254)입니다.

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 환경

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High 환경

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>포트 범위 (모든 환경에 해당)
미디어 프로세서의 포트 범위는 다음 표에 나와 있습니다. 

|**통신량**|**보낸 사람**|**받는 사람**|**원본 포트**|**대상 포트**|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|미디어 프로세서|하더라도|3478-3481 및 49152 – 53247|SBC에 정의 됨|
|UDP/SRTP|하더라도|미디어 프로세서|SBC에 정의 됨|3478-3481 및 49152 – 53247|

  > [!NOTE]
  > Microsoft는 SBC에서 동시에 포트를 두 개 이상 사용할 것을 권장 합니다.


## <a name="media-traffic-media-processors-geography"></a>미디어 트래픽: 미디어 프로세서 지리

미디어 소통량은 미디어 프로세서 라는 구성 요소를 통해 흐릅니다. 미디어 프로세서는 SIP 프록시와 동일한 데이터 센터에 배치 됩니다. 또한 미디어 흐름을 최적화 하는 추가 미디어 프로세서가 있습니다. 예를 들어 지금 오스트레일리아에 SIP 프록시 구성 요소가 없기 때문에 (싱가포르 또는 홍콩의 SIP 흐름), 오스트레일리아에는 미디어 프로세서가 로컬로 설치 되어 있습니다. 미디어 프로세서가 로컬로 작동 하는 경우, 예를 들어 오스트레일리아에서 싱가포르 또는 홍콩 등의 소통량을 멀리 보내 경험 하는 대기 시간으로 규정 됩니다. 오스트레일리아에서 홍콩 또는 싱가포르로 흐르는 트래픽의 예에 있는 지연 시간은 SIP 소통량에 대 한 좋은 통화 음질을 유지 하는 데 허용 되지만, 실시간 미디어 소통량에는 적합 하지 않습니다.

미디어 프로세서 위치:

SIP 프록시와 미디어 프로세서 구성 요소가 모두 배포 된 위치:
- 미국 (미국 서 부 및 미국 동부 데이터 센터의 두 가지)
- 유럽 (암스테르담 및 더블린 데이터 센터)
- 아시아 (싱가포르/홍콩 데이터 센터)

미디어 프로세서만 배포 되는 위치 (위에 나열 된 가장 가까운 데이터 센터를 통한 SIP 흐름):
- 일본 (JP/서쪽 데이터 센터)
- 오스트레일리아 (AU 동쪽 및 서쪽 데이터 센터)




## <a name="media-traffic-codecs"></a>미디어 트래픽: 코덱

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>SBC 및 클라우드 미디어 프로세서나 Microsoft 팀 클라이언트 간의 레그.
미디어 바이패스 대/소문자 및 비 바이패스 케이스에 모두 적용 됩니다.

세션 경계 컨트롤러와 클라우드 미디어 프로세서 (미디어 바이패스 없음) 또는 팀 클라이언트와 SBC 간 (미디어 바이패스 사용이 설정 된 경우)의 직접 라우팅 인터페이스는 다음 코덱을 사용할 수 있습니다.

- 비 미디어 바이패스 (SBC에서 클라우드 미디어 프로세서): SILK, 711, 722, G. 729
- 미디어 바이패스 (SBC to 팀 클라이언트): SILK, 711, 722, G 729

제안에서 원하지 않는 코덱을 제외 하 여 세션 경계 컨트롤러에서 특정 코덱을 강제로 사용할 수 있습니다.

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Microsoft 팀 클라이언트와 클라우드 미디어 프로세서 간의 다리
비 미디어 바이패스 대/소문자에만 적용 됩니다. 미디어 바이패스를 사용 하 여 미디어는 팀 클라이언트와 SBC 간에 직접 흐릅니다.

클라우드 미디어 프로세서와 Microsoft 팀 클라이언트 간 레그에서 SILK 또는 722를 사용 합니다. 이 레그의 코덱 선택은 여러 매개 변수를 고려 하는 Microsoft 알고리즘을 기반으로 합니다. 


## <a name="supported-session-border-controllers-sbcs"></a>지원 되는 SBCs (세션 경계 컨트롤러)

Microsoft는 직접 라우팅과 쌍을 연결 하는 인증 된 SBCs만 지원 합니다. 엔터프라이즈 음성은 비즈니스에 중요 하기 때문에 Microsoft는 선택한 SBCs를 사용 하 여 집중적인 테스트를 실행 하 고 SBC 공급 업체와 협력 하 여 두 시스템이 호환 되는지 확인 합니다. 

유효성을 검사 한 디바이스는 팀의 직접적인 라우팅에 대 한 인증 된 것으로 표시 됩니다. 인증 된 장치가 모든 시나리오에서 작동 하도록 보장 됩니다. 

지원 되는 SBCs에 대 한 자세한 내용은 [직접 라우팅을 위해 인증 된 세션 경계 컨트롤러 목록을](direct-routing-border-controllers.md)참조 하세요.

 
## <a name="see-also"></a>참고 항목

[직접 라우팅 구성](direct-routing-configure.md)
