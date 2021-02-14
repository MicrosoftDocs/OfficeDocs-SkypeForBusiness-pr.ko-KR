---
title: 백업 서비스 구성 및 모니터링
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 비즈니스용 Skype 서버 관리 셸 명령을 사용하여 백업 서비스를 구성하고 모니터링할 수 있습니다.
ms.openlocfilehash: d38c9d0b0261fb7e1da89b3422496d94307a791d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817198"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a><span data-ttu-id="ae57f-103">비즈니스용 Skype 서버에서 백업 서비스 구성 및 모니터링</span><span class="sxs-lookup"><span data-stu-id="ae57f-103">Configuring and monitoring the Backup Service in Skype for Business Server</span></span>

<span data-ttu-id="ae57f-104">다음 비즈니스용 Skype 서버 관리 셸 명령을 사용하여 백업 서비스를 구성하고 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae57f-104">You can use the following Skype for Business Server Management Shell commands to configure and monitor the Backup Service.</span></span> <span data-ttu-id="ae57f-105">프런트 엔드 풀의 파일 저장소에 저장된 회의 정보를 복원하는 경우 아래 백업 서비스를 사용하여 회의 콘텐츠 [복원을](#restore-conference-contents-using-the-backup-service)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ae57f-105">To restore conference information stored in the file store of a Front End pool, see [Restore conference contents using the Backup Service](#restore-conference-contents-using-the-backup-service), below.</span></span>

> [!NOTE]  
> <span data-ttu-id="ae57f-106">RTCUniversalServerAdmins 그룹은 기본적으로 **Get-CsBackupServiceStatus** 를 실행할 수 있는 사용 권한을 보유한 유일한 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="ae57f-106">The RTCUniversalServerAdmins group is the only group that has permissions to run **Get-CsBackupServiceStatus** by default.</span></span> <span data-ttu-id="ae57f-107">이 cmdlet을 사용하려면 이 그룹의 구성원으로 로그온해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae57f-107">To use this cmdlet, log on as a member of this group.</span></span> <span data-ttu-id="ae57f-108">또는 **Set-CsBackupServiceConfiguration** cmdlet을 사용하여 이 명령에 대한 액세스 권한을 다른 그룹(예: CSAdministrator)에 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae57f-108">Or, you can grant access to this command to other groups (for example, CSAdministrator) by using the **Set-CsBackupServiceConfiguration** cmdlet.</span></span>

## <a name="to-see-the-backup-service-configuration"></a><span data-ttu-id="ae57f-109">백업 서비스 구성을 보려면</span><span class="sxs-lookup"><span data-stu-id="ae57f-109">To see the Backup Service configuration</span></span>

<span data-ttu-id="ae57f-110">다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ae57f-110">Run the following cmdlet:</span></span>

    Get-CsBackupServiceConfiguration

<span data-ttu-id="ae57f-111">SyncInterval의 기본값은 2분입니다.</span><span class="sxs-lookup"><span data-stu-id="ae57f-111">The default for SyncInterval is two minutes.</span></span>

## <a name="to-set-the-backup-service-sync-interval"></a><span data-ttu-id="ae57f-112">백업 서비스의 동기화 간격을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="ae57f-112">To set the Backup Service sync interval</span></span>

<span data-ttu-id="ae57f-113">다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ae57f-113">Run the following cmdlet:</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval interval

<span data-ttu-id="ae57f-114">예를 들어 다음 명령은 간격을 3분으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ae57f-114">For example, the following sets the interval to three minutes.</span></span>

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> <span data-ttu-id="ae57f-115">이 cmdlet을 사용하여 백업 서비스의 기본 동기화 간격을 변경할 수 있지만, 절대적으로 필요한 경우를 제외하고는 변경해서는 안 됩니다. 동기화 간격은 백업 서비스 성능과 RPO(복구 지점 목표)에 상당한 영향을 미치기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="ae57f-115">Although you can use this cmdlet to change the default sync interval for the Backup Service, you should not do so unless it is absolutely necessary, as the sync interval has a great impact on the Backup Service performance and the recovery point objective (RPO).</span></span>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a><span data-ttu-id="ae57f-116">특정 풀의 백업 서비스 상태를 가져오려면</span><span class="sxs-lookup"><span data-stu-id="ae57f-116">To get the Backup Service status for a particular pool</span></span>

<span data-ttu-id="ae57f-117">다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ae57f-117">Run the following cmdlet:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> <span data-ttu-id="ae57f-118">백업 서비스의 동기화 상태는 풀(P1)에서 백업 풀(P2)로 단방향으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae57f-118">The Backup Service sync status is defined unidirectionally from a pool (P1) to its backup pool (P2).</span></span> <span data-ttu-id="ae57f-119">P1에서 P2로의 동기화 상태는 P2에서 P1로의 동기화 상태와 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae57f-119">The sync status from P1 to P2 can be different than the one from P2 to P1.</span></span> <span data-ttu-id="ae57f-120">P1에서 P2로의 경우 P1의 모든 변경 내용이 동기화 간격 내에 P2로 완전히 복제되면 백업 서비스는 "안정" 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae57f-120">For P1 to P2, Backup Service is in a “steady” state if all the changes made in P1 are completely replicated over to P2 within the sync interval.</span></span> <span data-ttu-id="ae57f-121">P1에서 P2로 동기화할 변경 내용이 더 이상 없는 경우 "최종" 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae57f-121">It is in the “final” state if there are no more changes to be synchronized from P1 to P2.</span></span> <span data-ttu-id="ae57f-122">두 상태 모두 cmdlet이 실행되는 시점의 백업 서비스 스냅숏을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ae57f-122">Both states indicate a snapshot of the Backup Service at the time the cmdlet is executed.</span></span> <span data-ttu-id="ae57f-123">반환된 상태가 이후로도 계속 지속됨을 의미하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae57f-123">It does not imply that the state returned will stay as is afterwards.</span></span> <span data-ttu-id="ae57f-124">특히 "최종" 상태는 cmdlet이 실행된 이후 P1에 변경 내용이 전혀 생성되지 않은 경우에만 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae57f-124">In particular, the “final” state will continue to hold only if P1 does not generate any changes after the cmdlet is executed.</span></span> <span data-ttu-id="ae57f-125">이는 **Invoke-CsPoolfailover** 실행 논리의 일부로 읽기 전용 모드로 전환된 후 P1에서 P2로 장애 조치되는 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="ae57f-125">This is true in the case of failing P1 over to P2 after P1 is placed into the read-only mode as part of the **Invoke-CsPoolfailover** execution logic.</span></span>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a><span data-ttu-id="ae57f-126">특정 풀의 백업 관계 정보를 가져오려면</span><span class="sxs-lookup"><span data-stu-id="ae57f-126">To get information about the backup relationship for a particular pool</span></span>

<span data-ttu-id="ae57f-127">다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ae57f-127">Run the following cmdlet:</span></span>

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a><span data-ttu-id="ae57f-128">백업 서비스의 동기화를 강제로 실행하려면</span><span class="sxs-lookup"><span data-stu-id="ae57f-128">To force a Backup Service sync</span></span>

<span data-ttu-id="ae57f-129">다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ae57f-129">Run the following cmdlet:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a><span data-ttu-id="ae57f-130">백업 서비스를 사용하여 회의 콘텐츠 복원</span><span class="sxs-lookup"><span data-stu-id="ae57f-130">Restore conference contents using the Backup Service</span></span> 

<span data-ttu-id="ae57f-131">프런트 엔드 풀의 파일 저장소에 저장된 회의 정보를 사용할 수 없는 경우 풀에 있는 사용자가 자신의 회의 데이터를 유지할 수 있도록 이 정보를 복원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae57f-131">If the conference information stored in the file store of a Front End pool becomes unavailable, you must restore this information so that users homed on the pool retain their conference data.</span></span> <span data-ttu-id="ae57f-132">회의 데이터가 손실된 프런트 엔드 풀이 다른 프런트 엔드 풀과 쌍으로 지정되는 경우 백업 서비스를 사용하여 데이터를 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae57f-132">If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="ae57f-p105">또한 전체 풀이 실패한 경우에도 이 작업을 수행해야 하며 해당 사용자를 백업 풀로 장애 조치(failover)해야 합니다. 이러한 사용자를 원래 풀로 다시 장애 조치(failover)한 경우 이 절차에 따라 해당 회의 콘텐츠를 다시 원래 풀에도 복사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae57f-p105">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool. When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="ae57f-135">Pool1이 Pool2와 쌍으로 연결되었고 Pool1의 회의 데이터가 손실되었다고 가정해보십시오.</span><span class="sxs-lookup"><span data-stu-id="ae57f-135">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="ae57f-136">다음 cmdlet을 사용하여 백업 서비스를 호출하여 콘텐츠를 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae57f-136">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="ae57f-p107">회의 콘텐츠를 복원할 때는 크기에 따라 시간이 오래 걸릴 수 있습니다. 다음 cmdlet을 사용해서 프로세스 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae57f-p107">Restoring the conference contents may take some time, depending on their size. You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="ae57f-139">이 cmdlet이 데이터 회의 모듈에 대해 정상 상태 값을 반환하면 처리가 완료된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ae57f-139">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>
