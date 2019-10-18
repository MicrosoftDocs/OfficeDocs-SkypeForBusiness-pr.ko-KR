---
title: Microsoft 팀에서 게스트 액세스 관리
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: IT 관리자는 테 넌 트 수준에서 게스트를 추가 하 고, 게스트 사용자 정책 및 사용 권한을 설정 및 관리 하 고, 게스트를 초대할 수 있는 사용자를 결정 하 고, 게스트 사용자의 보고서를 가져올 수 있습니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7db3d42a8d4ae44364ee56f6c7f31ce501a34137
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573170"
---
<a name="manage-guest-access-in-microsoft-teams"></a><span data-ttu-id="14b1a-103">Microsoft 팀에서 게스트 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="14b1a-103">Manage guest access in Microsoft Teams</span></span>
======================================

<span data-ttu-id="14b1a-104">**게스트** 는 모든 Office 365 Business Premium, Office 365 Enterprise 및 Office 365 교육 구독에 포함 된 Microsoft 팀의 사용자/라이선스 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="14b1a-104">**Guest** is a user/license type in Microsoft Teams that is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="14b1a-105">추가 Office 365 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14b1a-105">No additional Office 365 license is necessary.</span></span> <span data-ttu-id="14b1a-106">팀 게스트 액세스는 테 넌 트 수준 설정 이므로 기본적으로 꺼져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14b1a-106">Teams guest access is a tenant-level setting and is turned off by default.</span></span> <span data-ttu-id="14b1a-107">게스트 액세스를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 [Microsoft 팀에 대 한 게스트 액세스 설정 또는 해제](set-up-guests.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="14b1a-107">For details about how to enable guest access, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span>

<span data-ttu-id="14b1a-108">**게스트** 사용자/라이선스 형식을 켠 후에는 [조직의 Microsoft 팀 설정 관리](enable-features-office-365.md) 에 설명 된 컨트롤을 통해 게스트에 대 한 설정을 구성 하 고 [새 Microsoft 팀으로 전환 하는 동안 팀을 관리할 수 있습니다. 관리 센터](manage-teams-skypeforbusiness-admin-center.md).</span><span class="sxs-lookup"><span data-stu-id="14b1a-108">After the **Guest** user/license type is turned on, you can configure settings for guests via the controls described in [Manage Microsoft Teams settings for your organization](enable-features-office-365.md) and [Manage Teams during the transition to the new Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md).</span></span>     
    
<span data-ttu-id="14b1a-109">IT 관리자는 테 넌 트 수준에서 게스트를 추가 하 고, 게스트 사용자 정책 및 사용 권한을 설정 및 관리 하 고, 게스트 사용자 활동에 대 한 보고서를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14b1a-109">IT admins can add guests at the tenant level, set and manage guest user policies and permissions, and pull reports on guest user activity.</span></span> <span data-ttu-id="14b1a-110">이러한 컨트롤은 Microsoft 팀 관리 센터를 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14b1a-110">These controls are available through the Microsoft Teams admin center.</span></span> <span data-ttu-id="14b1a-111">게스트 사용자 콘텐츠 및 활동은 Office 365의 나머지와 동일한 준수 및 감사 보호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="14b1a-111">Guest user content and activities are under the same compliance and auditing protection as the rest of Office 365.</span></span>

<span data-ttu-id="14b1a-112">팀 소유자는 새 게스트를 초대 하 고 기존 디렉터리 게스트 사용자를 팀에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14b1a-112">Team owners can invite new guests and add existing directory guest users to their teams.</span></span> <span data-ttu-id="14b1a-113">팀 소유자 **는 팀을** > **관리**하는 게스트 사용자를 식별 하 고, **조직 전체 설정** > **게스트 액세스**를 통해 guest에 대 한 채널 관련 기능을 설정 하 고, 게스트의 생성, 업데이트 및 사용을 허용할 수 있습니다. 다음 그림에 표시 된 대로 채널을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="14b1a-113">Team owners can identify guest users via **Teams** > **Manage teams**, and set channel-related capabilities for guests via **Org-wide settings** > **Guest access**, including allowing guests to create, update, and delete channels, as shown in the following illustration.</span></span>

![팀의 게스트 사용 권한 설정](media/manage-guest-access-image1.png)
  
<span data-ttu-id="14b1a-115">Azure AD (Active Directory) 포털을 사용 하 여 게스트와 Office 365 및 팀 리소스에 대 한 액세스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14b1a-115">You can use the Azure Active Directory (Azure AD) portal to manage guests and their access to Office 365 and Teams resources.</span></span> <span data-ttu-id="14b1a-116">팀 게스트 액세스는 Azure AD business (B2B) 공동 작업 기능을 기본 인프라로 사용 하 여 id 속성, 멤버 자격, 다단계 인증 설정 등의 보안 원칙 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="14b1a-116">Teams guest access makes use of Azure AD business-to-business (B2B) collaboration capabilities as the underlying infrastructure to store security principles information such as identity properties, memberships, and multi-factor authentication settings.</span></span> <span data-ttu-id="14b1a-117">Azure AD B2B에 대 한 자세한 내용은 [AZURE AD b2b 공동 작업 이란 무엇 인가요?](https://go.microsoft.com/fwlink/p/?linkid=853011) [AZURE Active Directory B2B 공동 작업](https://go.microsoft.com/fwlink/p/?linkid=853020)에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="14b1a-117">To learn more about Azure AD B2B, see [What is Azure AD B2B collaboration?](https://go.microsoft.com/fwlink/p/?linkid=853011) and [Azure Active Directory B2B collaboration FAQs](https://go.microsoft.com/fwlink/p/?linkid=853020).</span></span>

> [!NOTE]
> <span data-ttu-id="14b1a-118">Microsoft 팀은 테 넌 트에 대 한 게스트 사용자 추가를 허용 하거나 방지 하기 위해 항상 Azure AD 외부 설정을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="14b1a-118">Microsoft Teams always honors Azure AD external settings to allow or prevent guest user additions to the tenant.</span></span> <span data-ttu-id="14b1a-119">자세한 내용은 [Microsoft 팀에서 게스트 액세스 권한 부여](Teams-dependencies.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="14b1a-119">For more details, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
  
## <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="14b1a-120">게스트 액세스와 외부 액세스 (페더레이션) 비교</span><span class="sxs-lookup"><span data-stu-id="14b1a-120">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="review-guest-access-periodically"></a><span data-ttu-id="14b1a-121">정기적으로 게스트 액세스 검토</span><span class="sxs-lookup"><span data-stu-id="14b1a-121">Review guest access periodically</span></span>

<span data-ttu-id="14b1a-122">팀에서 사용이 허가 된 각 사용자에 대해 5 개의 게스트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14b1a-122">In Teams, you can add 5 guests for each licensed user.</span></span> <span data-ttu-id="14b1a-123">이러한 제한 사항으로 인해 또는 테 넌 트를 최신 상태로 유지 하려는 경우 게스트 액세스를 정기적으로 검토 하 여 더 이상 필요 하지 않은 액세스 권한이 있는 사용자를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14b1a-123">Because of this limitation, or because you want to keep your tenant up to date, you should review guest access periodically to identify users who have access that they don't need anymore.</span></span> <span data-ttu-id="14b1a-124">Azure AD를 사용 하 여 그룹 구성원 또는 응용 프로그램에 할당 된 사용자에 대 한 액세스 검토를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14b1a-124">You can use Azure AD to create an access review for group members or users assigned to an application.</span></span> <span data-ttu-id="14b1a-125">되풀이 되는 access 리뷰를 만들면 시간을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14b1a-125">Creating recurring access reviews can save you time.</span></span> <span data-ttu-id="14b1a-126">응용 프로그램에 대 한 액세스 권한이 있거나 그룹의 구성원 인 사용자를 정기적으로 검토 해야 하는 경우 이러한 검토의 빈도를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14b1a-126">If you need to routinely review users who have access to an application or are members of a group, you can define the frequency of those reviews.</span></span> 

<span data-ttu-id="14b1a-127">게스트 액세스 검토를 수행 하거나, 게스트에 게 자신의 구성원을 검토 하도록 요청 하거나, 응용 프로그램 소유자나 비즈니스 의사 결정권자에 게 액세스 검토를 수행 하도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="14b1a-127">You can perform a guest access review yourself, ask guests to review their own membership, or ask an application owner or business decision maker to perform the access review.</span></span> <span data-ttu-id="14b1a-128">Azure 포털을 사용 하 여 게스트 액세스 검토를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="14b1a-128">You use the Azure portal to perform guest access reviews.</span></span> <span data-ttu-id="14b1a-129">자세한 내용은 [AZURE AD access 리뷰를 사용 하 여 게스트 액세스 관리](https://docs.microsoft.com/en-us/azure/active-directory/governance/manage-guest-access-with-access-reviews)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="14b1a-129">For more information, see [Manage guest access with Azure AD access reviews](https://docs.microsoft.com/en-us/azure/active-directory/governance/manage-guest-access-with-access-reviews).</span></span>

###  <a name="prerequisites"></a><span data-ttu-id="14b1a-130">필요 조건</span><span class="sxs-lookup"><span data-stu-id="14b1a-130">Prerequisites</span></span>

<span data-ttu-id="14b1a-131">Microsoft Enterprise Mobility + Security, E5에 포함 되어 있는 Azure AD의 Premium P2 버전에서 Access 리뷰를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14b1a-131">Access reviews are available with the Premium P2 edition of Azure AD, which is included in Microsoft Enterprise Mobility + Security, E5.</span></span> <span data-ttu-id="14b1a-132">자세한 내용은 [Azure Active Directory 버전](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-whatis)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="14b1a-132">For more information, see [Azure Active Directory editions](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="14b1a-133">검토를 만들거나, 검토를 채우거 나, 액세스를 확인 하 여이 기능과 상호 작용 하는 각 사용자에 게 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14b1a-133">Each user who interacts with this feature by creating a review, filling out a review, or confirming their access, must have a license.</span></span>

<span data-ttu-id="14b1a-134">팀에서 추가할 수 있는 관람객 수를 제한 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14b1a-134">Teams doesn't restrict the number of guests you can add.</span></span> <span data-ttu-id="14b1a-135">그러나 테 넌 트에 추가할 수 있는 총 게스트 수는 AAD 라이선스에서 허용 하는 것을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="14b1a-135">However, the total number of guests that can be added to your tenant is based on what your AAD licensing allows.</span></span> <span data-ttu-id="14b1a-136">자세한 내용은 [AZURE AD B2B 공동 작업 라이선스](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="14b1a-136">For more information, see [Azure AD B2B collaboration licensing](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance).</span></span>

## <a name="guest-access-latencies"></a><span data-ttu-id="14b1a-137">게스트 액세스 대기 시간</span><span class="sxs-lookup"><span data-stu-id="14b1a-137">Guest access latencies</span></span>

<span data-ttu-id="14b1a-138">게스트 설정은 Azure AD에서 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14b1a-138">The guest settings are set in Azure AD.</span></span> <span data-ttu-id="14b1a-139">변경 내용이 Office 365 조직에서 유효 하 게 유지 되려면 2 시간에서 24 시간 정도 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="14b1a-139">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="14b1a-140">사용자가 팀에 게스트를 추가 하려고 할 때 "관리자에 게 문의" 라는 메시지가 표시 되 면 게스트 기능을 사용 하도록 설정 하지 않았거나 설정이 아직 유효 하지 않은 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14b1a-140">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings aren't effective yet.</span></span>

## <a name="more-information"></a><span data-ttu-id="14b1a-141">추가 정보</span><span class="sxs-lookup"><span data-stu-id="14b1a-141">More information</span></span>

<span data-ttu-id="14b1a-142">PowerShell을 사용 하 여 게스트 액세스를 관리 하는 방법에 대 한 자세한 내용은 [powershell을 사용 하 여 팀의 게스트 액세스 제어를](guest-access-powershell.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="14b1a-142">For information about using PowerShell to manage guest access, see [Use PowerShell to control guest access to a team](guest-access-powershell.md).</span></span>


