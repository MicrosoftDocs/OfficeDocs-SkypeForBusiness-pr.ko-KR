---
title: Microsoft 팀에서 게스트 액세스 관리
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
f1.keywords:
- NOCSH
description: 첫 번째 팀과 채널을 만들고, 초기 사용자를 미리 보고, 사용 및 피드백을 모니터링 하 고, 조직 전체 출시를 계획 하기 위한 리소스를 확보 하는 방법에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fea5ab9eec355d77f19165253fe97ee8aeb725ca
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43139247"
---
<a name="manage-guest-access-in-microsoft-teams"></a><span data-ttu-id="ff87a-103">Microsoft 팀에서 게스트 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="ff87a-103">Manage guest access in Microsoft Teams</span></span>
======================================

> [!IMPORTANT]
> <span data-ttu-id="ff87a-104">변경 내용이 적용되는 데 최대 24시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff87a-104">You may have to wait up to 24 hours for your changes to take effect.</span></span> 

<span data-ttu-id="ff87a-105">**게스트** 는 모든 Office 365 Business Premium, Office 365 Enterprise, Office 365 비즈니스 Essentials 및 Office 365 교육 구독에 포함 된 Microsoft 팀의 사용자 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="ff87a-105">**Guest** is a user type in Microsoft Teams that is included with all Office 365 Business Premium, Office 365 Enterprise, Office 365 Business Essentials, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="ff87a-106">추가 Office 365 라이선스가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ff87a-106">No additional Office 365 license is necessary.</span></span> <span data-ttu-id="ff87a-107">[게스트 액세스 라이선스](#guest-access-licensing-limits) 에 대 한 자세한 내용을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="ff87a-107">Read more about [guest access licensing](#guest-access-licensing-limits) below.</span></span>

<span data-ttu-id="ff87a-108">팀 게스트 액세스는 테 넌 트 수준 설정 이므로 기본적으로 꺼져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff87a-108">Teams guest access is a tenant-level setting and is turned off by default.</span></span> <span data-ttu-id="ff87a-109">게스트 액세스를 설정 하는 방법에 대 한 자세한 내용은 [팀에 대 한 게스트 액세스 설정 또는 해제](set-up-guests.md)또는 [게스트 액세스 검사 목록을](guest-access-checklist.md) 사용 하 여 설치를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff87a-109">For details about how to turn on guest access, see [Turn on or turn off guest access to Teams](set-up-guests.md), or use the [Guest access checklist ](guest-access-checklist.md) to walk you through the setup.</span></span>

<span data-ttu-id="ff87a-110">게스트 액세스를 설정한 후에는 [조직의 팀 관리 설정](enable-features-office-365.md) 에서 설명한 컨트롤을 사용 하 여 게스트에 대 한 설정을 구성 하 고 [새 Microsoft 팀 관리 센터로 전환 하는 동안 팀을 관리할](manage-teams-skypeforbusiness-admin-center.md)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff87a-110">After guest access is turned on, you can configure settings for guests using the controls described in [Manage Teams settings for your organization](enable-features-office-365.md) and [Manage Teams during the transition to the new Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md).</span></span>     
    
<span data-ttu-id="ff87a-111">IT 관리자는 테 넌 트 수준에서 게스트를 추가 하 고, 게스트 사용자 정책 및 사용 권한을 설정 및 관리 하 고, 게스트 사용자 활동에 대 한 보고서를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff87a-111">IT admins can add guests at the tenant level, set and manage guest user policies and permissions, and pull reports on guest user activity.</span></span> <span data-ttu-id="ff87a-112">이러한 컨트롤은 팀 관리 센터에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff87a-112">These controls are available in the Teams admin center.</span></span> <span data-ttu-id="ff87a-113">게스트 사용자 콘텐츠 및 활동은 Office 365의 나머지 부분과 동일한 준수 및 감사 보호에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="ff87a-113">Guest user content and activities fall under the same compliance and auditing protection as the rest of Office 365.</span></span>

