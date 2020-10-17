---
title: 'Lync Server 2013: 감시자 노드 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing watcher nodes
ms:assetid: 66deaf49-a71f-4a6e-ada0-ea8b688ee921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688078(v=OCS.15)
ms:contentKeyID: 49733674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94c1e056200a7fc1afec930b7548cfd018c1aa9d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524805"
---
# <a name="managing-watcher-nodes-in-lync-server-2013"></a>Lync Server 2013에서 감시자 노드 관리

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-20_

감시자 노드에서 실행되는 가상 트랜잭션을 수정하는 것 외에도 관리자는 **Set-CsWatcherNodeConfiguration** cmdlet을 사용하여 감시자 노드를 설정 및 해제하고, 테스트를 실행할 때 내부 URL 또는 외부 URL을 사용하도록 감시자 노드를 구성하는 두 가지 중요한 작업을 수행할 수 있습니다.

기본적으로 감시자 노드는 설정된 모든 가상 트랜잭션을 주기적으로 실행하도록 디자인되었습니다. 하지만 일부 경우에는 이러한 트랜잭션을 일시 중지해야 할 수 있습니다. 예를 들어 감시자 노드가 일시적으로 네트워크에서 연결이 해제된 경우에는 가상 트랜잭션을 실행할 이유가 없습니다. 네트워크 연결이 없으면 해당 트랜잭션이 실패할 것이 분명합니다. 감시자 노드를 일시적으로 사용 하지 않도록 설정 하려는 경우 Lync Server 관리 셸에서와 비슷한 명령을 실행 합니다.

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

이 명령은 감시자 노드 atl-watcher- 001.litwareinc.com에서 가상 트랜잭션이 실행되지 않도록 설정합니다. 가상 트랜잭션 실행을 다시 시작하려면 Enabled 속성을 다시 True($True)로 설정합니다.

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

<div>


> [!NOTE]  
> Enabled 속성을 사용하면 감시자 노드를 설정하거나 해제할 수 있습니다. 감시자 노드를 영구적으로 삭제하려면 <STRONG>Remove-CsWatcherNodeConfiguration</STRONG> cmdlet을 사용합니다.<BR>Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"<BR>이 명령은 지정된 컴퓨터에서 모든 감시자 노드 구성 설정을 제거하여 컴퓨터가 가상 트랜잭션을 자동으로 실행하지 못하도록 방지합니다. 그러나이 명령을 수행 해도 System Center 에이전트 파일 또는 Lync Server 2013 시스템 파일은 제거 되지 않습니다.



</div>

기본적으로 감시자 노드는 테스트를 수행할 때 조직 외부의 URL을 사용합니다. 하지만 조직 내부의 URL을 사용하도록 감시자 노드를 구성할 수도 있습니다. 이렇게 하면 관리자가 경계 네트워크 내부에 있는 사용자에 대한 URL 액세스를 확인할 수 있습니다. 감시자 노드가 외부 URL 대신 내부 URL을 사용하도록 구성하려면 UseInternalWebUrls 속성을 True($True)로 설정합니다.

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

이 속성을 기본값인 False($False)로 설정하면 감시자 노드가 외부 URL을 사용합니다.

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

</div>

<span> </span>

</div>

</div>

</div>

