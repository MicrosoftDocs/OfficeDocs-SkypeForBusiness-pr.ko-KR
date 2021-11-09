---
title: VideoStreamDetail 보기
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
ms.assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
description: VideoStreamDetail 보기는 데이터베이스에 각 비디오 스트림에 대한 정보를 저장합니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
ms.openlocfilehash: 38f97d5cd97d6a92961a377129cb533fd96ccd6d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863235"
---
# <a name="videostreamdetail-view"></a>VideoStreamDetail 보기
 
VideoStreamDetail 보기는 데이터베이스에 각 비디오 스트림에 대한 정보를 저장합니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
  
|**열**|**데이터 형식**|**설명**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |[MediaLine 테이블에서 참조됩니다.](medialine-0.md)  <br/> |
|SessionSeq  <br/> |int  <br/> |[MediaLine 테이블에서 참조됩니다.](medialine-0.md)  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |[MediaLine 테이블에서 참조됩니다.](medialine-0.md)  <br/> |
|StreamId  <br/> |int  <br/> |미디어 회선 내의 고유 ID입니다.  <br/> |
|StartTime  <br/> |datetime  <br/> |세션 시작 시간입니다.  <br/> |
|EndTime  <br/> |datetime  <br/> |세션 종료 시간입니다.  <br/> |
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
|ConnectivityIce  <br/> |tinyint  <br/> |직접 또는 중계와 같은 미디어 경로에 대한 정보입니다. 자세한 내용은 [MediaLine 테이블을](medialine-0.md) 참조하세요. <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |비트 플래그로 설명된 발신자 측 ICE(Interactive Connectivity Establishment) 프로세스에 대한 정보입니다. 자세한 내용은 체감 품질 모니터링 서버 프로토콜 사양을 참조하십시오.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |비트 플래그로 설명된 수신자 측 ICE(Interactive Connectivity Establishment) 프로세스에 대한 대한 정보입니다. 자세한 내용은 체감 품질 모니터링 서버 프로토콜 사양을 참조하십시오.  <br/> |
|전송  <br/> |int  <br/> |전송 종류: 0은 UDP, 1은 TCP입니다.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |발신자의 IP 주소입니다. 이 주소는 IPv4 또는 IPv6 주소일 수 있습니다.  <br/> |
|CallerPort  <br/> |int  <br/> |발신자가 사용하는 포트입니다.  <br/> |
|CallerInside  <br/> |bit  <br/> |발신자가 조직 네트워크 내부에 있는지 여부를 나타냅니다. 1은 발신자가 회사 네트워크 내에 있음을 의미하고 0은 발신자가 네트워크 외부에 있음을 의미합니다.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |수신자의 IP 주소입니다. 이 주소는 IPv4 또는 IPv6 주소일 수 있습니다.  <br/> |
|CalleePort  <br/> |int  <br/> |수신자가 사용하는 포트입니다.  <br/> |
|CalleeInside  <br/> |bit  <br/> |수신자가 조직 네트워크 내부에 있는지 여부를 나타냅니다. 1은 발신자가 회사 네트워크 내에 있음을 의미하고 0은 발신자가 네트워크 외부에 있음을 의미합니다.  <br/> |
|CallerUserSite  <br/> |nvarchar(128)  <br/> |발신자 사이트의 이름입니다.  <br/> |
|CallerRegion  <br/> |nvarchar(128)  <br/> |발신자 사이트의 국가/지역 이름입니다.  <br/> |
|CalleeUserSite  <br/> |nvarchar(128)  <br/> |발신자 사이트의 이름입니다.  <br/> |
|CalleeRegion  <br/> |nvarchar(128)  <br/> |발신자 사이트의 국가/지역 이름입니다.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |A/V 에지 서비스에서 발신자가 사용하는 IP 주소입니다. 자세한 내용은 [IPAddress 테이블을](ipaddress.md) 참조하세요. <br/> |
|CallerRelayPort  <br/> |int  <br/> |A/V 에지 서비스에서 발신자가 사용하는 포트입니다.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |A/V 에지 서비스에서 수신자가 사용하는 IP 주소 키입니다. 자세한 내용은 [IPAddress 테이블을](ipaddress.md) 참조하세요. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |A/V 에지 서비스에서 수신자가 사용하는 포트입니다.  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |발신자 캡처 장치 이름입니다.  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |발신자 렌더링 장치 이름입니다.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |발신자 캡처 장치 드라이버 이름입니다.  <br/> |
|CallerRenderDevDriver  <br/> |varchar(256)  <br/> |발신자 렌더링 장치 드라이버 이름입니다.  <br/> |
|CalleeCaptureDev  <br/> |varchar(256)  <br/> |발신자 캡처 장치 이름입니다.  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |발신자 렌더링 장치 이름입니다.  <br/> |
|CalleCaptureDevDriver  <br/> |varchar(256)  <br/> |발신자 캡처 장치 드라이버 이름입니다.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |발신자 렌더링 장치 드라이버 이름입니다.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |발신자 네트워크 연결 유형: 0은 유선, 1은 무선입니다.  <br/> |
|CallerVPN  <br/> |bit  <br/> |발신자가 VPN(가상 사설망)을 통해 연결되었는지 여부를 나타냅니다. 1은 VPN(가상 사설망), 0은 비VPN입니다.  <br/> |
|CallerLinkSpeed  <br/> |decimal(18,)  <br/> |발신자의 끝점에 대한 네트워크 연결 속도(bps)입니다.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |발신자 네트워크 연결 유형: 0은 유선, 1은 무선입니다.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |수신자가 VPN(가상 사설망)을 통해 연결되었는지 여부를 나타냅니다. 1은 VPN(가상 사설망), 0은 비VPN입니다.  <br/> |
|CalleeLinkSpeed  <br/> |decimal(18,0)  <br/> |발신자 끝점의 네트워크 연결 속도(bps)입니다.  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |오디오 세션의 협대역 대화 MOS입니다(두 오디오 스트림을 모두 기반으로 함).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |다양한 정책 설정(TURN, API, SDP, 정책 서버 등)이 제공된 지정된 송신측 스트림에 적용되는 실제 대역폭입니다. 이 대역폭은 대역폭 예상에 따라 유효 대역폭이 더 낮을 수 있으므로 유효 대역폭과 혼동해서는 안됩니다. 이 대역폭은 기본적으로 대역폭 예상치로 지정된 한도를 제외하고 송신 스트림이 사용할 수 있는 최대 대역폭입니다.  <br/> |
|JitterInterArrival  <br/> |int  <br/> |RTCP(Real Time Control Protocol) 통계로부터 가져온 평균 네트워크 지터입니다.  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |통화 중 최대 네트워크 지터입니다.  <br/> |
|RoundTrip  <br/> |int  <br/> |RTCP 통계로부터의 왕복 시간입니다.  <br/> |
|RoundTripMax  <br/> |int  <br/> |오디오 스트림에 대한 최대 왕복 시간입니다.  <br/> |
|PacketLossRate  <br/> |decimal(5,4)  <br/> |통화 중 평균 패킷 손실 비율입니다.  <br/> |
|PacketLossRateMax  <br/> |decimal(5,4)  <br/> |통화 중 관측된 최대 패킷 손실입니다.  <br/> |
|PacketUtilization  <br/> |int  <br/> |비디오 스트림에 대한 패킷 수입니다(실시간 전송 프로토콜, RTP).  <br/> |
|BandwidthEst  <br/> |int  <br/> |오디오 스트림에 대한 대역폭 예상치입니다.  <br/> |
|PayloadDescription  <br/> |int  <br/> |통화에 사용되는 오디오 코덱으로, [PayloadDescription](payloaddescription.md)테이블에서 참조됩니다.  <br/> |
|VideoResolution  <br/> |char(9)  <br/> |픽셀 너비와 픽셀 높이를 곱한 수치의 비디오 해상도입니다. 문자열로 보고됩니다.  <br/> |
|VideoBitRateAvg  <br/> |int  <br/> |비디오 스트림의 평균 비트 전송률입니다.  <br/> |
|InboundVideoFrameRateAvg  <br/> |decimal(9,4)  <br/> |수신된 비디오의 프레임 속도입니다.  <br/> |
|OutboundVideoFrameRateAvg  <br/> |decimal(9,4)  <br/> |전송된 비디오의 프레임 속도입니다.  <br/> |
|ViideoBitRateMax  <br/> |int  <br/> |비디오 세션 중의 최대 비디오 비트 전송률입니다.  <br/> |
|VideoPacketLossRate  <br/> |decimal(9,4)  <br/> |비디오 패킷이 손실된 비율입니다.  <br/> |
|VideoFrameLossRate  <br/> |decimal(9.4)  <br/> |총 비디오 프레임 중 손실된 백분율입니다.  <br/> |
|VideoFEC  <br/> |bit  <br/> |사용되지 않습니다.  <br/> |
|VideoAllocateBWAvg  <br/> |int  <br/> |비디오에 할당된 평균 대역폭 양입니다.  <br/> |
|VideoLocalFrameLossPercentageAvg  <br/> |decimal(9.4)  <br/> |총 비디오 프레임 중 손실된 백분율입니다.  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |p-어설션된 ID 정보에 대한 스트림 방향입니다. 1은 발신자에서 수신자로 방향이며, 0은 수신자에서 발신자로 방향입니다.  <br/> |
   

