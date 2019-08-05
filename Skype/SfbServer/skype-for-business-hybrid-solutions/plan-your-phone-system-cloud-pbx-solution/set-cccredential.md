---
title: 집합-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: 집합-CcCredential cmdlet은 현재 비즈니스용 Skype 클라우드 커넥터 에디션 배포의 자격 증명을 설정 합니다.
ms.openlocfilehash: 59c058f8965bbc6fc011806f383c547c1e7b6cd1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190647"
---
# <a name="set-cccredential"></a>집합-CcCredential
 
집합-CcCredential cmdlet은 현재 비즈니스용 Skype 클라우드 커넥터 에디션 배포의 자격 증명을 설정 합니다. 
  
클라우드 커넥터 버전 2.0 이상을 사용 하는 경우이 cmdlet은 가상 컴퓨터 관리자와 도메인 관리자에 대 한 계정 정보도 설정할 수 있습니다.
  
```
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예제 1

다음 예에서는 테 넌 트 관리자의 계정 이름 및 암호를 지정 합니다.
  
```
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

집합-CcCredential cmdlet은 테 넌 트 관리자의 계정 이름 및 암호를 설정 합니다. 2.0 이전 버전의 경우이 관리자는 Office 365 전역 관리자 여야 합니다. 클라우드 커넥터는이 계정을 사용 하 여 구성 정보를 가져오고, 구성 매개 변수를 설정 하 고, Office 365 테 넌 트 구성으로 기기 상태를 업데이트 합니다. 릴리스 2.0 이상에서는이 cmdlet을 사용 하 여 VmAdmin 및 DomainAdmin 계정에 대 한 암호를 업데이트할 수도 있습니다.
  
## <a name="parameters"></a>매개 변수
<a name="DetailedDescription"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
| 유형 <br/> | 필수 <br/> |System.String  <br/> | 매개 변수 값은 "TenantAdmin", "VmAdmin" 또는 "DomainAdmin" 이어야 합니다. <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음. Set-CcCredential cmdlet은 파이프라인 입력을 허용 하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Get-CcCredential](get-cccredential.md)
  

