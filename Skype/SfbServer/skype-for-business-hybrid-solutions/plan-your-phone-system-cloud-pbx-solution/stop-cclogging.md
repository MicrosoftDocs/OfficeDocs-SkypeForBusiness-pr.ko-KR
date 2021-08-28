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
ms.localizationpriority: medium
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: 이 Stop-CcLogging cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 어플라이언스에 대한 수신 및 발신 통화 로그 생성을 비즈니스용 Skype 클라우드 커넥터 버전 중지합니다.
ms.openlocfilehash: cfa07602f8465ce3c931010f835f52acc44e2ee2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580343"
---
# <a name="stop-cclogging"></a>Stop-CcLogging
 
이 Stop-CcLogging cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 어플라이언스에 대한 수신 및 발신 통화 로그 생성을 비즈니스용 Skype 클라우드 커넥터 버전 중지합니다.
  
```powershell
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 예에서는 수신 및 발신 통화 로그 생성을 중지합니다. 
  
```powershell
Stop-CcLogging
```

### <a name="example-2"></a>예 2

다음 예제에서는 수신 및 발신 호출 로그 생성을 중지하고 캐시 파일을 정리합니다.
  
```powershell
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

이 Stop-CcLogging cmdlet은 어플라이언스에서 수신 및 발신 전화 로깅을 중지합니다. 기본적으로 로깅은 4시간 후에 자동으로 중지됩니다.
  
## <a name="parameters"></a>매개 변수
<a name="DetailedDescription"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
| RemoveCache <br/> | 선택 <br/> | System.Management.Automation.SwitchParameter <br/> |로깅 캐시 파일을 제거합니다.  <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음 이 Stop-CcLogging cmdlet은 파이프라인된 입력을 허용하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Search-CcLog](search-cclog.md)
  
[Start-CcLogging](start-cclogging.md)
  

