---
title: Teams에서의 사용자 현재 상태
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: rakayala
description: 팀의 현재 상태와 현재 상태 기능에 대 한 관리 설정에 대해 알아봅니다.
ms.custom: seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9fd066fe06126043475a7264b3b2c4501c7ac3ae
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650951"
---
# <a name="user-presence-in-teams"></a><span data-ttu-id="c328c-103">Teams에서의 사용자 현재 상태</span><span class="sxs-lookup"><span data-stu-id="c328c-103">User presence in Teams</span></span>

<span data-ttu-id="c328c-104">현재 상태는 Microsoft 팀에서 사용자 프로필의 일부 이며 (Microsoft 365 또는 Office 365에 걸쳐 있는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-104">Presence is part of a user's profile in Microsoft Teams (and throughout Microsoft 365 or Office 365).</span></span> <span data-ttu-id="c328c-105">현재 상태는 사용자의 현재 사용 가능 시간 및 다른 사용자에 대 한 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-105">Presence indicates the user's current availability and status to other users.</span></span> <span data-ttu-id="c328c-106">기본적으로 Teams를 사용하는 조직의 모든 사용자는 온라인으로 다른 사용자의 대화 가능 여부를 거의 실시간으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-106">By default, anyone in your organization using Teams can see (in nearly real time) if other users are available online.</span></span> <span data-ttu-id="c328c-107">모바일에서 페이지를 새로 고치면 웹 및 데스크톱 버전에서 실시간으로 현재 상태가 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-107">Presence is updated in real time on the web and desktop versions when you refresh the page on mobile.</span></span>

 > [!Note]
 > <span data-ttu-id="c328c-108">다른 플랫폼의 팀 사용자 프로필에 대 한 자세한 내용은 [플랫폼용 팀 기능](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c328c-108">For details about Teams user profiles on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="presence-states-in-teams"></a><span data-ttu-id="c328c-109">Teams에서의 현재 상태</span><span class="sxs-lookup"><span data-stu-id="c328c-109">Presence states in Teams</span></span>

|<span data-ttu-id="c328c-110">사용자가 구성함</span><span class="sxs-lookup"><span data-stu-id="c328c-110">User configured</span></span>|<span data-ttu-id="c328c-111">앱이 구성함</span><span class="sxs-lookup"><span data-stu-id="c328c-111">App configured</span></span>|
|:--- |:---|
| ![채워진 녹색 확인 표시, 현재 상태 대화 가능 표시](media/Presence_Available.png) <span data-ttu-id="c328c-113">대화 가능</span><span class="sxs-lookup"><span data-stu-id="c328c-113">Available</span></span>|![채워진 녹색 확인 표시, 현재 상태 대화 가능 표시](media/Presence_Available.png) <span data-ttu-id="c328c-115">대화 가능</span><span class="sxs-lookup"><span data-stu-id="c328c-115">Available</span></span>|
|| ![빈 녹색 확인 표시, 대화 가능, 부재 중 표시](media/Presence_Available_OOF.png) <span data-ttu-id="c328c-117">사용 가능, 부재 중.</span><span class="sxs-lookup"><span data-stu-id="c328c-117">Available, Out of Office.</span></span> <span data-ttu-id="c328c-118">참고: 사용자가 "자동 회신"을 설정한 기간 동안에는 부재 중 office가 자동으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-118">Note: Out of office is automatically set for the periods of time where the user sets "automatic replies".</span></span> <span data-ttu-id="c328c-119">이 기간 동안 사용자가 앱을 사용 하는 경우 "부재 중, 사용 가능" 등의 이중 현재 상태가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-119">If the user is using the app during these periods of time, a dual presence might be shown, such as "Out of office, available".</span></span> |
|  ![채워진 빨간색 원, 다른 용무 중 표시](media/Presence_Busy.png) <span data-ttu-id="c328c-121">다른 용무 중</span><span class="sxs-lookup"><span data-stu-id="c328c-121">Busy</span></span> |  ![채워진 빨간색 원, 다른 용무 중 표시](media/Presence_Busy.png) <span data-ttu-id="c328c-123">다른 용무 중</span><span class="sxs-lookup"><span data-stu-id="c328c-123">Busy</span></span>  |
|| ![채워진 빨간색 원, 통화 중 표시](media/Presence_Busy.png) <span data-ttu-id="c328c-125">통화 중</span><span class="sxs-lookup"><span data-stu-id="c328c-125">On a call</span></span>|
|| ![채워진 빨간색 원, 회의 중 표시](media/Presence_Busy.png) <span data-ttu-id="c328c-127">회의 중</span><span class="sxs-lookup"><span data-stu-id="c328c-127">In a meeting</span></span> |
|| ![빈 빨간색 원, 다른 용무 중 표시](media/Presence_Busy_OOF.png) <span data-ttu-id="c328c-129">통화 중, 부재 중</span><span class="sxs-lookup"><span data-stu-id="c328c-129">On a call, out of office</span></span>|
|  ![흰색 선이 있는 빨간색 원, 방해 금지 표시](media/Presence_DND.png) <span data-ttu-id="c328c-131">방해 금지</span><span class="sxs-lookup"><span data-stu-id="c328c-131">Do not disturb</span></span> ||
|| ![흰색 선이 있는 빨간색 원, 프레젠테이션 중 표시](media/Presence_DND.png) <span data-ttu-id="c328c-133">프레젠테이션 중</span><span class="sxs-lookup"><span data-stu-id="c328c-133">Presenting</span></span>|
|| ![흰색 선이 있는 빨간색 원, 집중하는 중 표시](media/Presence_DND.png) <span data-ttu-id="c328c-135">집중할.</span><span class="sxs-lookup"><span data-stu-id="c328c-135">Focusing.</span></span> <span data-ttu-id="c328c-136">포커스는 사용자가 일정에서 MyAnalytics/Insights의 포커스 시간을 예약할 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-136">Focus happens when the users schedule focus time in MyAnalytics/Insights in their calendars.</span></span>|
| ![노란색 시계 아이콘, 자리 비움 표시](media/Presence_Away.png) <span data-ttu-id="c328c-138">자리 비움</span><span class="sxs-lookup"><span data-stu-id="c328c-138">Away</span></span>| ![노란색 시계 아이콘, 자리 비움 표시](media/Presence_Away.png) <span data-ttu-id="c328c-140">자리 비움</span><span class="sxs-lookup"><span data-stu-id="c328c-140">Away</span></span>|
|| <span data-ttu-id="c328c-141">![노란색 시계 아이콘, 자리 비움 표시](media/Presence_Away.png)자리 비움 마지막 접속 *시간*</span><span class="sxs-lookup"><span data-stu-id="c328c-141">![Yellow clock icon, indicates away](media/Presence_Away.png) Away Last Seen *time*</span></span>|
|![노란색 시계 아이콘, 자리 비움, 곧 돌아오겠음 표시](media/Presence_Away.png) <span data-ttu-id="c328c-143">곧 돌아오겠음</span><span class="sxs-lookup"><span data-stu-id="c328c-143">Be right back</span></span>| |
|![X가 있는 회색 원, 오프라인 표시](media/Presence_Offline.png) <span data-ttu-id="c328c-145">오프 라인으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-145">Appear offline.</span></span> <span data-ttu-id="c328c-146">팀에서 곧 제공 될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-146">Coming soon in Teams.</span></span>|![X가 있는 회색 원, 오프라인 표시](media/Presence_Offline.png) <span data-ttu-id="c328c-148">이거나.</span><span class="sxs-lookup"><span data-stu-id="c328c-148">Offline.</span></span>  <span data-ttu-id="c328c-149">사용자가 몇 분 동안 장치에 로그인 하지 않으면 오프 라인으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-149">When users aren't logged in on any of their devices for a few minutes, they appear offline.</span></span> | |
|| ![빈 회색 원, 상태 알 수 없음 표시](media/Presence_Unknown.png) <span data-ttu-id="c328c-151">상태 알 수 없음</span><span class="sxs-lookup"><span data-stu-id="c328c-151">Status unknown</span></span>|
|| ![화살표가 있는 자주색 원, 부재 중 표시](media/Presence_OOF.png) <span data-ttu-id="c328c-153">부재 중.</span><span class="sxs-lookup"><span data-stu-id="c328c-153">Out of Office.</span></span> <span data-ttu-id="c328c-154">자동 회신이 설정 된 경우 부재 중 Office가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-154">Out of Office is used when an automatic reply is set.</span></span> <span data-ttu-id="c328c-155">(Outlook 에서만 사용할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="c328c-155">(Available in Outlook only.)</span></span> |
|||

<span data-ttu-id="c328c-156">앱 구성 현재 상태는 사용자 활동 (사용 가능, 자리 비움), Outlook 일정 상태 (모임 중) 또는 팀 앱 상태 (통화 중)를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-156">App-configured presence states are based on user activity (Available, Away), Outlook calendar states (In a meeting), or Teams app states (In a call, Presenting).</span></span> <span data-ttu-id="c328c-157">일정을 기반으로 하는 포커스 모드에서는 포커스가 팀에 **표시 되는** 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-157">When you're in focus mode based on your calendar, **Focusing** will be the state people see in Teams.</span></span> <span data-ttu-id="c328c-158">포커스 모드는 다른 제품에서 **방해** 금지로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-158">Focus mode will display as **Do not disturb** in other products.</span></span>

<span data-ttu-id="c328c-159">컴퓨터를 잠그거나 컴퓨터가 유휴 또는 절전 모드로 전환 되 면 현재 상태 상태가 "자리 비움"으로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-159">Your current presence state changes to Away when you lock your computer or when your computer enters idle or sleep mode.</span></span> <span data-ttu-id="c328c-160">모바일 장치에서 팀 앱이 백그라운드에 있을 때마다 현재 상태가 자리 비움으로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-160">On a mobile device, your presence status changes to Away whenever the Teams app is in the background.</span></span>

<span data-ttu-id="c328c-161">사용자는 현재 상태와 관계없이 Teams에서 전송된 모든 채팅 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-161">Users receive all chat messages sent to them in Teams regardless of their presence state.</span></span> <span data-ttu-id="c328c-162">누군가 메시지를 보낼 때 사용자가 오프라인 상태인 경우 다음번에 사용자가 온라인 상태가 되면 채팅 메시지가 Teams에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-162">If a user is offline when someone sends them a message, the chat message appears in Teams the next time the user is online.</span></span> <span data-ttu-id="c328c-163">사용자 상태가 방해 금지로 설정 된 경우에도 사용자는 채팅 메시지를 받지만 배너 알림이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-163">If a user state is set to Do not disturb, the user will still receive chat messages, but banner notifications aren't displayed.</span></span>

<span data-ttu-id="c328c-164">사용자는 수신 전화를 음성 메일로 이동 하는 방해 금지를 제외한 모든 현재 상태에서 전화를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-164">Users receive calls in all presence states except for Do not disturb, in which incoming calls go to voicemail.</span></span> <span data-ttu-id="c328c-165">받는 사람이 발신자를 차단하는 경우 전화가 전달되지 않으며 받는 사람의 현재 상태가 발신자에 오프라인으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-165">If the recipient blocked the caller, the call won't be delivered and the caller sees the recipient's presence as Offline.</span></span>

<span data-ttu-id="c328c-166">사용자는 Teams에서 **설정** > **개인 정보**로 이동하여 특정 사용자를 우선 순위 액세스 목록에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-166">Users can add people to their priority access list by going to **Settings** > **Privacy** in Teams.</span></span> <span data-ttu-id="c328c-167">우선 순위가 높은 권한이 있는 사용자는 사용자의 상태가 방해 금지로 설정 된 경우에도 사용자에 게 연락할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-167">People who have priority access can contact the user even when the user's status is set to Do not disturb.</span></span>

### <a name="dual-presence"></a><span data-ttu-id="c328c-168">이중 현재 상태</span><span class="sxs-lookup"><span data-stu-id="c328c-168">Dual presence</span></span>

  <span data-ttu-id="c328c-169">현재 상태는 대부분의 사용자에 게 작동 하는 방식으로 일정 또는 장치 이벤트 (예: 통화)의 이벤트에 의해 동기를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-169">The way presence works for most users is motivated by the events in the calendar or device events, such as a call.</span></span> <span data-ttu-id="c328c-170">사용자는 만료 시간이 일부 인 상태를 수동으로 설정 하 여 UI에서이 상태를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-170">The user can override this status in the UI by manually setting states, which have some expiration time.</span></span>

## <a name="user-configured-states-expiration"></a><span data-ttu-id="c328c-171">사용자 구성 상태 만료</span><span class="sxs-lookup"><span data-stu-id="c328c-171">User configured states expiration</span></span>

<span data-ttu-id="c328c-172">사용자가 특정 현재 상태를 선택 하는 경우 앱 활동 업데이트 보다 우선 순위를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-172">When a user selects a specific presence state, it takes precedence over any app activity update.</span></span> <span data-ttu-id="c328c-173">예를 들어 사용자가 자신을 방해 금지로 설정 하는 경우에는 모임을 참석할 전화를 걸거나 응답 하더라도 현재 상태는 방해 금지로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-173">For example, if a user sets herself as Do not disturb, her presence will remain as Do not disturb even if she attends a meeting or answers a call.</span></span>

<span data-ttu-id="c328c-174">사용자가 일정 기간 후에는 관련이 없을 수 있는 상태를 표시 하지 않도록 하려면 팀의 기본 만료 설정을 사용 하는 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-174">User configured states have default expiration settings in Teams, in order to prevent users from displaying a status that may not be relevant after a period of time.</span></span>

|<span data-ttu-id="c328c-175">사용자 구성 상태</span><span class="sxs-lookup"><span data-stu-id="c328c-175">User configured state</span></span>|<span data-ttu-id="c328c-176">기본 만료</span><span class="sxs-lookup"><span data-stu-id="c328c-176">Default expiration</span></span>|
|:--- |:---|
| <span data-ttu-id="c328c-177">다른 용무 중</span><span class="sxs-lookup"><span data-stu-id="c328c-177">Busy</span></span>|<span data-ttu-id="c328c-178">1 일</span><span class="sxs-lookup"><span data-stu-id="c328c-178">1 day</span></span>|
| <span data-ttu-id="c328c-179">방해 금지</span><span class="sxs-lookup"><span data-stu-id="c328c-179">Do not disturb</span></span>|<span data-ttu-id="c328c-180">1 일</span><span class="sxs-lookup"><span data-stu-id="c328c-180">1 day</span></span>|
| <span data-ttu-id="c328c-181">타인</span><span class="sxs-lookup"><span data-stu-id="c328c-181">Others</span></span>|<span data-ttu-id="c328c-182">7 일</span><span class="sxs-lookup"><span data-stu-id="c328c-182">7 days</span></span>|
|||

## <a name="admin-settings-in-teams-compared-to-skype-for-business"></a><span data-ttu-id="c328c-183">Teams의 관리자 설정을 비즈니스용 Skype와 비교</span><span class="sxs-lookup"><span data-stu-id="c328c-183">Admin settings in Teams compared to Skype for Business</span></span>

<span data-ttu-id="c328c-184">Teams의 관리자 설정은 비즈니스용 Skype와 다음과 같은 점에서 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-184">The following admin settings Skype for Business are different in Teams:</span></span>

- <span data-ttu-id="c328c-185">Teams에서 조직의 사용자는 현재 상태 공유를 항상 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-185">In Teams, presence sharing is always enabled for users in the organization.</span></span> <span data-ttu-id="c328c-186">개인 정보 (현재 상태를 볼 수 있는 사용자를 정의 하는 위치) 구성은 팀에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-186">Privacy (where you define who can see presence) configuration isn't available in Teams.</span></span>
- <span data-ttu-id="c328c-187">Teams의 사용자는 항상 모든 사용자와 현재 상태 공유(페더레이션 서비스 포함)가 활성화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-187">Presence sharing with everyone (including Federated services) is always enabled for users in Teams.</span></span> <span data-ttu-id="c328c-188">연락처 목록(비즈니스용 Skype에 연락처 목록이 있는 경우)은 **채팅 > 연락처** 또는 **통화 > 연락처** 아래에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-188">Their contact list (if they had one in Skype for Business) is visible under **Chat > Contacts** or under **Calls > Contacts**.</span></span>
- <span data-ttu-id="c328c-189">Teams의 사용자는 클라이언트 방해 금지 및 혁신적인 기능이 항상 활성화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-189">Client Do Not Disturb and Breakthrough features are always enabled for users in Teams.</span></span>
- <span data-ttu-id="c328c-190">Teams가 Outlook과 통합된 경우 사용자는 일정(부재 중 및 기타 일정 정보 포함) 통합이 항상 활성화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-190">Calendar (includes out of office and other calendar information) integration  is always enabled for users when Teams is integrated with Outlook.</span></span>
- <span data-ttu-id="c328c-191">조직에서 비즈니스용 Skype를 사용하는 경우 Teams의 사용자는 *마지막 접속* 또는 *다음 시간동안 자리 비움* 표시기가 항상 활성화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-191">The *Last seen* or *Away since*  indicator is always enabled for users in Teams if the organization also uses Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="c328c-192">Teams 관리자가 이러한 설정을 사용자 지정하는 기능은 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-192">The ability of a Teams admin to customize these settings is not currently supported.</span></span>

## <a name="admin-settings-in-teams-compared-to-microsoft-outlook"></a><span data-ttu-id="c328c-193">Microsoft Outlook과 팀의 관리자 설정</span><span class="sxs-lookup"><span data-stu-id="c328c-193">Admin settings in Teams compared to Microsoft Outlook</span></span>

<span data-ttu-id="c328c-194">Outlook에 있는 팀의 현재 상태는 Outlook 2013 데스크톱 앱 이상에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-194">Teams presence in Outlook is supported on the Outlook 2013 desktop app and later.</span></span>

<span data-ttu-id="c328c-195">사용자 계정의 업그레이드 모드 정책이 팀 전용으로 설정 되어 있는 경우 Outlook에서 현재 상태를 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-195">If the upgrade mode policy of the user account is set to TeamsOnly, Outlook talks to Teams to get presence.</span></span> <span data-ttu-id="c328c-196">사용자 계정이 팀 전용으로 설정 되어 있지 않은 경우에는 Outlook이 비즈니스용 Skype와 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="c328c-196">If the user account isn't set to TeamsOnly, then Outlook talks to Skype for Business.</span></span>

## <a name="coexistence-with-skype-for-business"></a><span data-ttu-id="c328c-197">비즈니스용 Skype와 동시 사용</span><span class="sxs-lookup"><span data-stu-id="c328c-197">Coexistence with Skype for Business</span></span>

<span data-ttu-id="c328c-198">조직에서 비즈니스용 Skype를 사용 하는 경우 팀의 현재 상태 기능에 대 한 자세한 내용은 [비즈니스용 skype를 사용 하 여 함께 공존](coexistence-chat-calls-presence.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c328c-198">See [Coexistence with Skype for Business](coexistence-chat-calls-presence.md) for details on how Teams presence functions when your organization also uses Skype for Business.</span></span>
