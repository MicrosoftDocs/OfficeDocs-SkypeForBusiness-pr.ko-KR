---
title: Microsoft Teams 관리 센터에서 비즈니스용 Skype 설정 관리
author: cichur
ms.author: v-cichur
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
description: Microsoft Teams 관리 센터에서 비즈니스용 Skype 기능에 대한 설정을 관리하는 방법을 배워야 합니다.
ms.openlocfilehash: 944a5f8101b8355f4a2cc3e18966e5eb01b94be9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834218"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="e32a8-103">Microsoft Teams 관리 센터에서 비즈니스용 Skype 설정 관리</span><span class="sxs-lookup"><span data-stu-id="e32a8-103">Manage Skype for Business settings in the Microsoft Teams admin center</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="e32a8-104"><a name="sfb-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="e32a8-104"><a name="sfb-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="e32a8-105">관리자인 Microsoft Teams 관리 센터는 조직의 비즈니스용 Skype 사용자를 위한 비즈니스용 Skype 기능을 관리하는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="e32a8-105">As an admin, the Microsoft Teams admin center is where you manage Skype for Business features for Skype for Business users in your organization.</span></span> <span data-ttu-id="e32a8-106">비즈니스용 **Skype** 페이지에서 조직의 설정과 사용자 세부 [](#manage-skype-for-business-settings-for-individual-users) 정보 페이지의 비즈니스용 Skype 탭에 **있는** 개별 사용자에 대한 설정을 관리할 수 있습니다. [](#manage-skype-for-business-settings-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="e32a8-106">You can manage settings [for your organization](#manage-skype-for-business-settings-for-your-organization) on the **Skype for Business** page and settings [for individual users](#manage-skype-for-business-settings-for-individual-users) on the **Skype for Business** tab of user detail pages.</span></span>

