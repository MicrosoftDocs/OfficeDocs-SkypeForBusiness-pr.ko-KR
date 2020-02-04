---
title: 'Lync Server 2013: 프런트 엔드 풀 ABC 장애 조치(failover) 절차'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool ABC failover procedure
ms:assetid: 67763ad3-6796-45eb-a486-901f21ac1a95
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945635(v=OCS.15)
ms:contentKeyID: 51541486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edf3d12aa519ab7746ccec92998995ed463aa9be
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739778"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-pool-abc-failover-procedure-in-lync-server-2013"></a>Lync Server 2013의 프런트 엔드 풀 ABC 장애 조치(failover) 절차

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-05-22_

ABC 장애 조치 절차를 수행 하려면 다음 단계를 사용 합니다. 이 절차에는 각 단계에 대 한 상위 수준의 설명과 각 단계에 대해 실행할 명령 및 cmdlet이 포함 되어 있습니다.

Cmdlet을 실행 하려면 관리자로 실행을 사용 하 여 Lync Server Management Shell을 엽니다.

<div>

## <a name="to-perform-an-abc-failover"></a>ABC 장애 조치를 수행 하려면

1.  풀 A가 중앙 관리 서버 (CMS)에 대 한 호스트인 여부를 확인 합니다.
    
      - 다음 cmdlet을 실행 합니다.
        
            Get-CsService -CentralManagement
        
        활성 CMS의 Id 필드가 풀 A의 FQDN (정규화 된 도메인 이름)을 가리키는 경우이 절차의 2 단계와 3 단계를 사용 하 여 중앙 관리 서버를 먼저 장애 조치 (fail) 합니다. 그렇지 않으면 4 단계로 건너뜁니다.

2.  다음 cmdlet을 실행 하 여 재해 복구 모드에서 CMS를 풀 B로 장애 조치 합니다.
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    이 작업을 수행한 후 추가 복구를 위해 먼저 그룹 B에서 다른 기존 페어링 풀로 CMS를 이동 하는 것이 좋습니다. 자세한 내용은 [이동-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)을 참조 하세요.

3.  Pool에 CMS가 포함 된 경우 풀 A의 lis 구성을 풀 B의 LIS 데이터베이스 (Lis)로 가져옵니다. 이 기능은 정기적으로 LIS 데이터를 백업 하는 경우에만 사용할 수 있습니다. LIS 구성을 가져오려면 다음 cmdlet을 실행 합니다.
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  풀 A의 Lync Server 응답 그룹 서비스 워크플로를 풀 B에 가져옵니다.
    
    <div>
    

    > [!NOTE]  
    > 현재 <STRONG>CsRgsConfiguration</STRONG> cmdlet에서는 풀 A의 큐 및 워크플로 이름이 풀 B의 큐 및 워크플로 이름과 구분 되어야 합니다. 이름이 고유 하지 않은 경우 <STRONG>CsRgsConfiguration</STRONG> cmdlet을 실행할 때 오류가 발생 하 고 <STRONG>CsRgsConfiguration</STRONG> cmdlet을 진행 하기 전에 풀 B에서 큐와 워크플로의 이름을 변경 해야 합니다.

    
    </div>
    
    응답 그룹 구성을 풀 A에서 풀 B로 가져오기 위한 두 가지 옵션이 있습니다. 사용 하는 옵션은 풀 B의 응용 프로그램 수준 설정을 해당 그룹 A의 응용 프로그램 수준 설정으로 덮어쓸지 여부에 따라 달라 집니다.
    
      - 풀 B 설정을 덮어쓰려면 **ReplaceExistingSettings** 옵션을 사용 하 여 **CsRgsConfiguration** cmdlet을 실행 합니다.
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - 풀 B 설정을 덮어쓰지 않으려면 **ReplaceExistingSettings** 옵션 없이 **CsRgsConfiguration** cmdlet을 사용 합니다.
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > 백업 풀 (풀 B)의 응용 프로그램 수준 설정을 기본 풀의 설정으로 덮어쓰지 않으려는 경우 (풀 a), 응답 그룹 응용 프로그램에서 풀 A가 손실 되 면 풀 A의 응용 프로그램 수준 설정이 손실 됨을 염두에 두십시오. 풀 당 하나의 응용 프로그램 수준 설정 집합만 저장 합니다. 풀 C를 배포 하 여 풀 A를 대체 하는 경우 기본 음악 대기 오디오 파일을 포함 하 여 응용 프로그램 수준 설정을 다시 구성 해야 합니다.

    
    </div>

