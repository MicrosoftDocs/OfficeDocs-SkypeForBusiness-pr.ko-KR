---
title: Microsoft 팀 게스트 액세스 검사 목록
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: 이 검사 목록을 사용 하 여 Microsoft 팀에서 게스트 액세스를 설정할 수 있습니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04594f578d2375f69c38243251ee64506880d00e
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/28/2019
ms.locfileid: "37753323"
---
<a name="microsoft-teams-guest-access-checklist"></a><span data-ttu-id="3922e-103">Microsoft 팀 게스트 액세스 검사 목록</span><span class="sxs-lookup"><span data-stu-id="3922e-103">Microsoft Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="3922e-104">Microsoft 팀에서 게스트 액세스를 설정 하 고 구성 하는 데 도움이 되는 검사 목록을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-104">Use this checklist to help you turn on and configure guest access in Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3922e-105">변경 내용이 적용 되려면 24 시간까지 기다려야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-105">You may have to wait up to 24 hours for your changes to take effect.</span></span> 



## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a><span data-ttu-id="3922e-106">1 단계: 조직 전체 수준에서 게스트 액세스 켜기 팀</span><span class="sxs-lookup"><span data-stu-id="3922e-106">Step 1: Turn on guest access at the Teams org-wide level</span></span>

<span data-ttu-id="3922e-107">게스트 액세스를 설정 하려면 **Microsoft 팀 관리 센터로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-107">To turn on guest access, go to the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="3922e-108">팀 관리 센터에서 **조직 전체 설정** > **게스트 액세스**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-108">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="3922e-109">**Microsoft 팀에서 게스트 액세스 허용** 을 **설정으로 전환 합니다.**</span><span class="sxs-lookup"><span data-stu-id="3922e-109">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![팀 설정의 예를 보여 주는 스크린샷](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="3922e-111">이 페이지에서 게스트에 대 한 **통화**, **모임**및 **메시징** 설정을 설정 하거나 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-111">On this same page, turn on or turn off **Calling**, **Meeting**, and **Messaging** settings for guests.</span></span>
4. <span data-ttu-id="3922e-112">**저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-112">Click **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="3922e-113">Azure Active Directory, SharePoint Online 및 Office 365 그룹에서 기본 설정을 사용 하는 경우 게스트 액세스 구성이 완료 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-113">If you're using default settings in Azure Active Directory, SharePoint Online, and Office 365 Groups, you may be done configuring guest access.</span></span> <span data-ttu-id="3922e-114">이 경우 나머지 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-114">In this case, you can skip the rest of the steps.</span></span> <span data-ttu-id="3922e-115">확실 하지 않은 경우 또는 AAD, SharePoint Online 또는 Office 365 그룹에 대 한 사용자 지정 설정을 사용 하는 경우이 검사 목록의 나머지 단계를 계속 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-115">If you're not sure, or if you're using custom settings for AAD, SharePoint Online, or Office 365 Groups, continue with the rest of the steps in this checklist.</span></span>


## <a name="step-2-configure-azure-ad-business-to-business-settings"></a><span data-ttu-id="3922e-116">2 단계: Azure AD business 비즈니스에 대 한 설정 구성</span><span class="sxs-lookup"><span data-stu-id="3922e-116">Step 2: Configure Azure AD business-to-business settings</span></span>

1. <span data-ttu-id="3922e-117">테 넌 트 관리자로 [Azure 포털](https://portal.azure.com) 에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-117">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="3922e-118">**Azure Active Directory** > **사용자** > **사용자 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-118">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="3922e-119">**외부 사용자**아래에서 **외부 공동 작업 설정 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-119">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="3922e-120">**외부 공동 작업 설정은** **조직 관계** 페이지 에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-120">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="3922e-121">Azure Active Directory의 **관리**에서 **조직 관계** > **설정**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-121">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="3922e-122">**외부 공동 작업 설정** 페이지에서 사용 하도록 설정할 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-122">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

  - <span data-ttu-id="3922e-123">**게스트 사용자 권한이 제한 됨**:이 정책은 디렉터리의 게스트에 대 한 사용 권한을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-123">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="3922e-124">**예** 를 선택 하 여 사용자, 그룹 또는 기타 디렉터리 리소스 열거와 같은 특정 디렉터리 작업에서 게스트를 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-124">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="3922e-125">게스트를 사용 하 여 디렉터리 데이터에 대 한 액세스 권한을 다른 사용자와 동일 하 게 지정 하려면 ( **아니요** )를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-125">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
   - <span data-ttu-id="3922e-126">**게스트 inviter 역할의 관리자와 사용자는 초대할 수 있습니다**. "게스트 inviter" 역할의 관리자와 사용자가 게스트를 초대 하도록 허용 하려면이 정책을 **Yes**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-126">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
   - <span data-ttu-id="3922e-127">**구성원 초대 가능**: 해당 디렉터리의 관리자가 아닌 구성원이 게스트를 초대 하도록 허용 하려면이 정책을 **예로**설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-127">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes**.</span></span>
   
       > [!NOTE]
       > <span data-ttu-id="3922e-128">구성원을 **No** 에 **초대할 수** 있고 Office 365 그룹 및 Microsoft 팀에서 게스트 액세스를 사용 하도록 설정한 경우 관리자는 디렉터리에 대 한 게스트 초대를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-128">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="3922e-129">Guest가 디렉터리에 있으면 팀 소유자 인 관리자가 아닌 구성원에 따라 팀에 추가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-129">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span> <span data-ttu-id="3922e-130">자세한 내용은 [Microsoft 팀에서 게스트 액세스 권한 부여](Teams-dependencies.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3922e-130">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
       > [!IMPORTANT]
       > <span data-ttu-id="3922e-131">게스트의 모든 팀에서 작업에 액세스 하려면 구성원을 **예**에 **초대할 수** 있도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-131">For guest access to work at all in Teams, you must set **Members can invite** to **Yes**.</span></span>   
   - <span data-ttu-id="3922e-132">**게스트 초대**: 게스트가 다른 게스트를 초대할 수 있도록 하려면이 정책을 **Yes**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-132">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
       > [!IMPORTANT]
       > <span data-ttu-id="3922e-133">현재 팀은 게스트 inviter 역할을 지원 하지 않으므로, 게스트가 **예**에 **초대할 수** 있도록 설정한 경우에도 게스트는 다른 게스트를 팀에 초대할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-133">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
   - <span data-ttu-id="3922e-134">**게스트를 위한 전자 메일 1 회 암호 사용 (미리 보기)**: 일회성 암호 기능에 대 한 자세한 내용은 일회용 [암호 기반 전자 메일 인증 (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3922e-134">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
   - <span data-ttu-id="3922e-135">**공동 작업 제한 사항**: 특정 도메인에 대 한 초대를 허용 하거나 차단 하는 방법에 대 한 자세한 내용은 [특정 조직의 B2B 사용자에 대 한 초대 허용 또는 차단](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3922e-135">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
      > [!NOTE]
      > <span data-ttu-id="3922e-136">공동 작업 제한 사항은 [B2B 외부 공동 작업 사용 및 게스트 초대를 할 수 있는 사용자 관리](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3922e-136">For collaboration restrictions, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>
      
 
<span data-ttu-id="3922e-137">게스트를 초대할 수 있는 사용자를 제어 하는 방법에 대 한 자세한 내용은 [Azure Active DIRECTORY B2B 공동 작업에 대 한 초대 위임을](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3922e-137">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>


## <a name="step-3-configure-office-365-groups"></a><span data-ttu-id="3922e-138">3 단계: Office 365 그룹 구성</span><span class="sxs-lookup"><span data-stu-id="3922e-138">Step 3: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="3922e-139">Microsoft 365 관리 센터에서 **설정** > **서비스 & 추가 기능** > **Office 365 그룹**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-139">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="3922e-140">조직에서 그룹 **구성원을 액세스할 수 있도록 그룹 콘텐츠** 를 설정 하도록 허용 해야 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="3922e-140">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="3922e-141">이 설정이 해제 되어 있으면 게스트는 그룹 콘텐츠에 액세스할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-141">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="3922e-142">**그룹 소유자가 조직 외부의 사용자를 그룹에 추가 하도록 허용** 하는 것이 설정 되어 있는지 확인 **합니다.**</span><span class="sxs-lookup"><span data-stu-id="3922e-142">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="3922e-143">이 설정을 끄면 팀 소유자가 새 게스트를 추가할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-143">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="3922e-144">게스트 액세스를 지원 하려면 최소한이 설정이 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-144">At a minimum, this setting must be On to support guest access.</span></span>

     ![스크린샷에서는 Office 365 그룹을 표시 하거나 숨깁니다.](media/guest-access-checklist-office365.png)

<span data-ttu-id="3922e-146">이러한 설정을 구성 하는 방법에 대 한 자세한 지침은 [office 365 그룹에서 게스트 액세스 관리](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) 및 [office 365 그룹의 게스트 액세스 제어](Teams-dependencies.md#control-guest-access-in-office-365-groups)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3922e-146">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>
 

## <a name="step-4-configure-sharing-in-office-365"></a><span data-ttu-id="3922e-147">4 단계: Office 365에서 공유 구성</span><span class="sxs-lookup"><span data-stu-id="3922e-147">Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="3922e-148">사용자가 게스트를 추가할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-148">Make sure that users can add guests.</span></span> <span data-ttu-id="3922e-149">방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-149">Here's how:</span></span>

1. <span data-ttu-id="3922e-150">Microsoft 365 관리 센터에서 **설정** > **보안 & 개인 정보**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-150">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![스크린샷에서는 서비스 설정의 예를 보여 줍니다.](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="3922e-152">**공유**에서 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-152">In **Sharing**, select **Edit**.</span></span>

     ![공유 설정의 예를 보여 주는 스크린샷](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="3922e-154">**사용자가이 조직에 새 게스트를 추가할 수 있도록 허용** **을 선택한**다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-154">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![공유 설정의 예를 보여 주는 스크린샷](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> <span data-ttu-id="3922e-156">이 설정은 회원 들이 Azure AD의**외부 사용자** **설정** > 에서 설정을 **초대할 수** 있는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-156">This setting is equivalent to the **Members can invite** setting in **User settings** > **External users** in Azure AD.</span></span>  


## <a name="step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="3922e-157">5 단계: SharePoint에서 공유 설정 확인</span><span class="sxs-lookup"><span data-stu-id="3922e-157">Step 5: Verify sharing setting in SharePoint</span></span>

<span data-ttu-id="3922e-158">이는 여러분의 두뇌 teaser 한 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-158">This one's a bit of a brain teaser.</span></span> <span data-ttu-id="3922e-159">SharePoint 관리 센터에서 **조직 외부 공유** 설정이 선택 되어 있지 않으면 팀의 게스트 액세스가 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-159">Guest access in Teams doesn't work if the **Don't allow sharing outside your organization** setting is selected in the SharePoint admin center.</span></span>

1. <span data-ttu-id="3922e-160">Microsoft 365 관리 센터에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-160">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="3922e-161">**관리 센터**를 클릭 한 다음 **SharePoint**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-161">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="3922e-162">SharePoint 관리 센터에서 **공유**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-162">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="3922e-163">**조직 외부 공유 허용 안 함** 옵션이 선택 되어 *있지* 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-163">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![스크린샷에는 SparePoint 온라인 설정 토글의 예가 나와 있습니다.](media/guest-access-checklist-SPOSettings1.png)


## <a name="step-6-set-up-guest-user-permissions"></a><span data-ttu-id="3922e-165">6 단계: 게스트 사용자 권한 설정</span><span class="sxs-lookup"><span data-stu-id="3922e-165">Step 6: Set up guest user permissions</span></span>

<span data-ttu-id="3922e-166">팀 응용 프로그램 개별 팀 수준에서 게스트가 채널을 만들거나 업데이트 하거나 삭제할 수 있는지 여부를 제어 하는 게스트 권한을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-166">In the Teams application, at the individual team level, configure guest permissions that control whether guests can create, update, or delete channels.</span></span> <span data-ttu-id="3922e-167">팀 관리자는 물론 팀 소유자는 이러한 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3922e-167">Teams admins as well as team owners can configure these settings.</span></span>

![팀/채널 설정의 예를 보여 주는 스크린샷](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="3922e-169">게스트 액세스에 대 한 자세한 내용은 [팀에서 게스트 액세스](guest-access.md) 및 Microsoft 팀에 대 한 [게스트 액세스 설정 또는 해제](set-up-guests.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3922e-169">To learn more about guest access, see [Guest access in Teams](guest-access.md) and [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="3922e-170">해결사</span><span class="sxs-lookup"><span data-stu-id="3922e-170">Troubleshooting</span></span>

<span data-ttu-id="3922e-171">팀에서 게스트 액세스를 설정 하거나 게스트를 추가 하는 데 문제가 있는 경우 다음 리소스를 사용 하 여 도움을 받으세요.</span><span class="sxs-lookup"><span data-stu-id="3922e-171">If you have problems setting up guest access or adding guests in Teams, use these resources to help you:</span></span>

[<span data-ttu-id="3922e-172">Microsoft 팀의 게스트 액세스 문제 해결</span><span class="sxs-lookup"><span data-stu-id="3922e-172">Troubleshoot problems with guest access in Microsoft Teams</span></span>](troubleshoot-guest-access.md)

[<span data-ttu-id="3922e-173">팀 문제 해결</span><span class="sxs-lookup"><span data-stu-id="3922e-173">Teams troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)



