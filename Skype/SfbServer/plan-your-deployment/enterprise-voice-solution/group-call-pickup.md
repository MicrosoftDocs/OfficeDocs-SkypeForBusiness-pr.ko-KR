---
title: 비즈니스용 Skype에서 그룹 통화 픽업 요금제
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
description: 비즈니스용 Skype Server Enterprise Voice에서 그룹 통화 픽업 계획을 통해 사용자가 원래 다른 사람에 게 제공 되는 통화에 응답할 수 있습니다.
ms.openlocfilehash: c729e2d672d104337820c44fa41c113dded3110f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187686"
---
# <a name="plan-for-group-call-pickup-in-skype-for-business"></a><span data-ttu-id="f7406-103">비즈니스용 Skype에서 그룹 통화 픽업 요금제</span><span class="sxs-lookup"><span data-stu-id="f7406-103">Plan for Group Call Pickup in Skype for Business</span></span>
 
<span data-ttu-id="f7406-104">비즈니스용 Skype Server Enterprise Voice에서 그룹 통화 픽업 계획을 통해 사용자가 원래 다른 사람에 게 제공 되는 통화에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-104">Planning for Group Call Pickup in Skype for Business Server Enterprise Voice, which enables users to answer calls originally intended for others.</span></span>
  
<span data-ttu-id="f7406-105">그룹 통화 픽업 사용자는 자신의 전화기에서 자신의 동료에 게 걸려오는 전화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-105">Group Call Pickup enables users to answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="f7406-106">이렇게 하면 다른 사용자가 통화 픽업 그룹 번호로 전화를 걸어 수신 전화를 받을 수 있도록 하 여 사용자의 회선 사용 가능 시간을 늘립니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-106">This increases the availability of a user's line by enabling other users to answer an incoming call by dialing a call pickup group number.</span></span> <span data-ttu-id="f7406-107">그룹 통화 픽업이 배포 되 면 음성 메일로 라우팅되는 수신 전화 수가 크게 줄어들 수 있으며,이는 조직 외부의 고객 으로부터 전화를 거는 경우 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-107">When Group Call Pickup is deployed, the number of incoming calls that are routed to voice mail can be significantly reduced, which is particularly useful for calls from customers who are external to your organization.</span></span>
  
<span data-ttu-id="f7406-108">그룹 통화 픽업 기능은 열려 있는 office 환경의 비즈니스 단위에 대해 특별히 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-108">The Group Call Pickup feature is designed in particular for business units in open office environments.</span></span> <span data-ttu-id="f7406-109">수신 전화는 의도 한 대상에만 연결 되기 때문에 방해가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-109">Incoming calls are not disruptive because they ring only at the intended destination.</span></span> <span data-ttu-id="f7406-110">그러나 반지를 듣는 다른 사용자는 그룹 번호로 전화를 걸어 전화를 계속 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-110">Other users who hear the ring, however, can still pick up the call simply by dialing the group number.</span></span> 
  
<span data-ttu-id="f7406-111">사용자가 열려 있는 사무실 레이아웃에 없거나 공통 책임을 공유 하는 사용자가 지리적으로 분산 되어 있는 환경에서 팀 전화는 가장 적합 한 솔루션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-111">In environments where users are not located in an open office layout, or where users who share a common responsibility are geographically distributed, team call presents the most suitable solution.</span></span> <span data-ttu-id="f7406-112">그룹 통화 픽업와 팀 통화 간의 주요 차이점은 그룹 통화 픽업, 수신 통화는 의도 한 대상 에서만 울릴 수 있지만, 누구 든 지 그룹 번호로 전화를 걸어 응답 하도록 선택할 수도 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-112">The primary difference between Group Call Pickup and team call is that, with Group Call Pickup, an incoming call rings only at the intended destination, but anyone can still choose to answer it by dialing a group number.</span></span> <span data-ttu-id="f7406-113">팀 통화를 통해 통화가 모든 팀 구성원의 전화를 걸고 팀의 모든 사용자가 전화를 선택 하 여 통화를 답변할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-113">With team call, the call rings at all the team members' phones, and any user in the team can pick up the phone to answer the call.</span></span> <span data-ttu-id="f7406-114">그룹 통화 픽업 및 팀 통화 간의 추가적인 차이점은 그룹 통화 픽업은 비즈니스용 Skype 서버를 통해 관리자가 관리 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-114">An additional difference between Group Call Pickup and team call is that Group Call Pickup is managed by an administrator, through Skype for Business Server.</span></span> <span data-ttu-id="f7406-115">팀 통화를 통해 최종 사용자는 비즈니스용 Skype 클라이언트를 사용 하 여 기능을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-115">With team call, end users manage the feature by using the Skype for Business client.</span></span> <span data-ttu-id="f7406-116">따라서 그룹 통화 픽업 기능을 사용 하면이 통화 관리 측면을 중앙 집중화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-116">With Group Call Pickup, therefore, this aspect of call management can be centralized.</span></span>
  
