---
title: 'Lync Server 2013: 영구 채팅 서버 장애 조치 (failover)'
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
ms.openlocfilehash: 91c4d5092fc12ac374b57872b7cda2d6f88d9e33
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-over-persistent-chat-server-in-lync-server-2013"></a>Lync Server 2013의 영구 채팅 서버 장애 조치 (failover)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-02-05_

영구 채팅 서버에 대 한 장애 조치 (Failover)는 주로 수동 프로세스를 위한 것입니다.

장애 조치 (failover) 절차는 보조 데이터 센터가 실행 중이 고 기본 영구 채팅 데이터베이스가 있는 영구 채팅 서버 서비스를 사용 하 여 다음을 포함 하는 것을 완전히 사용할 수 없다는 가정을 기반으로 합니다.

  - 영구 채팅 서버 기본 데이터베이스 및 영구 채팅 서버 미러 데이터베이스의 작동이 중지 되었습니다.

  - Lync Server 프런트 엔드 서버가 다운 되었습니다.

이 절차는 다음과 같은 두 기본 단계를 기반으로 합니다.

  - 기본 영구 채팅 데이터베이스 (mgc)를 복구 합니다.

  - 새 주 데이터베이스에 대해 미러링을 설정합니다.

영구 채팅 준수 데이터베이스 (mgccomp)가 장애 조치 (failover) 되지 않습니다. 이 데이터베이스의 콘텐츠는 일시적인 항목이며 준수 어댑터가 데이터를 처리하면 삭제됩니다. 데이터 손실을 방지 하기 위해 어댑터 출력을 올바르게 관리 하는 것은 영구 채팅 관리자의 책임입니다.

<div>

## <a name="to-fail-over-persistent-chat-server"></a>영구 채팅 서버를 장애 조치 (failover)

1.  영구 채팅 서버 백업 로그 전달 데이터베이스에서 로그 전달을 제거 합니다.
    
    1.  SQL Server Management Studio를 사용 하 여 영구 채팅 서버 백업 mgc 데이터베이스가 있는 데이터베이스 인스턴스에 연결 합니다.
    
    2.  마스터 데이터베이스에 대한 쿼리 창을 엽니다.
    
    3.  다음 명령을 사용하여 로그 전달을 삭제합니다.
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  복사되지 않은 백업 파일을 백업 공유에서 백업 서버의 복사 대상 폴더로 복사합니다.

3.  시퀀스에서 적용되지 않은 트랜잭션 로그 백업을 보조 데이터베이스에 적용합니다. 자세한 내용은 "How to: Transaction Log Backup (Transact-sql) 적용"을 참조 하십시오 https://go.microsoft.com/fwlink/p/?linkid=247428.

4.  백업 mgc 데이터베이스를 온라인 상태로 설정합니다. 1b단계에서 연 쿼리 창을 사용하여 다음을 수행합니다.
    
    1.  mgc 데이터베이스에 대한 연결이 있는 경우 모두 종료합니다.
        
        1.  **exec sp\_who2** -mgc 데이터베이스에 대 한 연결을 식별 합니다.
        
        2.  ** \<spid\> 를 중단** 하 여 이러한 연결을 종료 합니다.
    
    2.  데이터베이스를 온라인 상태로 설정합니다.
        
        1.  **recovery를 사용 하 여 데이터베이스 mgc를 복원**합니다.

5.  Lync Server 관리 셸에서 명령 **집합-set-cspersistentchatstate-Identity "service: atl-001.litwareinc.com" – PoolState FailedOver** 를 사용 하 여 mgc 백업 데이터베이스로 장애 조치 (failover) 합니다. 영구 채팅 풀의 fqdn (정규화 된 도메인 이름)을 atl-cs-001.litwareinc.com로 대체 해야 합니다.
    
    이제 mgc 백업 데이터베이스가 주 데이터베이스로 사용됩니다.

6.  Lync Server 관리 셸에서 **CsMirrorDatabase** cmdlet을 사용 하 여 이제 기본 데이터베이스로 사용 되는 백업 데이터베이스에 대 한 고가용성 미러를 설정 합니다. 백업 데이터베이스 인스턴스를 주 데이터베이스로, 백업 미러 데이터베이스 인스턴스를 미러 인스턴스로 사용합니다. 이 미러는 설치 중에 주 데이터베이스에 대해 처음 구성한 미러와는 다릅니다. 자세한 내용은 [Lync server 2013에서 백 엔드 서버 고가용성을 위해 SQL 미러링 배포](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)의 "Lync Server 관리 셸 cmdlet 사용" 섹션을 참조 하십시오.

7.  영구 채팅 서버 활성 서버를 설정 합니다. Lync Server 명령 셸에서 **set-cspersistentchatactiveserver** cmdlet을 사용 하 여 활성 서버 목록을 설정 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 모든 활성 서버는 새 기본 데이터베이스와 동일한 데이터 센터 내에 배치하거나 데이터베이스에 대한 연결 대기 시간이 낮고 대역폭이 높은 데이터 센터에 배치해야 합니다.

    
    </div>
    
    이때 영구 채팅 서버 기본 데이터베이스에서 영구 채팅 서버 백업 데이터베이스로 장애 조치 (failover)가 정상적으로 완료 됩니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

