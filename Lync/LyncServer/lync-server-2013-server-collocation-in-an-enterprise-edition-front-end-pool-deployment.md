---
title: Enterprise Edition 프런트 엔드 풀 배포의 Lync server 2013 Server 배치
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in an Enterprise Edition Front End pool deployment
ms:assetid: 0516b18d-14c0-4237-9279-0f92e341b1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398102(v=OCS.15)
ms:contentKeyID: 48183287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0162a4338a1504ed425015e5b9391fca9903d4ab
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510285"
---
# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a><span data-ttu-id="41ff5-102">Lync Server 2013에 대 한 Enterprise Edition 프런트 엔드 풀 배포의 서버 배치</span><span class="sxs-lookup"><span data-stu-id="41ff5-102">Server collocation in an Enterprise Edition Front End pool deployment for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41ff5-103">_**마지막으로 수정 된 항목:** 2013-11-11_</span><span class="sxs-lookup"><span data-stu-id="41ff5-103">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="41ff5-104">이 섹션에서는 Lync Server 2013 프런트 엔드 풀 배포에서 함께 배치할 수 있는 서버 역할, 데이터베이스 및 파일 공유에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="41ff5-104">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Front End pool deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="41ff5-105">서버 역할</span><span class="sxs-lookup"><span data-stu-id="41ff5-105">Server Roles</span></span>

<span data-ttu-id="41ff5-106">Lync Server 2013에서 A/V 회의 서비스, 중재 서비스, 모니터링 및 보관은 프런트 엔드 서버에서 배치 된, 사용 하도록 설정 하기 위해 추가 구성이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="41ff5-106">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Front End Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="41ff5-107">중재 서버를 프런트 엔드 서버와 함께 배치하지 않으려면 별도의 컴퓨터에 독립 실행형 중재 서버로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41ff5-107">If you do not want to collocate the Mediation Server with the Front End Server, you can deploy it as a stand-alone Mediation Server on a separate computer.</span></span>

<span data-ttu-id="41ff5-108">신뢰할 수 있는 응용 프로그램 서버를 프런트 엔드 서버와 함께 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41ff5-108">You can collocate a trusted application server with the Front End Server.</span></span>

<span data-ttu-id="41ff5-109">다음 서버 역할을 각각의 개별 컴퓨터에 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41ff5-109">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="41ff5-110">Director</span><span class="sxs-lookup"><span data-stu-id="41ff5-110">Director</span></span>

  - <span data-ttu-id="41ff5-111">에지 서버</span><span class="sxs-lookup"><span data-stu-id="41ff5-111">Edge Server</span></span>

  - <span data-ttu-id="41ff5-112">중재 서버(프런트 엔드 서버와 함께 배치되지 않은 경우)</span><span class="sxs-lookup"><span data-stu-id="41ff5-112">Mediation Server (if not collocated with the Front End Server)</span></span>

  - <span data-ttu-id="41ff5-113">Office Web Apps 서버</span><span class="sxs-lookup"><span data-stu-id="41ff5-113">Office Web Apps Server</span></span>

<span data-ttu-id="41ff5-114">영구 채팅 서버 역할을 프런트 엔드 서버와 함께 배치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41ff5-114">You cannot collocate Persistent Chat server role with the Front End Server.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="41ff5-115">데이터베이스</span><span class="sxs-lookup"><span data-stu-id="41ff5-115">Databases</span></span>

<span data-ttu-id="41ff5-116">동일한 데이터베이스 서버에 다음과 같은 각 데이터베이스를 함께 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41ff5-116">You can collocate each of the following databases on the same database server:</span></span>

  - <span data-ttu-id="41ff5-117">백 엔드 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="41ff5-117">Back-end database</span></span>

  - <span data-ttu-id="41ff5-118">모니터링 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="41ff5-118">Monitoring database</span></span>

  - <span data-ttu-id="41ff5-119">보관 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="41ff5-119">Archiving database</span></span>

  - <span data-ttu-id="41ff5-120">영구 채팅 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="41ff5-120">Persistent Chat database</span></span>

  - <span data-ttu-id="41ff5-121">영구 채팅 준수 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="41ff5-121">Persistent Chat compliance database</span></span>

