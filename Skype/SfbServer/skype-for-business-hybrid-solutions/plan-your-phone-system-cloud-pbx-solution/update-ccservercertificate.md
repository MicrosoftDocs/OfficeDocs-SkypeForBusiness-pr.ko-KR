---
title: Update-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/11/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: 이 Update-CcServerCertificate 만료되거나 이미 만료된 비즈니스용 Skype 클라우드 커넥터 버전 인증서를 갱신합니다.
ms.openlocfilehash: 1e8afb05d691a1e3e696b619c816cfc45dd26f1e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623380"
---
# <a name="update-ccservercertificate"></a>Update-CcServerCertificate
 
이 Update-CcServerCertificate 만료되거나 이미 만료된 비즈니스용 Skype 클라우드 커넥터 버전 인증서를 갱신합니다. 
  
```powershell
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 예제에서는 인증서가 만료 거의 또는 이미 만료된 경우 중앙 관리 저장소, 중재 서버 및 에지 서버의 인증서를 갱신합니다.
  
```powershell
Update-CcServerCertificate
```

### <a name="example-2"></a>예 2

다음 예에서는 만료 날짜가 다가오거나 이미 만료되면 중재 서버 및 에지 서버에 대한 인증서를 갱신합니다.
  
```powershell
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

중앙 관리 저장소, 중재 서버 및 에지 서버에 발급된 클라우드 커넥터 내부 인증서는 인증 기관 서비스에서 발급된 후 2년 동안 유효합니다. 인증서가 만료 거의 또는 이미 만료된 경우 인증서를 Update-CcServerCertificate cmdlet을 실행하여 인증서를 갱신합니다. 
  
이 명령은 cloud connector 2.0 Renew-CcServerCertificate 릴리스의 cmdlet을 대체합니다.
  
## <a name="parameters"></a>매개 변수
<a name="DetailedDescription"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
|역할  <br/> |선택  <br/> |System.Array  <br/> | 클라우드 커넥터 서버 역할의 배열입니다. <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음 이 Update-CcServerCertificate cmdlet은 파이프라인된 입력을 허용하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

