---
title: 'Lync Server 2013: PSTN 사용 레코드'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN usage records
ms:assetid: b5f624aa-abe8-455b-a8e3-c228be230463
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412878(v=OCS.15)
ms:contentKeyID: 48185188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81f459c7ae6b581dedc5843fd2a89568a2f755a5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="pstn-usage-records-in-lync-server-2013"></a>Lync Server 2013의 PSTN 사용 레코드

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-23_

PSTN 사용 레코드 계획은 주로 CEO에서 임시 직원, 컨설턴트 및 비정규직 직원에 이르기까지 조직에서 현재 적용 중인 모든 통화 권한을 나열하는 작업으로 구성됩니다. 이 프로세스에서 기존 통화 권한을 다시 검사하고 수정할 수도 있습니다. 예상 Enterprise Voice 사용자에게 적용되는 통화 권한에 대해서만 PSTN 사용 레코드를 만들 수도 있지만 일부 통화 권한이 현재 Enterprise Voice를 사용할 수 있는 사용자 그룹에 적용되지 않는다 해도 모든 통화 권한에 대한 PSTN 사용 레코드를 만드는 것이 더 나은 장기적 솔루션이 될 수 있습니다. 통화 권한이 변경되거나 다른 통화 권한을 가진 새 사용자가 추가되어도 필요한 PSTN 사용 레코드를 이미 만들었을 것입니다.

다음 표는 일반적인 PSTN 사용 표를 보여 줍니다.

### <a name="pstn-usage-records"></a>PSTN 사용 레코드

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>전화 특성</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Local</p></td>
<td><p>시내 전화</p></td>
</tr>
<tr class="even">
<td><p>시외</p></td>
<td><p>시외 전화</p></td>
</tr>
<tr class="odd">
<td><p>영어</p></td>
<td><p>국제 전화</p></td>
</tr>
<tr class="even">
<td><p>Delhi</p></td>
<td><p>델리 정규 직원</p></td>
</tr>
<tr class="odd">
<td><p>니다</p></td>
<td><p>레드몬드 정규 직원</p></td>
</tr>
<tr class="even">
<td><p>RedmondTemps</p></td>
<td><p>레드몬드 임시 직원</p></td>
</tr>
<tr class="odd">
<td><p>취리히 정규</p></td>
<td><p>취리히 정규 직원</p></td>
</tr>
</tbody>
</table>


PSTN 사용 레코드 자체는 아무 작업도 수행하지 않습니다. PSTN 사용 레코드가 작동하려면 다음과 연결해야 합니다.

  - 사용자에게 할당된 음성 정책

  - 전화 번호에 할당된 경로

음성 정책 및 경로에 대 한 자세한 내용은 [Lync server 2013의 음성 정책](lync-server-2013-voice-policies.md) 및 [lync Server 2013의 음성 경로](lync-server-2013-voice-routes.md)를 참조 하세요. 이를 만들고 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 아웃 바운드 통화에 대 한 음성 경로 구성을](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)참조 하십시오.

</div>

<span> </span>

</div>

</div>

</div>

