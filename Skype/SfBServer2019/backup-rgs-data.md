---
title: 비즈니스용 Skype Server 2019에서 RGS (응답 그룹 서비스) 데이터 백업
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 비즈니스용 Skype 서버 2019에서 RGS (응답 그룹 서비스) 데이터를 백업 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 0a37b4d4771a75513666597de5eb87dedcbcd0c7
ms.sourcegitcommit: 14700a4faab81a294ac794f25b26619a5ed242a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2019
ms.locfileid: "36198008"
---
# <a name="back-up-response-group-service-rgs-data"></a><span data-ttu-id="83708-103">RGS (응답 그룹 서비스) 데이터 백업</span><span class="sxs-lookup"><span data-stu-id="83708-103">Back up Response Group Service (RGS) data</span></span>

<span data-ttu-id="83708-104">비즈니스용 Skype 서버 2019 7 월 누적 업데이트를 사용 하는 경우, 표준 백업의 일부로 RGS 데이터를 포함 하는 기능이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83708-104">With the Skype for Business Server 2019 July cumulative update, we’ve included the ability to include RGS data as part of the standard backup.</span></span>

## <a name="rgs-data-replication"></a><span data-ttu-id="83708-105">RGS 데이터 복제</span><span class="sxs-lookup"><span data-stu-id="83708-105">RGS data replication</span></span>

<span data-ttu-id="83708-106">RGS 데이터 복제 기능을 시도 하려면 아래 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="83708-106">To try RGS data replication functionality, please follow the steps below:</span></span>

1. <span data-ttu-id="83708-107">교차 하는 모든 풀의 모든 프런트 엔드 (FEs)에 7 월 누적 업데이트를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="83708-107">Install the July cumulative update on all front-ends (FEs) of your paired pool.</span></span>
1. <span data-ttu-id="83708-108">다음 쌍으로 연결 된 풀의 두 구성원에 RGS 데이터베이스를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="83708-108">Install the RGS database on both members of the paired pool:</span></span>
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. <span data-ttu-id="83708-109">두 풀에서 다음 cmdlet을 실행 하 여 RGSBackupService에서 데이터를 선택할 수 있도록 기존 RGS 데이터를 백업 테이블로 복제 합니다.</span><span class="sxs-lookup"><span data-stu-id="83708-109">Run the following cmdlet on both pools to replicate existing RGS Data to the backup tables so that the data can be picked up by RGSBackupService:</span></span>
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. <span data-ttu-id="83708-110">RGSBackupService 사용 (이는 RGSBackupService 전역으로 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83708-110">Enable RGSBackupService (This will enable RGSBackupService globally.</span></span> <span data-ttu-id="83708-111">이 매개 변수를 true로 설정 하면 RGSBackupService가 페어링 된 풀에서 RGS 데이터 동기화를 시작 합니다 (두 풀을 CU1 해야 함).</span><span class="sxs-lookup"><span data-stu-id="83708-111">If this parameter is set to true , RGSBackupService will start syncing RGS data on paired pools (both pools needs to be CU1).</span></span> <span data-ttu-id="83708-112">몇 분 후에 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83708-112">Wait for a few minutes to get it started.</span></span> <span data-ttu-id="83708-113">처음에는 RGS BackupService 상태가 NotInitialized 됩니다.):</span><span class="sxs-lookup"><span data-stu-id="83708-113">Initially, RGS BackupService status will be NotInitialized.):</span></span>
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. <span data-ttu-id="83708-114">BackupServiceStatus를 확인 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="83708-114">To check BackupServiceStatus:</span></span>
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. <span data-ttu-id="83708-115">풀에서 DataReplication을 확인 하려면 다음 cmdlet을 사용 합니다 (이러한 cmdlet에는 소유자 풀 데이터만 표시).</span><span class="sxs-lookup"><span data-stu-id="83708-115">To check DataReplication across pools, use these cmdlets (These cmdlets show only owner pool data):</span></span>
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. <span data-ttu-id="83708-116">소유자 풀 RGS 데이터 및 해당 백업 데이터를 확인 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="83708-116">To check Owner pool RGS data and its backup data:</span></span>
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. <span data-ttu-id="83708-117">워크플로에 대 한 오디오 통화를 만들어 워크플로 기능을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="83708-117">Verify workflow functionality by making an audio call to Workflow.</span></span>
1. <span data-ttu-id="83708-118">RGS 소유자 풀을 장애 조치 (Failover) 합니다.</span><span class="sxs-lookup"><span data-stu-id="83708-118">Failover your RGS Owner pool.</span></span>
1. <span data-ttu-id="83708-119">워크플로에 대 한 오디오 통화를 만들어 워크플로 기능을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="83708-119">Verify workflow functionality by making an audio call to Workflow.</span></span>
1. <span data-ttu-id="83708-120">풀을 장애 복구 합니다.</span><span class="sxs-lookup"><span data-stu-id="83708-120">Failback the pool.</span></span>
1. <span data-ttu-id="83708-121">원본 풀의 RGS 데이터를 업데이트 하 고 다른 장애 조치를 수행 하 여 변경 내용이 백업 풀에 반영 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="83708-121">Update RGS Data on source pool and perform another failover to check that changes are reflected on backup pool.</span></span> <span data-ttu-id="83708-122">RGS는 장애 조치 전에 작동 하는 것과 같은 방식으로 동작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83708-122">RGS should behave in same way as it was behaving before failover.</span></span>

