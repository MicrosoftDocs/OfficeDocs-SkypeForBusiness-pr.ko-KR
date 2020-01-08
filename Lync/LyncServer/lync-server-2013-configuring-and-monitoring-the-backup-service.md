---
title: 'Lync Server 2013: 백업 서비스 구성 및 모니터링'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring and monitoring the Backup Service
ms:assetid: c608280e-a7d1-4ae0-a75c-da6b524752fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205252(v=OCS.15)
ms:contentKeyID: 48185365
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66a800014b3327e83426c9f758b7d5359c1ce6c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979352"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a>Lync Server 2013에서 백업 서비스 구성 및 모니터링

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

다음 Lync Server 관리 셸 명령을 사용 하 여 백업 서비스를 구성 하 고 모니터링할 수 있습니다.

<div>


> [!NOTE]  
> RTCUniversalServerAdmins 그룹은 기본적으로 <STRONG>Get-CsBackupServiceStatus</STRONG> 를 실행할 수 있는 권한이 있는 유일한 그룹입니다. 이 cmdlet을 사용 하려면이 그룹의 구성원으로 로그온 합니다. 또는 <STRONG>Set-CsBackupServiceConfiguration</STRONG> cmdlet을 사용 하 여 다른 그룹 (예: csadministrator)에이 명령에 대 한 액세스 권한을 부여할 수 있습니다.



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a>백업 서비스 구성을 보려면 다음을 참조 하세요.

다음 cmdlet을 실행 합니다.

    Get-CsBackupServiceConfiguration

SyncInterval의 기본값은 2 분입니다.

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a>백업 서비스 동기화 간격을 설정 하려면

다음 cmdlet을 실행 합니다.

    Set-CsBackupServiceConfiguration -SyncInterval interval

예를 들어 다음은 간격을 3 분으로 설정 하는 예제입니다.

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> 이 cmdlet을 사용 하 여 백업 서비스의 기본 동기화 간격을 변경할 수 있지만, 동기화 간격이 백업 서비스 성능 및 RPO (복구 시점 목표)에 큰 영향을 주므로 반드시 필요한 경우가 아니면 안 됩니다.



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>특정 풀에 대 한 백업 서비스 상태를 가져오려면

다음 cmdlet을 실행 합니다.

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> 백업 서비스 동기화 상태는 풀 (P1)에서 해당 백업 풀 (P2)로 unidirectionally 정의 됩니다. P1에서 P2 까지의 동기화 상태가 P2 ~ P1과 다를 수 있습니다. P1에서 P2의 경우 P1의 모든 변경 내용이 동기화 간격 내에 P2로 완전히 복제 되는 경우 백업 서비스가 "안정 된" 상태가 됩니다. P1에서 P2와 동기화 할 변경 내용이 더 이상 없으면 "final" 상태가 됩니다. 두 상태 모두 cmdlet이 실행 될 때 백업 서비스의 스냅숏을 나타냅니다. 이는 반환 되는 상태가 나중에 그대로 유지 된다는 것을 의미 하지는 않습니다. 특히, "최종" 상태는 P1이 cmdlet을 실행 한 후 변경 내용을 생성 하지 않는 경우에만 계속 유지 됩니다. 이는 P1이 <STRONG>CsPoolfailover</STRONG> 실행 논리의 일부로 읽기 전용 모드로 설정 된 후에 P1을 P2로 실패 하는 경우에 적용 됩니다.



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>특정 풀의 백업 관계에 대 한 정보를 가져오려면

다음 cmdlet을 실행 합니다.

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a>백업 서비스 동기화를 적용 하려면

다음 cmdlet을 실행 합니다.

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>

