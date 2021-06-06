---
title: 외부 액세스 관리(페더레이션)
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.externalaccess.overview
- seo-marvel-mar2020
description: 팀 또는 IT 관리자가 다른 도메인(페더레이션)의 사용자가 Teams에 참여할 수 있도록 해당 도메인에 대한 외부 액세스를 구성할 수 있습니다.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 5f472ef2a009a3a0b9b87222d951ef34b65da15a
ms.sourcegitcommit: f5b6a0fe055e42e06eee21ce311813b5127474ea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2021
ms.locfileid: "52741077"
---
# <a name="manage-external-access-in-microsoft-teams"></a><span data-ttu-id="d82ca-103">Microsoft Teams에서 외부 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="d82ca-103">Manage external access in Microsoft Teams</span></span>

<span data-ttu-id="d82ca-104">외부 액세스는 전체 외부 도메인의 Teams 사용자가 Teams에서 검색, 통화, 채팅 및 사용자와의 모임을 설정할 수 있는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-104">External access is a way for Teams users from an entire external domain to find, call, chat, and set up meetings with you in Teams.</span></span> <span data-ttu-id="d82ca-105">외부 액세스를 사용하여 비즈니스용 Skype(온라인 및 온-프레미스) 및 Skype (미리 보기)를 계속 사용하는 다른 조직의 사용자와 통신할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-105">You can also use external access to communicate with people from other organizations who are still using Skype for Business (online and on-premises) and Skype (in preview).</span></span>

<span data-ttu-id="d82ca-106">다른 조직의 사용자가 팀과 채널에 액세스할 수 있도록 하려면 게스트 액세스를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-106">If you want people from other organizations to have access to teams and channels, guest access might be a better way to go.</span></span> <span data-ttu-id="d82ca-107">외부 액세스와 게스트 액세스 사이의 차이점에 대한 자세한 내용은 [외부 및 게스트 액세스 비교](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d82ca-107">For more information about the differences between external access and guest access, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span> 

<span data-ttu-id="d82ca-108">다음과 같은 경우에 외부 액세스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-108">Use external access when:</span></span>
  
- <span data-ttu-id="d82ca-p103">서로 다른 도메인에 공동 작업해야 하는 사용자가 있습니다. 예를 들어 Rob@contoso.com 및 Ann@northwindtraders.com은 contoso.com 및 northwindtraders.com 도메인의 다른 사용자들과 함께 프로젝트를 작업하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-p103">You have users in different domains who need to collaborate. For example, Rob@contoso.com and Ann@northwindtraders.com are working on a project together along with some others in the contoso.com and northwindtraders.com domains.</span></span>

- <span data-ttu-id="d82ca-111">조직 내 사용자가 Teams를 사용하여 조직 외부의 특정 비즈니스에 참여하는 사용자와 연락하도록 하려는 경우</span><span class="sxs-lookup"><span data-stu-id="d82ca-111">You want the people in your organization to use Teams to contact people in specific businesses outside of your organization.</span></span>

- <span data-ttu-id="d82ca-112">Teams를 사용하는 전 세계의 모든 사람이 전자 메일 주소를 사용하여 사용자를 찾고 연락할 수 있게 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-112">You want anyone else in the world who uses Teams to be able to find and contact you, using your email address.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="d82ca-113">Teams 클라이언트를 사용하여 외부 사용자와 통신하려면(사용자가 Teams를 사용 중이든 비즈니스용 Skype를 사용 중이든 상관 없음) Teams 사용자는 비즈니스용 Skype Online에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-113">To use the Teams client to communicate with an external user (whether that user is using Teams or Skype for Business), the Teams user must be homed in Skype for Business Online.</span></span>

## <a name="plan-for-external-access"></a><span data-ttu-id="d82ca-114">외부 액세스 계획</span><span class="sxs-lookup"><span data-stu-id="d82ca-114">Plan for external access</span></span>

