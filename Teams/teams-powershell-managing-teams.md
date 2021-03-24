---
title: Microsoft Teams PowerShell을 사용하여 Teams 관리
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
description: Teams PowerShell을 사용하여 Microsoft Teams를 관리하는 방법을 학습합니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: bd302e2e5572c98e3338f0803155876e1c7689fc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094148"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a><span data-ttu-id="78fd4-103">Microsoft Teams PowerShell을 사용하여 Teams 관리</span><span class="sxs-lookup"><span data-stu-id="78fd4-103">Manage Teams with Microsoft Teams PowerShell</span></span>

<span data-ttu-id="78fd4-104">이 문서에서는 Microsoft Teams PowerShell을 사용하여 Teams 및 비즈니스용 Skype를 관리하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-104">This article shows you how to use Microsoft Teams PowerShell to manage Teams and Skype for Business.</span></span> 

<span data-ttu-id="78fd4-105">[Microsoft Teams cmdlet](/powershell/teams/?view=teams-ps) 참조 및 [비즈니스용 Skype cmdlet 참조와](/powershell/skype/intro?view=skype-ps)함께 이 지침을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="78fd4-105">Use this guidance in conjunction with the [Microsoft Teams cmdlet reference](/powershell/teams/?view=teams-ps) and [Skype for Business cmdlet reference](/powershell/skype/intro?view=skype-ps).</span></span>

## <a name="create-and-manage-teams-using-powershell"></a><span data-ttu-id="78fd4-106">PowerShell을 사용하여 팀 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="78fd4-106">Create and manage teams using PowerShell</span></span>

