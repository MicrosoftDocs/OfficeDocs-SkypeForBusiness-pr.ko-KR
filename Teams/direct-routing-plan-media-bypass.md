---
title: 직접 라우팅을 위한 미디어 바이패스 계획
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 미디어 트래픽 경로를 단축하고 성능을 향상시킬 수 있는 전화 시스템 직접 라우팅을 사용하여 미디어 바이패스를 계획하는 방법을 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 638a39a843648ab8fab770c28d92b196201e20f5
ms.sourcegitcommit: c627bd1df17aefdc353bc4da6db169dfe169031e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2022
ms.locfileid: "68680511"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a>직접 라우팅을 위한 미디어 바이패스 계획

## <a name="about-media-bypass-with-direct-routing"></a>직접 라우팅을 사용하여 미디어 바이패스 정보

미디어 바이패스를 사용하면 더 나은 성능을 위해 미디어 트래픽 경로를 단축하고 전송 중인 홉 수를 줄일 수 있습니다. 미디어 바이패스로 미디어는 Microsoft 전화 시스템을 통해 전송하는 대신 SBC(세션 테두리 컨트롤러)와 클라이언트 간에 유지됩니다. 미디어 바이패스 구성을 위해 SBC와 클라이언트는 동일한 위치 또는 네트워크에 있어야 합니다.

**-MediaBypass** 매개 변수가 true 또는 false로 설정된 **Set-CSOnlinePSTNGateway** 명령을 사용하여 각 SBC에 대한 미디어 바이패스를 제어할 수 있습니다. 미디어 바이패스(media bypass)를 사용하도록 설정한다고 해서 모든 미디어 트래픽이 회사 네트워크 내에 유지된다는 의미는 아닙니다. 이 문서에서는 다양한 시나리오의 호출 흐름에 대해 설명합니다.

아래 다이어그램은 미디어 바이패스를 사용 및 사용하지 않는 통화 흐름의 차이를 보여 줍니다.

미디어 바이패스가 없으면 클라이언트가 전화를 걸거나 받을 때 다음 다이어그램과 같이 SBC, Microsoft Phone System 및 Teams 클라이언트 간에 신호 및 미디어 흐름이 모두 전달됩니다.

> [!div class="mx-imgBorder"]
> ![미디어 바이패스 없이 신호 및 미디어 흐름을 표시합니다.](media/direct-routing-media-bypass-1.png)


그러나 사용자가 SBC와 동일한 건물 또는 네트워크에 있다고 가정해 보겠습니다. 예를 들어 프랑크푸르트의 건물에 있는 사용자가 PSTN 사용자를 호출하는 경우를 가정합니다. 

- **미디어 바이패스 없이** 미디어는 암스테르담 또는 더블린(Microsoft 데이터 센터가 배포된 위치)을 통해 프랑크푸르트의 SBC로 돌아갑니다. 

  SBC가 유럽에 있고 Microsoft에서 SBC와 가장 가까운 데이터 센터를 사용하므로 유럽의 데이터 센터가 선택됩니다. 이 방법은 대부분의 지역에서 Microsoft 네트워크 내의 트래픽 흐름 최적화로 인해 통화 품질에 영향을 주지 않지만 트래픽에는 불필요한 루프가 있습니다.     

- **미디어 바이패** 스로 미디어는 다음 다이어그램과 같이 Teams 사용자와 SBC 간에 직접 유지됩니다.

  > [!div class="mx-imgBorder"]
  > ![미디어 바이패스로 신호 및 미디어 흐름을 표시합니다.](media/direct-routing-media-bypass-2.png)

미디어 바이패스는 Teams 클라이언트에서 ICE(Interactive Connectivity Establishment)라는 프로토콜을 활용하고 SBC의 ICE 라이트를 활용합니다. 이러한 프로토콜을 사용하면 직접 라우팅이 최적의 품질을 위해 가장 직접적인 미디어 경로를 사용할 수 있습니다. ICE 및 ICE Lite는 WebRTC 표준입니다. 이러한 프로토콜에 대한 자세한 내용은 RFC 5245를 참조하세요.


## <a name="call-flow-and-firewall-planning"></a>통화 흐름 및 방화벽 계획

통화 흐름 및 방화벽 계획은 사용자가 SBC의 공용 IP 주소에 직접 액세스할 수 있는지 여부와 사용자가 네트워크 내부 또는 외부에 있는지 여부에 따라 달라집니다.

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a>사용자가 SBC의 공용 IP 주소에 직접 액세스할 수 있는 경우 흐름 호출

