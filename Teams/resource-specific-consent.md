---
title: Microsoft 팀의 자원 관련 승인
author: LanaChin
ms.author: v-lanac
ms.reviewer: nkramer
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 조직의 팀 소유자가 앱에 동의 하도록 할 수 있는지 여부를 제어 하기 위해 구성 해야 하는 설정에 대해 알아봅니다.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1ed13f1f85b0c7eccead3737c4549931f016284c
ms.sourcegitcommit: 682566e51a9e5f0fc65540535c7dcdcbd38e04c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "45429380"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a><span data-ttu-id="85987-103">Microsoft 팀의 자원 관련 승인</span><span class="sxs-lookup"><span data-stu-id="85987-103">Resource-specific consent in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="85987-104">Microsoft 팀의 자원 관련 동의를 통해 팀 소유자는 팀 데이터에 액세스 하는 앱에 동의 합니다.</span><span class="sxs-lookup"><span data-stu-id="85987-104">Resource-specific consent in Microsoft Teams lets team owners give consent to apps to access team data.</span></span> <span data-ttu-id="85987-105">이러한 액세스의 예로는 채널 메시지를 읽고, 채널을 만들고, 삭제 하 고, 채널 탭을 만들고 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85987-105">Examples of such access include the ability to read channel messages, create and delete channels, and create and remove channel tabs.</span></span>

<span data-ttu-id="85987-106">관리자는 조직의 팀 소유자가 azure AD (azure Active Directory) PowerShell 모듈 또는 Azure 포털 및 Microsoft 팀 관리 센터를 사용 하 여 구성 하는 설정을 통해 승인을 제공할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="85987-106">As an admin, you control whether team owners in your organization can give consent through settings that you configure by using the Azure Active Directory (Azure AD) PowerShell module or the Azure portal and the Microsoft Teams admin center.</span></span>  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a><span data-ttu-id="85987-107">팀 소유자가 앱에 동의 하도록 지정할 수 있는지 여부 설정</span><span class="sxs-lookup"><span data-stu-id="85987-107">Set whether team owners can give consent to apps</span></span>

<span data-ttu-id="85987-108">팀 소유자가 앱에 동의 하도록 할 수 있는지 여부를 제어 하기 위해 설정 해야 하는 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="85987-108">Here are the settings that you must set to control whether team owners can give consent to apps.</span></span> <span data-ttu-id="85987-109">다음 설정을 모두 검토 하세요.</span><span class="sxs-lookup"><span data-stu-id="85987-109">Be sure to review all the following settings.</span></span>

### <a name="settings-in-azure-ad"></a><span data-ttu-id="85987-110">Azure AD의 설정</span><span class="sxs-lookup"><span data-stu-id="85987-110">Settings in Azure AD</span></span>

<span data-ttu-id="85987-111">다음 두 설정은 팀 소유자가 앱에 동의 하는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="85987-111">The following two settings determine whether team owners can give consent to apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="85987-112">이러한 설정을 변경 해도 이미 동의 하는 앱에 대 한 데이터 액세스는 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85987-112">Changing any of these settings doesn't affect data access for apps that were already granted consent.</span></span> <span data-ttu-id="85987-113">예를 들어 팀 소유자가 동의 하지 않도록 이러한 설정을 구성 하는 경우에는 이미 부여 된 데이터 액세스는 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85987-113">For example, if you configure these settings to prevent team owners from giving consent, these changes don't remove data access that's already been granted.</span></span>

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a><span data-ttu-id="85987-114">"사용자를 대신 하 여 회사 데이터에 액세스 하는 앱에 동의할 수 있음" 설정</span><span class="sxs-lookup"><span data-stu-id="85987-114">The "Users can consent to apps accessing company data on their behalf" setting</span></span>

<span data-ttu-id="85987-115">이 설정은 조직의 사용자가 앱에 동의할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="85987-115">This setting controls whether users in your organization can consent to apps on their behalf.</span></span> <span data-ttu-id="85987-116">팀 소유자가 동의를 제공할 수 있도록 하려면이 설정을 **Yes**로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85987-116">To enable team owners to give consent, this setting must be set to **Yes**.</span></span> <span data-ttu-id="85987-117">이 설정을 관리 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="85987-117">To manage this setting, do the following:</span></span>

1. <span data-ttu-id="85987-118">Azure 포털에서 **엔터프라이즈 응용 프로그램**  >  **사용자 설정**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="85987-118">In the Azure portal, go to **Enterprise applications** > **User settings**.</span></span>
2. <span data-ttu-id="85987-119">**엔터프라이즈 응용 프로그램**에서 사용자를 대신 **하 여** **회사 데이터에 액세스 하는 앱에 동의** 하는 것을 **설정 합니다.**</span><span class="sxs-lookup"><span data-stu-id="85987-119">Under **Enterprise applications**, set **Users can consent to apps accessing company data on their behalf** to **No** or **Yes**.</span></span>

