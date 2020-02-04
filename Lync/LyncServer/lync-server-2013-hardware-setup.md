---
title: 'Lync Server 2013: 하드웨어 설치'
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
ms.openlocfilehash: 6831ba5f8d2afea7bddbd0c26ab4cebb2cff44f1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727898"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-setup-for-lync-server-2013"></a><span data-ttu-id="835e8-102">Lync Server 2013의 하드웨어 설치</span><span class="sxs-lookup"><span data-stu-id="835e8-102">Hardware setup for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="835e8-103">_**마지막으로 수정한 주제:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="835e8-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="835e8-104">토폴로지를 구현 해야 하는 인프라에 필요한 하드웨어 및 기타 구성 요소를 설정 하려면 토폴로지 작성기에 토폴로지를 게시 하기 전에 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="835e8-104">Setting up the hardware and other components required in the infrastructure that you need to implement your topology requires that, prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="835e8-105">필요한 모든 컴퓨터 (Lync Server 2013, 데이터베이스 서버, IIS (인터넷 정보 서비스)를 실행 하는 서버)를 비롯 한 토폴로지 디자인의 각 구성 요소에 대 한 하드웨어를 설치 하 고 다음을 실행 합니다. 프록시 서버 (해당 하는 경우), 네트워크 어댑터, 하드웨어 로드 균형 조정기, 저장소 장치 (예: 파일 서버)</span><span class="sxs-lookup"><span data-stu-id="835e8-105">Install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="835e8-106">네트워크 어댑터의 수 및 속도에 대 한 권장 사항을 팔 로우 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="835e8-106">Confirm that you have followed the recommendations for the number and speed for network adapters.</span></span> <span data-ttu-id="835e8-107">하드웨어 부하 분산 장치를 사용 하는 경우, Lync Server 2013에서 사용할 수 있도록 공급 업체의 적절 한 정보를 보유 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="835e8-107">If you will be using hardware load balancers, make sure that you have the proper information from the vendor to configure them for use with Lync Server 2013.</span></span> <span data-ttu-id="835e8-108">Lync Server에서 필요한 파일 공유를 보관 하는 데 파일 서버 또는 다른 서버를 사용 하는 경우 서버를 사용할 수 있는지 확인 하 고 파일 공유를 구성할 준비가 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="835e8-108">If you will be using a file server or other server to house the file share required by Lync Server, make sure that the server is available and ready for the configuration of the file share.</span></span> <span data-ttu-id="835e8-109">배포에 필요한 구성 요소를 지정 하는 토폴로지를 정의 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 토폴로지 정의 및 구성을](lync-server-2013-defining-and-configuring-the-topology.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="835e8-109">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="835e8-110">서버에 대 한 하드웨어 요구 사항에 대 한 자세한 내용은 지원 가능성 문서에서 [Lync Server 2013에 대해 지원 되는 하드웨어](lync-server-2013-supported-hardware.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="835e8-110">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="835e8-111">네트워킹 인프라가 요구 사항을 충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="835e8-111">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="835e8-112">자세한 내용은 계획 설명서의 [Lync Server 2013에 대 한 네트워크 인프라 요구 사항을](lync-server-2013-network-infrastructure-requirements.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="835e8-112">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="835e8-113">Active Directory 도메인 서비스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="835e8-113">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="835e8-114">Ad ds를 설정 하려면 ad ds에 배포 하려는 모든 구성 요소를 정의 하는 것이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="835e8-114">Setting up AD DS includes preparing AD DS and defining all components that you want to deploy in AD DS.</span></span> <span data-ttu-id="835e8-115">AD DS를 준비 하는 방법에 대 한 자세한 내용은 배포 설명서에서 [Lync Server 2013에 대 한 Active Directory 도메인 서비스 준비](lync-server-2013-preparing-active-directory-domain-services.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="835e8-115">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="835e8-116">파일 공유를 만드는 데 필요한 사용 권한을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="835e8-116">Set up the required permissions for creating the file share.</span></span> <span data-ttu-id="835e8-117">Lync Server 2013에서 파일 공유를 사용 하는 권한은 토폴로지를 게시할 때 토폴로지 작성기에 의해 자동으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="835e8-117">Permissions for use of file shares by Lync Server 2013 are automatically configured by Topology Builder when you publish your topology.</span></span> <span data-ttu-id="835e8-118">그러나 토폴로지를 게시 하는 데 사용 되는 사용자 계정에는 토폴로지 작성기가 필요한 권한을 구성할 수 있도록 파일 공유에 대 한 모든 권한 (읽기/쓰기/수정)이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="835e8-118">However, the user account used to publish the topology must have full control (read/write/modify) on the file share in order for Topology Builder to configure the required permissions.</span></span> <span data-ttu-id="835e8-119">토폴로지 작성기 게시 프로세스 중에 파일 공유를 올바르게 관리할 수 있으려면 사용자가 구성원으로 속해 있는 사용자 또는 도메인 그룹을 파일 공유가 있는 컴퓨터에서 로컬 관리자 그룹의 구성원으로 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="835e8-119">To make sure that the file share can be managed properly during the Topology Builder publishing process, the user or domain group that the user is a member of should be made a member of the local Administrators group on the machine where the file share is located.</span></span> <span data-ttu-id="835e8-120">다중 도메인 시나리오에서 사용자 또는 그룹을 도메인 B의 컴퓨터에서 로컬 관리자 그룹의 구성원으로 만들어야 합니다 (여기서는 파일 공유가 위치할 위치).</span><span class="sxs-lookup"><span data-stu-id="835e8-120">In a multi-domain scenario, Domain A user or group should be made a member of the local Administrators group on the machine in Domain B where the file share will be located.</span></span>
    
    <span data-ttu-id="835e8-121">DFS (분산 파일 시스템)에서 파일 공유를 사용 하 여 업데이트 하는 방법에 대 한 자세한 내용은 [Lync Server 2013의 파일 저장소 구성을](lync-server-2013-configure-dfs-file-storage.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="835e8-121">For details about updating using file shares in a Distributed File System (DFS), see [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="835e8-122">Lync Server 2013, Enterprise Edition 용 파일 공유를 프런트 엔드 서버에서 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="835e8-122">The file share for Lync Server 2013, Enterprise Edition cannot be located on the Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="835e8-123">웹 서비스의 하드웨어 부하 분산 장치를 설치 하 고 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="835e8-123">Install and set up the hardware load balancer for Web Services.</span></span> <span data-ttu-id="835e8-124">DNS (도메인 이름 시스템) 부하 분산을 배포 하는 경우에도 이러한 풀에 대해 하드웨어 부하 분산 장치를 사용 해야 하지만 HTTP/HTTPS 트래픽에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="835e8-124">With Domain Name System (DNS) load balancing deployed, you still need to also use hardware load balancers for these pools, but only for HTTP/HTTPS traffic.</span></span> <span data-ttu-id="835e8-125">하드웨어 로드 균형 조정기는 포트 443 및 80을 통해 클라이언트의 HTTPS 트래픽에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="835e8-125">The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span> <span data-ttu-id="835e8-126">이러한 풀에 대 한 하드웨어 부하 분산 장치가 여전히 필요 하지만, 설정 및 관리는 하드웨어 로드 균형 조정기의 관리자가 가장 하는 HTTP/HTTPS 트래픽에 주로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="835e8-126">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTP/HTTPS traffic, which the administrators of the hardware load balancers are accustomed to.</span></span>

<span data-ttu-id="835e8-127">이 항목에 설명 된 대로 모든 준비 작업을 완료 한 후에 토폴로지를 게시 하기 전에 다음 작업도 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="835e8-127">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to:</span></span>

  - [<span data-ttu-id="835e8-128">Lync Server 2013의 서버에 운영 체제 및 필수 구성 요소 소프트웨어 설치</span><span class="sxs-lookup"><span data-stu-id="835e8-128">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>](lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md)

  - [<span data-ttu-id="835e8-129">Lync Server 2013에 대한 IIS 구성</span><span class="sxs-lookup"><span data-stu-id="835e8-129">Configure IIS for Lync Server 2013</span></span>](lync-server-2013-configure-iis.md)

  - [<span data-ttu-id="835e8-130">Lync Server 2013에 대해 SQL Server 구성</span><span class="sxs-lookup"><span data-stu-id="835e8-130">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="835e8-131">프런트 엔드 풀 또는 Standard Edition 서버에 대한 Lync Server 2013의 DNS 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="835e8-131">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

</div>

<span> </span>

</div>

</div>

</div>

