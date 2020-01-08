---
title: Lync Server 2013 풀 오류 발생 시 응답 그룹 환경
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response group experience during pool failure
ms:assetid: 4e00fb38-64b1-4fd9-903d-7639177bc303
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204886(v=OCS.15)
ms:contentKeyID: 48184116
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90911bebc7c3e60847f5b3fcb8f69523697af0f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985287"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a>풀 오류 발생 시 Lync Server 2013의 응답 그룹 환경

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-30_

이 섹션에서는 응답 그룹 활동이 다음 단계에서 영향을 받는 방법에 대해 자세히 설명 합니다.

  - 기본 풀에서 작동 중지가 발생 하지만 장애 조치는 아직 시작 되지 않았습니다.

  - 서비스가 백업 풀로 장애 조치 되었습니다.

  - 서비스가 기본 풀로 장애 복구 됩니다.

<div>

## <a name="user-experience-when-outage-occurs"></a>중단 발생 시 사용자 환경

풀 또는 사이트 중단이 발생 하지만 관리자가 아직 장애 조치를 시작 하지 않은 경우 응답 그룹 활동은 다음 표에 설명 된 대로 처리 됩니다.

<div>


> [!NOTE]  
> 재해 복구 중에는 복구 중에 기본 풀 응답 그룹을 백업 풀로 가져왔는지 여부에 따라 호출이 다르게 작동 합니다. 다음 표에서는 재해 복구 모드 중에 주 풀 응답 그룹을 백업 풀로 가져왔는지 평균 응답 그룹을 참조 합니다.



</div>

### <a name="outage-occurs"></a>중단 발생

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>통화 유형 또는 사용자 작업</th>
<th>비활성 동안</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>에이전트에 연결 된 통화</p></td>
<td><ul>
<li><p>일반 통화는 연결 된 상태로 유지 됩니다.</p></li>
<li><p>익명 통화는 연결이 끊깁니다.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>아직 에이전트에 연결 되지 않은 진행 중인 통화</p></td>
<td><p>통화가 끊깁니다.</p></td>
</tr>
<tr class="odd">
<td><p>새로운 통화</p></td>
<td><ul>
<li><p>통화가 끊깁니다.</p></li>
<li><p>응답 그룹을 가져온 경우 백업 풀에 연결을 호출 하지만 기본 풀에 있는 에이전트는 연결할 수 없습니다.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>응답 그룹을 대신 하 여 에이전트 호출</p></td>
<td><p>이 단계에서는 기능을 사용할 수 없습니다.</p></td>
</tr>
<tr class="odd">
<td><p>에이전트 로그인 및 에이전트 정보</p></td>
<td><ul>
<li><p>주 풀 소유의 에이전트 그룹은 에이전트 콘솔에서 볼 수 있지만 에이전트는 로그인 할 수 없습니다.</p></li>
<li><p>에이전트 콘솔에서 백업 풀 소유의 에이전트 그룹을 볼 수 있으며, 에이전트는 로그인 할 수 있습니다.</p></li>
<li><p>가져온 에이전트 그룹은 에이전트 콘솔에 표시 되지 않습니다.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>응답 그룹 구성</p></td>
<td><ul>
<li><p>기본 풀에서 소유 하는 응답 그룹은 기본 풀의 백 엔드 데이터베이스 가용성에 따라 볼 수 있지만 수정할 수는 없습니다.</p></li>
<li><p>백업 풀 소유의 응답 그룹을 보고 수정할 수 있습니다.</p></li>
<li><p>가져온 응답 그룹은 Lync Server 제어판 또는 응답 그룹 구성 도구로 볼 수 없지만 Lync Server 관리 셸 cmdlet을 사용 하 여 구성할 수 있습니다.</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a>장애 조치 중 사용자 환경

관리자가 백업 풀로 장애 조치 (failover)를 호출 하면 다음 표에 설명 된 대로 응답 그룹 활동이 장애 조치 중에 처리 됩니다. 첫 번째 열은 수행할 수 있는 활동 유형을 설명 합니다. 중간 열에서는 백업 풀로 장애 조치 하는 데 걸리는 짧은 시간 동안 각 활동이 처리 되는 방식을 설명 합니다. 마지막 열은 장애 조치 프로세스가 완료 되 고 백업 풀이 기본 풀에 대해 발생 한 후 해당 기간 동안 활동이 처리 되는 방식을 설명 합니다.

<div>


> [!NOTE]  
> 재해 복구 중에는 복구 중에 기본 풀 응답 그룹을 백업 풀로 가져왔는지 여부에 따라 호출이 다르게 작동 합니다. 다음 표에서는 재해 복구 모드 중에 주 풀 응답 그룹을 백업 풀로 가져왔는지 평균 응답 그룹을 참조 합니다.



