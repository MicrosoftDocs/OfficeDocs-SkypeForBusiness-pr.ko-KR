---
title: 복원-CcCredentials
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: Cc-Credentials 복원 cmdlet은 현재 비즈니스용 Skype 클라우드 커넥터 에디션 배포의 모든 자격 증명을 복원 합니다.
ms.openlocfilehash: efa1bcda9af6abccd2ced0faf1e772e779a4483f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190656"
---
# <a name="restore-cccredentials"></a>복원-CcCredentials
 
Cc-Credentials 복원 cmdlet은 현재 비즈니스용 Skype 클라우드 커넥터 에디션 배포의 모든 자격 증명을 복원 합니다. 
  
이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 2.1에 적용 됩니다.
  
```
Restore-CcCredentials 
```

## <a name="detailed-description"></a>자세한 정보

Restore-CcCredentials cmdlet은 모든 자격 증명을 정리 하 고 현재 비즈니스용 Skype 클라우드 커넥터 배포에 사용 되는 모든 자격 증명을 다시 입력 하 라는 메시지를 표시 합니다.
  
## <a name="parameters"></a>매개 변수

없음
  
## <a name="input-types"></a>입력 형식

없음. Restore-CcCredentials cmdlet은 파이프라인 입력을 허용 하지 않습니다.
  
## <a name="return-types"></a>반환 형식

없음.
  
## <a name="example"></a>예

다음 예제에서는 현재 클라우드 커넥터 배포의 모든 자격 증명을 복원 합니다.
  
```
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a>참고 항목

[Get-CcCredential](get-cccredential.md)
  
[집합-CcCredential](set-cccredential.md)
  

