---
title: 'Lync Server 2013: Enterprise Edition 백 엔드 서버 복원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring an Enterprise Edition Back End Server
ms:assetid: 1450eb4e-3315-4d02-8f02-6e1791fb1550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202163(v=OCS.15)
ms:contentKeyID: 51541446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e0121ee654846bcb60acc6da6847995b967a880
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984474"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-back-end-server-in-lync-server-2013"></a><span data-ttu-id="57cf1-102">Lync Server 2013에서 Enterprise Edition 백 엔드 서버 복원</span><span class="sxs-lookup"><span data-stu-id="57cf1-102">Restoring an Enterprise Edition Back End Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57cf1-103">_**마지막으로 수정한 주제:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="57cf1-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="57cf1-104">이 항목에 설명 된 절차는 다음 두 가지 경우에 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-104">Use the procedure described in this topic in the following two cases:</span></span>

  - <span data-ttu-id="57cf1-105">미러된 Enterprise Edition 백 엔드 서버의 기본 및 미러 데이터베이스 모두에 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-105">Both the primary and mirror databases of a mirrored Enterprise Edition Back End Server fail.</span></span>

  - <span data-ttu-id="57cf1-106">미러링 되지 않는 Enterprise Edition 백 엔드 서버가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-106">An Enterprise Edition Back End Server that is not mirrored fails.</span></span>

<span data-ttu-id="57cf1-107">미러된 Enterprise Edition 백 엔드를 사용 하 고 있는 경우 미러 또는 기본 데이터베이스에 오류가 발생 하는 경우 [Lync server 2013에서 미러된 Enterprise Edition 백 엔드 서버 복원을](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) 참조 하세요-기본 데이터베이스를 복원 하 고 미러 [Enterprise Edition 백 엔드 서버를 복원 하 여 lync server 2013-](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) 미러를 복원 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-107">If you have a mirrored Enterprise Edition Back End and only the mirror or primary database fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) for restoring the primary database, and [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) for restoring the mirror.</span></span>

