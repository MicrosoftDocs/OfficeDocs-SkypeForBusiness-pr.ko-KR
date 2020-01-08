---
title: Lync Server 2013 소개
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Introduction to Lync Server
ms:assetid: 99dd6b65-e591-421f-852b-ee9fe9588998
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398795(v=OCS.15)
ms:contentKeyID: 48184885
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df182c8d58d6f1e60b164fbb28299945f6a8cba3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="introduction-to-lync-server-2013"></a>Lync Server 2013 소개

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-10-07_

Lync Server 2013 및 해당 클라이언트 소프트웨어 (예: Lync 2013)는 사용자가 실제 위치에 관계 없이 새로운 방법으로 연결 하 고 연결을 유지할 수 있도록 합니다. Lync와 Lync 서버는 사용자가 단일 클라이언트 인터페이스에서 통신 하는 다양 한 방법, 그리고 통합 플랫폼으로 배포 되며 단일 관리 인프라를 통해 관리 됩니다.

이 표 및 다음 섹션에서는 사용자에 게 제공 되는 Lync Server의 주요 기능 집합 또는 *작업 부하*에 대해 설명 합니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>튜닝</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>메신저 및 현재 상태</p></td>
<td><p>인스턴트 메시지 (IM) 및 현재 상태를 통해 사용자 들이 쉽고 효과적으로 서로를 찾고 통신할 수 있습니다.</p>
<p>IM은 대화 기록과 인스턴트 메시징 플랫폼을 제공 하며, MSN/Windows Live, Yahoo!, AOL, Google 대화 등의 공용 IM 네트워크 사용자와 공용 IM 연결을 지원 합니다.</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>2012 년 9 월 1 일부 터, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")는 신규 또는 갱신 계약에 대해 더 이상 구매할 수 없습니다. 활성 라이선스가 있는 고객은 계속 Yahoo!에 페더레이션 할 수 있습니다. 서비스 종료 날짜가 될 때까지 메신저를 종료 합니다. AOL 및 Yahoo!에 대 한 6 월 2014의 기간 종료 날짜 님이 발표 되었습니다. 자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공개 인스턴트 메신저 연결 지원을</A>참조 하세요.</P>
> <LI>
> <P>PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!에 페더레이션 하는 데 필요한 사용자별 사용자 단위 구독 라이선스입니다. 받으려면. 이 서비스를 제공 하는 Microsoft의 기능은 기본 계약 인 Yahoo!에 대 한 지원을 받을 수 있습니다.</P>
> <LI>
> <P>이전 보다 훨씬 더 많은 수의 Lync는 전세계의 조직과 사용자 간에 연결 하는 강력한 도구입니다. Windows Live Messenger를 사용 하는 페더레이션에서는 Lync 표준 CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다. Skype 페더레이션이이 목록에 추가 되어 Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 연락할 수 있도록 합니다.</P></LI></UL>


