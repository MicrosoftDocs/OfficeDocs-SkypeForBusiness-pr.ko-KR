---
title: Microsoft Teams 게스트 액세스 검사 목록
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: Microsoft 팀에서 전역 또는 팀 관리자로 게스트 액세스를 설정 하 고 구성 하는 방법에 대해 알아봅니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ee7fd8e7fc85e345df3e29de99e16292c6ef7e1f
ms.sourcegitcommit: bdf6cea0face74809ad3b8b935bc14ad60b3bb35
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/21/2020
ms.locfileid: "45201052"
---
<a name="microsoft-teams-guest-access-checklist"></a><span data-ttu-id="8fd17-103">Microsoft Teams 게스트 액세스 검사 목록</span><span class="sxs-lookup"><span data-stu-id="8fd17-103">Microsoft Teams guest access checklist</span></span>
=========================================

<span data-ttu-id="8fd17-104">이 검사 목록을 사용하여 Microsoft Teams에서 게스트 액세스를 설정하고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-104">Use this checklist to help you turn on and configure guest access in Microsoft Teams.</span></span> <span data-ttu-id="8fd17-105">이렇게 변경하려면 사용자가 전역 관리자 또는 Teams 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-105">You need to be a Global Administrator or a Teams Administrator to make these changes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8fd17-106">변경 내용이 적용 되려면 몇 시간 정도 기다려야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-106">You may have to wait a few hours for your changes to take effect.</span></span> 

<span data-ttu-id="8fd17-107">이 짧은 비디오(5분 31초)를 시청하여 Teams와 같은 Microsoft 365를 통해 게스트 액세스를 설정하는 방법에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="8fd17-107">Watch this short video (5:31 minutes) to see how to turn on guest access throughout Microsoft 365, including Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a><span data-ttu-id="8fd17-108">1단계: 조직 전체 수준에서 게스트 액세스 설정</span><span class="sxs-lookup"><span data-stu-id="8fd17-108">Step 1: Turn on guest access at the Teams org-wide level</span></span>

<span data-ttu-id="8fd17-109">게스트 액세스를 설정 하려면 관리 센터로 이동 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-109">To turn on guest access, go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span> 

