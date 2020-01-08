---
title: 'Lync Server 2013: 응답 그룹 재해 복구 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for response group disaster recovery
ms:assetid: 14e0f5dc-77cd-42cd-a9c9-4d0da38fb1cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204699(v=OCS.15)
ms:contentKeyID: 48183482
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70622364349eb83ecbc171cb3d5bf894ba03d3f9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985654"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="d5098-102">Lync Server 2013의 응답 그룹 재해 복구 계획</span><span class="sxs-lookup"><span data-stu-id="d5098-102">Planning for response group disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5098-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d5098-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d5098-104">이 섹션에서는 재해 복구를 위해 응답 그룹을 준비 하는 몇 가지 방법과 재해 복구 프로세스에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-104">This section describes some ways to prepare response groups for disaster recovery and provides an overview of the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a><span data-ttu-id="d5098-105">응답 그룹 재해 복구 준비</span><span class="sxs-lookup"><span data-stu-id="d5098-105">Preparing for Response Group Disaster Recovery</span></span>

<span data-ttu-id="d5098-106">재해 복구 절차를 준비 하 고 수행할 때 다음 사항에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="d5098-106">Keep the following in mind when you prepare for and carry out disaster recovery procedures.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d5098-107">공존 환경에서는이 문서에서 설명 하는 재해 복구 절차에 대해 Lync Server 2013 응답 그룹만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-107">In a coexistence environment, only the Lync Server 2013 response groups are supported for the disaster recovery procedures described in this document.</span></span>



