---
title: 'Lync Server 2013: 그룹 통화 픽업 개요'
description: 'Lync Server 2013: 그룹 통화 픽업 개요입니다.'
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
ms.openlocfilehash: c968ac466c7242253cb5a9594e1942d86031494d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562884"
---
# <a name="overview-of-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="642c7-103">Lync Server 2013의 그룹 통화 픽업 개요</span><span class="sxs-lookup"><span data-stu-id="642c7-103">Overview of Group Call Pickup in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="642c7-104">_**마지막으로 수정 된 항목:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="642c7-104">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="642c7-105">Lync Server 2013 년 2 2013 월에 대 한 누적 업데이트의 새로운 기능인 그룹 호출 Pickup에서는 사용자가 자신의 휴대폰에서 자신의 동료에 게 들어오는 호출에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-105">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="642c7-106">이 새로운 기능을 사용 하면 다른 사용자가 통화 픽업 그룹 번호로 전화를 걸어 들어오는 호출에 응답할 수 있도록 하 여 사용자의 회선을 더 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-106">This new feature increases the availability of a user's line by enabling other users to answer an incoming call by dialing a call pickup group number.</span></span> <span data-ttu-id="642c7-107">그룹 통화 픽업이 배포 되 면 음성 메일에 라우팅되는 수신 전화의 수가 상당히 줄어들 수 있으며,이는 특히 조직 외부에 있는 고객의 통화에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-107">When Group Call Pickup is deployed, the number of incoming calls that are routed to voice mail can be significantly reduced, which is particularly useful for calls from customers who are external to your organization.</span></span>

<span data-ttu-id="642c7-108">그룹 통화 픽업 기능은 열린 office 환경의 비즈니스 단위에 대해 특별히 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-108">The Group Call Pickup feature is designed in particular for business units in open office environments.</span></span> <span data-ttu-id="642c7-109">수신 전화는 의도 한 대상에만 울릴 수 있으므로 방해가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-109">Incoming calls are not disruptive because they ring only at the intended destination.</span></span> <span data-ttu-id="642c7-110">그러나 반지를 들리는 다른 사용자는 그룹 번호에 전화를 걸어 통화를 계속 해 서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-110">Other users who hear the ring, however, can still pick up the call simply by dialing the group number.</span></span>

<span data-ttu-id="642c7-111">사용자가 열린 사무실 레이아웃에 없거나 일반적인 책임을 공유 하는 사용자가 지리적으로 분산 된 환경에서는 팀 호출이 가장 적합 한 솔루션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-111">In environments where users are not located in an open office layout, or where users who share a common responsibility are geographically distributed, team call presents the most suitable solution.</span></span> <span data-ttu-id="642c7-112">그룹 통화 픽업 및 팀 호출의 주요 차이점은 그룹 호출 Pickup을 사용 하 여 수신 전화가 의도 한 대상 에서만 울릴 것 이지만 누구나 그룹 번호에 전화를 걸어 응답 하도록 선택할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-112">The primary difference between Group Call Pickup and team call is that, with Group Call Pickup, an incoming call rings only at the intended destination, but anyone can still choose to answer it by dialing a group number.</span></span> <span data-ttu-id="642c7-113">팀 호출을 통해 통화는 모든 팀원의 전화를 걸고 팀의 모든 사용자가 전화를 걸어 통화에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-113">With team call, the call rings at all the team members' phones, and any user in the team can pick up the phone to answer the call.</span></span> <span data-ttu-id="642c7-114">그룹 통화 픽업 및 팀 통화 간의 추가 차이점은 관리자가 Lync Server를 통해 그룹 통화 픽업을 관리 한다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-114">An additional difference between Group Call Pickup and team call is that Group Call Pickup is managed by an administrator, through Lync Server.</span></span> <span data-ttu-id="642c7-115">팀 호출을 사용 하는 경우 최종 사용자는 Lync 클라이언트를 사용 하 여 기능을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-115">With team call, end users manage the feature by using the Lync client.</span></span> <span data-ttu-id="642c7-116">따라서 그룹 통화 픽업 기능을 사용 하 여 이러한 통화 관리 측면을 중앙 집중식으로 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-116">With Group Call Pickup, therefore, this aspect of call management can be centralized.</span></span>

