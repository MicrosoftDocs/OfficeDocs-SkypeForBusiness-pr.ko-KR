---
title: 'Lync Server 2013: (선택 사항) 응답 그룹 배포 확인'
description: 'Lync Server 2013: (선택 사항) 응답 그룹 배포를 확인 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify Response Group deployment
ms:assetid: 202ca4ab-8e6d-44a4-b7c8-071133074feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687989(v=OCS.15)
ms:contentKeyID: 49733579
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cfe15026bc1fcfbe10b593987d2717fc0dc8104
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565714"
---
# <a name="optional-verify-response-group-deployment-in-lync-server-2013"></a><span data-ttu-id="83962-103">반드시 Lync Server 2013에서 응답 그룹 배포 확인</span><span class="sxs-lookup"><span data-stu-id="83962-103">(Optional) Verify Response Group deployment in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83962-104">_**마지막으로 수정 된 항목:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="83962-104">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="83962-105">응답 그룹을 구성한 후에는 해당 구성에서 응답 그룹이 예상 대로 작동 하는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83962-105">After you configure Response Group, you need to verify the configuration to make sure your response groups work as expected.</span></span> <span data-ttu-id="83962-106">최소한 다음과 같은 유형의 사용자를 사용 하 여 다음 시나리오를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="83962-106">At minimum, verify the following scenarios by using the following types of users:</span></span>

<span data-ttu-id="83962-107">**사용자**</span><span class="sxs-lookup"><span data-stu-id="83962-107">**Users**</span></span>

  - <span data-ttu-id="83962-108">Lync Server 2013에 있는 사용자</span><span class="sxs-lookup"><span data-stu-id="83962-108">A user who is homed on Lync Server 2013</span></span>

  - <span data-ttu-id="83962-109">공중 전화망 (PSTN)을 사용 하는 외부 사용자</span><span class="sxs-lookup"><span data-stu-id="83962-109">An external user who uses the public switched telephone network (PSTN)</span></span>

  - <span data-ttu-id="83962-110">Lync Server 2013에 있는 에이전트</span><span class="sxs-lookup"><span data-stu-id="83962-110">An agent who is homed on Lync Server 2013</span></span>

<span data-ttu-id="83962-111">**시나리오**</span><span class="sxs-lookup"><span data-stu-id="83962-111">**Scenarios**</span></span>

  - <span data-ttu-id="83962-112">Lync Server 2013 사용자가 응답 그룹에 전화를 거는 경우</span><span class="sxs-lookup"><span data-stu-id="83962-112">The Lync Server 2013 user calls the response group.</span></span>

  - <span data-ttu-id="83962-113">외부 사용자가 응답 그룹에 전화를 겁니다.</span><span class="sxs-lookup"><span data-stu-id="83962-113">The external user calls the response group.</span></span>

  - <span data-ttu-id="83962-114">에이전트가 다른 전화를 받는 중에 사용자가 응답 그룹에 전화를 걸어 사용자가 큐로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="83962-114">A user calls the response group while the agent is on another call and goes to the queue.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

