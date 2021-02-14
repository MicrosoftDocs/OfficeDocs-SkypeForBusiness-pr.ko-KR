---
title: Enter-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: 이 Enter-CcUpdate cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 호스트 서버를 유지 관리 모드로 설정하여 업데이트 프로세스를 준비합니다. 어플라이언스가 모든 서비스를 즉시 중지하여 지속적인 통화를 종료하고 새 통화를 거부합니다.
ms.openlocfilehash: 25d2fbc56bd4de6a08985de18c178d5a8f993492
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802178"
---
# <a name="enter-ccupdate"></a>Enter-CcUpdate

이 Enter-CcUpdate cmdlet은 비즈니스용 Skype 클라우드 커넥터 버전 호스트 서버를 유지 관리 모드로 설정하여 업데이트 프로세스를 준비합니다. 어플라이언스가 모든 서비스를 즉시 중지하여 지속적인 통화를 종료하고 새 통화를 거부합니다.
  
```powershell
Enter-CcUpdate
```

## <a name="parameters"></a>매개 변수

없음
  
## <a name="examples"></a>예
<a name="Examples"> </a>

### <a name="example-1"></a>예 1

다음 예에서는 유지 관리 모드로 전환하여 어플라이언스를 업데이트 프로세스를 준비합니다.
  
```powershell
Enter-CcUpdate 
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

이 Enter-CcUpdate cmdlet은 진행되는 호출을 종료하는 모든 서비스를 즉시 중지하고 어플라이언스가 다른 프로덕션 어플라이언스로 전송되는 새 통화를 거부합니다. 나머지 프로덕션 어플라이언스에 업데이트 준비 중인 어플라이언스의 호출을 처리할 수 있는 충분한 용량이 있어야 합니다.
  
유지 관리 모드는 어플라이언스에서 자동 업데이트를 사용하도록 설정하고 Microsoft에서 중요한 핫픽스를 릴리스하는 경우 유용합니다. 유지 관리 모드는 자동 업데이트를 해제하기로 결정했지만 일관된 기준으로 수동 업데이트를 수행하는 경우 유용합니다.
  
업데이트를 설치한 후 이 cmdlet을 실행하여 어플라이언스를 프로덕션 모드로 Exit-CcUpdate 있습니다.
  
> [!NOTE]
> Cloud Connector 어플라이언스를 수동으로 업데이트하기로 결정한 경우 Microsoft에서 다음 버전을 릴리스한 후 60일 이내에 업데이트해야 합니다. Microsoft는 새 버전이 릴리스된 후 60일 동안 이전에 출시된 클라우드 커넥터 버전을 지원합니다. 
  
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음 이 Enter-CCUpdate cmdlet은 파이프라인된 입력을 허용하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음 
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[Exit-CcUpdate](exit-ccupdate.md)
  

