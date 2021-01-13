---
title: 비즈니스용 Skype의 그룹 통화 선택 계획
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
description: 사용자가 원래 다른 사용자를 위해 의도한 통화에 응답할 수 있도록 하는 비즈니스용 Skype Enterprise Voice 그룹 통화 선택 계획
ms.openlocfilehash: 874b9385352a8c51d9c9a356dd0ccc2ca3070601
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825618"
---
# <a name="plan-for-group-call-pickup-in-skype-for-business"></a><span data-ttu-id="2224b-103">비즈니스용 Skype의 그룹 통화 선택 계획</span><span class="sxs-lookup"><span data-stu-id="2224b-103">Plan for Group Call Pickup in Skype for Business</span></span>
 
<span data-ttu-id="2224b-104">사용자가 원래 다른 사용자를 위해 의도한 통화에 응답할 수 있도록 하는 비즈니스용 Skype 서버 Enterprise Voice 그룹 통화 선택 계획</span><span class="sxs-lookup"><span data-stu-id="2224b-104">Planning for Group Call Pickup in Skype for Business Server Enterprise Voice, which enables users to answer calls originally intended for others.</span></span>
  
<span data-ttu-id="2224b-105">그룹 통화 Pickup을 사용하면 사용자가 자신의 휴대폰에서 동료에게 걸려오는 전화에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-105">Group Call Pickup enables users to answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="2224b-106">이렇게 하면 통화 수신 그룹 번호로 전화를 걸면 다른 사용자가 수신 전화에 응답할 수 있으므로 사용자 줄의 가용성이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-106">This increases the availability of a user's line by enabling other users to answer an incoming call by dialing a call pickup group number.</span></span> <span data-ttu-id="2224b-107">그룹 통화 수신이 배포되면 음성 메일로 라우팅되는 수신 전화 수가 크게 감소할 수 있습니다. 이는 특히 조직 외부의 고객의 통화에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-107">When Group Call Pickup is deployed, the number of incoming calls that are routed to voice mail can be significantly reduced, which is particularly useful for calls from customers who are external to your organization.</span></span>
  
<span data-ttu-id="2224b-108">그룹 통화 선택 기능은 열려 있는 사무실 환경의 업무 단위에 특히 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-108">The Group Call Pickup feature is designed in particular for business units in open office environments.</span></span> <span data-ttu-id="2224b-109">수신 전화는 의도한 대상에서만 울리기 때문에 중단되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-109">Incoming calls are not disruptive because they ring only at the intended destination.</span></span> <span data-ttu-id="2224b-110">그러나 링을 듣는 다른 사용자는 그룹 번호로 전화를 걸기만 하여 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-110">Other users who hear the ring, however, can still pick up the call simply by dialing the group number.</span></span> 
  
<span data-ttu-id="2224b-111">사용자가 열린 사무실 레이아웃에 있지 않은 환경이나 공통 책임을 공유하는 사용자가 지리적으로 분산되어 있는 환경에서 팀 통화는 가장 적합한 솔루션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-111">In environments where users are not located in an open office layout, or where users who share a common responsibility are geographically distributed, team call presents the most suitable solution.</span></span> <span data-ttu-id="2224b-112">그룹 통화 수신과 팀 통화의 주요 차이점은 그룹 통화 Pickup을 사용할 경우 수신 전화가 의도한 대상에서만 벨이 울리지만 누구나 그룹 번호로 전화를 걸고 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-112">The primary difference between Group Call Pickup and team call is that, with Group Call Pickup, an incoming call rings only at the intended destination, but anyone can still choose to answer it by dialing a group number.</span></span> <span data-ttu-id="2224b-113">팀 통화를 통해 통화가 모든 팀 구성원의 전화에서 울리며, 팀의 모든 사용자는 전화를 통해 통화에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-113">With team call, the call rings at all the team members' phones, and any user in the team can pick up the phone to answer the call.</span></span> <span data-ttu-id="2224b-114">그룹 통화 선택과 팀 통화 간의 추가적인 차이점은 그룹 통화 Pickup은 관리자가 비즈니스용 Skype 서버를 통해 관리하다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-114">An additional difference between Group Call Pickup and team call is that Group Call Pickup is managed by an administrator, through Skype for Business Server.</span></span> <span data-ttu-id="2224b-115">팀 통화를 사용하면 최종 사용자가 비즈니스용 Skype 클라이언트를 사용하여 기능을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-115">With team call, end users manage the feature by using the Skype for Business client.</span></span> <span data-ttu-id="2224b-116">따라서 그룹 통화 Pickup을 사용하여 이러한 통화 관리 측면을 중앙 집중화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-116">With Group Call Pickup, therefore, this aspect of call management can be centralized.</span></span>
  
