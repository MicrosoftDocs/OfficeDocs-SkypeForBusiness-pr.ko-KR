---
title: 'Lync Server 2013: 요청-CsOUPermission에의 한 변경 내용'
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
ms.openlocfilehash: 9056753e57f57b131a05d13eb2862611ba34f966
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a>Lync Server 2013의 허용-CsOUPermission에의 한 변경 내용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-06-20_

Lync Server 2013 관리를 위임 하려면 포리스트 준비로 만든 RTC 유니버설 그룹의 구성원이 도메인 관리자 그룹의 구성원이 아닌 Ou에 액세스할 수 있도록 지정 된 조직 구성 단위 (Ou)에 대 한 사용 권한을 추가 하면 됩니다.

**허용-CsOuPermission** cmdlet은 다음 표에 지정 된 대로 지정 된 OU의 개체에 대 한 사용 권한을 부여 합니다.

<div>

## <a name="granting-permission-for-user-objects"></a>사용자 개체에 대 한 사용 권한 부여

OU의 사용자 개체에 대해 **허용-CsOuPermission** cmdlet을 실행 하는 경우 그룹에는 다음 표에 나와 있는 것 처럼 권한이 부여 됩니다.

### <a name="permissions-granted-for-user-objects"></a>사용자 개체에 부여 된 사용 권한

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>그룹과</th>
<th>있는</th>
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
<td><p>내용 목록</p>
<p>모든 속성 읽기</p>
<p>읽기 권한</p></td>
<td><p>이 개체만</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>내용 목록</p>
<p>모든 속성 읽기</p>
<p>읽기 권한</p></td>
<td><p>이 개체만</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>RTCUserSearchPropertySet 읽기</p>
<p>RTCUserProvisioningPropertySet 읽기</p>
<p>RTCPropertySet 읽기</p>
<p>공개 정보 읽기</p>
<p>일반 정보 읽기</p>
<p>사용자 계정 제한 사항 읽기</p></td>
<td><p>하위 사용자 개체</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>RTCUserSearchPropertySet 쓰기</p>
<p>MsExchUCVoiceMailSettings 쓰기</p>
<p>RTCUserProvisioningPropertySet 쓰기</p>
<p>RTCPropertySet 쓰기</p>
<p>ProxyAddresses 쓰기</p></td>
<td><p>하위 사용자 개체</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a>컴퓨터 개체에 대 한 사용 권한 부여

OU의 컴퓨터 개체에 대해 **허용-CsOuPermission** cmdlet을 실행 하는 경우 그룹에는 다음 표에 나와 있는 것 처럼 권한이 부여 됩니다.

### <a name="permissions-granted-for-computer-objects"></a>컴퓨터 개체에 부여 된 사용 권한

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>그룹과</th>
<th>있는</th>
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
<td><p>내용 목록</p>
<p>모든 속성 읽기</p>
<p>읽기 권한</p></td>
<td><p>이 개체만</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>내용 목록</p>
<p>모든 속성 읽기</p>
<p>읽기 권한</p></td>
<td><p>이 개체만</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>공개 정보 읽기</p>
<p>읽음 확인 됨-DNS-호스트 이름</p></td>
<td><p>하위 컴퓨터 개체</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>공개 정보 읽기</p>
<p>읽음 확인 됨-DNS-호스트 이름</p></td>
<td><p>하위 컴퓨터 개체</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a>연락처 또는 AppContact 개체에 대 한 사용 권한 부여

