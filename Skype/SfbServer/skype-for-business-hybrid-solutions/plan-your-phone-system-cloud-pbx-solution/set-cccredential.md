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
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: 설정-CcCredential cmdlet은 현재 비즈니스용 Skype 클라우드 커넥터 에디션 배포의 자격 증명을 설정 합니다.
ms.openlocfilehash: 3717eb0dcaa46bb6708f40ecb7f94869f24774a2
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221572"
---
# <a name="set-cccredential"></a>Set-CcCredential
 
설정-CcCredential cmdlet은 현재 비즈니스용 Skype 클라우드 커넥터 에디션 배포의 자격 증명을 설정 합니다. 
  
클라우드 커넥터 버전 2.0 이상을 사용 하는 경우이 cmdlet은 가상 컴퓨터 관리자 및 도메인 관리자에 대 한 계정 정보도 설정할 수 있습니다.
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 예에서는 테 넌 트 관리자의 계정 이름 및 암호를 지정 합니다.
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

Set-CcCredential cmdlet은 테 넌 트 관리자의 계정 이름 및 암호를 설정 합니다. 2.0 이전 버전의 경우이 관리자는 전역 관리자 여야 합니다. 클라우드 커넥터는이 계정을 사용 하 여 구성 정보를 가져오고, 구성 매개 변수를 설정 하 고, Microsoft 365 또는 Office 365 조직 구성으로 기기 상태를 업데이트 합니다. 릴리스 2.0 이상에서이 cmdlet을 사용 하 여 VmAdmin 및 DomainAdmin 계정의 암호를 업데이트할 수도 있습니다.
  
## <a name="parameters"></a>매개 변수 
<a name="DetailedDescription"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
| AccountType <br/> | 필수 <br/> |System.string  <br/> | 매개 변수 값은 "TenantAdmin", "VmAdmin" 또는 "DomainAdmin" 이어야 합니다. <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음 설정-CcCredential cmdlet은 파이프라인 된 입력을 허용 하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Get-CcCredential](get-cccredential.md)
  

