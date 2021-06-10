---
title: 사용자 의견 정책 관리 Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: heprecel
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 피드백 정책을 사용하여 조직의 사용자가 Microsoft에 Teams 피드백을 제출할 수 있는지 여부를 Teams 방법을 알아보습니다.
ms.openlocfilehash: 66f14467e66456f244664a8273e0ff962297c05f
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656724"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="bda9c-103">사용자 의견 정책 관리 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bda9c-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="bda9c-104">조직의 사용자는 Microsoft에 사용자에 대한 피드백을 Teams 데스크톱 및 웹 클라이언트 내에서 직접 Microsoft에 Teams 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bda9c-104">Users in your organization can send feedback about Teams to Microsoft let us know how we're doing, directly from within the Teams desktop and web clients.</span></span> <span data-ttu-id="bda9c-105">이 피드백을 사용하여 더 나은 Teams 환경을 지속적으로 개선하고 Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bda9c-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

> [!NOTE]
> <span data-ttu-id="bda9c-106">피드백 정책은 고가 또는 DOD GCC GCC 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bda9c-106">Feedback policies aren't available in GCC, GCC High, or DOD deployments.</span></span>

<span data-ttu-id="bda9c-107">**피드백 제공 기능**</span><span class="sxs-lookup"><span data-stu-id="bda9c-107">**The Give feedback feature**</span></span>

<span data-ttu-id="bda9c-108">사용자는 사용자에 대한 의견과 제안을 Teams 도움말로   >   Teams.</span><span class="sxs-lookup"><span data-stu-id="bda9c-108">Users can send comments and suggestions about Teams to us by going to **Help** > **Give feedback** in Teams.</span></span> <span data-ttu-id="bda9c-109">피드백 **제공을** 통해 전송된 데이터는 "고객 데이터" 또는 "개인 데이터"로 간주되는 Microsoft 365 Office 365 계약에 따라 "지원 데이터"로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="bda9c-109">Data sent through **Give feedback** is considered as "Support Data" under your Microsoft 365 or Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

