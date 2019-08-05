---
title: 중지-CcLogging
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: CcLogging 중지 cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 기기의 수신 및 발신 통화 로그 생성을 중지 합니다.
ms.openlocfilehash: dcc62e8ec772912a8275f5321a6c91e28dde8c25
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190617"
---
# <a name="stop-cclogging"></a>중지-CcLogging
 
CcLogging 중지 cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 기기의 수신 및 발신 통화 로그 생성을 중지 합니다.
  
```
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예제 1

다음 예제에서는 수신 및 발신 통화 로그의 생성을 중지 합니다. 
  
```
Stop-CcLogging
```

### <a name="example-2"></a>예제 2

다음 예제에서는 수신 및 발신 통화 로그 생성을 중지 하 고 캐시 파일을 정리 합니다.
  
```
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

CcLogging을 중지 하는 cmdlet은 기기의 수신 및 발신 통화 기록을 중지 합니다. 기본적으로 로깅이 4 시간 후에 자동으로 중지 됩니다.
  
## <a name="parameters"></a>매개 변수
<a name="DetailedDescription"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
| RemoveCache <br/> | 선택 <br/> | System.Management.Automation.SwitchParameter <br/> |로깅 캐시 파일을 제거 합니다.  <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음. ' CcLogging 중지 ' cmdlet은 파이프라인 입력을 허용 하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[검색-CcLog](search-cclog.md)
  
[시작-CcLogging](start-cclogging.md)
  

