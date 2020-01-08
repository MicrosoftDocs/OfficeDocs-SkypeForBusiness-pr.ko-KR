---
title: 'Lync Server 2013: 사용자별 현재 상태 정책 지정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assigning per-user presence policies
ms:assetid: fd1097b7-248d-4b78-8c43-456b03257c18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182614(v=OCS.15)
ms:contentKeyID: 48185955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 905065e231869b4b6075fc1894e51c91df8f0aee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983851"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-presence-policies-in-lync-server-2013"></a>Lync Server 2013에서 사용자 단위 현재 상태 정책 지정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-11_

현재 상태 정책은 현재 상태에 영향을 주는 제한 및 제한 집합입니다. 다음 표에서는 Lync Server 2013에서 사용할 수 있는 현재 상태 정책 설정에 대해 설명 합니다.

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
<th>유형</th>
<th>값</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CategorySubscriptions</p></td>
<td><p>최대 구독자 범주 구독 수</p></td>
<td><p>구독자 범주 구독 수를 제한 합니다. 예를 들어 Communicator에서 사용자의 현재 상태를 구독할 때 각 연락처 카드, 일정 데이터, 메모, 서비스 및 상태 범주에 대 한 범주 구독을 가져옵니다.</p>
<p>0으로 설정 하면 사용자 또는 연락처 개체가 다른 사람에 의해 구독 될 수 없음을 의미 합니다.</p>
<div>

> [!NOTE]  
> 이 설정은 높은 번호로 설정 했 고 평균 사용자가 자신의 현재 상태를 구독 하는 사용자 수가 많은 경우 성능에 큰 영향을 미칠 수 있습니다.


</div></td>
<td><p>정수</p></td>
<td><p>0-3000</p></td>
</tr>
<tr class="even">
<td><p>PromptedSubscribers</p></td>
<td><p>대기 중인 현재 상태 구독 알림의 최대 수</p></td>
<td><p>메시지를 입력 하 여 구독자 테이블의 항목 수를 제한 합니다. 이 설정은 지정 된 사용자에 대해 대기 시킬 수 있는 최대 메시지 수를 결정 합니다. 예를 들어 사용자 A가 사용자 B의 현재 상태를 구독 하는 경우 사용자 B가 사용자 B에 게 구독 하 라는 메시지가 표시 되 고 사용자 B의 질문 구독자 테이블에 승인 메시지가 만들어집니다. 사용자 B가 구독을 수락 하거나 승인 하면 사용자 B의 질문 구독자 테이블에서 승인 메시지가 제거 됩니다.</p>
<p>0으로 설정 하면 다른 사용자가 자신의 현재 상태를 구독할 때 메시지가 표시 되지 않는다는 의미입니다.</p></td>
<td><p>정수 또는 토큰</p></td>
<td><p>0-500</p></td>
</tr>
</tbody>
</table>


기본적으로 **기본 정책** 및 **서비스:** 사용자가 Lync Server를 배포할 때 중간 현재 상태 정책이 설치 됩니다. 다음 표에서는 두 현재 상태 정책의 특정 설정에 대해 설명 합니다.

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
<td><p>일반 사용자를 위한 정책. 이는 기본 현재 상태 정책입니다.</p></td>
<td><p>1000</p></td>
<td><p>200</p></td>
</tr>
<tr class="even">
<td><p>서비스: 보통</p></td>
<td><p>더 많은 사용자가 개체의 현재 상태를 구독 하도록 요구 하는 응용 프로그램에 대 한 정책입니다.</p></td>
<td><p>1000</p></td>
<td><p>0</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

