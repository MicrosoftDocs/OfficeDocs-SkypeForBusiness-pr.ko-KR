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
description: 미디어 트래픽 경로를 줄이고 성능을 향상 시킬 수 있는 휴대폰 시스템 다이렉트 라우팅과 함께 미디어 바이패스를 계획 하는 방법에 대해 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cabbfd62ecc1a86d6e893d8d26ecdbe6cbbe7dbb
ms.sourcegitcommit: 51d94d621e3411f35622e852b699275f526600dd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2020
ms.locfileid: "48469584"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a>직접 라우팅을 위한 미디어 바이패스 계획

## <a name="about-media-bypass-with-direct-routing"></a>다이렉트 라우팅으로 미디어 바이패스 정보

미디어 바이패스를 통해 미디어 트래픽 경로를 줄이고, 더 나은 성능을 위해 전송 하는 홉 수를 줄일 수 있습니다. 미디어 바이패스를 사용 하 여 미디어는 Microsoft 전화 시스템을 통해 전송 되는 대신 SBC (세션 경계 컨트롤러)와 클라이언트 간에 유지 됩니다. 미디어 바이패스를 구성 하려면 SBC 및 클라이언트가 같은 위치 또는 네트워크에 있어야 합니다.

**-MediaBypass** 매개 변수가 true 또는 false로 설정 된 **set-CSOnlinePSTNGateway** 명령을 사용 하 여 각 SBC에 대 한 미디어 바이패스를 제어할 수 있습니다. 미디어 바이패스를 사용 하도록 설정 하면 모든 미디어 트래픽이 회사 네트워크 내에 유지 된다는 의미는 아닙니다. 이 문서에서는 다양 한 시나리오의 통화 흐름에 대해 설명 합니다.    

아래 다이어그램은 미디어 바이패스와 함께 통화 흐름의 차이점을 보여 줍니다.

미디어 바이패스 없이 클라이언트가 다음 다이어그램과 같이 SBC, Microsoft 전화 시스템, 팀 클라이언트 간의 신호 및 미디어 흐름을 모두 호출 하거나 수신할 때 다음을 수행 합니다.

> [!div class="mx-imgBorder"]
> ![미디어 바이패스 없이 신호 및 미디어 흐름 표시](media/direct-routing-media-bypass-1.png)


사용자가 SBC와 같은 건물이 나 네트워크상에 있다고 가정 합니다. 예를 들어 Frankfurt에서 빌드하는 사용자가 PSTN 사용자에 게 전화를 거는 것으로 가정 합니다. 

- **미디어를 우회 하지 않으면**미디어는 암스테르담 또는 더블린 (Microsoft 데이터 센터가 배포 된 위치)를 통해 FRANKFURT의 SBC로 다시 흐릅니다. 

  이 SBC는 유럽에 있으며, Microsoft는 SBC에 가장 가까운 데이터 센터를 사용 하므로 유럽의 데이터 센터가 선택 됩니다. 이 접근 방식은 대부분의 지역에서 Microsoft 네트워크 내의 트래픽 흐름 최적화로 인해 통화 품질에 영향을 주지는 않지만 소통량이 불필요 한 루프를가지고 있습니다.     

- **미디어 바이패스를 사용**하는 경우 미디어는 다음 다이어그램에 표시 된 대로 팀 사용자와 SBC 간에 직접 유지 됩니다.

  > [!div class="mx-imgBorder"]
  > ![미디어 우회를 사용 하 여 신호 및 미디어 흐름 표시](media/direct-routing-media-bypass-2.png)

미디어 바이패스는 팀 클라이언트 및 SBC의 ICE lite에 있는 ICE (대화형 연결 설정) 프로토콜을 활용 합니다. 이러한 프로토콜은 최적의 음질을 위해 직접 라우팅이 가장 직접적인 미디어 경로를 사용할 수 있도록 합니다. ICE 및 얼음 Lite는 WebRTC 표준입니다. 이러한 프로토콜에 대 한 자세한 내용은 RFC 5245을 참조 하세요.


## <a name="call-flow-and-firewall-planning"></a>통화 흐름 및 방화벽 계획

통화 흐름 및 방화벽 계획은 사용자가 SBC의 공용 IP 주소에 직접 액세스 했는지 여부와 네트워크 내부 또는 외부에 있는지 여부에 따라 달라 집니다.

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a>사용자가 SBC의 공용 IP 주소에 직접 액세스 하는 경우의 호출 흐름

