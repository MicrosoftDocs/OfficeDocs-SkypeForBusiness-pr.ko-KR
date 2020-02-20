---
title: 'Lync Server 2013: 모임에 대 한 세부 정보 예약'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scheduling details
ms:assetid: 39ca6fff-2c15-4347-9f1f-6c8687a39a49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204823(v=OCS.15)
ms:contentKeyID: 48183910
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fa7186ed00ea2c42db392af72555bdbbbeeaaab
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scheduling-details-for-meetings-in-lync-server-2013"></a><span data-ttu-id="b5677-102">Lync Server 2013의 모임에 대 한 일정 세부 정보</span><span class="sxs-lookup"><span data-stu-id="b5677-102">Scheduling details for meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5677-103">_**마지막으로 수정 된 항목:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="b5677-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="b5677-104">요청을 처리하는 대규모 모임 지원 담당자는 요청된 시간에 다른 모임이 예약되어 있지 않은지 확인한 후에 대규모 모임 풀에서 모임을 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="b5677-104">After checking to ensure that no other meeting is scheduled at the requested time, the large meeting support staff that handles the request schedules the meeting on the large-meeting pool.</span></span> <span data-ttu-id="b5677-105">Lync Server 2013 클라이언트와 함께 설치 되는 Lync 용 온라인 모임 추가 기능을 사용 하 여 전용 대규모 모임 풀에서 Lync Server에 대해 사용 하도록 설정 된 사용자의 자격 증명을 사용 하 여이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5677-105">Use the Online Meeting Add-in for Lync that is installed with the Lync Server 2013 client to perform this task, using the credentials of a user enabled for Lync Server in the dedicated large-meeting pool.</span></span>

