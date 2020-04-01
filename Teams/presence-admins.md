---
title: Teams에서의 사용자 현재 상태
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: Teams에서의 현재 상태에 대한 관리자를 위한 정보.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: ea756b24a0292a35d4e47252383bfc954fcb8fa7
ms.sourcegitcommit: 4ee9835282e1440d03abc6dbcd172bc20c5b3015
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2020
ms.locfileid: "43096973"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="f1414-103">Teams에서의 사용자 현재 상태</span><span class="sxs-lookup"><span data-stu-id="f1414-103">User presence in Teams</span></span>

<span data-ttu-id="f1414-104">현재 상태는 Microsoft 팀 (및 Office 365)의 사용자 프로필의 일부로, 다른 사용자에 대 한 현재의 가용성과 상태를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1414-104">Presence is part of a user's profile in Microsoft Teams (and throughout Office 365) that indicates the user's current availability and status to other users.</span></span> <span data-ttu-id="f1414-105">기본적으로 Teams를 사용하는 조직의 모든 사용자는 온라인으로 다른 사용자의 대화 가능 여부를 거의 실시간으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1414-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f1414-106">사용자가 **Teams 전용** 모드로 이동한 후 비즈니스용 Skype 클라이언트를 제거하면 Outlook 및 기타 Office 앱에서 현재 상태가 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1414-106">If you uninstall the Skype for Business client after you move a user to **Teams Only** mode, presence stops working in Outlook and other Office apps.</span></span> <span data-ttu-id="f1414-107">현재 상태는 Teams에서 잘 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="f1414-107">Presence works fine in Teams.</span></span> <span data-ttu-id="f1414-108">해결 방법: **Teams 전용** 모드에서 팀을 실행하는 경우에도 Outlook (및 기타 Office 앱)에서 현재 상태를 보려면 비즈니스용 Skype를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1414-108">Workaround: To see presence in Outlook (and other Office apps), Skype for Business must be installed, even if you're running Teams in **Teams Only** mode.</span></span> <span data-ttu-id="f1414-109">Microsoft는 이 문제를 알고 있으며 해결하기 위해 노력하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1414-109">Microsoft is aware of this problem and is working on a fix.</span></span>

<span data-ttu-id="f1414-110">Outlook에 있는 팀의 현재 상태는 Outlook 2013 데스크톱 앱 이상에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1414-110">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="f1414-111">Teams에서의 현재 상태</span><span class="sxs-lookup"><span data-stu-id="f1414-111">Presence states in Teams</span></span>