</div>

  - <span data-ttu-id="d5098-108">용량 계획을 수립할 때 재해 복구 계획을 수립 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-108">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="d5098-109">재해 복구 용량을 위해 쌍으로 연결 된 풀의 각 풀은 두 풀의 모든 응답 그룹에 대 한 작업 부하를 처리할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-109">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of all the response groups in both pools.</span></span> <span data-ttu-id="d5098-110">응답 그룹 용량 계획에 대 한 자세한 내용은 [Lync Server 2013의 응답 그룹에 대 한 용량 계획](lync-server-2013-capacity-planning-for-response-group.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d5098-110">For details about Response Group capacity planning, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).</span></span>

  - <span data-ttu-id="d5098-111">이 문서에서 설명 하는 내보내기 절차를 사용 하 여 응답 그룹 응용 프로그램을 배포한 모든 프런트 엔드 풀에 있는 모든 응답 그룹 구성의 정기 백업 복사본을 찍습니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-111">Take regular backup copies of all the response group configurations in all the Front End pools where you deployed the Response Group application by using the export procedure described in this document.</span></span> <span data-ttu-id="d5098-112">자세한 내용은 [Lync Server 2013의 응답 그룹 장애 복구 절차](lync-server-2013-response-group-disaster-recovery-procedures.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d5098-112">For details, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span> <span data-ttu-id="d5098-113">백업 복사본은 안전한 위치에 보관 하세요.</span><span class="sxs-lookup"><span data-stu-id="d5098-113">Keep the backup copies in a safe location.</span></span>

  - <span data-ttu-id="d5098-114">기록 및 음악 포함 파일을 포함 하 여 응답 그룹 응용 프로그램에 사용 된 모든 원본 오디오 파일의 백업 복사본을 별도로 보관 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-114">Keep a separate backup copy of all the original audio files you used for the Response Group application, including any recordings and music-on-hold files.</span></span> <span data-ttu-id="d5098-115">백업 파일은 안전한 곳에 보관 하세요.</span><span class="sxs-lookup"><span data-stu-id="d5098-115">Keep the backup files in a safe location.</span></span>

  - <span data-ttu-id="d5098-116">Lync Server 2013 재해 복구의 경우 모든 응답 그룹 설정에는 배포 전체에서 고유한 이름이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-116">For Lync Server 2013 disaster recovery, all Response Group settings must have unique names across your deployment.</span></span> <span data-ttu-id="d5098-117">이 요구 사항은 워크플로, 큐, 에이전트 그룹, 휴일 집합 및 비즈니스 시간에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-117">This requirement applies to workflows, queues, agent groups, holiday sets, and hours of business.</span></span> <span data-ttu-id="d5098-118">기본 및 백업 풀이 계속 활성 상태 이거나 장애 조치 (failover) 절차를 시작 해야 하는 경우이 요구 사항이 충족 되는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-118">You should verify that this requirement is met when the primary and backup pools are still active, and before you need to initiate any failover procedure.</span></span> <span data-ttu-id="d5098-119">응답 그룹 데이터를 백업 풀로 가져오는 동안 이름 충돌이 발생 하는 경우 가져오기에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-119">If you encounter name conflicts while importing response group data to the backup pool, the import fails.</span></span> <span data-ttu-id="d5098-120">가져오기 및 장애 조치 절차를 완료 하려면 백업 풀에서 응답 그룹 개체의 이름을 바꾸거나 – ResolveNameConflicts 매개 변수와 함께 **CsRgsConfiguration** cmdlet을 사용 하 여 응답 그룹 개체에 고유 하 게 식별 되는 번호를 추가 하 여 충돌을 자동으로 해결 하는 이름 충돌을 해결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-120">To complete the import and failover procedure, you need to resolve the name conflicts by renaming the response group object in the backup pool or by using the **Import-CsRgsConfiguration** cmdlet with the –ResolveNameConflicts parameter to automatically resolve the conflict by appending a unique identifying number to the response group object.</span></span>

  - <span data-ttu-id="d5098-121">일반적으로 매일 백업을 수행 하는 것이 좋지만 많은 양의 변경 내용이 있는 경우에는 백업을 더 자주 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-121">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups.</span></span> <span data-ttu-id="d5098-122">재해가 발생 했을 때 손실 될 수 있는 정보의 양은 백업 빈도 및 변경 빈도 및 볼륨에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-122">The amount of information you can lose in the event of a disaster depends on the frequency of your backups, as well as the frequency and volume of changes.</span></span>

  - <span data-ttu-id="d5098-123">재해 또는 장애 조치 작업이 발생 하기 전에 응답 그룹을 백업 풀로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-123">It is possible to import response groups to a backup pool before a disaster or failover operation occurs.</span></span> <span data-ttu-id="d5098-124">응답 그룹을 미리 가져오면 호출이 백업 풀로 라우팅되는 즉시 Lync Server 응답 그룹 서비스를 백업 풀에 복원할 수 있기 때문에 가동 중지 시간이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-124">Importing response groups in advance reduces downtime, because the Lync Server Response Group service can be restored in the backup pool as soon as calls are routed to the backup pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d5098-125">응답 그룹 응용 프로그램은 장애 조치가 완료 될 때까지 비활성 풀에 속한 에이전트에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-125">The Response Group application cannot reach any agents homed in an inactive pool until failover is complete.</span></span> <span data-ttu-id="d5098-126">이 기간 동안 응답 그룹 응용 프로그램은 해당 에이전트를 사용할 수 없는 것 처럼 통화를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-126">During this time, the Response Group application processes calls as if those agents are unavailable.</span></span>

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a><span data-ttu-id="d5098-127">응답 그룹 재해 복구 프로세스</span><span class="sxs-lookup"><span data-stu-id="d5098-127">Response Group Disaster Recovery Process</span></span>

<span data-ttu-id="d5098-128">재해가 발생할 경우 다음 복구 방법 중 하나를 사용 하 여 응답 그룹을 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-128">In the event of a disaster, you can recover response groups by using either of the following recovery approaches:</span></span>

  - <span data-ttu-id="d5098-129">백업 풀로 장애 조치 하 고 원래 풀로 장애 복구 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-129">Fail over to a backup pool and then fail back to the original pool.</span></span>

  - <span data-ttu-id="d5098-130">백업 풀로 장애 조치 하 고 다른 FQDN (정규화 된 도메인 이름)을 사용 하 여 새 풀을 만든 다음 응답 그룹을 새 풀로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-130">Fail over to a backup pool, create a new pool with a different fully qualified domain name (FQDN), and then import the response groups to the new pool.</span></span>

<span data-ttu-id="d5098-131">재해 복구의 장애 조치 단계에서 응답 그룹은 기본 풀 (사용할 수 없음) 및 백업 풀에 여러 풀에 위치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-131">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool.</span></span> <span data-ttu-id="d5098-132">두 풀의 응답 그룹에는 동일한 이름과 소유자 (기본 풀)가 있지만 부모 항목이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-132">The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span>

<span data-ttu-id="d5098-133">다른 FQDN을 사용 하 여 새 풀을 만들어 복구 하는 경우 새 풀을 가져올 때 응답 그룹의 소유자로 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-133">When you recover by creating a new pool with a different FQDN, you need to assign the new pool as the owner of the response groups when you import them.</span></span> <span data-ttu-id="d5098-134">**CsRgsConfiguration** cmdlet에서 – OverwriteOwner 매개 변수를 사용 하 여 소유권을 명시적으로 다시 할당할 때 까지는 또는 응답 그룹의 소유권이 원본 풀에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-134">Ownership of response groups remains with the original pool unless or until you explicitly reassign ownership by using the –OverwriteOwner parameter with the **Import-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d5098-135">또한 복구 중에 풀을 다시 작성 한 경우 (즉, 응답 그룹 데이터베이스가 비어 있는 경우), 동일한 FQDN을 사용 하는지 여부에 상관 없이 – OverwriteOwner 매개 변수를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-135">You also need to use the –OverwriteOwner parameter if you rebuilt the pool during the recovery (that is, the Response Group database is empty), whether or not you use the same FQDN.</span></span> <span data-ttu-id="d5098-136">풀을 다시 빌드하지 않은 경우 – OverwriteOwner 매개 변수를 사용할 필요가 없지만 응답 그룹을 다시 기본 풀로 가져올 때마다이 매개 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-136">You do not need to use the –OverwriteOwner parameter if you did not rebuild the pool, but it is permissible to use this parameter whenever you import response groups back to the primary pool.</span></span>



</div>

<span data-ttu-id="d5098-137">풀 당 하나의 응용 프로그램 수준 응답 그룹 구성 설정 집합을 하나만 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-137">You can define only one set of application-level Response Group configuration settings per pool.</span></span> <span data-ttu-id="d5098-138">이러한 설정에는 기본 음악 보관 구성, 기본 음악 오디오 파일, 에이전트 ringback 유예 기간, 호출 컨텍스트 구성 등이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-138">These settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="d5098-139">이러한 구성 설정을 보려면 **Get-CsRgsConfiguration** cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-139">To view these configuration settings, run the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="d5098-140">**CsRgsConfiguration** cmdlet에 대 한 자세한 내용은 [get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d5098-140">For details about the **Get-CsRgsConfiguration** cmdlet, see [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).</span></span>

<span data-ttu-id="d5098-141">**CsRgsConfiguration** cmdlet에서 – ReplaceExistingSettings 매개 변수를 사용 하 여 해당 응용 프로그램 수준의 설정을 다른 풀로 전송할 수 있지만, 이렇게 하면 대상 풀의 설정이 재정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-141">You can transfer these application-level settings from one pool to another by using the **Import-CsRgsConfiguration** cmdlet with the –ReplaceExistingSettings parameter, but doing so overrides the settings in the destination pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d5098-142">다른 풀로 설정 전송에 대 한이 제약 조건은 응용 프로그램 수준 설정 및 기본 음악/보류 오디오 파일에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-142">This constraint about transferring settings to another pool is true only for the application-level settings and the default music-on-hold audio file.</span></span> <span data-ttu-id="d5098-143">에이전트 그룹, 큐, 워크플로, 비즈니스 시간 및 휴일 집합에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-143">It does not apply to agent groups, queues, workflows, business hours, and holiday sets.</span></span>



</div>

<span data-ttu-id="d5098-144">재해가 발생 했을 때 백업 풀의 응용 프로그램 수준 설정을 바꾸지 않고 주 풀을 복구할 수 없는 경우 기본 풀의 응용 프로그램 수준 설정이 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-144">If you don't want to replace the application-level settings in the backup pool during a disaster and the primary pool can't be recovered, the application-level settings from the primary pool will be lost.</span></span> <span data-ttu-id="d5098-145">복구 하는 동안 기본 풀을 바꿔야 하는 FQDN 또는 fqdn이 다른 새 풀을 만들어야 하는 경우 원래 응용 프로그램 수준 설정을 복구할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-145">If you need to create a new pool to replace the primary pool during recovery, either with the same FQDN or with a different FQDN, you can't recover the original application-level settings.</span></span> <span data-ttu-id="d5098-146">이 경우 이러한 설정을 사용 하 여 새 풀을 구성 하 고 음악 대기 오디오 파일을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-146">In this case, you need to configure the new pool with these settings and include the music-on-hold audio file.</span></span>

<span data-ttu-id="d5098-147">재해가 발생 한 동안 **CsRgsConfiguration** cmdlet을 사용 하 여 기본 풀의 응용 프로그램 수준 설정을 백업 풀로 전송 하기로 결정 한 경우 복구 중에 백업 풀의 설정을 기본 풀에서 백업 풀로 전송 하는 것과 동일한 방법으로 해당 풀로 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-147">If you decide to use the **Import-CsRgsConfiguration** cmdlet to transfer application-level settings from the primary pool to the backup pool during a disaster, you can then transfer the settings from the backup pool to the new pool during recovery in the same way that you transferred them from the primary pool to the backup pool.</span></span>

<span data-ttu-id="d5098-148">다음 표에서는 응답 그룹 복구와 관련 된 단계를 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-148">The following table is an overview of the steps involved in recovering response groups.</span></span>

<span data-ttu-id="d5098-149">이러한 단계를 수행 하는 방법에 대 한 자세한 내용은 [Lync Server 2013의 응답 그룹 장애 복구 절차](lync-server-2013-response-group-disaster-recovery-procedures.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d5098-149">For details about performing these steps, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span>

### <a name="response-group-disaster-recovery-steps"></a><span data-ttu-id="d5098-150">응답 그룹 재해 복구 단계</span><span class="sxs-lookup"><span data-stu-id="d5098-150">Response Group Disaster Recovery Steps</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d5098-151">단계의</span><span class="sxs-lookup"><span data-stu-id="d5098-151">Phase</span></span></th>
<th><span data-ttu-id="d5098-152">방법은</span><span class="sxs-lookup"><span data-stu-id="d5098-152">Steps</span></span></th>
<th><span data-ttu-id="d5098-153">필수 그룹 및 역할</span><span class="sxs-lookup"><span data-stu-id="d5098-153">Required groups and roles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d5098-154">중단 전</span><span class="sxs-lookup"><span data-stu-id="d5098-154">Before outage</span></span></p></td>
<td><p><span data-ttu-id="d5098-155">루틴을 기준으로 <strong>CsRgsConfiguration</strong> cmdlet을 실행 하 여 응답 그룹 응용 프로그램이 배포 된 모든 프런트 엔드 풀의 모든 응답 그룹 구성에 대 한 백업을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-155">On a routine basis, run the <strong>Export-CsRgsConfiguration</strong> cmdlet to create backups of all Response Group configurations in all Front End pools where Response Group application is deployed.</span></span></p></td>
<td><p><span data-ttu-id="d5098-156">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="d5098-156">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="d5098-157">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="d5098-157">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5098-158">비활성 동안</span><span class="sxs-lookup"><span data-stu-id="d5098-158">During outage</span></span></p></td>
<td><p><span data-ttu-id="d5098-159"><strong>가져오기-CsRgsConfiguration</strong> cmdlet을 실행 하 여 백업 된 Lync Server 응답 그룹 서비스 구성을 기본 풀에서 백업 풀로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-159">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the backed up Lync Server Response Group service configuration from the primary pool to the backup pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="d5098-160">백업 풀의 응용 프로그램 수준 응답 그룹 설정을 기본 풀의 설정으로 대체 하려면 – ReplaceExistingSettings 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-160">Use the –ReplaceExistingSettings parameter if you want to replace application-level Response Group settings in the backup pool with the settings from the primary pool.</span></span> <span data-ttu-id="d5098-161">기본 풀의 응용 프로그램 수준 설정을 백업 풀로 전송 하지 않고 주 풀을 복구할 수 없는 경우 기본 풀의 설정이 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-161">If you do not transfer the application-level settings from the primary pool to the backup pool, and the primary pool can't be recovered, you will lose the settings from the primary pool.</span></span>


</div></td>
<td><p><span data-ttu-id="d5098-162">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="d5098-162">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="d5098-163">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="d5098-163">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5098-164">가져온 후</span><span class="sxs-lookup"><span data-stu-id="d5098-164">After importing</span></span></p></td>
<td><p><span data-ttu-id="d5098-165">모든 응답 그룹 구성을 백업 풀로 가져왔는지 확인 하려면 – ShowAll 매개 변수 (모든 응답 그룹 표시) 또는 – Owner 매개 변수 (가져온 응답 그룹만 표시)를 사용 하 여 응답 그룹 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-165">Run Response Group cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were imported to the backup pool.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="d5098-166">– ShowAll 매개 변수 또는 – Owner 매개 변수를 사용 하지 않는 경우 백업 풀로 가져온 응답 그룹이 cmdlet에서 반환 된 결과에 나열 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-166">If you do not use either the –ShowAll parameter or the –Owner parameter, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>


</div>
<p><span data-ttu-id="d5098-167">다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-167">Run the following cmdlets:</span></span></p>
<ul>
<li><p><span data-ttu-id="d5098-168"><strong>Get-CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="d5098-168"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="d5098-169"><strong>Get-CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="d5098-169"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="d5098-170"><strong>Get-CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="d5098-170"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="d5098-171"><strong>Get-CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="d5098-171"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="d5098-172"><strong>Get-CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="d5098-172"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="d5098-173">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="d5098-173">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="d5098-174">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="d5098-174">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5098-175">장애 조치 이후</span><span class="sxs-lookup"><span data-stu-id="d5098-175">After failover</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d5098-176">백업 풀로 가져온 응답 그룹에 테스트 호출을 배치 하 고 통화가 올바르게 처리 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-176">Place a test call to a response group that was imported to the backup pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="d5098-177">모든 공식 에이전트는 백업 풀의 정식 그룹에 다시 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-177">All formal agents must sign in again to their formal groups on backup pool.</span></span></p></li>
<li><p><span data-ttu-id="d5098-178">구성 변경 내용 관리:</span><span class="sxs-lookup"><span data-stu-id="d5098-178">Manage configuration changes:</span></span></p>
<p><span data-ttu-id="d5098-179">백업 풀로 가져올지 또는 백업 풀에서 소유 하 든 지에 관계 없이 백업 풀의 응답 그룹은 중단 중 평소와 같이 수정 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-179">Response groups in the backup pool, whether imported to the backup pool or owned by the backup pool, can be modified as usual during the outage.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="d5098-180">Lync Server Management Shell을 사용 하 여 백업 풀로 가져온 응답 그룹을 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-180">You must use Lync Server Management Shell to manage the response groups that you imported to the backup pool.</span></span> <span data-ttu-id="d5098-181">이 응답 그룹은 백업 풀에 있는 동안 Lync Server 제어판을 사용 하 여 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-181">You cannot use Lync Server Control Panel to manage these response groups while they are in the backup pool.</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="d5098-182">해당 없음</span><span class="sxs-lookup"><span data-stu-id="d5098-182">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5098-183">복구 후, 장애 복구 전</span><span class="sxs-lookup"><span data-stu-id="d5098-183">After recovery, before failback</span></span></p></td>
<td><p><span data-ttu-id="d5098-184">-Source 매개 변수를 백업 풀로 지정 하 고-Owner 매개 변수를 기본 풀로 <strong>CsRgsConfiguration</strong> cmdlet을 실행 하 여 기본 풀이 소유한 응답 그룹을 백업 풀에서 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-184">Run the <strong>Export-CsRgsConfiguration</strong> cmdlet specifying the -Source parameter as the backup pool and the –Owner parameter as the primary pool to export the response groups owned by the primary pool from the backup pool.</span></span></p></td>
<td><p><span data-ttu-id="d5098-185">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="d5098-185">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="d5098-186">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="d5098-186">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5098-187">장애 복구 후</span><span class="sxs-lookup"><span data-stu-id="d5098-187">After failback</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d5098-188"><strong>CsRgsConfiguration</strong> cmdlet을 실행 하 여 응답 그룹을 다시 기본 풀로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-188">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the response groups back to the primary pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="d5098-189">주 풀을 복구할 수 없고 새 풀을 배포 하 여 해당 파일을 바꾸려면 – ReplaceExistingSettings 매개 변수를 사용 하 여 백업 풀의 응용 프로그램 수준 설정을 새 풀로 이전 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-189">If the primary pool can't be recovered and you deploy a new pool to replace it, use the –ReplaceExistingSettings parameter to transfer the application-level settings from the backup pool to the new pool.</span></span> <span data-ttu-id="d5098-190">백업 풀에서 설정을 전송 하지 않으면 새 풀에 기본 설정이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-190">If you do not transfer the settings from the backup pool, the new pool will use the default settings.</span></span>


</div></li>
<li><p><span data-ttu-id="d5098-191">모든 응답 그룹 구성을 성공적으로 다시 기본 풀로 가져왔는지 확인 하려면 – ShowAll 매개 변수 (모든 응답 그룹을 표시 하기 위해) 또는 – Owner 매개 변수를 사용 하 여 다음 cmdlet을 실행 합니다 (가져온 응답 그룹만 표시).</span><span class="sxs-lookup"><span data-stu-id="d5098-191">Run the following cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were successfully imported back to the primary pool:</span></span></p>
<ul>
<li><p><span data-ttu-id="d5098-192"><strong>Get-CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="d5098-192"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="d5098-193"><strong>Get-CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="d5098-193"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="d5098-194"><strong>Get-CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="d5098-194"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="d5098-195"><strong>Get-CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="d5098-195"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="d5098-196"><strong>Get-CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="d5098-196"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="d5098-197">기본 풀로 다시 가져온 응답 그룹에 테스트 호출을 배치 하 고 통화가 올바르게 처리 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-197">Place a test call to a response group that was imported back to the primary pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="d5098-198">또는-RemoveExportedConfiguration 매개 변수를 사용 하 여 백업 풀에서 <strong>CsRgsConfiguration</strong> cmdlet을 실행 하 여 백업 풀의 기본 풀에서 소유 하는 응답 그룹을 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5098-198">Optionally, run the <strong>Export-CsRgsConfiguration</strong> cmdlet on the backup pool with the –RemoveExportedConfiguration parameter to remove the response groups owned by the primary pool from the backup pool.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="d5098-199">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="d5098-199">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="d5098-200">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="d5098-200">CsResponseGroupAdministrator</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

