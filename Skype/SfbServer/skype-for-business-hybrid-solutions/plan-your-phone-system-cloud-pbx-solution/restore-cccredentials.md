---
title: Restore-CcCredentials
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: Restore Cc-Credentials cmdlet은 현재 배포의 모든 자격 증명을 비즈니스용 Skype 클라우드 커넥터 버전 복원합니다.
ms.openlocfilehash: 050c4265bff7673a7db620ff41a56a2735d6b4a7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58588440"
---
# <a name="restore-cccredentials"></a>Restore-CcCredentials
 
Restore Cc-Credentials cmdlet은 현재 배포의 모든 자격 증명을 비즈니스용 Skype 클라우드 커넥터 버전 복원합니다. 
  
이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 2.1에 적용됩니다.
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a>자세한 정보

이 Restore-CcCredentials cmdlet은 모든 자격 증명을 정리하고 현재 클라우드 커넥터 배포에 사용되는 모든 자격 증명을 비즈니스용 Skype 다시 입력하라는 메시지를 제공합니다.
  
## <a name="parameters"></a>매개 변수

없음
  
## <a name="input-types"></a>입력 형식

없음 이 Restore-CcCredentials cmdlet은 파이프라인된 입력을 허용하지 않습니다.
  
## <a name="return-types"></a>반환 형식

없음
  
## <a name="example"></a>예제

다음 예에서는 현재 클라우드 커넥터 배포의 모든 자격 증명을 복원합니다.
  
```powershell
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a>참고 항목

[Get-CcCredential](get-cccredential.md)
  
[Set-CcCredential](set-cccredential.md)
  

