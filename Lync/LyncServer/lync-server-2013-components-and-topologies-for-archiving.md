---
title: 'Lync Server 2013: 보관의 구성 요소 및 토폴로지'
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
ms.openlocfilehash: b3ccb77d8d2d0b7bd7d4d564087a69b7605863fe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742728"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="5e440-102">Lync Server 2013의 보관의 구성 요소 및 토폴로지</span><span class="sxs-lookup"><span data-stu-id="5e440-102">Components and topologies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e440-103">_**마지막으로 수정한 주제:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="5e440-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="5e440-104">Lync Server 2013 IM 및 회의 콘텐츠를 보관 하려는 경우 Lync Server에서 보관을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e440-104">If you want to archive Lync Server 2013 IM and conferencing content, you can implement Archiving in Lync Server.</span></span>

<div>

## <a name="archiving-components"></a><span data-ttu-id="5e440-105">구성 요소 보관</span><span class="sxs-lookup"><span data-stu-id="5e440-105">Archiving Components</span></span>

<span data-ttu-id="5e440-106">보관 기능은 다음 구성 요소를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e440-106">The Archiving feature includes the following components:</span></span>

  - <span data-ttu-id="5e440-107">**보관 에이전트**.</span><span class="sxs-lookup"><span data-stu-id="5e440-107">**Archiving agents**.</span></span> <span data-ttu-id="5e440-108">보관 에이전트 (통합 데이터 수집 에이전트도 라고도 함)는 모든 프런트 엔드 풀 및 Standard Edition 서버에 자동으로 설치 되 고 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e440-108">Archiving agents (also known as unified data collection agents) are installed and activated automatically on every Front End pool and Standard Edition server.</span></span> <span data-ttu-id="5e440-109">보관 에이전트는 자동으로 활성화 되지만, 보관이 사용 되 고 적절 하 게 구성 될 때까지 메시지가 실제로 캡처되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5e440-109">Although archiving agents are activated automatically, no messages are actually captured until Archiving is enabled and appropriately configured.</span></span>

  - <span data-ttu-id="5e440-110">**데이터 저장소 보관**.</span><span class="sxs-lookup"><span data-stu-id="5e440-110">**Archiving data storage**.</span></span> <span data-ttu-id="5e440-111">Lync Server 2013의 데이터 저장소는 다음 중 하나가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e440-111">Data storage for Lync Server 2013 can be either of the following:</span></span>
    
      - <span data-ttu-id="5e440-112">Exchange 2013 저장소.</span><span class="sxs-lookup"><span data-stu-id="5e440-112">Exchange 2013 storage.</span></span> <span data-ttu-id="5e440-113">Microsoft Exchange 통합 옵션을 사용 하도록 설정 하는 경우 Exchange 2013 서버에 있는 사용자 사서함이 보관 된 데이터에 Exchange 2013 저장소를 사용 하지만 사서함이 원본 위치 유지에 저장 되어 있는 경우에만 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e440-113">If you enable the Microsoft Exchange integration option, user mailboxes homed on the Exchange 2013 server use Exchange 2013 storage for archived data, but only if the mailboxes have been put on In-Place Hold.</span></span>
    
      - <span data-ttu-id="5e440-114">SQL Server 저장소.</span><span class="sxs-lookup"><span data-stu-id="5e440-114">SQL Server storage.</span></span> <span data-ttu-id="5e440-115">배포에서 Lync Server 2013에 있는 사용자가 있는 경우 지원 되는 버전의 SQL Server를 실행 하는 보관 데이터베이스를 설정 하 여 해당 사용자의 보관을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e440-115">If you have users in your deployment who are homed on Lync Server 2013, you can set up Archiving databases that run a supported version of SQL Server to enable archiving for those users.</span></span>

<span data-ttu-id="5e440-116">또한 보관에는 파일 저장소가 필요 하지만, 보관에는 프런트 엔드 서버 또는 스탠더드 버전 서버와 동일한 파일 저장소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e440-116">Archiving also requires file storage, but Archiving uses the same file storage as the Front End Servers or Standard Edition server.</span></span>

