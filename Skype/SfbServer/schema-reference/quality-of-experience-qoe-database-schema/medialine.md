---
title: MediaLine
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
ms.assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
description: MediaLine는 데이터베이스의 각 미디어 라인에 대 한 정보를 저장 합니다. 일반적으로 하나의 오디오 세션에 오디오 미디어 선이 하나 있습니다. 하나의 오디오 및 비디오 (A/V) 세션에는 일반적으로 오디오 미디어 회선 하 나와 비디오 미디어 라인 하나가 포함 됩니다. 그러나 회의 장치를 사용 하거나 갤러리 보기를 사용 하는 경우에는 세션에 두 개의 비디오 미디어 줄이 포함 될 수 있습니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: b22408ddc40f1df6452895327e8a67800ef24eb9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41808196"
---
# <a name="medialine-view"></a>MediaLine
 
MediaLine는 데이터베이스의 각 미디어 라인에 대 한 정보를 저장 합니다. 일반적으로 하나의 오디오 세션에 오디오 미디어 선이 하나 있습니다. 하나의 오디오 및 비디오 (A/V) 세션에는 일반적으로 오디오 미디어 회선 하 나와 비디오 미디어 라인 하나가 포함 됩니다. 그러나 회의 장치를 사용 하거나 갤러리 보기를 사용 하는 경우에는 세션에 두 개의 비디오 미디어 줄이 포함 될 수 있습니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
  
