---
title: Microsoft 팀의 앱에 대 한 관리자 설정
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: ritikag, rarang
description: Microsoft 팀에서 조직의 앱을 관리 하는 데 사용할 수 있는 정책 및 설정에 대해 알아봅니다.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
f1keywords:
- ms.teamsadmincenter.apppermspolicies.adminsettings
- ms.teamsadmincenter.apppermspolicies.orgwideapps.thirdpartyapps
- ms.teamsadmincenter.apppolicies.adminsettings
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: efeb467c5cf3cad5e427a26b01f972d40922db21
ms.sourcegitcommit: 16345e8a19dba6fd1b39f876755088f9d8368f13
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/23/2019
ms.locfileid: "36620454"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="5d492-103">Microsoft 팀의 앱에 대 한 관리자 설정</span><span class="sxs-lookup"><span data-stu-id="5d492-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="5d492-104">앱은 조직의 다양 한 도구를 제공 하 여 팀을 최대한 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d492-104">Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="5d492-105">이러한 앱은 Microsoft에서 제공 하는 제 3 자, 메시징 확장, 커넥터, 인공 지능 기능을 기반으로 하거나 조직의 개발자가 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5d492-105">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="5d492-106">Microsoft 팀 관리 센터의 **팀 앱** 에서 조직의 앱을 관리 하는 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d492-106">In **Teams apps** in the Microsoft Teams admin center, you can set policies to manage apps for your organization.</span></span> <span data-ttu-id="5d492-107">예를 들어 팀 사용자가 사용할 수 있는 앱을 제어 하는 정책을 설정 하 고 사용자에 게 가장 중요 한 앱을 고정 하 여 팀을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d492-107">For example, you can set policies to control what apps are available to Teams users and you can customize Teams by pinning the apps that are most important for your users.</span></span>

<span data-ttu-id="5d492-108">팀에서 앱 환경을 지속적으로 개선 하 고 기능 및 기능을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d492-108">We're continually improving the app experience in Teams and adding features and functionality.</span></span> <span data-ttu-id="5d492-109">시간이 지남에 따라 추가 앱 관리 기능을 구축 하 게 되므로 앱 정책에 대 한 최신 정보를 다시 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="5d492-109">Over time, we'll be building additional app management capabilities, so check back for the most up-to-date information on app policies.</span></span>

## <a name="app-permission-policies"></a><span data-ttu-id="5d492-110">앱 권한 정책</span><span class="sxs-lookup"><span data-stu-id="5d492-110">App permission policies</span></span>

<span data-ttu-id="5d492-111">앱 사용 권한 정책을 사용 하 여 조직 전체 또는 특정 사용자에 대 한 앱을 차단 하거나 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d492-111">With app permission policies, you can block or allow apps, either org-wide or for specific users.</span></span>  <span data-ttu-id="5d492-112">앱을 차단 하면 해당 앱과의 모든 조작이 비활성화 되며 사용자 용 팀에 앱이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d492-112">When you block an app, all interactions with that app are disabled and the app doesn't appear in Teams for users.</span></span>

<span data-ttu-id="5d492-113">예를 들어 앱 권한 정책을 사용 하 여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d492-113">For example, you can use app permission policies to:</span></span>

- <span data-ttu-id="5d492-114">조직에 대 한 사용 권한이 나 데이터 손실 위험을 초래 하는 앱을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d492-114">Disable an app that poses a permission or data loss risk to your organization.</span></span>
- <span data-ttu-id="5d492-115">새로운 타사 또는 사용자 지정 빌드된 앱을 특정 사용자에 게 점진적으로 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d492-115">Gradually roll out new third-party or custom built apps to specific users.</span></span>
- <span data-ttu-id="5d492-116">조직에서 팀을 롤아웃하기 시작 하는 경우 특히 사용자 환경을 간소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d492-116">Simplify the user experience, especially when you start rolling out Teams across your organization.</span></span>

