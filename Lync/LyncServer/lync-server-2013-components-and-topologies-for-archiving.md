---
title: 'Lync Server 2013: 보관용 구성 요소 및 토폴로지'
description: 'Lync Server 2013: 보관용 구성 요소 및 토폴로지'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Archiving
ms:assetid: 5893063d-a44a-4034-aba9-cbe883ecf710
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204916(v=OCS.15)
ms:contentKeyID: 48184213
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f6ccb62993dc6a8dbc098d4a9c5f28b9b3f7fac9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576924"
---
# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="9e1dd-103">Lync Server 2013의 보관에 대 한 구성 요소 및 토폴로지</span><span class="sxs-lookup"><span data-stu-id="9e1dd-103">Components and topologies for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e1dd-104">_**마지막으로 수정 된 항목:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="9e1dd-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="9e1dd-105">Lync Server 2013 IM 및 회의 콘텐츠를 보관 하려는 경우 Lync Server에서 보관을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e1dd-105">If you want to archive Lync Server 2013 IM and conferencing content, you can implement Archiving in Lync Server.</span></span>

<div>

## <a name="archiving-components"></a><span data-ttu-id="9e1dd-106">보관 구성 요소</span><span class="sxs-lookup"><span data-stu-id="9e1dd-106">Archiving Components</span></span>

<span data-ttu-id="9e1dd-107">보관 기능에 포함되는 구성 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9e1dd-107">The Archiving feature includes the following components:</span></span>

  - <span data-ttu-id="9e1dd-p101">**보관 에이전트**. 보관 에이전트(통합 데이터 수집 에이전트라고도 함)는 모든 프런트 엔드 풀 및 Standard Edition 서버에 자동으로 설치되고 활성화됩니다. 보관 에이전트가 자동으로 활성화되더라도 보관을 사용하도록 설정하고 올바르게 구성하기 전까지는 메시지가 실제로 캡처되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e1dd-p101">**Archiving agents**. Archiving agents (also known as unified data collection agents) are installed and activated automatically on every Front End pool and Standard Edition server. Although archiving agents are activated automatically, no messages are actually captured until Archiving is enabled and appropriately configured.</span></span>

  - <span data-ttu-id="9e1dd-111">**보관 데이터 저장소**.</span><span class="sxs-lookup"><span data-stu-id="9e1dd-111">**Archiving data storage**.</span></span> <span data-ttu-id="9e1dd-112">Lync Server 2013의 데이터 저장소는 다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e1dd-112">Data storage for Lync Server 2013 can be either of the following:</span></span>
    
      - <span data-ttu-id="9e1dd-113">Exchange 2013 저장소</span><span class="sxs-lookup"><span data-stu-id="9e1dd-113">Exchange 2013 storage.</span></span> <span data-ttu-id="9e1dd-114">Microsoft Exchange 통합 옵션을 사용 하도록 설정 하는 경우 Exchange 2013 서버에 있는 사용자 사서함은 보관 된 데이터에 대해 Exchange 2013 저장소를 사용 하지만 사서함이 보존 In-Place에 있는 경우에만 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1dd-114">If you enable the Microsoft Exchange integration option, user mailboxes homed on the Exchange 2013 server use Exchange 2013 storage for archived data, but only if the mailboxes have been put on In-Place Hold.</span></span>
    
      - <span data-ttu-id="9e1dd-115">SQL Server 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="9e1dd-115">SQL Server storage.</span></span> <span data-ttu-id="9e1dd-116">배포의 사용자가 Lync Server 2013에 있는 경우에는 지원 되는 버전의 SQL Server를 실행 하는 보관 데이터베이스를 설정 하 여 해당 사용자에 대 한 보관을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e1dd-116">If you have users in your deployment who are homed on Lync Server 2013, you can set up Archiving databases that run a supported version of SQL Server to enable archiving for those users.</span></span>

<span data-ttu-id="9e1dd-117">보관을 설정하려면 또한 파일 저장소가 필요하지만 보관은 프런트 엔드 서버 또는 Standard Edition 서버와 동일한 파일 저장소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1dd-117">Archiving also requires file storage, but Archiving uses the same file storage as the Front End Servers or Standard Edition server.</span></span>

