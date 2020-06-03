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
description: Microsoft Teams 라이선스가 없는 Microsoft 365 또는 Office 365 사용자는 예비 Teams 라이선스를 시작할 수 있습니다.
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
appliesto:
- Microsoft Teams
ms.openlocfilehash: 502bdb8c5e441449680fa383b20f3e570d8a8ecc
ms.sourcegitcommit: ef3cd762e799df43bdcde03363c501d7ca9bb6b3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2020
ms.locfileid: "44489130"
---
<a name="manage-the-microsoft-teams-exploratory-license"></a><span data-ttu-id="03ff4-103">Microsoft Teams의 예비 라이선스 관리</span><span class="sxs-lookup"><span data-stu-id="03ff4-103">Manage the Microsoft Teams Exploratory license</span></span>
=======================================================

<span data-ttu-id="03ff4-104">Microsoft Teams 예비 환경을 통해 조직에서 AAD (Azure Active Directory)를 사용하고 Teams 라이선스가 없는 사용자는 Teams의 예비 환경을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-104">The Microsoft Teams Exploratory experience lets users in your organization who have Azure Active Directory (AAD) and are not licensed for Teams initiate an exploratory experience of Teams.</span></span> <span data-ttu-id="03ff4-105">관리자는 조직의 사용자에 대해 이 기능을 설정 하거나 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-105">Admins can switch this feature on or off for users in their organization.</span></span> <span data-ttu-id="03ff4-106">이전의 [Microsoft 상용 클라우드 평가판](iw-trial-teams.md)은 이제 Teams 예비 환경으로 대체되었습니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-106">The earlier [Microsoft Commercial Cloud Trial](iw-trial-teams.md) is now replaced by The Teams Exploratory experience.</span></span>

## <a name="whats-in-the-teams-exploratory-experience"></a><span data-ttu-id="03ff4-107">Teams의 예비 환경에는 무엇이 있나요?</span><span class="sxs-lookup"><span data-stu-id="03ff4-107">What's in the Teams Exploratory experience?</span></span>

<span data-ttu-id="03ff4-108">관리자가 Teams 예비 환경의 일부로서 보게 될 서비스 계획은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-108">The service plans that an admin will see as part of the Teams Exploratory experience are:</span></span>
 - <span data-ttu-id="03ff4-109">Exchange Online(플랜 1)</span><span class="sxs-lookup"><span data-stu-id="03ff4-109">Exchange Online (Plan 1)</span></span>
 - <span data-ttu-id="03ff4-110">Office 365용 흐름</span><span class="sxs-lookup"><span data-stu-id="03ff4-110">Flow for Office 365</span></span>
 - <span data-ttu-id="03ff4-111">MyAnalytics의 인사이트</span><span class="sxs-lookup"><span data-stu-id="03ff4-111">Insights by MyAnalytics</span></span>
 - <span data-ttu-id="03ff4-112">Microsoft Forms(플랜 E1)</span><span class="sxs-lookup"><span data-stu-id="03ff4-112">Microsoft Forms (Plan E1)</span></span>
 - <span data-ttu-id="03ff4-113">Microsoft Planner</span><span class="sxs-lookup"><span data-stu-id="03ff4-113">Microsoft Planner</span></span>
 - <span data-ttu-id="03ff4-114">Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="03ff4-114">Microsoft Search</span></span>
 - <span data-ttu-id="03ff4-115">Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="03ff4-115">Microsoft StaffHub</span></span>
 - <span data-ttu-id="03ff4-116">O365 E1 SKU용 Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="03ff4-116">Microsoft Stream for O365 E1 SKU</span></span>
 - <span data-ttu-id="03ff4-117">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="03ff4-117">Microsoft Teams</span></span>
 - <span data-ttu-id="03ff4-118">Office 365용 모바일 장치 관리</span><span class="sxs-lookup"><span data-stu-id="03ff4-118">Mobile Device Management for Office 365</span></span>
 - <span data-ttu-id="03ff4-119">Office 365용 Office 모바일 앱</span><span class="sxs-lookup"><span data-stu-id="03ff4-119">Office Mobile Apps for Office 365</span></span> 
 - <span data-ttu-id="03ff4-120">Office Online</span><span class="sxs-lookup"><span data-stu-id="03ff4-120">Office Online</span></span>
 - <span data-ttu-id="03ff4-121">Office 365용 PowerApps</span><span class="sxs-lookup"><span data-stu-id="03ff4-121">PowerApps for Office 365</span></span>
 - <span data-ttu-id="03ff4-122">SharePoint Online(플랜 1)</span><span class="sxs-lookup"><span data-stu-id="03ff4-122">SharePoint Online (Plan 1)</span></span>
 - <span data-ttu-id="03ff4-123">Sway</span><span class="sxs-lookup"><span data-stu-id="03ff4-123">Sway</span></span>
 - <span data-ttu-id="03ff4-124">To-Do(플랜 1)</span><span class="sxs-lookup"><span data-stu-id="03ff4-124">To-Do (Plan 1)</span></span>
 - <span data-ttu-id="03ff4-125">화이트보드(플랜 1)</span><span class="sxs-lookup"><span data-stu-id="03ff4-125">Whiteboard (Plan 1)</span></span>
 - <span data-ttu-id="03ff4-126">Yammer Enterprise</span><span class="sxs-lookup"><span data-stu-id="03ff4-126">Yammer Enterprise</span></span>


