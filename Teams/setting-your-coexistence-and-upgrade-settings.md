---
title: 공존 및 업그레이드 설정 지정
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: bjwhalen
search.appverid: MET150
description: 조직의 모든 사용자 또는 조직의 단일 또는 사용자 집합에 대해 동시에 공존 및 업그레이드 설정을 설정하는 방법에 대해 자세히 배워야 합니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: a20e8c355df4103980dc9da460d003382c721800
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940608"
---
# <a name="set-your-coexistence-and-upgrade-settings"></a><span data-ttu-id="f633a-103">공존 및 업그레이드 설정 지정</span><span class="sxs-lookup"><span data-stu-id="f633a-103">Set your coexistence and upgrade settings</span></span>


<span data-ttu-id="f633a-104">Teams를 사용하기 위해 비즈니스용 Skype 사용자를 업그레이드할 때 사용자에게 원활한 프로세스를 만드는 데 도움이 되는 몇 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f633a-104">When you upgrade your Skype for Business users to use Teams, you have several options to help you make it a seamless process for your users.</span></span> <span data-ttu-id="f633a-105">조직의 모든 사용자에 대해 동시에 공존 및 업그레이드 설정을 만들거나 조직의 단일 또는 사용자 집합에 대한 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f633a-105">You have the option to make coexistence and upgrade settings for all of the users in your organization at once, or you can make settings changes for a single or set of users in your organization.</span></span> <span data-ttu-id="f633a-106">이전 버전의 비즈니스용 Skype 클라이언트는 이러한 설정을 적용하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f633a-106">Note that older versions of Skype for Business clients may not honor these settings.</span></span> <span data-ttu-id="f633a-107">비즈니스용 Skype 클라이언트 버전에 대한 자세한 내용은 비즈니스용 Skype 다운로드 및 업데이트 [페이지로 이동하세요.](https://docs.microsoft.com/skypeforbusiness/software-updates)</span><span class="sxs-lookup"><span data-stu-id="f633a-107">For more information about Skype for Business client versions, go to the [Skype for Business downloads and updates page](https://docs.microsoft.com/skypeforbusiness/software-updates).</span></span> 

<span data-ttu-id="f633a-108">비즈니스용 Skype와의 Microsoft Teams 및 [비즈니스용 Skype](teams-and-skypeforbusiness-coexistence-and-interoperability.md) 공존 및 상호 연동성 또는 공존 이해를 읽어 사용할 수 있는 모드를 더 잘 이해할 [수 있습니다.](coexistence-chat-calls-presence.md)</span><span class="sxs-lookup"><span data-stu-id="f633a-108">You can get a better understanding of the modes that are available to you by reading [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md) or [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>  

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]


## <a name="set-upgrade-options-for-all-users-in-your-organization"></a><span data-ttu-id="f633a-109">조직의 모든 사용자에 대한 업그레이드 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="f633a-109">Set upgrade options for all users in your organization</span></span>

