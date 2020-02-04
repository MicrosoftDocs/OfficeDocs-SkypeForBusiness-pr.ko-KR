---
title: 'Lync Server 2013: 대용량 모임 예약 프로세스'
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
ms.openlocfilehash: b2cfe26b70db612249ca840c86b41fb3d60db663
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-scheduling-process-in-lync-server-2013"></a><span data-ttu-id="3517f-102">Lync Server 2013의 대용량 모임 예약 프로세스</span><span class="sxs-lookup"><span data-stu-id="3517f-102">Large-meeting scheduling process in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3517f-103">_**마지막으로 수정한 주제:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="3517f-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="3517f-104">전용 대형 모임 풀에서는 한 번에 하나의 큰 모임만 지원 되므로 대규모 모임 예약 프로세스를 구현 하 여 큰 모임이 충돌 하는 것을 방지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3517f-104">Because only one large meeting at a time is supported on the dedicated large meeting pool, we recommend implementing a large meeting scheduling process to help prevent large meeting conflicts.</span></span> <span data-ttu-id="3517f-105">이러한 예약 프로세스의 목적은 대규모 모임 설정을 용이 하 게 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3517f-105">The purpose of such the scheduling process is to facilitate setting up large meetings.</span></span> <span data-ttu-id="3517f-106">이러한 접근 권한 값은 Lync Server 또는 Lync Server 클라이언트에서 직접 제공 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3517f-106">Such capability is not provided directly by Lync Server or Lync Server clients.</span></span> <span data-ttu-id="3517f-107">이러한 프로세스를 구현 하는 한 가지 방법은 가능한 경우 조직의 지원 팀의 티켓 시스템을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3517f-107">One way to implement such a process is to use your organization’s support team’s ticketing system, if available.</span></span>

<span data-ttu-id="3517f-108">대규모 모임 이끌이의 경우 대규모 모임 예약에는 다음 단계를 완료 하는 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3517f-108">For organizers of large meetings, scheduling a large meeting involves completing the following steps:</span></span>

1.  <span data-ttu-id="3517f-109">모임 이끌이 또는 대리인은 발표자 목록 외에도 예정 된 모임의 시간, 기간, 크기를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3517f-109">The meeting organizer or delegate determines the time, duration, and size of an upcoming meeting, in addition to the list of presenters.</span></span> <span data-ttu-id="3517f-110">예상 되는 모임 크기가 250 사용자를 초과 하거나 250 사용자 보다 적은 모임에 대 한 최상의 사용자 환경을 보장 하는 경우 이끌이 또는 대리인이 대용량 모임에 대 한 요청을 제출 합니다.</span><span class="sxs-lookup"><span data-stu-id="3517f-110">If the anticipated meeting size exceeds 250 users or to ensure the best user experience for a meeting of fewer than 250 users, the organizer or the delegate submits a request for a large meeting.</span></span>

2.  <span data-ttu-id="3517f-111">예약 직원은 요청한 날짜와 시간을 사용할 수 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3517f-111">The scheduling staff checks to see whether the requested date and time is available.</span></span> <span data-ttu-id="3517f-112">전용 풀에서 한 번에 하나의 대규모 모임만 지원 하기 때문에, 일정 관리 직원이 대용량 모임 일정을 검사 하 여 요청 된 날짜와 시간에 대해 예정 된 다른 모임이 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3517f-112">Since we support only a single large meeting on the dedicated pool at a time, the scheduling staff needs to check the large-meeting calendar to determine whether there is another meeting scheduled for the requested date and time.</span></span> <span data-ttu-id="3517f-113">요청한 시간을 사용할 수 있는 경우 직원이 모임 요청을 승인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3517f-113">If the requested time is available, the staff approves the meeting request.</span></span>

3.  <span data-ttu-id="3517f-114">요청이 승인 되는 경우, 예약 스태프 (전용 풀의 자격 증명 사용)는 Outlook을 사용 하 여 Lync 2013에 대 한 온라인 모임 추가 기능을 사용 하 여 전용 대용량 모임 풀에서 모임을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3517f-114">If the request is approved, the scheduling staff (using credentials on the dedicated pool) uses Online Meeting Add-in for Lync 2013 with Outlook to set up a meeting on the dedicated large-meeting pool.</span></span> <span data-ttu-id="3517f-115">모임에 참가 하는 데 사용 되는 URL은 승인 공지의 일부로 요청자에 게 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3517f-115">The URL to be used to join the meeting is provided to the requester as part of the approval notice.</span></span>

4.  <span data-ttu-id="3517f-116">모임 이끌이 또는 대리인이 Outlook을 사용 하 여 모임 초대에 모임 참가에 대 한 URL을 추가 하 여 예정 된 모임을 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="3517f-116">The meeting organizer or delegate uses Outlook to schedule the upcoming meeting, adding the URL for joining the meeting to the meeting invitation.</span></span> <span data-ttu-id="3517f-117">모임 이끌이 또는 대리인은 초대 하 고 모임 초대를 보낼 사용자를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3517f-117">The meeting organizer or delegate then specifies the users to be invited and sends out the meeting invitation.</span></span>
    
    <span data-ttu-id="3517f-118">다음 그림에서는 대규모 모임을 예약 하기 위한 일반적인 요청 및 승인 워크플로를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3517f-118">The following figure illustrates a typical request and approval workflow for scheduling large meetings.</span></span>
    
    <span data-ttu-id="3517f-119">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span><span class="sxs-lookup"><span data-stu-id="3517f-119">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span></span>  

</div>

<span> </span>

</div>

</div>

</div>

