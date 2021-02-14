---
title: ExpressRoute를 사용하는 호출 흐름
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.topic: article
ms.assetid: 413acb29-ad83-4393-9402-51d88e7561ab
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Optimization
description: 이 문서는 비즈니스용 Skype Online 및 ExpressRoute의 핵심 통화 흐름 원칙을 설명하고, 올바르게 이해하고 계획할 수 있도록 통화 흐름의 몇 가지 자세한 예를 제공합니다.
ms.openlocfilehash: b65d7b1e3677c82e562de63257f28ad1561d7190
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164637"
---
# <a name="call-flow-using-expressroute"></a>ExpressRoute를 사용하는 호출 흐름

이 문서는 비즈니스용 Skype Online 및 ExpressRoute의 핵심 통화 흐름 원칙을 설명하고, 올바르게 이해하고 계획할 수 있도록 통화 흐름의 몇 가지 자세한 예를 제공합니다.

비즈니스용 Skype Online을 Microsoft 365 또는 Office 365, 비즈니스용 Skype Server 하이브리드 또는 비즈니스용 Skype Cloud Connector Edition의 일부로 배포하는 경우 비즈니스용 Skype 클라이언트와 서버 간의 통신과 통화 흐름을 이해해야 비즈니스용 Skype Online 서비스를 효과적으로 계획, 배포, 운영 및 해결할 수 있습니다.

## <a name="call-flow-overview"></a>호출 흐름 개요

이 문서에서는 이러한 호출 흐름에 대한 데이터를 전달할 수 있는 네트워크 세그먼트를 설명하고 인터넷 또는 ExpressRoute를 통해 이동하는 트래픽에 비해 네트워크에 로컬로 유지되는 트래픽을 이해하는 데 도움이 됩니다. ExpressRoute를 사용하는 트래픽을 알면 ExpressRoute를 사용하여 회사에서 받을 이점을 평가할 수 있으며, ExpressRoute를 사용하기로 결정한 후 배포의 유효성을 검사하고 문제를 해결하는 ExpressRoute 배포 지침을 이해하는 데 도움이 됩니다.

여기에 설명된 호출 흐름은 방화벽 규칙, NAT 구성, Proxies 및 라우터 구성을 포함하여 제어에 있는 다양한 요인의 영향을 미칠 수 있습니다. 이 문서에서는 권장 설정이 적용되었다고 가정합니다. 이러한 권장 설정은 다음에 설명되어 있습니다.

