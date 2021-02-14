---
title: PowerShell을 사용하여 Microsoft Teams의 공동 작업 막대에 대한 Microsoft Teams 리소스 계정 만들기
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
description: Microsoft Teams에 대한 공동 작업 막대를 배포하는 방법에 대한 자세한 내용은 이 항목을 참조하세요.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 0cb8043e0530c986b9ddcaa9a1022254939adfd2
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268050"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a><span data-ttu-id="b1ce4-103">PowerShell을 사용하여 Microsoft 365 리소스 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="b1ce4-103">Create a Microsoft 365 resource account using the PowerShell</span></span>

<span data-ttu-id="b1ce4-104">PowerShell을 사용하여 Microsoft Teams의 공동 작업 막대에 대한 리소스 계정을 만드는 방법에 대한 자세한 내용은 이 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b1ce4-104">Read this topic for information on how to create resource accounts for collaboration bars for Microsoft Teams using PowerShell.</span></span>

<span data-ttu-id="b1ce4-105">리소스 계정을 만드는 가장 쉬운 방법은 Microsoft 365 관리 센터를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b1ce4-105">The easiest way to create a resource account is by using the Microsoft 365 admin center.</span></span> <span data-ttu-id="b1ce4-106">[이 작업을 하는 방법에 대한 이 문서를 참조하세요.](resource-account-ui.md)</span><span class="sxs-lookup"><span data-stu-id="b1ce4-106">[See this article on how to do this](resource-account-ui.md).</span></span>

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a><span data-ttu-id="b1ce4-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b1ce4-107">Requirements</span></span>

<span data-ttu-id="b1ce4-108">Office 365에서 Microsoft Teams 회의실을 배포하기 전에 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1ce4-108">Before you deploy Microsoft Teams Rooms with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="b1ce4-109">자세한 내용은 Microsoft Teams의 공동 [작업 막대 배포를 참조하세요.](collab-bar-deploy.md)</span><span class="sxs-lookup"><span data-stu-id="b1ce4-109">For more information, see [Deploy collaboration bars for Microsoft Teams](collab-bar-deploy.md).</span></span>

- <span data-ttu-id="b1ce4-110">공동 작업 표시줄에 PSTN 기능이 필요한 경우 전화 시스템 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b1ce4-110">If you need PSTN capabilities for the collaboration bar, you will need Phone System license.</span></span>

- <span data-ttu-id="b1ce4-111">리소스 계정에 Exchange 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1ce4-111">Your resource accounts must have Exchange mailboxes.</span></span> <span data-ttu-id="b1ce4-112">리소스 계정이기 때문에 Exchange 라이선스가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b1ce4-112">As these are resource accounts, no Exchange license is required.</span></span> <span data-ttu-id="b1ce4-113">리소스 계정에 회의실 라이선스를 사용할 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b1ce4-113">We recommend the usage of the Meeting Rooms license for resource accounts.</span></span>


### <a name="add-a-resource-account"></a><span data-ttu-id="b1ce4-114">리소스 계정 추가</span><span class="sxs-lookup"><span data-stu-id="b1ce4-114">Add a resource account</span></span>

1. <span data-ttu-id="b1ce4-115">Exchange Online PowerShell에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="b1ce4-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="b1ce4-116">자세한 내용은 [Exchange Online PowerShell에 연결합니다.](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)</span><span class="sxs-lookup"><span data-stu-id="b1ce4-116">For instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module).</span></span>

