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
ms.openlocfilehash: 1d64f8fe7b2d6dcf276ae34e74c84faf5c93f65a
ms.sourcegitcommit: 2b4fcf2561134b9f1b9a1b49401d97da1286e89d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2019
ms.locfileid: "37979781"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a>비즈니스용 Skype Online 및 Exchange Server 간 통합 및 OAuth 구성 

Exchange server와 비즈니스용 Skype Online의 통합을 구성 하면 [기능 지원](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)에서 설명 하는 비즈니스용 Skype 및 Exchange 통합 기능을 사용할 수 있습니다.

이 항목은 Exchange Server 2013 ~ 2019과의 통합에 적용 됩니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작 하기 전에 알아야 할 사항

- 이 작업을 완료 하는 데 예상 되는 시간: 15 분

-  이 절차 또는 절차를 수행 하기 전에 사용 권한을 할당 받아야 합니다. 필요한 사용 권한을 확인 하려면 [Exchange 및 셸 인프라 사용 권한](https://go.microsoft.com/fwlink/p/?LinkId=746511) 항목을 참조 하세요.

- 이 항목의 절차에 적용 될 수 있는 바로 가기 키에 대 한 자세한 내용은 [Exchange 관리 센터의 바로 가기 키]( https://go.microsoft.com/fwlink/p/?LinkId=746512)를 참조 하세요.

- 호환성에 대 한 자세한 내용은 [Office 앱과 비즈니스용 Skype 호환성](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office)을 참조 하세요.

## <a name="configure-integration-between-exchange-server-and-o365"></a>Exchange Server와 O365 간 통합 구성

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>1 단계: Exchange Server와 O365 간의 OAuth 인증 구성

다음 문서의 단계를 수행 합니다.

[Exchange 및 Exchange Online 조 직 간의 OAuth 인증 구성](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a>2 단계: 비즈니스용 Skype Online 파트너 응용 프로그램에 대 한 새 메일 사용자 계정 만들기

이 단계는 Exchange 서버에서 수행 됩니다. 이를 통해 메일 사용자를 만들고 적절 한 관리 역할 권한을 할당 합니다. 이 계정은 다음 단계에서 사용 됩니다.

Exchange 조직의 확인 된 도메인을 지정 합니다. 이 도메인은 온-프레미스 Exchange 계정에 사용 되는 기본 SMTP 도메인에 사용 되는 도메인과 동일 해야 합니다. 이 도메인을 확인 된 \<도메인\> 이라고 하는 절차는 다음과 같습니다. 또한 domaincontrollerfqdn \<\> 은 도메인 컨트롤러의 FQDN 이어야 합니다.

``` Powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

이 명령을 사용 하면 주소 목록에서 새 메일 사용자를 숨길 수 있습니다.

``` Powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

다음 두 명령에서는 UserApplication 및 ArchiveApplication 관리 역할을이 새 계정에 할당 합니다.

``` Powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

``` Powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a>3 단계: 비즈니스용 Skype Online 용 파트너 응용 프로그램 만들기 및 사용 

새 파트너 응용 프로그램을 만들고 방금 만든 계정을 사용 하 게 됩니다. 온-프레미스 Exchange 조직의 Exchange PowerShell에서 다음 명령을 실행 합니다.

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a>4 단계: 온-프레미스 인증 인증서 내보내기

PowerShell 스크립트를 실행 하 여 다음 단계에서 비즈니스용 Skype Online 조 직에 가져올 온-프레미스 인증 인증서를 내보냅니다.

다음 텍스트를 명명 된 PowerShell 스크립트 파일 (예: ExportAuthCert. ps1)에 저장 합니다.

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

온-프레미스 Exchange 조직의 Exchange PowerShell에서 방금 만든 PowerShell 스크립트를 실행 합니다. 예: .\ExportAuthCert.ps1

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a>5 단계: Azure Active Directory ACS에 온-프레미스 인증 인증서 업로드

다음으로, Windows PowerShell을 사용 하 여 이전 단계에서 내보낸 온-프레미스 인증 인증서를 Azure Active Directory ACS (Access Control Services)에 업로드 합니다. 이렇게 하려면 Windows PowerShell cmdlet 용 Azure Active Directory 모듈이 이미 설치 되어 있어야 합니다. 설치 되어 있지 않은 경우에 [https://aka.ms/aadposh](https://aka.ms/aadposh) 는 Windows PowerShell 용 Azure Active Directory 모듈 설치로 이동 합니다. Windows PowerShell 용 Azure Active Directory 모듈을 설치한 후 다음 단계를 완료 합니다.

1. **Windows powershell 용 Azure Active Directory 모듈** 바로 가기를 클릭 하 여 azure AD cmdlet이 설치 되어 있는 windows powershell 작업 영역을 엽니다. 이 단계의 모든 명령은 Azure Active Directory 콘솔용 Windows PowerShell을 사용 하 여 실행 됩니다.

2. 예를 들어, 다음과 같이 명명 된 PowerShell 스크립트 파일에 다음 텍스트 `UploadAuthCert.ps1`를 저장 합니다.

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

3. 이전 단계에서 만든 PowerShell 스크립트를 실행 합니다. 예를 들어:`.\UploadAuthCert.ps1`

4. 스크립트를 시작 하면 자격 증명 대화 상자가 표시 됩니다. Microsoft Online Azure AD 조직의 테 넌 트 관리자 계정에 대 한 자격 증명을 입력 합니다. 스크립트를 실행 한 후 Azure AD 세션 용 Windows PowerShell을 열어 둡니다. 이는 다음 단계에서 PowerShell 스크립트를 실행 하는 데 사용 됩니다.

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a>6 단계: 인증서가 비즈니스용 Skype 서비스 사용자에 게 업로드 되었는지 확인
1. Azure Active Directory로 열리고 인증 된 PowerShell에서 다음을 실행 합니다.
```
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. ReturnKeyValues에 대 한 메시지가 나타나면 enter 키를 누릅니다.
3. Exchange Oauth 인증서 시작 및 종료 날짜와 일치 하는 시작 날짜 및 끝 데이터가 나열 된 키가 표시 되는지 확인 합니다.

### <a name="verify-your-success"></a>성공 여부 확인

일부 기능이 제대로 작동 하는지 확인 하 여 구성이 올바른지 확인 합니다. 

1. 하이브리드 Exchange Server 구성을 사용 하는 조직에서 비즈니스용 Skype 사용자가 클라우드 보이스 메일 서비스를 사용 하는 경우 보이스 메일 인사말을 변경할 수 있는지 확인 합니다.

2. 모바일 클라이언트에 대 한 대화 내용 확인은 Outlook 대화 내용 폴더에 표시 됩니다.

3. 저장 된 채팅 메시지가 사용자의 온-프레미스 사서함에 [EWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/)를 사용 하 여 제거 폴더에 보관 되어 있는지 확인 합니다.

또는 트래픽을 살펴봅니다. OAuth 핸드셰이크의 트래픽 (기본 인증과 유사 하지는 않음), 특히 아래와 같이 발급자 소통량을 표시 하기 시작 하는 00000004-0000-0ff1-ce00-000000000000 @ (간혹/이전 전달 되는 토큰의 @ 기호)입니다. OAuth의 지점인 사용자 이름 또는 암호는 표시 되지 않습니다. 그러나 ' Office ' 발급자가 표시 되는 경우 (이 경우 ' 4 '는 비즈니스용 Skype 이며 구독 영역입니다.)

OAuth를 사용 하 여 성공적으로 진행 되 고 있는지 확인 하려면 예상 되는 내용과 트래픽 형태를 알아야 합니다. 이 [에](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)대 한 자세한 내용은 [Microsoft 응용 프로그램의 oauth 트래픽](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (토큰 새로 고침을 사용 하지는 않음)에 대 한 일반적인 예와 oauth JWT (JSON)를 확인 하는 데 사용할 수 있는 Fiddler 확장명을 제공 합니다. 웹 토큰).

다음은 [설정의 예](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/)입니다. 하지만 원하는 모든 네트워크 추적 도구를 사용 하 여이 프로세스를 실행할 수 있습니다.

## <a name="related-topics"></a>관련 주제

[Exchange 및 Exchange Online 조 직 간의 OAuth 인증 구성](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
