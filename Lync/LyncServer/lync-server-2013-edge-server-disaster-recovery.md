---
title: Lync Server 2013:에 지 서버 재해 복구
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edge Server disaster recovery
ms:assetid: 05ec8d26-d167-4a6f-a966-a1f8873cf974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687960(v=OCS.15)
ms:contentKeyID: 49733545
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 519243475f5452cebc6fff82cc54f267bb8b36fd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136355"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="edge-server-disaster-recovery-in-lync-server-2013"></a>Lync Server 2013의에 지 서버 재해 복구

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-03-12_

다른 서버 역할과 마찬가지로, 에지 서버에 대해 고가용성을 제공하는 가장 효율적인 방법은 각 사이트의 풀에서 여러 에지 서버를 배포하는 것입니다. 이 경우 에지 서버 하나가 다운되면 풀의 다른 서버가 에지 서비스를 계속 제공합니다.

재해 복구 절차를 수행할 수 있도록 설정하려면 서로 다른 사이트에 개별 에지 서버 풀을 배포한 상태여야 합니다. 프런트 엔드 풀에서처럼 에지 풀 쌍을 명시적으로 지정할 필요는 없지만, 여러 에지 풀을 포함하는 경우 전체 에지 풀 하나가 다운되어도 작업을 계속할 수 있습니다. 다음 섹션에서는 다양한 에지 서버 기능의 재해 복구에 대해 자세히 설명합니다.

<div>

## <a name="remote-access"></a>원격 액세스

각각에 지 서버 풀을 포함 하는 여러 사이트가 있고, 하나의 전체에 지 풀에 오류가 발생 하는 경우에는 원격 액세스 서비스가 관리자 작업 없이도 계속 작동 합니다. 서로 다른 사이트에에 지 풀을 만들 때는 동일한 FQDN을 사용할 수 없습니다. 각에 지 풀에는 고유 Fqdn (내부 및 외부)이 있어야 합니다. 에 지 풀은 역방향 프록시 게시 규칙을 사용 하 여 프런트 엔드 서버와 통신 하지 않습니다. 자동 장애 조치 (failover)는 클라이언트가 원격 액세스 DNS 서비스 레코드를 다시 쿼리하거나 원격 사용자가 다른 사이트의에 지 서버로 라우팅되는 경우 발생 합니다. 클라이언트는 DNS SRV 레코드의 우선 순위에 따라 각 외부에 지 FQDN을 시도 합니다.

<div>


> [!NOTE]  
> 장애 조치 (failover)가 원활 하 게 작동 하려면 모든 풀의 프런트 엔드 서버가 모든에 지 서버와 통신할 수 있도록 하는 방화벽을 사용 해야 합니다.



</div>

</div>

<div>

## <a name="federation"></a>연결

Lync Server를 실행 하는 다른 조직과의 페더레이션 관계의 경우 지리적 DNS GTM 같은 해결 방법이 있으면 인바운드 페더레이션 요청이 계속 작동 합니다. 페더레이션 장애 조치 (failover)에서는 SRV 레코드의 우선 순위를 사용 하 여 장애 조치 (failover)를 제공 하지 않습니다. 이전에 제공 된 솔루션은 인바운드 페더레이션에 대 한 재해 복구 기능을 제공 하는 데 도움이 될 수 있습니다.

아웃바운드 페더레이션은 항상 조직의 게시된 에지 풀 또는 에지 서버 하나를 통해 설정됩니다. 이 에지 풀이 다운되는 경우에는 토폴로지 작성기를 사용하여 계속 실행 중인 에지 풀을 사용하도록 아웃바운드 페더레이션 경로를 변경해야 합니다. 자세한 내용은 [Lync server 2013의 Lync server federation에 사용 된에 지 풀 장애 조치](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md) (failover)를 참조 하세요.

</div>

<div>

## <a name="xmpp-federation"></a>XMPP 페더레이션

XMPP 페더레이션의 경우에는 XMPP 페더레이션 게이트웨이로 지정된 에지 풀이 다운되는 경우 아웃바운드 및 인바운드 트래픽에서 모두 오류가 발생합니다. XMPP 페더레이션이 다시 작동하도록 하려면 다른 에지 풀을 사용하도록 XMPP 페더레이션을 변경해야 합니다. 자세한 내용은 [Lync Server 2013에서 XMPP 페더레이션에 사용 되는에 지 풀 장애 조치](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)(failover)를 참조 하세요.

</div>

<div>

## <a name="edge-pool-fails-but-front-end-pool-is-still-running"></a>에지 풀에 오류가 발생해도 프런트 엔드 풀은 계속 실행됨

사이트에서 에지 풀에 오류가 발생했는데 해당 사이트의 프런트 엔드 풀은 계속 실행되는 경우에는 첫 번째 에지 풀이 다운된 동안 다른 사이트의 다른 에지 풀을 사용하도록 프런트 엔드 풀을 변경해야 합니다. 자세한 내용은 [Lync Server 2013에서 프런트 엔드 풀과 연결 된에 지 풀 변경을](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

