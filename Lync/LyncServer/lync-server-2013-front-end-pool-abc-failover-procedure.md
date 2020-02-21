---
title: 'Lync Server 2013: 프런트 엔드 풀 ABC 장애 조치 (failover) 절차'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool ABC failover procedure
ms:assetid: 67763ad3-6796-45eb-a486-901f21ac1a95
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945635(v=OCS.15)
ms:contentKeyID: 51541486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f60ded6539f6d984662449562d0f978e98dc3078
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="front-end-pool-abc-failover-procedure-in-lync-server-2013"></a><span data-ttu-id="f2671-102">Lync Server 2013의 프런트 엔드 풀 ABC 장애 조치 (failover) 절차</span><span class="sxs-lookup"><span data-stu-id="f2671-102">Front End pool ABC failover procedure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2671-103">_**마지막으로 수정 된 항목:** 2014-05-22_</span><span class="sxs-lookup"><span data-stu-id="f2671-103">_**Topic Last Modified:** 2014-05-22_</span></span>

<span data-ttu-id="f2671-104">ABC 장애 조치 (failover) 절차를 수행 하려면 다음 단계를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-104">Use the following steps to perform the ABC failover procedure.</span></span> <span data-ttu-id="f2671-105">이 절차에는 각 단계에 대 한 간략 한 설명과 각 단계에 대해 실행할 명령 및 cmdlet이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-105">This procedure contains a high-level description of each step, followed by commands and cmdlets to be run for each step.</span></span>

<span data-ttu-id="f2671-106">Cmdlet을 실행 하려면 관리자 권한으로 실행을 사용 하 여 Lync Server 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-106">To run the cmdlets, open a Lync Server Management Shell using Run as Administrator.</span></span>

<div>

## <a name="to-perform-an-abc-failover"></a><span data-ttu-id="f2671-107">ABC 장애 조치 (Failover)를 수행 하려면</span><span class="sxs-lookup"><span data-stu-id="f2671-107">To Perform an ABC Failover</span></span>

1.  <span data-ttu-id="f2671-108">풀 A가 중앙 관리 서버 (CMS)에 대 한 호스트 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-108">Check whether the pool A is the host for the Central Management Server (CMS).</span></span>
    
      - <span data-ttu-id="f2671-109">다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-109">Run the following cmdlet:</span></span>
        
            Get-CsService -CentralManagement
        
        <span data-ttu-id="f2671-110">활성 CMS의 Identity 필드가 풀 A의 FQDN (정규화 된 도메인 이름)을 가리키면이 절차의 2 단계와 3 단계로 중앙 관리 서버를 먼저 장애 조치 (failover) 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-110">If the Identity field of the active CMS points to the fully qualified domain name (FQDN) of Pool A, then you use steps 2 and 3 of this procedure to fail over the Central Management Server first.</span></span> <span data-ttu-id="f2671-111">그렇지 않은 경우에는 4 단계로 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-111">Otherwise, skip to step 4.</span></span>

2.  <span data-ttu-id="f2671-112">다음 cmdlet을 실행 하 여 재해 복구 모드에서 CMS를 풀 B로 장애 조치 (failover) 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-112">Fail over the CMS to Pool B in disaster recovery mode by running the following cmdlet:</span></span>
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    <span data-ttu-id="f2671-113">이 작업을 수행한 후 추가 복구를 위해 CMS를 풀 B에서 기존의 다른 연결 된 풀로 이동 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-113">After you do this, we recommend that you move the CMS from pool B to another existing paired pool for extra resiliency.</span></span> <span data-ttu-id="f2671-114">자세한 내용은 [Move-move-csmanagementserver](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f2671-114">For details, see [Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)..</span></span>

