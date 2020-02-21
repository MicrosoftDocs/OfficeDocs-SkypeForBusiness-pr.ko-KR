---
title: 'Lync Server 2013: SIP 트렁크를 사용 하 여 E9-1-1 통화 라우팅'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Routing E9-1-1 calls by using a SIP trunk
ms:assetid: 157753c3-fe74-4e2c-81da-ee06911d4cc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204701(v=OCS.15)
ms:contentKeyID: 48183492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 035279fe9c87b7901092408941538871f1c663fb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-a-sip-trunk-in-lync-server-2013"></a>Lync Server 2013에서 SIP 트렁크를 사용 하 여 E9-1-1 통화 라우팅

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-29_

SIP 트렁크를 사용하여 적격 E9-1-1 서비스 공급자에 연결하는 것은 E9-1-1을 배포하는 데 사용할 수 있는 한 가지 방법입니다. ELIN 게이트웨이를 사용 하 여 PSTN (공중 전화망) 기반 E9-1-1 서비스 공급자에 연결 하는 방법에 대 한 자세한 내용은 [Routing E9-1-1 통화를 Lync Server 2013에서 ELIN 게이트웨이를 사용 하 여 라우팅을](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)참조 하십시오.

다음 다이어그램에서는 SIP 트렁크 및 정규화 된 E9-1-1 서비스 공급자를 사용할 때 Lync Server에서 공용 안전 응답 지점 (PSAP)으로 긴급 통화를 라우팅하는 방법을 보여 줍니다.

**SIP 트렁크를 통한 E9-1-1 통화 라우팅**

![Lync Server에서 PSAP로의 긴급 통화 라우팅](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Lync Server에서 PSAP로의 긴급 통화 라우팅")

호환 되는 Lync Server 클라이언트에서 긴급 통화를 하면 다음이 발생 합니다.

1.  위치, 발신자의 콜백 번호 및 (선택 사항) 알림 URL 및 회의 콜백 번호를 포함 하는 SIP 초대는 Lync Server로 라우팅됩니다.

2.  Lync Server는 긴급 전화 번호와 일치 하 고 해당 통화를 적절 한 위치 정책에 정의 된 **PSTN 사용** 값에 따라 중재 서버에 라우트 하며, E9-1-1 서비스 공급자에 게 전달 합니다.

3.  E9-1-1 서비스 공급자는 통화와 함께 제공된 위치에 따라 긴급 통화를 올바른 PSAP로 라우팅합니다. 클라이언트가 긴급 통화와 함께 확인된 ERL(Emergency Response Location)을 포함하는 경우 공급자는 통화를 적절한 PSAP로 자동으로 라우팅합니다. 사용자가 수동으로 위치를 입력한 경우에는 먼저 ECRC(Emergency Call Response Center)에서 발신자와 구두로 위치가 정확한지 확인한 후 긴급 통화를 PSAP로 라우팅합니다.

4.  알림에 대 한 위치 정책을 구성한 경우 조직의 보안 관리자 중 한 명 이상이 특수 Lync 긴급 알림 인스턴트 메시지를 보냅니다. 보안 담당자의 화면에 항상 팝업으로 표시되는 이 메시지에는 발신자 이름, 전화 번호, 시간, 및 위치가 포함되므로 보안 담당자가 인스턴트 메시지나 음성을 통해 긴급 발신자에게 빠르게 대응할 수 있습니다.

5.  회의에 대해 위치 정책을 구성한 경우 E9-1-1 서비스 공급자가 해당 정책을 지원하면 내부 보안 데스크가 단방향 오디오 또는 양방향 오디오를 사용하여 전화 회의에 참가하게 됩니다.

6.  통화가 중간에 끊기면 PSAP가 콜백 번호를 사용하여 발신자와 직접 연결합니다.

</div>

<span> </span>

</div>

</div>

</div>

