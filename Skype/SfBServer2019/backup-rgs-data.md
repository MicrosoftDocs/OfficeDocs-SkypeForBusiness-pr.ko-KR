---
title: 비즈니스용 Skype 응답 그룹 서비스(RGS) 데이터 백업
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 비즈니스용 Skype 서버 2019에서 응답 그룹 서비스(RGS) 데이터를 백업하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: f9c62953dcb859be2aa34bdee84ca76e3303d738
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824072"
---
# <a name="back-up-response-group-service-rgs-data"></a><span data-ttu-id="bad8e-103">RGS(응답 그룹 서비스) 백업</span><span class="sxs-lookup"><span data-stu-id="bad8e-103">Back up Response Group Service (RGS) data</span></span>

<span data-ttu-id="bad8e-104">비즈니스용 Skype 서버 2019 7월 누적 업데이트에서는 표준 백업의 일부로 RGS 데이터를 포함할 수 있는 기능을 포함했습니다.</span><span class="sxs-lookup"><span data-stu-id="bad8e-104">With the Skype for Business Server 2019 July cumulative update, we’ve included the ability to include RGS data as part of the standard backup.</span></span>

## <a name="rgs-data-replication"></a><span data-ttu-id="bad8e-105">RGS 데이터 복제</span><span class="sxs-lookup"><span data-stu-id="bad8e-105">RGS data replication</span></span>

<span data-ttu-id="bad8e-106">RGS 데이터 복제 기능을 사용하려는 경우 아래 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="bad8e-106">To try RGS data replication functionality, please follow the steps below:</span></span>

