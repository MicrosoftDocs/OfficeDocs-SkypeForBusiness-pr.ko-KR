---
title: 'Lync Server 2013: 부여-CsSetupPermission을 통해 변경한 내용'
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
ms.openlocfilehash: 12c9431e413428080f72d34510cdb3879e26e7cf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a>Lync Server 2013의 부여-CsSetupPermission에서 수행한 변경 내용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-06-20_

설치를 위임 하려면 특정 Active Directory OU (조직 구성 단위)에 대 한 RTCUniversalServerAdmins 유니버설 그룹에 사용 권한을 부여 하 여 해당 OU에 있는 RTCUniversalServerAdmins 그룹의 구성원이 지정 된에 Lync Server 2013을 설치할 수 있도록 합니다. domain Admins 그룹의 구성원이 아닌 도메인

**Grant-CsSetupPermission** cmdlet을 실행하면 다음 표에 지정된 것과 같이 OU의 RTCUniversalServerAdmins 그룹에 사용 권한을 부여할 수 있습니다.

### <a name="permissions-granted-to-objects-in-the-ou"></a>OU의 개체에 부여되는 사용 권한

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>사용 권한의 적용 대상</th>
<th>부여받는 사용 권한</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>특수 액세스 권한:</p>
<ul>
<li><p>servicePrincipalName 읽기</p></li>
<li><p>servicePrincipalName 쓰기</p></li>
<li><p>트리 삭제</p></li>
<li><p>디렉터리 변경 내용 복제</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>하위 serviceConnectionPoint 개체</p></td>
<td><p>특수 액세스 권한:</p>
<ul>
<li><p>사용 권한 읽기</p></li>
<li><p>사용 권한 쓰기</p></li>
<li><p>자식 항목 만들기</p></li>
<li><p>자식 항목 삭제</p></li>
<li><p>콘텐츠 나열</p></li>
<li><p>속성 쓰기</p></li>
<li><p>속성 읽기</p></li>
<li><p>트리 삭제</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>하위 msRTCSIP-Server 개체</p></td>
<td><p>특수 액세스 권한:</p>
<ul>
<li><p>속성 쓰기</p></li>
<li><p>속성 읽기</p></li>
<li><p>트리 삭제</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>하위 msRTCSIP-WebComponents 개체</p></td>
<td><p>특수 액세스 권한:</p>
<ul>
<li><p>속성 쓰기</p></li>
<li><p>속성 읽기</p></li>
<li><p>트리 삭제</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>하위 msRTCSIP-MCU 개체</p></td>
<td><p>특수 액세스 권한:</p>
<ul>
<li><p>속성 쓰기</p></li>
<li><p>속성 읽기</p></li>
<li><p>트리 삭제</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>하위 msRTCSIP-MediationServer 개체</p></td>
<td><p>특수 액세스 권한:</p>
<ul>
<li><p>속성 쓰기</p></li>
<li><p>속성 읽기</p></li>
<li><p>트리 삭제</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>하위 msRTCSIP-ApplicationServer 개체</p></td>
<td><p>특수 액세스 권한:</p>
<ul>
<li><p>속성 쓰기</p></li>
<li><p>속성 읽기</p></li>
<li><p>트리 삭제</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>하위 msRTCSIP-ConnectionPoint 개체</p></td>
<td><p>특수 액세스 권한:</p>
<ul>
<li><p>속성 쓰기</p></li>
<li><p>속성 읽기</p></li>
<li><p>트리 삭제</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>하위 Computer 개체</p></td>
<td><p>serviceConnectionPoint에 대한 특수 액세스 권한:</p>
<ul>
<li><p>자식 개체 만들기</p></li>
<li><p>자식 개체 삭제</p></li>
<li><p>트리 삭제</p></li>
</ul>
<p>공개 정보에 대한 특수 액세스 권한:</p>
<ul>
<li><p>속성 읽기</p></li>
</ul>
<p>DNS 호스트 이름에 대한 특수 액세스 권한:</p>
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