<span data-ttu-id="2224b-117">그룹 통화 선택은 통화 파크 응용 프로그램을 통해 구축됩니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-117">Group Call Pickup is built on the Call Park application.</span></span> <span data-ttu-id="2224b-118">그룹 통화 선택을 배포할 때 통화 Pickup 그룹 번호로 지정된 별도의 내선 번호 범위로 통화 파크 파크 번호 테이블을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-118">When you deploy Group Call Pickup, you configure the call park orbit table with separate ranges of extension numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="2224b-119">통화 걸기 그룹 번호와 마찬가지로, 통화 선택 그룹 번호는 사용자에게 할당된 사용자나 전화가 없는 가상 내선 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-119">Like call park orbit numbers, call pickup group numbers must be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="2224b-120">그룹 통화 선택을 배포하는 각 프런트 엔드 풀에는 하나 이상의 통화 선택 그룹 번호 범위가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-120">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="2224b-121">그룹 번호 범위는 비즈니스용 Skype 서버 배포에서 전역적으로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-121">The group number ranges must be globally unique across the Skype for Business Server deployment.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2224b-122">통화 파기 번호 테이블에서 그룹 통화 선택 번호로 지정된 번호 범위는 비즈니스용 Skype 서버 제어판을 사용하여 관리하거나 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-122">Number ranges that are designated as Group Call Pickup numbers in the call park orbit table cannot be managed or viewed by using the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="2224b-123">통화 파기 번호 테이블의 모든 번호 범위를 보는 유일한 방법은 비즈니스용 Skype 서버 관리 셸을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-123">The only way to see all the number ranges in the call park orbit table is to use Skype for Business Server Management Shell.</span></span> <span data-ttu-id="2224b-124">마찬가지로 그룹 통화 선택 번호를 추가, 수정 또는 제거하는 유일한 방법은 비즈니스용 Skype 서버 관리 셸을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-124">Similarly, the only way to add, modify, or remove Group Call Pickup numbers is to use Skype for Business Server Management Shell.</span></span> 
  
<span data-ttu-id="2224b-125">통화 선택 그룹 번호를 구성한 후 사용자를 통화 Pickup 그룹에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-125">After you configure the call pickup group numbers, you assign users to a call pickup group.</span></span> <span data-ttu-id="2224b-126">통화 선택 그룹에 할당된 사용자는 다른 사용자가 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-126">Any user who is assigned to a call pickup group can have their calls answered by other users.</span></span> <span data-ttu-id="2224b-127">통화를 Pickup 그룹에 할당된 사용자에게 전화를 걸면 통화를 발견한 다른 사용자가 수동으로 통화 Pickup 그룹 번호로 전화를 걸면 해당 통화에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-127">When a call comes in to a user who is assigned to a call pickup group, any other user who notices the call can answer it by manually dialing the call pickup group number.</span></span> <span data-ttu-id="2224b-128">통화를 선택한 사용자는 그룹의 구성원이 아니어도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-128">The user who picks up the call does not need to be a member of the group.</span></span> <span data-ttu-id="2224b-129">다른 사용자가 전화를 걸면 원래 호출된 번호로 알림이 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-129">When a call is picked up by another user, a notification is sent to the number originally called.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2224b-130">사용자는 하나의 통화 Pickup 그룹의 구성원일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-130">A user can be a member of only one call pickup group.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2224b-131">비즈니스용 Skype 서버 배포의 모든 사용자가 통화 Pickup 그룹 구성원에게 전화를 걸 수 있는 경우 전화를 거는 사람은 전화를 걸 올바른 통화 Pickup 그룹 번호를 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-131">Although any user in the Skype for Business Server deployment can answer a call to a call pickup group member, the person answering the call must know the correct call pickup group number to dial.</span></span> 
  
