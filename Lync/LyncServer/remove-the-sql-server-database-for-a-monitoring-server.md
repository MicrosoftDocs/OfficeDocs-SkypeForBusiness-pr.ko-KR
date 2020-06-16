---
title: 모니터링 서버용 SQL Server 데이터베이스 제거
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for a Monitoring server
ms:assetid: aed5e394-d63e-4ad4-af40-f12d3a044344
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721848(v=OCS.15)
ms:contentKeyID: 49733781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5f899fd36a985c124d5b0bfca899592eb9b7a17
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757270"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>모니터링 서버용 SQL Server 데이터베이스 제거

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-04_

Microsoft Lync Server 2010 모니터링 서버를 제거한 후에는 서버 데이터를 호스트 하는 SQL Server 데이터베이스를 제거할 수 있습니다. 다음 절차에 따라 토폴로지 작성기에서 정의를 제거 하 고 데이터베이스 서버에서 데이터베이스 및 로그 파일을 제거 합니다.

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>토폴로지 작성기를 사용 하 여 SQL Server 데이터베이스를 제거 하려면

1.  Lync Server 2013 프런트 엔드 서버에서 토폴로지 작성기를 엽니다.

2.  토폴로지 작성기에서 **공유 구성 요소** 를 탐색 하 고 **SQL server 저장소**로 이동한 다음, 제거 되거나 다시 구성 된 모니터링 서버에 연결 된 SQL Server 인스턴스를 마우스 오른쪽 단추로 클릭 한 다음 **삭제**를 클릭 합니다.

3.  토폴로지를 게시한 후 복제 상태를 확인합니다.

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a>SQL Server에서 데이터베이스 파일을 제거하려면

1.  SQL Server 기반 서버에서 데이터베이스를 제거 하려면 데이터베이스 파일을 제거 하려는 SQL Server 서버에 대해 SQL Server sysadmins 그룹의 구성원 이어야 합니다.

2.  Lync Server 관리 셸을 엽니다.

3.  명령줄에 다음을 입력합니다.
    
        Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    여기서 \<FQDN\> 은 데이터베이스 서버의 FQDN (정규화 된 도메인 이름) 이며, \<instance\> 선택적 명명 된 데이터베이스 인스턴스입니다.

4.  **Uninstall-CsDataBase** cmdlet에서 작업을 확인하라는 메시지가 표시되면 해당 정보를 읽고, 계속하려면 **Y**(또는 Enter 키)를 누르고, cmdlet을 중지하려면 **N**을 누른 후 Enter 키를 누릅니다(즉, 오류가 있을 경우에 대비하여).

</div>

</div>

<span> </span>

</div>

</div>

</div>

