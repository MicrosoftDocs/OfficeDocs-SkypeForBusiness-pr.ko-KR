---
title: Microsoft Teams에 대한 사용자 액세스 관리
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: 조직의 사용자에게 Teams 라이선스를 할당하거나 제거하여 Teams에 대한 사용자 액세스를 관리하는 방법을 배워야 합니다.
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7d49b27de8fe6c6d13ef6ac626764b13e1fe36a0
ms.sourcegitcommit: 4e648c3dd71d9c38cbcb81fab9e8cb9d241fe79c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49871017"
---
# <a name="manage-user-access-to-teams"></a><span data-ttu-id="6a67c-103">Teams에 대한 사용자 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="6a67c-103">Manage user access to Teams</span></span>

<span data-ttu-id="6a67c-104">Microsoft Teams 제품 라이선스를 할당하거나 제거하여 사용자 수준에서 Teams에 대한 액세스를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="6a67c-104">You manage access to Teams at the user level by assigning or removing a Microsoft Teams product license.</span></span> <span data-ttu-id="6a67c-105">익명으로 Teams 모임에 참가하는 것을 제외하고 조직의 각 사용자에게 Teams 라이선스가 있어야 Teams를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a67c-105">Except for joining Teams meetings anonymously, each user in your organization must have a Teams license before they can use Teams.</span></span> <span data-ttu-id="6a67c-106">새 사용자 계정을 만들 때 새 사용자 또는 기존 계정이 있는 사용자에게 Teams 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a67c-106">You can assign a Teams license for new users when new user accounts are created or to users with existing accounts.</span></span>

<span data-ttu-id="6a67c-107">기본적으로 라이선스 계획(예: Microsoft 365 Enterprise E3 또는 Microsoft 365 Business Premium)이 사용자에게 할당되면 Teams 라이선스가 자동으로 할당되고 사용자가 Teams에 대해 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a67c-107">By default, when a licensing plan (for example, Microsoft 365 Enterprise E3 or Microsoft 365 Business Premium) is assigned to a user, a Teams license is automatically assigned, and the user is enabled for Teams.</span></span> <span data-ttu-id="6a67c-108">라이선스를 제거하거나 할당하여 사용자에 대해 Teams를 사용하지 않도록 설정하거나 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a67c-108">You can disable or enable Teams for a user by removing or assigning a license at any time.</span></span>

