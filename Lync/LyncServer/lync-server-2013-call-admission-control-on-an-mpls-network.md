---
title: 'Lync Server 2013: MPLS 네트워크에서 통화 허용 제어'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call admission control on an MPLS network
ms:assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398168(v=OCS.15)
ms:contentKeyID: 48183387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee138a0f61bace067db12c9df4f06338aa13ac8b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979929"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-on-an-mpls-network-with-lync-server-2013"></a>Lync Server 2013에서 MPLS 네트워크에 대 한 통화 허용 제어

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-22_

멀티 프로토콜 레이블 전환 (MPLS) 네트워크에서 모든 사이트는 풀 메시로 연결 됩니다. 즉, 모든 사이트가 인터넷 서비스 공급자의 MPLS 백본으로 직접 연결 되며, 각 사이트는 MPLS 클라우드의 WAN 링크에서 사용할 수 있도록 프로 비전 된 대역폭을 제공 합니다. IP 라우팅을 제어 하는 네트워크 허브나 중앙 사이트는 없습니다. 다음 그림은 MPLS 기술을 기반으로 하는 간단한 네트워크를 보여줍니다.

**예제 MPLS 네트워크**

(images/Gg398168.54602e6e-ec11-4dae-936d-b01acda8a179(OCS.15).jpg "MPLS 있는 MPLS cac") ![포함 cac]

MPLS 네트워크에 CAC (call 허용 제어)를 배포 하려면 MPLS 클라우드를 나타내는 네트워크 영역을 만들고 각 MPLS 위성 사이트를 나타내는 네트워크 사이트를 만듭니다. 다음 그림에서는 네트워크 지역과 네트워크 사이트를 구성 하 여 이전 그림의 예제 MPLS 네트워크를 표시 하는 방법을 보여 줍니다. 각 네트워크 사이트에서 MPLS 클라우드를 나타내는 네트워크 지역으로의 WAN 링크 용량을 기준으로 전체 대역폭 한도와 대역폭 세션 한도가 적용 됩니다.

**MPLS 네트워크에 대 한 네트워크 지역 및 네트워크 사이트**

(images/Gg398168.f8f76283-5c0c-4133-8a78-3fbbfd016dc4(OCS.15).jpg "MPLS 다이어그램을 사용 하는 MPLS 다이어그램 호출 허용 제어 (cac)") ![와의 호출 허용 제어 (cac])

</div>

<span> </span>

</div>

</div>

</div>

