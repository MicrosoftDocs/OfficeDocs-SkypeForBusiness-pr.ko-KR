---
title: 'Lync Server 2013: 영구 채팅 서버에 대한 조직 요구 사항 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your organization's requirements for Persistent Chat Server
ms:assetid: 568674fb-c08a-4170-ac38-e2f8428c69e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398372(v=OCS.15)
ms:contentKeyID: 48184166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68f9195a91a4f8334933d1fce7ffd3a5dceb564c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-organizations-requirements-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="8f0c9-102">Lync Server 2013에서 영구 채팅 서버에 대한 조직 요구 사항 정의</span><span class="sxs-lookup"><span data-stu-id="8f0c9-102">Defining your organization's requirements for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f0c9-103">_**마지막으로 수정한 주제:** 2014-01-15_</span><span class="sxs-lookup"><span data-stu-id="8f0c9-103">_**Topic Last Modified:** 2014-01-15_</span></span>

<span data-ttu-id="8f0c9-104">조직의 영구 채팅 서버를 배포 하기 전에 배포를 최적화 하는 다음 주요 질문을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-104">Before you deploy Persistent Chat Server for your organization, it’s essential to consider the following key questions to optimize your deployment:</span></span>

  - <span data-ttu-id="8f0c9-105">영구 채팅 서버에 대해 누가 (사용자 프로필)을 사용 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="8f0c9-105">Who (user profile) should be enabled for Persistent Chat Server?</span></span> <span data-ttu-id="8f0c9-106">영구 채팅 서버는 전역, 사이트, 풀 또는 사용자 수준에서 설정할 수 있는 정책에 따라 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-106">Persistent Chat Server is enabled by a policy that can be set at a Global, Site, Pool or User level.</span></span>

  - <span data-ttu-id="8f0c9-107">영구 채팅 서버에서 사용할 수 있는 사용자 (소수 자릿수)의 수는 몇 개입니까?</span><span class="sxs-lookup"><span data-stu-id="8f0c9-107">How many users (scale) should be enabled for Persistent Chat Server?</span></span> <span data-ttu-id="8f0c9-108">영구 채팅 서버는 15만에서 제공 하는 사용자 (정책에 따라 설정) 및 영구 채팅 서버를 사용 하는 최대 8만 동시 사용자를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-108">Persistent Chat Server supports 150,000 provisioned users (enabled by policy), and a maximum of 80,000 concurrent users using Persistent Chat Server.</span></span> <span data-ttu-id="8f0c9-109">단일 영구 채팅 서버는 2만 연결 된 사용자를 지원할 수 있으며, 단일 영구 채팅 서버 풀에는 동시에 연결 된 총 8만의 활성 서버를 최대 4 개까지 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-109">A single Persistent Chat Server can support 20,000 connected users, and a single Persistent Chat Server pool can have up to 4 active servers for a total of 80,000 concurrently connected users.</span></span>

  - <span data-ttu-id="8f0c9-110">이전 버전의 그룹 채팅 서버에서 마이그레이션하는 경우 또는 처음으로 영구 채팅 서버를 배포 하는 경우</span><span class="sxs-lookup"><span data-stu-id="8f0c9-110">Are you migrating from a previous version of Group Chat Server, or are you deploying Persistent Chat Server for the first time?</span></span>

  - <span data-ttu-id="8f0c9-111">준수 요구 사항이 있나요?</span><span class="sxs-lookup"><span data-stu-id="8f0c9-111">Are there compliance requirements?</span></span> <span data-ttu-id="8f0c9-112">영구 채팅 서버는 규정 준수를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-112">Persistent Chat Server supports compliance.</span></span> <span data-ttu-id="8f0c9-113">준수 서비스는 이전 그룹 채팅 서버 배포에서 별도의 컴퓨터에 대 한 요구 사항이 아니라 영구 채팅 서버 프런트 엔드 서버에서 collocated를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-113">The compliance service runs collocated on the Persistent Chat Server Front End Server, as opposed to the requirement for a separate computer in previous Group Chat Server deployments.</span></span> <span data-ttu-id="8f0c9-114">준수는 선택 사항이 며, 선택 하는 경우 준수 데이터 및 이벤트를 저장 하도록 구성 해야 하는 준수 데이터베이스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-114">Compliance is optional, and if chosen, requires a compliance database that must be configured to store compliance data and events.</span></span> <span data-ttu-id="8f0c9-115">규정 준수 데이터베이스에서 데이터를 가져와 다른 형식 (예: XML 파일 또는 Exchange 호스팅 보관 함)으로 변환 하도록 어댑터를 구성 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-115">You may want to also configure an adapter to take the data from the compliance database and convert to another format (such as XML files or Exchange-hosted archives).</span></span>

  - <span data-ttu-id="8f0c9-116">범위, 윤리적인 경계 및 액세스를 제어 하는 방법을 선택 하세요.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-116">How do you want to control scopes, ethical boundaries, and access?</span></span> <span data-ttu-id="8f0c9-117">**범주** 를 정의 하 여 이러한 경계를 분리 하 고 각 범주에서 만든 채팅방에 허용 되는 사람을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-117">You can define **Categories** to segregate these boundaries, and choose who is allowed to be in rooms that are created in each of these categories.</span></span>

  - <span data-ttu-id="8f0c9-118">방을 만들 수 있는 사용자를 제어 하는 방법을 선택 하세요.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-118">How do you want to control who can create rooms?</span></span> <span data-ttu-id="8f0c9-119">범주에 적합 한 **작성자**를 구성 하 여 회의실을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-119">You can configure **Creators**, appropriate to your categories, who can create rooms.</span></span> <span data-ttu-id="8f0c9-120">작성자는 범주에 의해 구성 된 **allowedmembers/DeniedMembers** 범위에 따라 채팅방의 지속적인 관리 (추가 구성원 추가 또는 제거)를 위해 다른 구성원을 **채팅방** 관리자로 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-120">Creators can assign other members as **Chat Room Managers** for ongoing management of the rooms (adding or removing additional members), according to the scope for **AllowedMembers/DeniedMembers** configured by the category.</span></span>

  - <span data-ttu-id="8f0c9-121">채팅방을 만들려는 방법을 선택 하세요.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-121">How do you want to create rooms?</span></span> <span data-ttu-id="8f0c9-122">영구 채팅 서버는 회의실 만들기 및 관리를 위한 웹 기반 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-122">Persistent Chat Server provides a web-based feature for room creation and management.</span></span> <span data-ttu-id="8f0c9-123">Lync 2013 클라이언트에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-123">This can be launched from the Lync 2013 client.</span></span> <span data-ttu-id="8f0c9-124">비즈니스 요구 사항 및 워크플로를 구현 하는 영구 채팅 서버 SDK (소프트웨어 개발 키트)를 사용 하 여 사용자 지정 솔루션을 정의 하 고 사용자가 사용자 지정 솔루션을 직접 사용할 수 있도록 영구 채팅 서버를 구성 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-124">You can choose to define a custom solution (by using the Persistent Chat Server Software Development Kit (SDK)) that implements your business requirements and workflows, and configures Persistent Chat Server to direct users to your custom solution.</span></span>

  - <span data-ttu-id="8f0c9-125">프로 비전 할 추가 기능의 종류</span><span class="sxs-lookup"><span data-stu-id="8f0c9-125">What kind of add-ins do you want to provision?</span></span> <span data-ttu-id="8f0c9-126">**추가 기능** 을 통해 Lync 2013 클라이언트의 확장 창을 활용 하 여 채팅방과 관련 된 컨텍스트를 제공 함으로써 채팅방의 경험을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-126">**Add-ins** enhance the in-room experience by leveraging the extensibility pane in the Lync 2013 client to provide context that is relevant to the room.</span></span> <span data-ttu-id="8f0c9-127">가장 유용 하 게 사용할 수 있는 일반 추가 기능 (예: 회사 웹 사이트, 내부 공동 작업 문서 등)을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-127">You can choose what general add-ins might be most useful (for example, your company website, internal collaboration documents, and so on).</span></span> <span data-ttu-id="8f0c9-128">채팅방 관리자는 등록 된 추가 기능 중 하나를 선택 하 여 원하는 경우 해당 채팅방과 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-128">Chat room managers can choose one of the registered add-ins and associate it with their rooms, if desired.</span></span>

  - <span data-ttu-id="8f0c9-129">어떤 종류의 고가용성 및 재해 복구 요구 사항이 있나요?</span><span class="sxs-lookup"><span data-stu-id="8f0c9-129">What kind of high availability and disaster recovery requirements do you have?</span></span> <span data-ttu-id="8f0c9-130">영구 채팅 서버는 가용성을 높이기 위해 SQL Server 미러링 및 SQL Server 클러스터링을 지원 하며, 장애 복구용 SQL Server 로그 전달을 사용 하는 스트레치 된 풀에서 최대 8 개의 서버 (4 활성 및 4 대기)를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-130">Persistent Chat Server supports SQL Server mirroring and SQL Server clustering for high availability and supports up to 8 servers (4 active and 4 standby) in a stretched pool with SQL Server log shipping for disaster recovery.</span></span>

  - <span data-ttu-id="8f0c9-131">규정 요구 사항이 있나요?</span><span class="sxs-lookup"><span data-stu-id="8f0c9-131">Are there regulatory requirements?</span></span> <span data-ttu-id="8f0c9-132">회사가 해당 국가 내에 데이터를 보관 해야 하는 국가/지역에 있는 경우 각 지역에 대해 각각 로컬로 여러 영구 채팅 서버 풀을 배포 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-132">If your company is in a country/region where data needs to be kept within the country, you may need to deploy multiple Persistent Chat Server pools, each local to a specific geography.</span></span> <span data-ttu-id="8f0c9-133">회의실, 범주 또는 추가 기능은 풀을 확장 하지 않으며, 하나의 영구 채팅 서버 풀에만 속합니다.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-133">A room, category, or add-in does not span pools—it belongs to only one Persistent Chat Server pool.</span></span> <span data-ttu-id="8f0c9-134">각 영구 채팅 서버 풀에 대 한 범주, 추가 기능 및 회의실 집합을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-134">You can manage the set of categories, add-ins and rooms for each Persistent Chat Server pool.</span></span> <span data-ttu-id="8f0c9-135">사용자는 범주를 디자인 하는 방법에 따라 AllowedMembers 범위 또는 룸의 구성원 범위를 사용 하 여 하나 이상의 풀에 있는 채팅방에 대 한 액세스 권한을 갖도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-135">Users can be configured to have access to rooms in one or more pools using the category AllowedMembers scope or Room’s membership scope, depending on how you design your categories.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8f0c9-136">여러 영구 채팅 서버 풀을 사용 하는 것이 더 이상 제공 되지 않습니다 (모든 영구 채팅 서버 풀에서 동시에 연결 된 사용자는 항상 8만이 있을 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="8f0c9-136">Having multiple Persistent Chat Server pools does not give you more scale (you can still have only 80,000 concurrently connected users across all your Persistent Chat Server pools).</span></span> <span data-ttu-id="8f0c9-137">여러 영구 채팅 서버 풀을 지 원하는 주요 이유는 규정 관련 사항을 지원 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8f0c9-137">The primary reason for supporting multiple Persistent Chat Server pools is to support regulatory concerns.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

