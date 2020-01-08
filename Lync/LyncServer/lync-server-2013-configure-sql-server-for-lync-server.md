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

# <a name="configure-sql-server-for-lync-server-2013"></a><span data-ttu-id="36b3f-102">Lync Server 2013에 대해 SQL Server 구성</span><span class="sxs-lookup"><span data-stu-id="36b3f-102">Configure SQL Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36b3f-103">_**마지막으로 수정한 주제:** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="36b3f-103">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="36b3f-104">이 섹션의 항목에서는 Lync Server의 엔터프라이즈 배포에 사용할 SQL Server를 배포 하 고 구성 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="36b3f-104">The topics in this section discuss how to deploy and configure SQL Server to use in an Enterprise deployment of Lync Server.</span></span> <span data-ttu-id="36b3f-105">Standard Edition 서버는 collocated SQL server Express 버전의 SQL Server를 사용 하며,이는 스탠더드 버전 서버의 작업 부하에 맞게 크기가 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36b3f-105">Standard Edition servers use a collocated SQL Server Express version of SQL Server that is right sized for the workloads of a Standard Edition server.</span></span>

<span data-ttu-id="36b3f-106">Lync Server 2013 중앙 관리 저장소는 풀 내의 모든 Enterprise Edition 서버에 대 한 사용자 데이터를 보유 하 고 있으며 SQL Server 기반 백 엔드 서버에 위치 하도록 디자인 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="36b3f-106">The Lync Server 2013 Central Management store holds user data for all Enterprise Edition servers within a pool, and is designed to be located on a SQL Server -based Back End Server.</span></span> <span data-ttu-id="36b3f-107">중앙 집중화 된 저장소는 다른 Lync Server 2013 역할과 동일한 컴퓨터에 중앙 관리 저장소를 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36b3f-107">As a centralized repository, the Central Management store cannot be installed on the same computer as any other Lync Server 2013 role.</span></span> <span data-ttu-id="36b3f-108">중앙 관리 저장소는 풀의 엔터프라이즈 버전 서버에 상주할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36b3f-108">The Central Management store cannot reside on an Enterprise Edition server in the pool.</span></span> <span data-ttu-id="36b3f-109">중앙 관리 저장소는 처음으로 토폴로지를 게시 하 고 데이터베이스를 만들기 위해 선택 하면 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="36b3f-109">The Central Management store is created automatically when you publish the topology for the first time and select to create the databases.</span></span> <span data-ttu-id="36b3f-110">백 엔드 서버로 지정 하는 컴퓨터는 설치를 완료 하기 위해 이미 SQL Server 데이터베이스 소프트웨어를 실행 중 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36b3f-110">The computer that you designate as the Back End Server must already be running SQL Server database software in order for the installation to succeed.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="36b3f-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="36b3f-111">In This Section</span></span>

  - [<span data-ttu-id="36b3f-112">Lync Server 2013에 대한 SQL Server 데이터 및 로그 파일 배치</span><span class="sxs-lookup"><span data-stu-id="36b3f-112">SQL Server data and log file placement for Lync Server 2013</span></span>](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [<span data-ttu-id="36b3f-113">Lync Server 2013에서 SQL Server 구성</span><span class="sxs-lookup"><span data-stu-id="36b3f-113">Configure SQL Server in Lync Server 2013</span></span>](lync-server-2013-configure-sql-server.md)

  - [<span data-ttu-id="36b3f-114">Lync Server 2013의 SQL Server에 대한 배포 권한</span><span class="sxs-lookup"><span data-stu-id="36b3f-114">Deployment permissions for SQL Server in Lync Server 2013</span></span>](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [<span data-ttu-id="36b3f-115">Lync Server 2013에서 Lync Server 관리 셸을 사용하여 데이터베이스 설치</span><span class="sxs-lookup"><span data-stu-id="36b3f-115">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [<span data-ttu-id="36b3f-116">Lync Server 2013의 SQL Server에 대한 방화벽 요구 사항 이해</span><span class="sxs-lookup"><span data-stu-id="36b3f-116">Understanding firewall requirements for SQL Server with Lync Server 2013</span></span>](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [<span data-ttu-id="36b3f-117">Lync Server 2013 용 SQL Server 클러스터링 구성</span><span class="sxs-lookup"><span data-stu-id="36b3f-117">Configure SQL Server clustering for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

