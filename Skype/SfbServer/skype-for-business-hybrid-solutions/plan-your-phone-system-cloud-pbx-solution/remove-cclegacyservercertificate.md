---
title: Remove-CcLegacyServerCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/22/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ff21cecb-5035-48fd-9705-11ea81ce7df6
description: Remove-CcLegacyServerCertificate cmdlet은 Renew-CcCACertificate 또는 Renew CcServerCertificate cmdlet을 실행한 후 중앙 관리 저장소, 중재 서버 및 에지 서버에서 레거시 서버 인증서를 제거합니다.
ms.openlocfilehash: 93df3e8658cecdb4a6cc8b14d59d61a716dab8fc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589952"
---
# <a name="remove-cclegacyservercertificate"></a>Remove-CcLegacyServerCertificate
 
Remove-CcLegacyServerCertificate cmdlet은 Renew-CcCACertificate 또는 Renew CcServerCertificate cmdlet을 실행한 후 중앙 관리 저장소, 중재 서버 및 에지 서버에서 레거시 서버 인증서를 제거합니다.
  
```powershell
Remove-CcLegacyServerCertificate [[-Roles] <array> {Cms | MS | Edge}] 
```

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 예에서는 인증서를 갱신한 후 중앙 관리 저장소, 중재 서버 및 에지 서버에 대해 발급된 레거시 인증서를 제거합니다.
  
```powershell
Remove-CcLegacyServerCertificate
```

### <a name="example-2"></a>예 2

다음 예에서는 인증서를 갱신한 후 중재 서버 및 에지 서버에 대해 발급된 인증서를 제거합니다. 
  
```powershell
Remove-CcLegacyServerCertificate -Roles @("MS", "Edge") 
```

## <a name="parameters"></a>매개 변수
<a name="Examples"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
| 역할 <br/> |선택  <br/> |System.Array  <br/> | 클라우드 커넥터 서버 역할의 배열입니다. <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음 이 Remove-CcLegacyServerCertificate cmdlet은 파이프라인된 입력을 허용하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Renew-CcServerCertificate](renew-ccservercertificate.md)
  
[Reset-CcCACertificate](reset-cccacertificate.md)
  
[Renew-CcCACertificate](renew-cccacertificate.md)
  
[Update-CcCACertificate](update-cccacertificate.md)
  

