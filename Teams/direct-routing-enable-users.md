---
title: 직접 라우팅에 대한 사용자 사용
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
description: 시스템 직접 라우팅을 사용하여 Microsoft 전화 방법을 알아보습니다.
ms.openlocfilehash: 7d2b7c4b5d6268d1498a47537e0edbbf892198aa
ms.sourcegitcommit: cae94cd5761baafde51aea1137e6d164722eead9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2021
ms.locfileid: "53075371"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a><span data-ttu-id="7d406-103">직접 라우팅, 음성 및 음성메일에 사용자를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="7d406-103">Enable users for Direct Routing, voice, and voicemail</span></span>

<span data-ttu-id="7d406-104">이 문서에서는 직접 라우팅에 대해 전화 시스템 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7d406-104">This article describes how to enable users for Phone System Direct Routing.</span></span>  <span data-ttu-id="7d406-105">직접 라우팅을 구성하기 위한 다음 단계의 2단계입니다.</span><span class="sxs-lookup"><span data-stu-id="7d406-105">This is step 2 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="7d406-106">1단계.</span><span class="sxs-lookup"><span data-stu-id="7d406-106">Step 1.</span></span> [<span data-ttu-id="7d406-107">커넥트 시스템으로 SBC를 Microsoft 전화 연결의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="7d406-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="7d406-108">**2단계. 직접 라우팅,**   음성 및 음성 문서에 사용자를 사용하도록 설정(이 문서)</span><span class="sxs-lookup"><span data-stu-id="7d406-108">**Step 2. Enable users for Direct Routing, voice, and voicemail**   (this article)</span></span>
- <span data-ttu-id="7d406-109">3단계.</span><span class="sxs-lookup"><span data-stu-id="7d406-109">Step 3.</span></span> [<span data-ttu-id="7d406-110">음성 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="7d406-110">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="7d406-111">4단계.</span><span class="sxs-lookup"><span data-stu-id="7d406-111">Step 4.</span></span> [<span data-ttu-id="7d406-112">숫자를 대체 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="7d406-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 


<span data-ttu-id="7d406-113">직접 라우팅을 설정하는 데 필요한 모든 단계에 대한 자세한 내용은 직접 라우팅 [구성 을 참조하세요.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="7d406-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

<span data-ttu-id="7d406-114">직접 라우팅에 사용자를 사용하도록 설정할 준비가 된 경우 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="7d406-114">When you are ready to enable users for Direct Routing, follow these steps:</span></span> 

1. <span data-ttu-id="7d406-115">사용자 또는 사용자 Microsoft 365 Office 365 라이선스를 전화 시스템 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="7d406-115">Create a user in Microsoft 365 or Office 365 and assign a Phone System license.</span></span> 
2. <span data-ttu-id="7d406-116">사용자가 온라인에 비즈니스용 Skype 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d406-116">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="7d406-117">전화 번호를 구성하고 엔터프라이즈 음성 및 음성을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7d406-117">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="7d406-118">사용자에게 Teams 전용 모드를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="7d406-118">Assign Teams Only mode to users.</span></span>

## <a name="create-a-user-and-assign-the-license"></a><span data-ttu-id="7d406-119">사용자 만들기 및 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="7d406-119">Create a user and assign the license</span></span> 

<span data-ttu-id="7d406-120">새 사용자를 만들기 위한 두 가지 옵션이 Microsoft 365 또는 Office 365.</span><span class="sxs-lookup"><span data-stu-id="7d406-120">There are two options for creating a new user in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="7d406-121">그러나 조직에서 라우팅 문제를 방지하기 위해 한 가지 옵션을 선택하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7d406-121">However, Microsoft recommends that your organization choose one option to avoid routing issues:</span></span> 

- <span data-ttu-id="7d406-122">프레미스 Active Directory에서 사용자를 만들고 사용자를 클라우드에 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="7d406-122">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="7d406-123">를 통해 [프레미스](/azure/active-directory/connect/active-directory-aadconnect)Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7d406-123">See [Integrate your on-premises directories with Azure Active Directory](/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="7d406-124">사용자 직접 Microsoft 365 관리 센터.</span><span class="sxs-lookup"><span data-stu-id="7d406-124">Create the user directly in the Microsoft 365 admin center.</span></span> <span data-ttu-id="7d406-125">사용자 추가를 개별적으로 또는 일괄적으로 Microsoft 365 또는 Office 365 [관리자 도움말을 참조하세요.](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</span><span class="sxs-lookup"><span data-stu-id="7d406-125">See [Add users individually or in bulk to Microsoft 365 or Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="7d406-126">온라인 비즈니스용 Skype 비즈니스용 Skype 2015 또는 Lync 2010 또는 2013 온-프레미스와 온라인 배포가 공존하는 경우 온-프레미스 Active Directory에서 사용자를 만들고 사용자를 클라우드에 동기화하는 유일한 옵션입니다(옵션 1).</span><span class="sxs-lookup"><span data-stu-id="7d406-126">If your Skype for Business Online deployment coexists with Skype for Business 2015 or Lync 2010 or 2013 on-premises, the only supported option is to create the user in the on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="7d406-127">라이선스 요구 사항에 대한 [](direct-routing-plan.md#licensing-and-other-requirements) 자세한 내용은 계획 직접 라우팅 의 라이선스 및 기타 [요구 사항을 참조하세요.](direct-routing-plan.md)</span><span class="sxs-lookup"><span data-stu-id="7d406-127">For information about license requirements, see [licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).</span></span>

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a><span data-ttu-id="7d406-128">사용자가 온라인에 홈되고 전화 번호가온-프레미스에서 동기화되지 않는지 확인합니다(비즈니스용 Skype 서버 Enterprise Voice 직접 라우팅으로 마이그레이션할 Teams 적용)</span><span class="sxs-lookup"><span data-stu-id="7d406-128">Ensure that the user is homed online and phone number is not being synced from on-premises (applicable for Skype for Business Server Enterprise Voice enabled users being migrated to Teams Direct Routing)</span></span>

<span data-ttu-id="7d406-129">직접 라우팅을 사용하려면 사용자가 온라인으로 홈으로 돌아와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d406-129">Direct Routing requires the user to be homed online.</span></span> <span data-ttu-id="7d406-130">도메인에 값이 필요한 RegistrarPool 매개 변수를 확인하여 확인할 infra.lync.com 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d406-130">You can check by looking at the RegistrarPool parameter, which needs to have a value in the infra.lync.com domain.</span></span> <span data-ttu-id="7d406-131">OnPremLineUriManuallySet 매개 변수도 True로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d406-131">OnPremLineUriManuallySet parameter should also to be set to True.</span></span> <span data-ttu-id="7d406-132">전화 번호를 구성하고 온라인 PowerShell을 사용하여 엔터프라이즈 음성 및 음성 비즈니스용 Skype 달성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d406-132">This is achieved by configuring the phone number and enable enterprise voice and voicemail using Skype for Business Online PowerShell.</span></span>

1. <span data-ttu-id="7d406-133">커넥트 PowerShell 비즈니스용 Skype 세션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7d406-133">Connect a Skype for Business Online PowerShell session.</span></span>

2. <span data-ttu-id="7d406-134">명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7d406-134">Issue the command:</span></span> 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    <span data-ttu-id="7d406-135">OnPremLineUriManuallySet이 False로 설정되고 LineUri에 전자 메일 번호가 <E.164 전화 번호가> 경우 온라인 PowerShell을 사용하여 전화 번호를 구성하기 전에 비즈니스용 Skype 비즈니스용 Skype 관리 셸을 사용하여 매개 변수를 정리하세요.</span><span class="sxs-lookup"><span data-stu-id="7d406-135">In case OnPremLineUriManuallySet is set to False and LineUri is populated with a <E.164 phone number>, please clean the parameters using on-premises Skype for Business Management Shell, before configuring the phone number using Skype for Business Online PowerShell.</span></span> 

1. <span data-ttu-id="7d406-136">관리 비즈니스용 Skype 셸에서 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7d406-136">From Skype for Business Management Shell issue the command:</span></span> 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   <span data-ttu-id="7d406-137">변경 내용이 동기화된 Office 365 출력은 `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="7d406-137">After the changes have synced to Office 365 the expected output of `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` would be:</span></span>

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="7d406-138">전화 번호 구성 및 엔터프라이즈 음성 및 음성메일 사용</span><span class="sxs-lookup"><span data-stu-id="7d406-138">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="7d406-139">사용자를 만들어 라이선스를 할당한 후 다음 단계는 사용자의 전화 번호 및 음성 번호를 구성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7d406-139">After you have created the user and assigned a license, the next step is to configure the user's phone number and voicemail.</span></span> 

<span data-ttu-id="7d406-140">전화 번호를 추가하고 음성메일을 사용하도록 설정하려면:</span><span class="sxs-lookup"><span data-stu-id="7d406-140">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="7d406-141">커넥트 PowerShell 비즈니스용 Skype 세션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7d406-141">Connect a Skype for Business Online PowerShell session.</span></span> 

2. <span data-ttu-id="7d406-142">명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7d406-142">Issue the command:</span></span> 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    <span data-ttu-id="7d406-143">예를 들어 "Spencer Low"에 대한 전화 번호를 추가하면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7d406-143">For example, to add a phone number for user "Spencer Low," enter the following:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    <span data-ttu-id="7d406-144">사용자가 "Spencer Low" 및 "Stacy Quinn"이 고유 확장과 동일한 기본 번호를 공유하는 경우 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7d406-144">If the users "Spencer Low" and "Stacy Quinn" share the same base number with unique extensions, enter the following</span></span>
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI "tel:+14255388701;ext=1001" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI "tel:+14255388701;ext=1002" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    <span data-ttu-id="7d406-145">사용된 전화 번호는 국가 코드가 있는 전체 E.164 전화 번호로 구성되는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7d406-145">It's recommended, but not required, that the phone number used is configured as a full E.164 phone number with country code.</span></span> <span data-ttu-id="7d406-146">기본 번호에 대한 보기가 두 개 이상의 결과를 반환할 때 사용자를 찾아보는 데 사용할 확장을 사용하여 전화 번호를 구성하는 것이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d406-146">It is supported to configure phone numbers with extensions which will be used to lookup users when the lookup against the base number returns more than one result.</span></span> <span data-ttu-id="7d406-147">이렇게 하면 회사에서 동일한 기본 번호 및 고유 확장으로 전화 번호를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d406-147">This allows companies to configure phone numbers with the same base number and unique extensions.</span></span> <span data-ttu-id="7d406-148">보기가 성공하려면 다음과 같이 확장이 포함된 전체 번호를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d406-148">For lookup to be successful, the invite must include the full number with extension as follows:</span></span>
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > <span data-ttu-id="7d406-149">사용자의 전화 번호가 프레미스에서 관리되는 경우 관리 비즈니스용 Skype 제어판을 사용하여 사용자의 전화 번호를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7d406-149">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 


## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="7d406-150">음성 메일에 직접 통화 보내기 구성</span><span class="sxs-lookup"><span data-stu-id="7d406-150">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="7d406-151">직접 라우팅을 사용하면 사용자에 대한 통화를 종료하고 사용자의 음성 메일로 직접 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d406-151">Direct Routing allows you to end the call to a user and send it directly to the user's voicemail.</span></span> <span data-ttu-id="7d406-152">음성 메일에 직접 전화를 보내고 싶은 경우 요청 URI 헤더에 opaque=app:voicemail을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="7d406-152">If you want to send the call directly to voicemail, attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="7d406-153">예를 들어 "sip:user@yourdomain.com;opaque=app:voicemail"을 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d406-153">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span> <span data-ttu-id="7d406-154">이 경우 Teams 사용자가 호출 알림을 받지 못하고 통화가 사용자의 음성 메일에 직접 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d406-154">In this case, the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="7d406-155">사용자에게 Teams 전용 모드를 할당하여 호출이 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7d406-155">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="7d406-156">직접 라우팅을 사용하려면 사용자가 Teams 클라이언트에서 들어오는 호출이 Teams 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d406-156">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="7d406-157">사용자를 Teams 전용 모드로 전환하려면 TeamsUpgradePolicy의 "UpgradeToTeams" 인스턴스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="7d406-157">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="7d406-158">자세한 내용은 IT 관리자에 대한 업그레이드 [전략을 참조하세요.](upgrade-to-teams-on-prem-implement.md)</span><span class="sxs-lookup"><span data-stu-id="7d406-158">For more information, see [Upgrade strategies for IT administrators](upgrade-to-teams-on-prem-implement.md).</span></span> <span data-ttu-id="7d406-159">조직에서 비즈니스용 Skype 서버 또는 비즈니스용 Skype 사용하는 경우 Skype 및 Teams 간의 상호운용성에 대한 자세한 내용은 다음 문서를 [비즈니스용 Skype.](migration-interop-guidance-for-teams-with-skype.md)</span><span class="sxs-lookup"><span data-stu-id="7d406-159">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information about interoperability between Skype and Teams: [Migration and interoperability with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7d406-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7d406-160">See also</span></span>

[<span data-ttu-id="7d406-161">직접 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="7d406-161">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="7d406-162">직접 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="7d406-162">Configure Direct Routing</span></span>](direct-routing-configure.md)
