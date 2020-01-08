---
title: 풀 실패 중 Lync Server 2013 사용자 환경
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User experience during pool failure
ms:assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205184(v=OCS.15)
ms:contentKeyID: 48185166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca33dc8f77ac697b7eea9cc89fee9aa401318566
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982902"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a>Lync Server 2013에서 풀 장애가 발생 한 사용자 환경

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-03_

풀이 장애 조치 되는 경우 영향을 받는 풀의 모든 사용자는 강제로 로그 아웃 한 다음 백업 풀에 로그인 합니다. 간단한 기간 동안에는 백업 풀에 로그인 하는 사용자가 복원 가능 모드일 수 있습니다. 복원 모드에서는 사용자가 Lync Server에서 영구 변경 (예: 연락처 추가)을 발생 시키는 작업을 수행할 수 없습니다. 장애 조치를 완료 한 후 모든 사용자가 백업 풀에서 모든 서비스를 받을 수 있습니다.

풀에 장애가 발생할 경우 사용자가 보유 한 모든 세션은 중단 되며 계속 하려면 장애 조치 (failover) 후에 해당 세션을 다시 설정 해야 합니다.

장애 조치 또는 장애 복구 시 사용자가 상주 하지 않습니다. 실패 한 풀에 속한 사용자는 백업 풀에서 일시적으로 서비스를 받습니다. 홈 풀이 복원 되 면 관리자는 해당 사용자가 원래 홈 풀에서 서비스를 받을 수 없게 됩니다.

참고 Lync 2013에서 위치 정보 서버 데이터베이스는 백업 풀로 복제 되지 않습니다. 모범 사례를 위해 관리자는 정기적으로 LIS 데이터베이스를 백업 하 고 최신 백업 복사본을 사용 하 여 장애 조치 후 백업 풀에 LIS 데이터베이스를 복원 해야 합니다.

<div>

## <a name="user-experience-during-failover"></a>장애 조치 중 사용자 환경

사용자가 실패 한 풀에 있으면 사용자가 로그 아웃 됩니다. 사용자가 참여 한 모든 피어 투 피어 세션은 해당 사용자가 구성한 컨퍼런스와 같이 종료 됩니다. 레지스트라 복원 타이머가 만료 되거나 관리자가 장애 조치 절차를 시작할 때까지 사용자는 다시 로그인 할 수 없습니다 (먼저 제공 됨). 사용자가 다시 로그인 하면 백업 풀에 로그인 됩니다. 장애 조치가 완료 되기 전에 로그인 하는 경우 장애 조치가 완료 될 때까지 복원 모드에 있게 됩니다. 그 다음에만 사용자가 새 세션을 설정 하거나 이전 세션을 다시 설정할 수 있습니다.

</div>

<div>

## <a name="user-experience-during-failback"></a>장애 복구 중 사용자 환경

풀 장애 복구는 영향을 받는 사용자가 백업 풀에 로그온 하는 동안 발생할 수 있으며, 장애 복구 중에 사용자가 로그인 하 여 작동 하는 것으로 유지 됩니다. 장애 복구 프로세스가 완료 되기까지 몇 분이 소요 됩니다.참조용으로 2만 사용자 풀에 대해 최대 60 분이 소요 될 것으로 예상 됩니다.

다음 표에서는 장애가 있는 사용자가 Lync 2013 클라이언트 또는 Microsoft Lync 2010 클라이언트를 사용 하는 방법에 대 한 자세한 정보를 보여 줍니다. 또한 다른 풀의 사용자가 장애 복구 되는 풀의 사용자를 보고 상호 작용 하는 방법을 설명 합니다. Microsoft Office Communicator 2007 R2 클라이언트가 있는 사용자는 프런트 엔드 풀이 완전히 장애 복구 될 때까지 로그인 할 수 없습니다.

