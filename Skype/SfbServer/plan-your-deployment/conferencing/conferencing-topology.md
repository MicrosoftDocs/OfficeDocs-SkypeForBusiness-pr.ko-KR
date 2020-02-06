---
title: 비즈니스용 Skype 서버에 대 한 회의 토폴로지 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7392dfa7-791a-4723-88ff-0ef8a9ef11c8
description: '요약: 비즈니스용 Skype 서버에서 회의 토폴로지를 계획 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.'
ms.openlocfilehash: 1b9d9024d90b4bd847c763747dad7a5f96616aa3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816017"
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server"></a>비즈니스용 Skype 서버에 대 한 회의 토폴로지 계획
 
**요약:** 비즈니스용 Skype 서버에서 회의 토폴로지를 계획 하는 방법에 대해 자세히 알아보려면이 항목을 참조 하세요.
  
이 항목에서는 비즈니스용 Skype 서버의 회의에 대 한 토폴로지 기본 사항에 대해 설명 합니다.
  
- 지원되는 토폴로지
    
- 전화 접속 회의 고려 사항
    
- 웹 회의 고려 사항
    
- 대규모 모임에 대 한 요구 사항
    
하드웨어 및 소프트웨어 요구 사항에 대 한 자세한 내용은 [비즈니스용 Skype 서버에서 회의를 위한 하드웨어 및 소프트웨어 요구 사항을](hardware-and-software-requirements.md)참조 하세요.
  
## <a name="supported-topologies"></a>지원되는 토폴로지

비즈니스용 Skype Server에서 회의 서비스를 실행 하는 서버는 항상 프런트 엔드 서버 또는 Standard Edition 서버와 collocated 됩니다. 비즈니스용 Skype 서버를 배포 하는 경우 메신저 대화 회의 기능이 자동으로 배포 됩니다. 토폴로지 작성기를 사용 하 여 웹, 오디오 및 비디오 (A/V)를 배포할지 여부와 전화 접속 회의를 지정할 수 있습니다. 토폴로지 작성기를 사용 하 여 기존 배포에 회의를 추가할 수도 있습니다. 토폴로지 기본 사항 및 콜론 위치 시나리오에 대 한 자세한 내용은 [비즈니스용 Skype 서버에 대 한 토폴로지 기본 사항을](../../plan-your-deployment/topology-basics/topology-basics.md)참조 하세요.
  
다음과 같은 토폴로지와 구성으로 회의를 배포할 수 있습니다.
  
- 비즈니스용 Skype Server Standard Edition
    
- 비즈니스용 Skype Server Enterprise Edition
    
- 기업 음성이 있거나 없는 경우
    
## <a name="dial-in-conferencing-considerations"></a>전화 접속 회의 고려 사항

전화 접속 회의를 배포 하는 경우 다음 사항을 고려해 야 합니다.
  
- 전화 접속 회의에는 비즈니스용 Skype 서버와 PSTN 게이트웨이 간의 신호 및 미디어를 번역 하는 조정 서버가 필요 하며, 중재 서버와 PSTN 게이트웨이 간에 신호 및 미디어를 번역 하는 PSTN 게이트웨이 .
    
   전화 접속 회의를 구성 하려면 먼저 엔터프라이즈 음성 또는 중재 서버를 배포 하 고 다음 중 하나 이상을 실행 해야 합니다.
    
  - PSTN 게이트웨이
    
  - IP-PBX
    
  - SBC (세션 경계 컨트롤러) (SIP 트렁크 구성으로 연결 되는 인터넷 전화 통신 서비스 공급자의 경우)
    
- 중앙 사이트에는 응용 프로그램 서비스, 회의 수행자 응용 프로그램, 회의 알림 응용 프로그램을 배포할 수 있지만 분기 사이트에 있는 경우는 안 됩니다.
    
- 비즈니스용 Skype 서버 회의를 배포 하는 모든 풀에 전화 접속 회의를 배포 해야 합니다. 모든 풀에 액세스 번호를 할당할 필요는 없지만 모든 풀에 전화 접속 회의 기능을 배포 해야 합니다. 이 요구 사항은 사용자가 한 풀의 액세스 번호를 호출 하 여 다른 풀의 비즈니스용 Skype 서버 컨퍼런스에 참가 하는 경우 기록 된 이름 기능을 지원 합니다. 
    
자세한 내용은 [비즈니스용 Skype 서버의 전화 접속 회의 계획](dial-in-conferencing.md)을 참조 하세요.
  
## <a name="web-conferencing-considerations"></a>웹 회의 고려 사항