1. <span data-ttu-id="8fd17-110">Teams 관리 센터에서 **조직 전체 설정** > **게스트 액세스**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-110">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="8fd17-111">**Microsoft Teams에서 게스트 액세스 허용** 스위치를 **켬**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-111">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Teams 설정 토글의 예를 보여주는 스크린샷](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="8fd17-113">이 페이지에서 게스트의 **통화**, **모임** 및 **메시징** 설정을 켜거나 끕니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-113">On this same page, turn on or turn off **Calling**, **Meeting**, and **Messaging** settings for guests.</span></span>
4. <span data-ttu-id="8fd17-114">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-114">Click **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="8fd17-115">Azure Active Directory, SharePoint Online 및 Microsoft 365 그룹에서 기본 설정을 사용 하는 경우 게스트 액세스 구성이 완료 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-115">If you're using default settings in Azure Active Directory, SharePoint Online, and Microsoft 365 Groups, you may be done configuring guest access.</span></span> <span data-ttu-id="8fd17-116">이 경우 나머지 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-116">In this case, you can skip the rest of the steps.</span></span> <span data-ttu-id="8fd17-117">확실 하지 않은 경우 또는 AAD, SharePoint Online 또는 Microsoft 365 그룹에 대 한 사용자 지정 설정을 사용 하는 경우이 검사 목록의 나머지 단계를 계속 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-117">If you're not sure, or if you're using custom settings for AAD, SharePoint Online, or Microsoft 365 Groups, continue with the rest of the steps in this checklist.</span></span>

## <a name="step-2-configure-azure-ad-business-to-business-settings"></a><span data-ttu-id="8fd17-118">2단계: Azure AD B2B 설정</span><span class="sxs-lookup"><span data-stu-id="8fd17-118">Step 2: Configure Azure AD business-to-business settings</span></span>

<span data-ttu-id="8fd17-119">다음은 Teams에서 게스트 액세스를 지원하는 Azure AD 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-119">These are the Azure AD settings that support guest access in Teams.</span></span> <span data-ttu-id="8fd17-120">이러한 설정을 구성한 후에는 Teams에서 게스트를 [추가](add-guests.md)하고 [관리](manage-guests.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-120">Once these settings are configured, you'll be able to [add](add-guests.md) and [manage guests](manage-guests.md) in Teams.</span></span>

1. <span data-ttu-id="8fd17-121">테넌트 관리자로 [Azure Portal](https://portal.azure.com)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-121">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="8fd17-122">**Azure Active Directory** > **사용자** > **사용자 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-122">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="8fd17-123">**외부 사용자**에서 **외부 공동 작업 관리 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-123">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="8fd17-124">**조직 관계** 페이지에서 **외부 공동 작업 설정**도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-124">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="8fd17-125">Azure Active Directory의 **관리**에서 **조직 관계** > **설정**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-125">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="8fd17-126">**외부 공동 작업 설정** 페이지에서 사용하려는 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-126">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

    - <span data-ttu-id="8fd17-127">**게스트 사용자의 사용 권한 제한**: 이 정책은 디렉터리에서 게스트의 사용 권한을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-127">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="8fd17-128">**예**를 선택하여 사용자, 그룹 또는 기타 디렉터리 리소스 열거와 같이 특정 디렉터리 작업에서 게스트를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-128">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="8fd17-129">**아니요**를 선택하여 게스트에게 사용자 디렉터리의 일반 사용자와 같은 액세스 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-129">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
     - <span data-ttu-id="8fd17-130">**게스트 초대자 역할의 관리자 및 사용자 초대 가능**: "게스트 초대자" 역할의 관리자가 게스트를 초대하도록 허용하려면 이 정책을 **예**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-130">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
     - <span data-ttu-id="8fd17-131">**회원 초대 가능**: 디렉토리의 관리자가 아닌 회원이 손님을 초대할 수 있게 하려면 이 정책을 **예**(권장)로 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="8fd17-131">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes** (recommended).</span></span> <span data-ttu-id="8fd17-132">관리자만 게스트를 추가할 수 있게 하려는 경우 이 정책을 **아니오**로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-132">If you prefer that only admins be able to add guests, you can set this policy to **No**.</span></span> <span data-ttu-id="8fd17-133">**아니오**로 설정할 경우 관리자가 아닌 Teams 소유자의 게스트 환경이 제한됨에 유의하십시오. 이 소유자들은 AAD에 이미 추가된 Teams에만 게스트를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-133">Keep in mind that setting **No** will limit the guest experience for non-admin teams owners; they'll only be able to add guests in Teams that have already been added in AAD by the admin.</span></span>
     - <span data-ttu-id="8fd17-134">**게스트가 게스트를 초대할 수 있음**: 게스트가 다른 게스트를 초대하도록 허용하려면 이 정책을 **예**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-134">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
         > [!IMPORTANT]
         > <span data-ttu-id="8fd17-135">현재 Teams는 게스트 초대자 역할을 지원하지 않으므로 **참석자를 초대 할 수 있음**으로 **설정**하더라도 손님은 Teams에서 다른 참석자를 초대할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-135">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
     - <span data-ttu-id="8fd17-136">**게스트에 메일 일회용 암호 사용(미리 보기)**: 일회용 암호 기능에 대한 자세한 내용은 [메일 일회용 암호 인증(미리 보기)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8fd17-136">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
     - <span data-ttu-id="8fd17-137">**공동 작업 제한 사항**: 특정 도메인에 대한 초대를 허용하거나 차단하는 방법에 대한 자세한 내용은 [특정 조직에서 B2B 사용자에 대한 초대 허용 또는 차단](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8fd17-137">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
        > [!NOTE]
        > <span data-ttu-id="8fd17-138">공동 작업 제한 사항에 대한 자세한 내용은 [B2B 외부 공동 작업 사용 및 게스트를 초대할 수 있는 사용자 관리](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8fd17-138">For collaboration restrictions, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>
      
    <span data-ttu-id="8fd17-139">게스트를 초대할 수 있는 사용자를 제어하는 방법에 대한 자세한 내용은 [Azure Active Directory B2B 공동 작업에 대한 초대 위임](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-139">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

## <a name="step-3-configure-microsoft-365-groups"></a><span data-ttu-id="8fd17-140">3 단계: Microsoft 365 그룹 구성</span><span class="sxs-lookup"><span data-stu-id="8fd17-140">Step 3: Configure Microsoft 365 Groups</span></span>

1. <span data-ttu-id="8fd17-141">Microsoft 365 관리 센터에서 **설정**  >  **조직 설정**으로 이동 하 여 **서비스**를 클릭 한 다음 **Microsoft 365 그룹**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-141">In the Microsoft 365 admin center, go to **Settings** > **Org Settings**, click **Services**, and then select **Microsoft 365 Groups**.</span></span>

     ![스크린샷에는 Microsoft 365 Groups 설정이 나와 있습니다.](media/guest-access-checklist-services-settings.png)
2. <span data-ttu-id="8fd17-143">**조직 외부의 그룹 구성원이 그룹 콘텐츠에 액세스하도록 허용** 확인란을 선택했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-143">Make sure that the **Let group members outside the organization access group content** check box is selected.</span></span> <span data-ttu-id="8fd17-144">이 설정을 선택하지 않으면 게스트가 그룹 콘텐츠에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-144">If this setting is not selected, guests won't be able to access any group content.</span></span>

    ![스크린샷에는 Microsoft 365 Groups 설정이 나와 있습니다.](media/guest-access-checklist-office365.png)
3. <span data-ttu-id="8fd17-146">**그룹 소유자가 조직 외부의 사람을 그룹에 추가하도록 허용** 확인란을 선택했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-146">Make sure that the **Let group owners add people outside the organization to groups** check box is selected.</span></span> <span data-ttu-id="8fd17-147">이 설정을 선택하지 않으면 팀 소유자가 새 게스트를 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-147">If this setting is not selected, team owners won't be able to add new guests.</span></span> <span data-ttu-id="8fd17-148">게스트 액세스를 지원하려면 이 설정은 기본으로 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-148">At a minimum, this setting must be on to support guest access.</span></span>

<span data-ttu-id="8fd17-149">이러한 설정을 구성 하는 방법에 대 한 자세한 지침은 [microsoft 365 그룹에서 게스트 액세스 관리](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) 및 [microsoft 365 그룹의 게스트 액세스 제어](Teams-dependencies.md#control-guest-access-in-microsoft-365-groups)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8fd17-149">For detailed instructions about configuring these settings, see [Manage guest access in Microsoft 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Microsoft 365 Groups](Teams-dependencies.md#control-guest-access-in-microsoft-365-groups).</span></span>

## <a name="step-4-configure-sharing-in-microsoft-365"></a><span data-ttu-id="8fd17-150">4 단계: Microsoft 365에서 공유 구성</span><span class="sxs-lookup"><span data-stu-id="8fd17-150">Step 4: Configure sharing in Microsoft 365</span></span> 

<span data-ttu-id="8fd17-151">사용자가 게스트를 추가할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-151">Make sure that users can add guests.</span></span> <span data-ttu-id="8fd17-152">방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-152">Here's how:</span></span>

1. <span data-ttu-id="8fd17-153">Microsoft 365 관리 센터에서 **설정**  >  **조직 설정**으로 이동 하 여 **보안 & 개인 정보**를 클릭 한 다음 **공유**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-153">In the Microsoft 365 admin center, go to **Settings** > **Org Settings**, click **Security & privacy**, and then select **Sharing**.</span></span>

     ![서비스 설정의 예를 보여주는 스크린샷](media/guest-access-checklist-security-privacy-settings.png)
 
2. <span data-ttu-id="8fd17-155">**사용자가 이 조직에 새 게스트를 추가하도록 허용** 확인란을 선택한 다음 **변경 내용 저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-155">Select the **Let users add new guests to this organization** check box, and then click **Save changes**.</span></span>

     ![공유 설정 토글의 예를 보여주는 스크린샷](media/guest-access-checklist-sharing-setting.png)
 
    > [!NOTE]
    > <span data-ttu-id="8fd17-157">이 설정은 Azure AD의 **사용자 설정** > **외부 사용자**에 있는 **구성원 초대 허용** 설정과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-157">This setting is equivalent to the **Members can invite** setting in **User settings** > **External users** in Azure AD.</span></span>  

## <a name="step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="8fd17-158">5단계: SharePoint에서 공유 설정 확인</span><span class="sxs-lookup"><span data-stu-id="8fd17-158">Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="8fd17-159">Microsoft 365 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-159">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="8fd17-160">**관리 센터**에서 **SharePoint**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-160">Under **Admin centers**, select  **SharePoint**.</span></span>
3. <span data-ttu-id="8fd17-161">새 SharePoint 관리 센터의 **사이트**에서 **활성 사이트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-161">In the new SharePoint admin center,  under **Sites**, select **Active sites**.</span></span>

    ![SharePoint 관리 센터의 활성 사이트](media/guest-access-checklist-SPOSettings0.png)

3. <span data-ttu-id="8fd17-163">사이트를 선택하고 **공유**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-163">Select the site, and then click **Sharing**.</span></span>
4. <span data-ttu-id="8fd17-164">옵션이 **모든 사용자** 또는 **신규 및 기존 게스트**로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-164">Make sure that the option is set to **Anyone** or **New and existing guests**.</span></span>

     ![SharePoint Online 설정 토글의 예를 보여주는 스크린샷](media/guest-access-checklist-SPOSettings1.png)

## <a name="step-6-set-up-guest-user-permissions"></a><span data-ttu-id="8fd17-166">6단계: 게스트 사용자 권한 설정</span><span class="sxs-lookup"><span data-stu-id="8fd17-166">Step 6: Set up guest user permissions</span></span>

<span data-ttu-id="8fd17-167">Teams 응용 프로그램의 개별 팀 수준에서 게스트에서 채널을 만들고, 업데이트 또는 삭제할 수 있는지를 제어하는 게스트 권한을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-167">In the Teams application, at the individual team level, configure guest permissions that control whether guests can create, update, or delete channels.</span></span> <span data-ttu-id="8fd17-168">팀 관리자뿐만 아니라 팀 소유자도 이러한 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-168">Teams admins as well as team owners can configure these settings.</span></span>

![팀/채널 설정 토글의 예를 보여주는 스크린샷](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="8fd17-170">게스트 액세스에 대한 자세한 내용은 [Teams에서 게스트 액세스](guest-access.md) 및 [Microsoft Teams에 대한 게스트 액세스 켜기 또는 끄기](set-up-guests.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8fd17-170">To learn more about guest access, see [Guest access in Teams](guest-access.md) and [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="8fd17-171">문제 해결</span><span class="sxs-lookup"><span data-stu-id="8fd17-171">Troubleshooting</span></span>

<span data-ttu-id="8fd17-172">Teams에서 게스트 액세스를 설정하거나 게스트를 추가하는 데 문제가 있는 경우 다음 리소스를 사용하여 도움을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fd17-172">If you have problems setting up guest access or adding guests in Teams, use these resources to help you:</span></span>

[<span data-ttu-id="8fd17-173">Microsoft Teams의 게스트 액세스에 대한 문제 해결</span><span class="sxs-lookup"><span data-stu-id="8fd17-173">Troubleshoot problems with guest access in Microsoft Teams</span></span>](troubleshoot-guest-access.md)

[<span data-ttu-id="8fd17-174">Teams 문제 해결</span><span class="sxs-lookup"><span data-stu-id="8fd17-174">Teams troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)
