---
title: 클라우드 음성 사서함 설정
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
description: '사용자에 대한 클라우드 음성 사서함 방법을 자세히 알아보습니다. '
ms.openlocfilehash: c6fbd02e30c5be0280b05088a1cec281c2534039
ms.sourcegitcommit: 31c5b9cd3d4f500e1f9d7823052dae8f8c298b1e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52901915"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="d8f6d-103">클라우드 음성 사서함 설정</span><span class="sxs-lookup"><span data-stu-id="d8f6d-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="d8f6d-104">이 문서는 Microsoft 365 Office 365 모든 사용자에 대한 클라우드 음성 사서함 [](/microsoft-365/admin/add-users/about-admin-roles) 관리자 역할에 설명된 클라우드 음성 사서함 관리자에 대한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d8f6d-104">This article is for the Microsoft 365 or Office 365 admin as described in [About admin roles](/microsoft-365/admin/add-users/about-admin-roles) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="d8f6d-105">클라우드 음성 사서함 사서함에서만 음성 메일 메시지를 Exchange 지원하며 타사 전자 메일 시스템을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f6d-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

> [!NOTE]
> <span data-ttu-id="d8f6d-106">대리인이 위임자를 대신하여 호출에 응답하면 알림은 위임자에서 사용할 수 클라우드 음성 사서함.</span><span class="sxs-lookup"><span data-stu-id="d8f6d-106">When a delegate answers a call on behalf of a delegator, notifications are not available in Cloud Voicemail.</span></span> <span data-ttu-id="d8f6d-107">사용자는 부재 중 전화에 대한 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f6d-107">Users can receive notifications for missed calls.</span></span>

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a><span data-ttu-id="d8f6d-108">클라우드 전용 환경: 클라우드 음성 사서함 사용자에 대한 전화 시스템 설정</span><span class="sxs-lookup"><span data-stu-id="d8f6d-108">Cloud-only environments: Set up Cloud Voicemail for Online Phone System users</span></span>

<span data-ttu-id="d8f6d-109">Online 전화 시스템 사용자의 경우 클라우드 음성 사서함 라이선스를 사용자에게 할당한 후 사용자에게 전화 시스템 자동으로  설정되고 프로비전됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8f6d-109">For Online Phone System users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license to the users.</span></span> 

> [!NOTE]
> <span data-ttu-id="d8f6d-110">온라인 비즈니스용 Skype 전화 시스템 제공된 전화 번호를 사용하려면 [Set-CsUser -HostedVoicemail](/powershell/module/skype/set-csuser?view=skype-ps)$True.</span><span class="sxs-lookup"><span data-stu-id="d8f6d-110">For Online Skype for Business Phone System users with on-premises provided phone numbers, you may need to enable hosted voice mail with [Set-CsUser -HostedVoicemail $True](/powershell/module/skype/set-csuser?view=skype-ps).</span></span> 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a><span data-ttu-id="d8f6d-111">사서함 사용자에 클라우드 음성 사서함 Exchange Server 설정</span><span class="sxs-lookup"><span data-stu-id="d8f6d-111">Set up Cloud Voicemail for Exchange Server Mailbox Users</span></span>

<span data-ttu-id="d8f6d-112">다음 정보는 온라인에 클라우드 음성 사서함 사용자와 함께 작업할 수 있도록 전화 시스템 사서함을 Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="d8f6d-112">The following information is about configuring Cloud Voicemail to work with users who are online for Phone System but have their mailbox on Exchange Server.</span></span> 
  
