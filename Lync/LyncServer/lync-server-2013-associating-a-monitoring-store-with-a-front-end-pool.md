---
title: 'Lync Server 2013: 모니터링 저장소를 프런트 엔드 풀과 연결'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associating a monitoring store with a Front End pool
ms:assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205271(v=OCS.15)
ms:contentKeyID: 48185439
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1228f3108b00a6af1d53b08c67f1fa723fcde8b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044770"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associating-a-monitoring-store-with-a-front-end-pool-in-lync-server-2013"></a>Lync Server 2013에서 모니터링 저장소를 프런트 엔드 풀과 연결

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-04-22_

Microsoft Lync Server 2013 모니터링 데이터는 모니터링 저장소와 연결 된 프런트 엔드 풀 에서만 수집할 수 있으며, 일반적으로 토폴로지 작성기에 프런트 엔드 풀을 정의 하는 작업이 수행 됩니다. 모니터링 저장소를 새 프런트 엔드 풀에 연결 하려면 새 프런트 엔드 풀 정의 마법사의 **기능 선택** 페이지에서 **모니터링 (통화 정보 기록 및 경험 메트릭의 품질 메트릭)** 옵션을 선택 해야 합니다. 이 옵션을 선택 하는 경우에는 마법사를 완료 하기 위해 SQL 저장소도 지정 해야 합니다. 그러나이 저장소는 마법사를 실행할 때 존재 하지 않아도 됩니다. 즉, 먼저 풀을 모니터링 저장소에 연결한 후 나중에 설치 하 고 해당 저장소를 구성할 수 있습니다.

또는 다음 절차를 완료 하 여 기존 프런트 엔드 풀을 새 모니터링 저장소나 다른 monitoring store에 연결할 수 있습니다.

1.  **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.

2.  **토폴로지 작성기** 대화 상자에서 **기존 배포에서 토폴로지 다운로드**를 선택한 후 **확인**을 클릭합니다.

3.  **다른 이름으로 저장** 대화 상자에서 현재 토폴로지의 파일 이름을 입력 한 다음 **저장**을 클릭 합니다. 새 토폴로지에 문제가 있는 경우 저장 된 토폴로지를 나중에 검색 하 고 다시 게시할 수 있습니다.

4.  토폴로지 작성기에서 **Lync Server 2013**을 확장 하 고 프런트 엔드 풀이 포함 된 사이트의 이름을 확장 한 후 **Enterprise Edition 프런트 엔드 풀**을 클릭 합니다.

5.  모니터링 저장소와 연결할 풀의 이름을 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 클릭 합니다.

6.  **속성 편집** 대화 상자의 **일반** 탭에서 **모니터링 (CDR 및 QoE 메트릭)** 옵션을 선택한 다음 **모니터링 SQL Server 저장소** 드롭다운 목록에서 기존 SQL server 데이터베이스를 선택 합니다. 또는 **새로 만들기** 를 클릭 하 여 풀을 새 데이터베이스 저장소에 연결 합니다. 새 데이터베이스 저장소를 사용 하도록 선택한 경우 **새 Sql 저장소 정의** 대화 상자에서 SQL server **FQDN** 상자에 sql server 컴퓨터의 정규화 된 도메인 이름을 입력 합니다. 해당 저장소에 대 한 기본 SQL Server 인스턴스를 사용 하려는 경우 **기본 인스턴스**를 선택 합니다. 그렇지 않으면 **명명 된 인스턴스** 를 선택 하 고 명명 된 **인스턴스** 상자에 인스턴스 이름을 입력 합니다.
    
    **속성 편집** 대화 상자에는 모니터링 데이터베이스에 대 한 sql 미러를 만들 수 있는 옵션이 제공 됩니다 (sql 미러를 통해 모니터링 데이터베이스의 복사본을 두 개, 모니터링 저장소 컴퓨터에 저장 한 복사본, SQL 미러 컴퓨터에 저장할 수도 있습니다.) 미러링을 사용 하도록 설정 하려면**SQL 인스턴스가 미러링 관계에 있는 것** 을 선택 하 고 **미러링 포트 번호** 상자에 미러 서버의 포트 번호를 입력 합니다.