|<span data-ttu-id="f1414-112">사용자가 구성함</span><span class="sxs-lookup"><span data-stu-id="f1414-112">User configured</span></span>|<span data-ttu-id="f1414-113">앱이 구성함</span><span class="sxs-lookup"><span data-stu-id="f1414-113">App configured</span></span>|
|:--- |:---|
| ![채워진 녹색 확인 표시, 현재 상태 대화 가능 표시](media/Presence_Available.png) <span data-ttu-id="f1414-115">대화 가능</span><span class="sxs-lookup"><span data-stu-id="f1414-115">Available</span></span>|![채워진 녹색 확인 표시, 현재 상태 대화 가능 표시](media/Presence_Available.png) <span data-ttu-id="f1414-117">대화 가능</span><span class="sxs-lookup"><span data-stu-id="f1414-117">Available</span></span>|
|| ![빈 녹색 확인 표시, 대화 가능, 부재 중 표시](media/Presence_Available_OOF.png) <span data-ttu-id="f1414-119">대화 가능, 부재 중</span><span class="sxs-lookup"><span data-stu-id="f1414-119">Available, Out of Office</span></span> |
|  ![채워진 빨간색 원, 다른 용무 중 표시](media/Presence_Busy.png) <span data-ttu-id="f1414-121">다른 용무 중</span><span class="sxs-lookup"><span data-stu-id="f1414-121">Busy</span></span> |  ![채워진 빨간색 원, 다른 용무 중 표시](media/Presence_Busy.png) <span data-ttu-id="f1414-123">다른 용무 중</span><span class="sxs-lookup"><span data-stu-id="f1414-123">Busy</span></span>  |
|| ![채워진 빨간색 원, 통화 중 표시](media/Presence_Busy.png) <span data-ttu-id="f1414-125">통화 중</span><span class="sxs-lookup"><span data-stu-id="f1414-125">On a call</span></span>|
|| ![채워진 빨간색 원, 회의 중 표시](media/Presence_Busy.png) <span data-ttu-id="f1414-127">회의 중</span><span class="sxs-lookup"><span data-stu-id="f1414-127">In a meeting</span></span> |
|| ![빈 빨간색 원, 다른 용무 중 표시](media/Presence_Busy_OOF.png) <span data-ttu-id="f1414-129">통화 중, 부재 중</span><span class="sxs-lookup"><span data-stu-id="f1414-129">On a call, out of office</span></span>|
|  ![흰색 선이 있는 빨간색 원, 방해 금지 표시](media/Presence_DND.png) <span data-ttu-id="f1414-131">방해 금지</span><span class="sxs-lookup"><span data-stu-id="f1414-131">Do not disturb</span></span> ||
|| ![흰색 선이 있는 빨간색 원, 프레젠테이션 중 표시](media/Presence_DND.png) <span data-ttu-id="f1414-133">프레젠테이션 중</span><span class="sxs-lookup"><span data-stu-id="f1414-133">Presenting</span></span>|
|| ![흰색 선이 있는 빨간색 원, 집중하는 중 표시](media/Presence_DND.png) <span data-ttu-id="f1414-135">집중하는 중</span><span class="sxs-lookup"><span data-stu-id="f1414-135">Focusing</span></span>|
| ![노란색 시계 아이콘, 자리 비움 표시](media/Presence_Away.png) <span data-ttu-id="f1414-137">자리 비움</span><span class="sxs-lookup"><span data-stu-id="f1414-137">Away</span></span>| ![노란색 시계 아이콘, 자리 비움 표시](media/Presence_Away.png) <span data-ttu-id="f1414-139">자리 비움</span><span class="sxs-lookup"><span data-stu-id="f1414-139">Away</span></span>|
|| <span data-ttu-id="f1414-140">![노란색 시계 아이콘, 자리 비움 표시](media/Presence_Away.png)자리 비움 마지막 접속 *시간*</span><span class="sxs-lookup"><span data-stu-id="f1414-140">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![노란색 시계 아이콘, 자리 비움, 곧 돌아오겠음 표시](media/Presence_Away.png) <span data-ttu-id="f1414-142">곧 돌아오겠음</span><span class="sxs-lookup"><span data-stu-id="f1414-142">Be right back</span></span>| |
|| ![노란색 시계 아이콘, 퇴근 표시](media/Presence_Away.png)  <span data-ttu-id="f1414-144">퇴근</span><span class="sxs-lookup"><span data-stu-id="f1414-144">Off Work</span></span>|
|| ![X가 있는 회색 원, 오프라인 표시](media/Presence_Offline.png) <span data-ttu-id="f1414-146">오프라인</span><span class="sxs-lookup"><span data-stu-id="f1414-146">Offline</span></span> |
|| ![빈 회색 원, 상태 알 수 없음 표시](media/Presence_Unknown.png) <span data-ttu-id="f1414-148">상태 알 수 없음</span><span class="sxs-lookup"><span data-stu-id="f1414-148">Status unknown</span></span>|
||![대각선이 있는 빈 빨간색 원, 차단됨 표시](media/Presence_Blocked.png) <span data-ttu-id="f1414-150">차단됨</span><span class="sxs-lookup"><span data-stu-id="f1414-150">Blocked</span></span> |
|| ![화살표가 있는 자주색 원, 부재 중 표시](media/Presence_OOF.png) <span data-ttu-id="f1414-152">부재 중</span><span class="sxs-lookup"><span data-stu-id="f1414-152">Out of Office</span></span>|
|||

<span data-ttu-id="f1414-153">앱 구성 현재 상태는 사용자 활동 (사용 가능, 자리 비움), Outlook 일정 상태 (모임 중) 또는 팀 앱 상태 (통화 중)를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1414-153">App-configured presence states are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting).</span></span>