<span data-ttu-id="2224b-132">그룹의 여러 전화가 울리는 경우 사용자가 통화에 응답하기 위해 통화 Pickup 그룹 번호로 전화를 걸면 가장 긴 벨이 울리는 통화에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-132">If a user dials a call pickup group number to answer a call when multiple phones in the group are ringing, the user answers the call that has been ringing the longest.</span></span>
  
<span data-ttu-id="2224b-133">동시 전화 울림 설정은 그룹 통화 Pickup이 있는 사용자에 대해 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-133">Simultaneous ringing settings will work for users who have group call pickup.</span></span> <span data-ttu-id="2224b-134">즉, 그룹 통화 Pickup이 있는 사용자에게 걸린 통화가 구성된 모든 대상에 대해 벨이 울리며 다른 사용자가 통화에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-134">That is, a call made to a user who has Group Call Pickup will ring for all the configured destinations, and another user can answer the call.</span></span> <span data-ttu-id="2224b-135">이 규칙의 예외는 사용자가 모든 팀 구성원에게 전화를 걸도록 동시 벨 울림을 구성한 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-135">The exception to this rule is when the user configures simultaneous ringing to call all the team members.</span></span>
  
<span data-ttu-id="2224b-136">그룹 통화 Pickup을 사용하여 다음 유형의 통화에 응답할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-136">Group Call Pickup cannot be used to answer the following types of calls:</span></span>
  
- <span data-ttu-id="2224b-137">전용선 호출</span><span class="sxs-lookup"><span data-stu-id="2224b-137">Calls to a private line</span></span>
    
- <span data-ttu-id="2224b-138">친구 및 가족 개인 정보 보호 관계가 할당된 연락처의 통화</span><span class="sxs-lookup"><span data-stu-id="2224b-138">Calls from a contact who has been assigned the Friends and Family privacy relationship</span></span>
    
    > [!TIP]
    > <span data-ttu-id="2224b-139">통화 선택 그룹의 구성원인 사용자는 연락처를 비즈니스용 Skype 클라이언트에서 개인 연락처로 표시하여 그룹 통화 Pickup을 통해 특정 통화가 검색되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-139">A user who is a member of a call pickup group can prevent certain calls from being retrieved through Group Call Pickup by marking the contact as a personal contact in the Skype for Business client.</span></span> <span data-ttu-id="2224b-140">연락처를 개인 연락처로 표시하기 위해 연락처의 개인 정보 관계를 친구 및 가족으로 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="2224b-140">To mark a contact as a personal contact, set the Privacy Relationship for the contact to Friends and Family.</span></span> <span data-ttu-id="2224b-141">개인 정보 관계가 Friends 및 Family로 설정된 연락처로부터의 수신 전화는 그룹 통화 Pickup을 사용하여 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-141">Any incoming call from contacts with the Privacy Relationship set to Friends and Family cannot be retrieved by using Group Call Pickup.</span></span> 
  
- <span data-ttu-id="2224b-142">오디오/비디오 통화의 비디오 부분</span><span class="sxs-lookup"><span data-stu-id="2224b-142">Video portion of audio/video calls</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="2224b-143">사용자가 오디오/비디오 통화에 응답하면 사용자는 오디오만 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-143">If a user answers an audio/video call, the user receives only the audio.</span></span> <span data-ttu-id="2224b-144">통화를 하는 사람 또는 통화에 응답한 사람이 전화를 에스컬레이터하여 비디오를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-144">Either the person calling or the person answering the call can escalate the call to add video.</span></span> 
  
