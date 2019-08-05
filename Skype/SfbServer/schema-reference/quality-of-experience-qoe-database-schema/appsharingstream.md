---
title: AppSharingStream 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
description: AppSharingStream 테이블에는 응용 프로그램 공유에 사용 되는 네트워크 스트림에 대 한 경험 메트릭스가 포함 되어 있습니다. 이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: 61606f204310b3956eb74bd19d0c9d8d421e7818
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196586"
---
# <a name="appsharingstream-table"></a>AppSharingStream 테이블
 
AppSharingStream 테이블에는 응용 프로그램 공유에 사용 되는 네트워크 스트림에 대 한 경험 메트릭스가 포함 되어 있습니다. 이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |Dmtf  <br/> |기본, 외래  <br/> |세션이 시작 된 날짜 및 시간입니다.  <br/> |
|**SessionSeq** <br/> |int  <br/> |기본, 외래  <br/> |동일한 날짜와 동시에 시작 된 세션을 구분 하는 데 사용 되는 순차 식별자입니다.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |기본, 외래  <br/> | 자세한 내용은 [Medialine 테이블](https://docs.microsoft.com/skypeforbusiness/schema-reference/quality-of-experience-qoe-database-schema/medialine-0)을 참조 하세요. <br/> |
|**StreamID** <br/> |int  <br/> |주요한  <br/> |응용 프로그램 공유 스트림의 고유 식별자입니다.  <br/> |
|**JitterInterArrival** <br/> |int  <br/> ||RTP 패킷 도착 간에 감지 된 평균 지터. (지터는 통화에 대 한 "shakiness"의 척도입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오를 왜곡 하거나 손실 하 게 됩니다.  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> ||RTP 패킷 도착 사이에서 감지 된 최대 지터. (지터는 통화에 대 한 "shakiness"의 척도입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오를 왜곡 하거나 손실 하 게 됩니다.  <br/> |
|**왕복이** <br/> |int  <br/> ||실시간 전송 프로토콜 패킷이 다른 끝점으로 이동한 다음 다시 이동 하는 데 필요한 평균 시간 (밀리초)입니다. 200 밀리초 이하의 왕복 시간은 허용 되는 품질로 간주 됩니다.  <br/> 높은 라운드트립 값은 국제 통화 라우팅으로 인해 발생할 수 있습니다. 라우팅 구성이 잘못 되었습니다. 또는 오버 로드 된 미디어 서버. 왕복 시간이 높으면 양방향 실시간 음성 대화에서 문제가 발생 합니다.  <br/> |
|**RoundTripMax** <br/> |int  <br/> ||실시간 전송 프로토콜 패킷이 다른 끝점으로 이동한 다음 다시 이동 하는 데 필요한 최대 양 (밀리초)입니다. 200 밀리초 이하의 왕복 시간은 허용 되는 품질로 간주 됩니다.  <br/> 높은 라운드트립 값은 국제 통화 라우팅으로 인해 발생할 수 있습니다. 라우팅 구성이 잘못 되었습니다. 또는 오버 로드 된 미디어 서버. 왕복 시간이 높으면 양방향 실시간 음성 대화에서 문제가 발생 합니다.  <br/> |
|**PacketLossRate** <br/> |o  <br/> ||RTP (실시간 전송 프로토콜) 패킷 손실의 평균 비율입니다. (패킷 손실은 RTP 패킷, 인터넷에서 오디오 및 비디오를 전송 하는 데 사용 되는 프로토콜인 해당 목적지에 도달 하지 못한 경우에 발생 합니다.) 일반적으로 정체 때문에 손실률이 높습니다. 대역폭 부족, 무선 정체 또는 간섭. 또는 오버 로드 된 미디어 서버. 패킷 손실은 일반적으로 오디오의 왜곡 또는 분실을 발생 합니다.  <br/> |
|**PacketLossRateMax** <br/> |o  <br/> ||RTP (실시간 전송 프로토콜) 패킷 손실의 최대 속도입니다. (패킷 손실은 RTP 패킷, 인터넷에서 오디오 및 비디오를 전송 하는 데 사용 되는 프로토콜인 해당 목적지에 도달 하지 못한 경우에 발생 합니다.) 일반적으로 정체 때문에 손실률이 높습니다. 대역폭 부족, 무선 정체 또는 간섭. 또는 오버 로드 된 미디어 서버. 패킷 손실은 일반적으로 오디오의 왜곡 또는 분실을 발생 합니다.  <br/> |
|**PacketUtilization** <br/> |int  <br/> ||전송 된 패킷 수입니다.  <br/> |
|**BandwidthEst** <br/> |int  <br/> ||세션이 끝날 때 사용 가능한 예상 단방향 대역폭입니다. 초당 비트 수로 보고 됩니다.  <br/> |
|**AppSharingPayloadDescription** <br/> |int  <br/> ||응용 프로그램 공유 페이로드에 대 한 설명입니다.  <br/> |
|**RelativeOneWayTotal** <br/> |o  <br/> ||단방향 총 대기 시간입니다. 상대적 단방향 대기 시간은 클라이언트와 서버 간의 지연을 측정 합니다.  <br/> |
|**RelativeOneWayAverage** <br/> |o  <br/> ||평균 단방향 대기 시간입니다. 상대적 단방향 대기 시간은 클라이언트와 서버 간의 지연을 측정 합니다.  <br/> |
|**RelativeOneWayMax** <br/> |o  <br/> ||단방향 대기 시간의 최대 양입니다. 상대적 단방향 대기 시간은 클라이언트와 서버 간의 지연을 측정 합니다.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||전체 단방향 버스트 횟수입니다. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |o  <br/> ||전체 단방향 버스트 밀도. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |o  <br/> ||전체 단방향 버스트 기간입니다. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||전체 단방향 간격이 발생 합니다. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 간격은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.  <br/> |
|**RelativeOneWayGapDensity** <br/> |o  <br/> ||전체 단방향 간격 밀도. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 간격은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.  <br/> |
|**RelativeOneWayGapDuration** <br/> |o  <br/> ||전체 단방향 간격 기간입니다. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 간격은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.  <br/> |
|**ApplicationSharingType** <br/> |varChar (256)  <br/> ||응용 프로그램 역할 (공유자 또는 뷰어) 및 콘텐츠 형식.  <br/> |
|**RDPTileProcessingLatencyTotal** <br/> |o  <br/> ||RDP (원격 데스크톱 프로토콜) 타일의 총 처리 시간입니다. 합계가 높을수록 보기 환경에 걸리는 시간이 길어집니다.  <br/> |
|**RDPTileProcessingLatencyAverage** <br/> |o  <br/> ||RDP (원격 데스크톱 프로토콜) 타일의 평균 처리 시간입니다. 합계가 높을수록 보기 환경에 걸리는 시간이 길어집니다.  <br/> |
|**RDPTileProcessingLatencyMax** <br/> |o  <br/> ||RDP (원격 데스크톱 프로토콜) 타일의 최대 처리 시간입니다. 합계가 높을수록 보기 환경에 걸리는 시간이 길어집니다.  <br/> |
|**RDPTileProcessingLatencyBurstOccurrences** <br/> |int  <br/> ||RDP (원격 데스크톱 프로토콜) 타일에 대해 처리 시간에 걸리는 버스트 횟수입니다. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다.  <br/> |
|**RDPTileProcessingLatencyBurstDensity** <br/> |o  <br/> ||RDP (원격 데스크톱 프로토콜) 타일의 처리 시간에 대 한 버스트 밀도. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다.  <br/> |
|**RDPTileProcessingLatencyBurstDuration** <br/> |o  <br/> ||RDP (원격 데스크톱 프로토콜) 타일의 처리 시간에 대 한 버스트 기간입니다. "Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다.  <br/> |
|**RDPTileProcessingLatencyGapOccurrences** <br/> |int  <br/> ||RDP (원격 데스크톱 프로토콜) 타일에 대 한 처리 시간 간격  <br/> |
|**RDPTileProcessingLatencyGapDensity** <br/> |o  <br/> ||RDP (원격 데스크톱 프로토콜) 타일의 처리 시간에 대 한 간격 밀도 낮은 간격 밀도는 더 나은 시청 환경을 말합니다.  <br/> |
|**RDPTileProcessingLatencyGapDuration** <br/> |o  <br/> ||RDP (원격 데스크톱 프로토콜) 타일의 처리 시간에 대 한 간격 기간입니다. 짧은 간격 기간은 더 나은 시청 환경과 동등 합니다.  <br/> |
|**CaptureTileRateTotal** <br/> |o  <br/> ||캡처된 타일의 총 속도 (타일/초)입니다.  <br/> |
|**CaptureTileRateAverage** <br/> |o  <br/> ||캡처된 타일의 평균 비율 (초당 타일 수)입니다.  <br/> |
|**CaptureTileRateMax** <br/> |o  <br/> ||캡처한 타일의 최대 속도 (초 당 타일 수)입니다.  <br/> |
|**CaptureTileRateBurstOccurrences** <br/> |t  <br/> ||캡처된 타일의 속도 (초 당 타일 단위)의 버스트 횟수입니다.  <br/> |
|**CaptureTileRateBurstDensity** <br/> |o  <br/> ||캡처한 타일 속도의 버스트 밀도 (초당 타일 수)입니다.  <br/> |
|**CaptureTileRateBurstDuration** <br/> |o  <br/> ||캡처된 타일의 속도 (초당 타일 단위)로 버스트 기간을 유지 합니다.  <br/> |
|**CaptureTileRateGapOccurrences** <br/> |int  <br/> ||캡처된 타일의 비율 (초 당 타일 단위) 간격입니다.  <br/> |
|**CaptureTileRateGapDensity** <br/> |o  <br/> ||캡처된 타일의 비율 (초당 타일 수)의 간격 밀도  <br/> |
|**CaptureTileRateGapDuration** <br/> |o  <br/> ||캡처된 타일의 비율 (초당 타일 단위) 간격입니다.  <br/> |
|**SpoiledTilePercentTotal** <br/> |o  <br/> ||Viewer에 도달 하지 않았지만 대신 새 콘텐츠가 삭제 되 고 덮어쓴 콘텐츠의 총 백분율입니다.  <br/> |
|**SpoiledTilePercentAverage** <br/> |o  <br/> ||Viewer에 도달 하지 않은 콘텐츠의 평균 백분율이 며, 그 대신 삭제 되 고 새 콘텐츠가 덮어쓰여집니다.  <br/> |
|**SpoiledTilePercentMax** <br/> |o  <br/> ||Viewer에 도달 하지 않았지만 대신 새 콘텐츠가 삭제 되 고 덮어쓴 콘텐츠의 최대 백분율입니다.  <br/> |
|**SpoiledTilePercentBurstOccurrences** <br/> |int  <br/> ||Viewer에 도달 하지 않았지만 대신 새 콘텐츠가 삭제 되 고 덮어쓴 콘텐츠의 버스트 발생  <br/> |
|**SpoiledTilePercentBurstDensity** <br/> |o  <br/> ||Viewer에 도달 하지는 않았지만 대신 새 콘텐츠가 삭제 되 고 덮어쓴 콘텐츠의 버스트 밀도.  <br/> |
|**SpoiledTilePercentBurstDuration** <br/> |o  <br/> ||Viewer에 도달 하지 않았지만 대신 새 콘텐츠가 삭제 되 고 덮어쓴 콘텐츠의 버스트 기간입니다.  <br/> |
|**SpoiledTilePercentGapOccurrences** <br/> |int  <br/> ||표시기에 도달 하지는 않았지만 대신 새 콘텐츠가 삭제 되 고 덮어쓴 콘텐츠의 간격이 발생 합니다.  <br/> |
|**SpoiledTilePercentGapDensity** <br/> |o  <br/> ||Viewer에 도달 하지는 않지만 대신 새 콘텐츠가 삭제 되 고 덮어쓴 콘텐츠의 간격 조밀도  <br/> |
|**SpoiledTilePercentGapDuration** <br/> |o  <br/> ||Viewer에 도달 하지 않았지만 대신 새 콘텐츠가 삭제 되 고 덮어쓴 콘텐츠의 간격 기간입니다.  <br/> |
|**ScrapingFrameRateTotal** <br/> |o  <br/> ||그래픽 원본에서 scraped 총 프레임 수입니다.  <br/> |
|**ScrapingFrameRateAverage** <br/> |o  <br/> ||그래픽 원본에서 scraped 평균 프레임 수입니다.  <br/> |
|**ScrapingFrameRateMax** <br/> |o  <br/> ||그래픽 원본에서 scraped 최대 프레임 수를 표시 합니다.  <br/> |
|**ScrapingFrameRateBurstOccurrences** <br/> |int  <br/> ||그래픽 원본에서 scraped 프레임의 버스트 발생  <br/> |
|**ScrapingFrameRateBurstDensity** <br/> |o  <br/> ||그래픽 원본에서 scraped 프레임의 버스트 밀도.  <br/> |
|**ScrapingFrameRateBurstDuration** <br/> |o  <br/> ||그래픽 원본에서 scraped 프레임의 버스트 지속 시간입니다.  <br/> |
|**ScrapingFrameRateGapOccurrences** <br/> |int  <br/> ||그래픽 원본에서 프레임의 간격 scraped.  <br/> |
|**ScrapingFrameRateGapDensity** <br/> |o  <br/> ||그래픽 원본에서 scraped 프레임의 간격 조밀도  <br/> |
|**ScrapingFrameRateGapDuration** <br/> |o  <br/> ||그래픽 원본에서 scraped 프레임의 간격 지속 시간입니다.  <br/> |
|**IncomingTileRateTotal** <br/> |o  <br/> ||뷰어에서 받은 총 수신 프레임 속도입니다.  <br/> |
|**IncomingTileRateAverage** <br/> |o  <br/> ||뷰어에서 받은 수신 프레임의 평균 속도입니다.  <br/> |
|**IncomingTileRateMax** <br/> |o  <br/> ||뷰어에서 수신 된 최대 타일 속도입니다.  <br/> |
|**IncomingTileRateBurstOccurrences** <br/> |int  <br/> ||뷰어에서 받은 들어오는 타일 속도의 버스트 횟수입니다.  <br/> |
|**IncomingTileRateBurstDensity** <br/> |o  <br/> ||뷰어에서 받은 들어오는 타일 속도의 버스트 밀도.  <br/> |
|**IncomingTileRateBurstDuration** <br/> |o  <br/> ||뷰어에서 받은 들어오는 타일 속도의 버스트 기간입니다.  <br/> |
|**IncomingTileRateGapOccurrences** <br/> |int  <br/> ||Viewer에서 받은 들어오는 타일 속도의 간격 횟수입니다.  <br/> |
|**IncomingTileRateGapDensity** <br/> |o  <br/> ||뷰어에서 받은 들어오는 타일 속도의 간격 밀도  <br/> |
|**IncomingTileRateGapDuration** <br/> |o  <br/> ||뷰어에서 받은 들어오는 타일 속도의 간격 기간입니다.  <br/> |
|**IncomingFrameRateTotal** <br/> |o  <br/> ||뷰어에서 받은 총 수신 프레임 속도입니다.  <br/> |
|**IncomingFrameRateAverage** <br/> |o  <br/> ||뷰어에서 받은 수신 프레임의 평균 속도입니다.  <br/> |
|**IncomingFrameRateMax** <br/> |o  <br/> ||뷰어에서 받은 최대 수신 프레임 속도입니다.  <br/> |
|**IncomingFrameRateBurstOccurrences** <br/> |int  <br/> ||뷰어에서 받은 들어오는 프레임 속도의 버스트 횟수입니다.  <br/> |
|**IncomingFrameRateBurstDensity** <br/> |o  <br/> ||뷰어에서 받은 들어오는 프레임 속도의 버스트 밀도.  <br/> |
|**IncomingFrameRateBurstDuration** <br/> |o  <br/> ||뷰어에서 받은 들어오는 프레임 속도의 버스트 기간입니다.  <br/> |
|**IncomingFrameRateGapOccurrences** <br/> |int  <br/> ||뷰어에서 받은 들어오는 프레임 속도의 간격  <br/> |
|**IncomingFrameRateGapDensity** <br/> |o  <br/> ||뷰어에서 받은 들어오는 프레임 속도의 간격 밀도  <br/> |
|**IncomingFrameRateDuration** <br/> |o  <br/> ||뷰어에서 받은 들어오는 프레임 속도의 간격 기간입니다.  <br/> |
|**OutgoingTileRateTotal** <br/> |o  <br/> ||보낸 사람의 총 송신 타일 속도입니다.  <br/> |
|**OutgoingTileRateAverage** <br/> |o  <br/> ||보낸 사람에 대 한 송신 타일 속도의 평균입니다.  <br/> |
|**OutgoingTileRateMax** <br/> |o  <br/> ||보낸 사람의 최대 보내는 타일 속도입니다.  <br/> |
|**OutgoingTileRateBurstOccurrences** <br/> |int  <br/> ||보낸 사람에 대 한 보내는 타일 속도의 버스트 횟수입니다.  <br/> |
|**OutgoingTileRateBurstDensity** <br/> |o  <br/> ||보낸 사람에 대 한 송신 타일 속도의 버스트 밀도입니다.  <br/> |
|**OutgoingTileRateBurstDuration** <br/> |o  <br/> ||보낸 사람에 대 한 송신 타일 속도의 버스트 기간입니다.  <br/> |
|**OutgoingTileRateGapOccurrences** <br/> |int  <br/> ||보낸 사람에 대 한 보내는 타일 속도의 간격입니다.  <br/> |
|**OutgoingTileRateGapDensity** <br/> |o  <br/> ||보낸 사람에 대 한 송신 타일 속도의 간격 밀도입니다.  <br/> |
|**OutgoingTileRateGapDuration** <br/> |o  <br/> ||보낸 사람에 대 한 보내는 타일 속도의 간격 기간입니다.  <br/> |
|**OutgoingFrameRateTotal** <br/> |o  <br/> ||보낸 사람의 총 송신 프레임 속도입니다.  <br/> |
|**OutgoingFrameRateAverage** <br/> |o  <br/> ||보낸 사람의 평균 송신 프레임 속도입니다.  <br/> |
|**OutgoingFrameRateMax** <br/> |o  <br/> ||보낸 사람의 최대 송신 프레임 속도입니다.  <br/> |
|**OutgoingFrameRateBurstOccurrences** <br/> |int  <br/> ||보낸 사람에 대해 보내는 프레임 속도의 버스트 횟수입니다.  <br/> |
|**OutgoingFrameRateBurstDensity** <br/> |o  <br/> ||보낸 사람의 보내는 프레임 속도에 대 한 버스트 밀도입니다.  <br/> |
|**OutgoingFrameRateBurstDuration** <br/> |o  <br/> ||보낸 사람에 대 한 보내는 프레임 속도의 버스트 기간입니다.  <br/> |
|**OutgoingFrameRateGapOccurrences** <br/> |int  <br/> ||보낸 사람에 대해 보내는 프레임 속도의 간격입니다.  <br/> |
|**OutgoingFrameRateGapDensity** <br/> |o  <br/> ||보낸 사람의 보내는 프레임 속도에 대 한 간격 밀도입니다.  <br/> |
|**OutgoingFrameRateGapDuration** <br/> |o  <br/> ||보낸 사람의 보내는 프레임 속도에 대 한 간격 기간입니다.  <br/> |
|**AverageRectangleHeight** <br/> |int  <br/> ||평균 비디오 해상도 높이 (픽셀)입니다.  <br/> |
|**AverageRectangleWidth** <br/> |int  <br/> ||평균 비디오 해상도 너비 (픽셀 단위)입니다.  <br/> |
|**Ipsec** <br/> |다소  <br/> ||인바운드 전송의 평균 프레임 속도 (초당 프레임 수)입니다.  <br/> |
|**위한** <br/> |다소  <br/> ||아웃 바운드 전송의 평균 프레임 속도 (초당 프레임 수)입니다.  <br/> |
|**SenderIsCallerPAI** <br/> |다소  <br/> ||1은 스트림 방향이 호출자에서 피호출자로 되었음을 의미 합니다.  <br/> 0은 스트림 방향이 피호출자부터 호출자에 게 있음을 의미 합니다.  <br/> |
   

