---
title: Set-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: 이 Set-CcApplianceDirectory cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 호스트 서버에 작업 디렉터리를 설정합니다. 모든 배포 파일은 이 디렉터리에 저장됩니다.
ms.openlocfilehash: 8ca6b8b8e175058e5f19c86a9dd1c6e0cf8a43ab6ef7a439eee4e09b5430f6a2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306599"
---
# <a name="set-ccappliancedirectory"></a>Set-CcApplianceDirectory
 
이 Set-CcApplianceDirectory cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 호스트 서버에 작업 디렉터리를 설정합니다. 모든 배포 파일은 이 디렉터리에 저장됩니다.
  
```powershell
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 예에서는 호스트 서버의 작업 디렉터리를 c:\cloudconnector\applianceroot로 설정합니다.
  
```powershell
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a>매개 변수
<a name="Examples"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
| 경로 <br/> | 필수 <br/> |System.String  <br/> | 모든 배포 파일이 저장되는 경로를 지정합니다. <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음 이 Set-CcApplianceDirectory cmdlet은 파이프라인된 입력을 허용하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

없음
  

