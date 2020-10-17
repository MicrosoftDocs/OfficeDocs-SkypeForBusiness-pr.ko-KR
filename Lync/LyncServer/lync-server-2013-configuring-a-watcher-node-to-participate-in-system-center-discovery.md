---
title: System Center discovery에 참여 하도록 감시자 노드 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to participate in System Center discovery
ms:assetid: 15c5dcfd-603b-47ea-af1b-8714c2ec08af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204704(v=OCS.15)
ms:contentKeyID: 48183500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 49b34e623b885bb7e85afc258c1d533c2a8feb46
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527005"
---
# <a name="configuring-a-watcher-node-in-lync-server-2013-to-participate-in-system-center-discovery"></a>System Center discovery에 참여 하도록 Lync Server 2013에서 감시자 노드 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-22_

감시자 노드가 System Center Operations Manager의 검색 프로세스에 참여 하는지 확인 하려면 System Center Operations Manager 콘솔이 설치 된 컴퓨터에서 다음 절차를 완료 해야 합니다.

1.  **관리** 탭에서 **에이전트에서 관리**를 클릭합니다.

2.  감시자 노드 컴퓨터의 이름을 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다. **속성** 대화 상자의 **보안** 탭에서 **이 에이전트를 프록시로 허용하고 다른 컴퓨터에서 관리되는 개체 검색**을 선택하고 **확인**을 클릭합니다.

감시자 노드가 프록시로 작동하도록 구성한 후 감시자 노드 컴퓨터를 다시 부팅합니다. 컴퓨터를 다시 부팅 한 후에는 해당 컴퓨터의 Operations Manager 이벤트 로그에 오류 이벤트가 기록 되지 않는지 확인 합니다. 15 분 동안 컴퓨터를 실행 한 후 Operations Manager 콘솔을 사용 하 여 lync Server 컴퓨터가 **lync** 범주에 나열 되는지 확인 합니다.

</div>

<span> </span>

</div>

</div>

</div>

