---
title: Teams에서의 사용자 현재 상태
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: 팀의 현재 상태 및 현재 상태 기능에 대 한 관리 설정에 대해 알아봅니다.
ms.custom: seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: c31439485f245b522a55c2e5e1134ca6cdddbdf7
ms.sourcegitcommit: b14ad0a6c454b20f34fccbd1d312de24379faef0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2020
ms.locfileid: "46572353"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="2e261-103">Teams에서의 사용자 현재 상태</span><span class="sxs-lookup"><span data-stu-id="2e261-103">User presence in Teams</span></span>

<span data-ttu-id="2e261-104">현재 상태는 Microsoft 팀 (및 Microsoft 365 또는 Office 365)의 일부 이며, 다른 사용자에 대 한 현재의 가용성과 상태를 나타내는 사용자 프로필의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="2e261-104">Presence is part of a user's profile in Microsoft Teams (and throughout Microsoft 365 or Office 365) that indicates the user's current availability and status to other users.</span></span> <span data-ttu-id="2e261-105">기본적으로 Teams를 사용하는 조직의 모든 사용자는 온라인으로 다른 사용자의 대화 가능 여부를 거의 실시간으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e261-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

<span data-ttu-id="2e261-106">Outlook에 있는 팀의 현재 상태는 Outlook 2013 데스크톱 앱 이상에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e261-106">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="2e261-107">Teams에서의 현재 상태</span><span class="sxs-lookup"><span data-stu-id="2e261-107">Presence states in Teams</span></span>

