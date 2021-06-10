---
title: Microsoft Teams 룸 또는 Microsoft Teams 룸 Microsoft 365 배포합니다Office 365
ms.author: v-cichur
author: cichur
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
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: 이 항목을 참조하세요. Microsoft Teams 룸 또는 Microsoft 365 Office 365 또는 온라인 Teams 비즈니스용 Skype Exchange 참조하세요.
ms.openlocfilehash: 64567cd9925a0a11d9e9b896c522a2c4bfe13f40
ms.sourcegitcommit: 3840d72f9ad1c0c7803dc3662a0318f558fe92ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739648"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a><span data-ttu-id="ceae6-103">Microsoft Teams 룸 또는 Microsoft Teams 룸 Microsoft 365 배포합니다Office 365</span><span class="sxs-lookup"><span data-stu-id="ceae6-103">Deploy Microsoft Teams Rooms with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="ceae6-104">이 항목을 참조하여 Microsoft Teams 룸 또는 Microsoft 365 Office 365 온라인 Microsoft Teams 비즈니스용 Skype Exchange 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ceae6-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, where Microsoft Teams or Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="ceae6-105">사용자 계정을 설정하는 가장 쉬운 방법은 원격 계정을 사용하여 구성하는 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ceae6-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="ceae6-106">Microsoft는 [ ](https://go.microsoft.com/fwlink/?linkid=870105)SkypeRoomProvisioningScript.ps1사용자 계정으로 전환할 수 있도록 새 사용자 계정을 만들거나 기존 리소스 계정의 유효성을 검사하는 데 도움이 되는 Microsoft Teams 룸 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="ceae6-107">원하는 경우 아래 단계를 수행하여 디바이스에서 사용할 계정을 Microsoft Teams 룸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-107">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="ceae6-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ceae6-108">Requirements</span></span>

<span data-ttu-id="ceae6-109">Microsoft Teams 룸 또는 Microsoft 365 Office 365 배포하기 전에 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-109">Before you deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="ceae6-110">자세한 내용은 요구 사항 [Microsoft Teams 룸 참조하세요.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="ceae6-110">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>

<span data-ttu-id="ceae6-111">비즈니스용 Skype하려면 다음이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="ceae6-112">비즈니스용 Skype 온라인(계획 2 또는 Enterprise 기반 계획) 이상을 Microsoft 365 또는 Office 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="ceae6-113">계획은 전화 접속 회의 기능을 허용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="ceae6-114">모임에서 전화 접속 기능이 필요한 경우 오디오 회의 및 전화 시스템 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-114">If you need dial-in capabilities from a meeting, you will need an Audio Conferencing and Phone System license.</span></span>  <span data-ttu-id="ceae6-115">모임에서 전화 접속 기능이 필요한 경우 오디오 회의 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-115">If you need dial-out capabilities from a meeting, you will need an Audio Conferencing license.</span></span>

- <span data-ttu-id="ceae6-116">테넌트 사용자에게 사서함이 Exchange 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="ceae6-117">Microsoft Teams 룸 계정에는 최소 비즈니스용 Skype(계획 2) 라이선스가 필요하지만 라이선스가 Exchange Online 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-117">Your Microsoft Teams Rooms account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="ceae6-118">자세한 [Microsoft Teams 룸 라이선스를](rooms-licensing.md) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-118">See [Microsoft Teams Rooms licenses](rooms-licensing.md) for details.</span></span>

<span data-ttu-id="ceae6-119">온라인 요금제에 대한 비즈니스용 Skype 자세한 내용은 온라인 비즈니스용 Skype [설명 을 참조하세요.](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)</span><span class="sxs-lookup"><span data-stu-id="ceae6-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="ceae6-120">디바이스 계정 추가</span><span class="sxs-lookup"><span data-stu-id="ceae6-120">Add a device account</span></span>

