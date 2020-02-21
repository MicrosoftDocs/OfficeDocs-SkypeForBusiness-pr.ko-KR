---
title: 'Lync Server 2013: 응답 그룹 재해 복구 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for response group disaster recovery
ms:assetid: 14e0f5dc-77cd-42cd-a9c9-4d0da38fb1cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204699(v=OCS.15)
ms:contentKeyID: 48183482
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab630dae949d1972d9e5077035d88d91964034f1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201984"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="17905-102">Lync Server 2013에서 응답 그룹 재해 복구 계획</span><span class="sxs-lookup"><span data-stu-id="17905-102">Planning for response group disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17905-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="17905-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="17905-104">이 섹션에서는 재해 복구용으로 응답 그룹을 준비하는 몇 가지 방법에 대해 설명하며 재해 복구 프로세스에 대해 간략하게 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="17905-104">This section describes some ways to prepare response groups for disaster recovery and provides an overview of the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a><span data-ttu-id="17905-105">응답 그룹 재해 복구 준비</span><span class="sxs-lookup"><span data-stu-id="17905-105">Preparing for Response Group Disaster Recovery</span></span>

<span data-ttu-id="17905-106">재해 복구 절차를 준비 및 수행할 때는 다음 사항을 기억하십시오.</span><span class="sxs-lookup"><span data-stu-id="17905-106">Keep the following in mind when you prepare for and carry out disaster recovery procedures.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="17905-107">동시 사용 환경에서는이 문서에서 설명 하는 재해 복구 절차에 대해 Lync Server 2013 response 그룹만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="17905-107">In a coexistence environment, only the Lync Server 2013 response groups are supported for the disaster recovery procedures described in this document.</span></span>



