---
title: Exchange와 함께 Microsoft 팀 대화방 배포 (온-프레미스)
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection: M365-voice
description: Exchange 온-프레미스를 사용 하는 하이브리드 환경에서 Microsoft 팀 대화방을 배포 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.
ms.openlocfilehash: 6d0f7703235e0724b105dd862f2a6549f884d3b2
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243270"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a><span data-ttu-id="cab9c-103">Exchange와 함께 Microsoft 팀 대화방 배포 (온-프레미스)</span><span class="sxs-lookup"><span data-stu-id="cab9c-103">Deploy Microsoft Teams Rooms with Exchange on premises</span></span>

<span data-ttu-id="cab9c-104">온-프레미스와 Microsoft 팀 또는 비즈니스용 Skype Online을 사용 하는 하이브리드 환경에서 Microsoft 팀 대화방을 배포 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cab9c-104">Read this topic for information on how to deploy Microsoft Teams Rooms in a hybrid environment with Exchange on premises and Microsoft Teams or Skype for Business Online.</span></span>
  
<span data-ttu-id="cab9c-105">조직에서 서비스를 혼합 하 여 온-프레미스 호스트와 일부 온라인 상태를 갖춘 경우 각 서비스가 호스팅되는 위치에 따라 구성이 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="cab9c-106">이 항목에서는 구내에 호스팅되는 Exchange를 사용 하 여 Microsoft 팀 회의실을 위한 하이브리드 배포에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted on premises.</span></span> <span data-ttu-id="cab9c-107">이러한 유형의 배포에는 다양 한 변형이 있기 때문에 모든 방법에 대 한 자세한 지침을 제공 하는 것은 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="cab9c-108">다음 프로세스는 여러 구성에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-108">The following process will work for many configurations.</span></span> <span data-ttu-id="cab9c-109">프로세스가 설정에 적합 하지 않은 경우에는 Windows PowerShell을 사용 하 여 여기에 명시 된 것과 다른 배포 옵션에 대 한 동일한 최종 결과를 얻을 것을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="cab9c-110">Microsoft는 새 사용자 계정을 만들거나, 호환 되는 Microsoft 팀 대화방 사용자 계정으로 전환 하는 데 도움을 주는 기존 리소스 계정이 있는지 확인 하는 데 도움이 되는 [SkypeRoomProvisioningScript. ps1을 제공 합니다.](https://go.microsoft.com/fwlink/?linkid=870105)</span><span class="sxs-lookup"><span data-stu-id="cab9c-110">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="cab9c-111">원하는 경우 아래 단계에 따라 Microsoft 팀 대화방 장치에서 사용할 계정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-111">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="cab9c-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cab9c-112">Requirements</span></span>

<span data-ttu-id="cab9c-113">Exchange와 함께 Microsoft 팀 대화방을 구내에 배포 하기 전에 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-113">Before you deploy Microsoft Teams Rooms with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="cab9c-114">자세한 내용은 [Microsoft 팀 공간 요구 사항을](requirements.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cab9c-114">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="cab9c-115">Exchange를 사용 하 여 Microsoft 팀 회의실을 구내에 배포 하는 경우 Active Directory 관리 도구를 사용 하 여 온-프레미스 도메인 계정의 전자 메일 주소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-115">If you are deploying Microsoft Teams Rooms with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="cab9c-116">이 계정은 Office 365와 동기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-116">This account will be synced to Office 365.</span></span> <span data-ttu-id="cab9c-117">다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-117">You will need to:</span></span>
  
- <span data-ttu-id="cab9c-118">계정을 만들고 Active Directory와 계정을 동기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-118">Create an account and synchronize the account with Active Directory.</span></span>

- <span data-ttu-id="cab9c-119">원격 사서함을 사용 하도록 설정 하 고 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-119">Enable the remote mailbox and set properties.</span></span>

- <span data-ttu-id="cab9c-120">Office 365 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-120">Assign an Office 365 license.</span></span>

