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
ms.openlocfilehash: 5739797649c639e3259c6972da665ae0ced4b4bf
ms.sourcegitcommit: 0a9c5c01b37a93eecc369ca0ed49ae18f6a5065b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655485"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a><span data-ttu-id="b51e4-103">사용자가 직접 라우팅, 음성, 보이스 메일을 사용할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="b51e4-103">Enable users for Direct Routing, voice, and voicemail</span></span>

<span data-ttu-id="b51e4-104">이 문서에서는 전화 시스템 다이렉트 라우팅에 대 한 사용자를 설정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-104">This article describes how to enable users for Phone System Direct Routing.</span></span>  <span data-ttu-id="b51e4-105">직접 라우팅 구성에 대 한 다음 단계 중 2 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-105">This is step 2 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="b51e4-106">1 단계.</span><span class="sxs-lookup"><span data-stu-id="b51e4-106">Step 1.</span></span> [<span data-ttu-id="b51e4-107">Microsoft 전화 시스템을 사용 하 여 SBC 연결 및 연결 확인</span><span class="sxs-lookup"><span data-stu-id="b51e4-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="b51e4-108">**2 단계. 사용자가 직접 라우팅, 음성 및 보이스 메일을 사용할 수 있도록 설정**   (이 문서)</span><span class="sxs-lookup"><span data-stu-id="b51e4-108">**Step 2. Enable users for Direct Routing, voice, and voicemail**   (this article)</span></span>
- <span data-ttu-id="b51e4-109">3 단계.</span><span class="sxs-lookup"><span data-stu-id="b51e4-109">Step 3.</span></span> [<span data-ttu-id="b51e4-110">음성 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="b51e4-110">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="b51e4-111">4 단계.</span><span class="sxs-lookup"><span data-stu-id="b51e4-111">Step 4.</span></span> [<span data-ttu-id="b51e4-112">숫자를 대체 형식으로 번역</span><span class="sxs-lookup"><span data-stu-id="b51e4-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 


<span data-ttu-id="b51e4-113">직접 라우팅을 설정 하는 데 필요한 모든 단계에 대 한 자세한 내용은 [직접 라우팅 구성을](direct-routing-configure.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b51e4-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

<span data-ttu-id="b51e4-114">사용자가 직접 라우팅을 사용할 준비가 되 면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-114">When you are ready to enable users for Direct Routing, follow these steps:</span></span> 

1. <span data-ttu-id="b51e4-115">Microsoft 365 또는 Office 365에서 사용자를 만들고 전화 시스템 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-115">Create a user in Microsoft 365 or Office 365 and assign a Phone System license.</span></span> 
2. <span data-ttu-id="b51e4-116">사용자가 비즈니스용 Skype Online에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-116">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="b51e4-117">전화 번호를 구성 하 고 엔터프라이즈 음성 및 보이스 메일을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-117">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="b51e4-118">사용자에 게 팀 전용 모드를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-118">Assign Teams Only mode to users.</span></span>

## <a name="create-a-user-and-assign-the-license"></a><span data-ttu-id="b51e4-119">사용자 만들기 및 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="b51e4-119">Create a user and assign the license</span></span> 

<span data-ttu-id="b51e4-120">Microsoft 365 또는 Office 365에서 새 사용자를 만드는 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-120">There are two options for creating a new user in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="b51e4-121">그러나 조직에서 라우팅 문제를 방지 하기 위한 옵션 하나를 선택 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-121">However, Microsoft recommends that your organization choose one option to avoid routing issues:</span></span> 

- <span data-ttu-id="b51e4-122">온-프레미스 Active Directory에서 사용자를 만들고 사용자를 클라우드와 동기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-122">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="b51e4-123">[Azure Active Directory와 온-프레미스 디렉터리 통합](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b51e4-123">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="b51e4-124">Microsoft 365 관리 센터에서 직접 사용자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-124">Create the user directly in the Microsoft 365 admin center.</span></span> <span data-ttu-id="b51e4-125">[Microsoft 365 또는 Office 365-관리자 도움말에서 사용자를 개별적으로 또는 대량으로 추가를](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b51e4-125">See [Add users individually or in bulk to Microsoft 365 or Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="b51e4-126">비즈니스용 Skype Online 배포가 비즈니스용 Skype 2015 또는 Lync 2010 또는 2013 온-프레미스와 함께 존재 하는 경우 유일 하 게 지원 되는 옵션은 온-프레미스 Active Directory에서 사용자를 만들고 사용자를 클라우드와 동기화 (옵션 1) 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-126">If your Skype for Business Online deployment coexists with Skype for Business 2015 or Lync 2010 or 2013 on-premises, the only supported option is to create the user in the on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="b51e4-127">라이선스 요구 사항에 대 한 자세한 내용은 [직접 라우팅 계획](direct-routing-plan.md)의 [라이선스 및 기타 요구 사항을](direct-routing-plan.md#licensing-and-other-requirements) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b51e4-127">For information about license requirements, see [licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).</span></span>

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a><span data-ttu-id="b51e4-128">사용자가 온라인 상태이 고 전화 번호가 온-프레미스에서 동기화 되지 않았는지 확인 (비즈니스용 Skype Server Enterprise Voice 사용 사용자가 팀에 직접 라우팅 하도록 설정 된 경우 해당)</span><span class="sxs-lookup"><span data-stu-id="b51e4-128">Ensure that the user is homed online and phone number is not being synced from on-premises (applicable for Skype for Business Server Enterprise Voice enabled users being migrated to Teams Direct Routing)</span></span>

<span data-ttu-id="b51e4-129">직접 라우팅에는 사용자가 온라인으로 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-129">Direct Routing requires the user to be homed online.</span></span> <span data-ttu-id="b51e4-130">Infra.lync.com 도메인에 값이 있어야 하는 RegistrarPool 매개 변수를 확인 하 여 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-130">You can check by looking at the RegistrarPool parameter, which needs to have a value in the infra.lync.com domain.</span></span> <span data-ttu-id="b51e4-131">OnPremLineUriManuallySet 매개 변수도 True로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-131">OnPremLineUriManuallySet parameter should also to be set to True.</span></span> <span data-ttu-id="b51e4-132">이는 전화 번호를 구성 하 고 비즈니스용 Skype Online PowerShell을 사용 하 여 엔터프라이즈 음성 및 보이스 메일을 사용 하도록 설정 함으로써 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-132">This is achieved by configuring the phone number and enable enterprise voice and voicemail using Skype for Business Online PowerShell.</span></span>

1. <span data-ttu-id="b51e4-133">비즈니스용 Skype Online PowerShell 세션을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-133">Connect a Skype for Business Online PowerShell session.</span></span>

2. <span data-ttu-id="b51e4-134">다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-134">Issue the command:</span></span> 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    <span data-ttu-id="b51e4-135">OnPremLineUriManuallySet가 False로 설정 되 고 LineUri가 <E> 전화 번호를 사용 하 여 채워지면, 비즈니스용 skype Online PowerShell을 사용 하 여 전화 번호를 구성 하기 전에 온-프레미스 비즈니스용 Skype 관리 셸을 사용해 매개 변수를 정리 하세요.</span><span class="sxs-lookup"><span data-stu-id="b51e4-135">In case OnPremLineUriManuallySet is set to False and LineUri is populated with a <E.164 phone number>, please clean the parameters using on-premises Skype for Business Management Shell, before configuring the phone number using Skype for Business Online PowerShell.</span></span> 

1. <span data-ttu-id="b51e4-136">비즈니스용 Skype 관리 셸에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-136">From Skype for Business Management Shell issue the command:</span></span> 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   <span data-ttu-id="b51e4-137">변경 내용이 Office 365와 동기화 된 후의 예상 출력은 `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-137">After the changes have synced to Office 365 the expected output of `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` would be:</span></span>

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="b51e4-138">전화 번호를 구성 하 고 엔터프라이즈 음성 및 보이스 메일 사용</span><span class="sxs-lookup"><span data-stu-id="b51e4-138">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="b51e4-139">사용자를 만들고 라이선스를 할당 한 후 다음 단계는 사용자의 전화 번호와 보이스 메일을 구성 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-139">After you have created the user and assigned a license, the next step is to configure the user's phone number and voicemail.</span></span> 

<span data-ttu-id="b51e4-140">전화 번호를 추가 하 고 보이스 메일을 사용 하도록 설정 하려면:</span><span class="sxs-lookup"><span data-stu-id="b51e4-140">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="b51e4-141">비즈니스용 Skype Online PowerShell 세션을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-141">Connect a Skype for Business Online PowerShell session.</span></span> 

2. <span data-ttu-id="b51e4-142">다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-142">Issue the command:</span></span> 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    <span data-ttu-id="b51e4-143">예를 들어 사용자 "Spencer Low"에 대 한 전화 번호를 추가 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-143">For example, to add a phone number for user "Spencer Low," enter the following:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    <span data-ttu-id="b51e4-144">"Spencer Low" 및 "Stacy Quinn" 사용자가 고유한 확장명을 가진 동일한 기준 번호를 공유 하는 경우 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-144">If the users "Spencer Low" and "Stacy Quinn" share the same base number with unique extensions, enter the following</span></span>
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388701;ext=1001 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI tel:+14255388701;ext=1002 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    <span data-ttu-id="b51e4-145">필요한 것은 아니지만, 사용 하는 전화 번호가 국가 코드와 함께 전체 E의 164 자로 구성 되어 있는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-145">It's recommended, but not required, that the phone number used is configured as a full E.164 phone number with country code.</span></span> <span data-ttu-id="b51e4-146">기준 번호를 조회할 때 두 개 이상의 결과를 반환 하는 경우 사용자를 조회 하는 데 사용 되는 확장명을 사용 하 여 전화 번호를 구성 하는 것이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-146">It is supported to configure phone numbers with extensions which will be used to lookup users when the lookup against the base number returns more than one result.</span></span> <span data-ttu-id="b51e4-147">이를 통해 회사는 기본 번호와 고유 확장명을 사용 하 여 전화 번호를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-147">This allows companies to configure phone numbers with the same base number and unique extensions.</span></span> <span data-ttu-id="b51e4-148">조회에 성공 하려면 다음과 같이 초대에 확장명이 있는 전체 번호를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-148">For lookup to be successful, the invite must include the full number with extension as follows:</span></span>
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > <span data-ttu-id="b51e4-149">사용자의 전화 번호가 온-프레미스에서 관리 되는 경우 온-프레미스 Skype for Business 관리 셸 또는 제어판을 사용 하 여 사용자의 전화 번호를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-149">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 


## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="b51e4-150">전화를 음성 메일로 바로 보내는 방법 구성</span><span class="sxs-lookup"><span data-stu-id="b51e4-150">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="b51e4-151">직접 라우팅이 사용자에 대 한 통화를 종료 하 고 사용자의 음성 메일로 직접 보낼 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-151">Direct Routing allows you to end the call to a user and send it directly to the user's voicemail.</span></span> <span data-ttu-id="b51e4-152">전화를 음성 메일로 바로 보내려면 불투명 = 앱: 보이스 메일을 요청 URI 헤더에 첨부 합니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-152">If you want to send the call directly to voicemail, attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="b51e4-153">예를 들어 "sip: user@yourdomain .com, 불투명 = 앱: 보이스".</span><span class="sxs-lookup"><span data-stu-id="b51e4-153">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span> <span data-ttu-id="b51e4-154">이 경우에는 팀 사용자가 통화 알림을 받지 못할 수 있으며 통화는 사용자의 보이스 메일에 직접 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-154">In this case, the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="b51e4-155">Microsoft 팀에서 전화를 걸 수 있도록 사용자에 게 팀 전용 모드 할당</span><span class="sxs-lookup"><span data-stu-id="b51e4-155">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="b51e4-156">다이렉트 라우팅은 팀 클라이언트에서 수신 전화를 받을 수 있도록 사용자가 팀 전용 모드에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-156">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="b51e4-157">사용자를 팀 전용 모드로 전환 하려면 TeamsUpgradePolicy의 "UpgradeToTeams" 인스턴스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b51e4-157">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="b51e4-158">자세한 내용은 [IT 관리자를 위한 업그레이드 지침](upgrade-to-teams-on-prem-overview.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b51e4-158">For more information, see [Upgrade guidance for IT administrators](upgrade-to-teams-on-prem-overview.md).</span></span> <span data-ttu-id="b51e4-159">조직에서 비즈니스용 skype Server 또는 비즈니스용 Skype Online을 사용 하는 경우 Skype와 팀 간의 상호 운용성에 대 한 자세한 내용은 다음 문서를 참조 하세요. 비즈니스용 [skype를 통한 마이그레이션 및 상호 운용성](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="b51e4-159">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information about interoperability between Skype and Teams: [Migration and interoperability with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b51e4-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b51e4-160">See also</span></span>

[<span data-ttu-id="b51e4-161">직접 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="b51e4-161">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="b51e4-162">직접 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="b51e4-162">Configure Direct Routing</span></span>](direct-routing-configure.md)
