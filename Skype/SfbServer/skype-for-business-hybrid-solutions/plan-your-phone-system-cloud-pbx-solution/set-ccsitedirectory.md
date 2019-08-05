---
title: 집합-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: Set-CcSiteDirectory cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션의 사이트 수준 구성 파일이 저장 되는 디렉터리를 설정 합니다. 폴더에 기본 VHD 및 클라우드 커넥터 구성 파일이 포함 됩니다.
ms.openlocfilehash: d2627da8bcd2cae5e388571457f4d6d9eb6813c9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190635"
---
# <a name="set-ccsitedirectory"></a>집합-CcSiteDirectory
 
Set-CcSiteDirectory cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션의 사이트 수준 구성 파일이 저장 되는 디렉터리를 설정 합니다. 폴더에 기본 VHD 및 클라우드 커넥터 구성 파일이 포함 됩니다.
  
이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 1.4.1, 1.4.2에 적용 됩니다.
  
```
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예제 1

다음 예에서는 사이트 루트 디렉토리를 SiteShare\CloudConnector로 \\설정 합니다.
  
```
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

게이트웨이 선호도 및 고가용성을 제공 하기 위해 사이트에서 클라우드 커넥터 기기를 결합할 수 있습니다. 클라우드 커넥터 기기 대신 사용자가 사이트에 할당 됩니다. 각 사이트에는 기본 VHD 및 클라우드 커넥터 설치 파일이 저장 되어 있는 공유 폴더가 있습니다. 기기는 배포 중에이 폴더를 사용 합니다. 이 폴더는 클라우드 커넥터 사이트의 다른 모든 기기와 공유 되어야 합니다.
  
기본 폴더는 C:\Users\%userprofile%\CloudConnector\SiteRoot. Path는 Get-CcSiteDirectory cmdlet을 사용 하 여 볼 수 있습니다.
  
## <a name="parameters"></a>매개 변수
<a name="DetailedDescription"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
| 패스가 <br/> | 필수 <br/> | System.String <br/> |클라우드 커넥터 사이트 파일이 저장 되는 폴더의 경로를 제공 합니다.  <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음. Set-CcSiteDirectory cmdlet은 파이프라인 입력을 허용 하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Get-CcSiteDirectory](get-ccsitedirectory.md)
  

