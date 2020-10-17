---
title: 'Lync Server 2013: 구성 고급 9-1-1'
description: 'Lync Server 2013: 고급 9-1-1을 구성 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Enhanced 9-1-1
ms:assetid: 5967de00-c8b9-4923-86da-6ad3369a4cad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398390(v=OCS.15)
ms:contentKeyID: 48184205
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc7a2a9ed10e7f29f53a4dfff6dff926ded18d38
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553334"
---
# <a name="configure-enhanced-9-1-1-in-lync-server-2013"></a>Lync Server 2013에서 향상 된 9-1-1 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-24_

E9-1-1(고급 9-1-1)은 발신자의 전화 번호와 주소 또는 번지를 연결하는 응급 알림 기능입니다. 이 정보를 사용하여 PSAP(Public Safety Answering Point)는 긴급 상황에 처한 발신자에게 즉시 긴급 서비스를 보낼 수 있습니다.

E9-1-1을 지원 하려면 Lync Server 2013에서 위치를 클라이언트에 올바르게 연결 하 고이 정보를 사용 하 여 가장 가까운 PSAP로 긴급 통화를 라우팅하는 데 사용할 수 있어야 합니다.

E9-1-1 배포를 계획 하는 방법에 대 한 자세한 내용은 [Lync Server 2013의 응급 서비스 계획 (E9-1)](lync-server-2013-planning-for-emergency-services-e9-1-1.md)을 참조 하십시오.

<div>


> [!IMPORTANT]  
> Lync Server 2013는 미국 내에서 E9-1-1만 지원 합니다. E9-1-1을 배포하려면 적격한 E9-1-1 서비스 공급자에 대한 SIP 연결을 구성하거나 PSTN(공중 전화망) 기반 E9-1-1 서비스 공급자에 ELIN(emergency location identification number) 게이트웨이를 배포해야 합니다. 자세한 내용은 향상 된 <A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">9-1-1 (E9-1-1) 및 Lync server 2013의 중재 서버</A>를 참조 하십시오. 트렁크 연결을 구성 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">Configure a 트렁크 with media bypass In Lync Server 2013</A>을 참조 하십시오.



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 E9-1-1 음성 경로 구성](lync-server-2013-configure-an-e9-1-1-voice-route.md)

  - [Lync Server 2013의 위치 정책 만들기](lync-server-2013-create-location-policies.md)

  - [Lync Server 2013에서 E9-1-1에 대 한 사이트 정보 구성](lync-server-2013-configure-site-information-for-e9-1-1.md)

  - [Lync Server 2013에서 위치 데이터베이스 구성](lync-server-2013-configure-the-location-database.md)

  - [Lync Server 2013에서 고급 E9-1-1 기능 구성](lync-server-2013-configure-advanced-e9-1-1-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

