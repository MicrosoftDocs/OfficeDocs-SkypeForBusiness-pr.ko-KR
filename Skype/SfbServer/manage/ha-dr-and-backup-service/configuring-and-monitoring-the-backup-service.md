---
title: 백업 서비스 구성 및 모니터링
ms.reviewer: ''
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 관리 셸 비즈니스용 Skype 서버 사용하여 백업 서비스를 구성 및 모니터링할 수 있습니다.
ms.openlocfilehash: 0881d40ca639edf825b0af104981ceddcab6e87a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60832022"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a>백업 서비스 구성 및 비즈니스용 Skype 서버

다음 관리 셸 비즈니스용 Skype 서버 사용하여 백업 서비스를 구성하고 모니터링할 수 있습니다. 프런트 엔드 풀의 파일 저장소에 저장된 회의 정보를 복원하기 위해 아래 백업 서비스를 사용하여 회의 콘텐츠 [복원을](#restore-conference-contents-using-the-backup-service)참조하세요.

> [!NOTE]  
> RTCUniversalServerAdmins 그룹은 기본적으로 **Get-CsBackupServiceStatus** 를 실행할 수 있는 사용 권한을 보유한 유일한 그룹입니다. 이 cmdlet을 사용하려면 이 그룹의 구성원으로 로그온해야 합니다. 또는 **Set-CsBackupServiceConfiguration** cmdlet을 사용하여 이 명령에 대한 액세스 권한을 다른 그룹(예: CSAdministrator)에 부여할 수 있습니다.

## <a name="to-see-the-backup-service-configuration"></a>백업 서비스 구성을 보려면

다음 cmdlet을 실행합니다.<br/><br/>Get-CsBackupServiceConfiguration

SyncInterval의 기본값은 2분입니다.

## <a name="to-set-the-backup-service-sync-interval"></a>백업 서비스의 동기화 간격을 설정하려면

다음 cmdlet을 실행합니다.<br/><br/>Set-CsBackupServiceConfiguration -SyncInterval 간격

예를 들어 다음 명령은 간격을 3분으로 설정합니다.<br/><br/>Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> 이 cmdlet을 사용하여 백업 서비스의 기본 동기화 간격을 변경할 수 있지만, 절대적으로 필요한 경우를 제외하고는 변경해서는 안 됩니다. 동기화 간격은 백업 서비스 성능과 RPO(복구 지점 목표)에 상당한 영향을 미치기 때문입니다.

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>특정 풀의 백업 서비스 상태를 가져오려면

다음 cmdlet을 실행합니다.<br/><br/>Get-CsBackupServiceStatus -PoolFqdn \<pool-FQDN>

> [!NOTE]  
> 백업 서비스의 동기화 상태는 풀(P1)에서 백업 풀(P2)로 단방향으로 정의됩니다. P1에서 P2로의 동기화 상태는 P2에서 P1로의 동기화 상태와 다를 수 있습니다. P1에서 P2로의 경우 P1의 모든 변경 내용이 동기화 간격 내에 P2로 완전히 복제되면 백업 서비스는 "안정" 상태가 됩니다. P1에서 P2로 동기화할 변경 내용이 더 이상 없는 경우 "최종" 상태가 됩니다. 두 상태 모두 cmdlet이 실행되는 시점의 백업 서비스 스냅숏을 나타냅니다. 반환된 상태가 이후로도 계속 지속됨을 의미하지는 않습니다. 특히 "최종" 상태는 cmdlet이 실행된 이후 P1에 변경 내용이 전혀 생성되지 않은 경우에만 유지됩니다. 이는 **Invoke-CsPoolfailover** 실행 논리의 일부로 읽기 전용 모드로 전환된 후 P1에서 P2로 장애 조치되는 경우에도 마찬가지입니다.

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>특정 풀의 백업 관계 정보를 가져오려면

다음 cmdlet을 실행합니다.<br/><br/>Get-CsPoolBackupRelationship -PoolFQDN \<poolFQDN>

## <a name="to-force-a-backup-service-sync"></a>백업 서비스의 동기화를 강제로 실행하려면

다음 cmdlet을 실행합니다.<br/><br/>Invoke-CsBackupServiceSync -PoolFqdn \<poolFqdn> [-BackupModule {All| PresenceFocus| DataConf| CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a>백업 서비스를 사용하여 회의 콘텐츠 복원 

프런트 엔드 풀의 파일 저장소에 저장된 회의 정보를 사용할 수 없게 되는 경우 풀에 있는 사용자가 자신의 회의 데이터를 유지하도록 이 정보를 복원해야 합니다. 회의 데이터가 손실된 프런트 엔드 풀이 다른 프런트 엔드 풀과 페어링된 경우 백업 서비스를 사용하여 데이터를 복원할 수 있습니다.

또한 전체 풀이 실패한 경우에도 이 작업을 수행해야 하며 해당 사용자를 백업 풀로 장애 조치(failover)해야 합니다. 이러한 사용자를 원래 풀로 다시 장애 조치(failover)한 경우 이 절차에 따라 해당 회의 콘텐츠를 다시 원래 풀에도 복사해야 합니다.

Pool1이 Pool2와 쌍으로 연결되었고 Pool1의 회의 데이터가 손실되었다고 가정해보십시오. 다음 cmdlet을 사용하여 백업 서비스를 호출하여 콘텐츠를 복원할 수 있습니다.<br/><br/>Invoke-CsBackupServiceSync -PoolFqdn \<Pool2 FQDN> -BackupModule ConfServices.DataConf

회의 콘텐츠를 복원할 때는 크기에 따라 시간이 오래 걸릴 수 있습니다. 다음 cmdlet을 사용해서 프로세스 상태를 확인할 수 있습니다.<br/><br/>Get-CsBackupServiceStatus -PoolFqdn \<Pool2 FQDN> -BackupModule ConfServices.DataConf

이 cmdlet이 데이터 회의 모듈에 대해 정상 상태 값을 반환하면 처리가 완료된 것입니다.
