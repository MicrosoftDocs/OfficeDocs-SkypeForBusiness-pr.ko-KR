---
title: 'Lync Server 2013: 그룹 통화 픽업 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Group Call Pickup
ms:assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945623(v=OCS.15)
ms:contentKeyID: 51541466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0efc85b28a689b43d024d9996211a70dcd91cee0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755552"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="11002-102">Lync Server 2013의 그룹 통화 픽업 개요</span><span class="sxs-lookup"><span data-stu-id="11002-102">Overview of Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11002-103">_**마지막으로 수정한 주제:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="11002-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="11002-104">그룹 통화 픽업 (Lync Server 2013 2013 년 2 월)에 대 한 누적 업데이트의 새로운 기능인 사용자는 자신의 전화기에서 자신의 동료에 게 걸려오는 전화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11002-104">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="11002-105">이 새로운 기능은 다른 사용자가 통화 픽업 그룹 번호로 전화를 걸어 수신 전화를 받을 수 있도록 하 여 사용자의 회선 사용 가능성을 높입니다.</span><span class="sxs-lookup"><span data-stu-id="11002-105">This new feature increases the availability of a user's line by enabling other users to answer an incoming call by dialing a call pickup group number.</span></span> <span data-ttu-id="11002-106">그룹 통화 픽업이 배포 되 면 음성 메일로 라우팅되는 수신 전화 수가 크게 줄어들 수 있으며,이는 조직 외부의 고객 으로부터 전화를 거는 경우 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="11002-106">When Group Call Pickup is deployed, the number of incoming calls that are routed to voice mail can be significantly reduced, which is particularly useful for calls from customers who are external to your organization.</span></span>

<span data-ttu-id="11002-107">그룹 통화 픽업 기능은 열려 있는 office 환경의 비즈니스 단위에 대해 특별히 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="11002-107">The Group Call Pickup feature is designed in particular for business units in open office environments.</span></span> <span data-ttu-id="11002-108">수신 전화는 의도 한 대상에만 연결 되기 때문에 방해가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11002-108">Incoming calls are not disruptive because they ring only at the intended destination.</span></span> <span data-ttu-id="11002-109">그러나 반지를 듣는 다른 사용자는 그룹 번호로 전화를 걸어 전화를 계속 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11002-109">Other users who hear the ring, however, can still pick up the call simply by dialing the group number.</span></span>

<span data-ttu-id="11002-110">사용자가 열려 있는 사무실 레이아웃에 없거나 공통 책임을 공유 하는 사용자가 지리적으로 분산 되어 있는 환경에서 팀 전화는 가장 적합 한 솔루션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="11002-110">In environments where users are not located in an open office layout, or where users who share a common responsibility are geographically distributed, team call presents the most suitable solution.</span></span> <span data-ttu-id="11002-111">그룹 통화 픽업와 팀 통화 간의 주요 차이점은 그룹 통화 픽업, 수신 통화는 의도 한 대상 에서만 울릴 수 있지만, 누구 든 지 그룹 번호로 전화를 걸어 응답 하도록 선택할 수도 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="11002-111">The primary difference between Group Call Pickup and team call is that, with Group Call Pickup, an incoming call rings only at the intended destination, but anyone can still choose to answer it by dialing a group number.</span></span> <span data-ttu-id="11002-112">팀 통화를 통해 통화가 모든 팀 구성원의 전화를 걸고 팀의 모든 사용자가 전화를 선택 하 여 통화를 답변할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11002-112">With team call, the call rings at all the team members' phones, and any user in the team can pick up the phone to answer the call.</span></span> <span data-ttu-id="11002-113">그룹 통화 픽업 및 팀 통화 간의 추가적인 차이점은 그룹 통화 픽업은 관리자가 Lync Server를 통해 관리 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="11002-113">An additional difference between Group Call Pickup and team call is that Group Call Pickup is managed by an administrator, through Lync Server.</span></span> <span data-ttu-id="11002-114">팀 호출을 통해 최종 사용자는 Lync 클라이언트를 사용 하 여 기능을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="11002-114">With team call, end users manage the feature by using the Lync client.</span></span> <span data-ttu-id="11002-115">따라서 그룹 통화 픽업 기능을 사용 하면이 통화 관리 측면을 중앙 집중화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11002-115">With Group Call Pickup, therefore, this aspect of call management can be centralized.</span></span>

