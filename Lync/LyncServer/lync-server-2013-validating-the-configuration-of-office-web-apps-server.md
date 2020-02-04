---
title: 'Lync Server 2013: Office Web Apps 서버 구성 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating the configuration of Office Web Apps Server
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205393(v=OCS.15)
ms:contentKeyID: 48185859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 541929233eff5e401b3998aa84e463e2640378c0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a><span data-ttu-id="5f3ea-102">Lync Server 2013에서 Office Web Apps 서버의 구성 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="5f3ea-102">Validating the configuration of Office Web Apps Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f3ea-103">_**마지막으로 수정한 주제:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="5f3ea-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="5f3ea-104">Office Web Apps 서버를 토폴로지에 추가 하 고 해당 토폴로지가 게시 된 후에는 Lync Server 이벤트 로그에 새 이벤트 로그 이벤트가 두 개 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f3ea-104">After Office Web Apps Server has been added to the topology, and after that topology has been published, you should see two new event log events in the Lync Server event log.</span></span> <span data-ttu-id="5f3ea-105">첫째, LS 데이터 MCU 이벤트 (이벤트 ID 41034)를 추가 해야 합니다. 이 이벤트는 Office Web Apps 서버가 검색 되었음을 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f3ea-105">First, an LS Data MCU event (event ID 41034) should be added; this event will report that the Office Web Apps Server has been discovered:</span></span>

<span data-ttu-id="5f3ea-106">**웹 회의 서버 Office Web Apps 서버가 검색 되었으며, PowerPoint 콘텐츠를 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="5f3ea-106">**Web Conferencing Server Office Web Apps Server is discovered, PowerPoint content is enabled.**</span></span>

<span data-ttu-id="5f3ea-107">이 외에도, Office Web Apps 서버 Url을 보고 하는 다른 LS 데이터 MCU 이벤트 (이벤트 ID 41032)가 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f3ea-107">In addition to that you should see another LS Data MCU event (event ID 41032) that reports back Office Web Apps Server URLs.</span></span> <span data-ttu-id="5f3ea-108">예를 들어 다음과 같은 항목이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f3ea-108">For example, you should see something similar to this:</span></span>

<span data-ttu-id="5f3ea-109">**웹 회의 서버 Office Web Apps 서버 검색에 성공 했습니다.**</span><span class="sxs-lookup"><span data-stu-id="5f3ea-109">**Web Conferencing Server Office Web Apps Server discovery has succeeded.**</span></span>

<span data-ttu-id="5f3ea-110">**Office Web Apps Server 내부 발표자 페이지:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span><span class="sxs-lookup"><span data-stu-id="5f3ea-110">**Office Web Apps Server internal presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span></span>

<span data-ttu-id="5f3ea-111">**Office Web Apps Server 내부 참석자 페이지:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span><span class="sxs-lookup"><span data-stu-id="5f3ea-111">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span></span>

<span data-ttu-id="5f3ea-112">**Office Web Apps Server 외부 발표자 페이지:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span><span class="sxs-lookup"><span data-stu-id="5f3ea-112">**Office Web Apps Server external presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span></span>

<span data-ttu-id="5f3ea-113">**Office Web Apps Server 내부 참석자 페이지:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span><span class="sxs-lookup"><span data-stu-id="5f3ea-113">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span></span>

<span data-ttu-id="5f3ea-114">이벤트 ID가 41033 인 LS 데이터 MCU 이벤트가 표시 되는 경우 Office Web Apps 서버 검색에 실패 했음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f3ea-114">If you see an LS Data MCU event with the event ID of 41033 that means that Office Web Apps Server discovery has failed.</span></span> <span data-ttu-id="5f3ea-115">이 경우 Microsoft Lync Server 2013에서 새로 구성 된 Office Web Apps 서버를 검색 하는 데 필요한 횟수 만큼 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f3ea-115">In that case, Microsoft Lync Server 2013 will try as many times as needed to discover the newly-configured Office Web Apps Server.</span></span> <span data-ttu-id="5f3ea-116">검색 프로세스가 반복적으로 실행 되지 않는 경우 토폴로지 문서에서 Office Web Apps 서버를 제거 하 고 업데이트 된 토폴로지를 게시 한 다음 연결 문제가 해결 된 후에 Office Web Apps 서버를 토폴로지에 다시 추가 해 보세요.</span><span class="sxs-lookup"><span data-stu-id="5f3ea-116">If the discovery process fails repeatedly you should remove Office Web Apps Server from your topology document, publish the updated topology, and then try adding Office Web Apps Server back to the topology after the connectivity issues have been resolved.</span></span>

<span data-ttu-id="5f3ea-117">Office Web Apps 서버가 올바르게 구성 되어 있고 검색 프로세스에서 인식 되는 것으로 표시 되는 경우 Microsoft Lync 2013 클라이언트 쌍 간에 PowerPoint 프레젠테이션을 공유 하 여 Office Web Apps 서버가 예상 대로 작동 하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f3ea-117">If Office Web Apps Server appears to be configured correctly and has been recognized by the discovery process you can verify that Office Web Apps Server is working as expected by sharing a PowerPoint presentation between a pair of Microsoft Lync 2013 clients.</span></span> <span data-ttu-id="5f3ea-118">사용자 A가 PowerPoint 프레젠테이션을 로드 하 고 표시할 수 있으며, 사용자 B가 모임에 참가 하 여 해당 프레젠테이션을 볼 수 있으면 Office Web Apps 서버가 작동 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5f3ea-118">If User A can load and display the PowerPoint presentation and if User B can then join the meeting and see that presentation then Office Web Apps Server is working.</span></span>

<span data-ttu-id="5f3ea-119">Office Web Apps Server가 올바르게 구성 되어 있더라도 PowerPoint 프레젠테이션을 공유 하려고 하면 "서버 연결 문제로 인해 일부 공유 기능을 사용할 수 없습니다." 오류 메시지가 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f3ea-119">Even if Office Web Apps Server appears to be configured correctly, you could potentially receive the error message “Some sharing features are unavailable due to server connectivity issues” when you try sharing a PowerPoint presentation.</span></span> <span data-ttu-id="5f3ea-120">해당 오류 메시지가 나타나면 새 Office Web Apps 서버와 연결 된 프런트 엔드 서버 (또는 서버)를 다시 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f3ea-120">If you receive that error message you should restart the Front End server (or servers) associated with the new Office Web Apps Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

