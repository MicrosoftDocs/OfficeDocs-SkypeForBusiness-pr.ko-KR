---
title: 'Lync Server 2013: 영구 채팅 서버에 대 한 구성 요소 및 토폴로지'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Persistent Chat Server
ms:assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398500(v=OCS.15)
ms:contentKeyID: 48184420
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45707cafca4a7ed9da7cdeb5e162128ccd73468d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191511"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="df9b7-102">Lync Server 2013의 영구 채팅 서버에 대 한 구성 요소 및 토폴로지</span><span class="sxs-lookup"><span data-stu-id="df9b7-102">Components and topologies for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df9b7-103">_**마지막으로 수정 된 항목:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="df9b7-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="df9b7-104">영구 채팅 서버는 단일 서버 구성과 다중 서버 구성을 모두 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-104">Persistent Chat Server supports both single-server configurations and multiple-server configurations.</span></span> <span data-ttu-id="df9b7-105">영구 채팅 서버는 Lync Server 2013 Standard Edition Server 에서도 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-105">Persistent Chat Server can also run on a Lync Server 2013 Standard Edition server.</span></span> <span data-ttu-id="df9b7-106">이러한 구성은 다음과 같은 영구 채팅 서버 구성 요소 및 토폴로지로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-106">These configurations consist of the following Persistent Chat Server components and topologies.</span></span>

<div>

## <a name="persistent-chat-server-components"></a><span data-ttu-id="df9b7-107">영구 채팅 서버 구성 요소</span><span class="sxs-lookup"><span data-stu-id="df9b7-107">Persistent Chat Server Components</span></span>

<span data-ttu-id="df9b7-108">최신 버전의 영구 채팅 서버를 설치 하려면 다음 구성 요소가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-108">Installing the latest version of Persistent Chat Server requires the following components:</span></span>

  - <span data-ttu-id="df9b7-109">영구 채팅 서버를 실행 하며 다음 서비스를 제공 하는 하나 이상의 컴퓨터:</span><span class="sxs-lookup"><span data-stu-id="df9b7-109">One or more computers running Persistent Chat Server and providing the following services:</span></span>
    
      - <span data-ttu-id="df9b7-110">영구 채팅 서비스</span><span class="sxs-lookup"><span data-stu-id="df9b7-110">Persistent Chat service</span></span>
    
      - <span data-ttu-id="df9b7-111">준수를 사용 하도록 설정 된 경우 설정 되는 준수 서비스</span><span class="sxs-lookup"><span data-stu-id="df9b7-111">Compliance service, which is turned on if compliance is enabled</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="df9b7-112">Lync Server 2013에서 파일 업로드/다운로드를 위한 영구 채팅 웹 서비스는 이제 Lync Server 2013&nbsp;프런트 엔드 서버를 사용 하 여 배치 된.</span><span class="sxs-lookup"><span data-stu-id="df9b7-112">In Lync Server 2013, the Persistent Chat Web Services for File Upload/Download is now collocated with Lync Server 2013&nbsp;Front End Server.</span></span><BR><span data-ttu-id="df9b7-113">또한 대화방 용 영구 채팅 웹 서비스는 Lync Server 2013&nbsp;프런트 엔드 서버를 사용 하 여 배치 된 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-113">The Persistent Chat Web Services for Chat Room Management is also collocated with Lync Server 2013&nbsp;Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="df9b7-114">대화방 콘텐츠, 대화방 및 범주가 저장 되는 영구 채팅 콘텐츠 데이터베이스를 호스팅하기 위한 SQL Server 백 엔드 데이터베이스를 호스트 하는 서버 (미러링이 사용 되는 경우 둘 이상의 서버)</span><span class="sxs-lookup"><span data-stu-id="df9b7-114">Server(s) (more than one server if mirroring is used) that host the SQL Server back-end database for hosting the Persistent Chat content database where chat room content, rooms, and categories are stored.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="df9b7-115">백 엔드 데이터베이스에는 범주 및 만들어지는 영구 채팅방에 대 한 정보를 비롯 하 여 채팅 기록 데이터가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-115">The back-end database stores chat history data, including information about categories and Persistent Chat rooms that are created.</span></span>

    
    </div>

  - <span data-ttu-id="df9b7-116">규정 준수를 사용 하도록 설정 하면 영구 채팅 준수 데이터베이스 호스팅을 위한 SQL Server 백 엔드 데이터베이스를 호스트 하는 서버 (미러링이 사용 되는 경우 둘 이상의 서버)가 저장 되며, 준수 이벤트 및 준수 목적에 대 한 채팅 콘텐츠를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-116">If compliance was enabled, a server(s) (more than one server if mirroring is used) that host the SQL Server back-end database for hosting the Persistent Chat Compliance database, where compliance events and chat content for the purpose of compliance are stored.</span></span>