<span data-ttu-id="5e440-117">보관을 위한 하드웨어 및 소프트웨어 요구 사항 목록은 제공 가능성 설명서의 lync server 2013에서 Lync Server 2013 및 [서버 소프트웨어 및 인프라 지원](lync-server-2013-server-software-and-infrastructure-support.md) [에 대해 지원 되는 하드웨어](lync-server-2013-supported-hardware.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e440-117">For a list of hardware and software requirements for Archiving, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="5e440-118">지원 되는 토폴로지</span><span class="sxs-lookup"><span data-stu-id="5e440-118">Supported Topologies</span></span>

<span data-ttu-id="5e440-119">보관 지원이 필요한 사용자가 있는 각 풀에 보관을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e440-119">You deploy Archiving in each pool that has users that require archiving support.</span></span> <span data-ttu-id="5e440-120">엔터프라이즈 버전 풀이나 Standard Edition 서버의 프런트 엔드 서버에서 보관을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e440-120">Archiving runs on Front End Servers in Enterprise Edition pools and on Standard Edition servers.</span></span> <span data-ttu-id="5e440-121">보관 데이터 저장소는 다음이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e440-121">Archiving data storage can be the following:</span></span>

  - <span data-ttu-id="5e440-122">Exchange 2013 저장소와 통합</span><span class="sxs-lookup"><span data-stu-id="5e440-122">Integrated with Exchange 2013 storage</span></span>

  - <span data-ttu-id="5e440-123">별도의 SQL Server 데이터베이스를 사용 하 여 배포</span><span class="sxs-lookup"><span data-stu-id="5e440-123">Deployed using separate SQL Server databases</span></span>

<span data-ttu-id="5e440-124">Exchange 2013 배포에 Lync Server 배포의 모든 사용자가 포함 되어 있지 않은 경우 Exchange 2013 서버에서 사서함이 홈 상태인 사용자에 대해 Microsoft Exchange 통합을 사용 하 고 다른 모든 컴퓨터에 대해 별도의 SQL Server 데이터베이스를 배포 해야 합니다. Lync 사용자는 보관에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e440-124">If your Exchange 2013 deployment does not include all users in your Lync Server deployment, you must use Microsoft Exchange integration for the users whose mailboxes are home on Exchange 2013 servers, and you must deploy separate SQL Server databases for all other Lync users to use for archiving.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="5e440-125">지원 되는 Collocation</span><span class="sxs-lookup"><span data-stu-id="5e440-125">Supported Collocation</span></span>

<span data-ttu-id="5e440-126">Lync Server 2013는 특정 서버에서 여러 구성 요소를 실행 하 여 하드웨어 비용을 절약 하 고 (소규모 조직의 경우) 다른 서버에서 개별 구성 요소를 실행 하 여 유연성 있게 사용할 수 있는 다양 한 collocation 시나리오를 지원 합니다 (규모가 큰 경우 확장성 및 성능이 필요한 조직</span><span class="sxs-lookup"><span data-stu-id="5e440-126">Lync Server 2013 supports a variety of collocation scenarios, allowing you flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="5e440-127">구성 요소를 collocate 여부를 결정 하기 전에 확장성 요인을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e440-127">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="5e440-128">보관은 풀 또는 스탠더드 버전 서버의 프런트 엔드 서버에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e440-128">Archiving is deployed on the Front End Servers of a pool or Standard Edition servers.</span></span> <span data-ttu-id="5e440-129">Collocated 수 있는 구성 요소에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync server 2013에서 지원 되는 server collocation](lync-server-2013-supported-server-collocation.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e440-129">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="5e440-130">저장소를 Exchange 2013 저장소와 통합 하는 대신 별도의 SQL Server 데이터베이스를 사용 하는 경우 다음 중 하나를 사용 하 여 보관 데이터베이스를 collocate 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e440-130">If you use separate SQL Server databases for Archiving, instead of or in addition to integrating storage with Exchange 2013 storage, you can collocate the Archiving database with any of the following:</span></span>

  - <span data-ttu-id="5e440-131">모니터링 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="5e440-131">Monitoring database</span></span>

  - <span data-ttu-id="5e440-132">Enterprise Edition 프런트 엔드 풀의 백 엔드 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="5e440-132">Back-end database of an Enterprise Edition Front End pool</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5e440-133">보관 데이터베이스를 호스트 하는 서버는 다른 데이터베이스를 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e440-133">The server hosting the Archiving database can host other databases.</span></span> <span data-ttu-id="5e440-134">그러나 다른 데이터베이스와 보관 데이터베이스를 collocating 하는 경우에는 여러 사용자에 게 메시지를 보관 하는 경우 보관 데이터베이스에 필요한 디스크 공간이 매우 커질 수 있다는 점에 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e440-134">However, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="5e440-135">이 때문에 백 엔드 데이터베이스를 사용 하는 경우 보관 데이터베이스를 collocating 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5e440-135">For this reason, we do not recommend collocating the Archiving database with the back-end database.</span></span>



</div>

<span data-ttu-id="5e440-136">모니터링 데이터베이스, 백 엔드 데이터베이스 또는 둘 다를 사용 하 여 보관 데이터베이스를 collocate 경우 데이터베이스 전체 또는 일부에 대해 단일 SQL 인스턴스를 사용 하거나, 다음과 같이 각 데이터베이스에 대해 별도의 SQL 인스턴스를 사용할 수 있습니다. 큰</span><span class="sxs-lookup"><span data-stu-id="5e440-136">If you collocate the Archiving database with the Monitoring database, back-end database, or both of these databases, you can either use a single SQL instance for any or all of the databases, or you can use a separate SQL instance for each database, with the following limitation:</span></span>

  - <span data-ttu-id="5e440-137">각 SQL 인스턴스에는 단일 백 엔드 데이터베이스, 단일 모니터링 데이터베이스 및 단일 보관 데이터베이스만 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e440-137">Each SQL instance can contain only a single back-end database, single Monitoring database, and single Archiving database.</span></span>

<span data-ttu-id="5e440-138">모든 서버 역할 및 데이터베이스의 collocation에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync server 2013에서 지원 되는 server collocation](lync-server-2013-supported-server-collocation.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e440-138">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

