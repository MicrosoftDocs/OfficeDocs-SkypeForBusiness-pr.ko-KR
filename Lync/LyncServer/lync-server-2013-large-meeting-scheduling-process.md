---
title: 'Lync Server 2013: 대규모 모임 예약 프로세스'
description: 'Lync Server 2013: 대규모 모임 예약 프로세스'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Large-meeting scheduling process
ms:assetid: de267458-885f-4176-a8d7-1a218e67640e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205334(v=OCS.15)
ms:contentKeyID: 48185639
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96d383b6da96fb7d36e031485feac2ff927df347
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557594"
---
# <a name="large-meeting-scheduling-process-in-lync-server-2013"></a><span data-ttu-id="bfc13-103">Lync Server 2013의 대량 모임 예약 프로세스</span><span class="sxs-lookup"><span data-stu-id="bfc13-103">Large-meeting scheduling process in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfc13-104">_**마지막으로 수정 된 항목:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="bfc13-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="bfc13-105">대규모 전용 모임 풀에서는 한 번에 하나의 대규모 모임만 지원되므로 대규모 모임 간 충돌을 방지하기 위해 대규모 모임 예약 프로세스를 구현하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc13-105">Because only one large meeting at a time is supported on the dedicated large meeting pool, we recommend implementing a large meeting scheduling process to help prevent large meeting conflicts.</span></span> <span data-ttu-id="bfc13-106">이러한 예약 프로세스의 목적은 대규모 모임을 쉽게 설정할 수 있게 지원하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bfc13-106">The purpose of such the scheduling process is to facilitate setting up large meetings.</span></span> <span data-ttu-id="bfc13-107">Lync Server 또는 Lync Server 클라이언트는 이러한 기능을 직접 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc13-107">Such capability is not provided directly by Lync Server or Lync Server clients.</span></span> <span data-ttu-id="bfc13-108">이러한 프로세스를 구현하는 한 가지 방법은 조직 지원 팀의 발권 시스템(사용 가능한 경우)을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bfc13-108">One way to implement such a process is to use your organization’s support team’s ticketing system, if available.</span></span>

<span data-ttu-id="bfc13-109">대규모 모임 이끌이는 대규모 모임 예약 시 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc13-109">For organizers of large meetings, scheduling a large meeting involves completing the following steps:</span></span>

1.  <span data-ttu-id="bfc13-p102">모임 이끌이나 대리자가 예정된 모임의 시간, 기간 및 규모와 발표자 목록을 결정합니다. 또한 예상된 모임 규모가 250명을 초과하거나 250명 미만의 모임을 위한 최상의 사용자 환경을 유지하려는 경우 대규모 모임 요청을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc13-p102">The meeting organizer or delegate determines the time, duration, and size of an upcoming meeting, in addition to the list of presenters. If the anticipated meeting size exceeds 250 users or to ensure the best user experience for a meeting of fewer than 250 users, the organizer or the delegate submits a request for a large meeting.</span></span>

2.  <span data-ttu-id="bfc13-p103">예약 직원은 요청된 날짜와 시간이 예약 가능한지 확인합니다. 전용 풀에서 한 번에 하나의 대규모 모임만 지원되므로 예약 직원은 요청한 날짜 및 시간에 예약된 다른 모임이 있는지 알아보기 위해 대규모 모음 일정을 확인해야 합니다. 요청한 시간이 예약 가능하면 직원은 모임 요청을 승인합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc13-p103">The scheduling staff checks to see whether the requested date and time is available. Since we support only a single large meeting on the dedicated pool at a time, the scheduling staff needs to check the large-meeting calendar to determine whether there is another meeting scheduled for the requested date and time. If the requested time is available, the staff approves the meeting request.</span></span>

3.  <span data-ttu-id="bfc13-115">요청이 승인 되 면 예약 직원 (전용 풀에서 자격 증명 사용)이 Outlook을 사용 하 여 Lync 2013에 대 한 온라인 모임 추가 기능을 사용 하 여 전용 대규모 모임 풀에서 모임을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc13-115">If the request is approved, the scheduling staff (using credentials on the dedicated pool) uses Online Meeting Add-in for Lync 2013 with Outlook to set up a meeting on the dedicated large-meeting pool.</span></span> <span data-ttu-id="bfc13-116">모임에 참가하는 데 사용될 URL은 승인 알림의 일부로 요청자에게 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfc13-116">The URL to be used to join the meeting is provided to the requester as part of the approval notice.</span></span>

4.  <span data-ttu-id="bfc13-117">모임 이끌이 또는 대리인은 Outlook을 사용 하 여 모임 초대에 모임에 참가 하는 데 사용할 수 있는 URL을 추가 하 고 예정 된 모임을 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc13-117">The meeting organizer or delegate uses Outlook to schedule the upcoming meeting, adding the URL for joining the meeting to the meeting invitation.</span></span> <span data-ttu-id="bfc13-118">그런 다음 초대할 사용자를 지정하여 모임 초대를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="bfc13-118">The meeting organizer or delegate then specifies the users to be invited and sends out the meeting invitation.</span></span>
    
    <span data-ttu-id="bfc13-119">다음 그림은 대규모 모임 예약을 위한 일반적인 요청 및 승인 워크플로를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bfc13-119">The following figure illustrates a typical request and approval workflow for scheduling large meetings.</span></span>
    
    <span data-ttu-id="bfc13-120">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span><span class="sxs-lookup"><span data-stu-id="bfc13-120">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span></span>  

</div>

<span> </span>

</div>

</div>

</div>

