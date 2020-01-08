---
title: 결과 해석
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0a3dc473765a67db2e09f5a56db14b1ea8a41a4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a>결과 해석

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-24_

Lync Server 2013 스트레스 및 성능 도구 (L Cperftool. exe)에는 클라이언트가 수행 하는 작업과 문제가 발생 하는지 여부를 이해 하는 데 사용할 수 있는 많은 카운터가 있습니다.

<div>

## <a name="client-counters"></a>클라이언트 카운터

실행 중인 L이라는 Cperftool의 각 인스턴스에는 별도의 카운터 인스턴스가 있습니다. 각 인스턴스는 해당 프로세스 ID로 이름을 지정 합니다.

클라이언트가 오버 로드 되 면 문제가 발생할 수 있습니다. 이러한 문제를 방지 하려면 다음을 수행 합니다.

1.  클라이언트 컴퓨터의 CPU 및 메모리 사용량을 모니터링 합니다. CPU가 90 퍼센트 이상으로 일관 되는 경우 사용자 수를 줄입니다.

2.  메모리 공간이 높으면 페이지 파일의 크기가 충분 하지 않은 경우 문제가 발생할 수 있습니다. 커밋 충전량이 컴퓨터의 한도에 도달 하 고 있지 않은지 확인 합니다. 메모리 제한을 실행 하는 경우 페이지 파일 크기를 늘리거나 사용자 수를 줄이는 것이 좋습니다.

다음 표에는 key L Cperftool 성능 카운터가 나열 되어 있습니다.

**일반 정보**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>성능 카운터</strong></th>
<th><strong>설명</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>분 내에 소요 된 시간</p></td>
<td><p>프로세스가 시작 된 이후 경과한 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p>활성 끝점</p></td>
<td><p>현재 서버에 연결 된 끝점 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>실패 한 로그온</p></td>
<td><p>끝점 로그인 실패의 총 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>로그온 시도</p></td>
<td><p>끝점 로그인 시도의 총 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>끝점 연결 끊김</p></td>
<td><p>연결이 끊어진 끝점의 총 수입니다.</p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


**현재 상태 정보**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>성능 카운터</strong></th>
<th><strong>설명</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SetPresence 상태 통화</p></td>
<td><p>현재 상태 변경 시도의 총 수입니다. 다른 유형의 현재 변경 내용에 대해서는 SetPresence 상태 (현재 상태 유형) 통화 성능 카운터를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p>NNN의 SetPresence 상태에 대 한 응답</p></td>
<td><p>서버에서 받은 총 nnn response 코드 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>GetPresence 상태 통화</p></td>
<td><p>현재 상태 요청 시도의 총 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>A GetPresence 상태에 대 한 NNN 응답</p></td>
<td><p>서버에서 받은 총 nnn response 코드 수입니다.</p></td>
</tr>
</tbody>
</table>


**주소록 서비스 정보**

이 범주에는 ABS (주소록 서비스) 파일 다운로드 및 주소록 웹 쿼리 서비스 요청을 모니터링 하는 데 사용 되는 카운터가 포함 됩니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>성능 카운터</strong></th>
<th><strong>설명</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ABS 전체/델타 파일 다운로드를 시도 했습니다.</p></td>
<td><p>시도한 전체 또는 델타 파일 다운로드 요청의 총 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>ABS 전체/델타 파일 다운로드 성공</p></td>
<td><p>시도한 전체 또는 델타 파일 다운로드 요청의 총 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>주소록 웹 쿼리 서비스 관련 카운터</p></td>
<td><p>주소록 파일 다운로드 관련 카운터입니다.</p></td>
</tr>
<tr class="even">
<td><p>ABS WS 호출 시도</p></td>
<td><p>시도한 총 주소록 웹 쿼리 서비스 요청 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>ABS WS 호출 성공</p></td>
<td><p>성공적인 응답 코드를 반환한 총 주소록 웹 쿼리 서비스 요청 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>ABS WS 호출 실패</p></td>
<td><p>오류 응답 코드를 반환한 총 주소록 웹 쿼리 서비스 요청 수입니다.</p></td>
</tr>
</tbody>
</table>


**DL (메일 그룹) 정보**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>성능 카운터</strong></th>
<th><strong>설명</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>시도한 통화</p></td>
<td><p>시도 된 DLX (메일 그룹 확장) 웹 서비스 요청의 총 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>통화 성공</p></td>
<td><p>성공적인 응답 코드를 반환한 총 DLX 웹 서비스 요청 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>통화 실패</p></td>
<td><p>오류 응답 코드를 반환 하는 DLX 웹 서비스 요청의 총 수입니다.</p></td>
</tr>
</tbody>
</table>


**VoIP 기본 정보**

