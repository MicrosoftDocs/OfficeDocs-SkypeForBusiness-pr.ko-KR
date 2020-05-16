---
title: PowerShell을 사용 하 여 Microsoft 팀의 공동 작업 모음에 대 한 Microsoft 팀 자원 계정 만들기
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
description: Microsoft 팀에 대 한 공동 작업 표시줄을 배포 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 0cb8043e0530c986b9ddcaa9a1022254939adfd2
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268050"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a><span data-ttu-id="cdce8-103">PowerShell을 사용 하 여 Microsoft 365 리소스 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="cdce8-103">Create a Microsoft 365 resource account using the PowerShell</span></span>

<span data-ttu-id="cdce8-104">PowerShell을 사용 하 여 Microsoft 팀의 공동 작업 모음에 대 한 리소스 계정을 만드는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cdce8-104">Read this topic for information on how to create resource accounts for collaboration bars for Microsoft Teams using PowerShell.</span></span>

<span data-ttu-id="cdce8-105">리소스 계정을 만드는 가장 쉬운 방법은 Microsoft 365 관리 센터를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cdce8-105">The easiest way to create a resource account is by using the Microsoft 365 admin center.</span></span> <span data-ttu-id="cdce8-106">[이 작업을 수행 하는 방법에 대해서는이 문서를 참조](resource-account-ui.md)하세요.</span><span class="sxs-lookup"><span data-stu-id="cdce8-106">[See this article on how to do this](resource-account-ui.md).</span></span>

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a><span data-ttu-id="cdce8-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cdce8-107">Requirements</span></span>

<span data-ttu-id="cdce8-108">Microsoft 팀 회의실을 Office 365에 배포 하기 전에 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdce8-108">Before you deploy Microsoft Teams Rooms with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="cdce8-109">자세한 내용은 [Microsoft 팀에 대 한 공동 작업 표시줄 배포](collab-bar-deploy.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cdce8-109">For more information, see [Deploy collaboration bars for Microsoft Teams](collab-bar-deploy.md).</span></span>

- <span data-ttu-id="cdce8-110">공동 작업 표시줄에 PSTN 기능이 필요한 경우에는 전화 시스템 라이선스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdce8-110">If you need PSTN capabilities for the collaboration bar, you will need Phone System license.</span></span>

- <span data-ttu-id="cdce8-111">리소스 계정에 Exchange 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdce8-111">Your resource accounts must have Exchange mailboxes.</span></span> <span data-ttu-id="cdce8-112">이러한 계정은 리소스 계정 이므로 Exchange 라이선스가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cdce8-112">As these are resource accounts, no Exchange license is required.</span></span> <span data-ttu-id="cdce8-113">리소스 계정에 대해 회의실 라이선스를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cdce8-113">We recommend the usage of the Meeting Rooms license for resource accounts.</span></span>


### <a name="add-a-resource-account"></a><span data-ttu-id="cdce8-114">자원 계정 추가</span><span class="sxs-lookup"><span data-stu-id="cdce8-114">Add a resource account</span></span>

1. <span data-ttu-id="cdce8-115">Exchange Online PowerShell에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdce8-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="cdce8-116">지침은 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cdce8-116">For instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module).</span></span>

