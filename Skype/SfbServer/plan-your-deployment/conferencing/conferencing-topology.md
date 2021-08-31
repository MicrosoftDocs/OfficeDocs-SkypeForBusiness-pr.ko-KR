---
title: 회의 토폴로 비즈니스용 Skype 서버지 계획
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7392dfa7-791a-4723-88ff-0ef8a9ef11c8
description: '요약: 이 항목을 통해 2013에서 회의 토폴로지 계획에 대해 비즈니스용 Skype 서버.'
ms.openlocfilehash: 09d793a75ab72ef96d3ded85156c99a7590e087d
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58732637"
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server"></a>회의 토폴로 비즈니스용 Skype 서버지 계획
 
**요약:** 이 항목을 통해 2013에서 회의 토폴로지 계획에 대해 비즈니스용 Skype 서버.
  
이 항목에서는 회의를 위한 토폴로지 기본 비즈니스용 Skype 서버.
  
- 지원되는 토폴로지
    
- 전화 접속 회의 고려 사항
    
- 웹 회의 고려 사항
    
- 대규모 모임에 대한 요구 사항
    
하드웨어 및 소프트웨어 요구 사항에 대한 자세한 내용은 에서 회의를 위한 하드웨어 및 소프트웨어 요구 [사항을 비즈니스용 Skype 서버.](hardware-and-software-requirements.md)
  
## <a name="supported-topologies"></a>지원되는 토폴로지

비즈니스용 Skype 서버 회의 서비스를 실행하는 서버는 항상 프런트 엔드 서버 또는 Standard Edition 함께 설치됩니다. 사용자 비즈니스용 Skype 서버 IM 회의 기능이 자동으로 배포됩니다. 토폴로지 작성기를 사용하여 웹, A/V(오디오 및 비디오) 및 전화 접속 회의를 배포할지 여부를 지정할 수 있습니다. 토폴로지 작성기에서 기존 배포에 회의를 추가할 수도 있습니다. 토폴로지 기본 사항 및 함께 사용 시나리오에 대한 자세한 내용은 [Topology Basics for 비즈니스용 Skype 서버.](../../plan-your-deployment/topology-basics/topology-basics.md)
  
다음 토폴로지 및 구성에서 회의를 배포할 수 있습니다.
  
- 비즈니스용 Skype 서버 Standard Edition
    
- 비즈니스용 Skype 서버 Enterprise Edition
    
- 사용 또는 Enterprise Voice
    
## <a name="dial-in-conferencing-considerations"></a>전화 접속 회의 고려 사항

전화 접속 회의를 배포하는 경우 다음을 고려해야 합니다.
  
- 전화 접속 회의를 사용하려면 중재 서버가 비즈니스용 Skype 서버 게이트웨이와 PSTN 게이트웨이 간에 신호(및 일부 구성의 미디어)를 변환하고 중재 서버와 PSTN 게이트웨이 간에 신호 및 미디어를 변환하는 PSTN 게이트웨이가 필요합니다.
    
   전화 접속 회의를 구성하려면 먼저 Enterprise Voice 중재 서버와 다음 중 하나 이상을 배포해야 합니다.
    
  - PSTN 게이트웨이
    
  - IP-PBX
    
  - SBC(Session Border Controller)(SIP 트렁크를 구성하여 연결하는 인터넷 전화 통신 서비스 공급자용)
    
- 분기 사이트에는 응용 프로그램 서비스, 회의 도우미 애플리케이션 회의 알림 애플리케이션 배포할 수 없습니다.
    
- 전화 접속 회의를 배포하는 모든 풀에 전화 접속 회의를 비즈니스용 Skype 서버 합니다. 모든 풀에 액세스 번호를 할당할 필요는 없지만 모든 풀에 전화 접속 회의 기능을 배포해야 합니다. 이 요구 사항은 사용자가 한 풀의 액세스 번호로 전화를 걸고 다른 풀에서 비즈니스용 Skype 서버 회의에 참가할 때 기록된 이름 기능을 지원하는 요구 사항입니다. 
    
자세한 내용은 [Plan for dial-in conferencing in 비즈니스용 Skype 서버.](dial-in-conferencing.md)
  
## <a name="web-conferencing-considerations"></a>웹 회의 고려 사항

