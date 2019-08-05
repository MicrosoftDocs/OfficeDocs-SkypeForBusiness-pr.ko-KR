---
title: 검색-CcLog
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bbae05f9-d8de-40dc-8968-d225dcde80e4
description: 검색-CcLog cmdlet는 비즈니스용 Skype 클라우드 커넥터 에디션 기기 로그 디렉터리에서 수신 및 발신 통화 기록을 검색 합니다.
ms.openlocfilehash: 7d1591953004ecf0e0d0a3bfdf2e998e06002325
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190653"
---
# <a name="search-cclog"></a>검색-CcLog
 
검색-CcLog cmdlet는 비즈니스용 Skype 클라우드 커넥터 에디션 기기 로그 디렉터리에서 수신 및 발신 통화 기록을 검색 합니다.
  
```
Search-CcLog [[-StartTime] <datetime>] [[-EndTime] <datetime>] [[-FileName] <string>]
```

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예제 1

다음 예에서는 기본 파일 이름을 사용 하 여 기기 로그 디렉터리의 수신 및 발신 통화 로그를 검색 합니다.
  
```
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM"
```

### <a name="example-2"></a>예제 2

다음 예제에서는 지정 된 파일 경로 및 이름을 사용 하 여 수신 및 발신 통화 로그를 검색 합니다.
  
```
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM" -FileName "C:\Log\LogFile.log"
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

검색-CsClsLogging cmdlet은 중앙 로깅 서비스에서 생성 된 로그 파일을 검색 하기 위한 명령줄 옵션을 제공 합니다.
  
## <a name="parameters"></a>매개 변수
<a name="DetailedDescription"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
|StartTime  <br/> | 필수 <br/> |시스템. 날짜/시간  <br/> | 검색할 로그 항목에 대 한 시작 날짜 및 시간입니다. 현지 표준 시간대에서 지정 합니다. <br/> |
|EndTime  <br/> |필수  <br/> |시스템. 날짜/시간  <br/> |검색할 로그 항목의 끝 날짜 및 시간입니다. 현지 표준 시간대에서 지정 합니다.  <br/> |
|이름이  <br/> |필수  <br/> |System.String  <br/> |검색 결과를 포함 하는 텍스트 파일의 전체 경로를 지정 합니다.  <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음. 검색-CcLog cmdlet은 파이프라인 입력을 허용 하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[시작-CcLogging](start-cclogging.md)
  
[중지-CcLogging](stop-cclogging.md)
  

