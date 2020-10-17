---
title: 'Lync Server 2013: 하드웨어 설정'
description: 'Lync Server 2013: 하드웨어 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware setup
ms:assetid: 37a9f295-cde3-4beb-9a6a-2580082798ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425852(v=OCS.15)
ms:contentKeyID: 48183834
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e798ce32c1f89bba40ad9245426492b0489e7b4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552914"
---
# <a name="hardware-setup-for-lync-server-2013"></a>Lync Server 2013의 하드웨어 설정

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-21_

토폴로지를 구현 하는 데 필요한 인프라에 필요한 하드웨어 및 기타 구성 요소를 설정 하려면 토폴로지 작성기에서 토폴로지를 게시 하기 전에 다음 작업을 수행 해야 합니다.

  - 필요한 모든 컴퓨터 (Lync Server 2013, 데이터베이스 서버, IIS (인터넷 정보 서비스)를 실행 하는 서버 및 역방향 프록시 서버를 실행 하는 서버), 네트워크 어댑터, 하드웨어 부하 분산 및 저장 장치 (예: 파일 서버)를 포함 하 여 토폴로지 작성기를 사용 하 여 만들고 저장 한 토폴로지 디자인에서 각 구성 요소에 대 한 하드웨어를 설치 합니다. 네트워크 어댑터 수 및 속도에 대해 권장 사항을 준수했는지 확인합니다. 하드웨어 부하 분산 장치를 사용 하는 경우에는 해당 공급 업체의 적절 한 정보를 사용 하 여 Lync Server 2013에서 사용할 수 있도록 구성 해야 합니다. Lync Server에 필요한 파일 공유를 저장할 파일 서버나 기타 서버를 사용 하는 경우에는 해당 서버를 사용할 수 있는지와 파일 공유의 구성을 준비 해야 합니다. 배포에 필요한 구성 요소를 지정 하는 토폴로지를 정의 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 토폴로지 정의 및 구성을](lync-server-2013-defining-and-configuring-the-topology.md)참조 하십시오. 서버에 대 한 하드웨어 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서에서 [Lync Server 2013 용으로 지 원하는 하드웨어](lync-server-2013-supported-hardware.md) 를 참조 하십시오.

  - 네트워크 인프라가 요구 사항을 충족 하는지 확인 합니다. 자세한 내용은 계획 설명서에서 [Lync Server 2013의 네트워크 인프라 요구 사항](lync-server-2013-network-infrastructure-requirements.md) 를 참조 하십시오.

  - Active Directory 도메인 서비스를 설정 합니다. AD DS 설치 작업에는 AD DS를 준비하는 작업과 AD DS에서 배포할 모든 구성 요소를 정의하는 작업이 포함됩니다. AD DS를 준비 하는 방법에 대 한 자세한 내용은 배포 설명서에서 [Active Directory 도메인 서비스에 대 한 Lync Server 2013 준비](lync-server-2013-preparing-active-directory-domain-services.md) 를 참조 하세요.

  - 파일 공유를 만드는 데 필요한 권한을 설정합니다. Lync Server 2013의 파일 공유 사용 권한은 토폴로지를 게시할 때 토폴로지 작성기에 의해 자동으로 구성 됩니다. 그러나 토폴로지를 게시 하는 데 사용 되는 사용자 계정에는 토폴로지 작성기에서 필요한 권한을 구성 하기 위해 파일 공유에 대 한 모든 권한 (읽기/쓰기/수정)이 있어야 합니다. 토폴로지 작성기 게시 프로세스 중에 파일 공유를 올바르게 관리할 수 있도록 하려면 사용자가 구성원으로 속해 있는 사용자 또는 도메인 그룹이 파일 공유가 있는 컴퓨터에서 로컬 Administrators 그룹의 구성원 이어야 합니다. 다중 도메인 시나리오에서 도메인 A 사용자나 그룹은 파일 공유가 있는 도메인 B의 컴퓨터에서 로컬 Administrators 그룹의 구성원으로 지정되어야 합니다.
    
    DFS (분산 파일 시스템)에서 파일 공유를 사용 하 여 업데이트 하는 방법에 대 한 자세한 내용은 [Configure file storage For Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md)을 참조 하십시오.
    
    <div>
    

    > [!WARNING]  
    > Lync Server 2013, Enterprise Edition에 대 한 파일 공유는 프런트 엔드 서버에 있을 수 없습니다.

    
    </div>

  - 웹 서비스에 대 한 하드웨어 부하 분산 장치를 설치 하 고 설정 합니다. DNS (Domain Name System) 부하 분산을 배포 하는 경우에도 이러한 풀에 대 한 하드웨어 부하 분산 장치를 사용 해야 하지만 HTTP/HTTPS 트래픽만 사용할 수 있습니다. 하드웨어 부하 분산 장치는 포트 443 및 80을 통해 클라이언트에서 전송되는 HTTPS 트래픽에 사용됩니다. 이러한 풀에 대 한 하드웨어 부하 분산 장치는 여전히 필요 하지만 설치 및 관리는 하드웨어 부하 분산 장치의 관리자가 익숙한 HTTP/HTTPS 트래픽을 위한 것입니다.

이 항목에서 설명하는 모든 준비 작업을 완료한 후에는 토폴로지를 게시하기 전에 다음 작업도 수행해야 합니다.

  - [Lync Server 2013의 서버에 운영 체제 및 필수 구성 요소 소프트웨어 설치](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [Lync Server 2013에 대 한 IIS 구성](lync-server-2013-configure-iis.md)

  - [Lync Server 2013에 대해 SQL Server 구성](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [Lync Server 2013에서 프런트 엔드 풀 또는 Standard Edition Server에 대 한 DNS 레코드 구성](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

