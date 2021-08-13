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
description: 이 Switch-CcVersion cmdlet은 실행 중인 어플라이언스 연결을 끊고 새로 배포된 어플라이언스 또는 백업 어플라이언스로 전환합니다.
ms.openlocfilehash: 1558f34d2388dc75bf4398ba15fc09cd36c439e2d70a39588ee697bc0ef04341
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54320041"
---
# <a name="switch-ccversion"></a>Switch-CcVersion
 
이 Switch-CcVersion cmdlet은 실행 중인 어플라이언스 연결을 끊고 새로 배포된 어플라이언스 또는 백업 어플라이언스로 전환합니다. 
  
```powershell
Switch-CcVersion [-Force]
```

## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 예제에서는 현재 실행 중인 어플라이언스의 서비스를 드레인한 다음 새로 배포된 어플라이언스 또는 백업 어플라이언스로 전환합니다.
  
```powershell
Switch-CcVersion
```

### <a name="example-2"></a>예 2

다음 예제에서는 현재 실행 중인 어플라이언스의 서비스를 드레인하고 서비스 드레인이 실패하면 서비스를 억지로 중지합니다. 그런 다음 새로 배포된 어플라이언스 또는 백업 어플라이언스로 전환합니다.
  
```powershell
Switch-CcVersion -Force
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

이 Switch-CcVersion cmdlet은 중재 서버 및 에지 서버에서 클라우드 커넥터 서비스를 드레인합니다. 실행 중인 모든 통화가 완료되지만 어플라이언스에서 새 통화를 거부합니다. 드레인 후 이 cmdlet은 회사 및 인터넷 네트워크에서 실행 중인 어플라이언스를 분리하고 어플라이언스에 속한 모든 가상 컴퓨터를 해제한 다음 회사 및 인터넷 네트워크에 백업 어플라이언스를 연결합니다.
  
## <a name="parameters"></a>매개 변수
<a name="DetailedDescription"> </a>

|**매개 변수**|**필수**|**유형**|**설명**|
|:-----|:-----|:-----|:-----|
| Force <br/> | 선택 <br/> |System.Management.Automation.SwitchParameter  <br/> | 서비스 드레인이 실패할 경우 서비스를 강요 중지합니다. <br/> |
   
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

없음
  

