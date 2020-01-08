---
title: 'Lync Server 2013: Lync 메뉴에 명령 추가'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Adding commands to Lync menus
ms:assetid: a8443bc2-e234-4022-870a-00700f38b1ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412788(v=OCS.15)
ms:contentKeyID: 48185091
ms.date: 04/11/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1dfb79a985791e6994d8409339d12b12e1146ec5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a>Lync Server 2013에서 Lync 메뉴에 명령 추가

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2016-04-11_

Lync 2013 메뉴에 사용자 지정 명령을 추가 하 고 현재 사용자의 SIP URI (Uniform Resource Identifier) 및 선택한 연락처를 사용자 지정 명령이 시작 되는 응용 프로그램에 전달할 수 있습니다.

추가 하는 사용자 지정 명령은 다음 메뉴 중 하나 이상에 나타날 수 있습니다.

  - Lync 주 창의 메뉴 모음에 있는 도구 메뉴

  - 연락처 목록의 연락처에 대 한 바로 가기 메뉴

  - 대화 창에 있는 기타 옵션 메뉴

  - 대화 창 참가자 목록에 나열 된 사용자의 바로 가기 메뉴

  - 대화 상대 카드의 옵션 메뉴

다음 중 하나를 수행 하는 응용 프로그램 이라는 두 가지 유형의 응용 프로그램에 대해 사용자 지정 명령을 정의할 수 있습니다.

  - 현재 사용자 에게만 적용 되 고 로컬 컴퓨터에서 시작 됩니다.

  - 온라인 공동 작업 프로그램과 같은 추가 사용자를 포함 하 고 각 사용자의 컴퓨터에서 시작 해야 합니다.

사용자 지정 명령은 다음과 같은 방식으로 호출할 수 있습니다.

  - 하나 이상의 사용자를 선택한 다음 사용자 지정 명령을 선택 합니다.

  - 2-파티 또는 단체 대화를 시작한 다음 사용자 지정 명령을 선택 합니다.

<div>

## <a name="to-add-a-custom-command"></a>사용자 지정 명령을 추가 하려면

다음 표의 레지스트리 설정을 사용 하 여 메뉴에 명령을 추가 합니다. 이러한 항목은 다음 위치 중 하나에 있는 레지스트리에 저장 됩니다.

  - 32 비트 OS: HKEY\_로컬\_컴퓨터\\소프트웨어\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps

  - 64 비트 OS: HKEY\_로컬\_컴퓨터\\소프트웨어\\Wow6432Node\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\앱

### <a name="custom-command-registry-entries"></a>사용자 지정 명령 레지스트리 항목

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
<td><p>0 = 실행 파일 (기본값)</p>
<div>

> [!NOTE]  
> ApplicationInstallPath 필요


</div>
<p>1 = 프로토콜</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationInstallPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>실행 파일의 전체 경로입니다.</p>
<div>

> [!NOTE]  
> ApplicationType이 0 (실행) 인 경우에는 반드시 지정 해야 합니다.


</div></td>
</tr>
<tr class="even">
<td><p>패스가</p></td>
<td><p>REG_SZ</p></td>
<td><p>기본 매개 변수 <em>% user-id%</em> 및 <em>% contact-id%</em>를 포함 하 여 모든 매개 변수와 함께 시작 되는 전체 경로입니다.</p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>DWORD(32</p></td>
<td><p>0 = 로컬 세션. 로컬 컴퓨터에서 응용 프로그램이 시작 됩니다.</p>
<p>1 = 파티 2 세션 (기본값). Lync 2013에서 로컬로 응용 프로그램이 시작 된 다음 바탕 화면 알림을 다른 사용자에 게 보냅니다. 다른 사용자가 컴퓨터에서 알림을 클릭 하 여 응용 프로그램을 시작 합니다.</p>
<p>2 = 단체 세션. Lync 2013에서 로컬로 응용 프로그램이 시작 된 다음 데스크톱 알림을 다른 사용자에 게 보냅니다. 다른 사용자가 알림을 클릭 하 여 컴퓨터에서 지정 된 응용 프로그램을 시작 합니다.</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>이 명령이 표시 되는 메뉴 목록 (세미콜론으로 구분)입니다. 사용할 수 있는 값은 다음과 같습니다.</p>
<p>MainWindowActions</p>
<p>MainWindowRightClick</p>
<p>ConversationWindowActions</p>
<p>ConversationWindowRightClick</p>
<p>연락처 메뉴</p>
<p>ExtensibleMenu가 정의 되어 있지 않으면 MainWindowRightClick ConversationWindowActions의 default 값이 사용 됩니다.</p></td>
</tr>
</tbody>
</table>


예를 들어 다음 레지스트리 편집기 (. REG) 파일은 Contoso Sales Contact Manager 메뉴 항목을 대화 창의 동작 메뉴에 추가한 결과를 보여 줍니다.

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Office\15.0\Lync\SessionManager\Apps\{1F9F07C6-7E0B-462B-AAD7-98C6DBEA8F69}]
    "Name"="Contoso Sales Contact Manager"
    "HelpMessage"="The Contoso Sales Contact Manager is not installed. Contact the Help Desk for more information."
    "ApplicationType"=dword:00000000
    "ApplicationInstallPath"="C:\\cscm.exe"
    "Path"="C:\\cscm.exe %user-id% %contact-id%"
    "SessionType"=dword:00000001
    "ExtensibleMenu"="ConversationWindowActions;MainWindowRightClick"

</div>

<div>

## <a name="to-access-a-custom-command"></a>사용자 지정 명령에 액세스 하려면

추가 된 사용자 지정 명령에 액세스 하려면 정의한 ExtensibleMenu 값에 따라 다음 중 하나를 수행 합니다.

  - **Mainwindowactions**   Lync 주 창에서 **도구**를 클릭 한 다음 사용자 지정 명령을 클릭 합니다.

  - **Mainwindowrightclick**   Lync 주 창에서 대화 상대를 마우스 오른쪽 단추로 클릭 한 다음 사용자 지정 명령을 클릭 합니다.

  - **ConversationWindowActions**   대화 창에서 **기타 옵션** 아이콘을 클릭 한 다음 사용자 지정 명령을 클릭 합니다.

  - **ConversationWindowRightClick**   대화 창에서 대화 상대의 이름을 마우스 오른쪽 단추로 클릭 한 다음 사용자 지정 명령을 클릭 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

