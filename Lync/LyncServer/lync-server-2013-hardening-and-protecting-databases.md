---
title: 'Lync Server 2013: 데이터베이스 보안 강화 및 보호'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting the databases of Lync Server 2013
ms:assetid: 6953e721-3511-4235-b848-51bab093dc89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518330(v=OCS.15)
ms:contentKeyID: 62625490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f222e92da686792a48ccceeaf1686d96f0406e50
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140261"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a><span data-ttu-id="c347b-102">Lync Server 2013의 데이터베이스 보안 강화 및 보호</span><span class="sxs-lookup"><span data-stu-id="c347b-102">Hardening and protecting the databases of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c347b-103">_**마지막으로 수정 된 항목:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="c347b-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="c347b-104">또한 Microsoft Lync Server 2013은 사용자 정보, 회의 상태, 보관 데이터 및 CDRs (통화 정보 기록)를 저장 하기 위한 SQL Server 데이터베이스에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="c347b-104">Microsoft Lync Server 2013 also depends on SQL Server databases for storing user information, conference state, archiving data, and Call Detail Records (CDRs).</span></span> <span data-ttu-id="c347b-105">응용 프로그램 데이터를 분할 하 여 내결함성을 개선 하 고 문제 해결을 간소화 하 여 Lync Server 백 엔드 데이터베이스에서 Lync Server 2013 데이터의 가용성을 최대화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c347b-105">You can maximize the availability of Lync Server 2013 data on Lync Server back-end databases, by partitioning the application data in a way that improves fault tolerance and simplifies troubleshooting.</span></span> <span data-ttu-id="c347b-106">이러한 목표를 달성하려면 다음과 같은 방법으로 응용 프로그램을 분할합니다.</span><span class="sxs-lookup"><span data-stu-id="c347b-106">To achieve these goals, partition the application data by:</span></span>

  - <span data-ttu-id="c347b-107">**최적의 서버 분할 방법을**   사용 하면 운영 체제, 응용 프로그램 및 프로그램 파일을 데이터 파일과 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="c347b-107">**Using server partitioning best practices**   Separate your operating system, application, and program files from your data files.</span></span>

  - <span data-ttu-id="c347b-108">**트랜잭션 로그 파일 및 데이터베이스 파일**   저장 이러한 파일을 별도로 저장 하 여 내결함성을 향상 하 고 복구를 최적화 하 고 암호화 된 디스크 또는 볼륨에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="c347b-108">**Storing transaction log files and database files**   Store these files separately to increase fault tolerance and optimize recovery, and store them on an encrypted disk or volume.</span></span>

  - <span data-ttu-id="c347b-109">**서버 클러스터링**   을 사용 하 여 Lync server 2013 시스템 가용성을 최적화 하기 위해 백 엔드 서버를 클러스터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="c347b-109">**Using server clustering**   Cluster the back-end servers to optimize Lync Server 2013 system availability.</span></span>

  - <span data-ttu-id="c347b-110">**모든 데이터 백업이 암호화 되 고 적절 하 게 처리**   되었는지 확인 합니다. 백업 미디어는 Lync Server 2013 배포의 데이터 보안에 큰 위협이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c347b-110">**Ensure that all data backups are encrypted and properly handled**   Lost, discarded, or misplaced backup media can pose a significant threat to data security for Lync Server 2013 deployments</span></span>

