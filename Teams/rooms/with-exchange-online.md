---
title: Exchange Online을 사용 하 여 Microsoft 팀 대화방 배포
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Exchange Online을 사용 하 여 Microsoft 팀 회의실을 배포 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.
ms.openlocfilehash: fc403e2553fce157737b1bdda75c821563e6b0dd
ms.sourcegitcommit: 9bead87a7f4c4e71f19f8980e9dce2b979735055
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2020
ms.locfileid: "41269151"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a><span data-ttu-id="bd782-103">Exchange Online을 사용 하 여 Microsoft 팀 대화방 배포</span><span class="sxs-lookup"><span data-stu-id="bd782-103">Deploy Microsoft Teams Rooms with Exchange Online</span></span>

<span data-ttu-id="bd782-104">Exchange Online과 비즈니스용 Skype Server 온-프레미스를 사용 하 여 Microsoft 팀 회의실을 배포 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bd782-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="bd782-105">조직에서 서비스를 혼합 하 여 온-프레미스 호스트와 일부 온라인 상태를 갖춘 경우 각 서비스가 호스팅되는 위치에 따라 구성이 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="bd782-106">이 항목에서는 Exchange에서 온라인으로 호스팅되는 Microsoft 팀 회의실에 대 한 하이브리드 배포에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted online.</span></span> <span data-ttu-id="bd782-107">이러한 유형의 배포에는 다양 한 변형이 있기 때문에 모든 방법에 대 한 자세한 지침을 제공 하는 것은 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="bd782-108">다음 프로세스는 여러 구성에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-108">The following process will work for many configurations.</span></span> <span data-ttu-id="bd782-109">프로세스가 설정에 적합 하지 않은 경우에는 Windows PowerShell을 사용 하 여 여기에 명시 된 것과 다른 배포 옵션에 대 한 동일한 최종 결과를 얻을 것을 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="bd782-110">사용자 계정을 설정 하는 가장 쉬운 방법은 원격 Windows PowerShell을 사용 하 여 구성 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="bd782-111">Microsoft는 새 사용자 계정을 만들거나, 호환 되는 Microsoft 팀 대화방 사용자 계정으로 전환 하는 데 도움을 주는 기존 리소스 계정이 있는지 확인 하는 데 도움이 되는 [SkypeRoomProvisioningScript. ps1을 제공 합니다.](https://go.microsoft.com/fwlink/?linkid=870105)</span><span class="sxs-lookup"><span data-stu-id="bd782-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="bd782-112">원하는 경우 아래 단계에 따라 Microsoft 팀 대화방 장치에서 사용할 계정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-112">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="bd782-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bd782-113">Requirements</span></span>

<span data-ttu-id="bd782-114">Exchange Online을 사용 하 여 Microsoft 팀 회의실을 배포 하기 전에 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-114">Before you deploy Microsoft Teams Rooms with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="bd782-115">자세한 내용은 [Microsoft 팀 공간 요구 사항을](requirements.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bd782-115">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="bd782-116">Exchange Online을 사용 하 여 Microsoft 팀 대화방을 배포 하려면 아래 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="bd782-116">To deploy Microsoft Teams Rooms with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="bd782-117">연결 된 cmdlet을 실행할 수 있는 권한이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-117">Be sure you have the right permissions to run the associated cmdlets.</span></span> 

   > [!NOTE]
   >  <span data-ttu-id="bd782-118">이 섹션 (예: MsolUser)의 [Windows PowerShell 용 Azure Active Directory 모듈](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) 은 Microsoft 팀 회의실 장치에 대 한 계정 설정에서 테스트를 거쳤습니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-118">The [Azure Active Directory Module for Windows PowerShell cmdlets](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) in this section (for example,  Set-MsolUser) have been tested in setting up accounts for Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="bd782-119">그러나이 특정 시나리오에서 테스트 하지 않은 경우에도 다른 cmdlet이 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-119">It's possible that other cmdlets may work, however, they haven't been tested in this specific scenario.</span></span>
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="bd782-120">계정 만들기 및 Exchange 속성 설정</span><span class="sxs-lookup"><span data-stu-id="bd782-120">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="bd782-121">PC에서 원격 Windows PowerShell 세션을 시작 하 고 아래와 같이 Exchange Online에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-121">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>

