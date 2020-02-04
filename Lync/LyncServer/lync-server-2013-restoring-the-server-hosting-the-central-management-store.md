---
title: 'Lync Server 2013: 중앙 관리 저장소를 호스팅하는 서버 복원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring the server hosting the Central Management store
ms:assetid: 3bd6c82c-07fb-4798-b8f9-e7c78a5a83d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202172(v=OCS.15)
ms:contentKeyID: 51541464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 976f486d096f7be59e2eef74eab7b03d6cc4bab0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733048"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-the-server-hosting-the-central-management-store-in-lync-server-2013"></a><span data-ttu-id="15598-102">Lync Server 2013에서 중앙 관리 저장소를 호스팅하는 서버 복원</span><span class="sxs-lookup"><span data-stu-id="15598-102">Restoring the server hosting the Central Management store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15598-103">_**마지막으로 수정한 주제:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="15598-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="15598-104">Lync Server 배포에는 단일 중앙 관리 저장소가 있으며,이 복사본은 Lync Server 서버 역할을 실행 하는 각 서버에 복제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15598-104">A Lync Server deployment has a single Central Management store, a copy of which is replicated to each server running a Lync Server server role.</span></span> <span data-ttu-id="15598-105">이 항목에서는 중앙 관리 저장소를 호스트 하는 백 엔드 서버 또는 Standard Edition 서버를 복원 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-105">This topic describes how to restore a Back End Server or Standard Edition server that hosts the Central Management store.</span></span>

<span data-ttu-id="15598-106">중앙 관리 서버가 있는 풀을 찾으려면 토폴로지 작성기를 열고 **Lync Server**를 클릭 하 고 **중앙 관리 서버**아래의 오른쪽 창에서 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-106">To find the pool where the Central Management Server is located, open Topology Builder, click **Lync Server**, and look in the right pane under **Central Management Server**.</span></span>

<span data-ttu-id="15598-107">중앙 관리 저장소를 호스트 하는 백 엔드 서버가 미러링된 설정에 있고 미러 데이터베이스가 제대로 작동 하는 경우에는이 계속 작동 하는 미러의 백업을 만든 다음 기본 데이터베이스와 두 파일 모두에서 전체 복원을 수행 하는 것이 좋습니다. 다음 복원 절차에 따라이 백업을 사용 하 여 데이터베이스를 미러링합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-107">If the Back End Server that hosts the Central Management store is in a mirrored setup and the mirror database is still functional, we recommend that you make a backup of this still-functioning mirror, and then perform a full restore on both the primary database and the mirror database, using this backup, by following the restoration procedure below.</span></span> <span data-ttu-id="15598-108">백 엔드 복원에는 토폴로지를 수정 하 고 게시 해야 하기 때문에이 작업이 필요 하며, CMS를 호스트 하는 기본 데이터베이스가 작동 하는 경우에만 이렇게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15598-108">This is necessary because Back End restore requires modifying and publishing the topology, and this can be done only if the primary database hosting CMS is operational.</span></span> <span data-ttu-id="15598-109">또한 토폴로지가 게시 될 수 없는 경우 기본 및 미러 데이터베이스 역할은 서로를 사용할 수 없다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="15598-109">Also note that the primary and mirror database roles cannot be interchanged if the topology cannot be published.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="15598-110">중앙 관리 저장소를 호스팅하지 않는 백 엔드 서버 또는 Standard Edition 서버에 오류가 발생 하는 경우 lync <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">server 2013에서 Enterprise Edition 백 엔드 서버 복원</A> 또는 <A href="lync-server-2013-restoring-a-standard-edition-server.md">lync Server 2013에서 Standard edition 서버 복원</A>을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="15598-110">If a Back End Server or Standard Edition server that does not host the Central Management store failed, see <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition Back End Server in Lync Server 2013</A> or <A href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a Standard Edition server in Lync Server 2013</A>.</span></span> <span data-ttu-id="15598-111">중앙 관리 저장소를 호스트 하는 백 엔드 서버가 미러링된 구성에 있고 미러만 실패 한 경우에는 <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Lync server 2013-미러에서 미러된 Enterprise Edition 백 엔드 서버 복원을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="15598-111">If a Back End Server that hosts the Central Management store is in a mirrored configuration and only the mirror failed, see <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</A>.</span></span> <span data-ttu-id="15598-112">다른 서버에 오류가 발생 한 경우 <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">에는 Lync server 2013에서 Enterprise Edition 구성원 서버 복원을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="15598-112">If any other server failed, see <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="15598-113">복원을 시작 하기 전에 시스템의 이미지 복사본을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="15598-113">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="15598-114">복원 중에 문제가 발생 하는 경우이 이미지를 롤백 시점으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15598-114">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="15598-115">운영 체제 및 SQL Server를 설치 하 고 인증서를 복원 하거나 reenroll 이미지 복사본을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15598-115">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-the-central-management-store"></a><span data-ttu-id="15598-116">중앙 관리 저장소를 복원 하려면</span><span class="sxs-lookup"><span data-stu-id="15598-116">To restore the Central Management store</span></span>

