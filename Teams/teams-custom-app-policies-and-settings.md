---
title: Microsoft 팀에서 사용자 지정 앱 정책 및 설정 관리
author: lanachin
ms.author: v-lanac
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
description: 사용자 지정 앱 정책 및 설정을 관리 하 여 조직에서 Microsoft 팀의 사용자 지정 앱을 업로드할 수 있는 사용자를 제어 하는 방법에 대해 알아봅니다.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
ms.openlocfilehash: 86bf441f6dfa74b243f1a6e64139a32b8b94d7fa
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161634"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a><span data-ttu-id="7799b-103">Microsoft 팀에서 사용자 지정 앱 정책 및 설정 관리</span><span class="sxs-lookup"><span data-stu-id="7799b-103">Manage custom app policies and settings in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="7799b-104">앱 Studio를 사용 하려면 [c #/.net 및 App studio에서 Microsoft 팀 플랫폼 시작](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-dotnet-app-studio) 을 참조 하세요. 마지막 단계는 아직 작동 하지 않기 때문에 [microsoft 팀에 앱 패키지를 업로드](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload)하려면 zip을 다운로드 하 여 기존 방법으로 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-104">To use App Studio see [Get started on the Microsoft Teams platform with C#/.NET and App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-dotnet-app-studio) The last step is not working yet, so you will need to download the zip and install it the old way at [Upload an app package to Microsoft Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload).</span></span>

<span data-ttu-id="7799b-105">관리자는 사용자 지정 앱 정책 및 설정을 사용 하 여 조직에서 Microsoft 팀에 사용자 지정 앱을 업로드할 수 있는 사용자를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-105">As an admin, you can use custom app policies and settings to control who in your organization can upload custom apps to Microsoft Teams.</span></span> <span data-ttu-id="7799b-106">관리자는 사용자 지정 앱을 업로드할 수 있는 사용자를 결정 하 고, 관리자와 팀 소유자는 조직의 특정 팀이 사용자 지정 앱을 추가할 수 있도록 허용할지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-106">Admins decide which users can upload custom apps, and admins and team owners can determine whether specific teams in your organization allow custom apps to be added to them.</span></span>  <span data-ttu-id="7799b-107">사용자 지정 앱 정책을 편집 하 고 나면 변경 내용이 적용 되는 데 최대 24 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-107">After you edit the custom app policy, it can take up to 24 hours for changes to take effect.</span></span>

## <a name="overview-of-custom-apps"></a><span data-ttu-id="7799b-108">사용자 지정 앱 개요</span><span class="sxs-lookup"><span data-stu-id="7799b-108">Overview of custom apps</span></span>

<span data-ttu-id="7799b-109">사용자는 앱 패키지 (.zip 파일)를 팀 또는 개인 컨텍스트에 직접 업로드 하 여 팀에 사용자 지정 앱을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-109">Users can add a custom app to Teams by uploading an app package (in a .zip file) directly to a team or in the personal context.</span></span> <span data-ttu-id="7799b-110">이것은 팀 앱 스토어를 통해 앱을 추가 하는 방법과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-110">This is different from how apps are added through the Teams app store.</span></span> <span data-ttu-id="7799b-111">앱 패키지를 업로드 하 여 사용자 지정 앱을 추가 하면 (테스트용 로드 라고도 함), 개발 하는 동안 앱을 테스트 하 여 광범위 하 게 배포할 준비가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-111">Adding a custom app by uploading an app package, also known as sideloading, lets you test an app as it's being developed, before it's ready to be widely distributed.</span></span> <span data-ttu-id="7799b-112">또한 앱을 내부용 으로만 빌드 하 고 팀 앱 저장소의 팀 앱 카탈로그에 제출 하지 않고 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-112">It also lets you build an app for internal use only and share it with your team without submitting it to the Teams app catalog in the Teams app store.</span></span>

![App store에서 사용자 지정 앱 업로드 옵션을 보여 주는 스크린샷](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a><span data-ttu-id="7799b-114">사용자 지정 앱 정책 및 설정</span><span class="sxs-lookup"><span data-stu-id="7799b-114">Custom app policy and settings</span></span>

<span data-ttu-id="7799b-115">세 가지 구성 요소는 사용자가 팀에 사용자 지정 앱을 업로드할 수 있는지 여부를 결정 하 고 사용자 지정 앱을 팀에 추가할 수 있는 사용자 지정 앱을 제공 하 고 다음에 추가할 수 있는 팀을 세부적으로 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-115">Three components determine whether a user can upload a custom app to a team, giving you granular control over who can add custom apps to a team and which teams custom apps can be added to:</span></span>

- [<span data-ttu-id="7799b-116">사용자 지정 앱 정책</span><span class="sxs-lookup"><span data-stu-id="7799b-116">User custom app policy</span></span>](#user-custom-app-policy)
- [<span data-ttu-id="7799b-117">팀 사용자 지정 앱 설정</span><span class="sxs-lookup"><span data-stu-id="7799b-117">Team custom app setting</span></span>](#team-custom-app-setting)
- [<span data-ttu-id="7799b-118">조직 전체 사용자 지정 앱 설정</span><span class="sxs-lookup"><span data-stu-id="7799b-118">Org-wide custom app setting</span></span>](#org-wide-custom-app-setting)

<span data-ttu-id="7799b-119">이러한 설정은 타사 앱을 차단 하는 기능에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-119">These settings don't affect the ability to block third-party apps.</span></span>  

### <a name="user-custom-app-policy"></a><span data-ttu-id="7799b-120">사용자 지정 앱 정책</span><span class="sxs-lookup"><span data-stu-id="7799b-120">User custom app policy</span></span>

<span data-ttu-id="7799b-121">[앱 설정 정책의](teams-app-setup-policies.md)일부로 관리자는 사용자가 사용자 지정 앱을 팀에 업로드할 수 있는지 여부를 제어 하기 위해 정책 설정을 사용 하 여 **사용자 지정 앱을 업로드**합니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-121">As part of [app setup policies](teams-app-setup-policies.md), admins can use a policy setting, **Upload custom apps**, to control whether a user can upload custom apps to Teams.</span></span>
 
<span data-ttu-id="7799b-122">이 설정이 꺼져 있는 경우:</span><span class="sxs-lookup"><span data-stu-id="7799b-122">If this setting is turned off:</span></span>

- <span data-ttu-id="7799b-123">사용자는 조직의 팀 또는 개인 컨텍스트에서 사용자 지정 앱을 업로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-123">The user can't upload a custom app to any team in your organization or in the personal context.</span></span>
- <span data-ttu-id="7799b-124">사용자는 조직 전체 사용자 지정 앱 설정에 따라 사용자 지정 앱과 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-124">The user can interact with custom apps, depending on the org-wide custom app setting.</span></span>

<span data-ttu-id="7799b-125">이 설정이 설정 된 경우:</span><span class="sxs-lookup"><span data-stu-id="7799b-125">If this setting is turned on:</span></span>

- <span data-ttu-id="7799b-126">사용자는 조직 전체 사용자 지정 앱 설정에 따라 팀 구성원에 게 사용자 지정 앱을 업로드 하 고 해당 소유자에 게 팀을 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-126">The user can upload custom apps to teams that allow it and to teams for which they are owners, depending on the org-wide custom app setting.</span></span>
- <span data-ttu-id="7799b-127">사용자는 개인 컨텍스트에 사용자 지정 앱을 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-127">The user can upload custom apps to the personal context.</span></span> 
- <span data-ttu-id="7799b-128">사용자는 조직 전체 사용자 지정 앱 설정에 따라 사용자 지정 앱과 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-128">The user can interact with custom apps, depending on the org-wide custom app setting.</span></span>

<span data-ttu-id="7799b-129">전역 앱 설정 정책의 설정을 편집 하 여 원하는 앱을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-129">You can edit the settings in the global app setup policy to include the apps that you want.</span></span> <span data-ttu-id="7799b-130">조직의 여러 사용자 그룹에 대해 팀을 사용자 지정 하려는 경우 하나 이상의 사용자 지정 앱 설정 정책 만들기 및 할당을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-130">If you want to customize Teams for different groups of users in your organization, create and assign one or more custom app setup policies.</span></span>

#### <a name="set-a-user-custom-app-policy"></a><span data-ttu-id="7799b-131">사용자 지정 앱 정책 설정</span><span class="sxs-lookup"><span data-stu-id="7799b-131">Set a user custom app policy</span></span>

1. <span data-ttu-id="7799b-132">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱** > **설정 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-132">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="7799b-133">**추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-133">Click **Add**.</span></span>
3. <span data-ttu-id="7799b-134">**사용자 지정 앱 업로드**를 켜거나 끕니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-134">Turn on or turn off **Upload custom apps**.</span></span>
4. <span data-ttu-id="7799b-135">정책에 대해 원하는 다른 설정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-135">Choose any other settings that you want to for the policy.</span></span>
5. <span data-ttu-id="7799b-136">**저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-136">Click **Save**.</span></span>

### <a name="team-custom-app-setting"></a><span data-ttu-id="7799b-137">팀 사용자 지정 앱 설정</span><span class="sxs-lookup"><span data-stu-id="7799b-137">Team custom app setting</span></span>

<span data-ttu-id="7799b-138">관리자와 팀 소유자는 팀이 사용자 지정 앱을 추가할 수 있도록 허용할 것인지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-138">Admins and team owners can control whether a team allows for custom apps to be added to it.</span></span> <span data-ttu-id="7799b-139">이 설정에서는 구성원이 사용자 지정 앱을 **업로드할 수 있도록 허용**합니다. 사용자의 사용자 지정 앱 정책으로 특정 팀에 사용자 지정 앱을 추가할 수 있는 사용자를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-139">This setting, **Allow members to upload custom apps**, together with a user's custom app policy determines who can add custom apps to a particular team.</span></span>
 
<span data-ttu-id="7799b-140">이 설정이 꺼져 있는 경우:</span><span class="sxs-lookup"><span data-stu-id="7799b-140">If this setting is turned off:</span></span>

- <span data-ttu-id="7799b-141">사용자 지정 앱 정책에서 허용 하는 경우 팀 소유자가 사용자 지정 앱을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-141">Team owners can add custom apps, if their custom app policy allows it.</span></span>
- <span data-ttu-id="7799b-142">팀 소유자가 아닌 팀 구성원은 팀에 사용자 지정 앱을 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-142">Team members who aren't team owners can't add custom apps to the team.</span></span>

<span data-ttu-id="7799b-143">이 설정이 설정 된 경우:</span><span class="sxs-lookup"><span data-stu-id="7799b-143">If this setting is turned on:</span></span>

- <span data-ttu-id="7799b-144">사용자 지정 앱 정책에서 허용 하는 경우 팀 소유자가 사용자 지정 앱을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-144">Team owners can add custom apps, if their custom app policy allows for it.</span></span>
- <span data-ttu-id="7799b-145">팀 소유자가 아닌 팀 구성원은 사용자 지정 앱 정책에서 허용 하는 경우 사용자 지정 앱을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-145">Team members who aren't team owners can add custom apps, if their custom app policy allows for it.</span></span>

#### <a name="configure-the-team-custom-app-setting"></a><span data-ttu-id="7799b-146">팀 사용자 지정 앱 설정 구성</span><span class="sxs-lookup"><span data-stu-id="7799b-146">Configure the team custom app setting</span></span>

1. <span data-ttu-id="7799b-147">팀에서 팀으로 이동 하 고 **추가 옵션 ̇ ̇ ̇** > **팀 관리**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-147">In Teams, go to the team, click **More options ˙˙˙** > **Manage team**.</span></span>
2. <span data-ttu-id="7799b-148">**설정을**클릭 한 다음 **구성원 권한을**확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-148">Click **Settings**, and then expand **Member permissions**.</span></span>
3. <span data-ttu-id="7799b-149">**구성원에 게 사용자 지정 앱 업로드 허용** 확인란을 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-149">Select or clear the **Allow members to upload custom apps** check box.</span></span>

    ![팀 사용자 지정 앱 설정을 보여 주는 스크린샷](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a><span data-ttu-id="7799b-151">조직 전체 사용자 지정 앱 설정</span><span class="sxs-lookup"><span data-stu-id="7799b-151">Org-wide custom app setting</span></span>

<span data-ttu-id="7799b-152">[앱 관리](manage-apps.md) 페이지의 조직 내 모든 사용자 지정 앱에서 조직 전체의 **상호 작용 허용** 을 설정 하 고 사용자 지정 앱을 업로드 하거나 상호 작용할 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-152">The **Allow interaction with custom apps** org-wide custom app setting on the [Manage apps](manage-apps.md) page applies to everyone in your organization and governs whether they can upload or interact with custom apps.</span></span> <span data-ttu-id="7799b-153">이 설정은 사용자 및 팀 사용자 지정 앱 정책 및 설정 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-153">This setting overrides the user and team custom app policy and setting.</span></span> <span data-ttu-id="7799b-154">이는 보안 이벤트 중 마스터 on/off 스위치 역할을 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-154">It's intended to serve as a master on/off switch during security events.</span></span>

#### <a name="configure-the-org-wide-custom-app-setting"></a><span data-ttu-id="7799b-155">조직 전체에 걸친 사용자 지정 앱 설정 구성</span><span class="sxs-lookup"><span data-stu-id="7799b-155">Configure the org-wide custom app setting</span></span>

1. <span data-ttu-id="7799b-156">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱** > 으로**앱 관리**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-156">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="7799b-157">**조직 전체 앱 설정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-157">Click **Org-wide app settings**.</span></span>
3. <span data-ttu-id="7799b-158">**사용자 지정 앱**에서 **사용자 지정 앱과 상호 작용 허용**또는 해제를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-158">Under **Custom apps**, turn on or turn off **Allow interaction with custom apps**.</span></span>

    ![조직 전체에 걸친 사용자 지정 앱 설정을 보여 주는 스크린샷](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a><span data-ttu-id="7799b-160">사용자 지정 앱 정책 및 설정이 함께 작동 하는 방식</span><span class="sxs-lookup"><span data-stu-id="7799b-160">How custom app policies and settings work together</span></span>

<span data-ttu-id="7799b-161">이 표에는 사용자 지정 앱 정책 및 설정, 이들이 함께 작동 하는 방식, 조직에서 사용자 지정 앱을 팀에 업로드할 수 있는 사람을 제어 하는 데 적용 되는 효과의 조합이 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-161">This table summarizes the custom app policy and settings, how they work together, and their combined effect on controlling who in your organization can upload custom apps to Teams.</span></span>

<span data-ttu-id="7799b-162">예를 들어 팀 소유자만 특정 팀에 사용자 지정 앱을 업로드할 수 있도록 하려는 경우를 가정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="7799b-162">Say, for example, you want to allow only team owners to upload custom apps to specific teams.</span></span> <span data-ttu-id="7799b-163">다음을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-163">You would set the following:</span></span>
- <span data-ttu-id="7799b-164">Microsoft 팀 관리 센터에서 **사용자 지정 앱과 상호 작용 허용** 을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-164">Turn on the **Allow interaction with custom apps** setting in the Microsoft Teams admin center.</span></span>
- <span data-ttu-id="7799b-165">구성원에 게 액세스를 제한 하려는 모든 팀에 대해 **사용자 지정 앱을 업로드 하도록 허용을** 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-165">Turn off the **Allow members to upload custom apps** for every team to which you want to restrict access.</span></span>
- <span data-ttu-id="7799b-166">**사용자 지정 앱 업로드** 설정이 설정 된 Microsoft 팀 관리 센터에서 사용자 지정 앱 설치 정책을 만들고 할당 한 다음 팀 소유자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-166">Create and assign a custom app setup policy in the Microsoft Teams admin center with the **Upload custom apps** setting turned on, and assign it to the team owners.</span></span>

|<span data-ttu-id="7799b-167">조직 전체 사용자 지정 앱 설정</span><span class="sxs-lookup"><span data-stu-id="7799b-167">Org-wide custom app setting</span></span> |<span data-ttu-id="7799b-168">팀 사용자 지정 앱 설정</span><span class="sxs-lookup"><span data-stu-id="7799b-168">Team custom app setting</span></span> |<span data-ttu-id="7799b-169">사용자 지정 앱 정책</span><span class="sxs-lookup"><span data-stu-id="7799b-169">User custom app policy</span></span> |<span data-ttu-id="7799b-170">조절점</span><span class="sxs-lookup"><span data-stu-id="7799b-170">Effect</span></span>  |
|---------|---------|---------|---------|
| <span data-ttu-id="7799b-171">끄십시오</span><span class="sxs-lookup"><span data-stu-id="7799b-171">Off</span></span>    | <span data-ttu-id="7799b-172">끄십시오</span><span class="sxs-lookup"><span data-stu-id="7799b-172">Off</span></span>    | <span data-ttu-id="7799b-173">끄십시오</span><span class="sxs-lookup"><span data-stu-id="7799b-173">Off</span></span>     |<span data-ttu-id="7799b-174">조직에 대해 모든 사용자 지정 앱과의 조작이 차단 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-174">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="7799b-175">사용자 지정 앱은 아무도 업로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-175">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="7799b-176">PowerShell을 사용 하 여 사용자 지정 앱을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-176">You can use PowerShell to remove the custom app.</span></span>   |
| <span data-ttu-id="7799b-177">끄십시오</span><span class="sxs-lookup"><span data-stu-id="7799b-177">Off</span></span>     | <span data-ttu-id="7799b-178">끄십시오</span><span class="sxs-lookup"><span data-stu-id="7799b-178">Off</span></span>     | <span data-ttu-id="7799b-179">등</span><span class="sxs-lookup"><span data-stu-id="7799b-179">On</span></span>        |<span data-ttu-id="7799b-180">조직에 대해 모든 사용자 지정 앱과의 조작이 차단 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-180">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="7799b-181">사용자 지정 앱은 아무도 업로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-181">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="7799b-182">PowerShell을 사용 하 여 사용자 지정 앱을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-182">You can use PowerShell to remove the custom app.</span></span>         |
| <span data-ttu-id="7799b-183">끄십시오</span><span class="sxs-lookup"><span data-stu-id="7799b-183">Off</span></span>    | <span data-ttu-id="7799b-184">등</span><span class="sxs-lookup"><span data-stu-id="7799b-184">On</span></span>        | <span data-ttu-id="7799b-185">끄십시오</span><span class="sxs-lookup"><span data-stu-id="7799b-185">Off</span></span>        |<span data-ttu-id="7799b-186">조직에 대해 모든 사용자 지정 앱과의 조작이 차단 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-186">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="7799b-187">사용자 지정 앱은 아무도 업로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-187">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="7799b-188">Windows PowerShell을 사용 하 여 사용자 지정 앱을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-188">You can use Windows PowerShell to delete custom apps.</span></span>         |
| <span data-ttu-id="7799b-189">끄십시오</span><span class="sxs-lookup"><span data-stu-id="7799b-189">Off</span></span>    | <span data-ttu-id="7799b-190">등</span><span class="sxs-lookup"><span data-stu-id="7799b-190">On</span></span>      | <span data-ttu-id="7799b-191">등</span><span class="sxs-lookup"><span data-stu-id="7799b-191">On</span></span>       |<span data-ttu-id="7799b-192">조직에 대해 모든 사용자 지정 앱과의 조작이 차단 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-192">Interaction with all custom apps is blocked for your organization.</span></span> <span data-ttu-id="7799b-193">사용자 지정 앱은 아무도 업로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-193">Custom apps can't be uploaded by anyone.</span></span> <span data-ttu-id="7799b-194">PowerShell을 사용 하 여 사용자 지정 앱을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-194">You can use PowerShell to remove the custom app.</span></span>         |
| <span data-ttu-id="7799b-195">등</span><span class="sxs-lookup"><span data-stu-id="7799b-195">On</span></span>    | <span data-ttu-id="7799b-196">끄십시오</span><span class="sxs-lookup"><span data-stu-id="7799b-196">Off</span></span>       | <span data-ttu-id="7799b-197">끄십시오</span><span class="sxs-lookup"><span data-stu-id="7799b-197">Off</span></span>         |  <span data-ttu-id="7799b-198">사용자가 사용자 지정 앱을 업로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-198">The user can't upload custom apps.</span></span>      |
| <span data-ttu-id="7799b-199">등</span><span class="sxs-lookup"><span data-stu-id="7799b-199">On</span></span>     | <span data-ttu-id="7799b-200">끄십시오</span><span class="sxs-lookup"><span data-stu-id="7799b-200">Off</span></span>       | <span data-ttu-id="7799b-201">등</span><span class="sxs-lookup"><span data-stu-id="7799b-201">On</span></span>         | <span data-ttu-id="7799b-202">사용자가 팀 소유자 인 경우 팀에 사용자 지정 앱을 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-202">If the user is a team owner, they can upload custom apps to the team.</span></span> <span data-ttu-id="7799b-203">사용자가 팀 소유자가 아닌 경우 팀에 사용자 지정 앱을 업로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-203">If the user isn't a team owner, they can't upload custom apps to the team.</span></span> <span data-ttu-id="7799b-204">사용자는 개인 컨텍스트에서 사용자 지정 앱을 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-204">The user can upload custom apps in the personal context.</span></span>     |
| <span data-ttu-id="7799b-205">등</span><span class="sxs-lookup"><span data-stu-id="7799b-205">On</span></span>     | <span data-ttu-id="7799b-206">등</span><span class="sxs-lookup"><span data-stu-id="7799b-206">On</span></span>     | <span data-ttu-id="7799b-207">끄십시오</span><span class="sxs-lookup"><span data-stu-id="7799b-207">Off</span></span>         | <span data-ttu-id="7799b-208">사용자가 사용자 지정 앱을 업로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-208">The user can't upload custom apps.</span></span>       |
| <span data-ttu-id="7799b-209">등</span><span class="sxs-lookup"><span data-stu-id="7799b-209">On</span></span>    | <span data-ttu-id="7799b-210">등</span><span class="sxs-lookup"><span data-stu-id="7799b-210">On</span></span>        | <span data-ttu-id="7799b-211">등</span><span class="sxs-lookup"><span data-stu-id="7799b-211">On</span></span>        | <span data-ttu-id="7799b-212">사용자가 팀 소유자 인지 여부에 관계 없이 팀에 사용자 지정 앱을 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-212">The user can upload custom apps to the team, regardless of whether the user is a team owner.</span></span> <span data-ttu-id="7799b-213">사용자는 개인 컨텍스트에서 사용자 지정 앱을 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7799b-213">The user can upload custom apps in the personal context.</span></span>       |

 ## <a name="related-topics"></a><span data-ttu-id="7799b-214">관련 주제</span><span class="sxs-lookup"><span data-stu-id="7799b-214">Related topics</span></span>
 
- [<span data-ttu-id="7799b-215">Team에서 앱의 관리 설정</span><span class="sxs-lookup"><span data-stu-id="7799b-215">Admin settings for apps in Teams</span></span>](admin-settings.md)
