---
title: 'Lync Server 2013: 도메인 준비로 인 한 변경 내용'
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
ms.openlocfilehash: fb693f79470e7d68a1aaf662c9ab82b8bafa5c39
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a>Lync Server 2013에서 도메인 준비로 인 한 변경 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2010-10-18_

다음 표에는 도메인 준비가 도메인 루트에 대해 만든 ACE(액세스 제어 항목)가 나열되어 있습니다. 다른 언급이 없는 경우 모든 ACE는 상속됩니다.

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a>도메인 루트에 추가된 ACE

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
<th>RTCUniversal UserAdmins</th>
<th>RTCHSUniversal-서비스</th>
<th>인증 된 사용자</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>컨테이너 읽기(상속되지 않음)</p></td>
<td><p><strong>예</strong></p></td>
<td><p><strong>예</strong></p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="even">
<td><p>사용자 PropertySet User-Account-Restrictions 읽기</p></td>
<td><p><strong>예</strong></p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="odd">
<td><p>사용자 PropertySet Personal-Information 읽기</p></td>
<td><p><strong>예</strong></p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="even">
<td><p>사용자 PropertySet General-Information 읽기</p></td>
<td><p><strong>예</strong></p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="odd">
<td><p>사용자 PropertySet Public-Information 읽기</p></td>
<td><p><strong>예</strong></p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="even">
<td><p>사용자 PropertySet RTCUserSearchProperty-Set 읽기</p></td>
<td><p><strong>예</strong></p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p><strong>예</strong></p></td>
</tr>
<tr class="odd">
<td><p>사용자 PropertySet RTCPropertySet 읽기</p></td>
<td><p><strong>예</strong></p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="even">
<td><p>사용자 Property Proxy-Addresses 쓰기</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p><strong>예</strong></p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="odd">
<td><p>사용자 PropertySet RTCUserSearchProperty-Set 쓰기</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p><strong>예</strong></p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="even">
<td><p>사용자 PropertySet RTCPropertySet 쓰기</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p><strong>예</strong></p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
</tr>
<tr class="odd">
<td><p>모든 Active Directory 개체의 PropertySet DS-Replication-Get-Changes 읽기</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p><strong>예</strong></p></td>
<td><p>아니요</p></td>
</tr>
</tbody>
</table>


다음 표에는 도메인 준비가 세 개의 기본 제공 컨테이너인 사용자, 컴퓨터 및 도메인 컨트롤러에 만드는 ACE가 나열되어 있습니다. 다른 언급이 없는 경우 모든 ACE는 상속됩니다.

### <a name="aces-added-to-built-in-containers"></a>기본 제공 컨테이너에 추가 된 Ace

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
<td><p>컨테이너 읽기(상속되지 않음)</p></td>
<td><p><strong>예</strong></p></td>
<td><p><strong>예</strong></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

