---
title: Microsoft 팀에 대 한 사용자 액세스 관리
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: 조직의 사용자에 게 팀 라이선스를 할당 하거나 제거 하 여 팀에 대 한 사용자 액세스를 관리 하는 방법을 알아봅니다.
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6d877a4c6534c76b894583401dc5dba0936c3c75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521385"
---
# <a name="manage-user-access-to-teams"></a><span data-ttu-id="bd232-103">Teams에 대한 사용자 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="bd232-103">Manage user access to Teams</span></span>

<span data-ttu-id="bd232-104">Microsoft 팀 제품 라이선스를 할당 하거나 제거 하 여 사용자 수준에서 팀에 대 한 액세스를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd232-104">You manage access to Teams at the user level by assigning or removing a Microsoft Teams product license.</span></span> <span data-ttu-id="bd232-105">조직의 각 사용자는 팀을 사용할 수 있으려면 팀 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd232-105">Each user in your organization must have a Teams license before they can use Teams.</span></span> <span data-ttu-id="bd232-106">새 사용자 계정이 만들어지거나 기존 계정이 있는 사용자에 게 팀 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd232-106">You can assign a Teams license for new users when new user accounts are created or to users with existing accounts.</span></span>

<span data-ttu-id="bd232-107">기본적으로 라이선스 계획 (예: Microsoft 365 Enterprise E3 또는 Microsoft 365 Business Premium)을 사용자에 게 할당 하면 팀 라이선스가 자동으로 할당 되며 사용자가 팀을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd232-107">By default, when a licensing plan (for example, Microsoft 365 Enterprise E3 or Microsoft 365 Business Premium)  is assigned to a user, a Teams license is automatically assigned, and the user is enabled for Teams.</span></span> <span data-ttu-id="bd232-108">언제 든 지 라이선스를 제거 하거나 할당 하 여 사용자의 팀을 사용 하지 않도록 설정 하거나 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd232-108">You can disable or enable Teams for a user by removing or assigning a license at any time.</span></span>

