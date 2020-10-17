---
title: 'Lync Server 2013: Lync 2013의 클라이언트 상호 운용성'
description: 'Lync Server 2013: Lync 2013의 클라이언트 상호 운용성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client interoperability in Lync 2013
ms:assetid: 0f126571-91a2-45d5-855c-1e4ddb45fc04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204672(v=OCS.15)
ms:contentKeyID: 48183417
ms.date: 03/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ea6e90d9479f03dd6d946787e70a2b3cc078699
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549614"
---
# <a name="client-interoperability-in-lync-2013"></a>Lync 2013의 클라이언트 상호 운용성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2016-03-04_

이 항목에서는 Microsoft Lync Server 2013 클라이언트가 이전 버전의 Lync Server 및 Office Communications Server와 함께 사용 되 고 클라이언트와 상호 작용 하는 기능에 대해 설명 합니다.

<div>

## <a name="server-and-client-compatibility"></a>서버 및 클라이언트 호환성

다음 표에는 지원 되는 클라이언트 버전 및 서버 버전 조합이 나와 있습니다. 이 테이블은 클라이언트가 지정 된 서버에 연결 하려고 할 때 로그인이 지원 되는지 여부를 나타냅니다. Lync Server 2013는 이전 클라이언트 버전을 지원 합니다. 또한 이전 릴리스와 달리 Lync Server 2010는 새 Lync 2013 클라이언트를 지원 합니다. 이를 통해 Lync Server 2010에서 업그레이드 하는 조직은 Lync Server 업그레이드에 관계 없이 새 클라이언트를 롤아웃할 수 있습니다.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>클라이언트</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>지원</p></td>
<td><p>Supported5</p></td>
<td><p>지원되지 않음</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>지원</p></td>
<td><p>지원</p></td>
<td><p>지원되지 않음</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2013</p></td>
<td><p>지원</p></td>
<td><p>지원되지 않음</p></td>
<td><p>지원되지 않음</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>지원</p></td>
<td><p>지원</p></td>
<td><p>지원되지 않음</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Attendant</p></td>
<td><p>지원</p></td>
<td><p>지원</p></td>
<td><p>지원되지 않음</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 그룹 채팅</p></td>
<td><p>1</p></td>
<td><p>2</p></td>
<td><p>해당 없음</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2010</p></td>
<td><p>지원되지 않음</p></td>
<td><p>않음</p></td>
<td><p>지원되지 않음</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendee</p></td>
<td><p>Supported3 아님</p></td>
<td><p>지원</p></td>
<td><p>지원되지 않음</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperable4</p></td>
<td><p>지원</p></td>
<td><p>지원</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Office Communications Server 2007 R2 Attendant</p></td>
<td><p>지원되지 않음</p></td>
<td><p>않음</p></td>
<td><p>지원</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007</p></td>
<td><p>지원되지 않음</p></td>
<td><p>않음</p></td>
<td><p>지원</p></td>
</tr>
<tr class="even">
<td><p>Office Live Meeting 2007</p></td>
<td><p>지원되지 않음</p></td>
<td><p>않음</p></td>
<td><p>지원</p></td>
</tr>
<tr class="odd">
<td><p>Lync Windows 스토어 앱</p></td>
<td><p>지원</p></td>
<td><p>지원</p></td>
<td><p>지원되지 않음</p></td>
</tr>
</tbody>
</table>


1For 자세한 내용은 [Lync server 2010, 그룹 채팅 또는 Office Communications Server 2007 R2 그룹 채팅에서 Lync server 2013, 영구 채팅 서버로 마이그레이션을](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)참조 하십시오.

2In Lync Server 2010에서 그룹 채팅 기능은 Lync Server 2010 용 타사 트러스트 응용 프로그램을 사용 하 여 그룹 채팅 서버에서 사용할 수 있었습니다. Lync 2013 클라이언트는 Lync Server 2010, 그룹 채팅과 호환 되지 않습니다.

3Lync Web App 2013는 이제 컴퓨터 오디오 및 비디오를 비롯 한 전체 모임 환경을 제공 하며 Lync 2010 참석자의 교체로 간주 됩니다. Lync 2010 참석자는 지원 되지 않는 브라우저 (Internet Explorer 6 또는 Internet Explorer 7) 및 Windows XP를 사용 하는 경우에만 Lync Server 2013에 연결 됩니다.