1. <span data-ttu-id="ceae6-121">커넥트 PowerShell을 Exchange Online 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="ceae6-122">지침은 [PowerShell을 커넥트 Exchange Online 참조하세요.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="ceae6-122">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="ceae6-123">PowerShell에서 새 Exchange Online 사서함을 만들거나 기존 방 사서함을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="ceae6-124">기본적으로 룸 사서함에는 연결된 계정이 없습니다. 따라서 Room Systems v2를 사용하여 인증할 수 있는 방 사서함을 만들거나 수정할 때 계정을 추가해야 Skype 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="ceae6-125">새 룸 사서함을 만들 경우 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="ceae6-126">이 예제에서는 다음 설정을 사용하여 새 룸 사서함을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="ceae6-127">이름: Rigel-01</span><span class="sxs-lookup"><span data-stu-id="ceae6-127">Name: Rigel-01</span></span>

     - <span data-ttu-id="ceae6-128">별칭: Rigel1</span><span class="sxs-lookup"><span data-stu-id="ceae6-128">Alias: Rigel1</span></span>

     - <span data-ttu-id="ceae6-129">계정: Rigel1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="ceae6-129">Account: Rigel1@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="ceae6-130">계정 암호: P@$$W 0rd5959</span><span class="sxs-lookup"><span data-stu-id="ceae6-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="ceae6-131">기존 룸 사서함을 수정하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="ceae6-132">이 예제에서는 별칭 값이 Rigel2인 기존 룸 사서함에 대한 계정을 사용할 수 있으며 암호를 9898P@$$W 0rd로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-132">This example enables the account for the existing room mailbox that has the alias value Rigel2, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="ceae6-133">기존 별칭 값으로 Rigel2@contoso.onmicrosoft.com 계정이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-133">Note that the account will be Rigel2@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="ceae6-134">자세한 구문 및 매개 변수 정보는 [New-사서함](/powershell/module/exchange/mailboxes/new-mailbox) 및 [Set-사서함 을 참조하세요.](/powershell/module/exchange/mailboxes/set-mailbox)</span><span class="sxs-lookup"><span data-stu-id="ceae6-134">For detailed syntax and parameter information, see [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).</span></span>

3. <span data-ttu-id="ceae6-135">PowerShell의 Exchange Online 회의실 사서함에서 다음 설정을 구성하여 모임 환경을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="ceae6-136">AutomateProcessing: AutoAccept(모임 이끌이는 사용자 개입 없이 직접 회의실 예약 결정을 수신합니다. 무료 = 수락, 사용 중 = 거부).)</span><span class="sxs-lookup"><span data-stu-id="ceae6-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="ceae6-137">AddOrganizerToSubject: $false(모임 이끌이가 모임 요청의 제목에 추가되지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="ceae6-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="ceae6-138">DeleteComments: $false(들어오는 모임 요청의 메시지 본문에 텍스트를 보관합니다.)</span><span class="sxs-lookup"><span data-stu-id="ceae6-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="ceae6-139">DeleteSubject: $false(들어오는 모임 요청의 제목 유지)입니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="ceae6-140">RemovePrivateProperty: $false(원래 모임 요청에서 모임 이끌이가 보낸 개인 플래그가 지정된 상태로 유지되도록 합니다.)</span><span class="sxs-lookup"><span data-stu-id="ceae6-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="ceae6-141">AddAdditionalResponse: $true(AdditionalResponse 매개 변수에서 지정한 텍스트가 모임 요청에 추가됩니다.)</span><span class="sxs-lookup"><span data-stu-id="ceae6-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="ceae6-142">AdditionalResponse: "이 방은 Skype 모임 방입니다!"</span><span class="sxs-lookup"><span data-stu-id="ceae6-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="ceae6-143">(모임 요청에 추가할 추가 텍스트입니다.)</span><span class="sxs-lookup"><span data-stu-id="ceae6-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="ceae6-144">이 예제에서는 Rigel-01이라는 룸 사서함에서 이러한 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-144">This example configures these settings on the room mailbox named Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="ceae6-145">자세한 구문 및 매개 변수 정보는 [Set-CalendarProcessing 을 참조하세요.](/powershell/module/exchange/mailboxes/set-calendarprocessing)</span><span class="sxs-lookup"><span data-stu-id="ceae6-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="ceae6-146">커넥트 PowerShell cmdlet을 실행하여 Active Directory 설정을 만들기 위해 MS `Connect-MsolService -Credential $cred` Online PowerShell으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-146">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` PowerShell cmdlet.</span></span> <span data-ttu-id="ceae6-147">Active Directory에 대한 자세한 내용은 [Azure ActiveDirectory(MSOnline) 1.0 을 참조하세요.](/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="ceae6-147">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

   > [!NOTE]
   > <span data-ttu-id="ceae6-148">[Azure Active Directory PowerShell 2.0은](/powershell/azure/active-directory/overview?view=azureadps-2.0) 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-148">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span>

5. <span data-ttu-id="ceae6-149">암호가 만료되지 않는 경우 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="ceae6-149">If you do not want the password to expire, use the following syntax:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   <span data-ttu-id="ceae6-150">이 예제에서는 계정 암호가 만료되지 Rigel1@contoso.onmicrosoft.com 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-150">This example sets the password for the account Rigel1@contoso.onmicrosoft.com to never expire.</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   <span data-ttu-id="ceae6-151">다음 명령을 실행하여 계정에 대한 전화 번호를 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-151">You can also set a phone number for the account by running the following command:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

    > [!NOTE]
    > <span data-ttu-id="ceae6-152">암호가 만료되지 않은 것으로 설정되어 있지 않은 경우 계정이 만료 기간에 도달하면 더 이상 디바이스에 로그인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-152">If the password is not set to Never Expire, the account will no longer sign in on the device when the account reaches the expiry period.</span></span> <span data-ttu-id="ceae6-153">그러면 계정에 대한 암호를 변경하고 MTR 디바이스에서 로컬로 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-153">The password will then need to be changed for the account and also updated locally on the MTR device.</span></span>

6. <span data-ttu-id="ceae6-154">디바이스 계정에 유효한 Microsoft 365 Office 365 라이선스가 있어야 Exchange Microsoft Teams 비즈니스용 Skype 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-154">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams or Skype for Business will not work.</span></span> <span data-ttu-id="ceae6-155">라이선스가 있는 경우 디바이스 계정에 사용 위치를 할당해야 합니다. 그러면 계정에 사용할 수 있는 라이선스 SKUS가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-155">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="ceae6-156">사용할 수 있습니다. `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="ceae6-156">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="ceae6-157">다음을 수행하여 조직 또는 조직에서 Microsoft 365 사용할 Office 365 목록을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-157">to retrieve a list of available SKUs for your Microsoft 365 or Office 365 organization as follows:</span></span>

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   <span data-ttu-id="ceae6-158">다음으로, `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="ceae6-158">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!--Set-AzureADUserLicense --> <span data-ttu-id="ceae6-159">cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-159">cmdlet.</span></span> <span data-ttu-id="ceae6-160">이 예제에서는 계정에 미팅룸 라이선스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-160">This example adds the Meeting Room license to the account:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   <span data-ttu-id="ceae6-161">자세한 지침은 PowerShell을 통해 사용자 계정에 라이선스 [할당을 Office 365 참조하세요.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="ceae6-161">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

   <span data-ttu-id="ceae6-162">이 계정에 전화 시스템 기능을 추가할 수도 있지만 먼저 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-162">You can also add Phone System capabilities to this account, but you have to configure it first.</span></span> <span data-ttu-id="ceae6-163">자세한 [내용은 전화 시스템?를](../what-is-phone-system-in-office-365.md) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ceae6-163">See [What is Phone System?](../what-is-phone-system-in-office-365.md) for more details.</span></span> <span data-ttu-id="ceae6-164">이 예제에서는 PSTN 국내 및 국제 통화 계획을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-164">This example adds the PSTN Domestic and International Calling Plan:</span></span>

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "Contoso:MCOPSTN2"
   ```

    > [!NOTE]
    > <span data-ttu-id="ceae6-165">모임에 Teams 룸 모임에 Microsoft Teams 구성하는 경우 다음 단계를 진행하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-165">If you are configuring Teams Rooms to only natively join Microsoft Teams meetings, you should not proceed with the following step.</span></span> <span data-ttu-id="ceae6-166">다음은 프레미스에 대한 지원도 활성화하는 비즈니스용 Skype 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-166">The following is only required if you will also be enabling support for Skype for Business on-premises.</span></span>