- <span data-ttu-id="cab9c-121">비즈니스용 Skype 서버에서 디바이스 계정을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="cab9c-122">디바이스 계정을 사용 하도록 설정 하려면 환경이 다음 선행 조건을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>

  - <span data-ttu-id="cab9c-123">Office 365 요금제에는 비즈니스용 Skype Online (요금제 2) 이상이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Office 365 plan.</span></span> <span data-ttu-id="cab9c-124">요금제는 회의 기능을 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-124">The plan needs to support conferencing capability.</span></span>
  
  - - <span data-ttu-id="cab9c-125">Microsoft 팀 대화방에 대 한 전화 통신 서비스 공급자를 사용 하 여 엔터프라이즈 음성 (PSTN 전화 통신)이 필요한 경우 비즈니스용 Skype Online이 필요 합니다 (계획 3).</span><span class="sxs-lookup"><span data-stu-id="cab9c-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Microsoft Teams Rooms you need Skype for Business Online (Plan 3).</span></span>
  
  - - <span data-ttu-id="cab9c-126">테 넌 트 사용자에 게 Exchange 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-126">Your tenant users must have Exchange mailboxes.</span></span>
  
  - - <span data-ttu-id="cab9c-127">Microsoft 팀 대화방 계정에는 비즈니스용 Skype Online (계획 2) 또는 비즈니스용 Skype Online (계획 3) 라이선스가 필요 하지만 Exchange Online 라이선스는 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-127">Your Microsoft Teams Rooms account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>

- <span data-ttu-id="cab9c-128">Microsoft 팀 대화방 계정에 비즈니스용 Skype 서버 라이선스를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-128">Assign a Skype for Business Server license to your Microsoft Teams Rooms account.</span></span>

### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="cab9c-129">계정 만들기 및 Active Directory와 동기화</span><span class="sxs-lookup"><span data-stu-id="cab9c-129">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="cab9c-130">**Active Directory 사용자 및 컴퓨터** 도구에서 Microsoft 팀 대화방 계정이 생성 될 폴더 또는 조직 구성 단위를 마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 클릭 한 다음 **사용자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-130">In the **Active Directory Users and Computers** tool, right-click on the folder or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>

2. <span data-ttu-id="cab9c-131">이전 cmdlet의 표시 이름을 **전체 이름** 상자에 입력 하 고 별칭을 **사용자 로그온 이름** 상자에 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-131">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="cab9c-132">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-132">Click **Next**.</span></span>

3. <span data-ttu-id="cab9c-133">이 계정에 대 한 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-133">Type the password for this account.</span></span> <span data-ttu-id="cab9c-134">확인을 위해 암호를 다시 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-134">You'll need to retype it for verification.</span></span> <span data-ttu-id="cab9c-135">**암호 사용 기간 제한 없음** 확인란이 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-135">Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cab9c-136">**암호 사용 기간 제한 없음** 선택은 Microsoft 팀 대화방의 비즈니스용 Skype 서버에 대 한 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-136">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="cab9c-137">도메인 규칙에 따라 만료 되지 않는 암호가 금지 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-137">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="cab9c-138">그렇다면 각 Microsoft 팀 공간 디바이스 계정에 대 한 예외를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-138">If so, you'll need to create an exception for each Microsoft Teams Rooms device account.</span></span>
  
