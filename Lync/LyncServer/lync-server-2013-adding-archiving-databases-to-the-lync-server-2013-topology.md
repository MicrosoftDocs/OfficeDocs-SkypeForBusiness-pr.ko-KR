---
title: 'Lync Server 2013: Lync Server 2013 토폴로지에 보관 데이터베이스 추가'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding Archiving databases to the Lync Server 2013 topology
ms:assetid: 089ab32f-1167-4bb8-a283-fdc6c9613072
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204654(v=OCS.15)
ms:contentKeyID: 48183338
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e73fe49aaf3a5b90a23bcfd6b99c9a5bb4476513
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008794"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-archiving-databases-to-the-lync-server-2013-topology"></a>Lync Server 2013 토폴로지에 보관 데이터베이스 추가

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-10_

보관을 지원하도록 배포를 구성하려면 먼저 토폴로지에 보관을 통합해야 합니다. 이 항목의 정보에서는 토폴로지 작성기를 사용 하 여 기존 토폴로지에 보관을 추가 하는 방법에 대해 설명 합니다.

<div>


> [!NOTE]  
> Microsoft Exchange 통합을 사용 하 여 배포의 모든 사용자에 대해 Exchange 2013 서버에 보관 데이터 및 파일을 저장 하려면 <STRONG>보관 Sql server 저장소</STRONG> 를 지정 하거나 <STRONG>sql server 저장소 미러링</STRONG> 정보를 사용 하지 마십시오.



</div>

<div>

## <a name="to-add-archiving-database-support-to-your-topology"></a>토폴로지에 보관 데이터베이스 지원을 추가하려면

1.  Lync Server 2013을 실행 중이거나 Lync Server 관리 도구가 설치 된 컴퓨터에서 로컬 사용자 그룹의 구성원 인 계정 또는 이와 동등한 사용자 권한을 가진 계정을 사용 하 여 로그온 합니다.
    
    <div>
    

    > [!NOTE]  
    > 로컬 Users 그룹의 구성원 인 계정을 사용 하 여 토폴로지를 정의할 수 있지만 토폴로지를 게시 하려면 토폴로지에 서버를 추가 하는 데 필요 합니다. <STRONG>Domain Admins</STRONG> 그룹 및 <STRONG>RTCUniversalServerAdmins</STRONG> 그룹의 구성원 인 계정을 사용 해야 하며, Lync server 2013 파일 저장소에 사용 하는 파일 공유에 대 한 모든 권한 (읽기, 쓰기 및 수정)을 포함 하는 경우, 즉 토폴로지 작성기에서 필요한 dacl (임의 액세스 제어 목록)을 구성할 수 있도록 합니다. 또는 이와 동등한 권한을 가진 계정

    
    </div>

2.  토폴로지 작성기를 시작합니다.

3.  콘솔 트리에서 보관을 배포할 프런트 엔드 풀로 이동한 다음 보관을 배포할 프런트 엔드 풀의 이름을 클릭합니다.

4.  **동작** 메뉴에서 **속성 편집**을 클릭합니다.

5.  **속성 편집** 대화 상자에서 **일반**을 클릭합니다.

6.  아래쪽의 **보관**으로 스크롤합니다.

7.  **보관** 확인란을 선택합니다.

8.  **SQL Server 저장소 보관** 에서 다음 중 하나를 수행 합니다.
    
      - 기존 SQL Server 저장소를 사용하려면 드롭다운 목록 상자에서 사용할 SQL Server 저장소의 이름을 클릭합니다. 모든 사용자가 Microsoft Exchange Server 2013 이상에 있는 경우 Exchange의 모든 사용자에 대 한 Lync 통신을 보관할 수 있습니다. 이 경우 SQL Server 보관 저장소를 구성할 필요가 없습니다.
    
      - 새 SQL Server 저장소를 지정 하려면 **새로 만들기**를 클릭 하 고 **새 Sql server 저장소 정의** 대화 상자에서 다음을 수행 합니다.
        
          - **Sql SERVER fqdn**에서 새 SQL Server 저장소를 만들 서버의 FQDN을 지정 합니다.
        
          - **기본 인스턴스**를 클릭하여 기본 인스턴스를 사용하거나, 다른 인스턴스를 지정하려면 **명명된 인스턴스**를 클릭하고 사용할 인스턴스를 지정합니다.
        
          - 지정 된 SQL Server 인스턴스가 미러링 관계에 있는 경우 **이 SQL 인스턴스가 미러링 관계에** 있습니다. 확인란을 선택한 다음 **미러 포트 번호**에 포트 번호를 지정 합니다.

9.  SQL Server 저장소 미러링을 사용 하려면 **Sql Server 저장소 미러링 사용**을 선택 하 고 다음을 수행 합니다.
    
      - 미러링에 대해 기존 SQL Server 저장소를 사용 하려면 **보관 SQL server 저장소 미러** 드롭다운 목록 상자에서 미러링에 사용할 sql Server 저장소의 이름을 클릭 합니다.
    
      - 미러링 용으로 새 SQL Server 저장소를 지정 하려면 **새로 만들기**를 클릭 하 고 **새 SQL server 저장소 정의** 대화 상자에서 다음 중 하나를 수행 합니다.
        
        1.  **Sql SERVER fqdn**에서 새 sql server 저장소를 만들 sql SERVER의 FQDN을 지정 합니다.
        
        2.  **기본 인스턴스**를 클릭하여 기본 인스턴스를 사용하거나, 다른 인스턴스를 지정하려면 **명명된 인스턴스**를 클릭하고 사용할 인스턴스를 지정합니다.
        
        3.  지정 된 SQL Server 인스턴스가 미러링 관계에 있는 경우 **이 SQL 인스턴스가 미러링 관계에** 있습니다. 확인란을 선택한 다음 **미러 포트 번호**에 포트 번호를 지정 합니다.
    
      - SQL Server 미러링을 사용 하도록 설정 하 고 SQL Server 미러링 모니터 서버를 포함 하려면 (기본 SQL Server server 및 미러 인스턴스의 상태를 검색할 수 있는 세 개의 별도 SQL Server 인스턴스), **Sql server 미러링 모니터 서버가 자동 장애 조치 (failover** )를 사용 하도록 설정 확인란을 선택 하 고 다음 중 하나를 수행 합니다.
        
        1.  **Sql SERVER fqdn**에서 새 SQL Server 미러링 모니터 서버를 만들 서버의 FQDN을 지정 합니다.
        
        2.  **기본 인스턴스**를 클릭하여 기본 인스턴스를 사용하거나, 다른 인스턴스를 지정하려면 **명명된 인스턴스**를 클릭하고 미러링 모니터 서버에 사용할 인스턴스를 지정합니다.
        
        3.  지정 된 SQL Server 인스턴스가 미러링 관계에 있는 경우 **이 SQL 인스턴스가 미러링 관계에** 있습니다. 확인란을 선택한 다음 **미러 포트 번호**에 포트 번호를 지정 합니다.

10. 구성을 저장하려면 **확인**을 클릭합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

