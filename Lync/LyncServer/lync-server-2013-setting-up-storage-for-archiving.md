---
title: 'Lync Server 2013: 보관 저장소 설정'
description: 'Lync Server 2013: 보관 저장소를 설정 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up storage for Archiving
ms:assetid: f751245c-743e-454f-8325-968ae5e3de71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205392(v=OCS.15)
ms:contentKeyID: 48185858
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7ee431b17b31c49ace7fae1f90d79ec6de2ada4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554244"
---
# <a name="setting-up-storage-for-archiving-in-lync-server-2013"></a><span data-ttu-id="16e08-103">Lync Server 2013에서 보관을 위한 저장소 설정</span><span class="sxs-lookup"><span data-stu-id="16e08-103">Setting up storage for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16e08-104">_**마지막으로 수정 된 항목:** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="16e08-104">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="16e08-105">Lync Server 2013에 대 한 보관 저장소에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16e08-105">Archiving storage for Lync Server 2013 includes the following:</span></span>

  - <span data-ttu-id="16e08-106">**데이터 저장소**     데이터 저장소는 IM 콘텐츠를 저장 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e08-106">**Data storage**   Data storage is required to store IM content.</span></span>

  - <span data-ttu-id="16e08-107">**파일 저장소**     파일 저장소는 회의 (모임) 콘텐츠 데이터 저장소 및 파일 저장소를 저장 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e08-107">**File storage**   File storage is required to store conferencing (meeting) content data storage and file storage.</span></span>

<div>

## <a name="setting-up-data-storage"></a><span data-ttu-id="16e08-108">데이터 저장소 설정</span><span class="sxs-lookup"><span data-stu-id="16e08-108">Setting Up Data Storage</span></span>

<span data-ttu-id="16e08-109">Lync Server 2013에서 보관용 데이터 저장소를 설정 하는 데 필요한 요구 사항은 보관 데이터를 저장 하는 방법에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="16e08-109">Requirements for setting up data storage for Archiving in Lync Server 2013 depend on how you want to store archiving data:</span></span>

  - <span data-ttu-id="16e08-110">Exchange 저장소를 사용 하 여 보관 데이터를 저장 하기 위해 Lync Server 2013 보관을 Exchange 배포와 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e08-110">Integrate Lync Server 2013 Archiving with your Exchange deployment to store Archiving data using Exchange storage.</span></span>

  - <span data-ttu-id="16e08-111">보관 데이터를 저장 하도록 별도의 SQL Server 데이터베이스 서버를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e08-111">Set up separate SQL Server database servers to store Archiving data.</span></span>

<div>

## <a name="setting-up-exchange-storage-for-archiving-data"></a><span data-ttu-id="16e08-112">Exchange 저장소를 데이터 보관용으로 설정</span><span class="sxs-lookup"><span data-stu-id="16e08-112">Setting Up Exchange Storage for Archiving Data</span></span>

<span data-ttu-id="16e08-113">Exchange를 설정 하 여 보관 데이터를 저장 하려면 Exchange 배포에서 Exchange 2013이 실행 되 고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e08-113">Setting up Exchange for storage of Archiving data requires that your Exchange deployment is running Exchange 2013.</span></span> <span data-ttu-id="16e08-114">또한 사용자 사서함은 Exchange 2013 서버에 있어야 하며 해당 사서함을 In-Place 보류 상태로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e08-114">Additionally, user mailboxes must be homed on the Exchange 2013 server and their mailboxes must be put on In-Place Hold.</span></span> <span data-ttu-id="16e08-115">Exchange 2013 구성에 대 한 자세한 내용은 Exchange 제품 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="16e08-115">For details about configuring Exchange 2013, see the Exchange product documentation.</span></span>

</div>

<div>

## <a name="setting-up-sql-server-database-servers-for-storage-of-archiving-data"></a><span data-ttu-id="16e08-116">SQL Server 데이터베이스 서버를 보관 데이터 저장소로 설정</span><span class="sxs-lookup"><span data-stu-id="16e08-116">Setting Up SQL Server Database Servers for Storage of Archiving Data</span></span>