2. <span data-ttu-id="cdce8-117">Exchange Online PowerShell에서 새 회의실 사서함을 만들거나 기존 회의실 사서함을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdce8-117">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span>

   - <span data-ttu-id="cdce8-118">새 회의실 사서함을 만들려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdce8-118">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="cdce8-119">이 예제에서는 다음 설정을 사용 하 여 새 채팅방 사서함을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cdce8-119">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="cdce8-120">이름: Huddle--룸-01</span><span class="sxs-lookup"><span data-stu-id="cdce8-120">Name: Huddle-Room-01</span></span>

     - <span data-ttu-id="cdce8-121">별칭: HuddleRoom01</span><span class="sxs-lookup"><span data-stu-id="cdce8-121">Alias: HuddleRoom01</span></span>

     - <span data-ttu-id="cdce8-122">계정: huddleroom01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="cdce8-122">Account: huddleroom01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="cdce8-123">계정 암호: P@ $ $W 0rd242</span><span class="sxs-lookup"><span data-stu-id="cdce8-123">Account password: P@$$W0rd242</span></span>

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - <span data-ttu-id="cdce8-124">기존 회의실 사서함을 수정 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdce8-124">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="cdce8-125">이 예제에서는 별칭 값 HuddleRoom02를 가진 기존 회의실 사서함에 대 한 계정을 사용 하도록 설정 하 고 암호를 808P@ $ $W 0rd으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdce8-125">This example enables the account for the existing room mailbox that has the alias value HuddleRoom02, and sets the password to 808P@$$W0rd.</span></span> <span data-ttu-id="cdce8-126">기존 별칭 값 때문에 계정이 HuddleRoom02@contoso.onmicrosoft.com 것을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="cdce8-126">Note that the account will be HuddleRoom02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="cdce8-127">자세한 구문 및 매개 변수 정보는 [새 사서함](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) 및 [설정 사서함](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cdce8-127">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="cdce8-128">Exchange Online PowerShell에서 회의실 사서함에 다음 설정을 구성 하 여 모임 환경을 개선 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdce8-128">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="cdce8-129">AutomateProcessing: AutoAccept (모임 이끌이는 사용자 간섭 없이 직접 회의실 예약 결정을 받습니다: 무료 = 수락; 사용 중 = 거절).</span><span class="sxs-lookup"><span data-stu-id="cdce8-129">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="cdce8-130">AddOrganizerToSubject: $false (모임 이끌이는 모임 요청의 제목에 추가 되지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="cdce8-130">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="cdce8-131">Deletecomdea: $false (받는 모임 요청의 메시지 본문에 있는 텍스트는 유지 합니다.)</span><span class="sxs-lookup"><span data-stu-id="cdce8-131">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="cdce8-132">DeleteSubject: $false (들어오는 모임 요청의 주제를 보관 합니다.)</span><span class="sxs-lookup"><span data-stu-id="cdce8-132">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="cdce8-133">RemovePrivateProperty: $false (원래 모임 이끌이가 보낸 개인 플래그가 지정 된 대로 유지 되도록 합니다.)</span><span class="sxs-lookup"><span data-stu-id="cdce8-133">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="cdce8-134">AddAdditionalResponse: $true (AdditionalResponse 매개 변수에서 지정한 텍스트가 모임 요청에 추가 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="cdce8-134">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="cdce8-135">AdditionalResponse: "이 채팅방에는 Microsoft 팀에 대 한 공동 작업 표시줄이 있습니다!"</span><span class="sxs-lookup"><span data-stu-id="cdce8-135">AdditionalResponse: "This room has a collaboration bar for Microsoft Teams!"</span></span> <span data-ttu-id="cdce8-136">(모임 요청에 추가 하는 추가 텍스트입니다.)</span><span class="sxs-lookup"><span data-stu-id="cdce8-136">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="cdce8-137">이 예제에서는 Huddle 라는 룸 사서함에서 이러한 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdce8-137">This example configures these settings on the room mailbox named Huddle-Room-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   <span data-ttu-id="cdce8-138">자세한 구문 및 매개 변수 정보는 [설정-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cdce8-138">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="cdce8-139">Powershell cmdlet을 실행 하 여 Active Directory 설정을 만들기 위해 MS Online PowerShell에 연결 `Connect-MsolService -Credential $cred` 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdce8-139">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="cdce8-140">Active Directory에 대 한 자세한 내용은 [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cdce8-140">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="cdce8-141">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) 는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cdce8-141">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

5. <span data-ttu-id="cdce8-142">Huddleroom01@contoso.onmicrosoft.com의 암호가 만료 되지 않도록 설정 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdce8-142">Set the password for huddleroom01@contoso.onmicrosoft.com to not expire using the following syntax:</span></span>

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. <span data-ttu-id="cdce8-143">리소스 계정에는 유효한 Office 365 라이선스 (특히 회의실 SKU)가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdce8-143">The resource account needs to have a valid Office 365 license, preferably the Meeting Room SKU.</span></span> <span data-ttu-id="cdce8-144">또한 장치 계정에 사용 위치를 할당 해야 하며,이는 계정에 사용할 수 있는 라이선스 Sku를 결정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cdce8-144">You also need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="cdce8-145">`Get-MsolAccountSku`Office 365 테 넌 트에 대해 사용 가능한 sku 목록을 검색 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdce8-145">You can use `Get-MsolAccountSku` to retrieve a list of available SKUs for your Office 365 tenant.</span></span>

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    <span data-ttu-id="cdce8-146">Set-MsolUserLicense를 사용 하 여 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdce8-146">You can assign the license using Set-MsolUserLicense.</span></span> 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   <span data-ttu-id="cdce8-147">자세한 지침은 [Office 365 PowerShell을 사용 하 여 사용자 계정에 라이선스 할당](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cdce8-147">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>




[<span data-ttu-id="cdce8-148">PowerShell을 사용 하 여 Microsoft 팀의 공동 작업 모음에 대 한 계정 구성</span><span class="sxs-lookup"><span data-stu-id="cdce8-148">Configure accounts for collaboration bars for Microsoft Teams using PowerShell</span></span>](resource-account-ps.md)

[<span data-ttu-id="cdce8-149">Microsoft 팀을 위한 공동 작업 표시줄 배포</span><span class="sxs-lookup"><span data-stu-id="cdce8-149">Deploy collaboration bars for Microsoft Teams</span></span>](collab-bar-deploy.md)

[<span data-ttu-id="cdce8-150">Microsoft 팀 라이선스에 대 한 공동 작업 표시줄</span><span class="sxs-lookup"><span data-stu-id="cdce8-150">Collaboration bars for Microsoft Teams Licensing</span></span>](../rooms/rooms-licensing.md)


