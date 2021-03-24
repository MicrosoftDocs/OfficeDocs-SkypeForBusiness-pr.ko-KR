---
title: Microsoft Teams 관리 센터에서 앱 권한 보기 및 관리자 동의 부여
author: cichur
ms.author: v-cichur
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 앱에서 요청한 권한을 보고 Microsoft Teams 관리 센터의 앱 관리 페이지에서 앱에 관리자 동의를 부여하는 방법을 알아보십시오.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2833a548ccf66b327d9feb71155f1ed33a671f1c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094660"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="a3546-103">Microsoft Teams 관리 센터에서 앱 권한 보기 및 관리자 동의 부여</span><span class="sxs-lookup"><span data-stu-id="a3546-103">View app permissions and grant admin consent in the Microsoft Teams admin center</span></span>

<span data-ttu-id="a3546-104">Microsoft [Teams](manage-apps.md) 관리 센터의 앱 관리 페이지는 조직의 모든 Teams 앱을 보고 관리하는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-104">The [Manage apps](manage-apps.md) page in the Microsoft Teams admin center is where you view and manage all Teams apps for your organization.</span></span> <span data-ttu-id="a3546-105">예를 들어 앱의 조직 수준 상태 및 속성을 보고, 조직의 앱 스토어에 새 사용자 지정 앱을 승인 또는 업로드하고, 조직 수준에서 앱을 차단 또는 허용하고, 조직 전체 앱 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-105">For example, you can see the org-level status and properties of apps, approve or upload new custom apps to your organization's app store, block or allow apps at the org level, and manage org-wide app settings.</span></span>

<span data-ttu-id="a3546-106">여기에서 데이터에 액세스하고 앱에 대한 리소스별 동의(RSC) 권한을 볼 수 있는 권한을 요청하는 앱에 대한 전체 관리자 동의를 부여할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-106">Here, you can also grant org-wide admin consent to apps that request permissions to access data and view resource-specific consent (RSC) permissions for apps.</span></span>

## <a name="grant-org-wide-admin-consent-to-an-app"></a><span data-ttu-id="a3546-107">앱에 대한 전체 관리자 동의 부여</span><span class="sxs-lookup"><span data-stu-id="a3546-107">Grant org-wide admin consent to an app</span></span>

<span data-ttu-id="a3546-108">전역 관리자인 경우 조직의 모든 사용자를 대신하여 권한을 요청하는 앱에 대한 동의를 검토하고 동의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-108">If you're a global admin, you can review and grant consent to apps that request permissions on behalf of all users in your organization.</span></span> <span data-ttu-id="a3546-109">사용자가 앱을 시작할 때 앱에서 요청한 권한을 검토하고 수락할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-109">You do this so that users don't have to review and accept the permissions requested by the app when they start the app.</span></span> <span data-ttu-id="a3546-110">또한 Azure AD(Azure Active [](/azure/active-directory/manage-apps/configure-user-consent) Directory)의 사용자의 동의 설정에 따라 일부 사용자가 회사 데이터에 액세스하는 앱에 대한 동의를 부여할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-110">Additionally, depending on the user's [consent settings](/azure/active-directory/manage-apps/configure-user-consent) in Azure Active Directory (Azure AD), some users may not be allowed to grant consent to apps that access company data.</span></span>

<span data-ttu-id="a3546-111">앱에서 요청하는 사용 권한의 예로는 팀에 저장된 정보를 읽고, 사용자의 프로필을 읽고, 사용자를 대신하여 전자 메일을 보낼 수 있는 기능을 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-111">Examples of permissions requested by apps include the ability to read information stored in a team, read a user's profile, and send an email on behalf of users.</span></span> <span data-ttu-id="a3546-112">자세한 내용은 Microsoft ID 플랫폼 엔드포인트의 사용 권한 및 [동의를 참조합니다.](/azure/active-directory/develop/v2-permissions-and-consent)</span><span class="sxs-lookup"><span data-stu-id="a3546-112">To learn more, see [Permissions and consent in the Microsoft identity platform endpoint](/azure/active-directory/develop/v2-permissions-and-consent).</span></span> 

