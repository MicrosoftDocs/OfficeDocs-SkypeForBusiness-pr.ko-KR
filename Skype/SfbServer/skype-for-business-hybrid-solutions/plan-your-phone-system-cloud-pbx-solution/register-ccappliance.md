---
title: Register-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: 이 Register-CcAppliance 온라인 테넌트 구성의 PSTN 사이트에 어플라이언스 정보를 등록합니다. 어플라이언스를 등록해야 응용 비즈니스용 Skype 클라우드 커넥터 버전 수 있습니다.
ms.openlocfilehash: 5b63ce38b358d41fea15551df1e8134d1b56db00851317cbc5c81ac8f3aea058
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54288806"
---
# <a name="register-ccappliance"></a>Register-CcAppliance
 
이 Register-CcAppliance 온라인 테넌트 구성의 PSTN 사이트에 어플라이언스 정보를 등록합니다. 어플라이언스를 등록해야 응용 비즈니스용 Skype 클라우드 커넥터 버전 수 있습니다.
  
```powershell
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 예에서는 온라인 테넌트 구성에 현재 어플라이언스 정보를 등록합니다.
  
```powershell
Register-CcAppliance
```

### <a name="example-2"></a>예 2

다음 예제에서는 온라인 테넌트 구성에 연결하지 않고 로컬로 등록에 대한 구성을 검사합니다.
  
```powershell
Register-CcAppliance -Local
```

### <a name="example-3"></a>예 3

다음 예제에서는 이름이 "Appliance1"인 현재 어플라이언스를 PSTN 사이트 "Site1"에 등록합니다.
  
```powershell
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

테넌트 관리자 계정 이름과 암호를 제공해야 합니다. 클라우드 커넥터 온라인 관리를 위해 만든 계정을 사용하세요. 
  
릴리스 1.4.2 이전 버전에서는 지침에 따라 외부 인증서 암호, 안전 모드 관리자 암호, 도메인 관리자 암호 및 VM 관리자 암호를 제공합니다. 
  
릴리스 2.0 이상에서 지침에 따라 외부 인증서 암호, CceService 암호 및 CABackupFile 암호를 제공합니다.
  
등록이 끝나면 클라우드 커넥터 관리 서비스를 다시 시작하고 CceService 계정으로 서비스에 로그온합니다.
  
사이트 이름과 에지 서버 외부 FQDN을 CloudConnector.ini PSTN 사이트 ID로 간주됩니다. 사이트를 등록하는 데 SiteName과 에지 서버 외부 FQDN이 모두 사용되지 않은 경우 온라인 테넌트 구성에서 이 어플라이언스에 대한 새 사이트가 만들어집니다. PSTN 사이트 ID가 발견되는 경우 PSTN 사이트에서 이 ID를 사용하며 어플라이언스가 이 PSTN 사이트에 등록됩니다. 
  
다음과 같은 경우 cmdlet이 실패하고 Site1이 이미 등록되어 있습니다. 
  
- SiteName은 Site1이고 에지 서버 외부 FQDN은 edgserver1.contoso.com. 
    
- SiteName이 Site1인 PSTN 사이트와 에지 서버 외부 FQDN이 edgserver.contoso.com.
    
- SiteName이 NewSite인 PSTN 사이트와 에지 서버 외부 FQDN이 등록된 edgserver1.contoso.com 사이트입니다. 
    
파일에서 중재 서버 FQDN과 결합된 ApplianceName은 CloudConnector.ini ID로 간주됩니다. ApplianceName과 중재 서버 FQDN을 모두 사용하여 어플라이언스를 등록하지 않은 경우 온라인 테넌트 구성에서 새 어플라이언스가 만들어집니다. 어플라이언스가 이미 등록되어 있는 경우 cmdlet이 실패합니다.
  
다음과 같은 상황에서는 cmdlet이 실패하고 어플라이언스가 이미 등록되어 있는 것으로 나타냅니다. 
  
- ApplianceName은 Appliance1이고 중재 서버 FQDN은 ms1.vdomain.com.
    
- 현재 PSTN 사이트에서 이름이 Appliance1 및 중재 서버 FQDN인 어플라이언스가 ms.vdomain.com 이름이 NewAppliance 및 중재 서버 FQDN이 등록된 ms1.vdomain.com 경우.
    
## <a name="parameters"></a>매개 변수
<a name="DetailedDescription"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
|SiteName  <br/> |옵션  <br/> |System.String  <br/> |어플라이언스가 등록된 PSTN 사이트 이름입니다. 기본값은 파일에서 SiteName CloudConnector.ini 있습니다.  <br/> |
|ApplianceName  <br/> |옵션  <br/> |System.String  <br/> |현재 어플라이언스 이름입니다. 기본값은 호스트 서버의 컴퓨터 이름입니다.  <br/> |
|로컬  <br/> |선택  <br/> |System.Management.Automation.SwitchParameter  <br/> |온라인 테넌트 구성에 연결하지 않고 구성을 로컬로 등록합니다.  <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음 이 Register-CcAppliance cmdlet은 파이프라인된 입력을 허용하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Publish-CcAppliance](publish-ccappliance.md)
  
[Install-CcAppliance](install-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

