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
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 조직의 팀 사용자가 Microsoft에 팀에 대 한 피드백을 제출할 수 있는지 여부를 제어 하는 데 피드백 정책을 사용 하는 방법을 알아봅니다.
ms.openlocfilehash: 78a6f0856d8b973ecfa1c8af52ee50480be0e838
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991423"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="4db5b-103">Microsoft 팀에서 피드백 정책 관리</span><span class="sxs-lookup"><span data-stu-id="4db5b-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="4db5b-104">조직의 사용자는 팀에 대 한 피드백을 Microsoft에 보내 팀 데스크톱 및 웹 클라이언트 내에서 바로 수행 하는 방법을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-104">Users in your organization can send feedback about Teams to Microsoft let us know how we're doing, directly from within the Teams desktop and web clients.</span></span> <span data-ttu-id="4db5b-105">팀 경험을 지속적으로 개선 하 고 있으며,이 피드백을 사용 하 여 팀을 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

<span data-ttu-id="4db5b-106">**피드백 제공 기능**</span><span class="sxs-lookup"><span data-stu-id="4db5b-106">**The Give feedback feature**</span></span>

<span data-ttu-id="4db5b-107">팀에 > **의견을 제공** **하기 위해**팀에 대 한 의견 및 제안을 사용자에 게 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-107">Users can send comments and suggestions about Teams to us by going to **Help** > **Give feedback** in Teams.</span></span> <span data-ttu-id="4db5b-108">**의견 제공** 을 통해 전송 되는 데이터는 "고객 데이터" 또는 "개인 데이터"로 간주 되는 정보를 포함 하 여 Office 365 계약에 "지원 데이터"로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-108">Data sent through **Give feedback** is considered as "Support Data" under your Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

