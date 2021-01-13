---
title: 비즈니스용 Skype 서버에서 대규모 모임 계획
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 21507e18-bd79-4019-9c3a-0867fccaa3b4
description: '요약: 비즈니스용 Skype 서버에서 대규모 모임을 구현하고 관리하는 모범 사례에 대해 알아보는 이 항목을 참조하세요.'
ms.openlocfilehash: 8e982f08b1ff65ac6a4ea6f47a15e57f1eded163
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813978"
---
# <a name="plan-for-large-meetings-in-skype-for-business-server"></a><span data-ttu-id="99482-103">비즈니스용 Skype 서버에서 대규모 모임 계획</span><span class="sxs-lookup"><span data-stu-id="99482-103">Plan for large meetings in Skype for Business Server</span></span>
 
<span data-ttu-id="99482-104">**요약:** 이 항목을 통해 비즈니스용 Skype 서버에서 대규모 모임을 구현하고 관리하는 모범 사례에 대해 자세히 알아보실 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99482-104">**Summary:** Read this topic to learn about best practices for implementing and managing large meetings in Skype for Business Server.</span></span>
  
<span data-ttu-id="99482-105">비즈니스용 Skype 서버에서 지원할 수 있는 모임의 크기는 회의가 공유 풀 또는 전용 풀에서 호스팅되는지 여부에 따라 결정됩니다. 공유 풀의 참가자 250명에서 전용 풀의 참가자 1,000명까지.</span><span class="sxs-lookup"><span data-stu-id="99482-105">The size of meetings that Skype for Business Server can support depends on whether conferencing is hosted on a shared or dedicated pool: anywhere from 250 participants on a shared pool to 1000 participants on a dedicated pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="99482-106">이 항목에서는 비즈니스용 Skype 서버에서 지원하는 대규모 모임에 대한 모범 사례를 중점적으로 다수 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-106">This topic focuses on best practices for large meetings supported by Skype for Business Server.</span></span> <span data-ttu-id="99482-107">조직에 더 큰 모임 기능이 필요한 경우 Microsoft 365 및 Office 365의 일부인 새로운 온라인 서비스인 Skype 모임 브로드캐스트를 활용하는 하이브리드 환경을 구현하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="99482-107">If your organization requires larger meeting capabilities, you should consider implementing a hybrid environment that takes advantage of Skype Meeting Broadcast, a new online service that is part of Microsoft 365 and Office 365.</span></span> 

> [!NOTE]
> <span data-ttu-id="99482-108">Skype 모임 브로드캐스트를 사용하면 최대 10,000명이 참가하는 대규모 온라인 대상에게 모임을 호스팅하고 브로드캐스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99482-108">Skype Meeting Broadcast enables users to host and broadcast meetings to large online audiences of up to 10,000 participants.</span></span> <span data-ttu-id="99482-109">Skype 모임 브로드캐스트를 사용하려면 프로덕션 Microsoft 365 또는 Office 365 조직과의 하이브리드 설정에서 비즈니스용 Skype 서버를 이미 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-109">The use of Skype Meeting Broadcast requires that Skype for Business Server already be configured in a hybrid setup with a production Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="99482-110">모든 사용자는 온라인 테넌트가 전제로 설정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-110">All users must have an online tenant established as a prerequisite.</span></span> <span data-ttu-id="99482-111">Skype 모임 브로드캐스트를 활용할 수 있는 하이브리드 솔루션을 배포하는 데 관심이 있는 경우 [Skype](https://go.microsoft.com/fwlink/?LinkId=617071) 모임 브로드캐스트란? 및 Skype 모임 브로드캐스트에 대한 프레미스 배포 구성을 [참조하세요.](../../deploy/configure-skype-meeting-broadcast.md)</span><span class="sxs-lookup"><span data-stu-id="99482-111">If you are interested in deploying a hybrid solution that can take advantage of Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Configure your on-premises deployment for Skype Meeting Broadcast](../../deploy/configure-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="99482-112">대규모 모임의 특징은 일반적으로 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="99482-112">Large meetings typically have the following characteristics:</span></span>
  
- <span data-ttu-id="99482-113">모임 형식이 일대다 프레젠테이션입니다.</span><span class="sxs-lookup"><span data-stu-id="99482-113">The meeting format is a one-to-many presentation.</span></span>
    
- <span data-ttu-id="99482-114">한 명 또는 소수의 사용자가 발표자이고 그외 모든 사람은 참석자로만 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-114">One or a few users are presenters, and everyone else participates only as attendees.</span></span>
    
- <span data-ttu-id="99482-115">PowerPoint 프레젠테이션 공유가 기본 데이터 공동 작업 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="99482-115">PowerPoint presentation sharing is the main data collaboration activity.</span></span>
    
- <span data-ttu-id="99482-116">오디오가 필요하고 비디오를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99482-116">Audio is required and video may also be used.</span></span>
    
- <span data-ttu-id="99482-117">일반적으로 모임 이끌이 또는 이끌이의 비서인 전담 사람이 모임을 미리 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-117">A dedicated person, generally either the meeting organizer or an assistant to the organizer, sets up the meeting well in advance.</span></span>
    
