---
title: 'Lync Server 2013: IPv6에 대한 마이그레이션 및 동시 사용 고려 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migration and coexistence considerations for IPv6
ms:assetid: 8c769c4f-c8a9-4cbf-9080-beee3be9848a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205068(v=OCS.15)
ms:contentKeyID: 48184751
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8adf81df14d5c87eb2b54b63d9a58fc1b6f5b97e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-and-coexistence-considerations-for-ipv6-in-lync-server-2013"></a>Lync Server 2013의 IPv6에 대한 마이그레이션 및 동시 사용 고려 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-06-14_

Lync Server 2010 또는 Office Communications Server에서는 IPv6 (IP 버전 6)이 지원 되지 않습니다. 시험 운용 목적으로 Lync Server 2010 및 Lync Server 2013 이중 스택 공존을 테스트할 수 있습니다. 모든 풀에 대해 IPv6 (듀얼 스택 네트워크)을 사용 하도록 설정 하기 전에 지정 된 중앙 사이트의 모든 풀을 Lync Server 2013로 업그레이드 하는 것이 좋습니다. IPv6에 대해서만 풀을 구성 해야 하는 경우 테스트를 위해 랩 환경에서 IPv6 전용 풀을 설정 하는 것이 좋습니다.

마이그레이션 및 공존 중에 지원 되는 시나리오는 다음과 같습니다.

  - IPv4 모드의 lync Server 2013, Lync Server 2010 및 Office Communications Server 2007 R2 풀은 듀얼 스택 모드에서 Lync Server 2013를 사용 하 여 동시에 공존할 것입니다.

  - Ipv6 전용 풀이 siloed 인 경우에는 ipv6 전용 모드의 Lync Server 2013 풀입니다.

</div>

<span> </span>

</div>

</div>

</div>

