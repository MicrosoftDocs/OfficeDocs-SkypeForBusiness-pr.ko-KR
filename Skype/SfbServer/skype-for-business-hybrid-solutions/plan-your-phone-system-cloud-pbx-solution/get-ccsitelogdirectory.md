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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: 이 Get-CcSiteLogDirectory cmdlet은 서버의 사이트 수준 로그가 저장되는 현재 디렉터리를 비즈니스용 Skype 클라우드 커넥터 버전 표시됩니다.
ms.openlocfilehash: 7c15d0b715384fd18522122571da69f58a83ed337d46420e83f7ac35cfd0c018
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349520"
---
# <a name="get-ccsitelogdirectory"></a>Get-CcSiteLogDirectory
 
이 Get-CcSiteLogDirectory cmdlet은 서버의 사이트 수준 로그가 저장되는 현재 디렉터리를 비즈니스용 Skype 클라우드 커넥터 버전 표시됩니다. 
  
이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 1.4.1, 1.4.2에 적용됩니다.
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="parameters"></a>매개 변수

없음
  
## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 예에서는 클라우드 커넥터 사이트의 로그 파일이 저장되는 현재 폴더를 보여 주며,
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

기본 폴더는 C:\Users \% userprofile%\CloudConnector\SiteRoot\Logs입니다. cmdlet을 실행하여 폴더를 변경할 Set-CcSiteDirectory 있습니다. 사이트 디렉터리를 변경하지 않고 로그 폴더 위치만 변경하는 별도의 cmdlet은 없습니다.
  
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음 이 Get-CcSiteLogDirectory cmdlet은 파이프라인된 입력을 허용하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

명령은 파일 경로를 반환합니다.
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