- <span data-ttu-id="99482-118">전담 직원(발표자가 아님)이 온라인 모임에 연결하고, 오디오, 비디오 및 슬라이드 공유가 작동하는지 확인하고, 대기실 및 사용자 역할을 관리하고, 참가자를 음소거하거나 음소거를 해제하고, 질문을 받고, 기록을 관리하는 등 모임을 적절하게 운영합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-118">Dedicated staff (not the presenters) runs the meeting, including connecting to an online meeting, verifying that audio, video, and slide sharing work, managing lobby and user roles, muting and unmuting participants, taking questions, and managing recordings, as appropriate.</span></span>
    
<span data-ttu-id="99482-119">사용자가 모임을 예약하면 비즈니스용 Skype 서버는 회의 데이터를 저장하지만 미리 예약된 모임에 대한 하드웨어 리소스를 예약하지 않는 회의 데이터베이스에 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="99482-119">When a user schedules a meeting, Skype for Business Server creates a record in the conferencing database, which stores conferencing data, but does not reserve any hardware resources for the scheduled meeting ahead of time.</span></span> <span data-ttu-id="99482-120">대신 비즈니스용 Skype 서버에는 풀의 모든 프런트 엔드 서버에 부하를 동일하게 분산하는 방식으로 프런트 엔드 서버에 회의 리소스를 동적으로 할당하는 기본 제공 부하 분산 논리가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99482-120">Instead, Skype for Business Server has built-in load balancing logic to dynamically allocate conferencing resources on Front End Servers in a way that distributes loads equally across all Front End Servers in the pool.</span></span> <span data-ttu-id="99482-121">이렇게 하여 하드웨어 리소스를 효과적으로 프로비전하고 사용하지만 대규모 모임을 적절하게 지원하도록 계획하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-121">This effectively provisions and uses hardware resources, but it is important that you plan appropriately to support very large meetings.</span></span> 
  
<span data-ttu-id="99482-122">예를 들어 비즈니스용 Skype 서버 풀이 최대 용량에 가까운 실행 중인 경우 각 프런트 엔드 서버는 약 125의 평균 크기 모임을 호스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99482-122">For example, when a Skype for Business Server pool is running close to its top capacity, each Front End Server might host approximately 125 average-size meetings.</span></span> <span data-ttu-id="99482-123">다른 소규모 모임을 추가하는 것은 문제가 되지 않지만, 프런트 엔드 서버가 다른 125개 모임과 동시에 이러한 대규모 모임을 지원하지 못하기 때문에 1,000명에 대한 모임을 추가하는 것은 문제가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99482-123">Adding another small meeting would not be a problem, but adding a meeting for 1000 users would be a problem because the Front End Servers would probably not be able to support such a large meeting at the same time as the other 125 meetings.</span></span>
  
<span data-ttu-id="99482-124">최대 1,000명이 참가하는 대규모 모임을 지원하려면 공유 하드웨어 모델과 예약 없음 모델과 관련된 문제를 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-124">Supporting large meetings of up to 1000 participants requires addressing the issues related to both the shared hardware model and the no-reservation model.</span></span> <span data-ttu-id="99482-125">일반적으로 전용 풀을 계획하고 다음 섹션에 설명된 모범 사례를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-125">In general, you need to plan for a dedicated pool and follow best practices as described in the following sections.</span></span> 
  
## <a name="plan-for-a-dedicated-pool"></a><span data-ttu-id="99482-126">전용 풀 계획</span><span class="sxs-lookup"><span data-stu-id="99482-126">Plan for a dedicated pool</span></span>

<span data-ttu-id="99482-127">조직에 참가자가 250명 이상인 모임이 필요한 경우 부하를 지원하기 위한 전용 풀을 계획해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-127">If your organization requires meetings with greater than 250 participants, you need to plan for a dedicated pool to support the load.</span></span> 
  
<span data-ttu-id="99482-128">최대 1,000명 이상의 모임에 충분한 CPU 및 메모리 리소스를 확보하기 위해 호스팅 프런트 엔드 서버는 다른 IM(인스턴트 메시징) 및 현재 상태 또는 Enterprise Voice 호스트하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-128">To have sufficient CPU and memory resources for meetings of up to 1000 users, the hosting Front End Servers should not host any other instant messaging (IM) and presence or Enterprise Voice workloads.</span></span> <span data-ttu-id="99482-129">또한 서버는 다른 모임의 크기에 관계없이 다른 모임을 호스팅하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-129">The servers should also not host any other meetings, regardless of the size of the other meetings.</span></span> <span data-ttu-id="99482-130">최대 1,000명 이상의 모임을 호스팅하려면 대규모 모임 호스팅 전용으로 사용할 별도의 비즈니스용 Skype 서버 풀을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-130">To host meetings of up to 1000 users, you need to set up a separate Skype for Business Server pool that is dedicated to hosting large meetings.</span></span>
  
<span data-ttu-id="99482-131">대규모 모임을 호스팅하는 데 전용되는 비즈니스용 Skype 서버 풀은 동시에 최대 1,000명인 모임 하나만 호스팅해야 하여 프런트 엔드 서버의 전용 지원을 보장하려면 대역 외 예약 프로세스를 통해 모임 시간을 미리 예약해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-131">A Skype for Business Server pool that is dedicated to hosting large meetings should host one and only one meeting of up to 1000 users at the same time, so meeting times need to be reserved in advance via an out of band scheduling process to ensure dedicated support from the Front End Servers.</span></span> <span data-ttu-id="99482-132">두 개 이상의 대규모 모임을 동시에 지원하기 위해 여러 개의 전용 대규모 모임 풀을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-132">To support more than one large meeting at the same time, you should set up multiple dedicated large-meeting pools.</span></span>
  
