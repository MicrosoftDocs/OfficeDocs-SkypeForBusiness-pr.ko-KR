---
title: 'Lync Server 2013: 사용자 모델'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 user models
ms:assetid: c551371c-d740-4372-bada-f0d713ec0d33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398811(v=OCS.15)
ms:contentKeyID: 49733811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8f45b3ea11911ea7a3dce36b0b6a9d64ac1e690
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-models-in-lync-server-2013"></a>Lync Server 2013의 사용자 모델

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-10-07_

여기에 설명 된 사용자 모델은 [사용자 모델을 사용 하 여 Lync Server 2013의 용량 계획](lync-server-2013-capacity-planning-using-the-user-models.md)에 설명 된 용량 계획 측정값 및 권장 사항에 대 한 기반을 제공 합니다.

<div>

## <a name="lync-server-2013-user-models"></a>Lync Server 2013 사용자 모델

다음 표에서는 Lync Server 2013의 등록, 연락처, 인스턴트 메시징 (IM) 및 현재 상태에 대 한 사용자 모델에 대해 설명 합니다.

### <a name="environment-and-registration-user-model"></a>환경 및 등록 사용자 모델

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>범주만</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>배포 크기 및 배포</p></td>
<td><p>사이트 당 하나의 프런트 엔드 풀을 사용 하 여 세 개의 중앙 사이트를 사용 하는 대규모 배포를 모델링 합니다.</p></td>
</tr>
<tr class="even">
<td><p>Active Directory 사용자의 백분율</p></td>
<td><p>조직의 모든 Active Directory 사용자의 70%가 Lync Server에 대해 사용 하도록 설정 되어 있다고 가정 합니다. 이 사용 가능한 사용자의 80%가 하루 종일 Lync Server에 로그온 되어 있습니다 (80% 병행성). 동시 사용자는이 섹션의 나머지 부분에 있는 숫자를 기반으로 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>Active Directory 변경 내용</p></td>
<td><p>모든 사용자의 0.5%가 매주 Active Directory에서 Lync에 만들어지고 사용 하도록 설정 되었고, 모든 사용자의 0.5%는 Active Directory 및 매 주마다 Lync에서 사용 하지 않도록 설정 되어 있다고 가정 합니다. 사용자의 5%는 매주 1 개 이상의 Active Directory 특성을 변경 합니다.</p></td>
</tr>
<tr class="even">
<td><p>Active Directory 메일 그룹</p></td>
<td><p>조직의 Active Directory 메일 그룹 수가 Active Directory의 모든 사용자 수의 3 배가 되는 것으로 가정 합니다. 메일 그룹의 크기는 다음과 같습니다.</p>
<ul>
<li><p>64%에 2-30 사용자가 있습니다.</p></li>
<li><p>13%에 31-50 사용자가 있습니다.</p></li>
<li><p>10%에 51-100 사용자가 있습니다.</p></li>
<li><p>13%에 101-500 사용자가 있습니다.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>VoIP (Voice over IP) 사용자</p></td>
<td><p>Lync Server 사용자의 60%는 통합 커뮤니케이션 (UC)에 사용할 수 있습니다 (즉, 전화 번호는 Lync Server에서 소유).</p></td>
</tr>
<tr class="even">
<td><p>등록 된 클라이언트 배포</p></td>
<td><p>클라이언트의 65%는 Lync 및 Lync Phone 버전을 포함 하 여 Lync 2013 소프트웨어를 실행 합니다.</p>
<p>이전 버전의 Lync에서 클라이언트 소프트웨어를 실행 하는 클라이언트의 30%</p>
<p>Lync Web App을 사용 하는 클라이언트의 5%</p>
<p>이동성을 사용 하도록 설정한 경우 사용자의 40%가 이전에 인용 된 다른 클라이언트 옵션과 동시에 이동성을 사용 하 고 있다고 가정 합니다. 이 경우 클라이언트는 MPOP (다중 시점) 비율이 1:1.9입니다. 이동성을 사용 하지 않도록 설정한 경우 MPOP 비율은 1:1.5입니다.</p></td>
</tr>
<tr class="odd">
<td><p>원격 사용자 배포</p></td>
<td><p>내부적으로 연결 하는 사용자의 70%입니다.</p>
<p>Edge 서버 및 디렉터를 통해 연결 되는 사용자의 30%</p></td>
</tr>
<tr class="even">
<td><p>연락처 배포</p></td>
<td><p>사용자에 게 표시 되는 최대 연락처 수는 1000입니다. 1% 미만의 사용자가 1000 연락처를가지고 있습니다. 사용자 중 25% 미만의 연락처가 100 개 이상 있습니다.</p>
<p>공용 클라우드 연결이 있는 사용자에 대 한 80 연락처의 평균입니다. 다음 사용자:</p>
<ul>
<li><p>50%의 연락처가 조직 내에 있습니다. 이러한 사용자의 10%는 원격 사용자로 방화벽 외부에서 연결 합니다.</p></li>
<li><p>연락처의 40%는 공용 클라우드 사용자 (AOL, Yahoo!, MSN 또는 Google 대화 사용자 등)입니다.</p></li>
<li><p>연락처의 10%는 페더레이션 파트너에서 가져온 것입니다.</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>2012 년 9 월 1 일부 터, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")는 신규 또는 갱신 계약에 대해 더 이상 구매할 수 없습니다. 활성 라이선스가 있는 고객은 계속 Yahoo!에 페더레이션 할 수 있습니다. 서비스 종료 날짜가 될 때까지 메신저를 종료 합니다. AOL 및 Yahoo!에 대 한 6 월 2014의 기간 종료 날짜 님이 발표 되었습니다. 자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공개 인스턴트 메신저 연결 지원을</A>참조 하세요.</P>
> <LI>
> <P>PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!에 페더레이션 하는 데 필요한 사용자별 사용자 단위 구독 라이선스입니다. 받으려면. 이 서비스를 제공 하는 Microsoft의 기능은 기본 계약 인 Yahoo!에 대 한 지원을 받을 수 있습니다.</P>
> <LI>
> <P>이전 보다 훨씬 더 많은 수의 Lync는 전세계의 조직과 사용자 간에 연결 하는 강력한 도구입니다. Windows Live Messenger를 사용 하는 페더레이션에서는 Lync 표준 CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다. Skype 페더레이션이이 목록에 추가 되어 Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 연락할 수 있도록 합니다.</P></LI></UL>


