---
title: 'Lync Server 2013: 기본 URL 필터 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default URL filter
ms:assetid: 80a472b3-054e-45a6-80fc-9ee2bda28ee6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182544(v=OCS.15)
ms:contentKeyID: 48184653
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15511ea6b48697cddfebc40c671880a14a545557
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-url-filter-in-lync-server-2013"></a><span data-ttu-id="6f477-102">Lync Server 2013의 기본 URL 필터 수정</span><span class="sxs-lookup"><span data-stu-id="6f477-102">Modify the default URL filter in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f477-103">_**마지막으로 수정 된 항목:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="6f477-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="6f477-104">Lync Server 2013에서는 IM (인스턴트 메시징) 필터를 사용 하 여 Lync Server 2013 배포 전체에서 사용자 간의 IM 대화에 포함 된 특정 Url을 차단 하는 글로벌 URL 필터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f477-104">By using the instant messaging (IM) filter, Lync Server 2013 provides a global URL filter that blocks specific URLs contained in IM conversations among users throughout your Lync Server 2013 deployment.</span></span> <span data-ttu-id="6f477-105">Lync Server 제어판을 사용 하 여 다음을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f477-105">By using Lync Server Control Panel, you can do the following:</span></span>

  - <span data-ttu-id="6f477-106">인스턴트 메시지 대화에서 모든 URL 또는 URL의 하위 집합을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="6f477-106">Block all or a subset of URLs in instant message conversations.</span></span>

  - <span data-ttu-id="6f477-p102">모든 URL을 허용합니다. 옵션으로 URL이 포함된 각 인스턴트 메시지의 시작 부분에 삽입되는 공지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f477-p102">Allow all URLs. As an option, you can create a notice that is inserted at the beginning of each instant message that contains a URL.</span></span>

  - <span data-ttu-id="6f477-109">특정 URL을 허용하고 URL이 포함된 각 인스턴트 메시지에 경고를 포함시킵니다.</span><span class="sxs-lookup"><span data-stu-id="6f477-109">Allow specific URLs and include a warning with each instant message that contains a URL.</span></span>

<span data-ttu-id="6f477-110">또한 특정 파일 형식이 포함된 URL을 차단하거나 서버의 로컬 인트라넷 영역 내에 있는 URL(인트라넷 URL)만 서버를 통과하도록 허용하여 인터넷 URL만 차단하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f477-110">In addition, you can choose to block URLs that contain specific file types, or block only Internet URLs by allowing URLs that are within the server’s local intranet zone — intranet URLs — to pass through the server.</span></span> <span data-ttu-id="6f477-111">URL 필터링에 대 한 자세한 내용은 [Lync Server 2013에서 IM (인스턴트 메시징)에 대 한 파일 전송 및 URL 필터링 구성을](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6f477-111">For details about URL filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="6f477-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6f477-112">See Also</span></span>


[<span data-ttu-id="6f477-113">Lync Server 2013에서 IM (인스턴트 메시징)에 대 한 파일 전송 및 URL 필터링 구성</span><span class="sxs-lookup"><span data-stu-id="6f477-113">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="6f477-114">특정 사이트에 대해 Lync Server 2013에서 새 파일 전송 필터 만들기</span><span class="sxs-lookup"><span data-stu-id="6f477-114">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="6f477-115">Lync Server 2013에서 새 URL 필터 만들기 IM 대화의 하이퍼링크를 처리 하려면</span><span class="sxs-lookup"><span data-stu-id="6f477-115">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[<span data-ttu-id="6f477-116">Lync Server 2013에서 기본 파일 전송 필터 수정</span><span class="sxs-lookup"><span data-stu-id="6f477-116">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

