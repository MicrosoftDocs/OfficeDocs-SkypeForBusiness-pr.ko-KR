---
title: 'Lync Server 2013: 하드웨어 설치'
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
ms.openlocfilehash: 6831ba5f8d2afea7bddbd0c26ab4cebb2cff44f1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727898"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-setup-for-lync-server-2013"></a>Lync Server 2013의 하드웨어 설치

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-21_

토폴로지를 구현 해야 하는 인프라에 필요한 하드웨어 및 기타 구성 요소를 설정 하려면 토폴로지 작성기에 토폴로지를 게시 하기 전에 다음을 수행 해야 합니다.

  - 필요한 모든 컴퓨터 (Lync Server 2013, 데이터베이스 서버, IIS (인터넷 정보 서비스)를 실행 하는 서버)를 비롯 한 토폴로지 디자인의 각 구성 요소에 대 한 하드웨어를 설치 하 고 다음을 실행 합니다. 프록시 서버 (해당 하는 경우), 네트워크 어댑터, 하드웨어 로드 균형 조정기, 저장소 장치 (예: 파일 서버) 네트워크 어댑터의 수 및 속도에 대 한 권장 사항을 팔 로우 하 고 있는지 확인 합니다. 하드웨어 부하 분산 장치를 사용 하는 경우, Lync Server 2013에서 사용할 수 있도록 공급 업체의 적절 한 정보를 보유 하 고 있는지 확인 합니다. Lync Server에서 필요한 파일 공유를 보관 하는 데 파일 서버 또는 다른 서버를 사용 하는 경우 서버를 사용할 수 있는지 확인 하 고 파일 공유를 구성할 준비가 되어 있어야 합니다. 배포에 필요한 구성 요소를 지정 하는 토폴로지를 정의 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 토폴로지 정의 및 구성을](lync-server-2013-defining-and-configuring-the-topology.md)참조 하세요. 서버에 대 한 하드웨어 요구 사항에 대 한 자세한 내용은 지원 가능성 문서에서 [Lync Server 2013에 대해 지원 되는 하드웨어](lync-server-2013-supported-hardware.md) 를 참조 하세요.

  - 네트워킹 인프라가 요구 사항을 충족 하는지 확인 합니다. 자세한 내용은 계획 설명서의 [Lync Server 2013에 대 한 네트워크 인프라 요구 사항을](lync-server-2013-network-infrastructure-requirements.md) 참조 하세요.

  - Active Directory 도메인 서비스를 설정 합니다. Ad ds를 설정 하려면 ad ds에 배포 하려는 모든 구성 요소를 정의 하는 것이 포함 됩니다. AD DS를 준비 하는 방법에 대 한 자세한 내용은 배포 설명서에서 [Lync Server 2013에 대 한 Active Directory 도메인 서비스 준비](lync-server-2013-preparing-active-directory-domain-services.md) 를 참조 하세요.

  - 파일 공유를 만드는 데 필요한 사용 권한을 설정 합니다. Lync Server 2013에서 파일 공유를 사용 하는 권한은 토폴로지를 게시할 때 토폴로지 작성기에 의해 자동으로 구성 됩니다. 그러나 토폴로지를 게시 하는 데 사용 되는 사용자 계정에는 토폴로지 작성기가 필요한 권한을 구성할 수 있도록 파일 공유에 대 한 모든 권한 (읽기/쓰기/수정)이 있어야 합니다. 토폴로지 작성기 게시 프로세스 중에 파일 공유를 올바르게 관리할 수 있으려면 사용자가 구성원으로 속해 있는 사용자 또는 도메인 그룹을 파일 공유가 있는 컴퓨터에서 로컬 관리자 그룹의 구성원으로 만들어야 합니다. 다중 도메인 시나리오에서 사용자 또는 그룹을 도메인 B의 컴퓨터에서 로컬 관리자 그룹의 구성원으로 만들어야 합니다 (여기서는 파일 공유가 위치할 위치).
    
    DFS (분산 파일 시스템)에서 파일 공유를 사용 하 여 업데이트 하는 방법에 대 한 자세한 내용은 [Lync Server 2013의 파일 저장소 구성을](lync-server-2013-configure-dfs-file-storage.md)참조 하세요.
    
    <div>
    

    > [!WARNING]  
    > Lync Server 2013, Enterprise Edition 용 파일 공유를 프런트 엔드 서버에서 찾을 수 없습니다.

    
    </div>

  - 웹 서비스의 하드웨어 부하 분산 장치를 설치 하 고 설정 합니다. DNS (도메인 이름 시스템) 부하 분산을 배포 하는 경우에도 이러한 풀에 대해 하드웨어 부하 분산 장치를 사용 해야 하지만 HTTP/HTTPS 트래픽에만 사용할 수 있습니다. 하드웨어 로드 균형 조정기는 포트 443 및 80을 통해 클라이언트의 HTTPS 트래픽에 사용 됩니다. 이러한 풀에 대 한 하드웨어 부하 분산 장치가 여전히 필요 하지만, 설정 및 관리는 하드웨어 로드 균형 조정기의 관리자가 가장 하는 HTTP/HTTPS 트래픽에 주로 사용할 수 있습니다.

이 항목에 설명 된 대로 모든 준비 작업을 완료 한 후에 토폴로지를 게시 하기 전에 다음 작업도 수행 해야 합니다.

  - [Lync Server 2013의 서버에 운영 체제 및 필수 구성 요소 소프트웨어 설치](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [Lync Server 2013에 대한 IIS 구성](lync-server-2013-configure-iis.md)

  - [Lync Server 2013에 대해 SQL Server 구성](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [프런트 엔드 풀 또는 Standard Edition 서버에 대한 Lync Server 2013의 DNS 레코드 구성](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

