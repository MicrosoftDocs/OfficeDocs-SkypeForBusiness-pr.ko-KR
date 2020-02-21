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
ms.openlocfilehash: 389d545c18edb4a3c14fc2f0abdf5fb185fcd0ae
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-models-in-lync-server-2013"></a>Lync Server 2013의 사용자 모델

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-10-07_

여기에 설명 된 사용자 모델은 [사용자 모델을 사용 하 여 Lync Server 2013의 용량 계획](lync-server-2013-capacity-planning-using-the-user-models.md)에 설명 된 용량 계획 측정값 및 권장 사항에 대 한 토대를 제공 합니다.

<div>

## <a name="lync-server-2013-user-models"></a>Lync Server 2013 사용자 모델

다음 표에서는 Lync Server 2013의 등록, 연락처, IM (인스턴트 메시징) 및 현재 상태에 대 한 사용자 모델을 설명 합니다.

### <a name="environment-and-registration-user-model"></a>환경 및 등록 사용자 모델

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>범주</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>배포 크기 및 분포</p></td>
<td><p>모델링하는 대상은 대규모 배포로, 3개의 중앙 사이트와 사이트당 하나의 프런트 엔드 풀이 구축됩니다.</p></td>
</tr>
<tr class="even">
<td><p>Active Directory 사용자의 비율(%)</p></td>
<td><p>조직의 모든 Active Directory 사용자 중 70%가 Lync Server에 대해 사용 된다고 가정 합니다. 이 사용 가능한 사용자의 80%가 매일 Lync Server에 로그온 되어 있습니다 (80% 동시). 동시 사용자 수는 이 섹션의 나머지 부분에 나오는 수치의 기본 요소입니다.</p></td>
</tr>
<tr class="odd">
<td><p>Active Directory 변경 사항</p></td>
<td><p>총 사용자의 0.5%가 매주 Active Directory의 Lync에 대해 만들어지고 사용 하도록 설정 되어 있으며, 총 사용자의 0.5%는 Active Directory 및 각 주에 Lync에서 사용 하지 않도록 설정 되어 있다고 가정 합니다. 사용자의 5%는 매주 하나 이상의 Active Directory 특성을 변경합니다.</p></td>
</tr>
<tr class="even">
<td><p>Active Directory 메일 그룹</p></td>
<td><p>조직의 Active Directory 메일 그룹 수는 Active Directory에 있는 모든 사용자 수의 3배와 동일한 것으로 가정합니다. 메일 그룹의 크기는 다음과 같습니다.</p>
<ul>
<li><p>64%: 2-30명의 사용자</p></li>
<li><p>13%: 31-50명의 사용자</p></li>
<li><p>10%: 51-100명의 사용자</p></li>
<li><p>13%: 101-500명의 사용자</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>VoIP(Voice over IP) 사용자</p></td>
<td><p>Lync Server 사용자의 60%는 UC (통합 통신)를 사용 하도록 설정 되어 있습니다 (즉, 전화 번호는 Lync Server에서 소유 함).</p></td>
</tr>
<tr class="even">
<td><p>등록된 클라이언트 분포</p></td>
<td><p>클라이언트의 65%는 Lync 및 Lync Phone Edition을 포함 하 여 Lync 2013 소프트웨어를 실행 합니다.</p>
<p>이전 버전의 Lync에서 클라이언트 소프트웨어를 실행 하는 클라이언트의 30%</p>
<p>Lync Web App을 사용 하는 클라이언트의 5%</p>
<p>이동성을 사용 하도록 설정 하면 사용자의 40%가 이전에 설명한 다른 모든 등록 된 클라이언트 옵션과 동시에 모바일 기능을 사용 하 고 있다고 가정 합니다. 이 경우 클라이언트의 다중 현재 상태 (MPOP) 비율은 1:1.9입니다. 모바일을 사용하지 않도록 설정하면 MPOP 비율이 1:1.5가 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>원격 사용자 분포</p></td>
<td><p>사용자의 70%는 내부에서 연결합니다.</p>
<p>사용자의 30%는 에지 서버 및 디렉터를 통해 연결합니다.</p></td>
</tr>
<tr class="even">
<td><p>대화 상대 분포</p></td>
<td><p>사용자가 유지할 수 있는 최대 대화 상대 수는 1,000명입니다. 대화 상대 수가 1,000명인 사용자는 1% 미만입니다. 또한 25% 미만의 사용자는 대화 상대 수가 100명 이상입니다.</p>
<p>사용자의 대화 상대 중 평균 80명은 공용 클라우드를 통해 연결합니다. 이러한 사용자의 비율은 다음과 같습니다.</p>
<ul>
<li><p>대화 상대의 50%는 조직 내에 있습니다. 이러한 사용자의 10%는 방화벽 외부에서 연결하는 원격 사용자입니다.</p></li>
<li><p>대화 상대의 40%는 공용 클라우드 사용자(예: AOL, Yahoo!, MSN, Google Talk 사용자)입니다.</p></li>
<li><p>대화 상대의 10%는 페더레이션 파트너의 사용자입니다.</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>2012 년 9 월 1 일, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")를 신규 또는 갱신 동의를 위해 더 이상 구매할 수 없습니다. 활성 라이선스를 사용 하는 고객은 Yahoo!에 계속 페더레이션 할 수 있습니다. 서비스 종료 날짜까지 메신저 AOL 및 Yahoo!의 6 월 2014 일 종료 날짜 이 발표 되었습니다. 자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공용 인스턴트 메신저 연결에 대 한 지원을</A>참조 하세요.</P>
> <LI>
> <P>PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!을 페더레이션 하는 데 필요한 사용자별 구독 라이선스입니다. 메신저로. 이 서비스를 제공 하는 Microsoft의 기능은 기본 규약에 따라 세로 맞춤에 사용 되는 Yahoo!에 대 한 지원을 받을 수 있습니다.</P>
> <LI>
> <P>이전 보다 Lync는 전 세계의 조직과 조직 간에 연결 하는 강력한 도구입니다. Windows Live Messenger와 페더레이션 하려면 Lync Standard CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다. Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 도달할 수 있도록 하는이 목록에 Skype 페더레이션이 추가 됩니다.</P></LI></UL>


