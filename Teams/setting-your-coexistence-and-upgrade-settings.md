---
title: 공존 및 업그레이드 설정 지정
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: 조직의 모든 사용자 또는 조직의 단일 또는 집합 사용자에 대해 한 번씩 공존 및 업그레이드 설정을 설정하는 방법에 대해 자세히 알아보습니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e7559b5376f6b386132e7814b88b6fcce3f5b378
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282725"
---
# <a name="set-your-coexistence-and-upgrade-settings"></a><span data-ttu-id="852a3-103">공존 및 업그레이드 설정 지정</span><span class="sxs-lookup"><span data-stu-id="852a3-103">Set your coexistence and upgrade settings</span></span>


<span data-ttu-id="852a3-104">사용자 비즈니스용 Skype 업그레이드하여 Teams 원활한 프로세스를 만드는 데 도움이 되는 몇 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="852a3-104">When you upgrade your Skype for Business users to use Teams, you have several options to help you make it a seamless process for your users.</span></span> <span data-ttu-id="852a3-105">조직의 모든 사용자에 대해 동시에 공존 및 업그레이드 설정을 만들거나 조직의 단일 사용자 또는 집합에 대한 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="852a3-105">You have the option to make coexistence and upgrade settings for all of the users in your organization at once, or you can make settings changes for a single or set of users in your organization.</span></span> <span data-ttu-id="852a3-106">이전 버전의 비즈니스용 Skype 이러한 설정을 적용하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="852a3-106">Note that older versions of Skype for Business clients may not honor these settings.</span></span> <span data-ttu-id="852a3-107">클라이언트 버전에 대한 비즈니스용 Skype 자세한 내용은 다운로드 및 업데이트 비즈니스용 Skype [페이지로 이동합니다.](/skypeforbusiness/software-updates)</span><span class="sxs-lookup"><span data-stu-id="852a3-107">For more information about Skype for Business client versions, go to the [Skype for Business downloads and updates page](/skypeforbusiness/software-updates).</span></span> 

