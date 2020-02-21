---
title: Microsoft 팀 테 넌 트 앱 카탈로그에서 앱 게시
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: Microsoft 팀 테 넌 트 앱 카탈로그에서 앱을 게시 하기 위한 지침입니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.publishtenantapps
- ms.teamsadmincenter.apppolicies.publishtenantapps
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f3d4f5937c766c1c4f6f54a6a38872e793a3825
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161617"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-app-catalog"></a><span data-ttu-id="ef627-103">Microsoft 팀 테 넌 트 앱 카탈로그에서 앱 게시</span><span class="sxs-lookup"><span data-stu-id="ef627-103">Publish apps in the Microsoft Teams tenant app catalog</span></span>
=======================================================

<span data-ttu-id="ef627-104">Microsoft 팀 테 넌 트 앱 카탈로그를 사용 하 여 조직에 lob (기간 업무) 응용 프로그램을 테스트 하 고 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef627-104">You can use the Microsoft Teams tenant app catalog to test and distribute line-of-business applications to your organization.</span></span>

<span data-ttu-id="ef627-105">팀 테 넌 트 앱 카탈로그를 사용 하면 조직에 맞게 특별히 빌드되고 중요 한 비즈니스 기능을 완료 하는 데 의존 하는 lob (기간 업무) 응용 프로그램을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef627-105">The Teams tenant app catalog lets you distribute line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions.</span></span>

<span data-ttu-id="ef627-106">조직에 대 한 앱을 게시 하려면 전역 관리자 또는 팀 서비스 관리자 역할이 있는 계정을 사용 하 여 팀 클라이언트에 로그인 한 후 아래 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="ef627-106">To publish apps for your organization, sign in to the Teams client using an account with either the global admin or teams service admin role and then follow the steps below.</span></span>

## <a name="publish-an-app-in-the-tenant-app-catalog-from-the-teams-client"></a><span data-ttu-id="ef627-107">팀 클라이언트에서 테 넌 트 앱 카탈로그에 앱 게시</span><span class="sxs-lookup"><span data-stu-id="ef627-107">Publish an app in the tenant app catalog from the Teams client</span></span>

