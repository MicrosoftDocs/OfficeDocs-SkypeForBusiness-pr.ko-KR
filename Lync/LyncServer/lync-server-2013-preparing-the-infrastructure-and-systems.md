---
title: 'Lync Server 2013: 인프라 및 시스템 준비'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the infrastructure and systems
ms:assetid: 1254ee38-0679-4714-b293-1050f107c158
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398205(v=OCS.15)
ms:contentKeyID: 48183458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fc49f5e246e69f600506d990ace7362d9666f1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747308"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-infrastructure-and-systems-for-lync-server-2013"></a><span data-ttu-id="b6146-102">Lync Server 2013에 대한 인프라 및 시스템 준비</span><span class="sxs-lookup"><span data-stu-id="b6146-102">Preparing the infrastructure and systems for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6146-103">_**마지막으로 수정한 주제:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="b6146-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="b6146-104">Lync Server 2013을 배포 하려면 토폴로지 작성기를 사용 하 여 토폴로지 디자인을 정의 하 고 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6146-104">Deployment of Lync Server 2013 requires the use of Topology Builder to define and publish the topology design.</span></span> <span data-ttu-id="b6146-105">토폴로지에 필요한 구성 요소를 식별 하려면 토폴로지 작성기를 사용 하 여 토폴로지 디자인을 만들고 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6146-105">To identify the components required for your topology, you use Topology Builder to create and save a topology design.</span></span> <span data-ttu-id="b6146-106">토폴로지 작성기에 토폴로지를 게시 하기 전에 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6146-106">Prior to publishing your topology in Topology Builder, you do the following:</span></span>

  - <span data-ttu-id="b6146-107">필요한 모든 컴퓨터 (Lync Server 2013, 데이터베이스 서버, Iis (인터넷 정보 서비스)를 실행 하는 서버를 비롯 한 토폴로지 작성기를 사용 하 여 만들고 저장 한 토폴로지 디자인의 각 구성 요소에 대 한 하드웨어를 가져오고 설치 합니다 ( IIS), 역방향 프록시 서버, 적절 하 게, 네트워크 어댑터, 하드웨어 부하 분산 장치, 저장소 장치 (예: 파일 서버)</span><span class="sxs-lookup"><span data-stu-id="b6146-107">Acquire and install the hardware for each component in the topology design that you created and saved by using Topology Builder, including all required computers (servers running Lync Server 2013, database servers, servers running Internet Information Services (IIS), and reverse proxy servers, as appropriate), network adapters, hardware load balancers, and storage devices (such as file servers).</span></span> <span data-ttu-id="b6146-108">배포에 필요한 구성 요소를 지정 하는 토폴로지를 정의 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 토폴로지 정의 및 구성을](lync-server-2013-defining-and-configuring-the-topology.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b6146-108">For details about how to define a topology that specifies the components needed for your deployment, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span> <span data-ttu-id="b6146-109">서버에 대 한 하드웨어 요구 사항에 대 한 자세한 내용은 지원 가능성 문서에서 [Lync Server 2013에 대해 지원 되는 하드웨어](lync-server-2013-supported-hardware.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b6146-109">For details about hardware requirements for servers, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="b6146-110">네트워킹 인프라가 요구 사항을 충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6146-110">Make sure that the networking infrastructure meets requirements.</span></span> <span data-ttu-id="b6146-111">자세한 내용은 계획 설명서의 [Lync Server 2013에 대 한 네트워크 인프라 요구 사항을](lync-server-2013-network-infrastructure-requirements.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b6146-111">For details, see [Network infrastructure requirements for Lync Server 2013](lync-server-2013-network-infrastructure-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="b6146-112">Active Directory 도메인 서비스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6146-112">Set up Active Directory Domain Services.</span></span> <span data-ttu-id="b6146-113">토폴로지를 게시 하 고 사용 하도록 설정 하려면 AD DS의 컴퓨터 계정으로 내부 서버를 표시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6146-113">To publish and enable the topology, you need the internal servers to be represented by computer accounts in AD DS.</span></span> <span data-ttu-id="b6146-114">이 작업은 컴퓨터를 AD DS에 가입 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6146-114">This is accomplished by joining the computers to AD DS.</span></span> <span data-ttu-id="b6146-115">AD DS를 준비 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에 대 한 Active Directory 도메인 서비스 준비](lync-server-2013-preparing-active-directory-domain-services.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b6146-115">For details about preparing AD DS, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

  - <span data-ttu-id="b6146-116">파일 공유를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b6146-116">Create a file share.</span></span> <span data-ttu-id="b6146-117">Standard Edition 서버는 필요한 파일에 대 한 파일 공유를 호스트할 수 있지만 엔터프라이즈 배포에서는 프런트 엔드 서버에서 파일 공유를 호스팅할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b6146-117">Standard Edition servers can host the file share for the required file, while in an Enterprise deployment the file share cannot be hosted on the front end server.</span></span> <span data-ttu-id="b6146-118">토폴로지 작성기를 성공적으로 완료 하려면 폴더 및 공유에 대 한 ACL (액세스 제어 목록)을 배포 하 고 설정 하는 데 필요한 사용 권한 및 그룹 구성원 자격이 올바르게 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6146-118">The permissions and group memberships required for deploying and setting the access control list (ACL) on the folder and the share must be set correctly for Topology Builder to complete successfully.</span></span> <span data-ttu-id="b6146-119">토폴로지 작성기를 실행 하는 사용자에 게 다음과 같은 사용 권한 및 그룹 구성원이 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6146-119">You should make sure that the person running Topology Builder has the following permissions and group memberships:</span></span>
    
      - <span data-ttu-id="b6146-120">로컬 관리자의 구성원</span><span class="sxs-lookup"><span data-stu-id="b6146-120">Member of Local Administrators</span></span>
    
      - <span data-ttu-id="b6146-121">도메인 사용자의 구성원</span><span class="sxs-lookup"><span data-stu-id="b6146-121">Member of Domain Users</span></span>
    
      - <span data-ttu-id="b6146-122">공유 및 파일 저장소 폴더에 대 한 모든 권한</span><span class="sxs-lookup"><span data-stu-id="b6146-122">Full Control on share and folder of file store</span></span>

  - <span data-ttu-id="b6146-123">Enterprise Edition의 경우 SQL Server를 설치 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6146-123">For Enterprise Edition, install and configure SQL Server.</span></span> <span data-ttu-id="b6146-124">Sql Server 기반 서버가 온라인 상태 여야 하며, 토폴로지를 게시 하는 사용자는 sql server의 로컬 관리자이 고 sql server 인스턴스에서 SQL Server sysadmin 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6146-124">For SQL Server setup to succeed the SQL Server-based server must be online and the person publishing the topology be a local admin on the SQL Server and must be a member of the SQL Server sysadmin group on the SQL Server instance.</span></span>

<span data-ttu-id="b6146-125">이 항목에 설명 된 대로 모든 준비 작업을 완료 한 후 토폴로지를 게시 하기 전에 Windows 운영 체제 및 기타 필수 구성 요소 소프트웨어 설치를 비롯 한 다른 준비 작업을 수행 해야 할 수도 있습니다. IIS 및 DNS 구성</span><span class="sxs-lookup"><span data-stu-id="b6146-125">After you complete all of the preparation tasks as described in this topic, but prior to publishing the topology, you also need to perform the other preparation tasks, including installing the Windows operating systems and other prerequisite software, setting up IIS, and configuring DNS.</span></span> <span data-ttu-id="b6146-126">이러한 작업에 대 한 자세한 내용은 [Lync server 2013을 실행 하는 서버의 시스템 요구 사항](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [lync SERVER 2013 용 IIS 구성](lync-server-2013-configure-iis.md)및 [lync 2013 server 용 인프라 및 시스템을 준비 하는](lync-server-2013-preparing-the-infrastructure-and-systems.md)방법에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="b6146-126">For details about these tasks, see [System requirements for servers running Lync Server 2013](lync-server-2013-system-requirements-for-servers-running-lync-server-2013.md), [Configure IIS for Lync Server 2013](lync-server-2013-configure-iis.md), and [Preparing the infrastructure and systems for Lync Server 2013](lync-server-2013-preparing-the-infrastructure-and-systems.md).</span></span> <span data-ttu-id="b6146-127">또한 클라이언트 및 클라이언트 요구 사항에 대해 잘 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6146-127">Additionally, you should familiarize yourself with the clients and client requirements.</span></span> <span data-ttu-id="b6146-128">자세한 내용은 [Lync Server 2013에서 클라이언트 및 장치 배포](lync-server-2013-deploying-clients-and-devices.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b6146-128">For details, see [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b6146-129">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="b6146-129">In This Section</span></span>

  - [<span data-ttu-id="b6146-130">Lync Server 2013의 하드웨어 설치</span><span class="sxs-lookup"><span data-stu-id="b6146-130">Hardware setup for Lync Server 2013</span></span>](lync-server-2013-hardware-setup.md)

  - [<span data-ttu-id="b6146-131">Lync Server 2013의 소프트웨어 설치</span><span class="sxs-lookup"><span data-stu-id="b6146-131">Software setup for Lync Server 2013</span></span>](lync-server-2013-software-setup.md)

  - [<span data-ttu-id="b6146-132">Lync Server 2013에 대한 Active Directory 도메인 서비스 준비</span><span class="sxs-lookup"><span data-stu-id="b6146-132">Preparing Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-preparing-active-directory-domain-services.md)

  - [<span data-ttu-id="b6146-133">Lync Server 2013에 대해 SQL Server 구성</span><span class="sxs-lookup"><span data-stu-id="b6146-133">Configure SQL Server for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-for-lync-server.md)

  - [<span data-ttu-id="b6146-134">프런트 엔드 풀 또는 Standard Edition 서버에 대한 Lync Server 2013의 DNS 레코드 구성</span><span class="sxs-lookup"><span data-stu-id="b6146-134">Configure DNS records in Lync Server 2013 for a Front End pool or Standard Edition server</span></span>](lync-server-2013-configure-dns-records-for-a-front-end-pool-or-standard-edition-server.md)

  - [<span data-ttu-id="b6146-135">Lync Server 2013 관리 도구 설치</span><span class="sxs-lookup"><span data-stu-id="b6146-135">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

