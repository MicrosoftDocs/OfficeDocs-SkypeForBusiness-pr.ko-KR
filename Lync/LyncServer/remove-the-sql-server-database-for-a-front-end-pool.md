---
title: 프런트 엔드 풀에 대 한 SQL Server 데이터베이스 제거
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for a Front End pool
ms:assetid: 6bb932df-3ed7-49b6-ae17-61e4c6a5fe82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688084(v=OCS.15)
ms:contentKeyID: 49733681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65c192bbc800c7b122911950e59439c43d8b0480
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>프런트 엔드 풀에 대 한 SQL Server 데이터베이스 제거

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-04_

Microsoft Lync Server 2010 프런트 엔드 풀을 제거 하거나 다른 데이터베이스를 사용 하도록 풀을 다시 구성한 후에는 해당 풀 데이터를 호스팅한 SQL Server 데이터베이스를 제거할 수 있습니다. 다음 절차에 따라 토폴로지 작성기에서 정의를 제거 하 고 데이터베이스 서버에서 데이터베이스 및 로그 파일을 제거 합니다.

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>토폴로지 작성기를 사용 하 여 SQL Server 데이터베이스를 제거 하려면

1.  Lync Server 2013 프런트 엔드 서버에서 토폴로지 작성기를 열고 기존 토폴로지를 다운로드 합니다.

2.  토폴로지 작성기에서 **공유 구성 요소** 를 탐색 한 다음 **sql server 저장소**로 이동한 후 제거 되거나 다시 구성 된 프런트 엔드 풀과 연결 된 SQL Server 인스턴스를 마우스 오른쪽 단추로 클릭 한 다음 **삭제**를 클릭 합니다.

3.  토폴로지를 게시 한 후 복제 상태를 확인 합니다.

</div>

<div>

## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>SQL Server에서 사용자 및 응용 프로그램 데이터베이스를 제거 하려면

1.  SQL Server에서 데이터베이스를 제거하려면 사용자가 데이터베이스 파일을 제거하려는 SQL Server에 대해 SQL Server sysadmins 그룹의 구성원이어야 합니다.

2.  Lync Server 관리 셸 열기

3.  풀 사용자 저장소에 대 한 데이터베이스를 제거 하려면 다음을 입력 합니다.
    
        Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    여기서 \<fqdn\> 은 데이터베이스 서버의 fqdn (정규화 된 도메인 이름)이 고 \<인스턴스\> 는 명명 된 데이터베이스 인스턴스이며 (즉, 정의 된 경우).

4.  풀 응용 프로그램 저장소에 대 한 데이터베이스를 제거 하려면 다음을 입력 합니다.
    
        Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    여기서 \<fqdn\> 은 데이터베이스 서버의 FQDN이 고 \<인스턴스\> 는 명명 된 데이터베이스 인스턴스이며 (즉, 정의 된 경우).

5.  **Uninstall-CsDataBase** cmdlet에서 작업을 확인하라는 메시지가 표시되면 해당 정보를 읽고, 계속하려면 **Y**(또는 Enter 키)를 누르고, cmdlet을 중지하려면 **N**을 누른 후 Enter 키를 누릅니다(즉, 오류가 있을 경우에 대비하여).

</div>

</div>

<span> </span>

</div>

</div>

</div>

