---
title: 등록-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: 등록-CcAppliance cmdlet는 온라인 테 넌 트 구성의 PSTN 사이트에 기기 정보를 등록 합니다. 비즈니스용 Skype 클라우드 커넥터 에디션 관리 서비스에서 기기를 배포 하 고 관리 하기 전에 먼저 등록 해야 합니다.
ms.openlocfilehash: 9e15d7b8227bf9ee657d197041056703505ca7c8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190704"
---
# <a name="register-ccappliance"></a>등록-CcAppliance
 
등록-CcAppliance cmdlet는 온라인 테 넌 트 구성의 PSTN 사이트에 기기 정보를 등록 합니다. 비즈니스용 Skype 클라우드 커넥터 에디션 관리 서비스에서 기기를 배포 하 고 관리 하기 전에 먼저 등록 해야 합니다.
  
```
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예제 1

다음 예에서는 현재 기기 정보를 온라인 테 넌 트 구성에 등록 합니다.
  
```
Register-CcAppliance
```

### <a name="example-2"></a>예제 2

다음 예제에서는 온라인 테 넌 트 구성에 연결 하지 않고 로컬로 등록 구성을 검사 합니다.
  
```
Register-CcAppliance -Local
```

### <a name="example-3"></a>예제 3

다음 예에서는 "Appliance1" 라는 이름의 현재 기기를 PSTN 사이트 "Site1"에 등록 합니다.
  
```
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

테 넌 트 관리 계정 이름 및 암호를 제공 해야 합니다. 클라우드 커넥터 온라인 관리에 대해 만든 계정을 사용 합니다. 
  
릴리스 1.4.2 및 이전 버전의 지침에 따라 외부 인증서 암호, 안전 모드 관리자 암호, 도메인 관리자 암호, VM 관리자 암호를 제공 합니다. 
  
릴리스 2.0 이상에서는 지침에 따라 외부 인증서 암호, CceService password 및 CABackupFile 암호를 제공 합니다.
  
등록이 종료 되 면 클라우드 커넥터 관리 서비스를 다시 시작 하 고 서비스에 CceService 계정으로 로그온 합니다.
  
CloudConnector .ini 파일의 Edge 서버 외부 FQDN과 결합 된 SiteName은 PSTN 사이트 id로 간주 됩니다. 사이트를 등록 하는 데 SiteName 또는 Edge 서버 외부 FQDN을 사용 하지 않은 경우 온라인 테 넌 트 구성에서이 기기에 대 한 새 사이트가 생성 됩니다. PSTN 사이트 id가 발견 되 면 PSTN 사이트는이 id를 사용 하 고 기기는이 PSTN 사이트에 등록 됩니다. 
  
다음과 같은 경우에는 cmdlet이 실패 하 고 Site1가 이미 등록 되었음을 나타냅니다. 
  
- SiteName은 Site1이 고 Edge 서버 외부 FQDN은 edgserver1.contoso.com입니다. 
    
- SiteName이 Site1 및 Edge 서버 외부 FQDN 인 PSTN 사이트는 edgserver.contoso.com입니다.
    
- SiteName이 NewSite 및 Edge 서버 외부 FQDN 인 PSTN 사이트는 edgserver1.contoso.com 등록 되어 있습니다. 
    
ApplianceName는 CloudConnector .ini 파일의 중재 서버 FQDN과 결합 된 것을 기기 Id로 간주 합니다. 기기를 등록 하는 데 ApplianceName 또는 중재 서버 FQDN이 모두 사용 되지 않은 경우, 온라인 테 넌 트 구성에서 새 기기가 생성 됩니다. 기기가 이미 등록 되어 있으면 cmdlet이 실패 합니다.
  
다음과 같은 경우에는 cmdlet이 실패 하 고 기기가 이미 등록 된 것으로 표시 됩니다. 
  
- ApplianceName는 Appliance1이 고 중재 서버 FQDN은 ms1.vdomain.com입니다.
    
- 현재 PSTN 사이트에서 이름이 Appliance1이 고, 중재 서버 FQDN이 ms.vdomain.com 이거나, 이름 NewAppliance 및 중재 서버 FQDN이 ms1.vdomain.com 인 기기가 등록 되어 있는 경우에는이를 발생 합니다.
    
## <a name="parameters"></a>매개 변수
<a name="DetailedDescription"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
|Name  <br/> |선택  <br/> |System.String  <br/> |기기가 등록 된 PSTN 사이트 이름입니다. 기본값은 CloudConnector .ini 파일의 SiteName 값입니다.  <br/> |
|ApplianceName  <br/> |선택  <br/> |System.String  <br/> |현재 기기의 이름입니다. Default 값은 호스트 서버의 컴퓨터 이름입니다.  <br/> |
|로컬  <br/> |선택  <br/> |System.Management.Automation.SwitchParameter  <br/> |온라인 테 넌 트 구성에 연결 하지 않고 로컬에서 등록을 위한 구성을 확인 합니다.  <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음. 등록-CcAppliance cmdlet은 파이프라인 입력을 허용 하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[CcAppliance 등록 취소](unregister-ccappliance.md)
  
[게시-CcAppliance](publish-ccappliance.md)
  
[설치-CcAppliance](install-ccappliance.md)
  
[제거-CcAppliance](uninstall-ccappliance.md)
  

