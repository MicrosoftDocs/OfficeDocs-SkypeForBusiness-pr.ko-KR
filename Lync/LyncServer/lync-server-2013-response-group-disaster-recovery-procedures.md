---
title: Lync Server 2013 응답 그룹 재해 복구 절차
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response group disaster recovery procedures
ms:assetid: b49577b7-0ca3-4f20-b614-f3a2a0046b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205186(v=OCS.15)
ms:contentKeyID: 48185171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7f28f13d1acdbdae58b1aadd6f73871af270b7d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983117"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-disaster-recovery-procedures-in-lync-server-2013"></a><span data-ttu-id="1746a-102">Lync Server 2013의 응답 그룹 재해 복구 절차</span><span class="sxs-lookup"><span data-stu-id="1746a-102">Response group disaster recovery procedures in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1746a-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1746a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1746a-104">재해 복구의 장애 조치 단계에서 응답 그룹은 기본 풀 (사용할 수 없음) 및 백업 풀에 여러 풀에 위치 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-104">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool.</span></span> <span data-ttu-id="1746a-105">두 풀의 응답 그룹에는 동일한 이름과 소유자 (기본 풀)가 있지만 부모 항목이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-105">The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span> <span data-ttu-id="1746a-106">이 기간 동안 응답 그룹 cmdlet은 약간 다르게 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-106">During this time, Response Group cmdlets work a little differently.</span></span> <span data-ttu-id="1746a-107">다음 절차에 명시 된 대로 매개 변수를 사용 하세요.</span><span class="sxs-lookup"><span data-stu-id="1746a-107">Be sure to use parameters as specified in the following procedure.</span></span> <span data-ttu-id="1746a-108">장애 조치 단계에서 cmdlet을 작동 하는 방법에 대 한 자세한 내용은 NextHop 블로그 문서 "Lync Server 2013: 재해 복구 중 응답 그룹 [http://go.microsoft.com/fwlink/p/?LinkId=263957](http://go.microsoft.com/fwlink/p/?linkid=263957)복구"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1746a-108">For details about how cmdlets work during the failover phase, see NextHop blog article "Lync Server 2013: Recovering Response Groups During Disaster Recovery" at [http://go.microsoft.com/fwlink/p/?LinkId=263957](http://go.microsoft.com/fwlink/p/?linkid=263957).</span></span> <span data-ttu-id="1746a-109">이 블로그 문서는 출시 버전의 Lync Server 2013에도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-109">This blog article also applies to the released version of Lync Server 2013.</span></span>

<span data-ttu-id="1746a-110">Lync Server 응답 그룹 서비스에 대 한 재해 복구를 준비 하 고 수행 하려면 다음 절차의 단계를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-110">Use the steps in the following procedure to prepare for and perform disaster recovery for Lync Server Response Group service.</span></span>

<div>

## <a name="to-fail-over-and-fail-back-response-group"></a><span data-ttu-id="1746a-111">응답 그룹 장애 조치 및 실패 복구</span><span class="sxs-lookup"><span data-stu-id="1746a-111">To fail over and fail back Response Group</span></span>

1.  <span data-ttu-id="1746a-112">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="1746a-113">백업을 정기적으로 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-113">Routinely perform backups.</span></span> <span data-ttu-id="1746a-114">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-114">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="1746a-115">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-115">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimary.zip"

