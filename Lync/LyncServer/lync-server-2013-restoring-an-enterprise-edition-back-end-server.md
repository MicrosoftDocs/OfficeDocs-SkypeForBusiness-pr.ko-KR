---
title: 'Lync Server 2013: Enterprise Edition 백 엔드 서버 복원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition Back End Server
ms:assetid: 1450eb4e-3315-4d02-8f02-6e1791fb1550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202163(v=OCS.15)
ms:contentKeyID: 51541446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2bd57054505b3200f63bed8a60c47b400f7e7642
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733228"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-back-end-server-in-lync-server-2013"></a>Lync Server 2013에서 Enterprise Edition 백 엔드 서버 복원

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-18_

이 항목에 설명 된 절차는 다음 두 가지 경우에 사용 합니다.

  - 미러된 Enterprise Edition 백 엔드 서버의 기본 및 미러 데이터베이스 모두에 오류가 발생 합니다.

  - 미러링 되지 않는 Enterprise Edition 백 엔드 서버가 실패 합니다.

미러된 Enterprise Edition 백 엔드를 사용 하 고 있는 경우 미러 또는 기본 데이터베이스에 오류가 발생 하는 경우 [Lync server 2013에서 미러된 Enterprise Edition 백 엔드 서버 복원을](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) 참조 하세요-기본 데이터베이스를 복원 하 고 미러 [Enterprise Edition 백 엔드 서버를 복원 하 여 lync server 2013-](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) 미러를 복원 하는 데 사용 됩니다.

중앙 관리 저장소에 오류가 발생 하는 경우 [Lync server 2013에서 중앙 관리 저장소를 호스팅하는 서버 복원을](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)참조 하세요. 백 엔드 서버가 아닌 Enterprise Edition 구성원 서버가 실패 하는 경우 [Lync server 2013에서 Enterprise edition 구성원 서버 복원을](lync-server-2013-restoring-an-enterprise-edition-member-server.md)참조 하세요.

<div>


> [!TIP]  
> 복원을 시작 하기 전에 시스템의 이미지 복사본을 사용 하는 것이 좋습니다. 복원 중에 문제가 발생 하는 경우이 이미지를 롤백 시점으로 사용할 수 있습니다. 운영 체제 및 SQL Server를 설치 하 고 인증서를 복원 하거나 reenroll 이미지 복사본을 사용할 수 있습니다.



</div>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server"></a>Enterprise Edition 백 엔드 서버를 복원 하려면

1.  실패 한 컴퓨터와 FQDN (정규화 된 도메인 이름)이 동일한 깨끗 한 새 서버를 사용 하 여 시작 하 고, 운영 체제를 설치한 다음, 인증서를 복원 하거나 reenroll.
    
    <div>
    

    > [!NOTE]  
    > 조직의 서버 배포 절차에 따라이 단계를 수행 합니다.

    
    </div>

2.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정에서 복원 하려는 서버에 로그온 합니다.

3.  SQL Server 2012 또는 SQL Server 2008 R2를 설치 하 고 인스턴스 이름을 오류 전과 동일 하 게 유지 합니다.
    
    <div>
    

    > [!NOTE]  
    > 배포에 따라 백 엔드 서버에 여러 collocated 또는 별도의 데이터베이스가 포함 될 가능성이 있습니다. SQL Server 사용 권한 및 로그인을 포함 하 여 처음에 서버를 배포 하는 데 사용한 SQL Server를 설치 하려면 같은 절차를 따릅니다.

    
    </div>

4.  SQL Server를 설치한 후 다음을 수행 합니다.
    
    1.  토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.
    
    2.  **기존 배포에서 토폴로지 다운로드**를 클릭 한 다음 **확인**을 클릭 합니다.
    
    3.  토폴로지를 선택한 다음 **저장**을 클릭 합니다. **예** 를 클릭 하 여 선택 내용을 확인 합니다.
    
    4.  **Lync Server 2013** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **토폴로지 게시**를 클릭 합니다.
    
    5.  **토폴로지 게시** 마법사를 따릅니다. **데이터베이스 만들기** 페이지에서 다시 생성 하려는 데이터베이스를 선택 합니다.
        
        <div>
        

        > [!NOTE]  
        > <STRONG>데이터베이스 만들기</STRONG> 페이지에는 독립 실행형 데이터베이스만 표시 됩니다.

        
        </div>
    
    6.  미러링된 백 엔드를 복원 하는 경우에는 **미러 데이터베이스 만들기** 메시지가 나타날 때까지 마법사의 나머지 단계를 계속 진행 합니다. 설치 하려는 데이터베이스를 선택 하 고 프로세스를 완료 합니다.
    
    7.  마법사의 나머지 단계를 따르고 **마침을**클릭 합니다.
    
    <div>
    

    > [!TIP]  
    > 토폴로지 작성기를 실행 하는 대신, <STRONG>설치-CsDatabase</STRONG> cmdlet을 사용 하 여 각 데이터베이스를 만들고 <STRONG>CsMirrorDatabase</STRONG> cmdlet을 사용해 미러링을 구성할 수 있습니다. 자세한 내용은 Lync Server 관리 셸 설명서를 참조 하세요.

    
    </div>

5.  다음을 수행 하 여 사용자 데이터를 복원 합니다.
    
    1.  $Backup\\ 에서 로컬 디렉터리로 ExportedUserData을 복사 합니다.
    
    2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.
    
    3.  사용자 데이터를 복원 하기 전에 Lync 서비스를 중지 해야 합니다. 이렇게 하려면 다음을 입력 합니다.
        
            Stop-CsWindowsService
    
    4.  사용자 데이터를 복원 하려면 명령줄에 다음을 입력 합니다.
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        예를 들면 다음과 같습니다.
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  다음과 같이 입력 하 여 Lync 서비스를 다시 시작 합니다.
        
            Start-CsWindowsService

6.  이 풀에 응답 그룹을 배포한 경우 응답 그룹 구성 데이터를 복원 합니다. 자세한 내용은 [Lync Server 2013에서 응답 그룹 설정 복원을](lync-server-2013-restoring-response-group-settings.md)참조 하세요.

7.  보관 또는 모니터링 데이터베이스가 포함 된 백 엔드 서버를 복원 하는 경우 sql Server Management Studio와 같은 SQL Server 도구를 사용 하 여 보관 또는 모니터링 데이터를 복원 합니다. 자세한 내용은 [Lync Server 2013에서 모니터링 또는 데이터 보관 복구](lync-server-2013-restoring-monitoring-or-archiving-data.md)를 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

