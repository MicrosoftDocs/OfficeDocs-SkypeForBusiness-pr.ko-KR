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
- m365initiative-externalcollab
ms.reviewer: rafarhi
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
description: 네 가지 수준의 권한 부여를 통해 Microsoft Teams 게스트 액세스 기능을 관리합니다.
ms.openlocfilehash: 40bc8c68ac3f1ad3117fa47aa0aad5f14ff3be69
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030994"
---
# <a name="authorize-guest-access-in-microsoft-teams"></a><span data-ttu-id="70d87-103">Microsoft Teams에서 게스트 액세스 권한 부여</span><span class="sxs-lookup"><span data-stu-id="70d87-103">Authorize guest access in Microsoft Teams</span></span>

<span data-ttu-id="70d87-104">조직의 요구 사항을 충족하기 위해 네 가지 수준의 권한 부여를 통해 Teams 게스트 액세스 기능 및 기능을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70d87-104">To satisfy your organization's requirements, you can manage Teams guest access features and capabilities through four different levels of authorization.</span></span> <span data-ttu-id="70d87-105">모든 권한 부여 수준은 Microsoft 365 조직에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="70d87-105">All the authorization levels apply to your Microsoft 365 organization.</span></span> <span data-ttu-id="70d87-106">각 권한 수준은 아래와 같이 게스트 경험을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="70d87-106">Each authorization level controls the guest experience as shown below:</span></span>

- <span data-ttu-id="70d87-107">**Azure Active Directory:** Teams의 게스트 액세스는 Azure AD B2B(Business-to-Business) 플랫폼에 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="70d87-107">**Azure Active Directory**: Guest access in Teams relies on the Azure AD business-to-business (B2B) platform.</span></span> <span data-ttu-id="70d87-108">이 권한 수준은 디렉터리, 테넌트 및 응용 프로그램 수준에서의 게스트 경험을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="70d87-108">This authorization level controls the guest experience at the directory, tenant, and application level.</span></span>
- <span data-ttu-id="70d87-109">**Teams:** Teams에서만 게스트 환경을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="70d87-109">**Teams**: Controls the guest experience in Teams only.</span></span>
- <span data-ttu-id="70d87-110">**Microsoft 365 그룹:** Microsoft 365 그룹 및 Teams의 게스트 환경을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="70d87-110">**Microsoft 365 Groups**: Controls the guest experience in Microsoft 365 Groups and Teams.</span></span>
- <span data-ttu-id="70d87-111">**SharePoint 및 OneDrive:** SharePoint, OneDrive, Microsoft 365 그룹 및 Teams에서 게스트 환경을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="70d87-111">**SharePoint and OneDrive**: Controls the guest experience in SharePoint, OneDrive, Microsoft 365 Groups, and Teams.</span></span>

<span data-ttu-id="70d87-112">이러한 서로 다른 권한 수준은 조직에 게스트 액세스를 설정하는 방법에 유연성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="70d87-112">These different authorization levels provide you with flexibility in how you set up guest access for your organization.</span></span> <span data-ttu-id="70d87-113">예를 들어 Teams에서 게스트 사용자를 허용하지 않지만 조직에서 게스트 사용자를 허용하려는 경우 Teams에서 게스트 액세스를 해제하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70d87-113">For example, if you don't want to allow guest users in Teams but want to allow it overall in your organization, just turn off guest access in Teams.</span></span> <span data-ttu-id="70d87-114">또 다른 예: Azure AD, Teams 및 그룹 수준에서 게스트 액세스를 사용하도록 설정한 다음 데이터 분류와 같은 하나 이상의 조건과 일치하는 선택한 팀에 게스트 사용자를 추가하지 않도록 설정할 수 [있습니다.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)</span><span class="sxs-lookup"><span data-stu-id="70d87-114">Another example: You could enable guest access at the Azure AD, Teams, and Groups levels, but then [disable the addition of guest users on selected teams that match one or more criteria such as data classification equals confidential](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span> <span data-ttu-id="70d87-115">SharePoint 및 OneDrive에는 Microsoft 365 그룹을 사용하지 않는 자체 게스트 액세스 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70d87-115">SharePoint and OneDrive have their own guest access settings that don't rely on Microsoft 365 Groups.</span></span>

