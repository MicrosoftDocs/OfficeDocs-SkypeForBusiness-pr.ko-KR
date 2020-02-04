---
title: 'Lync Server 2013: 에지 구성 요소에 대한 지원되는 서버 배치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported server collocation for edge components
ms:assetid: 435c4dd8-36af-4b71-9b88-3ffcf0fc5c65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425934(v=OCS.15)
ms:contentKeyID: 48183978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc12e442be98ba1fd962634460200ce749aca3d6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731668"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-server-collocation-for-edge-components-in-lync-server-2013"></a><span data-ttu-id="af585-102">Lync Server 2013의 에지 구성 요소에 대한 지원되는 서버 배치</span><span class="sxs-lookup"><span data-stu-id="af585-102">Supported server collocation for edge components in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af585-103">_**마지막으로 수정한 주제:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="af585-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="af585-104">액세스에 지 서비스, 웹 회의 Edge 서비스, A/V Edge 서비스 및 XMPP 프록시 서비스는 Edge 서버에 collocated 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af585-104">The Access Edge service, Web Conferencing Edge service, A/V Edge service and XMPP Proxy service are collocated on the Edge Servers.</span></span> <span data-ttu-id="af585-105">다음 서버는 외부 사용자 액세스에 필요한 기능을 제공 하며 전용 서버로 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af585-105">The following servers provide functions needed for external user access and must be deployed as dedicated servers:</span></span>

  - <span data-ttu-id="af585-106">Edge 서버</span><span class="sxs-lookup"><span data-stu-id="af585-106">Edge Server</span></span>

  - <span data-ttu-id="af585-107">이사 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="af585-107">Director (Optional)</span></span>

  - <span data-ttu-id="af585-108">역방향 프록시</span><span class="sxs-lookup"><span data-stu-id="af585-108">Reverse proxy</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="af585-109">역방향 프록시는 Lync Server 2013만을 제공 하기 위해 전용으로 설정할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af585-109">The reverse proxy does not need to be dedicated to serving only Lync Server 2013.</span></span> <span data-ttu-id="af585-110">예를 들어 Lync Server 웹 서비스를 게시 하는 서비스를 제공 하 고 동시에 Lync Server와 다른 웹 사이트에 대 한 게시 된 웹 사이트를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af585-110">For example, you can provide services to publish the Lync Server Web services, and concurrently provide a published Web site for another Web site that has no bearing on Lync Server at all.</span></span> <span data-ttu-id="af585-111">주변 네트워크에 다른 서비스를 지 원하는 역방향 프록시 서버가 이미 있는 경우 Lync Server 2013에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af585-111">If you already have a reverse proxy server in the perimeter network to support other services, you can use it for Lync Server 2013.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

