---
title: 'Lync Server 2013: 중앙 관리 저장소를 호스팅하는 서버 복원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring the server hosting the Central Management store
ms:assetid: 3bd6c82c-07fb-4798-b8f9-e7c78a5a83d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202172(v=OCS.15)
ms:contentKeyID: 51541464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95696c682e7acfba32e4f9a2bfd71ba988f22243
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-the-server-hosting-the-central-management-store-in-lync-server-2013"></a>Lync Server 2013에서 중앙 관리 저장소를 호스팅하는 서버 복원

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-21_

Lync Server 배포에는 단일 중앙 관리 저장소가 있으며,이 복사본은 Lync Server 서버 역할을 실행 하는 각 서버에 복제 됩니다. 이 항목에서는 중앙 관리 저장소를 호스트 하는 백 엔드 서버 또는 Standard Edition 서버를 복원 하는 방법에 대해 설명 합니다.

중앙 관리 서버가 있는 풀을 찾으려면 토폴로지 작성기를 열고 **Lync Server**를 클릭 하 고 **중앙 관리 서버**아래의 오른쪽 창에서 확인 합니다.

중앙 관리 저장소를 호스트 하는 백 엔드 서버가 미러링된 설정에 있고 미러 데이터베이스가 제대로 작동 하는 경우에는이 계속 작동 하는 미러의 백업을 만든 다음 기본 데이터베이스와 두 파일 모두에서 전체 복원을 수행 하는 것이 좋습니다. 다음 복원 절차에 따라이 백업을 사용 하 여 데이터베이스를 미러링합니다. 백 엔드 복원에는 토폴로지를 수정 하 고 게시 해야 하기 때문에이 작업이 필요 하며, CMS를 호스트 하는 기본 데이터베이스가 작동 하는 경우에만 이렇게 할 수 있습니다. 또한 토폴로지가 게시 될 수 없는 경우 기본 및 미러 데이터베이스 역할은 서로를 사용할 수 없다는 점에 유의 하세요.

<div>


> [!NOTE]  
> 중앙 관리 저장소를 호스팅하지 않는 백 엔드 서버 또는 Standard Edition 서버에 오류가 발생 하는 경우 lync <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">server 2013에서 Enterprise Edition 백 엔드 서버 복원</A> 또는 <A href="lync-server-2013-restoring-a-standard-edition-server.md">lync Server 2013에서 Standard edition 서버 복원</A>을 참조 하세요. 중앙 관리 저장소를 호스트 하는 백 엔드 서버가 미러링된 구성에 있고 미러만 실패 한 경우에는 <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Lync server 2013-미러에서 미러된 Enterprise Edition 백 엔드 서버 복원을</A>참조 하세요. 다른 서버에 오류가 발생 한 경우 <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">에는 Lync server 2013에서 Enterprise Edition 구성원 서버 복원을</A>참조 하세요.



</div>

<div>


> [!TIP]  
> 복원을 시작 하기 전에 시스템의 이미지 복사본을 사용 하는 것이 좋습니다. 복원 중에 문제가 발생 하는 경우이 이미지를 롤백 시점으로 사용할 수 있습니다. 운영 체제 및 SQL Server를 설치 하 고 인증서를 복원 하거나 reenroll 이미지 복사본을 사용할 수 있습니다.



</div>

<div>

## <a name="to-restore-the-central-management-store"></a>중앙 관리 저장소를 복원 하려면

1.  실패 한 컴퓨터와 FQDN (정규화 된 도메인 이름)이 동일한 깨끗 한 새 서버를 사용 하 여 시작 하 고, 운영 체제를 설치한 다음, 인증서를 복원 하거나 reenroll.
    
    <div>
    

    > [!NOTE]  
    > 조직의 서버 배포 절차에 따라이 단계를 수행 합니다.

    
    </div>

2.  RTCUniversalServerAdmins 그룹 및 로컬 관리자 그룹의 구성원 인 사용자 계정에서 복원 하려는 서버에 로그온 합니다.

3.  스탠더드 버전 서버를 복원 하는 경우 $Backup의 적절 한 파일 저장소를 서버의 파일 저장소 위치에 복사 하 여 파일 저장소를 복원 하 고 폴더를 공유 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 파일을 사용 하는 구성 요소에서 액세스할 수 있도록 복원 된 파일 저장소의 경로와 파일 이름이 백업 된 파일 저장소와 정확히 동일 해야 합니다.

    
    </div>

4.  다음 중 하나를 수행 합니다.
    
      - 스탠더드 버전 서버를 설치 하는 경우 Lync Server 설치 폴더 또는 미디어로 이동한 다음, 설치 \\\\Amd64\\Setup.exe에 있는 lync server 배포 마법사를 시작 합니다. 배포 마법사에서 **첫 번째 Standard Edition Server 준비** 를 클릭 하 고 마법사의 지시에 따라 중앙 관리 저장소를 설치 합니다.
    
      - 엔터프라이즈 백 엔드 서버를 설치 하는 경우 SQL Server 2012 또는 SQL Server 2008 R2를 설치 하 고 인스턴스 이름을 오류 전과 동일 하 게 유지 합니다.
        
        <div>
        

        > [!NOTE]  
        > 복원 하는 서버와 배포에 따라 서버에 여러 collocated 또는 별도의 데이터베이스가 포함 될 수 있습니다. SQL Server 사용 권한 및 로그인을 포함 하 여 처음에 서버를 배포 하는 데 사용한 SQL Server를 설치 하려면 같은 절차를 따릅니다.

        
        </div>

5.  프런트 엔드 서버에서 Lync Server Management Shell을 시작 합니다. **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server management shell**을 클릭 합니다.

