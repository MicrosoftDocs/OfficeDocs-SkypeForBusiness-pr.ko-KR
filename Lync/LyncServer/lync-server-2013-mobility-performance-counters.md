---
title: 'Lync Server 2013: Mobility 성능 카운터'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mobility performance counters
ms:assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690046(v=OCS.15)
ms:contentKeyID: 48185441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c0759ccd6a9203dfac87f0ec55f555d49d19ccc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-performance-counters-in-lync-server-2013"></a>Lync Server 2013의 이동성 성능 카운터

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-22_

다음 표에는 통합 커뮤니케이션 웹 API () 및 Lync Server 2013 Mcx Mobility Service를 실행 하는 서버를 모니터링 하는 데 사용할 수 있는 성능 카운터의 이름과 설명이 나와 있습니다.

A **: 웹 –** 테이블의 카운터에 대 한 범주 이름은 LS입니다.

Mcx Mobility Service 테이블의 카운터에 대 한 범주 이름은 **웹-모바일 통신 서비스**입니다.

<div>

## <a name="performance-counters-for-ucwa"></a>기타 WA의 성능 카운터


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>부서</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>활성 응용 프로그램 수</p></td>
<td><p>현재 응용 프로그램 수</p></td>
</tr>
<tr class="even">
<td><p>활성 응용 프로그램 공유 모달의 수</p></td>
<td><p>현재 응용 프로그램 공유 모달의 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>활성 오디오 모달 수</p></td>
<td><p>현재 오디오의 수는 모달입니다.</p></td>
</tr>
<tr class="even">
<td><p>활성 데이터 공동 작업 모달 수</p></td>
<td><p>현재 데이터 공동 작업의 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>Active Directory 사진 가져오기 대기 시간 (밀리초)</p></td>
<td><p>이 카운터는 active directory에서 사진을 검색 하는 평균 시간 (밀리초)을 보여 줍니다.</p></td>
</tr>
<tr class="even">
<td><p>활성 메시징 모달 수</p></td>
<td><p>현재 메시징 모달 수</p></td>
</tr>
<tr class="odd">
<td><p>활성 파노라마 비디오 모달 수</p></td>
<td><p>현재 파노라마 비디오 모달의 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>활성 보류 중인 Get 수</p></td>
<td><p>현재 활성 보류 중인 가져오기 수입니다. 서버에 대 한 장기 연결</p></td>
</tr>
<tr class="odd">
<td><p>활성 세션 수</p></td>
<td><p>각 응용 프로그램 및 요약에 등록 된 현재 끝점 수</p></td>
</tr>
<tr class="even">
<td><p>활성 사용자 인스턴스 수</p></td>
<td><p>현재 사용자 인스턴스 수</p></td>
</tr>
<tr class="odd">
<td><p>응용 프로그램이 없는 활성 사용자 인스턴스</p></td>
<td><p>응용 프로그램이 없는 현재 사용자 인스턴스 수</p></td>
</tr>
<tr class="even">
<td><p>활성 비디오 모달 수</p></td>
<td><p>현재 비디오 모달 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>초당 받은 응용 프로그램 만들기 요청</p></td>
<td><p>수신 된 응용 프로그램 만들기 요청 비율 (초 단위)</p></td>
</tr>
<tr class="even">
<td><p>MCU 참가 실패</p></td>
<td><p>MCU 참가 실패 횟수</p></td>
</tr>
<tr class="odd">
<td><p>AV MCU 참가 실패</p></td>
<td><p>AV MCU 참가 실패 횟수</p></td>
</tr>
<tr class="even">
<td><p>평균 응용 프로그램 시작 시간 (밀리초)</p></td>
<td><p>평균 응용 프로그램 시작 시간 (밀리초)</p></td>
</tr>
<tr class="odd">
<td><p>평균 세션 수명 (밀리초)</p></td>
<td><p>세션의 평균 수명 (밀리초)</p></td>
</tr>
<tr class="even">
<td><p>데이터 MCU 참가 실패</p></td>
<td><p>데이터 MCU 참가 실패 횟수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>Exchange 연락처 검색 지연 시간 (밀리초)</p></td>
<td><p>이 카운터는 Exchange에서 연락처를 검색할 평균 시간 (밀리초)을 보여 줍니다.</p></td>
</tr>
<tr class="even">
<td><p>Exchange HD 사진 가져오기 대기 시간 (밀리초)</p></td>
<td><p>이 카운터는 Exchange에서 사진을 검색 하는 평균 시간 (밀리초)을 보여 줍니다.</p></td>
</tr>
<tr class="odd">
<td><p>HTTP 4xx 응답/초</p></td>
<td><p>HTTP 4xx 코드와의 초당 응답 비율</p></td>
</tr>
<tr class="even">
<td><p>HTTP 5xx 응답/초</p></td>
<td><p>HTTP 5xx 코드와의 초당 응답 비율</p></td>
</tr>
<tr class="odd">
<td><p>메신저 대화 MCU 참가 실패</p></td>
<td><p>메신저 대화 MCU 참가 실패 횟수</p></td>
</tr>
<tr class="even">
<td><p>Active Directory 사진 가져오기 오류 수</p></td>
<td><p>Active Directory에서 사진을 검색 하는 데 실패 한 총 횟수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>연락처 검색 실패 횟수</p></td>
<td><p>Exchange에서 연락처를 검색 하는 데 실패 한 총 횟수</p></td>
</tr>
<tr class="even">
<td><p>Deserialization 오류 수</p></td>
<td><p>총 deserialization 오류 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>HD 사진 가져오기 실패 횟수</p></td>
<td><p>Exchange에서 HD 사진을 검색 하는 데 실패 한 총 횟수</p></td>
</tr>
<tr class="even">
<td><p>응용 프로그램 당 최대 구독 수</p></td>
<td><p>응용 프로그램당 허용 되는 최대값을 초과 하는 구독 요청 수</p></td>
</tr>
<tr class="odd">
<td><p>일괄 처리당 최대 구독 수</p></td>
<td><p>일괄 처리당 허용 되는 최대값을 초과 하는 구독 요청 수</p></td>
</tr>
<tr class="even">
<td><p>현재 상태 구독 실패</p></td>
<td><p>현재 상태를 구독 하는 데 실패 한 횟수</p></td>
</tr>
<tr class="odd">
<td><p>끝점 오류 등록</p></td>
<td><p>끝점 등록 실패 횟수</p></td>
</tr>
<tr class="even">
<td><p>초당 받은 요청</p></td>
<td><p>받은 요청 비율 (초 단위)</p></td>
</tr>
<tr class="odd">
<td><p>성공한 요청/초</p></td>
<td><p>성공한 요청의 초당 속도 (HTTP 2xx/3xx 응답 코드)</p></td>
</tr>
<tr class="even">
<td><p>성공적으로 응용 프로그램 요청 만들기/초</p></td>
<td><p>성공한 응용 프로그램 만들기 요청 비율 (초 단위)</p></td>
</tr>
<tr class="odd">
<td><p>Get Count 보류 중 시간 초과</p></td>
<td><p>시간이 초과 된 보류 중인 가져오기 수</p></td>
</tr>
<tr class="even">
<td><p>받은 총 응용 프로그램 만들기 요청</p></td>
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
<td><p>명령 채널에서 받은 총 요청 수</p></td>
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
<td><p>사용자 유휴 시간 초과로 인해 종료 된 총 세션 수</p></td>
</tr>
<tr class="odd">
<td><p>제한 되는 총 응용 프로그램</p></td>
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
<th>부서</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>세션의 평균 수명 (밀리초)</p></td>
<td><p>세션의 평균 수명 (밀리초)</p></td>
</tr>
<tr class="even">
<td><p>현재 푸시 알림 구독</p></td>
<td><p>현재 푸시 알림 구독 수입니다. 이 번호는 현재 활성 세션 수와 함께 Windows Mobile 또는 iPhone 장치에 대해 등록 된 현재 활성 세션의 하위 집합을 나타냅니다.</p></td>
</tr>
<tr class="odd">
<td><p>현재 활성 상태인 네트워크 시간 제한 폴링 횟수</p></td>
<td><p>시간이 초과 된 네트워크 폴링 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>현재 활성 상태인 폴링 횟수</p></td>
<td><p>현재 활성 폴링 수 (서버에 대 한 장기 유지 연결)</p></td>
</tr>
<tr class="odd">
<td><p>현재 활성 세션 수</p></td>
<td><p>모바일 서비스에 등록 된 현재 끝점 수</p></td>
</tr>
<tr class="even">
<td><p>활성 현재 상태 구독이 있는 현재 활성 세션 수</p></td>
<td><p>활성 현재 상태 구독이 있는 현재 활성 세션 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>실패 한 푸시 알림 요청/초</p></td>
<td><p>실패 한 푸시 알림 비율 (초 단위)</p></td>
</tr>
<tr class="even">
<td><p>성공한 밀어넣기 알림 요청/초</p></td>
<td><p>성공한 푸시 알림 비율 (초 단위)</p></td>
</tr>
<tr class="odd">
<td><p>푸시 알림 요청이 초당 제한 됨</p></td>
<td><p>제한 된 푸시 알림 비율 (초 단위)</p></td>
</tr>
<tr class="even">
<td><p>푸시 알림 요청/초</p></td>
<td><p>전송 된 푸시 알림 비율 (초 단위)</p></td>
</tr>
<tr class="odd">
<td><p>초당 실패 한 요청</p></td>
<td><p>실패 한 요청 비율 (초 단위)</p></td>
</tr>
<tr class="even">
<td><p>초당 받은 요청</p></td>
<td><p>받은 요청 비율 (초 단위)</p></td>
</tr>
<tr class="odd">
<td><p>거부 된 요청/초</p></td>
<td><p>거부 된 요청 비율 (초 단위)</p></td>
</tr>
<tr class="even">
<td><p>성공한 요청/초</p></td>
<td><p>성공한 요청 비율 (초 단위)</p></td>
</tr>
<tr class="odd">
<td><p>초당 세션 요청 초기화 완료</p></td>
<td><p>성공적인 위치 요청 비율 (초 단위) 세션 시작 요청이 서버에서 대부분의 CPU를 사용 합니다. 지원 되는 최고 로드는 12 초입니다. 지속 가능성은 서버의 다른 로드에 따라 달라 집니다. 일반적으로 세션 시작은 오랜 시간 동안 로그 아웃 한 사용자에 대 한 로그인을 의미 합니다.</p></td>
</tr>
<tr class="even">
<td><p>거부 된 총 인바운드 음성 통화</p></td>
<td><p>거절 된 총 인바운드 음성 통화 수</p></td>
</tr>
<tr class="odd">
<td><p>실패 한 총 인바운드 음성 통화</p></td>
<td><p>실패 한 총 인바운드 음성 통화 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>실패 한 총 아웃 바운드 음성 통화</p></td>
<td><p>실패 한 총 아웃 바운드 음성 통화 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>사용자가 종료 한 총 세션 수</p></td>
<td><p>사용자가 종료 한 총 세션 수</p></td>
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
<td><p>제한 되는 총 푸시 알림 요청</p></td>
<td><p>제한 된 푸시 알림 요청의 총 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>실패 한 총 요청</p></td>
<td><p>실패 한 총 요청 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>명령 채널에서 받은 총 요청</p></td>
<td><p>명령 채널에서 받은 총 요청 수</p></td>
</tr>
<tr class="even">
<td><p>거부 된 총 요청</p></td>
<td><p>거부 된 총 요청 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p>성공한 총 요청</p></td>
<td><p>성공한 이동성 서비스에 대 한 총 요청 수입니다.</p></td>
</tr>
<tr class="even">
<td><p>총 세션 시작 횟수</p></td>
<td><p>모바일 서비스가 시작 된 이후 시작 된 총 세션 수</p></td>
</tr>
<tr class="odd">
<td><p>사용자 유휴 시간 초과로 인해 종료 된 총 세션</p></td>
<td><p>사용자 유휴 시간 초과로 인해 종료 된 총 세션 수</p></td>
</tr>
<tr class="even">
<td><p>성공한 총 인바운드 음성 통화</p></td>
<td><p>성공한 총 인바운드 음성 통화 수</p></td>
</tr>
<tr class="odd">
<td><p>성공한 총 발신 음성 통화</p></td>
<td><p>성공한 총 발신 음성 통화 수</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

