---
title: MediaLine 보기
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
description: 미디어 회선 보기에는 데이터베이스의 각 미디어 회선에 대한 정보가 저장됩니다. 하나의 오디오 세션은 일반적으로 오디오 미디어 회선 하나를 포함합니다. 하나의 A/V(오디오 및 비디오) 세션은 보통 오디오 미디어 회선과 비디오 미디어 회선을 하나씩 포함하지만, 회의 장치나 갤러리 보기를 사용하는 경우에는 세션이 비디오 미디어 회선 두 개를 포함할 수 있습니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
ms.openlocfilehash: 8ef825fd75fc4cf61f0416b5ce2b64ca9f58634c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62417421"
---
# <a name="medialine-view"></a>MediaLine 보기
 
미디어 회선 보기에는 데이터베이스의 각 미디어 회선에 대한 정보가 저장됩니다. 하나의 오디오 세션은 일반적으로 오디오 미디어 회선 하나를 포함합니다. 하나의 A/V(오디오 및 비디오) 세션은 보통 오디오 미디어 회선과 비디오 미디어 회선을 하나씩 포함하지만, 회의 장치나 갤러리 보기를 사용하는 경우에는 세션이 비디오 미디어 회선 두 개를 포함할 수 있습니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
  
|**열**|**데이터 형식**|**details**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |[MediaLine 테이블에서 참조됩니다](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |[MediaLine 테이블에서 참조됩니다](medialine-0.md).  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |[MediaLine 테이블에서 참조됩니다](medialine-0.md).  <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |비트 플래그로 설명된 발신자 측 ICE(Interactive Connectivity Establishment) 프로세스에 대한 정보입니다. 자세한 내용은 체감 품질 모니터링 서버 프로토콜 사양을 참조하십시오.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |수신자에 대해 비트 플래그로 설명되는 ICE(Interactive Connectivity Establishment) 프로세스에 대한 정보입니다. 자세한 내용은 체감 품질 모니터링 서버 프로토콜 사양을 참조하십시오.  <br/> |
|보안  <br/> |tinyint  <br/> |사용 중인 보안 프로필입니다. 0은 NONE, 1은 SRTP, 2는 V1입니다.  <br/> |
|전송  <br/> |tinyint  <br/> |전송 유형입니다. 0은 UDP, 1은 TCP입니다.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |발신자의 IP 주소입니다. IPv4 또는 IPv6 주소일 수 있습니다.  <br/> |
|CallerPort  <br/> |int  <br/> |발신자가 사용하는 포트입니다.  <br/> |
|CallerInside  <br/> |bit  <br/> |발신자가 조직 네트워크 내부에 있는지 여부를 나타냅니다. 값이 1이면 발신자가 엔터프라이즈 네트워크 내부에 있는 것입니다. 값이 0이면 발신자가 네트워크 외부에 있는 것입니다.  <br/> |
|CallerMacAddress  <br/> |varchar(256)  <br/> |발신자가 사용하는 네트워크 인터페이스의 MAC 주소입니다.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |A/V 에지 서비스에서 발신자가 사용하는 IP 주소입니다. 자세한 내용은 [IPAddress 테이블](ipaddress.md) 을 참조하세요. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |A/V 에지 서비스에서 발신자가 사용하는 포트입니다.  <br/> |
|CallerReflexiveIPAddr  <br/> |var(50)  <br/> |A/V 에지 서비스에서 보고한 발신자 IP 주소입니다. 클라이언트에 NAT가 적용되는 등의 경우 이 주소는 CallerIPAddr과 다를 수 있습니다.  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |발신자 캡처 장치 이름입니다.  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |발신자 렌더링 장치 이름입니다.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |발신자 캡처 장치 드라이버 이름입니다.  <br/> |
|CallerRenderDevDriver  <br/> |varchar(256)  <br/> |발신자 렌더링 장치 드라이버 이름입니다.  <br/> |
|CallerWifiDriverDeviceDesc  <br/> |varchar(256)  <br/> |발신자 Wi-Fi 드라이버 설명입니다.  <br/> |
|CallerWifiDriverVersion  <br/> |varchar(256)  <br/> |발신자 Wi-Fi 드라이버 버전입니다.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar(256)  <br/> |발신자 네트워크 연결에 대한 세부 정보입니다. 자세한 내용은 [NetworkConnectionDetail 테이블](networkconnectiondetail.md) 을 참조하세요. <br/> |
|CallerBssid  <br/> |varchar(256)  <br/> |발신자 Wi-Fi 연결에 사용되는 기본 서비스 집합 식별자입니다.  <br/> |
|CallerVPN  <br/> |bit  <br/> |발신자가 가상 사설망을 통해 연결했는지 여부를 나타냅니다. 1은 VPN(가상 사설망), 0은 비 VPN입니다.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |수신자의 IP 주소입니다. IPv4 또는 IPv6 주소일 수 있습니다.  <br/> |
|CalleePort  <br/> |int  <br/> |수신자가 사용하는 포트입니다.  <br/> |
|CalleeInside  <br/> |bit  <br/> |수신자가 엔터프라이즈 네트워크 내부에 있는지 여부를 나타냅니다. 값이 1이면 수신자가 엔터프라이즈 네트워크 내부에 있는 것입니다. 값이 0이면 수신자가 네트워크 외부에 있는 것입니다.  <br/> |
|CalleeMacAddress  <br/> |varchar(256)  <br/> |수신자가 사용하는 네트워크 인터페이스의 MAC 주소입니다.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |수신자가 사용하는 A/V 에지 서비스의 IP 주소입니다. 자세한 내용은 [IPAddress 테이블](ipaddress.md) 을 참조하세요. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |A/V 에지 서비스에서 수신자가 사용하는 포트입니다.  <br/> |
|CalleeReflexiveIPAddr  <br/> |var(50)  <br/> |A/V 에지 서비스에서 보고한 발신자 IP 주소입니다. 클라이언트에 NAT가 적용되는 등의 경우 이 주소는 CalleeIPAddr과 다를 수 있습니다.  <br/> |
|CalleeCaptureDev  <br/> |var(50)  <br/> |발신자 캡처 장치 이름입니다.  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |발신자 렌더링 장치 이름입니다.  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar(256)  <br/> |발신자 캡처 장치 드라이버 이름입니다.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |발신자 렌더링 장치 드라이버 이름입니다.  <br/> |
|CalleeWifiDriverDeviceDesc  <br/> |varchar(256)  <br/> |발신자 Wi-Fi 드라이버 설명입니다.  <br/> |
|CalleeWifiDriverVersion  <br/> |varchar(256)  <br/> |발신자 Wi-Fi 드라이버 버전입니다.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar(256)  <br/> |발신자 네트워크 연결에 대한 세부 정보입니다. 자세한 내용은 [NetworkConnectionDetail 테이블](networkconnectiondetail.md) 을 참조하세요. <br/> |
|CalleeBssid  <br/> |varchar(256)  <br/> |발신자 Wi-Fi 연결에 사용되는 기본 서비스 집합 식별자입니다.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |수신자가 가상 사설망을 통해 연결했는지 여부를 나타냅니다. 1은 VPN(가상 사설망), 0은 비 VPN입니다.  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |오디오 세션의 협대역 대화 MOS입니다(두 오디오 스트림을 모두 기반으로 함).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |다양한 정책 설정(TURN, API, SDP, 정책 서버 등)이 제공된 지정된 송신 쪽 스트림에 적용되는 실제 대역폭입니다. 대역폭 예상치에 따라 유효 대역폭은 더 낮을 수 있으므로 이 대역폭을 유효 대역폭과 혼동해서는 안 됩니다. 이 대역폭은 기본적으로 대역폭 예상치로 지정된 한도를 제외하고 송신 스트림이 사용할 수 있는 최대 대역폭입니다.  <br/> |
|AppliedBandwidthSource  <br/> |varchar(256)  <br/> |적용 중인 대역폭의 원본입니다. 대역폭 제한이 시작되는 위치(예: "정책 서버", "TURN Server" 또는 "Modality")를 설명합니다.  <br/> |
|발신자  <br/> |bit  <br/> |발신자의 메트릭이 수신되었는지 여부를 나타냅니다. 1은 예, 0은 아니요입니다.  <br/> |
|발신자  <br/> |bit  <br/> |통화 수신자의 메트릭이 수신되었는지 여부를 나타냅니다. 1은 예, 0은 아니요입니다.  <br/> |
|MidCallReport  <br/> |bit  <br/> |보고서가 통화의 일부분에 대한 것인지 전체 통화에 대한 것인지를 나타냅니다.  <br/> |
|ClassifiedPoorCall  <br/> |bit  <br/> |통화가 불량 통화(1)로 분류되었는지 양호한 통화(0)로 분류되었는지를 나타냅니다.  <br/> |
|CallerConnectivityICE  <br/> |tinyint  <br/> |발신자가 ICE(Internet Connectivity Establishment) 프로토콜을 사용하여 네트워크에 연결했는지 여부를 나타냅니다.  <br/> |
|CalleeConnectivityICE  <br/> |tinyint  <br/> |전화를 건 사용자가 ICE(Internet Connectivity Establishment) 프로토콜을 사용하여 네트워크에 연결했는지 여부를 나타냅니다.  <br/> |
   