<span data-ttu-id="70d87-116">종단별 게스트 액세스 구성 지침은 팀의 게스트와 공동 [작업을 참조하세요.](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)</span><span class="sxs-lookup"><span data-stu-id="70d87-116">For end-to-end guest access configuration instructions, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

> [!NOTE]
> <span data-ttu-id="70d87-117">게스트는 [Microsoft 365 및 Office 365 서비스 설명](https://go.microsoft.com/fwlink/p/?linkid=282347) 및 [Azure AD B2B 공동 작업의 제한 사항](https://docs.microsoft.com/azure/active-directory/external-identities/current-limitations)에서 설명하는 서비스 제한의 적용을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="70d87-117">Guests are subject to the service limits described in [Microsoft 365 and Office 365 service descriptions](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Limitations of Azure AD B2B collaboration](https://docs.microsoft.com/azure/active-directory/external-identities/current-limitations).</span></span> 

<span data-ttu-id="70d87-118">다음 다이어그램에서는 Azure Active Directory, Teams 및 Microsoft 365 간에 게스트 액세스 권한 부여 종속성의 부여 및 통합 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="70d87-118">The following diagram shows how guest access authorization dependency is granted and integrated between Azure Active Directory, Teams, and Microsoft 365.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="70d87-119">![게스트 액세스에 대한 권한 종속성 다이어그램.](media/teams_dependencies_image1.png)</span><span class="sxs-lookup"><span data-stu-id="70d87-119">![Diagram of authorization dependencies for guest access.](media/teams_dependencies_image1.png)</span></span>

<span data-ttu-id="70d87-120">다음 다이어그램은 일반적인 게스트 액세스 초대 및 상환 흐름을 통해 사용자 경험이 권한 모델을 사용하는 방법을 개략적으로 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="70d87-120">The next diagram shows, at a high level, how the user experience works with the permission model through a typical guest access invitation and redemption flow.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="70d87-121">![초대 및 상환 흐름 다이어그램](media/authorize-guest-image1.png)</span><span class="sxs-lookup"><span data-stu-id="70d87-121">![Diagram of invitation and redemption flows](media/authorize-guest-image1.png)</span></span>

<span data-ttu-id="70d87-122">앱, 봇 및 커넥터에는 사용자 계정에 특정된 자체 사용 권한 및/또는 동의 집합이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70d87-122">It's important to note here that apps, bots, and connectors might require their own set of permissions and/or consent specific to the user account.</span></span> <span data-ttu-id="70d87-123">이들은 별도로 부여해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70d87-123">These might need to be granted separately.</span></span> <span data-ttu-id="70d87-124">마찬가지로 SharePoint는 특정 사용자, 사용자 그룹 또는 사이트 수준에 대해 추가 외부 공유 경계를 부과할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70d87-124">Similarly, SharePoint might impose extra external sharing boundaries for a specific user, groups of users, or even at the site level.</span></span>

<span data-ttu-id="70d87-125">앞의 두 다이어그램은 [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true)에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70d87-125">The previous two diagrams are also available in [Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/media/teams_dependencies.vsdx?raw=true).</span></span>

## <a name="control-guest-access-in-azure-active-directory"></a><span data-ttu-id="70d87-126">Azure Active Directory에서 게스트 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="70d87-126">Control guest access in Azure Active Directory</span></span>

<span data-ttu-id="70d87-127">Azure AD를 사용하여 외부 협력자를 게스트로 초대할지와 초대 방식을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70d87-127">Use Azure AD to determine whether external collaborators can be invited into your tenant as guests, and in what ways.</span></span> <span data-ttu-id="70d87-128">Azure B2B 게스트 액세스에 대한 자세한 내용은 [Azure Active Directory B2B의 게스트 사용자 액세스란](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70d87-128">For more information about Azure B2B guest access, see [What is guest user access in Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b).</span></span> <span data-ttu-id="70d87-129">Azure AD 역할에 대한 자세한 내용은 [Azure Active Directory 테넌트에서 파트너 조직의 사용자에게 권한 부여](https://docs.microsoft.com/azure/active-directory/b2b/add-guest-to-role)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70d87-129">For information about Azure AD roles, see [Grant permissions to users from partner organizations in your Azure Active Directory tenant](https://docs.microsoft.com/azure/active-directory/b2b/add-guest-to-role).</span></span>

<span data-ttu-id="70d87-130">초대 설정은 조직 수준에서 적용하고 디렉터리 및 애플리케이션 수준에서 게스트 환경을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="70d87-130">The settings for invitations apply at the organization level and control the guest experience at the directory and application level.</span></span> <span data-ttu-id="70d87-131">외부 공동 작업 설정에서 이러한 [설정을 구성할 수 있습니다.](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/CompanyRelationshipsMenuBlade/Settings)</span><span class="sxs-lookup"><span data-stu-id="70d87-131">You can configure these settings in [External collaboration settings](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/CompanyRelationshipsMenuBlade/Settings).</span></span>

<span data-ttu-id="70d87-132">Azure AD에는 외부 사용자를 구성하기위한 다음 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70d87-132">Azure AD includes the following settings to configure external users:</span></span>

- [<span data-ttu-id="70d87-133">게스트 사용자 액세스 제한</span><span class="sxs-lookup"><span data-stu-id="70d87-133">Guest user access restrictions</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-restrict-guest-permissions)

- <span data-ttu-id="70d87-134">**게스트 초대자 역할의 관리자 및 사용자 초대 가능**: **예** 는 게스트 초대자 역할의 관리자 및 사용자가 게스트를 테넌트로 초대할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="70d87-134">**Admins and users in the guest inviter role can invite**: **Yes** means that admins and users in the guest inviter role will be able to invite guests to the tenant.</span></span> <span data-ttu-id="70d87-135">**아니요** 는 관리자와 사용자가 테넌트에 게스트를 초대할 수 없음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="70d87-135">**No** means admins and users can't invite guests to the tenant.</span></span>
- <span data-ttu-id="70d87-136">**회원 초대 가능**: 디렉토리의 관리자가 아닌 회원이 손님을 초대할 수 있게 하려면 이 정책을 **예**(권장)로 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="70d87-136">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes** (recommended).</span></span> <span data-ttu-id="70d87-137">관리자만 게스트를 추가할 수 있게 하려는 경우 이 정책을 **아니오** 로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70d87-137">If you prefer that only admins be able to add guests, you can set this policy to **No**.</span></span> <span data-ttu-id="70d87-138">**아니오** 로 설정할 경우 관리자가 아닌 Teams 소유자의 게스트 환경이 제한됨에 유의하십시오. 이 소유자들은 AAD에 이미 추가된 Teams에만 게스트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70d87-138">Keep in mind that setting **No** will limit the guest experience for non-admin teams owners; they'll only be able to add guests in Teams that have already been added in AAD by the admin.</span></span>
- <span data-ttu-id="70d87-139">**게스트 초대 가능**: **예** 는 디렉터리의 게스트를 초대하여 SharePoint 사이트 또는 Azure 리소스와 같은 Azure AD로 보안된 리소스에 대해 공동 작업을 수행할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="70d87-139">**Guests can invite**: **Yes** means that guests in your directory can invite other guests to collaborate on resources secured by your Azure AD, such as SharePoint sites or Azure resources.</span></span> <span data-ttu-id="70d87-140">**아니요** 는 게스트가 다른 게스트를 초대하여 조직과 공동 작업을 할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70d87-140">**No** means that guests can't invite other guests to collaborate with your organization.</span></span> <span data-ttu-id="70d87-141">예로 **설정되어 있는 경우에도** 게스트는 Teams에서 다른 게스트를 초대할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70d87-141">Even if set to **Yes**, guest cannot invite other guests in Teams.</span></span>
 
<span data-ttu-id="70d87-142">게스트를 초대할 수 있는 사용자 제어에 대한 자세한 내용은 B2B 외부 공동 작업 사용 및 게스트 초대할 수 있는 [사용자 관리를 참조하세요.](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)</span><span class="sxs-lookup"><span data-stu-id="70d87-142">For more information about controlling who can invite guests, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

> [!NOTE]
> <span data-ttu-id="70d87-143">또한 테넌트에 게스트로 초대되는 도메인을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70d87-143">You can also manage which domains can be invited into your tenant as guests.</span></span> <span data-ttu-id="70d87-144">특정 조직의 B2B 사용자에 대한 초대 허용 또는 [차단을 참조합니다.](https://docs.microsoft.com/azure/active-directory/external-identities/allow-deny-list)</span><span class="sxs-lookup"><span data-stu-id="70d87-144">See [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/external-identities/allow-deny-list).</span></span>

<span data-ttu-id="70d87-145">Teams에 게스트를 추가할 때 계정이 디렉터리에 자동으로 추가되므로 사용자 게스트 계정을 Azure AD B2B에 수동으로 추가할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70d87-145">Adding the user guest account manually to Azure AD B2B is not required, as the account will be added to the directory automatically when you add the guest to Teams.</span></span>

### <a name="licensing-for-guest-access"></a><span data-ttu-id="70d87-146">게스트 액세스에 대한 라이선스</span><span class="sxs-lookup"><span data-stu-id="70d87-146">Licensing for guest access</span></span>

<span data-ttu-id="70d87-147">게스트 액세스 라이선스는 Azure AD 외부 ID 가격을 사용하며 월별 활성 게스트를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="70d87-147">Guest access licensing uses Azure AD External Identities pricing and is based on monthly active guests.</span></span> <span data-ttu-id="70d87-148">자세한 [내용은 Azure AD 외부 ID에](https://docs.microsoft.com/azure/active-directory/external-identities/external-identities-pricing) 대한 청구 모델을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70d87-148">See [Billing model for Azure AD External Identities](https://docs.microsoft.com/azure/active-directory/external-identities/external-identities-pricing) for details.</span></span>

> [!NOTE]
> <span data-ttu-id="70d87-149">Exchange Online Plan 2와 같이 독립실행형 Office 365 구독 계획만 가진 조직의 사용자는 Teams에서 동일한 조직에 속한 것으로 간주하기 때문에 조직에 게스트로 초대될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70d87-149">Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="70d87-150">사용자가 Teams를 사용하려면 Microsoft 365 Business Standard, Office 365 Enterprise 또는 Office 365 Education 구독에 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70d87-150">For these users to use Teams, they must be assigned an Microsoft 365 Business Standard, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="70d87-151">외부 액세스 (페더레이션) 및 게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="70d87-151">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="related-topics"></a><span data-ttu-id="70d87-152">관련 항목</span><span class="sxs-lookup"><span data-stu-id="70d87-152">Related topics</span></span>

- [<span data-ttu-id="70d87-153">Microsoft 365 게스트 공유 설정 참조</span><span class="sxs-lookup"><span data-stu-id="70d87-153">Microsoft 365 guest sharing settings reference</span></span>](https://docs.microsoft.com/Office365/Enterprise/microsoft-365-guest-settings)

[<span data-ttu-id="70d87-154">Microsoft 365를 사용하여 안전한 공동 작업 설정</span><span class="sxs-lookup"><span data-stu-id="70d87-154">Set up secure collaboration with Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)