</div></li>
</ul>
<p>사용자의 대화 상대 중 평균 50명은 공용 클라우드 연결을 사용하지 않습니다. 이러한 사용자의 비율은 다음과 같습니다.</p>
<ul>
<li><p>대화 상대의 80%는 조직 내에 있습니다. 이러한 사용자의 10%는 방화벽 외부에서 연결하는 원격 사용자입니다.</p></li>
<li><p>대화 상대의 20%는 페더레이션 파트너의 사용자입니다.</p>
<p>각 사용자에게는 대화 상대 목록에 하나의 메일 그룹이 있습니다. 성능 테스트를 위해 메일 그룹은 항상 확장된 것으로 가정합니다.</p></li>
</ul>
<p>25%의 사용자 대화 상대가 XMPP를 사용합니다.</p></td>
</tr>
<tr class="odd">
<td><p>세션 시간</p></td>
<td><p>평균 사용자 로그온 세션은 12시간 동안 지속됩니다. 모든 사용자가 세션 시작 후 120분 이내에 로그온합니다.</p></td>
</tr>
</tbody>
</table>


### <a name="im-and-presence-user-model"></a>메신저 및 현재 상태 사용자 모델

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>범주</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>피어 투 피어 메신저 세션</p></td>
<td><p>각 사용자는 하루 평균 6개의 피어 투 피어 메신저 세션에 참가합니다.</p>
<p>세션당 메신저 메시지 수는 10개입니다.</p>
<p>각 메시지는 SIP 정보 메시지 두 개와 SIP 200 정상 메시지 2 개 ("&lt;이름이&gt; 입력 됨"와 같은 상태 표시기의 경우)와 일치 합니다.</p></td>
</tr>
<tr class="even">
<td><p>현재 상태 폴링</p></td>
<td><p>전반적으로 현재 상태 폴링을 사용자당 1시간에 평균 60개 설문으로 가정합니다. 각 사용자에 대해 다음과 같은 평균을 가정합니다.</p>
<ul>
<li><p>사용자의 조직 탭(대화 상대 목록이 아님)에 있는 사용자의 현재 상태에 대해 하루에 하나의 설문. 사용자의 조직 탭에 있는 대화 상대가 아닌 사용자는 평균 15명입니다. 대화 상대 카드를 보는 작업은 하루에 두 번 수행합니다.</p></li>
<li><p>사용자가 대화를 시작하기 위해 다른 사용자를 클릭할 때마다 하나의 현재 상태 설문(1시간에 평균 한 번)</p></li>
<li><p>시간당 6번의 사용자 검색. 검색이 수행될 때마다 일괄 설문이 검색 결과 목록 내의 모든 사람에게 전송됩니다. 검색 결과의 평균 크기는 20으로 가정됩니다. 검색 결과가 화면에 유지되면 일괄 설문은 5분 간격으로 새로 고쳐집니다. 여기서는 시간당 두 번의 새로 고침이 있는 것으로 가정합니다.</p></li>
<li><p>사용자가 Outlook에서 전자 메일을 열거나 미리 볼 때 전자 메일의 받는 사람 및 참조 필드에 있는 사용자의 현재 상태 설문(1시간에 평균 5개의 전자 메일, 전자 메일당 4명의 사용자)</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>현재 상태 구독</p></td>
<td><p>한 사용자가 다른 사용자를 대화 상대로 추가한 경우 첫 번째 사용자는 두 번째 사용자에 대한 5개 정보 범주를 <em>구독</em>할 수 있습니다. 이러한 정보 범주의 업데이트는 첫 번째 사용자에게 자동으로 전송됩니다.</p>
<p>각 클라이언트의 경우 단일 일괄 구독 요청이 전송되어 평균 대화 상대 40명의 현재 상태를 가져오고 추가적으로 40개의 대화를 통해 페더레이션 대화 상대의 현재 상태를 가져옵니다.</p>
<p>확장된 메일 그룹 구성원의 현재 상태는 폴링이 아닌 영구 현재 상태 구독을 통해 확인되고 각각 2시간마다 사용자당 1번의 확장으로 모델링됩니다.</p>
<p><em>단기 구독</em>은 사용자가 로그인하고 모든 사용자의 대화 상대에 대한 일괄 구독이 발생한 후 바로 로그오프한 경우에 발생합니다. 사용자당 1시간에 6번의 단기 구독, 즉 각 구독이 10분간 지속된다고 가정합니다.</p></td>
</tr>
<tr class="even">
<td><p>현재 상태 게시</p></td>
<td><p>현재 상태는 사용자당 1시간에 평균 4회, 최대 6회까지 게시됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>현재 상태 문서 크기</p></td>
<td><p>완전한 현재 상태 문서의 평균 크기는 4K, 최대 25K로 가정됩니다.</p></td>
</tr>
</tbody>
</table>


