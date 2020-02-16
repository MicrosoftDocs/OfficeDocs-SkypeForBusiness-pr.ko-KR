---
title: 비즈니스용 Skype Online에서 조직의 오디오 회의 설정 관리
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
description: '전화 접속 회의 라이선스 및 전화 회의 ID를 사용자와 여러 다른 전화 접속 회의 설정에 할당 하려면 비즈니스용 Skype Online 단계를 참조 하세요. '
ms.openlocfilehash: 46f55ba256759d86e93e9436e949ee49ff337f7c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41986523"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a><span data-ttu-id="fa797-103">비즈니스용 Skype Online에서 조직의 오디오 회의 설정 관리</span><span class="sxs-lookup"><span data-stu-id="fa797-103">Manage the Audio Conferencing settings for my organization in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="fa797-104">팀에서 이러한 설정을 관리 하려면 [Microsoft 팀에서 내 조직의 오디오 회의 설정 관리](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fa797-104">If you want to manage these settings in Teams, see [Manage the Audio Conferencing settings for my organization in Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span></span>

<span data-ttu-id="fa797-105">한 곳에서 비즈니스용 Skype에 대 한 오디오 회의 설정을 모두 확인 하는 것이 더 쉬울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-105">It might be easier for you to see all of the audio conferencing settings for Skype for Business in one place.</span></span>


## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="fa797-106">오디오 회의 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="fa797-106">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="fa797-107">**비즈니스용 Skype 관리 센터**를 사용 하 여 라이선스를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-107">You can't assign licenses using the **Skype for Business admin center**.</span></span> <span data-ttu-id="fa797-108">Microsoft 365 관리 센터를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-108">You must use the Microsoft 365 admin center.</span></span> <span data-ttu-id="fa797-109">[비즈니스용 Skype 라이선스 할당](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fa797-109">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

 <span data-ttu-id="fa797-110">**사용자에 게 라이선스를 할당 하려면**</span><span class="sxs-lookup"><span data-stu-id="fa797-110">**To assign a license for a user**</span></span>

1. <span data-ttu-id="fa797-111">회사 또는 학교 계정으로 Office 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-111">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="fa797-112">관리 센터의 왼쪽 탐색 창에서 **사용자** > **활성 사용자**로 이동한 다음 사용 가능한 사용자 목록에서 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-112">In the left navigation of the admin center, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fa797-113">동시에 최대 20 명의 사용자에 게 라이선스를 할당 하는 경우 **보기 선택** 드롭다운을 사용 하 여 해당 옵션 중 하나를 선택 하거나 고유한 보기를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-113">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="fa797-114">그런 다음 **편집**을 클릭 하 고 두 **번 다음 라이선스** 를 선택 하 고 **제출을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-114">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span> <span data-ttu-id="fa797-115">Windows Powershell을 사용 하 여 여러 사용자에 게 라이선스를 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-115">You can also assign licenses to multiple users by using Windows Powershell.</span></span> <span data-ttu-id="fa797-116">지침 및 샘플 PowerShell 스크립트는 [비즈니스용 Skype 라이선스 할당](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fa797-116">For instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

3. <span data-ttu-id="fa797-117">작업 창의 **제품 라이선스**에서 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-117">In the Action pane under **Product licenses**, click **Edit**.</span></span>

4. <span data-ttu-id="fa797-118">**제품 라이선스** 페이지에서 **오디오 회의** 를 켠 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-118">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="fa797-119">라이선스에 대 한 자세한 내용은 [비즈니스용 Skype 추가 기능 라이선스](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fa797-119">For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="fa797-120">라이선스를 할당 한 후에는 Microsoft에서 처음에 오디오 회의 공급자로 목록에 표시 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-120">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider.</span></span> <span data-ttu-id="fa797-121">이 문제가 발생 하면 관리 센터에서 로그 아웃 하거나 CTRL + F5를 눌러 브라우저 창을 새로 고칩니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-121">If this happens, either log out of the admin center or press CTRL+F5 to refresh the browser window.</span></span>

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="fa797-122">오디오 회의 사용자에 게 전송 되는 전자 메일 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="fa797-122">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="fa797-123">![비즈니스용 skype](../images/sfb-logo-30x30.png) **관리 센터를 사용 하 여** 비즈니스용 skype 로고를 표시 하는 아이콘</span><span class="sxs-lookup"><span data-stu-id="fa797-123">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="fa797-124">회사 또는 학교 계정으로 Office 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-124">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="fa797-125">**비즈니스용 Skype** > 관리 센터로 이동 하 여 왼쪽 탐색 창에서 **오디오 회의**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-125">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="fa797-126">**Microsoft 브리지 설정** 페이지에서 **오디오 회의 설정이 변경 된 경우 사용자에 게 자동으로 전자 메일 보내기**를 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-126">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="fa797-127">**저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-127">Click **Save**.</span></span>

    <span data-ttu-id="fa797-128">사용자의 오디오 회의 속성으로 이동한 다음 **전자 메일로 회의 정보 보내기를**클릭 하 여 오디오 회의 설정으로 사용자에 게 전자 메일을 보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-128">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span> <span data-ttu-id="fa797-129">전화 회의 ID 및 기본 오디오 회의 전화 번호가 모임 초대에 포함 되지만 PIN이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-129">The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>

    <span data-ttu-id="fa797-130">[오디오 회의 정보를 사용 하 여 사용자에 게 전자 메일 보내기를](send-an-email-to-a-user-with-their-dial-in-information.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fa797-130">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="fa797-131">**Windows PowerShell 사용**</span><span class="sxs-lookup"><span data-stu-id="fa797-131">**Using Windows PowerShell**</span></span>

- <span data-ttu-id="fa797-132">Windows PowerShell을 사용 하 여 다음을 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-132">You can also use the Windows PowerShell and run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="fa797-133">[Set-사용](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) 를 사용 하 여 전자 메일을 포함 한 조직의 기타 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-133">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) to manage other settings for your organization, including email.</span></span>

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="fa797-134">사용자에 게 전송 되는 전자 메일 메시지의 보낸 사람 연락처 정보 변경</span><span class="sxs-lookup"><span data-stu-id="fa797-134">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="fa797-135">실제 전자 메일 주소와 보낸 사람 연락처 정보의 표시 이름을 포함 하 여 사용자에 게 자동으로 전송 되는 전자 메일을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-135">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="fa797-136">기본적으로 전자 메일을 보낸 사람은 Office 365 이지만, Windows PowerShell 및 [사용](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet을 사용 하 여 전자 메일 주소와 표시 이름을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-136">By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="fa797-137">사용자에 게 전자 메일을 보내는 전자 메일 주소를 변경 하려면 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-137">To make changes to the email address that is sending the email to the users, you must:</span></span>

- <span data-ttu-id="fa797-138">_SendEmailFromAddress_ 매개 변수에 전자 메일 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-138">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>

- <span data-ttu-id="fa797-139">이 매개 변수에 전자 메일 표시 이름을 _입력 합니다._</span><span class="sxs-lookup"><span data-stu-id="fa797-139">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>

- <span data-ttu-id="fa797-140">"= _" 매개 변수를_ _True_로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-140">Set the _SendEmailOverride_ parameter to _True_.</span></span>

<span data-ttu-id="fa797-141">전자 메일을 보낸 전자 메일 주소 또는 다음을 실행 하 여 전자 메일의 표시 이름 등 사용자에 게 전송 되는 전자 메일을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-141">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="fa797-142">전자 메일 주소 정보를 변경 하려는 경우 조직의 인바운드 전자 메일 정책에서 사용자 지정 전자 메일 주소에 있는 전자 메일을 허용 하는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-142">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>

<span data-ttu-id="fa797-143">[Set-사용](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet을 사용 하 여 전자 메일을 비롯 한 조직의 다른 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-143">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to manage other settings for your organization, including email.</span></span>

<span data-ttu-id="fa797-144">[오디오 회의 설정이 변경 되 면 사용자에 게 자동으로 전송 되는 전자 메일](emails-sent-to-users-when-their-settings-change.md)을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-144">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="fa797-145">모임 전화 회의 ID 다시 설정</span><span class="sxs-lookup"><span data-stu-id="fa797-145">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="fa797-146">회사 또는 학교 계정으로 Office 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-146">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="fa797-147">**비즈니스용 Skype**> 관리 센터로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-147">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="fa797-148">**비즈니스용 Skype 관리 센터**의 왼쪽 탐색 창에서 **오디오 회의**로 이동한 다음, 작업 창의 **전화 회의 ID**에서 **원래 대로**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="fa797-149">**전화 회의 ID 다시 설정** 창에서 **예**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-149">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="fa797-150">사용자에 게 전자 메일을 보내는 경우 전화 회의 ID가 자동으로 만들어지고 새 전화 회의 ID를 사용 하 여 사용자에 게 전자 메일이 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-150">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="fa797-151">기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-151">It's enabled by default.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="fa797-152">새 전화 회의 ID를 만든 후에는 발신자가 이전 회의 ID를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-152">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="fa797-153">사용자에 게 기존 모임 초대를 다시 예약 하 여 새 회의 ID가 초대에 추가 되었는지 알려 주어 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-153">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="fa797-154">사용자는 비즈니스용 Skype 모임 마이그레이션 도구를 사용 하 여 기존 모임을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-154">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="fa797-155">비즈니스용 skype 모임 업데이트 도구를 다운로드 하 고 설치 하 고 실행 하는 방법에 대 한 자세한 내용은 비즈니스용 [skype 및 Lync 용 모임 업데이트 도구](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), 비즈니스용 [Skype Online, 모임 마이그레이션 도구 (64 비트)](https://go.microsoft.com/fwlink/?LinkID=626047), 비즈니스용 [Skype online, 모임 마이그레이션 도구 (32 비트)](https://www.microsoft.com/download/details.aspx?id=54079)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fa797-155">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/download/details.aspx?id=54079).</span></span>

<span data-ttu-id="fa797-156">[사용자의 전화 회의 ID 다시 설정을](reset-a-conference-id-for-a-user.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fa797-156">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>

## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="fa797-157">회의 이끌이의 PIN 다시 설정</span><span class="sxs-lookup"><span data-stu-id="fa797-157">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="fa797-158">사용자가 예약 하는 각 모임에는 고유한 전화 번호를 할당 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-158">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="fa797-159">전화 회의 ID는 자동으로 만들어지고 사용자에 게 할당 되지만, 사용자가이를 사용 하지 않고 특정 번호로 설정 하려는 경우 또는 사용자가 자신의 전화 회의 ID를 분실 하거나 잃어 버릴 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-159">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="fa797-160">비즈니스용 Skype 관리 센터 및 Windows PowerShell을 사용 하 여 전화 회의 ID를 보고 변경 하 고 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-160">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>


1. <span data-ttu-id="fa797-161">회사 또는 학교 계정으로 Office 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-161">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="fa797-162">**비즈니스용 Skype** > 관리 센터로 이동 하 여 왼쪽 탐색 창에서 **오디오 회의**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-162">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="fa797-163">**사용자**를 클릭 한 다음 PIN을 다시 설정 하려는 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-163">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="fa797-164">작업 창의 **핀**에서 **원래 대로**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-164">In the Action pane, under **PIN**, click **Reset**.</span></span>

<span data-ttu-id="fa797-165">사용자가 오디오 회의를 사용 하도록 설정 하거나 PIN을 다시 설정한 경우 PIN이 포함 된 전자 메일을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-165">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="fa797-166">그러나 자동으로 전자 메일 보내기를 사용 하지 않도록 설정한 경우 PIN 다시 설정 전자 메일을 보내지 않으며 사용자에 게 수동으로 PIN을 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-166">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="fa797-167">PIN은 다시 설정 된 후에만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-167">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="fa797-168">다시 설정 된 후에 표시 된 후에는 사용자 속성에 더 이상 PIN이 표시 되지 않습니다. 대신 \* \* \* \* \*가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-168">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span>

<span data-ttu-id="fa797-169">[오디오 회의 PIN 다시 설정을](reset-the-audio-conferencing-pin.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fa797-169">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="fa797-170">오디오 회의 정보를 사용 하 여 사용자에 게 전자 메일 보내기</span><span class="sxs-lookup"><span data-stu-id="fa797-170">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="fa797-171">회사 또는 학교 계정으로 Office 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-171">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="fa797-172">**비즈니스용 Skype** > 관리 센터로 이동 하 여 왼쪽 탐색 창에서 **오디오 회의**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-172">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="fa797-173">**사용자**를 클릭 한 다음 PIN을 다시 설정 하려는 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-173">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="fa797-174">작업 창에서 **전자 메일을 통해 회의 정보 보내기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-174">In the Action pane, click **Send conference info via email**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fa797-175">이렇게 하면 오디오 회의 PIN이 사용자에 게 전송 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-175">When you do this, the audio conferencing PIN isn't sent to the user.</span></span>

<span data-ttu-id="fa797-176">[오디오 회의 정보를 사용 하 여 사용자에 게 전자 메일 보내기를](send-an-email-to-a-user-with-their-dial-in-information.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fa797-176">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="fa797-177">초대에 포함 된 전화 번호 설정</span><span class="sxs-lookup"><span data-stu-id="fa797-177">Setting the phone numbers included on invites</span></span>

1. <span data-ttu-id="fa797-178">회사 또는 학교 계정으로 Office 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-178">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="fa797-179">**비즈니스용 Skype**> 관리 센터로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-179">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="fa797-180">왼쪽 탐색 창에서 **오디오 회의** > **사용자**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-180">In the left navigation, go to **Audio conferencing** > **Users**.</span></span> <span data-ttu-id="fa797-181">오디오 회의에 사용할 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-181">Select the user that you want to enable for Audio Conferencing.</span></span>

4. <span data-ttu-id="fa797-182">작업 창에서 **유료** 번호를 설정 하 고, 허용 되는 경우 무료 **번호**를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-182">In the Action pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

5. <span data-ttu-id="fa797-183">**저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-183">Click **Save**.</span></span>

<span data-ttu-id="fa797-184">[초대에 포함 된 전화 번호 설정을](set-the-phone-numbers-included-on-invites.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fa797-184">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>


## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="fa797-185">오디오 회의 브리지 설정 선택</span><span class="sxs-lookup"><span data-stu-id="fa797-185">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="fa797-186">**발신자가 모임에 참가 하는 경우의 모임 환경 설정**</span><span class="sxs-lookup"><span data-stu-id="fa797-186">**Set the meeting experience when callers join a meeting**</span></span>


1. <span data-ttu-id="fa797-187">회사 또는 학교 계정으로 Office 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-187">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="fa797-188">**비즈니스용 Skype**> 관리 센터로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-188">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="fa797-189">**비즈니스용 Skype 관리 센터**의 왼쪽 탐색 창에서 **오디오 회의** > **Microsoft bridge 설정**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-189">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="fa797-190">**모임 참가 환경**에서 다음 작업을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-190">Under **Meeting join experience**, select the following actions:</span></span>

   - <span data-ttu-id="fa797-191">**모임 입력 및 종료 알림이 설정 되도록 설정** 이 옵션이 기본적으로 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-191">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="fa797-192">이 확인란의 선택을 취소 하면 이미 모임에 참가 한 사용자는 다른 사용자가 모임을 시작 하거나 떠날 때 알림을 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-192">If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

     <span data-ttu-id="fa797-193">이는 사용자가 비즈니스용 Skype 앱을 사용 하 여 모임에 참가 하는 경우 모임 별로 설정할 수 있으며, 모임의 Skype 모임 **옵션** 메뉴에 사용자 **가 입력 하거나 탈퇴할 때의 알림** 설정을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-193">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business app and they modify the **Announce when people enter or leave** setting in the Skype Meeting **Options** menu of the meeting.</span></span>

   - <span data-ttu-id="fa797-194">**모임에 참가 하기 전에 호출자에 게 자신의 이름을 기록 하도록 요청** 이 옵션이 기본적으로 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-194">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="fa797-195">이 확인란의 선택을 취소 하면 호출자가 모임에 참가 하기 전에 자신의 이름을 기록해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-195">If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>

5. <span data-ttu-id="fa797-196">변경 작업을 수행한 후 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-196">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="fa797-197">[오디오 회의 브리지에 대 한 설정 변경을](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fa797-197">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="fa797-198">**모임의 PIN 길이 설정**</span><span class="sxs-lookup"><span data-stu-id="fa797-198">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="fa797-199">회사 또는 학교 계정으로 Office 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-199">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="fa797-200">**비즈니스용 Skype**> 관리 센터로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-200">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="fa797-201">**비즈니스용 Skype 관리 센터**의 왼쪽 탐색 창에서 **오디오 회의** > **Microsoft bridge 설정**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-201">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="fa797-202">**보안**에서 **pin 길이** 목록에 원하는 pin의 자릿수를 입력 한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-202">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="fa797-203">PIN은 4 ~ 12 자리 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-203">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="fa797-204">기본값은 5입니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-204">The default is 5.</span></span>
    
<span data-ttu-id="fa797-205">[오디오 회의 브리지에 대 한 설정 변경을](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fa797-205">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="fa797-206">**오디오 사용자에 게 전자 메일을 보낼 수 있도록 설정 또는 해제**</span><span class="sxs-lookup"><span data-stu-id="fa797-206">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="fa797-207">회사 또는 학교 계정으로 Office 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-207">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="fa797-208">**비즈니스용 Skype** > 관리 센터로 이동 하 여 왼쪽 탐색 창에서 **오디오 회의**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-208">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="fa797-209">**Microsoft 브리지 설정** 페이지에서 **오디오 회의 설정이 변경 된 경우 사용자에 게 자동으로 전자 메일 보내기**를 선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-209">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="fa797-210">**저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-210">Click **Save**.</span></span>

    <span data-ttu-id="fa797-211">사용자의 오디오 회의 속성으로 이동한 다음 **전자 메일로 회의 정보 보내기를**클릭 하 여 오디오 회의 설정을 사용 하 여 사용자에 게 전자 메일을 보낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-211">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>

    <span data-ttu-id="fa797-212">이렇게 하면 전화 회의 ID 및 전화 회의 전화 번호만 포함 된 전자 메일이 전송 되지만 PIN은 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-212">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

    <span data-ttu-id="fa797-213">[오디오 회의 정보를 사용 하 여 사용자에 게 전자 메일 보내기를](send-an-email-to-a-user-with-their-dial-in-information.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fa797-213">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="fa797-214">오디오 회의 브리지의 기본 (기본) 및 보조 (대체) 언어를 표시 하 고 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-214">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>


1. <span data-ttu-id="fa797-215">회사 또는 학교 계정으로 Office 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-215">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="fa797-216">**비즈니스용 Skype**> 관리 센터로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-216">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="fa797-217">**비즈니스용 Skype 관리 센터**의 왼쪽 탐색 창에서 **오디오 회의**로 이동한 다음 **Microsoft bridge**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-217">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>

4. <span data-ttu-id="fa797-218">목록에서 전화 번호를 선택 하 고, 작업 창에서 **언어 설정을** 클릭 한 다음 **언어 설정** 페이지에서 **기본 언어** 목록 사용을 클릭 하 여 지원 되는 언어의 전체 목록을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-218">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>

    <span data-ttu-id="fa797-219">Microsoft를 오디오 회의 공급자로 선택 하는 경우 지원 되는 기본 및 보조 언어를 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-219">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="fa797-220">목록에서 선택 하는 순서는 호출자에 게 표시 되는 언어의 순서와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-220">The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>

<span data-ttu-id="fa797-221">[오디오 회의에 대 한 자동 전화 교환 언어 설정을](set-auto-attendant-languages-for-audio-conferencing.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fa797-221">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>

## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="fa797-222">오디오 회의 전화 접속 번호 보기</span><span class="sxs-lookup"><span data-stu-id="fa797-222">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="fa797-223">회사 또는 학교 계정으로 Office 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-223">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="fa797-224">**비즈니스용 Skype**> 관리 센터로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-224">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="fa797-225">**비즈니스용 Skype 관리 센터**의 왼쪽 탐색 창에서 **오디오 회의** > **Microsoft bridge**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-225">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**.</span></span> <span data-ttu-id="fa797-226">다음과 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-226">Here you can:</span></span>

   - <span data-ttu-id="fa797-227">오디오 회의에 사용 하도록 Office 365에서 설정한 전화 번호를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-227">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span>

   - <span data-ttu-id="fa797-228">오디오 회의 자동 전화 교환에 사용 되는 위치와 기본 및 보조 언어를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-228">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>

   - <span data-ttu-id="fa797-229">오디오 회의를 사용 하도록 설정 된 사용자에 게 제공 되는 기본 전화 번호를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-229">Select the default phone number that will be given to users when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="fa797-230">그러나 오디오 회의 브리지의 기본 전화 번호가 변경 되는 경우 기존 사용자의 기본 전화 번호가 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-230">However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>

<span data-ttu-id="fa797-231">**오디오 회의** > **사용자** 로 이동 하 여 사용자의 속성을 선택 하 여 조직에서 사용할 수 있는 숫자 목록에서 새 번호를 선택 하 여 사용자의 기본 번호를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-231">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>

<span data-ttu-id="fa797-232">[오디오 회의 번호 목록 보기를](see-a-list-of-audio-conferencing-numbers.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fa797-232">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>

## <a name="see-a-list-of-users-that-are-enabled"></a><span data-ttu-id="fa797-233">사용 하도록 설정 된 사용자 목록 보기</span><span class="sxs-lookup"><span data-stu-id="fa797-233">See a list of users that are enabled</span></span>

1. <span data-ttu-id="fa797-234">회사 또는 학교 계정으로 Office 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-234">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="fa797-235">**비즈니스용 Skype**> 관리 센터로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-235">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="fa797-236">**비즈니스용 Skype 관리 센터**의 왼쪽 탐색 창에서 **오디오 회의**>으로 이동한 다음 **사용자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-236">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>

<span data-ttu-id="fa797-237">[오디오 회의를 사용 하도록 설정 된 사용자 목록 보기를](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fa797-237">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="fa797-238">Windows PowerShell을 사용 하 여 관리 하는 방법을 알고 싶으세요?</span><span class="sxs-lookup"><span data-stu-id="fa797-238">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="fa797-239">Windows PowerShell을 사용 하 여 조직 수준에서 관리할 수 있는 몇 가지 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-239">There are several settings that you can manage at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="fa797-240">이렇게 하면 모든 사용자에 게 설정을 쉽게 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-240">This makes it easy to apply settings to all of your users.</span></span>

<span data-ttu-id="fa797-241">각 cmdlet에 대 한 자세한 도움말을 보려면 [비즈니스용 Skype Online cmdlet](https://go.microsoft.com/fwlink/?LinkId=627324)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fa797-241">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="fa797-242">조직 수준 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-242">Here are the organization-level settings:</span></span>

- <span data-ttu-id="fa797-243">**입력/종료 알림 설정** 기본값은 _$true_입니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-243">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- <span data-ttu-id="fa797-244">**이름 기록 설정** 기본값은 _$true_입니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-244">**Setting name recording** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="fa797-245">**PIN 길이 설정** 기본값은 5입니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-245">**Setting the PIN length** The default is 5.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="fa797-246">**휴대폰에서 전화 접속 모임만 설정** 기본 _$false_입니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-246">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="fa797-247">**사용자에 게 전자 메일을 보낼지 여부 설정** 기본값은 _$true_입니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-247">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="fa797-248">**다른 계정에서 전자 메일을 보낼지 여부 설정** 기본값은 _$false_입니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-248">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="fa797-249">**사용자에 게 전송 되는 전자 메일의 보낸 사람 주소 설정** 기본값은 _$null_입니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-249">**Setting the From address on email that is sent to users** The default is _$null_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="fa797-250">**사용자에 게 전송 되는 전자 메일의 표시 이름 설정** 기본값은 _$null_입니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-250">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

  ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="fa797-251">Windows PowerShell에 대해 자세히 알고 싶은 경우</span><span class="sxs-lookup"><span data-stu-id="fa797-251">Want to know more about Windows PowerShell</span></span>
- <span data-ttu-id="fa797-252">Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-252">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="fa797-253">Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-253">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="fa797-254">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fa797-254">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="fa797-255">Office 365 PowerShell을 사용 해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="fa797-255">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [<span data-ttu-id="fa797-256">Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법</span><span class="sxs-lookup"><span data-stu-id="fa797-256">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

- <span data-ttu-id="fa797-257">Windows PowerShell에는 한 번에 여러 사용자에 게 설정을 변경 하는 경우와 같이 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등의 다양 한 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-257">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="fa797-258">다음 항목에서 이러한 이점에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="fa797-258">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="fa797-259">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="fa797-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="fa797-260">Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="fa797-260">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="fa797-261">Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행</span><span class="sxs-lookup"><span data-stu-id="fa797-261">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

    <span data-ttu-id="fa797-262">비즈니스용 Skype Online 용 Windows PowerShell 모듈을 사용 하면 비즈니스용 Skype Online에 연결 하는 원격 Windows PowerShell 세션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-262">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="fa797-263">이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688) 의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa797-263">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>

## <a name="related-topics"></a><span data-ttu-id="fa797-264">관련 항목</span><span class="sxs-lookup"><span data-stu-id="fa797-264">Related topics</span></span>

[<span data-ttu-id="fa797-265">사용자의 오디오 회의 설정 관리</span><span class="sxs-lookup"><span data-stu-id="fa797-265">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)