사용자가 SBC의 공용 IP 주소에 직접 액세스 하는 경우 통화 흐름은 다음과 같습니다.

- 미디어 바이패스의 경우 팀 클라이언트는 내부 네트워크 에서도 SBC의 공용 IP 주소에 액세스할 수 있어야 합니다. 직접 미디어를 원하지 않는 경우에는 전송 릴레이를 통해 미디어를 이동할 수 있습니다.

- 사용자가 SBC와 동일한 건물 및/또는 네트워크에 있는 경우 미디어 경로에서 Microsoft 클라우드 구성 요소를 제거 하는 것이 권장 되는 해결 방법입니다.

- 신호는 항상 Microsoft 클라우드를 통해 흐릅니다.

다음 다이어그램에서는 미디어 바이패스를 사용 하도록 설정 하 고 클라이언트는 내부 이며 클라이언트는 SBC의 공용 IP 주소 (직접 미디어)에 도달할 수 있습니다. 

- 경로의 화살표 및 숫자 값은 [Microsoft 팀의 통화 흐름](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)에 따라 이동 합니다.

- SIP 신호는 항상 경로 4 및 4를 받습니다 (트래픽 방향에 따라 다름). 미디어는 로컬에서 유지 되 고 경로 5b를 차지 합니다.

> [!div class="mx-imgBorder"]
> ![미디어 바이패스를 사용 하도록 설정 하 고 클라이언트가 내부 인 통화 흐름 표시](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a>사용자에 게 SBC의 공용 IP 주소에 대 한 액세스 권한이 없는 경우의 통화 흐름

다음은 사용자에 게 SBC의 공용 IP 주소에 대 한 액세스 권한이 없는 경우의 호출 흐름에 대 한 설명입니다. 

예를 들어 사용자가 외부에 있고 테 넌 트 관리자가 인터넷의 모든 사용자에 게 SBC의 공용 IP 주소를 열지 않기로 결정 한 경우에만 Microsoft Cloud로 간주 됩니다. 트래픽 내부 구성 요소는 팀 전송 릴레이를 통해 흐를 수 있습니다. 다음과 같은 사항을 고려해야 합니다.

- 팀 전송 릴레이를 사용 합니다.

- 미디어 바이패스의 경우 Microsoft는 팀 전송 릴레이와 SBC 간에 포트 50 000을 59 999으로 열어야 하는 전송 릴레이 버전을 사용 합니다 (앞으로는 3478 및 3479 포트만 필요로 하는 버전으로 이동 하려고 함).


다음 다이어그램에서는 미디어 바이패스를 사용 하도록 설정 하 고 클라이언트는 외부에 있으며 클라이언트가 세션 경계 컨트롤러의 공용 IP 주소에 연결할 수 없습니다 (미디어가 팀 전송 릴레이에 의해 릴레이 됨).

- 경로의 화살표 및 숫자 값은 [Microsoft 팀의 통화 흐름](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)에 따라 이동 합니다.

- 미디어는 경로 3, 3, 4, 4를 통해 릴레이 됩니다.

> [!div class="mx-imgBorder"]
> ![사용자가 SBC의 공용 IP에 액세스할 수 없는 경우 통화 흐름 표시](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a>사용자가 네트워크 외부에 있고 SBC의 공용 IP에 대 한 액세스 권한이 있는 경우의 통화 흐름

> [!NOTE]
> 이 구성은 팀 전송 릴레이를 이용 하지 않으므로 권장 되지 않습니다. 대신 사용자에 게 SBC의 공용 IP 주소에 대 한 액세스 권한이 없는 이전 시나리오를 고려해 야 합니다. 

다음 다이어그램은 미디어 바이패스를 사용 하도록 설정 하 고 클라이언트가 외부에 있는 경우 클라이언트는 SBC의 공용 IP 주소 (직접 미디어)에 도달할 수 있는 경우의 통화 흐름을 보여 줍니다.

- 경로의 화살표 및 숫자 값은 [Microsoft 팀의 통화 흐름](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) 문서에 따라 이동 합니다.

- SIP 신호는 항상 경로 3 및 3을 받습니다 (트래픽 방향에 따라 다름). 경로 2를 사용 하는 미디어 흐름

> [!div class="mx-imgBorder"]
> ![사용자가 SBC의 공용 IP에 액세스할 수 없는 경우 통화 흐름 표시](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a>미디어 프로세서 및 전송 릴레이 사용

미디어 트래픽 경로에 있을 수 있는 Microsoft 클라우드의 두 가지 구성 요소 (미디어 프로세서와 전송 릴레이)가 있습니다. 

- 미디어 프로세서는 비 바이패스 케이스에서 미디어를 처리 하 고 음성 응용 프로그램의 미디어를 처리 하는 공용 지향 구성 요소입니다.

   미디어 프로세서는 항상 최종 사용자가 무시할 수 없는 호출에 대 한 경로에 있지만 건너뛸 때는이 경로에 없습니다. 미디어 프로세서는 항상 통화 공원, 조직 자동 전화 교환, 통화 대기열 등의 모든 음성 응용 프로그램에 대 한 경로에 있습니다.

- 전송 릴레이는 실시간 트래픽을 보내기 위해 가장 가까운 전송 서비스에 연결 하는 데 사용 됩니다.

   전송 릴레이는 사용자가 어디에 있고 네트워크를 구성 하는 방법에 따라, 최종 사용자가 시작 하거나 대상으로 하는 호출 경로에 있을 수도 있고 그렇지 않을 수도 있습니다.

다음 다이어그램은 미디어 바이패스를 사용 하도록 설정 하 고 두 번째는 미디어 바이패스를 사용 하지 않는 두 가지 호출 흐름을 보여 줍니다. 참고 다이어그램은--또는로 보내는 사용자의 트래픽만 보여 줍니다.  
- 미디어 컨트롤러는 미디어 프로세서를 할당 하 고 SDP (세션 설명 프로토콜) 제공을 만드는 Azure의 microservice입니다.

- SIP 프록시는 팀에서 사용 되는 HTTP REST 신호를 SIP로 변환 하는 구성 요소입니다.    

> [!div class="mx-imgBorder"]
> ![미디어 바이패스 사용 및 사용 안 함이 설정 된 통화 흐름 표시](media/direct-routing-media-bypass-6.png)


아래 표에는 미디어 프로세서와 전송 릴레이의 차이점에 대 한 요약이 나와 있습니다.

|    | 미디어 프로세서 | 전송 릴레이|
| :--------------|:---------------|:------------|
최종 사용자에 대 한 무시할 수 없는 통화에 대 한 미디어 경로 | Always | 열리지 | 
최종 사용자에 대 한 바이패스 전화의 미디어 경로 | 열리지 | 클라이언트가 공용 IP 주소의 SBC에 연결할 수 없는 경우 | 
음성 응용 프로그램용 미디어 경로 | Always | 열리지 | 
코드 변환 가능 (B2BUA)\* | 예 | 아니요, 끝점 간 오디오만 릴레이 합니다. | 
전세계 인스턴스 수 및 위치 | 총 10 개: 미국 동부와 서쪽의 2 # 암스테르담 및 더블린의 경우 2 홍콩 및 싱가포르의 2 일본의 2 오스트레일리아 동쪽 및 남동쪽의 2 | 개인

IP 범위는 다음과 같습니다.
- 52.112.0.0/14 (IP 주소 52.112.0.1-52.115.255.254)
- 52.120.0.0/14 (IP 주소 52.120.0.1-52.123.255.254)

\* 코드 변환 설명: 

- 미디어 프로세서는 B2BUA, 즉, 코덱 (예: 팀 클라이언트에서 MP 및 SILK에 대 한 711 간)을 변경할 수 있다는 것을 의미 합니다.

- 전송 릴레이는 B2BUA 되지 않으므로 클라이언트와 SBC 간에 코덱이 변경 되지 않음을 의미 합니다--릴레이를 통해 트래픽이 흐름을 진행 하는 경우에도 마찬가지입니다.

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a>미디어 바이패스를 위해 트렁크가 구성 된 경우 팀 미디어 프로세서 사용

팀 미디어 프로세서는 항상 다음과 같은 시나리오에서 미디어 경로에 삽입 됩니다.

- 1:1에서 그룹 통화로 통화 에스컬레이션
- 연결이 페더레이션된 팀 사용자에 게 방문
- 비즈니스용 Skype 사용자에 게 착신 전환 또는 전송

SBC에 아래 설명 된 대로 미디어 프로세서 및 트랜스포트 릴레이 범위에 대 한 액세스 권한이 있는지 확인 합니다.    


## <a name="sip-signaling-fqdns"></a>SIP 신호: Fqdn

SIP 신호를 위해 FQDN 및 방화벽 요구 사항은 무시할 수 없는 경우와 동일 합니다. 

직접 라우팅은 다음 Microsoft 365 또는 Office 365 환경에서 제공 됩니다.
- Microsoft 365 또는 Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD, gcc, GCC High, DoD 등의 [office 365 및 US 정부 환경](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) 에 대해 자세히 알아보세요.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365, Office 365 및 Office 365 GCC 환경

직접 라우팅의 연결 지점은 다음 세 가지 Fqdn입니다.

- **sip.pstnhub.microsoft.com** – 전역 FQDN – 먼저 시도해 야 합니다. SBC에서이 이름을 확인 하는 요청을 보낼 때 Microsoft Azure DNS 서버는 SBC에 할당 된 기본 Azure 데이터 센터를 가리키는 IP 주소를 반환 합니다. 과제는 데이터 센터의 성과 메트릭과 SBC에 대 한 지리적 근접성을 기준으로 합니다. 반환 되는 IP 주소는 기본 FQDN에 해당 합니다.

- **sip2.pstnhub.microsoft.com** – 보조 FQDN – 지리적으로 두 번째 우선 순위 영역으로 매핑됩니다.

- **sip3.pstnhub.microsoft.com** – 세 번째 FQDN – 지리적으로 세번째 우선 순위 영역을 매핑합니다.

다음을 수행 하려면 이러한 세 가지 Fqdn을 배치 해야 합니다.

- 최적의 환경을 제공 합니다 (첫 번째 FQDN을 쿼리하면 지정 된 SBC 데이터 센터에 가장 가깝습니다).

- 일시적인 문제가 발생 하는 데이터 센터에 SBC의 연결이 설정 된 경우 장애 조치를 제공 합니다. 자세한 내용은 아래의 장애 조치 메커니즘을 참조 하세요.


Fqdn **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**및 **sip3.pstnhub.microsoft.com** 는 다음 IP 주소 중 하나로 확인 됩니다.
- 52.114.148.0
- 52.114.132.46
- 52.114.16.74
- 52.114.20.29
- 52.114.75.24
- 52.114.76.76
- 52.114.7.24
- 52.114.14.70

수신 및 송신 트래픽을 주소에서 주고 받을 수 있도록 방화벽에서 이러한 모든 IP 주소에 대해 포트를 열어야 합니다. 방화벽이 DNS 이름을 지 원하는 경우 FQDN **sip-all.pstnhub.microsoft.com** 이러한 모든 IP 주소를 확인 합니다. 

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 환경

직접 라우팅의 연결 지점은 다음 FQDN입니다.

**sip.pstnhub.dod.teams.microsoft.us** – 전역 FQDN. Office 365 DoD 환경은 미국 데이터 센터에만 있으므로 2 차 및 3 차 Fqdn이 없습니다.

Fqdn – sip.pstnhub.dod.teams.microsoft.us는 다음 IP 주소 중 하나로 확인 됩니다.

- 52.127.64.33
- 52.127.68.34

수신 및 송신 트래픽을 주소에서 주고 받을 수 있도록 방화벽에서 이러한 모든 IP 주소에 대해 포트를 열어야 합니다.  방화벽이 DNS 이름을 지 원하는 경우 FQDN sip.pstnhub.dod.teams.microsoft.us 이러한 모든 IP 주소를 확인 합니다. 

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High 환경

직접 라우팅의 연결 지점은 다음 FQDN입니다.

**sip.pstnhub.gov.teams.microsoft.us** – 전역 FQDN. GCC High 환경은 US 데이터 센터에만 존재 하므로 2 차 및 3 차 Fqdn이 없습니다.

Fqdn – sip.pstnhub.gov.teams.microsoft.us는 다음 IP 주소 중 하나로 확인 됩니다.

- 52.127.88.59
- 52.127.92.64

수신 및 송신 트래픽을 주소에서 주고 받을 수 있도록 방화벽에서 이러한 모든 IP 주소에 대해 포트를 열어야 합니다.  방화벽이 DNS 이름을 지 원하는 경우 FQDN sip.pstnhub.gov.teams.microsoft.us 이러한 모든 IP 주소를 확인 합니다. 

## <a name="sip-signaling-ports"></a>SIP 신호: 포트

포트 요구 사항은 직접 라우팅이 제공 되는 모든 Office 365 환경에 대해 동일 합니다.
- Microsoft 365 또는 Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

다음 포트를 사용 해야 합니다.

| 통신량 | 보낸 사람 | 받는 사람 | 원본 포트 | 대상 포트|
| :-------- | :-------- |:-----------|:--------|:---------|
SIP/TLS| SIP 프록시 | 하더라도 | 1024-65535 | SBC에 정의 됨 |
| SIP/TLS | 하더라도 | SIP 프록시 | SBC에 정의 됨 | 5061 |


## <a name="media-traffic-ip-and-port-ranges"></a>미디어 트래픽: IP 및 포트 범위

클라이언트가 공용 IP 주소를 사용 하 여 SBC에 연결할 수 없는 경우 직접 연결을 사용할 수 있거나 팀을 통해 전송 되는 경우에는 SBC 및 팀 클라이언트 간 미디어 소통량이 흐릅니다.

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a>직접 미디어 트래픽 (팀 클라이언트와 SBC 간)에 대 한 요구 사항 

클라이언트는 SBC의 공용 IP 주소에 지정 된 포트 (표 참조)에 액세스할 수 있어야 합니다. 

참고: 클라이언트가 내부 네트워크에 있는 경우 미디어는 SBC의 공용 IP 주소로 흐릅니다. NAT 장치에서 헤어 고정을 구성할 수 있으므로 트래픽이 기업 네트워크 장비를 떠나는 일은 없습니다.

| 통신량 | 보낸 사람 | 받는 사람 | 원본 포트 | 대상 포트|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | 클라이언트 | 하더라도 | 50 000 – 50 019  | SBC에 정의 됨 |
| UDP/SRTP | 하더라도 | 클라이언트 | SBC에 정의 됨 | 50 000 – 50 019  |


> [!NOTE]
> 클라이언트의 원본 포트를 변환 하는 네트워크 장치가 있는 경우 네트워크 장비와 SBC 사이에 변환 된 포트가 열려 있는지 확인 하세요. 

### <a name="requirements-for-using-transport-relays"></a>전송 릴레이를 사용 하기 위한 요구 사항

전송 릴레이는 미디어 프로세서와 같은 범위에 있습니다 (바이패스 이외의 경우). 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365, Office 365 및 Office 365 GCC 환경

- 52.112.0.0/14 (IP 주소 52.112.0.1-52.115.255.254)

## <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 환경

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High 환경

- 52.127.88.0/21


모든 환경에 적용 되는 팀 전송 릴레이의 포트 범위는 다음 표에 나와 있습니다.


| 통신량 | 보낸 사람 | 받는 사람 | 원본 포트 | 대상 포트|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | 전송 릴레이 | 하더라도 | 50 000-59 999    | SBC에 정의 됨 |
| UDP/SRTP | 하더라도 | 전송 릴레이 | SBC에 정의 됨 | 50 000-59 999, 3478, 3479     |


> [!NOTE]
> Microsoft는 SBC에서 동시에 포트를 두 개 이상 사용할 것을 권장 합니다. Microsoft에는 두 가지 버전의 전송 중계이 있기 때문에 다음이 필요 합니다.
> 
> - v4-포트 범위 50 000 ~ 59 999에만 작동할 수 있습니다.
> 
> - 포트 3478, 3479에서 작동 하는 v6

현재 미디어 바이패스는 v4 버전의 전송 릴레이만 지원 합니다. 앞으로 v6에 대 한 지원을 제공 합니다. 

전환을 위해 포트 3478 및 3479을 열어야 합니다. Microsoft에서 미디어 바이패스를 사용 하 여 v6 전송 릴레이에 대 한 지원을 도입 하는 경우 네트워크 장비 또는 SBCs를 다시 구성할 필요가 없습니다. 

### <a name="requirements-for-using-media-processors"></a>미디어 프로세서 사용에 대 한 요구 사항

미디어 프로세서는 항상 음성 응용 프로그램과 웹 클라이언트 (예: Edge 또는 Google Chrome의 팀 클라이언트)에 대 한 미디어 경로에 있습니다. 요구 사항은 비 바이패스 구성의 경우와 동일 합니다.


미디어 트래픽 IP 범위는 

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365 및 Office 365 GCC 환경

- 52.112.0.0/14 (IP 주소 52.112.0.1-52.115.255.254)

## <a name="office-365-gcc-dod-environment"></a>Office 365 GCC DoD 환경

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High 환경

- 52.127.88.0/21

모든 환경에 적용 되는 미디어 프로세서의 포트 범위는 다음 표에 나와 있습니다.

| 통신량 | 보낸 사람 | 받는 사람 | 원본 포트 | 대상 포트|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | 미디어 프로세서 | 하더라도 | 3478, 3479, 49 152-53 247    | SBC에 정의 됨 |
| UDP/SRTP | 하더라도 | 미디어 프로세서 | SBC에 정의 됨 | 3478, 3479, 49 152-53 247     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a>미디어 우회 및 비 미디어 바이패스에 대해 별도의 trunks 구성  

미디어를 우회 하 여 미디어 바이패스로 마이그레이션하고 기능을 확인 하기 위해 미디어 바이패스로 모든 사용량을 마이그레이션하기 전에 별도의 트렁크와 별도의 온라인 음성 라우팅 정책을 만들어 미디어를 우회 하 고 특정 사용자에 게 할당할 수 있습니다. 

상위 수준 구성 단계:

- 미디어 바이패스를 테스트할 사용자를 식별 합니다.

- 다른 Fqdn을 사용 하 여 별도의 trunks를 만듭니다 (미디어 바이패스에 사용 가능). 그렇지 않습니다. 

  두 trunks 모두 동일한 SBC를 가리킵니다. TLS SIP 신호에 대 한 포트는 달라 야 합니다. 미디어의 포트는 동일 해야 합니다.

- 새 온라인 음성 라우팅 정책을 만들고 미디어 우회 트렁크를이 정책의 PSTN 사용과 관련 된 해당 경로에 할당 합니다.

- 미디어 바이패스를 테스트 하도록 확인 한 사용자에 게 새 온라인 음성 라우팅 정책을 할당 합니다.

아래 예제에서는이 논리를 보여 줍니다.

| 사용자 집합 | 사용자 수 | OVRP에 할당 된 트렁크 FQDN | 미디어 바이패스 사용 |
| :------------ |:----------------- |:--------------|:--------------|
비 미디어 우회 트렁크를 사용 하는 사용자 | 980 | sbc1.contoso.com:5060 | false
미디어를 우회 하는 사용자 | 명 | sbc2.contoso.com:5061 | 해제 | 

두 trunks 모두 동일한 공용 IP 주소를 사용 하 여 동일한 SBC를 가리킬 수 있습니다. SBC의 TLS 신호 포트는 다음 다이어그램에 표시 된 것과 같이 달라 야 합니다. 참고 인증서가 두 trunks를 모두 지원 하는지 확인 해야 합니다. SAN에는 두 개의 이름 (**sbc1.contoso.com** 및 **sbc2.contoso.com**)이 있거나 와일드 카드 인증서가 있어야 합니다.

> [!div class="mx-imgBorder"]
> ![두 trunks 모두 동일한 공용 IP를 사용 하 여 동일한 SBC를 가리킬 수 있는지 표시 합니다.](media/direct-routing-media-bypass-7.png)

동일한 SBC에서 두 개의 trunks를 구성 하는 방법에 대 한 자세한 내용은 SBC 공급 업체에서 제공 하는 설명서를 참조 하세요.

 - [오디오 코드 배포 설명서](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle 배포 문서](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [리본 커뮤니케이션 배포 문서](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-시스템 (anynode) 배포 문서](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a>미디어 바이패스에서 지원 되는 클라이언트 끝점

미디어 바이패스는 모든 팀 데스크톱 클라이언트 및 팀 전화 장치에서 지원 됩니다. 

미디어 바이패스를 지원 하지 않는 다른 모든 끝점의 경우 건너뛰기 호출로 시작 된 경우에도 통화가 비 바이패스로 변환 됩니다. 이는 자동으로 수행 되며 관리자의 작업이 필요 하지 않습니다. 여기에는 비즈니스용 Skype 3PIP 휴대폰 및 다이렉트 라우팅 통화를 지 원하는 팀 웹 클라이언트 (Chromium, Google Chrome을 기반으로 하는 새로운 Microsoft Edge)가 포함 됩니다. 
 
## <a name="see-also"></a>참고 항목

[직접 라우팅을 위한 미디어 바이패스 구성](direct-routing-configure-media-bypass.md)


