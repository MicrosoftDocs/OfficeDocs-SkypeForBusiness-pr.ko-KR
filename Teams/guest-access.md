---
title: Microsoft Teams의 게스트 액세스
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
audience: admin
search.appverid: MET150
description: Microsoft Teams의 게스트 액세스를 사용하면 조직의 팀에서 팀과 채널에 대한 액세스 권한을 부여하여 조직 외부의 사용자와 공동 작업을 할 수 있습니다.
localization_priority: Priority
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c025e408842c3d883112b7c99d930fc77db47435
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "44867975"
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="343a6-103">Microsoft Teams의 게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="343a6-103">Guest access in Microsoft Teams</span></span>
======================================

<span data-ttu-id="343a6-104">게스트 액세스를 사용하여 조직 외부의 개인 사용자를 Microsoft Teams의 팀과 채널에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="343a6-104">Guest access lets you add individual users from outside your organization to your teams and channels in Microsoft Teams.</span></span> 

<span data-ttu-id="343a6-105">외부 액세스 (페더레이션)와 게스트 액세스를 비교하려면 (어느 것을 사용할 지 결정하려면) [Teams의 다른 조직의 사용자와 커뮤니케이션](communicate-with-users-from-other-organizations.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="343a6-105">To compare external access (federation) with guest access (and decide which one you should use), read [Communicate with users from other organizations in Teams](communicate-with-users-from-other-organizations.md).</span></span>

<span data-ttu-id="343a6-106">조직에서 게스트 액세스를 활성화할 준비가 되면 [게스트 액세스 검사 목록](guest-access-checklist.md)에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="343a6-106">If you're ready to turn on guest access in your organization, start with the [Guest access checklist](guest-access-checklist.md).</span></span>

## <a name="guest-access-overview"></a><span data-ttu-id="343a6-107">게스트 액세스 개요</span><span class="sxs-lookup"><span data-stu-id="343a6-107">Guest access overview</span></span>

<span data-ttu-id="343a6-108">게스트 액세스를 사용하면 조직의 팀에서 Teams의 기존 팀과 채널에 대한 액세스 권한을 부여하여 조직 외부의 사용자와 공동 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="343a6-108">Guest access allows teams in your organization to collaborate with people outside your organization by granting them access to existing teams and channels in Teams.</span></span> <span data-ttu-id="343a6-109">비즈니스 또는 소비자 전자 메일 계정(Outlook, Gmail 등)이 있는 사용자는 팀 채팅, 모임 및 파일에 대한 모든 액세스 권한을 부여받아 Teams에서 게스트로 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="343a6-109">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span> <span data-ttu-id="343a6-110">Teams 관리자는 Teams에서 게스트가 사용할 수 있거나 사용할 수 없는 기능을 제어할 수 있습니다. [게스트 액세스 관리](manage-guests.md)를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="343a6-110">As the Teams admin, you control which features guests can (and can't) use in Teams - check out [Manage guest access](manage-guests.md).</span></span>

<span data-ttu-id="343a6-111">게스트 액세스는 Teams에서 기본적으로 비활성화된 조직 전체에 대한 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="343a6-111">Guest access is an org-wide setting in Teams and is turned off by default.</span></span> <span data-ttu-id="343a6-112">게스트 액세스에는 Azure AD 및 Microsoft 365 또는 Office 365 서비스 제한이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="343a6-112">Guest access is subject to Azure AD and Microsoft 365 or Office 365 service limits.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="343a6-113">게스트 사용자는 동시 업그레이드 모드를 위해 Temas 조직 전체 설정을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="343a6-113">Guest users follow Teams Org-wide settings for the coexistence Upgrade mode.</span></span> <span data-ttu-id="343a6-114">변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="343a6-114">This can't be changed.</span></span>

## <a name="licensing-for-guest-access"></a><span data-ttu-id="343a6-115">게스트 액세스에 대한 라이선스</span><span class="sxs-lookup"><span data-stu-id="343a6-115">Licensing for guest access</span></span>

<span data-ttu-id="343a6-116">게스트 액세스는 모든 Microsoft 365 Business Standard, Office 365 Enterprise 및 Office 365 Education 구독에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="343a6-116">Guest access is included with all Microsoft 365 Business Standard, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="343a6-117">Microsoft 365 또는 Office 365 추가 라이선스가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="343a6-117">No additional Microsoft 365 or Office 365 license is necessary.</span></span> <span data-ttu-id="343a6-118">Teams에서는 추가할 수 있는 게스트 수를 제한하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="343a6-118">Teams doesn't restrict the number of guests you can add.</span></span> <span data-ttu-id="343a6-119">그러나 테넌트에 추가할 수 있는 총 게스트 수는 Azure AD 라이선스가 허용하는 항목을 기반으로 합니다. 일반적으로 라이선스가 있는 사용자 당 게스트 수는 5 명입니다.</span><span class="sxs-lookup"><span data-stu-id="343a6-119">However, the total number of guests that can be added to your tenant is based on what your Azure AD licensing allows - usually 5 guests per licensed user.</span></span> <span data-ttu-id="343a6-120">자세한 내용은 [Azure AD B2B 공동 작업 라이선스](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="343a6-120">For more information, see [Azure AD B2B collaboration licensing](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>


> [!NOTE]
> <span data-ttu-id="343a6-121">Exchange Online Plan 2와 같이 독립실행형 Microsoft 365 또는 Office 365 구독 계획만 보유한 조직의 사용자는 Teams에서 동일한 조직에 속한 것으로 간주하기 때문에 조직에 게스트로 초대될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="343a6-121">Users in your organization who have standalone Microsoft 365 or Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="343a6-122">사용자가 Teams를 사용하려면 Microsoft 365 Business Standard, Office 365 Enterprise 또는 Office 365 Education 구독에 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="343a6-122">For these users to use Teams, they must be assigned an Microsoft 365 Business Standard, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="343a6-123">누가 게스트인가요?</span><span class="sxs-lookup"><span data-stu-id="343a6-123">Who is a guest?</span></span>

<span data-ttu-id="343a6-124">게스트는 직원, 학생 또는 조직의 구성원이 아닌 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="343a6-124">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="343a6-125">조직에 학교 또는 직장 계정을 가지고 있지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="343a6-125">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="343a6-126">예를 들어, 게스트에는 파트너, 공급 업체, 공급자 또는 컨설턴트 등이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="343a6-126">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="343a6-127">조직에 속하지 않은 사용자를 Teams에서 게스트로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="343a6-127">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="343a6-128">비즈니스 계정 (즉, Azure Active Directory 계정) 또는 소비자 전자 메일 계정 (Outlook.com, Gmail.com 또는 기타 사용자)이 있는 모든 사용자는 팀과 채널 환경에 대한 모든 액세스 권한을 가지고 Teams에 게스트로 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="343a6-128">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span>

<span data-ttu-id="343a6-129">게스트가 수행할 수 있는 작업에 대한 자세한 내용을 알아보려면 [Microsoft Teams의 게스트 액세스 권한](teams-dependencies.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="343a6-129">To learn more about what a guest can and can't do, read [Authorize guest access in Microsoft Teams](teams-dependencies.md).</span></span> <span data-ttu-id="343a6-130">또는 [팀 구성원 및 게스트 권한 비교](guest-experience.md#comparison-of-team-member-and-guest-capabilities)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="343a6-130">Or check out the [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities) table.</span></span> 

<span data-ttu-id="343a6-131">끝으로, Teams의 모든 게스트는 Microsoft 365 및 Office 365의 나머지 부분과 동일한 준수 및 감사 보호가 적용이 되며 Azure AD에서 안전하게 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="343a6-131">Finally, all guests in Teams are covered by the same compliance and auditing protection as the rest of Microsoft 365 and Office 365, and can be managed securely within Azure AD.</span></span>

## <a name="why-use-guest-access"></a><span data-ttu-id="343a6-132">게스트 액세스를 사용하는 이유는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="343a6-132">Why use guest access?</span></span>

<span data-ttu-id="343a6-133">게스트 액세스에서 Teams를 사용하는 조직은 회사 데이터를 완전하게 제어하면서 팀, 채널의 문서, 리소스, 채팅 및 응용 프로그램에 대한 액세스 권한을 파트너에게 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="343a6-133">With guest access, organizations that use Teams can provide access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> <span data-ttu-id="343a6-134">Teams의 모든 게스트는 Microsoft 365 및 Office 365의 나머지 부분과 동일한 준수 및 감사 보호가 적용이 되며 Azure AD에서 안전하게 게스트를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="343a6-134">All guests in Teams are covered by the same compliance and auditing protection as the rest of Microsoft 365 and Office 365, and guests can be managed securely within Azure AD.</span></span>  

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="343a6-135">게스트에 대한 제한 사항 이해</span><span class="sxs-lookup"><span data-stu-id="343a6-135">Understand the limitations for guests</span></span>

<span data-ttu-id="343a6-136">게스트 환경에는 디자인별로 제약 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="343a6-136">The guest experience has limitations by design.</span></span> <span data-ttu-id="343a6-137">문제를 해결하려면 게스트 환경을 이해하고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="343a6-137">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="343a6-138">예를 들어 Microsoft Teams에서 게스트가 사용할 수 없는 몇 가지 기능이 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="343a6-138">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="343a6-139">비즈니스용 OneDrive</span><span class="sxs-lookup"><span data-stu-id="343a6-139">OneDrive for Business</span></span>
- <span data-ttu-id="343a6-140">Teams 외부에서 사용자 검색</span><span class="sxs-lookup"><span data-stu-id="343a6-140">People search outside of Teams</span></span>
- <span data-ttu-id="343a6-141">일정, 예약된 모임 또는 모임 세부 정보</span><span class="sxs-lookup"><span data-stu-id="343a6-141">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="343a6-142">PSTN</span><span class="sxs-lookup"><span data-stu-id="343a6-142">PSTN</span></span>
- <span data-ttu-id="343a6-143">조직도</span><span class="sxs-lookup"><span data-stu-id="343a6-143">Organization chart</span></span>
- <span data-ttu-id="343a6-144">팀 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="343a6-144">Create or revise a team</span></span>
- <span data-ttu-id="343a6-145">팀 찾아보기</span><span class="sxs-lookup"><span data-stu-id="343a6-145">Browse for a team</span></span>
- <span data-ttu-id="343a6-146">개인 채팅에 파일 업로드</span><span class="sxs-lookup"><span data-stu-id="343a6-146">Upload files to a person-to-person chat</span></span>
- <span data-ttu-id="343a6-147">현재 Teams는 [Azure B2B에서 정의한대로](https://docs.microsoft.com/azure/active-directory/b2b/user-properties) 상태 1 및 상태 2 유형의 게스트 사용자만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="343a6-147">Currently, Teams supports only State 1 and State 2 types of guest users [as defined by Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)</span></span>

<span data-ttu-id="343a6-148">게스트가 Teams에서 수행할 수 있는 작업에 대한 전체 목록을 보려면 [팀 구성원 및 게스트 권한 비교](guest-experience.md#comparison-of-team-member-and-guest-capabilities)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="343a6-148">For a full list of what a guest can and can't do in Teams, see the [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities) table.</span></span> <span data-ttu-id="343a6-149">Microsoft 365 및 Office 365 수준에서 게스트 액세스에 대한 자세한 내용은 [Microsoft 365 그룹에 게스트 추가](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="343a6-149">To learn more about guest access at the Microsoft 365 and Office 365 levels, read [Adding guests to Microsoft 365 Groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>


## <a name="more-information"></a><span data-ttu-id="343a6-150">추가 정보</span><span class="sxs-lookup"><span data-stu-id="343a6-150">More information</span></span>

[<span data-ttu-id="343a6-151">비즈니스용 제품에 대한 고객 지원 센터 - 관리자 도움말</span><span class="sxs-lookup"><span data-stu-id="343a6-151">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)  
[<span data-ttu-id="343a6-152">Microsoft 365 그룹에서 게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="343a6-152">Guest access in Microsoft 365 Groups</span></span>](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
