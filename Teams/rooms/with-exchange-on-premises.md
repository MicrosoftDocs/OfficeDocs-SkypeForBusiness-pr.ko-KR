---
title: Microsoft Teams 룸 Exchange 배포
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
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: 이 항목을 참조하여 Microsoft Teams 룸 하이브리드 환경에서 배포하는 방법에 Exchange 있습니다.
ms.openlocfilehash: 3931ba89dd4ad0dfd994fdf27a3f209275850116
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117356"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a><span data-ttu-id="f9a0a-103">Microsoft Teams 룸 Exchange 배포</span><span class="sxs-lookup"><span data-stu-id="f9a0a-103">Deploy Microsoft Teams Rooms with Exchange on premises</span></span>

<span data-ttu-id="f9a0a-104">이 항목에서는 온라인에서 Microsoft Teams 룸 및 Exchange 하이브리드 환경에서 Microsoft Teams 비즈니스용 Skype 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-104">Read this topic for information on how to deploy Microsoft Teams Rooms in a hybrid environment with Exchange on premises and Microsoft Teams or Skype for Business Online.</span></span>
  
<span data-ttu-id="f9a0a-105">조직에 일부 호스팅되는 일부 프레미스 및 온라인에서 호스팅되는 서비스가 혼합된 경우 구성은 각 서비스가 호스트되는 위치에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="f9a0a-106">이 항목에서는 프레미스에서 호스팅되는 Microsoft Teams 룸 Exchange 하이브리드 배포에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted on premises.</span></span> <span data-ttu-id="f9a0a-107">이 유형의 배포에는 다양한 변형이 있으므로 모든 배포에 대한 자세한 지침을 제공할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="f9a0a-108">다음 프로세스는 여러 구성에 대해 작동할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-108">The following process will work for many configurations.</span></span> <span data-ttu-id="f9a0a-109">프로세스가 설정에 맞지 않는 경우 여기에서 설명한 Windows PowerShell 및 다른 배포 옵션에 대해 동일한 최종 결과를 달성하기 위해 이 프로세스를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="f9a0a-110">Microsoft는 [ ](https://go.microsoft.com/fwlink/?linkid=870105)SkypeRoomProvisioningScript.ps1사용자 계정으로 전환할 수 있도록 새 사용자 계정을 만들거나 기존 리소스 계정의 유효성을 검사하는 데 도움이 되는 Microsoft Teams 룸 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-110">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="f9a0a-111">원하는 경우 아래 단계를 수행하여 디바이스에서 사용할 계정을 Microsoft Teams 룸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-111">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="f9a0a-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f9a0a-112">Requirements</span></span>

<span data-ttu-id="f9a0a-113">Microsoft Teams 룸 Exchange 배포하기 전에 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-113">Before you deploy Microsoft Teams Rooms with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="f9a0a-114">자세한 내용은 요구 사항 [Microsoft Teams 룸 참조하세요.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="f9a0a-114">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="f9a0a-115">Microsoft Teams 룸 Exchange 배포하는 경우 Active Directory 관리 도구를 사용하여 프레미스 도메인 계정에 대한 전자 메일 주소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-115">If you are deploying Microsoft Teams Rooms with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="f9a0a-116">이 계정은 Microsoft 365 또는 Office 365.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-116">This account will be synced to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="f9a0a-117">다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-117">You will need to:</span></span>
  
- <span data-ttu-id="f9a0a-118">계정을 만들고 Active Directory와 계정을 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-118">Create an account and synchronize the account with Active Directory.</span></span>

- <span data-ttu-id="f9a0a-119">원격 사서함을 사용하도록 설정하고 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-119">Enable the remote mailbox and set properties.</span></span>

- <span data-ttu-id="f9a0a-120">라이선스 또는 Microsoft 365 Office 365 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-120">Assign an Microsoft 365 or Office 365 license.</span></span>