<span data-ttu-id="f7406-117">그룹 통화 픽업 기능은 통화 공원 응용 프로그램을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-117">Group Call Pickup is built on the Call Park application.</span></span> <span data-ttu-id="f7406-118">그룹 통화 픽업을 배포 하는 경우 통화 픽업 그룹 번호로 지정 된 별도의 내선 번호 범위를 사용 하 여 통화 공원 궤도 테이블을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-118">When you deploy Group Call Pickup, you configure the call park orbit table with separate ranges of extension numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="f7406-119">통화 공원 번호와 같은 통화 픽업 그룹 번호는 사용자 또는 전화가 할당 되지 않은 가상 확장명 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-119">Like call park orbit numbers, call pickup group numbers must be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="f7406-120">그룹 통화 픽업을 배포 하는 각 프런트 엔드 풀에는 하나 이상의 통화 픽업 그룹 번호 범위가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-120">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="f7406-121">그룹 번호의 범위는 비즈니스용 Skype 서버 배포에서 전역적으로 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-121">The group number ranges must be globally unique across the Skype for Business Server deployment.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f7406-122">전화 번호 궤도 테이블의 그룹 통화 픽업 번호로 지정 된 숫자 범위는 비즈니스용 Skype 서버 제어판을 사용 하 여 관리 하거나 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-122">Number ranges that are designated as Group Call Pickup numbers in the call park orbit table cannot be managed or viewed by using the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="f7406-123">통화 공원 궤도 테이블의 모든 번호 범위를 보는 유일한 방법은 비즈니스용 Skype Server Management Shell을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-123">The only way to see all the number ranges in the call park orbit table is to use Skype for Business Server Management Shell.</span></span> <span data-ttu-id="f7406-124">마찬가지로 그룹 통화 픽업 번호를 추가, 수정 또는 제거 하는 유일한 방법은 비즈니스용 Skype Server Management Shell을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-124">Similarly, the only way to add, modify, or remove Group Call Pickup numbers is to use Skype for Business Server Management Shell.</span></span> 
  
<span data-ttu-id="f7406-125">통화 픽업 그룹 번호를 구성한 후에는 통화 픽업 그룹에 사용자를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-125">After you configure the call pickup group numbers, you assign users to a call pickup group.</span></span> <span data-ttu-id="f7406-126">통화 픽업 그룹에 할당 된 모든 사용자는 다른 사용자가 통화를 대답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-126">Any user who is assigned to a call pickup group can have their calls answered by other users.</span></span> <span data-ttu-id="f7406-127">통화가 통화 픽업 그룹에 할당 된 사용자에 게 제공 되는 경우 전화를 거는 다른 모든 사용자가 전화를 통해 통화 픽업 그룹 번호를 수동으로 착신 전환 하 여 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-127">When a call comes in to a user who is assigned to a call pickup group, any other user who notices the call can answer it by manually dialing the call pickup group number.</span></span> <span data-ttu-id="f7406-128">통화를 선택 하는 사용자는 그룹의 구성원이 될 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-128">The user who picks up the call does not need to be a member of the group.</span></span> <span data-ttu-id="f7406-129">다른 사용자가 통화를 선택 하면 원래 호출한 번호로 알림이 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-129">When a call is picked up by another user, a notification is sent to the number originally called.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f7406-130">사용자는 한 통화 픽업 그룹의 구성원 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-130">A user can be a member of only one call pickup group.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f7406-131">비즈니스용 Skype 서버 배포의 사용자는 통화 픽업 그룹 구성원에 게 전화를 받을 수 있지만 전화를 받는 사람은 올바른 통화 픽업 그룹 번호를 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-131">Although any user in the Skype for Business Server deployment can answer a call to a call pickup group member, the person answering the call must know the correct call pickup group number to dial.</span></span> 
  