``` Powershell
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
Import-PSSession $Session -DisableNameChecking
```

2. <span data-ttu-id="bd782-122">세션을 설정한 후 새 사서함을 만들고이를 RoomMailboxAccount 사용 하도록 설정 하거나 기존 회의실 사서함에 대 한 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-122">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="bd782-123">이렇게 하면 계정이 Microsoft 팀 방에 인증 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-123">This will allow the account to authenticate into Microsoft Teams Rooms.</span></span>

   <span data-ttu-id="bd782-124">기존 리소스 사서함을 변경 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-124">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="bd782-125">새 리소스 사서함을 만드는 경우:</span><span class="sxs-lookup"><span data-stu-id="bd782-125">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="bd782-126">모임 환경을 개선 하려면 다음과 같이 사용자 계정에 Exchange 속성을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-126">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```



### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="bd782-127">온-프레미스 도메인 계정에 대 한 전자 메일 주소 추가</span><span class="sxs-lookup"><span data-stu-id="bd782-127">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="bd782-128">**Active Directory 사용자 및 컴퓨터 광고** 도구에서 Microsoft 팀 대화방 계정이 생성 될 조직 구성 단위 또는 컨테이너를 마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 클릭 한 다음 **사용자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-128">In **Active Directory Users and Computers AD** tool, right-click on the container or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>
2. <span data-ttu-id="bd782-129">이전 cmdlet ((사서함 또는 새 사서함)의 표시 이름 (-Id)을 **전체 이름** 상자에 입력 하 고 별칭을 **사용자 로그온 이름** 상자에 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-129">Type the display name (- Identity ) from the prior cmdlet (Set-Mailbox or New-Mailbox) into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="bd782-130">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-130">Click **Next**.</span></span>
3. <span data-ttu-id="bd782-131">이 계정에 대 한 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-131">Type the password for this account.</span></span> <span data-ttu-id="bd782-132">확인을 위해 암호를 다시 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-132">You'll need to retype it for verification.</span></span> <span data-ttu-id="bd782-133">**암호 사용 기간 제한 없음** 확인란이 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-133">Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bd782-134">**암호 사용 기간 제한 없음** 선택은 Microsoft 팀 대화방의 비즈니스용 Skype 서버에 대 한 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-134">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="bd782-135">도메인 규칙에 따라 만료 되지 않는 암호가 금지 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-135">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="bd782-136">그렇다면 각 Microsoft 팀 대화방 사용자 계정에 대 한 예외를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-136">If so, you'll need to create an exception for each Microsoft Teams Rooms user account.</span></span>
  
4. <span data-ttu-id="bd782-137">**마침을** 클릭 하 여 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-137">Click **Finish** to create the account.</span></span>
5. <span data-ttu-id="bd782-138">계정을 만든 후 디렉터리 동기화를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-138">After you have created the account, run a directory synchronization.</span></span> <span data-ttu-id="bd782-139">PowerShell에서 [Set-MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) 를 사용 하 여이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-139">This can be accomplished by using [Set-MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) in PowerShell.</span></span> <span data-ttu-id="bd782-140">이 작업이 완료 되 면 사용자 페이지로 이동 하 여 이전 단계에서 만든 두 계정이 병합 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-140">When that is complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

### <a name="assign-an-office-365-license"></a><span data-ttu-id="bd782-141">Office 365 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="bd782-141">Assign an Office 365 license</span></span>

1. <span data-ttu-id="bd782-142">먼저 Azure AD에 연결 하 여 일부 계정 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-142">First, connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="bd782-143">이 cmdlet을 실행 하 여 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-143">You can run this cmdlet to connect.</span></span> <span data-ttu-id="bd782-144">Active Directory에 대 한 자세한 내용은 [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bd782-144">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="bd782-145">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) 는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-145">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

  ``` PowerShell
 Connect-MsolService -Credential $cred
  ```
<!--   ``` Powershell
   Connect-AzureAD -Credential $cred
   ``` -->

2. <span data-ttu-id="bd782-146">사용자 계정에는 비즈니스용 Exchange 및 비즈니스용 Skype 서버를 사용할 수 있도록 유효한 Office 365 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-146">The user account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="bd782-147">라이선스가 있는 경우 사용 위치를 사용자 계정에 할당 해야 하며,이는 계정에 사용할 수 있는 라이선스 Sku를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-147">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="bd782-148">다음 단계에서 과제를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-148">You'll make the assignment in a following step.</span></span>
3. <span data-ttu-id="bd782-149">다음으로 다음을 사용 합니다.`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="bd782-149">Next, use `Get-MsolAccountSku`</span></span> <!--Get-AzureADSubscribedSku--> <span data-ttu-id="bd782-150">Office 365 테 넌 트에 대해 사용 가능한 Sku 목록을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-150">to retrieve a list of available SKUs for your Office 365 tenant.</span></span>
4. <span data-ttu-id="bd782-151">Sku를 나열 하면 다음을 사용 하 여 라이선스를 추가할 수 있습니다.`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="bd782-151">Once you list out the SKUs, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense--> <span data-ttu-id="bd782-152">은.</span><span class="sxs-lookup"><span data-stu-id="bd782-152">cmdlet.</span></span> <span data-ttu-id="bd782-153">이 경우 $strLicense는 사용자에 게 표시 되는 SKU 코드입니다 (예: contoso: STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="bd782-153">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span> 

  ```PowerShell
    Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```
<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a><span data-ttu-id="bd782-154">비즈니스용 Skype 서버에서 사용자 계정 사용</span><span class="sxs-lookup"><span data-stu-id="bd782-154">Enable the user account with Skype for Business Server</span></span>

1. <span data-ttu-id="bd782-155">PC에서 원격 Windows PowerShell 세션을 다음과 같이 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-155">Create a remote Windows PowerShell session from a PC as follows:</span></span>

    ``` Powershell
    Import-Module SkypeOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="bd782-156">비즈니스용 Skype Server에 대해 Microsoft 팀 대화방 계정을 사용 하도록 설정 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-156">To enable your Microsoft Teams Rooms account for Skype for Business Server, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="bd782-157">환경에서 RegistrarPool 매개 변수에 어떤 값을 사용 해야 하는지 확실 하지 않은 경우이 명령을 사용 하 여 기존 비즈니스용 Skype Server 사용자의 값을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-157">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="bd782-158">Microsoft 팀 대화방 계정에 비즈니스용 Skype 서버 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="bd782-158">Assign a Skype for Business Server license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="bd782-159">테 넌 트 관리자로 로그인 하 고, Office 365 관리 포털을 열고, 관리 앱을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-159">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
