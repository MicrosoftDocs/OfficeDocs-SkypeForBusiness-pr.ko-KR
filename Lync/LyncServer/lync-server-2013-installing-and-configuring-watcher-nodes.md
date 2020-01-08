---
title: 'Lync Server 2013: 감시자 노드 설치 및 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing and configuring watcher nodes
ms:assetid: 61f6deea-e3ef-4468-9be8-a65705815ebb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204943(v=OCS.15)
ms:contentKeyID: 48184284
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36d466cbffff1cf1e68eefe120215895e52e7c81
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-and-configuring-watcher-nodes-in-lync-server-2013"></a>Lync Server 2013에서 감시자 노드 설치 및 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-11-07_

*감시자 노드* 는 Lync Server 가상 트랜잭션을 정기적으로 실행 하는 컴퓨터입니다. *가상 트랜잭션은* 시스템에 로그인 하거나 인스턴트 메시지를 교환 하는 등의 주요 최종 사용자 시나리오가 예상 대로 작동 하는지 확인 하는 Windows PowerShell cmdlet입니다. Lync Server 2013의 경우 System Center Operations Manager는 다음 표에 표시 된 가상 트랜잭션을 실행할 수 있습니다. 표에는 다음과 같은 세 가지 가상 트랜잭션 유형이 표시 됩니다.

  - **기본값**입니다. 다음은 기본적으로 감시자 노드가 실행 되는 가상 트랜잭션입니다. 새 감시자 노드를 만드는 경우 해당 노드가 실행할 가상 트랜잭션을 지정 하는 옵션이 표시 됩니다. (이는 **CsWatcherNodeConfiguration** cmdlet에 사용 되는 테스트 매개 변수의 목적입니다.) 감시자 노드를 만들 때 테스트 매개 변수를 사용 하지 않으면 모든 기본 가상 트랜잭션이 자동으로 실행 되 고 기본이 아닌 가상 트랜잭션은 실행 되지 않습니다. 즉, 예를 들어, 감시자 노드는 테스트-CsAddressBookService 테스트를 실행 하도록 구성 되지만 테스트 CsExumConnectivity 테스트를 실행 하도록 구성 되지 않습니다.

  - **비 기본값**. 이름에서 알 수 있듯이 기본이 아닌 가상 트랜잭션은 감시자 노드가 기본적으로 실행 되지 않는다는 것을 테스트 합니다. 그러나 감시자 노드를 사용 하 여 기본이 아닌 가상 트랜잭션을 실행할 수 있습니다. 이 작업은 **새 CsWatcherNodeConfiguration** cmdlet을 사용 하 여 감시자 노드를 만들거나 그 이후에 언제 든 지 사용할 수 있습니다. 대부분의 비 기본 가상 트랜잭션에는 추가 설정 단계가 필요 합니다. 자세한 내용은 [Lync Server 2013의 종합 거래에 대 한 특수 설정 지침](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)을 참조 하세요.

  - **확장**됩니다. 확장 된 테스트는 기본이 아닌 가상 트랜잭션의 특별 한 유형입니다. 다른 가상 트랜잭션과 달리 확장 테스트는 각 단계에서 여러 번 실행할 수 있습니다. 이는 풀에 대 한 여러 공공 PSTN (교환 전화망) 음성 경로와 같은 동작을 확인 하는 경우 유용할 수 있습니다. 이는 확장 테스트의 여러 인스턴스를 감시자 노드에 추가 하 여 간단 하 게 구성할 수 있습니다.

다른 가상 트랜잭션을 감시자 노드에 추가 하는 프로세스에 대 한 자세한 내용은 [Lync Server 2013에서 감시자 노드 관리](lync-server-2013-managing-watcher-nodes.md)를 참조 하세요. Lync Server Management Shell을 사용 하 여 감시자 노드에서 가상 트랜잭션을 제거할 수 있습니다.

