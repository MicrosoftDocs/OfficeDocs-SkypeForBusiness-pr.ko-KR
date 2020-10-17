---
title: Standard Edition 서버 배포의 Lync Server 2013 서버 배치
description: Lync Server 2013 Standard Edition 서버 배포의 서버 위치입니다.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in a Standard Edition server deployment
ms:assetid: 0763ffab-4fd6-463a-8e62-d97876b376d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398131(v=OCS.15)
ms:contentKeyID: 48183314
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af44761d36c472de1a3da5cd3b3938dc1a130836
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555114"
---
# <a name="server-collocation-in-a-standard-edition-server-deployment-for-lync-server-2013"></a><span data-ttu-id="02491-103">Lync Server 2013에 대 한 Standard Edition server 배포의 서버 배치</span><span class="sxs-lookup"><span data-stu-id="02491-103">Server collocation in a Standard Edition server deployment for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02491-104">_**마지막으로 수정 된 항목:** 2013-01-20_</span><span class="sxs-lookup"><span data-stu-id="02491-104">_**Topic Last Modified:** 2013-01-20_</span></span>

<span data-ttu-id="02491-105">이 섹션에서는 Lync Server 2013 Standard Edition server 배포에서 함께 배치할 수 있는 서버 역할, 데이터베이스 및 파일 공유에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="02491-105">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Standard Edition server deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="02491-106">서버 역할</span><span class="sxs-lookup"><span data-stu-id="02491-106">Server Roles</span></span>

<span data-ttu-id="02491-107">Lync Server 2013에서는 A/V 회의 서비스, 중재 서비스, 모니터링 및 보관을 Standard Edition Server에 배치 된, 사용 하도록 설정 하려면 추가 구성이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="02491-107">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Standard Edition Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="02491-108">중재 서비스는 별도의 서버에 배포하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02491-108">You can choose to deploy Mediation service on separate servers.</span></span>

<span data-ttu-id="02491-109">신뢰할 수 있는 응용 프로그램 서버를 Standard Edition 서버와 함께 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02491-109">You can collocate a trusted application server with a Standard Edition server.</span></span>

<span data-ttu-id="02491-110">다음 서버 역할을 각각의 개별 컴퓨터에 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02491-110">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="02491-111">Director</span><span class="sxs-lookup"><span data-stu-id="02491-111">Director</span></span>

  - <span data-ttu-id="02491-112">에지 서버</span><span class="sxs-lookup"><span data-stu-id="02491-112">Edge Server</span></span>

  - <span data-ttu-id="02491-113">중재 서버(Standard Edition 서버와 함께 배치되지 않은 경우)</span><span class="sxs-lookup"><span data-stu-id="02491-113">Mediation Server (if not collocated with the Standard Edition server)</span></span>

  - <span data-ttu-id="02491-114">Office Web Apps 서버</span><span class="sxs-lookup"><span data-stu-id="02491-114">Office Web Apps Server</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="02491-115">데이터베이스</span><span class="sxs-lookup"><span data-stu-id="02491-115">Databases</span></span>

<span data-ttu-id="02491-116">기본적으로 SQL Server Express 백 엔드 데이터베이스는 Standard Edition 서버에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="02491-116">By default, the SQL Server Express back-end database is collocated on the Standard Edition server.</span></span> <span data-ttu-id="02491-117">개별 컴퓨터로 이동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02491-117">You cannot move it to a separate computer.</span></span> <span data-ttu-id="02491-118">한 가지 예외를 제외 하면 Standard Edition 서버에서 다른 데이터베이스를 함께 배치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02491-118">With one exception, you cannot collocate other databases on the Standard Edition server.</span></span> <span data-ttu-id="02491-119">Standard Edition 서버에 영구 채팅 서버를 배포 하도록 선택한 경우 영구 채팅 데이터베이스 및 영구 채팅 준수 데이터베이스를 동일한 Standard Edition 서버에 함께 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02491-119">If you choose to deploy Persistent Chat Server on a Standard Edition server, you can collocate the Persistent chat database and the Persistent Chat Compliance database on the same Standard Edition server.</span></span>

<span data-ttu-id="02491-120">단일 데이터베이스 서버에 다음과 같은 각 데이터베이스를 함께 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02491-120">You can collocate each of the following databases on a single database server:</span></span>

  - <span data-ttu-id="02491-121">모니터링 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="02491-121">Monitoring database</span></span>

  - <span data-ttu-id="02491-122">보관 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="02491-122">Archiving database</span></span>

  - <span data-ttu-id="02491-123">Enterprise Edition 프런트 엔드 풀의 백 엔드 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="02491-123">A back-end database for an Enterprise Edition Front End pool</span></span>

