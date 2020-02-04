---
title: 비즈니스용 Skype Online에서 설정이 변경 될 때 사용자에 게 전송 되는 전자 메일
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
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
description: '비즈니스용 Skype Online에서 전화 접속 회의 설정이 변경 되는 경우 전자 메일을 통해 사용자에 게 자동으로 전송 되는 정보에 대해 알아봅니다. '
ms.openlocfilehash: 167b083c1cc212a6d301b0cfb2012ef9d639727d
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41707233"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-skype-for-business-online"></a><span data-ttu-id="612dd-103">비즈니스용 Skype Online에서 설정이 변경 될 때 사용자에 게 전송 되는 전자 메일</span><span class="sxs-lookup"><span data-stu-id="612dd-103">Emails sent to users when their settings change in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="612dd-104">Microsoft 팀에서 자동 전자 메일 정보를 찾고 있는 경우 [Microsoft 팀에서 설정이 변경 될 때 사용자에 게 전송 되는 전자 메일](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="612dd-104">If you're looking for automatic email information in Microsoft Teams, see [Emails sent to users when their settings change in Microsoft Teams](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="612dd-105">전자 메일은 오디오 회의 공급자로 Microsoft를 사용 하 여 [오디오 회의를 사용 하도록 설정](set-up-audio-conferencing.md) 된 사용자에 게 자동으로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-105">Emails will be automatically sent to users who are [enabled for Audio Conferencing](set-up-audio-conferencing.md) using Microsoft as the audio conferencing provider.</span></span>
  
<span data-ttu-id="612dd-106">기본적으로 오디오 회의를 사용 하도록 설정 된 사용자에 게 전송 되는 전자 메일에는 네 가지 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-106">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="612dd-107">그러나 사용자에 게 전송 되는 전자 메일의 수를 제한 하려는 경우이 기능을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-107">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="612dd-108">Office 365의 오디오 회의는 다음과 같은 경우 사용자의 전자 메일에 전자 메일을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-108">Audio Conferencing in Office 365 will send email to your users' email when:</span></span>
  
- <span data-ttu-id="612dd-109">**오디오 회의 라이선스가 자신에 게 할당 되거나 오디오 회의 공급자를 Microsoft로 변경 하는 경우**</span><span class="sxs-lookup"><span data-stu-id="612dd-109">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>
    
     <span data-ttu-id="612dd-110">이 전자 메일에는 전화 회의 ID, 모임에 대 한 기본 컨퍼런스 전화 번호, 사용자 용 오디오 회의 PIN, 지침 및 링크를 통해 비즈니스용 Skype Online 모임 업데이트 도구를 사용 하는 방법 및이에 대 한 기존 모임을 업데이트 하는 데 사용 되는 링크가 포함 되어 있습니다. 클릭할.</span><span class="sxs-lookup"><span data-stu-id="612dd-110">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="612dd-111">[비즈니스용 Skype 라이선스 할당](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) 또는 [Microsoft를 오디오 회의 공급자로 지정을](assign-microsoft-as-the-audio-conferencing-provider.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="612dd-111">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="612dd-112">조직에서 동적 전화 회의 Id를 사용할 수 있는 경우, 자신이 예약한 모든 사용자의 모임에 고유한 전화 회의 Id가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-112">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="612dd-113">[조직에서 오디오 회의 동적 id](using-audio-conferencing-dynamic-ids-in-your-organization.md)를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-113">You can set up [Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
    <span data-ttu-id="612dd-114">다음은이 전자 메일의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-114">Here is an example of this email:</span></span>
    
     ![비즈니스용 Skype 라이선스 확인](../images/audio-conferencing-user-enabled.png)
  
    <span data-ttu-id="612dd-116">비즈니스용 [skype 추가 기능 라이선스](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)를 보면 비즈니스용 skype 라이선스에 대해 자세히 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-116">You can find out more about Skype for Business licensing by seeing [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
- <span data-ttu-id="612dd-117">**사용자의 전화 회의 ID 또는 기본 컨퍼런스 전화 번호가 변경 되었습니다.**</span><span class="sxs-lookup"><span data-stu-id="612dd-117">**The conference ID or default conference phone number of a user changes.**</span></span>
    
    <span data-ttu-id="612dd-118">이 전자 메일에는 전화 회의 ID, 기본 컨퍼런스 전화 번호, 사용자의 기존 모임을 업데이트 하는 데 사용 되는 비즈니스용 Skype Online 모임 업데이트 도구를 사용 하는 지침 및 링크가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-118">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="612dd-119">그러나이 전자 메일에는 사용자의 오디오 회의 PIN이 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-119">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="612dd-120">[사용자의 전화 회의 ID 다시 설정을](reset-a-conference-id-for-a-user.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="612dd-120">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="612dd-121">조직에서 동적 전화 회의 Id를 사용할 수 있는 경우, 자신이 예약한 모든 사용자의 모임에 고유한 전화 회의 Id가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-121">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="612dd-122">[조직에서 오디오 회의 동적 id](using-audio-conferencing-dynamic-ids-in-your-organization.md)를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-122">You can set up [Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
    <span data-ttu-id="612dd-123">다음은이 전자 메일의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-123">Here is an example of this email:</span></span>
    
     ![전화 접속 회의 정보가 변경 되었습니다.](../images/audio-conferencing-info-change.png)
  
- <span data-ttu-id="612dd-125">**사용자의 오디오 회의 PIN이 다시 설정 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="612dd-125">**The audio conferencing PIN of a user is reset.**</span></span>
    
    <span data-ttu-id="612dd-126">이 전자 메일에는 이끌이의 오디오 회의 PIN, 기존 회의 ID 및 사용자의 기본 컨퍼런스 전화 번호가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-126">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="612dd-127">[오디오 회의 PIN 다시 설정을](reset-the-audio-conferencing-pin.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="612dd-127">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="612dd-128">조직에서 동적 전화 회의 Id를 사용할 수 있는 경우, 자신이 예약한 모든 사용자의 모임에 고유한 전화 회의 Id가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-128">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="612dd-129">[조직에서 오디오 회의 동적 id](using-audio-conferencing-dynamic-ids-in-your-organization.md)를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-129">You can set up [Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
    <span data-ttu-id="612dd-130">다음은이 전자 메일의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-130">Here is an example of this email:</span></span>
    
     ![전화 접속 회의 PIN이 변경 되었습니다.](../images/audio-conferencing-pin-has-changed.png)
  
- <span data-ttu-id="612dd-132">**사용자의 라이선스가 제거 되거나 오디오 회의 공급자가 Microsoft에서 다른 공급자 또는 없음으로 변경 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="612dd-132">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>
    
    <span data-ttu-id="612dd-133">이는 사용자가 **오디오 회의** 라이선스를 제거 하거나 사용자의 오디오 회의 공급자를 Microsoft에서 타사 오디오 회의 공급자로 변경 하거나 공급자를 **없음**으로 설정할 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-133">This happens when the **Audio Conferencing** license is removed from a user or when changing the audio conferencing provider of a user from Microsoft to a third-party audio conferencing provider or when setting the provider to **None**.</span></span> <span data-ttu-id="612dd-134">이 전자 메일에는 사용자가 비즈니스용 Skype Online 모임 업데이트 도구를 사용 하 여 기본 컨퍼런스 전화 번호 또는 전화 회의 ID와 같은 오디오 회의 관련 정보를 제거할 수 있는 지침 및 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-134">This email contains the instructions and information for the user to use the Skype for Business Online Meeting Update Tool to remove audio conferencing specific information, such as the default conference phone number or conference ID.</span></span>
    
    <span data-ttu-id="612dd-135">[비즈니스용 Office 365에 대 한 라이선스 할당 또는 제거를](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="612dd-135">See [Assign or remove licenses for Office 365 for business](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
    
    <span data-ttu-id="612dd-136">다음은이 전자 메일의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-136">Here is an example of this email:</span></span>
    
     ![전화 접속 회의 기능이 꺼져 있습니다.](../images/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="612dd-138">자신에 게 전송 되는 전자 메일 메시지 변경 하기</span><span class="sxs-lookup"><span data-stu-id="612dd-138">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="612dd-139">*보낸* 사람 연락처 정보에 포함 된 전자 메일 주소와 표시 이름을 포함 하 여 사용자에 게 자동으로 전송 되는 전자 메일을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-139">You can make changes to the email that is automatically sent to users including the email address and the display name that is included in the *From* contact information.</span></span> <span data-ttu-id="612dd-140">기본적으로 전자 메일을 보낸 사람은 Office 365에 있지만, Windows PowerShell 및 [사용](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet을 사용 하 여 전자 메일 주소와 표시 이름을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-140">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span> <span data-ttu-id="612dd-141">사용자에 게 전자 메일을 보내는 전자 메일 주소를 변경 하려면 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-141">To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="612dd-142">_SendEmailFromAddress_ 매개 변수에 전자 메일 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-142">Enter the email address in the  _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="612dd-143">이 매개 변수에 전자 메일 표시 이름을 _입력 합니다._</span><span class="sxs-lookup"><span data-stu-id="612dd-143">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="612dd-144">"= _" 매개 변수를_ _True_로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-144">Set the  _SendEmailOverride_ parameter to  _True_.</span></span>
    
<span data-ttu-id="612dd-145">다음을 실행 하 여 전자 메일을 보낸 전자 메일 주소와 전자 메일의 표시 이름 같은 사용자에 게 전송 되는 전자 메일을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-145">You can make changes to the email sent to users, such as the email address that the email is sent from and the display name for the email, by running:</span></span>
  
```PowerShell
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  <span data-ttu-id="612dd-146">전자 메일 주소 정보를 변경 하려는 경우 해당 환경의 인바운드 전자 메일 정책에서 사용자 지정 된 보낸 사람 주소에서 보낸 전자 메일을 허용 하는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-146">If you want to change the email address information, you need to make sure that the inbound email policies of your environment allow emails that come from the custom specified from address.</span></span> <span data-ttu-id="612dd-147">*보낸 사람* 연락처 정보를 재정의 하기로 결정 한 경우 전자 메일이 사용자에 게 올바르게 전송 되었는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-147">If you decide to override the *From* contact information, you should verify that the emails are correctly sent to users.</span></span> <span data-ttu-id="612dd-148">조직의 한 사용자와이를 테스트 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-148">You can do this by testing this with one user in your organization.</span></span>
  
<span data-ttu-id="612dd-149">[Set-사용](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet을 사용 하 여 전자 메일을 비롯 한 조직의 다른 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-149">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="612dd-150">전자 메일을 보낼 수 없도록 하려면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="612dd-150">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="612dd-151">사용자에 게 전자 메일 보내기를 사용 하지 않도록 설정 하면 사용자에 게 라이선스가 할당 되지 않은 경우에도 전자 메일이 전송 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-151">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="612dd-152">이 경우 전화 회의 ID, 기본 회의 전화 번호, 그리고 더 중요 한 것은 사용자에 게 오디오 회의 PIN이 전송 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-152">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="612dd-153">이런 경우에는 별도의 전자 메일을 보내거나 전화를 걸어 사용자에 게 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-153">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>
  
<span data-ttu-id="612dd-154">기본적으로 전자 메일은 사용자에 게 전송 되지만 오디오 회의에 대 한 전자 메일을 받지 않도록 하려면 비즈니스용 Skype 관리 센터 또는 Windows PowerShell을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-154">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use the Skype for Business admin center or Windows PowerShell.</span></span> 
 
<span data-ttu-id="612dd-155">![비즈니스용 skype](../images/sfb-logo-30x30.png)**관리 센터를 사용 하 여** 비즈니스용 skype 로고를 표시 하는 아이콘  </span><span class="sxs-lookup"><span data-stu-id="612dd-155">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png)  **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="612dd-156">**비즈니스용 Skype 관리 센터**의 왼쪽 탐색 창에서 **오디오 회의** > **Microsoft bridge 설정**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-156">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="612dd-157">**Microsoft 브리지 설정** 페이지에서 **오디오 회의 설정이 변경 된 경우 자동으로 전자 메일을 사용자에 게 보내기를**선택 하거나 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-157">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their audio conferencing settings change**.</span></span> 
    
3. <span data-ttu-id="612dd-158">**저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-158">Click **Save**.</span></span> 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
<span data-ttu-id="612dd-159">**Windows PowerShell 사용**</span><span class="sxs-lookup"><span data-stu-id="612dd-159">**Using Windows PowerShell**</span></span>
  
1. <span data-ttu-id="612dd-160">모든 사용자의 전자 메일을 보낼 수 없도록 설정 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-160">Run the following to disable sending all of your users email:</span></span>
    
   ```PowerShell
   Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $false
   ```

<span data-ttu-id="612dd-161">[Set-사용](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet을 사용 하 여 전자 메일을 비롯 한 조직의 다른 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-161">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="612dd-162">이 전자 메일에 대해 알아야 할 기타 사항</span><span class="sxs-lookup"><span data-stu-id="612dd-162">What else should you know about this email?</span></span>

- <span data-ttu-id="612dd-163">사용자에 게 자동으로 전자 메일을 보내는 기능을 사용 하거나 사용 하지 않도록 설정 하는 방법에 대 한 자세한 내용은 [오디오 회의 설정이 변경 되는 경우 전자 메일 보내기를 사용](enable-or-disable-sending-emails-when-their-settings-change.md)</span><span class="sxs-lookup"><span data-stu-id="612dd-163">For more on enabling and disabling automatically sending email to your users, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
    
- <span data-ttu-id="612dd-164">사용자가 오디오 정보를 분실 한 경우에는 모든 오디오 정보를 전자 메일로 보낼 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-164">Sometimes users lose their audio information and you need to be able to send them all of their audio information to them.</span></span> <span data-ttu-id="612dd-165">비즈니스용 Skype 관리 센터를 사용 하 고 사용자의 오디오 회의 속성에서 **전자 메일을 통해 회의 정보 보내기를** 클릭 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-165">You can do this by using the Skype for Business admin center and clicking **Send conference info via email** under the audio conferencing properties for a user.</span></span> <span data-ttu-id="612dd-166">[오디오 회의 정보를 사용 하 여 사용자에 게 전자 메일 보내기를](send-an-email-to-a-user-with-their-dial-in-information.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="612dd-166">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span> <span data-ttu-id="612dd-167">그러나이 정보에는 오디오 회의 PIN이 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-167">However, this information doesn't include the audio conferencing PIN.</span></span>
    
    <span data-ttu-id="612dd-168">다음은 여기에 전송 되는 전자 메일의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-168">Here is an example of this email that will be sent to them:</span></span>
    
     ![전화 접속 회의 전자 메일](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="612dd-170">Windows PowerShell을 사용 하 여 관리 하는 방법을 알고 싶으세요?</span><span class="sxs-lookup"><span data-stu-id="612dd-170">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="612dd-171">기본적으로 전자 메일을 보낸 사람은 Office 365에 있지만, Windows PowerShell 및 [사용](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet을 사용 하 여 전자 메일 주소와 표시 이름을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-171">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span>
    
- <span data-ttu-id="612dd-172">Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-172">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="612dd-173">Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-173">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="612dd-174">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="612dd-174">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="612dd-175">Office 365 PowerShell을 사용 해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="612dd-175">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="612dd-176">Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법</span><span class="sxs-lookup"><span data-stu-id="612dd-176">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="612dd-177">Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-177">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="612dd-178">다음 항목에서 이러한 이점에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="612dd-178">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="612dd-179">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="612dd-179">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="612dd-180">Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="612dd-180">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="612dd-181">Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행</span><span class="sxs-lookup"><span data-stu-id="612dd-181">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="612dd-182">비즈니스용 Skype Online 용 Windows PowerShell 모듈을 사용 하면 비즈니스용 Skype Online에 연결 하는 원격 Windows PowerShell 세션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-182">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="612dd-183">이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688) 의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612dd-183">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="612dd-184">관련 주제</span><span class="sxs-lookup"><span data-stu-id="612dd-184">Related topics</span></span>

[<span data-ttu-id="612dd-185">오디오 회의 설정이 변경되면 전자 메일 보내기 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="612dd-185">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[<span data-ttu-id="612dd-186">오디오 회의 정보를 사용하여 사용자에게 전자 메일 보내기</span><span class="sxs-lookup"><span data-stu-id="612dd-186">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)