<span data-ttu-id="11002-116">그룹 통화 픽업 기능은 통화 공원 응용 프로그램을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="11002-116">Group Call Pickup is built on the Call Park application.</span></span> <span data-ttu-id="11002-117">그룹 통화 픽업을 배포 하는 경우 통화 픽업 그룹 번호로 지정 된 별도의 내선 번호 범위를 사용 하 여 통화 공원 궤도 테이블을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="11002-117">When you deploy Group Call Pickup, you configure the call park orbit table with separate ranges of extension numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="11002-118">통화 공원 번호와 같은 통화 픽업 그룹 번호는 사용자 또는 전화가 할당 되지 않은 가상 확장명 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11002-118">Like call park orbit numbers, call pickup group numbers must be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="11002-119">그룹 통화 픽업을 배포 하는 각 프런트 엔드 풀에는 하나 이상의 통화 픽업 그룹 번호 범위가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11002-119">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="11002-120">그룹 번호 범위는 Lync Server 배포에서 전역적으로 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11002-120">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="11002-121">통화 공원 표에서 그룹 통화 픽업 번호로 지정 된 숫자 범위는 Lync Server 제어판을 사용 하 여 관리 하거나 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11002-121">Number ranges that are designated as Group Call Pickup numbers in the call park orbit table cannot be managed or viewed by using the Lync Server Control Panel.</span></span> <span data-ttu-id="11002-122">통화 공원 궤도 테이블에서 모든 숫자 범위를 보는 유일한 방법은 Lync Server Management Shell을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="11002-122">The only way to see all the number ranges in the call park orbit table is to use Lync Server Management Shell.</span></span> <span data-ttu-id="11002-123">마찬가지로 그룹 통화 픽업 번호를 추가, 수정 또는 제거 하는 유일한 방법은 Lync Server Management Shell을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="11002-123">Similarly, the only way to add, modify, or remove Group Call Pickup numbers is to use Lync Server Management Shell.</span></span>



</div>

<span data-ttu-id="11002-124">통화 픽업 그룹 번호를 구성한 후에는 통화 픽업 그룹에 사용자를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="11002-124">After you configure the call pickup group numbers, you assign users to a call pickup group.</span></span> <span data-ttu-id="11002-125">통화 픽업 그룹에 할당 된 모든 사용자는 다른 사용자가 통화를 대답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11002-125">Any user who is assigned to a call pickup group can have their calls answered by other users.</span></span> <span data-ttu-id="11002-126">통화가 통화 픽업 그룹에 할당 된 사용자에 게 제공 되는 경우 전화를 거는 다른 모든 사용자가 전화를 통해 통화 픽업 그룹 번호를 수동으로 착신 전환 하 여 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11002-126">When a call comes in to a user who is assigned to a call pickup group, any other user who notices the call can answer it by manually dialing the call pickup group number.</span></span> <span data-ttu-id="11002-127">통화를 선택 하는 사용자는 그룹의 구성원이 될 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11002-127">The user who picks up the call does not need to be a member of the group.</span></span> <span data-ttu-id="11002-128">다른 사용자가 통화를 선택 하면 원래 호출한 번호로 알림이 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11002-128">When a call is picked up by another user, a notification is sent to the number originally called.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="11002-129">사용자는 한 통화 픽업 그룹의 구성원 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11002-129">A user can be a member of only one call pickup group.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="11002-130">Lync Server 배포의 모든 사용자가 통화 픽업 그룹 구성원에 게 전화를 받을 수 있지만 전화를 받는 사람은 올바른 통화 픽업 그룹 번호를 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11002-130">Although any user in the Lync Server deployment can answer a call to a call pickup group member, the person answering the call must know the correct call pickup group number to dial.</span></span>



</div>

<span data-ttu-id="11002-131">사용자가 그룹에 있는 여러 개의 전화가 연결 될 때 전화를 받기 위해 통화 픽업 그룹 번호로 전화를 걸면 사용자는 가장 오랫동안 연결 된 전화에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="11002-131">If a user dials a call pickup group number to answer a call when multiple phones in the group are ringing, the user answers the call that has been ringing the longest.</span></span>

<span data-ttu-id="11002-132">동시 연결 설정은 그룹 통화 픽업 사용자에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11002-132">Simultaneous ringing settings will work for users who have group call pickup.</span></span> <span data-ttu-id="11002-133">즉, 그룹 통화 픽업이 있는 사용자에 대 한 통화가 구성 된 모든 대상에 대해 연결 되며 다른 사용자가 전화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11002-133">That is, a call made to a user who has Group Call Pickup will ring for all the configured destinations, and another user can answer the call.</span></span> <span data-ttu-id="11002-134">이 규칙의 예외는 사용자가 모든 팀 구성원에 게 전화를 거는 동시 벨 울림을 구성할 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="11002-134">The exception to this rule is when the user configures simultaneous ringing to call all the team members.</span></span>

