---
title: VideoStreamDetail 보기
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
ms.assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
description: VideoStreamDetail 보기에는 데이터베이스의 각 비디오 스트림에 대 한 정보가 저장 됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: 3fb598feec3b4dca87086504c620109a99bce7d0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804148"
---
# <a name="videostreamdetail-view"></a>VideoStreamDetail 보기
 
VideoStreamDetail 보기에는 데이터베이스의 각 비디오 스트림에 대 한 정보가 저장 됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
  
|**열**|**데이터 형식**|**설명**|
|:-----|:-----|:-----|
|SessionTime  <br/> |dmtf  <br/> |[Medialine 테이블](medialine-0.md)에서 참조 합니다.  <br/> |
|SessionSeq  <br/> |int  <br/> |[Medialine 테이블](medialine-0.md)에서 참조 합니다.  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |[Medialine 테이블](medialine-0.md)에서 참조 합니다.  <br/> |
|StreamId  <br/> |int  <br/> |미디어 라인 내의 고유 ID.  <br/> |
|StartTime  <br/> |dmtf  <br/> |세션 시작 시간입니다.  <br/> |
|EndTime  <br/> |dmtf  <br/> |세션 종료 시간입니다.  <br/> |
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
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |호출 수신자의 끝점에 대 한 CPU 코어 수입니다.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |호출자 끝점의 CPU 프로세서 속도입니다.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |호출 수신자의 끝점에 대 한 CPU 프로세서 속도입니다.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |호출자의 시스템이 가상화 된 환경에서 실행 중인지 여부를 나타냅니다. 자세한 내용은 [끝점 테이블](endpoint.md) 을 참조 하세요. <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |호출 수신자의 시스템이 가상화 된 환경에서 실행 중인지 여부를 나타냅니다. 자세한 내용은 [끝점 테이블](endpoint.md) 을 참조 하세요. <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |미디어 경로에 대 한 정보 (예: 직접 또는 릴레이)입니다. 자세한 내용은 [Medialine 테이블](medialine-0.md) 을 참조 하세요. <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |호출자의 bits 플래그에 설명 된 ICE (대화형 연결 설정) 프로세스에 대 한 정보입니다. 자세한 내용은 경험의 품질 모니터링 서버 프로토콜 사양을 참조 하세요.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |호출 수신자의 bits 플래그에 설명 된 ICE (대화형 연결 설정) 프로세스에 대 한 정보입니다. 자세한 내용은 경험의 품질 모니터링 서버 프로토콜 사양을 참조 하세요.  <br/> |
|운송  <br/> |int  <br/> |전송 종류: 0은 UDP이 고, 1은 TCP입니다.  <br/> |
|CallerIPAddr  <br/> |var (50)  <br/> |발신자의 IP 주소입니다. IPv4 또는 IPv6 주소 일 수 있습니다.  <br/> |
|CallerPort  <br/> |int  <br/> |호출자가 사용 하는 포트입니다.  <br/> |
|CallerInside  <br/> |다소  <br/> |호출자가 조직 네트워크 내에 있는지 여부를 나타냅니다. 1은 발신자가 엔터프라이즈 네트워크 내에 있음을 의미 하 고, 0 이면 발신자가 네트워크 외부에 있음을 의미 합니다.  <br/> |
|CalleeIPAddr  <br/> |var (50)  <br/> |호출 수신자의 IP 주소입니다. IPv4 또는 IPv6 주소 일 수 있습니다.  <br/> |
|CalleePort  <br/> |int  <br/> |호출 수신자가 사용 하는 포트입니다.  <br/> |
|CalleeInside  <br/> |다소  <br/> |호출자가 조직 네트워크 내에 있는지 여부를 나타냅니다. 1은 호출 수신자가 엔터프라이즈 네트워크 내에 있음을 의미 하 고 0은 호출 수신자가 네트워크 외부에 있음을 의미 합니다.  <br/> |
|CallerUserSite  <br/> |name  <br/> |호출자 사이트의 이름입니다.  <br/> |
|CallerRegion  <br/> |name  <br/> |발신자 사이트의 국가/지역 이름입니다.  <br/> |
|CalleeUserSite  <br/> |name  <br/> |피호출자 사이트의 이름입니다.  <br/> |
|CalleeRegion  <br/> |name  <br/> |피호출자 사이트의 국가/지역 이름입니다.  <br/> |
|CallerRelayIPAddr  <br/> |var (50)  <br/> |발신자가 사용 하는 A/V Edge 서비스의 IP 주소입니다. 자세한 내용은 [IPAddress 테이블](ipaddress.md) 을 참조 하세요. <br/> |
|CallerRelayPort  <br/> |int  <br/> |호출자가 사용 하는 A/V에 지 서비스의 포트입니다.  <br/> |
|CalleeRelayIPAddr  <br/> |var (50)  <br/> |호출 수신자가 사용 하는 A/V Edge 서비스의 IP 주소 키입니다. 자세한 내용은 [IPAddress 테이블](ipaddress.md) 을 참조 하세요. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |호출 수신자가 사용 하는 A/V에 지 서비스의 포트입니다.  <br/> |
|CallerCaptureDev  <br/> |varchar (256)  <br/> |발신자의 캡처 장치 이름입니다.  <br/> |
|CallerRenderDev  <br/> |varchar (256)  <br/> |발신자의 렌더링 장치 이름.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar (256)  <br/> |발신자의 캡처 장치 드라이버 이름.  <br/> |
|CallerRenderDevDriver  <br/> |varchar (256)  <br/> |호출자의 렌더링 장치 드라이버 이름입니다.  <br/> |
|CalleeCaptureDev  <br/> |varchar (256)  <br/> |호출 수신자의 캡처 디바이스 이름입니다.  <br/> |
|CalleeRenderDev  <br/> |varchar (256)  <br/> |피호출자의 렌더링 디바이스 이름입니다.  <br/> |
|CalleCaptureDevDriver  <br/> |varchar (256)  <br/> |피호출자의 캡처 장치 드라이버 이름입니다.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar (256)  <br/> |피호출자의 렌더링 장치 드라이버 이름입니다.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |발신자의 네트워크 연결 유형: 0이 유선 인 경우 1은 무선입니다.  <br/> |
|CallerVPN  <br/> |다소  <br/> |호출자가 가상 개인 네트워크를 통해 연결 되었는지 여부를 나타냅니다. 1은 VPN (가상 사설망)이 고 0은 VPN이 아닙니다.  <br/> |
|CallerLinkSpeed  <br/> |10 진수 (18,)  <br/> |Bps의 호출자 끝점에 대 한 네트워크 링크 속도입니다.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |피호출자의 네트워크 연결 형식: 0이 유선 인 경우 1은 무선입니다.  <br/> |
|CalleeVPN  <br/> |다소  <br/> |호출 수신자가 가상 개인 네트워크를 통해 연결 되었는지 여부를 나타냅니다. 1은 VPN (가상 사설망)이 고 0은 VPN이 아닙니다.  <br/> |
|CalleeLinkSpeed  <br/> |10 진수 (18, 0)  <br/> |호출 수신자의 끝점에 대 한 네트워크 링크 속도 (bps)입니다.  <br/> |
|ConversationalMOS  <br/> |10 진수 (3, 2)  <br/> |오디오 세션의 Narrowband 대화 SPECIALIST (두 오디오 스트림 모두 기준).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |다양 한 정책 설정 (TURN, API, SDP, 정책 서버 등)을 지정 하 여 지정 된 보내기 쪽 스트림에 실제 대역폭을 적용 했습니다. 대역폭 예측을 기준으로 낮은 유효 대역폭을 사용할 수 있기 때문에 효과적인 대역폭과 혼동 하지 않는 것이 좋습니다. 이 값이 기본적으로 최대 대역폭입니다. 송신 스트림은 대역폭 추정치에 의해 부과 된 제한을 받을 수 있습니다.  <br/> |
|JitterInterArrival  <br/> |int  <br/> |RTCP (실시간 제어 프로토콜) 통계의 평균 네트워크 지터입니다.  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |통화 중 최대 네트워크 지터.  <br/> |
|왕복이  <br/> |int  <br/> |RTCP 통계에서 왕복 시간을 계산 합니다.  <br/> |
|RoundTripMax  <br/> |int  <br/> |오디오 스트림의 최대 라운드트립 시간입니다.  <br/> |
|PacketLossRate  <br/> |10 진수 (5, 4)  <br/> |통화 중의 평균 패킷 손실 율입니다.  <br/> |
|PacketLossRateMax  <br/> |10 진수 (5, 4)  <br/> |통화 중에 최대 패킷 손실이 관찰 되었습니다.  <br/> |
|PacketUtilization  <br/> |int  <br/> |비디오 스트림의 패킷 개수 (리얼 시간 전송 프로토콜, RTP).  <br/> |
|BandwidthEst  <br/> |int  <br/> |오디오 스트림의 대역폭을 예측 합니다.  <br/> |
|PayloadDescription  <br/> |int  <br/> |[PayloadDescription 테이블](payloaddescription.md)에서 참조 되는 통화에 사용 되는 오디오 코덱입니다.  <br/> |
|VideoResolution  <br/> |char (9)  <br/> |픽셀 너비를 픽셀 높이로 곱한 비디오 해상도입니다. 문자열로 보고 되었습니다.  <br/> |
|VideoBitRateAvg  <br/> |int  <br/> |비디오 스트림의 평균 비트 전송률입니다.  <br/> |
|InboundVideoFrameRateAvg  <br/> |10 진수 (9, 4)  <br/> |수신 된 비디오의 프레임 속도입니다.  <br/> |
|OutboundVideoFrameRateAvg  <br/> |10 진수 (9, 4)  <br/> |전송 된 비디오의 프레임 속도입니다.  <br/> |
|ViideoBitRateMax  <br/> |int  <br/> |비디오 세션 중에 최대 비디오 비트 전송률입니다.  <br/> |
|VideoPacketLossRate  <br/> |10 진수 (9, 4)  <br/> |비디오 패킷이 손실 된 속도입니다.  <br/> |
|VideoFrameLossRate  <br/> |10 진수 (9.4)  <br/> |손실 된 총 비디오 프레임의 백분율입니다.  <br/> |
|VideoFEC  <br/> |다소  <br/> |사용 되지 않습니다.  <br/> |
|VideoAllocateBWAvg  <br/> |int  <br/> |비디오에 대해 할당 된 평균 대역폭 양입니다.  <br/> |
|VideoLocalFrameLossPercentageAvg  <br/> |10 진수 (9.4)  <br/> |손실 된 총 비디오 프레임의 백분율입니다.  <br/> |
|SenderIsCallerPAI  <br/> |다소  <br/> |P-어설션된 id 정보에 대 한 스트림 방향입니다. 1은 스트림 방향이 호출자에서 호출 수신자 까지의 것임을 의미 합니다. 0은 스트림 방향이 피호출자부터 호출자에 게 있음을 의미 합니다.  <br/> |
   

