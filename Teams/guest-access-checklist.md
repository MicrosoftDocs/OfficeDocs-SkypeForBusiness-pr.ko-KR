---
title: Microsoft 팀 게스트 액세스 검사 목록
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: 이 검사 목록을 사용 하 여 Microsoft 팀에서 게스트 액세스를 설정할 수 있습니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b60b0e5f0972d862ec1b945f1b267b04faae9a8a
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41833258"
---
<a name="microsoft-teams-guest-access-checklist"></a><span data-ttu-id="bd57f-103">Microsoft 팀 게스트 액세스 검사 목록</span><span class="sxs-lookup"><span data-stu-id="bd57f-103">Microsoft Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="bd57f-104">Microsoft 팀에서 게스트 액세스를 설정 하 고 구성 하는 데 도움이 되는 검사 목록을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-104">Use this checklist to help you turn on and configure guest access in Microsoft Teams.</span></span> <span data-ttu-id="bd57f-105">이러한 변경 작업을 수행 하려면 전역 관리자 또는 팀 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-105">You need to be a Global Administrator or a Teams Administrator to make these changes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd57f-106">변경 내용이 적용 되려면 24 시간까지 기다려야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-106">You may have to wait up to 24 hours for your changes to take effect.</span></span> 

<span data-ttu-id="bd57f-107">이 짧은 비디오를 시청 하세요 (5:31 분). 팀을 포함 하 여 Microsoft 365에서 게스트 액세스를 설정 하는 방법을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="bd57f-107">Watch this short video (5:31 minutes) to see how to turn on guest access throughout Microsoft 365, including Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a><span data-ttu-id="bd57f-108">1 단계: 조직 전체 수준에서 게스트 액세스 켜기 팀</span><span class="sxs-lookup"><span data-stu-id="bd57f-108">Step 1: Turn on guest access at the Teams org-wide level</span></span>

