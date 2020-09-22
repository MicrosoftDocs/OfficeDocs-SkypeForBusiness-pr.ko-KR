---
title: Microsoft 팀 관리 센터에서 전원 플랫폼 앱 관리
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: joglocke
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Microsoft 팀 관리 센터에서 Power Platform 앱에 대 한 액세스를 관리 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 74bfabaff0ec7ed5f27c08ac86b325164d9dad10
ms.sourcegitcommit: af9f96010460f9323db84912fe143aa0750ac798
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171465"
---
# <a name="manage-power-platform-apps-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="773c9-103">Microsoft 팀 관리 센터에서 전원 플랫폼 앱 관리</span><span class="sxs-lookup"><span data-stu-id="773c9-103">Manage Power Platform apps in the Microsoft Teams admin center</span></span>

## <a name="power-platform-apps-in-teams"></a><span data-ttu-id="773c9-104">팀의 파워 플랫폼 앱</span><span class="sxs-lookup"><span data-stu-id="773c9-104">Power Platform apps in Teams</span></span>

<span data-ttu-id="773c9-105">이 문서에서는 Microsoft 팀 관리 센터에서 팀에 추가 된 [파워 플랫폼](https://powerplatform.microsoft.com/) 앱을 관리 하는 방법에 대해 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-105">This article gives you an overview of how to manage [Power Platform](https://powerplatform.microsoft.com/) apps added to Teams in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="773c9-106">[Power Apps](https://powerapps.microsoft.com) 는 조직의 결정권자가 비즈니스 데이터에 연결 하는 사용자 지정 앱을 작성 하는 데 사용할 수 있는 낮은 코드/비 코드 응용 프로그램 개발 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-106">[Power Apps](https://powerapps.microsoft.com) is a low-code/no-code application development environment that makers in your organization can use to build custom apps that connect to your business data.</span></span> <span data-ttu-id="773c9-107">[파워 가상 에이전트](https://docs.microsoft.com/power-virtual-agents/fundamentals-what-is-power-virtual-agents) 는 의사 결정권자가 강력한 인공 지능을 만들 수 있는 비 코드 봇 빌딩 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-107">[Power Virtual Agents](https://docs.microsoft.com/power-virtual-agents/fundamentals-what-is-power-virtual-agents) is a no-code bot building environment for makers to create powerful bots.</span></span> <span data-ttu-id="773c9-108">조직에서는 강력한 플랫폼 앱을 팀에 통합 하 여 더 많은 공동 작업을 가능 하 게 하는 비즈니스 프로세스를 간소화 하 고, 생산성을 높이고 사용자 지정 솔루션을 만들고 공유 해 보세요.</span><span class="sxs-lookup"><span data-stu-id="773c9-108">With the integration of Power Platform apps into Teams, organizations can streamline business processes, respond to changing business needs more rapidly to drive greater collaboration, and create and share custom solutions to be more productive.</span></span>  

<span data-ttu-id="773c9-109">조직에서 결정권자가 만든 플랫폼 앱이 자동으로 팀에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-109">Power Platform apps created by makers in your organization are automatically added to Teams.</span></span> <span data-ttu-id="773c9-110">결정권자는 power [Apps의 공유 기능](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app) 을 사용 하 여 앱에 액세스할 수 있는 사용자와 [power Virtual agent의 공유 기능](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-110">Makers can control who can access their app by using the [sharing feature in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app) and the [sharing feature in Power Virtual Agents](https://docs.microsoft.com/power-virtual-agents/admin-share-bots).</span></span> 

<span data-ttu-id="773c9-111">Power Platform 앱을 만들거나 공유 하는 경우, 사용자는 동료 들이 작성 한 \*\* *조직 이름*에 대 한 빌드\*\*를 수행 하 여 앱 페이지에서 파일을 보고 설치할 수 있습니다  >  **Built by your colleagues**.</span><span class="sxs-lookup"><span data-stu-id="773c9-111">When a Power Platform app is created or shared, users can view and install it on the Apps page by going to **Built for *Your Organization Name*** > **Built by your colleagues**.</span></span> <span data-ttu-id="773c9-112">앱이 여기에 표시 되도록 앱을 만들거나 공유 하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-112">(It might take a few minutes after an app is created or shared for the app to appear here.)</span></span>

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="동료의 빌드 목록에 나열 된 파워 플랫폼 앱을 보여 주는 앱 페이지 스크린샷":::

<span data-ttu-id="773c9-114">앱이 다음 조건 중 하나를 충족 하는 경우 사용자는 **동료에 의해 기본으로 제공** 되는 전원 플랫폼 앱을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-114">A user will see a Power Platform app in **Built by your colleagues** if the app meets one of the following conditions.</span></span>

|<span data-ttu-id="773c9-115">Power Apps</span><span class="sxs-lookup"><span data-stu-id="773c9-115">Power Apps</span></span> |<span data-ttu-id="773c9-116">파워 가상 에이전트</span><span class="sxs-lookup"><span data-stu-id="773c9-116">Power Virtual Agents</span></span>  |
|---------|---------|
|<ul><li><span data-ttu-id="773c9-117">사용자가 앱을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-117">The user created the app.</span></span></li><li><span data-ttu-id="773c9-118">앱이 사용자와 직접 공유 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-118">The app was shared directly with the user.</span></span></li><li><span data-ttu-id="773c9-119">사용자가 최근에 앱을 사용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-119">The user recently used the app.</span></span> </li></ul>| <ul><li><span data-ttu-id="773c9-120">사용자가 봇을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-120">The user created the bot.</span></span></li><li><span data-ttu-id="773c9-121">봇은 사용자가 소속 된 팀에서 소유 합니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-121">The bot is owned by a team the user is a member of.</span></span> </li></ul>        |

<span data-ttu-id="773c9-122">사용자가 다른 팀 앱을 설치 하는 것과 동일한 방식으로 전원 플랫폼 앱을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-122">Users install Power Platform apps in the same way they install any other Teams app.</span></span> <span data-ttu-id="773c9-123">사용자는 자신이 소유한 팀, 자신이 속한 채팅, 개인 범위 등 사용 권한이 있는 컨텍스트에만 앱을 설치할 수 있다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="773c9-123">Keep in mind that users can only install  apps to the context to which they have permissions, for example, a team they own, a chat that they're a part of, or their personal scope.</span></span>

## <a name="manage-access-to-power-platform-apps-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="773c9-124">Microsoft 팀 관리 센터의 파워 플랫폼 앱에 대 한 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="773c9-124">Manage access to Power Platform apps in the Microsoft Teams admin center</span></span>

<span data-ttu-id="773c9-125">관리자는 팀의 앱 페이지에서 **동료에 의해 기본으로 제공** 되는 플랫폼 앱이 표시 되는지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-125">As an admin, you can control whether Power Platform apps are listed in **Built by your colleagues** on the Apps page in Teams.</span></span> <span data-ttu-id="773c9-126">Power app에서 만든 모든 앱 또는 앱 [관리](manage-apps.md) 페이지의 조직 수준에서 직접 만든 모든 앱 또는 [앱 권한 정책을](teams-app-permission-policies.md)사용 하는 특정 사용자에 대해 일괄적으로 차단 하거나 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-126">You can collectively block or allow all apps created in Power Apps or all apps created in Power Virtual Agents at the org level on the [Manage apps](manage-apps.md) page or for specific users using [app permission policies](teams-app-permission-policies.md).</span></span>

<span data-ttu-id="773c9-127">조직의 앱 스토어에 있는 **공유 Power Apps** 및 **공유 파워 가상 에이전트 앱** 앱은 해당 특정 플랫폼에서 만든 모든 앱을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-127">The **Shared Power Apps** and **Shared Power Virtual Agent Apps** apps in your organization's app store represent all apps created on that particular platform.</span></span> <span data-ttu-id="773c9-128">조직 수준에서 이러한 앱 중 하나 또는 둘 다를 차단 하거나 특정 사용자의 경우 해당 사용자가 **동료에 의해 빌드된** 플랫폼의 앱을 볼 수 없으며 팀에 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-128">If you block one or both these apps at the org level or for specific users, those users can't see any apps from those platforms in **Built by your colleagues** and can't install them in Teams.</span></span>  

<span data-ttu-id="773c9-129">Power Apps 및 Power Virtual Agent에서 만든 모든 앱에 대 한 액세스는 제어할 수 있지만 개별 앱을 허용 하거나 차단 하는 것은 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-129">Keep in mind that you can control access to all apps created in Power Apps and Power Virtual Agents but you can't allow or block individual apps.</span></span> <span data-ttu-id="773c9-130">결정권자는 Power App 및 Power Virtual Agent 내에서 공유 기능을 통해 자신이 만든 앱에 액세스할 수 있는 사용자를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-130">Makers decide who can access the apps they create through the sharing feature from within Power Apps and Power Virtual Agents.</span></span> <span data-ttu-id="773c9-131">작성자가 사용자와 파워 가상 에이전트에서 만든 앱을 공유 하 고 해당 사용자에 대 한 **공유 파워 가상 에이전트 앱** 을 차단한 경우 사용자는 해당 플랫폼에서 팀으로 앱을 보거나 설치할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-131">If a maker shared an app they created in Power Virtual Agents with a user and you blocked **Shared Power Virtual Agents Apps** for that user, the user won't be able to see or install any apps from that platform in Teams.</span></span>

<span data-ttu-id="773c9-132">사용자가 Power App 또는 Power Virtual Agent의 앱에 액세스할 수 있는 경우 사용자가 이러한 플랫폼 중 하나 또는 둘 다에서 앱에 액세스 하지 못하도록 차단 하면 앱 또는 앱을 차단 하기 전에 사용자가 설치한 Power 플랫폼용 앱을 계속 액세스 하 여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-132">If a user is allowed to access apps from Power Apps or Power Virtual Agents, and you then block the user from accessing apps from one or both these platforms, the user can still access and use the Power Platforms apps that they installed before you blocked the app or apps.</span></span> <span data-ttu-id="773c9-133">그러나 사용자는 동료 들이 **만든**플랫폼의 앱을 더 이상 보거나 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-133">However, the user can no longer see or install any apps from those platforms in **Built by your colleagues**.</span></span>

> [!NOTE]
> <span data-ttu-id="773c9-134">[앱 관리](manage-apps.md) 페이지의 조직 전체의 **사용자 지정 앱과 상호 작용 허용** 이 설정이 조직의 모든 사용자에 게 적용 되며 사용자 지정 앱과 상호 작용할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-134">The **Allow interaction with custom apps** org-wide app setting on the [Manage apps](manage-apps.md) page applies to everyone in your organization and governs whether they can interact with custom apps.</span></span> <span data-ttu-id="773c9-135">조직 전체 앱 설정은 모든 사용자의 동작을 제어 하 고 사용자에 게 할당 된 다른 앱 사용 권한 정책을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-135">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="773c9-136">이 설정은 기본적으로 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-136">By default, this setting is turned on.</span></span> <span data-ttu-id="773c9-137">이 설정을 끄면 조직의 사용자가 파워 플랫폼 앱을 포함 하 여 사용자 지정 앱을 보거나 설치할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-137">If this setting is turned off, users in your organization can't see or install any custom apps, including Power Platform apps.</span></span> <span data-ttu-id="773c9-138">자세히 알아보려면 [조직 전체 앱 설정 관리](manage-apps.md#manage-org-wide-app-settings)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="773c9-138">To learn  more, see [Manage org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

### <a name="allow-or-block-power-platform-apps-for-your-organization"></a><span data-ttu-id="773c9-139">조직의 파워 플랫폼 앱 허용 또는 차단</span><span class="sxs-lookup"><span data-stu-id="773c9-139">Allow or block Power Platform apps for your organization</span></span>

<span data-ttu-id="773c9-140">기본적으로 조직의 모든 팀 사용자가 **공유 Power Apps** 및 **공유 파워 가상 에이전트 앱** 을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-140">By default, **Shared Power Apps** and **Shared Power Virtual Agent Apps** are allowed for all Teams users in your organization.</span></span> <span data-ttu-id="773c9-141">Microsoft 팀 관리 센터의 [앱 관리](manage-apps.md) 페이지에서 조직 수준에서 해당 항목을 차단 하거나 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-141">You can block or allow them at the org level on the [Manage apps](manage-apps.md) page of the Microsoft Teams admin center.</span></span>  

1. <span data-ttu-id="773c9-142">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**으로  >  **앱 관리**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span> <span data-ttu-id="773c9-143">페이지에 액세스 하려면 전역 관리자 또는 팀 서비스 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-143">You must be a global admin or Teams service admin to access the page.</span></span>
2. <span data-ttu-id="773c9-144">앱 목록에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-144">In the list of apps, do one of the following.</span></span>

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="공유 전원 플랫폼 앱이 표시 된 앱 관리 페이지 스크린샷":::

    - <span data-ttu-id="773c9-146">Power Apps 또는 조직의 모든 사용자에 대해 Power Virtual Agent에서 만든 앱을 차단 하려면 **공유 Power apps** 또는 **공유 파워 가상 에이전트 앱**을 검색 하 여 선택한 다음 **block**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-146">To block apps created in Power Apps or Power Virtual Agents for all users in your organization, search for **Shared Power Apps** or **Shared Power Virtual Agent Apps**, select it, and then click **Block**.</span></span>
    - <span data-ttu-id="773c9-147">Power App에서 만든 앱 또는 조직의 모든 사용자에 대 한 파워 가상 에이전트를 허용 하려면 **공유 Power apps** 또는 **공유 파워 가상 에이전트 앱**을 검색 하 여 선택한 다음 **허용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-147">To allow apps created in Power Apps or Power Virtual Agents for all users in your organization, search for **Shared Power Apps** or **Shared Power Virtual Agent Apps**, select it, and then click **Allow**.</span></span>

### <a name="allow-or-block-power-platform-apps-for-specific-users"></a><span data-ttu-id="773c9-148">특정 사용자에 대 한 파워 플랫폼 앱 허용 또는 차단</span><span class="sxs-lookup"><span data-stu-id="773c9-148">Allow or block Power Platform apps for specific users</span></span>

<span data-ttu-id="773c9-149">조직의 특정 사용자가 Power App 또는 Power Virtual Agent에서 만든 앱에 액세스 하는 것을 허용 하거나 차단 하려면 하나 이상의 사용자 지정 [앱 권한 정책을](teams-app-permission-policies.md)만들고 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-149">To allow or block specific users in your organization from accessing apps created in Power Apps or Power Virtual Agents, create and assign one or more custom [app permission policies](teams-app-permission-policies.md).</span></span> 

<span data-ttu-id="773c9-150">예를 들어 Power Apps에서 만든 앱에 특정 사용자가 액세스 하는 것을 차단 하려면 **공유 Power 앱**을 차단 하는 사용자 지정 앱 권한 정책을 만든 다음 해당 사용자에 게 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="773c9-150">For example, to block specific users from accessing apps created in Power Apps, create a custom app permission policy to block **Shared Power Apps**, and then assign the policy to those users.</span></span>

:::image type="content" source="media/manage-power-platform-apps-app-permissions-policy.png" alt-text="공유 Power Apps가 차단 된 사용자 지정 앱 권한 정책 예제 스크린샷":::

## <a name="related-topics"></a><span data-ttu-id="773c9-152">관련 항목</span><span class="sxs-lookup"><span data-stu-id="773c9-152">Related topics</span></span>

- [<span data-ttu-id="773c9-153">Power Apps에서 캔버스 앱 공유</span><span class="sxs-lookup"><span data-stu-id="773c9-153">Share a canvas app in Power Apps</span></span>](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app)
- [<span data-ttu-id="773c9-154">다른 사용자와 인공 지능 공유</span><span class="sxs-lookup"><span data-stu-id="773c9-154">Share your bot with other users</span></span>](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)
- [<span data-ttu-id="773c9-155">Microsoft 팀 관리 센터에서 앱 관리</span><span class="sxs-lookup"><span data-stu-id="773c9-155">Manage apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="773c9-156">Teams에서 앱 사용 권한 정책 관리</span><span class="sxs-lookup"><span data-stu-id="773c9-156">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="773c9-157">팀 앱 제출 API를 통해 제출 된 사용자 지정 앱 게시</span><span class="sxs-lookup"><span data-stu-id="773c9-157">Publish a custom app submitted through the Teams App Submission API</span></span>](submit-approve-custom-apps.md)