3.  <span data-ttu-id="f2671-115">풀 A에 CMS가 포함 되어 있는 경우 풀 A에서 풀 B의 LIS 데이터베이스 (Lis)로 LIS 구성을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-115">If Pool A contains CMS, import the LIS configuration from pool A into pool B’s LIS database (Lis.mdf).</span></span> <span data-ttu-id="f2671-116">이 작업은 LIS 데이터를 정기적으로 백업 하는 경우에만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-116">This will work only if you have been backing up LIS data on a regular basis.</span></span> <span data-ttu-id="f2671-117">LIS 구성을 가져오려면 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-117">To import the LIS configuration, run the following cmdlets:</span></span>
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  <span data-ttu-id="f2671-118">풀 A에서 풀 B로 백업한 Lync Server 응답 그룹 서비스 워크플로를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-118">Import backed-up Lync Server Response Group service workflows from pool A into pool B.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f2671-119">현재 <STRONG>export-csrgsconfiguration</STRONG> cmdlet을 사용 하려면 풀 A의 큐와 워크플로 이름이 풀 B의 큐와 워크플로 이름과 달라 지는 것이 좋습니다. 이름이 고유 하지 않으면 <STRONG>export-csrgsconfiguration</STRONG> cmdlet을 실행할 때 오류가 발생 하 고 <STRONG>export-csrgsconfiguration</STRONG> cmdlet을 계속 하기 전에 풀 B에서 큐 및 워크플로의 이름을 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-119">Currently, the <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet requires that the queue and workflow names on pool A are distinct from the queue and workflow names on pool B. If the names are not distinct, you will get an error when running the <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet, and the queues and workflows will need to be renamed in pool B before proceeding with <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet.</span></span>

    
    </div>
    
    <span data-ttu-id="f2671-120">응답 그룹 구성을 풀 A에서 풀 B로 가져오는 두 가지 옵션을 사용할 수 있습니다. 사용 하는 옵션은 풀 B의 응용 프로그램 수준 설정을 해당 풀 A의 응용 프로그램 수준 설정과 덮어쓸지 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-120">You have two options for importing the Response Group configuration from pool A to pool B. Which option you use depends on whether you want to overwrite the application-level settings of pool B with the application-level settings in pool A.</span></span>
    
      - <span data-ttu-id="f2671-121">풀 B 설정을 덮어쓰려면 **ReplaceExistingSettings** 옵션을 사용 하 여 **export-csrgsconfiguration** cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-121">If you want to overwrite the Pool B settings, run the **Import-CsRgsConfiguration** cmdlet with the **ReplaceExistingSettings** option:</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - <span data-ttu-id="f2671-122">풀 B 설정을 덮어쓰지 않으려면 **ReplaceExistingSettings** 옵션 없이 **export-csrgsconfiguration** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-122">If you do not want to overwrite the Pool B settings, use the **Import-CsRgsConfiguration** cmdlet without the **ReplaceExistingSettings** option.</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="f2671-123">백업 풀의 응용 프로그램 수준 설정 (풀 A)을 기본 풀의 설정으로 덮어쓰지 않으려면 응답 그룹 응용 프로그램은 풀 a의 응용 프로그램 수준 설정이 손실 될 수 있으므로 해당 설정에 대 한 손실을 방지 하는 것이 좋습니다. 풀 당 하나의 응용 프로그램 수준 설정 집합만 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-123">Keep in mind that if you do not want to overwrite the application-level settings of the backup pool (pool B) with the settings of the primary pool (pool A), pool A’s application-level settings will be lost if pool A is lost, because the Response Group application can store only one set of application-level settings per pool.</span></span> <span data-ttu-id="f2671-124">풀 C를 배포 하 여 풀 A를 대체 하는 경우 기본 음악 대기 오디오 파일을 포함 하 여 응용 프로그램 수준 설정을 다시 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-124">When pool C is deployed to replace pool A, the application-level settings must be reconfigured, including the default music-on-hold audio file.</span></span>

    
    </div>

