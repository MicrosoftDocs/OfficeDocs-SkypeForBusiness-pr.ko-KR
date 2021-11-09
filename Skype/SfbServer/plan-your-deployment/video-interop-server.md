---
title: 2013의 비디오 Interop 서버 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
f1.keywords:
- ms.lync.plan.VideoInterop
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4a8daf23-77ba-428b-bcbc-161f6af52c11
description: '요약: 타사 전화 비즈니스용 Skype 서버 통합할 계획을 세우는 동안 이 항목을 검토합니다.'
ms.openlocfilehash: b928e432b464e6bf1a5ccb8748ebf75ef8cc596b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862065"
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server"></a>2013의 비디오 Interop 서버 비즈니스용 Skype 서버
 
**요약:** 타사 원격 구성 장치와 통합하는 비즈니스용 Skype 서버 이 항목을 검토하세요.
  
비즈니스용 Skype 서버 이제 특정 타사 VTC(Video Teleconferencing System) 솔루션과 통합할 수 있습니다. 이 비디오 회의 상호 연산을 가능하게 하는 새로운 서버 역할은 VIS(Video Interop Server)입니다. 이 서버 역할은 현재는 사내 설치에만 사용할 수 있는 독립 실행형 서버 역할로 구현됩니다. VIS는 타사 전화 통신 시스템과 시스템 배포 간의 비즈니스용 Skype 서버 역할을 합니다. 이 릴리스에서 VIS는 Cisco/Tandberg 비디오 시스템과의 상호 운영성에 중점을 두고 있습니다. 이 문서를 검토하여 설치 시 이 기능을 사용할지 비즈니스용 Skype 서버 합니다.
  
## <a name="device-interoperability"></a>장치 상호 연결성

상호 연결은 CUCM과 VIS 사이에 설정된 Cisco Unified Communications Manager(CallManager 또는 CUCM) 버전 10.5 및 TCP SIP 트렁크에 등록된 Cisco VTC를 통해 테스트 및 지원됩니다.
  
현재 지원되는 VTC는 다음을 지원합니다.
  
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
>  Cisco 소프트웨어 릴리스 TC7.0.0 이상은 이러한 시스템과의 통합을 위해 비즈니스용 Skype 서버 필요합니다.
  
## <a name="sip-trunks"></a>SIP 트렁크

