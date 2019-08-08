---
title: 비즈니스용 Skype 서버 2015로 업그레이드
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: '요약: Lync Server 2013에서 비즈니스용 Skype Server 2015으로 업그레이드 하는 방법에 대해 알아봅니다. Microsoft 평가 센터에서 비즈니스용 Skype Server 2015의 무료 평가판을 다운로드 https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server하세요.'
ms.openlocfilehash: c34cbc7ce1d755f093ac14bc85d78106216c450b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237860"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015로 업그레이드
 
**요약:** Lync Server 2013에서 비즈니스용 Skype Server 2015으로 업그레이드 하는 방법에 대해 알아봅니다. [Microsoft 평가 센터](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)에서 비즈니스용 Skype 서버 2015 무료 평가판을 다운로드 하세요.
  
비즈니스용 Skype 서버 토폴로지 작성기 및 새로운 현재 업그레이드 기능을 사용 하 여 Lync Server 2013에서 비즈니스용 Skype Server 2015으로 업그레이드 하려면이 문서의 절차를 사용 합니다. Lync Server 2010 또는 Office Communications Server 2007 R2에서 업그레이드 하려는 경우 [비즈니스용 Skype Server 2015으로 업그레이드 계획](../plan-your-deployment/upgrade.md)을 참조 하세요.

> [!NOTE]
> 현재 위치 업그레이드는 비즈니스용 Skype 서버 2015에서 사용할 수 있었지만 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다. 나란히 coexistance 지원 되는 경우 자세한 내용은 [비즈니스용 Skype 서버 2019 마이그레이션을](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) 참조 하세요.
  
## <a name="upgrade-from-lync-server-2013"></a>Lync Server 2013에서 업그레이드

Lync Server 2013을 비즈니스용 Skype Server 2015으로 업그레이드 하는 경우 비즈니스용 Skype Server 토폴로지 작성기를 사용 하 여 풀의 데이터베이스를 업그레이드 하 고 각각의 비즈니스용 Skype Server의 현재 위치 업그레이드를 사용 하 여 필수 소프트웨어를 설치 해야 합니다. 풀과 연결 된 서버 업그레이드를 완료 하려면이 항목의 8 단계를 진행 합니다.
  
### <a name="before-you-begin"></a>시작 하기 전에

- [비즈니스용 Skype 서버 2015 업그레이드 계획을](../plan-your-deployment/upgrade.md)검토 합니다.
    
- [비즈니스용 Skype 서버 2015에 대 한 서버 요구 사항을](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)검토 합니다.
    
- [비즈니스용 Skype 서버 2015에 대 한 필수 구성 요소를 설치](install/install-prerequisites.md) 합니다.
    
- [비즈니스용 Skype 서버 2015을 설치](install/install.md) 합니다.
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a>1 단계: 관리자 도구 설치 및 토폴로지 다운로드

1. Lync OCSCore 또는 다른 Lync 구성 요소가 설치 되지 않은 토폴로지에서 컴퓨터에 연결 합니다.
    
2. 비즈니스용 Skype 서버 2015 설치 미디어에서 **setup.exe** 를 **OCS_Volume\Setup\AMD64**에서 실행 합니다. 
    
3. **설치**를 클릭 합니다. 
    
4. 사용권 계약에 동의 합니다.
    
