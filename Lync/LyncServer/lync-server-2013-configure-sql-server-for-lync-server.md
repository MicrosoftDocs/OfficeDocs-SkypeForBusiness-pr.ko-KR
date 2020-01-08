---
title: 'Lync Server 2013: Lync Server에 대해 SQL Server 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure SQL Server for Lync Server 2013
ms:assetid: 375e5cc4-e436-46dc-9b02-5063f35cdcc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425848(v=OCS.15)
ms:contentKeyID: 48183869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0154b468540873f9b8ae6796f30336327809d394
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982887"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-for-lync-server-2013"></a>Lync Server 2013에 대해 SQL Server 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-08-12_

이 섹션의 항목에서는 Lync Server의 엔터프라이즈 배포에 사용할 SQL Server를 배포 하 고 구성 하는 방법에 대해 설명 합니다. Standard Edition 서버는 collocated SQL server Express 버전의 SQL Server를 사용 하며,이는 스탠더드 버전 서버의 작업 부하에 맞게 크기가 조정 됩니다.

Lync Server 2013 중앙 관리 저장소는 풀 내의 모든 Enterprise Edition 서버에 대 한 사용자 데이터를 보유 하 고 있으며 SQL Server 기반 백 엔드 서버에 위치 하도록 디자인 되었습니다. 중앙 집중화 된 저장소는 다른 Lync Server 2013 역할과 동일한 컴퓨터에 중앙 관리 저장소를 설치할 수 없습니다. 중앙 관리 저장소는 풀의 엔터프라이즈 버전 서버에 상주할 수 없습니다. 중앙 관리 저장소는 처음으로 토폴로지를 게시 하 고 데이터베이스를 만들기 위해 선택 하면 자동으로 만들어집니다. 백 엔드 서버로 지정 하는 컴퓨터는 설치를 완료 하기 위해 이미 SQL Server 데이터베이스 소프트웨어를 실행 중 이어야 합니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에 대한 SQL Server 데이터 및 로그 파일 배치](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [Lync Server 2013에서 SQL Server 구성](lync-server-2013-configure-sql-server.md)

  - [Lync Server 2013의 SQL Server에 대한 배포 권한](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [Lync Server 2013에서 Lync Server 관리 셸을 사용하여 데이터베이스 설치](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [Lync Server 2013의 SQL Server에 대한 방화벽 요구 사항 이해](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [Lync Server 2013 용 SQL Server 클러스터링 구성](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

