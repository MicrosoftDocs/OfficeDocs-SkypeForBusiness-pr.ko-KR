---
title: 미디어 품질 및 네트워크 연결 성능
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.topic: article
ms.assetid: 5fe3e01b-34cf-44e0-b897-b0b2a83f0917
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
description: 이 항목에서는 비즈니스용 Skype Online 서비스에 대 한 네트워크 성능 요구 사항 집합을 정의 하 고 네트워크 연결에 대 한 평가를 기반으로 네트워크와 비즈니스용 Skype Online 간 연결을 위해 인터넷 또는 Express 경로 사용을 선택 하는 방법에 대해 설명 합니다. Office 365에 대 한 전용 연결에 대 한 Azure Express를 배포 하기로 결정 한 경우,이 문서는 다른 비즈니스용 Skype Online 배포 시나리오에서 Express 경로 연결을 계획 하는 방법에 대 한 지침을 제공 합니다.
ms.openlocfilehash: ed7ad6ebd456122e41ccd74269180ff9c79fa3fb
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776443"
---
# <a name="media-quality-and-network-connectivity-performance-in-skype-for-business-online"></a>비즈니스용 Skype Online의 미디어 품질과 네트워크 연결 성능

이 항목에서는 비즈니스용 Skype Online 서비스에 대 한 네트워크 성능 요구 사항 집합을 정의 하 고 네트워크 연결에 대 한 평가를 기반으로 네트워크와 비즈니스용 Skype Online 간 연결을 위해 인터넷 또는 Express 경로 사용을 선택 하는 방법에 대해 설명 합니다. Office 365에 대 한 전용 연결에 대 한 Azure Express를 배포 하기로 결정 한 경우,이 문서는 다른 비즈니스용 Skype Online 배포 시나리오에서 Express 경로 연결을 계획 하는 방법에 대 한 지침을 제공 합니다.
  
IP를 통한 실시간 미디어 (오디오, 비디오 및 응용 프로그램 공유)의 품질은 종단간 네트워크 연결의 품질에 따라 크게 영향을 받습니다. 비즈니스용 Skype Online media의 품질을 최적화 하려면 회사 네트워크와 비즈니스용 Skype Online 간에 고품질의 연결을 설정 하는 것이 중요 합니다. 이 작업을 수행 하는 가장 좋은 방법은 모든 연결에 걸친 비즈니스용 Skype Online의 최고 트래픽 볼륨에 맞게 네트워크 용량을 기준으로 내부 네트워크 및 클라우드 연결을 설정 하는 것입니다.
  
Azure Express는 비즈니스용 Skype Online을 포함 한 Office 365 서비스에 대 한 요구 사항이 아닙니다. 그러나 Azure Express 경로는 Office 365에 대 한 연결이 비즈니스용 Skype 네트워크 성능 요구 사항을 충족 하는지 확인 하 고 비즈니스용 Skype Online 미디어 품질 환경을 최적화 하는 데 도움이 될 수 있는 배포 옵션 중 하나입니다.
  
