---
title: 'Lync Server 2013: 부록 B: Sba (survivable Branch 어플라이언스 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Appendix B: Managing a Survivable Branch Appliance'
ms:assetid: 2ec9d505-6d39-491c-9524-8cf36866b855
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425797(v=OCS.15)
ms:contentKeyID: 48183773
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df6e2dc473da81177dacb8d53ee673c9a5457c98
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="appendix-b-managing-a-survivable-branch-appliance-in-lync-server-2013"></a><span data-ttu-id="3f883-102">부록 B: Lync Server 2013에서 Sba (survivable 분기 기기 관리</span><span class="sxs-lookup"><span data-stu-id="3f883-102">Appendix B: Managing a Survivable Branch Appliance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f883-103">_**마지막으로 수정 된 항목:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="3f883-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="3f883-104">이 항목에서는 Sba (survivable 분기 어플라이언스를 관리 하는 절차에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-104">This topic describes the procedures for managing a Survivable Branch Appliance.</span></span> <span data-ttu-id="3f883-105">특히 Sba (survivable 분기 어플라이언스를 교체 하 고 이름을 바꾸는 방법 및 Sba (survivable 분기 기기가 연결 된 Lync Server 2013 프런트 엔드 풀을 변경 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-105">Specifically, how to replace and rename a Survivable Branch Appliance, and how to change the Lync Server 2013 Front End pool that the Survivable Branch Appliance is associated with.</span></span>

<div>

## <a name="to-replace-a-survivable-branch-appliance"></a><span data-ttu-id="3f883-106">SBA(Survivable Branch Appliance)를 대체하려면</span><span class="sxs-lookup"><span data-stu-id="3f883-106">To Replace a Survivable Branch Appliance</span></span>

1.  <span data-ttu-id="3f883-107">Sba (survivable Branch 기기에서 모든 Lync Server 2013 서비스를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-107">Stop all Lync Server 2013 services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="3f883-108">자세한 내용은 SBA(Survivable Branch Appliance) 공급업체 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3f883-108">(See the Survivable Branch Appliance vendor documentation.)</span></span>

2.  <span data-ttu-id="3f883-109">는 도메인에서 Sba (survivable Branch 기기를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-109">(Recommended) Remove the Survivable Branch Appliance from the domain.</span></span>

3.  <span data-ttu-id="3f883-110">다음 단계를 수행 하 여 Active Directory 도메인 서비스에서 Sba (survivable Branch 기기 computer 개체를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-110">Delete the Survivable Branch Appliance computer object in Active Directory Domain Services, by following these steps:</span></span>
    
      - <span data-ttu-id="3f883-111">Enterprise Admins 그룹의 구성원으로 구성원 서버에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-111">Log on to a member server as a member of the Enterprise Admins group.</span></span>
    
      - <span data-ttu-id="3f883-112">**시작**, **관리 도구**를 차례로 클릭한 다음 **Active Directory 사용자 및 컴퓨터**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-112">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
    
      - <span data-ttu-id="3f883-113">Sba (survivable Branch 기기 개체를 마우스 오른쪽 단추로 클릭 하 고 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-113">Right-click the Survivable Branch Appliance object, and click **Delete**.</span></span>

4.  <span data-ttu-id="3f883-114">Sba (survivable Branch 기기 컴퓨터 개체를 다시 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-114">Add the Survivable Branch Appliance computer object again.</span></span> <span data-ttu-id="3f883-115">( [Lync Server 2013에서 Active Directory에 Sba (survivable 분기 어플라이언스 추가](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)를 참조 하세요.)</span><span class="sxs-lookup"><span data-stu-id="3f883-115">(See [Add a Survivable Branch Appliance to Active Directory in Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).)</span></span>

5.  <span data-ttu-id="3f883-116">Active Directory 복제가 수행 될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-116">Wait for Active Directory replication to take place.</span></span>

6.  <span data-ttu-id="3f883-117">Lync Server 관리 셸을 열고 **Enable-enable-cstopology**을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-117">Open the Lync Server Management Shell, and type **Enable-CSTopology**.</span></span>

7.  <span data-ttu-id="3f883-118">새 Sba (survivable 분기 기기를 네트워크에 연결 하 고, [Sba (survivable Branch 기기 또는 server For Lync server 2013-중앙 사이트 작업](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) 을 배포 하 고 [, sba (survivable Branch 기기 또는 서버를 lync server 2013-Branch site task를 사용 하 여 배포](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)의 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-118">Connect the new Survivable Branch Appliance to the network, and follow the steps in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) and [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span></span>

</div>

<div>

## <a name="to-rename-a-survivable-branch-appliance"></a><span data-ttu-id="3f883-119">SBA(Survivable Branch Appliance)의 이름을 바꾸려면</span><span class="sxs-lookup"><span data-stu-id="3f883-119">To Rename a Survivable Branch Appliance</span></span>

1.  <span data-ttu-id="3f883-120">사용자를 중앙 사이트로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-120">Move users to the central site.</span></span> <span data-ttu-id="3f883-121">자세한 내용은 [Lync Server 2013의 다른 풀로 사용자 이동](lync-server-2013-move-users-to-another-pool.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3f883-121">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

2.  <span data-ttu-id="3f883-122">Sba (survivable Branch 기기에서 모든 Lync Server 2013 서비스를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-122">Stop all Lync Server 2013 services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="3f883-123">자세한 내용은 SBA(Survivable Branch Appliance) 공급업체 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3f883-123">(See the Survivable Branch Appliance vendor documentation.)</span></span>

3.  <span data-ttu-id="3f883-124">다음 단계를 수행 하 여 토폴로지에서 Sba (survivable Branch 기기를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-124">Remove the Survivable Branch Appliance from the topology, by following these steps:</span></span>
    
      - <span data-ttu-id="3f883-125">**시작**, **모든 프로그램**, **Microsoft Lync Server**를 차례로 클릭한 다음 **Lync Server 토폴로지 작성기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-125">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="3f883-126">콘솔 트리에서 **분기 사이트**를 확장 하 고 Sba (survivable Branch 기기를 클릭 한 다음 작업 창에서 **삭제** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-126">In the console tree, expand **Branch Sites**, click the Survivable Branch Appliance, and then click **Delete** on the Action pane.</span></span>

4.  <span data-ttu-id="3f883-127">도메인에서 Sba (survivable Branch 기기를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-127">Remove the Survivable Branch Appliance from the domain.</span></span>

5.  <span data-ttu-id="3f883-128">다음 단계를 수행 하 여 Active Directory에서 Sba (survivable Branch 기기 computer 개체를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-128">Delete the Survivable Branch Appliance computer object in Active Directory, by following these steps:</span></span>
    
      - <span data-ttu-id="3f883-129">Enterprise Admins 그룹의 구성원으로 도메인 컨트롤러에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-129">Log on to a domain controller as a member of the Enterprise Admins group.</span></span>
    
      - <span data-ttu-id="3f883-130">**시작**, **관리 도구**, **Active Directory 사용자 및 컴퓨터**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-130">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
    
      - <span data-ttu-id="3f883-131">Sba (survivable Branch 기기 개체를 마우스 오른쪽 단추로 클릭 하 고 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-131">Right-click the Survivable Branch Appliance object, and click **Delete**.</span></span>

6.  <span data-ttu-id="3f883-132">Sba (survivable 분기 어플라이언스를 출고시 기본값으로 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-132">Restore the Survivable Branch Appliance to factory defaults.</span></span> <span data-ttu-id="3f883-133">자세한 내용은 SBA(Survivable Branch Appliance) 공급업체 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3f883-133">(See the Survivable Branch Appliance vendor documentation.)</span></span>

7.  <span data-ttu-id="3f883-134">[Sba (survivable Branch 기기 또는 Lync server 2013을 사용](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) 하는 서버를 배포 하는 단계와 중앙 사이트 작업을 배포 하 고 [sba (survivable Branch 기기 또는 서버를 lync server 2013-Branch site task를 사용](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)하 여 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-134">Follow the steps in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) and [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span></span>

8.  <span data-ttu-id="3f883-135">이름이 바뀐 Sba (survivable Branch 기기로 사용자를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-135">Move users to the renamed Survivable Branch Appliance.</span></span> <span data-ttu-id="3f883-136">자세한 내용은 [Lync Server 2013의 다른 풀로 사용자 이동](lync-server-2013-move-users-to-another-pool.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3f883-136">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

</div>

<div>

## <a name="to-change-the-lync-server-front-end-pool-that-the-survivable-branch-appliance-is-associated-with"></a><span data-ttu-id="3f883-137">SBA(Survivable Branch Appliance)가 연결된 Lync Server 프런트 엔드 풀을 변경하려면</span><span class="sxs-lookup"><span data-stu-id="3f883-137">To Change the Lync Server Front End Pool that the Survivable Branch Appliance Is Associated With</span></span>

1.  <span data-ttu-id="3f883-138">Sba (survivable 분기 기기의 사용자를 중앙 사이트의 Lync Server 프런트 엔드 풀로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-138">Move users from the Survivable Branch Appliance to the Lync Server Front End pool at the central site.</span></span> <span data-ttu-id="3f883-139">자세한 내용은 [Lync Server 2013의 다른 풀로 사용자 이동](lync-server-2013-move-users-to-another-pool.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3f883-139">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

2.  <span data-ttu-id="3f883-140">Sba (survivable Branch 기기에서 모든 Lync Server 서비스를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-140">Stop all Lync Server services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="3f883-141">(Sba (survivable Branch 어플라이언스 공급 업체 설명서 참조).</span><span class="sxs-lookup"><span data-stu-id="3f883-141">(See the Survivable Branch Appliance vendor documentation).</span></span>

3.  <span data-ttu-id="3f883-142">다음 단계를 수행 하 여 Sba (survivable 분기 기기가 연결 된 Lync Server 프런트 엔드 풀을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-142">Update the Lync Server Front End pool that the Survivable Branch Appliance is associated with, by following these steps:</span></span>
    
      - <span data-ttu-id="3f883-143">**시작**, **모든 프로그램**, **Microsoft Lync Server**를 차례로 클릭한 다음 **Lync Server 토폴로지 작성기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-143">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="3f883-144">**분기 사이트**를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-144">Expand **Branch Sites**.</span></span>
    
      - <span data-ttu-id="3f883-145">수정할 Sba (survivable Branch 기기 개체를 마우스 오른쪽 단추로 클릭 하 고 **속성 편집** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-145">Right-click the Survivable Branch Appliance object to modify, and click **Edit Properties**</span></span>
    
      - <span data-ttu-id="3f883-146">복구에서 Sba (survivable 분기 기기가 연결 될 새 프런트 엔드 풀을 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-146">Under Resiliency, select the new Front End pool the Survivable Branch Appliance is to be associated to, and then click **Next**.</span></span>
    
      - <span data-ttu-id="3f883-147">콘솔 트리에서 새 Sba (survivable 분기 기기를 마우스 오른쪽 단추로 클릭 하 고 **토폴로지**를 클릭 한 다음 **게시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-147">In the console tree, right-click the new Survivable Branch Appliance, click **Topology**, and then click **Publish**.</span></span>

4.  <span data-ttu-id="3f883-148">Sba (survivable Branch 기기에서 모든 Lync Server 서비스를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-148">Restart all Lync Server Services on the Survivable Branch Appliance.</span></span>

5.  <span data-ttu-id="3f883-149">Sba (survivable Branch 기기를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-149">Test the Survivable Branch Appliance.</span></span> <span data-ttu-id="3f883-150">자세한 내용은 [Home users in a Sba (survivable Branch 어플라이언스 Or Server in a Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3f883-150">For details, see [Home users on a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span></span>

6.  <span data-ttu-id="3f883-151">중앙 사이트의 Lync Server 프런트 엔드 풀에서 Sba (survivable Branch 기기로 사용자를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f883-151">Move users from the Lync Server Front End pool at the central site to the Survivable Branch Appliance.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