<span data-ttu-id="85987-120">PowerShell을 사용 하 여이 설정을 관리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85987-120">You can also manage this setting using PowerShell.</span></span> <span data-ttu-id="85987-121">자세한 내용은 [응용 프로그램에 사용자 콘텐츠 구성을](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="85987-121">To learn more, see [Configure user content to applications](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications).</span></span>

#### <a name="the-enablegroupspecificconsent-setting"></a><span data-ttu-id="85987-122">"EnableGroupSpecificConsent" 설정</span><span class="sxs-lookup"><span data-stu-id="85987-122">The "EnableGroupSpecificConsent" setting</span></span>

<span data-ttu-id="85987-123">이 설정은 조직의 사용자가 소유 하 고 있는 그룹에 대 한 회사 데이터에 액세스 하는 앱에 동의할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="85987-123">This setting controls whether users in your organization can consent to apps accessing company data for the groups that they own.</span></span> <span data-ttu-id="85987-124">팀 소유자가 동의를 제공 하려면이 설정을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85987-124">This setting must be enabled for team owners to give consent.</span></span> <span data-ttu-id="85987-125">PowerShell을 사용 하 여이 설정을 관리 하는 방법에 대 한 단계는 [그룹 데이터에 액세스 하는 앱에 대 한 그룹 소유자 동의 구성을](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="85987-125">For steps on how to manage this setting by using PowerShell, see [Configure group owner consent to apps accessing group data](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data).</span></span>

### <a name="settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="85987-126">Microsoft 팀 관리 센터의 설정</span><span class="sxs-lookup"><span data-stu-id="85987-126">Settings in the Microsoft Teams admin center</span></span>

