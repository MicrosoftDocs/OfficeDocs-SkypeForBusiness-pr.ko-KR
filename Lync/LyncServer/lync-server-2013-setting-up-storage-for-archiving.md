---
title: 'Lync Server 2013: 보관 저장소 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up storage for Archiving
ms:assetid: f751245c-743e-454f-8325-968ae5e3de71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205392(v=OCS.15)
ms:contentKeyID: 48185858
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6728c02e9aa73faceaa8b3e681a5cf9cc4c700cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983317"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-storage-for-archiving-in-lync-server-2013"></a><span data-ttu-id="524ca-102">Lync Server 2013에서 보관할 저장소 설정</span><span class="sxs-lookup"><span data-stu-id="524ca-102">Setting up storage for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="524ca-103">_**마지막으로 수정한 주제:** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="524ca-103">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="524ca-104">Lync Server 2013의 보관 저장소에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="524ca-104">Archiving storage for Lync Server 2013 includes the following:</span></span>

  - <span data-ttu-id="524ca-105">\*\*\*\*   IM 콘텐츠를 저장 하려면 데이터 저장소 데이터 저장소가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="524ca-105">**Data storage**   Data storage is required to store IM content.</span></span>

  - <span data-ttu-id="524ca-106">**파일 저장소**   파일 저장소는 회의 (모임) 콘텐츠 데이터 저장소와 파일 저장소를 저장 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="524ca-106">**File storage**   File storage is required to store conferencing (meeting) content data storage and file storage.</span></span>

<div>

## <a name="setting-up-data-storage"></a><span data-ttu-id="524ca-107">데이터 저장소 설정</span><span class="sxs-lookup"><span data-stu-id="524ca-107">Setting Up Data Storage</span></span>

<span data-ttu-id="524ca-108">Lync Server 2013에서 보관할 데이터 저장소를 설정 하는 데 필요한 요구 사항은 보관 데이터를 저장 하는 방법에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="524ca-108">Requirements for setting up data storage for Archiving in Lync Server 2013 depend on how you want to store archiving data:</span></span>

  - <span data-ttu-id="524ca-109">Exchange 저장소를 사용 하 여 보관 데이터를 저장 하려면 Lync Server 2013 보관을 Exchange 배포와 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="524ca-109">Integrate Lync Server 2013 Archiving with your Exchange deployment to store Archiving data using Exchange storage.</span></span>

  - <span data-ttu-id="524ca-110">보관 데이터를 저장 하도록 별도의 SQL Server 데이터베이스 서버를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="524ca-110">Set up separate SQL Server database servers to store Archiving data.</span></span>

<div>

## <a name="setting-up-exchange-storage-for-archiving-data"></a><span data-ttu-id="524ca-111">데이터 보관을 위한 Exchange 저장소 설정</span><span class="sxs-lookup"><span data-stu-id="524ca-111">Setting Up Exchange Storage for Archiving Data</span></span>

<span data-ttu-id="524ca-112">보관 데이터 저장소에 Exchange를 설정 하려면 Exchange 배포에서 Exchange 2013을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="524ca-112">Setting up Exchange for storage of Archiving data requires that your Exchange deployment is running Exchange 2013.</span></span> <span data-ttu-id="524ca-113">또한 사용자 사서함은 Exchange 2013 서버에서 설정 하 고 해당 사서함은 원본 위치 유지에 배치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="524ca-113">Additionally, user mailboxes must be homed on the Exchange 2013 server and their mailboxes must be put on In-Place Hold.</span></span> <span data-ttu-id="524ca-114">Exchange 2013 구성에 대 한 자세한 내용은 Exchange 제품 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="524ca-114">For details about configuring Exchange 2013, see the Exchange product documentation.</span></span>

</div>

<div>

## <a name="setting-up-sql-server-database-servers-for-storage-of-archiving-data"></a><span data-ttu-id="524ca-115">보관 데이터 저장소에 대 한 SQL Server 데이터베이스 서버 설정</span><span class="sxs-lookup"><span data-stu-id="524ca-115">Setting Up SQL Server Database Servers for Storage of Archiving Data</span></span>

