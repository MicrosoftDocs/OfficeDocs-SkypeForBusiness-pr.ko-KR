---
title: 'Lync Server 2013: 번역 규칙'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Translation rules
ms:assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398520(v=OCS.15)
ms:contentKeyID: 48184460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22b6fbacf068f6a1a388a968989259afec81d17a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="translation-rules-in-lync-server-2013"></a>Lync Server 2013의 번역 규칙

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-05_

Lync Server 2013 Enterprise Voice에서는 역 번호 조회 (RNL)를 수행 하기 위해 모든 다이얼 문자열을 E 164 형식으로 정규화 해야 합니다. Microsoft Lync Server 2010에서 번역 규칙은 호출 된 번호에만 지원 됩니다. Microsoft Lync Server 2013의 새로운 기능은 숫자 통화에도 번역 규칙이 지원 됩니다. *트렁크 피어* (즉, 연결 된 게이트웨이, PBX (사설 지점 교환) 또는 SIP 트렁크)는 해당 번호를 지역 전화 걸기 형식으로 요구할 수 있습니다. E-164 형식의 숫자를 지역 전화 걸기 형식으로 번역 하려면 하나 이상의 번역 규칙을 정의 하 여 트렁크 피어로 라우팅하기 전에 요청 URI를 조작할 수 있습니다. 예를 들어 전화 문자열의 앞부분에서 +44를 제거하고 0144로 바꾸는 전환 규칙을 작성할 수 있습니다.

서버에서 아웃 바운드 경로 변환을 수행 하 여 전화 번호를 지역 전화 걸기 형식으로 변환 하기 위해 각각의 각 트렁크 피어에 대 한 구성 요구 사항을 줄일 수 있습니다. 특정 조정 서버 클러스터와 연결할 게이트웨이 및 게이트웨이의 수를 계획 하는 경우에는 유사한 지역 전화 걸기 요구 사항으로 트렁크 피어를 그룹화 하는 것이 유용할 수 있습니다. 이렇게 하면 필요한 번역 규칙의 수와 기록 하는 데 걸리는 시간을 줄일 수 있습니다.

<div>


> [!IMPORTANT]  
> 하나 이상의 번역 규칙을 엔터프라이즈 음성 트렁크 구성에 연결 하는 대신 트렁크 피어에서 번역 규칙을 구성할 수 있습니다. 두 규칙이 충돌할 수 있으므로 트렁크 피어에서 번역 규칙을 구성한 경우에는 번역 규칙을 엔터프라이즈 음성 트렁크 구성과 연결 하지 마세요.



</div>

<div>

## <a name="example-translation-rules"></a>예제 번역 규칙

다음 번역 규칙 예제에서는 서버에서 규칙을 개발 하 여 E. \ 164 형식의 숫자를 트렁크 피어의 로컬 형식으로 변환 하는 방법을 보여 줍니다.

번역 규칙을 구현 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 번역 규칙 정의](lync-server-2013-defining-translation-rules.md) 를 참조 하세요.


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
<th>더할 숫자</th>
<th>일치 패턴</th>
<th>변환용</th>
<th>예</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>미국 내 기존 시외 전화 통화</p>
<p>(' + ' 제거)</p></td>
<td><p>+ 1</p></td>
<td><p>정확히 12</p></td>
<td><p>1</p></td>
<td><p>0</p></td>
<td><p>^\+(1 \ d{10}) $</p></td>
<td><p>$1</p></td>
<td><p>+ 14255551010이 14255551010</p></td>
</tr>
<tr class="even">
<td><p>미국 국제 장거리 전화</p>
<p>(' + '를 제거 하 고 011을 추가 합니다.)</p></td>
<td><p>+</p></td>
<td><p>11 개 이상</p></td>
<td><p>1</p></td>
<td><p>011</p></td>
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

