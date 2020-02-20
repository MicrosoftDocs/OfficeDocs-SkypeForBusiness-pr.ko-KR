---
title: 'Lync Server 2013: (선택 사항) 통화 대기 배포 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify Call Park deployment
ms:assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413076(v=OCS.15)
ms:contentKeyID: 48185952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e0389e729f91da7cb91dff9426e38c1dcf20024
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a><span data-ttu-id="63200-102">반드시 Lync Server 2013의 통화 대기 배포 확인</span><span class="sxs-lookup"><span data-stu-id="63200-102">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63200-103">_**마지막으로 수정 된 항목:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="63200-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="63200-104">통화 대기를 설치 및 구성한 후에는 구성을 확인 하 여 대기 중 대기 및 검색 통화가 예상 대로 작동 하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63200-104">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="63200-105">최소한 다음 사항을 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="63200-105">At minimum, verify the following:</span></span>

  - <span data-ttu-id="63200-106">통화 대기를 사용 하도록 설정 하 고 사용자가 통화를 대기 하도록 하는 사용자에 게 전화를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="63200-106">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="63200-107">음성 정책에서이 테스트를 수행 하기 직전에 통화 대기를 사용 하도록 설정한 경우 통화를 대기 하는 사용자는 Lync Server에서 로그 아웃 한 다음 다시 로그인 하 여 통화 전송 목록의 통화 대기 옵션을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63200-107">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Lync Server, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span>

    
    </div>

  - <span data-ttu-id="63200-108">파킹된 통화 번호로 전화를 걸어 통화를 재개합니다.</span><span class="sxs-lookup"><span data-stu-id="63200-108">Dial the orbit number to retrieve the call.</span></span>

  - <span data-ttu-id="63200-p102">다른 통화를 대기 상태로 설정하고 대기된 통화의 제한 시간을 초과시키며 되걸려오는 전화를 받지 않습니다. 제한 시간이 초과된 통화가 **OnTimeoutURI**에 지정한 대체 대상으로 제대로 라우팅되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="63200-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

