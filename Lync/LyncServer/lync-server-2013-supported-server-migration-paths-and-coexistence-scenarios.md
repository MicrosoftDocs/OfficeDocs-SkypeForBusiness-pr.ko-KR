---
title: 'Lync Server 2013: 지원 되는 서버 마이그레이션 경로 및 동시 사용 시나리오'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported server migration paths and coexistence scenarios
ms:assetid: 2a6a730f-7f80-45f9-9540-3edfdaa265fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425764(v=OCS.15)
ms:contentKeyID: 48183686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ed7689931cf917c77527266918832ead8bd0a27
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523975"
---
# <a name="supported-server-migration-paths-and-coexistence-scenarios-in-lync-server-2013"></a><span data-ttu-id="182fc-102">Lync Server 2013의 지원 되는 서버 마이그레이션 경로 및 동시 사용 시나리오</span><span class="sxs-lookup"><span data-stu-id="182fc-102">Supported server migration paths and coexistence scenarios in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="182fc-103">_**마지막으로 수정 된 항목:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="182fc-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="182fc-104">Lync Server 2013에서는 다음 중 하나를 통해 마이그레이션을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="182fc-104">Lync Server 2013 supports migration from either of the following:</span></span>

  - <span data-ttu-id="182fc-105">Microsoft Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="182fc-105">Microsoft Lync Server 2010</span></span>

  - <span data-ttu-id="182fc-106">Microsoft Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="182fc-106">Microsoft Office Communications Server 2007 R2</span></span>

<span data-ttu-id="182fc-107">이 두 이전 버전을 모두 실행하는 환경으로부터의 마이그레이션은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="182fc-107">Migration from an environment running both of these previous versions is not supported.</span></span> <span data-ttu-id="182fc-108">Microsoft Office Communications Server 2007 또는 Live Communications Server 2005과 같은 이전 버전에서 마이그레이션하는 것은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="182fc-108">Migration from earlier versions, such as Microsoft Office Communications Server 2007 or Live Communications Server 2005, is not supported.</span></span> <span data-ttu-id="182fc-109">이전 배포에 그룹 채팅이 포함 된 경우 별도로 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="182fc-109">If your previous deployment included Group Chat, you must migrate it separately.</span></span>

<div>

## <a name="migration-methods"></a><span data-ttu-id="182fc-110">마이그레이션 방법</span><span class="sxs-lookup"><span data-stu-id="182fc-110">Migration Methods</span></span>

<span data-ttu-id="182fc-111">모든 Lync Server 토폴로지 및 서버 역할의 마이그레이션이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="182fc-111">Migration of all Lync Server topologies and server roles is supported.</span></span> <span data-ttu-id="182fc-112">Standard Edition 서버에서 Enterprise Edition 서버로의 마이그레이션을 포함하여 토폴로지 간 마이그레이션이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="182fc-112">You can migrate from one topology to a different topology, including from Standard Edition server to Enterprise Edition server.</span></span>

<span data-ttu-id="182fc-113">Lync Server 2013에서는 다음 마이그레이션 메서드만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="182fc-113">Lync Server 2013 supports only the following migration method:</span></span>

  - <span></span>  
    <span data-ttu-id="182fc-114">**병행 마이그레이션**</span><span class="sxs-lookup"><span data-stu-id="182fc-114">**Side-by-side migration.**</span></span> <span data-ttu-id="182fc-115">병렬 마이그레이션에서는 Lync Server 2013이 기존 Microsoft Lync Server 2010 또는 Office Communications Server 2007 R2 배포와 함께 배포 된 다음, 작업을 새 서버로 전송 하 고 사용자를 Lync Server 2013로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="182fc-115">In side-by-side migration, Lync Server 2013 is deployed alongside an existing Microsoft Lync Server 2010 or Office Communications Server 2007 R2 deployment, and then you transfer operations to the new servers and move users to Lync Server 2013.</span></span> <span data-ttu-id="182fc-116">이 방법을 사용 하려면 마이그레이션 중에 하드웨어 및 소프트웨어를 비롯 한 추가 서버 플랫폼이 필요 하며, 새 구성에서는 시스템 이름과 풀 이름이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="182fc-116">This method requires additional server platforms, including hardware and software, during migration, and system names and pool names are different in the new configuration.</span></span> <span data-ttu-id="182fc-117">이전 버전으로 롤백하는 데 필요한 경우 작업을 이전 서버로 다시 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="182fc-117">If it becomes necessary to roll back to the previous version, you can shift operations back to the previous servers.</span></span>

