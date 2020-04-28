---
title: Microsoft 팀에 대 한 사용자 액세스 관리
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.reviewer: ritikag
search.appverid: MET150
description: Microsoft 팀 제품 라이선스를 할당 하거나 제거 하 여 사용자별로 사용자 수준 액세스를 사용 하거나 사용 하지 않도록 설정 하는 방법에 대해 알아봅니다.
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 10485fd7f04cfae675ea38967389851d4d72be90
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43903353"
---
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="7d6e3-103">Microsoft 팀에 대 한 사용자 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="7d6e3-103">Manage user access to Microsoft Teams</span></span>
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="7d6e3-104">사용자 수준에서 microsoft 팀 제품 라이선스를 할당 하거나 제거 하 여 사용자 기준으로 Microsoft 팀에 대 한 액세스를 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e3-104">At the user level, access to Microsoft Teams can be enabled or disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="7d6e3-105">팀 관리 센터에서 관리 되는 메시징 정책을 사용 하 여 팀의 사용자가 사용할 수 있는 채팅 및 채널 메시징 기능을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e3-105">Use messaging policies, managed from the Teams Admin Center, to control what chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="7d6e3-106">기본 정책을 사용 하거나 조직의 사용자를 위해 하나 이상의 사용자 지정 메시징 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e3-106">You can use the default policy or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="7d6e3-107">자세한 내용은 [팀에서 메시징 정책 관리](messaging-policies-in-teams.md)를 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="7d6e3-107">To learn more, read [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>

> [!NOTE]
><span data-ttu-id="7d6e3-108">팀에서 프로젝트 및 기타 동적 이니셔티브에 대 한 organically를 만들 수 있도록 회사의 모든 사용자에 대해 팀을 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e3-108">Microsoft recommends that you turn on Teams for all users in a company so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="7d6e3-109">파일럿을 결정 하는 경우에도 팀이 모든 사용자에 게 사용 하도록 설정 하는 것이 좋지만, 사용자의 파일럿 그룹에 대 한 대상 통신만을 유지 하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e3-109">Even if you are deciding to pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="manage-teams-through-the-microsoft-365-admin-center"></a><span data-ttu-id="7d6e3-110">Microsoft 365 관리 센터를 통해 팀 관리</span><span class="sxs-lookup"><span data-stu-id="7d6e3-110">Manage Teams through the Microsoft 365 admin center</span></span>

<span data-ttu-id="7d6e3-111">팀 사용자 수준 라이선스는 Microsoft 365 관리 센터 사용자 관리 인터페이스를 통해 직접 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e3-111">Teams user-level licenses are managed directly through the Microsoft 365 admin center user management interfaces.</span></span> <span data-ttu-id="7d6e3-112">관리자는 새 사용자 계정이 만들어지거나 기존 계정이 있는 사용자에 게 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e3-112">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> <span data-ttu-id="7d6e3-113">관리자가 Microsoft 팀 라이선스를 관리 하려면 전역 관리자 또는 사용자 관리 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e3-113">The administrator must have Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="7d6e3-114">E3 또는 E5와 같은 라이선스 SKU가 사용자에 게 할당 되 면 Microsoft 팀 라이선스가 자동으로 할당 되며 사용자가 Microsoft 팀에 대해 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e3-114">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams.</span></span> <span data-ttu-id="7d6e3-115">관리자는 모든 Office 365 서비스 및 라이선스를 세부적으로 제어할 수 있으며 특정 사용자 또는 사용자 그룹의 Microsoft 팀 라이선스를 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e3-115">Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