1.  <span data-ttu-id="15598-117">실패 한 컴퓨터와 FQDN (정규화 된 도메인 이름)이 동일한 깨끗 한 새 서버를 사용 하 여 시작 하 고, 운영 체제를 설치한 다음, 인증서를 복원 하거나 reenroll.</span><span class="sxs-lookup"><span data-stu-id="15598-117">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="15598-118">조직의 서버 배포 절차에 따라이 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-118">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="15598-119">RTCUniversalServerAdmins 그룹 및 로컬 관리자 그룹의 구성원 인 사용자 계정에서 복원 하려는 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-119">From a user account that is a member of the RTCUniversalServerAdmins group and the Local Administrators group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="15598-120">스탠더드 버전 서버를 복원 하는 경우 $Backup의 적절 한 파일 저장소를 서버의 파일 저장소 위치에 복사 하 여 파일 저장소를 복원 하 고 폴더를 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-120">If you are restoring a Standard Edition server, restore the File Store by copying the appropriate File Store from $Backup to the File Store location on the server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="15598-121">파일을 사용 하는 구성 요소에서 액세스할 수 있도록 복원 된 파일 저장소의 경로와 파일 이름이 백업 된 파일 저장소와 정확히 동일 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-121">The path and file name for the restored File Store should be exactly the same as the backed up File Store so that components that use the files can access them.</span></span>

    
    </div>

4.  <span data-ttu-id="15598-122">다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-122">Do one of the following:</span></span>
    
      - <span data-ttu-id="15598-123">스탠더드 버전 서버를 설치 하는 경우 Lync Server 설치 폴더 또는 미디어로 이동한 다음, 설치 \\\\Amd64\\Setup.exe에 있는 lync server 배포 마법사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-123">If you are installing a Standard Edition server, browse to the Lync Server installation folder or media, and then start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="15598-124">배포 마법사에서 **첫 번째 Standard Edition Server 준비** 를 클릭 하 고 마법사의 지시에 따라 중앙 관리 저장소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-124">In the Deployment Wizard, click **Prepare first Standard Edition server** and follow the wizard to install the Central Management store.</span></span>
    
      - <span data-ttu-id="15598-125">엔터프라이즈 백 엔드 서버를 설치 하는 경우 SQL Server 2012 또는 SQL Server 2008 R2를 설치 하 고 인스턴스 이름을 오류 전과 동일 하 게 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-125">If you are installing an Enterprise Back End Server, install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="15598-126">복원 하는 서버와 배포에 따라 서버에 여러 collocated 또는 별도의 데이터베이스가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15598-126">Depending on the server that you are restoring and on your deployment, the server might include multiple collocated or separate databases.</span></span> <span data-ttu-id="15598-127">SQL Server 사용 권한 및 로그인을 포함 하 여 처음에 서버를 배포 하는 데 사용한 SQL Server를 설치 하려면 같은 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="15598-127">Follow the same procedure to install SQL Server that you used originally to deploy the server, including SQL Server permissions and logins.</span></span>

        
        </div>

5.  <span data-ttu-id="15598-128">프런트 엔드 서버에서 Lync Server Management Shell을 시작 합니다. **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-128">From a Front End Server, Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

