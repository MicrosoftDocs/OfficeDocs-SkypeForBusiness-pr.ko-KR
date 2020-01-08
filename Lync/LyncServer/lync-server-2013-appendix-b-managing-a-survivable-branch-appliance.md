---
title: 'Lync Server 2013: 부록 B: SBA(Survivable Branch Appliance) 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Appendix B: Managing a Survivable Branch Appliance'
ms:assetid: 2ec9d505-6d39-491c-9524-8cf36866b855
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425797(v=OCS.15)
ms:contentKeyID: 48183773
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e267f81327e9d1f49b81ab0d999c37c02da55b31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984454"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appendix-b-managing-a-survivable-branch-appliance-in-lync-server-2013"></a><span data-ttu-id="f10ad-102">부록 B: Lync Server 2013에서 SBA(Survivable Branch Appliance) 관리</span><span class="sxs-lookup"><span data-stu-id="f10ad-102">Appendix B: Managing a Survivable Branch Appliance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f10ad-103">_**마지막으로 수정한 주제:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="f10ad-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="f10ad-104">이 항목에서는 Survivable Branch 기기를 관리 하는 절차에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ad-104">This topic describes the procedures for managing a Survivable Branch Appliance.</span></span> <span data-ttu-id="f10ad-105">특히 Survivable Branch 기기를 바꾸거나 이름을 바꾸는 방법 및 Survivable 분기 기기가 연결 된 Lync Server 2013 프런트 엔드 풀을 변경 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ad-105">Specifically, how to replace and rename a Survivable Branch Appliance, and how to change the Lync Server 2013 Front End pool that the Survivable Branch Appliance is associated with.</span></span>

<div>

## <a name="to-replace-a-survivable-branch-appliance"></a><span data-ttu-id="f10ad-106">Survivable Branch 기기를 바꾸려면</span><span class="sxs-lookup"><span data-stu-id="f10ad-106">To Replace a Survivable Branch Appliance</span></span>

1.  <span data-ttu-id="f10ad-107">Survivable Branch 기기에서 모든 Lync Server 2013 서비스를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ad-107">Stop all Lync Server 2013 services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="f10ad-108">(Survivable Branch 기기 공급 업체 문서를 참조 하세요.)</span><span class="sxs-lookup"><span data-stu-id="f10ad-108">(See the Survivable Branch Appliance vendor documentation.)</span></span>

2.  <span data-ttu-id="f10ad-109">권장 도메인에서 Survivable Branch 기기를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ad-109">(Recommended) Remove the Survivable Branch Appliance from the domain.</span></span>

3.  <span data-ttu-id="f10ad-110">Active Directory 도메인 서비스에서 Survivable Branch 기기 컴퓨터 개체를 삭제 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="f10ad-110">Delete the Survivable Branch Appliance computer object in Active Directory Domain Services, by following these steps:</span></span>
    
      - <span data-ttu-id="f10ad-111">엔터프라이즈 관리자 그룹의 구성원으로 구성원 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ad-111">Log on to a member server as a member of the Enterprise Admins group.</span></span>
    
      - <span data-ttu-id="f10ad-112">**시작**을 클릭 하 고 **관리 도구**를 클릭 한 다음 **Active Directory 사용자 및 컴퓨터**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ad-112">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
    
      - <span data-ttu-id="f10ad-113">Survivable Branch 기기 개체를 마우스 오른쪽 단추로 클릭 하 고 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ad-113">Right-click the Survivable Branch Appliance object, and click **Delete**.</span></span>

4.  <span data-ttu-id="f10ad-114">Survivable Branch 기기 컴퓨터 개체를 다시 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ad-114">Add the Survivable Branch Appliance computer object again.</span></span> <span data-ttu-id="f10ad-115">( [Lync Server 2013에서 Active Directory에 Survivable Branch 기기 추가를](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)참조 하세요.)</span><span class="sxs-lookup"><span data-stu-id="f10ad-115">(See [Add a Survivable Branch Appliance to Active Directory in Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).)</span></span>

5.  <span data-ttu-id="f10ad-116">Active Directory 복제가 수행 될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="f10ad-116">Wait for Active Directory replication to take place.</span></span>