사용자가 SBC의 공용 IP 주소에 직접 액세스할 수 있는 경우 호출 흐름은 다음과 같습니다.

- 미디어 바이패스의 경우 Teams 클라이언트는 내부 네트워크에서도 SBC의 공용 IP 주소에 액세스할 수 있어야 합니다. 직접 미디어를 원하지 않는 경우 전송 릴레이를 통해 미디어가 흐를 수 있습니다.

- 사용자가 SBC와 동일한 건물 및/또는 네트워크에 있는 경우 미디어 경로에서 Microsoft 클라우드 구성 요소를 제거하는 것이 좋습니다.

- 신호는 항상 Microsoft 클라우드를 통해 전달됩니다.

다음 다이어그램은 미디어 바이패스가 활성화되고 클라이언트가 내부이며 클라이언트가 SBC(직접 미디어)의 공용 IP 주소에 도달할 수 있는 경우의 호출 흐름을 보여 줍니다. 

- 경로의 화살표 및 숫자 값은 [Microsoft Teams 호출 흐름에 따라 결정됩니다](./microsoft-teams-online-call-flows.md).

- SIP 신호는 항상 경로 4와 4'(트래픽 방향에 따라 다름)를 사용합니다. 미디어는 로컬로 유지되며 5b 경로를 사용합니다.

