---
title: 앱 사용 권한 보기 및 Microsoft Teams 관리 센터에서 관리자 동의
author: LanaChin
ms.author: v-lanac
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 앱에서 요청된 사용 권한을 보고 Microsoft Teams 관리 센터의 앱 관리 페이지에서 앱의 동의를 할당하는 방법을 알아보세요.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 737052ba5794b221caa08fa8ccfabec0d597c3ad
ms.sourcegitcommit: 34f407a6a40317056005e3bf38ce58f792c04810
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814617"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="7234c-103">앱 사용 권한 보기 및 Microsoft Teams 관리 센터에서 관리자 동의</span><span class="sxs-lookup"><span data-stu-id="7234c-103">View app permissions and grant admin consent in the Microsoft Teams admin center</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="7234c-104">Microsoft [Teams 관리 센터의](manage-apps.md) 앱 관리 페이지는 조직의 모든 Teams 앱을 보고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7234c-104">The [Manage apps](manage-apps.md) page in the Microsoft Teams admin center is where you view and manage all Teams apps for your organization.</span></span> <span data-ttu-id="7234c-105">예를 들어 앱의 조직 수준 상태 및 속성을 보고, 조직의 앱 스토어에 새 사용자 지정 앱을 승인 또는 업로드하고, 조직 수준에서 앱을 차단하거나 허용하고, 조직 전체 앱 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7234c-105">For example, you can see the org-level status and properties of apps, approve or upload new custom apps to your organization's app store, block or allow apps at the org level, and manage org-wide app settings.</span></span>

<span data-ttu-id="7234c-106">여기에서는 데이터에 액세스하고 앱에 대한 RSC(리소스별 동의) 권한을 볼 수 있는 앱에 대한 관리자 동의를 부여할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7234c-106">Here, you can also grant org-wide admin consent to apps that request permissions to access data and view resource-specific consent (RSC) permissions for apps.</span></span>

## <a name="grant-org-wide-admin-consent-to-an-app"></a><span data-ttu-id="7234c-107">조직 전체 관리 동의를 앱에 부여</span><span class="sxs-lookup"><span data-stu-id="7234c-107">Grant org-wide admin consent to an app</span></span>

<span data-ttu-id="7234c-108">관리자는 조직의 모든 사용자를 대신하여 권한을 요청하는 앱에 대한 동의를 검토하고 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7234c-108">As an admin, you can review and grant consent to apps that request permissions on behalf of all users in your organization.</span></span> <span data-ttu-id="7234c-109">이렇게 하면 다른 사용자가 앱을 시작할 때 앱에서 요청한 권한을 검토하고 수락할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7234c-109">You do this so that users don't have to review and accept the permissions requested by the app when they start the app.</span></span> <span data-ttu-id="7234c-110">또한 일부 사용자는 Azure [consent settings](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) AD(Azure Active Directory)의 사용자 동의 설정에 따라 일부 사용자는 회사 데이터에 액세스하는 앱에 동의하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7234c-110">Additionally, depending on the user's [consent settings](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) in Azure Active Directory (Azure AD), some users may not be allowed to grant consent to apps that access company data.</span></span>

<span data-ttu-id="7234c-111">앱에서 요청하는 사용 권한의 예로는 팀에 저장된 정보를 읽고, 사용자의 프로필을 읽고, 사용자를 대신하여 전자 메일을 보내는 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7234c-111">Examples of permissions requested by apps include the ability to read information stored in a team, read a user's profile, and send an email on behalf of users.</span></span> <span data-ttu-id="7234c-112">자세한 내용은 [Microsoft ID 플랫폼 끝점에서 사용 권한 및 동의를 참조하세요.](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)</span><span class="sxs-lookup"><span data-stu-id="7234c-112">To learn more, see [Permissions and consent in the Microsoft identity platform endpoint](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent).</span></span> 

<span data-ttu-id="7234c-113">조직 전체의 동의를 부여하려면 전역 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7234c-113">You have to be a global admin to grant org-wide consent to an app.</span></span> <span data-ttu-id="7234c-114">사용 **권한 열은** 앱에 동의하는 사용 권한이 있는지 여부를 나타내는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="7234c-114">The **Permissions** column indicates whether an app has permissions that need consent.</span></span> <span data-ttu-id="7234c-115">Azure AD에 **의해 동의가** 필요한 사용 권한이 있는 Azure AD에 등록된 각 앱에 대한 세부 정보 보기 링크가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7234c-115">You'll see a **View details** link for each app registered in Azure AD that has permissions that need consent.</span></span> <span data-ttu-id="7234c-116">이러한 변경은 사용자 지정 및 타사 앱에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7234c-116">Keep in mind that this applies only to custom and third-party apps and.</span></span> <span data-ttu-id="7234c-117">이 링크가 표시되지 않거나 Microsoft에서 게시한 앱에 대해 관리자 동의를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7234c-117">You won't see this link or need to grant admin consent for apps published by Microsoft.</span></span>

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="앱 관리 페이지의 사용 권한 열 스크린샷":::