5. 배포 마법사에서 **관리자 도구 설치**를 클릭 하 고 설치 단계를 따릅니다.
    
     ![' 관리자 설치 ' 도구에 대 한 링크가 포함 된 배포 마법사 스크린샷](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. Windows 시작 화면에서 비즈니스용 Skype 서버 토폴로지 작성기를 엽니다.
    
7. **기존 배포에서 토폴로지 다운로드**를 클릭 하 고 **다음**을 클릭 합니다.
    
8. 토폴로지의 이름을 입력 하 고 **저장**을 클릭 합니다.
    
9. 토폴로지를 저장 한 위치로 이동 하 여 토폴로지의 복사본을 만듭니다.
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a>2 단계: 토폴로지 작성기를 사용 하 여 토폴로지 업그레이드 및 게시

업그레이드 프로세스를 시작 하기 전에 업그레이드 하려는 풀에 대해 모든 서비스가 실행 중 이어야 합니다. 이렇게 하면 토폴로지 변경 내용이 풀에 있는 서버의 로컬 데이터베이스에 복제 됩니다.
  
> [!IMPORTANT]
>  업그레이드 하기 전에 토폴로지 파일의 복사본을 저장 합니다. 업그레이드 한 후에는 토폴로지를 다운 그레이드할 수 없습니다. 서비스가 데이터베이스와 같은 서버에 있는 경우 > 영구 채팅 서비스는 영구 채팅 데이터베이스와 같은 서버에 있으므로이 단계를 건너뛰고 4 단계로 이동 합니다. 서비스를 중지 한 후 각 서버에서 현재 위치 업그레이드 설정을 실행 하 여 로컬 데이터베이스를 업그레이드 합니다.
  
> [!NOTE]
> 토폴로지에 미러링 되는 백 엔드 데이터베이스가 있는 경우 토폴로지 작성기를 사용 하 여 **토폴로지를 게시** 하면 주 데이터베이스와 미러된 데이터베이스가 모두 표시 됩니다. 모든 데이터베이스가 주 서버에서 실행 되 고 있는지 확인 하 고 토폴로지를 게시할 때는 토폴로지가 아닌 사용자만 선택 하 고 토폴로지를 게시 한 후에는 경고가 표시 됩니다.
  
다음 옵션 중 하나를 선택 하 여 비즈니스용 Skype 서버 2015 토폴로지 작성기를 사용 하 여 새 토폴로지를 업그레이드 하 고 게시 합니다. 단계를 완료 하 고 업데이트 된 토폴로지를 게시 한 후에는이 항목의 3 단계로 이동 합니다.
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a>옵션 1: isolated 프런트 엔드 풀 및 연결 된 보관 및 모니터링 저장소 업그레이드

업그레이드 하는 풀에 보관 및 모니터링 저장소 종속성이 있는 경우 다음 단계를 사용할 때 보관 및 모니터링 저장소도 업그레이드 됩니다.
  
1. 토폴로지 작성기에서 Lync Server 2013 풀을 마우스 오른쪽 단추로 클릭 하 고 **비즈니스용 Skype Server 2015으로 업그레이드**를 선택 하 고 단계를 따릅니다. 
    
     ![Lync Server 2013의 업그레이드 옵션을 사용 하 여 마우스 오른쪽 단추 클릭 메뉴 스크린샷](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. 토폴로지 작성기에서 **작업** > **게시 토폴로지** 또는 **작업** > **토폴로지** > **게시**를 클릭 합니다. 
    
     ![토폴로지 작성기의 게시 토폴로지 옵션이 있는 작업 메뉴 스크린샷](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. 게시 하는 동안 보관 및 모니터링 저장소에 데이터베이스를 설치 하도록 선택 합니다.
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a>옵션 2: 보관 및 모니터링 저장소를 업그레이드 하지 않고 프런트 엔드 풀 업그레이드

다음 단계를 사용 하는 경우 선택한 풀에 대 한 보관 및 모니터링을 사용할 수 없습니다. 업그레이드 후에는 풀에 보관 및 모니터링 저장소가 남아 있지 않습니다.
  
1. 토폴로지 작성기에서 업그레이드 하려는 Lync Server 2013 풀을 선택 합니다.
    
2. Lync Server 2013 보관 및 모니터링 저장소에 대 한 종속성을 제거 합니다. 
    
   - **작업** > 으로 이동**속성을 편집**합니다.
    
   - **보관** 확인란의 선택을 취소 합니다.
    
     ![속성 편집 대화 상자의 보관 확인란 스크린샷](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - **모니터링** 확인란의 선택을 취소 합니다.
    
     ![모니터링 확인란을 showsr 하는 속성 편집 대화 상자의 스크린샷](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Lync Server 2013 풀을 마우스 오른쪽 단추로 클릭 하 고 **비즈니스용 Skype Server 2015으로 업그레이드**를 선택 하 고 단계를 따릅니다. 
    
     ![Lync Server 2013의 업그레이드 옵션을 사용 하 여 마우스 오른쪽 단추 클릭 메뉴 스크린샷](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. 토폴로지 작성기에서 **작업** > **게시 토폴로지** 또는 **작업** > **토폴로지** > **게시**를 클릭 합니다. 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a>옵션 3: 프런트 엔드 풀을 업그레이드 하 고 새 비즈니스용 Skype 서버 2015 보관 및 모니터링 저장소에 연결

다음 단계를 사용 하는 경우 보관 및 모니터링이 이전 스토어에서 중지 되 고 만든 새 상점에서 시작 됩니다. 
  
1. 토폴로지 작성기에서 업그레이드 하려는 Lync Server 2013 풀을 선택 합니다. 
    
2. Lync Server 2013 보관 및 모니터링 저장소에 대 한 종속성을 제거 합니다. 
    
   - **작업** > 으로 이동**속성을 편집**합니다.
    
   - **보관** 확인란의 선택을 취소 합니다.
    
     ![속성 편집 대화 상자의 보관 확인란 스크린샷](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - **모니터링** 확인란의 선택을 취소 합니다.
    
     ![모니터링 확인란을 showsr 하는 속성 편집 대화 상자의 스크린샷](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. Lync Server 2013 풀을 마우스 오른쪽 단추로 클릭 하 고 **비즈니스용 Skype Server 2015으로 업그레이드**를 선택 하 고 단계를 따릅니다. 
    
     ![Lync Server 2013의 업그레이드 옵션을 사용 하 여 마우스 오른쪽 단추 클릭 메뉴 스크린샷](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. 보관을 위한 새 SQL 저장소를 만듭니다. 
    
   - 풀 및 **작업** > **편집 속성**을 선택 합니다. 
    
   -  **보관** 확인란을 선택 합니다.
    
   - **새로 만들기**를 클릭 합니다.
    
     ![보관 섹션의 새로 만들기 단추를 표시 하는 속성 편집 대화 상자의 스크린샷](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. 모니터링을 위해 새 SQL 저장소를 만듭니다. 
    
   - 풀 및 **작업** > **편집 속성**을 선택 합니다. 
    
   -  **모니터링** 확인란을 선택 합니다.
    
   - **새로 만들기**를 클릭 합니다.
    
     ![모니터링 섹션 아래에 새로 만들기 단추가 표시 되는 속성 편집 대화 상자 스크린샷](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. 토폴로지 작성기에서 **작업** > **게시 토폴로지** 또는 **작업** > **토폴로지** > **게시**를 클릭 합니다. 
    
7. 게시 하는 동안 새 보관 및 모니터링 저장소에 데이터베이스를 설치 하도록 선택 합니다.
    
### <a name="step-3-wait-for-replication"></a>3 단계: 복제 대기

복제를 통해 환경의 모든 서버에 업데이트 된 토폴로지를 게시할 시간을 제공 합니다.
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a>4 단계: 풀에서 업그레이드할 모든 서비스 중지

업그레이드할 풀을 서비스 하는 각 서버에서 PowerShell에서 다음 cmdlet을 실행 합니다.
  
```
Disable-CsComputer -Scorch
```

현재 위치 업그레이드 프로세스를 진행 하는 동안 서버를 다시 부팅 해야 할 수 있으므로, Disable-CsComputer를 사용 하는 것이 좋습니다. CsWindowsService를 사용 하는 경우 재부팅 후 일부 서비스가 자동으로 다시 시작 될 수 있습니다. 이로 인해 현재 위치 업그레이드가 실패할 수 있습니다.
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a>5 단계: 프런트 엔드 풀 및 비 프런트 엔드 풀 서버 업그레이드

> [!NOTE]
>  업그레이드 하기 전에, 다음을 포함 하는 비즈니스용 Skype 서버 2015에 필요한 새 필수 구성 요소를 모두 설치 하세요. 업그레이드를 시도 하기 전에 최소한 32GB의 여유 공간이 >. 또한 드라이브가 고정 로컬 드라이브이 고, USB 또는 Firewire에 의해 연결 되지 않고, NTFS 파일 시스템으로 포맷 되며, 압축 되지 않고 페이지 파일이 포함 되어 있지 않은지 확인 합니다. > PowerShell 버전 6.2.9200.0 이상. 최신 Lync Server 2013을 > 합니다. 누적 업데이트가 설치 되었습니다. > SQL Server 2012 SP1이 설치 되어 있습니다. Microsoft 업데이트를 사용 하는 경우 자동으로 설치 되는 다음 KB의 설치 된 >. > Windows Server 2008 R2-[KB2533623](https://support.microsoft.com/kb/2533623)> windows server 2012-[KB2858668](https://support.microsoft.com/kb/2858668)> windows 서버 2012 R2-[KB2982006](https://support.microsoft.com/kb/2982006)
  
각 서버의 현재 위치 업그레이드를 사용 하 여 프런트 엔드 풀, Edge 풀, 중재 서버 및 영구 채팅 풀을 업데이트 합니다.
  
1. 각 서버에서 비즈니스용 Skype 서버 2015 설치 미디어의 **OCS_Volume\Setup\amd64** 에서 setup.exe를 실행 **합니다** .
    
2. 사용권 계약에 동의 하 고 현재 위치 업그레이드에 대 한 메시지를 따릅니다.
    
3. 프런트 엔드 풀 및 각 비 프런트 엔드 풀 서버의 각 서버에 대해이 단계를 반복 합니다.
    
> [!NOTE]
> 현재 위치 업그레이드 중에 서버를 다시 부팅 하 라는 메시지가 표시 될 수 있습니다. 괜찮아요. 다시 부팅 한 후에는 즉시 업그레이드를 계속 합니다. 
  
현재 위치 업그레이드가 성공적으로 완료 되 면 다음 메시지가 표시 됩니다.
  
![현재 위치 업그레이드를 성공적으로 완료 하 고 표시 하는 스크린샷.](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a>6 단계: 업그레이드 된 모든 서버에서 서비스 다시 시작

> [!NOTE]
> 서비스를 다시 시작 하기 전에 모든 프런트 엔드 서버에%ProgramData%\WindowsFabric이 없는지 확인 하세요. 서비스가 있는 경우 서비스를 시작 하기 전에 삭제 합니다. 
  
- 프런트 엔드 풀의 모든 서버를 업그레이드 한 후 다음 PowerShell 명령을 사용 하 여 서비스를 다시 시작 합니다. 
    
  ```
  Start-CsPool
  ```

    > [!NOTE]
    > 현재 위치 업그레이드를 시작 하기 전에 이미 시스템을 다시 부팅 해야 하는 경우 현재 위치 업그레이드는 설치 종료 시 재부팅을 요청 하지 않습니다. 이렇게 하면 시작-CSPool cmdlet을 사용 하 여 서비스를 시작 하려고 할 때 첫 번째 프런트 엔드 서버에 대해 일부 어셈블리 예외가 throw 됩니다. 이러한 오류를 해결 하려면 풀의 모든 서버를 다시 부팅 하 고 cmdlet을 다시 실행 합니다. 
  
- 프런트 엔드 이외의 풀 서버에서 다음 명령을 사용 하 여 서비스를 다시 시작 합니다.
    
  ```
  Start-CsWindowsService
  ```

현재 위치 업그레이드 페이지에서 **확인** 을 클릭 하면 다음 미리 알림이 표시 되어이 단계를 완료할 수 있습니다.
  
![현재 위치 업그레이드가 성공적으로 완료 되 면 다음 단계를 보여 주는 스크린샷](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a>7 단계: 비즈니스용 Skype 기능이 작동 하는지 확인

업그레이드의 성공 여부를 확인 하려면 업그레이드 된 풀에 대해 비즈니스용 Skype를 테스트 하 여 기능이 예상 대로 작동 하는지 확인 합니다. 
  
### <a name="step-8-upgrade-secondary-pools"></a>8 단계: 보조 풀 업그레이드

이 항목의 단계를 반복 하 여 환경에 보유 하 고 있는 추가 풀을 업그레이드 합니다.
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a>현재 위치 업그레이드 문제 해결

현재 위치 업그레이드에 실패 하면 다음 이미지와 비슷한 메시지가 표시 될 수 있습니다. 
  
![필요한 누적 업데이트가 설치 되어 있지 않아 현재 위치 업그레이드에 실패 하는 스크린샷.](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
페이지의 맨 아래에 있는 전체 메시지를 검토 하 여 문제 해결을 지원 합니다. 자세한 정보를 보려면 **로그 보기** 를 클릭 합니다.
  
**업그레이드 준비를 확인** 하거나 **누락 된 필수 구성 요소를 설치**하는 동안 현재 위치 업그레이드에 실패 하는 경우 서버에 모든 최신 Windows server, Lync server, SQL server 업데이트가 적용 되었는지 확인 하 고 필요한 모든 소프트웨어와 역할이 설치한. 필수 사항 목록은 비즈니스용 [Skype server 2015의 서버 요구 사항](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) 및 비즈니스용 [skype server 2015의 필수 구성 요소 설치](install/install-prerequisites.md)를 참조 하세요.
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버 2015 업그레이드 계획](../plan-your-deployment/upgrade.md)
  
[비즈니스용 Skype 서버 2015의 서버 요구 사항](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[비즈니스용 Skype 서버 2015에 대 한 필수 구성 요소 설치](install/install-prerequisites.md)
  
[비즈니스용 Skype 서버 2015 설치](install/install.md)
