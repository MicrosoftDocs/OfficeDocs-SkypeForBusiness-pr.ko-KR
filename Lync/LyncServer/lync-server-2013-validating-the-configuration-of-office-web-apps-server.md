---
title: 'Lync Server 2013: Office Web Apps 서버의 구성 유효성 검사'
description: 'Lync Server 2013: Office Web Apps 서버의 구성 유효성을 검사 하는 중입니다.'
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
ms.openlocfilehash: 80c3160dd9a76c129fbb0289929a868b897beb2c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547154"
---
# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a><span data-ttu-id="d4d74-103">Lync Server 2013에서 Office Web Apps 서버의 구성 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="d4d74-103">Validating the configuration of Office Web Apps Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4d74-104">_**마지막으로 수정 된 항목:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="d4d74-104">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="d4d74-105">Office Web Apps 서버를 토폴로지에 추가 하 고 토폴로지를 게시 한 후에는 Lync Server 이벤트 로그에 두 개의 새 이벤트 로그 이벤트가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4d74-105">After Office Web Apps Server has been added to the topology, and after that topology has been published, you should see two new event log events in the Lync Server event log.</span></span> <span data-ttu-id="d4d74-106">먼저 LS 데이터 MCU 이벤트 (이벤트 ID 41034)를 추가 해야 합니다. 이 이벤트는 Office Web Apps 서버가 검색 되었음을 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d74-106">First, an LS Data MCU event (event ID 41034) should be added; this event will report that the Office Web Apps Server has been discovered:</span></span>

<span data-ttu-id="d4d74-107">**웹 회의 서버 Office Web Apps 서버가 검색 되 면 PowerPoint 콘텐츠가 사용 되도록 설정 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="d4d74-107">**Web Conferencing Server Office Web Apps Server is discovered, PowerPoint content is enabled.**</span></span>

<span data-ttu-id="d4d74-p102">또한 백 오피스 Office Web Apps 서버 URL을 보고하는 또 다른 LS 데이터 MCU 이벤트(이벤트 ID 41032)도 표시되어야 합니다. 예를 들면 다음과 같은 로그가 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d74-p102">In addition to that you should see another LS Data MCU event (event ID 41032) that reports back Office Web Apps Server URLs. For example, you should see something similar to this:</span></span>

<span data-ttu-id="d4d74-110">**웹 회의 서버 Office Web Apps 서버 검색이 성공 했습니다.**</span><span class="sxs-lookup"><span data-stu-id="d4d74-110">**Web Conferencing Server Office Web Apps Server discovery has succeeded.**</span></span>

<span data-ttu-id="d4d74-111">**Office Web Apps Server 내부 발표자 페이지: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span><span class="sxs-lookup"><span data-stu-id="d4d74-111">**Office Web Apps Server internal presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span></span>

<span data-ttu-id="d4d74-112">**Office Web Apps Server 내부 참석자 페이지: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span><span class="sxs-lookup"><span data-stu-id="d4d74-112">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span></span>

<span data-ttu-id="d4d74-113">**Office Web Apps 서버 외부 발표자 페이지: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span><span class="sxs-lookup"><span data-stu-id="d4d74-113">**Office Web Apps Server external presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span></span>

<span data-ttu-id="d4d74-114">**Office Web Apps Server 내부 참석자 페이지: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span><span class="sxs-lookup"><span data-stu-id="d4d74-114">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span></span>

<span data-ttu-id="d4d74-115">이벤트 ID가 41033인 LS 데이터 MCU 이벤트가 표시되는 경우 이는 Office Web Apps 서버가 검색되지 않았음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d74-115">If you see an LS Data MCU event with the event ID of 41033 that means that Office Web Apps Server discovery has failed.</span></span> <span data-ttu-id="d4d74-116">이 경우 Microsoft Lync Server 2013는 새로 구성 된 Office Web Apps 서버를 검색 하는 데 필요한 횟수 만큼 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d74-116">In that case, Microsoft Lync Server 2013 will try as many times as needed to discover the newly-configured Office Web Apps Server.</span></span> <span data-ttu-id="d4d74-117">검색 프로세스가 계속 실패할 경우에는 Office Web Apps 서버를 토폴로지 문서에서 제거하고 업데이트된 토폴로지를 게시한 다음 연결 문제가 해결된 후에 Office Web Apps 서버를 토폴로지에 다시 추가해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="d4d74-117">If the discovery process fails repeatedly you should remove Office Web Apps Server from your topology document, publish the updated topology, and then try adding Office Web Apps Server back to the topology after the connectivity issues have been resolved.</span></span>

<span data-ttu-id="d4d74-118">Office Web Apps 서버가 올바르게 구성 된 것으로 표시 되 고 검색 프로세스에서 인식 되는 경우 Microsoft Lync 2013 클라이언트 쌍 간에 PowerPoint 프레젠테이션을 공유 하 여 Office Web Apps 서버가 예상 대로 작동 하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d74-118">If Office Web Apps Server appears to be configured correctly and has been recognized by the discovery process you can verify that Office Web Apps Server is working as expected by sharing a PowerPoint presentation between a pair of Microsoft Lync 2013 clients.</span></span> <span data-ttu-id="d4d74-119">사용자 A가 PowerPoint 프레젠테이션을 로드하고 표시할 수 있으며 사용자 B가 모임에 참가하고 해당 프레젠테이션을 볼 수 있는 경우에는 Office Web Apps 서버가 작동 중인 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d74-119">If User A can load and display the PowerPoint presentation and if User B can then join the meeting and see that presentation then Office Web Apps Server is working.</span></span>

<span data-ttu-id="d4d74-p105">Office Web Apps 서버가 올바르게 구성된 것처럼 보이지만, PowerPoint 프레젠테이션을 공유하려 할 때 “서버 연결 문제로 인해 일부 공유 기능을 사용할 수 없습니다.”라는 오류 메시지를 나타날 수도 있습니다. 이러한 오류 메시지가 나타나면 새 Office Web Apps 서버와 연결된 프런트 엔드 서버를 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d74-p105">Even if Office Web Apps Server appears to be configured correctly, you could potentially receive the error message “Some sharing features are unavailable due to server connectivity issues” when you try sharing a PowerPoint presentation. If you receive that error message you should restart the Front End server (or servers) associated with the new Office Web Apps Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

