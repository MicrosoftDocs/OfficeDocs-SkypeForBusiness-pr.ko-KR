---
title: Microsoft Teams에서 게스트 액세스 권한 부여
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- SPO_Content
ms.reviewer: rafarhi
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
description: 네 가지 수준의 권한 부여를 통해 Microsoft Teams 게스트 액세스 기능을 관리합니다.
ms.openlocfilehash: e74152bc61bdf0bb793338b50ddcd5da62e9b2d0
ms.sourcegitcommit: 43e5a4aac11c20dd5a4c35b59695f309e1559e82
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/03/2020
ms.locfileid: "48346189"
---
# <a name="authorize-guest-access-in-microsoft-teams"></a><span data-ttu-id="5e298-103">Microsoft Teams에서 게스트 액세스 권한 부여</span><span class="sxs-lookup"><span data-stu-id="5e298-103">Authorize guest access in Microsoft Teams</span></span>

<span data-ttu-id="5e298-104">조직의 요구 사항을 충족 하기 위해 네 가지 수준의 권한 부여를 통해 팀 게스트 액세스 기능 및 기능을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e298-104">To satisfy your organization's requirements, you can manage Teams guest access features and capabilities through four different levels of authorization.</span></span> <span data-ttu-id="5e298-105">모든 권한 수준은 Microsoft 365 조직에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e298-105">All the authorization levels apply to your Microsoft 365 organization.</span></span> <span data-ttu-id="5e298-106">각 권한 수준은 아래와 같이 게스트 경험을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="5e298-106">Each authorization level controls the guest experience as shown below:</span></span>

- <span data-ttu-id="5e298-107">**Azure Active Directory**: 팀의 게스트 액세스는 Azure AD BUSINESS (b2b) 플랫폼에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="5e298-107">**Azure Active Directory**: Guest access in Teams relies on the Azure AD business-to-business (B2B) platform.</span></span> <span data-ttu-id="5e298-108">이 권한 수준은 디렉터리, 테넌트 및 응용 프로그램 수준에서의 게스트 경험을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="5e298-108">This authorization level controls the guest experience at the directory, tenant, and application level.</span></span>
- <span data-ttu-id="5e298-109">**팀**: 팀 에서만 게스트 환경을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e298-109">**Teams**: Controls the guest experience in Teams only.</span></span>
- <span data-ttu-id="5e298-110">**Microsoft 365 그룹**: Microsoft 365 그룹 및 팀에서 게스트 환경을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e298-110">**Microsoft 365 Groups**: Controls the guest experience in Microsoft 365 Groups and Teams.</span></span>
- <span data-ttu-id="5e298-111">**Sharepoint 및 onedrive**: Sharepoint, Onedrive, Microsoft 365 그룹 및 팀에서 게스트 환경을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e298-111">**SharePoint and OneDrive**: Controls the guest experience in SharePoint, OneDrive, Microsoft 365 Groups, and Teams.</span></span>

<span data-ttu-id="5e298-112">이러한 서로 다른 권한 수준은 조직에 게스트 액세스를 설정하는 방법에 유연성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5e298-112">These different authorization levels provide you with flexibility in how you set up guest access for your organization.</span></span> <span data-ttu-id="5e298-113">예를 들어 팀에서 게스트 사용자를 허용 하 고 조직에서 전반적으로 허용 하려는 경우 팀에서 게스트 액세스를 해제 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e298-113">For example, if you don't want to allow guest users in Teams but want to allow it overall in your organization, just turn off guest access in Teams.</span></span> <span data-ttu-id="5e298-114">또 다른 예로는 Azure AD, 팀 및 그룹 수준에서 게스트 액세스를 사용 하도록 설정할 수 있지만, [선택 된 팀에서 데이터 분류와 같은 하나 이상의 조건과 일치 하는 게스트 사용자 추가를 사용 하지 않도록 설정 합니다](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="5e298-114">Another example: You could enable guest access at the Azure AD, Teams, and Groups levels, but then [disable the addition of guest users on selected teams that match one or more criteria such as data classification equals confidential](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span> <span data-ttu-id="5e298-115">SharePoint 및 OneDrive에는 Microsoft 365 그룹에 의존 하지 않는 고유한 게스트 액세스 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e298-115">SharePoint and OneDrive have their own guest access settings that don't rely on Microsoft 365 Groups.</span></span>

