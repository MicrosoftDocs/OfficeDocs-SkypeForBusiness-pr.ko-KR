---
title: 'Lync Server 2013: 도메인 준비에의 한 변경 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by domain preparation
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398742(v=OCS.15)
ms:contentKeyID: 48184845
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbdd1fa1fbb5bd7a396e17f478326a9e4dd700f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730108"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a>Lync Server 2013에서 도메인 준비에의 한 변경 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2010-10-18_

다음 표에는 도메인 준비에서 도메인 루트에 만드는 Ace (액세스 제어 항목)가 나열 되어 있습니다. 다른 언급이 없는 한 모든 Ace는 상속 됩니다.

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a>도메인 루트에 추가 된 Ace

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>ACE</th>
<th>RTCUniversal-UserReadOnly-Group</th>
<th>RTCUniversal-ServerReadOnly-Group</th>
<th>RTCUniversal-UserAdmins</th>
<th>RTCHSUniversal 서비스</th>
<th>인증 된 사용자</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>컨테이너 읽기 (상속 되지 않음)</p></td>
<td><p><strong>'</strong></p></td>
<td><p><strong>'</strong></p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="even">
<td><p>사용자 PropertySet 사용자 계정 제한 사항 읽기</p></td>
<td><p><strong>'</strong></p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="odd">
<td><p>사용자 PropertySet 개인 정보 읽기</p></td>
<td><p><strong>'</strong></p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="even">
<td><p>사용자 PropertySet 일반 정보 읽기</p></td>
<td><p><strong>'</strong></p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="odd">
<td><p>사용자 PropertySet 공개 정보 읽기</p></td>
<td><p><strong>'</strong></p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="even">
<td><p>PropertySet 사용자 읽기 RTCUserSearchProperty-설정</p></td>
<td><p><strong>'</strong></p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p><strong>예</strong></p></td>
</tr>
<tr class="odd">
<td><p>사용자 PropertySet RTCPropertySet 읽기</p></td>
<td><p><strong>'</strong></p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="even">
<td><p>사용자 속성 프록시-주소 쓰기</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p><strong>예</strong></p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="odd">
<td><p>PropertySet 사용자 쓰기 RTCUserSearchProperty-설정</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p><strong>예</strong></p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="even">
<td><p>사용자 PropertySet RTCPropertySet에 쓰기</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p><strong>예</strong></p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="odd">
<td><p>PropertySet 읽기-모든 Active Directory 개체의 가져오기-복제-변경</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p><strong>예</strong></p></td>
<td><p>아니요</p></td>
</tr>
</tbody>
</table>


다음 표에는 세 가지 기본 제공 컨테이너 (사용자, 컴퓨터 및 도메인 컨트롤러)에서 도메인 준비가 만드는 Ace가 나열 되어 있습니다. 다른 언급이 없는 한 모든 Ace는 상속 됩니다.

### <a name="aces-added-to-built-in-containers"></a>기본 제공 컨테이너에 Ace가 추가 됨

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>ACE</th>
<th>RTCUniversal-UserReadOnly-Group</th>
<th>RTCUniversal-ServerReadOnly-Group</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>컨테이너 읽기 (상속 되지 않음)</p></td>
<td><p><strong>'</strong></p></td>
<td><p><strong>'</strong></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

