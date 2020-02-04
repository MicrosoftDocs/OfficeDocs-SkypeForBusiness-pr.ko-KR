---
title: 'Lync Server 2013: 토폴로지에 영구 채팅 서버 추가'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Persistent Chat Server to the topology
ms:assetid: 8389b307-8c17-4e45-b3b5-5dc9fcfc2ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205049(v=OCS.15)
ms:contentKeyID: 48184682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53f8c65f561a0f2c7b1937d60344c0177d221ba8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a><span data-ttu-id="6f909-102">Lync Server 2013에서 토폴로지에 영구 채팅 서버 추가</span><span class="sxs-lookup"><span data-stu-id="6f909-102">Add Persistent Chat Server to the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f909-103">_**마지막으로 수정한 주제:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="6f909-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="6f909-104">영구 채팅 서버를 지원 하도록 배포를 구성할 수 있으려면 먼저 토폴로지에 Lync Server 2013, 영구 채팅 서버 지원을 통합 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-104">You must incorporate Lync Server 2013, Persistent Chat Server support in your topology before you can configure your deployment to support Persistent Chat Server.</span></span> <span data-ttu-id="6f909-105">이 항목의 정보는 토폴로지 작성기를 사용 하 여 기존 토폴로지에 영구 채팅 서버 지원을 추가 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-105">The information in this topic describes how to use Topology Builder to add Persistent Chat Server support to your existing topology.</span></span>

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a><span data-ttu-id="6f909-106">토폴로지에 영구 채팅 서버 추가</span><span class="sxs-lookup"><span data-stu-id="6f909-106">To add Persistent Chat Server to a topology</span></span>