4The Communicator 2007 R2의 현재 상태 및 IM 기능은 Lync Server 2013과 호환 되지만 회의 기능은 없습니다. Office Communications Server 2007 R2에서 마이그레이션하는 동안 Office Communicator 2007 R2는 현재 상태 및 IM 상호 운용성에 적합 하지만 lync Web App 2013을 사용 하 여 Lync Server 2013 meeting에 참가 해야 합니다.

5 제한에 대 한 자세한 내용은이 항목의 뒷부분에 나오는 "Lync Server 2010 회의의 Lync 2013 클라이언트에 대 한 회의 기능 지원"을 참조 하십시오.

</div>

<div>

## <a name="interoperability-among-clients"></a>클라이언트 간 상호 운용성

Lync Server 2013 릴리스를 사용 하면 다양 한 클라이언트 버전이 피어-투-피어 및 회의 시나리오에서 원활 하 게 상호 작용할 수 있습니다. 이 섹션에서는 사용자가 다른 버전의 클라이언트 및 서버를 사용 하는 다른 사용자와 상호 작용할 때의 기능 가용성에 대해 설명 합니다.

<div>

## <a name="peer-to-peer-feature-support"></a>피어-투-피어 기능 지원

피어 투 피어 기능은 서로 다른 서버 버전에 있고 다른 클라이언트 버전을 사용 하는 사용자에 대해 지원 됩니다. 최종 사용자 환경 및 사용 가능한 기능은 사용자 클라이언트의 기능과 사용자가 로그인 되어 있는 서버의 버전에 일치 합니다. 위의 명령이 반환하는 결과는 다음과 같습니다.

  - 사용자가 이전 클라이언트를 사용 하 여 Lync Server 2013에 로그인 되어 있으면 사용자는에 사용 하는 것과 같은 환경을 갖게 됩니다. Lync Server 2013에 도입 된 새로운 기능은 사용자의 클라이언트를 업그레이드할 때까지 사용할 수 없습니다. 비디오 갤러리 보기, HD 비디오, 업데이트 된 PowerPoint 공유, 모임 입장에서 모든 참석자 오디오 및 비디오 음소거 옵션을 예로 들 수 있습니다. 새로운 기능은 [Lync server 2013의 새로운 회의 기능과](lync-server-2013-new-conferencing-features.md) [lync server 2013의 클라이언트에 대 한](lync-server-2013-what-s-new-for-clients.md)새로운 기능에 설명 되어 있습니다.

  - Lync 2013 클라이언트를 사용 하 여 Lync Server 2010에 로그인 한 사용자는 lync server 2013로 이동할 때까지 Lync Server 2010에서 지원 하지 않는 모든 새 기능을 사용할 수 없습니다.

다음 표에서는 클라이언트가 Lync Server 2013 또는 Lync Server 2010에 로그인 한 피어 투 피어 세션의 기능 가용성을 비교 합니다.

<div>


> [!NOTE]  
> Lync Web App 및 Lync 2010 참석자는 모임 전용 클라이언트이 고이 테이블에 포함 되어 있지 않습니다.



</div>


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>클라이언트</th>
<th>인스턴트 메시징</th>
<th>이들의</th>
<th>음성</th>
<th>비디오</th>
<th>응용 프로그램 공유</th>
<th>파일 전송</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendant</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 모바일</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>Yes1</p></td>
<td><p>예</p></td>
</tr>
<tr class="even">
<td><p>공용 IM (AOL, Yahoo!)</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>공용 IM (MSN, Windows Live Messenger)</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>2012 년 9 월 1 일부 터 신규 또는 갱신 계약에 대 한 Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 (PIC USL)를 더 이상 사용할 수 없습니다. 활성 라이선스를 사용 하는 고객은 Yahoo!에 계속 페더레이션 할 수 있습니다. 서비스 종료 날짜까지 메신저 AOL 및 Yahoo!의 6 월 2014 일 종료 날짜 이 발표 되었습니다. 자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공용 인스턴트 메신저 연결에 대 한 지원을</A>참조 하세요..</P>
> <LI>
> <P>PIC USL은 Lync Server 또는 Office Communications Server가 Yahoo!과 페더레이션 하는 데 필요한 사용자별 구독 라이선스 (매달)입니다. 메신저로. 이 서비스를 제공 하는 Microsoft의 기능은 갱신 되지 않을 기본 규약 인 Yahoo!을 지원 합니다.</P>
> <LI>
> <P>이전 보다 Lync는 전 세계의 조직과 조직 간에 연결 하는 강력한 도구입니다. Windows Live Messenger와 페더레이션 하려면 Lync Standard CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다. Lync 사용자가 IM 및 음성을 통해 수백만 명의 사용자에 게 도달할 수 있도록 하는이 목록에 Skype 페더레이션이 추가 됩니다.</P></LI></UL>