<span data-ttu-id="99482-133">하드웨어 및 소프트웨어 요구 사항 및 대규모 모임을 지원하는 토폴로지 계획에 대한 자세한 내용은 비즈니스용 [Skype](hardware-and-software-requirements.md) 서버의 회의에 대한 하드웨어 및 소프트웨어 요구 사항을 참조하고 비즈니스용 [Skype](conferencing-topology.md)서버용 회의 토폴로지 계획을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99482-133">For more information about hardware and software requirements, and planning a topology that supports large meetings, see [Hardware and software requirements for conferencing in Skype for Business Server](hardware-and-software-requirements.md) and [Plan your conferencing topology for Skype for Business Server](conferencing-topology.md).</span></span>
  
## <a name="implement-best-practices-for-large-meetings"></a><span data-ttu-id="99482-134">대규모 모임에 대한 모범 사례 구현</span><span class="sxs-lookup"><span data-stu-id="99482-134">Implement best practices for large meetings</span></span>

<span data-ttu-id="99482-135">대규모 모임 전용 풀을 설정한 후 풀에서 호스팅된 대규모 모임이 최상의 사용자 환경을 제공하도록 하는 단계를 수행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99482-135">After setting up a dedicated pool for large meetings, you can take steps to help ensure that large meetings hosted in the pool provide the best user experience.</span></span> <span data-ttu-id="99482-136">다음 섹션에서는 대규모 모임 관리에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-136">The following sections provide guidelines for managing large meetings:</span></span>
  
- <span data-ttu-id="99482-137">전용 모임 이끌이 만들기</span><span class="sxs-lookup"><span data-stu-id="99482-137">Create dedicated meeting organizers</span></span>
    
- <span data-ttu-id="99482-138">전용 중재자 만들기</span><span class="sxs-lookup"><span data-stu-id="99482-138">Create dedicated moderators</span></span>
    
- <span data-ttu-id="99482-139">대규모 모임의 별도 일정 유지 관리</span><span class="sxs-lookup"><span data-stu-id="99482-139">Maintain a separate calendar of large meetings</span></span>
    
- <span data-ttu-id="99482-140">대규모 모임 계획 프로세스 구현</span><span class="sxs-lookup"><span data-stu-id="99482-140">Implement a large-meeting scheduling process</span></span>
    
- <span data-ttu-id="99482-141">적절한 예약 세부 정보 지정</span><span class="sxs-lookup"><span data-stu-id="99482-141">Specify appropriate scheduling details</span></span>
    
- <span data-ttu-id="99482-142">대규모 모임에 대한 회의 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="99482-142">Create a conferencing policy for large meetings</span></span>
    
### <a name="create-dedicated-meeting-organizers"></a><span data-ttu-id="99482-143">전용 모임 이끌이 만들기</span><span class="sxs-lookup"><span data-stu-id="99482-143">Create dedicated meeting organizers</span></span>

<span data-ttu-id="99482-144">대규모 모임 풀에서 실시간 통신 트래픽을 최소화하기 위해 Microsoft는 비즈니스용 Skype 클라이언트를 사용하여 정기적으로 로그인하고 IM(인스턴트 메시징), 현재 상태, 회의 및 음성 세션에 참여하는 사용자를 호스팅하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="99482-144">To minimize the real-time communications traffic in the large-meeting pool, Microsoft does not recommend hosting users who regularly sign in using Skype for Business clients and participate in instant messaging (IM), presence, conferencing, and voice sessions.</span></span> <span data-ttu-id="99482-145">대신 다음 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-145">Instead, do one of the following:</span></span>
  
- <span data-ttu-id="99482-146">대규모 모임을 위한 전용 사용자 계정 하나 이상 만들기</span><span class="sxs-lookup"><span data-stu-id="99482-146">Create one or more dedicated user accounts just for scheduling large meetings</span></span>
    
- <span data-ttu-id="99482-147">대규모 모임 풀에서 대규모 모임을 준비하는 직원의 사용자 계정 홈</span><span class="sxs-lookup"><span data-stu-id="99482-147">Home the user accounts of the staff responsible for scheduling large meetings on a large-meeting pool</span></span>
    
### <a name="create-dedicated-moderators"></a><span data-ttu-id="99482-148">전용 중재자 만들기</span><span class="sxs-lookup"><span data-stu-id="99482-148">Create dedicated moderators</span></span>

<span data-ttu-id="99482-149">모임에 수백- 수천 명의 사용자가 있는 경우 전담 사용자가 대규모 모임의 온라인 세션을 중재하게 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="99482-149">With several hundred to a thousand users in a meeting, it is a good practice to have a dedicated person moderate the online session of a large meeting.</span></span> <span data-ttu-id="99482-150">이 전담 직원은 모임 이끌이의 대리인 또는 조직의 대규모 모임 지원 직원의 구성원일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99482-150">This dedicated person can be a delegate of the meeting organizer or a member of the organization's large-meeting support staff.</span></span> <span data-ttu-id="99482-151">전담 모임 중재자를 모임이 예약된 시간에 발표자로 추가해야 하지만, 모임이 진행되는 동안에는 온라인 모임 참가자를 발표자 역할로 승격시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99482-151">It is important to add the dedicated meeting moderator as a presenter at the time that the meeting is scheduled, although it is possible to promote an online meeting attendee to the presenter role while the meeting is in progress.</span></span>
  
