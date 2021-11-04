---
title: AudioStreamDetail 보기
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
description: AudioStreamDetail 보기에는 데이터베이스의 각 오디오 스트림에 대한 정보가 저장됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
ms.openlocfilehash: 3485ac8e8f2f38e7440ef723dfa40b3530589fc8
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741864"
---
# <a name="audiostreamdetail-view"></a>AudioStreamDetail 보기
 
AudioStreamDetail 보기에는 데이터베이스의 각 오디오 스트림에 대한 정보가 저장됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
  
|**열**|**데이터 형식**|**세부 정보**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |[MediaLine 테이블에서 참조됩니다.](medialine-0.md)  <br/> |
|SessionSeq  <br/> |int  <br/> |[MediaLine 테이블에서 참조됩니다.](medialine-0.md)  <br/> |
|StreamId  <br/> |int  <br/> |미디어 회선 내의 고유 ID입니다.  <br/> |
|StartTime  <br/> |datetime  <br/> |세션 시작 시간입니다.  <br/> |
|EndTime  <br/> |datetime  <br/> |세션 종료 시간입니다.  <br/> |
|DialogCategory  <br/> |bit  <br/> |대화 상자 범주: 0은 비즈니스용 Skype 서버 서버 레그에 연결됩니다. 1은 중재 서버 -PSTN 게이트웨이 레그입니다.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |통화가 바이패스되었는지 여부를 나타내는 플래그입니다.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |이 필드는(제공된 경우) 바이패스 ID가 일치한 경우에도 통화가 바이패스되지 않은 이유를 나타냅니다. 하나의 값만 정의되어 있습니다.  <br/> 0x0001 - 기본 네트워크 어댑터의 알 수 없는 우회 ID입니다.  <br/> |
|CallPriority  <br/> |int  <br/> |통화 우선 순위입니다.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |발신자 풀 FQDN입니다.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |수신자 풀 FQDN입니다.  <br/> |
|발신자  <br/> |nvarchar(450)  <br/> |발신자 URI입니다.  <br/> |
|발신자  <br/> |nvarchar(450)  <br/> |발신자 URI입니다.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |발신자 사용자 에이전트 문자열입니다.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |발신자 사용자 에이전트의 유형입니다. 자세한 내용은 [UserAgent 테이블을](useragent.md) 참조합니다. <br/> |
|CallerUserAgentCategory  <br/> |nvarchar(64)  <br/> |발신자 사용자 에이전트의 범주입니다. 자세한 내용은 [UserAgentDef 테이블(QoE)을](useragentdef-qoe.md) 참조합니다. <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |발신자 사용자 에이전트 문자열입니다.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |발신자 사용자 에이전트의 유형입니다. 자세한 내용은 [UserAgent 테이블을](useragent.md) 참조하십시오. <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar(64)  <br/> |발신자 사용자 에이전트의 범주입니다. 자세한 내용은 [UserAgentDef 테이블(QoE)을](useragentdef-qoe.md) 참조하세요. <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |발신자 끝점 이름입니다.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |발신자 끝점 이름입니다.  <br/> |
|CallerOS  <br/> |nvarchar(128)  <br/> |발신자 끝점의 OS(운영 체제)입니다.  <br/> |
|CalleeOS  <br/> |nvarchar(128)  <br/> |발신자 끝점의 OS(운영 체제)입니다.  <br/> |
|CallerCPUName  <br/> |nvarchar(128)  <br/> |발신자 끝점의 CPU 이름입니다.  <br/> |
|CalleeCPUName  <br/> |nvarchar(128)  <br/> |발신자 끝점의 CPU 이름입니다.  <br/> |
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |발신자 끝점의 CPU 코어 수입니다.  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |발신자 끝점의 CPU 코어 수입니다.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |발신자 끝점의 CPU 프로세서 속도입니다.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |발신자 끝점의 CPU 프로세서 속도입니다.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |발신자 시스템이 가상화된 환경에서 실행되고 있는지 여부를 나타냅니다. 자세한 내용은 [Endpoint 테이블을](endpoint.md) 참조하세요. <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |가상화된 환경에서 발신자 시스템이 실행되고 있는지 여부를 나타냅니다. 자세한 내용은 [Endpoint 테이블을](endpoint.md) 참조하세요. <br/> |
|CorrelationKey  <br/> ||상관 관계 키입니다. [SessionCorrelation 테이블에서 참조됩니다.](sessioncorrelation.md)  <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |직접 또는 중계와 같은 미디어 경로에 대한 정보입니다. 자세한 내용은 [MediaLine 테이블을](medialine-0.md) 참조하세요. <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |비트 플래그로 설명된 발신자 측 ICE(Interactive Connectivity Establishment) 프로세스에 대한 정보입니다. 자세한 내용은 체감 품질 모니터링 서버 프로토콜 사양을 참조하십시오.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |비트 플래그로 설명된 수신자 측 ICE(Interactive Connectivity Establishment) 프로세스에 대한 대한 정보입니다. 자세한 내용은 체감 품질 모니터링 서버 프로토콜 사양을 참조하십시오.  <br/> |
|전송  <br/> |tinyint  <br/> |전송 종류: 0은 UDP, 1은 TCP입니다.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |발신자의 IP 주소입니다. 이 주소는 IPv4 또는 IPv6 주소일 수 있습니다.  <br/> |
|CallerPort  <br/> |int  <br/> |발신자가 사용하는 포트입니다.  <br/> |
|CallerInside  <br/> |bit  <br/> |발신자가 내부 네트워크에 있는지 여부를 나타냅니다. 1은 발신자가 회사 네트워크 내에 있음을 의미하고 0은 발신자가 네트워크 외부에 있음을 의미합니다.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |수신자의 IP 주소입니다. 이 주소는 IPv4 또는 IPv6 주소일 수 있습니다.  <br/> |
|CalleePort  <br/> |int  <br/> |수신자가 사용하는 포트입니다.  <br/> |
|CalleeInside  <br/> |bit  <br/> |수신자가 내부 네트워크에 있는지 여부를 나타냅니다. 1은 수신자가 회사 네트워크 내에 있음을 의미하고 0은 수신자가 네트워크 외부에 있음을 의미합니다.  <br/> |
|CallerUserSite  <br/> |nvarchar(128)  <br/> |발신자 사이트의 이름입니다.  <br/> |
|CallerRegion  <br/> |nvarchar(128)  <br/> |발신자 사이트의 국가/지역 이름입니다.  <br/> |
|CalleeUserSite  <br/> |nvarchar(128)  <br/> |발신자 사이트의 이름입니다.  <br/> |
|CalleeRegion  <br/> |nvarchar(128)  <br/> |발신자 사이트의 국가/지역 이름입니다.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |A/V 에지 서비스에서 발신자가 사용하는 IP 주소입니다. 자세한 내용은 [IPAddress 테이블을](ipaddress.md) 참조하세요. <br/> |
|CallerRelayPort  <br/> |int  <br/> |발신자가 사용하는 A/V 에지 서비스에서 사용되는 포트입니다.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |A/V 에지 서비스에서 수신자가 사용하는 IP 주소 키입니다. 자세한 내용은 [IPAddress 테이블을](ipaddress.md) 참조하세요. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |수신자가 사용하는 A/V 에지 서비스에서 사용되는 포트입니다.  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |발신자 캡처 장치 이름입니다.  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |발신자 렌더링 장치 이름입니다.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |발신자 캡처 장치 드라이버 이름입니다.  <br/> |
|CallerRenderDriver  <br/> |varchar(256)  <br/> |발신자 렌더링 장치 드라이버 이름입니다.  <br/> |
|CalleeCaptureDev  <br/> |varchar(256)  <br/> |발신자 캡처 장치 이름입니다.  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |발신자 렌더링 장치 이름입니다.  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar(256)  <br/> |발신자 캡처 장치 드라이버 이름입니다.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |발신자 렌더링 장치 드라이버 이름입니다.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |발신자 네트워크 연결 유형: 0은 유선, 1은 무선입니다.  <br/> |
|CallerVPN  <br/> |bit  <br/> |발신자가 가상 사설망을 통해 연결되어 있는지 여부를 나타냅니다.1은 VPN(가상 사설망), 0은 VPN 외입니다.  <br/> |
|CallerLinkSpeed  <br/> |decimal(18,0)  <br/> |발신자의 끝점에 대한 네트워크 연결 속도(bps)입니다.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |발신자 네트워크 연결 유형: 0은 유선, 1은 무선입니다.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |수신자가 가상 사설망을 통해 연결되어 있는지 여부를 나타냅니다.1은 VPN(가상 사설망), 0은 VPN 외입니다.  <br/> |
|CalleeLinkSpeed  <br/> |decimal(18,0)  <br/> |수신자의 끝점에 대한 네트워크 연결 속도(bps)입니다.  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |오디오 세션의 협대역 대화 MOS입니다(두 오디오 스트림을 모두 기반으로 함).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |다양한 정책 설정(TURN, API, SDP, 정책 서버 등)이 제공된 지정된 송신측 스트림에 적용되는 실제 대역폭입니다. 이 대역폭은 대역폭 예상에 따라 유효 대역폭이 더 낮을 수 있으므로 유효 대역폭과 혼동해서는 안됩니다. 이 대역폭은 기본적으로 대역폭 예상치로 지정된 한도를 제외하고 송신 스트림이 사용할 수 있는 최대 대역폭입니다.  <br/> |
|JitterInterArrival  <br/> |int  <br/> |RTCP(Real Time Control Protocol) 통계로부터 가져온 평균 네트워크 지터입니다.  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |통화 중 최대 네트워크 지터입니다.  <br/> |
|PacketLossRate  <br/> |decimal(5,4)  <br/> |통화 중 평균 패킷 손실 비율입니다.  <br/> |
|PacketLossRateMax  <br/> |decimal(5,4)  <br/> |통화 중 관측된 최대 패킷 손실량입니다.  <br/> |
|BurstDensity  <br/> |decimal(9,4)  <br/> |통화 중 손실량이 많아지는 기간 동안의 평균 패킷 손실 밀도입니다.  <br/> |
|BurstDuration  <br/> |int  <br/> |통화 중 손실량이 많아지는 기간 동안의 평균 패킷 손실 기간입니다.  <br/> |
|BurstGapDensity  <br/> |decimal(9,4)  <br/> |패킷 손실이 최고치인 기간 사이의 간격 중에 발생하는 평균 패킷 손실 밀도입니다.  <br/> |
|BurstGapDuration  <br/> |int  <br/> |패킷 손실이 최고치인 기간 사이의 간격에 대한 평균 기간입니다.  <br/> |
|PacketUtilization  <br/> |int  <br/> |오디오 스트림에 대한 패킷 수입니다.  <br/> |
|BandwidthEst  <br/> |int  <br/> |오디오 스트림에 대한 대역폭 예상치입니다.  <br/> |
|DegradationAvg  <br/> |decimal(3,2)  <br/> |전체 통화에 대한 네트워크 MOS 저하입니다. 범위는 0.0에서 5.0까지입니다. 이 메트릭은 지터 및 패킷 손실로 인해 감소된 네트워크 MOS의 양을 보여 줍니다. 적정 품질을 위해서는 0.5 미만이어야 합니다.  <br/> |
|DegradationMax  <br/> |decimal(3,2)  <br/> |통화 중 최대 네트워크 MOS 저하입니다.  <br/> |
|DegradationJitterAvg  <br/> |decimal(3,2)  <br/> |지터로 인해 발생한 네트워크 MOS 저하입니다.  <br/> |
|DegradationPacketLossAvg  <br/> |decimal(3,2)  <br/> |패킷 손실로 인해 발생한 네트워크 MOS 저하입니다.  <br/> |
|PayloadDescription  <br/> |int  <br/> |[PayloadDescription](payloaddescription.md)테이블에서 참조되는 통화에 사용되는 오디오 코덱입니다.  <br/> |
|AudioSampleRate  <br/> |int  <br/> |오디오 스트림에 대한 샘플링 속도입니다.  <br/> |
|CallerSendSignalLevel  <br/> |int  <br/> |발신자가 전송한 오디오의 포스트 아날로그 게인 컨트롤 오디오 신호 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 최소 30 dBmo여야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.  <br/> |
|CallerRecvSignalLevel  <br/> |int  <br/> |발신자가 수신한 오디오의 오디오 신호 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 최소 30 dBmo여야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.  <br/> |
|CallerSendNoiseLevel  <br/> |int  <br/> |발신자가 전송한 오디오의 포스트 아날로그 게인 컨트롤 오디오 소음 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 35 dBmo 미만이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.  <br/> |
|CallerRecvNoiseLevel  <br/> |int  <br/> |발신자가 수신한 오디오의 포스트 아날로그 게인 컨트롤 오디오 소음 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 35 dBmo 미만이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.  <br/> |
|CallerEchoReturn  <br/> |int  <br/> |발신자의 에코 반환 손실 향상 메트릭입니다. 이 메트릭의 단위는 dB입니다. 값이 낮으면 에코가 적습니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.  <br/> |
|CallerSpeakerGlitchRate  <br/> |int  <br/> |발신자 스피커 렌더링에 대한 5분당 평균 글리치입니다. 적정 품질을 위해서는 5분당 1 미만이어야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화에서 보고되지 않습니다.  <br/> |
|CallerMicGlitchRate  <br/> |int  <br/> |발신자 마이크 캡처에 대한 5분당 평균 글리치입니다. 적정 품질을 위해서는 5분당 1 미만이어야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화에서 보고되지 않습니다.  <br/> |
|CallerTimestampDriftRateMic  <br/> |decimal(9,2)  <br/> |CPU 클럭을 상대로 발신자 마이크 디바이스 클럭 드리프트 비율입니다.  <br/> |
|CallerTimestampDriftRateSpk  <br/> |decimal(9,2)  <br/> |CPU 클럭을 상대로 발신자 스피커 디바이스 클럭 드리프트 비율입니다.  <br/> |
|CallerTimestampErrorMicMs  <br/> |decimal(9,2)  <br/> |통화의 최근 20초 동안 발생한 평균 마이크 캡처 스트림 타임스탬프 오류(밀리초)입니다.  <br/> |
|CallerTimestampErrorSpkMs  <br/> |decimal(9,2)  <br/> |통화의 최근 20초 동안 발신자 스피커 렌더링 스트림 타임스탬프 오류의 평균(밀리초)입니다.  <br/> |
|CallerVsEntryCauses  <br/> |smallint  <br/> |음성 스위치는 중단 기능이 감소된 반이중 모드입니다. 자세한 내용은 [MediaLine 테이블을](medialine-0.md) 참조하세요. <br/> |
|CallerEchoEventCauses  <br/> |tinyint  <br/> |발신자의 에코 이벤트의 원인입니다. 자세한 내용은 [MediaLine 테이블을](medialine-0.md) 참조하세요. <br/> |
|CallerEchoPercentMicIn  <br/> |decimal(5,2)  <br/> |발신자 마이크 캡처 스트림에서 에코가 감지되는 시간의 백분율입니다. 헤드셋을 사용할 경우 값이 낮아집니다.  <br/> |
|CallerEchoPercentSend  <br/> |decimal(5,2)  <br/> |발신자 전송 스트림에서 에코가 감지되는 시간의 백분율입니다. 전송 스트림에서 에코 비율이 높으면 에코 누출을 나타낼 수 있습니다.  <br/> |
|CallerRxAGCSignalLevel  <br/> |int  <br/> |중재 서버에서 발신자 오디오 게이트웨이로부터 수신된 신호 수준 이는 중재 서버에만 적용됩니다. 이 메트릭의 단위는 dBoV입니다. 양질의 경우 허용되는 범위는 -30 ~-18 dBoV입니다.  <br/> |
|CallerRxAGCNoiseLevel  <br/> |int  <br/> |중재 서버에서 발신자 오디오 게이트웨이로부터 신호 수준을 수신했습니다. 중재 서버에만 적용됩니다. 이 메트릭의 단위는 dBoV입니다. 적정 품질을 위해 허용되는 범위는 -50 dBoV 미만입니다.  <br/> |
|CallerRxAGCGain  <br/> |int  <br/> |발신자 오디오에 적용된 중재 서버 쪽의 AGC(자동 게인 컨트롤)입니다.  <br/> |
|CallerInitialSignalLevelRMS  <br/> |float  <br/> |통화 초반의 최대 30초 동안 발신자에게 수신되는 신호의 RMS(제곱 평균 오차)입니다.  <br/> |
|CalleeSendSignalLevel  <br/> |int  <br/> |수신자가 전송한 오디오의 포스트 아날로그 게인 컨트롤 오디오 신호 수준을 나타냅니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 최소 30 dBmo여야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.  <br/> |
|CalleeRecvSignalLevel  <br/> |int  <br/> |수신자가 수신한 오디오의 오디오 신호 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 최소 30 dBmo여야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.  <br/> |
|CalleeSendNoiseLevel  <br/> |int  <br/> |수신자가 전송한 오디오의 포스트 아날로그 게인 컨트롤 오디오 소음 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 35 dBmo 미만이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.  <br/> |
|CalleeRecvNoiseLevel  <br/> |int  <br/> |수신자가 수신한 오디오의 포스트 아날로그 게인 컨트롤 오디오 소음 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 35 dBmo 미만이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.  <br/> |
|CalleeEchoReturn  <br/> |int  <br/> |수신자의 에코 반환 손실 향상 메트릭입니다. 이 메트릭의 단위는 dB입니다. 값이 낮으면 에코가 적습니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.  <br/> |
|CalleeSpeakerGlitchRate  <br/> |int  <br/> |발신자 스피커 렌더링에 대한 5분당 평균 글리치입니다. 적정 품질을 위해서는 5분당 1 미만이어야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화에서 보고되지 않습니다.  <br/> |
|CalleeMicGlitchRate  <br/> |int  <br/> |발신자 마이크 캡처에 대한 5분당 평균 불투명도입니다. 적정 품질을 위해서는 5분당 1 미만이어야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화에서 보고되지 않습니다.  <br/> |
|CalleeTimestampDriftRateMic  <br/> |decimal(9,2)  <br/> |CPU 클럭을 상대로 하는 발신자 마이크 디바이스 클럭 드리프트 속도입니다.  <br/> |
|CalleeTimestampDriftRateSpk  <br/> |decimal(9,2)  <br/> |CPU 클럭을 상대로 하는 발신자 스피커 디바이스 클럭 드리프트 속도입니다.  <br/> |
|CalleeTimestampErrorMicMs  <br/> |decimal(9,2)  <br/> |통화의 최근 20초 동안 발생한 평균 마이크 캡처 스트림 타임스탬프 오류(밀리초)입니다.  <br/> |
|CalleeTimestampErrorSpkMs  <br/> |decimal(9,2)  <br/> |통화의 최근 20초 동안의 발신자 스피커 렌더링 스트림 타임스탬프 오류의 평균(밀리초)입니다.  <br/> |
|CalleeVsEntryCauses  <br/> |smallint  <br/> |음성 스위치는 중단 기능이 감소된 반이중 모드입니다. 자세한 내용은 [MediaLine 테이블을](medialine-0.md) 참조하세요. <br/> |
|CalleeEchoEventCauses  <br/> |tinyint  <br/> |수신자의 에코 이벤트의 원인입니다. 자세한 내용은 [MediaLine 테이블을](medialine-0.md) 참조하세요. <br/> |
|CalleeEchoPercentMicIn  <br/> |decimal(5,2)  <br/> |발신자 마이크 캡처 스트림에서 에코가 감지되는 시간의 백분율입니다. 헤드셋을 사용할 경우 값이 낮아집니다.  <br/> |
|CalleeEchoPercentSend  <br/> |decimal(5,2)  <br/> |발신자 전송 스트림에서 에코가 감지되는 시간의 백분율입니다. 전송 스트림에서 에코 비율이 높으면 에코 누출을 나타낼 수 있습니다.  <br/> |
|CalleeRxAGCSignalLevel  <br/> |int  <br/> |중재 서버에서 수신자 오디오 게이트웨이로부터 수신된 신호 수준 이는 중재 서버에만 적용됩니다. 이 메트릭의 단위는 dBoV입니다. 양질의 경우 허용되는 범위는 [-30 ~ -18] dBoV입니다.  <br/> |
|CalleeRxAGCNoiseLevel  <br/> |int  <br/> |중재 서버에서 수신자 오디오 게이트웨이로부터 신호 수준을 수신했습니다. 중재 서버에만 적용됩니다. 이 메트릭의 단위는 dBoV입니다. 적정 품질을 위해 허용되는 범위는 -50 dBoV 미만입니다.  <br/> |
|CalleeRxAGCGain  <br/> |int  <br/> |중재 서버 쪽의 AGC(자동 게인 컨트롤)는 발신자 오디오에 적용됩니다.  <br/> |
|CalleeInitialSignalLevelRMS  <br/> |float  <br/> |통화 초반의 최대 30초 동안 수신자에게 수신되는 신호의 RMS(제곱 평균 오차)입니다.  <br/> |
|RatioConcealedSamplesAvg  <br/> |decimal(5,2)  <br/> |일반 샘플에 대한 오디오 힐링으로 생성된 숨겨진 평균 샘플 비율입니다.  <br/> |
|RatioStretchedSamplesAvg  <br/> |decimal(5,2)  <br/> |일반 샘플에 대한 오디오 힐링으로 생성된 평균 늘임 샘플 비율입니다.  <br/> |
|RatioCompressedSamplesAvg  <br/> |decimal(5,2)  <br/> |일반 샘플에 대한 오디오 힐링으로 생성된 숨겨진 압축 샘플 비율입니다.  <br/> |
|RoundTrip  <br/> |int  <br/> |RTCP 통계로부터의 왕복 시간입니다.  <br/> |
|RoundTripMax  <br/> |int  <br/> |오디오 스트림에 대한 최대 왕복 시간입니다.  <br/> |
|OverallAvgNetworkMOS  <br/> |decimal(3,2)  <br/> |통화에 대한 평균 광대역 네트워크 MOS입니다. 이 메트릭은 패킷 손실, 지터 및 사용된 코덱에 따라 달라집니다. 범위는 1.0 ~ 5.0입니다.  <br/> |
|OverallMinNetworkMOS  <br/> |decimal(3,2)  <br/> |통화에 대한 최소 광대역 네트워크 MOS입니다.  <br/> |
|SendListenMOS  <br/> |decimal(3,2)  <br/> |음성 수준, 잡음 수준 및 캡처 장치 특성을 포함하여 전송된 오디오에 대한 평균 예측 광대역 청취 MOS 점수입니다.  <br/> |
|SendListenMOSMin  <br/> |decimal(3,2)  <br/> |통화에 대한 최소 SendListenMOS입니다.  <br/> |
|RecvListenMOS  <br/> |decimal(3,2)  <br/> |음성 수준, 잡음 수준, 코덱, 네트워크 조건 및 캡처 장치 특성을 포함하여 수신된 오디오에 대한 평균 예측 광대역 청취 MOS 점수입니다.  <br/> |
|RecvListenMOSMin  <br/> |decimal(3,2)  <br/> |통화에 대한 최소 RecvListenMOS입니다.  <br/> |
|AudioFECUsed  <br/> |bit  <br/> |통화에 오디오 FEC가 사용되었는지 여부를 나타냅니다.  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |P-Asserted-Identity 정보의 방향을 나타냅니다. 1은 스트림 방향이 발신자에서 수신자의 방향임을 의미하고, 0은 스트림 방향이 수신자에서 발신자의 방향임을 의미합니다.  <br/> |
   

