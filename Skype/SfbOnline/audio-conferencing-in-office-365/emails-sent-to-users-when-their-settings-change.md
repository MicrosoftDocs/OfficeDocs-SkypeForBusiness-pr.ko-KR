---
title: 비즈니스용 Skype Online에서 설정이 변경될 때 사용자에게 전송된 전자 메일
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
description: '비즈니스용 Skype Online에서 전화 접속 회의 설정이 변경될 때 사용자에게 전자 메일로 자동으로 전송되는 정보에 대해 자세히 배워야 합니다. '
ms.openlocfilehash: e2f58bfe582b7adc6672c06bec0e90571ff9a96a
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164277"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-skype-for-business-online"></a><span data-ttu-id="1e786-103">비즈니스용 Skype Online에서 설정이 변경될 때 사용자에게 전송된 전자 메일</span><span class="sxs-lookup"><span data-stu-id="1e786-103">Emails sent to users when their settings change in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="1e786-104">Microsoft Teams에서 자동 전자 메일 정보를 찾고 있는 경우 Microsoft Teams에서 설정이 변경될 때 사용자에게 전송된 전자 메일을 [참조하세요.](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams)</span><span class="sxs-lookup"><span data-stu-id="1e786-104">If you're looking for automatic email information in Microsoft Teams, see [Emails sent to users when their settings change in Microsoft Teams](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="1e786-105">오디오 회의 공급자로 Microsoft를 [](set-up-audio-conferencing.md) 사용하여 오디오 회의를 사용하도록 설정된 사용자에게 전자 메일이 자동으로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-105">Emails will be automatically sent to users who are [enabled for Audio Conferencing](set-up-audio-conferencing.md) using Microsoft as the audio conferencing provider.</span></span>
  
<span data-ttu-id="1e786-106">기본적으로 오디오 회의를 사용하도록 설정된 사용자에게 전송되는 전자 메일에는 네 가지 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-106">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="1e786-107">그러나 사용자에게 전송된 전자 메일 수를 제한하려는 경우 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-107">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="1e786-108">Microsoft 365 또는 Office 365의 오디오 회의는 다음의 경우 사용자의 전자 메일로 전자 메일을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-108">Audio Conferencing in Microsoft 365 or Office 365 will send email to your users' email when:</span></span>
  
