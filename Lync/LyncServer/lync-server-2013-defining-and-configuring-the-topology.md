---
title: 'Lync Server 2013: 토폴로지 정의 및 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining and configuring the topology
ms:assetid: 51d1601e-4f83-48d4-ad08-3b4d5e2003aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398339(v=OCS.15)
ms:contentKeyID: 48184146
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8430ec5cc8b362aa78f97afc24ab0e588c7bc650
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a><span data-ttu-id="53d08-102">Lync Server 2013에서 토폴로지 정의 및 구성</span><span class="sxs-lookup"><span data-stu-id="53d08-102">Defining and configuring the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53d08-103">_**마지막으로 수정한 주제:** 2012-09-14_</span><span class="sxs-lookup"><span data-stu-id="53d08-103">_**Topic Last Modified:** 2012-09-14_</span></span>

<span data-ttu-id="53d08-104">토폴로지 작성기를 사용 하 여 토폴로지를 정의 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="53d08-104">You define and configure your topology by using Topology Builder.</span></span> <span data-ttu-id="53d08-105">토폴로지 작성기를 사용할 경우 로컬 관리자 그룹의 구성원 이거나 도메인 관리자와 같은 특권 수준의 도메인 그룹이 될 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="53d08-105">Topology Builder does not require you to be a member of the local Administrators group or a privileged domain group (such as Domain Admins).</span></span> <span data-ttu-id="53d08-106">토폴로지를 표준 사용자로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53d08-106">You can define your topology as a standard user.</span></span> <span data-ttu-id="53d08-107">첫 번째 사용 및 후속 편집 세션에서 토폴로지 작성기를 시작 하면 토폴로지 작성기가 현재 구성 문서를 로드할 위치를 묻는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53d08-107">When you start Topology Builder on first use and subsequent edit sessions, you are prompted for the location where you want Topology Builder to load the current configuration document.</span></span> <span data-ttu-id="53d08-108">선택 항목은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="53d08-108">The choices are the following:</span></span>

  - <span data-ttu-id="53d08-109">기존 배포에서 토폴로지 다운로드</span><span class="sxs-lookup"><span data-stu-id="53d08-109">Download topology from existing deployment</span></span>

  - <span data-ttu-id="53d08-110">로컬 파일에서 토폴로지 열기</span><span class="sxs-lookup"><span data-stu-id="53d08-110">Open topology from a local file</span></span>

  - <span data-ttu-id="53d08-111">새 토폴로지</span><span class="sxs-lookup"><span data-stu-id="53d08-111">New topology</span></span>

<span data-ttu-id="53d08-112">이미 토폴로지를 정의 하 고 중앙 관리 저장소를 설정한 경우 기존 배포에서 토폴로지를 다운로드 하도록 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53d08-112">If you have already defined a topology and have established the Central Management store, you should choose to download a topology from an existing deployment.</span></span> <span data-ttu-id="53d08-113">토폴로지 작성기는 데이터베이스를 읽고 현재 정의를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="53d08-113">Topology Builder will read the database and retrieve the current definition.</span></span> <span data-ttu-id="53d08-114">기존 중앙 관리 저장소가 있는 경우 항상이 옵션을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53d08-114">If you have an existing Central Management store, you should always choose this option.</span></span>

<span data-ttu-id="53d08-115">중앙 관리 저장소를 설정 하지 않은 경우 이전에 저장 된 구성을 편집 하려면 로컬 파일에서 토폴로지를 열도록 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53d08-115">If you have not established a Central Management store and want to edit a previously saved configuration, you should choose to open the topology from a local file.</span></span> <span data-ttu-id="53d08-116">열려고 하는 파일은 이전 세션에서 저장 된 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="53d08-116">The file that you will open would be the configuration file that was saved in a previous session.</span></span> <span data-ttu-id="53d08-117">이 옵션을 사용 하 여 이전에 저장 된 토폴로지를 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53d08-117">You can use this option to edit the previously saved topology.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="53d08-118">이미 게시 된 토폴로지가 있는 경우 로컬 구성 파일을 로드 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53d08-118">If you already have a published topology, you should not load a local configuration file.</span></span> <span data-ttu-id="53d08-119">기존 배포에서 토폴로지를 다운로드 하도록 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53d08-119">You should choose to download the topology from an existing deployment.</span></span>



</div>

<span data-ttu-id="53d08-120">새 토폴로지 작성기 구성을 만들려는 경우 새 토폴로지를 만들도록 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="53d08-120">Choose to create a new topology, if you want to create a new Topology Builder configuration.</span></span> <span data-ttu-id="53d08-121">이전 디자인 세션에서 만든 파일과 동일한 파일로 저장 하도록 선택 하지 않는 한 이전에 저장 된 디자인을 덮어쓰지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="53d08-121">A previously saved design is not overwritten unless you choose to save it as the same file that you created in an earlier design session.</span></span>

<span data-ttu-id="53d08-122">이러한 옵션 각각에 대해 토폴로지 작성기 구성 파일을 저장할 위치를 입력 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53d08-122">In each of these options, you will be prompted for a location to store the Topology Builder configuration file.</span></span> <span data-ttu-id="53d08-123">파일의 위치는 로컬 위치, 설정 된 파일 공유 상의 공유 위치 또는 이동식 미디어 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53d08-123">The location for the file could be a local location, a shared location on an established file share, or removable media.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="53d08-124">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="53d08-124">In This Section</span></span>

  - [<span data-ttu-id="53d08-125">Lync Server 2013에 대한 토폴로지 작성기에서 토폴로지 정의 및 구성</span><span class="sxs-lookup"><span data-stu-id="53d08-125">Define and configure a topology in Topology Builder for Lync Server 2013</span></span>](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [<span data-ttu-id="53d08-126">Lync Server 2013에서 프런트 엔드 풀 또는 Standard Edition 서버 정의 및 구성</span><span class="sxs-lookup"><span data-stu-id="53d08-126">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [<span data-ttu-id="53d08-127">Lync Server 2013에서 재해 복구를 위해 연결된 프런트 엔드 풀 배포</span><span class="sxs-lookup"><span data-stu-id="53d08-127">Deploying paired Front End pools for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [<span data-ttu-id="53d08-128">Lync Server 2013에서 백 엔드 서버 고가용성을 위해 SQL 미러링 배포</span><span class="sxs-lookup"><span data-stu-id="53d08-128">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [<span data-ttu-id="53d08-129">Lync Server 2013에서 단순 URL 편집 또는 구성</span><span class="sxs-lookup"><span data-stu-id="53d08-129">Edit or configure simple URLs in Lync Server 2013</span></span>](lync-server-2013-edit-or-configure-simple-urls.md)

  - [<span data-ttu-id="53d08-130">Lync Server 2013에서 중앙 관리 서버 선택</span><span class="sxs-lookup"><span data-stu-id="53d08-130">Select the Central Management Server in Lync Server 2013</span></span>](lync-server-2013-select-the-central-management-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

