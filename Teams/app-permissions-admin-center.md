---
title: Microsoft 팀 관리 센터에서 앱 사용 권한 보기 및 관리자 동의 허용
author: LanaChin
ms.author: v-lanac
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 앱에서 요청 하는 사용 권한을 확인 하 고 Microsoft 팀 관리 센터의 앱 관리 페이지에서 앱에 관리자 동의를 부여 하는 방법에 대해 알아봅니다.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a1c9f63c54711c5721ced661dc28d704c0b605c7
ms.sourcegitcommit: f4f5ad1391b472d64390180c81c2680f011a8a10
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2020
ms.locfileid: "48367598"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="907e8-103">Microsoft 팀 관리 센터에서 앱 사용 권한 보기 및 관리자 동의 허용</span><span class="sxs-lookup"><span data-stu-id="907e8-103">View app permissions and grant admin consent in the Microsoft Teams admin center</span></span>

<span data-ttu-id="907e8-104">Microsoft 팀 관리 센터의 [앱 관리](manage-apps.md) 페이지에서 조직의 모든 팀 앱을 보고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-104">The [Manage apps](manage-apps.md) page in the Microsoft Teams admin center is where you view and manage all Teams apps for your organization.</span></span> <span data-ttu-id="907e8-105">예를 들어 앱의 조직 수준 상태 및 속성을 확인 하 고, 조직의 앱 스토어에 새 사용자 지정 앱을 승인 또는 업로드 하 고, 조직 수준의 앱을 차단 하거나 허용 하 고, 조직 전체 앱 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-105">For example, you can see the org-level status and properties of apps, approve or upload new custom apps to your organization's app store, block or allow apps at the org level, and manage org-wide app settings.</span></span>

<span data-ttu-id="907e8-106">여기서는 데이터에 액세스 하 고 앱에 대 한 RSC (리소스 관련 승인) 권한을 볼 수 있는 권한을 요청 하는 앱에 조직 전체 관리자 동의를 부여할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-106">Here, you can also grant org-wide admin consent to apps that request permissions to access data and view resource-specific consent (RSC) permissions for apps.</span></span>

## <a name="grant-org-wide-admin-consent-to-an-app"></a><span data-ttu-id="907e8-107">앱에 조직 전체 관리자 동의 허용</span><span class="sxs-lookup"><span data-stu-id="907e8-107">Grant org-wide admin consent to an app</span></span>

<span data-ttu-id="907e8-108">전역 관리자 인 경우 조직의 모든 사용자를 대신 하 여 권한을 요청 하는 앱에 대 한 동의를 검토 하 고 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-108">If you're a global admin, you can review and grant consent to apps that request permissions on behalf of all users in your organization.</span></span> <span data-ttu-id="907e8-109">이렇게 하면 사용자가 앱을 시작할 때 앱에서 요청 하는 사용 권한을 검토 하 고 수락할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-109">You do this so that users don't have to review and accept the permissions requested by the app when they start the app.</span></span> <span data-ttu-id="907e8-110">또한 azure AD (Active Directory)의 사용자 [동의 설정](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) 에 따라 일부 사용자는 회사 데이터에 액세스 하는 앱에 동의를 허용 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-110">Additionally, depending on the user's [consent settings](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) in Azure Active Directory (Azure AD), some users may not be allowed to grant consent to apps that access company data.</span></span>

<span data-ttu-id="907e8-111">앱에서 요청 하는 권한에는 팀에 저장 된 정보를 읽고, 사용자 프로필을 읽고, 사용자를 대신 하 여 전자 메일을 보낼 수 있는 권한이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-111">Examples of permissions requested by apps include the ability to read information stored in a team, read a user's profile, and send an email on behalf of users.</span></span> <span data-ttu-id="907e8-112">자세한 내용은 [Microsoft id 플랫폼 끝점의 사용 권한 및 동의](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="907e8-112">To learn more, see [Permissions and consent in the Microsoft identity platform endpoint](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent).</span></span> 

<span data-ttu-id="907e8-113">**사용 권한** 열은 앱에 동의가 필요한 권한이 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-113">The **Permissions** column indicates whether an app has permissions that need consent.</span></span> <span data-ttu-id="907e8-114">동의를 필요로 하는 권한이 있는 Azure AD에 등록 된 각 앱에 대 한 **세부 정보 보기** 링크가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-114">You'll see a **View details** link for each app registered in Azure AD that has permissions that need consent.</span></span> <span data-ttu-id="907e8-115">이는 사용자 지정 및 타사 앱에만 적용 됨을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-115">Keep in mind that this applies only to custom and third-party apps.</span></span> <span data-ttu-id="907e8-116">Microsoft에서 게시 한 앱에 대해이 링크가 표시 되지 않거나 관리자 동의를 부여 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-116">You won't see this link or need to grant admin consent for apps published by Microsoft.</span></span>

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="앱 관리 페이지의 사용 권한 열 스크린샷":::

<span data-ttu-id="907e8-118">앱에 조직 전체 동의를 부여 하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-118">To grant org-wide consent to an app, follow these steps:</span></span>

