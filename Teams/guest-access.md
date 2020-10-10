---
title: Microsoft Teams의 게스트 액세스
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rafarhi
audience: admin
search.appverid: MET150
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
description: Microsoft Teams의 게스트 액세스를 사용하면 조직의 팀에서 팀과 채널에 대한 액세스 권한을 부여하여 조직 외부의 사용자와 공동 작업을 할 수 있습니다.
ms.openlocfilehash: 6efaa942b3818d8fb5aaca7a07b9300f1c731dca
ms.sourcegitcommit: 43823358e7e1c1cece72a69a2ceb4eff86d3f927
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/10/2020
ms.locfileid: "48416853"
---
# <a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="18a34-103">Microsoft Teams의 게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="18a34-103">Guest access in Microsoft Teams</span></span>

<span data-ttu-id="18a34-104">게스트 액세스를 사용 하면 조직 외부의 사용자에 게 팀, 채널, 리소스, 채팅, 응용 프로그램에 대 한 액세스를 제공 하 여 회사 데이터에 대 한 제어를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-104">With guest access, you can provide access to teams, documents in channels, resources, chats, and applications to people outside your organization, while maintaining control over your corporate data.</span></span>

<span data-ttu-id="18a34-105">게스트는 직원, 학생 또는 조직의 구성원이 아닌 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-105">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="18a34-106">조직에 학교 또는 직장 계정을 가지고 있지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-106">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="18a34-107">예를 들어, 게스트에는 파트너, 공급 업체, 공급자 또는 컨설턴트 등이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-107">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="18a34-108">조직에 속하지 않은 사용자를 Teams에서 게스트로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-108">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="18a34-109">즉, 비즈니스 계정 (즉, Azure Active Directory 계정) 또는 소비자 전자 메일 계정 (Outlook.com, Gmail.com 등)을 사용 하는 모든 사용자가 팀에서 게스트로 참여할 수 있으며,이에 따라 팀과 채널 환경에 대 한 액세스 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-109">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with access to teams and channel experiences.</span></span>

