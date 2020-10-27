---
title: Microsoft 팀에서 서비스 품질 구현
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Microsoft 팀의 QoS (서비스 품질)에 대 한 조직의 네트워크를 준비 하는 방법에 대해 알아봅니다.
localization_priority: Normal
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
ms.openlocfilehash: 52b1d03be3e5d54260084bbf44ad6695404607c9
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766581"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>Microsoft 팀에서 QoS (서비스 품질) 구현

Microsoft 팀의 QoS (서비스 품질)를 사용 하면 네트워크 지연 (예: 음성 또는 비디오 스트림)에 영향을 주는 실시간 네트워크 트래픽이 중요 하지 않은 트래픽 앞 (즉, 다운로드 하는 추가 초가 큰 문제가 아닌 경우 새 앱 다운로드)로 "줄이 잘린" 것으로 처리 됩니다. QoS는 Windows 그룹 정책 개체와 포트 기반 액세스 제어 목록을 사용 하 여 실시간 스트림에서 모든 패킷을 식별 하 고 표시 합니다. 이는 네트워크에서 음성, 비디오, 화면 공유 스트림을 네트워크 대역폭의 전용 부분으로 제공 하는 데 도움이 됩니다.

이 문서에 설명 된 문제가 발생 하는 대규모 사용자 그룹을 지 원하는 경우 QoS를 구현 해야 할 수 있습니다. 사용자 수가 적은 소규모 기업에는 QoS가 필요 하지 않을 수 있지만,이 경우에도 도움이 됩니다.

일부 QoS 형식이 없는 경우 다음과 같은 음성 및 비디오의 품질 문제가 나타날 수 있습니다.

- 지터 – 다른 요금으로 도착 하는 미디어 패킷으로,이로 인해 통화에 단어나 음절이 누락 될 수 있습니다.
- 패킷 손실 – 손실 된 패킷, 음성 품질을 낮추고 음성을 이해 하기 어려울 수도 있습니다.
- 지연 왕복 시간 (RTT) – 대상에 도달 하는 데 오랜 시간이 소요 되는 미디어 패킷이 있어 대화 중 두 당사자 간의 지연이 눈에 띄게 하 고 다른 사람들이 서로 대화를 나눌 수 있습니다.

이러한 문제를 해결 하는 가장 복잡 한 방법은 인터넷을 통해 내부와 외부 모두 데이터 연결의 크기를 늘리는 것입니다. QoS는 대개 비용을 초과 하기 때문에 대역폭을 추가 하는 대신 사용 하는 리소스를 보다 효과적으로 관리 하는 방법을 제공 합니다. 품질 문제를 해결 하려면 먼저 QoS를 사용 하 고 필요한 경우에만 대역폭을 추가 하는 것이 좋습니다.

QoS가 유효 하려면 조직 전체에 일관 된 QoS 설정을 적용 해야 합니다. QoS 우선 순위를 지원 하지 않는 경로의 일부는 통화, 비디오, 화면 공유의 품질을 저하 시킬 수 있습니다. 여기에는 모든 사용자 Pc 또는 장치, 네트워크 스위치, 인터넷 라우터에, 팀 서비스에 설정을 적용 하는 것이 포함 됩니다.

_그림 1. 조직의 네트워크와 Microsoft 365 또는 Office 365 서비스 간의 관계_

![네트워크와 서비스 간의 관계를 보여 주는 그림](media/Qos-in-Teams-Image1.png "조직의 네트워크와 Microsoft 365 또는 Office 365 서비스 간의 관계: 온-프레미스 네트워크 및 장치는 interconnect 네트워크로 연결 되며,이는 다시 Microsoft 365 또는 Office 365 클라우드 음성 및 오디오 회의 서비스와 연결 됩니다.")

## <a name="qos-implementation-checklist"></a>QoS 구현 검사 목록

높은 수준에서 QoS를 구현 하려면 다음을 수행 합니다.