> [!TIP]
> <span data-ttu-id="83708-123">대량 데이터에 대해 이러한 단계를 수행 하 고 자주 장애 조치 및 failbacks 백업 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="83708-123">It is recommended you perform these steps on a bulk of data and do frequent failover and failbacks.</span></span> <span data-ttu-id="83708-124">이 CU (업데이트 후 만들어진 모든 새 RGS도 복제 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83708-124">Any new RGS created after this CU update should also be replicated.</span></span>

## <a name="rgs-cmdlets"></a><span data-ttu-id="83708-125">RGS cmdlet</span><span class="sxs-lookup"><span data-stu-id="83708-125">RGS cmdlets</span></span>

- <span data-ttu-id="83708-126">BackupServiceStatus를 확인 하려면 (내보내기 상태는 최종 또는 일정 한 상태 여야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="83708-126">To check BackupServiceStatus (The export status should be in the Final or Steady state.</span></span> <span data-ttu-id="83708-127">가져오기 상태가 정상 상태 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83708-127">The import status should be in the Normal state.</span></span> <span data-ttu-id="83708-128">RGSBackupservice을 사용 하도록 설정 해야 합니다.):</span><span class="sxs-lookup"><span data-stu-id="83708-128">RGSBackupservice should be enabled.):</span></span>
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- <span data-ttu-id="83708-129">백업 풀의 RGS 데이터를 완전히 동기화 하려면 (백업 풀의 전체 RGS 데이터를 동기화 합니다.):</span><span class="sxs-lookup"><span data-stu-id="83708-129">To Fully Sync RGS Data on the backup pool (This will sync the full RGS data on the backup pool.):</span></span>
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- <span data-ttu-id="83708-130">백업 풀에서 RGS 파일 저장소를 완전히 동기화 하려면 (백업 풀의 전체 RGS 데이터를 동기화 합니다.):</span><span class="sxs-lookup"><span data-stu-id="83708-130">To Fully Sync the RGS filestore on the backup pool (This will sync the full RGS data on the backup pool.):</span></span>
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- <span data-ttu-id="83708-131">백업 풀에서 RGS 델타 데이터를 동기화 하려면 (이는 RGS에 대해서만 백업 풀의 델타 데이터를 동기화 합니다.):</span><span class="sxs-lookup"><span data-stu-id="83708-131">To Sync RGS delta data on the backup pool (This will sync delta data on backup pool for RGS only.):</span></span>
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- <span data-ttu-id="83708-132">RGS를 포함 하 여 모든 모듈 데이터를 동기화 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="83708-132">To sync all module data including RGS:</span></span>
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- <span data-ttu-id="83708-133">RGSBackupService를 사용 하지 않도록 설정 하려면 (RGSBackupService 전역으로 비활성화 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="83708-133">To disable RGSBackupService (This will disable RGSBackupService globally.</span></span> <span data-ttu-id="83708-134">이 매개 변수를 true로 설정 하면 모든 페어링 된 풀에서 RGSBackupService를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83708-134">If this parameter is set to true , RGSBackupService will be disabled on all paired pools.):</span></span>
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`