|<span data-ttu-id="2e261-108">사용자가 구성함</span><span class="sxs-lookup"><span data-stu-id="2e261-108">User configured</span></span>|<span data-ttu-id="2e261-109">앱이 구성함</span><span class="sxs-lookup"><span data-stu-id="2e261-109">App configured</span></span>|
|:--- |:---|
| ![채워진 녹색 확인 표시, 현재 상태 대화 가능 표시](media/Presence_Available.png) <span data-ttu-id="2e261-111">대화 가능</span><span class="sxs-lookup"><span data-stu-id="2e261-111">Available</span></span>|![채워진 녹색 확인 표시, 현재 상태 대화 가능 표시](media/Presence_Available.png) <span data-ttu-id="2e261-113">대화 가능</span><span class="sxs-lookup"><span data-stu-id="2e261-113">Available</span></span>|
|| ![빈 녹색 확인 표시, 대화 가능, 부재 중 표시](media/Presence_Available_OOF.png) <span data-ttu-id="2e261-115">대화 가능, 부재 중</span><span class="sxs-lookup"><span data-stu-id="2e261-115">Available, Out of Office</span></span> |
|  ![채워진 빨간색 원, 다른 용무 중 표시](media/Presence_Busy.png) <span data-ttu-id="2e261-117">다른 용무 중</span><span class="sxs-lookup"><span data-stu-id="2e261-117">Busy</span></span> |  ![채워진 빨간색 원, 다른 용무 중 표시](media/Presence_Busy.png) <span data-ttu-id="2e261-119">다른 용무 중</span><span class="sxs-lookup"><span data-stu-id="2e261-119">Busy</span></span>  |
|| ![채워진 빨간색 원, 통화 중 표시](media/Presence_Busy.png) <span data-ttu-id="2e261-121">통화 중</span><span class="sxs-lookup"><span data-stu-id="2e261-121">On a call</span></span>|
|| ![채워진 빨간색 원, 회의 중 표시](media/Presence_Busy.png) <span data-ttu-id="2e261-123">회의 중</span><span class="sxs-lookup"><span data-stu-id="2e261-123">In a meeting</span></span> |
|| ![빈 빨간색 원, 다른 용무 중 표시](media/Presence_Busy_OOF.png) <span data-ttu-id="2e261-125">통화 중, 부재 중</span><span class="sxs-lookup"><span data-stu-id="2e261-125">On a call, out of office</span></span>|
|  ![흰색 선이 있는 빨간색 원, 방해 금지 표시](media/Presence_DND.png) <span data-ttu-id="2e261-127">방해 금지</span><span class="sxs-lookup"><span data-stu-id="2e261-127">Do not disturb</span></span> ||
|| ![흰색 선이 있는 빨간색 원, 프레젠테이션 중 표시](media/Presence_DND.png) <span data-ttu-id="2e261-129">프레젠테이션 중</span><span class="sxs-lookup"><span data-stu-id="2e261-129">Presenting</span></span>|
|| ![흰색 선이 있는 빨간색 원, 집중하는 중 표시](media/Presence_DND.png) <span data-ttu-id="2e261-131">집중하는 중</span><span class="sxs-lookup"><span data-stu-id="2e261-131">Focusing</span></span>|
| ![노란색 시계 아이콘, 자리 비움 표시](media/Presence_Away.png) <span data-ttu-id="2e261-133">자리 비움</span><span class="sxs-lookup"><span data-stu-id="2e261-133">Away</span></span>| ![노란색 시계 아이콘, 자리 비움 표시](media/Presence_Away.png) <span data-ttu-id="2e261-135">자리 비움</span><span class="sxs-lookup"><span data-stu-id="2e261-135">Away</span></span>|
|| <span data-ttu-id="2e261-136">![노란색 시계 아이콘, 자리 비움 표시](media/Presence_Away.png)자리 비움 마지막 접속 *시간*</span><span class="sxs-lookup"><span data-stu-id="2e261-136">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![노란색 시계 아이콘, 자리 비움, 곧 돌아오겠음 표시](media/Presence_Away.png) <span data-ttu-id="2e261-138">곧 돌아오겠음</span><span class="sxs-lookup"><span data-stu-id="2e261-138">Be right back</span></span>| |
|| ![노란색 시계 아이콘, 퇴근 표시](media/Presence_Away.png)  <span data-ttu-id="2e261-140">퇴근</span><span class="sxs-lookup"><span data-stu-id="2e261-140">Off Work</span></span>|
|| ![X가 있는 회색 원, 오프라인 표시](media/Presence_Offline.png) <span data-ttu-id="2e261-142">오프라인</span><span class="sxs-lookup"><span data-stu-id="2e261-142">Offline</span></span> |
|| ![빈 회색 원, 상태 알 수 없음 표시](media/Presence_Unknown.png) <span data-ttu-id="2e261-144">상태 알 수 없음</span><span class="sxs-lookup"><span data-stu-id="2e261-144">Status unknown</span></span>|
||![대각선이 있는 빈 빨간색 원, 차단됨 표시](media/Presence_Blocked.png) <span data-ttu-id="2e261-146">차단됨</span><span class="sxs-lookup"><span data-stu-id="2e261-146">Blocked</span></span> |
|| ![화살표가 있는 자주색 원, 부재 중 표시](media/Presence_OOF.png) <span data-ttu-id="2e261-148">부재 중</span><span class="sxs-lookup"><span data-stu-id="2e261-148">Out of Office</span></span>|
|||

<span data-ttu-id="2e261-149">앱 구성 현재 상태는 사용자 활동 (사용 가능, 자리 비움), Outlook 일정 상태 (모임 중) 또는 팀 앱 상태 (통화 중)를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e261-149">App-configured presence states are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting).</span></span> <span data-ttu-id="2e261-150">포커스 모드에서 일정을 기반으로 하는 경우에는 사용자가 Teans에 표시 되는 상태가 되며 다른 제품에서는 방해 금지로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e261-150">Note that when you are in focus mode based on your calendar, Focusing will be the state people see in Teans but will show as Do not disturb in other products.</span></span>

