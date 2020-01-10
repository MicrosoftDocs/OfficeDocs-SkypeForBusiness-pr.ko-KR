---
title: 사용자가 Office 365 음성 사서함에서 전화 시스템과 Enterprise Voice 라인을 사용하도록 설정
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: 비즈니스용 Skype 사용자를 위한 Office 365 음성 서비스에서 전화 시스템을 사용 하도록 설정 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 902d2e1bad76c8275bfc8f4ce7ec7b4243b8572a
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003468"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-in-office-365-voicemail"></a><span data-ttu-id="83bde-103">사용자가 Office 365 음성 사서함에서 전화 시스템과 Enterprise Voice 라인을 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="83bde-103">Enable users for Enterprise Voice online and Phone System in Office 365 Voicemail</span></span>
 
<span data-ttu-id="83bde-104">비즈니스용 Skype 사용자를 위한 Office 365 음성 서비스에서 전화 시스템을 사용 하도록 설정 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-104">Learn how to enable Phone System in Office 365 voice services for your Skype for Business users.</span></span>
  
<span data-ttu-id="83bde-105">온-프레미스 PSTN 연결을 사용 하 여 Office 365에서 전화 시스템을 배포 하는 마지막 단계는 Office 365 및 보이스 메일에서 사용자의 전화 시스템을 사용 하도록 설정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-105">The final step in deploying Phone System in Office 365 with on-premises PSTN connectivity is to enable your users for Phone System in Office 365 and voicemail.</span></span> <span data-ttu-id="83bde-106">이러한 접근 권한 값을 사용 하려면 Office 365 전역 관리자 역할이 있는 사용자 여야 하며 원격 PowerShell을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-106">To enable these capabilities, you must be a user with the Office 365 Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="83bde-107">비즈니스용 Skype Online에 Enterprise Voice가 설정 되어 있지 않은 모든 사용자 계정에 대해이 항목의 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-107">You need to follow the steps in this topic for all user accounts that do not already have Enterprise Voice enabled for Skype for Business Online.</span></span>
  
## <a name="enable-phone-system-in-office-365-voice-services"></a><span data-ttu-id="83bde-108">Office 365 음성 서비스에서 전화 시스템 사용</span><span class="sxs-lookup"><span data-stu-id="83bde-108">Enable Phone System in Office 365 voice services</span></span>

<span data-ttu-id="83bde-109">Office 365 음성 및 음성 메일에서 전화 시스템용 사용자를 사용 하도록 설정 하려면 비즈니스용 Skype Online Connector가 서버에 배포 되어 있으며 사용자가 호스트 된 보이스 메일을 사용할 수 있도록 하는 등의 몇 가지 초기 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-109">To enable a user for Phone System in Office 365 Voice and voicemail, you'll need to perform some initial steps, like checking to see if the Skype for Business Online Connector is deployed on your servers and enable your users for hosted voicemail.</span></span>
  
### <a name="to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail"></a><span data-ttu-id="83bde-110">Office 365 음성 및 음성 메일에서 전화 시스템용 사용자를 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="83bde-110">To enable your users for Phone System in Office 365 voice and voicemail</span></span>

1. <span data-ttu-id="83bde-111">시작 하기 전에 비즈니스용 Skype Online 커넥터 (Windows PowerShell 모듈)가 프런트 엔드 서버에 배포 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-111">Before you begin, check that the Skype for Business Online Connector (Windows PowerShell module) is deployed on your Front End Servers.</span></span> <span data-ttu-id="83bde-112">그렇지 않은 경우 [다운로드 센터](https://www.microsoft.com/en-us/download/details.aspx?id=39366)에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-112">If it's not, you can download it from [the download center](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span> <span data-ttu-id="83bde-113">[비즈니스용 Skype Online 관리를 위해 컴퓨터를 구성할](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx)때이 모듈을 사용 하는 방법에 대 한 자세한 내용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-113">You can find more information about using this module at [Configuring your computer for Skype for Business Online management](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx).</span></span>
    
2. <span data-ttu-id="83bde-114">관리자 권한으로 Windows PowerShell을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-114">Start Windows PowerShell as an administrator.</span></span>
    
