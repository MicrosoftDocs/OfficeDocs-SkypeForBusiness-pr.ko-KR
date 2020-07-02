---
title: Microsoft 팀 PowerShell을 사용 하 여 팀 관리
ms.reviewer: brandber
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 팀 PowerShell을 사용 하 여 Microsoft 팀을 관리 하는 방법을 알아보세요.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c217cea4a9ad800c1f31f8dcfae9c88ee281188c
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "44944125"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a><span data-ttu-id="39868-103">Microsoft 팀 PowerShell을 사용 하 여 팀 관리</span><span class="sxs-lookup"><span data-stu-id="39868-103">Manage Teams with Microsoft Teams PowerShell</span></span>

<span data-ttu-id="39868-104">이 문서에서는 Microsoft 팀 PowerShell을 사용 하 여 팀과 비즈니스용 Skype를 관리 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="39868-104">This article shows you how to use Microsoft Teams PowerShell to manage Teams and Skype for Business.</span></span> 

<span data-ttu-id="39868-105">[Microsoft 팀 cmdlet 참조](https://docs.microsoft.com/powershell/teams/?view=teams-ps) 및 [비즈니스용 Skype cmdlet 참조](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)와 함께이 지침을 사용 하세요.</span><span class="sxs-lookup"><span data-stu-id="39868-105">Use this guidance in conjunction with the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps) and [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

## <a name="create-and-manage-teams-using-powershell"></a><span data-ttu-id="39868-106">PowerShell을 사용 하 여 팀 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="39868-106">Create and manage teams using PowerShell</span></span>

<span data-ttu-id="39868-107">팀을 만들고 관리 하는 cmdlet은 [Microsoft 팀 PowerShell 모듈](https://www.powershellgallery.com/packages/MicrosoftTeams/)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39868-107">The cmdlets for creating and managing teams are in the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span></span>

<span data-ttu-id="39868-108">팀은 Office 365 그룹에서 지원 되므로 팀을 만들 때 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="39868-108">Teams are backed by Office 365 Groups, so when you create a team, you create a group.</span></span> <span data-ttu-id="39868-109">핵심 팀과 해당 설정 (,,)에 대 한 작동을 위해 제공 되는 cmdlet 집합과 ``new-team`` ``get-team`` ``set-team`` 팀 사용자 관리 (( ``add-teamuser`` ) ``remove-teamuser`` ) 뿐만 아니라 팀 (,) 채널을 관리 ``new-teamchannel`` ``remove-teamchannel`` 하는 cmdlet도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39868-109">There are a set of cmdlets provided for operating on the core team and its settings (``new-team``, ``get-team``,  ``set-team``), managing team users (``add-teamuser``, ``remove-teamuser``), as well as cmdlets for managing the channels of the team (``new-teamchannel``, ``remove-teamchannel``).</span></span> <span data-ttu-id="39868-110">이러한 모든 cmdlet은 최종 사용자로 실행할 수 있지만 사용자가 소유 하거나 구성원 인 팀 에서만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="39868-110">All of these cmdlets can be run as end users, but they'll work only on the teams that you own or are a member of.</span></span> <span data-ttu-id="39868-111">전역 관리자 또는 팀 서비스 관리자는 조직의 모든 팀에 대해 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39868-111">If you are a Global Admin or Teams Service Administrator, you'll be able to act on all teams in your organization.</span></span>

```powershell
New-Team -Name "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department
```

> <span data-ttu-id="39868-112">Microsoft 팀 PowerShell 모듈 cmdlet에 사용 되는 **GroupId** 는 Exchange powershell 모듈에서 반환 되는 **Identity** 속성과 같습니다 ``Get-UnifiedGroup`` .</span><span class="sxs-lookup"><span data-stu-id="39868-112">The **GroupId** used in the Microsoft Teams PowerShell module cmdlets is the same as the **Identity** property returned by ``Get-UnifiedGroup`` in the Exchange PowerShell module.</span></span>

## <a name="manage-policies-via-powershell"></a><span data-ttu-id="39868-113">PowerShell을 통해 정책 관리</span><span class="sxs-lookup"><span data-stu-id="39868-113">Manage policies via PowerShell</span></span>

> [!NOTE]
> - <span data-ttu-id="39868-114">비즈니스용 Skype Online Connector를 팀 PowerShell로 통합 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39868-114">Skype for Business Online Connector is being consolidated into Teams PowerShell.</span></span> <span data-ttu-id="39868-115">현재 공개 미리 보기에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39868-115">It is currently available in public preview.</span></span> <span data-ttu-id="39868-116">시간 내에 팀에 적용 되는 비즈니스용 Skype Online cmdlet은 팀 PowerShell 모듈에서 기본적으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39868-116">In time, Skype for Business Online cmdlets that apply to Teams will be natively available in the Teams PowerShell module.</span></span> <span data-ttu-id="39868-117">설치 단계는 [팀 PowerShell 설치](teams-powershell-install.md) 문서에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39868-117">Installation steps are available in the [Install Teams PowerShell](teams-powershell-install.md) article.</span></span>
>
> - <span data-ttu-id="39868-118">비즈니스용 Skype Online에 연결 되 면 PowerShell 세션에서 cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39868-118">The cmdlets will be available in your PowerShell session once you connect to Skype for Business Online.</span></span> <span data-ttu-id="39868-119">자세한 내용은 [Office 365 PowerShell을 사용 하 여 비즈니스용 Skype Online 관리](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="39868-119">For more information, please see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="39868-120">[비즈니스용 Skype cmdlet 모듈](https://www.microsoft.com/download/details.aspx?id=39366)에서 정책을 관리 하는 cmdlet을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="39868-120">Find the cmdlets for managing policies in the [Skype for Business cmdlet module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>

<span data-ttu-id="39868-121">정책은 개인 사용자에 게 granularly 적용할 수 있는 설정 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="39868-121">A policy is a group of settings that can be applied granularly to individual users.</span></span> <span data-ttu-id="39868-122">각 정책 형식에는 정책 자체를 만들고, 보고, 삭제 하 고, 업데이트 하 고, 해당 정책을 사용자에 게 할당할 수 있는 고유한 cmdlet 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39868-122">Each policy type has its own set of cmdlets for creating, viewing, deleting, and updating the policies themselves, and then assigning those policies to users.</span></span> <span data-ttu-id="39868-123">일반적인 구조는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="39868-123">The general structure is:</span></span>

- <span data-ttu-id="39868-124">**GET** 명령 (예 ``Get-CsTeamsMeetingPolicy`` :)을 사용 하면 Microsoft에서 만든 정책 외에도 사용자가 만든 해당 정책에 따라 조직에서 할당할 수 있는 정책 문서를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="39868-124">**GET** commands (for example, ``Get-CsTeamsMeetingPolicy``): Returns the policy documents that are available for you to assign in your organization, including the policies created by Microsoft for you to use as well as the custom policies you’ve created.</span></span>
   - <span data-ttu-id="39868-125">조직에서 만든 사용자 지정 정책만 찾으려면을 사용 ``-Filter "tag:*"`` 합니다.</span><span class="sxs-lookup"><span data-stu-id="39868-125">To find only the custom policies you’ve created in your organization, use ``-Filter "tag:*"``.</span></span>

- <span data-ttu-id="39868-126">**새로운** 명령 (예 ``New-CsTeamsMeetingPolicy`` :)은 조직에서 조직의 사용자에 게 할당할 새 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="39868-126">**NEW** commands (for example, ``New-CsTeamsMeetingPolicy``): Creates new policies for your organization to assign to users in your organization.</span></span> <span data-ttu-id="39868-127">모든 정책이 사용자 지정 정책 만들기를 지원 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="39868-127">Not all policies support the creation of custom policies.</span></span> <span data-ttu-id="39868-128">조직에서 사용 하는 정책에 지원 되는 설정 조합이 있는지 확인 하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="39868-128">Often this is to ensure that the policies you use in your organization have a supported combination of settings.</span></span>

- <span data-ttu-id="39868-129">**SET** 명령 (예 ``Set-CsTeamsMeetingPolicy`` :)을 설정 합니다. 지정 된 정책에 특정 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="39868-129">**SET** commands (for example, ``Set-CsTeamsMeetingPolicy``): Sets particular values on a given policy.</span></span> <span data-ttu-id="39868-130">일부 정책에 사용할 수 있는 명령이 설정 되어 있지 않거나 정책에서 사용자 지정할 수 없는 매개 변수가 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="39868-130">Some policies don't have SET commands available, or they contain parameters that can't be customized in the policy.</span></span> <span data-ttu-id="39868-131">PowerShell 설명은 사용자 지정할 수 없는 매개 변수를 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="39868-131">The PowerShell descriptions tell you which parameters can't be customized.</span></span> 
   - <span data-ttu-id="39868-132">사용자 지정 정책이 할당 되지 않은 조직의 사용자에 게 기본적으로 할당 되는 정책을 편집 하려면를 실행 ``Set-Cs<PolicyName> -Identity Global`` 합니다.</span><span class="sxs-lookup"><span data-stu-id="39868-132">To edit the policy that will by default be assigned to users in your organization who do not have a custom policy assigned, run ``Set-Cs<PolicyName> -Identity Global``.</span></span>

- <span data-ttu-id="39868-133">명령 **제거** (예를 들어 ``Remove-CsTeamsMeetingPolicy`` ): 테 넌 트에서 만든 사용자 지정 정책을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="39868-133">**REMOVE** commands (for example, ``Remove-CsTeamsMeetingPolicy``): Deletes a custom policy that has been created in your tenant.</span></span> <span data-ttu-id="39868-134">조직에서 하나 이상의 사용자에 게 할당 된 사용자 지정 정책을 삭제 하는 경우 해당 사용자는 전역 정책으로 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39868-134">If you delete a custom policy that has been assigned to at least one user in your organization, that user will fall back to the global policy.</span></span>
   - <span data-ttu-id="39868-135">조직에서 글로벌 정책을 실제로 제거할 수는 없지만 조직의 전역 정책을 Microsoft에서 제공 하는 기본 설정으로 다시 설정 하려는 경우에는를 실행 ``Remove-Cs<PolicyName> -Identity Global`` 합니다.</span><span class="sxs-lookup"><span data-stu-id="39868-135">You can’t actually remove the global policy in your organization, but if you want to reset the global policy in your organization to the Microsoft-provided default settings, run ``Remove-Cs<PolicyName> -Identity Global``.</span></span>

- <span data-ttu-id="39868-136">**허용** 명령 (예를 들어 ``Grant-CsTeamsMeetingPolicy`` ): 특정 사용자에 게 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="39868-136">**GRANT** command (for example, ``Grant-CsTeamsMeetingPolicy``): Assigns a policy to a particular user.</span></span>
   - <span data-ttu-id="39868-137">사용자 지정 정책 할당을 제거 하 고 사용자가 조직의 기본 정책으로 돌아갈 수 있도록 설정 하려면를 실행 ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` 합니다.</span><span class="sxs-lookup"><span data-stu-id="39868-137">To remove a custom policy assignment and make the user fall back to the default policy in your organization, run ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null``.</span></span>

> [!TIP]
> <span data-ttu-id="39868-138">모든 정책에서 사용자 지정 정책을 만들 수 있는 것은 아니지만 일부 정책에는 사용자 지정할 수 없는 설정이 포함 되어 있으므로 설정을 볼 수 있지만 및 중에 사용자 지정 값을 설정할 수는 없습니다 ``set-`` ``new-`` .</span><span class="sxs-lookup"><span data-stu-id="39868-138">Not all policies allow custom policies to be created, and some policies have settings that you can’t customize (so you can view the setting but can’t set a custom value during ``set-`` and ``new-``).</span></span> <span data-ttu-id="39868-139">각 cmdlet에 대 한 설명서는 고객이 매개 변수를 사용할 수 있는지 여부를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="39868-139">The documentation for each cmdlet calls out whether parameters are available for use by customers.</span></span>

<span data-ttu-id="39868-140">공통 매개 변수:</span><span class="sxs-lookup"><span data-stu-id="39868-140">Common parameters:</span></span>

- <span data-ttu-id="39868-141">**Id**:, ``Get-`` , ``Set-`` ``New-`` , 및 ``Remove-`` 에서 **id** 매개 변수는 항상 특정 정책 인스턴스를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="39868-141">**Identity**: For ``Get-``, ``Set-``, ``New-``, and ``Remove-``, the **Identity** parameter will always refer to a specific policy instance.</span></span> <span data-ttu-id="39868-142">의 ``Grant`` 경우 **Identity** 매개 변수는 정책이 적용 되는 특정 사용자 개체를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="39868-142">For ``Grant``, the **Identity** parameter refers to a specific user object to whom the policy is being applied.</span></span>

## <a name="manage-configurations-via-powershell"></a><span data-ttu-id="39868-143">PowerShell을 통해 구성 관리</span><span class="sxs-lookup"><span data-stu-id="39868-143">Manage configurations via PowerShell</span></span>

<span data-ttu-id="39868-144">[비즈니스용 Skype cmdlet 모듈](https://www.microsoft.com/en-us/download/details.aspx?id=39366)에서 구성을 관리 하기 위한 cmdlet을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="39868-144">Find the cmdlets for managing your configuration in the [Skype for Business cmdlet module](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span>

<span data-ttu-id="39868-145">구성은 사용자 수준에서 지정할 수 없는 서비스에서 유지 관리 되는 설정의 버킷을 말합니다.</span><span class="sxs-lookup"><span data-stu-id="39868-145">Configurations are buckets of settings maintained in the service that can't be specified at a user level.</span></span> <span data-ttu-id="39868-146">설정은 항상 전체 조직에서 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39868-146">Settings always apply across the whole organization.</span></span> <span data-ttu-id="39868-147">글로벌 구성은 조직의 유일한 유효 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="39868-147">Your global configuration is the only effective configuration in your organization.</span></span> <span data-ttu-id="39868-148">각 구성 유형에는 두 가지 기본 cmdlet이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39868-148">Each configuration type comes with two primary cmdlets:</span></span>

- <span data-ttu-id="39868-149">``Get-Cs<ConfigurationName>``(예를 들어 ``Get-CsTeamsClientConfiguration`` ) 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="39868-149">``Get-Cs<ConfigurationName>`` (for example, ``Get-CsTeamsClientConfiguration``):</span></span>

- <span data-ttu-id="39868-150">명령 (예:)을 설정 합니다. ``Set-CsTeamsClientConfiguration`` 해당 형식의 구성에서 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="39868-150">SET commands (for example, ``Set-CsTeamsClientConfiguration``): set properties in the configuration of that type.</span></span> <span data-ttu-id="39868-151">수정 하려는 매개 변수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="39868-151">Specify the parameters that you want to modify.</span></span>
   > <span data-ttu-id="39868-152">**Id 전역**을 지정 하거나를 실행 하 여 두 가지 방법 중 하나로 수정 하는 구성을 참조할 수 있습니다 ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>`` .</span><span class="sxs-lookup"><span data-stu-id="39868-152">You can reference the configuration that you’re modifying in one of two ways: by specifying -**Identity Global**, or by running ``Get-Cs<ConfigurationName>`` | ``Set-Cs<ConfigurationName>``.</span></span>

## <a name="what-can-each-admin-role-do"></a><span data-ttu-id="39868-153">각 관리자 역할이 수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="39868-153">What can each admin role do?</span></span>

<span data-ttu-id="39868-154">[Microsoft 팀 관리자 역할을 사용 하 여 팀을 관리 하](using-admin-roles.md) 여 각 PowerShell cmdlet을 실행할 수 있는 관리자 역할을 파악 합니다.</span><span class="sxs-lookup"><span data-stu-id="39868-154">Read [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md) to understand which admin roles can run each PowerShell cmdlet.</span></span>

## <a name="related-topics"></a><span data-ttu-id="39868-155">관련 항목</span><span class="sxs-lookup"><span data-stu-id="39868-155">Related topics</span></span>

[<span data-ttu-id="39868-156">팀 PowerShell 설치</span><span class="sxs-lookup"><span data-stu-id="39868-156">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="39868-157">팀 PowerShell 릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="39868-157">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="39868-158">팀 cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="39868-158">Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="39868-159">비즈니스용 Skype cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="39868-159">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="39868-160">Teams 관리자 역할을 사용하여 Teams를 관리</span><span class="sxs-lookup"><span data-stu-id="39868-160">Use Teams admin roles to manage Teams</span></span>](using-admin-roles.md)