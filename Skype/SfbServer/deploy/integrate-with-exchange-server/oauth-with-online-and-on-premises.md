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
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a>비즈니스용 Skype Online과 비즈니스용 Skype 간의 통합 및 OAuth Exchange Server 

Exchange 서버와 비즈니스용 Skype Online 간의 통합을 구성하면 기능 지원에 설명된 비즈니스용 Skype 및 Exchange 통합 [기능을 사용할 수 있습니다.](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)

이 항목은 2013~Exchange Server 통합에 적용됩니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용

- 이 작업의 예상 완료 시간: 15분

-  이러한 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다. 필요한 사용 권한을 표시하려면 Exchange 및 셸 인프라 [사용 권한 항목을 참조하세요.](https://go.microsoft.com/fwlink/p/?LinkId=746511)

- 이 항목의 절차에 적용할 수 있는 바로 가기 키에 대한 자세한 내용은 [Exchange 관리 센터의 바로 가기 키]( https://go.microsoft.com/fwlink/p/?LinkId=746512)을 참조하세요.

- 호환성에 대한 자세한 내용은 [Office 앱과의 비즈니스용 Skype 호환성을 참조하세요.](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office)

## <a name="configure-integration-between-exchange-server-and-o365"></a>O365와 O365 Exchange Server 통합 구성

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>1단계: OAuth 인증과 O365 Exchange Server 구성

다음 문서의 단계를 수행합니다.

[Exchange 및 Exchange Online 조직 간의 OAuth 인증 구성](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>2단계: 비즈니스용 Skype Online 파트너 응용 프로그램에 대한 새 메일 사용자 계정 만들기

이 단계는 Exchange 서버에서 수행됩니다. 메일 사용자를 만들고 적절한 관리 역할 권한을 할당합니다. 이 계정은 다음 단계에서 사용됩니다.

Exchange 조직에 대해 확인된 도메인을 지정합니다. 이 도메인은 기본 SMTP 도메인으로 사용되는 도메인과 동일해야 합니다. 이 도메인은 다음 \<your Verified Domain\> 절차에서 참조됩니다. 또한 도메인 \<DomainControllerFQDN\> 컨트롤러의 FQDN을 지정해야 합니다.

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

이 명령은 새 메일 사용자를 주소 목록에서 숨길 것입니다.

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

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a>3단계: 비즈니스용 Skype Online에 대한 파트너 응용 프로그램 만들기 및 사용 

새 파트너 응용 프로그램을 만들고 방금 만든 계정을 사용하게 됩니다. 온-프레미스 Exchange 조직의 Exchange PowerShell에서 다음 명령을 실행합니다.

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a>4단계: 프레미스 인증 인증서 내보내기

PowerShell 스크립트를 실행하여 다음 단계에서 비즈니스용 Skype Online 조직으로 가져오는 인증 인증서를 내보낼 수 있습니다.

ExportAuthCert.ps1과 같이 이름을 지정한 PowerShell 스크립트 파일에 다음 텍스트를 저장합니다.

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

On-premises Exchange 조직의 Exchange PowerShell에서 방금 만든 PowerShell 스크립트를 실행합니다. 예: .\ExportAuthCert.ps1

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>5단계: Azure Active Directory ACS에 On-premises 권한 부여 인증서 업로드

다음으로, Windows PowerShell 사용하여 이전 단계에서 내보냈던 인증 인증서를 Azure Active Directory ACS(액세스 제어 서비스)에 업로드합니다. 이렇게하려면 cmdlet에 대한 Azure Active Directory Windows PowerShell 이미 설치되어 있어야 합니다. 설치되지 않은 경우 Azure Active Directory 모듈을 설치하는 [https://aka.ms/aadposh](https://aka.ms/aadposh) Windows PowerShell. Azure Active Directory 모듈 for Windows PowerShell 완료합니다.

1. Azure **AD** cmdlet이 Windows PowerShell 응용 프로그램 Windows PowerShell 열려면 Azure Active Directory 모듈을 클릭합니다. 이 단계의 모든 명령은 Azure Active Directory 콘솔용 Windows PowerShell 사용하여 실행됩니다.

2. 다음 텍스트를 이름이 지정한 PowerShell 스크립트 파일에  `UploadAuthCert.ps1` 저장합니다.

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

3. 이전 단계에서 만든 PowerShell 스크립트를 실행합니다. 예를 들면 다음과 같습니다.

4. 스크립트를 시작하면 자격 증명 대화 상자가 표시됩니다. Microsoft Online Azure AD 조직의 테넌트 관리자 계정에 대한 자격 증명을 입력합니다. 스크립트를 실행한 후 Azure AD Windows PowerShell 대한 세션을 열어 두면 됩니다. 이 세션을 사용하여 다음 단계에서 PowerShell 스크립트를 실행합니다.

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a>6단계: 인증서가 비즈니스용 Skype 서비스 사용자에 업로드 났는지 확인
1. Azure Active Directory에서 열고 인증된 PowerShell에서 다음을 실행합니다.
```powershell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. ReturnKeyValues를 입력하라는 메시지가 표시될 때 Enter 키 누르기
3. Exchange Oauth 인증서 시작 및 종료 날짜와 일치하는 시작 날짜 및 종료 데이터가 나열된 키가 표시되어 있는지 확인

### <a name="verify-your-success"></a>성공 확인

일부 기능이 성공적으로 작동하고 있는지 확인하여 구성이 올바른지 확인합니다. 

1. Hybrid Exchange Server 구성의 조직에서 Cloud Voicemail 서비스가 있는 비즈니스용 Skype 사용자가 음성 Exchange Server 성공적으로 변경할 수 있도록 합니다.

2. 모바일 클라이언트의 대화 기록이 Outlook 대화 기록 폴더에 표시되는지 확인합니다.

3. 보관된 채팅 메시지가 [EWSEditor를](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/)사용하여 제거 폴더의 사용자 사서함에 보관되어 있는지 확인합니다.

또는 트래픽을 살펴보아야 합니다. OAuth 핸드세이크의 트래픽은 실제로는 뚜렷하며 기본 인증처럼 보이지 않습니다. 특히, 전달되는 토큰에서 00000004-0000-0ff1-ce00-000000000000@(@기호 앞에 / 포함)과 같은 발급자 트래픽이 표시되기 시작할 것입니다. OAuth의 지점인 사용자 이름이나 암호가 표시되지 않습니다. 하지만 'Office' 발급자( 이 경우 '4'는 비즈니스용 Skype 및 구독의 전제가 됩니다.)가 표시될 것입니다.

OAuth를 성공적으로 사용하고 있는지 확인하려는 경우 예상할 예상과 트래픽의 모양을 알아야 합니다. 따라서 [](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)다음은 Microsoft 응용 프로그램의 [OAuth](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) 트래픽을 예로 들어 보겠습니다(새로 고침 토큰을 사용하지 않는 경우 읽기에 매우 유용), OAuth JWT(JSON 웹 토큰)를 살펴 볼 수 있는 Fiddler 확장이 있습니다.

다음은 하나를 [설정하는](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/)예이지만 이 프로세스를 진행하는 데 원하는 네트워크 추적 도구를 사용할 수 있습니다.

## <a name="related-topics"></a>관련 항목

[Exchange 및 Exchange Online 조직 간의 OAuth 인증 구성](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
