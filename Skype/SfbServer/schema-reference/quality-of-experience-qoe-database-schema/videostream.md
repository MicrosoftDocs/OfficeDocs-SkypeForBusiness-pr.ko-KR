---
title: VideoStream 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
description: 각 레코드는 하나의 비디오 스트림을 표현합니다. 한 비디오 미디어 줄에는 일반적으로 두 개의 비디오 스트림이 포함되어 있습니다.
ms.openlocfilehash: e506f022dbfa4ef0a1a8578dc6caf7c0f3984fa6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821328"
---
# <a name="videostream-table"></a>VideoStream 테이블
 
각 레코드는 하나의 비디오 스트림을 표현합니다. 한 비디오 미디어 선에는 일반적으로 두 개의 비디오 스트림이 포함되어 있습니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |[MediaLine 테이블에서 참조됩니다.](medialine-0.md)  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |[MediaLine 테이블에서 참조되는 R입니다.](medialine-0.md)  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |[MediaLine 테이블에서 참조됩니다.](medialine-0.md)  <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |미디어 회선 내의 고유 ID입니다.  <br/> |
|**VideoPayloadDescription** <br/> |smallint  <br/> |Foreign, Primary  <br/> |페이로드 설명입니다. 자세한 내용은 [PayloadDescription 테이블을](payloaddescription.md) 참조하세요. <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |RTCP(Real Time Control Protocol) 통계로부터 가져온 평균 네트워크 지터입니다.  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |비디오 세션 중 최대 네트워크 지터입니다.  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |RTCP 통계로부터의 왕복 시간입니다.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |비디오 스트림의 최대 왕복 시간입니다.  <br/> |
|**PacketLossRate** <br/> |decimal(5,4)  <br/> | <br/> |통화 중 평균 패킷 손실 비율입니다.  <br/> |
|**PacketLossRateMax** <br/> |decimal(5,4)  <br/> | <br/> |통화 중 관측된 최대 패킷 손실입니다.  <br/> |
|**PacketUtilization** <br/> |int  <br/> | <br/> |비디오 스트림에 대한 패킷 수입니다(실시간 전송 프로토콜, RTP).  <br/> |
|**BandwidthEst** <br/> |int  <br/> | <br/> |비디오 스트림에 대한 대역폭 예상치입니다.  <br/> |
|**VideoResolution** <br/> |char(9)  <br/> | <br/> |픽셀 너비와 픽셀 높이를 곱한 수치의 비디오 해상도입니다. 문자열로 보고됩니다.  <br/> |
|**VideoBitRateAvg** <br/> |int  <br/> | <br/> |비디오 스트림의 평균 비트 전송률입니다.  <br/> |
|**InboundVideoFrameRateAvg** <br/> |decimal(9,4)  <br/> | <br/> |수신된 비디오 프레임 속도입니다.  <br/> |
|**OutboundVideoFrameRateAvg** <br/> |decimal(9,4)  <br/> | <br/> |전송된 비디오 프레임 속도입니다.  <br/> |
|**VideoBitRateMax** <br/> |int  <br/> | <br/> |비디오 세션 중 최대 비디오 비트 속도입니다.  <br/> |
|**VideoFrameLossRate** <br/> |decimal(9,4)  <br/> | <br/> |손실된 총 비디오 프레임의 백분율입니다.  <br/> |
|**VideoFEC** <br/> |bit  <br/> | <br/> |사용할 수 없습니다.  <br/> |
|**VideoLocalFrameLossPercentageAvg** <br/> |decimal(9,4)  <br/> ||손실된 총 비디오 프레임의 백분율입니다.  <br/> |
|**CIFQualityRatio** <br/> |tinyint  <br/> ||CIF(Common Interchange Format) 해상도에 있는 호출의 백분율입니다.  <br/> |
|**VGAQualityRatio** <br/> |tinyint  <br/> ||VGA 확인 시 호출의 백분율입니다.  <br/> |
|**HD720QualityRatio** <br/> |tinyint  <br/> ||HD720 해상도에 있는 호출의 백분율입니다.  <br/> |
|**NoneDropRatio** <br/> |tinyint  <br/> ||프레임 삭제가 없는 통화 기간의 백분율입니다.  <br/> |
|**BDropRatio** <br/> |tinyint  <br/> ||B 프레임이 놓인 통화 기간의 백분율입니다.  <br/> |
|**BPDropRatio** <br/> |tinyint  <br/> ||BP 프레임이 놓인 통화 기간의 백분율입니다.  <br/> |
|**BPSPDropRatio** <br/> |tinyint  <br/> ||BPSP 프레임이 놓인 통화 시간의 백분율입니다.  <br/> |
|**BPSPIDropRatio** <br/> |tinyint  <br/> ||BPSPI 프레임이 놓인 통화 기간의 백분율입니다.  <br/> |
|**인바운드** <br/> |bit  <br/> | <br/> |수신기 쪽 스트림 데이터를 수신합니다.  <br/> |
|**아웃바운드** <br/> |bit  <br/> | <br/> |보낸 사람 쪽 스트림 데이터를 수신합니다.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1은 스트림 방향이 발신자에서 수신자의 방향임을 의미합니다.  <br/> 0은 스트림 방향이 수신자에서 발신자의 방향임을 의미합니다.  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||통화가 정체 상태인 시간의 백분율을 나타냅니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||지연된 네트워크 패킷 도착으로 인해 정체가 발생한 통화 비율을 나타냅니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||통화가 네트워크 리소스를 위해 경쟁하는 시간의 백분율을 나타냅니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||통화 중에 측정된 최소 대역폭 예상량입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||통화 중에 측정된 최대 대역폭 예상량입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||통화 중에 측정된 대역폭 예상 표준 편차입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||통화 중에 측정된 평균 대역폭 예상량입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**LowBandwidthForMultiview** <br/> |float  <br/> ||끝점에서 네트워크 연결이 멀티뷰 비디오를 지원하지 못했다고 판단한 통화 비율입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||총 단방향 대기 시간입니다. 상대 단방향 대기 시간이 클라이언트와 서버 간의 지연을 측정합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||평균 단방향 대기 시간입니다. 상대 단방향 대기 시간이 클라이언트와 서버 간의 지연을 측정합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||최대 단방향 대기 시간입니다. 상대 단방향 대기 시간이 클라이언트와 서버 간의 지연을 측정합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||총 단방향 버스트 발생 수입니다. "버스트" 전송은 데이터가 불안정한 스트림이 아니라 예측 불가능한 버스트로 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |int  <br/> ||총 단방향 버스트 밀도입니다. "버스트" 전송은 데이터가 불안정한 스트림이 아니라 예측 불가능한 버스트로 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||총 단방향 버스트 기간입니다. "버스트" 전송은 데이터가 불안정한 스트림이 아니라 예측 불가능한 버스트로 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||총 단방형 갭 발생 수입니다. "버스트" 전송은 데이터가 불안정한 스트림이 아니라 예측 불가능한 버스트로 흐르는 전송입니다. 간격은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||총 단방형 갭 밀도입니다. "버스트" 전송은 데이터가 불안정한 스트림이 아니라 예측 불가능한 버스트로 흐르는 전송입니다. 간격은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||총 단도 갭 기간입니다. "버스트" 전송은 데이터가 불안정한 스트림이 아니라 예측 불가능한 버스트로 흐르는 전송입니다. 간격은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**VideoPacketLossRate** <br/> |decimal(9,4)  <br/> ||비디오 패킷이 손실된 비율입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**VideoAllocateBWAvg** <br/> |int  <br/> ||비디오에 할당된 평균 대역폭 양입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**SendCodecTypes** <br/> |smallint  <br/> |외계인  <br/> |보낸 사람이 사용하는 비디오 코덱의 유형입니다. 자세한 내용은 [CodecDescription 테이블을](codecdescription.md) 참조하십시오. <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**SendResolutionWidth** <br/> |int  <br/> ||보낸 사람이 사용하는 해상도 너비입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**SendResolutionHeight** <br/> |int  <br/> ||보낸 사람이 사용하는 해상도 높이입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**SendFrameRateAverage** <br/> |float  <br/> ||보낸 사람이 사용한 평균 비디오 프레임 속도 전송입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**SendBitRateMaximum** <br/> |int  <br/> ||보낸 사람에 대한 최대 비트 전송률입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**SendBitRateAverage** <br/> |int  <br/> ||보낸 사람에 대한 평균 비트 전송률입니다.  <br/> |
|**SendVideoStreamsMax** <br/> |int  <br/> ||보낸 사람이 사용하는 최대 비디오 스트림 수입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**RecvCodecTypes** <br/> |smallint  <br/> |외계인  <br/> |수신자가 사용하는 비디오 코드입니다. 자세한 내용은 [CodecDescription 테이블을](codecdescription.md) 참조하십시오. <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**RecvResolutionWidth** <br/> |int  <br/> ||수신자가 사용하는 해상도 너비입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**RecvResolutionHeight** <br/> |int  <br/> ||수신자가 사용하는 해상도 높이입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**RecvFrameRateAverage** <br/> |float  <br/> ||수신기에서 사용하는 평균 비디오 프레임 속도입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**RecvBitRateMaximum** <br/> |int  <br/> ||수신기의 최대 비트 전송률입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**RecvBitRateAverage** <br/> |int  <br/> ||수신기의 평균 비트 전송률입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**RecvVideoStreamsMax** <br/> |int  <br/> ||수신기의 최대 비디오 스트림입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**RecvVideoStreamsMin** <br/> |int  <br/> ||수신기의 최소 비디오 스트림입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**RecvVideoStreamsMode** <br/> |int  <br/> ||수신기의 비디오 모드(예: 갤러리 또는 단일 스트림)입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**VideoPostFECPLR** <br/> |float  <br/> ||정방 오류 수정이 적용된 후 패킷 손실률입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**DynamicCapabilityPercent** <br/> |float  <br/> ||동적 기능 플래그가 활성 상태인 시간의 백분율입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**ResolutionMin** <br/> |char(9)  <br/> ||통화 중에 측정된 최소 해상도입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**LowBitRateCallPercent** <br/> |float  <br/> ||낮은 비트 속도 임계값 미만의 호출 비율(초당 70킬로비트)입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**LowFrameRateCallPercent** <br/> |float  <br/> ||낮은 프레임 속도 임계값 미만의 호출 비율(초당 7.5프레임, 인바운드)  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**LowResolutionCallPercent** <br/> |float  <br/> ||가장 낮은 해상도에서 발생한 호출의 백분율입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**DurationSeconds** <br/> |float  <br/> ||통화 길이(초)입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
|**IsAggregatedData** <br/> |bit  <br/> ||데이터가 여러 호출에서 집계된지 여부를 나타냅니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입된 것입니다.  <br/> |
   

