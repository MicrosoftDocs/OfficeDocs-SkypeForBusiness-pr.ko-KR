---
title: 직접 라우팅 계획
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: filippse
ms.topic: conceptual
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Microsoft 직접 라우팅을 통해 지원되는 고객 제공 SBC(세션 테두리 컨트롤러)를 전화 시스템에 연결할 수 있는 방법을 알아봅니다.
ms.openlocfilehash: d49e16ce4a61caf167574ab00189dbdfde1f1d61
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584039"
---
# <a name="plan-direct-routing"></a>직접 라우팅 계획

> [!Tip]
> 직접 라우팅의 이점, 계획 방법 및 배포 방법에 대해 알아보려면 다음 세션을 시청 [하세요. Microsoft Teams의 직접 라우팅](https://aka.ms/teams-direct-routing)

직접 라우팅을 사용하면 지원되는 고객이 제공한 SBC(세션 테두리 컨트롤러)를 전화 시스템에 연결할 수 있습니다. 이 기능을 사용하면 다음 다이어그램과 같이 Microsoft Teams 클라이언트를 사용하여 온-프레미스 PSTN(공중 전화망) 연결을 구성할 수 있습니다. 

![온-프레미스 PSTN 연결의 구성을 보여 주는 다이어그램](media/PlanDirectRouting1-PSTNwithTeams.png "Microsoft Teams 클라이언트를 사용하여 온-프레미스 PSTN 연결 구성")

  > [!NOTE]
  > 비즈니스용 Skype Online을 사용하면 고객이 제공한 SBC를 페어링할 수도 있지만, 이를 위해서는 온-프레미스 비즈니스용 Skype 서버 배포 또는 SBC와 Microsoft Cloud 사이에 Cloud Connector라는 특수 버전의 비즈니스용 Skype 필요합니다. 이 시나리오를 하이브리드 음성이라고 합니다. 반면, 직접 라우팅을 사용하면 지원되는 SBC와 Microsoft Cloud 간에 직접 연결할 수 있습니다.

> [!Important]
> Cloud Connector Edition은 비즈니스용 Skype Online과 함께 2021년 7월 31일 사용 중지됩니다. 조직이 Teams로 업그레이드되면 [직접 라우팅](direct-routing-landing-page.md)을 사용하여 온-프레미스 전화 통신 네트워크를 Teams에 연결하는 방법을 알아봅니다. 

직접 라우팅을 사용하면 SBC를 거의 모든 전화 통신 트렁크에 연결하거나 타사 PSTN 장비와 상호 연결할 수 있습니다. 직접 라우팅을 사용하면 다음을 수행할 수 있습니다. 

- 전화 시스템에서 거의 모든 PSTN 트렁크를 사용합니다. 

- 타사 PBX(프라이빗 분기 교환), 아날로그 디바이스 및 Teams와 같은 고객 소유 전화 통신 장비 간의 상호 운용성을 구성합니다.

또한 Microsoft는 통화 플랜과 같은 클라우드 내 음성 솔루션을 제공합니다. 그러나 다음과 같은 경우 하이브리드 음성 솔루션이 조직에 가장 적합할 수 있습니다. 

- Microsoft 통화 플랜은 해당 국가에서 사용할 수 없습니다. 

- 조직에서는 타사 아날로그 디바이스, 콜 센터 등에 연결해야 합니다. 

- 조직에는 PSTN 이동 통신 사업자와 기존 계약이 있습니다.

직접 라우팅은 Microsoft 통화 플랜에 대한 추가 라이선스가 있는 사용자를 지원합니다. 자세한 내용은 [전화 시스템 및 통화 플랜](calling-plan-landing-page.md)을 참조하세요. 

직접 라우팅을 사용하면 사용자가 예약된 회의에 참여할 때 전화 접속 번호는 적절한 라이선스가 필요한 Microsoft Audio Conferencing Service에서 제공됩니다.  전화를 걸 때 Microsoft 오디오 회의 서비스는 온라인 통화 기능을 사용하여 전화를 걸며 적절한 라이선스가 필요합니다. (사용자에게 Microsoft 오디오 회의 라이선스가 없는 경우 통화는 직접 라우팅을 통해 라우팅됩니다.) 자세한 내용은 [Teams와의 온라인 모임을 참조하세요](https://www.microsoft.com/en-us/microsoft-teams/online-meetings). 
 
직접 라우팅 배포를 계획하는 것은 성공적인 구현의 핵심입니다. 이 문서에서는 인프라 및 라이선스 요구 사항을 설명하고 SBC 연결에 대한 정보를 제공합니다. 

- [인프라 요구 사항](#infrastructure-requirements)
- [라이선스 및 기타 요구 사항](#licensing-and-other-requirements)
- [SBC 도메인 이름](#sbc-domain-names)
- [SBC에 대한 신뢰할 수 있는 공용 인증서](#public-trusted-certificate-for-the-sbc)
- [SIP 신호: FQDN](#sip-signaling-fqdns)
- [SIP 신호: 포트](#sip-signaling-ports)
- [미디어 트래픽: 포트 범위](#media-traffic-port-ranges)
- [지원되는 SCC(세션 테두리 컨트롤러)](#supported-session-border-controllers-sbcs)

직접 라우팅 구성에 대한 자세한 내용은 [직접 라우팅 구성을 참조하세요](direct-routing-configure.md).

## <a name="infrastructure-requirements"></a>인프라 요구 사항
직접 라우팅을 배포하기 위해 지원되는 SCC, 도메인 및 기타 네트워크 연결 요구 사항에 대한 인프라 요구 사항은 다음 표에 나와 있습니다.  

|인프라 요구 사항|다음이 필요합니다.|
|:--- |:--- |
|세션 테두리 컨트롤러(SBC)|지원되는 SBC입니다. 자세한 내용은 [지원되는 SCC를 참조하세요](#supported-session-border-controllers-sbcs).|
|SBC에 연결된 전화 통신 트렁크|SBC에 연결된 하나 이상의 전화 통신 트렁크입니다. 한쪽 끝에서 SBC는 직접 라우팅을 통해 전화 시스템에 연결합니다. 또한 SBC는 PBX, 아날로그 전화 통신 어댑터 등과 같은 타사 전화 통신 엔터티에 연결할 수도 있습니다. SBC에 연결된 모든 PSTN 연결 옵션이 작동합니다. (PSTN 트렁크를 SBC로 구성하려면 SBC 공급업체 또는 트렁크 공급자를 참조하세요.)|
|Microsoft 365 조직|Microsoft Teams 사용자를 홈으로 사용하는 Microsoft 365 조직 및 SBC에 대한 구성 및 연결.|
|사용자 등록 기관|사용자는 Microsoft 365에 있어야 합니다.<br/>회사에 Microsoft 365에 대한 하이브리드 연결이 있는 온-프레미스 비즈니스용 Skype 또는 Lync 환경이 있는 경우 온-프레미스에 있는 사용자에 대해 Teams에서 음성을 사용하도록 설정할 수 없습니다.<br/><br/>사용자의 등록자를 확인하려면 다음 비즈니스용 Skype Online PowerShell cmdlet을 사용합니다.<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>cmdlet의 출력은 다음을 표시해야 합니다.<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|도메인|Microsoft 365 또는 Office 365 조직에 추가된 도메인이 하나 이상 있습니다.<br/><br/>테넌트에 대해 자동으로 생성되는 기본 도메인인 \*.onmicrosoft.com 사용할 수 없습니다.<br/><br/>도메인을 보려면 다음 비즈니스용 Skype Online PowerShell cmdlet을 사용할 수 있습니다.<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>도메인 및 Microsoft 365 또는 Office 365 조직에 대한 자세한 내용은 [도메인 FAQ를](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a) 참조하세요.|
|SBC의 공용 IP 주소|SBC에 연결하는 데 사용할 수 있는 공용 IP 주소입니다. SBC 유형에 따라 SBC는 NAT를 사용할 수 있습니다.|
|SBC의 FQDN(정규화된 도메인 이름)|SBC용 FQDN입니다. 여기서 FQDN의 도메인 부분은 Microsoft 365 또는 Office 365 조직에 등록된 도메인 중 하나입니다. 자세한 내용은 [SBC 도메인 이름을 참조하세요](#sbc-domain-names).|
|SBC에 대한 공용 DNS 항목 |SBC FQDN을 공용 IP 주소에 매핑하는 공용 DNS 항목입니다. |
|SBC에 대한 신뢰할 수 있는 공용 인증서 |직접 라우팅과의 모든 통신에 사용할 SBC에 대한 인증서입니다. 자세한 내용은 [SBC에 대한 신뢰할 수 있는 공용 인증서를](#public-trusted-certificate-for-the-sbc) 참조하세요.|
|직접 라우팅을 위한 연결점 |직접 라우팅에 대한 연결점은 다음과 같은 세 가지 FQDN입니다.<br/><br/>`sip.pstnhub.microsoft.com` – 전역 FQDN을 먼저 시도해야 합니다.<br/>`sip2.pstnhub.microsoft.com` – 보조 FQDN은 지리적으로 두 번째 우선 순위 지역에 매핑됩니다.<br/>`sip3.pstnhub.microsoft.com` – 3차 FQDN은 지리적으로 세 번째 우선 순위 지역에 매핑됩니다.<br/><br/>구성 요구 사항에 대한 자세한 내용은 [SIP 신호: FQDN을 참조하세요](#sip-signaling-fqdns).|
|직접 라우팅 미디어에 대한 방화벽 IP 주소 및 포트 |SBC는 클라우드에서 다음 서비스와 통신합니다.<br/><br/>신호를 처리하는 SIP 프록시<br/>미디어 바이패스가 켜진 경우를 제외하고 미디어를 처리하는 미디어 프로세서<br/><br/>이 두 서비스에는 Microsoft Cloud에 별도의 IP 주소가 있습니다. 이 문서의 뒷부분에 설명되어 있습니다.<br/><br/>자세한 내용은 [URL 및 IP 주소 범위](/office365/enterprise/urls-and-ip-address-ranges)의 [Microsoft Teams 섹션](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)을 참조하세요. |
|미디어 전송 프로필|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Microsoft Teams 미디어의 방화벽 IP 주소 및 포트 |자세한 내용은 [URL 및 IP 주소 범위를 참조하세요](/office365/enterprise/urls-and-ip-address-ranges). |
|||

## <a name="licensing-and-other-requirements"></a>라이선스 및 기타 요구 사항 

직접 라우팅 사용자는 Microsoft 365에서 다음 라이선스를 할당해야 합니다. 

- Microsoft Phone System
- 라이선스에 포함된 경우 Microsoft Teams + 비즈니스용 Skype 플랜 2
- Microsoft 오디오 회의(이 라이선스가 필요한 시기에 대한 특정 예제를 보려면 아래 노트 및 단락을 읽어보세요.)

> [!NOTE]
> 비즈니스용 Skype 플랜이 포함된 라이선스 계약에서 제거해서는 안 됩니다. 
> 
> [!IMPORTANT]
> GCC High 및 DoD 사용자는 G5에 포함된 오디오 회의 라이선스를 사용하지 않도록 설정하고 직접 라우팅이 완전히 구성될 때까지 오디오 회의를 활성화할 때까지 기다려야 합니다. 사용자는 오디오 회의 라이선스를 사용하도록 설정하기 전에 전화 접속 전화 번호와 작동 다이얼 패드를 구성해야 합니다. 자세한 내용은 [GCC High 및 DoD에 대한 직접 라우팅을 사용한 오디오 회의를](./audio-conferencing-with-direct-routing-for-gcch-and-dod.md) 참조하세요.


> [!IMPORTANT]
>  외부 참가자를 예약된 모임에 추가하려면 전화를 걸거나 전화 접속 번호를 제공하여 오디오 회의 라이선스가 필요합니다.
> GCC High 및 DoD의 경우 G5 사용자에 대한 오디오 회의 라이선스를 할당하지 마세요. G3 사용자의 경우 직접 라우팅이 완전히 구성되고 사용자에게 작업 다이얼 패드가 있기 전까지는 오디오 회의 라이선스를 할당하지 마세요.


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>임시 통화 에스컬레이션 및 오디오 회의 라이선스

Teams 사용자는 일대일 Teams-PSTN 또는 Teams-투-Teams 통화를 시작하고 PSTN 참가자를 추가할 수 있습니다. 이 시나리오를 임시 회의라고 합니다. 호출이 수행되는 경로는 호출을 에스컬레이션하는 사용자에게 Microsoft Audio Conferencing 라이선스가 할당되었는지 여부에 따라 달라집니다.

- **통화를 에스컬레이션하는 Teams 사용자에게 Microsoft 오디오 회의 라이선스가 할당된 경우 Microsoft 오디오** 회의 서비스를 통해 에스컬레이션이 발생합니다. 기존 통화에 초대된 원격 PSTN 참가자는 수신 통화에 대한 알림을 받고 에스컬레이션을 시작한 Teams 사용자에게 할당된 Microsoft 브리지의 수를 확인합니다.

- **통화를 에스컬레이션하는 Teams 사용자에게 Microsoft 오디오 회의 라이선스가 할당되지 않은 경우** 직접 라우팅 인터페이스에 연결된 세션 테두리 컨트롤러를 통해 에스컬레이션이 발생합니다. 통화에 초대된 원격 PSTN 참가자는 수신 통화에 대한 알림을 받고 에스컬레이션을 시작한 Teams 사용자의 수를 확인합니다. 에스컬레이션에 사용되는 특정 SBC는 사용자의 라우팅 정책에 의해 정의됩니다. 

다음 사항을 확인해야 합니다.
 
- CsOnlineVoiceRoutingPolicy가 사용자에게 할당됩니다. 

- 프라이빗 통화 허용은 Microsoft Teams의 테넌트 수준에서 사용하도록 설정됩니다. 

직접 라우팅은 Microsoft 통화 플랜에 대한 라이선스가 부여된 사용자도 지원합니다. 통화 플랜이 있는 전화 시스템은 직접 라우팅 인터페이스를 사용하여 일부 통화를 라우팅할 수 있습니다. 그러나 사용자의 전화 번호는 온라인으로 획득하거나 Microsoft로 이식해야 합니다.  

동일한 사용자에 대한 통화 플랜 및 직접 라우팅 연결을 혼합하는 것은 선택 사항이지만 유용할 수 있습니다. 예를 들어 사용자에게 Microsoft 통화 플랜이 할당되었지만 SBC를 사용하여 일부 통화를 라우팅하려는 경우입니다. 가장 일반적인 시나리오 중 하나는 타사 PBX에 대한 호출입니다.  타사 PBX를 사용하면 해당 PBX에 연결된 휴대폰에 대한 호출을 제외한 모든 통화는 Microsoft 통화 플랜을 사용하여 라우팅되지만 타사 PBX에 연결된 휴대폰에 대한 호출은 SBC로 이동하므로 PSTN이 아닌 엔터프라이즈 네트워크 내에 유지됩니다. 

전화 시스템 라이선스에 대한 자세한 내용은 Office 및 [플랜 옵션](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options) 및 [Microsoft Teams 추가 기능 라이선스](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)[를 최대한](https://products.office.com/compare-all-microsoft-office-products?tab=2) 활용하세요. 

## <a name="supported-end-points"></a>지원되는 끝점 

엔드포인트로 사용할 수 있습니다.

- 모든 Teams 클라이언트. 

- 공용 영역 전화. [Microsoft Teams용 공용 영역 전화 설정을 참조하세요](./set-up-common-area-phones.md). 직접 라우팅을 사용하여 공용 영역 전화를 설정할 때 통화 플랜 라이선스가 필요하지 않습니다.

- 3PIP 휴대폰을 비즈니스용 Skype. [Microsoft Teams를 사용하여 비즈니스용 Skype 휴대폰(3PIP) 지원](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351) 참조


## <a name="sbc-domain-names"></a>SBC 도메인 이름

SBC 도메인 이름은 테넌트의 도메인에 등록된 이름 중 하나여야 합니다. SBC의 \*FQDN 이름에 .onmicrosoft.com 테넌트는 사용할 수 없습니다.

다음 표에서는 테넌트에 등록된 DNS 이름의 예, 이름을 SBC의 FQDN으로 사용할 수 있는지 여부 및 유효한 FQDN 이름의 예를 보여 줍니다.

|DNS 이름|SBC FQDN에 사용할 수 있습니다.|FQDN 이름의 예|
|:--- |:--- |:--- |
contoso.com|예|**유효한 이름:**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|아니요|*.onmicrosoft.com 도메인 사용은 SBC 이름에 대해 지원되지 않습니다.

새 도메인 이름을 사용하려는 경우를 가정합니다. 예를 들어 테넌트에 등록된 도메인 이름으로 contoso.com sbc1.sip.contoso.com 사용하려고 합니다. SBC를 이름 sbc1.sip.contoso.com 연결하려면 먼저 테넌트의 도메인에 sip.contoso.com 도메인 이름을 등록해야 합니다. 도메인 이름을 등록하기 전에 SBC를 sbc1.sip.contoso.com 페어링하려고 하면 "이 테넌트에 대해 구성되지 않았기 때문에 "sbc1.sip.contoso.com" 도메인을 사용할 수 없습니다." 오류가 발생합니다.
도메인 이름을 추가한 후에는 UPN user@sip.contoso.com 사용자를 만들고 Teams 라이선스를 할당해야 합니다. 테넌트 도메인에 추가되고, 새 이름을 가진 사용자가 만들어지고, 라이선스가 사용자에게 할당된 후 도메인 이름을 완전히 프로비전하는 데 최대 24시간이 걸릴 수 있습니다. 

회사에 하나의 테넌트에 여러 개의 SIP 주소 공간이 있을 수 있습니다. 예를 들어 회사에서 SIP 주소 공간으로 contoso.com 두 번째 SIP 주소 공간으로 fabrikam.com 수 있습니다. 일부 사용자는 주소 user@contoso.com 있고 일부 사용자에게는 주소 user@fabrikam.com 있습니다. 

SBC에는 하나의 FQDN만 필요하며 쌍을 이루는 테넌트의 모든 주소 공간에서 사용자를 서비스할 수 있습니다. 예를 들어 이름이 sbc1.contoso.com SBC는 주소가 user@contoso.com 사용자에 대해 PSTN 트래픽을 수신하고 보낼 수 있으며, 이러한 SIP 주소 공간이 동일한 테넌트에 등록되어 있는 한 user@fabrikam.com 수 있습니다.  

 > [!NOTE]
 > Azure Communication Services 직접 라우팅의 SBC FQDN은 Teams 직접 라우팅의 SBC FQDN과 달라야 합니다.
  
## <a name="public-trusted-certificate-for-the-sbc"></a>SBC에 대한 신뢰할 수 있는 공용 인증서

CSR(인증 서명 요청)을 생성하여 SBC에 대한 인증서를 요청하는 것이 좋습니다. SBC용 CSR 생성에 대한 구체적인 지침은 SBC 공급업체에서 제공하는 상호 연결 지침 또는 설명서를 참조하세요. 

> [!NOTE]
> 대부분의 CA(인증 기관)에는 프라이빗 키 크기가 2048 이상이어야 합니다. CSR을 생성할 때는 이 점을 염두에 두어야 합니다.

인증서에는 CN(일반 이름) 또는 SAN(주체 대체 이름) 필드로 SBC FQDN이 있어야 합니다.

또는 직접 라우팅은 CN 및/또는 SAN에서 와일드카드를 지원하며 와일드카드는 [TLS를 통한 표준 RFC HTTP](https://tools.ietf.org/html/rfc2818#section-3.1)를 준수해야 합니다. 예를 들어 SBC FQDN sbc.contoso.com 일치하지만 sbc.test.contoso.com 일치하지 않는 .contoso.com 사용하는 \*것이 있습니다.

직접 라우팅 SIP 인터페이스는 Microsoft 신뢰할 수 있는 루트 인증서 프로그램의 일부인 CA(인증 기관)에서 서명한 인증서만 신뢰합니다. SBC 인증서가 프로그램의 일부인 CA에서 서명하고 인증서의 EKU(확장 키 사용) 확장에 서버 인증이 포함되어 있는지 확인합니다.
자세한 정보: [프로그램 요구 사항 - Microsoft 신뢰할 수 있는 루트 프로그램](/security/trusted-root/program-requirements)
  
[포함된 CA 인증서 목록](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)
  
 Office 365 GCCH 및 DoD 환경에서 직접 라우팅의 경우 다음 루트 인증 기관 중 하나에서 인증서를 생성해야 합니다.

- DigiCert 글로벌 루트 CA
- DigiCert High Assurance EV 루트 CA

> [!NOTE]
> SBC에서 Teams 연결에 대해 MTLS(상호 TLS) 지원을 사용하도록 설정한 경우 Teams TLS 컨텍스트의 SBC 신뢰할 수 있는 루트 저장소에 Baltimore CyberTrust Root 및 DigiCert Global Root G2 인증서를 설치해야 합니다. (Microsoft 서비스 인증서는 이러한 두 루트 인증서 중 하나를 사용하기 때문입니다.) 이러한 루트 인증서를 다운로드하려면 [Office 365 암호화 체인](/microsoft-365/compliance/encryption-office-365-certificate-chains)을 참조하세요. 자세한 내용은 [Office TLS 인증서 변경 내용을](/microsoft-365/compliance/encryption-office-365-tls-certificates-changes) 참조하세요.

## <a name="sip-signaling-fqdns"></a>SIP 신호: FQDN 

직접 라우팅은 다음 환경에서 제공됩니다.

- Microsoft 365 또는 Office 365
- GCC Office 365
- Office 365 GCC High
- Office 365 DoD

GCC, GCC High 및 DoD[와 같은 Office 365 및 미국 정부 환경에](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) 대해 자세히 알아봅니다.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365, Office 365 및 Office 365 GCC 환경

직접 라우팅에 대한 연결점은 다음과 같은 세 가지 FQDN입니다.

- **sip.pstnhub.microsoft.com** – 전역 FQDN – 먼저 시도해야 합니다. SBC가 이 이름을 확인하기 위한 요청을 보내면 Microsoft Azure DNS 서버는 SBC에 할당된 기본 Azure 데이터 센터를 가리키는 IP 주소를 반환합니다. 할당은 데이터 센터의 성능 메트릭과 SBC에 대한 지리적 근접성을 기반으로 합니다. 반환되는 IP 주소는 기본 FQDN에 해당합니다.

- **sip2.pstnhub.microsoft.com** – 보조 FQDN – 지리적으로 두 번째 우선 순위 지역에 매핑됩니다.

- **sip3.pstnhub.microsoft.com** – 3차원 FQDN – 지리적으로 세 번째 우선 순위 지역에 매핑됩니다.

다음 세 가지 FQDN을 순서대로 배치해야 합니다.

- 최적의 환경을 제공합니다(첫 번째 FQDN을 쿼리하여 할당된 SBC 데이터 센터에 덜 로드되고 가장 가깝습니다).

- SBC에서 임시 문제가 발생하는 데이터 센터에 연결할 때 장애 조치(failover)를 제공합니다. 자세한 내용은 아래 [의 장애 조치(failover) 메커니즘](#failover-mechanism-for-sip-signaling) 을 참조하세요.  

FQDN(sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com 및 sip3.pstnhub.microsoft.com)은 다음 서브넷의 IP 주소로 확인됩니다.

- 52.112.0.0/14
- 52.120.0.0/14

신호 전달을 위해 주소 간에 들어오고 나가는 트래픽을 허용하려면 방화벽에서 이러한 모든 IP 주소 범위에 대한 포트를 열어야 합니다.

### <a name="office-gcc-dod-environment"></a>Office GCC DoD 환경

직접 라우팅에 대한 연결점은 다음과 같은 FQDN입니다.

**sip.pstnhub.dod.teams.microsoft.us** – 전역 FQDN. Office 365 DoD 환경은 미국 데이터 센터에만 존재하므로 보조 및 삼차 FQDN이 없습니다.

FQDN sip.pstnhub.dod.teams.microsoft.us 다음 서브넷에서 IP 주소로 확인됩니다.

- 52.127.64.0/21

신호 전송을 위해 주소 간에 들어오고 나가는 트래픽을 허용하려면 방화벽에서 이러한 모든 IP 주소에 대한 포트를 열어야 합니다.

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High 환경

직접 라우팅에 대한 연결점은 다음과 같은 FQDN입니다.

**sip.pstnhub.gov.teams.microsoft.us** – 전역 FQDN. GCC High 환경은 미국 데이터 센터에만 존재하므로 보조 및 3차 FQDN이 없습니다.

FQDN sip.pstnhub.gov.teams.microsoft.us 다음 서브넷에서 IP 주소로 확인됩니다.

- 52.127.88.0/21

신호 전송을 위해 주소 간에 들어오고 나가는 트래픽을 허용하려면 방화벽에서 이러한 모든 IP 주소에 대한 포트를 열어야 합니다.

## <a name="sip-signaling-ports"></a>SIP 신호: 포트

직접 라우팅이 제공되는 Microsoft 365 또는 Office 365 환경에 다음 포트를 사용해야 합니다.

- Microsoft 365 또는 Office 365
- GCC Office 365
- Office 365 GCC High
- Office 365 DoD

|트래픽을|보낸 사람|받는 사람|원본 포트|대상 포트|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP 프록시|Sbc|1024 – 65535|SBC에 정의됨(Office 365 GCC High/DoD의 경우 포트 5061만 사용해야 함)|
SIP/TLS|Sbc|SIP 프록시|SBC에 정의됨|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>SIP 신호에 대한 장애 조치(failover) 메커니즘

SBC는 dns 쿼리를 만들어 sip.pstnhub.microsoft.com 확인합니다. SBC 위치 및 데이터 센터 성능 메트릭에 따라 기본 데이터 센터가 선택됩니다. 기본 데이터 센터에 문제가 발생하는 경우 SBC는 두 번째 할당된 데이터 센터로 확인되는 sip2.pstnhub.microsoft.com 시도하며, 드물게 두 지역의 데이터 센터를 사용할 수 없는 경우 SBC는 3차 데이터 센터 IP를 제공하는 마지막 FQDN(sip3.pstnhub.microsoft.com)을 다시 시도합니다.

아래 표에는 기본 데이터 센터, 보조 데이터 센터 및 3차 데이터 센터 간의 관계가 요약되어 있습니다.

|기본 데이터 센터가 인 경우|Emea|Noam|아시아|
|:--- |:--- |:--- |:--- |
|보조 데이터 센터(sip2.pstnhub.microsoft.com)|우리|Eu|우리|
|3차 데이터 센터(sip3.pstnhub.microsoft.com)|아시아|아시아|Eu|
|||||

## <a name="media-traffic-port-ranges"></a>미디어 트래픽: 포트 범위
미디어 바이패스 없이 직접 라우팅을 배포하려는 경우 아래 요구 사항이 적용됩니다. 미디어 바이패스에 대한 방화벽 요구 사항은 [직접 라우팅을 사용한 미디어 바이패스 계획을](./direct-routing-plan-media-bypass.md) 참조하세요.

미디어 트래픽은 Microsoft Cloud에서 별도의 서비스로 들어오고 흐릅니다. 미디어 트래픽의 IP 주소 범위는 다음과 같습니다.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365, Office 365 및 Office 365 GCC 환경

- 52.112.0.0/14(52.112.0.1에서 52.115.255.254까지의 IP 주소).
- 52.120.0.0/14(52.120.0.1에서 52.123.255.254까지의 IP 주소).

### <a name="office-365-dod-environment"></a>Office 365 DoD 환경

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High 환경

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>포트 범위(모든 환경에 적용 가능)
미디어 프로세서의 포트 범위는 다음 표에 나와 있습니다. 

|트래픽을|보낸 사람|받는 사람|원본 포트|대상 포트|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|미디어 프로세서|Sbc|3478-3481 및 49152 – 53247|SBC에 정의됨|
|UDP/SRTP|Sbc|미디어 프로세서|SBC에 정의됨|3478-3481 및 49152 – 53247|

  > [!NOTE]
  > Microsoft는 SBC에서 동시 호출당 두 개 이상의 포트를 권장합니다.


## <a name="media-traffic-media-processors-geography"></a>미디어 트래픽: 미디어 프로세서 지리

미디어 트래픽은 미디어 프로세서라는 구성 요소를 통해 흐릅니다. 미디어 프로세서는 SIP 프록시와 동일한 데이터 센터에 배치됩니다.

- NOAM(미국 중남부, 미국 서부 및 미국 동부 데이터 센터 2개)
- 유럽(영국 남부, 프랑스 중부, 암스테르담 및 더블린 데이터 센터)
- 아시아(싱가포르 데이터 센터)
- 일본(JP 동부 및 서부 데이터 센터)
- 오스트레일리아(AU 동부 및 남동부 데이터 센터)
- LATAM(브라질 남부)
- 아프리카(남아프리카 북부)

## <a name="media-traffic-codecs"></a>미디어 트래픽: 코덱

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>SBC와 클라우드 미디어 프로세서 또는 Microsoft Teams 클라이언트 간 레그

미디어 바이패스 사례와 바이패스 이외의 경우 모두에 적용됩니다.

세션 테두리 컨트롤러와 클라우드 미디어 프로세서(미디어 바이패스 제외) 또는 Teams 클라이언트와 SBC 간(미디어 바이패스 사용이 설정된 경우) 다리의 직접 라우팅 인터페이스는 다음 코덱을 사용할 수 있습니다.

- 비미디어 바이패스(SBC에서 클라우드 미디어 프로세서로): SILK, G.711, G.722, G.729
- 미디어 바이패스(SBC에서 Teams 클라이언트로): SILK, G.711, G.722, G.729

제안에서 바람직하지 않은 코덱을 제외하여 세션 테두리 컨트롤러에서 특정 코덱을 강제로 사용할 수 있습니다.

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Microsoft Teams 클라이언트와 클라우드 미디어 프로세서 간 레그

미디어가 아닌 바이패스 사례에만 적용됩니다. 미디어 바이패스를 사용하면 미디어가 Teams 클라이언트와 SBC 간에 직접 흐릅니다.

클라우드 미디어 프로세서와 Microsoft Teams 클라이언트 간의 다리에서 SILK 또는 G.722가 사용됩니다. 이 레그에서 코덱 선택은 여러 매개 변수를 고려한 Microsoft 알고리즘을 기반으로 합니다. 

  > [!NOTE]
  > 미디어 다시 대상 지정은 지원되지 않습니다. 직접 라우팅 통화 중에 SBC가 Teams 직접 라우팅에 새 미디어 IP를 보내는 경우 SIP 신호에서 협상되지만 미디어는 Teams 직접 라우팅에서 새 IP 주소로 전송되지 않습니다.

## <a name="supported-session-border-controllers-sbcs"></a>지원되는 SCC(세션 테두리 컨트롤러)

Microsoft는 직접 라우팅과 쌍을 이루는 인증된 SCC만 지원합니다. Enterprise Voice 비즈니스에 중요하기 때문에 Microsoft는 선택한 SBC를 사용하여 집중적인 테스트를 실행하고 SBC 공급업체와 협력하여 두 시스템의 호환성을 보장합니다. 

유효성이 검사된 디바이스는 Teams 직접 라우팅용 인증으로 나열됩니다. 인증된 디바이스는 모든 시나리오에서 작동하도록 보장됩니다. 

지원되는 SCC에 대한 자세한 내용은 [직접 라우팅에 대해 인증된 세션 테두리 컨트롤러를 참조하세요](direct-routing-border-controllers.md).

## <a name="support-boundaries"></a>지원 경계
Microsoft는 인증 디바이스로 사용하는 경우에만 직접 라우팅을 사용하는 전화 시스템을 지원합니다. 문제가 있는 경우 SBC 공급업체의 고객 지원에 먼저 문의해야 합니다. 필요한 경우 SBC 공급업체에서 내부 채널을 통해 Microsoft로 문제를 에스컬레이션합니다. Microsoft에는 인증되지 않은 디바이스에서 직접 라우팅을 통해 전화 시스템에 연결할 경우 지원을 거부할 권리가 있습니다. Microsoft에서 고객의 직접 라우팅 문제가 공급업체의 SBC 장치와 관련된 것으로 판단되면 고객은 SBC 공급업체에 다시 참여를 요청해야 합니다.
 
## <a name="see-also"></a>참고 항목

[직접 라우팅 구성](direct-routing-configure.md)
