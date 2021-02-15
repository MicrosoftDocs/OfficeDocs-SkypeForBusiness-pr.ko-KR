---
title: Microsoft 365 또는 Office 365를 통해 Microsoft Teams 회의실 배포
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
description: Teams 또는 비즈니스용 Skype와 Exchange가 모두 온라인인 Microsoft 365 또는 Office 365에서 Microsoft Teams 회의실을 배포하는 방법에 대한 자세한 내용은 이 항목을 참조하세요.
ms.openlocfilehash: 4ec54763379e4a13a69eb3e08019924708873faf
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196212"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a><span data-ttu-id="cb1e6-103">Microsoft 365 또는 Office 365를 통해 Microsoft Teams 회의실 배포</span><span class="sxs-lookup"><span data-stu-id="cb1e6-103">Deploy Microsoft Teams Rooms with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="cb1e6-104">Microsoft Teams 또는 비즈니스용 Skype 및 Exchange가 모두 온라인인 Microsoft 365 또는 Office 365에서 Microsoft Teams 회의실을 배포하는 방법에 대한 자세한 내용은 이 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, where Microsoft Teams or Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="cb1e6-105">사용자 계정을 설정하는 가장 쉬운 방법은 원격 계정을 사용하여 구성하는 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="cb1e6-106">Microsoft는 [ ](https://go.microsoft.com/fwlink/?linkid=870105)SkypeRoomProvisioningScript.ps1계정을 만들거나 호환되는 Microsoft Teams Rooms 사용자 계정으로 전환할 수 있도록 기존 리소스 계정의 유효성을 검사하는 데 도움이 되는 스크립트인 스크립트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="cb1e6-107">원하는 경우 아래 단계에 따라 Microsoft Teams 회의실 장치에서 사용할 계정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-107">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="cb1e6-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cb1e6-108">Requirements</span></span>

<span data-ttu-id="cb1e6-109">Microsoft 365 또는 Office 365에서 Microsoft Teams 회의실을 배포하기 전에 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-109">Before you deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="cb1e6-110">자세한 내용은 Microsoft Teams 회의실 요구 [사항을 참조하세요.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="cb1e6-110">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>

<span data-ttu-id="cb1e6-111">비즈니스용 Skype를 사용하려면 다음이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="cb1e6-112">Microsoft 365 또는 Office 365 요금제의 비즈니스용 Skype Online(계획 2 또는 엔터프라이즈 기반 요금제) 이상</span><span class="sxs-lookup"><span data-stu-id="cb1e6-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="cb1e6-113">요금제는 전화 접속 회의 기능을 허용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="cb1e6-114">모임에서 전화 접속 기능이 필요한 경우 오디오 회의 및 전화 시스템 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-114">If you need dial-in capabilities from a meeting, you will need an Audio Conferencing and Phone System license.</span></span>  <span data-ttu-id="cb1e6-115">모임에서 전화 접속 기능이 필요한 경우 오디오 회의 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-115">If you need dial-out capabilities from a meeting, you will need an Audio Conferencing license.</span></span>

- <span data-ttu-id="cb1e6-116">테넌트 사용자에게 Exchange 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="cb1e6-117">Microsoft Teams 회의실 계정에는 최소한 비즈니스용 Skype Online(계획 2) 라이선스가 필요하지만 Exchange Online 라이선스는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-117">Your Microsoft Teams Rooms account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="cb1e6-118">자세한 [내용은 Microsoft Teams 회의실 라이선스를](rooms-licensing.md) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-118">See [Microsoft Teams Rooms licenses](rooms-licensing.md) for details.</span></span>

