---
title: Renew-CcServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7844b55e-b7e9-4599-9962-f0322728405a
description: 이 Renew-CcServerCertificate cmdlet은 만료 거의 또는 이미 만료된 비즈니스용 Skype 클라우드 커넥터 버전에 대한 인증서를 갱신합니다. 이 명령은 클라우드 커넥터 2.0 Update-CcServerCertificate 릴리스에서 이 명령으로 변경되었습니다.
ms.openlocfilehash: e4f3f4bbf0904733cf39f71534115543ff15fa65
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824264"
---
# <a name="renew-ccservercertificate"></a>Renew-CcServerCertificate
 
이 Renew-CcServerCertificate cmdlet은 만료 거의 또는 이미 만료된 비즈니스용 Skype 클라우드 커넥터 버전에 대한 인증서를 갱신합니다. 이 명령은 클라우드 커넥터 2.0 Update-CcServerCertificate 릴리스에서 이 명령으로 변경되었습니다. 
  
```powershell
Renew-CcServerCertificate [[-Roles] <array> {Cms | MS | Edge}]
```

## <a name="examples"></a>예
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 예에서는 인증서가 만료 거의 또는 이미 만료된 경우 중앙 관리 저장소, 중재 서버 및 에지 서버의 인증서를 갱신합니다.
  
```powershell
Renew-CcServerCertificate
```

### <a name="example-2"></a>예 2

다음 예에서는 만료 거의 또는 이미 만료된 중재 서버 및 에지 서버에 대한 인증서를 갱신합니다.
  
```powershell
Renew-CcServerCertificate-Roles @("MS", "Edge")
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

중앙 관리 저장소, 중재 서버 및 에지 서버에 발급된 클라우드 커넥터 내부 인증서는 인증 기관 서비스에서 발급된 후 2년 동안 유효합니다. 인증서가 만료 거의 또는 이미 만료된 경우 인증서를 Renew-CcServerCertificate cmdlet을 실행하여 인증서를 갱신합니다. 
  
## <a name="parameters"></a>매개 변수
<a name="DetailedDescription"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
|역할  <br/> |선택  <br/> |System.Array  <br/> | 클라우드 커넥터 서버 역할의 배열입니다. <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음 이 Renew-CcServerCertificate cmdlet은 파이프라인된 입력을 허용하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Export-CcRootCertificate](export-ccrootcertificate.md)
  

