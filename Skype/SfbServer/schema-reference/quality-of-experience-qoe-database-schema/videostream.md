---
title: VideoStream 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
description: 각 레코드는 하나의 비디오 스트림을 나타냅니다. 하나의 비디오 미디어 라인에는 일반적으로 두 개의 비디오 스트림이 포함 됩니다.
ms.openlocfilehash: 678f8b14fb3746ddd50a83ebd68c3878237908e4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196502"
---
# <a name="videostream-table"></a>VideoStream 테이블
 
각 레코드는 하나의 비디오 스트림을 나타냅니다. 하나의 비디오 미디어 라인에는 일반적으로 두 개의 비디오 스트림이 포함 됩니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |dmtf  <br/> |주요한  <br/> |[Medialine 테이블](medialine-0.md)에서 참조 합니다.  <br/> |
|**SessionSeq** <br/> |int  <br/> |주요한  <br/> |R [Medialine 테이블](medialine-0.md)에서 참조 합니다.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |주요한  <br/> |[Medialine 테이블](medialine-0.md)에서 참조 합니다.  <br/> |
|**StreamID** <br/> |int  <br/> |주요한  <br/> |미디어 라인 내의 고유 ID.  <br/> |
|**VideoPayloadDescription** <br/> |smallint  <br/> |외국, 기본  <br/> |페이로드 설명입니다. 자세한 내용은 [PayloadDescription 테이블](payloaddescription.md) 을 참조 하세요. <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |RTCP (실시간 제어 프로토콜) 통계의 평균 네트워크 지터입니다.  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |비디오 세션 중에 최대 네트워크 지터.  <br/> |
|**왕복이** <br/> |int  <br/> | <br/> |RTCP 통계에서 왕복 시간을 계산 합니다.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |비디오 스트림의 최대 라운드 트립 시간입니다.  <br/> |
|**PacketLossRate** <br/> |10 진수 (5, 4)  <br/> | <br/> |통화 중의 평균 패킷 손실 율입니다.  <br/> |
|**PacketLossRateMax** <br/> |10 진수 (5, 4)  <br/> | <br/> |통화 중에 최대 패킷 손실이 관찰 되었습니다.  <br/> |
|**PacketUtilization** <br/> |int  <br/> | <br/> |비디오 스트림의 패킷 개수 (리얼 시간 전송 프로토콜, RTP).  <br/> |
|**BandwidthEst** <br/> |int  <br/> | <br/> |비디오 스트림의 대역폭을 예측 합니다.  <br/> |
|**VideoResolution** <br/> |char (9)  <br/> | <br/> |픽셀 너비를 픽셀 높이로 곱한 비디오 해상도입니다. 문자열로 보고 되었습니다.  <br/> |
|**VideoBitRateAvg** <br/> |int  <br/> | <br/> |비디오 스트림의 평균 비트 전송률입니다.  <br/> |
|**InboundVideoFrameRateAvg** <br/> |10 진수 (9, 4)  <br/> | <br/> |수신 된 비디오 프레임 속도입니다.  <br/> |
|**OutboundVideoFrameRateAvg** <br/> |10 진수 (9, 4)  <br/> | <br/> |전송 된 비디오 프레임 속도입니다.  <br/> |
|**VideoBitRateMax** <br/> |int  <br/> | <br/> |비디오 세션 중의 최대 비디오 비트 전송률입니다.  <br/> |
|**VideoFrameLossRate** <br/> |10 진수 (9, 4)  <br/> | <br/> |손실 된 총 비디오 프레임의 백분율입니다.  <br/> |
|**VideoFEC** <br/> |다소  <br/> | <br/> |사용할 수 없습니다.  <br/> |
|**VideoLocalFrameLossPercentageAvg** <br/> |10 진수 (9, 4)  <br/> ||손실 된 총 비디오 프레임의 백분율입니다.  <br/> |
|**CIFQualityRatio** <br/> |tinyint  <br/> ||CIF (Common 인터체인지 Format) 해상도에 있던 통화의 백분율입니다.  <br/> |
|**VGAQualityRatio** <br/> |tinyint  <br/> ||VGA 해상도의 통화에 대 한 백분율입니다.  <br/> |
|**HD720QualityRatio** <br/> |tinyint  <br/> ||HD720 해상도에 있던 통화의 백분율입니다.  <br/> |
|**NoneDropRatio** <br/> |tinyint  <br/> ||프레임 놓기가 없는 통화의 백분율입니다.  <br/> |
|**BDropRatio** <br/> |tinyint  <br/> ||B 프레임 놓기가 있는 통화 시간의 백분율입니다.  <br/> |
|**BPDropRatio** <br/> |tinyint  <br/> ||BP 프레임 낙하의 통화 시간 백분율.  <br/> |
|**BPSPDropRatio** <br/> |tinyint  <br/> ||BPSP 프레임 놓기를 사용 하는 통화 시간의 백분율입니다.  <br/> |
|**BPSPIDropRatio** <br/> |tinyint  <br/> ||BPSPI 프레임 낙하에 대 한 통화 시간의 백분율입니다.  <br/> |
|**Ipsec** <br/> |다소  <br/> | <br/> |수신기 쪽에 있는 스트림 데이터를 수신 합니다.  <br/> |
|**위한** <br/> |다소  <br/> | <br/> |보낸 사람 측에 있는 스트림 데이터를 수신 했습니다.  <br/> |
|**SenderIsCallerPAI** <br/> |다소  <br/> | <br/> |1은 스트림 방향이 호출자에서 피호출자로 되었음을 의미 합니다.  <br/> 0은 스트림 방향이 피호출자부터 호출자에 게 있음을 의미 합니다.  <br/> |
|**LossCongestionPercent** <br/> |o  <br/> ||통화가 손실 혼잡 상태에 있는 시간의 백분율을 나타냅니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**DelayCongestionPercent** <br/> |o  <br/> ||네트워크 패킷의 지연 도착으로 인해 혼잡이 있는 통화의 백분율을 나타냅니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**ContentionDetectedPercent** <br/> |o  <br/> ||통화가 네트워크 리소스에 대해 경쟁 하는 시간의 백분율을 나타냅니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||통화 중 측정 되는 최소 대역폭 예상 양입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||통화 중에 측정 되는 최대 대역폭 예상 금액입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||통화 중에 측정 되는 대역폭 예상의 표준 편차입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||통화 중 측정 되는 평균 대역폭 예상 금액입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**LowBandwidthForMultiview** <br/> |o  <br/> ||끝점에서 네트워크 연결이 multiview video를 지원 하지 않는 것으로 결정 한 통화의 백분율입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RelativeOneWayTotal** <br/> |o  <br/> ||단방향 총 대기 시간입니다. 상대적 단방향 대기 시간은 클라이언트와 서버 간의 지연을 측정 합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RelativeOneWayAverage** <br/> |o  <br/> ||평균 단방향 대기 시간입니다. 상대적 단방향 대기 시간은 클라이언트와 서버 간의 지연을 측정 합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RelativeOneWayMax** <br/> |o  <br/> ||단방향 대기 시간의 최대 양입니다. 상대적 단방향 대기 시간은 클라이언트와 서버 간의 지연을 측정 합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||전체 단방향 버스트 횟수입니다. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |int  <br/> ||전체 단방향 버스트 밀도. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |o  <br/> ||전체 단방향 버스트 기간입니다. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||전체 단방향 간격이 발생 합니다. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 간격은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RelativeOneWayGapDensity** <br/> |o  <br/> ||전체 단방향 간격 밀도. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 간격은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RelativeOneWayGapDuration** <br/> |o  <br/> ||전체 단방향 간격 기간입니다. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 간격은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**VideoPacketLossRate** <br/> |10 진수 (9, 4)  <br/> ||비디오 패킷이 손실 된 속도입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**VideoAllocateBWAvg** <br/> |int  <br/> ||비디오에 대해 할당 된 평균 대역폭 양입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**SendCodecTypes** <br/> |smallint  <br/> |외부  <br/> |보낸 사람이 사용 하는 비디오 코덱 유형입니다. 자세한 내용은 [CodecDescription 테이블](codecdescription.md) 을 참조 하세요. <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**SendResolutionWidth** <br/> |int  <br/> ||보낸 사람이 사용 하는 해상도 너비입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**SendResolutionHeight** <br/> |int  <br/> ||보낸 사람이 사용 하는 해상도 높이입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**SendFrameRateAverage** <br/> |o  <br/> ||보낸 사람이 사용한 평균 비디오 프레임 속도 전송입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**SendBitRateMaximum** <br/> |int  <br/> ||보낸 사람의 최대 비트 전송률입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**SendBitRateAverage** <br/> |int  <br/> ||보낸 사람의 평균 비트 전송률입니다.  <br/> |
|**SendVideoStreamsMax** <br/> |int  <br/> ||보낸 사람이 사용 하는 비디오 스트림의 최대 수입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RecvCodecTypes** <br/> |smallint  <br/> |외부  <br/> |수신자가 사용 하는 영상 코드입니다. 자세한 내용은 [CodecDescription 테이블](codecdescription.md) 을 참조 하세요. <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RecvResolutionWidth** <br/> |int  <br/> ||수신자가 사용 하는 해상도 너비입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RecvResolutionHeight** <br/> |int  <br/> ||수신기에서 사용 하는 해상도 높이입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RecvFrameRateAverage** <br/> |o  <br/> ||수신기에서 사용 하는 평균 비디오 프레임 속도입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RecvBitRateMaximum** <br/> |int  <br/> ||받는 사람에 대 한 최대 비트 전송률입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RecvBitRateAverage** <br/> |int  <br/> ||수신기의 평균 비트 전송률입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RecvVideoStreamsMax** <br/> |int  <br/> ||수신기에 대 한 최대 비디오 스트림.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RecvVideoStreamsMin** <br/> |int  <br/> ||수신기의 최소 비디오 스트림  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RecvVideoStreamsMode** <br/> |int  <br/> ||수신기에 대 한 비디오 모드 (예: 갤러리 또는 단일 스트림)입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**VideoPostFECPLR** <br/> |o  <br/> ||전달 오류 수정 후 패킷 손실 율이 적용 되었습니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**DynamicCapabilityPercent** <br/> |o  <br/> ||동적 접근 권한 플래그가 활성 상태인 시간의 백분율입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**ResolutionMin** <br/> |char (9)  <br/> ||통화 중에 측정 되는 최소 해상도.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**LowBitRateCallPercent** <br/> |o  <br/> ||낮은 비트 전송률 임계값 이하의 통화 백분율 (초당 70 킬로 비트)입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**LowFrameRateCallPercent** <br/> |o  <br/> ||낮은 프레임 속도 임계값 미만의 통화 백분율 (7.5 프레임/초)  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**LowResolutionCallPercent** <br/> |o  <br/> ||최저 해상도에서 발생 한 통화의 백분율입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**DurationSeconds** <br/> |o  <br/> ||통화의 길이 (초)입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**IsAggregatedData** <br/> |다소  <br/> ||데이터가 여러 호출에서 집계 되었는지 여부를 나타냅니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
   

