---
title: Lync Server 2013 소개
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Introduction to Lync Server
ms:assetid: 99dd6b65-e591-421f-852b-ee9fe9588998
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398795(v=OCS.15)
ms:contentKeyID: 48184885
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b25a989913db4e76b306eaaf7efba38612a2315
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186871"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="introduction-to-lync-server-2013"></a>Lync Server 2013 소개

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-10-07_

Lync Server 2013 및 해당 클라이언트 소프트웨어 (예: Lync 2013)는 실제 위치에 관계 없이 사용자가 새로운 방식으로 연결 하 고 연결을 유지할 수 있도록 합니다. Lync 및 Lync Server는 사용자가 단일 클라이언트 인터페이스에서 통신 하는 다양 한 방법을 함께 제공 하며, 통합 플랫폼으로 배포 되며 단일 관리 인프라를 통해 관리 됩니다.

이 표 및 다음 섹션에서는 Lync Server에서 사용자에 게 제공 하는 주요 기능 집합 또는 *작업*에 대해 설명 합니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>작업량</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IM 및 현재 상태</p></td>
<td><p>IM(인스턴트 메시징) 및 현재 상태를 통해 사용자는 효율적이고 효과적으로 대화 상대를 찾아 통신할 수 있습니다.</p>
<p>IM은 대화 기록 기능이 있는 인스턴트 메시징 플랫폼을 제공하며 MSN/Windows Live, Yahoo!, AOL 및 Google Talk와 같은 공용 IM 네트워크 사용자와의 공용 IM 연결을 지원합니다.</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>2012 년 9 월 1 일, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")를 신규 또는 갱신 동의를 위해 더 이상 구매할 수 없습니다. 활성 라이선스를 사용 하는 고객은 Yahoo!에 계속 페더레이션 할 수 있습니다. 서비스 종료 날짜까지 메신저 AOL 및 Yahoo!의 6 월 2014 일 종료 날짜 이 발표 되었습니다. 자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공용 인스턴트 메신저 연결에 대 한 지원을</A>참조 하세요.</P>
> <LI>
> <P>PIC USL은 Lync Server 또는 Office Communications Server와 Yahoo!을 페더레이션 하는 데 필요한 사용자별 구독 라이선스입니다. 메신저로. 이 서비스를 제공 하는 Microsoft의 기능은 기본 규약에 따라 세로 맞춤에 사용 되는 Yahoo!에 대 한 지원을 받을 수 있습니다.</P>
> <LI>
> <P>이전 보다 Lync는 전 세계의 조직과 조직 간에 연결 하는 강력한 도구입니다. Windows Live Messenger와 페더레이션 하려면 Lync Standard CAL 외에 추가 사용자/장치 라이선스가 필요 하지 않습니다. Lync 사용자가 IM 및 음성을 사용 하 여 수백만 명의 사용자에 게 도달할 수 있도록 하는이 목록에 Skype 페더레이션이 추가 됩니다.</P></LI></UL>