</div></li>
</ul>
<p>공용 클라우드 연결이 없는 사용자에 대 한 50 연락처의 평균입니다. 다음 사용자:</p>
<ul>
<li><p>80%의 연락처가 조직 내에 있습니다. 이러한 사용자의 10%는 원격 사용자로 방화벽 외부에서 연결 합니다.</p></li>
<li><p>페더레이션 파트너는 연락처의 20%를 말합니다.</p>
<p>각 사용자의 연락처 목록에는 1 개의 메일 그룹이 있습니다. 성능 테스트를 위해 메일 그룹이 항상 확장 되었다고 가정 합니다.</p></li>
</ul>
<p>사용자의 연락처 중 25%는 XMPP를 사용 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>세션 시간</p></td>
<td><p>평균 사용자 로그온 세션은 12 시간 동안 지속 됩니다. 모든 사용자가 세션 시작 시 120 분 내에 로그온 합니다.</p></td>
</tr>
</tbody>
</table>


### <a name="im-and-presence-user-model"></a>IM 및 현재 상태 사용자 모델

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>범주만</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>피어 투 피어 IM 세션</p></td>
<td><p>각 사용자는 하루에 6 개의 피어 투 피어 IM 세션 평균을 계산 합니다.</p>
<p>세션 당 10 개의 인스턴트 메시지.</p>
<p>각 메시지는 두 개의 SIP 정보 메시지와 ""&lt;이름&gt; 입력 "과 같은 상태 표시기 용 2 sip 200 OK 메시지와 일치 합니다.</p></td>
</tr>
<tr class="even">
<td><p>현재 상태 폴링</p></td>
<td><p>전반적으로 시간 당 사용자 당 평균 60 폴링에 대 한 현재 상태 폴링을 가정 합니다. 각 사용자에 대해 다음 평균을 가정 합니다.</p>
<ul>
<li><p>사용자의 조직 탭에 있는 사용자의 하루에 한 번의 폴링 (대화 상대 목록 제외) 사용자의 조직 탭에 있는 연락처가 아닌 평균 수는 사용자 15 명입니다. 1 일에 두 개의 대화 상대 카드 보기 작업</p></li>
<li><p>사용자가 다른 사용자를 클릭 하 여 대화를 시작할 때마다 한 번의 현재 상태 폴링으로 시간 당 한 번씩 예상 됩니다.</p></li>
<li><p>시간 당 6 명의 사용자 검색. 검색을 수행할 때마다 검색 결과 목록의 모든 사용자에 대해 일괄 처리 폴링이 전송 됩니다. 검색 결과의 평균 크기는 20으로 가정 합니다. 검색 결과가 화면에 남아 있는 경우 일괄 처리 설문은 5 분 마다 새로 고쳐집니다. 이번에는 시간 당 두 가지 그러한 새로 고침이 있을 것으로 가정 합니다.</p></li>
<li><p>사용자가 Outlook에서 전자 메일을 열거나 미리 볼 때 전자 메일의 받는 사람: 및 CC: 필드에 사용자가 있는 경우와 전자 메일 당 최대 4 명의 사용자에 게 표시 됩니다.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>현재 상태 구독</p></td>
<td><p>사용자 중 한 명에 게 연락처를 추가 하는 경우 첫 번째 사용자는 두 번째 사용자에 대 한 다섯 가지 범주의 정보를 <em>구독</em> 합니다. 이러한 범주의 정보에 대 한 업데이트는 자동으로 첫 번째 사용자에 게 전송 됩니다.</p>
<p>각 클라이언트에 대해 단일 일괄 처리 요청을 전송 하 여 평균 40 연락처의 현재 상태를 얻고 추가 40 대화 상자를 사용 하 여 페더레이션 대화 상대에 대 한 상태를 얻을 수 있습니다.</p>
<p>확장 된 메일 그룹의 구성원에 대 한 현재 상태는 폴링이 아닌 영구 현재 상태 구독을 통해 검색 되며 각 2 시간 동안 사용자 당 하나의 확장으로 모델링 됩니다.</p>
<p><em>짧은</em> 플랜 사용자가 로그인 하면 모든 사용자의 연락처에 대 한 일괄 구독이 있는 경우 사용자가 곧 로그 오프 됩니다. 각 구독이 10 분 후에 시간 당 6 개의 짧은 구독이 있는 것으로 가정 합니다.</p></td>
</tr>
<tr class="even">
<td><p>현재 상태 게시</p></td>
<td><p>현재 상태는 시간당 사용자 당 최대 4 개의 출판물에 게시 됩니다 (시간당 사용자 당 최고 6 개).</p></td>
</tr>
<tr class="odd">
<td><p>현재 상태 문서 크기</p></td>
<td><p>전체 현재 상태 문서의 평균 크기는 최대 25K의 4K로 간주 됩니다.</p></td>
</tr>
</tbody>
</table>


