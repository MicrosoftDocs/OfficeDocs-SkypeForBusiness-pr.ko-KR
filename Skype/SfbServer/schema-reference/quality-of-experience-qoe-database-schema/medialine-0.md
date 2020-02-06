---
title: MediaLine 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
description: 각 레코드는 하나의 미디어 회선을 나타냅니다. (하나의 오디오 세션에는 일반적으로 하나의 오디오 미디어 회선이 있습니다. 회의 장치를 사용 하는 경우 또는 갤러리 보기를 사용 하는 경우 한 오디오 및 비디오 (A/V) 세션에는 일반적으로 하나의 오디오 미디어 회선 및 비디오 미디어 회선이 포함 되지만, 세션에는 두 개의 비디오 미디어 줄이 포함 될 수 있습니다.
ms.openlocfilehash: 0c189a79a9d87e76ec48be1acb7b4062876b5b16
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41808816"
---
# <a name="medialine-table"></a>MediaLine 테이블
 
각 레코드는 하나의 미디어 회선을 나타냅니다. (하나의 오디오 세션에는 일반적으로 하나의 오디오 미디어 회선이 있습니다. 회의 장치를 사용 하는 경우 또는 갤러리 보기를 사용 하는 경우 한 오디오 및 비디오 (A/V) 세션에는 일반적으로 하나의 오디오 미디어 회선 및 비디오 미디어 회선이 포함 되지만, 세션에는 두 개의 비디오 미디어 줄이 포함 될 수 있습니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |dmtf  <br/> |주요한  <br/> |[세션 테이블](session.md)에서 참조 됩니다.  <br/> |
|**SessionSeq** <br/> |int  <br/> |주요한  <br/> |[세션 테이블](session.md)에서 참조 됩니다.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |주요한  <br/> |0은 기본 오디오, 1은 기본 비디오, 2는 파노라마 비디오, 3은 응용 프로그램/데스크톱 공유 이며, 16은 비디오 기반 화면 공유 (VbSS)입니다. 이 레이블은 단일 세션 내에서 고유 해야 합니다.  <br/> |
|**ConnectivityIce** <br/> |tinyint  <br/> | <br/> |이 열은 현재 있지만 Microsoft Lync Server 2013에서 사용 되지 않습니다. 미디어 줄에 사용 되는 연결에 대 한 정보는 CallerConnectivityICE 및 CalleeConnectivityICE 열에 캡처됩니다.  <br/> |
|**CallerIceWarningFlags** <br/> |int  <br/> | <br/> |Bits 플래그에 설명 된 ICE (대화형 연결 설정) 프로세스에 대 한 정보입니다. 자세한 내용은 다운로드 가능한 *경험 치 모니터링 서버 프로토콜 사양을* 참조 하세요. <br/> |
|**CalleeIceWarningFlags** <br/> |int  <br/> | <br/> |CallerIceWarningFlags와 동일 하지만 호출 수신자 측에 있습니다. 자세한 내용은 다운로드 가능한 *경험 치 모니터링 서버 프로토콜 사양을* 참조 하세요. <br/> |
|**보안** <br/> |tinyint  <br/> | <br/> |사용 중인 보안 프로필입니다. 0은 없음, 1은 SRTP, 2는 V1입니다.  <br/> |
|**운송** <br/> |tinyint  <br/> | <br/> |0은 UDP이 고, 1은 TCP입니다.  <br/> |
|**CallerIPAddr** <br/> |int  <br/> |외부  <br/> |발신자의 IP 주소입니다. 자세한 내용은 [IPAddress 테이블](ipaddress.md) 을 참조 하세요. <br/> |
|**CallerPort** <br/> |int  <br/> | <br/> | 호출자가 사용 하는 포트입니다. <br/> |
|**CallerSubnet** <br/> |int  <br/> | 외부 <br/> |호출자의 서브넷입니다. 자세한 내용은 [IPAddress 테이블](ipaddress.md) 을 참조 하세요. <br/> |
|**CallerInside** <br/> |다소  <br/> | <br/> |1은 발신자가 엔터프라이즈 네트워크 내에 있음을 의미 하 고, 0 이면 발신자가 네트워크 외부에 있음을 의미 합니다.  <br/> |
|**CallerMacAddress** <br/> |int  <br/> |외부  <br/> |전화 및이 [테이블](macaddress.md)에서 참조 하는 발신자의 mac 주소입니다.  <br/> |
|**CallerRelayIPAddr** <br/> |int  <br/> |외부  <br/> |발신자가 사용 하는 A/V Edge 서비스의 IP 주소입니다. 자세한 내용은 [IPAddress 테이블](ipaddress.md) 을 참조 하세요. <br/> |
|**CallerRelayPort** <br/> |int  <br/> | <br/> |발신자에의 한 A/V Edge 서비스에 사용 되는 포트입니다.  <br/> |
|**CallerCaptureDev** <br/> |int  <br/> |외부  <br/> |호출자가 사용 하는 캡처 장치입니다. [장치 테이블](device.md)에서 참조 됩니다.  <br/> |
|**CallerRenderDev** <br/> |int  <br/> |외부  <br/> |발신자에 사용 된 장치를 렌더링 합니다. [장치 테이블](device.md)에서 참조 됩니다.  <br/> |
|**CallerCaptureDevDriver** <br/> |int  <br/> |외부  <br/> |[Devicedriver 테이블](devicedriver.md)에서 참조 되는 호출자 캡처 장치용 드라이버입니다.  <br/> |
|**CallerRenderDevDriver** <br/> |int  <br/> |외부  <br/> |[Devicedriver 테이블](devicedriver.md)에서 참조 되는 발신자의 렌더 디바이스 드라이버입니다.  <br/> |
|**CallerNetworkConnectionType** <br/> |tinyint  <br/> |외부  <br/> |발신자가 네트워크에 연결 되는 방법을 나타냅니다. 값은 [Networkconnectiondetail 테이블](networkconnectiondetail.md)에서 가져옵니다. WiFi 연결에 대 한 유선 연결의 경우 일반적으로 값은 0이 고, 그렇지 않으면-1입니다. 이더넷 연결의 경우 3.  <br/> |
|**CallerBssid** <br/> |int  <br/> |외부  <br/> |무선이 사용 되는 경우 발신자의 BSSID입니다. 로이 [테이블](macaddress.md)에서 참조 됩니다.  <br/> |
|**CallerVPN** <br/> |다소  <br/> ||호출자의 링크입니다. 1은 VPN (가상 사설망)이 고 0은 VPN이 아닙니다.  <br/> |
|**CallerLinkSpeed** <br/> |10 진수 (18, 0)  <br/> ||호출자 끝점에 대 한 bps의 네트워크 링크 속도입니다.  <br/> |
|**CalleeIPAddr** <br/> |int  <br/> |외부  <br/> |통화 수신기의 IP 주소입니다. 자세한 내용은 [IPAddress 테이블](ipaddress.md) 을 참조 하세요. <br/> |
|**CalleePort** <br/> |다소  <br/> ||전화 수신기에서 사용 하는 포트입니다.  <br/> |
|**Calleesnet** <br/> |int  <br/> |외부  <br/> |호출 수신자의 서브넷입니다. 자세한 내용은 [IPAddress 테이블](ipaddress.md) 을 참조 하세요. <br/> |
|**CalleeInside** <br/> |다소  <br/> | <br/> |1은 통화 수신기가 엔터프라이즈 네트워크 내에 있음을 의미 하 고, 0 이면 전화 수신기가 네트워크 외부에 있음을 의미 합니다.  <br/> |
|**CalleeMacAddress** <br/> |int  <br/> |외부  <br/> |호출 수신자 Mac 주소입니다. (가) [테이블](macaddress.md)에서 참조 됩니다.  <br/> |
|**CalleeRelayIPAddr** <br/> |int  <br/> |외부  <br/> |통화 수신기에서 사용 하는 A/V Edge 서비스의 IP 주소입니다. 자세한 내용은 [IPAddress 테이블](ipaddress.md) 을 참조 하세요. <br/> |
|**CalleeRelayPort** <br/> |int  <br/> | <br/> |전화 수신기에 의해 A/V에 지 서비스에 사용 되는 포트입니다.  <br/> |
|**CalleeCaptureDev** <br/> |int  <br/> |외부  <br/> |호출 수신자가 사용 하는 캡처 장치입니다. [장치 테이블](device.md)에서 참조 됩니다.  <br/> |
|**CalleeRenderDev** <br/> |int  <br/> |외부  <br/> |통화 수신기에 사용 되는 장치를 렌더링 합니다. [장치 테이블](device.md)에서 참조 됩니다.  <br/> |
|**CalleeCaptureDevDriver** <br/> |int  <br/> |외부  <br/> |전화 수화기 캡처 장치용 드라이버입니다. [Devicedriver 테이블](devicedriver.md)에서 참조 했습니다.  <br/> |
|**CalleeRenderDevDriver** <br/> |varchar (256)  <br/> |외부  <br/> |통화 수신기의 렌더링 장치 드라이버입니다. [Devicedriver 테이블](devicedriver.md)에서 참조 했습니다.  <br/> |
|**CalleeNetworkConnectionType** <br/> |tinyint  <br/> |외부  <br/> |호출 수신자가 네트워크에 연결 되는 방법을 나타냅니다. 값은 [Networkconnectiondetail 테이블](networkconnectiondetail.md)에서 가져옵니다. WiFi 연결에 대 한 유선 연결의 경우 일반적으로 값은 0이 고, 그렇지 않으면-1입니다. 이더넷 연결의 경우 3.  <br/> |
|**CalleeBssid** <br/> |int  <br/> |외부  <br/> |무선이 사용 되는 경우 피호출자의 BSSID입니다. 로이 [테이블](macaddress.md)에서 참조 됩니다.  <br/> |
|**CalleeVPN** <br/> |다소  <br/> | <br/> |전화 수화기의 링크입니다. 1은 VPN (가상 사설망)이 고 0은 VPN이 아닙니다.  <br/> |
|**CalleeLinkSpeed** <br/> |10 진수 (18, 0)  <br/> | <br/> |통화 수신기의 끝점에 대 한 bps의 네트워크 링크 속도입니다.  <br/> |
|**ConversationalMOS** <br/> |10 진수 (3, 2)  <br/> | <br/> |오디오 세션의 Narrowband 대화 SPECIALIST (두 오디오 스트림 모두 기준).  <br/> |
|**AppliedBandwidthLimit** <br/> |int  <br/> ||다양 한 정책 설정 (TURN, API, SDP, 정책 서버 등)이 지정 된 지정 된 보내기 쪽 스트림에 적용 되는 실제 대역폭입니다. 대역폭 예측을 기준으로 낮은 유효 대역폭을 사용할 수 있기 때문에 효과적인 대역폭과 혼동 하지 않는 것이 좋습니다. 이 값이 기본적으로 최대 대역폭입니다. 송신 스트림은 대역폭 추정치에 의해 부과 된 제한을 받을 수 있습니다.  <br/> |
|**AppliedBandwidthSourceKey** <br/> |smallint  <br/> ||적용 되는 대역폭 cap의 원본입니다. 이는 대역폭 한도가 어디에서 오는지 ("정책 서버", "서버 켜기", "모달" 등)를 설명 합니다. [AppliedBandwidthSource 테이블](appliedbandwidthsource.md)에서 참조 됩니다.  <br/> |
|**호출인** <br/> |다소  <br/> | <br/> |호출자의 메트릭을 받았는지 여부를 나타냅니다. 1은 예, null 값은 no입니다.  <br/> |
|**피호출자** <br/> |다소  <br/> | <br/> |통화 수신기의 메트릭을 받았는지 여부를 나타냅니다. 1은 예, null 값은 no입니다.  <br/> |
|**MidCallReport** <br/> |다소  <br/> ||보고서가 세션의 일부 인지 또는 전체 세션에 대 한 것인지를 나타냅니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**ClassifiedPoorCall** <br/> |다소  <br/> ||통화가 불량 통화 (값 1) 또는 좋은 통화 (0)로 분류 되었는지 여부를 나타냅니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**CallerConnectivityICE** <br/> |tinyInt  <br/> ||발신자가 ICE 프로토콜 (인터넷 연결 설정)을 사용 하 여 네트워크에 연결 되었는지 여부를 나타냅니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**CalleeConnectivityICE** <br/> |tinyint  <br/> ||발신자가 ICE 프로토콜 (인터넷 연결 설정)을 사용 하 여 네트워크에 연결 되었는지 여부를 나타냅니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**CallerReflexiveLocalIPAddr** <br/> |int  <br/> |외부  <br/> |통화를 설정한 사용자의 재귀 IP 주소입니다. NAT (네트워크 주소 변환)를 사용 하는 조직에서 재귀 IP 주소는 프록시 서버의 IP 주소입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**CallerWiFiDriverDevicesDesc** <br/> |int  <br/> |외부  <br/> |통화를 설정한 사용자가 사용 하는 WiFi 드라이버에 대 한 디바이스 설명입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**CallerWiFiDriverVersion** <br/> |int  <br/> |외부  <br/> |통화를 설정한 사용자가 사용 하는 WiFi 드라이버의 버전 번호입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**CalleReflexiveLocalIPAddr** <br/> |int  <br/> |외부  <br/> |통화를 받은 사용자의 재귀 IP 주소입니다. NAT (네트워크 주소 변환)를 사용 하는 조직에서 재귀 IP 주소는 프록시 서버의 IP 주소입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**CalleeWiFiDriverDevicesDesc** <br/> |int  <br/> |외부  <br/> |통화를 받은 사용자가 사용 하는 WiFi 드라이버에 대 한 디바이스 설명입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**CalleeWiFiDriverVersion** <br/> |int  <br/> |외부  <br/> |통화를 받은 사용자가 사용 하는 WiFi 드라이버의 버전 번호입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
   

