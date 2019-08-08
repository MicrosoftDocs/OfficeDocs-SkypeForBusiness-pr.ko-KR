---
title: 파일럿 풀 배포
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 비즈니스용 Skype Server 2019 마이그레이션에 필요한 첫 번째 단계 중 하나는 파일럿 풀을 배포 하는 것입니다. 파일럿 풀은 레거시 배포의 비즈니스용 Skype 서버 2019 공존을 테스트 하는 위치입니다. 공존은 모든 사용자와 풀을 비즈니스용 Skype 서버 2019으로 이동할 때까지 지속 되는 임시 상태입니다.
ms.openlocfilehash: dc0e5b984aaa9ed931f3937b253fbe40aef9b051
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238858"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a>비즈니스용 Skype 서버 배포 2019 파일럿 풀

비즈니스용 Skype Server 2019 마이그레이션에 필요한 첫 번째 단계 중 하나는 파일럿 풀을 배포 하는 것입니다. 파일럿 풀은 레거시 배포의 비즈니스용 Skype 서버 2019 공존을 테스트 하는 위치입니다. 공존은 모든 사용자와 풀을 비즈니스용 Skype 서버 2019으로 이동할 때까지 지속 되는 임시 상태입니다. 
  
파일럿 풀을 배포 하는 경우 새 프런트 엔드 풀 정의 마법사를 사용 합니다. 레거시 풀에 있는 비즈니스용 Skype 서버 2019의 파일럿 풀에 동일한 기능 및 작업을 배포 해야 합니다. 보관 서버, 모니터링 서버 또는 System Center Operations Manager를 배포 하 여 레거시 환경을 보관 하거나 모니터링 하는 경우 마이그레이션 전체에서 보관 또는 모니터링을 계속 하려면 다음 기능을 함께 배포 해야 합니다. 파일럿 환경. 레거시 환경을 보관 하거나 모니터링 하기 위해 배포 된 버전은 비즈니스용 Skype Server 2019 환경에서 데이터를 캡처하지 않습니다. 
  
> [!NOTE]
> 다음 절차에서는 전체 파일럿 풀 배포 프로세스의 일부로 고려해 야 하는 기능과 설정에 대해 설명 합니다. 이 섹션에서는 파일럿 풀 배포의 일부로 고려해 야 하는 주요 요점만 중점적으로 설명 합니다. <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a>비즈니스용 Skype 서버 2019 파일럿 풀을 배포 하려면

1. 도메인 관리자 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 토폴로지 작성기가 설치 된 컴퓨터에 로그온 합니다.
    
2. 비즈니스용 **Skype 서버 2019** > **엔터프라이즈 에디션 프런트 엔드 풀**에 도달할 때까지 트리를 확장 합니다.
    
3. **Enterprise Edition 프런트 엔드 풀** 을 마우스 오른쪽 단추로 클릭 하 고 **새 프런트 엔드 풀**을 선택 합니다.
  
4. 풀 정규화 된 도메인 이름 (FQDN)을 입력 합니다. 파일럿 풀을 정의할 때 Enterprise Edition 프런트 엔드 풀 또는 Standard Edition 서버를 배포 하도록 선택할 수 있습니다. 비즈니스용 Skype 서버 2019에는 이전 풀에 배포 된 것과 일치 하는 파일럿 풀 기능이 필요 하지 않습니다.
    
    > [!CAUTION]
    > 파일럿 풀에 대해 정의한 풀 또는 서버 FQDN이 고유 해야 합니다. 현재 배포 된 레거시 풀이나 현재 배포 되어 있는 다른 서버의 이름에는 일치 시킬 수 없습니다. 
  
5. **기능 선택** 페이지에서이 프런트 엔드 풀에 대해 원하는 기능에 해당 하는 확인란을 선택 합니다. 예를 들어 메신저 (IM) 및 현재 상태 기능만을 배포 하는 경우에는 회의 확인란을 선택 하 여 단체 메신저를 허용 하지만 PSTN (Dial) 회의, 엔터프라이즈 음성 또는 통화 허용 제어 검사를 선택 하지 않습니다. 상자는 음성, 비디오, 공동 회의 기능을 나타냅니다. <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. **Collocated 서버 역할 선택** 페이지에서 비즈니스용 Skype server 2019에서 중재 서버를 collocate 하도록 선택 하는 것이 좋습니다. 레거시 토폴로지를 비즈니스용 Skype 서버 2019와 병합 하는 경우 먼저 레거시 중재 서버를 collocate 해야 합니다. 토폴로지를 병합 하 고 비즈니스용 Skype 서버 2019 조정 서버를 구성한 후에는 중재 서버 역할을 비즈니스용 Skype 서버로 이동할 때 collocated 중재 서버를 유지할지 또는 독립 실행형 서버로 변경할지를 결정할 수 있습니다. 배포 프로세스의 이후 2019. 
   
7. 이 프런트 엔드 풀을 사용 하 여 **서버 역할 연결** 페이지에서 파일럿 풀 배포 중에 **Edge 풀을이 프론트 엔드 풀의 미디어 구성 요소에서 사용할 수 있도록 설정** 합니다 옵션을 선택 *하지 마세요* . 이 기능을 사용 하 여 이후 마이그레이션 단계에서 온라인 상태로 만들 수 있습니다. 지금은이 설정을 지워짐 상태로 유지 합니다. 
  
8. **Office Web Apps 서버 선택** 페이지에서 **새로 만들기**를 클릭 하 고 응용 프로그램 서버의 FQDN을 지정 합니다.
  
9. 비즈니스용 skype server 보관 및 모니터링에 대해 SQL Server store를 정의할 때 **sql server Store 보관 정의** 페이지에서 비즈니스용 skype 서버 2019에 대해 이전에 만든 sql server 인스턴스를 선택 합니다. 
  
10. 토폴로지를 게시 하려면 **비즈니스용 Skype 서버** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **토폴로지 게시**를 클릭 합니다.
  
11. 게시 프로세스가 완료 되 면 **마침을**클릭 합니다.

12. "레거시 풀과 함께 조종사 풀 공존 여부 확인" 이라는 다음 섹션으로 이동 하기 전에 먼저 게시 된 토폴로지에서 정의한 비즈니스용 Skype Server의 새 프런트 엔드 파일럿 풀을 설치 해야 하며 여기에 나와 있는 Skype 설치 절차를 따르세요. [ 토폴로지에 있는 서버의 비즈니스 서버](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)

13. 이전 단계가 완료 되 면 다음 섹션으로 이동 하 여 레거시 풀과의 파일럿 풀 공존을 확인 합니다.
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
  

