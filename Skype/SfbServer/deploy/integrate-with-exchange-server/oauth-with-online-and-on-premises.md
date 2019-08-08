---
title: 비즈니스용 Skype Online 및 Exchange server의 통합
ms.reviewer: cbland
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: 온-프레미스 Exchange와 비즈니스용 Skype Online 간에 OAuth 인증을 구성 하면 기능 지원에서 설명 하는 비즈니스용 Skype 및 Exchange 통합 기능을 사용할 수 있습니다.
ms.openlocfilehash: 3c896e8b430276e5bb48bc425425292a382a1021
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244222"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a><span data-ttu-id="b6f29-103">비즈니스용 Skype Online 및 Exchange Server 간 통합 및 OAuth 구성</span><span class="sxs-lookup"><span data-stu-id="b6f29-103">Configure Integration and OAuth between Skype for Business Online and Exchange Server</span></span> 

<span data-ttu-id="b6f29-104">Exchange server와 비즈니스용 Skype Online의 통합을 구성 하면 [기능 지원](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)에서 설명 하는 비즈니스용 Skype 및 Exchange 통합 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-104">Configuring integration between Exchange server and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>

<span data-ttu-id="b6f29-105">이 항목은 Exchange Server 2013 ~ 2019과의 통합에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-105">This topic applies to integration with Exchange Server 2013 through 2019.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b6f29-106">시작 하기 전에 알아야 할 사항</span><span class="sxs-lookup"><span data-stu-id="b6f29-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b6f29-107">이 작업을 완료 하는 데 예상 되는 시간: 15 분</span><span class="sxs-lookup"><span data-stu-id="b6f29-107">Estimated time to complete this task: 15 minutes</span></span>