다음 표에서는 주소록 사용에 대 한 사용자 모델에 대해 설명 합니다.

### <a name="address-book-usage-user-model"></a>주소록 사용 사용자 모델

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>주소록 검색 모드</th>
<th>용도</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>주소록 웹 쿼리 전용 (주소록 웹 쿼리 서비스를 통해 수행 되는 모든 쿼리)</p></td>
<td><p>일일 사용자 당 4 개의 접두 번호 쿼리.</p>
<p>60 사용자 당 정확한 검색 쿼리. 쿼리 당 평균 20 개의 연락처가 있는 일괄 처리 된 40%가 있습니다. 쿼리의 다른 60%는 단일 연락처에 대 한 것입니다.</p>
<p>일일 사용자 당 25 개의 사진 쿼리. 24는 단일 사진에 대 한 것이 고, 다른 하나는 평균 20 개의 연락처를 포함 하는 일괄 처리 쿼리입니다.</p>
<p>일일 사용자 당 총 조직 검색 쿼리 1 개.</p></td>
</tr>
<tr class="even">
<td><p>주소록 파일과 웹 쿼리를 모두 사용 하는 혼합 모드 기본 모드입니다.</p></td>
<td><p>두 가지 유형의 쿼리만 네트워크, 사진 및 총 조직 검색 쿼리로 이동 합니다.</p>
<p>일일 사용자 당 25 개의 사진 쿼리. 24는 단일 사진에 대 한 것이 고, 다른 하나는 평균 20 개의 연락처를 포함 하는 일괄 처리 쿼리입니다.</p>
<p>일일 사용자 당 총 조직 검색 쿼리 1 개.</p></td>
</tr>
</tbody>
</table>


