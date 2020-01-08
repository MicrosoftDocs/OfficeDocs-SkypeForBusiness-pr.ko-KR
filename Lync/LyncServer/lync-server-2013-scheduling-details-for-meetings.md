---
title: 'Lync Server 2013: 모임 일정 세부 정보'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scheduling details
ms:assetid: 39ca6fff-2c15-4347-9f1f-6c8687a39a49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204823(v=OCS.15)
ms:contentKeyID: 48183910
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f027aac5372865bfb2803e19591dadaa1aca4805
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981267"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scheduling-details-for-meetings-in-lync-server-2013"></a><span data-ttu-id="eb815-102">Lync Server 2013의 모임에 대 한 일정 세부 정보</span><span class="sxs-lookup"><span data-stu-id="eb815-102">Scheduling details for meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb815-103">_**마지막으로 수정한 주제:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="eb815-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="eb815-104">요청한 시간에 다른 모임이 예약 되어 있지 않은지 확인 한 후, 요청을 처리 하는 대규모 모임 지원 직원이 대용량 모임 풀에서 모임을 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb815-104">After checking to ensure that no other meeting is scheduled at the requested time, the large meeting support staff that handles the request schedules the meeting on the large-meeting pool.</span></span> <span data-ttu-id="eb815-105">Lync Server 2013 클라이언트에 설치 된 Lync 용 온라인 모임 추가 기능을 사용 하 여 전용 대용량 모임 풀에서 Lync Server에 대해 사용 하도록 설정 된 사용자의 자격 증명을 사용 하 여이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb815-105">Use the Online Meeting Add-in for Lync that is installed with the Lync Server 2013 client to perform this task, using the credentials of a user enabled for Lync Server in the dedicated large-meeting pool.</span></span>