<span data-ttu-id="f7406-132">사용자가 그룹에 있는 여러 개의 전화가 연결 될 때 전화를 받기 위해 통화 픽업 그룹 번호로 전화를 걸면 사용자는 가장 오랫동안 연결 된 전화에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-132">If a user dials a call pickup group number to answer a call when multiple phones in the group are ringing, the user answers the call that has been ringing the longest.</span></span>
  
<span data-ttu-id="f7406-133">동시 연결 설정은 그룹 통화 픽업 사용자에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-133">Simultaneous ringing settings will work for users who have group call pickup.</span></span> <span data-ttu-id="f7406-134">즉, 그룹 통화 픽업이 있는 사용자에 대 한 통화가 구성 된 모든 대상에 대해 연결 되며 다른 사용자가 전화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-134">That is, a call made to a user who has Group Call Pickup will ring for all the configured destinations, and another user can answer the call.</span></span> <span data-ttu-id="f7406-135">이 규칙의 예외는 사용자가 모든 팀 구성원에 게 전화를 거는 동시 벨 울림을 구성할 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-135">The exception to this rule is when the user configures simultaneous ringing to call all the team members.</span></span>
  
<span data-ttu-id="f7406-136">그룹 통화 픽업을 사용 하 여 다음 통화 유형에 응답할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-136">Group Call Pickup cannot be used to answer the following types of calls:</span></span>
  
- <span data-ttu-id="f7406-137">전용 회선으로 전화 걸기</span><span class="sxs-lookup"><span data-stu-id="f7406-137">Calls to a private line</span></span>
    
- <span data-ttu-id="f7406-138">친구 및 가족 개인 정보 취급 방침에 배정 된 대화 상대에 게 전화 걸기</span><span class="sxs-lookup"><span data-stu-id="f7406-138">Calls from a contact who has been assigned the Friends and Family privacy relationship</span></span>
    
    > [!TIP]
    > <span data-ttu-id="f7406-139">통화 픽업 그룹의 구성원 인 사용자는 비즈니스용 Skype 클라이언트에서 해당 연락처를 개인 연락처로 표시 하 여 특정 전화를 그룹 통화 픽업을 통해 검색 하지 못하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-139">A user who is a member of a call pickup group can prevent certain calls from being retrieved through Group Call Pickup by marking the contact as a personal contact in the Skype for Business client.</span></span> <span data-ttu-id="f7406-140">연락처를 개인 연락처로 표시 하려면 연락처에 대 한 개인 정보 취급 방침을 친구나 가족에 게 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-140">To mark a contact as a personal contact, set the Privacy Relationship for the contact to Friends and Family.</span></span> <span data-ttu-id="f7406-141">그룹 통화 픽업을 사용 하 여 개인 정보 공개 범위를 친구 및 가족과 연락 하는 모든 수신 통화를 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-141">Any incoming call from contacts with the Privacy Relationship set to Friends and Family cannot be retrieved by using Group Call Pickup.</span></span> 
  
- <span data-ttu-id="f7406-142">오디오/비디오 통화의 비디오 부분</span><span class="sxs-lookup"><span data-stu-id="f7406-142">Video portion of audio/video calls</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="f7406-143">사용자가 오디오/비디오 통화에 응답 하면 사용자가 오디오만 받습니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-143">If a user answers an audio/video call, the user receives only the audio.</span></span> <span data-ttu-id="f7406-144">상대방이 전화를 걸거나 전화를 하는 사람이 통화를 escalation 하 여 비디오를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-144">Either the person calling or the person answering the call can escalate the call to add video.</span></span> 
  
