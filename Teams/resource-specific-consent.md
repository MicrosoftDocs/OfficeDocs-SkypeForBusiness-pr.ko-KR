---
title: Microsoft Teams의 리소스별 동의
author: cichur
ms.author: v-cichur
ms.reviewer: nkramer
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 조직의 팀 소유자가 앱에 동의할 수 있는지 여부를 제어하도록 구성해야 하는 설정에 대해 자세히 배워야 합니다.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d6267f4b42890716ca31fd1b44de435af50ad6ae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815678"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a><span data-ttu-id="1ba91-103">Microsoft Teams의 리소스별 동의</span><span class="sxs-lookup"><span data-stu-id="1ba91-103">Resource-specific consent in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="1ba91-104">Microsoft Teams의 리소스별 동의를 통해 팀 소유자는 앱에 동의하여 팀 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ba91-104">Resource-specific consent in Microsoft Teams lets team owners give consent to apps to access team data.</span></span> <span data-ttu-id="1ba91-105">이러한 액세스의 예로는 채널 메시지를 읽고, 채널을 만들고 삭제하고, 채널 탭을 만들고 제거하는 기능을 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ba91-105">Examples of such access include the ability to read channel messages, create and delete channels, and create and remove channel tabs.</span></span>

<span data-ttu-id="1ba91-106">관리자는 조직의 팀 소유자가 Azure AD(Azure Active Directory) PowerShell 모듈 또는 Azure Portal 및 Microsoft Teams 관리 센터를 사용하여 구성한 설정을 통해 동의할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="1ba91-106">As an admin, you control whether team owners in your organization can give consent through settings that you configure by using the Azure Active Directory (Azure AD) PowerShell module or the Azure portal and the Microsoft Teams admin center.</span></span>  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a><span data-ttu-id="1ba91-107">팀 소유자가 앱에 동의할 수 있는지 여부 설정</span><span class="sxs-lookup"><span data-stu-id="1ba91-107">Set whether team owners can give consent to apps</span></span>

<span data-ttu-id="1ba91-108">다음은 팀 소유자가 앱에 동의할 수 있는지 여부를 제어하기 위해 설정해야 하는 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="1ba91-108">Here are the settings that you must set to control whether team owners can give consent to apps.</span></span> <span data-ttu-id="1ba91-109">다음 설정을 모두 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ba91-109">Be sure to review all the following settings.</span></span>

### <a name="settings-in-azure-ad"></a><span data-ttu-id="1ba91-110">Azure AD의 설정</span><span class="sxs-lookup"><span data-stu-id="1ba91-110">Settings in Azure AD</span></span>

<span data-ttu-id="1ba91-111">다음 두 설정은 팀 소유자가 앱에 동의할 수 있는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1ba91-111">The following two settings determine whether team owners can give consent to apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1ba91-112">이러한 설정을 변경해도 이미 동의가 부여된 앱의 데이터 액세스에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ba91-112">Changing any of these settings doesn't affect data access for apps that were already granted consent.</span></span> <span data-ttu-id="1ba91-113">예를 들어 팀 소유자가 동의하지 못하도록 이러한 설정을 구성하는 경우 이러한 변경 내용은 이미 부여된 데이터 액세스를 제거하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ba91-113">For example, if you configure these settings to prevent team owners from giving consent, these changes don't remove data access that's already been granted.</span></span>

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a><span data-ttu-id="1ba91-114">"사용자가 사용자를 대신하여 회사 데이터에 액세스하는 앱에 동의할 수 있습니다." 설정</span><span class="sxs-lookup"><span data-stu-id="1ba91-114">The "Users can consent to apps accessing company data on their behalf" setting</span></span>

<span data-ttu-id="1ba91-115">이 설정은 조직의 사용자가 사용자를 대신하여 앱에 동의할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="1ba91-115">This setting controls whether users in your organization can consent to apps on their behalf.</span></span> <span data-ttu-id="1ba91-116">팀 소유자가 동의할 수 있도록 설정하려면 이 설정을 예로 설정해야 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="1ba91-116">To enable team owners to give consent, this setting must be set to **Yes**.</span></span> <span data-ttu-id="1ba91-117">이 설정을 관리하기 위해 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ba91-117">To manage this setting, do the following:</span></span>

1. <span data-ttu-id="1ba91-118">Azure Portal에서 엔터프라이즈 애플리케이션 **사용자**  >  **설정으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="1ba91-118">In the Azure portal, go to **Enterprise applications** > **User settings**.</span></span>
2. <span data-ttu-id="1ba91-119">엔터프라이즈 **애플리케이션에서**  사용자를 대신하여 회사 데이터에 액세스하는 앱에 동의할 수 있도록 **설정하여 아니요** 또는 예로 **설정할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="1ba91-119">Under **Enterprise applications**, set **Users can consent to apps accessing company data on their behalf** to **No** or **Yes**.</span></span>

