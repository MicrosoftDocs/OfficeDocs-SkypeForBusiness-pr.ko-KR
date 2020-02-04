---
title: 'Lync Server 2013: 데이터베이스 강화 및 보호'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting the databases of Lync Server 2013
ms:assetid: 6953e721-3511-4235-b848-51bab093dc89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518330(v=OCS.15)
ms:contentKeyID: 62625490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77e02a5fd0f90367f23e7b0fb314f037f7b31e45
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a>Lync Server 2013의 데이터베이스 강화 및 보호

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-12-05_

Microsoft Lync Server 2013는 사용자 정보, 회의 상태, 보관 데이터, 그리고 CDRs (통화 정보 레코드)를 저장 하는 SQL Server 데이터베이스에 따라서도 달라 집니다. 내결함성을 개선 하 고 문제 해결을 간소화 하는 방식으로 응용 프로그램 데이터를 분할 하 여 Lync Server 백 엔드 데이터베이스에서 Lync Server의 2013 데이터 가용성을 최대화할 수 있습니다. 이러한 목표를 달성 하려면 다음을 기준으로 응용 프로그램 데이터를 분할 합니다.

  - **서버 분할 모범 사례**   를 사용 하 여 운영 체제, 응용 프로그램 및 프로그램 파일을 데이터 파일과 구분 합니다.

  - **트랜잭션 로그 파일 및 데이터베이스 파일**   을 저장 하면 이러한 파일을 별도로 저장 하 여 내결함성을 높이고 복구를 최적화 하 고 암호화 된 디스크 또는 볼륨에 저장할 수 있습니다.

  - **서버 클러스터링**   사용-백 엔드 서버를 클러스터 하 여 Lync server 2013 시스템 가용성을 최적화 합니다.

  - **모든 데이터 백업이 암호화 되 고 적절 하 게 처리**   되었는지 확인 합니다. 백업 미디어는 Lync Server 2013 배포에 대 한 데이터 보안에 중대 한 위험을 초래할 수 있습니다.

Standard Edition server를 제외한 모든 Lync Server 2013 서버에서 SQL Server Express 인스턴스 (RTCLOCAL instance)에 원격으로 액세스할 수 없으며 Standard Edition 서버에서 SQL Server Express를 제외한 로컬 방화벽 예외는 만들어지지 않습니다. 스탠더드 버전 서버에서는 백 엔드 데이터베이스와 CMS (중앙 관리 저장소)가 모두 원격으로 액세스할 수 있도록 설정 됩니다. SQL Server 데이터베이스를 강화 하려면 다음을 수행 하면 됩니다.

  - Standard Edition 서버에서 SQL Server Express 방화벽을 사용자 지정 하 여 데이터베이스에 원격으로 액세스할 수 있는 서버의 범위를 제한 합니다. 기본적으로 모든 IP 주소는 데이터베이스에 원격으로 액세스할 수 있습니다.

  - SQL Server 구성 관리자를 사용 하 여 SQL Server 원격 액세스용 프로토콜, IP 주소 및 포트를 지정 합니다.
    
      - Lync 서버 2013는 TCP/IP 프로토콜을 사용 합니다. IPv4 (ip 버전 4)를 지원 하지만 IPv6는 아닙니다.
        
        <div>
        

        > [!NOTE]  
        > Lync Server 2013는 이중 IP 스택을 사용 하는 네트워크에서 작동할 수 있습니다.

        
        </div>
    
      - Lync 서버 2013는 여러 IP 주소 (멀티홈 네트워크 주소 카드)를 지원 합니다. SQL Server에서 특정 IP 주소 (개별 주소 또는 서브넷)만 수신 하 고 특정 프로토콜만 사용 하도록 지정할 수 있습니다.
    
      - Lync Server 2013는 정적 및 동적 SQL Server 포트를 지원 합니다.

  - 기본이 아닌 정적 포트에서 SQL Server를 실행 하 고 클라이언트에 수신 대기 포트를 보고할 수 없기 때문에 SQL Server Browser를 실행 하지 않습니다. 이를 위해서는 프런트 엔드 서버, 모니터링 서버, 보관 서버, 관리 콘솔 (Lync Server Management Shell, Lync Server 제어판 또는 토폴로지 작성기 실행)을 포함 하 여 각 SQL Server 클라이언트에 사용자 지정 구성이 필요 합니다. Lync Server 데이터베이스를 실행 하는 서버).

<div>


> [!NOTE]  
> 데이터베이스에 대 한 액세스는 신뢰할 수 있는 데이터베이스 관리자만 사용할 수 있어야 합니다. 데이터베이스 관리자가 직접 액세스 권한을 부여 하지 않은 경우에도 악의적인 데이터베이스 관리자가 데이터베이스에 데이터를 삽입 하거나 수정 하 여 Lync Server 2013 서버에 대 한 권한을 얻거나 서비스에서 중요 한 정보를 얻을 수 있습니다. Lync Server 2013 서버를 제어 합니다.



</div>

사용자 지정 구성 및 SQL Server 데이터베이스 강화에 대 한 자세한 내용은 NextHop 블로그 문서 "사용자 지정 SQL Server 네트워크 구성을 사용 하 여 Lync Server 2010 사용"을 [http://go.microsoft.com/fwlink/p/?LinkId=214008](http://go.microsoft.com/fwlink/p/?linkid=214008)참조 하세요.

<div>


> [!NOTE]  
> 또한 운영 체제 및 응용 프로그램 서버를 강화 하 고 그룹 정책을 사용 하 여 Lync Server 배포에서 보안 lockdowns를 구현할 수 있습니다. 자세한 내용은 <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Lync Server 2013에 대 한 서버 및 응용 프로그램 강화 및 보호</A>를 참조 하세요.



</div>

</div>

<span> </span>

</div>

</div>

</div>

