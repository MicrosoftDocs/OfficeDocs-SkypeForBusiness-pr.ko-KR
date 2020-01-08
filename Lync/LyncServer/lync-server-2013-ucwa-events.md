---
title: Lync Server 2013:로 이벤트
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UCWA events
ms:assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945621(v=OCS.15)
ms:contentKeyID: 51541461
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0671b51e5fbd4b5f072676855d9e8f5201b3e04
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983666"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a>Lync Server 2013의 일부 이벤트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-15_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013는 연락처 검색을 위해 Microsoft Exchange에 액세스 하 여 모바일 클라이언트에 대 한 현재 상태를 업데이트 하는 데 이르기까지 다양 한 용도로 통합 커뮤니케이션 웹 API (c)를 사용 합니다.

작업 동작의 레코드를 이벤트 형식 정보, 경고 및 오류로 기록 합니다. 다음 표에서는 함께 사용할 수 있는 이벤트에 대해 설명 합니다.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>이벤트 ID</th>
<th>이벤트 유형</th>
<th>요약</th>
<th>원인 및 해결 방법</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>20001</p></td>
<td><p>나타낼</p></td>
<td><p>초기화</p></td>
<td><p>해당 없음</p>
<p>해당 없음</p></td>
</tr>
<tr class="even">
<td><p>20002</p></td>
<td><p>오류</p></td>
<td><p>초기화 중에 예기치 않은 예외가 발생 했습니다.</p></td>
<td><p>초기화 하는 동안 예기치 않은 오류가 발생 했습니다.</p>
<p>연결 된 이벤트 로그 항목에서 예외 정보를 검사 하 여 가능한 원인을 확인 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>20003</p></td>
<td><p>오류</p></td>
<td><p>A;/WA에서 처리 되지 않은 예외가 발생 했습니다.</p></td>
<td><p>처리 되지 않은 예외가 발생 했습니다.</p>
<p>서버를 다시 시작 합니다. 문제가 지속 되 면 기술 지원팀에 문의 하세요.</p></td>
</tr>
<tr class="even">
<td><p>20004</p></td>
<td><p>오류</p></td>
<td><p>HD photo에 대 한 Exchange에 액세스할 수 없음</p></td>
<td><p>Exchange에 대 한 연결을 사용할 수 없습니다.</p>
<p>Exchange에 대 한 연결을 사용할 수 있는지 확인</p></td>
</tr>
<tr class="odd">
<td><p>20005</p></td>
<td><p>나타낼</p></td>
<td><p>HD photo에 대 한 Exchange 액세스 실패 복구</p></td>
<td><p>해당 없음</p></td>
</tr>
<tr class="even">
<td><p>20006</p></td>
<td><p>오류</p></td>
<td><p>연락처 검색을 위해 Exchange에 액세스할 수 없음</p></td>
<td><p>Exchange에 대 한 연결을 사용할 수 없습니다.</p>
<p>Exchange에 대 한 연결을 사용할 수 있는지 확인</p></td>
</tr>
<tr class="odd">
<td><p>20007</p></td>
<td><p>나타낼</p></td>
<td><p>Exchange에서 연락처 검색 실패에서 복구 됨</p></td>
<td><p>해당 없음</p></td>
</tr>
<tr class="even">
<td><p>20008</p></td>
<td><p>오류</p></td>
<td><p>앱 당 허용 된 현재 상태 구독 보다 더 많은 구독을 시도 합니다.</p></td>
<td><p>앱 당 허용 된 현재 상태 구독 보다 더 많은 구독을 시도 합니다.</p>
<p>클라이언트에 불필요 한 구독이 있는지 확인</p></td>
</tr>
<tr class="odd">
<td><p>20009</p></td>
<td><p>오류</p></td>
<td><p>일괄 처리당 허용 된 현재 상태 구독 보다 더 많은 구독을 시도 합니다.</p></td>
<td><p>일괄 처리당 허용 된 현재 상태 구독 보다 더 많은 구독을 시도 합니다.</p>
<p>클라이언트에 불필요 한 구독이 있는지 확인</p></td>
</tr>
<tr class="even">
<td><p>20010</p></td>
<td><p>오류</p></td>
<td><p>Inband 데이터를 검색할 수 없음</p></td>
<td><p>Inband 데이터를 검색할 수 없음</p>
<p>문제가 지속 되 면 기술 지원팀에 문의 하세요.</p></td>
</tr>
<tr class="odd">
<td><p>20011</p></td>
<td><p>오류</p></td>
<td><p>현재 상태를 구독할 수 없음</p></td>
<td><p>현재 상태를 구독할 수 없음</p>
<p>문제가 지속 되 면 기술 지원팀에 문의 하세요.</p></td>
</tr>
<tr class="even">
<td><p>20012</p></td>
<td><p>오류</p></td>
<td><p>끝점을 등록 하지 못했습니다.</p></td>
<td><p>끝점을 등록 하지 못했습니다.</p>
<p>문제가 지속 되 면 기술 지원팀에 문의 하세요.</p></td>
</tr>
<tr class="odd">
<td><p>20013</p></td>
<td><p>오류</p></td>
<td><p>메신저 대화 MCU를 사용할 수 없음</p></td>
<td><p>메신저 대화 MCU를 사용할 수 없음</p>
<p>메신저 대화 MCU 실행 중인지 확인</p></td>
</tr>
<tr class="even">
<td><p>20014</p></td>
<td><p>나타낼</p></td>
<td><p>실패에서 메신저 대화에 연결 되지 않도록 복구 됨</p></td>
<td><p>해당 없음</p></td>
</tr>
<tr class="odd">
<td><p>20015</p></td>
<td><p>오류</p></td>
<td><p>AV MCU를 사용할 수 없음</p></td>
<td><p>AV MCU를 사용할 수 없음</p>
<p>AV MCU가 실행 중인지 확인</p></td>
</tr>
<tr class="even">
<td><p>20016</p></td>
<td><p>나타낼</p></td>
<td><p>이 (가) AV MCU 연결 실패에서 복구 됨</p></td>
<td><p>해당 없음</p></td>
</tr>
<tr class="odd">
<td><p>20017</p></td>
<td><p>오류</p></td>
<td><p>MCU를 사용할 수 없음</p></td>
<td><p>MCU를 사용할 수 없음</p>
<p>MCU가 실행 중인지 확인</p></td>
</tr>
<tr class="even">
<td><p>20018</p></td>
<td><p>나타낼</p></td>
<td><p>이 (가) MCU에 연결 하지 못한 경우 복구 됨</p></td>
<td><p>해당 없음</p></td>
</tr>
<tr class="odd">
<td><p>20019</p></td>
<td><p>오류</p></td>
<td><p>데이터 MCU를 사용할 수 없음</p></td>
<td><p>데이터 MCU를 사용할 수 없음</p>
<p>데이터 MCU가 실행 중인지 확인</p></td>
</tr>
<tr class="even">
<td><p>20020</p></td>
<td><p>나타낼</p></td>
<td><p>데이터 MCU 연결에 실패 하 여 복구 되지 않음</p></td>
<td><p>해당 없음</p></td>
</tr>
<tr class="odd">
<td><p>20021</p></td>
<td><p>오류</p></td>
<td><p>메신저 대화 MCU에 참가할 수 없음</p></td>
<td><p>메신저 대화 MCU에 참가할 수 없음</p>
<p>메신저 대화 MCU 실행 중인지 확인</p></td>
</tr>
<tr class="even">
<td><p>20022</p></td>
<td><p>오류</p></td>
<td><p>AV MCU에 참가할 수 없음</p></td>
<td><p>AV MCU에 참가할 수 없음</p>
<p>AV MCU가 실행 중인지 확인</p></td>
</tr>
<tr class="odd">
<td><p>20023</p></td>
<td><p>오류</p></td>
<td><p>MCU로 참가할 수 없음</p></td>
<td><p>MCU로 참가할 수 없음</p>
<p>MCU가 실행 중인지 확인</p></td>
</tr>
<tr class="even">
<td><p>20024</p></td>
<td><p>오류</p></td>
<td><p>데이터 MCU에 참가할 수 없음</p></td>
<td><p>데이터 MCU에 참가할 수 없음</p>
<p>데이터 MCU가 실행 중인지 확인</p></td>
</tr>
<tr class="odd">
<td><p>20025</p></td>
<td><p>오류</p></td>
<td><p>사진에 대 한 active directory에 액세스할 수 없음</p></td>
<td><p>Active directory에 대 한 연결을 사용할 수 없습니다.</p>
<p>Active directory에 대 한 연결을 사용할 수 있는지 확인</p></td>
</tr>
<tr class="even">
<td><p>20026</p></td>
<td><p>나타낼</p></td>
<td><p>사진에 대 한 active directory 액세스가 실패 함에 복구 됨</p></td>
<td><p>해당 없음</p></td>
</tr>
<tr class="odd">
<td><p>20027</p></td>
<td><p>오류</p></td>
<td><p>Deserialize 할 수 없음</p></td>
<td><p>Deserialize 할 수 없음</p>
<p>문제가 지속 되 면 기술 지원팀에 문의 하세요.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

