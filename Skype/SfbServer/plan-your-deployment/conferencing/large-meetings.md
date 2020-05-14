---
title: 비즈니스용 Skype 서버에서 대규모 모임 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 21507e18-bd79-4019-9c3a-0867fccaa3b4
description: '요약: 비즈니스용 Skype 서버에서 대규모 모임을 구현 및 관리 하기 위한 모범 사례에 대해 자세히 알아보려면이 항목을 읽어 보십시오.'
ms.openlocfilehash: acb0dd1dbd0efe93b985ed2f9e143ef1538ecb86
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221258"
---
# <a name="plan-for-large-meetings-in-skype-for-business-server"></a><span data-ttu-id="29be5-103">비즈니스용 Skype 서버에서 대규모 모임 계획</span><span class="sxs-lookup"><span data-stu-id="29be5-103">Plan for large meetings in Skype for Business Server</span></span>
 
<span data-ttu-id="29be5-104">**요약:** 비즈니스용 Skype 서버에서 대규모 모임을 구현 및 관리 하기 위한 모범 사례에 대해 자세히 알아보려면이 항목을 읽어 보십시오.</span><span class="sxs-lookup"><span data-stu-id="29be5-104">**Summary:** Read this topic to learn about best practices for implementing and managing large meetings in Skype for Business Server.</span></span>
  
<span data-ttu-id="29be5-105">비즈니스용 Skype 서버가 지원할 수 있는 모임 크기는 공유 풀에 있는 250 명의 참가자에서 전용 풀의 참가자 1000까지 회의를 호스트 하는지 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-105">The size of meetings that Skype for Business Server can support depends on whether conferencing is hosted on a shared or dedicated pool: anywhere from 250 participants on a shared pool to 1000 participants on a dedicated pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="29be5-106">이 항목에서는 비즈니스용 Skype 서버에서 지원 되는 대규모 모임에 대 한 최상의 방법을 중점적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-106">This topic focuses on best practices for large meetings supported by Skype for Business Server.</span></span> <span data-ttu-id="29be5-107">조직에서 더 큰 모임 기능을 사용 해야 하는 경우에는 Microsoft 365 및 Office 365에 속하는 새로운 온라인 서비스인 Skype 모임 브로드캐스트를 활용 하는 하이브리드 환경을 구현 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-107">If your organization requires larger meeting capabilities, you should consider implementing a hybrid environment that takes advantage of Skype Meeting Broadcast, a new online service that is part of Microsoft 365 and Office 365.</span></span> 