<span data-ttu-id="a3546-113">사용 **권한 열은** 앱에 동의가 필요한 권한이 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-113">The **Permissions** column indicates whether an app has permissions that need consent.</span></span> <span data-ttu-id="a3546-114">동의가 필요한  권한이 있는 Azure AD에 등록된 각 앱에 대한 보기 세부 정보 링크가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-114">You'll see a **View details** link for each app registered in Azure AD that has permissions that need consent.</span></span> <span data-ttu-id="a3546-115">이 기능은 사용자 지정 및 타사 앱에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-115">Keep in mind that this applies only to custom and third-party apps.</span></span> <span data-ttu-id="a3546-116">이 링크가 표시되거나 Microsoft에서 게시한 앱에 대한 관리자 동의를 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-116">You won't see this link or need to grant admin consent for apps published by Microsoft.</span></span>

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="앱 관리 페이지에서 사용 권한 열 스크린샷":::

<span data-ttu-id="a3546-118">앱에 대한 전체 동의를 부여하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-118">To grant org-wide consent to an app, follow these steps:</span></span>

1. <span data-ttu-id="a3546-119">Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **Teams 앱** > **앱 관리** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-119">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="a3546-120">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-120">Do one of the following:</span></span>
    - <span data-ttu-id="a3546-121">원하는 앱을 검색하고 앱 이름을 클릭하여 앱 세부 정보 페이지로 이동한 다음 사용 권한 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-121">Search for the app you want, click the app name to go to the app details page, and then select the **Permissions** tab.</span></span>
    - <span data-ttu-id="a3546-122">사용 **권한** 열을 내선 순서로 정렬하여 앱을 찾은 다음 세부 **정보 보기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a3546-122">Sort the **Permissions** column in descending order to find the app, and then select **View details**.</span></span> <span data-ttu-id="a3546-123">이렇게 하면 앱 세부 정보 페이지의 **사용** 권한 탭으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-123">Doing this takes you to the **Permissions** tab of the app details page.</span></span>

3. <span data-ttu-id="a3546-124">**Org 전체 사용 권한에서** 사용 권한 검토 **및 동의를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a3546-124">Under **Org-wide permissions**, select **Review permissions and consent**.</span></span>

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="앱에 대한 사용 권한 탭의 전체 권한 스크린샷":::

    <span data-ttu-id="a3546-126">이 작업을하려면 전역 관리자가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-126">You must be a global admin to do this.</span></span> <span data-ttu-id="a3546-127">Teams 서비스 관리자는 이 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-127">This option isn't available to Teams service admins.</span></span>

4. <span data-ttu-id="a3546-128">사용 권한 **탭에서** 앱에서 요청한 권한을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-128">On the **Permissions** tab, review the permissions requested by the app.</span></span>

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="앱에서 요청한 권한 스크린샷":::

    > [!IMPORTANT]
    > <span data-ttu-id="a3546-130">앱에 조직 전체 동의를 부여하면 앱이 조직의 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-130">Granting org-wide consent to an app allows the app to access your organization's data.</span></span> <span data-ttu-id="a3546-131">동의를 부여하기 전에 앱에서 요청한 권한을 신중하게 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-131">Carefully review the permissions requested by the app before you grant consent.</span></span>
5. <span data-ttu-id="a3546-132">앱에서 요청한 사용 권한에 동의하는 경우 수락을 클릭하여 **동의를** 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-132">If you agree with the permissions requested by the app, click **Accept** to grant consent.</span></span> <span data-ttu-id="a3546-133">요청된 사용 권한이 앱에 부여된 것을 알 수 있는 배너가 페이지 맨 위에 일시적으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-133">A banner temporarily appears at the top of the page to let you know that the requested permissions have been granted for the app.</span></span> <span data-ttu-id="a3546-134">이제 앱에서 조직의 모든 사용자에 대해 지정된 리소스에 액세스할 수 있으며 다른 사용자가 권한을 검토하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-134">The app now has access to the specified resources for all users in your organization and no one else will be prompted to review the permissions.</span></span>