> [!div class="mx-imgBorder"]
> ![미디어 바이패스 사용이 설정된 통화 흐름을 표시하고 클라이언트는 내부입니다.](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a>사용자가 SBC의 공용 IP 주소에 액세스할 수 없는 경우 흐름 호출

다음은 사용자가 SBC의 공용 IP 주소에 액세스할 수 없는 경우의 호출 흐름에 대해 설명합니다. 

예를 들어 사용자가 외부에 있고 테넌트 관리자가 SBC의 공용 IP 주소를 인터넷의 모든 사용자에게 열지 않고 Microsoft 클라우드로만 열기로 결정했다고 가정합니다. 트래픽의 내부 구성 요소는 Teams 전송 릴레이를 통해 흐를 수 있습니다. 다음과 같은 사항을 고려해야 합니다.

- Teams 전송 릴레이가 사용됩니다.

- 미디어 바이패스의 경우 Microsoft는 Teams 전송 릴레이와 SBC 간에 포트 50 000~59 999를 열어야 하는 전송 릴레이 버전을 사용합니다(향후 3478-3481 포트가 필요한 버전으로 전환할 계획임).


다음 다이어그램은 미디어 바이패스가 활성화되고 클라이언트가 외부에 있고 클라이언트가 세션 테두리 컨트롤러의 공용 IP 주소에 도달할 수 없는 경우의 통화 흐름을 보여 줍니다(미디어는 Teams 전송 릴레이에 의해 릴레이됨).

- 경로의 화살표 및 숫자 값은 [Microsoft Teams 호출 흐름에 따라 결정됩니다](./microsoft-teams-online-call-flows.md).

- 미디어는 경로 3, 3', 4 및 4'를 통해 릴레이됩니다.

> [!div class="mx-imgBorder"]
> ![사용자가 SBC의 공용 IP에 액세스할 수 없는 경우 통화 흐름을 표시합니다.](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a>사용자가 네트워크 외부에 있고 SBC의 공용 IP에 액세스할 수 있는 경우 흐름 호출

> [!NOTE]
> Teams 전송 릴레이를 활용하지 않으므로 권장되는 구성이 아닙니다. 대신 사용자가 SBC의 공용 IP 주소에 액세스할 수 없는 이전 시나리오를 고려해야 합니다. 

다음 다이어그램은 미디어 바이패스가 활성화되고 클라이언트가 외부에 있고 클라이언트가 SBC(직접 미디어)의 공용 IP 주소에 도달할 수 있는 경우의 호출 흐름을 보여 줍니다.

- 경로의 화살표 및 숫자 값은 [Microsoft Teams 호출 흐름](./microsoft-teams-online-call-flows.md) 문서에 따라 다릅니다.

- SIP 신호는 항상 경로 3과 3'(트래픽 방향에 따라 다름)을 사용합니다. 경로 2를 사용하여 미디어 흐름

> [!div class="mx-imgBorder"]
> ![사용자가 SBC의 공용 IP에 액세스할 수 없는 경우 통화 흐름을 표시합니다.](media/direct-routing-media-bypass-5.png)



## <a name="use-of-media-processors-and-transport-relays"></a>미디어 프로세서 및 전송 릴레이 사용

Microsoft Cloud에는 미디어 트래픽 경로에 있을 수 있는 두 가지 구성 요소인 미디어 프로세서 및 전송 릴레이가 있습니다. 

- 미디어 프로세서는 비 우회 사례에서 미디어를 처리하고 음성 애플리케이션에 대한 미디어를 처리하는 공용 구성 요소입니다.

   미디어 프로세서는 항상 최종 사용자가 바이패스되지 않은 호출의 경로에 있지만 바이패스된 호출의 경로에는 없습니다. 미디어 프로세서는 항상 통화 대기, 조직 자동 전화 교환 및 통화 큐와 같은 모든 음성 애플리케이션의 경로에 있습니다.

- 전송 릴레이는 실시간 트래픽을 보내기 위해 가장 가까운 전송 서비스에 연결하는 데 사용됩니다.

   전송 릴레이는 사용자가 있는 위치와 네트워크 구성 방식에 따라 바이패스된 호출의 경로에 있거나 없을 수 있습니다.

다음 다이어그램에서는 미디어 바이패스가 사용하도록 설정된 호출 흐름과 미디어 바이패스를 사용하지 않도록 설정된 두 호출 흐름의 두 가지 호출 흐름을 보여 줍니다.

> [!NOTE]
> 이 다이어그램은 최종 사용자로부터 시작되거나 최종 사용자로 향하는 트래픽만 보여 줍니다.  

- 미디어 컨트롤러는 미디어 프로세서를 할당하고 SDP(세션 설명 프로토콜) 제품을 만드는 Azure의 마이크로 서비스입니다.

- SIP 프록시는 Teams에서 사용되는 HTTP REST 신호를 SIP로 변환하는 구성 요소입니다.    

> [!div class="mx-imgBorder"]
> ![미디어 바이패스를 사용하도록 설정하고 사용하지 않도록 설정한 통화 흐름을 표시합니다.](media/direct-routing-media-bypass-6.png)


아래 표에는 미디어 프로세서와 전송 릴레이 간의 차이점이 요약되어 있습니다.

|  &nbsp; | 미디어 프로세서 | 전송 릴레이|
| :--------------|:---------------|:------------|
|최종 사용자에 대한 바이패스되지 않은 호출에 대한 미디어 경로 | 항상 | 클라이언트가 미디어 프로세서에 직접 연결할 수 없는 경우 |
|최종 사용자에 대한 바이패스된 호출에 대한 미디어 경로 | 결코 | 클라이언트가 공용 IP 주소의 SBC에 연결할 수 없는 경우 |
|음성 애플리케이션의 미디어 경로 | 항상 | 결코 |
|코드 변환 가능(B2BUA)\* | 예 | 아니요, 엔드포인트 간에만 오디오 릴레이 |

IP 범위는 다음과 같습니다.
- 52.112.0.0/14(IP 주소는 52.112.0.1에서 52.115.255.254로)
- 52.120.0.0/14(IP 주소는 52.120.0.1에서 52.123.255.254로)

\* 코드 변환 설명: 

- 미디어 프로세서는 B2BUA입니다. 즉, 코덱을 변경할 수 있습니다(예: TEAMS 클라이언트에서 MP로 SILK, MP와 SBC 간에 G.711).

- 전송 릴레이는 B2BUA가 아닙니다. 즉, 트래픽이 릴레이를 통해 흐르는 경우에도 클라이언트와 SBC 간에 코덱이 변경되지 않습니다.

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a>트렁크가 미디어 바이패스용으로 구성된 경우 Teams 미디어 프로세서 사용

Teams 미디어 프로세서는 다음 시나리오에서 항상 미디어 경로에 삽입됩니다.

- 통화가 1:1에서 그룹 호출로 에스컬레이션됩니다.
- 페더레이션된 Teams 사용자에게 전화 걸기
- 통화가 전달되거나 비즈니스용 Skype 사용자에게 전송됩니다.

SBC가 아래에 설명된 대로 미디어 프로세서 및 전송 릴레이 범위에 액세스할 수 있는지 확인합니다.    


## <a name="sip-signaling-fqdns"></a>SIP 신호: FQDN

SIP 신호의 경우 FQDN 및 방화벽 요구 사항은 바이패스되지 않은 경우와 동일합니다. 

직접 라우팅은 다음 Microsoft 365 또는 Office 365 환경에서 제공됩니다.
- Microsoft 365 또는 Office 365
- GCC Office 365
- Office 365 GCC High
- Office 365 DoD GCC, GCC High 및 DoD[와 같은 Office 365 및 미국 정부 환경에](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) 대해 자세히 알아봅니다.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365, Office 365 및 Office 365 GCC 환경

직접 라우팅의 연결점은 다음과 같은 세 가지 FQDN입니다.

- **전역** FQDN인 sip.pstnhub.microsoft.com 먼저 시도해야 합니다. SBC가 이 이름을 확인하기 위한 요청을 보내면 Microsoft Azure DNS 서버는 SBC에 할당된 기본 Azure 데이터 센터를 가리키는 IP 주소를 반환합니다. 할당은 데이터 센터의 성능 메트릭과 SBC에 대한 지리적 근접성을 기반으로 합니다. 반환된 IP 주소는 기본 FQDN에 해당합니다.

- **sip2.pstnhub.microsoft.com** – 보조 FQDN – 지리적으로 두 번째 우선 순위 지역에 매핑됩니다.

- **sip3.pstnhub.microsoft.com** – 3차 FQDN – 지리적으로 세 번째 우선 순위 지역에 매핑됩니다.

다음 세 가지 FQDN을 배치해야 합니다.

- 최적의 환경(첫 번째 FQDN을 쿼리하여 할당된 SBC 데이터 센터에 덜 로드되고 가장 가깝음)을 제공합니다.

- SBC에서 임시 문제가 발생하는 데이터 센터에 연결할 때 장애 조치(failover)를 제공합니다. 자세한 내용은 아래의 장애 조치(failover) 메커니즘을 참조하세요.


FQDN **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com** 및 **sip3.pstnhub.microsoft.com** 다음 서브넷의 IP 주소로 확인됩니다.
- 52.112.0.0/14
- 52.120.0.0/14

신호를 위해 주소에서 들어오고 나가는 트래픽을 허용하려면 방화벽에서 이러한 모든 IP 범위에 대한 포트를 열어야 합니다.

### <a name="office-365-gcc-dod-environment"></a>GCC DoD 환경 Office 365

직접 라우팅의 연결점은 다음 FQDN입니다.

**sip.pstnhub.dod.teams.microsoft.us** – 전역 FQDN. Office 365 DoD 환경은 미국 데이터 센터에만 존재하므로 보조 및 삼차 FQDN이 없습니다.

FQDN sip.pstnhub.dod.teams.microsoft.us 다음 서브넷에서 IP 주소로 확인됩니다.

- 52.127.64.0/21

신호를 위해 주소에서 들어오고 나가는 트래픽을 허용하려면 방화벽에서 이러한 모든 IP 범위에 대한 포트를 열어야 합니다.  방화벽이 DNS 이름을 지원하는 경우 FQDN sip.pstnhub.dod.teams.microsoft.us 이러한 모든 IP 서브넷으로 확인됩니다. 

### <a name="office-365-gcc-high-environment"></a>GCC High 환경 Office 365

직접 라우팅의 연결점은 다음 FQDN입니다.

**sip.pstnhub.gov.teams.microsoft.us** – 전역 FQDN. GCC High 환경은 미국 데이터 센터에만 존재하므로 보조 및 삼차 FQDN이 없습니다.

FQDN sip.pstnhub.gov.teams.microsoft.us 다음 서브넷에서 IP 주소로 확인됩니다.

- 52.127.88.0/21

신호를 위해 주소에서 들어오고 나가는 트래픽을 허용하려면 방화벽에서 이러한 모든 IP 범위에 대한 포트를 열어야 합니다.  방화벽이 DNS 이름을 지원하는 경우 FQDN sip.pstnhub.gov.teams.microsoft.us 이러한 모든 IP 서브넷으로 확인됩니다. 

## <a name="sip-signaling-ports"></a>SIP 신호: 포트

포트 요구 사항은 직접 라우팅이 제공되는 모든 Office 365 환경에서 동일합니다.
- Microsoft 365 또는 Office 365
- GCC Office 365
- Office 365 GCC High
- Office 365 DoD

다음 포트를 사용해야 합니다.

| 트래픽을 | 보낸 사람 | 받는 사람 | 원본 포트 | 대상 포트|
| :-------- | :-------- |:-----------|:--------|:---------|
| SIP/TLS| SIP 프록시 | Sbc | 1024 - 65535 | SBC에 정의됨 |
| SIP/TLS | Sbc | SIP 프록시 | SBC에 정의됨 | 5061 |


## <a name="media-traffic-ip-and-port-ranges"></a>미디어 트래픽: IP 및 포트 범위

직접 연결을 사용할 수 있는 경우 또는 클라이언트가 공용 IP 주소를 사용하여 SBC에 연결할 수 없는 경우 Teams 전송 릴레이를 통해 SBC와 Teams 클라이언트 간에 미디어 트래픽이 흐릅니다.

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a>직접 미디어 트래픽에 대한 요구 사항(Teams 클라이언트와 SBC 간) 

클라이언트는 SBC의 공용 IP 주소에서 지정된 포트(테이블 참조)에 액세스할 수 있어야 합니다. 

> [!NOTE]
> 클라이언트가 내부 네트워크에 있는 경우 미디어는 SBC의 공용 IP 주소로 흐릅니다. 트래픽이 엔터프라이즈 네트워크 장비를 벗어나지 않도록 NAT 디바이스에서 모발 고정을 구성할 수 있습니다.

| 트래픽을 | 보낸 사람 | 받는 사람 | 원본 포트 | 대상 포트|
| :-------- | :-------- |:-----------|:--------|:---------|
| UDP/SRTP | 클라이언트 | Sbc | 50000-50019| SBC에 정의됨 |
| UDP/SRTP | Sbc | 클라이언트 | SBC에 정의됨 | 50000-50019  |


> [!NOTE]
> 클라이언트의 원본 포트를 변환하는 네트워크 디바이스가 있는 경우 네트워크 장비와 SBC 간에 변환된 포트가 열려 있는지 확인하세요. 

### <a name="requirements-for-using-transport-relays"></a>전송 릴레이 사용에 대한 요구 사항

전송 릴레이는 미디어 프로세서와 동일한 범위에 있습니다(바이패스가 아닌 경우). 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365, Office 365 및 Office 365 GCC 환경

- 52.112.0.0 /14(IP 주소는 52.112.0.1에서 52.115.255.254로)

### <a name="office-365-gcc-dod-environment"></a>GCC DoD 환경 Office 365

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>GCC High 환경 Office 365

- 52.127.88.0/21


Teams 전송 릴레이의 포트 범위(모든 환경에 적용 가능)는 다음 표에 나와 있습니다.


| 트래픽을 | 보낸 사람 | 받는 사람 | 원본 포트 | 대상 포트|
| :-------- | :-------- |:-----------|:--------|:---------|
| UDP/SRTP | 전송 릴레이 | Sbc | 50 000 -59 999    | SBC에 정의됨 |
| UDP/SRTP | Sbc | 전송 릴레이 | SBC에 정의됨 | 50 000 – 59 999, 3478-3481     |


> [!NOTE]
> Microsoft는 SBC에서 동시 호출당 두 개 이상의 포트를 권장합니다. Microsoft에는 두 가지 버전의 전송 릴레이가 있으므로 다음이 필요합니다.
> 
> - v4- 포트 범위 50 000~59 999에서만 사용할 수 있습니다.
> 
> - 포트 3478-3481에서 작동하는 v6

현재 미디어 바이패스는 v4 버전의 전송 릴레이만 지원합니다. 향후 v6 지원을 도입할 예정입니다. 

전환하려면 포트 3478-3481을 열어야 합니다. Microsoft에서 미디어 바이패스를 사용하는 v6 전송 릴레이에 대한 지원을 도입하는 경우 네트워크 장비 또는 SCC를 다시 구성할 필요가 없습니다. 

### <a name="requirements-for-using-media-processors"></a>미디어 프로세서를 사용하기 위한 요구 사항

미디어 프로세서는 항상 음성 애플리케이션 및 웹 클라이언트(예: Edge 또는 Google Chrome의 Teams 클라이언트)에 대한 미디어 경로에 있습니다. 비 바이패스 구성의 요구 사항은 동일합니다.


미디어 트래픽의 IP 범위는 입니다. 

### <a name="office-365-and-office-365-gcc-environments"></a>GCC 환경 Office 365 및 Office 365

- 52.112.0.0 /14(IP 주소는 52.112.0.1에서 52.115.255.254로)

### <a name="office-365-gcc-dod-environment"></a>GCC DoD 환경 Office 365

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>GCC High 환경 Office 365

- 52.127.88.0/21

미디어 프로세서의 포트 범위(모든 환경에 적용 가능)는 다음 표에 나와 있습니다.

| 트래픽을 | 보낸 사람 | 받는 사람 | 원본 포트 | 대상 포트|
| :-------- | :-------- |:-----------|:--------|:---------|
| UDP/SRTP | 미디어 프로세서 | Sbc | 3478-3481 및 49 152 – 53 247    | SBC에 정의됨 |
| UDP/SRTP | Sbc | 미디어 프로세서 | SBC에 정의됨 | 3478-3481 및 49 152 – 53 247     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a>미디어 바이패스 및 비미디어 바이패스에 대해 별도의 트렁크 구성  

미디어 바이패스 이외의 미디어 바이패스로 마이그레이션하고 모든 사용량을 미디어 바이패스로 마이그레이션하기 전에 기능을 확인하려는 경우 별도의 트렁크를 만들고 별도의 온라인 음성 라우팅 정책을 만들어 미디어 바이패스 트렁크로 라우팅하고 특정 사용자에게 할당할 수 있습니다. 

상위 수준 구성 단계:

- 미디어 바이패스 테스트할 사용자를 식별합니다.

- 서로 다른 FQDN을 사용하여 두 개의 개별 트렁크를 만듭니다. 하나는 미디어 바이패스용으로 사용하도록 설정됩니다. 다른 은 그렇지 않습니다. 

  두 트렁크는 동일한 SBC를 가리킵니다. TLS SIP 신호에 대한 포트는 달라야 합니다. 미디어의 포트는 동일해야 합니다.

- 새 온라인 음성 라우팅 정책을 만들고 이 정책의 PSTN 사용과 연결된 해당 경로에 미디어 바이패스 트렁크를 할당합니다.

- 미디어 바이패스 테스트를 위해 식별한 사용자에게 새 온라인 음성 라우팅 정책을 할당합니다.

아래 예제에서는 이 논리를 보여 줍니다.

| 사용자 집합 | 사용자 수 | OVRP에 할당된 트렁크 FQDN | 미디어 바이패스 사용 |
| :------------ |:----------------- |:--------------|:--------------|
| 미디어가 아닌 바이패스 트렁크가 있는 사용자 | 980 | sbc1.contoso.com:5061 | False |
| 미디어 바이패스 트렁크가 있는 사용자 | 20 | sbc2.contoso.com:5060 | 사실 | 

두 트렁크는 동일한 공용 IP 주소를 가진 동일한 SBC를 가리킬 수 있습니다. 다음 다이어그램과 같이 SBC의 TLS 신호 포트는 달라야 합니다. 인증서가 두 트렁크를 모두 지원하는지 확인해야 합니다. SAN에서는 두 개의 이름(**sbc1.contoso.com** 및 **sbc2.contoso.com**)이 있거나 와일드카드 인증서가 있어야 합니다.

> [!div class="mx-imgBorder"]
> ![두 트렁크가 동일한 공용 IP를 사용하여 동일한 SBC를 가리킬 수 있습니다.](media/direct-routing-media-bypass-7.png)

동일한 SBC에서 두 트렁크를 구성하는 방법에 대한 자세한 내용은 SBC 공급업체에서 제공하는 설명서를 참조하세요.

 - [AudioCodes 배포 설명서](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle 배포 설명서](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [리본 통신 배포 설명서](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-Systems(anynode) 배포 설명서](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a>미디어 바이패스로 지원되는 클라이언트 엔드포인트

미디어 바이패스는 모든 독립 실행형 Teams 데스크톱 클라이언트, Android 및 iOS 클라이언트 및 Teams 전화 디바이스에서 지원됩니다. 

미디어 바이패스를 지원하지 않는 다른 모든 엔드포인트의 경우 바이패스 호출로 시작된 경우에도 호출을 비 바이패스로 변환합니다. 이 작업은 자동으로 수행되며 관리자의 작업이 필요하지 않습니다. 여기에는 비즈니스용 Skype 3PIP 휴대폰 및 직접 라우팅 호출을 지원하는 Teams 웹 클라이언트(Microsoft Edge, Google Chrome, Mozilla Firefox에서 실행되는 WebRTC 기반 클라이언트)가 포함됩니다. 
 
## <a name="see-also"></a>참고 항목

[직접 라우팅을 위한 미디어 바이패스 구성](direct-routing-configure-media-bypass.md)
