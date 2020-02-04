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
ms.openlocfilehash: 8081ba60d826f0f765533abdb6c0f548045a7fa8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="load-balancing-requirements-for-lync-server-2013"></a>Lync Server 2013에 대 한 부하 분산 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-05_

프런트 엔드 풀, 디렉터 풀 또는 Edge 서버 풀을 사용 하는 경우 이러한 풀에 대 한 부하 분산을 배포 해야 합니다. 부하 분산은 풀의 서버 간에 트래픽을 분산 시킵니다.

Lync Server 2013는 DNS (Domain Name System) 부하 분산 및 하드웨어 부하 분산에 대해 클라이언트 간 트래픽에 대 한 두 가지 유형의 부하 분산 솔루션을 지원 합니다. DNS 부하 분산 기능을 통해 더 간단한 관리, 보다 효율적인 문제 해결, 다양 한 하드웨어 로드 균형 조정기 문제 로부터 Lync 서버 소통량의 대부분을 격리할 수 있습니다.

배포의 각 풀에 적합 한 부하 분산 솔루션을 결정 하 고 다음 제한 사항을 염두에 두어야 합니다.

  - 내부 에지 인터페이스와 외부 에지 인터페이스는 같은 유형의 부하 분산을 사용해야 합니다. 한 인터페이스에서 DNS 부하 분산을 사용할 수 없으며, 그 밖의 하드웨어 로드 균형 조정이 없습니다.

  - 일부 트래픽 유형에는 하드웨어 부하 분산이 필요 합니다. 예를 들어 HTTP 트래픽에는 DNS 부하 분산 대신 하드웨어 부하 분산이 필요 합니다. DNS 부하 분산이 클라이언트와 서버 간 웹 트래픽에 작동 하지 않습니다.

하드웨어 부하 분산 장치 솔루션 선택에 대 한 자세한 내용은 [Lync Server 2013의 하드웨어 부하 분산 장치 요구 사항](lync-server-2013-hardware-load-balancer-requirements.md)을 참조 하세요.

풀에 대해 DNS 부하 분산을 사용 하도록 선택 했지만 HTTP 트래픽 등의 트래픽에 대 한 하드웨어 로드 균형 조정기도 구현 해야 하는 경우 하드웨어 로드 균형 조정기의 관리가 매우 간소화 됩니다. 예를 들어 하드웨어 부하 분산 장치 구성은 HTTP 및 HTTPS 트래픽만 관리 하 고 다른 모든 프로토콜은 DNS 부하 분산으로 관리 되므로 더 간단 합니다. 자세한 내용은 [Lync Server 2013의 DNS 부하 분산](lync-server-2013-dns-load-balancing.md)을 참조 하세요.

서버 간 트래픽의 경우, Lync 서버 2013는 토폴로지 인식 부하 분산을 사용 합니다. 서버는 중앙 관리 저장소에서 게시 된 토폴로지를 읽어 토폴로지에 있는 서버의 Fqdn을 확보 하 고 서버 간에 트래픽을 자동으로 배포 합니다. 관리자는 이러한 유형의 부하 분산을 설정 하거나 관리할 필요가 없습니다.

DNS 부하 분산을 사용 하는 경우 특정 컴퓨터로의 트래픽을 차단 해야 하는 경우에는 풀 FQDN에서 IP 주소 항목을 제거 하는 것 만으로는 충분 하지 않습니다. 컴퓨터 에서도 DNS 항목을 제거 해야 합니다.

</div>

<span> </span>

</div>

</div>

</div>

