---
title: 풀 오류 발생 시 Lync Server 2013 응답 그룹 환경
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response group experience during pool failure
ms:assetid: 4e00fb38-64b1-4fd9-903d-7639177bc303
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204886(v=OCS.15)
ms:contentKeyID: 48184116
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 684d33219bb6146a0c5dc85894c060affd6745a2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511645"
---
# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a>풀 오류 발생 시 Lync Server 2013의 응답 그룹 환경

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-30_

이 섹션에서는 다음 단계에서 응답 그룹 활동에 주는 영향에 대해 자세히 설명합니다.

  - 기본 풀에서 중단이 발생하지만 장애 조치(Failover)가 아직 시작되지 않았습니다.

  - 서비스가 백업 풀로 장애 조치(failover)됩니다.

  - 서비스가 기본 풀로 장애 복구(failback)됩니다.

<div>

## <a name="user-experience-when-outage-occurs"></a>중단 발생 시 사용자 환경

풀 또는 사이트 중단이 발생하지만 관리자가 아직 장애 조치(failover)를 시작하지 않은 경우 응답 그룹 활동은 다음 표에 설명된 방식으로 처리됩니다.

<div>


> [!NOTE]  
> 재해 복구 중 통화는 기본 풀 응답 그룹을 복구 중에 백업 풀로 가져왔는지 여부에 따라 다르게 작동합니다. 다음 표에서 가져온 응답 그룹에 대한 참조는 기본 풀 응답 그룹을 재해 복구 모드 중에 백업 풀로 가져왔음을 의미합니다.



</div>

### <a name="outage-occurs"></a>중단 발생

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>통화 또는 사용자 작업 유형</th>
<th>중단 중</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>에이전트에 연결된 통화</p></td>
<td><ul>
<li><p>일반 통화는 연결된 상태로 유지됩니다.</p></li>
<li><p>익명 통화는 연결이 끊어집니다.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>에이전트에 아직 연결되지 않은 진행 중인 통화</p></td>
<td><p>통화 연결이 끊어집니다.</p></td>
</tr>
<tr class="odd">
<td><p>새 통화</p></td>
<td><ul>
<li><p>통화 연결이 끊어집니다.</p></li>
<li><p>응답 그룹을 가져왔으면 백업 풀로 통화가 연결되지만 기본 풀에 있는 에이전트에 연결할 수 없습니다.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>응답 그룹을 대신하는 에이전트 통화</p></td>
<td><p>이 단계 중에는 기능이 해제됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>에이전트 로그인 및 에이전트 정보</p></td>
<td><ul>
<li><p>기본 풀이 소유하는 에이전트 그룹은 에이전트 콘솔에서 볼 수 있지만 에이전트가 로그인할 수 없습니다.</p></li>
<li><p>백업 풀이 소유하는 에이전트 그룹은 에이전트 콘솔에서 볼 수 있고 에이전트가 로그인할 수 있습니다.</p></li>
<li><p>가져온 에이전트 그룹은 에이전트 콘솔에 표시되지 않습니다.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>응답 그룹 구성</p></td>
<td><ul>
<li><p>기본 풀이 소유하는 응답 그룹은 기본 풀의 백 엔드 데이터베이스 가용성에 따라 볼 수 있지만 수정할 수는 없습니다.</p></li>
<li><p>백업 풀이 소유하는 응답 그룹은 보고 수정할 수 있습니다.</p></li>
<li><p>가져온 응답 그룹은 Lync Server 제어판 또는 응답 그룹 구성 도구로 볼 수 없지만 Lync Server 관리 셸 cmdlet을 사용 하 여 구성할 수 있습니다.</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a>장애 조치(Failover) 중 사용자 환경

관리자가 백업 풀에 대한 장애 조치(failover)를 호출할 경우, 장애 조치(failover) 동안 및 이후의 응답 그룹 활동은 다음 표에 설명된 대로 처리됩니다. 첫 번째 열은 발생 가능한 활동 유형에 대해 설명합니다. 가운데 열은 백업 풀로 장애 조치(failover)하는 짧은 시간 동안 각 활동이 처리되는 방법에 대해 설명합니다. 마지막 열은 장애 조치(failover) 프로세스가 완료되고 백업 풀이 기본 풀 대신 작동하는 기간 동안 활동이 처리되는 방법을 설명합니다.

<div>


> [!NOTE]  
> 재해 복구 중 통화는 기본 풀 응답 그룹을 복구 중에 백업 풀로 가져왔는지 여부에 따라 다르게 작동합니다. 다음 표에서 가져온 응답 그룹에 대한 참조는 기본 풀 응답 그룹을 재해 복구 모드 중에 백업 풀로 가져왔음을 의미합니다.