5.  다음 cmdlet을 실행 하 여 가져온 응답 그룹을 표시 하 여 응답 그룹 구성 가져오기가 성공적으로 수행 되었는지 확인 합니다. 가져온 응답 그룹은 여전히 풀 A에 의해 소유 됨을 참고 하세요.
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  지정 하지 않은 번호에 대해 "공지 사항"을 사용 하는 할당 되지 않은 번호 범위를 그룹 A에서 풀 B로 선택한 알림 서비스로 이동 합니다. 실행할 작업:
    
      - 그룹 B의 풀 A에 배포 된 모든 알림을 다시 만듭니다. 풀 A에 알림을 배포할 때 오디오 파일을 사용 하는 경우에는이 파일이 풀 B에 알림을 다시 만드는 데 필요 합니다. 그룹 B에서 알림을 다시 만들려면 상위 서비스로 서 그룹 B를 사용 하 여 **새 CsAnnouncement** cmdlet을 사용 합니다.
    
      - 풀 A의 공지 사항을 대상으로 하는 모든 할당 되지 않은 번호 범위를 그룹 a의 새로 배포 된 공지 사항에 대해 실행 합니다. 풀 A의 공지 사항 대상으로 지정 되지 않은 모든 숫자 범위에 대해 다음 cmdlet을 실행 합니다.
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    
    <div>
    

    > [!NOTE]  
    > "Exchange UM"을 선택한 알림 서비스로 사용 하는 할당 되지 않은 숫자 범위에는이 단계가 필요 하지 않습니다.

    
    </div>

7.  다음 cmdlet을 실행 하 여 재해 복구 (DR) 모드의 풀 A를 풀 A로 장애 조치 합니다.
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  풀 C를 빌드 하지만, 풀 C에서 서비스를 시작 하지는 않습니다.
    
    이 단계는 5와 6 단계를 사용 하 여 동시에 수행할 수 있다는 점에 유의 하세요.

9.  다음 cmdlet을 실행 하 여 풀 A에 속한 사용자를 강제로 그룹 C로 이동 합니다.
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    이 시점에서 풀 A에 있는 사용자는 서비스 중단을 시작 합니다. 이 중단 시간은 C 풀에서 시작 되는 지점 서비스의 16 단계까지 계속 됩니다.

10. 다음 cmdlet을 실행 하 여 A 풀의 컨퍼런스 디렉터리를 C 풀로 이동 하도록 강제 합니다.
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. 다음 cmdlet을 실행 하 여 자동 전화 교환 (CAA) Contact 개체를 강제 하 여 풀 A에서 풀 C로 이동 합니다.
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. 그룹 B에서 그룹 C로 회의 콘텐츠를 복사 합니다.

13. 그룹 B에서 사용자 데이터를 내보내고 다음 cmdlet을 실행 하 여 사용자 데이터를 풀 C로 가져옵니다.
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. 백업 통화를 복원 하 여 풀 A에서 풀 C로 응용 프로그램 데이터를 확보 하 고 풀 A의 통화 공원 궤도 범위를 풀 C에 할당 합니다.
    
      - Lync Server 제어판 또는 Lync Server Management Shell을 통해 풀 A의 통화 공원 궤도 범위를 A 풀 C로 다시 할당할 수 있습니다. Lync Server 관리 셸에서는 풀 A에 할당 된 모든 통화 공원 궤도 범위에 대해 다음 cmdlet을 실행 합니다 (Id 매개 변수는 풀 A에 속하는 통화 대기 궤도 범위를 참조 한다는 점에 유의).
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - 풀 A의 통화 파킹에 대해 사용자 지정 된 음악을 구성한 경우, 풀 C에서 통화 공원 사용자 지정 된 음악-고정 파일을 복원 합니다.
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        예를 들면 다음과 같습니다.
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - 마지막으로 **CsCpsConfiguration** cmdlet을 사용 하 여 풀 C의 통화 공원 설정을 다시 구성 합니다. 통화 공원 응용 프로그램은 하나의 설정 집합 및 사용자 지정 된 음악/보류 오디오 파일만 저장할 수 있으며, 이러한 설정은 재해가 발생 했을 때 백업 되거나 보존 되지 않습니다.

