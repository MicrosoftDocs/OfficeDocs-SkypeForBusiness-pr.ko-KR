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
description: 이 항목에서는 비즈니스용 Skype Online 서비스에 대한 네트워크 성능 요구 사항 집합 및 네트워크 연결 평가에 따라 네트워크와 비즈니스용 Skype Online 간의 연결에 인터넷 또는 ExpressRoute를 사용할 수 있는 방법을 정의합니다. Microsoft 365 또는 Office 365에 대한 전용 연결을 위해 Azure ExpressRoute를 배포하기로 결정한 경우 이 문서에서는 다른 비즈니스용 Skype Online 배포 시나리오에서 ExpressRoute 연결을 계획하는 방법에 대한 지침도 제공합니다.
ms.openlocfilehash: d49dd3e925c71a9e0f2b73bbe364ad4478566cad
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164767"
---
# <a name="media-quality-and-network-connectivity-performance-in-skype-for-business-online"></a>비즈니스용 Skype Online의 미디어 품질 및 네트워크 연결 성능

이 항목에서는 비즈니스용 Skype Online 서비스에 대한 네트워크 성능 요구 사항 집합 및 네트워크 연결 평가에 따라 네트워크와 비즈니스용 Skype Online 간의 연결에 인터넷 또는 ExpressRoute를 사용할 수 있는 방법을 정의합니다. Microsoft 365 또는 Office 365에 대한 전용 연결을 위해 Azure ExpressRoute를 배포하기로 결정한 경우 이 문서에서는 다른 비즈니스용 Skype Online 배포 시나리오에서 ExpressRoute 연결을 계획하는 방법에 대한 지침도 제공합니다.
  
IP를 Real-Time 미디어(오디오, 비디오 및 애플리케이션 공유)의 품질은 종단 내 네트워크 연결의 품질에 크게 영향을 미치고 있습니다. 최적의 비즈니스용 Skype Online 미디어 품질을 위해 회사 네트워크와 비즈니스용 Skype Online 간에 고품질 연결이 있는지 반드시 확인합니다. 이 작업을 수행하기 위한 가장 좋은 방법은 모든 연결에서 비즈니스용 Skype Online의 최대 트래픽 볼륨을 수용할 수 있도록 네트워크 용량에 따라 내부 네트워크 및 클라우드 연결을 설정하는 것입니다.
  
Azure ExpressRoute는 비즈니스용 Skype Online을 포함한 Microsoft 365 및 Office 365 서비스에 대한 요구 사항이 아닙니다. 그러나 Azure ExpressRoute는 Microsoft 365 또는 Office 365에 대한 연결이 비즈니스용 Skype 네트워크 성능 요구 사항을 충족하고 최적의 비즈니스용 Skype Online 미디어 품질 환경을 보장하는 데 도움이 되는 배포 옵션 중 하나입니다.
  