6.  <span data-ttu-id="f10ad-117">Lync Server Management Shell을 열고 **Enable-CSTopology**를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ad-117">Open the Lync Server Management Shell, and type **Enable-CSTopology**.</span></span>

7.  <span data-ttu-id="f10ad-118">새 Survivable Branch 기기를 네트워크에 연결 하 고 [Lync server 2013를 사용 하 여 Survivable Branch 기기 또는 서버 배포](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) 의 단계를 따르고, [lync server 2013-지사 사이트 작업으로 Survivable Branch 기기 또는 서버를 배포](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ad-118">Connect the new Survivable Branch Appliance to the network, and follow the steps in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) and [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span></span>

</div>

<div>

## <a name="to-rename-a-survivable-branch-appliance"></a><span data-ttu-id="f10ad-119">Survivable Branch 기기 이름 바꾸기</span><span class="sxs-lookup"><span data-stu-id="f10ad-119">To Rename a Survivable Branch Appliance</span></span>

1.  <span data-ttu-id="f10ad-120">사용자를 중앙 사이트로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ad-120">Move users to the central site.</span></span> <span data-ttu-id="f10ad-121">자세한 내용은 [Lync Server 2013에서 다른 풀로 사용자 이동을](lync-server-2013-move-users-to-another-pool.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f10ad-121">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

2.  <span data-ttu-id="f10ad-122">Survivable Branch 기기에서 모든 Lync Server 2013 서비스를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ad-122">Stop all Lync Server 2013 services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="f10ad-123">(Survivable Branch 기기 공급 업체 문서를 참조 하세요.)</span><span class="sxs-lookup"><span data-stu-id="f10ad-123">(See the Survivable Branch Appliance vendor documentation.)</span></span>

3.  <span data-ttu-id="f10ad-124">다음 단계에 따라 토폴로지에서 Survivable Branch 기기를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ad-124">Remove the Survivable Branch Appliance from the topology, by following these steps:</span></span>
    
      - <span data-ttu-id="f10ad-125">**시작**을 클릭 하 고 **모든 프로그램**, **Microsoft Lync server**를 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ad-125">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="f10ad-126">콘솔 트리에서 **지점 사이트**를 확장 하 고 Survivable Branch 기기를 클릭 한 다음 작업 창에서 **삭제** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ad-126">In the console tree, expand **Branch Sites**, click the Survivable Branch Appliance, and then click **Delete** on the Action pane.</span></span>

4.  <span data-ttu-id="f10ad-127">도메인에서 Survivable Branch 기기를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ad-127">Remove the Survivable Branch Appliance from the domain.</span></span>

5.  <span data-ttu-id="f10ad-128">Active Directory에서 Survivable Branch 기기 컴퓨터 개체를 삭제 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="f10ad-128">Delete the Survivable Branch Appliance computer object in Active Directory, by following these steps:</span></span>
    
      - <span data-ttu-id="f10ad-129">엔터프라이즈 관리자 그룹의 구성원으로 도메인 컨트롤러에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ad-129">Log on to a domain controller as a member of the Enterprise Admins group.</span></span>
    
      - <span data-ttu-id="f10ad-130">**시작**을 클릭 하 고 **관리 도구**를 클릭 한 다음 **Active Directory 사용자 및 컴퓨터**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ad-130">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
    
      - <span data-ttu-id="f10ad-131">Survivable Branch 기기 개체를 마우스 오른쪽 단추로 클릭 하 고 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ad-131">Right-click the Survivable Branch Appliance object, and click **Delete**.</span></span>

6.  <span data-ttu-id="f10ad-132">Survivable Branch 기기를 출하시 기본값으로 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ad-132">Restore the Survivable Branch Appliance to factory defaults.</span></span> <span data-ttu-id="f10ad-133">(Survivable Branch 기기 공급 업체 문서를 참조 하세요.)</span><span class="sxs-lookup"><span data-stu-id="f10ad-133">(See the Survivable Branch Appliance vendor documentation.)</span></span>

7.  <span data-ttu-id="f10ad-134">[Lync server 2013를 사용 하 여 Survivable Branch 기기 또는 서버 배포](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) 의 단계를 따르고 [lync server 2013-지사 사이트 작업을 사용 하 여 Survivable Branch 기기 또는 서버를 배포](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ad-134">Follow the steps in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) and [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span></span>

8.  <span data-ttu-id="f10ad-135">이름을 바꾼 Survivable Branch 기기로 사용자를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ad-135">Move users to the renamed Survivable Branch Appliance.</span></span> <span data-ttu-id="f10ad-136">자세한 내용은 [Lync Server 2013에서 다른 풀로 사용자 이동을](lync-server-2013-move-users-to-another-pool.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f10ad-136">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

</div>

<div>

## <a name="to-change-the-lync-server-front-end-pool-that-the-survivable-branch-appliance-is-associated-with"></a><span data-ttu-id="f10ad-137">Survivable 분기 기기가 연결 된 Lync Server 프런트 엔드 풀을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="f10ad-137">To Change the Lync Server Front End Pool that the Survivable Branch Appliance Is Associated With</span></span>

1.  <span data-ttu-id="f10ad-138">Survivable Branch 기기에서 중앙 사이트의 Lync Server 프런트 엔드 풀로 사용자를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ad-138">Move users from the Survivable Branch Appliance to the Lync Server Front End pool at the central site.</span></span> <span data-ttu-id="f10ad-139">자세한 내용은 [Lync Server 2013에서 다른 풀로 사용자 이동을](lync-server-2013-move-users-to-another-pool.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f10ad-139">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

2.  <span data-ttu-id="f10ad-140">Survivable Branch 기기에서 모든 Lync Server 서비스를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ad-140">Stop all Lync Server services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="f10ad-141">(Survivable Branch 기기 공급 업체 문서를 참조 하세요.)</span><span class="sxs-lookup"><span data-stu-id="f10ad-141">(See the Survivable Branch Appliance vendor documentation).</span></span>

3.  <span data-ttu-id="f10ad-142">다음 단계에 따라 Survivable 분기 기기가 연결 된 Lync Server 프런트 엔드 풀을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ad-142">Update the Lync Server Front End pool that the Survivable Branch Appliance is associated with, by following these steps:</span></span>
    
      - <span data-ttu-id="f10ad-143">**시작**을 클릭 하 고 **모든 프로그램**, **Microsoft Lync server**를 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ad-143">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="f10ad-144">**지점 사이트**를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ad-144">Expand **Branch Sites**.</span></span>
    
      - <span data-ttu-id="f10ad-145">수정할 Survivable Branch 기기 개체를 마우스 오른쪽 단추로 클릭 하 고 **속성 편집** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ad-145">Right-click the Survivable Branch Appliance object to modify, and click **Edit Properties**</span></span>
    
      - <span data-ttu-id="f10ad-146">회복성에서 Survivable Branch 기기를 연결할 새 프런트 엔드 풀을 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ad-146">Under Resiliency, select the new Front End pool the Survivable Branch Appliance is to be associated to, and then click **Next**.</span></span>
    
      - <span data-ttu-id="f10ad-147">콘솔 트리에서 새 Survivable Branch 기기를 마우스 오른쪽 단추로 클릭 하 고 **토폴로지**를 클릭 한 다음 **게시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ad-147">In the console tree, right-click the new Survivable Branch Appliance, click **Topology**, and then click **Publish**.</span></span>

4.  <span data-ttu-id="f10ad-148">Survivable Branch 기기에서 모든 Lync Server 서비스를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ad-148">Restart all Lync Server Services on the Survivable Branch Appliance.</span></span>

5.  <span data-ttu-id="f10ad-149">Survivable Branch 기기를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ad-149">Test the Survivable Branch Appliance.</span></span> <span data-ttu-id="f10ad-150">자세한 내용은 [Lync Server 2013에서 Survivable Branch 기기 또는 서버의 가정용 사용자](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f10ad-150">For details, see [Home users on a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span></span>

6.  <span data-ttu-id="f10ad-151">중앙 사이트의 Lync Server 프런트 엔드 풀에서 Survivable Branch 기기로 사용자를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10ad-151">Move users from the Lync Server Front End pool at the central site to the Survivable Branch Appliance.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

