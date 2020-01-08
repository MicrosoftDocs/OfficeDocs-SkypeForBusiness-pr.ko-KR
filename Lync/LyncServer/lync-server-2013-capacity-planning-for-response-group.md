---
title: 'Lync Server 2013: 응답 그룹 용량 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning for Response Group
ms:assetid: a2459a69-1f45-4f2f-bca5-d4f442708e44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412754(v=OCS.15)
ms:contentKeyID: 48184951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72f3e49806dc573a4e17bc917834deba97a74ca2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a>Lync Server 2013의 응답 그룹 용량 계획

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-29_

<div id="sectionSection0" class="section">

다음 표에서는 용량 계획 요구 사항의 기준으로 사용할 수 있는 응답 그룹 사용자 모델에 대해 설명 합니다.

<div>


> [!NOTE]  
> 다음 표의 숫자는 모든 응답 그룹 오디오 파일에 대해 16Khz, 모노, 16 비트 웨이브 (.wav) 파일을 사용 한다고 가정 합니다. Windows Media 오디오 (.wma) 등의 다른 파일 형식을 사용 하는 경우 숫자는 다를 수 있습니다.



</div>

<div>


> [!IMPORTANT]  
> 장애 복구 용량 계획의 경우 쌍으로 연결 된 풀의 각 풀은 두 풀의 모든 응답 그룹에 대 한 작업 부하를 처리할 수 있어야 한다는 점에 유의 하세요.



</div>

### <a name="response-group-user-model"></a>응답 그룹 사용자 모델

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>미터</th>
<th>엔터프라이즈 에디션 풀 (8 대의 프런트 엔드 서버 사용)</th>
<th>스탠더드 에디션 서버 당</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>초당 수신 전화</p></td>
<td><p>16</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>IVR 또는 MoH에 연결 된 동시 통화</p></td>
<td><p>480</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>동시 익명 세션 (IM 제외)</p></td>
<td><p>224</p></td>
<td><p>일까</p></td>
</tr>
<tr class="even">
<td><p>동시 익명 세션 (IM 포함)</p></td>
<td><p>64</p></td>
<td><p>20cm(8</p></td>
</tr>
<tr class="odd">
<td><p>활성 에이전트 (형식 및 비공식적인)</p></td>
<td><p>1200</p></td>
<td><p>1200</p></td>
</tr>
<tr class="even">
<td><p>헌트 그룹 수</p></td>
<td><p>400</p></td>
<td><p>400</p></td>
</tr>
<tr class="odd">
<td><p>IVR 그룹 수 (음성 인식 사용)</p></td>
<td><p>200</p></td>
<td><p>200</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