- <span data-ttu-id="f9a0a-121">디바이스 계정을 비즈니스용 Skype 서버.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="f9a0a-122">디바이스 계정을 사용하도록 설정하려면 환경이 다음 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>

  - <span data-ttu-id="f9a0a-123">온라인 또는 비즈니스용 Skype(계획 2) 이상이 Microsoft 365 Office 365 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="f9a0a-124">계획은 회의 기능을 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-124">The plan needs to support conferencing capability.</span></span>
  
  - <span data-ttu-id="f9a0a-125">전화 통신 서비스 공급자를 Enterprise Voice(PSTN 전화 통신)가 필요한 경우 Microsoft Teams 룸 온라인(계획 3)비즈니스용 Skype 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Microsoft Teams Rooms you need Skype for Business Online (Plan 3).</span></span>

  - <span data-ttu-id="f9a0a-126">온라인 또는 Microsoft Teams 비즈니스용 Skype 룸 계정을 구성할 경우, 계정이 룸 계정으로 사용하도록 설정하기 전에 전화 번호를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-126">When configuring a room account with Microsoft Teams or Skype for Business Online, the phone number should be assigned prior to the account being enabled as a room account.</span></span>
  
  - <span data-ttu-id="f9a0a-127">테넌트 사용자에게 사서함이 Exchange 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-127">Your tenant users must have Exchange mailboxes.</span></span>
  
  - <span data-ttu-id="f9a0a-128">Microsoft Teams 룸 계정에는 비즈니스용 Skype(계획 2) 또는 비즈니스용 Skype(계획 3) 라이선스가 필요하지만 라이선스가 Exchange Online 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-128">Your Microsoft Teams Rooms account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>

- <span data-ttu-id="f9a0a-129">비즈니스용 Skype 서버 계정에 Microsoft Teams 룸 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-129">Assign a Skype for Business Server license to your Microsoft Teams Rooms account.</span></span>

### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="f9a0a-130">계정 만들기 및 Active Directory와 동기화</span><span class="sxs-lookup"><span data-stu-id="f9a0a-130">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="f9a0a-131">Active **Directory** 사용자 및 컴퓨터 도구에서 사용자 계정이 생성될 폴더 또는 조직 단위를 마우스 오른쪽 단추로 클릭하고 Microsoft Teams 룸 클릭한 다음 사용자 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f9a0a-131">In the **Active Directory Users and Computers** tool, right-click on the folder or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>

2. <span data-ttu-id="f9a0a-132">이전 cmdlet의 표시 이름을 전체  이름 상자에 입력하고 별칭을 사용자 로그온 이름 상자에 **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="f9a0a-132">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="f9a0a-133">다음 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f9a0a-133">Click **Next**.</span></span>

3. <span data-ttu-id="f9a0a-134">이 계정에 대한 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-134">Type the password for this account.</span></span> <span data-ttu-id="f9a0a-135">확인을 위해 다시 타이프해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-135">You'll need to retype it for verification.</span></span> <span data-ttu-id="f9a0a-136">암호가 **만료되지** 않는지 확인란만 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-136">Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f9a0a-137">암호가  만료되지 않는 경우 암호를 선택해야 비즈니스용 Skype 서버 Microsoft Teams 룸.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-137">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="f9a0a-138">도메인 규칙은 만료되지 않는 암호를 금지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-138">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="f9a0a-139">그렇다면 각 디바이스 계정에 대한 예외를 Microsoft Teams 룸 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-139">If so, you'll need to create an exception for each Microsoft Teams Rooms device account.</span></span>
  
4. <span data-ttu-id="f9a0a-140">계정을 만든 후 디렉터리 동기화를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-140">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="f9a0a-141">완료되면 관리자 센터의 사용자 페이지로 Microsoft 365 이전 단계에서 만든 계정이 온라인에 병합되어 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-141">When it's complete, go to the users page in your Microsoft 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="f9a0a-142">원격 사서함 사용 및 속성 설정</span><span class="sxs-lookup"><span data-stu-id="f9a0a-142">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="f9a0a-143">[원격 PowerShell을](/powershell/exchange/exchange-server/open-the-exchange-management-shell) 사용하여 Exchange 관리 셸을 열거나 Exchange 서버에 [연결합니다.](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)</span><span class="sxs-lookup"><span data-stu-id="f9a0a-143">[Open the Exchange Management Shell](/powershell/exchange/exchange-server/open-the-exchange-management-shell) or [connect to your Exchange server using remote PowerShell](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="f9a0a-144">PowerShell의 Exchange 다음 명령을 실행하여 계정에 대한 사서함(사서함 사용 계정)을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-144">In Exchange PowerShell, create a mailbox for the account (mailbox-enable the account) by running the following command:</span></span>

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   <span data-ttu-id="f9a0a-145">자세한 구문 및 매개 변수 정보는 [사용-사서함 을 참조하세요.](/powershell/module/exchange/mailboxes/enable-mailbox)</span><span class="sxs-lookup"><span data-stu-id="f9a0a-145">For detailed syntax and parameter information, see [Enable-Mailbox](/powershell/module/exchange/mailboxes/enable-mailbox).</span></span>

