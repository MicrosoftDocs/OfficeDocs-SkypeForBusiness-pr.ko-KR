---
title: Microsoft Teams 룸 Exchange Online
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: 이 항목을 참조하여 Microsoft Teams 룸 및 Exchange Online 비즈니스용 Skype 서버 정보를 참조하세요.
ms.openlocfilehash: 2f92f85ddf39c5e1a813492b3092eeeef9b77e4c
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796682"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a><span data-ttu-id="66627-103">Microsoft Teams 룸 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="66627-103">Deploy Microsoft Teams Rooms with Exchange Online</span></span>

<span data-ttu-id="66627-104">이 항목을 참조하여 Microsoft Teams 룸 및 Exchange Online 비즈니스용 Skype 서버 정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="66627-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="66627-105">조직에 일부 호스팅되는 일부 프레미스 및 온라인에서 호스팅되는 서비스가 혼합된 경우 구성은 각 서비스가 호스트되는 위치에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="66627-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="66627-106">이 항목에서는 온라인에서 호스팅되는 Microsoft Teams 룸 하이브리드 Exchange 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="66627-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted online.</span></span> <span data-ttu-id="66627-107">이 유형의 배포에는 다양한 변형이 있으므로 모든 배포에 대한 자세한 지침을 제공할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66627-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="66627-108">다음 프로세스는 여러 구성에 대해 작동할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="66627-108">The following process will work for many configurations.</span></span> <span data-ttu-id="66627-109">프로세스가 설정에 맞지 않는 경우 여기에서 설명한 Windows PowerShell 및 다른 배포 옵션에 대해 동일한 최종 결과를 달성하기 위해 이 프로세스를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="66627-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="66627-110">사용자 계정을 설정하는 가장 쉬운 방법은 원격 계정을 사용하여 구성하는 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="66627-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="66627-111">Microsoft는 [ ](https://go.microsoft.com/fwlink/?linkid=870105)SkypeRoomProvisioningScript.ps1사용자 계정으로 전환할 수 있도록 새 사용자 계정을 만들거나 기존 리소스 계정의 유효성을 검사하는 데 도움이 되는 Microsoft Teams 룸 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="66627-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="66627-112">원하는 경우 아래 단계를 수행하여 디바이스에서 사용할 계정을 Microsoft Teams 룸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66627-112">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="66627-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="66627-113">Requirements</span></span>

<span data-ttu-id="66627-114">Microsoft Teams 룸 배포하기 Exchange Online 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66627-114">Before you deploy Microsoft Teams Rooms with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="66627-115">자세한 내용은 요구 사항 [Microsoft Teams 룸 참조하세요.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="66627-115">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="66627-116">Microsoft Teams 룸 배포 Exchange Online 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="66627-116">To deploy Microsoft Teams Rooms with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="66627-117">연결된 cmdlet을 실행할 수 있는 권한이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="66627-117">Be sure you have the right permissions to run the associated cmdlets.</span></span> 

   > [!NOTE]
   >  <span data-ttu-id="66627-118">이 [Azure Active Directory cmdlet에](/powershell/azure/active-directory/overview?view=azureadps-1.0) 대한 Windows PowerShell 모듈(예: Set-MsolUser)은 디바이스에 대한 계정을 설정하는 Microsoft Teams 룸 테스트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="66627-118">The [Azure Active Directory Module for Windows PowerShell cmdlets](/powershell/azure/active-directory/overview?view=azureadps-1.0) in this section (for example,  Set-MsolUser) have been tested in setting up accounts for Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="66627-119">다른 cmdlet이 작동할 수 있습니다. 그러나 이 특정 시나리오에서는 테스트되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="66627-119">It's possible that other cmdlets may work, however, they haven't been tested in this specific scenario.</span></span>