<span data-ttu-id="99482-152">모임 중재자는 비즈니스용 Skype 클라이언트의 모든 발표자 기능을 사용하여 대규모 모임을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99482-152">The meeting moderator can use all presenter functionalities of Skype for Business clients to manage the large meeting.</span></span> <span data-ttu-id="99482-153">이러한 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="99482-153">These functionalities include:</span></span>
  
- <span data-ttu-id="99482-154">대기실 모니터링 및 대기실의 사용자 수락 또는 거부</span><span class="sxs-lookup"><span data-stu-id="99482-154">Monitoring the lobby and admitting or rejecting users in the lobby</span></span>
    
- <span data-ttu-id="99482-155">모임에 참석하지 말아야 하는 사용자 제거</span><span class="sxs-lookup"><span data-stu-id="99482-155">Removing any users from the meeting who should not be in the meeting</span></span>
    
- <span data-ttu-id="99482-156">모임 액세스 유형 변경</span><span class="sxs-lookup"><span data-stu-id="99482-156">Changing meeting access types</span></span>
    
- <span data-ttu-id="99482-157">참가자 역할 변경</span><span class="sxs-lookup"><span data-stu-id="99482-157">Changing participant roles</span></span>
    
- <span data-ttu-id="99482-158">끌어서 놓기 기능, 전화 걸기 또는 전자 메일을 사용하여 모임 중에 추가 참가자 모이기</span><span class="sxs-lookup"><span data-stu-id="99482-158">Inviting additional participants during the meeting using drag and drop functionality, phone dial out, or email</span></span>
    
- <span data-ttu-id="99482-159">대상 또는 개별 사용자 음소거 및 음소거</span><span class="sxs-lookup"><span data-stu-id="99482-159">Muting and unmuting the audience or individual users</span></span>
    
- <span data-ttu-id="99482-160">콘텐츠 업로드, 콘텐츠 삭제, 활성 콘텐츠 전환 등 모임 콘텐츠 관리</span><span class="sxs-lookup"><span data-stu-id="99482-160">Managing meeting content, including uploading content, deleting content, and switching active content</span></span>

    
### <a name="maintain-a-separate-calendar"></a><span data-ttu-id="99482-161">별도의 달력 유지 관리</span><span class="sxs-lookup"><span data-stu-id="99482-161">Maintain a separate calendar</span></span>

<span data-ttu-id="99482-162">각 대규모 모임 풀에 대해 해당 풀에 예약된 별도의 대규모 모임 일정을 유지 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-162">For each large-meeting pool, you should maintain a separate calendar of large meetings scheduled on that pool.</span></span> <span data-ttu-id="99482-163">예를 들어 대규모 모임 풀에 단일 사용자 계정을 사용하고 Outlook과 Exchange 및 비즈니스용 Skype용 온라인 모임 추가 기능을 사용하여 별도의 일정을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99482-163">For example, you can home a single user account on the large-meeting pool and use Outlook with Exchange and Online Meeting Add-in for Skype for Business to maintain a separate calendar.</span></span> <span data-ttu-id="99482-164">지원 부서가 대규모 모임을 만들 수 있도록 설정하기 위해 여러 사용자 계정을 사용할 경우 해당 지원 부서의 구성원이 만든 모든 대규모 모임을 집계하는 별도의 일정을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99482-164">If you use multiple user accounts to enable a support staff to create large meetings, you can set up a separate calendar that aggregates all large meetings created by the members of the support staff.</span></span> 
  
<span data-ttu-id="99482-165">별도의 대규모 모임 일정을 유지 관리하면 충돌을 방지하고 항상 하나의 대규모 모임만 활성화된 상태로 유지되도록 보장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99482-165">Maintaining a separate large meeting calendar helps to prevent conflicts and ensure that only one large meeting is active at any time.</span></span>
  
### <a name="implement-a-scheduling-process"></a><span data-ttu-id="99482-166">계획 프로세스 구현</span><span class="sxs-lookup"><span data-stu-id="99482-166">Implement a scheduling process</span></span>

<span data-ttu-id="99482-167">전용 대규모 모임 풀에서는 한 번씩의 대규모 모임만 지원하기 때문에 대규모 모임을 쉽게 설정하고 충돌을 방지할 수 있도록 대규모 모임 계획 프로세스를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-167">Because only one large meeting at a time is supported on the dedicated large meeting pool, you should implement a large meeting scheduling process to facilitate setting up large meetings and help prevent conflicts.</span></span> <span data-ttu-id="99482-168">이러한 기능은 비즈니스용 Skype 서버 또는 비즈니스용 Skype 클라이언트에서 직접 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99482-168">Such capability is not provided directly by Skype for Business Server or Skype for Business clients.</span></span> <span data-ttu-id="99482-169">이러한 프로세스를 구현하는 한 가지 방법은 사용 가능한 경우 조직의 지원 팀의 티켓 시스템을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="99482-169">One way to implement such a process is to use your organization's support team's ticketing system, if available.</span></span>
  
