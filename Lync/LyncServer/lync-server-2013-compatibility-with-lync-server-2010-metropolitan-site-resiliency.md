---
title: Lync Server 2010 대도시 사이트 복구와 Lync Server 2013의 호환성
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
ms.openlocfilehash: 395ec568ebafea5c7a06e19340ff5ad10158ffb3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742748"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2010-metropolitan-site-resiliency"></a><span data-ttu-id="4085b-102">Lync Server 2010 대도시 사이트 복구</span><span class="sxs-lookup"><span data-stu-id="4085b-102">Lync Server 2010 metropolitan site resiliency</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4085b-103">_**마지막으로 수정한 주제:** 2014-03-19_</span><span class="sxs-lookup"><span data-stu-id="4085b-103">_**Topic Last Modified:** 2014-03-19_</span></span>

<span data-ttu-id="4085b-104">Lync server 2010에 대해 지원 되는 수도권 사이트 복원 솔루션은 Lync Server 2013에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4085b-104">The metropolitan site resiliency solution supported for Lync Server 2010 is not supported for Lync Server 2013.</span></span> <span data-ttu-id="4085b-105">이 솔루션은 동일한 수도권 영역의 두 데이터 센터에 걸쳐 단일 프런트 엔드 풀을 확장 하는 데 관여 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4085b-105">This solution involved spanning a single Front End pool across two data centers in the same metropolitan area.</span></span>

<span data-ttu-id="4085b-106">수도권 사이트 복원 솔루션은 전체 데이터 센터의 손실 으로부터 복구 하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4085b-106">The metropolitan site resiliency solution was designed to recover from the loss of a full datacenter.</span></span> <span data-ttu-id="4085b-107">두 데이터 센터를 통해 풀을 확장 하는 경우 일반적으로 프런트 엔드의 절반을 두 번째 데이터 센터에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="4085b-107">When you span your pool across two datacenters, you typically put half of your front ends in one datacenter and the other half in the second datacenter.</span></span> <span data-ttu-id="4085b-108">전체 데이터 센터가 손실 되는 경우 프런트 엔드 서버의 절반을 손실 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4085b-108">If you lose an entire datacenter, you have lost half of your Front End Servers.</span></span> <span data-ttu-id="4085b-109">이로 인해 Lync Server 2013의 프런트 엔드 풀에 대 한 새 분산 시스템 모델 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4085b-109">This can cause issues with the new distributed system model for Front End Pools in Lync Server 2013.</span></span> <span data-ttu-id="4085b-110">자세한 내용은 [Lync Server 2013의 프런트 엔드 서버, 인스턴트 메시징 및 현재 상태에 대 한 토폴로지 및 구성 요소](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4085b-110">For more information, see [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

