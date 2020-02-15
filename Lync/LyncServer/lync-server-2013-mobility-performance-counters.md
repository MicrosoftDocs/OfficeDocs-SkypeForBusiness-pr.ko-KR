---
title: 'Lync Server 2013: 모바일 성능 카운터'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility performance counters
ms:assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690046(v=OCS.15)
ms:contentKeyID: 48185441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56454e4ea4fa1498dc73056d5b5f01193b007352
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-performance-counters-in-lync-server-2013"></a>Lync Server 2013의 모바일 기능 성능 카운터

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-22_

다음 표에는 통합 커뮤니케이션 웹 API (WA) 및 Lync Server 2013 Mcx Mobility Service를 실행 하는 서버를 모니터링 하는 데 사용할 수 있는 성능 카운터의 이름과 설명이 나와 있습니다.

(C) 테이블에 있는 카운터의 범주 이름은 **LS: WEB – wa**입니다.

Mcx Mobility Service 테이블의 카운터에 대 한 범주 이름 **: 웹-모바일 통신 서비스**입니다.

<div>

## <a name="performance-counters-for-ucwa"></a>DATWA에 대 한 성능 카운터


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>카운터</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>활성 응용 프로그램 수</p></td>
<td><p>현재 응용 프로그램 수</p></td>
</tr>
<tr class="even">
<td><p>활성 응용 프로그램 공유 모달 수</p></td>
<td><p>현재 응용 프로그램 공유 모달의 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>활성 오디오 모달 수</p></td>
<td><p>현재 오디오 모달 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>활성 데이터 공동 작업 모달 수</p></td>
<td><p>현재 데이터 공동 작업의 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>Active Directory 사진 가져오기 대기 시간 (ms)</p></td>
<td><p>이 카운터는 active directory에서 사진을 검색 하는 데 걸린 평균 시간 (밀리초)을 보여 줍니다.</p></td>
</tr>
<tr class="even">
<td><p>활성 메시징 모달 수</p></td>
<td><p>현재 메시징 모달 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>활성 파노라마 비디오 모달 수</p></td>
<td><p>현재 파노라마 비디오 모달 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>활성 보류 중인 가져오기 수</p></td>
<td><p>현재 보류 중인 활성 상태 수입니다. 서버에 대 한 장기 유지 연결</p></td>
</tr>
<tr class="odd">
<td><p>활성 세션 수</p></td>
<td><p>응용 프로그램당 및 total에 등록 된 현재 끝점 수</p></td>
</tr>
<tr class="even">
<td><p>활성 사용자 인스턴스 수</p></td>
<td><p>현재 사용자 인스턴스 수</p></td>
</tr>
<tr class="odd">
<td><p>응용 프로그램이 없는 활성 사용자 인스턴스</p></td>
<td><p>응용 프로그램이 없는 현재 사용자 인스턴스 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>활성 비디오 모달 수</p></td>
<td><p>현재 비디오 모달 수</p></td>
</tr>
<tr class="odd">
<td><p>초당 수신 되는 응용 프로그램 만들기 요청</p></td>
<td><p>받은 응용 프로그램 만들기 요청의 초당 비율입니다.</p></td>
</tr>
<tr class="even">
<td><p>MCU 참가 실패</p></td>
<td><p>MCU 연결 실패 횟수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>AV MCU 참가 실패</p></td>
<td><p>AV MCU 참가 실패 횟수입니다.</p></td>
</tr>
<tr class="even">
<td><p>평균 응용 프로그램 시작 시간 (밀리초)</p></td>
<td><p>평균 응용 프로그램 시작 시간 (밀리초)입니다.</p></td>
</tr>
<tr class="odd">
<td><p>평균 세션 수명 (ms)</p></td>
<td><p>세션의 평균 수명 (밀리초)입니다.</p></td>
</tr>
<tr class="even">
<td><p>데이터 MCU 참가 실패</p></td>
<td><p>데이터 MCU 참가 실패 횟수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>Exchange 연락처 검색 대기 시간 (밀리초)</p></td>
<td><p>이 카운터는 Exchange에서 연락처를 검색 하는 데 걸린 평균 시간 (밀리초)을 표시 합니다.</p></td>
</tr>
<tr class="even">
<td><p>Exchange HD 사진 가져오기 대기 시간 (ms)</p></td>
<td><p>이 카운터는 Exchange에서 사진을 검색 하는 데 걸린 평균 시간 (밀리초)을 보여 줍니다.</p></td>
</tr>
<tr class="odd">
<td><p>HTTP 4xx 응답/초</p></td>
<td><p>HTTP 4xx 코드를 사용한 응답 비율 (초 단위)</p></td>
</tr>
<tr class="even">
<td><p>HTTP 5xx 응답/초</p></td>
<td><p>HTTP 5xx 코드를 사용한 응답 비율 (초 단위)</p></td>
</tr>
<tr class="odd">
<td><p>IM MCU 참가 실패</p></td>
<td><p>IM MCU 참가 실패 횟수</p></td>
</tr>
<tr class="even">
<td><p>Active Directory 사진 가져오기 오류 수</p></td>
<td><p>Active Directory에서 사진 검색에 대 한 총 실패 횟수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>연락처 검색 실패 횟수</p></td>
<td><p>Exchange에서 연락처를 검색 하는 데 실패 한 총 횟수입니다.</p></td>
</tr>
<tr class="even">
<td><p>Deserialization 오류 발생 횟수</p></td>
<td><p>총 deserialization 실패 횟수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>HD 사진 가져오기 실패 수</p></td>
<td><p>Exchange에서 HD 사진을 검색 하는 데 실패 한 총 횟수입니다.</p></td>
</tr>
<tr class="even">
<td><p>응용 프로그램당 최대 구독 수</p></td>
<td><p>응용 프로그램당 허용 되는 최대 수를 초과 하는 구독 요청 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>일괄 처리당 최대 구독 수</p></td>
<td><p>일괄 처리당 허용 되는 최대값을 초과 하는 구독 요청 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>현재 상태 구독 실패</p></td>
<td><p>현재 상태 구독 실패 횟수</p></td>
</tr>
<tr class="odd">
<td><p>끝점 오류 등록</p></td>
<td><p>끝점 등록 실패 횟수</p></td>
</tr>
<tr class="even">
<td><p>초당 수신한 요청</p></td>
<td><p>수신 된 요청의 초당 비율입니다.</p></td>
</tr>
<tr class="odd">
<td><p>초당 성공한 요청</p></td>
<td><p>성공한 요청의 초당 비율 (HTTP 2xx/3xx 응답 코드)</p></td>
</tr>
<tr class="even">
<td><p>성공한 응용 프로그램 요청 만들기/초</p></td>
<td><p>성공적인 응용 프로그램 만들기 요청의 초당 비율입니다.</p></td>
</tr>
<tr class="odd">
<td><p>보류 중인 가져오기 수 제한</p></td>
<td><p>시간 초과 된 보류 중인 일정의 수</p></td>
</tr>
<tr class="even">
<td><p>수신 되는 총 응용 프로그램 만들기 요청</p></td>
<td><p>서비스가 시작 된 이후 받은 총 응용 프로그램 만들기 요청 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>총 HTTP 4xx 응답</p></td>
<td><p>총 HTTP 4xx 응답 수</p></td>
</tr>
<tr class="even">
<td><p>총 HTTP 5xx 응답</p></td>
<td><p>총 HTTP 5xx 응답 수</p></td>
</tr>
<tr class="odd">
<td><p>명령 채널에서 받은 총 요청</p></td>
<td><p>명령 채널에서 받은 요청의 총 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>성공한 총 요청</p></td>
<td><p>성공한 요청의 총 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>시작 된 총 세션</p></td>
<td><p>서비스가 시작 된 이후 시작 된 총 세션 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>유휴 시간 제한으로 인해 종료 된 총 세션</p></td>
<td><p>사용자 유휴 시간 제한으로 인해 종료 된 총 세션 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>총 제한 된 응용 프로그램</p></td>
<td><p>제한 된 응용 프로그램 수</p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a>Mcx Mobility Service에 대 한 성능 카운터

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>카운터</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>평균 세션 수명 (밀리초)</p></td>
<td><p>세션의 평균 수명 (밀리초)입니다.</p></td>
</tr>
<tr class="even">
<td><p>현재 푸시 알림 구독</p></td>
<td><p>현재 푸시 알림 구독 수입니다. 현재 활성 세션 수와 함께이 번호는 Windows Mobile 또는 iPhone 장치에 대해 등록 된 현재 활성 세션의 하위 집합을 나타냅니다.</p></td>
</tr>
<tr class="odd">
<td><p>현재 활성 상태인 네트워크 시간 제한 폴링 수</p></td>
<td><p>시간이 초과 된 네트워크 폴링 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>현재 활성 상태인 폴링 횟수</p></td>
<td><p>현재 활성 상태인 폴링 (서버에 대 한 장기 유지 연결)의 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>현재 활성 세션 수</p></td>
<td><p>모바일 서비스에 등록 된 현재 끝점 수</p></td>
</tr>
<tr class="even">
<td><p>활성 현재 상태 구독이 있는 현재 활성 상태의 세션 수</p></td>
<td><p>활성 현재 상태 구독이 있는 현재 활성 세션 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>푸시 알림 요청 실패/초</p></td>
<td><p>실패 한 푸시 알림의 초당 비율입니다.</p></td>
</tr>
<tr class="even">
<td><p>초당 성공한 푸시 알림 요청</p></td>
<td><p>성공한 푸시 알림의 초당 비율입니다.</p></td>
</tr>
<tr class="odd">
<td><p>초당 제한 된 푸시 알림 요청</p></td>
<td><p>제한 된 푸시 알림의 초당 비율입니다.</p></td>
</tr>
<tr class="even">
<td><p>푸시 알림 요청/초</p></td>
<td><p>전송 된 푸시 알림의 초당 비율입니다.</p></td>
</tr>
<tr class="odd">
<td><p>실패 한 요청/초</p></td>
<td><p>실패 한 요청의 초당 비율입니다.</p></td>
</tr>
<tr class="even">
<td><p>초당 수신한 요청</p></td>
<td><p>수신 된 요청의 초당 비율입니다.</p></td>
</tr>
<tr class="odd">
<td><p>거부 된 요청/초</p></td>
<td><p>거부 된 요청의 초당 비율입니다.</p></td>
</tr>
<tr class="even">
<td><p>초당 성공한 요청</p></td>
<td><p>성공한 요청의 초당 비율입니다.</p></td>
</tr>
<tr class="odd">
<td><p>성공한 세션 요청 시작/초</p></td>
<td><p>성공적인 위치 가져오기 요청의 초당 비율입니다. 세션 시작 요청은 서버에서 가장 많은 CPU를 사용 합니다. 지원 되는 최대 부하는 12 초입니다. 지속 가능성은 서버의 다른 부하에 따라 달라 집니다. 세션 시작은 일반적으로 오랜 시간 동안 로그 아웃 된 사용자에 대 한 로그인을 의미 합니다.</p></td>
</tr>
<tr class="even">
<td><p>총 거부 되는 인바운드 음성 통화</p></td>
<td><p>거절 된 인바운드 음성 통화의 총 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>총 실패 한 인바운드 음성 통화</p></td>
<td><p>실패 한 인바운드 음성 통화의 총 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>총 실패 한 아웃 바운드 음성 통화</p></td>
<td><p>실패 한 아웃 바운드 음성 통화의 총 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>사용자가 종료 한 총 세션 수입니다.</p></td>
<td><p>사용자가 종료 한 총 세션 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>총 푸시 알림 요청</p></td>
<td><p>푸시 알림 요청의 총 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>실패 한 총 푸시 알림 요청</p></td>
<td><p>실패 한 푸시 알림 요청의 총 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>성공한 총 푸시 알림 요청</p></td>
<td><p>성공한 푸시 알림 요청의 총 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>제한 된 총 푸시 알림 요청</p></td>
<td><p>제한 된 푸시 알림 요청의 총 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>실패 한 총 요청</p></td>
<td><p>실패 한 요청의 총 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>명령 채널에서 받은 총 요청</p></td>
<td><p>명령 채널에서 받은 요청의 총 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>거부 된 총 요청</p></td>
<td><p>거부 된 요청의 총 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>성공한 총 요청</p></td>
<td><p>모바일 서비스에 대해 성공한 요청의 총 요청 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>총 세션 시작 횟수</p></td>
<td><p>Mobility Service를 시작한 이후 시작 된 세션의 총 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>사용자 유휴 시간 초과로 인해 종료 된 총 세션 수</p></td>
<td><p>사용자 유휴 시간 제한으로 인해 종료 된 총 세션 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>총 성공한 인바운드 음성 통화</p></td>
<td><p>성공한 인바운드 음성 통화의 총 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>총 성공한 아웃 바운드 음성 통화</p></td>
<td><p>성공한 아웃 바운드 음성 통화의 총 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

