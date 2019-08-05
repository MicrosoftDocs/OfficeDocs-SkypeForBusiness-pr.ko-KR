---
title: 파일럿에 지 서버 배포
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 이 항목에서는 비즈니스용 Skype Server 2019 Edge 서버를 배포 하기 전에 알아야 하는 구성 설정을 강조 합니다. 비즈니스용 Skype Server 2019의 배포 및 구성 프로세스는 비즈니스용 Skype 서버 2015와 매우 유사 합니다. 이 섹션에서는 파일럿 풀 배포의 일부로 고려해 야 하는 주요 요점만 중점적으로 설명 합니다. 자세한 단계는 배포 프로세스를 설명 하는 배포 설명서의 비즈니스용 Skype 서버 2019 외부 사용자 액세스 배포를 참조 하 고 외부 사용자 액세스에 대 한 구성 정보도 제공 합니다.
ms.openlocfilehash: f692eb5ad4a24b47a8bab7a56be218eab04af7dd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189096"
---
# <a name="deploy-pilot-edge-server"></a>파일럿에 지 서버 배포

이 항목에서는 비즈니스용 Skype Server 2019 Edge 서버를 배포 하기 전에 알아야 하는 구성 설정을 강조 합니다. 비즈니스용 Skype Server 2019의 배포 및 구성 프로세스는 비즈니스용 Skype 서버 2015와 매우 유사 합니다. 이 섹션에서는 파일럿 풀 배포의 일부로 고려해 야 하는 주요 요점만 중점적으로 설명 합니다. <!-- For detailed steps, see 
 [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.  -->
  
**새 Edge 풀 정의** 마법사를 탐색할 때 다음 단계에 표시 된 키 구성 설정을 검토 합니다. **새 Edge 풀 정의** 마법사의 몇 페이지만 표시 됨에 유의 하세요. 
  
### <a name="to-define-an-edge-pool"></a>Edge 풀을 정의 하려면

1. 도메인 관리자 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 토폴로지 작성기가 설치 된 컴퓨터에 로그온 합니다.
    
2. 비즈니스용 Skype 서버 2019 노드를 탐색 합니다. **Edge 풀**을 마우스 오른쪽 단추로 클릭 하 고 **새 edge 풀**을 클릭 합니다.
    
     ![새 에지 풀 정의 대화 상자](../media/migration_ocs_topo_edgepool_page1.JPG)
  
3. Edge 풀은 **여러 컴퓨터 풀** 또는 **단일 컴퓨터 풀**일 수 있습니다.
    
     ![에지 풀 FQDN 정의 대화 상자](../media/migration_ocs_topo_edgepool_page2.JPG)
  
4. **기능 선택** 페이지에서 페더레이션 또는 xmpp 페더레이션을 사용 하지 않습니다. 페더레이션 및 XMPP federation가 현재 레거시 Edge 서버를 통해 라우팅된 경우 이러한 기능은 이후 마이그레이션 단계에서 구성 됩니다. 

  
5. **외부 fqdn**을 지정 하 고 **내부 ip 주소를 정의**하 고 **외부 ip 주소를 정의**하 여 다음 마법사 페이지를 계속 합니다.
    
6. **다음 홉 서버 정의** 페이지에서 레거시 Edge 풀의 다음 홉에 대 한 디렉터를 선택 합니다. 
    
     ![다음 홉 정의 대화 상자](../media/migration_ocs_topo_edgepool_page7.JPG)
  
7. **프런트 엔드 또는 중재 풀 연결** 페이지에서 지금은이 Edge 풀과 풀을 연결 하지 않습니다. 외부 미디어 트래픽은 현재 레거시에 지 서버를 통해 라우트됩니다. 이 설정은 이후 마이그레이션 단계에서 구성 됩니다. 
    
     ![프런트 엔드 풀 연결 대화 상자](../media/migration_ocs_topo_edgepool_page8.JPG)
  
8. **마침을**클릭 한 다음 토폴로지를 **게시** 합니다. 
    
9. 배포 설명서의 단계에 따라 새 Edge 서버에 파일을 설치 하 고 인증서를 구성한 다음 서비스를 시작 합니다. 
<!-- [Install Edge Servers for Skype for Business Server 2019](../deployment/deploying-external-user-access/install-edge-servers.md) in -->
    
배포 설명서의 항목에 있는 지침을 준수 하는 것이 매우 중요 합니다. 이 섹션에서는 이러한 서버 역할을 설치할 때 구성 설정에 대 한 몇 가지 지침만 제공 합니다. 
<!-- [Deploying external user access in Skype for Business Server 2019](../deployment/deploying-external-user-access/deploying-external-user-access.md) -->
  
이제 비즈니스용 Skype Server 2019 Edge 서버 배포와 함께 레거시 Edge 서버를 배포 해야 합니다. 두 배포가 모두 제대로 실행 되 고 있는지 확인 하 고 서비스가 시작 되며 다음 단계로 이동 하기 전에 각 배포를 관리할 수 있습니다. 
  

