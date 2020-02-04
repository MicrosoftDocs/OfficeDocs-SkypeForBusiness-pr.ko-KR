---
title: 'Lync Server 2013: 백업 및 복원 프로세스 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration process overview
ms:assetid: e0f23b21-070f-4df5-b795-cea2f5338d85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202192(v=OCS.15)
ms:contentKeyID: 51541524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 559ebb5a5d5ba91b5a4952037c18ad509ed5cec7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728958"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a><span data-ttu-id="cf2b5-102">Lync Server 2013의 백업 및 복원 프로세스 개요</span><span class="sxs-lookup"><span data-stu-id="cf2b5-102">Backup and restoration process overview for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf2b5-103">_**마지막으로 수정한 주제:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="cf2b5-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="cf2b5-104">이 섹션에서는 Lync Server 2013의 백업 및 복원 프로세스가 작동 하는 방식에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b5-104">This section provides an overview of how the backup and restoration process works for Lync Server 2013.</span></span> <span data-ttu-id="cf2b5-105">위치에 관계 없이 모든 스탠더드 버전 서버와 Enterprise Edition 서버에 동일한 프로세스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b5-105">You use the same process for all Standard Edition servers and Enterprise Edition servers, regardless of their location.</span></span>

<span data-ttu-id="cf2b5-106">일반적으로 백업 프로세스가 작동 하는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b5-106">In general, the backup process works as follows:</span></span>

  - <span data-ttu-id="cf2b5-107">풀에 속하지 않는 독립 실행형 컴퓨터에서 백업 위치를 공유 폴더로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b5-107">You create a backup location as a shared folder on a stand-alone computer that is not part of any pool.</span></span> <span data-ttu-id="cf2b5-108">백업의 위치 **$Backup**에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b5-108">The location of the backup is referenced in **$Backup**.</span></span>

  - <span data-ttu-id="cf2b5-109">정기적으로 예약 된 시간에는 lync server [2013의 백업 및 복원 요구 사항](lync-server-2013-backup-and-restoration-requirements-data.md) 에 설명 된 모든 파일 저장소와 lync server [2013](lync-server-2013-backing-up-lync-server.md) 에서 설명 하는 절차에 따라 데이터를 백업 합니다. 중앙 관리 저장소에는 모든 서버 설정 및 구성이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b5-109">On a regular, scheduled basis, you back up all the Lync Server databases and all the file stores that are described in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md) by following the procedures described in [Backing up Lync Server 2013](lync-server-2013-backing-up-lync-server.md) The Central Management store includes all the server settings and configurations.</span></span>

  - <span data-ttu-id="cf2b5-110">후속 백업을 실행할 때마다 새 공유 폴더를 만들고 참조를 **$Backup** 하는 경로를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b5-110">Each time you run a subsequent backup, you create a new shared folder and change the path that **$Backup** references.</span></span>

<span data-ttu-id="cf2b5-111">일반적으로 복원 프로세스는 아래와 같이 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b5-111">In general, the restoration process works as follows:</span></span>

  - <span data-ttu-id="cf2b5-112">장애가 발생 하거나 중단 되 면 **$Backup** 에서 참조 하는 위치에 있는 데이터를 새 컴퓨터 또는 깨끗 한 컴퓨터로 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b5-112">When a failure or outage occurs, you restore the data in the location referenced by **$Backup** to new or clean computers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cf2b5-113">이 복원 프로세스는 데이터를 기존 서버 상태로 복원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b5-113">This restoration process does not restore data onto an existing server state.</span></span> <span data-ttu-id="cf2b5-114">즉,이 프로세스에서는 서버가 깨끗 하거나 새로운 것 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b5-114">That is, this process requires that the server is clean or new.</span></span>

    
    </div>

  - <span data-ttu-id="cf2b5-115">사용자와 회의 정보를 실패 시점으로 복구할 수 있도록 하기 위해 [Lync Server 2013의 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)에서 설명한 대로 쌍 프런트 엔드 풀을 사용 하 여 재해 복구 토폴로지를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b5-115">To enable your user and conference information to be recoverable to the point of failure, you can implement a disaster recovery topology with paired Front End pools, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="cf2b5-116">모든 DNS (도메인 이름 시스템) 구성, DHCP (동적 호스트 구성 프로토콜) 구성, 도메인 이름, 컴퓨터의 Fqdn (정규화 된 도메인 이름), 파일 저장소 경로 등은 당시 복원 당시 동일 해야 합니다. 뒷받침하다.</span><span class="sxs-lookup"><span data-stu-id="cf2b5-116">All Domain Name System (DNS) configuration, Dynamic Host Configuration Protocol (DHCP) configuration, domain names, computer fully qualified domain names (FQDNs), file store paths, and so on must be the same at the time of restoration that they were at the time of back up.</span></span>

<span data-ttu-id="cf2b5-117">Lync Server를 실행 하는 서버에 장애가 발생 하는 경우 복구에는 다음 단계가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b5-117">If a server running Lync Server fails, recovery includes the following steps:</span></span>

  - <span data-ttu-id="cf2b5-118">실패 한 컴퓨터와 FQDN이 같은 새 컴퓨터 또는 깨끗 한 시스템에 운영 체제를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b5-118">Install the operating system on a new or clean computer with the same FQDN as the failed computer.</span></span>

  - <span data-ttu-id="cf2b5-119">인증서를 다시 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b5-119">Reinstall certificates.</span></span>

  - <span data-ttu-id="cf2b5-120">서버에서 데이터베이스를 호스트 하는 경우 Microsoft SQL Server 2012 또는 Microsoft SQL Server 2008 R2를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b5-120">If the server hosted a database, install Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2.</span></span>

  - <span data-ttu-id="cf2b5-121">일반적으로 서버가 데이터베이스를 호스트 하는 경우 토폴로지 작성기를 실행 하 여 데이터베이스를 만들고 설치 하 고 Acl (액세스 제어 목록)을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b5-121">In general, if the server hosted a database, run Topology Builder to create and install the database and set up access control lists (ACLs).</span></span>

  - <span data-ttu-id="cf2b5-122">일반적으로 서버가 서버 역할을 호스트 하는 경우 Lync Server 배포 마법사의 1 단계 ~ 4 단계를 실행 하 여 로컬 구성 파일을 설치 하 고, 서버 역할 구성 요소를 설치 하 고, 인증서를 할당 하 고, 서비스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b5-122">In general, if the server hosted a server role, run step 1 through step 4 of the Lync Server Deployment Wizard to install the local configuration files, install the server role components, assign certificates, and start the services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cf2b5-123">서버에서 서버 역할을 collocated 데이터베이스를 호스트 하는 경우 Lync Server 배포 마법사의 2 단계를 실행 하 여 데이터베이스를 다시 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b5-123">If the server hosted a database collocated with the server role, running step 2 of the Lync Server Deployment Wizard recreates the database.</span></span>

    
    </div>

  - <span data-ttu-id="cf2b5-124">서버에서 데이터베이스를 호스트 하는 경우 백업 된 데이터를 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf2b5-124">If the server hosted a database, restore the backed up data.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