- <span data-ttu-id="f7406-145">팀 통화 구성원으로 라우팅되는 동시 벨 통화</span><span class="sxs-lookup"><span data-stu-id="f7406-145">Simultaneous ringing calls that are routed to team call members</span></span>
    
- <span data-ttu-id="f7406-146">대리인에 게 라우팅된 통화</span><span class="sxs-lookup"><span data-stu-id="f7406-146">Calls routed to a delegate</span></span>
    
- <span data-ttu-id="f7406-147">응답 그룹에 게 전달 되는 통화</span><span class="sxs-lookup"><span data-stu-id="f7406-147">Calls routed to a response group</span></span>
    
<span data-ttu-id="f7406-148">다음 유형의 사용자는 그룹 통화 픽업에 참여할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-148">The following types of users cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="f7406-149">즉, 그룹 통화 픽업 그룹에 포함 하지 않아야 하며, 그룹 통화 픽업를 사용 하는 사용자에 게는 통화를 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-149">That is, they should not be included in a Group Call Pickup group, and they cannot pick up calls for users who have Group Call Pickup enabled.</span></span>
  
- <span data-ttu-id="f7406-150">하이브리드 배포에서 온라인으로 홈 인 사용자</span><span class="sxs-lookup"><span data-stu-id="f7406-150">Users who are homed online in a hybrid deployment</span></span>
    
- <span data-ttu-id="f7406-151">비즈니스용 Skype 서버 2015 풀 또는 Lync 2013 Server에 대 한 누적 업데이트를 포함 하는 Lync Server 2013 풀 (온-프레미스 배포의 경우 2 월 2013)에 속하지 않는 사용자</span><span class="sxs-lookup"><span data-stu-id="f7406-151">Users who are not homed on either a Skype for Business Server 2015 pool or a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013 in an on-premises deployment</span></span>
    
<span data-ttu-id="f7406-152">통화 픽업 그룹의 구성원에 게 전화를 걸 수 없는 경우 클라이언트 설정에 지정 된 대로 통화가 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-152">If no one answers a call to a member of a call pickup group, the call is routed as specified in the client settings.</span></span> <span data-ttu-id="f7406-153">즉, 클라이언트 설정에 지정 된 대로 통화는 보이스 메일로 이동 하거나 다른 목적지로 착신 전환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-153">That is, the call goes to voicemail or is forwarded to a different destination, as specified in the client settings.</span></span>
  
## <a name="deployment-and-requirements"></a><span data-ttu-id="f7406-154">배포 및 요구 사항</span><span class="sxs-lookup"><span data-stu-id="f7406-154">Deployment and requirements</span></span>

<span data-ttu-id="f7406-155">그룹 통화 픽업 기능은 엔터프라이즈 음성과 통화 공원 응용 프로그램을 배포할 때 자동으로 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-155">Group Call Pickup is automatically deployed when you deploy Enterprise Voice and the Call Park application.</span></span> <span data-ttu-id="f7406-156">통화 픽업 그룹 번호로 지정 된 별도의 숫자 범위를 사용 하 여 통화 공원 표를 구성한 다음 픽업 그룹을 호출 하 고 그룹 통화 픽업으로 사용자를 설정 하 여 그룹 통화 픽업을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-156">You enable Group Call Pickup by configuring the Call Park orbit table with separate ranges of numbers designated as call pickup group numbers, and then by assigning users to call pickup groups and enabling the users for Group Call Pickup.</span></span>
  
## <a name="clients-supported-for-group-call-pickup"></a><span data-ttu-id="f7406-157">그룹 통화 픽업 지원 클라이언트</span><span class="sxs-lookup"><span data-stu-id="f7406-157">Clients supported for Group Call Pickup</span></span>

<span data-ttu-id="f7406-158">그룹 통화 픽업 회원에 게 전화를 받기 위해 다음 클라이언트를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-158">Any of the following clients can be used to answer calls to Group Call Pickup members:</span></span>
  
