---
title: Convert-CcIsoToVhdx
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
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: 이 Convert-CcIsoToVhdx cmdlet은 고객이 R2 ISO 파일로 제공한 기본 VHDX(Windows Server 2012 하드 디스크 파일)를 만듭니다. VHDX 파일은 비즈니스용 Skype 클라우드 커넥터 버전 배포 중에 사용됩니다.
ms.openlocfilehash: f6b16c27b82919f24b9ee0e3094fb03fffa6443b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802428"
---
# <a name="convert-ccisotovhdx"></a>Convert-CcIsoToVhdx
 
이 Convert-CcIsoToVhdx cmdlet은 고객이 R2 ISO 파일로 제공한 기본 VHDX(Windows Server 2012 하드 디스크 파일)를 만듭니다. VHDX 파일은 비즈니스용 Skype 클라우드 커넥터 버전 배포 중에 사용됩니다.
  
```powershell
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a>매개 변수

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
|IsoFilePath  <br/> | 필수 <br/> |System.String  <br/> | R2 ISO Windows Server 2012 경로입니다. <br/> |
|GeneralizeOnly  <br/> |선택  <br/> |System.Management.Automation.SwitchParameter  <br/> |Windows 업데이트 중에 변환 프로세스가 실패하면 네트워크/프록시를 구성하고 Windows를 수동으로 업데이트할 수 있습니다. 수동 작업이 완료되면 -GeneralizeOnly 매개 변수를 사용하여 이 cmdlet을 실행할 수 있으며 나머지 작업을 완료합니다.  <br/> |
|PauseBeforeUpdate  <br/> |선택  <br/> |System.Management.Automation.SwitchParameter  <br/> |Windows를 업데이트하려면 기본 VM의 일부 수동 네트워크/프록시 구성이 필요합니다. 이 매개 변수를 제공하는 경우 Windows 업데이트 전에 변환 프로세스가 일시 중지됩니다. 수동 구성이 완료되면 프로세스를 다시 시작할 수 있습니다.  <br/> |
   
## <a name="examples"></a>예
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 예제에서는 "C:\Windows_Server_2012_R2-EN-US-x64.ISO"에 있는 Windows Server 2012 R2 ISO 파일을 사용하여 기본 VHDX 파일을 준비합니다. 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a>예 2

Windows 업데이트 Convert-CcIsoToVhdx cmdlet이 실패하는 경우 잘못된 네트워크/프록시 구성으로인 것일 수 있습니다. 오류 메시지의 지침에 따라 기본 가상 머신에 로그온하여 문제를 해결하고 Windows를 수동으로 업데이트할 수 있습니다. 수동 작업이 완료되면 -GeneralizeOnly 매개 변수를 사용하여 cmdlet을 다시 실행하여 나머지 작업을 완료합니다. 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a>예 3

Windows를 업데이트하는 데 수동 구성이 필요한 경우 -PauseBeforeUpdate 매개 변수를 사용할 수 있습니다. 이 매개 변수를 사용하면 클라우드 커넥터가 Windows 업데이트 프로세스 전에 일시 중지됩니다. 그런 다음 수동 구성을 완료하고 다음과 같이 변환 프로세스를 다시 시작할 수 있습니다.
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

이 Convert-CcIsoToVhdx 먼저 기본 VM을 만들고 클라우드 커넥터가 사용하는 몇 가지 기본 구성 요소를 설치한 다음 Windows 업데이트를 설치합니다. 마지막으로 가상 컴퓨터(sysprep)를 일반화하여 클라우드 커넥터 어플라이언스의 가상 머신에서 사용할 기본 VHDX 파일을 얻습니다. 
  
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음 이 Convert-CcIsoToVhdx cmdlet은 파이프라인된 입력을 허용하지 않습니다. 
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

없음
  

