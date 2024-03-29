---
title: Export-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: 비즈니스용 Skype 클라우드 커넥터 버전 호스트 서버의 로컬 파일로 비즈니스용 Skype 클라우드 커넥터 버전 내보낼 수 있습니다.
ms.openlocfilehash: b2b3ea0171b68701b47b8ae2ed239f2e0495855b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625010"
---
# <a name="export-ccconfiguration"></a>Export-CcConfiguration
 
비즈니스용 Skype 클라우드 커넥터 버전 호스트 서버의 로컬 파일로 비즈니스용 Skype 클라우드 커넥터 버전 내보낼 수 있습니다.
  
```powershell
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 예제에서는 Path 매개 변수를 전체 파일 경로로 설정하고 구성을 해당 파일로 내보낼 수 있습니다.
  
```powershell
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a>자세한 정보
<a name="Examples"> </a>

이 Export-CcConfiguration cmdlet을 사용하면 클라우드 커넥터 구성을 선택한 경로의 파일에 저장할 수 있습니다. 이 명령은 Cloud Connector Edition 버전 2.0에서 도입되었습니다.
  
## <a name="parameters"></a>매개 변수
<a name="Examples"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
|경로  <br/> |필수  <br/> |System.String  <br/> |클라우드 커넥터 구성을 저장할 전체 파일 경로입니다.  <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="Examples"> </a>

없음 이 Export-CcConfiguration cmdlet은 파이프라인된 입력을 허용하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="Examples"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="Examples"> </a>

Import-CcConfiguration
  

