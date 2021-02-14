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
ms.openlocfilehash: 76fbc20b11c0ec91685479d768b88abf71b65d21
ms.sourcegitcommit: 619b68d28b4fbf8b5296d95bbc7ed566f839f1db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/20/2020
ms.locfileid: "48625114"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a><span data-ttu-id="df240-103">사용자가 전화 시스템 음성 사서함과 온라인으로 Enterprise Voice를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="df240-103">Enable users for Enterprise Voice online and Phone System Voicemail</span></span>
 
> [!Important]
> <span data-ttu-id="df240-104">비즈니스용 Skype Online은 2021년 7월 31에 서비스가 더 이상 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="df240-104">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="df240-105">또한 비즈니스용 Skype 서버 또는 클라우드 커넥터 버전과 비즈니스용 Skype Online을 통해 더 이상 지원되지 않는 모든 비즈니스용 Skype 환경 간의 PSTN 연결도 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="df240-105">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="df240-106">직접 라우팅을 사용하여 프레미스 전화 통신 네트워크를 Teams에 연결하는 [방법을 학습합니다.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="df240-106">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="df240-107">비즈니스용 Skype 사용자에 대해 전화 시스템 음성 서비스를 사용하도록 설정하는 방법을 배워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df240-107">Learn how to enable Phone System voice services for your Skype for Business users.</span></span>
  
<span data-ttu-id="df240-108">전화 시스템을 배포하는 마지막 단계는 사용자가 전화 시스템 및 음성메일을 사용할 수 있도록 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="df240-108">The final step in deploying Phone System with on-premises PSTN connectivity is to enable your users for Phone System and voicemail.</span></span> <span data-ttu-id="df240-109">이러한 기능을 사용하려면 전역 관리자 역할이 있는 사용자로 원격 PowerShell을 실행할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df240-109">To enable these capabilities, you must be a user with the Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="df240-110">비즈니스용 Skype Online에 대해 아직 사용하도록 설정되지 않은 모든 사용자 계정에 대해 이 Enterprise Voice 단계를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df240-110">You need to follow the steps in this topic for all user accounts that do not already have Enterprise Voice enabled for Skype for Business Online.</span></span>
  
## <a name="enable-phone-system-voice-services"></a><span data-ttu-id="df240-111">전화 시스템 음성 서비스 사용</span><span class="sxs-lookup"><span data-stu-id="df240-111">Enable Phone System voice services</span></span>

<span data-ttu-id="df240-112">사용자가 전화 시스템 음성 및 음성메일을 사용할 수 있도록 설정하려면 서버에 비즈니스용 Skype Online 커넥터가 배포되어 있으며 사용자가 호스팅된 음성메일을 사용할 수 있도록 설정하는 등 몇 가지 초기 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df240-112">To enable a user for Phone System Voice and voicemail, you'll need to perform some initial steps, like checking to see if the Skype for Business Online Connector is deployed on your servers and enable your users for hosted voicemail.</span></span>
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a><span data-ttu-id="df240-113">사용자가 전화 시스템 음성 및 음성메일을 사용할 수 있도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="df240-113">To enable your users for Phone System voice and voicemail</span></span>

> [!NOTE]
> <span data-ttu-id="df240-114">비즈니스용 Skype Online 커넥터는 현재 최신 Teams PowerShell 모듈의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="df240-114">Skype for Business Online Connector is currently part of latest Teams PowerShell Module.</span></span>
> <span data-ttu-id="df240-115">최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 릴리스를 사용하는 경우 비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="df240-115">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

1. <span data-ttu-id="df240-116">시작하기 전에 Teams PowerShell 모듈이 프런트 엔드 서버에 설치되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="df240-116">Before you begin, check that the Teams PowerShell module is installed on your Front End Servers.</span></span> <span data-ttu-id="df240-117">그렇지 않은 경우 Teams PowerShell 모듈 설치에 있는 지침을 [사용하여 설치하세요.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="df240-117">If it's not, please  install using the instructions in [Teams PowerShell Module Installation](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="df240-118">관리자 Windows PowerShell 시작</span><span class="sxs-lookup"><span data-stu-id="df240-118">Start Windows PowerShell as an administrator.</span></span>
    
3. <span data-ttu-id="df240-119">다음을 입력하고 Enter를 누를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df240-119">Type the following and press Enter:</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   ```

4. <span data-ttu-id="df240-120">다음을 입력하고 Enter를 누를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df240-120">Type the following and press Enter:</span></span>
    
   ```powershell
   $cred = Get-Credential
   ```

    <span data-ttu-id="df240-121">Enter를 누르면 자격 증명 Windows PowerShell 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="df240-121">After you press Enter, you should see the Windows PowerShell Credential dialog box.</span></span>
    
5. <span data-ttu-id="df240-122">테넌트 관리자 사용자 이름과 암호를 입력하고 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="df240-122">Type your tenant admin username and password, and click **OK**.</span></span>
    
6. <span data-ttu-id="df240-123">PowerShell 창에서 다음을 입력하고 Enter를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="df240-123">In the PowerShell window, type the following and press Enter:</span></span>
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. <span data-ttu-id="df240-124">다음 cmdlet을 입력하여 세션을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df240-124">Import the session by typing the following cmdlet:</span></span>
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    <span data-ttu-id="df240-125">비즈니스용 Skype 서버에서 PowerShell을 실행하는 경우 PowerShell을 열면 로컬 비즈니스용 Skype cmdlet이 이미 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="df240-125">When running PowerShell on a Skype for Business Server, the local Skype for Business cmdlets are already loaded when you open PowerShell.</span></span> <span data-ttu-id="df240-126">온라인 cmdlet이 같은 이름의 온라인 cmdlet을 덮어 사용할 수 있도록 -AllowClobber 매개 변수를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df240-126">You must specify the -AllowClobber parameter to allow the online cmdlets to overwrite the on-premises cmdlets with the same name.</span></span>
    
8. <span data-ttu-id="df240-127">Set-CsUser cmdlet을 사용하여 $EnterpriseVoiceEnabled 및 $HostedVoiceMail 속성을 사용자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="df240-127">Use the Set-CsUser cmdlet to assign the $EnterpriseVoiceEnabled and $HostedVoiceMail properties to your user as follows:</span></span>
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    <span data-ttu-id="df240-128">예시:</span><span class="sxs-lookup"><span data-stu-id="df240-128">For example:</span></span>
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > <span data-ttu-id="df240-129">또한 사용자의 SIP 주소, UPN(사용자 계정 이름), 도메인 이름 및 사용자 이름(도메인\사용자 이름) 및 Active Directory의 표시 이름("Bob Kelly")으로 사용자를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df240-129">You can also specify a user by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a><span data-ttu-id="df240-130">전화 시스템을 사용하도록 설정된 사용자의 줄 URI 및 다이얼 플랜 업데이트</span><span class="sxs-lookup"><span data-stu-id="df240-130">Update the Line URI and dial plan for users enabled for Phone System</span></span>

<span data-ttu-id="df240-131">이 섹션에서는 전화 시스템을 사용하도록 설정된 사용자의 줄 URI 및 다이얼 플랜을 업데이트하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="df240-131">This section describes how to update the Line URI and dial plan for users enabled for Phone System.</span></span> 
  
### <a name="to-update-the-line-uri"></a><span data-ttu-id="df240-132">줄 URI를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="df240-132">To update the Line URI</span></span>

1. <span data-ttu-id="df240-133">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="df240-133">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="df240-134">시작 메뉴 또는 데스크톱 바로 가기를 사용하여 비즈니스용 Skype 서버 제어판을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df240-134">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="df240-135">브라우저 창을 연 다음 관리자 URL을 입력하여 비즈니스용 Skype 서버 제어판을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df240-135">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span> 
  
3. <span data-ttu-id="df240-136">왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="df240-136">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="df240-137">**사용자 검색** 상자에 사용하도록 설정할 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫부분을 입력하고 **찾기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="df240-137">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="df240-138">표에서 줄 URI를 변경할 비즈니스용 Skype 사용자 계정을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="df240-138">In the table, click the Skype for Business user account that you want to change line URI.</span></span>
    
6. <span data-ttu-id="df240-139">줄 **URI를** 클릭하고 고유한 정규화된 전화 번호(예: tel:+14255550200)를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="df240-139">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="df240-140">그런 다음 **커밋을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="df240-140">Then click **Commit**.</span></span>
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="df240-141">프레미스 및 cmdlet을 사용하여 Windows PowerShell 업데이트</span><span class="sxs-lookup"><span data-stu-id="df240-141">Update the dial plan using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="df240-142">권한 부여 및 [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet을 사용하여 Windows PowerShell 다이얼 플랜을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df240-142">You can assign per-user dial plans with Windows PowerShell and the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="df240-143">이 cmdlet은 비즈니스용 Skype 서버 2015 또는 비즈니스용 Skype의 원격 세션에서 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df240-143">You can run this cmdlet either from the Skype for Business Server 2015 or from a remote session of Windows PowerShell.</span></span>
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="df240-144">사용자당 다이얼 플랜을 단일 사용자에게 할당</span><span class="sxs-lookup"><span data-stu-id="df240-144">To assign a per-user dial plan to a single user</span></span>

- <span data-ttu-id="df240-145">[Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet을 사용하여 사용자 Ken Myer에게 사용자당 다이얼 플랜 RedmondDialPlan을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="df240-145">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to assign the per-user dial plan RedmondDialPlan to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="df240-146">사용자당 다이얼 플랜을 여러 사용자에게 할당</span><span class="sxs-lookup"><span data-stu-id="df240-146">To assign a per-user dial plan to multiple users</span></span>

- <span data-ttu-id="df240-147">다음 명령은 Redmond 시에서 작업하는 모든 사용자에게 사용자당 다이얼 플랜 RedmondDialPlan을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="df240-147">The following command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="df240-148">이 명령에 사용된 LdapFilter 매개 변수에 대한 자세한 내용은 [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet에 대한 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="df240-148">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet:</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> <span data-ttu-id="df240-149">온라인 사용자에 대해 전역 또는 사용자 다이얼 플랜을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df240-149">You may use either Global or User dial plans for online users.</span></span> <span data-ttu-id="df240-150">사이트 다이얼 플랜은 이러한 다이얼 플랜이 프레미스에서 호스팅되는 사용자에게만 적용될 수 있으며, 이 경우 해당 다이얼 플랜을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="df240-150">Site dial plans cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="df240-151">사용자당 다이얼 플랜의 사용이 확정되지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="df240-151">To unassign a per-user dial plan</span></span>

- <span data-ttu-id="df240-152">[Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet을 사용하여 이전에 Ken Myer에게 할당된 사용자당 다이얼 플랜의 할당을 Unassigner로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="df240-152">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to unassign any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="df240-153">사용자당 다이얼 플랜을 할당하지 않은 후 Ken Myer는 전역 다이얼 플랜 또는 등록자 또는 PSTN 게이트웨이에 할당된 서비스 범위 다이얼 플랜을 사용하여 자동으로 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="df240-153">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="df240-154">서비스 범위 다이얼 플랜은 전역 다이얼 플랜보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="df240-154">A service scope dial plan takes precedence over the global dial plan:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="df240-155">cmdlet을 사용하여 음성 라우팅 Windows PowerShell 업데이트</span><span class="sxs-lookup"><span data-stu-id="df240-155">Update the voice routing policies using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="df240-156">이 섹션에서는 전화 시스템에 대해 사용하도록 설정된 사용자의 음성 라우팅 정책을 업데이트하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="df240-156">This section describes how to update the voice routing policies for users enabled for Phone System.</span></span>
  
<span data-ttu-id="df240-157">통화를 성공적으로 라우팅하려면 전화 시스템 사용자에게 음성 라우팅 정책이 할당되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df240-157">Phone System users must have a Voice Routing Policy assigned to them for calls to route successfully.</span></span> <span data-ttu-id="df240-158">이는 통화가 성공적으로 라우팅될 수 있도록 음성 정책을 할당해야 하는 On-프레미스 비즈니스 음성 사용자와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="df240-158">This differs from on-premises business voice users who require a Voice Policy to be assigned to them to allow calls to route successfully.</span></span> <span data-ttu-id="df240-159">음성 라우팅 정책에는 전화 시스템 사용자에 대해 권한이 부여된 통화 및 경로를 정의하는 PSTN 사용법이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df240-159">The Voice Routing Policy should contain PSTN usages that define authorized calls and routes for Phone System users.</span></span> <span data-ttu-id="df240-160">이러한 PSTN 사용법을 기존 음성 정책에서 새 음성 라우팅 정책으로 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df240-160">You can copy these PSTN usages from existing Voice Policies to new Voice Routing Policies.</span></span> <span data-ttu-id="df240-161">자세한 내용은 [New-CsVoiceRoutingPolicy를 참조하세요.](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="df240-161">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="df240-162">모든 전화 시스템 사용자에게 허용된 통화 기능을 정의하는 BusinessVoice라는 온라인 음성 정책이 할당됩니다. 예를 들어 동시 벨 울림을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="df240-162">All Phone System users are assigned the same online Voice Policy named BusinessVoice which defines the calling features allowed; for example, Allow Simultaneous Ring.</span></span> 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a><span data-ttu-id="df240-163">단일 사용자에게 사용자당 음성 라우팅 정책을 할당하기 위해</span><span class="sxs-lookup"><span data-stu-id="df240-163">To assign a per-user voice routing policy to a single user</span></span>

- <span data-ttu-id="df240-164">[Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet을 사용하여 사용자 Ken Myer에게 사용자당 음성 라우팅 정책 RedmondVoiceRoutingPolicy를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="df240-164">Use the [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet to assign the per-user voice routing policy RedmondVoiceRoutingPolicy to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a><span data-ttu-id="df240-165">여러 사용자에게 사용자당 음성 라우팅 정책을 할당하기 위해</span><span class="sxs-lookup"><span data-stu-id="df240-165">To assign a per-user voice routing policy to multiple users</span></span>

- <span data-ttu-id="df240-166">다음 명령은 Redmond 시에서 작업하는 모든 사용자에게 사용자당 음성 라우팅 정책 RedmondVoiceRoutingPolicy를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="df240-166">The next command assigns the per-user voice routing policy RedmondVoiceRoutingPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="df240-167">이 명령에 사용된 LdapFilter 매개 변수에 대한 자세한 내용은 [Get-CsUser를 참조하십시오.](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="df240-167">For more information on the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > <span data-ttu-id="df240-168">온라인 사용자에 대해 전역 또는 사용자 음성 라우팅 정책을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df240-168">You may use either Global or User voice routing policies for online users.</span></span> <span data-ttu-id="df240-169">사이트 음성 라우팅 정책은 이러한 정책이 프레미스에서 호스팅되는 사용자에게만 적용될 수 있으며, 이 정책은 모든 사용자에게 적용될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="df240-169">Site voice routing policies cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a><span data-ttu-id="df240-170">사용자당 음성 라우팅 정책의 위임</span><span class="sxs-lookup"><span data-stu-id="df240-170">To unassign a per-user voice routing policy</span></span>

- <span data-ttu-id="df240-171">이 Grant-CsVoiceRoutingPolicy Ken Myer에게 이전에 할당된 사용자당 음성 라우팅 정책의 할당을 해지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df240-171">Use the Grant-CsVoiceRoutingPolicy to unassign any per-user voice routing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="df240-172">사용자당 음성 라우팅 정책의 사용이 자동으로 수행되고 나면 Ken Myer는 전역 음성 라우팅 정책을 사용하여 자동으로 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="df240-172">After the per-user voice routing policy is unassigned, Ken Myer will automatically be managed by using the global voice routing policy.</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    <span data-ttu-id="df240-173">자세한 내용은 [Grant-CsVoiceRoutingPolicy를 참조하세요.](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="df240-173">For more information, see [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span></span>
    

