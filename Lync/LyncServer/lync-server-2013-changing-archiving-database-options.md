---
title: 'Lync Server 2013: 보관 데이터베이스 옵션 변경'
description: 'Lync Server 2013: 보관 데이터베이스 옵션을 변경 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changing Archiving database options
ms:assetid: 3775f09d-65b0-48bc-8a4d-d97bd0c3423c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204814(v=OCS.15)
ms:contentKeyID: 48183879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a3751be63e17688ad9258b9773a1a5397b67952
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543584"
---
# <a name="changing-archiving-database-options-in-lync-server-2013"></a>Lync Server 2013에서 보관 데이터베이스 옵션 변경

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

사용자의 보관 저장소에 대해 SQL Server 저장소를 사용 하 여 보관을 배포 하는 경우 다음과 같은 데이터베이스 저장소 변경 작업을 수행할 수 있습니다.

  - 보관 저장소에 다른 SQL Server 데이터베이스를 사용 합니다. 여기에는 기본 보관 데이터베이스와 SQL Server 미러링에 사용 하는 데이터베이스가 포함 됩니다.

  - Microsoft Exchange 통합으로 전환 하 여 보관 데이터 및 파일을 Exchange 2013 서버에 저장 합니다. 모든 사용자가 Exchange 2013 서버에 있고 배포의 모든 사용자에 대해 Microsoft Exchange 저장소를 사용 하려는 경우에는 토폴로지에서 SQL Server 저장소 데이터베이스를 제거 해야 합니다.

이러한 변경 작업을 수행 하려면 토폴로지 작성기를 실행 하 고 필요한 사항을 변경한 다음 토폴로지를 다시 게시 해야 합니다. 토폴로지 작성기를 사용 하 여이 작업을 수행할 수 있습니다. Exchange 2013 서버에 있지 않은 Lync 사용자가 없는 경우에는 **Sql server 저장소 보관** 을 지정 하거나 **sql server 저장소 미러링 정보를 사용 하도록 설정** 하지 마십시오.

<div>

## <a name="to-change-your-archiving-database-option"></a>보관 데이터베이스 옵션을 변경하려면

1.  Lync Server 2013을 실행 중이거나 Lync Server 관리 도구가 설치 된 컴퓨터에서 로컬 사용자 그룹의 구성원 인 계정 또는 이와 동등한 사용자 권한을 가진 계정을 사용 하 여 로그온 합니다.
    
    <div>
    

    > [!NOTE]  
    > 로컬 Users 그룹의 구성원 인 계정을 사용 하 여 토폴로지를 정의할 수 있지만 토폴로지에 구성 요소를 추가 하는 데 필요한 토폴로지를 게시 하려면 <STRONG>Domain Admins</STRONG> 그룹 및 <STRONG>RTCUniversalServerAdmins</STRONG> 그룹의 구성원 인 계정을 사용 해야 합니다. 여기에는 Lync Server 2013 파일 저장소에 사용 하는 파일 공유에 대 한 모든 권한 (읽기, 쓰기 및 수정)이 있으며, 토폴로지 작성기가 필요한 dacl (임의 액세스 제어 목록)을 구성할 수 있도록 하는 것이 좋습니다.

    
    </div>

2.  토폴로지 작성기를 시작합니다.

3.  콘솔 트리에서 보관을 배포한 프런트 엔드 풀로 이동한 다음 데이터베이스 옵션을 변경할 프런트 엔드 풀의 이름을 클릭합니다.

4.  **동작** 메뉴에서 **속성 편집**을 클릭합니다.

5.  **속성 편집** 대화 상자에서 **일반**을 클릭합니다.

6.  아래쪽의 **보관**으로 스크롤합니다.

