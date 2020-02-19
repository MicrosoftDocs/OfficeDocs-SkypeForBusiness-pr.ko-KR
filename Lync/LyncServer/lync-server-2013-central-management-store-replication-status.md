---
title: 'Lync Server 2013: 중앙 관리 저장소 복제 상태'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Central management store replication status
ms:assetid: f514f88d-986b-4e45-b79b-e04a7616c1fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720926(v=OCS.15)
ms:contentKeyID: 63969663
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb72b44cf53a33b3c0d7a79f6adda8870fe37254
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135355"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="central-management-store-replication-status-in-lync-server-2013"></a>Lync Server 2013의 중앙 관리 저장소 복제 상태

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2015-01-26_

관리자가 특정 종류의 Lync Server를 변경 하는 경우 (예: 관리자가 새 음성 정책을 만들거나 주소록 서버 구성 설정을 변경 하면 변경 내용이 중앙 관리 저장소에 기록 되는 경우) 그런 후에는 Lync Server 서비스 또는 서버 역할을 실행 하는 모든 컴퓨터에 변경 내용을 복제 해야 합니다.

데이터를 복제 하기 위해 마스터 복제기 (중앙 관리 서버에서 실행)에서는 변경 된 구성 데이터의 스냅숏을 만듭니다. 이 스냅숏의 복사본은 Lync Server 서비스 또는 서버 역할을 실행 하는 각 컴퓨터에 전송 됩니다. 이러한 컴퓨터에서 복제 에이전트는 스냅숏을 수신 하 고 변경 된 데이터를 업로드 합니다. 그런 다음 에이전트는 마스터 복제기에서 최신 복제 상태를 보고 하는 메시지를 보냅니다.

Get-csmanagementstorereplicationstatus cmdlet을 사용 하면 조직에 있는 모든 Lync Server 컴퓨터의 복제 상태를 확인할 수 있습니다.

이 cmdlet을 실행할 수 있는 사람은 누구 인가요? 기본적으로 다음 그룹의 구성원은 Get-csmanagementstorereplicationstatus cmdlet을 로컬로 실행할 수 있습니다 RTCUniversalUserAdmins, RTCUniversalServerAdmins를 사용 하도록 허가 됩니다.

이 cmdlet이 할당 된 모든 RBAC 역할 목록 (직접 만든 사용자 지정 RBAC 역할 포함)을 반환 하려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsManagementStoreReplicationStatus"}

<div>

## <a name="see-also"></a>참고 항목


[Get-csmanagementstorereplicationstatus](https://docs.microsoft.com/powershell/module/skype/Get-CsManagementStoreReplicationStatus)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

