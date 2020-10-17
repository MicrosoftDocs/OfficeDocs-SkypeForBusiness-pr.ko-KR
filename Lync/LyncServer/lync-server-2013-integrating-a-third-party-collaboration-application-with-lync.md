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
ms.openlocfilehash: e7bbe3f6439b357253ae49a5c1609319b6a91bfb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534763"
---
# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a>Lync Server 2013를 사용 하 여 타사 공동 작업 응용 프로그램 통합

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-20_

응용 프로그램에 대 한 정보를 레지스트리에 추가 하 여 Lync 2013을 타사 온라인 공동 작업 응용 프로그램과 통합할 수 있습니다. Lync 2013을 사용 하 여 내부 서버, 인터넷 기반 서비스 또는 둘 다에 호스트 되는 데이터 회의 세션을 시작할 수 있습니다. 대화 상대 목록 또는 기존의 인스턴트 메시징, 음성 및 화상 세션에서 공동 작업(또는 데이터 회의) 세션을 시작할 수 있습니다. Lync 2013는 응용 프로그램을 시작 하기 위한 수단 으로만 작동 합니다. 기존 Lync 2013 대화는 온라인 공동 작업 세션이 시작 된 후에도 활성 상태로 유지 됩니다.

다음 섹션에서는 Lync 2013를 인터넷 기반 및 서버 기반 공동 작업 응용 프로그램과 통합 하는 방법에 대해 설명 합니다.

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a>Lync 2013을 사용 하 여 Internet-Based 공동 작업 응용 프로그램 통합

타사 공동 작업 응용 프로그램을 통합하는 일반적인 단계는 다음과 같습니다.

1.  응용 프로그램에 대한 정보를 레지스트리에 추가합니다.

2.  이끌이는 Lync 2013에 로그인 하 고 데이터 공유 및 공동 작업을 위해 연락처를 선택 합니다. 또는 이끌이가 대화 중에 데이터 회의를 추가할 수도 있습니다.

3.  Lync 2013에서 레지스트리를 읽고 공동 작업 응용 프로그램을 시작한 다음 선택한 참가자에 게 사용자 지정 SIP 메시지 (appINVITE)를 보냅니다.

4.  참가자가 초대를 수락하면 각 참가자의 컴퓨터에서 공동 작업 응용 프로그램이 시작됩니다. Lync 2013는 레지스트리를 사용 하 여 사용할 공동 작업 응용 프로그램을 확인 한 다음 appINVITE 메시지에 포함 된 매개 변수를 사용 하 여 해당 응용 프로그램을 시작 합니다.

다음 표에서는 인터넷 기반 공동 작업 응용 프로그램을 Lync 2013와 통합 하는 데 필요한 레지스트리 항목에 대해 설명 합니다. 이러한 항목은 레지스트리에 다음 위치에 배치 됩니다.

  - HKEY \_ 로컬 \_ 컴퓨터 \\ 소프트웨어 \\ Microsoft \\ Office \\ 15.0 \\ Lync \\ SessionManager \\ Apps \\ 매개 변수

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
<th>형식</th>
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
<td><p>16 x 16픽셀 아이콘(BMP 또는 PNG)의 경로입니다.</p></td>
</tr>
<tr class="odd">
<td><p>경로</p></td>
<td><p>REG_SZ</p></td>
<td><p>온라인 공동 작업 응용 프로그램을 시작할 참가자의 경로입니다.</p></td>
</tr>
<tr class="even">
<td><p>OriginatorPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>온라인 공동 작업 응용 프로그램을 시작할 이끌이의 경로입니다. 이 경로에는 Parameters 하위 키에 정의된 사용자 지정 매개 변수가 하나 이상 포함될 수 있습니다. 예를 들어 <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = 로컬 세션. 응용 프로그램이 로컬 컴퓨터에서 시작됩니다.</p>
<p>1 = 두 그룹 세션(기본값). Lync 2013에서는 응용 프로그램을 로컬로 시작한 다음 시스템 알림을 다른 사용자에 게 보냅니다. 다른 사용자는 알림을 클릭하여 지정된 응용 프로그램을 자신의 컴퓨터에서 시작합니다.</p>
<p>2 = 단체 세션. Lync 2013에서는 응용 프로그램을 로컬로 시작한 다음 다른 사용자에 게 시스템 알림을 보내 자신의 컴퓨터에서 지정 된 응용 프로그램을 시작 하 라는 메시지를 표시 합니다.</p></td>
</tr>
<tr class="even">
<td><p>ExensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>이 명령이 표시될 메뉴 목록입니다. 각 메뉴는 세미콜론으로 구분됩니다. 가능한 값은 다음과 같습니다.</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>Conversationwindowactions가 기본값으로</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>ConversationWindowRightClick</p></li>
</ul>
<p>ExtensibleMenu가 정의되어 있지 않으면 MainWindowRightClick 및 ConversationWindowActions가 기본값으로 사용됩니다.</p></td>
</tr>
</tbody>
</table>


