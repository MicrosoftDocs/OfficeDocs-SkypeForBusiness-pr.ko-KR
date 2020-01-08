---
title: 'Lync Server 2013: 트렁크 간 라우팅'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Inter-trunk routing
ms:assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721940(v=OCS.15)
ms:contentKeyID: 49733877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 204402ba6620fa75b64bb9710ce979b44b63f412
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979312"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="inter-trunk-routing-in-lync-server-2013"></a>Lync Server 2013의 트렁크 간 라우팅

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-08_

Lync Server 2013는 intertrunk 라우팅 지원을 통해 기본적인 세션 관리를 제공 합니다. 이 새로운 접근 권한 값을 통해 Lync Server에서 다운스트림 전화 통신 시스템에 대 한 통화 제어 기능을 제공할 수 있습니다. Intertrunk 라우팅은 IP-PBX (사설 브랜치 교환) 휴대폰의 호출을 PSTN으로 라우팅할 수 있고 들어오는 PSTN 통화를 PBX 전화기로 라우팅할 수 있도록 IP PBX를 PSTN (공개 전환 통신 네트워크) 게이트웨이와 상호 연결할 수 있습니다. 마찬가지로, Lync Server는 두 개 이상의 IP PBX 시스템을 상호 연결 하 여 여러 IP PBX 시스템에서 PBX 전화기 간에 전화를 걸고 받을 수 있습니다.

다음 그림에서는 PSTN 게이트웨이와 IP PBX 간의 interconnectivity을 제공 하는 Lync Server 2013을 보여 줍니다.

Pstn 게이트웨이 ![/i p r-pbx 다이어그램을 연결 하는 Lync SERVER](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "pstn 게이트웨이/i p r-pbx 다이어그램을 연결 하는 lync server")

다음 그림은 두 개의 IP PBX 시스템을 연결 하는 Lync Server 2013을 보여 줍니다.

![Lync server INTERCONNECTING ip-PAX 시스템 다이어그램](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "LYNC server INTERCONNECTING ip-PAX 시스템") 다이어그램

</div>

<span> </span>

</div>

</div>

</div>

