---
title: 'Lync Server 2013: 사용자별 현재 상태 정책 할당'
description: 'Lync Server 2013: 사용자별 현재 상태 정책을 할당 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning per-user presence policies
ms:assetid: fd1097b7-248d-4b78-8c43-456b03257c18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182614(v=OCS.15)
ms:contentKeyID: 48185955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c3d4b4bda0c4bb85065d546fdbb4b2578db0e3f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563374"
---
# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a>Lync Server 2013에서 사용자별 현재 상태 정책 할당

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-11_

현재 상태 정책은 현재 상태에 영향을 미치는 제한 집합입니다. 다음 표에서는 Lync Server 2013에서 사용할 수 있는 현재 상태 정책 설정에 대해 설명 합니다.

### <a name="presence-policy-settings"></a>현재 상태 정책 설정

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>XML 이름</th>
<th>표시 이름</th>
<th>설명</th>
<th>타이핑</th>
<th>값</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CategorySubscriptions</p></td>
<td><p>구독자 범주의 최대 구독 수</p></td>
<td><p>구독자의 범주 구독 수를 제한합니다. 예를 들어 Communicator가 사용자의 현재 상태를 구독하면 대화 상대 카드, 일정 데이터, 메모, 서비스 및 상태 범주 각각에 대한 범주 구독을 가져오게 됩니다.</p>
<p>설정이 0인 경우 다른 사용자가 사용자나 대화 상대 개체의 상태를 구독할 수 없습니다.</p>
<div>

> [!NOTE]  
> 이 설정에 지정된 숫자가 높을 경우 성능이 심각하게 저하될 수 있으며 해당 사용자의 현재 상태를 구독하는 사용자가 많아집니다.


</div></td>
<td><p>정수</p></td>
<td><p>0-3000</p></td>
</tr>
<tr class="even">
<td><p>PromptedSubscribers</p></td>
<td><p>현재 상태 구독에 대해 대기할 수 있는 최대 알림 수</p></td>
<td><p>프롬프트 구독자 테이블의 항목 수를 제한합니다. 이 설정으로, 해당 사용자에 대해 대기할 수 있는 최대 프롬프트 수가 결정됩니다. 예를 들어 사용자 A가 사용자 B의 현재 상태를 구독할 때 사용자 B는 사용자 A가 이제 사용자 B의 현재 상태를 구독한다는 프롬프트를 받게 되며 사용자 B의 프롬프트 구독자 테이블에서 승인 프롬프트가 만들어집니다. 사용자 B가 구독을 수락하거나 승인하고 나면 사용자 B의 프롬프트 구독자 테이블에서 승인 프롬프트가 제거됩니다.</p>
<p>설정이 0인 경우 다른 사람이 사용자의 현재 상태를 구독할 때 해당 사용자에게 메시지가 표시되지 않습니다.</p></td>
<td><p>정수 또는 토큰</p></td>
<td><p>0-500</p></td>
</tr>
</tbody>
</table>


기본적으로 **기본 정책** 및 **서비스: 중간** 거점 정책은 Lync Server를 배포할 때 설치 됩니다. 다음 표에는 두 개의 현재 상태 정책에 대한 특정 설정이 나와 있습니다.

### <a name="presence-policies"></a>현재 상태 정책

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>정책 이름</th>
<th>설명</th>
<th>CategorySubscriptions</th>
<th>PromptedSubscribers</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>기본 정책</p></td>
<td><p>일반 사용자를 위한 정책이며, 기본 현재 상태 정책입니다.</p></td>
<td><p>1000</p></td>
<td><p>200</p></td>
</tr>
<tr class="even">
<td><p>서비스: 보통</p></td>
<td><p>기타 사용자가 개체의 현재 상태를 구독해야 하는 응용 프로그램을 위한 정책입니다.</p></td>
<td><p>1000</p></td>
<td><p>개</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