- <span data-ttu-id="f7406-159">비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="f7406-159">Skype for Business</span></span>
    
- <span data-ttu-id="f7406-160">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="f7406-160">Lync 2013</span></span>
    
- <span data-ttu-id="f7406-161">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="f7406-161">Lync 2010</span></span>
    
- <span data-ttu-id="f7406-162">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="f7406-162">Lync Phone Edition</span></span>
    
> [!NOTE]
> <span data-ttu-id="f7406-163">사용자는 이러한 클라이언트 중 하나를 사용 하 여 그룹 통화 픽업 회원에 게 전화를 걸 수 있지만, 사용자는 비즈니스용 Skype 서버 풀 또는 Lync Server 2013 2013의 누적 업데이트를 사용 하는 Lync Server 2013 풀에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-163">Users can use any of these clients to answer calls to Group Call Pickup members, but the users must be homed on a Skype for Business Server pool or a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="f7406-164">다음 클라이언트 및 장치는 그룹 통화 픽업 구성원에 대 한 통화를 선택 하는 데 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-164">The following clients and devices are not supported for picking up calls to Group Call Pickup members:</span></span>
  
- <span data-ttu-id="f7406-165">Lync 모바일</span><span class="sxs-lookup"><span data-stu-id="f7406-165">Lync Mobile</span></span>
    
- <span data-ttu-id="f7406-166">Windows 8 및 Windows RT 용 Lync 앱</span><span class="sxs-lookup"><span data-stu-id="f7406-166">Lync app for Windows 8 and Windows RT</span></span>
    
- <span data-ttu-id="f7406-167">IPad 용 Lync</span><span class="sxs-lookup"><span data-stu-id="f7406-167">Lync for iPad</span></span>
    
- <span data-ttu-id="f7406-168">아날로그 전화</span><span class="sxs-lookup"><span data-stu-id="f7406-168">Analog phones</span></span>
    
- <span data-ttu-id="f7406-169">PSTN (공개 전화 통신망) 번호가 있는 전화</span><span class="sxs-lookup"><span data-stu-id="f7406-169">Phones with public switched telephone network (PSTN) numbers</span></span>
    
## <a name="capacity-planning"></a><span data-ttu-id="f7406-170">용량 계획</span><span class="sxs-lookup"><span data-stu-id="f7406-170">Capacity planning</span></span>

<span data-ttu-id="f7406-171">다음 표에서는 용량 계획 요구 사항의 기준으로 사용할 수 있는 그룹 통화 픽업 사용자 모델에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-171">The following table describes the Group Call Pickup user model that you can use as the basis for capacity planning requirements.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f7406-172">그룹 통화 픽업는 통화 공원 응용 프로그램을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-172">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="f7406-173">재해 복구 용량 계획을 위해 쌍으로 연결 된 풀의 각 풀은 그룹 통화 픽업을 포함 한 통화 공원 서비스의 작업량을 두 풀에서 처리할 수 있어야 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="f7406-173">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services, including Group Call Pickup, in both pools.</span></span> 
  
<span data-ttu-id="f7406-174">**그룹 통화 픽업 사용자 모델**</span><span class="sxs-lookup"><span data-stu-id="f7406-174">**Group Call Pickup User Model**</span></span>