<span data-ttu-id="bd57f-109">게스트 액세스를 설정 하려면 **Microsoft 팀 관리 센터로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-109">To turn on guest access, go to the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="bd57f-110">팀 관리 센터에서 **조직 전체 설정** > **게스트 액세스**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-110">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="bd57f-111">**Microsoft 팀에서 게스트 액세스 허용** 을 **설정으로 전환 합니다.**</span><span class="sxs-lookup"><span data-stu-id="bd57f-111">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![팀 설정의 예를 보여 주는 스크린샷](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="bd57f-113">이 페이지에서 게스트에 대 한 **통화**, **모임**및 **메시징** 설정을 설정 하거나 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-113">On this same page, turn on or turn off **Calling**, **Meeting**, and **Messaging** settings for guests.</span></span>
4. <span data-ttu-id="bd57f-114">**저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-114">Click **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="bd57f-115">Azure Active Directory, SharePoint Online 및 Office 365 그룹에서 기본 설정을 사용 하는 경우 게스트 액세스 구성이 완료 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-115">If you're using default settings in Azure Active Directory, SharePoint Online, and Office 365 Groups, you may be done configuring guest access.</span></span> <span data-ttu-id="bd57f-116">이 경우 나머지 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-116">In this case, you can skip the rest of the steps.</span></span> <span data-ttu-id="bd57f-117">확실 하지 않은 경우 또는 AAD, SharePoint Online 또는 Office 365 그룹에 대 한 사용자 지정 설정을 사용 하는 경우이 검사 목록의 나머지 단계를 계속 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-117">If you're not sure, or if you're using custom settings for AAD, SharePoint Online, or Office 365 Groups, continue with the rest of the steps in this checklist.</span></span>

## <a name="step-2-configure-azure-ad-business-to-business-settings"></a><span data-ttu-id="bd57f-118">2 단계: Azure AD business 비즈니스에 대 한 설정 구성</span><span class="sxs-lookup"><span data-stu-id="bd57f-118">Step 2: Configure Azure AD business-to-business settings</span></span>

<span data-ttu-id="bd57f-119">팀에서 게스트 액세스를 지 원하는 Azure AD 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-119">These are the Azure AD settings that support guest access in Teams.</span></span> <span data-ttu-id="bd57f-120">이러한 설정이 구성 되 면 팀에서 게스트를 [추가](add-guests.md) 하 고 [관리할](manage-guests.md) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-120">Once these settings are configured, you'll be able to [add](add-guests.md) and [manage guests](manage-guests.md) in Teams.</span></span>

1. <span data-ttu-id="bd57f-121">테 넌 트 관리자로 [Azure 포털](https://portal.azure.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-121">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="bd57f-122">**Azure Active Directory** > **사용자** > **사용자 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-122">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="bd57f-123">**외부 사용자**아래에서 **외부 공동 작업 설정 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-123">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="bd57f-124">**외부 공동 작업 설정은** **조직 관계** 페이지 에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-124">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="bd57f-125">Azure Active Directory의 **관리**에서 **조직 관계** > **설정**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-125">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="bd57f-126">**외부 공동 작업 설정** 페이지에서 사용 하도록 설정할 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-126">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

    - <span data-ttu-id="bd57f-127">**게스트 사용자 권한이 제한 됨**:이 정책은 디렉터리의 게스트에 대 한 사용 권한을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-127">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="bd57f-128">**예** 를 선택 하 여 사용자, 그룹 또는 기타 디렉터리 리소스 열거와 같은 특정 디렉터리 작업에서 게스트를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-128">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="bd57f-129">게스트를 사용 하 여 디렉터리 데이터에 대 한 액세스 권한을 다른 사용자와 동일 하 게 지정 하려면 ( **아니요** )를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-129">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
     - <span data-ttu-id="bd57f-130">**게스트 inviter 역할의 관리자와 사용자는 초대할 수 있습니다**. "게스트 inviter" 역할의 관리자와 사용자가 게스트를 초대 하도록 허용 하려면이 정책을 **Yes**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-130">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
     - <span data-ttu-id="bd57f-131">**회원 초대 가능**: 디렉토리의 관리자가 아닌 회원이 손님을 초대할 수 있게 하려면 이 정책을 **예**(권장)로 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="bd57f-131">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes** (recommended).</span></span> <span data-ttu-id="bd57f-132">관리자만 게스트를 추가할 수 있게 하려는 경우 이 정책을 **아니오**로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-132">If you prefer that only admins be able to add guests, you can set this policy to **No**.</span></span> <span data-ttu-id="bd57f-133">**아니오**로 설정할 경우 관리자가 아닌 Teams 소유자의 게스트 환경이 제한됨에 유의하십시오. 이 소유자들은 AAD에 이미 추가된 Teams에만 게스트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-133">Keep in mind that setting **No** will limit the guest experience for non-admin teams owners; they'll only be able to add guests in Teams that have already been added in AAD by the admin.</span></span>
     - <span data-ttu-id="bd57f-134">**게스트 초대**: 게스트가 다른 게스트를 초대할 수 있도록 하려면이 정책을 **Yes**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-134">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
         > [!IMPORTANT]
         > <span data-ttu-id="bd57f-135">현재 Teams는 게스트 초대자 역할을 지원하지 않으므로 **참석자를 초대 할 수 있음**으로 **설정**하더라도 손님은 Teams에서 다른 참석자를 초대할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-135">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
     - <span data-ttu-id="bd57f-136">**게스트를 위한 전자 메일 1 회 암호 사용 (미리 보기)**: 일회성 암호 기능에 대 한 자세한 내용은 일회용 [암호 기반 전자 메일 인증 (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bd57f-136">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
     - <span data-ttu-id="bd57f-137">**공동 작업 제한 사항**: 특정 도메인에 대 한 초대를 허용 하거나 차단 하는 방법에 대 한 자세한 내용은 [특정 조직의 B2B 사용자에 대 한 초대 허용 또는 차단](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bd57f-137">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
        > [!NOTE]
        > <span data-ttu-id="bd57f-138">공동 작업 제한 사항은 [B2B 외부 공동 작업 사용 및 게스트 초대를 할 수 있는 사용자 관리](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bd57f-138">For collaboration restrictions, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>
      
    <span data-ttu-id="bd57f-139">게스트를 초대할 수 있는 사용자를 제어하는 방법에 대한 자세한 내용은 [Azure Active Directory B2B 공동 작업에 대한 초대 위임](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-139">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

## <a name="step-3-configure-office-365-groups"></a><span data-ttu-id="bd57f-140">3 단계: Office 365 그룹 구성</span><span class="sxs-lookup"><span data-stu-id="bd57f-140">Step 3: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="bd57f-141">Microsoft 365 관리 센터에서 **설정** > **설정**으로 이동 하 여 **서비스**를 클릭 한 다음 **Office 365 그룹**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-141">In the Microsoft 365 admin center, go to **Settings** > **Settings**, click **Services**, and then select **Office 365 Groups**.</span></span>

     ![스크린샷에는 Office 365 Groups 설정이 나와 있습니다.](media/guest-access-checklist-services-settings.png)
2. <span data-ttu-id="bd57f-143">**조직 외부 회원 그룹 구성원에 게 그룹 콘텐츠 액세스 허용** 확인란을 선택 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-143">Make sure that the **Let group members outside the organization access group content** check box is selected.</span></span> <span data-ttu-id="bd57f-144">이 설정을 선택 하지 않으면 게스트가 그룹 컨텐트에 액세스할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-144">If this setting is not selected, guests won't be able to access any group content.</span></span>

    ![스크린샷에는 Office 365 Groups 설정이 나와 있습니다.](media/guest-access-checklist-office365.png)
3. <span data-ttu-id="bd57f-146">**그룹 소유자가 조직 외부 사람을 그룹에 추가** 확인란을 선택 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-146">Make sure that the **Let group owners add people outside the organization to groups** check box is selected.</span></span> <span data-ttu-id="bd57f-147">이 설정을 선택 하지 않으면 팀 소유자가 새 게스트를 추가할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-147">If this setting is not selected, team owners won't be able to add new guests.</span></span> <span data-ttu-id="bd57f-148">게스트 액세스를 지원 하려면 최소한이 설정이 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-148">At a minimum, this setting must be on to support guest access.</span></span>

<span data-ttu-id="bd57f-149">이러한 설정을 구성 하는 방법에 대 한 자세한 지침은 [office 365 그룹에서 게스트 액세스 관리](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) 및 [office 365 그룹의 게스트 액세스 제어](Teams-dependencies.md#control-guest-access-in-office-365-groups)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bd57f-149">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>

## <a name="step-4-configure-sharing-in-office-365"></a><span data-ttu-id="bd57f-150">4 단계: Office 365에서 공유 구성</span><span class="sxs-lookup"><span data-stu-id="bd57f-150">Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="bd57f-151">사용자가 게스트를 추가할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-151">Make sure that users can add guests.</span></span> <span data-ttu-id="bd57f-152">방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-152">Here's how:</span></span>

1. <span data-ttu-id="bd57f-153">Microsoft 365 관리 센터에서 **설정** > **설정**으로 이동 하 여 **보안 & 개인 정보**를 클릭 한 다음 **공유**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-153">In the Microsoft 365 admin center, go to **Settings** > **Settings**, click **Security & privacy**, and then select **Sharing**.</span></span>

     ![스크린샷에서는 서비스 설정의 예를 보여 줍니다.](media/guest-access-checklist-security-privacy-settings.png)
 
2. <span data-ttu-id="bd57f-155">**사용자가이 조직에 새 게스트를 추가 하도록 허용** 확인란을 선택 하 고 **변경 내용 저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-155">Select the **Let users add new guests to this organization** check box, and then click **Save changes**.</span></span>

     ![공유 설정의 예를 보여 주는 스크린샷](media/guest-access-checklist-sharing-setting.png)
 
    > [!NOTE]
    > <span data-ttu-id="bd57f-157">이 설정은 회원 들이 Azure AD의**외부 사용자** **설정** > 에서 설정을 **초대할 수** 있는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-157">This setting is equivalent to the **Members can invite** setting in **User settings** > **External users** in Azure AD.</span></span>  

## <a name="step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="bd57f-158">5 단계: SharePoint에서 공유 설정 확인</span><span class="sxs-lookup"><span data-stu-id="bd57f-158">Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="bd57f-159">Microsoft 365 관리 센터에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-159">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="bd57f-160">**관리 센터**에서 **SharePoint**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-160">Under **Admin centers**, select  **SharePoint**.</span></span>
3. <span data-ttu-id="bd57f-161">새 SharePoint 관리 센터의 **사이트**에서 **활성 사이트**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-161">In the new SharePoint admin center,  under **Sites**, select **Active sites**.</span></span>

    ![SharePoint 관리 센터의 활성 사이트](media/guest-access-checklist-SPOSettings0.png)

3. <span data-ttu-id="bd57f-163">사이트를 선택한 다음 **공유**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-163">Select the site, and then click **Sharing**.</span></span>
4. <span data-ttu-id="bd57f-164">이 옵션이 **사용자** 또는 **신규 및 기존 게스트로**설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-164">Make sure that the option is set to **Anyone** or **New and existing guests**.</span></span>

     ![SharePoint Online 설정/해제의 예를 보여 주는 스크린샷](media/guest-access-checklist-SPOSettings1.png)

## <a name="step-6-set-up-guest-user-permissions"></a><span data-ttu-id="bd57f-166">6 단계: 게스트 사용자 권한 설정</span><span class="sxs-lookup"><span data-stu-id="bd57f-166">Step 6: Set up guest user permissions</span></span>

<span data-ttu-id="bd57f-167">팀 응용 프로그램 개별 팀 수준에서 게스트가 채널을 만들거나 업데이트 하거나 삭제할 수 있는지 여부를 제어 하는 게스트 권한을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-167">In the Teams application, at the individual team level, configure guest permissions that control whether guests can create, update, or delete channels.</span></span> <span data-ttu-id="bd57f-168">팀 관리자는 물론 팀 소유자는 이러한 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd57f-168">Teams admins as well as team owners can configure these settings.</span></span>

![팀/채널 설정의 예를 보여 주는 스크린샷](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="bd57f-170">게스트 액세스에 대 한 자세한 내용은 [팀에서 게스트 액세스](guest-access.md) 및 Microsoft 팀에 대 한 [게스트 액세스 설정 또는 해제](set-up-guests.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bd57f-170">To learn more about guest access, see [Guest access in Teams](guest-access.md) and [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="bd57f-171">해결사</span><span class="sxs-lookup"><span data-stu-id="bd57f-171">Troubleshooting</span></span>

<span data-ttu-id="bd57f-172">팀에서 게스트 액세스를 설정 하거나 게스트를 추가 하는 데 문제가 있는 경우 다음 리소스를 사용 하 여 도움을 받으세요.</span><span class="sxs-lookup"><span data-stu-id="bd57f-172">If you have problems setting up guest access or adding guests in Teams, use these resources to help you:</span></span>

[<span data-ttu-id="bd57f-173">Microsoft 팀의 게스트 액세스 문제 해결</span><span class="sxs-lookup"><span data-stu-id="bd57f-173">Troubleshoot problems with guest access in Microsoft Teams</span></span>](troubleshoot-guest-access.md)

[<span data-ttu-id="bd57f-174">팀 문제 해결</span><span class="sxs-lookup"><span data-stu-id="bd57f-174">Teams troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)
