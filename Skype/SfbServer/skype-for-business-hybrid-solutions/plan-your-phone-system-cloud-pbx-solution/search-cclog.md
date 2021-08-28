---
title: Search-CcLog
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: bbae05f9-d8de-40dc-8968-d225dcde80e4
description: 이 Search-CcLog cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 로그 디렉터리에서 수신 및 발신 통화 로그를 검색합니다.
ms.openlocfilehash: b96e0bea7c8a7ac9d3a12c135c828440eea9fb32
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618694"
---
# <a name="search-cclog"></a>Search-CcLog
 
이 Search-CcLog cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 로그 디렉터리에서 수신 및 발신 통화 로그를 검색합니다.
  
```powershell
Search-CcLog [[-StartTime] <datetime>] [[-EndTime] <datetime>] [[-FileName] <string>]
```

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 예에서는 기본 파일 이름을 사용하여 어플라이언스 로그 디렉터리의 수신 및 발신 통화 로그를 검색합니다.
  
```powershell
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM"
```

### <a name="example-2"></a>예 2

다음 예제에서는 지정한 파일 경로와 이름을 사용하여 수신 및 발신 통화 로그를 검색합니다.
  
```powershell
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM" -FileName "C:\Log\LogFile.log"
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

Search-CsClsLogging cmdlet은 중앙 로깅 서비스로 생성된 로그 파일을 검색하기 위한 명령줄 옵션을 제공합니다.
  
## <a name="parameters"></a>매개 변수
<a name="DetailedDescription"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
|StartTime  <br/> | 필수 <br/> |System.Datetime  <br/> | 로그 항목 검색 시작 날짜 및 시간입니다. 현지 표준 시간대로 지정됩니다. <br/> |
|EndTime  <br/> |필수  <br/> |System.Datetime  <br/> |로그 항목 검색 종료 날짜 및 시간입니다. 현지 표준 시간대로 지정됩니다.  <br/> |
|FileName  <br/> |필수  <br/> |System.String  <br/> |검색 결과가 포함된 텍스트 파일의 전체 경로를 지정합니다.  <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음 이 Search-CcLog cmdlet은 파이프라인된 입력을 허용하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Start-CcLogging](start-cclogging.md)
  
[Stop-CcLogging](stop-cclogging.md)
  

