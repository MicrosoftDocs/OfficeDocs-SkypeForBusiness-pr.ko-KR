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
ms.openlocfilehash: 5526bee2bd365a4047e3641ea223941227858d1a
ms.sourcegitcommit: 6acede580649588334aeb48130ab2a5d73245723
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2020
ms.locfileid: "44523121"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="e269f-103">클라우드 음성 메일 설정</span><span class="sxs-lookup"><span data-stu-id="e269f-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="e269f-104">이 문서는 비즈니스의 모든 사용자에 대해 클라우드 보이스 메일 기능을 설정 하려는 [Office 365 관리자](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-104">This article is for the [Office 365 admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="e269f-105">클라우드 보이스 메일은 Exchange 사서함 에서만 depositing 보이스 메일 메시지를 지원 하며 제 3 자 이메일 시스템을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-phone-system-users"></a><span data-ttu-id="e269f-106">클라우드 전용 환경: 전화 시스템 사용자를 위한 클라우드 보이스 메일 설정</span><span class="sxs-lookup"><span data-stu-id="e269f-106">Cloud-only environments: Set up Cloud Voicemail for Phone System users</span></span>

<span data-ttu-id="e269f-107">비즈니스용 Skype Online 및 통화 계획 사용자의 경우, **전화 시스템** 라이선스와 전화 번호를 할당 한 후 사용자에 대 한 클라우드 보이스 메일이 자동으로 설정 되 고 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-107">For Skype for Business Online and Calling Plans users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="e269f-108">전화 시스템 기능이 요금제에 포함 되어 있지 않은 경우에는 **전화 시스템** 추가 기능 라이선스를 구입 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-108">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="e269f-109">Exchange Online 라이선스를 구입 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-109">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="e269f-110">[Microsoft 팀 추가 기능 라이선스](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e269f-110">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="e269f-111">비즈니스용 [Office 365에 대 한 라이선스를 할당 또는 제거](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)하 고, [Microsoft 팀 추가 기능 라이선스를 할당](teams-add-on-licensing/assign-teams-add-on-licenses.md)하 고, 비즈니스 사용자에 게 Exchange Online 라이선스를 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-111">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md), and the Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="e269f-112">이렇게 하면 해당 사용자가 보이스 메일 메시지를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-112">After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="e269f-113">보이스 메일에 대 한 지원은 3 월 2017 (으)로 추가 되었으며 모든 조직 및 사용자에 대해 기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-113">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="e269f-114">Windows PowerShell을 사용 하 고 아래 단계를 수행 하 여 조직의 기록을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-114">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a><span data-ttu-id="e269f-115">Exchange Server 사서함 사용자를 위한 클라우드 보이스 메일 설정</span><span class="sxs-lookup"><span data-stu-id="e269f-115">Set up Cloud Voicemail for Exchange Server Mailbox Users</span></span>

<span data-ttu-id="e269f-116">다음 정보는 클라우드 보이스 메일을 구성 하 여 전화 시스템용으로 온라인 상태 이지만 Exchange Server에서 사서함을 사용 하는 사용자와 작동 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-116">The following information is about configuring Cloud Voicemail to work with users who are online for Phone System but have their mailbox on Exchange Server.</span></span> 
  
1. <span data-ttu-id="e269f-117">전화 시스템 기능이 요금제에 포함 되어 있지 않은 경우에는 **전화 시스템** 추가 기능 라이선스를 구입 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-117">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="e269f-118">[Microsoft 팀 추가 기능 라이선스](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e269f-118">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="e269f-119">비즈니스의 사용자에 게 [Microsoft 팀 추가 기능 라이선스를 할당](teams-add-on-licensing/assign-teams-add-on-licenses.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-119">[Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md) to the people in your business.</span></span>
    
3. <span data-ttu-id="e269f-120">보이스 메일에 대 한 지원은 3 월 2017 (으)로 추가 되었으며 모든 조직 및 사용자에 대해 기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-120">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="e269f-121">Windows PowerShell을 사용 하 고 아래 단계를 수행 하 여 조직의 기록을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-121">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

4. <span data-ttu-id="e269f-122">보이스 메일 메시지는 Exchange Online 보호를 통해 라우팅된 SMTP를 통해 사용자의 Exchange 사서함으로 배달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-122">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="e269f-123">이러한 메시지를 성공적으로 배달 하려면 exchange 서버와 Exchange Online 보호 간에 Exchange 커넥터가 올바르게 구성 되어 있는지 확인 하세요. [커넥터를 사용 하 여 메일 흐름을 구성](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)합니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-123">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection; [Use Connectors to Configure Mail Flow](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> 

6. <span data-ttu-id="e269f-124">인사말 사용자 지정, 비즈니스용 Skype 클라이언트의 시각적 보이스 메일 기능을 사용 하도록 설정 하려면 Exchange Web Services를 통해 Office 365에서 Exchange server 사서함으로 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-124">To enable Voicemail features such as customizing greetings, and visual voicemail in Skype for Business clients, connectivity from Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="e269f-125">이 연결을 사용 하도록 설정 하려면 [exchange 및 Exchange Online 조 직 간의 Oauth 인증 구성](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx)에 설명 된 새 Exchange Oauth 인증 프로토콜을 구성 하거나 EXCHANGE 2013 CU5 이상에서 Exchange 하이브리드 마법사를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-125">To enable this connectivity you must configure the new Exchange Oauth authentication protocol described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span></span> <span data-ttu-id="e269f-126">또한 통합 구성에 설명 된 비즈니스용 Skype Online 및 Exchange server (비즈니스용 [Skype online 및 Exchange server 간](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises))의 통합 및 oauth를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-126">Additionally, you must configure integration and Oauth between Skype for Business Online and Exchange server described in [Configure Integration and OAuth between Skype for Business Online and Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span></span> 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a><span data-ttu-id="e269f-127">비즈니스용 Skype Server 사용자를 위한 클라우드 보이스 메일 설정</span><span class="sxs-lookup"><span data-stu-id="e269f-127">Set up Cloud Voicemail for Skype for Business Server Users</span></span>

<span data-ttu-id="e269f-128">다음 정보는 Exchange 용 인터넷 및 비즈니스용 Skype에 온-프레미스 사용자와 작동 하도록 클라우드 보이스 메일을 구성 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-128">The following information is about configuring Cloud Voicemail to work with users who are online for Exchange and on-premises for Skype for Business.</span></span> 
  
1. <span data-ttu-id="e269f-129">비즈니스 사용자에 게 Exchange Online 라이선스를 구입 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-129">You may need to purchase Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="e269f-130">[Microsoft 팀 추가 기능 라이선스](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e269f-130">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="e269f-131">비즈니스 사용자에 게 Exchange Online 라이선스를 [비즈니스용 Office 365에 대 한 라이선스를 할당 하거나 제거](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) 합니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-131">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="e269f-132">보이스 메일에 대 한 지원은 3 월 2017 (으)로 추가 되었으며 모든 조직 및 사용자에 대해 기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-132">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="e269f-133">Windows PowerShell을 사용 하 고 아래 단계를 수행 하 여 조직의 기록을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-133">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

4. <span data-ttu-id="e269f-134">클라우드 보이스 메일에 대 한 비즈니스용 Skype 서버 사용자를 구성 하려면 [온-프레미스 사용자 용 클라우드 보이스 메일 서비스 계획](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e269f-134">To configure Skype for Business server users for Cloud Voicemail please see [Plan Cloud Voicemail service for on-premises users](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail)</span></span>


> [!NOTE]
> <span data-ttu-id="e269f-135">대리인이 대리인을 대신 하 여 전화를 받으면 클라우드 보이스 메일에서 알림을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-135">When a delegate answers a call on behalf of a delegator, notifications are not available in Cloud Voicemail.</span></span> <span data-ttu-id="e269f-136">사용자는 부재 중 통화에 대 한 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-136">Users can receive notifications for missed calls.</span></span>

## <a name="enabling-protected-voicemail-in-your-organization"></a><span data-ttu-id="e269f-137">조직에서 보호 된 보이스 메일 사용</span><span class="sxs-lookup"><span data-stu-id="e269f-137">Enabling protected voicemail in your organization</span></span>

<span data-ttu-id="e269f-138">다른 사용자가 조직의 사용자에 대 한 보이스 메일 메시지를 떠날 때, 보이스 메일은 사용자의 사서함에 이메일 메시지 첨부 파일로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-138">When someone leaves a voicemail message for a user in your organization, the voicemail is delivered to the user's mailbox as an email message attachment.</span></span> <span data-ttu-id="e269f-139">메일 흐름 규칙을 사용 하 여 메시지 암호화를 적용 하면 이러한 보이스 메일 메시지가 다른 사람에 게 전달 되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-139">Using mail flow rules to apply message encryption, you can prevent those voicemail messages from being forwarded to other recipients.</span></span> <span data-ttu-id="e269f-140">보호 된 음성 메일을 사용 하는 경우 사용자는 음성 메일 사서함으로 전화 하거나 Outlook, 웹용 Outlook 또는 Android 또는 iOS 용 Outlook에서 메시지를 열어 보호 된 음성 메일 메시지를 수신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-140">When you enable protected voicemail, users can listen to protected voicemail messages by calling into their voicemail mailbox or by opening the message in Outlook, Outlook on the web, or in Outlook for Android or iOS.</span></span> <span data-ttu-id="e269f-141">비즈니스용 Skype에서 보호 된 보이스 메일 메시지를 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-141">Protected voicemail messages can't be opened in Skype for Business.</span></span>

<span data-ttu-id="e269f-142">메시지 암호화에 대 한 자세한 내용은 [전자 메일 암호화](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e269f-142">For more information about message encryption, see [Email encryption](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide).</span></span>

<span data-ttu-id="e269f-143">보호 된 보이스 메일을 설정 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-143">To set up protected voicemail, do the following:</span></span>

1. <span data-ttu-id="e269f-144">https://admin.microsoft.com전역 관리자 권한이 있는 계정을 사용 하 여 이동 하 고 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-144">Go to https://admin.microsoft.com and sign in using an account with global administrator permissions.</span></span>
2. <span data-ttu-id="e269f-145">**모두 표시** 를 선택 하 고 **관리 센터**  >  **Exchange**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-145">Select **Show all** and then go to **Admin centers** > **Exchange**.</span></span>
3. <span data-ttu-id="e269f-146">Exchange 관리 센터에서 **메일 흐름**  >  **규칙**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-146">In the Exchange Admin Center, select **Mail flow** > **Rules**.</span></span>
4. <span data-ttu-id="e269f-147">**+** **추가**를 선택한 다음 **Office 365 메시지 암호화 및 권한 보호를 메시지에 적용을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-147">Select **+** **Add**, and then select **Apply Office 365 Message Encryption and rights protection to messages**.</span></span>
5. <span data-ttu-id="e269f-148">새 메일 흐름 규칙의 이름을 입력 하 고 다음 **규칙 적용**에서 **메시지 속성**을 선택 합니다  >  **Include the message type**  >  .**음성 메일**메시지를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-148">Provide a name for the new mail flow rule and then under **Apply this rule if**, select **The message properties** > **Include the message type** > **Voice mail**.</span></span> <span data-ttu-id="e269f-149">**확인을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-149">Select **OK**.</span></span>
6. <span data-ttu-id="e269f-150">**다음 작업 수행**에서 **메시지에 Office 365 메시지 암호화 및 권한 보호 적용** 을 선택한 다음, **하나 선택을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-150">Under **Do the following**, select **Apply Office 365 Message Encryption and rights protection to the message with** and then select **Select one**.</span></span> <span data-ttu-id="e269f-151">**RMS 템플릿에서** **전달 안 함**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-151">Under **RMS template**, select **Do not forward**.</span></span> <span data-ttu-id="e269f-152">**확인** 을 선택한 다음 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-152">Select **OK** and then **Save**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="e269f-153">**RMS 서식 파일** 목록이 비어 있으면 Office 365 메시지 암호화를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-153">If the **RMS template** list is empty, you need to set up Office 365 Message Encryption.</span></span> <span data-ttu-id="e269f-154">Office 365 메시지 암호화를 설정 하는 방법에 대 한 자세한 내용은 다음 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e269f-154">For more information about setting up Office 365 Message Encryption, see the following articles:</span></span>
    > - [<span data-ttu-id="e269f-155">새로운 Office 365 메시지 암호화 기능 설정</span><span class="sxs-lookup"><span data-stu-id="e269f-155">Set up new Office 365 Message Encryption capabilities</span></span>](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [<span data-ttu-id="e269f-156">Azure Information Protection 서식 파일 구성 및 관리</span><span class="sxs-lookup"><span data-stu-id="e269f-156">Configuring and managing templates for Azure Information Protection</span></span>](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)
    > - [<span data-ttu-id="e269f-157">전자 메일에 대 한 전달 옵션 안 함</span><span class="sxs-lookup"><span data-stu-id="e269f-157">Do Not Forward option for emails</span></span>](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="e269f-158">조직에서 음성 메일 정책 설정</span><span class="sxs-lookup"><span data-stu-id="e269f-158">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="e269f-159">비즈니스용 Skype 고객의 경우 Microsoft 팀 호출 정책으로 보이스 메일을 사용 하지 않도록 설정 하면 비즈니스용 Skype 사용자를 위한 보이스 메일 서비스를 사용 하지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-159">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="e269f-160">보이스 메일은 기본적으로 사용 하도록 설정 되어 있으며, 모든 조직 및 사용자에 대해 기본적으로 기록 불경 마스크를 사용할 수 없습니다. 그러나 [CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) 및 [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet을 사용 하 여 컨트롤을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-160">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

<span data-ttu-id="e269f-161">조직의 사용자가 받은 보이스 메일 메시지는 Office 365 조직이 호스팅되는 지역의 transcribed입니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-161">Voicemail messages received by users in your organization are transcribed in the region where your Office 365 organization is hosted.</span></span> <span data-ttu-id="e269f-162">테 넌 트가 호스팅되는 영역은 보이스 메일 메시지를 받는 사용자가 있는 지역과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-162">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="e269f-163">테 넌 트가 호스팅되는 지역을 보려면 [조직 프로필](https://go.microsoft.com/fwlink/p/?linkid=2067339) 페이지로 이동한 다음 **데이터 위치**옆에 있는 **세부 정보 보기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-163">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e269f-164">**새 CsOnlineVoiceMailPolicy** cmdlet을 사용 하 여 기록 및 기록 불경 표시 해제에 대 한 새 정책 인스턴스를 만들 수 없으며, **CsOnlineVoiceMailPolicy** cmdlet을 사용 하 여 기존 정책 인스턴스를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-164">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="e269f-165">음성 메일 정책을 사용 하 여 사용자의 기록 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-165">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="e269f-166">사용할 수 있는 모든 보이스 메일 정책 인스턴스를 보려면 [CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-166">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="e269f-167">**PS C: \\> CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="e269f-167">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![CsOnlineVoiceMailPolicy 결과 창입니다.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="e269f-169">조직의 기록을 끄는 중</span><span class="sxs-lookup"><span data-stu-id="e269f-169">Turning off transcription for your organization</span></span>

<span data-ttu-id="e269f-170">조직에 대 한 기본 기록 설정이 설정 되어 있으므로, [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx)를 사용 하 여 기록을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-170">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="e269f-171">이 작업을 수행 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-171">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="e269f-172">조직의 기록 불경 마스크 설정</span><span class="sxs-lookup"><span data-stu-id="e269f-172">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="e269f-173">조직에서는 기본적으로 기록 불경 마스크를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-173">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="e269f-174">기능을 사용 하도록 설정 해야 하는 경우 [CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx)를 사용 하 여 기록 비속어 마스킹을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-174">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="e269f-175">이 작업을 수행 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-175">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="e269f-176">사용자에 대 한 기록을 끄는 중</span><span class="sxs-lookup"><span data-stu-id="e269f-176">Turning off transcription for a user</span></span>

<span data-ttu-id="e269f-177">사용자 정책은 조직 기본 설정 전에 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-177">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="e269f-178">예를 들어 모든 사용자에 대해 음성 메일을 사용할 수 있는 경우 [CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet을 사용 하 여 특정 사용자에 대 한 기록을 사용 하지 않도록 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-178">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="e269f-179">단일 사용자에 대 한 기록을 사용 하지 않도록 설정 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-179">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="e269f-180">사용자에 대 한 기록 사용 금지 마스크 설정</span><span class="sxs-lookup"><span data-stu-id="e269f-180">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="e269f-181">특정 사용자에 대해 기록 불경 마스크를 사용 하도록 설정 하려면 [CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet을 사용 하 여 특정 사용자에 대 한 기록 불경 마스크를 사용 하도록 설정 하는 정책을 할당 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-181">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="e269f-182">단일 사용자에 대해 기록 불경 마스크를 사용 하도록 설정 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-182">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="e269f-183">Office 365의 보이스 메일 서비스는 음성 메일 정책을 캐시 하 고 4 시간 마다 캐시를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-183">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours.</span></span> <span data-ttu-id="e269f-184">따라서 정책 변경은 적용 하는 데 최대 4 시간까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-184">So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-teams-voicemail-features"></a><span data-ttu-id="e269f-185">사용자가 팀의 보이스 메일 기능을 배우는 데 유용한 정보</span><span class="sxs-lookup"><span data-stu-id="e269f-185">Help your users learn Teams voicemail features</span></span>

<span data-ttu-id="e269f-186">팀의 다른 통화 기능 뿐만 아니라 보이스 메일 설정을 관리 하는 사용자에 게 다음과 같은 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-186">We have the following information for your users on managing their voicemail settings as well as other calling features in Teams:</span></span>

- <span data-ttu-id="e269f-187">[팀에서 통화 설정을 관리](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)합니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-187">[Manage your call settings in Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span> <span data-ttu-id="e269f-188">이 문서에서는 최종 사용자 팀의 모든 통화 기능을 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-188">This article explains how to manage all end-user Teams calling features.</span></span> 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="e269f-189">사용자가 비즈니스용 Skype 보이스 메일 기능 배우기</span><span class="sxs-lookup"><span data-stu-id="e269f-189">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="e269f-190">사용자에 게 비즈니스용 Skype 보이스 메일을 성공적으로 사용 하는 데 도움이 되는 교육 정보와 기사가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-190">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="e269f-191">다음 문서를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-191">Point them to the following articles:</span></span>

- <span data-ttu-id="e269f-192">[비즈니스용 skype 음성 메일 및 옵션 확인](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8):이 문서에서는 비즈니스용 skype에서 음성 메일을 청취 하 고, 음성 사서함을 변경 하 고, 음성 사서함 설정을 변경 하 고, 보이스 메일을 다른 속도로 청취 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e269f-192">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="e269f-193">비즈니스용 Skype 2016 교육</span><span class="sxs-lookup"><span data-stu-id="e269f-193">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="e269f-194">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e269f-194">Related topics</span></span>
[<span data-ttu-id="e269f-195">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="e269f-195">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="e269f-196">Office 365에서 전화 시스템을 사용 하 여 얻을 수 있는 기능</span><span class="sxs-lookup"><span data-stu-id="e269f-196">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="e269f-197">비즈니스용 Skype Server 및 Exchange Server의 마이그레이션 계획</span><span class="sxs-lookup"><span data-stu-id="e269f-197">Plan for Skype for Business Server and Exchange Server migration</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)