![관리 센터의 제품 라이선스 섹션 스크린샷](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

<span data-ttu-id="7d6e3-117">팀 사용자 라이선스는 언제 든 지 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e3-117">A Teams user license can be disabled at any time.</span></span> <span data-ttu-id="7d6e3-118">라이선스를 사용 하지 않도록 설정 하면 Microsoft 팀에 대 한 사용자 액세스가 차단 되 고 사용자가 Office 365 앱 시작 관리자 및 홈페이지에서 팀을 더 이상 볼 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e3-118">Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Teams in the Office 365 app launcher and homepage.</span></span>

![제품 라이선스 섹션에서 선택한 팀을 보여 주는 스크린샷](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a><span data-ttu-id="7d6e3-120">PowerShell을 통해 관리</span><span class="sxs-lookup"><span data-stu-id="7d6e3-120">Manage via PowerShell</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7d6e3-121">MsolLicenseOptions는 사용자 지정 된 스크립트에서 명시적으로 식별 하지 않는 한 이전에 비활성화 한 모든 서비스를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e3-121">New-MsolLicenseOptions will enable all services that were previously disabled unless explicitly identified in your customized script.</span></span> <span data-ttu-id="7d6e3-122">예를 들어, 더 이상 팀을 사용 하지 않도록 설정 하는 동안 Exchange & Sway를 모두 사용 하지 않도록 설정 하려면 스크립트에이를 포함 하거나 Exchange & 모두 사용자가 확인 하 여 Sway를 사용할 수 있도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e3-122">As an example, if you wanted to leave both Exchange & Sway disabled while additionally disabling Teams, you'd need to include this in the script or both Exchange & Sway will become enabled for those users you've identified.</span></span> <span data-ttu-id="7d6e3-123">GUI를 사용 하 여이 기능을 관리 하려면 [Office 365 라이선스 보고 및 관리 도구-자세한 내용은 라이선스 제거를 대량으로 할당](https://gallery.technet.microsoft.com/Office365-License-cfd9489c) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7d6e3-123">To use a GUI to manage this functionality, see [Office 365 License Reporting and Management Tool -Assign Remove Licenses in Bulk](https://gallery.technet.microsoft.com/Office365-License-cfd9489c) for more information.</span></span>

<span data-ttu-id="7d6e3-124">다른 작업을 수행 하는 것 처럼 PowerShell을 통해 팀을 작업 부하 라이선스로 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e3-124">Enabling and disabling Teams as a workload license through PowerShell is done just as any other workload.</span></span> <span data-ttu-id="7d6e3-125">Microsoft 팀에 대 한 서비스 계획 이름은 TEAMS1입니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e3-125">The service plan name is TEAMS1 for Microsoft Teams.</span></span> <span data-ttu-id="7d6e3-126">GCC의 경우 서비스 계획 이름은 TEAMS_GOV입니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e3-126">For GCC the service plan name is TEAMS_GOV.</span></span> <span data-ttu-id="7d6e3-127">GCC High의 경우 서비스 계획 이름은 TEAMS_GCCHIGH입니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e3-127">For GCC High the service plan name is TEAMS_GCCHIGH.</span></span> <span data-ttu-id="7d6e3-128">DoD의 경우 서비스 계획 이름이 TEAMS_DOD 합니다 (자세한 내용은 [Office 365 PowerShell을 사용 하 여 서비스에 대 한 액세스 비활성화](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) 를 참조 하세요.)</span><span class="sxs-lookup"><span data-stu-id="7d6e3-128">For DoD the service plan name is TEAMS_DOD (See [Disable access to services with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) for more information.)</span></span>

<span data-ttu-id="7d6e3-129">**샘플:** 다음은 특정 라이선스 유형의 모든 사용자에 대해 팀을 비활성화 하는 방법에 대 한 간단한 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e3-129">**Sample:** The following is just a quick sample on how you would disable Teams for everyone in a particular license type.</span></span> <span data-ttu-id="7d6e3-130">먼저이 작업을 수행한 다음 파일럿을 위해 액세스 해야 하는 사용자에 대해 개별적으로 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e3-130">You'll need to do this first, then individually enable it for the users who should have access for piloting purposes.</span></span>

<span data-ttu-id="7d6e3-131">조직 내에 있는 구독 유형을 표시 하려면 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e3-131">To display the subscription types you have within your organization, use the following command:</span></span>

      Get-MsolAccountSku

<span data-ttu-id="7d6e3-132">조직의 이름과 학교에 대 한 요금제 (ContosoSchool: ENTERPRISEPACK_STUDENT)를 포함 하는 계획의 이름을 입력 하 고 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e3-132">Fill in the name of your plan that includes your organization name and the plan for your school (such as ContosoSchool:ENTERPRISEPACK_STUDENT), and then run the following commands:</span></span>

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
<span data-ttu-id="7d6e3-133">지정 된 요금제에 대 한 활성 라이선스가 있는 모든 사용자에 대해 팀을 사용 하지 않도록 설정 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e3-133">To disable Teams for all users with an active license for your named plan, run the following command:</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![결정 지점을 나타내는 아이콘](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="7d6e3-135">의사 결정 지점</span><span class="sxs-lookup"><span data-stu-id="7d6e3-135">Decision Point</span></span>         |<ul><li><span data-ttu-id="7d6e3-136">조직에서 온 팀에 대 한 조직의 계획은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="7d6e3-136">What is your organization's plan for Teams onboarding across the organization?</span></span>  <span data-ttu-id="7d6e3-137">(파일럿 또는 열기)</span><span class="sxs-lookup"><span data-stu-id="7d6e3-137">(Pilot or Open)</span></span></li></ul>         |
|![다음 단계를 나타내는 아이콘](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="7d6e3-139">다음 단계</span><span class="sxs-lookup"><span data-stu-id="7d6e3-139">Next Steps</span></span>         |<ul><li><span data-ttu-id="7d6e3-140">폐쇄형 파일럿을 통해 온 보 딩이 있는 경우 라이선스를 통해 수행할 것인지 또는 대상을 지정 하 여 의사 소통을 할지 결정 하세요.</span><span class="sxs-lookup"><span data-stu-id="7d6e3-140">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targeted communication.</span></span></li><li><span data-ttu-id="7d6e3-141">의사 결정에 따라 팀에 액세스할 수 있도록 허용 된 파일럿 사용자만 (필요한 경우) 해야 하는지 여부를 확인 하는 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e3-141">Depending on decision, take steps to make sure only Pilot users who are allowed to access Teams (if needed).</span></span></li><li><span data-ttu-id="7d6e3-142">팀에 대 한 액세스 권한이 있는 사용자를 위한 지침을 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e3-142">Document the guidelines for which users who will (or will not) have access to Teams.</span></span></li></ul>         |

## <a name="manage-teams-at-the-office-365-organization-level"></a><span data-ttu-id="7d6e3-143">Office 365 조직 수준에서 팀 관리</span><span class="sxs-lookup"><span data-stu-id="7d6e3-143">Manage Teams at the Office 365 organization level</span></span>
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