<span data-ttu-id="a3546-135">사용 권한을 수락하면 앱 세부 정보 페이지에 **Org 전체** 사용 권한 아래에서 동의가 부여된 것을 알 수 있는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-135">After you accept the permissions, you'll see a message under **Org-wide permissions** on the app details page to let you know that consent was granted.</span></span> <span data-ttu-id="a3546-136">앱의 사용 권한에 대한 세부 정보를 보려면 **Azure Active Directory** 링크를 클릭하여 Azure AD 포털의 앱 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-136">To view details about the app's permissions, click the **Azure Active Directory** link to go to the app's page in the Azure AD portal.</span></span>

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="동의가 부여될 때 표시되는 메시지 스크린샷":::

<span data-ttu-id="a3546-138">조직의 사용자가 동의를 부여할 수 있으며 특정 앱에 대해 하나 이상의 사용자가 동의를 부여한 경우 Azure AD 포털의 앱 페이지에 대한 Azure Active Directory 링크와 동의가 부여된 것을 알려주는 동일한 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-138">If users in your organization are allowed to grant consent and if one or more users granted consent to a particular app, you'll also see the same message to let you know that consent was granted and the Azure Active Directory link to the app's page in the Azure AD portal.</span></span>

> [!NOTE]
> <span data-ttu-id="a3546-139">Teams 서비스  관리자가 검토 권한 및 동의 옵션을 사용할 수 없는 경우 앱에 대한 전체 관리자 동의를 부여할 수 없습니다.  Teams 서비스 관리자는 앱의 사용 권한 탭에서 콘텐츠를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-139">Although, the **Review permissions and consent** option isn't available to Teams service admins and they can't grant org-wide admin consent to apps, Teams service admins can view the content on the **Permissions** tab for an app.</span></span> <span data-ttu-id="a3546-140">예를 들어 Teams 서비스 관리자는 **Azure Active Directory 링크를** 클릭하여 Azure AD 포털에서 앱 사용 권한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-140">For example, a Teams service admin can click the **Azure Active Directory** link to view app permissions details in the Azure AD portal.</span></span> 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a><span data-ttu-id="a3546-141">앱의 리소스별 동의 권한 보기</span><span class="sxs-lookup"><span data-stu-id="a3546-141">View resource-specific consent permissions of an app</span></span>

<span data-ttu-id="a3546-142">RSC 권한을 통해 팀 소유자는 앱에 대한 동의를 부여하여 팀의 데이터에 액세스하고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-142">RSC permissions let team owners grant consent for an app to access and modify a team's data.</span></span> <span data-ttu-id="a3546-143">RSC 권한은 특정 팀에서 앱에서 할 수 있는 작업을 정의하는 세분화된 Teams별 사용 권한입니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-143">RSC permissions are granular, Teams-specific permissions that define what an app can do in a specific team.</span></span> <span data-ttu-id="a3546-144">RSC 사용 권한의 예로는 채널을 만들고 삭제하고, 팀에 대한 설정을 구하고, 채널 탭을 만들고 제거할 수 있는 기능을 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-144">Examples of RSC permissions include the ability to create and delete channels, get the settings for a team, and create and remove channel tabs.</span></span> 

<span data-ttu-id="a3546-145">RSC 권한은 Azure AD가 아닌 앱 매니페스트에 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-145">RSC permissions are defined in the app manifest and not in Azure AD.</span></span> <span data-ttu-id="a3546-146">팀에 앱을 추가할 때 RSC 사용 권한에 대한 동의를 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-146">You grant consent to RSC permissions when you add the app to a team.</span></span> <span data-ttu-id="a3546-147">자세한 내용은 [RSC(리소스별 동의) 를 참조하세요.](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)</span><span class="sxs-lookup"><span data-stu-id="a3546-147">To learn more, see [Resource-specific consent (RSC)](/microsoftteams/platform/graph-api/rsc/resource-specific-consent).</span></span>

