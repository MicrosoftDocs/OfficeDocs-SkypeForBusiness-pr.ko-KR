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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 비즈니스용 Skype 서버 2019에서 RGS (응답 그룹 서비스) 데이터를 백업 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: f9c62953dcb859be2aa34bdee84ca76e3303d738
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824072"
---
# <a name="back-up-response-group-service-rgs-data"></a>RGS (응답 그룹 서비스) 데이터 백업

비즈니스용 Skype 서버 2019 7 월 누적 업데이트를 사용 하는 경우, 표준 백업의 일부로 RGS 데이터를 포함 하는 기능이 포함 되어 있습니다.

## <a name="rgs-data-replication"></a>RGS 데이터 복제

RGS 데이터 복제 기능을 시도 하려면 아래 단계를 따르세요.

1. 교차 하는 모든 풀의 모든 프런트 엔드 (FEs)에 7 월 누적 업데이트를 설치 합니다.
1. 다음 쌍으로 연결 된 풀의 두 구성원에 RGS 데이터베이스를 설치 합니다.
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. 두 풀에서 다음 cmdlet을 실행 하 여 RGSBackupService에서 데이터를 선택할 수 있도록 기존 RGS 데이터를 백업 테이블로 복제 합니다.
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. RGSBackupService 사용 (이는 RGSBackupService 전역으로 활성화 됩니다. 이 매개 변수를 true로 설정 하면 RGSBackupService가 페어링 된 풀에서 RGS 데이터 동기화를 시작 합니다 (두 풀을 CU1 해야 함). 몇 분 후에 시작할 수 있습니다. 처음에는 RGS BackupService 상태가 NotInitialized 됩니다.):
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. BackupServiceStatus를 확인 하려면 다음을 수행 합니다.
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. 풀에서 DataReplication을 확인 하려면 다음 cmdlet을 사용 합니다 (이러한 cmdlet에는 소유자 풀 데이터만 표시).
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. 소유자 풀 RGS 데이터 및 해당 백업 데이터를 확인 하려면 다음을 수행 합니다.
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. 워크플로에 대 한 오디오 통화를 만들어 워크플로 기능을 확인 합니다.
1. RGS 소유자 풀을 장애 조치 (Failover) 합니다.
1. 워크플로에 대 한 오디오 통화를 만들어 워크플로 기능을 확인 합니다.
1. 풀을 장애 복구 합니다.
1. 원본 풀의 RGS 데이터를 업데이트 하 고 다른 장애 조치를 수행 하 여 변경 내용이 백업 풀에 반영 되는지 확인 합니다. RGS는 장애 조치 전에 작동 하는 것과 같은 방식으로 동작 해야 합니다.

> [!TIP]
> 대량 데이터에 대해 이러한 단계를 수행 하 고 자주 장애 조치 및 failbacks 백업 하는 것이 좋습니다. 이 CU (업데이트 후 만들어진 모든 새 RGS도 복제 되어야 합니다.

## <a name="rgs-cmdlets"></a>RGS cmdlet

- BackupServiceStatus를 확인 하려면 (내보내기 상태는 최종 또는 일정 한 상태 여야 합니다.) 가져오기 상태가 정상 상태 여야 합니다. RGSBackupservice을 사용 하도록 설정 해야 합니다.):
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- 백업 풀의 RGS 데이터를 완전히 동기화 하려면 (백업 풀의 전체 RGS 데이터를 동기화 합니다.):
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- 백업 풀에서 RGS 파일 저장소를 완전히 동기화 하려면 (백업 풀의 전체 RGS 데이터를 동기화 합니다.):
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- 백업 풀에서 RGS 델타 데이터를 동기화 하려면 (이는 RGS에 대해서만 백업 풀의 델타 데이터를 동기화 합니다.):
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- RGS를 포함 하 여 모든 모듈 데이터를 동기화 하려면 다음을 실행 합니다.
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- RGSBackupService를 사용 하지 않도록 설정 하려면 (RGSBackupService 전역으로 비활성화 됩니다.) 이 매개 변수를 true로 설정 하면 모든 페어링 된 풀에서 RGSBackupService를 사용할 수 없습니다.
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`