<span data-ttu-id="2e261-151">컴퓨터를 잠그거나 유휴 또는 절전 모드로 전환 하면 현재 상태 상태가 ' 자리 비움 '으로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e261-151">Your current presence state changes to Away when you lock your computer or when it enters idle or sleep mode.</span></span> <span data-ttu-id="2e261-152">모바일에서 팀 앱이 백그라운드에 있을 때마다 현재 상태는 자리 비움으로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e261-152">On mobile, your presence status changes to Away whenever the Teams app is in the background.</span></span>

<span data-ttu-id="2e261-153">사용자는 현재 상태와 관계없이 Teams에서 전송된 모든 채팅 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="2e261-153">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="2e261-154">누군가 메시지를 보낼 때 사용자가 오프라인 상태인 경우 다음번에 사용자가 온라인 상태가 되면 채팅 메시지가 Teams에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="2e261-154">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="2e261-155">사용자가 방해 금지를 사용 하는 경우 채팅 메시지는 계속 표시 되지만 배너 알림은 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e261-155">If a user is in Do not disturb, the user will still get chat messages but banner notifications aren't displayed.</span></span>

<span data-ttu-id="2e261-156">사용자는 수신 전화를 음성 메일로 이동 하는 방해 금지를 제외한 모든 현재 상태에서 전화를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="2e261-156">Users receive calls in all presence states except for Do not disturb, in which incoming calls go to voicemail.</span></span> <span data-ttu-id="2e261-157">받는 사람이 발신자를 차단하는 경우 전화가 전달되지 않으며 받는 사람의 현재 상태가 발신자에 오프라인으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e261-157">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="2e261-158">사용자는 Teams에서 **설정** > **개인 정보**로 이동하여 특정 사용자를 우선 순위 액세스 목록에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e261-158">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="2e261-159">우선 순위 액세스 권한이 있는 사용자는 사용자가 방해 금지 인 경우에도 사용자에 게 연락할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e261-159">People who have priority access can contact the user even when the user is in Do not disturb.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="2e261-160">Teams의 관리자 설정을 비즈니스용 Skype와 비교</span><span class="sxs-lookup"><span data-stu-id="2e261-160">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="2e261-161">Teams의 관리자 설정은 비즈니스용 Skype와 다음과 같은 점에서 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="2e261-161">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="2e261-162">Teams에서 조직의 사용자는 현재 상태 공유를 항상 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e261-162">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="2e261-163">Teams에서는 개인 정보(현재 상태를 볼 수 있는 사용자를 정의하는 위치) 구성을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2e261-163">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="2e261-164">Teams의 사용자는 항상 모든 사용자와 현재 상태 공유(페더레이션 서비스 포함)가 활성화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e261-164">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="2e261-165">연락처 목록(비즈니스용 Skype에 연락처 목록이 있는 경우)은 **채팅 > 연락처** 또는 **통화 > 연락처** 아래에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e261-165">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="2e261-166">Teams의 사용자는 클라이언트 방해 금지 및 혁신적인 기능이 항상 활성화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e261-166">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="2e261-167">Teams가 Outlook과 통합된 경우 사용자는 일정(부재 중 및 기타 일정 정보 포함) 통합이 항상 활성화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e261-167">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="2e261-168">조직에서 비즈니스용 Skype를 사용하는 경우 Teams의 사용자는 *마지막 접속* 또는 *다음 시간동안 자리 비움* 표시기가 항상 활성화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e261-168">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="2e261-169">Teams 관리자가 이러한 설정을 사용자 지정하는 기능은 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e261-169">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="2e261-170">비즈니스용 Skype와 동시 사용</span><span class="sxs-lookup"><span data-stu-id="2e261-170">Coexistence with Skype for Business</span></span>

<span data-ttu-id="2e261-171">조직에서 비즈니스용 Skype를 사용하는 경우 Teams의 현재 상태가 작동하는 방법에 대한 자세한 내용은 [비즈니스용 Skype와 동시 사용](coexistence-chat-calls-presence.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2e261-171">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