<span data-ttu-id="852a3-108">사용 가능한 모드에 대한 이해 및 Microsoft Teams 및 [](teams-and-skypeforbusiness-coexistence-and-interoperability.md) 상호 비즈니스용 Skype 및 공존성을 읽은 후 사용할 수 [비즈니스용 Skype.](coexistence-chat-calls-presence.md)</span><span class="sxs-lookup"><span data-stu-id="852a3-108">You can get a better understanding of the modes that are available to you by reading [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md) or [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a><span data-ttu-id="852a3-109">조직의 모든 사용자에 대한 업그레이드 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="852a3-109">Set upgrade options for all users in your organization</span></span>

<span data-ttu-id="852a3-110">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="852a3-110">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="852a3-111">Microsoft Teams [](https://admin.teams.microsoft.com/)관리 센터의 왼쪽 탐색에서 업그레이드 에서 **org-wide**  >  **설정으로 Teams 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="852a3-111">In the [Microsoft Teams admin center](https://admin.teams.microsoft.com/), in the left navigation, go to **Org-wide settings** > **Teams upgrade**.</span></span> 

2. <span data-ttu-id="852a3-112">업그레이드 페이지 **맨 Teams** 원하는 경우 다음 옵션을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="852a3-112">At the top of the **Teams upgrade** page, modify the following options as desired.</span></span>
    - <span data-ttu-id="852a3-113">공존 **모드를 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="852a3-113">Set the **Coexistence** mode.</span></span>
        - <span data-ttu-id="852a3-114">**섬** - 사용자가 이 설정을 사용하여 사용자와 사용자 비즈니스용 Skype 동시에 Teams 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="852a3-114">**Islands** - Use this setting if you want users to be able to use both Skype for Business and Teams simultaneously.</span></span>
        - <span data-ttu-id="852a3-115">**비즈니스용 Skype -** 사용자만 사용하려는 경우 이 설정을 비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="852a3-115">**Skype for Business only** - Use this setting if you want your users to only use Skype for Business.</span></span>
        - <span data-ttu-id="852a3-116">**비즈니스용 Skype 공동 작업과 Teams** - 사용자가 그룹 공동 작업(채널)에 비즈니스용 Skype 사용할 Teams 이 설정을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="852a3-116">**Skype for Business with Teams collaboration** - Use this setting if you want your users to use Skype for Business in addition to using Teams for group collaboration (channels).</span></span>
        - <span data-ttu-id="852a3-117">**비즈니스용 Skype** 공동 작업 및 Teams 사용 - 사용자가 그룹 공동 작업(채널) 및 비즈니스용 Skype 모임에 Teams 사용하려는 경우 이 Teams 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="852a3-117">**Skype for Business with Teams collaboration and meetings** - Use this setting if you want your users to use Skype for Business in addition to using Teams for group collaboration (channels) and Teams meetings.</span></span>
        - <span data-ttu-id="852a3-118">**Teams -** 사용자만 사용하려는 경우 이 설정을 Teams.</span><span class="sxs-lookup"><span data-stu-id="852a3-118">**Teams only** - Use this setting if you want your users to use only Teams.</span></span> <span data-ttu-id="852a3-119">이 설정이라도 사용자는 여전히 이 설정에서 호스트된 모임에 참가할 비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="852a3-119">Note that even with this setting, users can still join meetings hosted in Skype for Business.</span></span>
        
    - <span data-ttu-id="852a3-120">업그레이드할 비즈니스용 Skype 사용할 수 Teams **사용자에게 알리기 를 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="852a3-120">Set **Notify Skype for Business users that Teams is available for upgrade**.</span></span> <span data-ttu-id="852a3-121">이 기능을 설정하면 사용자에게 비즈니스용 Skype 앱으로 곧 업그레이드될 Teams 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="852a3-121">If you turn this on, it will tell the Skype for Business users that they will soon be upgraded to the Teams app.</span></span>
    - <span data-ttu-id="852a3-122">사용자가 모임에 참가할 수 있도록 기본 **비즈니스용 Skype 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="852a3-122">Set the **Preferred app for users to join Skype for Business meetings**.</span></span> <span data-ttu-id="852a3-123">이 설정은 모임에 참가하는 데 비즈니스용 Skype 결정하며 공존 모드의 값에 관계없이 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="852a3-123">This setting determines which app is used for joining Skype for Business meetings and is honored regardless of the value of coexistence mode.</span></span>
      - <span data-ttu-id="852a3-124">**Skype 모임 앱**</span><span class="sxs-lookup"><span data-stu-id="852a3-124">**Skype Meetings app**</span></span>
      - <span data-ttu-id="852a3-125">**비즈니스용 Skype 기능이 있는 기능**</span><span class="sxs-lookup"><span data-stu-id="852a3-125">**Skype for Business with limited features**</span></span>
    - <span data-ttu-id="852a3-126">사용자에 대한 백그라운드에서 Teams 앱을 **다운로드할지** 여부를 비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="852a3-126">Set whether to **Download the Teams app in the background for Skype for Business users**.</span></span>  <span data-ttu-id="852a3-127">이 설정은 Teams 실행 중인 사용자에 대한 비즈니스용 Skype 앱을 Windows.</span><span class="sxs-lookup"><span data-stu-id="852a3-127">This setting silently downloads the Teams app for users running Skype for Business on Windows.</span></span> <span data-ttu-id="852a3-128">사용자에 대한 공존 모드가 Teams 보류 중인 업그레이드 알림을 사용할 수 있는 비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="852a3-128">It is honored only if coexistence mode for the user is Teams only or if notifications of pending upgrade are enabled in Skype for Business.</span></span>
3. <span data-ttu-id="852a3-129">**변경한** 후 저장을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="852a3-129">Click **Save** after you make your changes.</span></span>

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a><span data-ttu-id="852a3-130">조직의 단일 사용자에 대한 업그레이드 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="852a3-130">Set upgrade options for a single user in your organization</span></span>

<span data-ttu-id="852a3-131">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="852a3-131">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="852a3-132">왼쪽 탐색에서 **사용자로** 이동한 다음 목록에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="852a3-132">In the left navigation, go to **Users**, and then select the user from the list.</span></span> 
2. <span data-ttu-id="852a3-133">사용자의 **계정** 탭에서 업그레이드 Teams **을** **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="852a3-133">On the **Account** tab for the user, under **Teams upgrade**, click **Edit**.</span></span>
3. <span data-ttu-id="852a3-134">공존 모드를 **설정할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="852a3-134">You can set the **Coexistence mode**.</span></span> <span data-ttu-id="852a3-135">다음 옵션에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="852a3-135">Choose from the following options:</span></span>
     - <span data-ttu-id="852a3-136">**Org-wide 설정** 사용 - 사용자가 **Org-wide** 설정에서 설정을 사용하려면 이 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="852a3-136">**Use Org-wide settings** - Use this setting if you want the user to use the settings in the **Org-wide** settings.</span></span> 
     - <span data-ttu-id="852a3-137">**섬** - 사용자가 이 설정과 비즈니스용 Skype 사용할 수 Teams.</span><span class="sxs-lookup"><span data-stu-id="852a3-137">**Islands** - Use this setting if you want the user to be able to use both Skype for Business and Teams.</span></span> 
     - <span data-ttu-id="852a3-138">**비즈니스용 Skype 전용** - 사용자가 이 설정을 사용하려는 경우 이 설정을 비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="852a3-138">**Skype for Business only** - Use this setting if you want the user to use Skype for Business.</span></span>
     - <span data-ttu-id="852a3-139">**비즈니스용 Skype 공동 작업과 Teams** - 사용자가 그룹 공동 작업(채널)에 비즈니스용 Skype 사용하려는 Teams 설정을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="852a3-139">**Skype for Business with Teams collaboration** - Use this setting if you want the user to use Skype for Business in addition to using Teams for group collaboration (channels).</span></span>
      - <span data-ttu-id="852a3-140">**비즈니스용 Skype** 공동 작업 및 Teams 사용 - 사용자가 그룹 공동 작업(채널) 및 모임에 Teams 추가 비즈니스용 Skype 경우 이 Teams 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="852a3-140">**Skype for Business with Teams collaboration and meetings** - Use this setting if you want the user to use Skype for Business in addition to using Teams for group collaboration (channels) and Teams meetings.</span></span>
     - <span data-ttu-id="852a3-141">**Teams 전용** - 사용자가 사용자만 사용하려는 경우 이 설정을 Teams.</span><span class="sxs-lookup"><span data-stu-id="852a3-141">**Teams only** - Use this setting if you want the user to use only Teams.</span></span> <span data-ttu-id="852a3-142">사용자는 여전히 모임에 참가할 비즈니스용 Skype 있습니다.</span><span class="sxs-lookup"><span data-stu-id="852a3-142">The user will still be able to join Skype for Business meetings.</span></span>
4. <span data-ttu-id="852a3-143">**Org-wide** 설정 사용 외의 공존 모드를 선택하는 경우 사용자 비즈니스용 Skype 앱에 알림을 사용하도록 설정하는 옵션이 Teams 있습니다. </span><span class="sxs-lookup"><span data-stu-id="852a3-143">If you select any **Coexistence mode** other than **Use Org-wide settings**, you have the option to enable notifications in the user's Skype for Business app that upgrade to Teams is coming soon.</span></span> <span data-ttu-id="852a3-144">사용자 알림 옵션을 설정하여 이 비즈니스용 Skype **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="852a3-144">You can enable this notification for the user by turning on the **Notify the Skype for Business user** option.</span></span>
5. <span data-ttu-id="852a3-145">**변경한** 후 저장을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="852a3-145">Click **Save** after you make your changes.</span></span>

### <a name="related-topics"></a><span data-ttu-id="852a3-146">관련 주제</span><span class="sxs-lookup"><span data-stu-id="852a3-146">Related topics</span></span>
[<span data-ttu-id="852a3-147">여정 계획</span><span class="sxs-lookup"><span data-stu-id="852a3-147">Plan the journey</span></span>](upgrade-plan-journey.md)

[<span data-ttu-id="852a3-148">프로세스 및 업그레이드에 대한 공존 및 업그레이드 비즈니스용 Skype Teams</span><span class="sxs-lookup"><span data-stu-id="852a3-148">Understand the coexistence and upgrade journey for Skype for Business and Teams</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[<span data-ttu-id="852a3-149">조직과 함께 Teams 조직에 대한 마이그레이션 및 상호 비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="852a3-149">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md)