---
title: 직접 라우팅을 위한 미디어 바이패스 계획
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 미디어 트래픽 경로를 단축하고 성능을 개선할 수 있는 Phone System Direct 라우팅을 사용하여 미디어 우회를 계획하는 방법을 알아보습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e21007c31dca540e4f659aad627911b4aec2e456
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460868"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a>직접 라우팅을 위한 미디어 바이패스 계획

## <a name="about-media-bypass-with-direct-routing"></a>직접 라우팅을 통해 미디어 우회에 대해

미디어 우회를 사용하면 미디어 트래픽 경로를 단축하고 더 나은 성능을 위해 전송되는 홉 수를 줄일 수 있습니다. 미디어 우회를 사용하여 Microsoft Phone System을 통해 전송하는 대신 SBC(세션 테두리 컨트롤러)와 클라이언트 간에 미디어가 유지됩니다. 미디어 우회를 구성하려면 SBC와 클라이언트가 동일한 위치 또는 네트워크에 있어야 합니다.

**-MediaBypass** 매개 변수가 true 또는 false로 설정된 **Set-CSOnlinePSTNGateway** 명령을 사용하여 각 SBC에 대한 미디어 우회를 제어할 수 있습니다. 미디어 우회를 사용하도록 설정하는 경우 모든 미디어 트래픽이 회사 네트워크 내에 유지되지는 않습니다. 이 문서에서는 다양한 시나리오에서 호출 흐름을 설명합니다.    

아래 다이어그램은 미디어 우회와 없는 호출 흐름의 차이를 보여 주는 것입니다.

미디어 우회 없이 클라이언트가 전화를 걸거나 받을 때 다음 다이어그램과 같이 SBC, Microsoft Phone System 및 Teams 클라이언트 간에 신호 및 미디어 흐름이 모두 표시됩니다.

> [!div class="mx-imgBorder"]
> ![미디어 우회 없이 신호 및 미디어 흐름 표시](media/direct-routing-media-bypass-1.png)


그러나 사용자가 SBC와 동일한 건물 또는 네트워크에 있는 것으로 가정해 가정해 야 합니다. 예를 들어 프랑크푸르트의 건물에 있는 사용자가 PSTN 사용자에게 전화를 걸었다고 가정합니다. 

- **미디어 우회** 없이는 미디어가 암스테르담 또는 더블린(Microsoft 데이터 센터가 배포되는 곳)을 통해 다시 프랑크푸르트의 SBC로 흐르게 됩니다. 

  유럽의 데이터 센터는 SBC가 유럽에 있으며 Microsoft는 SBC에 가장 가까운 데이터 센터를 사용하기 때문에 선택됩니다. 이 접근 방식은 대부분의 지리에서 Microsoft 네트워크 내의 트래픽 흐름 최적화로 인해 통화 품질에 영향을 주지는 하지만 트래픽에는 불필요한 루프가 있습니다.     

- **미디어 우회를** 사용하면 다음 다이어그램과 같이 Teams 사용자와 SBC 간에 미디어가 직접 유지됩니다.

  > [!div class="mx-imgBorder"]
  > ![미디어 우회를 통해 신호 및 미디어 흐름 표시](media/direct-routing-media-bypass-2.png)

미디어 우회는 SBC의 Teams 클라이언트 및 ICE 라이트에서 ICE(Interactive Connectivity Establishment)라는 프로토콜을 활용합니다. 이러한 프로토콜을 사용하면 직접 라우팅이 최적의 품질을 위해 가장 직접적인 미디어 경로를 사용할 수 있습니다. ICE 및 ICE Lite는 WebRTC 표준입니다. 이러한 프로토콜에 대한 자세한 내용은 RFC 5245를 참조하세요.


## <a name="call-flow-and-firewall-planning"></a>통화 흐름 및 방화벽 계획

통화 흐름 및 방화벽 계획은 사용자가 SBC의 공용 IP 주소에 직접 액세스할 수 있는지 여부와 사용자가 네트워크 내부 또는 외부에 있는지 여부에 따라 결정됩니다.

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a>사용자가 SBC의 공용 IP 주소에 직접 액세스하는 경우 통화 흐름

사용자가 SBC의 공용 IP 주소에 직접 액세스할 수 있는 경우 호출 흐름은 다음과 같습니다.