<span data-ttu-id="18a34-110">팀 관리자는 [게스트가 팀에 사용할 수 있는 기능을 제어](manage-guests.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-110">As the Teams admin, you [control which features guests can (and can't) use in Teams](manage-guests.md).</span></span> <span data-ttu-id="18a34-111">팀의 게스트는 Microsoft 365의 나머지와 동일한 준수 및 감사 보호를 통해 다루고 있으며, Azure AD 내에서 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-111">Guests in Teams are covered by the same compliance and auditing protection as the rest of Microsoft 365, and can be managed within Azure AD.</span></span> <span data-ttu-id="18a34-112">게스트 액세스에는 Azure AD 및 Microsoft 365 또는 Office 365 서비스 제한이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-112">Guest access is subject to Azure AD and Microsoft 365 or Office 365 service limits.</span></span>

<span data-ttu-id="18a34-113">게스트 환경에는 디자인별로 제약 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-113">The guest experience has limitations by design.</span></span> <span data-ttu-id="18a34-114">게스트가 팀에서 수행할 수 있는 작업에 대 한 전체 목록은 [팀 구성원 및 게스트 기능 비교](guest-experience.md#comparison-of-team-member-and-guest-capabilities)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="18a34-114">For a full list of what a guest can and can't do in Teams, see [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="18a34-115">게스트 사용자는 동시 업그레이드 모드를 위해 Temas 조직 전체 설정을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-115">Guest users follow Teams Org-wide settings for the coexistence Upgrade mode.</span></span> <span data-ttu-id="18a34-116">변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-116">This can't be changed.</span></span>

<span data-ttu-id="18a34-117">외부 액세스 (페더레이션)와 게스트 액세스를 비교하려면 (어느 것을 사용할 지 결정하려면) [Teams의 다른 조직의 사용자와 커뮤니케이션](communicate-with-users-from-other-organizations.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="18a34-117">To compare external access (federation) with guest access (and decide which one you should use), read [Communicate with users from other organizations in Teams](communicate-with-users-from-other-organizations.md).</span></span>

## <a name="set-up-guest-access"></a><span data-ttu-id="18a34-118">게스트 액세스 설정</span><span class="sxs-lookup"><span data-stu-id="18a34-118">Set up guest access</span></span>

<span data-ttu-id="18a34-119">팀에서 게스트 액세스를 사용 하려면 Azure AD, Microsoft 365 그룹, SharePoint의 설정을 포함 하 여 Microsoft 365의 다른 설정을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-119">Guest access in Teams requires configuring other settings in Microsoft 365, including settings in Azure AD, Microsoft 365 Groups, and SharePoint.</span></span> <span data-ttu-id="18a34-120">팀에 게스트 초대를 시작할 준비가 되었으면 다음 중 하나를 읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="18a34-120">If you're ready to start inviting guests to teams, read one of the following:</span></span>

- <span data-ttu-id="18a34-121">일반적인 사용을 위해 팀에 대 한 게스트 액세스를 구성 하려면 [팀에서 게스트 공동 작업](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="18a34-121">To configure guest access for Teams for general use, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>
- <span data-ttu-id="18a34-122">Azure Active Directory를 사용 하 고 게스트가 팀 액세스를 자체 등록할 수 있도록 허용 하는 파트너 조직과 공동 작업 하려면 [관리 되는 게스트를 사용 하 여 B2B 엑스트라넷 만들기](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="18a34-122">To collaborate with a partner organization that uses Azure Active Directory and allow guests to self-enroll for team access, see [Create a B2B extranet with managed guests](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet).</span></span>

<span data-ttu-id="18a34-123">팀에서 게스트 액세스는 조직 전체에서 설정 되며 기본적으로 꺼져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-123">Guest access in Teams is an organization-wide setting and is turned off by default.</span></span> <span data-ttu-id="18a34-124">[민감도 레이블을](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)사용 하 여 개별 팀에 대 한 게스트 액세스를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-124">You can control guest access to individual teams by using [sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

## <a name="how-a-guest-becomes-a-member-of-a-team"></a><span data-ttu-id="18a34-125">게스트가 팀 구성원이 되는 방법</span><span class="sxs-lookup"><span data-stu-id="18a34-125">How a guest becomes a member of a team</span></span>

1. <span data-ttu-id="18a34-126">팀 소유자나 Microsoft 365 관리자가 [팀에 게스트를 추가](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)합니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-126">A team owner or a Microsoft 365 admin [adds a guest to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span>
2. <span data-ttu-id="18a34-127">게스트는 팀에 대한 정보와 구성원이 되었으므로 기대할 수 있는 내용이 포함된 팀 소유자의 환영 전자 메일을 받게 됩니다. </span><span class="sxs-lookup"><span data-stu-id="18a34-127">The guest receives a welcome email from the team owner, with information about the team and what to expect now that they're a member.</span></span>
3. <span data-ttu-id="18a34-128">게스트가 초대를 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-128">The guest accepts the invitation.</span></span>
  <span data-ttu-id="18a34-129">Azure Active Directory에서 회사 또는 학교 계정이 있는 게스트 사용자는 초대를 수락 하 고 직접 인증할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-129">Guest users who have an work or school account in Azure Active Directory can accept the invitation and authenticate directly.</span></span> <span data-ttu-id="18a34-130">다른 사용자는 1 회 통과 코드를 보내 id의 유효성을 검사 합니다 ([일회성 암호 인증](https://docs.microsoft.com/azure/active-directory/external-identities/one-time-passcode) 필요).</span><span class="sxs-lookup"><span data-stu-id="18a34-130">Other users are sent a one-time pass code to validate their identity ([One-time passcode authentication](https://docs.microsoft.com/azure/active-directory/external-identities/one-time-passcode) required).</span></span>
4. <span data-ttu-id="18a34-131">초대를 수락하면 게스트는 [팀과 채널에 참여](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499), 채널 메시지 받기 및 응답, [채널에서 파일에 액세스](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e), 채팅에 참여, 모임에 참여, 문서 공동 작업 등을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-131">After accepting the invitation, the guest can [participate in teams and channels](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499), receive and respond to channel messages, [access files in channels](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e), participate in chats, join meetings, collaborate on documents, and more.</span></span> 

<span data-ttu-id="18a34-132">Teams에서는 게스트를 명확하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-132">In Teams, guests are clearly identified.</span></span> <span data-ttu-id="18a34-133">게스트 사용자 이름에는 레이블 **(게스트)** 이 포함되고, 채널에는 팀에 게스트가 있음을 나타내는 아이콘이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-133">A guest user's name includes the label **(Guest)**, and a channel includes an icon to indicate that there are guests on the team.</span></span> <span data-ttu-id="18a34-134">자세한 내용은 [게스트 환경의 모습](guest-experience.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="18a34-134">For more details, see [What the guest experience is like](guest-experience.md).</span></span>
  
<span data-ttu-id="18a34-135">게스트는 Teams 내에서 언제든지 팀을 떠날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-135">Guests can leave the team at any time from within Teams.</span></span> <span data-ttu-id="18a34-136">자세한 내용은 [팀에서 나가는 방법](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="18a34-136">For details, see  [How do I leave a team?](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)</span></span>

> [!NOTE]
> <span data-ttu-id="18a34-137">팀에서 나가면 조직의 디렉터리에서 게스트 계정이 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-137">Leaving the team doesn't remove the guest account from your organization's directory.</span></span> <span data-ttu-id="18a34-138">Microsoft 365 전역 관리자 또는 Azure AD 관리자가이 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-138">This must be done by a Microsoft 365 global admin or an Azure AD admin.</span></span>

## <a name="licensing-for-guest-access"></a><span data-ttu-id="18a34-139">게스트 액세스에 대한 라이선스</span><span class="sxs-lookup"><span data-stu-id="18a34-139">Licensing for guest access</span></span>

<span data-ttu-id="18a34-140">게스트 액세스는 모든 Microsoft 365 비즈니스 표준, Microsoft 365 Enterprise 및 Microsoft 365 교육 구독에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-140">Guest access is included with all Microsoft 365 Business Standard, Microsoft 365 Enterprise, and Microsoft 365 Education subscriptions.</span></span> <span data-ttu-id="18a34-141">Microsoft 365 라이선스가 추가로 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-141">No additional Microsoft 365 license is necessary.</span></span> <span data-ttu-id="18a34-142">Teams에서는 추가할 수 있는 게스트 수를 제한하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-142">Teams doesn't restrict the number of guests you can add.</span></span> <span data-ttu-id="18a34-143">그러나 테넌트에 추가 할 수 있는 총 방문자 수는 Azure AD의 유료 기능에 따라 제한될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-143">However, the total number of guests that can be added to your tenant may be restricted by the paid features of Azure AD.</span></span> <span data-ttu-id="18a34-144">자세한 내용은 [AZURE AD External id에 대 한 청구 모델](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="18a34-144">For more information, see [Billing model for Azure AD External Identities](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>

> [!NOTE]
> <span data-ttu-id="18a34-145">독립 실행형 Microsoft 365 구독 계획 (예: Exchange Online 계획 2)만 있는 조직의 사용자는 해당 사용자가 동일한 조직에 속해 있는 것으로 간주 되므로 조직에 게스트로 초대 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-145">Users in your organization who have standalone Microsoft 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="18a34-146">사용자가 Teams를 사용하려면 Microsoft 365 Business Standard, Office 365 Enterprise 또는 Office 365 Education 구독에 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-146">For these users to use Teams, they must be assigned an Microsoft 365 Business Standard, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="guest-access-reviews"></a><span data-ttu-id="18a34-147">게스트 액세스 검토</span><span class="sxs-lookup"><span data-stu-id="18a34-147">Guest access reviews</span></span>

<span data-ttu-id="18a34-148">Azure AD를 사용 하 여 그룹 구성원 또는 응용 프로그램에 할당 된 사용자에 대 한 액세스 검토를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-148">You can use Azure AD to create an access review for group members or users assigned to an application.</span></span> <span data-ttu-id="18a34-149">되풀이 되는 access 리뷰를 만들면 시간을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-149">Creating recurring access reviews can save you time.</span></span> <span data-ttu-id="18a34-150">응용 프로그램, 팀 또는 그룹의 구성원에 대 한 액세스 권한이 있는 사용자를 정기적으로 검토 해야 하는 경우 이러한 검토의 빈도를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-150">If you need to routinely review users who have access to an application, a team, or are members of a group, you can define the frequency of those reviews.</span></span> 

<span data-ttu-id="18a34-151">게스트 액세스 검토를 수행 하거나, 게스트에 게 자신의 구성원을 검토 하도록 요청 하거나, 응용 프로그램 소유자나 비즈니스 의사 결정권자에 게 액세스 검토를 수행 하도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-151">You can perform a guest access review yourself, ask guests to review their own membership, or ask an application owner or business decision maker to perform the access review.</span></span> <span data-ttu-id="18a34-152">Azure 포털을 사용 하 여 게스트 액세스 검토를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="18a34-152">Use the Azure portal to perform guest access reviews.</span></span> <span data-ttu-id="18a34-153">자세한 내용은 [AZURE AD access 리뷰를 사용 하 여 게스트 액세스 관리](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="18a34-153">For more information, see [Manage guest access with Azure AD access reviews](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews).</span></span>

## <a name="related-topics"></a><span data-ttu-id="18a34-154">관련 항목</span><span class="sxs-lookup"><span data-stu-id="18a34-154">Related topics</span></span>

[<span data-ttu-id="18a34-155">조직 외부의 사용자와 공동 작업</span><span class="sxs-lookup"><span data-stu-id="18a34-155">Collaborating with people outside your organization</span></span>](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[<span data-ttu-id="18a34-156">특정 Microsoft 365 그룹 또는 Microsoft 팀 팀의 게스트 사용자 차단</span><span class="sxs-lookup"><span data-stu-id="18a34-156">Block guest users from a specific Microsoft 365 group or Microsoft Teams team</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="18a34-157">안전한 게스트 공유 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="18a34-157">Create a secure guest sharing environment</span></span>](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

[<span data-ttu-id="18a34-158">비즈니스용 제품에 대한 고객 지원 센터 - 관리자 도움말</span><span class="sxs-lookup"><span data-stu-id="18a34-158">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)

[<span data-ttu-id="18a34-159">세 가지 보호 계층을 사용 하 여 팀 구성</span><span class="sxs-lookup"><span data-stu-id="18a34-159">Configure Teams with three tiers of protection</span></span>](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