감시자 노드에 사용할 수 있는 가상 트랜잭션은 다음과 같습니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Cmdlet 이름 (테스트 이름)</th>
<th>설명</th>
<th>가상 트랜잭션 형식</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ABS (테스트-CsAddressBookService)</p></td>
<td><p>사용자가 대화 상대 목록에 없는 사용자를 조회할 수 있는지 확인 합니다.</p></td>
<td><p>기본값</p></td>
</tr>
<tr class="even">
<td><p>테스트-CsAddressBookWebQuery (ABWQ)</p></td>
<td><p>사용자가 HTTP를 통해 대화 상대 목록에 없는 사용자를 조회할 수 있는지 확인 합니다.</p></td>
<td><p>기본값</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsIM (IM)</p></td>
<td><p>사용자가 피어 투 피어 인스턴트 메시지를 보낼 수 있는지 확인 합니다.</p></td>
<td><p>기본값</p></td>
</tr>
<tr class="even">
<td><p>CsP2PAV (P2PAV)</p></td>
<td><p>사용자가 피어 투 피어 오디오 통화를 배치할 수 있는지 확인 합니다 (신호 전용).</p></td>
<td><p>기본값</p></td>
</tr>
<tr class="odd">
<td><p>테스트-CsPresence 현재 상태)</p></td>
<td><p>사용자가 다른 사용자의 현재 상태를 볼 수 있는지 확인 합니다.</p></td>
<td><p>기본값</p></td>
</tr>
<tr class="even">
<td><p>테스트-CsRegistration (Registration)</p></td>
<td><p>사용자가 Lync에 로그인 할 수 있는지 확인 합니다.</p></td>
<td><p>기본값</p></td>
</tr>
<tr class="odd">
<td><p>CsAudioConferencingProvider (ACP)</p></td>
<td><p>온-프레미스 버전의 Lync Server 2013에서 사용 되지 않음</p></td>
<td><p>확장이</p></td>
</tr>
<tr class="even">
<td><p>테스트-CsPstnPeerToPeerCall (PSTN)</p></td>
<td><p>사용자가 엔터프라이즈 이외의 사용자와 전화를 걸고 받을 수 있는지 확인 합니다 (PSTN 번호).</p></td>
<td><p>비기본, 확장</p></td>
</tr>
<tr class="odd">
<td><p>테스트-CsAVConference (AvConference)</p></td>
<td><p>사용자가 음성/영상 회의를 만들고 참가할 수 있는지 확인 합니다.</p></td>
<td><p>기본값</p></td>
</tr>
<tr class="even">
<td><p>CsAVEdgeConnectivity (AVEdgeConnectivity)</p></td>
<td><p>A/V Edge 서버가 피어 투 피어 통화 및 전화 회의 통화에 대 한 연결을 수락할 수 있는지 확인 합니다.</p></td>
<td><p>비기본</p></td>
</tr>
<tr class="odd">
<td><p>CsDataConference (DataConference)</p></td>
<td><p>사용자가 화이트 보드, 설문 등의 활동을 포함 하는 온라인 모임 인 데이터 공동 작업 회의에 참가할 수 있는지 확인 합니다.</p></td>
<td><p>비기본</p></td>
</tr>
<tr class="even">
<td><p>CsExumConnectivity (ExumConnectivity)</p></td>
<td><p>사용자가 UM (통합 메시징)에 연결할 수 있는지 확인 합니다.</p></td>
<td><p>비기본</p></td>
</tr>
<tr class="odd">
<td><p>테스트-CsGroupIM (GroupIM)</p></td>
<td><p>사용자가 회의 중에 인스턴트 메시지를 보내고 세 명 이상의 사용자와 인스턴트 메시지 대화에 참여할 수 있음을 확인 합니다.</p></td>
<td><p>기본값</p></td>
</tr>
<tr class="even">
<td><p>테스트-CsGroupIM – TestJoinLauncher 관리자 (Join시작 관리자)</p></td>
<td><p>사용자가 웹 주소 링크를 통해 예약 된 모임을 만들고 참가할 수 있는지 확인 합니다.</p></td>
<td><p>비기본</p></td>
</tr>
<tr class="odd">
<td><p>CsMCXP2PIM (MCXP2PIM)</p></td>
<td><p>모바일 장치 사용자가 인스턴트 메시지를 등록 하 고 보낼 수 있는지 확인 합니다.</p></td>
<td><p>비기본</p></td>
</tr>
<tr class="even">
<td><p>CsPersistentChatMessage (PersistentChatMessage)</p></td>
<td><p>사용자가 영구 채팅 서비스를 사용 하 여 메시지를 교환할 수 있는지 확인 합니다.</p></td>
<td><p>비기본</p></td>
</tr>
<tr class="odd">
<td><p>CsUnifiedContactStore (UnifiedContactStore)</p></td>
<td><p>통합 된 대화 상대 저장소를 통해 사용자의 연락처에 액세스할 수 있는지 확인 합니다. 통합 된 연락처 저장소는 사용자가 Lync 2013, Outlook, Outlook Web Access를 사용 하 여 액세스할 수 있는 단일 연락처 집합을 유지 관리 하는 방법을 제공 합니다.</p></td>
<td><p>비기본</p></td>
</tr>
<tr class="even">
<td><p>테스트-CsXmppIM (XmppIM)</p></td>
<td><p>XMPP (확장 가능 메시지 및 현재 상태 프로토콜) 게이트웨이에서 인스턴트 메시지를 보낼 수 있는지 확인 합니다.</p></td>
<td><p>비기본</p></td>
</tr>
</tbody>
</table>


