---
title: 비즈니스용 Skype Online에서 조직에 대한 오디오 회의 설정 관리
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '사용자 및 기타 여러 전화 접속 회의 설정에 전화 접속 회의 라이선스 및 전화 회의 ID를 할당하려면 비즈니스용 Skype Online 단계를 참조하세요. '
ms.openlocfilehash: aa8e9cbaf063ebf1780e3f8ce45b7bd54ced474f
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164147"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a><span data-ttu-id="604d9-103">비즈니스용 Skype Online에서 조직에 대한 오디오 회의 설정 관리</span><span class="sxs-lookup"><span data-stu-id="604d9-103">Manage the Audio Conferencing settings for my organization in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="604d9-104">Teams에서 이러한 설정을 관리하려면 Microsoft Teams에서 조직에 대한 오디오 회의 설정 관리를 [참조하세요.](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams)</span><span class="sxs-lookup"><span data-stu-id="604d9-104">If you want to manage these settings in Teams, see [Manage the Audio Conferencing settings for my organization in Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span></span>

<span data-ttu-id="604d9-105">비즈니스용 Skype의 모든 오디오 회의 설정을 한 곳으로 쉽게 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-105">It might be easier for you to see all of the audio conferencing settings for Skype for Business in one place.</span></span>


## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="604d9-106">오디오 회의 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="604d9-106">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="604d9-107">비즈니스용 Skype 관리 센터를 사용하여 라이선스를 **할당할 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="604d9-107">You can't assign licenses using the **Skype for Business admin center**.</span></span> <span data-ttu-id="604d9-108">Microsoft 365 관리 센터를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-108">You must use the Microsoft 365 admin center.</span></span> <span data-ttu-id="604d9-109">비즈니스용 [Skype 라이선스 할당을 참조하세요.](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="604d9-109">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

 <span data-ttu-id="604d9-110">**사용자에 대한 라이선스를 할당합니다.**</span><span class="sxs-lookup"><span data-stu-id="604d9-110">**To assign a license for a user**</span></span>

1. <span data-ttu-id="604d9-111">직장 또는 학교 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-111">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="604d9-112">관리 센터의 왼쪽 탐색 모음에서 **사용자** 활성 사용자로 이동한 다음 사용 가능한 사용자 목록에서 사용자 또는  >  사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-112">In the left navigation of the admin center, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="604d9-113">동시에 최대 20명까지 라이선스를 할당하는 경우 보기 선택 드롭다운을 사용하여 옵션 중 하나를 선택하거나 고유한 보기를 만들 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="604d9-113">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="604d9-114">그런 다음 **편집을 클릭하고** **다음을** 두 번 클릭한 다음 라이선스를 선택하고 제출을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="604d9-114">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span> <span data-ttu-id="604d9-115">Windows Powershell을 사용하여 여러 사용자에게 라이선스를 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-115">You can also assign licenses to multiple users by using Windows Powershell.</span></span> <span data-ttu-id="604d9-116">지침 및 샘플 PowerShell 스크립트는 비즈니스용 Skype 라이선스 [할당을 참조하세요.](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="604d9-116">For instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

3. <span data-ttu-id="604d9-117">제품 라이선스 아래의 작업 창에서 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="604d9-117">In the Action pane under **Product licenses**, click **Edit**.</span></span>