OU의 Contact objects 또는 AppContact 개체에 대해 **허용-CsOuPermission** cmdlet을 실행 하면 다음 표에 표시 된 것 처럼 그룹에 권한이 부여 됩니다.

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a>연락처 또는 AppContact 개체에 부여 된 사용 권한

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>그룹과</th>
<th>있는</th>
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
<td><p>내용 목록</p>
<p>모든 속성 읽기</p>
<p>읽기 권한</p></td>
<td><p>이 개체만</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>내용 목록</p>
<p>모든 속성 읽기</p>
<p>읽기 권한</p></td>
<td><p>이 개체만</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>RTCUserSearchPropertySet 읽기</p>
<p>RTCUserProvisioningPropertySet 읽기</p>
<p>RTCPropertySet 읽기</p>
<p>공개 정보 읽기</p>
<p>일반 정보 읽기</p>
<p>개인 정보 읽기</p>
<p>사용자 계정 제한 사항 읽기</p></td>
<td><p>하위 연락처 개체</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>RTCUserSearchPropertySet 쓰기</p>
<p>OtherIpPhone 작성</p>
<p>DisplayName 쓰기</p>
<p>설명 쓰기</p>
<p>TelephoneNumber 쓰기</p>
<p>MsExchUCVoiceMailSettings 쓰기</p>
<p>RTCUserProvisioningPropertySet 쓰기</p>
<p>RTCPropertySet 쓰기</p>
<p>ProxyAddresses 쓰기</p></td>
<td><p>하위 연락처 개체</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a>디바이스 개체에 대 한 사용 권한 부여

OU의 디바이스 개체에 대해 **허용-CsOuPermission** cmdlet을 실행 하면 다음 표에 표시 된 대로 그룹에 대 한 권한이 부여 됩니다.

### <a name="permissions-granted-for-device-objects"></a>장치 개체에 부여 된 사용 권한

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>그룹과</th>
<th>있는</th>
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
<td><p>내용 목록</p>
<p>모든 속성 읽기</p>
<p>읽기 권한</p></td>
<td><p>이 개체만</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>내용 목록</p>
<p>모든 속성 읽기</p>
<p>읽기 권한</p></td>
<td><p>이 개체만</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>RTCUserSearchPropertySet 읽기</p>
<p>RTCUserProvisioningPropertySet 읽기</p>
<p>RTCPropertySet 읽기</p>
<p>공개 정보 읽기</p>
<p>개인 정보 읽기</p>
<p>일반 정보 읽기</p>
<p>사용자 계정 제한 사항 읽기</p></td>
<td><p>하위 연락처 개체</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>하위 항목 만들기</p>
<p>하위 항목 삭제</p>
<p>트리 삭제</p></td>
<td><p>Contact</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>DisplayName 쓰기</p>
<p>설명 쓰기</p>
<p>TelephoneNumber 쓰기</p></td>
<td><p>하위 사용자 개체</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>RTCUserSearchPropertySet 쓰기</p>
<p>OtherIpPhone 작성</p>
<p>DisplayName 쓰기</p>
<p>설명 쓰기</p>
<p>TelephoneNumber 쓰기</p>
<p>MsExchUCVoiceMailSettings 쓰기</p>
<p>RTCUserProvisioningPropertySet 쓰기</p>
<p>RTCPropertySet 쓰기</p>
<p>ProxyAddresses 쓰기</p></td>
<td><p>하위 연락처 개체</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a>InetOrgPerson 개체에 대 한 사용 권한 부여

OU의 InetOrgPerson 개체에 대해 **허용-CsOuPermission** cmdlet을 실행 하는 경우 그룹에는 다음 표에 나와 있는 것 처럼 권한이 부여 됩니다.

### <a name="permissions-granted-for-inetorgperson-objects"></a>InetOrgPerson 개체에 부여 된 사용 권한

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>그룹과</th>
<th>있는</th>
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
<td><p>내용 목록</p>
<p>모든 속성 읽기</p>
<p>읽기 권한</p></td>
<td><p>이 개체만</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>내용 목록</p>
<p>모든 속성 읽기</p>
<p>읽기 권한</p></td>
<td><p>이 개체만</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>RTCUserSearchPropertySet 읽기</p>
<p>RTCUserProvisioningPropertySet 읽기</p>
<p>RTCPropertySet 읽기</p>
<p>개인 정보 읽기</p>
<p>공개 정보 읽기</p>
<p>일반 정보 읽기</p>
<p>사용자 계정 제한 사항 읽기</p></td>
<td><p>하위 항목 inetOrgPerson 개체</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>RTCUserSearchPropertySet 쓰기</p>
<p>RTCUserProvisioningPropertySet 쓰기</p>
<p>RTCPropertySet 쓰기</p>
<p>ProxyAddresses 쓰기</p></td>
<td><p>하위 항목 inetOrgPerson 개체</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