<span data-ttu-id="5d492-117">자세한 내용을 보려면 [팀에서 앱 권한 정책 관리](teams-app-permission-policies.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5d492-117">To learn more, go to [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>

## <a name="app-setup-policies"></a><span data-ttu-id="5d492-118">앱 설정 정책</span><span class="sxs-lookup"><span data-stu-id="5d492-118">App setup policies</span></span>

<span data-ttu-id="5d492-119">앱 설정 정책을 사용 하 여 사용자에 대 한 앱 환경을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d492-119">App setup policies let you customize the app experience for your users.</span></span> <span data-ttu-id="5d492-120">팀 클라이언트의 앱 표시줄에 고정 하려는 앱을 선택 하 고 웹, 데스크톱 및 모바일 클라이언트에서 표시 되는 순서를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d492-120">You choose the apps that you want to pin to the app bar in the Teams clients and the order in which they appear, on web, desktop, and mobile clients.</span></span>

<span data-ttu-id="5d492-121">다음은 앱 설치 정책을 사용할 수 있는 방법의 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="5d492-121">Here's some examples of how you can use app setup policies:</span></span>
- <span data-ttu-id="5d492-122">핵심 앱의 인식 및 채택을 드라이브.</span><span class="sxs-lookup"><span data-stu-id="5d492-122">Drive awareness and adoption of core apps.</span></span> <span data-ttu-id="5d492-123">예를 들어 HR 팀의 사용자에 게 사용자 지정 채용 및 재능 관리 앱을 고정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d492-123">For example, pin a custom recruiting and talent management app for users on your HR team.</span></span>
- <span data-ttu-id="5d492-124">채팅, 팀, 통화 등의 핵심 팀 기능을 선택적으로 고정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d492-124">Selectively pin core Teams features, such as Chat, Teams, and Calling.</span></span> <span data-ttu-id="5d492-125">이렇게 하면 사용자가 팀 내에서 특정 활동을 진행 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d492-125">Doing so can help ensure users are engaged in specific activities within Teams.</span></span>

<span data-ttu-id="5d492-126">자세한 내용은 [팀에서 앱 설치 정책 관리](teams-app-setup-policies.md)를 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="5d492-126">To learn more, check out [Manage app setup policies in Teams](teams-app-setup-policies.md).</span></span>

## <a name="custom-app-policies-and-settings"></a><span data-ttu-id="5d492-127">사용자 지정 앱 정책 및 설정</span><span class="sxs-lookup"><span data-stu-id="5d492-127">Custom app policies and settings</span></span>

<span data-ttu-id="5d492-128">조직의 개발자는 팀을 통해 사용자 지정 앱을 만들고 테스트 하 고 다른 사용자에 게 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d492-128">Teams allows developers in your organization to build, test, and deploy custom apps to other users.</span></span> <span data-ttu-id="5d492-129">.Zip 파일의 앱 패키지를 팀 또는 개인 컨텍스트에서 직접 업로드 하 여 사용자 지정 앱을 팀에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d492-129">Custom apps can be added to Teams by uploading an app package in a .zip file directly to a team or in the personal context.</span></span> <span data-ttu-id="5d492-130">앱 설치 정책을 사용 하 여 조직에서 사용자 지정 앱을 업로드할 수 있는 사용자를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d492-130">You can use app setup policies to control who in your organization can upload custom apps.</span></span> <span data-ttu-id="5d492-131">또한 조직 전체 설정을 설정 하 여 사용자가 특정 사용자 지정 앱과 상호 작용할 수 있는지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d492-131">You can also set org-wide settings to control whether users can interact with specific custom  apps.</span></span>

<span data-ttu-id="5d492-132">자세한 내용은 [팀에서 사용자 지정 앱 정책 및 설정 관리](teams-custom-app-policies-and-settings.md)를 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="5d492-132">To learn more, go to [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>