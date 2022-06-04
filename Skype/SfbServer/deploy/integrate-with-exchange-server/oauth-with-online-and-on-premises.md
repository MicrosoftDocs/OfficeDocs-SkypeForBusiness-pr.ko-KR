---
title: 비즈니스용 Skype Online과 Exchange 서버 간의 통합
ms.reviewer: cbland
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 02/17/2022
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: Exchange 온-프레미스와 비즈니스용 Skype Online 간에 OAuth 인증을 구성하면 기능 지원에 설명된 비즈니스용 Skype 및 Exchange 통합 기능을 사용할 수 있습니다.
ms.openlocfilehash: 0b312dfde144f12a9c2db523ce4526153b445d59
ms.sourcegitcommit: e3931446943684db155bb3edf7d7e52d41775013
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2022
ms.locfileid: "65886645"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a>비즈니스용 Skype Online과 Exchange Server 간에 통합 및 OAuth 구성 

Exchange 서버와 비즈니스용 Skype Online 간의 통합을 구성하면 [기능 지원에](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) 설명된 비즈니스용 Skype 및 Exchange 통합 기능을 사용할 수 있습니다.

이 항목은 Exchange Server 2013~2019와의 통합에 적용됩니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용

- 이 작업의 예상 완료 시간: 15분

-  이러한 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다. 필요한 권한을 보려면 [Exchange 및 Shell 인프라 권한](/exchange/exchange-and-shell-infrastructure-permissions-exchange-2013-help) 항목을 참조하세요.

