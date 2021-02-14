---
title: Microsoft Teams의 앱에 대한 관리자 설정
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: ritikag, rarang
description: Microsoft Teams에서 조직의 앱을 관리하는 데 사용할 수 있는 정책 및 설정에 대해 자세히 배워야 합니다.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.adminsettings
- ms.teamsadmincenter.apppermspolicies.orgwideapps.thirdpartyapps
- ms.teamsadmincenter.apppolicies.adminsettings
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fb824c7082679591b3fa39a1c8a4b13152e0cc75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532525"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="1ad57-103">Microsoft Teams의 앱에 대한 관리자 설정</span><span class="sxs-lookup"><span data-stu-id="1ad57-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="1ad57-104">앱은 조직에서 Teams를 더 많이 활용하는 데 사용할 수 있는 도구를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1ad57-104">Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="1ad57-105">이러한 앱은 타사 또는 조직의 개발자가 Microsoft에서 제공하는 탭, 메시징 확장, 커넥터 및 봇의 기능을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="1ad57-105">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="1ad57-106">관리 센터의 **Teams** 앱에서 조직의 앱을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="1ad57-106">You manage apps for your organization in **Teams apps** in the admin center.</span></span> <span data-ttu-id="1ad57-107">(Teams 관리자 역할을 사용하여 [Teams를](https://docs.microsoft.com/microsoftteams/using-admin-roles) 관리하여 관리자 역할 및 사용 권한 부여에 대한 자세한 내용을 참조하세요.) 예를 들어 조직 수준에서 앱을 허용하거나 차단하고, Teams 사용자가 사용할 수 있는 앱을 제어하는 정책을 설정하고, 사용자에게 가장 중요한 앱을 고정하여 Teams를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ad57-107">(See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.) For example, you can allow or block apps at the org level, set policies to control what apps are available to Teams users, and customize Teams by pinning the apps that are most important for your users.</span></span>

<span data-ttu-id="1ad57-108">Teams에서 앱 환경을 지속적으로 개선하고 기능 및 기능을 추가하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ad57-108">We're continually improving the app experience in Teams and adding features and functionality.</span></span> <span data-ttu-id="1ad57-109">시간이 지날 때 추가 앱 관리 기능을 구축할 예정이니 앱 정책에 대한 최신 정보를 다시 확인해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ad57-109">Over time, we'll be building additional app management capabilities, so check back for the most up-to-date information on app policies.</span></span>

## <a name="manage-apps"></a><span data-ttu-id="1ad57-110">앱 관리</span><span class="sxs-lookup"><span data-stu-id="1ad57-110">Manage apps</span></span>

<span data-ttu-id="1ad57-111">앱 관리 **페이지를** 사용하여 조직의 앱 카탈로그에서 모든 Teams 앱을 보고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="1ad57-111">Use the **Manage apps** page to view and manage all Teams apps in your organization's app catalog.</span></span> <span data-ttu-id="1ad57-112">앱의 구성 수준 상태 및 속성을 보고, 앱을 차단 또는 허용하고, 테넌트 카탈로그에 새 사용자 지정 앱을 업로드하고, 전체 앱 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ad57-112">You can see the org-level status and properties of apps, block or allow apps at the org level, upload new custom apps to your tenant catalog, and manage org-wide app settings.</span></span>

