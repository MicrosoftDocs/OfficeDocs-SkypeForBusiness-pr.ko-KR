---
title: 'Lync Server 2013: Lync 2013 호환성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync 2013 compatibility
ms:assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412817(v=OCS.15)
ms:contentKeyID: 51541502
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0af6d5d11494e24ecf54dd2ff06cbee9011814e4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507255"
---
# <a name="lync-2013-compatibility"></a>Lync 2013 호환성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-10-07_

이 섹션에서는 다양 한 버전의 Microsoft Office 제품군, Microsoft Exchange Server, Windows 운영 체제 및 선택한 공용 IM (인스턴트 메시징) 클라이언트를 사용한 Lync 2013의 호환성에 대해 설명 합니다.

<div>

## <a name="office-and-lync-2013"></a>Office 및 Lync 2013

다음 표에서는 다양 한 버전의 Office에서 지 원하는 Lync 2013 기능에 대해 설명 합니다.

### <a name="lync-2013-and-microsoft-office-compatibility"></a>Lync 2013 및 Microsoft Office 호환성

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>기능</th>
<th>Microsoft Office 2003 SP3(서비스 팩 3)(필수) 또는 최신 서비스 팩(권장)</th>
<th>Microsoft Office 2007</th>
<th>Microsoft Office 2010</th>
<th>Microsoft Office 2013</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Outlook 모임 초대 사용자 지정 (로고, 도움말 URL, 고 지 사항, 바닥글 텍스트 추가)</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>예</p></td>
</tr>
<tr class="even">
<td><p>Outlook에서 기본적으로 참석자 오디오 및 비디오를 음소거 하도록 모임 옵션을 구성 합니다.</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>예</p></td>
</tr>
<tr class="odd">
<td><p>Office 및 Lync에서 연락처 목록을 관리 하기 위한 통합 연락처 저장소</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>예 (Exchange 2013 필요) 1</p></td>
</tr>
<tr class="even">
<td><p>고해상도 그림</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>예 (Exchange 2013 필요) 1</p></td>
</tr>
<tr class="odd">
<td><p>Office 설치 프로그램에 통합 된 Lync 2013 설치</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>예</p></td>
</tr>
<tr class="even">
<td><p>OneNote 공유 메모</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>예</p></td>
</tr>
<tr class="odd">
<td><p>PowerPoint 프레젠테이션 콘텐츠</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Outlook 받는 사람 및 참조 필드의 현재 상태</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
</tr>
<tr class="odd">
<td><p>가용성 메뉴에서 전화 회의로 회신</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>예(대화 상대 카드에서)</p></td>
<td><p>예(대화 상대 카드에서)</p></td>
</tr>
<tr class="even">
<td><p>일정 정리 탭의 모임 요청의 현재 상태</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
</tr>
<tr class="odd">
<td><p>수신 된 전자 메일 메시지의 도구 모음 또는 리본에서 IM으로 회신 또는 통화</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
</tr>
<tr class="even">
<td><p>Outlook 보낸 사람 필드의 현재 상태</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
</tr>
<tr class="odd">
<td><p>가용성 메뉴에서 IM 또는 음성으로 회신</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>예(대화 상대 카드에서)</p></td>
<td><p>예(대화 상대 카드에서)</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Word 및 Microsoft Excel 파일(스마트 태그 사용)의 IM 및 현재 상태</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>Microsoft Word 전용</p></td>
<td><p>Microsoft Word 전용</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft SharePoint 사이트(Outlook이 설치되어 있어야 함)의 IM 및 현재 상태</p></td>
<td><p>아니요</p></td>
<td><p>아니요</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
</tr>
</tbody>
</table>


1 자세한 내용은 계획 설명서에서 [Microsoft Lync Server 2013 및 Microsoft Exchange server 2013 통합](lync-server-2013-integrating-with-microsoft-exchange-server-2013.md) 을 참조 하십시오.

