---
title: 비즈니스용 Skype 서버 하이브리드 환경에 대 한 서버 간 인증 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: '요약: 비즈니스용 Skype 서버 하이브리드 환경에 대 한 서버 간 인증을 구성 합니다.'
ms.openlocfilehash: 191d5d2f391df73401ff27e8c71a60624e74296c
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780737"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a>비즈니스용 Skype 서버 하이브리드 환경에 대해 서버 간 인증을 구성 합니다.

**요약:** 비즈니스용 Skype 서버 하이브리드 환경에 대해 서버 간 인증을 구성 합니다.

하이브리드 구성에서 일부 사용자는 다른 사용자가 비즈니스용 skype 서버를 온-프레미스로 설치 하는 동안 설정 되며, 그 중 일부는 Office 365 버전의 Skype 서버에 속해 있습니다. 하이브리드 환경에서 서버 간 인증을 구성 하려면 먼저 Office 365 인증 서버를 신뢰 하도록 비즈니스용 Skype 서버의 온-프레미스 설치를 구성 해야 합니다. 이 프로세스의 초기 단계는 다음 비즈니스용 Skype 서버 관리 셸 스크립트를 실행 하 여 수행할 수 있습니다.

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

이 스크립트를 실행 하려면 비즈니스용 Skype Online PowerShell 모듈을 설치 하 고이 모듈을 사용 하 여 테 넌 트에 연결 해야 합니다. 이러한 cmdlet을 설치 하지 않은 경우 CsTenant cmdlet을 사용할 수 없으므로 스크립트에 오류가 발생 합니다. 스크립트를 완료 한 후에는 비즈니스용 Skype 서버와 인증 서버 간의 트러스트 관계를 구성 하 고 Exchange 2013/2016과 인증 서버 간의 두 번째 트러스트 관계를 설정 해야 합니다. 이 작업은 Microsoft Online Services cmdlet을 사용해서만 수행할 수 있습니다.

> [!NOTE]
> Microsoft Online Services cmdlet을 설치 하지 않은 경우에는 cmdlet `install-module MSOnline`을 사용 하 여 PowerShell 리포지토리에서 설치 해야 합니다. Microsoft Online Services 모듈 설치 및 사용에 대한 자세한 정보는 Office 365 웹 사이트에서 찾을 수 있습니다. 이러한 지침에서는 Office 365 및 Active Directory 간의 단일 로그인 구성, 페더레이션 및 동기화 방법을 설명합니다. 



Office 365를 구성 하 고 비즈니스용 Skype 서버 및 Exchange 2013에 대 한 Office 365 서비스 사용자를 만든 후에는 이러한 서비스 주체에 자격 증명을 등록 해야 합니다. 이 작업을 수행 하려면 먼저로 저장 된 x.509 Base64 인증서를 가져와야 합니다. CER 파일 이 인증서는 Office 365 서비스 계정에 적용됩니다.

X.509 인증서를 가져온 후 PowerShell 콘솔을 열고 서비스 주체를 관리 하는 데 사용할 수 있는 cmdlet이 포함 된 Microsoft Online Windows PowerShell 모듈을 가져옵니다.

```PowerShell
Import-Module MSOnline
```

모듈을 가져왔으면 Office 365에 연결하기 위해 다음 명령을 입력하고 Enter 키를 누릅니다.

```PowerShell
Connect-MsolService
```

Enter를 누르면 자격 증명 대화 상자가 표시됩니다. 대화 상자에 Microsoft 365 또는 Office 365 사용자 이름과 암호를 입력 한 다음 확인을 클릭 합니다.

Office 365에 연결 되는 즉시 서비스 계정에 대 한 정보를 반환 하기 위해 다음 명령을 실행할 수 있습니다.

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

다음 단계에서는 X.509 인증서를 가져오고, 인코딩하고, 지정합니다. 인증서를 가져오고 인코딩하려면 다음 Windows PowerShell 명령을 사용 하 여에 대 한 전체 파일 경로를 지정 해야 합니다. CER 파일에서 가져오기 메서드를 호출 합니다.

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

인증서를 가져오고 인코딩한 후에는 인증서를 Office 365 서비스 사용자에 게 할당할 수 있습니다. 이 작업을 수행 하려면 먼저 (New-msolserviceprincipal를 사용 하 여 비즈니스용 Skype 서버와 Microsoft Exchange 서비스 사용자 둘 다에 대 한 AppPrincipalId 속성 값을 검색 합니다. AppPrincipalId 속성 값은 인증서가 할당 되는 서비스 사용자를 식별 하는 데 사용 됩니다. 비즈니스용 Skype 서버에 AppPrincipalId 속성 값을 사용 하 여 비즈니스용 Skype Online 버전에 인증서를 할당 합니다.

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

이 때 Exchange 2013에 AppPrincipalId 속성 값을 사용 하 여이 명령을 반복 해야 합니다.

나중에 해당 인증서를 삭제 해야 하는 경우 (예: 만료 된 경우) 먼저 인증서의 KeyId를 검색 하 여 삭제할 수 있습니다.

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

인증서를 할당 하는 것 외에도 Exchange Online 서비스 사용자를 구성 하 고 온-프레미스 버전의 비즈니스용 Skype 서버 외부 웹 서비스 Url을 Office 365 서비스 주체로 구성 해야 합니다. 이 작업은 다음 두 명령을 실행 하 여 수행할 수 있습니다. 

다음 예제에서는 Pool1ExternalWebFQDN.contoso.com가 비즈니스용 Skype 서버 풀의 외부 웹 서비스 URL입니다. 모든 외부 웹 서비스 Url을 배포에 추가 하려면 다음 단계를 반복 해야 합니다.

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
