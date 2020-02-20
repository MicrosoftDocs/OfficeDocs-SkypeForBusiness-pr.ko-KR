---
title: 'Lync Server 2013: 영구 채팅 서버 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Persistent Chat Server
ms:assetid: e3b930fb-6855-47f0-b6b3-7dfae386540d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205357(v=OCS.15)
ms:contentKeyID: 48185717
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83a23190033bca9047a3d1a6d70b914d02017db8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="b4af3-102">Lync Server 2013에서 영구 채팅 서버 배포</span><span class="sxs-lookup"><span data-stu-id="b4af3-102">Deploying Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4af3-103">_**마지막으로 수정 된 항목:** 2014-03-31_</span><span class="sxs-lookup"><span data-stu-id="b4af3-103">_**Topic Last Modified:** 2014-03-31_</span></span>

<span data-ttu-id="b4af3-104">Lync Server 2013, 영구 채팅 서버는 Lync Server 2013 인프라의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-104">Lync Server 2013, Persistent Chat Server is part of the Lync Server 2013 infrastructure.</span></span>

<span data-ttu-id="b4af3-105">영구 채팅 서버를 배포 하려면 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-105">Deploying Persistent Chat Server requires that you:</span></span>

  - <span data-ttu-id="b4af3-106">토폴로지 작성기를 사용 하 여 배포 하려는 토폴로지 및 구성 요소를 정의 하거나 가져온 후에 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-106">Use Topology Builder to define, or import, and subsequently publish your topology and the components that you want to deploy.</span></span>

  - <span data-ttu-id="b4af3-107">영구 채팅 서버 구성 요소를 배포 하기 위한 환경을 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-107">Prepare your environment for deploying Persistent Chat Server components.</span></span>

  - <span data-ttu-id="b4af3-108">배포에 대해 영구 채팅 서버 구성 요소를 설치 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-108">Install and configure Persistent Chat Server components for your deployment.</span></span>

<span data-ttu-id="b4af3-109">영구 채팅 서버는 Lync Server 2013 Enterprise Edition을 별도의 풀로 사용할 수 있습니다 (Enterprise Edition 프런트 엔드 서버와 배치 된가 아님).</span><span class="sxs-lookup"><span data-stu-id="b4af3-109">Persistent Chat Server is available with Lync Server 2013 Enterprise Edition as a separate pool (not collocated with the Enterprise Edition Front End Servers).</span></span> <span data-ttu-id="b4af3-110">영구 채팅 서버에는 대화방 콘텐츠 및 기타 관련 메타 데이터를 저장 하기 위한 Enterprise Edition 풀의 SQL Server 백 엔드 서버가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-110">Persistent Chat Server requires a SQL Server Back End Server in your Enterprise Edition pool to store the chat room content and other relevant metadata.</span></span> <span data-ttu-id="b4af3-111">배치 Lync Server 2013 백 엔드 서버와 **PersistentChatStore** 이 동일한 SQL server 인스턴스에 지원 되기는 하지만 **PERSISTENTCHATSTORE** 을 전용 SQL server 백 엔드 서버에 설치 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-111">We recommend that you install the **PersistentChatStore** on a dedicated SQL Server Back End Server, although collocating Lync Server 2013 Back End Server and **PersistentChatStore** on the same SQL Server instance is supported.</span></span>

<span data-ttu-id="b4af3-112">또한 영구 채팅 서버는 Lync Server 2013 Standard Edition과 함께 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-112">Persistent Chat Server can also be deployed with Lync Server 2013 Standard Edition.</span></span> <span data-ttu-id="b4af3-113">이 경우 **PersistentChatService** 프런트 엔드 서버가 Standard Edition 컴퓨터에서 배치 된 되 고, **PersistentChatStore** 백 엔드 서버는 로컬 SQL Server Express 인스턴스에 배포 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-113">In this case, the **PersistentChatService** Front End Server is collocated on the Standard Edition computer, and the **PersistentChatStore** Back End Server can be deployed on the local SQL Server Express instance.</span></span>