웹 회의에는 다음이 필요 합니다. 
  
- 웹 회의 콘텐츠를 저장 하는 데 사용 되는 파일 저장소에 액세스할 수 있습니다.
    
- 회의 중에 PowerPoint 파일을 공유 하기 위해 필요한 Office Web Apps Server/Office Online Server와 통합
    
> [!NOTE]
> Office Web Apps Server의 최신 이터레이션을 비즈니스용 Skype 서버에서 지 원하는 Office Online Server 라고 합니다. 자세한 내용은 [Office Online 서버 설명서](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx)를 참조 하세요. 
  
비즈니스용 Skype Server는 Office Web Apps 서버/Office Online Server를 구성 하는 다음과 같은 방법을 제공 합니다. 필요 사항에 따라 다음을 수행할 수 있습니다.
  
- **조직의 방화벽 및 같은 네트워크 영역에 비즈니스용 Skype 서버와 office Online Server를 모두 설치 합니다.** 이 토폴로지에서는 리버스 프록시 서버를 통해 Office Web Apps 서버/Office Online 서버에 대 한 외부 액세스가 제공 됩니다. 가장 좋은 방법은 비즈니스용 Skype 서버와 동일한 네트워크 영역에 Office Web Apps Server/Office Online Server를 설치 하는 것입니다.
    
    외부 비즈니스용 Skype 클라이언트는 인터넷에서 요청을 받아서 내부 네트워크에 전달 하는 서버 인 리버스 프록시 서버를 사용 하 여 비즈니스용 Skype 서버와 office Online Server에 연결할 수 있습니다. (내부 클라이언트는 Office Web Apps Server/Office Online Server에 직접 연결할 수 있으므로 리버스 프록시 서버를 사용할 필요가 없습니다.) 이 토폴로지는 비즈니스용 Skype Server 에서만 사용 하는 전용 Office Web Apps Server/Office Online Server 팜을 사용 하려는 경우에 가장 적합 합니다.
    
- **외부에서 배포 된 Office Web Apps Server/Office Online Server를 사용 합니다.** 이 토폴로지에서는 비즈니스용 Skype 서버를 온-프레미스에 배포 하 고 비즈니스용 Skype Server 네트워크 영역 외부에 배포 된 Office Web Apps Server/Office Online Server를 사용 합니다. 이 문제는 Office Web Apps Server/Office Online Server가 회사의 여러 응용 프로그램에서 공유 되 고 비즈니스용 Skype Server가 Office Web Apps Server/Office Online Server의 외부 인터페이스를 사용 해야 하는 네트워크에 배포 되는 경우와 그 반대의 경우도 가능 합니다.
    
    역방향 프록시 서버를 설치할 필요는 없습니다. 대신 Office Web Apps 서버/Office Online Server에서 비즈니스용 Skype 서버에 대 한 모든 요청이 Edge 서버를 통해 라우팅됩니다. 내부와 외부 비즈니스용 Skype 클라이언트 모두 외부 URL을 사용 하 여 Office Web Apps 서버/Office Online 서버에 연결 합니다.
    
    Office Web Apps 서버/Office Online Server가 내부 방화벽 외부에 배포 된 경우 **Office Web Apps 서버가** 토폴로지 작성기에서 외부 네트워크 (즉, 외곽/인터넷)에 배포 됨 옵션을 선택 합니다.
    
자세한 내용은 비즈니스용 [Skype 서버에서 Office Web Apps 서버 통합 구성을](../../deploy/deploy-conferencing/office-web-app-server.md)참조 하세요. 
  
선택 하는 토폴로지에 관계 없이 올바른 방화벽 포트를 열어야 하는 것이 중요 합니다. Office Web Apps Server/Office Online Server, 부하 분산 장치 또는 비즈니스용 Skype 서버의 방화벽에서 DNS 이름, IP 주소 및 포트가 차단 되지 않는지 확인 해야 합니다.
  
> [!NOTE]
> Office Web Apps Server/Office Online Server에 대 한 외부 액세스를 제공 하는 또 다른 옵션은 주변 네트워크에 서버를 배포 하는 것입니다. 이렇게 하는 경우 Office Web Apps 서버/Office Online Server 설치 프로그램에서 서버 컴퓨터를 Active Directory 도메인의 구성원으로 만들어야 한다는 점에 유의 하세요. 네트워크 정책에서 주변 네트워크의 컴퓨터를 Active Directory 도메인 구성원으로 사용할 수 있는 경우가 아니면 주변 네트워크에 Office Web Apps Server/Office Online Server를 설치 하지 않는 것이 좋습니다. 대신 내부 네트워크에 Office Web Apps Server/Office Online Server를 설치 하 고 리버스 프록시 서버를 통해 외부 사용자 액세스를 제공 해야 합니다. 
  
