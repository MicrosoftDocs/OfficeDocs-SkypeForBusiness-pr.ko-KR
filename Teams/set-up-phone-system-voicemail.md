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
ms.openlocfilehash: dc771847db8dca52d22b4c1db1b8ae585b99f8e4
ms.sourcegitcommit: 2d44f1a673316daf0aca3149571b24a63ca72772
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/11/2020
ms.locfileid: "43227502"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="e7174-103">클라우드 음성 메일 설정</span><span class="sxs-lookup"><span data-stu-id="e7174-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="e7174-104">이 문서는 비즈니스의 모든 사용자에 대해 클라우드 보이스 메일 기능을 설정 하려는 [Office 365 관리자](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-104">This article is for the [Office 365 admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="e7174-105">클라우드 보이스 메일은 Exchange 사서함 에서만 depositing 보이스 메일 메시지를 지원 하며 제 3 자 이메일 시스템을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a><span data-ttu-id="e7174-106">클라우드 전용 환경: 클라우드 보이스 메일 설정</span><span class="sxs-lookup"><span data-stu-id="e7174-106">Cloud-only environments: Set up Cloud Voicemail</span></span>

<span data-ttu-id="e7174-107">비즈니스용 Skype Online 및 통화 계획 사용자의 경우, **전화 시스템** 라이선스와 전화 번호를 할당 한 후 사용자에 대 한 클라우드 보이스 메일이 자동으로 설정 되 고 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-107">For Skype for Business Online and Calling Plans users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="e7174-108">전화 시스템 기능이 요금제에 포함 되어 있지 않은 경우에는 **전화 시스템** 추가 기능 라이선스를 구입 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-108">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="e7174-109">Exchange Online 라이선스를 구입 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-109">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="e7174-110">[Microsoft 팀 추가 기능 라이선스](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e7174-110">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="e7174-111">비즈니스용 [Office 365에 대 한 라이선스를 할당 또는 제거](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)하 고, [Microsoft 팀 라이선스 할당](assign-teams-licenses.md)및 Exchange Online 라이선스를 비즈니스 사용자에 게 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-111">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="e7174-112">이렇게 하면 해당 사용자가 보이스 메일 메시지를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-112">After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="e7174-113">보이스 메일에 대 한 지원은 3 월 2017 (으)로 추가 되었으며 모든 조직 및 사용자에 대해 기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-113">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="e7174-114">Windows PowerShell을 사용 하 고 아래 단계를 수행 하 여 조직의 기록을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-114">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="e7174-115">온-프레미스 환경에서 사용 하는 전화 시스템</span><span class="sxs-lookup"><span data-stu-id="e7174-115">Phone System with on-premises environments</span></span>

<span data-ttu-id="e7174-116">다음 정보는 온-프레미스 호출 계획 환경과 작동 하도록 클라우드 보이스 메일을 구성 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-116">The following information is about configuring Cloud Voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="e7174-117">전화 시스템 기능이 요금제에 포함 되어 있지 않은 경우에는 **전화 시스템** 추가 기능 라이선스를 구입 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-117">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="e7174-118">또한 Exchange Online 라이선스를 구입 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-118">You also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="e7174-119">[Microsoft 팀 추가 기능 라이선스](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e7174-119">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="e7174-120">비즈니스용 [Office 365에 대 한 라이선스를 할당 또는 제거](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)하 고, [Microsoft 팀 라이선스 할당](assign-teams-licenses.md)및 Exchange Online 라이선스를 비즈니스 사용자에 게 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-120">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="e7174-121">사용자를 위해 배포 된 온-프레미스 PSTN 호출 솔루션에 맞는 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="e7174-121">Follow instructions matching on-premises PSTN calling solution deployed for your users.</span></span> <span data-ttu-id="e7174-122">Cloud Connector Edition의 경우 [비즈니스용 Skype 클라우드 커넥터 구성 가이드](https://technet.microsoft.com/library/mt605228.aspx)의 **전화 시스템 음성 및 보이스 메일 서비스 사용** 섹션의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-122">For Cloud Connector Edition, follow instructions in the **Enable users for Phone System voice and voicemail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/library/mt605228.aspx).</span></span> <span data-ttu-id="e7174-123">비즈니스용 Skype 서버와 PSTN 통화를 하려면, [온-프레미스 엔터프라이즈 음성을 사용할 수 있도록 설정](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises)합니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-123">For PSTN calling with Skype for Business Server, follow [Enable the users for Enterprise Voice on premises](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises).</span></span> <span data-ttu-id="e7174-124">직접 라우팅에 대 한 자세한 내용은 전화 번호 구성 및 [다이렉트 라우팅 구성](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail)의 **enterprise voice and 보이스 메일 사용** 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e7174-124">For Teams Direct Routing, follow  the **Configure the phone number and enable enterprise voice and voicemail** section of [Configure Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail).</span></span>