<span data-ttu-id="cb1e6-119">비즈니스용 Skype Online 요금제에 대한 자세한 내용은 비즈니스용 [Skype Online 서비스 설명을 참조하세요.](https://technet.microsoft.com/library/jj822172.aspx)</span><span class="sxs-lookup"><span data-stu-id="cb1e6-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="cb1e6-120">디바이스 계정 추가</span><span class="sxs-lookup"><span data-stu-id="cb1e6-120">Add a device account</span></span>

1. <span data-ttu-id="cb1e6-121">Exchange Online PowerShell에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="cb1e6-122">자세한 내용은 [Exchange Online PowerShell에 연결합니다.](https://go.microsoft.com/fwlink/p/?linkid=396554)</span><span class="sxs-lookup"><span data-stu-id="cb1e6-122">For instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

2. <span data-ttu-id="cb1e6-123">Exchange Online PowerShell에서 새 방 사서함을 만들거나 기존 방 사서함을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="cb1e6-124">기본적으로 채팅방 사서함에는 연결된 계정이 없습니다. 따라서 Skype Room Systems v2로 인증할 수 있는 채팅방 사서함을 만들거나 수정할 때 계정을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="cb1e6-125">새 방 사서함을 만들 경우 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="cb1e6-126">이 예제에서는 다음 설정을 사용하여 새 방 사서함을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="cb1e6-127">이름: Rigel-01</span><span class="sxs-lookup"><span data-stu-id="cb1e6-127">Name: Rigel-01</span></span>

     - <span data-ttu-id="cb1e6-128">별칭: Rigel1</span><span class="sxs-lookup"><span data-stu-id="cb1e6-128">Alias: Rigel1</span></span>

     - <span data-ttu-id="cb1e6-129">계정: Rigel1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="cb1e6-129">Account: Rigel1@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="cb1e6-130">계정 암호: P@$$W 0rd5959</span><span class="sxs-lookup"><span data-stu-id="cb1e6-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="cb1e6-131">기존 방 사서함을 수정하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="cb1e6-132">이 예제에서는 별칭 값이 Rigel2인 기존 방 사서함의 계정을 사용할 수 있으며 암호를 9898P@$$W 0rd로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-132">This example enables the account for the existing room mailbox that has the alias value Rigel2, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="cb1e6-133">기존 별칭 값으로 Rigel2@contoso.onmicrosoft.com 계정이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-133">Note that the account will be Rigel2@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="cb1e6-134">자세한 구문 및 매개 변수 정보는 [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) 및 [Set-Mailbox을 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)</span><span class="sxs-lookup"><span data-stu-id="cb1e6-134">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>

3. <span data-ttu-id="cb1e6-135">Exchange Online PowerShell에서 회의실 사서함에서 다음 설정을 구성하여 모임 환경을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="cb1e6-136">AutomateProcessing: AutoAccept(모임 이끌이는 사용자 개입 없이 바로 회의실 예약 결정을 수신합니다. 무료 = 수락, 사용 중 = 거절).</span><span class="sxs-lookup"><span data-stu-id="cb1e6-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="cb1e6-137">AddOrganizerToSubject: $false(모임 이끌이는 모임 요청의 제목에 추가되지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="cb1e6-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="cb1e6-138">DeleteComments: $false(들어오는 모임 요청의 메시지 본문에 텍스트를 보관합니다.)</span><span class="sxs-lookup"><span data-stu-id="cb1e6-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="cb1e6-139">DeleteSubject: $false(들어오는 모임 요청의 제목 유지)</span><span class="sxs-lookup"><span data-stu-id="cb1e6-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="cb1e6-140">RemovePrivateProperty: $false(원래 모임 요청에서 모임 이끌이가 보낸 개인 플래그가 지정된 상태로 유지되도록 합니다.)</span><span class="sxs-lookup"><span data-stu-id="cb1e6-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="cb1e6-141">AddAdditionalResponse: $true(AdditionalResponse 매개 변수로 지정된 텍스트가 모임 요청에 추가됩니다.)</span><span class="sxs-lookup"><span data-stu-id="cb1e6-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="cb1e6-142">AdditionalResponse: "Skype 회의실입니다!"</span><span class="sxs-lookup"><span data-stu-id="cb1e6-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="cb1e6-143">(모임 요청에 추가할 추가 텍스트입니다.)</span><span class="sxs-lookup"><span data-stu-id="cb1e6-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="cb1e6-144">이 예제에서는 Rigel-01이라는 방 사서함에서 이러한 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-144">This example configures these settings on the room mailbox named Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="cb1e6-145">자세한 구문 및 매개 변수 정보는 [Set-CalendarProcessing을 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)</span><span class="sxs-lookup"><span data-stu-id="cb1e6-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="cb1e6-146">MS Online PowerShell에 연결하여 `Connect-MsolService -Credential $cred` PowerShell cmdlet을 실행하여 Active Directory 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-146">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` PowerShell cmdlet.</span></span> <span data-ttu-id="cb1e6-147">Active Directory에 대한 자세한 내용은 [Azure ActiveDirectory(MSOnline) 1.0을 참조하세요.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="cb1e6-147">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

   > [!NOTE]
   > <span data-ttu-id="cb1e6-148">[Azure Active Directory PowerShell 2.0은](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-148">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span>

5. <span data-ttu-id="cb1e6-149">암호가 만료되지 못하게 하려는 경우 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-149">If you do not want the password to expire, use the following syntax:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   <span data-ttu-id="cb1e6-150">이 예제에서는 계정 암호가 만료되지 Rigel1@contoso.onmicrosoft.com 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-150">This example sets the password for the account Rigel1@contoso.onmicrosoft.com to never expire.</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   <span data-ttu-id="cb1e6-151">다음 명령을 실행하여 계정에 대한 전화 번호를 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-151">You can also set a phone number for the account by running the following command:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

> [!NOTE]
> <span data-ttu-id="cb1e6-152">암호가 만료되지 않는 것으로 설정되지 않은 경우 계정이 만료 기간에 도달하면 계정에 더 이상 로그인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-152">If the password is not set to Never Expire, the account will no longer sign in on the device when the account reaches the expiry period.</span></span> <span data-ttu-id="cb1e6-153">그런 다음 계정에 대한 암호를 변경하고 MTR 디바이스에서 로컬로 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-153">The password will then need to be changed for the account and also updated locally on the MTR device.</span></span>

6. <span data-ttu-id="cb1e6-154">장치 계정에 유효한 Microsoft 365 또는 Office 365 라이선스가 있어야 합니다. 또는 Exchange 및 Microsoft Teams 또는 비즈니스용 Skype가 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-154">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams or Skype for Business will not work.</span></span> <span data-ttu-id="cb1e6-155">라이선스가 있는 경우 사용 위치를 디바이스 계정에 할당해야 합니다. 그러면 계정에 사용할 수 있는 라이선스 SKUS가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-155">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="cb1e6-156">다음을 사용할 수 있습니다. `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="cb1e6-156">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="cb1e6-157">다음과 같이 Microsoft 365 또는 Office 365 조직에 사용 가능한 SKUS 목록을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-157">to retrieve a list of available SKUs for your Microsoft 365 or Office 365 organization as follows:</span></span>

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   <span data-ttu-id="cb1e6-158">다음으로, `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="cb1e6-158">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!--Set-AzureADUserLicense --> <span data-ttu-id="cb1e6-159">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-159">cmdlet.</span></span> <span data-ttu-id="cb1e6-160">이 예제에서는 계정에 회의실 라이선스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-160">This example adds the Meeting Room license to the account:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   <span data-ttu-id="cb1e6-161">자세한 지침은 [Office 365 PowerShell을](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)통해 사용자 계정에 라이선스 할당을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-161">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

   <span data-ttu-id="cb1e6-162">이 계정에 전화 시스템 기능을 추가할 수도 있지만 먼저 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-162">You can also add Phone System capabilities to this account, but you have to configure it first.</span></span> <span data-ttu-id="cb1e6-163">자세한 [내용은 전화 시스템이란?](../what-is-phone-system-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="cb1e6-163">See [What is Phone System?](../what-is-phone-system-in-office-365.md) for more details.</span></span> <span data-ttu-id="cb1e6-164">이 예제에서는 PSTN 국내 및 국제 통화 계획을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-164">This example adds the PSTN Domestic and International Calling Plan:</span></span>

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "Contoso:MCOPSTN2"
   ```

7. <span data-ttu-id="cb1e6-165">다음으로, 비즈니스용 Skype에서 장치 계정을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-165">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="cb1e6-166">환경이 Microsoft Teams 회의실 요구 사항에 정의된 요구 [사항을 충족하는지 확인합니다.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="cb1e6-166">Be sure your environment meets the requirements defined in [Microsoft Teams Rooms requirements](requirements.md).</span></span>

   <span data-ttu-id="cb1e6-167">다음과 같이 [원격](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) Windows PowerShell 세션을 시작하세요(비즈니스용 [Skype Online PowerShell 구성 요소를 설치해야 합니다).](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)</span><span class="sxs-lookup"><span data-stu-id="cb1e6-167">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

> [!NOTE]
> <span data-ttu-id="cb1e6-168">비즈니스용 Skype Online Connector는 현재 최신 Teams PowerShell 모듈의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-168">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="cb1e6-169">최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 릴리스를 사용하는 경우 비즈니스용 Skype Online Connector를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-169">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

   ``` Powershell
   Import-Module -Name MicrosoftTeams  
   $cssess = New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="cb1e6-170">이 예제와 같이 설치되는 새 사용자 계정에서 RegistrarPool 정보를 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-170">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

   ``` Powershell
    Get-CsOnlineUser -Identity "Rigel1@contoso.onmicrosoft.com" | Select -Expand RegistrarPool
   ```

   <span data-ttu-id="cb1e6-171">다음으로, 다음 cmdlet을 실행하여 비즈니스용 Skype 서버용 Microsoft Teams 회의실 계정을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-171">Next, enable your Microsoft Teams Rooms account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity "Rigel1@contoso.onmicrosoft.com" -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   > [!NOTE]
   > <span data-ttu-id="cb1e6-172">테넌트의 기존 사용자 계정과 동일한 등록 기관 풀에 새 사용자 계정을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-172">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="cb1e6-173">위의 명령은 이 상황으로 인해 계정 설정 오류를 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-173">The command above will prevent errors in account setup due to this situation.</span></span>

## <a name="validate"></a><span data-ttu-id="cb1e6-174">유효성 검사</span><span class="sxs-lookup"><span data-stu-id="cb1e6-174">Validate</span></span>

<span data-ttu-id="cb1e6-175">유효성 검사를 위해 비즈니스용 Skype 클라이언트를 사용하여 만든 계정에 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-175">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb1e6-176">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb1e6-176">See also</span></span>

[<span data-ttu-id="cb1e6-177">Microsoft Teams 회의실에 대한 계정 구성</span><span class="sxs-lookup"><span data-stu-id="cb1e6-177">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="cb1e6-178">Microsoft Teams 룸 계획</span><span class="sxs-lookup"><span data-stu-id="cb1e6-178">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="cb1e6-179">Microsoft Teams 룸 배포</span><span class="sxs-lookup"><span data-stu-id="cb1e6-179">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)

[<span data-ttu-id="cb1e6-180">Microsoft Teams 룸 콘솔 구성</span><span class="sxs-lookup"><span data-stu-id="cb1e6-180">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="cb1e6-181">Microsoft Teams 룸 관리</span><span class="sxs-lookup"><span data-stu-id="cb1e6-181">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)

[<span data-ttu-id="cb1e6-182">Microsoft Teams 회의실 라이선스</span><span class="sxs-lookup"><span data-stu-id="cb1e6-182">Microsoft Teams Rooms Licensing</span></span>](rooms-licensing.md)
