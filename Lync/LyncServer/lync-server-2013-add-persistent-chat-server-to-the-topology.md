---
title: 'Lync Server 2013: 토폴로지에 영구 채팅 서버 추가'
description: 'Lync Server 2013: 토폴로지에 영구 채팅 서버를 추가 합니다.'
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
ms.openlocfilehash: 0321978ce4a0c7381cf2915030267645931f572b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572434"
---
# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a><span data-ttu-id="75653-103">Lync Server 2013의 토폴로지에 영구 채팅 서버 추가</span><span class="sxs-lookup"><span data-stu-id="75653-103">Add Persistent Chat Server to the topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75653-104">_**마지막으로 수정 된 항목:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="75653-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="75653-105">영구 채팅 서버를 지원 하도록 배포를 구성 하기 전에 토폴로지의 Lync Server 2013, 영구 채팅 서버 지원을 통합 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75653-105">You must incorporate Lync Server 2013, Persistent Chat Server support in your topology before you can configure your deployment to support Persistent Chat Server.</span></span> <span data-ttu-id="75653-106">이 항목의 정보에서는 토폴로지 작성기를 사용 하 여 기존 토폴로지에 영구 채팅 서버 지원을 추가 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="75653-106">The information in this topic describes how to use Topology Builder to add Persistent Chat Server support to your existing topology.</span></span>

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a><span data-ttu-id="75653-107">토폴로지에 영구 채팅 서버를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="75653-107">To add Persistent Chat Server to a topology</span></span>