7. <span data-ttu-id="ceae6-167">프레미스에서 디바이스 계정을 비즈니스용 Skype 환경이 요구 사항에 정의된 요구 사항을 [충족해야 Microsoft Teams 룸 합니다.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="ceae6-167">To enable the device account with Skype for Business on-premises, be sure your environment meets the requirements defined in [Microsoft Teams Rooms requirements](requirements.md).</span></span>

   <span data-ttu-id="ceae6-168">다음과 같이 [원격](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) Windows PowerShell 세션을 [시작합니다(온라인 PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)구성 요소에 비즈니스용 Skype 있는지 확인).</span><span class="sxs-lookup"><span data-stu-id="ceae6-168">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

   > [!NOTE]
   > <span data-ttu-id="ceae6-169">비즈니스용 Skype 온라인 커넥터는 현재 최신 PowerShell Teams 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-169">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
   >
   > <span data-ttu-id="ceae6-170">최신 [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 Teams 사용하는 경우 온라인 커넥터를 비즈니스용 Skype 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-170">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

   <span data-ttu-id="ceae6-171">이 예제와 같이 설정되는 새 사용자 계정에서 RegistrarPool 정보를 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-171">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

   ``` Powershell
    Get-CsOnlineUser -Identity "Rigel1@contoso.onmicrosoft.com" | Select -Expand RegistrarPool
   ```

   <span data-ttu-id="ceae6-172">다음으로, 다음 cmdlet을 Microsoft Teams 룸 비즈니스용 Skype 서버 계정을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-172">Next, enable your Microsoft Teams Rooms account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity "Rigel1@contoso.onmicrosoft.com" -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   > [!NOTE]
   > <span data-ttu-id="ceae6-173">테넌트의 기존 사용자 계정과 동일한 등록 기관 풀에서 새 사용자 계정을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-173">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="ceae6-174">위의 명령은 이 상황으로 인해 계정 설정의 오류를 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-174">The command above will prevent errors in account setup due to this situation.</span></span>

## <a name="validate"></a><span data-ttu-id="ceae6-175">유효성 검사</span><span class="sxs-lookup"><span data-stu-id="ceae6-175">Validate</span></span>

<span data-ttu-id="ceae6-176">유효성 검사의 경우 모든 클라이언트를 사용하여 비즈니스용 Skype 계정에 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ceae6-176">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="ceae6-177">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ceae6-177">See also</span></span>

[<span data-ttu-id="ceae6-178">Microsoft Teams 룸</span><span class="sxs-lookup"><span data-stu-id="ceae6-178">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="ceae6-179">Microsoft Teams 룸 계획</span><span class="sxs-lookup"><span data-stu-id="ceae6-179">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="ceae6-180">Microsoft Teams 룸 배포</span><span class="sxs-lookup"><span data-stu-id="ceae6-180">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)

[<span data-ttu-id="ceae6-181">Microsoft Teams 룸 콘솔 구성</span><span class="sxs-lookup"><span data-stu-id="ceae6-181">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="ceae6-182">Microsoft Teams 룸 관리</span><span class="sxs-lookup"><span data-stu-id="ceae6-182">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)

[<span data-ttu-id="ceae6-183">Microsoft Teams 룸 라이선스</span><span class="sxs-lookup"><span data-stu-id="ceae6-183">Microsoft Teams Rooms Licensing</span></span>](rooms-licensing.md)
