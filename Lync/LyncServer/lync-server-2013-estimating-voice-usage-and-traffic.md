---
title: 'Lync Server 2013: 음성 사용량 및 트래픽 예상'
description: 'Lync Server 2013: 음성 사용 및 트래픽을 예측 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Estimating voice usage and traffic
ms:assetid: 621b08fb-f894-4d91-ac38-e443401b098b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398439(v=OCS.15)
ms:contentKeyID: 48184332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fc288e6da65e8e6f221a05c6c82f0588414c8af
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555014"
---
# <a name="estimating-voice-usage-and-traffic-for-lync-server-2013"></a><span data-ttu-id="77620-103">Lync Server 2013의 음성 사용량 및 트래픽 예상</span><span class="sxs-lookup"><span data-stu-id="77620-103">Estimating voice usage and traffic for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77620-104">_**마지막으로 수정 된 항목:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="77620-104">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="77620-105">Microsoft Lync Server 2013, 계획 도구에서는 다음 메트릭을 사용 하 여 각 사이트의 사용자 트래픽과 해당 트래픽을 지 원하는 데 필요한 포트 수를 예측 합니다.</span><span class="sxs-lookup"><span data-stu-id="77620-105">The Microsoft Lync Server 2013, Planning Tool uses the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>

  - <span></span>  
    <span data-ttu-id="77620-106">**경량 트래픽**(매시간 사용자당 PSTN 호출 하나)의 경우 포트당 사용자 15명</span><span class="sxs-lookup"><span data-stu-id="77620-106">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>

  - <span></span>  
    <span data-ttu-id="77620-107">**중간 정도의 트래픽**(매시간 사용자당 PSTN 호출 두 개)의 경우 포트당 사용자 10명</span><span class="sxs-lookup"><span data-stu-id="77620-107">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>

  - <span></span>  
    <span data-ttu-id="77620-108">**높은 트래픽**(매시간 사용자당 PSTN 호출 세 개 이상)의 경우 포트당 사용자 5명</span><span class="sxs-lookup"><span data-stu-id="77620-108">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>

<span data-ttu-id="77620-109">그런 다음 포트 수에 따라 필요한 중재 서버 및 게이트웨이 수가 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77620-109">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="77620-110">대부분의 조직에서 배포를 고려하는 PSTN(공중 전화망) 게이트웨이의 크기는 포트 2개에서 포트 960개까지 다양합니다.</span><span class="sxs-lookup"><span data-stu-id="77620-110">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="77620-111">훨씬 더 큰 게이트웨이도 있지만 이러한 게이트웨이는 주로 전화 서비스 공급자가 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="77620-111">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>

<span data-ttu-id="77620-p102">예를 들어 사용자 수가 1만 명이고 트래픽은 중간 정도인 조직의 경우 1,000개의 포트가 필요합니다. 필요한 게이트웨이 수는 총 게이트웨이 용량에 따라 결정되는 필요한 총 포트 수와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="77620-p102">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

