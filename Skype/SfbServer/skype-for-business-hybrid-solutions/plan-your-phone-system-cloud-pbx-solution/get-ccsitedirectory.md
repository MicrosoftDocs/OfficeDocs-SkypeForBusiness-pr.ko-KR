---
title: Get-CcSiteDirectory
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
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: 이 Get-CcSiteDirectory cmdlet은 사이트 수준 구성 파일이 저장되는 현재 디렉터리를 보여줍니다. 폴더에는 기본 VHD 및 비즈니스용 Skype 클라우드 커넥터 버전 설치 파일이 포함되어 있습니다. 이 폴더는 클라우드 커넥터 사이트의 다른 모든 어플라이언스와 공유해야 합니다.
ms.openlocfilehash: 6722b66f6c71feec158adaf442f9e57ef9943c84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799868"
---
# <a name="get-ccsitedirectory"></a>Get-CcSiteDirectory
 
이 Get-CcSiteDirectory cmdlet은 사이트 수준 구성 파일이 저장되는 현재 디렉터리를 보여줍니다. 폴더에는 기본 VHD 및 비즈니스용 Skype 클라우드 커넥터 버전 설치 파일이 포함되어 있습니다. 이 폴더는 클라우드 커넥터 사이트의 다른 모든 어플라이언스와 공유해야 합니다.
  
이 cmdlet은 Cloud Connector Edition 1.4.1, 1.4.2에 적용됩니다.
  
```powershell
Get-CcSiteDirectory
```

## <a name="parameters"></a>매개 변수

없음
  
## <a name="examples"></a>예
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 예에서는 클라우드 커넥터 구성 요소의 구성 및 가상 컴퓨터 파일이 저장되는 현재 폴더를 보여줍니다.
  
```powershell
Get-CcSiteDirectory
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

게이트웨이 관련성 및 고가용성을 제공하기 위해 Cloud Connector 어플라이언스를 사이트에 결합할 수 있습니다. 사용자는 클라우드 커넥터 어플라이언스 대신 사이트에 할당됩니다. 각 사이트에는 기본 VHD 및 클라우드 커넥터 설치 파일이 저장되는 공유 폴더가 있습니다. 어플라이언스에서는 배포 중에 이 폴더를 사용하게 됩니다. 기본 폴더는 C:\Users \% userprofile%\CloudConnector\SiteRoot입니다. 이 cmdlet을 사용하여 경로를 변경할 Set-CcSiteDirectory 있습니다.
  
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음 이 Get-CcSiteDirectory cmdlet은 파이프라인된 입력을 허용하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

이 명령은 파일 경로를 반환합니다.
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