<span data-ttu-id="7234c-119">앱에 대비하여 전체 동의를 부여하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="7234c-119">To grant org-wide consent to an app, follow these steps:</span></span>

1. <span data-ttu-id="7234c-120">Microsoft Teams 관리 센터의 왼쪽 탐색에서 Teams 앱 관리 **앱으로**  >  **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="7234c-120">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="7234c-121">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7234c-121">Do one of the following:</span></span>
    - <span data-ttu-id="7234c-122">원하는 앱을 검색하고 앱 이름을 클릭하여 앱 세부 정보 페이지로 이동한 다음 사용 권한 **탭을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7234c-122">Search for the app you want, click the app name to go to the app details page, and then select the **Permissions** tab.</span></span>
    - <span data-ttu-id="7234c-123">사용 권한 **열을** 내림차순으로 정렬하여 앱을 찾은 다음 세부 정보 **보기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7234c-123">Sort the **Permissions** column in descending order to find the app, and then select **View details**.</span></span> <span data-ttu-id="7234c-124">이렇게 하면 앱 세부 정보 **페이지의 사용** 권한 탭으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7234c-124">Doing this takes you to the **Permissions** tab of the app details page.</span></span>

3. <span data-ttu-id="7234c-125">구성 **전체 사용 권한에서 권한** **검토와 동의를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7234c-125">Under **Org-wide permissions**, select **Review permissions and consent**.</span></span> <span data-ttu-id="7234c-126">이 작업을 수행하려면 전역 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7234c-126">You must be a global admin to do this.</span></span> <span data-ttu-id="7234c-127">이 옵션은 Teams 서비스 관리자에게는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7234c-127">This option isn't available to Teams service admins.</span></span>

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="앱에 대한 사용 권한 탭에 대한 전체 사용 권한 스크린샷":::

4. <span data-ttu-id="7234c-129">사용 **권한 탭에서** 앱에서 요청한 사용 권한을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="7234c-129">On the **Permissions** tab, review the permissions requested by the app.</span></span>

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="앱에서 요청한 사용 권한 스크린샷":::

    > [!IMPORTANT]
    > <span data-ttu-id="7234c-131">앱에 조직 전체 동의를 부여하면 앱에서 조직 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7234c-131">Granting org-wide consent to an app allows the app to access your organization's data.</span></span> <span data-ttu-id="7234c-132">동의를 부여하기 전에 앱에서 요청한 사용 권한을 신중히 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="7234c-132">Carefully review the permissions requested by the app before you grant consent.</span></span>
5. <span data-ttu-id="7234c-133">앱에서 요청한 사용 권한에 동의하는 경우 **동의를** 클릭하여 동의를 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="7234c-133">If you agree with the permissions requested by the app, click **Accept** to grant consent.</span></span> <span data-ttu-id="7234c-134">페이지 맨 위에 일시적으로 배너가 표시되어 앱에 대해 요청된 사용 권한이 부여된 사이를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7234c-134">A banner temporarily appears at the top of the page to let you know that the requested permissions have been granted for the app.</span></span> <span data-ttu-id="7234c-135">이제 앱이 조직의 모든 사용자에 대해 지정된 리소스에 액세스할 수 있고 사용 권한을 검토하라는 메시지가 다른 사람도 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7234c-135">The app now has access to the specified resources for all users in your organization and no one else will be prompted to review the permissions.</span></span>

<span data-ttu-id="7234c-136">사용 권한을 수락하면 앱 세부 정보 페이지에 있는 **조직** 전체 의료 사용 권한 아래에 동의해야 한다는 내용이 사용자에게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7234c-136">After you accept the permissions, you'll see a message under **Org-wide permissions** on the app details page to let you know that consent was granted.</span></span> <span data-ttu-id="7234c-137">앱의 사용 권한에 대한 세부 정보를 보려면 **Azure Active Directory** 링크를 클릭하여 Azure AD 포털의 앱 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7234c-137">To view details about the app's permissions, click the **Azure Active Directory** link to go to the app's page in the Azure AD portal.</span></span>

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="동의가 전송된 경우 표시되는 메시지 스크린샷":::