<span data-ttu-id="a3546-148">전역 관리자 및 Teams 서비스 관리자는 앱 세부 정보 페이지의  사용 권한 탭에서 앱에 대한 RSC 권한을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-148">Global admins and Teams service admin can view RSC permissions for an app on the **Permissions** tab of the app details page.</span></span> 

<span data-ttu-id="a3546-149">앱에 대한 RSC 권한을 보기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-149">To view RSC permissions for an app, follow these steps:</span></span>

1. <span data-ttu-id="a3546-150">Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **Teams 앱** > **앱 관리** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-150">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="a3546-151">원하는 앱을 검색하고 앱 이름을 클릭하여 앱 세부 정보 페이지로 이동한 다음 사용 권한 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-151">Search for the app you want, click the app name to go to the app details page, and then select the **Permissions** tab.</span></span>
3. <span data-ttu-id="a3546-152">**Microsoft Graph 리소스별 동의(RSC)** 사용 권한 아래에서 앱에서 요청한 RSC 권한을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-152">Under **Microsoft Graph resource-specific consent (RSC) permissions**, review the RSC permissions requested by the app.</span></span>

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="앱에 대한 RSC 사용 권한 스크린샷":::

## <a name="known-issues"></a><span data-ttu-id="a3546-154">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="a3546-154">Known issues</span></span>

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a><span data-ttu-id="a3546-155">권한을 요청하는 일부 타사 앱의 사용 권한 열에 "세부 정보 보기" 링크가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-155">The "View details" link isn't displayed in the Permissions column for some third-party apps that request permissions</span></span>

<span data-ttu-id="a3546-156">현재 권한을 요청하는 Azure AD에 등록된 모든 타사 앱에는 사용 권한을 검토하고 동의를 부여하는 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-156">Currently, the ability to review permissions and grant consent isn't available for all third-party apps registered in Azure AD that request permissions.</span></span> <span data-ttu-id="a3546-157">보기 세부  정보 링크 대신 사용 권한 **--** **열에 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="a3546-157">Instead of the **View details** link, you'll see **--** in the **Permissions** column.</span></span> <span data-ttu-id="a3546-158">해당 앱에 대해 이 기능을 사용하도록 설정하기 위해 ISV를 사용 중입니다.</span><span class="sxs-lookup"><span data-stu-id="a3546-158">We're working with ISVs to enable this feature for their apps.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a3546-159">관련 항목</span><span class="sxs-lookup"><span data-stu-id="a3546-159">Related topics</span></span>

- [<span data-ttu-id="a3546-160">Microsoft Teams 관리 센터에서 앱 관리</span><span class="sxs-lookup"><span data-stu-id="a3546-160">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="a3546-161">Microsoft ID 플랫폼 엔드포인트의 사용 권한 및 동의</span><span class="sxs-lookup"><span data-stu-id="a3546-161">Permissions and consent in the Microsoft identity platform endpoint</span></span>](/azure/active-directory/develop/v2-permissions-and-consent)
- [<span data-ttu-id="a3546-162">Teams의 리소스별 동의</span><span class="sxs-lookup"><span data-stu-id="a3546-162">Resource-specific consent in Teams</span></span>](resource-specific-consent.md)
- [<span data-ttu-id="a3546-163">RSC(리소스별 동의)</span><span class="sxs-lookup"><span data-stu-id="a3546-163">Resource-specific consent (RSC)</span></span>](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- <span data-ttu-id="a3546-164">[Teams 앱](https://aka.ms/PR132) 수명 주기(Ignite 2020 세션)</span><span class="sxs-lookup"><span data-stu-id="a3546-164">[Navigating the Teams app lifecycle](https://aka.ms/PR132) (Ignite 2020 session)</span></span>