<span data-ttu-id="c347b-111">Standard Edition server를 제외한 모든 Lync Server 2013 서버에서 SQL Server Express 인스턴스 (RTCLOCAL 인스턴스)에 원격으로 액세스할 수 없으며 Standard Edition 서버에서 SQL Server Express를 제외 하 고 로컬 방화벽 예외가 생성 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c347b-111">On any Lync Server 2013 server except Standard Edition server, the SQL Server Express instance (RTCLOCAL instance) is not remotely accessible, and no local firewall exceptions are created, except for SQL Server Express on a Standard Edition server.</span></span> <span data-ttu-id="c347b-112">Standard Edition 서버에서는 백 엔드 데이터베이스 및 CMS(중앙 관리 저장소)가 모두 원격으로 액세스할 수 있도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c347b-112">On a Standard Edition server, both the back-end database and the Central Management store (CMS) are set up to be remotely accessible.</span></span> <span data-ttu-id="c347b-113">SQL Server 데이터베이스를 강화하려면 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c347b-113">To harden SQL Server databases, you can do the following:</span></span>

  - <span data-ttu-id="c347b-p103">Standard Edition 서버에서 SQL Server Express 방화벽을 사용자 지정하여 데이터베이스에 원격으로 액세스할 수 있는 서버 범위를 제한합니다. 기본적으로 모든 IP 주소가 데이터베이스에 원격으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c347b-p103">Customize the SQL Server Express firewall on Standard Edition servers, limiting the scope of servers that can remotely access the database. By default, any IP address can remotely access the database.</span></span>

  - <span data-ttu-id="c347b-116">SQL Server 구성 관리자를 사용하여 SQL Server 원격 액세스에 대한 프로토콜, IP 주소 및 포트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c347b-116">Use SQL Server Configuration Manager to specify the protocols, IP addresses, and ports for SQL Server remote access:</span></span>
    
      - <span data-ttu-id="c347b-117">Lync Server 2013는 TCP/IP 프로토콜을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c347b-117">Lync Server 2013 uses the TCP/IP protocol.</span></span> <span data-ttu-id="c347b-118">여기에서 IPv4(IP 버전 4)는 지원되지만 IPv6(IP 버전 6)이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c347b-118">It supports IP version 4 (IPv4), but not IP version 6 (IPv6).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c347b-119">Lync Server 2013는 이중 IP 스택이 설정 된 네트워크에서 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c347b-119">Lync Server 2013 can function in a network with dual IP stack enabled.</span></span>

        
        </div>
    
      - <span data-ttu-id="c347b-120">Lync Server 2013에서는 여러 IP 주소 (다중 홈 네트워크 주소 카드)를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c347b-120">Lync Server 2013 supports multiple IP address (multi-homed network address cards).</span></span> <span data-ttu-id="c347b-121">SQL Server가 특정 IP 주소로만 수신 대기하고(개별 주소 또는 서브넷별) 특정 프로토콜만 사용하도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c347b-121">You can specify that SQL Server listen only to specific IP addresses (individual address or by subnet) and only use specific protocols.</span></span>
    
      - <span data-ttu-id="c347b-122">Lync Server 2013는 정적 및 동적 SQL Server 포트를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c347b-122">Lync Server 2013 supports static and dynamic SQL Server ports.</span></span>

  - <span data-ttu-id="c347b-123">정적(기본값이 아님) 포트에서 SQL Server를 실행하고 수신 대기 포트를 클라이언트에 보고할 수 없도록 SQL Server 브라우저는 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c347b-123">Run SQL Server on a static (non-default) port, and do not run SQL Server Browser (so it cannot report the listening port to the client).</span></span> <span data-ttu-id="c347b-124">이를 위해서는 프런트 엔드 서버, 모니터링 서버, 보관 서버 및 관리 콘솔 (Lync Server 관리 셸, Lync Server 제어판 또는 토폴로지 작성기 실행)을 비롯 한 각 SQL Server 클라이언트에 사용자 지정 구성이 필요 합니다. Lync Server 데이터베이스를 실행 하는 서버)</span><span class="sxs-lookup"><span data-stu-id="c347b-124">This requires a custom configuration on each SQL Server client, including Front End Servers, Monitoring Server, Archiving Server, and administrative consoles (running Lync Server Management Shell, Lync Server Control Panel, or Topology Builder), and all other servers running Lync Server databases).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c347b-125">데이터베이스에 대한 액세스는 신뢰할 수 있는 데이터베이스 관리자로 제한해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c347b-125">Access to databases must be limited to trusted database administrators.</span></span> <span data-ttu-id="c347b-126">악의적인 데이터베이스 관리자가 데이터베이스 관리자가 직접 액세스 권한을 부여 하지 않은 경우에도 Lync Server 2013 서버에 대 한 권한을 얻거나 서비스에서 중요 한 정보를 가져올 수 있도록 데이터베이스에 데이터를 삽입 하거나 수정 하는 것이 가능 합니다. Lync Server 2013 서버를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="c347b-126">A malicious database administrator could insert or modify data into the databases to acquire privileges over the Lync Server 2013 servers or obtain sensitive information from the services, even if the database administrator has not been granted direct access or control of the Lync Server 2013 servers.</span></span>



</div>

<span data-ttu-id="c347b-127">사용자 지정 구성에 대 한 자세한 내용과 SQL Server 데이터베이스를 강화 하는 방법에 대 한 자세한 내용은 다음 홉 blog 문서 "사용자 지정 SQL Server 네트워크 구성으로 [https://go.microsoft.com/fwlink/p/?LinkId=214008](https://go.microsoft.com/fwlink/p/?linkid=214008)Lync Server 2010 사용"을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c347b-127">For details about custom configurations and hardening SQL Server databases, see the NextHop blog article, "Using Lync Server 2010 with a Custom SQL Server Network Configuration," at [https://go.microsoft.com/fwlink/p/?LinkId=214008](https://go.microsoft.com/fwlink/p/?linkid=214008).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c347b-128">운영 체제 및 응용 프로그램 서버를 강화 하 고, 그룹 정책을 사용 하 여 Lync Server 배포에서 보안 잠금을을 구현할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c347b-128">You can also harden operating systems and applications servers, and you can use Group Policy to implement security lockdowns in your Lync Server deployment.</span></span> <span data-ttu-id="c347b-129">자세한 내용은 <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Lync Server 2013에 대 한 서버 및 응용 프로그램 강화 및 보호</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c347b-129">For details, see <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Hardening and protecting servers and applications for Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

