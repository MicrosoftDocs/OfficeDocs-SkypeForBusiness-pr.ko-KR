---
title: 비즈니스용 Skype 서버에 대한 비디오 기반 화면 공유
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 2/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: VbSS(비디오 기반 화면 공유)에 대한 비즈니스용 Skype 서버 계획 및 구성 정보
ms.openlocfilehash: 6c24ad9e2f74495fc616a66472f338f1b0b281d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832768"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a>비즈니스용 Skype 서버에 대한 비디오 기반 화면 공유 
 
비즈니스용 Skype 서버 2015의 VbSS(비디오 기반 화면 공유)를 다운로드할 수 있습니다. 비즈니스용 [Skype 서버 2015 누적 업데이트 KB3061064.](https://www.microsoft.com/download/details.aspx?id=47690) VbSS는 비즈니스용 Skype 서버 2019에 포함되어 있습니다.
  
비디오 기반 화면 공유 또는 VbSS는 Lync 화면 공유에서 증가했습니다. VbSS와 기존 화면 공유의 차이는 사용되는 프로토콜과 Excel에서 사용하는 프로토콜과는 관계가 있습니다. 화면 공유는 사용자 컴퓨터 간에 수천 개의 일대일 세션을 만드는 데 매우 좋은 RDP(원격 데스크톱 프로토콜)를 사용합니다. 새로운 기술인 VbSS는 UDP(User Datagram Protocol)를 사용합니다.
  
비즈니스용 Skype 서버는 사용자 일대일 및 일대다(다대다) 대화 및 모임 환경을 개선하기를 원했습니다. VbSS는 미디어 플랫폼(UDP를 기반 프로토콜로 사용)을 활용하며 비디오 시작 시간, 시청하는 보기 품질(특히 빠르게 시청하는 경우) 및 전반적인 안정성을 개선합니다.
  
화면 공유 개선의 목표는 VbSS와 RDP 간 전환이 발생할 때 최대한 매끄럽게 전환하는 것입니다. VbSS는 비즈니스용 Skype 서버의 화면 공유에 사용되는 기술에 대한 업데이트이기 때문에 네트워크 트래픽에서 SIP 세부 정보를 보거나 빠르게 이동하거나 3D로 빠르게 이동하는 콘텐츠를 공유하지 않는 한 활용하고 있는 기술을 검색하기 어려울 수 있습니다. 예를 들어 작업 공간에 많은 레거시 클라이언트가 있는 경우 RDP를 모임 및 대화에 장애 조치(failsafe)로 계속 사용할 수 있습니다. 비즈니스용 Skype 서버는 내부 논리를 사용하여 클라이언트가 연결할 때 적용할 두 가지 방법(VbSS 또는 기존 화면 공유) 중 어떤 방법을 적용할지 결정합니다. RDP는 상황이 호출될 때 VbSS 대신 사용할 수 있으며 이를 대체하여 보기 환경이 중단되지 않습니다.
  
## <a name="planning"></a>계획

### <a name="vbss-pros-and-cons"></a>VbSS 장단

VbSS로 전환하는 것은 세 가지 주요 개선을 목표로 합니다.
  
1. 화면 공유 만들기(최대 5%) RDP 단독에 비해 안정성이 더 습니다.

2. RDP 단독에 비해 세션 설정 및 비디오 환경을 더 빠르게 만들 수 있습니다(초당 프레임 수가 6:1이 향상되었습니다.)

3. 3D 그래픽과 같은 고성능 콘텐츠를 공유하는 경우에도 낮은 대역폭 조건에서 RDP보다 훨씬 더 잘 작동합니다.
    
이러한 수치는 네트워크의 상태 및 적절한 성능 조정을 사용하며 클라이언트가 모바일 장치에 있는 경우 네트워크 외부에 있을 수 있습니다.
  
또한 공유 콘텐츠의 일부 품질/선명도는 안정성, 속도 및 효율성으로 거래되고 있습니다. 대부분의 경우 이러한 설정은 사용자에게 쉽게 표시되지 않습니다.
  
### <a name="ports-and-protocols"></a>포트 및 프로토콜

**필수 서버 포트**

|**서버 역할**|**서비스 이름**|**포트 또는 포트 범위**|**Protocol(프로토콜)**|**참고**|
|:-----|:-----|:-----|:-----|:-----|
|프런트 엔드 서버  <br/> |비즈니스용 Skype 서버 응용 프로그램 공유 서비스  <br/> |5065  <br/> |TCP  <br/> |응용 프로그램 공유의 받는 SIP 수신 대기 요청에 사용됩니다.  <br/> |
|프런트 엔드 서버  <br/> |비즈니스용 Skype 서버 응용 프로그램 공유 서비스  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |응용 프로그램 공유에 사용되는 미디어 포트 범위입니다.  <br/> |
   
**필수 클라이언트 포트**

|**구성 요소**|**포트 범위**|**Protocol(프로토콜)**|**참고**|
|:-----|:-----|:-----|:-----|
|클라이언트  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |응용 프로그램 공유  <br/> |
   
다음 미디어 포트에 대해 QoS를 사용하도록 설정하고 VbSS도 사용하도록 설정하면 AS MCU를 공유하는 데스크톱이 포함된 회의 중에 화면 공유 트래픽에 대해 아래 굵게 표시된 비디오 포트 설정을 사용합니다. 
  
> [!IMPORTANT]
> 이러한 설정은 특수한 경우로, 이러한 두 기능을 모두 구현할 때 이러한 정확한 설정을 사용해야 합니다. 이 설정은 QoS에 대한 설명서의 다른 권장 설정을 [의합니다.](https://technet.microsoft.com/library/gg405409%28v=ocs.15%29.aspx) 응용 프로그램 공유의 경우 이러한 포트 값을 정의하는 ASMCUSVC.exe 뿐만 아니라 QoS GPO에서 응용 프로그램을 지정해야 합니다. 
  
**응용 프로그램 서버 QoS/VbSS 필수 설정**

|**속성**|**포트 값**|**Protocol(프로토콜)**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |UDP  <br/> |
|AudioPortCount  <br/> |8348  <br/> |UDP  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |UDP  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |UDP  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |TCP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |TCP  <br/> |
   
### <a name="capacity-planning"></a>용량 계획

비즈니스용 Skype 서버 2015 CU2(누적 업데이트 2) 이상을 실행하는 각 프런트 엔드 서버는 RDP를 사용하여 화면 공유를 위해 최대 375명 참가자를 지원합니다(모임당 250개만 지원). VbSS가 도입 및 사용되는 경우 CU3 후의 이 용량은 변경되지 않습니다.
  
테스트에서 성능 및 스트레스 테스트를 수행했기 때문에 자체 배포와 관련하여 다음 측정도 고려해야 합니다(물론 사용 현황에 따라 다를 수 있습니다).
  
전제:
  
- 배포에서 비즈니스용 Skype 서버 2015 CU2 이상을 사용하고 있습니다.
    
- 비즈니스용 Skype 서버 환경의 모든 사용자는 1920x1080보다 높은 화면 해상도를 가집니다.
    
전체 용량(위에서 설명한 대로, 모임당 250명만 가능) 프런트 엔드 서버당 총 375 화면 공유 참가자 수가 375명인 경우 프런트 엔드 서버가 네트워크 카드 1기가비트의 89%를 사용할 수 있습니다. 이는 RDP(비즈니스용 Skype 서버 CU2)의 기존 화면 공유 기술이 발표자 PC의 기본 해상도로 화면 콘텐츠를 전송하기 때문에입니다. 따라서 화면 해상도가 더 높을수록 비즈니스용 Skype 서버 2015 CU2와 화면 공유에 대한 네트워크 병목 현상이 이미 발생하고 있을 수 있습니다.
  
이를 완화하기 위해 다음 옵션 중 하나 이상이 도움이 될 수 있습니다.
  
- 1기가비트 네트워크 카드에서 10기가비트 이더넷 카드로 프런트 엔드 서버를 업그레이드합니다.

- 트래픽 부하를 균형 조정하기 위해 프런트 엔드 서버 수를 늘입니다.

- 두 채널 중 하나에서 사용하는 최대 대역폭에 한도를 설정하여 VbSS 및 RDP에 사용되는 대역폭(비트 속도)을 제한합니다.
    
이 표의 숫자는 개별 네트워크 및 공유되는 콘텐츠의 영향을 습니다. 네트워크 또는 네트워크에 대한 기준을 설정하기 위해 테스트하세요.
  
|**1080p 콘텐츠**|**RDP 평균**|**RDP 최대**|**VbSS 평균**|**VbSS 최대**|
|:-----|:-----|:-----|:-----|:-----|
|PPT  <br/> |200kbps  <br/> |12mbps  <br/> |100kbps  <br/> |3mbps  <br/> |
|CAD  <br/> |3mbps  <br/> |7mbps  <br/> |1mbps  <br/> |3mbps  <br/> |
|비디오  <br/> |5mbps  <br/> |7mbps  <br/> |1.3mbps  <br/> |2.2mbps  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>미디어 트래픽에 대한 네트워크 대역폭 요구 사항

VbSS 대역폭은 다음입니다.
  
|**비디오 코덱**|**해상도 및 가로 세로 비율**|**최대 비디오 페이로드 비트 속도(Kbps)**|**최소 비디오 페이로드 비트 속도(Kbps)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |1920x1080(16:9)  <br/> (세로 비율은 공유자 모니터 해상도에 따라 달라지며 항상 16:9가 아는 것은 아니며)  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>클라이언트 및 서버 지원

비디오 기반 화면 공유에는 비즈니스용 Skype 서버 2015 CU3 이상이 필요하며 비즈니스용 [Skype](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) 및 모임 지원에 대한 모바일 클라이언트 기능 비교에 나열된 지원 클라이언트의 현재 버전이 [필요합니다.](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing) 
  
화면 공유가 RDP로 전환되는 상황이 있습니다.
  
- ASMCU가 VbSS를 지원하는 최소 빌드를 충족하지 않는 환경에서 계정을 호스팅하는 경우
- 이전 버전의 비즈니스용 Skype 클라이언트를 사용하는 사용자가 세션에 참가하는 경우(예: 16.0.6330.1000보다 낮은 Windows 클라이언트 버전, 비즈니스용 Skype 룸 시스템 장치 또는 비즈니스용 Skype 모바일 앱을 사용하는 사용자). 
- 사용자가 비즈니스용 Skype Web App에서 공유하는 경우
- 누군가 Mac에서 비즈니스용 Skype를 사용하고 있으며 비즈니스용 Skype Online 또는 비즈니스용 Skype 서버 2015(2018년 7월 누적 업데이트 이상)에 있지 않은 경우
- 누군가가 프로그램/Windows 공유를 시작하는 경우.
- 누군가 세션 녹음/녹화를 시작하는 경우
- 세션 중에 원격 화면 제어를 호출하는 경우 
- 참가자가 250명 이상인 모임(현재 VbSS가 지원되지 않는 경우)

세션이 RDP로 전환된 경우 VbSS로 다시 전환되지 않습니다. 또한 VbSS에서 전환하는 것은 매끄럽게 하기 위한 것이기 때문에 대부분의 상황에서는 이를 감지하기가 쉽지 않습니다.
    
> [!NOTE]
> 비즈니스용 Skype 화면 공유에서 VbSS에서 RDP로의 전환을 차단하거나 차단하려고 할 수 없습니다. 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>VbSS 사용, 사용 안 하게 설정 및 구성

좋은 점은 비즈니스용 Skype 서버 2015 CU3(누적 업데이트 3) 이상을 설치하면 모든 사용자가 기본적으로 일대일 및 다자 VbSS를 사용할 수 있도록 설정됩니다. 모든 사용자에 대해 이 기능을 사용하도록 설정하지 않은 이유가 있는 경우 이 문제가 될 수 있습니다. 이 경우 다음 단계를 사용하여 사용자를 사용하지 않도록 설정할 수 있습니다(사용자 사용 단계가 수행됨).
  
### <a name="how-to-disable-users-from-using-vbss"></a>사용자가 VbSS를 사용하지 않도록 설정하는 방법

- 비즈니스용 Skype 관리 콘솔에서 이 cmdlet을 실행하여 VbSS를 사용할 수 없는 사용자에게 VbSS를 허용하지 않는 사용자 정책을 할당할 수 있습니다([PolicyName] 대신 이 작업을 수행 중인 정책).
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- 또한 할당된 정책이 없는 모든 사용자에게 영향을 주는 전역 회의 정책을 업데이트할 수 있습니다.
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    이 명령에 대한 자세한 내용은 [Set-CsConferencingPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)
    
- VbSS를 완전히 해제해야 하는 경우 다음 명령을 실행할 수 있습니다.
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    이 명령에 대한 자세한 내용은 [Set-CsMediaConfiguration을 참조하십시오.](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)
    
> [!NOTE]
> 여러 비즈니스용 Skype 모임에서 모든 클라이언트 끝점은 모임 이끌이에 대한 정책 설정을 적용합니다. 
  
### <a name="how-to-enable-users-to-use-vbss"></a>사용자가 VbSS를 사용하도록 설정하는 방법

- 비즈니스용 Skype 관리 콘솔에서 이 cmdlet을 실행하여 VbSS를 사용해야 하는 모든 사용자에게 VbSS를 허용하는 특정 사용자 정책을 할당할 수 있습니다(이 작업을 수행 중인 정책으로 [PolicyName] 바꾸기).
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- 또한 할당된 정책이 없는 모든 사용자에게 영향을 주는 전역 회의 정책을 업데이트할 수 있습니다.
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    이 명령에 대한 자세한 내용은 [Set-CsConferencingPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)
    
- VbSS를 끄고(기본적으로 켜진) VbSS를 다시 켜야 하는 경우 다음 명령을 실행할 수 있습니다.
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    이 명령에 대한 자세한 내용은 [Set-CsMediaConfiguration을 참조하십시오.](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)
    
> [!NOTE]
> 여러 비즈니스용 Skype 모임에서 모든 클라이언트 끝점은 모임 이끌이에 대한 정책 설정을 적용합니다. 
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버 2015 누적 업데이트 KB3061064](https://www.microsoft.com/download/details.aspx?id=47690)
  
[VBSS(비디오 기반 화면 공유)는 비즈니스용 Skype 서버에서 사용할 수 있습니다.](https://support.microsoft.com/kb/3170163)