1. <span data-ttu-id="bad8e-107">페어링된 풀의 모든 프런트 엔드(FES)에 7월 누적 업데이트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="bad8e-107">Install the July cumulative update on all front-ends (FEs) of your paired pool.</span></span>
1. <span data-ttu-id="bad8e-108">페어링된 풀의 두 구성원 모두에 RGS 데이터베이스를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="bad8e-108">Install the RGS database on both members of the paired pool:</span></span>
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. <span data-ttu-id="bad8e-109">두 풀에서 다음 cmdlet을 실행하여 기존 RGS 데이터를 백업 테이블에 복제하여 RGSBackupService에서 데이터를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bad8e-109">Run the following cmdlet on both pools to replicate existing RGS Data to the backup tables so that the data can be picked up by RGSBackupService:</span></span>
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. <span data-ttu-id="bad8e-110">RGSBackupService를 사용하도록 설정(전역적으로 RGSBackupService를 사용하도록 설정)</span><span class="sxs-lookup"><span data-stu-id="bad8e-110">Enable RGSBackupService (This will enable RGSBackupService globally.</span></span> <span data-ttu-id="bad8e-111">이 매개 변수를 true로 설정하면 RGSBackupService가 페어링된 풀에서 RGS 데이터 동기화를 시작합니다(두 풀 모두 CU1이 필요).</span><span class="sxs-lookup"><span data-stu-id="bad8e-111">If this parameter is set to true , RGSBackupService will start syncing RGS data on paired pools (both pools needs to be CU1).</span></span> <span data-ttu-id="bad8e-112">시작될 때까지 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="bad8e-112">Wait for a few minutes to get it started.</span></span> <span data-ttu-id="bad8e-113">처음에는 RGS BackupService 상태가 NotInitialized가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bad8e-113">Initially, RGS BackupService status will be NotInitialized.):</span></span>
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. <span data-ttu-id="bad8e-114">BackupServiceStatus를 확인:</span><span class="sxs-lookup"><span data-stu-id="bad8e-114">To check BackupServiceStatus:</span></span>
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. <span data-ttu-id="bad8e-115">풀 간 DataReplication을 확인하기 위해 다음 cmdlet을 사용(이러한 cmdlet에는 소유자 풀 데이터만 표시됨)</span><span class="sxs-lookup"><span data-stu-id="bad8e-115">To check DataReplication across pools, use these cmdlets (These cmdlets show only owner pool data):</span></span>
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. <span data-ttu-id="bad8e-116">소유자 풀 RGS 데이터 및 해당 백업 데이터를 확인:</span><span class="sxs-lookup"><span data-stu-id="bad8e-116">To check Owner pool RGS data and its backup data:</span></span>
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. <span data-ttu-id="bad8e-117">워크플로를 오디오 호출하여 워크플로 기능을 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="bad8e-117">Verify workflow functionality by making an audio call to Workflow.</span></span>
1. <span data-ttu-id="bad8e-118">RGS 소유자 풀 장애 조치(failover)를 합니다.</span><span class="sxs-lookup"><span data-stu-id="bad8e-118">Failover your RGS Owner pool.</span></span>
1. <span data-ttu-id="bad8e-119">워크플로를 오디오 호출하여 워크플로 기능을 검증합니다.</span><span class="sxs-lookup"><span data-stu-id="bad8e-119">Verify workflow functionality by making an audio call to Workflow.</span></span>
1. <span data-ttu-id="bad8e-120">풀 장애 조치(failback)</span><span class="sxs-lookup"><span data-stu-id="bad8e-120">Failback the pool.</span></span>
1. <span data-ttu-id="bad8e-121">원본 풀에서 RGS 데이터를 업데이트하고 다른 장애 조치(failover)를 수행하여 변경 내용이 백업 풀에 반영되어 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bad8e-121">Update RGS Data on source pool and perform another failover to check that changes are reflected on backup pool.</span></span> <span data-ttu-id="bad8e-122">RGS는 장애 조치(failover) 전에 작동하지 않을 때와 동일한 방식으로 행동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bad8e-122">RGS should behave in same way as it was behaving before failover.</span></span>

> [!TIP]
> <span data-ttu-id="bad8e-123">이러한 단계는 대량의 데이터에 대해 수행하고 장애 조치(failover) 및 장애 조치(failback)를 자주 수행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bad8e-123">It is recommended you perform these steps on a bulk of data and do frequent failover and failbacks.</span></span> <span data-ttu-id="bad8e-124">이 CU 업데이트 후에 만들어진 모든 새 RGS도 복제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bad8e-124">Any new RGS created after this CU update should also be replicated.</span></span>

## <a name="rgs-cmdlets"></a><span data-ttu-id="bad8e-125">RGS cmdlet</span><span class="sxs-lookup"><span data-stu-id="bad8e-125">RGS cmdlets</span></span>

- <span data-ttu-id="bad8e-126">BackupServiceStatus를 확인(내보내기 상태는 최종 상태 또는 정적 상태)입니다.</span><span class="sxs-lookup"><span data-stu-id="bad8e-126">To check BackupServiceStatus (The export status should be in the Final or Steady state.</span></span> <span data-ttu-id="bad8e-127">가져오기 상태는 보통 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="bad8e-127">The import status should be in the Normal state.</span></span> <span data-ttu-id="bad8e-128">RGSBackupservice를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bad8e-128">RGSBackupservice should be enabled.):</span></span>
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- <span data-ttu-id="bad8e-129">백업 풀에서 RGS 데이터를 완전히 동기화(백업 풀의 전체 RGS 데이터를 동기화합니다.)</span><span class="sxs-lookup"><span data-stu-id="bad8e-129">To Fully Sync RGS Data on the backup pool (This will sync the full RGS data on the backup pool.):</span></span>
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- <span data-ttu-id="bad8e-130">백업 풀에서 RGS 파일스토어를 완전히 동기화하려면(백업 풀의 전체 RGS 데이터를 동기화합니다.)</span><span class="sxs-lookup"><span data-stu-id="bad8e-130">To Fully Sync the RGS filestore on the backup pool (This will sync the full RGS data on the backup pool.):</span></span>
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- <span data-ttu-id="bad8e-131">백업 풀에서 RGS 델타 데이터를 동기화(RGS 전용으로 백업 풀의 델타 데이터를 동기화합니다.)</span><span class="sxs-lookup"><span data-stu-id="bad8e-131">To Sync RGS delta data on the backup pool (This will sync delta data on backup pool for RGS only.):</span></span>
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- <span data-ttu-id="bad8e-132">RGS를 포함하여 모든 모듈 데이터를 동기화하는 경우:</span><span class="sxs-lookup"><span data-stu-id="bad8e-132">To sync all module data including RGS:</span></span>
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- <span data-ttu-id="bad8e-133">RGSBackupService를 사용하지 않도록 설정(전역적으로 RGSBackupService를 사용하지 않도록 설정)</span><span class="sxs-lookup"><span data-stu-id="bad8e-133">To disable RGSBackupService (This will disable RGSBackupService globally.</span></span> <span data-ttu-id="bad8e-134">이 매개 변수를 true로 설정하면 페어링된 모든 풀에서 RGSBackupService를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bad8e-134">If this parameter is set to true , RGSBackupService will be disabled on all paired pools.):</span></span>
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`
