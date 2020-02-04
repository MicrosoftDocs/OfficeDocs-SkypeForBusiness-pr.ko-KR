---
title: 'Lync Server 2013: 토폴로지 게시'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the topology
ms:assetid: 3b5a744b-b3a8-4538-a55e-e2e4f72dff47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425880(v=OCS.15)
ms:contentKeyID: 48183866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5760315cc60aa53a40457423c2b5402896c2a90c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747078"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-topology-in-lync-server-2013"></a><span data-ttu-id="350a4-102">Lync Server 2013에서 토폴로지 게시</span><span class="sxs-lookup"><span data-stu-id="350a4-102">Publish the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="350a4-103">_**마지막으로 수정한 주제:** 2013-10-01_</span><span class="sxs-lookup"><span data-stu-id="350a4-103">_**Topic Last Modified:** 2013-10-01_</span></span>

<span data-ttu-id="350a4-104">서버 역할을 추가 하거나 제거할 때 토폴로지를 성공적으로 게시, 사용 또는 사용 하지 않도록 설정 하려면 RTCUniversalServerAdmins 및 Domain Admins 그룹의 구성원 인 사용자로 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-104">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="350a4-105">또한 적절 한 관리자 권한 및 사용 권한을 위임할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-105">It is also possible to delegate the proper administrator rights and permissions.</span></span> <span data-ttu-id="350a4-106">자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="350a4-106">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span> <span data-ttu-id="350a4-107">다른 구성 변경의 경우 RTCUniversalServerAdmins 그룹의 구성원만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-107">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="350a4-108">토폴로지 작성기에서 토폴로지를 정의한 후에는 중앙 관리 저장소에 토폴로지를 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-108">After you define your topology in Topology Builder, you must publish the topology to the Central Management store.</span></span> <span data-ttu-id="350a4-109">중앙 관리 저장소는 Lync Server 2013 배포를 정의 하 고, 설정 하 고, 유지 관리 하 고, 관리 하 고, 설명 하 고, 운영 하는 데 필요한 데이터의 강력한 schematized 저장소를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-109">The Central Management store provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync Server 2013 deployment.</span></span> <span data-ttu-id="350a4-110">또한 구성을 일관성 있게 유지 하기 위해 데이터의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-110">It also validates the data to help ensure configuration consistency.</span></span> <span data-ttu-id="350a4-111">이 구성 데이터에 대 한 모든 변경 사항은 중앙 관리 저장소에서 수행 되며 "동기화 되지 않은" 문제를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-111">All changes to this configuration data happen at the Central Management store, eliminating “out-of-sync” issues.</span></span> <span data-ttu-id="350a4-112">데이터의 읽기 전용 복사본은 Edge 서버를 포함 하 여 토폴로지의 모든 서버에 복제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-112">Read-only copies of the data are replicated to all servers in the topology, including Edge Servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="350a4-113">초기 토폴로지를 성공적으로 게시 하 고 중앙 관리 서버를 만들려면 SQL Server에 최소 20gb의 사용 가능한 디스크 공간이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-113">SQL Server needs a minimum of 20 GB of free disk space to successfully publish the initial topology and create the Central Management Server.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="350a4-114">Enterprise Edition 전용: 토폴로지를 게시 하려면 SQL Server 기반 백 엔드 서버가 온라인 상태이 고 방화벽 예외를 사용 하 여 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-114">For Enterprise Edition only: In order to publish the topology, the SQL Server-based Back End Server must be online and accessible with firewall exceptions in place.</span></span> <span data-ttu-id="350a4-115">방화벽 예외를 지정 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Lync server 2013를 사용 하 여 SQL Server 방화벽 요구 사항 이해</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="350a4-115">For details about specifying firewall exceptions, see <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Understanding firewall requirements for SQL Server with Lync Server 2013</A>.</span></span> <span data-ttu-id="350a4-116">SQL Server를 구성 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-configure-sql-server-for-lync-server.md">Lync server 2013에 맞게 Sql Server 구성을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="350a4-116">For details about configuring SQL Server, see <A href="lync-server-2013-configure-sql-server-for-lync-server.md">Configure SQL Server for Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-publish-a-topology"></a><span data-ttu-id="350a4-117">토폴로지를 게시 하려면</span><span class="sxs-lookup"><span data-stu-id="350a4-117">To publish a topology</span></span>

1.  <span data-ttu-id="350a4-118">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="350a4-119">로컬 파일에서 토폴로지를 열려면 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-119">Select to open the topology from a local file.</span></span> <span data-ttu-id="350a4-120">토폴로지를 정의한 컴퓨터에 있는 경우에는 이전 단계에서 저장 한 위치에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-120">If you are on the computer where you defined the topology, this will be in the location where you saved it in earlier steps.</span></span> <span data-ttu-id="350a4-121">일반적으로이는 토폴로지를 구성한 사용자의 문서 폴더가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-121">Typically, this will be the Documents folder of the user who configured the topology.</span></span>

3.  <span data-ttu-id="350a4-122">**Lync Server 2013** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **토폴로지 게시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-122">Right-click the **Lync Server 2013** node, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="350a4-123">**토폴로지 게시** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-123">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="350a4-124">**데이터베이스 만들기** 페이지에서 퍼블 리 시 할 데이터베이스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-124">On the **Create databases** page, select the databases you want to publish.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="350a4-125">데이터베이스를 만들 수 있는 적절 한 권한이 없는 경우 해당 데이터베이스 옆에 있는 확인란의 선택을 취소 하 고 해당 권한이 있는 다른 사용자가 나중에 데이터베이스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-125">If you don’t have the appropriate rights to create the databases, you can clear the check boxes next to those databases, and someone with appropriate rights can later create the databases.</span></span> <span data-ttu-id="350a4-126">자세한 내용은 <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013에서 SQL Server에 대 한 배포 권한을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="350a4-126">For details, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>

    
    </div>

