---
title: 제거-CcLegacyServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: CcLegacyServerCertificate cmdlet은 CcCACertificate 갱신 또는 CcServerCertificate cmdlet 갱신을 실행 한 후 중앙 관리 저장소, 중재 서버 및 Edge 서버에서 레거시 서버 인증서를 제거 합니다.
ms.openlocfilehash: ab332f6f0c88de01f59342002f6387ab8a83a13b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190686"
---
# <a name="remove-cclegacyservercertificate"></a>제거-CcLegacyServerCertificate
 
CcLegacyServerCertificate cmdlet은 CcCACertificate 갱신 또는 CcServerCertificate cmdlet 갱신을 실행 한 후 중앙 관리 저장소, 중재 서버 및 Edge 서버에서 레거시 서버 인증서를 제거 합니다.
  
```
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예제 1

다음 예제에서는 인증서를 갱신 한 후 중앙 관리 저장소, 중재 서버 및 Edge 서버에 대해 발급 된 레거시 인증서를 제거 합니다.
  
```
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a>예제 2

다음 예제에서는 인증서를 갱신 한 후 중재 서버와 Edge 서버에 대해 발급 된 인증서를 제거 합니다. 
  
```
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a>매개 변수
<a name="Examples"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
| 역할 <br/> |선택  <br/> |System. Array  <br/> | 클라우드 커넥터 서버 역할의 배열입니다. <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음. CcLegacyServerCertificate cmdlet은 파이프라인 입력을 허용 하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[갱신-CcServerCertificate](renew-ccservercertificate.md)
  
[다시 설정-CcCACertificate](reset-cccacertificate.md)
  
[갱신-CcCACertificate](renew-cccacertificate.md)
  
[업데이트-CcCACertificate](update-cccacertificate.md)
  