<span data-ttu-id="1ba91-120">PowerShell을 사용하여 이 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ba91-120">You can also manage this setting using PowerShell.</span></span> <span data-ttu-id="1ba91-121">자세한 내용은 애플리케이션에 [대한 사용자 콘텐츠 구성을 참조하세요.](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications)</span><span class="sxs-lookup"><span data-stu-id="1ba91-121">To learn more, see [Configure user content to applications](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications).</span></span>

#### <a name="the-enablegroupspecificconsent-setting"></a><span data-ttu-id="1ba91-122">"EnableGroupSpecificConsent" 설정</span><span class="sxs-lookup"><span data-stu-id="1ba91-122">The "EnableGroupSpecificConsent" setting</span></span>

<span data-ttu-id="1ba91-123">이 설정은 조직의 사용자가 소유한 그룹의 회사 데이터에 액세스하는 앱에 동의할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="1ba91-123">This setting controls whether users in your organization can consent to apps accessing company data for the groups that they own.</span></span> <span data-ttu-id="1ba91-124">팀 소유자가 동의를 제공하려면 이 설정을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ba91-124">This setting must be enabled for team owners to give consent.</span></span> <span data-ttu-id="1ba91-125">PowerShell을 사용하여 이 설정을 관리하는 방법에 대한 단계는 그룹 데이터에 액세스하는 앱에 대한 그룹 소유자 동의 [구성을 참조하세요.](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data)</span><span class="sxs-lookup"><span data-stu-id="1ba91-125">For steps on how to manage this setting by using PowerShell, see [Configure group owner consent to apps accessing group data](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data).</span></span>

### <a name="settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="1ba91-126">Microsoft Teams 관리 센터의 설정</span><span class="sxs-lookup"><span data-stu-id="1ba91-126">Settings in the Microsoft Teams admin center</span></span>

