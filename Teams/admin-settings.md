---
title: Microsoft 팀의 앱에 대 한 관리자 설정
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: ritikag, rarang
description: Microsoft 팀에서 조직의 앱을 관리 하는 데 사용할 수 있는 정책 및 설정에 대해 알아봅니다.
localization_priority: Normal
ms.custom:
- ms.teamsadmincenter.apppermspolicies.adminsettings
- ms.teamsadmincenter.apppermspolicies.orgwideapps.thirdpartyapps
- ms.teamsadmincenter.apppolicies.adminsettings
f1.keywords:
- CSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6235352b845898c194e82f3ec292539904a7f61c
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582445"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="72253-103">Microsoft 팀의 앱에 대 한 관리자 설정</span><span class="sxs-lookup"><span data-stu-id="72253-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="72253-104">앱은 조직의 다양 한 도구를 제공 하 여 팀을 최대한 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72253-104">Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="72253-105">이러한 앱은 Microsoft에서 제공 하는 제 3 자, 메시징 확장, 커넥터, 인공 지능 기능을 기반으로 하거나 조직의 개발자가 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="72253-105">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="72253-106">관리 센터의 **팀 앱** 에서 조직의 앱을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="72253-106">You manage apps for your organization in **Teams apps** in the admin center.</span></span> <span data-ttu-id="72253-107">(팀 [관리자 역할을 사용 하 여 팀 관리에서](https://docs.microsoft.com/microsoftteams/using-admin-roles) 관리자 역할 및 사용 권한 가져오기를 참조 하세요.) 예를 들어 조직 수준에서 앱을 허용 하거나 차단 하 고, 팀 사용자가 사용할 수 있는 앱을 제어 하는 정책을 설정 하 고, 사용자에 게 가장 중요 한 앱을 고정 하 여 팀을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72253-107">(See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.) For example, you can allow or block apps at the org level, set policies to control what apps are available to Teams users, and customize Teams by pinning the apps that are most important for your users.</span></span>

<span data-ttu-id="72253-108">팀에서 앱 환경을 지속적으로 개선 하 고 기능 및 기능을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="72253-108">We're continually improving the app experience in Teams and adding features and functionality.</span></span> <span data-ttu-id="72253-109">시간이 지남에 따라 추가 앱 관리 기능을 구축 하 게 되므로 앱 정책에 대 한 최신 정보를 다시 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="72253-109">Over time, we'll be building additional app management capabilities, so check back for the most up-to-date information on app policies.</span></span>

## <a name="manage-apps"></a><span data-ttu-id="72253-110">앱 관리</span><span class="sxs-lookup"><span data-stu-id="72253-110">Manage apps</span></span>

<span data-ttu-id="72253-111">**앱 관리** 페이지를 사용 하 여 조직의 앱 카탈로그에 있는 모든 팀 앱을 보고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72253-111">Use the **Manage apps** page to view and manage all Teams apps in your organization's app catalog.</span></span> <span data-ttu-id="72253-112">앱의 조직 수준 상태 및 속성을 확인 하 고, 조직 수준의 앱을 차단 하거나 허용 하 고, 테 넌 트 카탈로그에 새 사용자 지정 앱을 업로드 하 고, 조직 전체 앱 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72253-112">You can see the org-level status and properties of apps, block or allow apps at the org level, upload new custom apps to your tenant catalog, and manage org-wide app settings.</span></span>