</div>

### <a name="failover-is-initiated"></a>장애 조치 시작 됨

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>통화 유형 또는 사용자 작업</th>
<th>장애 조치 동안</th>
<th>장애 조치 완료 후</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>에이전트에 연결 된 통화</p></td>
<td><ul>
<li><p>일반 통화는 연결 된 상태로 유지 됩니다.</p></li>
<li><p>익명 통화는 연결이 끊깁니다.</p></li>
</ul></td>
<td><ul>
<li><p>일반 통화는 연결 된 상태로 유지 됩니다.</p></li>
<li><p>가져온 응답 그룹의 경우 백업 풀에 도달한 익명 호출은 연결 된 상태로 유지 됩니다.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>아직 에이전트에 연결 되지 않은 진행 중인 통화</p></td>
<td><p>통화가 끊깁니다.</p></td>
<td><ul>
<li><p>응답 그룹을 가져오지 못한 경우에는 모든 호출이이 상태에 있지 않습니다.</p></li>
<li><p>가져온 응답 그룹의 경우 백업 풀에 도달 하는 호출은 연결 된 상태로 유지 됩니다.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>새로운 통화</p></td>
<td><ul>
<li><p>통화가 끊깁니다.</p></li>
<li><p>가져온 응답 그룹의 경우 백업 풀에 연결을 호출 하지만 기본 풀에 있는 에이전트는 연결할 수 없습니다.</p></li>
</ul></td>
<td><ul>
<li><p>응답 그룹을 가져오지 못한 경우에는 통화가 끊깁니다.</p></li>
<li><p>가져온 응답 그룹의 경우 백업 풀에 연결을 호출 합니다.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>응답 그룹을 대신 하 여 에이전트 호출</p></td>
<td><p>이 단계에서 기능을 사용할 수 없습니다.</p></td>
<td><ul>
<li><p>응답 그룹을 가져오지 못한 경우에는 호출이 실패 합니다.</p></li>
<li><p>가져온 응답 그룹의 경우 호출이 성공 합니다.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>에이전트 로그인 및 에이전트 정보</p></td>
<td><ul>
<li><p>주 풀 소유의 에이전트 그룹은 에이전트 콘솔에서 볼 수 있지만 에이전트는 로그인 할 수 없습니다.</p></li>
<li><p>에이전트 콘솔에서 백업 풀 소유의 에이전트 그룹을 볼 수 있으며, 에이전트는 로그인 할 수 있습니다.</p></li>
<li><p>가져온 에이전트 그룹은 에이전트 콘솔에 표시 되 고, 에이전트는 로그인 할 수 있습니다.</p></li>
</ul></td>
<td><ul>
<li><p>주 풀 소유의 에이전트 그룹은 에이전트 콘솔에서 볼 수 있지만 에이전트는 로그인 할 수 없습니다.</p></li>
<li><p>에이전트 콘솔에서 백업 풀 소유의 에이전트 그룹을 볼 수 있으며, 에이전트는 로그인 할 수 있습니다.</p></li>
<li><p>가져온 에이전트 그룹은 에이전트 콘솔에 표시 되 고, 에이전트는 로그인 할 수 있습니다.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>응답 그룹 구성</p></td>
<td><ul>
<li><p>기본 풀에서 소유 하는 응답 그룹은 기본 풀의 백 엔드 데이터베이스 가용성에 따라 볼 수 있지만 수정할 수는 없습니다.</p></li>
<li><p>백업 풀 소유의 응답 그룹을 보고 수정할 수 있습니다.</p></li>
<li><p>가져온 응답 그룹은 Lync Server 제어판 또는 응답 그룹 구성 도구로 볼 수 없지만 Lync Server 관리 셸 cmdlet을 사용 하 여 구성할 수 있습니다.</p></li>
</ul></td>
<td><ul>
<li><p>백 엔드 데이터베이스의 가용성에 따라 주 풀에서 소유 하는 응답 그룹을 볼 수는 있지만 수정할 수는 없습니다.</p></li>
<li><p>백업 풀 소유의 응답 그룹을 보고 수정할 수 있습니다.</p></li>
<li><p>가져온 응답 그룹은 Lync Server 제어판 또는 응답 그룹 구성 도구로 볼 수 없지만 Lync Server 관리 셸 cmdlet을 사용 하 여 구성할 수 있습니다.</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a>장애 복구 중 사용자 환경

관리자가 기본 풀로 장애 복구 (failback)를 호출 하면 다음 표에 설명 된 대로 응답 그룹 활동이 장애 복구 중 및 이후 처리 됩니다.

<div>


