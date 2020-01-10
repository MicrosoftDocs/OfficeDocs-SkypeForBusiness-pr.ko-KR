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
localization_priority: Normal
ms.assetid: b2b5aefb-a08d-4bec-9204-76597d413849
description: Get-CcCredential cmdlet은 현재 비즈니스용 Skype 클라우드 커넥터 에디션 배포의 자격 증명을 반환 합니다.
ms.openlocfilehash: 46c51783361ad6613d1e2971600969b324f0f350
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003388"
---
# <a name="get-cccredential"></a>Get-CcCredential
 
Get-CcCredential cmdlet은 현재 비즈니스용 Skype 클라우드 커넥터 에디션 배포의 자격 증명을 반환 합니다. 
  
버전 2.0 이상에서는-DisplayPassword 매개 변수를 사용 하 여 TenantAdmin, DomainAdmin, VMAdmin에 대 한 암호를 표시할 수도 있습니다.
  
```powershell
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예제 1

다음 예에서는 클라우드 커넥터 가상 컴퓨터 도메인의 도메인 관리자 자격 증명을 반환 합니다.
  
```powershell
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

Get-CcCredential cmdlet은 지정 된 계정 유형에 대 한 자격 증명 정보를 반환 합니다. 이러한 자격 증명은 현재 기기를 배포할 때 등록-CcAppliance 및 설치-CcAppliance cmdlet을 실행 하는 관리자가 지정 합니다. 
  
Get-CcCredential cmdlet은 System.webserver 개체의 인스턴스를 반환 합니다. 반환 개체의 password 속성은 System.webserver입니다.
  
도메인 관리자 암호의 일반 텍스트를 가져오려면 해당 암호가 호스트 서버의 현재 로그온 계정에 의해 입력 되었는지 확인 하 고 PowerShell 콘솔을 관리자로 열고 아래 스크립트를 실행 합니다.
  
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
| 유형 <br/> |필수  <br/> | System.String <br/> | AccountType 값은 다음 중 하나가 될 수 있습니다. <br/>  VmAdmin: 클라우드 커넥터 가상 컴퓨터의 로컬 관리자입니다. <br/>  DomainAdmin: 클라우드 커넥터 가상 컴퓨터 도메인의 도메인 관리자입니다. <br/>  컴퓨터 관리: 클라우드 커넥터 가상 컴퓨터 도메인 컨트롤러의 컴퓨터 분리 Emodeadmin. <br/>  ExternalCert: Edge 서버에 설치 된 외부 인증서의 계정입니다. <br/>  TenantAdmin: O365 테 넌 트의 관리자. <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음. Get-CcCredential cmdlet은 파이프라인 입력을 허용 하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

Get-CcCredential cmdlet은 System.webserver 개체의 인스턴스를 반환 합니다.
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Set-CcCredential](set-cccredential.md)
  

