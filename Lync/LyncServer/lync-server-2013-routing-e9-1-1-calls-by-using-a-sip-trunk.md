---
title: 'Lync Server 2013: SIP 트렁크를 사용하여 E9-1-1 통화 라우팅'
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
ms.openlocfilehash: 918aaf97b1567f012a2b41de7128db23aa383acb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732858"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-a-sip-trunk-in-lync-server-2013"></a><span data-ttu-id="08959-102">Lync Server 2013에서 SIP 트렁크를 사용하여 E9-1-1 통화 라우팅</span><span class="sxs-lookup"><span data-stu-id="08959-102">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08959-103">_**마지막으로 수정한 주제:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="08959-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="08959-104">SIP 트렁크를 사용 하 여 적격 E9-1 서비스 공급자에 연결 하는 방법은 E9-1-1을 배포할 수 있는 한 가지 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="08959-104">Using a SIP trunk to connect to a qualified E9-1-1 service provider is one way that you can deploy E9-1-1.</span></span> <span data-ttu-id="08959-105">게이트웨이에서 elin를 사용 하 여 공공 교환 전화 네트워크 (PSTN) 기반 E9 서비스 공급자에 연결 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 elin gateway를 사용 하 여 E9-1-1 통화 라우팅](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="08959-105">For details about using an ELIN gateway to connect to a public switched telephone network (PSTN)-based E9-1-1 service provider, see [Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md).</span></span>

<span data-ttu-id="08959-106">다음 다이어그램에서는 SIP 트렁크 및 유자격 E9-1 서비스 공급자를 사용 하는 경우 Lync Server에서 공용 안전 응답 시점 (PSAP)으로 긴급 통화를 라우팅하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="08959-106">The following diagram shows how an emergency call is routed from Lync Server to the Public Safety Answering Point (PSAP) when you use a SIP trunk and qualified E9-1-1 service provider.</span></span>

<span data-ttu-id="08959-107">**라우팅 E9-SIP 트렁크를 통해 1 ~ 1 통화**</span><span class="sxs-lookup"><span data-stu-id="08959-107">**Routing E9-1-1 calls through a SIP trunk**</span></span>

<span data-ttu-id="08959-108">![Lync Server에서 PSAP로의 긴급 통화 라우팅](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Lync Server에서 PSAP로의 긴급 통화 라우팅")</span><span class="sxs-lookup"><span data-stu-id="08959-108">![Emergency Call Routing from Lync Server to PSAP](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Emergency Call Routing from Lync Server to PSAP")</span></span>

<span data-ttu-id="08959-109">호환 가능한 Lync 서버 클라이언트에서 긴급 통화를 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="08959-109">When an emergency call is placed from a compatible Lync Server client:</span></span>

1.  <span data-ttu-id="08959-110">위치, 발신자의 콜백 번호 및 (선택 사항) 알림 URL과 회의 콜백 번호를 포함 하는 SIP 초대가 Lync 서버로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="08959-110">A SIP INVITE that contains the location, the caller's callback number, and the (optional) Notification URL and conference callback number is routed to Lync Server.</span></span>

2.  <span data-ttu-id="08959-111">Lync Server는 비상 번호와 일치 하 고 해당 위치 정책에 정의 된 **PSTN 사용** 값에 기반 하 여 통화를 중재 서버에 연결 하 고, E9-1-1 서비스 공급자에 대 한 SIP 트렁크를 통해이에 대 한 통신을 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="08959-111">Lync Server matches the emergency number and routes the call (based on the **PSTN Usage** value that is defined in the applicable location policy) to a Mediation Server, and from there, over a SIP trunk to the E9-1-1 service provider.</span></span>

3.  <span data-ttu-id="08959-112">E9 서비스 공급자는 통화와 함께 제공 된 위치에 따라 비상 전화를 올바른 PSAP로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="08959-112">The E9-1-1 service provider routes the emergency call to the correct PSAP based on the location that is provided with the call.</span></span> <span data-ttu-id="08959-113">클라이언트에 비상 전화를 사용 하 여 확인 된 긴급 응답 위치 (ERL)가 포함 되어 있으면 공급자가 자동으로 해당 PSAP로 전화를 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="08959-113">When the client includes a validated Emergency Response Location (ERL) with the emergency call, the provider automatically routes the call to the appropriate PSAP.</span></span> <span data-ttu-id="08959-114">사용자가 위치를 수동으로 입력 한 경우 비상 통화 응답 센터 (ECRC)에서 첫 구두로는 응급 호출을 PSAP로 라우팅하기 전에 호출자와의 정확성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="08959-114">If the location was manually entered by the user, the Emergency Call Response Center (ECRC) first verbally verifies the accuracy of the location with the caller before routing the emergency call to the PSAP.</span></span>

4.  <span data-ttu-id="08959-115">알림에 대 한 위치 정책을 구성한 경우 조직의 보안 책임자 중 한 명에 게 특별 Lync 긴급 알림 인스턴트 메시지가 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08959-115">If you configured the location policy for notifications, one or more of your organization’s security officers are sent a special Lync emergency notification instant message.</span></span> <span data-ttu-id="08959-116">이 메시지는 항상 보안 관리자의 화면에 표시 되며, 발신자의 이름, 전화 번호, 시간 및 위치를 포함 하 여 보안 담당자가 인스턴트 메시지 또는 음성을 사용 하 여 긴급 호출자에 게 신속 하 게 응답할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="08959-116">This message always pops up on the security officers’ screen(s) and contains the caller’s name, phone number, time, and location, enabling security personnel to quickly respond to the emergency caller by using an instant message or voice.</span></span>

5.  <span data-ttu-id="08959-117">회의에 대 한 위치 정책을 구성 하 고 E9 서비스 공급자에서 지원 되는 경우 내부 보안 데스크는 단방향 오디오 또는 양방향 오디오를 사용 하 여 통화에 conferenced 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08959-117">If you configured the location policy for conferencing and it is supported by the E9-1-1 service provider, an internal Security Desk is conferenced into the call with either one-way audio or two-way audio.</span></span>

6.  <span data-ttu-id="08959-118">통화가 중간에 끊어지면 PSAP는 콜백 번호를 사용 하 여 직접 호출자에 게 연락을 합니다.</span><span class="sxs-lookup"><span data-stu-id="08959-118">If the call is broken prematurely, the PSAP uses the callback number to contact the caller directly.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

