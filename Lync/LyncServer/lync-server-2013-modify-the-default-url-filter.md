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
ms.openlocfilehash: 975824faa6a567992001ae10cafec61ef2ea1370
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766019"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-url-filter-in-lync-server-2013"></a><span data-ttu-id="d4487-102">Lync Server 2013의 기본 URL 필터 수정</span><span class="sxs-lookup"><span data-stu-id="d4487-102">Modify the default URL filter in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4487-103">_**마지막으로 수정한 주제:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="d4487-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="d4487-104">Lync Server 2013는 메신저 대화 (IM) 필터를 사용 하 여 Lync Server 2013 배포 전체에서 사용자 간의 IM 인스턴트 메시지에 포함 된 특정 Url을 차단 하는 전역 URL 필터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4487-104">By using the instant messaging (IM) filter, Lync Server 2013 provides a global URL filter that blocks specific URLs contained in IM conversations among users throughout your Lync Server 2013 deployment.</span></span> <span data-ttu-id="d4487-105">Lync Server 제어판을 사용 하 여 다음을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4487-105">By using Lync Server Control Panel, you can do the following:</span></span>

  - <span data-ttu-id="d4487-106">인스턴트 메시지 대화에서 Url 전체 또는 일부를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4487-106">Block all or a subset of URLs in instant message conversations.</span></span>

  - <span data-ttu-id="d4487-107">모든 Url을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4487-107">Allow all URLs.</span></span> <span data-ttu-id="d4487-108">옵션으로 URL을 포함 하는 각 인스턴트 메시지의 시작 부분에 삽입 되는 알림을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4487-108">As an option, you can create a notice that is inserted at the beginning of each instant message that contains a URL.</span></span>

  - <span data-ttu-id="d4487-109">특정 Url을 허용 하 고 URL이 포함 된 각 인스턴트 메시지에 대 한 경고를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4487-109">Allow specific URLs and include a warning with each instant message that contains a URL.</span></span>

<span data-ttu-id="d4487-110">또한 특정 파일 형식이 포함 된 Url을 차단 하거나 서버 로컬 인트라넷 영역에 있는 Url (인트라넷 Url)을 통해 서버를 통과할 수 있도록 하 여 인터넷 Url만 차단 하도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4487-110">In addition, you can choose to block URLs that contain specific file types, or block only Internet URLs by allowing URLs that are within the server’s local intranet zone — intranet URLs — to pass through the server.</span></span> <span data-ttu-id="d4487-111">URL 필터링에 대 한 자세한 내용은 [Lync Server 2013에서 IM (인스턴트 메시징)에 대 한 파일 전송 및 URL 필터링 구성을](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d4487-111">For details about URL filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="d4487-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4487-112">See Also</span></span>


[<span data-ttu-id="d4487-113">Lync Server 2013에서 IM (인스턴트 메시징)에 대 한 파일 전송 및 URL 필터링 구성</span><span class="sxs-lookup"><span data-stu-id="d4487-113">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="d4487-114">특정 사이트에 대 한 Lync Server 2013에서 새 파일 전송 필터 만들기</span><span class="sxs-lookup"><span data-stu-id="d4487-114">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="d4487-115">Lync Server 2013에서 새 URL 필터를 만들어 메신저 대화의 하이퍼링크 처리</span><span class="sxs-lookup"><span data-stu-id="d4487-115">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[<span data-ttu-id="d4487-116">Lync Server 2013의 기본 파일 전송 필터 수정</span><span class="sxs-lookup"><span data-stu-id="d4487-116">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

