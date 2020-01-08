---
title: 'Lync Server 2013: 그룹 통화 픽업 용량 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning for Group Call Pickup
ms:assetid: 0d654a19-6cf0-4118-903d-ec2c4e519253
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ984297(v=OCS.15)
ms:contentKeyID: 51476680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba588de723e7482039fdae4b97991080a1b92c47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a>Lync Server 2013의 그룹 통화 픽업에 대 한 용량 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-12_

<div id="sectionSection0" class="section">

다음 표에서는 용량 계획 요구 사항의 기준으로 사용할 수 있는 그룹 통화 픽업 사용자 모델에 대해 설명 합니다.

<div>


> [!IMPORTANT]  
> 그룹 통화 픽업는 통화 공원 응용 프로그램을 기반으로 합니다. 재해 복구 용량 계획을 위해 쌍으로 연결 된 풀의 각 풀은 그룹 통화 픽업을 포함 한 통화 공원 서비스의 작업량을 두 풀에서 처리할 수 있어야 한다는 점에 유의 하세요.



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
<th>미터</th>
<th>프런트 엔드 풀 단위 (프런트 엔드 서버 8 개)</th>
<th>스탠더드 에디션 서버 당</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>그룹 당 권장 되는 사용자 수</p></td>
<td><p>50</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>추천 그룹 수</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>그룹 통화 픽업에 사용할 수 있는 풀 당 최대 사용자 수</p></td>
<td><p>25000</p></td>
<td><p>3000</p></td>
</tr>
<tr class="even">
<td><p>분당 그룹 통화 픽업에 대해 사용 하도록 설정 된 총 사용자에 대 한 최대 수신 통화 속도입니다.</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>분 당 그룹 통화 픽업 트럭을 사용 하 여 사용자가 검색 한 통화의 최대 속도입니다.</p></td>
<td><p>200</p></td>
<td><p>km</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>프런트 엔드 서버를 8 개 미만으로 하는 프런트 엔드 풀의 경우 메트릭을 선형으로 계산 합니다. 예를 들어 프런트 엔드 풀에 프런트 엔드 서버가 한 개 있는 경우 최대 로드를 표에 표시 된 값의 1/8로 계산 합니다.</P>
> <LI>
> <P>풀 당 최대 사용자 수를 초과 하지 않는 한 그룹 당 권장 되는 사용자 수와 그룹 수를 늘리거나 줄일 수 있습니다. 예를 들어 그룹 통화 픽업에 대해 사용 하도록 설정 된 사용자 수가 최대 사용자 모델 (즉, 120 그룹 시간 25 명의 사용자는 그룹 통화 픽업에 대해 사용 하도록 설정 3000 되어 있음)에 포함 되어 있기 때문에 Standard Edition 서버는 그룹당 25 명의 사용자를 갖는 120 그룹을 가질 수 있습니다.</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

