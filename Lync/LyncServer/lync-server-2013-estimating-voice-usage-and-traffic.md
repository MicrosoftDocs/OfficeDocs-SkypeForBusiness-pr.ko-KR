---
title: 'Lync Server 2013: 음성 사용량 및 트래픽 예상'
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
ms.openlocfilehash: 06093893c5de9a08322e1577fbbbe6779d4209cc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735248"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="estimating-voice-usage-and-traffic-for-lync-server-2013"></a><span data-ttu-id="b8814-102">Lync Server 2013의 음성 사용량 및 트래픽 예상</span><span class="sxs-lookup"><span data-stu-id="b8814-102">Estimating voice usage and traffic for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b8814-103">_**마지막으로 수정한 주제:** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="b8814-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="b8814-104">Microsoft Lync Server 2013, 계획 도구는 다음 메트릭을 사용 하 여 각 사이트의 사용자 트래픽과 해당 트래픽을 지 원하는 데 필요한 포트 수를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8814-104">The Microsoft Lync Server 2013, Planning Tool uses the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>

  - <span></span>  
    <span data-ttu-id="b8814-105">**가벼운 트래픽** (사용자 당 한 시간에 한 PSTN 통화), 그림 15 포트 당 사용자.</span><span class="sxs-lookup"><span data-stu-id="b8814-105">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>

  - <span></span>  
    <span data-ttu-id="b8814-106">**중간 규모의 소통량** (사용자 당 2 시간 당 PSTN 통화), 그림 10 사용자/포트</span><span class="sxs-lookup"><span data-stu-id="b8814-106">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>

  - <span></span>  
    <span data-ttu-id="b8814-107">**사용량이 많은 트래픽** (3 개 이상의 PSTN 사용자 통화/시간)은 포트 당 5 명의 사용자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b8814-107">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>

<span data-ttu-id="b8814-108">그런 다음 포트의 수에 따라 필요한 중재 서버 및 게이트웨이 수가 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8814-108">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="b8814-109">대부분의 조직이 2 개 포트에서 960 포트로의 크기를 배포 하는 것으로 간주 하는 PSTN (공개 전화망 네트워크) 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="b8814-109">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="b8814-110">(더 많은 게이트웨이가 있지만 이러한 게이트웨이는 주로 전화 통신 서비스 공급자가 사용 합니다.)</span><span class="sxs-lookup"><span data-stu-id="b8814-110">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>

<span data-ttu-id="b8814-111">예를 들어 1만 사용자 및 중간 트래픽을 포함 하는 조직에는 1000 포트가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8814-111">For example, an organization with 10,000 users and medium traffic would require 1000 ports.</span></span> <span data-ttu-id="b8814-112">필요한 게이트웨이 수는 게이트웨이의 총 용량에 따라 결정 되는 데 필요한 총 포트 수와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b8814-112">The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

