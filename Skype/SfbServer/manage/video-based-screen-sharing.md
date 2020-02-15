---
title: 비즈니스용 Skype 서버에 대 한 비디오 기반 화면 공유
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: 비디오 기반 화면 공유에 대 한 비즈니스용 Skype 서버 계획 및 구성 정보 (VbSS)
ms.openlocfilehash: d6b66da2994db892bc193103bca75e844c62197f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009571"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a>비즈니스용 Skype 서버에 대 한 비디오 기반 화면 공유 
 
이제 비즈니스용 Skype 서버 2015에서 비디오 기반 화면 공유 (VbSS)를 다운로드할 수 있습니다. [비즈니스용 Skype 서버 2015 누적 업데이트 KB3061064](https://www.microsoft.com/download/details.aspx?id=47690). VbSS는 비즈니스용 Skype 서버 2019에 포함 되어 있습니다.
  
비디오 기반 화면 공유 또는 VbSS가 Lync 화면 공유에서 증가 합니다. VbSS와 전통적인 화면 공유의 차이점은 사용 된 기본 프로토콜과 excel에서 수행 해야 합니다. 화면 공유에서는 RDP (원격 데스크톱 프로토콜)를 사용 하므로 사용자 컴퓨터 간에 수천 개의 세션을 만들 때 매우 유용 합니다. 신형 기술인 VbSS는 UDP (사용자 데이터 그램 프로토콜)를 사용 합니다.
  
비즈니스용 Skype 서버는 사용자의 일대일 및 일대다 (멀티 파티) 대화 및 모임 환경을 개선 하기 위해 원했습니다. VbSS는 미디어 플랫폼을 기본 프로토콜로 사용 하 여, 비디오 시작 시간을 개선 하는 목표, 시청 하 고 있는 대상의 품질 (특히 시청 하 고 있는 작업을 수행 하는 경우)을 전체적으로 확인 하는 등의 작업을 수행 합니다.
  
화면 공유 기능을 향상 시킬 수 있는 목표 중 일부는 VbSS와 RDP 간의 전환이 가능한 한 원활 하 게 진행 된다는 것입니다. VbSS는 비즈니스용 Skype 서버에 대 한 화면 공유에 사용 되는 기본 기술에 대 한 업데이트 이므로 네트워크 트래픽에 SIP 세부 정보를 확인 하거나 콘텐츠를 공유 하는 경우가 아니면 활용 중인 기술을 검색 하기 어려울 수 있습니다. 은 빠른 이동 이나 3 차원입니다. 예를 들어 회사의 레거시 클라이언트가 많은 경우에도 사용자의 모임 및 대화에 대 한 안전에 따라 RDP를 사용할 수 있습니다. 비즈니스용 Skype 서버는 내부 논리를 사용 하 여 클라이언트가 연결할 때 적용할 두 가지 방법 (VbSS 또는 전통적인 화면 공유)을 결정 합니다. RDP가 요청을 호출 하는 경우, 사용자의 보기 환경이 중단 되지 않도록이를 요청할 수 있습니다.
  
## <a name="planning"></a>계획

### <a name="vbss-pros-and-cons"></a>VbSS의 장단점

VbSS 목표로 전환 하면 다음과 같은 세 가지 주요 기능을 향상 시킬 수 있습니다.
  
1. 화면 공유 설정 (최대 5%) 신뢰할 수 있는 RDP에 비해 더 안정적입니다.

2. RDP를 사용 하는 경우에 비해 세션 설정 및 비디오 환경이 더 빠르게 수행 되도록 설정 (2 초에 6:1을 개선 하는 동시에 시간을 절반으로 설치) 합니다.

3. 3 차원 그래픽과 같은 높은 모션 콘텐츠를 공유 하는 경우에도 낮은 대역폭 조건의 RDP 보다 훨씬 더 효율적으로 작동 합니다.
    
이러한 수치는 네트워크의 상태 및 적절 한 성능 조정에 의존 하며, 클라이언트가 모바일 장치에 있는 경우에는 자체 외부 네트워크를 포함할 수 있습니다.
  
또한 공유 콘텐츠의 일부 충실도/crispness가 안정성, 속도 및 효율성을 위한 것 이라는 점을 알고 있어야 합니다. 대부분의 경우이는 사용자에 게 즉시 표시 되지 않습니다.
  
### <a name="ports-and-protocols"></a>포트 및 프로토콜

**필요한 서버 포트**

|**서버 역할**|**서비스 이름**|**포트 또는 포트 범위**|**프로토콜**|**참고**|
|:-----|:-----|:-----|:-----|:-----|
|프런트 엔드 서버  <br/> |비즈니스용 Skype 서버 응용 프로그램 공유 서비스  <br/> |5065  <br/> |TCP  <br/> |응용 프로그램 공유의 받는 SIP 수신 대기 요청에 사용됩니다.  <br/> |
|프런트 엔드 서버  <br/> |비즈니스용 Skype 서버 응용 프로그램 공유 서비스  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |응용 프로그램 공유에 사용되는 미디어 포트 범위입니다.  <br/> |
   
**필요한 클라이언트 포트**

|**구성 요소**|**포트 범위**|**프로토콜**|**참고**|
|:-----|:-----|:-----|:-----|
|클라이언트  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |응용 프로그램 공유  <br/> |
   
다음 미디어 포트에 대해 QoS가 사용 하도록 설정 되어 있고 VbSS가 사용 되도록 설정 된 경우 데스크톱 공유를 포함 하는 회의 중에는 화면 공유 트래픽에 아래 굵게 표시 된 비디오 포트 설정을 사용 합니다. 
  
> [!IMPORTANT]
> 이러한 설정은 특수 한 경우 이며, 이러한 기능을 모두 구현할 때 이러한 설정을 사용 해야 합니다. 이렇게 하면 [QoS 설명서](https://technet.microsoft.com/library/gg405409%28v=ocs.15%29.aspx)의 기타 권장 설정이 재정의 됩니다. 응용 프로그램 공유의 경우 QoS GPO에서 ASMCUSVC를 지정 해야 하며 이러한 포트 값을 정의할 수도 있습니다. 
  
**Application Server QoS/VbSS 필요한 설정**

|**속성**|**포트 값**|**프로토콜**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |P  <br/> |
|AudioPortCount  <br/> |8348  <br/> |P  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |P  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |P  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |TCP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |TCP  <br/> |
   
### <a name="capacity-planning"></a>용량 계획

비즈니스용 Skype 서버 2015 C U 2 (누적 업데이트 2) 이상을 실행 하는 각 프런트 엔드 서버는 RDP를 사용 하 여 화면을 공유 하기 위해 최대 375 명의 참가자를 지원 합니다 (모임 당 250만 해당). 이 용량은 VbSS가 도입 되 고 사용 될 때 C U 3를 변경 하지 않습니다.
  
즉, 랩에서는 성능 및 스트레스 테스트를 완료 했으며, 사용에 따라 다음 측정법도 사용자의 배포와 관련 하 여 고려해 야 합니다.
  
없다고
  
- 배포에서 비즈니스용 Skype 서버 2015 C U 2 이상 버전을 사용 하 고 있습니다.
    
- 비즈니스용 Skype 서버 환경의 모든 사용자에 게는 해상도 1920x1080 보다 높은 화면 해상도가 있습니다.
    
위에서 설명한 대로 전체 용량 (위에 설명 된 것 처럼, 모든 프런트 엔드 서버에서 총 1 회 (모임 당 250)로 표시 됨)에는 프런트 엔드 서버에서 375 비트의 네트워크 카드를 89 사용할 수 있습니다. 이는 lync (비즈니스용 Skype 서버 C U 2)의 기존 화면 공유 기술이 발표자 PC의 기본 해상도로 화면상의 콘텐츠를 전송 하기 때문입니다. 더 높은 화면 해상도가 사용 되는 경우에는 비즈니스용 Skype 서버 2015 C U 2의 화면 공유에 대 한 네트워크 병목 현상이 이미 발생 했을 수 있습니다.
  
이를 완화 하기 위해 다음 옵션 중 하나 이상이 도움이 될 수 있습니다.
  
- 1 기가 비트 네트워크 카드에서 10 기가 비트 이더넷 카드로 프런트 엔드 서버를 업그레이드 합니다.

- 프런트 엔드 서버의 수를 늘려 트래픽을 부하 분산 합니다.

- 각 채널에서 사용 되는 최대 대역폭에 cap를 추가 하 여 VbSS 및 RDP에 사용 되는 대역폭 (비트 전송률)을 제한 합니다.
    
이 표에 나와 있는 숫자는 개별 네트워크와 공유 되는 콘텐츠의 영향을 받습니다. 테스트를 통해 네트워크 또는 네트워크에 대 한 기준을 설정 하십시오.
  
|**1080p Content**|**RDP 평균**|**RDP 피크**|**VbSS 평균**|**VbSS 피크**|
|:-----|:-----|:-----|:-----|:-----|
|.PPT  <br/> |200kbps  <br/> |12mbps  <br/> |100kbps  <br/> |3mbps  <br/> |
|CAD  <br/> |3mbps  <br/> |7mbps  <br/> |1mbps  <br/> |3mbps  <br/> |
|비디오  <br/> |5mbps  <br/> |7mbps  <br/> |1.3 mbps  <br/> |2.2 mbps  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>미디어 트래픽에 대 한 네트워크 대역폭 요구 사항

VbSS 대역폭은 다음과 같습니다.
  
|**비디오 코덱**|**해상도 및 가로 세로 비율**|**최대 비디오 페이로드 비트 전송률 (Kbps)**|**최소 비디오 페이로드 비트 전송률 (Kbps)**|
|:-----|:-----|:-----|:-----|
|.H. 264  <br/> |해상도 1920x1080 (16:9)  <br/> 가로 세로 비율은 공유자의 모니터 해상도에 따라 다르며 항상 16:9이 아닙니다.  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>클라이언트 및 서버 지원

비디오 기반 화면 공유를 사용 하려면 비즈니스용 Skype 서버 2015 C U 3 이상이 필요 하며, [모바일 클라이언트 기능](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) 에 나열 된 지원 클라이언트의 현재 버전은 비즈니스용 Skype 및 [모임 지원을 지원](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)합니다. 
  
다음과 같이 화면 공유가 RDP로 전환 되는 경우가 있습니다.
  
- 계정이 VbSS를 지 원하는 최소 빌드를 충족 하지 않는 환경에서 호스트 되는 경우
- 이전 버전의 비즈니스용 Skype 클라이언트를 사용 하는 사용자가 16.0.6330.1000 보다 낮은 Windows 클라이언트 버전을 사용 하는 경우 (예: 비즈니스용 Skype 대화방 시스템 장치 또는 비즈니스용 Skype 모바일 앱) 사용자의 세션에 참가 합니다. 
- 사용자가 비즈니스용 Skype Web App에서 공유 하는 경우
- 다른 사용자가 Mac에서 비즈니스용 Skype를 사용 하 고 있고 비즈니스용 skype Online 또는 비즈니스용 skype 서버 2015에서 7 월, 2018 누적 업데이트 (이상)가 있는 경우는 그렇지 않습니다.
- 다른 사용자가 프로그램/Windows 공유를 시작 하는 경우
- 누군가 세션 기록을 시작 합니다.
- 세션 중에 다른 사용자가 원격 화면 제어를 호출 하는 경우 
- 참가자가 250 명 이상인 모임 (현재 VbSS가 지원 되지 않음)

세션이 RDP로 전환 되 면 다시 VbSS로 전환 되지 않습니다. 다시 말하지만, VbSS 로부터의 전환은 원활한 것 이며, 대부분의 상황에서 쉽게 검색할 수 있는 것은 아닙니다.
    
> [!NOTE]
> 비즈니스용 Skype 화면 공유에서 VbSS에서 RDP로의 전환을 차단 하거나 차단을 시도할 수 없습니다. 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>VbSS 사용, 사용 안 함 및 구성

C U 3 (비즈니스용 Skype 서버 2015 누적 업데이트 3) 이상을 설치한 후에는 모든 사용자가 기본적으로 1 ~ 1, 멀티 당사자 VbSS를 사용할 수 있습니다. 모든 사용자에 대해이 기능을 사용 하도록 설정 하지 않은 이유가 있는 경우에는이로 인해 문제가 발생할 수 있습니다. 이 경우 다음 단계를 사용 하 여 사용자가 사용 하지 않도록 설정할 수 있습니다 (사용자 단계를 수행할 수 있음).
  
### <a name="how-to-disable-users-from-using-vbss"></a>사용자가 VbSS를 사용 하지 못하도록 설정 하는 방법

- 비즈니스용 Skype 관리 콘솔에서이 cmdlet을 실행 하 여 vbss를 사용 하지 않는 사용자에 게 vbss를 허용 하지 않는 사용자 정책을 할당할 수 있습니다 ([PolicyName]을이 작업을 수행 하는 정책으로 바꾸기).
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- 또한 할당 된 정책이 없는 모든 사용자에 게 영향을 주는 전역 회의 정책을 업데이트할 수 있습니다.
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    이 명령에 대 한 자세한 내용은 [get-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)를 참조 하십시오.
    
- VbSS를 완전히 해제 해야 하는 경우 다음 명령을 실행할 수 있습니다.
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    이 명령에 대 한 자세한 내용은 [get-csmediaconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)를 참조 하십시오.
    
> [!NOTE]
> 단체 비즈니스용 Skype 모임에서 모든 클라이언트 끝점은 모임 이끌이의 정책 설정을 고려 합니다. 
  
### <a name="how-to-enable-users-to-use-vbss"></a>사용자가 VbSS를 사용할 수 있도록 설정 하는 방법

- 비즈니스용 Skype 관리 콘솔에서이 cmdlet을 실행 하 여 vbss를 사용 해야 하는 사용자에 게 PolicyName를 허용 하는 특정 사용자 정책을 할당할 수 있습니다.
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- 또한 할당 된 정책이 없는 모든 사용자에 게 영향을 주는 전역 회의 정책을 업데이트할 수 있습니다.
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    이 명령에 대 한 자세한 내용은 [get-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)를 참조 하십시오.
    
- 일단 전원을 끈 후에 VbSS를 해제 해야 하는 경우 (기본적으로 설정), 다음 명령을 실행할 수 있습니다.
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    이 명령에 대 한 자세한 내용은 [get-csmediaconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)를 참조 하십시오.
    
> [!NOTE]
> 여러 사용자의 비즈니스용 Skype 모임에서 모든 클라이언트 끝점은 모임 이끌이의 정책 설정을 고려 합니다. 
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버 2015 누적 업데이트 KB3061064](https://www.microsoft.com/download/details.aspx?id=47690)
  
[비즈니스용 Skype 서버 2015에서 비디오 기반 화면 공유 (VBSS)를 사용할 수 있음](https://support.microsoft.com/kb/3170163)
