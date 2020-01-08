---
title: Lync Server 2013 프런트 엔드 풀에 SBA(Survivable Branch Appliance) 연결
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool
ms:assetid: 3c7ca33f-5295-4d82-9152-41d8bc6f35cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688026(v=OCS.15)
ms:contentKeyID: 49733616
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77d22a71272ae7dd3c426b0439f7a3765ca6848c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981643"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a><span data-ttu-id="c9daa-102">Lync Server 2013 프런트 엔드 풀에 SBA(Survivable Branch Appliance) 연결</span><span class="sxs-lookup"><span data-stu-id="c9daa-102">Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9daa-103">_**마지막으로 수정한 주제:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="c9daa-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="c9daa-104">모든 Survivable Branch 기기 (SBA)는 SBA에 대 한 백업 등록 기관 역할을 하는 프런트 엔드 풀과 연결 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9daa-104">Every Survivable Branch Appliance (SBA) is associated with a Front End pool, which serves as a backup Registrar for the SBA.</span></span> <span data-ttu-id="c9daa-105">프런트 엔드 풀을 Lync Server 2013으로 업그레이드 한 경우 프런트 엔드 풀을 업그레이드 하는 동안에는 SBA를 프런트 엔드 풀에서 분리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9daa-105">When the Front End pool is upgraded to Lync Server 2013, the SBA must be disassociated from the Front End pool while the Front End pool is upgraded.</span></span> <span data-ttu-id="c9daa-106">프런트 엔드 풀을 업그레이드 한 후에는 프런트 엔드 풀을 사용 하 여 reassociated 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9daa-106">After the Front End pool is upgraded, the SBA can be reassociated with the Front End pool.</span></span> <span data-ttu-id="c9daa-107">여기에는 토폴로지 작성기의 토폴로지에서 SBA를 삭제 한 다음 토폴로지 작성기에 SBA를 다시 추가 하는 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9daa-107">This involves deleting the SBA from the topology in Topology Builder and then adding the SBA, again, to Topology Builder.</span></span> <span data-ttu-id="c9daa-108">SBA의 사용자를 다른 프런트 엔드 풀로 이동한 후에는 토폴로지에서 SBA를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9daa-108">Users homed on the SBA must be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="c9daa-109">SBA가 토폴로지에 다시 추가 된 후 해당 사용자는 다시 SBA로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9daa-109">After the SBA is added back to the topology, those users can be moved back to the SBA.</span></span>

<span data-ttu-id="c9daa-110">이러한 단계는 다음과 같이 요약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9daa-110">These steps are summarized below:</span></span>

1.  <span data-ttu-id="c9daa-111">SBA에 속한 분기 사용자를 다른 프런트 엔드 풀로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9daa-111">Move branch users homed on SBA to another Front End pool.</span></span>

2.  <span data-ttu-id="c9daa-112">토폴로지에서 기존 프런트 엔드 풀을 제거 하 여 백업 등록 기관으로 분리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9daa-112">Remove SBA from your topology to disassociate the existing Front End pool as the backup Registrar.</span></span>

3.  <span data-ttu-id="c9daa-113">프런트 엔드 풀을 Microsoft Lync Server 2013로 업그레이드 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9daa-113">Upgrade Front End pool to Microsoft Lync Server 2013.</span></span>

4.  <span data-ttu-id="c9daa-114">토폴로지에 다시 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9daa-114">Add SBA back into your topology.</span></span>

5.  <span data-ttu-id="c9daa-115">새 프런트 엔드 풀을 백업 등록 기관으로 SBA에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9daa-115">Associate the new Front End pool to the SBA as a backup Registrar.</span></span>

6.  <span data-ttu-id="c9daa-116">분기 사용자를 다시 SBA로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9daa-116">Move branch users back to the SBA.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c9daa-117">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="c9daa-117">In This Section</span></span>

  - [<span data-ttu-id="c9daa-118">토폴로지에 Lync Server 2013 SBA(Survivable Branch Appliance) 분기 사이트 추가</span><span class="sxs-lookup"><span data-stu-id="c9daa-118">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [<span data-ttu-id="c9daa-119">토폴로지에 Lync Server 2010 SBA(Survivable Branch Appliance) 분기 사이트 추가</span><span class="sxs-lookup"><span data-stu-id="c9daa-119">Add Lync Server 2010 Survivable Branch Appliance branch site to your topology</span></span>](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

