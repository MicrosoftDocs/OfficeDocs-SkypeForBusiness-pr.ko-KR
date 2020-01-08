---
title: 'Lync Server 2013: 지원되는 서버 마이그레이션 경로 및 동시 사용 시나리오'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported server migration paths and coexistence scenarios
ms:assetid: 2a6a730f-7f80-45f9-9540-3edfdaa265fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425764(v=OCS.15)
ms:contentKeyID: 48183686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33b2ce878fef53f444e3834e8b1cd40286c24b0e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984514"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-server-migration-paths-and-coexistence-scenarios-in-lync-server-2013"></a><span data-ttu-id="de60d-102">Lync Server 2013의 지원되는 서버 마이그레이션 경로 및 동시 사용 시나리오</span><span class="sxs-lookup"><span data-stu-id="de60d-102">Supported server migration paths and coexistence scenarios in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de60d-103">_**마지막으로 수정한 주제:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="de60d-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="de60d-104">Lync Server 2013는 다음 중 한 가지 방법으로 마이그레이션을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="de60d-104">Lync Server 2013 supports migration from either of the following:</span></span>

  - <span data-ttu-id="de60d-105">Microsoft Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="de60d-105">Microsoft Lync Server 2010</span></span>

  - <span data-ttu-id="de60d-106">Microsoft Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="de60d-106">Microsoft Office Communications Server 2007 R2</span></span>

<span data-ttu-id="de60d-107">이러한 이전 버전을 모두 실행 하는 환경에서 마이그레이션하는 것은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="de60d-107">Migration from an environment running both of these previous versions is not supported.</span></span> <span data-ttu-id="de60d-108">Microsoft Office Communications Server 2007 또는 Live Communications Server 2005 등 이전 버전에서의 마이그레이션은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="de60d-108">Migration from earlier versions, such as Microsoft Office Communications Server 2007 or Live Communications Server 2005, is not supported.</span></span> <span data-ttu-id="de60d-109">이전 배포에 그룹 채팅이 포함 된 경우 별도로 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de60d-109">If your previous deployment included Group Chat, you must migrate it separately.</span></span>

<div>

## <a name="migration-methods"></a><span data-ttu-id="de60d-110">마이그레이션 방법</span><span class="sxs-lookup"><span data-stu-id="de60d-110">Migration Methods</span></span>

<span data-ttu-id="de60d-111">모든 Lync Server 토폴로지 및 서버 역할의 마이그레이션이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de60d-111">Migration of all Lync Server topologies and server roles is supported.</span></span> <span data-ttu-id="de60d-112">표준 버전 서버와 Enterprise Edition server를 포함 하 여 한 토폴로지에서 다른 토폴로지로 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de60d-112">You can migrate from one topology to a different topology, including from Standard Edition server to Enterprise Edition server.</span></span>

<span data-ttu-id="de60d-113">Lync 서버 2013는 다음 마이그레이션 메서드만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="de60d-113">Lync Server 2013 supports only the following migration method:</span></span>

  - <span></span>  
    <span data-ttu-id="de60d-114">**나란히 마이그레이션.**</span><span class="sxs-lookup"><span data-stu-id="de60d-114">**Side-by-side migration.**</span></span> <span data-ttu-id="de60d-115">병렬 마이그레이션에서는 Lync Server 2013이 기존 Microsoft Lync Server 2010 또는 Office Communications Server 2007 R2 배포와 함께 배포 된 다음 새 서버로 작업을 전송 하 고 사용자를 Lync Server 2013로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="de60d-115">In side-by-side migration, Lync Server 2013 is deployed alongside an existing Microsoft Lync Server 2010 or Office Communications Server 2007 R2 deployment, and then you transfer operations to the new servers and move users to Lync Server 2013.</span></span> <span data-ttu-id="de60d-116">이 방법을 사용 하려면 마이그레이션 도중 하드웨어 및 소프트웨어를 비롯 한 추가 서버 플랫폼 및 시스템 이름 및 풀 이름이 새 구성에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="de60d-116">This method requires additional server platforms, including hardware and software, during migration, and system names and pool names are different in the new configuration.</span></span> <span data-ttu-id="de60d-117">이전 버전으로 롤백하는 데 필요한 경우 이전 서버로 작업을 다시 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de60d-117">If it becomes necessary to roll back to the previous version, you can shift operations back to the previous servers.</span></span>

