---
title: Microsoft Teams 예비 환경 관리
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: baluc
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: Microsoft Teams 라이선스가 없는 Office 365 사용자는 예비 Teams 라이선스를 시작할 수 있습니다.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6777dfbafac89c798955245b93f1e4537093b0cf
ms.sourcegitcommit: 96d98e145ff300833d827a7d43b4e4b0331b7538
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871791"
---
<a name="manage-the-microsoft-teams-exploratory-license"></a><span data-ttu-id="972c6-103">Microsoft Teams의 예비 라이선스 관리</span><span class="sxs-lookup"><span data-stu-id="972c6-103">Manage the Microsoft Teams Exploratory license</span></span>
=======================================================

<span data-ttu-id="972c6-104">Microsoft Teams 예비 환경을 통해 조직에서 AAD (Azure Active Directory)를 사용하고 Teams 라이선스가 없는 사용자는 Teams의 예비 환경을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-104">The Microsoft Teams Exploratory experience lets users in your organization who have Azure Active Directory (AAD) and are not licensed for Teams initiate an exploratory experience of Teams.</span></span> <span data-ttu-id="972c6-105">관리자는 조직의 사용자에 대해 이 기능을 설정 하거나 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-105">Admins can switch this feature on or off for users in their organization.</span></span> <span data-ttu-id="972c6-106">이전의 [Microsoft 상용 클라우드 평가판](iw-trial-teams.md)은 이제 Teams 예비 환경이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-106">The earlier [Microsoft Commercial Cloud Trial](iw-trial-teams.md) is now called The Teams Exploratory experience.</span></span>

<span data-ttu-id="972c6-107">[!INCLUDE [preview-feature](includes/preview-feature.md)] 이 환경은 2020년 1월 중순부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-107">[!INCLUDE [preview-feature](includes/preview-feature.md)] This experience will be available starting in mid January, 2020.</span></span>

## <a name="whats-in-the-teams-exploratory-experience"></a><span data-ttu-id="972c6-108">Teams의 예비 환경에는 무엇이 있나요?</span><span class="sxs-lookup"><span data-stu-id="972c6-108">What's in the Teams Exploratory experience?</span></span>

<span data-ttu-id="972c6-109">Teams의 예비 환경에 포함된 서비스 플랜은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-109">The service plans included in the Teams Exploratory experience are:</span></span>
 - <span data-ttu-id="972c6-110">Exchange Online(플랜 1)</span><span class="sxs-lookup"><span data-stu-id="972c6-110">Exchange Online (Plan 1)</span></span>
 - <span data-ttu-id="972c6-111">Office 365용 흐름</span><span class="sxs-lookup"><span data-stu-id="972c6-111">Flow for Office 365 Plan 1</span></span>
 - <span data-ttu-id="972c6-112">MyAnalytics의 인사이트</span><span class="sxs-lookup"><span data-stu-id="972c6-112">Insights by MyAnalytics</span></span>
 - <span data-ttu-id="972c6-113">Microsoft Forms(플랜 E1)</span><span class="sxs-lookup"><span data-stu-id="972c6-113">Microsoft Forms (Plan E1)</span></span>
 - <span data-ttu-id="972c6-114">Microsoft Planner</span><span class="sxs-lookup"><span data-stu-id="972c6-114">Microsoft Planner</span></span>
 - <span data-ttu-id="972c6-115">Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="972c6-115">Microsoft Search</span></span>
 - <span data-ttu-id="972c6-116">Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="972c6-116">Microsoft StaffHub</span></span>
 - <span data-ttu-id="972c6-117">O365 E1 SKU용 Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="972c6-117">Microsoft Stream for O365 E1 SKU</span></span>
 - <span data-ttu-id="972c6-118">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="972c6-118">Welcome to Microsoft Teams</span></span>
 - <span data-ttu-id="972c6-119">Office 365용 모바일 장치 관리</span><span class="sxs-lookup"><span data-stu-id="972c6-119">Mobile Device Management for Office 365</span></span>
 - <span data-ttu-id="972c6-120">Office 365용 Office 모바일 앱</span><span class="sxs-lookup"><span data-stu-id="972c6-120">Office Mobile Apps for Office 365</span></span> 
 - <span data-ttu-id="972c6-121">Office Online</span><span class="sxs-lookup"><span data-stu-id="972c6-121">Office Online</span></span>
 - <span data-ttu-id="972c6-122">Office 365용 PowerApps</span><span class="sxs-lookup"><span data-stu-id="972c6-122">PowerApps for Office 365 Plan 1</span></span>
 - <span data-ttu-id="972c6-123">SharePoint Online(플랜 1)</span><span class="sxs-lookup"><span data-stu-id="972c6-123">SharePoint Online (Plan 1)</span></span>
 - <span data-ttu-id="972c6-124">Sway</span><span class="sxs-lookup"><span data-stu-id="972c6-124">Sway</span></span>
 - <span data-ttu-id="972c6-125">To-Do(플랜 1)</span><span class="sxs-lookup"><span data-stu-id="972c6-125">To-Do (Plan 1)</span></span>
 - <span data-ttu-id="972c6-126">화이트보드(플랜 1)</span><span class="sxs-lookup"><span data-stu-id="972c6-126">Whiteboard (Plan 1)</span></span>
 - <span data-ttu-id="972c6-127">Yammer Enterprise</span><span class="sxs-lookup"><span data-stu-id="972c6-127">Yammer Enterprise</span></span>