웹 회의에는 다음이 필요합니다. 
  
- 웹 회의 콘텐츠를 저장하는 데 사용되는 파일 저장소 액세스
    
- 전화 회의 Office 파일을 공유하는 데 필요한 Office Online Server Web Apps Server/PowerPoint 통합
    
> [!NOTE]
> 웹앱 서버의 최신 Office 웹앱 서버의 Office Online Server 이름이 비즈니스용 Skype 서버. 자세한 내용은 Office Online Server [참조하십시오.](/officeonlineserver/office-online-server) 
  
비즈니스용 Skype 서버 Web Apps 서버/웹앱 서버를 구성하는 Office 방법을 Office Online Server. 요구에 따라 다음을 할 수 있습니다.
  
- **조직의 방화벽 비즈니스용 Skype 서버 Office 웹앱 서버/Office Online Server 웹앱 서버/웹앱 서버를 모두 설치하고 동일한 네트워크 영역 내에 설치합니다.** 이 토폴로지에서는 역방향 프록시 서버를 통해 Office Web Apps 서버/Office Online Server 외부 액세스가 제공됩니다. 웹앱 서버/웹 Office 동일한 네트워크 Office Online Server 설치하는 것이 비즈니스용 Skype 서버.
    
    외부 비즈니스용 Skype 클라이언트는 비즈니스용 Skype 서버 요청을 Office 내부 네트워크로 전달하는 서버인 역방향 프록시 서버를 사용하여 Office Online Server Web Apps Server/Office Online Server 서버에 연결할 수 있습니다. 내부 클라이언트는 웹앱 서버/웹앱 서버에 직접 연결할 수 있기 때문에 Office 서버를 사용할 Office Online Server 없습니다. 이 토폴로지는 웹앱 서버에서만 사용되는 전용 Office Web Apps 서버/Office Online Server 팜을 사용하려는 비즈니스용 Skype 서버.
    
- **Web Apps Server/Office 외부에 배포된 Office Online Server.** 이 토폴로지에서는 비즈니스용 Skype 서버 배포되어 Office 네트워크 영역 외부에 배포된 Office Online Server Web Apps Server/비즈니스용 Skype 서버 사용하게 됩니다. 이 경우 Office Web Apps Server/Office Online Server 회사에 있는 여러 응용 프로그램에서 공유하고 비즈니스용 Skype 서버 Web Apps Server/Office 외부 인터페이스를 사용하기 위해 네트워크에서 배포할 Office Online Server 있습니다.
    
    역방향 프록시 서버를 설치할 필요는 없습니다. 대신 Office Web Apps Server/Office Online Server 비즈니스용 Skype 서버 모든 요청이 에지 서버를 통해 라우팅됩니다. 내부 및 외부 비즈니스용 Skype 클라이언트는 모두 외부 URL을 Office Web Apps Server/Office Online Server 연결합니다.
    
    Office Web Apps Server/Office Online Server 내부 방화벽 외부에 배포된 경우 토폴로지 작성기에서 Office **Web Apps Server가** 외부 네트워크(경계/인터넷)에 배포되어 있는 경우 옵션을 선택합니다.
    
자세한 내용은 [Configure integration with Office Web Apps Server in 비즈니스용 Skype 서버.](../../deploy/deploy-conferencing/office-web-app-server.md) 
  
선택한 토폴로지와 관계없이 올바른 방화벽 포트를 열는 것이 중요합니다. DNS 이름, IP 주소 및 포트가 Office Web Apps Server/Office 부하 Office Online Server 또는 포트에 의해 차단되지 않는지 비즈니스용 Skype 서버.
  
> [!NOTE]
> Web Apps Server/Office 외부 액세스를 제공하기 위한 Office Online Server 옵션은 경계 네트워크에 서버를 배포하는 것입니다. 이렇게 하려면 Office Web Apps Server/Office Online Server 설치하려면 서버 컴퓨터가 Active Directory 도메인의 구성원이 되어야 합니다. 네트워크 정책으로 경계 네트워크의 컴퓨터가 Active Directory 도메인 구성원이 될 수 있도록 허용하지 않는 한 경계 네트워크에 Office Web Apps Server/Office Online Server 설치하지 않는 것이 좋습니다. 대신 내부 네트워크에 Office Web Apps Server/Office Online Server 설치하고 역방향 프록시 서버를 통해 외부 사용자 액세스를 제공해야 합니다. 
  
