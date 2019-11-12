---
title: Microsoft Teams에서 게스트 액세스 권한 부여
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- SPO_Content
ms.reviewer: sbhatta
localization_priority: Priority
search.appverid: MET150
description: 네 가지 수준의 권한 부여를 통해 Microsoft Teams 게스트 액세스 기능을 관리합니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2340d684aecbe427ef5e7426dff4f1daefb92d71
ms.sourcegitcommit: ddb4eaf634476680494025a3aa1c91d15fb58413
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2019
ms.locfileid: "38231129"
---
<a name="authorize-guest-access-in-microsoft-teams"></a><span data-ttu-id="0afee-103">Microsoft Teams에서 게스트 액세스 권한 부여</span><span class="sxs-lookup"><span data-stu-id="0afee-103">Authorize guest access in Microsoft Teams</span></span>
===========================================

<span data-ttu-id="0afee-104">조직의 요구 사항을 충족시키기 위해, 네 가지 수준의 권한 부여를 통해 Microsoft Teams 게스트 액세스 기능을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-104">To satisfy your organization’s requirements, you can manage Microsoft Teams guest access features and capabilities through four different levels of authorization.</span></span> <span data-ttu-id="0afee-105">모든 권한 수준은 Office 365 테넌트에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-105">All the authorization levels apply to your Office 365 tenant.</span></span> <span data-ttu-id="0afee-106">각 권한 수준은 아래와 같이 게스트 경험을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-106">Each authorization level controls the guest experience as shown below:</span></span>

- <span data-ttu-id="0afee-107">**Azure Active Directory**: Microsoft Teams의 게스트 액세스는 Azure AD B2B (Business-to-Business) 플랫폼에 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-107">**Azure Active Directory**: Guest access in Microsoft Teams relies on the Azure AD business-to-business (B2B) platform.</span></span> <span data-ttu-id="0afee-108">이 권한 수준은 디렉터리, 테넌트 및 응용 프로그램 수준에서의 게스트 경험을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-108">This authorization level controls the guest experience at the directory, tenant, and application level.</span></span>
- <span data-ttu-id="0afee-109">**Microsoft Teams**: Microsoft Teams의 게스트 경험만 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-109">**Microsoft Teams**: Controls the guest experience in Microsoft Teams only.</span></span>
- <span data-ttu-id="0afee-110">**Office 365 그룹**: Office 365 그룹 및 Microsoft Teams에서 게스트 환경을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-110">**Office 365 Groups**: Controls the guest experience in Office 365 Groups and Microsoft Teams.</span></span>
- <span data-ttu-id="0afee-111">**SharePoint Online 및 비즈니스용 OneDrive**: SharePoint Online, 비즈니스용 OneDrive, Office 365 그룹 및 Microsoft Teams에서 게스트 환경을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-111">**SharePoint Online and OneDrive for Business**: Controls the guest experience in SharePoint Online, OneDrive for Business, Office 365 Groups, and Microsoft Teams.</span></span>

<span data-ttu-id="0afee-112">이러한 서로 다른 권한 수준은 조직에 게스트 액세스를 설정하는 방법에 유연성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-112">These different authorization levels provide you with flexibility in how you set up guest access for your organization.</span></span> <span data-ttu-id="0afee-113">예를 들어 Microsoft Teams에서 게스트 사용자를 허용하지 않고 조직 전체에서 게스트 사용자를 허용하려면 Microsoft Teams에서 게스트 액세스를 해제하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-113">For example, if you don’t want to allow guest users in your Microsoft Teams but want to allow it overall in your organization, just turn off guest access in Microsoft Teams.</span></span> <span data-ttu-id="0afee-114">또 다른 예: Azure AD, Teams, 그룹 수준에서 게스트 액세스를 사용하도록 설정할 수 있지만, 선택한 팀에서 데이터 분류와 같은 하나 이상의 조건과 일치하는 게스트 사용자를 추가하는 기능을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-114">Another example: You could enable guest access at the Azure AD, Teams, and Groups levels, but then disable the addition of guest users on selected teams that match one or more criteria such as data classification equals confidential.</span></span> <span data-ttu-id="0afee-115">SharePoint Online 및 비즈니스용 OneDrive에는 Office 365 그룹에 의존하지 않는 자체 게스트 액세스 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-115">SharePoint Online and OneDrive for Business have their own guest access settings that don't rely on Office 365 Groups.</span></span>

