---
title: Teams에서 사용자 현재 상태 확인
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 08/21/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: 팀의 현재 상태에 대 한 관리자 정보.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b829fbffa728d3449ba19466d0a2cb85f266c9c2
ms.sourcegitcommit: b9710149ad0bb321929139118b7df0bc4cca08de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/06/2019
ms.locfileid: "38010601"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="794e2-103">Teams에서 사용자 현재 상태 확인</span><span class="sxs-lookup"><span data-stu-id="794e2-103">User presence in Teams</span></span>

<span data-ttu-id="794e2-104">현재 상태는 Microsoft 팀 (및 Office 365)의 사용자 프로필의 일부로, 다른 사용자에 대 한 현재의 가용성과 상태를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="794e2-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) that indicates the user’s current availability and status to other users.</span></span> <span data-ttu-id="794e2-105">다른 사용자가 온라인 상태를 사용할 수 있는 경우 기본적으로 팀을 사용 하는 조직의 모든 사용자가 거의 실시간으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="794e2-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="794e2-106">사용자를 **팀 전용** 모드로 이동한 후 비즈니스용 Skype 클라이언트를 제거 하는 경우 Outlook 및 다른 Office 앱에서 현재 상태는 작동 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="794e2-106">If you uninstall the Skype for Business client after you move a user to **Teams Only** mode, presence stops working in Outlook and other Office apps.</span></span> <span data-ttu-id="794e2-107">팀에서 상태는 제대로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="794e2-107">Presence works fine in Teams.</span></span> <span data-ttu-id="794e2-108">해결 방법: Outlook (및 다른 Office 앱)에서 현재 상태를 확인 하려면 팀 **전용** 모드로 팀을 실행 하는 경우에도 비즈니스용 Skype를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="794e2-108">Workaround: To see presence in Outlook (and other Office apps), Skype for Business must be installed, even if you're running Teams in **Teams Only** mode.</span></span> <span data-ttu-id="794e2-109">Microsoft는이 문제를 알고 있으며 수정 작업을 진행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="794e2-109">Microsoft is aware of this problem and is working on a fix.</span></span>

<span data-ttu-id="794e2-110">Outlook에서 팀 현재 상태는 Outlook 2013 데스크톱 앱 이상에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="794e2-110">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="794e2-111">팀의 현재 상태</span><span class="sxs-lookup"><span data-stu-id="794e2-111">Presence states in Teams</span></span>

<span data-ttu-id="794e2-112">팀에서 사용할 수 있는 사용자 현재 상태는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="794e2-112">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="794e2-113">사용자 구성 됨</span><span class="sxs-lookup"><span data-stu-id="794e2-113">User configured</span></span>|<span data-ttu-id="794e2-114">앱 구성 됨</span><span class="sxs-lookup"><span data-stu-id="794e2-114">App configured</span></span>|
|:--- |:---|
| ![현재 상태를 나타내는 녹색 확인 표시가 있습니다.](media/Presence_Available.png) <span data-ttu-id="794e2-116">공간이</span><span class="sxs-lookup"><span data-stu-id="794e2-116">Available</span></span>|![현재 상태를 나타내는 녹색 확인 표시가 있습니다.](media/Presence_Available.png) <span data-ttu-id="794e2-118">공간이</span><span class="sxs-lookup"><span data-stu-id="794e2-118">Available</span></span>|
|| ![녹색 확인 표시를 열고 사용 가능한 oof를 나타냅니다.](media/Presence_Available_OOF.png) <span data-ttu-id="794e2-120">사용 가능, 부재 중</span><span class="sxs-lookup"><span data-stu-id="794e2-120">Available, Out of Office</span></span> |
|  ![빨간색 실선 원으로, 약속이 있음을 나타냅니다.](media/Presence_Busy.png) <span data-ttu-id="794e2-122">작업</span><span class="sxs-lookup"><span data-stu-id="794e2-122">Busy</span></span> |  ![빨간색 실선 원으로, 약속이 있음을 나타냅니다.](media/Presence_Busy.png) <span data-ttu-id="794e2-124">작업</span><span class="sxs-lookup"><span data-stu-id="794e2-124">Busy</span></span>  |
|| ![빨간색 원으로 표시 되며 통화 중입니다.](media/Presence_Busy.png) <span data-ttu-id="794e2-126">통화 중</span><span class="sxs-lookup"><span data-stu-id="794e2-126">In a call</span></span>|
|| ![빨간색 실선 원으로, 모임에서 약속이 있음을 나타냅니다.](media/Presence_Busy.png) <span data-ttu-id="794e2-128">모임에서</span><span class="sxs-lookup"><span data-stu-id="794e2-128">In a meeting</span></span> |
|| ![빨간색 원 열림, 약속이 있음을 나타냅니다.](media/Presence_Busy_OOF.png) <span data-ttu-id="794e2-130">통화 중, 부재 중</span><span class="sxs-lookup"><span data-stu-id="794e2-130">In a call, out of office</span></span>|
|  ![흰색 선이 있는 빨간색 원, 방해 금지 표시](media/Presence_DND.png) <span data-ttu-id="794e2-132">방해 금지</span><span class="sxs-lookup"><span data-stu-id="794e2-132">Do not disturb</span></span> ||
|| ![흰색 선이 있는 빨간색 원으로 프레젠테이션 표시](media/Presence_DND.png) <span data-ttu-id="794e2-134">프레젠테이션할</span><span class="sxs-lookup"><span data-stu-id="794e2-134">Presenting</span></span>|
|| ![흰색 선이 있는 빨간색 원이 포커스를 나타냄](media/Presence_DND.png) <span data-ttu-id="794e2-136">집중할</span><span class="sxs-lookup"><span data-stu-id="794e2-136">Focusing</span></span>|
| ![노란색 시계 아이콘, 자리 비움 상태임을 나타냄](media/Presence_Away.png) <span data-ttu-id="794e2-138">방향</span><span class="sxs-lookup"><span data-stu-id="794e2-138">Away</span></span>| ![노란색 시계 아이콘, 자리 비움 상태임을 나타냄](media/Presence_Away.png) <span data-ttu-id="794e2-140">방향</span><span class="sxs-lookup"><span data-stu-id="794e2-140">Away</span></span>|
|| <span data-ttu-id="794e2-141">![노란색 시계 아이콘, 마지막으로](media/Presence_Away.png) 표시 되는 자리 비움 *시간* 표시</span><span class="sxs-lookup"><span data-stu-id="794e2-141">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![노란색 시계 아이콘, 자리 비움 표시, 오른쪽으로](media/Presence_Away.png) <span data-ttu-id="794e2-143">곧 돌아오겠음</span><span class="sxs-lookup"><span data-stu-id="794e2-143">Be right back</span></span>| |
|| ![자리 비움, 작업 시간을 나타내는 노란색 시계 아이콘](media/Presence_Away.png)  <span data-ttu-id="794e2-145">작업 해제</span><span class="sxs-lookup"><span data-stu-id="794e2-145">Off Work</span></span>|
|| ![X가 있는 회색 원, 오프 라인 상태임을 나타냄](media/Presence_Offline.png) <span data-ttu-id="794e2-147">이거나</span><span class="sxs-lookup"><span data-stu-id="794e2-147">Offline</span></span> |
|| ![회색 원 열림, 알 수 없는 상태 표시](media/Presence_Unknown.png) <span data-ttu-id="794e2-149">알 수 없는 상태</span><span class="sxs-lookup"><span data-stu-id="794e2-149">Status unknown</span></span>|
||![대각선이 있는 빨간색 원 열림, 차단 됨을 나타냄](media/Presence_Blocked.png) <span data-ttu-id="794e2-151">약속이</span><span class="sxs-lookup"><span data-stu-id="794e2-151">Blocked</span></span> |
|| ![화살표가 있는 자주색 원, 부재 중임을 나타냄](media/Presence_OOF.png) <span data-ttu-id="794e2-153">부재 중</span><span class="sxs-lookup"><span data-stu-id="794e2-153">Out of Office</span></span>|
|||
 
