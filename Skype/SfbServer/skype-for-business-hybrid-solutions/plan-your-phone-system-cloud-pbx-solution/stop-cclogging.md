---
title: Stop-CcLogging
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
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: CcLogging 중지 cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 기기의 수신 및 발신 통화 로그 생성을 중지 합니다.
ms.openlocfilehash: 8a012e9b1a94c3698cc61da4326eb0ccbb27bca2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824162"
---
# <a name="stop-cclogging"></a>Stop-CcLogging
 
CcLogging 중지 cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 기기의 수신 및 발신 통화 로그 생성을 중지 합니다.
  
```powershell
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예제 1

다음 예제에서는 수신 및 발신 통화 로그의 생성을 중지 합니다. 
  
```powershell
Stop-CcLogging
```

### <a name="example-2"></a>예제 2

다음 예제에서는 수신 및 발신 통화 로그 생성을 중지 하 고 캐시 파일을 정리 합니다.
  
```powershell
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

[Search-CcLog](search-cclog.md)
  
[Start-CcLogging](start-cclogging.md)
  