-  <span data-ttu-id="b6f29-108">이 절차 또는 절차를 수행 하기 전에 사용 권한을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="b6f29-109">필요한 사용 권한을 확인 하려면 [Exchange 및 셸 인프라 사용 권한](https://go.microsoft.com/fwlink/p/?LinkId=746511) 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b6f29-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) topic.</span></span>

- <span data-ttu-id="b6f29-110">이 항목의 절차에 적용 될 수 있는 바로 가기 키에 대 한 자세한 내용은 [Exchange 관리 센터의 바로 가기 키]( https://go.microsoft.com/fwlink/p/?LinkId=746512)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b6f29-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>

- <span data-ttu-id="b6f29-111">호환성에 대 한 자세한 내용은 [Office 앱과 비즈니스용 Skype 호환성](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b6f29-111">For information about compatibility, see [Skype for Business compatibility with Office apps](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office).</span></span>

## <a name="configure-integration-between-exchange-server-and-o365"></a><span data-ttu-id="b6f29-112">Exchange Server와 O365 간 통합 구성</span><span class="sxs-lookup"><span data-stu-id="b6f29-112">Configure integration between Exchange Server and O365</span></span>

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a><span data-ttu-id="b6f29-113">1 단계: Exchange Server와 O365 간의 OAuth 인증 구성</span><span class="sxs-lookup"><span data-stu-id="b6f29-113">Step 1: Configure OAuth authentication between Exchange Server and O365</span></span>

<span data-ttu-id="b6f29-114">다음 문서의 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-114">Perform the steps in the following article:</span></span>

[<span data-ttu-id="b6f29-115">Exchange 및 Exchange Online 조 직 간의 OAuth 인증 구성</span><span class="sxs-lookup"><span data-stu-id="b6f29-115">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a><span data-ttu-id="b6f29-116">2 단계: 비즈니스용 Skype Online 파트너 응용 프로그램에 대 한 새 메일 사용자 계정 만들기</span><span class="sxs-lookup"><span data-stu-id="b6f29-116">Step 2: Create a new Mail User account for the Skype for Business Online Partner Application</span></span>

<span data-ttu-id="b6f29-117">이 단계는 Exchange 서버에서 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-117">This step is done on the Exchange server.</span></span> <span data-ttu-id="b6f29-118">이를 통해 메일 사용자를 만들고 적절 한 관리 역할 권한을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-118">It will create a mail user and assign it the appropriate management role rights.</span></span> <span data-ttu-id="b6f29-119">이 계정은 다음 단계에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-119">This account will then be used in the next step.</span></span>

<span data-ttu-id="b6f29-120">Exchange 조직의 확인 된 도메인을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-120">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="b6f29-121">이 도메인은 온-프레미스 Exchange 계정에 사용 되는 기본 SMTP 도메인에 사용 되는 도메인과 동일 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-121">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="b6f29-122">이 도메인을 확인 된 \<도메인\> 이라고 하는 절차는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-122">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="b6f29-123">또한 domaincontrollerfqdn \<\> 은 도메인 컨트롤러의 FQDN 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-123">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span>

``` Powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="b6f29-124">이 명령을 사용 하면 주소 목록에서 새 메일 사용자를 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-124">This command will hide the new mail user from address lists.</span></span>

``` Powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="b6f29-125">다음 두 명령에서는 UserApplication 및 ArchiveApplication 관리 역할을이 새 계정에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-125">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>

``` Powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

``` Powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a><span data-ttu-id="b6f29-126">3 단계: 비즈니스용 Skype Online 용 파트너 응용 프로그램 만들기 및 사용</span><span class="sxs-lookup"><span data-stu-id="b6f29-126">Step 3: Create and enable a Partner Application for Skype for Business Online</span></span> 

<span data-ttu-id="b6f29-127">새 파트너 응용 프로그램을 만들고 방금 만든 계정을 사용 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-127">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="b6f29-128">온-프레미스 Exchange 조직의 Exchange PowerShell에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-128">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a><span data-ttu-id="b6f29-129">4 단계: 온-프레미스 인증 인증서 내보내기</span><span class="sxs-lookup"><span data-stu-id="b6f29-129">Step 4: Export the on-premises authorization certificate</span></span>

<span data-ttu-id="b6f29-130">PowerShell 스크립트를 실행 하 여 다음 단계에서 비즈니스용 Skype Online 조 직에 가져올 온-프레미스 인증 인증서를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-130">Run a PowerShell script to export the on-premises authorization certificate, which you will import to your Skype for Business Online organization in the next step.</span></span>

<span data-ttu-id="b6f29-131">다음 텍스트를 명명 된 PowerShell 스크립트 파일 (예: ExportAuthCert. ps1)에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-131">Save the following text to a PowerShell script file named, for example, ExportAuthCert.ps1.</span></span>

``` Powershell
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

<span data-ttu-id="b6f29-132">온-프레미스 Exchange 조직의 Exchange PowerShell에서 방금 만든 PowerShell 스크립트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-132">In Exchange PowerShell in your on-premises Exchange organization, run the PowerShell script that you just created.</span></span> <span data-ttu-id="b6f29-133">예: .\ExportAuthCert.ps1</span><span class="sxs-lookup"><span data-stu-id="b6f29-133">For example: .\ExportAuthCert.ps1</span></span>

### <a name="step-6-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a><span data-ttu-id="b6f29-134">6 단계: Azure Active Directory ACS에 온-프레미스 인증 인증서 업로드</span><span class="sxs-lookup"><span data-stu-id="b6f29-134">Step 6: Upload the on-premises authorization certificate to Azure Active Directory ACS</span></span>

<span data-ttu-id="b6f29-135">다음으로, Windows PowerShell을 사용 하 여 이전 단계에서 내보낸 온-프레미스 인증 인증서를 Azure Active Directory ACS (Access Control Services)에 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-135">Next, use Windows PowerShell to upload the on-premises authorization certificate that you exported in the previous step to Azure Active Directory Access Control Services (ACS).</span></span> <span data-ttu-id="b6f29-136">이렇게 하려면 Windows PowerShell cmdlet 용 Azure Active Directory 모듈이 이미 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-136">To do this, the Azure Active Directory Module for Windows PowerShell cmdlets must already be installed.</span></span> <span data-ttu-id="b6f29-137">설치 되어 있지 않은 경우에 [https://aka.ms/aadposh](https://aka.ms/aadposh) 는 Windows PowerShell 용 Azure Active Directory 모듈 설치로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-137">If it's not installed, go to [https://aka.ms/aadposh](https://aka.ms/aadposh) to install the Azure Active Directory Module for Windows PowerShell.</span></span> <span data-ttu-id="b6f29-138">Windows PowerShell 용 Azure Active Directory 모듈을 설치한 후 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-138">Complete the following steps after the Azure Active Directory Module for Windows PowerShell is installed.</span></span>

1. <span data-ttu-id="b6f29-139">**Windows powershell 용 Azure Active Directory 모듈** 바로 가기를 클릭 하 여 azure AD cmdlet이 설치 되어 있는 windows powershell 작업 영역을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-139">Click the **Azure Active Directory Module for Windows PowerShell** shortcut to open a Windows PowerShell workspace that has the Azure AD cmdlets installed.</span></span> <span data-ttu-id="b6f29-140">이 단계의 모든 명령은 Azure Active Directory 콘솔용 Windows PowerShell을 사용 하 여 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-140">All commands in this step will be run using the Windows PowerShell for Azure Active Directory console.</span></span>

2. <span data-ttu-id="b6f29-141">예를 들어, 다음과 같이 명명 된 PowerShell 스크립트 파일에 다음 텍스트 `UploadAuthCert.ps1`를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-141">Save the following text to a PowerShell script file named, for example,  `UploadAuthCert.ps1`.</span></span>

   ``` Powershell
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

3. <span data-ttu-id="b6f29-142">이전 단계에서 만든 PowerShell 스크립트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-142">Run the PowerShell script that you created in the previous step.</span></span> <span data-ttu-id="b6f29-143">예를 들어:`.\UploadAuthCert.ps1`</span><span class="sxs-lookup"><span data-stu-id="b6f29-143">For example:  `.\UploadAuthCert.ps1`</span></span>

4. <span data-ttu-id="b6f29-144">스크립트를 시작 하면 자격 증명 대화 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-144">After you start the script, a credentials dialog box is displayed.</span></span> <span data-ttu-id="b6f29-145">Microsoft Online Azure AD 조직의 테 넌 트 관리자 계정에 대 한 자격 증명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-145">Enter the credentials for the tenant administrator account of your Microsoft Online Azure AD organization.</span></span> <span data-ttu-id="b6f29-146">스크립트를 실행 한 후 Azure AD 세션 용 Windows PowerShell을 열어 둡니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-146">After running the script, leave the Windows PowerShell for Azure AD session open.</span></span> <span data-ttu-id="b6f29-147">이는 다음 단계에서 PowerShell 스크립트를 실행 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-147">You will use this to run a PowerShell script in the next step.</span></span>

### <a name="step-7-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a><span data-ttu-id="b6f29-148">7 단계: 인증서가 비즈니스용 Skype 서비스 사용자에 게 업로드 되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="b6f29-148">Step 7: Verify that the Certificate has Uploaded to the Skype for Business Service Principal</span></span>
1. <span data-ttu-id="b6f29-149">Azure Active Directory로 열리고 인증 된 PowerShell에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-149">In the PowerShell opened and authenticated to Azure Active Directory, run the following</span></span>
```
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. <span data-ttu-id="b6f29-150">ReturnKeyValues에 대 한 메시지가 나타나면 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-150">Press Enter when prompted for ReturnKeyValues</span></span>
3. <span data-ttu-id="b6f29-151">Exchange Oauth 인증서 시작 및 종료 날짜와 일치 하는 시작 날짜 및 끝 데이터가 나열 된 키가 표시 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-151">Confirm you see a key listed with start date and end data that matches your Exchange Oauth certificate start and end dates</span></span>

### <a name="verify-your-success"></a><span data-ttu-id="b6f29-152">성공 여부 확인</span><span class="sxs-lookup"><span data-stu-id="b6f29-152">Verify your success</span></span>

<span data-ttu-id="b6f29-153">일부 기능이 제대로 작동 하는지 확인 하 여 구성이 올바른지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-153">Verify that the configuration is correct by verifying some of the features are working successfully.</span></span> 

1. <span data-ttu-id="b6f29-154">하이브리드 Exchange Server 구성을 사용 하는 조직에서 비즈니스용 Skype 사용자가 클라우드 보이스 메일 서비스를 사용 하는 경우 보이스 메일 인사말을 변경할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-154">Confirm that Skype for Business users with Cloud Voicemail service, in an organization with a Hybrid Exchange Server configuration, can successfully change their voicemail greetings.</span></span>

2. <span data-ttu-id="b6f29-155">모바일 클라이언트에 대 한 대화 내용 확인은 Outlook 대화 내용 폴더에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-155">Confirm conversation history for mobile clients is visible in the Outlook Conversation History folder.</span></span>

3. <span data-ttu-id="b6f29-156">저장 된 채팅 메시지가 [EWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/)를 사용 하 여 제거 폴더의 사용자의 온-프레미스 사서함에 보관 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-156">Confirm that archived chat messages are deposited in the user's on premise mailbox in the Purges folder using [EWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/).</span></span>

<span data-ttu-id="b6f29-157">또는 트래픽을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-157">Alternately, look at your traffic.</span></span> <span data-ttu-id="b6f29-158">OAuth 핸드셰이크의 트래픽 (기본 인증과 유사 하지는 않음), 특히 아래와 같이 발급자 소통량을 표시 하기 시작 하는 00000004-0000-0ff1-ce00-000000000000 @ (간혹/이전 전달 되는 토큰의 @ 기호)입니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-158">The traffic in an OAuth handshake is really distinctive (and doesn't look like Basic authentication), particularly around realms, where you’ll begin to see issuer traffic that looks like this: 00000004-0000-0ff1-ce00-000000000000@ (sometimes with a / before the @ sign), in the tokens that are being passed.</span></span> <span data-ttu-id="b6f29-159">OAuth의 지점인 사용자 이름 또는 암호는 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-159">You won’t see a username or password, which is the point of OAuth.</span></span> <span data-ttu-id="b6f29-160">그러나 ' Office ' 발급자가 표시 되는 경우 (이 경우 ' 4 '는 비즈니스용 Skype 이며 구독 영역입니다.)</span><span class="sxs-lookup"><span data-stu-id="b6f29-160">But you will see   the ‘Office’ issuer – in this case ‘4’ is Skype for Business – and the realm of your subscription.</span></span>

<span data-ttu-id="b6f29-161">OAuth를 사용 하 여 성공적으로 진행 되 고 있는지 확인 하려면 예상 되는 내용과 트래픽 형태를 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-161">If you want to be sure you’re successfully using OAuth, make certain you know what to expect and know what the traffic should look like.</span></span> <span data-ttu-id="b6f29-162">이 [에](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)대 한 자세한 내용은 [Microsoft 응용 프로그램의 oauth 트래픽](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (토큰 새로 고침을 사용 하지는 않음)에 대 한 일반적인 예와 oauth JWT (JSON)를 확인 하는 데 사용할 수 있는 Fiddler 확장명을 제공 합니다. 웹 토큰).</span><span class="sxs-lookup"><span data-stu-id="b6f29-162">So [here’s what to expect](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), here’s a pretty standard [example of OAuth traffic in a Microsoft application](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (really helpful to read, though it doesn't use Refresh tokens), and there are Fiddler extensions that will let you look into your OAuth JWT (JSON Web Token).</span></span>

<span data-ttu-id="b6f29-163">다음은 [설정의 예](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/)입니다. 하지만 원하는 모든 네트워크 추적 도구를 사용 하 여이 프로세스를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f29-163">Here's an [example of setting one up](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), but you can use any network tracing tool you like to undertake this process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b6f29-164">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b6f29-164">Related topics</span></span>

[<span data-ttu-id="b6f29-165">Exchange 및 Exchange Online 조 직 간의 OAuth 인증 구성</span><span class="sxs-lookup"><span data-stu-id="b6f29-165">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