다음 표에 매개 변수의 레지스트리 항목에 대한 설명이 나와 있습니다. 이러한 항목은 HKEY \_ 현재 \_ 사용자 \\ 소프트웨어 \\ Microsoft \\ Office \\ 15.0 \\ Lync \\ SessionManager \\ Apps \\ 매개 변수에 배치 됩니다.

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
<th>형식</th>
<th>데이터</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Param1</p></td>
<td><p>REG_SZ</p></td>
<td><p><code>%Parm1%</code>OriginatorPath 레지스트리 키에 사용자 관련 값을 추가 하기 위해 토큰화 된 형식 ()으로 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>Param2</p></td>
<td><p>REG_SZ</p></td>
<td><p>Param1을 참조하십시오.</p></td>
</tr>
<tr class="odd">
<td><p>Param3</p></td>
<td><p>REG_SZ</p></td>
<td><p>Param1을 참조하십시오.</p></td>
</tr>
</tbody>
</table>


다음 예제 레지스트리 설정은 ADatum 공동 작업 클라이언트를 Lync 2013와 통합 합니다.

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

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a>Server-Based 공동 작업 응용 프로그램을 Lync 2013에 통합

Lync 2013 내에서 서버 기반 공동 작업 응용 프로그램을 시작 하기 위한 명령을 추가 하는 설정은 이전 섹션에서 설명한 것과 유사 하며 Internet-Based 공동 작업 응용 프로그램을 Lync 2013에 통합 합니다. 그러나 이번에는 OriginatorPath가 필요하지 않으며 일부 값이 다릅니다. 레지스트리 항목은 다음 위치에 배치 됩니다.

  - HKEY \_ 로컬 \_ 컴퓨터 \\ 소프트웨어 \\ Microsoft \\ Office \\ 15.0 \\ Lync \\ SessionManager \\ Apps \\ 매개 변수

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
<td><p>값 = 1. 응용 프로그램 유형을 프로토콜로 설정합니다. 이 경우에는 다른 값이 적용되지 않습니다. 이 매개 변수가 없으면 ApplicationType이 0 (실행)으로 설정 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>경로</p></td>
<td><p>REG_SZ</p></td>
<td><p>공동 작업 응용 프로그램을 시작하는 데 사용되는 프로토콜입니다. Live Meeting 2007의 경우 경로 값은로 설정 됩니다 <code>meet:%conf-uri%</code> .</p></td>
</tr>
<tr class="even">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = 로컬 세션. 응용 프로그램이 로컬 컴퓨터에서 시작됩니다.</p>
<p>1 = 두 그룹 세션(기본값). Lync 2013에서는 응용 프로그램을 로컬로 시작한 다음 시스템 알림을 다른 사용자에 게 보냅니다. 다른 사용자는 알림을 클릭하여 지정된 응용 프로그램을 자신의 컴퓨터에서 시작합니다.</p>
<p>2 = 단체 세션. Lync 2013은 응용 프로그램을 로컬로 시작한 다음 시스템에서 지정한 응용 프로그램을 시작 하 라는 메시지를 다른 사용자에 게 보냅니다.</p></td>
</tr>
<tr class="odd">
<td><p>M가공선 유형</p></td>
<td><p>REG_SZ</p></td>
<td><p>DATA = 서버 유형입니다.</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>이 명령이 표시 되는 메뉴의 목록이 며 세미콜론으로 구분 합니다. 가능한 값은 다음과 같습니다.</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>Conversationwindowactions가 기본값으로</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>ConversationWindowRightClick</p></li>
</ul>
<p>ExtensibleMenu가 정의되어 있지 않으면 MainWindowRightClick 및 ConversationWindowActions가 기본값으로 사용됩니다.</p></td>
</tr>
</tbody>
</table>


다음은 Lync 2013 내에서 ADatum 공동 작업 클라이언트를 시작 하기 위한 명령을 추가 하는 예제입니다.

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

