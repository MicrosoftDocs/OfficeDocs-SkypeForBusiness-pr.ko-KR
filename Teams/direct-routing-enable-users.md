---
title: 사용자가 직접 라우팅 하도록 설정
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 사용자의 Microsoft 전화 시스템 다이렉트 라우팅을 사용 하도록 설정 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: f89133b5205dc77f8045c484b97d3049773c28e2
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814547"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a><span data-ttu-id="1add5-103">사용자가 직접 라우팅, 음성, 보이스 메일을 사용할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="1add5-103">Enable users for Direct Routing, voice, and voicemail</span></span>

<span data-ttu-id="1add5-104">이 문서에서는 전화 시스템 다이렉트 라우팅에 대 한 사용자를 설정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1add5-104">This article describes how to enable users for Phone System Direct Routing.</span></span>  <span data-ttu-id="1add5-105">직접 라우팅 구성에 대 한 다음 단계 중 2 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="1add5-105">This is step 2 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="1add5-106">1 단계.</span><span class="sxs-lookup"><span data-stu-id="1add5-106">Step 1.</span></span> [<span data-ttu-id="1add5-107">Microsoft 전화 시스템을 사용 하 여 SBC 연결 및 연결 확인</span><span class="sxs-lookup"><span data-stu-id="1add5-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="1add5-108">**2 단계. 사용자가 직접 라우팅, 음성 및 보이스 메일을 사용할 수 있도록 설정**   (이 문서)</span><span class="sxs-lookup"><span data-stu-id="1add5-108">**Step 2. Enable users for Direct Routing, voice, and voicemail**   (this article)</span></span>
- <span data-ttu-id="1add5-109">3 단계.</span><span class="sxs-lookup"><span data-stu-id="1add5-109">Step 3.</span></span> [<span data-ttu-id="1add5-110">음성 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="1add5-110">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="1add5-111">4 단계.</span><span class="sxs-lookup"><span data-stu-id="1add5-111">Step 4.</span></span> [<span data-ttu-id="1add5-112">숫자를 대체 형식으로 번역</span><span class="sxs-lookup"><span data-stu-id="1add5-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 


<span data-ttu-id="1add5-113">직접 라우팅을 설정 하는 데 필요한 모든 단계에 대 한 자세한 내용은 [직접 라우팅 구성을](direct-routing-configure.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1add5-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

<span data-ttu-id="1add5-114">사용자가 직접 라우팅을 사용할 준비가 되 면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="1add5-114">When you are ready to enable users for Direct Routing, follow these steps:</span></span> 

1. <span data-ttu-id="1add5-115">Microsoft 365 또는 Office 365에서 사용자를 만들고 전화 시스템 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="1add5-115">Create a user in Microsoft 365 or Office 365 and assign a Phone System license.</span></span> 
2. <span data-ttu-id="1add5-116">사용자가 비즈니스용 Skype Online에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1add5-116">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="1add5-117">전화 번호를 구성 하 고 엔터프라이즈 음성 및 보이스 메일을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1add5-117">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="1add5-118">사용자에 게 팀 전용 모드를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="1add5-118">Assign Teams Only mode to users.</span></span>

## <a name="create-a-user-and-assign-the-license"></a><span data-ttu-id="1add5-119">사용자 만들기 및 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="1add5-119">Create a user and assign the license</span></span> 

<span data-ttu-id="1add5-120">Microsoft 365 또는 Office 365에서 새 사용자를 만드는 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1add5-120">There are two options for creating a new user in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="1add5-121">그러나 조직에서 라우팅 문제를 방지 하기 위한 옵션 하나를 선택 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1add5-121">However, Microsoft recommends that your organization choose one option to avoid routing issues:</span></span> 

- <span data-ttu-id="1add5-122">온-프레미스 Active Directory에서 사용자를 만들고 사용자를 클라우드와 동기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="1add5-122">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="1add5-123">[Azure Active Directory와 온-프레미스 디렉터리 통합](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1add5-123">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="1add5-124">Microsoft 365 관리 센터에서 직접 사용자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1add5-124">Create the user directly in the Microsoft 365 admin center.</span></span> <span data-ttu-id="1add5-125">[Microsoft 365 또는 Office 365-관리자 도움말에서 사용자를 개별적으로 또는 대량으로 추가를](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1add5-125">See [Add users individually or in bulk to Microsoft 365 or Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="1add5-126">비즈니스용 Skype Online 배포가 비즈니스용 Skype 2015 또는 Lync 2010 또는 2013 온-프레미스와 함께 존재 하는 경우 유일 하 게 지원 되는 옵션은 온-프레미스 Active Directory에서 사용자를 만들고 사용자를 클라우드와 동기화 (옵션 1) 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1add5-126">If your Skype for Business Online deployment coexists with Skype for Business 2015 or Lync 2010 or 2013 on-premises, the only supported option is to create the user in the on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="1add5-127">라이선스 요구 사항에 대 한 자세한 내용은 [직접 라우팅 계획](direct-routing-plan.md)의 [라이선스 및 기타 요구 사항을](direct-routing-plan.md#licensing-and-other-requirements) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1add5-127">For information about license requirements, see [licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).</span></span>

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a><span data-ttu-id="1add5-128">사용자가 온라인 상태이 고 전화 번호가 온-프레미스에서 동기화 되지 않았는지 확인 (비즈니스용 Skype Server Enterprise Voice 사용 사용자가 팀에 직접 라우팅 하도록 설정 된 경우 해당)</span><span class="sxs-lookup"><span data-stu-id="1add5-128">Ensure that the user is homed online and phone number is not being synced from on-premises (applicable for Skype for Business Server Enterprise Voice enabled users being migrated to Teams Direct Routing)</span></span>

<span data-ttu-id="1add5-129">직접 라우팅에는 사용자가 온라인으로 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1add5-129">Direct Routing requires the user to be homed online.</span></span> <span data-ttu-id="1add5-130">Infra.lync.com 도메인에 값이 있어야 하는 RegistrarPool 매개 변수를 확인 하 여 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1add5-130">You can check by looking at the RegistrarPool parameter, which needs to have a value in the infra.lync.com domain.</span></span> <span data-ttu-id="1add5-131">OnPremLineUriManuallySet 매개 변수도 True로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1add5-131">OnPremLineUriManuallySet parameter should also to be set to True.</span></span> <span data-ttu-id="1add5-132">이는 전화 번호를 구성 하 고 비즈니스용 Skype Online PowerShell을 사용 하 여 엔터프라이즈 음성 및 보이스 메일을 사용 하도록 설정 함으로써 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="1add5-132">This is achieved by configuring the phone number and enable enterprise voice and voicemail using Skype for Business Online PowerShell.</span></span>

1. <span data-ttu-id="1add5-133">비즈니스용 Skype Online PowerShell 세션을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="1add5-133">Connect a Skype for Business Online PowerShell session.</span></span>

2. <span data-ttu-id="1add5-134">다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1add5-134">Issue the command:</span></span> 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    <span data-ttu-id="1add5-135">OnPremLineUriManuallySet가 False로 설정 되 고 LineUri가 <E> 전화 번호를 사용 하 여 채워지면, 비즈니스용 skype Online PowerShell을 사용 하 여 전화 번호를 구성 하기 전에 온-프레미스 비즈니스용 Skype 관리 셸을 사용해 매개 변수를 정리 하세요.</span><span class="sxs-lookup"><span data-stu-id="1add5-135">In case OnPremLineUriManuallySet is set to False and LineUri is populated with a <E.164 phone number>, please clean the parameters using on-premises Skype for Business Management Shell, before configuring the phone number using Skype for Business Online PowerShell.</span></span> 

1. <span data-ttu-id="1add5-136">비즈니스용 Skype 관리 셸에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1add5-136">From Skype for Business Management Shell issue the command:</span></span> 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   <span data-ttu-id="1add5-137">변경 내용이 Office 365와 동기화 된 후의 예상 출력은 `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1add5-137">After the changes have synced to Office 365 the expected output of `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` would be:</span></span>

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="1add5-138">전화 번호를 구성 하 고 엔터프라이즈 음성 및 보이스 메일 사용</span><span class="sxs-lookup"><span data-stu-id="1add5-138">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="1add5-139">사용자를 만들고 라이선스를 할당 한 후 다음 단계는 사용자의 전화 번호와 보이스 메일을 구성 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1add5-139">After you have created the user and assigned a license, the next step is to configure the user's phone number and voicemail.</span></span> 

<span data-ttu-id="1add5-140">전화 번호를 추가 하 고 보이스 메일을 사용 하도록 설정 하려면:</span><span class="sxs-lookup"><span data-stu-id="1add5-140">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="1add5-141">비즈니스용 Skype Online PowerShell 세션을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="1add5-141">Connect a Skype for Business Online PowerShell session.</span></span> 

2. <span data-ttu-id="1add5-142">다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1add5-142">Issue the command:</span></span> 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
    ```
    
    <span data-ttu-id="1add5-143">예를 들어 사용자 "Spencer Low"에 대 한 전화 번호를 추가 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1add5-143">For example, to add a phone number for user "Spencer Low," enter the following:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    <span data-ttu-id="1add5-144">사용 된 전화 번호는 국가 코드를 사용 하 여 전체 전자 164 자로 구성 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1add5-144">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="1add5-145">사용자의 전화 번호가 온-프레미스에서 관리 되는 경우 온-프레미스 Skype for Business 관리 셸 또는 제어판을 사용 하 여 사용자의 전화 번호를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1add5-145">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 


## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="1add5-146">전화를 음성 메일로 바로 보내는 방법 구성</span><span class="sxs-lookup"><span data-stu-id="1add5-146">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="1add5-147">직접 라우팅이 사용자에 대 한 통화를 종료 하 고 사용자의 음성 메일로 직접 보낼 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1add5-147">Direct Routing allows you to end the call to a user and send it directly to the user's voicemail.</span></span> <span data-ttu-id="1add5-148">전화를 음성 메일로 바로 보내려면 불투명 = 앱: 보이스 메일을 요청 URI 헤더에 첨부 합니다.</span><span class="sxs-lookup"><span data-stu-id="1add5-148">If you want to send the call directly to voicemail, attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="1add5-149">예를 들어 "sip: user@yourdomain .com, 불투명 = 앱: 보이스".</span><span class="sxs-lookup"><span data-stu-id="1add5-149">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span> <span data-ttu-id="1add5-150">이 경우에는 팀 사용자가 통화 알림을 받지 못할 수 있으며 통화는 사용자의 보이스 메일에 직접 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1add5-150">In this case, the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="1add5-151">Microsoft 팀에서 전화를 걸 수 있도록 사용자에 게 팀 전용 모드 할당</span><span class="sxs-lookup"><span data-stu-id="1add5-151">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="1add5-152">다이렉트 라우팅은 팀 클라이언트에서 수신 전화를 받을 수 있도록 사용자가 팀 전용 모드에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1add5-152">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="1add5-153">사용자를 팀 전용 모드로 전환 하려면 TeamsUpgradePolicy의 "UpgradeToTeams" 인스턴스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="1add5-153">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="1add5-154">자세한 내용은 [IT 관리자를 위한 업그레이드 지침](upgrade-to-teams-on-prem-overview.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1add5-154">For more information, see [Upgrade guidance for IT administrators](upgrade-to-teams-on-prem-overview.md).</span></span> <span data-ttu-id="1add5-155">조직에서 비즈니스용 skype Server 또는 비즈니스용 Skype Online을 사용 하는 경우 Skype와 팀 간의 상호 운용성에 대 한 자세한 내용은 다음 문서를 참조 하세요. 비즈니스용 [skype를 통한 마이그레이션 및 상호 운용성](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="1add5-155">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information about interoperability between Skype and Teams: [Migration and interoperability with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1add5-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1add5-156">See also</span></span>

[<span data-ttu-id="1add5-157">직접 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="1add5-157">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="1add5-158">직접 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="1add5-158">Configure Direct Routing</span></span>](direct-routing-configure.md)