> [!NOTE]
> <span data-ttu-id="ef627-108">이 단계에서는 팀 클라이언트를 사용 하 여 앱을 게시 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef627-108">These steps describe how to publish an app by using the Teams client.</span></span> <span data-ttu-id="ef627-109">Microsoft 팀 관리 센터의 **앱 관리** 페이지에서 앱을 게시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef627-109">You can also publish an app on the **Manage apps** page in the Microsoft Teams admin center.</span></span> <span data-ttu-id="ef627-110">자세히 알아보려면 [팀에서 앱 관리](manage-apps.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ef627-110">To learn more, see [Manage apps in Teams](manage-apps.md).</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="ef627-111">팀 앱 패키지 가져오기</span><span class="sxs-lookup"><span data-stu-id="ef627-111">Get a Teams app package</span></span>

<span data-ttu-id="ef627-112">팀 앱 패키지는 [팀 앱 Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio)를 사용 하 여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ef627-112">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="ef627-113">앱 패키지를 사용 하는 경우 테 넌 트 앱 카탈로그에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef627-113">Once you have the app package, you can add it to the tenant app catalog.</span></span> <span data-ttu-id="ef627-114">조직의 모든 사용자가 앱 카탈로그를 볼 수 있지만, 전역 관리자 및 팀 서비스 관리자만이를 게시 및 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef627-114">While all users in your organization can view the app catalog, only global admins and teams service admins have the ability to publish and manage it.</span></span>

### <a name="go-to-the-tenant-app-catalog"></a><span data-ttu-id="ef627-115">테 넌 트 앱 카탈로그로 이동</span><span class="sxs-lookup"><span data-stu-id="ef627-115">Go to the tenant app catalog</span></span>

<span data-ttu-id="ef627-116">팀을 시작 하 고 전역 또는 팀 서비스 관리자 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef627-116">Start Teams and sign in using your global or teams service admin credentials.</span></span> <span data-ttu-id="ef627-117">앱의 왼쪽에서 **앱** 을 선택 하 고 특정 조직 (이 예제에서는 Contoso)에 대해 이름이 지정 된 새 섹션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef627-117">Select **Apps** on the left side of the app, and then select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="ef627-118">조직의 사용자는 카탈로그에서 앱을 보고 자신이 구성원으로 속해 있는 팀을 위해 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef627-118">Users in your organization can view apps in the catalog and install them for teams of which they are a member.</span></span>

![앱 카탈로그를 보여 주는 팀 앱 스토어의 스크린샷](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-app-catalog"></a><span data-ttu-id="ef627-120">테 넌 트 앱 카탈로그에 앱 추가</span><span class="sxs-lookup"><span data-stu-id="ef627-120">Add an app to the tenant app catalog</span></span>

1. <span data-ttu-id="ef627-121">Apps ( **앱** ) 페이지에서**Contoso에 대 한** **사용자 지정 앱** > 업로드 업로드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef627-121">On the **Apps** page, select **Upload a custom app** > **Upload for Contoso**.</span></span>

    ![앱 카탈로그를 보여 주는 팀 앱 스토어의 스크린샷](media/private-app-store-teams-image02.png)

    <span data-ttu-id="ef627-123">( **또는 my에 대 한 업로드**( *테스트용 로드*라고도 함)를 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef627-123">(You can also choose **Upload for me or my teams**, which is called *sideloading*.</span></span> <span data-ttu-id="ef627-124">테스트용 로드를 통해 팀 또는 선택한 팀 에서만 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef627-124">Sideloading makes the app available only to your teams or to teams you select.)</span></span>

2. <span data-ttu-id="ef627-125">앱 패키지로 이동 하 여 선택한 다음 **열기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef627-125">Navigate to the app package and select it, and then click **Open**.</span></span>

    ![앱 카탈로그를 보여 주는 팀 앱 스토어의 스크린샷](media/private-app-store-teams-image03.png)

<span data-ttu-id="ef627-127">테 넌 트 앱 카탈로그로 돌아오면 새 엔터프라이즈 앱이 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="ef627-127">When you go back to your tenant app catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="ef627-128">사용자와 조직의 구성원만이 앱 카탈로그에 액세스할 수 있다는 것을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef627-128">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-app-catalog"></a><span data-ttu-id="ef627-129">테 넌 트 앱 카탈로그에서 앱 업데이트</span><span class="sxs-lookup"><span data-stu-id="ef627-129">Update an app in the tenant app catalog</span></span>

1. <span data-ttu-id="ef627-130">테 넌 트 앱 카탈로그에서 "..."를 선택**합니다**.</span><span class="sxs-lookup"><span data-stu-id="ef627-130">From your tenant app catalog, select “**…**”</span></span> <span data-ttu-id="ef627-131">업데이트 하려는 앱의 오른쪽 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef627-131">on the top right of the app you want to update.</span></span>

2. <span data-ttu-id="ef627-132">업데이트 된 앱 패키지로 이동 하 여 선택한 다음 **열기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef627-132">Navigate to the updated app package and select it, and then click **Open**.</span></span>

    ![앱 카탈로그를 보여 주는 팀 앱 스토어의 스크린샷](media/private-app-store-teams-image04.png)

<span data-ttu-id="ef627-134">앱이 버전 2.0으로 수정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef627-134">The app will be revised to version 2.0.</span></span> <span data-ttu-id="ef627-135">이 메뉴에서 전체 회사에 대 한 앱을 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef627-135">You can also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-manage-the-tenant-app-catalog"></a><span data-ttu-id="ef627-136">Microsoft 팀 관리 센터를 사용 하 여 테 넌 트 앱 카탈로그 관리</span><span class="sxs-lookup"><span data-stu-id="ef627-136">Use the Microsoft Teams admin center to manage the tenant app catalog</span></span>

<span data-ttu-id="ef627-137">버그 수정이 필요한 앱이 있는 경우 앱 권한 정책에서 사용자 용 앱을 일시적으로 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef627-137">If you have apps that need bug fixes, you can temporarily disable apps for users in an app permission policy.</span></span>

1. <span data-ttu-id="ef627-138">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱** > **권한 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef627-138">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="ef627-139">편집 하려는 앱 권한 정책을 선택 하 고 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef627-139">Select the app permission policy that you want to edit, and then click **Edit**.</span></span>
3. <span data-ttu-id="ef627-140">**테 넌 트 앱**에서 **특정 앱 차단 및 다른 모든 항목 허용**을 선택한 다음 차단 하려는 앱을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef627-140">Under **Tenant apps**, select **Block specific apps and allow all others**, and then add the apps that you want to block.</span></span>

<span data-ttu-id="ef627-141">앱을 사용 하지 않도록 설정 하면 앱이 완전히 삭제 되지 않고 사용자가 앱과 상호 작용 하지 못하도록 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef627-141">Disabling an app blocks users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="ef627-142">이러한 컨트롤을 통해 조직의 앱을 관리할 때 유연성과 제어권을 추가로 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef627-142">These controls give you additional flexibility and control when managing apps in your organization.</span></span>

<span data-ttu-id="ef627-143">자세히 알아보려면 [팀에서 앱 권한 정책 관리](teams-app-permission-policies.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ef627-143">To learn more, see [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>