5.  <span data-ttu-id="f2671-125">다음 cmdlet을 실행 하 여 가져온 응답 그룹을 표시 하 여 응답 그룹 구성 가져오기가 성공적으로 수행 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-125">Verify that the Response Group configuration import was successful by running the following cmdlets to display the imported response groups.</span></span> <span data-ttu-id="f2671-126">가져온 응답 그룹은 여전히 풀 A에서 소유 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-126">Note that the imported response groups are still owned by pool A.</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  <span data-ttu-id="f2671-127">할당 되지 않은 번호의 경우 "공지 사항"을 사용 하는 지정 되지 않은 번호 범위를 선택한 알림 서비스로 그룹 A에서 풀 B로 이동 합니다. 이렇게 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-127">For Unassigned Numbers, move the Unassigned Number ranges that are using "Announcement" as the selected announcement service from pool A to pool B. To do so:</span></span>
    
      - <span data-ttu-id="f2671-128">풀 A에 배포 된 모든 알림을 그룹 B에 다시 만듭니다. 풀 A에 알림을 배포할 때 오디오 파일을 사용 하는 경우에는이 파일이 풀 B에 알림을 다시 만들어야 합니다. 풀 B에서 알림을 다시 만들려면 상위 서비스로 B 풀을 사용 하 여 **새 CsAnnouncement** cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-128">Re-create all announcements that were deployed in pool A on pool B. If any audio files were used when deploying the announcements in pool A, these files will be needed to re-create the announcements in pool B. To re-create the announcements in pool B, use the **New-CsAnnouncement** cmdlets, with pool B as the Parent service.</span></span>
    
      - <span data-ttu-id="f2671-129">풀 A에서 공지를 대상으로 하는 모든 지정 되지 않은 번호 범위를 pool A에 있는 새로 배포 된 공지로, 그룹 A의 알림을 대상으로 하는 지정 되지 않은 모든 번호 범위에 대해 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-129">Retarget all the Unassigned Number ranges that are targeting an announcement in pool A to the newly deployed announcements in pool B. Run the following cmdlet for every Unassigned Number range targeting an announcement of pool A:</span></span>
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f2671-130">"Exchange UM"을 선택한 알림 서비스로 사용 하는 할당 되지 않은 번호 범위에는이 단계가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-130">This step is not required for unassigned number ranges that use "Exchange UM" as the selected announcement service.</span></span>

    
    </div>

7.  <span data-ttu-id="f2671-131">다음 cmdlet을 실행 하 여 재해 복구 (DR) 모드의 풀 A를 풀 A로 장애 조치 (failover) 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-131">Fail over Pool A to Pool B in Disaster Recovery (DR) mode, by running the following cmdlet:</span></span>
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  <span data-ttu-id="f2671-132">풀 C를 구축 하 되, 풀 C에서는 서비스를 시작 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-132">Build pool C, but do not start any services on pool C.</span></span>
    
    <span data-ttu-id="f2671-133">이 단계는 5 및 6 단계와 동시에 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-133">Note that this step can be carried out concurrently with steps 5 and 6.</span></span>

9.  <span data-ttu-id="f2671-134">다음 cmdlet을 실행 하 여 풀 A에 있는 사용자를 그룹 C로 이동 하도록 강제 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-134">Force users homed on pool A to move to pool C by running the following cmdlet:</span></span>
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    <span data-ttu-id="f2671-135">이때 풀 A에 있는 사용자가 서비스 중단을 경험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-135">At this point, users homed on pool A will begin to experience a service outage.</span></span> <span data-ttu-id="f2671-136">이 중단은 16 단계까지 계속 되며, 서비스가 풀 C에서 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-136">This outage will continue until step 16, at which point services are started on pool C.</span></span>

10. <span data-ttu-id="f2671-137">다음 cmdlet을 실행 하 여 풀 A의 전화 회의 디렉터리를 풀 C로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-137">Force the conference directory of pool A to move to pool C by running the following cmdlet:</span></span>
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. <span data-ttu-id="f2671-138">다음 cmdlet을 실행 하 여 전화 회의 자동 전화 교환 (CAA) 연락처 개체를 강제 풀 A에서 풀 C로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-138">Force the Conference Auto Attendant (CAA) Contact Object to move from pool A to pool C by running the following cmdlet:</span></span>
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. <span data-ttu-id="f2671-139">풀 B에서 풀 C로 회의 콘텐츠를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-139">Copy conference content from pool B to pool C.</span></span>