4. <span data-ttu-id="604d9-118">제품 **라이선스** 페이지에서 오디오 회의를 켜고 저장을 **클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="604d9-118">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="604d9-119">라이선스에 대한 자세한 내용은 비즈니스용 Skype 추가 [기능 라이선스를 참조하세요.](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="604d9-119">For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="604d9-120">라이선스를 할당한 후 Microsoft는 처음에 목록에 오디오 회의 공급자로 나타나지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-120">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider.</span></span> <span data-ttu-id="604d9-121">이 경우 관리 센터에서 로그아웃하거나 Ctrl+F5를 눌러 브라우저 창을 새로 고치십시오.</span><span class="sxs-lookup"><span data-stu-id="604d9-121">If this happens, either log out of the admin center or press CTRL+F5 to refresh the browser window.</span></span>

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="604d9-122">오디오 회의 사용자에게 전송된 전자 메일 사용 또는 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="604d9-122">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="604d9-123">![비즈니스용 skype 로고를 나타내는 아이콘](../images/sfb-logo-30x30.png) **비즈니스용 Skype 관리 센터 사용**</span><span class="sxs-lookup"><span data-stu-id="604d9-123">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="604d9-124">직장 또는 학교 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-124">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="604d9-125">비즈니스용 **Skype의** 관리 > 왼쪽 탐색 모음에서 오디오 **회의를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="604d9-125">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="604d9-126">Microsoft **브리지 설정** 페이지에서 오디오 회의 설정이 변경되는 경우 사용자에게 자동으로 전자 메일 보내기를 선택하거나 선택 **취소합니다.**</span><span class="sxs-lookup"><span data-stu-id="604d9-126">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="604d9-127">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-127">Click **Save**.</span></span>

    <span data-ttu-id="604d9-128">사용자의 오디오 회의 속성으로 이동하고 전자 메일을 통해 전화 회의 정보 보내기를 클릭하여 오디오 회의 설정을 사용하여 사용자에게 전자 메일을 보낼 **수도 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="604d9-128">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span> <span data-ttu-id="604d9-129">전화 회의 ID 및 기본 오디오 회의 전화 번호는 모임 초대에 포함되지만 PIN은 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-129">The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>

    <span data-ttu-id="604d9-130">오디오 회의 정보가 있는 사용자에게 전자 메일 [보내기를 참조하세요.](send-an-email-to-a-user-with-their-dial-in-information.md)</span><span class="sxs-lookup"><span data-stu-id="604d9-130">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="604d9-131">**다음 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="604d9-131">**Using Windows PowerShell**</span></span>

- <span data-ttu-id="604d9-132">또한 다음을 사용하여 Windows PowerShell 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-132">You can also use the Windows PowerShell and run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="604d9-133">[Set-CsOnlineDialInConferencingTenantSettings를](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) 사용하여 전자 메일을 비롯한 조직의 다른 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-133">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) to manage other settings for your organization, including email.</span></span>

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="604d9-134">사용자에게 전송된 전자 메일 메시지에서 보낸 사람 연락처 정보 변경</span><span class="sxs-lookup"><span data-stu-id="604d9-134">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="604d9-135">보낸 사람 연락처 정보의 실제 전자 메일 주소 및 표시 이름을 포함하여 사용자에게 자동으로 전송되는 전자 메일을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-135">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="604d9-136">기본적으로 전자 메일의 보낸 사람이 Microsoft 365 또는 Office 365이지만 Windows PowerShell [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet을 사용하여 전자 메일 주소와 표시 이름을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-136">By default, the sender of the emails is Microsoft 365 or Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="604d9-137">사용자에게 전자 메일을 보내는 전자 메일 주소를 변경하려면 다음을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-137">To make changes to the email address that is sending the email to the users, you must:</span></span>

- <span data-ttu-id="604d9-138">_SendEmailFromAddress_ 매개 변수에 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-138">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>

- <span data-ttu-id="604d9-139">_SendEmailFromDisplayName_ 매개 변수에 전자 메일 표시 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-139">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>

- <span data-ttu-id="604d9-140">_SendEmailOverride_ 매개 변수를 _True로 설정_</span><span class="sxs-lookup"><span data-stu-id="604d9-140">Set the _SendEmailOverride_ parameter to _True_.</span></span>

<span data-ttu-id="604d9-141">다음을 실행하여 사용자에게 전송된 전자 메일(예: 전자 메일이 전송된 전자 메일 주소 또는 전자 메일의 표시 이름)을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-141">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="604d9-142">전자 메일 주소 정보를 변경하려면 조직의 인바운드 전자 메일 정책에서 사용자 지정 전자 메일 주소에서 오는 전자 메일을 허용하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-142">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>