## <a name="whos-eligible"></a><span data-ttu-id="03ff4-127">사용 자격이 있는 사용자</span><span class="sxs-lookup"><span data-stu-id="03ff4-127">Who's eligible?</span></span>

<span data-ttu-id="03ff4-128">사용자에게 관리되는 AAD 도메인 전자 메일 주소가 있고 현재 Teams 라이선스가 할당되지 않은 경우 이 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-128">As long as the user has a managed AAD domain email address and currently does not have/haven't been assigned a Teams license, they are eligible for this experience.</span></span> <span data-ttu-id="03ff4-129">예를 들어 사용자에게 Microsoft 365 앱(Teams가 포함되지 않음)이 있는 경우 Teams 예비 환경을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-129">For example, if a user has Microsoft 365 Apps for business (which doesn't include Teams), they're eligible for the Teams Exploratory experience.</span></span>

<span data-ttu-id="03ff4-130">(Microsoft 365 관리 센터에서) 사용자는 앱과 평가판을 사용할 수 있게 등록하도록 설정을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-130">Users must be enabled to sign up for apps and trials (in the Microsoft 365 admin center).</span></span> <span data-ttu-id="03ff4-131">자세한 내용은 이 문서 뒷부분의 [Teams 예비 환경 관리](#manage-the-teams-exploratory-experience)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="03ff4-131">For more information, see [Manage the Teams Exploratory experience](#manage-the-teams-exploratory-experience), later in this article.</span></span> 


## <a name="who-isnt-eligible"></a><span data-ttu-id="03ff4-132">사용 자격이 없는 사용자</span><span class="sxs-lookup"><span data-stu-id="03ff4-132">Who isn't eligible</span></span>

<span data-ttu-id="03ff4-133">사용자가 Syndication 파트너 고객이거나 GCC, GCC High, DoD 또는 EDU 고객인 경우 사용자의 조직은 이 서비스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-133">Your organization isn't eligible for this offer if you're a Syndication Partner Customer or a GCC, GCC High, DoD, or EDU customer.</span></span>


## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a><span data-ttu-id="03ff4-134">Teams 예비 환경에 등록하는 방법</span><span class="sxs-lookup"><span data-stu-id="03ff4-134">How users sign up for the Teams Exploratory experience</span></span>

<span data-ttu-id="03ff4-135">적격 사용자는 Teams에 로그인하여 Teams 예비 환경에 등록할 수 있습니다([teams.microsoft.com](https://teams.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="03ff4-135">Eligible users can sign up for the Teams Exploratory experience by signing in to Teams ([teams.microsoft.com](https://teams.microsoft.com)).</span></span> <span data-ttu-id="03ff4-136">적격 사용자에게는 자동으로 라이선스가 할당 되고 조직 내 사용자가 Teams 예비 환경을 처음 시작할 때 테넌트 관리자가 전자 메일 알림을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-136">They will be assigned this license automatically and the tenant admin will receive an email notification the first time someone in your org starts the Teams Exploratory experience.</span></span>

## <a name="manage-the-teams-exploratory-experience"></a><span data-ttu-id="03ff4-137">Teams 예비 환경 관리</span><span class="sxs-lookup"><span data-stu-id="03ff4-137">Manage the Teams Exploratory experience</span></span>

<span data-ttu-id="03ff4-138">Teams 예비 환경은 개별 최종 사용자가 시작하고 최종 사용자 직원을 대신해 이 서비스를 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-138">The Teams Exploratory experience is meant to be initiated by individual end users, and you may not initiate this offer on behalf of end-user employees.</span></span>

<span data-ttu-id="03ff4-139">Teams 예비 환경은 Exchange Online 라이선스와 함께 제공되지만 관리자가 할당할 때까지 사용자에게 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-139">The Teams Exploratory experience comes with an Exchange Online license but it won't be assigned to the user until the admin assigns it.</span></span> <span data-ttu-id="03ff4-140">사용자에게 아직 Exchange 라이선스가 없으며 관리자가 아직 Exchange Online 라이선스를 할당하지 않은 경우, 사용자는 Teams에서 모임을 예약할 수 없으며 Teams의 다른 기능이 표시되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-140">If the user doesn't have an Exchange license already and the admin has yet to assign the Exchange Online license, the user won't be able to schedule meetings in Teams and may be missing other Teams functionality.</span></span>

<span data-ttu-id="03ff4-141">관리자는 **평가판 앱 및 서비스** 스위치를 사용하여 조직 내에서 최종 사용자가 Teams 예비 환경을 실행할 수 있는 기능을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-141">Admins can disable the ability for end users to run the Teams Exploratory experience within their organization by using the **Trial apps and services** switch.</span></span>


### <a name="prevent-users-from-installing-trial-apps-and-services"></a><span data-ttu-id="03ff4-142">사용자가 평가판 앱 및 서비스를 설치하지 못하도록 방지</span><span class="sxs-lookup"><span data-stu-id="03ff4-142">Prevent users from installing trial apps and services</span></span>

<span data-ttu-id="03ff4-143">사용자가 평가판 앱 및 서비스를 설치하는 기능을 해제하여 사용자가 Teams 예비 환경을 실행하지 못하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-143">You can turn off a user's ability to install trial apps and services, would prevent the user from running the Teams Exploratory experience.</span></span> <span data-ttu-id="03ff4-144">관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-144">You must have admin privileges.</span></span> <span data-ttu-id="03ff4-145">관리자 역할에 대한 자세한 내용은 [Teams를 관리하기 위한 Microsoft Teams 관리자 역할의 활용](teams-exploratory.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03ff4-145">To learn more about admin roles, see [Use Microsoft Teams administrator roles to manage Teams](teams-exploratory.md)</span></span>

1. <span data-ttu-id="03ff4-146">[Microsoft 365 관리 센터](https://portal.office.com/adminportal/home)에서 **설정** > **설정**으로 이동하여 **서비스**를 선택한 다음 **사용자 소유 앱 및 서비스**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-146">From the [Microsoft 365 admin center](https://portal.office.com/adminportal/home), go to **Settings** > **Settings**, select **Services**, and then select **User owned apps and services**.</span></span>

    ![관리 센터의 서비스 페이지 스크린샷](media/iw-trial-services.png)

2. <span data-ttu-id="03ff4-148">**사용자가 평가판 앱 및 서비스를 설치하도록 허용** 확인란을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-148">Clear the **Let users install trial apps and services** check box.</span></span>

    ![관리 센터의 사용자 소유의 앱과 서비스 페이지 스크린샷](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > <span data-ttu-id="03ff4-150">조직에서 Teams 예비 환경을 사용할 수 없는 경우 **사용자가 평가판 앱 및 서비스를 설치하도록 허용** 옵션이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-150">If your organization is ineligible for the Teams Exploratory experience, you won't see the **Let users install trial apps and services** option.</span></span>

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a><span data-ttu-id="03ff4-151">Teams를 포함하는 라이선스가 있는 사용자의 상태 관리</span><span class="sxs-lookup"><span data-stu-id="03ff4-151">Manage availability for a user with a license that includes Teams</span></span>

<span data-ttu-id="03ff4-152">Teams를 포함하는 라이선스가 할당된 사용자는 Teams 예비 환경을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-152">A user who is assigned a license that includes Teams isn't eligible for the Teams Exploratory experience.</span></span> <span data-ttu-id="03ff4-153">Teams 서비스 플랜을 사용할 수 있도록 설정한 경우 사용자는 로그인을 하고 Teams를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-153">When the Teams service plan is turned on, the user can sign in and use Teams.</span></span> <span data-ttu-id="03ff4-154">서비스 플랜을 사용하지 않도록 설정한 경우 사용자가 로그인할 수 없으며 Teams 예비 환경을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-154">If the service plan is disabled, the user can't sign in and the Teams Exploratory experience isn't available.</span></span> <span data-ttu-id="03ff4-155">관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-155">You must have admin privileges.</span></span> 

<span data-ttu-id="03ff4-156">Teams로의 액세스를 해제하려면:</span><span class="sxs-lookup"><span data-stu-id="03ff4-156">To turn off access to Teams:</span></span>

1. <span data-ttu-id="03ff4-157">[Microsoft 365 관리 센터에서](https://portal.office.com/adminportal/home)에서 **사용자** > **활성 사용자**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-157">In the [Microsoft 365 admin center](https://portal.office.com/adminportal/home), select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="03ff4-158">사용자 이름 옆에 있는 상자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-158">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="03ff4-159">우측의 **제품 라이선스** 행에서 **편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-159">On the right, in the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="03ff4-160">**제품 라이선스** 창에서 토글 스위치를 **해제**로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-160">In the **Product licenses** pane, switch the toggle to **Off**.</span></span>

    ![관리 센터의 제품 라이선스 페이지 스크린샷.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a><span data-ttu-id="03ff4-162">Teams 예비 환경을 이미 사용 중인 사용자의 Teams 상태 관리</span><span class="sxs-lookup"><span data-stu-id="03ff4-162">Manage Teams availability for users who are already using the Teams Exploratory experience</span></span>

<span data-ttu-id="03ff4-163">사용자가 Teams 예비 환경을 실행하고 있는 경우 해당 라이선스 혹은 서비스 플랜을 제거하여이 기능을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-163">If a user is running the Teams Exploratory experience, you can turn it off by removing the license or service plan.</span></span> <span data-ttu-id="03ff4-164">관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-164">You must have admin privileges.</span></span> 

<span data-ttu-id="03ff4-165">Teams 예비 환경 라이선스를 해제하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-165">To turn off the the Teams Exploratory experience license:</span></span>

1. <span data-ttu-id="03ff4-166">Microsoft 365 관리 센터에서 **사용자** > **활성 사용자**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-166">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="03ff4-167">사용자 이름 옆에 있는 상자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-167">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="03ff4-168">우측의 **제품 라이선스** 행에서 **편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-168">On the right, in the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="03ff4-169">**제품 라이선스** 창에서 예비 라이선스 토글 스위치를 **해제**로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-169">In the **Product licenses** pane, switch the toggle for this exploratory license to **Off**.</span></span>
   
    >[!Note]
    ><span data-ttu-id="03ff4-170">조직에서 첫 번째 사용자가 Teams 예비 환경을 실행한 후 Teams 예비 토글 스위치가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-170">The Teams Exploratory toggle switch will appear after the first user in the organization launches the Teams Exploratory experience.</span></span>

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a><span data-ttu-id="03ff4-171">Teams 예비 라이선스가 있는 사용자의 Teams 관리</span><span class="sxs-lookup"><span data-stu-id="03ff4-171">Manage Teams for users who have the Teams Exploratory license</span></span>

<span data-ttu-id="03ff4-172">정규 유료 라이선스가 있는 사용자를 관리하는 것과 같은 방식으로 Teams 예비 라이선스가 있는 사용자를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-172">You can manage users who have the Teams Exploratory license just like you manage users who have a regular paid license.</span></span> <span data-ttu-id="03ff4-173">자세한 내용은 [조직에서 Teams 설정 관리](enable-features-office-365.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03ff4-173">For more information, see [Manage Teams settings for your organization](enable-features-office-365.md).</span></span>

### <a name="upgrade-users-from-the-teams-exploratory-license"></a><span data-ttu-id="03ff4-174">Teams 예비 라이선스에서 사용자 업그레이드</span><span class="sxs-lookup"><span data-stu-id="03ff4-174">Upgrade users from the Teams Exploratory license</span></span>

<span data-ttu-id="03ff4-175">Teams 예비 라이선스에서 사용자를 업그레이드하려면(관리자 권한이 필요) 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-175">To upgrade users from the Teams Exploratory license (you must have admin privileges), do the following:</span></span>

1. <span data-ttu-id="03ff4-176">Teams를 포함하는 구독을 구입합니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-176">Purchase a subscription that includes Teams.</span></span>

2. <span data-ttu-id="03ff4-177">사용자의 Teams 예비 구독을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-177">Remove the Teams Exploratory subscription from the user.</span></span>

3. <span data-ttu-id="03ff4-178">새로 구매한 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-178">Assign the newly purchased license.</span></span>

<span data-ttu-id="03ff4-179">자세한 내용은 [Microsoft Teams 서비스 설명](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03ff4-179">For more information, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

> [!NOTE]
> <span data-ttu-id="03ff4-180">Teams 예비 라이선스가 종료되고 사용자가 Teams을 포함하는 구독으로 즉시 업그레이드 되지 않는 경우 사용자의 데이터는 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-180">If the Teams Exploratory license ends and a user isn't immediately upgraded to a subscription that includes Teams, the user data is not removed.</span></span> <span data-ttu-id="03ff4-181">사용자는 여전히 Azure Active Directory에 존재하고 Teams 내의 모든 데이터는 계속 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-181">The user still exists in Azure Active Directory and all data within Teams still remains.</span></span> <span data-ttu-id="03ff4-182">Teams의 기능을 다시 사용할 수 있도록 사용자에게 새 라이선스가 할당되면 모든 콘텐츠가 계속 존재하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-182">Once a new license is assigned to the user to enable Teams functionality again, all content will still exist.</span></span> 

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a><span data-ttu-id="03ff4-183">레거시 Microsoft Teams 상용 클라우드 평가판 라이선스는 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="03ff4-183">What happens to legacy Microsoft Teams Commercial Cloud Trial licenses?</span></span>

<span data-ttu-id="03ff4-184">2020년 2월부로 적격 사용자는 최신 Microsoft Teams 예비 환경을 사용하기 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-184">As of February, 2020, eligible users can begin using the latest Microsoft Teams Exploratory experience.</span></span> <span data-ttu-id="03ff4-185">모든 레거시 Teams 상용 클라우드 평가판 라이선스는 평가판이 만료되기 전에 자동으로 신규 서비스로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-185">All legacy Teams Commercial Cloud Trial licenses will be automatically converted to the new offer before their trial expires.</span></span>

### <a name="remove-a-teams-exploratory-license"></a><span data-ttu-id="03ff4-186">Teams 예비 라이선스 제거</span><span class="sxs-lookup"><span data-stu-id="03ff4-186">Remove a Teams Exploratory license</span></span>

- <span data-ttu-id="03ff4-187">PowerShell을 통해 이 라이선스를 제거하려면 [Office 365 PowerShell을 사용하여 사용자 계정에서 라이선스 제거](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03ff4-187">If you would like to remove this license by using PowerShell, see: [Remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span></span>

- <span data-ttu-id="03ff4-188">관리 포털을 통해 이 라이선스를 제거하려면 [비즈니스용 Office 365의 사용자 라이선스 제거](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/remove-licenses-from-users?view=o365-worldwide)를 참조하세요. </span><span class="sxs-lookup"><span data-stu-id="03ff4-188">If you would like to remove this license through the admin portal, see: [Remove licenses from users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/remove-licenses-from-users?view=o365-worldwide)</span></span>

## <a name="how-long-does-the-teams-exploratory-experience-last"></a><span data-ttu-id="03ff4-189">Teams 예비 환경은 얼마나 오래 지속되나요?</span><span class="sxs-lookup"><span data-stu-id="03ff4-189">How long does the Teams Exploratory experience last?</span></span>

<span data-ttu-id="03ff4-190">Microsoft Teams의 예비 환경은 다음 엔터프라이즈 **계약 기념일** 또는 2021년 1월 이후에 **갱신**될 때까지 추가 비용 없이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-190">The Microsoft Teams Exploratory experience is available at no additional cost until your next **agreement anniversary** or **renewal** on or after January 2021.</span></span> <span data-ttu-id="03ff4-191">이 경우 Microsoft 예비 환경 라이선스의 최종 사용자는 Teams가 포함된 유료 라이선스로 전환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-191">At that time, end users on a Microsoft Exploratory experience license will need to move to a paid license that includes Teams.</span></span> <span data-ttu-id="03ff4-192">그 이후에 시작된 모든 Microsoft 예비 환경 라이선스는 다음 **기념일** 또는 **갱신** 주기까지 추가 비용 없이 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-192">Any Microsoft Exploratory experience licenses initiated after that will remain available at no additional cost until your next **anniversary** or **renewal** cycle.</span></span> 

### <a name="what-happens-if-an-end-user-initiates-the-microsoft-teams-exploratory-experience-just-before-my-anniversary-or-renewal-date"></a><span data-ttu-id="03ff4-193">최종 사용자가 기념일 또는 갱신 날짜 직전에 Microsoft Teams 예비 환경을 시작하는 경우 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="03ff4-193">What happens if an end user initiates the Microsoft Teams Exploratory experience just before my anniversary or renewal date?</span></span>

<span data-ttu-id="03ff4-194">**계약 기념일** 또는 **갱신** 후 90일 이내에 시작된 Microsoft Teams 예비 환경 라이선스는 다음 기념일 또는 갱신 주기까지 유료 라이선스로 전환할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-194">Microsoft Teams Exploratory experience licenses initiated within 90 days of your **agreement anniversary** or **renewal** will not be required to move to a paid license until the subsequent anniversary or renewal cycle.</span></span> 

### <a name="what-if-my-agreement-doesnt-have-an-anniversary-or-yearly-renewal-date-for-example-month-to-month-agreements"></a><span data-ttu-id="03ff4-195">계약서에 주기 혹은 연간 갱신 날짜가 없는 경우 어떻게 하나요(예: 월 단위 계약)</span><span class="sxs-lookup"><span data-stu-id="03ff4-195">What if my agreement doesn’t have an anniversary or yearly renewal date (for example, month-to-month agreements)?</span></span>

<span data-ttu-id="03ff4-196">주기 또는 연간 갱신 날짜가 없는 계약서의 경우, 첫 번째 최종 사용자가 Microsoft Teams Exploratory 환경 라이선스를 정품 인증한 다음의 년도가 기념일 또는 갱신 날짜로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-196">For agreements without an anniversary or yearly renewal date, the subsequent year after the first end user activates the Microsoft Teams Exploratory experience licenses will be treated as the anniversary or renewal date.</span></span> <span data-ttu-id="03ff4-197">위에 간략히 설명한 정책에 따라 Microsoft Teams Exploratory 라이선스를 사용하는 사용자는 각 해 해당일까지 유료 라이선스로 전환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-197">Users on the Microsoft Teams Exploratory license must be converted to a paid license by that date each year, according to the policies outlined above.</span></span>

<span data-ttu-id="03ff4-198">예를 들어, 첫 번째 최종 사용자가 Microsoft Teams Exploratory 라이선스를 2020년 6월 19일에 정품 인증을 하면, 해당 사용자와 고객 테넌트에 있는 다른 모든 적격 사용자는 2021년 6월 19일까지 유료 라이선스로 전환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03ff4-198">For example, if the first end user activates Microsoft Teams Exploratory on June 19, 2020, then they and all other eligible users in the customer tenant must convert to a paid license with Teams by June 19, 2021.</span></span> 