- <span data-ttu-id="2224b-145">팀 통화 구성원에게 라우팅된 동시 전화 울림 통화</span><span class="sxs-lookup"><span data-stu-id="2224b-145">Simultaneous ringing calls that are routed to team call members</span></span>
    
- <span data-ttu-id="2224b-146">대리인에게 라우팅된 통화</span><span class="sxs-lookup"><span data-stu-id="2224b-146">Calls routed to a delegate</span></span>
    
- <span data-ttu-id="2224b-147">응답 그룹으로 라우팅된 통화</span><span class="sxs-lookup"><span data-stu-id="2224b-147">Calls routed to a response group</span></span>
    
<span data-ttu-id="2224b-148">다음 유형의 사용자는 그룹 통화 Pickup에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-148">The following types of users cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="2224b-149">즉, 그룹 통화 Pickup 그룹에 포함되지 말고 그룹 통화 Pickup을 사용하도록 설정된 사용자에 대한 통화를 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-149">That is, they should not be included in a Group Call Pickup group, and they cannot pick up calls for users who have Group Call Pickup enabled.</span></span>
  
- <span data-ttu-id="2224b-150">하이브리드 배포에서 온라인에 있는 사용자</span><span class="sxs-lookup"><span data-stu-id="2224b-150">Users who are homed online in a hybrid deployment</span></span>
    
- <span data-ttu-id="2224b-151">비즈니스용 Skype 서버 2015 풀 또는 Lync Server 2013용 누적 업데이트가 있는 Lync Server 2013 풀에 있지 않은 사용자: 온-프레미스 배포의 2013년 2월</span><span class="sxs-lookup"><span data-stu-id="2224b-151">Users who are not homed on either a Skype for Business Server 2015 pool or a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013 in an on-premises deployment</span></span>
    
<span data-ttu-id="2224b-152">통화 선택 그룹의 구성원에게 전화를 응답하는 사용자가 없는 경우 통화는 클라이언트 설정에 지정된 것으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-152">If no one answers a call to a member of a call pickup group, the call is routed as specified in the client settings.</span></span> <span data-ttu-id="2224b-153">즉, 통화가 음성으로 이동되거나 클라이언트 설정에 지정된 다른 대상으로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-153">That is, the call goes to voicemail or is forwarded to a different destination, as specified in the client settings.</span></span>
  
## <a name="deployment-and-requirements"></a><span data-ttu-id="2224b-154">배포 및 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2224b-154">Deployment and requirements</span></span>

<span data-ttu-id="2224b-155">그룹 통화 Pickup은 통화 파크 응용 프로그램을 배포할 Enterprise Voice 자동으로 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-155">Group Call Pickup is automatically deployed when you deploy Enterprise Voice and the Call Park application.</span></span> <span data-ttu-id="2224b-156">통화 선택 그룹 번호로 지정된 별도의 번호 범위로 통화 파킹된 통화 번호 테이블을 구성한 다음 사용자에게 Pickup 그룹에 통화를 할당하고 사용자가 그룹 통화 선택을 사용하도록 설정하여 그룹 통화 선택을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-156">You enable Group Call Pickup by configuring the Call Park orbit table with separate ranges of numbers designated as call pickup group numbers, and then by assigning users to call pickup groups and enabling the users for Group Call Pickup.</span></span>
  
## <a name="clients-supported-for-group-call-pickup"></a><span data-ttu-id="2224b-157">그룹 통화 Pickup에 지원되는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="2224b-157">Clients supported for Group Call Pickup</span></span>

<span data-ttu-id="2224b-158">다음 클라이언트를 사용하여 그룹 통화 Pickup 구성원에 대한 통화에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-158">Any of the following clients can be used to answer calls to Group Call Pickup members:</span></span>
  
- <span data-ttu-id="2224b-159">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="2224b-159">Skype for Business</span></span>
    
