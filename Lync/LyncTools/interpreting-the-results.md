---
title: 결과 해석
description: 결과 해석
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8342a1ec1e15e42852fc5293f87342e98587a60
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565344"
---
# <a name="interpreting-the-results"></a>결과 해석

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-24_

Lync Server 2013 스트레스 및 성능 도구 (LyncPerfTool.exe)에는 클라이언트가 수행 하는 작업과 문제가 발생 하는지 여부를 이해 하는 데 사용할 수 있는 많은 카운터가 있습니다.

<div>

## <a name="client-counters"></a>클라이언트 카운터

실행 중인 각 LyncPerfTool.exe 인스턴스에는 별도의 카운터 인스턴스가 있습니다. 각 인스턴스의 이름은 해당 프로세스 ID에 의해 지정 됩니다.

클라이언트가 오버 로드 되 면 문제가 발생할 수 있습니다. 이러한 문제를 방지 하려면 다음을 수행 합니다.

1.  클라이언트 컴퓨터의 CPU 및 메모리 사용량을 모니터링 합니다. CPU가 지속적으로 90% 이상 지속 되 면 사용자 수를 줄입니다.

2.  메모리 공간이 높으면 페이지 파일 크기가 충분 하지 않은 경우 문제가 발생할 수 있습니다. 컴퓨터에서 커밋 충전량이 한도를 적중 하지 않는지 확인 합니다. 메모리 제한으로 실행 하는 경우에는 페이지 파일 크기를 늘리거나 사용자 수를 줄이는 것이 좋습니다.

다음 표에서는 키 LyncPerfTool 성능 카운터를 나열 합니다.

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
<td><p>소요 시간 (분)</p></td>
<td><p>프로세스를 시작한 후 소요 된 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p>활성 끝점</p></td>
<td><p>현재 서버에 연결 되어 있는 끝점 수입니다.</p></td>
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
<td><p>끝점 연결 끊기</p></td>
<td><p>연결을 끊은 총 끝점 수입니다.</p></td>
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
<td><p>현재 상태 변경 시도 횟수입니다. 다른 유형의 현재 변경 내용은 SetPresence 상태 (현재 유형) 통화 성능 카운터를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p>NNN 현재 상태에 대 한 응답</p></td>
<td><p>서버에서 받은 총 nnn 응답 코드 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>GetPresence 상태 통화</p></td>
<td><p>현재 상태 요청 시도의 총 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>NNN-GetPresence 상태에 대 한 응답</p></td>
<td><p>서버에서 받은 총 nnn 응답 코드 수입니다.</p></td>
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
<td><p>ABS 전체/델타 파일 다운로드 시도</p></td>
<td><p>시도한 총 전체 또는 델타 파일 다운로드 요청 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>ABS 전체/델타 파일 다운로드 성공</p></td>
<td><p>시도한 총 전체 또는 델타 파일 다운로드 요청 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>주소록 웹 쿼리 서비스 관련 카운터</p></td>
<td><p>주소록 파일 다운로드 관련 카운터입니다.</p></td>
</tr>
<tr class="even">
<td><p>ABS WS 호출이 시도 됨</p></td>
<td><p>시도한 총 주소록 웹 쿼리 서비스 요청 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>ABS WS 호출이 성공 함</p></td>
<td><p>성공적인 응답 코드를 반환한 총 주소록 웹 쿼리 서비스 요청 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>ABS WS 호출이 실패 함</p></td>
<td><p>오류 응답 코드를 반환한 총 주소록 웹 쿼리 서비스 요청 수입니다.</p></td>
</tr>
</tbody>
</table>


**메일 그룹 (DL) 정보**


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
<td><p>시도 된 DLX (총 메일 그룹 확장) 웹 서비스 요청 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>통화 성공</p></td>
<td><p>성공적인 응답 코드를 반환한 총 DLX web service 요청 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>통화 실패</p></td>
<td><p>오류 응답 코드를 반환한 총 DLX 웹 서비스 요청 수입니다.</p></td>
</tr>
</tbody>
</table>


**VoIP 기본 정보**

