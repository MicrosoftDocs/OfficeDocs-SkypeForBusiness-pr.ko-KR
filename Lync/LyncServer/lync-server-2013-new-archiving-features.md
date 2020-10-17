---
title: 'Lync Server 2013: 새로운 보관 기능'
description: 'Lync Server 2013: 새로운 보관 기능'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Archiving features
ms:assetid: c002e367-41ad-498d-9d23-8b117ac435b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205225(v=OCS.15)
ms:contentKeyID: 48185288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5b69c90e62914284f178ae328375c6e350f5b3e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561354"
---
# <a name="new-archiving-features-in-lync-server-2013"></a><span data-ttu-id="a002a-103">Lync Server 2013의 새로운 보관 기능</span><span class="sxs-lookup"><span data-stu-id="a002a-103">New Archiving features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a002a-104">_**마지막으로 수정 된 항목:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="a002a-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="a002a-105">Lync Server 2013의 보관은 다음과 같은 유형의 콘텐츠를 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a002a-105">Archiving in Lync Server 2013 can archive the following types of content:</span></span>

  - <span data-ttu-id="a002a-106">피어 투 피어 인스턴트 메시지</span><span class="sxs-lookup"><span data-stu-id="a002a-106">Peer-to-peer instant messages</span></span>

  - <span data-ttu-id="a002a-107">단체 인스턴트 메시지인 회의(모임)</span><span class="sxs-lookup"><span data-stu-id="a002a-107">Conferences (meetings) that are multi-party instant messages</span></span>

  - <span data-ttu-id="a002a-108">업로드된 콘텐츠(예: 참고 파일) 및 이벤트 관련 콘텐츠(예: 입장, 퇴장, 업로드 공유 및 표시 여부 변경)를 비롯한 회의 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="a002a-108">Conference content, including uploaded content (for example, handouts) and event-related content (for example, joining, leaving, uploading sharing, and changes in visibility)</span></span>

<span data-ttu-id="a002a-109">또한 Lync Server 2013의 보관은 배포 및 작업 효율성을 향상 시키는 새로운 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a002a-109">Additionally, Archiving in Lync Server 2013 provides new features that improve deployment and operations efficiency.</span></span> <span data-ttu-id="a002a-110">이러한 새 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a002a-110">These new features consist of:</span></span>

  - <span data-ttu-id="a002a-111">**프런트 엔드 서버에서 보관 위치입니다.**     Lync Server 2013에는 별도의 보관 서버 역할이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a002a-111">**Collocation of Archiving on Front End Servers.**   Lync Server 2013 does not have a separate Archiving Server role.</span></span> <span data-ttu-id="a002a-112">보관은 Enterprise Edition 배포의 모든 프런트 엔드 서버와 풀 또는 사이트에 대해 구성하여 구현될 수 있는 Standard Edition Server에서 사용할 수 있는 선택적 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="a002a-112">Archiving is an optional feature available on all Front End Servers in an Enterprise Edition deployment, and on Standard Edition servers, that can be implemented configured for a pool or a site.</span></span>

  - <span data-ttu-id="a002a-113">**Microsoft Exchange 통합**     보관을 배포할 때는 데이터 저장소를 Exchange 2013에 있는 모든 사용자의 기존 Exchange 2013 저장소와 통합 하 여 보관할 수 In-Place 있으며, 별도의 SQL Server 데이터베이스를 배포 하 여 Lync 데이터를 보관할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a002a-113">**Microsoft Exchange integration.**   When you deploy Archiving, you can integrate data storage for Archiving with your existing Exchange 2013 storage for all users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, so you don’t need to deploy separate SQL Server databases to archive Lync data.</span></span> <span data-ttu-id="a002a-114">Exchange 2013 배포가 없거나 해당 사서함과 통합 하지 않으려는 경우 또는 Exchange 2013에 포함 되지 않은 Lync 2013 사용자가 있는 경우에는 (이) In-Place 유지 하려면 SQL Server를 사용 하 여 Lync communications에서 보관 된 데이터를 저장 하는 별도의 보관 데이터베이스를 배포 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a002a-114">If you do not have an Exchange 2013 deployment, or if you prefer not to integrate with it, or if you have any Lync 2013 users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold, you can deploy separate Archiving databases by using SQL Server to store archived data from Lync communications.</span></span> <span data-ttu-id="a002a-115">배포의 일부 사용자에 대해서만 Microsoft Exchange 통합을 사용 하려는 경우 Microsoft Exchange 통합 및 Lync Server 2013 보관 데이터베이스를 모두 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a002a-115">You can use both Microsoft Exchange integration and Lync Server 2013 Archiving databases if you want to use Microsoft Exchange integration for some but not all users in your deployment.</span></span> <span data-ttu-id="a002a-116">In-Place 보존에 대 한 자세한 내용은의 "원본 위치 유지"를 참조 하십시오 [https://go.microsoft.com/fwlink/p/?LinkId=267500](https://go.microsoft.com/fwlink/p/?linkid=267500) .</span><span class="sxs-lookup"><span data-stu-id="a002a-116">For details about In-Place Hold, see “In-Place Hold” at [https://go.microsoft.com/fwlink/p/?LinkId=267500](https://go.microsoft.com/fwlink/p/?linkid=267500).</span></span>

  - <span data-ttu-id="a002a-117">**SQL 저장소 미러링**     보관을 배포할 때 보관 데이터베이스에 대해 SQL Server 데이터베이스 미러링을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a002a-117">**SQL Store Mirroring.**   When you deploy Archiving, you can enable SQL Server database mirroring for your Archiving database.</span></span>

  - <span data-ttu-id="a002a-118">**화이트 보드 및 설문 조사 보관**     보관 된 회의 콘텐츠는 이제 모임 중 공유 되는 화이트 보드 및 설문 조사를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a002a-118">**Archiving of Whiteboards and Polls.**   Archived conference content now includes whiteboards and polls that are shared during the meeting.</span></span>

<span data-ttu-id="a002a-119">보관되지 않는 콘텐츠 유형은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a002a-119">The following types of content are not archived:</span></span>

  - <span data-ttu-id="a002a-120">피어 투 피어 파일 전송</span><span class="sxs-lookup"><span data-stu-id="a002a-120">Peer-to-peer file transfers</span></span>

  - <span data-ttu-id="a002a-121">피어 투 피어 인스턴스 메시지 및 회의에 대한 오디오/비디오</span><span class="sxs-lookup"><span data-stu-id="a002a-121">Audio/video for peer-to-peer instant messages and conferences</span></span>

  - <span data-ttu-id="a002a-122">피어 투 피어 인스턴스 메시지 및 회의에 대한 응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="a002a-122">Application sharing for peer-to-peer instant messages and conferences</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="a002a-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a002a-123">See Also</span></span>


[<span data-ttu-id="a002a-124">Lync Server 2013의 보관 계획</span><span class="sxs-lookup"><span data-stu-id="a002a-124">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

