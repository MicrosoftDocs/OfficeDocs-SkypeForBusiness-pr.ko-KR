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
ms.openlocfilehash: 3181a266e5792d190186e9f09b2cab5852156cbe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755268"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a>Lync Server 2013에서 백업 수행 및 모니터링

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-05-15_

비즈니스 우선 순위는 조직의 백업 및 복원 요구 사항에 대 한 사양을 구동 해야 합니다. 서버와 데이터의 백업을 수행 하는 것은 재해 계획의 첫 번째 줄입니다.

Lync Server 2013 서비스 또는 서버 역할을 실행 하는 컴퓨터는 현재 토폴로지, 현재 구성 설정 및 현재 정책의 복사본을 가져야만 해당 역할에서 작동할 수 있습니다. Lync 서버는이 정보를 필요로 하는 각 컴퓨터에이 정보가 전달 되도록 하는 역할을 합니다.

중앙 관리 저장소 업그레이드 중에는 Lync Server 토폴로지, 구성 설정 및 정책을 백업 하 고 복원 하는 데 **내보내기-csconfiguration** 및 **가져오기-csconfiguration** cmdlet이 사용 됩니다. **수출-CsConfiguration** cmdlet을 사용 하면 데이터를로 내보낼 수 있습니다. ZIP 파일. 그런 다음 **가져오기-CsConfiguration** cmdlet을 사용 하 여이를 읽을 수 있습니다. ZIP 파일을 만들고 토폴로지, 구성 설정 및 정책을 중앙 관리 저장소에 복원 합니다. 그 이후에는 Lync Server의 복제 서비스에서 복원 된 정보를 Lync Server services를 실행 하는 다른 컴퓨터로 복제 합니다.

구성 데이터를 내보내고 가져오는 기능은 경계 네트워크 (예: Edge 서버)에 있는 컴퓨터의 초기 구성 중에도 사용 됩니다. 경계 네트워크에서 컴퓨터를 구성할 때는 먼저 CsConfiguration cmdlet을 사용 하 여 수동 복제를 수행 해야 합니다. **내보내기-CsConfiguration** 을 사용 하 여 구성 데이터를 내보낸 다음을 복사 해야 합니다. 주변 네트워크의 컴퓨터에 ZIP 파일을 추가할 수 있습니다. 그런 다음 **가져오기-CsConfiguration** 및 localstore 매개 변수를 사용 하 여 데이터를 가져올 수 있습니다. 한 번만 수행 하면 됩니다. 그 이후에는 복제가 자동으로 수행 됩니다.

이 cmdlet을 실행할 수 있는 사람: 기본적으로 다음 그룹의 구성원은 **수출-CsConfiguration** cmdlet을 로컬로 실행할 권한이 있습니다. RTCUniversalServerAdmins. 이 cmdlet이 할당 된 모든 RBAC 역할 목록 (직접 만든 사용자 지정 RBAC 역할 포함)을 반환 하려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

모든 SQL 2012 백 엔드 데이터베이스는 [sql 모범 사례](http://go.microsoft.com/fwlink/p/?linkid=290716)에 따라 백업 해야 합니다.

Lync Server 2013 인프라에 대 한 재난 복구 계획의 정기적인 테스트는 프로덕션 환경을 최대한 비슷하게 모방 하는 랩 환경에서 수행 해야 합니다. 재해 복구 테스트에 대 한 자세한 내용은 월 작업을 참조 하세요.

복원 지점과 복구 시점 목표에 따라 백업 빈도를 조정할 수 있습니다. 가장 좋은 방법은 하루 종일 정기적으로 스냅숏을 작성 하는 것입니다. 일반적으로 24 시간 마다 전체 백업을 수행 해야 합니다.

<div>

## <a name="see-also"></a>참고 항목


[가져오기-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[수출-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[SQL 모범 사례](http://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

