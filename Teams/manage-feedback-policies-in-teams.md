---
title: Microsoft 팀에서 피드백 정책 관리
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: msedliak
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 조직의 팀 사용자가 Microsoft에 팀에 대 한 피드백을 제출할 수 있는지 여부를 제어 하는 데 피드백 정책을 사용 하는 방법을 알아봅니다.
ms.openlocfilehash: 3c9d05a3003906377447ee119b8cfc9bd137db81
ms.sourcegitcommit: f26bb86d38c3b45a82e6d77c5aa521360a81ee9b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2019
ms.locfileid: "36184682"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="3a8db-103">Microsoft 팀에서 피드백 정책 관리</span><span class="sxs-lookup"><span data-stu-id="3a8db-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="3a8db-104">팀 클라이언트에서 \*\*\*\* > **피드백을 제공** 하기 위해 사용자는 팀에 대 한 의견 및 제안을 Microsoft에 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8db-104">Users can send comments and suggestions about Teams to Microsoft by going to **Help** > **Give feedback** in the Teams clients.</span></span> <span data-ttu-id="3a8db-105">팀 경험을 지속적으로 개선 하 고 있으며,이 피드백을 사용 하 여 팀을 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8db-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

![팀의 피드백 제공 옵션 스크린샷](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="3a8db-107">**의견 제공** 을 통해 전송 되는 데이터는 "고객 데이터" 또는 "개인 데이터"로 간주 되는 정보를 포함 하 여 Office 365 계약에 "지원 데이터"로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a8db-107">Data sent through **Give feedback** is considered as "Support Data" under your Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="3a8db-108">사용자가 Microsoft에 팀에 대 한 피드백을 보낼 수 있는지 여부 설정</span><span class="sxs-lookup"><span data-stu-id="3a8db-108">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="3a8db-109">관리자는 조직의 사용자가 Microsoft에 팀에 대 한 피드백을 보낼 수 있는지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8db-109">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft.</span></span> <span data-ttu-id="3a8db-110">기본적으로 조직의 모든 사용자에 게 전역 (조직 전체 기본값) 정책이 자동으로 할당 되며 정책에서 해당 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8db-110">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the feature is enabled in the policy.</span></span> <span data-ttu-id="3a8db-111">이 예외는 교사를 위해 기능을 사용 하도록 설정 하 고 학생에 게 사용할 수 없는 교육용 팀입니다.</span><span class="sxs-lookup"><span data-stu-id="3a8db-111">The exception is Teams for Education, where the feature is enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="3a8db-112">전역 정책을 편집 하거나 사용자 지정 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8db-112">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="3a8db-113">사용자가 사용자 지정 정책을 할당 한 경우 해당 정책이 사용자에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a8db-113">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="3a8db-114">사용자가 사용자 지정 정책을 할당 하지 않으면 전역 정책이 사용자에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a8db-114">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span> <span data-ttu-id="3a8db-115">전역 정책을 편집 하거나 정책을 할당 한 후 변경 내용이 적용 되는 데 최대 24 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8db-115">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

<span data-ttu-id="3a8db-116">예를 들어 조직의 모든 사용자가 교육의 새 고용를 제외 하 고 의견을 보낼 수 있도록 하려는 경우를 예로 들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8db-116">Say, for example, you want to allow all users in your organization to send feedback except for new hires in training.</span></span> <span data-ttu-id="3a8db-117">이 시나리오에서는 사용자 지정 정책을 만들어 기능을 끄고 새 고용에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8db-117">In this scenario, you create a custom policy to turn off the feature and assign it to new hires.</span></span> <span data-ttu-id="3a8db-118">조직의 다른 모든 사용자는 기능이 설정 된 전역 정책을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8db-118">All other users in your organization get the global policy with the feature turned on.</span></span>  

<span data-ttu-id="3a8db-119">**CsTeamsFeedbackPolicy** cmdlet을 사용 하 여 사용자 지정 정책 및 **허용-CsTeamsFeedbackPolicy** cmdlet을 만들어 보안 그룹 또는 메일 그룹과 같은 하나 이상의 사용자 또는 사용자 그룹에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8db-119">You use the **New-CsTeamsFeedbackPolicy** cmdlet to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span> 

<span data-ttu-id="3a8db-120">**UserInitiatedMode** 매개 변수를 **enabled** 로 설정 하면 정책에 할당 된 사용자가 피드백을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8db-120">Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="3a8db-121">매개 변수를 **disabled** 로 설정 하면 기능이 해제 되 고 정책에 할당 된 사용자에 게 피드백을 제공 하는 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8db-121">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="3a8db-122">사용자 지정 피드백 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="3a8db-122">Create a custom feedback policy</span></span>

<span data-ttu-id="3a8db-123">이 예제에서는 새 고용 피드백 정책 이라고 하는 피드백 정책을 만들고 피드백을 제공 하는 기능을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8db-123">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback.</span></span>

```
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled
```

## <a name="assign-a-custom-feedback-policy"></a><span data-ttu-id="3a8db-124">사용자 지정 피드백 정책 지정</span><span class="sxs-lookup"><span data-stu-id="3a8db-124">Assign a custom feedback policy</span></span>

### <a name="assign-a-custom-feedback-policy-to-a-user"></a><span data-ttu-id="3a8db-125">사용자에 게 사용자 지정 피드백 정책 할당</span><span class="sxs-lookup"><span data-stu-id="3a8db-125">Assign a custom feedback policy to a user</span></span>

<span data-ttu-id="3a8db-126">이 예제에서는 user1 이라는 사용자에 게 새 채용 사용자 의견 정책 이라는 사용자 지정 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8db-126">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```
### <a name="assign-a-custom-feedback-policy-to-users-in-a-group"></a><span data-ttu-id="3a8db-127">그룹의 사용자에 게 사용자 지정 피드백 정책 할당</span><span class="sxs-lookup"><span data-stu-id="3a8db-127">Assign a custom feedback policy to users in a group</span></span>

<span data-ttu-id="3a8db-128">이미 식별 한 여러 사용자에 게 사용자 지정 피드백 정책을 할당 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8db-128">You may want to assign a custom feedback policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="3a8db-129">예를 들어 보안 그룹의 모든 사용자에 게 정책을 할당 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8db-129">For example, you may want to assign a policy to all users in a security group.</span></span>

<span data-ttu-id="3a8db-130">이 예제에서는 Contoso 새 고용 그룹의 모든 사용자에 게 새 채용 사용자 의견 정책 이라는 사용자 지정 피드백 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8db-130">In this example, we assign a custom feedback policy called New Hire Feedback Policy to all users in the Contoso New Hires group.</span></span>  

<span data-ttu-id="3a8db-131">특정 그룹의 GroupObjectId를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3a8db-131">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso New Hires"
```
<span data-ttu-id="3a8db-132">지정 된 그룹의 구성원을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3a8db-132">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="3a8db-133">그룹의 모든 사용자를 특정 피드백 정책에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8db-133">Assign all users in the group to a particular feedback policy.</span></span> <span data-ttu-id="3a8db-134">이 예제에서는 새 채용에 대 한 의견 수집 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="3a8db-134">In this example, it's New Hire Feedback Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsFeedbackPolicy -PolicyName "New Hire Feedback Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="3a8db-135">그룹의 구성원 수에 따라이 명령을 실행 하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8db-135">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3a8db-136">관련 항목</span><span class="sxs-lookup"><span data-stu-id="3a8db-136">Related topics</span></span>

- [<span data-ttu-id="3a8db-137">팀 PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="3a8db-137">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)