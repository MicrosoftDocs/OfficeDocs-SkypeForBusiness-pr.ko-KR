---
title: 'Lync Server 2013: 감시자 노드 설치 및 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing and configuring watcher nodes
ms:assetid: 61f6deea-e3ef-4468-9be8-a65705815ebb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204943(v=OCS.15)
ms:contentKeyID: 48184284
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 980dc8c92488e3806cd6c1bf15970a79af6fa2b4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534945"
---
# <a name="installing-and-configuring-watcher-nodes-in-lync-server-2013"></a>Lync Server 2013에서 감시자 노드 설치 및 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-11-07_

*감시자 노드* 는 Lync Server 가상 트랜잭션을 주기적으로 실행 하는 컴퓨터입니다. *가상 트랜잭션은* 시스템에 로그인 하는 기능, 또는 인스턴트 메시지를 교환 하는 기능과 같은 주요 최종 사용자 시나리오가 예상 대로 작동 하는지 확인 하는 Windows PowerShell cmdlet입니다. Lync Server 2013의 경우 System Center Operations Manager는 다음 표에 나와 있는 가상 트랜잭션을 실행할 수 있습니다. 이 표에서는 세 가지 서로 다른 가상 트랜잭션 유형을 보여줍니다.

  - **기본값**입니다. 감시자 노드가 기본적으로 실행 되는 가상 트랜잭션입니다. 새 감시자 노드를 만들 때는 해당 노드가 실행 될 가상 트랜잭션을 지정할 수 있습니다. 이는 **get-cswatchernodeconfiguration** cmdlet에서 사용 되는 테스트 매개 변수의 용도입니다. 감시자 노드를 만들 때 테스트 매개 변수를 사용 하지 않으면 기본 가상 트랜잭션이 모두 자동으로 실행 되며 비기본 가상 트랜잭션이 실행 되지 않습니다. 즉, 예를 들어 감시자 노드가 Test-CsAddressBookService 테스트를 실행 하도록 구성 되지만 Test-CsExumConnectivity 테스트를 실행 하도록 구성 되지는 않습니다.

  - **기본값 아님** 이름 그대로 기본값이 아닌 가상 트랜잭션은 감시자 노드가 기본적으로 실행하지 않는 테스트입니다. 하지만 감시자 노드가 기본값이 아닌 가상 트랜잭션을 실행하도록 설정할 수는 있습니다. 이러한 설정은 **New-CsWatcherNodeConfiguration** cmdlet을 사용하여 감시자 노드를 만들 때 또는 그 이후 언제라도 지정할 수 있습니다. 기본값이 아닌 가상 트랜잭션은 대부분의 경우 추가 설정 단계가 필요합니다. 자세한 내용은 [Lync Server 2013의 가상 트랜잭션에 대 한 특별 설치 지침](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)을 참조 하십시오.

  - **확장**됩니다. 확장 테스트는 특별한 유형의 기본값이 아닌 가상 트랜잭션입니다. 다른 가상 트랜잭션과 달리 확장 테스트는 한 번의 테스트 과정 중에 여러 번 실행할 수 있습니다. 이러한 특성은 풀의 여러 PSTN(공중 전화망) 음성 경로와 같은 동작을 확인할 때 유용할 수 있습니다. 이 테스트는 단순히 확장 테스트의 여러 인스턴스를 감시자 노드에 추가하여 구성할 수 있습니다.

다른 가상 트랜잭션을 감시자 노드에 추가 하는 프로세스에 대 한 자세한 내용은 [Lync Server 2013에서 감시자 노드 관리](lync-server-2013-managing-watcher-nodes.md)를 참조 하십시오. Lync Server 관리 셸을 사용 하 여 감시자 노드에서 가상 트랜잭션을 제거할 수 있습니다.

