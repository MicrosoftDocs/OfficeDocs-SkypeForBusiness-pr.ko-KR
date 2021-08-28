---
title: Exit-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: 이 Exit-CcUpdate cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 호스트 서버에서 업데이트 유지 관리 모드를 종료합니다.
ms.openlocfilehash: 11499950a3332de31fe045ea23c1aa8f567da072
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625020"
---
# <a name="exit-ccupdate"></a>Exit-CcUpdate
 
이 Exit-CcUpdate cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 호스트 서버에서 업데이트 유지 관리 모드를 종료합니다. 
  
이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 1.4.1, 1.4.2에 적용됩니다. 
  
```powershell
Exit-CcUpdate
```

## <a name="parameters"></a>매개 변수

없음
  
## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 명령은 어플라이언스가 실행되는 어플라이언스를 프로덕션 모드로 전환합니다. 
  
```powershell
Exit-CcUpdate
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

Enter-CcUpdate cmdlet을 지정하여 유지 관리 모드를 설정한 어플라이언스가 있는 경우 Exit-CcUpdate cmdlet은 이러한 제품을 프로덕션 모드로 다시 전환합니다. 
  
유지 관리 모드로 어플라이언스를 설정하는 자세한 내용은 Enter-CcUpdate를 참조하세요.
  
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음 이 Exit-CcUpdate cmdlet은 파이프라인된 입력을 허용하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음 
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Enter-CcUpdate](enter-ccupdate.md)
  

