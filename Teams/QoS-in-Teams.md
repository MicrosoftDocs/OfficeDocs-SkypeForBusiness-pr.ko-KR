---
title: Microsoft Teams에서 서비스 품질 구현
ms.author: mikeplum
author: MikePlumleyMSFT
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Microsoft Teams에서 QoS(서비스 품질)를 위해 조직의 네트워크를 준비하는 방법에 대해 알아봅니다.
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
ms.openlocfilehash: 6015c7b7cf1e7be5bc6b9b3e1fe0577a7f707377
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66564146"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>Microsoft Teams에서 QoS(서비스 품질) 구현

Microsoft Teams의 QoS(서비스 품질)를 사용하면 네트워크 지연(예: 음성 또는 비디오 스트림)에 민감한 실시간 네트워크 트래픽이 덜 민감한 트래픽 앞에서 "줄 바꿈"할 수 있습니다(예: 새 앱 다운로드와 같이 다운로드할 추가 시간이 큰 문제가 아님). QoS는 Windows 그룹 정책 개체 및 포트 기반 Access Control 목록을 사용하여 모든 패킷을 실시간으로 식별하고 표시합니다. 이렇게 하면 네트워크에서 음성, 비디오 및 화면 공유 스트림에 네트워크 대역폭의 전용 부분을 제공할 수 있습니다.

이 문서에 설명된 문제가 발생한 대규모 사용자 그룹을 지원하는 경우 QoS를 구현해야 할 수 있습니다. 사용자가 적은 소규모 기업은 QoS가 필요하지 않을 수 있지만, 거기에도 도움이 될 수 있습니다.

어떤 형태의 QoS가 없으면 음성 및 비디오에서 다음과 같은 품질 문제가 표시될 수 있습니다.

- 지터 – 다른 속도로 도착하는 미디어 패킷으로, 통화에서 단어 또는 음절이 누락 될 수 있습니다.
- 패킷 손실 – 패킷이 삭제되어 음성 품질이 낮아지고 음성을 이해하기 어려울 수 있습니다.
- 지연된 RTT(왕복 시간) - 미디어 패킷이 목적지에 도달하는 데 시간이 오래 걸리며, 이로 인해 두 당사자가 대화에서 눈에 띄게 지연되고 사람들이 서로 대화하게 됩니다.

이러한 문제를 해결하는 가장 복잡한 방법은 내부적으로나 인터넷으로 데이터 연결의 크기를 늘리는 것입니다. 이는 종종 비용이 많이 들기 때문에 QoS는 대역폭을 추가하는 대신 리소스를 보다 효과적으로 관리할 수 있는 방법을 제공합니다. 품질 문제를 해결하려면 먼저 QoS를 사용한 다음 필요한 경우에만 대역폭을 추가하는 것이 좋습니다.

QoS가 유효하려면 조직 전체에 일관된 QoS 설정을 적용해야 합니다. QoS 우선 순위를 지원하지 않는 경로의 모든 부분은 통화, 비디오 및 화면 공유의 품질을 저하시킬 수 있습니다. 여기에는 모든 사용자 PC 또는 디바이스, 네트워크 스위치, 인터넷에 라우터 및 Teams 서비스에 설정을 적용하는 것이 포함됩니다.

_그림 1. 조직의 네트워크와 Microsoft 365 또는 Office 365 서비스 간의 관계_

![네트워크와 서비스 간의 관계에 대한 그림입니다.](media/Qos-in-Teams-Image1.png "조직의 네트워크와 Microsoft 365 또는 Office 365 서비스 간의 관계: 온-프레미스 네트워크와 디바이스는 상호 연결 네트워크와 연결되며, 이 네트워크는 Microsoft 365 또는 Office 365 Cloud Voice 및 오디오 회의 서비스와 연결됩니다.")

## <a name="qos-implementation-checklist"></a>QoS 구현 검사 목록

높은 수준에서 다음을 수행하여 QoS를 구현합니다.