15. 영구 채팅의 다음 홉 풀이 풀 A를 가리키고 있는 경우 다음 홉 서버가 풀 C를 가리키도록 토폴로지 변경 사항을 적용 하 고 게시 합니다.
    
      - 토폴로지 작성기에서 영구 채팅 풀을 다음 홉으로 풀 C를 가리키도록 변경 합니다. 이렇게 하려면 영구 채팅 풀을 마우스 오른쪽 단추로 클릭 한 다음 **일반** 탭을 클릭 하 고 **다음 홉 풀**에 풀 C의 이름을 입력 합니다.
    
      - 다음 cmdlet을 실행 하 여 C 풀에서 서비스를 시작 합니다.
        
            Start-csWindowsService
    
    이 시점에서 그룹 A에 원래 홈에 있는 사용자에 대 한 서비스 중단은 종료 됩니다.

16. 다음 cmdlet을 실행 하 여 풀 A가 소유 하는 풀 B에서 Lync Server 응답 그룹 서비스 워크플로를 내보내기로 가져옵니다.
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. Lync Server 응답 그룹 서비스 워크플로를 그룹 B에서 풀 C로 가져옵니다.
    
    두 가지 옵션은 그룹 B에서 그룹 C로 응답 그룹 구성을 가져오는 데 사용 됩니다. 사용 하는 옵션은 풀 C의 응용 프로그램 수준 설정을 해당 풀 B의 응용 프로그램 수준 설정으로 덮어쓸지 여부에 따라 달라 집니다.
    
      - 풀 C 설정을 덮어쓰려면 **ReplaceExistingSettings** 옵션을 사용 하 여 **CsRgsConfiguration** cmdlet을 실행 합니다.
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - 풀 C 설정을 덮어쓰지 않으려면 **ReplaceExistingSettings** 옵션 없이 **CsRgsConfiguration** cmdlet을 사용 합니다.
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > 풀 C의 응용 프로그램 수준 설정을 백업 풀의 설정으로 덮어쓰지 않으려는 경우 응답 그룹 응용 프로그램에서 응용 프로그램 수준의 집합을 하나만 저장할 수 있기 때문에 그룹 B의 응용 프로그램 수준 설정이 손실 됨을 염두에 두십시오. 풀 당 설정.

    
    </div>

18. 다음 cmdlet을 실행 하 여 풀 C로 가져온 응답 그룹을 표시 하 여 응답 그룹 구성 가져오기가 성공적으로 수행 되었는지 확인 합니다.
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. 가져온 구성을 풀 C에서 확인 한 경우에는 풀 B의 기본 풀에서 소유 하는 응답 그룹을 제거 합니다. 이렇게 하면 응답 그룹의 가동 중지 시간이 최소화 됩니다.
    
    이 단계에서는 내보낸 구성을 사용 하 여 새 파일을 만든 다음 해당 파일을 풀 B에서 제거 합니다.
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. 풀 A에서 그룹 A에서 그룹 B로 이동 된, 할당 되지 않은 숫자 범위
    
      - 풀 A에서 다시 생성 한 모든 공지 사항 C의 풀 A에서 그룹 B 이동할 알림을 배포할 때 오디오 파일을 사용 하는 경우이 파일을 사용 하 여 그룹 C에서 알림을 다시 만들어야 합니다. 풀 C에서 알림을 다시 만들려면 상위 서비스로 C 풀을 사용 하 여 **새 csannouncement** cmdlet을 사용 합니다.
    
      - 대상 그룹으로 지정 그룹 A에서 그룹 A로 대상을 변경한 할당 되지 않은 모든 숫자 범위: 대상 지정이 해제 되어야 하는 지정 되지 않은 모든 숫자 범위에 대해 다음 cmdlet을 실행 합니다.
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - ) 풀 B에서 제거 된 공지는 풀 b에서 더 이상 사용 되지 않는 경우에는 풀 C에 다시 생성 됩니다. 알림을 제거 하려면 **Csannouncement 공고** cmdlet을 사용 합니다.
        
        <div>
        

        > [!NOTE]  
        > "Exchange UM"을 알림 서비스로 사용 하는 할당 되지 않은 숫자 범위에는이 단계가 필요 하지 않습니다.

        
        </div>

21. 다음 cmdlet을 실행 하 여 그룹 B에서 풀 A의 사용자 데이터를 정리 합니다.
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. 토폴로지 작성기에서 다음을 실행 합니다.
    
      - 언 페어링 풀 A 및 풀 B-페어 풀 B 및 풀 C. 그런 다음 토폴로지에서 풀 A를 제거 하 고 게시 합니다. 실행할 작업:
        
          - 토폴로지 작성기에서 Pool B를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.
        
          - 왼쪽 창에서 **회복성 (탄력성** )을 클릭 합니다.
        
          - **연결 된 백업 풀**아래 상자에서 pool C를 선택 합니다. 그룹 B는 이전에이 풀에 연결 되어 있기 때문에 연결 된 백업 풀 선택 상자에는 처음에 그룹 A가 표시 됩니다.
        
          - **자동 장애 조치 및 음성 장애 복구**를 선택한 다음 **확인**을 클릭 합니다.
            
            이 풀에 대 한 세부 정보를 볼 때 이제 오른쪽 창의 **복원 력**아래에 연결 된 풀이 표시 됩니다.
        
          - 콘솔 트리에서 풀 A를 마우스 오른쪽 단추로 클릭 한 다음 삭제를 클릭 합니다.
        
          - 토폴로지를 게시 합니다.

