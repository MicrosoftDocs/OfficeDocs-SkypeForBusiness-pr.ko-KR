---
title: Microsoft Teams 예비 환경 관리
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: baluc
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: Microsoft Teams 라이선스가 없는 Microsoft 365 또는 Office 365 사용자는 예비 Teams 라이선스를 시작할 수 있습니다.
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8803219c93a66d7094ce6ca1aa635f1fbff8580e
ms.sourcegitcommit: b39bd1de0219a9e3a3b0c97fc485c9578ddb643c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2021
ms.locfileid: "53230555"
---
# <a name="manage-the-microsoft-teams-exploratory-license"></a><span data-ttu-id="6e510-103">Microsoft Teams의 예비 라이선스 관리</span><span class="sxs-lookup"><span data-stu-id="6e510-103">Manage the Microsoft Teams Exploratory license</span></span>

<span data-ttu-id="6e510-p101">Microsoft Teams Exploratory 환경을 통해 조직에서 Azure AD(Azure Active Directory)를 사용하고 Teams 라이선스가 없는 사용자는 Teams의 탐색 환경을 시작할 수 있습니다. 관리자는 조직의 사용자에 대해 이 기능을 켜거나 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-p101">The Microsoft Teams Exploratory experience lets users in your organization who have Azure Active Directory (Azure AD) and aren't licensed for Teams initiate an exploratory experience of Teams. Admins can switch this feature on or off for users in their organization.</span></span>

## <a name="whats-in-the-teams-exploratory-experience"></a><span data-ttu-id="6e510-106">Teams Exploratory 환경에는 무엇이 있나요?</span><span class="sxs-lookup"><span data-stu-id="6e510-106">What's in the Teams Exploratory experience</span></span>

<span data-ttu-id="6e510-107">관리자가 Teams 예비 환경의 일부로서 보게 될 서비스 계획은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-107">The service plans that an admin will see as part of the Teams Exploratory experience are:</span></span>

- <span data-ttu-id="6e510-108">Exchange Online(플랜 1)</span><span class="sxs-lookup"><span data-stu-id="6e510-108">Exchange Online (Plan 1)</span></span>
- <span data-ttu-id="6e510-109">Microsoft 365 혹은 Office 365에 대한 흐름</span><span class="sxs-lookup"><span data-stu-id="6e510-109">Flow for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="6e510-110">MyAnalytics의 인사이트</span><span class="sxs-lookup"><span data-stu-id="6e510-110">Insights by MyAnalytics</span></span>
- <span data-ttu-id="6e510-111">Microsoft Forms(플랜 E1)</span><span class="sxs-lookup"><span data-stu-id="6e510-111">Microsoft Forms (Plan E1)</span></span>
- <span data-ttu-id="6e510-112">Microsoft Planner</span><span class="sxs-lookup"><span data-stu-id="6e510-112">Microsoft Planner</span></span>
- <span data-ttu-id="6e510-113">Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="6e510-113">Microsoft Search</span></span>
- <span data-ttu-id="6e510-114">Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="6e510-114">Microsoft StaffHub</span></span>
- <span data-ttu-id="6e510-115">Microsoft 365 및 Office 365 E1 SKU용 Microsoft Stream <sup>1</1></span><span class="sxs-lookup"><span data-stu-id="6e510-115">Microsoft Stream for Microsoft 365 and Office 365 E1 SKUs <sup>1</1></span></span>
- <span data-ttu-id="6e510-116">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6e510-116">Microsoft Teams</span></span>
- <span data-ttu-id="6e510-117">Microsoft 365 혹은 Office 365용 모바일 장치 관리</span><span class="sxs-lookup"><span data-stu-id="6e510-117">Mobile Device Management for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="6e510-118">Office 365용 Office 모바일 앱</span><span class="sxs-lookup"><span data-stu-id="6e510-118">Office Mobile Apps for Office 365</span></span>
- <span data-ttu-id="6e510-119">Office Online</span><span class="sxs-lookup"><span data-stu-id="6e510-119">Office Online</span></span>
- <span data-ttu-id="6e510-120">Microsoft 365 혹은 Office 365용 PowerApps</span><span class="sxs-lookup"><span data-stu-id="6e510-120">PowerApps for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="6e510-121">SharePoint Online(플랜 1)</span><span class="sxs-lookup"><span data-stu-id="6e510-121">SharePoint Online (Plan 1)</span></span>
- <span data-ttu-id="6e510-122">Sway</span><span class="sxs-lookup"><span data-stu-id="6e510-122">Sway</span></span>
- <span data-ttu-id="6e510-123">To-Do(플랜 1)</span><span class="sxs-lookup"><span data-stu-id="6e510-123">To-Do (Plan 1)</span></span>
- <span data-ttu-id="6e510-124">화이트보드(플랜 1)</span><span class="sxs-lookup"><span data-stu-id="6e510-124">Whiteboard (Plan 1)</span></span>
- <span data-ttu-id="6e510-125">Yammer Enterprise</span><span class="sxs-lookup"><span data-stu-id="6e510-125">Yammer Enterprise</span></span>

  <span data-ttu-id="6e510-126"><sup>1</sup> Microsoft Stream에서 [모임 녹음/녹화를 위해 비즈니스용 OneDrive 및 SharePoint](tmr-meeting-recording-change.md)로의 변경은 단계별로 접근합니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-126"><sup>1</sup> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach.</span></span> <span data-ttu-id="6e510-127">시작할 때 이 환경을 옵트인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-127">At launch, you'll be able to opt in to this experience.</span></span> <span data-ttu-id="6e510-128">11월에는 Stream을 계속 사용하는 경우 옵트아웃해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-128">In November, you'll have to opt out if you want to continue using Stream.</span></span> <span data-ttu-id="6e510-129">2021년 초에는 모든 고객이 비즈니스용 OneDrive 및 SharePoint를 사용하여 새로운 모임 기록을 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-129">Sometime in early 2021, we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