|**열**|**데이터 형식**|**세부적인**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |dmtf  <br/> |[Medialine 테이블](medialine-0.md)에서 참조 합니다.  <br/> |
|SessionSeq  <br/> |int  <br/> |[Medialine 테이블](medialine-0.md)에서 참조 합니다.  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |[Medialine 테이블](medialine-0.md)에서 참조 합니다.  <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |호출자의 bits 플래그에 설명 된 ICE (대화형 연결 설정) 프로세스에 대 한 정보입니다. 자세한 내용은 경험의 품질 모니터링 서버 프로토콜 사양을 참조 하세요.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |호출 수신자의 bits 플래그에 설명 된 ICE (대화형 연결 설정) 프로세스에 대 한 정보입니다. 자세한 내용은 경험의 품질 모니터링 서버 프로토콜 사양을 참조 하세요.  <br/> |
|보안  <br/> |tinyint  <br/> |사용 중인 보안 프로필 0은 없음, 1은 SRTP, 2는 V1입니다.  <br/> |
|운송  <br/> |tinyint  <br/> |전송 종류. 0은 UDP이 고, 1은 TCP입니다.  <br/> |
|CallerIPAddr  <br/> |var (50)  <br/> |발신자의 IP 주소입니다. IPv4 또는 IPv6 주소 중 하나가 될 수 있습니다.  <br/> |
|CallerPort  <br/> |int  <br/> |호출자가 사용 하는 포트입니다.  <br/> |
|CallerInside  <br/> |다소  <br/> |호출자가 조직 네트워크 내에 있는지 여부를 나타냅니다. 1은 호출자가 엔터프라이즈 네트워크 내에 있음을 의미 합니다. 0은 호출자가 네트워크 외부에 있음을 의미 합니다.  <br/> |
|CallerMacAddress  <br/> |varchar (256)  <br/> |발신자가 사용 하는 네트워크 인터페이스의 MAC 주소입니다.  <br/> |
|CallerRelayIPAddr  <br/> |var (50)  <br/> |발신자가 사용 하는 A/V Edge 서비스의 IP 주소입니다. 자세한 내용은 [IPAddress 테이블](ipaddress.md) 을 참조 하세요. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |호출자가 사용 하는 A/V Edge 서비스에 사용 되는 포트입니다.  <br/> |
|CallerReflexiveIPAddr  <br/> |var (50)  <br/> |A/V Edge 서비스에서 보고 한 발신자의 IP 주소입니다. 이 주소는 클라이언트가 NAT 뒤에 있는 경우 CallerIPAddr와 같은 경우에 발생할 수 있습니다.  <br/> |
|CallerCaptureDev  <br/> |varchar (256)  <br/> |발신자의 캡처 장치 이름입니다.  <br/> |
|CallerRenderDev  <br/> |varchar (256)  <br/> |발신자의 렌더링 장치 이름.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar (256)  <br/> |발신자의 캡처 장치 드라이버 이름.  <br/> |
|CallerRenderDevDriver  <br/> |varchar (256)  <br/> |호출자의 렌더링 장치 드라이버 이름입니다.  <br/> |
|CallerWifiDriverDeviceDesc  <br/> |varchar (256  <br/> |발신자의 Wifi 드라이버 설명.  <br/> |
|CallerWifiDriverVersion  <br/> |varchar (256)  <br/> |발신자의 Wifi 드라이버 버전.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar (256)  <br/> |호출자의 네트워크 연결에 대 한 세부 정보입니다. 자세한 내용은 [Networkconnectiondetail 테이블](networkconnectiondetail.md) 을 참조 하세요. <br/> |
|CallerBssid  <br/> |varchar (256)  <br/> |발신자 WiFi 연결에 사용 되는 기본 서비스 설정 식별자입니다.  <br/> |
|CallerVPN  <br/> |다소  <br/> |호출자가 가상 개인 네트워크를 통해 연결 되었는지 여부를 나타냅니다. 1은 VPN (가상 사설망)이 고 0은 VPN이 아닙니다.  <br/> |
|CalleeIPAddr  <br/> |var (50)  <br/> |호출 수신자의 IP 주소입니다. IPv4 또는 IPv6 주소 중 하나가 될 수 있습니다.  <br/> |
|CalleePort  <br/> |int  <br/> |호출 수신자가 사용 하는 포트입니다.  <br/> |
|CalleeInside  <br/> |다소  <br/> |호출 수신자가 엔터프라이즈 네트워크 내에 있는지 여부를 나타냅니다. 1은 호출 수신자가 엔터프라이즈 네트워크 내에 있음을 의미 하 고 0은 호출 수신자가 네트워크 외부에 있음을 의미 합니다.  <br/> |
|CalleeMacAddress  <br/> |varchar (256)  <br/> |호출 수신자가 사용 하는 네트워크 인터페이스의 MAC 주소입니다.  <br/> |
|CalleeRelayIPAddr  <br/> |var (50)  <br/> |호출 수신자가 사용 하는 A/V Edge 서비스의 IP 주소입니다. 자세한 내용은 [IPAddress 테이블](ipaddress.md) 을 참조 하세요. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |호출 수신자가 사용 하는 A/V Edge 서비스에 사용 되는 포트입니다.  <br/> |
|Callere| Iveipaddr  <br/> |var (50)  <br/> |A/V Edge 서비스에서 보고 한 호출 수신자의 IP 주소입니다. 이 주소는 클라이언트가 NAT 뒤에 있는 경우 CalleeIPAddr와 같이 다를 수 있습니다.  <br/> |
|CalleeCaptureDev  <br/> |var (50)  <br/> |호출 수신자의 캡처 디바이스 이름입니다.  <br/> |
|CalleeRenderDev  <br/> |varchar (256)  <br/> |피호출자의 렌더링 디바이스 이름입니다.  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar (256)  <br/> |피호출자의 캡처 장치 드라이버 이름입니다.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar (256)  <br/> |피호출자의 렌더링 장치 드라이버 이름입니다.  <br/> |
|CalleeWifiDriverDeviceDesc  <br/> |varchar (256)  <br/> |호출 수신자의 Wifi 드라이버 설명입니다.  <br/> |
|CalleeWifiDriverVersion  <br/> |varchar (256  <br/> |피호출자의 Wifi 드라이버 버전.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar (256)  <br/> |호출 수신자의 네트워크 연결에 대 한 세부 정보입니다. 자세한 내용은 [Networkconnectiondetail 테이블](networkconnectiondetail.md) 을 참조 하세요. <br/> |
|CalleeBssid  <br/> |varchar (256)  <br/> |피호출자의 WiFi 연결에 사용 되는 기본 서비스 집합 식별자입니다.  <br/> |
|CalleeVPN  <br/> |다소  <br/> |호출 수신자가 가상 개인 네트워크를 통해 연결 되었는지 여부를 나타냅니다. 1은 VPN (가상 사설망)이 고 0은 VPN이 아닙니다.  <br/> |
|ConversationalMOS  <br/> |10 진수 (3, 2)  <br/> |오디오 세션의 Narrowband 대화 SPECIALIST (두 오디오 스트림 모두 기준).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |다양 한 정책 설정 (TURN, API, SDP, 정책 서버 등)을 지정 하 여 지정 된 보내기 쪽 스트림에 실제 대역폭을 적용 한 것입니다. 대역폭 예측을 기준으로 낮은 유효 대역폭을 사용할 수 있기 때문에 효과적인 대역폭과 혼동 해서는 안 됩니다. 이 값이 기본적으로 최대 대역폭입니다. 송신 스트림은 대역폭 추정치에 의해 부과 된 제한을 받을 수 있습니다.  <br/> |
|AppliedBandwidthSource  <br/> |varchar (256)  <br/> |적용 되는 대역폭 캡의 원본입니다. 대역폭 한도가 시작 되는 위치를 설명 합니다 (예: "정책 서버", "서버 설정" 또는 "모달").  <br/> |
|호출인  <br/> |다소  <br/> |호출자의 메트릭을 받았는지 여부를 나타냅니다. 1은 예, 0은 no입니다.  <br/> |
|피호출자  <br/> |다소  <br/> |통화 수신기의 메트릭을 받았는지 여부를 나타냅니다. 1은 예, 0은 no입니다.  <br/> |
|MidCallReport  <br/> |다소  <br/> |보고서가 통화 일부 인지 또는 전체 통화에 대 한 것인지를 나타냅니다.  <br/> |
|ClassifiedPoorCall  <br/> |다소  <br/> |통화가 불량 통화 (1) 또는 좋은 통화 (0)로 분류 되었는지 여부를 나타냅니다.  <br/> |
|CallerConnectivityICE  <br/> |tinyint  <br/> |발신자가 ICE 프로토콜 (인터넷 연결 설정)을 사용 하 여 네트워크에 연결 되었는지 여부를 나타냅니다.  <br/> |
|CalleeConnectivityICE  <br/> |tinyint  <br/> |사용자가 ICE 프로토콜 (인터넷 연결 설정)을 사용 하 여 네트워크에 연결 되어 있는지 여부를 나타냅니다.  <br/> |
   

