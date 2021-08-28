---
title: 서비스 품질 구현 Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: 조직에서 QoS(품질 품질)에 대한 조직의 네트워크를 준비하는 방법을 Microsoft Teams.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.qos
- ms.teamsadmincenter.meetingsettings.network.qosmarkers
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3547f23d43f07d8de28ba8ca53626be119de30de
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595290"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>서비스 품질(QoS)을 Microsoft Teams

서비스 품질(QoS)Microsoft Teams 네트워크 지연(예: 음성 또는 비디오 스트림)에 민감한 실시간 네트워크 트래픽이 덜 민감하지 않은 트래픽(예: 다운로드할 추가 초가 큰 거래가 아닌 경우)의 트래픽 앞에서 "줄을 끊습니다"를 허용합니다. QoS는 Windows 그룹 정책 개체 및 포트 기반 액세스 제어 목록을 사용하여 실시간 스트림에서 모든 패킷을 식별하고 표시합니다. 이렇게 하면 네트워크에서 음성, 비디오 및 화면 공유가 네트워크 대역폭의 전용 부분을 스트리밍할 수 있습니다.

이 문서에 설명된 문제 중 한 가지가 발생하는 대규모 사용자 그룹을 지원하는 경우 QoS를 구현해야 할 수 있습니다. 사용자 수가 적은 소규모 기업에서는 QoS가 필요하지 않을 수 있지만, 이 경우에도 도움이 될 수 있습니다.

일부 형태의 QoS가 없는 경우 음성 및 비디오에서 다음과 같은 품질 문제가 표시될 수 있습니다.

- Jitter – 다른 요금으로 도착하는 미디어 패킷으로 인해 통화에서 단어나 음성이 누락될 수 있습니다.
- 패킷 손실 – 패킷이 삭제되어 음성 품질이 낮아지며 음성을 이해하기가 어려워질 수 있습니다.
- RTT(지연된 왕복 시간) – 미디어 패킷이 대상에 도달하는 데 시간이 오래 늦어 대화의 두 당사자 간에 눈에 띄게 지연되고 사람들이 서로 대화할 수 있도록 합니다.

이러한 문제를 해결하기 위해 가장 복잡한 방법은 데이터 연결의 크기를 늘리는 것입니다. 비용이 많이 들기 때문에 QoS는 대역폭을 추가하는 대신 사용자가 확보한 리소스를 보다 효과적으로 관리할 수 있는 방법을 제공합니다. 품질 문제를 해결하기 위해 먼저 QoS를 사용한 다음 필요한 경우 대역폭을 추가하는 것이 좋습니다.

QoS가 효과적이기 위해 조직 전체에서 일관된 QoS 설정을 적용해야 합니다. QoS 우선 순위를 지원하지 못하는 경로의 일부가 통화, 비디오 및 화면 공유의 품질을 저하할 수 있습니다. 여기에는 모든 사용자 PC 또는 디바이스, 네트워크 스위치, 인터넷에 라우터 및 Teams 포함됩니다.

_그림 1. 조직의 네트워크와 서비스 간의 Microsoft 365 Office 365 관계_

![네트워크와 서비스 간의 관계에 대한 그림](media/Qos-in-Teams-Image1.png "조직의 네트워크와 Microsoft 365 또는 Office 365 서비스 간의 관계: 프레미스 Microsoft 365 디바이스는 상호 연결 네트워크와 연결됩니다. 따라서 클라우드 음성 및 오디오 회의 Microsoft 365 Office 365 연결됩니다.")

## <a name="qos-implementation-checklist"></a>QoS 구현 검사 목록

높은 수준에서 QoS를 구현하기 위해 다음을 실행합니다.

