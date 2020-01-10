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
localization_priority: Normal
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: CcUpdate cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 호스트 서버에서 업데이트 유지 관리 모드를 종료 합니다.
ms.openlocfilehash: f79023c50e951e6678abdccc29b12cb30a329dfc
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003448"
---
# <a name="exit-ccupdate"></a>Exit-CcUpdate
 
CcUpdate cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 호스트 서버에서 업데이트 유지 관리 모드를 종료 합니다. 
  
이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 1.4.1, 1.4.2에 적용 됩니다. 
  
```powershell
Exit-CcUpdate
```

## <a name="parameters"></a>매개 변수

없음
  
## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예제 1

다음 명령은 프로덕션 모드로 다시 실행 되는 기기를 배치 합니다. 
  
```powershell
Exit-CcUpdate
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

-CcUpdate cmdlet을 지정 하 여 유지 관리 모드에 있는 기기를 사용 하는 경우에는이를 프로덕션 모드에 다시 포함 합니다. 
  
유지 관리 모드에 기기를 배치 하는 방법에 대 한 자세한 내용은-CcUpdate 입력을 참조 하세요.
  
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음. CcUpdate cmdlet은 파이프라인 입력을 허용 하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음 
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Enter-CcUpdate](enter-ccupdate.md)
  

