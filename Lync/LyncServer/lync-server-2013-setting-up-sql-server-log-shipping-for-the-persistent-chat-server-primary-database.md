---
title: 'Lync Server 2013: 영구 채팅 서버 기본 데이터베이스에 대해 SQL Server 로그 전달 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up SQL Server Log Shipping for the Persistent Chat Server primary database
ms:assetid: 088ea1c2-d592-4a11-b3b8-f1e2f8beae93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204653(v=OCS.15)
ms:contentKeyID: 48183337
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0de2285d77ba2228b90d244c841efc0b986bf454
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-sql-server-log-shipping-in-lync-server-2013-for-the-persistent-chat-server-primary-database"></a>영구 채팅 서버 기본 데이터베이스에 대해 Lync Server 2013의 SQL Server 로그 전달 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-12_

SQL Server Management Studio를 사용 하 여 영구 채팅 서버 보조 로그 전달 데이터베이스 인스턴스에 연결 하 고 SQL Server 에이전트가 실행 중인지 확인 합니다.

영구 채팅 기본 데이터베이스 인스턴스에 연결 된 SQL Server Management Studio를 사용 하 여 다음 단계를 수행 합니다.

1.  SQL Server 에이전트가 실행 중인지 확인 합니다.

2.  Mgc 데이터베이스를 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.

3.  **페이지 선택**에서 **트랜잭션 로그 전달을**클릭 합니다.

4.  **로그 전달 구성의 기본 데이터베이스로 사용할 수 있도록이** 확인란을 선택 합니다.

5.  **트랜잭션 로그 백업**에서 **백업 설정을**클릭 합니다.

6.  **백업 폴더에 대 한 네트워크 경로** 상자에 트랜잭션 로그 백업 폴더에 대해 만든 공유의 네트워크 경로를 입력 합니다.

7.  백업 폴더가 주 서버에 있는 경우 백업 폴더의 백업 폴더에 대 한 로컬 경로를 **주 서버에 입력 하 고 폴더에 대 한 로컬 경로 (예: c:\\백업)** 상자를 입력 합니다. (백업 폴더가 주 서버에 없는 경우에는이 상자를 비워 둘 수 있습니다.)
    
    <div>
    

    > [!IMPORTANT]  
    > 주 서버의 SQL Server 서비스 계정이 로컬 시스템 계정에서 실행 되는 경우 주 서버에서 백업 폴더를 만들고 해당 폴더에 대 한 로컬 경로를 지정 해야 합니다.

    
    </div>

8.  **보다 오래 된 파일 삭제** 및 매개 변수 **내에서 백업이 수행 되지 않는 경우 경고** 를 구성 합니다.

9.  **백업 작업**아래의 **일정** 상자에 나열 된 백업 일정을 확인 합니다. 설치 일정을 사용자 지정 하려면 **일정**을 클릭 하 고 필요에 따라 SQL Server 에이전트 일정을 조정 합니다.

10. **압축**에서 **기본 서버 설정 사용**을 선택 하 고 **확인**을 클릭 합니다.

11. **보조 서버 인스턴스 및 데이터베이스**에서 **추가**를 클릭 합니다.

12. **연결** 을 클릭 하 고 보조 서버로 구성한 SQL Server 인스턴스에 연결 합니다.

13. **보조 데이터베이스** 상자에서 목록에 있는 **mgc** 데이터베이스를 선택 합니다.

14. **보조 데이터베이스 초기화** 탭에서 **예, 기본 데이터베이스의 전체 백업을 생성 하 고 보조 데이터베이스에 복원 합니다 (없는 경우 보조 데이터베이스 만들기)**.

15. **파일 복사** 탭의 **복사 된 파일의 대상 폴더** 상자에 트랜잭션 로그 백업을 복사 해야 하는 폴더의 경로를 입력 합니다. 이 폴더는 주로 보조 서버에 있습니다.

16. **작업 복사**아래에 있는 **일정** 상자에 나열 된 복사 일정을 확인 합니다. 설치 일정을 사용자 지정 하려면 **일정**을 클릭 하 고 필요에 따라 SQL Server 에이전트 일정을 조정 합니다. 이 일정은 거의 백업 일정과 동일 해야 합니다.

17. **복원** 탭의 **데이터베이스 상태에서 백업을 복원할 때** **복구 안 됨 모드** 옵션을 선택 합니다.

18. **최소 백업 복구 지연**에서 **0 분**을 선택 합니다.

19. **내에 복원이 발생 하지 않는 경우 알림**아래에서 경고 임계값을 선택 합니다.

20. **복원 작업**아래에 있는 **일정** 상자에 나열 된 복원 일정을 확인 합니다. 설치 일정을 사용자 지정 하려면 **일정**을 클릭 하 고 필요에 따라 SQL Server 에이전트 일정을 조정 하 고 **확인**을 클릭 합니다. 이 일정은 거의 백업 일정과 동일 해야 합니다.

21. **데이터베이스 속성** 대화 상자에서 **확인** 을 클릭 하 여 구성 프로세스를 시작 합니다.

</div>

<span> </span>

</div>

</div>

</div>

