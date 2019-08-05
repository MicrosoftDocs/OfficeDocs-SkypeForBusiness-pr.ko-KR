---
title: 백업 서비스 구성 및 모니터링
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 비즈니스용 Skype 서버 관리 셸 명령을 사용 하 여 백업 서비스를 구성 하 고 모니터링할 수 있습니다.
ms.openlocfilehash: 2170f58fcc60a648788934048f3d0e6bbfac9c77
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197481"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a><span data-ttu-id="48c65-103">비즈니스용 Skype 서버에서 백업 서비스 구성 및 모니터링</span><span class="sxs-lookup"><span data-stu-id="48c65-103">Configuring and monitoring the Backup Service in Skype for Business Server</span></span>

<span data-ttu-id="48c65-104">다음 비즈니스용 Skype Server Management Shell 명령을 사용 하 여 백업 서비스를 구성 하 고 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48c65-104">You can use the following Skype for Business Server Management Shell commands to configure and monitor the Backup Service.</span></span> <span data-ttu-id="48c65-105">프런트 엔드 풀의 파일 저장소에 저장 된 회의 정보를 복원 하려면 아래 [백업 서비스를 사용 하 여 컨퍼런스 콘텐츠 복원을](#restore-conference-contents-using-the-backup-service)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="48c65-105">To restore conference information stored in the file store of a Front End pool, see [Restore conference contents using the Backup Service](#restore-conference-contents-using-the-backup-service), below.</span></span>

> [!NOTE]  
> <span data-ttu-id="48c65-106">RTCUniversalServerAdmins 그룹은 기본적으로 **Get-CsBackupServiceStatus** 를 실행할 수 있는 권한이 있는 유일한 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="48c65-106">The RTCUniversalServerAdmins group is the only group that has permissions to run **Get-CsBackupServiceStatus** by default.</span></span> <span data-ttu-id="48c65-107">이 cmdlet을 사용 하려면이 그룹의 구성원으로 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="48c65-107">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="48c65-108">또는 **Set-CsBackupServiceConfiguration** cmdlet을 사용 하 여 다른 그룹 (예: csadministrator)에이 명령에 대 한 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48c65-108">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the **Set-CsBackupServiceConfiguration** cmdlet.</span></span>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="48c65-109">백업 서비스 구성을 보려면 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="48c65-109">To see the Backup Service configuration</span></span>

<span data-ttu-id="48c65-110">다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="48c65-110">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="48c65-111">SyncInterval의 기본값은 2 분입니다.</span><span class="sxs-lookup"><span data-stu-id="48c65-111">The default for SyncInterval is two minutes.</span></span>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="48c65-112">백업 서비스 동기화 간격을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="48c65-112">To set the Backup Service sync interval</span></span>

<span data-ttu-id="48c65-113">다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="48c65-113">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="48c65-114">예를 들어 다음은 간격을 3 분으로 설정 하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="48c65-114">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> <span data-ttu-id="48c65-115">이 cmdlet을 사용 하 여 백업 서비스의 기본 동기화 간격을 변경할 수 있지만, 동기화 간격이 백업 서비스 성능 및 RPO (복구 시점 목표)에 큰 영향을 주므로 반드시 필요한 경우가 아니면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48c65-115">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="48c65-116">특정 풀에 대 한 백업 서비스 상태를 가져오려면</span><span class="sxs-lookup"><span data-stu-id="48c65-116">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="48c65-117">다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="48c65-117">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> <span data-ttu-id="48c65-118">백업 서비스 동기화 상태는 풀 (P1)에서 해당 백업 풀 (P2)로 unidirectionally 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48c65-118">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="48c65-119">P1에서 P2 까지의 동기화 상태가 P2 ~ P1과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48c65-119">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="48c65-120">P1에서 P2의 경우 P1의 모든 변경 내용이 동기화 간격 내에 P2로 완전히 복제 되는 경우 백업 서비스가 "안정 된" 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48c65-120">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="48c65-121">P1에서 P2와 동기화 할 변경 내용이 더 이상 없으면 "final" 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48c65-121">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="48c65-122">두 상태 모두 cmdlet이 실행 될 때 백업 서비스의 스냅숏을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="48c65-122">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="48c65-123">이는 반환 되는 상태가 나중에 그대로 유지 된다는 것을 의미 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="48c65-123">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="48c65-124">특히, "최종" 상태는 P1이 cmdlet을 실행 한 후 변경 내용을 생성 하지 않는 경우에만 계속 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48c65-124">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="48c65-125">이는 P1이 **CsPoolfailover** 실행 논리의 일부로 읽기 전용 모드로 설정 된 후에 P1을 P2로 실패 하는 경우에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48c65-125">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the **Invoke-CsPoolfailover** execution logic.</span></span>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="48c65-126">특정 풀의 백업 관계에 대 한 정보를 가져오려면</span><span class="sxs-lookup"><span data-stu-id="48c65-126">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="48c65-127">다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="48c65-127">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="48c65-128">백업 서비스 동기화를 적용 하려면</span><span class="sxs-lookup"><span data-stu-id="48c65-128">To force a Backup Service sync</span></span>

<span data-ttu-id="48c65-129">다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="48c65-129">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a><span data-ttu-id="48c65-130">백업 서비스를 사용 하 여 컨퍼런스 콘텐츠 복원</span><span class="sxs-lookup"><span data-stu-id="48c65-130">Restore conference contents using the Backup Service</span></span> 

<span data-ttu-id="48c65-131">프런트 엔드 풀의 파일 저장소에 저장 된 회의 정보를 사용할 수 없게 되 면이 정보를 복원 하 여 해당 그룹에 속한 사용자가 회의 데이터를 유지 하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48c65-131">If the conference information stored in the file store of a Front End pool becomes unavailable, you must restore this information so that users homed on the pool retain their conference data.</span></span> <span data-ttu-id="48c65-132">회의 데이터가 손실 된 프런트 엔드 풀이 다른 프런트 엔드 풀과 쌍을 이루는 경우 백업 서비스를 사용 하 여 데이터를 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48c65-132">If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="48c65-133">전체 풀이 실패 하 고 해당 사용자를 백업 풀로 장애 조치 해야 하는 경우에도이 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48c65-133">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool.</span></span> <span data-ttu-id="48c65-134">이러한 사용자가 원래 풀로 장애 복구 되는 경우이 절차를 사용 하 여 회의 콘텐츠를 원래 풀로 다시 복사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48c65-134">When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="48c65-135">Pool1가 Pool2와 쌍을 이루고 있고 Pool1의 컨퍼런스 데이터가 손실 된다고 가정 하세요.</span><span class="sxs-lookup"><span data-stu-id="48c65-135">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="48c65-136">다음 cmdlet을 사용 하 여 백업 서비스를 호출 하 여 콘텐츠를 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48c65-136">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="48c65-137">회의 콘텐츠는 크기에 따라 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48c65-137">Restoring the conference contents may take some time, depending on their size.</span></span> <span data-ttu-id="48c65-138">다음 cmdlet을 사용 하 여 프로세스 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48c65-138">You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="48c65-139">이 cmdlet은 데이터 컨퍼런스 모듈에 대 한 안정 된 상태 값을 반환 하는 경우에 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48c65-139">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>