1. [네트워크가 준비 되었는지 확인](#make-sure-your-network-is-ready)

1. [QoS 구현 방법 선택](#select-a-qos-implementation-method)

1. [각 미디어 유형의 초기 포트 범위 선택](#choose-initial-port-ranges-for-each-media-type)

1. QoS 설정 구현:
   1. GPO (그룹 정책 개체)를 사용 하 여 [클라이언트 장치 포트 범위 및 표식을 설정](QoS-in-Teams-clients.md) 하는 클라이언트
   2. 라우터 (제조업체 설명서 참조) 또는 기타 네트워크 장치 여기에는 포트 기반 Acl (액세스 제어 목록)이 포함 되거나 QoS 큐 및 DSCP 표시 또는 이러한 모든 항목을 정의할 수가 있습니다.

      > [!IMPORTANT]
      > 클라이언트 원본 포트와 "모든"의 원본 및 대상 IP 주소를 사용 하 여 이러한 QoS 정책을 구현 하는 것이 좋습니다. 이렇게 하면 내부 네트워크의 들어오고 나가는 미디어 소통량이 모두 포착 됩니다.  

   3. [팀 모임에 대 한 미디어 트래픽을 처리 하는 방법을 설정 합니다.](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

5. 네트워크에서 팀 트래픽을 분석 하 여 [QoS 구현에 대 한 유효성을 검사](#validate-your-qos-implementation) 합니다.

QoS를 구현할 준비가 되 면 다음 지침을 염두에 두어야 합니다.

- Microsoft 365의 최단 경로는 가장 좋은 방법입니다.
- 포트를 닫으면 음질이 저하 될 수 있습니다.
- 프록시 등의 장애를 하는 것은 권장 되지 않습니다.
- 홉 수 제한:
  - 클라이언트-네트워크에 지-3 ~ 5 홉
  - ISP-Microsoft 네트워크에 지-3 홉
  - Microsoft 네트워크 edge에서 최종 목적지까지-관련이 없음

방화벽 포트를 구성 하는 방법에 대 한 자세한 내용은 [Office 365 url 및 IP 범위로](office-365-urls-ip-address-ranges.md)이동 하세요.

## <a name="make-sure-your-network-is-ready"></a>네트워크가 준비 되었는지 확인

QoS 구현을 고려 하는 경우에는 이미 대역폭 요구 사항 및 기타 [네트워크 요구 사항을](prepare-network.md)결정 해야 합니다.
  
네트워크를 통한 트래픽 정체는 미디어 품질에 큰 영향을 줍니다. 대역폭 부족으로 인해 성능이 저하 되 고 사용자 환경이 저하 될 수 있습니다. 팀을 도입 하 고 사용 하는 데는 보고, 사용자별 [통화 분석](use-call-analytics-to-troubleshoot-poor-call-quality.md), [통화 품질 대시보드 (cqd)](turning-on-and-using-call-quality-dashboard.md) 를 사용 하 여 문제를 식별 하 고 QoS 및 선택적 대역폭 추가를 사용 하 여 조정을 만듭니다.

### <a name="vpn-considerations"></a>VPN 고려 사항

QoS는 호출자 간의 모든 링크에서 구현 되는 경우 예상 대로 작동 합니다. 내부 네트워크에서 QoS를 사용 하 고 사용자가 원격 위치에서 로그인 하는 경우 내부 관리 네트워크 내 에서만 우선 순위를 지정할 수 있습니다. 원격 위치에서 VPN (가상 사설망)을 구현 하 여 관리 되는 연결을 받을 수 있지만 VPN은 본질적으로 패킷 오버 헤드를 추가 하 고 실시간 트래픽에 대 한 지연을 생성 합니다. VPN을 통해 실시간 통신 소통량을 실행 하는 것을 방지 하는 것이 좋습니다.

대륙에 걸친 관리 링크가 있는 전역 조직에서는 이러한 링크에 대 한 대역폭이 LAN에 비해 제한 되어 있으므로 QoS를 사용 하는 것이 좋습니다.

## <a name="introduction-to-qos-queues"></a>QoS 큐 소개

QoS를 제공 하려면 네트워크 장치에 트래픽을 분류 하는 방법이 있어야 하며 다른 네트워크 트래픽과 음성 또는 비디오를 구별할 수 있어야 합니다.

네트워크 트래픽이 라우터로 들어가면 소통량이 대기열에 배치 됩니다. QoS 정책이 구성 되지 않은 경우 하나의 큐만 있으며 모든 데이터는 동일한 우선 순위로 첫 번째 항목으로 처리 됩니다. 즉, 지연 하는 것이 매우 중요 한 음성 소통량이 발생 하는 것은 몇 가지 추가 밀리초의 지연이 문제가 되지 않는 트래픽 뒤에 있을 수 있다는 것입니다.

QoS를 구현할 때 Cisco의 우선 순위 대기열 및 [클래스 기반 가중치가 지정 공정 (CBWFQ)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) 및 혼잡 방지 기능 (예: 가중치가 지정 된 [임의 조기 검색) (wred)](https://en.wikipedia.org/wiki/Weighted_random_early_detection)등의 여러 혼잡 관리 기능 중 하나를 사용 하 여 여러 개의 큐를 정의 합니다.

_그림 2. QoS 큐의 예_

![QoS 큐 및 대역폭 디비전 그림](media/Qos-in-Teams-Image2.png "사용할 수 있는 총 대역폭이 서로 다른 우선 순위를 할당 한 여러 큐 (오디오, 비디오 및 기타 트래픽) 간에 나뉘어 있습니다.")

간단한 비유는 QoS에서 데이터 네트워크에 가상 "carpool 레인"을 만들기 때문에 일부 데이터 형식에는 지연이 발생 하지 않을 수 있다는 것입니다. 이러한 레인을 만든 후에는 해당 하는 상대적 크기를 조정할 수 있으며, 사용자에 게 제공 되는 연결 대역폭을 더욱 효과적으로 관리 하는 동시에 조직에서 사용 하는 비즈니스에 대 한 환경을 유지 합니다.

## <a name="select-a-qos-implementation-method"></a>QoS 구현 방법 선택

네트워크 라우터의 Acl (액세스 제어 목록)을 사용 하 여 포트 기반 태깅을 통해 QoS를 구현할 수 있습니다. 포트 기반 태깅은 혼합 Windows, Mac 및 Linux 환경에서 작동 하 고 구현 하기가 가장 쉽고 가장 신뢰할 수 있는 방법입니다. 모바일 클라이언트는 DSCP 값을 사용 하 여 트래픽을 표시 하는 메커니즘을 제공 하지 않으므로이 방법이 필요 합니다.  

포트 기반 태깅을 사용 하면 네트워크 라우터가 들어오는 패킷을 검사 하 고, 특정 포트 또는 포트 범위를 사용 하 여 패킷이 도착 하는 경우, 다른 장치가 해당 트래픽 유형을 인식 하 고 해당 사용자의 큐에 우선 순위를 지정할 수 있도록 IP 패킷 헤더에 미리 정의 된 [DSCP](https://tools.ietf.org/html/rfc2474) 표시를 추가 하 여 해당 형식의 큐에 배치 합니다.

포트 기반 태그는 플랫폼에서 작동 하지만 WAN edge의 트래픽만 클라이언트 컴퓨터에 표시 되는 것이 아니라 관리 오버 헤드를 생성 합니다. 이 방법을 구현 하는 방법에 대 한 지침은 라우터 제조업체에서 제공 하는 문서를 참조 하세요.

### <a name="insert-dscp-markers"></a>DSCP 표식 삽입

또한 GPO (그룹 정책 개체)를 사용 하 여 클라이언트 장치를 특정 유형의 트래픽 (예: 음성)으로 식별 하는 IP 패킷 헤더에 DSCP 마커를 삽입 하도록 하 여 QoS를 구현할 수도 있습니다. 라우터 및 기타 네트워크 장치가이를 인식 하 고 우선 순위가 높은 별도의 큐에 트래픽을 전송 하도록 구성할 수 있습니다.

이 시나리오는 완전히 유효 하지만 도메인에 가입 된 Windows 클라이언트에 대해서만 작동 합니다. 도메인에 가입 된 Windows 클라이언트가 아닌 모든 장치는 DSCP 태깅에 대해 사용 하도록 설정 되지 않습니다. Mac OS와 같은 클라이언트는 하드 코딩 된 태그를 포함 하며 항상 트래픽에 태그를 지정 합니다.

플러스 측면에서, GPO를 통해 DSCP 표시를 제어 하면 모든 도메인 참가 컴퓨터가 동일한 설정을 받고 관리자만 관리할 수 있습니다. GPO를 사용할 수 있는 클라이언트는 원래 장치에서 태그가 지정 되 고, 구성 된 네트워크 디바이스는 DSCP 코드에서 실시간 스트림을 인식 하 고 적절 한 우선 순위를 제공할 수 있습니다.

### <a name="best-practice"></a>모범 사례

끝점 및 포트 기반 Acl (가능 하면 라우터의 경우)에 DSCP 표시를 조합 하는 것이 좋습니다. GPO를 사용 하 여 대부분의 클라이언트를 catch 하 고 포트 기반 DSCP 태깅을 사용 하면 모바일, Mac 및 다른 클라이언트가 계속 QoS 처리를 할 수 있습니다 (최소한 부분적).

DSCP 표시는 우편 작업자에 게 배달이 얼마나 긴급 한지, 그리고 빠른 전달을 위해 정렬 하는 방법에 대 한 우표 스탬프로 likened 수 있습니다. 실시간 미디어 스트림에 우선 순위를 부여 하도록 네트워크를 구성 하면 손실 된 패킷과 지연 패킷이 크게 감소 합니다.

네트워크의 모든 장치가 동일한 분류, 표시 및 우선 순위를 사용 하는 경우 각 트래픽 형식에 사용 되는 큐에 할당 된 포트 범위 크기를 변경 하 여 지연, 손실 된 패킷 및 지터를 줄이거나 제거할 수 있습니다. 팀 관점에서 가장 중요 한 구성 단계는 패킷의 분류와 표시입니다. 그러나 종단 간 QoS를 성공적으로 수행 하려면 기본 네트워크 구성으로 응용 프로그램의 구성을 주의 해 서 정렬 해야 합니다. QoS가 완벽 하 게 구현 되는 경우, 진행 중인 관리는 조직의 필요 성과 실제 사용량에 따라 각 트래픽 유형에 할당 된 포트 범위를 조정 하는 질문입니다.

## <a name="choose-initial-port-ranges-for-each-media-type"></a>각 미디어 유형의 초기 포트 범위 선택

DSCP 값은 패킷 또는 스트림에 제공 되는 우선 순위 (dscp 표시가 클라이언트에 의해 할당 되는지 여부 또는 ACL 설정에 따라 네트워크 자체에 의해 지정 됨)에 대 한 우선순위를 구성 된 네트워크에 알려 줍니다. 각 미디어 작업 부하에는 고유한 DSCP 값 (다른 서비스를 사용 하 여 DSCP 표시, 팀이 아닌 사용자 공유) 및 각 미디어 유형에 사용 되는 정의 된 별도의 포트 범위가 있습니다. 다른 환경에는 네트워크 작업의 우선 순위를 결정 하는 데 도움이 되는 기존 QoS 전략이 있을 수 있습니다.

다양 한 실시간 스트리밍 작업의 포트 범위에 대 한 상대적 크기는 해당 작업 부하 전용의 총 사용 가능 대역폭의 비율을 설정 합니다. 앞에서 설명한 우편으로 돌아가려면 "Air Mail" 스탬프가 있는 문자는 1 시간 내에 가장 가까운 공항으로, "대량 메일" 표시로 표시 된 작은 패키지는 여러 개의 트럭을 통해 여행 하기 전에 하루 동안 대기할 수 있습니다.

_권장 되는 초기 포트 범위_

|미디어 트래픽 유형| 클라이언트 원본 포트 범위  |프로토콜|DSCP 값|DSCP 클래스|
|:--- |:--- |:--- |:--- |:--- |
|오디오| 50,000~50,019|TCP/UDP|46|Expedited Forwarding(EF)|
|비디오| 50,020~50,039|TCP/UDP|34|Assured Forwarding(AF41)|
|응용 프로그램/화면 공유| 50,040~50,059|TCP/UDP|awg|Assured Forwarding(AF21)|
||||||

이러한 설정을 사용할 때는 다음에 유의 해야 합니다.

- 향후에는 Express 경로를 구현 하 고 아직 QoS를 구현 하지 않은 경우에는 DSCP 값이 보낸 사람이 받는 사람에 게 동일 하도록 지침을 따르는 것이 좋습니다.
- 모바일 클라이언트와 팀 디바이스를 비롯 한 모든 클라이언트는 이러한 포트 범위를 사용 하 고, 이러한 원본 포트 범위를 사용 하는 모든 DSCP 정책에 의해 영향을 받게 됩니다. 동적 포트를 계속 사용 하는 유일한 클라이언트는 브라우저 기반 클라이언트 (브라우저를 사용 하 여 참가자가 모임에 참가할 수 있도록 하는 클라이언트)입니다.
- Mac 클라이언트는 동일한 포트 범위를 사용 하지만 오디오 (EF) 및 비디오 (AF41)에 하드 코드 된 값도 사용 합니다. 이러한 값은 구성할 수 없습니다.
- 나중에 사용자 환경을 개선 하기 위해 포트 범위를 조정 해야 하는 경우 포트 범위가 겹칠 수 없으며 서로 인접해 야 합니다.

## <a name="migrate-qos-to-teams"></a>팀에 QoS 마이그레이션

이전에 QoS 태깅 및 포트 범위를 포함 하 여 비즈니스용 Skype Online을 배포한 경우 지금 배포 합니다. 팀은 기존 구성을 존중 하 고 비즈니스용 Skype 클라이언트와 동일한 포트 범위와 태그를 사용 하 게 됩니다. 대부분의 경우 추가 구성은 필요 하지 않습니다.

> [!NOTE]
> 그룹 정책을 통해 응용 프로그램 이름 QoS 태그를 사용 하는 경우 응용 프로그램 이름으로 Teams.exe 추가 해야 합니다.

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a>PowerShell을 사용 하 여 Windows 팀에서 QoS 구현

**오디오에 대 한 QoS 설정**

```powershell
new-NetQosPolicy -Name "Teams Audio" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50000
-IPSrcPortEndMatchCondition 50019 -DSCPAction 46 -NetworkProfile All
```

**비디오에 대 한 QoS 설정**

```powershell
new-NetQosPolicy -Name "Teams Video" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50020
-IPSrcPortEndMatchCondition 50039 -DSCPAction 34 -NetworkProfile All
```

**공유에 대 한 QoS 설정**

```powershell
new-NetQosPolicy -Name "Teams Sharing" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50040
-IPSrcPortEndMatchCondition 50059 -DSCPAction 18 -NetworkProfile All
```

## <a name="managing-source-ports-in-the-teams-admin-center"></a>팀 관리 센터의 원본 포트 관리

팀에서 여러 작업 부하에 사용 되는 QoS 원본 포트는 적극적으로 관리 되 고 필요에 따라 조정 되어야 합니다. [각 미디어 유형의 초기 포트 범위 선택](#choose-initial-port-ranges-for-each-media-type)에서 테이블을 참조 하면 포트 범위는 조정할 수 있지만 DSCP 표시는 구성 불가능 합니다. 이러한 설정을 구현한 후에는 지정 된 미디어 형식에 대해 더 많거나 적은 포트가 필요할 수 있습니다. 팀을 구현 하 고 주기적으로 변경 해야 하는 경우 포트 범위를 조정 하기로 결정 하는 데는 [사용자 단위 호출 분석](use-call-analytics-to-troubleshoot-poor-call-quality.md) 및 [call Quality 대시보드 (cqd)](turning-on-and-using-call-quality-dashboard.md) 를 사용 해야 합니다.

> [!NOTE]
> 비즈니스용 Skype Online에 대 한 원본 포트 범위 및 DSCP 표시를 기반으로 QoS를 이미 구성한 경우 팀에 [사용 되는 범위](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) 를 비즈니스용 skype online에 대해 구성 된 것과 일치 시 키 지 않도록 설정 해야 하는 것은 아니지만, 매핑에 대 한 추가 클라이언트 또는 네트워크 변경은 필요 하지 않을 수 있습니다.

이전에 비즈니스용 Skype 서버를 온-프레미스로 배포한 경우에는 QoS 정책을 다시 검사 해야 할 수 있습니다. 정책을 조정 하 여 팀에 대 한 품질 사용자 환경 제공을 확인 한 포트 범위 설정에 일치 합니다.

## <a name="validate-your-qos-implementation"></a>QoS 구현 확인

QoS가 유효 하기 위해서는 GPO가 설정 하는 DSCP 값이 통화의 양끝에 있어야 합니다. 팀 클라이언트에서 생성 된 트래픽을 분석 하 여 팀 작업 부하 트래픽이 네트워크를 통해 이동할 때 DSCP 값이 변경 되거나 제거 되지 않았는지 확인할 수 있습니다.

가능 하면 네트워크 송신 지점에서 트래픽을 캡처 하세요. 스위치 또는 라우터에서 포트 미러링을 사용 하 여이 작업을 도울 수 있습니다.

## <a name="implement-qos-for-other-devices"></a>다른 장치에 대 한 QoS 구현

Intune, Surface, iOS, Android 및 Mac 용 QoS를 구현 하는 방법에 대 한 자세한 내용은 다음 항목을 참조 하세요.

- [Surface Hub 2S 용 QoS](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune)

- [Surface Hub 용 QoS](https://docs.microsoft.com/surface-hub/surface-hub-qos)

- [IOS, Android 및 Mac의 QoS](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a>관련 항목

- [비디오: 네트워크 계획](https://aka.ms/teams-networking)

- [Microsoft Teams에 대한 조직의 네트워크 준비](prepare-network.md)

- [팀 클라이언트에서 QoS 구현](QoS-in-Teams-clients.md)
