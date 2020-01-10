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
localization_priority: Normal
ms.assetid: cd2889c4-0eb1-4752-9274-93a5a68a8080
description: 업데이트가 거의 만료 되거나 이미 만료 된 경우 업데이트-CcServerCertificate cmdlet이 비즈니스용 Skype 클라우드 커넥터 에디션의 인증서를 갱신 합니다.
ms.openlocfilehash: 920770b4ce77e893a7195d1326ea13ac73e0cc70
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003118"
---
# <a name="update-ccservercertificate"></a>Update-CcServerCertificate
 
업데이트가 거의 만료 되거나 이미 만료 된 경우 업데이트-CcServerCertificate cmdlet이 비즈니스용 Skype 클라우드 커넥터 에디션의 인증서를 갱신 합니다. 
  
```powershell
Update-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예제 1

다음 예제에서는 인증서가 거의 만료 되었거나 이미 만료 된 경우 중앙 관리 저장소, 중재 서버 및 Edge 서버의 인증서를 갱신 합니다.
  
```powershell
Update-CcServerCertificate
```

### <a name="example-2"></a>예제 2

다음 예에서는 중재 서버 및 Edge 서버의 인증서가 거의 만료 되거나 이미 만료 된 경우이를 갱신 합니다.
  
```powershell
Update-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

중앙 관리 저장소, 중재 서버 및 Edge 서버에 발급 된 클라우드 커넥터 내부 인증서는 인증 기관 서비스에서 발급 된 후 2 년 동안 유효 합니다. 인증서가 거의 만료 되거나 이미 만료 된 경우 업데이트-CcServerCertificate cmdlet을 실행 하 여 인증서를 갱신 합니다. 
  
이 명령은 클라우드 커넥터 2.0 및 이후 릴리스의 갱신-CcServerCertificate cmdlet을 대체 합니다.
  
## <a name="parameters"></a>매개 변수
<a name="DetailedDescription"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
|역할  <br/> |선택  <br/> |System. Array  <br/> | 클라우드 커넥터 서버 역할의 배열입니다. <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음. 업데이트-CcServerCertificate cmdlet은 파이프라인 입력을 허용 하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