</div>

1 Office Communicator 2007 R2에서는 데스크톱 공유 (및 프로그램 공유 아님)만 사용할 수 있습니다.

<div>


> [!NOTE]  
> Office Communicator 2007 R2와 비즈니스용 Skype 2015 간의 데스크톱 공유는 비즈니스용 Skype 2015 클라이언트 사용자 인터페이스가 적용 되는 경우 최신 클라이언트에서 시작할 수 없습니다.



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a>Lync Server 2010 모임의 Lync 2013 클라이언트에 대 한 회의 기능 지원

사용자가 lync 2013 클라이언트를 사용 하 여 Lync Server 2010 회의에 참가 하면 다음과 같은 예외 사항을 제외 하 고 Lync 2013 클라이언트 기능에 액세스할 수 있습니다.

  - 모임 창에서 사람 아이콘을 가리켜 액세스할 수 있는 **참가자** 관리 옵션에서 **모임 메신저 대화** 상대가 작동 하지 않습니다.

  - 갤러리 보기가 비디오 회의에서 작동 하지 않습니다. 사용자는 모든 스피커가 아닌 활성 발표자만 볼 수 있습니다. **레이아웃 옵션 선택** 목록에서 **갤러리 보기** 를 사용할 수 없음

  - 참가자 목록은 비디오 회의에 기본적으로 표시 됩니다.

  - 참가자 목록에서 사용자를 마우스 오른쪽 단추로 클릭 하는 경우에는 **비디오 스포트라이트** 및 **Pin을 갤러리** 참가자 관리 옵션으로 잠글 수 없습니다.

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a>Lync Server 2013 모임의 회의 기능 지원

Lync Server 2013에서는 계정이 Lync Server 2013로 이동 되 고 Lync 2013 클라이언트에 로그인 한 후 사용자에 게 제공 되는 새로운 회의 기능을 제공 합니다. 비디오 갤러리 보기, HD 비디오, PowerPoint 공유 및 모든 참석자의 오디오 및 비디오를 모임 항목에 음소거 하는 옵션을 예로 들 수 있습니다. 새로운 기능은 [Lync server 2013의 새로운 회의 기능과](lync-server-2013-new-conferencing-features.md) [lync server 2013의 클라이언트에 대 한](lync-server-2013-what-s-new-for-clients.md)새로운 기능에 설명 되어 있습니다.

Lync Server 2013 모임에서는 서로 다른 클라이언트 및 클라이언트 버전을 사용 하는 사용자 및 서버 버전에 따라 특정 회의 기능이 지원 됩니다. 클라이언트가 Lync Server 2013 회의에 참가 하면 사용자는이 표에 나와 있는 기능에 액세스할 수 있습니다.


<table style="width:100%;">
<colgroup>
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
</colgroup>
<thead>
<tr class="header">
<th>클라이언트</th>
<th>피어 투 피어 IM</th>
<th>음성</th>
<th>비디오</th>
<th>응용 프로그램 공유</th>
<th>PowerPoint</th>
<th>파일 전송</th>
<th>Whiteboard</th>
<th>폴링</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예2</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>Yes3</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
<td><p>예</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2 4</p></td>
<td><p>예</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


1 Office Communicator 2007 R2에서는 데스크톱 공유 (및 프로그램 공유 아님)만 사용할 수 있습니다.

2 Lync Server 2013에서는 PowerPoint 파일을 업로드 하는 데 업데이트 된 메커니즘을 사용 합니다. 처음에 Lync Server 2010에 예약 된 모임에 참가 하는 lync Web App 사용자는 PowerPoint 프레젠테이션을 보고 탐색할 수 있지만 PowerPoint 파일을 업로드 하는 것은 불가능 합니다.