<span data-ttu-id="16e08-117">Exchange에 배포를 통합 하지 않으면 Lync Server 2013의 보관을 위해 SQL Server 데이터베이스 소프트웨어에 보관 된 데이터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e08-117">Archiving in Lync Server 2013 requires the SQL Server database software to store the archived data, unless you integrate your deployment with Exchange.</span></span>

<span data-ttu-id="16e08-118">SQL Server 보관 데이터베이스의 경우 보관 데이터베이스를 호스트 하는 컴퓨터에 SQL Server를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e08-118">For SQL Server archiving databases, you must install SQL Server on the computer that will host the Archiving database.</span></span> <span data-ttu-id="16e08-119">프런트 엔드 풀용 백엔드 데이터베이스에 사용하는 동일한 SQL 인스턴스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16e08-119">You can use the same SQL instance that you use for the back-end database of a Front End pool.</span></span> <span data-ttu-id="16e08-120">성능을 최대화하려면 중앙 관리 저장소와는 분리된 컴퓨터에 보관 데이터베이스를 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e08-120">For best performance, you should deploy the Archiving database on a computer that is separate from the Central Management store.</span></span> <span data-ttu-id="16e08-121">배치 lync server 2013 구성 요소에 대 한 자세한 내용은 지원 가능성 설명서의 [lync server 2013에서 Supported server 배치](lync-server-2013-supported-server-collocation.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="16e08-121">For details about collocating Lync Server 2013 components, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="16e08-122">각 데이터베이스 서버는 지원 되는 버전의 SQL Server를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e08-122">Each database server must be running a supported version of SQL Server.</span></span> <span data-ttu-id="16e08-123">지원 되는 버전에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 보관용 기술 요구 사항을](lync-server-2013-technical-requirements-for-archiving.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="16e08-123">For details about the supported versions, see [Technical requirements for Archiving in Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="16e08-124">보관을 배포 하 고 사용 하도록 설정 하기 전에 SQL Server 플랫폼을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e08-124">You must set up the SQL Server platforms prior to deploying and enabling Archiving.</span></span> <span data-ttu-id="16e08-125">토폴로지를 게시하는 데 사용될 계정에 적절한 관리자 권한 및 권한이 있는 경우 토폴로지를 게시할 때 보관 데이터베이스(LcsLog)를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16e08-125">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="16e08-126">또한 설치 절차의 일부로 포함하는 등 나중에 데이터베이스를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16e08-126">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="16e08-127">SQL Server에 대 한 자세한 내용은 SQL Server TechCenter at를 참조 하십시오 [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045) .</span><span class="sxs-lookup"><span data-stu-id="16e08-127">For details about SQL Server, see the SQL Server TechCenter at [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="16e08-128">Sql Server 에이전트 서비스 시작 유형이 자동이 고 sql server 에이전트 서비스가 보관 데이터베이스를 보유 하 고 있는 SQL 인스턴스에 대해 실행 중 이어야 하며, 기본 보관 SQL Server 유지 관리 작업은 SQL Server 에이전트 서비스의 제어 하에서 일정에 따라 실행 될 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e08-128">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Archiving database, so that the Default Archiving SQL Server Maintenance Job can run on its scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

</div>

</div>

<div>

## <a name="setting-up-file-storage"></a><span data-ttu-id="16e08-129">파일 저장소 설정</span><span class="sxs-lookup"><span data-stu-id="16e08-129">Setting Up File Storage</span></span>

<span data-ttu-id="16e08-130">보관에서는 프런트 엔드 풀 또는 Standard Edition Server를 설정할 때 지정한 Lync Server 2013 파일 공유를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e08-130">Archiving uses the Lync Server 2013 file share that you specified when you set up your Front End pool or Standard Edition server.</span></span> <span data-ttu-id="16e08-131">보관용으로 사용되는 파일 공유는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="16e08-131">You cannot change the file share used for Archiving.</span></span> <span data-ttu-id="16e08-132">지원 되는 파일 저장소 시스템에 대 한 자세한 내용은 지원 가능성 설명서에서 [Lync Server 2013의 파일 저장소 지원을](lync-server-2013-file-storage-support.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="16e08-132">For details about supported file storage systems, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