- 이 항목의 절차에 적용할 수 있는 바로 가기 키에 대한 자세한 내용은 [Exchange 관리 센터의 바로 가기 키]( https://go.microsoft.com/fwlink/p/?LinkId=746512)을 참조하세요.

- 호환성에 대한 자세한 내용은 [Office 앱과의 비즈니스용 Skype 호환성을 참조하세요](../../plan-your-deployment/clients-and-devices/compatibility-with-office.md).

## <a name="configure-integration-between-exchange-server-and-o365"></a>Exchange Server와 O365 간의 통합 구성

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>1단계: Exchange Server와 O365 간에 OAuth 인증 구성

다음 문서의 단계를 수행합니다.

[Exchange 및 Exchange Online 조직 간의 OAuth 인증 구성](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>2단계: 비즈니스용 Skype Online 파트너 애플리케이션에 대한 새 메일 사용자 계정 만들기

이 단계는 Exchange 서버에서 수행됩니다. 메일 사용자를 만들고 적절한 관리 역할 권한을 할당합니다. 이 계정은 다음 단계에서 사용됩니다.

Exchange 조직에 대해 확인된 도메인을 지정합니다. 이 도메인은 온-프레미스 Exchange 계정에 사용되는 기본 SMTP 도메인과 동일한 도메인이어야 합니다. 이 도메인은 다음 절차에서 참조 \<your Verified Domain\> 합니다. \<DomainControllerFQDN\> 또한 도메인 컨트롤러의 FQDN이어야 합니다.

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

이 명령은 주소 목록에서 새 메일 사용자를 숨깁니다.

```powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

다음 두 명령은 UserApplication 및 ArchiveApplication 관리 역할을 이 새 계정에 할당합니다.

```powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a>3단계: 비즈니스용 Skype Online용 파트너 애플리케이션 만들기 및 사용 

새 파트너 애플리케이션을 만들고 방금 만든 계정을 사용합니다. 온-프레미스 Exchange 조직의 Exchange PowerShell에서 다음 명령을 실행합니다.

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a>4단계: 온-프레미스 권한 부여 인증서 내보내기

PowerShell 스크립트를 실행하여 다음 단계에서 비즈니스용 Skype Online 조직으로 가져올 온-프레미스 권한 부여 인증서를 내보냅니다.

ExportAuthCert.ps1과 같이 이름을 지정한 PowerShell 스크립트 파일에 다음 텍스트를 저장합니다.

```powershell
$thumbprint = (Get-AuthConfig).CurrentCertificateThumbprint
if((test-path $env:SYSTEMDRIVE\OAuthConfig) -eq $false) {
    md $env:SYSTEMDRIVE\OAuthConfig
}
cd $env:SYSTEMDRIVE\OAuthConfig
$oAuthCert = (dir Cert:\LocalMachine\My) | where {$_.Thumbprint -match $thumbprint}
$certType = [System.Security.Cryptography.X509Certificates.X509ContentType]::Cert
$certBytes = $oAuthCert.Export($certType)
$CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
[System.IO.File]::WriteAllBytes($CertFile, $certBytes)
```

온-프레미스 Exchange 조직의 Exchange PowerShell에서 방금 만든 PowerShell 스크립트를 실행합니다. 예: .\ExportAuthCert.ps1

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>5단계: Azure Active Directory ACS에 온-프레미스 권한 부여 인증서 업로드

다음으로, Windows PowerShell을 사용하여 이전 단계에서 내보낸 온-프레미스 권한 부여 인증서를 Azure Active Directory ACS(Access Control Services)에 업로드합니다. 이렇게 하려면 Windows PowerShell cmdlet용 Azure Active Directory 모듈이 이미 설치되어 있어야 합니다. 설치 [https://aka.ms/aadposh](/previous-versions/azure/jj151815(v=azure.100)) 되지 않은 경우 Windows PowerShell용 Azure Active Directory 모듈을 설치합니다. Windows PowerShell용 Azure Active Directory 모듈이 설치된 후 다음 단계를 완료합니다.

1. **Windows PowerShell용 Azure Active Directory 모듈** 바로 가기를 클릭하여 Azure AD cmdlet이 설치된 Windows PowerShell 작업 영역을 엽니다. 이 단계의 모든 명령은 Azure Active Directory 콘솔용 Windows PowerShell을 사용하여 실행됩니다.

2. 예를 들어  `UploadAuthCert.ps1`다음 텍스트를 PowerShell 스크립트 파일에 저장합니다.

   ```powershell
   Connect-MsolService
   Import-Module MSOnline
   $CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
   $objFSO = New-Object -ComObject Scripting.FileSystemObject
   $CertFile = $objFSO.GetAbsolutePathName($CertFile);
   $cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
   $cer.Import($CertFile)
   $binCert = $cer.GetRawCertData();
   $credValue = [System.Convert]::ToBase64String($binCert)
   $ServiceName = "00000004-0000-0ff1-ce00-000000000000"
   $p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName
   New-MsolServicePrincipalCredential -AppPrincipalId $p.AppPrincipalId -Type asymmetric -Usage Verify -Value $credValue
   ```

3. 이전 단계에서 만든 PowerShell 스크립트를 실행합니다. 예를 들면 다음과 같습니다.

4. 스크립트를 시작하면 자격 증명 대화 상자가 표시됩니다. Microsoft Online Azure AD 조직의 테넌트 관리자 계정에 대한 자격 증명을 입력합니다. 스크립트를 실행한 후 Azure AD용 Windows PowerShell 세션을 열어 둡니다. 이 세션을 사용하여 다음 단계에서 PowerShell 스크립트를 실행합니다.

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a>6단계: 인증서가 비즈니스용 Skype 서비스 주체에 업로드되었는지 확인
1. Azure Active Directory에 대해 열리고 인증된 PowerShell에서 다음을 실행합니다.

   ```powershell
   Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
   ```
2. ReturnKeyValues에 대한 메시지가 표시되면 Enter 키를 누릅니다.
3. Exchange Oauth 인증서 시작 및 종료 날짜와 일치하는 시작 날짜 및 종료 데이터가 나열된 키가 표시되는지 확인합니다.

### <a name="verify-your-success"></a>성공 확인

일부 기능이 제대로 작동하는지 확인하여 구성이 올바른지 확인합니다. 

1. 하이브리드 Exchange Server 구성이 있는 조직에서 Cloud Voicemail 서비스를 사용하는 비즈니스용 Skype 사용자가 음성 메일 인사말을 성공적으로 변경할 수 있음을 확인합니다.

2. 모바일 클라이언트의 대화 기록이 Outlook 대화 기록 폴더에 표시되는지 확인합니다.

3. 보관된 채팅 메시지가 [EWSEditor](/archive/blogs/webdav_101/where-to-get-ewseditor)를 사용하여 Purges 폴더에 있는 사용자의 온-프레미스 사서함에 보관되어 있는지 확인합니다.

또는 트래픽을 살펴보세요. OAuth 핸드셰이크의 트래픽은 특히 전달되는 토큰에서 000000004-0000-0ff1-ce00-0000000000000@(때로는 @ 기호 앞에 있음)과 같은 발급자 트래픽을 보기 시작하는 영역과 관련하여 매우 독특합니다(기본 인증처럼 보이지 않음). OAuth의 지점인 사용자 이름 또는 암호가 표시되지 않습니다. 하지만 'Office' 발급자(이 경우 '4'는 비즈니스용 Skype)와 구독 영역이 표시됩니다.

OAuth를 성공적으로 사용하고 있는지 확인하려면 무엇을 기대해야 하는지 알고 트래픽의 모양을 알고 있는지 확인합니다. Microsoft [애플리케이션의 OAuth 트래픽](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)에 대한 표준 예제는 [다음과 같습니다](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)(새로 고침 토큰을 사용하지는 않지만 읽기에 정말 유용함). OAuth JWT(JSON 웹 토큰)를 살펴볼 수 있는 Fiddler 확장이 있습니다.

다음은 [설정의 예](/archive/blogs/kaevans/updated-fiddler-oauth-inspector)이지만 이 프로세스를 수행하려는 모든 네트워크 추적 도구를 사용할 수 있습니다.

## <a name="related-topics"></a>관련 항목

[Exchange 및 Exchange Online 조직 간의 OAuth 인증 구성](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