13. <span data-ttu-id="f2671-140">풀 B에서 사용자 데이터를 내보내고 다음 cmdlet을 실행 하 여 사용자 데이터를 풀 C로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-140">Export user data from pool B and import the user data into pool C by running the following cmdlets:</span></span>
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. <span data-ttu-id="f2671-141">풀 A에서 풀 a로 백업한 통화 대기 응용 프로그램 데이터를 복원 하 고 풀 A의 통화 대기 번호 범위를 pool C에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-141">Restore backed-up Call Park application data from pool A into pool C and assign the Call Park orbit ranges of pool A to pool C.</span></span>
    
      - <span data-ttu-id="f2671-142">Lync Server 제어판 또는 Lync Server 관리 셸을 통해 풀 A의 통화 대기 궤도 범위를 풀 C에 다시 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-142">You can reassign a Call Park orbit range of pool A to pool C either through the Lync Server Control Panel or the Lync Server Management Shell.</span></span> <span data-ttu-id="f2671-143">Lync Server 관리 셸에서 풀 A에 할당 된 모든 통화 대기 번호 범위에 대해 다음 cmdlet을 실행 합니다 (Identity 매개 변수는 풀 A에 속하는 통화 대기 번호 범위를 참조 한다는 점에 유의).</span><span class="sxs-lookup"><span data-stu-id="f2671-143">For the Lync Server Management Shell, run the following cmdlet for every Call Park orbit range assigned to pool A (note that the Identity parameter refers to the Call Park Orbit Ranges that belong to pool A):</span></span>
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - <span data-ttu-id="f2671-144">풀 A의 통화 대기에 대해 사용자 지정 된 음악 연결을 구성한 경우에는 풀 C에서 통화 대기 사용자 지정 된 보류 중인 파일을 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-144">If a customized music-on-hold has been configured for Call Park in pool A, restore the Call Park customized music-on-hold file in pool C.</span></span>
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        <span data-ttu-id="f2671-145">예:</span><span class="sxs-lookup"><span data-stu-id="f2671-145">For example:</span></span>
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - <span data-ttu-id="f2671-146">마지막으로 **new-cscpsconfiguration** cmdlet을 사용 하 여 풀 C의 통화 대기 설정을 다시 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-146">Finally, reconfigure the Call Park settings on pool C by using the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="f2671-147">통화 대기 응용 프로그램은 하나의 설정 집합 및 사용자 지정 된 음악 대기 오디오 파일을 풀 당 하나만 저장할 수 있으며 재해 발생 시 이러한 설정이 백업 되거나 보존 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-147">The Call Park application can store only one set of settings and one customized music-on-hold audio file per pool, and these settings are not backed up or preserved in the event of a disaster.</span></span>

15. <span data-ttu-id="f2671-148">영구 채팅에 대 한 다음 홉 풀이 풀 A를 가리키고 토폴로지 변경 내용을 만들고 게시 하 여 다음 홉 서버가 풀 C를 가리키도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-148">If the next hop pool for Persistent Chat is pointing to pool A, make and publish topology changes so that the next hop server points to pool C.</span></span>
    
      - <span data-ttu-id="f2671-149">토폴로지 작성기에서 영구 채팅 풀이 다음 홉으로 Pool C를 가리키도록 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-149">In Topology Builder, change the Persistent Chat pool to point to Pool C as its next hop.</span></span> <span data-ttu-id="f2671-150">이렇게 하려면 영구 채팅 풀을 마우스 오른쪽 단추로 클릭 하 고 **일반** 탭을 클릭 한 다음 **다음 홉 풀**에 풀 C의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-150">To do so, right-click on the Persistent Chat pool, then click the **General** tab, and then type the name of Pool C in **Next Hop Pool**.</span></span>
    
      - <span data-ttu-id="f2671-151">다음 cmdlet을 실행 하 여 풀 C에서 서비스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-151">Start services on pool C by running the following cmdlet:</span></span>
        
            Start-csWindowsService
    
    <span data-ttu-id="f2671-152">이 시점에서 서비스 중단은 원래 풀 A에 있는 사용자에 대해 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-152">At this point, the service outage ends for users originally homed on pool A.</span></span>

