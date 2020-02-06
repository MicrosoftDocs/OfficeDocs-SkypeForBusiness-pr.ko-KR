---
title: Get-CcApplianceLogDirectory
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
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: CcApplianceLogDirectory cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 기기에 대 한 로그가 저장 되어 있는 현재 디렉터리를 표시 합니다.
ms.openlocfilehash: 284846bbc305d76602ae1e2f065fcdd571c9deb2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800828"
---
# <a name="get-ccappliancelogdirectory"></a>Get-CcApplianceLogDirectory
 
CcApplianceLogDirectory cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 기기에 대 한 로그가 저장 되어 있는 현재 디렉터리를 표시 합니다.
  
이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 1.4.1, 1.4.2에 적용 됩니다.
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a>매개 변수

없음
  
## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예제 1

다음 예에서는 클라우드 커넥터의 현재 기기에 대 한 로그가 저장 되어 있는 현재 폴더를 보여 줍니다.
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

CcApplianceLogDirectory cmdlet은 클라우드 커넥터 기기에 대 한 로그가 저장 되는 현재 디렉터리를 표시 합니다. 기본 폴더는 C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs. 
  
Set-CcApplianceDirectory cmdlet을 사용 하 여 디렉터리를 변경할 수 있습니다. 
  
참고: 기기 디렉터리를 변경 하지 않고 로그 폴더 위치만 변경 하는 cmdlet은 없습니다.
  
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음. Get-CcApplianceLogDirectory cmdlet은 파이프라인 입력을 허용 하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

이 명령은 파일 경로를 반환 합니다.
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