<span data-ttu-id="794e2-154">사용자는 일부 옵션에 대 한 현재 현재 상태 상태를 수동으로 설정할 수 있으며 해당 상태는 다른 모든 사용자에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="794e2-154">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="794e2-155">또한 추가 사용자 현재 상태 정보도 자동으로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="794e2-155">More user presence details are also automatically updated.</span></span> <span data-ttu-id="794e2-156">변경 사항은 사용자 활동 (사용 가능, 자리 비움), Outlook 일정 상태 (모임 중) 또는 팀 앱 상태 (통화 중 발표 됨)에 따라 목록에서 들여쓰기 되는 상태에 기반 합니다.</span><span class="sxs-lookup"><span data-stu-id="794e2-156">The changes are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span> 

<span data-ttu-id="794e2-157">현재 현재 상태가 자리 비움으로 다시 설정 되는 데 15 분 비활성 시간 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="794e2-157">There's a 15-minute inactivity timeout, after which a current presence state is reset to Away.</span></span>

<span data-ttu-id="794e2-158">사용자는 끊을 수 있는 사용자를 지정할 수 있습니다 (방해 금지 상태에도 연락 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="794e2-158">Users can specify who can break through (meaning contact them despite a Do Not Disturb state).</span></span> <span data-ttu-id="794e2-159">이러한 설정은 팀 클라이언트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="794e2-159">These settings are available in the Teams client.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="794e2-160">비즈니스용 Skype와 팀의 관리 설정</span><span class="sxs-lookup"><span data-stu-id="794e2-160">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="794e2-161">다음 관리 설정 비즈니스용 Skype는 팀에서 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="794e2-161">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="794e2-162">팀에서 조직의 사용자는 항상 현재 상태 공유를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="794e2-162">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="794e2-163">개인 정보 (현재 상태를 볼 수 있는 사용자를 정의 하는 위치) 구성은 팀에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="794e2-163">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="794e2-164">팀의 사용자는 모든 사용자 (페더레이션된 서비스 포함)와의 현재 상태 공유를 항상 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="794e2-164">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="794e2-165">대화 상대 목록 (비즈니스용 Skype에서 하나가 있는 경우)은 **채팅 > 연락처** 또는 **통화 > 연락처**아래에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="794e2-165">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="794e2-166">클라이언트가 방해 금지이 고 팀의 사용자에 게 탁월한 기능을 항상 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="794e2-166">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="794e2-167">일정 (부재 중 및 다른 일정 정보 포함) 통합은 팀이 Outlook과 통합 될 때 항상 사용자가 사용할 수 있도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="794e2-167">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="794e2-168">조직에서 비즈니스용 Skype를 사용 하는 경우 팀의 사용자는 표시기를 볼 수 있는 *마지막* 또는 *반대* 입니다.</span><span class="sxs-lookup"><span data-stu-id="794e2-168">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="794e2-169">이러한 설정을 사용자 지정 하는 팀 관리자의 기능은 현재 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="794e2-169">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="794e2-170">비즈니스용 Skype와 공존</span><span class="sxs-lookup"><span data-stu-id="794e2-170">Coexistence with Skype for Business</span></span>

<span data-ttu-id="794e2-171">조직에서 비즈니스용 Skype를 사용 하는 경우 팀의 현재 상태 기능에 대 한 자세한 내용은 [비즈니스용 skype를 사용 하 여 함께 공존](coexistence-chat-calls-presence.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="794e2-171">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