<span data-ttu-id="f633a-110">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="f633a-110">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="f633a-111">Microsoft [Teams 관리 센터의](https://admin.teams.microsoft.com/)왼쪽 탐색 모음에서 Teams 업그레이드의 **전체**  >  **설정으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="f633a-111">In the [Microsoft Teams admin center](https://admin.teams.microsoft.com/), in the left navigation, go to **Org-wide settings** > **Teams upgrade**.</span></span> 

2. <span data-ttu-id="f633a-112">Teams 업그레이드 페이지의 맨 **위에** 있는 다음 옵션을 원하는 경우 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="f633a-112">At the top of the **Teams upgrade** page, modify the following options as desired.</span></span>
    - <span data-ttu-id="f633a-113">공존 **모드를** 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f633a-113">Set the **Coexistence** mode.</span></span>
        - <span data-ttu-id="f633a-114">**제도** - 사용자가 비즈니스용 Skype와 Teams를 동시에 사용할 수 있도록 하려는 경우 이 설정을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f633a-114">**Islands** - Use this setting if you want users to be able to use both Skype for Business and Teams simultaneously.</span></span>
        - <span data-ttu-id="f633a-115">**비즈니스용 Skype만** - 사용자가 비즈니스용 Skype만 사용하게 하려는 경우 이 설정을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f633a-115">**Skype for Business only** - Use this setting if you want your users to only use Skype for Business.</span></span>
        - <span data-ttu-id="f633a-116">**Teams** 공동 작업을 사용하는 비즈니스용 Skype - 사용자가 그룹 공동 작업(채널)에 Teams를 사용할 뿐만 아니라 비즈니스용 Skype를 사용하게 하려는 경우 이 설정을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f633a-116">**Skype for Business with Teams collaboration** - Use this setting if you want your users to use Skype for Business in addition to using Teams for group collaboration (channels).</span></span>
        - <span data-ttu-id="f633a-117">**Teams** 공동 작업 및 모임이 있는 비즈니스용 Skype - 사용자가 그룹 공동 작업(채널) 및 Teams 모임에 Teams를 사용할 뿐만 아니라 비즈니스용 Skype를 사용하게 하려는 경우 이 설정을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f633a-117">**Skype for Business with Teams collaboration and meetings** - Use this setting if you want your users to use Skype for Business in addition to using Teams for group collaboration (channels) and Teams meetings.</span></span>
        - <span data-ttu-id="f633a-118">**Teams만** - 사용자가 Teams만 사용하게 하려는 경우 이 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f633a-118">**Teams only** - Use this setting if you want your users to use only Teams.</span></span> <span data-ttu-id="f633a-119">이 설정에서도 사용자는 비즈니스용 Skype에서 호스트된 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f633a-119">Note that even with this setting, users can still join meetings hosted in Skype for Business.</span></span>
        
    - <span data-ttu-id="f633a-120">Teams를 업그레이드할 수 있도록 **비즈니스용 Skype 사용자에게 알림으로 설정하세요.**</span><span class="sxs-lookup"><span data-stu-id="f633a-120">Set **Notify Skype for Business users that Teams is available for upgrade**.</span></span> <span data-ttu-id="f633a-121">이 기능을 설정하면 비즈니스용 Skype 사용자에게 곧 Teams 앱으로 업그레이드될 것 을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f633a-121">If you turn this on, it will tell the Skype for Business users that they will soon be upgraded to the Teams app.</span></span>
    - <span data-ttu-id="f633a-122">사용자가 **비즈니스용 Skype 모임에 참가할 수 있도록 기본 설정 앱을 설정하세요.**</span><span class="sxs-lookup"><span data-stu-id="f633a-122">Set the **Preferred app for users to join Skype for Business meetings**.</span></span> <span data-ttu-id="f633a-123">이 설정은 비즈니스용 Skype 모임에 참가하는 데 사용되는 앱을 결정하며 공존 모드의 값에 관계없이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f633a-123">This setting determines which app is used for joining Skype for Business meetings and is honored regardless of the value of coexistence mode.</span></span>
      - <span data-ttu-id="f633a-124">**Skype 모임 앱**</span><span class="sxs-lookup"><span data-stu-id="f633a-124">**Skype Meetings app**</span></span>
      - <span data-ttu-id="f633a-125">**제한된 기능이 있는 비즈니스용 Skype**</span><span class="sxs-lookup"><span data-stu-id="f633a-125">**Skype for Business with limited features**</span></span>
    - <span data-ttu-id="f633a-126">비즈니스용 Skype 사용자의 백그라운드에서 Teams 앱을 **다운로드할지 여부를 설정하세요.**</span><span class="sxs-lookup"><span data-stu-id="f633a-126">Set whether to **Download the Teams app in the background for Skype for Business users**.</span></span>  <span data-ttu-id="f633a-127">이 설정은 Windows에서 비즈니스용 Skype를 실행하는 사용자를 위한 Teams 앱을 자동으로 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="f633a-127">This setting silently downloads the Teams app for users running Skype for Business on Windows.</span></span> <span data-ttu-id="f633a-128">사용자의 공존 모드가 Teams 전용인 경우 또는 비즈니스용 Skype에서 보류 중인 업그레이드 알림을 사용하도록 설정한 경우 이 모드가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f633a-128">It is honored only if coexistence mode for the user is Teams only or if notifications of pending upgrade are enabled in Skype for Business.</span></span>
3. <span data-ttu-id="f633a-129">변경한 **후** 저장을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f633a-129">Click **Save** after you make your changes.</span></span>

## <a name="set-upgrade-options-for-a-single-user-in-your-organization"></a><span data-ttu-id="f633a-130">조직의 단일 사용자에 대한 업그레이드 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="f633a-130">Set upgrade options for a single user in your organization</span></span>

<span data-ttu-id="f633a-131">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png) **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="f633a-131">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="f633a-132">왼쪽 탐색에서 사용자로 이동한 다음 **목록에서** 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f633a-132">In the left navigation, go to **Users**, and then select the user from the list.</span></span> 
2. <span data-ttu-id="f633a-133">사용자의 **계정** 탭의 Teams **업그레이드 아래에서** 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f633a-133">On the **Account** tab for the user, under **Teams upgrade**, click **Edit**.</span></span>
3. <span data-ttu-id="f633a-134">공존 모드를 **설정할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="f633a-134">You can set the **Coexistence mode**.</span></span> <span data-ttu-id="f633a-135">다음 옵션에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f633a-135">Choose from the following options:</span></span>
     - <span data-ttu-id="f633a-136">**전체 설정** 사용 - 사용자가 전체 설정에서 설정을 사용하려면 이 설정을 **사용합니다.**</span><span class="sxs-lookup"><span data-stu-id="f633a-136">**Use Org-wide settings** - Use this setting if you want the user to use the settings in the **Org-wide** settings.</span></span> 
     - <span data-ttu-id="f633a-137">**제도** - 사용자가 비즈니스용 Skype와 Teams를 모두 사용할 수 있도록 하려는 경우 이 설정을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f633a-137">**Islands** - Use this setting if you want the user to be able to use both Skype for Business and Teams.</span></span> 
     - <span data-ttu-id="f633a-138">**비즈니스용 Skype만** - 사용자가 비즈니스용 Skype를 사용하게 하려는 경우 이 설정을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f633a-138">**Skype for Business only** - Use this setting if you want the user to use Skype for Business.</span></span>
     - <span data-ttu-id="f633a-139">**Teams** 공동 작업을 사용하는 비즈니스용 Skype - 사용자가 그룹 공동 작업(채널)에 Teams를 사용할 뿐만 아니라 비즈니스용 Skype를 사용하게 하려는 경우 이 설정을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f633a-139">**Skype for Business with Teams collaboration** - Use this setting if you want the user to use Skype for Business in addition to using Teams for group collaboration (channels).</span></span>
      - <span data-ttu-id="f633a-140">**Teams** 공동 작업 및 모임이 있는 비즈니스용 Skype - 사용자가 그룹 공동 작업(채널) 및 Teams 모임에 Teams를 사용할 뿐만 아니라 비즈니스용 Skype를 사용하게 하려는 경우 이 설정을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f633a-140">**Skype for Business with Teams collaboration and meetings** - Use this setting if you want the user to use Skype for Business in addition to using Teams for group collaboration (channels) and Teams meetings.</span></span>
     - <span data-ttu-id="f633a-141">**Teams만** - 사용자가 Teams만 사용하게 하려는 경우 이 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f633a-141">**Teams only** - Use this setting if you want the user to use only Teams.</span></span> <span data-ttu-id="f633a-142">사용자는 여전히 비즈니스용 Skype 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f633a-142">The user will still be able to join Skype for Business meetings.</span></span>