<span data-ttu-id="99482-170">대규모 모임을 예정하는 경우 다음 단계를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-170">Scheduling a large meeting involves completing the following steps:</span></span>
  
- <span data-ttu-id="99482-p114">모임 이끌이나 대리자가 예정된 모임의 시간, 기간 및 규모와 발표자 목록을 결정합니다. 또한 예상된 모임 규모가 250명을 초과하거나 250명 미만의 모임을 위한 최상의 사용자 환경을 유지하려는 경우 대규모 모임 요청을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-p114">The meeting organizer or delegate determines the time, duration, and size of an upcoming meeting, in addition to the list of presenters. If the anticipated meeting size exceeds 250 users or to ensure the best user experience for a meeting of fewer than 250 users, the organizer or the delegate submits a request for a large meeting.</span></span>
    
- <span data-ttu-id="99482-p115">예약 직원은 요청된 날짜와 시간이 예약 가능한지 확인합니다. 전용 풀에서 한 번에 하나의 대규모 모임만 지원되므로 예약 직원은 요청한 날짜 및 시간에 예약된 다른 모임이 있는지 알아보기 위해 대규모 모음 일정을 확인해야 합니다. 요청한 시간이 예약 가능하면 직원은 모임 요청을 승인합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-p115">The scheduling staff checks to see whether the requested date and time is available. Since we support only a single large meeting on the dedicated pool at a time, the scheduling staff needs to check the large-meeting calendar to determine whether there is another meeting scheduled for the requested date and time. If the requested time is available, the staff approves the meeting request.</span></span>
    
- <span data-ttu-id="99482-176">요청이 승인되면 예약 직원(전용 풀에서 자격 증명 사용)은 Outlook과 함께 비즈니스용 Skype용 온라인 모임 추가 기능을 사용하여 전용 대규모 모임 풀에서 모임을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-176">If the request is approved, the scheduling staff (using credentials on the dedicated pool) uses Online Meeting Add-in for Skype for Business with Outlook to set up a meeting on the dedicated large-meeting pool.</span></span> <span data-ttu-id="99482-177">모임에 참가하는 데 사용될 URL은 승인 알림의 일부로 요청자에게 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="99482-177">The URL to be used to join the meeting is provided to the requester as part of the approval notice.</span></span>
    
- <span data-ttu-id="99482-178">모임 이끌이 또는 대리인은 Outlook을 사용하여 예정된 모임을 예약하고 모임 참가용 URL을 모임 초대에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-178">The meeting organizer or delegate uses Outlook to schedule the upcoming meeting, adding the URL for joining the meeting to the meeting invitation.</span></span> <span data-ttu-id="99482-179">그런 다음 초대할 사용자를 지정하여 모임 초대를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="99482-179">The meeting organizer or delegate then specifies the users to be invited and sends out the meeting invitation.</span></span>
    
### <a name="specify-appropriate-scheduling-details"></a><span data-ttu-id="99482-180">적절한 예약 세부 정보 지정</span><span class="sxs-lookup"><span data-stu-id="99482-180">Specify appropriate scheduling details</span></span>

<span data-ttu-id="99482-181">요청을 처리하는 대규모 모임 지원 담당자는 요청된 시간에 다른 모임이 예약되어 있지 않은지 확인한 후에 대규모 모임 풀에서 모임을 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-181">After checking to ensure that no other meeting is scheduled at the requested time, the large meeting support staff that handles the request schedules the meeting on the large-meeting pool.</span></span> 
  
<span data-ttu-id="99482-182">최상의 사용자 환경을 보장하려면 모임 이끌이의 요구에 적합한 액세스 수준 및 모임 설정을 사용하여 대규모 모임을 예약하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-182">To ensure the best user experience, it is important to schedule the large meeting with the right access levels and meeting settings that are appropriate to the meeting organizer's needs.</span></span> <span data-ttu-id="99482-183">비즈니스용 Skype 모임 옵션에 구성된 다음의 계획 설정을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="99482-183">Consider the following scheduling settings configured in Skype for Business Meeting options:</span></span>
  
- <span data-ttu-id="99482-184">전용 모임 공간을 다시 사용하는 대신 각각의 대규모 모임용으로 새 모임 공간을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="99482-184">Use a new meeting space for each large meeting instead of reusing the dedicated meeting space.</span></span> 
    