<span data-ttu-id="02491-124">단일 SQL 인스턴스에서 이러한 모든 데이터베이스를 함께 배치하거나 각 데이터베이스에 대해 개별 SQL 인스턴스를 사용할 수 있지만 다음과 같은 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02491-124">You can collocate any or any or all of these databases in a single SQL instance or use a separate SQL instances for each, with the following limitations:</span></span>

  - <span data-ttu-id="02491-125">각 SQL 인스턴스는 단일 백 엔드 데이터베이스(Enterprise Edition 프런트 엔드 풀용), 단일 모니터링 데이터베이스, 단일 보관 데이터베이스, 단일 영구 채팅 데이터베이스 및 단일 영구 채팅 준수 데이터베이스만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02491-125">Each SQL instance can contain only a single back-end database (for an Enterprise Edition Front End pool), single Monitoring database, single Archiving database, single persistent chat database, and single persistent chat compliance database.</span></span>

  - <span data-ttu-id="02491-126">데이터베이스 서버는 두 개 이상의 Enterprise Edition 프런트 엔드 풀, 보관을 실행 하는 하나의 서버, 단일 영구 채팅 데이터베이스 및 단일 영구 채팅 준수 데이터베이스를 지원할 수 없지만 데이터베이스에 동일한 SQL Server 인스턴스 또는 개별 SQL Server 인스턴스가 사용 되는지 여부에 관계 없이 각 항목 중 하나를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02491-126">The database server cannot support more than one Enterprise Edition Front End pool, one server running Archiving, one server running Monitoring, single Persistent Chat database, and single Persistent Chat compliance database, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="02491-127">이 섹션의 뒷부분에서 설명하는 대로 파일 공유를 데이터베이스와 함께 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02491-127">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="02491-128">Lync Server 2013에서는 배포의 일부 또는 모든 사용자에 대해 모니터링 및 보관 저장소와 Exchange 2013 저장소를 통합 하는 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02491-128">In Lync Server 2013, you have the option of integrating Monitoring and Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="02491-129">Lync Server를 실행 하는 서버 또는 구성 요소는 Exchange 저장소와 동일한 서버에 배포할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02491-129">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="02491-130">데이터베이스 배치가 지원되기는 하지만, 데이터베이스는 크기가 빠르게 커질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02491-130">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="02491-131">예를 들어 보관 데이터베이스를 다른 데이터베이스와 함께 배치하도록 고려할 때 여러 사용자의 메시지를 보관하는 경우 보관 데이터베이스에 필요한 디스크 공간이 매우 커질 수 있음을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02491-131">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="02491-132">따라서 여러 데이터베이스, 특히 보관 데이터베이스, 영구 채팅 데이터베이스 및 영구 채팅 준수 데이터베이스를 엔터프라이즈 풀의 백 엔드 데이터베이스와 배치 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="02491-132">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, Persistent Chat database, and Persistent Chat compliance database with the back-end database of an Enterprise pool.</span></span>



</div>

</div>

<div>

## <a name="file-shares"></a><span data-ttu-id="02491-133">파일 공유</span><span class="sxs-lookup"><span data-stu-id="02491-133">File Shares</span></span>

<span data-ttu-id="02491-134">파일 공유는 개별 서버이거나 다음 중 일부 또는 전체와 동일한 서버에 배치될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02491-134">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="02491-135">Enterprise Edition 프런트 엔드 풀의 백 엔드 서버를 포함하는 데이터베이스 서버</span><span class="sxs-lookup"><span data-stu-id="02491-135">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="02491-136">보관 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="02491-136">Archiving database</span></span>

  - <span data-ttu-id="02491-137">모니터링 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="02491-137">Monitoring database</span></span>

  - <span data-ttu-id="02491-138">영구 채팅 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="02491-138">Persistent Chat database</span></span>

  - <span data-ttu-id="02491-139">영구 채팅 준수 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="02491-139">Persistent Chat compliance database</span></span>

<span data-ttu-id="02491-140">단일 파일 공유를 여러 프런트 엔드 풀 및 Standard Edition 서버(모두 동일 사이트에 포함됨)에 대해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02491-140">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="02491-141">Lync Server 2013에서 모니터링 및 보관은 Lync Server 파일 공유를 Standard Edition 서버로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="02491-141">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Standard Edition server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="02491-142">기타 구성 요소</span><span class="sxs-lookup"><span data-stu-id="02491-142">Other Components</span></span>

<span data-ttu-id="02491-143">Lync server 2013 서버 역할이 있는 페더레이션 사용자에 대해 웹 콘텐츠 공유를 지원 하려면 역방향 프록시 서버 2013를 함께 배치할 수는 없지만이 구성 요소는 배포에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="02491-143">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="02491-144">그러나 조직의 다른 응용 프로그램에 사용 되는 기존 역방향 프록시 서버에 대 한 지원을 구성 하 여 Lync Server 2013 배포에 대 한 역방향 프록시 지원을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02491-144">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="02491-145">모든 Lync Server 2013 역할을 사용 하 여 모든 Exchange UM 구성 요소 또는 SharePoint 구성 요소를 함께 배치할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02491-145">You cannot collocate any Exchange UM component or SharePoint component with any Lync Server 2013 role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