> [!NOTE]
> <span data-ttu-id="0afee-116">게스트는 [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) 및 [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) 서비스 제한에 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-116">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span> 

<span data-ttu-id="0afee-117">다음 다이어그램은 게스트 액세스 권한 종속성이 Azure Active Directory, Microsoft Teams 및 Office 365간에 부여되고 통합되는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-117">The following diagram shows how guest access authorization dependency is granted and integrated between Azure Active Directory, Microsoft Teams, and Office 365.</span></span>

![게스트 액세스에 대한 권한 종속성 다이어그램.](media/teams_dependencies_image1.png)

<span data-ttu-id="0afee-119">다음 다이어그램은 일반적인 게스트 액세스 초대 및 상환 흐름을 통해 사용자 경험이 권한 모델을 사용하는 방법을 개략적으로 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-119">The next diagram shows, at a high level, how the user experience works with the permission model through a typical guest access invitation and redemption flow.</span></span>

![초대 및 상환 흐름 다이어그램](media/authorize-guest-image1.png)

<span data-ttu-id="0afee-121">여기에서 앱, 봇 및 커넥터는 사용자 계정에 고유한 권한 및 / 또는 동의가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-121">It’s important to note here that apps, bots, and connectors might require their own set of permissions and/or consent specific to the user account.</span></span> <span data-ttu-id="0afee-122">이들은 별도로 부여해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-122">These might need to be granted separately.</span></span> <span data-ttu-id="0afee-123">마찬가지로 SharePoint는 특정 사용자, 사용자 그룹 또는 사이트 수준에 대해 추가 외부 공유 경계를 부과할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-123">Similarly, SharePoint might impose extra external sharing boundaries for a specific user, groups of users, or even at the site level.</span></span>

<span data-ttu-id="0afee-124">앞의 두 다이어그램은 [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true)에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-124">The previous two diagrams are also available in [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true).</span></span>

## <a name="control-guest-access-in-azure-active-directory"></a><span data-ttu-id="0afee-125">Azure Active Directory에서 게스트 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="0afee-125">Control guest access in Azure Active Directory</span></span>

