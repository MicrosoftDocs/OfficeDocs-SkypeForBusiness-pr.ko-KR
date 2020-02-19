---
title: Lync Server 2013 부하 분산 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Load balancing requirements
ms:assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615011(v=OCS.15)
ms:contentKeyID: 48184697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83e5ebe92601b839f50604a93f10f7fc2f5d7deb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134964"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="load-balancing-requirements-for-lync-server-2013"></a>Lync Server 2013에 대 한 부하 분산 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-05_

프런트 엔드 풀, 디렉터 풀 또는에 지 서버 풀을 보유 하 고 있는 경우 이러한 풀에 대 한 부하 분산을 배포 해야 합니다. 부하 분산은 풀의 서버 간에 트래픽을 분산시킵니다.

Lync Server 2013에서는 클라이언트와 서버 간 트래픽에 대 한 두 가지 유형의 부하 분산 솔루션, 즉 DNS (Domain Name System) 부하 분산 및 하드웨어 부하 분산을 지원 합니다. DNS 부하 분산은 보다 간단한 관리, 보다 효율적인 문제 해결, 모든 잠재적 하드웨어 부하 분산 장치 문제에 대 한 Lync Server 트래픽의 대부분을 격리 하는 기능 등의 여러 가지 이점을 제공 합니다.

다음 제한에 유의하여 배포의 각 풀에 적합한 부하 분산 솔루션을 결정하십시오.

  - 내부 에지 인터페이스와 외부 에지 인터페이스는 같은 유형의 부하 분산을 사용해야 합니다. 즉, 한 인터페이스에서는 DNS 부하 분산을 사용하고 다른 인터페이스에서는 하드웨어 부하 분산을 사용할 수는 없습니다.

  - 일부 트래픽 유형의 경우 하드웨어 부하 분산 장치를 사용해야 합니다. 예를 들어 HTTP 트래픽에는 DNS 부하 분산이 아닌 하드웨어 부하 분산 장치가 필요합니다. DNS 부하 분산은 클라이언트-서버 간 웹 트래픽에서 작동하지 않습니다.

하드웨어 부하 분산 장치 솔루션을 선택 하는 방법에 대 한 자세한 내용은 [Lync Server 2013의 하드웨어 부하 분산 장치 요구 사항](lync-server-2013-hardware-load-balancer-requirements.md)를 참조 하세요.

풀에 대해 DNS 부하 분산을 사용하지만 HTTP 트래픽 등의 트래픽에 대해서는 하드웨어 부하 분산 장치를 구현해야 하는 경우 하드웨어 부하 분산 장치의 관리는 훨씬 간소화됩니다. 예를 들어 하드웨어 부하 분산 장치 구성은 HTTP 및 HTTPS 트래픽만 관리 하는 것 보다 더 간단 하며, 다른 모든 프로토콜은 DNS 부하 분산을 통해 관리 됩니다. 자세한 내용은 [Lync Server 2013의 DNS 부하 분산](lync-server-2013-dns-load-balancing.md)을 참조 하십시오.

서버 간 트래픽의 경우 Lync Server 2013에서는 토폴로지를 통해 부하 분산을 사용 합니다. 서버는 중앙 관리 저장소에서 게시 된 토폴로지를 읽어 토폴로지의 서버 Fqdn을 가져오고 서버 간에 트래픽을 자동으로 분산 합니다. 관리자는 이러한 유형의 부하 분산을 설정 하거나 관리할 필요가 없습니다.

DNS 부하 분산을 사용 하는 경우 특정 컴퓨터로의 트래픽을 차단 해야 하는 경우에는 풀 FQDN에서 IP 주소 항목을 제거 하는 것 만으로는 충분 하지 않습니다. 또한 컴퓨터에 대 한 DNS 항목도 제거 해야 합니다.

</div>

<span> </span>

</div>

</div>

</div>