<span data-ttu-id="d82ca-115">기본적으로 외부 액세스는 Teams에서 활성화되어 있습니다. 즉, 조직에서 모든 외부 도메인과 의사소통할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-115">By default, external access is turned on in Teams, which means that your organization can communicate with all external domains.</span></span> <span data-ttu-id="d82ca-116">차단된 도메인을 추가하면 다른 모든 도메인이 허용됩니다. 허용된 도메인을 추가하면 다른 모든 도메인이 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-116">If you add blocked domains, all other domains will be allowed; and if you add allowed domains, all other domains will be blocked.</span></span> <span data-ttu-id="d82ca-117">이 규칙의 예외는 익명 참가자가 모임에서 허용되는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-117">The exception to this rule is if anonymous participants are allowed in meetings.</span></span> <span data-ttu-id="d82ca-118">Teams 관리 센터에서 외부 액세스를 설정하는 세 가지 시나리오가 있습니다(**조직 전체 설정** > **외부 액세스**).</span><span class="sxs-lookup"><span data-stu-id="d82ca-118">There are three scenarios for setting up external access in the Teams admin center (**Org-wide settings** > **External access**):</span></span>

> [!NOTE]
> <span data-ttu-id="d82ca-119">Teams 사용자는 다른 조직의 사용자와 모임 또는 채팅을 호스트할 때 앱을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-119">Teams users can add apps when they host meetings or chats with people from other organizations.</span></span> <span data-ttu-id="d82ca-120">또한 해당 조직에서 호스트하는 모임 또는 채팅에 참가할 때 다른 조직의 사용자가 공유하는 앱을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-120">They can also use apps shared by people in other organizations when they join meetings or chats hosted by those organizations.</span></span> <span data-ttu-id="d82ca-121">호스팅 사용자 조직의 데이터 정책과 해당 사용자 조직에서 공유하는 타사 앱의 데이터 공유 사례가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-121">The data policies of the hosting user's organization, as well as the data sharing practices of any third-party apps shared by that user's organization, are applied.</span></span>

> [!NOTE]
> <span data-ttu-id="d82ca-122">조직에서 외부 액세스를 해제하는 경우 외부 사용자는 여전히 익명 참가를 통해 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-122">If you turn off external access in your organization, external users can still join meetings through anonymous join.</span></span> <span data-ttu-id="d82ca-123">자세한 내용은 [Teams에서 모임 정책 관리](./meeting-settings-in-teams.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d82ca-123">To learn more, see [Manage meeting settings in Teams](./meeting-settings-in-teams.md).</span></span>

- <span data-ttu-id="d82ca-124">**열려 있는 페더레이션**: 이는 Teams의 기본 설정이며, 조직의 사용자가 조직 외부의 사용자를 찾아서 통화하고, IM/채팅을 전송하고, 모임을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-124">**Open federation**: This is the default setting in Teams, and it lets people in your organization find, call, chat, and set up meetings with people external to your organization in any domain.</span></span>

    <span data-ttu-id="d82ca-125">이 시나리오에서는 사용자가 Temas 또는 비즈니스용 Skype를 실행하고 열려 있는 페더레이션을 사용하거나 내 도메인을 허용 목록에 추가한 모든 외부 도메인과 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-125">In this scenario, your users can communicate with all external domains that are running Teams or Skype for Business AND are using open federation OR have added your domain to their allow list.</span></span>

- <span data-ttu-id="d82ca-126">**특정 도메인 허용**: **허용** 목록에 도메인을 추가하여 외부 액세스를 허용된 도메인만으로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-126">**Allow specific domains**: By adding domains to an **Allow** list, you limit external access to only the allowed domains.</span></span> <span data-ttu-id="d82ca-127">허용된 도메인 목록을 설정하면 다른 모든 도메인은 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-127">Once you set up a list of allowed domains, all other domains will be blocked.</span></span> <span data-ttu-id="d82ca-128">특정 도메인을 허용하려면 **도메인 추가** 를 클릭하고 도메인 이름을 추가하고 **이 도메인에서 수행할 작업** 을 클릭한 다음 **허용됨** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-128">To allow specific domains, click **Add a domain**, add the domain name, click **Action to take on this domain**, and then select **Allowed**.</span></span>

