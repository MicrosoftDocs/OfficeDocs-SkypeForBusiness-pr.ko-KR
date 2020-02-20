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
ms.openlocfilehash: 1da289a6c0cf73e1466acdf28a74b1fbce76251a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-back-end-server-in-lync-server-2013"></a>Lync Server 2013에서 Enterprise Edition 백 엔드 서버 복원

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-18_

이 항목에서 설명 하는 절차는 다음과 같은 두 가지 경우에 사용 합니다.

  - 미러된 Enterprise Edition 백 엔드 서버의 기본 데이터베이스와 미러 데이터베이스가 모두 실패 합니다.

  - 미러링 되지 않은 Enterprise Edition 백 엔드 서버가 작동 하지 않습니다.

미러된 Enterprise Edition 백 엔드가 있고 미러 또는 기본 데이터베이스만 오류가 발생 하는 경우에 [는 Lync server 2013에서 미러된 Enterprise Edition 백 엔드 서버 복원을](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) 참조 하 여 기본 데이터베이스를 복원 하 고, [lync server 2013-미러에서 미러링된 Enterprise Edition 백 엔드 서버를 복원](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) 하 여 미러를 복원 합니다.

중앙 관리 저장소에 오류가 발생 하면 [Lync server 2013에서 중앙 관리 저장소를 호스트 하는 서버 복원을](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)참조 하세요. 백 엔드 서버가 아닌 Enterprise Edition 구성원 서버가 실패 하면 [Lync server 2013에서 Enterprise edition 구성원 서버 복원을](lync-server-2013-restoring-an-enterprise-edition-member-server.md)참조 하십시오.

<div>


> [!TIP]  
> 복원을 시작 하기 전에 시스템의 이미지 복사본을 사용 하는 것이 좋습니다. 복원 중에 문제가 발생 하는 경우를 대비 하 여이 이미지를 롤백 지점으로 사용할 수 있습니다. 운영 체제 및 SQL Server를 설치 하 고 인증서를 복원 하거나 reenroll 후 이미지 복사본을 사용할 수 있습니다.



</div>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server"></a>Enterprise Edition 백 엔드 서버를 복원하려면

1.  오류가 발생 한 컴퓨터와 FQDN (정규화 된 도메인 이름)이 동일한 깨끗 한 서버 또는 새 서버로 시작 하 고, 운영 체제를 설치한 후 인증서를 복원 하거나 reenroll 합니다.
    
    <div>
    

    > [!NOTE]  
    > 조직의 서버 배포 절차에 따라 이 단계를 수행합니다.

    
    </div>

2.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정에서 복원 중인 서버에 로그온 합니다.

3.  SQL Server 2012 또는 SQL Server 2008 r 2를 설치 하 고 인스턴스 이름을 오류 이전과 동일 하 게 유지 합니다.
    
    <div>
    

    > [!NOTE]  
    > 배포에 따라 백 엔드 서버에는 여러 개의 배치되었거나 개별적인 데이터베이스가 포함될 수 있습니다. SQL Server 권한 및 로그인을 포함하여 원래 서버를 배포할 때 사용한 동일한 절차에 따라 SQL Server를 설치합니다.

    
    </div>

4.  SQL Server를 설치한 후 다음을 수행합니다.
    
    1.  토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.
    
    2.  **기존 배포에서 토폴로지 다운로드**를 클릭한 후 **확인**을 클릭합니다.
    
    3.  토폴로지를 선택한 후 **저장**을 클릭합니다. **예**를 클릭하여 선택을 확인합니다.
    
    4.  **Lync Server 2013** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **토폴로지 게시**를 클릭 합니다.
    
    5.  **토폴로지 게시** 마법사를 따릅니다. **데이터베이스 만들기** 페이지에서 다시 만들 데이터베이스를 선택 합니다.
        
        <div>
        

        > [!NOTE]  
        > 독립 실행형 데이터베이스만 <STRONG>데이터베이스 만들기</STRONG> 페이지에 표시됩니다.

        
        </div>
    
    6.  미러링된 백 엔드를 복원 하는 경우에는 메시지를 **만들 때 미러 데이터베이스 만들기** 가 표시 될 때까지 마법사의 나머지 단계를 계속 진행 합니다. 설치할 데이터베이스를 선택 하 고 프로세스를 완료 합니다.
    
    7.  나머지 마법사의 단계를 따른 후 **마침**을 클릭합니다.
    
    <div>
    

    > [!TIP]  
    > 토폴로지 작성기를 실행 하는 대신 <STRONG>설치-CsDatabase</STRONG> cmdlet을 사용 하 여 각 데이터베이스를 만들고 <STRONG>CsMirrorDatabase</STRONG> cmdlet을 통해 미러링을 구성할 수 있습니다. 자세한 내용은 Lync Server 관리 셸 설명서를 참조하십시오.

    
    </div>

5.  다음을 수행하여 사용자 데이터를 복원합니다.
    
    1.  $Backup\\ 에서 로컬 디렉터리로 ExportedUserData를 복사 합니다.
    
    2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.
    
    3.  사용자 데이터를 복원 하기 전에 Lync services를 중지 해야 합니다. 이렇게 하려면 다음을 입력 합니다.
        
            Stop-CsWindowsService
    
    4.  사용자 데이터를 복원하려면 명령줄에 다음을 입력합니다.
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        예:
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  다음을 입력 하 여 Lync Services를 다시 시작 합니다.
        
            Start-CsWindowsService

6.  이 풀에 응답 그룹을 배포한 경우 응답 그룹 구성 데이터를 복원 합니다. 자세한 내용은 [Lync Server 2013에서 응답 그룹 설정 복원을](lync-server-2013-restoring-response-group-settings.md)참조 하십시오.

7.  보관 또는 모니터링 데이터베이스가 포함된 백 엔드 서버를 복원 중인 경우 SQL Server 도구(예: SQL Server Management Studio)를 사용하여 보관 또는 모니터링 데이터를 복원합니다. 자세한 내용은 [Lync Server 2013에서 모니터링 또는 보관 데이터 복원을](lync-server-2013-restoring-monitoring-or-archiving-data.md)참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