다음 표에서는 주소록 사용에 대한 사용자 모델을 설명합니다.

### <a name="address-book-usage-user-model"></a>주소록 사용 사용자 모델

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>주소록 검색 모드</th>
<th>Usage</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>주소록 웹 쿼리만(모든 쿼리는 주소록 웹 쿼리 서비스에 의해 수행됨)</p></td>
<td><p>사용자당 하루 4번의 접두어 쿼리</p>
<p>사용자당 하루 60번의 정확한 검색 쿼리. 이 중 40%는 일괄 처리되고(쿼리당 평균 20명의 대화 상대), 나머지 60%는 단일 대화 상대에 대한 쿼리입니다.</p>
<p>사용자당 하루 25번의 사진 쿼리. 24번은 단일 사전에 대한 쿼리이고, 나머지 하나는 평균 20명의 대화 상대에 대한 일괄 쿼리입니다.</p>
<p>사용자당 하루에 한 번의 전체 조직 검색 쿼리</p></td>
</tr>
<tr class="even">
<td><p>혼합 모드(주소록 파일과 사용된 웹 쿼리). 기본 모드입니다.</p></td>
<td><p>두 가지 유형의 쿼리(사진 및 전체 조직 검색 쿼리)만 네트워크로 이동합니다.</p>
<p>사용자당 하루 25번의 사진 쿼리. 24번은 단일 사전에 대한 쿼리이고, 나머지 하나는 평균 20명의 대화 상대에 대한 일괄 쿼리입니다.</p>
<p>사용자당 하루에 한 번의 전체 조직 검색 쿼리</p></td>
</tr>
</tbody>
</table>