4. <span data-ttu-id="e7174-125">보이스 메일에 대 한 지원은 3 월 2017 (으)로 추가 되었으며 모든 조직 및 사용자에 대해 기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-125">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users.</span></span> <span data-ttu-id="e7174-126">Windows PowerShell을 사용 하 고 아래 단계를 수행 하 여 조직의 기록을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-126">You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

5. <span data-ttu-id="e7174-127">보이스 메일 메시지는 Exchange Online 보호를 통해 라우팅된 SMTP를 통해 사용자의 Exchange 사서함으로 배달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-127">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="e7174-128">이러한 메시지를 성공적으로 배달 하려면 exchange 서버와 Exchange Online 보호 간에 Exchange 커넥터가 올바르게 구성 되어 있는지 확인 하세요. [커넥터를 사용 하 여 메일 흐름을 구성](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)합니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-128">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection; [Use Connectors to Configure Mail Flow](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> 

6. <span data-ttu-id="e7174-129">인사말 사용자 지정, 비즈니스용 Skype 클라이언트의 시각적 보이스 메일 기능을 사용 하도록 설정 하려면 Exchange Web Services를 통해 Office 365에서 Exchange server 사서함으로 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-129">To enable Voicemail features such as customizing greetings, and visual voicemail in Skype for Business clients, connectivity from Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="e7174-130">이 연결을 사용 하도록 설정 하려면 [exchange 및 Exchange Online 조 직 간의 Oauth 인증 구성](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx)에 설명 된 새 Exchange Oauth 인증 프로토콜을 구성 하거나 EXCHANGE 2013 CU5 이상에서 Exchange 하이브리드 마법사를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-130">To enable this connectivity you must configure the new Exchange Oauth authentication protocol described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span></span> <span data-ttu-id="e7174-131">또한 통합 구성에 설명 된 비즈니스용 Skype Online 및 Exchange server (비즈니스용 [Skype online 및 Exchange server 간](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises))의 통합 및 oauth를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-131">Additionally, you must configure integration and Oauth between Skype for Business Online and Exchange server described in [Configure Integration and OAuth between Skype for Business Online and Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span></span> 

> [!NOTE]
> <span data-ttu-id="e7174-132">대리인이 대리인을 대신 하 여 전화를 받으면 클라우드 보이스 메일에서 알림을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-132">When a delegate answers a call on behalf of a delegator, notifications are not available in Cloud Voicemail.</span></span> <span data-ttu-id="e7174-133">사용자는 부재 중 통화에 대 한 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-133">Users can receive notifications for missed calls.</span></span>

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="e7174-134">조직에서 음성 메일 정책 설정</span><span class="sxs-lookup"><span data-stu-id="e7174-134">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="e7174-135">비즈니스용 Skype 고객의 경우 Microsoft 팀 호출 정책으로 보이스 메일을 사용 하지 않도록 설정 하면 비즈니스용 Skype 사용자를 위한 보이스 메일 서비스를 사용 하지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-135">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="e7174-136">보이스 메일은 기본적으로 사용 하도록 설정 되어 있으며, 모든 조직 및 사용자에 대해 기본적으로 기록 불경 마스크를 사용할 수 없습니다. 그러나 [CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) 및 [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet을 사용 하 여 컨트롤을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-136">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

<span data-ttu-id="e7174-137">조직의 사용자가 받은 보이스 메일 메시지는 Office 365 테 넌 트가 호스팅되는 지역의 transcribed입니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-137">Voicemail messages received by users in your organization are transcribed in the region where your Office 365 tenant is hosted.</span></span> <span data-ttu-id="e7174-138">테 넌 트가 호스팅되는 영역은 보이스 메일 메시지를 받는 사용자가 있는 지역과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-138">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="e7174-139">테 넌 트가 호스팅되는 지역을 보려면 [조직 프로필](https://go.microsoft.com/fwlink/p/?linkid=2067339) 페이지로 이동한 다음 **데이터 위치**옆에 있는 **세부 정보 보기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-139">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7174-140">**새 CsOnlineVoiceMailPolicy** cmdlet을 사용 하 여 기록 및 기록 불경 표시 해제에 대 한 새 정책 인스턴스를 만들 수 없으며, **CsOnlineVoiceMailPolicy** cmdlet을 사용 하 여 기존 정책 인스턴스를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-140">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="e7174-141">음성 메일 정책을 사용 하 여 사용자의 기록 설정을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-141">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="e7174-142">사용할 수 있는 모든 보이스 메일 정책 인스턴스를 보려면 [CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-142">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="e7174-143">**PS C:\\> CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="e7174-143">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![CsOnlineVoiceMailPolicy 결과 창입니다.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="e7174-145">조직의 기록을 끄는 중</span><span class="sxs-lookup"><span data-stu-id="e7174-145">Turning off transcription for your organization</span></span>

<span data-ttu-id="e7174-146">조직에 대 한 기본 기록 설정이 설정 되어 있으므로, [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx)를 사용 하 여 기록을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-146">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="e7174-147">이 작업을 수행 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-147">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="e7174-148">조직의 기록 불경 마스크 설정</span><span class="sxs-lookup"><span data-stu-id="e7174-148">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="e7174-149">조직에서는 기본적으로 기록 불경 마스크를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-149">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="e7174-150">기능을 사용 하도록 설정 해야 하는 경우 [CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx)를 사용 하 여 기록 비속어 마스킹을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-150">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="e7174-151">이 작업을 수행 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-151">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="e7174-152">사용자에 대 한 기록을 끄는 중</span><span class="sxs-lookup"><span data-stu-id="e7174-152">Turning off transcription for a user</span></span>

<span data-ttu-id="e7174-153">사용자 정책은 조직 기본 설정 전에 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-153">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="e7174-154">예를 들어 모든 사용자에 대해 음성 메일을 사용할 수 있는 경우 [CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet을 사용 하 여 특정 사용자에 대 한 기록을 사용 하지 않도록 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-154">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="e7174-155">단일 사용자에 대 한 기록을 사용 하지 않도록 설정 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-155">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="e7174-156">사용자에 대 한 기록 사용 금지 마스크 설정</span><span class="sxs-lookup"><span data-stu-id="e7174-156">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="e7174-157">특정 사용자에 대해 기록 불경 마스크를 사용 하도록 설정 하려면 [CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet을 사용 하 여 특정 사용자에 대 한 기록 불경 마스크를 사용 하도록 설정 하는 정책을 할당 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-157">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="e7174-158">단일 사용자에 대해 기록 불경 마스크를 사용 하도록 설정 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-158">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="e7174-159">Office 365의 보이스 메일 서비스는 음성 메일 정책을 캐시 하 고 4 시간 마다 캐시를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-159">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours.</span></span> <span data-ttu-id="e7174-160">따라서 정책 변경은 적용 하는 데 최대 4 시간까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-160">So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-teams-voicemail-features"></a><span data-ttu-id="e7174-161">사용자가 팀의 보이스 메일 기능을 배우는 데 유용한 정보</span><span class="sxs-lookup"><span data-stu-id="e7174-161">Help your users learn Teams voicemail features</span></span>

<span data-ttu-id="e7174-162">팀의 다른 통화 기능 뿐만 아니라 보이스 메일 설정을 관리 하는 사용자에 게 다음과 같은 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-162">We have the following information for your users on managing their voicemail settings as well as other calling features in Teams:</span></span>

- <span data-ttu-id="e7174-163">[팀에서 통화 설정을 관리](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)합니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-163">[Manage your call settings in Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span> <span data-ttu-id="e7174-164">이 문서에서는 최종 사용자 팀의 모든 통화 기능을 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-164">This article explains how to manage all end-user Teams calling features.</span></span> 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="e7174-165">사용자가 비즈니스용 Skype 보이스 메일 기능 배우기</span><span class="sxs-lookup"><span data-stu-id="e7174-165">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="e7174-166">사용자에 게 비즈니스용 Skype 보이스 메일을 성공적으로 사용 하는 데 도움이 되는 교육 정보와 기사가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-166">We have training information and articles to help your users be successful with Skype for Business voicemail.</span></span> <span data-ttu-id="e7174-167">다음 문서를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-167">Point them to the following articles:</span></span>

- <span data-ttu-id="e7174-168">[비즈니스용 skype 음성 메일 및 옵션 확인](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8):이 문서에서는 비즈니스용 skype에서 음성 메일을 청취 하 고, 음성 사서함을 변경 하 고, 음성 사서함 설정을 변경 하 고, 보이스 메일을 다른 속도로 청취 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7174-168">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="e7174-169">비즈니스용 Skype 2016 교육</span><span class="sxs-lookup"><span data-stu-id="e7174-169">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="e7174-170">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e7174-170">Related topics</span></span>
[<span data-ttu-id="e7174-171">비즈니스용 Skype 온라인 설정</span><span class="sxs-lookup"><span data-stu-id="e7174-171">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="e7174-172">Office 365에서 전화 시스템을 사용 하 여 얻을 수 있는 기능</span><span class="sxs-lookup"><span data-stu-id="e7174-172">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="e7174-173">비즈니스용 Skype Server 및 Exchange Server의 마이그레이션 계획</span><span class="sxs-lookup"><span data-stu-id="e7174-173">Plan for Skype for Business Server and Exchange Server migration</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)

