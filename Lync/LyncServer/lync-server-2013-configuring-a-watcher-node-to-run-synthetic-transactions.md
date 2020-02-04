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
ms.openlocfilehash: 19211c786c288326d5769824524f5571e5df2f00
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763422"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-run-synthetic-transactions-in-lync-server-2013"></a>Lync Server 2013에서 종합 트랜잭션을 실행 하도록 감시자 노드 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-02-07_

System Center agent 파일을 설치한 후에는 다음에 감시자 노드 자체를 구성 해야 합니다. 감시자 노드를 구성 하기 위해 수행 하는 단계는 감시자 노드 컴퓨터가 주변 네트워크 내에 있는지 아니면 경계 네트워크 외부에 있든에 따라 달라 집니다.

감시자 노드를 구성할 때는 해당 노드에서 사용할 인증 방법의 종류도 선택 해야 합니다. Lync Server 2013에서는 신뢰할 수 있는 서버 또는 자격 증명 인증 이라는 두 가지 인증 방법 중 하나를 선택할 수 있습니다. 다음 표에서는 이러한 두 메서드의 차이점에 대해 설명 합니다.


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
<td><p>인증서를 사용 하 여 내부 서버를 가장 하 고 인증 챌린지를 무시 합니다.</p>
<p>이 기능은 각 감시자 노드에 대 한 여러 사용자 암호 대신 단일 인증서를 관리 하는 관리자에 게 유용 합니다.</p></td>
<td><p>엔터프라이즈 내에 있습니다.</p>
<p>이 메서드를 사용 하는 경우 감시자 노드는 모니터링 하는 풀과 동일한 도메인에 있어야 합니다. 감시자 노드와 모니터링 되는 풀이 서로 다른 도메인에 있는 경우 자격 증명 인증을 대신 사용 합니다.</p></td>
</tr>
<tr class="even">
<td><p>자격 증명 인증</p></td>
<td><p>각 감시자 노드의 Windows 자격 증명 관리자에 사용자 이름 및 암호를 안전 하 게 저장 합니다.</p>
<p>이 모드는 더 많은 암호 관리가 필요 하지만, 엔터프라이즈 외부에 있는 감시자 노드에는 유일한 옵션입니다. 이러한 감시자 노드는 인증을 위해 신뢰할 수 있는 끝점으로 취급할 수 없습니다.</p></td>
<td><p>기업 외부</p>
<p>엔터프라이즈 내에 있습니다.</p></td>
</tr>
</tbody>
</table>


또한 방화벽에 MonitoringHost 및 debug.exe 모두에 대 한 인바운드 규칙이 있는지 확인 해야 합니다. 이러한 프로세스가 방화벽에 의해 차단 되는 경우 504 (서버 시간 초과) 오류로 인해 가상 트랜잭션을 수행할 수 없게 됩니다.

</div>

<span> </span>

</div>

</div>

</div>

