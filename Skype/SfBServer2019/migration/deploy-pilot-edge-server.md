---
title: 파일럿 Edge 서버 배포
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 이 항목에서는 비즈니스용 Skype 서버 2019에 지 서버를 배포 하기 전에 알아야 하는 구성 설정을 중점적으로 설명 합니다. 비즈니스용 Skype 서버 2019에 대 한 배포 및 구성 프로세스는 비즈니스용 Skype 서버 2015와 매우 비슷합니다. 또한 이 섹션에서는 파일럿 풀 배포 중에 고려해야 하는 핵심 사항들에 대해서도 설명합니다. 자세한 단계에 대 한 자세한 내용은 배포 설명서에서 외부 사용자 액세스 배포 (비즈니스용 Skype 서버 2019) 및 외부 사용자 액세스에 대 한 구성 정보 제공을 참조 하십시오.
ms.openlocfilehash: 00c371b917f2649dba9011fbbce6162b153822d1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752870"
---
# <a name="deploy-pilot-edge-server"></a>파일럿 Edge 서버 배포

이 항목에서는 비즈니스용 Skype 서버 2019에 지 서버를 배포 하기 전에 알아야 하는 구성 설정을 중점적으로 설명 합니다. 비즈니스용 Skype 서버 2019에 대 한 배포 및 구성 프로세스는 비즈니스용 Skype 서버 2015와 매우 비슷합니다. 또한 이 섹션에서는 파일럿 풀 배포 중에 고려해야 하는 핵심 사항들에 대해서도 설명합니다. <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
**새 에지 풀 정의** 마법사를 탐색할 때 다음 단계에 표시된 핵심 구성 설정을 검토합니다. **새 에지 풀 정의** 마법사의 일부 페이지만 표시됩니다. 
  
### <a name="to-define-an-edge-pool"></a>에 지 풀을 정의 하려면

1. 토폴로지 작성기가 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 설치되어 있는 컴퓨터에 로그온합니다.
    
2. 비즈니스용 Skype 서버 2019 노드로 이동 합니다. **에지 풀**을 마우스 오른쪽 단추로 클릭하고 **새 에지 풀**을 클릭합니다.
    
     ![새에 지 풀 정의 대화 상자](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. 에지 풀은 **다중 컴퓨터 풀** 또는 **단일 컴퓨터 풀**일 수 있습니다.
    
     ![에 지 풀 FQDN 정의 대화 상자](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. **기능 선택** 페이지에서 페더레이션을 사용하도록 설정하지 마십시오. 페더레이션 및 XMPP 페더레이션은 현재 레거시에 지 서버를 통해 라우팅됩니다. 이러한 기능은 마이그레이션의 이후 단계에서 구성됩니다. 

  
5. **외부 fqdn**, **내부 ip 주소 정의**및 **외부 IP 주소 정의**마법사 페이지를 계속 해 서 완료 합니다.
    
6. **다음 홉 서버 정의** 페이지에서 레거시에 지 풀의 다음 홉에 대 한 디렉터를 선택 합니다. 
    
     ![다음 홉 정의 대화 상자](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. **프런트 엔드 또는 중재 풀 연결** 페이지에서 지금은이에 지 풀과 풀을 연결 하지 않습니다. 외부 미디어 트래픽은 현재 레거시에 지 서버를 통해 라우팅됩니다. 이 설정은 마이그레이션의 이후 단계에서 구성됩니다. 
    
     ![프런트 엔드 풀 연결 대화 상자](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. **마침을**클릭 한 후 토폴로지를 **게시** 합니다. 
    
9. 배포 설명서의 단계에 따라 새에 지 서버에 파일을 설치 하 고, 인증서를 구성 하 고, 서비스를 시작 합니다. 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
배포 설명서의 항목에 나와 있는 지침을 따르는 것이 매우 중요 합니다. 이 섹션에는 단순히 이러한 서버 역할을 설치할 때의 구성 설정에 대한 일부 지침만 제공됩니다. 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
이제 비즈니스용 Skype 서버 2019에 지 서버 배포와 동시에 레거시에 지 서버를 배포 해야 합니다. 두 배포가 올바르게 실행되고 있는지, 서비스가 시작되었는지, 다음 단계로 이동하기 전에 각 배포를 관리할 수 있는지를 확인합니다. 
  

