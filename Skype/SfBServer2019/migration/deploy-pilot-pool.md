---
title: 파일럿 풀 배포
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
description: 비즈니스용 Skype 서버 2019로 마이그레이션하는 데 필요한 첫 번째 단계 중 하나는 파일럿 풀을 배포하는 것입니다. 파일럿 풀에서는 레거시 배포와 비즈니스용 Skype 서버 2019의 동시 사용 테스트를 합니다. 동시 사용은 모든 사용자 및 풀을 비즈니스용 Skype 서버 2019로 이동할 때까지 지속되는 임시 상태입니다.
ms.openlocfilehash: a8d9a1bbe5f629a91721ebe530e6a192e3e65b62
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113294"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a>비즈니스용 Skype 서버 2019 파일럿 풀 배포

비즈니스용 Skype 서버 2019로 마이그레이션하는 데 필요한 첫 번째 단계 중 하나는 파일럿 풀을 배포하는 것입니다. 파일럿 풀에서는 레거시 배포와 비즈니스용 Skype 서버 2019의 동시 사용 테스트를 합니다. 동시 사용은 모든 사용자 및 풀을 비즈니스용 Skype 서버 2019로 이동할 때까지 지속되는 임시 상태입니다. 
  
파일럿 풀을 배포할 때는 새 프런트 엔드 풀 정의 마법사를 사용합니다. 레거시 풀에 있는 비즈니스용 Skype 서버 2019 파일럿 풀에 동일한 기능 및 작업을 배포해야 합니다. 레거시 환경을 보관 또는 모니터링하기 위해 보관 서버, 모니터링 서버 또는 System Center Operations Manager를 배포한 경우 마이그레이션 동안 보관 또는 모니터링을 계속하려는 경우 파일럿 환경에 이러한 기능도 배포해야 합니다. 레거시 환경을 보관하거나 모니터링하기 위해 배포한 버전은 비즈니스용 Skype 서버 2019 환경에서 데이터를 캡처하지 않습니다. 
  
> [!NOTE]
> 다음 절차에서는 전체 파일럿 풀 배포 프로세스에서 고려해야 하는 기능 및 설정에 대해 설명합니다. 이 섹션에서는 파일럿 풀 배포 중에 고려해야 하는 핵심 사항들에 대해서만 설명합니다. <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a>비즈니스용 Skype 서버 2019 파일럿 풀을 배포하는 경우

1. 토폴로지 작성기가 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 설치되어 있는 컴퓨터에 로그온합니다.
    
2. 비즈니스용 **Skype 서버 2019** Enterprise Edition 프런트 엔드 풀에 도달할 때까지  >  **트리를 확장합니다.**
    
3. Enterprise Edition 프런트 엔드 **풀을 마우스 오른쪽 단추로 클릭하고** 새 프런트 엔드 **풀 을 선택합니다.**
  
4. 풀 FQDN(FQDN)을 입력합니다. 파일럿 풀을 정의할 때 Enterprise Edition 프런트 엔드 풀 또는 Standard Edition 서버를 배포할 수 있습니다. 비즈니스용 Skype 서버 2019에서는 파일럿 풀 기능이 레거시 풀에 배포된 기능과 일치할 필요가 없습니다.
    
    > [!CAUTION]
    > 파일럿 풀에 대해 정의하는 풀 또는 서버 FQDN은 고유해야 합니다. 현재 배포된 레거시 풀 또는 현재 배포된 다른 서버의 이름과 일치할 수 없습니다. 
  
5. **기능 선택** 페이지에서 이 프런트 엔드 풀에 필요한 기능의 확인란을 선택합니다. 예를 들어 IM(인스턴트 메시징) 및 현재 상태 기능만 배포하는 경우 회의 확인란을 선택하여 다국어 IM을 허용하지만 음성, 비디오 및 공동 작업 회의 기능을 나타내기 때문에 전화 접속(PSTN) 회의, Enterprise Voice 또는 통화 허용 제어 확인란은 선택하지 않습니다. <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. 함께 **사용 가능한** 서버 역할 선택 페이지에서 중재 서버를 비즈니스용 Skype 서버 2019에 함께 두는 것이 좋습니다. 레거시 토폴로지와 비즈니스용 Skype 서버 2019를 함께 사용하는 경우 먼저 레거시 중재 서버를 함께 설치해야 합니다. 토폴로지의 통합 및 비즈니스용 Skype 서버 2019 중재 서버를 구성한 후 배포 프로세스 후반부에 중재 서버 역할을 비즈니스용 Skype 서버 2019로 이동할 때 배치된 중재 서버를 유지할지 아니면 독립 실행형 서버로 변경할지 결정할 수 있습니다. 
   
7. 이 **프런트** 엔드 풀과 서버 역할 연결 페이지에서 파일럿  풀 배포 중에 이 프런트 엔드 풀의 미디어 구성 요소에서 에지 풀을 사용할 수 있도록 설정 옵션을 **선택하지** 않습니다. 이 기능은 나중에 마이그레이션 중에 사용하고 온라인으로 설정합니다. 현재는 이 설정을 해제한 상태로 둡니다. 
  
8. **Office Web Apps 서버 선택** 페이지에서 **새로 만들기** 를 클릭한 다음 응용 프로그램 서버의 FQDN을 지정합니다.
  
9. 보관  SQL Server 저장소 정의 페이지에서 비즈니스용 Skype 서버 보관 및 모니터링 둘 다에 대해 SQL Server 저장소를 정의할 때 비즈니스용 Skype 서버 2019에 대해 SQL Server 인스턴스를 선택합니다. 
  
10. 토폴로지 게시하려면 비즈니스용 Skype 서버 노드를 마우스 오른쪽 **단추로** 클릭한 다음 토폴로지 **게시 를 클릭합니다.**
  
11. 게시 프로세스를 완료했으면 **마침** 을 클릭합니다.

12. "레거시 풀과 파일럿 풀 동시 사용 확인"이라는 다음 섹션으로 이동하기 전에 방금 게시된 토폴로지에서 정의한 비즈니스용 Skype 서버 새 프런트 엔드 파일럿 풀을 설치해야 합니다. 토폴로지의 서버에 [비즈니스용 Skype 서버](../../SfbServer/deploy/install/install-skype-for-business-server.md) 설치에 설명된 절차를 따르세요.

13. 이전 단계가 완료되면 다음 섹션으로 이동하여 파일럿 풀과 레거시 풀의 동시 사용 확인으로 이동하세요.
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