다음 표에서는 회의 모델에 대해 설명합니다.

### <a name="conferencing-model"></a>회의 모델

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>범주</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>예약 된 모임 &quot;및 모임&quot; 시작 모임</p></td>
<td><p>60%는 예약, 40%는 비예약</p>
<p>예약된 모임의 경우 80%는 회의(되풀이 회의)에 할당되고, 10%는 1회성 공개 모임, 8%는 1회성 익명 모임, 2%는 1회성 폐쇄형 모임으로 가정됩니다.</p></td>
</tr>
<tr class="even">
<td><p>회의 클라이언트 분포</p></td>
<td><p>예약 모임의 경우</p>
<ul>
<li><p>65%의 회의 사용자가 Lync 2013을 사용 합니다.</p></li>
<li><p>회의 사용자의 5%가 Microsoft Lync Web App을 사용 합니다.</p></li>
<li><p>회의 사용자의 30%는 Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007 및 Microsoft Office Communicator Web Access (2007 release)를 포함 하 여 이전 버전의 클라이언트를 사용 합니다.</p></li>
</ul>
<p>예약되지 않은 모임의 경우</p>
<ul>
<li><p>70%의 회의 사용자가 Lync 2013을 사용 합니다.</p></li>
<li><p>회의 사용자의 30%는 Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007 및 Microsoft Office Communicator Web Access (2007 release)를 포함 하 여 이전 버전의 클라이언트를 사용 합니다.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>모임 동시성</p></td>
<td><p>사용자의 5%가 근무 시간 중에 회의에 참가합니다. 따라서 80,000명 사용자 풀의 경우 최대 4,000명의 사용자가 동시에 회의에 참가할 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>모임 오디오 분포</p></td>
<td><p>40%가 VoIP 오디오 및 전화 접속 회의 혼합(VoIP 사용자와 전화 접속 사용자의 비율 3:1)</p>
<p>35%가 VoIP 오디오만 사용</p>
<p>15%가 전화 접속 회의 오디오만 사용</p>
<p>10%가 오디오 사용 안 함(메신저 전용 회의, 사용자당 평균 5개의 메시지 전송)</p></td>
</tr>
<tr class="odd">
<td><p>회의의 미디어 혼합</p></td>
<td><p>회의의 75%가 웹 회의(오디오 + 다른 공동 작업 형식)</p>
<p>이러한 회의에 사용되는 다른 공동 작업 방법은 다음과 같습니다.</p>
<div>

> [!NOTE]  
> 한 회의에서 여러 공동 작업 방법을 사용할 수 있으므로 합계가 100%를 초과합니다.


</div>
<ul>
<li><p>50%가 응용 프로그램 공유 추가(한 사용자가 보내는 데이터는 초당 최대 1.1MB)</p></li>
<li><p>50%가 메신저 추가(사용자당 평균 2가지의 메신저)</p></li>
<li><p>20%가 데이터 공동 작업 추가(PowerPoint 또는 화이트보드 추가). 이 경우 회의당 평균 2개의 PowerPoint 파일을 발표하고, 포함된 비디오가 없는 경우 평균 PowerPoint 파일 크기는 10MB, 포함된 비디오가 있으면 평균 30MB이며, 화이트보드당 평균 주석 수는 20개입니다.</p></li>
<li><p>20%가 비디오 추가. 이들 가운데 70%는 여러 보기의 비디오를 사용하며 각 사용자는 2~3개의 비디오 스트림을 수신합니다.</p></li>
<li><p>15%가 공유 메모 추가</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>모임 참가자 분포</p></td>
<td><p>50%는 인증된 내부 사용자</p>
<p>25%는 인증된 원격 사용자</p>
<p>15%는 익명 사용자</p>
<p>10%는 페더레이션 사용자</p></td>
</tr>
<tr class="odd">
<td><p>모임 참가 분포</p></td>
<td><p>사용자는 처음 5분 이내에 모임에 참가하는 것으로 시뮬레이션합니다.</p></td>
</tr>
</tbody>
</table>