16. <span data-ttu-id="f2671-153">다음 cmdlet을 실행 하 여 가져오기 위해 풀 A가 소유 하는 풀 B에서 Lync Server Response Group 서비스 워크플로를 풀 C로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-153">Export Lync Server Response Group service workflows from pool B owned by pool A for import into pool C by running the following cmdlet:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. <span data-ttu-id="f2671-154">Lync Server 응답 그룹 서비스 워크플로를 풀 B에서 풀 C로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-154">Import Lync Server Response Group service workflows into pool C from pool B.</span></span>
    
    <span data-ttu-id="f2671-155">그룹 B에서 풀 C로 응답 그룹 구성을 가져오는 두 가지 옵션을 사용할 수 있습니다. 사용 하는 옵션은 풀 C의 응용 프로그램 수준 설정을 응용 프로그램 수준 설정과 풀 B에서 덮어쓸지 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-155">You have two options are for importing the Response Group configuration from pool B to pool C. Which option you use depends on whether you want to overwrite the application-level settings of pool C with the application-level settings in pool B.</span></span>
    
      - <span data-ttu-id="f2671-156">그룹 C 설정을 덮어쓰려면 **ReplaceExistingSettings** 옵션을 사용 하 여 **export-csrgsconfiguration** cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-156">If you want to overwrite the Pool C settings, run the **Import-CsRgsConfiguration** cmdlet with the **ReplaceExistingSettings** option:</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - <span data-ttu-id="f2671-157">풀 C 설정을 덮어쓰지 않으려면 **ReplaceExistingSettings** 옵션 없이 **export-csrgsconfiguration** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-157">If you do not want to overwrite the Pool C settings, use the **Import-CsRgsConfiguration** cmdlet without the **ReplaceExistingSettings** option.</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="f2671-158">그룹 C의 응용 프로그램 수준 설정을 백업 풀 (풀 B)의 설정으로 덮어쓰지 않으려면 응답 그룹 응용 프로그램은 하나의 응용 프로그램 수준 집합만 저장할 수 있으므로 풀 B의 응용 프로그램 수준 설정이 손실 됩니다. 풀 당 설정</span><span class="sxs-lookup"><span data-stu-id="f2671-158">Keep in mind that if you do not want to overwrite the application-level settings of Pool C with the settings of the backup pool (pool B), pool B’s application-level settings will be lost because the Response Group application can store only one set of application-level settings per pool.</span></span>

    
    </div>

18. <span data-ttu-id="f2671-159">다음 cmdlet을 실행 하 여 풀 C로 가져온 응답 그룹을 표시 하 여 응답 그룹 구성 가져오기가 성공적으로 수행 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-159">Verify that the Response Group configuration import was successful by running the following cmdlets to display the response groups that have been imported to Pool C.</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. <span data-ttu-id="f2671-160">풀 C에서 가져온 구성을 확인 한 경우에는 풀 B에서 기본 풀이 소유한 응답 그룹을 제거 합니다. 이렇게 하면 응답 그룹의 가동 중지 시간이 최소화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-160">When the imported configuration has been verified in pool C, remove the response groups owned by the primary pool from pool B. This will minimize the downtime of the response groups.</span></span>
    
    <span data-ttu-id="f2671-161">이 단계에서는 내보낸 구성을 사용 하 여 새 파일을 만든 다음 풀 B에서 해당 파일을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-161">This step creates a new file with the exported configuration, and then removes the file from pool B.</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. <span data-ttu-id="f2671-162">풀로 이동 그룹 A가 풀 A에서 풀 B로 이동 된 지정 되지 않은 번호 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-162">Move to pool C the Unassigned Number ranges that were moved from pool A to pool B.</span></span>
    
      - <span data-ttu-id="f2671-163">풀 A에서 다시 만듭니다. C 풀 A에서 풀 A를 다시 만든 모든 공지입니다. 이동할 알림을 배포할 때 오디오 파일을 사용 하는 경우에는 이러한 파일을 사용 하 여 풀 C에 알림을 다시 만들어야 합니다. 풀 C에서 알림을 다시 만들려면 **새-csannouncement** cmdlet을 사용 하 고, 상위 서비스로 C를 풀 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-163">Re-create in pool C all announcements that were re-created from pool A in pool B. If any audio files were used when deploying the announcements to be moved, you will need to use these files to re-create the announcements in pool C. To re-create the announcements in pool C, use the **New-CsAnnouncement** cmdlets, with pool C as the Parent service.</span></span>
    
      - <span data-ttu-id="f2671-164">대상 그룹으로 지정-그룹 A에서 풀 B로 대상이 지정 되지 않은 모든 할당 되지 않은 번호 범위에 대해 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-164">Retarget to pool C all the unassigned number ranges that were retargeted from pool A to pool B. Run the following cmdlet for every Unassigned Number range that needs to be retargeted:</span></span>
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - <span data-ttu-id="f2671-165">반드시 풀 B에서 제거 풀 C에서 더 이상 사용 하지 않는 경우에는 해당 이전에 다시 만들어진 공지입니다. 알림을 제거 하려면 **csannouncement** a r i 공지 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-165">(Optional) Remove from pool B the announcements that were re-created in pool C if they are no longer in use in pool B. To remove announcements, use the **Remove-CsAnnouncement** cmdlet.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f2671-166">"Exchange UM"을 알림 서비스로 사용 하는 할당 되지 않은 번호 범위에는이 단계가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-166">This step is not required for unassigned number ranges that use "Exchange UM" as the announcement service.</span></span>

        
        </div>