<span data-ttu-id="6f909-107">재해 복구 구성 없이 단일 영구 채팅 서버 풀을 설치 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-107">Perform the following steps for installing a single Persistent Chat Server pool without a disaster recovery configuration.</span></span> <span data-ttu-id="6f909-108">고가용성 및 재해 복구용으로 늘어난 영구 채팅 서버 풀을 구성 하려면 배포 설명서의 [Lync Server 2013에서 고가용성 및 재해 복구용으로 영구 채팅 서버 구성을](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6f909-108">For configuring a stretched Persistent Chat Server pool for high availability and disaster recovery, see [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in the Deployment documentation.</span></span>

<span data-ttu-id="6f909-109">여러 영구 채팅 서버 풀을 배포 하려면 각 풀에 대해 동일한 프로세스를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-109">To deploy multiple Persistent Chat Server pools, repeat the same process for each pool.</span></span>

1.  <span data-ttu-id="6f909-110">Lync Server 2013을 실행 중이거나 Lync Server 관리 도구가 설치 되어 있는 컴퓨터에서 로컬 사용자 그룹의 구성원 인 계정을 사용 하거나 해당 사용자 권한이 있는 계정으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-110">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6f909-111">로컬 사용자 그룹의 구성원 인 계정을 사용 하 여 토폴로지를 정의할 수 있지만, Lync Server 2013 서버를 설치 하는 데 필요한 토폴로지를 게시 하려면 <STRONG>Domain Admins</STRONG> 그룹 및 <STRONG>RTCUniversalServerAdmins</STRONG> 그룹의 구성원 인 계정을 사용 해야 하며 영구 채팅 서버 파일 저장소에 사용할 파일 저장소에 대 한 모든 권한 (즉, 읽기, 쓰기 및 수정)이 있는지 확인 합니다 (즉, 토폴로지 작성기가 필수 dacl을 구성할 수 있도록). 또는 해당 권한이 있는 계정</span><span class="sxs-lookup"><span data-stu-id="6f909-111">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to install a Lync Server 2013 server, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file store that you are going to use for the Persistent Chat Server file store (that is, so that Topology Builder can configure the required DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="6f909-112">토폴로지 작성기를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-112">Start Topology Builder.</span></span>

3.  <span data-ttu-id="6f909-113">콘솔 트리에서 **영구 채팅 풀** 노드로 이동한 다음 확장 하 여 영구 채팅 서버 풀을 선택 하거나 노드를 마우스 오른쪽 단추로 클릭 하 고 **새 영구 채팅 풀**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-113">In the console tree, navigate to the **Persistent Chat Pools** node and expand it to select a Persistent Chat Server pool, or right-click the node and select **New Persistent Chat Pool**.</span></span> <span data-ttu-id="6f909-114">풀의 FQDN (정규화 된 도메인 이름)을 정의 하 고 풀이 단일 서버 풀 또는 다중 서버 풀 배포 인지 여부를 표시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-114">You must define the pool’s fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.</span></span>
    
    <span data-ttu-id="6f909-115">**여러 컴퓨터 풀** 또는 **단일 컴퓨터 풀**을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-115">You can choose a **Multiple Computer Pool** or a **Single Computer Pool**.</span></span> <span data-ttu-id="6f909-116">영구 채팅 서버 풀에 둘 이상의 영구 채팅 서버 프런트 엔드 서버가 있는 경우에는 이전을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-116">Choose the former if you are planning to have more than one Persistent Chat Server Front End Server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="6f909-117">이 옵션을 지금 설정 하거나, 나중에 단일 컴퓨터 풀을 만든 후 나중에 추가 서버를 추가할 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-117">Make this choice now, or at a later point, because after you create a single computer pool, you cannot add additional servers to it later.</span></span> <span data-ttu-id="6f909-118">여러 컴퓨터 풀을 선택 하는 경우 풀을 구성 하는 개별 영구 채팅 서버 프런트 엔드 서버의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-118">If you choose a multiple computer pool, enter the names of the individual Persistent Chat Server Front End Servers that comprise the pool.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6f909-119">영구 채팅 서버 역할이 Lync Server 2013&nbsp;standard edition server에 설치 되는 경우 Fqdn은 스탠더드 버전 서버의 fqdn과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-119">If the Persistent Chat Server role is being installed on a Lync Server 2013&nbsp;Standard Edition server, the FQDN needs to match the FQDN of the Standard Edition server.</span></span>

    
    </div>

4.  <span data-ttu-id="6f909-120">영구 채팅 서버 풀에 대 한 간단한 **표시 이름을** 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-120">Define a simple **Display Name** for the Persistent Chat Server pool.</span></span> <span data-ttu-id="6f909-121">표시 이름은 사용자 지정 클라이언트 (특히 영구 채팅 서버 풀이 여러 개 있는 경우)를 사용 하 여 채팅방을 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-121">The display name can be used by custom clients, particularly when there are multiple Persistent Chat Server pools, to differentiate rooms.</span></span>

5.  <span data-ttu-id="6f909-122">Lync Server 프런트 엔드 서버와 통신 하기 위해 영구 채팅 서버에서 사용 하는 포트를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-122">Define the port used by the Persistent Chat Server to communicate with Lync Server Front End Servers.</span></span> <span data-ttu-id="6f909-123">기본 포트는 5041입니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-123">The default port is 5041.</span></span>

6.  <span data-ttu-id="6f909-124">조직에 준수 지원이 필요한 경우 **준수 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-124">If your organization requires compliance support, select the **Enable compliance** check box.</span></span> <span data-ttu-id="6f909-125">선택 하는 경우 영구 채팅 서버 준수 서비스는 영구 채팅 서버 프런트 엔드 서버와 동일한 컴퓨터에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-125">If chosen, the Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="6f909-126">나중에 영구 채팅 서버 준수에 대 한 SQL Server 백 엔드 서버를 선택 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-126">You are prompted to select a SQL Server Back End Server for Persistent Chat Server Compliance later.</span></span>

7.  <span data-ttu-id="6f909-127">영구 채팅 서버 풀에 대 한 사이트 선호도를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-127">Assign site affinity for the Persistent Chat Server pool.</span></span> <span data-ttu-id="6f909-128">**사이트 \<SiteName\> 에이 풀을 기본값으로 사용** 확인란을 선택 하거나이 **풀을 모든 사이트의 기본값으로 사용** 하 여이 영구 채팅 서버 풀을 현재 사이트 또는 모든 사이트의 기본 풀로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-128">Select the **Use this pool as default for site \<SiteName\>** check box or **Use this pool as default for all sites** to designate this Persistent Chat Server pool as the default pool for the current site or all sites.</span></span> <span data-ttu-id="6f909-129">Lync 2013 클라이언트를 사용 하 여 회의실을 만들고 관리 하는 경우, 사용자의 사이트와 연결 된 기본 풀을 룸 만들기 및 관리 환경에서 사용 하 여 룸 만들기 및 관리 작업을 해당 풀에 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-129">When the Lync 2013 client is used to create and manage rooms, the default pool associated with the user’s site is used by the room creation and management experience so that it can route room creation and management operations to that pool.</span></span> <span data-ttu-id="6f909-130">이는 여러 영구 채팅 서버 풀이 배포 되어 있고 영구 채팅 서버의 채팅방 만들기 및 관리 기능을 사용 하려는 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-130">This only applies when you have multiple Persistent Chat Server pools deployed, and want to use the room creation and management features of Persistent Chat Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6f909-131">영구 채팅 서버 SDK (소프트웨어 개발 키트)를 사용 하 여 채팅방 만들기 및 관리 기능을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-131">You can customize the room creation and management features using the Persistent Chat Server Software Development Kit (SDK).</span></span><BR><span data-ttu-id="6f909-132">장애 복구용 SQL Server 백업 데이터베이스를 구성 하는 방법에 대 한 자세한 내용은 배포 설명서의 <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Lync Server 2013에서 고가용성 및 재해 복구용 영구 채팅 서버 구성을</A> 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6f909-132">For details about how to configure SQL Server backup databases for disaster recovery, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="6f909-133">다음 중 하나를 실행 하 여 **영구 채팅 서버 백 엔드 (채팅방 콘텐츠 저장)에 대 한 SQL 저장소** 를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-133">Define the **SQL store for the Persistent Chat Server Back End (where chat room content is stored)** by doing one of the following:</span></span>
    
      - <span data-ttu-id="6f909-134">기존 SQL Server 데이터베이스를 사용 하려면 드롭다운 목록에서 사용 하려는 SQL Server 데이터베이스의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-134">To use an existing SQL Server database, in the drop-down list, click the name of the SQL Server database that you want to use.</span></span>
    
      - <span data-ttu-id="6f909-135">새 SQL Server 데이터베이스를 지정 하려면 **새로 만들기**를 클릭 하 고 **새 sql 저장소 정의**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-135">To specify a new SQL Server database, click **New**, and in **Define New SQL Store**, perform the following:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="6f909-136">**Sql SERVER fqdn**에서 새 sql server 데이터베이스를 만들 대상 sql SERVER의 fqdn을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-136">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server database.</span></span>
    
      - <span data-ttu-id="6f909-137">기본 인스턴스를 사용 하려면 **기본 인스턴스를 선택 하** 고, 다른 인스턴스를 지정 하려면 **명명 된 인스턴스**를 선택 하 고 사용 하려는 인스턴스를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-137">Either select **Default Instance** to use the default instance or, to specify a different instance, select **Named Instance**, and specify the instance that you want to use.</span></span>

9.  <span data-ttu-id="6f909-138">준수를 사용 하도록 설정한 경우 SQL Server 규정 준수 데이터베이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-138">Define the SQL Server compliance database if you enabled Compliance.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6f909-139">영구 채팅 서버 데이터베이스와 영구 채팅 서버 준수 데이터베이스에 대해 고가용성을 위해 SQL Server 미러를 구성 하는 방법에 대 한 자세한 내용은 배포 설명서의 <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Lync Server 2013에서 고가용성 및 재해 복구용 영구 채팅 서버 구성을</A> 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6f909-139">For details about how to configure SQL Server mirrors for high availability for the Persistent Chat Server database and the Persistent Chat Server compliance database, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

10. <span data-ttu-id="6f909-140">파일 저장소를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-140">Define the file store.</span></span> <span data-ttu-id="6f909-141">파일 저장소는 파일 저장소에 업로드 된 파일의 복사본이 저장 되는 폴더 (예: 채팅방에 게시 된 파일 첨부 저장)입니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-141">A file store is a folder where a copy of any file uploaded to the file repository is stored (for example, storing file attachments posted to a chat room).</span></span> <span data-ttu-id="6f909-142">다중 서버 영구 채팅 서버 토폴로지의 경우 UNC (범용 명명 규칙) 경로 여야 합니다. 단일 서버 영구 채팅 서버 토폴로지의 경우 로컬 파일 경로일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-142">In the case of a multiple-server Persistent Chat Server topology, this must be a Universal Naming Convention (UNC) path; and for a single-server Persistent Chat Server topology, it can be a local file path.</span></span>
    
    <span data-ttu-id="6f909-143">기존 파일 저장소를 사용 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-143">To use an existing file store, perform the following steps:</span></span>
    
      - <span data-ttu-id="6f909-144">**파일 서버 FQDN**에 새 파일 저장소를 만들 파일 저장소의 fqdn을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-144">In **File Server FQDN**, specify the FQDN of the file store on which you want to create the new file store.</span></span>
    
      - <span data-ttu-id="6f909-145">**파일 공유**에서 사용 하려는 파일 저장소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-145">In **File Share**, specify the file store that you want to use.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6f909-146">파일 저장소를 만들기 전에 토폴로지 작성기에서 파일 저장소를 정의할 수 있지만 토폴로지를 게시 하기 전에 정의한 위치에 파일 저장소를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-146">You can define the file store in Topology Builder before you create the file store, but you must create the file store in the defined location you define before you publish the topology.</span></span>

    
    </div>

11. <span data-ttu-id="6f909-147">이 영구 채팅 서버 풀의 다음 홉으로 사용할 프런트 엔드 서버 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-147">Select the Front End Server pool to be used as a next hop for this Persistent Chat Server pool.</span></span> <span data-ttu-id="6f909-148">이 풀로 영구 채팅 서버 요청을 라우팅할 수 있는 프런트 엔드 서버 풀입니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-148">This is the Front End Server pool that will be able to route Persistent Chat Server requests to this pool.</span></span>

12. <span data-ttu-id="6f909-149">구성을 저장 하려면 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-149">To save the configuration, click **Finish**.</span></span> <span data-ttu-id="6f909-150">토폴로지 작성기에는 특정 풀 설정에 따라 영구 채팅 서버 풀이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-150">The Persistent Chat Server pool appears in Topology Builder accompanied by your specific pool settings.</span></span>
    
    <span data-ttu-id="6f909-151">이제 영구 채팅 서버에 업데이트 된 토폴로지를 게시 하려면 배포 설명서의 [Lync Server 2013에 업데이트 된 토폴로지 게시](lync-server-2013-publish-the-updated-topology.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6f909-151">To now publish your updated topology to which you’ve Persistent Chat Server, see [Publish the updated topology in Lync Server 2013](lync-server-2013-publish-the-updated-topology.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6f909-152">토폴로지 작성기가 이미 열려 있는 경우에는 <A href="lync-server-2013-publish-the-updated-topology.md">Lync Server 2013에서 업데이트 된 토폴로지 게시</A> 의 3 단계를 진행 하 여 업데이트 된 토폴로지 게시를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f909-152">With Topology Builder already open, you can proceed to step 3 in <A href="lync-server-2013-publish-the-updated-topology.md">Publish the updated topology in Lync Server 2013</A> to begin publishing your updated topology.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