</div>

  - <span data-ttu-id="17905-108">용량을 계획할 때 재해 복구도 계획합니다.</span><span class="sxs-lookup"><span data-stu-id="17905-108">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="17905-109">재해 복구 용량의 경우 쌍으로 지정된 풀의 각 풀이 두 풀의 모든 응답 그룹 작업을 처리할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17905-109">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of all the response groups in both pools.</span></span> <span data-ttu-id="17905-110">응답 그룹 용량 계획에 대 한 자세한 내용은 [Lync Server 2013에서 응답 그룹에 대 한 용량 계획](lync-server-2013-capacity-planning-for-response-group.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="17905-110">For details about Response Group capacity planning, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).</span></span>

  - <span data-ttu-id="17905-111">이 문서에서 설명 하는 내보내기 절차를 사용 하 여 응답 그룹 응용 프로그램을 배포한 모든 프런트 엔드 풀에 있는 모든 응답 그룹 구성의 백업 복사본을 정기적으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="17905-111">Take regular backup copies of all the response group configurations in all the Front End pools where you deployed the Response Group application by using the export procedure described in this document.</span></span> <span data-ttu-id="17905-112">자세한 내용은 [Lync Server 2013의 응답 그룹 재해 복구 절차](lync-server-2013-response-group-disaster-recovery-procedures.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="17905-112">For details, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span> <span data-ttu-id="17905-113">백업 복사본은 안전한 위치에 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="17905-113">Keep the backup copies in a safe location.</span></span>

  - <span data-ttu-id="17905-114">응답 그룹 응용 프로그램에 사용한 모든 원본 오디오 파일의 백업 복사본을 보관 합니다 (예를 들어, 모든 레코딩 및 음악 대기 파일 포함).</span><span class="sxs-lookup"><span data-stu-id="17905-114">Keep a separate backup copy of all the original audio files you used for the Response Group application, including any recordings and music-on-hold files.</span></span> <span data-ttu-id="17905-115">백업 파일은 안전한 위치에 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="17905-115">Keep the backup files in a safe location.</span></span>

  - <span data-ttu-id="17905-116">Lync Server 2013 재해 복구의 경우 모든 응답 그룹 설정에는 배포 전체에서 고유한 이름이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17905-116">For Lync Server 2013 disaster recovery, all Response Group settings must have unique names across your deployment.</span></span> <span data-ttu-id="17905-117">이 요구 사항은 워크플로, 큐, 에이전트 그룹, 휴일 집합 및 업무 시간에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="17905-117">This requirement applies to workflows, queues, agent groups, holiday sets, and hours of business.</span></span> <span data-ttu-id="17905-118">기본 풀과 백업 풀이 아직 활성 상태일 때와 장애 조치(failover) 절차를 시작하기 전에 이 요구 사항이 충족되었는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17905-118">You should verify that this requirement is met when the primary and backup pools are still active, and before you need to initiate any failover procedure.</span></span> <span data-ttu-id="17905-119">응답 그룹 데이터를 백업 풀로 가져오는 동안 이름 충돌이 발생하는 경우 가져오기가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="17905-119">If you encounter name conflicts while importing response group data to the backup pool, the import fails.</span></span> <span data-ttu-id="17905-120">가져오기 및 장애 조치(failover) 절차를 완료하려면 백업 풀에서 응답 그룹 개체 이름을 바꾸거나, -ResolveNameConflicts 매개 변수를 포함하여 **Import-CsRgsConfiguration** cmdlet을 사용해 응답 그룹 개체에 고유한 식별 번호를 추가함으로써 충돌을 자동으로 해결하는 방법으로 이름 충돌을 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17905-120">To complete the import and failover procedure, you need to resolve the name conflicts by renaming the response group object in the backup pool or by using the **Import-CsRgsConfiguration** cmdlet with the –ResolveNameConflicts parameter to automatically resolve the conflict by appending a unique identifying number to the response group object.</span></span>

  - <span data-ttu-id="17905-p105">일반적으로는 일별 백업을 수행하는 것이 좋지만 변경 내용이 많은 경우에는 백업을 더 자주 수행하도록 예약할 수 있습니다. 재해 시 손실될 수 있는 정보의 양은 백업의 빈도와 변경 내용의 양 및 변경 빈도에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="17905-p105">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups. The amount of information you can lose in the event of a disaster depends on the frequency of your backups, as well as the frequency and volume of changes.</span></span>

  - <span data-ttu-id="17905-123">재해 또는 장애 조치(failover) 작업을 수행하기 전에 응답 그룹을 백업 풀로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17905-123">It is possible to import response groups to a backup pool before a disaster or failover operation occurs.</span></span> <span data-ttu-id="17905-124">응답 그룹을 미리 가져오면 호출이 백업 풀로 라우팅되는 즉시 Lync Server 응답 그룹 서비스를 백업 풀에 복원할 수 있으므로 가동 중지 시간이 단축 됩니다.</span><span class="sxs-lookup"><span data-stu-id="17905-124">Importing response groups in advance reduces downtime, because the Lync Server Response Group service can be restored in the backup pool as soon as calls are routed to the backup pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="17905-125">응답 그룹 응용 프로그램은 장애 조치 (failover)가 완료 될 때까지 비활성 풀에 속한 에이전트에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="17905-125">The Response Group application cannot reach any agents homed in an inactive pool until failover is complete.</span></span> <span data-ttu-id="17905-126">이 시간 동안에는 응답 그룹 응용 프로그램이 해당 에이전트를 사용할 수 없는 것으로 통화를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="17905-126">During this time, the Response Group application processes calls as if those agents are unavailable.</span></span>

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a><span data-ttu-id="17905-127">응답 그룹 재해 복구 프로세스</span><span class="sxs-lookup"><span data-stu-id="17905-127">Response Group Disaster Recovery Process</span></span>

<span data-ttu-id="17905-128">재해 시 다음 복구 방식 중 하나를 사용하여 응답 그룹을 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17905-128">In the event of a disaster, you can recover response groups by using either of the following recovery approaches:</span></span>

  - <span data-ttu-id="17905-129">백업 풀로 장애 조치(failover) 한 다음 원본 풀로 장애 복구(failback)합니다.</span><span class="sxs-lookup"><span data-stu-id="17905-129">Fail over to a backup pool and then fail back to the original pool.</span></span>

  - <span data-ttu-id="17905-130">백업 풀로 장애 조치(failover)하고 다른 FQDN(정규화된 도메인 이름)을 사용하여 새 풀을 만든 후에 응답 그룹을 새 풀로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="17905-130">Fail over to a backup pool, create a new pool with a different fully qualified domain name (FQDN), and then import the response groups to the new pool.</span></span>

<span data-ttu-id="17905-p108">재해 복구의 장애 조치(failover) 단계 중에 응답 그룹은 여러 풀, 즉 사용할 수 없는 기본 풀과 백업 풀에 있습니다. 두 풀의 응답 그룹 이름과 소유자(기본 풀)는 같지만 상위 항목은 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="17905-p108">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool. The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span>

<span data-ttu-id="17905-133">다른 FQDN을 사용해 새 풀을 만들어서 복구하는 경우에는 응답 그룹을 가져올 때 응답 그룹 소유자로 새 풀을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17905-133">When you recover by creating a new pool with a different FQDN, you need to assign the new pool as the owner of the response groups when you import them.</span></span> <span data-ttu-id="17905-134">응답 그룹 소유권은 -OverwriteOwner 매개 변수를 포함하여 **Import-CsRgsConfiguration** cmdlet을 사용해 소유권을 명시적으로 다시 할당하지 않으면 이처럼 다시 할당할 때까지 원본 풀에 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="17905-134">Ownership of response groups remains with the original pool unless or until you explicitly reassign ownership by using the –OverwriteOwner parameter with the **Import-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="17905-135">또한 동일한 FQDN을 사용 하는지 여부에 관계 없이 복구 중에 풀을 다시 구성한 경우에는-OverwriteOwner 매개 변수를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17905-135">You also need to use the –OverwriteOwner parameter if you rebuilt the pool during the recovery (that is, the Response Group database is empty), whether or not you use the same FQDN.</span></span> <span data-ttu-id="17905-136">풀을 다시 작성하지 않은 경우에는 -OverwriteOwner 매개 변수를 사용하지 않아도 되지만, 응답 그룹을 기본 풀로 다시 가져올 때마다 이 매개 변수를 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17905-136">You do not need to use the –OverwriteOwner parameter if you did not rebuild the pool, but it is permissible to use this parameter whenever you import response groups back to the primary pool.</span></span>



</div>

<span data-ttu-id="17905-137">풀 당 응용 프로그램 수준 응답 그룹 구성 설정 집합을 하나만 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17905-137">You can define only one set of application-level Response Group configuration settings per pool.</span></span> <span data-ttu-id="17905-138">이러한 설정에는 기본 통화 대기음 구성, 기본 통화 대기음 오디오 파일, 에이전트 되걸기 유예 기간, 통화 컨텍스트 구성 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17905-138">These settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="17905-139">이러한 구성 설정을 보려면 **Get-CsRgsConfiguration** cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="17905-139">To view these configuration settings, run the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="17905-140">**Export-csrgsconfiguration** cmdlet에 대 한 자세한 내용은 [get-export-csrgsconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="17905-140">For details about the **Get-CsRgsConfiguration** cmdlet, see [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).</span></span>

<span data-ttu-id="17905-141">-ReplaceExistingSettings 매개 변수를 포함해 **Import-CsRgsConfiguration** cmdlet을 사용하여 풀 간에 이러한 응용 프로그램 수준 설정을 전송할 수는 있지만 이렇게 하면 대상 풀의 설정이 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="17905-141">You can transfer these application-level settings from one pool to another by using the **Import-CsRgsConfiguration** cmdlet with the –ReplaceExistingSettings parameter, but doing so overrides the settings in the destination pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="17905-p112">다른 풀로 설정을 전송하는 작업과 관련된 이 제약 조건은 응용 프로그램 수준 설정 및 기본 통화 대기음 오디오 파일에만 해당됩니다. 에이전트 그룹, 큐, 워크플로, 업무 시간 및 휴일 집합에는 해당 제약 조건이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="17905-p112">This constraint about transferring settings to another pool is true only for the application-level settings and the default music-on-hold audio file. It does not apply to agent groups, queues, workflows, business hours, and holiday sets.</span></span>



</div>

<span data-ttu-id="17905-p113">재해 중에 백업 풀의 응용 프로그램 수준 설정을 바꾸지 않으려는 경우 기본 풀을 복구할 수 없으면 기본 풀의 응용 프로그램 수준 설정이 손실됩니다. 복구 중에 새 풀을 만들어 기본 풀을 대체해야 하는 경우(같은 FQDN 또는 다른 FQDN 사용)에는 원본 응용 프로그램 수준 설정을 복구할 수 없습니다. 이 경우 이러한 설정을 사용하여 새 풀을 구성하고 통화 대기음 오디오 파일을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17905-p113">If you don't want to replace the application-level settings in the backup pool during a disaster and the primary pool can't be recovered, the application-level settings from the primary pool will be lost. If you need to create a new pool to replace the primary pool during recovery, either with the same FQDN or with a different FQDN, you can't recover the original application-level settings. In this case, you need to configure the new pool with these settings and include the music-on-hold audio file.</span></span>

<span data-ttu-id="17905-147">**Import-CsRgsConfiguration** cmdlet을 사용하여 재해 중에 응용 프로그램 수준 설정을 기본 풀에서 백업 풀로 전송하기로 결정하는 경우, 기본 풀에서 백업 풀로 설정을 전송한 것과 같은 방법으로 복구 중에 설정을 백업 풀에서 새 풀로 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17905-147">If you decide to use the **Import-CsRgsConfiguration** cmdlet to transfer application-level settings from the primary pool to the backup pool during a disaster, you can then transfer the settings from the backup pool to the new pool during recovery in the same way that you transferred them from the primary pool to the backup pool.</span></span>

<span data-ttu-id="17905-148">아래 표에는 응답 그룹 복구 시 수행하는 단계가 간략하게 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17905-148">The following table is an overview of the steps involved in recovering response groups.</span></span>

<span data-ttu-id="17905-149">이러한 단계를 수행 하는 방법에 대 한 자세한 내용은 [Lync Server 2013의 응답 그룹 재해 복구 절차](lync-server-2013-response-group-disaster-recovery-procedures.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="17905-149">For details about performing these steps, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span>

### <a name="response-group-disaster-recovery-steps"></a><span data-ttu-id="17905-150">응답 그룹 재해 복구 단계</span><span class="sxs-lookup"><span data-stu-id="17905-150">Response Group Disaster Recovery Steps</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="17905-151">단계</span><span class="sxs-lookup"><span data-stu-id="17905-151">Phase</span></span></th>
<th><span data-ttu-id="17905-152">단계</span><span class="sxs-lookup"><span data-stu-id="17905-152">Steps</span></span></th>
<th><span data-ttu-id="17905-153">필수 그룹 및 역할</span><span class="sxs-lookup"><span data-stu-id="17905-153">Required groups and roles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17905-154">중단 전</span><span class="sxs-lookup"><span data-stu-id="17905-154">Before outage</span></span></p></td>
<td><p><span data-ttu-id="17905-155">루틴을 사용 하 여 <strong>export-csrgsconfiguration</strong> cmdlet을 실행 하 여 응답 그룹 응용 프로그램이 배포 되는 모든 프런트 엔드 풀에 있는 모든 응답 그룹 구성의 백업을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="17905-155">On a routine basis, run the <strong>Export-CsRgsConfiguration</strong> cmdlet to create backups of all Response Group configurations in all Front End pools where Response Group application is deployed.</span></span></p></td>
<td><p><span data-ttu-id="17905-156">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="17905-156">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="17905-157">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="17905-157">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17905-158">중단 상태</span><span class="sxs-lookup"><span data-stu-id="17905-158">During outage</span></span></p></td>
<td><p><span data-ttu-id="17905-159"><strong>Export-csrgsconfiguration</strong> cmdlet을 실행 하 여 백업 된 Lync Server 응답 그룹 서비스 구성을 기본 풀에서 백업 풀로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="17905-159">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the backed up Lync Server Response Group service configuration from the primary pool to the backup pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="17905-160">백업 풀의 응용 프로그램 수준 응답 그룹 설정을 기본 풀의 설정으로 바꾸려면 – ReplaceExistingSettings 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="17905-160">Use the –ReplaceExistingSettings parameter if you want to replace application-level Response Group settings in the backup pool with the settings from the primary pool.</span></span> <span data-ttu-id="17905-161">응용 프로그램 수준 설정을 기본 풀에서 백업 풀로 전송하지 않는 경우 기본 풀을 복구할 수 없으면 기본 풀의 설정이 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="17905-161">If you do not transfer the application-level settings from the primary pool to the backup pool, and the primary pool can't be recovered, you will lose the settings from the primary pool.</span></span>


</div></td>
<td><p><span data-ttu-id="17905-162">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="17905-162">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="17905-163">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="17905-163">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17905-164">가져오기 후</span><span class="sxs-lookup"><span data-stu-id="17905-164">After importing</span></span></p></td>
<td><p><span data-ttu-id="17905-165">-ShowAll 매개 변수 (모든 응답 그룹 표시) 또는-Owner 매개 변수 (가져온 응답 그룹만 표시)를 사용 하 여 응답 그룹 cmdlet을 실행 하 여 모든 응답 그룹 구성을 백업 풀로 가져왔는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="17905-165">Run Response Group cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were imported to the backup pool.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="17905-166">-ShowAll 매개 변수 또는 -Owner 매개 변수를 사용하지 않으면 백업 풀로 가져온 응답 그룹이 cmdlet에서 반환하는 결과에 나열되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="17905-166">If you do not use either the –ShowAll parameter or the –Owner parameter, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>


</div>
<p><span data-ttu-id="17905-167">다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="17905-167">Run the following cmdlets:</span></span></p>
<ul>
<li><p><span data-ttu-id="17905-168"><strong>Get-csrgsworkflow</strong></span><span class="sxs-lookup"><span data-stu-id="17905-168"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="17905-169"><strong>Get-csrgsqueue</strong></span><span class="sxs-lookup"><span data-stu-id="17905-169"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="17905-170"><strong>Get-csrgsagentgroup</strong></span><span class="sxs-lookup"><span data-stu-id="17905-170"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="17905-171"><strong>Get-csrgshoursofbusiness</strong></span><span class="sxs-lookup"><span data-stu-id="17905-171"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="17905-172"><strong>New-csrgsholidayset</strong></span><span class="sxs-lookup"><span data-stu-id="17905-172"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="17905-173">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="17905-173">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="17905-174">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="17905-174">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17905-175">장애 조치(failover) 후</span><span class="sxs-lookup"><span data-stu-id="17905-175">After failover</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="17905-176">백업 풀로 가져온 응답 그룹에 대해 테스트 통화를 수행하여 통화가 올바르게 처리되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="17905-176">Place a test call to a response group that was imported to the backup pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="17905-177">모든 공식 에이전트가 백업 풀에서 공식 그룹에 다시 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17905-177">All formal agents must sign in again to their formal groups on backup pool.</span></span></p></li>
<li><p><span data-ttu-id="17905-178">구성 변경 내용을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="17905-178">Manage configuration changes:</span></span></p>
<p><span data-ttu-id="17905-179">백업 풀의 응답 그룹은 백업 풀로 가져온 것이든 백업 풀이 소유한 것이든 중단 상태에서 일반적인 방법으로 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17905-179">Response groups in the backup pool, whether imported to the backup pool or owned by the backup pool, can be modified as usual during the outage.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="17905-180">Lync Server 관리 셸을 사용 하 여 백업 풀로 가져온 응답 그룹을 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17905-180">You must use Lync Server Management Shell to manage the response groups that you imported to the backup pool.</span></span> <span data-ttu-id="17905-181">Lync Server 제어판을 사용 하 여 이러한 응답 그룹은 백업 풀에 있을 때 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="17905-181">You cannot use Lync Server Control Panel to manage these response groups while they are in the backup pool.</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="17905-182">해당 없음</span><span class="sxs-lookup"><span data-stu-id="17905-182">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17905-183">복구 후/장애 복구(failback) 전</span><span class="sxs-lookup"><span data-stu-id="17905-183">After recovery, before failback</span></span></p></td>
<td><p><span data-ttu-id="17905-184">-Source 매개 변수를 백업 풀로, -Owner 매개 변수를 기본 풀로 지정하여 <strong>Export-CsRgsConfiguration</strong> cmdlet을 실행해 백업 풀에서 기본 풀이 소유한 응답 그룹을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="17905-184">Run the <strong>Export-CsRgsConfiguration</strong> cmdlet specifying the -Source parameter as the backup pool and the –Owner parameter as the primary pool to export the response groups owned by the primary pool from the backup pool.</span></span></p></td>
<td><p><span data-ttu-id="17905-185">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="17905-185">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="17905-186">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="17905-186">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17905-187">장애 복구(failback) 후</span><span class="sxs-lookup"><span data-stu-id="17905-187">After failback</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="17905-188"><strong>Import-CsRgsConfiguration</strong> cmdlet을 실행하여 응답 그룹을 기본 풀로 다시 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="17905-188">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the response groups back to the primary pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="17905-p116">기본 풀을 복구할 수 없어 새 풀을 배포해 기본 풀을 대체하는 경우에는 -ReplaceExistingSettings 매개 변수를 사용하여 응용 프로그램 수준 설정을 백업 풀에서 새 풀로 전송합니다. 백업 풀에서 설정을 전송하지 않으면 새 풀에서는 기본 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="17905-p116">If the primary pool can't be recovered and you deploy a new pool to replace it, use the –ReplaceExistingSettings parameter to transfer the application-level settings from the backup pool to the new pool. If you do not transfer the settings from the backup pool, the new pool will use the default settings.</span></span>


</div></li>
<li><p><span data-ttu-id="17905-191">-ShowAll 매개 변수(모든 응답 그룹 표시) 또는 -Owner 매개 변수(가져온 응답 그룹만 표시)를 포함해 다음 cmdlet을 실행하여 모든 응답 그룹 구성을 기본 풀로 올바르게 다시 가져왔는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="17905-191">Run the following cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were successfully imported back to the primary pool:</span></span></p>
<ul>
<li><p><span data-ttu-id="17905-192"><strong>Get-csrgsworkflow</strong></span><span class="sxs-lookup"><span data-stu-id="17905-192"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="17905-193"><strong>Get-csrgsqueue</strong></span><span class="sxs-lookup"><span data-stu-id="17905-193"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="17905-194"><strong>Get-csrgsagentgroup</strong></span><span class="sxs-lookup"><span data-stu-id="17905-194"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="17905-195"><strong>Get-csrgshoursofbusiness</strong></span><span class="sxs-lookup"><span data-stu-id="17905-195"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="17905-196"><strong>New-csrgsholidayset</strong></span><span class="sxs-lookup"><span data-stu-id="17905-196"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="17905-197">기본 풀로 다시 가져온 응답 그룹에 대해 테스트 통화를 수행하여 통화가 올바르게 처리되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="17905-197">Place a test call to a response group that was imported back to the primary pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="17905-198">원하는 경우 백업 풀에서 -RemoveExportedConfiguration 매개 변수를 포함하여 <strong>Export-CsRgsConfiguration</strong> cmdlet을 실행해 기본 풀이 소유한 응답 그룹을 백업 풀에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="17905-198">Optionally, run the <strong>Export-CsRgsConfiguration</strong> cmdlet on the backup pool with the –RemoveExportedConfiguration parameter to remove the response groups owned by the primary pool from the backup pool.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="17905-199">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="17905-199">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="17905-200">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="17905-200">CsResponseGroupAdministrator</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

