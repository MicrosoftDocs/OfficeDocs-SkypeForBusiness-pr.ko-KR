---
title: System Center discovery에 참여 하도록 Lync Server 컴퓨터 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the Lync Server computer to participate in System Center discovery
ms:assetid: 2f9c9cb0-3120-4571-9cd2-657c2123fe21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204776(v=OCS.15)
ms:contentKeyID: 48183731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b8e95ead01c89f33346a66a8212245c2350894f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154270"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-2013-computer-to-participate-in-system-center-discovery"></a>System Center discovery에 참여 하도록 Lync Server 2013 컴퓨터 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-20_

새 Lync Server 에이전트가 System Center Operations Manager의 검색 프로세스에 참여 하는지 확인 하려면 System Center Operations Manager 콘솔이 설치 된 각 컴퓨터에서 다음 절차를 완료 해야 합니다.

1.  **관리** 탭에서 **에이전트에서 관리**를 클릭합니다.

2.  컴퓨터의 이름을 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다. **속성** 대화 상자의 **보안** 탭에서 **이 에이전트를 프록시로 허용하고 다른 컴퓨터에서 관리되는 개체 검색**을 선택하고 **확인**을 클릭합니다.

2단계를 완료한 후 상태 에이전트 서비스를 다시 부팅합니다. 서비스를 다시 부팅하면 새 컴퓨터 검색이 "강제 수행"됩니다. 서비스를 다시 부팅하지 않으면 System Center Operations Manager에서 새 컴퓨터를 검색할 때까지 최대 4시간이 걸릴 수 있습니다. 서비스가 다시 부팅되고 나면 해당 컴퓨터의 작업 관리자 이벤트 로그에 오류 이벤트가 기록되지 않는지 확인합니다.

</div>

<span> </span>

</div>

</div>

</div>