<span data-ttu-id="6a67c-109"><a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams</a>관리 센터에서 관리되는 메시징 정책을 사용하여 Teams에서 사용자가 사용할 수 있는 채팅 및 채널 메시징 기능을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a67c-109">Use messaging policies, managed from the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams Admin Center</a>, to control what chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="6a67c-110">기본 정책을 사용하거나 조직의 사용자에 대해 하나 이상의 사용자 지정 메시징 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a67c-110">You can use the default policy or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="6a67c-111">자세한 내용은 Teams에서 메시지 [관리 정책을 읽어보아야 합니다.](messaging-policies-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="6a67c-111">To learn more, read [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>
<span data-ttu-id="6a67c-112">Microsoft 365 관리 센터에서 또는 PowerShell을 사용하여 Teams 라이선스를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="6a67c-112">You manage Teams licenses in the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="6a67c-113">라이선스를 관리하려면 전역 관리자 또는 사용자 관리 관리자해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a67c-113">You must be a Global admin or User management admin to manage licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="6a67c-114">팀이 프로젝트 및 기타 동적 이니셔티브에 대해 유기적으로 구성될 수 있도록 모든 사용자에 대해 Teams를 사용하도록 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6a67c-114">We recommend that you enable Teams for all users so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="6a67c-115">파일럿을 실행 중인 경우에도 모든 사용자에 대해 Teams를 사용하도록 설정하는 것이 유용할 수 있지만 파일럿 사용자 그룹에 대한 통신만 대상으로 지정하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a67c-115">Even if you're running a pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="6a67c-116">Microsoft 365 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="6a67c-116">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="6a67c-117">Teams 사용자 수준 라이선스는 Microsoft 365 관리 센터 사용자 관리 인터페이스를 통해 직접 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a67c-117">Teams user-level licenses are managed directly through the Microsoft 365 admin center user management interfaces.</span></span> <span data-ttu-id="6a67c-118">관리자는 새 사용자 계정을 만들 때 또는 기존 계정이 있는 사용자에게 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a67c-118">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="6a67c-119">관리자가 Microsoft Teams 라이선스를 관리하려면 전역 관리자 또는 사용자 관리 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a67c-119">The administrator must have Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>
<span data-ttu-id="6a67c-120">Microsoft 365 관리 센터를 사용하여 개별 사용자 또는 소규모 사용자 집합에 대한 Teams 라이선스를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="6a67c-120">Use the Microsoft 365 admin center to manage Teams licenses for individual users or small sets of users at a time.</span></span> <span data-ttu-id="6a67c-121">라이선스 페이지(한 시  최대 20명까지) 또는 활성 사용자 페이지에서 Teams 라이선스를 **관리할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a67c-121">You can manage Teams licenses on the **Licenses** page (for up to 20 users at at time) or **Active users** page.</span></span> <span data-ttu-id="6a67c-122">선택하는 방법은 특정 사용자에 대한 제품 라이선스를 관리하거나 특정 제품에 대한 사용자 라이선스를 관리할지 여부에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a67c-122">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="6a67c-123">수백 또는 수천 명의 사용자와 같은 많은 수의 사용자에 대한 Teams 라이선스를 관리해야 하는 경우 [Azure AD(Azure Active](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)Directory)에서 [PowerShell](#using-powershell) 또는 그룹 기반 라이선스를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="6a67c-123">If you need to manage Teams licenses for a large number of users, such as hundreds or thousands of users, [use PowerShell](#using-powershell) or [group-based licensing in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span> 

### <a name="assign-a-teams-license"></a><span data-ttu-id="6a67c-124">Teams 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="6a67c-124">Assign a Teams license</span></span>

<span data-ttu-id="6a67c-125">라이선스 페이지 또는 활성 사용자 페이지를  사용하는지 여부에 따라 **단계가** 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="6a67c-125">The steps are different depending on whether you use the **Licenses** page or **Active users** page.</span></span>  <span data-ttu-id="6a67c-126">단계별 지침은 사용자에게 라이선스 [할당을 참조하세요.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="6a67c-126">For step-by-step instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

|||
|---------|---------|
|![사용자에 대해 사용하도록 설정된 Teams 라이선스의 스크린샷](media/assign-teams-licenses-1.png)    | ![사용자에 대해 사용하도록 설정된 Teams 라이선스의 스크린샷](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a><span data-ttu-id="6a67c-129">Teams 라이선스 제거</span><span class="sxs-lookup"><span data-stu-id="6a67c-129">Remove a Teams license</span></span>

<span data-ttu-id="6a67c-130">사용자에서 Teams 라이선스를 제거하면 해당 사용자에 대해 Teams가 비활성화되어 앱 시작 프로그램 또는 홈페이지에 Teams가 더 이상 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a67c-130">When you remove a Teams license from a user, Teams is disabled for that user, and they will no longer see Teams in the app launcher or homepage.</span></span> <span data-ttu-id="6a67c-131">자세한 단계는 사용자로부터 라이선스의 [재할당 안 을 참조하세요.](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users)</span><span class="sxs-lookup"><span data-stu-id="6a67c-131">For detailed steps, see [Unassign licenses from users](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users).</span></span>

|||
|---------|---------|
|![사용자에 대해 사용할 수 없습니다. Teams 라이선스 스크린샷](media/remove-teams-licenses-1.png)    | ![사용자에 대해 사용할 수 없습니다. Teams 라이선스 스크린샷](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a><span data-ttu-id="6a67c-134">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="6a67c-134">Using PowerShell</span></span>

<span data-ttu-id="6a67c-135">PowerShell을 사용하여 사용자에 대한 Teams 라이선스를 일괄적으로 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="6a67c-135">Use PowerShell to manage Teams licenses for users in bulk.</span></span> <span data-ttu-id="6a67c-136">다른 서비스 계획 라이선스와 동일한 방식으로 PowerShell을 통해 Teams를 사용하도록 설정하고 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a67c-136">You enable and disable Teams through PowerShell in the same way that you would for any other service plan license.</span></span> <span data-ttu-id="6a67c-137">다음과 같이 Teams의 서비스 계획에 대한 식별자가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6a67c-137">You'll need the identifiers for the service plans for Teams, which are as follows:</span></span>

- <span data-ttu-id="6a67c-138">Microsoft Teams: TEAMS1</span><span class="sxs-lookup"><span data-stu-id="6a67c-138">Microsoft Teams: TEAMS1</span></span>
- <span data-ttu-id="6a67c-139">GCC용 Microsoft Teams: TEAMS_GOV</span><span class="sxs-lookup"><span data-stu-id="6a67c-139">Microsoft Teams for GCC: TEAMS_GOV</span></span>
- <span data-ttu-id="6a67c-140">DoD용 Microsoft Teams: TEAMS_DOD</span><span class="sxs-lookup"><span data-stu-id="6a67c-140">Microsoft Teams for DoD: TEAMS_DOD</span></span>

### <a name="assign-teams-licenses-in-bulk"></a><span data-ttu-id="6a67c-141">Teams 라이선스 일괄 할당</span><span class="sxs-lookup"><span data-stu-id="6a67c-141">Assign Teams licenses in bulk</span></span>

<span data-ttu-id="6a67c-142">자세한 단계는 PowerShell을 통해 사용자 계정에 라이선스 [할당을 참조하세요.](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="6a67c-142">For detailed steps, see [Assign licenses to user accounts with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="remove-teams-licenses-in-bulk"></a><span data-ttu-id="6a67c-143">Teams 라이선스 일괄 제거</span><span class="sxs-lookup"><span data-stu-id="6a67c-143">Remove Teams licenses in bulk</span></span>

<span data-ttu-id="6a67c-144">자세한 단계는 사용자 라이선스를 할당하는 동안 [PowerShell을](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) 통해 서비스에 대한 액세스 비활성화 및 서비스에 대한 액세스 사용 안 [을 참조하세요.](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)</span><span class="sxs-lookup"><span data-stu-id="6a67c-144">For detailed steps, see [Disable access to services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) and [Disable access to services while assigning user licenses](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).</span></span>

#### <a name="example"></a><span data-ttu-id="6a67c-145">예제</span><span class="sxs-lookup"><span data-stu-id="6a67c-145">Example</span></span> 

<span data-ttu-id="6a67c-146">다음은 [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) 및 [Set-MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) cmdlet을 사용하여 특정 라이선스 계획이 있는 사용자에 대해 Teams를 사용하지 않도록 설정하는 방법의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="6a67c-146">The following is an example of how to use the [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) and [Set-MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) cmdlets to disable Teams for users who have a specific licensing plan.</span></span> <span data-ttu-id="6a67c-147">예를 들어 다음 단계에 따라 먼저 특정 라이선스 계획이 있는 모든 사용자에 대해 Teams를 사용하지 않도록 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="6a67c-147">For example, follow these steps to first disable Teams for all users who have a particular licensing plan.</span></span> <span data-ttu-id="6a67c-148">그런 다음 Teams에 액세스할 수 있는 각 개별 사용자에 대해 Teams를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a67c-148">Then enable Teams for each individual user who should have access to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6a67c-149">[New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) cmdlet은 사용자 지정 스크립트에서 명시적으로 식별되지 않는 한 이전에 비활성화된 모든 서비스를 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="6a67c-149">The [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) cmdlet will enable all services that were previously disabled unless explicitly identified in your custom script.</span></span> <span data-ttu-id="6a67c-150">예를 들어 Teams를 사용하지 않도록 설정하는 동안 Exchange와 Sway를 모두 사용하지 않도록 설정하려는 경우 스크립트에 이를 포함하거나 식별한 사용자에 대해 Exchange 및 Sway를 모두 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a67c-150">For example, if you want to leave both Exchange and Sway disabled while also disabling Teams, you'll need to include this in the script or both Exchange and Sway will be enabled for those users you identified.</span></span>

<span data-ttu-id="6a67c-151">다음 명령을 실행하여 조직에서 사용 가능한 모든 라이선스 계획을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6a67c-151">Run the following command to display all available licensing plans in your organization.</span></span> <span data-ttu-id="6a67c-152">자세한 내용은 PowerShell을 통해 라이선스 및 [서비스 보기를 참조합니다.](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="6a67c-152">To learn more, see [View licenses and services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).</span></span>


```powershell
Get-MsolAccountSku
```

<span data-ttu-id="6a67c-153">이전 단계에서 검색한 라이선스 계획에 대한 조직 이름 및 식별자인 다음 명령을 \<CompanyName:License> 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6a67c-153">Run the following commands, where \<CompanyName:License> is your organization name and the identifier for the licensing plan that you retrieved in the earlier step.</span></span> <span data-ttu-id="6a67c-154">예를 들어 ContosoSchool:ENTERPRISEPACK_STUDENT.</span><span class="sxs-lookup"><span data-stu-id="6a67c-154">For example, ContosoSchool:ENTERPRISEPACK_STUDENT.</span></span>

```powershell
$acctSKU="<CompanyName:License>
$x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
```

<span data-ttu-id="6a67c-155">다음 명령을 실행하여 라이선스 계획에 대한 활성 라이선스가 있는 모든 사용자에 대해 Teams를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a67c-155">Run the following command to disable Teams for all users who have an active license for the licensing plan.</span></span>

```powershell
Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
```

## <a name="related-topics"></a><span data-ttu-id="6a67c-156">관련 항목</span><span class="sxs-lookup"><span data-stu-id="6a67c-156">Related topics</span></span>

- [<span data-ttu-id="6a67c-157">Teams 추가 기능 라이선스</span><span class="sxs-lookup"><span data-stu-id="6a67c-157">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="6a67c-158">Teams 추가 기능 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="6a67c-158">Assign Teams add-on licenses</span></span>](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [<span data-ttu-id="6a67c-159">PowerShell을 통해 라이선스 및 서비스 보기</span><span class="sxs-lookup"><span data-stu-id="6a67c-159">View licenses and services with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="6a67c-160">라이선싱에 대한 제품 이름 및 서비스 계획 식별자</span><span class="sxs-lookup"><span data-stu-id="6a67c-160">Product names and service plan identifiers for licensing</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="6a67c-161">Education SKU 참조</span><span class="sxs-lookup"><span data-stu-id="6a67c-161">Education SKU reference</span></span>](sku-reference-edu.md)