1. <span data-ttu-id="907e8-119">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**으로  >  **앱 관리**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-119">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="907e8-120">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-120">Do one of the following:</span></span>
    - <span data-ttu-id="907e8-121">원하는 앱을 검색 하 고 앱 이름을 클릭 하 여 앱 세부 정보 페이지로 이동한 다음 **사용 권한** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-121">Search for the app you want, click the app name to go to the app details page, and then select the **Permissions** tab.</span></span>
    - <span data-ttu-id="907e8-122">**사용 권한** 열을 내림차순으로 정렬 하 여 앱을 찾은 다음 **세부 정보 보기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-122">Sort the **Permissions** column in descending order to find the app, and then select **View details**.</span></span> <span data-ttu-id="907e8-123">이 작업을 수행 하면 앱 세부 정보 페이지의 **사용 권한** 탭으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-123">Doing this takes you to the **Permissions** tab of the app details page.</span></span>

3. <span data-ttu-id="907e8-124">**조직 전체 사용 권한**아래에서 **사용 권한 검토 및 동의**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-124">Under **Org-wide permissions**, select **Review permissions and consent**.</span></span>

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="앱에 대 한 사용 권한 탭의 조직 전체 사용 권한 스크린샷":::

    <span data-ttu-id="907e8-126">이 작업을 수행 하려면 전역 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-126">You must be a global admin to do this.</span></span> <span data-ttu-id="907e8-127">이 옵션은 팀 서비스 관리자가 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-127">This option isn't available to Teams service admins.</span></span>

4. <span data-ttu-id="907e8-128">**사용 권한** 탭에서 앱에 요청 된 사용 권한을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-128">On the **Permissions** tab, review the permissions requested by the app.</span></span>

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="앱에서 요청 하는 사용 권한의 스크린샷":::

    > [!IMPORTANT]
    > <span data-ttu-id="907e8-130">앱에 조직 전체 승인을 부여 하면 앱에서 조직의 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-130">Granting org-wide consent to an app allows the app to access your organization's data.</span></span> <span data-ttu-id="907e8-131">동의를 부여 하기 전에 앱에서 요청한 권한을 신중 하 게 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-131">Carefully review the permissions requested by the app before you grant consent.</span></span>
5. <span data-ttu-id="907e8-132">앱에서 요청 하는 사용 권한에 동의 하는 경우 **수락** 을 클릭 하 여 동의를 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-132">If you agree with the permissions requested by the app, click **Accept** to grant consent.</span></span> <span data-ttu-id="907e8-133">앱에 대해 요청 된 사용 권한이 부여 되었음을 알 수 있도록 페이지 맨 위에 잠시 배너가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-133">A banner temporarily appears at the top of the page to let you know that the requested permissions have been granted for the app.</span></span> <span data-ttu-id="907e8-134">이제 앱이 조직의 모든 사용자에 대해 지정 된 리소스에 액세스할 수 있으며 그 외에는 사용 권한을 검토 하 라는 메시지가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-134">The app now has access to the specified resources for all users in your organization and no one else will be prompted to review the permissions.</span></span>

<span data-ttu-id="907e8-135">사용 권한을 수락 하면 앱 세부 정보 페이지에 대 한 **조직 전체 사용 권한** 아래에 메시지가 표시 되어 동의가 승인 되었음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-135">After you accept the permissions, you'll see a message under **Org-wide permissions** on the app details page to let you know that consent was granted.</span></span> <span data-ttu-id="907e8-136">앱의 사용 권한에 대 한 세부 정보를 보려면 azure AD 포털에서 앱의 페이지로 이동 하려면 **Azure Active Directory** 링크를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-136">To view details about the app's permissions, click the **Azure Active Directory** link to go to the app's page in the Azure AD portal.</span></span>

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="동의를 허용 했을 때 표시 되는 메시지 스크린샷":::

<span data-ttu-id="907e8-138">조직의 사용자에 게 동의를 허용 하 고 특정 앱에 대 한 동의를 부여한 사용자가 한 명 이상에 게 부여 되는 경우,이를 알리는 메시지가 표시 되며 Azure AD portal에서 앱의 페이지에 대 한 Azure Active Directory 링크가 승인 되었음을 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-138">If users in your organization are allowed to grant consent and if one or more users granted consent to a particular app, you'll also see the same message to let you know that consent was granted and the Azure Active Directory link to the app's page in the Azure AD portal.</span></span>

> [!NOTE]
> <span data-ttu-id="907e8-139">그러나, **사용 권한 및 승인** 옵션은 팀 서비스 관리자가 사용할 수 없으며, 앱에 대 한 조직 전체 관리자 동의를 부여할 수는 없습니다. 팀 서비스 관리자는 앱에 대 한 **사용 권한** 탭의 콘텐츠를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-139">Although, the **Review permissions and consent** option isn't available to Teams service admins and they can't grant org-wide admin consent to apps, Teams service admins can view the content on the **Permissions** tab for an app.</span></span> <span data-ttu-id="907e8-140">예를 들어 팀 서비스 관리자는 azure AD 포털에서 앱 사용 권한 세부 정보를 볼 수 있는 **Azure Active Directory** 링크를 클릭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-140">For example, a Teams service admin can click the **Azure Active Directory** link to view app permissions details in the Azure AD portal.</span></span> 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a><span data-ttu-id="907e8-141">앱에 대 한 리소스 관련 승인 사용 권한 보기</span><span class="sxs-lookup"><span data-stu-id="907e8-141">View resource-specific consent permissions of an app</span></span>