1. <span data-ttu-id="d8f6d-113">음성 메일 메시지는 사용자의 Exchange 통해 라우팅된 SMTP를 통해 Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="d8f6d-113">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="d8f6d-114">이러한 메시지를 성공적으로 배달하도록 설정하려면 Exchange 서버와 서버 간에 커넥터가 올바르게 Exchange 있는지 Exchange Online Protection. [커넥터를 사용하여 메일](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)Flow.</span><span class="sxs-lookup"><span data-stu-id="d8f6d-114">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection; [Use Connectors to Configure Mail Flow](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> 

2. <span data-ttu-id="d8f6d-115">클라이언트에서 인사말 사용자 지정 및 비즈니스용 Skype 음성 메일과 같은 Voicemail 기능을 사용하도록 설정하려면 웹 서비스를 통해 Microsoft 365 Office 365 Exchange 서버 사서함에 Exchange 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f6d-115">To enable Voicemail features such as customizing greetings and visual voicemail in Skype for Business clients, connectivity from Microsoft 365 or Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="d8f6d-116">이 연결을 사용하도록 설정하려면 Exchange 조직과 조직 간에 [OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)인증 구성에 설명된 새 Exchange Exchange Online 인증 프로토콜을 구성하거나 2013 CU5 이상에서 Exchange 하이브리드 마법사를 Exchange 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f6d-116">To enable this connectivity, you must configure the new Exchange Oauth authentication protocol described in [Configure OAuth authentication between Exchange and Exchange Online organizations](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span></span> <span data-ttu-id="d8f6d-117">또한 온라인 및 비즈니스용 Skype 및 OAuth 구성에 설명된 비즈니스용 Skype 및 Exchange 서버 간에 통합 및 [Oauth를 비즈니스용 Skype 구성해야 Exchange Server.](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)</span><span class="sxs-lookup"><span data-stu-id="d8f6d-117">Additionally, you must configure integration and Oauth between Skype for Business Online and Exchange server described in [Configure Integration and OAuth between Skype for Business Online and Exchange Server](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span></span> 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a><span data-ttu-id="d8f6d-118">사용자에 클라우드 음성 사서함 비즈니스용 Skype 서버 설정</span><span class="sxs-lookup"><span data-stu-id="d8f6d-118">Set up Cloud Voicemail for Skype for Business Server Users</span></span>

<span data-ttu-id="d8f6d-119">비즈니스용 Skype 서버 사용자를 클라우드 음성 사서함 프레미스 사용자에 대한 클라우드 음성 사서함 계획 [을 참조합니다.](/skypeforbusiness/hybrid/plan-cloud-voicemail)</span><span class="sxs-lookup"><span data-stu-id="d8f6d-119">To configure Skype for Business server users for Cloud Voicemail, please see [Plan Cloud Voicemail service for on-premises users](/skypeforbusiness/hybrid/plan-cloud-voicemail).</span></span>

## <a name="enabling-protected-voicemail-in-your-organization"></a><span data-ttu-id="d8f6d-120">조직에서 보호된 음성메일 사용</span><span class="sxs-lookup"><span data-stu-id="d8f6d-120">Enabling protected voicemail in your organization</span></span>

<span data-ttu-id="d8f6d-121">조직의 사용자에 대한 음성 메일 메시지를 남기면 음성 메일이 사용자의 사서함에 전자 메일 메시지 첨부 파일로 배달됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8f6d-121">When someone leaves a voicemail message for a user in your organization, the voicemail is delivered to the user's mailbox as an email message attachment.</span></span> <span data-ttu-id="d8f6d-122">메일 흐름 규칙을 사용하여 메시지 암호화를 적용하면 해당 음성 메일 메시지가 다른 받는 사람에게 전달되지 못하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f6d-122">Using mail flow rules to apply message encryption, you can prevent those voicemail messages from being forwarded to other recipients.</span></span> <span data-ttu-id="d8f6d-123">보호된 음성 메일을 사용하도록 설정하면 사용자는 음성 메일 사서함에 전화를 걸거나 웹에서 메시지를 열거나 웹에서 Outlook Outlook Android 또는 iOS용 Outlook 수신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f6d-123">When you enable protected voicemail, users can listen to protected voicemail messages by calling into their voicemail mailbox or by opening the message in Outlook, Outlook on the web, or in Outlook for Android or iOS.</span></span> <span data-ttu-id="d8f6d-124">보호된 음성 메일 메시지를 비즈니스용 Skype 또는 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d8f6d-124">Protected voicemail messages can't be opened in Skype for Business or Microsoft Teams.</span></span>

<span data-ttu-id="d8f6d-125">메시지 암호화에 대한 자세한 내용은 전자 [메일 암호화를 참조하세요.](/microsoft-365/compliance/email-encryption?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="d8f6d-125">For more information about message encryption, see [Email encryption](/microsoft-365/compliance/email-encryption?view=o365-worldwide).</span></span>

<span data-ttu-id="d8f6d-126">보호된 음성메일을 설정하기 위해 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f6d-126">To set up protected voicemail, do the following:</span></span>

1. <span data-ttu-id="d8f6d-127">전역 관리자 권한으로 계정으로 이동하여 https://admin.microsoft.com 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f6d-127">Go to https://admin.microsoft.com and sign in using an account with global administrator permissions.</span></span>
2. <span data-ttu-id="d8f6d-128">모두 **표시를** 선택한 다음 관리 센터로  >  **Exchange.**</span><span class="sxs-lookup"><span data-stu-id="d8f6d-128">Select **Show all** and then go to **Admin centers** > **Exchange**.</span></span>
3. <span data-ttu-id="d8f6d-129">관리 Exchange 메일 흐름 규칙을   >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d8f6d-129">In the Exchange Admin Center, select **Mail flow** > **Rules**.</span></span>
4. <span data-ttu-id="d8f6d-130">추가 **+** **를** 선택한 다음 메시지에 Office 365 메시지 암호화 **권한 보호 적용을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d8f6d-130">Select **+** **Add**, and then select **Apply Office 365 Message Encryption and rights protection to messages**.</span></span>
5. <span data-ttu-id="d8f6d-131">새 메일 흐름 규칙에 대한 이름을 입력한 다음 이 규칙 적용에서 **메시지** 속성에 메시지 형식 음성 메일  >  **포함 을**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d8f6d-131">Provide a name for the new mail flow rule and then under **Apply this rule if**, select **The message properties** > **Include the message type** > **Voice mail**.</span></span> <span data-ttu-id="d8f6d-132">확인 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d8f6d-132">Select **OK**.</span></span>
6. <span data-ttu-id="d8f6d-133">다음 **작업을 진행할** 때 메시지에 Office 365 메시지 암호화 권한 보호 적용을 선택한 다음 을  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d8f6d-133">Under **Do the following**, select **Apply Office 365 Message Encryption and rights protection to the message with** and then select **Select one**.</span></span> <span data-ttu-id="d8f6d-134">**RMS 템플릿에서** 전달 **안 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="d8f6d-134">Under **RMS template**, select **Do not forward**.</span></span> <span data-ttu-id="d8f6d-135">**확인을** 선택한 다음 을 **저장합니다.**</span><span class="sxs-lookup"><span data-stu-id="d8f6d-135">Select **OK** and then **Save**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="d8f6d-136">**RMS 템플릿 목록이** 비어 있는 경우 메시지 암호화를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f6d-136">If the **RMS template** list is empty, you need to set up Message Encryption.</span></span> <span data-ttu-id="d8f6d-137">메시지 암호화 설정에 대한 자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8f6d-137">For more information about setting up Message Encryption, see the following articles:</span></span>
    > - [<span data-ttu-id="d8f6d-138">새 메시지 암호화 기능 설정</span><span class="sxs-lookup"><span data-stu-id="d8f6d-138">Set up new Message Encryption capabilities</span></span>](/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [<span data-ttu-id="d8f6d-139">Azure Information Protection에 대한 템플릿 구성 및 관리</span><span class="sxs-lookup"><span data-stu-id="d8f6d-139">Configuring and managing templates for Azure Information Protection</span></span>](/information-protection/deploy-use/configure-policy-templates)
    > - [<span data-ttu-id="d8f6d-140">전자 메일에 대한 전달 안 하세요 옵션</span><span class="sxs-lookup"><span data-stu-id="d8f6d-140">Do Not Forward option for emails</span></span>](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="help-your-users-learn-teams-voicemail-features"></a><span data-ttu-id="d8f6d-141">사용자가 음성 Teams 학습하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8f6d-141">Help your users learn Teams voicemail features</span></span>

<span data-ttu-id="d8f6d-142">음성메일 설정 관리 및 기타 통화 기능 관리에 대한 사용자에 대한 정보는 다음과 Teams.</span><span class="sxs-lookup"><span data-stu-id="d8f6d-142">We have the following information for your users on managing their voicemail settings as well as other calling features in Teams:</span></span>

- <span data-ttu-id="d8f6d-143">[에서](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)통화 설정을 Teams.</span><span class="sxs-lookup"><span data-stu-id="d8f6d-143">[Manage your call settings in Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span> <span data-ttu-id="d8f6d-144">이 문서에서는 모든 최종 사용자 호출 기능을 관리하는 Teams 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f6d-144">This article explains how to manage all end-user Teams calling features.</span></span> 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="d8f6d-145">사용자가 음성 비즈니스용 Skype 학습할 수 있도록 지원</span><span class="sxs-lookup"><span data-stu-id="d8f6d-145">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="d8f6d-146">사용자가 음성 비즈니스용 Skype 수 있도록 도와주는 교육 정보 및 문서가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8f6d-146">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="d8f6d-147">다음 문서를 지적합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f6d-147">Point them to the following articles:</span></span>

- <span data-ttu-id="d8f6d-148">[비즈니스용 Skype](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)음성 메일 및 옵션 확인: 이 문서에서는 음성 메일에서 음성 메일 비즈니스용 Skype 음성 메일 인사말을 변경하고, 음성 메일 설정을 변경하고, 다른 속도로 음성 메일에 귀를 기울이는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d8f6d-148">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="d8f6d-149">비즈니스용 Skype 2016 교육</span><span class="sxs-lookup"><span data-stu-id="d8f6d-149">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="d8f6d-150">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d8f6d-150">Related topics</span></span>
[<span data-ttu-id="d8f6d-151">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="d8f6d-151">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="d8f6d-152">다음은 통화 시스템 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="d8f6d-152">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="d8f6d-153">비즈니스용 Skype Server 및 Exchange Server의 마이그레이션 계획</span><span class="sxs-lookup"><span data-stu-id="d8f6d-153">Plan for Skype for Business Server and Exchange Server migration</span></span>](/SkypeForBusiness/hybrid/plan-um-migration)