다음 시나리오를 사용 하는 경우 중재 서버, A/V 회의 서버, Edge 서버, 응답 그룹 응용 프로그램, 회의 자동 전화 교환 등의 호출을 포함 하 여 모든 VoIP (Voice over IP) 통화에 대 한 번호를 아래에 나열 된 성능 카운터를 보고 합니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>성능 카운터</strong></th>
<th><strong>설명</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>통화 활성</p></td>
<td><p>현재 진행 중인 총 수신/발신 음성 통화 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>통화가 종료 됨</p></td>
<td><p>이미 종료 된 수신/발신 음성 통화의 총 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>통화가 거절 됨</p></td>
<td><p>거절 된 총 음성 통화 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>수신/발신 전화 시도</p></td>
<td><p>시도한 총 수신/발신 음성 통화 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>수신/발신 통화가 설정 됨</p></td>
<td><p>설정 된 수신/발신 음성 통화의 총 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>받은 통화 NNN</p></td>
<td><p>서버에서 받은 총 nnn response 코드 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>VoIP 통과 율 (%)</p></td>
<td><p>총 통화/총 통화를 시도 했습니다.</p></td>
</tr>
</tbody>
</table>


**응답 그룹 서비스 통화 정보**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>성능 카운터</strong></th>
<th><strong>설명</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>통화 활성</p></td>
<td><p>응답 그룹 응용 프로그램에 대 한 총 활성 통화 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>시도한 통화</p></td>
<td><p>시도한 총 통화 수입니다.</p></td>
</tr>
</tbody>
</table>


**인스턴트 메시지 (IM) 통화 정보**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>성능 카운터</strong></th>
<th><strong>설명</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>통화 활성</p></td>
<td><p>진행 중인 수신/발신 인스턴트 메시징 통화의 총 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>통화가 종료 됨</p></td>
<td><p>이미 종료 된 수신/발신 인스턴트 메시징 전화의 총 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>받은 통화 NNN</p></td>
<td><p>서버에서 받은 총 nnn response 코드 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>수신/전송 된 IM 메시지</p></td>
<td><p>모든 세션에 대해 수신 또는 전송 된 총 메시지 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>수신/발신 전화 시도</p></td>
<td><p>시도한 총 수신/발신 인스턴트 메시징 통화 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>수신/발신 통화가 설정 됨</p></td>
<td><p>설정 된 수신/발신 인스턴트 메시지 총 통화 수입니다.</p></td>
</tr>
</tbody>
</table>


**앱 공유 통화 정보**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>성능 카운터</strong></th>
<th><strong>설명</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>통화 활성</p></td>
<td><p>진행 중인 수신/발신 응용 프로그램 공유 통화의 총 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>통화가 종료 됨</p></td>
<td><p>이미 종료 된 수신/발신 응용 프로그램 공유 전화의 총 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>받은 통화 NNN</p></td>
<td><p>서버에서 받은 총 nnn response 코드 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>수신/발신 전화 시도</p></td>
<td><p>시도한 총 수신/발신 응용 프로그램 공유 통화 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>수신/발신 통화가 설정 됨</p></td>
<td><p>설정 된 수신/발신 응용 프로그램 공유 통화의 총 수입니다.</p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


**통화 정보를 ca**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>성능 카운터</strong></th>
<th><strong>설명</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>통화 활성</p></td>
<td><p>현재 진행 중인 수신/송신 공공 전화망 (PSTN) 통화의 총 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>통화가 종료 됨</p></td>
<td><p>이미 종료 된 수신/송신 PSTN 호출의 총 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>수신/발신 전화 시도</p></td>
<td><p>시도한 총 수신/송신 PSTN 통화 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>수신/발신 통화가 설정 됨</p></td>
<td><p>설정 된 수신/발신 PSTN 통화의 총 수입니다.</p></td>
</tr>
</tbody>
</table>


**컨퍼런스 정보**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>성능 카운터</strong></th>
<th><strong>설명</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>활성 인스턴트 메시지 회의</p></td>
<td><p>진행 중인 인스턴트 메시지 회의 총 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>활성 오디오/비디오 회의</p></td>
<td><p>진행 중인 총 오디오/비디오 (A/V) 회의 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>활성 응용 프로그램 공유 회의</p></td>
<td><p>진행 중인 응용 프로그램 공유 컨퍼런스의 총 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>참가자 수</p></td>
<td><p>현재 컨퍼런스에 연결 된 총 참가자 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>컨퍼런스 일정 실패</p></td>
<td><p>회의를 예약 하려고 시도 하는 동안 발생 한 총 실패 횟수입니다.</p></td>
</tr>
<tr class="even">
<td><p>컨퍼런스 참가 실패</p></td>
<td><p>회의에 연결 하려고 시도 하는 동안 발생 한 총 오류 수입니다.</p></td>
</tr>
</tbody>
</table>


**A/WA 클라이언트 카운터**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>성능 카운터</strong></th>
<th><strong>설명</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>성공한 IMMCU 조인의 총 수입니다.</p></td>
<td><p>참가 한 총 인스턴트 메시징 컨퍼런스 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>성공한 DMCU 조인의 총 수입니다.</p></td>
<td><p>참가 한 총 A/V 회의 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

