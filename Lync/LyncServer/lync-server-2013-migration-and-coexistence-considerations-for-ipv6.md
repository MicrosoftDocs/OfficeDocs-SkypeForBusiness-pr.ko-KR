---
title: 'Lync Server 2013: IPv6의 마이그레이션 및 동시 사용 고려 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration and coexistence considerations for IPv6
ms:assetid: 8c769c4f-c8a9-4cbf-9080-beee3be9848a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205068(v=OCS.15)
ms:contentKeyID: 48184751
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bbf7e062a7a96f6f7aca642298471b0a8cf8adaa
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185105"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-and-coexistence-considerations-for-ipv6-in-lync-server-2013"></a><span data-ttu-id="2ed7d-102">Lync Server 2013의 i p v 6에 대 한 마이그레이션 및 동시 사용 고려 사항</span><span class="sxs-lookup"><span data-stu-id="2ed7d-102">Migration and coexistence considerations for IPv6 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ed7d-103">_**마지막으로 수정 된 항목:** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="2ed7d-103">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="2ed7d-104">Lync Server 2010 또는 Office Communications Server에서는 IPv6 (IP 버전 6)이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ed7d-104">IP version 6 (IPv6) is not supported on Lync Server 2010 or Office Communications Server.</span></span> <span data-ttu-id="2ed7d-105">파일럿을 위해 Lync Server 2010과 Lync Server 2013 이중 스택 공존 성을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ed7d-105">For piloting purposes, you can test Lync Server 2010 and Lync Server 2013 dual-stack coexistence.</span></span> <span data-ttu-id="2ed7d-106">모든 풀에 대해 IPv6 (이중 스택 네트워크)을 사용 하도록 설정 하기 전에 지정 된 중앙 사이트에 대 한 모든 풀을 Lync Server 2013로 업그레이드 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2ed7d-106">We recommend that all pools for a given central site are upgraded to Lync Server 2013 before you enable IPv6 (dual-stack network) for any of the pools.</span></span> <span data-ttu-id="2ed7d-107">IPv6 전용의 풀을 구성해야 할 경우에는 랩 환경에서 테스트 목적으로 IPv6 전용 풀을 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2ed7d-107">If you need to configure a pool for IPv6 only, we recommend that you set up an IPv6-only pool in your lab environment for testing.</span></span>

<span data-ttu-id="2ed7d-108">마이그레이션 및 동시 사용 중에는 다음과 같은 시나리오가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ed7d-108">The following scenarios are supported during migration and coexistence:</span></span>

  - <span data-ttu-id="2ed7d-109">IPv4 모드에서 lync Server 2013, Lync Server 2010 및 Office Communications Server 2007 R2 풀은 이중 스택 모드에서 Lync Server 2013과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ed7d-109">Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2 pools in IPv4 mode, coexisting with Lync Server 2013 in dual-stack mode.</span></span>

  - <span data-ttu-id="2ed7d-110">IPv6 전용 풀을 격리 경우에는 IPv6 전용 모드의 Lync Server 2013 풀</span><span class="sxs-lookup"><span data-stu-id="2ed7d-110">Lync Server 2013 pool in IPv6-only mode, if the IPv6-only pool is siloed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