비디오 Interop 서버는 SIP 트렁크 모드에서 기능합니다. 여기서 VTC는 기존 Cisco 인프라에 계속 등록합니다(예: Cisco Call Manager(CUCM). 두 시스템 간에 통화를 라우팅할 수 있도록 CUCM과 VIS 간에 비디오 SIP 트렁크가 정의됩니다. VTC에서 VIS로의 SIP 트렁크를 통해 호출하는 것만 지원됩니다. 따라서 VTC는 전화 자동 비즈니스용 Skype 연결된 전화 번호로 전화를 걸 수 있지만 전화 회의에 끌어서 놓을 수는 없습니다.
  
![SfB의 VIS 다이어그램입니다.](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a>기능

이 서버 역할은 다음을 제공합니다.
  
- 제3자 비디오 시스템에서 사용하는 H.264 형식과 비즈니스용 Skype 서버 변환합니다.
    
- VTC에서 지정한 해상도의 단일 비디오 스트림을 배포에서 사용할 수 있는 서로 다른 해상도의 여러 simulcast 스트림으로 비즈니스용 Skype 서버 변환합니다. 이러한 스트림은 AVMCU로 전송된 다음 다른 해상도를 요청한 비즈니스용 Skype 서버 및 기타 비디오 시스템으로 전송할 수 있습니다. 이 변환은 타사 비디오 시스템이 A/V 전화 회의에 비즈니스용 Skype 사용됩니다. 특정 VIS 서버에서 코드 변환 제한에 도달하면 다른 해상도에 대한 다음 요청은 가장 낮은 해상도의 스트림만 수신합니다. 
    
- CUCM 게이트웨이와 비디오 interop 서버 간의 비디오 SIP 트렁크 비즈니스용 Skype 서버 지원 VTC는 Cisco 게이트웨이에 계속 등록하고 게이트웨이를 통해 비즈니스용 Skype 배포에 대한 호출을 시작합니다. 비디오 SIP 트렁크를 통해 게이트웨이에서 비즈니스용 Skype 비디오 Interop 서버로 통화가 라우팅됩니다.
    
- 지원되는 비디오 시스템이 있는 회의실의 사용자가 해당 시스템에서 전화를 걸 수 있도록 지원하여 열려 있는 회의 또는 닫힌 회의에 참가할 수 있습니다. 이 호출은 비디오 SIP 트렁크를 트래버스합니다.
    
- 지원되는 비디오 시스템이 있는 회의실의 사용자를 지원하여 비즈니스용 Skype 합니다. 호출이 SIP 트렁크를 트래버스합니다.
    
- 오디오 음소거/음소거 해제, 비디오 일시 중지/다시 시작, 비디오 잠금 및 보류/풀기 통화를 비롯한 지점 및 다중 지점 통화에 대해 비즈니스용 Skype 서버 쪽 또는 지원되는 VTC 시스템의 중간 통화 제어가 지원됩니다.
    
## <a name="known-limitations"></a>알려진 제한

이 서버 역할에는 다음과 같은 제한 사항이 있습니다.
  
- 비디오 SIP 트렁크를 비즈니스용 Skype VTC로의 새 배포 호출은 지원되지 않습니다. . 즉, VTC에서 비즈니스용 Skype 배포로의 새 호출만 비디오 SIP 트렁크를 통해 지원됩니다. 지원되는 비디오 시스템의 현재 상태는 VIS에 대한 비디오 SIP 트렁크를 통해 사용할 수 없습니다. 
    
- 비디오 SIP 트렁크 모드에는 독립 실행형 VIS 풀만 지원됩니다.
    
-  비디오 SIP 트렁크를 통해 VTC와 VIS 간의 통신에 대해 TLS + SRTP 또는 TCP + RTP가 지원됩니다.
    
- 응용 프로그램 공유는 지원되지 않습니다. 회의실의 비즈니스용 Skype 사용자는 비즈니스용 Skype 회의에 참가하고(예: 노트북을 통해) VTC와 연결되지 않은 회의실의 무료 모니터 중 하나에 앱 공유 화면을 표시해야 합니다.
    
- VTC가 VIS를 통해 페더전된 모임에 참가하는 것은 지원되지 않습니다.
    
- VTC가 VIS를 통해 온라인 모임에 참가하는 것은 지원되지 않습니다.
    
- VTC에서 VIS를 통한 PSTN으로의 호출은 지원되지 않습니다.
    
- PSTN에서 VIS를 통해 VTC로의 호출은 지원되지 않습니다.
    
## <a name="resiliency-mechanisms"></a>탄력성 메커니즘
<a name="resiliency"> </a>

VIS는 비디오 SIP 트렁크를 통해 수행되는 CUCM에서 들어오는 호출을 지원합니다. 업스트림 또는 다운스트림 연결이 손실될 수 있으므로 강력한 탄성을 위해 두 가지 가능성을 모두 고려합니다.
  
1. **VIS 풀 장애 조치(failover)** 비디오 게이트웨이가 지점하는 기본 VIS 풀이 다운된 경우 비디오 게이트웨이가 두 개 이상의 VIS 풀에 트렁크를 정의한 경우 복구할 수 있습니다. 비디오 게이트웨이가 기본 VIS 풀로 전화를 걸 수 없다고 판단하면 단순히 통화를 보조 VIS 풀로 라우팅합니다.
    
     ![VIS 풀 장애 조치(failover)의 다이어그램입니다.](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    특정 VIS 풀에는 여러 게이트웨이에 대한 트렁크가 있을 수 있지만 일반적으로 특정 게이트웨이에는 여러 VIS 풀에 대한 트렁크가 있을 수 없습니다. 따라서 이 장애 조치(failover)를 지원하기 위해 다음을 수행해야 합니다. 비디오 게이트웨이의 동일한 IP 주소로 확인되는 DNS에 2 FDQNs 정의 각 비디오 게이트웨이에 다른 VIS 풀에 대한 트렁크가 있으며 이제 복구가 가능한 토폴로지 문서에서 각 FQDN을 별도의 비디오 게이트웨이로 표현합니다. TLS를 사용하는 경우 여러 이름이 비디오 게이트웨이 인증서의 SAN에 와야 합니다.
    
    > [!NOTE]
    > VIS는 토폴로지 문서에 구성된 게이트웨이에서 들어오는 호출만 허용합니다. 
  
2. **프런트 엔드 장애 조치(failover)** VIS 풀이 CUCM에서 전화를 받지만 기본 다음 홉 등록자 또는 프런트 엔드 풀에 도달할 수 없는 경우 통화가 백업 프런트 엔드 풀로 라우팅됩니다.
    
     ![프런트 엔드 장애 조치(failover) 다이어그램.](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    VIS는 기본 프런트 엔드 풀 및 해당 백업 프런트 엔드 풀의 상태를 추적합니다(설정은 토폴로지 문서의 등록자 서비스에 대한 백업 설정에 있습니다). 옵션 폴링을 1분에 한 번 두 풀로 보내며, 5번 연속 오류가 발생하면 VIS에서 특정 프런트 엔드 풀이 다운된 것으로 가정합니다. 기본 프런트 엔드 풀이 다운된 것으로 표시되어 있으며 구성된 백업을 사용할 수 있는 경우 VIS는 게이트웨이에서 백업 프런트 엔드 풀로 새 통화를 전송합니다. 기본 프런트 엔드 풀이 돌아오면 VIS는 새 통화에 대해 기본 프런트 엔드 풀을 사용하여 다시 시작됩니다.
    
    또한 VIS는 비디오 SIP 트렁크의 통화에 대해 10초의 Timer를 구현합니다. 기본 다음 홉 프런트 엔드 풀이 비디오 SIP 트렁크의 통화에 사용되어 기본 홉 프런트 엔드 풀이 이 Timer 값 내에서 전송된 초대에 대한 일부 SIP 메시지(100 시도 포함)로 응답하지 않은 경우 통화에 대한 백업 다음 홉 프록시를 구성한 경우 시도해야 합니다. 
    
    > [!NOTE]
    > 백업 다음 홉을 먼저 시도한 경우 기본 홉은 다음에 시도되지 않습니다. 
  
    또한 관리자는 기본 Windows PowerShell 풀에서 유지 관리 작업을 수행해야 하는 경우와 같은 경우 VIS가 백업 프런트 엔드 풀을 강제로 사용하게 할 수 있습니다.
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a>동일한 게이트웨이 피어에 음성 및 비디오 트렁크 동시 사용
<a name="resiliency"> </a>

비즈니스용 Skype 서버 SIP 트렁크가 동일한 게이트웨이 피어를 사용할 수 있도록 지원됩니다. 따라서 동일한 CUCM 배포에 중재 서버에 대한 음성 SIP 트렁크와 VIS에 대한 비디오 SIP 트렁크가 있을 수 있습니다.
  
- 음성 SIP 트렁크에 대한 토폴로지 문서의 특정 FQDN으로 PSTN 게이트웨이를 정의해야 합니다.
    
- PSTN 게이트웨이에 대한 피어는 중재 서버가 됩니다.
    
- 필요한 경우 PSTN 게이트웨이에서 여러 중재 서버 풀로 스패닝되는 여러 음성 트렁크를 정의할 수 있습니다.
    
- 비디오 게이트웨이는 PSTN 게이트웨이와 FQDN이 동일한 비디오 SIP 트렁크에 대해 토폴로지 문서에 정의해야 합니다.
    
- 비디오 게이트웨이에 대한 피어는 VIS가 됩니다.
    
- 비디오 게이트웨이에서 특정 VIS 풀로 단일 비디오 트렁크를 정의할 수 있습니다.
    
- 음성 트렁크와 비디오 트렁크를 통해 통화를 올바르게 라우팅하도록 CUCM을 구성해야 합니다. 예를 들어 VTC에서 전화를 걸 때 특수한 전화 걸기 prefix를 사용할 수 있습니다. CUCM은 이 전화 걸기 prefix를 VIS 호출과 연결할 수 있으며 적절한 변환 규칙은 SIP Invite에서 VIS로 이 prefix를 제거합니다.
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a>Lync의 이전 릴리스와 비즈니스용 Skype VIS의 동시 사용
<a name="resiliency"> </a>

VIS는 배포의 일부로만 배포할 비즈니스용 Skype 있습니다. 기존 배포의 일부인 Lync 2013 회의 및 클라이언트와 상호 연결될 수 있습니다. 이러한 경우 VIS 풀은 VIS 풀의 다음 홉인 등록자/FE 풀을 포함하는 비즈니스용 Skype 배포에 포함되어야 합니다.
  
VIS는 RTV와 H.264 간의 변환을 지원하지 않습니다. Lync 2013 전 클라이언트와 회의에 참가한 VTC 참가자 간에는 비디오 상호 교환이 없습니다.
  
회의에 Lync 2013 전 클라이언트가 있는 경우 모바일 클라이언트가 주 발표자일 때 VTC가 비디오를 수신하지 못하게 하여 RTV를 사용하여 전송하게 됩니다.
  
Lync 2013이 비즈니스용 Skype 배포의 일부인 VIS에서 제대로 작동하려면 Lync 2013이 VIS와 함께 작동하도록 Lync 2013 클라이언트, CAA 및 AVMCU를 업그레이드하는 적절한 CU를 적용해야 합니다.
  
Lync 2013 및 비즈니스용 Skype VIS와의 상호 비즈니스용 Skype 테스트되고 지원됩니다.
  
비 데스크톱(Android, Ipad, Iphone, Windows Phone, LMX 등)과의 VIS 상호 운영성 비즈니스용 Skype 릴리스 당시 해당 앱 스토어에서 사용할 수 있는 클라이언트가 테스트되고 지원됩니다.
  
## <a name="recovery-from-packet-loss-via-fec"></a>FEC를 통한 패킷 손실에서 복구
<a name="resiliency"> </a>

FEC를 켜 패킷 손실로부터 복구할 수 있습니다. 켜져 있는 경우 VIS에서 VTC 방향으로 50% 더 많은 비디오 대역폭이 사용됩니다.
  
## <a name="vis-sizing-and-transcoding-costs"></a>VIS 크기 조정 및 변환 비용
<a name="resiliency"> </a>

Cisco VTC에서 여러 시뮬레이션 스트림으로 단일 비디오 스트림을 변환하는 경우 CPU 용량이 사용됩니다. 약 16개의 VTC는 Lync 2013 권장 FE 플랫폼과 동일한 VIS에서 실행되는 단일 VIS에서 각 VTC의 720p 비디오 스트림이 720p, 360p 및 180p의 3개의 별도 simulcast 스트림으로 코드 변환될 수 있습니다. Transcoding을 해제하면 VIS CPU에 저장됩니다. 그러나 VTC에서 VIS에서 요청하는 비디오 이미지는 가장 낮은 일반 해상도로, 측의 모든 수신기를 비즈니스용 Skype 됩니다. 클라이언트가 VTC에서 보낼 수 없는 특정 낮은 해상도를 비즈니스용 Skype 변환을 해제하는 경우에도 변환이 활성화될 수 있습니다.
  
## <a name="call-distribution-from-the-video-gateway-to-vis"></a>비디오 게이트웨이에서 VIS로의 통화 배포
<a name="resiliency"> </a>

배포는 CUCM 배포 메커니즘 중 하나를 통해 수행됩니다.
  
- DNS를 동적으로 사용
    
- CUCM 쪽에서는 각 트렁크가 VIS 풀의 다른 서버에서 종료되는 개별 트렁크를 정의할 수 있습니다. CUCM은 여러 트렁크를 통해 통화를 라우팅합니다.
    
## <a name="no-hybrid-interoperability"></a>하이브리드 상호 연결성 없음
<a name="resiliency"> </a>

사내 VIS를 통해 온라인 모임에 참가하는 VTC에 대한 지원은 비즈니스용 Skype.
  
## <a name="no-federation-support"></a>페더ation 지원 없음
<a name="resiliency"> </a>

VIS를 통해 페더링된 모임에 참가하는 VTC에 대한 지원은 비즈니스용 Skype.
  
## <a name="see-also"></a>참고 항목
<a name="resiliency"> </a>

[2016에서 비디오 interop 서버 비즈니스용 Skype 서버](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)