- <span data-ttu-id="d82ca-129">**특정 도메인 차단** - **차단** 목록에 도메인을 추가하여 차단한 도메인을 *제외* 한 모든 외부 도메인과 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-129">**Block specific domains** - By adding domains to a **Block** list, you can communicate with all external domains *except* the ones you've blocked.</span></span> <span data-ttu-id="d82ca-130">특정 도메인을 차단하려면 **도메인 추가** 를 클릭하고 도메인 이름을 추가하고 **이 도메인에서 수행할 작업** 을 클릭한 다음 **차단됨** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-130">To block specific domains, click **Add a domain**, add the domain name, click **Action to take on this domain**, and then select **Blocked**.</span></span> <span data-ttu-id="d82ca-131">차단된 도메인 목록을 설정하면 다른 모든 도메인은 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-131">Once you set up a list of blocked domains, all other domains will be allowed.</span></span>

> [!NOTE]
> <span data-ttu-id="d82ca-132">허용된 도메인 또는 차단된 도메인은 모임에 대한 익명 액세스가 "꺼진" 경우 모임에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-132">The allowed or blocked domains only apply to meetings if anonymous access to meetings is "off".</span></span>

## <a name="allow-or-block-domains"></a><span data-ttu-id="d82ca-133">도메인 허용 또는 차단</span><span class="sxs-lookup"><span data-stu-id="d82ca-133">Allow or block domains</span></span>

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-or-skype-for-business-organizations"></a><span data-ttu-id="d82ca-134">1단계 - 조직이 다른 Teams 또는 비즈니스용 Skype 조직과 통신할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="d82ca-134">Step 1 - Enable your organization to communicate with another Teams or Skype for Business organizations</span></span>

<span data-ttu-id="d82ca-135">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png)  **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="d82ca-135">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png)  **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="d82ca-136">왼쪽 탐색에서 **조직 전체 설정** > **외부 액세스** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-136">In the left navigation, go to **Org-wide settings** > **External access**.</span></span>

2. <span data-ttu-id="d82ca-137">**사용자가 다른 비즈니스용 Skype 및 Teams 사용자의 통신할 수 있음** 설정을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-137">Turn on the **Users can communicate with other Skype for Business and Teams users** setting.</span></span>

     ![사용자가 다른 비즈니스용 Skype 및 Teams 사용자의 통신할 수 있음 설정이 켜진 스크린샷](media/manage-external-access-2.png)<span data-ttu-id="d82ca-139">.</span><span class="sxs-lookup"><span data-stu-id="d82ca-139">.</span></span>

3. <span data-ttu-id="d82ca-140">모든 Teams 조직이 조직의 사용자와 통신하도록하려면 5단계로 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-140">If you want to allow all Teams organizations to communicate with users in your organization, skip to step 5.</span></span>

4. <span data-ttu-id="d82ca-141">조직의 사용자와 통신할 수 있는 조직을 제한하려면 일부 도메인을 제외한 모든 도메인을 허용하거나 특정 도메인만 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-141">If you want to limit the organizations that can communicate with users in your organization, you can either allow all except some domains, or you can allow only specific domains.</span></span> 

    - <span data-ttu-id="d82ca-142">일부 도메인을 제외한 모든 도메인을 허용하려면 **도메인 추가** 를 클릭하여 차단할 도메인을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-142">To allow all except some domains, add the domains you want to block by clicking **Add domain**.</span></span> <span data-ttu-id="d82ca-143">**도메인 추가** 창에서 도메인 이름을 입력하고 **차단됨** 을 클릭한 다음 **완료** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-143">In the **Add a domain** pane, type the domain name, click **Blocked**, and then click **Done**.</span></span> 
    - <span data-ttu-id="d82ca-144">특정 조직에 대한 통신을 제한하려면 해당 도메인을 **허용됨** 상태인 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-144">To limit communications to specific organizations, add those domains to the list with a status of **Allowed**.</span></span> <span data-ttu-id="d82ca-145">도메인을 허용 목록에 추가하면 다른 조직과의 통신은 도메인이 허용 목록에 있는 조직으로만 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-145">Once you have added any domain to the Allow list, communications with other organizations will be limited to only those organizations whose domains are in the Allow list.</span></span> 

