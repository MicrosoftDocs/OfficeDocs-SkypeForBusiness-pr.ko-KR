---
title: 'Lync Server 2013: IPv6의 마이그레이션 및 동시 사용 고려 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration and coexistence considerations for IPv6
ms:assetid: 8c769c4f-c8a9-4cbf-9080-beee3be9848a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205068(v=OCS.15)
ms:contentKeyID: 48184751
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f4a042089c0961eb8ea8313b78bbfcafa72c999
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-and-coexistence-considerations-for-ipv6-in-lync-server-2013"></a>Lync Server 2013의 i p v 6에 대 한 마이그레이션 및 동시 사용 고려 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-06-14_

Lync Server 2010 또는 Office Communications Server에서는 IPv6 (IP 버전 6)이 지원 되지 않습니다. 파일럿을 위해 Lync Server 2010과 Lync Server 2013 이중 스택 공존 성을 테스트할 수 있습니다. 모든 풀에 대해 IPv6 (이중 스택 네트워크)을 사용 하도록 설정 하기 전에 지정 된 중앙 사이트에 대 한 모든 풀을 Lync Server 2013로 업그레이드 하는 것이 좋습니다. IPv6 전용의 풀을 구성해야 할 경우에는 랩 환경에서 테스트 목적으로 IPv6 전용 풀을 설정하는 것이 좋습니다.

마이그레이션 및 동시 사용 중에는 다음과 같은 시나리오가 지원됩니다.

  - IPv4 모드에서 lync Server 2013, Lync Server 2010 및 Office Communications Server 2007 R2 풀은 이중 스택 모드에서 Lync Server 2013과 함께 사용 됩니다.

  - IPv6 전용 풀을 격리 경우에는 IPv6 전용 모드의 Lync Server 2013 풀

</div>

<span> </span>

</div>

</div>

</div>