<span data-ttu-id="ff87a-114">팀 소유자는 새 게스트를 초대 하 고 팀 관리 센터의 팀에 기존 디렉터리 게스트 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff87a-114">Team owners can invite new guests and add existing directory guest users to their teams in the Teams admin center.</span></span> <span data-ttu-id="ff87a-115">**팀 팀** > **관리** 페이지에서 게스트 사용자를 식별 하 고 **조직 전체 설정** > **게스트 액세스** 페이지에서 게스트에 대 한 채널 관련 기능을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff87a-115">Identify guest users on the **Teams** > **Manage teams** page, and set channel-related capabilities for guests on the  **Org-wide settings** > **Guest access** page.</span></span> <span data-ttu-id="ff87a-116">설정에는 다음 그림과 같이 게스트가 채널을 만들고 업데이트 하 고 삭제할 수 있도록 허용 하는 것이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff87a-116">Settings include allowing guests to create, update, and delete channels, as shown in the following illustration.</span></span>

![팀의 게스트 사용 권한 설정](media/manage-guest-access-image1.png)
  
<span data-ttu-id="ff87a-118">Azure AD (Active Directory) 포털을 사용 하 여 게스트와 Office 365 및 팀 리소스에 대 한 액세스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff87a-118">You can use the Azure Active Directory (Azure AD) portal to manage guests and their access to Office 365 and Teams resources.</span></span> <span data-ttu-id="ff87a-119">팀 게스트 액세스는 Azure AD business (B2B) 공동 작업 기능을 기본 인프라로 사용 하 여 id 속성, 멤버 자격, 다단계 인증 설정 등의 보안 원칙 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff87a-119">Teams guest access makes use of Azure AD business-to-business (B2B) collaboration capabilities as the underlying infrastructure to store security principles information such as identity properties, memberships, and multi-factor authentication settings.</span></span> <span data-ttu-id="ff87a-120">Azure AD B2B에 대 한 자세한 내용은 [AZURE AD b2b 공동 작업 이란 무엇 인가요?](https://go.microsoft.com/fwlink/p/?linkid=853011) [AZURE Active Directory B2B 공동 작업](https://go.microsoft.com/fwlink/p/?linkid=853020)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="ff87a-120">To learn more about Azure AD B2B, see [What is Azure AD B2B collaboration?](https://go.microsoft.com/fwlink/p/?linkid=853011) and [Azure Active Directory B2B collaboration FAQs](https://go.microsoft.com/fwlink/p/?linkid=853020).</span></span>

> [!NOTE]
> <span data-ttu-id="ff87a-121">Microsoft 팀은 테 넌 트에 대 한 게스트 사용자 추가를 허용 하거나 방지 하기 위해 항상 Azure AD 외부 설정을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ff87a-121">Microsoft Teams always honors Azure AD external settings to allow or prevent guest user additions to the tenant.</span></span> <span data-ttu-id="ff87a-122">자세한 내용은 [Microsoft 팀에서 게스트 액세스 권한 부여](Teams-dependencies.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ff87a-122">For more details, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>


## <a name="guest-access-licensing-limits"></a><span data-ttu-id="ff87a-123">게스트 액세스 라이선스 제한</span><span class="sxs-lookup"><span data-stu-id="ff87a-123">Guest access licensing limits</span></span>

<span data-ttu-id="ff87a-124">Teams에서는 추가할 수 있는 게스트 수를 제한하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ff87a-124">Teams doesn't restrict the number of guests you can add.</span></span> <span data-ttu-id="ff87a-125">그러나 테넌트에 추가할 수 있는 총 게스트 수는 Azure AD 라이선스가 허용하는 항목을 기반으로 합니다. 일반적으로 라이선스가 있는 사용자 당 게스트 수는 5 명입니다.</span><span class="sxs-lookup"><span data-stu-id="ff87a-125">However, the total number of guests that can be added to your tenant is based on what your Azure AD licensing allows - usually 5 guests per licensed user.</span></span> <span data-ttu-id="ff87a-126">자세한 내용은 [Azure AD B2B 공동 작업 라이선스](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff87a-126">For more information, see [Azure AD B2B collaboration licensing](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>

<span data-ttu-id="ff87a-127">이러한 라이선스 제한 사항으로 인해 (사용자의 테 넌 트를 최신으로 유지), 게스트 액세스를 정기적으로 검토 하 여 더 이상 필요 하지 않은 액세스 권한이 있는 사용자를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff87a-127">Because of these licensing limitations (and to keep your tenant up-to-date), you should review guest access periodically to identify users who have access that they don't need anymore.</span></span> <span data-ttu-id="ff87a-128">Azure AD를 사용 하 여 그룹 구성원 또는 응용 프로그램에 할당 된 사용자에 대 한 액세스 검토를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff87a-128">You can use Azure AD to create an access review for group members or users assigned to an application.</span></span> <span data-ttu-id="ff87a-129">되풀이 되는 access 리뷰를 만들면 시간을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff87a-129">Creating recurring access reviews can save you time.</span></span> <span data-ttu-id="ff87a-130">응용 프로그램에 대 한 액세스 권한이 있거나 그룹의 구성원 인 사용자를 정기적으로 검토 해야 하는 경우 이러한 검토의 빈도를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff87a-130">If you need to routinely review users who have access to an application or are members of a group, you can define the frequency of those reviews.</span></span> 

<span data-ttu-id="ff87a-131">게스트 액세스 검토를 수행 하거나, 게스트에 게 자신의 구성원을 검토 하도록 요청 하거나, 응용 프로그램 소유자나 비즈니스 의사 결정권자에 게 액세스 검토를 수행 하도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff87a-131">You can perform a guest access review yourself, ask guests to review their own membership, or ask an application owner or business decision maker to perform the access review.</span></span> <span data-ttu-id="ff87a-132">Azure 포털을 사용 하 여 게스트 액세스 검토를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff87a-132">Use the Azure portal to perform guest access reviews.</span></span> <span data-ttu-id="ff87a-133">자세한 내용은 [AZURE AD access 리뷰를 사용 하 여 게스트 액세스 관리](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ff87a-133">For more information, see [Manage guest access with Azure AD access reviews](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews).</span></span>

###  <a name="prerequisites-for-azure-ad-access-reviews"></a><span data-ttu-id="ff87a-134">Azure AD access 리뷰에 대 한 필수 조건</span><span class="sxs-lookup"><span data-stu-id="ff87a-134">Prerequisites for Azure AD access reviews</span></span>

<span data-ttu-id="ff87a-135">Microsoft Enterprise Mobility + Security, E5에 포함 되어 있는 Azure AD의 Premium P2 버전에서 Access 리뷰를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff87a-135">Access reviews are available with the Premium P2 edition of Azure AD, which is included in Microsoft Enterprise Mobility + Security, E5.</span></span> <span data-ttu-id="ff87a-136">자세한 내용은 [Azure Active Directory 버전](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ff87a-136">For more information, see [Azure Active Directory editions](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="ff87a-137">검토를 만들거나, 검토를 채우거 나, 액세스를 확인 하 여이 기능과 상호 작용 하는 각 사용자에 게 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff87a-137">Each user who interacts with this feature by creating a review, filling out a review, or confirming their access, must have a license.</span></span>



## <a name="lag-time-for-guest-access-settings-to-take-effect"></a><span data-ttu-id="ff87a-138">게스트 액세스 설정이 적용 되기까지 지연 되는 시간</span><span class="sxs-lookup"><span data-stu-id="ff87a-138">Lag time for guest access settings to take effect</span></span>

<span data-ttu-id="ff87a-139">Azure Active Directory의 게스트 액세스 설정의 경우 변경 내용이 Office 365 조직에 적용 되려면 2-24 시간이 소요 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff87a-139">For the guest access settings in Azure Active Directory, it takes 2-24 hours for the changes to take effect across your Office 365 organization.</span></span> <span data-ttu-id="ff87a-140">사용자가 팀에 게스트를 추가 하려고 할 때 "관리자에 게 문의" 라는 메시지가 표시 되는 경우 게스트 기능이 설정 되지 않았거나 설정이 아직 유효 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff87a-140">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been turned on or the settings aren't effective yet.</span></span> <span data-ttu-id="ff87a-141">게스트 액세스 설정 문제에 대 한 도움말은 [팀의 게스트 액세스 문제 해결](troubleshoot-guest-access.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ff87a-141">For help with problems setting up guest access, read [Troubleshoot guest access in Teams](troubleshoot-guest-access.md).</span></span>

  
## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="ff87a-142">외부 액세스(페더레이션) 대 게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="ff87a-142">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="ff87a-143">추가 정보</span><span class="sxs-lookup"><span data-stu-id="ff87a-143">More information</span></span>

<span data-ttu-id="ff87a-144">PowerShell을 사용 하 여 게스트 액세스를 관리 하는 방법에 대 한 자세한 내용은 [powershell을 사용 하 여 팀의 게스트 액세스 제어를](guest-access-powershell.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ff87a-144">For information about using PowerShell to manage guest access, see [Use PowerShell to control guest access to a team](guest-access-powershell.md).</span></span>


