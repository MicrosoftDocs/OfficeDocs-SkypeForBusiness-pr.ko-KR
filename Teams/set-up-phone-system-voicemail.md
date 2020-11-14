---
title: 클라우드 음성 메일 설정
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: wasseemh, phans
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: '사용자를 위해 클라우드 보이스 메일을 설정 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: df8e6d5962e3bff2148165466400e90ee3a4607d
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031074"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="82ff1-103">클라우드 음성 메일 설정</span><span class="sxs-lookup"><span data-stu-id="82ff1-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="82ff1-104">이 문서는 비즈니스의 모든 사용자에 게 클라우드 보이스 메일 기능을 설정 하려는 [관리자 역할에 대 한](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) 설명 대로 Microsoft 365 또는 Office 365 관리자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-104">This article is for the Microsoft 365 or Office 365 admin as described in [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="82ff1-105">클라우드 보이스 메일은 Exchange 사서함 에서만 depositing 보이스 메일 메시지를 지원 하며 제 3 자 이메일 시스템을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

> [!NOTE]
> <span data-ttu-id="82ff1-106">대리인이 대리인을 대신 하 여 전화를 받으면 클라우드 보이스 메일에서 알림을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-106">When a delegate answers a call on behalf of a delegator, notifications are not available in Cloud Voicemail.</span></span> <span data-ttu-id="82ff1-107">사용자는 부재 중 통화에 대 한 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-107">Users can receive notifications for missed calls.</span></span>

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a><span data-ttu-id="82ff1-108">클라우드 전용 환경: 온라인 전화 시스템 사용자를 위한 클라우드 보이스 메일 설정</span><span class="sxs-lookup"><span data-stu-id="82ff1-108">Cloud-only environments: Set up Cloud Voicemail for Online Phone System users</span></span>

<span data-ttu-id="82ff1-109">온라인 전화 시스템 사용자의 경우 사용자에 게 **전화 시스템** 라이선스를 할당 한 후에는 사용자에 대해 클라우드 보이스 메일이 자동으로 설정 되 고 프로 비전 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-109">For Online Phone System users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license to the users.</span></span> 

> [!NOTE]
> <span data-ttu-id="82ff1-110">온-프레미스 전화 번호와 함께 제공 되는 비즈니스용 Skype 휴대폰 시스템 사용자의 경우 [Set-CsUser-HostedVoicemail $True](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)를 사용 하 여 호스팅 음성 메일을 사용 하도록 설정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-110">For Online Skype for Business Phone System users with on-premises provided phone numbers, you may need to enable hosted voice mail with [Set-CsUser -HostedVoicemail $True](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps).</span></span> 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a><span data-ttu-id="82ff1-111">Exchange Server 사서함 사용자를 위한 클라우드 보이스 메일 설정</span><span class="sxs-lookup"><span data-stu-id="82ff1-111">Set up Cloud Voicemail for Exchange Server Mailbox Users</span></span>

<span data-ttu-id="82ff1-112">다음 정보는 클라우드 보이스 메일을 구성 하 여 전화 시스템용으로 온라인 상태 이지만 Exchange Server에서 사서함을 사용 하는 사용자와 작동 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-112">The following information is about configuring Cloud Voicemail to work with users who are online for Phone System but have their mailbox on Exchange Server.</span></span> 
  
