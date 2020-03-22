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
ms.openlocfilehash: 7e0d7ef2fa7ae12f660bf6b77ba7c45a8c49ab10
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863199"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="b82f8-103">Teams에서의 사용자 현재 상태</span><span class="sxs-lookup"><span data-stu-id="b82f8-103">User presence in Teams</span></span>

<span data-ttu-id="b82f8-104">현재 상태는 Microsoft Teams(및 Office 365 전체)의 사용자 프로필의 일부로서 다른 사용자에게 사용자의 현재 대화 가능 여부 및 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b82f8-104">Presence is part of a user’s profile in Microsoft Teams (and throughout Office 365) that indicates the user’s current availability and status to other users.</span></span> <span data-ttu-id="b82f8-105">기본적으로 Teams를 사용하는 조직의 모든 사용자는 온라인으로 다른 사용자의 대화 가능 여부를 거의 실시간으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b82f8-105">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b82f8-106">사용자가 **Teams 전용** 모드로 이동한 후 비즈니스용 Skype 클라이언트를 제거하면 Outlook 및 기타 Office 앱에서 현재 상태가 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b82f8-106">If you uninstall the Skype for Business client after you move a user to **Teams Only** mode, presence stops working in Outlook and other Office apps.</span></span> <span data-ttu-id="b82f8-107">현재 상태는 Teams에서 잘 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="b82f8-107">Presence works fine in Teams.</span></span> <span data-ttu-id="b82f8-108">해결 방법: **Teams 전용** 모드에서 팀을 실행하는 경우에도 Outlook (및 기타 Office 앱)에서 현재 상태를 보려면 비즈니스용 Skype를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b82f8-108">Workaround: To see presence in Outlook (and other Office apps), Skype for Business must be installed, even if you're running Teams in **Teams Only** mode.</span></span> <span data-ttu-id="b82f8-109">Microsoft는 이 문제를 알고 있으며 해결하기 위해 노력하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b82f8-109">Microsoft is aware of this problem and is working on a fix.</span></span>

<span data-ttu-id="b82f8-110">Outlook에 있는 팀의 현재 상태는 Outlook 2013 데스크톱 앱 이상에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="b82f8-110">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="b82f8-111">Teams에서의 현재 상태</span><span class="sxs-lookup"><span data-stu-id="b82f8-111">Presence states in Teams</span></span>

<span data-ttu-id="b82f8-112">Teams에서 사용할 수 있는 사용자 현재 상태는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b82f8-112">The user presence states available in Teams are:</span></span>