3.  <span data-ttu-id="1746a-116">중단 하는 동안 백업 풀로 장애 조치 (failover) 한 후 응답 그룹을 백업 풀로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-116">During an outage, after failover to the backup pool, import the response groups to the backup pool.</span></span> <span data-ttu-id="1746a-117">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-117">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<backup pool FQDN>" -FileName "<backup path and file name>"
    
    <span data-ttu-id="1746a-118">백업 풀의 응용 프로그램 수준 설정을 기본 풀의 설정으로 바꾸려면 – ReplaceExistingSettings 매개 변수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-118">If you want to replace the application-level settings in the backup pool with the settings from the primary pool, include the –ReplaceExistingSettings parameter.</span></span> <span data-ttu-id="1746a-119">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-119">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:backup.contoso.com" -FileName "C:\RgsExportPrimary.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="1746a-120">백업 풀의 설정을 바꾸지 않고 주 풀을 복구할 수 없는 경우 기본 풀 설정이 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-120">If you do not replace the settings in the backup pool and the primary pool can't be recovered, the primary pool settings will be lost.</span></span> <span data-ttu-id="1746a-121">자세한 내용은 <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Lync Server 2013의 응답 그룹 장애 복구 계획</A>을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1746a-121">For details, see <A href="lync-server-2013-planning-for-response-group-disaster-recovery.md">Planning for response group disaster recovery in Lync Server 2013</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="1746a-122">가져온 응답 그룹을 표시 하 여 성공적으로 가져오기 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-122">Verify that the import was successful by displaying the imported response groups.</span></span> <span data-ttu-id="1746a-123">가져온 응답 그룹은 여전히 기본 풀에서 소유 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-123">The imported response groups are still owned by the primary pool.</span></span> <span data-ttu-id="1746a-124">이렇게 하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-124">Do the following:</span></span>
    
      - <span data-ttu-id="1746a-125">기본 풀에서 소유 하는 백업 풀의 모든 워크플로를 표시 하 고 모든 기본 풀 워크플로가 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-125">Display all the workflows in the backup pool that are owned by the primary pool, and verify that all the primary pool workflows are included.</span></span> <span data-ttu-id="1746a-126">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-126">At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="1746a-127">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-127">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com"
    
      - <span data-ttu-id="1746a-128">기본 풀에서 소유 하는 백업 풀의 모든 큐를 표시 하 고 모든 기본 풀 큐가 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-128">Display all the queues in the backup pool that are owned by the primary pool, and verify that all the primary pool queues are included.</span></span> <span data-ttu-id="1746a-129">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-129">At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="1746a-130">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-130">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="1746a-131">기본 풀에서 소유 하는 백업 풀의 모든 에이전트 그룹을 표시 하 고 모든 기본 풀 에이전트 그룹이 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-131">Display all the agent groups in the backup pool that are owned by the primary pool, and verify that all the primary pool agent groups are included.</span></span> <span data-ttu-id="1746a-132">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-132">At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="1746a-133">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-133">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="1746a-134">주 풀에서 소유 하는 백업 풀의 모든 비즈니스 시간을 표시 하 고 모든 기본 풀의 비즈니스 시간이 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-134">Display all the hours of business in the backup pool that are owned by the primary pool, and verify that all the primary pool hours of business are included.</span></span> <span data-ttu-id="1746a-135">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-135">At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="1746a-136">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-136">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
      - <span data-ttu-id="1746a-137">기본 풀에서 소유 하는 백업 풀의 모든 공휴일 집합을 표시 하 고 모든 기본 풀 공휴일 집합이 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-137">Display all the holiday sets in the backup pool that are owned by the primary pool, and verify that all the primary pool holiday sets are included.</span></span> <span data-ttu-id="1746a-138">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-138">At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer"<primary pool FQDN>
        
        <span data-ttu-id="1746a-139">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-139">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer"primary.contoso.com"
    
    <span data-ttu-id="1746a-140">또는-Owner 매개 변수 대신 – ShowAll 매개 변수를 사용 하 여 기본 풀에서 소유 하는 파일과 백업 풀에서 소유 하 고 있는 모든 응답 그룹을 백업 풀에 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-140">Alternatively, you can display all the response groups in the backup pool, including the ones owned by the primary pool and the ones owned by the backup pool by using the –ShowAll parameter instead of the –Owner parameter.</span></span> <span data-ttu-id="1746a-141">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-141">For example:</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<backup pool FQDN>" -ShowAll
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1746a-142">– ShowAll 매개 변수 또는 – Owner 매개 변수 중 하나를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-142">You must use either the –ShowAll parameter or the –Owner parameter.</span></span> <span data-ttu-id="1746a-143">이러한 매개 변수 중 하나를 사용 하지 않는 경우 백업 풀로 가져온 응답 그룹이 cmdlet에서 반환 된 결과에 나열 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-143">If you do not use either of these parameters, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>

    
    </div>

