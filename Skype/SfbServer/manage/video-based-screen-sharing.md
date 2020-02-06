---
title: 비즈니스용 Skype 서버에 대한 비디오 기반 화면 공유
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
ms.openlocfilehash: f0d474772b94389c1d69264be61b3bee2b46a385
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817048"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a>비즈니스용 Skype 서버에 대한 비디오 기반 화면 공유 
 
비즈니스용 Skype 서버 2015에서 비디오 기반 화면 공유 (VbSS) 지금 다운로드 가능: 비즈니스용 [Skype server 2015 누적 업데이트 KB3061064](https://www.microsoft.com/en-us/download/details.aspx?id=47690). VbSS는 비즈니스용 Skype 서버 2019에 포함 되어 있습니다.
  
비디오 기반 화면 공유 또는 VbSS는 Lync 화면 공유에서 증가 합니다. VbSS와 전통적인 화면 공유의 차이는 사용 된 기본 프로토콜과 excel의 기능에 따라 수행 해야 합니다. 화면 공유는 RDP (원격 데스크톱 프로토콜)를 사용 하며,이는 사용자의 컴퓨터 간에 수천 대의 일대일 세션을 만들 때 유용 합니다. 새로운 기술인 VbSS는 사용자 데이터 그램 프로토콜 (UDP)을 사용 합니다.
  
비즈니스용 Skype 서버는 사용자의 일대일, 일대일 (멀티 파티) 대화 및 모임 환경을 개선 하기 위해 필요 합니다. VbSS는 미디어 플랫폼을 사용 하 여 비디오 시작 시간을 개선 하는 목표로, 시청 하는 항목의 시청 품질 (특히 시청 하 고 있는 경우) 및 전체적으로 안정성을 보장 합니다.
  
화면 공유를 개선 하는 목표의 일환으로, VbSS와 RDP 간의 전환이 가능한 한 원활 하 게 이루어집니다. VbSS는 비즈니스용 Skype 서버용 화면 공유에 사용 되는 기본 기술에 대 한 업데이트 이므로 네트워크 트래픽에 SIP 세부 정보를 보고 있거나 콘텐츠를 공유 하 고 있는 경우를 제외 하 고 이용 하는 기술을 감지 하기 어려울 수 있습니다. 빠른 이동 또는 3 차원입니다. 예를 들어 회사에서 많은 레거시 클라이언트를 사용 하는 경우에도 사용자의 모임 및 대화에 대 한 비상 용으로 RDP를 사용할 수 있습니다. 비즈니스용 Skype 서버는 내부 논리를 사용 하 여 클라이언트가 연결할 때 적용 되는 두 가지 방법 (VbSS 또는 기존 화면 공유)을 결정 합니다. RDP는 해당 상황이 발생할 때 VbSS를 대체 하 여 보기 환경이 중단 되지 않도록 할 수 있습니다.
  
## <a name="planning"></a>계획

### <a name="vbss-pros-and-cons"></a>VbSS 장점 및 단점

다음 세 가지 주요 향상을 위해 VbSS 목표로 전환 합니다.
  
1. 화면 공유 만들기 (최대 5%) RDP 단독으로 더욱 안정적으로 비교 합니다.

2. 세션 설정 및 비디오 환경을 RDP에 비해 더 빠르게 (1 초에 6:1 개선 된 시간 후에 설치 하 여 수행)

3. 3 차원 그래픽과 같은 높은 모션 콘텐츠를 공유 하는 경우에도 낮은 대역폭 조건의 RDP 보다 훨씬 더 효과적으로 작동 합니다.
    
이러한 번호는 네트워크의 상태 및 적절 한 성능 조정에 따라 달라 지 며 클라이언트가 모바일 장치를 사용 하 고 있는 경우에는 자신의 외부 네트워크를 포함할 수 있습니다.
  
또한 공유 콘텐츠의 일부 충실도/crispness 신뢰성, 속도 및 효율성에 대 한 것 이라는 점을 알아야 합니다. 대부분의 경우 사용자는이를 쉽게 볼 수 없습니다.
  
### <a name="ports-and-protocols"></a>포트 및 프로토콜

**필요한 서버 포트**

|**서버 역할**|**서비스 이름**|**포트 또는 포트 범위**|**프로토콜별**|**상속자**|
|:-----|:-----|:-----|:-----|:-----|
|프런트 엔드 서버  <br/> |비즈니스용 Skype 서버 응용 프로그램 공유 서비스  <br/> |5065  <br/> |NET.TCP  <br/> |응용 프로그램 공유에 대 한 수신 SIP 수신 요청에 사용 됩니다.  <br/> |
|프런트 엔드 서버  <br/> |비즈니스용 Skype 서버 응용 프로그램 공유 서비스  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |응용 프로그램 공유에 사용 되는 미디어 포트 범위입니다.  <br/> |
   
**필수 클라이언트 포트**

|**요소가**|**포트 범위**|**프로토콜별**|**상속자**|
|:-----|:-----|:-----|:-----|
|클라이언트  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |응용 프로그램 공유  <br/> |
   
다음 미디어 포트에 QoS를 사용 하는 경우 데스크톱 공유를 포함 하는 회의 중에도이를 사용 하는 경우에는 화면 공유 트래픽에 대해 아래 굵게 표시 된 비디오 포트 설정을 사용할 수 있습니다. 
  
> [!IMPORTANT]
> 이러한 설정은 특별 한 경우 이며 이러한 기능을 모두 구현할 때는 이러한 정확한 설정을 사용 해야 합니다. 이렇게 하면 [QoS 설명서](https://technet.microsoft.com/en-us/library/gg405409%28v=ocs.15%29.aspx)의 다른 권장 설정이 재정의 됩니다. 또한 응용 프로그램 공유를 위해 이러한 포트 값을 정의 하는 것 외에도 QoS GPO에서 ASMCUSVC .exe를 지정 해야 합니다. 
  
**Application Server QoS/VbSS 필요 설정**

|**속성**|**포트 값**|**프로토콜별**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |UDP  <br/> |
|AudioPortCount  <br/> |8348  <br/> |UDP  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |UDP  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |UDP  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |NET.TCP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |NET.TCP  <br/> |
   
### <a name="capacity-planning"></a>용량 계획

비즈니스용 Skype Server 2015 누적 업데이트 2) 이상을 실행 하는 각 프런트 엔드 서버는 RDP를 사용 하 여 화면을 공유 하는 데 최대 375 명의 참가자를 지원 합니다 (모임 당 250만 해당). 이 용량으로는 VbSS가 도입 되 고 사용 되는 경우 CU3 이상가 변경 되지 않습니다.
  
즉, 우리의 랩에서 성능 및 스트레스 테스트를 완료 했으며, 사용 방법에 따라 사용자의 배포와 관련 하 여 다음 측정법도 고려해 야 합니다.
  
되었다는
  
- 배포에서 비즈니스용 Skype 서버 2015 CU2 이상을 사용 하 고 있습니다.
    
- 비즈니스용 Skype 서버 환경의 모든 사용자에 게 1920x1080 보다 높은 화면 해상도가 있습니다.
    
전체 용량 (위에서 언급 한 것 처럼, 각 프런트 엔드 서버에는 375 화면 공유 참가자는 모임 당 250만 해당) 이지만, 프런트 엔드 서버는 1 기가 비트의 네트워크 카드 중 ~ 89%를 이용 하 고 있을 수 있습니다. 이는 비즈니스용 Skype 서버 CU2 (RDP)의 기존 화면 공유 기술이 화면 콘텐츠를 발표자 PC의 기본 해상도로 전송 하기 때문입니다. 더 높은 화면 해상도를 사용 하는 경우 비즈니스용 Skype 서버 2015 CU2의 화면 공유에 대 한 네트워크 병목 현상이 이미 발생 했을 수 있습니다.
  
이를 줄이기 위해 다음 옵션 중 하나 이상을 유용 하 게 사용할 수 있습니다.
  
- 1 기가 비트 네트워크 카드에서 10 기가 비트 이더넷 카드로 프런트 엔드 서버를 업그레이드 합니다.

- 프런트 엔드 서버 수를 늘려 트래픽을 부하 분산 합니다.

- 각 채널에서 사용 하는 최대 대역폭에 cap를 추가 하 여 VbSS 및 RDP에 사용 되는 대역폭 (비트 전송률)을 제한 합니다.
    
이 표에 나와 있는 숫자는 개별 네트워크와 공유 하는 콘텐츠의 영향을 받습니다. 테스트 하 여 네트워크 또는 네트워크에 대 한 기준을 설정 하십시오.
  
|**1080p 콘텐츠**|**RDP 평균**|**RDP 피크**|**VbSS 평균**|**VbSS 피크**|
|:-----|:-----|:-----|:-----|:-----|
|PPT  <br/> |200kbps  <br/> |12mbps  <br/> |100kbps  <br/> |3mbps  <br/> |
|CAD  <br/> |3mbps  <br/> |7mbps  <br/> |1mbps  <br/> |3mbps  <br/> |
|비디오만  <br/> |5mbps  <br/> |7mbps  <br/> |1.3 mbps  <br/> |2.2 mbps  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>미디어 트래픽에 대 한 네트워크 대역폭 요구 사항

VbSS 대역폭:
  
|**비디오 코덱**|**해상도 및 가로 세로 비율**|**최대 비디오 페이로드 비트 전송률 (Kbps)**|**최소 비디오 페이로드 비트 전송률 (Kbps)**|
|:-----|:-----|:-----|:-----|
|H. 264  <br/> |1920x1080 (16:9)  <br/> 가로 세로 비율은 공유자의 모니터 해상도에 따라 다르며 항상 16:9 일 수는 없습니다.  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>클라이언트 및 서버 지원

비디오 기반 화면 공유에는 비즈니스용 Skype Server 2015 CU3 이상 이상이 필요 하며, [모바일 클라이언트 기능](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) 에 나열 된 지원 클라이언트의 최신 버전이 비즈니스용 Skype 및 [모임 지원](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)에 대해 설명 합니다. 
  
다음과 같이 화면 공유를 RDP로 전환 하는 경우가 있습니다.
  
- 계정에서 ASMCU가 VbSS를 지 원하는 최소 빌드를 충족 하지 않는 환경에서 호스트 되는 경우
- 이전 버전의 비즈니스용 Skype 클라이언트를 사용 하는 다른 사용자가 16.0.6330.1000 보다 낮은 Windows 클라이언트 버전을 사용 하는 경우 (예: 비즈니스용 skype 실 시스템 장치 또는 비즈니스용 Skype 모바일 앱)에는 사용자의 세션에 참가 합니다. 
- 사용자가 비즈니스용 Skype Web App에서 공유 하는 경우
- 다른 사용자가 Mac에서 비즈니스용 Skype를 사용 하 고 있고 비즈니스용 Skype Online 또는 2006 년 7 월에 비즈니스용 Skype 서버 2015 (2018 누적 업데이트 (또는 이후 버전))가 아닌 경우
- 다른 사용자가 프로그램/Windows 공유를 시작 하는 경우
- 누군가 세션 기록을 시작 합니다.
- 다른 사용자가 세션 중에 원격 화면 제어를 호출 하는 경우 
- 250 명 이상의 참가자가 있는 모임 (VbSS가 현재 지원 되지 않는 경우)

세션을 RDP로 전환 하면 다시 VbSS로 전환 되지 않습니다. 여기서는 VbSS를 전환 하는 것이 원활 하 고, 대부분의 상황에서 쉽게 검색할 수 없는 것을 기대 합니다.
    
> [!NOTE]
> 비즈니스용 Skype 화면 공유에서 VbSS에서 RDP로의 전환을 차단 또는 차단 하는 것은 지원 되지 않습니다. 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>VbSS 사용, 사용 안 함 및 구성

좋은 점은 비즈니스용 Skype Server 2015 누적 업데이트 3 (CU3 이상) 이상을 설치한 후에 기본적으로 모든 사용자가 일대일 및 multi VbSS를 사용 하도록 설정 하는 것입니다. 이 기능이 모든 사용자에 대해 사용 하도록 설정 되지 않은 경우에는 문제가 발생할 수 있습니다. 이 경우 다음 단계를 사용 하 여 사용자를 사용 하지 않도록 설정할 수 있습니다 (사용자의 단계를 따를 수 있음).
  
### <a name="how-to-disable-users-from-using-vbss"></a>사용자가 VbSS를 사용할 수 없도록 설정 하는 방법

- 비즈니스용 Skype 관리 콘솔에서이 cmdlet을 실행 하 여 vbss를 사용 하 고 있지 않은 사용자 ([PolicyName]를 다음에 대 한 정책으로 바꾸기)에 할당할 수 있습니다.
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- 할당 된 정책이 없는 모든 사용자에 게 영향을 주는 전역 회의 정책을 업데이트할 수도 있습니다.
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    이 명령에 대 한 자세한 내용은 [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)를 참조 하세요.
    
- VbSS를 완전히 해제 해야 하는 경우 다음 명령을 실행할 수 있습니다.
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    이 명령에 대 한 자세한 내용은 [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)를 참조 하세요.
    
> [!NOTE]
> 단체 Skype 모임에서 모든 클라이언트 끝점은 모임 이끌이의 정책 설정을 준수 합니다. 
  
### <a name="how-to-enable-users-to-use-vbss"></a>사용자가 VbSS를 사용할 수 있도록 설정 하는 방법

- 비즈니스용 Skype 관리 콘솔에서이 cmdlet을 실행 하 여 vbss를 사용 해야 하는 특정 사용자 정책을 할당할 수 있습니다 ([PolicyName]을이 작업을 수행 하는 정책으로 바꾸기).
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- 할당 된 정책이 없는 모든 사용자에 게 영향을 주는 전역 회의 정책을 업데이트할 수도 있습니다.
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    이 명령에 대 한 자세한 내용은 [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)를 참조 하세요.
    
- 전원을 끈 후에 (기본적으로 켜져 있음), VbSS를 다시 설정 해야 하는 경우에는 다음 명령을 실행할 수 있습니다.
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    이 명령에 대 한 자세한 내용은 [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)를 참조 하세요.
    
> [!NOTE]
> 파티 비즈니스용 Skype 모임에서 모든 클라이언트 끝점은 모임 이끌이의 정책 설정을 준수 합니다. 
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버 2015 누적 업데이트 KB3061064](https://www.microsoft.com/en-us/download/details.aspx?id=47690)
  
[비즈니스용 Skype Server 2015에서 비디오 기반 화면 공유 (VBSS)를 사용할 수 있음](https://support.microsoft.com/en-us/kb/3170163)