4. <span data-ttu-id="f633a-143">전체 설정  사용 외의 공존 모드를 선택하는 경우 사용자의 비즈니스용 Skype 앱에서 Teams로 업그레이드하는 알림을 사용할 수 있는 옵션이 곧 제공될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="f633a-143">If you select any **Coexistence mode** other than **Use Org-wide settings**, you have the option to enable notifications in the user's Skype for Business app that upgrade to Teams is coming soon.</span></span> <span data-ttu-id="f633a-144">비즈니스용 Skype 사용자 알림 옵션을 설정하여 사용자에 대해 이 알림을 사용하도록 **설정할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f633a-144">You can enable this notification for the user by turning on the **Notify the Skype for Business user** option.</span></span>
5. <span data-ttu-id="f633a-145">변경한 **후** 저장을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f633a-145">Click **Save** after you make your changes.</span></span>

### <a name="related-topics"></a><span data-ttu-id="f633a-146">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f633a-146">Related topics</span></span>
[<span data-ttu-id="f633a-147">IT 관리자를 위해 비즈니스용 Skype에서 Teams로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="f633a-147">Upgrade from Skype for Business to Teams — for IT administrators</span></span>](upgrade-to-teams-on-prem-overview.md)

[<span data-ttu-id="f633a-148">여정 계획</span><span class="sxs-lookup"><span data-stu-id="f633a-148">Plan the journey</span></span>](upgrade-plan-journey.md)

[<span data-ttu-id="f633a-149">비즈니스용 Skype 및 Teams의 공존 및 업그레이드 여정 이해</span><span class="sxs-lookup"><span data-stu-id="f633a-149">Understand the coexistence and upgrade journey for Skype for Business and Teams</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

[<span data-ttu-id="f633a-150">비즈니스용 Skype와 함께 Teams를 사용하는 조직을 위한 마이그레이션 및 상호 연동성 지침</span><span class="sxs-lookup"><span data-stu-id="f633a-150">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md)