*영향을 받는 사용자* 는 홈 풀에서 장애 조치를 수행한 사용자를 참조 하 고 백업 풀에서 서비스를 제공 합니다. 정의에 따라 백업 풀에서 원래 설정한 사용자는 영향을 받지 않습니다.

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a>장애 복구 시 풀의 영향을 받는 사용자에 대 한 사용자 환경

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>사용자 상태 또는 작업</th>
<th>장애 복구 중</th>
<th>장애 복구 완료 후</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>사용자의 사용자 상태가 이미 로그인 되어 있음</p></td>
<td><p>사용자가 로그인 되어 있고 백업 풀에 연결 되어 있습니다. 일부 시점에서는 사용자가 로그 아웃 하 고 원래 홈 풀 (복원 모드)에 다시 로그인 합니다.</p></td>
<td><p>사용자는 로그인 상태를 유지 하 고 일반 모드로 전환 합니다.</p></td>
</tr>
<tr class="even">
<td><p>새 사용자 로그인</p></td>
<td><p>사용자는 복원 모드에서 홈 풀에 로그인 할 수 있습니다.</p></td>
<td><p>사용자는 일반 모드에서 원래 홈 풀에 로그인 할 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>영향을 받는 사용자가 구성한 지속적인 회의</p></td>
<td><p>모든 컨퍼런스 형식을 종료 됩니다. 다시 참가 단추가 표시 되지만, 영향을 받는 사용자가 복원 모드에 있는 동안에는 사용자가 다시 참가할 수 없습니다.</p></td>
<td><p>이제 모든 형식을 작동 합니다. 모든 참가자가 회의에 다시 참가 하려면을 클릭 해야 합니다.</p></td>
</tr>
<tr class="even">
<td><p>영향을 받지 않는 사용자가 구성한 지속적인 컨퍼런스</p></td>
<td><p>회의가 계속 되며 영향을 받는 사용자는 회의에 남아 있을 수 있습니다. 영향을 받는 사용자는 복원 모드에서 수행할 수 있는 작업으로 제한 됩니다.</p></td>
<td><p>회의가 계속 되며, 사용자가 복원 모드를 종료 한 후에도 영향을 받는 사용자가 회의 및 모든 형식을 작업에 유지할 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>예약 된 모임 예약 또는 수정, 특별 컨퍼런스 만들기</p></td>
<td><p>사용자가 복원 모드에 있는 동안에는 불가능 합니다.</p></td>
<td><p>모든 형식을에서 사용할 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>같은 풀의 다른 사용자가 표시 한 상태</p></td>
<td><p>현재 상태를 알 수 없음 복원 모드 동안 사용자가 백업 풀에 로그인 합니다.</p></td>
<td><p>사용자가 설정한 마지막 현재 상태를 표시 하 고 현재 존재 변경 내용이 적용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>연락처 목록 및 주소록 서비스 사용 가능성</p></td>
<td><p>사용할 수 없음</p></td>
<td><p>공간이</p></td>
</tr>
<tr class="even">
<td><p>모든 피어 투 피어 세션 및 형식을</p></td>
<td><p>공간이</p></td>
<td><p>공간이</p></td>
</tr>
</tbody>
</table>


### <a name="user-experience-for-a-user-homed-in-an-unaffected-pool-during-failback-of-another-pool"></a>다른 풀의 장애 복구를 수행 하는 동안 영향을 받지 않는 풀에 속한 사용자의 사용자 환경

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>사용자 작업</th>
<th>장애 복구 중</th>
<th>장애 복구 완료 후</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>영향을 받는 사용자의 현재 상태 보기</p></td>
<td><p>영향을 받는 사용자가 설정한 마지막 현재 상태를 표시 합니다.</p></td>
<td><p>중. 영향을 받지 않는 사용자는 해당 사용자가 수행한 업데이트를 볼 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>영향을 받는 사용자가 구성한 지속적인 회의</p></td>
<td><p>모든 컨퍼런스 형식을 종료 됩니다.</p></td>
<td><p>이제 모든 형식을 작동 합니다. 모든 참가자가 회의에 다시 참가 하려면을 클릭 해야 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>영향을 받지 않는 사용자가 구성한 지속적인 컨퍼런스</p></td>
<td><p>회의가 계속 되 고, 영향을 받는 사용자가 회의 및 모든 형식을 작업에 유지할 수 있습니다.</p></td>
<td><p>회의가 계속 되 고, 영향을 받는 사용자가 회의 및 모든 형식을 작업에 유지할 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>모든 피어 투 피어 세션 및 형식을</p></td>
<td><p>공간이</p></td>
<td><p>공간이</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