<span data-ttu-id="11002-135">그룹 통화 픽업을 사용 하 여 다음 통화 유형에 응답할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11002-135">Group Call Pickup cannot be used to answer the following types of calls:</span></span>

  - <span data-ttu-id="11002-136">전용 회선으로 전화 걸기</span><span class="sxs-lookup"><span data-stu-id="11002-136">Calls to a private line</span></span>

  - <span data-ttu-id="11002-137">친구 및 가족 개인 정보 취급 방침에 배정 된 대화 상대에 게 전화 걸기</span><span class="sxs-lookup"><span data-stu-id="11002-137">Calls from a contact who has been assigned the Friends and Family privacy relationship</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="11002-138">통화 픽업 그룹의 구성원 인 사용자는 대화 상대를 Lync 클라이언트에 개인 연락처로 표시 하 여 특정 통화가 그룹 통화 픽업을 통해 검색 되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11002-138">A user who is a member of a call pickup group can prevent certain calls from being retrieved through Group Call Pickup by marking the contact as a personal contact in the Lync client.</span></span> <span data-ttu-id="11002-139">연락처를 개인 연락처로 표시 하려면 연락처에 대 한 개인 정보 취급 방침을 친구나 가족에 게 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="11002-139">To mark a contact as a personal contact, set the Privacy Relationship for the contact to Friends and Family.</span></span> <span data-ttu-id="11002-140">그룹 통화 픽업을 사용 하 여 개인 정보 공개 범위를 친구 및 가족과 연락 하는 모든 수신 통화를 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11002-140">Any incoming call from contacts with the Privacy Relationship set to Friends and Family cannot be retrieved by using Group Call Pickup.</span></span>

    
    </div>

  - <span data-ttu-id="11002-141">오디오/비디오 통화의 비디오 부분</span><span class="sxs-lookup"><span data-stu-id="11002-141">Video portion of audio/video calls</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="11002-142">사용자가 오디오/비디오 통화에 응답 하면 사용자가 오디오만 받습니다.</span><span class="sxs-lookup"><span data-stu-id="11002-142">If a user answers an audio/video call, the user receives only the audio.</span></span> <span data-ttu-id="11002-143">상대방이 전화를 걸거나 전화를 하는 사람이 통화를 escalation 하 여 비디오를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11002-143">Either the person calling or the person answering the call can escalate the call to add video.</span></span>

    
    </div>

  - <span data-ttu-id="11002-144">팀 통화 구성원으로 라우팅되는 동시 벨 통화</span><span class="sxs-lookup"><span data-stu-id="11002-144">Simultaneous ringing calls that are routed to team call members</span></span>

  - <span data-ttu-id="11002-145">대리인에 게 라우팅된 통화</span><span class="sxs-lookup"><span data-stu-id="11002-145">Calls routed to a delegate</span></span>

  - <span data-ttu-id="11002-146">응답 그룹에 게 전달 되는 통화</span><span class="sxs-lookup"><span data-stu-id="11002-146">Calls routed to a response group</span></span>

<span data-ttu-id="11002-147">다음 유형의 사용자는 그룹 통화 픽업에 참여할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11002-147">The following types of users cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="11002-148">즉, 그룹 통화 픽업 그룹에 포함 하지 않아야 하며, 그룹 통화 픽업를 사용 하는 사용자에 게는 통화를 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="11002-148">That is, they should not be included in a Group Call Pickup group, and they cannot pick up calls for users who have Group Call Pickup enabled.</span></span>

  - <span data-ttu-id="11002-149">하이브리드 배포에서 온라인으로 홈 인 사용자</span><span class="sxs-lookup"><span data-stu-id="11002-149">Users who are homed online in a hybrid deployment</span></span>

  - <span data-ttu-id="11002-150">Lync server 2013 풀에서 외부에 있지 않은 사용자-온-프레미스 배포의 누적 2013 업데이트: 2 월 2013 일</span><span class="sxs-lookup"><span data-stu-id="11002-150">Users who are not homed on a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013 in an on-premises deployment</span></span>

<span data-ttu-id="11002-151">통화 픽업 그룹의 구성원에 게 전화를 걸 수 없는 경우 클라이언트 설정에 지정 된 대로 통화가 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11002-151">If no one answers a call to a member of a call pickup group, the call is routed as specified in the client settings.</span></span> <span data-ttu-id="11002-152">즉, 클라이언트 설정에 지정 된 대로 통화는 보이스 메일로 이동 하거나 다른 목적지로 착신 전환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11002-152">That is, the call goes to voicemail or is forwarded to a different destination, as specified in the client settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