<span data-ttu-id="78fd4-107">팀을 만들고 관리하기 위한 [cmdlet은 Microsoft Teams PowerShell 모듈 에 있습니다.](https://www.powershellgallery.com/packages/MicrosoftTeams/)</span><span class="sxs-lookup"><span data-stu-id="78fd4-107">The cmdlets for creating and managing teams are in the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams/).</span></span>

<span data-ttu-id="78fd4-108">팀은 Office 365 그룹에서 백업됩니다. 따라서 팀을 만들 때 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-108">Teams are backed by Office 365 Groups, so when you create a team, you create a group.</span></span> <span data-ttu-id="78fd4-109">팀의 채널을 관리하기 위한 ``new-team`` ``get-team``  ``set-team`` ``add-teamuser`` ``remove-teamuser`` cmdlet뿐만 ``new-teamchannel`` 아니라 핵심 팀 및 해당 설정(, , ) 관리 팀 사용자(, ) 에서 작동하기 위해 제공되는 cmdlet 집합이 ``remove-teamchannel`` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-109">There are a set of cmdlets provided for operating on the core team and its settings (``new-team``, ``get-team``,  ``set-team``), managing team users (``add-teamuser``, ``remove-teamuser``), as well as cmdlets for managing the channels of the team (``new-teamchannel``, ``remove-teamchannel``).</span></span> <span data-ttu-id="78fd4-110">이러한 모든 cmdlet은 최종 사용자로 실행할 수 있지만 사용자가 소유하거나 구성원인 팀에서만 작동하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-110">All of these cmdlets can be run as end users, but they'll work only on the teams that you own or are a member of.</span></span> <span data-ttu-id="78fd4-111">글로벌 관리자 또는 Teams 서비스 관리자인 경우 조직의 모든 팀에 대해 행동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-111">If you are a Global Admin or Teams Service Administrator, you'll be able to act on all teams in your organization.</span></span>

```powershell
New-Team -Name "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> <span data-ttu-id="78fd4-112">Microsoft Teams PowerShell 모듈 cmdlet에 사용되는 **GroupId는** Exchange PowerShell 모듈에서 반환한 **ID** 속성과 ``Get-UnifiedGroup`` 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-112">The **GroupId** used in the Microsoft Teams PowerShell module cmdlets is the same as the **Identity** property returned by ``Get-UnifiedGroup`` in the Exchange PowerShell module.</span></span>

## <a name="manage-policies-via-powershell"></a><span data-ttu-id="78fd4-113">PowerShell을 통해 정책 관리</span><span class="sxs-lookup"><span data-stu-id="78fd4-113">Manage policies via PowerShell</span></span>

> [!NOTE]
> - <span data-ttu-id="78fd4-114">비즈니스용 Skype Online 커넥터가 Teams PowerShell에 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-114">Skype for Business Online Connector is being consolidated into Teams PowerShell.</span></span> <span data-ttu-id="78fd4-115">현재 공개 미리 보기에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-115">It is currently available in public preview.</span></span> <span data-ttu-id="78fd4-116">시간이 지날 때 Teams에 적용되는 비즈니스용 Skype Online cmdlet은 Teams PowerShell 모듈에서 기본적으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-116">In time, Skype for Business Online cmdlets that apply to Teams will be natively available in the Teams PowerShell module.</span></span> <span data-ttu-id="78fd4-117">설치 단계는 Teams [PowerShell 설치](teams-powershell-install.md) 문서에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-117">Installation steps are available in the [Install Teams PowerShell](teams-powershell-install.md) article.</span></span>
>
> - <span data-ttu-id="78fd4-118">비즈니스용 Skype Online에 연결하면 PowerShell 세션에서 cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-118">The cmdlets will be available in your PowerShell session once you connect to Skype for Business Online.</span></span> <span data-ttu-id="78fd4-119">자세한 내용은 Office [365 PowerShell을 사용하여 비즈니스용 Skype Online 관리를 참조하세요.](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="78fd4-119">For more information, please see [Manage Skype for Business Online with Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="78fd4-120">비즈니스용 Skype cmdlet 모듈에서 정책을 관리하기 위한 [cmdlet을 찾을 수 있습니다.](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="78fd4-120">Find the cmdlets for managing policies in the [Skype for Business cmdlet module](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell).</span></span>

<span data-ttu-id="78fd4-121">정책은 개별 사용자에게 세분화하여 적용할 수 있는 설정 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-121">A policy is a group of settings that can be applied granularly to individual users.</span></span> <span data-ttu-id="78fd4-122">각 정책 유형에는 정책을 만들고, 보고, 삭제하고, 업데이트한 다음 사용자에게 해당 정책을 할당하기 위한 자체 cmdlet 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-122">Each policy type has its own set of cmdlets for creating, viewing, deleting, and updating the policies themselves, and then assigning those policies to users.</span></span> <span data-ttu-id="78fd4-123">일반적인 구조는:</span><span class="sxs-lookup"><span data-stu-id="78fd4-123">The general structure is:</span></span>

- <span data-ttu-id="78fd4-124">**GET** 명령(예: ): 조직에서 할당할 수 있는 정책 문서를 반환합니다( Microsoft에서 만든 정책 및 만든 사용자 지정 정책 ``Get-CsTeamsMeetingPolicy`` 포함).</span><span class="sxs-lookup"><span data-stu-id="78fd4-124">**GET** commands (for example, ``Get-CsTeamsMeetingPolicy``): Returns the policy documents that are available for you to assign in your organization, including the policies created by Microsoft for you to use as well as the custom policies you’ve created.</span></span>
   - <span data-ttu-id="78fd4-125">조직에서 만든 사용자 지정 정책만 찾으면 ``-Filter "tag:*"`` 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-125">To find only the custom policies you’ve created in your organization, use ``-Filter "tag:*"``.</span></span>

- <span data-ttu-id="78fd4-126">**NEW** 명령(예: ): 조직의 사용자에게 할당할 조직에 대한 새 정책을 ``New-CsTeamsMeetingPolicy`` 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-126">**NEW** commands (for example, ``New-CsTeamsMeetingPolicy``): Creates new policies for your organization to assign to users in your organization.</span></span> <span data-ttu-id="78fd4-127">모든 정책이 사용자 지정 정책 만들기를 지원하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-127">Not all policies support the creation of custom policies.</span></span> <span data-ttu-id="78fd4-128">조직에서 사용하는 정책에 지원되는 설정 조합이 되도록 하는 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-128">Often this is to ensure that the policies you use in your organization have a supported combination of settings.</span></span>

- <span data-ttu-id="78fd4-129">**SET** 명령(예: ): 특정 정책에서 ``Set-CsTeamsMeetingPolicy`` 특정 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-129">**SET** commands (for example, ``Set-CsTeamsMeetingPolicy``): Sets particular values on a given policy.</span></span> <span data-ttu-id="78fd4-130">일부 정책에는 SET 명령을 사용할 수 없는 경우 또는 정책에서 사용자 지정할 수 없는 매개 변수가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-130">Some policies don't have SET commands available, or they contain parameters that can't be customized in the policy.</span></span> <span data-ttu-id="78fd4-131">PowerShell 설명에서는 사용자 지정할 수 없는 매개 변수를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-131">The PowerShell descriptions tell you which parameters can't be customized.</span></span> 
   - <span data-ttu-id="78fd4-132">사용자 지정 정책이 할당되지 않은 조직의 사용자에게 기본적으로 할당될 정책을 편집하려면 ``Set-Cs<PolicyName> -Identity Global`` 을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-132">To edit the policy that will by default be assigned to users in your organization who do not have a custom policy assigned, run ``Set-Cs<PolicyName> -Identity Global``.</span></span>

- <span data-ttu-id="78fd4-133">**REMOVE** 명령(예: ): 테넌트에서 만든 사용자 지정 정책을 ``Remove-CsTeamsMeetingPolicy`` 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-133">**REMOVE** commands (for example, ``Remove-CsTeamsMeetingPolicy``): Deletes a custom policy that has been created in your tenant.</span></span> <span data-ttu-id="78fd4-134">조직에서 하나 이상의 사용자에게 할당된 사용자 지정 정책을 삭제하면 해당 사용자가 전역 정책으로 돌아가게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-134">If you delete a custom policy that has been assigned to at least one user in your organization, that user will fall back to the global policy.</span></span>
   - <span data-ttu-id="78fd4-135">조직의 전역 정책을 실제로 제거할 수 없지만 조직의 전역 정책을 Microsoft에서 제공한 기본 설정으로 다시 설정하려면 을 ``Remove-Cs<PolicyName> -Identity Global`` 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-135">You can’t actually remove the global policy in your organization, but if you want to reset the global policy in your organization to the Microsoft-provided default settings, run ``Remove-Cs<PolicyName> -Identity Global``.</span></span>

- <span data-ttu-id="78fd4-136">**GRANT** 명령(예: ): 특정 사용자에게 정책을 ``Grant-CsTeamsMeetingPolicy`` 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-136">**GRANT** command (for example, ``Grant-CsTeamsMeetingPolicy``): Assigns a policy to a particular user.</span></span>
   - <span data-ttu-id="78fd4-137">사용자 지정 정책 할당을 제거하고 사용자가 조직의 기본 정책으로 돌아가게하려면 ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` 을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-137">To remove a custom policy assignment and make the user fall back to the default policy in your organization, run ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null``.</span></span>

> [!TIP]
> <span data-ttu-id="78fd4-138">모든 정책이 사용자 지정 정책을 만들 수 있는 것은 아니며, 일부 정책에는 사용자 지정할 수 없는 설정이 있습니다(따라서 설정을 볼 수 있지만 및 동안에는 사용자 지정 값을 설정할 수 ``set-`` ``new-`` 없습니다).</span><span class="sxs-lookup"><span data-stu-id="78fd4-138">Not all policies allow custom policies to be created, and some policies have settings that you can’t customize (so you can view the setting but can’t set a custom value during ``set-`` and ``new-``).</span></span> <span data-ttu-id="78fd4-139">각 cmdlet에 대한 설명서는 고객이 매개 변수를 사용할 수 있는지 여부를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-139">The documentation for each cmdlet calls out whether parameters are available for use by customers.</span></span>

<span data-ttu-id="78fd4-140">일반적인 매개 변수:</span><span class="sxs-lookup"><span data-stu-id="78fd4-140">Common parameters:</span></span>

- <span data-ttu-id="78fd4-141">**ID**: 의 경우 , 및 의 경우 ID 매개 변수는 항상 특정 정책 ``Get-`` ``Set-`` ``New-`` ``Remove-`` 인스턴스를 참조합니다. </span><span class="sxs-lookup"><span data-stu-id="78fd4-141">**Identity**: For ``Get-``, ``Set-``, ``New-``, and ``Remove-``, the **Identity** parameter will always refer to a specific policy instance.</span></span> <span data-ttu-id="78fd4-142">의 경우 ID 매개 변수는 정책이 적용되는 특정 사용자 개체를 ``Grant`` 참조합니다. </span><span class="sxs-lookup"><span data-stu-id="78fd4-142">For ``Grant``, the **Identity** parameter refers to a specific user object to whom the policy is being applied.</span></span>

## <a name="manage-configurations-via-powershell"></a><span data-ttu-id="78fd4-143">PowerShell을 통해 구성 관리</span><span class="sxs-lookup"><span data-stu-id="78fd4-143">Manage configurations via PowerShell</span></span>

<span data-ttu-id="78fd4-144">비즈니스용 Skype cmdlet 모듈에서 구성을 관리하기 위한 [cmdlet을 찾습니다.](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="78fd4-144">Find the cmdlets for managing your configuration in the [Skype for Business cmdlet module](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell).</span></span>

<span data-ttu-id="78fd4-145">구성은 사용자 수준에서 지정할 수 없는 서비스에서 유지 관리되는 설정의 버킷입니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-145">Configurations are buckets of settings maintained in the service that can't be specified at a user level.</span></span> <span data-ttu-id="78fd4-146">설정은 항상 전체 조직에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-146">Settings always apply across the whole organization.</span></span> <span data-ttu-id="78fd4-147">전역 구성은 조직에서 유일한 효과적인 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-147">Your global configuration is the only effective configuration in your organization.</span></span> <span data-ttu-id="78fd4-148">각 구성 유형에는 두 개의 기본 cmdlet이 함께 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-148">Each configuration type comes with two primary cmdlets:</span></span>

- <span data-ttu-id="78fd4-149">``Get-Cs<ConfigurationName>`` (예: ``Get-CsTeamsClientConfiguration`` ):</span><span class="sxs-lookup"><span data-stu-id="78fd4-149">``Get-Cs<ConfigurationName>`` (for example, ``Get-CsTeamsClientConfiguration``):</span></span>

- <span data-ttu-id="78fd4-150">SET 명령(예: ): 해당 형식의 구성에서 속성을 ``Set-CsTeamsClientConfiguration`` 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-150">SET commands (for example, ``Set-CsTeamsClientConfiguration``): set properties in the configuration of that type.</span></span> <span data-ttu-id="78fd4-151">수정할 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-151">Specify the parameters that you want to modify.</span></span>
   > <span data-ttu-id="78fd4-152">을 지정하거나 를 실행하여 두 가지 방법 중 하나에서 수정하는 구성을 참조할 수 ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>`` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-152">You can reference the configuration that you’re modifying in one of two ways: by specifying -**Identity Global**, or by running ``Get-Cs<ConfigurationName>`` | ``Set-Cs<ConfigurationName>``.</span></span>

## <a name="what-can-each-admin-role-do"></a><span data-ttu-id="78fd4-153">각 관리자 역할은 무엇을 할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="78fd4-153">What can each admin role do?</span></span>

<span data-ttu-id="78fd4-154">Microsoft Teams 관리자 역할을 사용하여 [Teams를](using-admin-roles.md) 관리하여 각 PowerShell cmdlet을 실행할 수 있는 관리자 역할을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="78fd4-154">Read [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md) to understand which admin roles can run each PowerShell cmdlet.</span></span>

## <a name="related-topics"></a><span data-ttu-id="78fd4-155">관련 항목</span><span class="sxs-lookup"><span data-stu-id="78fd4-155">Related topics</span></span>

[<span data-ttu-id="78fd4-156">Teams PowerShell 설치</span><span class="sxs-lookup"><span data-stu-id="78fd4-156">Installing Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="78fd4-157">Teams PowerShell 릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="78fd4-157">Teams PowerShell Release Notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="78fd4-158">Teams cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="78fd4-158">Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="78fd4-159">비즈니스용 Skype cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="78fd4-159">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)

[<span data-ttu-id="78fd4-160">Teams 관리자 역할을 사용하여 Teams를 관리</span><span class="sxs-lookup"><span data-stu-id="78fd4-160">Use Teams admin roles to manage Teams</span></span>](using-admin-roles.md)