<span data-ttu-id="bd232-109">팀 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">관리 센터</a>에서 관리 되는 메시징 정책을 사용 하 여 팀의 사용자가 사용할 수 있는 채팅 및 채널 메시징 기능을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd232-109">Use messaging policies, managed from the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams Admin Center</a>, to control what chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="bd232-110">기본 정책을 사용 하거나 조직의 사용자를 위해 하나 이상의 사용자 지정 메시징 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd232-110">You can use the default policy or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="bd232-111">자세한 내용은 [팀에서 메시징 정책 관리](messaging-policies-in-teams.md)를 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="bd232-111">To learn more, read [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>
<span data-ttu-id="bd232-112">Microsoft 365 관리 센터에서 또는 PowerShell을 사용 하 여 팀 라이선스를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd232-112">You manage Teams licenses in the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="bd232-113">라이선스를 관리 하려면 전역 관리자 또는 사용자 관리 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd232-113">You must be a Global admin or User management admin to manage licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="bd232-114">팀이 프로젝트 및 기타 동적 이니셔티브에 organically 수 있도록 모든 사용자에 대해 팀을 사용 하도록 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bd232-114">We recommend that you enable Teams for all users so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="bd232-115">파일럿을 실행 하는 경우에도 팀을 모든 사용자에 게 사용 하도록 설정 하는 것이 좋지만, 사용자의 파일럿 그룹에 대 한 대상 통신만을 유지 하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd232-115">Even if you're running a pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="bd232-116">Microsoft 365 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="bd232-116">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="bd232-117">팀 사용자 수준 라이선스는 Microsoft 365 관리 센터 사용자 관리 인터페이스를 통해 직접 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd232-117">Teams user-level licenses are managed directly through the Microsoft 365 admin center user management interfaces.</span></span> <span data-ttu-id="bd232-118">관리자는 새 사용자 계정이 만들어지거나 기존 계정이 있는 사용자에 게 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd232-118">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="bd232-119">관리자가 Microsoft 팀 라이선스를 관리 하려면 전역 관리자 또는 사용자 관리 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd232-119">The administrator must have Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>
<span data-ttu-id="bd232-120">Microsoft 365 관리 센터를 사용 하 여 개별 사용자 또는 소규모 사용자 집합에 대 한 팀 라이선스를 한 번에 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd232-120">Use the Microsoft 365 admin center to manage Teams licenses for individual users or small sets of users at a time.</span></span> <span data-ttu-id="bd232-121">**라이선스** 페이지 (한 번에 최대 20 명의 사용자) 또는 **활성 사용자** 페이지에서 팀 라이선스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd232-121">You can manage Teams licenses on the **Licenses** page (for up to 20 users at at time) or **Active users** page.</span></span> <span data-ttu-id="bd232-122">특정 사용자에 대 한 제품 라이선스를 관리 하거나 특정 제품에 대 한 사용자 라이선스를 관리할 것인지 여부에 따라 다른 방법이 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd232-122">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="bd232-123">수백 또는 수천 명의 사용자와 같이 많은 사용자의 팀 라이선스를 관리 해야 하는 경우 Powershell 또는 azure [Active Directory (AZURE AD)의 그룹 기반 라이선스](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)를 [사용](#using-powershell) 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd232-123">If you need to manage Teams licenses for a large number of users, such as hundreds or thousands of users, [use Powershell](#using-powershell) or [group-based licensing in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span> 

### <a name="assign-a-teams-license"></a><span data-ttu-id="bd232-124">팀 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="bd232-124">Assign a Teams license</span></span>

<span data-ttu-id="bd232-125">단계는 **라이선스** 페이지 또는 **활성 사용자** 페이지 사용 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="bd232-125">The steps are different depending on whether you use the **Licenses** page or **Active users** page.</span></span>  <span data-ttu-id="bd232-126">단계별 지침은 [사용자에 게 라이선스 할당](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bd232-126">For step-by-step instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

|||
|---------|---------|
|![사용자가 사용할 수 있는 팀 라이선스의 스크린샷](media/assign-teams-licenses-1.png)    | ![사용자가 사용할 수 있는 팀 라이선스의 스크린샷](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a><span data-ttu-id="bd232-129">팀 라이선스 제거</span><span class="sxs-lookup"><span data-stu-id="bd232-129">Remove a Teams license</span></span>

<span data-ttu-id="bd232-130">사용자에 게 팀 라이선스를 제거 하면 해당 사용자에 대해 팀이 비활성화 되 고 앱 시작 관리자 또는 홈페이지에 팀이 더 이상 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bd232-130">When you remove a Teams license from a user, Teams is disabled for that user, and they will no longer see Teams in the app launcher or homepage.</span></span> <span data-ttu-id="bd232-131">자세한 단계는 [사용자의 라이선스 할당](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users)해제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bd232-131">For detailed steps, see [Unassign licenses from users](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users).</span></span>

|||
|---------|---------|
|![사용자가 사용할 수 없는 팀 라이선스 스크린샷](media/remove-teams-licenses-1.png)    | ![사용자가 사용할 수 없는 팀 라이선스 스크린샷](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a><span data-ttu-id="bd232-134">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="bd232-134">Using PowerShell</span></span>

<span data-ttu-id="bd232-135">PowerShell을 사용 하 여 사용자의 팀 라이선스를 대량으로 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd232-135">Use PowerShell to manage Teams licenses for users in bulk.</span></span> <span data-ttu-id="bd232-136">다른 서비스 계획 라이선스를 사용할 때와 동일한 방식으로 PowerShell을 통해 팀을 활성화 하거나 비활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd232-136">You enable and disable Teams through PowerShell in the same way that you would for any other service plan license.</span></span> <span data-ttu-id="bd232-137">팀에 대 한 서비스 계획의 식별자가 필요 합니다 (다음과 같습니다).</span><span class="sxs-lookup"><span data-stu-id="bd232-137">You'll need the identifiers for the service plans for Teams, which are as follows:</span></span>

- <span data-ttu-id="bd232-138">Microsoft 팀: TEAMS1</span><span class="sxs-lookup"><span data-stu-id="bd232-138">Microsoft Teams: TEAMS1</span></span>
- <span data-ttu-id="bd232-139">GCC 용 Microsoft 팀: TEAMS_GOV</span><span class="sxs-lookup"><span data-stu-id="bd232-139">Microsoft Teams for GCC: TEAMS_GOV</span></span>
- <span data-ttu-id="bd232-140">DoD에 대 한 Microsoft 팀: TEAMS_DOD</span><span class="sxs-lookup"><span data-stu-id="bd232-140">Microsoft Teams for DoD: TEAMS_DOD</span></span>

### <a name="assign-teams-licenses-in-bulk"></a><span data-ttu-id="bd232-141">팀 라이선스를 대량으로 배정</span><span class="sxs-lookup"><span data-stu-id="bd232-141">Assign Teams licenses in bulk</span></span>

<span data-ttu-id="bd232-142">자세한 단계는 PowerShell을 [사용 하 여 사용자 계정에 라이선스 할당](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bd232-142">For detailed steps, see [Assign licenses to user accounts with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="remove-teams-licenses-in-bulk"></a><span data-ttu-id="bd232-143">팀 라이선스를 대량으로 제거</span><span class="sxs-lookup"><span data-stu-id="bd232-143">Remove Teams licenses in bulk</span></span>

<span data-ttu-id="bd232-144">자세한 단계는 PowerShell을 [사용 하 여 서비스에 대 한 액세스 사용 안 함을](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) 참조 하 고 [사용자 라이선스를 할당 하는 동안 서비스에](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)대 한 액세스</span><span class="sxs-lookup"><span data-stu-id="bd232-144">For detailed steps, see [Disable access to services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) and [Disable access to services while assigning user licenses](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).</span></span>

#### <a name="example"></a><span data-ttu-id="bd232-145">예</span><span class="sxs-lookup"><span data-stu-id="bd232-145">Example</span></span> 

<span data-ttu-id="bd232-146">다음은 [MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) 및 [Set-MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) cmdlet을 사용 하 여 특정 라이선스 계획이 있는 사용자를 위해 팀을 비활성화 하는 방법의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="bd232-146">The following is an example of how to use the [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) and [Set-MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) cmdlets to disable Teams for users who have a specific licensing plan.</span></span> <span data-ttu-id="bd232-147">예를 들어 다음 단계에 따라 특정 라이선스 계획을 보유 하 고 있는 모든 사용자의 팀을 먼저 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd232-147">For example, follow these steps to first disable Teams for all users who have a particular licensing plan.</span></span> <span data-ttu-id="bd232-148">그런 다음 팀에 액세스 해야 하는 각 개별 사용자에 대해 팀을 활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd232-148">Then enable Teams for each individual user who should have access to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd232-149">[MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) cmdlet은 사용자 지정 스크립트에서 명시적으로 식별 되지 않는 한 이전에 비활성화 된 모든 서비스를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd232-149">The [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) cmdlet will enable all services that were previously disabled unless explicitly identified in your custom script.</span></span> <span data-ttu-id="bd232-150">예를 들어 팀을 사용 하지 않도록 설정 하는 동안 Exchange 및 Sway를 모두 사용 하지 않도록 설정 하려면 스크립트에이를 포함 하거나 Exchange 및 Sway 모두를 식별 한 사용자에 대해 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd232-150">For example, if you want to leave both Exchange and Sway disabled while also disabling Teams, you'll need to include this in the script or both Exchange and Sway will be enabled for those users you identified.</span></span>

<span data-ttu-id="bd232-151">다음 명령을 실행 하 여 조직에서 사용 가능한 모든 라이선스 계획을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd232-151">Run the following command to display all available licensing plans in your organization.</span></span> <span data-ttu-id="bd232-152">자세히 알아보려면 [PowerShell을 사용 하 여 라이선스 및 서비스 보기](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bd232-152">To learn more, see [View licenses and services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).</span></span>

      Get-MsolAccountSku

<span data-ttu-id="bd232-153">\<CompanyName:License>조직 이름과 앞 단계에서 검색 한 라이선스 계획의 식별자 인 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd232-153">Run the following commands, where \<CompanyName:License> is your organization name and the identifier for the licensing plan that you retrieved in the earlier step.</span></span> <span data-ttu-id="bd232-154">예를 들어 ContosoSchool: ENTERPRISEPACK_STUDENT.</span><span class="sxs-lookup"><span data-stu-id="bd232-154">For example, ContosoSchool:ENTERPRISEPACK_STUDENT.</span></span>

      $acctSKU="<CompanyName:License>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"

<span data-ttu-id="bd232-155">라이선스 요금제에 대 한 활성 라이선스가 있는 모든 사용자에 대해 팀을 사용 하지 않도록 설정 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd232-155">Run the following command to disable Teams for all users who have an active license for the licensing plan.</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

## <a name="manage-teams-at-the-organization-level"></a><span data-ttu-id="bd232-156">조직 수준에서 팀 관리</span><span class="sxs-lookup"><span data-stu-id="bd232-156">Manage teams at the organization level</span></span>

[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

## <a name="related-topics"></a><span data-ttu-id="bd232-157">관련 주제</span><span class="sxs-lookup"><span data-stu-id="bd232-157">Related topics</span></span>

- [<span data-ttu-id="bd232-158">팀 추가 기능 라이선스</span><span class="sxs-lookup"><span data-stu-id="bd232-158">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="bd232-159">팀 추가 기능 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="bd232-159">Assign Teams add-on licenses</span></span>](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [<span data-ttu-id="bd232-160">PowerShell을 사용 하 여 라이선스 및 서비스 보기</span><span class="sxs-lookup"><span data-stu-id="bd232-160">View licenses and services with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="bd232-161">라이선싱에 대한 제품 이름 및 서비스 계획 식별자</span><span class="sxs-lookup"><span data-stu-id="bd232-161">Product names and service plan identifiers for licensing</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="bd232-162">교육 SKU 참조</span><span class="sxs-lookup"><span data-stu-id="bd232-162">Education SKU reference</span></span>](sku-reference-edu.md)