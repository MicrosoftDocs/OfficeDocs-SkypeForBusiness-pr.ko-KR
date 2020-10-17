---
title: 'Lync Server 2013: 백업 서비스를 사용 하 여 전화 회의 내용 복원'
description: 'Lync Server 2013: 백업 서비스를 사용 하 여 전화 회의 내용을 복원 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring conference contents using the Backup Service
ms:assetid: 3e0f18ec-7319-4c07-a59b-2938e7787bc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688030(v=OCS.15)
ms:contentKeyID: 49733620
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3a0037af711948c008e74c5444373ed995f0e6e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555184"
---
# <a name="restoring-conference-contents-using-the-backup-service-in-lync-server-2013"></a>Lync Server 2013에서 백업 서비스를 사용 하 여 전화 회의 내용 복원

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

프런트 엔드 풀의 파일 저장소에 저장된 회의 정보가 사용할 수 없는 상태가 되면 풀에 있는 사용자가 자신의 회의 데이터를 보유할 수 있도록 이 정보를 복원해야 합니다. 회의 데이터가 손실된 프런트 엔드 풀이 다른 프런트 엔드 풀과 쌍으로 연결된 경우 백업 서비스를 사용하여 데이터를 복원할 수 있습니다.

또한 전체 풀이 실패한 경우에도 이 작업을 수행해야 하며 해당 사용자를 백업 풀로 장애 조치(failover)해야 합니다. 이러한 사용자를 원래 풀로 다시 장애 조치(failover)한 경우 이 절차에 따라 해당 회의 콘텐츠를 다시 원래 풀에도 복사해야 합니다.

Pool1이 Pool2와 쌍으로 연결되었고 Pool1의 회의 데이터가 손실되었다고 가정해보십시오. 다음 cmdlet을 사용 하 여 백업 서비스를 호출 하 여 콘텐츠를 복원할 수 있습니다.

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

회의 콘텐츠를 복원할 때는 크기에 따라 시간이 오래 걸릴 수 있습니다. 다음 cmdlet을 사용해서 프로세스 상태를 확인할 수 있습니다.

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

이 cmdlet이 데이터 회의 모듈에 대해 정상 상태 값을 반환하면 처리가 완료된 것입니다.

</div>

<span> </span>

</div>

</div>

</div>

