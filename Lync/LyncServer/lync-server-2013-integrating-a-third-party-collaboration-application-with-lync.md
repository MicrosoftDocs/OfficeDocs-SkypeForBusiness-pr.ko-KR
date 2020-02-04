---
title: Lync를 사용 하 여 타사 공동 작업 응용 프로그램 통합
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating a third-party collaboration application with Lync
ms:assetid: 00b9312c-b0c8-4f79-8b76-05b2d820e197
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398068(v=OCS.15)
ms:contentKeyID: 48183224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82b95f79202cbf96568b98dcb802e97bf4ca2d32
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725868"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a>Lync Server 2013을 사용 하 여 타사 공동 작업 응용 프로그램 통합

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-20_

앱에 대 한 정보를 레지스트리에 추가 하 여 Lync 2013을 타사 온라인 공동 작업 응용 프로그램과 통합할 수 있습니다. Lync 2013를 사용 하 여 사내 서버, 인터넷 기반 서비스 또는 둘 다에 호스트 된 데이터 회의 세션을 시작할 수 있습니다. 공동 작업 또는 데이터 회의 세션은 연락처 목록 또는 기존 인스턴트 메시징, 음성 또는 비디오 세션에서 시작할 수 있습니다. Lync 2013는 응용 프로그램을 시작 하는 수단 으로만 작동 합니다. 온라인 공동 작업 세션이 시작 된 후 기존의 모든 Lync 2013 대화가 활성 상태로 유지 됩니다.

다음 섹션에서는 Lync 2013를 인터넷 기반 및 서버 기반 공동 작업 응용 프로그램과 통합 하는 방법을 설명 합니다.

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a>인터넷 기반 공동 작업 응용 프로그램을 Lync 2013와 통합

일반적으로 타사 공동 작업 응용 프로그램 통합에 관련 된 단계는 다음과 같습니다.

1.  응용 프로그램에 대 한 정보가 레지스트리에 추가 됩니다.

2.  이끌이는 Lync 2013에 로그인 하 고 데이터 공유 및 공동 작업을 위해 연락처를 선택 합니다. 또는 이끌이는 이미 대화에 있을 수 있으며 데이터 회의 추가를 결정 합니다.

3.  Lync 2013에서 레지스트리를 읽고 공동 작업 응용 프로그램을 시작한 다음 사용자 지정 SIP 메시지 (appINVITE)를 선택 된 참가자에 게 보냅니다.

4.  참가자가 초대를 수락 하 고 공동 작업 응용 프로그램이 각 사용자의 컴퓨터에서 시작 됩니다. Lync 2013는 레지스트리를 사용 하 여 사용할 공동 작업 응용 프로그램을 결정 한 다음 appINVITE 메시지에 포함 된 매개 변수를 사용 하 여 해당 응용 프로그램을 시작 합니다.

