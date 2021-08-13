---
title: Microsoft Teams 통화 흐름
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 06/08/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sonua
audience: admin
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
description: 다양한 토폴로지에서 Teams Office 365 및 피어 투 피어 미디어 통신에 사용되는 고유한 팀 흐름을 사용하는 방법에 대해 알아보습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ebe6de7773ca77964619f5d90d1c189ea8d731c8d7c242c2a04a619a33c55414
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54319861"
---
# <a name="microsoft-teams-call-flows"></a>Microsoft Teams 통화 흐름

> [!TIP]
> 이 세션을 통해 네트워크 Teams 활용하는 방법 및 네트워크 연결 최적화를 계획하는 방법에 대해 알아보고 네트워크 Teams [를 확인합니다.](https://aka.ms/teams-networking)

## <a name="overview"></a>개요

이 문서에서는 다양한 토폴로지에서 Teams Microsoft 365 Office 365 호출 흐름을 사용하는 방법을 설명합니다. 또한 피어 투 피어 Teams 통신에 사용되는 고유한 흐름을 설명합니다. 이 문서에서는 이러한 흐름, 해당 목적 및 네트워크의 원본 및 종료를 설명합니다. 이 문서에서는 다음을 가정합니다.

- Flow X는 클라우드에서 서비스 또는 Microsoft 365 Office 365 위해 프레미스 클라이언트에서 사용됩니다. 이 네트워크는 고객 네트워크에서 시작되고, 네트워크 또는 네트워크의 엔드포인트로 Microsoft 365 Office 365.

- Flow Y는 인터넷에서 종속성 또는 종속성이 있는 인터넷 Microsoft 365 Office 365 클라이언트에서 사용됩니다. 고객 네트워크에서 시작되고 인터넷의 엔드포인트로 종료됩니다.

이 문서에서는 다음 정보를 다 제공합니다.

- **배경** 입니다. 흐름이 전달할 수 있는 네트워크, 트래픽 유형, 고객 네트워크에서 서비스 Microsoft 365 또는 Office 365 연결 지침, 타사 구성 요소와의 상호 작동성, 미디어 흐름을 선택하는 데 사용되는 Teams 등의 배경 정보를 제공합니다.

- **다양한 토폴로지의 통화 흐름입니다.** 다양한 토폴로지에서 호출 흐름의 사용을 보여 주는 것입니다. 각 토폴로지에 대해 섹션은 지원되는 모든 흐름을 열기하고 이러한 흐름이 여러 사용 사례에서 사용되는 방법을 보여 주는 것입니다. 각 사용 사례에 대해 흐름 다이어그램을 사용하여 흐름의 순서 및 선택을 설명합니다.

- **Teams 최적화를 사용할 수 있습니다.** 간단한 토폴로지로 설명된 Express Route가 최적화를 위해 배포될 때 이러한 흐름이 사용되는 방법을 설명합니다.

## <a name="background"></a>배경

### <a name="network-segments"></a>네트워크 세그먼트

**고객 네트워크** 입니다. 제어하고 관리하는 네트워크 세그먼트입니다. 여기에는 유선 또는 무선, 사무실 건물 간 연결, 프레미스 데이터 센터에 대한 연결, 인터넷 공급자, Express Route 또는 기타 개인 피어링에 대한 연결 등 고객 사무실 내의 모든 고객 연결이 포함됩니다.

일반적으로 고객 네트워크에는 방화벽 및/또는 프록시 서버가 있는 여러 네트워크 경계가 있으며 조직의 보안 정책을 적용하고 설정하고 구성한 특정 네트워크 트래픽만 허용합니다. 이 네트워크를 관리하기 때문에 네트워크의 성능을 직접 제어할 수 있으며 네트워크 내의 사이트와 네트워크에서 네트워크 또는 네트워크로의 성능의 유효성을 검사하기 위해 네트워크 평가를 완료하는 Microsoft 365 Office 365 것이 좋습니다.

**인터넷**. 이는 고객 네트워크 외부에서 Microsoft 365 또는 Office 365 사용자가 사용하는 전체 네트워크의 일부인 네트워크 세그먼트입니다. 또한 고객 네트워크의 일부 트래픽에서 Microsoft 365 또는 Office 365.

**방문한 또는 게스트 개인 네트워크 입니다.** 이는 사용자와 게스트가 방문할 수 있는 공용 인터넷 외부의 네트워크 세그먼트입니다(예: 홈 사설 네트워크 또는 엔터프라이즈 사설 네트워크) 사용자와 해당 Teams 상호 작용하는 사용자와 해당 고객이 상주할 수 있는 Teams 있습니다.

> [!NOTE]
> 이러한 네트워크에 Microsoft 365 Office 365 연결도 가능합니다.

**Microsoft 365 또는 Office 365.** 이 네트워크 세그먼트는 서비스 또는 Microsoft 365 Office 365 세그먼트입니다. 대부분의 위치에서 고객 네트워크에 근접한 에지로 전 세계에 배포됩니다. 함수에는 전송 릴레이, 회의 서버 및 미디어 프로세서가 포함됩니다.

**Express Route(선택 사항)**. 이는 전체 네트워크의 일부인 네트워크 세그먼트로, 네트워크 또는 네트워크 네트워크에 대한 전용 개인 Microsoft 365 Office 365 있습니다.

### <a name="types-of-traffic"></a>트래픽 유형

**실시간 미디어**. 오디오, 비디오 및 화면 공유 워크로드를 지원하는 RTP(실시간 전송 프로토콜) 내에 캡슐화된 데이터입니다. 일반적으로 미디어 트래픽은 대기 시간이 매우 중요하기 때문에 이 트래픽이 가능한 가장 직접적인 경로를 취하고 UDP와 TCP를 전송 계층 프로토콜로 사용하게 하려는데, 이는 양질의 관점에서 대화형 실시간 미디어에 가장 적합한 전송입니다. (마지막 수단으로 미디어는 TCP/IP를 사용할 수 있으며 HTTP 프로토콜 내에서 터널링할 수도 있지만 품질에 좋지 않은 의미로 인해 권장되지 않습니다.) RTP 흐름은 페이로드만 암호화되는 SRTP를 사용하여 보호됩니다.

**신호 입니다.** 클라이언트와 서버 또는 작업을 제어하는 데 사용되는 다른 클라이언트(예: 호출이 시작될 때)와 인스턴트 메시지를 전달하는 데 사용되는 다른 클라이언트 간의 통신 링크입니다. 대부분의 신호 트래픽은 HTTPS 기반 REST 인터페이스를 사용하며, 일부 시나리오에서는 SIP 프로토콜을 사용합니다(예: Microsoft 365 또는 Office 365 세션 테두리 컨트롤러 간의 연결). 이 트래픽은 대기 시간에 훨씬 덜 민감하지만 엔드포인트 간의 대기 시간이 몇 초를 초과하면 서비스 중단 또는 호출 시간 제한이 발생할 수 있다는 것을 이해하는 것이 중요합니다.

### <a name="connectivity-to-microsoft-365-or-office-365"></a>Microsoft 365 또는 Office 365

Teams [인터넷에 연결해야 합니다.](/office365/enterprise/assessing-network-connectivity) Teams 엔드포인트 URL 및 IP 주소 범위는 URL 및 IP Office 365 범위에 [나열됩니다.](/office365/enterprise/urls-and-ip-address-ranges) (TCP 포트 80 및 443 및 UDP 포트 3478~3481에 대한 연결이 필요합니다.) 또한 Teams 인터넷에 연결해야 하는 비즈니스용 Skype Online에 대한 종속성도 있습니다.

Teams 흐름 연결은 표준 IETF 대화형 연결 수립(ICE) 프로시저를 사용하여 구현됩니다.

### <a name="interoperability-restrictions"></a>상호 연동성 제한 사항

**타사 미디어 릴레이**. Teams 미디어 흐름(즉, 미디어 엔드포인트 중 Teams)은 네이티브 미디어 릴레이에서만 Teams 비즈니스용 Skype 수 있습니다. 타사 미디어 릴레이와의 상호 연동성은 지원되지 않습니다. (PSTN을 사용하는 경계의 타사 SBC는 SRTP를 사용하여 보호된 RTP/RTCP 스트림을 종료하고 다음 홉에 릴레이하지 말아야 합니다.)

**타사 SIP 프록시 서버 입니다.** 타사 SBC 및/Teams SIP 대화 상자를 통해 네이티브 SIP Teams 또는 비즈니스용 Skype 수 있습니다. 타사 SIP 프록시와의 상호 연동성은 지원되지 않습니다.

**타사 B2BUA(또는 SBC) 입니다.** PSTN Teams 미디어 흐름은 타사 SBC에 의해 종료됩니다. 그러나 타사 SBC와의 상호 Teams(타사 SBC가 두 개의 Teams 또는 비즈니스용 Skype 엔드포인트를 중재하는 경우)는 지원되지 않습니다.

### <a name="technologies-that-are-not-recommended-with-microsoft-teams"></a>권장되지 않는 기술 Microsoft Teams

**VPN 네트워크** 입니다. 미디어 트래픽(또는 흐름 2')에는 권장되지 않습니다. VPN 클라이언트는 [Lync](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Enabling-Lync-Media-to-Bypass-a-VPN-Tunnel/ba-p/620210)미디어를 사용하여 VPN 터널을 우회하는 Teams 외부 비 VPN 사용자와 같은 미디어 트래픽을 분할 터널링 및 라우팅해야 합니다.

> [!NOTE]
> 타이틀은 Lync를 나타내지만, 타이틀도 Lync에 Teams 있습니다.

**패킷 셰이프.** 모든 종류의 패킷 스니퍼, 패킷 검사 또는 패킷 셰이퍼 디바이스는 미디어 트래픽에 Teams 권장되지 않고 품질이 크게 저하될 수 있습니다.

### <a name="principles"></a>원칙

호출 흐름을 이해하는 데 도움이 되는 네 가지 일반적인 원칙은 Microsoft Teams.

- Microsoft Teams 첫 번째 Microsoft 365 참가한 Microsoft 365 Office 365 지역을 통해 개최됩니다. (일부 토폴로지에서 이 규칙에 대한 예외가 있는 경우 이 문서에 설명되어 적절한 호출 흐름에 의해 설명됩니다.)

- Teams 또는 Microsoft 365 Office 365 미디어 엔드포인트는 통화 유형에 기반하지 않는 미디어 처리 요구 사항을 기반으로 사용됩니다. (예를 들어 지점 간 통화는 클라우드의 미디어 엔드포인트를 사용하여 전사 또는 기록을 위해 미디어를 처리하고, 두 참가자가 있는 컨퍼런스는 클라우드에서 미디어 엔드포인트를 사용하지 않을 수 있습니다.) 그러나 대부분의 컨퍼런스는 미디어 엔드포인트를 사용하여 회의가 호스트되는 위치로 할당됩니다. 클라이언트에서 미디어 엔드포인트로 전송된 미디어 트래픽은 고객 네트워크 방화벽 제한으로 Microsoft 365 또는 Office 365 전송 릴레이를 직접 라우팅할 수 있습니다.

- 피어 투 피어 호출에 대한 미디어 트래픽은 호출이 클라우드에서 미디어 엔드포인트를 지시하지 않는다고 생각하면 사용할 수 있는 가장 직접적인 경로를 사용하게 됩니다(이전 원칙 참조). 기본 설정 경로는 원격 피어(클라이언트)로 직접 이동되지만 해당 경로를 사용할 수 없는 경우 하나 이상의 전송 릴레이가 트래픽을 릴레이합니다. 미디어 트래픽은 미디어 품질에 영향을 주기 때문에 패킷 셰이더, VPN 서버 등의 서버를 횡단하지 않는 것이 좋습니다.

- 신호 트래픽은 항상 사용자에게 가장 가까운 서버로 전송됩니다.

선택한 미디어 경로에 대한 자세한 내용은 [BRK4016의 미디어 흐름 이해를 Microsoft Teams 참조합니다.](https://www.youtube.com/watch?v=1tmHMIlAQdo)

## <a name="call-flows-in-various-topologies"></a>다양한 토폴로지의 통화 흐름

### <a name="teams-topology"></a>Teams 토폴로지

이 토폴로지는 직접 라우팅과 같은 Teams 배포하지 않고 클라우드에서 비즈니스용 Skype 서버 서비스를 전화 시스템 사용됩니다. 또한 Azure Express 경로 없이 Microsoft 365 Office 365 인터페이스가 인터넷을 통해 수행됩니다.

[![Microsoft Teams 온라인 통화 흐름 그림 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)

*그림 1 - Teams 토폴로지*

참고:

- 위의 다이어그램의 화살표 방향은 엔터프라이즈 경계의 연결에 영향을 주는 통신의 시작 방향을 반영합니다. 미디어용 UDP의 경우 첫 번째 패킷이 역방향으로 흐를 수 있지만 다른 방향으로 패킷이 흐를 때까지 이러한 패킷이 차단될 수 있습니다.
- Teams 온라인과 나란히 배포되는 비즈니스용 Skype 클라이언트는 "Teams/SFB 사용자"로 표시됩니다.

문서 의 2부에서 다음 선택적 토폴로지에 대한 자세한 정보를 찾을 수 있습니다.

- 비즈니스용 Skype 배포는 하이브리드 토폴로지에서 Teams **설명합니다.**
- 전화 시스템 PSTN 연결에 대한 직접 라우팅은 직접 라우팅 **토폴로지와** 함께 Teams 설명되어 있습니다.
- Express Route는 Express route 최적화를 Teams **설명되어 있습니다.**

**Flow 설명**:

- **Flow 2** – 고객 네트워크의 사용자가 인터넷으로 시작한 흐름을 사용자의 경험의 일부로 Teams 합니다. 이러한 흐름의 예로는 DNS 및 피어 투 피어 미디어가 있습니다.
- **Flow 2'** – 원격 모바일 Teams 사용자에 의해 시작된 흐름을 나타내며, VPN을 고객 네트워크에 제공합니다.
- **Flow 3** – 원격 모바일 Teams 사용자가 엔드포인트를 Microsoft 365 Office 365/Teams 표현합니다.
- **Flow 4** – 고객 네트워크의 사용자가 엔드포인트를 Microsoft 365 또는 Office 365 Teams 표현합니다.
- **Flow 5** – 고객 Teams 사용자와 다른 사용자 Teams 또는 비즈니스용 Skype 피어 투 피어 미디어 흐름을 나타내고 있습니다.
- **Flow 6** – 원격 모바일 Teams 사용자와 인터넷을 통해 다른 원격 모바일 Teams 또는 비즈니스용 Skype 피어 투 피어 미디어 흐름을 표현합니다.

#### <a name="use-case-one-to-one"></a>사용 사례: 일대일

일대일 호출은 호출자가 로컬, 릴레이 및 반사(릴레이에서 볼 수 있는 클라이언트의 공용 IP 주소)를 포함하여 IP 주소/포트로 구성된 후보 집합을 얻는 일반적인 모델을 사용합니다. 호출자는 이러한 후보를 호출된 파티로 보내고, 호출된 파티는 유사한 후보 집합을 획득하여 호출자에 전송합니다. STUN 연결 확인 메시지는 어떤 호출자/호출된 파티 미디어 경로가 작동하고 최상의 작업 경로가 선택되어 있는지 찾는 데 사용됩니다. 미디어(즉, SRTP를 사용하여 보호된 RTP/RTCP 패킷)는 선택한 후보 쌍을 사용하여 전송됩니다. 전송 릴레이는 Microsoft 365 및 Office 365.

로컬 IP 주소/포트 후보 또는 반사 후보에 연결이 있는 경우 클라이언트 간의 직접 경로(또는 NAT 사용)는 미디어에 대해 선택됩니다. 클라이언트가 고객 네트워크에 있는 경우 직접 경로를 선택해야 합니다. 이렇게 하려면 고객 네트워크 내에서 직접 UDP 연결이 필요합니다. 클라이언트가 유성 클라우드 사용자인 경우 NAT/방화벽에 따라 미디어에서 직접 연결을 사용할 수 있습니다.

한 클라이언트가 고객 네트워크의 내부에 있으며 하나의 클라이언트가 외부(예: 모바일 클라우드 사용자)인 경우 로컬 또는 반사 후보 간의 직접 연결은 작동하지 않습니다. 이 경우 옵션은 두 클라이언트에서 전송 릴레이 후보 중 하나를 사용하는 것입니다(예: 내부 클라이언트는 전송 릴레이에서 전송 릴레이 후보를 Microsoft 365 Office 365, 외부 클라이언트가 STUN/RTP/RTCP 패킷을 전송 릴레이로 보낼 수 있게 해야 합니다. 또 다른 옵션은 내부 클라이언트가 모바일 클라우드 클라이언트에서 얻은 릴레이 후보로 전송하는 것입니다. 미디어에 대한 UDP 연결은 매우 권장되는 것이지만 TCP가 지원됩니다.

**고급 단계:**

1. Teams 사용자 A는 흐름 2를 사용하여 DNS(URL 도메인 이름)를 확인합니다.
1. Teams 사용자 A는 흐름 4를 사용하여 전송 Teams 릴레이에 미디어 릴레이 포트를 할당합니다.
1. Teams 사용자 A는 흐름 4를 사용하여 ICE 후보와 함께 "초대"를 Microsoft 365 또는 Office 365.
1. Microsoft 365 또는 Office 365 흐름 4를 사용하여 Teams 사용자 B에게 알림을 전송합니다.
1. Teams 사용자 B는 흐름 4를 사용하여 전송 Teams 미디어 릴레이 포트를 할당합니다.
1. Teams 사용자 B는 흐름 4를 사용하여 ICE 후보와 "응답"을 보내며, 이 Teams 4를 사용하여 Teams 사용자 A로 Flow 합니다.
1. Teams 사용자 A 및 Teams 사용자 B는 ICE 연결 테스트를 호출하고 사용 가능한 최상의 미디어 경로가 선택됩니다(다양한 사용 사례에 대한 아래 다이어그램 참조).
1. Teams 사용자는 흐름 4를 사용하여 원격 분석 Microsoft 365 Office 365 전송합니다.

**고객 네트워크 내에서:**

[![Microsoft Teams 온라인 통화 흐름 그림 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)

*그림 2 - 고객 네트워크 내에서*

7단계에서 피어 투 피어 미디어 흐름 5가 선택됩니다.

미디어는 양방향입니다. 흐름 5의 방향은 한 쪽이 이 문서의 모든 흐름과 일치하여 연결 관점에서 통신을 시작했다는 것입니다. 이 경우 두 엔드포인트가 고객 네트워크 내에 있기 때문에 사용되는 방향은 중요하지 않습니다.

**외부 사용자에 대한 고객 네트워크(전송 릴레이로 Teams):**

[![Microsoft Teams 온라인 통화 흐름 그림 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)

*그림 3 - 외부 사용자에 대한 고객 네트워크(전송 릴레이로 Teams 미디어)*

7단계에서 고객 네트워크에서 원격 모바일 Microsoft 365 또는 Office 365 흐름 3, 원격 모바일 Teams 사용자에서 Microsoft 365 또는 Office 365 흐름이 선택됩니다. 이러한 흐름은 Teams 또는 Teams 전송 릴레이로 Microsoft 365 Office 365.

미디어는 양방향입니다. 여기서 방향은 연결 관점에서 통신을 시작하는 쪽을 나타냅니다. 이 경우 이러한 흐름은 서로 다른 전송 프로토콜 및 주소를 사용하여 신호 및 미디어에 사용됩니다.

**외부 사용자(직접 미디어)에 대한 고객 네트워크:**

[![Microsoft Teams 온라인 통화 흐름 그림 04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)

*그림 4 - 외부 사용자에 대한 고객 네트워크(직접 미디어)*

7단계에서 고객 네트워크에서 인터넷(클라이언트의 피어)으로의 흐름 2가 선택됩니다.

- 원격 모바일 사용자가 있는 직접 미디어(Microsoft 365 또는 Office 365)는 선택 사항입니다. 즉, 고객은 이 경로를 차단하여 전송 릴레이를 통해 미디어 경로를 Microsoft 365 또는 Office 365.

- 미디어는 양방향입니다. 흐름 2에서 원격 모바일 사용자로의 방향은 한 쪽이 연결 관점에서 통신을 시작했다는 것입니다.

**내부 사용자에 VPN 사용자(전송 릴레이로 Teams 미디어)**

[![Microsoft Teams 온라인 통화 흐름 그림 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)

*그림 5 - 내부 사용자에 VPN 사용자(전송 릴레이로 Teams 미디어)*

VPN 간을 고객 네트워크로 신호하는 것은 흐름 2'를 사용하고 있습니다. 고객 네트워크와 Microsoft 365 또는 Office 365 신호는 흐름 4를 사용하고 있습니다. 그러나 미디어는 VPN을 우회하고 흐름 3 및 4에서 Teams 미디어 릴레이를 사용하여 Microsoft 365 Office 365.

**내부 사용자에 대한 VPN 사용자(직접 미디어)**

[![Microsoft Teams 온라인 통화 흐름 그림 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)

*그림 6 - 내부 사용자에 VPN 사용자(직접 미디어)*

VPN 간을 고객 네트워크로 신호하는 것은 흐름 2'를 사용하고 있습니다. 고객 네트워크와 Microsoft 365 또는 Office 365 신호는 흐름 4를 사용하고 있습니다. 그러나 미디어는 VPN을 무시하고 고객 네트워크에서 인터넷으로 흐름 2를 사용하여 라우팅됩니다.

미디어는 양방향입니다. 원격 모바일 사용자로 흐름 2의 방향은 한 쪽이 연결 관점에서 통신을 시작했다는 것입니다.

**외부 사용자에 대한 VPN 사용자(직접 미디어)**

[![Microsoft Teams 흐름 그림 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)

*그림 7 - 외부 사용자에 대한 VPN 사용자(직접 미디어)*

VPN 사용자 간을 고객 네트워크에 신호하는 것은 흐름 2'를 사용하고 흐름 4를 사용하여 Microsoft 365 또는 Office 365. 그러나 미디어는 VPN을 우회하고 흐름 6을 사용하여 라우팅됩니다.

미디어는 양방향입니다. 흐름 6을 원격 모바일 사용자로 이동하는 방향은 한 쪽이 연결 관점에서 통신을 시작했다는 것입니다.

#### <a name="use-case-teams-to-pstn-through-microsoft-365-or-office-365-trunk"></a>사용 사례: Teams 또는 Microsoft 365 통해 PSTN에 Office 365 수 있습니다.

Microsoft 365 Office 365 PSTN(공용 전화 시스템 전화 네트워크)에서 전화를 걸고 받을 수 있는 기능을 제공합니다. PSTN 트렁크가 호출 전화 시스템 사용하여 연결된 경우 이 사용 사례에 대한 특별한 연결 요구 사항이 없습니다. (사용자 자신의 On-프레미스 PSTN 트렁크를 Microsoft 365 Office 365 직접 라우팅을 전화 시스템 있습니다.)

[![Microsoft Teams 온라인 통화 흐름 그림 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)

*그림 8 - Teams 트렁크를 통해 PSTN으로 Office 365*

#### <a name="use-case-teams-meeting"></a>사용 사례: Teams 모임

VBSS(오디오/비디오/화면 공유) 회의 서버는 Microsoft 365 Office 365. 고객 네트워크에서 도달할 수 있어야 하는 공용 IP 주소가 있으며 Nomadic Cloud 클라이언트에서 연결 가능해야 합니다. 각 클라이언트/엔드포인트는 회의 서버에 연결할 수 있습니다.

내부 클라이언트는 일대일 호출에 대해 설명한 방식으로 로컬, 반사 및 릴레이 후보를 얻습니다. 클라이언트는 초대에서 회의 서버에 이러한 후보를 보낼 것입니다. 회의 서버는 공개적으로 연결 가능한 IP 주소가 있으므로 릴레이를 사용하지 않습니다. 따라서 해당 로컬 IP 주소 후보와 응답합니다. 클라이언트 및 회의 서버는 일대일 호출에 대해 설명된 방식으로 연결을 검사합니다.

참고:

- Teams 클라이언트는 비즈니스용 Skype 모임에 참가할 수 비즈니스용 Skype 클라이언트가 Teams 수 없습니다.

- PSTN 사용자는 모임의 이끌이 PSTN 호출 및/또는 회의 프로비전에 따라 선택적으로 "IN 전화 걸기" 또는 "전화 걸기"입니다.

- 게스트 사용자 또는 고객 사용자는 엄격한 규칙으로 FW/NAT를 사용하여 보호되는 게스트 개인 네트워크에서 참가할 수 있습니다.

[![Microsoft Teams 온라인 통화 흐름 그림 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)

*그림 9 - Teams 모임*

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a>사용 사례: 비즈니스용 Skype 페더럴

**또는 Teams 전송 릴레이로 Microsoft 365 Office 365**

[![Microsoft Teams 온라인 통화 흐름 그림 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)

*그림 10 - Teams 전송 릴레이로 Office 365*

참고:

- 페더넌트는 정의에 따라 두 테넌트 간의 통신입니다. 이 경우, Teams 사용하는 테넌트 A는 비즈니스용 Skype 페더테이트합니다. 테넌트 B가 Microsoft 365 또는 Office 365 경우 비즈니스용 Skype 클라이언트는 흐름 3을 사용하여 Microsoft 365 Office 365.

- 페더링된 비즈니스용 Skype 클라이언트에서 비즈니스용 Skype 서버 미디어는 이 문서의 범위를 벗어날 수 없습니다. 그러나 명확성을 위해 여기에 설명되어 있습니다.

- 게이트웨이에서 Teams 비즈니스용 Skype 신호가 연결됩니다.

- 이 경우 미디어는 흐름 4를 사용하여 고객 Teams 원격 비즈니스용 Skype 전송 릴레이를 통해 릴레이됩니다.

**페더리드 테넌트에서 비즈니스용 Skype 미디어 릴레이로 릴레이된 미디어**

[![Microsoft Teams 온라인 통화 흐름 그림 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)

*그림 11 - 페더레이드 테넌트에서 비즈니스용 Skype 미디어 릴레이로 릴레이된 미디어*

참고:

- 페더링된 비즈니스용 Skype 클라이언트에서 비즈니스용 Skype 서버 미디어는 이 문서의 범위를 벗어날 수 없습니다. 그러나 명확성을 위해 여기에 설명되어 있습니다.

- 게이트웨이에서 Teams 비즈니스용 Skype 신호가 연결됩니다.

- 이 경우 미디어는 흐름 2를 사용하여 비즈니스용 Skype 미디어 릴레이를 통해 고객 네트워크에 릴레이됩니다. (페더레이드된 Teams 네트워크의 원격 미디어 릴레이로의 트래픽은 처음에는 역방향의 트래픽이 흐르기 시작할 때까지 미디어 릴레이에 의해 차단됩니다. 그러나 양방향 흐름은 양방향으로 연결이 열립니다.)

**직접(피어 투 피어)**

[![Microsoft Teams 온라인 통화 흐름 그림 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)

*그림 12 - 직접(피어 투 피어)*

### <a name="teams-hybrid-topology"></a>Teams 토폴로지

이 토폴로지에는 Teams 비즈니스용 Skype 배포가 포함된 토폴로지가 포함됩니다.

[![Microsoft Teams 온라인 통화 흐름 그림 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)

*그림 13 - Teams 토폴로지*

- 위의 다이어그램의 화살표 방향은 엔터프라이즈 경계의 연결에 영향을 주는 통신의 시작 방향을 반영합니다. 미디어용 UDP의 경우 첫 번째 패킷이 역방향으로 흐를 수 있지만 다른 방향으로 패킷이 흐를 때까지 이러한 패킷이 차단될 수 있습니다.

- Teams 온라인과 나란히 배포되는 비즈니스용 Skype 클라이언트는 "Teams/SFB 사용자"로 표시됩니다.

추가 흐름(토폴로지 위에 Teams):

- **Flow 5A** – 고객 네트워크 내의 Teams 사용자와 고객 네트워크 에지의 비즈니스용 Skype 프레미스 미디어 릴레이 간의 피어 투 피어 미디어 흐름을 표현합니다.

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a>사용 사례: Teams 비즈니스용 Skype 일대일

**고객 네트워크 내에서 하이브리드**

[![Microsoft Teams 온라인 통화 흐름 그림 14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)

*그림 14 - 고객 네트워크 내의 하이브리드*

게이트웨이에서 Teams 비즈니스용 Skype 신호가 연결됩니다. 그러나 미디어는 흐름 5를 사용하여 고객 네트워크 내에서 직접 피어 투 피어로 라우팅됩니다.

**외부 사용자와 비즈니스용 Skype 하이브리드 고객 네트워크 - Microsoft 365 또는 Office 365**

[![Microsoft Teams 온라인 통화 흐름 그림 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)

*그림 15 - 외부 사용자와 비즈니스용 Skype 하이브리드 고객 네트워크 - Office 365*

참고:

- 클라이언트에서 비즈니스용 Skype 클라이언트에서 비즈니스용 Skype 서버 이 문서의 범위를 벗어날 수 있습니다. 그러나 명확성을 위해 여기에 설명되어 있습니다.

- 게이트웨이에서 Teams 비즈니스용 Skype 신호가 연결됩니다.

- 미디어는 흐름 4를 통해 Teams 전송 릴레이를 통해 고객 네트워크에 릴레이됩니다.

**외부 사용자와 비즈니스용 Skype 하이브리드 고객 네트워크 - On-Premises Edge에서 릴레이**

[![Microsoft Teams 온라인 통화 흐름 그림 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)

*그림 16 - 외부 사용자와 비즈니스용 Skype 하이브리드 고객 네트워크 - On-Premises Edge에서 릴레이*

참고:

- 클라이언트에서 비즈니스용 Skype 클라이언트에서 비즈니스용 Skype 서버 미디어는 이 문서의 범위를 벗어날 수 없습니다. 그러나 명확성을 위해 여기에 설명되어 있습니다.

- 신호는 게이트웨이에 의해 브리지됩니다.

- 미디어는 비즈니스용 Skype 5A를 사용하여 비즈니스용 Skype 프레미스 에지 내에서 Teams 릴레이됩니다.

### <a name="teams-with-phone-system-direct-routing-topology"></a>Teams 직접 전화 시스템 토폴로지와 함께 사용할 수 있습니다.

이 토폴로지에는 직접 Teams 전화 시스템 포함된 토폴로지가 포함됩니다.

직접 라우팅을 사용하면 지원되는 SBC(고객 소유의 SBC) 하드웨어 디바이스를 연결한 후 전화 통신 트렁크를 해당 디바이스에 연결하여 타사 PSTN(공용 전환 전화 네트워크) 서비스 공급자를 사용할 수 Microsoft 365 Office 365 있습니다.

이 시나리오를 지원하려면 고객은 Microsoft의 인증된 파트너 중 하나에서 직접 라우팅에 대한 인증된 SBC를 배포해야 합니다. SBC는 공급업체에서 권장하는 Microsoft 365 UDP 트래픽에 Microsoft 365 Office 365 라우팅할 수 있어야 합니다. 미디어는 Teams 및/또는 비즈니스용 Skype 클라이언트에서 SBC(Teams 게이트웨이를 무시)로 직접 흐르거나 Teams 게이트웨이를 통과할 수 있습니다. 트렁크를 무시하도록 트렁크를 Teams SBC와의 연결은 SBC가 ICE-Lite를 지원하는 ICE를 기반으로 하는 반면, Teams/비즈니스용 Skype 미디어 엔드포인트는 ICE 전체 양식을 지원합니다.

[![Microsoft Teams 온라인 통화 흐름 그림 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)

*그림 17 - Teams 전화 시스템 토폴로지가 있는 경우

참고:

- 위의 다이어그램의 화살표 방향은 엔터프라이즈 경계의 연결에 영향을 주는 통신의 시작 방향을 반영합니다. 미디어용 UDP의 경우 첫 번째 패킷이 역방향으로 흐를 수 있지만 다른 방향으로 패킷이 흐를 때까지 이러한 패킷이 차단될 수 있습니다.

- Teams 온라인과 나란히 배포되는 비즈니스용 Skype 클라이언트는 "Teams/SFB 사용자"로 표시됩니다.

추가 흐름(온라인 토폴로지 위에 Teams):

- **Flow 4'** - Microsoft 365 Office 365 네트워크로의 흐름을 나타내며, 클라우드의 미디어 Teams SBC와의 연결을 설정하는 데 사용됩니다.
- **Flow 5B** – 우회 모드에서 직접 라우팅 SBC를 Teams 네트워크 내의 사용자 간에 미디어 흐름을 나타내고 있습니다.
- **Flow 5C** – PSTN 헤어 펜 호출 우회 모드에서 직접 라우팅 SBC 간에 다른 직접 라우팅 SBC 간 미디어 흐름을 나타내고

**직접 라우팅이 있는 내부 사용자(전송 릴레이로 Teams 미디어)**

[![Microsoft Teams 온라인 통화 흐름 그림 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)

*그림 18 - 직접 라우팅이 있는 내부 사용자(전송 릴레이로 Teams 미디어)*

참고:

- SBC에는 공용 IP 주소가 있어야 Microsoft 365 또는 Office 365.

- SBC에서 신호 및 미디어를 Microsoft 365 또는 Office 365 흐름 4 및/또는 흐름 4'를 사용하는 경우도 마찬가지입니다.

- 고객 네트워크 내의 클라이언트에서 흐름 4를 Microsoft 365 Office 365 신호 및 미디어입니다.

**직접 라우팅이 있는 원격 사용자(미디어는 MP(미디어 서버)를 통해 라우팅)**

[![Microsoft Teams 온라인 통화 흐름 그림 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)

*그림 19 - 직접 라우팅이 있는 원격 사용자(미디어는 MP(미디어 서버)를 통해 라우팅)*

참고:

- SBC에는 공용 IP 주소가 있어야 Microsoft 365 또는 Office 365.

- SBC에서 신호 및 미디어를 Microsoft 365 또는 Office 365 흐름 4 및/또는 흐름 4'를 사용하는 경우도 마찬가지입니다.

- 인터넷의 클라이언트에서 흐름 3을 Microsoft 365 Office 365 신호 및 미디어.

**내부 사용자 직접 라우팅(미디어 우회)**

[![Microsoft Teams 온라인 통화 흐름 그림 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)

*그림 20 - 내부 사용자 직접 라우팅(미디어 우회)*

참고:

- SBC에는 공용 IP 주소가 있어야 Microsoft 365 또는 Office 365.

- SBC에서 Microsoft 365 또는 Office 365 흐름 4 및/또는 흐름 4'를 사용하는 경우도 마찬가지입니다.

- 고객 네트워크 내의 클라이언트에서 흐름 4를 Microsoft 365 Office 365 신호.

- 고객 네트워크 내의 클라이언트에서 SBC로의 미디어는 흐름 5B를 사용합니다.

**직접 라우팅을 사용하여 원격 사용자(전송 릴레이로 Teams 미디어 우회)**

[![Microsoft Teams 온라인 통화 흐름 그림 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)

*그림 21 - 직접 라우팅을 사용하여 원격 사용자(전송 릴레이로 Teams 릴레이된 미디어 우회)*

참고:

- SBC에는 공용 IP 주소가 있어야 합니다. Microsoft 365 및 인터넷에서 라우팅할 Office 365 있어야 합니다.

- SBC에서 Microsoft 365 또는 Office 365 신호는 흐름 4 및/또는 흐름 4'를 사용하는 경우도 마찬가지입니다.

- 인터넷의 클라이언트에서 흐름 3을 Microsoft 365 Office 365 신호.

- 인터넷의 클라이언트에서 고객 네트워크 내의 SBC로의 미디어는 전송 릴레이를 통해 릴레이된 흐름 3과 4를 Teams 있습니다.

**원격 사용자 직접 라우팅(미디어 우회 직접)**

[![Microsoft Teams 온라인 통화 흐름 그림 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)

*그림 22 - 원격 사용자 직접 라우팅(미디어 우회 직접)*

참고:

- SBC에는 공용 IP 주소가 있어야 합니다. Microsoft 365 또는 인터넷에서 라우팅할 Office 365 있어야 합니다.

- SBC에서 Microsoft 365 또는 Office 365 신호는 흐름 4 및/또는 흐름 4'를 사용하는 경우도 마찬가지입니다.

- 인터넷의 클라이언트에서 흐름 3을 Microsoft 365 Office 365 신호.

- 인터넷의 클라이언트에서 고객 네트워크 내의 SBC로의 미디어는 흐름 2를 사용합니다.

**직접 라우팅(미디어 우회) – PSTN 헤어 펜 호출(앞으로/전송으로 인해)**

[![Microsoft Teams 온라인 통화 흐름 그림 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)

*그림 23 - 직접 라우팅(미디어 우회) - PSTN 헤어 펜 호출(앞으로/전송으로 인해)*

참고:

- SBC에는 공용 IP 주소가 있어야 Microsoft 365 또는 Office 365.

- SBC에서 Microsoft 365 또는 Office 365 신호는 흐름 4 및/또는 흐름 4'를 사용하는 경우도 마찬가지입니다.

- 호출이 PSTN에서 PSTN으로 머리를 털고 나면 클라이언트가 신호 및 미디어 루프에서 입니다.

- 고객 네트워크 내의 SBC 인스턴스 A에서 고객 네트워크 내의 SBC 인스턴스 B(여기서 A 및 B가 동일한 인스턴스일 수 있는 경우)는 흐름 5C를 사용합니다.

**직접 라우팅(Microsoft 365 또는 Office 365 통해 미디어) – 두 테넌트에서 PSTN 헤어 펜 호출**

[![Microsoft Teams 온라인 통화 흐름 그림 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)

*그림 24 - 직접 라우팅(Microsoft 365 또는 Office 365 통해 미디어) – 두 테넌트에서 PSTN 헤어 펜 호출*

참고:

- SBC에는 공용 IP 주소가 있어야 Microsoft 365 또는 Office 365.

- SBC에서 Microsoft 365 또는 Office 365 신호는 흐름 4 및/또는 흐름 4'를 사용하는 경우도 마찬가지입니다.

- 호출이 PSTN에서 PSTN으로 머리를 털고 나면 클라이언트가 신호 및 미디어 루프에서 입니다.

- 고객 네트워크 X 내의 SBC 인스턴스 A에서 SBC 인스턴스 B로의 미디어는 Media Server 또는 Microsoft 365 Office 365 릴레이해야 하며 우회 모드를 사용할 수 없습니다.

## <a name="teams-with-express-route-optimization"></a>Teams 최적화를 통해 사용

[![Microsoft Teams 온라인 통화 흐름 그림 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)

*그림 25 - Teams 최적화를 통해*

Express Route가 정당화되고 배포되는 경우 Teams 흐름을 흐름 4에서 흐름 1로, 흐름 4에서 흐름 1'로 다시 라우팅할 수 있습니다. 그러나 Teams 애플리케이션은 흐름 4 및 4'를 사용하여 인터넷을 통해 Microsoft 365 Office 365 다른 애플리케이션에 대한 하드 종속성이 있습니다. 따라서 이러한 흐름을 차단하지 말아야 합니다.

하이브리드 비즈니스용 Skype 트래픽은 외부 사용자와 통신하고 다른 테넌트와 페더테인하기 위해 Express Route가 아닌 인터넷으로 라우팅됩니다.

비대칭 흐름을 방지하려면 다시 라우팅을 양방향으로 해야 합니다. 즉, 고객 네트워크 내의 주소는 최적화에 따라 인터넷 또는 Express Route를 통해 라우팅할 수 있지만 둘 다를 통해 라우팅할 수 없습니다.


**외부 사용자에 대한 고객 네트워크(전송 릴레이로 Teams):**

[![Microsoft Teams 온라인 통화 흐름 그림 26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)

*그림 26 - 외부 사용자에 대한 고객 네트워크(전송 릴레이로 Teams 미디어)*

**고급 단계:**

1. Teams 고객 네트워크 내의 사용자는 flow2를 사용하여 DNS(URL 도메인 이름)를 확인합니다.
1. Teams 고객 네트워크 내의 사용자는 흐름 1을 사용하여 전송 Teams 미디어 릴레이 포트를 할당합니다.
1. Teams 고객 네트워크 내의 사용자는 흐름 1을 사용하여 ICE 후보와 함께 "초대"를 Microsoft 365 Office 365.
1. Microsoft 365 또는 Office 365 흐름 3을 사용하여 외부 Teams 사용자에게 알림을 전송합니다.
1. Teams 외부 사용자가 흐름 3을 사용하여 전송 Teams 릴레이에 미디어 릴레이 포트를 할당합니다.
1. Teams 외부 사용자는 흐름 3을 사용하여 ICE 후보와 "응답"을 보내며, 이 경우 Teams 1을 사용하여 사용자 A에게 Flow 합니다.
1. Teams 사용자 A 및 Teams 사용자 B는 ICE 연결 테스트를 호출하고 전송 릴레이에서 릴레이되는 흐름 1과 3을 Teams 선택합니다.
1. Teams 사용자는 흐름 1 및 3을 사용하여 Microsoft 365 Office 365 원격 분석 데이터를 전송합니다.

> [!NOTE]
> Flow 4를 사용하도록 설정하여 흐름 4를 Teams 다른 마이크로 서비스에 대한 애플리케이션의 종속성 지원