7.  **보관**에서 다음을 수행합니다.
    
      - 다른 기존 SQL Server 저장소로 변경하려면 **보관 SQL Server 저장소** 아래 드롭다운 목록 상자에서 다음을 수행합니다.
        
          - 기존 SQL Server 저장소를 사용하려면 드롭다운 목록 상자에서 사용할 SQL Server 저장소의 이름을 클릭합니다.
        
          - 새 SQL Server 저장소를 지정하려면 **새로 만들기**를 클릭하고 ** 새 SQL Server 저장소 정의** 대화 상자에서 다음을 수행합니다.
            
              - 기존 SQL Server 저장소를 사용하려면 드롭다운 목록 상자에서 사용할 SQL Server 저장소의 이름을 클릭합니다.
            
              - 새 SQL Server 저장소를 지정 하려면 **새로 만들기**를 클릭 하 고 **새 Sql server 저장소 정의** 대화 상자에서 다음을 수행 합니다.
                
                  - **Sql SERVER fqdn**에서 새 SQL Server 저장소를 만들 서버의 FQDN을 지정 합니다.
                
                  - **기본 인스턴스**를 클릭하여 기본 인스턴스를 사용하거나, 다른 인스턴스를 지정하려면 **명명된 인스턴스**를 클릭하고 사용할 인스턴스를 지정합니다.
                
                  - 지정 된 SQL Server 인스턴스가 미러링 관계에 있는 경우 **이 SQL 인스턴스가 미러링 관계에** 있습니다. 확인란을 선택한 다음 **미러 포트 번호**에 포트 번호를 지정 합니다.
    
      - 미러링용으로 SQL Server 저장소를 추가하거나 SQL Server 저장소 미러링을 위해 다른 기존 SQL Server 저장소로 변경하려면 **SQL Server 저장소 미러링 사용**을 선택하고 다음을 수행합니다.
        
          - 미러링에 대해 기존 SQL Server 저장소를 사용 하려면 **보관 SQL server 저장소 미러** 드롭다운 목록 상자에서 미러링에 사용할 sql Server 저장소의 이름을 클릭 합니다.
        
          - 미러링 용으로 새 SQL Server 저장소를 지정 하려면 **새로 만들기**를 클릭 하 고 **새 SQL server 저장소 정의** 대화 상자에서 다음 중 하나를 수행 합니다.
            
            1.  **Sql SERVER fqdn**에서 새 sql server 저장소를 만들 sql SERVER의 FQDN을 지정 합니다.
            
            2.  **기본 인스턴스**를 클릭하여 기본 인스턴스를 사용하거나, 다른 인스턴스를 지정하려면 **명명된 인스턴스**를 클릭하고 사용할 인스턴스를 지정합니다.
            
            3.  지정 된 SQL Server 인스턴스가 미러링 관계에 있는 경우 **이 SQL 인스턴스가 미러링 관계에** 있습니다. 확인란을 선택한 다음 **미러 포트 번호**에 포트 번호를 지정 합니다.
        
          - SQL Server 미러링을 사용 하도록 설정 하 고 SQL Server 미러링 모니터 서버를 추가 또는 변경 하려는 경우 (기본 SQL Server server 및 미러 인스턴스의 상태를 검색할 수 있는 세 번째 별도의 SQL Server 인스턴스), **Sql server 미러링 모니터 서버가 자동 장애 조치 (failover** )를 사용 하도록 설정 확인란을 선택 하 고 다음 중 하나를 수행 합니다.
            
            1.  **Sql SERVER fqdn**에서 새 SQL Server 미러링 모니터 서버를 만들 서버의 FQDN을 지정 합니다.
            
            2.  **기본 인스턴스**를 클릭하여 기본 인스턴스를 사용하거나, 다른 인스턴스를 지정하려면 **명명된 인스턴스**를 클릭하고 미러링 모니터 서버에 사용할 인스턴스를 지정합니다.
            
            3.  지정 된 SQL Server 인스턴스가 미러링 관계에 있는 경우 **이 SQL 인스턴스가 미러링 관계에** 있습니다. 확인란을 선택한 다음 **미러 포트 번호**에 포트 번호를 지정 합니다.
    
      - Exchange 2013 서버에 보관 데이터 및 파일을 저장 하는 Microsoft Exchange 통합으로 전환 하려면 (배포의 모든 사용자가 Exchange 2013 서버에 있는 경우) 보관 데이터베이스에 대 한 모든 정보를 삭제 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > Exchange 2013 서버에 있지 않은 Lync 사용자가 있는 경우 SQL Server 저장소 정보를 삭제 하지 마십시오.

    
    </div>

8.  구성을 저장하려면 **확인**을 클릭합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 토폴로지 작성기에서 변경한 내용은 새 토폴로지를 게시할 때까지 적용 되지 않습니다. 자세한 내용은 배포 설명서의 <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">업데이트 된 토폴로지 게시를 참조 하 여 Lync Server 2013에서 보관 데이터베이스를 추가</A> 합니다.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

