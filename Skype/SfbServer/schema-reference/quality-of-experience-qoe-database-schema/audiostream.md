---
title: AudioStream 테이블
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
description: 각 레코드는 하나의 오디오 스트림을 표현합니다. 하나의 오디오 미디어 줄에는 일반적으로 두 개의 오디오 스트림이 포함되어 있습니다.
ms.openlocfilehash: b9a5e184a258115934d3583e4f6cde8f659fb9fe
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856425"
---
# <a name="audiostream-table"></a>AudioStream 테이블
 
각 레코드는 하나의 오디오 스트림을 표현합니다. 하나의 오디오 미디어 줄에는 일반적으로 두 개의 오디오 스트림이 포함되어 있습니다.
  
|열|데이터 형식|키/인덱스|세부 정보|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |[MediaLine 테이블에서 참조됩니다.](medialine-0.md)  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |[MediaLine 테이블에서 참조됩니다.](medialine-0.md)  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |[MediaLine 테이블에서 참조됩니다.](medialine-0.md)  <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |미디어 회선 내의 고유 ID입니다.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |RTCP(Real Time Control Protocol) 통계로부터 가져온 평균 네트워크 지터입니다.  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |통화 중 최대 네트워크 지터입니다.  <br/> |
|**PacketLossRate** <br/> |decimal(5,4)  <br/> | <br/> |통화 중 평균 패킷 손실 비율입니다.  <br/> |
|**PacketLossRateMax** <br/> |decimal(5,4)  <br/> | <br/> |통화 중 관측된 최대 패킷 손실입니다.  <br/> |
|**BurstDensity** <br/> |decimal(9,4)  <br/> | <br/> |통화 중 손실 버스트 동안의 평균 패킷 손실 밀도입니다.  <br/> |
|**BurstDuration** <br/> |int  <br/> | <br/> |통화 중 손실량이 많아지는 기간 동안의 평균 패킷 손실 기간입니다.  <br/> |
|**BurstGapDensity** <br/> |decimal(9,4)  <br/> | <br/> |패킷 손실이 최고치인 기간 사이의 간격 중에 발생하는 평균 패킷 손실 밀도입니다.  <br/> |
|**BurstGapDuration** <br/> |int  <br/> | <br/> |패킷 손실이 최고치인 기간 사이의 간격에 대한 평균 기간입니다.  <br/> |
|**PacketUtilization** <br/> |임계값  <br/> | <br/> |오디오 스트림에 대한 패킷 수입니다.  <br/> |
|**BandwidthEst** <br/> |임계값  <br/> | <br/> |오디오 스트림에 대한 대역폭 예상치입니다.  <br/> |
|**DegradationAvg** <br/> |decimal(3,2)  <br/> | <br/> |전체 통화에 대한 네트워크 MOS 저하입니다. 범위는 0.0에서 5.0까지입니다. 이 메트릭은 지터 및 패킷 손실로 인해 감소된 네트워크 MOS의 양을 보여 줍니다. 적정 품질을 위해서는 0.5 미만이어야 합니다.  <br/> |
|**DegradationMax** <br/> |decimal(3,2)  <br/> | <br/> |통화 중 최대 네트워크 MOS 저하입니다.  <br/> |
|**DegradationJitterAvg** <br/> |decimal(3,2)  <br/> | <br/> |지터로 인해 발생한 네트워크 MOS 저하입니다.  <br/> |
|**DegradationPacketLossAvg** <br/> |decimal(3,2)  <br/> | <br/> |패킷 손실로 인해 발생한 네트워크 MOS 저하입니다.  <br/> |
|**AudioPayloadDescription** <br/> |int  <br/> |외계인  <br/> |PayloadDescription Table에서 참조되는 통화에 사용되는 오디오 코덱입니다.  <br/> |
|**AudioSampleRate** <br/> |int  <br/> | <br/> |오디오 스트림에 대한 샘플링 속도입니다.  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |RTCP 통계로부터의 왕복 시간입니다. 적정 품질을 위해 이 수준은 100ms 미만입니다.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |오디오 스트림에 대한 최대 왕복 시간입니다.  <br/> |
|**OverallAvgNetworkMOS** <br/> |decimal(3,2)  <br/> | <br/> |통화에 대한 평균 광대역 네트워크 MOS입니다. 이 메트릭은 패킷 손실, 지터 및 사용된 코덱에 따라 달라집니다. 범위는 [1.0 ~ 5.0]입니다.  <br/> |
|**OverallMinNetworkMOS** <br/> |decimal(3,2)  <br/> | <br/> |통화에 대한 최소 광대역 네트워크 MOS입니다.  <br/> |
|**SendListenMOS** <br/> |decimal(3,2)  <br/> | <br/> |음성 수준, 노이즈 수준 및 캡처 장치 특성을 포함하여 전송된 오디오에 대한 평균 예측된 광대역 수신 MOS 점수입니다.  <br/> |
|**SendListenMOSMin** <br/> |decimal(3,2)  <br/> | <br/> |통화에 대한 최소 SendListenMOS입니다.  <br/> |
|**RecvListenMOS** <br/> |decimal(3,2)  <br/> | <br/> |음성 수준, 노이즈 수준, 코덱, 네트워크 조건 및 캡처 장치 특성을 포함하여 네트워크에서 수신한 오디오에 대한 평균 예측된 광대역 수신 MOS 점수입니다.  <br/> |
|**RecvListenMOSMin** <br/> |decimal(3,2)  <br/> | <br/> |통화에 대한 최소 RecvListenMOS입니다.  <br/> |
|**AudioFECUsed** <br/> |bit  <br/> ||통화에 오디오 FEC가 사용 되었음을 나타내는 플래그입니다.  <br/> |
|**RatioConcealedSamplesAvg** <br/> |decimal(5,2)  <br/> ||일반 샘플에 대한 오디오 힐링으로 생성된 숨겨진 평균 샘플 비율입니다.  <br/> |
|**RatioStretchedSamplesAvg** <br/> |decimal(5,2)  <br/> ||일반 샘플에 대한 오디오 힐링으로 생성된 평균 늘임 샘플 비율입니다.  <br/> |
|**RatioCompressedSamplesAvg** <br/> |decimal(5,2)  <br/> ||일반 샘플에 대한 오디오 힐링으로 생성된 숨겨진 압축 샘플 비율입니다.  <br/> |
|**인바운드** <br/> |bit  <br/> | <br/> |수신자 쪽 스트림 데이터가 수신됩니다.  <br/> |
|**아웃바운드** <br/> |bit  <br/> | <br/> |보낸 사람 쪽 스트림 데이터를 수신합니다.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1은 스트림 방향이 발신자에서 발신자까지입니다.  <br/> 0은 스트림 방향이 수신자에서 발신자의 방향임을 의미합니다.  <br/> |
|**JitterInterArrivalSD** <br/> |float  <br/> ||지터 도착 시간의 표준 편차입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**ConcealRatioMax** <br/> |float  <br/> ||처리기에서 은(는)  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**ConcealRatioSD** <br/> |float  <br/> ||처리기에서 은(는)  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**HealerPacketDropRatio** <br/> |float  <br/> ||수신된 총 패킷 수와 비교할 때, 처리기에서 삭제한 패킷 비율입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**HealerFECPacketUsedRatio** <br/> |float  <br/> ||수신된 총 패킷 수와 비교한 사용된 전방 오류 수정 패킷의 비율입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**MaxCompressedSamples** <br/> |float  <br/> ||Healer에 의해 압축된 최대 오디오 패킷 수입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||통화가 정체 상태인 시간의 백분율을 나타냅니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||지연된 네트워크 패킷 도착으로 인해 정체가 발생한 통화 비율을 나타냅니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||통화가 네트워크 리소스에 경쟁한 시간의 백분율을 나타냅니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||통화 중에 측정된 최소 대역폭 예상 양입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||통화 중에 측정된 최대 대역폭 예상 양입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||통화 중에 측정된 대역폭 예상 표준 편차입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||통화 중 측정된 평균 대역폭 예상 양입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||총 단방향 대기 시간입니다. 상대 단방향 대기 시간이 클라이언트와 서버 간의 지연을 측정합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||평균 단방향 대기 시간입니다. 상대 단방향 대기 시간이 클라이언트와 서버 간의 지연을 측정합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||최대 단방향 대기 시간입니다. 상대 단방향 대기 시간이 클라이언트와 서버 간의 지연을 측정합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||총 단방향 버스트 발생 수입니다. "버스트" 전송은 데이터가 불안정한 스트림이 아니라 예측 불가능한 버스트로 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||총 단방향 버스트 밀도입니다. "버스트" 전송은 데이터가 불안정한 스트림이 아니라 예측 불가능한 버스트로 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||총 단방향 버스트 기간입니다. "버스트" 전송은 데이터가 불안정한 스트림이 아니라 예측 불가능한 버스트로 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||총 단도 갭 발생 수입니다. "버스트" 전송은 데이터가 불안정한 스트림이 아니라 예측 불가능한 버스트로 흐르는 전송입니다. 간격은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||총 단도 갭 밀도입니다. "버스트" 전송은 데이터가 불안정한 스트림이 아니라 예측 불가능한 버스트로 흐르는 전송입니다. 간격은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||총 단도 갭 기간입니다. "버스트" 전송은 데이터가 불안정한 스트림이 아니라 예측 불가능한 버스트로 흐르는 전송입니다. 간격은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**DecodeStereoPercent** <br/> |float  <br/> ||스테레오로 디코딩된 통화의 백분율입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**AecRenderStereoPercent** <br/> |float  <br/> ||사운드 에코 취소기에서 스테레오로 렌더링된 통화의 백분율입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**AudioPostFECPLR** <br/> |float  <br/> ||정방 오류 수정이 적용된 후 패킷 손실률입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**EncodeStereoPercent** <br/> |float  <br/> ||스테레오로 인코딩된 통화의 백분율입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**AecCaptureStereoPercent** <br/> |float  <br/> ||사운드 에코 취소기에서 스테레오로 캡처된 통화의 백분율입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
