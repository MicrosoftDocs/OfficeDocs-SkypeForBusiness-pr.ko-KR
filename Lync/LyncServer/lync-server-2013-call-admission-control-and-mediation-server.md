---
title: 'Lync Server 2013: 통화 허용 제어 및 중재 서버'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control and Mediation Server
ms:assetid: 76faccdc-67d0-4c8b-8e47-1e23c93b02c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398585(v=OCS.15)
ms:contentKeyID: 48184546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6c0cf06ccf9acde86e3ab344058803218eaf0cf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537265"
---
# <a name="call-admission-control-and-mediation-server-in-lync-server-2013"></a>Lync Server 2013의 통화 허용 제어 및 중재 서버

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-21_

Lync Server 2010에서 처음 도입 된 CAC (통화 허용 제어)는 사용 가능한 대역폭을 기반으로 실시간 세션 설정을 관리 하 여 혼잡 한 네트워크의 사용자에 게 품질이 낮은 QoE (환경 품질)를 방지할 수 있도록 합니다. 이 기능을 지원 하기 위해 엔터프라이즈 음성 인프라와 게이트웨이 또는 SIP 트렁크 공급자 간에 신호 및 미디어 변환을 제공 하는 중재 서버는 Lync Server 쪽 및 게이트웨이 쪽에서 두 가지 상호 작용을 위한 대역폭 관리를 담당 합니다. 통화 허용 제어에서 통화를 종료하는 엔터티는 대역폭 예약을 처리합니다. 중재 서버가 게이트웨이에서 상호 작용 하는 게이트웨이 피어 (PSTN 게이트웨이, IP-PBX, SBC)는 Lync Server 2013 통화 허용 제어를 지원 하지 않습니다. 따라서 중재 서버는 게이트웨이 피어를 대신 하 여 대역폭 상호 작용을 처리 해야 합니다. 가능할 때마다 중재 서버에서 대역폭을 미리 예약 합니다. 이렇게 하는 것이 불가능한 경우(예: 게이트웨이 쪽의 궁극적인 미디어 끝점 로컬러티가 게이트웨이 피어에 대한 발신 통화에 알려져 있지 않은 경우) 전화를 걸 때 대역폭이 예약됩니다. 이 동작은 대역폭의 과다 구독을 초래할 수 있지만 잘못된 연결을 방지할 수 있는 유일한 방법입니다.

미디어 바이패스와 대역폭 예약은 함께 사용할 수 없습니다. 통화에 미디어 바이패스가 사용되는 경우 해당 통화에 대해 통화 허용 제어가 수행되지 않습니다. 여기서는 통화에 관련된 제한된 대역폭에 대한 링크가 없다고 가정합니다. 중재 서버와 관련 된 특정 통화에 대해 통화 허용 제어를 사용 하는 경우 해당 통화는 미디어 바이패스를 사용할 수 없습니다.

미디어 바이패스 또는 통화 허용 제어에 대 한 자세한 내용은 계획 설명서의 lync server [2013](lync-server-2013-planning-for-call-admission-control.md) 에서 [미디어 2013 바이패스에 대 한 계획](lync-server-2013-planning-for-media-bypass.md) 을 참조 하십시오.

</div>

<span> </span>

</div>

</div>

</div>