<span data-ttu-id="85987-127">앱 관리 페이지에서 Azure AD의 설정 [, 앱](manage-apps.md#manage-org-wide-app-settings) 이 차단 되거나 허용 되는지 [Manage apps](manage-apps.md) 여부, 팀 소유자에 게 할당 된 [앱 권한 정책](teams-app-permission-policies.md) 에 따라 [Manage apps](manage-apps.md#allow-and-block-apps) 팀 소유자가 동의를 제공할 수 있는지 여부가 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85987-127">In addition to settings in Azure AD, [org-wide app settings](manage-apps.md#manage-org-wide-app-settings) on the [Manage apps](manage-apps.md) page, whether an app is blocked or allowed on the [Manage apps](manage-apps.md#allow-and-block-apps) page, and the [app permission policy](teams-app-permission-policies.md) assigned to the team owner determine whether a team owner can give consent.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="85987-128">이러한 설정을 변경 해도 이미 동의 하는 앱에 대 한 데이터 액세스는 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85987-128">Changing any of these settings doesn't affect data access for apps that were already granted consent.</span></span> <span data-ttu-id="85987-129">예를 들어 조직 전체에서 타사 앱을 사용 하지 않도록 설정 하거나 특정 앱을 차단 하 여 팀 소유자가 동의 하지 않도록 하는 경우 이러한 변경 내용은 이미 부여 된 데이터 액세스를 제거 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85987-129">For example, if you disable third-party apps org-wide or if you block specific apps to prevent team owners from giving consent, these changes don't remove data access that's already been granted.</span></span>  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a><span data-ttu-id="85987-130">조직 전체 앱 설정의 "타사 앱 허용" 설정</span><span class="sxs-lookup"><span data-stu-id="85987-130">The "Allow third party apps" setting in org-wide app settings</span></span>

<span data-ttu-id="85987-131">이 조직 전체 앱 설정은 조직의 사용자가 타사 앱을 사용할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="85987-131">This org-wide app setting controls whether users in your organization can use third-party apps.</span></span> <span data-ttu-id="85987-132">팀 소유자가 동의 하도록 설정 하려면이 설정을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85987-132">This setting must be on to enable team owners to give consent.</span></span> <span data-ttu-id="85987-133">이 설정을 관리 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="85987-133">To manage this setting, do the following:</span></span>

1. <span data-ttu-id="85987-134">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**으로 이동 하 여  >  **앱을 관리**하 고 **조직 전체 앱 설정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="85987-134">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**, and then click **Org-wide app settings**.</span></span>
2. <span data-ttu-id="85987-135">타사 **앱**에서 타사 **앱 허용**을 설정 하거나 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="85987-135">Under **Third party apps**, turn off or turn on **Allow third party apps**.</span></span>

    !["팀에서 타사 앱 허용" 설정의 스크린샷](media/resource-specific-consent-org-wide-setting.png)

<span data-ttu-id="85987-137">변경 내용이 적용되는 데 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85987-137">You may have to wait up to 24 hours for your changes to take effect.</span></span>

#### <a name="allow-or-block-the-app-at-the-org-level"></a><span data-ttu-id="85987-138">조직 수준에서 앱 허용 또는 차단</span><span class="sxs-lookup"><span data-stu-id="85987-138">Allow or block the app at the org level</span></span>

<span data-ttu-id="85987-139">앱 [관리](manage-apps.md#allow-and-block-apps) 페이지에서 앱을 차단 하거나 허용 하면 해당 앱이 차단 되거나 조직의 모든 사용자에 게 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85987-139">When you block or allow an app on the [Manage apps](manage-apps.md#allow-and-block-apps) page, that app is blocked or allowed for all users in your organization.</span></span> <span data-ttu-id="85987-140">앱이 허용 되는 경우 팀 소유자는 앱에 대 한 동의만 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85987-140">Team owners can only give consent to an app if the app is allowed.</span></span> <span data-ttu-id="85987-141">조직 수준에서 앱을 허용 하거나 차단 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="85987-141">To allow or block an app at the org level, do the following:</span></span>

1. <span data-ttu-id="85987-142">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**으로  >  **앱 관리**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="85987-142">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="85987-143">앱 관리 페이지에서 앱을 선택한 다음 **차단** 을 클릭 하 여 차단 하거나 허용 하도록 **허용** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="85987-143">On the Manage apps page, select the app, and then click **Block** to block it or click **Allow** to allow it.</span></span>

    ![조직 전체 설정의 차단 된 앱 스크린샷](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a><span data-ttu-id="85987-145">팀 소유자에 게 할당 된 앱 권한 정책</span><span class="sxs-lookup"><span data-stu-id="85987-145">App permission policy assigned to the team owner</span></span>

<span data-ttu-id="85987-146">팀 소유자는 앱 권한 정책에서 실행할 수 있도록 허용 하는 앱에만 동의를 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85987-146">Team owners can only give consent to apps that their app permission policy allows them to run.</span></span> <span data-ttu-id="85987-147">팀 소유자에 게 할당 된 앱 권한 정책을 보고 관리 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="85987-147">To view and manage the app permission policy that's assigned to a team owner, do the following:</span></span>

1. <span data-ttu-id="85987-148">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="85987-148">In the left navigation of the Microsoft Teams admin center, go to **Users**.</span></span>
2. <span data-ttu-id="85987-149">팀 소유자의 표시 이름을 두 번 클릭 한 다음 **정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="85987-149">Double-click the display name of the team owner, and then click **Policies**.</span></span>
3. <span data-ttu-id="85987-150">팀 소유자에 게 할당 된 정책이 **앱 권한 정책**아래에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85987-150">The policy assigned to the team owner is listed under **App permission policy**.</span></span>
    - <span data-ttu-id="85987-151">다른 정책을 할당 하려면 **편집**을 클릭 한 다음 할당 하려는 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="85987-151">To assign a different policy, click **Edit**, and then select the policy that you want to assign.</span></span>
    - <span data-ttu-id="85987-152">팀 소유자에 게 할당 된 정책의 설정을 편집 하려면 정책 이름을 클릭 한 다음 원하는 대로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="85987-152">To edit the settings of the policy that's assigned to the team owner, click the policy name, and then make the changes that you want.</span></span>  

## <a name="uploading-custom-apps"></a><span data-ttu-id="85987-153">사용자 지정 앱 업로드</span><span class="sxs-lookup"><span data-stu-id="85987-153">Uploading custom apps</span></span>

<span data-ttu-id="85987-154">리소스 관련 승인을 사용 하는 사용자 지정 앱 (또한 테스트용으로 생성 됨)을 업로드 하는 경우 앱이 설치 되는 테 넌 트에서 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85987-154">When uploading a custom app (also known sideloading) that uses resource-specific consent, the app must come from the tenant that it's being installed to.</span></span> <span data-ttu-id="85987-155">즉, Azure AD 앱 등록은이 테 넌 트에서 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85987-155">In other words, the Azure AD app registration must be from this tenant.</span></span> <span data-ttu-id="85987-156">전역 관리자는이 제한에서 제외 되며, 팀 (테스트용 로드) 또는 테 넌 트 앱 카탈로그로 직접 모든 테 넌 트에서 사용자 지정 앱을 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85987-156">Global admins are exempted from this restriction, and can upload custom apps from any tenant, either directly to a team (sideloading) or to the tenant app catalog.</span></span>

## <a name="related-topics"></a><span data-ttu-id="85987-157">관련 항목</span><span class="sxs-lookup"><span data-stu-id="85987-157">Related topics</span></span>

- [<span data-ttu-id="85987-158">사용 가능한 RSC 권한</span><span class="sxs-lookup"><span data-stu-id="85987-158">Available RSC permissions</span></span>](https://aka.ms/teams-rsc)
- [<span data-ttu-id="85987-159">Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="85987-159">Microsoft Graph</span></span>](https://developer.microsoft.com/graph)
- [<span data-ttu-id="85987-160">Microsoft 팀 관리 센터에서 앱 관리</span><span class="sxs-lookup"><span data-stu-id="85987-160">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="85987-161">Teams에서 앱 사용 권한 정책 관리</span><span class="sxs-lookup"><span data-stu-id="85987-161">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
