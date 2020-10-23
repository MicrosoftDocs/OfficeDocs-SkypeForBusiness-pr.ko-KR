---
title: Microsoft 팀 관리 센터에서 비즈니스용 Skype 설정 관리
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection: ''
f1.keywords:
- CSH
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.overview
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.presence
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.skypemeetingbroadcast
- ms.teamsadmincenter.users.skypeforbusiness.settings
ms.custom: ''
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft 팀 관리 센터의 비즈니스용 Skype 기능에 대 한 설정을 관리 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 7248d57c5a2efb49714bf9e43c4e367ef454bfd0
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739236"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="06ac3-103">Microsoft 팀 관리 센터에서 비즈니스용 Skype 설정 관리</span><span class="sxs-lookup"><span data-stu-id="06ac3-103">Manage Skype for Business settings in the Microsoft Teams admin center</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="06ac3-104"><a name="sfb-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="06ac3-104"><a name="sfb-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="06ac3-105">Microsoft 팀 관리 센터에서 관리자는 조직의 비즈니스용 skype 사용자에 대 한 비즈니스용 Skype 기능을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-105">As an admin, the Microsoft Teams admin center is where you manage Skype for Business features for Skype for Business users in your organization.</span></span> <span data-ttu-id="06ac3-106">비즈니스용 **skype** 페이지에서 [조직의](#manage-skype-for-business-settings-for-your-organization) 설정을 관리 하 고 사용자 세부 정보 페이지의 **비즈니스용 skype** 탭에서 [개별 사용자에](#manage-skype-for-business-settings-for-individual-users) 대 한 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-106">You can manage settings [for your organization](#manage-skype-for-business-settings-for-your-organization) on the **Skype for Business** page and settings [for individual users](#manage-skype-for-business-settings-for-individual-users) on the **Skype for Business** tab of user detail pages.</span></span>

<span data-ttu-id="06ac3-107">조직의 공존 모드가 **팀 으로만**설정 되어 있지 않은 경우 Microsoft 팀 관리 센터에 **비즈니스용 Skype** 페이지만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-107">You'll only see the **Skype for Business** page in the Microsoft Teams admin center if the coexistence mode for your organization isn't set to **Teams only**.</span></span> <span data-ttu-id="06ac3-108">마찬가지로 사용자의 공존 모드가 **팀 전용**인 경우 사용자에 대 한 **비즈니스용 Skype** 탭만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-108">Similarly, you'll only see the **Skype for Business** tab for a user if the coexistence mode of the user isn't **Teams only**.</span></span> <span data-ttu-id="06ac3-109">공존 모드에 대 한 자세한 내용은 [비즈니스용 Skype 공존 및 상호 운용성에 대 한 이해](teams-and-skypeforbusiness-coexistence-and-interoperability.md) 를 참조 하 고 [공존 및 업그레이드 설정을 설정](setting-your-coexistence-and-upgrade-settings.md)하는 방법에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="06ac3-109">To learn more about coexistence modes, see [Understand Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and [Set your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

> [!NOTE]
> <span data-ttu-id="06ac3-110">이전에는 Microsoft 팀 관리 센터의 **레거시 포털** 에 비즈니스용 Skype 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-110">Skype for Business settings were previously in **Legacy portal** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="06ac3-111">레거시 포털을 사용 하지 않는 경우에는 비즈니스용 Skype 관리 센터의 팀 관리 센터에서 이러한 새로운 위치로 설정을 마이그레이션 했습니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-111">With the retirement of the legacy portal, we migrated the settings to these new locations in the Teams admin center for Skype for Business management.</span></span>

## <a name="manage-skype-for-business-settings-for-your-organization"></a><span data-ttu-id="06ac3-112">조직의 비즈니스용 Skype 설정을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-112">Manage Skype for Business settings for your organization</span></span>

<span data-ttu-id="06ac3-113">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **조직 전체**  >  **비즈니스용 Skype**설정으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-113">In the left navigation of the Microsoft Teams admin center, go to **Org-wide settings** > **Skype for Business**.</span></span> <span data-ttu-id="06ac3-114">여기서는 조직의 모든 비즈니스용 Skype 사용자에 대 한 Skype 모임 브로드캐스트, 현재 상태 프라이버시 및 모바일 장치 알림을 구성 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-114">From here, you can configure and manage Skype Meeting Broadcast, presence privacy, and mobile device notifications for all Skype for Business users in your organization.</span></span>

### <a name="skype-meeting-broadcast"></a><span data-ttu-id="06ac3-115">Skype 모임 브로드캐스트</span><span class="sxs-lookup"><span data-stu-id="06ac3-115">Skype Meeting Broadcast</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="06ac3-116"><a name="sfb-org-wide-broadcast"> </a></span><span class="sxs-lookup"><span data-stu-id="06ac3-116"><a name="sfb-org-wide-broadcast"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="06ac3-117">다음 설정을 사용 하 여 조직에서 [Skype 모임 브로드캐스트](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) 를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-117">Use the following settings to manage [Skype Meeting Broadcast](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="관리 센터의 Skype 모임 브로드캐스트 설정 스크린샷":::

- <span data-ttu-id="06ac3-119">**Skype 모임 브로드캐스트**: 조직에 대해 Skype 모임 브로드캐스트를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-119">**Skype Meeting Broadcasts**: Turn this on to enable Skype Meeting Broadcast for your organization.</span></span> <span data-ttu-id="06ac3-120">이 기능을 사용 하도록 설정한 후에 [는 Skype 모임 브로드캐스트에 대 한 네트워크를 설정](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-120">After you enable this feature, you need to [set up your network for Skype Meeting Broadcast](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).</span></span>
- <span data-ttu-id="06ac3-121">**미리 보기 기능**: 새로운 기능에 빠르게 액세스 하려면이 옵션을 설정 하세요.</span><span class="sxs-lookup"><span data-stu-id="06ac3-121">**See preview features**: Turn this on to get early access to new features.</span></span>
- <span data-ttu-id="06ac3-122">**이끌이는 익명 모임을 예약할 수**있습니다. 이끌이가 로그인 할 필요 없이 조직 외부의 모든 사용자에 게 참가할 수 있도록 하는 브로드캐스트 이벤트를 만들도록 하려면이 옵션을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-122">**Organizers can schedule anonymous meetings**: Turn this on if you want to let organizers create broadcast events that allow anyone outside your organization to join without having to sign in.</span></span> 
- <span data-ttu-id="06ac3-123">**Skype 모임 브로드캐스트 모임 기록**: 이끌이 및 발표자가 모임을 녹음/녹화할 수 있도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-123">**Record Skype Meeting Broadcast meetings**: Turn this on to enable organizers and presenters to record meetings.</span></span>  
- <span data-ttu-id="06ac3-124">**참석자를 위한 헬프 데스크 지원 url**: 모임 참석자가 모임을 진행 하는 동안 도움이 필요한 경우 조직에서 사용할 수 있는 조직의 지원 url을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-124">**Helpdesk support URL for attendees**: Enter your organization's support URL that meeting attendees can use if they need help during a meeting.</span></span>

### <a name="presence-and-mobile-notifications"></a><span data-ttu-id="06ac3-125">현재 상태 및 모바일 알림</span><span class="sxs-lookup"><span data-stu-id="06ac3-125">Presence and mobile notifications</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="06ac3-126"><a name="sfb-org-wide-presence-mobile"> </a></span><span class="sxs-lookup"><span data-stu-id="06ac3-126"><a name="sfb-org-wide-presence-mobile"> </a></span></span>
<!-- Do not remove the bookmark link above. -->


<span data-ttu-id="06ac3-127">조직의 비즈니스용 Skype 현재 상태 개인 정보 및 모바일 알림을 관리 하려면 다음 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-127">Use the following settings to manage Skype for Business presence privacy and mobile notifications in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="관리 센터의 현재 상태 설정 스크린샷":::

#### <a name="presence"></a><span data-ttu-id="06ac3-129">현재 상태</span><span class="sxs-lookup"><span data-stu-id="06ac3-129">Presence</span></span>

<span data-ttu-id="06ac3-130">기본적으로 조직의 비즈니스용 Skype 사용자는 다른 비즈니스용 Skype 사용자의 현재 상태를 볼 수 있습니다 (예: 사용 중, 약속 있음 또는 자리 비움).</span><span class="sxs-lookup"><span data-stu-id="06ac3-130">By default, Skype for Business users in your organization can see the presence status (such as Available, Busy, or Away) of other Skype for Business users.</span></span> <span data-ttu-id="06ac3-131">다음 중 하나를 선택 하 여 비즈니스용 Skype 사용자의 현재 상태를 볼 수 있는 사용자를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-131">Choose one of the following to set who can see the presence of your Skype for Business users.</span></span>

- <span data-ttu-id="06ac3-132">**현재 상태 정보 표시**: 사용자의 **외부** 또는 **차단** 목록에 추가 되지 않은 조직의 모든 비즈니스용 Skype 사용자는 해당 사용자의 현재 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-132">**Automatically display presence information**: Any Skype for Business user in your organization who hasn't been added to the user's **External** or **Blocked** list can see that user's presence.</span></span>
- <span data-ttu-id="06ac3-133">**사용자의 대화 상대 에게만 현재 상태 정보 표시**: 사용자의 대화 **상대 목록에** 추가 되지 않은 모든 비즈니스용 Skype 사용자의 현재 상태 **External** 를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-133">**Display presence information only to a user's contacts**: Any Skype for Business user in the user's Contacts list who isn't added to their **External** or **Blocked** list can see that user's presence.</span></span> <span data-ttu-id="06ac3-134">사용자는 **설정**  >  **도구**  >  **옵션**으로 이동해 서 비즈니스용 Skype에서이 설정을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-134">Users can override this setting in Skype for Business by going to **Settings** > **Tools** > **Options**.</span></span>

#### <a name="mobile-notifications"></a><span data-ttu-id="06ac3-135">모바일 알림</span><span class="sxs-lookup"><span data-stu-id="06ac3-135">Mobile notifications</span></span>

<span data-ttu-id="06ac3-136">비즈니스용 Skype mobile 사용자가 푸시 알림 서비스를 통해 들어오고 부재 중 메신저 대화, 보이스 메일 메시지, 부재 중 통화에 대 한 알림을 받을 지 여부를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-136">You can set whether your Skype for Business mobile users get alerts about incoming and missed instant messages, voicemail messages, and missed calls through a push notification service.</span></span> <span data-ttu-id="06ac3-137">조직에서 사용 하는 모바일 장치에 따라 **Microsoft 푸시 알림 서비스**, **Apple 푸시 알림 서비스**또는 둘 다를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-137">Depending on the mobile devices used in your organization, you can use the **Microsoft Push Notification Service**, the **Apple Push Notification Service**, or both.</span></span>

<span data-ttu-id="06ac3-138">다음 사항에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="06ac3-138">Keep the following in mind:</span></span>

- <span data-ttu-id="06ac3-139">푸시 알림을 끄면 사용자가 다음에 모바일 장치에서 비즈니스용 Skype를 시작할 때 모든 알림을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-139">If you turn off push notifications, users will get all alerts the next time they start Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="06ac3-140">기본적으로 푸시 알림은 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-140">By default, push notifications are turned on.</span></span> <span data-ttu-id="06ac3-141">개별 사용자는 모바일 장치에서 비즈니스용 Skype를 통해 기능을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-141">Individual users can turn them off in Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="06ac3-142">푸시 알림을 해제 하면 사용자가 다시 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-142">When you turn off push notifications, users can't turn them back on.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="06ac3-143">Microsoft는 다른 회사를 사용 하 여 Windows Phone, iPhone 및 iPad 사용자에 게 비즈니스용 Skype 모바일 알림을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-143">Microsoft uses other companies to provide real-time Skype for Business mobile notifications for Windows Phone, iPhone, and iPad users.</span></span> <span data-ttu-id="06ac3-144">본 [개인 정보 취급 방침](https://go.microsoft.com/fwlink/p/?linkid=247732)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="06ac3-144">See this [Privacy Statement](https://go.microsoft.com/fwlink/p/?linkid=247732).</span></span>

## <a name="manage-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="06ac3-145">개별 사용자에 대 한 비즈니스용 Skype 설정 관리</span><span class="sxs-lookup"><span data-stu-id="06ac3-145">Manage Skype for Business settings for individual users</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="06ac3-146"><a name="sfb-user-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="06ac3-146"><a name="sfb-user-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="06ac3-147">개별 사용자의 비즈니스용 Skype 설정을 관리 하려면 팀 관리 센터의 왼쪽 탐색 **에서 사용자의**표시 이름을 클릭 하 여 사용자 세부 정보 페이지를 연 다음 비즈니스용 **Skype 설정** 탭을 선택 합니다. 여기에서 사용자에 대 한 외부 액세스 및 모임 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-147">To manage Skype for Business settings for individual users, in the left navigation of the Teams admin center, go to **Users**, click the user's display name to open the user details page, and then select the **Skype for Business settings** tab. From here, you can configure external access and meeting settings for the user.</span></span>

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="사용자 세부 정보 페이지의 비즈니스용 Skype 탭 스크린샷":::

### <a name="external-access-settings"></a><span data-ttu-id="06ac3-149">외부 액세스 설정</span><span class="sxs-lookup"><span data-stu-id="06ac3-149">External access settings</span></span>

<span data-ttu-id="06ac3-150">사용자가 조직 외부 사용자와 통신할 수 있는지 여부를 선택적으로 허용 하거나 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-150">You can selectively allow or block whether a user can communicate with people outside your organization.</span></span>

- <span data-ttu-id="06ac3-151">**외부 비즈니스용 skype 사용자**: 페더레이션 도메인에서 사용자가 비즈니스용 skype 사용자와 통신할 수 있도록 하려면이 옵션을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-151">**External Skype for Business users**: Turn this on if you want to allow the user to communicate with Skype for Business users in federated domains.</span></span>
- <span data-ttu-id="06ac3-152">**외부 skype 사용자**: 사용자가 Skype 사용자와 통신할 수 있도록 허용 하려면이 옵션을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-152">**External Skype users**: Turn this on if you want to allow the user to communicate with Skype users.</span></span> 

### <a name="meeting-settings"></a><span data-ttu-id="06ac3-153">모임 설정</span><span class="sxs-lookup"><span data-stu-id="06ac3-153">Meeting settings</span></span>

<span data-ttu-id="06ac3-154">사용자에 대해 다음 모임 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-154">You can configure the following meeting settings for the user.</span></span>

- <span data-ttu-id="06ac3-155">**오디오 & 비디오**: 다음 오디오 및 비디오 설정 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-155">**Audio & video**: Choose one of the following audio and video settings:</span></span>

    - <span data-ttu-id="06ac3-156">**없음**: 사용자가 오디오 또는 비디오를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-156">**None**: User can't use audio or video.</span></span>
    - <span data-ttu-id="06ac3-157">**오디오만**: 사용자가 오디오는 사용할 수 있지만 비디오는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-157">**Audio only**: User can use audio but not video.</span></span>
    - <span data-ttu-id="06ac3-158">**오디오 및 비디오**: 사용자는 오디오 및 비디오를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-158">**Audio and video**: User can use audio and video.</span></span>
    - <span data-ttu-id="06ac3-159">**오디오 및 비디오 (HD)**: 사용자는 오디오 및 고화질 비디오를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-159">**Audio and video (HD)**: User can use audio and high definition video.</span></span>
    
- <span data-ttu-id="06ac3-160">**모임 & 기록**: 사용자가 대화 및 모임을 녹화할 수 있도록이 기능을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-160">**Record conversations & meetings**: Turn this on to allow the user to record conversations and meetings.</span></span>
- <span data-ttu-id="06ac3-161">**준수**: 전자적으로 저장 된 정보를 유지 해야 하는 경우이 기능을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="06ac3-161">**Compliance**: Turn this on if you're legally required to retain electronically stored information.</span></span> 