<span data-ttu-id="604d9-143">[Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet을 사용하여 전자 메일을 비롯한 조직의 다른 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-143">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to manage other settings for your organization, including email.</span></span>

<span data-ttu-id="604d9-144">오디오 회의 설정이 변경될 때 사용자에게 자동으로 전송되는 전자 메일을 [참조하세요.](emails-sent-to-users-when-their-settings-change.md)</span><span class="sxs-lookup"><span data-stu-id="604d9-144">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="604d9-145">모임 회의 ID 다시 설정</span><span class="sxs-lookup"><span data-stu-id="604d9-145">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="604d9-146">직장 또는 학교 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-146">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="604d9-147">비즈니스용 Skype의 > **관리 센터로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="604d9-147">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="604d9-148">비즈니스용 **Skype** 관리 센터의 왼쪽 탐색 창에서 오디오 회의로 이동하고 회의 ID 아래의 작업 **창에서** 다시 설정을  **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="604d9-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="604d9-149">회의 **ID 재설정 창에서** **예를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="604d9-149">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="604d9-150">사용자에게 전자 메일을 보낼 수 있는 경우 회의 ID가 자동으로 생성되고 새 회의 ID가 있는 전자 메일이 사용자에게 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-150">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="604d9-151">기본적으로 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-151">It's enabled by default.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="604d9-152">새 전화 회의 ID가 생성되면 발신자에 의해 이전 전화 회의 ID를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-152">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="604d9-153">새 회의 ID가 초대에 추가될 수 있도록 사용자에게 기존 모임 초대를 다시 계획할지 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-153">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="604d9-154">사용자는 비즈니스용 Skype 모임 마이그레이션 도구를 사용하여 기존 모임을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-154">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="604d9-155">비즈니스용 Skype 모임 업데이트 도구를 다운로드, 설치 및 실행하려면 비즈니스용 Skype 및 [Lync용](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)모임 업데이트 도구, 비즈니스용 Skype Online, 모임 마이그레이션 [도구(64비트)](https://go.microsoft.com/fwlink/?LinkID=626047)및 비즈니스용 Skype Online 모임 마이그레이션  [도구(32비트)를](https://www.microsoft.com/download/details.aspx?id=54079)참조하세요.</span><span class="sxs-lookup"><span data-stu-id="604d9-155">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/download/details.aspx?id=54079).</span></span>

<span data-ttu-id="604d9-156">사용자의 [회의 ID 재설정을 참조합니다.](reset-a-conference-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="604d9-156">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>

## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="604d9-157">회의 이끌이의 PIN 다시 설정</span><span class="sxs-lookup"><span data-stu-id="604d9-157">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="604d9-158">사용자가 예약하는 각 모임에는 고유한 회의 ID가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-158">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="604d9-159">전화 회의 ID가 자동으로 만들어지며 사용자에게 할당되어도 사용자가 이 ID를 사용하지 못하고 특정 번호로 설정하려는 경우 또는 사용자가 전화 회의 ID를 기억하지 못하거나 분실한 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-159">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="604d9-160">비즈니스용 Skype 관리 센터 및 Windows PowerShell ID를 보고, 변경하고, 재설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-160">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>


1. <span data-ttu-id="604d9-161">직장 또는 학교 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-161">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="604d9-162">비즈니스용 **Skype의** 관리 > 왼쪽 탐색 모음에서 오디오 **회의를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="604d9-162">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="604d9-163">사용자를 **클릭한** 다음 PIN을 다시 설정할 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-163">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="604d9-164">작업 창의 PIN **아래에서** 재설정을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="604d9-164">In the Action pane, under **PIN**, click **Reset**.</span></span>

<span data-ttu-id="604d9-165">오디오 회의를 사용하도록 설정하거나 PIN이 다시 설정되면 사용자가 PIN이 있는 전자 메일을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-165">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="604d9-166">하지만 전자 메일 자동 전송을 사용하지 않도록 설정한 경우 PIN 재설정 전자 메일이 전송되지 않고 사용자에게 PIN을 수동으로 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-166">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="604d9-167">PIN은 다시 설정한 후에 한 번만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-167">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="604d9-168">다시 설정 직후에 PIN이 표시되면 사용자 속성에 더 이상 표시되지 않습니다. 대신 \*\*\*\*\*가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-168">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span>

<span data-ttu-id="604d9-169">오디오 [회의 PIN 재설정을 참조합니다.](reset-the-audio-conferencing-pin.md)</span><span class="sxs-lookup"><span data-stu-id="604d9-169">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="604d9-170">사용자에게 오디오 회의 정보가 있는 전자 메일 보내기</span><span class="sxs-lookup"><span data-stu-id="604d9-170">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="604d9-171">직장 또는 학교 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-171">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="604d9-172">비즈니스용 **Skype의** 관리 > 왼쪽 탐색 모음에서 오디오 **회의를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="604d9-172">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="604d9-173">사용자를 **클릭한** 다음 PIN을 다시 설정할 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-173">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="604d9-174">작업 창에서 전자 메일을 통해 **전화 회의 정보 보내기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="604d9-174">In the Action pane, click **Send conference info via email**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="604d9-175">이렇게 하는 경우 오디오 회의 PIN이 사용자에게 전송되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-175">When you do this, the audio conferencing PIN isn't sent to the user.</span></span>

<span data-ttu-id="604d9-176">오디오 회의 정보가 있는 사용자에게 전자 메일 [보내기를 참조하세요.](send-an-email-to-a-user-with-their-dial-in-information.md)</span><span class="sxs-lookup"><span data-stu-id="604d9-176">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="604d9-177">초대에 포함된 전화 번호 설정</span><span class="sxs-lookup"><span data-stu-id="604d9-177">Setting the phone numbers included on invites</span></span>

1. <span data-ttu-id="604d9-178">직장 또는 학교 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-178">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="604d9-179">비즈니스용 Skype의 > **관리 센터로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="604d9-179">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="604d9-180">왼쪽 탐색에서 오디오 회의 **사용자로**  >  **이동**</span><span class="sxs-lookup"><span data-stu-id="604d9-180">In the left navigation, go to **Audio conferencing** > **Users**.</span></span> <span data-ttu-id="604d9-181">오디오 회의를 사용하도록 설정할 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-181">Select the user that you want to enable for Audio Conferencing.</span></span>

4. <span data-ttu-id="604d9-182">작업 창에서 무료 번호를 설정하고 허용되는 경우 무료 번호를 설정할 **수 있습니다.** </span><span class="sxs-lookup"><span data-stu-id="604d9-182">In the Action pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

5. <span data-ttu-id="604d9-183">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-183">Click **Save**.</span></span>

<span data-ttu-id="604d9-184">초대에 [포함된 전화 번호](set-the-phone-numbers-included-on-invites.md)설정 참조</span><span class="sxs-lookup"><span data-stu-id="604d9-184">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>


## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="604d9-185">오디오 회의 브리지 설정 선택</span><span class="sxs-lookup"><span data-stu-id="604d9-185">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="604d9-186">**발신자 모임에 참가할 때 모임 환경 설정**</span><span class="sxs-lookup"><span data-stu-id="604d9-186">**Set the meeting experience when callers join a meeting**</span></span>


1. <span data-ttu-id="604d9-187">직장 또는 학교 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-187">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="604d9-188">비즈니스용 Skype의 > **관리 센터로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="604d9-188">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="604d9-189">비즈니스용 Skype 관리 **센터의** 왼쪽 탐색 모음에서 **오디오** 회의 Microsoft 브리지  >  **설정으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="604d9-189">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="604d9-190">모임 **참가 환경 아래에서** 다음 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-190">Under **Meeting join experience**, select the following actions:</span></span>

   - <span data-ttu-id="604d9-191">**모임 입장 및 퇴장 알림을** 사용하도록 설정 기본적으로 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-191">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="604d9-192">이 확인란의 선택을 취소하면 기본적으로 모임에 이미 참가한 사용자는 모임에 입장하거나 퇴장할 때 알림을 들을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-192">If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

     <span data-ttu-id="604d9-193">이 설정은 사용자가 비즈니스용 Skype 앱을 사용하여 모임에 참가하고 모임의 Skype 모임  옵션 메뉴에서 사용자가 입장하거나 떠날 때 발표를 수정할 때 모임을 기준으로 설정할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="604d9-193">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business app and they modify the **Announce when people enter or leave** setting in the Skype Meeting **Options** menu of the meeting.</span></span>

   - <span data-ttu-id="604d9-194">**발신자들에게** 모임에 참가하기 전에 이름을 기록해달라고 요청 기본적으로 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-194">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="604d9-195">이 확인란의 선택을 취소하면 발신자는 모임에 참가하기 전에 이름을 기록할지 묻는 요청이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-195">If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>

5. <span data-ttu-id="604d9-196">변경한 후 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="604d9-196">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="604d9-197">오디오 회의 브리지의 설정 [변경을 참조하세요.](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)</span><span class="sxs-lookup"><span data-stu-id="604d9-197">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="604d9-198">**모임의 PIN 길이 설정**</span><span class="sxs-lookup"><span data-stu-id="604d9-198">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="604d9-199">직장 또는 학교 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-199">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="604d9-200">비즈니스용 Skype의 > **관리 센터로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="604d9-200">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="604d9-201">비즈니스용 Skype 관리 **센터의** 왼쪽 탐색 모음에서 **오디오** 회의 Microsoft 브리지  >  **설정으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="604d9-201">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="604d9-202">보안 **아래에서** PIN 길이 목록에서 **PIN에** 사용할 자릿 수를 입력한 다음 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="604d9-202">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="604d9-203">PIN은 4~12자리 사이입니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-203">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="604d9-204">기본값은 5입니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-204">The default is 5.</span></span>
    
<span data-ttu-id="604d9-205">오디오 회의 브리지의 설정 [변경을 참조하세요.](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)</span><span class="sxs-lookup"><span data-stu-id="604d9-205">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="604d9-206">**오디오 사용자에게 전자 메일 보내기 사용 또는 사용 안 하도록 설정**</span><span class="sxs-lookup"><span data-stu-id="604d9-206">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="604d9-207">직장 또는 학교 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-207">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="604d9-208">비즈니스용 **Skype의** 관리 > 왼쪽 탐색 모음에서 오디오 **회의를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="604d9-208">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="604d9-209">Microsoft **브리지 설정** 페이지에서 오디오 회의 설정이 변경되는 경우 사용자에게 자동으로 전자 메일 보내기를 선택하거나 선택 **취소합니다.**</span><span class="sxs-lookup"><span data-stu-id="604d9-209">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="604d9-210">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-210">Click **Save**.</span></span>

    <span data-ttu-id="604d9-211">사용자의 오디오 회의 속성으로 이동하고 전자 메일을 통해 전화 회의 정보 보내기를 클릭하여 오디오 회의 설정을 사용하여 사용자에게 전자 메일을 보낼 **수도 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="604d9-211">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>

    <span data-ttu-id="604d9-212">이렇게 하면 전화 회의 ID와 전화 회의 전화 번호만 포함된 전자 메일이 전송되지만 PIN은 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-212">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

    <span data-ttu-id="604d9-213">오디오 회의 정보가 있는 사용자에게 전자 메일 [보내기를 참조하세요.](send-an-email-to-a-user-with-their-dial-in-information.md)</span><span class="sxs-lookup"><span data-stu-id="604d9-213">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="604d9-214">오디오 회의 브리지에서 기본(기본값) 및 보조(대체) 언어 보기 및 설정</span><span class="sxs-lookup"><span data-stu-id="604d9-214">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>


1. <span data-ttu-id="604d9-215">직장 또는 학교 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-215">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="604d9-216">비즈니스용 Skype의 > **관리 센터로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="604d9-216">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="604d9-217">비즈니스용 Skype 관리 **센터의** 왼쪽 탐색 모음에서 **오디오** 회의로 이동한 다음 Microsoft 브리지를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="604d9-217">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>

4. <span data-ttu-id="604d9-218">목록에서 전화 번호를 선택하고 작업 창에서 언어 설정을 클릭한  다음 언어 설정 페이지에서 기본  언어 목록을 클릭하여 지원되는 언어의 전체 목록을 볼 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="604d9-218">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>

    <span data-ttu-id="604d9-219">오디오 회의 공급자로 Microsoft를 선택할 때 지원되는 기본 및 보조 언어를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-219">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="604d9-220">목록에서 선택한 순서는 발신자에 언어를 표시하는 순서와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-220">The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>

<span data-ttu-id="604d9-221">오디오 [회의에 대한](set-auto-attendant-languages-for-audio-conferencing.md)자동 참석 언어 설정 참조</span><span class="sxs-lookup"><span data-stu-id="604d9-221">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>

## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="604d9-222">오디오 회의 전화 접속 번호 보기</span><span class="sxs-lookup"><span data-stu-id="604d9-222">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="604d9-223">직장 또는 학교 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-223">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="604d9-224">비즈니스용 Skype의 > **관리 센터로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="604d9-224">Go to the admin center > **Skype for Business**.</span></span>
 
3. <span data-ttu-id="604d9-225">비즈니스용 Skype 관리 **센터의** 왼쪽 탐색 모음에서 **오디오** 회의 Microsoft  >  **브리지로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="604d9-225">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**.</span></span> <span data-ttu-id="604d9-226">여기에서 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-226">Here you can:</span></span>

   - <span data-ttu-id="604d9-227">오디오 회의에 사용할 Microsoft 365 또는 Office 365에서 설정한 전화 번호를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-227">View the phone numbers that are set by Microsoft 365 or Office 365 to be used for Audio Conferencing.</span></span>

   - <span data-ttu-id="604d9-228">오디오 회의 자동 연결에서 사용할 위치 및 기본 및 보조 언어를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-228">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>

   - <span data-ttu-id="604d9-229">오디오 회의를 사용하도록 설정하면 사용자에게 제공될 기본 전화 번호를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-229">Select the default phone number that will be given to users when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="604d9-230">그러나 오디오 회의 브리지의 기본 전화 번호가 변경되는 경우 기존 사용자의 기본 전화 번호는 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-230">However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>

<span data-ttu-id="604d9-231">오디오 회의 사용자로 이동하여 사용자의 속성을 선택하여 조직에서 사용할 수 있는 번호 목록에서 새 번호를 선택하여 사용자의 기본 번호를 변경할  >   수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-231">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>

<span data-ttu-id="604d9-232">오디오 회의 번호 목록을 [참조하세요.](see-a-list-of-audio-conferencing-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="604d9-232">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>

## <a name="see-a-list-of-users-that-are-enabled"></a><span data-ttu-id="604d9-233">사용하도록 설정된 사용자 목록 보기</span><span class="sxs-lookup"><span data-stu-id="604d9-233">See a list of users that are enabled</span></span>

1. <span data-ttu-id="604d9-234">직장 또는 학교 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-234">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="604d9-235">비즈니스용 Skype의 > **관리 센터로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="604d9-235">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="604d9-236">비즈니스용 Skype 관리 **센터의** 왼쪽 탐색 모음에서 오디오 회의>  **사용자로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="604d9-236">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>

<span data-ttu-id="604d9-237">오디오 회의에 사용할 수 있는 사용자 목록을 [참조하세요.](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="604d9-237">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="604d9-238">사용자 계정으로 관리하는 방법을 알고 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="604d9-238">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="604d9-239">조직 수준에서 여러 설정을 사용하여 관리할 수 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="604d9-239">There are several settings that you can manage at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="604d9-240">이렇게 하면 모든 사용자에게 설정을 쉽게 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-240">This makes it easy to apply settings to all of your users.</span></span>

<span data-ttu-id="604d9-241">각 cmdlet에 대한 자세한 내용은 [비즈니스용 Skype Online cmdlet을 참조하세요.](https://go.microsoft.com/fwlink/?LinkId=627324)</span><span class="sxs-lookup"><span data-stu-id="604d9-241">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="604d9-242">다음은 조직 수준 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-242">Here are the organization-level settings:</span></span>

- <span data-ttu-id="604d9-243">**진입/종료 알림 설정** 기본값은 _$true._</span><span class="sxs-lookup"><span data-stu-id="604d9-243">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- <span data-ttu-id="604d9-244">**이름 녹음/녹화 설정** 기본값은 _$true._</span><span class="sxs-lookup"><span data-stu-id="604d9-244">**Setting name recording** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="604d9-245">**PIN 길이 설정** 기본값은 5입니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-245">**Setting the PIN length** The default is 5.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="604d9-246">**휴대폰에서 전화 접속 모임만 설정** 기본 _$false._</span><span class="sxs-lookup"><span data-stu-id="604d9-246">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="604d9-247">**사용자에게 전자 메일을 보낼지 여부 설정** 기본값은 _$true._</span><span class="sxs-lookup"><span data-stu-id="604d9-247">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="604d9-248">**다른 계정에서 전자 메일을 보낼지 여부 설정** 기본값은 _$false._</span><span class="sxs-lookup"><span data-stu-id="604d9-248">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="604d9-249">**사용자에게 전송된 전자** 메일에서 보낸 메일 주소 설정 기본값은 _$null._</span><span class="sxs-lookup"><span data-stu-id="604d9-249">**Setting the From address on email that is sent to users** The default is _$null_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="604d9-250">**사용자에게 전송된 전자 메일의 표시 이름 설정** 기본값은 _$null._</span><span class="sxs-lookup"><span data-stu-id="604d9-250">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

  ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="604d9-251">자세한 내용은 다음을 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="604d9-251">Want to know more about Windows PowerShell</span></span>
- <span data-ttu-id="604d9-252">Windows PowerShell 관리는 사용자 및 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-252">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="604d9-253">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-253">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="604d9-254">다음 항목을 Windows PowerShell 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="604d9-254">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="604d9-255">Microsoft 365 또는 Office 365 PowerShell을 사용하는 이유</span><span class="sxs-lookup"><span data-stu-id="604d9-255">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [<span data-ttu-id="604d9-256">Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="604d9-256">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

- <span data-ttu-id="604d9-257">Windows PowerShell 많은 사용자에 대한 설정을 한 번 변경하는 경우와 같이 관리 센터를 사용하는 것 이상으로 속도, 단순성 및 생산성에 많은 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-257">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="604d9-258">다음 항목에서 이러한 이점에 대해 자세히 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-258">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="604d9-259">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="604d9-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="604d9-260">비즈니스 Windows PowerShell 사용하여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="604d9-260">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="604d9-261">비즈니스용 Windows PowerShell Skype Online 관리 작업을 수행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-261">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

    <span data-ttu-id="604d9-262">비즈니스 Windows PowerShell용 Skype Online 모듈을 사용하면 비즈니스용 Skype Online에 Windows PowerShell 원격 세션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-262">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="604d9-263">64비트 컴퓨터에서만 지원되는 이 모듈은 비즈니스용 [Skype Online용](https://go.microsoft.com/fwlink/?LinkId=294688) Windows PowerShell 모듈의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="604d9-263">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>

## <a name="related-topics"></a><span data-ttu-id="604d9-264">관련 항목</span><span class="sxs-lookup"><span data-stu-id="604d9-264">Related topics</span></span>

[<span data-ttu-id="604d9-265">사용자의 오디오 회의 설정 관리</span><span class="sxs-lookup"><span data-stu-id="604d9-265">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)


