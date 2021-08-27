---
title: Set-CcCredential
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
ms.localizationpriority: medium
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: 이 Set-CcCredential cmdlet은 현재 배포에 대한 비즈니스용 Skype 클라우드 커넥터 버전 설정합니다.
ms.openlocfilehash: fa0d5f69e3263d273fabe17ae74ea46e0af40908
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617670"
---
# <a name="set-cccredential"></a>Set-CcCredential
 
이 Set-CcCredential cmdlet은 현재 배포에 대한 비즈니스용 Skype 클라우드 커넥터 버전 설정합니다. 
  
클라우드 커넥터 버전 2.0 이상을 사용할 경우 이 cmdlet은 가상 컴퓨터 관리자 및 도메인 관리자에 대한 계정 정보를 설정할 수도 있습니다.
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 예에서는 테넌트 관리자의 계정 이름과 암호를 지정합니다.
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

이 Set-CcCredential cmdlet은 테넌트 관리자의 계정 이름과 암호를 설정합니다. 2.0 이전 릴리스의 경우 이 관리자는 전역 관리자 되어야 합니다. 클라우드 커넥터는 이 계정을 사용하여 구성 정보를 얻거나, 구성 매개 변수를 설정하고, 어플라이언스 상태를 조직 구성의 Microsoft 365 Office 365 업데이트합니다. 릴리스 2.0 이상에서는 이 cmdlet을 사용하여 VmAdmin 및 DomainAdmin 계정의 암호를 업데이트할 수도 있습니다.
  
## <a name="parameters"></a>매개 변수
<a name="DetailedDescription"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> | 필수 <br/> |System.String  <br/> | 매개 변수 값은 "TenantAdmin", "VmAdmin" 또는 "DomainAdmin"입니다. <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음 이 Set-CcCredential cmdlet은 파이프라인된 입력을 허용하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Get-CcCredential](get-cccredential.md)
  

