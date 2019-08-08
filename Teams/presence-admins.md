---
title: 팀의 사용자 현재 상태
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: 정보 관리자는 팀의 현재 상태에 대해 이해 해야 합니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8b3c36f0f83937e72ae4477ad38c9bd3187c6577
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244830"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="15851-103">팀의 사용자 현재 상태</span><span class="sxs-lookup"><span data-stu-id="15851-103">User presence in Teams</span></span>

<span data-ttu-id="15851-104">현재 상태는 Microsoft 팀 (및 Office 365)에서 사용자 프로필의 일부 이며 조직의 다른 사용자에 대 한 사용자의 현재 사용 가능한 시간 및 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="15851-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) – and indicates the user’s current availability and status to other users in the organization.</span></span> <span data-ttu-id="15851-105">기본적으로 팀을 사용 하는 조직의 모든 사용자는 다른 사용자가 온라인으로 사용할 수 있는지 여부에 상관 없이 거의 실시간으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15851-105">By default, anyone in your organization using Teams can see – in nearly real time – whether or not other users are available online.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="15851-106">팀의 현재 상태</span><span class="sxs-lookup"><span data-stu-id="15851-106">Presence states in Teams</span></span>

<span data-ttu-id="15851-107">팀에서 사용할 수 있는 사용자 현재 상태는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="15851-107">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="15851-108">사용자 구성 됨</span><span class="sxs-lookup"><span data-stu-id="15851-108">User configured</span></span>|<span data-ttu-id="15851-109">앱 구성 됨</span><span class="sxs-lookup"><span data-stu-id="15851-109">App configured</span></span>|
|:--- |:---|
| ![현재 상태를 나타내는 진한 녹색 chek 표시](media/Presence_Available.png) <span data-ttu-id="15851-111">공간이</span><span class="sxs-lookup"><span data-stu-id="15851-111">Available</span></span>|![현재 상태를 나타내는 진한 녹색 chek 표시](media/Presence_Available.png) <span data-ttu-id="15851-113">공간이</span><span class="sxs-lookup"><span data-stu-id="15851-113">Available</span></span>|
|| ![녹색 chek 표시, 사용 가능한 oof 표시](media/Presence_Available_OOF.png) <span data-ttu-id="15851-115">사용 가능, 부재 중</span><span class="sxs-lookup"><span data-stu-id="15851-115">Available, Out of Office</span></span> |
|  ![약속 있음을 표시 하는 빨간색 실선 원](media/Presence_Busy.png) <span data-ttu-id="15851-117">작업</span><span class="sxs-lookup"><span data-stu-id="15851-117">Busy</span></span> |  ![약속 있음을 표시 하는 빨간색 실선 원](media/Presence_Busy.png) <span data-ttu-id="15851-119">작업</span><span class="sxs-lookup"><span data-stu-id="15851-119">Busy</span></span>  |
|| ![통화 중임을 나타내는 빨간색 원 실선](media/Presence_Busy.png) <span data-ttu-id="15851-121">통화 중</span><span class="sxs-lookup"><span data-stu-id="15851-121">In a call</span></span>|
|| ![모임의 약속 있음을 나타내는 빨간색 원 실선](media/Presence_Busy.png) <span data-ttu-id="15851-123">모임에서</span><span class="sxs-lookup"><span data-stu-id="15851-123">In a meeting</span></span> |
|| ![부재 중 통화를 나타내는 빨간색 원 열기](media/Presence_Busy_OOF.png) <span data-ttu-id="15851-125">통화 중, 부재 중</span><span class="sxs-lookup"><span data-stu-id="15851-125">In a call, out of office</span></span>|
|  ![흰색 선이 있는 빨간색 원 (방해 금지 표시)](media/Presence_DND.png) <span data-ttu-id="15851-127">방해 금지</span><span class="sxs-lookup"><span data-stu-id="15851-127">Do not disturb</span></span> ||
|| ![흰색 선이 있는 빨간색 원 (프레젠테이션 표시)](media/Presence_DND.png) <span data-ttu-id="15851-129">프레젠테이션할</span><span class="sxs-lookup"><span data-stu-id="15851-129">Presenting</span></span>|
| ![자리를 표시 하지 않는 노란색 시계 아이콘](media/Presence_Away.png) <span data-ttu-id="15851-131">방향</span><span class="sxs-lookup"><span data-stu-id="15851-131">Away</span></span>| ![자리를 표시 하지 않는 노란색 시계 아이콘](media/Presence_Away.png) <span data-ttu-id="15851-133">방향</span><span class="sxs-lookup"><span data-stu-id="15851-133">Away</span></span>|
|| <span data-ttu-id="15851-134">![마지막으로 표시 되는](media/Presence_Away.png) *동안* 자리를 비운 노란색 시계 아이콘</span><span class="sxs-lookup"><span data-stu-id="15851-134">![Yellow clock icon, indicating away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![자리 비움을 나타내는 노란색 시계 아이콘을 오른쪽으로 뒤로](media/Presence_Away.png) <span data-ttu-id="15851-136">곧 돌아오겠음</span><span class="sxs-lookup"><span data-stu-id="15851-136">Be right back</span></span>| |
|| ![자리 비움으로 표시 되는 노란색 시계 아이콘](media/Presence_Away.png)  <span data-ttu-id="15851-138">작업 해제</span><span class="sxs-lookup"><span data-stu-id="15851-138">Off Work</span></span>|
|| ![X가 있는 회색 원, 오프 라인 상태임](media/Presence_Offline.png) <span data-ttu-id="15851-140">이거나</span><span class="sxs-lookup"><span data-stu-id="15851-140">Offline</span></span> |
|| ![알 수 없는 상태를 나타내는 회색 원 열기](media/Presence_Unknown.png) <span data-ttu-id="15851-142">알 수 없는 상태</span><span class="sxs-lookup"><span data-stu-id="15851-142">Status unknown</span></span>|
||![대각선이 있는 빨간 원 (차단 됨 표시)을 엽니다.](media/Presence_Blocked.png) <span data-ttu-id="15851-144">약속이</span><span class="sxs-lookup"><span data-stu-id="15851-144">Blocked</span></span> |
|| ![화살표를 사용 하 여 부재 중 표시 되는 자주색 원](media/Presence_OOF.png) <span data-ttu-id="15851-146">부재 중</span><span class="sxs-lookup"><span data-stu-id="15851-146">Out of Office</span></span>|
|||
 
<span data-ttu-id="15851-147">사용자는 일부 옵션에 대 한 현재 현재 상태 상태를 수동으로 설정할 수 있으며 해당 상태는 다른 모든 사용자에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15851-147">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="15851-148">또한 추가 사용자 현재 상태 세부 정보는 사용자 활동 (예: 사용 가능 또는 자리 비움), Outlook 일정 상태 (예: 모임) 또는 팀 앱 상태 (통화 중 표시), 목록에서 들여쓴 상태에 따라 자동으로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15851-148">Additional user presence details are also automatically updated based on user activity (such as Available or Away), Outlook calendar states (such as In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span>

<span data-ttu-id="15851-149">사용자의 현재 현재 상태 상태가 자리 비움으로 다시 설정 될 때까지 15 분 동안 비활동 시간이 초과 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15851-149">There is a 15 minute inactivity timeout, after which your users' current presence state will be reset to Away.</span></span>

<span data-ttu-id="15851-150">사용자는 끊을 수 있는 사용자를 지정할 수 있습니다 (방해 금지 설정을 재정의 하도록 연락).</span><span class="sxs-lookup"><span data-stu-id="15851-150">Users can specify who can break through (contact them overriding a Do Not Disturb setting).</span></span> <span data-ttu-id="15851-151">이러한 설정은 앱에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15851-151">These settings are available in-app.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="15851-152">비즈니스용 Skype와 팀의 관리 설정</span><span class="sxs-lookup"><span data-stu-id="15851-152">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="15851-153">다음 관리 설정 비즈니스용 Skype는 팀에서 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="15851-153">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="15851-154">팀에서 조직의 사용자는 항상 현재 상태 공유를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15851-154">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="15851-155">팀에서는 개인 정보 (현재 상태를 볼 수 있는 사람 결정) 구성을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="15851-155">Privacy (deciding who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="15851-156">팀의 사용자는 모든 사용자 (페더레이션된 서비스 포함)와의 현재 상태 공유를 항상 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15851-156">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="15851-157">대화 상대 목록 (비즈니스용 Skype에서 하나가 있는 경우)은 **채팅 > 연락처** 또는 **통화 > 연락처**아래에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15851-157">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="15851-158">클라이언트가 방해 금지이 고 팀의 사용자에 게 탁월한 기능을 항상 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15851-158">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="15851-159">Outlook과 통합 된 팀의 사용자는 일정 (부재 중 및 다른 일정 정보 포함) 통합이 항상 활성화 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15851-159">Calendar (includes out of office and other calendar information) integration  is always enabled for users in Teams if integrated with Outlook.</span></span>
- <span data-ttu-id="15851-160">팀의 사용자에 게는 *마지막으로 표시* 된 또는 *자리 비움* (비즈니스용 Skype를 사용 하는 이중 환경) 표시기가 항상 활성화 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15851-160">The *Last seen* or *Away since* (if in a dual environment with Skype for Business) indicator is always enabled for users in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="15851-161">이러한 설정을 사용자 지정 하는 팀 관리자의 기능은 현재 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="15851-161">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="15851-162">비즈니스용 Skype와 공존</span><span class="sxs-lookup"><span data-stu-id="15851-162">Coexistence with Skype for Business</span></span>

<span data-ttu-id="15851-163">비즈니스용 Skype로 공존할 때의 팀 현재 상태 기능에 대 한 자세한 내용은 비즈니스용 [skype를 사용 하 여 함께 공존](coexistence-chat-calls-presence.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="15851-163">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when coexisting with Skype for Business.</span></span> 