3 lync Server 2013에 회의가 예약 되었고 PowerPoint 슬라이드를 Lync 2013 클라이언트에서 업로드 한 경우 Lync 2010 사용자에 게 슬라이드에 대 한 보기 전용 액세스 권한이 있습니다. 반대로, PowerPoint 슬라이드를 Lync 2010 사용자가 업로드 한 경우 Lync Server 2013 사용자는 보기 및 슬라이드를 볼 수 있으며, Office Web Apps 서버가 구성 되어 있는 경우 고해상도 디스플레이, 애니메이션, 화면 전환, 포함 된 비디오 등의 새로운 기능에 액세스 합니다. 자세한 내용은 [Office Web Apps 서버 및 Lync server 2013의 통합 구성을](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)참조 하세요.

4The Communicator 2007 R2의 현재 상태 및 IM 기능은 Lync Server 2013과 호환 되지만 회의 기능은 없습니다. Office Communications Server 2007 R2에서 마이그레이션하는 동안 Office Communicator 2007 R2는 현재 상태 및 IM 상호 운용성에 적합 하지만 lync Web App 2013을 사용 하 여 Lync Server 2013 meeting에 참가 해야 합니다.

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a>추가 기능 지원 예약

다양 한 일정 추가 기능에 대 한 서버 지원은 서버 및 클라이언트 버전 호환성과 일치 합니다. 일반적으로 Lync Server 2013에서는 다음과 같은 예약 추가 기능이 지원 됩니다. 그러나 이전 버전의 추가 기능은 모임 항목에 모든 참석자 오디오 및 비디오를 음소거 하는 옵션과 같은 새로운 Lync 2013 추가 기능 기능을 제공 하지 않습니다.

  - **Lync 2013**     용 온라인 모임 추가 기능 모임 이끌이가 기본적으로 참석자의 오디오 및 비디오가 음소거 된 전화 회의를 예약할 수 있도록 하는 Lync 2010의 온라인 모임 추가 기능과 같은 기능을 제공 합니다. 또한 관리자는 사용자 지정 로고, 지원 URL, 법적 고 지 사항 URL 또는 사용자 지정 바닥글 텍스트를 추가 하 여 조직의 모임 초대를 사용자 지정할 수 있습니다.

  - **Lync 2010**     용 온라인 모임 추가 기능 Lync 모임 예약을 제공 하 고 Office Live Meeting 회의를 예약 하는 기능을 제거 합니다.

  - **Office Communicator 2007 R2 회의 추가 기능**     Office Live Meeting 회의 및 Office Communicator 2007 R2 회의 모두의 일정을 제공 합니다. 

<div>


> [!NOTE]  
> Lync Server 2013에서는 Live Meeting 회의를 예약할 수 없습니다.



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>예약 클라이언트</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013 용 온라인 모임 추가 기능 (Office 2013, Outlook 2010 및 Outlook 2007과 함께 사용할 수 있음)</p></td>
<td><p>지원</p></td>
<td><p>지원 (새 추가 기능 기능을 사용할 수 없음)</p></td>
<td><p>지원되지 않음</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 웹 스케줄러</p></td>
<td><p>지원</p></td>
<td><p>지원되지 않음</p></td>
<td><p>지원되지 않음</p></td>
</tr>
<tr class="odd">
<td><p>Online Meeting Add-in for Lync 2010(Lync 2010용 온라인 모임 추가 기능)</p></td>
<td><p>지원</p></td>
<td><p>지원</p></td>
<td><p>지원되지 않음</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007 R2 회의 추가 기능</p></td>
<td><p>지원되지 않음</p></td>
<td><p>않음</p></td>
<td><p>지원</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a>모임 참가 지원

Lync Server 2013에서 지 원하는 모든 클라이언트는 Lync 2013 모임에 참가할 수 있습니다. Lync Web App은 lync Server 2013 회의에 참가 하는 것과 같은 서버 웹 구성 요소 이므로, 최신 버전의 Lync Web App이 항상 사용 됩니다.

Lync 2013 클라이언트는 Lync 2010 및 Office Communications Server 2007 r 2에서 호스트 되는 모임에 확장 된 기능을 사용할 수 있습니다. 모임 중인 기능은 모임이 호스트 되는 서버의 버전에 따라 제한 됩니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에 대 한 lync Windows 스토어 앱 요구 사항](lync-server-2013-lync-windows-store-app-requirements.md)  
[Lync Server 2013의 새로운 회의 기능](lync-server-2013-new-conferencing-features.md)  
[Lync Server 2013의 새로운 클라이언트 기능](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

