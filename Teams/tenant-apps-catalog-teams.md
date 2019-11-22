---
title: Microsoft 팀 테 넌 트 앱 카탈로그에서 앱 게시
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/20/2019
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: Microsoft 팀 테 넌 트 앱 카탈로그에서 앱을 게시 하기 위한 지침입니다.
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.apppermspolicies.publishtenantapps
- ms.teamsadmincenter.apppolicies.publishtenantapps
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 42fd9820f6f8ce11b245412a5ae99ed7b43dbc1e
ms.sourcegitcommit: 0f6321d51b40f06855679c18f7313febfedd419a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "38793534"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-apps-catalog"></a><span data-ttu-id="89dbd-103">Microsoft 팀 테 넌 트 앱 카탈로그에서 앱 게시</span><span class="sxs-lookup"><span data-stu-id="89dbd-103">Publish apps in the Microsoft Teams Tenant Apps Catalog</span></span>
=======================================================

<span data-ttu-id="89dbd-104">Microsoft 팀 테 넌 트 앱 카탈로그를 사용 하 여 조직에 lob (기간 업무) 응용 프로그램을 테스트 하 고 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89dbd-104">You can use the Microsoft Teams Tenant Apps Catalog to test and distribute line-of-business applications to your organization.</span></span>

<span data-ttu-id="89dbd-105">팀 테 넌 트 앱 카탈로그를 사용 하면 조직에 맞게 특별히 작성 하 고 중요 한 비즈니스 기능을 완료 하는 데 의존 하는 lob (기간 업무) 응용 프로그램을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89dbd-105">The Teams Tenant Apps Catalog lets you distribute line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions.</span></span>

<span data-ttu-id="89dbd-106">조직에 대 한 앱을 게시 하려면 전역 관리자 또는 팀 서비스 관리자 역할이 있는 계정을 사용 하 여 팀 클라이언트에 로그인 한 후 아래 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="89dbd-106">To publish apps for your organization, sign in to your Teams client using an account with the global admin or teams service admin roles and then follow the instructions below.</span></span>

## <a name="publish-an-app-in-the-tenant-apps-catalog-from-the-teams-client"></a><span data-ttu-id="89dbd-107">팀 클라이언트에서 테 넌 트 앱 카탈로그에 앱 게시</span><span class="sxs-lookup"><span data-stu-id="89dbd-107">Publish an app in the Tenant Apps Catalog from the Teams client</span></span>

> [!NOTE]
> <span data-ttu-id="89dbd-108">조직의 앱을 게시 하는 데 전역 관리자 또는 팀 서비스 관리자 역할이 설정 된 계정을 사용 하 여 Microsoft 팀 클라이언트에 로그인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89dbd-108">You need to be signed in to the Microsoft Teams client with an account that has either the global admin or teams service admin role enabled to publish apps for your organization.</span></span> <span data-ttu-id="89dbd-109">[관리자 역할을 사용 하 여 팀을 관리](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles)하는 방법에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="89dbd-109">Learn more about [using administrator roles to manage Teams](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles).</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="89dbd-110">팀 앱 패키지 가져오기</span><span class="sxs-lookup"><span data-stu-id="89dbd-110">Get a Teams app package</span></span>

<span data-ttu-id="89dbd-111">팀 앱 패키지는 [팀 앱 Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)를 사용 하 여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="89dbd-111">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="89dbd-112">앱 패키지를 사용 하는 경우 엔터프라이즈 앱 카탈로그에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89dbd-112">Once you have the app package, you can add it to the enterprise app catalog.</span></span> <span data-ttu-id="89dbd-113">테 넌 트에서 모든 사용자는 앱 카탈로그를 볼 수 있지만, 전역 관리자 및 팀 서비스 관리자만이를 게시 및 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89dbd-113">While all users in the tenant can view the app catalog, only global admins and teams service admins have the ability to publish and manage it.</span></span>

### <a name="go-to-the-tenant-apps-catalog"></a><span data-ttu-id="89dbd-114">테 넌 트 앱 카탈로그로 이동</span><span class="sxs-lookup"><span data-stu-id="89dbd-114">Go to the Tenant Apps Catalog</span></span>

<span data-ttu-id="89dbd-115">Microsoft 팀 클라이언트를 시작 하 고 전역 또는 팀 서비스 관리자 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="89dbd-115">Start the Microsoft Teams client and sign in using your global or teams service admin credentials.</span></span> <span data-ttu-id="89dbd-116">앱의 왼쪽에서 **앱** 을 선택 하 고 특정 조직 (이 예제에서는 Contoso)에 대해 이름이 지정 된 새 섹션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="89dbd-116">Select **Apps** on the left side of the app, and then select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="89dbd-117">조직의 사용자는 카탈로그에서 앱을 보고 자신이 구성원으로 속해 있는 팀을 위해 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89dbd-117">Users in your organization can view apps in the catalog and install them for teams of which they are a member.</span></span>