<span data-ttu-id="b4af3-114">지원 되는 위치 구성에 대 한 자세한 내용은 [Lync server 2013에서 지원 되는 서버 위치](lync-server-2013-supported-server-collocation.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b4af3-114">For details about supported colocation configurations, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b4af3-115">영구 채팅 서버&nbsp;Standard Edition에 대 한 고가용성은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-115">We do not support high availability for Persistent Chat Server&nbsp;Standard Edition.</span></span> <span data-ttu-id="b4af3-116">성능 및 확장 기능은 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-116">Performance and scale will be limited.</span></span> <span data-ttu-id="b4af3-117">또한 새 영구 채팅 서버&nbsp;Standard Edition 서버만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-117">Furthermore, we support only new Persistent Chat Server&nbsp;Standard Edition server.</span></span> <span data-ttu-id="b4af3-118">Lync Server 2010, 그룹 채팅 서버를 Lync Server 2013&nbsp;영구 채팅 서버&nbsp;Standard Edition으로 업그레이드 하는 것은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-118">We do not support upgrading Lync Server 2010, Group Chat Server to a Lync Server 2013&nbsp;Persistent Chat Server&nbsp;Standard Edition.</span></span>



</div>

<span data-ttu-id="b4af3-119">조직에서 준수 지원이 필요한 경우 영구 채팅 서버 프런트 엔드 서버에 영구 채팅 서버 준수 서비스를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-119">If your organization requires compliance support, you can install the Persistent Chat Server Compliance service on the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="b4af3-120">준수용으로 별도의 데이터베이스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-120">A separate database is required for compliance.</span></span>

<span data-ttu-id="b4af3-121">적어도 각 토폴로지에는 Lync Server 2013이 설치 된 서버와 SQL Server 데이터베이스 소프트웨어가 설치 된 서버가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-121">At a minimum, each topology requires a server with Lync Server 2013 installed and a server with SQL Server database software installed.</span></span>

<span data-ttu-id="b4af3-122">토폴로지 작성기를 사용 하 여 Lync Server 2013 배포에 영구 채팅 서버를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-122">Use Topology Builder to add Persistent Chat Server to your Lync Server 2013 deployments.</span></span> <span data-ttu-id="b4af3-123">토폴로지 작성기를 사용 하 여 하나 이상의 영구 채팅 서버 풀을 추가 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-123">You can choose to add one or more Persistent Chat Server pools using Topology Builder.</span></span> <span data-ttu-id="b4af3-124">모든 풀에 대해 수행 하는 것과 동일한 배포 지침을 따라 여러 영구 채팅 서버 풀을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-124">Follow the same deployment instructions for deploying multiple Persistent Chat Server pools as you would for any pool.</span></span> <span data-ttu-id="b4af3-125">자세한 내용은 배포 설명서의 [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b4af3-125">For details, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="b4af3-126">사용할 수 있는 토폴로지와 영구 채팅 서버 설치를 위한 기술 및 소프트웨어 요구 사항에 대 한 자세한 내용은 계획 설명서의 [2013 lync](lync-server-2013-planning-for-persistent-chat-server.md) server 2013에서 영구 채팅 서버 [작동 방식](lync-server-2013-how-persistent-chat-server-works.md) , 계획 설명서, 배포 설명서 또는 작업 설명서에서 [지원 되는 2013 하드웨어](lync-server-2013-supported-hardware.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b4af3-126">For details about available topologies and the technical and software requirements for installing Persistent Chat Server, see [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in the Planning documentation, [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation, and [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation.</span></span>

<span data-ttu-id="b4af3-127">인증서 획득, SQL Server 데이터베이스 만들기 및 파일 저장소 만들기에 대 한 자세한 내용은 배포 설명서에서 [Lync Server 2013 배포](lync-server-2013-deploying-lync-server.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b4af3-127">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="b4af3-128">단일 영구 채팅 서버 프런트 엔드 서버는 2만 활성 사용자를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-128">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="b4af3-129">총 8만 동시 사용자를 지 원하는 최대 4 개의 활성 프런트 엔드 서버와 영구 채팅 서버 풀을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-129">You can have a Persistent Chat Server pool with up to 4 active Front End Servers supporting a total of 80,000 concurrent users.</span></span>

<span data-ttu-id="b4af3-130">영구 채팅 서버는 가상 서버 에서도 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-130">Persistent Chat Server is also supported on a virtual server.</span></span> <span data-ttu-id="b4af3-131">가상 서버는 실제 서버의 사양과 일치할 경우 최대 20,000명의 동시 사용자를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-131">The virtual server can support up to 20,000 concurrent users if it matches the specifications of the physical server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b4af3-132">파일 시스템 보안을 강화 하려면 영구 채팅 서버를 NTFS 파일 시스템에 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-132">Persistent Chat Server must be installed on an NTFS file system to help enforce file system security.</span></span> <span data-ttu-id="b4af3-133">영구 채팅 서버에 대해 지원 되는 파일 시스템이 FAT32가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b4af3-133">FAT32 is not a supported file system for Persistent Chat Server.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b4af3-134">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="b4af3-134">In This Section</span></span>

  - [<span data-ttu-id="b4af3-135">Lync Server 2013에서 영구 채팅 서버가 작동 하는 방식</span><span class="sxs-lookup"><span data-stu-id="b4af3-135">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="b4af3-136">Lync Server 2013의 영구 채팅 서버에 대 한 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="b4af3-136">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

  - [<span data-ttu-id="b4af3-137">Lync Server 2013의 영구 채팅 서버에 대 한 기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="b4af3-137">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="b4af3-138">Lync Server 2013의 영구 채팅 서버에 대 한 시스템 및 인프라 설정</span><span class="sxs-lookup"><span data-stu-id="b4af3-138">Setting up systems and infrastructure for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [<span data-ttu-id="b4af3-139">Lync Server 2013에서 배포에 영구 채팅 서버 추가</span><span class="sxs-lookup"><span data-stu-id="b4af3-139">Adding Persistent Chat Server to your deployment in Lync Server 2013</span></span>](lync-server-2013-adding-persistent-chat-server-to-your-deployment.md)

  - [<span data-ttu-id="b4af3-140">Lync Server 2013에 영구 채팅 서버 설치</span><span class="sxs-lookup"><span data-stu-id="b4af3-140">Installing Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-installing-persistent-chat-server.md)

  - [<span data-ttu-id="b4af3-141">Lync Server 2013에서 영구 채팅 관리자 추가</span><span class="sxs-lookup"><span data-stu-id="b4af3-141">Adding a Persistent Chat administrator in Lync Server 2013</span></span>](lync-server-2013-adding-a-persistent-chat-administrator.md)

  - [<span data-ttu-id="b4af3-142">Lync Server 2013에서 영구 채팅 서버 구성</span><span class="sxs-lookup"><span data-stu-id="b4af3-142">Configuring Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server.md)

  - [<span data-ttu-id="b4af3-143">Windows PowerShell cmdlet을 사용 하 여 영구 채팅 서버 구성</span><span class="sxs-lookup"><span data-stu-id="b4af3-143">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</span></span>](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="b4af3-144">Lync Server 2013에서 Windows PowerShell cmdlet을 사용 하 여 영구 채팅 서버 구성 문제 해결</span><span class="sxs-lookup"><span data-stu-id="b4af3-144">Troubleshooting Persistent Chat Server configuration using Windows PowerShell cmdlets in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md)

  - [<span data-ttu-id="b4af3-145">Lync Server 2013에서 고가용성 및 재해 복구를 위한 영구 채팅 서버 구성</span><span class="sxs-lookup"><span data-stu-id="b4af3-145">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="b4af3-146">Lync Server 2013에서 영구 채팅 서버 장애 조치 및 장애 복구 (failback)</span><span class="sxs-lookup"><span data-stu-id="b4af3-146">Failing over and failing back Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-failing-over-and-failing-back-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

