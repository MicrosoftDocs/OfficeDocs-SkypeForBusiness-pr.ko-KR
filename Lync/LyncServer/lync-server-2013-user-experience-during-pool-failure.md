---
title: Lync Server 2013 풀 오류 발생 시 사용자 환경
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User experience during pool failure
ms:assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205184(v=OCS.15)
ms:contentKeyID: 48185166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd2d6733f2db3a988f604554df55a25f866f5099
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530195"
---
# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a>Lync Server 2013에서 풀 오류 시 사용자 환경

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-03_

풀이 장애 조치(failover)되는 경우 영향을 받는 풀의 모든 사용자는 로그아웃된 후 백업 풀에 로그인됩니다. 백업 풀에 로그인된 사용자는 잠시 동안 복구 모드에 있을 수 있습니다. 복구 모드에서는 사용자가 연락처 추가와 같이 Lync Server에 대 한 영구 변경을 수행 하는 작업을 수행할 수 없습니다. 장애 조치가 완료된 후에 모든 사용자는 백업 풀에서 모든 서비스를 받을 수 있습니다.

풀에 장애가 발생할 때 사용자가 참여 중인 세션은 모두 중단되며 사용자는 장애 조치 후에 이러한 세션을 다시 설정해야 세션을 계속할 수 있습니다.

사용자는 장애 조치 또는 장애 복구 후에 홈으로 복원되지 않습니다. 장애가 발생한 풀에 속한 사용자는 일시적으로 백업 풀에서 서비스를 받게 됩니다. 홈 풀이 복원되면 관리자가 이러한 사용자를 장애 복구하여 원래 홈 풀에서 서비스를 받도록 할 수 있습니다.

참고 Lync 2013에서 위치 정보 서버 데이터베이스는 백업 풀로 복제 되지 않습니다. 관리자는 LIS 데이터베이스를 백업하여 장애 조치 후 백업 풀에서 LIS 데이터베이스를 복원하는 데 최신 백업 복사본을 사용하는 것이 좋습니다.

<div>

## <a name="user-experience-during-failover"></a>장애 조치 시 사용자 경험

장애가 발생한 풀에 있던 사용자는 로그아웃됩니다. 사용자가 참가하고 있던 피어 투 피어 세션은 종료되며 사용자가 구성한 회의도 마찬가지입니다. 등록자 복구 타이머가 만료되거나 관리자가 장애 조치 절차를 시작할 때까지(먼저 도래하는 것) 다시 로그인할 수 없습니다. 사용자가 다시 로그인할 때는 백업 풀에 로그인하게 됩니다. 장애 조치가 완료되기 전에 로그인할 경우 장애 조치가 완료될 때까지 복구 모드에 있게 됩니다. 완료 후에 비로소 사용자는 새 세션을 설정하거나 이전 세션을 다시 설정할 수 있습니다.

</div>

<div>

## <a name="user-experience-during-failback"></a>장애 복구 시 사용자 경험

영향을 받은 사용자가 백업 풀에 로그온해 있는 동안 풀 장애 복구가 이루어질 수 있으며, 사용자는 장애 복구 동안 로그온 및 작동 상태로 유지됩니다. 장애 복구 프로세스가 완료되는 데는 몇 분 정도 걸립니다.  참고로 20,000명의 사용자가 있는 풀의 경우 최대 60분이 소요될 수 있습니다.

다음 표에는 장애 복구 중 및 후에 Lync 2013 클라이언트나 Microsoft Lync 2010 클라이언트의 사용자가 영향을 받는 방법에 대 한 자세한 내용이 나와 있고, 다른 풀의 사용자가 장애가 발생 한 풀에서 사용자를 보고 상호 작용 하는 방법에 대 한 자세한 내용을 확인할 수 있습니다. Microsoft Office Communicator 2007 R2 클라이언트를 사용 하는 사용자는 프런트 엔드 풀이 완전히 장애 복구 될 때까지 로그인 할 수 없습니다.

