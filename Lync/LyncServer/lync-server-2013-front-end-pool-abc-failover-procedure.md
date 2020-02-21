---
title: 'Lync Server 2013: 프런트 엔드 풀 ABC 장애 조치 (failover) 절차'
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
ms.openlocfilehash: f60ded6539f6d984662449562d0f978e98dc3078
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="front-end-pool-abc-failover-procedure-in-lync-server-2013"></a>Lync Server 2013의 프런트 엔드 풀 ABC 장애 조치 (failover) 절차

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-05-22_

ABC 장애 조치 (failover) 절차를 수행 하려면 다음 단계를 사용 합니다. 이 절차에는 각 단계에 대 한 간략 한 설명과 각 단계에 대해 실행할 명령 및 cmdlet이 포함 되어 있습니다.

Cmdlet을 실행 하려면 관리자 권한으로 실행을 사용 하 여 Lync Server 관리 셸을 엽니다.

<div>

## <a name="to-perform-an-abc-failover"></a>ABC 장애 조치 (Failover)를 수행 하려면

1.  풀 A가 중앙 관리 서버 (CMS)에 대 한 호스트 인지 확인 합니다.
    
      - 다음 cmdlet을 실행합니다.
        
            Get-CsService -CentralManagement
        
        활성 CMS의 Identity 필드가 풀 A의 FQDN (정규화 된 도메인 이름)을 가리키면이 절차의 2 단계와 3 단계로 중앙 관리 서버를 먼저 장애 조치 (failover) 합니다. 그렇지 않은 경우에는 4 단계로 건너뜁니다.

2.  다음 cmdlet을 실행 하 여 재해 복구 모드에서 CMS를 풀 B로 장애 조치 (failover) 합니다.
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    이 작업을 수행한 후 추가 복구를 위해 CMS를 풀 B에서 기존의 다른 연결 된 풀로 이동 하는 것이 좋습니다. 자세한 내용은 [Move-move-csmanagementserver](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)를 참조 하십시오.

3.  풀 A에 CMS가 포함 되어 있는 경우 풀 A에서 풀 B의 LIS 데이터베이스 (Lis)로 LIS 구성을 가져옵니다. 이 작업은 LIS 데이터를 정기적으로 백업 하는 경우에만 작동 합니다. LIS 구성을 가져오려면 다음 cmdlet을 실행 합니다.
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  풀 A에서 풀 B로 백업한 Lync Server 응답 그룹 서비스 워크플로를 가져옵니다.
    
    <div>
    

    > [!NOTE]  
    > 현재 <STRONG>export-csrgsconfiguration</STRONG> cmdlet을 사용 하려면 풀 A의 큐와 워크플로 이름이 풀 B의 큐와 워크플로 이름과 달라 지는 것이 좋습니다. 이름이 고유 하지 않으면 <STRONG>export-csrgsconfiguration</STRONG> cmdlet을 실행할 때 오류가 발생 하 고 <STRONG>export-csrgsconfiguration</STRONG> cmdlet을 계속 하기 전에 풀 B에서 큐 및 워크플로의 이름을 변경 해야 합니다.

    
    </div>
    
    응답 그룹 구성을 풀 A에서 풀 B로 가져오는 두 가지 옵션을 사용할 수 있습니다. 사용 하는 옵션은 풀 B의 응용 프로그램 수준 설정을 해당 풀 A의 응용 프로그램 수준 설정과 덮어쓸지 여부에 따라 달라 집니다.
    
      - 풀 B 설정을 덮어쓰려면 **ReplaceExistingSettings** 옵션을 사용 하 여 **export-csrgsconfiguration** cmdlet을 실행 합니다.
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - 풀 B 설정을 덮어쓰지 않으려면 **ReplaceExistingSettings** 옵션 없이 **export-csrgsconfiguration** cmdlet을 사용 합니다.
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > 백업 풀의 응용 프로그램 수준 설정 (풀 A)을 기본 풀의 설정으로 덮어쓰지 않으려면 응답 그룹 응용 프로그램은 풀 a의 응용 프로그램 수준 설정이 손실 될 수 있으므로 해당 설정에 대 한 손실을 방지 하는 것이 좋습니다. 풀 당 하나의 응용 프로그램 수준 설정 집합만 저장 합니다. 풀 C를 배포 하 여 풀 A를 대체 하는 경우 기본 음악 대기 오디오 파일을 포함 하 여 응용 프로그램 수준 설정을 다시 구성 해야 합니다.

    
    </div>

