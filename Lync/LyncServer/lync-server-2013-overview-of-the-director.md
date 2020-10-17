---
title: 'Lync Server 2013: 디렉터 개요'
description: 'Lync Server 2013: 디렉터 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Director
ms:assetid: cf9919b3-e16b-47c5-be1d-2c4bc64f44ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398879(v=OCS.15)
ms:contentKeyID: 48185393
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6686534e22bab5b02a2663789298e4cf7ea582c2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567634"
---
# <a name="overview-of-the-director-in-lync-server-2013"></a><span data-ttu-id="84ac4-103">Lync Server 2013의 디렉터 개요</span><span class="sxs-lookup"><span data-stu-id="84ac4-103">Overview of the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84ac4-104">_**마지막으로 수정 된 항목:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="84ac4-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="84ac4-105">디렉터는 사용자 요청을 인증 하지만 사용자 계정을 사용 하지 않는 Lync Server 2013을 실행 하는 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="84ac4-105">A Director is a server running Lync Server 2013 that authenticates user requests, but does not home any user accounts.</span></span> <span data-ttu-id="84ac4-106">선택적으로 디렉터를 배포할 수 있는 두 가지 시나리오는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="84ac4-106">You optionally can deploy a Director in the following two scenarios:</span></span>

  - <span data-ttu-id="84ac4-107">에 지 서버를 배포 하 여 외부 사용자가 액세스할 수 있도록 설정 하는 경우에는 디렉터도 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ac4-107">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="84ac4-108">이 시나리오에서는 디렉터가 외부 사용자를 인증 한 다음 트래픽을 내부 서버에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ac4-108">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="84ac4-109">디렉터를 사용 하 여 외부 사용자를 인증 하는 경우 프런트 엔드 풀 서버는 이러한 사용자의 인증을 수행 하는 오버 헤드에서 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84ac4-109">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="84ac4-110">또한 서비스 거부 공격과 같은 악의적인 트래픽에 대 한 내부 프런트 엔드 풀을 방지 하는 데에도 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84ac4-110">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="84ac4-111">이러한 공격에 잘못 된 외부 트래픽이 발생 하는 네트워크의 경우에는 디렉터에서이 트래픽을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ac4-111">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>

  - <span data-ttu-id="84ac4-112">중앙 사이트에 여러 프런트 엔드 풀을 배포 하는 경우 해당 사이트에 디렉터를 추가 하면 인증 요청을 합리화 하 고 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84ac4-112">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="84ac4-113">이 시나리오에서는 모든 요청이 먼저 디렉터로 이동한 다음 올바른 프런트 엔드 풀로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="84ac4-113">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