> [!TIP]
> 이 항목에서는 전체 네트워킹 성능 지침을 제공하나 네트워크 평가에 대한 전체 지침은 이 문서의 범위를 벗어날 수 있습니다. 철저하고 완전한 네트워크 평가의 일부로 네트워크 성능 측정을 지원할 수 있는 비즈니스용 Skype Online 파트너 목록을 찾으면 비즈니스용 Skype 파트너 솔루션을 [방문하세요.](http://partnersolutions.skypeforbusiness.com/) 
  
## <a name="network-connectivity-requirements-to-skype-for-business-online"></a>비즈니스용 Skype Online에 대한 네트워크 연결 요구 사항

### <a name="factors-that-impact-skype-for-business-online-media-quality"></a>비즈니스용 Skype Online 미디어 품질에 영향을 미치는 요인

사용되는 장치, 환경 및 네트워크 연결을 포함해 비즈니스용 Skype Online Real-Time 미디어(오디오, 비디오 및 응용 프로그램 공유) 품질에 기여하는 여러 가지 요인이 있습니다. 
  
#### <a name="devices"></a>디바이스

Real-Time 미디어 세션에서 헤드셋 및 웹 캠과 같은 모든 참가자가 사용하는 미디어 캡처 및 렌더링 디바이스는 전반적인 오디오 및 비디오 품질에 큰 영향을 미치고 있습니다. 잘못된 장치 드라이버가 있는 낮은 품질의 장치 또는 디바이스는 오디오에 대한 전반적인 음질을 낮추고 비디오의 이미지 품질을 낮출 수 있습니다. 반면에 인증된 디바이스 또는 고품질 디바이스는 에코 취소, 노이즈 필터링, 비디오 해상도 및 대기 시간을 줄이는 데 도움이 됩니다.
  
인증된 오디오 및 비디오 미디어 장치가 필요하지는 않습니다. 가장 최적의 미디어 환경을 위해 비즈니스용 Skype 인증을 받은 장치를 권장합니다. 모든 비즈니스용 Skype 인증 장치 목록은 비즈니스용 Skype용 전화 및 장치를 [참조하세요.](https://technet.microsoft.com/office/dn947482) 비즈니스용 Skype 관리 센터에 있는 비즈니스용  [Skype Online](/microsoftteams/turning-on-and-using-call-quality-dashboard)통화 품질 대시보드를 사용하여 사용 중 장치가 올바르게 작동하고 있는지 확인하고 오디오 및 비디오 미디어 품질을 모니터링할 수 있습니다.
  
> [!TIP]
> 가장 최적의 비즈니스용 Skype 미디어 품질 환경을 위해서는 인증된 **장치가 필요합니다.**
  
미디어가 흐르는 모든 미디어 장치, 비즈니스용 Skype 클라이언트 및 비즈니스용 Skype 서버가 Real-Time 대기 시간이 발생하고 있다는 점에 유의해야 합니다. 디바이스 및 소프트웨어 처리 대기 시간과 네트워크 대기 시간은 네트워크 대기 시간에 큰 영향을 미치고 전체 전체 대기 시간 및 최종 사용자의 환경에 영향을 미치고 있습니다.
  
#### <a name="environment"></a>환경

사용자가 모임에 참석하고 오디오 및 비디오 장치를 사용하는 환경 및 주변 영역은 오디오 및 비디오 품질에 대한 또 다른 중요한 요소입니다. 시즈음 환경에서 호출하는 사용자는 오디오가 울려 퍼지며 불확실해집니다. 어둡거나 낮은 조명 환경의 사용자는 비디오에 대해 밝고 선명한 이미지 품질을 만들 수 없습니다. 회의실 설정에서 마이크와 비디오 장치의 위치는 참가자가 받을 소리 및 이미지 품질에 직접적인 영향을 미치게 됩니다.
  
사용자의 오디오 및 비디오 환경을 더 명확하게 확인하려면 비즈니스용 Skype 앱 도구 옵션 오디오 장치 또는 비디오 장치를 사용하여 사용 중 장치를 변경하고 설정을 사용자  >    >   지정합니다. 

#### <a name="network"></a>네트워크

IP 네트워크를 Real-Time 미디어의 품질은 네트워크 연결의 품질에 크게 영향을 주지만, 특히 다음의 양에 의해 크게 영향을 미치게 됩니다.
  
- **대기 시간** 네트워크의 지점 A에서 B 지점까지 IP 패킷을 수신하는 데 걸리는 시간입니다. 이 네트워크 전파 지연은 기본적으로 다양한 라우터에서 취한 추가 오버헤드를 포함하여 두 지점 간의 물리적 거리와 광속에 연결됩니다. 대기 시간은 단방 또는 RTT(왕복 시간)로 측정됩니다.
    
- **패킷 손실** 이는 종종 특정 기간에 손실되는 패킷의 백분율로 정의됩니다. 패킷 손실은 거의 영향을 주지 않고 개별 손실된 작은 패킷부터 전체 오디오를 차단하는 백백 버스트 손실까지 오디오 품질에 직접 영향을 미치게 됩니다.
    
- **패킷 간 도착 지터 또는 단순히 지터** 연속 패킷 간 지연의 평균 변경입니다. 비즈니스용 Skype를 포함한 대부분의 최신 VoIP 소프트웨어는 버퍼링을 통해 일부 수준의 지터에 맞게 조정될 수 있습니다. 지터가 버퍼링을 초과하는 경우 참가자가 지터의 효과를 알 수 있습니다.
    
> [!NOTE]
>  지터에 대한 버퍼링은 종단적 대기 시간을 증가합니다.
  
여러 동시 비즈니스용 Skype Online Real-Time 미디어 세션과 다른 Microsoft 365 또는 Office 365 서비스 및 기타 비즈니스 응용 프로그램에서 생성한 기타 네트워크 트래픽을 사용하여 네트워크를 비즈니스용 Skype Online 서비스에 연결하는 전체 네트워크 경로에 충분한 대역폭이 있는지 확인하여 네트워크 정체 방지 및 뛰어난 미디어 Real-Time 미디어(오디오, 비디오 및 응용 프로그램 공유) 품질을 보장하는 것이 중요합니다. 
  
#### <a name="implementing-quality-of-service-qos-across-congested-networks"></a>정비된 네트워크에서 QoS(서비스 품질) 구현

또한 네트워크의 트래픽 정체는 미디어 품질에 큰 영향을 미치게 됩니다. 오디오 및 비디오 패킷이 네트워크를 더 빠르게 이동하고 정체된 네트워크의 다른 네트워크 트래픽보다 우선 순위를 지정할 수 있도록 오디오 및 비디오 통신에 최적의 최종 사용자 환경을 제공하는 데 QoS(서비스 품질)를 사용할 수 있습니다.
  
QoS는 오디오 또는 비디오 데이터를 전달하는 네트워크 패킷에 더 높은 우선 순위를 할당하는 방법을 제공합니다. 이러한 패킷에 더 높은 우선 순위를 할당하면 오디오 및 비디오 통신이 파일 전송, 웹 검색 또는 데이터베이스 백업과 같은 네트워크 세션보다 더 빠르고 중단이 적을 수 있습니다. 이는 기본적으로 파일 전송 또는 데이터베이스 백업에 사용되는 네트워크 패킷이 우선 순위로 "최선"으로 할당되어 네트워크 정체에 큰 영향을 미칠 수 있기 때문에입니다. 미디어(오디오, 비디오 및 응용 프로그램 공유) 패킷에 더 높은 우선 순위를 할당하지 않은 경우 "최선"으로 할당된 경우 다른 모든 네트워크 트래픽과 함께 처리됩니다. 네트워크 정체 양에 따라 이로 인하여 사용자의 전반적인 오디오 및 비디오 품질 환경이 낮아질 수 있습니다.
  
네트워크 내의 네트워크 정체가 영향을 하지 않는지 확인하여 네트워크에서 QoS를 구현하는 것이 좋습니다. 그러나 최대 영향을 주기 위해 모든 네트워킹 엔드포인트는 QoS를 지원해야 합니다. 즉, 모든 엔드포인트가 QoS 표시 및 패킷 우선 순위 지정을 존중해야 합니다. 비즈니스용 Skype Online 서비스는 Microsoft 네트워크 내에서 QoS 표시 및 우선 순위 지정을 존중합니다. 그러나 회사 네트워크에서 Microsoft 네트워크로 인터넷과 같은 공용 연결을 통해 라우팅되는 트래픽은 QoS 표시 및 패킷 우선 순위를 유지하지 않습니다. [Azure ExpressRoute를](https://azure.microsoft.com/services/expressroute/) 사용하여 네트워크에서 Microsoft 365 또는 Office 365로의 비공개 연결은 QoS 마킹 및 패킷 우선 순위를 유지하여 최종 사용자의 전반적인 오디오 및 비디오 품질을 향상하는 배포 솔루션을 제공합니다.
  
## <a name="network-performance-requirements-to-connect-to-skype-for-business-online"></a>비즈니스용 Skype Online에 연결하기 위한 네트워크 성능 요구 사항
<a name="bkNetworkPerf"> </a>

비즈니스용 Skype Real-Time 미디어는 다양한 장치, 클라이언트 앱, 서버 소프트웨어 및 여러 네트워크를 통해 이동됩니다. 모든 구성 요소 및 네트워크 세그먼트에서 Real-Time 미디어의 전체 대기 시간입니다. 종단-종단 네트워크 연결의 품질은 최악의 품질이 있는 네트워크 세그먼트에 의해 결정됩니다. 이 세그먼트는 이 네트워크 트래픽에 대한 병목 현상의 역할을 합니다.
  
다음 다이어그램은 한 비즈니스용 Skype 참가자에서 다른 참가자로의 전화 회의의 단면 오디오 흐름을 보여 주는 다이어그램입니다.
  
![ExpressRoute 호출 흐름입니다.](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
이 회의 시나리오에서 미디어 경로는 다음 네트워크 세그먼트에 걸쳐 구성됩니다.
  
1. **사용자 1에서 Microsoft** 네트워크 가장자리로 연결 일반적으로 WiFi 또는 이더넷과 같은 네트워크 연결, 사용자 1에서 인터넷 발신 지점(네트워크 Edge 디바이스)으로의 WAN 연결, 네트워크 Edge에서 Microsoft 네트워크 Edge로의 인터넷 연결이 포함됩니다.
    
2. **Microsoft 네트워크 내 연결** 이는 A/V 회의 서버가 사용되는 Microsoft Edge-비즈니스용 Skype Online 데이터 센터 사이에 있습니다.
    
3. **Microsoft Network 내의 연결** 비즈니스용 Skype Online 데이터 센터와 Microsoft 네트워크 Edge 사이에 있습니다.
    
4. **Microsoft 네트워크 에지에서 사용자 2로 연결** 여기에는 네트워크 Edge에서 Microsoft 네트워크 Edge로의 인터넷 연결, 사용자 2에서 인터넷 발신 지점(네트워크 Edge)으로의 WAN 연결, WiFi 또는 이더넷과 같은 네트워크 연결이 포함됩니다.
    
다음 다이어그램은 비즈니스용 Skype Online PSTN 통화의 구성 요소 및 네트워크 세그먼트를 분석한 것입니다.
  
![ExpressRoute PSTN 통신사 호출 흐름입니다.](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
PSTN 호출 시나리오에서 미디어 경로는 다음 네트워크 세그먼트를 교차합니다.
  
1. **비즈니스용 Skype 클라이언트 발신자에서 Microsoft Network** 가장자리로 연결 일반적으로 WiFi 또는 이더넷과 같은 네트워크 연결, 비즈니스용 Skype 클라이언트 호출자에서 인터넷 발신 지점(네트워크 Edge 장치)으로의 WAN 연결, 네트워크 Edge에서 Microsoft 네트워크 Edge로의 인터넷 연결이 포함됩니다.
    
2. **Microsoft 네트워크 내 연결** 중재 서버가 사용되는 Microsoft Edge-비즈니스용 Skype Online 데이터 센터 사이에 있습니다.
    
3. **Microsoft Network 내의 연결** 비즈니스용 Skype Online 데이터 센터와 Microsoft 네트워크 Edge 사이에 있습니다.
    
4. **Microsoft Network와 PSTN** 서비스 공급자 파트너 간의 연결 Microsoft 네트워크 외부에 있는 비즈니스용 Skype 클라이언트에서 PSTN 통화를 걸기 위한 연결입니다.
    
### <a name="network-performance-requirements-from-a-skype-for-business-client-to-microsoft-network-edge"></a>비즈니스용 Skype 클라이언트에서 Microsoft Network Edge로의 네트워크 성능 요구 사항
<a name="bkSfBClienttoEdge"></a>

최적의 비즈니스용 Skype 미디어 품질을 위해 회사 네트워크에서 Microsoft 네트워크 Edge로의 연결에는 다음 네트워크 성능 메트릭 목표 또는 임계값이 필요합니다. 네트워크의 이 세그먼트에는 내부 네트워크가 포함됩니다. 여기에는 모든 WiFi 및 이더넷 연결, WAN 연결을 통해 회사 사이트-사이트 트래픽(예: MPLS(Multiprotocol Label Switching) 및 Microsoft 네트워크 Edge에 대한 인터넷 또는 ExpressRoute 파트너 연결이 포함됩니다.
  
> [!CAUTION]
> **회사 네트워크의 비즈니스용 Skype 클라이언트를 Microsoft 365 또는 Office 365 서비스에 연결하려면 다음 네트워크 성능 요구 사항 및 임계값을 충족해야 합니다.**
  
|||
|:-----|:-----|
|**메트릭** <br/> |**대상** <br/> |
|대기 시간(단 방법)  <br/> |< 50ms  <br/> |
|대기 시간(RTT 또는 왕복 시간)  <br/> |< 100ms  <br/> |
|패킷 손실 버스트  <br/> |<200ms 간격 동안 10%입니다.  <br/> |
|패킷 손실  <br/> |<간격 중 1%입니다.  <br/> |
|패킷 도착 간 지터  <br/> |<30ms 간격으로 설정  <br/> |
|패킷 다시 오더  <br/> |<0.05% 순서 비지정 패킷  <br/> |
   
 **기타 성능 목표 요구 사항:**
  
- Microsoft 네트워크에는 전 세계 160개 이상의 Edge 위치가 있습니다. 이러한 Edge 사이트를 통해 전 세계 주요 ISP(인터넷 서비스 공급자)와 함께 작업합니다. 대기 시간 메트릭 대상은 회사 사이트 또는 사이트와 Microsoft Edge가 동일한 대륙에 있는 것으로 가정합니다.
    
- Microsoft 네트워크 Edge 연결에 대한 회사 사이트 또는 사이트에는 WiFi 또는 다른 무선 기술일 수 있는 첫 번째 홉 네트워크 액세스가 포함됩니다. 
    
- 네트워크 성능 대상은 적절한 대역폭 및/또는 서비스 계획 품질을 가정합니다. 즉, 네트워크 연결이 최대 부하에 Real-Time 비즈니스용 Skype Real-Time 미디어 트래픽에 직접 적용됩니다.
    
### <a name="network-performance-requirements-from-your-network-edge-to-microsoft-network-edge"></a>네트워크 Edge에서 Microsoft 네트워크 Edge로의 네트워크 성능 요구 사항
<a name="bkYourNetworkEdge"> </a>

다음은 네트워크 Edge와 Microsoft 네트워크 Edge 간의 연결에 필요한 네트워크 성능 목표 또는 임계값입니다. 네트워크의 이 세그먼트는 고객의 내부 네트워크 또는 WAN을 제외하며, 인터넷 또는 ExpressRoute 파트너 네트워크를 통해 전송되는 네트워크 트래픽을 테스트할 때 지침으로 사용하며 ExpressRoute 공급자와 성능 SLA(서비스 수준 계약)를 협상할 때에도 사용할 수 있습니다.
  
> [!CAUTION]
> **회사 네트워크 Edge와 Microsoft 네트워크 에지 간의 연결은 다음과 같은 네트워크 성능 요구 사항 및 임계값을 충족해야 합니다.**
  
|||
|:-----|:-----|
|**메트릭** <br/> |**대상** <br/> |
|대기 시간(단 방법)  <br/> |< 30ms  <br/> |
|RTT(대기 시간)  <br/> |< 60ms  <br/> |
|패킷 손실 버스트  <br/> |<1%를 200 ms 간격으로 설정  <br/> |
|패킷 손실  <br/> |<15% 동안 0.1%  <br/> |
|패킷 도착 간 지터  <br/> |<15ms 간격 동안 15ms  <br/> |
|패킷 다시 오더  <br/> |<0.01% 순서 비지정 패킷  <br/> |
   
 **기타 성능 목표 요구 사항:**
  
- 성능 목표에 따라 회사의 네트워크 Edge와 가장 가까운 Microsoft 네트워크 Edge 간의 연결이 동일한 대륙에 있습니다.
    
- 네트워크 성능 대상은 적절한 대역폭 및/또는 서비스 계획 품질을 가정합니다. 이는 네트워크 연결이 최대 부하에 Real-Time 경우 비즈니스용 Skype 및 미디어 트래픽에도 적용됩니다. 적절한 대역폭 및 QoS 계획은 비즈니스용 [Skype Online에서 ExpressRoute 및 QoS를 참조하세요.](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)
    
## <a name="measuring-network-performance"></a>네트워크 성능 측정
<a name="bkNetworkPerf"> </a>

특히 대기 시간 및 패킷 손실을 위해 회사 네트워크 사이트에서 네트워크 Edge로의 실제 네트워크 성능을 측정하기 위해 Microsoft Edge 및 데이터 센터 사이트에서 실행되는 비즈니스용 Skype 미디어 릴레이 서비스 집합에 대해 ping, 테스트와 같은 도구를 사용할 수 있습니다. 

>[!NOTE]
> PING(ICMP)을 통해 네트워크 성능을 측정하는 것은 효과적이지 않습니다. 이러한 이유로 아래에서 노출하는 모든 캐스트 IP는 2020년 1월부터 ICMP 요청에 대한 응답을 중지합니다. 네트워크 수행률을 효과적으로 측정하려면 Microsoft에서 네트워크 [Assesment 도구를 사용하는 것이 좋습니다.](https://www.microsoft.com/download/details.aspx?id=53885)
  
Microsoft 네트워크에 대한 인터넷 연결을 테스트하려면 비즈니스용 Skype 미디어 릴레이의 다음 VIP에 대해 테스트하는 것이 좋습니다. *Anycast VIP는* 테스트 위치에 가장 가까운 Microsoft 네트워크 Edge 사이트에서 미디어 릴레이의 IP 주소로 확인됩니다.
  
||||
|:-----|:-----|:-----|
|**IP 주소** <br/> |**유형** <br/> |**위치** <br/> |
|13.107.8.2  <br/> |VIP  <br/> |World Wide Anycast IP  <br/> |
   
 **다음은 네트워크 성능 평가를 위해 따라야 할 몇 가지 높은 수준의 권장 사항입니다.**
  
- Microsoft 365 또는 Office 365에 대한 연결뿐만 아니라 내부 네트워크를 평가해야 합니다.
    
- 오랜 기간 동안 모든 네트워크에 대한 데이터를 평가하고 수집해야 합니다. 업무일 및 시간에 대한 사용 패턴을 볼 수 있도록 최소 1주일 동안 네트워크 성능 테스트를 수행하는 것이 좋습니다. 그러면 최대 사용 시간을 보여 주게 될 것입니다.
    
- 네트워크 성능 측정의 여러 샘플을 취해야 합니다. 데이터를 수집하는 전체 기간 동안 회사 사이트에서 10분마다 측정을 하는 것이 좋습니다. 비즈니스용 Skype Online 네트워크 성능 요구 사항을 비교하기 위해 이 샘플 데이터 집합에서 90번째 백분위수 측정값을 사용하세요. 
    
- 네트워크의 성능을 지속적으로 평가해야 합니다. 네트워크 사용률은 사용 패턴 변경, 많은 양의 대역폭을 사용하는 새로운 엔터프라이즈 기반 애플리케이션 및 조직 또는 실제 회사 위치 변경으로 인해 시간이 지날 때 다릅니다. 이러한 네트워크 성능 요구 사항 및 목표/임계값에 대해 네트워크 성능을 지속적으로 모니터링하고 미디어 품질을 최적화하기 위해 시기 적절한 조정을 Real-Time 중요합니다. 
    
## <a name="measuring-network-performance-using-azure-vms"></a>Azure VM을 사용하여 네트워크 성능 측정
<a name="bkNetworkPerf"> </a>

Microsoft 네트워크 Edge 사이트에 대해 테스트하는 대신 Microsoft Azure 클라우드의 서비스에 대한 테스트 설정을 활용하는 비즈니스용 Skype 고객 및 파트너의 네트워크 평가 솔루션이 있습니다. 이러한 솔루션에서 네트워크 평가 도구는 Azure 클라우드에서 서비스로 설정된 사용자 지정 엔드포인트에 대해 대기 시간, 패킷 손실 및 지터를 테스트합니다. 결과적으로 테스트 네트워크 트래픽은 네트워크 평가 서비스를 호스트하는 네트워크 에지와 Azure 데이터 센터 간의 Microsoft 네트워크 내의 연결인 하나의 추가 네트워크 세그먼트를 통해 이동됩니다.
  
이러한 네트워크 평가 솔루션의 경우 Azure 호스팅 테스트 서비스를 기반으로 합니다. 국가 및/또는 지역 내에서 네트워크 평가를 수행하는 것이 좋습니다. 예를 들어 미국 동부의 고객 사이트의 경우 Azure의 미국 동부 데이터 센터 지역에 호스트된 테스트 서비스 인스턴스에 대해 평가를 수행해야 합니다. 
  
다음은 Azure 서비스 기반 네트워크 평가 설정에 대한 RTT(대기 시간) 대상입니다. 단방 대기 시간 대상은 해당 RTT 대상의 절반이 될 것입니다. 패킷 손실 및 지터 목표는 Skype Media Relay 기반 테스트에 대해 정의된 목표와 동일하게 유지됩니다.
  
|||||
|:-----|:-----|:-----|:-----|
|**고객 지역** <br/> |**Azure 지역** <br/> |**네트워크 Edge - Azure RTT(왕복 시간)** <br/> |**사이트 - Azure RTT(왕복 시간)** <br/> |
|미국 중부  <br/> |미국 중부  <br/> |99  <br/> |139  <br/> |
|미국 동부  <br/> |미국 동부  <br/> |86  <br/> |126  <br/> |
|미국 중북부  <br/> |미국 중북부  <br/> |97  <br/> |137  <br/> |
|미국 중남부  <br/> |미국 중남부  <br/> |94  <br/> |134  <br/> |
|미국 서부  <br/> |미국 서부  <br/> |94  <br/> |134  <br/> |
|미국의 하와이  <br/> |미국 서부  <br/> |116  <br/> |156  <br/> |
|캐나다 중부  <br/> |캐나다 중부  <br/> |138  <br/> |178  <br/> |
|캐나다 동부  <br/> |캐나다 동부  <br/> |131  <br/> |171  <br/> |
|북유럽  <br/> |북유럽  <br/> |99  <br/> |139  <br/> |
|유럽 서부  <br/> |유럽 서부  <br/> |95  <br/> |135  <br/> |
|동아시아  <br/> |동아시아  <br/> |118  <br/> |158  <br/> |
|동남 아시아  <br/> |동남 아시아  <br/> |97  <br/> |137  <br/> |
|일본 동부  <br/> |일본 동부  <br/> |111  <br/> |151  <br/> |
|일본 서부  <br/> |일본 서부  <br/> |118  <br/> |158  <br/> |
|브라질 남부  <br/> |브라질 남부  <br/> |70  <br/> |110  <br/> |
|오스트레일리아 동부  <br/> |오스트레일리아 동부  <br/> |124  <br/> |164  <br/> |
|오스트레일리아 남동부  <br/> |오스트레일리아 남동부  <br/> |124  <br/> |164  <br/> |
|인도 중부  <br/> |인도 중부  <br/> |103  <br/> |143  <br/> |
|인도 남부  <br/> |인도 남부  <br/> |103  <br/> |143  <br/> |
|인도 서부  <br/> |인도 서부  <br/> |103  <br/> |143  <br/> |
|중국 동부  <br/> |중국 동부  <br/> |120  <br/> |160  <br/> |
|중국 북부  <br/> |중국 북부  <br/> |120  <br/> |160  <br/> |
   
## <a name="media-quality-and-expressroute"></a>미디어 품질 및 ExpressRoute
<a name="bkNetworkPerf"> </a>

Microsoft 365 또는 Office 365용 Azure ExpressRoute는 Microsoft 365 또는 Office 365에 연결하기 위한 전용 네트워크 연결입니다. 고객에게 네트워크 트래픽이 걸리는 경로를 제어할 수 있는 기능을 제공합니다. 알 수 없는 통신 사업자, 공급자 및 ISP가 데이터를 전송하는 인터넷에서 발생하는 예측할 수 없는 라우팅에 더 이상 염려할 수 없습니다. ExpressRoute를 통해 전송된 네트워크 트래픽은 ExpressRoute 파트너의 네트워크를 통해 Microsoft 네트워크로 직접 전송됩니다. 이렇게 하면 고객이 전용 연결을 사용하여 Microsoft 365 또는 Office 365를 자체 오프사이트 데이터 센터에 있는 것으로 취급할 수 있습니다.
  
Azure ExpressRoute는 모든 Microsoft 365 및 Office 365 라이선스 제품에서 사용할 수 있습니다. 그러나 전역 라우팅을 사용하려면 Microsoft 365 및 Office 365에 Azure ExpressRoute 프리미엄 추가 기능만 필요합니다. ExpressRoute를 구현하는 사용자 수가 500명 이상인 고객은 추가 비용 부담이 없는 필수 *ExpressRoute 프리미엄* 추가 기능을 얻을 수 있습니다.
  
### <a name="is-expressroute-required-for-good-media-quality"></a>좋은 미디어 품질에 ExpressRoute가 필요한가요?

Azure ExpressRoute는 비즈니스용 Skype Online 미디어 품질을 가장 최적화하기 위한 요구 사항이 아닙니다. 그러나 클라우드 연결이 비즈니스용 Skype 네트워크 성능 목표 또는 임계값을 충족하는지 확인 하는 데 도움이 되는 배포 옵션 중 하나입니다.
  
Microsoft 365 및 Office 365는 인터넷을 사용하는 고성능 및 보안 서비스입니다. 보안 및 성능을 지속적으로 개선하기 위해 새로운 보안 기능 및 지역 에지 노드에 계속 투자하고 있습니다. Azure ExpressRoute는 비즈니스용 Skype Online을 포함한 Microsoft 365 또는 Office 365 서비스에 대한 요구 사항이 아닙니다. Azure ExpressRoute는 Microsoft 365 또는 Office 365에 대한 연결이 비즈니스용 Skype 네트워크 성능 요구 사항을 충족하고 최적의 비즈니스용 Skype Online 미디어 품질 환경을 보장하는 데 도움이 되는 배포 옵션 중 하나입니다.
  
비즈니스용 Skype Online 미디어 품질의 경우 회사 사이트와 Microsoft 네트워크 에지 간의 연결이 비즈니스용 Skype 클라이언트에서 Microsoft Network [Edge로의](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge) 네트워크 성능 요구 사항의 성능 목표를 충족하고 네트워크 에지와 Microsoft 네트워크 에지 간의 연결이 네트워크 [Edge에서 Microsoft](media-quality-and-network-connectivity-performance.md#bkYourNetworkEdge)네트워크 Edge로의 네트워크 성능 요구 사항의 성능 목표를 충족하는 것이 중요합니다.  
  
내부 네트워크 및 클라우드 연결 용량을 포함하여 회사의 물리적 네트워크 연결도 최대 미디어 트래픽 볼륨을 수용하는 것이 중요합니다. Azure ExpressRoute는 고객이 비즈니스용 Skype Online 클라우드 연결이 이러한 모든 성능 요구 사항을 충족하도록 하는 데 도움이 되는 여러 가지 방법 중 하나입니다.
  
### <a name="is-expressroute-required-for-voice-quality-sla"></a>음성 품질 SLA에 ExpressRoute가 필요합니까?

아니요, ExpressRoute는 비즈니스용 Skype Online 음성 품질 SLA에 필요하지 않습니다. [비즈니스용 Skype Online 음성](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37) 품질 SLA는 사용자가 모든 유형의 VoIP 또는 PSTN 통화를 걸 수 있도록 하는 올바른 라이선스 및 구독 내에서 비즈니스용 Skype Online 음성 서비스 사용자가 발신한 적격 통화에 적용됩니다. 음성 품질 SLA에는 다음 조건을 모두 해결해야 합니다.
  
- Microsoft 인증 IP 전화기에서 호출합니다.
    
- 유선 이더넷 연결.
    
- Microsoft 네트워크 문제로 인한 음성 품질 문제.
    
> [!NOTE]
> 음성 품질 SLA는 ExpressRoute 파트너 및 기타 네트워크를 포함한 Microsoft 외 네트워크의 문제로 인해 통화 품질이 낮은 호출을 제외합니다. 
  
### <a name="internet-or-azure-expressroute"></a>인터넷 또는 Azure ExpressRoute?

비즈니스용 Skype Online에 대한 네트워크 연결 옵션을 결정하기 전에 고객은 비즈니스용 [Skype Online에](media-quality-and-network-connectivity-performance.md#bkNetworkPerf)연결하기 위한 네트워크 성능 요구 사항에 설명된 네트워크 성능 요구 사항에 따라 네트워크 및 현재 인터넷 연결을 평가해야 합니다.
  
현재 인터넷 연결에 대한 네트워크 성능이 최대 사용 시간 동안 충분한 용량으로 설정되고 사이트와 Microsoft 네트워크 에지, 네트워크 에지에서 Microsoft 네트워크 에지로의 네트워크 성능 요구 사항을 충족하는 경우 기존 인터넷 연결을 계속 사용하여 비즈니스용 Skype Online에 연결할 수 있습니다.
  
네트워크 성능 요구 사항이 충족되지 않는 회사 사이트의 경우 먼저 기존 네트워크 서비스 공급자와 함께 전체 네트워크 성능을 개선하는 것이 좋습니다. 그러나 여전히 충족되지 않는 경우 Azure ExpressRoute를 사용하면 비즈니스용 Skype Online 클라우드 연결이 네트워크 성능 요구 사항을 충족하는 데 도움이 될 수 있습니다.
  
Azure ExpressRoute는 다음과 같은 추가 이점을 제공합니다.
  
- 네트워크와 Microsoft 네트워크 간의 연결 가용성에 대한 SLA(서비스 수준 계약)입니다. ExpressRoute에는 99.9%의 보장된 가용성 SLA가 있습니다.
    
- Microsoft 365 및 Office 365 서비스에 필요한 계획된 보장 대역폭입니다. ExpressRoute를 사용하여 Microsoft 365, Office 365 또는 비즈니스용 Skype 트래픽만 보내면 다른 모든 인터넷 트래픽이 네트워크의 다른 인터넷 송/수신 지점을 통과하도록 할 수 있습니다.
    
- ExpressRoute는 네트워크와 Microsoft 네트워크 간에 DSCP QoS 표시를 유지하도록 디자인되어 있습니다.
    
ExpressRoute QoS 및 용량 계획에 대한 자세한 내용은 비즈니스용 [Skype Online에서 ExpressRoute 및 QoS를 참조하세요.](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)
  
### <a name="can-i-setup-azure-expressroute-for-skype-for-business-online-only"></a>비즈니스용 Skype Online용 Azure ExpressRoute만 설정하면 하나요?

예, 회사 네트워크에서 비즈니스용 Skype Online으로의 뛰어난 네트워크 연결을 보장하도록 Azure ExpressRoute를 설정할 수 있습니다. 이렇게 하면 사용자에게 가장 Real-Time 미디어 품질을 제공하지만 인터넷을 통해 다른 Microsoft 365 또는 Office 365 서비스에 계속 연결할 수 있습니다.
  
BGP(Border Gateway Protocol)는 인터넷을 통해 네트워크 트래픽을 라우팅하는 데 사용되는 인터넷의 라우팅 프로토콜입니다. 인터넷을 통해 찾은 AS(자치 시스템) 간에 라우팅 정보를 교환하도록 디자인되었습니다. BGP 커뮤니티 값은 들어오거나 받는 경로에 적용할 수 있는 특성 태그입니다. BGP 커뮤니티는 종종 지리, 서비스 유형 또는 기타 조건에 따라 주어진 대상에 도달하는 데 사용할 아웃바운드 링크를 수신 AS에 신호하는 데 사용됩니다.
  
BGP 커뮤니티 지원을 통해 Microsoft는 해당 커뮤니티가 속한 서비스를 기반으로 적절한 BGP 커뮤니티 값으로 태그를 지정합니다. Microsoft는 공용 피어링 및 Microsoft 피어링을 통해 보급된 태그를 해당 BGP 커뮤니티 값으로 태그 지정합니다. 최적의 라우팅을 제공하는 적절한 라우팅 결정을 내리기 위해 커뮤니티 값을 사용할 수 있습니다. 비즈니스용 Skype Online BGP 커뮤니티 값을 사용하여 비즈니스용 Skype Online에 대한 ExpressRoute 연결을 설정하는 데 사용할 수 있습니다. ExpressRoute 라우팅 요구 사항에서 자세한 [정보를 찾을 수 있습니다.](https://azure.microsoft.com/documentation/articles/expressroute-routing/)
  
## <a name="expressroute-connectivity-scenarios-for-skype-for-business-online"></a>비즈니스용 Skype Online용 ExpressRoute 연결 시나리오
<a name="bkNetworkPerf"> </a>

위의 권장 사항에 따라 ExpressRoute를 결정한 경우 다음 권장 사항에서 얻을 ExpressRoute 연결의 위치 및 수에 대한 권장 사항이 있습니다.
  
### <a name="online-only-deployment---single-site"></a>온라인 전용 배포 - 단일 사이트

모든 사용자가 비즈니스용 Skype Online 서비스를 사용하고 사무실이 단일 물리적 위치를 중심으로 하는 경우 Azure ExpressRoute를 배포하기로 결정한 경우 회사 사이트 간에 가장 가까운 ExpressRoute 피어링 위치에 단일 [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-locations/)연결을 설정해야 합니다.
  
다음 그래픽은 이러한 유형의 배포의 예를 보여줍니다. 이 예제에서 Contoso는 FL 올랜도에 있는 대학입니다. Contoso에는 10,000명 이상의 교직원과 학생이 있습니다. 해당 위치에서 Microsoft Edge 사이트로의 인터넷 테스트는 최고 클래스 시간 동안 패킷 손실이 5% 이상으로 나타났습니다. Microsoft 365 또는 Office 365에 대해 과도하게 프로비전된 대역폭으로 ExpressRoute를 사용하여 Microsoft 365 또는 Office 365에 대한 전용 연결을 설정하여 특히 비즈니스용 Skype Online Real-Time 트래픽에 대한 네트워크 정체가 방지될 수 있도록 하기로 결정했습니다. Atlanta, GA MeetMe 사이트에서 ExpressRoute를 통해 Microsoft 클라우드에 연결합니다.
  
![ExpressRoute 단일 사이트.](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### <a name="online-only-deployment---multiple-sites-on-the-same-continent"></a>온라인 전용 배포 - 동일한 대륙의 여러 사이트

회사에서 동일한 지역 또는 대륙의 여러 사무실에서 비즈니스용 Skype Online 서비스를 사용하고 Azure ExpressRoute를 구현하기로 선택한 경우 ExpressRoute를 통해 기본 사이트를 연결한 다음, 선택적으로 권장되는 네트워크 성능 목표를 충족하지 않는 다른 위치에 대해 ExpressRoute 피어링을 추가하는 것이 좋습니다.
  
다음 예제에서 Contoso는 뉴욕에 본사가 있지만 미국 전역에 다른 사무실이 있는 미국 여행 서비스 회사입니다. 사무실은 Microsoft 365 또는 Office 365에 연결하는 데 MPLS를 사용하는 WAN을 통해 상호 연결됩니다. 처음에는 뉴저지 주 호보크의 인터넷 라우터에서 뉴욕 MeetMe 사이트로 ExpressRoute 연결을 설정했습니다. 
  
이 설정을 통해 대부분의 사이트에서 Microsoft Network(뉴욕 에지 사이트)로의 네트워크 트래픽은 비즈니스용 Skype 클라이언트에서 Microsoft Network Edge로의 네트워크 성능 요구 사항에 설명된 비즈니스용 Skype 클라이언트 연결 네트워크 성능 목표를 충족할 수 [있습니다.](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge) 그러나 Contoso의 서부 연안 사무실에서 뉴욕으로의 대기 시간이 50ms를 넘습니다. 또한 Honolulu는 Contoso에서 두 번째로 큰 사무실로, Honolulu에서 뉴욕으로의 대기 시간이 단방 80ms를 초과합니다. Contoso는 해당 사무실의 사용자에게 적절한 미디어 품질을 보장하기 위해 San Jose 사이트와 실리콘밸리 ExpressRoute MeetMe 사이트 간에 서부 해안 ExpressRoute 연결을 추가하기로 결정했습니다.
  
![동일한 대륙의 Express 라우터 다중 사이트.](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### <a name="online-only-deployment---multiple-sites-on-different-continents"></a>온라인 전용 배포 - 다른 대륙의 여러 사이트

모든 사용자가 비즈니스용 Skype Online 서비스를 사용하고 있으며 사무실이 여러 대륙의 여러 물리적 위치에 있는 경우 Azure ExpressRoute를 배포하기로 결정한 경우 각 대륙의 기본 사이트 간에 가장 가까운 ExpressRoute 피어링 위치에 대해 각 대륙에 대해 하나 이상의 [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-locations/)연결을 설정해야 합니다. 비용 및 혜택에 따라 네트워크 성능 목표가 충족되지 않는 사이트에서 추가 ExpressRoute 연결을 배포할 수 있습니다.
  
다음 예제에서 Contoso는 북아메리카 및 유럽의 주요 도시에 사무실을 두는 대기업 법률 회사입니다. Contoso는 인터넷 연결 및 내부 네트워크 성능 평가에 따라 북아메리카에 두 개의 ExpressRoute 연결과 모든 유럽 지사에 대해 단일 ExpressRoute 회로를 배포하기로 결정했습니다.
  
![여러 사이트 및 대륙이 있는 ExpressRoute](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### <a name="hybrid-deployment"></a>하이브리드 배포

온-프레미스 Lync 또는 비즈니스용 Skype 배포가 있으며 하이브리드 비즈니스용 Skype Online 통합을 구현하기로 선택한 경우 Azure ExpressRoute를 배포하기로 결정한 경우 각 온-프레미스 Lync 또는 비즈니스용 Skype Edge 사이트에 대해 하나 이상의 ExpressRoute 연결과 사무실과 각 대륙에 대해 하나 이상의 ExpressRoute 연결이 있는 것이 좋습니다. 비용 및 혜택에 따라 각 대륙에 대해 네트워크 성능 목표가 충족되지 않는 사무실에서 추가 ExpressRoute 연결을 배포할 수 있습니다.
  
비즈니스용 Skype를 배포하는 경우 Edge Server 계획 및 배포 가이드를 [따라야 합니다.](https://technet.microsoft.com/library/mt346417.aspx) 특히 Edge 서버는 네트워크 외부에서 연결 가능해야 합니다. 이는 일반적으로 라우팅 가능한 공용 IP 주소를 Edge 서버에 할당하거나 NAT(네트워크 주소 변환)를 사용하여 달성됩니다.
  
다음 예제에서 Contoso에는 기존 비즈니스용 Skype Enterprise Voice 있습니다. 이 사용자는 Microsoft 365 또는 Office 365 온라인 서비스로 온라인 사용자를 마이그레이션할 수 있습니다. 또한 모든온-프레미스 및 온라인 사용자에 대해 기존 PSTN 인프라를 계속 사용할 수 있도록 하이브리드 배포를 사용하기로 결정했습니다. Contoso의 클라우드 데이터 센터와 비즈니스용 Skype Edge Server는 시카고에 있습니다. 배포를 위해 Contoso는 시카고 데이터 센터와 시카고 ExpressRoute 간에 하나의 ExpressRoute 연결을 설정하기로 결정했습니다. 또한 서부 해안 ExpressRoute 연결을 추가하여 Honolulu 사무실을 더 잘 제공합니다.
  
![ExpressRoute 하이브리드.](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### <a name="online-deployment-with-cloud-connector-edition"></a>Cloud Connector Edition을 사용하여 온라인 배포

비즈니스용 Skype Online Cloud Connector Edition은 패키지된 VM(Virtual Machines) 집합으로 구성되는 하이브리드 제품으로, 이 집합은 온라인 PSTN 연결을 구현합니다. 가상화된 환경에서 최소한의 비즈니스용 Skype Server 토폴로지 배포를 통해 기존 PSTN 음성 인프라를 통해 유선전화 및 휴대폰으로 통화를 보내고 받을 수 있습니다.
  
Azure ExpressRoute 및 Cloud Connector Edition을 배포하기로 결정한 경우 가장 가까운 [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-locations/)피어링 위치에 각 대륙 간의 각 대륙에 대해 하나 이상의 Express Route 연결을 설정하는 것이 좋습니다. 비용 및 혜택에 따라 각 대륙에 대해 네트워크 성능 목표가 충족되지 않는 사이트에서 추가 ExpressRoute 연결을 배포할 수 있습니다.
  
비즈니스용 Skype를 배포하는 경우 비즈니스용 Skype Cloud Connector Edition에 대한 계획 [가이드를 따라야 합니다.](https://technet.microsoft.com/library/mt605227.aspx) 특히 Access Edge 및 A/V Edge 서비스에는 공용 IP 주소가 할당되어 있으며 Microsoft 365 또는 Office 365 데이터 센터에 연결 가능해야 합니다.
  
다음 예제에서 Contoso는 몇 가지 주요 유럽 국가 및 도시에 있는 유럽 회계 회사입니다. 모든 공동 작업 요구에 따라 비즈니스용 Skype Online에 등록할 때 이미 존재하는 PSTN 인프라 및 통신 사업자 계약을 계속 사용할 수 있는 물리적 위치가 있는 각 국가에 대한 클라우드 커넥터를 설정하기로 결정했습니다. 모든 사이트와 Microsoft 네트워크 Edge의 테스트에 따라 런던의 단일 ExpressRoute 연결이 비즈니스용 Skype 클라이언트에서 Microsoft Network Edge로의 네트워크 성능 요구 사항에 설명된 비즈니스용 Skype 클라이언트 연결 네트워크 성능 목표를 충족하는 데 도움이 된다고 [결정했습니다.](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)
  
![ExpressRoute 클라우드 커넥터 1.](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
다음은 Contoso에 대한 또 다른 배포 옵션입니다. 이 경우 클라우드 커넥터가 배포된 각 사이트에서 ExpressRoute 연결을 설정하기로 결정했습니다. 
  
![ExpressRoute Cloud Connector 2.](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## <a name="related-topics"></a>관련 항목

[비즈니스용 Skype Online의 ExpressRoute 및 QoS](expressroute-and-qos-in-skype-for-business-online.md)

  
 