이 시나리오를 사용 하도록 설정 하는 경우 중재 서버, A/V 회의 서버,에 지 서버, 응답 그룹 응용 프로그램 및 전화 회의 자동 전화 교환에 대 한 호출을 비롯 하 여 모든 VoIP (Voice over IP) 통화에 대 한 보고서 번호 아래에 나열 된 성능 카운터


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
<td><p>현재 진행 중인 수신/발신 음성 통화의 총 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>통화가 종료 됨</p></td>
<td><p>이미 종료 된 수신/발신 음성 통화의 총 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>통화가 거절 됨</p></td>
<td><p>거절 된 들어오는 음성 통화의 총 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>수신/발신 전화 시도</p></td>
<td><p>시도 된 수신/발신 음성 통화의 총 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>수신/발신 전화</p></td>
<td><p>설정 된 수신/발신 음성 통화의 총 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>호출 되는 NNN</p></td>
<td><p>서버에서 받은 총 nnn 응답 코드 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>VoIP 통과 속도 (%)</p></td>
<td><p>총 통화 횟수 설정/총 통화를 시도 했습니다.</p></td>
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
<td><p>응답 그룹 응용 프로그램에 대 한 총 활성 호출 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>시도한 통화</p></td>
<td><p>시도한 총 통화 수입니다.</p></td>
</tr>
</tbody>
</table>


**IM (인스턴트 메시징) 통화 정보**


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
<td><p>진행 된 수신/발신 인스턴트 메시징 통화의 총 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>통화가 종료 됨</p></td>
<td><p>이미 종료 된 수신/발신 인스턴트 메시징 호출의 총 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>호출 되는 NNN</p></td>
<td><p>서버에서 받은 총 nnn 응답 코드 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>수신/전송 되는 IM 메시지</p></td>
<td><p>모든 세션에 대해 수신 또는 전송 된 총 메시지 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>수신/발신 전화 시도</p></td>
<td><p>시도 된 수신/발신 인스턴트 메시징 호출의 총 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>수신/발신 전화</p></td>
<td><p>설정 된 수신/발신 인스턴트 메시지의 총 통화 수입니다.</p></td>
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
<td><p>이미 종료 된 수신/발신 응용 프로그램 공유 통화의 총 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>호출 되는 NNN</p></td>
<td><p>서버에서 받은 총 nnn 응답 코드 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>수신/발신 전화 시도</p></td>
<td><p>시도 된 수신/발신 응용 프로그램 공유 통화의 총 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>수신/발신 전화</p></td>
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
<td><p>현재 진행 중인 수신/발신 공중 전화망 (PSTN) 통화의 총 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>통화가 종료 됨</p></td>
<td><p>이미 종료 된 수신/발신 PSTN 통화의 총 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>수신/발신 전화 시도</p></td>
<td><p>시도 된 총 수신/발신 PSTN 통화 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>수신/발신 전화</p></td>
<td><p>설정 된 총 수신/발신 PSTN 통화 수입니다.</p></td>
</tr>
</tbody>
</table>


**전화 회의 정보**


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
<td><p>활성 인스턴트 메시징 회의</p></td>
<td><p>진행 중인 총 인스턴트 메시징 회의 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>활성 오디오/비디오 회의</p></td>
<td><p>진행 중인 총 오디오/비디오 (A/V) 회의 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>활성 응용 프로그램 공유 회의</p></td>
<td><p>진행 중인 총 응용 프로그램 공유 회의 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>참가자 수</p></td>
<td><p>현재 회의에 연결 된 총 참가자 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>전화 회의 일정 오류</p></td>
<td><p>회의를 예약 하려고 하는 동안 발생 한 총 실패 횟수입니다.</p></td>
</tr>
<tr class="even">
<td><p>전화 회의 참가 실패</p></td>
<td><p>전화 회의에 연결 하는 동안 발생 한 총 실패 횟수입니다.</p></td>
</tr>
</tbody>
</table>


**C 및 WA 클라이언트 카운터**


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
<td><p>성공한 IMMCU 조인의 총 수</p></td>
<td><p>가입한 총 인스턴트 메시징 회의 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>성공한 총 DMCU 조인 수</p></td>
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

