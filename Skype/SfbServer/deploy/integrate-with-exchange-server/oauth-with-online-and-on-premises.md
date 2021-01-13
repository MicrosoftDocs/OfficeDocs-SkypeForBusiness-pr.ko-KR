---
title: 비즈니스용 Skype Online과 Exchange 서버 간의 통합
ms.reviewer: cbland
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: Exchange온-프레미스와 비즈니스용 Skype Online 간에 OAuth 인증을 구성하면 기능 지원에 설명된 비즈니스용 Skype 및 Exchange 통합 기능을 사용할 수 있습니다.
ms.openlocfilehash: ac8bfe2f30e813e47a0256a68e4e81852d5bae68
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833978"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a><span data-ttu-id="297a4-103">비즈니스용 Skype Online과 비즈니스용 Skype 간의 통합 및 OAuth Exchange Server</span><span class="sxs-lookup"><span data-stu-id="297a4-103">Configure Integration and OAuth between Skype for Business Online and Exchange Server</span></span> 

<span data-ttu-id="297a4-104">Exchange 서버와 비즈니스용 Skype Online 간의 통합을 구성하면 기능 지원에 설명된 비즈니스용 Skype 및 Exchange 통합 [기능을 사용할 수 있습니다.](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)</span><span class="sxs-lookup"><span data-stu-id="297a4-104">Configuring integration between Exchange server and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>

<span data-ttu-id="297a4-105">이 항목은 2013~2019년 Exchange Server 통합에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-105">This topic applies to integration with Exchange Server 2013 through 2019.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="297a4-106">시작하기 전에 알아야 할 내용</span><span class="sxs-lookup"><span data-stu-id="297a4-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="297a4-107">이 작업의 예상 완료 시간: 15분</span><span class="sxs-lookup"><span data-stu-id="297a4-107">Estimated time to complete this task: 15 minutes</span></span>

-  <span data-ttu-id="297a4-108">이러한 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="297a4-109">필요한 사용 권한을 표시하려면 Exchange 및 셸 인프라 [사용 권한 항목을 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=746511)</span><span class="sxs-lookup"><span data-stu-id="297a4-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) topic.</span></span>