- [비즈니스용 Skype 온라인 설정](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

- [Office 365 URL 및 IP 주소 범위](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

- [ExpressRoute 개요](https://docs.microsoft.com/azure/expressroute/expressroute-introduction)

- [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/)

위의 설명서에 있는 설정 단계를 따르지 않은 설정 및 구성은 여기에 설명한 호출 흐름과 다를 수 있습니다. 또한 비대칭 및 최적이 아닌 네트워크 경로 또는 최적이 아닌 전송 프로토콜과 같은 구성 문제가 있을 수 있습니다. ExpressRoute는 한 방향으로 인터넷을 사용하는 경로와 다른 방향으로 ExpressRoute를 사용하는 다른 경로에 대한 가능성을 만드는 Office 365에 두 번째 경로를 도입하기 때문에 ExpressRoute가 관련될 때마다 비대칭 라우팅이 중요한 고려 사항입니다. 이로 인해 상태 설정 방화벽을 트래버스하는 경우 반환 방향으로 트래픽이 차단될 수 있습니다.

## <a name="network-segments-and-traffic-types"></a>네트워크 세그먼트 및 트래픽 유형

### <a name="network-segments"></a>네트워크 세그먼트

통화 흐름을 설명하기 전에 비즈니스용 Skype Online에서 사용되는 네트워크 세그먼트 및 미디어 유형을 이해하는 데 도움이 되는 몇 가지 용어를 정의해야 합니다.

아래 호출 흐름 다이어그램은 서로 다른 성능 특성을 가지고 있는 서로 다른 조직(내부 네트워크, 네트워크 서비스 공급자 및 해당 인터넷 피어링 파트너 및 Microsoft)에서 관리하는 4개의 서로 다른 네트워크 세그먼트를 보여 주며, 네트워크 성능 목표에 대한 지침은 비즈니스용 Skype Online의 미디어 품질 및 네트워크 연결 [성능을 참조하세요.](media-quality-and-network-connectivity-performance.md)

아래에서 설명할 각 네트워크 세그먼트를 볼 수 있습니다.

![Flow 네트워크 세그먼트를 호출합니다.](../images/25689bf2-4753-4bea-b8d7-88dc8b6d2e2a.png)

 **네트워크** 제어하고 관리하는 전체 네트워크의 일부인 네트워크 세그먼트입니다. 여기에는 유선 또는 무선, 사무실 건물 간, 프레미스 데이터 센터, 인터넷 공급자 또는 ExpressRoute 파트너에 대한 연결 등 사무실 내의 모든 연결이 포함됩니다.

일반적으로 네트워크 가장자리에는 방화벽 및/또는 프록시 서버가 있는 하나 이상의 DMZ가 있습니다. 이 DMZ는 조직의 보안 정책을 적용하고 사용자가 설정하고 구성한 특정 네트워크 트래픽만 허용합니다. 이 네트워크를 관리하기 때문에 네트워크 성능을 직접 제어할 수 있으며 네트워크 내의 사이트와 네트워크에서 비즈니스용 Skype Online으로의 성능 유효성을 검사하기 위해 네트워크 평가를 완료하는 것이 좋습니다. 성능 요구 사항을 참조하세요. 비즈니스용 Skype Online의 미디어 품질 및 네트워크 연결 [성능을 참조하세요.](media-quality-and-network-connectivity-performance.md)

 **인터넷** 네트워크 외부에서 비즈니스용 Skype Online에 연결하는 사용자가 사용하는 전체 네트워크의 일부인 네트워크 세그먼트로, ExpressRoute가 구성되지 않은 경우 모든 연결에 사용됩니다. 인터넷 및 모든 연결은 사용자 또는 Microsoft에서 관리하지 않습니다. 따라서 성능 및 라우팅 경로를 결정하지 못하며 이는 전체 호출 흐름 및 품질에 가장 큰 영향을 미치게 됩니다.

 **ExpressRoute** 이는 전체 네트워크의 일부인 네트워크 세그먼트로, Microsoft 네트워크에 대한 전용 개인 연결을 제공합니다. 비즈니스용 Skype Online 실시간 통신과 같이 네트워크 속도 및 성능에 종속된 모든 워크로드에 대해 네트워크를 Microsoft 네트워크(Microsoft 365 또는 Office 365 데이터 센터)에 연결하는 데 권장되는 옵션입니다. ExpressRoute 연결은 네트워크와 Microsoft 네트워크 간에 만들어지며 ExpressRoute 연결 공급자는 [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-locations/) 연결 공급자를 사용하여 네트워크 정체 기간 동안 실시간 미디어의 성능을 향상시킬 수 있는 99.9%의 운영 시간 및 QoS(서비스 품질) 지원을 통해 개인 및 관리되는 네트워크를 제공합니다.

 **Microsoft 네트워크** Microsoft 365 및 Office 365 서비스를 지원하는 전체 네트워크의 일부인 네트워크 세그먼트입니다. 여기에는 Microsoft 365 또는 Office 365용 온라인 서버 간의 모든 통신이 포함됩니다. 여기에는 Microsoft 네트워크 백본을 트래버스하고 지리적 지역 간에 전송되는 트래픽이 포함됩니다.

### <a name="types-of-traffic"></a>트래픽 유형

비즈니스용 Skype Online의 네트워크 트래픽은 통화 흐름에서 별도의 경로로 표시되는 두 가지 광범위한 범주로 나뉩습니다.

 **실시간 미디어는** RTP(실시간 전송 프로토콜) 내에서 캡슐화되는 데이터로, 오디오, 비디오, 애플리케이션 공유 및 파일 전송 워크로드를 지원합니다. 일반적으로 미디어 트래픽은 대기 시간이 매우 길기 때문에 이 트래픽이 가능한 가장 직접적인 경로를 사용하고 TCP를 사용하면 대기 시간이 길어지기 때문에 전송 계층 프로토콜로 UDP를 사용하게 됩니다.

 **신호는** 클라이언트와 서버 간의 통신 링크 또는 활동을 제어하는 데 사용되는 다른 클라이언트(예: 호출이 시작될 때)를 전달하고, IM을 배달하는 데 사용됩니다. 대부분의 신호 트래픽은 SIP 프로토콜을 사용하나 일부 클라이언트는 HTTP 기반 REST 인터페이스를 사용합니다. 간단하게 만들기 위해 이 유형의 트래픽에서 HTTP 및 HTTPS 또는 TLS 연결을 통해 전달할 수 있는 다양한 신호를 고려하고 있습니다. 이 트래픽은 대기 시간에 훨씬 덜 민감하지만 엔드포인트 간의 대기 시간이 몇 초를 초과하는 경우 서비스 중단 또는 호출 시간 제한이 발생할 수 있다는 것을 이해하는 것이 중요합니다.

이 트래픽의 대상은 [모든 Microsoft 365 또는 Office 365 서비스의 Office 365 URL](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) 및 IP 주소 범위에서 찾을 수 있습니다. 각 URL에 대해 트래픽의 해당 부분이 Microsoft 365용 ExpressRoute 또는 Office 365를 트래버스할 수 있는지 여부를 나타냅니다. ExpressRoute를 사용할 때 일부 트래픽에 인터넷이 여전히 사용된다고 표시하는 다이어그램은 [Office 365용 Azure ExpressRoute를 참조하세요.](https://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd) ExpressRoute를 통해 라우팅할 수 있는 것으로 나열된 URL도 인터넷을 통해 라우팅할 수 있습니다. 즉, 일부 시나리오에서는 인터넷 또는 ExpressRoute를 사용할지 여부에 대한 결정은 클라이언트의 위치와 프록시 서버 및 방화벽의 구성에 따라 다릅니다. 또한 Microsoft 365 또는 Office 365와 연결된 모든 URL이 ExpressRoute를 사용할 수 있는 것은 아니기 때문에 ExpressRoute 파트너로부터 ExpressRoute를 구입하는 경우에도 인터넷 연결이 필요합니다.

인터넷을 통해만 전송할 수 있는 트래픽에는 CRL(인증서 해지 목록), DNS 검색 및 이름 확인, 공유 Microsoft 365 또는 Office 365 서비스의 URL(예: Microsoft 365 관리 센터) 및 비즈니스용 Skype Online의 일부 실시간 통신 기능(예: Skype 소비자와의 상호 운영을 위한 원격 분석 및 페더링)과 같은 일반적인 인터넷 종속성이 포함됩니다. Skype 모임 브로드캐스트를 위해 스트리밍된 미디어도 있습니다. 결정을 내릴 수 있도록 네트워크 라우팅을 계획할 때 더 많은 고려 사항은 [Office 365용 ExpressRoute를](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) 통해 라우팅을 참조합니다.

## <a name="principles-for-call-flows-with-skype-for-business"></a>비즈니스용 Skype를 통해 통화 흐름에 대한 원칙

특정 통화 흐름 시나리오의 세부 정보를 시작하기 전에 비즈니스용 Skype의 통화 흐름을 이해하는 데 도움이 되는 6개의 일반적인 원칙이 있습니다.

1. 비즈니스용 Skype 회의는 회의 이끌이가 있는 동일한 지역에서 호스팅됩니다. 이끌이가 온라인 사용자인 경우 클라우드에 있는 것이고, 모임 이끌이가온-프레미스 사용자인 경우, 클라우드에 있습니다.

2. 클라이언트에서 호스트된 회의로 전송된 미디어 트래픽은 항상 회의가 호스트되는 서버로 전송됩니다. 이 서버는 관리하는 데이터 센터 내의 On-Premises 서버 또는 클라우드 내의 온라인 서버일 수 있습니다. 그러나 Edge 서버는 항상 온라인 회의를 위한 미디어 흐름에 사용됩니다.

3. 피어 투 피어 호출에 대한 미디어 트래픽은 사용 가능한 가장 직접적인 경로를 취합니다. 기본 경로는 원격 피어(클라이언트)에 직접 연결되지만 트래픽을 차단하는 방화벽 또는 이러한 경로로 인해 해당 경로를 사용할 수 없는 경우 하나 이상의 Edge 서버가 트래픽을 릴레이합니다.

4. 신호 트래픽은 항상 사용자가 홈이 있는 서버(온라인 또는온-프레미스)로 전송됩니다. 프런트 엔드 서버를 직접 연결할 수 없는 경우 Edge 서버가 사용됩니다.

5. 온라인에서 호스팅되는 회의에 참가하는 사용자는 항상 Edge 서버를 사용하며 클라이언트 방화벽 구성으로 인해 필요한 경우 두 개를 사용할 수 있습니다.

6. 일반적으로 사용자가 프레미스에서 호스트되는 회의에 참가하는 경우, 에지 서버를 사용하지 않습니다. 이 네트워크는 일반적으로 프레미스 배포가 포함된 동일한 네트워크 내에서 연결하고 네트워크 외부에서 연결할 때 하나 또는 두 개의 Edge 서버를 사용하게 됩니다.

선택한 미디어 경로에 대한 자세한 내용은 [ICE - Edge Media Connectivity를 참조합니다.](https://aka.ms/AVEdge) 이 비디오는 Lync Server 2013에 대한 것이지만 원칙과 프로토콜은 비즈니스용 Skype에 계속 적용됩니다.

## <a name="skype-for-business-call-flows-with-expressroute"></a>ExpressRoute를 통해 비즈니스용 Skype 통화 흐름

이제 4개의 서로 다른 네트워크 세그먼트와 비즈니스용 Skype 통화 흐름에 대한 몇 가지 일반적인 가이던스 원칙을 이해했기만, 이 정보를 사용하여 ExpressRoute 네트워크 세그먼트를 트래버스할 비즈니스용 Skype 트래픽을 이해할 수 있습니다.

일반적으로 하나의 엔드포인트가 네트워크에 있으며 다른 엔드포인트가 Microsoft 365 또는 Office 365 데이터 센터에 있는 경우 네트워크 트래픽은 ExpressRoute 연결을 트래버스합니다. 여기에는 클라이언트와 서버 간의 신호 트래픽, 전화 회의 중에 사용되는 미디어 트래픽 또는 Online Edge 서버를 사용하는 피어 투 피어 호출이 포함됩니다.

두 엔드포인트가 모두 인터넷을 통해 직접 통신할 수 있는 경우 또는 네트워크 내에 있는 경우 트래픽은 ExpressRoute 연결을 트래버스하지 않습니다. 여기에는 피어 투 피어 호출을 위한 미디어, 인터넷에서 프레미스 배포로 전송되는 트래픽 또는 인터넷과 Microsoft 365 또는 Office 365 Edge 서버 간의 트래픽이 포함됩니다. 예를 들어 호텔의 온라인 회의에 참가하는 사용자가 있습니다.

## <a name="basic-skype-for-business-call-flow"></a>기본 비즈니스용 Skype 통화 흐름

위에서 설명한 비즈니스용 Skype 통화 흐름에 대한 일반 주체 적용을 지원하기 위해 이 문서의 다음 섹션에는 참조할 수 있는 여러 다이어그램이 포함되어 있습니다. 가능한 모든 호출 흐름의 전체 목록은 아니며 위에서 설명한 원칙을 적용하는 데 도움이 됩니다. 또한 다이어그램의 시나리오는 온라인, 하이브리드, 클라우드 커넥터를 비롯한 일반적인 배포 유형과 Skype 모임 브로드캐스트를 다루기 위해 선택되었습니다.

> [!NOTE]
> 비즈니스용 Skype에서 사용하는 트래픽의 하위 집합은 ExpressRoute를 통해 라우팅할 수 없습니다. 항상 인터넷 경로를 사용하게 됩니다. [Office 365 URL](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) 및 IP 주소 범위를 참조하여 영향을 받을 수 있는 URL을 확인할 수 있습니다.

### <a name="peer-to-peer-call-for-microsoft-365-or-office-365-user-from-within-customer-network"></a>고객 네트워크 내에서 Microsoft 365 또는 Office 365 사용자에 대한 피어 투 피어 호출
<a name="bk_Figure2"> </a>

피어 투 피어 호출의 경우 미디어 트래픽은 항상 대상에 대한 가장 직접적인 경로를 사용하게 됩니다. 그러나 신호 트래픽은 온라인 사용자가 있는 Microsoft 365 또는 Office 365 데이터 센터로 전송됩니다. 두 사용자가 모두 동일한 WAN에 있으며 클라이언트가 직접 통신할 수 없는 것은 아니기 때문에 미디어는 이들 간에 직접 흐르게 됩니다. 두 사용자 모두에 대한 신호 트래픽은 각 조직의 데이터 센터로 향하는 ExpressRoute 연결을 트래버스합니다. 이 시나리오에서 호출 흐름을 표시하기 위해 다음을 참조합니다.

 **피어 투 피어 호출 흐름**

![피어 투 피어 호출을 통해 흐름 호출](../images/f460369e-bfce-4a03-a031-d7e92c4ace89.png)

### <a name="online-user-on-your-network-joining-a-conference-that-is-hosted-online"></a>온라인에서 호스팅하는 회의에 참가하는 네트워크의 온라인 사용자
<a name="bk_Figure3"> </a>

피어 투 피어 예제에서 미디어 트래픽은 항상 대상에 대한 가장 직접적인 경로를 사용하게 됩니다. 그러나 온라인 회의의 경우 대상이 클라우드에 있습니다. 즉, 네트워크 내에서 회의에 참가하는 모든 사용자의 미디어 트래픽이 ExpressRoute 연결을 트래버스하고 신호 트래픽이 클라우드로 전송됩니다. 아래 그래픽에서는 미디어와 신호가 모두 네트워크 내의 사용자에 대한 ExpressRoute 연결을 트래버스하고 커피숍이나 호텔과 같이 네트워크 외부에서 인터넷에 연결된 사용자의 인터넷을 직접 트래버스하는 것을 보여줍니다.

회의 위치는 참가자가 아닌 모임 이끌이가 정의합니다. 즉, 모임이 주문형 고객이 모임을 예약한 경우 미디어 트래픽이 ExpressRoute를 통해 클라우드로 흐르지 않고 대신 인터넷을 모임 이끌이의 프레미스 데이터 센터로 트래버스합니다.

온라인 회의 미디어의 대상은 Microsoft 365 또는 Office 365 클라우드 내의 데이터 센터이지만 데이터 센터는 회의에 참가하는 사용자와 다른 지역에 있을 수 있습니다. 이 방법은 다음 두 가지 방법 중 하나에서 발생될 수 있습니다.

- 모임 이끌이가 참석자 또는 참가자가 다른 회사에 있는 경우 이끌이의 조직이 다른 지리적 위치 또는 국가/지역에서 호스팅됩니다.

- 회사가 다국적이거나 사용자가 출장 중이기 때문에 사용자가 회사의 조직이 있는 다른 국가/지역에서 가입하는 경우.

이 시나리오에서 ExpressRoute를 사용하는 경우 ExpressRoute 프리미엄 추가 기능을 사용할 경우 모임 조직의 데이터 센터 이끌이의 지리적 지역에 관계없이 ExpressRoute 경로를 따르는 데이터가 Microsoft의 백본에 자동으로 전달됩니다.

 **온라인 모임 통화 흐름이 있는 온라인 사용자**

![온라인 호스팅 전화 회의에 대한 통화 흐름입니다.](../images/22d9ee64-b20c-4079-b3d1-a7a806b9a0bc.png)

### <a name="joining-a-conference-hosted-by-on-premises-user-in-hybrid-deployment"></a>하이브리드 배포에서 On-프레미스 사용자가 호스트하는 회의 참가
<a name="bk_Figure3"> </a>

호스팅된 회의를 지원하는 회의 서버는 모임 이끌이가 있는 위치가 결정됩니다. 이 시나리오에서는 하이브리드 배포의 On-프레미스 사용자가 예약한 회의에 참가하는 모든 사용자의 미디어가 프레미스 데이터 센터로 흐르게 됩니다. 온라인 홈 사용자에 대한 신호는 클라우드의 조직을 통해 설정됩니다. 미디어는 직접 연결을 시도합니다. 이 시나리오에서는 두 사용자가 네트워크 내에서 연결하기 때문에 직접 미디어 연결이 가능하기 때문에 ExpressRoute는 온라인 홈 사용자에 대한 트래픽 신호에만 사용됩니다. 온라인 홈 사용자가 인터넷에서 연결하는 경우 온라인 Edge 서버가 연결에 사용되는 경우 미디어가 ExpressRoute를 트래버스할 수 있습니다.

 **하이브리드 사용자 호출 흐름에서 호스트하는 회의**

![호스트된 onprem 호출 흐름입니다.](../images/9e669859-19f3-4a86-95b7-7185eb421ccd.png)

### <a name="on-premises-edge-server-with-microsoft-365-or-office-365-hosted-conferences"></a>Microsoft 365 또는 Office 365에서 호스팅되는 회의가 있는 프레미스 Edge 서버
<a name="bk_Figure5"> </a>

하이브리드 사용자가 온라인 호스팅 회의에 참가하면 신호 및 미디어가 Microsoft 365 또는 Office 365 클라우드로 전송됩니다. 사용자가 인터넷에서 참가하기 때문에 일반적으로 직접 인터넷 경로가 사용됩니다. 그러나 방화벽 제한으로 인해 인터넷 직접 경로를 사용할 수 없는 경우도 있습니다. 이 경우, 클라우드로 ExpressRoute 회로를 트래버스하기 전에 미디어 트래픽이 클라우드로 돌아오게 하는 미디어 트래픽을 릴레이할 수 있습니다.

 **온-프레미스 Edge 서버를 사용하여 온라인 전화 회의에 참가하는온-프레미스 사용자**

![에지 서버를 통과하는 전화 회의에 대한 통화 흐름입니다.](../images/0178c170-5837-430d-84f1-582784bfef55.png)

### <a name="pstn-call-using-skype-for-business-cloud-connector-edition"></a>비즈니스용 Skype Cloud Connector Edition을 사용한 PSTN 통화
<a name="bk_Figure6"> </a>

비즈니스용 [Skype Online Cloud Connector Edition을](https://aka.ms/CloudConnectorInstaller) 사용하면 SIP 트렁크 또는 PSTN 게이트웨이와 같은온-프레미스 리소스를 사용하는 PSTN 연결을 제공하거나 최소한의 하드웨어 장치를 사용하여 비즈니스용 Skype와 통합할 수 있습니다. Cloud Connector Edition을 사용하여 사용자는 온라인에 있으며 통화 계획을 포함하지 않는 경우 일반 온라인 사용자 역할을 합니다. PSTN 시나리오에 대한 신호는 사용 가능한 경우 ExpressRoute 연결을 통해 클라이언트와 클라우드 간에 이동하고 미디어 트래픽은 WAN 내에 있습니다. 이 경우 신호는 Microsoft 365 또는 Office 365 클라우드에서 전환되고 클라우드 커넥터에서 종료됩니다.

 **Microsoft 365 또는 Office 365 및 클라우드 커넥터의 전화 시스템을 통한 PSTN 통화**

![클라우드 PBX Cloud Connector를 사용하여 PSTN 호출에 대한 호출 흐름입니다.](../images/e48d0f2b-fa1e-4b43-b3dd-d34a33dcdf36.png)

### <a name="skype-meeting-broadcast-with-users-joining-from-customer-network"></a>고객 네트워크에서 참가하는 사용자와 Skype 모임 브로드캐스트
<a name="bk_Figure6"> </a>

Skype 모임 브로드캐스트는 서로 다른 네트워크 전송 프로필을 갖는 각 부분으로 구성된 두 부분으로 구성된 특별한 사용 사례입니다. 첫 번째 부분과 네트워크 성능의 보기에서 가장 중요한 부분은 내부 모임입니다. 클라우드에서 회의 서버에 연결하는 하나 이상의 클라이언트 엔드포인트를 포함하는 모임의 실시간 부분입니다. 모임의 이 부분을 사용하여 전송되는 데이터는 사용자가 온라인 회의에 참가하는 위의 예와 똑같은 것입니다.

Skype 모임 브로드캐스트를 고유하게 만드는 것은 모임이 브로드캐스트 스트리밍 서비스를 사용하여 많은 회의 참석자에게 배포되는 것입니다. 이 브로드캐스트 스트리밍 서비스는 ExpressRoute를 통해 라우팅할 수 없지만 대신 CDN(Content Delivery Network) 서비스의 선택적 지원으로 인터넷을 사용합니다. 참석자는 수신 대기 시간, 패킷 손실 및 지터와 같은 네트워크 성능 문제에 훨씬 덜 민감하기 때문에 브로드캐스트 스트리밍이 단방향 미디어 흐름인 것을 인식하는 데 도움이 됩니다. 이러한 문제에 대한 브로드캐스트 트래픽을 최적화하는 대신 스트리밍된 미디어를 수신하는 참석자 수가 매우 명이기 때문에 대역폭 사용률에 최적화됩니다.

 **고객 네트워크의 사용자와 Skype 모임 브로드캐스트**

![Skype 모임 브로드캐스트에 대한 통화 흐름입니다.](../images/cbe0e9f3-7eee-47e9-b61e-f2780b525dea.png)

## <a name="call-flow-patterns-by-deployment-type"></a>배포 유형별로 흐름 패턴 호출

위의 일반적인 호출 흐름 예제와 트래픽 패턴을 제어하는 일반적인 원칙에 대한 이해를 통해 아래 표에서는 배포 및 사용 시나리오의 대규모 조합에 대한 트래픽 패턴의 요약을 제공합니다. 이러한 테이블은 호출 흐름의 가능한 모든 조합을 캡처하지는 않지만 호출 흐름의 일반적인 원칙을 더 잘 이해하는 데 도움이 됩니다.

데이터가 전송되고 조직에 로컬로 나열됩니다. 고객 네트워크, 인터넷 또는 ExpressRoute를 떠날 수 없습니다. 아래 나열된 패턴은 방화벽, 페더레인 및 인터넷과 같은 가장 일반적인 네트워크 설정을 기반으로 하여 다자 또는 페더러드 흐름에 관련된 모든 조직에 ExpressRoute가 있는 것으로 가정합니다. 실제로 설정이 다르면 아래에 나열된 트래픽 패턴과 다른 트래픽 패턴이 있을 수 있습니다.

### <a name="call-flows-for-skype-for-business-online"></a>비즈니스용 Skype Online 통화 흐름

비즈니스용 Skype Online 사용 시나리오에는 온라인에 있는 사용자가 포함하며 내부 네트워크 또는 인터넷에서 전화를 걸 수 있습니다. 모든 회의 또는 PSTN 관련 미디어가 클라우드로 흐르고 온라인 사용자 에지 서버도 클라우드에 있습니다.

 **비즈니스용 Skype Online의 통화 흐름 요약**

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**사용 시나리오** <br/> |**엔드포인트** <br/> |**신호 경로** <br/> |**미디어 경로** <br/> |**예제 흐름** <br/> |**참고** <br/> |
|피어 투 피어 호출  <br/> |두 클라이언트, 둘 다 네트워크에 있습니다.  <br/> |ExpressRoute  <br/> |로컬  <br/> |[고객 네트워크 내에서 Microsoft 365 또는 Office 365 사용자에 대한 피어 투 피어 호출](call-flow-using-expressroute.md#bk_Figure2) <br/> ||
|피어 투 피어 호출  <br/> |네트워크(내부)에 있는 클라이언트와 인터넷의 다른 클라이언트(외부)의 두 클라이언트.  <br/> |내부 사용자: ExpressRoute  <br/> 외부 사용자: 인터넷  <br/> |내부 사용자: ExpressRoute  <br/> 외부 사용자: 인터넷에서 Microsoft 365 또는 Office 365 Edge 서버로  <br/> |[고객 네트워크 내에서 Microsoft 365 또는 Office 365 사용자에 대한 피어 투 피어 통화](call-flow-using-expressroute.md#bk_Figure2) <br/> |방화벽이 온라인 에지 서버가 필요한 클라이언트 간의 직접 연결을 차단했다고 가정합니다. 내부 사용자에서 Online Edge 서버로의 트래픽은 전화 회의용 회의 서버와 비슷한 경로를 따르게 됩니다.  <br/> |
|페더링된 조직의 사용자에 대한 피어 투 피어 호출  <br/> |네트워크(내부) 및 페더러드 조직의 네트워크(페더화)에 있는 온라인 사용자에 있는 두 개의 클라이언트  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[온라인에서 호스팅하는 회의에 참가하는 네트워크의 온라인 사용자](call-flow-using-expressroute.md#bk_Figure3) <br/> |방화벽이 클라이언트 간의 직접 연결을 차단하여 Online Edge 서버가 필요한 것으로 가정합니다. 내부 사용자에서 Online Edge 서버로의 트래픽은 전화 회의용 회의 서버와 비슷한 경로를 따르게 됩니다.  <br/> |
|고객 네트워크에서 사용자의 전화 회의 참가  <br/> |네트워크의 클라이언트 및 클라우드의 회의 서버.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[온라인에서 호스팅하는 회의에 참가하는 네트워크의 온라인 사용자](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|인터넷에서 사용자의 전화 회의 참가  <br/> |클라이언트가 클라우드의 인터넷 및 회의 서버에 있습니다.  <br/> |인터넷  <br/> |인터넷  <br/> |[온라인에서 호스팅하는 회의에 참가하는 네트워크의 온라인 사용자](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|다른 회사의 On-prem Server에서 호스팅하는 회의 참가  <br/> |타사 데이터 센터의 네트워크 및 회의 서버의 클라이언트.  <br/> |인터넷  <br/> |인터넷  <br/> |해당 사항 없음  <br/> |회의를 호스트하는 회의 서버는 다른 고객의 프레미스 네트워크에 있는 것이기 때문에 Microsoft 클라우드를 통해 데이터가 전달되지 않습니다.  <br/> |
|PSTN 통화  <br/> |고객 네트워크의 클라이언트 및 클라우드의 전화 시스템 서버  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[온라인에서 호스팅하는 회의에 참가하는 네트워크의 온라인 사용자](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|PSTN 통화  <br/> |클라우드의 인터넷 및 전화 시스템 서버의 클라이언트  <br/> |인터넷  <br/> |인터넷  <br/> |해당 사항 없음  <br/> |미디어 및 신호는 Microsoft 365 또는 Office 365 데이터 센터로 전달됩니다. 클라이언트 엔드포인트가 인터넷에 있는 경우 모든 데이터가 인터넷을 통해 Microsoft 데이터 센터로 흐르게 됩니다(온라인 에지 서버가 연결에 필요한 경우에도).  <br/> |

> [!NOTE]
> ExpressRoute는 회사 네트워크에 있는 사용자의 미디어 경로에서 온라인 에지 서버로 사용되지만 다른 고객의 온라인 프레미스 배포용 Edge 서버를 사용하는 경우 사용되지 않습니다.

### <a name="call-flows-for-skype-for-business-hybrid"></a>비즈니스용 Skype 하이브리드에 대한 통화 흐름

하이브리드 통화 흐름은 비즈니스용 Skype 배포가 있는 경우에 적용됩니다. 이 배포에는 적어도 일부 사용자가 홈에 있습니다. 이 섹션의 호출 흐름에는 하나 이상의 On-프레미스 홈 사용자와의 피어 투 피어 또는 PSTN 통화가 모두 포함됩니다.

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**사용 시나리오** <br/> |**엔드포인트** <br/> |**신호 경로** <br/> |**미디어 경로** <br/> |**예제 흐름** <br/> |**참고** <br/> |
|피어 투 피어 호출  <br/> |고객 네트워크와 홈에 있는 두 개의 클라이언트  <br/> |로컬  <br/> |로컬  <br/> |[고객 네트워크 내에서 Microsoft 365 또는 Office 365 사용자에 대한 피어 투 피어 호출](call-flow-using-expressroute.md#bk_Figure2) <br/> |사용자가 홈인-프레미스이기 때문에 신호는 클라우드가 아닌 로컬로 클라우드 데이터 센터로 전달됩니다.  <br/> |
|피어 투 피어 호출  <br/> |두 클라이언트, 둘 다 고객 네트워크에서 연결합니다. 하나는 온라인에, 다른 하나는 홈인 온라인입니다.  <br/> |온라인 사용자: ExpressRoute  <br/> 프레미스 사용자: 로컬  <br/> |로컬  <br/> |[고객 네트워크 내에서 Microsoft 365 또는 Office 365 사용자에 대한 피어 투 피어 통화](call-flow-using-expressroute.md#bk_Figure2) <br/> |온라인 홈 사용자만 클라우드에 신호 트래픽을 전송합니다.  <br/> |
|페더링된 조직의 사용자에 대한 피어 투 피어 호출  <br/> |고객 네트워크(내부)의 프레미스 사용자와 페더러드 회사 네트워크(페더화)의 온라인 사용자 두 클라이언트.  <br/> |내부 사용자: 로컬  <br/> 페더리된 사용자: ExpressRoute  <br/> |인터넷 또는 ExpressRoute(온라인 또는온-프레미스 에지 서버를 사용하는지 여부에 따라 다를 수 있습니다.)  <br/> |[](call-flow-using-expressroute.md#bk_Figure3) [Microsoft 365 또는 Office 365에서](call-flow-using-expressroute.md#bk_Figure5) 호스트되는 회의(미디어 트래픽용)를 통해 온라인에서 호스팅되는 회의 및 온라인 프레미스 Edge 서버의 일부에 참가하는 네트워크의 온라인 사용자입니다. <br/> |방화벽이 클라이언트 간의 직접 연결을 차단하여 Online Edge 서버가 필요한 것으로 가정합니다. ICE 협상은 연결에 대해 온라인(온라인 사용자)과 온라인 프레미스 Edge 서버(On-프레미스 사용자)를 모두 제공합니다.  <br/> |
|고객 네트워크의 사용자가 전화 회의에 참가(온라인 사용자가 예약한 회의)  <br/> |네트워크의 프레미스 사용자 및 클라우드의 회의 서버.  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[온라인에서 호스팅하는 회의에 참가하는 네트워크의 온라인 사용자](call-flow-using-expressroute.md#bk_Figure3) <br/> |전화 회의를 위한 서버 리소스는 모임 이끌이가 정의합니다. 이 경우 온라인 사용자가 예약한 리소스가 클라우드에 있습니다.  <br/> |
|PSTN 통화  <br/> |네트워크 및 비즈니스용 Skype 데이터 센터의 프레미스 사용자  <br/> |로컬  <br/> |로컬  <br/> |[비즈니스용 Skype Cloud Connector Edition을 사용한 PSTN 통화](call-flow-using-expressroute.md#bk_Figure6) <br/> |사용자가 홈인 것을 제외하고 Cloud Connector Edition을 사용하는 유사한 시나리오로, 신호는 네트워크 내에 유지됩니다.  <br/> |

### <a name="call-flows-for-skype-for-business-with-cloud-connector"></a>클라우드 커넥터를 사용하여 비즈니스용 Skype 통화 흐름

Cloud Connector Edition에 연결할 사용자는 모두 홈 온라인입니다. 즉, 회의가 온라인이 됐고 신호는 온라인 사용자와 동일한 패턴을 따르는 것입니다. PSTN 통화가 아니라 다른 시나리오의 경우 통화 흐름은 위에서 설명한 비즈니스용 Skype Online의 경우와 똑같은 것입니다.

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**사용 시나리오** <br/> |**엔드포인트** <br/> |**신호 경로** <br/> |**미디어 경로** <br/> |**예제 흐름** <br/> |**참고** <br/> |
|PSTN 통화  <br/> |Cloud Connector Edition을 사용하여 네트워크의 온라인 사용자입니다.  <br/> |로컬  <br/> |로컬  <br/> |[비즈니스용 Skype Cloud Connector Edition을 사용한 PSTN 통화](call-flow-using-expressroute.md#bk_Figure6) <br/> ||
|PSTN 통화  <br/> |Cloud Connector Edition을 사용하여 인터넷을 사용하는 온라인 사용자입니다.  <br/> |인터넷  <br/> |인터넷  <br/> |비즈니스용 Skype Cloud Connector Edition을 사용하는 [Microsoft 365 또는 Office 365](call-flow-using-expressroute.md#bk_Figure5) 호스팅 회의 및 PSTN 통화와의 [On-Premises Edge](call-flow-using-expressroute.md#bk_Figure6)서버 조합.  <br/> |인터넷 사용자는 클라우드 커넥터에 포함된 Edge 서버를 통해 연결하고 클라우드 커넥터는 PSTN 네트워크에 연결합니다.  <br/> |

## <a name="related-topics"></a>관련 항목

[ExpressRoute 설명서](https://go.microsoft.com/fwlink/?LinkId=690285)