- <span data-ttu-id="99482-185">모임 액세스 수준을 다음과 같이 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-185">Specify the meeting access level as follows:</span></span>
    
  - <span data-ttu-id="99482-186">한 개 이상의 초대를 조직 외부에 있는 경우 모임 액세스 유형을 모든 사용자(제한 **없음)로 설정하십시오.**</span><span class="sxs-lookup"><span data-stu-id="99482-186">If at least one invitee is external to the organization, set the meeting access type to **Anyone (no restrictions)**.</span></span> <span data-ttu-id="99482-187">그러면 모임이 진행 중일 때 대규모 대기실을 관리할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="99482-187">This enables you to avoid having to manage a potentially large lobby when the meeting is in progress.</span></span>
    
  - <span data-ttu-id="99482-188">내부 전용 모임의 경우에는 모임 액세스 유형을 **조직 구성원 모두** 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-188">If the meeting is an internal-only meeting, set the meeting access type to **Anyone from my organization**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="99482-189">모임 액세스 유형으로 **내 회사에서 초대한 사용자** 설정을 사용하는 경우 이끌이가 모든 사용자 전자 메일 주소를 초대 대상자 목록에 추가해야 하며 메일 그룹은 초대할 수 없으므로, 모임 액세스 유형을 이렇게 설정하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="99482-189">Avoid setting the meeting access type to **People I invite from my company** because when you use this setting, organizers must add all user email addresses to the invitee list and you cannot invite a distribution group.</span></span> <span data-ttu-id="99482-190">모임 액세스 유형으로 **나만, 모임 이끌이** 설정을 사용하는 경우 발표자를 비롯한 모든 모임 참가자가 모임 실행 시 대기실에서 기다려야 하므로 모임 액세스 유형을 이렇게 설정하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="99482-190">Avoid setting the meeting access type to **Only me, the meeting organizer** because this setting requires that every meeting participant, including presenters, must be put in the lobby at meeting run time.</span></span> <span data-ttu-id="99482-191">이 설정을 사용하는 경우에는 대규모 모임을 진행하는 사람이 대기실 명단을 지속적으로 모니터링하여 대기실에 있는 새 사용자를 허용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-191">The person responsible for running the large meeting must then constantly monitor the lobby roster and admit new users who are in the lobby.</span></span>
  
- <span data-ttu-id="99482-192">**발신자 바로 입장** 설정을 선택하여 전화를 통해 전화 접속하는 사용자가 모임에 자동으로 입장하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-192">Allow users who dial-in from phones to enter the meeting automatically by checking the **Callers get in directly** setting.</span></span>
    
- <span data-ttu-id="99482-193">다음 사용자를 명시적으로 초대합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-193">Explicitly invite the following users:</span></span>
    
  - <span data-ttu-id="99482-194">모임 이끌이 및 대리인(요청자)</span><span class="sxs-lookup"><span data-stu-id="99482-194">Meeting organizer and delegate (requester)</span></span>
    
  - <span data-ttu-id="99482-195">모임 요청자가 제공하는 발표자 목록</span><span class="sxs-lookup"><span data-stu-id="99482-195">The list of presenters provided by a meeting requester</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="99482-196">모임 액세스 유형을 **내가 선택한 사용자** 로 설정하는 경우에는 대규모 모임의 각 참가자를 명시적으로 모임 초대 대상자로 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-196">If the meeting access type is set to **People I choose**, you need to explicitly add each participant of a large meeting as an invitee of the meeting.</span></span> 
  
- <span data-ttu-id="99482-p121">발표자 옵션을 자동 승격 값 중 하나로 설정하는 대신 발표자를 명시적으로 관리합니다. 다음과 같은 사용자를 발표자로 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-p121">Explicitly manage presenters, instead of setting the presenter option to one of the auto-promote values. Be sure to add the following users as presenters:</span></span>
    
  - <span data-ttu-id="99482-199">모임 이끌이 및 대리인(요청자)</span><span class="sxs-lookup"><span data-stu-id="99482-199">Meeting organizer and delegate (requester)</span></span>
    
  - <span data-ttu-id="99482-200">대규모 모임 요청자가 제공하는 발표자 목록</span><span class="sxs-lookup"><span data-stu-id="99482-200">The list of presenters provided by large meeting requesters</span></span>
    
    <span data-ttu-id="99482-201">발표자는 명시적으로 관리하여 대규모 모임을 효과적으로 구성할 수 있도록 발표자 수를 적게 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99482-201">By explicitly managing presenters, you can limit presenters to a small enough number to make it possible to have an effective large meeting.</span></span> <span data-ttu-id="99482-202">대부분의 모임 참가자에게 참석자 역할이 지정되면 실수로 사용자들에게 프레젠테이션 제어권을 부여하거나, PowerPoint 프레젠테이션을 삭제하거나, 발표자를 음소거/음소거 해제하고 기타 이유로 모임을 중단할 가능성이 낮아집니다.</span><span class="sxs-lookup"><span data-stu-id="99482-202">If the majority of meeting participants have the attendee role, it helps reduce the chance of people accidentally taking control of the presentation, deleting a PowerPoint presentation, muting/unmuting presenters, and other disruptions to the meeting.</span></span> 
    
- <span data-ttu-id="99482-203">**모든 참석자 음소거** 설정을 선택하여 발표자만 모임에 오디오를 브로드캐스트할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-203">Check the **Mute all attendees** setting to make sure that only presenters can broadcast audio into the meeting.</span></span>
    
- <span data-ttu-id="99482-204">참석자  차단 비디오 설정을 확인하여 발표자만 모임에 비디오를 브로드캐스트할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-204">Check the **Block attendees' video** setting to make sure only presenters can broadcast video into the meeting.</span></span>
    
### <a name="create-a-conferencing-policy"></a><span data-ttu-id="99482-205">회의 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="99482-205">Create a conferencing policy</span></span>

<span data-ttu-id="99482-206">대규모 모임에 대해 특별히 새 회의 정책을 만든 다음 전용 대규모 모임 풀에 있는 사용자에게 회의 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-206">Create a new conferencing policy specifically for large meetings, and then assign the conferencing policy to the users who are homed on the dedicated large-meeting pool.</span></span> <span data-ttu-id="99482-207">다음 설정을 사용하여 회의 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-207">Configure the conferencing policy using the following settings:</span></span>
  