1. [네트워크가 준비되어 있는지 확인합니다.](#make-sure-your-network-is-ready)

1. [QoS](#select-a-qos-implementation-method)구현 방법을 선택합니다.

1. [각 미디어 유형에 대한 초기 포트 범위를 선택 합니다.](#choose-initial-port-ranges-for-each-media-type)

1. QoS 설정 구현:
   1. GPO(그룹 정책 개체)를 사용하여 클라이언트 디바이스 포트 범위 및 표시를 설정하는 [클라이언트에서](QoS-in-Teams-clients.md)
   2. 라우터(제조업체 설명서 참조) 또는 기타 네트워크 디바이스에서 여기에는 ACL(포트 기반 액세스 제어 목록)을 포함하거나 QoS 큐 및 DSCP 표시를 정의하거나 이러한 모든 항목만 정의할 수 있습니다.

      > [!IMPORTANT]
      > 클라이언트 원본 포트 및 "any"의 원본 및 대상 IP 주소를 사용하여 이러한 QoS 정책을 구현하는 것이 좋습니다. 이렇게 하면 내부 네트워크에서 들어오는 미디어 트래픽과 외부 미디어 트래픽이 모두 포획됩니다.  

   3. 모임에 대한 미디어 트래픽을 처리하는 [Teams 설정합니다.](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

5. [네트워크의 트래픽을 Teams QoS](#validate-your-qos-implementation) 구현의 유효성을 검사합니다.

QoS를 구현할 준비를 할 때 다음 지침을 염두에 두세요.

- 가장 짧은 경로는 Microsoft 365 가장 짧습니다.
- 포트를 닫는 경우 품질 저하만 발생할 수 있습니다.
- 그 사이에 있는 장애물(예: proxies)은 권장되지 않습니다.
- 홉 수를 제한합니다.
  - 클라이언트에서 네트워크 에지로 – 3~5개 홉
  - MICROSOFT 네트워크 에지로 ISP - 3홉
  - Microsoft 네트워크 에지에서 최종 대상까지 - 관련이 없습니다.

방화벽 포트 구성에 대한 자세한 내용은 URL 및 [IP Office 365 으로 이동하세요.](office-365-urls-ip-address-ranges.md)

## <a name="make-sure-your-network-is-ready"></a>네트워크가 준비되어 있는지 확인합니다.

QoS 구현을 고려하는 경우 대역폭 요구 사항 및 기타 네트워크 요구 사항을 이미 [결정해야 합니다.](prepare-network.md)
  
네트워크의 트래픽 정체는 미디어 품질에 크게 영향을 줍니다. 대역폭이 부족하면 성능 저하와 사용자 환경이 저하됩니다. 채택 및 Teams 증가함에 따라 [보고,](use-call-analytics-to-troubleshoot-poor-call-quality.md)사용자당 통화 분석 및 [CQD(품질 대시보드)를](turning-on-and-using-call-quality-dashboard.md) 사용하여 문제를 식별한 다음 QoS 및 선택적 대역폭 추가를 사용하여 조정합니다.

### <a name="vpn-considerations"></a>VPN 고려 사항

QoS는 호출자 간의 모든 링크에서 구현될 때만 예상대로 작동합니다. 내부 네트워크에서 QoS를 사용하며 사용자가 원격 위치에서 로그인하는 경우 관리되는 내부 네트워크 내에서만 우선 순위를 지정할 수 있습니다. 원격 위치는 VPN(가상 사설 네트워크)을 구현하여 관리되는 연결을 받을 수 있습니다. VPN은 기본적으로 패킷 오버헤드를 추가하고 실시간 트래픽에 지연을 만듭니다. VPN을 통해 실시간 통신 트래픽을 실행하지 않는 것이 좋습니다.

대륙을 아우르는 관리되는 링크가 있는 글로벌 조직에서는 이러한 링크에 대한 대역폭이 LAN과 비교하여 제한되어 있기 때문에 QoS를 강력히 추천합니다.

## <a name="introduction-to-qos-queues"></a>QoS 큐 소개

QoS를 제공하려면 네트워크 디바이스는 트래픽을 분류하는 방법이 있어야 합니다. 다른 네트워크 트래픽과 음성 또는 비디오를 구분할 수 있어야 합니다.

네트워크 트래픽이 라우터에 들어오면 트래픽이 큐에 배치됩니다. QoS 정책이 구성되지 않은 경우 하나의 큐만 있으며 모든 데이터는 동일한 우선 순위가 있는 선행, 선출으로 처리됩니다. 즉, 음성 트래픽(지연에 매우 민감)이 트래픽 뒤에 늦어지며 몇 밀리초의 지연이 문제가되지 않을 수 있습니다.

QoS를 구현할 때 Cisco의 우선 순위 큐 및 [CBWFQ(Class-Based Weighted Fair Queueing)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) 및 정체 방지 기능(예: [WRED)과](https://en.wikipedia.org/wiki/Weighted_random_early_detection)같은 여러 정체 관리 기능 중 하나를 사용하여 여러 큐를 정의합니다.

_그림 2. QoS 큐의 예_

![QoS 큐 및 대역폭 분할 그림](media/Qos-in-Teams-Image2.png "사용 가능한 총 대역폭은 여러 큐(오디오, 비디오 및 기타 트래픽)로 나뉘며, 우선 순위가 서로 다릅니다.")

간단한 비유는 QoS가 데이터 네트워크에서 가상 "카풀 차선"을 만들어 일부 유형의 데이터가 지연되거나 거의 발생하지 않습니다. 이러한 차선을 만들면 조직의 사용자에 대한 비즈니스 등급 환경을 제공하면서 상대 크기를 조정하고 연결 대역폭을 훨씬 효율적으로 관리할 수 있습니다.

## <a name="select-a-qos-implementation-method"></a>QoS 구현 방법 선택

네트워크의 라우터에서 ACL(액세스 제어 목록)을 사용하여 포트 기반 태그를 통해 QoS를 구현할 수 있습니다. 포트 기반 태그 지정은 혼합된 Windows, Mac 및 Linux 환경에서 작동하고 구현하기가 가장 쉬우기 때문에 가장 신뢰할 수 있는 방법입니다. 모바일 클라이언트는 DSCP 값을 사용하여 트래픽을 표시하는 메커니즘을 제공하지 않습니다. 따라서 이 메서드가 필요하게 됩니다.  

포트 기반 태그를 사용하여 네트워크의 라우터는 들어오는 패킷을 검사하고 패킷이 특정 포트 또는 포트 범위를 사용하여 도착한 경우 해당 패킷을 특정 미디어 유형으로 식별하고 해당 형식의 큐에 넣습니다. IP 패킷 헤더에 미리 정해진 [DSCP](https://tools.ietf.org/html/rfc2474) 표시를 추가하여 다른 디바이스가 트래픽 유형을 인식하고 큐에서 우선 순위를 부여할 수 있습니다.

포트 기반 태그는 플랫폼에서 작동하나 WAN 에지에서만 트래픽을 표시하고(클라이언트 컴퓨터로의 모든 방식이 아는 것은 아 않습니다. ) 관리 오버헤드를 만듭니다. 이 메서드를 구현하는 방법에 대한 지침은 라우터 제조업체에서 제공하는 설명서를 참조하세요.

### <a name="insert-dscp-markers"></a>DSCP 마커 삽입

GPO(그룹 정책 개체)를 사용하여 특정 트래픽 유형(예: 음성)으로 식별하는 IP 패킷 헤더에 DSCP 마커를 삽입하는 클라이언트 디바이스를 지시하여 QoS를 구현할 수도 있습니다. 라우터 및 기타 네트워크 디바이스는 이를 인식하고 트래픽을 우선 순위가 높은 별도의 큐에 넣도록 구성할 수 있습니다.

이 시나리오는 완전히 유효하기는 하지만 도메인에 가입된 클라이언트에서만 Windows 합니다. 도메인에 가입된 클라이언트가 아닌 Windows DSCP 태그 지정에는 사용할 수 없습니다. 실행 중인 macOS와 같은 다른 클라이언트에는 하드 코딩된 태그가 있으며 항상 트래픽에 태그를 지정합니다.

또한 GPO를 통해 DSCP 마킹을 제어하면 도메인에 가입된 모든 컴퓨터가 동일한 설정을 받고 관리자만 관리할 수 있습니다. GPO를 사용할 수 있는 클라이언트는 원래 디바이스에 태그가 지정된 다음, 구성된 네트워크 디바이스는 DSCP 코드로 실시간 스트림을 인식하고 적절한 우선 순위를 지정합니다.

### <a name="best-practice"></a>모범 사례

가능한 경우 엔드포인트의 DSCP 표시와 라우터의 포트 기반 ACL을 조합하는 것이 좋습니다. GPO를 사용하여 대부분의 클라이언트를 포획하고 포트 기반 DSCP 태그를 사용하면 모바일, Mac 및 기타 클라이언트가 여전히 QoS 처리(부분적으로)를 받을 수 있습니다.

DSCP 표시는 배달이 얼마나 긴급한지와 빠른 배달을 위해 정렬하는 가장 좋은 방법을 나타내는 우편물 스탬프에 비유할 수 있습니다. 실시간 미디어 스트림에 우선 순위를 제공하도록 네트워크를 구성한 후 패킷 손실 및 늦은 패킷은 크게 감소해야 합니다.

네트워크의 모든 디바이스가 동일한 분류, 표시 및 우선 순위를 사용하는 경우 각 트래픽 유형에 사용되는 큐에 할당된 포트 범위의 크기를 변경하여 지연, 삭제된 패킷 및 지터를 줄이거나 제거할 수 있습니다. Teams 관점에서 가장 중요한 구성 단계는 패킷의 분류 및 표시입니다. 그러나 종단 내지 엔드 QoS가 성공하려면 애플리케이션의 구성을 주된 네트워크 구성과 신중하게 조정해야 합니다. QoS가 완전히 구현된 후 지속적인 관리는 조직의 요구와 실제 사용량에 따라 각 트래픽 유형에 할당된 포트 범위를 조정하는 문제입니다.

## <a name="choose-initial-port-ranges-for-each-media-type"></a>각 미디어 유형에 대한 초기 포트 범위 선택

DSCP 값은 DSCP 표시가 클라이언트에 의해 할당되거나 ACL 설정에 따라 네트워크 자체에 할당되어 있는지 여부에 따라 해당 구성된 네트워크에 패킷 또는 스트림을 제공해야 하는 우선 순위를 알 수 있습니다. 각 미디어 워크로드는 고유한 DSCP 값을 얻습니다(다른 서비스는 워크로드가 DSCP 마킹을 공유하도록 허용할 수 Teams) 각 미디어 유형에 사용되는 정의된 별도의 포트 범위입니다. 다른 환경에는 기존 QoS 전략이 있을 수 있습니다. 이는 네트워크 워크로드의 우선 순위를 결정하는 데 도움이 됩니다.

서로 다른 실시간 스트리밍 워크로드에 대한 포트 범위의 상대 크기는 해당 워크로드에 전용으로 사용 가능한 총 대역폭의 비율을 설정합니다. 이전 우편 비유로 돌아가기 위해 " Air Mail" 스탬프가 있는 편지는 가장 가까운 공항으로 1시간 이내에 도착할 수 있습니다. "Bulk Mail" 표시가 표시된 작은 패키지는 일련의 트럭을 통해 육로로 이동하기 전에 하루를 기다릴 수 있습니다.

_권장되는 초기 포트 범위_

|미디어 트래픽 유형| 클라이언트 원본 포트 범위  |프로토콜|DSCP 값|DSCP 클래스|
|:--- |:--- |:--- |:--- |:--- |
|오디오| 50,000~50,019|TCP/UDP|46|Expedited Forwarding(EF)|
|비디오| 50,020~50,039|TCP/UDP|34|Assured Forwarding(AF41)|
|응용 프로그램/화면 공유| 50,040~50,059|TCP/UDP|18|Assured Forwarding(AF21)|
||||||

이러한 설정을 사용할 때 다음을 유의하세요.

- 향후 ExpressRoute를 구현할 계획이고 아직 QoS를 구현하지 않은 경우 DSCP 값이 보낸 사람에서 받는 사람으로 동일한지 지침을 따르는 것이 좋습니다.

- 모바일 클라이언트 및 Teams 디바이스를 포함한 모든 클라이언트는 이러한 포트 범위를 사용하며, 이러한 원본 포트 범위를 사용하는 구현하는 모든 DSCP 정책의 영향을 받는다. 동적 포트를 계속 사용할 클라이언트는 브라우저 기반 클라이언트(참가자가 브라우저를 사용하여 모임에 참가할 수 있도록 하는 클라이언트)입니다.

- Mac 클라이언트는 동일한 포트 범위를 사용하나 오디오(EF) 및 비디오(AF41)에 대해 하드 코딩된 값도 사용합니다. 이러한 값은 구성할 수 없습니다.

- 나중에 사용자 환경을 개선하기 위해 포트 범위를 조정해야 하는 경우 포트 범위는 겹칠 수 없습니다. 서로 인접해야 합니다.

## <a name="migrate-qos-to-teams"></a>QoS를 Teams

이전에 QoS 태그 비즈니스용 Skype 포트 범위를 포함하여 Online에서 배포한 경우 이제 배포 중입니다. Teams Teams 구성을 존중하고 클라이언트와 동일한 포트 범위 및 태그 지정을 비즈니스용 Skype 합니다. 대부분의 경우 추가 구성이 필요하지 않습니다.

> [!NOTE]
> 그룹 정책을 통해 애플리케이션 이름 QoS 태그를 사용하는 경우 애플리케이션 이름으로 Teams.exe 추가해야 합니다.

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a>PowerShell을 사용하여 Teams Windows QoS 구현

**오디오용 QoS 설정**

```powershell
new-NetQosPolicy -Name "Teams Audio" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50000 -IPSrcPortEndMatchCondition 50019 -DSCPAction 46 -NetworkProfile All
```

**비디오용 QoS 설정**

```powershell
new-NetQosPolicy -Name "Teams Video" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50020 -IPSrcPortEndMatchCondition 50039 -DSCPAction 34 -NetworkProfile All
```

**공유를 위한 QoS 설정**

```powershell
new-NetQosPolicy -Name "Teams Sharing" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50040 -IPSrcPortEndMatchCondition 50059 -DSCPAction 18 -NetworkProfile All
```

## <a name="managing-source-ports-in-the-teams-admin-center"></a>관리 센터에서 Teams 포트 관리

Teams 워크로드에서 사용되는 QoS 원본 포트를 적극적으로 관리하고 필요한 경우 조정해야 합니다. 각 미디어 유형에 [](#choose-initial-port-ranges-for-each-media-type)대한 초기 포트 범위 선택에서 표를 참조하면 포트 범위를 조정할 수 있지만 DSCP 표시는 구성할 수 없습니다. 이러한 설정을 구현한 후 특정 미디어 유형에 더 많은 포트가 필요하거나 적은 수의 포트가 필요할 수 있습니다. [사용자당](use-call-analytics-to-troubleshoot-poor-call-quality.md) 통화 분석 및 [CQD(품질](turning-on-and-using-call-quality-dashboard.md) 대시보드)를 사용하여 포트 범위를 구현한 후 Teams 요구가 변경될 때 주기적으로 조정해야 합니다.

> [!NOTE]
> 온라인용 원본 포트 범위 및 DSCP 마킹을 기반으로 QoS를 비즈니스용 Skype 경우 동일한 구성이 Teams 추가 클라이언트 또는 네트워크 변경이 필요하지 않습니다. 온라인에서 구성된 [](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) 범위와 일치하도록 Teams 비즈니스용 Skype 설정해야 할 수도 있습니다.

이전에 배포한 비즈니스용 Skype 서버 경우 QoS 정책을 다시 검사해야 할 수 있습니다. 확인한 포트 범위 설정과 일치하도록 정책을 조정하면 사용자 환경이 Teams.

## <a name="validate-your-qos-implementation"></a>QoS 구현 유효성 검사

QoS가 효과적이기 위해 GPO에서 설정한 DSCP 값이 호출의 양쪽 끝에 존재해야 합니다. 클라이언트에서 생성된 트래픽을 분석하여 Teams 워크로드 트래픽이 네트워크를 통해 이동하면 DSCP 값이 변경되거나 제거되지 Teams 확인할 수 있습니다.

바람직하게는 네트워크 시작 지점에서 트래픽을 캡처합니다. 스위치 또는 라우터에서 포트 미러링을 사용하여 이를 도울 수 있습니다.

## <a name="implement-qos-for-other-devices"></a>다른 디바이스에 대한 QoS 구현

Intune, Surface, iOS, Android 및 Mac용 QoS 구현에 대한 자세한 내용은 다음 항목을 참조하세요.

- [2S용 QoS Surface Hub](/surface-hub/surface-hub-2s-manage-intune)

- [QoS for Surface Hub](/surface-hub/surface-hub-qos)

- [iOS, Android 및 Mac용 QoS](./meeting-settings-in-teams.md?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a>관련 주제

- [비디오: 네트워크 계획](https://aka.ms/teams-networking)

- [Microsoft Teams에 대한 조직의 네트워크 준비](prepare-network.md)

- [클라이언트에서 QoS Teams 구현](QoS-in-Teams-clients.md)