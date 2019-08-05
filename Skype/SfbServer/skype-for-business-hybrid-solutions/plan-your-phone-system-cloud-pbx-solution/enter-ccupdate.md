---
title: 입력-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: Enter-CcUpdate cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 호스트 서버를 유지 관리 모드로 전환 하 여 해당 버전의 업데이트 프로세스를 준비 합니다. 기기는 즉시 모든 서비스를 중지 하 고, 진행 중인 통화를 종료 하 고, 새로운 통화를 거부 합니다.
ms.openlocfilehash: 3ff4c1543e3e882a7ccbaf0b9a216ce902a77c5f
ms.sourcegitcommit: 04c819504e23f9e3a618b57d54411ffb83888fb9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2019
ms.locfileid: "36197824"
---
# <a name="enter-ccupdate"></a>입력-CcUpdate

Enter-CcUpdate cmdlet은 비즈니스용 Skype 클라우드 커넥터 에디션 호스트 서버를 유지 관리 모드로 전환 하 여 해당 버전의 업데이트 프로세스를 준비 합니다. 기기는 즉시 모든 서비스를 중지 하 고, 진행 중인 통화를 종료 하 고, 새로운 통화를 거부 합니다.
  
```
Enter-CcUpdate
```

## <a name="parameters"></a>매개 변수

없음
  
## <a name="examples"></a>예제
<a name="Examples"> </a>

### <a name="example-1"></a>예제 1

다음 예제에서는 유지 관리 모드를 시작 하 여 업데이트 프로세스에 대 한 기기를 준비 합니다.
  
```
Enter-CcUpdate 
```

## <a name="detailed-description"></a>자세한 정보
<a name="DetailedDescription"> </a>

입력-CcUpdate cmdlet은 진행 중인 모든 통화를 종료 하는 모든 서비스를 즉시 중지 하 고, 기기는 다른 생산 기기로 전송 되는 모든 새 통화를 거부 하 게 됩니다. 남아 있는 프로덕션 기기의 용량이 업데이트를 준비 하려는 기기의 호출을 처리 하기에 충분 한지 확인 해야 합니다.
  
유지 관리 모드는 기기에서 자동 업데이트를 사용할 수 있도록 설정한 경우, 예를 들어 Microsoft에서 중요 한 핫픽스를 출시 하는 경우에 유용 합니다. 유지 관리 모드는 자동 업데이트를 해제 하기로 결정 한 경우에도 일관 된 방식으로 수동 업데이트를 수행 하려는 경우에 유용 합니다.
  
업데이트를 설치한 후 기기는 끝내기-CcUpdate cmdlet을 실행 하 여 프로덕션 모드로 다시 전환할 수 있습니다.
  
> [!NOTE]
> 클라우드 커넥터 기기를 수동으로 업데이트 하기로 결정 한 경우, Microsoft가 다음 버전을 릴리스할 때 60 일 내에 업데이트 해야 합니다. Microsoft는 새 버전이 출시 된 이후 60 일간 이전에 출시 된 클라우드 커넥터 버전을 지원 합니다. 
  
## <a name="input-types"></a>입력 형식
<a name="InputTypes"> </a>

없음. 입력-CCUpdate cmdlet은 파이프라인 입력을 허용 하지 않습니다.
  
## <a name="return-types"></a>반환 형식
<a name="ReturnTypes"> </a>

없음 
  
## <a name="see-also"></a>참고 항목
<a name="ReturnTypes"> </a>

[끝내기-CcUpdate](exit-ccupdate.md)
  