다음 표에서는 회의 모델에 대해 설명 합니다.

### <a name="conferencing-model"></a>회의 모델

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>범주만</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>예약 된 모임 &quot;과 모임&quot; 시작 모임 비교</p></td>
<td><p>60%의 예정, 40%가 없습니다.</p>
<p>예약 된 모임의 경우 80%에 회의 회의가 있는 것으로 간주 됩니다. 10%는 일회성 열려 있는 모임입니다. 8%는 일회성 익명 모임이 며 2%는 일회성으로 닫힌 모임입니다.</p></td>
</tr>
<tr class="even">
<td><p>회의 클라이언트 배포</p></td>
<td><p>예약 된 모임의 경우:</p>
<ul>
<li><p>회의 사용자의 65%는 Lync 2013를 사용 합니다.</p></li>
<li><p>회의 사용자의 5%는 Microsoft Lync Web App을 사용 합니다.</p></li>
<li><p>회의의 30%는 Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007, Microsoft Office Communicator Web Access (2007 release)를 포함 하 여 이전 버전의 클라이언트를 사용 하 고 있습니다.</p></li>
</ul>
<p>예정 되지 않은 모임의 경우:</p>
<ul>
<li><p>회의 사용자의 70%는 Lync 2013를 사용 합니다.</p></li>
<li><p>회의의 30%는 Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007, Microsoft Office Communicator Web Access (2007 release)를 포함 하 여 이전 버전의 클라이언트를 사용 하 고 있습니다.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>모임 동시성</p></td>
<td><p>사용자의 5%는 근무 시간 동안 회의에 참여 하 고 있는 것입니다. 따라서 8만 사용자 풀에서 4000 사용자는 언제 든 지 회의에 참석할 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>모임 오디오 배포</p></td>
<td><p>40% 혼합 VoIP 오디오 및 전화 접속 회의, 그리고 전화 접속 사용자를 위한 VoIP 사용자의 3:1 비율.</p>
<p>35% VoIP 오디오만.</p>
<p>15% 전화 접속 회의 오디오만</p>
<p>10% 오디오 없음 (IM 전용 회의, 사용자 당 평균 5 개의 메시지가 전송 됨).</p></td>
</tr>
<tr class="odd">
<td><p>회의를 위한 미디어 조합</p></td>
<td><p>회의의 75%는 오디오와 다른 공동 작업 형식을 포함 하는 웹 회의입니다.</p>
<p>이러한 컨퍼런스에 대 한 다른 공동 작업 방법은 다음과 같습니다.</p>
<div>

> [!NOTE]  
> 이러한 수치는 하나의 회의에 여러 공동 작업 방법이 있을 수 있으므로 100% 이상을 추가 합니다.


</div>
<ul>
<li><p>50% 응용 프로그램 공유 추가 한 명의 사용자가 초당 최대 1.1 MB의 데이터를 전송 하는 것으로 가정 합니다.</p></li>
<li><p>50% 인스턴트 메시지 추가 (사용자 당 평균 2 개의 메시지)</p></li>
<li><p>20% 이러한 데이터 공동 작업 (예: PowerPoint 또는 화이트 보드 포함)을 추가 하면 각 회의에 대해 표시 되는 평균 2 개의 PowerPoint 파일, 최대 PowerPoint 파일 크기: 10 MB (임베디드 비디오 제외) 또는 30mb (포함 된 비디오 사용)가 있습니다. 화이트 보드 당 평균 20 개의 주석</p></li>
<li><p>20% 영상 추가. 이러한 사용자 중 70%는 각 사용자가 2-3 비디오 스트림을 수신 하는 multiview 비디오에 대해 회의에 설정 되어 있습니다.</p></li>
<li><p>15% 공유 메모 추가</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>모임 참가자 배포</p></td>
<td><p>50% 내부 인증 된 사용자</p>
<p>인증 된 사용자 인 25% 원격 액세스</p>
<p>15% 익명 사용자.</p>
<p>10% 페더레이션 사용자.</p></td>
</tr>
<tr class="odd">
<td><p>모임 참가 배포</p></td>
<td><p>사용자는 처음 5 분 내에 모임에 참가 하는 것으로 시뮬레이션 됩니다.</p></td>
</tr>
</tbody>
</table>