</div>

### <a name="failover-is-initiated"></a>장애 조치(Failover)가 시작됨

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>통화 또는 사용자 작업 유형</th>
<th>장애 조치(Failover) 동안</th>
<th>장애 조치(Failover) 완료 후</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>에이전트에 연결된 통화</p></td>
<td><ul>
<li><p>일반 통화는 연결된 상태로 유지됩니다.</p></li>
<li><p>익명 통화는 연결이 끊어집니다.</p></li>
</ul></td>
<td><ul>
<li><p>일반 통화는 연결된 상태로 유지됩니다.</p></li>
<li><p>가져온 응답 그룹의 경우 백업 풀에 연결된 익명 통화는 연결된 상태로 유지됩니다.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>에이전트에 아직 연결되지 않은 진행 중인 통화</p></td>
<td><p>통화 연결이 끊어집니다.</p></td>
<td><ul>
<li><p>응답 그룹을 가져오지 않은 경우 이 상태의 통화가 없습니다.</p></li>
<li><p>가져온 응답 그룹의 경우 백업 풀에 연결된 통화는 연결된 상태로 유지됩니다.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>새 통화</p></td>
<td><ul>
<li><p>통화 연결이 끊어집니다.</p></li>
<li><p>가져온 응답 그룹의 경우 통화가 백업 풀에 연결되지만 기본 풀에 있는 에이전트에는 연결할 수 없습니다.</p></li>
</ul></td>
<td><ul>
<li><p>응답 그룹을 가져오지 않은 경우 통화의 연결이 끊어집니다.</p></li>
<li><p>가져온 응답 그룹의 경우 통화가 백업 풀에 연결됩니다.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>응답 그룹을 대신하는 에이전트 통화</p></td>
<td><p>이 단계 중에는 기능이 해제됩니다.</p></td>
<td><ul>
<li><p>응답 그룹을 가져오지 않은 경우 통화가 실패합니다.</p></li>
<li><p>가져온 응답 그룹의 경우 통화가 성공합니다.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>에이전트 로그인 및 에이전트 정보</p></td>
<td><ul>
<li><p>기본 풀이 소유하는 에이전트 그룹은 에이전트 콘솔에서 볼 수 있지만 에이전트가 로그인할 수 없습니다.</p></li>
<li><p>백업 풀이 소유하는 에이전트 그룹은 에이전트 콘솔에서 볼 수 있고 에이전트가 로그인할 수 있습니다.</p></li>
<li><p>가져온 에이전트 그룹이 에이전트 콘솔에 표시되고 에이전트가 로그인할 수 있습니다.</p></li>
</ul></td>
<td><ul>
<li><p>기본 풀이 소유하는 에이전트 그룹은 에이전트 콘솔에서 볼 수 있지만 에이전트가 로그인할 수 없습니다.</p></li>
<li><p>백업 풀이 소유하는 에이전트 그룹은 에이전트 콘솔에서 볼 수 있고 에이전트가 로그인할 수 있습니다.</p></li>
<li><p>가져온 에이전트 그룹이 에이전트 콘솔에 표시되고 에이전트가 로그인할 수 있습니다.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>응답 그룹 구성</p></td>
<td><ul>
<li><p>기본 풀이 소유하는 응답 그룹은 기본 풀의 백 엔드 데이터베이스 가용성에 따라 볼 수 있지만 수정할 수는 없습니다.</p></li>
<li><p>백업 풀이 소유하는 응답 그룹은 보고 수정할 수 있습니다.</p></li>
<li><p>가져온 응답 그룹은 Lync Server 제어판 또는 응답 그룹 구성 도구로 볼 수 없지만 Lync Server 관리 셸 cmdlet을 사용 하 여 구성할 수 있습니다.</p></li>
</ul></td>
<td><ul>
<li><p>기본 풀이 소유하는 응답 그룹은 백 엔드 데이터베이스의 가용성에 따라 볼 수 있지만 수정할 수는 없습니다.</p></li>
<li><p>백업 풀이 소유하는 응답 그룹은 보고 수정할 수 있습니다.</p></li>
<li><p>가져온 응답 그룹은 Lync Server 제어판 또는 응답 그룹 구성 도구로 볼 수 없지만 Lync Server 관리 셸 cmdlet을 사용 하 여 구성할 수 있습니다.</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a>복구(Failback) 중 사용자 환경

