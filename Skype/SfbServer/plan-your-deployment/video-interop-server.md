---
title: 비즈니스용 Skype 서버의 비디오 Interop 서버 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a8daf23-77ba-428b-bcbc-161f6af52c11
description: '요약: 비즈니스용 Skype 서버를 타사 teleconferencing 장치와 통합 하기 위해 계획 하는 동안이 항목을 검토 하세요.'
ms.openlocfilehash: af7618efa0b5f13419be216b37a4f1e7d4065e97
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815566"
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 비디오 Interop 서버 계획
 
**요약:** 비즈니스용 Skype 서버와 타사 teleconferencing 장치를 통합 하는 계획을 수립할 때이 항목을 검토 하세요.
  
이제 비즈니스용 Skype 서버를 사용 하 여 특정 타사 VTC (비디오 Teleconferencing System) 솔루션과 통합할 수 있습니다. 이 비디오 회의 상호 운용성을 가능 하 게 하는 새로운 서버 역할은 현재 온-프레미스 설치에만 사용할 수 있는 독립 실행형 서버 역할로 구현 되는 VIS (동영상 Interop 서버)입니다. VIS는 타사의 원격 회의 시스템 및 비즈니스용 Skype 서버 배포 간에 중개 역할을 합니다. 이번 릴리스의 경우 VIS는 Cisco/Tandberg 영상 시스템과의 상호 운용성에 중점을 두었습니다. 비즈니스용 Skype 서버 설치에이 기능을 사용할지 여부를 결정 하려면이 문서를 검토 하세요.
  
## <a name="device-interoperability"></a>장치 상호 운용성

VTCs는 cisco 통합 커뮤니케이션 관리자 (CallManager 또는 CUCM) 버전 10.5 및 TCP SIP trunks에서 CUCM와 VIS 간에 설정 된 Cisco를 통해 테스트 및 지원 됩니다.
  
현재 지원 되는 VTCs는 다음과 같습니다.
  
- Cisco C40
    
- Cisco C60
    
- Cisco C90
    
- Cisco MX200
    
- Cisco MX300
    
- Cisco DX80
    
- Cisco EX60
    
- Cisco EX90
    
- Cisco SX20
    
> [!NOTE]
>  비즈니스용 Skype Server와 통합 하기 위해 이러한 시스템에서는 Cisco 소프트웨어 릴리스 TC 7.0.0 이상이 필요 합니다.
  
## <a name="sip-trunks"></a>SIP trunks

VTCs가 기존 Cisco 인프라에 계속 등록 되는 SIP 트렁크 모드의 비디오 Interop 서버 기능 (예: CUCM (Cisco Call Manager)). 비디오 SIP 트렁크는 CUCM와 VIS 사이에 정의 되어 있으며, 두 시스템 간에 통화가 라우팅될 수 있도록 합니다. VTC에서 VIS로의 SIP 트렁크에 대 한 호출만 지원 됩니다. 따라서 VTCs는 비즈니스용 Skype 컨퍼런스 (자동 전화 교환과 연결 된 전화 번호로 전화를 걸고)로 전화를 걸 수 있지만, 회의에 끌어서 놓을 수는 없습니다.
  