![사용자 의견 제공 옵션의 스크린샷Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="bda9c-111">**설문 조사**</span><span class="sxs-lookup"><span data-stu-id="bda9c-111">**Surveys**</span></span>

<span data-ttu-id="bda9c-112">또한 사용자는 사용자 경험에 대한 평가를 Teams 등급에 대한 세부 정보를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bda9c-112">Users can also rate their experience with Teams and send us details about the rating they give.</span></span> <span data-ttu-id="bda9c-113">이 팝업 설문 조사는 사용자에 대해 수시로 표시됩니다Teams.</span><span class="sxs-lookup"><span data-stu-id="bda9c-113">This pop-up survey is displayed to users from time-to-time in Teams.</span></span> <span data-ttu-id="bda9c-114">사용자가 알림에서  피드백 제공을 선택하면 설문 조사가 완료될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bda9c-114">When a user selects **Provide feedback** in the notification, the survey is displayed for them to complete.</span></span>

![설문 조사 알림 및 양식 Teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="bda9c-116">사용자가 Microsoft에 대한 피드백을 보낼 수 Teams 설정</span><span class="sxs-lookup"><span data-stu-id="bda9c-116">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="bda9c-117">관리자는 조직의 사용자가 피드백 제공을 통해 Microsoft에 Teams 피드백에 대한  피드백을 보낼 수 있는지 여부와 설문 조사를 받을지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bda9c-117">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft through **Give feedback** and whether they receive the survey.</span></span> <span data-ttu-id="bda9c-118">기본적으로 조직의 모든 사용자에게 전역(조직 전체 기본값) 정책이 자동으로 할당되고  피드백 제공 기능 및 설문 조사가 정책에서 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="bda9c-118">By default, all users in your organization are automatically assigned the global (Org-wide default) policy, and the **Give feedback** feature and survey are enabled in the policy.</span></span> <span data-ttu-id="bda9c-119">예외는 Teams 지원되지 않습니다. 여기서는 교사가 기능을 사용하도록 설정하고 학생들을 위해 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="bda9c-119">The exception is Teams for Education, where the features are enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="bda9c-120">전역 정책을 편집하거나 사용자 지정 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bda9c-120">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="bda9c-121">전역 정책을 편집하거나 사용자 지정 정책을 할당한 후 변경 내용이 적용될 수 있는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bda9c-121">After you edit the global policy or assign a custom policy, it can take a few hours for changes to take effect.</span></span>

<span data-ttu-id="bda9c-122">예를 들어 조직의 모든 사용자가 피드백 제공을 통해 피드백을 보내고 교육에서 신규 고용을 제외한 설문 조사를 받을 수 있도록 허용하려는 경우를 예로 들 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="bda9c-122">Say, for example, you want to allow all users in your organization to send feedback through **Give feedback** and receive surveys except for new hires in training.</span></span> <span data-ttu-id="bda9c-123">이 시나리오에서는 두 기능을 모두 해제하고 새 고용에 할당하는 사용자 지정 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bda9c-123">In this scenario, you create a custom policy to turn off both features and assign it to new hires.</span></span> <span data-ttu-id="bda9c-124">조직의 다른 모든 사용자는 기능이 켜져 있는 전역 정책을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="bda9c-124">All other users in your organization get the global policy with the features turned on.</span></span>  

<span data-ttu-id="bda9c-125">PowerShell을 사용하여 피드백 정책을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="bda9c-125">You manage feedback policies by using PowerShell.</span></span> <span data-ttu-id="bda9c-126">여기에서 찾을 수 있는 **New-CsTeamsFeedbackPolicy** cmdlet을 사용하여 사용자 지정 정책을 만들 수 있습니다. *[](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*</span><span class="sxs-lookup"><span data-stu-id="bda9c-126">Use the **New-CsTeamsFeedbackPolicy** cmdlet, *which can be [found here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, to create a custom policy.</span></span> <span data-ttu-id="bda9c-127">**Grant-CsTeamsFeedbackPolicy** cmdlet을 사용하여 보안 그룹 또는 메일 그룹과 같은 하나 이상의 사용자 또는 사용자 그룹에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="bda9c-127">Use the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span> <span data-ttu-id="bda9c-128">**Set-CsTeamsFeedbackPolicy를** 사용하여 특정 플래그를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bda9c-128">Use **Set-CsTeamsFeedbackPolicy** to set specific flags.</span></span>

<span data-ttu-id="bda9c-129">기능을 끄고 켜기 위해 다음 매개 변수를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bda9c-129">To turn off and turn on the features, set the following parameters:</span></span>

 - <span data-ttu-id="bda9c-130">**피드백 제공:** 정책을 할당한 사용자가 피드백을  제공하도록 허용하도록 **userInitiatedMode** 매개 변수를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bda9c-130">**Give feedback**: Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="bda9c-131">매개 변수를 사용하지 않도록 **설정하면** 기능이 해제되어 정책에 할당된 사용자에게 피드백을 줄 수 있는 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bda9c-131">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>
 - <span data-ttu-id="bda9c-132">**설문 조사**: 정책에 할당된 사용자가 설문  조사를 받을 수 있도록 **하도록 receiveSurveysMode** 매개 변수를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bda9c-132">**Surveys**: Set the **receiveSurveysMode** parameter to **enabled** to allow users who are assigned the policy to receive the survey.</span></span> <span data-ttu-id="bda9c-133">사용자가 설문 조사를 수신하고 옵트아웃할 수 있도록 설정하기 위해 매개 변수를 **enabledUserOverride로 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="bda9c-133">To have users receive the survey and allow them to opt out, set the parameter to **enabledUserOverride**.</span></span> <span data-ttu-id="bda9c-134">이 Teams 사용자는 개인 정보 보호 설정 이동하여 설문 조사에 참여할지  >   여부를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bda9c-134">In Teams, users can then go to **Settings** > **Privacy** and choose whether they want to participate in surveys.</span></span> <span data-ttu-id="bda9c-135">매개 변수를 사용하지 않도록 **설정하면** 기능이 해제되어 정책이 할당된 사용자는 설문 조사를 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bda9c-135">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy won't receive the survey.</span></span>
 - <span data-ttu-id="bda9c-136">**전자 메일**: **AllowEmailCollection** 플래그를 사용하여 전자 메일 필드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bda9c-136">**Email**: Use the **AllowEmailCollection** flag to add an email field.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="bda9c-137">사용자 지정 피드백 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="bda9c-137">Create a custom feedback policy</span></span>

<span data-ttu-id="bda9c-138">이 예제에서는 신규 고용 피드백 정책이라는 피드백 정책을 만들고 피드백 제공 및  설문 조사를 통해 피드백을 주는 기능을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="bda9c-138">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback through **Give feedback** and the survey.</span></span>

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a><span data-ttu-id="bda9c-139">사용자에게 사용자 지정 피드백 정책 할당</span><span class="sxs-lookup"><span data-stu-id="bda9c-139">Assign a custom feedback policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="bda9c-140">이 예제에서는 user1이라는 사용자에게 새 고용 피드백 정책이라는 사용자 지정 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="bda9c-140">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a><span data-ttu-id="bda9c-141">관련 항목</span><span class="sxs-lookup"><span data-stu-id="bda9c-141">Related topics</span></span>

- [<span data-ttu-id="bda9c-142">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="bda9c-142">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="bda9c-143">Teams에서 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="bda9c-143">Assign policies to your users in Teams</span></span>](assign-policies.md)