2. <span data-ttu-id="b1ce4-117">Exchange Online PowerShell에서 새 방 사서함을 만들거나 기존 방 사서함을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="b1ce4-117">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span>

   - <span data-ttu-id="b1ce4-118">새 방 사서함을 만들 경우 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1ce4-118">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="b1ce4-119">이 예제에서는 다음 설정을 사용하여 새 방 사서함을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b1ce4-119">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="b1ce4-120">이름: Huddle-Room-01</span><span class="sxs-lookup"><span data-stu-id="b1ce4-120">Name: Huddle-Room-01</span></span>

     - <span data-ttu-id="b1ce4-121">별칭: HuddleRoom01</span><span class="sxs-lookup"><span data-stu-id="b1ce4-121">Alias: HuddleRoom01</span></span>

     - <span data-ttu-id="b1ce4-122">계정: huddleroom01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="b1ce4-122">Account: huddleroom01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="b1ce4-123">계정 암호: P@$$W 0rd242</span><span class="sxs-lookup"><span data-stu-id="b1ce4-123">Account password: P@$$W0rd242</span></span>

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - <span data-ttu-id="b1ce4-124">기존 방 사서함을 수정하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1ce4-124">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="b1ce4-125">이 예제에서는 별칭 값이 HuddleRoom02인 기존 회의실 사서함의 계정을 사용할 수 있으며 암호를 808P@$$W 0rd로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b1ce4-125">This example enables the account for the existing room mailbox that has the alias value HuddleRoom02, and sets the password to 808P@$$W0rd.</span></span> <span data-ttu-id="b1ce4-126">기존 별칭 값으로 HuddleRoom02@contoso.onmicrosoft.com 계정이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1ce4-126">Note that the account will be HuddleRoom02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="b1ce4-127">자세한 구문 및 매개 변수 정보는 [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) 및 [Set-Mailbox을 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)</span><span class="sxs-lookup"><span data-stu-id="b1ce4-127">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="b1ce4-128">Exchange Online PowerShell에서 회의실 사서함에서 다음 설정을 구성하여 모임 환경을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="b1ce4-128">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="b1ce4-129">AutomateProcessing: AutoAccept(모임 이끌이는 사용자 개입 없이 바로 회의실 예약 결정을 수신합니다. 무료 = 수락, 사용 중 = 거절).</span><span class="sxs-lookup"><span data-stu-id="b1ce4-129">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="b1ce4-130">AddOrganizerToSubject: $false(모임 이끌이는 모임 요청의 제목에 추가되지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="b1ce4-130">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="b1ce4-131">DeleteComments: $false(들어오는 모임 요청의 메시지 본문에 텍스트를 보관합니다.)</span><span class="sxs-lookup"><span data-stu-id="b1ce4-131">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="b1ce4-132">DeleteSubject: $false(들어오는 모임 요청의 제목 유지)</span><span class="sxs-lookup"><span data-stu-id="b1ce4-132">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="b1ce4-133">RemovePrivateProperty: $false(원래 모임 요청에서 모임 이끌이가 보낸 개인 플래그가 지정된 상태로 유지되도록 합니다.)</span><span class="sxs-lookup"><span data-stu-id="b1ce4-133">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="b1ce4-134">AddAdditionalResponse: $true(AdditionalResponse 매개 변수로 지정된 텍스트가 모임 요청에 추가됩니다.)</span><span class="sxs-lookup"><span data-stu-id="b1ce4-134">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="b1ce4-135">AdditionalResponse: "이 방에는 Microsoft Teams에 대한 공동 작업 표시줄이 있습니다!"</span><span class="sxs-lookup"><span data-stu-id="b1ce4-135">AdditionalResponse: "This room has a collaboration bar for Microsoft Teams!"</span></span> <span data-ttu-id="b1ce4-136">(모임 요청에 추가할 추가 텍스트입니다.)</span><span class="sxs-lookup"><span data-stu-id="b1ce4-136">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="b1ce4-137">이 예제에서는 Huddle-Room-01이라는 방 사서함에서 이러한 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b1ce4-137">This example configures these settings on the room mailbox named Huddle-Room-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   <span data-ttu-id="b1ce4-138">자세한 구문 및 매개 변수 정보는 [Set-CalendarProcessing을 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)</span><span class="sxs-lookup"><span data-stu-id="b1ce4-138">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="b1ce4-139">MS Online PowerShell에 연결하여 PowerShell cmdlet을 실행하여 Active Directory `Connect-MsolService -Credential $cred` 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b1ce4-139">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="b1ce4-140">Active Directory에 대한 자세한 내용은 [Azure ActiveDirectory(MSOnline) 1.0을 참조하세요.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="b1ce4-140">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="b1ce4-141">[Azure Active Directory PowerShell 2.0은](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b1ce4-141">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

5. <span data-ttu-id="b1ce4-142">다음 구문을 사용하여 huddleroom01@contoso.onmicrosoft.com 암호가 만료되지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1ce4-142">Set the password for huddleroom01@contoso.onmicrosoft.com to not expire using the following syntax:</span></span>

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. <span data-ttu-id="b1ce4-143">리소스 계정에 유효한 Office 365 라이선스가 있어야 합니다( 가급적이면 회의실 SKU).</span><span class="sxs-lookup"><span data-stu-id="b1ce4-143">The resource account needs to have a valid Office 365 license, preferably the Meeting Room SKU.</span></span> <span data-ttu-id="b1ce4-144">또한 디바이스 계정에 사용 위치를 할당해야 합니다. 그러면 계정에 사용할 수 있는 라이선스 SKUS가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1ce4-144">You also need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="b1ce4-145">Office 365 테넌트에 사용 가능한 SKUS 목록을 검색하는 `Get-MsolAccountSku` 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1ce4-145">You can use `Get-MsolAccountSku` to retrieve a list of available SKUs for your Office 365 tenant.</span></span>

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    <span data-ttu-id="b1ce4-146">Set-MsolUserLicense를 사용하여 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1ce4-146">You can assign the license using Set-MsolUserLicense.</span></span> 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   <span data-ttu-id="b1ce4-147">자세한 지침은 [Office 365 PowerShell을](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)통해 사용자 계정에 라이선스 할당을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b1ce4-147">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>




[<span data-ttu-id="b1ce4-148">PowerShell을 사용하여 Microsoft Teams에 대한 공동 작업 막대 계정 구성</span><span class="sxs-lookup"><span data-stu-id="b1ce4-148">Configure accounts for collaboration bars for Microsoft Teams using PowerShell</span></span>](resource-account-ps.md)

[<span data-ttu-id="b1ce4-149">Microsoft Teams에 대한 공동 작업 막대 배포</span><span class="sxs-lookup"><span data-stu-id="b1ce4-149">Deploy collaboration bars for Microsoft Teams</span></span>](collab-bar-deploy.md)

[<span data-ttu-id="b1ce4-150">Microsoft Teams 라이선싱을 위한 공동 작업 막대</span><span class="sxs-lookup"><span data-stu-id="b1ce4-150">Collaboration bars for Microsoft Teams Licensing</span></span>](../rooms/rooms-licensing.md)


