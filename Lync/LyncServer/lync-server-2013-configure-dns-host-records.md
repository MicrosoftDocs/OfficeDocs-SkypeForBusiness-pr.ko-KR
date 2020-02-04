---
title: 'Lync Server 2013: DNS 호스트 레코드 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS Host records
ms:assetid: 78a1afcf-41c8-4da5-8740-c6570c19078c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398593(v=OCS.15)
ms:contentKeyID: 48184577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b74da23cb0139a982a30207b61032f043f795b76
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-host-records-for-lync-server-2013"></a>Lync Server 2013에 대한 DNS 호스트 레코드 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-01_

이 절차를 완료 하려면 Domain Admins 그룹의 구성원 또는 DnsAdmins 그룹의 구성원으로 최소한 서버나 도메인에 로그온 해야 합니다.

<div>

## <a name="to-configure-dns-host-a-records"></a>DNS 호스트 A 레코드를 구성 하려면

1.  DNS (도메인 이름 시스템) 서버에서 **시작**을 클릭 하 고 **관리 도구**를 클릭 한 다음 **DNS**를 클릭 합니다.

2.  도메인의 콘솔 트리에서 **정방향 조회 영역**을 확장 한 다음 Lync Server 2013을 설치할 도메인을 마우스 오른쪽 단추로 클릭 합니다.

3.  **새 호스트 (A 또는 AAAA)** 를 클릭 합니다.

4.  **이름을**클릭 하 고 풀의 호스트 이름을 입력 합니다 (해당 레코드가 정의 되어 있고 A 레코드의 일부로 입력할 필요가 없는 영역에서 도메인 이름을 가정).

5.  **IP 주소**를 클릭 하 고 프런트 엔드 풀에 대 한 부하 분산 장치의 VIP (가상 IP)를 입력 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 디렉터 풀을 사용 하는 배포에서는 간단한 Url의 호스트 (A) 레코드가 디렉터 부하 분산 장치의 VIP를 가리켜야 합니다.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 부하 분산 장치 없이 토폴로지에 연결 된 Enterprise Edition 서버 또는 디렉터만 배포 하거나 Standard Edition 서버를 배포 하는 경우 Enterprise Edition server, Standard Edition server 또는 디렉터의 IP 주소를 입력 합니다. 풀에 둘 이상의 Enterprise Edition server 또는 디렉터를 배포 하는 경우 부하 분산 장치가 필요 합니다. 부하 분산 장치는 스탠더드 버전 서버에서 사용 되지 않습니다.

    
    </div>

6.  **호스트 추가**를 클릭 한 다음 **확인**을 클릭 합니다.

7.  추가 레코드를 만들려면 4 ~ 5 단계를 반복 합니다.

8.  필요한 모든 레코드를 만든 후 **완료**를 클릭 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