|<span data-ttu-id="f7406-175">**미터**</span><span class="sxs-lookup"><span data-stu-id="f7406-175">**Metric**</span></span>|<span data-ttu-id="f7406-176">**프런트 엔드 풀 <br/> 단위 (프런트 엔드 서버 8 개)**</span><span class="sxs-lookup"><span data-stu-id="f7406-176">**Per Front End pool  <br/>  (with 8 Front End Servers)**</span></span>|<span data-ttu-id="f7406-177">**스탠더드 에디션 서버 당**</span><span class="sxs-lookup"><span data-stu-id="f7406-177">**Per Standard Edition server**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f7406-178">그룹 당 권장 되는 사용자 수</span><span class="sxs-lookup"><span data-stu-id="f7406-178">Recommended number of users per group</span></span>  <br/> |<span data-ttu-id="f7406-179">50</span><span class="sxs-lookup"><span data-stu-id="f7406-179">50</span></span>  <br/> |<span data-ttu-id="f7406-180">50</span><span class="sxs-lookup"><span data-stu-id="f7406-180">50</span></span>  <br/> |
|<span data-ttu-id="f7406-181">추천 그룹 수</span><span class="sxs-lookup"><span data-stu-id="f7406-181">Recommended number of groups</span></span>  <br/> |<span data-ttu-id="f7406-182">500</span><span class="sxs-lookup"><span data-stu-id="f7406-182">500</span></span>  <br/> |<span data-ttu-id="f7406-183">60</span><span class="sxs-lookup"><span data-stu-id="f7406-183">60</span></span>  <br/> |
|<span data-ttu-id="f7406-184">그룹 통화 픽업에 사용할 수 있는 풀 당 최대 사용자 수</span><span class="sxs-lookup"><span data-stu-id="f7406-184">Maximum number of users per pool enabled for Group Call Pickup</span></span>  <br/> |<span data-ttu-id="f7406-185">25000</span><span class="sxs-lookup"><span data-stu-id="f7406-185">25,000</span></span>  <br/> |<span data-ttu-id="f7406-186">3000</span><span class="sxs-lookup"><span data-stu-id="f7406-186">3,000</span></span>  <br/> |
|<span data-ttu-id="f7406-187">분당 그룹 통화 픽업에 대해 사용 하도록 설정 된 총 사용자에 대 한 최대 수신 통화 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-187">Maximum rate of incoming calls to total users enabled for Group Call Pickup per pool per minute</span></span>  <br/> |<span data-ttu-id="f7406-188">500</span><span class="sxs-lookup"><span data-stu-id="f7406-188">500</span></span>  <br/> |<span data-ttu-id="f7406-189">60</span><span class="sxs-lookup"><span data-stu-id="f7406-189">60</span></span>  <br/> |
|<span data-ttu-id="f7406-190">분 당 그룹 통화 픽업 트럭을 사용 하 여 사용자가 검색 한 통화의 최대 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-190">Maximum rate of calls retrieved by users with Group Call Pickup per pool per minute</span></span>  <br/> |<span data-ttu-id="f7406-191">200</span><span class="sxs-lookup"><span data-stu-id="f7406-191">200</span></span>  <br/> |<span data-ttu-id="f7406-192">km</span><span class="sxs-lookup"><span data-stu-id="f7406-192">25</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="f7406-193">프런트 엔드 서버를 8 개 미만으로 하는 프런트 엔드 풀의 경우 메트릭을 선형으로 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-193">For Front End pools that have fewer than eight Front End Servers, calculate the metrics linearly.</span></span> <span data-ttu-id="f7406-194">예를 들어 프런트 엔드 풀에 프런트 엔드 서버가 한 개 있는 경우 최대 로드를 표에 표시 된 값의 1/8로 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-194">For example, if your Front End pool has one Front End Server, calculate the maximum load as 1/8 of the values shown in the table.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f7406-195">풀 당 최대 사용자 수를 초과 하지 않는 한 그룹 당 권장 되는 사용자 수와 그룹 수를 늘리거나 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-195">You can increase or decrease the recommended number of users per group and number of groups as long as you do not exceed the maximum number of users per pool.</span></span> <span data-ttu-id="f7406-196">예를 들어 그룹 통화 픽업에 대해 사용 하도록 설정 된 사용자 수가 최대 사용자 모델 (즉, 120 그룹 시간 25 명의 사용자는 그룹 통화 픽업에 대해 사용 하도록 설정 3000 되어 있음)에 포함 되어 있기 때문에 Standard Edition 서버는 그룹당 25 명의 사용자를 갖는 120 그룹을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7406-196">For example, your Standard Edition server can have 120 groups with 25 users per group because the number of users enabled for Group Call Pickup is still within the user model maximum (that is, 120 groups times 25 users is 3,000 users enabled for Group Call Pickup).</span></span> 
  