<span data-ttu-id="66627-120">AD FS(Active Directory Federation Services)를 배포한 경우 이러한 단계를 수행하기 전에 사용자 계정을 관리 사용자로 변환한 다음, 이 단계를 완료한 후 사용자를 페더리드 사용자로 다시 변환해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66627-120">If you deployed Active Directory Federation Services (AD FS), you may have to convert the user account to a managed user before you follow these steps, and then convert the user back to a federated user after you complete these steps.</span></span>
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="66627-121">계정 만들기 및 Exchange 설정</span><span class="sxs-lookup"><span data-stu-id="66627-121">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="66627-122">PC에서 원격 Windows PowerShell 세션을 시작하고 다음과 같이 Exchange Online 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="66627-122">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org = 'contoso.microsoft.com'
    $cred = Get-Credential $admin@$org
    $sess = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
    Import-PSSession $sess -DisableNameChecking
    ```

2. <span data-ttu-id="66627-123">세션을 설정한 후 새 사서함을 만들고 RoomMailboxAccount로 사용하도록 설정하거나 기존 방 사서함에 대한 설정을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="66627-123">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="66627-124">이렇게 하면 계정에서 인증할 수 Microsoft Teams 룸.</span><span class="sxs-lookup"><span data-stu-id="66627-124">This will allow the account to authenticate into Microsoft Teams Rooms.</span></span>

   <span data-ttu-id="66627-125">기존 리소스 사서함을 변경하는 경우:</span><span class="sxs-lookup"><span data-stu-id="66627-125">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECT01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="66627-126">새 리소스 사서함을 만드는 경우:</span><span class="sxs-lookup"><span data-stu-id="66627-126">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECT01@contoso.com' -Alias PROJECT01 -Name "Project--01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="66627-127">모임 환경을 개선하려면 다음과 같이 사용자 계정에 Exchange 속성을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66627-127">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="66627-128">프레미스 도메인 계정에 대한 전자 메일 주소 추가</span><span class="sxs-lookup"><span data-stu-id="66627-128">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="66627-129">**Active Directory** 사용자 및 컴퓨터 AD 도구에서 사용자 계정이 생성될 컨테이너 또는 조직 Microsoft Teams 룸 마우스 오른쪽 단추로 클릭하고 새 을 클릭한 다음 사용자 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="66627-129">In **Active Directory Users and Computers AD** tool, right-click on the container or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>
2. <span data-ttu-id="66627-130">이전 cmdlet(Set-사서함 또는 새로-사서함)의 표시 이름(-  ID)을 전체 이름 상자에 입력하고 별칭을 사용자 로그온 이름 상자에 **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="66627-130">Type the display name (- Identity ) from the prior cmdlet (Set-Mailbox or New-Mailbox) into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="66627-131">다음 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="66627-131">Click **Next**.</span></span>
3. <span data-ttu-id="66627-132">이 계정에 대한 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="66627-132">Type the password for this account.</span></span> <span data-ttu-id="66627-133">확인을 위해 다시 타이프해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66627-133">You'll need to retype it for verification.</span></span> <span data-ttu-id="66627-134">암호가 **만료되지** 않는지 확인란만 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66627-134">Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="66627-135">암호가  만료되지 않는 경우 암호를 선택해야 비즈니스용 Skype 서버 Microsoft Teams 룸.</span><span class="sxs-lookup"><span data-stu-id="66627-135">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="66627-136">도메인 규칙은 만료되지 않는 암호를 금지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66627-136">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="66627-137">그렇다면 각 사용자 계정에 대한 예외를 Microsoft Teams 룸 합니다.</span><span class="sxs-lookup"><span data-stu-id="66627-137">If so, you'll need to create an exception for each Microsoft Teams Rooms user account.</span></span>
  
4. <span data-ttu-id="66627-138">**완료를** 클릭하여 계정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66627-138">Click **Finish** to create the account.</span></span>
5. <span data-ttu-id="66627-139">계정을 만든 후 디렉터리 동기화를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="66627-139">After you have created the account, run a directory synchronization.</span></span> <span data-ttu-id="66627-140">PowerShell에서 [Set-MsolDirSyncConfiguration을](/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) 사용하여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66627-140">This can be accomplished by using [Set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) in PowerShell.</span></span> <span data-ttu-id="66627-141">이 작업을 완료하면 사용자 페이지로 이동하여 이전 단계에서 만든 두 계정이 병합된지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66627-141">When that is complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

### <a name="assign-a-microsoft-365-or-office-365-license"></a><span data-ttu-id="66627-142">라이선스 Microsoft 365 또는 Office 365 할당</span><span class="sxs-lookup"><span data-stu-id="66627-142">Assign a Microsoft 365 or Office 365 license</span></span>

1. <span data-ttu-id="66627-143">먼저 Azure AD에 연결하여 일부 계정 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="66627-143">First, connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="66627-144">이 cmdlet을 실행하여 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66627-144">You can run this cmdlet to connect.</span></span> <span data-ttu-id="66627-145">Active Directory에 대한 자세한 내용은 [Azure ActiveDirectory(MSOnline) 1.0 을 참조하세요.](/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="66627-145">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

   > [!NOTE]
   > <span data-ttu-id="66627-146">[Azure Active Directory PowerShell 2.0은](/powershell/azure/active-directory/overview?view=azureadps-2.0) 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66627-146">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span>

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. <span data-ttu-id="66627-147">사용자 계정에 유효한 Microsoft 365 Office 365 라이선스가 있어야 Exchange 비즈니스용 Skype 서버 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66627-147">The user account needs to have a valid Microsoft 365 or Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="66627-148">라이선스가 있는 경우 사용자 계정에 사용 위치를 할당해야 합니다. 그러면 계정에 사용할 수 있는 라이선스 SKUS가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="66627-148">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="66627-149">다음 단계에서 과제를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="66627-149">You'll make the assignment in a following step.</span></span>
3. <span data-ttu-id="66627-150">다음으로, `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="66627-150">Next, use `Get-MsolAccountSku`</span></span> <!--Get-AzureADSubscribedSku--> <span data-ttu-id="66627-151">를 사용하여 사용자 또는 조직에서 사용할 수 있는 SKUS Microsoft 365 Office 365 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="66627-151">to retrieve a list of available SKUs for your Microsoft 365 or Office 365 organization.</span></span>
4. <span data-ttu-id="66627-152">SKUS를 나열하면 다음을 사용하여 라이선스를 추가할 수 있습니다. `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="66627-152">Once you list out the SKUs, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense--> <span data-ttu-id="66627-153">cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="66627-153">cmdlet.</span></span> <span data-ttu-id="66627-154">이 경우 $strLicense SKU 코드입니다(예: contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="66627-154">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span> 

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
    Get-MsolAccountSku
    Set-MsolUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
    ```
  <!--   ``` Powershell
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-AzureADSubscribedSku
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
     ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a><span data-ttu-id="66627-155">사용자 계정을 비즈니스용 Skype 서버</span><span class="sxs-lookup"><span data-stu-id="66627-155">Enable the user account with Skype for Business Server</span></span>

> [!NOTE]
> <span data-ttu-id="66627-156">모임에 Teams 룸 모임에 Microsoft Teams 설정하는 경우 다음 단계를 수행하지 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66627-156">If you're setting up Teams Rooms to only join Microsoft Teams meetings, you don't need to do the following steps.</span></span> <span data-ttu-id="66627-157">다음 단계는 사용자에 대한 지원을 사용하도록 설정하려는 비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="66627-157">The following steps are only required if you want to enable support for Skype for Business.</span></span>

1. <span data-ttu-id="66627-158">다음과 Windows PowerShell PC에서 원격 세션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66627-158">Create a remote Windows PowerShell session from a PC as follows:</span></span>

> [!NOTE]
> <span data-ttu-id="66627-159">비즈니스용 Skype 온라인 커넥터는 현재 최신 PowerShell Teams 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="66627-159">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="66627-160">최신 [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 Teams 사용하는 경우 온라인 커넥터를 비즈니스용 Skype 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66627-160">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

    ``` Powershell
    # When using Teams PowerShell Module
    Import-Module MicrosoftTeams
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

