---
title: 'Lync Server 2013: 디렉터 시나리오'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scenarios for the Director
ms:assetid: d2cf384a-0860-4779-80ce-cba2543be322
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398908(v=OCS.15)
ms:contentKeyID: 48185419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eba35647e8ecc0cfa59d5c7c6b5c32b07bedf95e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983838"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-the-director-in-lync-server-2013"></a><span data-ttu-id="d7183-102">Lync Server 2013의 디렉터 시나리오</span><span class="sxs-lookup"><span data-stu-id="d7183-102">Scenarios for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7183-103">_**마지막으로 수정한 주제:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="d7183-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="d7183-104">디렉터는 사용자 요청을 인증할 수 있지만 사용자 계정은 홈이 아닌 Microsoft Lync Server 2013 통신 소프트웨어를 실행 하는 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="d7183-104">A Director is a server running Microsoft Lync Server 2013 communications software that can authenticate user requests, but does not home any user accounts.</span></span> <span data-ttu-id="d7183-105">또한 디렉터는 프런트 엔드 서버와 유사한 웹 서비스도 호스팅하고 웹 티켓 요청을 인증 하 고 다른 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7183-105">The Director also hosts web services similar to the Front End Server and will authenticate web ticket requests and provide other services.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d7183-106">디렉터를 배포 하는 경우 역방향 프록시를 통해 외부의 디렉터 웹 서비스 및 프런트 엔드 서버의 웹 서비스를 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7183-106">If you deploy Directors, you must publish the Director web services externally through the reverse proxy as well as the web services of the Front End Server.</span></span> <span data-ttu-id="d7183-107">다음 항목에서는 가능 디렉터 토폴로지에 대 한 계획 프로세스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7183-107">The topics following describe the planning process for the possible Director topologies.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d7183-108">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="d7183-108">In This Section</span></span>

  - [<span data-ttu-id="d7183-109">Lync Server 2013의 디렉터 개요</span><span class="sxs-lookup"><span data-stu-id="d7183-109">Overview of the Director in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-director.md)

  - [<span data-ttu-id="d7183-110">Lync Server 2013의 디렉터에 필요한 구성 요소</span><span class="sxs-lookup"><span data-stu-id="d7183-110">Components required for the Director in Lync Server 2013</span></span>](lync-server-2013-components-required-for-the-director.md)

  - [<span data-ttu-id="d7183-111">Lync Server 2013의 디렉터에 대한 하드웨어 및 소프트웨어 요구 사항</span><span class="sxs-lookup"><span data-stu-id="d7183-111">Hardware and software requirements for the Director in Lync Server 2013</span></span>](lync-server-2013-hardware-and-software-requirements-for-the-director.md)

  - [<span data-ttu-id="d7183-112">Lync Server 2013의 단일 디렉터</span><span class="sxs-lookup"><span data-stu-id="d7183-112">Single Director in Lync Server 2013</span></span>](lync-server-2013-single-director.md)

  - [<span data-ttu-id="d7183-113">Lync Server 2013의 조정된 디렉터 풀</span><span class="sxs-lookup"><span data-stu-id="d7183-113">Scaled Director pool in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d7183-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d7183-114">See Also</span></span>


[<span data-ttu-id="d7183-115">Lync Server 2013의 지원되는 토폴로지</span><span class="sxs-lookup"><span data-stu-id="d7183-115">Supported topologies in Lync Server 2013</span></span>](lync-server-2013-supported-topologies.md)  
[<span data-ttu-id="d7183-116">Lync Server 2013의 서버 하드웨어 플랫폼</span><span class="sxs-lookup"><span data-stu-id="d7183-116">Server hardware platforms for Lync Server 2013</span></span>](lync-server-2013-server-hardware-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