관리자가 기본 풀로 복구(failback)를 호출할 경우, 복구(failback) 동안 및 이후의 응답 그룹 활동은 다음 표에 설명된 대로 처리됩니다.

<div>


> [!NOTE]  
> 재해 복구 중 통화는 기본 풀 응답 그룹을 복구 중에 백업 풀로 가져왔는지 여부에 따라 다르게 작동합니다. 다음 표에서 가져온 응답 그룹에 대한 참조는 기본 풀 응답 그룹을 재해 복구 모드 중에 백업 풀로 가져왔음을 의미합니다.



</div>

### <a name="call-handling-in-failback"></a>복구(Failback) 중 통화 처리

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>통화 또는 사용자 작업 유형</th>
<th>복구(Failback) 동안</th>
<th>복구(Failback) 완료 후</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>에이전트에 연결된 통화</p></td>
<td><ul>
<li><p>일반 통화는 연결된 상태로 유지됩니다.</p></li>
<li><p>응답 그룹을 가져오지 않은 경우 이 상태의 익명 통화가 없습니다.</p></li>
<li><p>가져온 응답 그룹의 경우 익명 통화가 연결된 상태로 유지됩니다.</p></li>
</ul></td>
<td><ul>
<li><p>일반 통화는 연결된 상태로 유지됩니다.</p></li>
<li><p>응답 그룹을 가져오지 않은 경우 이 상태의 익명 통화가 없습니다.</p></li>
<li><p>가져온 응답 그룹의 경우 익명 통화가 연결된 상태로 유지됩니다.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>에이전트에 아직 연결되지 않은 진행 중인 통화</p></td>
<td><ul>
<li><p>응답 그룹을 가져오지 않은 경우 이 상태의 통화가 없습니다.</p></li>
<li><p>가져온 응답 그룹의 경우 통화의 연결이 끊어집니다.</p></li>
</ul></td>
<td><ul>
<li><p>응답 그룹을 가져오지 않은 경우 이 상태의 통화가 없습니다.</p></li>
<li><p>가져온 응답 그룹의 경우 통화의 연결이 끊어집니다.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>새 통화</p></td>
<td><p>통화가 기본 풀에 연결되지만 기본 풀에 있는 에이전트에는 연결할 수 없습니다.</p></td>
<td><p>통화가 기본 풀에 연결됩니다.</p></td>
</tr>
<tr class="even">
<td><p>응답 그룹을 대신하는 에이전트 통화</p></td>
<td><p>이 단계 중에는 기능이 해제됩니다.</p></td>
<td><p>통화가 성공합니다.</p></td>
</tr>
<tr class="odd">
<td><p>에이전트 로그인 및 에이전트 정보</p></td>
<td><ul>
<li><p>기본 풀이 소유하는 에이전트 그룹은 에이전트 콘솔에서 볼 수 있지만 에이전트가 로그인할 수 없습니다.</p></li>
<li><p>백업 풀이 소유하는 에이전트 그룹은 에이전트 콘솔에서 볼 수 있고 에이전트가 로그인할 수 있습니다.</p></li>
<li><p>가져온 에이전트 그룹이 에이전트 콘솔에 표시되고 에이전트가 로그인할 수 있습니다.</p></li>
</ul></td>
<td><ul>
<li><p>기본 풀이 소유하는 에이전트 그룹은 에이전트 콘솔에서 볼 수 있고 에이전트가 로그인할 수 있습니다.</p></li>
<li><p>백업 풀이 소유하는 에이전트 그룹은 에이전트 콘솔에서 볼 수 있고 에이전트가 로그인할 수 있습니다.</p></li>
<li><p>가져온 에이전트 그룹은 에이전트 콘솔에 표시되지 않습니다.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>응답 그룹 구성</p></td>
<td><ul>
<li><p>기본 풀이 소유하는 응답 그룹은 기본 풀의 백 엔드 데이터베이스 가용성에 따라 볼 수 있지만 수정할 수는 없습니다.</p></li>
<li><p>백업 풀이 소유하는 응답 그룹은 보고 수정할 수 있습니다.</p></li>
<li><p>가져온 응답 그룹은 Lync Server 제어판 또는 응답 그룹 구성 도구로 볼 수 없지만 Lync Server 관리 셸 cmdlet을 사용 하 여 구성할 수 있습니다.</p></li>
</ul></td>
<td><ul>
<li><p>기본 풀이 소유하는 응답 그룹은 보고 수정할 수 있습니다.</p></li>
<li><p>백업 풀이 소유하는 응답 그룹은 보고 수정할 수 있습니다.</p></li>
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