21. <span data-ttu-id="f2671-167">다음 cmdlet을 실행 하 여 풀 A에서 풀 A의 사용자 데이터를 정리 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-167">Clean up user data of pool A in pool B by running the following cmdlet:</span></span>
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. <span data-ttu-id="f2671-168">토폴로지 작성기에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-168">Do the following in Topology Builder:</span></span>
    
      - <span data-ttu-id="f2671-169">Unpair 풀 A 및 풀 B와 풀 C를 차례로 두 번 누릅니다. 그런 다음 토폴로지에서 풀 A를 제거 하 고 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-169">Unpair pool A and pool B. Pair pool B and pool C. Then remove Pool A from the topology and publish it.</span></span> <span data-ttu-id="f2671-170">방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-170">To do so:</span></span>
        
          - <span data-ttu-id="f2671-171">토폴로지 작성기에서 풀 B를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-171">In Topology Builder, right-click on Pool B, and then click **Edit Properties**.</span></span>
        
          - <span data-ttu-id="f2671-172">왼쪽 창에서 **복구** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-172">Click **Resiliency** in the left pane.</span></span>
        
          - <span data-ttu-id="f2671-173">**연결 된 백업 풀**아래 상자에서 pool C를 선택 합니다 .이 풀은 이전에 풀 B와 연결 되어 있으므로 연결 된 백업 풀 선택 상자에 먼저 그룹 A가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-173">In the box below **Associated Backup Pool**, select Pool C. Note that the Associated Backup Pool selection box will initially display pool A, because pool B was previously associated with this pool.</span></span>
        
          - <span data-ttu-id="f2671-174">**자동 음성 장애 조치(failover) 및 장애 복구(failback)** 를 선택하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-174">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
            
            <span data-ttu-id="f2671-175">이제 이 풀에 대한 세부 정보를 표시하면 연결된 풀이 오른쪽 창의 **탄성** 아래에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-175">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span>
        
          - <span data-ttu-id="f2671-176">콘솔 트리에서 풀 A를 마우스 오른쪽 단추로 클릭 한 다음 삭제를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-176">In the console tree, right-click pool A, and then click Delete.</span></span>
        
          - <span data-ttu-id="f2671-177">토폴로지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-177">Publish the topology.</span></span>