|<span data-ttu-id="b82f8-113">사용자가 구성함</span><span class="sxs-lookup"><span data-stu-id="b82f8-113">User configured</span></span>|<span data-ttu-id="b82f8-114">앱이 구성함</span><span class="sxs-lookup"><span data-stu-id="b82f8-114">App configured</span></span>|
|:--- |:---|
| ![채워진 녹색 확인 표시, 현재 상태 대화 가능 표시](media/Presence_Available.png) <span data-ttu-id="b82f8-116">대화 가능</span><span class="sxs-lookup"><span data-stu-id="b82f8-116">Available</span></span>|![채워진 녹색 확인 표시, 현재 상태 대화 가능 표시](media/Presence_Available.png) <span data-ttu-id="b82f8-118">대화 가능</span><span class="sxs-lookup"><span data-stu-id="b82f8-118">Available</span></span>|
|| ![빈 녹색 확인 표시, 대화 가능, 부재 중 표시](media/Presence_Available_OOF.png) <span data-ttu-id="b82f8-120">대화 가능, 부재 중</span><span class="sxs-lookup"><span data-stu-id="b82f8-120">Available, Out of Office</span></span> |
|  ![채워진 빨간색 원, 다른 용무 중 표시](media/Presence_Busy.png) <span data-ttu-id="b82f8-122">다른 용무 중</span><span class="sxs-lookup"><span data-stu-id="b82f8-122">Busy</span></span> |  ![채워진 빨간색 원, 다른 용무 중 표시](media/Presence_Busy.png) <span data-ttu-id="b82f8-124">다른 용무 중</span><span class="sxs-lookup"><span data-stu-id="b82f8-124">Busy</span></span>  |
|| ![채워진 빨간색 원, 통화 중 표시](media/Presence_Busy.png) <span data-ttu-id="b82f8-126">통화 중</span><span class="sxs-lookup"><span data-stu-id="b82f8-126">On a call</span></span>|
|| ![채워진 빨간색 원, 회의 중 표시](media/Presence_Busy.png) <span data-ttu-id="b82f8-128">회의 중</span><span class="sxs-lookup"><span data-stu-id="b82f8-128">In a meeting</span></span> |
|| ![빈 빨간색 원, 다른 용무 중 표시](media/Presence_Busy_OOF.png) <span data-ttu-id="b82f8-130">통화 중, 부재 중</span><span class="sxs-lookup"><span data-stu-id="b82f8-130">On a call, out of office</span></span>|
|  ![흰색 선이 있는 빨간색 원, 방해 금지 표시](media/Presence_DND.png) <span data-ttu-id="b82f8-132">방해 금지</span><span class="sxs-lookup"><span data-stu-id="b82f8-132">Do not disturb</span></span> ||
|| ![흰색 선이 있는 빨간색 원, 프레젠테이션 중 표시](media/Presence_DND.png) <span data-ttu-id="b82f8-134">프레젠테이션 중</span><span class="sxs-lookup"><span data-stu-id="b82f8-134">Presenting</span></span>|
|| ![흰색 선이 있는 빨간색 원, 집중하는 중 표시](media/Presence_DND.png) <span data-ttu-id="b82f8-136">집중하는 중</span><span class="sxs-lookup"><span data-stu-id="b82f8-136">Focusing</span></span>|
| ![노란색 시계 아이콘, 자리 비움 표시](media/Presence_Away.png) <span data-ttu-id="b82f8-138">자리 비움</span><span class="sxs-lookup"><span data-stu-id="b82f8-138">Away</span></span>| ![노란색 시계 아이콘, 자리 비움 표시](media/Presence_Away.png) <span data-ttu-id="b82f8-140">자리 비움</span><span class="sxs-lookup"><span data-stu-id="b82f8-140">Away</span></span>|
|| <span data-ttu-id="b82f8-141">![노란색 시계 아이콘, 자리 비움 표시](media/Presence_Away.png)자리 비움 마지막 접속 *시간*</span><span class="sxs-lookup"><span data-stu-id="b82f8-141">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![노란색 시계 아이콘, 자리 비움, 곧 돌아오겠음 표시](media/Presence_Away.png) <span data-ttu-id="b82f8-143">곧 돌아오겠음</span><span class="sxs-lookup"><span data-stu-id="b82f8-143">Be right back</span></span>| |
|| ![노란색 시계 아이콘, 퇴근 표시](media/Presence_Away.png)  <span data-ttu-id="b82f8-145">퇴근</span><span class="sxs-lookup"><span data-stu-id="b82f8-145">Off Work</span></span>|
|| ![X가 있는 회색 원, 오프라인 표시](media/Presence_Offline.png) <span data-ttu-id="b82f8-147">오프라인</span><span class="sxs-lookup"><span data-stu-id="b82f8-147">Offline</span></span> |
|| ![빈 회색 원, 상태 알 수 없음 표시](media/Presence_Unknown.png) <span data-ttu-id="b82f8-149">상태 알 수 없음</span><span class="sxs-lookup"><span data-stu-id="b82f8-149">Status unknown</span></span>|
||![대각선이 있는 빈 빨간색 원, 차단됨 표시](media/Presence_Blocked.png) <span data-ttu-id="b82f8-151">차단됨</span><span class="sxs-lookup"><span data-stu-id="b82f8-151">Blocked</span></span> |
|| ![화살표가 있는 자주색 원, 부재 중 표시](media/Presence_OOF.png) <span data-ttu-id="b82f8-153">부재 중</span><span class="sxs-lookup"><span data-stu-id="b82f8-153">Out of Office</span></span>|
|||
 
<span data-ttu-id="b82f8-154">사용자는 수동으로 현재 상태를 몇 가지 옵션으로 설정하고 해당 상태를 다른 모든 사용자에게 보여지도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b82f8-154">Users can manually set their current presence state to some options, and their state gets reflected to all other users.</span></span> <span data-ttu-id="b82f8-155">더 많은 사용자 현재 상태 세부 정보 또한 자동으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="b82f8-155">More user presence details are also automatically updated.</span></span> <span data-ttu-id="b82f8-156">변경 사항은 사용자 활동(대화 가능, 자리 비움), Outlook 일정 상태(회의 중) 또는 Teams 앱 상태(통화 중, 프레젠테이션 중)에 따라 목록에 들여쓰기된 상태를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b82f8-156">The changes are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting), to states that are indented in the list.</span></span> <span data-ttu-id="b82f8-157">15분의 비활성 시간 제한이 있으며, 해당 시간이 지나면 현재 상태가 자리 비움으로 재설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b82f8-157">There's a 15-minute inactivity timeout, after which a current presence state is reset to Away.</span></span>

