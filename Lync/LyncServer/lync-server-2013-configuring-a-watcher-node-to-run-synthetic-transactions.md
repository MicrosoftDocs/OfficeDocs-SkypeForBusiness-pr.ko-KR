---
title: 'Lync Server 2013: 가상 트랜잭션을 실행 하도록 감시자 노드 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to run synthetic transactions
ms:assetid: cedda508-8881-4079-88d5-49798f342ddf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205314(v=OCS.15)
ms:contentKeyID: 48185578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9514099b3981dafdbb34911d0cedd249221c5621
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499105"
---
# <a name="configuring-a-watcher-node-to-run-synthetic-transactions-in-lync-server-2013"></a>Lync Server 2013에서 가상 트랜잭션을 실행 하도록 감시자 노드 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-02-07_

System Center 에이전트 파일을 설치한 후에는 다음에 감시자 노드 자체를 구성 해야 합니다. 감시자 노드를 구성 하기 위해 수행 하는 단계는 감시자 노드 컴퓨터가 경계 네트워크 내에 있는지 아니면 경계 네트워크 외부에 있는 지에 따라 달라 집니다.

감시자 노드를 구성할 때는 해당 노드에서 사용할 인증 방법의 유형도 선택 해야 합니다. Lync Server 2013에서는 신뢰할 수 있는 서버 또는 자격 증명 인증 이라는 두 가지 인증 방법 중 하나를 선택할 수 있습니다. 다음 표에서는 이러한 두 방법의 차이점에 대해 설명 합니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>구성</th>
<th>설명</th>
<th>지원 되는 위치</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>신뢰할 수 있는 서버</p></td>
<td><p>인증서를 사용 하 여 내부 서버를 가장 하 고 인증 문제를 무시 합니다.</p>
<p>이 기능은 각 감시자 노드에서 많은 사용자 암호를 사용 하지 않고 단일 인증서를 관리 하려는 관리자에 게 유용 합니다.</p></td>
<td><p>기업 내부</p>
<p>이 방법을 사용 하는 경우 감시자 노드는 모니터링 되는 풀과 같은 도메인에 있어야 합니다. 감시자 노드와 모니터링 되는 풀이 서로 다른 도메인에 있는 경우 자격 증명 인증을 대신 사용 합니다.</p></td>
</tr>
<tr class="even">
<td><p>자격 증명 인증</p></td>
<td><p>각 감시자 노드의 Windows 자격 증명 관리자에 사용자 이름과 암호를 안전 하 게 저장 합니다.</p>
<p>이 모드를 사용 하는 경우에는 더 많은 암호 관리가 필요 하지만 기업 외부에 있는 감시자 노드에 대해서만 옵션을 선택할 수 있습니다. 이러한 감시자 노드는 인증에 대해 신뢰할 수 있는 끝점으로 취급할 수 없습니다.</p></td>
<td><p>기업 외부</p>
<p>기업 내부</p></td>
</tr>
</tbody>
</table>


또한 방화벽에 MonitoringHost.exe 및 PowerShell.exe에 대 한 인바운드 규칙이 있는지도 확인 해야 합니다. 이러한 프로세스가 방화벽에 의해 차단 되 면 가상 트랜잭션이 504 (서버 시간 제한) 오류로 인해 실패 합니다.

</div>

<span> </span>

</div>

</div>

</div>