<span data-ttu-id="b5677-106">최적의 사용자 환경을 보장하려면 모임 이끌이의 요구에 적합한 적절한 모임 설정 및 액세스 수준을 사용하여 대규모 모임을 예약해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5677-106">To ensure the best user experience, it is important to schedule the large meeting with the right access levels and meeting settings that are appropriate to the meeting organizer’s needs.</span></span> <span data-ttu-id="b5677-107">Lync 모임 옵션에서 다음 일정 설정을 구성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b5677-107">We recommend the following scheduling settings configured in Lync Meeting options:</span></span>

  - <span data-ttu-id="b5677-108">전용 모임 공간을 다시 사용하는 대신 각각의 대규모 모임용으로 새 모임 공간을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b5677-108">Use a new meeting space for each large meeting instead of reusing the dedicated meeting space.</span></span>

  - <span data-ttu-id="b5677-109">모임 액세스 수준을 다음과 같이 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b5677-109">Specify the meeting access level as follows:</span></span>
    
      - <span data-ttu-id="b5677-p103">초대 대상자 중 한 명 이상이 조직 외부에 있으면 모임 액세스 유형을 **모두(제한 없음)** 로 설정합니다. 그러면 모임이 진행 중일 때 대규모 대기실을 관리할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b5677-p103">If at least one invitee is external to the organization, set the meeting access type to **Anyone (no restrictions**. This enables you to avoid having to manage a potentially large lobby when the meeting is in progress.</span></span>
    
      - <span data-ttu-id="b5677-112">내부 전용 모임의 경우에는 모임 액세스 유형을 **조직 구성원 모두**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b5677-112">If the meeting is an internal-only meeting, set the meeting access type to **Anyone from my organization**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b5677-113">모임 액세스 유형으로 <STRONG>내 회사에서 초대한 사용자</STRONG> 설정을 사용하는 경우 이끌이가 모든 사용자 전자 메일 주소를 초대 대상자 목록에 추가해야 하며 메일 그룹은 초대할 수 없으므로, 모임 액세스 유형을 이렇게 설정하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="b5677-113">Avoid setting the meeting access type to <STRONG>People I invite from my company</STRONG> because when you use this setting, organizers must add all user email addresses to the invitee list and you cannot invite a distribution group.</span></span><BR><span data-ttu-id="b5677-p104">모임 액세스 유형으로 <STRONG>나만, 모임 이끌이</STRONG> 설정을 사용하는 경우 발표자를 비롯한 모든 모임 참가자가 모임 실행 시 대기실에서 기다려야 하므로 모임 액세스 유형을 이렇게 설정하지 마십시오. 이 설정을 사용하는 경우에는 대규모 모임을 진행하는 사람이 대기실 명단을 지속적으로 모니터링하여 대기실에 있는 새 사용자를 허용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5677-p104">Avoid setting the meeting access type to <STRONG>Only me, the meeting organizer</STRONG> because this setting requires that every meeting participant, including presenters, must be put in the lobby at meeting run time. The person responsible for running the large meeting must then constantly monitor the lobby roster and admit new users who are in the lobby.</span></span>

        
        </div>

  - <span data-ttu-id="b5677-116">**발신자 바로 입장** 설정을 선택하여 전화를 통해 전화 접속하는 사용자가 모임에 자동으로 입장하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="b5677-116">Allow users who dial-in from phones to enter the meeting automatically by checking the **Callers get in directly** setting.</span></span>

  - <span data-ttu-id="b5677-117">다음 사용자를 명시적으로 초대합니다.</span><span class="sxs-lookup"><span data-stu-id="b5677-117">Explicitly invite the following users:</span></span>
    
      - <span data-ttu-id="b5677-118">모임 이끌이 및 대리인(요청자)</span><span class="sxs-lookup"><span data-stu-id="b5677-118">Meeting organizer and delegate (requester)</span></span>
    
      - <span data-ttu-id="b5677-119">모임 요청자가 제공하는 발표자 목록</span><span class="sxs-lookup"><span data-stu-id="b5677-119">The list of presenters provided by a meeting requester</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b5677-120">모임 액세스 유형을 <STRONG>내가 선택한 사용자</STRONG>로 설정하는 경우에는 대규모 모임의 각 참가자를 명시적으로 모임 초대 대상자로 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5677-120">If the meeting access type is set to <STRONG>People I choose</STRONG>, you need to explicitly add each participant of a large meeting as an invitee of the meeting.</span></span>

    
    </div>

  - <span data-ttu-id="b5677-p105">발표자 옵션을 자동 승격 값 중 하나로 설정하는 대신 발표자를 명시적으로 관리합니다. 다음과 같은 사용자를 발표자로 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5677-p105">Explicitly manage presenters, instead of setting the presenter option to one of the auto-promote values. Be sure to add the following users as presenters:</span></span>
    
      - <span data-ttu-id="b5677-123">모임 이끌이 및 대리인(요청자)</span><span class="sxs-lookup"><span data-stu-id="b5677-123">Meeting organizer and delegate (requester)</span></span>
    
      - <span data-ttu-id="b5677-124">대규모 모임 요청자가 제공하는 발표자 목록</span><span class="sxs-lookup"><span data-stu-id="b5677-124">The list of presenters provided by large meeting requesters</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b5677-p106">발표자를 명시적으로 관리하면 발표자 수를 제어할 수 있으므로 대규모 모임을 효율적으로 유지하는 데 충분하도록 발표자 수를 적게 제한할 수 있습니다. 대부분의 모임 참가자에게 참석자 역할이 지정되면 실수로 사용자들에게 프레젠테이션 제어권을 부여하거나, PowerPoint 프레젠테이션을 삭제하거나, 발표자를 음소거/음소거 해제하고 기타 이유로 모임을 중단할 가능성이 낮아집니다.</span><span class="sxs-lookup"><span data-stu-id="b5677-p106">By explicitly managing presenters, you can control the number of presenters, so that you can limit presenters to a small enough number to make it possible to have an effective large meeting. If the majority of meeting participants have the attendee role, it helps reduce the chance of people accidentally taking control of the presentation, deleting a PowerPoint presentation, muting/unmuting presenters, and other disruptions to the meeting.</span></span>

    
    </div>

  - <span data-ttu-id="b5677-127">**모든 참석자 음소거** 설정을 선택하여 발표자만 모임에 오디오를 브로드캐스트할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5677-127">Check the **Mute all attendees** setting to make sure that only presenters can broadcast audio into the meeting.</span></span>

  - <span data-ttu-id="b5677-128">**참석자의 비디오 차단**을 선택하여 발표자만 모임에 비디오를 브로드캐스트할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5677-128">Check the **Block attendees’ video** setting to make sure only presenters can broadcast video into the meeting.</span></span>

<span data-ttu-id="b5677-129">다음 그림에서는 Lync 용 온라인 모임 추가 기능에 대 한 권장 설정을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b5677-129">The following figure shows the recommended settings for the Online Meeting Add-in for Lync.</span></span>

<span data-ttu-id="b5677-130">![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")</span><span class="sxs-lookup"><span data-stu-id="b5677-130">![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

