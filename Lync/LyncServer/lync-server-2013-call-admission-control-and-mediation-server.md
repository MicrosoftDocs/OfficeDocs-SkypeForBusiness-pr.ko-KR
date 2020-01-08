---
title: 'Lync Server 2013: 통화 허용 제어 서비스 및 중재 서버'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call admission control and Mediation Server
ms:assetid: 76faccdc-67d0-4c8b-8e47-1e23c93b02c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398585(v=OCS.15)
ms:contentKeyID: 48184546
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 787e312bcdee289050f2147912e87ef542433db4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-and-mediation-server-in-lync-server-2013"></a>Lync Server 2013의 통화 허용 제어 서비스 및 중재 서버

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-21_

Lync Server 2010에 처음 도입 된 Call 허용 제어 (CAC)는 사용 가능한 대역폭을 기준으로 실시간 세션 설정을 관리 하 여 혼잡 네트워크 사용자를 위해 체감 품질 (환경 품질을 저하 시킬 수 있습니다.) 이 접근 권한 값을 지원 하기 위해 엔터프라이즈 음성 인프라와 게이트웨이 또는 SIP 트렁크 공급자 간에 신호 및 미디어 변환을 제공 하는 중재 서버는 Lync에서 두 가지 상호 작용에 대 한 대역폭 관리를 담당 합니다. 서버 쪽 및 게이트웨이 쪽 호출 허용 제어에서 통화의 종료 엔티티가 대역폭 예약을 처리 합니다. 중재 서버가 게이트웨이에서 상호 작용 하는 게이트웨이 피어 (PSTN 게이트웨이, IP PBX, SBC)는 Lync Server 2013 호출 허용 컨트롤을 지원 하지 않습니다. 따라서 중재 서버는 게이트웨이 피어를 대신 하 여 대역폭 상호 작용을 처리 해야 합니다. 가능할 때마다 중재 서버는 대역폭을 미리 예약 합니다. 이를 수행할 수 없는 경우 (예를 들어 게이트웨이 피어에 대 한 송신 호출에 대해 게이트웨이에 대 한 궁극적인 미디어 끝점의 집약성을 알 수 없는 경우), 통화를 할 때 대역폭이 예약 됩니다. 이 동작은 대역폭의 초과 구독을 발생 시킬 수 있지만, 거짓 링을 방지 하는 유일한 방법입니다.

미디어 바이패스와 대역폭 예약은 동시에 사용할 수 없습니다. 통화에 미디어 바이패스를 사용 하는 경우 해당 통화에 대 한 통화 허용 제어가 수행 되지 않습니다. 여기서는 통화에 제한 된 대역폭을 사용 하는 링크가 없다는 것을 가정 합니다. 호출 허용 제어가 중재 서버와 관련 된 특정 통화에 사용 되는 경우, 해당 통화는 미디어 바이패스를 사용할 수 없습니다.

미디어 바이패스 또는 통화 허용 제어에 대 한 자세한 내용은 [Lync server 2013의 미디어 바이패스](lync-server-2013-planning-for-media-bypass.md) 계획 또는 [lync server 2013의 통화 허용 제어](lync-server-2013-planning-for-call-admission-control.md) 계획 문서를 참조 하세요.

</div>

<span> </span>

</div>

</div>

</div>