## <a name="topology-requirements-for-large-meetings"></a>대규모 모임에 대 한 토폴로지 요구 사항

단일 대규모 모임에는 하나 이상의 프런트 엔드 서버와 1 백 엔드 서버가 필요 합니다. 그러나 고가용성을 제공 하려면 다음 다이어그램에 표시 된 것 처럼 미러 백 엔드 서버가 있는 2 개의 프런트 엔드 서버 풀을 사용 하는 것이 좋습니다.
  
**대규모 모임 토폴로지**

![대규모 모임 토폴로지](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
대규모 모임을 호스트 하는 사용자는 프런트 엔드 풀에 사용자 계정이 있어야 합니다. 그러나이 풀에는 다른 사용자 계정을 호스트 하지 않는 것이 좋습니다. 그 대신 대규모 모임에만 사용 합니다. 이 풀에는 대규모 모임을 호스트 하는 데만 사용 될 특수 사용자 계정을 만드는 것이 가장 좋습니다. 대규모 모임 설정은 성능에 최적화 되어 있으므로 일반 사용자로 사용 하면 PSTN 끝점을 사용할 때 P2P 세션을 모임으로 승격할 수 없는 등의 문제가 발생할 수도 있습니다.
  
정확히 두 개의 프런트 엔드 서버를 사용 하 여 풀을 관리 하려면 몇 가지 특별 고려 사항이 필요 합니다. 자세한 내용은 비즈니스용 Skype 서버 2015 및 비즈니스용 [Skype server 2015의 참조 토폴로지에](../../plan-your-deployment/topology-basics/reference-topologies.md) [대 한 토폴로지 기본 사항을](../../plan-your-deployment/topology-basics/topology-basics.md) 참조 하세요.
  
또한 대규모 모임에 사용 되는 풀에 대해 필요에 따라 재해 복구 백업 및 장애 조치를 제공 하려는 경우에는 다른 데이터 센터에 비슷한 설정 전용 풀을 사용 하 여 연결할 수 있습니다. 자세한 내용은 [비즈니스용 Skype 서버에서 고가용성 및 재해 복구 계획](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)을 참조 하세요.
  
토폴로지에 대 한 추가 정보는 다음과 같습니다.
  
- 파일 공유는 모임 콘텐츠를 저장 하는 데 필요 하며 보관 서버를 배포 하 여 사용 하는 경우 보관 파일을 저장 하기 위한 것입니다. 파일 공유는 풀 전용 이거나 풀이 배포 된 사이트의 다른 풀에서 사용 하는 것과 동일한 파일 공유 일 수 있습니다. 파일 공유를 구성 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버 2015에서 파일 공유 만들기](../../deploy/install/create-a-file-share.md)를 참조 하세요.
    
- 대규모 모임에서 PowerPoint 프레젠테이션 기능을 사용 하도록 설정 하려면 Office Web Apps 서버/Office Online Server가 필요 합니다. Office Web Apps 서버/Office Online 서버는 대규모 모임 풀 전용 이거나, 전용 풀이 배포 된 사이트의 다른 풀에서 사용 하는 동일한 Office Web Apps 서버/Office Online 서버 일 수 있습니다. 자세한 내용은 비즈니스용 [Skype 서버에서 Office Web Apps 서버 통합 구성을](../../deploy/deploy-conferencing/office-web-app-server.md)참조 하세요. 
    
- 프런트 엔드 서버의 부하 분산에는 HTTP 트래픽에 대 한 하드웨어 로드 밸런싱 (예: 모임 콘텐츠 다운로드)이 필요 합니다. DNS 부하 분산은 SIP 트래픽에 적합 합니다. 자세한 내용은 [비즈니스용 Skype에 대 한 부하 분산 요구 사항을](../../plan-your-deployment/network-requirements/load-balancing.md)참조 하세요. 
    
- 전용 대용량 모임 풀에 모니터링 서버를 사용 하려는 경우 비즈니스용 Skype Server 배포의 모든 프런트 엔드 서버 풀에서 공유 되는 모니터링 서버와 해당 데이터베이스를 사용 하는 것이 좋습니다. 자세한 내용은 [비즈니스용 Skype 서버의 모니터링 계획](../../plan-your-deployment/monitoring.md)을 참조 하세요.
    

