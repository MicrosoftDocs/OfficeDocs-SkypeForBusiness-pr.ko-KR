---
title: 'Lync Server 2013: Intertrunk 라우팅'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Intertrunk routing
ms:assetid: d3a33b4a-8bf4-4a8c-a371-8ef79e740780
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205272(v=OCS.15)
ms:contentKeyID: 48185442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23aab6df352b162f7f389ef56fb2300f01654edb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="intertrunk-routing-in-lync-server-2013"></a>Lync Server 2013의 인터 트렁크 라우팅

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-20_

Lync Server 2013는 ip-pbx를 pstn (공중 전화망) 게이트웨이에 상호 연결 하 여 PBX 전화 로부터의 통화를 PSTN으로 경로 설정할 수 있으며 들어오는 PSTN 통화를 PBX (private branch exchange) 전화로 라우팅할 수 있습니다. 마찬가지로 Lync Server 2013는 두 개 이상의 IP PBX 시스템을 상호 연결 하 여 서로 다른 IP PBX 시스템에서 PBX 전화 간에 통화를 주고 받을 수 있도록 합니다.

이 인터 트렁크 라우팅 기능은 Lync Server 관리 셸 cmdlet, **get-cstrunkconfiguration**, new 매개 변수 PstnUsages을 사용 하 여 구성할 수 있습니다. 이 매개 변수는 사용할 PSTN 사용 레코드 집합을 지정 합니다. 트렁크는이 PSTN 사용을 사용 하 여 경로를 결정 하 고 모든 수신 전화를 적절 하 게 라우팅합니다.

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

다음 다이어그램에서는 PSTN 게이트웨이와 ip-pbx 간의 ip-pbx을 제공 하는 Lync Server 2013를 보여 줍니다.

**게이트웨이와 IP PBX 간의 인터 트렁크 라우팅**

![Lync Server 연결 PSTN 게이트웨이/i p-PBX 다이어그램](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server 연결 PSTN 게이트웨이/i p-PBX 다이어그램")

다음 다이어그램에서는 Lync Server 2013 상호 연결 두 개의 IP PBX 시스템을 보여 줍니다.

**두 IP Pbx 사이의 트렁크 라우팅**

![Lync Server 상호 연결 IP-PAX systems 다이어그램](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server 상호 연결 IP-PAX systems 다이어그램")

</div>

<span> </span>

</div>

</div>

</div>