<span data-ttu-id="0afee-126">Azure AD를 사용하여 외부 협력자를 게스트로 초대할지와 초대 방식을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-126">Use Azure AD to determine whether external collaborators can be invited into your tenant as guests, and in what ways.</span></span> <span data-ttu-id="0afee-127">Azure B2B 게스트 액세스에 대한 자세한 내용은 [Azure Active Directory B2B의 게스트 사용자 액세스란](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0afee-127">For more information about Azure B2B guest access, see [What is guest user access in Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b).</span></span> <span data-ttu-id="0afee-128">Azure AD 역할에 대한 자세한 내용은 [Azure Active Directory 테넌트에서 파트너 조직의 사용자에게 권한 부여](https://docs.microsoft.com/azure/active-directory/b2b/add-guest-to-role)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0afee-128">For information about Azure AD roles, see [Grant permissions to users from partner organizations in your Azure Active Directory tenant](https://docs.microsoft.com/azure/active-directory/b2b/add-guest-to-role).</span></span>

<span data-ttu-id="0afee-129">초대 설정은 테넌트 수준에서 적용되고 디렉터리, 테넌트 및 응용 프로그램 수준에서 게스트 환경을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-129">The settings for invitations apply at the tenant level and control the guest experience at the directory, tenant, and application level.</span></span> <span data-ttu-id="0afee-130">Azure Portal에서 이러한 설정을 구성하려면 **Azure Active Directory** > **사용자** > **사용자 설정**으로 이동하고, **외부 사용자**에서 **외부 공동 작업 설정 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-130">To configure these settings in the Azure portal, go to **Azure Active Directory** > **Users** > **User settings**, and under **External users**, select **Manage external collaboration settings**.</span></span>

<span data-ttu-id="0afee-131">Azure AD에는 외부 사용자를 구성하기위한 다음 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-131">Azure AD includes the following settings to configure external users:</span></span>

- <span data-ttu-id="0afee-132">**게스트 사용자 권한이 제한됨**: **예**는 게스트, 그룹 또는 기타 디렉토리 리소스 열거와 같은 특정 디렉토리 작업에 대한 권한이 게스트에게 없음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-132">**Guest user permissions are limited**: **Yes** means that guests don't have permission for certain directory tasks, such as enumerate users, groups, or other directory resources.</span></span> <span data-ttu-id="0afee-133">또한 게스트를 디렉토리의 관리 역할에 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-133">In addition, guests can't be assigned to administrative roles in your directory.</span></span> <span data-ttu-id="0afee-134">**아니요**는 게스트가 일반 사용자의 디렉토리에 있는 디렉토리 데이터에 동일한 액세스 권한을 갖음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-134">**No** means that guests have the same access to directory data that regular users have in your directory.</span></span>
- <span data-ttu-id="0afee-135">**게스트 초대자 역할의 관리자 및 사용자 초대 가능**: **예**는 게스트 초대자 역할의 관리자 및 사용자가 게스트를 테넌트로 초대할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-135">**Admins and users in the guest inviter role can invite**: **Yes** means that admins and users in the guest inviter role will be able to invite guests to the tenant.</span></span> <span data-ttu-id="0afee-136">**아니요**는 관리자와 사용자가 테넌트에 게스트를 초대할 수 없음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-136">**No** means admins and users can't invite guests to the tenant.</span></span>
- <span data-ttu-id="0afee-137">**구성원 초대 가능**: **예**는 관리자가 아닌 디렉터리 구성원이 게스트를 초대하여 SharePoint 사이트 또는 Azure 리소스와 같은 Azure AD로 보안된 리소스에 대해 공동 작업을 수행할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-137">**Members can invite**: **Yes** means that non-admin members of your directory can invite guests to collaborate on resources secured by your Azure AD, such as SharePoint sites or Azure resources.</span></span> <span data-ttu-id="0afee-138">**아니요**는 관리자만 디렉터리에 게스트를 초대할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-138">**No** means that only admins can invite guests to your directory.</span></span></br>
      
    > [!IMPORTANT]
    > <span data-ttu-id="0afee-139">게스트 액세스가 Teams에서 작동하려면 **멤버가 초대할 수 있음**을 **예**로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-139">For guest access to work at all in Teams, you must set **Members can invite** to **Yes**.</span></span>
- <span data-ttu-id="0afee-140">**게스트 초대 가능**: **예**는 디렉터리의 게스트를 초대하여 SharePoint 사이트 또는 Azure 리소스와 같은 Azure AD로 보안된 리소스에 대해 공동 작업을 수행할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-140">**Guests can invite**: **Yes** means that guests in your directory can invite other guests to collaborate on resources secured by your Azure AD, such as SharePoint sites or Azure resources.</span></span> <span data-ttu-id="0afee-141">**아니요**는 게스트가 다른 게스트를 초대하여 조직과 공동 작업을 할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-141">**No** means that guests can't invite other guests to collaborate with your organization.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="0afee-142">현재 Teams는 게스트 초대자 역할을 지원하지 않으므로 **참석자를 초대 할 수 있음**으로 **설정**하더라도 손님은 Teams에서 다른 참석자를 초대할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-142">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
 
<span data-ttu-id="0afee-143">게스트를 초대할 수 있는 사용자를 제어하는 방법에 대한 자세한 내용은 [Azure Active Directory B2B 공동 작업에 대한 초대 위임](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-143">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

> [!NOTE]
> <span data-ttu-id="0afee-144">또한 테넌트에 게스트로 초대되는 도메인을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-144">You can also manage which domains can be invited into your tenant as guests.</span></span> <span data-ttu-id="0afee-145">[Office 365 그룹에 대한 게스트 액세스 허용/차단](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0afee-145">See [Allow/Block guest access to Office 365 Groups](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups).</span></span>

<span data-ttu-id="0afee-146">Teams에 게스트를 추가할 때 계정이 디렉터리에 자동으로 추가되므로 사용자 게스트 계정을 Azure AD B2B에 수동으로 추가할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-146">Adding the user guest account manually to Azure AD B2B is not required, as the account will be added to the directory automatically when you add the guest to Teams.</span></span>

### <a name="licensing-for-guest-access"></a><span data-ttu-id="0afee-147">게스트 액세스에 대한 라이선스</span><span class="sxs-lookup"><span data-stu-id="0afee-147">Licensing for guest access</span></span>
<span data-ttu-id="0afee-148">게스트 액세스 라이선스는 Azure AD 라이선스의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-148">Guest access licensing is part of Azure AD licensing.</span></span> <span data-ttu-id="0afee-149">모든 Office 365 Business Premium 및 Office 365 Enterprise 구독에는 게스트 액세스가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-149">Guest access is included with all OFfice 365 Business Premium and Office 365 Enterprise subscriptions.</span></span> <span data-ttu-id="0afee-150">라이선스에 대한 자세한 내용은 [Azure Active Directory B2B 공동 작업 라이선스 지침](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0afee-150">For more information about licensing, see [Azure Active Directory B2B collaboration licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>


> [!NOTE]
> <span data-ttu-id="0afee-151">Exchange Online Plan 2와 같이 독립실행형 Office 365 구독 계획만 가진 조직의 사용자는 Teams에서 동일한 조직에 속한 것으로 간주하기 때문에 조직에 게스트로 초대될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-151">Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="0afee-152">사용자가 Teams를 사용하려면 Office 365 Business Premium, Office 365 Enterprise 또는 Office 365 Education 구독에 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-152">For these users to use Teams, they must be assigned an Office 365 Business Premium, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="control-guest-access-in-teams"></a><span data-ttu-id="0afee-153">Teams에서 게스트 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="0afee-153">Control guest access in Teams</span></span>

<span data-ttu-id="0afee-154">Teams에서 게스트 액세스 기능은 기본적으로 꺼져있습니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-154">Guest access is turned off by default in Teams.</span></span> <span data-ttu-id="0afee-155">게스트 액세스를 켜려면 [Microsoft Teams에서 게스트 액세스 설정 또는 해제](set-up-guests.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0afee-155">To turn on guest access, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span> 


## <a name="control-guest-access-in-office-365-groups"></a><span data-ttu-id="0afee-156">Office 365 그룹에서 게스트 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="0afee-156">Control guest access in Office 365 Groups</span></span>

<span data-ttu-id="0afee-157">Office 365 그룹에서 조직의 모든 Office 365 그룹 및 Microsoft Teams 팀에 대한 게스트 사용자 및 게스트 액세스 추가를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-157">From Office 365 Groups, you can control adding guest users and guest access to all Office 365 Groups and Microsoft Teams teams in your organization.</span></span>

1. <span data-ttu-id="0afee-158">[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home)에서 Office 365 전역 관리자 계정으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-158">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>

2. <span data-ttu-id="0afee-159">왼쪽에서**설정**을 선택한 다음 **서비스 &amp; 추가 기능**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-159">On the left, choose **Settings** and then select **Services &amp; add-ins**.</span></span>

3. <span data-ttu-id="0afee-160">**Office 365 그룹**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-160">Select **Office 365 Groups**.</span></span>

     ![설정에서 Office 365 그룹의 스크린샷](media/authorize-guest-image2.png)
  
4. <span data-ttu-id="0afee-162">Office 365 그룹 페이지에서 조직 외부의 팀 및 그룹 소유자가 Office 365 그룹에 액세스 할 수 있도록 허용할지에 따라 전환을 **설정** 또는 **해제**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-162">On the Office 365 Groups page, set the toggle to **On** or **Off**, depending on whether you want to let team and group owners outside your organization access Office 365 Groups.</span></span> <span data-ttu-id="0afee-163">**그룹 소유자가 조직 외부의 사람들을 그룹에 추가하도록 허용** 옆의 토글을 **켬**으로 설정하거나 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-163">Click or tap the toggle to **On** next to **Let group owners add people outside the organization to groups**.</span></span> <span data-ttu-id="0afee-164">이 토글을 **켬**으로 설정하면 그룹 및 팀 소유자가 조직 외부의 사용자를 Office 365 그룹 및 Microsoft Teams에 추가할 수 있도록 할지 여부를 제어하는 다른 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-164">If you turn this toggle to **On**, you'll see another option to control whether you want to let group and team owners add people outside your organization to Office 365 Groups and Microsoft Teams.</span></span> <span data-ttu-id="0afee-165">그룹 및 팀 소유자에게 게스트 사용자를 추가할 수 있도록 허용하려면 이 토글을 **켬**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-165">Set this toggle to **On** if you want to let group and team owners add guest users.</span></span> 
 
   ![옵션이 설정된 Office 365 그룹 패널의 스크린 샷](media/authorize-guest-image3.png)

<span data-ttu-id="0afee-167">이러한 설정은 테넌트 수준에서 적용되며 Office 365 그룹 및 팀에서 게스트 환경을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-167">These settings apply at the tenant level and control the guest experience in Office 365 Groups and Teams.</span></span>

<span data-ttu-id="0afee-168">게스트 액세스 작동 방식, 게스트 액세스 관리 방법, 자주 묻는 질문에 대한 답변 등 그룹의 게스트 액세스에 대한 자세한 내용은 [Office 365 그룹의 게스트 액세스](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-168">See [Guest access in Office 365 Groups](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6) for more information about guest access in groups, including how guest access works, how to manage guest access, and answers to frequently asked questions.</span></span>

## <a name="control-guest-access-to-sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="0afee-169">SharePoint Online 및 비즈니스용 OneDrive에 대한 게스트 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="0afee-169">Control guest access to SharePoint Online and OneDrive for Business</span></span>

<span data-ttu-id="0afee-170">Teams는 SharePoint Online 및 비즈니스용 OneDrive를 사용하여 채널 및 채팅 대화를 위한 파일과 문서를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-170">Teams relies on SharePoint Online and OneDrive for Business to store files and documents for channels and chat conversations.</span></span>  

<span data-ttu-id="0afee-171">전체 Teams 게스트 액세스 환경을 위해서는 Office 365 관리자가 다음 설정을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-171">For the full Teams guest access experience, Office 365 admins need to configure the following settings:</span></span>

- <span data-ttu-id="0afee-172">SharePoint Online에서 **기존 게스트**, **신규 및 기존 게스트** 또는 모두를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-172">In SharePoint Online: Select **Existing guests**, **New and existing guests**, or **Anyone**.</span></span>

    <span data-ttu-id="0afee-173">자세한 내용은 [외부 공유 설정 또는 해제](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0afee-173">For more information, see [Turn external sharing on or off](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off).</span></span>

- <span data-ttu-id="0afee-174">Office 365 그룹에서 **그룹 소유자가 조직 외부의 사람을 그룹에 추가하도록 허용** 설정</span><span class="sxs-lookup"><span data-stu-id="0afee-174">In Office 365 Groups: Turn on **Let group owners add people outside the organization to groups**</span></span>

    <span data-ttu-id="0afee-175">자세한 내용은 위의 [Office 365 그룹에서 게스트 액세스 제어](#control-guest-access-in-office-365-groups)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0afee-175">For more information, see [Control guest access in Office 365 Groups](#control-guest-access-in-office-365-groups), above.</span></span>
  
<span data-ttu-id="0afee-176">이러한 설정은 테넌트 수준에서 적용되며 SharePoint Online, 비즈니스용 OneDrive, Office 365 그룹 및 Teams에서 게스트 환경을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-176">These settings apply at the tenant level and control the guest experience in SharePoint Online, OneDrive for Business, Office 365 Groups, and Teams.</span></span>

<span data-ttu-id="0afee-177">Teams에 연결된 팀 사이트의 SharePoint Online 외부 사용자 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0afee-177">You can manage SharePoint Online external user settings for the team sites connected to Teams.</span></span> <span data-ttu-id="0afee-178">자세한 내용은 [SharePoint 팀 사이트 설정 관리](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0afee-178">To learn more, see  [Manage your SharePoint team site settings](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span></span>

## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="0afee-179">외부 액세스 (페더레이션) 및 게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="0afee-179">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="related-topics"></a><span data-ttu-id="0afee-180">관련 항목</span><span class="sxs-lookup"><span data-stu-id="0afee-180">Related topics</span></span>

- [<span data-ttu-id="0afee-181">Microsoft 365 게스트 공유 설정 참조</span><span class="sxs-lookup"><span data-stu-id="0afee-181">Microsoft 365 guest sharing settings reference</span></span>](https://docs.microsoft.com/Office365/Enterprise/microsoft-365-guest-settings)