System Center Operations Manager를 사용 하기 위해 감시자 노드를 설치할 필요가 없습니다. 이러한 노드를 설치 하지 않은 경우에도 문제가 발생 하면 Lync Server 2013 구성 요소에서 실시간 알림을 받을 수 있습니다. (구성 요소 및 사용자 관리 팩은 감시자 노드를 사용 하지 않습니다.) 그러나 활성 모니터링 관리 팩을 사용 하 여 종단 간 시나리오를 모니터링 하려면 감시자 노드가 필요 합니다.

<div>


> [!NOTE]  
> 또한 관리자는 Operations Manager를 사용 하거나 설치할 필요 없이 수동으로 가상 트랜잭션을 실행할 수 있습니다. 다양 한 테스트 Cs cmdlet에 대 한 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Lync Server 2013 cmdlet 인덱스</A>를 참조 하세요.



</div>

배포의 크기에 따라 가상 트랜잭션에서는 많은 양의 컴퓨터 메모리와 프로세서 시간을 사용할 수 있습니다. 따라서 전용 컴퓨터를 감시자 노드로 사용 하는 것이 좋습니다. 예를 들어, 감시자 노드로 작동 하도록 프런트 엔드 서버를 구성 하지 않아야 합니다. 감시자 노드는 다음 하드웨어 사양을 충족 해야 합니다.

<div>


> [!NOTE]  
> Lync Server 2013 감시자 노드가 있는 컴퓨터에서 레거시 Microsoft Lync Server 2010 감시자 노드를 collocated 수 없습니다. 이는 Lync Server 2010의 핵심 시스템 파일과 Lync Server 2013을 같은 컴퓨터에 설치할 수 없기 때문입니다.<BR>그러나 Lync Server 2013 감시자 노드는 Lync Server 2013 및 Lync Server 2010을 동시에 모니터링할 수 있습니다. 기본 가상 트랜잭션은 두 제품 버전에서 모두 지원 됩니다.



</div>

Lync Server 2013 감시자 노드는 엔터프라이즈 내부 또는 외부에 배포 되어 확인을 위해 다음을 확인할 수 있습니다.

  - <span></span>  
    엔터프라이즈 내부의 사용자에 대 한 풀에 대 한 연결.

  - <span></span>  
    기업 외부에서 작업 하는 원격 사용자의 경계 네트워크를 통한 연결.

  - <span></span>  
    지사 기기에 대 한 연결.

  - <span></span>  
    기업 및 경계 네트워크 내부의 Lync Server 2010 연결

관리를 간소화 하기 위해 엔터프라이즈 내부 및 외부에서 다양 한 인증 옵션을 사용할 수 있습니다. 자세한 내용은 [Lync Server 2013에서 가상 트랜잭션을 실행 하도록 감시자 노드 구성을](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md)참조 하세요.

컴퓨터가 감시자 노드로 작동 하도록 구성 하려면 System Center Operations Manager를 설치 하 고 Lync Server 2013 관리 팩을 가져온 후에 다음 단계를 완료 해야 합니다.

Lync Server 2013 core 파일 및 System Center 에이전트 파일을 설치 하기 전에, 감시자 노드 컴퓨터가 Lync Server 2013을 설치 하기 위한 모든 선행 조건을 충족 하는지 확인 해야 합니다. 또한 감시자 노드 컴퓨터에는 다음 항목도 설치 되어 있어야 합니다.


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
<td><p>%</p></td>
<td><p>다음 중 하나입니다.</p>
<ul>
<li><p>64 비트 프로세서, 쿼드 코어, 2.33 GHz 이상</p></li>
<li><p>64 비트 양방향 프로세서, 듀얼 코어, 2.33 GHz 이상</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Memory</p></td>
<td><p>8gb</p></td>
</tr>
<tr class="odd">
<td><p>네트워크 운영 체제</p></td>
<td><ul>
<li><p>1 Gbps 네트워크 어댑터</p></li>
<li><p>Windows Server 2008 R2, Windows Server 2012 또는</p>
<p>Windows Server 2012 R2</p></li>
</ul></td>
</tr>
</tbody>
</table>


  - 전체 버전의 .NET Framework 4.5.

  - Windows Id 파운데이션.

  - Windows PowerShell 3.0.

이러한 전제 조건이 모두 충족 되 면 다음을 기준으로 감시자 노드를 구성할 수 있습니다.

  - 감시자 노드 컴퓨터에 Lync Server 2013 core 파일을 설치 합니다.

  - 감시자 노드 컴퓨터에 System Center Operations Manager 에이전트를 설치 하는 중입니다.

  - Watchernode 실행 파일을 실행 합니다.

  - **CsWatcherNodeConfiguration** cmdlet을 사용 하 여 감시자 노드에서 사용할 테스트 사용자를 구성 합니다.

</div>

<span> </span>

</div>

</div>

</div>