- <span data-ttu-id="99482-208">**MaxMeetingSize** 옵션을 1000으로 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="99482-208">Set the **MaxMeetingSize** option to 1000.</span></span> <span data-ttu-id="99482-209">기본값은 250입니다.</span><span class="sxs-lookup"><span data-stu-id="99482-209">(The default is 250.)</span></span>
    
- <span data-ttu-id="99482-210">**AllowLargeMeetings** 옵션을 **True** 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-210">Set the **AllowLargeMeetings** option to **True**.</span></span> 
    
- <span data-ttu-id="99482-211">**EnableAppDesktopSharing** 옵션을 **None** 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-211">Set the **EnableAppDesktopSharing** option to **None**.</span></span>
    
- <span data-ttu-id="99482-212">**AllowUserToScheduleMeetingsWithAppSharing** 옵션을 **False** 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-212">Set the **AllowUserToScheduleMeetingsWithAppSharing** option to **False**.</span></span>
    
- <span data-ttu-id="99482-213">**AllowSharedNotes** 옵션을 **False** 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-213">Set the **AllowSharedNotes** option to **False**.</span></span>
    
- <span data-ttu-id="99482-214">**AllowAnnotations** 옵션을 **False** 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-214">Set the **AllowAnnotations** option to **False**.</span></span>
    
- <span data-ttu-id="99482-215">**DisablePowerPointAnnotations** 옵션을 **True** 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-215">Set the **DisablePowerPointAnnotations** option to **True**.</span></span>
    
- <span data-ttu-id="99482-216">**AllowMultiview** 옵션을 **False** 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-216">Set the **AllowMultiview** option to **False**.</span></span>
    
- <span data-ttu-id="99482-217">**EnableMultiviewJoin** 옵션을 **False** 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-217">Set the **EnableMultiviewJoin** option to **False**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="99482-218">비즈니스용 Skype 서버에서 대규모 모임을 지원하려면 **AllowLargeMeetings** 설정을 true로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-218">Support for large meetings in Skype for Business Server requires that the **AllowLargeMeetings** setting be set to true.</span></span> <span data-ttu-id="99482-219">이 설정을 true로 설정하면 사용자가 모임에 참가할 때 비즈니스용 Skype 환경이 대규모 모임에 최적화됩니다.</span><span class="sxs-lookup"><span data-stu-id="99482-219">When this setting is set to true, the Skype for Business experience will be optimized for extra-large meetings when users join the meeting.</span></span> <span data-ttu-id="99482-220">특히 대규모 모임에서 비즈니스용 Skype는 전체 모임 참가자 목록의 초기 또는 업데이트(클라이언트와 비즈니스용 Skype 서버 둘 다에 대한 성능 병목 현상)를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99482-220">Specifically, in a large meeting, Skype for Business will not show the initial or update of the full meeting participant list, which is a performance bottleneck for both the client and Skype for Business Server.</span></span> <span data-ttu-id="99482-221">대신 비즈니스용 Skype에는 사용자 및 모임의 발표자 목록에 대한 정보만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="99482-221">Instead, Skype for Business will only show information about the user and the list of presenters of the meeting.</span></span> <span data-ttu-id="99482-222">비즈니스용 Skype에는 대규모 모임에서 사용할 수 있는 총 참가자 수가 계속 표시될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="99482-222">Skype for Business will still show the total number of participants available in the large meetings.</span></span>

<span data-ttu-id="99482-223">**AllowLargeMeetings** $true 설정하면 다음과 같은 문제가 발생하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99482-223">The **AllowLargeMeetings $true** setting causes the following:</span></span>

- <span data-ttu-id="99482-224">참석자명단을 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99482-224">Hides the Attendee roster.</span></span> 

- <span data-ttu-id="99482-225">IM 창에서 오류를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-225">Disables errors in the IM window.</span></span>

- <span data-ttu-id="99482-226">다중 파티 비디오를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-226">Disables multi-party video.</span></span>

- <span data-ttu-id="99482-227">참석자에서 발표자로 승격하는 기능을 사용하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-227">Disables ability to promote an Attendee to Presenter.</span></span> <span data-ttu-id="99482-228">모임 전에 미리 계획하고 모든 발표자에 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-228">You must plan ahead and declare all Presenters before the meeting.</span></span>

- <span data-ttu-id="99482-229">개별 참석자에 대한 해제 기능을 사용하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-229">Disables ability to unmute individual Attendees.</span></span>

- <span data-ttu-id="99482-230">참석자에 비디오 잠금 추천 기능을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="99482-230">Disables ability to apply the Lock Video Spotlight feature to Attendees.</span></span>

- <span data-ttu-id="99482-231">활성 대규모 모임에서 DTMF 명령을 담당하는 개인 가상 지원이 누락된 경우 사용자의 PSTN 전화 걸기에서 사용자가 6을 사용하여 직접 음성을 내보내지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-231">PSTN dial in users will be unable to unmute themselves using 6 because Personal Virtual Assistance which is responsible for DTMF commands in active large meetings is missing.</span></span>