7.  **속성 편집** 대화 상자에서 **확인**을 클릭 합니다.

모니터링 저장소를 프런트 엔드 풀과 연결한 후에는 변경 내용을 적용 하기 전에 새 토폴로지를 게시 해야 합니다. 새 토폴로지를 게시 하려면 토폴로지 작성기에서 다음 단계를 완료 합니다.

1.  **동작**을 클릭 하 고 **토폴로지**를 가리킨 다음 **게시**를 클릭 합니다.

2.  토폴로지 게시 마법사의 **토폴로지 게시** 페이지에서 **다음**을 클릭 합니다.

3.  **게시 마법사 완료** 페이지에서 **마침**을 클릭합니다.

토폴로지를 게시 한 후에는 모니터링 저장소를 호스팅할 컴퓨터에 모니터링 데이터베이스를 설치할 수 있습니다. Lync Server 관리 셸 및 Windows PowerShell을 사용 하 여 모니터링 데이터베이스를 설치할 수 있습니다. 데이터베이스를 로컬로 설치 하려면 (즉, Lync Server 관리 셸을 실행 하는 동일한 컴퓨터에 데이터베이스를 설치 하려면) 해당 컴퓨터에서 관리 셸을 시작한 후 다음 명령을 입력 하 고 enter 키를 누릅니다.

    Install-CsDatabase -LocalDatabases

위의 명령을 실행 하면 CsDatabase p r a r a r i a r a r i r a r a r a r a r a r a r a r a r a r a r a r a r a r a r a r a r a r a r

원격 컴퓨터 (관리 셸이 실행 되는 컴퓨터가 아닌 컴퓨터)에 데이터베이스를 설치 하려면 최소 두 개의 매개 변수, 즉 ConfiguredDatabases 매개 변수와 변수와 sqlserverfqdn 매개 변수를 포함 해야 합니다. 이 매개 변수는 CsDatabase cmdlet에 Lync Server 토폴로지를 검색 한 다음 변수와 sqlserverfqdn 매개 변수로 지정 된 컴퓨터에서 필요한 데이터베이스를 설치 및 구성 하도록 지시 합니다. 변수와 sqlserverfqdn 매개 변수는 데이터베이스를 설치할 컴퓨터의 정규화 된 도메인 이름을 나타내는 매개 변수 값을 사용 해야 합니다.

예를 들어 다음 명령은 atl-sql-001.litwareinc.com 컴퓨터에 모니터링 데이터베이스를 설치 합니다.

    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com

또는 모니터링 저장소를 호스트 하는 컴퓨터에서 Lync Server 배포 마법사를 실행 하 여 모니터링 데이터베이스를 설치할 수도 있습니다. 이렇게 하려면 적절 한 컴퓨터에 로그온 하 고 다음 절차를 완료 합니다.

1.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013**, **Lync server 배포 마법사**를 차례로 클릭 합니다.

2.  배포 마법사에서 **Lync Server 시스템 설치 또는 업데이트**를 클릭합니다.

3.  **배포** 페이지의 **2 단계: Lync Server 구성 요소 설치 또는 제거**에서 **다시 실행**을 클릭 합니다.

4.  Lync Server 구성 요소 설치 마법사의 **Lync server 구성 요소 설치** 페이지에서 **다음**을 클릭 합니다.

5.  **Msi에 대 한 경로 지정** 페이지에서 ocscore 파일 (Lync Server 설치 미디어에 포함 된 파일)의 경로를 입력 하 고 **다음**을 클릭 합니다.

6.  **명령 실행** 페이지에서 **마침**을 클릭합니다.

필요한 모든 Lync Server 서비스가 시작 되었는지 확인 하려면 제목 **4 단계:** **배포** 페이지에서 서비스 시작 **을 클릭 합니다** .

</div>

<span> </span>

</div>

</div>

</div>