5. <span data-ttu-id="d82ca-146">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-146">Click **Save**.</span></span>

6. <span data-ttu-id="d82ca-147">다른 Teams 조직의 관리자가 동일한 단계를 완료하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-147">Make sure the admin in the other Teams organization completes these same steps.</span></span> <span data-ttu-id="d82ca-148">예를 들어 **허용된 도메인** 목록에서 관리자가 사용자와 통신할 수있는 조직을 제한하는 경우 해당 관리자가 비즈니스 도메인을 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-148">For example, in their **allowed domains** list, their admin needs to enter the domain for your business if they limit the organizations that can communicate with their users.</span></span>

### <a name="step-2---test-it"></a><span data-ttu-id="d82ca-149">2단계 - 테스트</span><span class="sxs-lookup"><span data-stu-id="d82ca-149">Step 2 - Test it</span></span>

<span data-ttu-id="d82ca-150">설정을 테스트하려면 사용자의 방화벽 외부에 있는 Teams 사용자가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-150">To test your setup, you need a Teams user who's not behind your firewall.</span></span>
  
1. <span data-ttu-id="d82ca-151">사용자와 조직의 관리자가 **외부 액세스 설정** 을 변경한 후에는 계속 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-151">After you and the admin from the organization have changed the **External access** settings, you should be good to go.</span></span>

2. <span data-ttu-id="d82ca-152">Teams 앱에서 전자 메일 주소로 사용자를 검색하고 채팅 요청을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-152">In the Teams app, search for the person by email address, and send a request to chat.</span></span>

3. <span data-ttu-id="d82ca-153">사용자의 Teams 연락처에 요청하여 사용자에게 채팅 요청을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-153">Ask your Teams contact to send you a request to chat.</span></span> <span data-ttu-id="d82ca-154">요청을 받지 못한 경우 (방화벽 설정이 올바른지 이미 확인했다고 가정한다면) 방화벽 설정에 문제가 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-154">If you don't receive their request, the problem is your firewall settings (assuming they've already confirmed their firewall settings are correct).</span></span>

4. <span data-ttu-id="d82ca-155">방화벽에 문제가 있는지 테스트하는 또 다른 방법은 방화벽 외부에 있는 WiFi 위치로 이동하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-155">Another way to test whether the problem is your firewall is to go to a WiFi location not behind your firewall.</span></span> <span data-ttu-id="d82ca-156">커피숍과 같은 위치에서 Teams를 사용하여 연락처에 채팅 요청을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-156">such as a coffee shop, and use Teams to send a request to your contact to chat.</span></span> <span data-ttu-id="d82ca-157">메시지가 WiFi 위치를 통과하지만, 회사 내부에 있을 때는 통과하지 않으면 방화벽에 문제가 있음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-157">If the message goes through at the WiFi location, but does not when you're at work, then you know the problem is your firewall.</span></span>

> [!NOTE]
> <span data-ttu-id="d82ca-158">사용자와 다른 사용자가 모두 외부 액세스를 켜고 서로의 도메인을 허용하는 경우 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-158">If you and another user both turn on external access and allow one another's domains, this will work.</span></span> <span data-ttu-id="d82ca-159">그래도 문제가 해결되지 않으면 다른 사용자가 구성에서 사용자의 도메인을 차단하고 있지 않은지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-159">If it doesn't work, the other user should make sure their configuration isn't blocking your domain.</span></span>


