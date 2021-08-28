---
title: 2019년 응답 그룹 서비스 RGS(비즈니스용 Skype 서버) 데이터 백업
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
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: 2019년 RGS(응답 그룹 서비스) 데이터를 백업하는 방법을 비즈니스용 Skype 서버 대해 자세히 알아보습니다.
ms.openlocfilehash: 7e3e4116a281584da7afc1807fe58e79d2528183
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58581162"
---
# <a name="back-up-response-group-service-rgs-data"></a>RGS(응답 그룹 서비스 데이터 백업)

2019년 7월 비즈니스용 Skype 서버 누적 업데이트를 통해 RGS 데이터를 표준 백업의 일부로 포함할 수 있습니다.

## <a name="rgs-data-replication"></a>RGS 데이터 복제

RGS 데이터 복제 기능을 사용하려는 경우 다음 단계를 따르세요.

1. 페어링된 풀의 모든 프런트 엔드(FES)에 7월 누적 업데이트를 설치합니다.
1. 페어링된 풀의 두 구성원 모두에 RGS 데이터베이스를 설치합니다.
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. 두 풀 모두에서 다음 cmdlet을 실행하여 RGSBackupService에서 데이터를 선택할 수 있도록 기존 RGS 데이터를 백업 테이블에 복제합니다.
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. RGSBackupService를 사용하도록 설정(RGSBackupService를 전역적으로 사용하도록 설정). 이 매개 변수를 true로 설정하면 RGSBackupService가 페어링된 풀에서 RGS 데이터 동기화를 시작합니다(두 풀 모두 CU1 필요). 시작될 때까지 몇 분 정도 기다립니다. 처음에는 RGS BackupService 상태가 NotInitialized가 됩니다.
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. BackupServiceStatus를 확인:
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. 풀 전체에서 DataReplication을 확인하기 위해 다음 cmdlet을 사용(이러한 cmdlet은 소유자 풀 데이터만 표시)
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. 소유자 풀 RGS 데이터 및 해당 백업 데이터를 확인:
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. 워크플로를 오디오 호출하여 워크플로 기능을 검증합니다.
1. RGS 소유자 풀을 장애 조치(failover)합니다.
1. 워크플로를 오디오 호출하여 워크플로 기능을 검증합니다.
1. 풀을 장애 조치(failback)합니다.
1. 원본 풀에서 RGS 데이터를 업데이트하고 다른 장애 조치(failover)를 수행하여 변경 내용이 백업 풀에 반영되어 있는지 확인할 수 있습니다. RGS는 장애 조치(failover) 전에 작동하지 않을 때와 같은 방식으로 행동해야 합니다.

> [!TIP]
> 이러한 단계는 대량의 데이터에 대해 수행하고 장애 조치(failover) 및 장애 조치(failback)를 자주 수행하는 것이 좋습니다. 이 CU 업데이트 후에 만들어진 모든 새 RGS도 복제해야 합니다.

## <a name="rgs-cmdlets"></a>RGS cmdlet

- BackupServiceStatus를 확인(내보내기 상태는 최종 또는 정수 상태)입니다. 가져오기 상태는 보통 상태입니다. RGSBackupservice를 사용하도록 설정해야 합니다.
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- 백업 풀에서 RGS 데이터를 완전히 동기화(백업 풀의 전체 RGS 데이터를 동기화합니다.)
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- 백업 풀에서 RGS 파일스토어를 완전히 동기화하려면(백업 풀의 전체 RGS 데이터를 동기화합니다.)
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- 백업 풀에서 RGS 델타 데이터를 동기화(RGS에 한해 백업 풀의 델타 데이터를 동기화합니다.)
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- RGS를 포함하여 모든 모듈 데이터를 동기화하는 경우:
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- RGSBackupService를 사용하지 않도록 설정(RGSBackupService를 전역적으로 사용하지 않도록 설정)합니다. 이 매개 변수를 true로 설정하면 페어링된 모든 풀에서 RGSBackupService를 사용할 수 없습니다.
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`