5.  다음 cmdlet을 실행 하 여 가져온 응답 그룹을 표시 하 여 응답 그룹 구성 가져오기가 성공적으로 수행 되었는지 확인 합니다. 가져온 응답 그룹은 여전히 풀 A에서 소유 하 고 있습니다.
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  할당 되지 않은 번호의 경우 "공지 사항"을 사용 하는 지정 되지 않은 번호 범위를 선택한 알림 서비스로 그룹 A에서 풀 B로 이동 합니다. 이렇게 하려면 다음을 수행 합니다.
    
      - 풀 A에 배포 된 모든 알림을 그룹 B에 다시 만듭니다. 풀 A에 알림을 배포할 때 오디오 파일을 사용 하는 경우에는이 파일이 풀 B에 알림을 다시 만들어야 합니다. 풀 B에서 알림을 다시 만들려면 상위 서비스로 B 풀을 사용 하 여 **새 CsAnnouncement** cmdlet을 사용할 수 있습니다.
    
      - 풀 A에서 공지를 대상으로 하는 모든 지정 되지 않은 번호 범위를 pool A에 있는 새로 배포 된 공지로, 그룹 A의 알림을 대상으로 하는 지정 되지 않은 모든 번호 범위에 대해 다음 cmdlet을 실행 합니다.
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    
    <div>
    

    > [!NOTE]  
    > "Exchange UM"을 선택한 알림 서비스로 사용 하는 할당 되지 않은 번호 범위에는이 단계가 필요 하지 않습니다.

    
    </div>

7.  다음 cmdlet을 실행 하 여 재해 복구 (DR) 모드의 풀 A를 풀 A로 장애 조치 (failover) 합니다.
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  풀 C를 구축 하 되, 풀 C에서는 서비스를 시작 하지 않습니다.
    
    이 단계는 5 및 6 단계와 동시에 수행할 수 있습니다.

9.  다음 cmdlet을 실행 하 여 풀 A에 있는 사용자를 그룹 C로 이동 하도록 강제 합니다.
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    이때 풀 A에 있는 사용자가 서비스 중단을 경험할 수 있습니다. 이 중단은 16 단계까지 계속 되며, 서비스가 풀 C에서 시작 됩니다.

10. 다음 cmdlet을 실행 하 여 풀 A의 전화 회의 디렉터리를 풀 C로 이동 합니다.
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. 다음 cmdlet을 실행 하 여 전화 회의 자동 전화 교환 (CAA) 연락처 개체를 강제 풀 A에서 풀 C로 이동 합니다.
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. 풀 B에서 풀 C로 회의 콘텐츠를 복사 합니다.

13. 풀 B에서 사용자 데이터를 내보내고 다음 cmdlet을 실행 하 여 사용자 데이터를 풀 C로 가져옵니다.
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. 풀 A에서 풀 a로 백업한 통화 대기 응용 프로그램 데이터를 복원 하 고 풀 A의 통화 대기 번호 범위를 pool C에 할당 합니다.
    
      - Lync Server 제어판 또는 Lync Server 관리 셸을 통해 풀 A의 통화 대기 궤도 범위를 풀 C에 다시 할당할 수 있습니다. Lync Server 관리 셸에서 풀 A에 할당 된 모든 통화 대기 번호 범위에 대해 다음 cmdlet을 실행 합니다 (Identity 매개 변수는 풀 A에 속하는 통화 대기 번호 범위를 참조 한다는 점에 유의).
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - 풀 A의 통화 대기에 대해 사용자 지정 된 음악 연결을 구성한 경우에는 풀 C에서 통화 대기 사용자 지정 된 보류 중인 파일을 복원 합니다.
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        예:
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - 마지막으로 **new-cscpsconfiguration** cmdlet을 사용 하 여 풀 C의 통화 대기 설정을 다시 구성 합니다. 통화 대기 응용 프로그램은 하나의 설정 집합 및 사용자 지정 된 음악 대기 오디오 파일을 풀 당 하나만 저장할 수 있으며 재해 발생 시 이러한 설정이 백업 되거나 보존 되지 않습니다.

15. 영구 채팅에 대 한 다음 홉 풀이 풀 A를 가리키고 토폴로지 변경 내용을 만들고 게시 하 여 다음 홉 서버가 풀 C를 가리키도록 설정 합니다.
    
      - 토폴로지 작성기에서 영구 채팅 풀이 다음 홉으로 Pool C를 가리키도록 변경 합니다. 이렇게 하려면 영구 채팅 풀을 마우스 오른쪽 단추로 클릭 하 고 **일반** 탭을 클릭 한 다음 **다음 홉 풀**에 풀 C의 이름을 입력 합니다.
    
      - 다음 cmdlet을 실행 하 여 풀 C에서 서비스를 시작 합니다.
        
            Start-csWindowsService
    
    이 시점에서 서비스 중단은 원래 풀 A에 있는 사용자에 대해 종료 됩니다.

