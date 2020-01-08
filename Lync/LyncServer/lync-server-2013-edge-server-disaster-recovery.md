---
title: 'Lync Server 2013: 에지 서버 재해 복구'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Edge Server disaster recovery
ms:assetid: 05ec8d26-d167-4a6f-a966-a1f8873cf974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687960(v=OCS.15)
ms:contentKeyID: 49733545
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d19e5a606c3217ad7653fd4c3c885a97aafdb5ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983592"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edge-server-disaster-recovery-in-lync-server-2013"></a>Lync Server 2013의 에지 서버 재해 복구

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-03-12_

다른 서버 역할의 경우와 마찬가지로, Edge 서버에서 고가용성을 제공 하는 가장 좋은 방법은 각 사이트의 풀에 여러 개의 Edge 서버를 배포 하는 것입니다. 한 쪽 서버의 작동이 중단 되 면 풀의 다른 서버는 계속 해 서 Edge 서비스를 제공 합니다.

재해 복구 절차를 사용 하려면 별도의 사이트에 별도의 Edge 서버 풀이 배포 되어 있어야 합니다. 프런트 엔드 풀을 사용 하는 것과 동일한 방법으로 Edge 풀을 명시적으로 쌍으로 묶을 필요는 없지만, 여러 개의 Edge 풀을 사용 하면 한 전체 Edge 풀이 중단 되는 경우 계속 사용할 수 있게 됩니다. 다음 섹션에서는 Edge 서버의 다양 한 기능에 대 한 재난 복구에 대 한 세부 정보를 제공 합니다.

<div>

## <a name="remote-access"></a>원격 액세스

각 사이트에 대 한 Edge 서버 풀이 있고 하나의 전체 Edge 풀에 장애가 발생 하는 경우에는 관리자 작업이 필요 없이 원격 액세스 서비스가 계속 작동 합니다. 여러 사이트에서 Edge 풀을 만들 때 동일한 FQDN을 사용할 수 없습니다. 각 Edge 풀에는 고유한 Fqdn (내부 및 외부)이 있어야 합니다. Edge 풀은 프런트 엔드 서버와 대화 하는 데 역방향 프록시 게시 규칙을 사용 하지 않습니다. 자동 장애 조치 (failover)는 클라이언트가 원격 액세스 DNS 서비스 레코드를 다시 쿼리 하 고 원격 사용자가 다른 사이트의 Edge 서버로 라우팅되는 경우에 발생 합니다. 클라이언트가 DNS SRV 레코드의 우선 순위에 따라 각 외부에 지 FQDN을 시도 합니다.

<div>


> [!NOTE]  
> 장애 조치가 원활 하 게 작동 하려면 방화벽에서 모든 Edge 서버와 통신 하는 데 모든 풀의 프런트 엔드 서버를 허용 해야 합니다.



</div>

</div>

<div>

## <a name="federation"></a>페더레이션

Lync Server를 실행 하는 다른 조직과의 페더레이션 관계의 경우 지역-DNS GTM와 같은 해결 방법이 있으면 인바운드 페더레이션 요청이 계속 작동 합니다. 페더레이션 장애 조치는 SRV 레코드의 우선 순위에 대 한 장애 조치를 제공 하지 않는다는 점을 이해 하는 것이 중요 합니다. 이전에 제공 되는 솔루션을 통해 인바운드 페더레이션에 대 한 재해 복구 기능을 제공할 수 있습니다.

아웃 바운드 페더레이션은 조직에서 게시 된 하나의 Edge 풀 또는 Edge 서버를 통해 항상 설정 됩니다. 이 Edge 풀이 다운 된 경우 토폴로지 작성기를 사용 하 여 계속 실행 중인 Edge 풀을 사용 하도록 아웃 바운드 페더레이션 경로를 변경 해야 합니다. 자세한 내용은 Lync server [2013에서 Lync server federation에 사용 되는 Edge 풀을 통한 장애 조치](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md) 를 참조 하세요.

</div>

<div>

## <a name="xmpp-federation"></a>XMPP 페더레이션

Xmpp 페더레이션의 경우 XMPP 페더레이션 게이트웨이로 지정 된 가장자리 풀이 작동 하지 않으면 아웃 바운드 및 인바운드 트래픽 모두 실패 합니다. XMPP 페더레이션이 다시 작동 하도록 만들려면 다른 Edge 풀을 사용 하도록 XMPP 페더레이션을 변경 해야 합니다. 자세한 내용은 [Lync Server 2013에서 XMPP 페더레이션에 사용 되는 Edge 풀을 통한 장애 조치](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)를 참조 하세요.

</div>

<div>

## <a name="edge-pool-fails-but-front-end-pool-is-still-running"></a>Edge 풀에 실패 하지만 프런트 엔드 풀은 계속 실행 중입니다.

사이트에서 가장자리 풀이 실패 하지만 해당 사이트의 프런트 엔드 풀은 계속 실행 되 고 있는 경우, 첫 번째 Edge 풀이 중단 된 동안 다른 사이트에서 다른 Edge 풀을 사용 하도록 프런트 엔드 풀을 변경 해야 합니다. 자세한 내용은 [Lync Server 2013의 프런트 엔드 풀에 연결 된 Edge 풀 변경을](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