<span data-ttu-id="5e298-116">엔드 투 엔드 게스트 액세스 구성 지침은 [팀에서 게스트 공동 작업](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e298-116">For end-to-end guest access configuration instructions, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

> [!NOTE]
> <span data-ttu-id="5e298-117">게스트는 [Microsoft 365 및 Office 365 서비스 설명](https://go.microsoft.com/fwlink/p/?linkid=282347) 및 [Azure AD B2B 공동 작업의 제한 사항](https://docs.microsoft.com/azure/active-directory/external-identities/current-limitations)에서 설명하는 서비스 제한의 적용을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="5e298-117">Guests are subject to the service limits described in [Microsoft 365 and Office 365 service descriptions](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Limitations of Azure AD B2B collaboration](https://docs.microsoft.com/azure/active-directory/external-identities/current-limitations).</span></span> 

<span data-ttu-id="5e298-118">다음 다이어그램은 게스트 액세스 권한 부여 종속성이 Azure Active Directory, 팀 및 Microsoft 365 간에 부여 되 고 통합 되는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5e298-118">The following diagram shows how guest access authorization dependency is granted and integrated between Azure Active Directory, Teams, and Microsoft 365.</span></span>

![게스트 액세스에 대한 권한 종속성 다이어그램.](media/teams_dependencies_image1.png)

<span data-ttu-id="5e298-120">다음 다이어그램은 일반적인 게스트 액세스 초대 및 상환 흐름을 통해 사용자 경험이 권한 모델을 사용하는 방법을 개략적으로 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="5e298-120">The next diagram shows, at a high level, how the user experience works with the permission model through a typical guest access invitation and redemption flow.</span></span>

![초대 및 상환 흐름 다이어그램](media/authorize-guest-image1.png)

<span data-ttu-id="5e298-122">앱, 인공 지능 및 커넥터에는 고유한 사용 권한 집합 및/또는 사용자 계정에 대 한 동의가 필요 하다는 점에 유의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e298-122">It's important to note here that apps, bots, and connectors might require their own set of permissions and/or consent specific to the user account.</span></span> <span data-ttu-id="5e298-123">이들은 별도로 부여해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e298-123">These might need to be granted separately.</span></span> <span data-ttu-id="5e298-124">마찬가지로 SharePoint는 특정 사용자, 사용자 그룹 또는 사이트 수준에 대해 추가 외부 공유 경계를 부과할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e298-124">Similarly, SharePoint might impose extra external sharing boundaries for a specific user, groups of users, or even at the site level.</span></span>

<span data-ttu-id="5e298-125">앞의 두 다이어그램은 [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true)에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e298-125">The previous two diagrams are also available in [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true).</span></span>

## <a name="control-guest-access-in-azure-active-directory"></a><span data-ttu-id="5e298-126">Azure Active Directory에서 게스트 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="5e298-126">Control guest access in Azure Active Directory</span></span>

<span data-ttu-id="5e298-127">Azure AD를 사용하여 외부 협력자를 게스트로 초대할지와 초대 방식을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e298-127">Use Azure AD to determine whether external collaborators can be invited into your tenant as guests, and in what ways.</span></span> <span data-ttu-id="5e298-128">Azure B2B 게스트 액세스에 대한 자세한 내용은 [Azure Active Directory B2B의 게스트 사용자 액세스란](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5e298-128">For more information about Azure B2B guest access, see [What is guest user access in Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b).</span></span> <span data-ttu-id="5e298-129">Azure AD 역할에 대한 자세한 내용은 [Azure Active Directory 테넌트에서 파트너 조직의 사용자에게 권한 부여](https://docs.microsoft.com/azure/active-directory/b2b/add-guest-to-role)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5e298-129">For information about Azure AD roles, see [Grant permissions to users from partner organizations in your Azure Active Directory tenant](https://docs.microsoft.com/azure/active-directory/b2b/add-guest-to-role).</span></span>

<span data-ttu-id="5e298-130">초대에 대 한 설정은 조직 수준에서 적용 되며 디렉터리 및 응용 프로그램 수준에서 게스트 환경을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e298-130">The settings for invitations apply at the organization level and control the guest experience at the directory and application level.</span></span> <span data-ttu-id="5e298-131">[외부 공동 작업 설정](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/CompanyRelationshipsMenuBlade/Settings)에서 이러한 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e298-131">You can configure these settings in [External collaboration settings](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/CompanyRelationshipsMenuBlade/Settings).</span></span>

<span data-ttu-id="5e298-132">Azure AD에는 외부 사용자를 구성하기위한 다음 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e298-132">Azure AD includes the following settings to configure external users:</span></span>

- [<span data-ttu-id="5e298-133">게스트 사용자 액세스 제한</span><span class="sxs-lookup"><span data-stu-id="5e298-133">Guest user access restrictions</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-restrict-guest-permissions)

- <span data-ttu-id="5e298-134">**게스트 초대자 역할의 관리자 및 사용자 초대 가능**: **예**는 게스트 초대자 역할의 관리자 및 사용자가 게스트를 테넌트로 초대할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="5e298-134">**Admins and users in the guest inviter role can invite**: **Yes** means that admins and users in the guest inviter role will be able to invite guests to the tenant.</span></span> <span data-ttu-id="5e298-135">**아니요**는 관리자와 사용자가 테넌트에 게스트를 초대할 수 없음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="5e298-135">**No** means admins and users can't invite guests to the tenant.</span></span>
- <span data-ttu-id="5e298-136">**회원 초대 가능**: 디렉토리의 관리자가 아닌 회원이 손님을 초대할 수 있게 하려면 이 정책을 **예**(권장)로 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="5e298-136">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes** (recommended).</span></span> <span data-ttu-id="5e298-137">관리자만 게스트를 추가할 수 있게 하려는 경우 이 정책을 **아니오**로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e298-137">If you prefer that only admins be able to add guests, you can set this policy to **No**.</span></span> <span data-ttu-id="5e298-138">**아니오**로 설정할 경우 관리자가 아닌 Teams 소유자의 게스트 환경이 제한됨에 유의하십시오. 이 소유자들은 AAD에 이미 추가된 Teams에만 게스트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e298-138">Keep in mind that setting **No** will limit the guest experience for non-admin teams owners; they'll only be able to add guests in Teams that have already been added in AAD by the admin.</span></span>
- <span data-ttu-id="5e298-139">**게스트 초대 가능**: **예**는 디렉터리의 게스트를 초대하여 SharePoint 사이트 또는 Azure 리소스와 같은 Azure AD로 보안된 리소스에 대해 공동 작업을 수행할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="5e298-139">**Guests can invite**: **Yes** means that guests in your directory can invite other guests to collaborate on resources secured by your Azure AD, such as SharePoint sites or Azure resources.</span></span> <span data-ttu-id="5e298-140">**아니요**는 게스트가 다른 게스트를 초대하여 조직과 공동 작업을 할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5e298-140">**No** means that guests can't invite other guests to collaborate with your organization.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="5e298-141">현재 Teams는 게스트 초대자 역할을 지원하지 않으므로 **참석자를 초대 할 수 있음**으로 **설정**하더라도 손님은 Teams에서 다른 참석자를 초대할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5e298-141">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
 
<span data-ttu-id="5e298-142">게스트를 초대할 수 있는 사용자를 제어 하는 방법에 대 한 자세한 내용은 [B2B 외부 공동 작업 사용 및 게스트를 초대할 수 있는 사용자 관리](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)를 참조 하세요</span><span class="sxs-lookup"><span data-stu-id="5e298-142">For more information about controlling who can invite guests, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

> [!NOTE]
> <span data-ttu-id="5e298-143">또한 테넌트에 게스트로 초대되는 도메인을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e298-143">You can also manage which domains can be invited into your tenant as guests.</span></span> <span data-ttu-id="5e298-144">[특정 조직의 B2B 사용자에 대 한 초대 허용 또는 차단을](https://docs.microsoft.com/azure/active-directory/external-identities/allow-deny-list)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e298-144">See [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/external-identities/allow-deny-list).</span></span>

<span data-ttu-id="5e298-145">Teams에 게스트를 추가할 때 계정이 디렉터리에 자동으로 추가되므로 사용자 게스트 계정을 Azure AD B2B에 수동으로 추가할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5e298-145">Adding the user guest account manually to Azure AD B2B is not required, as the account will be added to the directory automatically when you add the guest to Teams.</span></span>

### <a name="licensing-for-guest-access"></a><span data-ttu-id="5e298-146">게스트 액세스에 대한 라이선스</span><span class="sxs-lookup"><span data-stu-id="5e298-146">Licensing for guest access</span></span>

<span data-ttu-id="5e298-147">게스트 액세스 라이선스는 Azure AD External Id 가격을 사용 하며 월간 활성 게스트를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e298-147">Guest access licensing uses Azure AD External Identities pricing and is based on monthly active guests.</span></span> <span data-ttu-id="5e298-148">자세한 내용은 [AZURE AD External id에 대 한 청구 모델을](https://docs.microsoft.com/azure/active-directory/external-identities/external-identities-pricing) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e298-148">See [Billing model for Azure AD External Identities](https://docs.microsoft.com/azure/active-directory/external-identities/external-identities-pricing) for details.</span></span>

> [!NOTE]
> <span data-ttu-id="5e298-149">Exchange Online Plan 2와 같이 독립실행형 Office 365 구독 계획만 가진 조직의 사용자는 Teams에서 동일한 조직에 속한 것으로 간주하기 때문에 조직에 게스트로 초대될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5e298-149">Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="5e298-150">사용자가 Teams를 사용하려면 Microsoft 365 Business Standard, Office 365 Enterprise 또는 Office 365 Education 구독에 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e298-150">For these users to use Teams, they must be assigned an Microsoft 365 Business Standard, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="5e298-151">외부 액세스 (페더레이션) 및 게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="5e298-151">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="related-topics"></a><span data-ttu-id="5e298-152">관련 항목</span><span class="sxs-lookup"><span data-stu-id="5e298-152">Related topics</span></span>

- [<span data-ttu-id="5e298-153">Microsoft 365 게스트 공유 설정 참조</span><span class="sxs-lookup"><span data-stu-id="5e298-153">Microsoft 365 guest sharing settings reference</span></span>](https://docs.microsoft.com/Office365/Enterprise/microsoft-365-guest-settings)

[<span data-ttu-id="5e298-154">Microsoft 365를 사용 하 여 보안 공동 작업 설정</span><span class="sxs-lookup"><span data-stu-id="5e298-154">Set up secure collaboration with Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)
