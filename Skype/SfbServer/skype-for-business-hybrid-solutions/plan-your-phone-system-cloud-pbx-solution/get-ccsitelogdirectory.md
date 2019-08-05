---
title: Get-CcSiteLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: Get-CcSiteLogDirectory cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션의 사이트 수준 로그가 저장 되는 현재 디렉터리를 표시 합니다.
ms.openlocfilehash: bc47c2ea2d81e70538305daa98f97a35cf3d9e0a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190770"
---
# <a name="get-ccsitelogdirectory"></a>Get-CcSiteLogDirectory
 
Get-CcSiteLogDirectory cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션의 사이트 수준 로그가 저장 되는 현재 디렉터리를 표시 합니다. 
  
이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 1.4.1, 1.4.2에 적용 됩니다.
  
```
Get-CcSiteLogDirectory
```

## <a name="parameters"></a>매개 변수

없음
  
## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예제 1

다음 예제에서는 클라우드 커넥터 사이트의 로그 파일이 저장 되어 있는 현재 폴더를 보여 줍니다.
  
```
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

기본 폴더는 C:\Users\%userprofile%\CloudConnector\SiteRoot\Logs. Set-CcSiteDirectory cmdlet을 실행 하 여 폴더를 변경할 수 있습니다. 사이트 디렉터리를 변경 하지 않고 로그 폴더 위치만 변경 하는 별도의 cmdlet은 없습니다.
  
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음. Get-CcSiteLogDirectory cmdlet은 파이프라인 입력을 허용 하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

이 명령은 파일 경로를 반환 합니다.
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[집합-CcSiteDirectory](set-ccsitedirectory.md)
  

