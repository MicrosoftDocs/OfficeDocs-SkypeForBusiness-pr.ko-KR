---
title: AppSharingStream 테이블
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
description: AppSharingStream 테이블은 응용 프로그램 공유에 사용되는 네트워크 스트림에 대한 체감 품질 메트릭을 포함합니다. 이 표는 Microsoft Lync Server 2013에서 도입된 것입니다.
ms.openlocfilehash: 6bd74e7e67a5292382a09f6a4cba7fb73fb9c100
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862005"
---
# <a name="appsharingstream-table"></a>AppSharingStream 테이블
 
AppSharingStream 테이블은 응용 프로그램 공유에 사용되는 네트워크 스트림에 대한 체감 품질 메트릭을 포함합니다. 이 표는 Microsoft Lync Server 2013에서 도입된 것입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |dateTime  <br/> |Primary, Foreign  <br/> |세션이 시작된 날짜 및 시간입니다.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary, Foreign  <br/> |같은 날짜와 시간에 시작된 세션을 구분하는 데 사용되는 순차 식별자입니다.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary, Foreign  <br/> | [MediaLine 테이블을 참조합니다.](./medialine-0.md) <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |응용 프로그램 공유 스트림의 고유 식별자입니다.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> ||RTP 패킷 도착 시간 사이에 발견된 평균 지터입니다. 지터는 통화 신호가 "뒤섞인 정도"를 나타냅니다. 일반적으로 정체 현상, 미디어 서버 과부하 등의 경우에는 지터 값이 높게 발생하며 이로 인해 오디오가 왜곡되거나 끊깁니다.  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> ||RTP 패킷 도착 시간 사이에 발견된 최대 지터입니다. 지터는 통화 신호가 "뒤섞인 정도"를 나타냅니다. 일반적으로 정체 현상, 미디어 서버 과부하 등의 경우에는 지터 값이 높게 발생하며 이로 인해 오디오가 왜곡되거나 끊깁니다.  <br/> |
|**RoundTrip** <br/> |int  <br/> ||RTP(Real-time Transport Protocol) 패킷이 다른 끝점으로 이동한 후 다시 돌아오는 데 걸리는 평균 시간(밀리초)입니다. 적정 품질의 왕복 시간은 약 200밀리초 미만 정도로 간주됩니다.  <br/> 국제 통화 라우팅, 잘못된 라우팅 구성 또는 미디어 서버 과부하 등으로 인해 왕복 값이 높게 발생할 수 있습니다. 왕복 시간이 높으면 양방향 실시간 오디오 대화가 어려워집니다.  <br/> |
|**RoundTripMax** <br/> |int  <br/> ||실시간 전송 프로토콜 패킷이 다른 끝점으로 이동한 후 다시 돌아오는 데 걸리는 최대 시간(밀리초)입니다. 적정 품질의 왕복 시간은 약 200밀리초 미만 정도로 간주됩니다.  <br/> 국제 통화 라우팅, 잘못된 라우팅 구성 또는 미디어 서버 과부하 등으로 인해 왕복 값이 높게 발생할 수 있습니다. 왕복 시간이 높으면 양방향 실시간 오디오 대화가 어려워집니다.  <br/> |
|**PacketLossRate** <br/> |float  <br/> ||RTP(Real-time Transport Protocol) 패킷 손실의 평균 비율입니다. 패킷 손실은 RTP 패킷, 인터넷을 통한 오디오 및 비디오 전송을 위해 사용되는 프로토콜인 RTP 패킷이 해당 목적지에 도달하지 못했을 때 발생합니다. 정체 현상, 대역폭 부족, 무선 통화 정체 또는 간섭, 미디어 서버의 과부하 등의 경우에는 손실률이 높게 나타날 수 있습니다. 패킷 손실률이 높으면 오디오가 왜곡되거나 끊깁니다.  <br/> |
|**PacketLossRateMax** <br/> |float  <br/> ||RTP(Real-time Transport Protocol) 패킷 손실의 최대 비율입니다. 패킷 손실은 RTP 패킷, 인터넷을 통한 오디오 및 비디오 전송을 위해 사용되는 프로토콜인 RTP 패킷이 해당 목적지에 도달하지 못했을 때 발생합니다. 정체 현상, 대역폭 부족, 무선 통화 정체 또는 간섭, 미디어 서버의 과부하 등의 경우에는 손실률이 높게 나타날 수 있습니다. 패킷 손실률이 높으면 오디오가 왜곡되거나 끊깁니다.  <br/> |
|**PacketUtilization** <br/> |int  <br/> ||보낸 패킷의 수입니다.  <br/> |
|**BandwidthEst** <br/> |int  <br/> ||세션 종료 시 사용 가능한 예상 단방향 대역폭입니다. 초당 비트 수로 보고됩니다.  <br/> |
|**AppSharingPayloadDescription** <br/> |int  <br/> ||응용 프로그램 공유 페이로드의 설명입니다.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||총 단방향 대기 시간입니다. 상대 단방향 대기 시간이 클라이언트와 서버 간의 지연을 측정합니다.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||평균 단방향 대기 시간입니다. 상대 단방향 대기 시간이 클라이언트와 서버 간의 지연을 측정합니다.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||최대 단방향 대기 시간입니다. 상대 단방향 대기 시간이 클라이언트와 서버 간의 지연을 측정합니다.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||총 단방향 버스트 발생 수입니다. "버스트" 전송은 데이터가 불안정한 스트림이 아니라 예측 불가능한 버스트로 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||총 단방향 버스트 밀도입니다. "버스트" 전송은 데이터가 불안정한 스트림이 아니라 예측 불가능한 버스트로 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||총 단방향 버스트 기간입니다. "버스트" 전송은 데이터가 불안정한 스트림이 아니라 예측 불가능한 버스트로 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||총 단도 갭 발생 수입니다. "버스트" 전송은 데이터가 불안정한 스트림이 아니라 예측 불가능한 버스트로 흐르는 전송입니다. 간격은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||총 단도 갭 밀도입니다. "버스트" 전송은 데이터가 불안정한 스트림이 아니라 예측 불가능한 버스트로 흐르는 전송입니다. 간격은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||총 단도 갭 기간입니다. "버스트" 전송은 데이터가 불안정한 스트림이 아니라 예측 불가능한 버스트로 흐르는 전송입니다. 간격은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.  <br/> |
|**ApplicationSharingType** <br/> |varChar(256)  <br/> ||응용 프로그램 역할(공유자 또는 보기 권한자) 및 콘텐츠 형식입니다.  <br/> |
|**RDPTileProcessingLatencyTotal** <br/> |float  <br/> ||RDP(원격 데스크톱 프로토콜) 타일의 총 처리 시간입니다. 총 시간 값이 크면 보기 환경에서 지연 시간이 길어집니다.  <br/> |
|**RDPTileProcessingLatencyAverage** <br/> |float  <br/> ||RDP(원격 데스크톱 프로토콜) 타일의 평균 처리 시간입니다. 총 시간 값이 크면 보기 환경에서 지연 시간이 길어집니다.  <br/> |
|**RDPTileProcessingLatencyMax** <br/> |float  <br/> ||RDP(원격 데스크톱 프로토콜) 타일의 최대 처리 시간입니다. 총 시간 값이 크면 보기 환경에서 지연 시간이 길어집니다.  <br/> |
|**RDPTileProcessingLatencyBurstOccurrences** <br/> |int  <br/> ||RDP(원격 데스크톱 프로토콜) 타일의 버스트 발생 수입니다. "버스트" 전송은 데이터가 불안정한 스트림이 아니라 예측 불가능한 버스트로 흐르는 전송입니다.  <br/> |
|**RDPTileProcessingLatencyBurstDensity** <br/> |float  <br/> ||RDP(원격 데스크톱 프로토콜) 타일의 버스트 밀도입니다. "버스트" 전송은 데이터가 불안정한 스트림이 아니라 예측 불가능한 버스트로 흐르는 전송입니다.  <br/> |
|**RDPTileProcessingLatencyBurstDuration** <br/> |float  <br/> ||RDP(원격 데스크톱 프로토콜) 타일의 버스트 기간입니다. "버스트" 전송은 데이터가 불안정한 스트림이 아니라 예측 불가능한 버스트로 흐르는 전송입니다.  <br/> |
|**RDPTileProcessingLatencyGapOccurrences** <br/> |int  <br/> ||RDP(원격 데스크톱 프로토콜) 타일의 갭 발생 수입니다.  <br/> |
|**RDPTileProcessingLatencyGapDensity** <br/> |float  <br/> ||RDP(원격 데스크톱 프로토콜) 타일의 처리 시간 갭 밀도입니다. 갭 밀도가 낮으면 보기 환경 성능이 향상됩니다.  <br/> |
|**RDPTileProcessingLatencyGapDuration** <br/> |float  <br/> ||RDP(원격 데스크톱 프로토콜) 타일의 처리 시간 갭 기간입니다. 갭 기간이 짧으면 보기 환경 성능이 향상됩니다.  <br/> |
|**CaptureTileRateTotal** <br/> |float  <br/> ||캡처된 타일의 총 속도(초당 타일 수)입니다.  <br/> |
|**CaptureTileRateAverage** <br/> |float  <br/> ||캡처된 타일의 평균 속도(초당 타일 수)입니다.  <br/> |
|**CaptureTileRateMax** <br/> |float  <br/> ||캡처된 타일의 최대 속도(초당 타일 수)입니다.  <br/> |
|**CaptureTileRateBurstOccurrences** <br/> |int  <br/> ||캡처된 타일 속도의 버스트 발생 수(초당 타일 수)입니다.  <br/> |
|**CaptureTileRateBurstDensity** <br/> |float  <br/> ||캡처된 타일 속도의 버스트 밀도(초당 타일 수)입니다.  <br/> |
|**CaptureTileRateBurstDuration** <br/> |float  <br/> ||캡처된 타일 속도의 버스트 기간(초당 타일 수)입니다.  <br/> |
|**CaptureTileRateGapOccurrences** <br/> |int  <br/> ||캡처된 타일 속도의 갭 발생 수(초당 타일 수)입니다.  <br/> |
|**CaptureTileRateGapDensity** <br/> |float  <br/> ||캡처된 타일 속도의 갭 밀도(초당 타일 수)입니다.  <br/> |
|**CaptureTileRateGapDuration** <br/> |float  <br/> ||캡처된 타일 속도의 갭 기간(초당 타일 수)입니다.  <br/> |
|**SpoiledTilePercentTotal** <br/> |float  <br/> ||보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠의 총 비율입니다.  <br/> |
|**SpoiledTilePercentAverage** <br/> |float  <br/> ||보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠의 평균 비율입니다.  <br/> |
|**SpoiledTilePercentMax** <br/> |float  <br/> ||보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠의 최대 비율입니다.  <br/> |
|**SpoiledTilePercentBurstOccurrences** <br/> |int  <br/> ||보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠에 대한 버스트 발생 수입니다.  <br/> |
|**SpoiledTilePercentBurstDensity** <br/> |float  <br/> ||보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠에 대한 버스트 밀도입니다.  <br/> |
|**SpoiledTilePercentBurstDuration** <br/> |float  <br/> ||보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠에 대한 버스트 기간입니다.  <br/> |
|**SpoiledTilePercentGapOccurrences** <br/> |int  <br/> ||보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠에 대한 갭 발생 수입니다.  <br/> |
|**SpoiledTilePercentGapDensity** <br/> |float  <br/> ||보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠에 대한 갭 밀도입니다.  <br/> |
|**SpoiledTilePercentGapDuration** <br/> |float  <br/> ||보기 권한자에게 전송되지 않았으며 삭제되어 새 콘텐츠로 덮어쓰기된 콘텐츠에 대한 갭 기간입니다.  <br/> |
|**ScrapingFrameRateTotal** <br/> |float  <br/> ||그래픽 원본에서 스크랩된 총 프레임 수입니다.  <br/> |
|**ScrapingFrameRateAverage** <br/> |float  <br/> ||그래픽 원본에서 스크랩된 평균 프레임 수입니다.  <br/> |
|**ScrapingFrameRateMax** <br/> |float  <br/> ||그래픽 원본에서 스크랩된 최대 프레임 수입니다.  <br/> |
|**ScrapingFrameRateBurstOccurrences** <br/> |int  <br/> ||그래픽 원본에서 스크랩된 프레임의 버스트 발생 수입니다.  <br/> |
|**ScrapingFrameRateBurstDensity** <br/> |float  <br/> ||그래픽 원본에서 스크랩된 프레임의 버스트 밀도입니다.  <br/> |
|**ScrapingFrameRateBurstDuration** <br/> |float  <br/> ||그래픽 원본에서 스크랩된 프레임의 버스트 기간입니다.  <br/> |
|**ScrapingFrameRateGapOccurrences** <br/> |int  <br/> ||그래픽 원본에서 스크랩된 프레임의 갭 발생 수입니다.  <br/> |
|**ScrapingFrameRateGapDensity** <br/> |float  <br/> ||그래픽 원본에서 스크랩된 프레임의 갭 밀도입니다.  <br/> |
|**ScrapingFrameRateGapDuration** <br/> |float  <br/> ||그래픽 원본에서 스크랩된 프레임의 갭 기간입니다.  <br/> |
|**IncomingTileRateTotal** <br/> |float  <br/> ||보기 권한자가 받은 총 들어오는 프레임 속도입니다.  <br/> |
|**IncomingTileRateAverage** <br/> |float  <br/> ||보기 권한자가 받은 평균 들어오는 프레임 속도입니다.  <br/> |
|**IncomingTileRateMax** <br/> |float  <br/> ||보기 권한자가 받은 최대 들어오는 타일 속도입니다.  <br/> |
|**IncomingTileRateBurstOccurrences** <br/> |int  <br/> ||보기 권한자가 받은 들어오는 타일 속도의 버스트 발생 수입니다.  <br/> |
|**IncomingTileRateBurstDensity** <br/> |float  <br/> ||보기 권한자가 받은 들어오는 타일 속도의 버스트 밀도입니다.  <br/> |
|**IncomingTileRateBurstDuration** <br/> |float  <br/> ||보기 권한자가 받은 들어오는 타일 속도의 버스트 기간입니다.  <br/> |
|**IncomingTileRateGapOccurrences** <br/> |int  <br/> ||보기 권한자가 받은 들어오는 타일 속도의 갭 발생 수입니다.  <br/> |
|**IncomingTileRateGapDensity** <br/> |float  <br/> ||보기 권한자가 받은 들어오는 타일 속도의 갭 밀도입니다.  <br/> |
|**IncomingTileRateGapDuration** <br/> |float  <br/> ||보기 권한자가 받은 들어오는 타일 속도의 갭 기간입니다.  <br/> |
|**IncomingFrameRateTotal** <br/> |float  <br/> ||보기 권한자가 받은 총 들어오는 프레임 속도입니다.  <br/> |
|**IncomingFrameRateAverage** <br/> |float  <br/> ||보기 권한자가 받은 평균 들어오는 프레임 속도입니다.  <br/> |
|**IncomingFrameRateMax** <br/> |float  <br/> ||보기 권한자가 받은 최대 들어오는 프레임 속도입니다.  <br/> |
|**IncomingFrameRateBurstOccurrences** <br/> |int  <br/> ||보기 권한자가 받은 들어오는 프레임 속도의 버스트 발생 수입니다.  <br/> |
|**IncomingFrameRateBurstDensity** <br/> |float  <br/> ||보기 권한자가 받은 들어오는 프레임 속도의 버스트 밀도입니다.  <br/> |
|**IncomingFrameRateBurstDuration** <br/> |float  <br/> ||보기 권한자가 받은 들어오는 프레임 속도의 버스트 기간입니다.  <br/> |
|**IncomingFrameRateGapOccurrences** <br/> |int  <br/> ||보기 권한자가 받은 들어오는 프레임 속도의 갭 발생 수입니다.  <br/> |
|**IncomingFrameRateGapDensity** <br/> |float  <br/> ||보기 권한자가 받은 들어오는 프레임 속도의 갭 밀도입니다.  <br/> |
|**IncomingFrameRateDuration** <br/> |float  <br/> ||보기 권한자가 받은 들어오는 프레임 속도의 갭 기간입니다.  <br/> |
|**OutgoingTileRateTotal** <br/> |float  <br/> ||보낸 사람에 대한 총 나가는 타일 속도입니다.  <br/> |
|**OutgoingTileRateAverage** <br/> |float  <br/> ||보낸 사람에 대한 평균 나가는 타일 속도입니다.  <br/> |
|**OutgoingTileRateMax** <br/> |float  <br/> ||보낸 사람에 대한 최대 나가는 타일 속도입니다.  <br/> |
|**OutgoingTileRateBurstOccurrences** <br/> |int  <br/> ||보낸 사람에 대한 나가는 타일 속도의 버스트 발생 수입니다.  <br/> |
|**OutgoingTileRateBurstDensity** <br/> |float  <br/> ||보낸 사람에 대한 나가는 타일 속도의 버스트 밀도입니다.  <br/> |
|**OutgoingTileRateBurstDuration** <br/> |float  <br/> ||보낸 사람에 대한 나가는 타일 속도의 버스트 기간입니다.  <br/> |
|**OutgoingTileRateGapOccurrences** <br/> |int  <br/> ||보낸 사람에 대한 나가는 타일 속도의 갭 발생 수입니다.  <br/> |
|**OutgoingTileRateGapDensity** <br/> |float  <br/> ||보낸 사람에 대한 나가는 타일 속도의 갭 밀도입니다.  <br/> |
|**OutgoingTileRateGapDuration** <br/> |float  <br/> ||보낸 사람에 대한 나가는 타일 속도의 갭 기간입니다.  <br/> |
|**OutgoingFrameRateTotal** <br/> |float  <br/> ||보낸 사람에 대한 총 나가는 프레임 속도입니다.  <br/> |
|**OutgoingFrameRateAverage** <br/> |float  <br/> ||보낸 사람에 대한 평균 나가는 프레임 속도입니다.  <br/> |
|**OutgoingFrameRateMax** <br/> |float  <br/> ||보낸 사람에 대한 최대 나가는 프레임 속도입니다.  <br/> |
|**OutgoingFrameRateBurstOccurrences** <br/> |int  <br/> ||보낸 사람에 대한 나가는 프레임 속도의 버스트 발생 수입니다.  <br/> |
|**OutgoingFrameRateBurstDensity** <br/> |float  <br/> ||보낸 사람에 대한 나가는 프레임 속도의 버스트 밀도입니다.  <br/> |
|**OutgoingFrameRateBurstDuration** <br/> |float  <br/> ||보낸 사람에 대한 나가는 프레임 속도의 버스트 기간입니다.  <br/> |
|**OutgoingFrameRateGapOccurrences** <br/> |int  <br/> ||보낸 사람에 대한 나가는 프레임 속도의 갭 발생 수입니다.  <br/> |
|**OutgoingFrameRateGapDensity** <br/> |float  <br/> ||보낸 사람에 대한 나가는 프레임 속도의 갭 밀도입니다.  <br/> |
|**OutgoingFrameRateGapDuration** <br/> |float  <br/> ||보낸 사람에 대한 나가는 프레임 속도의 갭 기간입니다.  <br/> |
|**AverageRectangleHeight** <br/> |int  <br/> ||평균 비디오 해상도 높이(픽셀)입니다.  <br/> |
|**AverageRectangleWidth** <br/> |int  <br/> ||평균 비디오 해상도 너비(픽셀)입니다.  <br/> |
|**인바운드** <br/> |bit  <br/> ||인바운드 전송에 대한 평균 프레임 속도(초당 프레임 수)입니다.  <br/> |
|**아웃바운드** <br/> |bit  <br/> ||아웃바운드 전송에 대한 평균 프레임 속도(초당 프레임 수)입니다.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> ||1은 스트림 방향이 발신자에서 수신자의 방향임을 의미합니다.  <br/> 0은 스트림 방향이 수신자에서 발신자의 방향임을 의미합니다.  <br/> |
