---
title: 'Lync Server 2013: 영구 채팅 서버 장애 복구(failback)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing back Persistent Chat Server
ms:assetid: 67b91de4-6ddc-43e6-9812-5e1aa84a7980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204970(v=OCS.15)
ms:contentKeyID: 48184396
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d79c25d153de81906fcaf9355a543d31cb8fe0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984119"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="72d48-102">Lync Server 2013에서 영구 채팅 서버 장애 복구(failback)</span><span class="sxs-lookup"><span data-stu-id="72d48-102">Failing back Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72d48-103">_**마지막으로 수정한 주제:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="72d48-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="72d48-104">이 절차에서는 영구 채팅 서버 오류에서 복구 하 고 기본 데이터 센터에서 작업을 다시 설정 하는 데 필요한 단계에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-104">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>

<span data-ttu-id="72d48-105">영구 채팅 서버 장애가 발생 한 경우 기본 데이터 센터에서 중단 되 고 기본 및 미러 데이터베이스를 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-105">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="72d48-106">주 데이터 센터가 백업 서버로 장애 조치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-106">The primary data center fails over to the backup server.</span></span>

<span data-ttu-id="72d48-107">다음 절차는 기본 데이터 센터를 백업한 후에 정상 작업을 복원 하 고 서버를 다시 작성 했습니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-107">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="72d48-108">이 절차에서는 기본 데이터 센터가 총 중단 으로부터 복구 되었고, mgc 데이터베이스와 mgccomp 데이터베이스가 토폴로지 작성기를 사용 하 여 다시 작성 되 고 다시 설치 되었다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-108">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>

<span data-ttu-id="72d48-109">또한이 절차에서는 장애 조치 기간 동안 새 미러 및 백업 서버가 배포 되지 않은 것으로 가정 하 고, [Lync server 2013의 영구 채팅 서버 장애](lync-server-2013-failing-over-persistent-chat-server.md)조치에 정의 된 대로 백업 서버와 미러 서버만 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-109">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in [Failing over Persistent Chat Server in Lync Server 2013](lync-server-2013-failing-over-persistent-chat-server.md).</span></span>

<span data-ttu-id="72d48-110">이러한 단계는 재해가 발생 하기 이전에 구성을 복구 하도록 설계 되었으며, 결과적으로 주 서버에서 백업 서버로 장애 조치를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-110">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>

<div>

## <a name="to-fail-back-persistent-chat-server"></a><span data-ttu-id="72d48-111">영구 채팅 서버에 장애 복구</span><span class="sxs-lookup"><span data-stu-id="72d48-111">To fail back Persistent Chat Server</span></span>

1.  <span data-ttu-id="72d48-112">Lync Server 관리 셸에서 cmdlet을 `Set-CsPersistentChatActiveServer` 사용 하 여 영구 채팅 서버 활성 서버 목록에서 모든 서버를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-112">Clear all servers from the Persistent Chat Server Active Server list by using the `Set-CsPersistentChatActiveServer` cmdlet from the Lync Server Management Shell.</span></span> <span data-ttu-id="72d48-113">이렇게 하면 장애 복구 하는 동안 mgc 데이터베이스 및 mgccomp 데이터베이스에 연결 하는 모든 영구 채팅 서버가 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-113">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="72d48-114">보조 영구 채팅 서버 백 엔드 서버의 SQL Server 에이전트는 특권 계정으로 실행 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-114">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="72d48-115">특히, 계정에는 다음이 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-115">Specifically, the account must include:</span></span> 
    > <UL>
    > <LI>
    > <P><span data-ttu-id="72d48-116">백업이 저장 되는 네트워크 공유에 대 한 읽기 액세스입니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-116">Read access to the network share that backups are being placed in.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="72d48-117">백업을 복사할 특정 로컬 디렉터리에 대 한 쓰기 액세스입니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-117">Write access to the specific local directory that the backups are being copied to.</span></span></P></LI></UL>

    
    </div>

2.  <span data-ttu-id="72d48-118">Backup mgc 데이터베이스에서 미러링을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-118">Disable mirroring on the backup mgc database:</span></span>
    
    1.  <span data-ttu-id="72d48-119">SQL Server Management Studio를 사용 하 여 backup mgc 인스턴스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-119">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
    2.  <span data-ttu-id="72d48-120">Mgc 데이터베이스를 마우스 오른쪽 단추로 클릭 하 고 **작업**을 가리킨 다음 **미러**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-120">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
    3.  <span data-ttu-id="72d48-121">**미러링 제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-121">Click **Remove Mirroring**.</span></span>
    
    4.  <span data-ttu-id="72d48-122">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-122">Click **OK**.</span></span>
    
    5.  <span data-ttu-id="72d48-123">Mgccomp 데이터베이스에 대해 동일한 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-123">Perform the same steps with the mgccomp database.</span></span>