<span data-ttu-id="b82f8-158">사용자는 현재 상태와 관계없이 Teams에서 전송된 모든 채팅 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="b82f8-158">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="b82f8-159">누군가 메시지를 보낼 때 사용자가 오프라인 상태인 경우 다음번에 사용자가 온라인 상태가 되면 채팅 메시지가 Teams에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="b82f8-159">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="b82f8-160">사용자가 방해 금지 상태인 경우에도 채팅 메시지는 계속 받게 되나 배너 알림은 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b82f8-160">If a user is in a Do Not Disturb state, the user will still get chat messages but a banner notification won't be displayed.</span></span>

<span data-ttu-id="b82f8-161">사용자는 방해 금지 상태를 제외한 모든 현재 상태에서 걸려오는 전화를 받게 되며, 방해 금지 상태에서는 전화가 음성 메일로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="b82f8-161">Users receive calls in all presence states except for Do Not Disturb states, in which incoming calls are delivered to their voicemail.</span></span> <span data-ttu-id="b82f8-162">받는 사람이 발신자를 차단하는 경우 전화가 전달되지 않으며 받는 사람의 현재 상태가 발신자에 오프라인으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b82f8-162">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="b82f8-163">사용자는 Teams에서 **설정** > **개인 정보**로 이동하여 특정 사용자를 우선 순위 액세스 목록에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b82f8-163">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="b82f8-164">우선 순위 액세스 권한이 있는 사용자는 상대방이 방해 금지 상태에 있더라도 연락이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="b82f8-164">People who have priority access can contact the user even when the user is in a Do Not Disturb state.</span></span>

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="b82f8-165">Teams의 관리자 설정을 비즈니스용 Skype와 비교</span><span class="sxs-lookup"><span data-stu-id="b82f8-165">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="b82f8-166">Teams의 관리자 설정은 비즈니스용 Skype와 다음과 같은 점에서 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b82f8-166">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="b82f8-167">Teams에서 조직의 사용자는 현재 상태 공유를 항상 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b82f8-167">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="b82f8-168">Teams에서는 개인 정보(현재 상태를 볼 수 있는 사용자를 정의하는 위치) 구성을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b82f8-168">Privacy (where you define who can see presence) configuration is not available in Teams.</span></span>
- <span data-ttu-id="b82f8-169">Teams의 사용자는 항상 모든 사용자와 현재 상태 공유(페더레이션 서비스 포함)가 활성화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b82f8-169">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="b82f8-170">연락처 목록(비즈니스용 Skype에 연락처 목록이 있는 경우)은 **채팅 > 연락처** 또는 **통화 > 연락처** 아래에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b82f8-170">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="b82f8-171">Teams의 사용자는 클라이언트 방해 금지 및 혁신적인 기능이 항상 활성화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b82f8-171">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="b82f8-172">Teams가 Outlook과 통합된 경우 사용자는 일정(부재 중 및 기타 일정 정보 포함) 통합이 항상 활성화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b82f8-172">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="b82f8-173">조직에서 비즈니스용 Skype를 사용하는 경우 Teams의 사용자는 *마지막 접속* 또는 *다음 시간동안 자리 비움* 표시기가 항상 활성화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b82f8-173">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="b82f8-174">Teams 관리자가 이러한 설정을 사용자 지정하는 기능은 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b82f8-174">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="b82f8-175">비즈니스용 Skype와 동시 사용</span><span class="sxs-lookup"><span data-stu-id="b82f8-175">Coexistence with Skype for Business</span></span>

<span data-ttu-id="b82f8-176">조직에서 비즈니스용 Skype를 사용하는 경우 Teams의 현재 상태가 작동하는 방법에 대한 자세한 내용은 [비즈니스용 Skype와 동시 사용](coexistence-chat-calls-presence.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b82f8-176">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses  Skype for Business.</span></span>