</div>
<p>현재 상태는 <strong>사용</strong> 가능 여부와 같은 일반적인 <strong>상태를 사용</strong>하 여 통신 하는 사용자의 개인 사용 가능 시간 및 willingness를 설정 하 고, <strong>오른쪽 뒤로</strong> , <strong>방해</strong>금지 등의 자세한 상태를 함께 표시 합니다. 이 풍부한 현재 상태 정보를 통해 다른 사용자가 즉시 효과적인 의사 소통을 선택할 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>회의</p></td>
<td><p>Lync Server에는 예정 된 모임 및 임시 모임의 두 가지에 대 한 IM 회의, 오디오 회의, 웹 회의, 영상 회의, 응용 프로그램 공유에 대 한 지원이 포함 됩니다. 이러한 모든 모임 유형은 단일 클라이언트에서 지원 됩니다. Lync 서버는 또한 전화 접속 회의를 지원 하므로, PSTN (공개 통신 네트워크) 전화의 사용자가 회의의 오디오 부분에 참가할 수 있습니다.</p>
<p>회의가 실시간으로 변경 및 확대 될 수 있습니다. 예를 들어 단일 회의는 몇 명의 사용자 사이에서 인스턴트 메시지로 시작 하 고, 데스크톱 공유를 사용 하 여 음성 회의를 하 고, 쉽고 빠르게 대화 흐름을 방해 하지 않고 더 많은 청중에 게 전환할 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Enterprise Voice</p></td>
<td><p><em>Enterprise Voice</em> 는 Lync Server의 Voip (Voice Over 인터넷 프로토콜)를 제공 합니다. 기존 PBX (개인 브랜치 교환) 시스템을 개선 하거나 대체 하는 음성 옵션을 제공 합니다. IP PBX의 완벽 한 전화 통신 기능 외에도 엔터프라이즈 음성은 다양 한 현재 상태, 메신저 대화, 공동 작업, 모임에 통합 되어 있습니다. 통화 응답, 보류, 이력서, 이전, 앞으로, 접속해 등의 기능을 직접 지원 하 고, 개인 설정 된 스피드 다이얼 키가 연락처 목록으로 바뀌고 자동 인터 컴 메신저 대화로 대체 됩니다.</p>
<p>Enterprise Voice는 호출 허용 제어 (CAC), 지사 survivability, 데이터 탄력성을 위한 확장 옵션을 통해 고가용성을 지원 합니다.</p></td>
</tr>
<tr class="even">
<td><p>원격 사용자를 위한 지원</p></td>
<td><p>이러한 원격 사용자에 대 한 연결을 제공 하기 위해 <em>Edge 서버</em> 라고 하는 서버를 배포 하 여 현재 조직의 방화벽 외부에 있는 사용자에 대해 전체 Lync Server 기능을 제공할 수 있습니다. 이러한 원격 사용자는 Lync 2013이 설치 된 개인 컴퓨터, 휴대폰 또는 웹 인터페이스를 사용 하 여 회의에 연결할 수 있습니다.</p>
<p>Edge 서버를 배포 하는 경우에도 파트너 또는 공급 업체 조직과 <em>페더레이션</em> 할 수 있습니다. 페더레이션 관계를 통해 사용자는 페더레이션 사용자를 대화 상대 목록에 배치할 수 있고, 현재 상태 정보 및 인스턴트 메시지를 이러한 사용자와 연결 하 고, 음성 통화, 영상 통화, 회의에 초대 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>모바일 클라이언트 지원</p></td>
<td><p>또한 Lync Server mobility services를 통해 사용자는 지원 되는 Apple iOS, Android, Windows Phone 또는 Nokia 모바일 장치를 사용 하 여 Lync 기능에 액세스 하 고 인스턴트 메시지 보내기 및 받기, 연락처 보기 등의 작업을 수행할 수 있습니다. 현재 상태 보기 또한 모바일 장치는 클릭 하 여 회의에 참가 하 고, 회사, 단일 전화 접속, 음성 메일 및 부재 중 통화를 통해 전화를 걸 수 있는 몇 가지 엔터프라이즈 음성 기능을 지원 합니다. 푸시 알림은 백그라운드에서 실행 되는 응용 프로그램을 지원 하지 않는 모바일 장치 에서도 지원 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>다른 제품과 통합</p></td>
<td><p>Lync Server는 다른 여러 제품과 통합 되어 사용자와 관리자에 게 추가 혜택을 제공 합니다.</p>
<p>모임 도구는 주최자가 모임을 예약 하거나 한 번의 클릭으로 즉석 회의를 시작할 수 있도록 Outlook에 통합 되어 참석자 들이 쉽게 참가할 수 있도록 해 주는 것입니다.</p>
<p>현재 상태 정보는 Outlook과 SharePoint에 통합 됩니다.</p>
<p>Exchange UM (통합 메시징)는 여러 가지 통합 기능을 제공 합니다. 사용자는 Lync Server 내에서 새로운 음성 메일을 사용 하 고 있는지 확인할 수 있습니다. Outlook 메시지에서 재생 단추를 클릭 하 여 오디오 음성 메일을 듣거나 알림 메시지에서 음성 사서함의 기록을 볼 수 있습니다.</p>
<p>또한 Exchange 2013를 사용 하 여 Lync Server 2013를 실행 하면 두 제품의 클라이언트에서 액세스할 수 있는 통일 된 연락처 저장소와 같은 몇 가지 새로운 기능과 Exchange 2013 데이터베이스에 저장 된 연락처의 고해상도 사진이 제공 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>간단한 배포</p></td>
<td><p>서버 및 클라이언트를 계획 하 고 배포 하는 데 도움이 되도록 Lync Server는 토폴로지 작성기를 제공 합니다.</p>
<p>토폴로지 작성기는 Lync Server의 설치 구성 요소입니다. 토폴로지 작성기를 사용 하 여 계획 된 토폴로지를 만들고, 조정 하 고, 게시 합니다. 또한 서버 설치를 시작 하기 전에 토폴로지의 유효성을 검사 합니다. 개별 서버에 Lync Server를 설치 하는 경우 설치 프로그램은 토폴로지에서 지시한 대로 서버를 배포 합니다.</p></td>
</tr>
<tr class="even">
<td><p>간단한 관리</p></td>
<td><p>Lync Server를 배포한 후 다음과 같은 강력 하 고 능률적인 관리 도구가 제공 됩니다.</p>
<ul>
<li><p>중앙 구성 관리-변경 내용을 중앙에서 관리 하 고 전체 배포에 신속 하 게 복제할 수 있습니다.</p></li>
<li><p>관리자를 위한 웹 기반 그래픽 사용자 인터페이스인 Lync 서버 컨트롤 패널 이 웹 기반 UI를 사용 하 여 Lync Server 관리자는 컴퓨터에 특별 한 관리 소프트웨어를 설치 하지 않고도 회사 네트워크의 어디에서 나 시스템을 관리할 수 있습니다.</p></li>
<li><p>Windows PowerShell 명령줄 인터페이스를 기반으로 하는 Lync Server 관리 셸 명령줄 관리 도구 제품의 모든 측면을 관리 하기 위한 풍부한 명령 집합을 제공 하 고 Lync Server 관리자가 익숙한 도구를 사용 하 여 반복적인 작업을 자동화할 수 있습니다.</p></li>
</ul></td>
</tr>
</tbody>
</table>


메신저 대화 및 현재 상태 기능은 모든 Lync Server 배포에 자동으로 설치 되지만, 조직의 요구 사항에 맞게 배포를 조정 하기 위해 회의, Enterprise Voice, 원격 사용자 액세스를 배포할지 선택할 수 있습니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013의 메신저 및 현재 상태](lync-server-2013-im-and-presence.md)

  - [Lync Server 2013의 회의](lync-server-2013-conferencing.md)

  - [Lync Server 2013의 Enterprise Voice](lync-server-2013-enterprise-voice.md)

  - [Lync Server 2013의 확장성](lync-server-2013-scalability.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