감시자 노드에서 사용할 수 있는 가상 트랜잭션에는 다음 항목이 포함됩니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Cmdlet 이름(테스트 이름)</th>
<th>설명</th>
<th>가상 트랜잭션 유형</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Test-CsAddressBookService(ABS)</p></td>
<td><p>사용자가 자신의 대화 상대 목록에 없는 사용자를 조회할 수 있는지 확인합니다.</p></td>
<td><p>기본</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAddressBookWebQuery(ABWQ)</p></td>
<td><p>사용자가 HTTP를 통해 자신의 대화 상대 목록에 없는 사용자를 조회할 수 있는지 확인합니다.</p></td>
<td><p>기본</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsIM(IM)</p></td>
<td><p>사용자가 피어 투 피어 인스턴트 메시지를 보낼 수 있는지 확인합니다.</p></td>
<td><p>기본</p></td>
</tr>
<tr class="even">
<td><p>Test-CsP2PAV (P2PAV)</p></td>
<td><p>사용자가 피어 투 피어 음성 통화를 걸 수 있는지 확인합니다(신호만).</p></td>
<td><p>기본</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsPresence(Presence)</p></td>
<td><p>사용자가 다른 사용자의 현재 상태를 볼 수 있는지 확인합니다.</p></td>
<td><p>기본</p></td>
</tr>
<tr class="even">
<td><p>Test-CsRegistration(Registration)</p></td>
<td><p>사용자가 Lync에 로그인할 수 있는지 확인합니다.</p></td>
<td><p>기본</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsAudioConferencingProvider(ACP)</p></td>
<td><p>온-프레미스 버전의 Lync Server 2013와 함께 사용 되지 않음</p></td>
<td><p>오랜</p></td>
</tr>
<tr class="even">
<td><p>Test-CsPstnPeerToPeerCall(PSTN)</p></td>
<td><p>사용자가 기업 외부에 있는 사용자와 통화를 걸거나 받을 수 있는지 확인합니다(PSTN 번호).</p></td>
<td><p>기본값이 아님, 확장</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsAVConference (AvConference)</p></td>
<td><p>사용자가 오디오/비디오 회의를 만들고 참가할 수 있는지 확인합니다.</p></td>
<td><p>기본</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</p></td>
<td><p>A/V 에지 서버가 피어 투 피어 통화 및 회의 통화에 대한 연결을 허용할 수 있는지 확인합니다.</p></td>
<td><p>비기본</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsDataConference (DataConference)</p></td>
<td><p>사용자가 화이트보드 및 설문 조사와 같은 활동을 포함하여 데이터 공동 작업 회의 및 온라인 모임에 참가할 수 있는지 확인합니다.</p></td>
<td><p>비기본</p></td>
</tr>
<tr class="even">
<td><p>Test-CsExumConnectivity (ExumConnectivity)</p></td>
<td><p>사용자가 Exchange UM (통합 메시징)에 연결할 수 있는지 확인 합니다.</p></td>
<td><p>비기본</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsGroupIM (GroupIM)</p></td>
<td><p>사용자가 회의 중 인스턴트 메시지를 보내고 3명 이상의 사용자가 포함된 인스턴트 메시지 대화에 참가할 수 있는지 확인합니다.</p></td>
<td><p>기본</p></td>
</tr>
<tr class="even">
<td><p>Test-CsGroupIM-TestJoinLauncher 관리자 (Join시작 관리자)</p></td>
<td><p>사용자가 웹 주소 링크를 통해 예약된 모임을 만들고 참가할 수 있는지 확인합니다.</p></td>
<td><p>비기본</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsMCXP2PIM (MCXP2PIM)</p></td>
<td><p>모바일 장치 사용자가 등록하고 인스턴트 메시지를 보낼 수 있는지 확인합니다.</p></td>
<td><p>비기본</p></td>
</tr>
<tr class="even">
<td><p>Test-CsPersistentChatMessage (PersistentChatMessage)</p></td>
<td><p>사용자가 영구 채팅 서비스를 사용 하 여 메시지를 교환할 수 있는지 확인 합니다.</p></td>
<td><p>비기본</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsUnifiedContactStore (UnifiedContactStore)</p></td>
<td><p>통합 연락처 저장소를 사용해서 사용자의 연락처에 액세스할 수 있는지 확인합니다. 통합 연락처 저장소는 사용자가 Lync 2013, Outlook 및/또는 Outlook Web Access를 사용 하 여 액세스할 수 있는 단일 연락처 집합을 유지 관리 하는 방법을 제공 합니다.</p></td>
<td><p>비기본</p></td>
</tr>
<tr class="even">
<td><p>Test-CsXmppIM (XmppIM)</p></td>
<td><p>XMPP(Extensible Messaging and Presence Protocol) 게이트웨이에서 인스턴트 메시지를 전송할 수 있는지 확인합니다.</p></td>
<td><p>비기본</p></td>
</tr>
</tbody>
</table>


System Center Operations Manager를 사용 하기 위해 감시자 노드를 설치할 필요가 없습니다. 이러한 노드를 설치 하지 않으면 문제가 발생할 때 Lync Server 2013 구성 요소에서 실시간 알림을 받을 수 있습니다. (구성 요소 및 사용자 관리 팩은 감시자 노드를 사용 하지 않습니다.) 그러나 활성 모니터링 관리 팩을 사용 하 여 종단 간 시나리오를 모니터링 하려는 경우에는 감시자 노드가 필요 합니다.