<span data-ttu-id="524ca-116">배포를 Exchange와 통합 하지 않는 한 Lync Server 2013에서 보관 하려면 SQL Server 데이터베이스 소프트웨어에 보관 된 데이터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="524ca-116">Archiving in Lync Server 2013 requires the SQL Server database software to store the archived data, unless you integrate your deployment with Exchange.</span></span>

<span data-ttu-id="524ca-117">SQL Server 보관 데이터베이스의 경우 보관 데이터베이스를 호스트 하는 컴퓨터에 SQL Server를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="524ca-117">For SQL Server archiving databases, you must install SQL Server on the computer that will host the Archiving database.</span></span> <span data-ttu-id="524ca-118">프런트 엔드 풀의 백 엔드 데이터베이스에 사용 하는 것과 동일한 SQL 인스턴스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="524ca-118">You can use the same SQL instance that you use for the back-end database of a Front End pool.</span></span> <span data-ttu-id="524ca-119">최상의 성능을 위해서는 중앙 관리 저장소와 별도의 컴퓨터에 보관 데이터베이스를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="524ca-119">For best performance, you should deploy the Archiving database on a computer that is separate from the Central Management store.</span></span> <span data-ttu-id="524ca-120">Collocating Lync Server 2013 구성 요소에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync server 2013에서 지원 되는 Server collocation](lync-server-2013-supported-server-collocation.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="524ca-120">For details about collocating Lync Server 2013 components, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="524ca-121">각 데이터베이스 서버는 지원 되는 버전의 SQL Server를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="524ca-121">Each database server must be running a supported version of SQL Server.</span></span> <span data-ttu-id="524ca-122">지원 되는 버전에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 보관에 대 한 기술 요구 사항을](lync-server-2013-technical-requirements-for-archiving.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="524ca-122">For details about the supported versions, see [Technical requirements for Archiving in Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="524ca-123">보관을 배포 하 고 사용 하기 전에 SQL Server 플랫폼을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="524ca-123">You must set up the SQL Server platforms prior to deploying and enabling Archiving.</span></span> <span data-ttu-id="524ca-124">토폴로지를 게시 하는 데 사용 되는 계정에 적절 한 관리자 권한과 사용 권한이 있는 경우, 토폴로지를 게시할 때 LcsLog (보관 데이터베이스)를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="524ca-124">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="524ca-125">나중에 설치 절차의 일부로 포함 하 여 데이터베이스를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="524ca-125">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="524ca-126">SQL Server에 대 한 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045)Sql server TechCenter을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="524ca-126">For details about SQL Server, see the SQL Server TechCenter at [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="524ca-127">Sql Server 에이전트 서비스 시작 유형이 자동이 고 sql Server 에이전트 서비스가 보관 데이터베이스를 보유 하 고 있는 SQL 인스턴스에 대해 실행 되 고 있는지 확인 하 여, 기본 보관 SQL Server 유지 관리 작업을 예약 된 기준으로 실행할 수 있도록 합니다. SQL Server 에이전트 서비스의 제어권입니다.</span><span class="sxs-lookup"><span data-stu-id="524ca-127">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Archiving database, so that the Default Archiving SQL Server Maintenance Job can run on its scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

</div>

</div>

<div>

## <a name="setting-up-file-storage"></a><span data-ttu-id="524ca-128">파일 저장소 설정</span><span class="sxs-lookup"><span data-stu-id="524ca-128">Setting Up File Storage</span></span>

<span data-ttu-id="524ca-129">보관은 프런트 엔드 풀 또는 Standard Edition 서버를 설정할 때 지정한 Lync Server 2013 파일 공유를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="524ca-129">Archiving uses the Lync Server 2013 file share that you specified when you set up your Front End pool or Standard Edition server.</span></span> <span data-ttu-id="524ca-130">보관에 사용 되는 파일 공유는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="524ca-130">You cannot change the file share used for Archiving.</span></span> <span data-ttu-id="524ca-131">지원 되는 파일 저장소 시스템에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync Server 2013에서 파일 저장소 지원을](lync-server-2013-file-storage-support.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="524ca-131">For details about supported file storage systems, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

