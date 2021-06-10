---
title: PowerShell을 Microsoft Teams 공동 작업용 공동 작업 Microsoft Teams 리소스 계정 만들기
ms.author: mitressl
author: flinchbot
manager: ericwe
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: 공동 작업 막대를 배포하는 방법에 대한 자세한 내용은 이 Microsoft Teams.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 812fb4704661aa11d3388048fa044030cdb1ce00
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115606"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a><span data-ttu-id="06b2d-103">PowerShell을 사용하여 Microsoft 365 리소스 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="06b2d-103">Create a Microsoft 365 resource account using the PowerShell</span></span>

<span data-ttu-id="06b2d-104">PowerShell을 사용하여 공동 작업용 공동 작업 막대에 Microsoft Teams 방법에 대한 자세한 내용은 이 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06b2d-104">Read this topic for information on how to create resource accounts for collaboration bars for Microsoft Teams using PowerShell.</span></span>

<span data-ttu-id="06b2d-105">리소스 계정을 만드는 가장 쉬운 방법은 관리 센터를 Microsoft 365 것입니다.</span><span class="sxs-lookup"><span data-stu-id="06b2d-105">The easiest way to create a resource account is by using the Microsoft 365 admin center.</span></span> <span data-ttu-id="06b2d-106">[이 작업을 하는 방법에 대한 이 문서를 참조하세요.](resource-account-ui.md)</span><span class="sxs-lookup"><span data-stu-id="06b2d-106">[See this article on how to do this](resource-account-ui.md).</span></span>

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a><span data-ttu-id="06b2d-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="06b2d-107">Requirements</span></span>

<span data-ttu-id="06b2d-108">Microsoft Teams 룸 배포하기 Office 365 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06b2d-108">Before you deploy Microsoft Teams Rooms with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="06b2d-109">자세한 내용은 에 대한 공동 [작업 Microsoft Teams.](collab-bar-deploy.md)</span><span class="sxs-lookup"><span data-stu-id="06b2d-109">For more information, see [Deploy collaboration bars for Microsoft Teams](collab-bar-deploy.md).</span></span>

- <span data-ttu-id="06b2d-110">공동 작업 표시줄에 PSTN 기능이 필요한 경우 라이선스가 전화 시스템 합니다.</span><span class="sxs-lookup"><span data-stu-id="06b2d-110">If you need PSTN capabilities for the collaboration bar, you will need Phone System license.</span></span>

- <span data-ttu-id="06b2d-111">리소스 계정에 사서함이 Exchange 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06b2d-111">Your resource accounts must have Exchange mailboxes.</span></span> <span data-ttu-id="06b2d-112">리소스 계정이기 때문에 라이선스가 Exchange 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06b2d-112">As these are resource accounts, no Exchange license is required.</span></span> <span data-ttu-id="06b2d-113">리소스 계정에 회의실 라이선스를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="06b2d-113">We recommend the usage of the Meeting Rooms license for resource accounts.</span></span>


### <a name="add-a-resource-account"></a><span data-ttu-id="06b2d-114">리소스 계정 추가</span><span class="sxs-lookup"><span data-stu-id="06b2d-114">Add a resource account</span></span>

1. <span data-ttu-id="06b2d-115">커넥트 PowerShell을 Exchange Online 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06b2d-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="06b2d-116">지침은 [PowerShell을 커넥트 Exchange Online 참조하세요.](/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)</span><span class="sxs-lookup"><span data-stu-id="06b2d-116">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module).</span></span>