- <span data-ttu-id="2224b-160">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="2224b-160">Lync 2013</span></span>
    
- <span data-ttu-id="2224b-161">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="2224b-161">Lync 2010</span></span>
    
- <span data-ttu-id="2224b-162">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="2224b-162">Lync Phone Edition</span></span>
    
> [!NOTE]
> <span data-ttu-id="2224b-163">사용자는 이러한 클라이언트를 사용하여 그룹 통화 선택 구성원에 대한 통화에 응답할 수 있지만 사용자는 Lync Server 2013용 누적 업데이트가 있는 비즈니스용 Skype 서버 풀 또는 Lync Server 2013 풀에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-163">Users can use any of these clients to answer calls to Group Call Pickup members, but the users must be homed on a Skype for Business Server pool or a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="2224b-164">다음 클라이언트 및 장치는 그룹 통화 Pickup 구성원에 대한 통화를 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-164">The following clients and devices are not supported for picking up calls to Group Call Pickup members:</span></span>
  
- <span data-ttu-id="2224b-165">Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="2224b-165">Lync Mobile</span></span>
    
- <span data-ttu-id="2224b-166">Windows 8 및 Windows RT용 Lync 앱</span><span class="sxs-lookup"><span data-stu-id="2224b-166">Lync app for Windows 8 and Windows RT</span></span>
    
- <span data-ttu-id="2224b-167">Lync for iPad</span><span class="sxs-lookup"><span data-stu-id="2224b-167">Lync for iPad</span></span>
    
- <span data-ttu-id="2224b-168">아날로그 전화</span><span class="sxs-lookup"><span data-stu-id="2224b-168">Analog phones</span></span>
    
- <span data-ttu-id="2224b-169">PSTN(Public Switched Telephone Network) 번호가 있는 전화</span><span class="sxs-lookup"><span data-stu-id="2224b-169">Phones with public switched telephone network (PSTN) numbers</span></span>
    
## <a name="capacity-planning"></a><span data-ttu-id="2224b-170">용량 계획</span><span class="sxs-lookup"><span data-stu-id="2224b-170">Capacity planning</span></span>

<span data-ttu-id="2224b-171">다음 표에서는 용량 계획 요구 사항의 기준으로 사용할 수 있는 그룹 통화 Pickup 사용자 모델에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-171">The following table describes the Group Call Pickup user model that you can use as the basis for capacity planning requirements.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2224b-172">그룹 통화 Pickup은 통화 파크 응용 프로그램을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-172">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="2224b-173">재해 복구 용량 계획을 위해 페어링된 풀의 각 풀은 두 풀 모두에서 그룹 통화 선택을 비롯한 통화 파크 서비스에 대한 작업을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-173">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services, including Group Call Pickup, in both pools.</span></span> 
  
<span data-ttu-id="2224b-174">**그룹 통화 Pickup 사용자 모델**</span><span class="sxs-lookup"><span data-stu-id="2224b-174">**Group Call Pickup User Model**</span></span>

