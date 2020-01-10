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
localization_priority: Normal
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: 설치-CcAppliance cmdlet는 AD, 중앙 관리 저장소, 중재 서버, Edge 서버 가상 컴퓨터 등의 비즈니스용 Skype 클라우드 커넥터 에디션 기기를 호스트 서버에 설치 합니다.
ms.openlocfilehash: cccf500c6506c8ba3459631d5c823940907ad213
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003328"
---
# <a name="install-ccappliance"></a>Install-CcAppliance
 
설치-CcAppliance cmdlet는 AD, 중앙 관리 저장소, 중재 서버, Edge 서버 가상 컴퓨터 등의 비즈니스용 Skype 클라우드 커넥터 에디션 기기를 호스트 서버에 설치 합니다. 
  
```powershell
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예제 1

다음 예제에서는 호스트 서버에 새 클라우드 커넥터 기기를 설치 합니다.
  
```powershell
Install-CcAppliance
```

### <a name="example-2"></a>예제 2

다음 예에서는 클라우드 커넥터를 최신 버전으로 업그레이드 합니다.
  
```powershell
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a>예제 3

다음 예제에서는 호스트 서버에서 캐시 된 모든 클라우드 커넥터 자격 증명을 제거 하 고, 사용자에 게 모든 자격 증명 정보를 다시 지정 하 라는 메시지를 표시 한 후 클라우드 커넥터를 설치 합니다.
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a>예제 4

다음 예제에서는 PowerShell 콘솔의 모든 배포 단계를 표시 합니다.
  
```powershell
Install-CcAppliance -ShowStepsOnly
```

-ShowStepsOnly 매개 변수는 문제 해결만을 위한 것입니다.
  
### <a name="example-5"></a>예제 5

다음 예제에서는 호스트 서버의 각 배포 단계에 대 한 구성 파일을 생성 합니다. 구성 파일은 호스트 \<서버의 ApplianceRoot\>\instances\\<버전\>-default\ExportedConfig 폴더에 저장 됩니다.
  
```powershell
Install-CcAppliance -PrepareOnly
```

기기 루트를 확인 하려면 CcApplianceDirectory cmdlet을 실행 합니다. 
  
### <a name="example-6"></a>예제 6

다음 예제에서 클라우드 커넥터는 배포 단계 1, 2, 3을 실행 하 여 가상 스위치를 만들고, 광고 가상 컴퓨터를 만들고, 광고 서버에 도메인 서비스를 설치 합니다. 단계가 이미 실행 된 경우 단계를 건너뜁니다.
  
```powershell
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

SkipExistingObjects 매개 변수는 단계 매개 변수와 함께 사용 해야 합니다.
  
> [!NOTE]
> 단계 매개 변수는 문제 해결 목적 으로만 사용 됩니다. 이 매개 변수를 사용 하 여 기기를 배포 하거나 서비스 기기를 업그레이드 하지 마세요. 
  
배포의 단계를 확인 하려면 다음 명령을 실행 합니다.
  
설치-CcAppliance-ShowStepsOnly
  
## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

설치-CcAppliance cmdlet은 새 기기에 클라우드 커넥터를 배포 하거나 기존 기기를 최신 버전으로 업그레이드 하는 데 사용 됩니다.
  
새 기기가 있는 경우 먼저 클라우드 커넥터에 대 한 환경 준비를 읽고, 기기를 등록 하기 위해 등록-CcAppliance cmdlet을 실행 한 다음 Install-CcAppliance cmdlet을 실행 해야 합니다. 자세한 내용은 [클라우드 커넥터에 단일 사이트 배포](deploy-a-single-site-in-cloud-connector.md) 및 [클라우드 커넥터에 여러 사이트 배포](deploy-multiple-sites-in-cloud-connector.md)를 참조 하세요. 
  
기존 클라우드 커넥터 배포가 있고 업그레이드 하려는 경우 [새 버전의 클라우드 커넥터로 업그레이드](upgrade-to-a-new-version-of-cloud-connector.md)의 지침을 따르세요.
  
## <a name="parameters"></a>매개 변수
<a name="DetailedDescription"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
|PrepareOnly  <br/> |선택  <br/> |System.Management.Automation.SwitchParameter  <br/> | 각 배포 단계에 대 한 구성 파일을 생성 합니다. 이 매개 변수는 문제 해결에만 해당 됩니다. <br/> |
|ShowStepsOnly  <br/> |선택  <br/> |System.Management.Automation.SwitchParameter  <br/> |배포 단계 이름만 표시 합니다. 이 매개 변수는 문제 해결에만 해당 됩니다.  <br/> |
|SkipExistingObjects  <br/> |선택  <br/> |System.Management.Automation.SwitchParameter  <br/> |이 매개 변수는 단계 매개 변수와 함께 사용 해야 합니다. 이 매개 변수는 문제 해결에만 해당 됩니다.  <br/> |
|방법은  <br/> |선택  <br/> |System. Array  <br/> |배포 단계를 실행 합니다. 이 매개 변수는 문제 해결에만 해당 됩니다.  <br/> |
|업그레이드  <br/> |선택  <br/> |System.Management.Automation.SwitchParameter  <br/> |기존 클라우드 커넥터를 최신 버전으로 업그레이드 합니다.  <br/> |
|UpdateAllCredentials  <br/> |선택  <br/> |System.Management.Automation.SwitchParameter  <br/> |모든 클라우드 커넥터 자격 증명을 캐시에서 제거 합니다. 사용자에 게 설치에 대 한 새 자격 증명 정보를 지정 하 라는 메시지를 표시 합니다.  <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음. 설치-CcAppliance cmdlet은 파이프라인 입력을 허용 하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

