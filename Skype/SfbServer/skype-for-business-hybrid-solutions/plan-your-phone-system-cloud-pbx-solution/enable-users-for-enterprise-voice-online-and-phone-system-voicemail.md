---
title: 사용자가 전화 시스템 음성 사서함과 온라인으로 Enterprise Voice를 사용하도록 설정
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: 비즈니스용 Skype 사용자에 대해 전화 시스템 음성 서비스를 사용하도록 설정하는 방법을 배워야 합니다.
ms.openlocfilehash: f1c59505073a7113407f28b7ebbe3a323724782e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098574"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a><span data-ttu-id="92220-103">사용자가 전화 시스템 음성 사서함과 온라인으로 Enterprise Voice를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="92220-103">Enable users for Enterprise Voice online and Phone System Voicemail</span></span>
 
> [!Important]
> <span data-ttu-id="92220-104">비즈니스용 Skype Online은 2021년 7월 31에 서비스가 더 이상 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="92220-104">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="92220-105">또한 비즈니스용 Skype 서버 또는 클라우드 커넥터 버전과 비즈니스용 Skype Online을 통해 지원되지 않는 모든 사내 환경 간의 PSTN 연결도 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="92220-105">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="92220-106">직접 라우팅을 사용하여 프레미스 전화 통신 네트워크를 Teams에 연결하는 [방법을 학습합니다.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="92220-106">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="92220-107">비즈니스용 Skype 사용자에 대해 전화 시스템 음성 서비스를 사용하도록 설정하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92220-107">Learn how to enable Phone System voice services for your Skype for Business users.</span></span>
  
<span data-ttu-id="92220-108">전화 시스템을 배포하는 마지막 단계는 사용자가 전화 시스템 및 음성메일을 사용할 수 있도록 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="92220-108">The final step in deploying Phone System with on-premises PSTN connectivity is to enable your users for Phone System and voicemail.</span></span> <span data-ttu-id="92220-109">이러한 기능을 사용하려면 전역 관리자 역할이 있는 사용자로, 원격 PowerShell을 실행할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92220-109">To enable these capabilities, you must be a user with the Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="92220-110">비즈니스용 Skype Online에 대해 아직 사용하도록 설정되지 않은 모든 사용자 계정에 대해 이 Enterprise Voice 단계를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92220-110">You need to follow the steps in this topic for all user accounts that do not already have Enterprise Voice enabled for Skype for Business Online.</span></span>
  
## <a name="enable-phone-system-voice-services"></a><span data-ttu-id="92220-111">전화 시스템 음성 서비스 사용</span><span class="sxs-lookup"><span data-stu-id="92220-111">Enable Phone System voice services</span></span>

<span data-ttu-id="92220-112">사용자가 전화 시스템 음성 및 음성메일을 사용할 수 있도록 설정하려면 서버에 비즈니스용 Skype Online 커넥터가 배포되어 있으며 사용자가 호스팅된 음성메일을 사용할 수 있도록 설정하는 등 초기 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92220-112">To enable a user for Phone System Voice and voicemail, you'll need to perform some initial steps, like checking to see if the Skype for Business Online Connector is deployed on your servers and enable your users for hosted voicemail.</span></span>
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a><span data-ttu-id="92220-113">사용자가 전화 시스템 음성 및 음성메일을 사용할 수 있도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="92220-113">To enable your users for Phone System voice and voicemail</span></span>

> [!NOTE]
> <span data-ttu-id="92220-114">비즈니스용 Skype Online 커넥터는 현재 최신 Teams PowerShell 모듈의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="92220-114">Skype for Business Online Connector is currently part of latest Teams PowerShell Module.</span></span>
> <span data-ttu-id="92220-115">최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 릴리스를 사용하는 경우 비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="92220-115">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

1. <span data-ttu-id="92220-116">시작하기 전에 Teams PowerShell 모듈이 프런트 엔드 서버에 설치되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="92220-116">Before you begin, check that the Teams PowerShell module is installed on your Front End Servers.</span></span> <span data-ttu-id="92220-117">그렇지 않은 경우 Teams PowerShell 모듈 설치의 지침을 [사용하여 설치하세요.](/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="92220-117">If it's not, please  install using the instructions in [Teams PowerShell Module Installation](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="92220-118">관리자 Windows PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="92220-118">Start Windows PowerShell as an administrator.</span></span>
    
3. <span data-ttu-id="92220-119">다음을 입력하고 Enter를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="92220-119">Type the following and press Enter:</span></span>
    
 ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

  
4. <span data-ttu-id="92220-120">Set-CsUser cmdlet을 사용하여 $EnterpriseVoiceEnabled $HostedVoiceMail 속성을 사용자에게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92220-120">Use the Set-CsUser cmdlet to assign the $EnterpriseVoiceEnabled and $HostedVoiceMail properties to your user as follows:</span></span>
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    <span data-ttu-id="92220-121">예:</span><span class="sxs-lookup"><span data-stu-id="92220-121">For example:</span></span>
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > <span data-ttu-id="92220-122">또한 SIP 주소, UPN(사용자 계정 이름), 도메인 이름 및 사용자 이름(도메인\사용자 이름) 및 Active Directory의 표시 이름("Bob Kelly")으로 사용자를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92220-122">You can also specify a user by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a><span data-ttu-id="92220-123">전화 시스템에 대해 사용하도록 설정된 사용자의 줄 URI 및 다이얼 플랜 업데이트</span><span class="sxs-lookup"><span data-stu-id="92220-123">Update the Line URI and dial plan for users enabled for Phone System</span></span>

<span data-ttu-id="92220-124">이 섹션에서는 전화 시스템에 대해 사용하도록 설정된 사용자의 줄 URI 및 다이얼 플랜을 업데이트하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="92220-124">This section describes how to update the Line URI and dial plan for users enabled for Phone System.</span></span> 
  
### <a name="to-update-the-line-uri"></a><span data-ttu-id="92220-125">줄 URI를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="92220-125">To update the Line URI</span></span>

1. <span data-ttu-id="92220-126">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="92220-126">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="92220-127">시작 메뉴 또는 데스크톱 바로 가기를 사용하여 비즈니스용 Skype 서버 제어판을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92220-127">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="92220-128">브라우저 창을 열고 관리자 URL을 입력하여 비즈니스용 Skype 서버 제어판을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92220-128">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span> 
  
3. <span data-ttu-id="92220-129">왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="92220-129">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="92220-130">**사용자 검색** 상자에 사용하도록 설정할 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫부분을 입력하고 **찾기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="92220-130">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="92220-131">표에서 줄 URI를 변경할 비즈니스용 Skype 사용자 계정을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="92220-131">In the table, click the Skype for Business user account that you want to change line URI.</span></span>
    
6. <span data-ttu-id="92220-132">줄 **URI를 클릭하고** 고유한 정규화된 전화 번호(예: tel:+14255550200)를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="92220-132">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="92220-133">그런 다음 **커밋을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="92220-133">Then click **Commit**.</span></span>
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="92220-134">프레미스 cmdlet을 사용하여 다이얼 Windows PowerShell 업데이트</span><span class="sxs-lookup"><span data-stu-id="92220-134">Update the dial plan using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="92220-135">[Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet과 함께 사용자 Windows PowerShell 다이얼 플랜을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92220-135">You can assign per-user dial plans with Windows PowerShell and the [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="92220-136">이 cmdlet은 비즈니스용 Skype 서버 2015 또는 비즈니스용 Skype 서버의 원격 세션에서 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="92220-136">You can run this cmdlet either from the Skype for Business Server 2015 or from a remote session of Windows PowerShell.</span></span>
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="92220-137">단일 사용자에게 사용자당 다이얼 플랜을 할당하는 경우</span><span class="sxs-lookup"><span data-stu-id="92220-137">To assign a per-user dial plan to a single user</span></span>

- <span data-ttu-id="92220-138">[Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet을 사용하여 사용자 Ken Myer에게 사용자당 다이얼 플랜 RedmondDialPlan을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="92220-138">Use the [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to assign the per-user dial plan RedmondDialPlan to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="92220-139">여러 사용자에게 사용자당 다이얼 플랜을 할당하는 경우</span><span class="sxs-lookup"><span data-stu-id="92220-139">To assign a per-user dial plan to multiple users</span></span>

- <span data-ttu-id="92220-140">다음 명령은 사용자당 다이얼 플랜 RedmondDialPlan을 Redmond 시에서 작업하는 모든 사용자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="92220-140">The following command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="92220-141">이 명령에 사용되는 LdapFilter 매개 변수에 대한 자세한 내용은 [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps) cmdlet에 대한 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="92220-141">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps) cmdlet:</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> <span data-ttu-id="92220-142">온라인 사용자에 대해 전역 또는 사용자 다이얼 플랜을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92220-142">You may use either Global or User dial plans for online users.</span></span> <span data-ttu-id="92220-143">사이트 다이얼 플랜을 사용할 수는 없습니다. 이러한 계획은 프레미스에서 호스팅되는 사용자에게만 적용될 수 있으며, 이러한 요금제는 사내 사이트에 할당된 사용자에게만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="92220-143">Site dial plans cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="92220-144">사용자당 다이얼 플랜의 이지정을 확정하지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="92220-144">To unassign a per-user dial plan</span></span>

- <span data-ttu-id="92220-145">[Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet을 사용하여 이전에 Ken Myer에게 할당된 사용자당 다이얼 플랜의 할당을 할당을 중단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92220-145">Use the [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to unassign any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="92220-146">사용자당 다이얼 플랜이 할당되지 않은 후 Ken Myer는 등록자 또는 PSTN 게이트웨이에 할당된 서비스 범위 다이얼 플랜 또는 전역 다이얼 플랜을 사용하여 자동으로 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="92220-146">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="92220-147">서비스 범위 다이얼 플랜은 전역 다이얼 플랜보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="92220-147">A service scope dial plan takes precedence over the global dial plan:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="92220-148">cmdlet을 사용하여 음성 라우팅 정책 Windows PowerShell 업데이트</span><span class="sxs-lookup"><span data-stu-id="92220-148">Update the voice routing policies using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="92220-149">이 섹션에서는 전화 시스템에 대해 사용하도록 설정된 사용자에 대한 음성 라우팅 정책을 업데이트하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="92220-149">This section describes how to update the voice routing policies for users enabled for Phone System.</span></span>
  
<span data-ttu-id="92220-150">통화가 성공적으로 라우팅될 수 있도록 전화 시스템 사용자에게 음성 라우팅 정책이 할당되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92220-150">Phone System users must have a Voice Routing Policy assigned to them for calls to route successfully.</span></span> <span data-ttu-id="92220-151">이는 통화가 성공적으로 라우팅될 수 있도록 음성 정책을 할당해야 하는 사내 비즈니스 음성 사용자와는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="92220-151">This differs from on-premises business voice users who require a Voice Policy to be assigned to them to allow calls to route successfully.</span></span> <span data-ttu-id="92220-152">음성 라우팅 정책에는 전화 시스템 사용자에 대해 인증된 통화 및 경로를 정의하는 PSTN 사용법이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92220-152">The Voice Routing Policy should contain PSTN usages that define authorized calls and routes for Phone System users.</span></span> <span data-ttu-id="92220-153">이러한 PSTN 사용법을 기존 음성 정책에서 새 음성 라우팅 정책으로 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92220-153">You can copy these PSTN usages from existing Voice Policies to new Voice Routing Policies.</span></span> <span data-ttu-id="92220-154">자세한 내용은 [New-CsVoiceRoutingPolicy를 참조하세요.](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="92220-154">For more information, see [New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="92220-155">모든 전화 시스템 사용자에게 허용되는 통화 기능을 정의하는 BusinessVoice라는 온라인 음성 정책이 할당됩니다. 예를 들어 동시 벨 울림을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="92220-155">All Phone System users are assigned the same online Voice Policy named BusinessVoice which defines the calling features allowed; for example, Allow Simultaneous Ring.</span></span> 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a><span data-ttu-id="92220-156">단일 사용자에게 사용자당 음성 라우팅 정책을 할당하기 위해</span><span class="sxs-lookup"><span data-stu-id="92220-156">To assign a per-user voice routing policy to a single user</span></span>

- <span data-ttu-id="92220-157">[Grant-CsVoiceRoutingPolicy](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet을 사용하여 사용자 Ken Myer에게 사용자당 음성 라우팅 정책 RedmondVoiceRoutingPolicy를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="92220-157">Use the [Grant-CsVoiceRoutingPolicy](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet to assign the per-user voice routing policy RedmondVoiceRoutingPolicy to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a><span data-ttu-id="92220-158">여러 사용자에게 사용자당 음성 라우팅 정책을 할당하기 위해</span><span class="sxs-lookup"><span data-stu-id="92220-158">To assign a per-user voice routing policy to multiple users</span></span>

- <span data-ttu-id="92220-159">다음 명령은 Redmond 시에서 작업하는 모든 사용자에게 사용자당 음성 라우팅 정책 RedmondVoiceRoutingPolicy를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="92220-159">The next command assigns the per-user voice routing policy RedmondVoiceRoutingPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="92220-160">이 명령에 사용되는 LdapFilter 매개 변수에 대한 자세한 내용은 [Get-CsUser를 참조하세요.](/powershell/module/skype/get-csuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="92220-160">For more information on the LdapFilter parameter used in this command, see [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > <span data-ttu-id="92220-161">온라인 사용자에 대해 전역 또는 사용자 음성 라우팅 정책을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92220-161">You may use either Global or User voice routing policies for online users.</span></span> <span data-ttu-id="92220-162">사이트 음성 라우팅 정책은 이러한 정책이 프레미스에서 호스팅되는 사용자에게만 적용되어 있으며, 이 정책은 사내 사이트에 할당된 사용자에게만 적용될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="92220-162">Site voice routing policies cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a><span data-ttu-id="92220-163">사용자당 음성 라우팅 정책의 위임</span><span class="sxs-lookup"><span data-stu-id="92220-163">To unassign a per-user voice routing policy</span></span>

- <span data-ttu-id="92220-164">이 Grant-CsVoiceRoutingPolicy 사용하여 이전에 Ken Myer에게 할당된 사용자당 음성 라우팅 정책의 할당을 해지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92220-164">Use the Grant-CsVoiceRoutingPolicy to unassign any per-user voice routing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="92220-165">사용자당 음성 라우팅 정책의 사용이 자동으로 설정되지 않은 경우 Ken Myer는 전역 음성 라우팅 정책을 사용하여 자동으로 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="92220-165">After the per-user voice routing policy is unassigned, Ken Myer will automatically be managed by using the global voice routing policy.</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    <span data-ttu-id="92220-166">자세한 내용은 [Grant-CsVoiceRoutingPolicy를 참조하세요.](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="92220-166">For more information, see [Grant-CsVoiceRoutingPolicy](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span></span>
