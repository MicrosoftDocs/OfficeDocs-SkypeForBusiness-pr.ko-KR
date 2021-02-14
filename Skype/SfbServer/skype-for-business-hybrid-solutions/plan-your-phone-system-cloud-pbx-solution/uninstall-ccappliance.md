---
title: Uninstall-CcAppliance
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
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: 이 Uninstall-CcAppliance cmdlet은 호스트 서버에서 실행 중인 비즈니스용 Skype 클라우드 커넥터 버전 어플라이언스를 제거합니다.
ms.openlocfilehash: c92ad5c31e2e254e4f10511835b6cc9f60c7c43c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824142"
---
# <a name="uninstall-ccappliance"></a>Uninstall-CcAppliance
 
이 Uninstall-CcAppliance cmdlet은 호스트 서버에서 실행 중인 비즈니스용 Skype 클라우드 커넥터 버전 어플라이언스를 제거합니다. 
  
```powershell
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a>예
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 예에서는 호스트 서버에서 Cloud Connector 어플라이언스를 드레인 및 제거합니다.
  
```powershell
Uninstall-CcAppliance
```

### <a name="example-2"></a>예 2

다음 예제에서는 드레인 프로세스가 실패한 경우에도 호스트 서버에서 실행 중인 Cloud Connector 어플라이언스를 드레인 및 강요하여 제거합니다.
  
```powershell
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a>예 3

다음 예에서는 사용자의 확인 없이 클라우드 커넥터 백업 버전을 제거합니다.
  
```powershell
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

현재 실행 중인 버전의 클라우드 커넥터를 설치하는 경우 드레인 서비스가 먼저 중재 서버 및 에지 서버에서 실행되어 가상 컴퓨터를 설치하기 전에 동시 통화가 완료됩니다. 백업 버전을 설치하는 경우 드레인이 수행되지 않습니다.
  
## <a name="parameters"></a>매개 변수
<a name="DetailedDescription"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
| 버전 <br/> | 옵션 <br/> |System.String  <br/> | 호스트 서버에서 제거될 클라우드 커넥터 버전입니다. 지정하지 않으면 현재 실행 중인 버전을 제거합니다. <br/> |
|Force  <br/> |선택  <br/> |System.Management.Automation.SwitchParameter  <br/> |현재 실행 중인 버전을 지우는 경우 가상 컴퓨터를 설치하기 전에 중재 서버 및 에지 서버에서 서버를 드레인합니다. "강제" 스위치를 지정하면 드레인 서비스가 실패한 경우에도 가상 컴퓨터는 제거됩니다. 이 매개 변수는 현재 실행 중인 버전을 제거하기 위해만 사용됩니다.  <br/> |
|확인  <br/> |선택  <br/> |System.Management.Automation.SwitchParameter  <br/> |가상 컴퓨터를 제거하도록 사용자의 확인을 요청합니다. 기본값은 TRUE입니다.  <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음 이 Uninstall-CcAppliance cmdlet은 파이프라인된 입력을 허용하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Install-CcAppliance](install-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  

