---
title: 'Lync Server 2013: SIP 트렁크를 사용하여 E9-1-1 통화 라우팅'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Routing E9-1-1 calls by using a SIP trunk
ms:assetid: 157753c3-fe74-4e2c-81da-ee06911d4cc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204701(v=OCS.15)
ms:contentKeyID: 48183492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c537b66883ab786bc28e3cc808874c0fcb79b92d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-a-sip-trunk-in-lync-server-2013"></a>Lync Server 2013에서 SIP 트렁크를 사용하여 E9-1-1 통화 라우팅

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-29_

SIP 트렁크를 사용 하 여 적격 E9-1 서비스 공급자에 연결 하는 방법은 E9-1-1을 배포할 수 있는 한 가지 방법입니다. 게이트웨이에서 elin를 사용 하 여 공공 교환 전화 네트워크 (PSTN) 기반 E9 서비스 공급자에 연결 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 elin gateway를 사용 하 여 E9-1-1 통화 라우팅](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)을 참조 하세요.

다음 다이어그램에서는 SIP 트렁크 및 유자격 E9-1 서비스 공급자를 사용 하는 경우 Lync Server에서 공용 안전 응답 시점 (PSAP)으로 긴급 통화를 라우팅하는 방법을 보여 줍니다.

**라우팅 E9-SIP 트렁크를 통해 1 ~ 1 통화**

Lync server에서 psap로의 ![비상 통화 라우팅-]서버(images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "에서 psap로의") 비상 통화 라우팅

호환 가능한 Lync 서버 클라이언트에서 긴급 통화를 하는 경우:

1.  위치, 발신자의 콜백 번호 및 (선택 사항) 알림 URL과 회의 콜백 번호를 포함 하는 SIP 초대가 Lync 서버로 라우팅됩니다.

2.  Lync Server는 비상 번호와 일치 하 고 해당 위치 정책에 정의 된 **PSTN 사용** 값에 기반 하 여 통화를 중재 서버에 연결 하 고, E9-1-1 서비스 공급자에 대 한 SIP 트렁크를 통해이에 대 한 통신을 라우팅합니다.

3.  E9 서비스 공급자는 통화와 함께 제공 된 위치에 따라 비상 전화를 올바른 PSAP로 라우팅합니다. 클라이언트에 비상 전화를 사용 하 여 확인 된 긴급 응답 위치 (ERL)가 포함 되어 있으면 공급자가 자동으로 해당 PSAP로 전화를 라우팅합니다. 사용자가 위치를 수동으로 입력 한 경우 비상 통화 응답 센터 (ECRC)에서 첫 구두로는 응급 호출을 PSAP로 라우팅하기 전에 호출자와의 정확성을 확인 합니다.

4.  알림에 대 한 위치 정책을 구성한 경우 조직의 보안 책임자 중 한 명에 게 특별 Lync 긴급 알림 인스턴트 메시지가 전송 됩니다. 이 메시지는 항상 보안 관리자의 화면에 표시 되며, 발신자의 이름, 전화 번호, 시간 및 위치를 포함 하 여 보안 담당자가 인스턴트 메시지 또는 음성을 사용 하 여 긴급 호출자에 게 신속 하 게 응답할 수 있도록 합니다.

5.  회의에 대 한 위치 정책을 구성 하 고 E9 서비스 공급자에서 지원 되는 경우 내부 보안 데스크는 단방향 오디오 또는 양방향 오디오를 사용 하 여 통화에 conferenced 됩니다.

6.  통화가 중간에 끊어지면 PSAP는 콜백 번호를 사용 하 여 직접 호출자에 게 연락을 합니다.

</div>

<span> </span>

</div>

</div>

</div>