## <a name="communicate-with-skype-users-in-preview"></a><span data-ttu-id="d82ca-160">Skype 사용자와의 통신(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="d82ca-160">Communicate with Skype users (in preview)</span></span>

<span data-ttu-id="d82ca-161">조직의 Teams 사용자가 Skype 사용자와 채팅하고 통화하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="d82ca-161">Follow these steps to let Teams users in your organization chat with and call Skype users.</span></span> <span data-ttu-id="d82ca-162">그런 다음 Teams 사용자는 일대일 텍스트 전용 대화 또는 Skype 사용자와의 음성/화상 통화를 검색 및 시작할 수 있으며 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-162">Teams users can then search for and start a one-on-one text-only conversation or an audio/video call with Skype users and vice versa.</span></span>

<span data-ttu-id="d82ca-163">![Microsoft Teams 로고를 나타내는 아이콘](media/teams-logo-30x30.png)  **Microsoft Teams 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="d82ca-163">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png)  **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="d82ca-164">왼쪽 탐색에서 **조직 전체 설정** > **외부 액세스** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-164">In the left navigation, go to **Org-wide settings** > **External access**.</span></span>

2. <span data-ttu-id="d82ca-165">**사용자가 Skype 사용자의 통신할 수 있음** 설정을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-165">Turn on the **Users can communicate with Skype users** setting.</span></span>

    ![사용자가 Skype 사용자의 통신할 수 있음 설정이 켜진 스크린샷](media/manage-external-access-5.png)<span data-ttu-id="d82ca-167">.</span><span class="sxs-lookup"><span data-stu-id="d82ca-167">.</span></span>