<span data-ttu-id="7234c-139">조직의 사용자가 동의를 부여할 수 있으며 한 명 이상의 사용자가 특정 앱에 동의할 수 있는 경우 동의가 허용되었고 Azure Active Directory 링크만 있음을 알리는 메시지만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7234c-139">If users in your organization are allowed to grant consent and if one or more users granted consent to a particular app, you'll only see the message to let you know that consent was granted and the Azure Active Directory link.</span></span> 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a><span data-ttu-id="7234c-140">앱에 대한 리소스별 동의 사용 권한 보기</span><span class="sxs-lookup"><span data-stu-id="7234c-140">View resource-specific consent permissions of an app</span></span>

<span data-ttu-id="7234c-141">RSC 권한을 부여하면 팀 소유자가 앱에 대한 동의를 부여하여 팀의 데이터에 액세스하고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7234c-141">RSC permissions let team owners grant consent for an app to access and modify a team's data.</span></span> <span data-ttu-id="7234c-142">RSC 사용 권한은 특정 팀에서 수행할 수 있는 작업을 정의하는 Teams 전용 권한의 일반적인 사용 권한입니다.</span><span class="sxs-lookup"><span data-stu-id="7234c-142">RSC permissions are granular, Teams-specific permissions that define what an app can do in a specific team.</span></span> <span data-ttu-id="7234c-143">RSC 사용 권한의 예로는 채널을 만들고 삭제하고, 팀의 설정을 가져올 수 있는 권한을 가져올 수 있는 권한을 비동기, 채널 탭을 만들고 제거하는 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7234c-143">Examples of RSC permissions include the ability to create and delete channels, get the settings for a team, and create and remove channel tabs.</span></span> <span data-ttu-id="7234c-144">RSC 권한은 Azure AD에 있지 만며 앱 매니메이션에 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="7234c-144">RSC permissions are defined in the app manifest and not in Azure AD.</span></span>

<span data-ttu-id="7234c-145">팀에 앱을 추가하는 경우 RSC 사용 권한에 동의합니다.</span><span class="sxs-lookup"><span data-stu-id="7234c-145">You grant consent to RSC permissions when you add the app to a team.</span></span> <span data-ttu-id="7234c-146">자세한 내용은 [Teams에서 리소스 관련 동의(RSC) 및](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent) [리소스 관련 동의를 참조하세요.](resource-specific-consent.md)</span><span class="sxs-lookup"><span data-stu-id="7234c-146">To learn more, see [Resource-specific consent (RSC)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent) and [Resource-specific consent in Teams](resource-specific-consent.md).</span></span>

<span data-ttu-id="7234c-147">전역 관리자 및 Teams 서비스 관리자는 RSC 사용 권한을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7234c-147">Global admins and Teams service admin can view RSC permissions.</span></span> <span data-ttu-id="7234c-148">앱용 RSC 권한을 보려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="7234c-148">To view RSC permissions for an app, follow these steps:</span></span>

1. <span data-ttu-id="7234c-149">Microsoft Teams 관리 센터의 왼쪽 탐색에서 Teams 앱 관리 **앱으로**  >  **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="7234c-149">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="7234c-150">원하는 앱을 검색하고 앱 이름을 클릭하여 앱 세부 정보 페이지로 이동한 다음 사용 권한 **탭을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7234c-150">Search for the app you want, click the app name to go to the app details page, and then select the **Permissions** tab.</span></span>
3. <span data-ttu-id="7234c-151">**Microsoft Graph Resource(Conph Resource-specific consent) 권한에서**앱에서 요청한 RSC 권한을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="7234c-151">Under **Microsoft Graph resource-specific consent (RSC) permissions**, review the RSC permissions requested by the app.</span></span>

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="앱에 대한 RSC 사용 권한 스크린샷":::

## <a name="related-topics"></a><span data-ttu-id="7234c-153">관련 항목</span><span class="sxs-lookup"><span data-stu-id="7234c-153">Related topics</span></span>

- [<span data-ttu-id="7234c-154">Microsoft Teams 관리 센터에서 앱 관리</span><span class="sxs-lookup"><span data-stu-id="7234c-154">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="7234c-155">Microsoft ID 플랫폼 끝점의 사용 권한 및 동의</span><span class="sxs-lookup"><span data-stu-id="7234c-155">Permissions and consent in the Microsoft identity platform endpoint</span></span>](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)
- [<span data-ttu-id="7234c-156">Teams에서 리소스별 동의</span><span class="sxs-lookup"><span data-stu-id="7234c-156">Resource-specific consent in Teams</span></span>](resource-specific-consent.md)
- [<span data-ttu-id="7234c-157">RSC(Resource-specific 동의)</span><span class="sxs-lookup"><span data-stu-id="7234c-157">Resource-specific consent (RSC)</span></span>](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)


