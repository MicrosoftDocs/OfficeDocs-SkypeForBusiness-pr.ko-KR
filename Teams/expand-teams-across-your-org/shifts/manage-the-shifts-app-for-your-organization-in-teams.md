---
title: 조직의 교대 근무 앱 관리
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 조직의 Firstline Worker 용 팀에서 교대 근무 앱을 설정 하 고 관리 하는 방법에 대해 알아봅니다.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 745644c7a6cf2207412faacd78e7b5a26d7b754d
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2020
ms.locfileid: "44349662"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="7e56a-103">Microsoft 팀에서 조직의 교대 근무 앱 관리</span><span class="sxs-lookup"><span data-stu-id="7e56a-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7e56a-104">유효 2020 년 6 월 30 일에 Microsoft StaffHub 사용이 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-104">Effective June 30, 2020, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="7e56a-105">Microsoft 팀에 StaffHub 접근 권한 값을 구축 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-105">We're building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="7e56a-106">현재 팀에는 일정 관리를 위해 교대 근무 앱이 포함 되어 있으며 추가 기능이 시간에 따라 롤아웃 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="7e56a-107">StaffHub은 2020 년 6 월 30 일에 모든 사용자의 작업을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-107">StaffHub will stop working for all users on June 30, 2020.</span></span> <span data-ttu-id="7e56a-108">StaffHub를 열려고 하는 모든 사용자에 게 팀을 다운로드 하도록 지시 하는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="7e56a-109">자세한 내용은 [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md)을 사용 중지 하세요.</span><span class="sxs-lookup"><span data-stu-id="7e56a-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="7e56a-110">교대의 개요</span><span class="sxs-lookup"><span data-stu-id="7e56a-110">Overview of Shifts</span></span>

<span data-ttu-id="7e56a-111">Microsoft 팀의 교대 근무 앱은 Firstline Worker를 연결 된 상태로 유지 하 고 동기화 합니다. 팀에 대 한 신속 하 고 효율적인 시간 관리 및 통신을 위해 먼저 모바일을 구축할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-111">The Shifts app in Microsoft Teams keeps Firstline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="7e56a-112">교대 근무를 통해 최신 회선 근로자와 해당 관리자는 모바일 장치를 사용 하 여 일정을 관리 하 고 지속적인 연락을 즐길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-112">Shifts lets Firstline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span>

- <span data-ttu-id="7e56a-113">관리자는 팀에 대 한 교대 근무 일정을 만들고 업데이트 하 고 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="7e56a-114">각 사용자에 게 메시지를 보낼 수 있습니다 ("층에는 분할이 있습니다") 또는 전체 팀 ("지역 GM은 20 분 내에 도착 하 고 있습니다.").</span><span class="sxs-lookup"><span data-stu-id="7e56a-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="7e56a-115">또한 정책 문서, 뉴스 게시판, 비디오를 보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="7e56a-116">직원 들이 예정 된 교대 근무를 보거나, 하루에 대해 다른 사람을 예약 하 고, 교대 근무를 교환 하거나,, 휴가를 요청 하는 경우를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-116">Employees view their upcoming shifts, can see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="7e56a-117">현재 이동이 게스트 사용자를 지원 하지 않는다는 것을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="7e56a-118">즉, 팀에서 게스트 액세스가 설정 되어 있을 때는 팀의 게스트를 추가 하거나 shift 일정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

## <a name="availability-of-shifts"></a><span data-ttu-id="7e56a-119">이동 가능</span><span class="sxs-lookup"><span data-stu-id="7e56a-119">Availability of Shifts</span></span>

<span data-ttu-id="7e56a-120">이동은 팀을 사용할 수 있는 모든 Enterprise Sku에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-120">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="7e56a-121">데이터 이동 위치</span><span class="sxs-lookup"><span data-stu-id="7e56a-121">Location of Shifts data</span></span>

<span data-ttu-id="7e56a-122">현재 북미, 서유럽, 아시아 태평양의 데이터 센터에서 Azure에 저장 된 데이터를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-122">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="7e56a-123">데이터가 저장 되는 위치에 대 한 자세한 내용은 [내 데이터 위치](http://o365datacentermap.azurewebsites.net/)를 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="7e56a-123">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="7e56a-124">교대 근무 설정</span><span class="sxs-lookup"><span data-stu-id="7e56a-124">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="7e56a-125">조직의 교대 근무 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="7e56a-125">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="7e56a-126">이동은 조직의 모든 팀 사용자에 대해 기본적으로 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-126">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="7e56a-127">Microsoft 팀 관리 센터에서 [앱 관리](../../manage-apps.md) 페이지의 조직 수준에서 앱을 끄거나 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-127">You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="7e56a-128">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**으로  >  **앱 관리** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-128">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps** .</span></span>
2. <span data-ttu-id="7e56a-129">앱 목록에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-129">In the list of apps, do one of the following:</span></span>

    - <span data-ttu-id="7e56a-130">조직의 이동 기능을 해제 하려면 교대 앱을 검색 하 여 선택한 다음 **차단을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-130">To turn off Shifts for your organization, search for the Shifts app, select it, and then click **Block**.</span></span>
    - <span data-ttu-id="7e56a-131">조직의 교대 근무를 설정 하려면 교대 앱을 검색 하 여 선택한 다음 **허용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-131">To turn on Shifts for your organization, search for the Shifts app, select it, and then click **Allow**.</span></span>

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="7e56a-132">조직의 특정 사용자에 대 한 교대 근무 설정 또는 해제</span><span class="sxs-lookup"><span data-stu-id="7e56a-132">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="7e56a-133">조직의 특정 사용자가 교대 근무를 사용 하는 것을 허용 하거나 차단 하려면 [앱 관리](../../manage-apps.md) 페이지에서 조직에 대 한 교대가 설정 되어 있는지 확인 한 다음 사용자 지정 앱 권한 정책을 만들어 해당 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-133">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="7e56a-134">자세히 알아보려면 [팀에서 앱 권한 정책 관리](../../teams-app-permission-policies.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7e56a-134">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="7e56a-135">FirstlineWorker 앱 설정 정책을 사용 하 여 팀에 고정 이동</span><span class="sxs-lookup"><span data-stu-id="7e56a-135">Use the FirstlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="7e56a-136">앱 설정 정책은 팀을 사용자 지정 하 여 조직의 사용자에 게 가장 중요 한 앱을 강조 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-136">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="7e56a-137">정책에 설정 된 앱은 &mdash; 팀 데스크톱 클라이언트의 측면에 있는 표시줄과 팀 모바일 클라이언트의 맨 아래에 있으며 &mdash; 사용자가 빠르고 쉽게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-137">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span> 
 
