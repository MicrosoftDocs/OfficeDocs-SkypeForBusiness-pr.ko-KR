---
title: 'Lync Server 2013: 이전 배포에서 지원 되는 클라이언트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported clients from previous deployments
ms:assetid: 69d427f8-57a5-4244-b2ed-f2eb7600285e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398499(v=OCS.15)
ms:contentKeyID: 48184390
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f404dad679eeffa91465f3f8547fbe86ce74b0c1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524135"
---
# <a name="supported-clients-from-previous-deployments-in-lync-server-2013"></a>Lync Server 2013의 이전 배포에서 지원 되는 클라이언트

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-12-14_

동시 사용 시나리오에서 Lync Server 2013 클라이언트는 이전 버전의 Lync Server 및 Office Communications Server에서 클라이언트와 상호 작용할 수 있습니다. 이전 릴리스와 달리 Lync Server 2010에서는 새 Lync 2013 클라이언트를 지원 합니다. 이를 통해 Lync Server 2010에서 업그레이드 하는 조직은 Lync Server 업그레이드에 관계 없이 새 클라이언트를 롤아웃할 수 있습니다.

<div>

## <a name="supported-server-and-client-combinations"></a>지원 되는 서버 및 클라이언트 조합

다음 표에는 지원 되는 클라이언트 버전 및 서버 버전 조합이 나와 있습니다. Lync Server 2013는 이전 클라이언트 버전 두 개를 지원 하며 Lync Server 2010은 새로운 Lync 2013 클라이언트를 지원 합니다.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>클라이언트</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>지원</p></td>
<td><p>지원</p></td>
<td><p>지원되지 않음</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2013</p></td>
<td><p>지원</p></td>
<td><p>지원되지 않음</p></td>
<td><p>지원되지 않음</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010</p></td>
<td><p>지원</p></td>
<td><p>지원</p></td>
<td><p>지원되지 않음</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendant</p></td>
<td><p>지원</p></td>
<td><p>지원</p></td>
<td><p>지원되지 않음</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 그룹 채팅</p></td>
<td><p>해당 없음</p></td>
<td><p>1</p></td>
<td><p>해당 없음</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2010</p></td>
<td><p>지원되지 않음</p></td>
<td><p>않음</p></td>
<td><p>지원되지 않음</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Attendee</p></td>
<td><p>2 아님</p></td>
<td><p>지원</p></td>
<td><p>지원되지 않음</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperable3</p></td>
<td><p>지원</p></td>
<td><p>지원</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft Office Communications Server 2007 R2 Attendant</p></td>
<td><p>지원되지 않음</p></td>
<td><p>않음</p></td>
<td><p>지원</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007</p></td>
<td><p>지원되지 않음</p></td>
<td><p>않음</p></td>
<td><p>지원</p></td>
</tr>
<tr class="odd">
<td><p>Office Live Meeting 2007</p></td>
<td><p>지원되지 않음</p></td>
<td><p>않음</p></td>
<td><p>지원</p></td>
</tr>
</tbody>
</table>


1In Microsoft Lync Server 2010의 경우 그룹 채팅 기능은 Lync Server 2010 용 타사 트러스트 응용 프로그램 그룹 채팅 서버에서 사용할 수 있었습니다. Lync 2013 클라이언트는 Lync Server 2010, 그룹 채팅과 호환 되지 않습니다.

2Lync Web App 2013는 이제 컴퓨터 오디오 및 비디오를 비롯 한 전체 모임 환경을 제공 하며 Lync 2010 참석자의 교체로 간주 됩니다.

3 Office Communicator 2007 R2의 현재 상태 및 IM 기능은 Lync Server 2013와 호환 되지만 회의 기능은 없습니다. Office Communications Server 2007 R2에서 마이그레이션하는 동안 Office Communicator 2007 R2는 현재 상태 및 IM 상호 운용성에 적합 하지만 lync Web App 2013을 사용 하 여 Lync Server 2013 meeting에 참가 해야 합니다.

<div>


> [!NOTE]  
> Lync Server 2013 클라이언트가 이전 버전의 Lync Server 및 Office Communications Server와 함께 사용 되 고 클라이언트와 상호 작용 하는 기능에 대 한 자세한 내용은 계획 설명서에서 <A href="lync-server-2013-client-interoperability-in-lync-2013.md">lync 2013의 클라이언트 상호 운용성</A> 을 참조 하십시오.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

