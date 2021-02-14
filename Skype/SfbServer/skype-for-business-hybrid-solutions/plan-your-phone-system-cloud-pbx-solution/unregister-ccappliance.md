---
title: Unregister-CcAppliance
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
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: 이 Unregister-CcAppliance cmdlet은 온라인 테넌트 구성의 PSTN 사이트에서 현재 비즈니스용 Skype 클라우드 커넥터 버전 어플라이언스 등록을 등록을 해지합니다.
ms.openlocfilehash: 84a25321b6affda6b8783c40baa18a91b5b95ef5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824132"
---
# <a name="unregister-ccappliance"></a>Unregister-CcAppliance
 
이 Unregister-CcAppliance cmdlet은 온라인 테넌트 구성의 PSTN 사이트에서 현재 비즈니스용 Skype 클라우드 커넥터 버전 어플라이언스 등록을 등록을 해지합니다.
  
```powershell
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>예
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 예에서는 온라인 테넌트 구성에서 현재 어플라이언스 등록을 등록을 해지합니다.
  
```powershell
Unregister-CcAppliance
```

### <a name="example-2"></a>예 2

다음 예제에서는 온라인 테넌트 구성에 연결하지 않고 구성에서 로컬로 등록을 등록을 하지 않는지 검사합니다.
  
```powershell
Unregister-CcAppliance -Local
```

### <a name="example-3"></a>예 3

다음 예제에서는 이름이 "Appliance1"인 현재 어플라이언스를 PSTN 사이트 "Site1"에 등록을 등록하지 않습니다.
  
```powershell
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

Register-CcAppliance cmdlet과 마찬가지로 사이트 이름과 에지 서버 외부 FQDN을 CloudConnector.ini PSTN 사이트 ID로 간주됩니다. 마찬가지로, CloudConnector.ini 파일의 중재 서버 FQDN과 결합된 ApplianceName은 어플라이언스 ID로 간주됩니다.
  
어플라이언스가 등록되지 않은 후 클라우드 커넥터 관리 서비스를 다시 시작하고 NetworkService 계정으로 로그온합니다.
  
## <a name="parameters"></a>매개 변수
<a name="DetailedDescription"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
| SiteName <br/> |옵션  <br/> |System.String  <br/> |어플라이언스가 등록된 PSTN 사이트 이름입니다. 기본값은 파일에서 SiteName CloudConnector.ini 있습니다.  <br/> |
|ApplianceName  <br/> |옵션  <br/> |System.String  <br/> |현재 어플라이언스 이름입니다. 기본값은 호스트 서버의 컴퓨터 이름입니다.  <br/> |
|로컬  <br/> |선택  <br/> |System.Management.Automation.SwitchParameter  <br/> |온라인 테넌트 구성에 연결하지 않고 로컬로 등록을 구성합니다.  <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음 이 Unregister-CcAppliance cmdlet은 파이프라인된 입력을 허용하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Register-CcAppliance](register-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  