- <span data-ttu-id="297a4-110">이 항목의 절차에 적용할 수 있는 바로 가기 키에 대한 자세한 내용은 [Exchange 관리 센터의 바로 가기 키]( https://go.microsoft.com/fwlink/p/?LinkId=746512)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="297a4-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>

- <span data-ttu-id="297a4-111">호환성에 대한 자세한 내용은 [Office 앱과의 비즈니스용 Skype 호환성을 참조하세요.](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office)</span><span class="sxs-lookup"><span data-stu-id="297a4-111">For information about compatibility, see [Skype for Business compatibility with Office apps](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office).</span></span>

## <a name="configure-integration-between-exchange-server-and-o365"></a><span data-ttu-id="297a4-112">O365와 O365 Exchange Server 통합 구성</span><span class="sxs-lookup"><span data-stu-id="297a4-112">Configure integration between Exchange Server and O365</span></span>

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a><span data-ttu-id="297a4-113">1단계: OAuth 인증과 O365 Exchange Server 구성</span><span class="sxs-lookup"><span data-stu-id="297a4-113">Step 1: Configure OAuth authentication between Exchange Server and O365</span></span>

<span data-ttu-id="297a4-114">다음 문서의 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-114">Perform the steps in the following article:</span></span>

[<span data-ttu-id="297a4-115">Exchange 및 Exchange Online 조직 간의 OAuth 인증 구성</span><span class="sxs-lookup"><span data-stu-id="297a4-115">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a><span data-ttu-id="297a4-116">2단계: 비즈니스용 Skype Online 파트너 응용 프로그램에 대한 새 메일 사용자 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="297a4-116">Step 2: Create a new Mail User account for the Skype for Business Online Partner Application</span></span>

<span data-ttu-id="297a4-117">이 단계는 Exchange 서버에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-117">This step is done on the Exchange server.</span></span> <span data-ttu-id="297a4-118">메일 사용자를 만들고 적절한 관리 역할 권한을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-118">It will create a mail user and assign it the appropriate management role rights.</span></span> <span data-ttu-id="297a4-119">이 계정은 다음 단계에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-119">This account will then be used in the next step.</span></span>

<span data-ttu-id="297a4-120">Exchange 조직에 대해 확인된 도메인을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-120">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="297a4-121">이 도메인은 기본 SMTP 도메인으로 사용되는 도메인과 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-121">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="297a4-122">이 도메인은 다음 \<your Verified Domain\> 절차에서 참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-122">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="297a4-123">또한 도메인 \<DomainControllerFQDN\> 컨트롤러의 FQDN을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-123">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span>

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="297a4-124">이 명령은 새 메일 사용자를 주소 목록에서 숨길 것입니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-124">This command will hide the new mail user from address lists.</span></span>

```powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="297a4-125">다음 두 명령은 UserApplication 및 ArchiveApplication 관리 역할을 이 새 계정에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-125">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>

```powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a><span data-ttu-id="297a4-126">3단계: 비즈니스용 Skype Online에 대한 파트너 응용 프로그램 만들기 및 사용</span><span class="sxs-lookup"><span data-stu-id="297a4-126">Step 3: Create and enable a Partner Application for Skype for Business Online</span></span> 

<span data-ttu-id="297a4-127">새 파트너 응용 프로그램을 만들고 방금 만든 계정을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-127">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="297a4-128">온-프레미스 Exchange 조직의 Exchange PowerShell에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-128">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a><span data-ttu-id="297a4-129">4단계: 프레미스 인증 인증서 내보내기</span><span class="sxs-lookup"><span data-stu-id="297a4-129">Step 4: Export the on-premises authorization certificate</span></span>

<span data-ttu-id="297a4-130">PowerShell 스크립트를 실행하여 다음 단계에서 비즈니스용 Skype Online 조직으로 가져오는 인증 인증서를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-130">Run a PowerShell script to export the on-premises authorization certificate, which you will import to your Skype for Business Online organization in the next step.</span></span>

<span data-ttu-id="297a4-131">ExportAuthCert.ps1과 같이 이름을 지정한 PowerShell 스크립트 파일에 다음 텍스트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-131">Save the following text to a PowerShell script file named, for example, ExportAuthCert.ps1.</span></span>

```powershell
$thumbprint = (Get-AuthConfig).CurrentCertificateThumbprint
if((test-path $env:SYSTEMDRIVE\OAuthConfig) -eq $false)
{
md $env:SYSTEMDRIVE\OAuthConfig
}
cd $env:SYSTEMDRIVE\OAuthConfig
$oAuthCert = (dir Cert:\LocalMachine\My) | where {$_.Thumbprint -match $thumbprint}
$certType = [System.Security.Cryptography.X509Certificates.X509ContentType]::Cert
$certBytes = $oAuthCert.Export($certType)
$CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
[System.IO.File]::WriteAllBytes($CertFile, $certBytes)
```

<span data-ttu-id="297a4-132">On-premises Exchange 조직의 Exchange PowerShell에서 방금 만든 PowerShell 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-132">In Exchange PowerShell in your on-premises Exchange organization, run the PowerShell script that you just created.</span></span> <span data-ttu-id="297a4-133">예: .\ExportAuthCert.ps1</span><span class="sxs-lookup"><span data-stu-id="297a4-133">For example: .\ExportAuthCert.ps1</span></span>

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a><span data-ttu-id="297a4-134">5단계: Azure Active Directory ACS에 On-premises 권한 부여 인증서 업로드</span><span class="sxs-lookup"><span data-stu-id="297a4-134">Step 5: Upload the on-premises authorization certificate to Azure Active Directory ACS</span></span>

<span data-ttu-id="297a4-135">다음으로, Windows PowerShell 사용하여 이전 단계에서 내보냈던 인증 인증서를 Azure Active Directory ACS(액세스 제어 서비스)에 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-135">Next, use Windows PowerShell to upload the on-premises authorization certificate that you exported in the previous step to Azure Active Directory Access Control Services (ACS).</span></span> <span data-ttu-id="297a4-136">이렇게하려면 cmdlet에 대한 Azure Active Directory Windows PowerShell 이미 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-136">To do this, the Azure Active Directory Module for Windows PowerShell cmdlets must already be installed.</span></span> <span data-ttu-id="297a4-137">설치되지 않은 경우 Azure Active Directory 모듈을 설치하는 [https://aka.ms/aadposh](https://aka.ms/aadposh) Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="297a4-137">If it's not installed, go to [https://aka.ms/aadposh](https://aka.ms/aadposh) to install the Azure Active Directory Module for Windows PowerShell.</span></span> <span data-ttu-id="297a4-138">Azure Active Directory 모듈 for Windows PowerShell 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-138">Complete the following steps after the Azure Active Directory Module for Windows PowerShell is installed.</span></span>

1. <span data-ttu-id="297a4-139">Azure **AD** cmdlet이 Windows PowerShell 응용 프로그램 Windows PowerShell 열려면 Azure Active Directory 모듈을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-139">Click the **Azure Active Directory Module for Windows PowerShell** shortcut to open a Windows PowerShell workspace that has the Azure AD cmdlets installed.</span></span> <span data-ttu-id="297a4-140">이 단계의 모든 명령은 Azure Active Directory 콘솔용 Windows PowerShell 사용하여 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-140">All commands in this step will be run using the Windows PowerShell for Azure Active Directory console.</span></span>

2. <span data-ttu-id="297a4-141">다음 텍스트를 이름이 지정한 PowerShell 스크립트 파일에  `UploadAuthCert.ps1` 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-141">Save the following text to a PowerShell script file named, for example,  `UploadAuthCert.ps1`.</span></span>

   ```powershell
   Connect-MsolService;
   Import-Module msonlineextended;
   $CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
   $objFSO = New-Object -ComObject Scripting.FileSystemObject;
   $CertFile = $objFSO.GetAbsolutePathName($CertFile);
   $cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
   $cer.Import($CertFile);
   $binCert = $cer.GetRawCertData();
   $credValue = [System.Convert]::ToBase64String($binCert);
   $ServiceName = "00000004-0000-0ff1-ce00-000000000000";
   $p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName
   New-MsolServicePrincipalCredential -AppPrincipalId $p.AppPrincipalId -Type asymmetric -Usage Verify -Value $credValue
   ```

3. <span data-ttu-id="297a4-142">이전 단계에서 만든 PowerShell 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-142">Run the PowerShell script that you created in the previous step.</span></span> <span data-ttu-id="297a4-143">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-143">For example:  `.\UploadAuthCert.ps1`</span></span>

4. <span data-ttu-id="297a4-144">스크립트를 시작하면 자격 증명 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-144">After you start the script, a credentials dialog box is displayed.</span></span> <span data-ttu-id="297a4-145">Microsoft Online Azure AD 조직의 테넌트 관리자 계정에 대한 자격 증명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-145">Enter the credentials for the tenant administrator account of your Microsoft Online Azure AD organization.</span></span> <span data-ttu-id="297a4-146">스크립트를 실행한 후 Azure AD 세션에 대한 Windows PowerShell 열어 두면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-146">After running the script, leave the Windows PowerShell for Azure AD session open.</span></span> <span data-ttu-id="297a4-147">이 세션을 사용하여 다음 단계에서 PowerShell 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-147">You will use this to run a PowerShell script in the next step.</span></span>

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a><span data-ttu-id="297a4-148">6단계: 인증서가 비즈니스용 Skype 서비스 사용자에 업로드 났는지 확인</span><span class="sxs-lookup"><span data-stu-id="297a4-148">Step 6: Verify that the Certificate has Uploaded to the Skype for Business Service Principal</span></span>
1. <span data-ttu-id="297a4-149">Azure Active Directory에서 열고 인증된 PowerShell에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-149">In the PowerShell opened and authenticated to Azure Active Directory, run the following</span></span>
```powershell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. <span data-ttu-id="297a4-150">ReturnKeyValues를 입력하라는 메시지가 표시될 때 Enter 키 누르기</span><span class="sxs-lookup"><span data-stu-id="297a4-150">Press Enter when prompted for ReturnKeyValues</span></span>
3. <span data-ttu-id="297a4-151">Exchange Oauth 인증서 시작 및 종료 날짜와 일치하는 시작 날짜 및 종료 데이터가 나열된 키가 표시되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="297a4-151">Confirm you see a key listed with start date and end data that matches your Exchange Oauth certificate start and end dates</span></span>

### <a name="verify-your-success"></a><span data-ttu-id="297a4-152">성공 확인</span><span class="sxs-lookup"><span data-stu-id="297a4-152">Verify your success</span></span>

<span data-ttu-id="297a4-153">일부 기능이 성공적으로 작동하고 있는지 확인하여 구성이 올바른지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-153">Verify that the configuration is correct by verifying some of the features are working successfully.</span></span> 

1. <span data-ttu-id="297a4-154">Hybrid Exchange Server 구성의 조직에서 Cloud Voicemail 서비스가 있는 비즈니스용 Skype 사용자가 음성 Exchange Server 성공적으로 변경할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-154">Confirm that Skype for Business users with Cloud Voicemail service, in an organization with a Hybrid Exchange Server configuration, can successfully change their voicemail greetings.</span></span>

2. <span data-ttu-id="297a4-155">모바일 클라이언트의 대화 기록이 Outlook 대화 기록 폴더에 표시되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-155">Confirm conversation history for mobile clients is visible in the Outlook Conversation History folder.</span></span>

3. <span data-ttu-id="297a4-156">보관된 채팅 메시지가 [EWSEditor를](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/)사용하여 제거 폴더의 사용자 사서함에 보관되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-156">Confirm that archived chat messages are deposited in the user's on-premises mailbox in the Purges folder using [EWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/).</span></span>

<span data-ttu-id="297a4-157">또는 트래픽을 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-157">Alternately, look at your traffic.</span></span> <span data-ttu-id="297a4-158">OAuth 핸드세이크의 트래픽은 실제로는 뚜렷하며 기본 인증처럼 보이지 않습니다. 특히, 전달되는 토큰에서 00000004-0000-0ff1-ce00-000000000000@(@기호 앞에 / 포함)과 같은 발급자 트래픽이 표시되기 시작할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-158">The traffic in an OAuth handshake is really distinctive (and doesn't look like Basic authentication), particularly around realms, where you’ll begin to see issuer traffic that looks like this: 00000004-0000-0ff1-ce00-000000000000@ (sometimes with a / before the @ sign), in the tokens that are being passed.</span></span> <span data-ttu-id="297a4-159">OAuth의 지점인 사용자 이름이나 암호가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-159">You won’t see a username or password, which is the point of OAuth.</span></span> <span data-ttu-id="297a4-160">하지만 'Office' 발급자( 이 경우 '4'는 비즈니스용 Skype 및 구독의 전제가 됩니다.)가 표시될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-160">But you will see   the ‘Office’ issuer – in this case ‘4’ is Skype for Business – and the realm of your subscription.</span></span>

<span data-ttu-id="297a4-161">OAuth를 성공적으로 사용하고 있는지 확인하려는 경우 예상할 예상과 트래픽의 모양을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-161">If you want to be sure you’re successfully using OAuth, make certain you know what to expect and know what the traffic should look like.</span></span> <span data-ttu-id="297a4-162">다음은 [](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)Microsoft 응용 프로그램의 [OAuth](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) 트래픽을 예로 들어 보겠습니다(새로 고침 토큰을 사용하지 않는 경우 읽기에 매우 유용), OAuth JWT(JSON 웹 토큰)를 살펴 볼 수 있는 Fiddler 확장이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-162">So [here’s what to expect](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), here’s a pretty standard [example of OAuth traffic in a Microsoft application](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (really helpful to read, though it doesn't use Refresh tokens), and there are Fiddler extensions that will let you look into your OAuth JWT (JSON Web Token).</span></span>

<span data-ttu-id="297a4-163">다음은 하나를 [설정하는](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/)예이지만 이 프로세스를 진행하는 데 원하는 네트워크 추적 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="297a4-163">Here's an [example of setting one up](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), but you can use any network tracing tool you like to undertake this process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="297a4-164">관련 항목</span><span class="sxs-lookup"><span data-stu-id="297a4-164">Related topics</span></span>

[<span data-ttu-id="297a4-165">Exchange 및 Exchange Online 조직 간의 OAuth 인증 구성</span><span class="sxs-lookup"><span data-stu-id="297a4-165">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