다음 표에서는 인터넷 기반 공동 작업 응용 프로그램을 Lync 2013와 통합 하는 데 필요한 레지스트리 항목에 대해 설명 합니다. 이러한 항목은 다음 위치의 레지스트리에 저장 됩니다.

  - HKEY\_로컬\_컴퓨터\\소프트웨어\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\매개 변수

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a>인터넷 기반 공동 작업 응용 프로그램의 레지스트리 항목

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>이름</th>
<th>유형</th>
<th>데이터</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>이름</p></td>
<td><p>REG_SZ</p></td>
<td><p>Lync 2013 메뉴의 응용 프로그램 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>SmallIcon</p></td>
<td><p>REG_SZ</p></td>
<td><p>16 픽셀 x 16 픽셀 아이콘, BMP 또는 PNG에 대 한 경로입니다.</p></td>
</tr>
<tr class="odd">
<td><p>패스가</p></td>
<td><p>REG_SZ</p></td>
<td><p>온라인 공동 작업 응용 프로그램을 시작 하기 위한 참가자 경로입니다.</p></td>
</tr>
<tr class="even">
<td><p>OriginatorPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>온라인 공동 작업 응용 프로그램을 시작 하기 위한 이끌이 경로입니다. 이 경로에는 Parameters 하위 키에 정의 된 대로 하나 이상의 사용자 지정 매개 변수가 포함 될 수 있습니다. 예를 들어<code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>DWORD(32</p></td>
<td><p>0 = 로컬 세션. 로컬 컴퓨터에서 응용 프로그램이 시작 됩니다.</p>
<p>1 = 파티 2 세션 (기본값). Lync 2013는 응용 프로그램을 로컬로 시작한 다음 시스템 알림을 다른 사용자에 게 보냅니다. 다른 사용자가 알림을 클릭 하 고 컴퓨터에서 지정 된 응용 프로그램을 시작 합니다.</p>
<p>2 = 단체 세션. Lync 2013는 응용 프로그램을 로컬로 시작한 다음 다른 사용자에 게 시스템 알림을 보내어 자신의 컴퓨터에서 지정 된 응용 프로그램을 시작 하도록 요청 합니다.</p></td>
</tr>
<tr class="even">
<td><p>ExensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>이 명령이 표시 되는 메뉴의 목록으로, 세미콜론으로 구분 됩니다. 사용할 수 있는 값은 다음과 같습니다.</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>ConversationWindowActions</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>ConversationWindowRightClick</p></li>
</ul>
<p>ExtensibleMenu가 정의 되어 있지 않으면 MainWindowRightClick ConversationWindowActions의 default 값이 사용 됩니다.</p></td>
</tr>
</tbody>
</table>


다음 표에서는 매개 변수에 대 한 레지스트리 항목에 대해 설명 합니다. 이러한 항목\_은 HKEY 현재\_사용자\\소프트웨어\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\매개 변수를 사용 하 여 배치 됩니다.

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a>인터넷 기반 공동 작업 응용 프로그램의 레지스트리 항목

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>이름</th>
<th>유형</th>
<th>데이터</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Param1</p></td>
<td><p>REG_SZ</p></td>
<td><p>OriginatorPath 레지스트리 키에 사용자<code>%Parm1%</code>관련 값을 추가 하기 위해 토큰화 된 형식 ()으로 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>Param2</p></td>
<td><p>REG_SZ</p></td>
<td><p>Param1을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p>Param3</p></td>
<td><p>REG_SZ</p></td>
<td><p>Param1을 참조 하세요.</p></td>
</tr>
</tbody>
</table>


다음 예제 레지스트리 설정은 ADatum 협업 클라이언트를 Lync 2013와 통합 합니다.

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Path"="https://meetingservice.adatum.com/cc/%param1%/meet/%param2%"
    "OriginatorPath"="https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&role=present&pw=%param3%"
    "SessionType"=dword:00000002
    "ApplicationType"=dword:00000001
    "LiveServerIntegration"=dword:00000000
    "Name"="ADatum Online Collaboration Service"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"
    
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Param1"="meetserv"
    "Param2"="admin"
    "Param3"="abcdefg123"

</div>

<div>

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a>서버 기반 공동 작업 응용 프로그램을 Lync 2013와 통합

Lync 2013에서 서버 기반 공동 작업 응용 프로그램을 시작 하는 데 사용할 수 있는 명령을 추가 하는 설정은 이전 섹션에서 설명한 것과 유사 하며, Lync 2013를 사용 하 여 인터넷 기반 공동 작업 응용 프로그램을 통합 합니다. 그러나 OriginatorPath는 필요 하지 않으며 일부 값이 변경 됩니다. 레지스트리 항목은 다음 위치에 저장 됩니다.

  - HKEY\_로컬\_컴퓨터\\소프트웨어\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\매개 변수

### <a name="registry-entries-for-a-server-based-collaboration-application"></a>서버 기반 공동 작업 응용 프로그램의 레지스트리 항목

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>이름</th>
<th>유형</th>
<th>데이터</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>이름</p></td>
<td><p>REG_SZ</p></td>
<td><p>메뉴에 표시 되는 응용 프로그램의 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>ApplicationType</p></td>
<td><p>DWORD(32</p></td>
<td><p>값 = 1. 응용 프로그램 종류를 protocol으로 설정 합니다. 이 경우에는 다른 가능 값이 적용 되지 않습니다. 없을 경우 ApplicationType이 0 (실행)으로 설정 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>패스가</p></td>
<td><p>REG_SZ</p></td>
<td><p>공동 작업 응용 프로그램을 시작 하는 데 사용 되는 프로토콜입니다. Live Meeting 2007의 경우 경로 값이로 <code>meet:%conf-uri%</code>설정 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>SessionType</p></td>
<td><p>DWORD(32</p></td>
<td><p>0 = 로컬 세션. 로컬 컴퓨터에서 응용 프로그램이 시작 됩니다.</p>
<p>1 = 파티 2 세션 (기본값). Lync 2013는 응용 프로그램을 로컬로 시작한 다음 시스템 알림을 다른 사용자에 게 보냅니다. 다른 사용자가 알림을 클릭 하 고 컴퓨터에서 지정 된 응용 프로그램을 시작 합니다.</p>
<p>2 = 단체 세션. Lync 2013는 응용 프로그램을 로컬로 시작한 다음 다른 사용자에 게 시스템 알림을 보내어 컴퓨터에서 지정 된 응용 프로그램을 시작 하 라는 메시지를 표시 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>M가공선</p></td>
<td><p>REG_SZ</p></td>
<td><p>데이터 = 서버의 유형입니다.</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>이 명령이 표시 되는 메뉴 목록 (세미콜론으로 구분)입니다. 사용할 수 있는 값은 다음과 같습니다.</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>ConversationWindowActions</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>ConversationWindowRightClick</p></li>
</ul>
<p>ExtensibleMenu가 정의 되어 있지 않으면 MainWindowRightClick ConversationWindowActions의 default 값이 사용 됩니다.</p></td>
</tr>
</tbody>
</table>


다음 예에서는 Lync 2013 내에서 ADatum 공동 작업 클라이언트를 시작 하는 명령을 추가 합니다.

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{27877e66-615c-4582-ab88-0cb2ca05d951}]
    "Path"="meet:%conf-uri%"
    "SessionType"=dword:00000002
    "LiveServerIntegration"=dword:00000001
    "ApplicationType"=dword:00000001
    "Name"="ADatum Collaboration Client"
    "MCUType"="Data"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"

</div>

</div>

<span> </span>

</div>

</div>

</div>