<span data-ttu-id="1ad57-113">앱 **관리** 페이지에서는 테넌트 카탈로그에서 사용 가능한 모든 앱에 대한 보기를 제공하여 조직 전체에서 허용하거나 차단할 앱을 결정하는 데 필요한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1ad57-113">The **Manage apps** page gives you a view into all available apps in your tenant catalog, providing you with the information you need to decide which apps to allow or block across your organization.</span></span> <span data-ttu-id="1ad57-114">그런 다음 앱 사용 [](#app-setup-policies) [권한 정책,](#app-permission-policies) [](#custom-app-policies-and-settings) 앱 설정 정책 및 사용자 지정 앱 정책 및 설정을 사용하여 조직의 특정 사용자에 대한 앱 환경을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ad57-114">You can then use [app permission policies](#app-permission-policies), [app setup policies](#app-setup-policies), and [custom app policies and settings](#custom-app-policies-and-settings) to configure the app experience for specific users in your organization.</span></span>

<span data-ttu-id="1ad57-115">자세한 내용은 [Teams에서 앱 관리를 참조하세요.](manage-apps.md)</span><span class="sxs-lookup"><span data-stu-id="1ad57-115">To learn more, see [Manage apps in Teams](manage-apps.md).</span></span>

## <a name="app-permission-policies"></a><span data-ttu-id="1ad57-116">앱 사용 권한 정책</span><span class="sxs-lookup"><span data-stu-id="1ad57-116">App permission policies</span></span>

<span data-ttu-id="1ad57-117">앱 사용 권한 정책을 사용하여 조직의 특정 사용자가 사용할 수 있는 앱을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ad57-117">With app permission policies, you can control what apps are available to specific users in your organization.</span></span> <span data-ttu-id="1ad57-118">모든 앱 또는 Microsoft, 타사 및 조직에서 게시한 특정 앱을 허용하거나 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ad57-118">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span>

<span data-ttu-id="1ad57-119">예를 들어 앱 사용 권한 정책을 사용하여 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ad57-119">For example, you can use app permission policies to:</span></span>

- <span data-ttu-id="1ad57-120">새 타사 또는 사용자 지정 구축 앱을 특정 사용자에게 점진적으로 롤아웃합니다.</span><span class="sxs-lookup"><span data-stu-id="1ad57-120">Gradually roll out new third-party or custom built apps to specific users.</span></span>
- <span data-ttu-id="1ad57-121">특히 조직 전체에서 Teams를 배포하기 시작할 때 사용자 환경을 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="1ad57-121">Simplify the user experience, especially when you start rolling out Teams across your organization.</span></span>

<span data-ttu-id="1ad57-122">자세한 내용은 Teams에서 앱 [사용 권한 정책 관리로 이동하세요.](teams-app-permission-policies.md)</span><span class="sxs-lookup"><span data-stu-id="1ad57-122">To learn more, go to [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>

## <a name="app-setup-policies"></a><span data-ttu-id="1ad57-123">앱 설정 정책</span><span class="sxs-lookup"><span data-stu-id="1ad57-123">App setup policies</span></span>

<span data-ttu-id="1ad57-124">앱 설정 정책을 사용하면 사용자에 대한 앱 환경을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ad57-124">App setup policies let you customize the app experience for your users.</span></span> <span data-ttu-id="1ad57-125">Teams 클라이언트의 앱 바에 고정할 앱과 웹, 데스크톱 및 모바일 클라이언트에 나타나는 순서를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ad57-125">You choose the apps that you want to pin to the app bar in the Teams clients and the order in which they appear, on web, desktop, and mobile clients.</span></span>

<span data-ttu-id="1ad57-126">앱 설정 정책을 사용하는 방법에 대한 몇 가지 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1ad57-126">Here's some examples of how you can use app setup policies:</span></span>

- <span data-ttu-id="1ad57-127">핵심 앱의 인식 및 채택을 주도합니다.</span><span class="sxs-lookup"><span data-stu-id="1ad57-127">Drive awareness and adoption of core apps.</span></span> <span data-ttu-id="1ad57-128">예를 들어 HR 팀의 사용자에 대한 사용자 지정 채용 및 인재 관리 앱을 고정합니다.</span><span class="sxs-lookup"><span data-stu-id="1ad57-128">For example, pin a custom recruiting and talent management app for users on your HR team.</span></span>
- <span data-ttu-id="1ad57-129">채팅, Teams 및 통화와 같은 핵심 Teams 기능을 선택적으로 고정합니다.</span><span class="sxs-lookup"><span data-stu-id="1ad57-129">Selectively pin core Teams features, such as Chat, Teams, and Calling.</span></span> <span data-ttu-id="1ad57-130">이렇게 하면 사용자가 Teams 내에서 특정 활동에 참여하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ad57-130">Doing so can help ensure users are engaged in specific activities within Teams.</span></span>

<span data-ttu-id="1ad57-131">자세한 내용은 Teams에서 앱 설정 [정책 관리를 확인하세요.](teams-app-setup-policies.md)</span><span class="sxs-lookup"><span data-stu-id="1ad57-131">To learn more, check out [Manage app setup policies in Teams](teams-app-setup-policies.md).</span></span>

## <a name="custom-app-policies-and-settings"></a><span data-ttu-id="1ad57-132">사용자 지정 앱 정책 및 설정</span><span class="sxs-lookup"><span data-stu-id="1ad57-132">Custom app policies and settings</span></span>

<span data-ttu-id="1ad57-133">Teams를 사용하면 조직의 개발자가 사용자 지정 앱을 빌드, 테스트 및 다른 사용자에게 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ad57-133">Teams allows developers in your organization to build, test, and deploy custom apps to other users.</span></span> <span data-ttu-id="1ad57-134">.zip 파일에서 앱 패키지를 팀 또는 개인 컨텍스트에 직접 업로드하여 사용자 지정 앱을 Teams에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ad57-134">Custom apps can be added to Teams by uploading an app package in a .zip file directly to a team or in the personal context.</span></span> <span data-ttu-id="1ad57-135">앱 설정 정책을 사용하여 조직에서 사용자 지정 앱을 업로드할 수 있는 사용자들을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ad57-135">You can use app setup policies to control who in your organization can upload custom apps.</span></span> <span data-ttu-id="1ad57-136">사용자가 특정 사용자 지정 앱과 상호 작용할 수 있는지 여부를 제어하도록 전체 설정을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ad57-136">You can also set org-wide settings to control whether users can interact with specific custom apps.</span></span>

<span data-ttu-id="1ad57-137">자세한 내용은 Teams에서 사용자 지정 앱 정책 [및 설정 관리로 이동하세요.](teams-custom-app-policies-and-settings.md)</span><span class="sxs-lookup"><span data-stu-id="1ad57-137">To learn more, go to [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>
