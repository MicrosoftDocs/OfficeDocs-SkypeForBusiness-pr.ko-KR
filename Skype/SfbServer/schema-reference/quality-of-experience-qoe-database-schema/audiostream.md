---
title: AudioStream 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
description: 각 레코드는 하나의 오디오 스트림을 나타냅니다. 일반적으로 하나의 오디오 미디어 선에는 두 개의 오디오 스트림이 있습니다.
ms.openlocfilehash: 265125202de25da4c6e653ecd53bd465f9a5472b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810436"
---
# <a name="audiostream-table"></a>AudioStream 테이블
 
각 레코드는 하나의 오디오 스트림을 나타냅니다. 일반적으로 하나의 오디오 미디어 선에는 두 개의 오디오 스트림이 있습니다.
  
|열|데이터 형식|키/인덱스|세부적인|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |dmtf  <br/> |주요한  <br/> |[Medialine 테이블](medialine-0.md)에서 참조 합니다.  <br/> |
|**SessionSeq** <br/> |int  <br/> |주요한  <br/> |[Medialine 테이블](medialine-0.md)에서 참조 합니다.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |주요한  <br/> |[Medialine 테이블](medialine-0.md)에서 참조 합니다.  <br/> |
|**StreamID** <br/> |int  <br/> |주요한  <br/> |미디어 라인 내의 고유 ID.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |RTCP (실시간 제어 프로토콜) 통계의 평균 네트워크 지터입니다.  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |통화 중 최대 네트워크 지터.  <br/> |
|**PacketLossRate** <br/> |10 진수 (5, 4)  <br/> | <br/> |통화 중의 평균 패킷 손실 율입니다.  <br/> |
|**PacketLossRateMax** <br/> |10 진수 (5, 4)  <br/> | <br/> |통화 중에 최대 패킷 손실이 관찰 되었습니다.  <br/> |
|**BurstDensity** <br/> |10 진수 (9, 4)  <br/> | <br/> |통화 중에 손실이 발생 한 경우 패킷 손실의 평균 밀도입니다.  <br/> |
|**BurstDuration** <br/> |int  <br/> | <br/> |통화 중에 손실 되는 패킷 손실의 평균 지속 시간입니다.  <br/> |
|**BurstGapDensity** <br/> |10 진수 (9, 4)  <br/> | <br/> |패킷 손실의 버스트 간에 간격을 두는 경우 패킷 손실의 평균 밀도.  <br/> |
|**BurstGapDuration** <br/> |int  <br/> | <br/> |패킷 손실의 버스트 간 평균 간격 기간입니다.  <br/> |
|**PacketUtilization** <br/> |Int  <br/> | <br/> |오디오 스트림의 패킷 수입니다.  <br/> |
|**BandwidthEst** <br/> |Int  <br/> | <br/> |오디오 스트림의 대역폭을 예측 합니다.  <br/> |
|**DegradationAvg** <br/> |10 진수 (3, 2)  <br/> | <br/> |전체 통화에 대 한 네트워크 SPECIALIST 성능이 저하 됩니다. 범위는 0.0 ~ 5.0입니다. 이 메트릭은 지터 및 패킷 손실로 인해 네트워크 SPECIALIST 감소 된 양을 표시 합니다. 허용 되는 품질은 0.5 미만 이어야 합니다.  <br/> |
|**DegradationMax** <br/> |10 진수 (3, 2)  <br/> | <br/> |통화 중에 최대 네트워크 SPECIALIST 저하 됩니다.  <br/> |
|**DegradationJitterAvg** <br/> |10 진수 (3, 2)  <br/> | <br/> |지터로 인해 네트워크 SPECIALIST 저하 됩니다.  <br/> |
|**DegradationPacketLossAvg** <br/> |10 진수 (3, 2)  <br/> | <br/> |패킷 손실로 인해 네트워크 SPECIALIST 저하 됩니다.  <br/> |
|**AudioPayloadDescription** <br/> |int  <br/> |외부  <br/> |PayloadDescription 테이블에서 참조 되는 통화에 사용 되는 오디오 코덱입니다.  <br/> |
|**AudioSampleRate** <br/> |int  <br/> | <br/> |오디오 스트림의 샘플링 속도입니다.  <br/> |
|**왕복이** <br/> |int  <br/> | <br/> |RTCP 통계에서 왕복 시간을 계산 합니다. 적절 한 품질을 위해서는 100ms 보다 작아야 합니다.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |오디오 스트림의 최대 라운드트립 시간입니다.  <br/> |
|**OverallAvgNetworkMOS** <br/> |10 진수 (3, 2)  <br/> | <br/> |통화에 대 한 평균 광대역 네트워크 SPECIALIST. 이 메트릭은 사용 되는 패킷 손실, 지터 및 코덱에 따라 달라 집니다. 범위는 [1.0에서 5.0]입니다.  <br/> |
|**OverallMinNetworkMOS** <br/> |10 진수 (3, 2)  <br/> | <br/> |통화에 대 한 최소 광대역 네트워크 SPECIALIST.  <br/> |
|**SendListenMOS** <br/> |10 진수 (3, 2)  <br/> | <br/> |음성 수준, 노이즈 수준 및 캡처 장치 특성을 포함 하 여 발송 된 오디오에 대 한 평균 예측 광대역 SPECIALIST 점수입니다.  <br/> |
|**SendListenMOSMin** <br/> |10 진수 (3, 2)  <br/> | <br/> |통화에 대 한 최소 SendListenMOS입니다.  <br/> |
|**RecvListenMOS** <br/> |10 진수 (3, 2)  <br/> | <br/> |음성 수준, 소음 수준, 코덱, 네트워크 상태 및 캡처 장치 특성을 포함 하 여 네트워크에서 받은 오디오에 대 한 평균 예측 광대역 SPECIALIST 점수입니다.  <br/> |
|**RecvListenMOSMin** <br/> |10 진수 (3, 2)  <br/> | <br/> |통화에 대 한 최소 RecvListenMOS입니다.  <br/> |
|**오디오 및 사용** <br/> |다소  <br/> ||오디오 FEC 통화에 사용 되었는지 여부를 나타내는 플래그입니다.  <br/> |
|**RatioConcealedSamplesAvg** <br/> |10 진수 (5, 2)  <br/> ||오디오 치유에서 생성 한 숨겨진 샘플의 평균 비율을 일반적인 샘플입니다.  <br/> |
|**RatioStretchedSamplesAvg** <br/> |10 진수 (5, 2)  <br/> ||표준 샘플에 대 한 오디오 치유에서 생성 된 늘이기 샘플의 평균 비율입니다.  <br/> |
|**RatioCompressedSamplesAvg** <br/> |10 진수 (5, 2)  <br/> ||오디오 치유에서 생성 한 압축 샘플의 평균 비율을 일반적인 샘플로 나타낸 것입니다.  <br/> |
|**Ipsec** <br/> |다소  <br/> | <br/> |수신기 쪽에 있는 스트림 데이터를 수신 합니다.  <br/> |
|**위한** <br/> |다소  <br/> | <br/> |보낸 사람 측에 있는 스트림 데이터를 수신 했습니다.  <br/> |
|**SenderIsCallerPAI** <br/> |다소  <br/> | <br/> |1은 스트림 방향이 호출자에서 호출 수신자 까지의 것임을 의미 합니다.  <br/> 0은 스트림 방향이 피호출자부터 호출자에 게 있음을 의미 합니다.  <br/> |
|**JitterInterArrivalSD** <br/> |o  <br/> ||지터 도착 시간에 대 한 표준 편차입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**ConcealRatioMax** <br/> |o  <br/> ||Healer에서 숨겨진 패킷의 최대 비율입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**ConcealRatioSD** <br/> |o  <br/> ||Healer에서 숨겨진 패킷의 비율에 대 한 표준 편차입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**HealerPacketDropRatio** <br/> |o  <br/> ||Healer에서 손실 된 패킷의 총 수를 수신 하 여 받은 패킷의 총량을 말합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**HealerFECPacketUsedRatio** <br/> |o  <br/> ||받은 총 패킷 수와 비교 하 여 사용한 착신 전환 오류 수정 패킷의 비율입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**MaxCompressedSamples** <br/> |o  <br/> ||Healer에서 압축 한 최대 오디오 패킷 수입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**LossCongestionPercent** <br/> |o  <br/> ||통화가 손실 혼잡 상태에 있는 시간의 백분율을 나타냅니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**DelayCongestionPercent** <br/> |o  <br/> ||네트워크 패킷의 지연 도착으로 인해 혼잡이 있는 통화의 백분율을 나타냅니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**ContentionDetectedPercent** <br/> |o  <br/> ||통화가 네트워크 리소스에 대해 경쟁 하는 시간의 백분율을 나타냅니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||통화 중 측정 되는 최소 대역폭 예상 양입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||통화 중에 측정 되는 최대 대역폭 예상 금액입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||통화 중에 측정 되는 대역폭 예상의 표준 편차입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||통화 중 측정 되는 평균 대역폭 예상 금액입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RelativeOneWayTotal** <br/> |o  <br/> ||단방향 총 대기 시간입니다. 상대적 단방향 대기 시간은 클라이언트와 서버 간의 지연을 측정 합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RelativeOneWayAverage** <br/> |o  <br/> ||평균 단방향 대기 시간입니다. 상대적 단방향 대기 시간은 클라이언트와 서버 간의 지연을 측정 합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RelativeOneWayMax** <br/> |o  <br/> ||단방향 대기 시간의 최대 양입니다. 상대적 단방향 대기 시간은 클라이언트와 서버 간의 지연을 측정 합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||전체 단방향 버스트 횟수입니다. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |o  <br/> ||전체 단방향 버스트 밀도. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |o  <br/> ||전체 단방향 버스트 기간입니다. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||전체 단방향 간격이 발생 합니다. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 간격은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RelativeOneWayGapDensity** <br/> |o  <br/> ||전체 단방향 간격 밀도. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 간격은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RelativeOneWayGapDuration** <br/> |o  <br/> ||전체 단방향 간격 기간입니다. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 간격은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**DecodeStereoPercent** <br/> |o  <br/> ||스테레오로 디코딩된 통화의 백분율입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**AecRenderStereoPercent** <br/> |o  <br/> ||음향 반향 제거 기 스테레오로 렌더링 되는 통화의 백분율입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**오디오 및이 어//또는 r** <br/> |o  <br/> ||전달 오류 수정 후 패킷 손실 율이 적용 되었습니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**EncodeStereoPercent** <br/> |o  <br/> ||스테레오로 인코딩된 통화의 백분율입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**AecCaptureStereoPercent** <br/> |o  <br/> ||음향 반향 제거 기 스테레오로 캡처한 통화의 백분율입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
