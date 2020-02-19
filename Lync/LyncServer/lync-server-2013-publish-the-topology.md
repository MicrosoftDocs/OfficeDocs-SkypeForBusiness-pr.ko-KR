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
ms.openlocfilehash: 84d02d5b41c76e69f76c9c6e667cc694a264d2ef
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publish-the-topology-in-lync-server-2013"></a><span data-ttu-id="ebe09-102">Lync Server 2013에서 토폴로지 게시</span><span class="sxs-lookup"><span data-stu-id="ebe09-102">Publish the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebe09-103">_**마지막으로 수정 된 항목:** 2013-10-01_</span><span class="sxs-lookup"><span data-stu-id="ebe09-103">_**Topic Last Modified:** 2013-10-01_</span></span>

<span data-ttu-id="ebe09-104">서버 역할을 추가하거나 제거할 때 토폴로지를 성공적으로 게시하거나 사용 또는 사용하지 않도록 설정하려면 RTCUniversalServerAdmins 및 Domain Admins 그룹 구성원인 사용자로 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe09-104">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="ebe09-105">또한 적절한 관리자 권한을 위임할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebe09-105">It is also possible to delegate the proper administrator rights and permissions.</span></span> <span data-ttu-id="ebe09-106">자세한 내용은 [Lync Server 2013에서 설치 권한 위임을](lync-server-2013-delegate-setup-permissions.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ebe09-106">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span> <span data-ttu-id="ebe09-107">그 밖의 구성 변경은 RTCUniversalServerAdmins 그룹의 구성원이면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebe09-107">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="ebe09-108">토폴로지 작성기에서 토폴로지를 정의한 후에는 토폴로지를 중앙 관리 저장소에 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe09-108">After you define your topology in Topology Builder, you must publish the topology to the Central Management store.</span></span> <span data-ttu-id="ebe09-109">중앙 관리 저장소는 Lync Server 2013 배포를 정의, 설정, 유지 관리, 관리, 설명 및 운영 하는 데 필요한 데이터에 대 한 강력 하 고 schematized 저장소를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe09-109">The Central Management store provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync Server 2013 deployment.</span></span> <span data-ttu-id="ebe09-110">또한 구성 일관성을 유지 하기 위해 데이터의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe09-110">It also validates the data to help ensure configuration consistency.</span></span> <span data-ttu-id="ebe09-111">이 구성 데이터에 대 한 모든 변경 내용은 중앙 관리 저장소에서 수행 되며 "비동기화" 문제를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe09-111">All changes to this configuration data happen at the Central Management store, eliminating “out-of-sync” issues.</span></span> <span data-ttu-id="ebe09-112">데이터의 읽기 전용 복사본이 에지 서버를 포함한 토폴로지의 모든 서버로 복제됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebe09-112">Read-only copies of the data are replicated to all servers in the topology, including Edge Servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ebe09-113">초기 토폴로지를 성공적으로 게시 하 고 중앙 관리 서버를 만들려면 SQL Server에 최소 20gb의 사용 가능한 디스크 공간이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe09-113">SQL Server needs a minimum of 20 GB of free disk space to successfully publish the initial topology and create the Central Management Server.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="ebe09-114">Enterprise Edition에만 해당: 토폴로지를 게시하려면 SQL Server 기반 백 엔드 서버가 온라인이며 방화벽 예외가 지정된 상태에서 액세스 가능한 상태여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe09-114">For Enterprise Edition only: In order to publish the topology, the SQL Server-based Back End Server must be online and accessible with firewall exceptions in place.</span></span> <span data-ttu-id="ebe09-115">방화벽 예외 지정에 대 한 자세한 내용은 <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Lync server 2013을 사용 하 여 SQL Server에 대 한 방화벽 요구 사항 이해</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ebe09-115">For details about specifying firewall exceptions, see <A href="lync-server-2013-understanding-firewall-requirements-for-sql-server.md">Understanding firewall requirements for SQL Server with Lync Server 2013</A>.</span></span> <span data-ttu-id="ebe09-116">SQL Server 구성에 대 한 자세한 내용은 <A href="lync-server-2013-configure-sql-server-for-lync-server.md">CONFIGURE Sql Server For Lync server 2013</A>을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ebe09-116">For details about configuring SQL Server, see <A href="lync-server-2013-configure-sql-server-for-lync-server.md">Configure SQL Server for Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-publish-a-topology"></a><span data-ttu-id="ebe09-117">토폴로지를 게시하려면</span><span class="sxs-lookup"><span data-stu-id="ebe09-117">To publish a topology</span></span>

1.  <span data-ttu-id="ebe09-118">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe09-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="ebe09-p104">로컬 파일에서 토폴로지를 선택하여 엽니다. 토폴로지를 정의한 컴퓨터의 경우 이 위치는 이전 단계에서 토폴로지를 저장한 위치입니다. 일반적으로 이 위치는 토폴로지를 구성한 사용자의 Documents 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="ebe09-p104">Select to open the topology from a local file. If you are on the computer where you defined the topology, this will be in the location where you saved it in earlier steps. Typically, this will be the Documents folder of the user who configured the topology.</span></span>

3.  <span data-ttu-id="ebe09-122">**Lync Server 2013** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **토폴로지 게시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe09-122">Right-click the **Lync Server 2013** node, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="ebe09-123">**토폴로지 게시** 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe09-123">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="ebe09-124">**데이터베이스 만들기** 페이지에서 게시할 데이터베이스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe09-124">On the **Create databases** page, select the databases you want to publish.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ebe09-125">데이터베이스를 만들 수 있는 적절 한 권한이 없는 경우 해당 데이터베이스 옆의 확인란을 선택 취소할 수 있으며 해당 권한을 가진 사용자는 나중에 데이터베이스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebe09-125">If you don’t have the appropriate rights to create the databases, you can clear the check boxes next to those databases, and someone with appropriate rights can later create the databases.</span></span> <span data-ttu-id="ebe09-126">자세한 내용은 <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013의 SQL Server에 대 한 배포 권한을</A>참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ebe09-126">For details, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>

    
    </div>

6.  <span data-ttu-id="ebe09-127">원하는 경우 **고급**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe09-127">Optionally click **Advanced**.</span></span> <span data-ttu-id="ebe09-128">고급 SQL Server 데이터 파일 배치 옵션을 사용 하 여 다음 옵션 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebe09-128">The Advanced SQL Server data file placement options let you select between the following options:</span></span>
    
      - <span data-ttu-id="ebe09-129">**데이터베이스 파일 위치 자동 지정** – 이 옵션은 가장 적절한 위치로 로그 및 데이터 파일을 분산시켜 SQL Server 기반 서버에서 디스크 구성을 기반으로 최적의 작동 성능을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe09-129">**Automatically determine database file location** – This option will determine the best operational performance based on the disk configuration on your SQL Server-based server by distributing the log and data files to the best location.</span></span>
    
      - <span data-ttu-id="ebe09-p107">**SQL Server 인스턴스 기본값 사용** – 이 옵션은 인스턴스 설정을 사용하여 SQL Server 기반 서버에 로그 및 데이터 파일을 저장합니다. 이 옵션은 SQL Server 기반 서버 작동 기능을 사용하여 로그 및 데이터의 최적 위치를 결정하지 않습니다. SQL Server 관리자는 일반적으로 SQL Server 기반 서버 및 조직 관리 절차에 적합한 위치로 로그 및 데이터 파일을 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe09-p107">**Use SQL Server instance defaults** – This option puts log and data files onto the SQL Server-based server by using the instance settings. This option does not use the operational functionality of the SQL Server-based server to determine optimal locations for logs and data. The SQL Server administrator would typically move the log and data files to locations that are appropriate for the SQL Server-based server and organization management procedures.</span></span>
    
    <span data-ttu-id="ebe09-133">**확인**을 클릭하고 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe09-133">Click **OK**, and then click **Next**.</span></span>

7.  <span data-ttu-id="ebe09-134">**중앙 관리 서버 선택** 페이지에서 프런트 엔드 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe09-134">On the **Select Central Management Server** page, select a Front End pool.</span></span>

8.  <span data-ttu-id="ebe09-135">원하는 경우 **고급**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe09-135">Optionally click **Advanced**.</span></span> <span data-ttu-id="ebe09-136">고급 SQL Server 데이터 파일 배치 옵션을 사용 하 여 다음 옵션 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebe09-136">The Advanced SQL Server data file placement options enables you to select between the following options:</span></span>
    
      - <span data-ttu-id="ebe09-137">**데이터베이스 파일 위치 자동 지정** – 이 옵션은 가장 적절한 위치로 로그 및 데이터 파일을 분산시켜 SQL Server 기반 서버에서 디스크 구성을 기반으로 최적의 작동 성능을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe09-137">**Automatically determine database file location** – This option will determine the best operational performance based on the disk configuration on your SQL Server-based server by distributing the log and data files to the best location.</span></span>
    
      - <span data-ttu-id="ebe09-p109">**SQL Server 인스턴스 기본값 사용** – 이 옵션은 인스턴스 설정을 사용하여 SQL Server 기반 서버에 로그 및 데이터 파일을 저장합니다. 이 옵션은 SQL Server 기반 서버 작동 기능을 사용하여 로그 및 데이터의 최적 위치를 결정하지 않습니다. SQL Server 관리자는 일반적으로 SQL Server 기반 서버 및 조직 관리 절차에 적합한 위치로 로그 및 데이터 파일을 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe09-p109">**Use SQL Server instance defaults** – This option puts log and data files onto the SQL Server-based server by using the instance settings. This option does not use the operational functionality of the SQL Server-based server to determine optimal locations for logs and data. The SQL Server administrator would typically move the log and data files to locations that are appropriate for the SQL Server-based server and organization management procedures.</span></span>
    
    <span data-ttu-id="ebe09-141">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe09-141">Click **OK**.</span></span>

9.  <span data-ttu-id="ebe09-142">**다음**을 클릭하여 게시 프로세스를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe09-142">Click **Next** to complete the publishing process.</span></span>

10. <span data-ttu-id="ebe09-143">게시 프로세스를 완료했으면 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe09-143">When the publish process has completed, click **Finish**.</span></span>
    
    <span data-ttu-id="ebe09-144">토폴로지가 성공적으로 게시 되 면 토폴로지에서 Lync Server 2013을 실행 하는 각 서버에 중앙 관리 저장소의 로컬 복제본을 설치 하기 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebe09-144">When the topology has been published successfully, you can begin installing a local replica of the Central Management store on each server running Lync Server 2013 in your topology.</span></span> <span data-ttu-id="ebe09-145">첫 번째 프런트 엔드 풀로 시작 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ebe09-145">We recommend that you begin with the first Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ebe09-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ebe09-146">See Also</span></span>


[<span data-ttu-id="ebe09-147">Lync Server 2013에 대 한 프런트 엔드 서버 및 프런트 엔드 풀 설정</span><span class="sxs-lookup"><span data-stu-id="ebe09-147">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

