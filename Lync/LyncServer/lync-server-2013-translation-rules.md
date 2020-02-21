---
title: 'Lync Server 2013: 변환 규칙'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Translation rules
ms:assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398520(v=OCS.15)
ms:contentKeyID: 48184460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1576b9c0c7286150c62f1491960bf9beef5d700
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="translation-rules-in-lync-server-2013"></a>Lync Server 2013의 변환 규칙

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-05_

Lync Server 2013 Enterprise Voice를 사용 하려면 RNL (역방향 번호 조회)를 수행할 목적으로 모든 다이얼 문자열을 E. 164 형식으로 정규화 해야 합니다. Microsoft Lync Server 2010에서 변환 규칙은 호출 된 번호에 대해서만 지원 됩니다. Microsoft Lync Server 2013의 새로운 기능은 통화 번호에 대해서도 변환 규칙을 지원 합니다. *트렁크 피어* (연결 된 게이트웨이, PBX (private branch exchange) 또는 SIP 트렁크)가 해당 번호를 로컬 전화 걸기 형식으로 지정 해야 할 수 있습니다. E. 164 형식의 숫자를 로컬 전화 걸기 형식으로 변환 하려면이를 트렁크 피어로 라우팅하기 전에 요청 URI를 조작 하는 하나 이상의 변환 규칙을 정의할 수 있습니다. 예를 들어 전화 걸기 문자열의 시작 부분에서 +44를 제거하고 대신 0144를 넣는 변환 규칙을 작성할 수 있습니다.

서버에서 아웃 바운드 경로 변환을 수행 하 여 전화 번호를 로컬 전화 걸기 형식으로 변환 하기 위해 각 개별 트렁크 피어에서 구성 요구 사항을 줄일 수 있습니다. 특정 중재 서버 클러스터와 연결할 게이트웨이 및 게이트웨이 개수를 계획할 때는 유사한 로컬 전화 걸기 요구 사항을 적용 하 여 트렁크 피어를 그룹화 하는 것이 유용할 수 있습니다. 이를 통해 필요한 변환 규칙의 수와이를 작성 하는 데 소요 되는 시간을 줄일 수 있습니다.

<div>


> [!IMPORTANT]  
> 트렁크 피어에서 변환 규칙을 구성 하는 대신 하나 이상의 변환 규칙을 엔터프라이즈 음성 트렁크 구성에 연결 하는 것이 사용 되어야 합니다. 두 규칙이 충돌할 수 있으므로 트렁크 피어에서 변환 규칙을 구성한 경우에는 변환 규칙을 엔터프라이즈 음성 트렁크 구성과 연결 하지 마십시오.



</div>

<div>

## <a name="example-translation-rules"></a>예제 변환 규칙

다음 변환 규칙의 예에서는 서버에서 규칙을 개발 하 여 E. 164 형식의 번호를 트렁크 피어의 로컬 형식으로 변환 하는 방법을 보여 줍니다.

변환 규칙을 구현 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 변환 규칙 정의](lync-server-2013-defining-translation-rules.md) 를 참조 하십시오.


<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th>설명</th>
<th>시작 번호</th>
<th>Content-length</th>
<th>제거할 숫자</th>
<th>추가할 숫자</th>
<th>일치 패턴</th>
<th>Translation</th>
<th>예제</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>미국 내에서의 일반적인 시외 전화 걸기</p>
<p>(' + ' 제거)</p></td>
<td><p>+ 1</p></td>
<td><p>정확히 12 개</p></td>
<td><p>개</p></td>
<td><p>개</p></td>
<td><p>^\+(1 \ d{10}) $</p></td>
<td><p>$1</p></td>
<td><p>+ 14255551010이 14255551010</p></td>
</tr>
<tr class="even">
<td><p>미국 국제 장거리 전화 걸기</p>
<p>(' + ' 제거 및 011 추가)</p></td>
<td><p>+</p></td>
<td><p>11 이상</p></td>
<td><p>개</p></td>
<td><p>이진수</p></td>
<td><p>^\+(\d{9}\d +) $</p></td>
<td><p>011 $1</p></td>
<td><p>+ 441235551010이 011441235551010</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

