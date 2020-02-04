---
title: 'Lync Server 2013: 권한 부여-CsSetupPermission에의 한 변경 내용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsSetupPermission
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205250(v=OCS.15)
ms:contentKeyID: 48185360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d82b896f1d6d1da1184bfa61d7352c9b4803a03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742358"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a>Lync Server 2013의 허용-Cssetupsetuppermission에의 한 변경 내용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-06-20_

설치를 위임 하려면 특정 Active Directory OU (조직 구성 단위)에 대 한 RTCUniversalServerAdmins 유니버설 그룹에 대 한 사용 권한을 부여 하 여 해당 OU에 있는 RTCUniversalServerAdmins 그룹의 구성원이 지정 된 사용자의 Lync Server 2013을 설치할 수 있도록 합니다. 도메인 관리자 그룹의 구성원이 되지 않고 도메인

**부여-CsSetupPermission** cmdlet은 다음 표에 지정 된 대로 OU에 대 한 RTCUniversalServerAdmins 그룹 권한을 부여 합니다.

### <a name="permissions-granted-to-objects-in-the-ou"></a>OU의 개체에 부여 된 사용 권한

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>사용 권한은 다음에 적용 됩니다.</th>
<th>부여 된 사용 권한은 다음과 같습니다.</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>특별 액세스:</p>
<ul>
<li><p>ServicePrincipalName 읽기</p></li>
<li><p>ServicePrincipalName 쓰기</p></li>
<li><p>트리 삭제</p></li>
<li><p>디렉터리 변경 내용 복제</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>하위 항목 serviceConnectionPoint 개체</p></td>
<td><p>특별 액세스:</p>
<ul>
<li><p>읽기 권한</p></li>
<li><p>쓰기 권한</p></li>
<li><p>하위 항목 만들기</p></li>
<li><p>하위 항목 삭제</p></li>
<li><p>내용 목록</p></li>
<li><p>쓰기 속성</p></li>
<li><p>속성 읽기</p></li>
<li><p>트리 삭제</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>하위 항목 msRTCSIP-서버 개체</p></td>
<td><p>특별 액세스:</p>
<ul>
<li><p>쓰기 속성</p></li>
<li><p>속성 읽기</p></li>
<li><p>트리 삭제</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>하위 msRTCSIP-WebComponents 개체</p></td>
<td><p>특별 액세스:</p>
<ul>
<li><p>쓰기 속성</p></li>
<li><p>속성 읽기</p></li>
<li><p>트리 삭제</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>하위 항목 msRTCSIP-MCU 개체</p></td>
<td><p>특별 액세스:</p>
<ul>
<li><p>쓰기 속성</p></li>
<li><p>속성 읽기</p></li>
<li><p>트리 삭제</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>하위 항목 msRTCSIP-MediationServer 개체</p></td>
<td><p>특별 액세스:</p>
<ul>
<li><p>쓰기 속성</p></li>
<li><p>속성 읽기</p></li>
<li><p>트리 삭제</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>하위 항목 msRTCSIP-ApplicationServer 개체</p></td>
<td><p>특별 액세스:</p>
<ul>
<li><p>쓰기 속성</p></li>
<li><p>속성 읽기</p></li>
<li><p>트리 삭제</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>하위 msRTCSIP-ConnectionPoint 개체</p></td>
<td><p>특별 액세스:</p>
<ul>
<li><p>쓰기 속성</p></li>
<li><p>속성 읽기</p></li>
<li><p>트리 삭제</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>하위 컴퓨터 개체</p></td>
<td><p>ServiceConnectionPoint에 대 한 특수 액세스:</p>
<ul>
<li><p>자식 개체 만들기</p></li>
<li><p>자식 개체 삭제</p></li>
<li><p>트리 삭제</p></li>
</ul>
<p>공개 정보에 대 한 특별 액세스:</p>
<ul>
<li><p>속성 읽기</p></li>
</ul>
<p>DNS 호스트 이름에 대 한 특수 액세스:</p>
<ul>
<li><p>속성 읽기</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

