---
title: 서버 유지 관리를 위한 Lync Server의 새 연결 금지
description: 서버 유지 관리를 위해 Lync Server에 대 한 새 연결을 차단 합니다.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prevent new connections to Lync Server for server maintenance
ms:assetid: 22b27adf-a590-43bd-9306-a5789ae108d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520964(v=OCS.15)
ms:contentKeyID: 48183625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd676467cdd6b5bb430f972e48c2f3a53f3f6f14
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579834"
---
# <a name="prevent-new-connections-to-lync-server-2013-for-server-maintenance"></a>서버 유지 관리를 위해 Lync Server 2013에 대 한 새 연결 차단

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

Lync Server를 사용 하면 사용자에 대 한 서비스 손실 없이도 서버를 오프 라인으로 설정 (예: 소프트웨어 또는 하드웨어 업그레이드 적용) 할 수 있습니다.

풀의 서버에 대한 새 연결 또는 통화를 방지하기 위한 옵션을 지정하면 이 옵션을 구현하는 즉시 새 연결 및 호출 수행이 중지됩니다. 이러한 새 연결 및 통화는 풀의 다른 서버를 통해 라우팅됩니다. 새 연결을 방지하는 서버는 기존 연결의 세션을 자연적으로 종료될 때까지 둡니다. 모든 기존 세션이 종료되면 서버를 오프라인으로 설정할 수 있습니다.

프런트 엔드 서버에 대 한 새 연결을 차단 하면 일부 Lync Server 기능 및 서비스가 DNS 부하 분산을 사용 하 여 제대로 작동 하는지 확인 합니다. 풀에서 DNS 부하 분산을 사용하지 않는 경우, 이러한 서비스를 통한 연결이 서버가 새 연결을 방지하는 기간 동안 다른 서버로 다시 라우팅되지 않아 서버가 오프라인으로 설정될 때 일부 세션 및 통화가 중단될 수 있습니다. 이 옵션이 적절하게 작동하도록 하기 위해 DNS 부하 분산을 사용하는 기능은 다음과 같습니다.

  - 도우미

  - 회의 알림 응용 프로그램

  - 응답 그룹 응용 프로그램

  - Announcement application(알림 응용 프로그램)

  - 통화 대기 응용 프로그램

DNS 부하 분산에 대 한 자세한 내용은 계획 설명서에서 [Lync Server 2013의 dns 부하 분산](lync-server-2013-dns-load-balancing.md) 을 참조 하십시오.

Lync Server를 실행 하는 서버의 모든 서비스에 대 한 새 연결을 차단 하는 것 외에, 개별 Lync Server 서비스에 대 한 새 연결을 차단할 수도 있습니다. 예를 들어이 방법은 전체 서버를 종료할 필요가 없는 Lync Server 업데이트를 적용 해야 하는 경우에 유용 합니다. 특정 서비스에 대한 연결을 방지할 때는 Windows 서비스 목록에서 그룹화되어 표시되는 서비스를 선택해야 합니다. 예를 들어 Lync Server Front-End 서비스와 모니터링에 대 한 데이터 수집 에이전트는 별도의 Lync Server 서비스 이지만 Windows 서비스 목록에 통합 되어 Lync Server 프런트 엔드 서비스로 표시 됩니다. Lync Server 프런트 엔드 서비스에 대 한 새 연결이 차단 되지만 이러한 두 가지 개별 Lync Server 서비스에 대 한 새 연결은 별도로 방지할 수 없습니다.

<div>


> [!IMPORTANT]
> 새 연결을 차단하도록 서버를 설정한 후에 서버를 다시 시작하면 기본적으로 서버가 시작된 직후 새 연결을 허용하기 시작합니다. 이러한 현상을 방지하려면 서버를 다시 시작하기 전에 서버를 수동으로만 일시 중지 및 다시 시작하도록 설정합니다.



</div>

<div>

## <a name="to-prevent-new-connections-to-lync-server"></a>Lync Server에 대 한 새 연결을 차단 하려면 다음을 수행 합니다.

1.  Administrators 그룹의 구성원으로 로컬 컴퓨터에 로그온 합니다.

2.  **시작**을 클릭 하 고 **모든 프로그램**, **관리 도구**를 차례로 가리킨 다음 **서비스**를 클릭 하 여 서비스 스냅인 콘솔을 엽니다.

3.  목록에서 새 연결을 금지할 Lync Server Windows 서비스를 두 번 클릭 합니다.

4.  속성 대화 상자의 **서비스 상태: 시작 됨**에서 **일시 중지**를 클릭 합니다.

5.  또는 **시작 유형**옆의 **수동**을 클릭 합니다 (선택 사항).
    
    <div>
    

    > [!IMPORTANT]
    > 새 연결을 차단하도록 서버를 설정한 후에 서버를 다시 시작하면 기본적으로 서버가 시작된 직후 새 연결을 허용하기 시작합니다. 이러한 현상을 방지하려면 서버를 다시 시작하기 전에 서버를 수동으로만 일시 중지 및 다시 시작하도록 설정합니다.

    
    </div>

6.  작업이 끝나면 **확인**을 클릭합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

