---
title: Switch-CcVersion
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
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: 스위치용 버전 cmdlet은 실행 중인 기기의 연결을 끊고 새로 배포 또는 백업 기기로 전환 합니다.
ms.openlocfilehash: 31dbb841caae51de0accedf081fa576ec378044b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824152"
---
# <a name="switch-ccversion"></a>Switch-CcVersion
 
스위치용 버전 cmdlet은 실행 중인 기기의 연결을 끊고 새로 배포 또는 백업 기기로 전환 합니다. 
  
```powershell
Switch-CcVersion [-Force]
```

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예제 1

다음 예에서는 현재 실행 중인 기기의 서비스를 고갈 한 다음 새로 배포 또는 백업 기기로 전환 합니다.
  
```powershell
Switch-CcVersion
```

### <a name="example-2"></a>예제 2

다음 예에서는 현재 실행 중인 기기의 서비스를 드레이닝 하 고 서비스를 드레이닝 하지 못하면 서비스를 강제로 중지 합니다. 그런 다음 새 배포 또는 백업 기기로 명령을 전환 합니다.
  
```powershell
Switch-CcVersion -Force
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

이 스위치를 사용 하는 경우에는 중재 서버와 Edge 서버에서 클라우드 커넥터 서비스를 드레이닝 합니다. 실행 중인 모든 통화가 완료 되지만 기기는 새로운 통화를 거부 하 게 됩니다. 드레이닝이 완료 되 면 cmdlet이 회사 및 인터넷 네트워크에서 실행 중인 기기의 연결을 끊고 기기에 속한 모든 가상 머신을 끈 다음, 백업 기기를 회사 및 인터넷 네트워크에 연결 합니다.
  
## <a name="parameters"></a>매개 변수
<a name="DetailedDescription"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
| Force <br/> | 선택 <br/> |System.Management.Automation.SwitchParameter  <br/> | 서비스 드레이닝이 실패 하는 경우 서비스를 강제로 중지 합니다. <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

없음
  