2. <span data-ttu-id="06b2d-117">PowerShell에서 새 Exchange Online 사서함을 만들거나 기존 방 사서함을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="06b2d-117">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span>

   - <span data-ttu-id="06b2d-118">새 룸 사서함을 만들 경우 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="06b2d-118">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="06b2d-119">이 예제에서는 다음 설정을 사용하여 새 룸 사서함을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="06b2d-119">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="06b2d-120">이름: Huddle-Room-01</span><span class="sxs-lookup"><span data-stu-id="06b2d-120">Name: Huddle-Room-01</span></span>

     - <span data-ttu-id="06b2d-121">별칭: HuddleRoom01</span><span class="sxs-lookup"><span data-stu-id="06b2d-121">Alias: HuddleRoom01</span></span>

     - <span data-ttu-id="06b2d-122">계정: huddleroom01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="06b2d-122">Account: huddleroom01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="06b2d-123">계정 암호: P@$$W 0rd242</span><span class="sxs-lookup"><span data-stu-id="06b2d-123">Account password: P@$$W0rd242</span></span>

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - <span data-ttu-id="06b2d-124">기존 룸 사서함을 수정하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="06b2d-124">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="06b2d-125">이 예제에서는 별칭 값이 HuddleRoom02인 기존 회의실 사서함에 대한 계정을 사용할 수 있으며 암호를 808P@$$W 0rd로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="06b2d-125">This example enables the account for the existing room mailbox that has the alias value HuddleRoom02, and sets the password to 808P@$$W0rd.</span></span> <span data-ttu-id="06b2d-126">기존 별칭 값으로 HuddleRoom02@contoso.onmicrosoft.com 계정이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="06b2d-126">Note that the account will be HuddleRoom02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="06b2d-127">자세한 구문 및 매개 변수 정보는 [New-사서함](/powershell/module/exchange/mailboxes/new-mailbox) 및 [Set-사서함 을 참조하세요.](/powershell/module/exchange/mailboxes/set-mailbox)</span><span class="sxs-lookup"><span data-stu-id="06b2d-127">For detailed syntax and parameter information, see [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="06b2d-128">PowerShell의 Exchange Online 회의실 사서함에서 다음 설정을 구성하여 모임 환경을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="06b2d-128">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="06b2d-129">AutomateProcessing: AutoAccept(모임 이끌이는 사용자 개입 없이 직접 회의실 예약 결정을 수신합니다. 무료 = 수락, 사용 중 = 거부).)</span><span class="sxs-lookup"><span data-stu-id="06b2d-129">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="06b2d-130">AddOrganizerToSubject: $false(모임 이끌이가 모임 요청의 제목에 추가되지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="06b2d-130">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="06b2d-131">DeleteComments: $false(들어오는 모임 요청의 메시지 본문에 텍스트를 보관합니다.)</span><span class="sxs-lookup"><span data-stu-id="06b2d-131">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="06b2d-132">DeleteSubject: $false(들어오는 모임 요청의 제목 유지)입니다.</span><span class="sxs-lookup"><span data-stu-id="06b2d-132">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="06b2d-133">RemovePrivateProperty: $false(원래 모임 요청에서 모임 이끌이가 보낸 개인 플래그가 지정된 상태로 유지되도록 합니다.)</span><span class="sxs-lookup"><span data-stu-id="06b2d-133">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="06b2d-134">AddAdditionalResponse: $true(AdditionalResponse 매개 변수에서 지정한 텍스트가 모임 요청에 추가됩니다.)</span><span class="sxs-lookup"><span data-stu-id="06b2d-134">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="06b2d-135">추가Response: "이 방에는 공동 작업 표시줄이 Microsoft Teams!"</span><span class="sxs-lookup"><span data-stu-id="06b2d-135">AdditionalResponse: "This room has a collaboration bar for Microsoft Teams!"</span></span> <span data-ttu-id="06b2d-136">(모임 요청에 추가할 추가 텍스트입니다.)</span><span class="sxs-lookup"><span data-stu-id="06b2d-136">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="06b2d-137">이 예제에서는 Huddle-Room-01이라는 룸 사서함에서 이러한 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="06b2d-137">This example configures these settings on the room mailbox named Huddle-Room-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   <span data-ttu-id="06b2d-138">자세한 구문 및 매개 변수 정보는 [Set-CalendarProcessing 을 참조하세요.](/powershell/module/exchange/mailboxes/set-calendarprocessing)</span><span class="sxs-lookup"><span data-stu-id="06b2d-138">For detailed syntax and parameter information, see [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="06b2d-139">커넥트 powershell cmdlet을 실행하여 Active Directory 설정을 만들기 위해 MS Online `Connect-MsolService -Credential $cred` PowerShell으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="06b2d-139">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="06b2d-140">Active Directory에 대한 자세한 내용은 [Azure ActiveDirectory(MSOnline) 1.0 을 참조하세요.](/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="06b2d-140">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="06b2d-141">[Azure Active Directory PowerShell 2.0은](/powershell/azure/active-directory/overview?view=azureadps-2.0) 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06b2d-141">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

5. <span data-ttu-id="06b2d-142">다음 구문을 사용하여 huddleroom01@contoso.onmicrosoft.com 암호가 만료되지 않는지 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="06b2d-142">Set the password for huddleroom01@contoso.onmicrosoft.com to not expire using the following syntax:</span></span>

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. <span data-ttu-id="06b2d-143">리소스 계정에 유효한 SKU Office 365 라이선스가 미팅룸 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="06b2d-143">The resource account needs to have a valid Office 365 license, preferably the Meeting Room SKU.</span></span> <span data-ttu-id="06b2d-144">또한 디바이스 계정에 사용 위치를 할당해야 합니다. 그러면 계정에 사용할 수 있는 라이선스 SKUS가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="06b2d-144">You also need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="06b2d-145">테넌트에 사용할 수 있는 SKUS 목록을 검색하는 `Get-MsolAccountSku` 데 Office 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06b2d-145">You can use `Get-MsolAccountSku` to retrieve a list of available SKUs for your Office 365 tenant.</span></span>

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    <span data-ttu-id="06b2d-146">Set-MsolUserLicense를 사용하여 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06b2d-146">You can assign the license using Set-MsolUserLicense.</span></span> 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   <span data-ttu-id="06b2d-147">자세한 지침은 PowerShell을 통해 사용자 계정에 라이선스 [할당을 Office 365 참조하세요.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="06b2d-147">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>




[<span data-ttu-id="06b2d-148">PowerShell을 사용하여 공동 작업 Microsoft Teams 계정 구성</span><span class="sxs-lookup"><span data-stu-id="06b2d-148">Configure accounts for collaboration bars for Microsoft Teams using PowerShell</span></span>](resource-account-ps.md)

[<span data-ttu-id="06b2d-149">공동 작업용 공동 작업 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="06b2d-149">Deploy collaboration bars for Microsoft Teams</span></span>](collab-bar-deploy.md)

[<span data-ttu-id="06b2d-150">라이선스에 Microsoft Teams 공동 작업 막대</span><span class="sxs-lookup"><span data-stu-id="06b2d-150">Collaboration bars for Microsoft Teams Licensing</span></span>](../rooms/rooms-licensing.md)