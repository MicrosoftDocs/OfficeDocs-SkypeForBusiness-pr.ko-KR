---
title: 하이브리드 환경에 대한 서버 비즈니스용 Skype 서버 구성
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: '요약: 하이브리드 환경에 대해 서버 비즈니스용 Skype 서버 구성합니다.'
ms.openlocfilehash: 617c388dc4c4120beb457e4e2c90246e06c76d6d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60830932"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>하이브리드 환경에 대해 서버 비즈니스용 Skype 서버 구성합니다.

**요약:** 하이브리드 환경에 대해 서버 비즈니스용 Skype 서버 구성합니다.

하이브리드 구성에서 일부 사용자는 비즈니스용 Skype 서버 버전의 Microsoft 365 또는 Office 365 버전의 비즈니스용 Skype 서버. 하이브리드 환경에서 서버-서버 인증을 구성하려면 먼저 인증 서버를 신뢰하도록 비즈니스용 Skype 서버 설치를 구성해야 합니다. 이 프로세스의 초기 단계는 다음 관리 셸 스크립트를 실행하여 비즈니스용 Skype 서버 수 있습니다.

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId

$sts = Get-CsOAuthServer microsoft.sts -ErrorAction SilentlyContinue

   if ($sts -eq $null)
      {
         New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
      }
   else
      {
         if ($sts.MetadataUrl -ne  "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1")
            {
               Remove-CsOAuthServer microsoft.sts
               New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
            }
        }

$exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue

if ($exch -eq $null)
   {
      New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer
    }
else
    {
       if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
          {
             Remove-CsPartnerApplication microsoft.exchange
             New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer 
          }
       else
          {
             Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full -UseOAuthServer
          }
   }

Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

테넌트의 영역 이름은 일반적으로 조직 이름과 다릅니다. 하지만 실제로 영역 이름은 거의 항상 테넌트 ID와 동일합니다. 이러한 이유로 인해 스크립트의 첫 번째 줄은 지정된 테넌트(이 예의 경우 fabrikam.com)에 대한 TenantId 속성의 값을 반환하고 해당 이름을 $TenantId 변수에 지정하는 데 사용됩니다.

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

이 스크립트를 실행하려면 온라인 PowerShell 모듈에 비즈니스용 Skype 이 모듈을 사용하여 테넌트에 연결해야 합니다. 이러한 cmdlet을 설치하지 않은 경우 해당 cmdlet을 사용할 수 Get-CsTenant 스크립트가 실패합니다. 스크립트가 완료되면 비즈니스용 Skype 서버 서버와 인증 서버 간의 트러스트 관계와 Exchange 2013/2016과 인증 서버 간의 두 번째 트러스트 관계를 구성해야 합니다. 이 작업은 Microsoft Online Services cmdlet을 사용해서만 수행할 수 있습니다.

> [!NOTE]
> Microsoft Online Services 설치하지 않은 경우 cmdlet을 통해 PowerShell 리포지토리에서 설치해야 `install-module MSOnline` 합니다. Microsoft Online Services 모듈을 설치하고 사용하는 자세한 내용은 Microsoft 365 웹 사이트에서 찾을 수 있습니다. 이러한 지침에서는 Microsoft 365 또는 Active Directory와 Active Directory 간에 single sign-on, federation 및 동기화를 Microsoft 365 Office 365 있습니다. 



Microsoft 365 또는 Office 365 구성한 후 비즈니스용 Skype 서버 및 Exchange 2013에 대한 Microsoft 365 또는 Office 365 서비스 계정을 만든 후 이러한 서비스에 자격 증명을 등록해야 합니다. principals. 이렇게하려면 먼저 로 저장된 X.509 Base64 인증서를 얻어야 합니다. CER 파일. 이 인증서는 서비스 Microsoft 365 Office 365 적용됩니다.

X.509 인증서를 얻은 경우 PowerShell 콘솔을 열고 서비스 주체 관리에 사용할 수 있는 cmdlet이 Windows PowerShell 포함된 Microsoft Online Windows PowerShell 모듈을 가져올 수 있습니다.

```PowerShell
Import-Module MSOnline
```

모듈을 가져온 후 다음 명령을 입력하고 Enter를 누르고 있습니다.

```PowerShell
Connect-MsolService
```

Enter를 누르면 자격 증명 대화 상자가 표시됩니다. 대화 Microsoft 365 또는 Office 365 사용자 이름과 암호를 입력한 다음 확인을 클릭합니다.

Microsoft 365 또는 Office 365 즉시 다음 명령을 실행하여 서비스 사용자에 대한 정보를 반환할 수 있습니다.

```PowerShell
Get-MsolServicePrincipal
```

모든 서비스 계정에 대해 이와 비슷한 정보를 얻으려면

<pre>
ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
AccountEnabled       : True
Addresses            : {}
AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
DisplayName          : Skype for Business Server
ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
ServicePrincipalName : SkypeForBusinessServer/litwareinc.com
TrustedForDelegation : True
</pre>

다음 단계에서는 X.509 인증서를 가져오고, 인코딩하고, 지정합니다. 인증서를 가져오고 인코딩하기 위해 다음 Windows PowerShell 명령을 사용하여 에 대한 전체 파일 경로를 지정해야 합니다. Import 메서드를 호출할 때 CER 파일:

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue) 
```

인증서를 가져와 인코딩한 후 인증서를 Microsoft 365 Office 365 있습니다. 이를 위해 먼저 Get-MsolServicePrincipal 를 사용하여 비즈니스용 Skype 서버 및 Microsoft Exchange 서비스 계정의 AppPrincipalId 속성 값을 검색합니다. AppPrincipalId 속성의 값은 인증서가 할당되는 서비스 주체를 식별하는 데 사용됩니다. 앱에 대한 AppPrincipalId 속성 비즈니스용 Skype 서버 다음 명령을 사용하여 비즈니스용 온라인 Skype 인증서를 할당합니다.

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

그런 다음 2013에 AppPrincipalId 속성 값을 사용하여 명령을 Exchange 합니다.

나중에 해당 인증서를 삭제해야 하는 경우(예: 인증서가 만료된 경우) 먼저 인증서의 KeyId를 검색하여 삭제할 수 있습니다.

```PowerShell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

이 명령은 다음과 비슷한 데이터를 반환합니다.

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

그런 후 다음과 비슷한 명령을 사용하여 인증서를 삭제할 수 있습니다.

```PowerShell
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

인증서를 할당하는 것 외에도 Exchange Online 서비스 사용자 및 비즈니스용 Skype 서버 외부 웹 서비스 URL의 비즈니스용 Skype 서버 버전도 Microsoft 365 또는 Office 365 구성해야 합니다. 이 경우 다음 두 명령을 실행합니다. 

다음 예제에서는 Pool1ExternalWebFQDN.contoso.com 풀의 외부 웹 서비스 URL을 비즈니스용 Skype 서버 있습니다. 이러한 단계를 반복하여 배포의 모든 외부 웹 서비스 URL을 추가해야 합니다.

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