<span data-ttu-id="de60d-118">Active Directory 도메인 서비스 포리스트 간 마이그레이션은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="de60d-118">Migration across Active Directory Domain Services forests is not supported.</span></span>

<span data-ttu-id="de60d-119">권장 되는 마이그레이션 경로는 단계별 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="de60d-119">The recommended migration path is a phased approach.</span></span> <span data-ttu-id="de60d-120">구성 요소 배포의 적절 한 단계을 포함 하 여 이전 릴리스에서 마이그레이션하는 방법에 대 한 자세한 내용은 마이그레이션 설명서의 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="de60d-120">For details about migrating from a previous release, including the appropriate phasing of component deployment, see the following topics in the Migration documentation:</span></span>

  - [<span data-ttu-id="de60d-121">Lync Server 2010에서 Lync Server 2013으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="de60d-121">Migration from Lync Server 2010 to Lync Server 2013</span></span>](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [<span data-ttu-id="de60d-122">Office Communications Server 2007 R2에서 Lync Server 2013으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="de60d-122">Migration from Office Communications Server 2007 R2 to Lync Server 2013</span></span>](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [<span data-ttu-id="de60d-123">Lync Server 2010, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅에서 Lync Server 2013, 영구 채팅 서버로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="de60d-123">Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server</span></span>](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

</div>

<span id="BKMK_PhasedMigration"></span>

<div>

## <a name="coexistence-scenarios"></a><span data-ttu-id="de60d-124">공존 시나리오</span><span class="sxs-lookup"><span data-stu-id="de60d-124">Coexistence Scenarios</span></span>

<span data-ttu-id="de60d-125">Lync Server 2013는 Lync Server 2010 배포 또는 Office Communications Server 2007 R2 배포의 구성 요소와 공존할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de60d-125">Lync Server 2013 can coexist with components of either a Lync Server 2010 deployment or an Office Communications Server 2007 R2 deployment.</span></span> <span data-ttu-id="de60d-126">Lync Server 2010 및 Office Communications Server 2007 R2를 둘 다 사용 하 여 Lync Server 2013을 동시에 배포할 수 있습니다 (모든 세 버전의 동시 배포).</span><span class="sxs-lookup"><span data-stu-id="de60d-126">Concurrent deployment of Lync Server 2013 with both Lync Server 2010 and Office Communications Server 2007 R2 (concurrent deployment of all three versions) is not supported.</span></span>

<span data-ttu-id="de60d-127">이전 Lync Server 2010 또는 Office Communications Server 2007 R2 배포가 일시적으로 새 Lync Server 2013 배포를 사용 하 여 진행 되는 동안에는 혼합 버전 라우팅에 대 한 지원이 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de60d-127">During a phased migration in which a previous Lync Server 2010 or Office Communications Server 2007 R2 deployment coexists temporarily with the new Lync Server 2013 deployment, support for mixed version routing is limited.</span></span> <span data-ttu-id="de60d-128">자세한 내용은 마이그레이션 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="de60d-128">For details, see the Migration documentation.</span></span>

<span data-ttu-id="de60d-129">Lync Server 2013 데이터베이스 인스턴스에 대해 Microsoft SQL Server 2008 R2 또는 Microsoft SQL Server 2012를 실행 하는 별개의 컴퓨터를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de60d-129">You must use separate and distinct computers running Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 for your Lync Server 2013 database instances.</span></span> <span data-ttu-id="de60d-130">Lync server 2010 또는 Office Communications Server 2007 R2 프런트 엔드 풀에 사용 하는 Lync Server 2013 프런트 엔드 풀에 대해서도 동일한 SQL Server 인스턴스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de60d-130">You cannot use the same instance of SQL Server for a Lync Server 2013 Front End pool that you use for a Lync Server 2010 or Office Communications Server 2007 R2 Front End pool.</span></span> <span data-ttu-id="de60d-131">Lync server 2010 또는 Office Communications Server 2007 R2가 배포 된 배포에 대 한 토폴로지 작성기에서 Lync Server 2013을 정의 하 고 구성 하는 경우에는 토폴로지 작성기를 통해 이미 사용 중인 Lync Server 2013의 인스턴스를 정의할 수 없습니다. 토폴로지.</span><span class="sxs-lookup"><span data-stu-id="de60d-131">If you define and configure Lync Server 2013 in Topology Builder for a deployment that already has Lync Server 2010 or Office Communications Server 2007 R2 deployed, Topology Builder will not allow you to define an instance of a Lync Server 2013 that is already in use in the topology.</span></span>

<span data-ttu-id="de60d-132">토폴로지 작성기에는 "서버의 \[\] SQL server FQDN에 sql 인스턴스 호스팅 역할 ' 사용자 저장소가 이미 포함 되어 있습니다." 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de60d-132">Topology Builder will display the following message to inform you of this issue: "The SQL server \[FQDN of the server\] already contains a SQL instance hosting role 'User Store'."</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="de60d-133">Lync Server 2013 배포에 새로운 서버 역할을 배포 하려는 경우 먼저 마이그레이션 설명서 및 배포 설명서에 설명 된 대로 기존 배포를 업그레이드 한 다음 아래에 설명 된 대로 새 서버 역할을 배포 해야 합니다. 계획 문서 및 배포 설명서입니다.</span><span class="sxs-lookup"><span data-stu-id="de60d-133">If you intend to deploy server roles that are new to your Lync Server 2013 deployment, you should first upgrade your existing deployment as described in the Migration documentation and the Deployment documentation, and then deploy the new server roles as described in the Planning documentation and Deployment documentation.</span></span> <span data-ttu-id="de60d-134">이전 버전의 그룹 채팅을 마이그레이션하는 경우 Lync Server 2010 또는 Office Communications Server 2007 R2의 다른 모든 구성 요소 마이그레이션 프로세스를 완료 한 후에 마지막으로 마이그레이션하십시오.</span><span class="sxs-lookup"><span data-stu-id="de60d-134">If you are migrating a previous version of Group Chat, migrate it last, after completing the process for migrating all other components from Lync Server 2010 or Office Communications Server 2007 R2.</span></span>



</div>

<span data-ttu-id="de60d-135">Lync Server 2010 또는 Office Communications Server 2007 R2 및 Lync Server 2013 구성 요소의 공존 및 마이그레이션에 대 한 자세한 공존 요구 사항 및 기타 자세한 내용은 마이그레이션 설명서의 [Lync server 2010에서 Lync server 2013로 마이그레이션](migration-from-lync-server-2010-to-lync-server-2013.md) 및 [Office Communications server 2007 R2에서 lync Server로의 마이그레이션을](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="de60d-135">For specific coexistence requirements and other details about coexistence and migration of Lync Server 2010 or Office Communications Server 2007 R2 and Lync Server 2013 components, see [Migration from Lync Server 2010 to Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) and [Migration from Office Communications Server 2007 R2 to Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) in the Migration documentation.</span></span> <span data-ttu-id="de60d-136">클라이언트의 혼합 버전 지원에 대 한 자세한 내용은 [Lync Server 2013의 이전 배포에서 지원 되는 클라이언트](lync-server-2013-supported-clients-from-previous-deployments.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="de60d-136">For details about mixed version support for clients, see [Supported clients from previous deployments in Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