<span data-ttu-id="907e8-142">RSC 권한을 통해 팀 소유자는 팀 데이터에 액세스 하 고 수정할 수 있는 앱에 대 한 동의를 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-142">RSC permissions let team owners grant consent for an app to access and modify a team's data.</span></span> <span data-ttu-id="907e8-143">RSC 권한은 앱이 특정 팀에서 수행할 수 있는 작업을 정의 하는 세부적인 팀 관련 권한입니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-143">RSC permissions are granular, Teams-specific permissions that define what an app can do in a specific team.</span></span> <span data-ttu-id="907e8-144">RSC 권한의 예로는 채널을 만들고 삭제 하 고, 팀에 대 한 설정을 가져오고, 채널 탭을 만들고 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-144">Examples of RSC permissions include the ability to create and delete channels, get the settings for a team, and create and remove channel tabs.</span></span> 

<span data-ttu-id="907e8-145">RSC 권한은 Azure AD가 아니라 앱 매니페스트에서 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-145">RSC permissions are defined in the app manifest and not in Azure AD.</span></span> <span data-ttu-id="907e8-146">앱을 팀에 추가할 때 RSC 권한에 대 한 동의를 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-146">You grant consent to RSC permissions when you add the app to a team.</span></span> <span data-ttu-id="907e8-147">자세한 내용은 [RSC (리소스 관련 승인)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="907e8-147">To learn more, see [Resource-specific consent (RSC)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent).</span></span>

<span data-ttu-id="907e8-148">전역 관리자 및 팀 서비스 관리자는 앱 세부 정보 페이지의 **사용 권한** 탭에서 앱에 대 한 RSC 권한을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-148">Global admins and Teams service admin can view RSC permissions for an app on the **Permissions** tab of the app details page.</span></span> 

<span data-ttu-id="907e8-149">앱에 대 한 RSC 권한을 보려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-149">To view RSC permissions for an app, follow these steps:</span></span>

1. <span data-ttu-id="907e8-150">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **팀 앱**으로  >  **앱 관리**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-150">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="907e8-151">원하는 앱을 검색 하 고 앱 이름을 클릭 하 여 앱 세부 정보 페이지로 이동한 다음 **사용 권한** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-151">Search for the app you want, click the app name to go to the app details page, and then select the **Permissions** tab.</span></span>
3. <span data-ttu-id="907e8-152">**Microsoft Graph (리소스 관련 승인) 사용 권한**아래에서 앱에 의해 요청 된 rsc 권한을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-152">Under **Microsoft Graph resource-specific consent (RSC) permissions**, review the RSC permissions requested by the app.</span></span>

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="앱에 대 한 RSC 권한 스크린샷":::

## <a name="known-issues"></a><span data-ttu-id="907e8-154">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="907e8-154">Known issues</span></span>

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a><span data-ttu-id="907e8-155">"자세히 보기" 링크가 사용 권한을 요청 하는 일부 타사 앱에 대 한 사용 권한 열에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-155">The "View details" link isn't displayed in the Permissions column for some third-party apps that request permissions</span></span>

<span data-ttu-id="907e8-156">현재 사용 권한을 요청 하는 Azure AD에 등록 된 모든 타사 앱에 대 한 권한 부여 및 동의 허용 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-156">Currently, the ability to review permissions and grant consent isn't available for all third-party apps registered in Azure AD that request permissions.</span></span> <span data-ttu-id="907e8-157">**세부 정보 보기** 링크 대신 **--** **사용 권한** 열에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-157">Instead of the **View details** link, you'll see **--** in the **Permissions** column.</span></span> <span data-ttu-id="907e8-158">Isv와 협력 하 여 앱에 대해이 기능을 사용 하도록 설정 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="907e8-158">We're working with ISVs to enable this feature for their apps.</span></span>

## <a name="related-topics"></a><span data-ttu-id="907e8-159">관련 항목</span><span class="sxs-lookup"><span data-stu-id="907e8-159">Related topics</span></span>

- [<span data-ttu-id="907e8-160">Microsoft 팀 관리 센터에서 앱 관리</span><span class="sxs-lookup"><span data-stu-id="907e8-160">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="907e8-161">Microsoft id 플랫폼 끝점의 사용 권한 및 승인</span><span class="sxs-lookup"><span data-stu-id="907e8-161">Permissions and consent in the Microsoft identity platform endpoint</span></span>](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)
- [<span data-ttu-id="907e8-162">팀의 자원 관련 승인</span><span class="sxs-lookup"><span data-stu-id="907e8-162">Resource-specific consent in Teams</span></span>](resource-specific-consent.md)
- [<span data-ttu-id="907e8-163">RSC (리소스 관련 승인)</span><span class="sxs-lookup"><span data-stu-id="907e8-163">Resource-specific consent (RSC)</span></span>](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)