<span data-ttu-id="f1414-154">컴퓨터를 잠그거나 유휴 또는 절전 모드로 전환 하면 현재 상태 상태가 ' 자리 비움 '으로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1414-154">Your current presence state changes to Away when you lock your computer or when it enters idle or sleep mode.</span></span> <span data-ttu-id="f1414-155">모바일에서 팀 앱이 백그라운드에 있을 때마다 현재 상태는 자리 비움으로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1414-155">On mobile, your presence status changes to Away whenever the Teams app is in the background.</span></span>

<span data-ttu-id="f1414-156">사용자는 현재 상태와 관계없이 Teams에서 전송된 모든 채팅 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="f1414-156">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="f1414-157">누군가 메시지를 보낼 때 사용자가 오프라인 상태인 경우 다음번에 사용자가 온라인 상태가 되면 채팅 메시지가 Teams에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="f1414-157">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="f1414-158">사용자가 방해 금지를 사용 하는 경우 채팅 메시지는 계속 표시 되지만 배너 알림은 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1414-158">If a user is in Do not disturb, the user will still get chat messages but banner notifications aren't displayed.</span></span>

<span data-ttu-id="f1414-159">사용자는 수신 전화를 음성 메일로 이동 하는 방해 금지를 제외한 모든 현재 상태에서 전화를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="f1414-159">Users receive calls in all presence states except for Do not disturb, in which incoming calls go to voicemail.</span></span> <span data-ttu-id="f1414-160">받는 사람이 발신자를 차단하는 경우 전화가 전달되지 않으며 받는 사람의 현재 상태가 발신자에 오프라인으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1414-160">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="f1414-161">사용자는 Teams에서 **설정** > **개인 정보**로 이동하여 특정 사용자를 우선 순위 액세스 목록에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1414-161">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="f1414-162">우선 순위 액세스 권한이 있는 사용자는 사용자가 방해 금지 인 경우에도 사용자에 게 연락할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1414-162">People who have priority access can contact the user even when the user is in Do not disturb.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="f1414-163">Teams의 관리자 설정을 비즈니스용 Skype와 비교</span><span class="sxs-lookup"><span data-stu-id="f1414-163">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="f1414-164">Teams의 관리자 설정은 비즈니스용 Skype와 다음과 같은 점에서 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="f1414-164">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="f1414-165">Teams에서 조직의 사용자는 현재 상태 공유를 항상 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1414-165">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="f1414-166">Teams에서는 개인 정보(현재 상태를 볼 수 있는 사용자를 정의하는 위치) 구성을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f1414-166">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="f1414-167">Teams의 사용자는 항상 모든 사용자와 현재 상태 공유(페더레이션 서비스 포함)가 활성화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1414-167">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="f1414-168">연락처 목록(비즈니스용 Skype에 연락처 목록이 있는 경우)은 **채팅 > 연락처** 또는 **통화 > 연락처** 아래에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1414-168">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="f1414-169">Teams의 사용자는 클라이언트 방해 금지 및 혁신적인 기능이 항상 활성화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1414-169">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="f1414-170">Teams가 Outlook과 통합된 경우 사용자는 일정(부재 중 및 기타 일정 정보 포함) 통합이 항상 활성화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1414-170">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="f1414-171">조직에서 비즈니스용 Skype를 사용하는 경우 Teams의 사용자는 *마지막 접속* 또는 *다음 시간동안 자리 비움* 표시기가 항상 활성화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1414-171">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="f1414-172">Teams 관리자가 이러한 설정을 사용자 지정하는 기능은 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1414-172">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="f1414-173">비즈니스용 Skype와 동시 사용</span><span class="sxs-lookup"><span data-stu-id="f1414-173">Coexistence with Skype for Business</span></span>

<span data-ttu-id="f1414-174">조직에서 비즈니스용 Skype를 사용하는 경우 Teams의 현재 상태가 작동하는 방법에 대한 자세한 내용은 [비즈니스용 Skype와 동시 사용](coexistence-chat-calls-presence.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f1414-174">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
