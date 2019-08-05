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
localization_priority: Normal
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: CcApplianceDirectory cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 호스트 서버에서 작업 디렉터리를 설정 합니다. 모든 배포 파일은이 디렉터리에 저장 됩니다.
ms.openlocfilehash: 56a13da740b0c23adee7e05ddbcc1bbc82f0f1cc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190650"
---
# <a name="set-ccappliancedirectory"></a>Set-CcApplianceDirectory
 
CcApplianceDirectory cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 호스트 서버에서 작업 디렉터리를 설정 합니다. 모든 배포 파일은이 디렉터리에 저장 됩니다.
  
```
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예제 1

다음 예에서는 호스트 서버의 작업 디렉터리를 c:\cloudconnector\applianceroot로 설정 합니다.
  
```
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a>매개 변수
<a name="Examples"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
| 패스가 <br/> | 필수 <br/> |System.String  <br/> | 모든 배포 파일이 저장 되는 경로를 지정 합니다. <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음. CcApplianceDirectory cmdlet은 파이프라인 입력을 허용 하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

없음
  