## <a name="topology-requirements-for-large-meetings"></a>대규모 모임에 대한 토폴로지 요구 사항

대규모 모임을 하나만 수행하려면 프런트 엔드 서버와 백 엔드 서버가 하나씩 필요합니다. 그러나 고가용성을 제공하기 위해 다음 다이어그램과 같이 미러된 백 엔드 서버가 있는 두 프런트 엔드 서버 풀을 사용하는 것이 좋습니다.
  
**대규모 모임 토폴로지**

![대규모 모임 토폴로지](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
대규모 모임을 호스팅하는 사용자에게는 해당 사용자 계정이 프런트 엔드 풀에 있어야 합니다. 하지만 이 풀에서 다른 사용자 계정은 호스팅하지 않는 것이 좋습니다. 대신 대규모 모임에 대해서만 사용하십시오. 최선의 방법은 대규모 모임을 호스팅하는 데에만 사용되도록 이 풀에 특별한 사용자 계정을 만드는 것입니다. 대규모 모임 설정은 성능에 최적화되어 있어서 일반 사용자로 사용하면 PSTN 끝점이 관련되어 있을 때 P2P 세션을 모임으로 승격할 수 없는 등의 문제가 발생할 수 있습니다.
  
정확히 두 개의 프런트 엔드 서버를 포함하는 풀을 관리하기 위해서는 특별한 고려 사항이 필요합니다. 자세한 내용은 [Topology Basics for 비즈니스용 Skype 서버](../../plan-your-deployment/topology-basics/topology-basics.md) and [Reference topologies for 비즈니스용 Skype 서버 2015을 참조하십시오.](../../plan-your-deployment/topology-basics/reference-topologies.md)
  
또한 대규모 모임에 사용되는 풀에 대해 선택적으로 재해 복구 백업 및 장애 조치(failover)를 제공하려는 경우 다른 데이터 센터에서 유사한 설정 전용 풀과 쌍을 이루어도 됩니다. 자세한 내용은 [Plan for high availability and disaster recovery in 비즈니스용 Skype 서버.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
토폴로지에 대한 추가 정보에는 다음이 포함됩니다.
  
- 모임 콘텐츠를 저장하고 보관 서버를 배포하고 사용하도록 설정한 경우 보관 파일을 저장하려면 파일 공유가 필요합니다. 파일 공유는 풀 전용이거나 풀이 배포된 사이트에서 다른 풀에 사용되는 것과 동일한 파일 공유일 수 있습니다. 파일 공유를 구성하는 데 대한 자세한 내용은 [Create a file share in 비즈니스용 Skype 서버 2015를 참조합니다.](../../deploy/install/create-a-file-share.md)
    
- 대규모 Office 프레젠테이션 기능을 사용하도록 Office Online Server Web Apps Server/PowerPoint 웹앱 서버/웹앱 서버가 필요합니다. Office Web Apps 서버/Office Online Server 전용으로 사용할 수도 있으며, 전용 풀이 배포된 사이트의 다른 풀에서 Office Web Apps Server/Office Online Server 같은 웹앱 서버/웹앱 서버를 사용할 수도 있습니다. 자세한 내용은 [Configure integration with Office Web Apps Server in 비즈니스용 Skype 서버.](../../deploy/deploy-conferencing/office-web-app-server.md) 
    
- 프런트 엔드 서버의 부하 분산을 위해서는 HTTP 트래픽(예: 모임 콘텐츠 다운로드)에 대한 하드웨어 부하 분산이 필요합니다. SIP 트래픽에는 DNS 부하 분산이 권장됩니다. 자세한 내용은 [에 대한 부하 분산](../../plan-your-deployment/network-requirements/load-balancing.md)요구 비즈니스용 Skype. 
    
- 전용 대규모 모임 풀에 모니터링 서버를 사용하려는 경우 모니터링 서버 및 해당 데이터베이스를 사용하여 배포의 모든 프런트 엔드 서버 풀에서 공유하는 비즈니스용 Skype 서버 좋습니다. 자세한 내용은 [Plan for monitoring in 비즈니스용 Skype 서버.](../../plan-your-deployment/monitoring.md)
