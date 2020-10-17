---
title: 'Lync Server 2013: Lync 메뉴에 명령 추가'
description: 'Lync Server 2013: Lync 메뉴에 명령을 추가 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding commands to Lync menus
ms:assetid: a8443bc2-e234-4022-870a-00700f38b1ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412788(v=OCS.15)
ms:contentKeyID: 48185091
ms.date: 04/11/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed4d62d085eaf115d107244ae50a7cc69e0aacd5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558234"
---
# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a>Lync Server 2013의 Lync 메뉴에 명령 추가

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2016-04-11_

Lync 2013 메뉴에 사용자 지정 명령을 추가 하 고 현재 사용자의 SIP URI (Uniform Resource Identifier) 및 선택한 연락처를 사용자 지정 명령이 시작 되는 응용 프로그램에 전달할 수 있습니다.

추가할 수 있는 사용자 지정 명령은 다음 메뉴 중 하나 이상에 표시될 수 있습니다.

  - Lync 주 창에 있는 메뉴 표시줄의 도구 메뉴

  - 대화 상대 목록의 대화 상대에 대한 바로 가기 메뉴

  - 대화 창의 기타 옵션 메뉴

  - 대화 창의 참가자 목록에 나열된 사용자에 대한 바로 가기 메뉴

  - 대화 상대 카드의 옵션 메뉴

다음 중 하나를 수행하는 두 가지 유형의 응용 프로그램에 대한 사용자 지정 명령을 정의할 수 있습니다.

  - 현재 사용자에게만 적용되고 로컬 컴퓨터에서 시작됩니다.

  - 온라인 공동 작업 프로그램 등과 같은 추가 사용자를 포함하고 각 사용자의 컴퓨터에서 시작되어야 합니다.

다음과 같은 방법으로 사용자 지정 명령을 호출할 수 있습니다.

  - 한 명 이상의 사용자를 선택하고 사용자 지정 명령을 선택합니다.

  - 두 사용자 간 대화 또는 단체 간 대화를 시작하고 사용자 지정 명령을 선택합니다.

<div>

## <a name="to-add-a-custom-command"></a>사용자 지정 명령을 추가하려면

다음 표의 레지스트리 설정을 사용 하 여 메뉴에 명령을 추가 합니다. 이러한 항목은 레지스트리에 다음 위치 중 하나에 포함 됩니다.

  - 32 비트 OS: HKEY \_ 로컬 \_ 컴퓨터 \\ 소프트웨어 \\ Microsoft \\ Office \\ 15.0 \\ Lync \\ SessionManager \\ Apps

  - 64 비트 OS: HKEY \_ 로컬 \_ 컴퓨터 \\ 소프트웨어 \\ Wow6432Node \\ Microsoft \\ Office \\ 15.0 \\ Lync \\ SessionManager \\ Apps

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
<th>형식</th>
<th>데이터</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>이름</p></td>
<td><p>REG_SZ</p></td>
<td><p>메뉴에 표시되는 응용 프로그램 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>ApplicationType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = 실행 파일(기본값)</p>
<div>

> [!NOTE]  
> ApplicationInstallPath가 필요합니다.


</div>
<p>1 = 프로토콜</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationInstallPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>실행 파일의 전체 경로.</p>
<div>

> [!NOTE]  
> ApplicationType이 0(실행 파일)일 경우 지정해야 합니다.


</div></td>
</tr>
<tr class="even">
<td><p>경로</p></td>
<td><p>REG_SZ</p></td>
<td><p><em>%user-id%</em> 및 <em>%contact-id%</em> 등 기본 매개 변수를 비롯한 매개 변수와 함께 시작될 전체 경로</p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = 로컬 세션. 응용 프로그램이 로컬 컴퓨터에서 시작됩니다.</p>
<p>1 = 두 그룹 세션(기본값). Lync 2013에서는 응용 프로그램을 로컬로 시작한 다음 바탕 화면 알림을 다른 사용자에 게 보냅니다. 상대방이 알림을 클릭하여 응용 프로그램을 자신의 컴퓨터에서 시작합니다.</p>
<p>2 = 단체 세션. Lync 2013에서는 응용 프로그램을 로컬로 시작한 다음 다른 사용자에 게 바탕 화면 알림을 보냅니다. 다른 사용자가 해당 알림을 클릭 하 여 컴퓨터에서 지정 된 응용 프로그램을 시작 합니다.</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>이 명령이 표시 되는 메뉴의 목록이 며 세미콜론으로 구분 합니다. 가능한 값은 다음과 같습니다.</p>
<p>MainWindowActions</p>
<p>MainWindowRightClick</p>
<p>Conversationwindowactions가 기본값으로</p>
<p>ConversationWindowRightClick</p>
<p>Contactcardmenu 개인</p>
<p>ExtensibleMenu가 정의되어 있지 않으면 MainWindowRightClick 및 ConversationWindowActions가 기본값으로 사용됩니다.</p></td>
</tr>
</tbody>
</table>


예를 들어 다음 레지스트리 편집기(.REG) 파일에는 Contoso Sales Contact Manager 메뉴 항목을 대화 창의 동작 메뉴에 추가한 결과가 표시됩니다.

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

## <a name="to-access-a-custom-command"></a>사용자 지정 명령에 액세스하려면

사용자 지정 명령이 추가 된 후 액세스 하려면 정의 하는 ExtensibleMenu 값에 따라 다음 중 하나를 수행 합니다.

  - **Mainwindowactions**     Lync 주 창에서 **도구**를 클릭 한 다음 사용자 지정 명령을 클릭 합니다.

  - **Mainwindowrightclick**     Lync 주 창에서 대화 상대를 마우스 오른쪽 단추로 클릭 한 다음 사용자 지정 명령을 클릭 합니다.

  - **Conversationwindowactions가 기본값으로**     대화 창에서 **기타 옵션** 아이콘을 클릭 한 다음 사용자 지정 명령을 클릭 합니다.

  - **ConversationWindowRightClick**     대화 창에서 대화 상대 이름을 마우스 오른쪽 단추로 클릭 한 다음 사용자 지정 명령을 클릭 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

