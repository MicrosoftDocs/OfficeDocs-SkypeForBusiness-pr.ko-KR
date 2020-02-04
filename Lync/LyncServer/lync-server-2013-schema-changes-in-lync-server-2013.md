---
title: 'Lync Server 2013: Lync Server 2013에서 스키마 변경'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema changes in Lync Server 2013
ms:assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398944(v=OCS.15)
ms:contentKeyID: 48185575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54a3fd5f18785a649803cc6f9a0a56d7b98a2ee6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-changes-in-lync-server-2013"></a>Lync Server 2013의 스키마 변경 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-18_

Lync Server 2013를 배포 하 고 작동 하기 전에 스키마를 확장 하 여 Active Directory 도메인 서비스를 준비 해야 합니다. 스키마 확장에서는 Lync Server 2013에서 요구 하는 클래스 및 특성을 추가 합니다.

Lync Server 2013에는 몇 가지 새로운 클래스 및 특성이 필요 하며 일부 기존 클래스 및 특성을 수정 합니다. 또한 Lync Server 2013에 대 한 많은 구성 정보는 이전 버전 에서처럼 AD DS 대신 중앙 관리 저장소에 저장 됩니다. 다음 정보는 여전히 Lync Server 2013의 AD DS에 저장 되어 있습니다.

  - **스키마 확장**:
    
      - 사용자 개체 확장
    
      - 지원 되는 이전 버전과의 호환성을 유지 하기 위해 Office Communications Server 2007 및 Office Communications Server 2007 R2 클래스의 확장

<!-- end list -->

  - **데이터** (Lync Server 확장 스키마 및 기존 스키마 클래스에 저장 됨):
    
      - 사용자 SIP URI (Uniform Resource Identifier) 및 기타 사용자 설정
    
      - 응답 그룹 및 회의 수행자와 같은 응용 프로그램에 대 한 연락처 개체
    
      - 중앙 관리 저장소에 대 한 포인터
    
      - Kerberos 인증 계정 (선택적 컴퓨터 개체)

이 항목에서는 Lync Server 2013에 필요한 Active Directory 스키마 변경 사항에 대해 설명 합니다. 이전 버전의 Office Communications Server에서 도입 된 스키마 변경은 설명 하지 않습니다. 수업 목록과 해당 설명은 [Lync Server 2013의 스키마 클래스 및 설명을](lync-server-2013-schema-classes-and-descriptions.md)참조 하세요. 특성 및 설명 목록은 [Lync Server 2013의 스키마 특성 및 설명을](lync-server-2013-schema-attributes-and-descriptions.md)참조 하세요. 포함 될 수 있는 특성을 가진 클래스 목록은 [Lync Server 2013에서 클래스별 스키마 특성](lync-server-2013-schema-attributes-by-class.md)을 참조 하세요.

MsRTCSIP 접두사는 Lync Server와 관련 된 클래스 및 특성을 식별 합니다.

<div>

## <a name="new-active-directory-attributes"></a>새 Active Directory 특성

다음 표에서는 Lync Server 2013에서 추가 된 Active Directory 특성에 대해 설명 합니다.

### <a name="attributes-added-by-lync-server-2013"></a>Lync Server 2013에서 추가한 특성

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>특성</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>이 다중 값 특성에는 사용자에 게 적용 되는 보류 정책에 대 한 식별자가 저장 됩니다. 보존 정책은 보류 기간 동안 사용자의 사서함 항목을 보존 합니다. 이 특성은 Exchange 2013와 공유 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserRoutingGroupId</p></td>
<td><p>SIP 라우팅 그룹 ID입니다. 같은 그룹의 사용자가 동일한 프런트 엔드 서버에 등록 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
<td><p>이 특성은 프런트 엔드 풀에 사용 되는 미러된 SQL Server 백 엔드를 저장 하는 데 사용 됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a>수정 된 Active Directory 클래스

다음 표에서는 Lync Server 2013에서 수정 된 Active Directory 클래스에 대해 설명 합니다.

### <a name="classes-modified-by-lync-server-2013"></a>Lync Server 2013에서 수정한 클래스

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>클래스만</th>
<th>바뀌지</th>
<th>클래스 또는 특성</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>사용자</p></td>
<td><p>추가: mayContain</p>
<p>추가: mayContain</p></td>
<td><p>ProxyAddresses</p>
<p>msRTCSIP-UserRoutingGroupId</p></td>
</tr>
<tr class="even">
<td><p>Contact</p></td>
<td><p>추가: mayContain</p>
<p>추가: mayContain</p></td>
<td><p>ProxyAddresses</p>
<p>msRTCSIP-UserRoutingGroupId</p></td>
</tr>
<tr class="odd">
<td><p>메일 받는 사람</p></td>
<td><p>추가: mayContain</p></td>
<td><p>msExchUserHoldPolicies</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
<td><p>추가: mayContain</p></td>
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