<span data-ttu-id="182fc-118">Active Directory 도메인 서비스 포리스트를 통한 마이그레이션은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="182fc-118">Migration across Active Directory Domain Services forests is not supported.</span></span>

<span data-ttu-id="182fc-p104">권장 마이그레이션 경로는 단계적 마이그레이션입니다. 적절한 구성 요소 배포 단계 지정을 비롯하여, 이전 릴리스에서 마이그레이션하는 방법에 대한 자세한 내용은 마이그레이션 설명서에서 다음 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="182fc-p104">The recommended migration path is a phased approach. For details about migrating from a previous release, including the appropriate phasing of component deployment, see the following topics in the Migration documentation:</span></span>

  - [<span data-ttu-id="182fc-121">Lync Server 2010에서 Lync Server 2013로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="182fc-121">Migration from Lync Server 2010 to Lync Server 2013</span></span>](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [<span data-ttu-id="182fc-122">Office Communications Server 2007 R2에서 Lync Server 2013으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="182fc-122">Migration from Office Communications Server 2007 R2 to Lync Server 2013</span></span>](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [<span data-ttu-id="182fc-123">Lync Server 2013, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅에서 Lync Server 2013, 영구 채팅 서버로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="182fc-123">Migration from Lync Server 2010, Group Chat or Office Communications Server 2007 R2 Group Chat to Lync Server 2013, Persistent Chat Server</span></span>](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

</div>

<span id="BKMK_PhasedMigration"></span>

<div>

## <a name="coexistence-scenarios"></a><span data-ttu-id="182fc-124">동시 사용 시나리오</span><span class="sxs-lookup"><span data-stu-id="182fc-124">Coexistence Scenarios</span></span>

<span data-ttu-id="182fc-125">Lync Server 2013는 Lync Server 2010 배포 또는 Office Communications Server 2007 R2 배포의 구성 요소와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="182fc-125">Lync Server 2013 can coexist with components of either a Lync Server 2010 deployment or an Office Communications Server 2007 R2 deployment.</span></span> <span data-ttu-id="182fc-126">Lync server 2010 및 Office Communications Server 2007 r 2를 모두 사용 하는 Lync Server 2013의 동시 배포 (세 가지 버전을 모두 동시에 배포)는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="182fc-126">Concurrent deployment of Lync Server 2013 with both Lync Server 2010 and Office Communications Server 2007 R2 (concurrent deployment of all three versions) is not supported.</span></span>

<span data-ttu-id="182fc-127">이전 Lync server 2010 또는 Office Communications Server 2007 R2 배포가 새로운 Lync Server 2013 배포와 함께 일시적으로 존재 하는 단계적 마이그레이션 중에는 혼합 버전 라우팅에 대 한 지원이 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="182fc-127">During a phased migration in which a previous Lync Server 2010 or Office Communications Server 2007 R2 deployment coexists temporarily with the new Lync Server 2013 deployment, support for mixed version routing is limited.</span></span> <span data-ttu-id="182fc-128">자세한 내용은 마이그레이션 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="182fc-128">For details, see the Migration documentation.</span></span>

<span data-ttu-id="182fc-129">Lync Server 2013 데이터베이스 인스턴스에 대해 Microsoft SQL Server 2008 R2 또는 Microsoft SQL Server 2012을 실행 하는 별도의 컴퓨터를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="182fc-129">You must use separate and distinct computers running Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 for your Lync Server 2013 database instances.</span></span> <span data-ttu-id="182fc-130">Lync server 2010 또는 Office Communications Server 2007 R2 프런트 엔드 풀에 사용 하는 Lync Server 2013 프런트 엔드 풀에 대해서는 동일한 SQL Server 인스턴스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="182fc-130">You cannot use the same instance of SQL Server for a Lync Server 2013 Front End pool that you use for a Lync Server 2010 or Office Communications Server 2007 R2 Front End pool.</span></span> <span data-ttu-id="182fc-131">Lync server 2010 또는 Office Communications Server 2007 R2가 배포 된 배포에 대해 토폴로지 작성기에서 Lync Server 2013을 정의 하 고 구성 하는 경우 토폴로지 작성기에서 이미 토폴로지에서 사용 중인 Lync Server 2013의 인스턴스를 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="182fc-131">If you define and configure Lync Server 2013 in Topology Builder for a deployment that already has Lync Server 2010 or Office Communications Server 2007 R2 deployed, Topology Builder will not allow you to define an instance of a Lync Server 2013 that is already in use in the topology.</span></span>

<span data-ttu-id="182fc-132">토폴로지 작성기에는 "서버의 SQL server \[ FQDN에 \] sql 인스턴스 호스팅 역할 ' User Store '가 이미 포함 되어 있습니다." 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="182fc-132">Topology Builder will display the following message to inform you of this issue: "The SQL server \[FQDN of the server\] already contains a SQL instance hosting role 'User Store'."</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="182fc-133">Lync Server 2013 배포에 새로운 서버 역할을 배포 하려면 먼저 마이그레이션 설명서 및 배포 설명서에 설명 된 대로 기존 배포를 업그레이드 한 다음 계획 설명서 및 배포 설명서에 설명 된 대로 새 서버 역할을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="182fc-133">If you intend to deploy server roles that are new to your Lync Server 2013 deployment, you should first upgrade your existing deployment as described in the Migration documentation and the Deployment documentation, and then deploy the new server roles as described in the Planning documentation and Deployment documentation.</span></span> <span data-ttu-id="182fc-134">이전 버전의 그룹 채팅을 마이그레이션하는 경우 Lync Server 2010 또는 Office Communications Server 2007 r 2에서 다른 모든 구성 요소를 마이그레이션하기 위한 프로세스를 완료 한 후에 마지막으로 마이그레이션하십시오.</span><span class="sxs-lookup"><span data-stu-id="182fc-134">If you are migrating a previous version of Group Chat, migrate it last, after completing the process for migrating all other components from Lync Server 2010 or Office Communications Server 2007 R2.</span></span>



</div>

<span data-ttu-id="182fc-135">Lync Server 2010 또는 Office Communications Server 2007 R2 및 Lync Server 2013 구성 요소의 동시 사용 및 마이그레이션에 대 한 자세한 동시 요구 사항 및 기타 자세한 내용은 마이그레이션 설명서에서 [Lync server 2010에서 lync server 2013로 마이그레이션](migration-from-lync-server-2010-to-lync-server-2013.md) 및 [Office communications server 2007 r 2에서 lync Server 2013로 마이그레이션](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="182fc-135">For specific coexistence requirements and other details about coexistence and migration of Lync Server 2010 or Office Communications Server 2007 R2 and Lync Server 2013 components, see [Migration from Lync Server 2010 to Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) and [Migration from Office Communications Server 2007 R2 to Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) in the Migration documentation.</span></span> <span data-ttu-id="182fc-136">클라이언트에 대 한 혼합 버전 지원에 대 한 자세한 내용은 [Lync Server 2013의 이전 배포에서 지원 되는 클라이언트](lync-server-2013-supported-clients-from-previous-deployments.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="182fc-136">For details about mixed version support for clients, see [Supported clients from previous deployments in Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