> [!NOTE]  
> 재해 복구 중에는 복구 중에 기본 풀 응답 그룹을 백업 풀로 가져왔는지 여부에 따라 호출이 다르게 작동 합니다. 다음 표에서는 재해 복구 모드 중에 주 풀 응답 그룹을 백업 풀로 가져왔는지 평균 응답 그룹을 참조 합니다.



</div>

### <a name="call-handling-in-failback"></a>장애 복구 시 통화 처리

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>통화 유형 또는 사용자 작업</th>
<th>장애 복구 중</th>
<th>장애 복구 완료 후</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>에이전트에 연결 된 통화</p></td>
<td><ul>
<li><p>일반 통화는 연결 된 상태로 유지 됩니다.</p></li>
<li><p>응답 그룹을 가져오지 못한 경우에는 익명 호출이이 상태에 있지 않습니다.</p></li>
<li><p>가져온 응답 그룹의 경우 익명 통화가 연결 된 상태로 유지 됩니다.</p></li>
</ul></td>
<td><ul>
<li><p>일반 통화는 연결 된 상태로 유지 됩니다.</p></li>
<li><p>응답 그룹을 가져오지 못한 경우에는 익명 호출이이 상태에 있지 않습니다.</p></li>
<li><p>가져온 응답 그룹의 경우 익명 통화가 연결 된 상태로 유지 됩니다.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>아직 에이전트에 연결 되지 않은 진행 중인 통화</p></td>
<td><ul>
<li><p>응답 그룹을 가져오지 못한 경우에는 모든 호출이이 상태에 있지 않습니다.</p></li>
<li><p>가져온 응답 그룹의 경우 통화 연결이 끊어집니다.</p></li>
</ul></td>
<td><ul>
<li><p>응답 그룹을 가져오지 못한 경우에는 모든 호출이이 상태에 있지 않습니다.</p></li>
<li><p>가져온 응답 그룹의 경우 통화 연결이 끊어집니다.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>새로운 통화</p></td>
<td><p>기본 풀에 연결 하는 호출이 있지만 기본 풀에 있는 에이전트에는 연결할 수 없습니다.</p></td>
<td><p>기본 풀에 연결을 호출 합니다.</p></td>
</tr>
<tr class="even">
<td><p>응답 그룹을 대신 하 여 에이전트 호출</p></td>
<td><p>이 단계에서는 기능을 사용할 수 없습니다.</p></td>
<td><p>통화에 성공 했습니다.</p></td>
</tr>
<tr class="odd">
<td><p>에이전트 로그인 및 에이전트 정보</p></td>
<td><ul>
<li><p>주 풀 소유의 에이전트 그룹은 에이전트 콘솔에서 볼 수 있지만 에이전트는 로그인 할 수 없습니다.</p></li>
<li><p>에이전트 콘솔에서 백업 풀 소유의 에이전트 그룹을 볼 수 있으며, 에이전트는 로그인 할 수 있습니다.</p></li>
<li><p>가져온 에이전트 그룹은 에이전트 콘솔에 표시 되 고, 에이전트는 로그인 할 수 있습니다.</p></li>
</ul></td>
<td><ul>
<li><p>주 풀 소유의 에이전트 그룹은 에이전트 콘솔에서 볼 수 있으며, 에이전트는 로그인 할 수 있습니다.</p></li>
<li><p>에이전트 콘솔에서 백업 풀 소유의 에이전트 그룹을 볼 수 있으며, 에이전트는 로그인 할 수 있습니다.</p></li>
<li><p>가져온 에이전트 그룹은 에이전트 콘솔에 표시 되지 않습니다.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>응답 그룹 구성</p></td>
<td><ul>
<li><p>기본 풀에서 소유 하는 응답 그룹은 기본 풀의 백 엔드 데이터베이스 가용성에 따라 볼 수 있지만 수정할 수는 없습니다.</p></li>
<li><p>백업 풀 소유의 응답 그룹을 보고 수정할 수 있습니다.</p></li>
<li><p>가져온 응답 그룹은 Lync Server 제어판 또는 응답 그룹 구성 도구로 볼 수 없지만 Lync Server 관리 셸 cmdlet을 사용 하 여 구성할 수 있습니다.</p></li>
</ul></td>
<td><ul>
<li><p>기본 풀 소유의 응답 그룹을 보고 수정할 수 있습니다.</p></li>
<li><p>백업 풀 소유의 응답 그룹을 보고 수정할 수 있습니다.</p></li>
<li><p>가져온 응답 그룹은 Lync Server 제어판 또는 응답 그룹 구성 도구로 볼 수 없지만 Lync Server 관리 셸 cmdlet을 사용 하 여 구성할 수 있습니다.</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