6.  <span data-ttu-id="350a4-127">선택적으로 **고급**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-127">Optionally click **Advanced**.</span></span> <span data-ttu-id="350a4-128">고급 SQL Server 데이터 파일 배치 옵션을 사용 하 여 다음 옵션 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-128">The Advanced SQL Server data file placement options let you select between the following options:</span></span>
    
      - <span data-ttu-id="350a4-129">**자동으로 데이터베이스 파일 위치 결정** –이 옵션은 로그 및 데이터 파일을 가장 적합 한 위치에 배포 하 여 SQL server 기반 서버의 디스크 구성에 따라 최적의 작업 성능을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-129">**Automatically determine database file location** – This option will determine the best operational performance based on the disk configuration on your SQL Server-based server by distributing the log and data files to the best location.</span></span>
    
      - <span data-ttu-id="350a4-130">**Sql server 인스턴스 기본값 사용** -이 옵션은 인스턴스 설정을 사용 하 여 로그 및 데이터 파일을 sql server 기반 서버에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-130">**Use SQL Server instance defaults** – This option puts log and data files onto the SQL Server-based server by using the instance settings.</span></span> <span data-ttu-id="350a4-131">이 옵션은 SQL Server 기반 서버의 작동 기능을 사용 하 여 로그 및 데이터에 대 한 최적의 위치를 결정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-131">This option does not use the operational functionality of the SQL Server-based server to determine optimal locations for logs and data.</span></span> <span data-ttu-id="350a4-132">일반적으로 SQL Server 관리자는 로그 및 데이터 파일을 SQL Server 기반 서버와 조직 관리 절차에 적합 한 위치로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-132">The SQL Server administrator would typically move the log and data files to locations that are appropriate for the SQL Server-based server and organization management procedures.</span></span>
    
    <span data-ttu-id="350a4-133">**확인**을 클릭 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-133">Click **OK**, and then click **Next**.</span></span>

7.  <span data-ttu-id="350a4-134">**중앙 관리 서버 선택** 페이지에서 프런트 엔드 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-134">On the **Select Central Management Server** page, select a Front End pool.</span></span>

8.  <span data-ttu-id="350a4-135">선택적으로 **고급**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-135">Optionally click **Advanced**.</span></span> <span data-ttu-id="350a4-136">고급 SQL Server 데이터 파일 배치 옵션을 사용 하 여 다음 옵션 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-136">The Advanced SQL Server data file placement options enables you to select between the following options:</span></span>
    
      - <span data-ttu-id="350a4-137">**자동으로 데이터베이스 파일 위치 결정** –이 옵션은 로그 및 데이터 파일을 가장 적합 한 위치에 배포 하 여 SQL server 기반 서버의 디스크 구성에 따라 최적의 작업 성능을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-137">**Automatically determine database file location** – This option will determine the best operational performance based on the disk configuration on your SQL Server-based server by distributing the log and data files to the best location.</span></span>
    
      - <span data-ttu-id="350a4-138">**Sql server 인스턴스 기본값 사용** -이 옵션은 인스턴스 설정을 사용 하 여 로그 및 데이터 파일을 sql server 기반 서버에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-138">**Use SQL Server instance defaults** – This option puts log and data files onto the SQL Server-based server by using the instance settings.</span></span> <span data-ttu-id="350a4-139">이 옵션은 SQL Server 기반 서버의 작동 기능을 사용 하 여 로그 및 데이터에 대 한 최적의 위치를 결정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-139">This option does not use the operational functionality of the SQL Server-based server to determine optimal locations for logs and data.</span></span> <span data-ttu-id="350a4-140">일반적으로 SQL Server 관리자는 로그 및 데이터 파일을 SQL Server 기반 서버와 조직 관리 절차에 적합 한 위치로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-140">The SQL Server administrator would typically move the log and data files to locations that are appropriate for the SQL Server-based server and organization management procedures.</span></span>
    
    <span data-ttu-id="350a4-141">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-141">Click **OK**.</span></span>

9.  <span data-ttu-id="350a4-142">**다음** 을 클릭 하 여 게시 프로세스를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-142">Click **Next** to complete the publishing process.</span></span>

10. <span data-ttu-id="350a4-143">게시 프로세스가 완료 되 면 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-143">When the publish process has completed, click **Finish**.</span></span>
    
    <span data-ttu-id="350a4-144">토폴로지가 성공적으로 게시 되 면 토폴로지에서 Lync Server 2013을 실행 하는 각 서버에 중앙 관리 저장소의 로컬 복제본을 설치 하기 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-144">When the topology has been published successfully, you can begin installing a local replica of the Central Management store on each server running Lync Server 2013 in your topology.</span></span> <span data-ttu-id="350a4-145">첫 번째 프런트 엔드 풀로 시작 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="350a4-145">We recommend that you begin with the first Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="350a4-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="350a4-146">See Also</span></span>


[<span data-ttu-id="350a4-147">Lync Server 2013에 대한 프런트 엔드 서버 및 프런트 엔드 풀 설정</span><span class="sxs-lookup"><span data-stu-id="350a4-147">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

