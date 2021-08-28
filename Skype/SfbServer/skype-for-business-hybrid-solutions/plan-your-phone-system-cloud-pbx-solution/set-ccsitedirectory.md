---
title: Set-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: 이 Set-CcSiteDirectory cmdlet은 서버의 사이트 수준 구성 파일이 비즈니스용 Skype 클라우드 커넥터 버전 디렉터리를 설정합니다. 폴더에는 기본 VHD 및 클라우드 커넥터 구성 파일이 포함되어 있습니다.
ms.openlocfilehash: e5685ac8c203338365141a4a7ba59daa82a06ef0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58610535"
---
# <a name="set-ccsitedirectory"></a>Set-CcSiteDirectory
 
이 Set-CcSiteDirectory cmdlet은 서버의 사이트 수준 구성 파일이 비즈니스용 Skype 클라우드 커넥터 버전 디렉터리를 설정합니다. 폴더에는 기본 VHD 및 클라우드 커넥터 구성 파일이 포함되어 있습니다.
  
이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 1.4.1, 1.4.2에 적용됩니다.
  
```powershell
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 예에서는 사이트 루트 디렉터리를 \\ SiteShare\CloudConnector로 설정합니다.
  
```powershell
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

게이트웨이 관련성 및 고가용성을 제공하기 위해 Cloud Connector 어플라이언스를 사이트에 결합할 수 있습니다. 사용자는 클라우드 커넥터 어플라이언스 대신 사이트에 할당됩니다. 각 사이트에는 기본 VHD 및 클라우드 커넥터 설치 파일이 저장되는 공유 폴더가 있습니다. 어플라이언스에서는 배포 중에 이 폴더를 사용하게 됩니다. 이 폴더는 클라우드 커넥터 사이트의 다른 모든 어플라이언스와 공유해야 합니다.
  
기본 폴더는 C:\Users \% userprofile%\CloudConnector\SiteRoot입니다. 경로는 cmdlet을 사용하여 볼 Get-CcSiteDirectory 있습니다.
  
## <a name="parameters"></a>매개 변수
<a name="DetailedDescription"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
| 경로 <br/> | 필수 <br/> | System.String <br/> |클라우드 커넥터 사이트 파일이 저장될 폴더의 경로를 제공합니다.  <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음 이 Set-CcSiteDirectory cmdlet은 파이프라인된 입력을 허용하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Get-CcSiteDirectory](get-ccsitedirectory.md)
  

