---
title: 비즈니스용 Skype 서버에 대한 회의 토폴로지 계획
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7392dfa7-791a-4723-88ff-0ef8a9ef11c8
description: '요약: 이 항목을 읽고 비즈니스용 Skype 서버에서 회의 토폴로지 계획에 대해 자세히 알아보습니다.'
ms.openlocfilehash: dc7c62d45a2ebd84f38cc67ce996ba0ac72aa794
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814098"
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server"></a>비즈니스용 Skype 서버에 대한 회의 토폴로지 계획
 
**요약:** 이 항목을 읽고 비즈니스용 Skype 서버에서 회의 토폴로지 계획에 대해 자세히 알아보습니다.
  
이 항목에서는 비즈니스용 Skype 서버의 회의에 대한 토폴로지 기본 사항에 대해 설명합니다.
  
- 지원되는 토폴로지
    
- 전화 접속 회의 고려 사항
    
- 웹 회의 고려 사항
    
- 대규모 모임에 대한 요구 사항
    
하드웨어 및 소프트웨어 요구 사항에 대한 자세한 내용은 비즈니스용 Skype 서버의 회의에 대한 하드웨어 및 소프트웨어 요구 [사항을 참조하세요.](hardware-and-software-requirements.md)
  
## <a name="supported-topologies"></a>지원되는 토폴로지

비즈니스용 Skype 서버에서 회의 서비스를 실행하는 서버는 항상 프런트 엔드 서버 또는 Standard Edition 서버와 함께 함께 설치됩니다. 비즈니스용 Skype 서버를 배포하면 IM 회의 기능이 자동으로 배포됩니다. 토폴로지 작성기를 사용하여 웹, A/V(오디오 및 비디오) 및 전화 접속 회의를 배포할지 여부를 지정할 수 있습니다. 토폴로지 작성기에서 기존 배포에 회의를 추가할 수도 있습니다. 토폴로지 기본 사항 및 함께 사용 시나리오에 대한 자세한 내용은 비즈니스용 Skype 서버용 토폴로지 [기본 사항을 참조하세요.](../../plan-your-deployment/topology-basics/topology-basics.md)
  
다음 토폴로지 및 구성에서 회의를 배포할 수 있습니다.
  
- 비즈니스용 Skype 서버 Standard Edition
    
- 비즈니스용 Skype 서버 Enterprise Edition
    
- 비어 있는 경우 또는 Enterprise Voice
    
## <a name="dial-in-conferencing-considerations"></a>전화 접속 회의 고려 사항

전화 접속 회의를 배포하는 경우 다음을 고려해야 합니다.
  
- 전화 접속 회의를 사용하려면 중재 서버가 비즈니스용 Skype 서버와 PSTN 게이트웨이 간에 신호(및 일부 구성의 미디어)를 변환하고 중재 서버와 PSTN 게이트웨이 간에 신호 및 미디어를 변환하기 위한 PSTN 게이트웨이가 필요합니다.
    
   전화 접속 회의를 구성하려면 먼저 Enterprise Voice 중재 서버와 다음 중 하나 이상을 배포해야 합니다.
    
  - PSTN 게이트웨이
    
  - IP-PBX
    
  - SBC(Session Border Controller)(SIP 트렁크를 구성하여 연결하는 인터넷 전화 통신 서비스 공급자용)
    
- 응용 프로그램 서비스, 회의 참석자 응용 프로그램 및 회의 공지 응용 프로그램을 분기 사이트에 배포할 수 있지만 분기 사이트에는 배포할 수 없습니다.
    
- 비즈니스용 Skype 서버 회의를 배포하는 모든 풀에 전화 접속 회의를 배포해야 합니다. 모든 풀에 액세스 번호를 할당할 필요는 없지만 모든 풀에 전화 접속 회의 기능을 배포해야 합니다. 이 요구 사항은 사용자가 한 풀의 액세스 번호로 전화를 걸고 다른 풀의 비즈니스용 Skype 서버 회의에 참가할 때 기록된 이름 기능을 지원합니다. 
    
자세한 내용은 비즈니스용 Skype 서버의 전화 접속 회의 [계획을 참조하세요.](dial-in-conferencing.md)
  
## <a name="web-conferencing-considerations"></a>웹 회의 고려 사항

웹 회의에는 다음이 필요합니다. 
  
- 웹 회의 콘텐츠를 저장하는 데 사용되는 파일 저장소 액세스
    