1. [네트워크가 준비되었는지 확인합니다](#make-sure-your-network-is-ready).

1. [QoS 구현 방법을 선택합니다](#select-a-qos-implementation-method).

1. [각 미디어 유형에 대한 초기 포트 범위를 선택합니다](#choose-initial-port-ranges-for-each-media-type).

1. QoS 설정을 구현합니다.
   1. 클라이언트에서 GPO(그룹 정책 Object)를 사용하여 [클라이언트 디바이스 포트 범위 및 표시를 설정합니다](QoS-in-Teams-clients.md).
   2. 라우터(제조업체 설명서 참조) 또는 기타 네트워크 디바이스에서 여기에는 포트 기반 ACL(Access Control 목록) 또는 단순히 QoS 큐 및 DSCP 표시 정의 또는 이러한 모든 항목이 포함될 수 있습니다.

      > [!IMPORTANT]
      > 클라이언트 원본 포트와 "any"의 원본 및 대상 IP 주소를 사용하여 이러한 QoS 정책을 구현하는 것이 좋습니다. 그러면 내부 네트워크에서 들어오는 미디어 트래픽과 나가는 미디어 트래픽을 모두 catch할 수 있습니다.  

   3. [Teams 모임의 미디어 트래픽을 처리하는 방법을 설정합니다](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).

5. 네트워크에서 Teams 트래픽을 분석하여 [QoS 구현의 유효성을 검사](#validate-your-qos-implementation)합니다.

QoS 구현을 준비할 때 다음 지침을 염두에 두어야 합니다.

- Microsoft 365의 가장 짧은 경로가 가장 좋습니다.
- 포트를 닫으면 품질이 저하됩니다.
- 프록시와 같은 그 사이에 있는 장애물은 권장되지 않습니다.
- 홉 수를 제한합니다.
  - 클라이언트-네트워크 에지 – 3~5홉
  - ISP에서 Microsoft 네트워크 에지로 – 3홉
  - 최종 대상에 대한 Microsoft 네트워크 에지 - 관련이 없습니다.

방화벽 포트를 구성하는 방법에 대한 자세한 내용은 [Office 365 URL 및 IP 범위](office-365-urls-ip-address-ranges.md)로 이동하세요.

## <a name="make-sure-your-network-is-ready"></a>네트워크가 준비되었는지 확인

QoS 구현을 고려하는 경우 대역폭 요구 사항 및 기타 [네트워크 요구 사항을](prepare-network.md) 이미 결정했어야 합니다.
  
네트워크 간 트래픽 정체는 미디어 품질에 큰 영향을 줍니다. 대역폭이 부족하면 성능이 저하되고 사용자 환경이 저하됩니다. Teams 채택 및 사용량이 증가함에 따라 보고, [사용자별 통화 분석](use-call-analytics-to-troubleshoot-poor-call-quality.md) 및 [CQD(통화 품질 대시보드)](turning-on-and-using-call-quality-dashboard.md) 를 사용하여 문제를 식별한 다음 QoS 및 선택적 대역폭 추가를 사용하여 조정합니다.

### <a name="vpn-considerations"></a>VPN 고려 사항

QoS는 호출자 간의 모든 링크에서 구현될 때만 예상대로 작동합니다. 내부 네트워크에서 QoS를 사용하고 사용자가 원격 위치에서 로그인하는 경우 내부 관리형 네트워크 내에서만 우선 순위를 지정할 수 있습니다. 원격 위치는 VPN(가상 사설망)을 구현하여 관리되는 연결을 받을 수 있지만 VPN은 기본적으로 패킷 오버헤드를 추가하고 실시간 트래픽에서 지연을 만듭니다. VPN을 통해 실시간 통신 트래픽을 실행하지 않는 것이 좋습니다.

대륙에 걸쳐 있는 관리되는 링크가 있는 글로벌 조직에서는 해당 링크의 대역폭이 LAN에 비해 제한되기 때문에 QoS를 강력히 권장합니다.

## <a name="introduction-to-qos-queues"></a>QoS 큐 소개

QoS를 제공하려면 네트워크 디바이스가 트래픽을 분류하는 방법이 있어야 하며 음성 또는 비디오를 다른 네트워크 트래픽과 구분할 수 있어야 합니다.

네트워크 트래픽이 라우터에 들어가면 트래픽이 큐에 배치됩니다. QoS 정책이 구성되지 않은 경우 하나의 큐만 있고 모든 데이터는 동일한 우선 순위로 선점된 첫 번째 데이터로 처리됩니다. 즉, 음성 트래픽(지연에 매우 민감)은 몇 밀리초의 추가 지연이 문제가 되지 않는 트래픽 뒤에 갇히게 될 수 있습니다.

QoS를 구현할 때 Cisco의 우선 순위 큐 및 [CBWFQ(클래스 기반 가중 공정 큐)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) 및 [WRED(가중 무작위 조기 검색)](https://en.wikipedia.org/wiki/Weighted_random_early_detection)와 같은 혼잡 회피 기능과 같은 여러 정체 관리 기능 중 하나를 사용하여 여러 큐를 정의합니다.

_그림 2. QoS 큐의 예_

![QoS 큐 및 대역폭 나누기의 그림입니다.](media/Qos-in-Teams-Image2.png "사용 가능한 총 대역폭은 서로 다른 우선 순위가 할당된 여러 큐(오디오, 비디오 및 기타 트래픽)로 나뉩니다.")

간단한 비유는 QoS가 데이터 네트워크에 가상 "카풀 레인"을 만들어 일부 유형의 데이터가 지연되거나 거의 발생하지 않도록 한다는 것입니다. 해당 레인을 만들면 상대적 크기를 조정하고 조직의 사용자에게 비즈니스 수준의 환경을 제공하는 동시에 보유하는 연결 대역폭을 훨씬 더 효과적으로 관리할 수 있습니다.

## <a name="select-a-qos-implementation-method"></a>QoS 구현 방법 선택

네트워크의 라우터에서 ACL(Access Control 목록)을 사용하여 포트 기반 태그 지정을 통해 QoS를 구현할 수 있습니다. 포트 기반 태그 지정은 혼합 Windows, Mac 및 Linux 환경에서 작동하며 구현하기 가장 쉽기 때문에 가장 신뢰할 수 있는 방법입니다. 모바일 클라이언트는 DSCP 값을 사용하여 트래픽을 표시하는 메커니즘을 제공하지 않으므로 이 메서드가 필요합니다.  

포트 기반 태그 지정을 사용하여 네트워크의 라우터는 들어오는 패킷을 검사하고 패킷이 특정 포트 또는 포트 범위를 사용하여 도착한 경우 특정 미디어 유형으로 식별하여 해당 형식의 큐에 배치하여 다른 디바이스가 트래픽 유형을 인식하고 큐에서 우선 순위를 부여할 수 있도록 IP 패킷 헤더에 미리 결정된 [DSCP](https://tools.ietf.org/html/rfc2474) 표시를 추가합니다.

포트 기반 태그 지정은 플랫폼 간에 작동하지만 WAN 에지에서 트래픽만 표시하고(클라이언트 머신에 대한 모든 방법은 아님) 관리 오버헤드를 만듭니다. 이 메서드 구현에 대한 지침은 라우터 제조업체에서 제공하는 설명서를 참조하세요.

### <a name="insert-dscp-markers"></a>DSCP 표식 삽입

GPO(그룹 정책 개체)를 사용하여 클라이언트 디바이스에 특정 유형의 트래픽(예: 음성)으로 식별하는 IP 패킷 헤더에 DSCP 마커를 삽입하도록 지시하여 QoS를 구현할 수도 있습니다. 라우터 및 기타 네트워크 디바이스는 이를 인식하고 트래픽을 우선 순위가 높은 별도의 큐에 배치하도록 구성할 수 있습니다.

이 시나리오는 전적으로 유효하지만 도메인에 가입된 Windows 클라이언트에서만 작동합니다. 도메인에 가입된 Windows 클라이언트가 아닌 모든 디바이스는 DSCP 태그 지정에 사용할 수 없습니다. macOS를 실행하는 클라이언트와 같은 다른 클라이언트에는 하드 코드된 태그가 있으며 항상 트래픽에 태그를 지정합니다.

더하기 측면에서 GPO를 통해 DSCP 표시를 제어하면 도메인에 가입된 모든 컴퓨터가 동일한 설정을 받고 관리자만 관리할 수 있습니다. GPO를 사용할 수 있는 클라이언트는 원래 디바이스에서 태그가 지정되고 구성된 네트워크 디바이스는 DSCP 코드로 실시간 스트림을 인식하고 적절한 우선 순위를 부여할 수 있습니다.

### <a name="best-practice"></a>모범 사례

가능하면 엔드포인트에서 DSCP 표시와 라우터의 포트 기반 ACL을 조합하는 것이 좋습니다. GPO를 사용하여 대부분의 클라이언트를 catch하고 포트 기반 DSCP 태그 지정을 사용하면 모바일, Mac 및 기타 클라이언트가 QoS 처리(적어도 부분적으로)를 계속 받을 수 있습니다.

DSCP 표시는 우편 근로자에게 배달이 얼마나 긴급한지, 그리고 신속한 배송을 위해 가장 잘 정렬하는 방법을 나타내는 우표에 비유할 수 있습니다. 실시간 미디어 스트림에 우선 순위를 부여하도록 네트워크를 구성한 후에는 패킷 손실 및 지연 패킷이 크게 감소해야 합니다.

네트워크의 모든 디바이스에서 동일한 분류, 표시 및 우선 순위를 사용하면 각 트래픽 유형에 사용되는 큐에 할당된 포트 범위의 크기를 변경하여 지연, 패킷 삭제 및 지터를 줄이거나 제거할 수 있습니다. Teams 관점에서 가장 중요한 구성 단계는 패킷의 분류 및 표시입니다. 그러나 엔드투엔드 QoS가 성공하려면 애플리케이션의 구성을 기본 네트워크 구성과 신중하게 조정해야 합니다. QoS가 완전히 구현되면 지속적인 관리는 조직의 요구 사항 및 실제 사용량에 따라 각 트래픽 유형에 할당된 포트 범위를 조정하는 문제입니다.

## <a name="choose-initial-port-ranges-for-each-media-type"></a>각 미디어 유형에 대한 초기 포트 범위 선택

DSCP 값은 클라이언트에서 DSCP 표시를 할당하는지 또는 ACL 설정에 따라 네트워크 자체에 할당되는지 여부에 관계없이 패킷 또는 스트림을 제공할 우선 순위를 해당하게 구성된 네트워크에 알려줍니다. 각 미디어 워크로드는 고유한 DSCP 값(다른 서비스에서는 워크로드가 DSCP 표시를 공유할 수 있고 Teams는 공유하지 않음)과 각 미디어 유형에 사용되는 정의되고 별도의 포트 범위를 가져옵니다. 다른 환경에는 네트워크 워크로드의 우선 순위를 결정하는 데 도움이 되는 기존 QoS 전략이 있을 수 있습니다.

다양한 실시간 스트리밍 워크로드에 대한 포트 범위의 상대적 크기는 해당 워크로드 전용으로 사용 가능한 총 대역폭의 비율을 설정합니다. 이전 우편 비유로 돌아가려면 : "에어 메일"스탬프가있는 편지는 가장 가까운 공항으로 한 시간 이내에 촬영 될 수 있으며"대량 메일"표시로 표시된 작은 패키지는 일련의 트럭으로 땅을 여행하기 전에 하루 동안 기다릴 수 있습니다.

_권장되는 초기 포트 범위_

|미디어 트래픽 유형| 클라이언트 원본 포트 범위  |프로토콜|DSCP 값|DSCP 클래스|
|:--- |:--- |:--- |:--- |:--- |
|오디오| 50,000~50,019|TCP/UDP|46|Expedited Forwarding(EF)|
|비디오| 50,020~50,039|TCP/UDP|34|Assured Forwarding(AF41)|
|응용 프로그램/화면 공유| 50,040~50,059|TCP/UDP|18|Assured Forwarding(AF21)|
||||||

이러한 설정을 사용하는 경우 다음 사항에 유의하세요.

- 나중에 ExpressRoute를 구현할 계획이며 아직 QoS를 구현하지 않은 경우 DSCP 값이 보낸 사람에서 받는 사람까지 동일하도록 지침을 따르는 것이 좋습니다.

- 모바일 클라이언트 및 Teams 디바이스를 포함한 모든 클라이언트는 이러한 포트 범위를 사용하며 이러한 원본 포트 범위를 사용하는 구현하는 모든 DSCP 정책의 영향을 받습니다. 동적 포트를 계속 사용하는 유일한 클라이언트는 브라우저 기반 클라이언트(참가자가 브라우저를 사용하여 모임에 참가할 수 있도록 하는 클라이언트)입니다.

- Mac 클라이언트는 동일한 포트 범위를 사용하지만 오디오(EF) 및 비디오(AF41)에도 하드 코딩된 값을 사용합니다. 이러한 값은 구성할 수 없습니다.

- 나중에 사용자 환경을 개선하기 위해 포트 범위를 조정해야 하는 경우 포트 범위는 겹칠 수 없으며 서로 인접해야 합니다.

## <a name="migrate-qos-to-teams"></a>QoS를 Teams로 마이그레이션

이전에 QoS 태그 지정 및 포트 범위를 포함하여 비즈니스용 Skype Online을 배포했으며 현재 배포 중인 경우 Teams, Teams는 기존 구성을 준수하며 비즈니스용 Skype 클라이언트와 동일한 포트 범위 및 태그 지정을 사용합니다. 대부분의 경우 추가 구성이 필요하지 않습니다.

> [!NOTE]
> 그룹 정책 통해 애플리케이션 이름 QoS 태그 지정을 사용하는 경우 Teams.exe 애플리케이션 이름으로 추가해야 합니다.

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a>PowerShell을 사용하여 Windows의 Teams에서 QoS 구현

**오디오에 대한 QoS 설정**

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

## <a name="managing-source-ports-in-the-teams-admin-center"></a>Teams 관리 센터에서 원본 포트 관리

Teams에서 다양한 워크로드에서 사용하는 QoS 원본 포트를 적극적으로 관리하고 필요에 따라 조정해야 합니다. [각 미디어 유형에 대한 초기 포트 범위 선택](#choose-initial-port-ranges-for-each-media-type)에서 테이블을 참조하면 포트 범위를 조정할 수 있지만 DSCP 표시는 구성할 수 없습니다. 이러한 설정을 구현한 후에는 지정된 미디어 유형에 더 많거나 적은 포트가 필요하다는 것을 알 수 있습니다. [사용자별 통화 분석](use-call-analytics-to-troubleshoot-poor-call-quality.md) 및 [CQD(통화 품질 대시보드)](turning-on-and-using-call-quality-dashboard.md) 는 Teams가 구현된 후 포트 범위를 조정하고 필요에 따라 주기적으로 변경하도록 결정하는 데 사용해야 합니다.

> [!NOTE]
> 비즈니스용 Skype Online에 대한 원본 포트 범위 및 DSCP 표시를 기반으로 QoS를 이미 구성한 경우 Teams에 동일한 구성이 적용되며, [Teams에서 사용된 범위를](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) 비즈니스용 Skype Online에 대해 구성된 범위와 일치하도록 설정해야 하지만 매핑에 대한 추가 클라이언트 또는 네트워크 변경이 필요하지 않습니다.

이전에 온-프레미스에 비즈니스용 Skype 서버 배포한 경우 QoS 정책을 다시 검토해야 할 수 있습니다. 확인된 포트 범위 설정과 일치하도록 정책을 조정하여 Teams에 양질의 사용자 환경을 제공합니다.

## <a name="validate-your-qos-implementation"></a>QoS 구현 유효성 검사

QoS가 유효하려면 GPO에서 설정한 DSCP 값이 호출의 양쪽 끝에 있어야 합니다. Teams 클라이언트에서 생성된 트래픽을 분석하여 Teams 워크로드 트래픽이 네트워크를 통해 이동할 때 DSCP 값이 변경되거나 제거되지 않는지 확인할 수 있습니다.

네트워크 송신 지점에서 트래픽을 캡처하는 것이 좋습니다. 이를 돕기 위해 스위치 또는 라우터에서 포트 미러링을 사용할 수 있습니다.

## <a name="implement-qos-for-other-devices"></a>다른 디바이스에 대한 QoS 구현

Intune, Surface, iOS, Android 및 Mac용 QoS 구현에 대한 자세한 내용은 다음 항목을 참조하세요.

- [Surface Hub 2S용 QoS](/surface-hub/surface-hub-2s-manage-intune)

- [Surface Hub용 QoS](/surface-hub/surface-hub-qos)

- [iOS, Android 및 Mac용 QoS](./meeting-settings-in-teams.md?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a>관련 항목

- [비디오: 네트워크 계획](https://aka.ms/teams-networking)

- [Microsoft Teams에 대한 조직의 네트워크 준비](prepare-network.md)

- [Teams 클라이언트에서 QoS 구현](QoS-in-Teams-clients.md)