5.  <span data-ttu-id="1746a-144">가져온 응답 그룹에 전화를 걸고 통화가 올바르게 처리 되었는지 확인 하 여 가져오기가 성공적으로 수행 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-144">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

6.  <span data-ttu-id="1746a-145">백업 풀의 에이전트 그룹에 로그인 하려면 공식 에이전트 그룹의 구성원 인 에이전트를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-145">Request agents who are members of formal agent groups to sign in to their agent groups in the backup pool.</span></span>

7.  <span data-ttu-id="1746a-146">가져온 응답 그룹을 평소 대로 관리 하 고 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-146">Manage and modify the imported response groups as usual.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1746a-147">응답 그룹이 백업 풀에 있는 동안에는 Lync Server Management Shell을 사용 하 여 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-147">While the response groups are in the backup pool, you need to use Lync Server Management Shell to manage them.</span></span> <span data-ttu-id="1746a-148">Lync Server 제어판을 사용 하 여 백업 풀로 가져온 응답 그룹을 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-148">You cannot use Lync Server Control Panel to manage the response groups that you imported to the backup pool.</span></span>

    
    </div>

8.  <span data-ttu-id="1746a-149">주 풀을 복원 하 고 장애 복구를 완료 한 후에는 백업 풀로 가져온 기본 풀 응답 그룹을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-149">After the primary pool is restored and failback is complete, export the primary pool response groups that were imported to the backup pool.</span></span> <span data-ttu-id="1746a-150">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-150">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source ApplicationServer:<backup pool FQDN> -Owner ApplicationServer:<primary pool FQDN> -FileName "<backup path and file name>"