<span data-ttu-id="e32a8-107">조직의 공존 모드가 **Teams로만** 설정되어 있지 않은 경우 비즈니스용 Skype 페이지만 **표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="e32a8-107">You'll only see the **Skype for Business** page if the coexistence mode for your organization isn't set to **Teams only**.</span></span> <span data-ttu-id="e32a8-108">마찬가지로 사용자의 공존 모드가 **Teams만이** 아닌 경우 사용자의 비즈니스용 Skype 탭만 **표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="e32a8-108">Similarly, you'll only see the **Skype for Business** tab for a user if the coexistence mode of the user isn't **Teams only**.</span></span> <span data-ttu-id="e32a8-109">공존 모드에 대한 자세한 내용은 [Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) 및 비즈니스용 Skype 공존 및 상호 운영성 이해 및 공존 및 업그레이드 설정을 [참조하세요.](setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e32a8-109">To learn more about coexistence modes, see [Understand Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md) and [Set your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e32a8-110">비즈니스용 Skype 설정은 이전에 Microsoft Teams 관리 센터의 레거시 **포털에** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e32a8-110">Skype for Business settings were previously in **Legacy portal** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="e32a8-111">레거시 포털이 사용 중지된 후 비즈니스용 Skype 관리용 Teams 관리 센터에서 이러한 새 위치로 설정을 마이그레이션했습니다.</span><span class="sxs-lookup"><span data-stu-id="e32a8-111">With the retirement of the legacy portal, we migrated the settings to these new locations in the Teams admin center for Skype for Business management.</span></span>

<span data-ttu-id="e32a8-112">Microsoft Teams 관리 센터에서 비즈니스용 Skype 기능을 관리하려면 전역 관리자 또는 비즈니스용 Skype 관리자의 [Azure AD](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) 관리자 역할이 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e32a8-112">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Microsoft Teams admin center.</span></span>

## <a name="manage-skype-for-business-settings-for-your-organization"></a><span data-ttu-id="e32a8-113">조직의 비즈니스용 Skype 설정 관리</span><span class="sxs-lookup"><span data-stu-id="e32a8-113">Manage Skype for Business settings for your organization</span></span>

<span data-ttu-id="e32a8-114">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 비즈니스용 Skype의 **전체**  >  **설정으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="e32a8-114">In the left navigation of the Microsoft Teams admin center, go to **Org-wide settings** > **Skype for Business**.</span></span> <span data-ttu-id="e32a8-115">여기에서 조직의 모든 비즈니스용 Skype 사용자에 대한 Skype 모임 브로드캐스트, 현재 상태 개인 정보 보호 및 모바일 장치 알림을 구성하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e32a8-115">From here, you can configure and manage Skype Meeting Broadcast, presence privacy, and mobile device notifications for all Skype for Business users in your organization.</span></span>

### <a name="skype-meeting-broadcast"></a><span data-ttu-id="e32a8-116">Skype 모임 브로드캐스트</span><span class="sxs-lookup"><span data-stu-id="e32a8-116">Skype Meeting Broadcast</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="e32a8-117"><a name="sfb-org-wide-broadcast"> </a></span><span class="sxs-lookup"><span data-stu-id="e32a8-117"><a name="sfb-org-wide-broadcast"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="e32a8-118">조직에서 [Skype 모임 브로드캐스트를 관리하려면](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) 다음 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e32a8-118">Use the following settings to manage [Skype Meeting Broadcast](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="관리 센터의 Skype 모임 브로드캐스트 설정 스크린샷":::

- <span data-ttu-id="e32a8-120">**Skype 모임 브로드캐스트:** 조직에서 Skype 모임 브로드캐스트를 사용하도록 설정하려면 이 기능을 끄면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e32a8-120">**Skype Meeting Broadcasts**: Turn this on to enable Skype Meeting Broadcast for your organization.</span></span> <span data-ttu-id="e32a8-121">이 기능을 사용하도록 설정한 후 Skype 모임 브로드캐스트에 대한 [네트워크를 설정해야 합니다.](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)</span><span class="sxs-lookup"><span data-stu-id="e32a8-121">After you enable this feature, you need to [set up your network for Skype Meeting Broadcast](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).</span></span>
- <span data-ttu-id="e32a8-122">**미리 보기 기능 참조:** 이 기능을 켜서 새 기능에 대한 초기 액세스 권한을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="e32a8-122">**See preview features**: Turn this on to get early access to new features.</span></span>
- <span data-ttu-id="e32a8-123">**이끌이는** 익명 모임을 예약할 수 있습니다. 이끌이가 조직 외부의 모든 사용자가 로그인할 필요 없이 참가할 수 있는 브로드캐스트 이벤트를 만들 수 있도록 허용하려는 경우 이 기능을 켰습니다.</span><span class="sxs-lookup"><span data-stu-id="e32a8-123">**Organizers can schedule anonymous meetings**: Turn this on if you want to let organizers create broadcast events that allow anyone outside your organization to join without having to sign in.</span></span> 
- <span data-ttu-id="e32a8-124">**Skype 모임 브로드캐스트 모임** 녹화: 이끌이와 발표자가 모임을 녹음/녹화할 수 있도록 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="e32a8-124">**Record Skype Meeting Broadcast meetings**: Turn this on to enable organizers and presenters to record meetings.</span></span>  
- <span data-ttu-id="e32a8-125">**참석자에** 대한 기술 지원 URL: 모임 참석자에 대한 도움이 필요한 경우 사용할 수 있는 조직의 지원 URL을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e32a8-125">**Helpdesk support URL for attendees**: Enter your organization's support URL that meeting attendees can use if they need help during a meeting.</span></span>

### <a name="presence-and-mobile-notifications"></a><span data-ttu-id="e32a8-126">현재 상태 및 모바일 알림</span><span class="sxs-lookup"><span data-stu-id="e32a8-126">Presence and mobile notifications</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="e32a8-127"><a name="sfb-org-wide-presence-mobile"> </a></span><span class="sxs-lookup"><span data-stu-id="e32a8-127"><a name="sfb-org-wide-presence-mobile"> </a></span></span>
<!-- Do not remove the bookmark link above. -->


<span data-ttu-id="e32a8-128">다음 설정을 사용하여 조직의 비즈니스용 Skype 현재 상태 개인 정보 보호 및 모바일 알림을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="e32a8-128">Use the following settings to manage Skype for Business presence privacy and mobile notifications in your organization.</span></span>

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="관리 센터의 현재 상태 설정 스크린샷":::

#### <a name="presence"></a><span data-ttu-id="e32a8-130">현재 상태</span><span class="sxs-lookup"><span data-stu-id="e32a8-130">Presence</span></span>

<span data-ttu-id="e32a8-131">기본적으로 조직의 비즈니스용 Skype 사용자는 다른 비즈니스용 Skype 사용자의 현재 상태(예: 사용 가능, 바쁘게 또는 부재 중)를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e32a8-131">By default, Skype for Business users in your organization can see the presence status (such as Available, Busy, or Away) of other Skype for Business users.</span></span> <span data-ttu-id="e32a8-132">비즈니스용 Skype 사용자의 현재 상태 표시를 볼 수 있는 사용자를 설정하기 위해 다음 중 하나를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="e32a8-132">Choose one of the following to set who can see the presence of your Skype for Business users.</span></span>

- <span data-ttu-id="e32a8-133">**현재 상태 정보** 자동 표시: 사용자의 외부 또는 차단 목록에 추가되지 않은  조직의  비즈니스용 Skype 사용자는 해당 사용자의 현재 상태 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e32a8-133">**Automatically display presence information**: Any Skype for Business user in your organization who hasn't been added to the user's **External** or **Blocked** list can see that user's presence.</span></span>
- <span data-ttu-id="e32a8-134">**사용자의** 연락처에만 현재 상태 정보 표시: 사용자의 연락처 목록에 외부 또는 차단 목록에 추가되지 않은  비즈니스용 Skype 사용자는 해당 사용자의 현재 상태만 볼 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="e32a8-134">**Display presence information only to a user's contacts**: Any Skype for Business user in the user's Contacts list who isn't added to their **External** or **Blocked** list can see that user's presence.</span></span> <span data-ttu-id="e32a8-135">사용자는 설정 도구 옵션으로 이동하여 비즈니스용 Skype에서 이 설정을 오버라이드할  >  **수**  >  **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="e32a8-135">Users can override this setting in Skype for Business by going to **Settings** > **Tools** > **Options**.</span></span>

#### <a name="mobile-notifications"></a><span data-ttu-id="e32a8-136">모바일 알림</span><span class="sxs-lookup"><span data-stu-id="e32a8-136">Mobile notifications</span></span>

<span data-ttu-id="e32a8-137">비즈니스용 Skype 모바일 사용자가 푸시 알림 서비스를 통해 수신 및 부재 중 인스턴트 메시지, 음성 메일 메시지 및 부재 중 전화에 대한 알림을 받을지 여부를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e32a8-137">You can set whether your Skype for Business mobile users get alerts about incoming and missed instant messages, voicemail messages, and missed calls through a push notification service.</span></span> <span data-ttu-id="e32a8-138">조직에서 사용되는 모바일 디바이스에 따라 **Microsoft 푸시** 알림 서비스, **Apple 푸시** 알림 서비스 또는 둘 다를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e32a8-138">Depending on the mobile devices used in your organization, you can use the **Microsoft Push Notification Service**, the **Apple Push Notification Service**, or both.</span></span>

<span data-ttu-id="e32a8-139">다음에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e32a8-139">Keep the following in mind:</span></span>

- <span data-ttu-id="e32a8-140">푸시 알림을 끄면 다음에 모바일 장치에서 비즈니스용 Skype를 시작할 때 모든 알림이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e32a8-140">If you turn off push notifications, users will get all alerts the next time they start Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="e32a8-141">기본적으로 푸시 알림은 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e32a8-141">By default, push notifications are turned on.</span></span> <span data-ttu-id="e32a8-142">개별 사용자는 모바일 장치에서 비즈니스용 Skype에서 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e32a8-142">Individual users can turn them off in Skype for Business on their mobile device.</span></span>
- <span data-ttu-id="e32a8-143">푸시 알림을 해제하면 사용자가 푸시 알림을 다시 끄지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="e32a8-143">When you turn off push notifications, users can't turn them back on.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="e32a8-144">Microsoft는 다른 회사를 사용하여 Windows Phone, iPhone 및 iPad 사용자에게 비즈니스용 Skype 모바일 알림을 실시간으로 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e32a8-144">Microsoft uses other companies to provide real-time Skype for Business mobile notifications for Windows Phone, iPhone, and iPad users.</span></span> <span data-ttu-id="e32a8-145">본 개인 정보 [취급 방침을 참조합니다.](https://go.microsoft.com/fwlink/p/?linkid=247732)</span><span class="sxs-lookup"><span data-stu-id="e32a8-145">See this [Privacy Statement](https://go.microsoft.com/fwlink/p/?linkid=247732).</span></span>

## <a name="manage-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="e32a8-146">개별 사용자의 비즈니스용 Skype 설정 관리</span><span class="sxs-lookup"><span data-stu-id="e32a8-146">Manage Skype for Business settings for individual users</span></span>

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<span data-ttu-id="e32a8-147"><a name="sfb-user-settings"> </a></span><span class="sxs-lookup"><span data-stu-id="e32a8-147"><a name="sfb-user-settings"> </a></span></span>
<!-- Do not remove the bookmark link above. -->

<span data-ttu-id="e32a8-148">개별 사용자의 비즈니스용 Skype 설정을 관리하려면 Teams 관리 센터의 왼쪽 탐색 창에서 사용자로 이동하고 **사용자의** 표시 이름을 클릭하여 사용자 세부 정보 페이지를 연 다음 비즈니스용 **Skype** 설정 탭을 선택합니다. 여기에서 사용자에 대한 외부 액세스 및 모임 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e32a8-148">To manage Skype for Business settings for individual users, in the left navigation of the Teams admin center, go to **Users**, click the user's display name to open the user details page, and then select the **Skype for Business settings** tab. From here, you can configure external access and meeting settings for the user.</span></span>

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="사용자 세부 정보 페이지의 비즈니스용 Skype 탭 스크린샷":::

### <a name="external-access-settings"></a><span data-ttu-id="e32a8-150">외부 액세스 설정</span><span class="sxs-lookup"><span data-stu-id="e32a8-150">External access settings</span></span>

<span data-ttu-id="e32a8-151">사용자가 조직 외부의 사용자와 통신할 수 있는지 여부를 선택적으로 허용하거나 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e32a8-151">You can selectively allow or block whether a user can communicate with people outside your organization.</span></span>

- <span data-ttu-id="e32a8-152">**외부 비즈니스용 Skype 사용자:** 사용자가 페더맹된 도메인에서 비즈니스용 Skype 사용자와 통신할 수 있도록 허용하려면 이 기능을 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e32a8-152">**External Skype for Business users**: Turn this on if you want to allow the user to communicate with Skype for Business users in federated domains.</span></span>
- <span data-ttu-id="e32a8-153">**외부 Skype 사용자:** 사용자가 Skype 사용자와 통신할 수 있도록 허용하려는 경우 이 기능을 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e32a8-153">**External Skype users**: Turn this on if you want to allow the user to communicate with Skype users.</span></span> 

### <a name="meeting-settings"></a><span data-ttu-id="e32a8-154">모임 설정</span><span class="sxs-lookup"><span data-stu-id="e32a8-154">Meeting settings</span></span>

<span data-ttu-id="e32a8-155">사용자에 대해 다음 모임 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e32a8-155">You can configure the following meeting settings for the user.</span></span>

- <span data-ttu-id="e32a8-156">**오디오 & 비디오:** 다음 오디오 및 비디오 설정 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e32a8-156">**Audio & Video**: Choose one of the following audio and video settings:</span></span>

    - <span data-ttu-id="e32a8-157">**없음:** 사용자가 오디오 또는 비디오를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e32a8-157">**None**: User can't use audio or video.</span></span>
    - <span data-ttu-id="e32a8-158">**오디오만:** 사용자는 오디오를 사용할 수 있지만 비디오는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e32a8-158">**Audio only**: User can use audio but not video.</span></span>
    - <span data-ttu-id="e32a8-159">**오디오 및 비디오:** 사용자가 오디오 및 비디오를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e32a8-159">**Audio and video**: User can use audio and video.</span></span>
    - <span data-ttu-id="e32a8-160">**오디오 및 비디오(HD)**: 사용자가 오디오 및 고화질 비디오를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e32a8-160">**Audio and video (HD)**: User can use audio and high definition video.</span></span>
    
- <span data-ttu-id="e32a8-161">**모임에서 &** 기록: 사용자가 대화 및 모임을 녹음/녹화할 수 있도록 이 기능을 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e32a8-161">**Record conversations & meetings**: Turn this on to allow the user to record conversations and meetings.</span></span>
- <span data-ttu-id="e32a8-162">**규정** 준수: 전자적으로 저장된 정보를 법적으로 보존해야 하는 경우 이 기능을 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e32a8-162">**Compliance**: Turn this on if you're legally required to retain electronically stored information.</span></span> 
