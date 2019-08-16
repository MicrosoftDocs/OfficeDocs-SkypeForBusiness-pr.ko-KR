---
title: Office 365를 사용 하 여 Microsoft 팀 대화방 배포
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Office 365를 사용 하 여 Microsoft 팀 회의실을 배포 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.
ms.openlocfilehash: 1d0bd8270671ba1a666d07fd2e7826704c309f01
ms.sourcegitcommit: 1401ee484a2bc8e72d96649b0571bb59198f9dab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "36427740"
---
# <a name="deploy-microsoft-teams-rooms-with-office-365"></a><span data-ttu-id="f791d-103">Office 365를 사용 하 여 Microsoft 팀 대화방 배포</span><span class="sxs-lookup"><span data-stu-id="f791d-103">Deploy Microsoft Teams Rooms with Office 365</span></span>

<span data-ttu-id="f791d-104">Microsoft 팀 또는 비즈니스용 Skype와 Exchange가 모두 온라인 상태에 있는 Microsoft 팀 대화방을 Office 365와 함께 배포 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f791d-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Office 365, where Microsoft Teams or Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="f791d-105">사용자 계정을 설정 하는 가장 쉬운 방법은 원격 Windows PowerShell을 사용 하 여 구성 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="f791d-106">Microsoft는 새 사용자 계정을 만들거나, 호환 되는 Microsoft 팀 대화방 사용자 계정으로 전환 하는 데 도움을 주는 기존 리소스 계정이 있는지 확인 하는 데 도움이 되는 [SkypeRoomProvisioningScript. ps1을 제공 합니다.](https://go.microsoft.com/fwlink/?linkid=870105)</span><span class="sxs-lookup"><span data-stu-id="f791d-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="f791d-107">원하는 경우 아래 단계에 따라 Microsoft 팀 대화방 장치에서 사용할 계정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-107">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="f791d-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f791d-108">Requirements</span></span>

<span data-ttu-id="f791d-109">Microsoft 팀 회의실을 Office 365에 배포 하기 전에 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-109">Before you deploy Microsoft Teams Rooms with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="f791d-110">자세한 내용은 [Microsoft 팀 공간 요구 사항을](requirements.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f791d-110">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>

<span data-ttu-id="f791d-111">비즈니스용 Skype를 사용 하도록 설정 하려면 다음이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="f791d-112">Office 365 요금제의 비즈니스용 Skype Online (계획 2 또는 엔터프라이즈 기반 계획) 이상</span><span class="sxs-lookup"><span data-stu-id="f791d-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Office 365 plan.</span></span> <span data-ttu-id="f791d-113">요금제는 전화 접속 회의 기능을 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="f791d-114">모임에서 전화 접속 기능이 필요한 경우에는 오디오 회의 및 전화 시스템 라이선스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-114">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="f791d-115">모임에서 전화 접속 기능이 필요한 경우 국내 또는 국내 및 국제 통화 요금제가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-115">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span>

- <span data-ttu-id="f791d-116">테 넌 트 사용자에 게 Exchange 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="f791d-117">Microsoft 팀 대화방 계정에는 최소한 비즈니스용 Skype Online (요금제 2) 라이선스가 필요 하지만 Exchange Online 라이선스는 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-117">Your Microsoft Teams Rooms account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="f791d-118">자세한 내용은 [Microsoft 팀 대화방 라이선스](skype-room-systems-v2.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f791d-118">See [Microsoft Teams Rooms licenses](skype-room-systems-v2.md) for details.</span></span>

<span data-ttu-id="f791d-119">비즈니스용 Skype Online 요금제에 대 한 자세한 내용은 [비즈니스용 Skype Online 서비스 설명을](https://technet.microsoft.com/library/jj822172.aspx)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f791d-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="f791d-120">디바이스 계정 추가</span><span class="sxs-lookup"><span data-stu-id="f791d-120">Add a device account</span></span>

1. <span data-ttu-id="f791d-121">Exchange Online PowerShell에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="f791d-122">지침은 [Exchange Online PowerShell에 연결](https://go.microsoft.com/fwlink/p/?linkid=396554)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f791d-122">For instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

2. <span data-ttu-id="f791d-123">Exchange Online PowerShell에서 새 회의실 사서함을 만들거나 기존 회의실 사서함을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="f791d-124">기본적으로 회의실 사서함에는 연결 된 계정이 없으므로 Skype 대화방 시스템을 인증 하는 데 사용할 수 있는 채팅방 사서함을 만들거나 수정할 때 계정을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="f791d-125">새 회의실 사서함을 만들려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="f791d-126">이 예제에서는 다음 설정을 사용 하 여 새 채팅방 사서함을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="f791d-127">이름: Project-Rigel-01</span><span class="sxs-lookup"><span data-stu-id="f791d-127">Name: Project-Rigel-01</span></span>

     - <span data-ttu-id="f791d-128">별칭: ProjectRigel01</span><span class="sxs-lookup"><span data-stu-id="f791d-128">Alias: ProjectRigel01</span></span>

     - <span data-ttu-id="f791d-129">계정: ProjectRigel01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="f791d-129">Account: ProjectRigel01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="f791d-130">계정 암호: P @ $ $W 0rd5959</span><span class="sxs-lookup"><span data-stu-id="f791d-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Project-Rigel-01" -Alias ProjectRigel01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID ProjectRigel01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="f791d-131">기존 회의실 사서함을 수정 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="f791d-132">이 예제에서는 별칭 값 ProjectRigel02를 가진 기존 채팅방 사서함에 대 한 계정을 사용 하도록 설정 하 고 암호를 9898P @ $ $W 0rd으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-132">This example enables the account for the existing room mailbox that has the alias value ProjectRigel02, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="f791d-133">기존 별칭 값 때문에 계정이 ProjectRigel02@contoso.onmicrosoft.com 것을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="f791d-133">Note that the account will be ProjectRigel02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity ProjectRigel02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="f791d-134">자세한 구문 및 매개 변수 정보는 [새 사서함](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) 및 [설정 사서함](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f791d-134">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="f791d-135">Exchange Online PowerShell에서 회의실 사서함에 다음 설정을 구성 하 여 모임 환경을 개선 합니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="f791d-136">AutomateProcessing: AutoAccept (모임 이끌이는 사용자 간섭 없이 직접 회의실 예약 결정을 받습니다: 무료 = 수락; 사용 중 = 거절).</span><span class="sxs-lookup"><span data-stu-id="f791d-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="f791d-137">AddOrganizerToSubject: $false (모임 이끌이는 모임 요청의 제목에 추가 되지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="f791d-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="f791d-138">Deletecomdea: $false (받는 모임 요청의 메시지 본문에 있는 텍스트는 유지 합니다.)</span><span class="sxs-lookup"><span data-stu-id="f791d-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="f791d-139">DeleteSubject: $false (들어오는 모임 요청의 주제를 보관 합니다.)</span><span class="sxs-lookup"><span data-stu-id="f791d-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="f791d-140">RemovePrivateProperty: $false (원래 모임 이끌이가 보낸 개인 플래그가 지정 된 대로 유지 되도록 합니다.)</span><span class="sxs-lookup"><span data-stu-id="f791d-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="f791d-141">AddAdditionalResponse: $true (AdditionalResponse 매개 변수에서 지정한 텍스트가 모임 요청에 추가 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="f791d-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="f791d-142">AdditionalResponse: "Skype 회의실입니다!"</span><span class="sxs-lookup"><span data-stu-id="f791d-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="f791d-143">(모임 요청에 추가 하는 추가 텍스트입니다.)</span><span class="sxs-lookup"><span data-stu-id="f791d-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="f791d-144">이 예제에서는 Rigel-01 이라는 대화방 사서함에서 이러한 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-144">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="f791d-145">자세한 구문 및 매개 변수 정보는 [설정-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f791d-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="f791d-146">`Connect-MsolService -Credential $cred` Powershell cmdlet을 실행 하 여 Active Directory 설정을 만들기 위해 MS Online PowerShell에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-146">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="f791d-147">Active Directory에 대 한 자세한 내용은 [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f791d-147">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="f791d-148">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) 는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-148">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

5. <span data-ttu-id="f791d-149">암호가 만료 되지 않도록 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-149">If you do not want the password to expire, use the following syntax:</span></span>

    ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
    ```
<!--
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   <span data-ttu-id="f791d-150">이 예제에서는 계정 ProjectRigel01@contoso.onmicrosoft.com의 암호가 만료 되지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-150">This example sets the password for the account ProjectRigel01@contoso.onmicrosoft.com to never expire.</span></span>

  ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName ProjectRigel01@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   <span data-ttu-id="f791d-151">다음 명령을 실행 하 여 계정의 전화 번호를 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-151">You can also set a phone number for the account by running the following command:</span></span>

  ``` PowerShell
    Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. <span data-ttu-id="f791d-152">장치 계정에 유효한 Office 365 라이선스가 있어야 하며, Exchange 및 Microsoft 팀 또는 비즈니스용 Skype가 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-152">The device account needs to have a valid Office 365 license, or Exchange and Microsoft Teams or Skype for Business will not work.</span></span> <span data-ttu-id="f791d-153">라이선스가 있는 경우 사용 위치를 디바이스 계정에 할당 해야 하며,이는 계정에 사용할 수 있는 라이선스 Sku를 결정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-153">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="f791d-154">사용할 수 있는`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="f791d-154">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="f791d-155">다음과 같이 Office 365 테 넌 트에 대해 사용 가능한 Sku 목록을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-155">to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>

  ``` Powershell
  Get-MsolAccountSku
  ```
<!--
   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   <span data-ttu-id="f791d-156">다음으로, 다음을 사용 하 여 라이선스를 추가할 수 있습니다.`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="f791d-156">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!--Set-AzureADUserLicense --> <span data-ttu-id="f791d-157">은.</span><span class="sxs-lookup"><span data-stu-id="f791d-157">cmdlet.</span></span> <span data-ttu-id="f791d-158">이 경우 $strLicense는 사용자에 게 표시 되는 SKU 코드입니다 (예: contoso: STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="f791d-158">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

  ``` PowerShell
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
  ``` 
<!-- 
   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```   -->

   <span data-ttu-id="f791d-159">자세한 지침은 [Office 365 PowerShell을 사용 하 여 사용자 계정에 라이선스 할당](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f791d-159">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

7. <span data-ttu-id="f791d-160">다음으로 비즈니스용 Skype를 사용 하 여 디바이스 계정을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-160">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="f791d-161">환경이 [Microsoft 팀 회의실 요구 사항](requirements.md)에 정의 된 요구 사항을 충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-161">Be sure your environment meets the requirements defined in [Microsoft Teams Rooms requirements](requirements.md).</span></span>

   <span data-ttu-id="f791d-162">다음과 같이 원격 [Windows PowerShell 세션](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) 을 시작 합니다 (비즈니스용 [Skype Online PowerShell 구성 요소를 설치](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)해야 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="f791d-162">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="f791d-163">다음 cmdlet을 실행 하 여 비즈니스용 Skype Server에 대해 Microsoft 팀 대화방 계정을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-163">Next, enable your Microsoft Teams Rooms account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   <span data-ttu-id="f791d-164">이 예제에 표시 된 대로 새 사용자 계정을 설정 하 여 RegistrarPool 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-164">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

    ``` Powershell
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > <span data-ttu-id="f791d-165">새 사용자 계정이 테 넌 트에서 기존 사용자 계정과 동일한 등록자 풀에 만들어지지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-165">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="f791d-166">위의 명령은이 문제 때문에 계정 설정 오류를 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-166">The command above will prevent errors in account setup due to this situation.</span></span>

<span data-ttu-id="f791d-167">Microsoft 팀 또는 비즈니스용 Skype Online에서 Microsoft 팀 회의실 계정을 사용할 수 있도록 앞의 단계를 완료 한 후에 Microsoft 팀 대화방 장치에 라이선스를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-167">After you've completed the preceding steps to enable your Microsoft Teams Rooms account in Microsoft Teams or Skype for Business Online, you need to assign a license to Microsoft Teams Rooms device.</span></span> <span data-ttu-id="f791d-168">Office 365 관리 포털을 사용 하 여 비즈니스용 Skype Online (계획 2) 또는 비즈니스용 Skype Online (계획 3) 라이선스를 장치에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-168">Using the Office 365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

### <a name="assign-a-license-to-your-account"></a><span data-ttu-id="f791d-169">계정에 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="f791d-169">Assign a license to your account</span></span>

1. <span data-ttu-id="f791d-170">테 넌 트 관리자로 로그인 하 고, Office 365 관리 포털을 열고, 관리 앱을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-170">Login as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>

2. <span data-ttu-id="f791d-171">**사용자 및 그룹** 을 클릭 한 다음 **사용자 추가, 암호 다시 설정**등을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-171">Click **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>

3. <span data-ttu-id="f791d-172">Microsoft 팀 대화방 계정을 선택한 다음 펜 아이콘을 클릭 하거나 탭 하 여 편집을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-172">Select the Microsoft Teams Rooms account, and then click or tap the pen icon, which means edit.</span></span>

4. <span data-ttu-id="f791d-173">**라이선스** 옵션을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-173">Click on the **Licenses** option.</span></span>

5. <span data-ttu-id="f791d-174">라이선스 **할당** 섹션에서 사용권 및 Enterprise Voice 필요 조건에 따라 비즈니스용 skype Online (계획 2) 또는 비즈니스용 skype Online (계획 3)을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-174">In the **Assign licenses** section, you need to select Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3), depending on your licensing and what you've decided in terms of needing Enterprise Voice.</span></span> <span data-ttu-id="f791d-175">Microsoft 팀 방에 클라우드 PBX를 사용 하려면 요금제 3 라이선스를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-175">You'll have to use a Plan 3 license if you want to use Cloud PBX on Microsoft Teams Rooms.</span></span> <span data-ttu-id="f791d-176">최소한 음성 연결에는 CloudPBX가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-176">Minimally you will need CloudPBX for voice connectivity.</span></span> <span data-ttu-id="f791d-177">그런 다음 PSTN 연결 방법을 기반으로 하이브리드 음성 또는 PSTN 통화를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-177">Then configure hybrid voice or PSTN calling based on the PSTN connectivity method.</span></span> <span data-ttu-id="f791d-178">자세한 내용은 [Microsoft 팀 공간 라이선스](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f791d-178">See [Microsoft Teams Rooms licenses](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) for more details.</span></span>

6. <span data-ttu-id="f791d-179">**저장** 을 클릭 하 여 작업을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-179">Click **Save** to complete the task.</span></span>

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="f791d-180">샘플: Exchange Online 및 비즈니스용 Skype Online의 채팅방 계정 설정</span><span class="sxs-lookup"><span data-stu-id="f791d-180">Sample: Room account setup in Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="f791d-181">Exchange Online PowerShell 명령:</span><span class="sxs-lookup"><span data-stu-id="f791d-181">Exchange Online PowerShell commands:</span></span>

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept-AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

<span data-ttu-id="f791d-182">Azure Active Directory PowerShell 명령:</span><span class="sxs-lookup"><span data-stu-id="f791d-182">Azure Active Directory PowerShell commands:</span></span>

``` PowerShell
Set-MsolUser -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```

<!-- 
``` PowerShell
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```  -->

<span data-ttu-id="f791d-183">비즈니스용 Skype PowerShell 명령:</span><span class="sxs-lookup"><span data-stu-id="f791d-183">Skype for Business PowerShell command:</span></span>

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> <span data-ttu-id="f791d-184">이렇게 하면 CloudPBX와 PSTNCallingDomesticAndInternational이 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-184">This adds CloudPBX and PSTNCallingDomesticAndInternational.</span></span> <span data-ttu-id="f791d-185">또한 관리자 인터페이스를 사용 하 여 전화 번호를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-185">Additionally, you will need to use the Admin interface to assign a phone number.</span></span>

## <a name="validate"></a><span data-ttu-id="f791d-186">Validate</span><span class="sxs-lookup"><span data-stu-id="f791d-186">Validate</span></span>

<span data-ttu-id="f791d-187">유효성 검사를 위해 Skype for Business 클라이언트를 사용 하 여 만든 계정에 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f791d-187">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="f791d-188">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f791d-188">See also</span></span>

[<span data-ttu-id="f791d-189">Microsoft 팀 대화방 계정 구성</span><span class="sxs-lookup"><span data-stu-id="f791d-189">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="f791d-190">Microsoft 팀 회의실 계획</span><span class="sxs-lookup"><span data-stu-id="f791d-190">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)

[<span data-ttu-id="f791d-191">Microsoft 팀 대화방 배포</span><span class="sxs-lookup"><span data-stu-id="f791d-191">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)

[<span data-ttu-id="f791d-192">Microsoft 팀 대화방 콘솔 구성</span><span class="sxs-lookup"><span data-stu-id="f791d-192">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="f791d-193">Microsoft 팀 대화방 관리</span><span class="sxs-lookup"><span data-stu-id="f791d-193">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)

[<span data-ttu-id="f791d-194">Microsoft 팀 대화방 라이선스</span><span class="sxs-lookup"><span data-stu-id="f791d-194">Microsoft Teams Rooms Licensing</span></span>](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md)
