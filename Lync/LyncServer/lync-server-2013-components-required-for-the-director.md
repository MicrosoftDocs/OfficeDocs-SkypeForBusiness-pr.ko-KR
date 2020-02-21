---
title: 'Lync Server 2013: 디렉터에 필요한 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for the Director
ms:assetid: 15c7c8d4-b93f-4386-b2d1-d76dab8f801e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398228(v=OCS.15)
ms:contentKeyID: 48183502
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84a5765ce21ba955e4354c693171180a9d828210
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204704"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-required-for-the-director-in-lync-server-2013"></a>Lync Server 2013의 디렉터에 필요한 구성 요소

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-08_

디렉터를 만들고 구성 하는 데 필요한 유일한 구성 요소는 디렉터 서버 역할을 배포 하는 것입니다. 토폴로지 작성기를 사용 하 여이 작업을 수행 하 고 디렉터 풀 노드에 단일 컴퓨터 풀 또는 다중 컴퓨터 풀을 정의 합니다. 디렉터 또는 디렉터 풀을 정의한 후에는 디렉터가 될 컴퓨터에서 Lync Server 배포 마법사를 실행 합니다. 디렉터 풀의 경우 풀의 구성원이 되는 각 서버에서 Lync Server 배포 마법사를 실행 합니다.

<div>

## <a name="topologies"></a>기술

단일 디렉터 서버 또는 디렉터 풀을 구현할 수 있습니다. 배치 된은 Lync Server 2013의 다른 서버 역할을 사용 하는 것이 아니라 항상 별도의 서버 또는 풀입니다.

<div>


> [!NOTE]  
> 디렉터를 배포 하지 않으면 프런트 엔드 서버 또는 프런트 엔드 풀에서 디렉터 역할을 가정 합니다.



</div>

디렉터 풀은 부하 분산 되어 있어야 합니다. 다음 중 하나를 수행할 수 있습니다.

  - 웹 서비스에는 하드웨어 부하 분산 장치를 사용하고 다른 트래픽 유형에는 DNS(Domain Name System) 부하 분산을 사용하는 토폴로지를 만듭니다.
    
    [Lync Server 2013의 확장 된 디렉터 풀-DNS 부하 분산 및 하드웨어 부하 분산 장치](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - 디렉터 풀에 필요한 부하 분산을 위해 하드웨어 부하 분산 장치를 사용 하는 토폴로지를 만듭니다.
    
    [확장 된 디렉터 풀-Lync Server 2013의 하드웨어 부하 분산 장치](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

