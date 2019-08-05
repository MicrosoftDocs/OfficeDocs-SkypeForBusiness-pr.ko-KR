---
title: 공존 및 업그레이드 설정 설정
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: 이 문서는 공존 모드를 선택 하 고 다른 공존 설정을 설정 하는 데 도움이 될 것입니다.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 52b398a9e70d650ad2afd70c60250076f1ab9fc2
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2019
ms.locfileid: "36183437"
---
# <a name="setting-your-coexistence-and-upgrade-settings"></a><span data-ttu-id="0f53e-103">공존 및 업그레이드 설정 설정</span><span class="sxs-lookup"><span data-stu-id="0f53e-103">Setting your coexistence and upgrade settings</span></span>

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="0f53e-104">비즈니스용 Skype 사용자를 업그레이드 하 여 팀을 사용 하는 경우 사용자를 위한 원활한 프로세스를 수행 하는 데 도움이 되는 몇 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f53e-104">When you upgrade your Skype for Business users to use Teams, you have several options to help you make it a seamless process for your users.</span></span> <span data-ttu-id="0f53e-105">조직의 모든 사용자에 대해 동시에 동시 사용 및 업그레이드 설정을 설정 하거나 조직의 단일 또는 사용자 집합에 대 한 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f53e-105">You have the option to make coexistence and upgrade settings for all of the users in your organization at once, or you can make settings changes for a single or set of users in your organization.</span></span> <span data-ttu-id="0f53e-106">이전 버전의 비즈니스용 Skype 클라이언트에서는 이러한 설정을 인식 하지 못할 수 있다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="0f53e-106">Note that older versions of Skype for Business clients may not honor these settings.</span></span> <span data-ttu-id="0f53e-107">비즈니스용 Skype 클라이언트 버전에 대 한 자세한 내용을 보려면 비즈니스용 [skype 다운로드 및 업데이트 페이지로](https://docs.microsoft.com/en-us/skypeforbusiness/software-updates)이동 하세요.</span><span class="sxs-lookup"><span data-stu-id="0f53e-107">For more information about Skype for Business client versions, go to the [Skype for Business downloads and updates page](https://docs.microsoft.com/en-us/skypeforbusiness/software-updates).</span></span> 

<span data-ttu-id="0f53e-108">비즈니스용 [skype에서](coexistence-chat-calls-presence.md) [Microsoft 팀과 비즈니스용 skype 공존 및 상호 운용성](teams-and-skypeforbusiness-coexistence-and-interoperability.md) 또는 공존을 이해 하 여 사용할 수 있는 모드 유형을 더 잘 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f53e-108">You can get a better understanding of the types of modes that are available to you by reading [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md) or [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a><span data-ttu-id="0f53e-109">조직의 모든 사용자에 대 한 업그레이드 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="0f53e-109">Set upgrade options for all users in your organization</span></span>

<span data-ttu-id="0f53e-110">![](media/teams-logo-30x30.png) **Microsoft 팀 관리 센터를 사용 하 여** microsoft 팀 로고를 표시 하는 아이콘</span><span class="sxs-lookup"><span data-stu-id="0f53e-110">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="0f53e-111">왼쪽 탐색 창에서 **조직 전체 설정** > **팀 업그레이드**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f53e-111">In the left navigation, go to **Org-wide settings** > **Teams upgrade**.</span></span> 

2. <span data-ttu-id="0f53e-112">**팀 업그레이드** 페이지의 맨 위에서 해당 작업을 수행할 경우 다음과 같이 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f53e-112">At the top of the **Teams upgrade** page, make the following changes if they will work for you.</span></span>
    - <span data-ttu-id="0f53e-113">**공존** 모드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f53e-113">Set the **Coexistence** mode.</span></span>
        - <span data-ttu-id="0f53e-114">**아일랜드** -사용자가 비즈니스용 Skype와 팀을 동시에 사용할 수 있게 하려는 경우이 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f53e-114">**Islands** - Use this setting if you want users to be able to use both Skype for Business and Teams simultaneously.</span></span>
        - <span data-ttu-id="0f53e-115">비즈니스용 **skype 전용** -사용자가 비즈니스용 skype만을 사용 하도록 하려는 경우이 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f53e-115">**Skype for Business only** - Use this setting if you want your users to only use Skype for Business.</span></span>
        - <span data-ttu-id="0f53e-116">**팀만** (일부 조직의 경우 미리 보기)-사용자가 팀만 사용 하도록 하려면이 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f53e-116">**Teams only** (in preview for some organizations) - Use this setting if you want your users to use only Teams.</span></span> <span data-ttu-id="0f53e-117">이 설정을 사용 하는 경우에도 사용자는 비즈니스용 Skype에서 호스트 된 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f53e-117">Note that even with this setting, users can still join meetings hosted in Skype for Business.</span></span>
    - <span data-ttu-id="0f53e-118">**팀이 업그레이드에 사용할 수 있는 비즈니스용 Skype 사용자에 게 알림을**설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f53e-118">Set **Notify Skype for Business users that Teams is available for upgrade**.</span></span> <span data-ttu-id="0f53e-119">이 기능을 켜면 비즈니스용 Skype 사용자에 게 곧 팀 앱으로 업그레이드 될 것으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f53e-119">If you turn this on, it will tell the Skype for Business users that they will soon be upgraded to the Teams app.</span></span>
    - <span data-ttu-id="0f53e-120">**사용자가 비즈니스용 Skype 모임에 참가 하도록 기본 설정 앱**을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f53e-120">Set the **Preferred app for users to join Skype for Business meetings**.</span></span> <span data-ttu-id="0f53e-121">이 설정은 비즈니스용 Skype 모임에 참가 하는 데 사용 되는 앱을 결정 하 고 공존 모드 값에 관계 없이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f53e-121">This setting determines which app is used for joining Skype for Business meetings and is honored regardless of the value of coexistence mode.</span></span>
      - <span data-ttu-id="0f53e-122">**Skype 모임 앱**</span><span class="sxs-lookup"><span data-stu-id="0f53e-122">**Skype Meetings app**</span></span>
      - <span data-ttu-id="0f53e-123">**기능이 제한 된 비즈니스용 Skype**</span><span class="sxs-lookup"><span data-stu-id="0f53e-123">**Skype for Business with limited features**</span></span>
    - <span data-ttu-id="0f53e-124">**비즈니스용 Skype 사용자를 위해 백그라운드에서 팀 앱을 다운로드할지**여부를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f53e-124">Set whether to **Download the Teams app in the background for Skype for Business users**.</span></span>  <span data-ttu-id="0f53e-125">이 설정은 Windows에서 비즈니스용 Skype를 실행 하는 사용자를 위해 팀 앱을 자동으로 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f53e-125">This setting silently downloads the Teams app for users running Skype for Business on Windows.</span></span> <span data-ttu-id="0f53e-126">이는 사용자의 공존 모드가 팀 전용 이거나 비즈니스용 Skype에서 보류 중인 업그레이드의 알림을 사용 하는 경우에만 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f53e-126">It is honored only if coexistence mode for the user is Teams only or if notifications of pending upgrade are enabled in Skype for Business.</span></span>
3. <span data-ttu-id="0f53e-127">변경한 후 **저장** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f53e-127">Click **Save** after you make your changes.</span></span>

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a><span data-ttu-id="0f53e-128">조직의 단일 사용자에 대 한 업그레이드 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="0f53e-128">Set upgrade options for a single user in your organization</span></span>

<span data-ttu-id="0f53e-129">![](media/teams-logo-30x30.png) **Microsoft 팀 관리 센터를 사용 하 여** microsoft 팀 로고를 표시 하는 아이콘</span><span class="sxs-lookup"><span data-stu-id="0f53e-129">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="0f53e-130">왼쪽 탐색 창에서 **사용자**로 이동한 다음 목록에서 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f53e-130">In the left navigation, go to **Users**, and then select the user from the list.</span></span> 
2. <span data-ttu-id="0f53e-131">사용자의 **계정** 탭에서 **팀 업그레이드**아래에서 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f53e-131">On the **Account** tab for the user, under **Teams upgrade**, click **Edit**.</span></span>
3. <span data-ttu-id="0f53e-132">**공존 모드**를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f53e-132">You can set the **Coexistence mode**.</span></span> <span data-ttu-id="0f53e-133">다음 옵션 중에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f53e-133">Choose from the following options:</span></span>
     - <span data-ttu-id="0f53e-134">**조직 전체 설정 사용** -사용자가 **조직 전체** 설정의 설정을 사용 하도록 하려면이 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f53e-134">**Use Org-wide settings** - Use this setting if you want the user to use the settings in the **Org-wide** settings.</span></span> 
     - <span data-ttu-id="0f53e-135">**아일랜드** -사용자가 비즈니스용 Skype와 팀을 모두 사용할 수 있도록 하려면이 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f53e-135">**Islands** - Use this setting if you want the user to be able to use both Skype for Business and Teams.</span></span> 
     - <span data-ttu-id="0f53e-136">비즈니스용 **skype 전용** -사용자가 비즈니스용 skype를 사용 하도록 하려는 경우이 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f53e-136">**Skype for Business only** - Use this setting if you want the user to use Skype for Business.</span></span> 
     - <span data-ttu-id="0f53e-137">**팀 전용** -사용자가 팀만 사용할 수 있도록 하려면이 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f53e-137">**Teams only** - Use this setting if you want the user to use only Teams.</span></span> <span data-ttu-id="0f53e-138">사용자는 계속 비즈니스용 Skype 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f53e-138">The user will still be able to join Skype for Business meetings.</span></span>
4. <span data-ttu-id="0f53e-139">**조직 전체 설정을 사용**하는 것 이외의 **공존 모드** 를 선택 하면 사용자의 비즈니스용 Skype 앱에서 팀으로 업그레이드 하는 알림을 사용할 수 있는 옵션이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f53e-139">If you select any **Coexistence mode** other than **Use Org-wide settings**, you have the option to enable notifications in the user's Skype for Business app that upgrade to Teams is coming soon.</span></span> <span data-ttu-id="0f53e-140">**비즈니스용 Skype 사용자에 게 알림** 옵션을 설정 하 여 사용자에 대해이 알림을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f53e-140">You can enable this notification for the user by turning on the **Notify the Skype for Business user** option.</span></span>
5. <span data-ttu-id="0f53e-141">변경한 후 **저장** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f53e-141">Click **Save** after you make your changes.</span></span>

### <a name="related-topics"></a><span data-ttu-id="0f53e-142">관련 항목</span><span class="sxs-lookup"><span data-stu-id="0f53e-142">Related topics</span></span>
[<span data-ttu-id="0f53e-143">여행 계획</span><span class="sxs-lookup"><span data-stu-id="0f53e-143">Plan the journey</span></span>](upgrade-plan-journey.md)

[<span data-ttu-id="0f53e-144">비즈니스용 Skype 및 팀에 대 한 공존 및 업그레이드 여행 이해</span><span class="sxs-lookup"><span data-stu-id="0f53e-144">Understand the coexistence and upgrade journey for Skype for Business and Teams</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[<span data-ttu-id="0f53e-145">비즈니스용 Skype로 팀을 함께 사용 하는 조직에 대 한 마이그레이션 및 상호 운용성 지침</span><span class="sxs-lookup"><span data-stu-id="0f53e-145">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md)