1. <span data-ttu-id="82ff1-113">보이스 메일 메시지는 Exchange Online 보호를 통해 라우팅된 SMTP를 통해 사용자의 Exchange 사서함으로 배달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-113">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="82ff1-114">이러한 메시지를 성공적으로 배달 하려면 exchange 서버와 Exchange Online 보호 간에 Exchange 커넥터가 올바르게 구성 되어 있는지 확인 하세요. [커넥터를 사용 하 여 메일 흐름을 구성](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)합니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-114">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection; [Use Connectors to Configure Mail Flow](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> 

2. <span data-ttu-id="82ff1-115">비즈니스용 Skype 클라이언트에서 인사말 및 시각적 보이스 메일을 사용자 지정 하는 등의 보이스 메일 기능을 사용 하려면 Exchange Web Services를 통해 Microsoft 365 또는 Office 365에서 Exchange server 사서함으로 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-115">To enable Voicemail features such as customizing greetings and visual voicemail in Skype for Business clients, connectivity from Microsoft 365 or Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="82ff1-116">이 연결을 사용 하도록 설정 하려면 [exchange 및 Exchange Online 조 직 간 Oauth 인증 구성](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx)에서 설명한 새로운 exchange Oauth 인증 프로토콜을 구성 하거나 EXCHANGE 2013 CU5 이상에서 Exchange 하이브리드 마법사를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-116">To enable this connectivity, you must configure the new Exchange Oauth authentication protocol described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span></span> <span data-ttu-id="82ff1-117">또한 통합 구성에 설명 된 비즈니스용 Skype Online 및 Exchange server (비즈니스용 [Skype online 및 Exchange server 간](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises))의 통합 및 oauth를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-117">Additionally, you must configure integration and Oauth between Skype for Business Online and Exchange server described in [Configure Integration and OAuth between Skype for Business Online and Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span></span> 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a><span data-ttu-id="82ff1-118">비즈니스용 Skype Server 사용자를 위한 클라우드 보이스 메일 설정</span><span class="sxs-lookup"><span data-stu-id="82ff1-118">Set up Cloud Voicemail for Skype for Business Server Users</span></span>

<span data-ttu-id="82ff1-119">클라우드 보이스 메일에 대 한 비즈니스용 Skype 서버 사용자를 구성 하려면 [온-프레미스 사용자 용 클라우드 보이스 메일 관리 서비스 계획](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="82ff1-119">To configure Skype for Business server users for Cloud Voicemail, please see [Plan Cloud Voicemail service for on-premises users](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail).</span></span>

## <a name="enabling-protected-voicemail-in-your-organization"></a><span data-ttu-id="82ff1-120">조직에서 보호 된 보이스 메일 사용</span><span class="sxs-lookup"><span data-stu-id="82ff1-120">Enabling protected voicemail in your organization</span></span>

<span data-ttu-id="82ff1-121">다른 사용자가 조직의 사용자에 대 한 보이스 메일 메시지를 떠날 때, 보이스 메일은 사용자의 사서함에 이메일 메시지 첨부 파일로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-121">When someone leaves a voicemail message for a user in your organization, the voicemail is delivered to the user's mailbox as an email message attachment.</span></span> <span data-ttu-id="82ff1-122">메일 흐름 규칙을 사용 하 여 메시지 암호화를 적용 하면 이러한 보이스 메일 메시지가 다른 사람에 게 전달 되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-122">Using mail flow rules to apply message encryption, you can prevent those voicemail messages from being forwarded to other recipients.</span></span> <span data-ttu-id="82ff1-123">보호 된 음성 메일을 사용 하는 경우 사용자는 음성 메일 사서함으로 전화 하거나 Outlook, 웹용 Outlook 또는 Android 또는 iOS 용 Outlook에서 메시지를 열어 보호 된 음성 메일 메시지를 수신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-123">When you enable protected voicemail, users can listen to protected voicemail messages by calling into their voicemail mailbox or by opening the message in Outlook, Outlook on the web, or in Outlook for Android or iOS.</span></span> <span data-ttu-id="82ff1-124">비즈니스용 Skype에서 보호 된 보이스 메일 메시지를 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-124">Protected voicemail messages can't be opened in Skype for Business.</span></span>

<span data-ttu-id="82ff1-125">메시지 암호화에 대 한 자세한 내용은 [전자 메일 암호화](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="82ff1-125">For more information about message encryption, see [Email encryption](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide).</span></span>

<span data-ttu-id="82ff1-126">보호 된 보이스 메일을 설정 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-126">To set up protected voicemail, do the following:</span></span>

1. <span data-ttu-id="82ff1-127">https://admin.microsoft.com전역 관리자 권한이 있는 계정을 사용 하 여 이동 하 고 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-127">Go to https://admin.microsoft.com and sign in using an account with global administrator permissions.</span></span>
2. <span data-ttu-id="82ff1-128">**모두 표시** 를 선택 하 고 **관리 센터**  >  **Exchange** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-128">Select **Show all** and then go to **Admin centers** > **Exchange**.</span></span>
3. <span data-ttu-id="82ff1-129">Exchange 관리 센터에서 **메일 흐름**  >  **규칙** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-129">In the Exchange Admin Center, select **Mail flow** > **Rules**.</span></span>
4. <span data-ttu-id="82ff1-130">**+** **추가** 를 선택한 다음 **Office 365 메시지 암호화 및 권한 보호를 메시지에 적용을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-130">Select **+** **Add** , and then select **Apply Office 365 Message Encryption and rights protection to messages**.</span></span>
5. <span data-ttu-id="82ff1-131">새 메일 흐름 규칙의 이름을 입력 하 고 다음 **규칙 적용** 에서 **메시지 속성** 을 선택 합니다  >  **Include the message type**  >  . **음성 메일** 메시지를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-131">Provide a name for the new mail flow rule and then under **Apply this rule if** , select **The message properties** > **Include the message type** > **Voice mail**.</span></span> <span data-ttu-id="82ff1-132">**확인을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-132">Select **OK**.</span></span>
6. <span data-ttu-id="82ff1-133">**다음 작업 수행** 에서 **메시지에 Office 365 메시지 암호화 및 권한 보호 적용** 을 선택한 다음, **하나 선택을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-133">Under **Do the following** , select **Apply Office 365 Message Encryption and rights protection to the message with** and then select **Select one**.</span></span> <span data-ttu-id="82ff1-134">**RMS 템플릿에서** **전달 안 함** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-134">Under **RMS template** , select **Do not forward**.</span></span> <span data-ttu-id="82ff1-135">**확인** 을 선택한 다음 **저장** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-135">Select **OK** and then **Save**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="82ff1-136">**RMS 서식 파일** 목록이 비어 있으면 메시지 암호화를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-136">If the **RMS template** list is empty, you need to set up Message Encryption.</span></span> <span data-ttu-id="82ff1-137">메시지 암호화 설정에 대 한 자세한 내용은 다음 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="82ff1-137">For more information about setting up Message Encryption, see the following articles:</span></span>
    > - [<span data-ttu-id="82ff1-138">새 메시지 암호화 기능 설정</span><span class="sxs-lookup"><span data-stu-id="82ff1-138">Set up new Message Encryption capabilities</span></span>](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [<span data-ttu-id="82ff1-139">Azure Information Protection 서식 파일 구성 및 관리</span><span class="sxs-lookup"><span data-stu-id="82ff1-139">Configuring and managing templates for Azure Information Protection</span></span>](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)
    > - [<span data-ttu-id="82ff1-140">전자 메일에 대 한 전달 옵션 안 함</span><span class="sxs-lookup"><span data-stu-id="82ff1-140">Do Not Forward option for emails</span></span>](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="82ff1-141">조직에서 음성 메일 정책 설정</span><span class="sxs-lookup"><span data-stu-id="82ff1-141">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="82ff1-142">비즈니스용 Skype 고객의 경우 Microsoft 팀 호출 정책으로 보이스 메일을 사용 하지 않도록 설정 하면 비즈니스용 Skype 사용자를 위한 보이스 메일 서비스를 사용 하지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-142">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="82ff1-143">보이스 메일은 기본적으로 사용 하도록 설정 되어 있으며, 모든 조직 및 사용자에 대해 기본적으로 기록 불경 마스크를 사용할 수 없습니다. 그러나 [CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) 및 [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet을 사용 하 여 컨트롤을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-143">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

<span data-ttu-id="82ff1-144">조직의 사용자가 받은 보이스 메일 메시지는 Microsoft 365 또는 Office 365 조직이 호스팅되는 지역에 transcribed 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-144">Voicemail messages received by users in your organization are transcribed in the region where your Microsoft 365 or Office 365 organization is hosted.</span></span> <span data-ttu-id="82ff1-145">테 넌 트가 호스팅되는 영역은 보이스 메일 메시지를 받는 사용자가 있는 지역과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-145">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="82ff1-146">테 넌 트가 호스팅되는 지역을 보려면 [조직 프로필](https://go.microsoft.com/fwlink/p/?linkid=2067339) 페이지로 이동한 다음 **데이터 위치** 옆에 있는 **세부 정보 보기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-146">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="82ff1-147">**새 CsOnlineVoiceMailPolicy** cmdlet을 사용 하 여 기록 및 기록 불경 표시 해제에 대 한 새 정책 인스턴스를 만들 수 없으며, **CsOnlineVoiceMailPolicy** cmdlet을 사용 하 여 기존 정책 인스턴스를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-147">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="82ff1-148">음성 메일 정책을 사용 하 여 사용자의 기록 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-148">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="82ff1-149">사용할 수 있는 모든 보이스 메일 정책 인스턴스를 보려면 [CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-149">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="82ff1-150">**PS C: \\> CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="82ff1-150">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolicy 결과 창](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="82ff1-152">조직의 기록을 끄는 중</span><span class="sxs-lookup"><span data-stu-id="82ff1-152">Turning off transcription for your organization</span></span>

<span data-ttu-id="82ff1-153">조직에 대 한 기본 기록 설정이 설정 되어 있으므로, [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx)를 사용 하 여 기록을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-153">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="82ff1-154">이 작업을 수행 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-154">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="82ff1-155">조직의 기록 불경 마스크 설정</span><span class="sxs-lookup"><span data-stu-id="82ff1-155">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="82ff1-156">조직에서는 기본적으로 기록 불경 마스크를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-156">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="82ff1-157">기능을 사용 하도록 설정 해야 하는 경우 [CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx)를 사용 하 여 기록 비속어 마스킹을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-157">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="82ff1-158">이 작업을 수행 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-158">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="82ff1-159">사용자에 대 한 기록을 끄는 중</span><span class="sxs-lookup"><span data-stu-id="82ff1-159">Turning off transcription for a user</span></span>

<span data-ttu-id="82ff1-160">사용자 정책은 조직 기본 설정 전에 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-160">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="82ff1-161">예를 들어 모든 사용자에 대해 음성 메일을 사용할 수 있는 경우 [CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet을 사용 하 여 특정 사용자에 대 한 기록을 사용 하지 않도록 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-161">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="82ff1-162">단일 사용자에 대 한 기록을 사용 하지 않도록 설정 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-162">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="82ff1-163">사용자에 대 한 기록 사용 금지 마스크 설정</span><span class="sxs-lookup"><span data-stu-id="82ff1-163">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="82ff1-164">특정 사용자에 대해 기록 불경 마스크를 사용 하도록 설정 하려면 [CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet을 사용 하 여 특정 사용자에 대 한 기록 불경 마스크를 사용 하도록 설정 하는 정책을 할당 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-164">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="82ff1-165">단일 사용자에 대해 기록 불경 마스크를 사용 하도록 설정 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-165">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="82ff1-166">Microsoft 365 및 Office 365의 보이스 메일 서비스는 음성 메일 정책을 캐시 하 고 4 시간 마다 캐시를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-166">The voicemail service in Microsoft 365 and Office 365 caches voicemail policies and updates the cache every 4 hours.</span></span> <span data-ttu-id="82ff1-167">따라서 정책 변경은 적용 하는 데 최대 4 시간까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-167">So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-teams-voicemail-features"></a><span data-ttu-id="82ff1-168">사용자가 팀의 보이스 메일 기능을 배우는 데 유용한 정보</span><span class="sxs-lookup"><span data-stu-id="82ff1-168">Help your users learn Teams voicemail features</span></span>

<span data-ttu-id="82ff1-169">팀의 다른 통화 기능 뿐만 아니라 보이스 메일 설정을 관리 하는 사용자에 게 다음과 같은 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-169">We have the following information for your users on managing their voicemail settings as well as other calling features in Teams:</span></span>

- <span data-ttu-id="82ff1-170">[팀에서 통화 설정을 관리](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)합니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-170">[Manage your call settings in Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span> <span data-ttu-id="82ff1-171">이 문서에서는 최종 사용자 팀의 모든 통화 기능을 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-171">This article explains how to manage all end-user Teams calling features.</span></span> 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="82ff1-172">사용자가 비즈니스용 Skype 보이스 메일 기능 배우기</span><span class="sxs-lookup"><span data-stu-id="82ff1-172">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="82ff1-173">사용자에 게 비즈니스용 Skype 보이스 메일을 성공적으로 사용 하는 데 도움이 되는 교육 정보와 기사가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-173">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="82ff1-174">다음 문서를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-174">Point them to the following articles:</span></span>

- <span data-ttu-id="82ff1-175">[비즈니스용 skype 음성 메일 및 옵션 확인](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8):이 문서에서는 비즈니스용 skype에서 음성 메일을 청취 하 고, 음성 사서함을 변경 하 고, 음성 사서함 설정을 변경 하 고, 보이스 메일을 다른 속도로 청취 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-175">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="82ff1-176">비즈니스용 Skype 2016 교육</span><span class="sxs-lookup"><span data-stu-id="82ff1-176">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="82ff1-177">관련 주제</span><span class="sxs-lookup"><span data-stu-id="82ff1-177">Related topics</span></span>
[<span data-ttu-id="82ff1-178">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="82ff1-178">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="82ff1-179">다음은 전화 시스템 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="82ff1-179">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="82ff1-180">비즈니스용 Skype Server 및 Exchange Server의 마이그레이션 계획</span><span class="sxs-lookup"><span data-stu-id="82ff1-180">Plan for Skype for Business Server and Exchange Server migration</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)