- <span data-ttu-id="99482-232">발표자/이끌이가 모든 사람을 먼저 음소거해야 하는 모임을 예약하는 경우("모두 음소거") PSTN 사용자는 통화 전체에서 음소거되고 직접 음소거를 언테이트할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="99482-232">If the presenter/organizer schedules a meeting where everyone should be muted first ("Mute All"), PSTN users will be muted throughout the call and will not be able to unmute themselves.</span></span>

<span data-ttu-id="99482-233">**최대 모임 크기** 설정을 제외하고 여기에 지정되는 다른 모든 모임 정책 설정은 대규모 모임에 필요하지 않은 회의 기능을 사용하지 않도록 설정하기 위해 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-233">Except for the **Maximum meeting size** setting, all the other conferencing policy settings specified here are required in order to disable conferencing capabilities that are not necessary in large meetings.</span></span>
  
<span data-ttu-id="99482-234">또한 풀에 있으며 모임 일정 관리를 담당하는 각 비즈니스용 Skype 서버 사용자에게 적절한 권한이 있도록 전용 대규모 모임 풀을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-234">Additionally, you need to configure the dedicated large-meeting pool so that each Skype for Business Server user who is homed on the pool and responsible for managing the meeting schedule has the appropriate permissions.</span></span> <span data-ttu-id="99482-235">이렇게 하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-235">To do this, do the following:</span></span>
  
- <span data-ttu-id="99482-p128">**발표자로 지정** 옵션을 **없음** 으로 설정합니다. 일반적으로 대규모 모임의 모든 참가자 중 일부 소수만 발표자가 됩니다. 대규모 모임에서 참가자를 자동으로 발표자로 허용해서는 안됩니다. 대신 모임 예약 시에 발표자를 명시적으로 지정하거나 대규모 모임 중에 명시적으로 승격해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-p128">Set the **Designate as presenter** option to **None**. Typically, one or just a few users of all the participants of a large meeting are presenters, so participants should not be automatically admitted to large meetings as presenters. Instead, the presenters should be explicitly designated at meeting scheduling time, or be explicitly promoted during the large meeting.</span></span>
    
- <span data-ttu-id="99482-239">기본적으로 할당된 **회의 유형이 선택되어** 있지 않은지 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-239">Make sure that the **Assigned conference type by default** check box is not selected.</span></span> <span data-ttu-id="99482-240">이 설정은 비즈니스용 Skype용 온라인 모임 추가 기능에서 이끌이의 할당된 전화 회의를 사용하여 항상 전화 회의를 예약하는지 여부를 제어합니다. 즉, 예약된 모임의 참가 URL과 오디오 정보가 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-240">This setting controls whether the Online Meeting Add-in for Skype for Business always schedules conferences using the organizer's assigned conference, which means that scheduled meetings have the same join URL and audio information.</span></span> <span data-ttu-id="99482-241">소규모 그룹 공동 작업 시나리오에서는 모든 사용자가 자체적으로 할당된 회의를 가지고 있기 때문에 이와 같은 할당된 회의 유형이 잘 작동하고, 일정한 참가 URL 및 오디오 정보를 사용하면 모임 참가를 보다 빠르게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99482-241">In small group collaboration scenarios, having such assigned conference type works well because everyone has their own individual assigned conference, and the constant join URL and audio information helps to facilitate faster meeting joining.</span></span> <span data-ttu-id="99482-242">그러나 대규모 모임 시나리오에서는 대규모 모임 지원 직원이 단일 사용자 자격 증명 집합을 사용하여 대규모 모임을 예약한 다음 모임 요청자에 참가 URL 및 오디오 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-242">However, in the large-meeting scenario, the large meeting support staff schedules the large meetings using a single set of user credentials, and then provides join URLs and audio information to the meeting requesters.</span></span> <span data-ttu-id="99482-243">이 경우 다른 URL을 사용하여 각 모임에 참가하는 것이 더 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="99482-243">In this case, using a different URL to join each meeting works better.</span></span>
    
- <span data-ttu-id="99482-244">필요한 경우가 아니면 **기본적으로 익명 사용자 허용** 확인란의 선택이 취소되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-244">Ensure that the **Admit anonymous users by default** check box is not selected, unless it is required.</span></span> <span data-ttu-id="99482-245">이 설정은 할당된 회의를 사용하지 않을 때 비즈니스용 Skype용 온라인 모임 추가 기능에서 예약한 기본 모임 액세스 유형에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99482-245">This setting affects the default meeting access type scheduled by the Online Meeting Add-in for Skype for Business when not using an assigned conference.</span></span> <span data-ttu-id="99482-246">이 설정에 적합한 옵션은 조직의 요구에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="99482-246">The appropriate option for this setting depends on your organization's needs.</span></span> <span data-ttu-id="99482-247">조직에서 수행되는 대규모 모임 중 대부분이 내부 모임인 경우에는 이 옵션을 선택하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="99482-247">If most large meetings for your organization are internal meetings, do not select this option.</span></span> <span data-ttu-id="99482-248">대부분의 대규모 모임에 외부 사용자가 참가할 수 있어야 하는 경우 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="99482-248">If most large meetings require that external users be able to join, select this option.</span></span>
    
<span data-ttu-id="99482-249">회의 정책을 만드는 데 대한 자세한 내용은 비즈니스용 Skype 서버에서 회의 정책 [관리를 참조하세요.](../../manage/conferencing/conferencing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="99482-249">For more information about creating a conferencing policy, see [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).</span></span>
  

