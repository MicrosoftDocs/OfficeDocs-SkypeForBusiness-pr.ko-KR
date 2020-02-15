---
title: 'Lync Server 2013: 토폴로지 게시'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the topology
ms:assetid: 3b5a744b-b3a8-4538-a55e-e2e4f72dff47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425880(v=OCS.15)
ms:contentKeyID: 48183866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1aa216ba3db48f03dbcdd69f4deea029e7a366df
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-topology-in-lync-server-2013"></a>Lync Server 2013에서 토폴로지 게시

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-10-01_

서버 역할을 추가하거나 제거할 때 토폴로지를 성공적으로 게시하거나 사용 또는 사용하지 않도록 설정하려면 RTCUniversalServerAdmins 및 Domain Admins 그룹 구성원인 사용자로 로그인해야 합니다. 또한 적절한 관리자 권한을 위임할 수도 있습니다. 자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하십시오. 그 밖의 구성 변경은 RTCUniversalServerAdmins 그룹의 구성원이면 됩니다.

토폴로지 작성기에서 토폴로지를 정의한 후에는 토폴로지를 중앙 관리 저장소에 게시 해야 합니다. 중앙 관리 저장소는 Lync Server 2013 배포를 정의, 설정, 유지 관리, 관리, 설명 및 운영 하는 데 필요한 데이터에 대 한 강력 하 고 schematized 저장소를 제공 합니다. 또한 구성 일관성을 유지 하기 위해 데이터의 유효성을 검사 합니다. 이 구성 데이터에 대 한 모든 변경 내용은 중앙 관리 저장소에서 수행 되며 "비동기화" 문제를 제거 합니다. 데이터의 읽기 전용 복사본이 에지 서버를 포함한 토폴로지의 모든 서버로 복제됩니다.

<div>


> [!NOTE]  
> 초기 토폴로지를 성공적으로 게시 하 고 중앙 관리 서버를 만들려면 SQL Server에 최소 20gb의 사용 가능한 디스크 공간이 필요 합니다.



</div>

<div>


> [!NOTE]  
> Enterprise Edition에만 해당: 토폴로지를 게시하려면 SQL Server 기반 백 엔드 서버가 온라인이며 방화벽 예외가 지정된 상태에서 액세스 가능한 상태여야 합니다. 방화벽 예외 지정에 대 한 자세한 내용은 <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Lync server 2013을 사용 하 여 SQL Server에 대 한 방화벽 요구 사항 이해</A>를 참조 하십시오. SQL Server 구성에 대 한 자세한 내용은 <A href="lync-server-2013-configure-sql-server-for-lync-server.md">CONFIGURE Sql Server For Lync server 2013</A>을 참조 하십시오.



</div>

<div>

## <a name="to-publish-a-topology"></a>토폴로지를 게시하려면

1.  토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.

2.  로컬 파일에서 토폴로지를 선택하여 엽니다. 토폴로지를 정의한 컴퓨터의 경우 이 위치는 이전 단계에서 토폴로지를 저장한 위치입니다. 일반적으로 이 위치는 토폴로지를 구성한 사용자의 Documents 폴더입니다.

3.  **Lync Server 2013** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **토폴로지 게시**를 클릭 합니다.

4.  **토폴로지 게시** 페이지에서 **다음**을 클릭합니다.

5.  **데이터베이스 만들기** 페이지에서 게시할 데이터베이스를 선택합니다.
    
    <div>
    

    > [!NOTE]  
    > 데이터베이스를 만들 수 있는 적절 한 권한이 없는 경우 해당 데이터베이스 옆의 확인란을 선택 취소할 수 있으며 해당 권한을 가진 사용자는 나중에 데이터베이스를 만들 수 있습니다. 자세한 내용은 <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013의 SQL Server에 대 한 배포 권한을</A>참조 하십시오.

    
    </div>

6.  원하는 경우 **고급**을 클릭합니다. 고급 SQL Server 데이터 파일 배치 옵션을 사용 하 여 다음 옵션 중 하나를 선택할 수 있습니다.
    
      - **데이터베이스 파일 위치 자동 지정** – 이 옵션은 가장 적절한 위치로 로그 및 데이터 파일을 분산시켜 SQL Server 기반 서버에서 디스크 구성을 기반으로 최적의 작동 성능을 결정합니다.
    
      - **SQL Server 인스턴스 기본값 사용** – 이 옵션은 인스턴스 설정을 사용하여 SQL Server 기반 서버에 로그 및 데이터 파일을 저장합니다. 이 옵션은 SQL Server 기반 서버 작동 기능을 사용하여 로그 및 데이터의 최적 위치를 결정하지 않습니다. SQL Server 관리자는 일반적으로 SQL Server 기반 서버 및 조직 관리 절차에 적합한 위치로 로그 및 데이터 파일을 이동합니다.
    
    **확인**을 클릭하고 **다음**을 클릭합니다.

7.  **중앙 관리 서버 선택** 페이지에서 프런트 엔드 풀을 선택 합니다.

8.  원하는 경우 **고급**을 클릭합니다. 고급 SQL Server 데이터 파일 배치 옵션을 사용 하 여 다음 옵션 중 하나를 선택할 수 있습니다.
    
      - **데이터베이스 파일 위치 자동 지정** – 이 옵션은 가장 적절한 위치로 로그 및 데이터 파일을 분산시켜 SQL Server 기반 서버에서 디스크 구성을 기반으로 최적의 작동 성능을 결정합니다.
    
      - **SQL Server 인스턴스 기본값 사용** – 이 옵션은 인스턴스 설정을 사용하여 SQL Server 기반 서버에 로그 및 데이터 파일을 저장합니다. 이 옵션은 SQL Server 기반 서버 작동 기능을 사용하여 로그 및 데이터의 최적 위치를 결정하지 않습니다. SQL Server 관리자는 일반적으로 SQL Server 기반 서버 및 조직 관리 절차에 적합한 위치로 로그 및 데이터 파일을 이동합니다.
    
    **확인**을 클릭합니다.

9.  **다음**을 클릭하여 게시 프로세스를 완료합니다.

10. 게시 프로세스를 완료했으면 **마침**을 클릭합니다.
    
    토폴로지가 성공적으로 게시 되 면 토폴로지에서 Lync Server 2013을 실행 하는 각 서버에 중앙 관리 저장소의 로컬 복제본을 설치 하기 시작할 수 있습니다. 첫 번째 프런트 엔드 풀로 시작 하는 것이 좋습니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에 대 한 프런트 엔드 서버 및 프런트 엔드 풀 설정](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

