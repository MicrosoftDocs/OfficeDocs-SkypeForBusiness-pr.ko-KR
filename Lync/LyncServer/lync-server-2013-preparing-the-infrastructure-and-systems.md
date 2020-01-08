---
title: 'Lync Server 2013: 인프라 및 시스템 준비'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing the infrastructure and systems
ms:assetid: 1254ee38-0679-4714-b293-1050f107c158
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398205(v=OCS.15)
ms:contentKeyID: 48183458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e724dd3b6105be3f4601c523dbbf558c91ca9f3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a>Lync Server 2013에 대한 인프라 및 시스템 준비

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-21_

Lync Server 2013을 배포 하려면 토폴로지 작성기를 사용 하 여 토폴로지 디자인을 정의 하 고 게시 해야 합니다. 토폴로지에 필요한 구성 요소를 식별 하려면 토폴로지 작성기를 사용 하 여 토폴로지 디자인을 만들고 저장 합니다. 토폴로지 작성기에 토폴로지를 게시 하기 전에 다음을 수행 합니다.

  - 필요한 모든 컴퓨터 (Lync Server 2013, 데이터베이스 서버, Iis (인터넷 정보 서비스)를 실행 하는 서버를 비롯 한 토폴로지 작성기를 사용 하 여 만들고 저장 한 토폴로지 디자인의 각 구성 요소에 대 한 하드웨어를 가져오고 설치 합니다 ( IIS), 역방향 프록시 서버, 적절 하 게, 네트워크 어댑터, 하드웨어 부하 분산 장치, 저장소 장치 (예: 파일 서버) 배포에 필요한 구성 요소를 지정 하는 토폴로지를 정의 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 토폴로지 정의 및 구성을](lync-server-2013-defining-and-configuring-the-topology.md)참조 하세요. 서버에 대 한 하드웨어 요구 사항에 대 한 자세한 내용은 지원 가능성 문서에서 [Lync Server 2013에 대해 지원 되는 하드웨어](lync-server-2013-supported-hardware.md) 를 참조 하세요.

  - 네트워킹 인프라가 요구 사항을 충족 하는지 확인 합니다. 자세한 내용은 계획 설명서의 [Lync Server 2013에 대 한 네트워크 인프라 요구 사항을](lync-server-2013-network-infrastructure-requirements.md) 참조 하세요.

  - Active Directory 도메인 서비스를 설정 합니다. 토폴로지를 게시 하 고 사용 하도록 설정 하려면 AD DS의 컴퓨터 계정으로 내부 서버를 표시 해야 합니다. 이 작업은 컴퓨터를 AD DS에 가입 하 여 수행 됩니다. AD DS를 준비 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에 대 한 Active Directory 도메인 서비스 준비](lync-server-2013-preparing-active-directory-domain-services.md)를 참조 하세요.

  - 파일 공유를 만듭니다. Standard Edition 서버는 필요한 파일에 대 한 파일 공유를 호스트할 수 있지만 엔터프라이즈 배포에서는 프런트 엔드 서버에서 파일 공유를 호스팅할 수 없습니다. 토폴로지 작성기를 성공적으로 완료 하려면 폴더 및 공유에 대 한 ACL (액세스 제어 목록)을 배포 하 고 설정 하는 데 필요한 사용 권한 및 그룹 구성원 자격이 올바르게 설정 되어 있어야 합니다. 토폴로지 작성기를 실행 하는 사용자에 게 다음과 같은 사용 권한 및 그룹 구성원이 있는지 확인 해야 합니다.
    
      - 로컬 관리자의 구성원
    
      - 도메인 사용자의 구성원
    
      - 공유 및 파일 저장소 폴더에 대 한 모든 권한

  - Enterprise Edition의 경우 SQL Server를 설치 하 고 구성 합니다. Sql Server 기반 서버가 온라인 상태 여야 하며, 토폴로지를 게시 하는 사용자는 sql server의 로컬 관리자이 고 sql server 인스턴스에서 SQL Server sysadmin 그룹의 구성원 이어야 합니다.

이 항목에 설명 된 대로 모든 준비 작업을 완료 한 후 토폴로지를 게시 하기 전에 Windows 운영 체제 및 기타 필수 구성 요소 소프트웨어 설치를 비롯 한 다른 준비 작업을 수행 해야 할 수도 있습니다. IIS 및 DNS 구성 이러한 작업에 대 한 자세한 내용은 [Lync server 2013을 실행 하는 서버의 시스템 요구 사항](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [lync SERVER 2013 용 IIS 구성](lync-server-2013-configure-iis.md)및 [lync 2013 server 용 인프라 및 시스템을 준비 하는](lync-server-2013-preparing-the-infrastructure-and-systems.md)방법에 대해 알아보세요. 또한 클라이언트 및 클라이언트 요구 사항에 대해 잘 알고 있어야 합니다. 자세한 내용은 [Lync Server 2013에서 클라이언트 및 장치 배포](lync-server-2013-deploying-clients-and-devices.md)를 참조 하세요.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013의 하드웨어 설치](lync-server-2013-hardware-setup.md)

  - [Lync Server 2013의 소프트웨어 설치](lync-server-2013-software-setup.md)

  - [Lync Server 2013에 대한 Active Directory 도메인 서비스 준비](lync-server-2013-preparing-active-directory-domain-services.md)

  - [Lync Server 2013에 대해 SQL Server 구성](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [프런트 엔드 풀 또는 Standard Edition 서버에 대한 Lync Server 2013의 DNS 레코드 구성](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [Lync Server 2013 관리 도구 설치](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