6.  중앙 관리 저장소를 다시 만듭니다. 명령줄에 다음을 입력 합니다.
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    예를 들면 다음과 같습니다.
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  중앙 관리 저장소에 대 한 Active Directory 도메인 서비스 제어 지점을 설정 합니다. 명령줄에 다음을 입력 합니다.
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    예를 들면 다음과 같습니다.
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    <div>
    

    > [!NOTE]  
    > 연결 지점이 손실 된 경우이 cmdlet을 다시 실행할 수 있습니다.

    
    </div>

8.  $Backup에서 중앙 관리 저장소 데이터를 가져옵니다. 명령줄에 다음을 입력 합니다.
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    예를 들면 다음과 같습니다.
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  방금 변경한 내용을 사용 하도록 설정 합니다. 명령줄에 다음을 입력 합니다.
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > 토폴로지를 사용 하도록 설정한 후에는 데이터베이스에서 토폴로지 문서를 찾을 수 있습니다.

    
    </div>

10. CMS를 호스트 하는 Enterprise Edition 백 엔드 서버를 복원 하거나 CMS의 미러를 다시 만들어야 하는 경우이 단계를 수행 합니다. 그렇지 않으면 11 단계로 건너뜁니다.
    
    다음을 수행 하 여 독립 실행형 데이터베이스를 설치 합니다.
    
    1.  토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.
    
    2.  **기존 배포에서 토폴로지 다운로드**를 클릭 한 다음 **확인**을 클릭 합니다.
    
    3.  토폴로지를 선택한 다음 **저장**을 클릭 합니다. **예** 를 클릭 하 여 선택 내용을 확인 합니다.
    
    4.  **Lync Server 2013** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **데이터베이스 설치**를 클릭 합니다.
    
    5.  **데이터베이스 설치** 마법사를 따릅니다. 이 서버의 중앙 관리 저장소 이외의 데이터베이스를 복원 하는 경우 **데이터베이스 만들기** 페이지에서 다시 만들려는 데이터베이스를 선택 합니다.
        
        <div>
        

        > [!NOTE]  
        > <STRONG>데이터베이스 만들기</STRONG> 페이지에는 독립 실행형 데이터베이스만 표시 됩니다. Collocated 데이터베이스는 Lync Server 배포 마법사를 실행할 때 만들어집니다.

        
        </div>
    
    6.  미러 백 엔드 서버를 복원 하는 경우 미러 데이터베이스 만들기 메시지가 나타날 때까지 마법사의 나머지 단계를 계속 진행 합니다. 설치 하고자 하는 데이터베이스를 선택 하 고 프로세스를 완료 합니다.
    
    7.  마법사의 나머지 단계를 따르고 **마침을**클릭 합니다.
    
    <div>
    

    > [!TIP]  
    > 토폴로지 작성기를 실행 하는 대신, <STRONG>설치-CsDatabase</STRONG> cmdlet을 사용 하 여 각 데이터베이스를 만들고 <STRONG>CsMirrorDatabase</STRONG> cmdlet을 사용해 미러링을 구성할 수 있습니다. 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">설치-CsDatabase</A> 및 <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">install-CsMirrorDatabase</A>을 참조 하세요.

    
    </div>

11. Standard Edition server를 복원 하는 경우 Lync Server 설치 폴더 또는 미디어를 찾아 설치 \\\\Amd64\\Setup.exe에 있는 lync server 배포 마법사를 시작 합니다. Lync Server 배포 마법사를 사용 하 여 다음을 수행 합니다.
    
    1.  **1 단계: 로컬 구성 저장소 설치** 를 실행 하 여 로컬 구성 파일을 설치 합니다.
    
    2.  **2 단계: lync Server 구성 요소 설치 또는 제거** 를 실행 하 여 lync server 서버 역할을 설치 합니다.
    
    3.  **3 단계: 인증서 요청, 설치 또는 할당** 을 실행 하 여 인증서를 할당 합니다.
    
    4.  서버에서 서비스를 시작 하려면 **4 단계: 서비스 시작** 을 실행 합니다.
    
    배포 마법사를 실행 하는 방법에 대 한 자세한 내용은 복원할 서버 역할에 대 한 배포 설명서를 참조 하세요.

12. 다음을 수행 하 여 사용자 데이터를 복원 합니다.
    
    1.  $Backup\\ 에서 로컬 디렉터리로 ExportedUserData을 복사 합니다.
    
    2.  사용자 데이터를 복원 하기 전에 Lync 서비스를 중지 해야 합니다. 이렇게 하려면 다음을 입력 합니다.
        
            Stop-CsWindowsService
    
    3.  사용자 데이터를 복원 하려면 명령줄에 다음을 입력 합니다.
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        예를 들면 다음과 같습니다.
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  다음과 같이 입력 하 여 Lync 서비스를 다시 시작 합니다.
        
            Start-CsWindowsService

13. 위치 정보 데이터를 중앙 관리 저장소에 복원 합니다. 명령줄에 다음을 입력 합니다.
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    예를 들면 다음과 같습니다.
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. 이 풀 또는 Standard Edition 서버에서 응답 그룹을 배포한 경우 응답 그룹 구성 데이터를 복원 합니다. 자세한 내용은 [Lync Server 2013에서 응답 그룹 설정 복원을](lync-server-2013-restoring-response-group-settings.md)참조 하세요.

15. 보관 또는 모니터링 데이터베이스가 포함 된 백 엔드 서버를 복원 하는 경우 sql Server Management Studio와 같은 SQL Server 관리 도구를 사용 하 여 보관 또는 모니터링 데이터를 복원 합니다. 자세한 내용은 [Lync Server 2013에서 모니터링 또는 데이터 보관 복구](lync-server-2013-restoring-monitoring-or-archiving-data.md)를 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