<span data-ttu-id="642c7-117">그룹 통화 픽업 기능은 통화 대기 응용 프로그램을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-117">Group Call Pickup is built on the Call Park application.</span></span> <span data-ttu-id="642c7-118">그룹 통화 픽업를 배포할 때는 통화 픽업 그룹 번호로 지정 된 별도의 내선 번호 범위를 사용 하 여 통화 대기 궤도 테이블을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-118">When you deploy Group Call Pickup, you configure the call park orbit table with separate ranges of extension numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="642c7-119">통화 대기 궤도 번호와 마찬가지로 call pickup 그룹 번호는 사용자 또는 전화가 할당 되지 않은 가상 확장명 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-119">Like call park orbit numbers, call pickup group numbers must be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="642c7-120">그룹 통화 픽업를 배포 하는 각 프런트 엔드 풀에는 하나 이상의 통화 픽업 그룹 번호 범위가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-120">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="642c7-121">그룹 번호 범위는 Lync Server 배포에서 전역적으로 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-121">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="642c7-122">그룹으로 지정 된 숫자 범위 통화 대기 번호 표의 통화 픽업 번호는 Lync Server 제어판을 사용 하 여 관리 하거나 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-122">Number ranges that are designated as Group Call Pickup numbers in the call park orbit table cannot be managed or viewed by using the Lync Server Control Panel.</span></span> <span data-ttu-id="642c7-123">통화 대기 번호 표에서 모든 숫자 범위를 확인 하는 유일한 방법은 Lync Server 관리 셸을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-123">The only way to see all the number ranges in the call park orbit table is to use Lync Server Management Shell.</span></span> <span data-ttu-id="642c7-124">마찬가지로 그룹 통화 픽업 번호를 추가, 수정 또는 제거 하는 유일한 방법은 Lync Server 관리 셸을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-124">Similarly, the only way to add, modify, or remove Group Call Pickup numbers is to use Lync Server Management Shell.</span></span>



</div>

<span data-ttu-id="642c7-125">통화 픽업 그룹 번호를 구성한 후에는 통화 픽업 그룹에 사용자를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-125">After you configure the call pickup group numbers, you assign users to a call pickup group.</span></span> <span data-ttu-id="642c7-126">통화 픽업 그룹에 할당 된 모든 사용자는 다른 사용자가 전화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-126">Any user who is assigned to a call pickup group can have their calls answered by other users.</span></span> <span data-ttu-id="642c7-127">통화가 통화 픽업 그룹에 할당 된 사용자에 게 들어오는 경우 전화를 받는 다른 사용자는 통화 픽업 그룹 번호를 수동으로 전화를 걸어 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-127">When a call comes in to a user who is assigned to a call pickup group, any other user who notices the call can answer it by manually dialing the call pickup group number.</span></span> <span data-ttu-id="642c7-128">통화를 선택 하는 사용자는 그룹의 구성원이 될 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-128">The user who picks up the call does not need to be a member of the group.</span></span> <span data-ttu-id="642c7-129">다른 사용자가 통화를 선택 하면 처음에 호출한 번호로 알림이 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-129">When a call is picked up by another user, a notification is sent to the number originally called.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="642c7-130">사용자는 하나의 통화 픽업 그룹 구성원 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-130">A user can be a member of only one call pickup group.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="642c7-131">Lync Server 배포의 모든 사용자가 통화 픽업 그룹 구성원에 게 전화를 걸 수 있지만 통화에 응답 하는 사람은 전화를 걸 올바른 통화 픽업 그룹 번호를 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-131">Although any user in the Lync Server deployment can answer a call to a call pickup group member, the person answering the call must know the correct call pickup group number to dial.</span></span>



</div>

<span data-ttu-id="642c7-132">사용자가 그룹의 여러 전화가 연결 될 때 통화에 응답 하기 위해 통화 픽업 그룹 번호에 전화를 걸면 사용자는 가장 오랫동안 연결 된 통화에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-132">If a user dials a call pickup group number to answer a call when multiple phones in the group are ringing, the user answers the call that has been ringing the longest.</span></span>

<span data-ttu-id="642c7-133">동시 벨 울림 설정은 그룹 통화 픽업 사용자에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-133">Simultaneous ringing settings will work for users who have group call pickup.</span></span> <span data-ttu-id="642c7-134">즉, 그룹 통화 픽업이 있는 사용자에 대 한 통화가 구성 된 모든 대상에 대해 울릴 것 이며 다른 사용자가 통화에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-134">That is, a call made to a user who has Group Call Pickup will ring for all the configured destinations, and another user can answer the call.</span></span> <span data-ttu-id="642c7-135">이 규칙에 대 한 예외는 사용자가 모든 팀 구성원에 게 전화를 거는 동시 벨 울림을 구성 하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-135">The exception to this rule is when the user configures simultaneous ringing to call all the team members.</span></span>