4. <span data-ttu-id="cab9c-139">계정을 만든 후 디렉터리 동기화를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-139">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="cab9c-140">완료 되 면 Microsoft 365 관리 센터의 사용자 페이지로 이동 하 여 이전 단계에서 만든 계정이 온라인에 병합 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-140">When it's complete, go to the users page in your Microsoft 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="cab9c-141">원격 사서함을 사용 하도록 설정 하 고 속성 설정</span><span class="sxs-lookup"><span data-stu-id="cab9c-141">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="cab9c-142">[Exchange 관리 셸을 열거나](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) [원격 PowerShell을 사용 하 여 exchange 서버에 연결](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-142">[Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) or [connect to your Exchange server using remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="cab9c-143">Exchange PowerShell에서 다음 명령을 실행 하 여 계정에 대 한 사서함 (사서함 사용이 허용 되는 계정)을 상자에 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-143">In Exchange PowerShell, crate a mailbox for the account (mailbox-enable the account)by running the following command:</span></span>

   ``` Powershell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   <span data-ttu-id="cab9c-144">자세한 구문 및 매개 변수 정보는 [사서함 사용](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cab9c-144">For detailed syntax and parameter information, see [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).</span></span>

3. <span data-ttu-id="cab9c-145">Exchange PowerShell에서 회의실 사서함에 다음 설정을 구성 하 여 모임 환경을 개선 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-145">In Exchange PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="cab9c-146">AutomateProcessing: AutoAccept (모임 이끌이는 사용자 간섭 없이 직접 회의실 예약 결정을 받습니다: 무료 = 수락; 사용 중 = 거절).</span><span class="sxs-lookup"><span data-stu-id="cab9c-146">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="cab9c-147">AddOrganizerToSubject: $false (모임 이끌이는 모임 요청의 제목에 추가 되지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="cab9c-147">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="cab9c-148">Deletecomdea: $false (받는 모임 요청의 메시지 본문에 있는 텍스트는 유지 합니다.)</span><span class="sxs-lookup"><span data-stu-id="cab9c-148">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="cab9c-149">DeleteSubject: $false (들어오는 모임 요청의 주제를 보관 합니다.)</span><span class="sxs-lookup"><span data-stu-id="cab9c-149">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="cab9c-150">RemovePrivateProperty: $false (원래 모임 이끌이가 보낸 개인 플래그가 지정 된 대로 유지 되도록 합니다.)</span><span class="sxs-lookup"><span data-stu-id="cab9c-150">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="cab9c-151">AddAdditionalResponse: $true (AdditionalResponse 매개 변수에서 지정한 텍스트가 모임 요청에 추가 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="cab9c-151">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="cab9c-152">AdditionalResponse: "Skype 회의실입니다!"</span><span class="sxs-lookup"><span data-stu-id="cab9c-152">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="cab9c-153">(모임 요청에 추가 하는 추가 텍스트입니다.)</span><span class="sxs-lookup"><span data-stu-id="cab9c-153">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="cab9c-154">이 예제에서는 Rigel-01 이라는 대화방 사서함에서 이러한 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-154">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="cab9c-155">자세한 구문 및 매개 변수 정보는 [설정-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cab9c-155">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

### <a name="assign-an-office-365-license"></a><span data-ttu-id="cab9c-156">Office 365 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="cab9c-156">Assign an Office 365 license</span></span>

1. <span data-ttu-id="cab9c-157">Azure Active Directory에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-157">Connect to Azure Active Directory.</span></span> <span data-ttu-id="cab9c-158">Active Directory에 대 한 자세한 내용은 [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cab9c-158">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="cab9c-159">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) 는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-159">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

2. <span data-ttu-id="cab9c-160">장치 계정에 유효한 Office 365 라이선스가 필요 하거나 Exchange 및 Microsoft 팀이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-160">The device account needs to have a valid Office 365 license, or Exchange and Microsoft Teams will not work.</span></span> <span data-ttu-id="cab9c-161">라이선스가 있는 경우 사용 위치를 디바이스 계정에 할당 해야 하며,이는 계정에 사용할 수 있는 라이선스 Sku를 결정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-161">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="cab9c-162">사용할 수 있는`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="cab9c-162">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="cab9c-163">사용 가능한 Sku 목록을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-163">to retrieve a list of available SKUs.</span></span>

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. <span data-ttu-id="cab9c-164">다음으로, 다음을 사용 하 여 라이선스를 추가할 수 있습니다.`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="cab9c-164">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense --> <span data-ttu-id="cab9c-165">은.</span><span class="sxs-lookup"><span data-stu-id="cab9c-165">cmdlet.</span></span> <span data-ttu-id="cab9c-166">이 경우 $strLicense는 사용자에 게 표시 되는 SKU 코드입니다 (예: contoso: STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="cab9c-166">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

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

   <span data-ttu-id="cab9c-167">자세한 지침은 [Office 365 PowerShell을 사용 하 여 사용자 계정에 라이선스 할당](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cab9c-167">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="enable-the-device-account"></a><span data-ttu-id="cab9c-168">디바이스 계정 사용</span><span class="sxs-lookup"><span data-stu-id="cab9c-168">Enable the device account</span></span>

<span data-ttu-id="cab9c-169">비즈니스용 skype Online PowerShell은 Microsoft 팀과 비즈니스용 Skype Online에 대 한 서비스를 관리 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-169">Skype for Business Online PowerShell is used to manage services for both Microsoft Teams and Skype for Business Online.</span></span>

1. <span data-ttu-id="cab9c-170">PC에서 원격 Windows PowerShell 세션을 다음과 같이 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-170">Create a remote Windows PowerShell session from a PC as follows:</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="cab9c-171">계정의 SIP 주소 받기:</span><span class="sxs-lookup"><span data-stu-id="cab9c-171">Obtain SIP address of the account:</span></span>

  ``` Powershell
   $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
   ```

3. <span data-ttu-id="cab9c-172">Microsoft 팀 대화방 계정을 사용 하도록 설정 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-172">To enable your Microsoft Teams Rooms account, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="cab9c-173">환경에서 RegistrarPool 매개 변수에 어떤 값을 사용 해야 하는지 확실 하지 않은 경우이 명령을 사용 하 여 기존 사용자의 값을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-173">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing user using this command:</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="cab9c-174">Microsoft 팀원에 게 라이선스 할당 공간 계정</span><span class="sxs-lookup"><span data-stu-id="cab9c-174">Assign a license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="cab9c-175">테 넌 트 관리자로 로그인 하 고, Office 365 관리 포털을 열고, 관리 앱을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-175">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
2. <span data-ttu-id="cab9c-176">**사용자 및 그룹** 을 클릭 한 다음 **사용자 추가, 암호 다시 설정**등을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-176">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="cab9c-177">Microsoft 팀 대화방 계정을 클릭 한 다음 펜 아이콘을 클릭 하 여 계정 정보를 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-177">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="cab9c-178">**라이선스**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-178">Click **Licenses**.</span></span>
5. <span data-ttu-id="cab9c-179">라이선스 **할당**에서 라이선스 및 엔터프라이즈 음성 요구 사항에 따라 비즈니스용 Skype (계획 2) 또는 비즈니스용 Skype (계획 3)를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-179">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="cab9c-180">Microsoft 팀 방에 Enterprise Voice를 사용 하려면 요금제 3 라이선스를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-180">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="cab9c-181">**저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-181">Click **Save**.</span></span>

<span data-ttu-id="cab9c-182">유효성 검사를 위해 모든 클라이언트를 사용 하 여이 계정에 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cab9c-182">For validation, you should be able to use any client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cab9c-183">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cab9c-183">See also</span></span>

[<span data-ttu-id="cab9c-184">Microsoft 팀 대화방 계정 구성</span><span class="sxs-lookup"><span data-stu-id="cab9c-184">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="cab9c-185">Microsoft 팀 회의실 계획</span><span class="sxs-lookup"><span data-stu-id="cab9c-185">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)
  
[<span data-ttu-id="cab9c-186">Microsoft 팀 대화방 배포</span><span class="sxs-lookup"><span data-stu-id="cab9c-186">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="cab9c-187">Microsoft 팀 대화방 콘솔 구성</span><span class="sxs-lookup"><span data-stu-id="cab9c-187">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="cab9c-188">Microsoft 팀 대화방 관리</span><span class="sxs-lookup"><span data-stu-id="cab9c-188">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
