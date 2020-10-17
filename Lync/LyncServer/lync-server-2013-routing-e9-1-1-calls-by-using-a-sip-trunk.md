---
title: 'Lync Server 2013: SIP 트렁크를 사용 하 여 E9-1-1 통화 라우팅'
description: 'Lync Server 2013: SIP 트렁크를 사용 하 여 E9-1-1 통화 라우팅'
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
ms.openlocfilehash: 9e45b2b3d33556a5ff97235345c7b538023a7449
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571824"
---
# <a name="routing-e9-1-1-calls-by-using-a-sip-trunk-in-lync-server-2013"></a><span data-ttu-id="dce43-103">Lync Server 2013에서 SIP 트렁크를 사용 하 여 E9-1-1 통화 라우팅</span><span class="sxs-lookup"><span data-stu-id="dce43-103">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dce43-104">_**마지막으로 수정 된 항목:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="dce43-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="dce43-105">SIP 트렁크를 사용하여 적격 E9-1-1 서비스 공급자에 연결하는 것은 E9-1-1을 배포하는 데 사용할 수 있는 한 가지 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="dce43-105">Using a SIP trunk to connect to a qualified E9-1-1 service provider is one way that you can deploy E9-1-1.</span></span> <span data-ttu-id="dce43-106">ELIN 게이트웨이를 사용 하 여 PSTN (공중 전화망) 기반 E9-1-1 서비스 공급자에 연결 하는 방법에 대 한 자세한 내용은 [Routing E9-1-1 통화를 Lync Server 2013에서 ELIN 게이트웨이를 사용 하 여 라우팅을](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dce43-106">For details about using an ELIN gateway to connect to a public switched telephone network (PSTN)-based E9-1-1 service provider, see [Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md).</span></span>

<span data-ttu-id="dce43-107">다음 다이어그램에서는 SIP 트렁크 및 정규화 된 E9-1-1 서비스 공급자를 사용할 때 Lync Server에서 공용 안전 응답 지점 (PSAP)으로 긴급 통화를 라우팅하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dce43-107">The following diagram shows how an emergency call is routed from Lync Server to the Public Safety Answering Point (PSAP) when you use a SIP trunk and qualified E9-1-1 service provider.</span></span>

<span data-ttu-id="dce43-108">**SIP 트렁크를 통한 E9-1-1 통화 라우팅**</span><span class="sxs-lookup"><span data-stu-id="dce43-108">**Routing E9-1-1 calls through a SIP trunk**</span></span>

<span data-ttu-id="dce43-109">![Lync Server에서 PSAP로의 긴급 통화 라우팅](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Lync Server에서 PSAP로의 긴급 통화 라우팅")</span><span class="sxs-lookup"><span data-stu-id="dce43-109">![Emergency Call Routing from Lync Server to PSAP](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Emergency Call Routing from Lync Server to PSAP")</span></span>

<span data-ttu-id="dce43-110">호환 되는 Lync Server 클라이언트에서 긴급 통화를 하면 다음이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="dce43-110">When an emergency call is placed from a compatible Lync Server client:</span></span>

1.  <span data-ttu-id="dce43-111">위치, 발신자의 콜백 번호 및 (선택 사항) 알림 URL 및 회의 콜백 번호를 포함 하는 SIP 초대는 Lync Server로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="dce43-111">A SIP INVITE that contains the location, the caller's callback number, and the (optional) Notification URL and conference callback number is routed to Lync Server.</span></span>

2.  <span data-ttu-id="dce43-112">Lync Server는 긴급 전화 번호와 일치 하 고 해당 통화를 적절 한 위치 정책에 정의 된 **PSTN 사용** 값에 따라 중재 서버에 라우트 하며, E9-1-1 서비스 공급자에 게 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="dce43-112">Lync Server matches the emergency number and routes the call (based on the **PSTN Usage** value that is defined in the applicable location policy) to a Mediation Server, and from there, over a SIP trunk to the E9-1-1 service provider.</span></span>

3.  <span data-ttu-id="dce43-p102">E9-1-1 서비스 공급자는 통화와 함께 제공된 위치에 따라 긴급 통화를 올바른 PSAP로 라우팅합니다. 클라이언트가 긴급 통화와 함께 확인된 ERL(Emergency Response Location)을 포함하는 경우 공급자는 통화를 적절한 PSAP로 자동으로 라우팅합니다. 사용자가 수동으로 위치를 입력한 경우에는 먼저 ECRC(Emergency Call Response Center)에서 발신자와 구두로 위치가 정확한지 확인한 후 긴급 통화를 PSAP로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="dce43-p102">The E9-1-1 service provider routes the emergency call to the correct PSAP based on the location that is provided with the call. When the client includes a validated Emergency Response Location (ERL) with the emergency call, the provider automatically routes the call to the appropriate PSAP. If the location was manually entered by the user, the Emergency Call Response Center (ECRC) first verbally verifies the accuracy of the location with the caller before routing the emergency call to the PSAP.</span></span>

4.  <span data-ttu-id="dce43-116">알림에 대 한 위치 정책을 구성한 경우 조직의 보안 관리자 중 한 명 이상이 특수 Lync 긴급 알림 인스턴트 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="dce43-116">If you configured the location policy for notifications, one or more of your organization’s security officers are sent a special Lync emergency notification instant message.</span></span> <span data-ttu-id="dce43-117">보안 담당자의 화면에 항상 팝업으로 표시되는 이 메시지에는 발신자 이름, 전화 번호, 시간, 및 위치가 포함되므로 보안 담당자가 인스턴트 메시지나 음성을 통해 긴급 발신자에게 빠르게 대응할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dce43-117">This message always pops up on the security officers’ screen(s) and contains the caller’s name, phone number, time, and location, enabling security personnel to quickly respond to the emergency caller by using an instant message or voice.</span></span>

5.  <span data-ttu-id="dce43-118">회의에 대해 위치 정책을 구성한 경우 E9-1-1 서비스 공급자가 해당 정책을 지원하면 내부 보안 데스크가 단방향 오디오 또는 양방향 오디오를 사용하여 전화 회의에 참가하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dce43-118">If you configured the location policy for conferencing and it is supported by the E9-1-1 service provider, an internal Security Desk is conferenced into the call with either one-way audio or two-way audio.</span></span>

6.  <span data-ttu-id="dce43-119">통화가 중간에 끊기면 PSAP가 콜백 번호를 사용하여 발신자와 직접 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="dce43-119">If the call is broken prematurely, the PSAP uses the callback number to contact the caller directly.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