3. <span data-ttu-id="f9a0a-146">PowerShell의 Exchange 회의실 사서함에서 다음 설정을 구성하여 모임 환경을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-146">In Exchange PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="f9a0a-147">AutomateProcessing: AutoAccept(모임 이끌이는 사용자 개입 없이 직접 회의실 예약 결정을 수신합니다. 무료 = 수락, 사용 중 = 거부).)</span><span class="sxs-lookup"><span data-stu-id="f9a0a-147">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="f9a0a-148">AddOrganizerToSubject: $false(모임 이끌이가 모임 요청의 제목에 추가되지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="f9a0a-148">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="f9a0a-149">DeleteComments: $false(들어오는 모임 요청의 메시지 본문에 텍스트를 보관합니다.)</span><span class="sxs-lookup"><span data-stu-id="f9a0a-149">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="f9a0a-150">DeleteSubject: $false(들어오는 모임 요청의 제목 유지)입니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-150">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="f9a0a-151">RemovePrivateProperty: $false(원래 모임 요청에서 모임 이끌이가 보낸 개인 플래그가 지정된 상태로 유지되도록 합니다.)</span><span class="sxs-lookup"><span data-stu-id="f9a0a-151">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="f9a0a-152">AddAdditionalResponse: $true(AdditionalResponse 매개 변수에서 지정한 텍스트가 모임 요청에 추가됩니다.)</span><span class="sxs-lookup"><span data-stu-id="f9a0a-152">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="f9a0a-153">AdditionalResponse: "이 방은 Skype 모임 방입니다!"</span><span class="sxs-lookup"><span data-stu-id="f9a0a-153">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="f9a0a-154">(모임 요청에 추가할 추가 텍스트입니다.)</span><span class="sxs-lookup"><span data-stu-id="f9a0a-154">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="f9a0a-155">이 예제에서는 Project-Rigel-01이라는 방 사서함에서 이러한 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-155">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="f9a0a-156">자세한 구문 및 매개 변수 정보는 [Set-CalendarProcessing 을 참조하세요.](/powershell/module/exchange/mailboxes/set-calendarprocessing)</span><span class="sxs-lookup"><span data-stu-id="f9a0a-156">For detailed syntax and parameter information, see [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

### <a name="assign-a-microsoft-365-or-office-365-license"></a><span data-ttu-id="f9a0a-157">라이선스 Microsoft 365 또는 Office 365 할당</span><span class="sxs-lookup"><span data-stu-id="f9a0a-157">Assign a Microsoft 365 or Office 365 license</span></span>

1. <span data-ttu-id="f9a0a-158">커넥트 Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-158">Connect to Azure Active Directory.</span></span> <span data-ttu-id="f9a0a-159">Active Directory에 대한 자세한 내용은 [Azure ActiveDirectory(MSOnline) 1.0 을 참조하세요.](/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="f9a0a-159">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="f9a0a-160">[Azure Active Directory PowerShell 2.0은](/powershell/azure/active-directory/overview?view=azureadps-2.0) 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-160">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

2. <span data-ttu-id="f9a0a-161">디바이스 계정에 유효한 Microsoft 365 Office 365 라이선스가 있어야 Exchange Microsoft Teams 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-161">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams will not work.</span></span> <span data-ttu-id="f9a0a-162">라이선스가 있는 경우 디바이스 계정에 사용 위치를 할당해야 합니다. 그러면 계정에 사용할 수 있는 라이선스 SKUS가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-162">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="f9a0a-163">사용할 수 있습니다. `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="f9a0a-163">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="f9a0a-164">를 사용하여 사용 가능한 SKUS 목록을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-164">to retrieve a list of available SKUs.</span></span>

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. <span data-ttu-id="f9a0a-165">다음으로, `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="f9a0a-165">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense --> <span data-ttu-id="f9a0a-166">cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-166">cmdlet.</span></span> <span data-ttu-id="f9a0a-167">이 경우 $strLicense SKU 코드입니다(예: contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="f9a0a-167">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

  ``` PowerShell
  Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
  Get-MsolAccountSku
  Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```

