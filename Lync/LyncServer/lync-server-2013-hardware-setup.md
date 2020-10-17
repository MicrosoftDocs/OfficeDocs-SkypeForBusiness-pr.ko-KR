---
title: 'Lync Server 2013: 하드웨어 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware setup
ms:assetid: 37a9f295-cde3-4beb-9a6a-2580082798ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425852(v=OCS.15)
ms:contentKeyID: 48183834
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57b06362ad70bedd8edd0baafc3d512cbbf95714
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528345"
---
# <a name="hardware-setup-for-lync-server-2013"></a><span data-ttu-id="80586-102">Lync Server 2013의 하드웨어 설정</span><span class="sxs-lookup"><span data-stu-id="80586-102">Hardware setup for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80586-103">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="80586-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="80586-104">토폴로지를 구현 하는 데 필요한 인프라에 필요한 하드웨어 및 기타 구성 요소를 설정 하려면 토폴로지 작성기에서 토폴로지를 게시 하기 전에 다음 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80586-104">Setting up the hardware and other components required in the infrastructure that you need to implement your topology requires that, prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="80586-105">필요한 모든 컴퓨터 (Lync Server 2013, 데이터베이스 서버, IIS (인터넷 정보 서비스)를 실행 하는 서버 및 역방향 프록시 서버를 실행 하는 서버), 네트워크 어댑터, 하드웨어 부하 분산 및 저장 장치 (예: 파일 서버)를 포함 하 여 토폴로지 작성기를 사용 하 여 만들고 저장 한 토폴로지 디자인에서 각 구성 요소에 대 한 하드웨어를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="80586-105">Install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="80586-106">네트워크 어댑터 수 및 속도에 대해 권장 사항을 준수했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="80586-106">Confirm that you have followed the recommendations for the number and speed for network adapters.</span></span> <span data-ttu-id="80586-107">하드웨어 부하 분산 장치를 사용 하는 경우에는 해당 공급 업체의 적절 한 정보를 사용 하 여 Lync Server 2013에서 사용할 수 있도록 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80586-107">If you will be using hardware load balancers, make sure that you have the proper information from the vendor to configure them for use with Lync Server 2013.</span></span> <span data-ttu-id="80586-108">Lync Server에 필요한 파일 공유를 저장할 파일 서버나 기타 서버를 사용 하는 경우에는 해당 서버를 사용할 수 있는지와 파일 공유의 구성을 준비 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80586-108">If you will be using a file server or other server to house the file share required by Lync Server, make sure that the server is available and ready for the configuration of the file share.</span></span> <span data-ttu-id="80586-109">배포에 필요한 구성 요소를 지정 하는 토폴로지를 정의 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 토폴로지 정의 및 구성을](lync-server-2013-defining-and-configuring-the-topology.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="80586-109">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="80586-110">서버에 대 한 하드웨어 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서에서 [Lync Server 2013 용으로 지 원하는 하드웨어](lync-server-2013-supported-hardware.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="80586-110">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="80586-111">네트워크 인프라가 요구 사항을 충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="80586-111">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="80586-112">자세한 내용은 계획 설명서에서 [Lync Server 2013의 네트워크 인프라 요구 사항](lync-server-2013-network-infrastructure-requirements.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="80586-112">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="80586-113">Active Directory 도메인 서비스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80586-113">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="80586-114">AD DS 설치 작업에는 AD DS를 준비하는 작업과 AD DS에서 배포할 모든 구성 요소를 정의하는 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="80586-114">Setting up AD DS includes preparing AD DS and defining all components that you want to deploy in AD DS.</span></span> <span data-ttu-id="80586-115">AD DS를 준비 하는 방법에 대 한 자세한 내용은 배포 설명서에서 [Active Directory 도메인 서비스에 대 한 Lync Server 2013 준비](lync-server-2013-preparing-active-directory-domain-services.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="80586-115">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="80586-116">파일 공유를 만드는 데 필요한 권한을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="80586-116">Set up the required permissions for creating the file share.</span></span> <span data-ttu-id="80586-117">Lync Server 2013의 파일 공유 사용 권한은 토폴로지를 게시할 때 토폴로지 작성기에 의해 자동으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80586-117">Permissions for use of file shares by Lync Server 2013 are automatically configured by Topology Builder when you publish your topology.</span></span> <span data-ttu-id="80586-118">그러나 토폴로지를 게시 하는 데 사용 되는 사용자 계정에는 토폴로지 작성기에서 필요한 권한을 구성 하기 위해 파일 공유에 대 한 모든 권한 (읽기/쓰기/수정)이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80586-118">However, the user account used to publish the topology must have full control (read/write/modify) on the file share in order for Topology Builder to configure the required permissions.</span></span> <span data-ttu-id="80586-119">토폴로지 작성기 게시 프로세스 중에 파일 공유를 올바르게 관리할 수 있도록 하려면 사용자가 구성원으로 속해 있는 사용자 또는 도메인 그룹이 파일 공유가 있는 컴퓨터에서 로컬 Administrators 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80586-119">To make sure that the file share can be managed properly during the Topology Builder publishing process, the user or domain group that the user is a member of should be made a member of the local Administrators group on the machine where the file share is located.</span></span> <span data-ttu-id="80586-120">다중 도메인 시나리오에서 도메인 A 사용자나 그룹은 파일 공유가 있는 도메인 B의 컴퓨터에서 로컬 Administrators 그룹의 구성원으로 지정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80586-120">In a multi-domain scenario, Domain A user or group should be made a member of the local Administrators group on the machine in Domain B where the file share will be located.</span></span>
    
    <span data-ttu-id="80586-121">DFS (분산 파일 시스템)에서 파일 공유를 사용 하 여 업데이트 하는 방법에 대 한 자세한 내용은 [Configure file storage For Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="80586-121">For details about updating using file shares in a Distributed File System (DFS), see [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="80586-122">Lync Server 2013, Enterprise Edition에 대 한 파일 공유는 프런트 엔드 서버에 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="80586-122">The file share for Lync Server 2013, Enterprise Edition cannot be located on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="80586-123">웹 서비스에 대 한 하드웨어 부하 분산 장치를 설치 하 고 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80586-123">Install and set up the hardware load balancer for Web Services.</span></span> <span data-ttu-id="80586-124">DNS (Domain Name System) 부하 분산을 배포 하는 경우에도 이러한 풀에 대 한 하드웨어 부하 분산 장치를 사용 해야 하지만 HTTP/HTTPS 트래픽만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80586-124">With Domain Name System (DNS) load balancing deployed, you still need to also use hardware load balancers for these pools, but only for HTTP/HTTPS traffic.</span></span> <span data-ttu-id="80586-125">하드웨어 부하 분산 장치는 포트 443 및 80을 통해 클라이언트에서 전송되는 HTTPS 트래픽에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="80586-125">The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span> <span data-ttu-id="80586-126">이러한 풀에 대 한 하드웨어 부하 분산 장치는 여전히 필요 하지만 설치 및 관리는 하드웨어 부하 분산 장치의 관리자가 익숙한 HTTP/HTTPS 트래픽을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="80586-126">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTP/HTTPS traffic, which the administrators of the hardware load balancers are accustomed to.</span></span>

<span data-ttu-id="80586-127">이 항목에서 설명하는 모든 준비 작업을 완료한 후에는 토폴로지를 게시하기 전에 다음 작업도 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="80586-127">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to:</span></span>

  - [<span data-ttu-id="80586-128">Lync Server 2013의 서버에 운영 체제 및 필수 구성 요소 소프트웨어 설치</span><span class="sxs-lookup"><span data-stu-id="80586-128">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [<span data-ttu-id="80586-129">Lync Server 2013에 대 한 IIS 구성</span><span class="sxs-lookup"><span data-stu-id="80586-129">Configure IIS for Lync Server 2013</span></span>](lync-server-2013-configure-iis.md)

  - [<span data-ttu-id="80586-130">Lync Server 2013에 대해 SQL Server 구성</span><span class="sxs-lookup"><span data-stu-id="80586-130">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="80586-131">Lync Server 2013에서 프런트 엔드 풀 또는 Standard Edition Server에 대 한 DNS 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="80586-131">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