23. 풀 C에서 부트스트랩 응용 프로그램을 실행 하 여 백업 서비스 응용 프로그램을 설치 하 고 다음을 실행 하 여 풀 C의 로컬 컴퓨터에 있는 배포 폴더에서 다음을 수행 합니다.
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. 다음 cmdlet을 실행 하 여 풀 B의 백업 서비스 응용 프로그램을 다시 시작 합니다.
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. 풀 C가 SE (Standard Edition) 풀이 고 풀 B에 CMS가 있는 경우 다음 cmdlet을 실행 하 여 풀 C에 CMS 데이터베이스를 수동으로 설치 합니다.
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. 백업 서비스를 호출 하 여 이전 회의 콘텐츠를 그룹 B에서 연결 하 고, B와 C를 함께 연결 하기 전에 생성 된 풀 C로 동기화 하 고, 풀 c의 새 회의 콘텐츠를 그룹 c로 시작 하 고 B와 C가 서로 쌍을 이룬 그룹 B와 동기화 합니다. 이렇게 하려면 다음 cmdlet을 실행 합니다.
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. 풀 A에 연결 된 각 Survivable Branch 기기 X에 대해 다음을 수행 합니다.
    
      - 다음 cmdlet을 실행 하 여 SBA X를 종료 합니다.
        
            Stop-CsWindowsService
    
      - SBA X에 속한 사용자 목록을 포함 하는 파일을 만듭니다. 이 목록은 사용자를 30 단계에서 SBA X로 다시 이동할 때 필요 합니다. 이렇게 하려면 다음 cmdlet을 실행 합니다.
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - 다음 cmdlet을 실행 하 여 SBA X에 속한 사용자를 강제로 그룹 C로 이동 합니다.
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - 다음 cmdlet을 먼저 실행 하 여 이러한 사용자의 데이터를 업데이트 합니다.
        
            Convert-csUserData -InputFile <Data file exported from PoolB> -OutputFile c:\Logs\ExportedUserData.xml -TargetVersionLync2010 
            $a=get-csuser -Filter {RegistrarPool -eq "FQDN of SBA X"} | select SipAddress
            foreach($x in $a) {$x.SipAddress.Substring(4) >> users.txt}
        
        그런 다음이 스크립트를 실행 합니다.
        
            $users=gc c:\logs\users.txt
            foreach ($user in $users)
            {
            Update-CsUserData -FileName c:\logs\exportedUserDAta.xml -UserFilter $user - 
            }
        
        <div>
        

        > [!NOTE]  
        > 이 사용자가 SBAs로 이동할 때까지 풀 A에 연결 된 사용자에 대해 서비스 중단이 발생 합니다.

        
        </div>

28. 토폴로지 작성기에서 이전에 풀 A와 연결 된 각 SBA X에 대해 다음을 수행 합니다.
    
      - 풀 C와의 연결을 변경 합니다. 이렇게 하려면 지점 사이트를 클릭 하 고 Survivable Branch 기기 또는 서버 노드를 확장 한 다음, **Survivable Branch 기기**를 클릭 합니다. 그런 다음이 Survivable 분기 기기가 해당 기기에 연결 하는 **프런트 엔드 풀, 사용자 서비스 풀** 을 선택 하 고 **다음**을 클릭 합니다.
    
      - 토폴로지를 게시 합니다. 이렇게 하려면 콘솔 트리에서 새 **Survivable Branch 기기**를 마우스 오른쪽 단추로 클릭 하 고 **토폴로지**를 클릭 한 다음 **게시**를 클릭 합니다.

29. 현재 풀 C에 연결 된 각 SBA X:
    
      - Survivable branch 기기에서 다음 cmdlet을 실행 하 여 SBA X를 시작 합니다.
        
            Start-CsWindowsService
    
      - 다음 cmdlet을 실행 하 여 SBA X에서 원래 설정한 사용자를 풀 C에서 SBA X로 이동 합니다.
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

</div>

</div>

<span> </span>

</div>

</div>

</div>