3.  <span data-ttu-id="72d48-124">새 기본 데이터베이스로 복원할 수 있도록 mgc 데이터베이스를 백업 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-124">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
    1.  <span data-ttu-id="72d48-125">SQL Server Management Studio를 사용 하 여 backup mgc 인스턴스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-125">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
    2.  <span data-ttu-id="72d48-126">Mgc 데이터베이스를 마우스 오른쪽 단추로 클릭 하 고 **작업**을 가리킨 다음 **백업을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-126">Right-click the mgc database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="72d48-127">**데이터베이스 백업** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-127">The **Back Up Database** dialog box appears.</span></span>
    
    3.  <span data-ttu-id="72d48-128">**백업 유형에**서 Full ( **전체**)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-128">In **Backup type**, select **Full**.</span></span>
    
    4.  <span data-ttu-id="72d48-129">**백업 구성 요소**를 보려면 **데이터베이스**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-129">For **Backup component**, click **Database**.</span></span>
    
    5.  <span data-ttu-id="72d48-130">**이름**에 제시 된 기본 백업 집합 이름을 그대로 사용 하거나 백업 집합에 다른 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-130">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
    6.  <span data-ttu-id="72d48-131">\* \<선택\> 사항\* **설명**에 백업 집합에 대 한 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-131">*\<Optional\>* In **Description**, enter a description of the backup set.</span></span>
    
    7.  <span data-ttu-id="72d48-132">대상 목록에서 기본 백업 위치를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-132">Remove the default backup location from the destination list.</span></span>
    
    8.  <span data-ttu-id="72d48-133">로그 전달을 위해 설정한 공유 위치의 경로를 사용 하 여 목록에 파일을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-133">Add a file to the list by using the path to the share location that you established for log shipping.</span></span> <span data-ttu-id="72d48-134">이 경로는 기본 데이터베이스와 백업 데이터베이스에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-134">This path is available to the primary database and to the backup database.</span></span>
    
    9.  <span data-ttu-id="72d48-135">**확인** 을 클릭 하 여 대화 상자를 닫고 백업 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-135">Click **OK** to close the dialog box and begin the backup process.</span></span>

4.  <span data-ttu-id="72d48-136">이전 단계에서 만든 백업 데이터베이스를 사용 하 여 기본 데이터베이스를 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-136">Restore the primary database by using the backup database created in the previous step.</span></span>
    
    1.  <span data-ttu-id="72d48-137">SQL Server Management Studio를 사용 하 여 기본 mgc 인스턴스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-137">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
    2.  <span data-ttu-id="72d48-138">Mgc 데이터베이스를 마우스 오른쪽 단추로 클릭 하 고 **작업**, **복원을**차례로 가리킨 다음 **데이터베이스**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-138">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**.</span></span> <span data-ttu-id="72d48-139">**데이터베이스 복원** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-139">The **Restore Database** dialog box appears.</span></span>
    
    3.  <span data-ttu-id="72d48-140">**장치에서를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-140">Select **From Device**.</span></span>
    
    4.  <span data-ttu-id="72d48-141">찾아보기 단추를 클릭 하 여 **백업 지정** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-141">Click the browse button, which opens the **Specify Backup** dialog box.</span></span> <span data-ttu-id="72d48-142">**백업 미디어**에서 **파일**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-142">In **Backup media**, select **File**.</span></span> <span data-ttu-id="72d48-143">**추가**를 클릭 하 고 3 단계에서 만든 백업 파일을 선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-143">Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
    5.  <span data-ttu-id="72d48-144">**복원할 백업 세트 선택**에서 백업을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-144">In **Select the backup sets to restore**, select the backup.</span></span>
    
    6.  <span data-ttu-id="72d48-145">**페이지 선택** 창에서 **옵션** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-145">Click **Options** in the **Select a page** pane.</span></span>
    
    7.  <span data-ttu-id="72d48-146">**복원 옵션**에서 **기존 데이터베이스 덮어쓰기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-146">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
    8.  <span data-ttu-id="72d48-147">**복구 상태**에서 **데이터베이스를 사용할 준비가 된 상태로 둡니다**.를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-147">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
    9.  <span data-ttu-id="72d48-148">**확인** 을 클릭 하 여 복원 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-148">Click **OK** to begin the restoration process.</span></span>

5.  <span data-ttu-id="72d48-149">기본 데이터베이스에 대 한 SQL Server 로그 전달을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-149">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="72d48-150">[Lync server 2013의 고가용성 및 재해 복구용으로 영구 채팅 서버 구성](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) 의 절차에 따라 기본 mgc 데이터베이스에 대 한 로그 전달을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-150">Follow the procedures in [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) to establish log shipping for the primary mgc database.</span></span>

6.  <span data-ttu-id="72d48-151">영구 채팅 서버 활성 서버를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-151">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="72d48-152">Lync Server 관리 셸에서 **CsPersistentChatActiveServer** cmdlet을 사용 하 여 활성 서버 목록을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-152">From the Lync Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="72d48-153">모든 활성 서버는 새 기본 데이터베이스와 동일한 데이터 센터 내에 있거나 데이터베이스에 대 한 대기/고속 대역폭 연결이 낮은 데이터 센터에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-153">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span>

    
    </div>

<span data-ttu-id="72d48-154">풀을 정상 상태로 복원 다음 Windows PowerShell 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="72d48-154">The restore the pool to its normal state run the following Windows PowerShell command:</span></span>

    Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal

<span data-ttu-id="72d48-155">자세한 내용은 [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="72d48-155">See the help topic for the [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) cmdlet for more information.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