![SfB의 VIS 다이어그램](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a>기능

이 서버 역할은 다음을 제공 합니다.
  
- 타사 비디오 시스템 및 비즈니스용 Skype 서버 배포에 사용 되는 .H 264 형식 간의 변환입니다.
    
- VTC에서 지정 된 해상도의 단일 비디오 스트림을 비즈니스용 Skype 서버 배포에 사용 되는 다른 해상도의 여러 simulcast 스트림으로 변환 합니다. 이러한 스트림은 AVMCU에 게 전송 된 다음 다른 해결 방법을 요청한 비즈니스용 Skype 서버 끝점 및 기타 영상 시스템으로 보내질 수 있습니다. 이 변환은 타사 영상 시스템을 비즈니스용 Skype A/V 컨퍼런스 통화에 참여 하는 경우에도 사용 됩니다. 특정 VIS 서버에서 코드 변환 제한에 도달 하면 다른 해결 방법에 대 한 다음 요청은 해상도가 가장 낮은 스트림만 받습니다. 
    
- CUCM 게이트웨이와 비즈니스용 Skype Server 비디오 Interop 서버 간 비디오 SIP 트렁크 지원 VTCs 계속 Cisco 게이트웨이에 등록 하 고 게이트웨이를 통해 비즈니스용 Skype 배포에 대 한 통화를 시작 합니다. 통화는 게이트웨이에서 비디오 SIP 트렁크로 Skype for 비즈니스용 비디오 Interop 서버로 라우팅됩니다.
    
- 시스템에서 전화를 걸어 열려 있거나 종료 된 회의에 참가할 수 있는 지원 되는 비디오 시스템을 사용 하 여 회의실의 사용자 지원 이 통화는 비디오 SIP 트렁크를 통과 합니다.
    
- 비즈니스용 Skype 클라이언트에 게 전화를 걸 수 있는 지원 되는 비디오 시스템을 사용 하 여 회의실의 사용자 지원 통화가 SIP 트렁크를 통과 하 게 됩니다.
    
- 비즈니스용 Skype 서버 쪽 또는 지원 되는 VTC 시스템 (음소거/음소거 해제, 비디오 일시 중지/다시 시작, 비디오 잠금, 보류/제거 통화)에 대 한 지원이 지원 됩니다.
    
## <a name="known-limitations"></a>알려진 제한 사항

이 서버 역할에는 다음과 같은 제한 사항이 있습니다.
  
- 비즈니스용 Skype 배포에서 비디오 SIP 트렁크를 통해 VTCs에 대 한 새로운 통화는 지원 되지 않습니다. . 즉, 비디오 SIP 트렁크에서 VTCs의 비즈니스용 Skype 배포에 대 한 새로운 호출만 지원 됩니다. 지원 되는 비디오 시스템에 대 한 현재 상태는 비디오 SIP 트렁크에서 VIS에 제공 되지 않습니다. 
    
- 비디오 SIP 트렁크 모드에서는 독립 실행형 VIS 풀만 지원 됩니다.
    
-  TLS + SRTP 또는 TCP + RTP는 비디오 SIP 트렁크를 통해 VTC와 VIS 간 통신에 지원 됩니다.
    
- 응용 프로그램 공유가 지원 되지 않습니다. 회의실의 비즈니스용 Skype 사용자는 비즈니스용 Skype 컨퍼런스 (예: 랩톱)에 참가 하 고 VTC에 연결 되지 않은 회의실의 무료 모니터 중 하나에 앱 공유 화면을 표시 해야 합니다.
    
- VTC가 VIS를 통해 페더레이션된 모임에 참가할 수 있는 기능은 지원 되지 않습니다.
    
- VTC가 VIS를 통해 온라인 모임에 참가할 수 있는 기능은 지원 되지 않습니다.
    
- VTC에서 VIS를 통해 PSTN으로 거는 호출은 지원 되지 않습니다.
    
- PSTN에서 VIS를 통해 VTC로 거는 호출은 지원 되지 않습니다.
    
## <a name="resiliency-mechanisms"></a>복원 메커니즘
<a name="resiliency"> </a>

VIS는 비디오 SIP 트렁크를 통해 운반 된 CUCM에서 걸려오는 전화를 지원 합니다. 업스트림 또는 다운스트림에 대 한 연결이 끊어질 수 있으므로 강력한 탄력성을 위해 두 가지 가능성을 모두 고려해 야 합니다.
  
1. **VIS 풀 장애 조치** 비디오 게이트웨이가 가리키는 기본 VIS 풀이 작동 하지 않는 경우 비디오 게이트웨이가 두 개 이상의 VIS 풀로 trunks를 정의한 경우 복구 될 수 있습니다. 비디오 게이트웨이에서 기본 VIS 풀로 전화를 걸 수 없는 것으로 판단 되는 경우에는 단순히 보조 VIS 풀로 착신 경로를 설정 합니다.
    
     ![VIS 풀 장애 조치 다이어그램](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    특정 VIS 풀은 여러 게이트웨이에 trunks 수 있지만, 일반적으로 특정 게이트웨이는 여러 VIS 풀에 trunks 수 없으므로 이러한 장애 조치를 지원 하기 위해 트릭을 수행 해야 합니다. DNS에서 두 FDQNs을 정의 하 여 비디오 게이트웨이의 동일한 IP 주소로 확인 됩니다. 각 비디오 게이트웨이에서 다른 VIS 풀로 트렁크를 보유 하 고 있으며 이제 복구가 가능 하는 토폴로지 문서에서 각 FQDN을 별도의 비디오 게이트웨이로 나타냅니다. TLS를 사용 하는 경우에는 여러 이름이 비디오 게이트웨이 인증서의 SAN에 있어야 합니다.
    
    > [!NOTE]
    > VIS는 토폴로지 문서에 구성 된 게이트웨이에서 수신 호출만 허용 합니다. 
  
2. **프론트 엔드 장애 조치** VIS 풀이 CUCM에서 전화를 받지만 기본 다음 홉 등록자 또는 프런트 엔드 풀에 도달할 수 없는 경우에는 통화가 백업 프런트 엔드 풀로 라우팅됩니다.
    
     ![프런트 엔드 장애 조치 다이어그램](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    VIS는 기본 프런트 엔드 풀 및 해당 백업 프런트 엔드 풀의 상태를 추적 합니다 (이 설정은 토폴로지 문서의 등록자 서비스에 대 한 백업 설정에 있음). 이 옵션은 두 풀에 1 분에 한 번만 투표 하 고 다섯 개의 연속 된 실패가 있으면 VIS는 특정 프론트 엔드 풀이 중단 되었다고 가정 합니다. 기본 프런트 엔드 풀이 down으로 표시 되어 있고 사용 가능한 구성 된 백업이 있는 경우 VIS는 게이트웨이에서 새 통화를 백업 프런트 엔드 풀에 보냅니다. 기본 프런트 엔드 풀이 다시 들어오면 VIS에서 새 통화에 기본 프런트 엔드 풀을 사용 하 여 다시 시작 됩니다.
    
    VIS는 또한 비디오 SIP 트렁크에서 전화를 걸 수 있도록 10 초의 타이머를 구현 하 게 됩니다. 기본 다음 홉 프런트 엔드 풀을 비디오 SIP 트렁크에서 전화를 거는 데 사용 했지만 기본 다음 홉 프런트 엔드 풀이이 타이머 값 내에 전송 된 초대에 대 한 일부 SIP 메시지 (100를 포함 하 여)에 응답 하지 않은 경우, 통화에 대 한 백업 다음 홉 프록시 구성 된 경우 hould을 시도 합니다. 
    
    > [!NOTE]
    > 다음 홉을 먼저 시도한 경우에는 기본 백업이 다음에 시도 되지 않습니다. 
  
    또한 관리자는 Windows PowerShell 장애 조치 (failover) 명령을 사용 하 여 기본 프런트 엔드 풀에서 유지 관리를 수행 해야 하는 경우와 같이 VIS에서 백업 프런트 엔드 풀을 사용 하도록 강제할 수 있습니다.
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a>동일한 게이트웨이 피어에 음성 및 비디오 Trunks의 공존
<a name="resiliency"> </a>

비즈니스용 Skype 서버는 동일한 게이트웨이 피어를 사용 하는 음성 및 비디오 SIP trunks 지원 합니다. 따라서 동일한 CUCM 배포 시 중재 서버와 동영상 SIP trunks에 대 한 음성 SIP trunks를 VIS 할 수 있습니다.
  
- PSTN 게이트웨이는 음성 SIP trunks에 대 한 토폴로지 문서의 특정 FQDN으로 정의 해야 합니다.
    
- PSTN 게이트웨이에 대 한 피어는 중재 서버가 됩니다.
    
- 여러 음성 trunks 필요한 경우 PSTN 게이트웨이에서 여러 중재 서버 풀로 스패닝을 정의할 수 있습니다.
    
- 비디오 게이트웨이는 PSTN 게이트웨이와 동일한 FQDN의 비디오 SIP 트렁크에 대 한 토폴로지 문서에서 정의 해야 합니다.
    
- 비디오 게이트웨이의 피어가 VIS 됩니다.
    
- 단일 영상 트렁크를 비디오 게이트웨이에서 특정 VIS 풀로 정의할 수 있습니다.
    
- CUCM는 음성 트렁크 및 영상 트렁크를 통해 착신 통화를 제대로 라우팅하도록 구성 해야 합니다. 예를 들어 VTC에서 전화를 걸 때 특별 한 전화 번호를 사용할 수 있습니다. CUCM는이 다이얼 접두 번호를 VIS에 연결할 수 있으며, 적절 한 번역 규칙이 SIP 초대에서 VIS로이 접두어를 제거 합니다.
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a>이전 버전의 Lync를 사용 하 여 비즈니스용 Skype 릴리스에 VIS의 공존
<a name="resiliency"> </a>

VIS는 비즈니스용 Skype 배포의 일부로만 배포할 수 있습니다. 기존 배포의 일부인 Lync 2013 컨퍼런스 및 클라이언트와 상호 작용할 수 있습니다. 이러한 경우 VIS 풀은 VIS 풀의 다음 홉 인 등록자/FE 풀을 포함 하는 비즈니스용 Skype 배포에 포함 되어야 합니다.
  
VIS는 RTV와 .H 간의 코드 변환을 지원 하지 않습니다. 프리 Lync 2013 클라이언트와 회의의 VTC 참가자 간에는 영상 상호 운영성이 없습니다.
  
전화 회의 중에 Lync 2013 클라이언트를 사용 하면 모바일 클라이언트가 기준 스피커가 될 때 VTCs에서 비디오를 받지 않도록 하는 RTV를 통해 전송 됩니다.
  
비즈니스용 Skype 배포의 일부인 VIS에서 Lync 2013이 제대로 작동 하도록 하려면 lync 2013에서 Lync 2013 클라이언트, CAA 및 AVMCU를 업그레이드 하 여 VIS와 함께 작동 하도록 적절 한 CU (을 적용 해야 합니다.
  
Lync 2013 및 비즈니스용 Skype 데스크톱 클라이언트와 VIS의 상호 운영성이 테스트 되었으며 지원 됩니다.
  
비 데스크톱 (Android, Ipad, Iphone, Windows Phone, LMX 등)과 VIS의 상호 운용성 VIS 릴리스가 테스트 되 고 지원 되는 시점에는 해당 앱 스토어에서 사용할 수 있는 비즈니스용 Skype 클라이언트가 있습니다.
  
## <a name="recovery-from-packet-loss-via-fec"></a>FEC를 통한 패킷 손실 복구
<a name="resiliency"> </a>

패킷 손실에 대 한 복구를 돕기 위해 FEC을 켤 수 있습니다. 켜져 있는 경우 50% 이상의 비디오 대역폭이 VIS에서 VTC 방향으로 사용 됩니다.
  
## <a name="vis-sizing-and-transcoding-costs"></a>VIS 크기 조정 및 코드 변환 비용
<a name="resiliency"> </a>

Cisco VTC에서 여러 simulcast 스트림으로 단일 비디오 스트림을 코드 변환 하는 것은 CPU 용량을 사용 합니다. 약 16 개의 VTCs 비디오 코드 변환이 가능 합니다 (각 VTC의 720p 비디오 스트림이 720p, 360p, 180p)의 3 개의 개별 simulcast 스트림으로 트랜스 코딩 되는 것으로 가정 하 여 Lync 2013 권장 FE 플랫폼에 해당 하는 단일 VIS를 실행 합니다. 코드 변환이 해제 되어 있으면 VIS CPU에 저장 됩니다. 그러나 VTC에서 VIS에 의해 요청 된 비디오 이미지는 비즈니스용 Skype 측의 모든 수신기를 충족 하는 가장 낮은 수준의 해상도입니다. 코드 변환 해제를 사용 하는 경우에도 비즈니스용 Skype 클라이언트가 VTCs에서 보낼 수 없는 특정 저해상도 해상도를 요청 하면 코드 변환이 활성화 될 수 있습니다.
  
## <a name="call-distribution-from-the-video-gateway-to-vis"></a>영상 게이트웨이에서 VIS에 게 배포 전화 걸기
<a name="resiliency"> </a>

배포는 CUCM 배포 메커니즘 중 하나를 통해 수행 됩니다.
  
- DNS를 동적으로 사용 합니다.
    
- CUCM side에서는 각 트렁크가 VIS 풀의 다른 서버에서 종료 되는 개별 trunks 정의할 수 있습니다. CUCM는 다른 trunks에 걸친 통화를 라우팅합니다.
    
## <a name="no-hybrid-interoperability"></a>하이브리드 상호 운용성 없음
<a name="resiliency"> </a>

온-프레미스 VIS를 통한 온라인 모임 VTCs에 대 한 지원은 비즈니스용 Skype에 포함 되어 있지 않습니다.
  
## <a name="no-federation-support"></a>페더레이션 지원 없음
<a name="resiliency"> </a>

VIS를 통한 페더레이션된 모임 참가 VTCs에 대 한 지원은 비즈니스용 Skype에 포함 되어 있지 않습니다.
  
## <a name="see-also"></a>참고 항목
<a name="resiliency"> </a>

[비즈니스용 Skype 서버에서 비디오 Interop 서버 배포](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)