<span data-ttu-id="41ff5-122">다음 제한 사항을 사용 하 여 단일 SQL Server 인스턴스에 이러한 데이터베이스 중 일부 또는 전부 또는 일부 또는 전체를 함께 배치할 하거나 개별 SQL Server 인스턴스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41ff5-122">You can collocate any or any or all of these databases in a single instance of SQL Server or use a separate instance of SQL Server for each, with the following limitations:</span></span>

  - <span data-ttu-id="41ff5-123">각 SQL Server 인스턴스는 단일 백 엔드 데이터베이스, 단일 모니터링 데이터베이스, 단일 보관 데이터베이스, 단일 영구 채팅 데이터베이스 및 단일 영구 채팅 준수 데이터베이스만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41ff5-123">Each instance of SQL Server can contain only a single back-end database, a single Monitoring database, a single Archiving database, a single Persistent Chat database, and a single Persistent Chat compliance database.</span></span>

  - <span data-ttu-id="41ff5-124">데이터베이스 서버는 두 개 이상의 프런트 엔드 풀, 보관 배포 및 모니터링 배포를 지원할 수 없지만 데이터베이스에 동일한 SQL Server 인스턴스 또는 별도의 SQL Server 인스턴스가 사용 되는지 여부에 관계 없이 각 항목 중 하나를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41ff5-124">The database server cannot support more than one Front End pool, one Archiving deployment, and one Monitoring deployment, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="41ff5-125">이 섹션의 뒷부분에서 설명하는 대로 파일 공유를 데이터베이스와 함께 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41ff5-125">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="41ff5-126">Lync Server 2013에서는 배포의 일부 또는 모든 사용자에 대해 보관 저장소를 Exchange 2013 저장소와 통합 하는 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41ff5-126">In Lync Server 2013, you have the option of integrating Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="41ff5-127">Lync Server를 실행 하는 서버 또는 구성 요소는 Exchange 저장소와 동일한 서버에 배포할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41ff5-127">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="41ff5-128">데이터베이스 배치가 지원되기는 하지만, 데이터베이스는 크기가 빠르게 커질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41ff5-128">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="41ff5-129">예를 들어 보관 데이터베이스를 다른 데이터베이스와 함께 배치하도록 고려할 때 여러 사용자의 메시지를 보관하는 경우 보관 데이터베이스에 필요한 디스크 공간이 매우 커질 수 있음을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41ff5-129">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="41ff5-130">따라서 여러 데이터베이스, 특히 보관 데이터베이스, 영구 채팅 데이터베이스 또는 백 엔드 데이터베이스와의 영구 채팅 준수 데이터베이스를 배치 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="41ff5-130">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, the Persistent Chat database, or the Persistent Chat compliance database with the back-end database.</span></span>



</div>

</div>

<div>

## <a name="file-share"></a><span data-ttu-id="41ff5-131">파일 공유</span><span class="sxs-lookup"><span data-stu-id="41ff5-131">File Share</span></span>

<span data-ttu-id="41ff5-132">파일 공유는 개별 서버이거나 다음 중 일부 또는 전체와 동일한 서버에 배치될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41ff5-132">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="41ff5-133">Enterprise Edition 프런트 엔드 풀의 백 엔드 서버를 포함하는 데이터베이스 서버</span><span class="sxs-lookup"><span data-stu-id="41ff5-133">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="41ff5-134">보관 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="41ff5-134">Archiving database</span></span>

  - <span data-ttu-id="41ff5-135">모니터링 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="41ff5-135">Monitoring database</span></span>

  - <span data-ttu-id="41ff5-136">영구 채팅 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="41ff5-136">Persistent Chat database</span></span>

  - <span data-ttu-id="41ff5-137">영구 채팅 준수 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="41ff5-137">Persistent Chat compliance database</span></span>

<span data-ttu-id="41ff5-138">단일 파일 공유를 여러 프런트 엔드 풀 및 Standard Edition 서버(모두 동일 사이트에 포함됨)에 대해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41ff5-138">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="41ff5-139">Lync Server 2013에서 모니터링 및 보관은 Lync Server 파일 공유를 프런트 엔드 서버로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="41ff5-139">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Front End Server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="41ff5-140">기타 구성 요소</span><span class="sxs-lookup"><span data-stu-id="41ff5-140">Other Components</span></span>

<span data-ttu-id="41ff5-141">Lync server 2013 서버 역할이 있는 페더레이션 사용자에 대해 웹 콘텐츠 공유를 지원 하려면 역방향 프록시 서버 2013를 함께 배치할 수는 없지만이 구성 요소는 배포에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="41ff5-141">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="41ff5-142">그러나 조직의 다른 응용 프로그램에 사용 되는 기존 역방향 프록시 서버에 대 한 지원을 구성 하 여 Lync Server 2013 배포에 대 한 역방향 프록시 지원을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41ff5-142">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="41ff5-143">모든 SharePoint Server 역할을 사용 하 여 모든 Exchange UM (통합 메시징) 구성 요소 또는 SharePoint 구성 요소를 함께 배치할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41ff5-143">You cannot collocate any Exchange Unified Messaging (UM) component or SharePoint component with any SharePoint Server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