</div>
<p>현재 상태는 <strong>대화 가능</strong> 또는 <strong>다른 용무 중</strong>과 같은 일반 상태와 <strong>곧 돌아오겠음</strong> 및 <strong>방해 금지</strong>와 같은 보다 상세한 상태를 사용하여 사용자의 개인 상태 및 통신 의사를 설정하고 표시합니다. 이 향상된 현재 상태 정보를 통해 다른 사용자가 효과적인 통신을 즉시 선택할 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>전화</p></td>
<td><p>Lync Server에는 예약 된 모임 및 즉석 회의 모두에 대해 IM 회의, 오디오 회의, 웹 회의, 비디오 회의 및 응용 프로그램 공유에 대 한 지원이 포함 됩니다. 이러한 모임 유형이 모두 단일 클라이언트로 지원됩니다. 또한 Lync Server는 공중 전화망 (PSTN) 전화 사용자가 회의의 오디오 부분에 참가할 수 있도록 전화 접속 회의를 지원 합니다.</p>
<p>전화 회의는 실시간으로 원활하게 변경되고 확대될 수 있습니다. 예를 들어 단일 전화 회의가 소수의 사용자 간에 인스턴트 메시지로 시작되어 데스크톱 공유를 지원하고 대화의 흐름을 중단하지 않고도 더 많은 대상이 즉시 쉽게 참가할 수 있는 오디오 회의로 확대될 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>Enterprise Voice</p></td>
<td><p><em>Enterprise Voice</em> 는 Lync Server의 VoIP (Voice Over Internet Protocol) 제공입니다. 기존 PBX (private branch exchange) 시스템을 향상 시키거나 교체 하기 위한 음성 옵션을 제공 합니다. IP PBX의 전체 전화 통신 기능 외에도 엔터프라이즈 음성은 다양 한 현재 상태, IM, 공동 작업 및 모임과 통합 됩니다. 전화 응답, 보류, 다시 시작, 전송, 정방향 및 divert 같은 기능은 직접 지원 되며, 개인 설정 된 스피드 전화 걸기 키는 연락처 목록으로 바뀌고 자동 intercom이 메신저로 바뀝니다.</p>
<p>Enterprise Voice는 CAC(통화 허용 제어), 지점 지속 가능성 및 확장된 데이터 복구 옵션을 통해 고가용성을 지원합니다.</p></td>
</tr>
<tr class="even">
<td><p>원격 사용자 지원</p></td>
<td><p>이러한 원격 사용자에 대 한 연결을 제공 하기 위해에 <em>지 서버</em> 를 배포 하 여 현재 조직의 방화벽 외부에 있는 사용자에 대해 전체 Lync Server 기능을 제공할 수 있습니다. 이러한 원격 사용자는 Lync 2013이 설치 된 개인 컴퓨터, 휴대폰 또는 웹 인터페이스를 사용 하 여 전화 회의에 연결할 수 있습니다.</p>
<p>또한 에지 서버를 배포하면 파트너 또는 공급업체 조직과 <em>페더레이션</em>할 수 있습니다. 페더레이션 관계를 설정하면 사용자가 대화 상대 목록에 페더레이션 사용자를 추가하고, 이러한 사용자와 현재 상태 정보 및 인스턴트 메시지를 교환하고, 이러한 사용자를 음성 통화, 화상 통화 및 전화 회의에 초대할 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>모바일 클라이언트 지원</p></td>
<td><p>또한 Lync Server mobility services를 사용 하는 경우 사용자는 지원 되는 Apple iOS, Android, Windows Phone 또는 Nokia 모바일 장치를 사용 하 여 Lync 기능에 액세스 하 고 인스턴트 메시지 보내기/받기, 연락처 보기 등의 작업을 수행할 수 있습니다. 현재 상태를 확인 합니다. 또한 모바일 장치에서는 클릭하여 회의 참가, 회사번호로 전화, 단일 번호 연결, 음성 메일, 부재 중 통화 등의 일부 Enterprise Voice 기능도 지원됩니다. 응용 프로그램의 백그라운드 실행을 지원하지 않는 모바일 장치에 대해 푸시 알림도 지원됩니다.</p></td>
</tr>
<tr class="even">
<td><p>다른 제품과 통합</p></td>
<td><p>Lync Server는 다른 여러 제품과 통합 되어 사용자와 관리자에 게 추가적인 이점을 제공 합니다.</p>
<p>모임 도구는 이끌이가 모임을 예약 하거나 한 번의 클릭으로 즉석 회의를 시작 하 여 참가자가 참석할 수 있도록 Outlook에 통합 되어 있습니다.</p>
<p>현재 상태 정보가 Outlook 및 SharePoint에 통합 됩니다.</p>
<p>Exchange UM(통합 메시징)은 여러 가지 통합 기능을 제공합니다. 사용자는 Lync Server 내에서 새 음성 메일을 갖고 있는지 볼 수 있습니다. Outlook 메시지에서 재생 단추를 클릭하여 오디오 음성 메일을 듣거나 알림 메시지에서 음성 메일의 기록을 볼 수 있습니다.</p>
<p>또한 Exchange 2013을 사용 하 여 Lync Server 2013을 실행 하면 두 제품의 클라이언트에서 액세스할 수 있는 통합 연락처 저장소와 같은 몇 가지 새로운 기능과 Exchange 2013 데이터베이스에 저장 된 연락처의 고해상도 사진이 제공 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>간단한 배포</p></td>
<td><p>서버 및 클라이언트를 계획 하 고 배포 하는 데 도움이 되도록 Lync Server에서는 토폴로지 작성기를 제공 합니다.</p>
<p>토폴로지 작성기는 Lync Server의 설치 구성 요소입니다. 토폴로지 작성기를 사용 하 여 계획 된 토폴로지를 만들고, 조정 하 고, 게시 합니다. 또한 서버 설치를 시작하기 전에 토폴로지의 유효성을 검사할 수 있습니다. 개별 서버에 Lync Server를 설치 하는 경우 설치 프로그램은 토폴로지의 지시에 따라 서버를 배포 합니다.</p></td>
</tr>
<tr class="even">
<td><p>관리 용이성</p></td>
<td><p>Lync Server를 배포한 후에는 다음과 같은 강력 하 고 능률적인 관리 도구를 제공 합니다.</p>
<ul>
<li><p>중앙 구성 관리 - 변경 내용을 중앙 집중식으로 관리하고 전체 배포에 빠르게 적용할 수 있도록 합니다.</p></li>
<li><p>Lync Server 제어판, 관리자를 위한 웹 기반 그래픽 사용자 인터페이스 Lync Server 관리자는이 웹 기반 UI를 사용 하 여 컴퓨터에 특수 한 관리 소프트웨어를 설치 하지 않고도 회사 네트워크의 모든 위치에서 시스템을 관리할 수 있습니다.</p></li>
<li><p>Lync Server 관리 셸 명령줄 관리 도구-Windows PowerShell 명령줄 인터페이스를 기반으로 합니다. 이 기능은 제품의 모든 측면을 관리 하기 위한 다양 한 명령 집합을 제공 하며 Lync Server 관리자는 익숙한 도구를 사용 하 여 반복적인 작업을 자동화할 수 있습니다.</p></li>
</ul></td>
</tr>
</tbody>
</table>


모든 Lync Server 배포에 IM 및 현재 상태 기능이 자동으로 설치 되는 동안 회의, Enterprise Voice 및 원격 사용자 액세스를 배포할 것인지 여부를 선택 하 여 조직의 요구에 맞게 배포를 조정할 수 있습니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013의 IM 및 현재 상태](lync-server-2013-im-and-presence.md)

  - [Lync Server 2013의 회의](lync-server-2013-conferencing.md)

  - [Lync Server 2013의 Enterprise Voice](lync-server-2013-enterprise-voice.md)

  - [Lync Server 2013의 확장성](lync-server-2013-scalability.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

