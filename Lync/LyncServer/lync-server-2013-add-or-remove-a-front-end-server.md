---
title: 'Lync Server 2013: 프런트 엔드 서버 추가 또는 제거'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add or remove a Front End Server
ms:assetid: ab748733-6bad-4c93-8dda-db8d5271653d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205153(v=OCS.15)
ms:contentKeyID: 48185050
ms.date: 01/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1fe1e81d3983b89d4f68111179c3adc7409bee2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a><span data-ttu-id="24350-102">Lync Server 2013에서 프런트 엔드 서버 추가 또는 제거</span><span class="sxs-lookup"><span data-stu-id="24350-102">Add or remove a Front End Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24350-103">_**마지막으로 수정한 주제:** 2016-01-21_</span><span class="sxs-lookup"><span data-stu-id="24350-103">_**Topic Last Modified:** 2016-01-21_</span></span>

<span data-ttu-id="24350-104">풀에 프런트 엔드 서버를 추가 하거나 풀에서 프런트 엔드 서버를 제거 하는 경우에는 풀을 다시 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24350-104">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> <span data-ttu-id="24350-105">사용자에 대 한 서비스 중단을 방지 하려면 프런트 엔드 서버를 추가 하거나 제거할 때 다음 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="24350-105">To prevent any interruption of service to users, use the following procedure when adding or removing a Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="24350-106">풀에 새 서버를 추가 하는 경우 새 풀 서버를 풀의 기존 서버와 동일한 누적 업데이트 수준으로 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="24350-106">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span>



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="24350-107">프런트 엔드 서버를 추가 하거나 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="24350-107">To add or remove Front End servers</span></span>

1.  <span data-ttu-id="24350-108">프런트 엔드 서버를 제거 하는 경우 먼저 해당 서버에 대 한 새 연결을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="24350-108">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="24350-109">이렇게 하려면 다음 cmdlet을 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24350-109">To do so, you can use the following cmdlet:</span></span>
    
        Stop-CsWindowsServices -Graceful

2.  <span data-ttu-id="24350-110">제거할 서버에 현재 세션이 없는 경우에는 Lync Server 서비스를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="24350-110">When the servers being removed have no current sessions, stop Lync Server services on them.</span></span>

3.  <span data-ttu-id="24350-111">토폴로지 작성기를 열고 필요한 서버를 추가 또는 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="24350-111">Open Topology Builder, and add or remove the necessary servers.</span></span>

4.  <span data-ttu-id="24350-112">토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="24350-112">Publish the topology.</span></span>

5.  <span data-ttu-id="24350-113">풀의 프런트 엔드 서버를 2 개 이상으로 유지 하거나, 두 개 이상의 서버에서 정확히 2 개에 이르기까지 다음 cmdlet을 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24350-113">If the pool has gone from having two Front End Servers to more than two, or gone from more than two servers to exactly two, you need to type the following cmdlet:</span></span>
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    <span data-ttu-id="24350-114">풀에 서버가 세 대 이상 있는 경우이 cmdlet을 입력할 때 세 개 이상의 서버가 실행 중 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="24350-114">If the pool has three or more servers, then at least three of those servers must be running when you type this cmdlet.</span></span>

6.  <span data-ttu-id="24350-115">풀의 모든 프런트 엔드 서버를 한 번에 하나씩 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="24350-115">Restart all Front End Servers in the pool, one at a time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

