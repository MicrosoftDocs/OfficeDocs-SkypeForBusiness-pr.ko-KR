---
title: 'Lync Server 2013: (선택 사항) 통화 공원 배포 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Verify Call Park deployment
ms:assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413076(v=OCS.15)
ms:contentKeyID: 48185952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 110617bbd77da0efb8802c6aba401f2ea5075b01
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980113"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a><span data-ttu-id="8bad8-102">) Lync Server 2013에서 통화 공원 배포 확인</span><span class="sxs-lookup"><span data-stu-id="8bad8-102">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8bad8-103">_**마지막으로 수정한 주제:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="8bad8-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="8bad8-104">통화 대기를 설치 및 구성한 후에는 파킹 및 검색 통화가 예상 대로 작동 하는지 확인 하는 구성을 검증 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bad8-104">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="8bad8-105">최소한 다음 사항을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="8bad8-105">At minimum, verify the following:</span></span>

  - <span data-ttu-id="8bad8-106">통화 공원을 사용 하도록 설정한 사용자에 게 전화를 걸고 사용자에 게 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bad8-106">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8bad8-107">이 테스트를 수행 하기 바로 전에 음성 정책에서 통화 대기를 사용 하도록 설정한 경우 통화를 파킹 하는 사용자는 Lync Server에서 로그 아웃 한 다음 다시 로그인 하 여 통화 전송 목록의 통화 대기 옵션을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bad8-107">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Lync Server, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span>

    
    </div>

  - <span data-ttu-id="8bad8-108">통화를 검색 하려면 궤도 번호로 전화를 겁니다.</span><span class="sxs-lookup"><span data-stu-id="8bad8-108">Dial the orbit number to retrieve the call.</span></span>

  - <span data-ttu-id="8bad8-109">다른 전화를 걸고, 파킹 된 통화 시간을 초과 하 고, ringback를 선택 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8bad8-109">Park another call, let the parked call time out, and do not pick up the ringback.</span></span> <span data-ttu-id="8bad8-110">시간 제한 통화가 **Ontimeouturi**에 대해 지정 된 대체 대상으로 올바르게 라우팅 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bad8-110">Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

