---
title: 사용자 지정 앱 정책 및 설정 관리
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: akino
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
description: 사용자 지정 앱 정책 및 설정을 관리하여 Microsoft Teams에서 사용자 지정 앱을 업로드할 수 있는 조직 내 사용자 제어 방법을 배워야 합니다.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- seo-marvel-mar2020
ms.openlocfilehash: 4e9863508d7b10c76ed29bfcb0fec79ca7a33dc5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821008"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a><span data-ttu-id="18db1-103">Microsoft Teams에서 사용자 지정 앱 정책 및 설정 관리</span><span class="sxs-lookup"><span data-stu-id="18db1-103">Manage custom app policies and settings in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="18db1-104">App Studio를 사용하려면 [C#/.NET](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-dotnet-app-studio) 및 App Studio에서 Microsoft Teams 플랫폼 시작을 참조하세요. 마지막 단계는 아직 작동하지 않습니다. 따라서 zip을 다운로드하고 [Microsoft Teams에](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload)앱 패키지 업로드에서 이전 방법을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-104">To use App Studio see [Get started on the Microsoft Teams platform with C#/.NET and App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-dotnet-app-studio) The last step is not working yet, so you will need to download the zip and install it the old way at [Upload an app package to Microsoft Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload).</span></span>

<span data-ttu-id="18db1-105">관리자는 사용자 지정 앱 정책 및 설정을 사용하여 조직에서 Microsoft Teams에 사용자 지정 앱을 업로드할 수 있는 사용자들을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-105">As an admin, you can use custom app policies and settings to control who in your organization can upload custom apps to Microsoft Teams.</span></span> <span data-ttu-id="18db1-106">관리자는 사용자 지정 앱을 업로드할 수 있는 사용자를 결정하고, 관리자와 팀 소유자는 조직의 특정 팀이 사용자 지정 앱을 추가할 수 있도록 허용하는지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-106">Admins decide which users can upload custom apps, and admins and team owners can determine whether specific teams in your organization allow custom apps to be added to them.</span></span>  <span data-ttu-id="18db1-107">사용자 지정 앱 정책을 편집한 후 변경 내용을 적용하는 데 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-107">After you edit the custom app policy, it can take a few hours for changes to take effect.</span></span> <span data-ttu-id="18db1-108">이러한 정책을 관리하려면 전역 관리자 또는 Teams 서비스 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-108">You must be a global admin or Teams service admin to manage these policies.</span></span>

## <a name="overview-of-custom-apps"></a><span data-ttu-id="18db1-109">사용자 지정 앱 개요</span><span class="sxs-lookup"><span data-stu-id="18db1-109">Overview of custom apps</span></span>

<span data-ttu-id="18db1-110">사용자는 팀 또는 개인 컨텍스트에서 앱 패키지(.zip 파일)를 직접 업로드하여 Teams에 사용자 지정 앱을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-110">Users can add a custom app to Teams by uploading an app package (in a .zip file) directly to a team or in the personal context.</span></span> <span data-ttu-id="18db1-111">Teams 앱 스토어를 통해 앱을 추가하는 방법과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-111">This is different from how apps are added through the Teams app store.</span></span> <span data-ttu-id="18db1-112">테스트용 로드라고도 하는 앱 패키지를 업로드하여 사용자 지정 앱을 추가하면 앱을 개발 중일 때 광범위하게 배포할 준비가 되기 전에 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-112">Adding a custom app by uploading an app package, also known as sideloading, lets you test an app as it's being developed, before it's ready to be widely distributed.</span></span> <span data-ttu-id="18db1-113">또한 내부용 앱을 빌드하고 Teams 앱 스토어의 Teams 앱 카탈로그에 제출하지 않고도 팀과 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-113">It also lets you build an app for internal use only and share it with your team without submitting it to the Teams app catalog in the Teams app store.</span></span>

![앱 스토어에서 사용자 지정 앱 업로드 옵션을 보여주는 스크린샷](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a><span data-ttu-id="18db1-115">사용자 지정 앱 정책 및 설정</span><span class="sxs-lookup"><span data-stu-id="18db1-115">Custom app policy and settings</span></span>

<span data-ttu-id="18db1-116">세 가지 구성 요소는 사용자가 사용자 지정 앱을 팀에 업로드할 수 있는지 여부를 결정하여 팀에 사용자 지정 앱을 추가할 수 있는 사용자 및 팀 사용자 지정 앱을 세부적으로 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-116">Three components determine whether a user can upload a custom app to a team, giving you granular control over who can add custom apps to a team and which teams custom apps can be added to:</span></span>

- [<span data-ttu-id="18db1-117">사용자 지정 앱 정책</span><span class="sxs-lookup"><span data-stu-id="18db1-117">User custom app policy</span></span>](#user-custom-app-policy)
- [<span data-ttu-id="18db1-118">팀 사용자 지정 앱 설정</span><span class="sxs-lookup"><span data-stu-id="18db1-118">Team custom app setting</span></span>](#team-custom-app-setting)
- [<span data-ttu-id="18db1-119">전체 사용자 지정 앱 설정</span><span class="sxs-lookup"><span data-stu-id="18db1-119">Org-wide custom app setting</span></span>](#org-wide-custom-app-setting)

<span data-ttu-id="18db1-120">이러한 설정은 타사 앱을 차단하는 능력에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-120">These settings don't affect the ability to block third-party apps.</span></span>  

### <a name="user-custom-app-policy"></a><span data-ttu-id="18db1-121">사용자 지정 앱 정책</span><span class="sxs-lookup"><span data-stu-id="18db1-121">User custom app policy</span></span>

<span data-ttu-id="18db1-122">앱 설정 [정책의 일부로](teams-app-setup-policies.md)관리자는 정책 **설정인** 사용자 지정 앱 업로드를 사용하여 사용자가 Teams에 사용자 지정 앱을 업로드할 수 있는지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-122">As part of [app setup policies](teams-app-setup-policies.md), admins can use a policy setting, **Upload custom apps**, to control whether a user can upload custom apps to Teams.</span></span>
 
<span data-ttu-id="18db1-123">이 설정이 꺼져 있는 경우:</span><span class="sxs-lookup"><span data-stu-id="18db1-123">If this setting is turned off:</span></span>

- <span data-ttu-id="18db1-124">사용자는 조직 또는 개인 컨텍스트에서 사용자 지정 앱을 업로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-124">The user can't upload a custom app to any team in your organization or in the personal context.</span></span>
- <span data-ttu-id="18db1-125">사용자는 전체 사용자 지정 앱 설정에 따라 사용자 지정 앱과 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-125">The user can interact with custom apps, depending on the org-wide custom app setting.</span></span>

<span data-ttu-id="18db1-126">이 설정이 켜져 있는 경우:</span><span class="sxs-lookup"><span data-stu-id="18db1-126">If this setting is turned on:</span></span>

- <span data-ttu-id="18db1-127">사용자는 전체 사용자 지정 앱 설정에 따라 사용자 지정 앱을 허용하는 팀 및 소유자인 팀에 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-127">The user can upload custom apps to teams that allow it and to teams for which they are owners, depending on the org-wide custom app setting.</span></span>
- <span data-ttu-id="18db1-128">사용자는 개인 컨텍스트에 사용자 지정 앱을 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-128">The user can upload custom apps to the personal context.</span></span> 
- <span data-ttu-id="18db1-129">사용자는 전체 사용자 지정 앱 설정에 따라 사용자 지정 앱과 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-129">The user can interact with custom apps, depending on the org-wide custom app setting.</span></span>

<span data-ttu-id="18db1-130">글로벌 앱 설정 정책에서 설정을 편집하여 원하는 앱을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-130">You can edit the settings in the global app setup policy to include the apps that you want.</span></span> <span data-ttu-id="18db1-131">조직의 여러 사용자 그룹에 대해 Teams를 사용자 지정하려면 하나 이상의 사용자 지정 앱 설정 정책을 만들고 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-131">If you want to customize Teams for different groups of users in your organization, create and assign one or more custom app setup policies.</span></span>

#### <a name="set-a-user-custom-app-policy"></a><span data-ttu-id="18db1-132">사용자 지정 앱 정책 설정</span><span class="sxs-lookup"><span data-stu-id="18db1-132">Set a user custom app policy</span></span>

1. <span data-ttu-id="18db1-133">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 **Teams** 앱 설정  >  **정책으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="18db1-133">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="18db1-134">추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="18db1-134">Click **Add**.</span></span>
3. <span data-ttu-id="18db1-135">사용자 지정 앱 업로드를 **설정하거나 해제합니다.**</span><span class="sxs-lookup"><span data-stu-id="18db1-135">Turn on or turn off **Upload custom apps**.</span></span>
4. <span data-ttu-id="18db1-136">정책에 사용할 다른 설정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-136">Choose any other settings that you want to for the policy.</span></span>
5. <span data-ttu-id="18db1-137">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-137">Click **Save**.</span></span>

### <a name="team-custom-app-setting"></a><span data-ttu-id="18db1-138">팀 사용자 지정 앱 설정</span><span class="sxs-lookup"><span data-stu-id="18db1-138">Team custom app setting</span></span>

<span data-ttu-id="18db1-139">관리자와 팀 소유자는 팀이 사용자 지정 앱을 추가할 수 있는지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-139">Admins and team owners can control whether a team allows for custom apps to be added to it.</span></span> <span data-ttu-id="18db1-140">이 설정에서는 **구성원이** 사용자 지정 앱을 업로드할 수 있도록 허용하고 사용자 지정 앱 정책과 함께 특정 팀에 사용자 지정 앱을 추가할 수 있는 사용자를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-140">This setting, **Allow members to upload custom apps**, together with a user's custom app policy determines who can add custom apps to a particular team.</span></span>
 
<span data-ttu-id="18db1-141">이 설정이 꺼져 있는 경우:</span><span class="sxs-lookup"><span data-stu-id="18db1-141">If this setting is turned off:</span></span>

- <span data-ttu-id="18db1-142">사용자 지정 앱 정책에서 허용하는 경우 팀 소유자는 사용자 지정 앱을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-142">Team owners can add custom apps, if their custom app policy allows it.</span></span>
- <span data-ttu-id="18db1-143">팀 소유자가 아닌 팀 구성원은 사용자 지정 앱을 팀에 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-143">Team members who aren't team owners can't add custom apps to the team.</span></span>

<span data-ttu-id="18db1-144">이 설정이 켜져 있는 경우:</span><span class="sxs-lookup"><span data-stu-id="18db1-144">If this setting is turned on:</span></span>

- <span data-ttu-id="18db1-145">사용자 지정 앱 정책에서 허용하는 경우 팀 소유자는 사용자 지정 앱을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-145">Team owners can add custom apps, if their custom app policy allows for it.</span></span>
- <span data-ttu-id="18db1-146">팀 소유자가 아닌 팀 구성원은 사용자 지정 앱 정책에서 허용하는 경우 사용자 지정 앱을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-146">Team members who aren't team owners can add custom apps, if their custom app policy allows for it.</span></span>

#### <a name="configure-the-team-custom-app-setting"></a><span data-ttu-id="18db1-147">팀 사용자 지정 앱 설정 구성</span><span class="sxs-lookup"><span data-stu-id="18db1-147">Configure the team custom app setting</span></span>

1. <span data-ttu-id="18db1-148">Teams에서 팀으로 이동하고 추가 **옵션을** 클릭하여 ̇ ̇ ̇  >  **관리합니다.**</span><span class="sxs-lookup"><span data-stu-id="18db1-148">In Teams, go to the team, click **More options ˙˙˙** > **Manage team**.</span></span>
2. <span data-ttu-id="18db1-149">설정을 **클릭한** 다음 멤버 권한을 **확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="18db1-149">Click **Settings**, and then expand **Member permissions**.</span></span>
3. <span data-ttu-id="18db1-150">구성원이 사용자 지정 앱 **업로드 허용 확인란을 선택하거나 선택 취소합니다.**</span><span class="sxs-lookup"><span data-stu-id="18db1-150">Select or clear the **Allow members to upload custom apps** check box.</span></span>

    ![팀 사용자 지정 앱 설정을 보여주는 스크린샷](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a><span data-ttu-id="18db1-152">전체 사용자 지정 앱 설정</span><span class="sxs-lookup"><span data-stu-id="18db1-152">Org-wide custom app setting</span></span>

<span data-ttu-id="18db1-153">앱 관리 **페이지의** 사용자 지정 앱 조직 전체 [](manage-apps.md) 사용자 지정 앱 설정과의 상호 작용 허용은 조직의 모든 사용자에 적용하며 사용자 지정 앱을 업로드하거나 상호 작용할 수 있는지 여부를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-153">The **Allow interaction with custom apps** org-wide custom app setting on the [Manage apps](manage-apps.md) page applies to everyone in your organization and governs whether they can upload or interact with custom apps.</span></span> <span data-ttu-id="18db1-154">이 설정은 사용자 및 팀 사용자 지정 앱 정책 설정에 대한 마스터 켜기/끄기 스위치 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-154">This setting acts as a master on/off switch for the user and team custom app policy settings.</span></span> <span data-ttu-id="18db1-155">보안 이벤트 중에 마스터 켜기/끄기 스위치 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-155">It's intended to serve as a master on/off switch during security events.</span></span> <span data-ttu-id="18db1-156">따라서 사용자 및 팀 사용자 지정 앱 정책 설정을 사용하도록 설정한 경우에도 전체 사용자 지정 앱 설정을 사용하도록 설정하지 않으면 사용자 및 팀 사용자 지정 앱 정책 설정이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-156">As such, user and team custom app policy settings will not take effect unless the org-wide custom app setting is enabled even if user and team custom app policy settings are enabled.</span></span>

#### <a name="configure-the-org-wide-custom-app-setting"></a><span data-ttu-id="18db1-157">전체 사용자 지정 앱 설정 구성</span><span class="sxs-lookup"><span data-stu-id="18db1-157">Configure the org-wide custom app setting</span></span>

1. <span data-ttu-id="18db1-158">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 Teams 앱 **관리**  >  **앱으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="18db1-158">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="18db1-159">전체 **앱 설정을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="18db1-159">Click **Org-wide app settings**.</span></span>
3. <span data-ttu-id="18db1-160">사용자 **지정 앱에서** 사용자 지정 앱과의 상호 작용 허용을 설정하거나 **해제합니다.**</span><span class="sxs-lookup"><span data-stu-id="18db1-160">Under **Custom apps**, turn on or turn off **Allow interaction with custom apps**.</span></span>

    ![전체 사용자 지정 앱 설정을 보여주는 스크린샷](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a><span data-ttu-id="18db1-162">사용자 지정 앱 정책 및 설정이 함께 작동 하는 방법</span><span class="sxs-lookup"><span data-stu-id="18db1-162">How custom app policies and settings work together</span></span>

<span data-ttu-id="18db1-163">이 표에는 사용자 지정 앱 정책 및 설정, 함께 작업하는 방법 및 조직의 사용자 지정 앱을 Teams에 업로드할 수 있는 사용자 제어에 대한 결합된 효과가 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-163">This table summarizes the custom app policy and settings, how they work together, and their combined effect on controlling who in your organization can upload custom apps to Teams.</span></span>

<span data-ttu-id="18db1-164">예를 들어 팀 소유자만 특정 팀에 사용자 지정 앱을 업로드하도록 허용하려는 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-164">Say, for example, you want to allow only team owners to upload custom apps to specific teams.</span></span> <span data-ttu-id="18db1-165">다음을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-165">You would set the following:</span></span>
- <span data-ttu-id="18db1-166">Microsoft Teams 관리 **센터에서** 사용자 지정 앱 설정과의 상호 작용 허용을 턴합니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-166">Turn on the **Allow interaction with custom apps** setting in the Microsoft Teams admin center.</span></span>
- <span data-ttu-id="18db1-167">구성원이  액세스를 제한하려는 모든 팀에 대해 사용자 지정 앱을 업로드할 수 있도록 허용을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-167">Turn off the **Allow members to upload custom apps** for every team to which you want to restrict access.</span></span>
- <span data-ttu-id="18db1-168">사용자 지정 앱 업로드 설정이 켜져 있는  Microsoft Teams 관리 센터에서 사용자 지정 앱 설정 정책을 만들고 할당하고 팀 소유자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-168">Create and assign a custom app setup policy in the Microsoft Teams admin center with the **Upload custom apps** setting turned on, and assign it to the team owners.</span></span>

|<span data-ttu-id="18db1-169">전체 사용자 지정 앱 설정</span><span class="sxs-lookup"><span data-stu-id="18db1-169">Org-wide custom app setting</span></span> |<span data-ttu-id="18db1-170">팀 사용자 지정 앱 설정</span><span class="sxs-lookup"><span data-stu-id="18db1-170">Team custom app setting</span></span> |<span data-ttu-id="18db1-171">사용자 지정 앱 정책</span><span class="sxs-lookup"><span data-stu-id="18db1-171">User custom app policy</span></span> |<span data-ttu-id="18db1-172">효과</span><span class="sxs-lookup"><span data-stu-id="18db1-172">Effect</span></span>  |
|---------|---------|---------|---------|
| <span data-ttu-id="18db1-173">끄기</span><span class="sxs-lookup"><span data-stu-id="18db1-173">Off</span></span>    | <span data-ttu-id="18db1-174">끄기</span><span class="sxs-lookup"><span data-stu-id="18db1-174">Off</span></span>    | <span data-ttu-id="18db1-175">끄기</span><span class="sxs-lookup"><span data-stu-id="18db1-175">Off</span></span>     |<span data-ttu-id="18db1-176">모든 사용자 지정 앱과의 상호 작용은 조직에 대해 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-176">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="18db1-177">Teams 서비스 관리자 또는 전역 관리자를 제외한 모든 사용자가 사용자 지정 앱을 업로드할 수 없습니다. PowerShell을 사용하여 사용자 지정 앱을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-177">Custom apps can't be uploaded by anyone except a Teams Service Admin or a Global admin. You can use PowerShell to remove the custom app.</span></span>   |
| <span data-ttu-id="18db1-178">끄기</span><span class="sxs-lookup"><span data-stu-id="18db1-178">Off</span></span>     | <span data-ttu-id="18db1-179">끄기</span><span class="sxs-lookup"><span data-stu-id="18db1-179">Off</span></span>     | <span data-ttu-id="18db1-180">On</span><span class="sxs-lookup"><span data-stu-id="18db1-180">On</span></span>        |<span data-ttu-id="18db1-181">모든 사용자 지정 앱과의 상호 작용은 조직에 대해 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-181">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="18db1-182">Teams 서비스 관리자 또는 전역 관리자를 제외한 모든 사용자가 사용자 지정 앱을 업로드할 수 없습니다. PowerShell을 사용하여 사용자 지정 앱을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-182">Custom apps can't be uploaded by anyone except a Teams Service Admin or a Global admin. You can use PowerShell to remove the custom app.</span></span>         |
| <span data-ttu-id="18db1-183">끄기</span><span class="sxs-lookup"><span data-stu-id="18db1-183">Off</span></span>    | <span data-ttu-id="18db1-184">On</span><span class="sxs-lookup"><span data-stu-id="18db1-184">On</span></span>        | <span data-ttu-id="18db1-185">끄기</span><span class="sxs-lookup"><span data-stu-id="18db1-185">Off</span></span>        |<span data-ttu-id="18db1-186">모든 사용자 지정 앱과의 상호 작용은 조직에 대해 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-186">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="18db1-187">Teams 서비스 관리자 또는 전역 관리자를 제외한 모든 사용자가 사용자 지정 앱을 업로드할 수 없습니다. 사용자 지정 앱을 Windows PowerShell 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-187">Custom apps can't be uploaded by anyone except a Teams Service Admin or a Global admin. You can use Windows PowerShell to delete custom apps.</span></span>         |
| <span data-ttu-id="18db1-188">끄기</span><span class="sxs-lookup"><span data-stu-id="18db1-188">Off</span></span>    | <span data-ttu-id="18db1-189">On</span><span class="sxs-lookup"><span data-stu-id="18db1-189">On</span></span>      | <span data-ttu-id="18db1-190">On</span><span class="sxs-lookup"><span data-stu-id="18db1-190">On</span></span>       |<span data-ttu-id="18db1-191">모든 사용자 지정 앱과의 상호 작용은 조직에 대해 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-191">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="18db1-192">Teams 서비스 관리자 또는 전역 관리자를 제외한 모든 사용자가 사용자 지정 앱을 업로드할 수 없습니다. PowerShell을 사용하여 사용자 지정 앱을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-192">Custom apps can't be uploaded by anyone except a Teams Service Admin or a Global admin. You can use PowerShell to remove the custom app.</span></span>         |
| <span data-ttu-id="18db1-193">On</span><span class="sxs-lookup"><span data-stu-id="18db1-193">On</span></span>    | <span data-ttu-id="18db1-194">끄기</span><span class="sxs-lookup"><span data-stu-id="18db1-194">Off</span></span>       | <span data-ttu-id="18db1-195">끄기</span><span class="sxs-lookup"><span data-stu-id="18db1-195">Off</span></span>         |  <span data-ttu-id="18db1-196">사용자는 사용자 지정 앱을 업로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-196">The user can't upload custom apps.</span></span>      |
| <span data-ttu-id="18db1-197">On</span><span class="sxs-lookup"><span data-stu-id="18db1-197">On</span></span>     | <span data-ttu-id="18db1-198">끄기</span><span class="sxs-lookup"><span data-stu-id="18db1-198">Off</span></span>       | <span data-ttu-id="18db1-199">On</span><span class="sxs-lookup"><span data-stu-id="18db1-199">On</span></span>         | <span data-ttu-id="18db1-200">사용자가 팀 소유자인 경우 사용자 지정 앱을 팀에 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-200">If the user is a team owner, they can upload custom apps to the team.</span></span> <span data-ttu-id="18db1-201">사용자가 팀 소유자가 아닌 경우 사용자 지정 앱을 팀에 업로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-201">If the user isn't a team owner, they can't upload custom apps to the team.</span></span> <span data-ttu-id="18db1-202">사용자는 개인 컨텍스트에서 사용자 지정 앱을 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-202">The user can upload custom apps in the personal context.</span></span>     |
| <span data-ttu-id="18db1-203">On</span><span class="sxs-lookup"><span data-stu-id="18db1-203">On</span></span>     | <span data-ttu-id="18db1-204">On</span><span class="sxs-lookup"><span data-stu-id="18db1-204">On</span></span>     | <span data-ttu-id="18db1-205">끄기</span><span class="sxs-lookup"><span data-stu-id="18db1-205">Off</span></span>         | <span data-ttu-id="18db1-206">사용자는 사용자 지정 앱을 업로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-206">The user can't upload custom apps.</span></span>       |
| <span data-ttu-id="18db1-207">On</span><span class="sxs-lookup"><span data-stu-id="18db1-207">On</span></span>    | <span data-ttu-id="18db1-208">On</span><span class="sxs-lookup"><span data-stu-id="18db1-208">On</span></span>        | <span data-ttu-id="18db1-209">On</span><span class="sxs-lookup"><span data-stu-id="18db1-209">On</span></span>        | <span data-ttu-id="18db1-210">사용자는 사용자가 팀 소유자인지 여부에 관계없이 사용자 지정 앱을 팀에 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-210">The user can upload custom apps to the team, regardless of whether the user is a team owner.</span></span> <span data-ttu-id="18db1-211">사용자는 개인 컨텍스트에서 사용자 지정 앱을 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18db1-211">The user can upload custom apps in the personal context.</span></span>       |

## <a name="related-topics"></a><span data-ttu-id="18db1-212">관련 항목</span><span class="sxs-lookup"><span data-stu-id="18db1-212">Related topics</span></span>
 
[<span data-ttu-id="18db1-213">Team에서 앱의 관리 설정</span><span class="sxs-lookup"><span data-stu-id="18db1-213">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="18db1-214">Teams에서 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="18db1-214">Assign policies to your users in Teams</span></span>](assign-policies.md)