<span data-ttu-id="d82ca-168">적용되는 제한 사항을 포함하여 Teams 사용자 및 Skype 사용자가 통신할 수 있는 방법에 대한 자세한 내용은 [Teams 및 Skype 상호 운용성](teams-skype-interop.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d82ca-168">To learn more about the ways that Teams users and Skype users can communicate, including limitations that apply, see [Teams and Skype interoperability](teams-skype-interop.md).</span></span>

## <a name="common-external-access-scenarios"></a><span data-ttu-id="d82ca-169">일반적인 외부 액세스 시나리오</span><span class="sxs-lookup"><span data-stu-id="d82ca-169">Common external access scenarios</span></span>

<span data-ttu-id="d82ca-170">다음 섹션에서는 일반적인 외부 액세스 시나리오에서 페더레이션을 사용하도록 설정하는 방법과 TeamsUpgradePolicy에서 들어오는 채팅 및 통화의 전달을 결정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-170">The following sections describe how to enable federation for common external access scenarios, and how the TeamsUpgradePolicy determines delivery of incoming chats and calls.</span></span>

### <a name="enable-federation"></a><span data-ttu-id="d82ca-171">페더레이션 사용</span><span class="sxs-lookup"><span data-stu-id="d82ca-171">Enable federation</span></span>

<span data-ttu-id="d82ca-172">조직의 사용자가 다른 조직의 사용자와 통신할 수 있도록 설정하려면 두 조직 모두 페더레이션 기능을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-172">To enable users in your organization to communicate with users in another organization, both organizations must enable federation.</span></span> <span data-ttu-id="d82ca-173">특정 조직에 대해 페더레이션을 사용하도록 설정하는 단계는 조직이 온라인인지, 하이브리드인지 또는 온-프레미스인지에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-173">The steps to enable federation for a given organization depend on whether the organization is purely online, hybrid, or purely on-premises.</span></span>

| <span data-ttu-id="d82ca-174">조직에서 데스크톱 시각화에 대한</span><span class="sxs-lookup"><span data-stu-id="d82ca-174">If your organization is</span></span> | <span data-ttu-id="d82ca-175">다음과 같이 페더레이션을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="d82ca-175">Enable federation as follows</span></span> |
|:---------|:-----------------------|
|<span data-ttu-id="d82ca-176">비즈니스용 Skype 온-프레미스가 아닌 사용자.</span><span class="sxs-lookup"><span data-stu-id="d82ca-176">Online with no Skype for Business on-premises.</span></span> <span data-ttu-id="d82ca-177">여기에는 TeamsOnly 사용자 및/또는 비즈니스용 Skype Online 사용자가 있는 조직이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-177">This includes organizations that have TeamsOnly users and/or Skype for Business Online users.</span></span>| <span data-ttu-id="d82ca-178">Teams 관리 센터를 사용하는 경우:</span><span class="sxs-lookup"><span data-stu-id="d82ca-178">If using Teams Admin Center:</span></span> <br><span data-ttu-id="d82ca-179">-   외부 액세스에서 **사용자가 다른 비즈니스용 Skype 및 Teams 사용자의 통신할 수 있도록 허용** 설정을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-179">-   Make sure the **Users can communicate with other Skype for Business and Teams users** setting is enabled in External Access.</span></span><br><span data-ttu-id="d82ca-180">- 공개 페더레이션(다른 도메인과 페더레이션 연동이 허용됨)을 사용하지 않는 경우 허용된 목록에 외부 도메인을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-180">- If you are not using open federation (which allows federation with any other domain), then add the external domain to the Allowed list.</span></span><br><br><span data-ttu-id="d82ca-181">PowerShell을 사용하는 경우:</span><span class="sxs-lookup"><span data-stu-id="d82ca-181">If using PowerShell:</span></span><br><span data-ttu-id="d82ca-182">- 테넌트가 페더레이션에 대해 `Get-CsTenantFederationConfiguration`이 `AllowFederatedUsers=true`를 표시하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-182">- Ensure the tenant is enabled for federation: `Get-CsTenantFederationConfiguration` must show `AllowFederatedUsers=true`.</span></span> <br><span data-ttu-id="d82ca-183">- 사용자의 `CsExternalAccessPolicy`에 적합한 값인 `EnableFederationAccess=true`가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-183">- Ensure the user’s effective value of `CsExternalAccessPolicy` has `EnableFederationAccess=true`.</span></span><br><span data-ttu-id="d82ca-184">- 공개 페더레이션을 사용하지 않는 경우, 대상 도메인이 `CsTenantFederationConfiguration`의 `AllowedDomains`에 나열되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-184">- If you are not using open federation, ensure the target domain is listed in `AllowedDomains` of `CsTenantFederationConfiguration`.</span></span> |
|<span data-ttu-id="d82ca-185">온-프레미스에서만</span><span class="sxs-lookup"><span data-stu-id="d82ca-185">Pure on-premises</span></span> | <span data-ttu-id="d82ca-186">온-프레미스 도구에서:</span><span class="sxs-lookup"><span data-stu-id="d82ca-186">In on-premises tools:</span></span> <br><span data-ttu-id="d82ca-187">- 페더레이션이 `CsAccessEdgeConfiguration`에서 사용하도록 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-187">- Ensure federation is enabled in `CsAccessEdgeConfiguration`.</span></span><br><span data-ttu-id="d82ca-188">- 사용자에 대한 페더레이션이 `ExternalAccessPolicy`를 통해(또는 전역 정책, 사이트 정책 또는 사용자에게 할당된 정책) 사용하도록 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-188">- Ensure federation for the user is enabled through `ExternalAccessPolicy` (either through the global policy, site policy, or user assigned policy).</span></span> <br> <span data-ttu-id="d82ca-189">- 공개 페더레이션을 사용하지 않는 경우, 대상 도메인이 `AllowedDomains`에 나열되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-189">- If you are not using open federation, ensure the target domain is listed in `AllowedDomains`.</span></span> |
|<span data-ttu-id="d82ca-190">일부 사용자(비즈니스용 Skype 또는 Teams)와 사내 일부 사용자와의 하이브리드 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-190">Hybrid with some users online (in either Skype for Business or Teams) and some users on-premises.</span></span> | <span data-ttu-id="d82ca-191">온라인 및 온-프레미스 조직은 위의 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="d82ca-191">Follow above steps for both online and on-premises organizations.</span></span> |

### <a name="delivery-of-incoming-chats-and-calls"></a><span data-ttu-id="d82ca-192">수신 채팅 및 통화 전달</span><span class="sxs-lookup"><span data-stu-id="d82ca-192">Delivery of incoming chats and calls</span></span> 

<span data-ttu-id="d82ca-193">페더레이션 조직의 수신 채팅 및 통화는 TeamsUpgradePolicy의 받는 사람의 모드에 따라 사용자의 Teams 또는 비즈니스용 Skype 클라이언트에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-193">Incoming chats and calls from a federation organization will land in the user’s Teams or Skype for Business client depending on the recipient user’s mode in TeamsUpgradePolicy.</span></span>

| <span data-ttu-id="d82ca-194">원하는 작업</span><span class="sxs-lookup"><span data-stu-id="d82ca-194">If you want to</span></span> | <span data-ttu-id="d82ca-195">방법</span><span class="sxs-lookup"><span data-stu-id="d82ca-195">Do this:</span></span> |
|:---------|:-----------------------|
| <span data-ttu-id="d82ca-196">수신 페더레이션 채팅 및 통화가 사용자의 Teams 클라이언트에 도착하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-196">Ensure incoming federated chats and calls arrive in the user’s Teams client:</span></span> | <span data-ttu-id="d82ca-197">사용자를 TeamsOnly로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-197">Configure your users to be TeamsOnly.</span></span>
| <span data-ttu-id="d82ca-198">수신 페더레이션 채팅 및 통화가 사용자의 비즈니스용 Skype 클라이언트에 도착하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-198">Ensure incoming federated chats and calls arrive in the user’s Skype for Business client</span></span> | <span data-ttu-id="d82ca-199">사용자가 TeamOnly 이외의 다른 모드를 사용하도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-199">Configure your users to be in any mode other than TeamsOnly.</span></span> |


### <a name="enable-federation-between-users-in-your-organization-and-consumer-users-of-skype"></a><span data-ttu-id="d82ca-200">조직의 사용자와 Skype 고객 사용자 간 페더레이션을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="d82ca-200">Enable federation between users in your organization and consumer users of Skype</span></span>

<span data-ttu-id="d82ca-201">조직의 사용자와 Skype 고객 사용자 간 페더레이션을 사용하도록 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="d82ca-201">To enable federation between users in your organization and consumer users of Skype:</span></span>

| <span data-ttu-id="d82ca-202">조직에서 데스크톱 시각화에 대한</span><span class="sxs-lookup"><span data-stu-id="d82ca-202">If your organization is</span></span> | <span data-ttu-id="d82ca-203">다음과 같이 페더레이션을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="d82ca-203">Enable consumer federation as follows</span></span> |
|:---------|:-----------------------|
| <span data-ttu-id="d82ca-204">비즈니스용 Skype 온-프레미스가 아닌 사용자.</span><span class="sxs-lookup"><span data-stu-id="d82ca-204">Pure online with no Skype for Business on-premises.</span></span>  <span data-ttu-id="d82ca-205">여기에는 TeamsOnly 사용자 및/또는 비즈니스용 Skype Online 사용자가 있는 조직이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-205">This includes organizations that have TeamsOnly users and/or Skype for Business Online users.</span></span> | <span data-ttu-id="d82ca-206">Teams 관리 센터를 사용하는 경우:</span><span class="sxs-lookup"><span data-stu-id="d82ca-206">If using Teams Admin Center:</span></span> <br><span data-ttu-id="d82ca-207">-외부 액세스에서 **사용자가 Skype 사용자의 통신할 수 있음** 설정을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-207">-Make sure **Users can communicate with Skype users** is enabled in External Access.</span></span><br><br><span data-ttu-id="d82ca-208">PowerShell을 사용하는 경우:</span><span class="sxs-lookup"><span data-stu-id="d82ca-208">If using PowerShell:</span></span> <br><span data-ttu-id="d82ca-209">-테넌트가 페더레이션에 대해 `Get-CsTenantFederationConfiguration`이 `AllowPublicUsers=true`를 표시하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-209">-Ensure the tenant is enabled for federation: `Get-CsTenantFederationConfiguration` must show `AllowPublicUsers=true`.</span></span> <br> <span data-ttu-id="d82ca-210">- 사용자의 `CsExternalAccessPolicy`에 적합한 값인 `EnablePublicCloudAccess=true`가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-210">- Ensure the user’s effective value of `CsExternalAccessPolicy` has `EnablePublicCloudAccess=true`.</span></span> |
| <span data-ttu-id="d82ca-211">온-프레미스에서만</span><span class="sxs-lookup"><span data-stu-id="d82ca-211">Pure on-premises</span></span> | <span data-ttu-id="d82ca-212">온-프레미스 도구에서:</span><span class="sxs-lookup"><span data-stu-id="d82ca-212">In on-premises tools:</span></span> <br> <span data-ttu-id="d82ca-213">- Skype를 페더레이션되는 파트너로 사용하도록 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-213">- Ensure Skype is enabled as a federated partner.</span></span> <br> <span data-ttu-id="d82ca-214">- 사용자에 대한 `EnablePublicCloudAccess=true`가 `ExternalAccessPolicy`를 통해(또는 전역 정책, 사이트 정책 또는 사용자에게 할당된 정책) 사용하도록 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-214">- Ensure `EnablePublicCloudAccess=true` for the user through `ExternalAccessPolicy` (either via global policy, site policy, or user assigned policy).</span></span>|
| <span data-ttu-id="d82ca-215">일부 사용자(비즈니스용 Skype 또는 Teams)와 사내 일부 사용자와의 하이브리드 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-215">Hybrid with some users online (in either Skype for Business or Teams) and some users on-premises.</span></span>| <span data-ttu-id="d82ca-216">온라인 및 온-프레미스 조직은 위의 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="d82ca-216">Follow above steps for both online and on-premises organizations.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="d82ca-217">Teams 또는 비즈니스용 Skype Online 사용자가 조직 내부 또는 외부의 Skype 사용자와 통신할 수 있도록 허용하려면 **Skype 도메인** 을 허용된 도메인으로 추가할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-217">You don't have to add any **Skype domains** as allowed domains in order to enable Teams or Skype for Business Online users to communicate with Skype users inside or outside your organization.</span></span> <span data-ttu-id="d82ca-218">모든 **Skype 도메인** 이 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d82ca-218">All **Skype domains** are allowed.</span></span>

## <a name="how-does-external-access-compare-with-guest-access"></a><span data-ttu-id="d82ca-219">외부 액세스는 게스트 액세스와 어떻게 비교하나요?</span><span class="sxs-lookup"><span data-stu-id="d82ca-219">How does external access compare with guest access?</span></span>

<span data-ttu-id="d82ca-220">외부 액세스와 게스트 액세스의 차이점에 대한 자세한 내용은 [다른 조직의 사용자와 의사 소통](communicate-with-users-from-other-organizations.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d82ca-220">To learn about the difference between external access and guest access, read [Communicate with users from other organizations](communicate-with-users-from-other-organizations.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d82ca-221">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d82ca-221">Related topics</span></span>

- [<span data-ttu-id="d82ca-222">외부 (페더레이션) 사용자를 위한 기본 채팅 환경</span><span class="sxs-lookup"><span data-stu-id="d82ca-222">Native chat experience for external (federated) users</span></span>](native-chat-for-external-users.md)
