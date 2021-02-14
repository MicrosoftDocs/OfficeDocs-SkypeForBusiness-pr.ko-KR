---
title: Install-CcAppliance
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
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: 이 Install-CcAppliance cmdlet은 호스트 서버에 AD, 중앙 관리 저장소, 중재 서버 및 에지 서버 가상 컴퓨터를 비롯한 비즈니스용 Skype 클라우드 커넥터 버전 어플라이언스를 설치합니다.
ms.openlocfilehash: fe1fab785e2681614f27035714b6ddead22b8707
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799878"
---
# <a name="install-ccappliance"></a>Install-CcAppliance
 
이 Install-CcAppliance cmdlet은 호스트 서버에 AD, 중앙 관리 저장소, 중재 서버 및 에지 서버 가상 컴퓨터를 비롯한 비즈니스용 Skype 클라우드 커넥터 버전 어플라이언스를 설치합니다. 
  
```powershell
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>예
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 예에서는 호스트 서버에 새 Cloud Connector 어플라이언스를 설치합니다.
  
```powershell
Install-CcAppliance
```

### <a name="example-2"></a>예 2

다음 예에서는 Cloud Connector를 최신 버전으로 업그레이드합니다.
  
```powershell
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a>예 3

다음 예에서는 호스트 서버에 캐시된 모든 클라우드 커넥터 자격 증명을 제거하고 사용자에게 모든 자격 증명 정보를 다시 지정하라는 메시지를 표시한 다음 클라우드 커넥터를 설치합니다.
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a>예 4

다음 예제에서는 PowerShell 콘솔의 모든 배포 단계를 표시합니다.
  
```powershell
Install-CcAppliance -ShowStepsOnly
```

-ShowStepsOnly 매개 변수는 문제 해결 전용입니다.
  
### <a name="example-5"></a>예 5

다음 예제에서는 호스트 서버의 각 배포 단계에 대한 구성 파일을 생성합니다. 구성 파일은 호스트 서버의 \< ApplianceRoot \> \Instances<\\ \> -default\ExportedConfig 폴더에 저장됩니다.
  
```powershell
Install-CcAppliance -PrepareOnly
```

어플라이언스 루트를 확인하기 위해 Get-CcApplianceDirectory 실행합니다. 
  
### <a name="example-6"></a>예 6

다음 예에서 Cloud Connector는 배포 1, 2 및 3단계를 실행하여 가상 스위치를 만들고 AD 가상 머신을 만들고 AD 서버에 도메인 서비스를 설치합니다. 단계가 이미 실행된 경우 이 단계를 건너뜁습니다.
  
```powershell
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

SkipExistingObjects 매개 변수는 Steps 매개 변수와 함께 사용되어야 합니다.
  
> [!NOTE]
> Steps 매개 변수는 문제 해결 목적으로만 사용됩니다. 이 매개 변수를 사용하여 어플라이언스를 배포하거나 서비스에 있는 어플라이언스를 업그레이드하지 마십시오. 
  
배포 단계를 결정하기 위해 다음 명령을 실행합니다.
  
Install-CcAppliance -ShowStepsOnly
  
## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

이 Install-CcAppliance cmdlet은 클라우드 커넥터를 새 어플라이언스에 배포하거나 기존 어플라이언스를 최신 버전으로 업그레이드하는 데 사용됩니다.
  
새 어플라이언스가 있는 경우 먼저 클라우드 커넥터에 대한 환경 준비를 읽고 Register-CcAppliance cmdlet을 실행하여 어플라이언스를 등록한 다음 Install-CcAppliance cmdlet을 실행합니다. 자세한 내용은 [클라우드](deploy-a-single-site-in-cloud-connector.md) 커넥터에서 단일 사이트 배포 및 클라우드 커넥터에서 여러 사이트 [배포를 참조하세요.](deploy-multiple-sites-in-cloud-connector.md) 
  
기존 클라우드 커넥터 배포가 있으며 업그레이드하려는 경우 새 버전의 클라우드 커넥터로 업그레이드의 [지침을 따르세요.](upgrade-to-a-new-version-of-cloud-connector.md)
  
## <a name="parameters"></a>매개 변수
<a name="DetailedDescription"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
|PrepareOnly  <br/> |선택  <br/> |System.Management.Automation.SwitchParameter  <br/> | 각 배포 단계에 대한 구성 파일을 생성합니다. 이 매개 변수는 문제 해결 전용입니다. <br/> |
|ShowStepsOnly  <br/> |선택  <br/> |System.Management.Automation.SwitchParameter  <br/> |배포 단계 이름만 표시합니다. 이 매개 변수는 문제 해결 전용입니다.  <br/> |
|SkipExistingObjects  <br/> |선택  <br/> |System.Management.Automation.SwitchParameter  <br/> |이 매개 변수는 Steps 매개 변수와 함께 사용되어야 합니다. 이 매개 변수는 문제 해결 전용입니다.  <br/> |
|단계  <br/> |선택  <br/> |System.Array  <br/> |배포 단계를 실행합니다. 이 매개 변수는 문제 해결 전용입니다.  <br/> |
|업그레이드  <br/> |선택  <br/> |System.Management.Automation.SwitchParameter  <br/> |기존 클라우드 커넥터를 최신 버전으로 업그레이드합니다.  <br/> |
|UpdateAllCredentials  <br/> |선택  <br/> |System.Management.Automation.SwitchParameter  <br/> |캐시에서 모든 클라우드 커넥터 자격 증명을 제거합니다. 사용자에게 설치에 대한 새 자격 증명 정보를 지정하라는 메시지를 표시합니다.  <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음 이 Install-CcAppliance cmdlet은 파이프라인된 입력을 허용하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

