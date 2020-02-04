---
title: 'Lync Server 2013: 새 Enterprise Voice 기능'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Enterprise Voice features
ms:assetid: db0ad7b9-e469-4c29-89d9-52fed018ef08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398964(v=OCS.15)
ms:contentKeyID: 48185591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92c1c264b9ffa5459962b2b6e915ea0fef2cf775
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757512"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-enterprise-voice-features-in-lync-server-2013"></a><span data-ttu-id="f2cd7-102">Lync Server 2013의 새 Enterprise Voice 기능</span><span class="sxs-lookup"><span data-stu-id="f2cd7-102">New Enterprise Voice features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2cd7-103">_**마지막으로 수정한 주제:** 2013-05-01_</span><span class="sxs-lookup"><span data-stu-id="f2cd7-103">_**Topic Last Modified:** 2013-05-01_</span></span>

<span data-ttu-id="f2cd7-104">Lync Server 2013는 엔터프라이즈 음성을 개선 하는 몇 가지 새로운 라우팅 및 통화 관리 기능을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cd7-104">Lync Server 2013 introduces several new routing and call management features that enhance Enterprise Voice.</span></span>

<span data-ttu-id="f2cd7-105">Lync Server 2013는 중재 서버와 게이트웨이 간에 여러 trunks를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cd7-105">Lync Server 2013 supports multiple trunks between Mediation Servers and gateways.</span></span> <span data-ttu-id="f2cd7-106">*트렁크* 는 포트 번호와 포트 번호와 게이트웨이가 있는 중재 서버 간의 논리적 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="f2cd7-106">A *trunk* is a logical association between a port number and Mediation Server with a port number and gateway.</span></span> <span data-ttu-id="f2cd7-107">즉, 중재 서버는 서로 다른 게이트웨이에 여러 trunks 있을 수 있으며 게이트웨이는 서로 다른 중재 서버에 여러 trunks를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2cd7-107">This means that a Mediation Server can have multiple trunks to different gateways, and a gateway can have multiple trunks to different Mediation Servers.</span></span> <span data-ttu-id="f2cd7-108">라우팅 경로를 사용 하면 Lync Server 2013에서 IP-PBX를 PSTN (공개 전환 통신 네트워크) 게이트웨이에 상호 연결 하거나 여러 개의 IP PBX 시스템을 상호 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2cd7-108">Intertrunk routing makes it possible for Lync Server 2013 to interconnect an IP-PBX to a public switched telephone network (PSTN) gateway or to interconnect multiple IP-PBX systems.</span></span> <span data-ttu-id="f2cd7-109">Lync Server 2013는 서로 다른 전화 통신 시스템 간에 붙이기 (즉, 상호 연결) 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cd7-109">Lync Server 2013 serves as the glue (that is, the interconnection) between different telephony systems.</span></span>

<span data-ttu-id="f2cd7-110">Microsoft Lync Server 2013는 착신 전환, 동시 연결, 음성 메일 처리, 발신자 ID 프레젠테이션 등의 영역을 개선 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2cd7-110">Microsoft Lync Server 2013 makes improvements in the areas of call forwarding, simultaneous ringing, voice mail handling, and caller ID presentation.</span></span> <span data-ttu-id="f2cd7-111">이러한 기능은 엔터프라이즈 음성 통화 환경을 보강 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2cd7-111">These features enrich the Enterprise Voice call experience.</span></span>

<span data-ttu-id="f2cd7-112">Lync Server 2013에는 다음과 같은 Enterprise Voice의 새로운 향상 기능이 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f2cd7-112">Lync Server 2013 introduces the following new enhancements to Enterprise Voice:</span></span>

  - [<span data-ttu-id="f2cd7-113">Lync Server 2013의 새로운 통화 기능</span><span class="sxs-lookup"><span data-stu-id="f2cd7-113">New call features in Lync Server 2013</span></span>](lync-server-2013-new-call-features.md)

  - [<span data-ttu-id="f2cd7-114">Lync Server 2013의 새 발신자 번호 기능</span><span class="sxs-lookup"><span data-stu-id="f2cd7-114">New caller ID feature in Lync Server 2013</span></span>](lync-server-2013-new-caller-id-feature.md)

  - [<span data-ttu-id="f2cd7-115">Lync Server 2013의 새로운 음성 메일 기능</span><span class="sxs-lookup"><span data-stu-id="f2cd7-115">New voice mail feature in Lync Server 2013</span></span>](lync-server-2013-new-voice-mail-feature.md)

  - [<span data-ttu-id="f2cd7-116">Lync Server 2013의 새로운 트렁크 기능</span><span class="sxs-lookup"><span data-stu-id="f2cd7-116">New trunk feature in Lync Server 2013</span></span>](lync-server-2013-new-trunk-feature.md)

  - [<span data-ttu-id="f2cd7-117">Lync Server 2013의 새로운 인터트렁크 기능</span><span class="sxs-lookup"><span data-stu-id="f2cd7-117">New intertrunk feature in Lync Server 2013</span></span>](lync-server-2013-new-intertrunk-feature.md)

  - [<span data-ttu-id="f2cd7-118">Lync Server 2013의 새 통화 관리 기능</span><span class="sxs-lookup"><span data-stu-id="f2cd7-118">New call management features in Lync Server 2013</span></span>](lync-server-2013-new-call-management-features.md)

</div>

<span> </span>

</div>

</div>

</div>

