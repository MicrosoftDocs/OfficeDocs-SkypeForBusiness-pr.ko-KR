---
title: 'Lync Server 2013: PSTN 사용 레코드'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN usage records
ms:assetid: b5f624aa-abe8-455b-a8e3-c228be230463
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412878(v=OCS.15)
ms:contentKeyID: 48185188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e32000f1664591a3e054d058ced4f996a98f27cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984487"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-usage-records-in-lync-server-2013"></a>Lync Server 2013의 PSTN 사용 레코드

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-23_

PSTN 사용 레코드 계획은 주로 조직에서 현재 적용 되는 모든 통화 사용 권한 (CEO에서 임시 작업자, 컨설턴트, 불확정 스태프)으로 구성 됩니다. 이 프로세스는 또한 기존 통화 권한을 찾아 수정할 수 있는 기회를 제공 합니다. 예상 엔터프라이즈 음성 사용자에 게 적용 되는 통화 권한에 대해서만 PSTN 사용 레코드를 만들 수 있지만, 더 나은 범위의 해결 방법은 일부 통화 권한에 대 한 PSTN 사용 레코드를 만드는 것이 현재 일부 경우에는 발생 하지 않을 수 있는지 여부에 관계 없이 엔터프라이즈 음성에 대해 사용 하도록 설정할 사용자 그룹에 적용 합니다. 통화 권한이 변경 되거나 다른 통화 권한이 있는 새 사용자가 추가 된 경우에는 이미 필요한 PSTN 사용 레코드가 생성 된 것입니다.

다음 표에는 일반적인 PSTN 사용 테이블이 나와 있습니다.

### <a name="pstn-usage-records"></a>PSTN 사용 레코드

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Phone 특성</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>로컬</p></td>
<td><p>시내 통화</p></td>
</tr>
<tr class="even">
<td><p>시외</p></td>
<td><p>시외 통화</p></td>
</tr>
<tr class="odd">
<td><p>국제화</p></td>
<td><p>국제 전화</p></td>
</tr>
<tr class="even">
<td><p>뉴델리</p></td>
<td><p>뉴델리 전일 근무 직원</p></td>
</tr>
<tr class="odd">
<td><p>Redmond</p></td>
<td><p>Redmond 전일 근무 직원</p></td>
</tr>
<tr class="even">
<td><p>RedmondTemps</p></td>
<td><p>Redmond 임시 직원</p></td>
</tr>
<tr class="odd">
<td><p>Zurich</p></td>
<td><p>Zurich 전일 근무 직원</p></td>
</tr>
</tbody>
</table>


PSTN 사용 레코드는 그 자체로 아무런 작업도 수행 하지 않습니다. 이 작업을 수행 하려면 다음을 연결 해야 합니다.

  - 사용자에 게 할당 되는 음성 정책

  - 경로-전화 번호에 할당 됩니다.

음성 정책 및 경로에 대 한 자세한 내용은 lync [server 2013의 음성 정책](lync-server-2013-voice-policies.md) 및 [lync Server 2013의 음성 경로](lync-server-2013-voice-routes.md)를 참조 하세요. 이를 만들고 구성 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 발신 통화에 대 한 음성 경로 구성을](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)참조 하세요.

</div>

<span> </span>

</div>

</div>

</div>