> [!TIP]
> 이 항목에서는 전체 네트워킹 성능 지침을 제공 하지만, 네트워크 평가에 대 한 전체 지침은이 문서의 범위를 벗어납니다. 철저 하 고 완전 한 네트워크 평가의 일부로 네트워크 성능 측정치를 도울 수 있는 비즈니스용 Skype Online 파트너의 목록을 찾으려면 [비즈니스용 Skype 파트너 솔루션](http://partnersolutions.skypeforbusiness.com/)을 방문 하세요. 
  
## <a name="network-connectivity-requirements-to-skype-for-business-online"></a>비즈니스용 Skype Online에 대 한 네트워크 연결 요구 사항

### <a name="factors-that-impact-skype-for-business-online-media-quality"></a>비즈니스용 Skype Online 미디어 품질에 영향을 주는 요인

비즈니스용 Skype Online 실시간 미디어 (오디오, 비디오 및 응용 프로그램 공유)에 영향을 주는 다양 한 요소가 사용 되는 장치, 환경, 네트워크 연결 등이 포함 됩니다. 
  
#### <a name="devices"></a>디바이스

실시간 미디어 세션에서는 헤드셋 및 웹 캠 같은 모든 참가자가 사용 하는 미디어 캡처 및 렌더링 장치가 전체적인 오디오 및 비디오 품질에 큰 영향을 줍니다. 잘못 된 장치 드라이버를 사용 하는 낮은 음질 장치 또는 장치는 오디오에 대 한 전체적인 음질을 낮추고 비디오의 이미지 품질을 낮춥니다. 다른 한편, 인증 된 장치 또는 좋은 음질 장치는 에코 취소, 노이즈 필터링, 비디오 해상도 및 대기 시간 줄이기에 대 한 도움말을 표시 합니다.
  
인증 된 오디오 및 비디오 미디어 장치는 필요 하지 않지만 최적의 미디어 환경을 위해 비즈니스용 Skype에 대해 인증 되는 매우 권장 되는 장치입니다. 모든 비즈니스용 Skype 인증 디바이스 목록은 비즈니스용 [skype의 휴대폰 및 장치](https://technet.microsoft.com/office/dn947482)를 참조 하세요. 비즈니스용 skype **관리 센터**에 있는 비즈니스용 [Skype Online 통화 품질 대시보드](/microsoftteams/turning-on-and-using-call-quality-dashboard)를 사용 하 여 사용 중인 장치가 올바르게 작동 하는지 확인 하 고 오디오 및 비디오 미디어 품질을 모니터링할 수 있습니다.
  
> [!TIP]
> **가장 최적의 비즈니스용 Skype 미디어 품질 환경을 위해서는 인증 된 장치가 필요**합니다.
  
모든 미디어 장치, 비즈니스용 Skype 클라이언트, 실시간 미디어 흐름을 통해 비즈니스용 Skype 서버에는 몇 가지 대기 시간이 도입 된다는 점에 유의 해야 합니다. 디바이스 및 소프트웨어 처리 대기 시간이 네트워크 대기 시간을 포함 하 여, 종단간 전체 대기 시간 및 최종 사용자의 환경에 큰 영향을 미칩니다.
  
#### <a name="environment"></a>환경

오디오 및 비디오 장치를 사용 하는 환경과 주변 영역에 오디오 및 비디오 품질로 사용할 수 있는 또 다른 중요 한 요소입니다. 잡음이 있는 환경에서 전화를 거는 사용자는 오디오를 muffled 하 고 명확 하 게 조작할 수 있습니다. 어둡거나 저렴 한 환경에서 사용자는 비디오에 대 한 선명한 이미지 화질을 밝게 만들 수 없습니다. 회의실 설정에서 마이크와 비디오 장치의 위치는 참가자가 수신할 사운드 및 이미지 품질에 직접적인 영향을 미칩니다.
  
사용자의 오디오 및 비디오 환경에 대 한 자세한 그림을 얻으려면 비즈니스용 Skype 앱 **도구** > **옵션** > **오디오 장치** 또는 **비디오 장치** 를 사용 하 여 장치를 변경 하 고 설정을 사용자 지정 합니다.

#### <a name="network"></a>네트워크

IP 네트워크를 통한 실시간 미디어의 품질은 네트워크 연결의 품질에 큰 영향을 주지만, 특히 다음의 금액에 의해
  
- **대기 시간** 네트워크의 A 점에서 B 지점의 IP 패킷을 가져오는 데 걸리는 시간입니다. 이 네트워크 전파 지연은 본질적으로 두 점과 라이트의 속도 사이에서 다양 한 라우터가 차지 하는 추가 오버 헤드를 포함 하 여 실제 거리에 연결 됩니다. 대기 시간은 단방향 또는 왕복 시간 (RTT)으로 측정 됩니다.
    
- **패킷 손실** 이는 특정 시간 창에서 손실 되는 패킷의 백분율로 정의 되는 경우가 많습니다. 패킷 손실로 인해 오디오 품질에 직접적인 영향을 주지 않고, 거의 전혀 영향을 주지 않는 개별 손실 패킷, 그리고 완전 한 오디오 컷오프로 인 한 연속 버스트 손실.
    
- **패킷 간 도착 지터 또는 간단히 지터** 연속 된 패킷 간의 지연 시간 변경입니다. 비즈니스용 Skype를 포함 하 여 대부분의 최신 VoIP 소프트웨어는 버퍼링을 통해 일부 지터 수준에 적응할 수 있습니다. 이는 지터가 지터의 효과를 알리는 버퍼링을 초과 하는 경우에만 해당 됩니다.
    
> [!NOTE]
>  지터에 대 한 버퍼링을 통해 종단 간 대기 시간이 길어집니다.
  
다양 한 비즈니스용 Skype Online 실시간 미디어 세션 및 다른 Office 365 서비스 및 기타 비즈니스 응용 프로그램에서 생성 된 다른 네트워크 소통을 통해 네트워크 혼잡을 방지 하 고 우수한 미디어 실시간 미디어를 보장 하는 것이 중요 한 전체 네트워크 경로에 대 한 대역폭이 충분 한지 확인 합니다. , 비디오 및 응용 프로그램 공유) 품질. 
  
#### <a name="implementing-quality-of-service-qos-across-congested-networks"></a>혼잡 네트워크에서 QoS (서비스 품질) 구현

또한 네트워크 상에 서 트래픽이 정체 됨에 따라 미디어 품질이 크게 저하 될 수 있습니다. 오디오 및 비디오 패킷이 네트워크를 더 빠르게 여행 하 고 혼잡 네트워크의 다른 네트워크 트래픽에 대 한 우선 순위를 지정할 수 있도록 하기 위해 QoS (서비스 품질)를 사용 하 여 오디오 및 비디오 통신을 위한 최적의 최종 사용자 환경을 제공 하는 데 도움이 됩니다.
  
QoS는 오디오 또는 비디오 데이터를 운반 하는 네트워크 패킷에 더 높은 우선 순위를 할당할 수 있는 방법을 제공 합니다. 이러한 패킷에 더 높은 우선 순위를 할당 하는 경우 오디오 및 비디오 통신은 네트워크를 통해 더 빠르게 출장 하 고 파일 전송, 웹 검색 또는 데이터베이스 백업과 관련 된 네트워크 세션 보다는 중단을 덜 수 있습니다. 이는 파일 전송 또는 데이터베이스 백업에 사용 되는 네트워크 패킷에 대 한 우선 순위는 "최고 작업량"으로 지정 되어 있으므로 네트워크 정체 때문에 큰 영향을 받지 않기 때문입니다. 미디어 (오디오, 비디오, 응용 프로그램 공유) 패킷에 더 높은 우선 순위를 할당 하지 않은 경우에도 "최상 작업량"으로 지정 된 상태로 두면 다른 모든 네트워크 트래픽과 함께 처리 됩니다. 네트워크 정체의 양에 따라,이는 사용자에 대 한 전체적인 오디오 및 비디오 품질 환경에서 발생할 수 있습니다.
  
네트워크 내의 네트워크 정체에 영향을 주지 않도록 네트워크에서 QoS를 구현 하는 것이 좋습니다. 그러나이 경우 최대의 영향을 줄 수 있으려면 모든 네트워킹 종점이 qos를 지원 해야 하며, 모든 끝점에서 QoS 표시 및 패킷 우선 순위를 준수 해야 함을 의미 합니다. 비즈니스용 Skype Online 서비스는 Microsoft 네트워크 내의 QoS 표시 및 우선 순위를 준수 합니다. 그러나 회사 네트워크에서 Microsoft 네트워크까지 인터넷 같은 공용 연결을 통해 라우팅되는 트래픽은 QoS 표시와 패킷 우선 순위를 유지 하지 않습니다. [Azure express](https://azure.microsoft.com/services/expressroute/) 를 사용 하 여 네트워크에서 Office 365에 대 한 개인 연결을 제공 하면 최종 사용자의 전체 오디오 및 비디오 품질이 향상 된 QoS 표시와 패킷 우선 순위를 유지 하는 배포 솔루션을 제공할 수 있습니다.
  
## <a name="network-performance-requirements-to-connect-to-skype-for-business-online"></a>비즈니스용 Skype Online에 연결 하기 위한 네트워크 성능 요구 사항
<a name="bkNetworkPerf"> </a>

비즈니스용 Skype 실시간 미디어는 다양 한 장치, 클라이언트 앱, 서버 소프트웨어, 다양 한 네트워크에서 이동 합니다. 실시간 미디어의 종단 간 대기 시간은 모든 구성 요소 및 네트워크 세그먼트에서 발생 하는 총 대기 시간입니다. 종단 간 네트워크 연결의 품질은 품질이 낮은 네트워크 세그먼트에 따라 결정 됩니다. 이 세그먼트는이 네트워크 트래픽에 대 한 병목 현상 역할을 합니다.
  
다음 다이어그램은 비즈니스용 Skype 참가자 간 회의의 단방향 오디오 흐름을 보여 줍니다.
  
![Express 경로 통화 흐름.](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
이 회의 시나리오에서 미디어 경로는 다음 네트워크 세그먼트를 통해 구성 됩니다.
  
1. **사용자 1에서 Microsoft 네트워크 가장자리 까지의 연결** 여기에는 일반적으로 WiFi 또는 이더넷과 같은 네트워크 연결, 사용자 1에서 인터넷 송신 시점으로의 WAN 연결 (네트워크에 지 장치), 네트워크 경계에서 Microsoft 네트워크에 지에 대 한 인터넷 연결 등이 포함 됩니다.
    
2. **Microsoft 네트워크 내에서의 연결** 이는 Microsoft Edge에서 비즈니스용 Skype Online 데이터 센터 (A/V 회의 서버를 사용 하는 경우)입니다.
    
3. **Microsoft 네트워크 내에서의 연결** 비즈니스용 Skype Online 데이터 센터와 Microsoft 네트워크 경계 사이에 있습니다.
    
4. **Microsoft 네트워크 edge에서 사용자 2로의 연결** 여기에는 네트워크 가장자리에서 Microsoft 네트워크에 지, 사용자 2에서 인터넷 송신 시점 (네트워크에 지)으로의 WAN 연결, WiFi 또는 이더넷과 같은 네트워크 연결 등의 인터넷 연결이 포함 됩니다.
    
다음 다이어그램은 비즈니스용 Skype Online PSTN 통화의 구성 요소 및 네트워크 세그먼트의 분석 결과를 보여 줍니다.
  
![Express로 PSTN 통신 회사 호출 흐름.](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
PSTN 통화 시나리오에서 미디어 경로는 다음 네트워크 세그먼트와 교차 합니다.
  
1. **비즈니스용 Skype 클라이언트 발신자에서 Microsoft 네트워크의 가장자리로의 연결** 여기에는 일반적으로 WiFi 또는 이더넷과 같은 네트워크 연결, 비즈니스용 Skype 클라이언트 발신자의 WAN 연결, 인터넷 송신 위치 (네트워크 경계 장치), 네트워크 경계에서 Microsoft 네트워크에 지에 대 한 인터넷 연결 등이 포함 됩니다.
    
2. **Microsoft 네트워크 내에서의 연결** 이는 중재 서버를 사용 하는 Microsoft Edge에서 비즈니스용 Skype Online 데이터 센터 사이에 있습니다.
    
3. **Microsoft 네트워크 내에서의 연결** 비즈니스용 Skype Online 데이터 센터와 Microsoft 네트워크 경계 사이에 있습니다.
    
4. **Microsoft 네트워크와 PSTN 서비스 공급자 파트너 간의 연결** 이것은 Microsoft 네트워크 외부에 있는 비즈니스용 Skype 클라이언트에서 PSTN 통화를 하는 데 존재 하는 연결입니다.
    
### <a name="network-performance-requirements-from-a-skype-for-business-client-to-microsoft-network-edge"></a>비즈니스용 Skype 클라이언트에서 Microsoft 네트워크에 지에 이르기까지 네트워크 성능 요구 사항
<a name="bkSfBClienttoEdge"></a>

비즈니스용 Skype media 품질을 최적화 하려면 다음 네트워크 성능 메트릭이 회사 네트워크에서 Microsoft 네트워크에 지에 연결 하는 데 필요 합니다. 이 네트워크 세그먼트에는 내부 네트워크가 포함 되며, 여기에는 모든 WiFi 및 이더넷 연결, WAN 연결을 통한 회사 사이트 간 트래픽 (예: 멀티 프로토콜 레이블 전환 (MPLS), Microsoft 네트워크 Edge에 대 한 비트 경로 연결)이 포함 됩니다.
  
> [!CAUTION]
> **회사 네트워크의 비즈니스용 Skype 클라이언트와 Office 365 서비스 간의 연결은 다음 네트워크 성능 요구 사항 및 임계값을 충족 해야 합니다.**
  
|||
|:-----|:-----|
|**미터** <br/> |**대상** <br/> |
|대기 시간 (단방향)  <br/> |< 50ms  <br/> |
|지연 (RTT 또는 왕복 시간)  <br/> |< 100ms  <br/> |
|버스트 패킷 손실  <br/> |200ms 간격 중 10% <  <br/> |
|패킷 손실  <br/> |15s 간격 중 1% <  <br/> |
|패킷 간 도착 지터  <br/> |15s 간격 중 30ms <  <br/> |
|패킷 순서 다시 매기기  <br/> |<0.05% 주문 종료 패킷  <br/> |
   
 **기타 성능 대상 요구 사항:**
  
- Microsoft 네트워크에는 전세계의 160 Edge 위치가 있습니다. 전세계의 주요 인터넷 서비스 공급자 (Isp)에 게 이러한 Edge 사이트를 통해 작업 합니다. 대기 시간 메트릭 대상은 회사 사이트 또는 사이트를 가정 하 고 Microsoft 경계는 동일한 대륙에 있습니다.
    
- Microsoft 네트워크에 지에 연결 되는 회사 사이트 또는 사이트에는 WiFi 또는 다른 무선 기술인 첫 번째 홉 네트워크 액세스가 포함 되어 있습니다. 
    
- 네트워크 성능 대상은 적절 한 대역폭과 서비스 품질 계획을 가정 합니다. 즉, 네트워크 연결이 최대 부하에 도달 했을 때 비즈니스용 Skype 실시간 미디어 소통량에 직접적인 적용 됩니다.
    
### <a name="network-performance-requirements-from-your-network-edge-to-microsoft-network-edge"></a>네트워크 경계에서 Microsoft 네트워크에 지에 이르기까지 네트워크 성능 요구 사항
<a name="bkYourNetworkEdge"> </a>

다음은 네트워크 경계와 Microsoft 네트워크 경계 간의 연결에 필요한 네트워크 성능 목표 또는 임계값입니다. 이 네트워크 세그먼트는 고객의 내부 네트워크 또는 WAN을 제외 하 고, 인터넷을 통해 전송 되는 네트워크 트래픽 또는 Express 경로 파트너 네트워크를 통해 사용자를 테스트 하는 경우를 위한 것 이며, Express 경로를 사용 하 여 성능 서비스 수준 계약 (SLA)을 협상할 때도 사용할 수 있습니다.
  
> [!CAUTION]
> **회사 네트워크 경계와 Microsoft 네트워크 edge 간의 연결은 다음 네트워크 성능 요구 사항 및 임계값을 충족 해야 합니다.**
  
|||
|:-----|:-----|
|**미터** <br/> |**대상** <br/> |
|대기 시간 (단방향)  <br/> |< 30ms  <br/> |
|대기 시간 (RTT)  <br/> |< 60ms  <br/> |
|버스트 패킷 손실  <br/> |200 ms interval 동안 1% <  <br/> |
|패킷 손실  <br/> |15s 기간 동안 0.1% <  <br/> |
|패킷 간 도착 지터  <br/> |모든 15s 기간 동안 15ms <  <br/> |
|패킷 순서 다시 매기기  <br/> |<0.01% 주문 종료 패킷  <br/> |
   
 **기타 성능 대상 요구 사항:**
  
- 성능 목표는 회사의 네트워크 경계와 가까운 Microsoft 네트워크 가장자리와 동일한 대륙에 연결 되어 있어야 합니다.
    
- 네트워크 성능 대상은 적절 한 대역폭과 서비스 품질 계획을 가정 합니다. 이는 또한 네트워크 연결이 최고 부하 상태일 때 비즈니스용 Skype의 실시간 미디어 트래픽에 적용 됩니다. 적절 한 대역폭과 QoS 계획을 위해서는 [비즈니스용 Skype Online의 express 경로 및 qos](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)를 참조 하세요.
    
## <a name="measuring-network-performance"></a>네트워크 성능 측정
<a name="bkNetworkPerf"> </a>

회사 네트워크 사이트에서 네트워크에 지에 이르기까지, 특히 대기 시간 및 패킷 손실에 대 한 실제 네트워크 성능을 측정 하기 위해 ping 등의 도구를 사용 하 여 Microsoft Edge 및 데이터 센터 사이트에서 실행 되는 비즈니스용 Skype media 릴레이 서비스 집합에 대해 테스트할 수 있습니다. 

>[!NOTE]
> Ping을 통해 네트워크 성능을 측정 하는 것은 유효 하지 않습니다. 이런 이유로 애니캐스트 IP 노출은 2020 년 1 월부터 ICMP 요청에 대 한 응답을 중지 합니다. 네트워크 performace 효과적으로 측정 하기 위해 Microsoft는 [네트워크 Assesment 도구](https://www.microsoft.com/download/details.aspx?id=53885)를 권장 합니다.
  
Microsoft 네트워크에 대 한 인터넷 연결을 테스트 하려면 비즈니스용 Skype 미디어 릴레이의 다음 Vip를 테스트 하는 것이 좋습니다. *애니캐스트 VIP* 는 테스트 위치에 가장 가까운 Microsoft 네트워크에 지 사이트에 있는 미디어 릴레이의 IP 주소로 확인 됩니다.
  
||||
|:-----|:-----|:-----|
|**IP 주소** <br/> |**유형** <br/> |**위치** <br/> |
|13.107.8.2  <br/> |VIP  <br/> |월드 와이드 애니캐스트 IP  <br/> |
   
 **다음은 네트워크 성능을 평가 하는 데 따르는 몇 가지 높은 수준의 권장 사항입니다.**
  
- 내부 네트워크 및 Office 365의 연결을 평가 해야 합니다.
    
- 장기간에 걸쳐 모든 네트워크에 대 한 데이터를 평가 하 고 수집 해야 합니다. 모든 비즈니스 일과 시간에 대 한 사용 패턴을 볼 수 있도록 최소 일주일 동안 네트워크 성능 테스트를 수행 하는 것이 좋습니다. 이렇게 하면 사용량이 가장 많은 시간이 표시 됩니다.
    
- 네트워크 성능 측정의 여러 샘플을 사용 해야 합니다. 전체 기간 동안 데이터를 수집 하는 동안 회사 사이트에서 10 분 마다 측정 하는 것이 좋습니다. 비즈니스용 Skype Online 네트워크 성능 요구 사항을 비교 하려면이 예제 데이터 집합의 90 번째 백분위 수 측정값 값을 사용 합니다. 
    
- 네트워크의 성능을 지속적으로 평가 해야 합니다. 네트워크 사용량은 사용 패턴 변경, 많은 대역폭을 사용 하는 새로운 엔터프라이즈 기반 응용 프로그램, 조직 또는 물리적 회사 위치 변경으로 인해 시간에 따라 달라 집니다. 이러한 네트워크 성능 요구 사항 및 대상/임계값에 대해 네트워크 성능을 지속적으로 모니터링 하 고 적시에 조정 하 여 최적의 실시간 미디어 품질을 유지 하는 것이 중요 합니다. 
    
## <a name="measuring-network-performance-using-azure-vms"></a>Azure Vm을 사용 하 여 네트워크 성능 측정
<a name="bkNetworkPerf"> </a>

Microsoft 네트워크에 지 사이트에 대해 테스트 하는 대신 Microsoft Azure 클라우드에서 서비스에 대 한 테스트 설정을 활용 하는 비즈니스용 Skype 고객 및 파트너의 네트워크 평가 솔루션이 있습니다. 이러한 솔루션에서는 Azure 클라우드에서 서비스로 설정 된 사용자 지정 끝점에 대 한 네트워크 평가 도구 테스트 지연, 패킷 손실 및 지터를 확인 합니다. 따라서 네트워크 경계와 네트워크 평가 서비스를 호스트 하는 Azure 데이터 센터 간에 Microsoft 네트워크 내에서 연결 되는 추가 네트워크 세그먼트 하나를 통해 테스트를 진행할 수 있습니다.
  
Azure에서 호스트 하는 테스트 서비스를 기반으로 하는 이러한 네트워크 평가 솔루션 국가 및/또는 지역 내에서 네트워크 평가를 수행 하는 것이 좋습니다. 예를 들어 동부 미국에 있는 고객 사이트의 경우 Azure의 미국 데이터 센터 지역에서 호스팅되는 테스트 서비스 인스턴스에 대해 평가를 수행 해야 합니다. 
  
다음은 Azure 서비스 기반 네트워크 평가 설정에 대 한 RTT (대기 시간) 대상입니다. 단방향 대기 시간 대상은 해당 RTT 대상의 절반이 됩니다. 패킷 손실 및 지터 목표는 Skype 미디어 릴레이 기반 테스트에 대해 정의 된 것과 동일 하 게 유지 됩니다.
  
|||||
|:-----|:-----|:-----|:-----|
|**고객 지역** <br/> |**Azure 지역** <br/> |**네트워크 경계-(RTT () Azure (왕복 시간)** <br/> |**사이트-Azure RTT (왕복 시간)** <br/> |
|중부 US  <br/> |중부 US  <br/> |99  <br/> |139  <br/> |
|미국 동부  <br/> |미국 동부  <br/> |86  <br/> |126  <br/> |
|대한민국 미국 중부  <br/> |대한민국 미국 중부  <br/> |97  <br/> |137  <br/> |
|미국 중부 US  <br/> |미국 중부 US  <br/> |94  <br/> |134  <br/> |
|미국 서 부  <br/> |미국 서 부  <br/> |94  <br/> |134  <br/> |
|하와이 미국  <br/> |미국 서 부  <br/> |116  <br/> |156  <br/> |
|캐나다 중부  <br/> |캐나다 중부  <br/> |138  <br/> |178  <br/> |
|캐나다 동부  <br/> |캐나다 동부  <br/> |131  <br/> |171  <br/> |
|동유럽  <br/> |동유럽  <br/> |99  <br/> |139  <br/> |
|유럽 서유럽  <br/> |유럽 서유럽  <br/> |95  <br/> |135  <br/> |
|동아시아  <br/> |동아시아  <br/> |118  <br/> |158  <br/> |
|동남 아시아  <br/> |동남 아시아  <br/> |97  <br/> |137  <br/> |
|일본 동부  <br/> |일본 동부  <br/> |111  <br/> |151  <br/> |
|일본 서쪽  <br/> |일본 서쪽  <br/> |118  <br/> |158  <br/> |
|브라질 남부  <br/> |브라질 남부  <br/> |70  <br/> |110  <br/> |
|오스트레일리아 동부  <br/> |오스트레일리아 동부  <br/> |124  <br/> |164  <br/> |
|오스트레일리아 남동쪽  <br/> |오스트레일리아 남동쪽  <br/> |124  <br/> |164  <br/> |
|중앙 인도  <br/> |중앙 인도  <br/> |103  <br/> |143  <br/> |
|남 인도  <br/> |남 인도  <br/> |103  <br/> |143  <br/> |
|서쪽 인도  <br/> |서쪽 인도  <br/> |103  <br/> |143  <br/> |
|중국 동부  <br/> |중국 동부  <br/> |120  <br/> |160  <br/> |
|중국 북부  <br/> |중국 북부  <br/> |120  <br/> |160  <br/> |
   
## <a name="media-quality-and-expressroute"></a>미디어 품질과 Express 경로
<a name="bkNetworkPerf"> </a>

Office 365의 Azure Express 경로는 Office 365에 연결 하기 위한 전용 네트워크 연결입니다. 이는 고객에 게 Office 365 네트워크 트래픽이 취하는 경로를 제어할 수 있는 능력을 제공 합니다. 더 이상, 알 수 없는 통신 업체, 공급자, Isp에 의해 데이터가 전달 되는 인터넷에서 발생 하는 예측 불가능 한 라우팅에 신경 쓰지 않아도 됩니다. Express 경로를 통해 전송 되는 네트워크 트래픽은 Express 경로 네트워크에서 Microsoft 네트워크로 바로 전송 됩니다. 이렇게 하면 고객이 Office 365를 전용 연결을 통해 자체의 오프 사이트 데이터 센터에 있는 것 처럼 취급할 수 있습니다.
  
Azure Express는 모든 Office 365 라이선스 제공에 사용할 수 있습니다. 그러나 Office 365에서는 전역 라우팅을 사용 하도록 설정 하는 데 Azure Express Premium 추가 기능이 필요 합니다. 500 대 중에서 대 중 하나 이상을 구현 하는 고객에 게 추가 비용 없이 필요한 *express 가능 Premium 추가 기능* 을 받을 수 있습니다.
  
### <a name="is-expressroute-required-for-good-media-quality"></a>미디어 품질을 위해서는 Express가 필요 한가요?

Azure Express 경로는 비즈니스용 Skype Online 미디어 품질을 최대한 활용 하기 위한 요구 사항이 아닙니다. 그러나 클라우드 연결이 비즈니스용 Skype 네트워크 성능 목표 또는 임계값을 충족 하는지 확인 하는 데 도움이 되는 배포 옵션 중 하나입니다.
  
Office 365는 인터넷을 사용 하는 고성능 및 안전한 서비스입니다. 새로운 보안 기능과 지역 경계 노드에 계속 투자 하 여 보안 및 성능을 지속적으로 개선 합니다. Azure Express는 비즈니스용 Skype Online을 포함 한 Office 365 서비스에 대 한 요구 사항이 아닙니다. Azure Express 경로는 Office 365에 대 한 연결이 비즈니스용 Skype 네트워크 성능 요구 사항을 충족 하는지 확인 하 고 비즈니스용 Skype Online media 품질 환경을 최적화 하는 데 도움이 되는 배포 옵션 중 하나입니다.
  
비즈니스용 Skype Online 미디어 품질의 경우, 회사 사이트와 Microsoft 네트워크 경계 간의 연결이 [네트워크 성능 요구 사항에서 비즈니스용 Skype 클라이언트에서 microsoft 네트워크로](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge) 의 성능 목표를 충족 하 고, 네트워크 가장자리와 microsoft 네트워크 가장자리 간의 연결이 네트워크 [가장자리에서 microsoft 네트워크 edge에 이르기까지 네트워크 성능 요구 사항에 대](media-quality-and-network-connectivity-performance.md#bkYourNetworkEdge)한 성능 목표를 충족 하는지 확인 해야 합니다.  
  
또한 내부 네트워크 및 클라우드 연결 용량을 비롯 하 여 최대 미디어 트래픽 볼륨을 수용 하는 회사의 실제 네트워크 연결을 사용 하는 것이 중요 합니다. Azure Express 경로는 고객이 비즈니스용 Skype Online 클라우드 연결이 모든 성능 요구 사항을 충족 하는지 확인 하는 데 도움이 되는 다양 한 방법 중 하나입니다.
  
### <a name="is-expressroute-required-for-voice-quality-sla"></a>음성 품질 SLA에는 Express가 필요 한가요?

아니요, 비즈니스용 Skype Online 음성 품질 SLA에는이를 사용할 필요가 없습니다. 비즈니스용 [Skype Online 음성 품질 SLA](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37) 는 해당 사용자가 모든 종류의 VOIP 또는 PSTN 통화를 할 수 있는 올바른 라이선스 및 구독 내 비즈니스용 skype online voice service 사용자가 설정한 모든 적격 통화에 적용 됩니다. 음성 품질 SLA에는 다음 조건이 모두 해결 되어 있어야 합니다.
  
- Microsoft 인증 된 IP 휴대폰에서 전화를 걸고 있습니다.
    
- 유선 이더넷 연결.
    
- Microsoft 네트워크 문제로 인 한 음성 음질 문제
    
> [!NOTE]
> 음성 품질 SLA는 저렴 한 통화 품질이 전화 접속 파트너 및 기타 네트워크를 포함 하 여 Microsoft가 아닌 네트워크의 문제로 인해 발생 하는 경우 이러한 통화를 제외 합니다. 
  
### <a name="internet-or-azure-expressroute"></a>인터넷 또는 Azure Express 경로

비즈니스용 Skype Online에 대 한 네트워크 연결 옵션을 결정 하기 전에, 고객은 비즈니스용 [Skype online에 연결 하기 위해 네트워크 성능 요구 사항](media-quality-and-network-connectivity-performance.md#bkNetworkPerf)에 설명 된 네트워크 성능 요구 사항에 따라 네트워크 및 현재 인터넷 연결을 평가 해야 합니다.
  
현재 인터넷 연결을 통한 네트워크 성능이 최고 시간 동안 충분 한 용량을 유지 하도록 설정 되어 있고 사이트의 네트워크 성능 요구 사항을 Microsoft 네트워크 경계 및 네트워크 경계에서 Microsoft 네트워크 가장자리로 충족 하는 경우에는 계속 해 서 기존 인터넷 연결을 사용 하 여 비즈니스용 Skype Online에 연결할 수 있습니다.
  
네트워크 성능 요구 사항이 충족 되지 않는 회사 사이트의 경우에는 먼저 기존 네트워크 서비스 공급자와 협력 하 여 전반적인 네트워크 성능을 향상 하는 것이 좋습니다. 그러나 아직 충족 되지 않는 경우 Azure Express 경로 사용은 비즈니스용 Skype Online 클라우드 연결이 네트워크 성능 요구 사항을 충족 하는 데 도움이 될 수 있도록 지원 합니다.
  
Azure Express 경로는 다음과 같은 추가 혜택을 제공 합니다.
  
- 네트워크와 Microsoft 네트워크 사이의 연결 가용성에 대 한 SLA (서비스 수준 계약)입니다. Express 경로에는 보장 된 가용성 SLA (99.9%)가 있습니다.
    
- Office 365 서비스에 필요한 대역폭을 계획 하 고 보장 합니다. 이 작업을 수행 하려면 Express 경로를 사용 하 여 Office 365 트래픽 또는 비즈니스용 Skype 트래픽을 보낸 다음 다른 모든 인터넷 트래픽이 네트워크에 대 한 다른 인터넷 송신/수신 지점을 통해 이동 하도록 합니다.
    
- Express 경로는 네트워크와 Microsoft 네트워크 간에 DSCP QoS 표식을 유지 하도록 설계 되었습니다.
    
Express 경로 QoS 및 용량 계획에 대 한 자세한 내용은 [비즈니스용 Skype Online의 express 경로 및 QoS](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)를 참조 하세요.
  
### <a name="can-i-setup-azure-expressroute-for-skype-for-business-online-only"></a>비즈니스용 Skype Online에 대 한 Azure Express를 설치할 수 있나요?

예, Azure Express 경로를 설정 하 여 회사 네트워크에서 비즈니스용 Skype Online에 대 한 탁월한 네트워크 연결을 유지할 수 있습니다. 이렇게 하면 사용자에 게 가장 최적화 된 실시간 미디어 품질이 제공 되지만, 이제 인터넷을 통해 다른 Office 365 서비스에 계속 연결할 수 있습니다.
  
BGP (Border Gateway Protocol)는 인터넷 상에 서 네트워크 트래픽을 라우팅하는 데 사용 되는 라우팅 프로토콜입니다. 인터넷을 통해 검색 된 자율적 시스템 간에 라우팅 정보를 교환 하도록 설계 되었습니다. BGP 커뮤니티 값은 수신 또는 송신 경로에 적용할 수 있는 특성 태그입니다. BGP 커뮤니티는 지리, 서비스 유형 또는 기타 기준에 따라 지정 된 대상에 연결 하는 데 사용할 아웃 바운드 링크를 수신에 알리는 데 주로 사용 됩니다.
  
BGP 커뮤니티 지원을 사용 하면 Microsoft는 자신이 속한 서비스에 따라 적절 한 BGP 커뮤니티 값을 사용 하 여 접두사와 경로에 태그를 지정 합니다. Microsoft는 공용 피어 링을 통해 알린 접두사 및 Microsoft 피어 링을 해당 하는 해당 BGP 커뮤니티 값으로 접두사가 호스팅되는 지역을 나타내는 태그를 지정 합니다. 커뮤니티 값을 사용 하 여 적절 한 라우팅 결정을 수행 하 여 최적의 라우팅을 제공할 수 있습니다. 비즈니스용 skype online BGP 커뮤니티 값을 사용 하 여 비즈니스용 Skype Online에 대해서만 Express 경로 연결을 설정할 수 있습니다. 자세한 정보는 사용자 [경로 라우팅 요구 사항](https://azure.microsoft.com/documentation/articles/expressroute-routing/)에서 확인할 수 있습니다.
  
## <a name="expressroute-connectivity-scenarios-for-skype-for-business-online"></a>비즈니스용 Skype Online에 대 한 Express 경로 연결 시나리오
<a name="bkNetworkPerf"> </a>

위의 권장 사항을 기반으로 하는 Express를 사용 하기로 결정 한 경우, 얻을 수 있는 여러 개의 Express 연결의 위치와 방법에 대 한 권장 사항을 참조 하세요.
  
### <a name="online-only-deployment---single-site"></a>온라인 전용 배포-단일 사이트

모든 사용자가 비즈니스용 Skype Online 서비스를 사용 하는 경우, 회사가 단일 물리적 위치를 중심으로 중앙에 있고 Azure Express 경로를 배포 하기로 결정 한 경우에는 회사 사이트 간에 가장 가까운 수의 [express 피어 링 위치](https://azure.microsoft.com/documentation/articles/expressroute-locations/)에 대 한 단일 경로 연결을 설정 해야 합니다.
  
다음 그래픽에서는 이러한 배포 형식의 예를 보여 줍니다. 이 예제에서 Contoso는 올랜도, FL에 위치한 대학입니다. Contoso는 1만 교직원 구성원 및 학생을 보유 하 고 있습니다. 해당 위치에서 Microsoft edge 사이트로의 인터넷 테스트는 최대 수업 시간 동안 5% 이상 패킷 손실이 발생 했습니다. 이는 특히 비즈니스용 Skype Online 실시간 트래픽에 대 한 Office 365의 네트워크 정체를 피할 수 있도록 과잉 프로 비전 된 대역폭을 사용 하 여 Office 365에 대 한 전용 연결을 제공 하기로 결정 했습니다. 이 사용자는 애틀랜타, GA MeetMe 사이트에서 Express 경로를 통해 Microsoft 클라우드에 연결 합니다.
  
![Express 경로 단일 사이트.](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### <a name="online-only-deployment---multiple-sites-on-the-same-continent"></a>온라인 전용 배포-동일한 대륙의 여러 사이트

회사에서 같은 지역 또는 대륙의 여러 사무실에 있는 비즈니스용 Skype Online 서비스를 사용 하는 경우 Azure Express 경로를 구현 하도록 선택한 경우 Express 경로를 사용 하 여 기본 사이트를 연결한 다음 필요에 따라 네트워크 성능 대상에 맞지 않는 다른 위치에 대 한 추가 경로 지정 피어 링을 추가 하는 것이 좋습니다.
  
다음 예제에서 Contoso는 미국 내 다른 사무실을 보유 하 고 있지만 뉴욕에 본사가 위치한는 미국 여행 서비스 회사입니다. Office 365에 연결 하기 위해 MPLS를 사용 하는 WAN을 통해 해당 사무실이 연결 되어 있습니다. 처음에는 Hoboken의 인터넷 라우터에서 Express 경로 연결을 설정 하 고 새로운 뉴저지는 뉴욕 MeetMe 사이트로 구성 합니다. 
  
이 설정을 사용 하면 대부분의 사이트에서 Microsoft 네트워크 (뉴욕 Edge 사이트)로 네트워크 소통량이 비즈니스용 skype 클라이언트 [에서 microsoft 네트워크 Edge로 네트워크 성능 요구 사항](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)에 설명 된 비즈니스용 skype 클라이언트 연결 네트워크 성능 목표를 충족할 수 있습니다. 그러나 Contoso의 서쪽에서 뉴욕 까지의 대기 시간은 50 밀리초 (1 방향) 이상입니다. 또한 Honolulu는 Contoso의 두 번째 가장 큰 office 이며, Honolulu에서 뉴욕 까지의 지연 시간은 80ms 단방향을 초과 합니다. 해당 사무소의 사용자에 게 적합 한 미디어 품질을 보장 하기 위해 Contoso는 San Jose 사이트와 실리콘 계곡을 위한 MeetMe 사이트 사이에 서쪽 해안 Express 연결을 추가 하기로 결정 했습니다.
  
![고속 라우터 다중 사이트-동일한 대륙.](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### <a name="online-only-deployment---multiple-sites-on-different-continents"></a>온라인 전용 배포-다른 대륙의 여러 사이트

모든 사용자가 비즈니스용 Skype Online 서비스를 사용 하는 경우, 여러 지역에 있는 여러 개의 실제 위치에 근무 하는 경우 Azure Express를 배포 하기로 결정 한 경우, 각 대륙의 기본 사이트 사이에 있는 각 대륙에 대해 하나 이상의 Express 경로 연결을 가장 가까운 [위치 지정 피어 링 위치로](https://azure.microsoft.com/documentation/articles/expressroute-locations/)설정 해야 합니다. 비용 vs 이점에 따라 네트워크 성능 대상이 충족 되지 않는 사이트에서 추가 Express 연결을 배포 하도록 선택할 수 있습니다.
  
다음 예제에서 Contoso는 북미와 유럽의 주요 도시에 사무소가 있는 대기업의 기업 법률 기업입니다. Contoso는 인터넷 연결 및 내부 네트워크 성능 평가에 따라 북미와 모든 유럽 사무소에 대 한 단일 Express 회로에 두 개의 Express 연결을 배포 하기로 결정 했습니다.
  
![여러 사이트와 대륙을 사용 하는 Express 경로입니다.](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### <a name="hybrid-deployment"></a>하이브리드 배포

온-프레미스 Lync 또는 비즈니스용 Skype 배포를 선택 하 고 하이브리드 비즈니스용 skype Online 통합을 구현 하는 경우 Azure Express를 배포 하기로 결정 한 경우, 각 온-프레미스 Lync 또는 비즈니스용 Skype Edge 사이트와 각 대륙에 대해 하나 이상의 Express 경로 연결에 대해 하나 이상의 Express 경로 연결을 사용 하는 것이 좋습니다. 각 대륙에 대 한 비용 vs 이점에 따라 네트워크 성능 대상이 충족 되지 않는 사무실에서 추가 Express 연결을 배포 하도록 선택할 수 있습니다.
  
온-프레미스 비즈니스용 Skype 배포를 사용 하는 경우에는 [Edge 서버 계획 및 배포 가이드](https://technet.microsoft.com/library/mt346417.aspx)를 따라야 합니다. 특히 Edge 서버는 네트워크 외부에서 연결할 수 있어야 합니다. 이는 일반적으로 Edge 서버에 라우팅할 수 있는 공용 IP 주소를 할당 하거나 NAT (network address translation)를 사용 하 여 수행 됩니다.
  
다음 예제에서 Contoso에는 기존의 온-프레미스 비즈니스용 기업 엔터프라이즈 음성 배포가 있습니다. 온-프레미스 사용자를 Office 365 온라인 서비스로 마이그레이션해야 합니다. 또한 하이브리드 배포를 사용 하 여 모든 온-프레미스 및 온라인 사용자에 대해 기존 PSTN 인프라를 계속 사용할 수 있도록 결정 했습니다. Contoso의 온-프레미스 데이터 센터 및 비즈니스용 Skype Edge 서버는 시카고에 있습니다. 해당 배포의 경우 Contoso는 시카고 데이터 센터와 시카고 Express 경로 사이에 하나의 Express 경로 연결을 설정 하기로 결정 했습니다. 또한 Honolulu office를 보다 효율적으로 사용할 수 있도록 서 부 해안 Express 연결을 추가 했습니다.
  
![Express 경로 하이브리드.](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### <a name="online-deployment-with-cloud-connector-edition"></a>클라우드 커넥터 에디션을 사용 하 여 온라인 배포

비즈니스용 Skype Online 클라우드 커넥터 에디션은 온-프레미스 PSTN 연결을 구현 하는 패키지 Vm (가상 컴퓨터) 집합으로 구성 된 하이브리드 제공입니다. 가상화 된 환경에서 최소의 비즈니스용 Skype 서버 토폴로지를 배포 하 여 기존의 온-프레미스 PSTN 음성 인프라를 통해 유선전화 및 휴대 전화로 전화를 걸고 받을 수 있게 됩니다.
  
Azure Express 경로 및 클라우드 커넥터 에디션을 배포 하기로 결정 한 경우, 각 대륙의 기본 사이트 사이에 있는 각 대륙에 대 한 하나 이상의 Express Route 연결을 가장 가까운 [위치 연결 피어 링 위치로](https://azure.microsoft.com/documentation/articles/expressroute-locations/)설정 하는 것이 좋습니다. 각 대륙에 대 한 비용 vs 이점에 따라 네트워크 성능 대상이 충족 되지 않는 사이트에서 추가 Express 연결을 배포 하도록 선택할 수 있습니다.
  
온-프레미스 비즈니스용 Skype 배포를 사용 하는 경우 [비즈니스용 Skype 클라우드 커넥터 에디션에 대 한 계획 가이드](https://technet.microsoft.com/library/mt605227.aspx)를 따라야 합니다. 특히 액세스에 지 및 A/V에 지 서비스에는 공용 IP 주소를 할당 하 고 Office 365 데이터 센터에서 연결할 수 있어야 합니다.
  
다음 예제에서 Contoso는 일부 주요 유럽 국가 및 도시에 현재 존재 하는 유럽 회계 기업입니다. 모든 사용자의 공동 작업 요구 사항에 맞게 비즈니스용 Skype Online에 등록 하는 경우, 이미 존재 하는 PSTN 인프라 및 통신 회사 계약을 계속 사용할 수 있도록 각 국가에 대해 클라우드 커넥터를 설정 하기로 결정 했습니다. 모든 사이트와 Microsoft 네트워크 Edge의 테스트에 따라, London의 단일 Express 연결을 통해 비즈니스용 skype 클라이언트의 비즈니스용 Skype 클라이언트 연결 네트워크 성능 목표 [를](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)충족 하는 데 도움이 되는 것을 확인 했습니다.
  
![Express 경로 구름 커넥터 1.](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
다음은 Contoso의 다른 배포 옵션입니다. 이 경우 클라우드 커넥터가 배포 된 각 사이트에서 Express 경로 연결을 설정 하기로 결정 했습니다. 
  
![Express 경로 구름 커넥터 2.](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## <a name="related-topics"></a>관련 항목

[비즈니스용 Skype Online의 ExpressRoute 및 QoS](expressroute-and-qos-in-skype-for-business-online.md)

  
 