<span data-ttu-id="642c7-136">그룹 통화 Pickup는 다음 유형의 통화에 응답 하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-136">Group Call Pickup cannot be used to answer the following types of calls:</span></span>

  - <span data-ttu-id="642c7-137">전용 회선 호출</span><span class="sxs-lookup"><span data-stu-id="642c7-137">Calls to a private line</span></span>

  - <span data-ttu-id="642c7-138">친구 및 가족 정보 공개 관계가 할당 된 대화 상대와 통화</span><span class="sxs-lookup"><span data-stu-id="642c7-138">Calls from a contact who has been assigned the Friends and Family privacy relationship</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="642c7-139">통화 픽업 그룹의 구성원 인 사용자는 Lync 클라이언트에서 해당 연락처를 개인 연락처로 표시 하 여 특정 통화가 그룹 호출 픽업을 통해 검색 되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-139">A user who is a member of a call pickup group can prevent certain calls from being retrieved through Group Call Pickup by marking the contact as a personal contact in the Lync client.</span></span> <span data-ttu-id="642c7-140">연락처를 개인 연락처로 표시 하려면 해당 연락처에 대 한 개인 정보 취급 방침을 친구나 가족으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-140">To mark a contact as a personal contact, set the Privacy Relationship for the contact to Friends and Family.</span></span> <span data-ttu-id="642c7-141">개인 정보 관계가 친구 및 가족과 연결 된 대화 상대와의 수신 통화는 그룹 통화 픽업을 사용 하 여 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-141">Any incoming call from contacts with the Privacy Relationship set to Friends and Family cannot be retrieved by using Group Call Pickup.</span></span>

    
    </div>

  - <span data-ttu-id="642c7-142">오디오/비디오 통화의 비디오 부분</span><span class="sxs-lookup"><span data-stu-id="642c7-142">Video portion of audio/video calls</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="642c7-143">사용자가 오디오/비디오 통화에 응답할 경우 사용자는 오디오만 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-143">If a user answers an audio/video call, the user receives only the audio.</span></span> <span data-ttu-id="642c7-144">전화를 거는 사람이 나 통화에 응답 하는 사용자가 통화를 에스컬레이션 하 여 비디오를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-144">Either the person calling or the person answering the call can escalate the call to add video.</span></span>

    
    </div>

  - <span data-ttu-id="642c7-145">팀 통화 구성원에 게 라우팅되는 동시 신호 울림</span><span class="sxs-lookup"><span data-stu-id="642c7-145">Simultaneous ringing calls that are routed to team call members</span></span>

  - <span data-ttu-id="642c7-146">대리인에 게 라우팅된 통화</span><span class="sxs-lookup"><span data-stu-id="642c7-146">Calls routed to a delegate</span></span>

  - <span data-ttu-id="642c7-147">응답 그룹으로 라우팅되는 통화</span><span class="sxs-lookup"><span data-stu-id="642c7-147">Calls routed to a response group</span></span>

<span data-ttu-id="642c7-148">다음 유형의 사용자는 그룹 통화 픽업에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-148">The following types of users cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="642c7-149">즉, 그룹 통화 픽업 그룹에 포함 되지 않아야 하며, 그룹 통화 Pickup가 사용 하도록 설정 된 사용자에 대 한 통화를 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-149">That is, they should not be included in a Group Call Pickup group, and they cannot pick up calls for users who have Group Call Pickup enabled.</span></span>

  - <span data-ttu-id="642c7-150">하이브리드 배포에서 온라인으로 홈에 있는 사용자</span><span class="sxs-lookup"><span data-stu-id="642c7-150">Users who are homed online in a hybrid deployment</span></span>

  - <span data-ttu-id="642c7-151">온-프레미스 배포에서 lync server 2013에 대 한 누적 업데이트와 함께 사용 되지 않는 (Lync Server 2013 년 2 2013 월) 사용자</span><span class="sxs-lookup"><span data-stu-id="642c7-151">Users who are not homed on a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013 in an on-premises deployment</span></span>

<span data-ttu-id="642c7-152">통화 픽업 그룹의 구성원에 대 한 호출에 응답 하지 않으면 클라이언트 설정에 지정 된 대로 통화가 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-152">If no one answers a call to a member of a call pickup group, the call is routed as specified in the client settings.</span></span> <span data-ttu-id="642c7-153">즉, 통화가 음성 메일로 이동 하거나 클라이언트 설정에 지정 된 다른 목적지로 착신 전환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="642c7-153">That is, the call goes to voicemail or is forwarded to a different destination, as specified in the client settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