*영향을 받는 사용자*라는 용어는 홈 풀에서 장애 조치되어 백업 풀에서 서비스를 받고 있는 사용자를 가리킵니다. 정의에 따라, 원래 백업 풀에 배치된 사용자는 영향을 받는 사용자가 아닙니다.

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a>장애 복구 시 풀에 있는 영향을 받는 사용자의 사용자 경험

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>사용자 상태 또는 작업</th>
<th>장애 복구 시</th>
<th>장애 복구 완료 후</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>이미 로그인된 사용자의 사용자 상태</p></td>
<td><p>사용자는 로그인된 상태로 유지되며 백업 풀에 연결되어 있습니다. 특정 시점에 사용자는 로그아웃되었다가 다시 원래 홈 풀로 로그인되어 복구 모드에 있게 됩니다.</p></td>
<td><p>사용자는 로그인된 상태로 유지되며 일반 모드로 전환됩니다.</p></td>
</tr>
<tr class="even">
<td><p>새 사용자 로그인</p></td>
<td><p>사용자는 홈 풀에 복구 모드로 로그인할 수 있습니다.</p></td>
<td><p>사용자는 원래 홈 풀에 일반 모드로 로그인할 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>영향을 받는 사용자가 구성한 진행 중인 회의</p></td>
<td><p>모든 형식의 회의가 종료됩니다. 다시 참가 단추가 나타나지만 영향을 받는 사용자가 복구 모드에 있는 동안에는 아무 사용자도 다시 참가할 수 없습니다.</p></td>
<td><p>모든 형식의 회의가 다시 작동합니다. 모든 참가자는 클릭하여 회의에 다시 참가해야 합니다.</p></td>
</tr>
<tr class="even">
<td><p>영향을 받지 않는 사용자가 구성한 진행 중인 회의</p></td>
<td><p>회의가 계속되며 영향을 받는 사용자가 회의에서 유지될 수 있습니다. 영향을 받는 사용자는 복구 모드에서 할 수 있는 작업으로 제한됩니다.</p></td>
<td><p>회의가 계속되며 영향을 받는 사용자가 회의에서 유지될 수 있습니다. 사용자가 복구 모드에서 전환되면 모든 형식이 작동합니다.</p></td>
</tr>
<tr class="odd">
<td><p>모임 예약 또는 예약된 모임 수정, 임시 회의 만들기</p></td>
<td><p>사용자가 복구 모드에 있는 동안 불가능</p></td>
<td><p>모든 형식에서 가능</p></td>
</tr>
<tr class="even">
<td><p>같은 풀에 있는 다른 사용자가 현재 상태 확인</p></td>
<td><p>사용자가 백업 풀에 로그인되어 복구 모드에 있는 동안에는 현재 상태를 알 수 없습니다.</p></td>
<td><p>사용자가 설정한 마지막 현재 상태 설정이 표시되고 이제 현재 상태 변경 내용이 반영됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>대화 상대 목록 및 주소록 서비스 사용 가능성</p></td>
<td><p>사용 불가</p></td>
<td><p>사용할 수 있음</p></td>
</tr>
<tr class="even">
<td><p>모든 피어 투 피어 세션 및 형식</p></td>
<td><p>사용할 수 있음</p></td>
<td><p>사용할 수 있음</p></td>
</tr>
</tbody>
</table>


### <a name="user-experience-for-a-user-homed-in-an-unaffected-pool-during-failback-of-another-pool"></a>다른 풀의 장애 복구 시 영향을 받지 않는 풀에 배치된 사용자의 사용자 경험

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>사용자 작업</th>
<th>장애 복구 시</th>
<th>장애 복구 완료 후</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>영향을 받는 사용자의 현재 상태 보기</p></td>
<td><p>영향을 받는 사용자가 설정한 마지막 현재 상태가 표시됩니다.</p></td>
<td><p>작동. 영향을 받지 않는 사용자는 영향을 받는 사용자가 수행한 업데이트를 볼 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>영향을 받는 사용자가 구성한 진행 중인 회의</p></td>
<td><p>모든 형식의 회의가 종료됩니다.</p></td>
<td><p>모든 형식의 회의가 다시 작동합니다. 모든 참가자는 클릭하여 회의에 다시 참가해야 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>영향을 받지 않는 사용자가 구성한 진행 중인 회의</p></td>
<td><p>회의가 계속되며 영향을 받는 사용자가 회의에서 유지되고 모든 형식이 작동합니다.</p></td>
<td><p>회의가 계속되며 영향을 받는 사용자가 회의에서 유지되고 모든 형식이 작동합니다.</p></td>
</tr>
<tr class="even">
<td><p>모든 피어 투 피어 세션 및 형식</p></td>
<td><p>사용할 수 있음</p></td>
<td><p>사용할 수 있음</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

