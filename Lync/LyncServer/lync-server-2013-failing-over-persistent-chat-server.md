---
title: 'Lync Server 2013: 영구 채팅 서버 장애 조치(failover)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over Persistent Chat Server
ms:assetid: 2cd79ffd-fee6-44ce-96cf-b98bf25e2690
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204772(v=OCS.15)
ms:contentKeyID: 48183726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd62d4037ae1795a553d207cb698f88f9b3b8ab8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013에서 영구 채팅 서버 장애 조치(failover)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-02-05_

영구 채팅 서버에 대 한 장애 조치는 주로 수동 프로세스를 위해 설계 되었습니다.

장애 조치 절차는 보조 데이터 센터가 실행 중이 고, 기본 영구 채팅 데이터베이스가 있는 영구 채팅 서버 서비스를 다음을 포함 하 여 완전히 사용할 수 없다는 가정을 기반으로 합니다.

  - 영구 채팅 서버 기본 데이터베이스와 영구 채팅 서버 미러 데이터베이스는 작동 하지 않습니다.

  - Lync Server 프런트 엔드 서버가 작동 중지 되었습니다.

절차는 두 가지 기본 단계를 기반으로 합니다.

  - Mgc (기본 영구 채팅 데이터베이스)를 복구 합니다.

  - 새 기본 데이터베이스에 대 한 미러링을 설정 합니다.

영구 채팅 준수 데이터베이스 (mgccomp)는 장애 조치 되지 않습니다. 이 데이터베이스의 콘텐츠는 임시 이며 준수 어댑터가 데이터를 처리 하므로 제거 됩니다. 데이터 손실을 방지 하기 위해 어댑터 출력을 올바르게 관리 하는 것은 관리자의 책임입니다.

<div>

## <a name="to-fail-over-persistent-chat-server"></a>영구 채팅 서버를 장애 조치할 때

1.  영구 채팅 서버 백업 로그 전달 데이터베이스에서 로그 전달을 제거 합니다.
    
    1.  SQL Server Management Studio를 사용 하 여 영구 채팅 서버 백업 mgc 데이터베이스가 있는 데이터베이스 인스턴스에 연결 합니다.
    
    2.  쿼리 창을 마스터 데이터베이스에 엽니다.
    
    3.  다음 명령을 사용 하 여 로그 전달을 삭제 합니다.
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  백업 공유의 uncopied 백업 파일을 백업 서버의 복사 대상 폴더에 복사 합니다.

3.  적용 되지 않은 트랜잭션 로그 백업을 보조 데이터베이스에 차례로 적용할 수 있습니다. 자세한 내용은에서 http://go.microsoft.com/fwlink/p/?linkid=247428"방법: 트랜잭션 로그 백업 (Transact-sql) 적용"을 참조 하세요.

4.  백업 mgc 데이터베이스를 온라인 상태로 전환 합니다. 1b 단계에서 열리는 쿼리 창을 사용 하 여 다음을 수행 합니다.
    
    1.  Mgc 데이터베이스에 대 한 모든 연결 (있는 경우)을 종료 합니다.
        
        1.  mgc 데이터베이스에 대 한 연결을 식별 하는 **exec sp\_who2** .
        
        2.  ** \<spid\> 를 중단** 하 여 이러한 연결을 종료 합니다.
    
    2.  데이터베이스를 온라인 상태로 만듭니다.
        
        1.  **복구로 데이터베이스 mgc를 복원**합니다.

5.  Lync Server 관리 셸에서는 명령 **집합-CsPersistentChatState-id "서비스: atl-cs-001.litwareinc.com" – PoolState FailedOver** 를 사용 하 여 mgc 백업 데이터베이스로 장애 조치 하세요. Atl-cs-001.litwareinc.com에 대 한 영구 채팅 풀의 정규화 된 도메인 이름을 대체 하세요.
    
    Mgc 백업 데이터베이스는 이제 기본 데이터베이스로 작동 합니다.

6.  Lync Server 관리 셸에서 **CsMirrorDatabase** cmdlet을 사용 하 여 이제 기본 데이터베이스로 작동 하는 백업 데이터베이스에 대해 고가용성 미러를 설정 합니다. 백업 데이터베이스 인스턴스를 기본 데이터베이스로 사용 하 고, 미러 인스턴스로 백업 미러 데이터베이스 인스턴스를 사용 합니다. 이는 처음에 설치 하는 동안 기본 데이터베이스에 대해 구성 된 것과는 다른 미러와 동일 합니다. 자세한 내용은 [lync server 2013에서 백 엔드 서버의 SQL 미러링 배포](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)에서 "Lync Server Management Shell cmdlet 사용" 섹션을 참조 하세요.

7.  영구 채팅 서버 활성 서버를 설정 합니다. Lync Server 명령 셸에서 **set-CsPersistentChatActiveServer** cmdlet을 사용 하 여 활성 서버 목록을 설정 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 모든 활성 서버는 새 기본 데이터베이스와 동일한 데이터 센터 내에 있거나 데이터베이스에 대 한 대기/고속 대역폭 연결이 낮은 데이터 센터에 있어야 합니다.

    
    </div>
    
    이 시점에서 영구 채팅 서버 기본 데이터베이스에서 영구 채팅 서버 백업 데이터베이스로 장애 조치 (failover)가 성공적으로 완료 됩니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

