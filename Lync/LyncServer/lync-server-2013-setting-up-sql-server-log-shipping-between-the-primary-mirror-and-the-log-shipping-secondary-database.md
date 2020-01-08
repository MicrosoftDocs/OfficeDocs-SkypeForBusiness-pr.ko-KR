---
title: 'Lync Server 2013: 기본 미러와 로그 전달 보조 데이터베이스 간의 SQL Server 로그 전달 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database
ms:assetid: 4e8e9ce9-4301-47f2-a0c3-669afeb53295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204887(v=OCS.15)
ms:contentKeyID: 48184119
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3758e654826de42f6bf6bed8ead29ce03adb6ca5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database-in-lync-server-2013"></a>Lync Server 2013에서 기본 미러와 로그 전달 보조 데이터베이스 간의 SQL Server 로그 전달 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-21_

기본 영구 채팅 데이터베이스가 미러 데이터베이스로 장애 조치 되는 경우 계속 하려면 로그 전달을 위해 다음 단계를 수행 합니다.

1.  기본 영구 채팅 데이터베이스를 미러에서 수동으로 장애 조치 합니다. 이 작업은 Lync Server 관리 셸 및 ' **CsDatabaseFailover** cmdlet '을 사용 하 여 수행 됩니다. 자세한 내용은 [lync server 2013에서 백 엔드 서버의 SQL 미러링 배포](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)에서 "Lync Server Management Shell cmdlet 사용"을 참조 하세요.

2.  SQL Server Management Studio를 사용 하 여 기본 영구 채팅 서버 미러 인스턴스에 연결 합니다.

3.  SQL Server 에이전트가 실행 중인지 확인 합니다.

4.  Mgc 데이터베이스를 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.

5.  **페이지 선택**에서 **트랜잭션 로그 전달을**클릭 합니다.

6.  **로그 전달 구성의 기본 데이터베이스로 사용할 수 있도록이** 확인란을 선택 합니다.

7.  **트랜잭션 로그 백업**에서 **백업 설정을**클릭 합니다.

8.  **백업 폴더에 대 한 네트워크 경로** 상자에 트랜잭션 로그 백업 폴더에 대해 만든 공유의 네트워크 경로를 입력 합니다.

9.  백업 폴더가 주 서버에 있는 경우 백업 폴더의 백업 폴더에 대 한 로컬 경로를 **주 서버에 입력 하 고 폴더 상자에 대 한 로컬 경로를 입력** 합니다. (백업 폴더가 주 서버에 없는 경우에는이 상자를 비워 둘 수 있습니다.)
    
    <div>
    

    > [!IMPORTANT]  
    > 주 서버의 SQL Server 서비스 계정이 로컬 시스템 계정에서 실행 되는 경우 주 서버에서 백업 폴더를 만들고 해당 폴더에 대 한 로컬 경로를 지정 해야 합니다.

    
    </div>

10. **보다 오래 된 파일 삭제** 및 매개 변수 **내에서 백업이 수행 되지 않는 경우 경고** 를 구성 합니다.

11. **백업 작업**아래의 **일정** 상자에 나열 된 백업 일정을 확인 합니다. 설치 일정을 사용자 지정 하려면 **예약**을 클릭 하 고 필요에 따라 SQL Server 에이전트 일정을 조정 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 기본 데이터베이스에 사용 했던 것과 동일한 설정을 사용 합니다.

    
    </div>

12. **압축**에서 **기본 서버 설정 사용**을 선택 하 고 **확인**을 클릭 합니다.

13. **보조 서버 인스턴스 및 데이터베이스**에서 **추가**를 클릭 합니다.

14. **연결**을 클릭 하 고 보조 서버로 구성한 SQL Server 인스턴스에 연결 합니다.

15. **보조 데이터베이스** 상자에서 목록에 있는 **mgc** 데이터베이스를 선택 합니다.

16. **보조 데이터베이스 초기화** 탭에서 아니요 옵션을 선택 합니다. **보조 데이터베이스가 초기화**됩니다.

17. **파일 복사** 탭에서 **복사 된 파일의 대상 폴더**에 트랜잭션 로그 백업을 복사 해야 하는 폴더의 경로를 입력 하 고 **확인**을 클릭 합니다. 이 폴더는 주로 보조 서버에 있습니다.

18. **스크립트 구성** 드롭다운 목록을 열고 **구성 스크립트를 새 쿼리 창으로**선택 합니다.

19. 새 쿼리 창의 **데이터베이스 속성**에서 **확인** 을 클릭 하 여 구성 프로세스를 시작 합니다.

20. 쿼리의 첫 번째 절반 (18 단계 참조)을 선택 하 \* \* \* \* \* \* 고 실행 합니다 (--끝: 기본 \* \* \* \* \* \*에서 실행할 스크립트:).
    
    <div>
    

    > [!IMPORTANT]  
    > Sql server Management Studio는 SQL Server 로그 전달 구성에서 여러 개의 기본 데이터베이스를 지원 하지 않으므로이 스크립트를 수동으로 실행 해야 합니다.

    
    </div>

21. ' **취소** '를 선택 하 여 로그 파일 전달 구성 패널을 닫고, 장애 조치 (failover)의 경우 기본 데이터베이스와 미러된 데이터베이스 모두에 대 한 로그 파일 전달을 올바르게 구현 하는 작동 설정을 설정 합니다.

22. 기본 영구 채팅 데이터베이스를 기본으로 다시 장애 복구 합니다. 이 작업은 Lync Server Management Shell을 사용 하 여 수행 하 고 **CsDatabaseFailover** Cmdlet을 호출 합니다. 자세한 내용은 [lync server 2013에서 백 엔드 서버의 SQL 미러링 배포](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)에서 "Lync Server Management Shell cmdlet 사용"을 참조 하세요.

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 백 엔드 서버 고가용성을 위해 SQL 미러링 배포](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
[Lync Server 2013에서 백 엔드 서버 고가용성을 위해 SQL 미러링 배포](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