다음 기능은 Office 2010 또는 Office 2013 에서만 사용할 수 있습니다.

  - 비디오 통화 및 데스크톱 공유와 같은 확장 된 옵션이 있는 대화 상대 카드

  - Outlook 연락처 찾기 필드의 빠른 검색

  - IM을 사용한 회신 또는 메일, 일정, 연락처 및 작업 폴더에 있는 Outlook 홈 리본에서 호출

  - Outlook To-Do 표시줄의 Lync 대화 상대 목록

  - Office Backstage(파일 탭) 현재 상태, 프로그램 공유 및 파일 전송

  - Microsoft Office SharePoint Workspace 2010(이전의 Microsoft Office Groove 2007)의 현재 상태 메뉴

  - 현재 상태 메뉴 확장성

</div>

<div>

## <a name="exchange-server-and-lync-2013"></a>Exchange Server 및 Lync 2013

다음 표에서는 다양 한 버전의 Exchange Server에 대 한 Lync 2013 지원에 대해 설명 합니다. 확장 MAPI 통화를 처리하려면 클라이언트 컴퓨터에 Outlook을 설치해야 하며 일부 기능의 경우 EWS(Exchange 웹 서비스)를 사용해야 합니다.

### <a name="lync-2013-and-exchange-server-compatibility"></a>Lync 2013 및 Exchange Server 호환성

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Exchange Server 버전</th>
<th>Lync 2013 지원</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Exchange Server 2013</p></td>
<td><p>통합 연락처 저장소, 고해상도 그림 및 보관 통합을 추가 하 여 Exchange Server 2010 지원과 동일 합니다.</p>
<div>

> [!NOTE]  
> 자세한 내용은 <A href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">Microsoft Lync Server 2013 And Microsoft Exchange Server 2013 통합</A>을 참조 하십시오.


</div></td>
</tr>
<tr class="even">
<td><p>Exchange Server 2010</p></td>
<td><p>Exchange Server 2007 지원(및 Exchange 연락처 동기화 추가)과 동일</p></td>
</tr>
<tr class="odd">
<td><p>Exchange Server 2007 SP1(서비스 팩 1)(필수) 또는 최신 서비스 팩(권장)</p></td>
<td><p>다음 기능은 EWS를 통해서만 사용할 수 있습니다.</p>
<ul>
<li><p>대화 내용 폴더에서 항목 읽기 또는 삭제</p></li>
<li><p>음성 메일 항목 읽기 또는 삭제</p></li>
<li><p>확장된 약속 있음/없음 정보 및 모임 제목과 위치 표시</p></li>
</ul>
<p>공용 폴더는 Exchange Server 2007 SP1(서비스 팩 1)(필수) 또는 최신 서비스 팩 또는 릴리스(권장)에서 선택 사항입니다.</p></td>
</tr>
<tr class="even">
<td><p>Exchange Server 2003</p></td>
<td><p>Outlook MAPI만 해당. EWS 전용 기능은 사용할 수 없습니다(이 항목의 뒷부분 참조).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="windows-and-lync-2013"></a>Windows 및 Lync 2013

Lync 2013 및 Windows 지원 가능성에 대 한 자세한 내용은 계획 설명서에서 lync [Server 2013의 lync 클라이언트 소프트웨어 지원](lync-server-2013-lync-client-software-support.md) 을 참조 하십시오.

</div>

<div>

## <a name="macintosh-and-lync-2013"></a>Macintosh 및 Lync 2013

Lync Server 2013에서는 Macintosh 운영 체제를 실행 하는 컴퓨터에서 특정 클라이언트를 지원 합니다. 자세한 내용은 계획 설명서에서 [Lync Server 2013의 lync 클라이언트 소프트웨어 지원](lync-server-2013-lync-client-software-support.md) 를 참조 하십시오.

</div>

<div>

## <a name="public-instant-messaging-clients-and-lync-2013"></a>공용 인스턴트 메시징 클라이언트 및 Lync 2013