- 미디어 우회의 경우 Teams 클라이언트는 내부 네트워크에서도 SBC의 공용 IP 주소에 액세스할 수 있어야 합니다. 직접 미디어를 원하지 않는 경우 미디어는 전송 릴레이를 통해 흐를 수 있습니다.

- 이 솔루션은 사용자가 SBC와 동일한 건물 및/또는 네트워크에 있는 경우 권장되는 솔루션입니다. 미디어 경로에서 Microsoft Cloud 구성 요소를 제거합니다.

- 신호는 항상 Microsoft 클라우드를 통해 전달됩니다.

다음 다이어그램은 미디어 우회를 사용하도록 설정하고 클라이언트가 내부 상태일 때 호출 흐름을 보여 주며, 클라이언트가 SBC(직접 미디어)의 공용 IP 주소에 도달할 수 있습니다. 

- 경로의 화살표 및 숫자 값은 Microsoft Teams 호출 흐름에 [따라 입니다.](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)

- SIP 신호는 항상 경로 4 및 4'(트래픽 방향에 따라 다를 수 있습니다)를 하게 됩니다. 미디어는 로컬로 유지하며 경로 5b를 하게 됩니다.

> [!div class="mx-imgBorder"]
> ![Media Bypass를 사용하도록 설정한 통화 흐름 표시, 클라이언트가 내부](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a>사용자가 SBC의 공용 IP 주소에 액세스할 수 없는 경우 통화 흐름

다음에서는 사용자가 SBC의 공용 IP 주소에 액세스할 수 없는 경우 호출 흐름을 설명합니다. 

예를 들어 사용자가 외부인 것으로 가정하고 테넌트 관리자는 인터넷의 모든 사용자에게 SBC의 공용 IP 주소를 열지 말고 Microsoft Cloud에만 열지로 결정했습니다. 트래픽의 내부 구성 요소는 Teams 전송 릴레이를 통해 흐를 수 있습니다. 다음과 같은 사항을 고려해야 합니다.

- Teams 전송 릴레이가 사용됩니다.

- 미디어 우회의 경우 Microsoft는 Teams 전송 릴레이와 SBC 간에 포트 50 000에서 59 999 포트를 여는 데 필요한 전송 릴레이 버전을 사용합니다(향후 3478 및 3479 포트만 필요한 버전으로 이동할 계획입니다).


다음 다이어그램은 미디어 우회를 사용하도록 설정하고 클라이언트가 외부에 있으며, 클라이언트가 세션 테두리 컨트롤러의 공용 IP 주소에 도달할 수 없는 경우 호출 흐름을 보여줍니다(미디어는 Teams 전송 릴레이로 릴레이됩니다).

- 경로의 화살표 및 숫자 값은 Microsoft Teams 호출 흐름에 [따라 입니다.](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)

- 미디어는 경로 3, 3', 4 및 4'를 통해 릴레이됩니다.

> [!div class="mx-imgBorder"]
> ![사용자가 SBC의 공용 IP에 액세스할 수 없는 경우 통화 흐름 표시](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a>사용자가 네트워크 외부에 있으며 SBC의 공용 IP에 대한 액세스 권한이 있는 경우 통화 흐름

> [!NOTE]
> Teams 전송 릴레이를 활용하지 못하기 때문에 권장되는 구성은 아니기 때문에 권장되지 않습니다. 대신 사용자가 SBC의 공용 IP 주소에 액세스할 수 없는 이전 시나리오를 고려해야 합니다. 

다음 다이어그램은 미디어 우회를 사용하도록 설정하고, 클라이언트가 외부에 있으며, 클라이언트가 SBC(직접 미디어)의 공용 IP 주소에 도달할 수 있는 호출 흐름을 보여줍니다.

- 경로의 화살표 및 숫자 값은 [Microsoft Teams](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) 호출 흐름 문서에 따라 표시됩니다.

- SIP 신호는 항상 경로 3 및 3'(트래픽 방향에 따라 다를 수 있습니다.)을 하게 됩니다. 경로 2를 사용하여 미디어 흐름입니다.

> [!div class="mx-imgBorder"]
> ![사용자가 SBC의 공용 IP에 액세스할 수 없는 경우 통화 흐름 표시](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a>미디어 프로세서 및 전송 릴레이 사용

Microsoft Cloud에는 미디어 트래픽 경로에 있는 미디어 프로세서 및 전송 릴레이의 두 가지 구성 요소가 있습니다. 

- Media Processor는 비우회 사례에서 미디어를 처리하고 음성 애플리케이션용 미디어를 처리하는 공용 직면 구성 요소입니다.

   미디어 프로세서는 항상 최종 사용자가 우회되지 않은 호출에 대한 경로에 있지만, 우회 호출 경로에는 없습니다. Media Processor는 호출 공원, 조직 자동 전화 교환 큐와 같은 모든 음성 애플리케이션에 대해 항상 경로에 있습니다.

- 전송 릴레이는 가장 가까운 전송 서비스에 연결하여 실시간 트래픽을 전송하는 데 사용됩니다.

   전송 릴레이는 사용자가 어디에 있는지, 네트워크가 구성되는 방식에 따라 우회 호출 경로에 있을 수도 있습니다.

다음 다이어그램은 미디어 우회를 사용하도록 설정한 호출 흐름과 미디어 우회를 사용하지 않도록 설정한 두 번째 호출 흐름을 보여줍니다. 다이어그램은 종단 사용자 또는 종단 사용자로부터 시작된 트래픽만 보여 주는 것입니다.  
- Media Controller는 미디어 프로세서를 할당하고 SDP(세션 설명 프로토콜) 제안을 만드는 Azure의 마이크로 서비스입니다.

- SIP 프록시는 Teams에서 사용되는 HTTP REST 신호를 SIP로 변환하는 구성 요소입니다.    

> [!div class="mx-imgBorder"]
> ![Media Bypass를 사용하도록 설정하고 사용하지 않도록 설정한 통화 흐름 표시](media/direct-routing-media-bypass-6.png)


아래 표에서는 Media Processor와 전송 릴레이의 차이점을 요약합니다.

|    | 미디어 프로세서 | 전송 릴레이|
| :--------------|:---------------|:------------|
최종 사용자의 비우회 호출에 대한 미디어 경로에서 | 항상 | 클라이언트가 Media Processor에 직접 도달할 수 없는 경우 | 
최종 사용자의 우회 호출에 대한 미디어 경로에서 | 절대로 안 | 클라이언트가 공용 IP 주소에서 SBC에 도달할 수 없는 경우 | 
음성 애플리케이션의 미디어 경로에서 | 항상 | 절대로 안 | 
트랜스코드를 할 수 있습니다(B2BUA)\* | 예 | 아니요, 엔드포인트 간에 오디오만 릴레이 | 
전 세계 인스턴스 수 및 위치 | 총 10개: 미국 동부 및 서부에서 2개; 암스테르담 및 더블린에서 2개; 홍콩 및 싱가포르에서 2개; 일본에서 2; 오스트레일리아 동부 및 남동부의 2 | 다중

IP 범위는:
- 52.112.0.0/14(52.112.0.1에서 52.115.255.254까지의 IP 주소)
- 52.120.0.0/14(52.120.0.1에서 52.123.255.254까지의 IP 주소)

\* 트랜스코드 설명: 

- Media Processor는 B2BUA로 코덱을 변경할 수 있습니다(예: TEAMS 클라이언트에서 MP로 SILK, MP와 SBC 간에 G.711).

- 전송 릴레이는 B2BUA가 아니기 때문에 릴레이를 통해 트래픽이 흐르는 경우에도 클라이언트와 SBC 간에 코덱이 변경되지 않습니다.

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a>미디어 우회에 대해 트렁크가 구성된 경우 Teams Media Processor 사용

Teams Media Processor는 항상 다음 시나리오의 미디어 경로에 삽입됩니다.

- 통화가 1:1에서 그룹 호출로 에스컬레이터됩니다.
- 페더리드 Teams 사용자에게 통화가 진행됩니다.
- 비즈니스용 Skype 사용자에게 통화가 전달되거나 전송됩니다.

아래 설명된 바와 같이 SBC에서 Media Processor 및 전송 릴레이 범위에 액세스할 수 있도록 합니다.    


## <a name="sip-signaling-fqdns"></a>SIP 신호: FQDNS

SIP 신호의 경우 FQDN 및 방화벽 요구 사항은 우회되지 않은 경우와 동일합니다. 

직접 라우팅은 다음 Microsoft 365 또는 Office 365 환경에서 제공됩니다.
- Microsoft 365 또는 Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD에서는 GCC, GCC High 및 DoD와 같은 [Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) 및 미국 정부 환경에 대해 자세히 알아보십시오.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365, Office 365 및 Office 365 GCC 환경

직접 라우팅의 연결 지점은 다음 세 가지 FQDNS입니다.

- **sip.pstnhub.microsoft.com** FQDN - 먼저 시도해야 합니다. SBC에서 이 이름을 확인하기 위한 요청을 보내면 Microsoft Azure DNS 서버는 SBC에 할당된 기본 Azure 데이터 센터를 지적하는 IP 주소를 반환합니다. 할당은 데이터 센터의 성능 메트릭 및 SBC에 대한 지리적 근접성을 기반으로 합니다. 반환된 IP 주소는 기본 FQDN에 해당합니다.

- **sip2.pstnhub.microsoft.com** - 보조 FQDN – 지리적으로 두 번째 우선 순위 지역에 매핑됩니다.

- **sip3.pstnhub.microsoft.com** - Tertiary FQDN – 지리적으로 세 번째 우선 순위 지역에 매핑됩니다.

다음을 위해 다음 세 개의 FQDNS를 두어야 합니다.

- 최적의 환경을 제공합니다(로드가 적고 첫 번째 FQDN을 쿼리하여 할당된 SBC 데이터 센터에 가장 가깝습니다).

- 일시적인 문제가 발생하는 데이터 센터에 SBC의 연결이 설정되면 장애 조치(failover)를 제공합니다. 자세한 내용은 아래 장애 조치 메커니즘을 참조하세요.


FQDNs **sip.pstnhub.microsoft.com** **및** sip2.pstnhub.microsoft.com 및 sip3.pstnhub.microsoft.com 다음 IP 주소 **중** 하나에 대해 해결됩니다.
- 52.114.148.0
- 52.114.132.46
- 52.114.16.74
- 52.114.20.29
- 52.114.75.24
- 52.114.76.76
- 52.114.7.24
- 52.114.14.70

신호에 대한 주소와 수신 트래픽을 허용하려면 방화벽에서 이러한 모든 IP 주소에 대한 포트를 열면 됩니다. 방화벽이 DNS 이름을 지원하는 경우 FQDN  sip-all.pstnhub.microsoft.com 모든 IP 주소로 확인됩니다. 

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 환경

직접 라우팅의 연결 지점은 다음 FQDN입니다.

**sip.pstnhub.dod.teams.microsoft.us** - 글로벌 FQDN입니다. Office 365 DoD 환경은 미국 데이터 센터에만 존재하기에 보조 및 세로 FQDNS가 없습니다.

FQDNs – sip.pstnhub.dod.teams.microsoft.us IP 주소 중 하나에 대해 해결됩니다.

- 52.127.64.33
- 52.127.68.34

신호에 대한 주소와 수신 트래픽을 허용하려면 방화벽에서 이러한 모든 IP 주소에 대한 포트를 열면 됩니다.  방화벽이 DNS 이름을 지원하는 경우 FQDN sip.pstnhub.dod.teams.microsoft.us 모든 IP 주소로 확인됩니다. 

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC 높은 환경

직접 라우팅의 연결 지점은 다음 FQDN입니다.

**sip.pstnhub.gov.teams.microsoft.us** – 글로벌 FQDN입니다. GCC High 환경은 미국 데이터 센터에만 존재하기에 보조 및 세로 FQDNS가 없습니다.

FQDNs – sip.pstnhub.gov.teams.microsoft.us IP 주소 중 하나에 대해 해결됩니다.

- 52.127.88.59
- 52.127.92.64

신호에 대한 주소와 수신 트래픽을 허용하려면 방화벽에서 이러한 모든 IP 주소에 대한 포트를 열면 됩니다.  방화벽이 DNS 이름을 지원하는 경우 FQDN sip.pstnhub.gov.teams.microsoft.us 모든 IP 주소로 확인됩니다. 

## <a name="sip-signaling-ports"></a>SIP 신호: 포트

포트 요구 사항은 직접 라우팅이 제공되는 모든 Office 365 환경에 대해 동일합니다.
- Microsoft 365 또는 Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

다음 포트를 사용해야 합니다.

| 트래픽 | 보낸 사람 | 받는 사람 | 원본 포트 | 대상 포트|
| :-------- | :-------- |:-----------|:--------|:---------|
SIP/TLS| SIP 프록시 | SBC | 1024 - 65535 | SBC에 정의 |
| SIP/TLS | SBC | SIP 프록시 | SBC에 정의 | 5061 |


## <a name="media-traffic-ip-and-port-ranges"></a>미디어 트래픽: IP 및 포트 범위

직접 연결을 사용할 수 있는 경우 또는 클라이언트가 공용 IP 주소를 사용하여 SBC에 도달할 수 없는 경우 Teams 전송 릴레이를 통해 SBC와 Teams 클라이언트 간에 미디어 트래픽이 흐르게 됩니다.

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a>직접 미디어 트래픽에 대한 요구 사항(Teams 클라이언트와 SBC 간) 

클라이언트는 SBC의 공용 IP 주소에서 지정된 포트(표 참조)에 액세스할 수 있어야 합니다. 

참고: 클라이언트가 내부 네트워크에 있는 경우 미디어는 SBC의 공용 IP 주소로 흐르게 됩니다. 트래픽이 엔터프라이즈 네트워크 장비에서 나가지 않을 수 있도록 NAT 디바이스에 머리 고정을 구성할 수 있습니다.

| 트래픽 | 보낸 사람 | 받는 사람 | 원본 포트 | 대상 포트|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | 클라이언트 | SBC | 50 000 – 50 019  | SBC에 정의 |
| UDP/SRTP | SBC | 클라이언트 | SBC에 정의 | 50 000 – 50 019  |


> [!NOTE]
> 클라이언트의 원본 포트를 변환하는 네트워크 장치가 있는 경우 네트워크 장비와 SBC 간에 번역된 포트가 열립니다. 

### <a name="requirements-for-using-transport-relays"></a>전송 릴레이 사용에 대한 요구 사항

전송 릴레이는 Media Processor와 동일한 범위에 있습니다(비 우회 사례의 경우). 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365, Office 365 및 Office 365 GCC 환경

- 52.112.0.0 /14(52.112.0.1에서 52.115.255.254까지의 IP 주소)

## <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 환경

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC 높은 환경

- 52.127.88.0/21


Teams 전송 릴레이의 포트 범위(모든 환경에 적용 가능)는 다음 표에 나와 있습니다.


| 트래픽 | 보낸 사람 | 받는 사람 | 원본 포트 | 대상 포트|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | 전송 릴레이 | SBC | 50 000 -59 999    | SBC에 정의 |
| UDP/SRTP | SBC | 전송 릴레이 | SBC에 정의 | 50 000 – 59 999, 3478, 3479     |


> [!NOTE]
> Microsoft는 SBC에서 동시 호출당 두 개 이상의 포트를 권장합니다. Microsoft에는 전송 릴레이의 두 가지 버전이 있기 때문에 다음이 필요합니다.
> 
> - v4, 포트 범위 50 000에서 59 999로만 작업할 수 있습니다.
> 
> - 포트 3478, 3479와 함께 작동하는 v6

현재 미디어 우회는 v4 버전의 전송 릴레이만 지원합니다. 향후 v6의 지원을 소개하겠습니다. 

전환을 위해 포트 3478 및 3479를 열어야 합니다. Microsoft에서 Media Bypass를 통해 v6 전송 릴레이에 대한 지원을 소개하는 경우 네트워크 장비 또는 SBC를 다시 구성할 필요가 없습니다. 

### <a name="requirements-for-using-media-processors"></a>미디어 프로세서 사용에 대한 요구 사항

미디어 프로세서는 항상 음성 애플리케이션 및 웹 클라이언트(예: Edge 또는 Google Chrome의 Teams 클라이언트)에 대한 미디어 경로에 있습니다. 요구 사항은 비우회 구성과 동일합니다.


미디어 트래픽의 IP 범위는 

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365 및 Office 365 GCC 환경

- 52.112.0.0 /14(52.112.0.1에서 52.115.255.254까지의 IP 주소)

## <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 환경

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC 높은 환경

- 52.127.88.0/21

Media Processor의 포트 범위(모든 환경에 적용 가능)는 다음 표에 나와 있습니다.

| 트래픽 | 보낸 사람 | 받는 사람 | 원본 포트 | 대상 포트|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | 미디어 프로세서 | SBC | 3478, 3479 및 49 152 – 53 247    | SBC에 정의 |
| UDP/SRTP | SBC | 미디어 프로세서 | SBC에 정의 | 3478, 3479 및 49 152 – 53 247     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a>미디어 우회 및 비미디어 우회에 대한 별도의 트렁크 구성  

비미디어 우회에서 미디어 우회로로 마이그레이션하고 모든 사용량을 미디어 우회로로 마이그레이션하기 전에 기능을 확인하려는 경우 별도의 트렁크 및 별도의 온라인 음성 라우팅 정책을 만들어 미디어 우회 트렁크로 라우팅하고 특정 사용자에게 할당할 수 있습니다. 

고급 구성 단계:

- 미디어 우회를 테스트할 사용자를 식별합니다.

- 서로 다른 FQDNS를 사용하여 두 개의 별도의 트렁크를 만들 수 있습니다. 미디어 우회에 사용하도록 설정되어 있습니다. 다른 것은 안 습니다. 

  두 트렁크는 모두 동일한 SBC를 지적합니다. TLS SIP 신호에 대한 포트는 다를 수 있어야 합니다. 미디어의 포트는 동일해야 합니다.

- 새 온라인 음성 라우팅 정책을 만들고 이 정책에 대한 PSTN 사용과 관련된 해당 경로에 미디어 우회 트렁크를 할당합니다.

- 미디어 우회를 테스트하기 위해 식별한 사용자에게 새 온라인 음성 라우팅 정책을 할당합니다.

아래 예제에서는 이 논리를 보여 주는 것입니다.

| 사용자 집합 | 사용자 수 | OVRP에 할당된 트렁크 FQDN | 미디어 우회 사용 |
| :------------ |:----------------- |:--------------|:--------------|
미디어가 아닌 우회 트렁크가 있는 사용자 | 980 | sbc1.contoso.com:5060 | true
미디어 우회 트렁크가 있는 사용자 | 20 | sbc2.contoso.com:5061 | false | 

두 트렁크 모두 동일한 공용 IP 주소가 있는 동일한 SBC를 지적할 수 있습니다. SBC의 TLS 신호 포트는 다음 다이어그램과 같이 다를 수 있어야 합니다. 인증서가 두 트렁크를 모두 지원하는지 확인해야 합니다. SAN에서 두 개의 이름(sbc1.contoso.com 및 **sbc2.contoso.com)** 또는 와일드카드 인증서가 필요합니다.

> [!div class="mx-imgBorder"]
> ![두 트렁크가 동일한 공용 IP를 사용하여 동일한 SBC를 지적할 수 있는 표시](media/direct-routing-media-bypass-7.png)

동일한 SBC에서 두 개의 트렁크를 구성하는 방법에 대한 자세한 내용은 SBC 공급업체에서 제공하는 설명서를 참조하세요.

 - [AudioCodes 배포 설명서](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle 배포 설명서](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [리본 통신 배포 설명서](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-Systems(anynode) 배포 설명서](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a>미디어 우회로 지원되는 클라이언트 엔드포인트

미디어 우회는 모든 독립 실행형 Teams 데스크톱 클라이언트, Android 및 iOS 클라이언트 및 Teams Phone 디바이스에서 지원됩니다. 

미디어 우회를 지원하지 않는 다른 모든 엔드포인트의 경우 우회 호출로 시작된 경우에도 호출을 비우회로 변환합니다. 이 작업은 자동으로 수행되며 관리자의 작업이 필요하지 않습니다. 여기에는 비즈니스용 Skype 3PIP 휴대폰 및 직접 라우팅 호출을 지원하는 Teams 웹 클라이언트(Microsoft Edge, Google Chrome, Mozilla Firefox에서 실행되는 WebRTC 기반 클라이언트)가 포함됩니다. 
 
## <a name="see-also"></a>참고 항목

[직접 라우팅을 위한 미디어 바이패스 구성](direct-routing-configure-media-bypass.md)