<span data-ttu-id="75653-108">재해 복구 구성 없이 단일 영구 채팅 서버 풀을 설치 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="75653-108">Perform the following steps for installing a single Persistent Chat Server pool without a disaster recovery configuration.</span></span> <span data-ttu-id="75653-109">고가용성 및 재해 복구를 위해 확장 된 영구 채팅 서버 풀을 구성 하려면 배포 설명서의 [Lync server 2013에서 고가용성 및 재해 복구용으로 영구 채팅 서버 구성을](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="75653-109">For configuring a stretched Persistent Chat Server pool for high availability and disaster recovery, see [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in the Deployment documentation.</span></span>

<span data-ttu-id="75653-110">여러 영구 채팅 서버 풀을 배포 하려면 각 풀에 대해 동일한 프로세스를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="75653-110">To deploy multiple Persistent Chat Server pools, repeat the same process for each pool.</span></span>

1.  <span data-ttu-id="75653-111">Lync Server 2013을 실행 중이거나 Lync Server 관리 도구가 설치 되어 있는 컴퓨터에서 로컬 사용자 그룹의 구성원 인 계정 또는 이와 동등한 사용자 권한이 있는 계정으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="75653-111">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="75653-112">로컬 Users 그룹의 구성원 인 계정을 사용 하 여 토폴로지를 정의할 수 있지만, Lync Server 2013 서버를 설치 하는 데 필요한 토폴로지를 게시 하려면 <STRONG>Domain Admins</STRONG> 그룹 및 <STRONG>RTCUniversalServerAdmins</STRONG> 그룹의 구성원 인 계정을 사용 해야 하며, 영구 채팅 서버 파일 저장소에 사용할 파일 저장소에 대 한 모든 권한 (읽기, 쓰기 및 수정)이 포함 되어 있어야 합니다 (즉, 토폴로지 작성기에서 필요한 dacl을 구성할 수 있음) 또는 이와 동등한 권한을 가진 계정</span><span class="sxs-lookup"><span data-stu-id="75653-112">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to install a Lync Server 2013 server, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file store that you are going to use for the Persistent Chat Server file store (that is, so that Topology Builder can configure the required DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="75653-113">토폴로지 작성기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="75653-113">Start Topology Builder.</span></span>

3.  <span data-ttu-id="75653-114">콘솔 트리에서 **영구 채팅 풀** 노드로 이동한 후 확장 하 여 영구 채팅 서버 풀을 선택 하거나, 노드를 마우스 오른쪽 단추로 클릭 하 고 **새 영구 채팅 풀**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75653-114">In the console tree, navigate to the **Persistent Chat Pools** node and expand it to select a Persistent Chat Server pool, or right-click the node and select **New Persistent Chat Pool**.</span></span> <span data-ttu-id="75653-115">풀의 FQDN(정규화된 도메인 이름)을 정의하고 풀이 단일 서버 풀 또는 다중 서버 풀 배포인지 여부를 나타내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75653-115">You must define the pool’s fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.</span></span>
    
    <span data-ttu-id="75653-116">**다중 컴퓨터 풀** 또는 **단일 컴퓨터 풀**을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75653-116">You can choose a **Multiple Computer Pool** or a **Single Computer Pool**.</span></span> <span data-ttu-id="75653-117">영구 채팅 서버 풀에 영구 채팅 서버 프런트 엔드 서버를 두 개 이상 사용할 계획인 경우에는 이전을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75653-117">Choose the former if you are planning to have more than one Persistent Chat Server Front End Server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="75653-118">이 항목을 지금 선택 하거나 나중에 단일 컴퓨터 풀을 만든 후 나중에 서버를 더 추가할 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="75653-118">Make this choice now, or at a later point, because after you create a single computer pool, you cannot add additional servers to it later.</span></span> <span data-ttu-id="75653-119">다중 컴퓨터 풀을 선택 하는 경우에는 풀을 구성 하는 개별 영구 채팅 서버 프런트 엔드 서버의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="75653-119">If you choose a multiple computer pool, enter the names of the individual Persistent Chat Server Front End Servers that comprise the pool.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="75653-120">영구 채팅 서버 역할을 Lync Server 2013 Standard Edition 서버에 설치 하는 경우 &nbsp; fqdn이 Standard Edition 서버의 fqdn과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75653-120">If the Persistent Chat Server role is being installed on a Lync Server 2013&nbsp;Standard Edition server, the FQDN needs to match the FQDN of the Standard Edition server.</span></span>

    
    </div>

4.  <span data-ttu-id="75653-121">영구 채팅 서버 풀에 대 한 간단한 **표시 이름을** 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="75653-121">Define a simple **Display Name** for the Persistent Chat Server pool.</span></span> <span data-ttu-id="75653-122">사용자 지정 클라이언트, 특히 영구 채팅 서버 풀이 여러 개 있는 경우에는 표시 이름을 사용 하 여 대화방을 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75653-122">The display name can be used by custom clients, particularly when there are multiple Persistent Chat Server pools, to differentiate rooms.</span></span>

5.  <span data-ttu-id="75653-123">영구 채팅 서버가 Lync Server 프런트 엔드 서버와 통신 하는 데 사용 하는 포트를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="75653-123">Define the port used by the Persistent Chat Server to communicate with Lync Server Front End Servers.</span></span> <span data-ttu-id="75653-124">기본 포트는 5041입니다.</span><span class="sxs-lookup"><span data-stu-id="75653-124">The default port is 5041.</span></span>

6.  <span data-ttu-id="75653-125">조직에 준수 지원이 필요한 경우에는 **준수 사용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="75653-125">If your organization requires compliance support, select the **Enable compliance** check box.</span></span> <span data-ttu-id="75653-126">선택 하는 경우 영구 채팅 서버 준수 서비스가 영구 채팅 서버 프런트 엔드 서버와 동일한 컴퓨터에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75653-126">If chosen, the Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="75653-127">영구 채팅 서버에 대 한 준수를 위해 SQL Server 백 엔드 서버를 선택 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75653-127">You are prompted to select a SQL Server Back End Server for Persistent Chat Server Compliance later.</span></span>

7.  <span data-ttu-id="75653-128">영구 채팅 서버 풀에 대해 사이트 선호도를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="75653-128">Assign site affinity for the Persistent Chat Server pool.</span></span> <span data-ttu-id="75653-129">이 **풀을 \<SiteName\> 사이트에 기본으로 사용** 확인란을 선택 하거나이 풀을 **모든 사이트의 기본값으로 사용** 하 여이 영구 채팅 서버 풀을 현재 사이트 또는 모든 사이트의 기본 풀로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="75653-129">Select the **Use this pool as default for site \<SiteName\>** check box or **Use this pool as default for all sites** to designate this Persistent Chat Server pool as the default pool for the current site or all sites.</span></span> <span data-ttu-id="75653-130">Lync 2013 클라이언트를 사용 하 여 대화방을 만들고 관리 하는 경우에는 사용자 사이트와 연결 된 기본 풀이 대화방 만들기 및 관리 환경에서 사용 되어 대화방 만들기 및 관리 작업을 해당 풀로 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75653-130">When the Lync 2013 client is used to create and manage rooms, the default pool associated with the user’s site is used by the room creation and management experience so that it can route room creation and management operations to that pool.</span></span> <span data-ttu-id="75653-131">이는 영구 채팅 서버 풀을 여러 개 배포 했으며 영구 채팅 서버의 대화방 만들기 및 관리 기능을 사용 하려는 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="75653-131">This only applies when you have multiple Persistent Chat Server pools deployed, and want to use the room creation and management features of Persistent Chat Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="75653-132">영구 채팅 서버 SDK (소프트웨어 개발 키트)를 사용 하 여 대화방 만들기 및 관리 기능을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75653-132">You can customize the room creation and management features using the Persistent Chat Server Software Development Kit (SDK).</span></span><BR><span data-ttu-id="75653-133">재해 복구를 위해 SQL Server 백업 데이터베이스를 구성 하는 방법에 대 한 자세한 내용은 배포 설명서의 configure <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">영구 채팅 서버 구성에서 Lync Server 2013의 고가용성 및 재해 복구</A> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="75653-133">For details about how to configure SQL Server backup databases for disaster recovery, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="75653-134">다음 중 하나를 수행 하 여 **영구 채팅 서버 백 엔드에 대 한 SQL 저장소 (대화방 콘텐츠가 저장 되는 위치)** 를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="75653-134">Define the **SQL store for the Persistent Chat Server Back End (where chat room content is stored)** by doing one of the following:</span></span>
    
      - <span data-ttu-id="75653-135">기존 SQL Server 데이터베이스를 사용 하려면 드롭다운 목록에서 사용 하려는 SQL Server 데이터베이스의 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="75653-135">To use an existing SQL Server database, in the drop-down list, click the name of the SQL Server database that you want to use.</span></span>
    
      - <span data-ttu-id="75653-136">새 SQL Server 데이터베이스를 지정 하려면 **새로 만들기**를 클릭 하 고 **새 sql 저장소 정의**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="75653-136">To specify a new SQL Server database, click **New**, and in **Define New SQL Store**, perform the following:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="75653-137">**Sql SERVER fqdn**에서 새 sql server 데이터베이스를 만들 sql SERVER의 FQDN을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="75653-137">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server database.</span></span>
    
      - <span data-ttu-id="75653-138">기본 인스턴스를 사용하려는 경우 **기본 인스턴스**를 선택하고, 다른 인스턴스를 지정하려면 **명명된 인스턴스**를 선택해서 사용하려는 인스턴스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="75653-138">Either select **Default Instance** to use the default instance or, to specify a different instance, select **Named Instance**, and specify the instance that you want to use.</span></span>

9.  <span data-ttu-id="75653-139">준수를 사용 하도록 설정한 경우 SQL Server 준수 데이터베이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="75653-139">Define the SQL Server compliance database if you enabled Compliance.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="75653-140">영구 채팅 서버 데이터베이스 및 영구 채팅 서버 준수 데이터베이스에 대 한 고가용성을 위해 SQL Server 미러를 구성 하는 방법에 대 한 자세한 내용은 배포 설명서에서 " <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Lync server 2013에서 고가용성 및 재해 복구를 위한 영구 채팅 서버 구성</A> "을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="75653-140">For details about how to configure SQL Server mirrors for high availability for the Persistent Chat Server database and the Persistent Chat Server compliance database, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

10. <span data-ttu-id="75653-141">파일 저장소를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="75653-141">Define the file store.</span></span> <span data-ttu-id="75653-142">파일 저장소는 파일 저장소에 업로드된 파일의 복사본이 저장되는 폴더입니다(예: 채팅방에 게시된 첨부 파일 저장).</span><span class="sxs-lookup"><span data-stu-id="75653-142">A file store is a folder where a copy of any file uploaded to the file repository is stored (for example, storing file attachments posted to a chat room).</span></span> <span data-ttu-id="75653-143">다중 서버 영구 채팅 서버 토폴로지의 경우 UNC (범용 명명 규칙) 경로 여야 합니다. 단일 서버 영구 채팅 서버 토폴로지의 경우 로컬 파일 경로일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75653-143">In the case of a multiple-server Persistent Chat Server topology, this must be a Universal Naming Convention (UNC) path; and for a single-server Persistent Chat Server topology, it can be a local file path.</span></span>
    
    <span data-ttu-id="75653-144">기존 파일 저장소를 사용하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="75653-144">To use an existing file store, perform the following steps:</span></span>
    
      - <span data-ttu-id="75653-145">**파일 서버 FQDN**에 새 파일 저장소를 만들려는 파일 저장소의 FQDN을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="75653-145">In **File Server FQDN**, specify the FQDN of the file store on which you want to create the new file store.</span></span>
    
      - <span data-ttu-id="75653-146">**파일 공유**에 사용하려는 파일 공유를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="75653-146">In **File Share**, specify the file store that you want to use.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="75653-147">파일 저장소를 만들기 전에 토폴로지 작성기에서 파일 저장소를 정의할 수 있지만 토폴로지를 게시 하기 전에 정의한 정의 된 위치에 파일 저장소를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75653-147">You can define the file store in Topology Builder before you create the file store, but you must create the file store in the defined location you define before you publish the topology.</span></span>

    
    </div>

11. <span data-ttu-id="75653-148">이 영구 채팅 서버 풀의 다음 홉으로 사용할 프런트 엔드 서버 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="75653-148">Select the Front End Server pool to be used as a next hop for this Persistent Chat Server pool.</span></span> <span data-ttu-id="75653-149">영구 채팅 서버 요청을이 풀로 라우팅할 수 있는 프런트 엔드 서버 풀입니다.</span><span class="sxs-lookup"><span data-stu-id="75653-149">This is the Front End Server pool that will be able to route Persistent Chat Server requests to this pool.</span></span>

12. <span data-ttu-id="75653-150">구성을 저장하려면 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="75653-150">To save the configuration, click **Finish**.</span></span> <span data-ttu-id="75653-151">영구 채팅 서버 풀은 토폴로지 작성기와 함께 특정 풀 설정을 함께 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="75653-151">The Persistent Chat Server pool appears in Topology Builder accompanied by your specific pool settings.</span></span>
    
    <span data-ttu-id="75653-152">이제 영구 채팅 서버에 업데이트 된 토폴로지를 게시 하려면 배포 설명서의 [Lync Server 2013에서 업데이트 한 토폴로지 게시](lync-server-2013-publish-the-updated-topology.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="75653-152">To now publish your updated topology to which you’ve Persistent Chat Server, see [Publish the updated topology in Lync Server 2013](lync-server-2013-publish-the-updated-topology.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="75653-153">토폴로지 작성기가 이미 열려 있으면 <A href="lync-server-2013-publish-the-updated-topology.md">Lync Server 2013의 업데이트 된 토폴로지 게시</A> 에서 3 단계를 진행 하 여 업데이트 된 토폴로지 게시를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75653-153">With Topology Builder already open, you can proceed to step 3 in <A href="lync-server-2013-publish-the-updated-topology.md">Publish the updated topology in Lync Server 2013</A> to begin publishing your updated topology.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