> [!NOTE]
> <span data-ttu-id="29be5-108">사용자는 Skype 모임 브로드캐스트를 사용 하 여 최대 1만 명의 참가자로 모임을 호스트 하 고 브로드캐스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-108">Skype Meeting Broadcast enables users to host and broadcast meetings to large online audiences of up to 10,000 participants.</span></span> <span data-ttu-id="29be5-109">Skype 모임 브로드캐스트를 사용 하려면 프로덕션 Microsoft 365 또는 Office 365 조 직을 사용 하 여 하이브리드 설치에서 비즈니스용 Skype 서버가 이미 구성 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-109">The use of Skype Meeting Broadcast requires that Skype for Business Server already be configured in a hybrid setup with a production Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="29be5-110">모든 사용자는 필수 구성 요소로 온라인 테 넌 트를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-110">All users must have an online tenant established as a prerequisite.</span></span> <span data-ttu-id="29be5-111">Skype 모임 브로드캐스트를 활용할 수 있는 하이브리드 솔루션을 배포 하려는 경우 skype 모임 [브로드캐스트 란?](https://go.microsoft.com/fwlink/?LinkId=617071) 를 참조 하 고 [skype 모임 브로드캐스트를 위한 온-프레미스 배포를 구성](../../deploy/configure-skype-meeting-broadcast.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-111">If you are interested in deploying a hybrid solution that can take advantage of Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Configure your on-premises deployment for Skype Meeting Broadcast](../../deploy/configure-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="29be5-112">일반적으로 큰 모임에는 다음과 같은 특징이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-112">Large meetings typically have the following characteristics:</span></span>
  
- <span data-ttu-id="29be5-113">모임 형식이 일대다 프레젠테이션입니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-113">The meeting format is a one-to-many presentation.</span></span>
    
- <span data-ttu-id="29be5-114">한 명 또는 소수의 사용자가 발표자이고 그외 모든 사람은 참석자로만 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-114">One or a few users are presenters, and everyone else participates only as attendees.</span></span>
    
- <span data-ttu-id="29be5-115">PowerPoint 프레젠테이션 공유가 기본 데이터 공동 작업 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-115">PowerPoint presentation sharing is the main data collaboration activity.</span></span>
    
- <span data-ttu-id="29be5-116">오디오가 필요하고 비디오를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-116">Audio is required and video may also be used.</span></span>
    
- <span data-ttu-id="29be5-117">일반적으로 모임 이끌이 또는 이끌이를 위한 보조자 인 전용 사람은 모임을 미리 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-117">A dedicated person, generally either the meeting organizer or an assistant to the organizer, sets up the meeting well in advance.</span></span>
    
- <span data-ttu-id="29be5-118">전담 직원(발표자가 아님)이 온라인 모임에 연결하고, 오디오, 비디오 및 슬라이드 공유가 작동하는지 확인하고, 대기실 및 사용자 역할을 관리하고, 참가자를 음소거하거나 음소거를 해제하고, 질문을 받고, 기록을 관리하는 등 모임을 적절하게 운영합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-118">Dedicated staff (not the presenters) runs the meeting, including connecting to an online meeting, verifying that audio, video, and slide sharing work, managing lobby and user roles, muting and unmuting participants, taking questions, and managing recordings, as appropriate.</span></span>
    
<span data-ttu-id="29be5-119">사용자가 모임을 예약 하면 비즈니스용 Skype 서버가 회의 데이터베이스에서 회의 데이터를 저장 하는 레코드를 만들며 예약 된 모임에 대 한 하드웨어 리소스는 미리 예약 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-119">When a user schedules a meeting, Skype for Business Server creates a record in the conferencing database, which stores conferencing data, but does not reserve any hardware resources for the scheduled meeting ahead of time.</span></span> <span data-ttu-id="29be5-120">대신, 비즈니스용 Skype 서버에는 풀의 모든 프런트 엔드 서버에서 분산을 동일 하 게 배포 하는 방식으로 프런트 엔드 서버에서 회의 리소스를 동적으로 할당 하는 부하 분산 논리가 기본적으로 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-120">Instead, Skype for Business Server has built-in load balancing logic to dynamically allocate conferencing resources on Front End Servers in a way that distributes loads equally across all Front End Servers in the pool.</span></span> <span data-ttu-id="29be5-121">이는 하드웨어 리소스를 효과적으로 프로 비전 하 고 사용 하지만 매우 큰 회의를 지원 하도록 적절 하 게 계획 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-121">This effectively provisions and uses hardware resources, but it is important that you plan appropriately to support very large meetings.</span></span> 
  
<span data-ttu-id="29be5-122">예를 들어 비즈니스용 Skype 서버 풀이 최상위 용량에 근접 하 게 실행 되는 경우 각 프런트 엔드 서버는 약 125의 평균 크기 모임을 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-122">For example, when a Skype for Business Server pool is running close to its top capacity, each Front End Server might host approximately 125 average-size meetings.</span></span> <span data-ttu-id="29be5-123">다른 소규모 모임을 추가 하는 것은 문제가 되지 않지만, 1000 사용자에 게 모임을 추가 하는 것은 프런트 엔드 서버가 다른 125 모임과 동시에 이러한 대규모 모임을 지원 하지 못할 수 있기 때문에 문제가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-123">Adding another small meeting would not be a problem, but adding a meeting for 1000 users would be a problem because the Front End Servers would probably not be able to support such a large meeting at the same time as the other 125 meetings.</span></span>
  
<span data-ttu-id="29be5-124">최대 1000 명의 참가자에 게 대규모 모임을 지원 하려면 공유 하드웨어 모델과 비 예약 모델에 관련 된 문제를 해결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-124">Supporting large meetings of up to 1000 participants requires addressing the issues related to both the shared hardware model and the no-reservation model.</span></span> <span data-ttu-id="29be5-125">일반적으로는 다음 섹션에서 설명 하는 것 처럼 전용 풀을 계획 하 고 모범 사례를 따르는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-125">In general, you need to plan for a dedicated pool and follow best practices as described in the following sections.</span></span> 
  
## <a name="plan-for-a-dedicated-pool"></a><span data-ttu-id="29be5-126">전용 풀 계획</span><span class="sxs-lookup"><span data-stu-id="29be5-126">Plan for a dedicated pool</span></span>

<span data-ttu-id="29be5-127">조직에서 250 명 이상의 참가자가 참석 해야 하는 경우에는 부하를 지원 하기 위한 전용 풀을 계획 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-127">If your organization requires meetings with greater than 250 participants, you need to plan for a dedicated pool to support the load.</span></span> 
  
<span data-ttu-id="29be5-128">최대 1000 명의 모임에 대 한 충분 한 CPU 및 메모리 리소스를 확보 하려면 호스팅 프런트 엔드 서버에서 다른 IM (인스턴트 메시징) 및 현재 상태 또는 Enterprise Voice 작업을 호스트 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-128">To have sufficient CPU and memory resources for meetings of up to 1000 users, the hosting Front End Servers should not host any other instant messaging (IM) and presence or Enterprise Voice workloads.</span></span> <span data-ttu-id="29be5-129">또한 서버는 다른 모임의 크기에 관계 없이 다른 모임을 호스트 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-129">The servers should also not host any other meetings, regardless of the size of the other meetings.</span></span> <span data-ttu-id="29be5-130">최대 1000 명의 사용자에 대 한 모임을 호스트 하려면 대규모 회의 호스팅 전용으로 사용할 별도의 비즈니스용 Skype 서버 풀을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-130">To host meetings of up to 1000 users, you need to set up a separate Skype for Business Server pool that is dedicated to hosting large meetings.</span></span>
  
<span data-ttu-id="29be5-131">대규모 모임 호스팅 전용 비즈니스용 Skype 서버 풀은 최대 1000 명의 모임을 동시에 호스팅해야 하므로, 모임 시간은 대역 외 예약 프로세스를 통해 미리 예약 해야 프런트 엔드 서버에서 전용으로 지원을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-131">A Skype for Business Server pool that is dedicated to hosting large meetings should host one and only one meeting of up to 1000 users at the same time, so meeting times need to be reserved in advance via an out of band scheduling process to ensure dedicated support from the Front End Servers.</span></span> <span data-ttu-id="29be5-132">두 개 이상의 대규모 모임을 동시에 지원 하려면 여러 전용 대규모 모임 풀을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-132">To support more than one large meeting at the same time, you should set up multiple dedicated large-meeting pools.</span></span>
  
<span data-ttu-id="29be5-133">하드웨어 및 소프트웨어 요구 사항에 대 한 자세한 내용과 대규모 모임을 지 원하는 토폴로지를 계획 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 회의에 대 한 하드웨어 및 소프트웨어 요구 사항](hardware-and-software-requirements.md) 및 비즈니스용 [skype 서버에 대 한 회의 토폴로지 계획](conferencing-topology.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="29be5-133">For more information about hardware and software requirements, and planning a topology that supports large meetings, see [Hardware and software requirements for conferencing in Skype for Business Server](hardware-and-software-requirements.md) and [Plan your conferencing topology for Skype for Business Server](conferencing-topology.md).</span></span>
  
## <a name="implement-best-practices-for-large-meetings"></a><span data-ttu-id="29be5-134">대규모 모임에 대 한 모범 사례 구현</span><span class="sxs-lookup"><span data-stu-id="29be5-134">Implement best practices for large meetings</span></span>

<span data-ttu-id="29be5-135">대규모 모임에 대 한 전용 풀을 설정한 후에는 풀에서 호스트 되는 대규모 모임이 최상의 사용자 환경을 제공 하도록 하기 위한 단계를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-135">After setting up a dedicated pool for large meetings, you can take steps to help ensure that large meetings hosted in the pool provide the best user experience.</span></span> <span data-ttu-id="29be5-136">다음 섹션에서는 대규모 모임을 관리 하기 위한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-136">The following sections provide guidelines for managing large meetings:</span></span>
  
- <span data-ttu-id="29be5-137">전용 모임 이끌이 만들기</span><span class="sxs-lookup"><span data-stu-id="29be5-137">Create dedicated meeting organizers</span></span>
    
- <span data-ttu-id="29be5-138">전용 중재자 만들기</span><span class="sxs-lookup"><span data-stu-id="29be5-138">Create dedicated moderators</span></span>
    
- <span data-ttu-id="29be5-139">대규모 모임에 대 한 별도 일정 유지 관리</span><span class="sxs-lookup"><span data-stu-id="29be5-139">Maintain a separate calendar of large meetings</span></span>
    
- <span data-ttu-id="29be5-140">대규모 모임 예약 프로세스 구현</span><span class="sxs-lookup"><span data-stu-id="29be5-140">Implement a large-meeting scheduling process</span></span>
    
- <span data-ttu-id="29be5-141">적절 한 일정 세부 정보 지정</span><span class="sxs-lookup"><span data-stu-id="29be5-141">Specify appropriate scheduling details</span></span>
    
- <span data-ttu-id="29be5-142">대규모 모임에 대 한 회의 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="29be5-142">Create a conferencing policy for large meetings</span></span>
    
### <a name="create-dedicated-meeting-organizers"></a><span data-ttu-id="29be5-143">전용 모임 이끌이 만들기</span><span class="sxs-lookup"><span data-stu-id="29be5-143">Create dedicated meeting organizers</span></span>

<span data-ttu-id="29be5-144">대규모 모임 풀에서 실시간 통신 트래픽을 최소화 하기 위해 Microsoft는 비즈니스용 Skype 클라이언트를 사용 하 여 정기적으로 로그인 하 고 인스턴트 메시징 (IM), 현재 상태, 회의 및 음성 세션에 참가 하는 사용자를 호스팅하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-144">To minimize the real-time communications traffic in the large-meeting pool, Microsoft does not recommend hosting users who regularly sign in using Skype for Business clients and participate in instant messaging (IM), presence, conferencing, and voice sessions.</span></span> <span data-ttu-id="29be5-145">대신 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-145">Instead, do one of the following:</span></span>
  
- <span data-ttu-id="29be5-146">대규모 모임 예약에만 하나 이상의 전용 사용자 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="29be5-146">Create one or more dedicated user accounts just for scheduling large meetings</span></span>
    
- <span data-ttu-id="29be5-147">집 대규모 모임 풀에서 대규모 모임 일정을 담당 하는 직원의 사용자 계정</span><span class="sxs-lookup"><span data-stu-id="29be5-147">Home the user accounts of the staff responsible for scheduling large meetings on a large-meeting pool</span></span>
    
### <a name="create-dedicated-moderators"></a><span data-ttu-id="29be5-148">전용 중재자 만들기</span><span class="sxs-lookup"><span data-stu-id="29be5-148">Create dedicated moderators</span></span>

<span data-ttu-id="29be5-149">회의에 포함 된 사용자를 수백 명까지 사용 하는 경우에는 대규모 모임의 온라인 세션을 전담 전용으로 유지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-149">With several hundred to a thousand users in a meeting, it is a good practice to have a dedicated person moderate the online session of a large meeting.</span></span> <span data-ttu-id="29be5-150">이 전용 사용자는 모임 이끌이의 대리인 이거나 조직의 대규모 모임 지원 담당자의 구성원 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-150">This dedicated person can be a delegate of the meeting organizer or a member of the organization's large-meeting support staff.</span></span> <span data-ttu-id="29be5-151">전담 모임 중재자를 모임이 예약된 시간에 발표자로 추가해야 하지만, 모임이 진행되는 동안에는 온라인 모임 참가자를 발표자 역할로 승격시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-151">It is important to add the dedicated meeting moderator as a presenter at the time that the meeting is scheduled, although it is possible to promote an online meeting attendee to the presenter role while the meeting is in progress.</span></span>
  
<span data-ttu-id="29be5-152">모임 중재자는 비즈니스용 Skype 클라이언트의 모든 발표자 기능을 사용 하 여 대규모 모임을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-152">The meeting moderator can use all presenter functionalities of Skype for Business clients to manage the large meeting.</span></span> <span data-ttu-id="29be5-153">이러한 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-153">These functionalities include:</span></span>
  
- <span data-ttu-id="29be5-154">로비에서 로비 및 입장 사용자 거부</span><span class="sxs-lookup"><span data-stu-id="29be5-154">Monitoring the lobby and admitting or rejecting users in the lobby</span></span>
    
- <span data-ttu-id="29be5-155">모임에 참석 하지 않아야 하는 모임에서 사용자 제거</span><span class="sxs-lookup"><span data-stu-id="29be5-155">Removing any users from the meeting who should not be in the meeting</span></span>
    
- <span data-ttu-id="29be5-156">모임 액세스 유형 변경</span><span class="sxs-lookup"><span data-stu-id="29be5-156">Changing meeting access types</span></span>
    
- <span data-ttu-id="29be5-157">참가자 역할 변경</span><span class="sxs-lookup"><span data-stu-id="29be5-157">Changing participant roles</span></span>
    
- <span data-ttu-id="29be5-158">모임 중에 끌어서 놓기 기능, 휴대폰 전화 걸기 또는 전자 메일을 사용 하 여 추가 참가자 초대</span><span class="sxs-lookup"><span data-stu-id="29be5-158">Inviting additional participants during the meeting using drag and drop functionality, phone dial out, or email</span></span>
    
- <span data-ttu-id="29be5-159">대상 그룹 또는 개별 사용자 음소거 해제 및 음소거 해제</span><span class="sxs-lookup"><span data-stu-id="29be5-159">Muting and unmuting the audience or individual users</span></span>
    
- <span data-ttu-id="29be5-160">콘텐츠 업로드, 콘텐츠 삭제 및 액티브 콘텐츠 전환 등 모임 콘텐츠 관리</span><span class="sxs-lookup"><span data-stu-id="29be5-160">Managing meeting content, including uploading content, deleting content, and switching active content</span></span>

    
### <a name="maintain-a-separate-calendar"></a><span data-ttu-id="29be5-161">별도의 일정 유지 관리</span><span class="sxs-lookup"><span data-stu-id="29be5-161">Maintain a separate calendar</span></span>

<span data-ttu-id="29be5-162">대규모 모임 풀 마다 해당 풀에 예약 된 대규모 모임의 개별 일정을 유지 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-162">For each large-meeting pool, you should maintain a separate calendar of large meetings scheduled on that pool.</span></span> <span data-ttu-id="29be5-163">예를 들어 대규모 모임 풀에 단일 사용자 계정을 홈으로 설정 하 고 비즈니스용 Skype 용 Exchange 및 온라인 모임 추가 기능과 Outlook을 함께 사용 하 여 별도의 일정을 유지 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-163">For example, you can home a single user account on the large-meeting pool and use Outlook with Exchange and Online Meeting Add-in for Skype for Business to maintain a separate calendar.</span></span> <span data-ttu-id="29be5-164">지원 부서가 대규모 모임을 만들 수 있도록 설정하기 위해 여러 사용자 계정을 사용할 경우 해당 지원 부서의 구성원이 만든 모든 대규모 모임을 집계하는 별도의 일정을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-164">If you use multiple user accounts to enable a support staff to create large meetings, you can set up a separate calendar that aggregates all large meetings created by the members of the support staff.</span></span> 
  
<span data-ttu-id="29be5-165">별도의 대규모 모임 일정을 유지 관리하면 충돌을 방지하고 항상 하나의 대규모 모임만 활성화된 상태로 유지되도록 보장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-165">Maintaining a separate large meeting calendar helps to prevent conflicts and ensure that only one large meeting is active at any time.</span></span>
  
### <a name="implement-a-scheduling-process"></a><span data-ttu-id="29be5-166">일정 관리 프로세스 구현</span><span class="sxs-lookup"><span data-stu-id="29be5-166">Implement a scheduling process</span></span>

<span data-ttu-id="29be5-167">전용 대규모 모임 풀에서는 한 번에 하나의 대규모 모임이 지원 되므로 대규모 모임을 간편 하 게 설정 하 고 충돌을 방지 하기 위해 대규모 모임 예약 프로세스를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-167">Because only one large meeting at a time is supported on the dedicated large meeting pool, you should implement a large meeting scheduling process to facilitate setting up large meetings and help prevent conflicts.</span></span> <span data-ttu-id="29be5-168">이러한 기능은 비즈니스용 Skype 서버 또는 비즈니스용 Skype 클라이언트에서 직접 제공 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-168">Such capability is not provided directly by Skype for Business Server or Skype for Business clients.</span></span> <span data-ttu-id="29be5-169">이러한 프로세스를 구현 하는 한 가지 방법은 가능한 경우 조직의 지원 팀 티켓 시스템을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-169">One way to implement such a process is to use your organization's support team's ticketing system, if available.</span></span>
  
<span data-ttu-id="29be5-170">대규모 모임 일정을 세울 때는 다음 단계를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-170">Scheduling a large meeting involves completing the following steps:</span></span>
  
- <span data-ttu-id="29be5-p114">모임 이끌이나 대리자가 예정된 모임의 시간, 기간 및 규모와 발표자 목록을 결정합니다. 또한 예상된 모임 규모가 250명을 초과하거나 250명 미만의 모임을 위한 최상의 사용자 환경을 유지하려는 경우 대규모 모임 요청을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-p114">The meeting organizer or delegate determines the time, duration, and size of an upcoming meeting, in addition to the list of presenters. If the anticipated meeting size exceeds 250 users or to ensure the best user experience for a meeting of fewer than 250 users, the organizer or the delegate submits a request for a large meeting.</span></span>
    
- <span data-ttu-id="29be5-p115">예약 직원은 요청된 날짜와 시간이 예약 가능한지 확인합니다. 전용 풀에서 한 번에 하나의 대규모 모임만 지원되므로 예약 직원은 요청한 날짜 및 시간에 예약된 다른 모임이 있는지 알아보기 위해 대규모 모음 일정을 확인해야 합니다. 요청한 시간이 예약 가능하면 직원은 모임 요청을 승인합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-p115">The scheduling staff checks to see whether the requested date and time is available. Since we support only a single large meeting on the dedicated pool at a time, the scheduling staff needs to check the large-meeting calendar to determine whether there is another meeting scheduled for the requested date and time. If the requested time is available, the staff approves the meeting request.</span></span>
    
- <span data-ttu-id="29be5-176">요청이 승인 되 면 예약 직원 (전용 풀에서 자격 증명 사용)은 Outlook을 사용 하 여 비즈니스용 Skype에 대 한 온라인 모임 추가 기능을 사용 하 여 전용 대규모 모임 풀에서 모임을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-176">If the request is approved, the scheduling staff (using credentials on the dedicated pool) uses Online Meeting Add-in for Skype for Business with Outlook to set up a meeting on the dedicated large-meeting pool.</span></span> <span data-ttu-id="29be5-177">모임에 참가하는 데 사용될 URL은 승인 알림의 일부로 요청자에게 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-177">The URL to be used to join the meeting is provided to the requester as part of the approval notice.</span></span>
    
- <span data-ttu-id="29be5-178">모임 이끌이 또는 대리인은 Outlook을 사용 하 여 모임 초대에 모임에 참가 하는 데 사용할 수 있는 URL을 추가 하 고 예정 된 모임을 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-178">The meeting organizer or delegate uses Outlook to schedule the upcoming meeting, adding the URL for joining the meeting to the meeting invitation.</span></span> <span data-ttu-id="29be5-179">그런 다음 초대할 사용자를 지정하여 모임 초대를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-179">The meeting organizer or delegate then specifies the users to be invited and sends out the meeting invitation.</span></span>
    
### <a name="specify-appropriate-scheduling-details"></a><span data-ttu-id="29be5-180">적절 한 일정 세부 정보 지정</span><span class="sxs-lookup"><span data-stu-id="29be5-180">Specify appropriate scheduling details</span></span>

<span data-ttu-id="29be5-181">요청을 처리하는 대규모 모임 지원 담당자는 요청된 시간에 다른 모임이 예약되어 있지 않은지 확인한 후에 대규모 모임 풀에서 모임을 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-181">After checking to ensure that no other meeting is scheduled at the requested time, the large meeting support staff that handles the request schedules the meeting on the large-meeting pool.</span></span> 
  
<span data-ttu-id="29be5-182">최상의 사용자 환경을 보장 하기 위해서는 모임 이끌이의 요구에 적합 한 적절 한 액세스 수준 및 모임 설정을 사용 하 여 대규모 모임을 예약 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-182">To ensure the best user experience, it is important to schedule the large meeting with the right access levels and meeting settings that are appropriate to the meeting organizer's needs.</span></span> <span data-ttu-id="29be5-183">비즈니스용 Skype 모임 옵션에서 다음 일정 설정을 구성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-183">Consider the following scheduling settings configured in Skype for Business Meeting options:</span></span>
  
- <span data-ttu-id="29be5-184">전용 모임 공간을 다시 사용하는 대신 각각의 대규모 모임용으로 새 모임 공간을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-184">Use a new meeting space for each large meeting instead of reusing the dedicated meeting space.</span></span> 
    
- <span data-ttu-id="29be5-185">모임 액세스 수준을 다음과 같이 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-185">Specify the meeting access level as follows:</span></span>
    
  - <span data-ttu-id="29be5-186">하나 이상의 초대 대 상자가 조직 외부에 있는 경우에는 모임 액세스 유형을 **모든 사람 (제한 없음)** 으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-186">If at least one invitee is external to the organization, set the meeting access type to **Anyone (no restrictions)**.</span></span> <span data-ttu-id="29be5-187">그러면 모임이 진행 중일 때 대규모 대기실을 관리할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-187">This enables you to avoid having to manage a potentially large lobby when the meeting is in progress.</span></span>
    
  - <span data-ttu-id="29be5-188">내부 전용 모임의 경우에는 모임 액세스 유형을 **조직 구성원 모두**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-188">If the meeting is an internal-only meeting, set the meeting access type to **Anyone from my organization**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="29be5-189">모임 액세스 유형으로 **내 회사에서 초대한 사용자** 설정을 사용하는 경우 이끌이가 모든 사용자 전자 메일 주소를 초대 대상자 목록에 추가해야 하며 메일 그룹은 초대할 수 없으므로, 모임 액세스 유형을 이렇게 설정하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="29be5-189">Avoid setting the meeting access type to **People I invite from my company** because when you use this setting, organizers must add all user email addresses to the invitee list and you cannot invite a distribution group.</span></span> <span data-ttu-id="29be5-190">모임 액세스 유형으로 **나만, 모임 이끌이** 설정을 사용하는 경우 발표자를 비롯한 모든 모임 참가자가 모임 실행 시 대기실에서 기다려야 하므로 모임 액세스 유형을 이렇게 설정하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="29be5-190">Avoid setting the meeting access type to **Only me, the meeting organizer** because this setting requires that every meeting participant, including presenters, must be put in the lobby at meeting run time.</span></span> <span data-ttu-id="29be5-191">이 설정을 사용하는 경우에는 대규모 모임을 진행하는 사람이 대기실 명단을 지속적으로 모니터링하여 대기실에 있는 새 사용자를 허용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-191">The person responsible for running the large meeting must then constantly monitor the lobby roster and admit new users who are in the lobby.</span></span>
  
- <span data-ttu-id="29be5-192">**발신자 바로 입장** 설정을 선택하여 전화를 통해 전화 접속하는 사용자가 모임에 자동으로 입장하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-192">Allow users who dial-in from phones to enter the meeting automatically by checking the **Callers get in directly** setting.</span></span>
    
- <span data-ttu-id="29be5-193">다음 사용자를 명시적으로 초대합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-193">Explicitly invite the following users:</span></span>
    
  - <span data-ttu-id="29be5-194">모임 이끌이 및 대리인(요청자)</span><span class="sxs-lookup"><span data-stu-id="29be5-194">Meeting organizer and delegate (requester)</span></span>
    
  - <span data-ttu-id="29be5-195">모임 요청자가 제공하는 발표자 목록</span><span class="sxs-lookup"><span data-stu-id="29be5-195">The list of presenters provided by a meeting requester</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="29be5-196">모임 액세스 유형을 **내가 선택한 사용자**로 설정하는 경우에는 대규모 모임의 각 참가자를 명시적으로 모임 초대 대상자로 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-196">If the meeting access type is set to **People I choose**, you need to explicitly add each participant of a large meeting as an invitee of the meeting.</span></span> 
  
- <span data-ttu-id="29be5-p121">발표자 옵션을 자동 승격 값 중 하나로 설정하는 대신 발표자를 명시적으로 관리합니다. 다음과 같은 사용자를 발표자로 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-p121">Explicitly manage presenters, instead of setting the presenter option to one of the auto-promote values. Be sure to add the following users as presenters:</span></span>
    
  - <span data-ttu-id="29be5-199">모임 이끌이 및 대리인(요청자)</span><span class="sxs-lookup"><span data-stu-id="29be5-199">Meeting organizer and delegate (requester)</span></span>
    
  - <span data-ttu-id="29be5-200">대규모 모임 요청자가 제공하는 발표자 목록</span><span class="sxs-lookup"><span data-stu-id="29be5-200">The list of presenters provided by large meeting requesters</span></span>
    
    <span data-ttu-id="29be5-201">명시적으로 발표자를 관리 하면 발표자를 충분히 작은 수로 제한 하 여 효과적인 대규모 모임을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-201">By explicitly managing presenters, you can limit presenters to a small enough number to make it possible to have an effective large meeting.</span></span> <span data-ttu-id="29be5-202">대부분의 모임 참가자에게 참석자 역할이 지정되면 실수로 사용자들에게 프레젠테이션 제어권을 부여하거나, PowerPoint 프레젠테이션을 삭제하거나, 발표자를 음소거/음소거 해제하고 기타 이유로 모임을 중단할 가능성이 낮아집니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-202">If the majority of meeting participants have the attendee role, it helps reduce the chance of people accidentally taking control of the presentation, deleting a PowerPoint presentation, muting/unmuting presenters, and other disruptions to the meeting.</span></span> 
    
- <span data-ttu-id="29be5-203">**모든 참석자 음소거** 설정을 선택하여 발표자만 모임에 오디오를 브로드캐스트할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-203">Check the **Mute all attendees** setting to make sure that only presenters can broadcast audio into the meeting.</span></span>
    
- <span data-ttu-id="29be5-204">참석자의 **비디오 차단** 설정을 확인 하 여 발표자만 모임에 비디오를 브로드캐스트할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-204">Check the **Block attendees' video** setting to make sure only presenters can broadcast video into the meeting.</span></span>
    
### <a name="create-a-conferencing-policy"></a><span data-ttu-id="29be5-205">회의 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="29be5-205">Create a conferencing policy</span></span>

<span data-ttu-id="29be5-206">대규모 모임에 대해 특별히 새 회의 정책을 만든 다음, 전용 대규모 모임 풀에 속한 사용자에 게 회의 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-206">Create a new conferencing policy specifically for large meetings, and then assign the conferencing policy to the users who are homed on the dedicated large-meeting pool.</span></span> <span data-ttu-id="29be5-207">다음 설정을 사용하여 회의 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-207">Configure the conferencing policy using the following settings:</span></span>
  
- <span data-ttu-id="29be5-208">**MaxMeetingSize** 옵션을 1000으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-208">Set the **MaxMeetingSize** option to 1000.</span></span> <span data-ttu-id="29be5-209">기본값은 250입니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-209">(The default is 250.)</span></span>
    
- <span data-ttu-id="29be5-210">**AllowLargeMeetings** 옵션을 **True**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-210">Set the **AllowLargeMeetings** option to **True**.</span></span> 
    
- <span data-ttu-id="29be5-211">**EnableAppDesktopSharing** 옵션을 **None**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-211">Set the **EnableAppDesktopSharing** option to **None**.</span></span>
    
- <span data-ttu-id="29be5-212">**AllowUserToScheduleMeetingsWithAppSharing** 옵션을 **False**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-212">Set the **AllowUserToScheduleMeetingsWithAppSharing** option to **False**.</span></span>
    
- <span data-ttu-id="29be5-213">**AllowSharedNotes** 옵션을 **False**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-213">Set the **AllowSharedNotes** option to **False**.</span></span>
    
- <span data-ttu-id="29be5-214">**AllowAnnotations** 옵션을 **False**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-214">Set the **AllowAnnotations** option to **False**.</span></span>
    
- <span data-ttu-id="29be5-215">**DisablePowerPointAnnotations** 옵션을 **True**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-215">Set the **DisablePowerPointAnnotations** option to **True**.</span></span>
    
- <span data-ttu-id="29be5-216">**AllowMultiview** 옵션을 **False**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-216">Set the **AllowMultiview** option to **False**.</span></span>
    
- <span data-ttu-id="29be5-217">**EnableMultiviewJoin** 옵션을 **False**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-217">Set the **EnableMultiviewJoin** option to **False**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="29be5-218">비즈니스용 Skype 서버에서 대규모 모임을 지원 하려면 **AllowLargeMeetings** 설정이 true로 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-218">Support for large meetings in Skype for Business Server requires that the **AllowLargeMeetings** setting be set to true.</span></span> <span data-ttu-id="29be5-219">이 설정이 true로 설정 되 면 사용자가 모임에 참가할 때 비즈니스용 Skype 환경이 더 큰 모임에 최적화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-219">When this setting is set to true, the Skype for Business experience will be optimized for extra-large meetings when users join the meeting.</span></span> <span data-ttu-id="29be5-220">특히 대규모 모임에서 비즈니스용 Skype에는 전체 모임 참가자 목록의 초기 또는 업데이트가 표시 되지 않으며,이로 인해 클라이언트 및 비즈니스용 Skype 서버의 성능 병목 현상이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-220">Specifically, in a large meeting, Skype for Business will not show the initial or update of the full meeting participant list, which is a performance bottleneck for both the client and Skype for Business Server.</span></span> <span data-ttu-id="29be5-221">대신 비즈니스용 Skype에는 사용자 및 모임의 발표자 목록에 대 한 정보만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-221">Instead, Skype for Business will only show information about the user and the list of presenters of the meeting.</span></span> <span data-ttu-id="29be5-222">비즈니스용 Skype는 대규모 모임에서 사용할 수 있는 총 참가자 수를 계속 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-222">Skype for Business will still show the total number of participants available in the large meetings.</span></span>

<span data-ttu-id="29be5-223">**AllowLargeMeetings $true** 설정은 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-223">The **AllowLargeMeetings $true** setting causes the following:</span></span>

- <span data-ttu-id="29be5-224">참석자 명단을 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-224">Hides the Attendee roster.</span></span> 

- <span data-ttu-id="29be5-225">IM 창에서 오류를 비활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-225">Disables errors in the IM window.</span></span>

- <span data-ttu-id="29be5-226">다중 사용자 비디오를 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-226">Disables multi-party video.</span></span>

- <span data-ttu-id="29be5-227">참석자를 발표자로 승격 하는 기능을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-227">Disables ability to promote an Attendee to Presenter.</span></span> <span data-ttu-id="29be5-228">모임 전에 모든 발표자를 미리 계획 하 고 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-228">You must plan ahead and declare all Presenters before the meeting.</span></span>

- <span data-ttu-id="29be5-229">개별 참석자의 음소거를 해제 하는 기능을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-229">Disables ability to unmute individual Attendees.</span></span>

- <span data-ttu-id="29be5-230">참석자에 게 비디오 잠금 기능을 적용할 수 없도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-230">Disables ability to apply the Lock Video Spotlight feature to Attendees.</span></span>

- <span data-ttu-id="29be5-231">활성 대규모 모임에서 DTMF 명령을 담당 하는 개인 가상 지원이 없기 때문에 PSTN 전화 접속 사용자는 6을 사용 하 여 자체적으로 음소거를 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-231">PSTN dial in users will be unable to unmute themselves using 6 because Personal Virtual Assistance which is responsible for DTMF commands in active large meetings is missing.</span></span>

- <span data-ttu-id="29be5-232">발표자/이끌이는 모든 사용자가 조용히 음소거를 해야 하는 모임 ("모두 음소거")을 수행 하는 경우 PSTN 사용자는 통화 전체에 음소거 되며 자신에 게 음소거를 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-232">If the presenter/organizer schedules a meeting where everyone should be muted first ("Mute All"), PSTN users will be muted throughout the call and will not be able to unmute themselves.</span></span>

<span data-ttu-id="29be5-233">**최대 모임 크기** 설정을 제외하고 여기에 지정되는 다른 모든 모임 정책 설정은 대규모 모임에 필요하지 않은 회의 기능을 사용하지 않도록 설정하기 위해 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-233">Except for the **Maximum meeting size** setting, all the other conferencing policy settings specified here are required in order to disable conferencing capabilities that are not necessary in large meetings.</span></span>
  
<span data-ttu-id="29be5-234">또한 풀에 있고 모임 일정 관리를 담당 하는 각 비즈니스용 Skype 서버 사용자에 게 적절 한 사용 권한이 있도록 전용 대규모 모임 풀을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-234">Additionally, you need to configure the dedicated large-meeting pool so that each Skype for Business Server user who is homed on the pool and responsible for managing the meeting schedule has the appropriate permissions.</span></span> <span data-ttu-id="29be5-235">이렇게 하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-235">To do this, do the following:</span></span>
  
- <span data-ttu-id="29be5-p128">**발표자로 지정** 옵션을 **없음**으로 설정합니다. 일반적으로 대규모 모임의 모든 참가자 중 일부 소수만 발표자가 됩니다. 대규모 모임에서 참가자를 자동으로 발표자로 허용해서는 안됩니다. 대신 모임 예약 시에 발표자를 명시적으로 지정하거나 대규모 모임 중에 명시적으로 승격해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-p128">Set the **Designate as presenter** option to **None**. Typically, one or just a few users of all the participants of a large meeting are presenters, so participants should not be automatically admitted to large meetings as presenters. Instead, the presenters should be explicitly designated at meeting scheduling time, or be explicitly promoted during the large meeting.</span></span>
    
- <span data-ttu-id="29be5-239">**기본적으로 배정 된 회의 유형** 확인란이 선택 되지 않았는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-239">Make sure that the **Assigned conference type by default** check box is not selected.</span></span> <span data-ttu-id="29be5-240">이 설정은 비즈니스용 Skype의 온라인 모임 추가 기능에서 이끌이가 할당 된 전화 회의를 사용 하 여 항상 회의를 예약할 지 여부, 즉 예약 된 모임에 동일한 참가 URL 및 오디오 정보가 있음을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-240">This setting controls whether the Online Meeting Add-in for Skype for Business always schedules conferences using the organizer's assigned conference, which means that scheduled meetings have the same join URL and audio information.</span></span> <span data-ttu-id="29be5-241">소규모 그룹 공동 작업 시나리오에서는 모든 사용자에 게 고유한 회의가 있고, 상수 조인 URL 및 오디오 정보를 사용 하면 모임에 더 빠르게 참가할 수 있으므로 이러한 지정 된 회의 유형이 제대로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-241">In small group collaboration scenarios, having such assigned conference type works well because everyone has their own individual assigned conference, and the constant join URL and audio information helps to facilitate faster meeting joining.</span></span> <span data-ttu-id="29be5-242">그러나 대규모 모임 시나리오에서는 대규모 모임 지원 담당자가 단일 사용자 자격 증명 집합을 사용 하 여 대규모 모임을 예약 하 고 모임 요청자에 게 참가 Url 및 오디오 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-242">However, in the large-meeting scenario, the large meeting support staff schedules the large meetings using a single set of user credentials, and then provides join URLs and audio information to the meeting requesters.</span></span> <span data-ttu-id="29be5-243">이 경우에는 각 모임에 서로 다른 URL을 사용 하 여 작업 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-243">In this case, using a different URL to join each meeting works better.</span></span>
    
- <span data-ttu-id="29be5-244">필요한 경우가 아니면 **기본적으로 익명 사용자 허용** 확인란의 선택이 취소되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-244">Ensure that the **Admit anonymous users by default** check box is not selected, unless it is required.</span></span> <span data-ttu-id="29be5-245">이 설정은 지정 된 전화 회의를 사용 하지 않는 경우 비즈니스용 Skype의 온라인 모임 추가 기능에 의해 예약 된 기본 모임 액세스 유형에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-245">This setting affects the default meeting access type scheduled by the Online Meeting Add-in for Skype for Business when not using an assigned conference.</span></span> <span data-ttu-id="29be5-246">이 설정에 적절 한 옵션은 조직의 요구 사항에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-246">The appropriate option for this setting depends on your organization's needs.</span></span> <span data-ttu-id="29be5-247">조직에서 수행되는 대규모 모임 중 대부분이 내부 모임인 경우에는 이 옵션을 선택하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="29be5-247">If most large meetings for your organization are internal meetings, do not select this option.</span></span> <span data-ttu-id="29be5-248">대부분의 대규모 모임에 외부 사용자가 참가할 수 있어야 하는 경우 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="29be5-248">If most large meetings require that external users be able to join, select this option.</span></span>
    
<span data-ttu-id="29be5-249">회의 정책을 만드는 방법에 대 한 자세한 내용은 [비즈니스용 Skype 서버에서 회의 정책 관리](../../manage/conferencing/conferencing-policies.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="29be5-249">For more information about creating a conferencing policy, see [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).</span></span>
  