- <span data-ttu-id="1e786-109">**오디오 회의 라이선스가 할당되거나 오디오 회의 공급자를 Microsoft로 변경할 때 할당됩니다.**</span><span class="sxs-lookup"><span data-stu-id="1e786-109">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>
    
     <span data-ttu-id="1e786-110">이 전자 메일에는 회의 ID, 모임의 기본 전화 회의 전화 번호, 사용자의 오디오 회의 PIN, 사용자의 기존 모임을 업데이트하는 데 사용되는 비즈니스용 Skype Online 모임 업데이트 도구를 사용하는 지침 및 링크가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-110">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="1e786-111">비즈니스용 [Skype 라이선스](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) 할당 또는 오디오 회의 [공급자로 Microsoft 할당을 참조하세요.](assign-microsoft-as-the-audio-conferencing-provider.md)</span><span class="sxs-lookup"><span data-stu-id="1e786-111">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1e786-112">조직에서 동적 회의 ID를 사용하도록 설정한 경우 예약하는 모든 사용자의 모임에는 고유한 회의 ID가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-112">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="1e786-113">조직에서 오디오 회의 동적 [ID를](using-audio-conferencing-dynamic-ids-in-your-organization.md)설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-113">You can set up [Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
    <span data-ttu-id="1e786-114">이 전자 메일의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-114">Here is an example of this email:</span></span>
    
     ![비즈니스용 Skype 라이선스 확인](../images/audio-conferencing-user-enabled.png)
  
    <span data-ttu-id="1e786-116">비즈니스용 Skype 추가 기능 라이선스를 참조하여 비즈니스용 Skype 라이선스에 대한 자세한 [정보를 확인할 수 있습니다.](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="1e786-116">You can find out more about Skype for Business licensing by seeing [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
- <span data-ttu-id="1e786-117">**사용자의 전화 회의 ID 또는 기본 전화 회의 전화 번호가 변경됩니다.**</span><span class="sxs-lookup"><span data-stu-id="1e786-117">**The conference ID or default conference phone number of a user changes.**</span></span>
    
    <span data-ttu-id="1e786-118">이 전자 메일에는 사용자의 기존 모임을 업데이트하는 데 사용되는 비즈니스용 Skype Online 모임 업데이트 도구를 사용하는 전화 회의 ID, 기본 전화 회의 번호 및 지침 및 링크가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-118">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="1e786-119">하지만 이 전자 메일에는 사용자의 오디오 회의 PIN이 포함되어 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-119">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="1e786-120">사용자의 [회의 ID 재설정을 참조합니다.](reset-a-conference-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="1e786-120">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1e786-121">조직에서 동적 회의 ID를 사용하도록 설정한 경우 예약하는 모든 사용자의 모임에는 고유한 회의 ID가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-121">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="1e786-122">조직에서 오디오 회의 동적 [ID를](using-audio-conferencing-dynamic-ids-in-your-organization.md)설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-122">You can set up [Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
    <span data-ttu-id="1e786-123">이 전자 메일의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-123">Here is an example of this email:</span></span>
    
     ![전화 접속 회의 정보가 변경되었습니다.](../images/audio-conferencing-info-change.png)
  
- <span data-ttu-id="1e786-125">**사용자의 오디오 회의 PIN이 다시 설정됩니다.**</span><span class="sxs-lookup"><span data-stu-id="1e786-125">**The audio conferencing PIN of a user is reset.**</span></span>
    
    <span data-ttu-id="1e786-126">이 전자 메일에는 이끌이의 오디오 회의 PIN, 기존 전화 회의 ID 및 사용자의 기본 전화 회의 전화 번호가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-126">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="1e786-127">오디오 [회의 PIN 재설정을 참조합니다.](reset-the-audio-conferencing-pin.md)</span><span class="sxs-lookup"><span data-stu-id="1e786-127">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1e786-128">조직에서 동적 회의 ID를 사용하도록 설정한 경우 예약하는 모든 사용자의 모임에는 고유한 회의 ID가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-128">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="1e786-129">조직에서 오디오 회의 동적 [ID를](using-audio-conferencing-dynamic-ids-in-your-organization.md)설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-129">You can set up [Audio Conferencing dynamic IDs in your organization](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
    <span data-ttu-id="1e786-130">이 전자 메일의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-130">Here is an example of this email:</span></span>
    
     ![전화 접속 회의 PIN이 변경되었습니다.](../images/audio-conferencing-pin-has-changed.png)
  
- <span data-ttu-id="1e786-132">**사용자의 라이선스가 제거되거나 오디오 회의 공급자가 Microsoft에서 다른 공급자 또는 없음으로 변경되면 제거됩니다.**</span><span class="sxs-lookup"><span data-stu-id="1e786-132">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>
    
    <span data-ttu-id="1e786-133">이 문제는  오디오 회의 라이선스가 사용자로부터 제거되거나 사용자의 오디오 회의 공급자를 Microsoft에서 타사 오디오 회의 공급자로 변경하거나 공급자를 **None으로** 설정할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-133">This happens when the **Audio Conferencing** license is removed from a user or when changing the audio conferencing provider of a user from Microsoft to a third-party audio conferencing provider or when setting the provider to **None**.</span></span> <span data-ttu-id="1e786-134">이 전자 메일에는 사용자가 비즈니스용 Skype Online 모임 업데이트 도구를 사용하여 기본 전화 회의 전화 번호 또는 전화 회의 ID와 같은 오디오 회의 특정 정보를 제거할 수 있는 지침과 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-134">This email contains the instructions and information for the user to use the Skype for Business Online Meeting Update Tool to remove audio conferencing specific information, such as the default conference phone number or conference ID.</span></span>
    
    <span data-ttu-id="1e786-135">비즈니스용 [Microsoft 365 앱에 대한](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)라이선스 할당 또는 제거를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e786-135">See [Assign or remove licenses for Microsoft 365 Apps for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
    
    <span data-ttu-id="1e786-136">이 전자 메일의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-136">Here is an example of this email:</span></span>
    
     ![전화 접속 회의가 꺼져 있습니다.](../images/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="1e786-138">전송된 전자 메일 메시지를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-138">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="1e786-139">보낸 메일 주소 및 보낸 메일 정보에 포함된 표시 이름을 포함하여 사용자에게 자동으로 전송되는 전자 메일을 변경할 *수* 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-139">You can make changes to the email that is automatically sent to users including the email address and the display name that is included in the *From* contact information.</span></span> <span data-ttu-id="1e786-140">기본적으로 전자 메일의 보낸 사람이 Microsoft 365 또는 Office 365에서 전송되지만, Windows PowerShell [및 Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet을 사용하여 전자 메일 주소와 표시 이름을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-140">By default, the sender of the emails will be from Microsoft 365 or Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span> <span data-ttu-id="1e786-141">사용자에게 전자 메일을 보내는 전자 메일 주소를 변경하려면 다음을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-141">To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="1e786-142">_SendEmailFromAddress_ 매개 변수에 전자 메일 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-142">Enter the email address in the  _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="1e786-143">_SendEmailFromDisplayName_ 매개 변수에 전자 메일 표시 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-143">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="1e786-144">_SendEmailOverride_ 매개 변수를 _True로 설정_</span><span class="sxs-lookup"><span data-stu-id="1e786-144">Set the  _SendEmailOverride_ parameter to  _True_.</span></span>
    
<span data-ttu-id="1e786-145">다음을 실행하여 사용자에게 전송된 전자 메일(예: 전자 메일이 전송된 전자 메일 주소 및 전자 메일의 표시 이름)을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-145">You can make changes to the email sent to users, such as the email address that the email is sent from and the display name for the email, by running:</span></span>
  
```PowerShell
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  <span data-ttu-id="1e786-146">전자 메일 주소 정보를 변경하려는 경우 사용자 환경의 인바운드 전자 메일 정책에서 주소에서 지정된 사용자 지정에서 오는 전자 메일을 허용하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-146">If you want to change the email address information, you need to make sure that the inbound email policies of your environment allow emails that come from the custom specified from address.</span></span> <span data-ttu-id="1e786-147">보낸 메일 정보를 다시  설정하기로 결정한 경우 전자 메일이 사용자에게 올바르게 전송됐는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-147">If you decide to override the *From* contact information, you should verify that the emails are correctly sent to users.</span></span> <span data-ttu-id="1e786-148">조직의 한 사용자로 이 작업을 테스트하여 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-148">You can do this by testing this with one user in your organization.</span></span>
  
<span data-ttu-id="1e786-149">[Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet을 사용하여 전자 메일을 비롯한 조직의 다른 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-149">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="1e786-150">전자 메일을 보내지 못하게 하려는 경우 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="1e786-150">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="1e786-151">사용자에게 전자 메일 보내기 기능을 사용하지 않도록 설정하면 사용자에게 라이선스가 할당된 경우에도 전자 메일이 전송되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-151">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="1e786-152">이 경우 전화 회의 ID, 기본 회의 전화 번호 및 무엇보다도 오디오 회의 PIN은 사용자에게 전송되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-152">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="1e786-153">이 경우 사용자에게 별도의 전자 메일을 보내거나 전화를 걸고 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-153">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>
  
<span data-ttu-id="1e786-154">기본적으로 전자 메일은 사용자에게 전송되지만, 사용자가 오디오 회의에 대한 전자 메일을 받지 못하게 하려는 경우 비즈니스용 Skype 관리 센터 또는 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e786-154">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use the Skype for Business admin center or Windows PowerShell.</span></span> 
 
<span data-ttu-id="1e786-155">![비즈니스용 Skype 관리 센터를 사용하여 비즈니스용 Skype 로고를 ](../images/sfb-logo-30x30.png) **보여주는 아이콘**  </span><span class="sxs-lookup"><span data-stu-id="1e786-155">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png)  **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="1e786-156">비즈니스용 Skype 관리 **센터의** 왼쪽 탐색 모음에서 **오디오** 회의 Microsoft 브리지  >  **설정으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="1e786-156">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="1e786-157">Microsoft **브리지 설정 페이지에서** 오디오 회의 설정이 변경되는 경우 사용자에게 자동으로 전자 메일을 보내거나 선택 **취소합니다.**</span><span class="sxs-lookup"><span data-stu-id="1e786-157">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their audio conferencing settings change**.</span></span> 
    
3. <span data-ttu-id="1e786-158">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-158">Click **Save**.</span></span> 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
<span data-ttu-id="1e786-159">**다음 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="1e786-159">**Using Windows PowerShell**</span></span>
  
1. <span data-ttu-id="1e786-160">다음을 실행하여 모든 사용자 전자 메일 보내기 기능을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-160">Run the following to disable sending all of your users email:</span></span>
    
   ```PowerShell
   Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $false
   ```

<span data-ttu-id="1e786-161">[Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet을 사용하여 전자 메일을 비롯한 조직의 다른 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-161">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="1e786-162">이 전자 메일에 대해 알아야 할 다른 것은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="1e786-162">What else should you know about this email?</span></span>

- <span data-ttu-id="1e786-163">사용자에게 자동으로 전자 메일을 보내거나 사용하지 않도록 설정하는 데 대한 자세한 내용은 오디오 회의 설정이 변경될 때 전자 메일 보내기 사용 또는 사용 안 [을 참조하세요.](enable-or-disable-sending-emails-when-their-settings-change.md)</span><span class="sxs-lookup"><span data-stu-id="1e786-163">For more on enabling and disabling automatically sending email to your users, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
    
- <span data-ttu-id="1e786-164">사용자가 오디오 정보를 잃어버려 모든 오디오 정보를 사용자에게 보낼 수 있는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-164">Sometimes users lose their audio information and you need to be able to send them all of their audio information to them.</span></span> <span data-ttu-id="1e786-165">비즈니스용 Skype 관리 센터를 사용하고 사용자의 오디오  회의 속성 아래에서 전자 메일을 통해 전화 회의 정보 보내기를 클릭하여 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-165">You can do this by using the Skype for Business admin center and clicking **Send conference info via email** under the audio conferencing properties for a user.</span></span> <span data-ttu-id="1e786-166">오디오 회의 정보가 있는 사용자에게 전자 메일 [보내기를 참조하세요.](send-an-email-to-a-user-with-their-dial-in-information.md)</span><span class="sxs-lookup"><span data-stu-id="1e786-166">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span> <span data-ttu-id="1e786-167">그러나 이 정보는 오디오 회의 PIN을 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-167">However, this information doesn't include the audio conferencing PIN.</span></span>
    
    <span data-ttu-id="1e786-168">다음은 전송될 이 전자 메일의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-168">Here is an example of this email that will be sent to them:</span></span>
    
     ![전화 접속 회의 전자 메일](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="1e786-170">사용자 계정으로 관리하는 방법을 알고 Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="1e786-170">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="1e786-171">기본적으로 전자 메일의 보낸 사람이 Microsoft 365 또는 Office 365에서 전송되지만, Windows PowerShell [및 Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet을 사용하여 전자 메일 주소와 표시 이름을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-171">By default, the sender of the emails will be from Microsoft 365 or Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span>
    
- <span data-ttu-id="1e786-172">Windows PowerShell 관리는 사용자 및 사용자가 허용되거나 허용되지 않는 작업을 관리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-172">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="1e786-173">이 Windows PowerShell 여러 작업을 수행할 때 일상적인 작업을 간소화할 수 있는 단일 관리 지점을 사용하여 Microsoft 365 또는 Office 365를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-173">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="1e786-174">다음 항목을 Windows PowerShell 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e786-174">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="1e786-175">Microsoft 365 또는 Office 365 PowerShell을 사용하는 이유</span><span class="sxs-lookup"><span data-stu-id="1e786-175">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="1e786-176">Microsoft 365 또는 Office 365를 관리하는 가장 좋은 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e786-176">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="1e786-177">Windows PowerShell Microsoft 365 관리 센터를 사용하는 것 이상으로 속도, 단순성 및 생산성에 많은 이점이 있습니다. 예를 들어 한 번으로 많은 사용자를 위한 설정을 변경할 때도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-177">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="1e786-178">다음 항목에서 이러한 이점에 대해 자세히 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-178">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="1e786-179">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="1e786-179">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="1e786-180">비즈니스 Windows PowerShell 사용하여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="1e786-180">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="1e786-181">비즈니스용 Windows PowerShell Skype Online 관리 작업을 수행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-181">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="1e786-182">비즈니스 Windows PowerShell용 Skype Online 모듈을 사용하면 비즈니스용 Skype Online에 Windows PowerShell 원격 세션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e786-182">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="1e786-183">64비트 컴퓨터에서만 지원되는 이 모듈은 비즈니스용 Skype Online용 Windows PowerShell 모듈의 Microsoft 다운로드 센터에서 [다운로드할 수 있습니다.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="1e786-183">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="1e786-184">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1e786-184">Related topics</span></span>

[<span data-ttu-id="1e786-185">오디오 회의 설정이 변경되면 전자 메일 보내기 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="1e786-185">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[<span data-ttu-id="1e786-186">오디오 회의 정보를 사용하여 사용자에게 전자 메일 보내기</span><span class="sxs-lookup"><span data-stu-id="1e786-186">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)