2. <span data-ttu-id="66627-161">Microsoft Teams 룸 계정을 사용하도록 비즈니스용 Skype 서버 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="66627-161">To enable your Microsoft Teams Rooms account for Skype for Business Server, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="66627-162">환경에서 RegistrarPool 매개 변수에 사용할 값이 확실하지 않은 경우 이 명령을 사용하여 기존 사용자로부터 값을 비즈니스용 Skype 서버 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66627-162">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="66627-163">비즈니스용 Skype 서버 계정에 Microsoft Teams 룸 할당</span><span class="sxs-lookup"><span data-stu-id="66627-163">Assign a Skype for Business Server license to your Microsoft Teams Rooms account</span></span>

> [!NOTE]
> <span data-ttu-id="66627-164">모임에 Teams 룸 모임에 Microsoft Teams 설정하는 경우 다음 단계를 수행하지 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66627-164">If you're setting up Teams Rooms to only join Microsoft Teams meetings, you don't need to do the following steps.</span></span> <span data-ttu-id="66627-165">다음 단계는 사용자에 대한 지원을 사용하도록 설정하려는 비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="66627-165">The following steps are only required if you want to enable support for Skype for Business.</span></span>

1. <span data-ttu-id="66627-166">테넌트 관리자로 로그인하고 관리자 Microsoft 365 센터를 열고 관리자 앱을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="66627-166">Log in as a tenant administrator, open the Microsoft 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="66627-167">사용자 및 **그룹을 클릭한** 다음 사용자 추가, 암호 재설정 **등 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="66627-167">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="66627-168">계정 Microsoft Teams 룸 클릭한 다음 펜 아이콘을 클릭하여 계정 정보를 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="66627-168">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="66627-169">라이선스를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="66627-169">Click **Licenses**.</span></span>
5. <span data-ttu-id="66627-170">라이선스 **할당에서** 라이선스 비즈니스용 Skype 요구 사항에 따라 비즈니스용 Skype(계획 2) 또는 비즈니스용 Skype(계획 3)를 Enterprise Voice 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="66627-170">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="66627-171">이 라이선스를 사용하려는 경우 계획 3 라이선스를 Enterprise Voice Microsoft Teams 룸.</span><span class="sxs-lookup"><span data-stu-id="66627-171">You'll have to use a Plan 3 license if you want to use Enterprise Voice on Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="66627-172">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="66627-172">Click **Save**.</span></span>