<div>


> [!NOTE]  
> 관리자는 또한 Operations Manager를 사용하거나 설치할 필요 없이 가상 트랜잭션을 수동으로 실행할 수 있습니다. 다양 한 Test-Cs cmdlet에 대 한 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Lync Server 2013 cmdlet 인덱스</A>를 참조 하십시오.



</div>

배포 크기에 따라 가상 트랜잭션에는 대량의 컴퓨터 메모리 및 프로세서 시간이 사용될 수 있습니다. 따라서 전용 컴퓨터를 감시자 노드로 사용하는 것이 좋습니다. 예를 들어, 감시자 노드로 작동 하도록 프런트 엔드 서버를 구성 해서는 안 됩니다. 감시자 노드는 다음 하드웨어 사양을 충족 해야 합니다.

<div>


> [!NOTE]  
> Lync Server 2013 감시자 노드를 사용 하 여 레거시 Microsoft Lync Server 2010 감시자 노드를 같은 컴퓨터에 배치 된 수 없습니다. Lync Server 2010 및 Lync Server 2013의 핵심 시스템 파일을 같은 컴퓨터에 설치할 수 없기 때문입니다.<BR>그러나 Lync Server 2013 감시자 노드는 Lync Server 2013 및 Lync Server 2010을 동시에 모니터링할 수 있습니다. 두 제품 버전 모두 기본 가상 트랜잭션이 지원됩니다.



</div>

Lync Server 2013 감시자 노드를 엔터프라이즈 내부 또는 외부에 배포 하 여 확인 하는 데 도움을 받을 수 있습니다.

  - <span></span>  
    기업 내부의 사용자 풀에 대한 연결

  - <span></span>  
    기업 외부에서 근무하는 원격 사용자를 위한 경계 네트워크를 통한 연결

  - <span></span>  
    지점 사무소 기기에 대한 연결

  - <span></span>  
    기업 내부 및 경계 네트워크 내부의 Lync Server 2010에 대 한 연결

관리를 간소화할 수 있도록 기업 내부 및 외부에서 다양한 인증 옵션을 사용할 수 있습니다. 자세한 내용은 [Lync Server 2013에서 가상 트랜잭션을 실행 하도록 감시자 노드 구성을](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md)참조 하십시오.

컴퓨터가 감시자 노드로 작동 하도록 구성 하려면 System Center Operations Manager를 설치 하 고 Lync Server 2013 관리 팩을 가져온 후에 다음 단계를 완료 해야 합니다.

Lync Server 2013 코어 파일과 System Center 에이전트 파일을 설치 하기 전에, 감시자 노드 컴퓨터가 Lync Server 2013 설치를 위한 모든 필수 구성 요소를 충족 하는지도 확인 해야 합니다. 또한 감시자 노드 컴퓨터에는 다음과 같은 항목도 설치되어 있어야 합니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>하드웨어 구성 요소</th>
<th>최소 요구 사항</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>다음 중 하나여야 합니다.</p>
<ul>
<li><p>64 비트 프로세서, 쿼드 코어, 2.33 GHz 이상</p></li>
<li><p>64 비트 2 방향 프로세서, 듀얼 코어, 2.33 GHz 이상</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>메모리</p></td>
<td><p>8GB</p></td>
</tr>
<tr class="odd">
<td><p>네트워크 운영 체제</p></td>
<td><ul>
<li><p>1Gbps 네트워크 어댑터 1 개</p></li>
<li><p>Windows Server 2008 R2, Windows Server 2012 또는</p>
<p>Windows Server 2012 R2</p></li>
</ul></td>
</tr>
</tbody>
</table>


  - 전체 버전의 .NET Framework 4.5

  - Windows Identity Foundation

  - Windows PowerShell 3.0.

이러한 모든 필수 구성 요소가 충족되었으면 다음을 통해 감시자 노드를 구성할 수 있습니다.

  - 감시자 노드 컴퓨터에 Lync Server 2013 코어 파일 설치

  - 감시자 노드 컴퓨터에 System Center Operations Manager 에이전트를 설치 합니다.

  - Watchernode.msi executable 파일 실행

  - **CsWatcherNodeConfiguration** cmdlet을 사용하여 감시자 노드에 사용할 테스트 사용자 구성

</div>

<span> </span>

</div>

</div>

</div>

