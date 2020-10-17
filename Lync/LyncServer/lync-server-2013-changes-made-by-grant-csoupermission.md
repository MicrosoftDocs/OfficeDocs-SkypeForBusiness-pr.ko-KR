---
title: 'Lync Server 2013: Grant-CsOUPermission에서 변경한 내용'
description: 'Lync Server 2013: 부여-CsOUPermission을 통해 변경한 내용입니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsOUPermission
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205310(v=OCS.15)
ms:contentKeyID: 48185564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10d3db0e9dde380628690bc016e2b4bd2ec85b54
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543614"
---
# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a>Lync Server 2013의 Grant-CsOUPermission에의 한 변경 사항

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-06-20_

Lync Server 2013 관리를 위임 하기 위해 포리스트 준비로 만든 RTC 유니버설 그룹의 구성원이 Domain Admins 그룹의 구성원이 아닌 Ou에 액세스할 수 있도록 지정 된 Ou (조직 구성 단위)에 사용 권한을 추가할 수 있습니다.

**Grant-CsOuPermission** cmdlet을 사용하면 다음 표에 지정된 대로 지정한 OU의 개체에 대한 사용 권한이 부여됩니다.

<div>

## <a name="granting-permission-for-user-objects"></a>User 개체에 대한 사용 권한 부여

OU의 User 개체에 대해 **Grant-CsOuPermission** cmdlet을 실행하면 다음 표에 나타난 것처럼 그룹이 사용 권한을 부여받습니다.

### <a name="permissions-granted-for-user-objects"></a>User 개체에 대해 부여되는 사용 권한

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>그룹</th>
<th>사용 권한</th>
<th>적용 대상</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>디렉터리 변경 내용 복제</p></td>
<td><p>이 개체만</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>콘텐츠 나열</p>
<p>모든 속성 읽기</p>
<p>사용 권한 읽기</p></td>
<td><p>이 개체만</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>콘텐츠 나열</p>
<p>모든 속성 읽기</p>
<p>사용 권한 읽기</p></td>
<td><p>이 개체만</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>RTCUserSearchPropertySet 읽기</p>
<p>RTCUserProvisioningPropertySet 읽기</p>
<p>RTCPropertySet 읽기</p>
<p>공용 정보 읽기</p>
<p>일반 정보 읽기</p>
<p>사용자 계정 제한 사항 읽기</p></td>
<td><p>하위 User 개체</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>RTCUserSearchPropertySet 쓰기</p>
<p>msExchUCVoiceMailSettings 쓰기</p>
<p>RTCUserProvisioningPropertySet 쓰기</p>
<p>RTCPropertySet 쓰기</p>
<p>proxyAddresses 쓰기</p></td>
<td><p>하위 User 개체</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a>Computer 개체에 대한 사용 권한 부여

OU의 Computer 개체에 대해 **Grant-CsOuPermission** cmdlet을 실행하면 다음 표에 나타난 것처럼 그룹이 사용 권한을 부여받습니다.

### <a name="permissions-granted-for-computer-objects"></a>Computer 개체에 대해 부여되는 사용 권한

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>그룹</th>
<th>사용 권한</th>
<th>적용 대상</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>디렉터리 변경 내용 복제</p></td>
<td><p>이 개체만</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>콘텐츠 나열</p>
<p>모든 속성 읽기</p>
<p>사용 권한 읽기</p></td>
<td><p>이 개체만</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>콘텐츠 나열</p>
<p>모든 속성 읽기</p>
<p>사용 권한 읽기</p></td>
<td><p>이 개체만</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>공용 정보 읽기</p>
<p>Validated-DNS-Host-Name 읽기</p></td>
<td><p>하위 Computer 개체</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>공용 정보 읽기</p>
<p>Validated-DNS-Host-Name 읽기</p></td>
<td><p>하위 Computer 개체</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a>Contact 또는 AppContact 개체에 대한 사용 권한 부여

