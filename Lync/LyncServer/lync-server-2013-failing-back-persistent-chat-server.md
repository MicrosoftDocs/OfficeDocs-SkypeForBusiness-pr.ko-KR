---
title: 'Lync Server 2013: 영구 채팅 서버 장애 복구 (failback)'
description: 'Lync Server 2013: 영구 채팅 서버 장애 복구 (failback)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back Persistent Chat Server
ms:assetid: 67b91de4-6ddc-43e6-9812-5e1aa84a7980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204970(v=OCS.15)
ms:contentKeyID: 48184396
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fa36562b3892c0e22960677ffcba4b862e708c4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567734"
---
# <a name="failing-back-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013에서 영구 채팅 서버 장애 복구 (failback)

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-02-05_

이 절차에서는 영구 채팅 서버 오류에서 복구 하 고 기본 데이터 센터에서 작업을 다시 설정 하는 데 필요한 단계에 대해 설명 합니다.

영구 채팅 서버 오류 시 기본 데이터 센터에서 중단 되 고 기본 및 미러 데이터베이스를 사용할 수 없게 됩니다. 기본 데이터 센터는 백업 서버로 장애 조치(failover)됩니다.

다음 절차에서는 기본 데이터 센터가 백업되고 서버를 다시 구축한 후에 일반 작업을 복원합니다. 이 절차에서는 기본 데이터 센터가 전체 중단 으로부터 복구 되었으며, 토폴로지 작성기를 사용 하 여 mgc 데이터베이스와 mgccomp 데이터베이스를 다시 작성 하 고 다시 설치 했다고 가정 합니다.

또한 장애 조치 (failover) 기간 중에 새 미러 서버 및 백업 서버가 배포 되지 않은 것으로 가정 하 고, 배포 된 유일한 서버가 백업 서버 및 해당 미러 서버인 경우에는 [Lync server 2013의 영구 채팅 서버에 오류가](lync-server-2013-failing-over-persistent-chat-server.md)발생 하는 것으로 간주 합니다.

이러한 단계는 구성을 재해 이전의 상태로 복구하여 기본 서버를 백업 서버로 장애 조치(failover)하도록 디자인되었습니다.

<div>

## <a name="to-fail-back-persistent-chat-server"></a>영구 채팅 서버를 장애 복구 하려면

1.  Lync Server 관리 셸에서 cmdlet을 사용 하 여 영구 채팅 서버 활성 서버 목록에서 모든 서버를 지웁니다 `Set-CsPersistentChatActiveServer` . 이 작업을 수행 하면 장애 복구 중에 모든 영구 채팅 서버가 mgc 데이터베이스 및 mgccomp 데이터베이스에 연결 하지 못합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 보조 영구 채팅 서버 백 엔드 서버의 SQL Server 에이전트는 권한이 부여 된 계정으로 실행 되어야 합니다. 특히 이 계정은 다음과 같은 권한을 포함해야 합니다. 
    > <UL>
    > <LI>
    > <P>백업을 배치 중인 네트워크 공유에 대한 읽기 액세스 권한</P>
    > <LI>
    > <P>백업을 복사 중인 특정 로컬 디렉터리에 대한 쓰기 액세스 권한</P></LI></UL>

    
    </div>

2.  백업 mgc 데이터베이스에서 미러링 해제:
    
    1.  SQL Server Management Studio를 사용 하 여 backup mgc 인스턴스에 연결 합니다.
    
    2.  mgc 데이터베이스를 마우스 오른쪽 단추로 클릭하고 **작업**을 가리킨 후 **미러**를 클릭합니다.
    
    3.  **미러링 제거**를 클릭합니다.
    
    4.  **확인**을 클릭합니다.
    
    5.  mgccomp 데이터베이스에서도 같은 단계를 수행합니다.

3.  새 기본 데이터베이스로 복원할 수 있도록 mgc 데이터베이스를 백업합니다.
    
    1.  SQL Server Management Studio를 사용 하 여 backup mgc 인스턴스에 연결 합니다.
    
    2.  mgc 데이터베이스를 마우스 오른쪽 단추로 클릭하고 **작업**을 가리킨 후 **백업**을 클릭합니다. **데이터베이스 백업** 대화 상자가 나타납니다.
    
    3.  **백업 유형**에서 **전체**를 선택합니다.
    
    4.  **백업 구성 요소**에 대해 **데이터베이스**를 클릭합니다.
    
    5.  **이름**에 제안된 기본 백업 집합 이름을 사용하거나 백업 집합에 대해 다른 이름을 입력합니다.
    
    6.  *\<Optional\>***설명**에 백업 집합에 대 한 설명을 입력 합니다.
    
    7.  대상 목록에서 기본 백업 위치를 제거합니다.
    
    8.  로그 전달을 위해 설정한 공유 위치에 대한 경로를 사용해서 목록에 파일을 추가합니다. 이 경로는 기본 데이터베이스 및 백업 데이터베이스 모두 사용할 수 있습니다.
    
    9.  **확인**을 클릭하여 대화 상자를 닫고 백업 프로세스를 시작합니다.

4.  이전 단계에서 만든 백업 데이터베이스를 사용하여 기본 데이터베이스를 복원합니다.
    
    1.  SQL Server Management Studio를 사용 하 여 기본 mgc 인스턴스에 연결 합니다.
    
    2.  mgc 데이터베이스를 마우스 오른쪽 단추로 클릭하고 **작업**, **복원**을 차례로 클릭한 후 **데이터베이스**를 클릭합니다. **데이터베이스 복원** 대화 상자가 나타납니다.
    
    3.  **장치에서**를 선택합니다.
    
    4.  찾아보기 단추를 클릭하여 **백업 지정** 대화 상자를 엽니다. **백업 미디어**에서 **파일**을 선택합니다. **추가**를 클릭하고 3단계에서 만든 백업 파일을 선택한 후 **확인**을 클릭합니다.
    
    5.  **복원할 백업 집합 선택**에서 백업을 선택합니다.
    
    6.  **페이지 선택** 창에서 **옵션**을 클릭합니다.
    
    7.  **복원 옵션**에서 **기존 데이터베이스 덮어쓰기**를 선택합니다.
    
    8.  **복구 상태**에서 **데이터베이스를 사용할 수 있는 상태로 유지합니다.** 를 선택합니다.
    
    9.  **확인**을 클릭하여 복원 프로세스를 시작합니다.

5.  기본 데이터베이스에 대해 SQL Server 로그 전달을 구성 합니다. [Lync server 2013의 고가용성 및 재해 복구를 위한 영구 채팅 서버 구성](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) 의 절차에 따라 기본 mgc 데이터베이스에 대 한 로그 전달을 설정 합니다.

6.  영구 채팅 서버 활성 서버를 설정 합니다. Lync Server 관리 셸에서 **set-cspersistentchatactiveserver** cmdlet을 사용 하 여 활성 서버 목록을 설정 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 모든 활성 서버는 새 기본 데이터베이스와 동일한 데이터 센터 내에 배치하거나 데이터베이스에 대한 연결 대기 시간이 낮고 대역폭이 높은 데이터 센터에 배치해야 합니다.

    
    </div>

풀을 일반 상태로 복원 다음 Windows PowerShell 명령을 실행 합니다.

    Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal

자세한 내용은 [set-cspersistentchatstate](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

