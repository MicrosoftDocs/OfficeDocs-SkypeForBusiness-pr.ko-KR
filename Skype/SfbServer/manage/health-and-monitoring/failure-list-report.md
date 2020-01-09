---
title: 비즈니스용 Skype 서버의 오류 목록 보고서
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: '요약: 비즈니스용 Skype 서버의 오류 목록 보고서에 대해 자세히 알아보세요.'
ms.openlocfilehash: d0ba76974d99b123c99e3df40a6850736423ab73
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992825"
---
# <a name="failure-list-report-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 오류 목록 보고서 
 
**요약:** 비즈니스용 Skype 서버의 오류 목록 보고서에 대해 자세히 알아보세요.
  
실패 목록 보고서는 실패 한 피어 투 피어 또는 회의 세션에서 참여 한 개별 참가자에 대 한 정보를 제공 합니다. 이 정보에는 문제가 발생 한 사용자의 URI와 실패와 연결 된 SIP 응답 코드 및 진단 ID가 포함 됩니다.
  
## <a name="accessing-the-failure-list-report"></a>실패 목록 보고서에 액세스

실패 목록 보고서는 [비즈니스용 Skype 서버의 실패 한 배포 보고서](failure-distribution-report.md)에서 다음 메트릭 중 하나를 클릭 하 여 액세스할 수 있습니다.
  
- 주요 진단 이유 (세션)
    
- 최상위 형식을 (세션)
    
- 상위 풀 (세션)
    
- 상위 원본 (세션)
    
- 상위 구성 요소 (세션)
    
- 사용자 (세션)의 상위
    
- 상위 사용자 (세션)
    
- 사용자 에이전트 (세션)에서 맨 위로
    
실패 목록 보고서에서 피어 투 피어 세션에 대 한 세션 세부 정보 메트릭을 클릭 하 여 비즈니스용 [Skype 서버의 피어 투 피어 세션 세부 정보 보고서](peer-to-peer-session-detail-report.md) 에 액세스할 수 있습니다. 회의에 대 한 회의 메트릭을 클릭 하 여 회의 세부 정보 보고서에 액세스할 수도 있습니다.
  
## <a name="making-the-best-use-of-the-failure-list-report"></a>실패 목록 보고서를 최대한 활용 하기

실패 목록 보고서에서 해당 값 위에 마우스를 놓으면 각 응답 코드 또는 각 진단 ID에 대 한 설명을 볼 수 있습니다. 예를 들어 마우스를 진단 ID 7025에 포함 하면 도구 설명에 다음이 표시 됩니다.
  
사용자의 미디어를 만드는 동안 내부 서버 오류가 발생 했습니다.
  
실패 목록 보고서에는 실패 한 하나 이상의 세션에 참가 한 모든 사용자의 목록을 직접 검색 하는 간단한 방법이 나와 있지 않으며, 실패 한 사용자에 게 가장 자주 관여 하는 사람을 확인 하는 방법이 제공 되지 않는다는 점에 유의 해야 합니다. 세션만. 한 가지 방법으로 실패 목록 보고서에는 필터링 기능이 없습니다. 그러나 데이터를 내보낸 다음 쉼표로 구분 된 값 파일로 변환 하는 경우 Windows PowerShell을 사용 하 여 이와 같은 질문에 대 한 답변을 찾을 수 있습니다. 예를 들어 데이터를에 저장 한다고 가정 합니다. CSV 파일 이름 \ Failure_List. 이 명령은 해당 파일에 저장 된 데이터를 기반으로 하나 이상의 실패 한 세션에 참가 한 모든 사용자를 나열 합니다. 
  
```PowerShell
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

이 명령은 다음과 같은 목록을 반환 합니다.
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

다음 두 명령은 각 사용자가 참여 한 실패 한 총 세션 수를 보고 합니다.
  
```PowerShell
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

이는 다음과 같은 데이터를 반환 합니다.
  
<pre>
Count    Name
 -----    ----
    20    Pilar.Ackerman@litwareinc.com
    20    David.Ahs@litwareinc.com
    16    Gilead.Amosnino@litwareinc.com
    16    Ken.Myero@litwareinc.com
    14    Henrik.Jensen@litwareinc.com
</pre>

## <a name="filters"></a>필터가

없음. 실패 목록 보고서는 필터링 할 수 없습니다.
  
## <a name="metrics"></a>매트릭스

다음 표에는 실패 목록 보고서에 제공 된 각 통화에 대 한 정보가 나와 있습니다.
  
**실패 목록 보고서 메트릭**

|**이름**|**이 항목을 정렬할 수 있나요?**|**설명**|
|:-----|:-----|:-----|
|**보고 시간** <br/> |아니요  <br/> |보고서가 기록 된 날짜 및 시간입니다.  <br/> |
|**요청당** <br/> |아니요  <br/> |실패 한 SIP 요청 유형입니다. 예를 들어 초대 또는 BYE.  <br/> |
|**응답 코드** <br/> |아니요  <br/> |회의에 실패 한 경우 SIP 응답 코드가 전송 됩니다.  <br/> |
|**진단 ID** <br/> |아니요  <br/> |오류 문제 해결에 유용한 정보를 자주 제공 하는 SIP 메시지에 첨부 된 고유 식별자 (ms-진단 헤더 형식)입니다.  <br/> |
|**참가 비용 시간 (밀리초)** <br/> |아니요  <br/> |사용자가 회의에 참가 하는 데 필요한 시간 (밀리초 단위)입니다.  <br/> |
|**사용자의** <br/> |아니요  <br/> |통화를 시작한 사용자의 SIP 주소입니다.  <br/> |
|**사용자 에이전트에서** <br/> |아니요  <br/> |통화를 시작한 사용자의 끝점에서 사용 하는 소프트웨어입니다.  <br/> |
|**사용자에 게** <br/> |아니요  <br/> |호출 되는 사용자의 SIP 주소입니다.  <br/> |
   

