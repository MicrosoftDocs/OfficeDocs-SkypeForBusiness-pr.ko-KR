---
title: 시스템 센터 검색에 참가 하도록 Lync Server 컴퓨터 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the Lync Server computer to participate in System Center discovery
ms:assetid: 2f9c9cb0-3120-4571-9cd2-657c2123fe21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204776(v=OCS.15)
ms:contentKeyID: 48183731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4b50fad3e0d197259847db9a94bf9e64618d7e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-2013-computer-to-participate-in-system-center-discovery"></a>시스템 센터 검색에 참가 하도록 Lync Server 2013 컴퓨터 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-20_

새 Lync Server 에이전트가 System Center Operations Manager의 검색 프로세스에 참여 하 고 있는지 확인 하려면 System Center Operations Manager 콘솔이 설치 된 각 컴퓨터에서 다음 절차를 완료 해야 합니다.

1.  **관리** 탭에서 **에이전트 관리**를 클릭 합니다.

2.  컴퓨터의 이름을 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다. **속성** 대화 상자의 **보안** 탭에서 **이 에이전트가 프록시로 작동할 수 있도록 허용을 선택 하 고 다른 컴퓨터에서 관리 되는 개체를 검색**한 다음 **확인**을 클릭 합니다.

2 단계를 완료 한 후 상태 에이전트 서비스를 다시 부팅 합니다. (서비스를 다시 부팅 하면 새 컴퓨터에 "강제" 검색을 수행 합니다. 서비스를 다시 부팅 하지 않으면 시스템 센터 Operations Manager에서 새 컴퓨터가 검색 되기까지 4 시간 정도 걸릴 수 있습니다. 서비스를 다시 부팅 한 후 해당 컴퓨터의 Operations Manager 이벤트 로그에 오류 이벤트가 기록 되지 않는지 확인 합니다.

</div>

<span> </span>

</div>

</div>

</div>

