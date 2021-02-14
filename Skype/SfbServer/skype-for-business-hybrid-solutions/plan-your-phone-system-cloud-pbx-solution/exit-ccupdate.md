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
localization_priority: Normal
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: 이 Exit-CcUpdate 비즈니스용 Skype 클라우드 커넥터 버전 호스트 서버에서 업데이트 유지 관리 모드를 종료합니다.
ms.openlocfilehash: 315d6b7dccb6708901128bf8faa29a60f712e833
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801768"
---
# <a name="exit-ccupdate"></a>Exit-CcUpdate
 
이 Exit-CcUpdate 비즈니스용 Skype 클라우드 커넥터 버전 호스트 서버에서 업데이트 유지 관리 모드를 종료합니다. 
  
이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 1.4.1, 1.4.2에 적용됩니다. 
  
```powershell
Exit-CcUpdate
```

## <a name="parameters"></a>매개 변수

없음
  
## <a name="examples"></a>예
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 명령은 다시 실행되는 어플라이언스를 프로덕션 모드로 전환합니다. 
  
```powershell
Exit-CcUpdate
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

Enter-CcUpdate cmdlet을 지정하여 유지 관리 모드를 설정한 어플라이언스가 있는 경우 Exit-CcUpdate cmdlet은 이러한 어플라이언스를 프로덕션 모드로 다시 전환합니다. 
  
어플라이언스를 유지 관리 모드로 설정하는 자세한 내용은 Enter-CcUpdate를 참조하십시오.
  
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음 이 Exit-CcUpdate cmdlet은 파이프라인된 입력을 허용하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음 
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Enter-CcUpdate](enter-ccupdate.md)
  