## <a name="whos-eligible"></a><span data-ttu-id="972c6-128">사용 자격이 있는 사용자</span><span class="sxs-lookup"><span data-stu-id="972c6-128">Who's eligible?</span></span>

<span data-ttu-id="972c6-129">(Microsoft 365 관리 센터에서) 사용자는 앱과 평가판을 사용할 수 있게 등록하도록 설정을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-129">Users must be enabled to sign up for apps and trials (in the Microsoft 365 admin center).</span></span> <span data-ttu-id="972c6-130">자세한 내용은 이 문서 뒷부분의 [Teams 예비 환경 관리](#manage-the-teams-exploratory-experience)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="972c6-130">For more information, see [Manage the trial](#manage-the-teams-exploratory-experience), later in this article.</span></span> 

<span data-ttu-id="972c6-131">Teams를 포함하는 Office 365 라이선스가 없는 사용자는 Teams 예비 환경을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-131">Users who do not have an Office 365 license that includes Teams can initiate the Microsoft Teams Commercial Cloud Trial offer.</span></span> <span data-ttu-id="972c6-132">예를 들어 사용자에게 Office 365 Business(Teams가 포함되지 않음)가 있는 경우 Teams 예비 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-132">For example, if a user has Office 365 Business (which doesn't include Teams), they are eligible for the trial.</span></span>

## <a name="who-isnt-eligible"></a><span data-ttu-id="972c6-133">사용 자격이 없는 사용자</span><span class="sxs-lookup"><span data-stu-id="972c6-133">Who isn't eligible</span></span>

<span data-ttu-id="972c6-134">사용자가 Syndication 파트너 고객이거나 GCC, GCC High, DoD 또는 EDU 고객인 경우 사용자의 조직은 이 서비스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-134">Your organization is not eligible for the trial if you are a Syndication Partner Customer or if you are a GCC, GCC High, DoD, or EDU customer.</span></span>


## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a><span data-ttu-id="972c6-135">Teams 예비 환경에 등록하는 방법</span><span class="sxs-lookup"><span data-stu-id="972c6-135">How users sign up for the Teams Exploratory experience</span></span>

<span data-ttu-id="972c6-136">적격 사용자는 Teams에 로그인하여 Teams 예비 환경에 등록할 수 있습니다([teams.microsoft.com](https://teams.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="972c6-136">Eligible users can sign up for the trial offer by signing in to Teams ([teams.microsoft.com](https://teams.microsoft.com)).</span></span> <span data-ttu-id="972c6-137">적격 사용자에게는 자동으로 라이선스가 할당 되고 조직 내 사용자가 Teams 예비 환경을 처음 시작할 때 테넌트 관리자가 전자 메일 알림을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-137">They will be assigned this license automatically and the tenant admin will receive an email notification the first time someone in your org starts the Teams Exploratory experience.</span></span>

## <a name="manage-the-teams-exploratory-experience"></a><span data-ttu-id="972c6-138">Teams 예비 환경 관리</span><span class="sxs-lookup"><span data-stu-id="972c6-138">Manage the Teams Exploratory experience</span></span>

<span data-ttu-id="972c6-139">Teams 예비 환경은 개별 최종 사용자가 시작하고 최종 사용자 직원을 대신해 이 서비스를 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-139">The Teams Trial is meant to be initiated by individual end users, and you may not initiate the Teams Trial offer on behalf of end-user employees.</span></span>

<span data-ttu-id="972c6-140">Teams 예비 환경은 Exchange Online 라이선스와 함께 제공되지만 관리자가 할당할 때까지 사용자에게 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-140">The Teams Exploratory experience comes with an Exchange Online license but it won't be assigned to the user until the admin assigns it.</span></span> <span data-ttu-id="972c6-141">사용자에게 아직 Exchange 라이선스가 없으며 관리자가 아직 Exchange Online 라이선스를 할당하지 않은 경우, 사용자는 Teams에서 모임을 예약할 수 없으며 Teams의 다른 기능이 표시되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-141">If the user doesn't have an Exchange license already and the admin has yet to assign the Exchange Online license, the user won't be able to schedule meetings in Teams and may be missing other Teams functionality.</span></span>

<span data-ttu-id="972c6-142">관리자는 **평가판 앱 및 서비스** 스위치를 사용하여 조직 내에서 최종 사용자가 Teams 예비 환경을 실행할 수 있는 기능을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-142">Admins can disable the ability for end users to run the Teams Exploratory experience within their organization by using the **Trial apps and services** switch.</span></span>


### <a name="prevent-users-from-installing-trial-apps-and-services"></a><span data-ttu-id="972c6-143">사용자가 평가판 앱 및 서비스를 설치하지 못하도록 방지</span><span class="sxs-lookup"><span data-stu-id="972c6-143">Prevent users from installing trial apps and services</span></span>

<span data-ttu-id="972c6-144">사용자가 평가판 앱 및 서비스를 설치하는 기능을 해제하여 사용자가 Teams 예비 환경을 실행 하지 못하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-144">You can turn off a user’s ability to install trial apps and services, would prevent the user from running the Teams Exploratory experience.</span></span>

1. <span data-ttu-id="972c6-145">[Microsoft 365 관리 센터](https://portal.office.com/adminportal/home)에서 **설정** > **서비스 & 추가 기능** > **사용자 소유의 앱 및 서비스**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-145">From the [Microsoft 365 admin center](https://portal.office.com/adminportal/home), go to **Settings** > **Services & add-ins** > **User owned Apps and Services**.</span></span>

    ![관리 센터의 서비스 & 추가 기능 페이지 스크린샷](media/iw-trial-enable-1.png)

2. <span data-ttu-id="972c6-147">**사용자가 평가판 앱 및 서비스를 설치하도록 허용**을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-147">Turn off **Let users install trial apps and services**.</span></span>

    ![관리 센터의 사용자 소유의 앱 & 서비스 페이지 스크린샷](media/iw-trial-enable-2.png)
> [!NOTE]
> <span data-ttu-id="972c6-149">조직에서 Teams 예비 환경을 사용할 수 없는 경우 **사용자가 평가판 앱 및 서비스를 설치하도록 허용** 스위치가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-149">If your organization is ineligible for the Microsoft Teams Commercial Cloud Trial offer, you will not see the **Let users install trial apps and services** switch.</span></span>

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a><span data-ttu-id="972c6-150">Teams를 포함하는 라이선스가 있는 사용자의 상태 관리</span><span class="sxs-lookup"><span data-stu-id="972c6-150">Manage trial availability for a user with a license that includes Teams</span></span>

<span data-ttu-id="972c6-151">Teams를 포함하는 라이선스가 할당된 사용자는 Teams 예비 환경을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-151">A user who is assigned a license that includes Teams is not eligible for the trial.</span></span> <span data-ttu-id="972c6-152">Teams 서비스 플랜을 사용할 수 있도록 설정한 경우 사용자는 로그인을 하고 Teams를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-152">When the Teams service plan is enabled, the user can sign in and use Teams.</span></span> <span data-ttu-id="972c6-153">서비스 플랜을 사용하지 않도록 설정한 경우 사용자가 로그인할 수 없으며 Teams 예비 환경을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-153">If the service plan is disabled, the user can't sign in and the Teams Exploratory experience isn't available.</span></span>

<span data-ttu-id="972c6-154">Teams로의 액세스를 해제하려면:</span><span class="sxs-lookup"><span data-stu-id="972c6-154">To turn off access to Teams:</span></span>

1. <span data-ttu-id="972c6-155">Microsoft 365 관리 센터에서 **사용자** > **활성 사용자**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-155">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="972c6-156">사용자 이름 옆에 있는 상자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-156">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="972c6-157">우측의 **제품 라이선스** 행에서 **편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-157">On the right, in the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="972c6-158">**제품 라이선스** 창에서 토글 스위치를 **해제**로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-158">In the **Product licenses** pane, switch the toggle to **Off**.</span></span>

    ![관리 센터의 제품 라이선스 페이지 스크린샷.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a><span data-ttu-id="972c6-160">Teams 예비 환경을 이미 사용 중인 사용자의 Teams 상태 관리</span><span class="sxs-lookup"><span data-stu-id="972c6-160">Manage Teams availability for users who are already using the Teams Exploratory experience</span></span>

<span data-ttu-id="972c6-161">사용자가 Teams 예비 환경을 실행하고 있는 경우 해당 라이선스 혹은 서비스 플랜을 제거하여이 기능을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-161">If a user is running the Teams Exploratory experience, you can turn it off by removing the license or service plan.</span></span>

<span data-ttu-id="972c6-162">Teams 예비 환경 라이선스를 해제하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-162">To turn off the the Teams Exploratory experience license:</span></span>

1. <span data-ttu-id="972c6-163">Microsoft 365 관리 센터에서 **사용자** > **활성 사용자**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-163">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="972c6-164">사용자 이름 옆에 있는 상자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-164">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="972c6-165">우측의 **제품 라이선스** 행에서 **편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-165">On the right, in the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="972c6-166">**제품 라이선스** 창에서 예비 라이선스 토글 스위치를 **해제**로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-166">In the **Product licenses** pane, switch the toggle to **Off**.</span></span>

    
>[!Note]
><span data-ttu-id="972c6-167">조직에서 첫 번째 사용자가 Teams 예비 환경을 실행한 후 Teams 예비 토글 스위치가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-167">The Teams Exploratory toggle switch will appear after the first user in the organization launches the Teams Exploratory experience.</span></span>

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a><span data-ttu-id="972c6-168">Teams 예비 라이선스가 있는 사용자의 Teams 관리</span><span class="sxs-lookup"><span data-stu-id="972c6-168">Manage Teams for users who have the trial license</span></span>

<span data-ttu-id="972c6-169">정규 유료 라이선스가 있는 사용자를 관리하는 것과 같은 방식으로 Teams 예비 라이선스가 있는 사용자를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-169">You can manage users who have a trial license just like you manage users who have a regular paid license.</span></span> <span data-ttu-id="972c6-170">자세한 내용은 [조직에서 Teams 설정 관리](enable-features-office-365.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="972c6-170">For more information, see [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

### <a name="upgrade-users-from-the-teams-exploratory-license"></a><span data-ttu-id="972c6-171">Teams 예비 라이선스에서 사용자 업그레이드</span><span class="sxs-lookup"><span data-stu-id="972c6-171">Upgrade users from the trial license</span></span>

<span data-ttu-id="972c6-172">Teams 예비 라이선스에서 사용자를 업그레이드하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-172">To upgrade users from the trial license, do the following:</span></span>

1. <span data-ttu-id="972c6-173">Teams를 포함하는 구독을 구입합니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-173">Purchase a subscription that includes Teams.</span></span>

2. <span data-ttu-id="972c6-174">사용자의 Teams 예비 구독을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-174">Remove the Teams trial subscription from the user.</span></span>

3. <span data-ttu-id="972c6-175">새로 구매한 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-175">Assign the newly purchased license.</span></span>

<span data-ttu-id="972c6-176">자세한 내용은 [Microsoft Teams 사용을 위한 Office 365 라이선싱](Office-365-licensing.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="972c6-176">For more information, see [Office 365 licensing for Microsoft Teams](Office-365-licensing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="972c6-177">Teams 예비 라이선스가 종료되고 사용자가 Teams을 포함하는 구독으로 즉시 업그레이드 되지 않는 경우 사용자의 데이터는 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-177">If the trial ends and a user is not immediately upgraded to a subscription that includes teams, the user data is not removed.</span></span> <span data-ttu-id="972c6-178">사용자는 여전히 Azure Active Directory에 존재하고 Teams 내의 모든 데이터는 계속 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-178">The user still exists in Azure Active Directory and all data within Teams still remains.</span></span> <span data-ttu-id="972c6-179">Teams의 기능을 다시 사용할 수 있도록 사용자에게 새 라이선스가 할당되면 모든 콘텐츠가 계속 존재하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-179">Once a new license is assigned to the user to enable Teams functionality again, all content will still exist.</span></span> 

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a><span data-ttu-id="972c6-180">레거시 Microsoft Teams 상용 클라우드 평가판 라이선스는 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="972c6-180">What happens to legacy Microsoft Teams Commercial Cloud Trial licenses?</span></span>

<span data-ttu-id="972c6-181">2020년 1월 중순부로 적격 사용자는 최신 Microsoft Teams 예비 환경을 사용하기 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-181">As of mid January, 2020, eligible users can begin using the latest Microsoft Teams Exploratory experience.</span></span> <span data-ttu-id="972c6-182">모든 레거시 Teams 상용 클라우드 평가판 라이선스는 평가판이 만료되기 전에 자동으로 신규 서비스로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="972c6-182">All legacy Teams Commercial Cloud Trial licenses will be automatically converted to the new offer before their trial expires.</span></span>

### <a name="remove-a-teams-exploratory-license"></a><span data-ttu-id="972c6-183">Teams 예비 라이선스 제거</span><span class="sxs-lookup"><span data-stu-id="972c6-183">Remove a Teams Exploratory license</span></span>

- <span data-ttu-id="972c6-184">PowerShell을 통해 이 라이선스를 제거하려면 [Office 365 PowerShell을 사용하여 사용자 계정에서 라이선스 제거](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="972c6-184">If you would like to remove this license via PowerShell, see: [Remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span></span>

- <span data-ttu-id="972c6-185">관리 포털을 통해 이 라이선스를 제거하려면 [비즈니스용 Office 365의 사용자 라이선스 제거](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/remove-licenses-from-users?view=o365-worldwide)를 참조하세요. </span><span class="sxs-lookup"><span data-stu-id="972c6-185">If you would like to remove this license through the admin portal, see: [Remove licenses from users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/remove-licenses-from-users?view=o365-worldwide)</span></span>
