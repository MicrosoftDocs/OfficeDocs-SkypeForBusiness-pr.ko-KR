---
title: Get-CcApplianceDirectory
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
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: 이 Get-CcApplianceDirectory cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 호스트 서버에서 작업 디렉터리를 검색합니다. 모든 배포 파일은 이 디렉터리에 저장됩니다.
ms.openlocfilehash: 04764f312138132fb34c0979423da5dc4696ee63
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800848"
---
# <a name="get-ccappliancedirectory"></a>Get-CcApplianceDirectory
 
이 Get-CcApplianceDirectory cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 호스트 서버에서 작업 디렉터리를 검색합니다. 모든 배포 파일은 이 디렉터리에 저장됩니다. 
  
이 cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 1.4.1, 1.4.2에 적용됩니다.
  
```powershell
Get-CcApplianceDirectory
```

## <a name="parameters"></a>매개 변수

없음
  
## <a name="examples"></a>예
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 예에서는 클라우드 커넥터 구성 요소의 구성 및 가상 컴퓨터 파일이 저장되는 현재 폴더를 보여줍니다.
  
```powershell
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

이 Get-CcApplianceDirectory cmdlet은 클라우드 커넥터 어플라이언스에 대해 모든 구성 및 가상 컴퓨터 파일, 로그 및 외부 인증서가 저장되는 위치를 보여줍니다.
  
각 클라우드 커넥터 어플라이언스에는 중재 서버, 중앙 관리 저장소, 에지 서버 및 도메인 컨트롤러의 네 가지 구성 요소가 있습니다. 기본 폴더는 C:\Users \% userprofile%\CloudConnector\ApplianceRoot입니다. 이 폴더는 다음 cmdlet을 사용하여 변경할 Set-CCApplianceDirectory 있습니다.
  
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음 이 Get-CCApplianceDirectory cmdlet은 파이프라인된 입력을 허용하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

이 명령은 파일 경로를 반환합니다.
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