OU의 Contact 또는 AppContact 개체에 대해 **Grant-CsOuPermission** cmdlet을 실행하면 다음 표에 나타난 것처럼 그룹이 사용 권한을 부여받습니다.

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a>Contact 또는 AppContact 개체에 대해 부여되는 사용 권한

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>그룹</th>
<th>사용 권한</th>
<th>적용 대상</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>디렉터리 변경 내용 복제</p></td>
<td><p>이 개체만</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>콘텐츠 나열</p>
<p>모든 속성 읽기</p>
<p>사용 권한 읽기</p></td>
<td><p>이 개체만</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>콘텐츠 나열</p>
<p>모든 속성 읽기</p>
<p>사용 권한 읽기</p></td>
<td><p>이 개체만</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>RTCUserSearchPropertySet 읽기</p>
<p>RTCUserProvisioningPropertySet 읽기</p>
<p>RTCPropertySet 읽기</p>
<p>공용 정보 읽기</p>
<p>일반 정보 읽기</p>
<p>개인 정보 읽기</p>
<p>사용자 계정 제한 사항 읽기</p></td>
<td><p>하위 Contact 개체</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>RTCUserSearchPropertySet 쓰기</p>
<p>otherIpPhone 쓰기</p>
<p>displayName 쓰기</p>
<p>description 쓰기</p>
<p>telephoneNumber 쓰기</p>
<p>msExchUCVoiceMailSettings 쓰기</p>
<p>RTCUserProvisioningPropertySet 쓰기</p>
<p>RTCPropertySet 쓰기</p>
<p>proxyAddresses 쓰기</p></td>
<td><p>하위 Contact 개체</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a>Device 개체에 대한 사용 권한 부여

OU의 Device 개체에 대해 **Grant-CsOuPermission** cmdlet을 실행하면 다음 표에 나타난 것처럼 그룹이 사용 권한을 부여받습니다.

### <a name="permissions-granted-for-device-objects"></a>Device 개체에 대해 부여되는 사용 권한

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>그룹</th>
<th>사용 권한</th>
<th>적용 대상</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>디렉터리 변경 내용 복제</p></td>
<td><p>이 개체만</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>콘텐츠 나열</p>
<p>모든 속성 읽기</p>
<p>사용 권한 읽기</p></td>
<td><p>이 개체만</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>콘텐츠 나열</p>
<p>모든 속성 읽기</p>
<p>사용 권한 읽기</p></td>
<td><p>이 개체만</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>RTCUserSearchPropertySet 읽기</p>
<p>RTCUserProvisioningPropertySet 읽기</p>
<p>RTCPropertySet 읽기</p>
<p>공용 정보 읽기</p>
<p>개인 정보 읽기</p>
<p>일반 정보 읽기</p>
<p>사용자 계정 제한 사항 읽기</p></td>
<td><p>하위 Contact 개체</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>자식 항목 만들기</p>
<p>자식 항목 삭제</p>
<p>트리 삭제</p></td>
<td><p>담당자</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>displayName 쓰기</p>
<p>description 쓰기</p>
<p>telephoneNumber 쓰기</p></td>
<td><p>하위 User 개체</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>RTCUserSearchPropertySet 쓰기</p>
<p>otherIpPhone 쓰기</p>
<p>displayName 쓰기</p>
<p>description 쓰기</p>
<p>telephoneNumber 쓰기</p>
<p>msExchUCVoiceMailSettings 쓰기</p>
<p>RTCUserProvisioningPropertySet 쓰기</p>
<p>RTCPropertySet 쓰기</p>
<p>proxyAddresses 쓰기</p></td>
<td><p>하위 Contact 개체</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a>InetOrgPerson 개체에 대한 사용 권한 부여

OU의 InetOrgPerson 개체에 대해 **Grant-CsOuPermission** cmdlet을 실행하면 다음 표에 나타난 것처럼 그룹이 사용 권한을 부여받습니다.

### <a name="permissions-granted-for-inetorgperson-objects"></a>InetOrgPerson 개체에 대해 부여되는 사용 권한

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>그룹</th>
<th>사용 권한</th>
<th>적용 대상</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>디렉터리 변경 내용 복제</p></td>
<td><p>이 개체만</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>콘텐츠 나열</p>
<p>모든 속성 읽기</p>
<p>사용 권한 읽기</p></td>
<td><p>이 개체만</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>콘텐츠 나열</p>
<p>모든 속성 읽기</p>
<p>사용 권한 읽기</p></td>
<td><p>이 개체만</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>RTCUserSearchPropertySet 읽기</p>
<p>RTCUserProvisioningPropertySet 읽기</p>
<p>RTCPropertySet 읽기</p>
<p>개인 정보 읽기</p>
<p>공용 정보 읽기</p>
<p>일반 정보 읽기</p>
<p>사용자 계정 제한 사항 읽기</p></td>
<td><p>하위 inetOrgPerson 개체</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>RTCUserSearchPropertySet 쓰기</p>
<p>RTCUserProvisioningPropertySet 쓰기</p>
<p>RTCPropertySet 쓰기</p>
<p>proxyAddresses 쓰기</p></td>
<td><p>하위 inetOrgPerson 개체</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