<span data-ttu-id="72253-113">**앱 관리** 페이지는 테 넌 트 카탈로그에서 사용 가능한 모든 앱에 대 한 보기를 제공 하 여 조직 전체에서 허용 하거나 차단 하는 앱을 결정 하는 데 필요한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="72253-113">The **Manage apps** page gives you a view into all available apps in your tenant catalog, providing you with the information you need to decide which apps to allow or block across your organization.</span></span> <span data-ttu-id="72253-114">그런 다음 [앱 권한 정책](#app-permission-policies), [앱 설치 정책](#app-setup-policies), [사용자 지정 앱 정책 및 설정을](#custom-app-policies-and-settings) 사용 하 여 조직의 특정 사용자에 대 한 앱 환경을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72253-114">You can then use [app permission policies](#app-permission-policies), [app setup policies](#app-setup-policies), and [custom app policies and settings](#custom-app-policies-and-settings) to configure the app experience for specific users in your organization.</span></span>

<span data-ttu-id="72253-115">자세히 알아보려면 [팀에서 앱 관리](manage-apps.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="72253-115">To learn more, see [Manage apps in Teams](manage-apps.md).</span></span>

## <a name="app-permission-policies"></a><span data-ttu-id="72253-116">앱 사용 권한 정책</span><span class="sxs-lookup"><span data-stu-id="72253-116">App permission policies</span></span>

<span data-ttu-id="72253-117">앱 사용 권한 정책을 사용 하 여 조직의 특정 사용자가 사용할 수 있는 앱을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72253-117">With app permission policies, you can control what apps are available to specific users in your organization.</span></span> <span data-ttu-id="72253-118">Microsoft, 타사, 조직에서 게시 한 앱 또는 특정 앱을 모두 허용 하거나 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72253-118">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span>

<span data-ttu-id="72253-119">예를 들어 앱 권한 정책을 사용 하 여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72253-119">For example, you can use app permission policies to:</span></span>

- <span data-ttu-id="72253-120">새로운 타사 또는 사용자 지정 빌드된 앱을 특정 사용자에 게 점진적으로 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="72253-120">Gradually roll out new third-party or custom built apps to specific users.</span></span>
- <span data-ttu-id="72253-121">조직에서 팀을 롤아웃하기 시작 하는 경우 특히 사용자 환경을 간소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="72253-121">Simplify the user experience, especially when you start rolling out Teams across your organization.</span></span>

<span data-ttu-id="72253-122">자세한 내용을 보려면 [팀에서 앱 권한 정책 관리](teams-app-permission-policies.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="72253-122">To learn more, go to [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>

## <a name="app-setup-policies"></a><span data-ttu-id="72253-123">앱 설정 정책</span><span class="sxs-lookup"><span data-stu-id="72253-123">App setup policies</span></span>

<span data-ttu-id="72253-124">앱 설정 정책을 사용 하 여 사용자에 대 한 앱 환경을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72253-124">App setup policies let you customize the app experience for your users.</span></span> <span data-ttu-id="72253-125">팀 클라이언트의 앱 표시줄에 고정 하려는 앱을 선택 하 고 웹, 데스크톱 및 모바일 클라이언트에서 표시 되는 순서를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72253-125">You choose the apps that you want to pin to the app bar in the Teams clients and the order in which they appear, on web, desktop, and mobile clients.</span></span>

<span data-ttu-id="72253-126">다음은 앱 설치 정책을 사용할 수 있는 방법의 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="72253-126">Here's some examples of how you can use app setup policies:</span></span>

- <span data-ttu-id="72253-127">핵심 앱의 인식 및 채택을 드라이브.</span><span class="sxs-lookup"><span data-stu-id="72253-127">Drive awareness and adoption of core apps.</span></span> <span data-ttu-id="72253-128">예를 들어 HR 팀의 사용자에 게 사용자 지정 채용 및 재능 관리 앱을 고정 합니다.</span><span class="sxs-lookup"><span data-stu-id="72253-128">For example, pin a custom recruiting and talent management app for users on your HR team.</span></span>
- <span data-ttu-id="72253-129">채팅, 팀, 통화 등의 핵심 팀 기능을 선택적으로 고정 합니다.</span><span class="sxs-lookup"><span data-stu-id="72253-129">Selectively pin core Teams features, such as Chat, Teams, and Calling.</span></span> <span data-ttu-id="72253-130">이렇게 하면 사용자가 팀 내에서 특정 활동을 진행 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72253-130">Doing so can help ensure users are engaged in specific activities within Teams.</span></span>

<span data-ttu-id="72253-131">자세한 내용은 [팀에서 앱 설치 정책 관리](teams-app-setup-policies.md)를 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="72253-131">To learn more, check out [Manage app setup policies in Teams](teams-app-setup-policies.md).</span></span>

## <a name="custom-app-policies-and-settings"></a><span data-ttu-id="72253-132">사용자 지정 앱 정책 및 설정</span><span class="sxs-lookup"><span data-stu-id="72253-132">Custom app policies and settings</span></span>

<span data-ttu-id="72253-133">조직의 개발자는 팀을 통해 사용자 지정 앱을 만들고 테스트 하 고 다른 사용자에 게 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72253-133">Teams allows developers in your organization to build, test, and deploy custom apps to other users.</span></span> <span data-ttu-id="72253-134">.Zip 파일의 앱 패키지를 팀 또는 개인 컨텍스트에서 직접 업로드 하 여 사용자 지정 앱을 팀에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72253-134">Custom apps can be added to Teams by uploading an app package in a .zip file directly to a team or in the personal context.</span></span> <span data-ttu-id="72253-135">앱 설치 정책을 사용 하 여 조직에서 사용자 지정 앱을 업로드할 수 있는 사용자를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72253-135">You can use app setup policies to control who in your organization can upload custom apps.</span></span> <span data-ttu-id="72253-136">또한 조직 전체 설정을 설정 하 여 사용자가 특정 사용자 지정 앱과 상호 작용할 수 있는지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72253-136">You can also set org-wide settings to control whether users can interact with specific custom apps.</span></span>

<span data-ttu-id="72253-137">자세한 내용은 [팀에서 사용자 지정 앱 정책 및 설정 관리](teams-custom-app-policies-and-settings.md)를 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="72253-137">To learn more, go to [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>