<span data-ttu-id="57cf1-108">중앙 관리 저장소에 오류가 발생 하는 경우 [Lync server 2013에서 중앙 관리 저장소를 호스팅하는 서버 복원을](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="57cf1-108">If the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="57cf1-109">백 엔드 서버가 아닌 Enterprise Edition 구성원 서버가 실패 하는 경우 [Lync server 2013에서 Enterprise edition 구성원 서버 복원을](lync-server-2013-restoring-an-enterprise-edition-member-server.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="57cf1-109">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="57cf1-110">복원을 시작 하기 전에 시스템의 이미지 복사본을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-110">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="57cf1-111">복원 중에 문제가 발생 하는 경우이 이미지를 롤백 시점으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-111">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="57cf1-112">운영 체제 및 SQL Server를 설치 하 고 인증서를 복원 하거나 reenroll 이미지 복사본을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-112">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server"></a><span data-ttu-id="57cf1-113">Enterprise Edition 백 엔드 서버를 복원 하려면</span><span class="sxs-lookup"><span data-stu-id="57cf1-113">To restore an Enterprise Edition Back End Server</span></span>

1.  <span data-ttu-id="57cf1-114">실패 한 컴퓨터와 FQDN (정규화 된 도메인 이름)이 동일한 깨끗 한 새 서버를 사용 하 여 시작 하 고, 운영 체제를 설치한 다음, 인증서를 복원 하거나 reenroll.</span><span class="sxs-lookup"><span data-stu-id="57cf1-114">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="57cf1-115">조직의 서버 배포 절차에 따라이 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-115">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="57cf1-116">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정에서 복원 하려는 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-116">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="57cf1-117">SQL Server 2012 또는 SQL Server 2008 R2를 설치 하 고 인스턴스 이름을 오류 전과 동일 하 게 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-117">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="57cf1-118">배포에 따라 백 엔드 서버에 여러 collocated 또는 별도의 데이터베이스가 포함 될 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-118">Depending on your deployment, the Back End Server might include multiple collocated or separate databases.</span></span> <span data-ttu-id="57cf1-119">SQL Server 사용 권한 및 로그인을 포함 하 여 처음에 서버를 배포 하는 데 사용한 SQL Server를 설치 하려면 같은 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-119">Follow the same procedure to install SQL Server that you used originally to deploy the server, including SQL Server permissions and logins.</span></span>

    
    </div>

4.  <span data-ttu-id="57cf1-120">SQL Server를 설치한 후 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-120">After you install SQL Server, perform the following:</span></span>
    
    1.  <span data-ttu-id="57cf1-121">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-121">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="57cf1-122">**기존 배포에서 토폴로지 다운로드**를 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-122">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="57cf1-123">토폴로지를 선택한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-123">Select the topology, and then click **Save**.</span></span> <span data-ttu-id="57cf1-124">**예** 를 클릭 하 여 선택 내용을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-124">Click **Yes** to confirm your selection.</span></span>
    
    4.  <span data-ttu-id="57cf1-125">**Lync Server 2013** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **토폴로지 게시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-125">Right-click the **Lync Server 2013** node, and then click **Publish Topology**.</span></span>
    
    5.  <span data-ttu-id="57cf1-126">**토폴로지 게시** 마법사를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-126">Follow the **Publish the Topology** wizard.</span></span> <span data-ttu-id="57cf1-127">**데이터베이스 만들기** 페이지에서 다시 생성 하려는 데이터베이스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-127">On the **Create databases** page, select the databases that you want to re-create.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="57cf1-128"><STRONG>데이터베이스 만들기</STRONG> 페이지에는 독립 실행형 데이터베이스만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-128">Only stand-alone databases are displayed on the <STRONG>Create databases</STRONG> page.</span></span>

        
        </div>
    
    6.  <span data-ttu-id="57cf1-129">미러링된 백 엔드를 복원 하는 경우에는 **미러 데이터베이스 만들기** 메시지가 나타날 때까지 마법사의 나머지 단계를 계속 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-129">If you are restoring a Back End that was mirrored, continue to follow the rest of the wizard until the prompt **Create Mirror Database** appears.</span></span> <span data-ttu-id="57cf1-130">설치 하려는 데이터베이스를 선택 하 고 프로세스를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-130">Select the database that you want to install, and complete the process.</span></span>
    
    7.  <span data-ttu-id="57cf1-131">마법사의 나머지 단계를 따르고 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-131">Follow the rest of the wizard, and then click **Finish**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="57cf1-132">토폴로지 작성기를 실행 하는 대신, <STRONG>설치-CsDatabase</STRONG> cmdlet을 사용 하 여 각 데이터베이스를 만들고 <STRONG>CsMirrorDatabase</STRONG> cmdlet을 사용해 미러링을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-132">Instead of running Topology Builder, you can use the <STRONG>Install-CsDatabase</STRONG> cmdlet to create each database, and the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="57cf1-133">자세한 내용은 Lync Server 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="57cf1-133">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

5.  <span data-ttu-id="57cf1-134">다음을 수행 하 여 사용자 데이터를 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-134">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="57cf1-135">$Backup\\ 에서 로컬 디렉터리로 ExportedUserData을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-135">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="57cf1-136">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    3.  <span data-ttu-id="57cf1-137">사용자 데이터를 복원 하기 전에 Lync 서비스를 중지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-137">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="57cf1-138">이렇게 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-138">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    4.  <span data-ttu-id="57cf1-139">사용자 데이터를 복원 하려면 명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-139">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="57cf1-140">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-140">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  <span data-ttu-id="57cf1-141">다음과 같이 입력 하 여 Lync 서비스를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-141">Restart Lync Services by typing:</span></span>
        
            Start-CsWindowsService

6.  <span data-ttu-id="57cf1-142">이 풀에 응답 그룹을 배포한 경우 응답 그룹 구성 데이터를 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-142">If you deployed Response Group on this pool, restore the Response Group configuration data.</span></span> <span data-ttu-id="57cf1-143">자세한 내용은 [Lync Server 2013에서 응답 그룹 설정 복원을](lync-server-2013-restoring-response-group-settings.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="57cf1-143">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

7.  <span data-ttu-id="57cf1-144">보관 또는 모니터링 데이터베이스가 포함 된 백 엔드 서버를 복원 하는 경우 sql Server Management Studio와 같은 SQL Server 도구를 사용 하 여 보관 또는 모니터링 데이터를 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="57cf1-144">If you are restoring a Back End Server that included Archiving or Monitoring databases, restore the Archiving or Monitoring data by using a SQL Server tool, such as SQL Server Management Studio.</span></span> <span data-ttu-id="57cf1-145">자세한 내용은 [Lync Server 2013에서 모니터링 또는 데이터 보관 복구](lync-server-2013-restoring-monitoring-or-archiving-data.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="57cf1-145">For details, see [Restoring monitoring or archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

