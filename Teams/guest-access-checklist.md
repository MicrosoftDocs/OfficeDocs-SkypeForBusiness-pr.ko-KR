---
title: Microsoft 팀 게스트 액세스 검사 목록
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
description: 이 검사 목록을 사용 하 여 Microsoft 팀에서 게스트 액세스를 설정할 수 있습니다.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 09a6ec1f60ca4bfc39dbeb5ba1829330c3413560
ms.sourcegitcommit: a78fee3cad5b58bf41dd014a79f4316cf310c8d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2019
ms.locfileid: "36185171"
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="3c4a0-103">팀 게스트 액세스 검사 목록</span><span class="sxs-lookup"><span data-stu-id="3c4a0-103">Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="3c4a0-104">조직의 기본 설정에 따라 Microsoft 팀에서 게스트 액세스 기능을 사용 하도록 설정 하 고 구성 하는 데 도움이 되는 검사 목록을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-104">Use this checklist to help you enable and configure the guest access feature in Microsoft Teams according to the preferences of your organization.</span></span>

> [!NOTE] 
> <span data-ttu-id="3c4a0-105">공동 작업 제한 사항은 [B2B 외부 공동 작업 사용 및 게스트 초대를 할 수 있는 사용자 관리를](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-105">For collaboration restrictions see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="3c4a0-106">게스트의 제한 사항 이해</span><span class="sxs-lookup"><span data-stu-id="3c4a0-106">Understand the limitations for guests</span></span>

<span data-ttu-id="3c4a0-107">게스트 환경에는 설계상의 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-107">The guest experience has limitations by design.</span></span> <span data-ttu-id="3c4a0-108">문제가 아닌 항목을 해결 하기 위해 게스트 환경을 이해 하 고 있는지 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-108">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="3c4a0-109">예를 들어 Microsoft 팀의 게스트에는 사용할 수 없는 몇 가지 기능이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-109">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="3c4a0-110">비즈니스용 OneDrive</span><span class="sxs-lookup"><span data-stu-id="3c4a0-110">OneDrive for Business</span></span>
- <span data-ttu-id="3c4a0-111">팀 외부에서 사용자 검색</span><span class="sxs-lookup"><span data-stu-id="3c4a0-111">People search outside of Teams</span></span>
- <span data-ttu-id="3c4a0-112">일정, 예약 된 모임 또는 모임 세부 정보</span><span class="sxs-lookup"><span data-stu-id="3c4a0-112">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="3c4a0-113">PSTN</span><span class="sxs-lookup"><span data-stu-id="3c4a0-113">PSTN</span></span>
- <span data-ttu-id="3c4a0-114">조직도</span><span class="sxs-lookup"><span data-stu-id="3c4a0-114">Organization chart</span></span>
- <span data-ttu-id="3c4a0-115">팀 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="3c4a0-115">Create or revise a team</span></span>
- <span data-ttu-id="3c4a0-116">팀 찾아보기</span><span class="sxs-lookup"><span data-stu-id="3c4a0-116">Browse for a team</span></span>
- <span data-ttu-id="3c4a0-117">사용자 간 채팅에 파일 업로드</span><span class="sxs-lookup"><span data-stu-id="3c4a0-117">Upload files to a person-to-person chat</span></span>
- <span data-ttu-id="3c4a0-118">게스트는 사용자의 전체 전자 메일 ID를 알고 있는 경우에도 사용자가 팀 외부에서 검색 하 고 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-118">Guests can still search and find users (outside their team) if they know the user's full email ID.</span></span> <span data-ttu-id="3c4a0-119">이를 방지 하기 위해 IT 관리자는 게스트를 고유한 가상 GAL으로 제한할 수 있는 [범위 디렉터리 검색](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search) 등의 패턴을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-119">To prevent this, IT admins can use patterns like [scoped directory search](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search) that have the ability to restrict Guests into their own virtual GAL.</span></span>

<span data-ttu-id="3c4a0-120">자세한 내용은 [게스트 환경](guest-experience.md) 및 [Office 365 그룹의 게스트 액세스에](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-120">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 Groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>

### <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="3c4a0-121">게스트 액세스와 외부 액세스 (페더레이션) 비교</span><span class="sxs-lookup"><span data-stu-id="3c4a0-121">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

> [!NOTE] 
> <span data-ttu-id="3c4a0-122">현재 Microsoft 팀은 게스트 inviter 역할을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-122">Currently, Microsoft Teams does not support the guest inviter role.</span></span> <span data-ttu-id="3c4a0-123">Microsoft 팀에서 작업 하려면 "구성원을 초대할 수 있습니다." 토글을 게스트 액세스에 대해 "예"로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-123">At a minimum the "members can invite" toggle must be set to "Yes" for guest access to work in Microsoft Teams.</span></span> <span data-ttu-id="3c4a0-124">"구성원이" 초대 가능 "을" 아니요 "로 설정한 다음 Office 365 그룹 및 Microsoft 팀에서 게스트 액세스를 사용 하도록 설정 하면 관리자가 디렉터리에 대 한 게스트 초대를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-124">If you set "members can invite" to "No" and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="3c4a0-125">Guest가 디렉터리에 있으면 팀 소유자 인 관리자가 아닌 구성원에 따라 팀에 추가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-125">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="3c4a0-126">게스트가 라이센스 오류를 보고 있는 경우</span><span class="sxs-lookup"><span data-stu-id="3c4a0-126">If your guests are seeing license errors</span></span>

<span data-ttu-id="3c4a0-127">Microsoft 팀의 게스트 액세스는 Azure AD (azure Active Directory) Business to Business (B2B) 및 해당 라이선스 모델을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-127">Guest access in Microsoft Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="3c4a0-128">라이선스 오류가 표시 되는 경우 사용자가 조직에 게스트를 초대할 수 있도록 [B2B 라이선스 지침](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) 을 읽고 조직의 라이선스 요구 사항을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-128">If you’re seeing licensing errors, make sure to read the [B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to understand the licensing requirements your organization has so that your users are able to invite guests to your organization.</span></span>

<span data-ttu-id="3c4a0-129">몇 가지 주의할 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-129">A few things to remember:</span></span>

- <span data-ttu-id="3c4a0-130">게스트는 조직 외부의 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-130">Guests are users outside your organization.</span></span> <span data-ttu-id="3c4a0-131">직원, 출장 대리점, 출장 업체 등은 게스트로 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-131">Your employees, onsite contractors, onsite agents, and so on can't be added as guests.</span></span> <span data-ttu-id="3c4a0-132">계열사에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-132">The same applies to your affiliates.</span></span>
- <span data-ttu-id="3c4a0-133">초청 기관에 대해 게스트 라이선스가 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-133">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="3c4a0-134">필요한 라이선스 수를 계산할 때이를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-134">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="3c4a0-135">라이선스는 초대 된 게스트가 다른 Office 365 테 넌 트에서 온 것인지 또는 개인 전자 메일 주소를 사용 하는 조직에 게 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-135">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a><span data-ttu-id="3c4a0-136">□ 단계 1: Azure AD business 비즈니스에서 설정 구성</span><span class="sxs-lookup"><span data-stu-id="3c4a0-136">□  Step 1: Configure settings in Azure AD business-to-business</span></span>

1. <span data-ttu-id="3c4a0-137">테 넌 트 관리자로 [Azure 포털](https://portal.azure.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-137">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="3c4a0-138">**Azure Active Directory** > **사용자** > **사용자 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-138">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="3c4a0-139">**외부 사용자**아래에서 **외부 공동 작업 설정 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-139">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="3c4a0-140">**외부 공동 작업 설정은** **조직 관계** 페이지 에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-140">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="3c4a0-141">Azure Active Directory의 **관리**에서 **조직 관계** > **설정**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-141">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="3c4a0-142">**외부 공동 작업 설정** 페이지에서 사용 하도록 설정할 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-142">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

  - <span data-ttu-id="3c4a0-143">**게스트 사용자 권한이 제한 됨**:이 정책은 디렉터리의 게스트에 대 한 사용 권한을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-143">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="3c4a0-144">**예** 를 선택 하 여 사용자, 그룹 또는 기타 디렉터리 리소스 열거와 같은 특정 디렉터리 작업에서 게스트를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-144">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="3c4a0-145">게스트를 사용 하 여 디렉터리 데이터에 대 한 액세스 권한을 다른 사용자와 동일 하 게 지정 하려면 ( **아니요** )를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-145">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
   - <span data-ttu-id="3c4a0-146">**게스트 inviter 역할의 관리자와 사용자는 초대할 수 있습니다**. "게스트 inviter" 역할의 관리자와 사용자가 게스트를 초대 하도록 허용 하려면이 정책을 **Yes**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-146">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
   - <span data-ttu-id="3c4a0-147">**구성원 초대 가능**: 해당 디렉터리의 관리자가 아닌 구성원이 게스트를 초대 하도록 허용 하려면이 정책을 **예로**설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-147">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes**.</span></span>
   
       > [!NOTE]
       > <span data-ttu-id="3c4a0-148">구성원을 **No** 에 **초대할 수** 있고 Office 365 그룹 및 Microsoft 팀에서 게스트 액세스를 사용 하도록 설정한 경우 관리자는 디렉터리에 대 한 게스트 초대를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-148">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="3c4a0-149">Guest가 디렉터리에 있으면 팀 소유자 인 관리자가 아닌 구성원에 따라 팀에 추가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-149">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span> <span data-ttu-id="3c4a0-150">자세한 내용은 [Microsoft 팀에서 게스트 액세스 권한 부여](Teams-dependencies.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-150">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
   
   - <span data-ttu-id="3c4a0-151">**게스트 초대**: 게스트가 다른 게스트를 초대할 수 있도록 하려면이 정책을 **Yes**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-151">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
   - <span data-ttu-id="3c4a0-152">**게스트를 위한 전자 메일 1 회 암호 사용 (미리 보기)**: 일회성 암호 기능에 대 한 자세한 내용은 일회용 [암호 기반 전자 메일 인증 (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-152">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
   - <span data-ttu-id="3c4a0-153">**공동 작업 제한 사항**: 특정 도메인에 대 한 초대를 허용 하거나 차단 하는 방법에 대 한 자세한 내용은 [특정 조직의 B2B 사용자에 대 한 초대 허용 또는 차단](allow-deny-list.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-153">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](allow-deny-list.md).</span></span>

## <a name="-step-2-configure-office-365-groups"></a><span data-ttu-id="3c4a0-154">□ 단계 2: Office 365 그룹 구성</span><span class="sxs-lookup"><span data-stu-id="3c4a0-154">□ Step 2: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="3c4a0-155">Microsoft 365 관리 센터에서 **설정** > **서비스 & 추가 기능** > **Office 365 그룹**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-155">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="3c4a0-156">조직에서 그룹 **구성원을 액세스할 수 있도록 그룹 콘텐츠** 를 설정 하도록 허용 \*\*\*\* 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-156">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="3c4a0-157">이 설정이 해제 되어 있으면 게스트는 그룹 콘텐츠에 액세스할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-157">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="3c4a0-158">**그룹 소유자가 조직 외부의 사용자를 그룹에 추가 하도록 허용** 하는 \*\*\*\* 것이 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-158">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="3c4a0-159">이 설정을 끄면 팀 소유자가 새 게스트를 추가할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-159">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="3c4a0-160">게스트 액세스를 지원 하려면 최소한이 설정이 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-160">At a minimum, this setting must be On to support guest access.</span></span>

     ![스크린샷에서는 Office 365 그룹을 표시 하거나 숨깁니다.](media/guest-access-checklist-office365.png)

<span data-ttu-id="3c4a0-162">이러한 설정을 구성 하는 방법에 대 한 자세한 지침은 [office 365 그룹에서 게스트 액세스 관리](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) 및 [office 365 그룹의 게스트 액세스 제어](Teams-dependencies.md#control-guest-access-in-office-365-groups)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-162">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="3c4a0-163">□ 단계 3: 테 넌 트 수준에서 게스트 액세스를 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="3c4a0-163">□ Step 3: Enable guest access at the tenant level</span></span>

<span data-ttu-id="3c4a0-164">최소한 microsoft **팀 관리 센터**에서 microsoft 팀에 대 한 게스트 액세스를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-164">At a minimum, you must turn on guest access for Microsoft Teams under the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="3c4a0-165">팀 관리 센터에서 **조직 전체 설정** > **게스트 액세스**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-165">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="3c4a0-166">**Microsoft 팀에서 게스트 액세스 허용** 을 설정으로 전환 \*\*\*\* 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-166">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![팀 설정의 예를 보여 주는 스크린샷](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="3c4a0-168">이 페이지에서 필요한 다른 게스트 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-168">On this same page, configure any other guest settings that you require.</span></span>
4. <span data-ttu-id="3c4a0-169">**저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-169">Click **Save**.</span></span>

<span data-ttu-id="3c4a0-170">자세한 지침은 [Microsoft 팀에 대 한 게스트 액세스 설정 또는 해제](set-up-guests.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-170">For detailed instructions, see [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="--step-4-configure-sharing-in-office-365"></a><span data-ttu-id="3c4a0-171">□ 단계 4: Office 365에서 공유 구성</span><span class="sxs-lookup"><span data-stu-id="3c4a0-171">□  Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="3c4a0-172">사용자가 게스트를 추가할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-172">Make sure that users can add guests.</span></span> <span data-ttu-id="3c4a0-173">방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-173">Here's how:</span></span>

1. <span data-ttu-id="3c4a0-174">Microsoft 365 관리 센터에서 **설정** > **보안 & 개인 정보**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-174">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![스크린샷에서는 서비스 설정의 예를 보여 줍니다.](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="3c4a0-176">**공유**에서 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-176">In **Sharing**, select **Edit**.</span></span>

     ![공유 설정의 예를 보여 주는 스크린샷](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="3c4a0-178">**사용자가이 조직에 새 게스트를 추가할 수 있도록 허용** 을 선택한 다음 **저장**을 클릭 합니다. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="3c4a0-178">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![공유 설정의 예를 보여 주는 스크린샷](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> <span data-ttu-id="3c4a0-180">이 설정은 회원 들이 Azure AD의**외부 사용자** **설정** > 에서 설정을 **초대할 수** 있는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-180">This setting is equivalent to the **Members can invite** setting in  **User settings** > **External users**  in Azure AD.</span></span>  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="3c4a0-181">□ 단계 5: SharePoint에서 공유 설정 확인</span><span class="sxs-lookup"><span data-stu-id="3c4a0-181">□ Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="3c4a0-182">Microsoft 365 관리 센터에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-182">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="3c4a0-183">**관리 센터**를 클릭 한 다음 **SharePoint**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-183">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="3c4a0-184">SharePoint 관리 센터에서 **공유**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-184">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="3c4a0-185">**조직 외부 공유 허용 안 함** 옵션이 선택 되어 *있지* 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-185">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![스크린샷에는 SparePoint 온라인 설정 토글의 예가 나와 있습니다.](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a><span data-ttu-id="3c4a0-187">□ 단계 6: 채널에 특정 설정 사용</span><span class="sxs-lookup"><span data-stu-id="3c4a0-187">□ Step 6: Enable specific settings for channels</span></span> 

<span data-ttu-id="3c4a0-188">팀 응용 프로그램 개별 팀 수준에서 게스트가 채널을 만들고 업데이트 하 고 삭제할 수 있도록 게스트 권한을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-188">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="3c4a0-189">관리자 외에도, 팀 소유자는이 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-189">In addition to admins,  team owners can configure this setting.</span></span>

![팀/채널 설정의 예를 보여 주는 스크린샷](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="3c4a0-191">방법 비디오를 비롯 한 자세한 내용은 [Microsoft 팀의 게스트 액세스](guest-access.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-191">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="3c4a0-192">해결사</span><span class="sxs-lookup"><span data-stu-id="3c4a0-192">Troubleshooting</span></span>

<span data-ttu-id="3c4a0-193">Microsoft 팀에서 게스트를 추가 하는 데 문제가 있는 경우 [게스트 액세스 문제 해결 가이드](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-193">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


