---
title: MediaLine 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
description: 각 레코드는 하나의 미디어 줄을 나타 내는 것입니다. (하나의 오디오 세션에는 일반적으로 오디오 미디어 라인이 하나씩 포함되어 있습니다. A/V(오디오 및 비디오) 세션 하나에는 일반적으로 오디오 미디어 라인과 비디오 미디어 라인이 하나씩 포함되어 있습니다. 단, 회의 장치가 사용되거나 갤러리 보기를 사용하는 경우 세션에 비디오 미디어 선이 두 개 포함될 수 있습니다.
ms.openlocfilehash: bb4efba0477193232991732c821aaaa547a19583f8899156a1f92cca119c6b3a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321640"
---
# <a name="medialine-table"></a>MediaLine 테이블
 
각 레코드는 하나의 미디어 줄을 나타 내는 것입니다. (하나의 오디오 세션에는 일반적으로 오디오 미디어 라인이 하나씩 포함되어 있습니다. A/V(오디오 및 비디오) 세션 하나에는 일반적으로 오디오 미디어 라인과 비디오 미디어 라인이 하나씩 포함되어 있습니다. 단, 회의 장치가 사용되거나 갤러리 보기를 사용하는 경우 세션에 비디오 미디어 선이 두 개 포함될 수 있습니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Session [테이블에서 참조됩니다.](session.md)  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Session [테이블에서 참조됩니다.](session.md)  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |0은 기본 오디오, 1은 기본 비디오, 2는 파노라마 비디오, 3은 응용 프로그램/데스크톱 공유, 16은 VbSS(비디오 기반 화면 공유)입니다. 이 레이블은 단일 세션 내에서 고유해야 합니다.  <br/> |
|**ConnectivityIce** <br/> |tinyint  <br/> | <br/> |이 열은 있지만 Microsoft Lync Server 2013에서는 사용되지 않습니다. 미디어 라인에 사용되는 연결에 대한 정보는 CallerConnectivityICE 및 CalleeConnectivityICE 열에 캡처됩니다.  <br/> |
|**CallerIceWarningFlags** <br/> |int  <br/> | <br/> |비트 플래그에 설명된 ICE(Interactive Connectivity Establishment) 프로세스에 대한 정보입니다. 자세한 내용은 다운로드할 수 있는 환경 품질 모니터링  *서버 프로토콜*  사양 을 참조하세요. <br/> |
|**CalleeIceWarningFlags** <br/> |int  <br/> | <br/> |CallerIceWarningFlags와 동일하지만, 발신자 쪽에 있습니다. 자세한 내용은 다운로드할 수 있는 환경 품질 모니터링  *서버 프로토콜*  사양 을 참조하세요. <br/> |
|**보안** <br/> |tinyint  <br/> | <br/> |사용 중인 보안 프로필입니다. 0은 NONE, 1은 SRTP, 2는 V1입니다.  <br/> |
|**전송** <br/> |tinyint  <br/> | <br/> |0은 UDP, 1은 TCP입니다.  <br/> |
|**CallerIPAddr** <br/> |int  <br/> |외계인  <br/> |발신자 IP 주소입니다. 자세한 내용은 [IPAddress 테이블을](ipaddress.md) 참조하세요. <br/> |
|**CallerPort** <br/> |int  <br/> | <br/> | 발신자가 사용하는 포트입니다. <br/> |
|**CallerSubnet** <br/> |int  <br/> | 외계인 <br/> |발신자 서브넷입니다. 자세한 내용은 [IPAddress 테이블을](ipaddress.md) 참조하세요. <br/> |
|**CallerInside** <br/> |bit  <br/> | <br/> |1은 발신자가 회사 네트워크 내에 있음을 의미하고 0은 발신자가 네트워크 외부에 있음을 의미합니다.  <br/> |
|**CallerMacAddress** <br/> |int  <br/> |외계인  <br/> |[MacAddress](macaddress.md)테이블에서 참조되는 발신자 Mac 주소입니다.  <br/> |
|**CallerRelayIPAddr** <br/> |int  <br/> |외계인  <br/> |A/V 에지 서비스에서 발신자가 사용하는 IP 주소입니다. 자세한 내용은 [IPAddress 테이블을](ipaddress.md) 참조하세요. <br/> |
|**CallerRelayPort** <br/> |int  <br/> | <br/> |발신자에 의해 A/V 에지 서비스에서 사용되는 포트입니다.  <br/> |
|**CallerCaptureDev** <br/> |int  <br/> |외계인  <br/> |발신자에 의해 사용되는 캡처 장치입니다. [Device 테이블에서 참조됩니다.](device.md)  <br/> |
|**CallerRenderDev** <br/> |int  <br/> |외계인  <br/> |발신자에 의해 사용되는 디바이스를 렌더링합니다. [Device 테이블에서 참조됩니다.](device.md)  <br/> |
|**CallerCaptureDevDriver** <br/> |int  <br/> |외계인  <br/> |[DeviceDriver](devicedriver.md)테이블에서 참조되는 발신자 캡처 디바이스용 드라이버입니다.  <br/> |
|**CallerRenderDevDriver** <br/> |int  <br/> |외계인  <br/> |[DeviceDriver](devicedriver.md)테이블에서 참조되는 발신자 렌더링 장치에 대한 드라이버입니다.  <br/> |
|**CallerNetworkConnectionType** <br/> |tinyint  <br/> |외계인  <br/> |발신자 네트워크 연결 방법을 나타냅니다. 값은 [NetworkConnectionDetail 테이블에서 얻을 수 있습니다.](networkconnectiondetail.md) 일반적인 값은 유선 연결의 경우 0입니다. WiFi 연결의 경우 1입니다. 및 3은 이더넷 연결의 경우 입니다.  <br/> |
|**CallerBssid** <br/> |int  <br/> |외계인  <br/> |무선이 사용되는 경우 발신자 BSSID입니다. [MacAddress 테이블에서 참조됩니다.](macaddress.md)  <br/> |
|**CallerVPN** <br/> |bit  <br/> ||발신자 링크입니다. 1은 VPN(가상 사설망), 0은 비VPN입니다.  <br/> |
|**CallerLinkSpeed** <br/> |decimal(18,0)  <br/> ||발신자 끝점의 네트워크 연결 속도(bps)입니다.  <br/> |
|**CalleeIPAddr** <br/> |int  <br/> |외계인  <br/> |통화 수신기의 IP 주소입니다. 자세한 내용은 [IPAddress 테이블을](ipaddress.md) 참조하세요. <br/> |
|**CalleePort** <br/> |bit  <br/> ||통화 수신자가 사용하는 포트입니다.  <br/> |
|**CalleeSubnet** <br/> |int  <br/> |외계인  <br/> |발신자 서브넷입니다. 자세한 내용은 [IPAddress 테이블을](ipaddress.md) 참조하세요. <br/> |
|**CalleeInside** <br/> |bit  <br/> | <br/> |1은 통화 수신자가 엔터프라이즈 네트워크 내부에 있는 것입니다. 0은 통화 수신자가 네트워크 외부에 있는 것입니다.  <br/> |
|**CalleeMacAddress** <br/> |int  <br/> |외계인  <br/> |발신자 Mac 주소입니다. [MacAddress 테이블에서 참조됩니다.](macaddress.md)  <br/> |
|**CalleeRelayIPAddr** <br/> |int  <br/> |외계인  <br/> |통화 수신자가 사용하는 A/V 에지 서비스의 IP 주소입니다. 자세한 내용은 [IPAddress 테이블을](ipaddress.md) 참조하세요. <br/> |
|**CalleeRelayPort** <br/> |int  <br/> | <br/> |통화 수신자가 A/V 에지 서비스에 사용되는 포트입니다.  <br/> |
|**CalleeCaptureDev** <br/> |int  <br/> |foreign  <br/> |통화 수신자가 사용하는 캡처 장치입니다. [Device 테이블에서 참조됩니다.](device.md)  <br/> |
|**CalleeRenderDev** <br/> |int  <br/> |외계인  <br/> |통화 수신기에서 사용하는 디바이스를 렌더링합니다. [Device 테이블에서 참조됩니다.](device.md)  <br/> |
|**CalleeCaptureDevDriver** <br/> |int  <br/> |외계인  <br/> |통화 수신기의 캡처 장치에 대한 드라이버입니다. [DeviceDriver](devicedriver.md)테이블에서 참조됩니다.  <br/> |
|**CalleeRenderDevDriver** <br/> |varchar(256)  <br/> |외계인  <br/> |통화 수신기의 렌더링 장치에 대한 드라이버입니다. [DeviceDriver](devicedriver.md)테이블에서 참조됩니다.  <br/> |
|**CalleeNetworkConnectionType** <br/> |tinyint  <br/> |외계인  <br/> |발신자 네트워크 연결 방법을 나타냅니다. 값은 [NetworkConnectionDetail 테이블에서 얻을 수 있습니다.](networkconnectiondetail.md) 일반적인 값은 유선 연결의 경우 0입니다. WiFi 연결의 경우 1입니다. 및 3은 이더넷 연결의 경우 입니다.  <br/> |
|**CalleeBssid** <br/> |int  <br/> |외계인  <br/> |무선을 사용하는 경우 발신자 BSSID입니다. [MacAddress 테이블에서 참조됩니다.](macaddress.md)  <br/> |
|**CalleeVPN** <br/> |bit  <br/> | <br/> |통화 수신자 링크 1은 VPN(가상 사설망), 0은 비 VPN입니다.  <br/> |
|**CalleeLinkSpeed** <br/> |decimal(18,0)  <br/> | <br/> |통화 수신기의 끝점에 대한 네트워크 연결 속도(bps)입니다.  <br/> |
|**ConversationalMOS** <br/> |decimal(3,2)  <br/> | <br/> |오디오 세션의 협대역 대화 MOS입니다(두 오디오 스트림을 모두 기반으로 함).  <br/> |
|**AppliedBandwidthLimit** <br/> |int  <br/> ||이는 다양한 정책 설정(TURN, API, SDP, 정책 서버 등)이 제공된 주어진 송신 쪽 스트림에 적용되는 실제 대역폭입니다. 이 대역폭은 대역폭 예상에 따라 유효 대역폭이 더 낮을 수 있으므로 유효 대역폭과 혼동해서는 안됩니다. 이 대역폭은 기본적으로 대역폭 예상치로 지정된 한도를 제외하고 송신 스트림이 사용할 수 있는 최대 대역폭입니다.  <br/> |
|**AppliedBandwidthSourceKey** <br/> |smallint  <br/> ||대역폭 한도가 부과되는 원본입니다. 대역폭 제한이 시작되는 위치("정책 서버", "TURN Server", "Modality" 등)를 설명합니다. [AppliedBandwidthSource](appliedbandwidthsource.md)테이블에서 참조됩니다.  <br/> |
|**발신자** <br/> |bit  <br/> | <br/> |발신자로부터 메트릭을 수신할지 여부를 나타냅니다. 1은 예, null 값은 아니요입니다.  <br/> |
|**발신자** <br/> |bit  <br/> | <br/> |통화 수신자로부터 메트릭을 수신할지 여부를 나타냅니다. 1은 예, null 값은 아니요입니다.  <br/> |
|**MidCallReport** <br/> |bit  <br/> ||보고서가 세션의 일부에 대한 보고서인지 아니면 전체 세션에 대한 것인지를 나타냅니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||통화가 불량 통화(값 1) 또는 양호한 통화(0)로 분류된 것인지를 나타냅니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**CallerConnectivityICE** <br/> |tinyInt  <br/> ||발신자가 ICE(Internet Connectivity Establishment) 프로토콜을 사용하여 네트워크에 연결했는지 여부를 나타냅니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**CalleeConnectivityICE** <br/> |tinyint  <br/> ||발신자가 ICE(Internet Connectivity Establishment) 프로토콜을 사용하여 네트워크에 연결했는지 여부를 나타냅니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**CallerReflexiveLocalIPAddr** <br/> |int  <br/> |외계인  <br/> |통화를 걸었다는 사용자의 반사 IP 주소입니다. NAT(네트워크 주소 변환)를 사용하는 조직에서 반사 IP 주소는 프록시 서버의 IP 주소입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**CallerWiFiDriverDevicesDesc** <br/> |int  <br/> |외계인  <br/> |통화를 걸었다는 사용자가 고용한 WiFi 드라이버에 대한 장치 설명입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**CallerWiFiDriverVersion** <br/> |int  <br/> |외계인  <br/> |통화를 걸고 사용자가 고용한 WiFi 드라이버의 버전 번호입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**CalleReflexiveLocalIPAddr** <br/> |int  <br/> |외계인  <br/> |통화를 받은 사용자의 반사 IP 주소입니다. NAT(네트워크 주소 변환)를 사용하는 조직에서 반사 IP 주소는 프록시 서버의 IP 주소입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**CalleeWiFiDriverDevicesDesc** <br/> |int  <br/> |외계인  <br/> |통화를 받은 사용자가 고용한 WiFi 드라이버에 대한 장치 설명입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**CalleeWiFiDriverVersion** <br/> |int  <br/> |외계인  <br/> |통화를 받은 사용자가 고용한 WiFi 드라이버의 버전 번호입니다.  <br/> 이 열은 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
   

