---
title: 수출-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: 비즈니스용 skype 클라우드 커넥터 에디션 구성을 비즈니스용 Skype 클라우드 커넥터 에디션 호스트 서버의 로컬 파일로 내보냅니다.
ms.openlocfilehash: 7548b2fba602364d98c7540607660ccc57710654
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190824"
---
# <a name="export-ccconfiguration"></a>수출-CcConfiguration
 
비즈니스용 skype 클라우드 커넥터 에디션 구성을 비즈니스용 Skype 클라우드 커넥터 에디션 호스트 서버의 로컬 파일로 내보냅니다.
  
```
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예제 1

다음 예제에서는 경로 매개 변수를 전체 파일 경로로 설정 하 고 구성을 해당 파일로 내보냅니다.
  
```
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a>자세한 정보
<a name="Examples"> </a>

수출-CcConfiguration cmdlet을 사용 하 여 클라우드 커넥터 구성을 선택한 경로에 있는 파일에 저장할 수 있습니다. 이 명령은 클라우드 커넥터 버전 2.0에서 도입 되었습니다.
  
## <a name="parameters"></a>매개 변수
<a name="Examples"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
|패스가  <br/> |필수  <br/> |System.String  <br/> |클라우드 커넥터 구성이 저장 되는 전체 파일 경로입니다.  <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="Examples"> </a>

없음. 수출-CcConfiguration cmdlet은 파이프라인 입력을 허용 하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="Examples"> </a>

없음.
  
## <a name="see-also"></a>참고 항목
<a name="Examples"> </a>

가져오기-CcConfiguration
  

