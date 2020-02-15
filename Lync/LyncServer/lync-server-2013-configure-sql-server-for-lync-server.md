---
title: 'Lync Server 2013: Lync Server에 대해 SQL Server 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server for Lync Server 2013
ms:assetid: 375e5cc4-e436-46dc-9b02-5063f35cdcc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425848(v=OCS.15)
ms:contentKeyID: 48183869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e52534744849e41fa08895bd114833892f4b8a2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-for-lync-server-2013"></a>Lync Server 2013에 대해 SQL Server 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-08-12_

이 섹션의 항목에서는 Lync Server의 엔터프라이즈 배포에서 사용할 SQL Server를 배포 하 고 구성 하는 방법을 설명 합니다. Standard Edition 서버는 Standard Edition server의 작업 부하를 위해 적절 한 크기를 가진 배치 된 SQL Server Express 버전의 SQL Server를 사용 합니다.

Lync Server 2013 중앙 관리 저장소는 풀 내의 모든 Enterprise Edition 서버에 대 한 사용자 데이터를 보유 하며, SQL Server 기반 백 엔드 서버에 배치 되도록 설계 되었습니다. 중앙 관리 저장소는 다른 Lync Server 2013 역할과 동일한 컴퓨터에 설치할 수 없습니다. 중앙 관리 저장소는 풀의 Enterprise Edition 서버에 상주할 수 없습니다. 처음으로 토폴로지를 게시 하 고 데이터베이스를 만들려면를 선택 하면 중앙 관리 저장소가 자동으로 만들어집니다. 백 엔드 서버로 지정 하는 컴퓨터는 설치에 성공 하기 위해 이미 SQL Server 데이터베이스 소프트웨어를 실행 중 이어야 합니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에 대 한 SQL Server 데이터 및 로그 파일 배치](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [Lync Server 2013에서 SQL Server 구성](lync-server-2013-configure-sql-server.md)

  - [Lync Server 2013의 SQL Server에 대 한 배포 권한](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [Lync Server 2013에서 Lync Server 관리 셸을 사용 하 여 데이터베이스 설치](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [Lync Server 2013을 사용 하 여 SQL Server에 대 한 방화벽 요구 사항 이해](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [Lync Server 2013에 대해 SQL Server 클러스터링 구성](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

