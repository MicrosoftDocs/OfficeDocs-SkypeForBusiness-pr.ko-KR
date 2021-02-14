---
title: Import-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: 로컬 파일에서 클라우드 커넥터 호스트 서버로 비즈니스용 Skype 클라우드 커넥터 버전 구성을 가져올 수 있습니다.
ms.openlocfilehash: 626ba52d4d67f99dd67d3d1f91d26d6e6d03f95e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799858"
---
# <a name="import-ccconfiguration"></a>Import-CcConfiguration
 
로컬 파일에서 클라우드 커넥터 호스트 서버로 비즈니스용 Skype 클라우드 커넥터 버전 구성을 가져올 수 있습니다.
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a>예
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 예에서는 클라우드 CloudConnector.ini 어플라이언스 디렉터리의 응용 프로그램을 %SystemDrive%\ProgramData\CloudConnector 디렉터리에 복사합니다.
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a>자세한 정보
<a name="Examples"> </a>

이 cmdlet은 클라우드 CloudConnector.ini 어플라이언스 디렉터리의 응용 프로그램을 %SystemDrive%\ProgramData\CloudConnector 디렉터리로 복사합니다. 어플라이언스 디렉터리는 Set-CcApplianceDirectory 지정합니다. 이 cmdlet은 %SystemDrive%\ProgramData\CloudConnector의 기존 파일을 덮어 덮어 덮어 니다. 이 명령은 Cloud Connector Edition 버전 2.0.1 이상에 적용됩니다.
  
## <a name="parameters"></a>매개 변수
<a name="Examples"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
|Force  <br/> |선택  <br/> |System.Management.Automation.SwitchParameter  <br/> |알림 없이 %SystemDrive%\ProgramData\CloudConnector의 기존 파일을 덮어 니다.  <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="Examples"> </a>

없음 이 Import-CcConfiguration cmdlet은 파이프라인된 입력을 허용하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="Examples"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="Examples"> </a>

Export-CcConfiguration
  