<span data-ttu-id="7e56a-138">팀에는 조직의 Firstline Worker에 할당할 수 있는 기본 제공 FirstlineWorker 앱 설정 정책이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-138">Teams includes a built-in FirstlineWorker app setup policy that you can assign to Firstline Workers in your organization.</span></span> <span data-ttu-id="7e56a-139">기본적으로 정책에는 활동, 교대, 채팅 및 통화 앱이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-139">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="7e56a-140">Firstlineworker 정책을 보려면 Microsoft 팀 관리 센터의 왼쪽 탐색에서 **팀 앱**  >  **앱 설치 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-140">To view the FirstlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="7e56a-141">![FirstlineWorker 앱 설정 정책의 스크린샷](../../media/firstline-worker-app-setup-policy.png "Microsoft 팀 관리 센터의 FirstlineWorker 앱 설치 정책 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="7e56a-141">![Screenshot of the FirstlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FirstlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-firstlineworker-policy-to-individual-users"></a><span data-ttu-id="7e56a-142">개별 사용자에 게 FirstlineWorker 정책 할당</span><span class="sxs-lookup"><span data-stu-id="7e56a-142">Assign the FirstlineWorker policy to individual users</span></span>

1. <span data-ttu-id="7e56a-143">Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동한 후 해당 사용자를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-143">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="7e56a-144">**할당된 정책** 옆에서 **편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-144">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="7e56a-145">**팀 앱 설정 정책**에서 **firstlineworker**를 선택 하 고 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-145">Under **Teams App Setup policy**, select **FirstlineWorker**, and then choose **Save**.</span></span>

#### <a name="assign-the-firstlineworker-app-setup-policy-to-user-members-of-a-group"></a><span data-ttu-id="7e56a-146">그룹의 사용자 구성원에 FirstlineWorker 앱 설정 정책 할당</span><span class="sxs-lookup"><span data-stu-id="7e56a-146">Assign the FirstlineWorker app setup policy to user members of a group</span></span>

<span data-ttu-id="7e56a-147">그래프 모듈의 Azure Active Directory PowerShell 및 비즈니스용 Skype PowerShell 모듈에 연결 하 여 보안 그룹과 같은 그룹의 사용자 구성원에 게 FirstlineWorker 앱 설정 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-147">You can assign the FirstlineWorker app setup policy to user members of a group, such as a security group, by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="7e56a-148">PowerShell을 사용 하 여 팀을 관리 하는 방법에 대 한 자세한 내용은 [팀 Powershell 개요](../../teams-powershell-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7e56a-148">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](../../teams-powershell-overview.md).</span></span>

<span data-ttu-id="7e56a-149">이 예제에서는 FirstlineWorker 앱 설정 정책을 Contoso Firstline 팀 그룹의 모든 사용자 구성원에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-149">In this example, we assign the FirstlineWorker app setup policy to all user members of the Contoso Firstline Team group.</span></span>

> [!NOTE]
> <span data-ttu-id="7e56a-150">먼저 [단일 Windows powershell 창에서 모든 Office 365 서비스에 연결](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)의 단계를 따라 Graph 모듈 및 비즈니스용 Skype powershell 모듈에 대 한 Azure Active Directory powershell에 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-150">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="7e56a-151">특정 그룹의 GroupObjectId를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-151">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
<span data-ttu-id="7e56a-152">지정 된 그룹의 구성원을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-152">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="7e56a-153">FirstlineWorker 앱 설치 정책을 그룹의 모든 사용자 구성원에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-153">Assign the FirstlineWorker app setup policy to all user members of the group.</span></span>
```PowerShell
$members | ForEach-Object {Grant-CsTeamsAppSetupPolicy -PolicyName "FirstlineWorker" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="7e56a-154">그룹의 구성원 수에 따라이 명령을 실행 하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e56a-154">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="7e56a-155">관련 항목</span><span class="sxs-lookup"><span data-stu-id="7e56a-155">Related topics</span></span>
- [<span data-ttu-id="7e56a-156">Firstline Worker에 대 한 도움말 이동</span><span class="sxs-lookup"><span data-stu-id="7e56a-156">Shifts Help for Firstline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
