---
title: CcAppliance 등록 취소
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: 비 CcAppliance cmdlet은 온라인 테 넌 트 구성의 PSTN 사이트에서 현재 비즈니스용 Skype 클라우드 커넥터 에디션 기기의 등록을 취소 합니다.
ms.openlocfilehash: fafe374371cd01b2ec7c67ade89dd2a905e16d18
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190587"
---
# <a name="unregister-ccappliance"></a>CcAppliance 등록 취소
 
비 CcAppliance cmdlet은 온라인 테 넌 트 구성의 PSTN 사이트에서 현재 비즈니스용 Skype 클라우드 커넥터 에디션 기기의 등록을 취소 합니다.
  
```
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예제 1

다음 예에서는 온라인 테 넌 트 구성에서 현재 기기의 등록을 취소 합니다.
  
```
Unregister-CcAppliance
```

### <a name="example-2"></a>예제 2

다음 예제에서는 온라인 테 넌 트 구성에 연결 하지 않고 로컬로 등록 취소 하는 구성을 확인 합니다.
  
```
Unregister-CcAppliance -Local
```

### <a name="example-3"></a>예제 3

다음 예제에서는 "Appliance1" 라는 이름으로 현재 기기를 "Site1" PSTN 사이트로 등록 취소 합니다.
  
```
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

CcAppliance cmdlet과 유사 하 게, CloudConnector .ini 파일의 Edge 서버 외부 FQDN과 결합 된 SiteName은 PSTN 사이트 id로 간주 됩니다. 마찬가지로, CloudConnector .ini 파일의 중재 서버 FQDN과 결합 한 ApplianceName는 기기 id로 간주 됩니다.
  
기기의 등록을 취소 한 후에는 클라우드 커넥터 관리 서비스를 다시 시작 하 고 NetworkService 계정으로 로그온 합니다.
  
## <a name="parameters"></a>매개 변수
<a name="DetailedDescription"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
| Name <br/> |선택  <br/> |System.String  <br/> |기기가 등록 된 PSTN 사이트 이름입니다. 기본 값은 CloudConnector .ini 파일의 SiteName 값입니다.  <br/> |
|ApplianceName  <br/> |선택  <br/> |System.String  <br/> |현재 기기의 이름입니다. Default 값은 호스트 서버의 컴퓨터 이름입니다.  <br/> |
|로컬  <br/> |선택  <br/> |System.Management.Automation.SwitchParameter  <br/> |온라인 테 넌 트 구성에 연결 하지 않고 로컬에서 등록에 대 한 구성을 확인 합니다.  <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음. CcAppliance cmdlet은 파이프라인 입력을 허용 하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[등록-CcAppliance](register-ccappliance.md)
  
[설치-CcAppliance](install-ccappliance.md)
  
[제거-CcAppliance](uninstall-ccappliance.md)
  
[게시-CcAppliance](publish-ccappliance.md)
  