23. <span data-ttu-id="f2671-178">풀 C에서 부트스트랩 응용 프로그램을 실행 하 여 백업 서비스 응용 프로그램을 설치한 다음, 풀 C의 로컬 컴퓨터에 있는 배포 폴더에서 다음을 실행 하 여 백업 서비스 응용 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-178">Run the bootstrapping application on pool C to install the backup service application, and then start the backup service application by running the following from the deployment folder on a local machine in pool C:</span></span>
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. <span data-ttu-id="f2671-179">다음 cmdlet을 실행 하 여 풀 B에서 백업 서비스 응용 프로그램을 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-179">Restart the backup service application on pool B by running the following cmdlets:</span></span>
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. <span data-ttu-id="f2671-180">풀 C가 SE (Standard Edition) 풀이 고 풀 B에 CMS가 있는 경우 다음 cmdlet을 실행 하 여 풀 C에 CMS 데이터베이스를 수동으로 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-180">If pool C is a Standard Edition (SE) Pool and pool B has CMS, install the CMS database manually on pool C by running the following cmdlet:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. <span data-ttu-id="f2671-181">백업 서비스를 호출 하 여 이전 회의 콘텐츠를 그룹 B에서 함께 연결 하기 전에 생성 된 pool C로 동기화 하 고, 풀 c와 B 및 C가 함께 연결 된 풀 B에서 새 회의 콘텐츠를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-181">Invoke the backup service to sync old conferencing content from pool B to pool C that was generated before pairing B and C together, and to sync new conferencing content from pool C to pool B that was generated after starting pool C and before B and C were paired together.</span></span> <span data-ttu-id="f2671-182">이렇게 하려면 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-182">To do so, run the following cmdlets:</span></span>
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. <span data-ttu-id="f2671-183">풀 A와 연결 된 각 Sba (survivable 분기 기기 X에 대해 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-183">For each Survivable Branch Appliance X associated with pool A:</span></span>
    
      - <span data-ttu-id="f2671-184">다음 cmdlet을 실행 하 여 SBA X를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-184">Shut down SBA X by running the following cmdlet:</span></span>
        
            Stop-CsWindowsService
    
      - <span data-ttu-id="f2671-185">SBA X에 홈에 있는 사용자 목록을 포함 하는 파일을 만듭니다. 이 목록은 사용자를 30 단계에서 SBA X로 다시 이동할 때 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-185">Create a file that contains a list of users homed on SBA X. The list will be needed when the users are moved back to SBA X in step 30.</span></span> <span data-ttu-id="f2671-186">이렇게 하려면 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-186">To do so, run the following cmdlet:</span></span>
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - <span data-ttu-id="f2671-187">SBA X에 있는 사용자가 다음 cmdlet을 실행 하 여 풀 C로 이동 하도록 강제 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-187">Force users homed on SBA X to move to pool C by running the following cmdlet:</span></span>
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - <span data-ttu-id="f2671-188">다음 cmdlet을 먼저 실행 하 여 이러한 사용자의 데이터를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-188">Update the data of these users by first running the following cmdlets:</span></span>
        
            Convert-csUserData -InputFile <Data file exported from PoolB> -OutputFile c:\Logs\ExportedUserData.xml -TargetVersionLync2010 
            $a=get-csuser -Filter {RegistrarPool -eq "FQDN of SBA X"} | select SipAddress
            foreach($x in $a) {$x.SipAddress.Substring(4) >> users.txt}
        
        <span data-ttu-id="f2671-189">다음 스크립트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-189">And then run this script:</span></span>
        
            $users=gc c:\logs\users.txt
            foreach ($user in $users)
            {
            Update-CsUserData -FileName c:\logs\exportedUserDAta.xml -UserFilter $user - 
            }
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f2671-190">풀 A에 연결 된 SBAs에 있는 사용자가 그룹 C로 이동 될 때까지 서비스 중단이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-190">A service outage will occur for users who are homed on SBAs that are associated with pool A until these users are moved to pool C.</span></span>

        
        </div>

28. <span data-ttu-id="f2671-191">토폴로지 작성기에서 이전에 풀 A와 연결 된 각 SBA X에 대해 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-191">In Topology Builder, for each SBA X previously associated with Pool A, do the following:</span></span>
    
      - <span data-ttu-id="f2671-192">풀 C로 연결을 변경 합니다. 이렇게 하려면 분기 사이트를 클릭 하 고 Sba (survivable Branch 기기 또는 Servers 노드를 확장 한 다음 **Sba (survivable Branch 기기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-192">Change the association to Pool C. To do so, click the branch site, expand the Survivable Branch Appliances or Servers node, and click **Survivable Branch Appliance**.</span></span> <span data-ttu-id="f2671-193">그런 다음이 Sba (survivable 분기 기기가이를 풀 C로 연결 하는 **프런트 엔드 풀, 사용자 서비스 풀을** 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-193">Then select the **Front End pool, User Services Pool** that this Survivable Branch Appliance will connect to as Pool C, and then click **Next**.</span></span>
    
      - <span data-ttu-id="f2671-194">토폴로지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-194">Publish the topology.</span></span> <span data-ttu-id="f2671-195">이렇게 하려면 콘솔 트리에서 새 **Sba (survivable Branch 기기**를 마우스 오른쪽 단추로 클릭 하 고 **토폴로지**를 클릭 한 다음 **게시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-195">To do so, in the console tree, right-click the new **Survivable Branch Appliance**, click **Topology**, and then click **Publish**.</span></span>

29. <span data-ttu-id="f2671-196">이제 풀 C에 연결 된 각 SBA X에 대해 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-196">For each SBA X now associated with pool C:</span></span>
    
      - <span data-ttu-id="f2671-197">Sba (survivable branch 기기에서 다음 cmdlet을 실행 하 여 SBA X를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-197">Start SBA X by running the following cmdlet on the survivable branch appliance:</span></span>
        
            Start-CsWindowsService
    
      - <span data-ttu-id="f2671-198">다음 cmdlet을 실행 하 여 SBA X에 원래 있던 사용자를 풀 C에서 SBA X로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2671-198">Move users who were originally homed on SBA X from pool C to SBA X by running the following cmdlet.</span></span>
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

</div>

</div>

<span> </span>

</div>

</div>

</div>

