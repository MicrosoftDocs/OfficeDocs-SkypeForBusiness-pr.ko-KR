---
title: 'Lync Server 2013: 응급 전화에 대한 요구 사항 정의'
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
ms.openlocfilehash: beb4b1e196a95d19a06c502cc9aeb989d6806b06
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743438"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-emergency-calls-in-lync-server-2013"></a>Lync Server 2013에서 응급 전화에 대한 요구 사항 정의

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-06-06_

Microsoft Lync Server 2013 E9-1-1 배포를 시작 하기 전에 먼저 다음 섹션에서 설명 하는 질문에 대 한 답을 얻을 수 있습니다. 수행 해야 하는 계획은 E9-1-1 솔루션 (SIP 트렁크 E9-1-1 서비스 공급자 또는 비상 위치 Id 번호 (ELIN) 게이트웨이)의 유형에 따라 달라 집니다. 다음 표에서는 이러한 각 솔루션에 대해 검토 해야 하는 계획 통합 문서의 섹션을 식별 합니다.

### <a name="planning-steps-by-type-of-e9-1-1-solution"></a>E9의 유형별 계획 단계-1-1 솔루션

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>SIP 트렁크 서비스 공급자</th>
<th>ELIN gateway</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Lync Server 2013에서 E9-1 배포의 범위 정의</a></p></td>
<td><p><a href="lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md">Lync Server 2013에서 E9-1 배포의 범위 정의</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Lync Server 2013에서 위치를 확인 하는 데 사용 되는 네트워크 요소 정의</a></p></td>
<td><p><a href="lync-server-2013-defining-the-network-elements-used-to-determine-location.md">Lync Server 2013에서 위치를 확인 하는 데 사용 되는 네트워크 요소 정의</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Lync Server 2013에서 E9에 대해 사용자 설정-1-1</a></p></td>
<td><p><a href="lync-server-2013-enabling-users-for-e9-1-1.md">Lync Server 2013에서 E9에 대해 사용자 설정-1-1</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-managing-locations-for-sip-trunk-service-providers.md">Lync Server 2013에서 SIP 트렁크 서비스 공급자의 위치 관리</a></p></td>
<td><p><a href="lync-server-2013-managing-locations-for-elin-gateways.md">Lync Server 2013의 게이트웨이에서 ELIN 대 한 위치 관리</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Lync Server 2013에서 위치를 수동으로 가져오기 위한 사용자 환경 정의</a></p></td>
<td><p><a href="lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md">Lync Server 2013에서 위치를 수동으로 가져오기 위한 사용자 환경 정의</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md">Lync Server 2013에서 E9 용 SIP 트렁크 디자인-1-1</a></p></td>
<td><p><a href="lync-server-2013-including-the-security-desk.md">Lync Server 2013에서 보안 데스크 포함</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-including-the-security-desk.md">Lync Server 2013에서 보안 데스크 포함</a></p></td>
<td><p><a href="lync-server-2013-defining-the-location-policy.md">Lync Server 2013의 위치 정책 정의</a></p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-choosing-an-e9-1-1-service-provider.md">Lync Server 2013의 E9-1-1 서비스 공급자 선택</a></p></td>
<td><p><a href="lync-server-2013-assigning-location-policy-scope.md">Lync Server 2013에서 위치 정책 범위 지정</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-defining-the-location-policy.md">Lync Server 2013의 위치 정책 정의</a></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-assigning-location-policy-scope.md">Lync Server 2013에서 위치 정책 범위 지정</a></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 E9-1 배포의 범위 정의](lync-server-2013-defining-the-scope-of-the-e9-1-1-deployment.md)

  - [Lync Server 2013에서 위치를 확인 하는 데 사용 되는 네트워크 요소 정의](lync-server-2013-defining-the-network-elements-used-to-determine-location.md)

  - [Lync Server 2013에서 E9에 대해 사용자 설정-1-1](lync-server-2013-enabling-users-for-e9-1-1.md)

  - [Lync Server 2013에서 SIP 트렁크 서비스 공급자의 위치 관리](lync-server-2013-managing-locations-for-sip-trunk-service-providers.md)

  - [Lync Server 2013의 게이트웨이에서 ELIN 대 한 위치 관리](lync-server-2013-managing-locations-for-elin-gateways.md)

  - [Lync Server 2013에서 위치를 수동으로 가져오기 위한 사용자 환경 정의](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md)

  - [Lync Server 2013에서 E9 용 SIP 트렁크 디자인-1-1](lync-server-2013-designing-the-sip-trunk-for-e9-1-1.md)

  - [Lync Server 2013에서 보안 데스크 포함](lync-server-2013-including-the-security-desk.md)

  - [Lync Server 2013의 E9-1-1 서비스 공급자 선택](lync-server-2013-choosing-an-e9-1-1-service-provider.md)

  - [Lync Server 2013의 위치 정책 정의](lync-server-2013-defining-the-location-policy.md)

  - [Lync Server 2013에서 위치 정책 범위 지정](lync-server-2013-assigning-location-policy-scope.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