<span data-ttu-id="eb815-106">최상의 사용자 환경을 위해서는 모임 이끌이의 요구에 적합 한 적절 한 액세스 수준 및 모임 설정을 사용 하 여 대규모 모임을 예약 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb815-106">To ensure the best user experience, it is important to schedule the large meeting with the right access levels and meeting settings that are appropriate to the meeting organizer’s needs.</span></span> <span data-ttu-id="eb815-107">Lync 모임 옵션에서 다음 일정 설정을 구성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="eb815-107">We recommend the following scheduling settings configured in Lync Meeting options:</span></span>

  - <span data-ttu-id="eb815-108">전용 모임 공간을 다시 사용 하는 대신 각 대용량 모임에 대해 새 모임 공간을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb815-108">Use a new meeting space for each large meeting instead of reusing the dedicated meeting space.</span></span>

  - <span data-ttu-id="eb815-109">다음과 같이 모임 액세스 수준을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb815-109">Specify the meeting access level as follows:</span></span>
    
      - <span data-ttu-id="eb815-110">하나 이상의 초대 대 상자가 조직의 외부에 있는 경우 모임 액세스 형식을 **모든 사용자 (제한 없음)** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb815-110">If at least one invitee is external to the organization, set the meeting access type to **Anyone (no restrictions**.</span></span> <span data-ttu-id="eb815-111">이를 통해 모임이 진행 중일 때 잠재적으로 큰 로비를 관리 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb815-111">This enables you to avoid having to manage a potentially large lobby when the meeting is in progress.</span></span>
    
      - <span data-ttu-id="eb815-112">모임이 내부 전용 모임이 면 모임 액세스 형식을 **조직의 모든 사용자**에 게 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb815-112">If the meeting is an internal-only meeting, set the meeting access type to **Anyone from my organization**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="eb815-113">이 설정을 사용 하는 경우 이끌이는 초대 목록에 모든 사용자 전자 메일 주소를 추가 해야 하 고 메일 그룹을 초대할 수 없기 때문에 <STRONG>회사에서 초대한 사람</STRONG> 에 게 모임 액세스 형식을 설정 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="eb815-113">Avoid setting the meeting access type to <STRONG>People I invite from my company</STRONG> because when you use this setting, organizers must add all user email addresses to the invitee list and you cannot invite a distribution group.</span></span><BR><span data-ttu-id="eb815-114">모임 액세스 형식을 <STRONG>나</STRONG> 자신만으로 설정 하지 마세요 .이 설정을 사용 하려면 발표자를 비롯 한 모든 모임 참가자가 모임 런타임에 대기실에 놓아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb815-114">Avoid setting the meeting access type to <STRONG>Only me, the meeting organizer</STRONG> because this setting requires that every meeting participant, including presenters, must be put in the lobby at meeting run time.</span></span> <span data-ttu-id="eb815-115">대용량 모임 실행을 담당 하는 사람은 로비 명단을 지속적으로 모니터링 하 고 대기실에 있는 새 사용자를 참가 시켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb815-115">The person responsible for running the large meeting must then constantly monitor the lobby roster and admit new users who are in the lobby.</span></span>

        
        </div>

  - <span data-ttu-id="eb815-116">전화 접속을 하는 사용자가 전화를 건 사람에 게 **직접 액세스** 를 확인 하 여 모임에 자동으로 들어갈 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb815-116">Allow users who dial-in from phones to enter the meeting automatically by checking the **Callers get in directly** setting.</span></span>

  - <span data-ttu-id="eb815-117">다음 사용자를 명시적으로 초대:</span><span class="sxs-lookup"><span data-stu-id="eb815-117">Explicitly invite the following users:</span></span>
    
      - <span data-ttu-id="eb815-118">모임 이끌이 및 대리인 (요청자)</span><span class="sxs-lookup"><span data-stu-id="eb815-118">Meeting organizer and delegate (requester)</span></span>
    
      - <span data-ttu-id="eb815-119">모임 요청 자가 제공 하는 발표자 목록</span><span class="sxs-lookup"><span data-stu-id="eb815-119">The list of presenters provided by a meeting requester</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eb815-120">모임 액세스 형식이 <STRONG>선택한 사람</STRONG>으로 설정 된 경우에는 대규모 모임의 각 참가자를 모임의 초대 대 상자를 명시적으로 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb815-120">If the meeting access type is set to <STRONG>People I choose</STRONG>, you need to explicitly add each participant of a large meeting as an invitee of the meeting.</span></span>

    
    </div>

  - <span data-ttu-id="eb815-121">발표자 옵션을 자동 승격 값 중 하나로 설정 하는 대신 발표자를 명시적으로 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb815-121">Explicitly manage presenters, instead of setting the presenter option to one of the auto-promote values.</span></span> <span data-ttu-id="eb815-122">다음 사용자를 발표자로 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb815-122">Be sure to add the following users as presenters:</span></span>
    
      - <span data-ttu-id="eb815-123">모임 이끌이 및 대리인 (요청자)</span><span class="sxs-lookup"><span data-stu-id="eb815-123">Meeting organizer and delegate (requester)</span></span>
    
      - <span data-ttu-id="eb815-124">대규모 모임 요청자에서 제공 하는 발표자 목록</span><span class="sxs-lookup"><span data-stu-id="eb815-124">The list of presenters provided by large meeting requesters</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eb815-125">발표자를 명시적으로 관리 하 여 발표자 수를 제어 하 여 효율적인 대규모 모임이 가능 하도록 하기에 충분 한 수의 번호로 발표자를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb815-125">By explicitly managing presenters, you can control the number of presenters, so that you can limit presenters to a small enough number to make it possible to have an effective large meeting.</span></span> <span data-ttu-id="eb815-126">대부분의 모임 참가자가 참석자 역할을 보유 하 고 있는 경우 사용자가 프레젠테이션을 제어할 수 있는 기회, PowerPoint 프레젠테이션 삭제, 음소거/음소거 해제, 모임에 대 한 기타 작업 중단을 줄이는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb815-126">If the majority of meeting participants have the attendee role, it helps reduce the chance of people accidentally taking control of the presentation, deleting a PowerPoint presentation, muting/unmuting presenters, and other disruptions to the meeting.</span></span>

    
    </div>

  - <span data-ttu-id="eb815-127">**모든 참석자 음소거** 설정을 확인 하 여 발표자만 오디오를 모임에 브로드캐스트할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb815-127">Check the **Mute all attendees** setting to make sure that only presenters can broadcast audio into the meeting.</span></span>

  - <span data-ttu-id="eb815-128">참석자의 **비디오** 설정을 확인 하 여 발표자만 모임에 비디오를 브로드캐스트할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb815-128">Check the **Block attendees’ video** setting to make sure only presenters can broadcast video into the meeting.</span></span>

<span data-ttu-id="eb815-129">다음 그림에는 Lync 용 온라인 모임 추가 기능에 대 한 권장 설정이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb815-129">The following figure shows the recommended settings for the Online Meeting Add-in for Lync.</span></span>

<span data-ttu-id="eb815-130">![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")</span><span class="sxs-lookup"><span data-stu-id="eb815-130">![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