9.  <span data-ttu-id="1746a-151">응답 그룹을 다시 기본 풀로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-151">Import the response groups back to the primary pool.</span></span> <span data-ttu-id="1746a-152">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-152">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>"
    
    <span data-ttu-id="1746a-153">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-153">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:primary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1746a-154">복구 하는 동안 풀을 다시 빌드하는 경우 (FQDN (정규화 된 도메인 이름)이 동일 하거나 다른 지에 관계 없이 – OverwriteOwner 매개 변수를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-154">If you rebuild a pool during recovery, whether with the same or a different fully qualified domain name (FQDN), you need to use the –OverwriteOwner parameter.</span></span> <span data-ttu-id="1746a-155">메시지를 표시 하는 규칙으로 응답 그룹을 다시 기본 풀로 가져올 때 항상 – OverwriteOwner 매개 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-155">As a rule of thumb, you can always use the –OverwriteOwner parameter when you import response groups back to the primary pool.</span></span>

    
    </div>
    
    <span data-ttu-id="1746a-156">기본 풀을 바꿀 새 풀 (동일한 또는 다른 FQDN)을 배포 하 고 새 풀에 대 한 백업 풀의 응용 프로그램 수준 설정을 사용 하려면 – ReplaceExistingSettings 매개 변수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-156">If you deployed a new pool (with the same or a different FQDN) to replace the primary pool, and you want to use the application-level settings from the backup pool for the new pool, include the –ReplaceExistingSettings parameter.</span></span> <span data-ttu-id="1746a-157">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-157">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<new primary pool FQDN>" -OverwriteOwner -FileName "<exported path and file name>" -ReplaceExistingSettings
    
    <span data-ttu-id="1746a-158">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-158">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:newprimary.contoso.com" -OverwriteOwner -FileName "C:\RgsExportPrimaryUpdated.zip" -ReplaceExistingSettings
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1746a-159">새 풀에 대 한 응용 프로그램 수준 설정 및 기본 음악 대기 오디오 파일을 백업 풀의 설정으로 바꾸지 않으려는 경우 새 풀에는 기본 응용 프로그램 수준 설정이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-159">If you don't want to replace the application-level settings and default music-on-hold audio file for the new pool with the settings from the backup pool, the new pool will use the default application-level settings.</span></span>

    
    </div>

10. <span data-ttu-id="1746a-160">가져온 응답 그룹 구성을 표시 하 여 기본 풀로 다시 가져오기가 성공적으로 수행 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-160">Verify that the import back to the primary pool was successful by displaying the imported response group configuration.</span></span> <span data-ttu-id="1746a-161">이렇게 하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-161">Do the following:</span></span>
    
      - <span data-ttu-id="1746a-162">기본 풀에 모든 워크플로를 표시 하 고 가져온 모든 워크플로가 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-162">Display all the workflows in the primary pool, and verify that all the imported workflows are included.</span></span> <span data-ttu-id="1746a-163">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-163">At the command line, type:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="1746a-164">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-164">For example:</span></span>
        
            Get-CsRgsWorkflow -Identity "service:ApplicationServer: primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="1746a-165">기본 풀의 모든 큐를 표시 하 고 가져온 모든 큐가 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-165">Display all the queues in the primary pool, and verify that all the imported queues are included.</span></span> <span data-ttu-id="1746a-166">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-166">At the command line, type:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="1746a-167">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-167">For example:</span></span>
        
            Get-CsRgsQueue -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="1746a-168">기본 풀에 모든 에이전트 그룹을 표시 하 고 가져온 모든 에이전트 그룹이 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-168">Display all the agent groups in the primary pool, and verify that all the imported agent groups are included.</span></span> <span data-ttu-id="1746a-169">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-169">At the command line, type:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer: <primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="1746a-170">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-170">For example:</span></span>
        
            Get-CsRgsAgentGroup -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="1746a-171">기본 풀에 모든 비즈니스 시간을 표시 하 고 가져온 모든 비즈니스 시간이 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-171">Display all the hours of business in the primary pool, and verify that all the imported hours of business are included.</span></span> <span data-ttu-id="1746a-172">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-172">At the command line, type:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="1746a-173">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-173">For example:</span></span>
        
            Get-CsRgsHoursOfBusiness -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll
    
      - <span data-ttu-id="1746a-174">기본 풀에 모든 공휴일 집합을 표시 하 고 가져온 공휴일 집합이 모두 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-174">Display all the holiday sets in the primary pool, and verify that all the imported holiday sets are included.</span></span> <span data-ttu-id="1746a-175">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-175">At the command line, type:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:<primary pool FQDN>" -ShowAll
        
        <span data-ttu-id="1746a-176">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-176">For example:</span></span>
        
            Get-CsRgsHolidaySet -Identity "service:ApplicationServer:primary.contoso.com" -ShowAll

11. <span data-ttu-id="1746a-177">가져온 응답 그룹에 전화를 걸고 통화가 올바르게 처리 되었는지 확인 하 여 가져오기가 성공적으로 수행 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-177">Verify that the import was successful by placing a call to an imported response group and verifying that the call is handled correctly.</span></span>

12. <span data-ttu-id="1746a-178">필요에 따라 백업 풀에서 기본 풀 소유의 응답 그룹을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-178">Optionally, remove the response groups owned by the primary pool from the backup pool.</span></span> <span data-ttu-id="1746a-179">명령줄에 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-179">At the command line, type:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<backup pool FQDN>" -Owner "service:ApplicationServer:<primary pool FQDN>" -FileName "<backup path and file name>" -RemoveExportedConfiguration
    
    <span data-ttu-id="1746a-180">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-180">For example:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:backup.contoso.com" -Owner "service:ApplicationServer:primary.contoso.com" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1746a-181">이 단계에서는 내보낸 구성을 사용 하 여 새 파일을 만든 다음 백업 풀에서 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="1746a-181">This step creates a new file with the exported configuration, and then removes it from the backup pool.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