일반 프런트 엔드 풀에서 Lync Server 2013에는 지원 되는 최대 모임 크기 (250 사용자)가 있습니다. 각 풀은 한 번에 1 250 사용자 모임을 호스트할 수 있습니다. 이 대규모 모임이 진행 되는 동안에는 풀이 다른 작은 회의를 호스트할 수도 있습니다. 또한이 모임을 호스팅하도록 전용 풀을 설정 하 여 최대 1000 사용자의 모임을 지원할 수 있습니다. 자세한 내용은 [Lync Server 2013의 대규모 모임 지원을](lync-server-2013-support-for-large-meetings.md)참조 하세요.

회의는 다음과 같이 시뮬레이트할 것입니다.

  - 회의의 85%는 참가자가 네 명 이었습니다.

  - 회의의 10%는 참가자가 6 명 이었습니다.

  - 회의의 5%는 참가자가 11 명 이었습니다.

  - 250 사용자 1 명으로 이루어진 대용량 회의.

다음 표에서는 전화 접속 사용자와 관련 된 사용자 모델에 대 한 세부 정보를 제공 합니다.

### <a name="dial-in-conferencing-user-model"></a>전화 접속 회의 사용자 모델

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>범주만</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>인증 됨/익명</p></td>
<td><p>발신자의 70%는 익명으로 참가 하 고 기록 된 이름을 입력 하 라는 메시지가 표시 됩니다. 인증 된 사용자로 30% 참가.</p></td>
</tr>
<tr class="even">
<td><p>통화 시간 및 음악 보류</p></td>
<td><p>음악을 보유 하지 않은 평균 통화 시간: 50 초.</p>
<p>통화 사용자의 50%는 평균적으로 5 분 동안 대기 음악을 들을 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Multifrequency (DTMF)</p></td>
<td><p>전화 접속 인 회의의 15%는 전화 선도 지역에만 있습니다. 전화 접속 사용자를 포함 하는 혼합 컨퍼런스 10%에도 전화 리더가 있습니다.</p>
<p>전화 리더의 20%는 각 회의에 대해 DTMF 명령 2 개를 사용 합니다.</p></td>
</tr>
<tr class="even">
<td><p>알림 언어</p></td>
<td><p>시뮬레이션에서는 영어를 공지 사항 언어로 사용 합니다.</p></td>
</tr>
</tbody>
</table>


다음 표에서는 컨퍼런스 로비 사용자 모델에 대 한 세부 정보를 제공 합니다.

### <a name="conference-lobby-user-model"></a>컨퍼런스 대기실 사용자 모델

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>범주만</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>대기실에 있는 사용자 수</p></td>
<td><p>전화 접속 사용자의 5%는 대기실에서 진행 되며, 다른 사용자의 25%는 대기실를 통해 진행 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>대기실에서 Admitting</p></td>
<td><p>시뮬레이션에서 클라이언트 제한 시간 전에 발표자가 모든 사용자를 허가 했습니다.</p></td>
</tr>
</tbody>
</table>


다음 표에서는 다른 피어 투 피어 세션의 사용자 모델에 대해 설명 합니다.