16. 다음 cmdlet을 실행 하 여 가져오기 위해 풀 A가 소유 하는 풀 B에서 Lync Server Response Group 서비스 워크플로를 풀 C로 내보냅니다.
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. Lync Server 응답 그룹 서비스 워크플로를 풀 B에서 풀 C로 가져옵니다.
    
    그룹 B에서 풀 C로 응답 그룹 구성을 가져오는 두 가지 옵션을 사용할 수 있습니다. 사용 하는 옵션은 풀 C의 응용 프로그램 수준 설정을 응용 프로그램 수준 설정과 풀 B에서 덮어쓸지 여부에 따라 달라 집니다.
    
      - 그룹 C 설정을 덮어쓰려면 **ReplaceExistingSettings** 옵션을 사용 하 여 **export-csrgsconfiguration** cmdlet을 실행 합니다.
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - 풀 C 설정을 덮어쓰지 않으려면 **ReplaceExistingSettings** 옵션 없이 **export-csrgsconfiguration** cmdlet을 사용 합니다.
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > 그룹 C의 응용 프로그램 수준 설정을 백업 풀 (풀 B)의 설정으로 덮어쓰지 않으려면 응답 그룹 응용 프로그램은 하나의 응용 프로그램 수준 집합만 저장할 수 있으므로 풀 B의 응용 프로그램 수준 설정이 손실 됩니다. 풀 당 설정

    
    </div>

18. 다음 cmdlet을 실행 하 여 풀 C로 가져온 응답 그룹을 표시 하 여 응답 그룹 구성 가져오기가 성공적으로 수행 되었는지 확인 합니다.
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. 풀 C에서 가져온 구성을 확인 한 경우에는 풀 B에서 기본 풀이 소유한 응답 그룹을 제거 합니다. 이렇게 하면 응답 그룹의 가동 중지 시간이 최소화 됩니다.
    
    이 단계에서는 내보낸 구성을 사용 하 여 새 파일을 만든 다음 풀 B에서 해당 파일을 제거 합니다.
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. 풀로 이동 그룹 A가 풀 A에서 풀 B로 이동 된 지정 되지 않은 번호 범위입니다.
    
      - 풀 A에서 다시 만듭니다. C 풀 A에서 풀 A를 다시 만든 모든 공지입니다. 이동할 알림을 배포할 때 오디오 파일을 사용 하는 경우에는 이러한 파일을 사용 하 여 풀 C에 알림을 다시 만들어야 합니다. 풀 C에서 알림을 다시 만들려면 **새-csannouncement** cmdlet을 사용 하 고, 상위 서비스로 C를 풀 합니다.
    
      - 대상 그룹으로 지정-그룹 A에서 풀 B로 대상이 지정 되지 않은 모든 할당 되지 않은 번호 범위에 대해 다음 cmdlet을 실행 합니다.
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - 반드시 풀 B에서 제거 풀 C에서 더 이상 사용 하지 않는 경우에는 해당 이전에 다시 만들어진 공지입니다. 알림을 제거 하려면 **csannouncement** a r i 공지 cmdlet을 사용 합니다.
        
        <div>
        

        > [!NOTE]  
        > "Exchange UM"을 알림 서비스로 사용 하는 할당 되지 않은 번호 범위에는이 단계가 필요 하지 않습니다.

        
        </div>

21. 다음 cmdlet을 실행 하 여 풀 A에서 풀 A의 사용자 데이터를 정리 합니다.
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. 토폴로지 작성기에서 다음을 수행 합니다.
    
      - Unpair 풀 A 및 풀 B와 풀 C를 차례로 두 번 누릅니다. 그런 다음 토폴로지에서 풀 A를 제거 하 고 게시 합니다. 방법은 다음과 같습니다.
        
          - 토폴로지 작성기에서 풀 B를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.
        
          - 왼쪽 창에서 **복구** 를 클릭 합니다.
        
          - **연결 된 백업 풀**아래 상자에서 pool C를 선택 합니다 .이 풀은 이전에 풀 B와 연결 되어 있으므로 연결 된 백업 풀 선택 상자에 먼저 그룹 A가 표시 됩니다.
        
          - **자동 음성 장애 조치(failover) 및 장애 복구(failback)** 를 선택하고 **확인**을 클릭합니다.
            
            이제 이 풀에 대한 세부 정보를 표시하면 연결된 풀이 오른쪽 창의 **탄성** 아래에 표시됩니다.
        
          - 콘솔 트리에서 풀 A를 마우스 오른쪽 단추로 클릭 한 다음 삭제를 클릭 합니다.
        
          - 토폴로지를 게시합니다.