2. <span data-ttu-id="bd782-160">**사용자 및 그룹** 을 클릭 한 다음 **사용자 추가, 암호 다시 설정**등을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-160">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="bd782-161">Microsoft 팀 대화방 계정을 클릭 한 다음 펜 아이콘을 클릭 하 여 계정 정보를 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-161">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="bd782-162">**라이선스**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-162">Click **Licenses**.</span></span>
5. <span data-ttu-id="bd782-163">라이선스 **할당**에서 라이선스 및 엔터프라이즈 음성 요구 사항에 따라 비즈니스용 Skype (계획 2) 또는 비즈니스용 Skype (계획 3)를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-163">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="bd782-164">Microsoft 팀 방에 Enterprise 음성을 사용 하려면 요금제 3 라이선스를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-164">You'll have to use a Plan 3 license if you want to use Enterprise Voice on Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="bd782-165">**저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-165">Click **Save**.</span></span>

<span data-ttu-id="bd782-166">유효성 검사를 위해 비즈니스용 Skype 클라이언트를 사용 하 여이 계정에 로그인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd782-166">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bd782-167">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd782-167">See also</span></span>

[<span data-ttu-id="bd782-168">Microsoft 팀 대화방 계정 구성</span><span class="sxs-lookup"><span data-stu-id="bd782-168">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="bd782-169">Microsoft 팀 회의실 계획</span><span class="sxs-lookup"><span data-stu-id="bd782-169">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="bd782-170">Microsoft 팀 대화방 배포</span><span class="sxs-lookup"><span data-stu-id="bd782-170">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="bd782-171">Microsoft 팀 대화방 콘솔 구성</span><span class="sxs-lookup"><span data-stu-id="bd782-171">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="bd782-172">Microsoft 팀 대화방 관리</span><span class="sxs-lookup"><span data-stu-id="bd782-172">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
