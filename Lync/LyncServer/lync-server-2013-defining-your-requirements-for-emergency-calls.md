---
title: 'Lync Server 2013: 긴급 통화에 대 한 요구 사항 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for emergency calls
ms:assetid: 5c12b517-9be6-41d0-83e2-11c78793620c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398404(v=OCS.15)
ms:contentKeyID: 48184276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4455e7072e6bdb25fb2b2bc0cd4e7bc39f1f05d1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151388"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-emergency-calls-in-lync-server-2013"></a>Lync Server 2013의 응급 전화에 대 한 요구 사항 정의

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-06-06_

Microsoft Lync Server 2013 E9-1-1 배포를 시작 하기 전에 먼저 다음 섹션에서 설명 하는 질문에 대 한 답을 얻을 수 있습니다. 수행 해야 하는 계획은 배포 하도록 선택한 E9-1-1 솔루션, SIP 트렁크 E9-1-1 서비스 공급자 또는 ELIN (응급 위치 식별 번호) 게이트웨이의 유형에 따라 달라 집니다. 다음 표에서는이 계획 통합 문서에서 각 솔루션에 대해 검토 해야 하는 섹션을 보여 줍니다.

### <a name="planning-steps-by-type-of-e9-1-1-solution"></a>E9-1-1 솔루션 유형별 계획 단계

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>SIP 트렁크 서비스 공급자</th>
<th>ELIN 게이트웨이</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Lync Server 2013에서 E9-1-1 배포 범위 정의</a></p></td>
<td><p><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Lync Server 2013에서 E9-1-1 배포 범위 정의</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Lync Server 2013에서 위치를 확인 하는 데 사용 되는 네트워크 요소 정의</a></p></td>
<td><p><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Lync Server 2013에서 위치를 확인 하는 데 사용 되는 네트워크 요소 정의</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Lync Server 2013에서 E9-1-1에 대해 사용자를 사용 하도록 설정</a></p></td>
<td><p><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Lync Server 2013에서 E9-1-1에 대해 사용자를 사용 하도록 설정</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Lync Server 2013에서 SIP 트렁크 서비스 공급자 위치 관리</a></p></td>
<td><p><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Lync Server 2013의 ELIN 게이트웨이 위치 관리</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Lync Server 2013에서 위치를 수동으로 가져오기 위한 사용자 환경 정의</a></p></td>
<td><p><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Lync Server 2013에서 위치를 수동으로 가져오기 위한 사용자 환경 정의</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Lync Server 2013에서 E9-1-1에 대 한 SIP 트렁크 디자인</a></p></td>
<td><p><a href="lync-server-2013-including-the-security-desk.md">Lync Server 2013의 보안 센터 포함</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-including-the-security-desk.md">Lync Server 2013의 보안 센터 포함</a></p></td>
<td><p><a href="lync-server-2013-defining-the-location-policy.md">Lync Server 2013에 대 한 위치 정책 정의</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Lync Server 2013 용 E9-1-1 서비스 공급자 선택</a></p></td>
<td><p><a href="lync-server-2013-assigning-location-policy-scope.md">Lync Server 2013에서 위치 정책 범위 할당</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-location-policy.md">Lync Server 2013에 대 한 위치 정책 정의</a></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-assigning-location-policy-scope.md">Lync Server 2013에서 위치 정책 범위 할당</a></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 E9-1-1 배포 범위 정의](lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md)

  - [Lync Server 2013에서 위치를 확인 하는 데 사용 되는 네트워크 요소 정의](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)

  - [Lync Server 2013에서 E9-1-1에 대해 사용자를 사용 하도록 설정](lync-server-2013-enabling-users-for-e9-1-1.md)

  - [Lync Server 2013에서 SIP 트렁크 서비스 공급자 위치 관리](lync-server-2013-managing-locations-for-sip-trunk-service-providers.md)

  - [Lync Server 2013의 ELIN 게이트웨이 위치 관리](lync-server-2013-managing-locations-for-elin-gateways.md)

  - [Lync Server 2013에서 위치를 수동으로 가져오기 위한 사용자 환경 정의](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)

  - [Lync Server 2013에서 E9-1-1에 대 한 SIP 트렁크 디자인](lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md)

  - [Lync Server 2013의 보안 센터 포함](lync-server-2013-including-the-security-desk.md)

  - [Lync Server 2013 용 E9-1-1 서비스 공급자 선택](lync-server-2013-choosing-an-e9-1-1-service-provider.md)

  - [Lync Server 2013에 대 한 위치 정책 정의](lync-server-2013-defining-the-location-policy.md)

  - [Lync Server 2013에서 위치 정책 범위 할당](lync-server-2013-assigning-location-policy-scope.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