<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```  -->

   <span data-ttu-id="f9a0a-168">자세한 지침은 PowerShell을 통해 사용자 계정에 라이선스 [할당을 Office 365 참조하세요.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="f9a0a-168">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="enable-the-device-account"></a><span data-ttu-id="f9a0a-169">디바이스 계정 사용</span><span class="sxs-lookup"><span data-stu-id="f9a0a-169">Enable the device account</span></span>

<span data-ttu-id="f9a0a-170">비즈니스용 Skype Online PowerShell은 온라인 및 Microsoft Teams 모두에 비즈니스용 Skype 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-170">Skype for Business Online PowerShell is used to manage services for both Microsoft Teams and Skype for Business Online.</span></span>

1. <span data-ttu-id="f9a0a-171">다음과 Windows PowerShell PC에서 원격 세션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-171">Create a remote Windows PowerShell session from a PC as follows:</span></span>
> [!NOTE]
> <span data-ttu-id="f9a0a-172">비즈니스용 Skype 온라인 커넥터는 현재 최신 PowerShell Teams 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-172">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="f9a0a-173">최신 [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 Teams 사용하는 경우 온라인 커넥터를 비즈니스용 Skype 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-173">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

2. <span data-ttu-id="f9a0a-174">계정의 SIP 주소를 구합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-174">Obtain SIP address of the account:</span></span>

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. <span data-ttu-id="f9a0a-175">**선택 사항입니다.**</span><span class="sxs-lookup"><span data-stu-id="f9a0a-175">**Optional.**</span></span> <span data-ttu-id="f9a0a-176">계정에 전화 번호를 할당하려면 이 시점에서 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-176">If you want to assign a phone number to the account, the operation should be performed at this point.</span></span> <span data-ttu-id="f9a0a-177">직접 라우팅 전화 번호를 할당하려는 경우:</span><span class="sxs-lookup"><span data-stu-id="f9a0a-177">If you want to assign a Direct Routing phone number:</span></span>

   ``` Powershell
    Set-CsUser -Identity $rm -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:+14255550012
    ```
    <span data-ttu-id="f9a0a-178">Microsoft에서 제공한 전화 번호를 할당하는 경우 사용자를 호출 계획 라이선스로 프로비전한 후 아래 cmdlet을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-178">If you're assigning a Microsoft provided phone number, use the cmdlet below after having provisioned the user with a Calling Plan license:</span></span>
    
    ``` Powershell
    Set-CsOnlineVoiceUser -Identity $rm -TelephoneNumber +14255550011 -LocationID xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
    ```
    
4. <span data-ttu-id="f9a0a-179">Microsoft Teams 룸 계정을 사용하도록 설정하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-179">To enable your Microsoft Teams Rooms account, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="f9a0a-180">환경에서 RegistrarPool 매개 변수에 사용할 값이 확실하지 않은 경우 이 명령을 사용하여 기존 사용자로부터 값을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-180">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing user using this command:</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="f9a0a-181">사용자 계정에 라이선스 Microsoft Teams 룸 할당</span><span class="sxs-lookup"><span data-stu-id="f9a0a-181">Assign a license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="f9a0a-182">테넌트 관리자로 로그인하고 관리자 Microsoft 365 센터를 열고 관리자 앱을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-182">Log in as a tenant administrator, open the Microsoft 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="f9a0a-183">사용자 및 **그룹을 클릭한** 다음 사용자 추가, 암호 재설정 **등 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f9a0a-183">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="f9a0a-184">계정 Microsoft Teams 룸 클릭한 다음 펜 아이콘을 클릭하여 계정 정보를 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-184">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="f9a0a-185">라이선스를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f9a0a-185">Click **Licenses**.</span></span>
5. <span data-ttu-id="f9a0a-186">라이선스 **할당에서** 라이선스 비즈니스용 Skype 요구 사항에 따라 비즈니스용 Skype(계획 2) 또는 비즈니스용 Skype(계획 3)를 Enterprise Voice 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-186">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="f9a0a-187">계획 3 라이선스를 사용하려는 경우 Enterprise Voice 라이선스를 Microsoft Teams 룸.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-187">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="f9a0a-188">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-188">Click **Save**.</span></span>

<span data-ttu-id="f9a0a-189">유효성 검사의 경우 클라이언트를 사용하여 이 계정에 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9a0a-189">For validation, you should be able to use any client to log in to this account.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f9a0a-190">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f9a0a-190">Related topics</span></span>

[<span data-ttu-id="f9a0a-191">Microsoft Teams 룸</span><span class="sxs-lookup"><span data-stu-id="f9a0a-191">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="f9a0a-192">Microsoft Teams 룸 계획</span><span class="sxs-lookup"><span data-stu-id="f9a0a-192">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="f9a0a-193">Microsoft Teams 룸 배포</span><span class="sxs-lookup"><span data-stu-id="f9a0a-193">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="f9a0a-194">Microsoft Teams 룸 콘솔 구성</span><span class="sxs-lookup"><span data-stu-id="f9a0a-194">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="f9a0a-195">Microsoft Teams 룸 관리</span><span class="sxs-lookup"><span data-stu-id="f9a0a-195">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)