<span data-ttu-id="df9b7-117">관리 콘솔과 같은 별도의 컴퓨터에서 영구 채팅 서버를 관리 하려면 컴퓨터에서 Lync Server 제어판을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-117">To administer Persistent Chat Server from a separate computer (such as an administrative console), use the Lync Server Control Panel on the computer.</span></span> <span data-ttu-id="df9b7-118">그런 다음 포리스트 루트에 하나 이상의 글로벌 카탈로그 서버가 있는 Active Directory 도메인 서비스 도메인에이 컴퓨터를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-118">This computer must then be deployed in an Active Directory Domain Services domain, with at least one global catalog server in the forest root.</span></span>

<span data-ttu-id="df9b7-119">영구 채팅 서버에 대 한 하드웨어 및 소프트웨어 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서의 lync server 2013, [지원 되는 하드웨어](lync-server-2013-supported-hardware.md)및 lync server 2013에서 lync server [2013의 서버 소프트웨어 및 인프라 지원](lync-server-2013-server-software-and-infrastructure-support.md) [에서 영구 채팅 서버에 대 한 기술 요구 사항을](lync-server-2013-technical-requirements-for-persistent-chat-server.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="df9b7-119">For details about hardware and software requirements for Persistent Chat Server, see [Technical requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md), and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="df9b7-120">지원되는 배치</span><span class="sxs-lookup"><span data-stu-id="df9b7-120">Supported Collocation</span></span>

<span data-ttu-id="df9b7-121">Lync Server 2013에서는 한 서버에서 여러 구성 요소를 실행 하거나 (소규모 조직의 경우) 개별 구성 요소를 다른 서버에서 실행 하 여 하드웨어 비용을 절약할 수 있도록 하는 다양 한 위치 시나리오를 지원 합니다. 확장성과 성능이 필요한 대규모 조직</span><span class="sxs-lookup"><span data-stu-id="df9b7-121">Lync Server 2013 supports a variety of collocation scenarios, providing you the flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="df9b7-122">구성 요소를 배치할지 여부를 결정하기 전에 확장성 요인을 분명하게 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-122">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="df9b7-123">준수를 사용 하도록 설정 된 경우 영구 채팅 준수 서비스는 Lync Server 2013 프런트 엔드 서버를 사용 하 여 배치 된 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-123">The Persistent Chat Compliance service, if compliance is enabled, is collocated with the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="df9b7-124">Standard Edition 서버에 영구 채팅 서버를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-124">Persistent Chat Server can be deployed on the Standard Edition server.</span></span> <span data-ttu-id="df9b7-125">영구 채팅 서버 백 엔드 서버와 영구 채팅 준수 데이터베이스는 로컬 SQL Server Express 백 엔드 서버의 Standard Edition 서버에서 배치 된 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-125">The Persistent Chat Server Back End Server and the Persistent Chat Compliance database can be collocated on the Standard Edition server on the local SQL Server Express Back End Server.</span></span> <span data-ttu-id="df9b7-126">배치 된 수 있는 구성 요소에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync server 2013에서 Supported server 배치](lync-server-2013-supported-server-collocation.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="df9b7-126">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="df9b7-127">Lync Server 2013 Enterprise Edition의 경우 Enterprise Edition 서버에서 영구 채팅 서버를 배치 된 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-127">For Lync Server 2013 Enterprise Edition, Persistent Chat Servers cannot be collocated on the Enterprise Edition server.</span></span> <span data-ttu-id="df9b7-128">영구 채팅 서버용 SQL Server 데이터베이스는 Enterprise Edition 프런트 엔드 풀의 백 엔드 서버 데이터베이스와 배치 된 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-128">The SQL Server database for Persistent Chat Server can be collocated with the Back End Server database of an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="df9b7-129">영구 채팅 준수에 대 한 SQL Server 데이터베이스는 Enterprise Edition 풀의 백 엔드 서버 데이터베이스와 배치 된 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-129">The SQL Server database for Persistent Chat compliance can also be collocated with the Back End Server database of an Enterprise Edition pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="df9b7-130">영구 채팅 데이터베이스를 호스트 하는 서버는 다른 데이터베이스를 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-130">The server hosting the Persistent Chat database can host other databases.</span></span> <span data-ttu-id="df9b7-131">그러나 영구 채팅 데이터베이스를 다른 데이터베이스와 배치 하는 경우에는 여러 사용자에 게 메시지를 저장 하는 경우 영구 채팅 데이터베이스에 필요한 디스크 공간이 매우 커질 수 있다는 사실을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-131">However, when you consider collocating the Persistent Chat database with other databases, be aware that if you are storing the messages of more than a few users, the disk space needed by the Persistent Chat database can grow very large.</span></span> <span data-ttu-id="df9b7-132">따라서 영구 채팅 데이터베이스를 백 엔드 데이터베이스와 배치 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-132">For this reason, we do not recommend collocating the Persistent Chat database with the back-end database.</span></span>



</div>

<span data-ttu-id="df9b7-133">영구 채팅 데이터베이스에 백 엔드 데이터베이스를 함께 배치할 하는 경우 데이터베이스 중 일부 또는 전체에 대해 단일 SQL Server 인스턴스를 사용 하거나 다음과 같은 제한 사항과 함께 각 데이터베이스에 대해 별도의 SQL Server 인스턴스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-133">If you collocate the Persistent Chat database with the back-end database, you can either use a single instance of SQL Server for any or all of the databases, or you can use a separate instance of SQL Server for each database, with the following limitation:</span></span>

  - <span data-ttu-id="df9b7-134">각 SQL Server 인스턴스는 단일 백 엔드 데이터베이스 및 단일 영구 채팅 데이터베이스만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-134">Each instance of SQL Server can contain only a single back-end database and a single Persistent Chat database.</span></span>

<span data-ttu-id="df9b7-135">모든 서버 역할 및 데이터베이스의 배치에 대 한 자세한 내용은 지원 가능성 설명서에서 [Lync server 2013의 Supported server 배치](lync-server-2013-supported-server-collocation.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="df9b7-135">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="persistent-chat-server-topologies"></a><span data-ttu-id="df9b7-136">영구 채팅 서버 토폴로지</span><span class="sxs-lookup"><span data-stu-id="df9b7-136">Persistent Chat Server Topologies</span></span>

<span data-ttu-id="df9b7-137">영구 채팅 서버는 다음 토폴로지를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-137">Persistent Chat Server supports the following topologies:</span></span>

  - <span data-ttu-id="df9b7-138">Lync Server 2013 Enterprise Edition 단일 서버 영구 채팅 서버 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="df9b7-138">Lync Server 2013 Enterprise Edition single server Persistent Chat Server Front End Server</span></span>

  - <span data-ttu-id="df9b7-139">Lync Server 2013 Enterprise Edition 다중 서버 영구 채팅 서버 프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="df9b7-139">Lync Server 2013 Enterprise Edition multiple server Persistent Chat Server Front End Server</span></span>

  - <span data-ttu-id="df9b7-140">SQL Server Express를 사용 하는 Lync Server 2013 Standard Edition 서버</span><span class="sxs-lookup"><span data-stu-id="df9b7-140">Lync Server 2013 Standard Edition server using SQL Server Express</span></span>

  - <span data-ttu-id="df9b7-141">Lync Server 2013 Standard Edition server 및 영구 채팅 서버는 다음 홉 서버로 Standard Edition server를 사용 하는 별도의 서버에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-141">Lync Server 2013 Standard Edition server and Persistent Chat Server on a separate server using Standard Edition server as the next hop server.</span></span>

<span data-ttu-id="df9b7-142">토폴로지 작성기를 사용 하 여 Lync Server 2013 배포에 영구 채팅 서버를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-142">You can add Persistent Chat Server to your Lync Server 2013 deployment by using Topology Builder.</span></span> <span data-ttu-id="df9b7-143">토폴로지에 단일 서버 또는 다중 서버 영구 채팅 서버 풀을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-143">You can add a single server or a multiple server Persistent Chat Server pool to your topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="df9b7-144">토폴로지 작성기를 사용 하 여 단일 서버에서 영구 채팅 서버 풀을 만든 후에는 풀에 서버를 더 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-144">After you create a Persistent Chat Server pool with a single server by using Topology Builder, you cannot add additional servers to the pool.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="df9b7-145">단일 서버 토폴로지</span><span class="sxs-lookup"><span data-stu-id="df9b7-145">Single-Server Topology</span></span>

<span data-ttu-id="df9b7-146">영구 채팅 서버에 대 한 최소 구성 및 가장 간단한 배포는 단일 영구 채팅 서버 프런트 엔드 서버 토폴로지입니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-146">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="df9b7-147">이 배포를 사용 하려면 영구 채팅 서버를 실행 하는 단일 서버 (선택적으로 준수 서비스를 실행 하는 경우, 준수 기능이 사용 하도록 설정 된 경우), SQL Server 데이터베이스를 모두 호스트 하는 서버 및 준수 해야 하는 경우에는 SQL Server 데이터베이스를 저장 합니다. 준수 데이터</span><span class="sxs-lookup"><span data-stu-id="df9b7-147">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="df9b7-148">토폴로지 작성기에서 단일 서버 배포로 시작 된 영구 채팅 서버 풀에는 서버를 더 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-148">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="df9b7-149">필요한 경우 나중에 서버를 더 추가할 수 있도록 단일 서버를 사용 하는 경우에도 다중 서버 풀 토폴로지를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-149">We recommend using the multiple-server pool topology, even if you’re using a single server, so that you can add more servers later, if needed..</span></span>



</div>

<span data-ttu-id="df9b7-150">다음 그림에서는 준수와 함께 단일 영구 채팅 서버 프런트 엔드 서버에 대 한 토폴로지의 모든 필수 및 선택적 구성 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-150">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="df9b7-151">**단일 영구 채팅 서버**</span><span class="sxs-lookup"><span data-stu-id="df9b7-151">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="df9b7-152">![준수 서비스를 사용 하는 단일 서버 토폴로지](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "준수 서비스를 사용 하는 단일 서버 토폴로지")</span><span class="sxs-lookup"><span data-stu-id="df9b7-152">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="df9b7-153">다중 서버 토폴로지</span><span class="sxs-lookup"><span data-stu-id="df9b7-153">Multiple-Server Topology</span></span>

<span data-ttu-id="df9b7-154">더 많은 용량과 안정성을 제공 하기 위해 [Lync server 2013의 영구 채팅 서버 계획](lync-server-2013-planning-for-persistent-chat-server.md)에 설명 된 대로 다중 서버 토폴로지를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-154">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="df9b7-155">다중 서버 토폴로지에는 영구 채팅 서버를 실행 하는 활성 컴퓨터가 최대 4 개까지 포함 될 수 있습니다 (고가용성 및 재해 복구 구성의 경우 8 개까지 가능 하지만 4 개만 활성화 될 수 있으며 나머지 4 개는 대기 중에 있음).</span><span class="sxs-lookup"><span data-stu-id="df9b7-155">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="df9b7-156">각 서버는 최대 2만 명의 동시 사용자를 지원할 수 있으며, 서버 4 대와 영구 채팅 서버 풀에 연결 된 총 8만 동시 사용자에 게 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-156">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="df9b7-157">다중 서버 토폴로지는 다중 서버가 영구 채팅 서버를 호스트 하는 것을 제외 하 고는 단일 서버 토폴로지와 동일 하며 더 높은 규모를 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-157">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="df9b7-158">영구 채팅 서버를 실행 하는 여러 컴퓨터가 Lync Server 및 준수 서비스와 동일한 Active Directory 도메인 서비스 도메인에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-158">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="df9b7-159">다음 그림에서는 영구 채팅 서버, 선택적 준수 서비스 및 별도의 준수 데이터베이스를 실행 하는 여러 컴퓨터를 사용 하는 다중 서버 토폴로지의 모든 구성 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-159">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="df9b7-160">**여러 영구 채팅 서버**</span><span class="sxs-lookup"><span data-stu-id="df9b7-160">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="df9b7-161">![다중 서버 토폴로지](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "다중 서버 토폴로지")</span><span class="sxs-lookup"><span data-stu-id="df9b7-161">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="df9b7-162">다중 서버 토폴로지는 서버 기능 풀링을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-162">Multiple-server topologies provide pooling of server functionality.</span></span> <span data-ttu-id="df9b7-163">서버 풀에서는 영구 채팅 서비스가 데이터를 전달 하 고 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-163">In a server pool, the Persistent Chat services communicate and share data.</span></span> <span data-ttu-id="df9b7-164">예를 들어 원래 하나의 영구 채팅 서비스에 게시 된 채팅 기록을 시스템의 모든 영구 채팅 서비스에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-164">For example, chat history that was originally posted to one Persistent Chat service is available from any Persistent Chat service in the system.</span></span> <span data-ttu-id="df9b7-165">하나의 영구 채팅 서비스를 통해 업로드 되는 파일은 모든 영구 채팅 서비스에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-165">A file that is uploaded through one Persistent Chat service can be accessed by any Persistent Chat service.</span></span> <span data-ttu-id="df9b7-166">사용자는 서로 다른 영구 채팅 서버 프런트 엔드 서버에 연결 하 고 채팅 하 여 서로 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-166">Users can be connected to different Persistent Chat Server Front End Servers and can be chatting and communicating with each other.</span></span>

<span data-ttu-id="df9b7-167">TCP 8011의 기본 포트는 서버를 서버 풀에 연결 하며 영구 채팅 서비스가 자신과 관리 목적으로 통신 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df9b7-167">The default port of TCP 8011 connects a server to a server pool, and is used by the Persistent Chat service to communicate between themselves, or for administrative purposes.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