23. 풀 C에서 부트스트랩 응용 프로그램을 실행 하 여 백업 서비스 응용 프로그램을 설치한 다음, 풀 C의 로컬 컴퓨터에 있는 배포 폴더에서 다음을 실행 하 여 백업 서비스 응용 프로그램을 시작 합니다.
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. 다음 cmdlet을 실행 하 여 풀 B에서 백업 서비스 응용 프로그램을 다시 시작 합니다.
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. 풀 C가 SE (Standard Edition) 풀이 고 풀 B에 CMS가 있는 경우 다음 cmdlet을 실행 하 여 풀 C에 CMS 데이터베이스를 수동으로 설치 합니다.
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. 백업 서비스를 호출 하 여 이전 회의 콘텐츠를 그룹 B에서 함께 연결 하기 전에 생성 된 pool C로 동기화 하 고, 풀 c와 B 및 C가 함께 연결 된 풀 B에서 새 회의 콘텐츠를 연결 합니다. 이렇게 하려면 다음 cmdlet을 실행합니다.
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. 풀 A와 연결 된 각 Sba (survivable 분기 기기 X에 대해 다음을 수행 합니다.
    
      - 다음 cmdlet을 실행 하 여 SBA X를 종료 합니다.
        
            Stop-CsWindowsService
    
      - SBA X에 홈에 있는 사용자 목록을 포함 하는 파일을 만듭니다. 이 목록은 사용자를 30 단계에서 SBA X로 다시 이동할 때 필요 합니다. 이렇게 하려면 다음 cmdlet을 실행 합니다.
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - SBA X에 있는 사용자가 다음 cmdlet을 실행 하 여 풀 C로 이동 하도록 강제 합니다.
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - 다음 cmdlet을 먼저 실행 하 여 이러한 사용자의 데이터를 업데이트 합니다.
        
            Convert-csUserData -InputFile <Data file exported from PoolB> -OutputFile c:\Logs\ExportedUserData.xml -TargetVersionLync2010 
            $a=get-csuser -Filter {RegistrarPool -eq "FQDN of SBA X"} | select SipAddress
            foreach($x in $a) {$x.SipAddress.Substring(4) >> users.txt}
        
        다음 스크립트를 실행 합니다.
        
            $users=gc c:\logs\users.txt
            foreach ($user in $users)
            {
            Update-CsUserData -FileName c:\logs\exportedUserDAta.xml -UserFilter $user - 
            }
        
        <div>
        

        > [!NOTE]  
        > 풀 A에 연결 된 SBAs에 있는 사용자가 그룹 C로 이동 될 때까지 서비스 중단이 발생 합니다.

        
        </div>

28. 토폴로지 작성기에서 이전에 풀 A와 연결 된 각 SBA X에 대해 다음을 수행 합니다.
    
      - 풀 C로 연결을 변경 합니다. 이렇게 하려면 분기 사이트를 클릭 하 고 Sba (survivable Branch 기기 또는 Servers 노드를 확장 한 다음 **Sba (survivable Branch 기기**를 클릭 합니다. 그런 다음이 Sba (survivable 분기 기기가이를 풀 C로 연결 하는 **프런트 엔드 풀, 사용자 서비스 풀을** 선택 하 고 **다음**을 클릭 합니다.
    
      - 토폴로지를 게시합니다. 이렇게 하려면 콘솔 트리에서 새 **Sba (survivable Branch 기기**를 마우스 오른쪽 단추로 클릭 하 고 **토폴로지**를 클릭 한 다음 **게시**를 클릭 합니다.

29. 이제 풀 C에 연결 된 각 SBA X에 대해 다음을 수행 합니다.
    
      - Sba (survivable branch 기기에서 다음 cmdlet을 실행 하 여 SBA X를 시작 합니다.
        
            Start-CsWindowsService
    
      - 다음 cmdlet을 실행 하 여 SBA X에 원래 있던 사용자를 풀 C에서 SBA X로 이동 합니다.
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

</div>

</div>

<span> </span>

</div>

</div>

</div>

