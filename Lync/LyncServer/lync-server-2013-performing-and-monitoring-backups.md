---
title: 'Lync Server 2013: 백업 수행 및 모니터링'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing and monitoring backups
ms:assetid: 2df415d4-0f37-460e-99ff-4035a9a2f445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720912(v=OCS.15)
ms:contentKeyID: 63969595
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d44fe94ab8e02551f8d33d95248c6cede63a6974
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215674"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a>Lync Server 2013에서 백업 수행 및 모니터링

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-05-15_

비즈니스 우선 순위에 따라 조직의 백업 및 복원 요구 사항 사양이 구동 됩니다. 재해 계획의 첫 번째 방어선은 서버 및 데이터 백업을 수행 하는 것입니다.

Lync Server 2013 서비스 또는 서버 역할을 실행 하는 컴퓨터에는 현재 토폴로지, 현재 구성 설정 및 현재 정책이 포함 되어 있어야 해당 역할에서 작동 될 수 있습니다. Lync Server는이 정보가 필요한 각 컴퓨터에이 정보를 전달 하는 일을 담당 합니다.

중앙 관리 저장소 업그레이드 중에는 **수출-csconfiguration** 및 **Import-csconfiguration** cmdlet을 사용 하 여 Lync Server 토폴로지, 구성 설정 및 정책을 백업 및 복원 합니다. **수출-CsConfiguration** cmdlet을 사용 하 여 데이터를로 내보낼 수 있습니다. ZIP 파일 그런 다음 **가져오기-CsConfiguration** cmdlet을 사용 하 여 해당를 읽을 수 있습니다. ZIP 파일을 만들고 토폴로지, 구성 설정 및 정책을 중앙 관리 저장소로 복원 합니다. 그런 다음 Lync server의 복제 서비스가 Lync Server 서비스를 실행 하는 다른 컴퓨터에 복원 된 정보를 복제 합니다.

구성 데이터를 내보내고 가져오는 기능은 경계 네트워크 (예:에 지 서버)에 있는 컴퓨터의 초기 구성 중에도 사용 됩니다. 경계 네트워크에서 컴퓨터를 구성 하는 경우 먼저 CsConfiguration cmdlet을 사용 하 여 수동 복제를 수행 해야 합니다. 그런 다음 **export-CsConfiguration** 을 사용 하 여 구성 데이터를 내보낸 다음를 복사 해야 합니다. 주변 네트워크에 있는 컴퓨터에 ZIP 파일을 추가할 수 있습니다. 그런 후에는 **가져오기-CsConfiguration** 및 localstore 매개 변수를 사용 하 여 데이터를 가져올 수 있습니다. 이 작업은 한 번만 수행 하면 됩니다. 그러면 복제가 자동으로 수행 됩니다.

이 cmdlet을 실행할 수 있는 사용자: 기본적으로 RTCUniversalServerAdmins 그룹의 구성원은 **Export-CsConfiguration** cmdlet을 로컬로 실행할 수 있습니다. 이 cmdlet이 할당 된 모든 RBAC 역할의 목록을 반환 하려면 (직접 만든 사용자 지정 RBAC 역할 포함) Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

모든 SQL 2012 백 엔드 데이터베이스는 [sql 모범 사례](https://go.microsoft.com/fwlink/p/?linkid=290716)당 백업 해야 합니다.

Lync Server 2013 인프라에 대 한 재해 복구 계획의 정기적인 테스트는 프로덕션 환경을 최대한 비슷하게 모방 하는 랩 환경에서 수행 해야 합니다. 재해 복구 테스트에 대 한 자세한 내용은 월별 작업을 참조 하세요.

복원 지점 및 복구 지점 목표를 기준으로 백업 빈도를 조정할 수 있습니다. 정기적으로 하루 종일 주기적으로 스냅숏을 정기적으로 수행 하는 것이 좋습니다. 일반적으로 24 시간 마다 전체 백업을 수행 해야 합니다.

<div>

## <a name="see-also"></a>참고 항목


[가져오기-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[수출-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[SQL 모범 사례](https://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