|<span data-ttu-id="2224b-175">**메트릭**</span><span class="sxs-lookup"><span data-stu-id="2224b-175">**Metric**</span></span>|<span data-ttu-id="2224b-176">**프런트 엔드  <br/>  풀당(프런트 엔드 서버 8대)**</span><span class="sxs-lookup"><span data-stu-id="2224b-176">**Per Front End pool  <br/>  (with 8 Front End Servers)**</span></span>|<span data-ttu-id="2224b-177">**Standard Edition Server별**</span><span class="sxs-lookup"><span data-stu-id="2224b-177">**Per Standard Edition server**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2224b-178">그룹당 권장되는 사용자 수</span><span class="sxs-lookup"><span data-stu-id="2224b-178">Recommended number of users per group</span></span>  <br/> |<span data-ttu-id="2224b-179">50</span><span class="sxs-lookup"><span data-stu-id="2224b-179">50</span></span>  <br/> |<span data-ttu-id="2224b-180">50</span><span class="sxs-lookup"><span data-stu-id="2224b-180">50</span></span>  <br/> |
|<span data-ttu-id="2224b-181">권장되는 그룹 수</span><span class="sxs-lookup"><span data-stu-id="2224b-181">Recommended number of groups</span></span>  <br/> |<span data-ttu-id="2224b-182">500</span><span class="sxs-lookup"><span data-stu-id="2224b-182">500</span></span>  <br/> |<span data-ttu-id="2224b-183">60</span><span class="sxs-lookup"><span data-stu-id="2224b-183">60</span></span>  <br/> |
|<span data-ttu-id="2224b-184">그룹 통화 Pickup에 대해 사용하도록 설정된 풀당 최대 사용자 수</span><span class="sxs-lookup"><span data-stu-id="2224b-184">Maximum number of users per pool enabled for Group Call Pickup</span></span>  <br/> |<span data-ttu-id="2224b-185">25,000</span><span class="sxs-lookup"><span data-stu-id="2224b-185">25,000</span></span>  <br/> |<span data-ttu-id="2224b-186">3,000</span><span class="sxs-lookup"><span data-stu-id="2224b-186">3,000</span></span>  <br/> |
|<span data-ttu-id="2224b-187">풀당 분당 그룹 통화 수신을 사용하도록 설정된 총 사용자에 대한 최대 수신 전화 속도</span><span class="sxs-lookup"><span data-stu-id="2224b-187">Maximum rate of incoming calls to total users enabled for Group Call Pickup per pool per minute</span></span>  <br/> |<span data-ttu-id="2224b-188">500</span><span class="sxs-lookup"><span data-stu-id="2224b-188">500</span></span>  <br/> |<span data-ttu-id="2224b-189">60</span><span class="sxs-lookup"><span data-stu-id="2224b-189">60</span></span>  <br/> |
|<span data-ttu-id="2224b-190">풀당 분당 그룹 통화 선택을 사용하여 사용자가 검색한 최대 통화 수</span><span class="sxs-lookup"><span data-stu-id="2224b-190">Maximum rate of calls retrieved by users with Group Call Pickup per pool per minute</span></span>  <br/> |<span data-ttu-id="2224b-191">200</span><span class="sxs-lookup"><span data-stu-id="2224b-191">200</span></span>  <br/> |<span data-ttu-id="2224b-192">25</span><span class="sxs-lookup"><span data-stu-id="2224b-192">25</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="2224b-193">프런트 엔드 서버가 8대 미만인 프런트 엔드 풀의 경우 메트릭을 선형으로 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-193">For Front End pools that have fewer than eight Front End Servers, calculate the metrics linearly.</span></span> <span data-ttu-id="2224b-194">예를 들어 프런트 엔드 풀에 프런트 엔드 서버가 하나인 경우 최대 부하를 표에 표시된 값의 1/8로 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-194">For example, if your Front End pool has one Front End Server, calculate the maximum load as 1/8 of the values shown in the table.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2224b-195">풀당 최대 사용자 수를 초과하지 않는 한 그룹 및 그룹 수에 따라 권장되는 사용자 수를 늘리거나 줄이면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-195">You can increase or decrease the recommended number of users per group and number of groups as long as you do not exceed the maximum number of users per pool.</span></span> <span data-ttu-id="2224b-196">예를 들어, 그룹 통화 선택을 사용하도록 설정된 사용자 수가 여전히 사용자 모델 최대값 내에 있기 때문에 Standard Edition 서버는 그룹당 25명이 있는 120개 그룹을 사용할 수 있습니다. 즉, 120개 그룹에서 25명 사용자가 그룹 통화 선택을 사용하도록 설정된 경우 3,000명입니다.</span><span class="sxs-lookup"><span data-stu-id="2224b-196">For example, your Standard Edition server can have 120 groups with 25 users per group because the number of users enabled for Group Call Pickup is still within the user model maximum (that is, 120 groups times 25 users is 3,000 users enabled for Group Call Pickup).</span></span> 
  

