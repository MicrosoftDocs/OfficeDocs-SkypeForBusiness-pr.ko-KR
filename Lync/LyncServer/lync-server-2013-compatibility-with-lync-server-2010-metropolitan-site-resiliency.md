---
title: Lync server 2013 2010 호환 대도시 사이트 복구
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2010 metropolitan site resiliency
ms:assetid: 18673ff6-b664-4a57-a89b-cbda8b129e6a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204715(v=OCS.15)
ms:contentKeyID: 48183526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f432941773b72d18c22adc87779341996771399
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2010-metropolitan-site-resiliency"></a><span data-ttu-id="a5619-102">Lync Server 2010 대도시 사이트 복구</span><span class="sxs-lookup"><span data-stu-id="a5619-102">Lync Server 2010 metropolitan site resiliency</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5619-103">_**마지막으로 수정 된 항목:** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="a5619-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="a5619-104">Lync server 2010에 대해 지원 되는 대도시 사이트 복구 솔루션은 lync 서버 2013에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a5619-104">The metropolitan site resiliency solution supported for Lync Server 2010 is not supported for Lync Server 2013.</span></span> <span data-ttu-id="a5619-105">이 솔루션은 같은 도시 지역의 두 데이터 센터에서 단일 프런트 엔드 풀을 제공했습니다.</span><span class="sxs-lookup"><span data-stu-id="a5619-105">This solution involved spanning a single Front End pool across two data centers in the same metropolitan area.</span></span>

<span data-ttu-id="a5619-106">대도시 사이트 복구 솔루션은 전체 데이터 센터가 손실 되는 것을 복구 하기 위해 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5619-106">The metropolitan site resiliency solution was designed to recover from the loss of a full datacenter.</span></span> <span data-ttu-id="a5619-107">두 데이터 센터를 가로질러 풀을 확장 하는 경우에는 일반적으로 프런트 엔드에서 두 번째 데이터 센터에 나머지 반쪽을 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5619-107">When you span your pool across two datacenters, you typically put half of your front ends in one datacenter and the other half in the second datacenter.</span></span> <span data-ttu-id="a5619-108">전체 데이터 센터가 손실 되 면 프런트 엔드 서버의 절반이 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5619-108">If you lose an entire datacenter, you have lost half of your Front End Servers.</span></span> <span data-ttu-id="a5619-109">이로 인해 Lync Server 2013의 프런트 엔드 풀에 대 한 새 분산 시스템 모델에서 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5619-109">This can cause issues with the new distributed system model for Front End Pools in Lync Server 2013.</span></span> <span data-ttu-id="a5619-110">자세한 내용은 [Lync Server 2013의 프런트 엔드 서버, 인스턴트 메시징 및 현재 상태에 대 한 토폴로지 및 구성 요소](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a5619-110">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

