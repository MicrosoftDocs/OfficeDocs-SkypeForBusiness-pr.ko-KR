---
title: 'Lync Server 2013: 데이터베이스 보안 강화 및 보호'
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
ms.openlocfilehash: 0254c77bb276add6f55ccff623c1fc2bec590102
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536915"
---
# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a>Lync Server 2013의 데이터베이스 보안 강화 및 보호

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-12-05_

또한 Microsoft Lync Server 2013은 사용자 정보, 회의 상태, 보관 데이터 및 CDRs (통화 정보 기록)를 저장 하기 위한 SQL Server 데이터베이스에 따라 달라 집니다. 응용 프로그램 데이터를 분할 하 여 내결함성을 개선 하 고 문제 해결을 간소화 하 여 Lync Server 백 엔드 데이터베이스에서 Lync Server 2013 데이터의 가용성을 최대화할 수 있습니다. 이러한 목표를 달성하려면 다음과 같은 방법으로 응용 프로그램을 분할합니다.

  - **서버 분할 모범 사례 사용**     운영 체제, 응용 프로그램 및 프로그램 파일을 데이터 파일과 분리 합니다.

  - **트랜잭션 로그 파일 및 데이터베이스 파일 저장**     이러한 파일을 별도로 저장 하 여 내결함성을 향상 하 고, 복구를 최적화 하 고, 암호화 된 디스크 또는 볼륨에 저장 합니다.

  - **서버 클러스터링 사용**     백 엔드 서버를 클러스터 하 여 Lync Server 2013 시스템 가용성을 최적화 합니다.

  - **모든 데이터 백업이 암호화 되 고 올바르게 처리**     되는지 확인 손실, 삭제 또는 잘못 된 백업 미디어는 Lync Server 2013 배포의 데이터 보안에 큰 위협이 될 수 있습니다.

Standard Edition server를 제외한 모든 Lync Server 2013 서버에서 SQL Server Express 인스턴스 (RTCLOCAL 인스턴스)에 원격으로 액세스할 수 없으며 Standard Edition 서버에서 SQL Server Express를 제외 하 고 로컬 방화벽 예외가 생성 되지 않습니다. Standard Edition 서버에서는 백 엔드 데이터베이스 및 CMS(중앙 관리 저장소)가 모두 원격으로 액세스할 수 있도록 설정됩니다. SQL Server 데이터베이스를 강화하려면 다음을 수행할 수 있습니다.

  - Standard Edition 서버에서 SQL Server Express 방화벽을 사용자 지정하여 데이터베이스에 원격으로 액세스할 수 있는 서버 범위를 제한합니다. 기본적으로 모든 IP 주소가 데이터베이스에 원격으로 액세스할 수 있습니다.

  - SQL Server 구성 관리자를 사용하여 SQL Server 원격 액세스에 대한 프로토콜, IP 주소 및 포트를 지정합니다.
    
      - Lync Server 2013는 TCP/IP 프로토콜을 사용 합니다. 여기에서 IPv4(IP 버전 4)는 지원되지만 IPv6(IP 버전 6)이 지원되지 않습니다.
        
        <div>
        

        > [!NOTE]  
        > Lync Server 2013는 이중 IP 스택이 설정 된 네트워크에서 작동할 수 있습니다.

        
        </div>
    
      - Lync Server 2013에서는 여러 IP 주소 (다중 홈 네트워크 주소 카드)를 지원 합니다. SQL Server가 특정 IP 주소로만 수신 대기하고(개별 주소 또는 서브넷별) 특정 프로토콜만 사용하도록 지정할 수 있습니다.
    
      - Lync Server 2013는 정적 및 동적 SQL Server 포트를 지원 합니다.

  - 정적(기본값이 아님) 포트에서 SQL Server를 실행하고 수신 대기 포트를 클라이언트에 보고할 수 없도록 SQL Server 브라우저는 실행하지 않습니다. 이를 위해서는 프런트 엔드 서버, 모니터링 서버, 보관 서버 및 관리 콘솔 (Lync Server 관리 셸, Lync Server 제어판 또는 토폴로지 작성기 실행)과 Lync Server 데이터베이스를 실행 하는 다른 모든 서버를 포함 하는 각 SQL Server 클라이언트에 사용자 지정 구성이 필요 합니다.

<div>


> [!NOTE]  
> 데이터베이스에 대한 액세스는 신뢰할 수 있는 데이터베이스 관리자로 제한해야 합니다. 악성 데이터베이스 관리자는 데이터베이스 관리자에 게 Lync Server 2013 서버에 대 한 직접 액세스 권한이 나 제어권을 부여 하지 않은 경우에도 Lync Server 2013 서버에 대 한 권한을 취득 하거나 서비스에서 중요 한 정보를 가져올 수 있도록 데이터베이스에 데이터를 삽입 하거나 수정할 수도 있습니다.



</div>

사용자 지정 구성에 대 한 자세한 내용과 SQL Server 데이터베이스를 강화 하는 방법에 대 한 자세한 내용은 다음 홉 blog 문서 "사용자 지정 SQL Server 네트워크 구성으로 Lync Server 2010 사용"을 참조 하십시오 [https://go.microsoft.com/fwlink/p/?LinkId=214008](https://go.microsoft.com/fwlink/p/?linkid=214008) .

<div>


> [!NOTE]  
> 운영 체제 및 응용 프로그램 서버를 강화 하 고, 그룹 정책을 사용 하 여 Lync Server 배포에서 보안 잠금을을 구현할 수도 있습니다. 자세한 내용은 <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Lync Server 2013에 대 한 서버 및 응용 프로그램 강화 및 보호</A>를 참조 하세요.



</div>

</div>

<span> </span>

</div>

</div>

</div>

