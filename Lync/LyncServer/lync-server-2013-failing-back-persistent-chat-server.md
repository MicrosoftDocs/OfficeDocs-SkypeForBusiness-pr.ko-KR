---
title: 'Lync Server 2013: 영구 채팅 서버 장애 복구(failback)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing back Persistent Chat Server
ms:assetid: 67b91de4-6ddc-43e6-9812-5e1aa84a7980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204970(v=OCS.15)
ms:contentKeyID: 48184396
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d79c25d153de81906fcaf9355a543d31cb8fe0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984119"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013에서 영구 채팅 서버 장애 복구(failback)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-02-05_

이 절차에서는 영구 채팅 서버 오류에서 복구 하 고 기본 데이터 센터에서 작업을 다시 설정 하는 데 필요한 단계에 대해 설명 합니다.

영구 채팅 서버 장애가 발생 한 경우 기본 데이터 센터에서 중단 되 고 기본 및 미러 데이터베이스를 사용할 수 없게 됩니다. 주 데이터 센터가 백업 서버로 장애 조치 됩니다.

다음 절차는 기본 데이터 센터를 백업한 후에 정상 작업을 복원 하 고 서버를 다시 작성 했습니다. 이 절차에서는 기본 데이터 센터가 총 중단 으로부터 복구 되었고, mgc 데이터베이스와 mgccomp 데이터베이스가 토폴로지 작성기를 사용 하 여 다시 작성 되 고 다시 설치 되었다고 가정 합니다.

또한이 절차에서는 장애 조치 기간 동안 새 미러 및 백업 서버가 배포 되지 않은 것으로 가정 하 고, [Lync server 2013의 영구 채팅 서버 장애](lync-server-2013-failing-over-persistent-chat-server.md)조치에 정의 된 대로 백업 서버와 미러 서버만 배포 됩니다.

이러한 단계는 재해가 발생 하기 이전에 구성을 복구 하도록 설계 되었으며, 결과적으로 주 서버에서 백업 서버로 장애 조치를 수행 합니다.

<div>

## <a name="to-fail-back-persistent-chat-server"></a>영구 채팅 서버에 장애 복구

1.  Lync Server 관리 셸에서 cmdlet을 `Set-CsPersistentChatActiveServer` 사용 하 여 영구 채팅 서버 활성 서버 목록에서 모든 서버를 지웁니다. 이렇게 하면 장애 복구 하는 동안 mgc 데이터베이스 및 mgccomp 데이터베이스에 연결 하는 모든 영구 채팅 서버가 중지 됩니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 보조 영구 채팅 서버 백 엔드 서버의 SQL Server 에이전트는 특권 계정으로 실행 되어야 합니다. 특히, 계정에는 다음이 포함 되어야 합니다. 
    > <UL>
    > <LI>
    > <P>백업이 저장 되는 네트워크 공유에 대 한 읽기 액세스입니다.</P>
    > <LI>
    > <P>백업을 복사할 특정 로컬 디렉터리에 대 한 쓰기 액세스입니다.</P></LI></UL>

    
    </div>

2.  Backup mgc 데이터베이스에서 미러링을 사용 하지 않도록 설정 합니다.
    
    1.  SQL Server Management Studio를 사용 하 여 backup mgc 인스턴스에 연결 합니다.
    
    2.  Mgc 데이터베이스를 마우스 오른쪽 단추로 클릭 하 고 **작업**을 가리킨 다음 **미러**를 클릭 합니다.
    
    3.  **미러링 제거**를 클릭 합니다.
    
    4.  **확인**을 클릭합니다.
    
    5.  Mgccomp 데이터베이스에 대해 동일한 단계를 수행 합니다.

3.  새 기본 데이터베이스로 복원할 수 있도록 mgc 데이터베이스를 백업 합니다.
    
    1.  SQL Server Management Studio를 사용 하 여 backup mgc 인스턴스에 연결 합니다.
    
    2.  Mgc 데이터베이스를 마우스 오른쪽 단추로 클릭 하 고 **작업**을 가리킨 다음 **백업을**클릭 합니다. **데이터베이스 백업** 대화 상자가 나타납니다.
    
    3.  **백업 유형에**서 Full ( **전체**)을 선택 합니다.
    
    4.  **백업 구성 요소**를 보려면 **데이터베이스**를 클릭 합니다.
    
    5.  **이름**에 제시 된 기본 백업 집합 이름을 그대로 사용 하거나 백업 집합에 다른 이름을 입력 합니다.
    
    6.  * \<선택\> 사항* **설명**에 백업 집합에 대 한 설명을 입력 합니다.
    
    7.  대상 목록에서 기본 백업 위치를 제거 합니다.
    
    8.  로그 전달을 위해 설정한 공유 위치의 경로를 사용 하 여 목록에 파일을 추가 합니다. 이 경로는 기본 데이터베이스와 백업 데이터베이스에서 사용할 수 있습니다.
    
    9.  **확인** 을 클릭 하 여 대화 상자를 닫고 백업 프로세스를 시작 합니다.

4.  이전 단계에서 만든 백업 데이터베이스를 사용 하 여 기본 데이터베이스를 복원 합니다.
    
    1.  SQL Server Management Studio를 사용 하 여 기본 mgc 인스턴스에 연결 합니다.
    
    2.  Mgc 데이터베이스를 마우스 오른쪽 단추로 클릭 하 고 **작업**, **복원을**차례로 가리킨 다음 **데이터베이스**를 클릭 합니다. **데이터베이스 복원** 대화 상자가 나타납니다.
    
    3.  **장치에서를**선택 합니다.
    
    4.  찾아보기 단추를 클릭 하 여 **백업 지정** 대화 상자를 엽니다. **백업 미디어**에서 **파일**을 선택 합니다. **추가**를 클릭 하 고 3 단계에서 만든 백업 파일을 선택한 다음 **확인**을 클릭 합니다.
    
    5.  **복원할 백업 세트 선택**에서 백업을 선택 합니다.
    
    6.  **페이지 선택** 창에서 **옵션** 을 클릭 합니다.
    
    7.  **복원 옵션**에서 **기존 데이터베이스 덮어쓰기를**선택 합니다.
    
    8.  **복구 상태**에서 **데이터베이스를 사용할 준비가 된 상태로 둡니다**.를 선택 합니다.
    
    9.  **확인** 을 클릭 하 여 복원 프로세스를 시작 합니다.

5.  기본 데이터베이스에 대 한 SQL Server 로그 전달을 구성 합니다. [Lync server 2013의 고가용성 및 재해 복구용으로 영구 채팅 서버 구성](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) 의 절차에 따라 기본 mgc 데이터베이스에 대 한 로그 전달을 설정 합니다.

6.  영구 채팅 서버 활성 서버를 설정 합니다. Lync Server 관리 셸에서 **CsPersistentChatActiveServer** cmdlet을 사용 하 여 활성 서버 목록을 설정 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 모든 활성 서버는 새 기본 데이터베이스와 동일한 데이터 센터 내에 있거나 데이터베이스에 대 한 대기/고속 대역폭 연결이 낮은 데이터 센터에 있어야 합니다.

    
    </div>

풀을 정상 상태로 복원 다음 Windows PowerShell 명령을 실행 합니다.

    Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal

자세한 내용은 [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) cmdlet에 대 한 도움말 항목을 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

