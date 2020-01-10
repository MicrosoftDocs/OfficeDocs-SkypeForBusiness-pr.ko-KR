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
localization_priority: Normal
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: 변환-CcIsoToVhdx cmdlet은 고객이 제공 하는 Windows Server 2012 R2 ISO 파일을 사용 하 여 기본 VHDX (virtual 하드 디스크 파일)를 만듭니다. VHDX 파일은 비즈니스용 Skype 클라우드 커넥터 에디션을 배포 하는 동안 사용 됩니다.
ms.openlocfilehash: 780002c54a77746c51f418cae077ffcc9b1fb608
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001348"
---
# <a name="convert-ccisotovhdx"></a>Convert-CcIsoToVhdx
 
변환-CcIsoToVhdx cmdlet은 고객이 제공 하는 Windows Server 2012 R2 ISO 파일을 사용 하 여 기본 VHDX (virtual 하드 디스크 파일)를 만듭니다. VHDX 파일은 비즈니스용 Skype 클라우드 커넥터 에디션을 배포 하는 동안 사용 됩니다.
  
```powershell
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a>매개 변수

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
|IsoFilePath  <br/> | 필수 <br/> |System.String  <br/> | Windows Server 2012 R2 ISO 파일의 경로입니다. <br/> |
|GeneralizeOnly  <br/> |선택  <br/> |System.Management.Automation.SwitchParameter  <br/> |Windows 업데이트 중에 변환 프로세스가 실패 하는 경우 네트워크/프록시를 구성 하 고 Windows를 수동으로 업데이트할 수 있습니다. 수동 작업이 완료 되 면-GeneralizeOnly 매개 변수를 사용 하 여이 cmdlet을 실행 하 고 나머지 작업을 완료할 수 있습니다.  <br/> |
|PauseBeforeUpdate  <br/> |선택  <br/> |System.Management.Automation.SwitchParameter  <br/> |Windows를 업데이트 하려면 기본 VM의 일부 수동 네트워크/프록시 구성이 필요할 수 있습니다. 이 매개 변수를 제공 하는 경우 Windows 업데이트 전에 변환 프로세스가 일시 중지 됩니다. 수동 구성이 완료 된 후에는 프로세스를 다시 시작할 수 있습니다.  <br/> |
   
## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예제 1

다음 예에서는 "C:\ Windows_Server_2012_R2-EN-US-x64: .ISO"에 있는 Windows Server 2012 R2 ISO 파일을 사용 하 여 기본 VHDX 파일을 준비 합니다. 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a>예제 2

Windows 업데이트 중에 Convert-CcIsoToVhdx cmdlet이 실패 하는 경우에는 잘못 된 네트워크/프록시 구성 때문입니다. 오류 메시지의 지침에 따라 기본 가상 컴퓨터에 로그온 하 여 문제를 해결 하 고 Windows를 수동으로 업데이트할 수 있습니다. 수동 작업이 완료 되 면-GeneralizeOnly 매개 변수를 사용 하 여 cmdlet을 다시 실행 하 여 나머지 작업을 완료 합니다. 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a>예제 3

Windows를 업데이트 하는 데 수동 구성이 필요한 경우-PauseBeforeUpdate 매개 변수를 사용할 수 있습니다. 이 매개 변수를 사용 하면 Windows 업데이트 프로세스 전에 클라우드 커넥터가 일시 중지 됩니다. 그런 다음 수동 구성을 완료 하 고 다음과 같이 변환 프로세스를 다시 시작할 수 있습니다.
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

Convert-CcIsoToVhdx cmdlet은 기본 VM을 먼저 만들고 클라우드 커넥터에 종속 된 몇 가지 기본 구성 요소를 설치한 다음 Windows 업데이트를 설치 합니다. 마지막으로, 클라우드 커넥터 기기의 가상 머신에서 사용 되는 기본 VHDX 파일을 가져오기 위해 virtual machine (sysprep)을 generalizes. 
  
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음. Convert-CcIsoToVhdx cmdlet은 파이프라인 입력을 허용 하지 않습니다. 
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

없음
  

