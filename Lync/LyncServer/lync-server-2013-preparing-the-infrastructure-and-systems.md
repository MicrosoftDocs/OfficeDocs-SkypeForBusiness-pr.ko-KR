---
title: 'Lync Server 2013: 인프라 및 시스템 준비'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the infrastructure and systems
ms:assetid: 1254ee38-0679-4714-b293-1050f107c158
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398205(v=OCS.15)
ms:contentKeyID: 48183458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1391d57232d261edcdfcdd7c4668ee025b1420b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506845"
---
# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a>Lync Server 2013의 인프라 및 시스템 준비

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-21_

Lync Server 2013을 배포 하려면 토폴로지 작성기를 사용 하 여 토폴로지 디자인을 정의 하 고 게시 해야 합니다. 토폴로지에 필요한 구성 요소를 확인 하려면 토폴로지 작성기를 사용 하 여 토폴로지 디자인을 만들고 저장 합니다. 토폴로지 작성기에서 토폴로지를 게시하기 전에 다음을 수행합니다.

  - 필요한 모든 컴퓨터 (Lync Server 2013, 데이터베이스 서버, IIS (인터넷 정보 서비스)를 실행 하는 서버, 적절 한 역방향 프록시 서버를 실행 하는 서버), 네트워크 어댑터, 하드웨어 부하 분산 및 저장 장치 (예: 파일 서버)를 포함 하 여 토폴로지 작성기를 사용 하 여 만들고 저장 한 토폴로지 디자인의 각 구성 요소에 대 한 하드웨어를 가져오고 설치 합니다. 배포에 필요한 구성 요소를 지정 하는 토폴로지를 정의 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 토폴로지 정의 및 구성을](lync-server-2013-defining-and-configuring-the-topology.md)참조 하십시오. 서버에 대 한 하드웨어 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서에서 [Lync Server 2013 용으로 지 원하는 하드웨어](lync-server-2013-supported-hardware.md) 를 참조 하십시오.

  - 네트워크 인프라가 요구 사항을 충족 하는지 확인 합니다. 자세한 내용은 계획 설명서에서 [Lync Server 2013의 네트워크 인프라 요구 사항](lync-server-2013-network-infrastructure-requirements.md) 를 참조 하십시오.

  - Active Directory 도메인 서비스를 설정 합니다. 토폴로지를 게시하고 사용하도록 설정하려면 AD DS의 컴퓨터 계정을 통해 내부 서버를 표시해야 합니다. 이렇게 하려면 컴퓨터를 AD DS에 연결합니다. AD DS를 준비 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에 대 한 Active Directory 도메인 서비스 준비](lync-server-2013-preparing-active-directory-domain-services.md)를 참조 하세요.

  - 파일 공유를 만듭니다. Standard Edition 서버에서는 필수 파일 저장소에 대한 파일 공유를 호스팅할 수 있는 반면, 엔터프라이즈 배포에서는 파일 공유를 프런트 엔드 서버에서 호스팅할 수 없습니다. 파일 공유를 호스팅하려면 토폴로지 작성기에 대해 폴더 및 공유에 ACL(액세스 제어 목록)을 배포하고 설정하는 데 필요한 사용 권한 및 그룹 구성원 자격을 제대로 설정해야 합니다. 토폴로지 작성기를 실행 하는 사용자에 게 다음과 같은 사용 권한 및 그룹 구성원 자격이 있는지 확인 해야 합니다.
    
      - Local Administrators 그룹의 구성원
    
      - Domain Users의 구성원
    
      - 파일 저장소의 공유 및 폴더에 대한 모든 권한

  - Enterprise Edition의 경우 SQL Server를 설치 및 구성합니다. SQL Server 설치를 정상적으로 수행하려면 SQL Server 기반 서버가 온라인 상태여야 하며, 토폴로지 게시자는 SQL Server의 로컬 관리자인 동시에 SQL Server 인스턴스의 SQL Server sysadmin 그룹 구성원이어야 합니다.

이 항목에서 설명된 준비 작업을 모두 완료한 후 토폴로지를 게시하기 전에 Windows 운영 체제 및 기타 필수 구성 요소 소프트웨어를 설치하고 IIS를 설정하며 DNS를 구성하는 작업을 비롯한 기타 준비 작업을 수행해야 합니다. 이러한 작업에 대 한 자세한 내용은 [lync server 2013를 실행 하는 서버의 시스템 요구 사항](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), lync [server 2013에 대 한 IIS 구성](lync-server-2013-configure-iis.md)및 [lync server 2013에 대 한 인프라 및 시스템 준비](lync-server-2013-preparing-the-infrastructure-and-systems.md)를 참조 하세요. 또한 클라이언트 및 클라이언트 요구 사항에 대해서도 잘 알고 있어야 합니다. 자세한 내용은 [Lync Server 2013에서 클라이언트 및 장치 배포](lync-server-2013-deploying-clients-and-devices.md)를 참조 하십시오.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013의 하드웨어 설정](lync-server-2013-hardware-setup.md)

  - [Lync Server 2013 용 소프트웨어 설치](lync-server-2013-software-setup.md)

  - [Lync Server 2013에 대한 Active Directory 도메인 서비스 준비](lync-server-2013-preparing-active-directory-domain-services.md)

  - [Lync Server 2013에 대해 SQL Server 구성](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [Lync Server 2013에서 프런트 엔드 풀 또는 Standard Edition Server에 대 한 DNS 레코드 구성](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [Lync Server 2013 관리 도구 설치](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