<span data-ttu-id="9e1dd-118">보관에 대 한 하드웨어 및 소프트웨어 요구 사항 목록은 지원 가능성 설명서의 lync Server 2013에서 Lync Server 2013 및 [서버 소프트웨어 및 인프라 지원](lync-server-2013-server-software-and-infrastructure-support.md) [에 대해 지 원하는 하드웨어](lync-server-2013-supported-hardware.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9e1dd-118">For a list of hardware and software requirements for Archiving, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="9e1dd-119">지원되는 토폴로지</span><span class="sxs-lookup"><span data-stu-id="9e1dd-119">Supported Topologies</span></span>

<span data-ttu-id="9e1dd-120">보관 지원이 필요한 사용자가 포함된 각 풀에 보관을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1dd-120">You deploy Archiving in each pool that has users that require archiving support.</span></span> <span data-ttu-id="9e1dd-121">보관은 Enterprise Edition 풀 및 Standard Edition server의 프런트 엔드 서버에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e1dd-121">Archiving runs on Front End Servers in Enterprise Edition pools and on Standard Edition servers.</span></span> <span data-ttu-id="9e1dd-122">보관 데이터 저장소는 다음과 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e1dd-122">Archiving data storage can be the following:</span></span>

  - <span data-ttu-id="9e1dd-123">Exchange 2013 저장소와 통합 됨</span><span class="sxs-lookup"><span data-stu-id="9e1dd-123">Integrated with Exchange 2013 storage</span></span>

  - <span data-ttu-id="9e1dd-124">별도의 SQL Server 데이터베이스를 사용 하 여 배포 됨</span><span class="sxs-lookup"><span data-stu-id="9e1dd-124">Deployed using separate SQL Server databases</span></span>

<span data-ttu-id="9e1dd-125">Exchange 2013 배포에 Lync Server 배포의 모든 사용자가 포함 되어 있지 않은 경우 Exchange 2013 서버에 사서함이 있는 사용자에 대해 Microsoft Exchange 통합을 사용 해야 하며, 다른 모든 Lync 사용자에 대해 보관에 사용할 별도의 SQL Server 데이터베이스를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1dd-125">If your Exchange 2013 deployment does not include all users in your Lync Server deployment, you must use Microsoft Exchange integration for the users whose mailboxes are home on Exchange 2013 servers, and you must deploy separate SQL Server databases for all other Lync users to use for archiving.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="9e1dd-126">지원되는 배치</span><span class="sxs-lookup"><span data-stu-id="9e1dd-126">Supported Collocation</span></span>

<span data-ttu-id="9e1dd-127">Lync Server 2013에서는 다양 한 배치 시나리오를 지원 하므로 단일 서버에서 여러 구성 요소를 실행 하거나 (소규모 조직이 있는 경우) 개별 구성 요소를 다른 서버에서 실행 하 여 하드웨어 비용을 절약할 수 있습니다 (확장성과 성능이 필요한 대규모 조직이 있는 경우).</span><span class="sxs-lookup"><span data-stu-id="9e1dd-127">Lync Server 2013 supports a variety of collocation scenarios, allowing you flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="9e1dd-128">구성 요소를 배치할지 여부를 결정하기 전에 확장성 요인을 분명하게 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1dd-128">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="9e1dd-129">보관은 풀 또는 Standard Edition 서버의 프런트 엔드 서버에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e1dd-129">Archiving is deployed on the Front End Servers of a pool or Standard Edition servers.</span></span> <span data-ttu-id="9e1dd-130">배치 된 수 있는 구성 요소에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync server 2013에서 Supported server 배치](lync-server-2013-supported-server-collocation.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9e1dd-130">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="9e1dd-131">저장소와 Exchange 2013 저장소를 통합 하는 대신 별도의 SQL Server 데이터베이스를 사용 하는 경우에는 다음 중 하나를 사용 하 여 보관 데이터베이스를 함께 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e1dd-131">If you use separate SQL Server databases for Archiving, instead of or in addition to integrating storage with Exchange 2013 storage, you can collocate the Archiving database with any of the following:</span></span>

  - <span data-ttu-id="9e1dd-132">모니터링 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="9e1dd-132">Monitoring database</span></span>

  - <span data-ttu-id="9e1dd-133">Enterprise Edition 프런트 엔드 풀의 백 엔드 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="9e1dd-133">Back-end database of an Enterprise Edition Front End pool</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9e1dd-p108">보관 데이터베이스를 호스팅하는 서버가 다른 데이터베이스를 호스팅할 수 있습니다. 단, 보관 데이터베이스를 다른 데이터베이스와 함께 배치하려는 경우 많은 사용자의 메시지를 보관하면 보관 데이터베이스에 필요한 디스크 공간이 매우 커질 수 있다는 점에 유의해야 합니다. 따라서 보관 데이터베이스는 백 엔드 데이터베이스와 함께 배치하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9e1dd-p108">The server hosting the Archiving database can host other databases. However, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large. For this reason, we do not recommend collocating the Archiving database with the back-end database.</span></span>



</div>

<span data-ttu-id="9e1dd-137">보관 데이터베이스를 모니터링 데이터베이스, 백 엔드 데이터베이스 또는 이러한 데이터베이스 모두와 함께 배치할 경우 이러한 데이터베이스 중 일부 또는 전체에 대해 단일 SQL 인스턴스를 사용하거나 다음과 같은 제한 사항과 함께 각 데이터베이스에 대해 개별 SQL 인스턴스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e1dd-137">If you collocate the Archiving database with the Monitoring database, back-end database, or both of these databases, you can either use a single SQL instance for any or all of the databases, or you can use a separate SQL instance for each database, with the following limitation:</span></span>

  - <span data-ttu-id="9e1dd-138">각 SQL 인스턴스는 단일 백 엔드 데이터베이스, 단일 모니터링 데이터베이스 및 단일 보관 데이터베이스만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e1dd-138">Each SQL instance can contain only a single back-end database, single Monitoring database, and single Archiving database.</span></span>

<span data-ttu-id="9e1dd-139">모든 서버 역할 및 데이터베이스의 배치에 대 한 자세한 내용은 지원 가능성 설명서에서 [Lync server 2013의 Supported server 배치](lync-server-2013-supported-server-collocation.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9e1dd-139">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

