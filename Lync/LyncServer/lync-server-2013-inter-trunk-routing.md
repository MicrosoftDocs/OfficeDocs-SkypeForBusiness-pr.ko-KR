---
title: 'Lync Server 2013: 트렁크 간 라우팅'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Inter-trunk routing
ms:assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721940(v=OCS.15)
ms:contentKeyID: 49733877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b73e4b7588c7f267a5fe4abc2db48661755dea03
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="inter-trunk-routing-in-lync-server-2013"></a>Lync Server 2013의 트렁크 간 라우팅

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-08_

Lync Server 2013에서는 인터 트렁크 라우팅 지원을 통해 기본 세션 관리 기능을 제공 합니다. 이 새로운 기능을 사용 하면 Lync Server에서 다운스트림 전화 통신 시스템에 통화 제어 기능을 제공할 수 있습니다. 트렁크 간 라우팅은 IP-PBX를 PSTN(공중 전화망) 게이트웨이에 상호 연결할 수 있으므로 PBX(Private Branch eXchange) 전화의 통화를 PSTN으로 라우팅하고 들어오는 PSTN 통화를 PBX 전화로 라우팅할 수 있습니다. 마찬가지로 Lync Server는 두 개 이상의 IP PBX 시스템을 상호 연결 하 여 서로 다른 IP PBX 시스템에서 PBX 전화 간에 통화를 주고 받을 수 있도록 합니다.

다음 그림에서는 PSTN 게이트웨이와 ip-pbx 간의 ip-pbx을 제공 하는 Lync Server 2013를 보여 줍니다.

![Lync Server 연결 PSTN 게이트웨이/i p-PBX 다이어그램](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server 연결 PSTN 게이트웨이/i p-PBX 다이어그램")

다음 그림에서는 두 개의 IP PBX 시스템을 연결 하는 Lync Server 2013를 보여 줍니다.

![Lync Server 상호 연결 IP-PAX systems 다이어그램](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server 상호 연결 IP-PAX systems 다이어그램")

</div>

<span> </span>

</div>

</div>

</div>

