---
title: 'Lync Server 2013: 고급 9-1-1 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Enhanced 9-1-1
ms:assetid: 5967de00-c8b9-4923-86da-6ad3369a4cad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398390(v=OCS.15)
ms:contentKeyID: 48184205
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0ef94e3de028f66684972fa6a3c95d4e63c35b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981292"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-enhanced-9-1-1-in-lync-server-2013"></a><span data-ttu-id="cdc2c-102">Lync Server 2013에서 고급 9-1-1 구성</span><span class="sxs-lookup"><span data-stu-id="cdc2c-102">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cdc2c-103">_**마지막으로 수정한 주제:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="cdc2c-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="cdc2c-104">확장 9-1-1 (E9-1-1)은 전화 상대의 전화 번호를 도심 또는 주소와 연결 하는 긴급 알림 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="cdc2c-104">Enhanced 9-1-1 (E9-1-1) is an emergency notification feature that associates the calling party’s telephone number with a civic or a street address.</span></span> <span data-ttu-id="cdc2c-105">이 정보를 사용 하 여 공용 안전 응답 지 (PSAP)에서 이용해의 호출자에 게 즉시 비상 서비스를 발송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdc2c-105">Using this information, the Public Safety Answering Point (PSAP) can immediately dispatch emergency services to the caller in distress.</span></span>

<span data-ttu-id="cdc2c-106">E9-1-1을 지원 하려면 Lync Server 2013에서 위치를 클라이언트에 올바르게 연결 하 고이 정보를 사용 하 여 가까운 PSAP로 긴급 통화를 라우팅하는 것을 확인할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdc2c-106">To support E9-1-1, Lync Server 2013 must be able to correctly associate a location with a client and to make sure that this information is used to route the emergency call to the nearest PSAP.</span></span>

<span data-ttu-id="cdc2c-107">E9-1 배포 계획에 대 한 자세한 내용은 [Lync Server 2013에서 응급 서비스 계획 (E9-1)](lync-server-2013-planning-for-emergency-services-e9-1-1.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cdc2c-107">For details about planning for an E9-1-1 deployment, see [Planning for emergency services (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cdc2c-108">Lync Server 2013는 미국 내에서 E9-1-1만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdc2c-108">Lync Server 2013 only supports E9-1-1 within the United States.</span></span> <span data-ttu-id="cdc2c-109">E9를 배포 하려면 E9-1-1 서비스 공급자에 대 한 SIP 연결을 구성 하거나, 긴급 한 위치 id 번호 (ELIN) 게이트웨이를 공공 교환 전화 (PSTN) 기반 E9-1-1 서비스 공급자에 게 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdc2c-109">To deploy E9-1-1, you need to configure a SIP connection to a qualified E9-1-1 service provider, or deploy an emergency location identification number (ELIN) gateway to a public switched telephone (PSTN)-based E9-1-1 service provider.</span></span> <span data-ttu-id="cdc2c-110">자세한 내용은 <A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">Lync server 2013의 향상 된 9-1-1 (E9-1) 및 중재 서버</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cdc2c-110">For details, see <A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</A>.</span></span> <span data-ttu-id="cdc2c-111">트렁크 연결을 구성 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">Lync Server 2013에서 미디어 바이패스를 사용 하 여 트렁크 구성을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cdc2c-111">For details about configuring trunk connections, see <A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">Configure a trunk with media bypass in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cdc2c-112">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="cdc2c-112">In This Section</span></span>

  - [<span data-ttu-id="cdc2c-113">Lync Server 2013의 E9-1-1 음성 경로 구성</span><span class="sxs-lookup"><span data-stu-id="cdc2c-113">Configure an E9-1-1 voice route in Lync Server 2013</span></span>](lync-server-2013-configure-an-e9-1-1-voice-route.md)

  - [<span data-ttu-id="cdc2c-114">Lync Server 2013에서 위치 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="cdc2c-114">Create location policies in Lync Server 2013</span></span>](lync-server-2013-create-location-policies.md)

  - [<span data-ttu-id="cdc2c-115">Lync Server 2013에서 E9에 대 한 사이트 정보 구성-1-1</span><span class="sxs-lookup"><span data-stu-id="cdc2c-115">Configure site information for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-site-information-for-e9-1-1.md)

  - [<span data-ttu-id="cdc2c-116">Lync Server 2013에서 위치 데이터베이스 구성</span><span class="sxs-lookup"><span data-stu-id="cdc2c-116">Configure the location database in Lync Server 2013</span></span>](lync-server-2013-configure-the-location-database.md)

  - [<span data-ttu-id="cdc2c-117">Lync Server 2013에서 고급 E9-1-1 기능 구성</span><span class="sxs-lookup"><span data-stu-id="cdc2c-117">Configure advanced E9-1-1 features in Lync Server 2013</span></span>](lync-server-2013-configure-advanced-e9-1-1-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

