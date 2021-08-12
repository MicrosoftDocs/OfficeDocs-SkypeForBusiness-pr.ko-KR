---
title: Get-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b2b5aefb-a08d-4bec-9204-76597d413849
description: 이 Get-CcCredential cmdlet은 현재 배포의 자격 증명을 비즈니스용 Skype 클라우드 커넥터 버전 반환합니다.
ms.openlocfilehash: 277062068c6e5e630fd22cd1bd4c6dbfb873db1cb90b915424aa6e3a3eb6ce50
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322891"
---
# <a name="get-cccredential"></a>Get-CcCredential
 
이 Get-CcCredential cmdlet은 현재 배포의 자격 증명을 비즈니스용 Skype 클라우드 커넥터 버전 반환합니다. 
  
버전 2.0 이상에서는 -DisplayPassword 매개 변수를 사용하여 TenantAdmin, DomainAdmin 및 VMAdmin의 암호를 표시할 수도 있습니다.
  
```powershell
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 예에서는 클라우드 커넥터 가상 컴퓨터 도메인의 도메인 관리자 자격 증명을 반환합니다.
  
```powershell
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

이 Get-CcCredential cmdlet은 지정된 계정 유형에 대한 자격 증명 정보를 반환합니다. 이러한 자격 증명은 현재 어플라이언스를 배포할 때 Register-CcAppliance Install-CcAppliance cmdlet을 실행한 관리자가 지정합니다. 
  
이 Get-CcCredential Cmdlet은 System.Management.Automation.PSCredential 개체의 인스턴스를 반환합니다. 반환 개체의 암호 속성은 System.Security.SecureString입니다.
  
도메인 관리자 암호의 암호를 명확하게 입력하려면 호스트 서버의 현재 로그온 계정에서 암호를 입력한 다음 관리자 권한으로 PowerShell 콘솔을 열고 아래 스크립트를 실행합니다.
  
```powershell
$cred = Get-CcCredential -AccountType DomainAdmin
$password =  $cred.Password
$bstr = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($password);
$text = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr);
[System.Runtime.InteropServices.Marshal]::ZeroFreeBSTR($bstr);
Write-Host $text
```

## <a name="parameters"></a>매개 변수
<a name="DetailedDescription"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> |필수  <br/> | System.String <br/> | AccountType 값은 다음 중 하나일 수 있습니다. <br/>  VmAdmin: 클라우드 커넥터 가상 컴퓨터의 로컬 관리자입니다. <br/>  DomainAdmin: 클라우드 커넥터 가상 컴퓨터 도메인의 도메인 관리자입니다. <br/>  SafeModeAdmin: 클라우드 커넥터 가상 컴퓨터 도메인 컨트롤러의 SafeModeAdmin입니다. <br/>  ExternalCert: 에지 서버에 설치된 외부 인증서의 계정입니다. <br/>  TenantAdmin: O365 테넌트의 관리자입니다. <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음 이 Get-CcCredential cmdlet은 파이프라인된 입력을 허용하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

이 Get-CcCredential Cmdlet은 System.Management.Automation.PSCredential 개체의 인스턴스를 반환합니다.
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Set-CcCredential](set-cccredential.md)
  

