---
title: 'Lync Server 2013: 그룹 통화 픽업 용량 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Group Call Pickup
ms:assetid: 0d654a19-6cf0-4118-903d-ec2c4e519253
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ984297(v=OCS.15)
ms:contentKeyID: 51476680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 403a00887cb64b33075f173499e855eb8783bb20
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036538"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a>Lync Server 2013의 그룹 통화 픽업 용량 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-12_

<div id="sectionSection0" class="section">

다음 표에서는 용량 계획 요구 사항의 기반으로 사용할 수 있는 그룹 통화 픽업 사용자 모델에 대해 설명 합니다.

<div>


> [!IMPORTANT]  
> 그룹 통화 픽업는 통화 대기 응용 프로그램을 기반으로 합니다. 재해 복구 용량 계획을 위해 연결 된 풀의 각 풀은 두 풀에서 그룹 호출 픽업을 포함 하 여 통화 대기 서비스의 작업을 처리할 수 있어야 합니다.



</div>

### <a name="group-call-pickup-user-model"></a>그룹 통화 픽업 사용자 모델

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>192.168.1.0</th>
<th>프런트 엔드 풀 당 (8 개의 프런트 엔드 서버 포함)</th>
<th>Standard Edition Server별</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>그룹 당 추천 사용자 수</p></td>
<td><p>50</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>권장 그룹 수</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>그룹 통화 픽업에 사용 하도록 설정 된 풀 당 최대 사용자 수</p></td>
<td><p>25,000</p></td>
<td><p>3000</p></td>
</tr>
<tr class="even">
<td><p>분당 그룹 통화 픽업 트럭에 대해 사용 하도록 설정 된 총 사용자에 대 한 수신 전화의 최대 속도입니다.</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>분당 그룹 호출 픽업가 있는 사용자가 검색 한 통화의 최대 속도입니다.</p></td>
<td><p>200</p></td>
<td><p>25@@</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>프런트 엔드 서버가 8 개 미만인 프런트 엔드 풀의 경우 메트릭을 선형으로 계산 합니다. 예를 들어 프런트 엔드 풀에 프런트 엔드 서버가 하나인 경우 표에 표시 된 값의 최대 부하를 1/8으로 계산 합니다.</P>
> <LI>
> <P>풀 당 최대 사용자 수를 초과 하지 않을 경우 그룹 당 권장 되는 사용자 수와 그룹 수를 늘리거나 낮출 수 있습니다. 예를 들어 그룹 통화 픽업에 사용 하도록 설정 된 사용자 수가 사용자 모델 최대 (즉, 120 그룹 시간 25 명의 사용자는 그룹 통화 픽업에 사용 하도록 설정 3000 된 경우) 이므로 Standard Edition 서버는 그룹 당 사용자가 25 명 인 120 그룹을 포함할 수 있습니다.</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