3. <span data-ttu-id="83bde-115">다음을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-115">Type the following and press Enter:</span></span>
    
   ```powershell
   Import-Module skypeonlineconnector
   ```

4. <span data-ttu-id="83bde-116">다음을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-116">Type the following and press Enter:</span></span>
    
   ```powershell
   $cred = Get-Credential
   ```

    <span data-ttu-id="83bde-117">Enter 키를 누르면 Windows PowerShell 자격 증명 대화 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-117">After you press Enter, you should see the Windows PowerShell Credential dialog box.</span></span>
    
5. <span data-ttu-id="83bde-118">테 넌 트 관리자 사용자 이름 및 암호를 입력 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-118">Type your tenant admin username and password, and click **OK**.</span></span>
    
6. <span data-ttu-id="83bde-119">PowerShell 창에서 다음을 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-119">In the PowerShell window, type the following and press Enter:</span></span>
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. <span data-ttu-id="83bde-120">다음 cmdlet을 입력 하 여 세션을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-120">Import the session by typing the following cmdlet:</span></span>
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    <span data-ttu-id="83bde-121">비즈니스용 Skype Server에서 PowerShell을 실행 하는 경우 PowerShell을 열 때 로컬 비즈니스용 Skype cmdlet이 이미 로드 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-121">When running PowerShell on a Skype for Business Server, the local Skype for Business cmdlets are already loaded when you open PowerShell.</span></span> <span data-ttu-id="83bde-122">온라인 cmdlet이 동일한 이름을 사용 하 여 온-프레미스 cmdlet을 덮어쓸 수 있도록 하려면-AllowClobber 매개 변수를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-122">You must specify the -AllowClobber parameter to allow the online cmdlets to overwrite the on-premises cmdlets with the same name.</span></span>
    
8. <span data-ttu-id="83bde-123">Set-CsUser cmdlet을 사용 하 여 $EnterpriseVoiceEnabled를 할당 하 고 다음과 같이 사용자에 게 속성을 $HostedVoiceMail 합니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-123">Use the Set-CsUser cmdlet to assign the $EnterpriseVoiceEnabled and $HostedVoiceMail properties to your user as follows:</span></span>
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    <span data-ttu-id="83bde-124">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-124">For example:</span></span>
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > <span data-ttu-id="83bde-125">또한 SIP 주소, UPN (사용자 계정 이름), 도메인 이름 및 사용자 이름 (domain\username), Active Directory에서 표시 이름 ("Bob 최소라")을 기준으로 사용자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-125">You can also specify a user by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system-in-office-365"></a><span data-ttu-id="83bde-126">Office 365에서 전화 시스템을 사용 하도록 설정 된 사용자에 대 한 줄 URI 및 다이얼 플랜 업데이트</span><span class="sxs-lookup"><span data-stu-id="83bde-126">Update the Line URI and dial plan for users enabled for Phone System in Office 365</span></span>

<span data-ttu-id="83bde-127">이 섹션에서는 Office 365에서 전화 시스템을 사용 하도록 설정 된 사용자 용 줄 URI 및 다이얼 플랜을 업데이트 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-127">This section describes how to update the Line URI and dial plan for users enabled for Phone System in Office 365.</span></span> 
  
### <a name="to-update-the-line-uri"></a><span data-ttu-id="83bde-128">줄 URI를 업데이트 하려면</span><span class="sxs-lookup"><span data-stu-id="83bde-128">To update the Line URI</span></span>

1. <span data-ttu-id="83bde-129">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-129">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="83bde-130">시작 메뉴 또는 바탕 화면 바로 가기를 사용 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-130">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="83bde-131">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype Server 제어판을 열 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-131">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span> 
  
3. <span data-ttu-id="83bde-132">왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-132">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="83bde-133">**사용자 검색** 상자에 표시 이름, 성, 이름, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 사용 하도록 설정할 사용자 계정의 URI (Uniform resource identifier) 중 일부 또는 전체를 입력 한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-133">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="83bde-134">표에서 줄 URI를 변경 하려는 비즈니스용 Skype 사용자 계정을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-134">In the table, click the Skype for Business user account that you want to change line URI.</span></span>
    