일반 프런트 엔드 풀에서 Lync Server 2013에는 지원 되는 최대 모임 크기인 250 사용자가 포함 되어 있습니다. 각 풀은 한 번에 하나의 250명 규모 모임을 호스팅할 수 있습니다. 이 대규모 모임 중에 다른 소규모 회의를 호스팅할 수도 있습니다. 추가적으로 이러한 모임을 호스팅하는 전용 풀을 설정하여 최대 1,000명의 사용자를 모임에 지원할 수도 있습니다. 자세한 내용은 [Lync Server 2013의 대규모 모임 지원](lync-server-2013-support-for-large-meetings.md)를 참조 하세요.

회의가 시뮬레이션된 환경은 다음과 같습니다.

  - 85%의 회의에 4명의 참가자가 있습니다.

  - 10%의 회의에 6명의 참가자가 있습니다.

  - 5%의 회의에 11명의 참가자가 있습니다.

  - 한 번의 대규모 회의에 250명의 사용자가 있습니다.

다음 표에서는 전화 접속 사용자가 포함된 회의에 대한 사용자 모델의 세부 정보를 제공합니다.

### <a name="dial-in-conferencing-user-model"></a>전화 접속 회의 사용자 모델

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>범주</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>인증 됨/익명</p></td>
<td><p>70%의 발신자가 익명으로 참가하고 기록된 이름을 묻는 프롬프트가 나타납니다. 30%는 인증된 사용자로 참가합니다.</p></td>
</tr>
<tr class="even">
<td><p>통화 시간 및 대기 음악</p></td>
<td><p>대기 음악을 제외한 평균 통화 시간: 50초.</p>
<p>전화 접속 사용자의 50%에게 평균 5분간 대기 음악 재생</p></td>
</tr>
<tr class="odd">
<td><p>DTMF(Dual-tone Mtifrequency)</p></td>
<td><p>전화 접속 전용 회의의 15%에 전화 리더가 있습니다. 또한 전화 접속 사용자가 포함된 혼합형 회의의 10%에도 전화 리더가 있습니다.</p>
<p>전화 리더의 20%는 회의당 두 가지 DTMF 명령을 사용합니다.</p></td>
</tr>
<tr class="even">
<td><p>알림 언어</p></td>
<td><p>알림 언어로 영어를 사용하여 시뮬레이션합니다.</p></td>
</tr>
</tbody>
</table>


다음 표에서는 회의 대기실 사용자 모델에 대한 세부 정보를 제공합니다.

### <a name="conference-lobby-user-model"></a>회의 대기실 사용자 모델

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>범주</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>대기실의 사용자 수</p></td>
<td><p>전화 접속 사용자의 5%와 다른 사용자의 25%가 대기실로 이동합니다.</p></td>
</tr>
<tr class="even">
<td><p>대기실에서 입장</p></td>
<td><p>시뮬레이션에서 클라이언트의 시간이 초과되기 전에 발표자가 모든 사용자의 입장을 허용합니다.</p></td>
</tr>
</tbody>
</table>


다음 표에서는 다른 피어 투 피어 세션 사용자 모델에 대해 설명합니다.