### <a name="peer-to-peer-sessions-user-model"></a>피어 투 피어 세션 사용자 모델

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>범주만</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>응용 프로그램 공유</p></td>
<td><p>각 사용자는 일일 5 개 피어 투 피어 응용 프로그램 공유 세션에 참여 합니다 (일별 평균 0.25 세션).</p></td>
</tr>
<tr class="even">
<td><p>파일 전송</p></td>
<td><p>각 사용자는 하루에 평균 0.05 세션에 대해 1 개월 피어 투 피어 파일 전송 세션 (IM 세션의 일부로)에 참여 합니다. 전송 되는 평균 세션 파일 크기는 1mb입니다.</p></td>
</tr>
</tbody>
</table>


다음 표에서는 정책에 대 한 사용자 모델에 대해 설명 합니다.

### <a name="policies-user-model"></a>정책 사용자 모델

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>범주만</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>회의, 현재 상태 및 보관 정책</p></td>
<td><p>글로벌 정책, 10 개의 태그 회의 정책, 보관 정책 4 개, 태그 현재 상태 정책 1 개가 있다고 가정 합니다.</p></td>
</tr>
<tr class="even">
<td><p>음성 정책</p></td>
<td><p>사이트 마다 하나의 글로벌 정책 및 2 개의 태그 정책이 있다고 가정 합니다. 사이트의 100%에는 사이트 정책이 있으며 사용자의 30%에는 사용자 별 정책이 할당 됩니다. 사이트별로 하나의 다이얼 플랜을 만들고 각 사이트에는 두 개의 경로를 계획 하 고 있다고 가정 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="busy-hour"></a>통화 시간

피어 투 피어 세션의 경우 사용량이 많은 시간 (BHCA)을 사용 하 여 최대 로드가 계산 됩니다. 이 음성 산업 약관은 하루 종일 통화의 50%가 20% 동안 완료 된다고 가정 합니다. 다음 수식을 사용 하 여 계산 됩니다.

`BHCA=(total calls * 0.5) / 1.6`

일일 최소 1.6 시간 동안 바쁜 시간에 VoIP 및 기타 피어 투 피어 세션을 실행 하 여 시간을 시뮬레이션 한 성능 테스트.

회의 최고 로드는 하루에 모든 컨퍼런스의 75%가 최대 4 시간 동안 발생 한다고 가정 합니다. 이러한 피크 시간은 평균 회의 부하의 1.5 배입니다.

</div>

<div>

## <a name="enterprise-voice-to-pstn-calls"></a>엔터프라이즈 음성 ~ PSTN 통화

엔터프라이즈 음성 통화에는 다음과 같은 가정이 적용 됩니다.

  - 사용자의 50%가 엔터프라이즈 음성에 대해 사용 하도록 설정 되어 있으며 이러한 사용자의 60%는 PSTN 통화에 사용할 수 있습니다.

  - PSTN 통화에 대해 사용 하도록 설정 된 이러한 각 사용자는 바쁜 시간 동안 4 개의 PSTN 통화를 수행 합니다. 각 통화 기간은 3 분입니다.

  - 이 PSTN 음성 통화의 65%는 미디어 바이패스를 사용 합니다.

</div>

<div>

## <a name="mobility"></a>이동성

등록 된 사용자의 40%는 이동성을 사용할 수 있는 것으로 간주 됩니다. 이동성을 사용 하는 각 사용자에 대해 모바일 클라이언트의 활동은 해당 사용자에 대 한 다른 MPOP 인스턴스를 추가 하는 것으로 간주 되며,이는 이동성 클라이언트가 다른 클라이언트 유형으로 서만 사용할 수 있는 것으로 서, 회의 조작의 예외입니다. 회의에 참여 하는 데 사용 됩니다.

</div>

<div>

## <a name="persistent-chat"></a>영구 채팅

등록 된 사용자 중 25%가 영구 채팅 세션에 포함 되는 경우 다음 특성을 사용 하는 것으로 가정 합니다.

  - 사용자 당 평균 1.5 채팅 채팅방

  - 각 채팅방은 평균 10 명의 사용자를 대상으로 하 여 시간당 12 회 폴링 요청을 생성 합니다.

</div>

<div>

## <a name="response-group-and-call-park"></a>응답 그룹 및 통화 공원

등록 된 사용자의 0.15%가 응답 그룹에 속해 있다고 가정 합니다. 사용자의 0.02%가 지정 된 시점에 대기 중인 통화를 보유 하 고 있다고 가정 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