<span data-ttu-id="1ba91-127">Azure AD의 설정 외에도 [](manage-apps.md#manage-org-wide-app-settings) 앱 관리 페이지의 전체 앱 설정, 앱 관리 페이지에서 앱이 차단되거나 허용되는지 [](teams-app-permission-policies.md) 여부 및 팀 소유자에게 할당된 앱 사용 권한 정책에 따라 팀 소유자가 동의할 수 있는지 여부가 결정됩니다. [](manage-apps.md) [](manage-apps.md#allow-and-block-apps)</span><span class="sxs-lookup"><span data-stu-id="1ba91-127">In addition to settings in Azure AD, [org-wide app settings](manage-apps.md#manage-org-wide-app-settings) on the [Manage apps](manage-apps.md) page, whether an app is blocked or allowed on the [Manage apps](manage-apps.md#allow-and-block-apps) page, and the [app permission policy](teams-app-permission-policies.md) assigned to the team owner determine whether a team owner can give consent.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1ba91-128">이러한 설정을 변경해도 이미 동의가 부여된 앱의 데이터 액세스에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ba91-128">Changing any of these settings doesn't affect data access for apps that were already granted consent.</span></span> <span data-ttu-id="1ba91-129">예를 들어, 타사 앱을 전체적으로 사용하지 않도록 설정하거나 팀 소유자가 동의하지 못하도록 특정 앱을 차단하는 경우 이러한 변경 내용은 이미 부여된 데이터 액세스를 제거하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ba91-129">For example, if you disable third-party apps org-wide or if you block specific apps to prevent team owners from giving consent, these changes don't remove data access that's already been granted.</span></span>  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a><span data-ttu-id="1ba91-130">전체 앱 설정의 "타사 앱 허용" 설정</span><span class="sxs-lookup"><span data-stu-id="1ba91-130">The "Allow third party apps" setting in org-wide app settings</span></span>

<span data-ttu-id="1ba91-131">이 조직 전체 앱 설정은 조직의 사용자가 타사 앱을 사용할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="1ba91-131">This org-wide app setting controls whether users in your organization can use third-party apps.</span></span> <span data-ttu-id="1ba91-132">팀 소유자가 동의할 수 있도록 이 설정이 설정되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ba91-132">This setting must be on to enable team owners to give consent.</span></span> <span data-ttu-id="1ba91-133">이 설정을 관리하기 위해 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ba91-133">To manage this setting, do the following:</span></span>

1. <span data-ttu-id="1ba91-134">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 **Teams** 앱 관리 앱으로 이동한 다음, 전체 앱 설정을  >   **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="1ba91-134">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**, and then click **Org-wide app settings**.</span></span>
2. <span data-ttu-id="1ba91-135">타사 **앱에서** 타사 앱 허용을 끄거나 **끄면 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="1ba91-135">Under **Third party apps**, turn off or turn on **Allow third party apps**.</span></span>

    !["Teams에서 타사 앱 허용" 설정 스크린샷](media/resource-specific-consent-org-wide-setting.png)

<span data-ttu-id="1ba91-137">변경 내용이 적용되는 데 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ba91-137">You may have to wait up to 24 hours for your changes to take effect.</span></span>

#### <a name="allow-or-block-the-app-at-the-org-level"></a><span data-ttu-id="1ba91-138">Or block the app at the or block the or block the app at the or block the level</span><span class="sxs-lookup"><span data-stu-id="1ba91-138">Allow or block the app at the org level</span></span>

<span data-ttu-id="1ba91-139">앱 관리 페이지에서 앱을 차단하거나 허용하면 해당 앱이 차단되거나 조직의 모든 사용자에게 허용됩니다. [](manage-apps.md#allow-and-block-apps)</span><span class="sxs-lookup"><span data-stu-id="1ba91-139">When you block or allow an app on the [Manage apps](manage-apps.md#allow-and-block-apps) page, that app is blocked or allowed for all users in your organization.</span></span> <span data-ttu-id="1ba91-140">팀 소유자는 앱이 허용되는 경우 앱에 동의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ba91-140">Team owners can only give consent to an app if the app is allowed.</span></span> <span data-ttu-id="1ba91-141">Or block an app at the or block the or block the or block the or do the following:</span><span class="sxs-lookup"><span data-stu-id="1ba91-141">To allow or block an app at the org level, do the following:</span></span>

1. <span data-ttu-id="1ba91-142">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 Teams 앱 **관리**  >  **앱으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="1ba91-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="1ba91-143">앱 관리 페이지에서 앱을 선택한 다음 차단을 클릭하여 차단하거나  허용을 클릭합니다. </span><span class="sxs-lookup"><span data-stu-id="1ba91-143">On the Manage apps page, select the app, and then click **Block** to block it or click **Allow** to allow it.</span></span>

    ![전체 설정에서 차단된 앱의 스크린샷](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a><span data-ttu-id="1ba91-145">팀 소유자에게 할당된 앱 사용 권한 정책</span><span class="sxs-lookup"><span data-stu-id="1ba91-145">App permission policy assigned to the team owner</span></span>

<span data-ttu-id="1ba91-146">팀 소유자는 앱 사용 권한 정책이 실행할 수 있도록 허용하는 앱에만 동의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ba91-146">Team owners can only give consent to apps that their app permission policy allows them to run.</span></span> <span data-ttu-id="1ba91-147">팀 소유자에게 할당된 앱 사용 권한 정책을 보고 관리하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1ba91-147">To view and manage the app permission policy that's assigned to a team owner, do the following:</span></span>

1. <span data-ttu-id="1ba91-148">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 사용자로 **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="1ba91-148">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="1ba91-149">팀 소유자의 표시 이름을 두 번 클릭한 다음 정책을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="1ba91-149">Double-click the display name of the team owner, and then click **Policies**.</span></span>
3. <span data-ttu-id="1ba91-150">팀 소유자에게 할당된 정책은 앱 사용 권한 정책 **아래에 나열됩니다.**</span><span class="sxs-lookup"><span data-stu-id="1ba91-150">The policy assigned to the team owner is listed under **App permission policy**.</span></span>
    - <span data-ttu-id="1ba91-151">다른 정책을 할당하려면 **편집을** 클릭한 다음 할당할 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1ba91-151">To assign a different policy, click **Edit**, and then select the policy that you want to assign.</span></span>
    - <span data-ttu-id="1ba91-152">팀 소유자에게 할당된 정책 설정을 편집하려면 정책 이름을 클릭한 다음 원하는 내용을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="1ba91-152">To edit the settings of the policy that's assigned to the team owner, click the policy name, and then make the changes that you want.</span></span>  

## <a name="uploading-custom-apps"></a><span data-ttu-id="1ba91-153">사용자 지정 앱 업로드</span><span class="sxs-lookup"><span data-stu-id="1ba91-153">Uploading custom apps</span></span>

<span data-ttu-id="1ba91-154">리소스별 동의를 사용하는 사용자 지정 앱(사이드로드라고도 하는)을 업로드할 때 앱이 설치되는 테넌트에서 제공되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ba91-154">When uploading a custom app (also known sideloading) that uses resource-specific consent, the app must come from the tenant that it's being installed to.</span></span> <span data-ttu-id="1ba91-155">즉, Azure AD 앱 등록은 이 테넌트에서 제공되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ba91-155">In other words, the Azure AD app registration must be from this tenant.</span></span> <span data-ttu-id="1ba91-156">전역 관리자는 이 제한에서 제외되고, 모든 테넌트에서 직접 팀(사이드로드) 또는 테넌트 앱 카탈로그에 사용자 지정 앱을 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ba91-156">Global admins are exempted from this restriction, and can upload custom apps from any tenant, either directly to a team (sideloading) or to the tenant app catalog.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1ba91-157">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1ba91-157">Related topics</span></span>

- [<span data-ttu-id="1ba91-158">사용 가능한 RSC 권한</span><span class="sxs-lookup"><span data-stu-id="1ba91-158">Available RSC permissions</span></span>](https://aka.ms/teams-rsc)
- [<span data-ttu-id="1ba91-159">Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="1ba91-159">Microsoft Graph</span></span>](https://developer.microsoft.com/graph)
- [<span data-ttu-id="1ba91-160">Microsoft Teams 관리 센터에서 앱 관리</span><span class="sxs-lookup"><span data-stu-id="1ba91-160">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="1ba91-161">Teams에서 앱 사용 권한 정책 관리</span><span class="sxs-lookup"><span data-stu-id="1ba91-161">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