공용 IM 연결을 사용 하도록 서버를 구성한 경우 Lync에서는 공용 IM 네트워크에서 다음 기능을 지원 합니다. 현재 상태는 공용 IM 클라이언트에서 지원되는 현재 상태로 필터링됩니다. 자세한 내용은 계획 설명서의 [Lync server 2013에서 공용 인스턴트 메시징 연결 계획](lync-server-2013-planning-for-public-instant-messaging-connectivity.md) 및 작업 설명서의 [lync server 2013에서 외부 액세스 관리](lync-server-2013-manage-external-access-policy-for-your-organization.md) 를 참조 하십시오.

또한 Lync Server 2013의 XMPP 통합 기능을 통해 사용자는 Google 대화와 같은 확장 가능한 메시징 및 현재 상태 프로토콜을 사용 하는 공용 IM 공급자의 사용자와 인스턴트 메시지 및 현재 상태 정보를 교환할 수 있습니다. 자세한 내용은 계획 설명서의 [Lync Server 2013에서 확장 가능한 메시징 및 현재 상태 프로토콜 (XMPP) 페더레이션을 계획](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md) 합니다 .를 참조 하십시오.

### <a name="lync-2013-and-public-im-clients-compatibility"></a>Lync 2013 및 공용 IM 클라이언트 호환성

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>클라이언트</th>
<th>지원되는 기능</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows Live Messenger</p></td>
<td><p>IM, 기본 현재 상태, 오디오/비디오(A/V)*</p></td>
</tr>
<tr class="even">
<td><p>스카이프</p></td>
<td><p>IM, 기본 현재 상태, 오디오</p></td>
</tr>
<tr class="odd">
<td><p>AOL</p></td>
<td><p>IM 및 기본 현재 상태</p></td>
</tr>
<tr class="even">
<td><p>!</p></td>
<td><p>IM 및 기본 현재 상태</p></td>
</tr>
<tr class="odd">
<td><p>Google 대화</p></td>
<td><p>IM 및 기본 현재 상태</p></td>
</tr>
</tbody>
</table>


\*최신 버전의 Windows Live Messenger에서는 A/V가 지원 됩니다. Windows Live Messenger를 사용 하 여 A/V (오디오/비디오) 페더레이션을 구현 하는 경우에는 서버 암호화 수준도 수정 해야 합니다. 기본적으로 암호화 수준은 필수입니다. Lync Server 관리 셸을 사용 하 여이 설정을 지원으로 변경 해야 합니다.

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>2012 년 9 월 1 일, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")를 신규 또는 갱신 동의를 위해 더 이상 구매할 수 없습니다. 활성 라이선스를 사용 하는 고객은 Yahoo!에 계속 페더레이션 할 수 있습니다. 서비스 종료 날짜까지 메신저 AOL 및 Yahoo!의 6 월 2014 일 종료 날짜 이 발표 되었습니다. 자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공용 인스턴트 메신저 연결에 대 한 지원을</A>참조 하세요.</P>
> <LI>
> <P>PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!을 페더레이션 하는 데 필요한 사용자별 구독 라이선스입니다. 메신저로. 이 서비스를 제공 하는 Microsoft의 기능은 기본 규약에 따라 세로 맞춤에 사용 되는 Yahoo!에 대 한 지원을 받을 수 있습니다.</P>
> <LI>
> <P>이전 보다 Lync는 전 세계의 조직과 조직 간에 연결 하는 강력한 도구입니다. Windows Live Messenger와 페더레이션 하려면 Lync Standard CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다.</P></LI></UL>



</div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync 2013의 클라이언트 상호 운용성](lync-server-2013-client-interoperability-in-lync-2013.md)  
[Lync Server 2013의 lync 클라이언트 소프트웨어 지원](lync-server-2013-lync-client-software-support.md)  
[Lync Server 2013의 lync Web App 지원 되는 플랫폼](lync-server-2013-lync-web-app-supported-platforms.md)  
[Lync Server 2013에 대 한 lync Windows 스토어 앱 요구 사항](lync-server-2013-lync-windows-store-app-requirements.md)  


[Lync Server 2013에 대 한 클라이언트 시스템 요구 사항](lync-server-2013-client-system-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