![팀의 피드백 제공 옵션 스크린샷](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="4db5b-110">**조사**</span><span class="sxs-lookup"><span data-stu-id="4db5b-110">**Surveys**</span></span>

<span data-ttu-id="4db5b-111">또한 사용자는 팀과 함께 경험을 평가 하 고 제공 된 등급에 대 한 세부 정보를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-111">Users can also rate their experience with Teams and send us details about the rating they give.</span></span> <span data-ttu-id="4db5b-112">이 팝업 설문 조사는 팀의 시간을 사용자에 게 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-112">This pop-up survey is displayed to users from time-to-time in Teams.</span></span> <span data-ttu-id="4db5b-113">사용자가 알림에서 **피드백 제공** 을 클릭 하면 설문 조사가 완료 될 때까지 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-113">When a user clicks **Provide feedback** in the notification, the survey is displayed for them to complete.</span></span>

![팀의 설문 조사 알림 및 양식 스크린샷](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="4db5b-115">사용자가 Microsoft에 팀에 대 한 피드백을 보낼 수 있는지 여부 설정</span><span class="sxs-lookup"><span data-stu-id="4db5b-115">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="4db5b-116">관리자는 조직의 사용자가 **피드백을 제공** 하 고 설문 조사를 받을지 여부를 통해 Microsoft에 팀에 대 한 피드백을 보낼 수 있는지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-116">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft through **Give feedback** and whether they receive the survey.</span></span> <span data-ttu-id="4db5b-117">기본적으로 조직의 모든 사용자에 게 전역 (조직 전체 기본값) 정책이 자동으로 할당 되며 **사용자 의견 제공** 기능 및 설문 조사가 정책에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-117">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the **Give feedback** feature and survey are enabled in the policy.</span></span> <span data-ttu-id="4db5b-118">예외는 교사를 위해 기능을 사용 하도록 설정 하 고 학생 들이 사용할 수 없도록 하는 교육용 팀입니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-118">The exception is Teams for Education, where the features are enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="4db5b-119">전역 정책을 편집 하거나 사용자 지정 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-119">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="4db5b-120">사용자가 사용자 지정 정책을 할당 한 경우 해당 정책이 사용자에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-120">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="4db5b-121">사용자가 사용자 지정 정책을 할당 하지 않으면 전역 정책이 사용자에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-121">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span> <span data-ttu-id="4db5b-122">전역 정책을 편집 하거나 정책을 할당 한 후 변경 내용이 적용 되는 데 최대 24 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-122">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

<span data-ttu-id="4db5b-123">예를 들어 조직의 모든 사용자가 교육에 대 한 새로운 채용을 제외 하 고 **피드백을 제공** 하 고 설문 조사를 통해 피드백을 보낼 수 있도록 하려는 경우를 예로 들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-123">Say, for example, you want to allow all users in your organization to send feedback through **Give feedback** and receive surveys except for new hires in training.</span></span> <span data-ttu-id="4db5b-124">이 시나리오에서는 두 기능을 해제 하 고 새 고용에 할당 하는 사용자 지정 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-124">In this scenario, you create a custom policy to turn off both features and assign it to new hires.</span></span> <span data-ttu-id="4db5b-125">조직의 다른 모든 사용자는 기능이 설정 된 전역 정책을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-125">All other users in your organization get the global policy with the features turned on.</span></span>  

<span data-ttu-id="4db5b-126">\* [여기서 찾을](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)수 있는\* **New CsTeamsFeedbackPolicy** cmdlet을 사용 하 여 사용자 지정 정책 및 **허용-CsTeamsFeedbackPolicy** cmdlet을 만들어 보안 그룹 또는 메일 그룹과 같은 하나 이상의 사용자 또는 사용자 그룹에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-126">You use the **New-CsTeamsFeedbackPolicy** cmdlet, *which can be [found here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span>

<span data-ttu-id="4db5b-127">기능을 끄고 켜려면 다음 매개 변수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-127">To turn off and turn on the features, set the following parameters:</span></span>

 - <span data-ttu-id="4db5b-128">**의견 제공**: **userInitiatedMode** 매개 변수를 **enabled** 로 설정 하 여 정책을 할당 한 사용자가 피드백을 제공 하도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-128">**Give feedback**: Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="4db5b-129">매개 변수를 **disabled** 로 설정 하면 기능이 해제 되 고 정책에 할당 된 사용자에 게 피드백을 제공 하는 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-129">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>
 - <span data-ttu-id="4db5b-130">**설문 조사**: **receiveSurveysMode** 매개 변수를 **enabled** 로 설정 하면 정책에 할당 된 사용자가 설문 조사를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-130">**Surveys**: Set the **receiveSurveysMode** parameter to **enabled** to allow users who are assigned the policy to receive the survey.</span></span> <span data-ttu-id="4db5b-131">사용자가 설문 조사를 받아 옵트아웃 하도록 허용 하려면 매개 변수를 **enabledUserOverride**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-131">To have users receive the survey and allow them to opt out, set the parameter to **enabledUserOverride**.</span></span> <span data-ttu-id="4db5b-132">팀에서는 사용자가 **설정** > **개인 정보** 로 이동 하 여 설문 조사 참여 여부를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-132">In Teams, users can then go to **Settings** > **Privacy** and choose whether they want to participate in surveys.</span></span> <span data-ttu-id="4db5b-133">매개 변수를 **disabled** 로 설정 하면 기능이 해제 되 고 정책에 할당 된 사용자는 설문 조사가 수신 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-133">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy won't receive the survey.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="4db5b-134">사용자 지정 피드백 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="4db5b-134">Create a custom feedback policy</span></span>

<span data-ttu-id="4db5b-135">이 예제에서는 새 고용 피드백 정책 이라고 하는 피드백 정책을 만들고 피드백 및 설문 조사 **를 통해 피드백** 을 제공 하는 기능을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-135">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback through **Give feedback** and the survey.</span></span>

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy"></a><span data-ttu-id="4db5b-136">사용자 지정 피드백 정책 지정</span><span class="sxs-lookup"><span data-stu-id="4db5b-136">Assign a custom feedback policy</span></span>

### <a name="assign-a-custom-feedback-policy-to-a-user"></a><span data-ttu-id="4db5b-137">사용자에 게 사용자 지정 피드백 정책 할당</span><span class="sxs-lookup"><span data-stu-id="4db5b-137">Assign a custom feedback policy to a user</span></span>

<span data-ttu-id="4db5b-138">이 예제에서는 user1 이라는 사용자에 게 새 채용 사용자 의견 정책 이라는 사용자 지정 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-138">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```
### <a name="assign-a-custom-feedback-policy-to-users-in-a-group"></a><span data-ttu-id="4db5b-139">그룹의 사용자에 게 사용자 지정 피드백 정책 할당</span><span class="sxs-lookup"><span data-stu-id="4db5b-139">Assign a custom feedback policy to users in a group</span></span>

<span data-ttu-id="4db5b-140">이미 식별 한 여러 사용자에 게 사용자 지정 피드백 정책을 할당 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-140">You may want to assign a custom feedback policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="4db5b-141">예를 들어 보안 그룹의 모든 사용자에 게 정책을 할당 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-141">For example, you may want to assign a policy to all users in a security group.</span></span>

<span data-ttu-id="4db5b-142">이 예제에서는 Contoso 새 고용 그룹의 모든 사용자에 게 새 채용 사용자 의견 정책 이라는 사용자 지정 피드백 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-142">In this example, we assign a custom feedback policy called New Hire Feedback Policy to all users in the Contoso New Hires group.</span></span>  

<span data-ttu-id="4db5b-143">특정 그룹의 GroupObjectId를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-143">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso New Hires"
```
<span data-ttu-id="4db5b-144">지정 된 그룹의 구성원을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-144">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="4db5b-145">그룹의 모든 사용자를 특정 피드백 정책에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-145">Assign all users in the group to a particular feedback policy.</span></span> <span data-ttu-id="4db5b-146">이 예제에서는 새 채용에 대 한 의견 수집 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-146">In this example, it's New Hire Feedback Policy.</span></span>
```PowerShell
$members | ForEach-Object {Grant-CsTeamsFeedbackPolicy -PolicyName "New Hire Feedback Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="4db5b-147">그룹의 구성원 수에 따라이 명령을 실행 하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4db5b-147">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4db5b-148">관련 항목</span><span class="sxs-lookup"><span data-stu-id="4db5b-148">Related topics</span></span>

- [<span data-ttu-id="4db5b-149">팀 PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="4db5b-149">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
