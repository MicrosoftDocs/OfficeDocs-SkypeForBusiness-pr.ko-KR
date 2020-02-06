---
title: 오디오 Streamdetail 보기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
description: 오디오 Streamdetail 보기에는 데이터베이스의 각 오디오 스트림에 대 한 정보가 저장 됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: 14815a107654fc83fc2b71c5070b82617154677c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810876"
---
# <a name="audiostreamdetail-view"></a>오디오 Streamdetail 보기
 
오디오 Streamdetail 보기에는 데이터베이스의 각 오디오 스트림에 대 한 정보가 저장 됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
  
|**열**|**데이터 형식**|**세부적인**|
|:-----|:-----|:-----|
|SessionTime  <br/> |dmtf  <br/> |[Medialine 테이블](medialine-0.md)에서 참조 합니다.  <br/> |
|SessionSeq  <br/> |int  <br/> |[Medialine 테이블](medialine-0.md)에서 참조 합니다.  <br/> |
|StreamId  <br/> |int  <br/> |미디어 라인 내의 고유 ID.  <br/> |
|StartTime  <br/> |dmtf  <br/> |세션 시작 시간입니다.  <br/> |
|EndTime  <br/> |dmtf  <br/> |세션 종료 시간입니다.  <br/> |
|DialogCategory  <br/> |다소  <br/> |대화 상자 범주: 0은 서버 레그 조정에 대 한 비즈니스용 Skype 서버입니다. 1은 PSTN 게이트웨이 레그에 대 한 중재 서버입니다.  <br/> |
|MediationServerBypassFlag  <br/> |다소  <br/> |통화가 바이패스 되었는지 여부를 나타내는 플래그입니다.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |바이패스 Id가 일치 하는 경우에도 통화가 무시 되지 않은 이유를 표시 합니다. 하나의 값만 정의 된 경우:  <br/> 0x0001-기본 네트워크 어댑터에 대 한 알 수 없는 바이패스 ID입니다.  <br/> |
|CallPriority  <br/> |int  <br/> |통화의 우선 순위입니다.  <br/> |
|CallerPool  <br/> |nvarchar (256)  <br/> |발신자 풀 FQDN.  <br/> |
|CalleePool  <br/> |nvarchar (256)  <br/> |호출 수신자 풀 FQDN입니다.  <br/> |
|호출인  <br/> |nvarchar (450)  <br/> |호출자의 URI입니다.  <br/> |
|피호출자  <br/> |nvarchar (450)  <br/> |호출 수신자의 URI입니다.  <br/> |
|CallerUserAgent  <br/> |nvarchar (256)  <br/> |호출자의 사용자 에이전트 문자열입니다.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |호출자의 사용자 에이전트 유형입니다. 자세한 내용은 [UserAgent 테이블](useragent.md) 을 참조 하세요. <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |호출자의 사용자 에이전트 범주입니다. 자세한 내용은 [Useragentdef 테이블 (체감 품질)](useragentdef-qoe.md) 을 참조 하세요. <br/> |
|CalleeUserAgent  <br/> |nvarchar (256)  <br/> |호출 수신자의 사용자 에이전트 문자열입니다.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |호출 수신자의 사용자 에이전트 유형입니다. 자세한 내용은 [UserAgent 테이블](useragent.md) 을 참조 하세요. <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |호출 수신자의 사용자 에이전트 범주입니다. 자세한 내용은 [Useragentdef 테이블 (체감 품질)](useragentdef-qoe.md) 을 참조 하세요. <br/> |
|CallerEndpoint  <br/> |nvarchar (256)  <br/> |호출자의 끝점 이름입니다.  <br/> |
|CalleeEndpoint  <br/> |nvarchar (256)  <br/> |호출 수신자의 끝점 이름입니다.  <br/> |
|CallerOS  <br/> |name  <br/> |호출자 끝점의 OS (운영 체제)입니다.  <br/> |
|CalleeOS  <br/> |name  <br/> |호출 수신자의 끝점에 대 한 OS (운영 체제)입니다.  <br/> |
|CallerCPUName  <br/> |name  <br/> |호출자 끝점의 CPU 이름입니다.  <br/> |
|CalleeCPUName  <br/> |name  <br/> |호출 수신자의 끝점에 대 한 CPU 이름입니다.  <br/> |
|Callercpunum<c13> Of코어  <br/> |smallint  <br/> |호출자 끝점의 CPU 코어 수입니다.  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |호출 수신자의 끝점에 있는 CPU 코어 수입니다.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |호출자 끝점의 CPU 프로세서 속도입니다.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |호출 수신자의 끝점에 대 한 CPU 프로세서 속도입니다.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |호출자의 시스템이 가상화 된 환경에서 실행 중인지 여부를 나타냅니다. 자세한 내용은 [끝점 테이블](endpoint.md) 을 참조 하세요. <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |호출 수신자의 시스템이 가상화 된 환경에서 실행 중인지 여부를 나타냅니다. 자세한 내용은 [끝점 테이블](endpoint.md) 을 참조 하세요. <br/> |
|CorrelationKey  <br/> ||상관 관계 키입니다. [Sessioncorrelation 관계 테이블](sessioncorrelation.md)에서 참조 합니다.  <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |미디어 경로에 대 한 정보 (예: 직접 또는 릴레이)입니다. 자세한 내용은 [Medialine 테이블](medialine-0.md) 을 참조 하세요. <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |호출자의 bits 플래그에 설명 된 ICE (대화형 연결 설정) 프로세스에 대 한 정보입니다. 자세한 내용은 경험의 품질 모니터링 서버 프로토콜 사양을 참조 하세요.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |호출 수신자의 bits 플래그에 설명 된 ICE (대화형 연결 설정) 프로세스에 대 한 정보입니다. 자세한 내용은 경험의 품질 모니터링 서버 프로토콜 사양을 참조 하세요.  <br/> |
|운송  <br/> |tinyint  <br/> |전송 종류: 0은 UDP이 고, 1은 TCP입니다.  <br/> |
|CallerIPAddr  <br/> |var (50)  <br/> |발신자의 IP 주소입니다. IPv4 또는 IPv6 주소 일 수 있습니다.  <br/> |
|CallerPort  <br/> |int  <br/> |호출자가 사용 하는 포트입니다.  <br/> |
|CallerInside  <br/> |다소  <br/> |호출자가 간격 네트워크 내에 있는지 여부를 나타냅니다. 1은 호출자가 엔터프라이즈 네트워크 내에 있음을 의미 하 고 0 이면 호출자가 네트워크 외부에 있음을 의미 합니다.  <br/> |
|CalleeIPAddr  <br/> |var (50)  <br/> |호출 수신자의 IP 주소입니다. IPv4 또는 IPv6 주소 일 수 있습니다.  <br/> |
|CalleePort  <br/> |int  <br/> |호출 수신자가 사용 하는 포트입니다.  <br/> |
|CalleeInside  <br/> |다소  <br/> |호출 수신자가 간격 네트워크 내에 있는지 여부를 나타냅니다. 1은 호출 수신자가 엔터프라이즈 네트워크 내에 있음을 의미 하 고 0은 호출 수신자가 네트워크 외부에 있음을 의미 합니다.  <br/> |
|CallerUserSite  <br/> |name  <br/> |호출자 사이트의 이름입니다.  <br/> |
|CallerRegion  <br/> |name  <br/> |발신자 사이트의 국가/지역 이름입니다.  <br/> |
|CalleeUserSite  <br/> |name  <br/> |피호출자 사이트의 이름입니다.  <br/> |
|CalleeRegion  <br/> |name  <br/> |피호출자 사이트의 국가/지역 이름입니다.  <br/> |
|CallerRelayIPAddr  <br/> |var (50)  <br/> |발신자가 사용 하는 A/V Edge 서비스의 IP 주소입니다. 자세한 내용은 [IPAddress 테이블](ipaddress.md) 을 참조 하세요. <br/> |
|CallerRelayPort  <br/> |int  <br/> |호출자가 사용 하는 A/V Edge 서비스에 사용 되는 포트입니다.  <br/> |
|CalleeRelayIPAddr  <br/> |var (50)  <br/> |호출 수신자가 사용 하는 A/V Edge 서비스의 IP 주소 키입니다. 자세한 내용은 [IPAddress 테이블](ipaddress.md) 을 참조 하세요. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |호출 수신자가 사용 하는 A/V Edge 서비스에 사용 되는 포트입니다.  <br/> |
|CallerCaptureDev  <br/> |varchar (256)  <br/> |발신자의 캡처 장치 이름입니다.  <br/> |
|CallerRenderDev  <br/> |varchar (256)  <br/> |발신자의 렌더링 장치 이름.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar (256)  <br/> |발신자의 캡처 장치 드라이버 이름.  <br/> |
|CallerRenderDriver  <br/> |varchar (256)  <br/> |호출자의 렌더링 장치 드라이버 이름입니다.  <br/> |
|CalleeCaptureDev  <br/> |varchar (256)  <br/> |호출 수신자의 캡처 디바이스 이름입니다.  <br/> |
|CalleeRenderDev  <br/> |varchar (256)  <br/> |피호출자의 렌더링 디바이스 이름입니다.  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar (256)  <br/> |피호출자의 캡처 장치 드라이버 이름입니다.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar (256)  <br/> |피호출자의 렌더링 장치 드라이버 이름입니다.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |발신자의 네트워크 연결 유형: 0이 유선 인 경우 1은 무선입니다.  <br/> |
|CallerVPN  <br/> |다소  <br/> |가상 개인 네트워크를 통해 연결 된 호출자가 VPN (가상 사설망) 인 경우 0이 고 VPN이 아닌 경우를 나타냅니다.  <br/> |
|CallerLinkSpeed  <br/> |10 진수 (18, 0)  <br/> |Bps의 호출자 끝점에 대 한 네트워크 링크 속도입니다.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |피호출자의 네트워크 연결 형식: 0이 유선 인 경우 1은 무선입니다.  <br/> |
|CalleeVPN  <br/> |다소  <br/> |가상 개인 네트워크를 통해 연결 된 호출자가 VPN (가상 사설망) 인 경우 0이 고 VPN이 아닌 경우를 나타냅니다.  <br/> |
|CalleeLinkSpeed  <br/> |10 진수 (18, 0)  <br/> |Bps의 호출 수신자 끝점에 대 한 네트워크 링크 속도입니다.  <br/> |
|ConversationalMOS  <br/> |10 진수 (3, 2)  <br/> |오디오 세션의 Narrowband 대화 SPECIALIST (두 오디오 스트림 모두 기준).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |다양 한 정책 설정 (TURN, API, SDP, 정책 서버 등)을 지정 하 여 지정 된 보내기 쪽 스트림에 실제 대역폭을 적용 했습니다. 대역폭 예측을 기준으로 낮은 유효 대역폭을 사용할 수 있기 때문에 효과적인 대역폭과 혼동 하지 않는 것이 좋습니다. 이 값은 기본적으로 전송 스트림에 의해 대역폭 예상에 의해 적용 되는 최대 대역폭을 제한할 수 있습니다.  <br/> |
|JitterInterArrival  <br/> |int  <br/> |RTCP (실시간 제어 프로토콜) 통계의 평균 네트워크 지터입니다.  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |통화 중 최대 네트워크 지터.  <br/> |
|PacketLossRate  <br/> |10 진수 (5, 4)  <br/> |통화 중의 평균 패킷 손실 율입니다.  <br/> |
|PacketLossRateMax  <br/> |10 진수 (5, 4)  <br/> |통화 중에 최대 패킷 손실이 관찰 되었습니다.  <br/> |
|BurstDensity  <br/> |10 진수 (9, 4)  <br/> |통화 중에 손실이 발생 한 경우 패킷 손실의 평균 밀도입니다.  <br/> |
|BurstDuration  <br/> |int  <br/> |통화 중에 손실 되는 패킷 손실의 평균 지속 시간입니다.  <br/> |
|BurstGapDensity  <br/> |10 진수 (9, 4)  <br/> |패킷 손실의 버스트 간에 간격을 두는 경우 패킷 손실의 평균 밀도.  <br/> |
|BurstGapDuration  <br/> |int  <br/> |패킷 손실의 버스트 간 평균 간격 기간입니다.  <br/> |
|PacketUtilization  <br/> |int  <br/> |오디오 스트림의 패킷 수입니다.  <br/> |
|BandwidthEst  <br/> |int  <br/> |오디오 스트림의 대역폭을 예측 합니다.  <br/> |
|DegradationAvg  <br/> |10 진수 (3, 2)  <br/> |전체 통화에 대 한 네트워크 SPECIALIST 성능이 저하 됩니다. 범위는 0.0 ~ 5.0입니다. 이 메트릭은 지터 및 패킷 손실로 인해 네트워크 SPECIALIST 감소 된 양을 표시 합니다. 허용 되는 품질은 0.5 미만 이어야 합니다.  <br/> |
|DegradationMax  <br/> |10 진수 (3, 2)  <br/> |통화 중에 최대 네트워크 SPECIALIST 저하 됩니다.  <br/> |
|DegradationJitterAvg  <br/> |10 진수 (3, 2)  <br/> |지터로 인해 네트워크 SPECIALIST 저하 됩니다.  <br/> |
|DegradationPacketLossAvg  <br/> |10 진수 (3, 2)  <br/> |패킷 손실로 인해 네트워크 SPECIALIST 저하 됩니다.  <br/> |
|PayloadDescription  <br/> |int  <br/> |[PayloadDescription 테이블](payloaddescription.md)에서 참조 되는 통화에 사용 되는 오디오 코덱입니다.  <br/> |
|AudioSampleRate  <br/> |int  <br/> |오디오 스트림의 샘플링 속도입니다.  <br/> |
|CallerSendSignalLevel  <br/> |int  <br/> |발신자가 보낸 오디오에 대 한 아날로그 게인 포스트 컨트롤 오디오 신호 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적절 한 품질을 위해서는 30 dBmo 이상 이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.  <br/> |
|CallerRecvSignalLevel  <br/> |int  <br/> |발신자가 받은 오디오에 대 한 오디오 신호 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적절 한 품질을 위해서는 30 dBmo 이상 이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.  <br/> |
|CallerSendNoiseLevel  <br/> |int  <br/> |발신자가 보낸 오디오에 대 한 아날로그 게인 사후 제어 오디오 노이즈 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적절 한 품질을 위해서는 35 dBmo 미만 이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.  <br/> |
|CallerRecvNoiseLevel  <br/> |int  <br/> |발신자가 받은 오디오에 대 한 아날로그 게인 포스트 컨트롤 오디오 잡음 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적절 한 품질을 위해서는 35 dBmo 미만 이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.  <br/> |
|CallerEchoReturn  <br/> |int  <br/> |호출자에 대 한 에코 반환 손실 보정. 이 메트릭의 단위는 dB입니다. 값이 낮을수록 화면 표시 수준이 낮아집니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.  <br/> |
|CallerSpeakerGlitchRate  <br/> |int  <br/> |호출자의 스피커 렌더링에 대 한 5 분 당 평균 결함입니다. 좋은 품질을 위해서는 5 분에 1 보다 작아야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화기에서 보고 되지 않습니다.  <br/> |
|CallerMicGlitchRate  <br/> |int  <br/> |발신자의 마이크 캡처에 대 한 5 분 당 평균 결함. 좋은 품질을 위해서는 5 분에 1을 미만 이어야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화기에서 보고 되지 않습니다.  <br/> |
|CallerTimestampDriftRateMic  <br/> |10 진수 (9, 2)  <br/> |발신자의 마이크 장치 시계 드리프트 속도 (CPU 클록 기준).  <br/> |
|CallerTimestampDriftRateSpk  <br/> |10 진수 (9, 2)  <br/> |호출자의 스피커 장치 시계 드리프트 속도 (CPU 클록 기준)입니다.  <br/> |
|CallerTimestampErrorMicMs  <br/> |10 진수 (9, 2)  <br/> |평균 마이크 캡처 스트림 타임 스탬프 (밀리초) (통화의 마지막 20 초)  <br/> |
|CallerTimestampErrorSpkMs  <br/> |10 진수 (9, 2)  <br/> |호출자의 스피커 평균 마지막 20 초 동안 스트림 타임 스탬프 오류를 밀리초 단위로 렌더링 합니다.  <br/> |
|CallerVsEntryCauses  <br/> |smallint  <br/> |음성 스위치는 인터럽트 감소 기능이 있는 반 양방향 모드입니다. 자세한 내용은 [Medialine 테이블](medialine-0.md) 을 참조 하세요. <br/> |
|CallerEchoEventCauses  <br/> |tinyint  <br/> |호출자에 대 한 에코 이벤트의 원인입니다. 자세한 내용은 [Medialine 테이블](medialine-0.md) 을 참조 하세요. <br/> |
|CallerEchoPercentMicIn  <br/> |10 진수 (5, 2)  <br/> |발신자의 마이크 캡처 스트림에서 반향을 감지 하는 시간의 백분율입니다. 헤드셋을 사용 하는 경우 값이 작아야 합니다.  <br/> |
|CallerEchoPercentSend  <br/> |10 진수 (5, 2)  <br/> |발신자의 전송 된 스트림에서 반향을 감지 하는 시간의 백분율입니다. 송신 스트림의 화면 표시 백분율 에코 누수를 나타냅니다.  <br/> |
|CallerRxAGCSignalLevel  <br/> |int  <br/> |게이트웨이에서 호출자 오디오에 대 한 중재 서버의 신호 수준을 수신 했습니다. 이는 중재 서버에만 적용 됩니다. 이 메트릭의 단위는 dBoV입니다. 좋은 품질을 위해서는 허용 되는 범위는-30 ~-18 dBoV 이어야 합니다.  <br/> |
|CallerRxAGCNoiseLevel  <br/> |int  <br/> |발신자의 오디오에 대 한 게이트웨이에서 중재 서버에 대 한 신호 수준을 수신 했습니다. 이는 중재 서버에만 적용 됩니다. 이 메트릭의 단위는 dBoV입니다. 좋은 품질을 위해서는 허용 되는 범위가-50 dBoV 미만 이어야 합니다.  <br/> |
|CallerRxAGCGain  <br/> |int  <br/> |조정 서버 쪽의 자동 게인 제어 (AGC)를 호출자의 오디오에 적용 했습니다.  <br/> |
|CallerInitialSignalLevelRMS  <br/> |o  <br/> |통화의 처음 30 초까지 호출자에 게 들어오는 신호에 대 한 루트 평균 제곱근 (RMS).  <br/> |
|CalleeSendSignalLevel  <br/> |int  <br/> |호출 수신자가 보낸 오디오에 대 한 아날로그 게인 포스트 컨트롤 오디오 신호 수준을 나타냅니다. 이 메트릭의 단위는 dBmo입니다. 적절 한 품질을 위해서는 30 dBmo 이상 이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.  <br/> |
|CalleeRecvSignalLevel  <br/> |int  <br/> |호출 수신자가 받은 오디오에 대 한 오디오 신호 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적절 한 품질을 위해서는 30 dBmo 이상 이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.  <br/> |
|CalleeSendNoiseLevel  <br/> |int  <br/> |호출 수신자가 보낸 오디오에 대 한 아날로그 게인 사후 제어 오디오 노이즈 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적절 한 품질을 위해서는 35 dBmo 미만 이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.  <br/> |
|CalleeRecvNoiseLevel  <br/> |int  <br/> |호출 수신자가 받은 오디오에 대 한 아날로그 게인 사후 제어 오디오 노이즈 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적절 한 품질을 위해서는 35 dBmo 미만 이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.  <br/> |
|CalleeEchoReturn  <br/> |int  <br/> |호출 수신자에 대 한 에코 반환 손실 보정. 이 메트릭의 단위는 dB입니다. 값이 낮을수록 화면 표시 수준이 낮아집니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.  <br/> |
|CalleeSpeakerGlitchRate  <br/> |int  <br/> |호출 수신자의 스피커 렌더링에 대 한 5 분 당 평균 결함입니다. 좋은 품질을 위해서는 5 분에 1 보다 작아야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화기에서 보고 되지 않습니다.  <br/> |
|CalleeMicGlitchRate  <br/> |int  <br/> |호출 수신자의 마이크 캡처에 대 한 5 분 당 평균 결함입니다. 좋은 품질을 위해서는 5 분에 1을 미만 이어야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화기에서 보고 되지 않습니다.  <br/> |
|CalleeTimestampDriftRateMic  <br/> |10 진수 (9, 2)  <br/> |CPU 클록을 기준으로 피호출자의 마이크 장치 시계 드리프트 속도입니다.  <br/> |
|CalleeTimestampDriftRateSpk  <br/> |10 진수 (9, 2)  <br/> |CPU 클록을 기준으로 호출 수신자의 스피커 장치 시계 드리프트 속도입니다.  <br/> |
|CalleeTimestampErrorMicMs  <br/> |10 진수 (9, 2)  <br/> |평균 마이크 캡처 스트림 타임 스탬프 (밀리초) (통화의 마지막 20 초)  <br/> |
|CalleeTimestampErrorSpkMs  <br/> |10 진수 (9, 2)  <br/> |호출 수신자의 스피커 평균 마지막 20 초 동안 밀리초 단위의 렌더링 스트림 타임 스탬프 오류  <br/> |
|CalleeVsEntryCauses  <br/> |smallint  <br/> |음성 스위치는 인터럽트 감소 기능이 있는 반 양방향 모드입니다. 자세한 내용은 [Medialine 테이블](medialine-0.md) 을 참조 하세요. <br/> |
|CalleeEchoEventCauses  <br/> |tinyint  <br/> |호출 수신자에 대 한 에코 이벤트의 원인입니다. 자세한 내용은 [Medialine 테이블](medialine-0.md) 을 참조 하세요. <br/> |
|CalleeEchoPercentMicIn  <br/> |10 진수 (5, 2)  <br/> |호출 수신자의 마이크 캡처 스트림에서 화면 표시를 감지 하는 시간의 백분율입니다. 헤드셋을 사용 하는 경우 값이 작아야 합니다.  <br/> |
|CalleeEchoPercentSend  <br/> |10 진수 (5, 2)  <br/> |호출 수신자의 전송 된 스트림에서 반향을 감지 하는 시간의 백분율입니다. 송신 스트림의 화면 표시 백분율 에코 누수를 나타냅니다.  <br/> |
|CalleeRxAGCSignalLevel  <br/> |int  <br/> |게이트웨이에서 호출 수신자의 오디오에 대 한 중재 서버의 신호 수준을 수신 했습니다. 이는 중재 서버에만 적용 됩니다. 이 메트릭의 단위는 dBoV입니다. 좋은 품질을 위해서는 허용 되는 범위는 [-30 ~-18] dBoV 이어야 합니다.  <br/> |
|CalleeRxAGCNoiseLevel  <br/> |int  <br/> |게이트웨이에서 호출 수신자의 오디오에 대 한 조정 서버의 신호 수준을 수신 했습니다. 이는 중재 서버에만 적용 됩니다. 이 메트릭의 단위는 dBoV입니다. 좋은 품질을 위해서는 허용 되는 범위가-50 dBoV 미만 이어야 합니다.  <br/> |
|CalleeRxAGCGain  <br/> |int  <br/> |조정 서버 쪽의 자동 게인 제어 (AGC)를 호출 수신자의 오디오에 적용 했습니다.  <br/> |
|CalleeInitialSignalLevelRMS  <br/> |o  <br/> |호출의 처음 30 초까지 수신자에 대 한 수신 신호에 대 한 루트 평균 제곱근 (RMS)입니다.  <br/> |
|RatioConcealedSamplesAvg  <br/> |10 진수 (5, 2)  <br/> |오디오 치유에서 생성 한 숨겨진 샘플의 평균 비율을 일반적인 샘플입니다.  <br/> |
|RatioStretchedSamplesAvg  <br/> |10 진수 (5, 2)  <br/> |표준 샘플에 대 한 오디오 치유에서 생성 된 늘이기 샘플의 평균 비율입니다.  <br/> |
|RatioCompressedSamplesAvg  <br/> |10 진수 (5, 2)  <br/> |오디오 치유에서 생성 한 압축 샘플의 평균 비율을 일반적인 샘플로 나타낸 것입니다.  <br/> |
|왕복이  <br/> |int  <br/> |RTCP 통계에서 왕복 시간을 계산 합니다.  <br/> |
|RoundTripMax  <br/> |int  <br/> |오디오 스트림의 최대 라운드트립 시간입니다.  <br/> |
|OverallAvgNetworkMOS  <br/> |10 진수 (3, 2)  <br/> |통화에 대 한 평균 광대역 네트워크 SPECIALIST. 이 메트릭은 사용 되는 패킷 손실, 지터 및 코덱에 따라 달라 집니다. 범위는 1.0 ~ 5.0입니다.  <br/> |
|OverallMinNetworkMOS  <br/> |10 진수 (3, 2)  <br/> |통화에 대 한 최소 광대역 네트워크 SPECIALIST.  <br/> |
|SendListenMOS  <br/> |10 진수 (3, 2)  <br/> |음성 수준, 노이즈 수준 및 캡처 장치 특성을 포함 하 여 전송 되는 오디오에 대 한 평균 예측 광대역 SPECIALIST 점수입니다.  <br/> |
|SendListenMOSMin  <br/> |10 진수 (3, 2)  <br/> |통화에 대 한 최소 SendListenMOS.  <br/> |
|RecvListenMOS  <br/> |10 진수 (3, 2)  <br/> |음성 수준, 소음 수준, 코덱, 네트워크 상태 및 캡처 장치 특성을 포함 하 여 네트워크에서 받은 오디오에 대 한 평균 예측 광대역 SPECIALIST 점수입니다.  <br/> |
|RecvListenMOSMin  <br/> |10 진수 (3, 2)  <br/> |통화에 대 한 최소 RecvListenMOS.  <br/> |
|오디오 및 사용  <br/> |다소  <br/> |오디오 FEC 통화에 사용 되었는지 여부를 나타냅니다.  <br/> |
|SenderIsCallerPAI  <br/> |다소  <br/> |P-어설션된 식별 정보의 방향을 나타냅니다. 1은 스트림 방향이 호출자에서 호출 수신자 까지의 것임을 의미 합니다. 0은 스트림 방향이 피호출자부터 호출자에 게 있음을 의미 합니다.  <br/> |
   