## <a name="whos-eligible"></a><span data-ttu-id="6e510-130">사용 자격이 있는 사용자</span><span class="sxs-lookup"><span data-stu-id="6e510-130">Who's eligible</span></span>

<span data-ttu-id="6e510-131">사용자는 다음과 같은 경우 Teams 탐색적 경험에 대한 기준을 충족합니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-131">Users fit the criteria for a Teams Exploratory experience if they:</span></span>

- <span data-ttu-id="6e510-132">관리되는 Azure AD 도메인 전자 메일 주소를 포함 니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-132">Have a managed Azure AD domain email address.</span></span>
- <span data-ttu-id="6e510-133">유료 구독이 있는 테넌트에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-133">Belong to a tenant with a paid subscription.</span></span>
- <span data-ttu-id="6e510-134">활성 Teams 라이선스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-134">Do not have an active Teams license.</span></span>
- <span data-ttu-id="6e510-135">라이선스 할당 정책을 만든 테넌트에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-135">Are not in a tenant where a license assignment policy was created.</span></span>

<span data-ttu-id="6e510-136">(Microsoft 365 관리 센터에서) 사용자는 앱과 평가판을 사용할 수 있게 등록하도록 설정을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-136">Users must be enabled to sign up for apps and trials (in the Microsoft 365 admin center).</span></span> <span data-ttu-id="6e510-137">자세한 내용은 이 문서 뒷부분의 [Teams 예비 환경 관리](#manage-the-teams-exploratory-experience)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6e510-137">For more information, see [Manage the Teams Exploratory experience](#manage-the-teams-exploratory-experience), later in this article.</span></span>

## <a name="who-isnt-eligible"></a><span data-ttu-id="6e510-138">사용 자격이 없는 사용자</span><span class="sxs-lookup"><span data-stu-id="6e510-138">Who isn't eligible</span></span>

<span data-ttu-id="6e510-139">다음과 같은 경우 사용자는 기준에 맞지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-139">Users don't fit the criteria if they:</span></span>

- <span data-ttu-id="6e510-140">현재 또는 이전에 유료, 미결제 또는 평가판 라이선스에서 Teams를 보유하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-140">Currently or previously had Teams from a paid, unpaid, or trial license</span></span>
- <span data-ttu-id="6e510-141">하나 이상의 특별 COVID 제안을 사용하거나 받은 테넌트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-141">Are in a tenant that used/received at least one special COVID offer.</span></span>

<span data-ttu-id="6e510-142">사용자가 Syndication 파트너 고객이거나 GCC, GCC High, DoD 또는 EDU 고객인 경우 사용자의 조직은 이 서비스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-142">Your organization isn't eligible for this offer if you're a Syndication Partner Customer or a GCC, GCC High, DoD, or EDU customer.</span></span>

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a><span data-ttu-id="6e510-143">Teams 예비 환경에 등록하는 방법</span><span class="sxs-lookup"><span data-stu-id="6e510-143">How users sign up for the Teams Exploratory experience</span></span>

<span data-ttu-id="6e510-144">적격 사용자는 데스크톱 또는 웹 Teams에 로그인하여 Teams 예비 환경에 등록할 수 있습니다([teams.microsoft.com](https://teams.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="6e510-144">Eligible users can sign up for the Teams Exploratory experience by signing in to Teams from the desktop or web ([teams.microsoft.com](https://teams.microsoft.com)).</span></span> <span data-ttu-id="6e510-145">현재 모바일을 통한 탐색 기능은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-145">At this time, enabling Exploratory through mobile is not supported.</span></span> <span data-ttu-id="6e510-146">로그인 시, 자동으로 라이선스가 할당 되고 조직 내 사용자가 Teams 예비 환경을 처음 시작할 때 테넌트 관리자가 전자 메일 알림을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-146">When they sign up, they'll be assigned this license automatically and the tenant admin will receive an email notification the first time someone in your org starts the Teams Exploratory experience.</span></span>

## <a name="manage-the-teams-exploratory-experience"></a><span data-ttu-id="6e510-147">Teams 예비 환경 관리</span><span class="sxs-lookup"><span data-stu-id="6e510-147">Manage the Teams Exploratory experience</span></span>

<span data-ttu-id="6e510-148">Teams 예비 환경은 개별 최종 사용자가 시작하고 최종 사용자 직원을 대신해 이 서비스를 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-148">The Teams Exploratory experience is meant to be initiated by individual end users, and you can't initiate this offer on behalf of end-user employees.</span></span>

<span data-ttu-id="6e510-149">Teams 예비 환경은 Exchange Online 라이선스와 함께 제공되지만 관리자가 할당할 때까지 사용자에게 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-149">The Teams Exploratory experience comes with an Exchange Online license, but it won't be assigned to the user until the admin assigns it.</span></span> <span data-ttu-id="6e510-150">사용자에게 아직 Exchange 라이선스가 없으며 관리자가 아직 Exchange Online 라이선스를 할당하지 않은 경우, 사용자는 Teams에서 모임을 예약할 수 없으며 Teams의 다른 기능이 표시되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-150">If the user doesn't have an Exchange license already, and the admin has yet to assign the Exchange Online license, the user won't be able to schedule meetings in Teams and might be missing other Teams functionality.</span></span>

<span data-ttu-id="6e510-151">관리자는 **평가판 앱 및 서비스** 스위치를 사용하여 조직 내에서 최종 사용자가 Teams 예비 환경을 실행할 수 있는 기능을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-151">Admins can disable the ability for end users to run the Teams Exploratory experience within their organization by using the **Trial apps and services** switch.</span></span>

### <a name="prevent-users-from-installing-trial-apps-and-services"></a><span data-ttu-id="6e510-152">사용자가 평가판 앱 및 서비스를 설치하지 못하도록 방지</span><span class="sxs-lookup"><span data-stu-id="6e510-152">Prevent users from installing trial apps and services</span></span>

<span data-ttu-id="6e510-153">사용자가 평가판 앱 및 서비스를 설치하는 기능을 해제하여 사용자가 Teams 예비 환경을 실행하지 못하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-153">You can turn off a user's ability to install trial apps and services, which would prevent the user from running the Teams Exploratory experience.</span></span>

1. <span data-ttu-id="6e510-154">Microsoft 365 관리 센터에서 **설정** > **조직 설정** 으로 이동하여 **서비스** 를 선택한 다음 **사용자 소유 앱 및 서비스** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-154">From the Microsoft 365 admin center, go to **Settings** > **Org settings**, select **Services**, and then select **User owned apps and services**.</span></span>

    ![관리 센터의 서비스 페이지](media/iw-trial-services.png)

2. <span data-ttu-id="6e510-156">**사용자가 평가판 앱 및 서비스를 설치하도록 허용** 확인란을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-156">Clear the check mark from **Let users install trial apps and services**.</span></span>

    ![관리 센터의 사용자 소유의 앱과 서비스 페이지](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > <span data-ttu-id="6e510-158">조직에서 Teams 예비 환경을 사용할 수 없는 경우 **사용자가 평가판 앱 및 서비스를 설치하도록 허용** 옵션이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-158">If your organization is ineligible for the Teams Exploratory experience, you won't see the **Let users install trial apps and services** option.</span></span>

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a><span data-ttu-id="6e510-159">Teams를 포함하는 라이선스가 있는 사용자의 상태 관리</span><span class="sxs-lookup"><span data-stu-id="6e510-159">Manage availability for a user with a license that includes Teams</span></span>

<span data-ttu-id="6e510-160">Teams를 포함하는 라이선스가 할당된 사용자는 Teams 예비 환경을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-160">A user who is assigned a license that includes Teams isn't eligible for the Teams Exploratory experience.</span></span> <span data-ttu-id="6e510-161">Teams 서비스 플랜을 사용할 수 있도록 설정한 경우 사용자는 로그인을 하고 Teams를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-161">When the Teams service plan is turned on, the user can sign in and use Teams.</span></span> <span data-ttu-id="6e510-162">서비스 플랜을 사용하지 않도록 설정한 경우 사용자가 로그인할 수 없으며 Teams 예비 환경을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-162">If the service plan is disabled, the user can't sign in and the Teams Exploratory experience isn't available.</span></span> <span data-ttu-id="6e510-163">관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-163">You must have admin privileges.</span></span>

<span data-ttu-id="6e510-164">Teams로의 액세스를 해제하려면:</span><span class="sxs-lookup"><span data-stu-id="6e510-164">To turn off access to Teams:</span></span>

1. <span data-ttu-id="6e510-165">Microsoft 365 관리 센터에서 **사용자** > **활성 사용자** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-165">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="6e510-166">사용자 이름 옆에 있는 상자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-166">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="6e510-167">**제품 라이선스** 행에서 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-167">In the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="6e510-168">**제품 라이선스** 창에서 토글 스위치를 **해제** 로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-168">In the **Product licenses** pane, switch the toggle to **Off**.</span></span>

    ![관리 센터의 제품 라이선스 페이지](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a><span data-ttu-id="6e510-170">Teams 예비 환경을 이미 사용 중인 사용자의 Teams 상태 관리</span><span class="sxs-lookup"><span data-stu-id="6e510-170">Manage Teams availability for users who are already using the Teams Exploratory experience</span></span>

<span data-ttu-id="6e510-p107">Teams Exploratory 환경을 실행하고 있는 경우 해당 라이선스 혹은 서비스 플랜을 제거하여 이 기능을 해제할 수 있습니다. 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-p107">If a user is running the Teams Exploratory experience, you can turn it off by removing the license or service plan. You must have admin privileges.</span></span>

<span data-ttu-id="6e510-173">Teams 예비 환경 라이선스를 해제하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-173">To turn off the Teams Exploratory experience license:</span></span>

1. <span data-ttu-id="6e510-174">Microsoft 365 관리 센터에서 **사용자** > **활성 사용자** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-174">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="6e510-175">사용자 이름 옆에 있는 상자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-175">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="6e510-176">**제품 라이선스** 행에서 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-176">In the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="6e510-177">**제품 라이선스** 창에서 예비 라이선스 토글 스위치를 **해제** 로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-177">In the **Product licenses** pane, switch the toggle for this exploratory license to **Off**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6e510-178">조직에서 첫 번째 사용자가 Teams 예비 환경을 실행한 후 Teams 예비 토글 스위치가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-178">The Teams Exploratory toggle switch will appear after the first user in the organization launches the Teams Exploratory experience.</span></span>

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a><span data-ttu-id="6e510-179">Teams 예비 라이선스가 있는 사용자의 Teams 관리</span><span class="sxs-lookup"><span data-stu-id="6e510-179">Manage Teams for users who have the Teams Exploratory license</span></span>

<span data-ttu-id="6e510-180">정규 유료 라이선스가 있는 사용자를 관리하는 것과 같은 방식으로 Teams 예비 라이선스가 있는 사용자를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-180">You can manage users who have the Teams Exploratory license just like you manage users who have a regular paid license.</span></span> <span data-ttu-id="6e510-181">자세한 내용은 [조직에서 Teams 설정 관리](enable-features-office-365.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6e510-181">For more information, see [Manage Teams settings for your organization](enable-features-office-365.md).</span></span>

### <a name="upgrade-users-from-teams-exploratory"></a><span data-ttu-id="6e510-182">Teams Exploratory에서 사용자 업그레이드</span><span class="sxs-lookup"><span data-stu-id="6e510-182">Upgrade users from Teams Exploratory</span></span>

<span data-ttu-id="6e510-183">Teams Exploratory에서 사용자를 업그레이드하려면 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-183">You must have admin privileges to upgrade users from Teams Exploratory.</span></span> <span data-ttu-id="6e510-184">자세한 내용은 [Teams Exploratory 평가판에서 사용자 업그레이드](upgrade-from-teams-exploratory.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6e510-184">For more information see [Upgrade users from the Teams Exploratory trial](upgrade-from-teams-exploratory.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6e510-185">Teams Exploratory 라이선스가 종료되고 사용자가 Teams를 포함하는 구독으로 즉시 업그레이드되지 않으면 30일의 유예 기간 후에 Teams에 액세스할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-185">If the Teams Exploratory license ends and a user isn't immediately upgraded to a subscription that includes Teams, they lose access to Teams after a 30-days grace period.</span></span> <span data-ttu-id="6e510-186">그 후 30일이 지나면 데이터가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-186">Another 30 days after which, the data is deleted.</span></span> <span data-ttu-id="6e510-187">사용자가 여전히 Azure Active Directory에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-187">The user still exists in Azure Active Directory.</span></span> <span data-ttu-id="6e510-188">Teams 기능을 다시 활성화하기 위해 사용자에게 새 라이선스를 할당하더라도 사용자가 유예 기간 내에 추가되더라도 모든 콘텐츠는 계속 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-188">Once a new license is assigned to the user to enable Teams functionality again, all content will still exist if the user is added within the grace period time frame.</span></span>

### <a name="remove-a-teams-exploratory-license"></a><span data-ttu-id="6e510-189">Teams 예비 라이선스 제거</span><span class="sxs-lookup"><span data-stu-id="6e510-189">Remove a Teams Exploratory license</span></span>

- <span data-ttu-id="6e510-190">PowerShell을 통해 이 라이선스를 제거하려면 [Office 365 PowerShell을 사용하여 사용자 계정에서 라이선스 제거](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6e510-190">If you would like to remove this license by using PowerShell, see: [Remove licenses from user accounts with Office 365 PowerShell](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span></span>

- <span data-ttu-id="6e510-191">관리 포털을 통해 이 라이선스를 제거하려면 [조직에서 사용자 제거](/microsoft-365/admin/add-users/delete-a-user)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6e510-191">If you would like to remove this license through the admin portal, see: [Delete a user from your organization](/microsoft-365/admin/add-users/delete-a-user)</span></span>

## <a name="what-is-the-data-retention-policy"></a><span data-ttu-id="6e510-192">데이터 보존 정책이란 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="6e510-192">What is the data retention policy</span></span>

<span data-ttu-id="6e510-193">[Microsoft 365 구독 정보](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6e510-193">See [Microsoft 365 subscription information](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).</span></span>

## <a name="how-long-does-the-teams-exploratory-experience-last"></a><span data-ttu-id="6e510-194">Teams Exploratory 환경은 얼마나 오래 지속되나요?</span><span class="sxs-lookup"><span data-stu-id="6e510-194">How long does the Teams Exploratory experience last</span></span>

<span data-ttu-id="6e510-195">2021년 초부터 Teams Exploratory는 모든 신규 고객에게 12개월 구독(초기 사용자 등록부터)으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-195">As of early 2021, Teams Exploratory is available as a 12 month subscription (from initial user sign-up) for all new customers.</span></span> <span data-ttu-id="6e510-196">새 Teams Exploratory 구독은 조직의 첫 번째 사용자가 Teams 탐색에 등록할 때 시작되고 12개월 후에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-196">The new Teams Exploratory subscription starts when the first user in an organization signs-up for Teams Exploratory and it will expire after 12 months.</span></span> <span data-ttu-id="6e510-197">동일한 테넌트의 모든 사용자에게 만료 날짜가 적용되며, 첫 번째 사용자의 구독 날짜부터 12개월 기간이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-197">The expiry date will apply to all users in the same tenant as the 12-month term begins on the first user's sign-up date.</span></span>

> [!NOTE]
> <span data-ttu-id="6e510-198">환경의 종료 날짜는 조직 수준에서 구성됩니다. 즉, 동일한 조직의 모든 사용자에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-198">The end date for the experience is configured at an organization level, meaning it will apply to all users in the same organization.</span></span> <span data-ttu-id="6e510-199">예를 들어 사용자 1은 2021년 1월 1일 구독에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-199">For example, User 1 signs up for the subscription on January 1, 2021.</span></span> <span data-ttu-id="6e510-200">그러면 2021년 12월 31일의 구독 종료 날짜가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-200">This initiates a subscription end-date of December 31, 2021.</span></span> <span data-ttu-id="6e510-201">다른 사용자인 사용자 2는 2021년 10월 1일에 구독에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-201">Another user, User 2, signs up for the subscription on October 1, 2021.</span></span> <span data-ttu-id="6e510-202">사용자 2는 조직이 사용자 1과 동일한 구독을 사용 중이기 때문에 종료 날짜가 2021년 12월 31일이 되고 두 달 동안 Teams Exploratory를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-202">User 2 can use Teams Exploratory for two months, as their end-date will be December 31, 2021 because they're under the same organization's subscription as User 1.</span></span>

### <a name="what-should-administrators-do-at-the-end-of-the-12-month-teams-exploratory-experience"></a><span data-ttu-id="6e510-203">12개월 동안의 Teams Exploratory가 끝나면 관리자가 어떤 작업을 해야 하는지</span><span class="sxs-lookup"><span data-stu-id="6e510-203">What should administrators do at the end of the 12 month Teams Exploratory experience</span></span>

<span data-ttu-id="6e510-204">12개월 구독이 종료되는 경우 관리자는 모든 Teams Exploratory 사용자를 Teams가 포함된 유료 라이선스로 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-204">At the end of the 12 month subscription, administrators should convert all Teams Exploratory users to a paid license that includes Teams.</span></span> <span data-ttu-id="6e510-205">사용자의 환경 중단을 방지하기 위해 Teams Exploratory 구독이 만료되기 전에 이 작업을 완료하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-205">It is vital to ensure this is completed before the Teams Exploratory subscription expires to avoid any disruption to user's experience.</span></span>


> [!NOTE]
> <span data-ttu-id="6e510-206">고객은 이전 탐색 평가판 라이선스가 만료된 후 3개월 동안 새로운 탐색 평가판 라이선스를 시작할 수 없으며 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e510-206">Customers will be disabled and blocked from starting a new Exploratory trial licenses for 3 months past the expiration of their previous Exploratory trial license.</span></span>

<span data-ttu-id="6e510-207">자세한 내용은 이 문서에서 [Teams Exploratory 라이선스의 사용자 업그레이드](#upgrade-users-from-teams-exploratory)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6e510-207">For more information, see [Upgrade users from Teams Exploratory](#upgrade-users-from-teams-exploratory), above in this article.</span></span>