6.  <span data-ttu-id="15598-129">중앙 관리 저장소를 다시 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="15598-129">Re-create the Central Management store.</span></span> <span data-ttu-id="15598-130">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-130">At the command line, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    <span data-ttu-id="15598-131">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="15598-131">For example:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  <span data-ttu-id="15598-132">중앙 관리 저장소에 대 한 Active Directory 도메인 서비스 제어 지점을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-132">Set the Active Directory Domain Services control point for the Central Management store.</span></span> <span data-ttu-id="15598-133">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-133">At the command line, type:</span></span>
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    <span data-ttu-id="15598-134">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="15598-134">For example:</span></span>
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="15598-135">연결 지점이 손실 된 경우이 cmdlet을 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15598-135">If you lose the connection point, you can rerun this cmdlet.</span></span>

    
    </div>

8.  <span data-ttu-id="15598-136">$Backup에서 중앙 관리 저장소 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="15598-136">Import the Central Management store data from $Backup.</span></span> <span data-ttu-id="15598-137">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-137">At the command line, type:</span></span>
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    <span data-ttu-id="15598-138">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="15598-138">For example:</span></span>
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  <span data-ttu-id="15598-139">방금 변경한 내용을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-139">Enable the changes you have just made.</span></span> <span data-ttu-id="15598-140">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-140">At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="15598-141">토폴로지를 사용 하도록 설정한 후에는 데이터베이스에서 토폴로지 문서를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15598-141">After you enable the topology, you can find the topology document in the database.</span></span>

    
    </div>

10. <span data-ttu-id="15598-142">CMS를 호스트 하는 Enterprise Edition 백 엔드 서버를 복원 하거나 CMS의 미러를 다시 만들어야 하는 경우이 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-142">If you are restoring an Enterprise Edition Back End Server that also hosted the CMS, or if you need to re-create a mirror of the CMS, then follow this step.</span></span> <span data-ttu-id="15598-143">그렇지 않으면 11 단계로 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="15598-143">Otherwise, skip to step 11.</span></span>
    
    <span data-ttu-id="15598-144">다음을 수행 하 여 독립 실행형 데이터베이스를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-144">Install the stand-alone databases by doing the following:</span></span>
    
    1.  <span data-ttu-id="15598-145">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-145">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="15598-146">**기존 배포에서 토폴로지 다운로드**를 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-146">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="15598-147">토폴로지를 선택한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-147">Select the topology, and then click **Save**.</span></span> <span data-ttu-id="15598-148">**예** 를 클릭 하 여 선택 내용을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-148">Click **Yes** to confirm your selection.</span></span>
    
    4.  <span data-ttu-id="15598-149">**Lync Server 2013** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **데이터베이스 설치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-149">Right-click the **Lync Server 2013** node, and then click **Install Database**.</span></span>
    
    5.  <span data-ttu-id="15598-150">**데이터베이스 설치** 마법사를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="15598-150">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="15598-151">이 서버의 중앙 관리 저장소 이외의 데이터베이스를 복원 하는 경우 **데이터베이스 만들기** 페이지에서 다시 만들려는 데이터베이스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-151">If you are restoring a database other than the Central Management store on this server, on the **Create databases** page, select the databases you want to recreate.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="15598-152"><STRONG>데이터베이스 만들기</STRONG> 페이지에는 독립 실행형 데이터베이스만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15598-152">Only stand-alone databases are displayed on the <STRONG>Create databases</STRONG> page.</span></span> <span data-ttu-id="15598-153">Collocated 데이터베이스는 Lync Server 배포 마법사를 실행할 때 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="15598-153">Collocated databases are created when you run the Lync Server Deployment Wizard.</span></span>

        
        </div>
    
    6.  <span data-ttu-id="15598-154">미러 백 엔드 서버를 복원 하는 경우 미러 데이터베이스 만들기 메시지가 나타날 때까지 마법사의 나머지 단계를 계속 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-154">If you are restoring a mirrored Back End Server, continue to follow the rest of the wizard until you come to a prompt of Create Mirror Database.</span></span> <span data-ttu-id="15598-155">설치 하고자 하는 데이터베이스를 선택 하 고 프로세스를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-155">Select the database you want to install, and complete the process.</span></span>
    
    7.  <span data-ttu-id="15598-156">마법사의 나머지 단계를 따르고 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-156">Follow the rest of the wizard, and then click **Finish**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="15598-157">토폴로지 작성기를 실행 하는 대신, <STRONG>설치-CsDatabase</STRONG> cmdlet을 사용 하 여 각 데이터베이스를 만들고 <STRONG>CsMirrorDatabase</STRONG> cmdlet을 사용해 미러링을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15598-157">Instead of running Topology Builder, you can use the <STRONG>Install-CsDatabase</STRONG> cmdlet to create each database, and the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="15598-158">자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">설치-CsDatabase</A> 및 <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">install-CsMirrorDatabase</A>을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="15598-158">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">Install-CsDatabase</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">Install-CsMirrorDatabase</A>.</span></span>

    
    </div>

