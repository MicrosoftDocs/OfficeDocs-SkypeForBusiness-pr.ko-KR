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

# <a name="configure-sql-server-for-lync-server-2013"></a><span data-ttu-id="f1acb-102">Lync Server 2013에 대해 SQL Server 구성</span><span class="sxs-lookup"><span data-stu-id="f1acb-102">Configure SQL Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1acb-103">_**마지막으로 수정 된 항목:** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="f1acb-103">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="f1acb-104">이 섹션의 항목에서는 Lync Server의 엔터프라이즈 배포에서 사용할 SQL Server를 배포 하 고 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1acb-104">The topics in this section discuss how to deploy and configure SQL Server to use in an Enterprise deployment of Lync Server.</span></span> <span data-ttu-id="f1acb-105">Standard Edition 서버는 Standard Edition server의 작업 부하를 위해 적절 한 크기를 가진 배치 된 SQL Server Express 버전의 SQL Server를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1acb-105">Standard Edition servers use a collocated SQL Server Express version of SQL Server that is right sized for the workloads of a Standard Edition server.</span></span>

<span data-ttu-id="f1acb-106">Lync Server 2013 중앙 관리 저장소는 풀 내의 모든 Enterprise Edition 서버에 대 한 사용자 데이터를 보유 하며, SQL Server 기반 백 엔드 서버에 배치 되도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f1acb-106">The Lync Server 2013 Central Management store holds user data for all Enterprise Edition servers within a pool, and is designed to be located on a SQL Server -based Back End Server.</span></span> <span data-ttu-id="f1acb-107">중앙 관리 저장소는 다른 Lync Server 2013 역할과 동일한 컴퓨터에 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f1acb-107">As a centralized repository, the Central Management store cannot be installed on the same computer as any other Lync Server 2013 role.</span></span> <span data-ttu-id="f1acb-108">중앙 관리 저장소는 풀의 Enterprise Edition 서버에 상주할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f1acb-108">The Central Management store cannot reside on an Enterprise Edition server in the pool.</span></span> <span data-ttu-id="f1acb-109">처음으로 토폴로지를 게시 하 고 데이터베이스를 만들려면를 선택 하면 중앙 관리 저장소가 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="f1acb-109">The Central Management store is created automatically when you publish the topology for the first time and select to create the databases.</span></span> <span data-ttu-id="f1acb-110">백 엔드 서버로 지정 하는 컴퓨터는 설치에 성공 하기 위해 이미 SQL Server 데이터베이스 소프트웨어를 실행 중 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1acb-110">The computer that you designate as the Back End Server must already be running SQL Server database software in order for the installation to succeed.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f1acb-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="f1acb-111">In This Section</span></span>

  - [<span data-ttu-id="f1acb-112">Lync Server 2013에 대 한 SQL Server 데이터 및 로그 파일 배치</span><span class="sxs-lookup"><span data-stu-id="f1acb-112">SQL Server data and log file placement for Lync Server 2013</span></span>](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [<span data-ttu-id="f1acb-113">Lync Server 2013에서 SQL Server 구성</span><span class="sxs-lookup"><span data-stu-id="f1acb-113">Configure SQL Server in Lync Server 2013</span></span>](lync-server-2013-configure-sql-server.md)

  - [<span data-ttu-id="f1acb-114">Lync Server 2013의 SQL Server에 대 한 배포 권한</span><span class="sxs-lookup"><span data-stu-id="f1acb-114">Deployment permissions for SQL Server in Lync Server 2013</span></span>](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [<span data-ttu-id="f1acb-115">Lync Server 2013에서 Lync Server 관리 셸을 사용 하 여 데이터베이스 설치</span><span class="sxs-lookup"><span data-stu-id="f1acb-115">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [<span data-ttu-id="f1acb-116">Lync Server 2013을 사용 하 여 SQL Server에 대 한 방화벽 요구 사항 이해</span><span class="sxs-lookup"><span data-stu-id="f1acb-116">Understanding firewall requirements for SQL Server with Lync Server 2013</span></span>](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [<span data-ttu-id="f1acb-117">Lync Server 2013에 대해 SQL Server 클러스터링 구성</span><span class="sxs-lookup"><span data-stu-id="f1acb-117">Configure SQL Server clustering for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