![앱 카탈로그를 보여 주는 팀 앱 스토어의 스크린샷](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a><span data-ttu-id="89dbd-119">테 넌 트 앱 카탈로그에 앱 추가</span><span class="sxs-lookup"><span data-stu-id="89dbd-119">Add an app to the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="89dbd-120">Apps ( **앱** ) 페이지에서**Contoso에 대 한** **사용자 지정 앱** > 업로드 업로드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="89dbd-120">On the **Apps** page, select **Upload a custom app** > **Upload for Contoso**.</span></span>

    ![앱 카탈로그를 보여 주는 팀 앱 스토어의 스크린샷](media/private-app-store-teams-image02.png)

    <span data-ttu-id="89dbd-122">( **또는 my에 대 한 업로드**( *테스트용 로드*라고도 함)를 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89dbd-122">(You can also choose **Upload for me or my teams**, which is called *sideloading*.</span></span> <span data-ttu-id="89dbd-123">테스트용 로드를 통해 팀 또는 선택한 팀 에서만 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89dbd-123">Sideloading makes the app available only to your teams or to teams you select.)</span></span>

2. <span data-ttu-id="89dbd-124">앱 패키지로 이동 하 여 선택한 다음 **열기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="89dbd-124">Navigate to the app package and select it, and then click **Open**.</span></span>

    ![앱 카탈로그를 보여 주는 팀 앱 스토어의 스크린샷](media/private-app-store-teams-image03.png)

<span data-ttu-id="89dbd-126">테 넌 트 앱 카탈로그로 돌아오면 새 엔터프라이즈 앱이 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="89dbd-126">When you go back to your Tenant Apps Catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="89dbd-127">사용자와 조직의 구성원만이 앱 카탈로그에 액세스할 수 있다는 것을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89dbd-127">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-apps-catalog"></a><span data-ttu-id="89dbd-128">테 넌 트 앱 카탈로그에서 앱 업데이트</span><span class="sxs-lookup"><span data-stu-id="89dbd-128">Update an app in the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="89dbd-129">테 넌 트 앱 카탈로그에서 "..."를 선택**합니다**.</span><span class="sxs-lookup"><span data-stu-id="89dbd-129">From your Tenant Apps Catalog, select “**…**”</span></span> <span data-ttu-id="89dbd-130">업데이트 하려는 앱의 오른쪽 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89dbd-130">on the top right of the app you want to update.</span></span>

2. <span data-ttu-id="89dbd-131">업데이트 된 앱 패키지로 이동 하 여 선택한 다음 **열기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="89dbd-131">Navigate to the updated app package and select it, and then click **Open**.</span></span>

    ![앱 카탈로그를 보여 주는 팀 앱 스토어의 스크린샷](media/private-app-store-teams-image04.png)

<span data-ttu-id="89dbd-133">앱이 버전 2.0으로 수정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89dbd-133">The app will be revised to version 2.0.</span></span> <span data-ttu-id="89dbd-134">이 메뉴에서 전체 회사에 대 한 앱을 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89dbd-134">You can also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a><span data-ttu-id="89dbd-135">Office 365 관리 포털을 사용 하 여 테 넌 트 앱 카탈로그 관리</span><span class="sxs-lookup"><span data-stu-id="89dbd-135">Use the Office 365 admin portal to manage the Tenant Apps Catalog</span></span>

<span data-ttu-id="89dbd-136">버그 수정이 필요한 앱이 있는 경우 Microsoft 365 관리 센터 > **팀 관리 센터** > **팀 앱** > **권한 정책** > <정책 이름 (예: "전역 (조직 전체)") > **테 넌 트 > 앱** 은 특정 앱을 차단 하 고 다른 사용자를 모두 허용 하 고 앱을 목록에 추가 하는 등의 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="89dbd-136">If you have apps that need bug fixes, you can temporarily disable apps through the Microsoft 365 admin center > **Teams admin center** > **Teams apps** > **Permission Policies** > <policy name, e.g. "Global (Org-wide default)"> **Tenant apps** > Block specific apps and allow all others and add your app to the list.</span></span>

![앱 카탈로그를 보여 주는 팀 앱 스토어의 스크린샷](media/private-app-store-teams-image05.png)

<span data-ttu-id="89dbd-138">앱을 사용 하지 않도록 설정 하면 앱이 완전히 삭제 되지 않고 사용자가 앱과 상호 작용 하지 못하도록 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="89dbd-138">Disabling an app will block users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="89dbd-139">이러한 컨트롤을 통해 엔터프라이즈에서 앱을 관리할 때 유연성과 제어권을 추가로 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89dbd-139">These controls give you additional flexibility and control when managing apps in your enterprise.</span></span>