11. <span data-ttu-id="15598-159">Standard Edition server를 복원 하는 경우 Lync Server 설치 폴더 또는 미디어를 찾아 설치 \\\\Amd64\\Setup.exe에 있는 lync server 배포 마법사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-159">If you are restoring a Standard Edition server, browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="15598-160">Lync Server 배포 마법사를 사용 하 여 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-160">Use the Lync Server Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="15598-161">**1 단계: 로컬 구성 저장소 설치** 를 실행 하 여 로컬 구성 파일을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-161">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="15598-162">**2 단계: lync Server 구성 요소 설치 또는 제거** 를 실행 하 여 lync server 서버 역할을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-162">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server roles.</span></span>
    
    3.  <span data-ttu-id="15598-163">**3 단계: 인증서 요청, 설치 또는 할당** 을 실행 하 여 인증서를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-163">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="15598-164">서버에서 서비스를 시작 하려면 **4 단계: 서비스 시작** 을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-164">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="15598-165">배포 마법사를 실행 하는 방법에 대 한 자세한 내용은 복원할 서버 역할에 대 한 배포 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="15598-165">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

12. <span data-ttu-id="15598-166">다음을 수행 하 여 사용자 데이터를 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-166">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="15598-167">$Backup\\ 에서 로컬 디렉터리로 ExportedUserData을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-167">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="15598-168">사용자 데이터를 복원 하기 전에 Lync 서비스를 중지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-168">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="15598-169">이렇게 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-169">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    3.  <span data-ttu-id="15598-170">사용자 데이터를 복원 하려면 명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-170">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="15598-171">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="15598-171">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  <span data-ttu-id="15598-172">다음과 같이 입력 하 여 Lync 서비스를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-172">Restart Lync services by typing:</span></span>
        
            Start-CsWindowsService

13. <span data-ttu-id="15598-173">위치 정보 데이터를 중앙 관리 저장소에 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-173">Restore Location Information data to the Central Management store.</span></span> <span data-ttu-id="15598-174">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-174">At the command line, type:</span></span>
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    <span data-ttu-id="15598-175">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="15598-175">For example:</span></span>
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. <span data-ttu-id="15598-176">이 풀 또는 Standard Edition 서버에서 응답 그룹을 배포한 경우 응답 그룹 구성 데이터를 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-176">If you deployed Response Group on this pool or Standard Edition server, restore the Response Group configuration data.</span></span> <span data-ttu-id="15598-177">자세한 내용은 [Lync Server 2013에서 응답 그룹 설정 복원을](lync-server-2013-restoring-response-group-settings.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="15598-177">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

15. <span data-ttu-id="15598-178">보관 또는 모니터링 데이터베이스가 포함 된 백 엔드 서버를 복원 하는 경우 sql Server Management Studio와 같은 SQL Server 관리 도구를 사용 하 여 보관 또는 모니터링 데이터를 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="15598-178">If you are restoring a Back End Server that includes Archiving or Monitoring databases, restore the Archiving or Monitoring data by using a SQL Server management tool, such as SQL Server Management Studio.</span></span> <span data-ttu-id="15598-179">자세한 내용은 [Lync Server 2013에서 모니터링 또는 데이터 보관 복구](lync-server-2013-restoring-monitoring-or-archiving-data.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="15598-179">For details, see [Restoring monitoring or archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