<span data-ttu-id="66627-173">유효성 검사를 위해 모든 클라이언트를 비즈니스용 Skype 이 계정에 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66627-173">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>

> [!NOTE]
> <span data-ttu-id="66627-174">현재 오디오 회의 또는 오디오 회의 및 통화 계획이 있는 비즈니스용 Skype 계획 전화 시스템2에서 E1, E3, E4 또는 E5 SKUS를 사용하고 있는 경우 이러한 SK는 계속 작동하게 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="66627-174">If you're currently using E1, E3, E4, or E5 SKUs with Skype for Business Plan 2 with Audio Conferencing or with Phone System and a Calling Plan, these will continue to work.</span></span> <span data-ttu-id="66627-175">그러나 현재 라이선스가 만료된 후 라이선스 업데이트에서 [](rooms-licensing.md)설명한 Teams 미팅룸 더 간단한 라이선스 모델로 이동하는 것이 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="66627-175">However, you should consider moving to a simpler licensing model as described in [Teams Meeting Room Licensing Update](rooms-licensing.md), after current licenses expire.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66627-176">계획 2를 사용하는 경우 비즈니스용 Skype 전용 모드에서만 Microsoft Teams 룸 비즈니스용 Skype 수 있습니다. 즉, 모든 모임은 비즈니스용 Skype 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66627-176">If you're using Skype for Business Plan 2, you can only use the Microsoft Teams Rooms in Skype for Business Only mode, meaning all of your meetings will be Skype for Business meetings.</span></span> <span data-ttu-id="66627-177">모임에 회의실을 사용하도록 설정하려면 Microsoft Teams 라이선스를 미팅룸 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="66627-177">In order to enable your meeting room for Microsoft Teams meetings, we recommend you purchase the Meeting Room license.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="66627-178">관련 항목</span><span class="sxs-lookup"><span data-stu-id="66627-178">Related topics</span></span>

[<span data-ttu-id="66627-179">Microsoft Teams 룸</span><span class="sxs-lookup"><span data-stu-id="66627-179">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="66627-180">Microsoft Teams 룸 계획</span><span class="sxs-lookup"><span data-stu-id="66627-180">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="66627-181">Microsoft Teams 룸 배포</span><span class="sxs-lookup"><span data-stu-id="66627-181">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="66627-182">Microsoft Teams 룸 콘솔 구성</span><span class="sxs-lookup"><span data-stu-id="66627-182">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="66627-183">Microsoft Teams 룸 관리</span><span class="sxs-lookup"><span data-stu-id="66627-183">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