### <a name="peer-to-peer-sessions-user-model"></a>피어 투 피어 세션 사용자 모델

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>범주</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>응용 프로그램 공유</p></td>
<td><p>각 사용자는 한 달에 5번 피어 투 피어 응용 프로그램 공유 세션에 참가합니다(하루 평균 0.25세션).</p></td>
</tr>
<tr class="even">
<td><p>파일 전송</p></td>
<td><p>각 사용자는 한 달에 한 번 메신저 세션의 일부로 피어 투 피어 파일 전송 세션에 참가합니다(하루 평균 0.05 세션). 세션에서 전송되는 평균 파일 크기는 1MB입니다.</p></td>
</tr>
</tbody>
</table>


다음 표에서는 정책에 대한 사용자 모델을 설명합니다.

### <a name="policies-user-model"></a>정책 사용자 모델

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>범주</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>회의, 현재 상태 및 보관 정책</p></td>
<td><p>1개의 전역 정책, 10개의 태그 전화 회의 정책, 4개의 보관 정책 및 10개의 태그 현재 상태 정책이 있다고 가정합니다.</p></td>
</tr>
<tr class="even">
<td><p>음성 정책</p></td>
<td><p>사이트당 1개의 전역 정책과 2개의 태그 정책이 있다고 가정합니다. 100%의 사이트에 사이트 정책이 있고 30%의 사용자에게 사용자별 정책이 할당되어 있습니다. 사이트당 하나의 다이얼 플랜 및 사이트당 두 개의 경로가 있다고 가정합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="busy-hour"></a>사용량이 많은 시간

피어 투 피어 세션의 경우 BHCA(Busy Hour Call Attempts)를 사용하여 최대 부하를 계산합니다. 이 음성 산업 용어는 하루 총 통화의 50%가 20% 시간 내에 완료되는 것으로 가정합니다. 이는 다음 수식을 통해 계산됩니다.

`BHCA=(total calls * 0.5) / 1.6`

성능 테스트를 통해 하루 1.6시간 이상의 사용량이 많은 시간에 VoIP와 다른 피어 투 피어 세션을 실행하여 사용량이 많은 시간을 시뮬레이션했습니다.

회의 최대 부하는 하루 8시간 동안 이루어지는 모든 회의의 75%가 4시간의 피크 시간 동안 발생하는 것으로 가정합니다. 이러한 피크 시간의 부하는 평균 회의 부하의 1.5배입니다.

</div>

<div>

## <a name="enterprise-voice-to-pstn-calls"></a>Enterprise Voice to PSTN 통화

Enterprise Voice 통화에는 다음과 같은 가정이 적용 됩니다.

  - 사용자의 50%가 Enterprise Voice를 사용 하도록 설정 되었으며, 이러한 사용자의 60%는 PSTN 통화에 사용 하도록 설정 됩니다.

  - PSTN 통화를 사용하는 개별 사용자는 사용량이 많은 시간에 4번의 PSTN 통화를 하고 각 통화는 3분간 지속됩니다.

  - PSTN 음성 통화의 65%가 미디어 바이패스를 사용합니다.

</div>

<div>

## <a name="mobility"></a>이동성

40%의 등록된 사용자에게 모바일 기능이 허용되는 것으로 가정합니다. 모바일 기능을 사용하는 각 사용자의 경우 모바일 클라이언트의 작업이 해당 사용자의 다른 MPOP 인스턴스의 작업에 추가됩니다. 단, 모바일 클라이언트가 회의 상호 작용을 위해 회의 참가에 사용되는 또 다른 유형의 클라이언트인 경우는 제외합니다.

</div>

<div>

## <a name="persistent-chat"></a>영구 채팅

등록된 사용자의 25%가 다음과 같은 특징으로 영구 채팅 세션에 연관된다고 가정합니다.

  - 사용자당 평균 1.5개의 채팅방

  - 각 채팅방에는 시간당 평균 10명의 사용자를 대상으로 하는 12개의 설문 조사 요청이 발생합니다.

</div>

<div>

## <a name="response-group-and-call-park"></a>응답 그룹 및 통화 대기

등록된 사용자의 0.15%가 응답 그룹에 속하고, 등록된 사용자의 0.02%가 지정한 시점에 통화 대기 상태인 것으로 가정합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