6. <span data-ttu-id="83bde-135">**줄 URI**를 클릭 하 고 고유한 정규화 된 전화 번호를 입력 합니다 (예: tel: + 14255550200).</span><span class="sxs-lookup"><span data-stu-id="83bde-135">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="83bde-136">그런 다음 **커밋을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-136">Then click **Commit**.</span></span>
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="83bde-137">온-프레미스 Windows PowerShell cmdlet을 사용 하 여 다이얼 플랜 업데이트</span><span class="sxs-lookup"><span data-stu-id="83bde-137">Update the dial plan using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="83bde-138">Windows PowerShell 및 [권한 부여-csdialplan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet을 사용 하 여 사용자 단위 다이얼 플랜을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-138">You can assign per-user dial plans with Windows PowerShell and the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="83bde-139">이 cmdlet은 비즈니스용 Skype 서버 2015 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-139">You can run this cmdlet either from the Skype for Business Server 2015 or from a remote session of Windows PowerShell.</span></span>
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="83bde-140">사용자 당 다이얼 플랜을 단일 사용자에 게 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="83bde-140">To assign a per-user dial plan to a single user</span></span>

- <span data-ttu-id="83bde-141">[권한 부여-csdialplan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet을 사용 하 여 사용자 단위 다이얼 플랜 RedmondDialPlan을 사용자: 진구 Myer에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-141">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to assign the per-user dial plan RedmondDialPlan to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="83bde-142">사용자 단위 다이얼 플랜을 여러 사용자에 게 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="83bde-142">To assign a per-user dial plan to multiple users</span></span>

- <span data-ttu-id="83bde-143">다음 명령을 사용 하 여 사용자 단위 다이얼 플랜 RedmondDialPlan을 Redmond의 구/군/시로 근무 하는 모든 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-143">The following command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="83bde-144">이 명령에 사용 되는 LdapFilter 매개 변수에 대 한 자세한 내용은 [Get CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet에 대 한 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="83bde-144">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet:</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> <span data-ttu-id="83bde-145">온라인 사용자에 게 전역 또는 사용자 다이얼 플랜을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-145">You may use either Global or User dial plans for online users.</span></span> <span data-ttu-id="83bde-146">사이트 다이얼 플랜은 온-프레미스에서 호스트 되 고 온-프레미스 사이트에 할당 된 사용자 에게만 적용 되므로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-146">Site dial plans cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="83bde-147">사용자 단위 다이얼 플랜을 할당 취소 하려면</span><span class="sxs-lookup"><span data-stu-id="83bde-147">To unassign a per-user dial plan</span></span>

- <span data-ttu-id="83bde-148">[허용-csdialplan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet을 사용 하 여 이전에: 진구 Myer에 할당 된 사용자 단위 다이얼 플랜을 할당 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-148">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to unassign any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="83bde-149">사용자 단위 다이얼 플랜의 할당을 해제 한 후에는: 진구 Myer이 전역 다이얼 플랜 또는 해당 레지스트라 또는 PSTN 게이트웨이에 할당 된 서비스 범위 다이얼 플랜을 사용 하 여 자동으로 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-149">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="83bde-150">서비스 범위 다이얼 플랜은 전역 다이얼 플랜에 우선권을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-150">A service scope dial plan takes precedence over the global dial plan:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="83bde-151">온-프레미스 Windows PowerShell cmdlet을 사용 하 여 음성 라우팅 정책 업데이트</span><span class="sxs-lookup"><span data-stu-id="83bde-151">Update the voice routing policies using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="83bde-152">이 섹션에서는 Office 365에서 전화 시스템을 사용 하도록 설정 된 사용자에 대 한 음성 라우팅 정책을 업데이트 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-152">This section describes how to update the voice routing policies for users enabled for Phone System in Office 365.</span></span>
  
<span data-ttu-id="83bde-153">Office 365에서 전화를 거는 통화에 대 한 음성 라우팅 정책이 사용자에 게 할당 되어 있어야 연결 경로가 성공적으로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-153">Phone System in Office 365 users must have a Voice Routing Policy assigned to them for calls to route successfully.</span></span> <span data-ttu-id="83bde-154">이는 전화를 성공적으로 라우팅하도록 허용 하기 위해 음성 정책을 할당 해야 하는 온-프레미스 비즈니스 음성 사용자와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-154">This differs from on-premises business voice users who require a Voice Policy to be assigned to them to allow calls to route successfully.</span></span> <span data-ttu-id="83bde-155">음성 라우팅 정책에는 Office 365 사용자에서 전화 시스템에 대 한 인증 된 통화 및 경로를 정의 하는 PSTN 사용이 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-155">The Voice Routing Policy should contain PSTN usages that define authorized calls and routes for Phone System in Office 365 users.</span></span> <span data-ttu-id="83bde-156">기존 음성 정책에서 이러한 PSTN 용도를 새 음성 라우팅 정책으로 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-156">You can copy these PSTN usages from existing Voice Policies to new Voice Routing Policies.</span></span> <span data-ttu-id="83bde-157">자세한 내용은 [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="83bde-157">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="83bde-158">Office 365 사용자의 모든 전화 시스템에는 허용 되는 통화 기능을 정의 하는 BusinessVoice 이라는 동일한 온라인 음성 정책이 할당 됩니다. 예를 들어 동시 벨 울림을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-158">All Phone System in Office 365 users are assigned the same online Voice Policy named BusinessVoice which defines the calling features allowed; for example, Allow Simultaneous Ring.</span></span> 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a><span data-ttu-id="83bde-159">단일 사용자에 게 사용자 단위 음성 라우팅 정책을 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="83bde-159">To assign a per-user voice routing policy to a single user</span></span>

- <span data-ttu-id="83bde-160">[CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet을 사용 하 여 사용자 단위 음성 라우팅 정책 RedmondVoiceRoutingPolicy을 User: 진구 Myer에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-160">Use the [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet to assign the per-user voice routing policy RedmondVoiceRoutingPolicy to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a><span data-ttu-id="83bde-161">사용자 단위 음성 라우팅 정책을 여러 사용자에 게 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="83bde-161">To assign a per-user voice routing policy to multiple users</span></span>

- <span data-ttu-id="83bde-162">다음 명령을 사용 하 여 사용자 단위 음성 라우팅 정책을 Redmond의 구/군/시로 근무 하는 모든 사용자에 게 RedmondVoiceRoutingPolicy를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-162">The next command assigns the per-user voice routing policy RedmondVoiceRoutingPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="83bde-163">이 명령에 사용 되는 LdapFilter 매개 변수에 대 한 자세한 내용은 [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="83bde-163">For more information on the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > <span data-ttu-id="83bde-164">온라인 사용자에 게 글로벌 또는 사용자 음성 라우팅 정책을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-164">You may use either Global or User voice routing policies for online users.</span></span> <span data-ttu-id="83bde-165">사이트 음성 라우팅 정책은 온-프레미스에 호스트 되 고 온-프레미스 사이트에 할당 된 사용자 에게만 적용 되므로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-165">Site voice routing policies cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a><span data-ttu-id="83bde-166">사용자 단위 음성 라우팅 정책을 할당 취소 하려면</span><span class="sxs-lookup"><span data-stu-id="83bde-166">To unassign a per-user voice routing policy</span></span>

- <span data-ttu-id="83bde-167">CsVoiceRoutingPolicy를 사용 하 여 이전에: 진구 Myer에 할당 된 사용자 단위 음성 라우팅 정책을 할당 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-167">Use the Grant-CsVoiceRoutingPolicy to unassign any per-user voice routing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="83bde-168">사용자 단위 음성 라우팅 정책을 할당 하지 않으면: 진구 Myer는 전역 음성 라우팅 정책을 사용 하 여 자동으로 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83bde-168">After the per-user voice routing policy is unassigned, Ken Myer will automatically be managed by using the global voice routing policy.</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    <span data-ttu-id="83bde-169">자세한 내용은 [허용-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="83bde-169">For more information, see [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span></span>
    