- 회의 중에 PowerPoint 파일을 공유하는 데 필요한 Office Web Apps Server/Office Online Server와의 통합
    
> [!NOTE]
> Office Web Apps 서버의 최신 이니션은 비즈니스용 Skype 서버에서 지원되는 Office Online Server입니다. 자세한 내용은 [Office Online Server 설명서를 참조하십시오.](https://technet.microsoft.com/library/jj219456%28v=office.16%29.aspx) 
  
비즈니스용 Skype 서버는 Office Web Apps 서버/Office Online Server를 구성하는 다음과 같은 방법을 제공합니다. 요구에 따라 다음을 할 수 있습니다.
  
- **조직의 방화벽 뒤에 비즈니스용 Skype 서버와 Office Web Apps 서버/Office Online Server를 모두 설치하고 동일한 네트워크 영역 내에 설치합니다.** 이 토폴로지에서는 역방향 프록시 서버를 통해 Office Web Apps 서버/Office Online Server에 대한 외부 액세스가 제공됩니다. 비즈니스용 Skype 서버와 동일한 네트워크 영역으로 Office Web Apps 서버/Office Online Server를 설치하는 것이 좋습니다.
    
    외부 비즈니스용 Skype 클라이언트는 인터넷에서 요청을 들어 내부 네트워크로 전달하는 서버인 역방향 프록시 서버를 사용하여 비즈니스용 Skype 서버 및 Office Web Apps Server/Office Online Server에 연결할 수 있습니다. 내부 클라이언트는 Office Web Apps 서버/Office Online Server에 직접 연결할 수 있기 때문에 역방향 프록시 서버를 사용할 필요가 없습니다. 이 토폴로지는 비즈니스용 Skype 서버에서만 사용되는 전용 Office Web Apps 서버/Office Online Server 팜을 사용하려는 경우 가장 잘 작동합니다.
    
- **외부에서 배포된 Office Web Apps 서버/Office Online Server를 사용하세요.** 이 토폴로지에서 비즈니스용 Skype 서버는온-프레미스로 배포되어 비즈니스용 Skype 서버 네트워크 영역 외부에 배포된 Office Web Apps 서버/Office Online Server를 사용하게 됩니다. 이는 Office Web Apps 서버/Office Online Server가 기업의 여러 응용 프로그램에서 공유되는 경우 비즈니스용 Skype 서버가 Office Web Apps 서버/Office Online Server의 외부 인터페이스를 사용하고 그 반대의 경우도 마찬가지인 네트워크에서 배포될 때 이러한 문제가 발생될 수 있습니다.
    
    역방향 프록시 서버를 설치할 필요는 없습니다. 대신 Office Web Apps 서버/Office Online Server에서 비즈니스용 Skype 서버로의 모든 요청이 에지 서버를 통해 라우팅됩니다. 내부 및 외부 비즈니스용 Skype 클라이언트 모두 외부 URL을 사용하여 Office Web Apps Server/Office Online Server에 연결합니다.
    
    Office Web Apps 서버/Office Online Server가 내부 방화벽 외부에 배포된 경우 토폴로지 작성기에서 외부 네트워크(경계/인터넷)에 **Office Web Apps 서버가** 배포되는 옵션을 선택합니다.
    
자세한 내용은 비즈니스용 Skype 서버에서 Office Web Apps 서버와의 통합 [구성을 참조하세요.](../../deploy/deploy-conferencing/office-web-app-server.md) 
  
선택한 토폴로지와 관계없이 올바른 방화벽 포트를 열는 것이 중요합니다. DNS 이름, IP 주소 및 포트가 Office Web Apps Server/Office Online Server, 부하 런타임 또는 비즈니스용 Skype 서버의 방화벽에 의해 차단되지 않는지 확인해야 합니다.
  
> [!NOTE]
> Office Web Apps 서버/Office Online Server에 대한 외부 액세스를 제공하기 위한 또 다른 옵션은 경계 네트워크에 서버를 배포하는 것입니다. 이 작업을 수행하려면 Office Web Apps 서버/Office Online Server 설치를 위해서는 서버 컴퓨터가 Active Directory 도메인의 구성원이 상태임에 유의해야 합니다. 네트워크 정책으로 인해 경계 네트워크의 컴퓨터가 Active Directory 도메인 구성원이 될 수 있도록 허용하지 않는 한 경계 네트워크에 Office Web Apps Server/Office Online Server를 설치하지 않는 것이 좋습니다. 대신 내부 네트워크에 Office Web Apps 서버/Office Online Server를 설치하고 역방향 프록시 서버를 통해 외부 사용자 액세스를 제공해야 합니다. 
  
## <a name="topology-requirements-for-large-meetings"></a>대규모 모임에 대한 토폴로지 요구 사항

대규모 모임을 하나만 수행하려면 프런트 엔드 서버와 백 엔드 서버가 하나씩 필요합니다. 그러나 고가용성을 제공하기 위해 다음 다이어그램과 같이 미러된 백 엔드 서버가 있는 2개의 프런트 엔드 서버 풀을 사용하는 것이 좋습니다.
  
**대규모 모임 토폴로지**

![대규모 모임 토폴로지](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
대규모 모임을 호스팅하는 사용자에게는 해당 사용자 계정이 프런트 엔드 풀에 있어야 합니다. 하지만 이 풀에서 다른 사용자 계정은 호스팅하지 않는 것이 좋습니다. 대신 대규모 모임에 대해서만 사용하십시오. 최선의 방법은 대규모 모임을 호스팅하는 데에만 사용되도록 이 풀에 특별한 사용자 계정을 만드는 것입니다. 대규모 모임 설정은 성능에 최적화되어 있어서 일반 사용자로 사용하면 PSTN 끝점이 관련되어 있을 때 P2P 세션을 모임으로 승격할 수 없는 등의 문제가 발생할 수 있습니다.
  
정확히 두 개의 프런트 엔드 서버를 포함하는 풀을 관리하기 위해서는 특별한 고려 사항이 필요합니다. 자세한 내용은 비즈니스용 Skype 서버 [2015의](../../plan-your-deployment/topology-basics/topology-basics.md) 토폴로지 기본 정보와 비즈니스용 [Skype 서버 2015에](../../plan-your-deployment/topology-basics/reference-topologies.md)대한 참조 토폴로지 를 참조하세요.
  
또한 대규모 모임에 사용되는 풀에 대해 선택적으로 재해 복구 백업 및 장애 조치(failover)를 제공하려는 경우 다른 데이터 센터에서 유사하게 설정된 전용 풀과 쌍으로 설정할 수 있습니다. 자세한 내용은 비즈니스용 Skype 서버에서 고가용성 및 재해 복구 [계획을 참조하세요.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
토폴로지에 대한 추가 정보에는 다음이 포함됩니다.
  
- 모임 콘텐츠를 저장하고 보관 서버를 배포하고 사용하도록 설정한 경우 보관 파일을 저장하려면 파일 공유가 필요합니다. 파일 공유는 풀 전용이거나 풀이 배포된 사이트에서 다른 풀에 사용되는 것과 동일한 파일 공유일 수 있습니다. 파일 공유 구성에 대한 자세한 내용은 [비즈니스용 Skype 서버 2015에서](../../deploy/install/create-a-file-share.md)파일 공유 만들기를 참조하세요.
    
- 대규모 모임에서 PowerPoint 프레젠테이션 기능을 사용하도록 설정하려면 Office Web Apps 서버/Office Online Server가 필요합니다. Office Web Apps 서버/Office Online Server는 대규모 모임 풀 전용으로 사용할 수도 있으며, 전용 풀이 배포된 사이트의 다른 풀에서 사용하는 Office Web Apps 서버/Office Online Server와 동일할 수도 있습니다. 자세한 내용은 비즈니스용 Skype 서버에서 Office Web Apps 서버와의 통합 [구성을 참조하세요.](../../deploy/deploy-conferencing/office-web-app-server.md) 
    
- 프런트 엔드 서버의 부하 분산에는 HTTP 트래픽(예: 모임 콘텐츠 다운로드)에 대한 하드웨어 부하 분산이 필요합니다. SIP 트래픽에는 DNS 부하 분산이 권장됩니다. 자세한 내용은 [비즈니스용 Skype에 대한 부하 분산 요구 사항을 참조하세요.](../../plan-your-deployment/network-requirements/load-balancing.md) 
    
- 전용 대규모 모임 풀에 모니터링 서버를 사용하려면 비즈니스용 Skype 서버 배포의 모든 프런트 엔드 서버 풀에서 공유되는 모니터링 서버 및 해당 데이터베이스를 사용하는 것이 좋습니다. 자세한 내용은 비즈니스용 [Skype 서버의 모니터링 계획을 참조하세요.](../../plan-your-deployment/monitoring.md)
    

