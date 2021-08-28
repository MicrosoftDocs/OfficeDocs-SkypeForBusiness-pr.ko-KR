---
title: 보고서의 오류 목록 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: '요약: 오류 목록 보고서에 대해 비즈니스용 Skype 서버.'
ms.openlocfilehash: 3943c802bd6f6bce593c8fdfafb05179252712b5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582742"
---
# <a name="failure-list-report-in-skype-for-business-server"></a>보고서의 오류 목록 비즈니스용 Skype 서버 
 
**요약:** 오류 목록 보고서에 대해 비즈니스용 Skype 서버.
  
오류 목록 보고서에서는 실패한 피어 투 피어 또는 회의 세션에 참가한 개별 참가자에 대한 정보를 제공합니다. 이 정보에는 문제를 경험한 사용자의 URI와 실패와 관련된 SIP 응답 코드 및 진단 ID가 포함됩니다.
  
## <a name="accessing-the-failure-list-report"></a>오류 목록 보고서 액세스

오류 목록 보고서는 오류 분포 보고서의 다음 메트릭 중 [비즈니스용 Skype 서버.](failure-distribution-report.md)
  
- 상위 진단 이유(세션)
    
- 상위 형식(세션)
    
- 상위 풀(세션)
    
- 상위 원본(세션)
    
- 상위 구성 요소(세션)
    
- 상위 출처 사용자(세션)
    
- 상위 대상 사용자(세션)
    
- 상위 출처 사용자 에이전트(세션)
    
오류 목록 보고서에서 피어 투 피어 세션에 대한 세션 세부 비즈니스용 Skype 서버 메트릭을 클릭하여 피어 투 [피어](peer-to-peer-session-detail-report.md) 세션 세부 정보 보고서에 액세스할 수 있습니다. 또한 전화 회의에 대한 전화 회의 메트릭을 클릭하여 전화 회의 정보 보고서에 액세스할 수 있습니다.
  
## <a name="making-the-best-use-of-the-failure-list-report"></a>오류 목록 보고서의 효과적인 활용

오류 목록 보고서에서는 각 응답 코드 또는 각 진단 ID 위에 마우스를 놓기만 하면 해당 값에 대한 설명을 볼 수 있습니다. 예를 들어 진단 ID 7025 위에 마우스를 놓으면 도구 설명에 다음이 표시됩니다.
  
사용자를 위한 미디어를 만드는 동안 내부 서버 오류가 발생했습니다.
  
오류 목록 보고서는 하나 이상의 실패한 세션에 참가한 모든 사용자의 목록을 직접 검색하는 간편한 방법이나 실패한 세션에서 가장 자주 참여한 사용자를 파악하는 방법을 제공하지 않습니다. 우선 한 가지 이유는 오류 목록 보고서에 필터링 기능이 없기 때문입니다. 그러나 데이터를 내보낸 후에 쉼표로 구분된 값 파일로 변환할 경우 Windows PowerShell을 사용하여 이러한 사항을 찾을 수 있습니다. 예를 들어 데이터를 C:\Data\Failure_List.csv라는 이름의 .CSV 파일로 저장한 경우 다음 명령을 사용하면 이 파일에 저장된 데이터를 기반으로 하나 이상의 실패한 세션에 참여한 모든 사용자가 나열됩니다. 
  
```PowerShell
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

그러면 다음과 같은 목록이 반환됩니다.
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

다음 두 명령은 각 사용자가 참가한 실패한 총 세션 수를 보고합니다.
  
```PowerShell
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

그러면 다음과 같은 데이터가 반환됩니다.
  
<pre>
Count    Name
 -----    ----
    20    Pilar.Ackerman@litwareinc.com
    20    David.Ahs@litwareinc.com
    16    Gilead.Amosnino@litwareinc.com
    16    Ken.Myero@litwareinc.com
    14    Henrik.Jensen@litwareinc.com
</pre>

## <a name="filters"></a>필터

없음. 오류 목록 보고서는 필터링할 수 없습니다.
  
## <a name="metrics"></a>메트릭

다음 표에서는 각 실패한 통화에 대해 오류 목록 보고서에 제공된 정보를 보여 줍니다.
  
**오류 목록 보고서 메트릭**

|**이름**|**이 항목에 대한 정렬 가능 여부**|**설명**|
|:-----|:-----|:-----|
|**보고된 시간** <br/> |아니요  <br/> |보고서가 기록된 날짜 및 시간입니다.  <br/> |
|**요청** <br/> |아니요  <br/> |실패한 SIP 요청 유형입니다. 예: INVITE 또는 BYE  <br/> |
|**응답 코드** <br/> |아니요  <br/> |회의가 실패했을 때 전송된 SIP 응답 코드입니다.  <br/> |
|**진단 ID** <br/> |아니요  <br/> |오류 문제를 해결할 때 종종 유용한 정보를 제공하는 SIP 메시지에 연결된 고유 식별자(ms-diagnostics 헤더 형식)입니다.  <br/> |
|**참가 소요 시간(밀리초)** <br/> |아니요  <br/> |사용자가 전화 회의에 참가하기까지 소요된 시간(밀리초)입니다.  <br/> |
|**시작 사용자** <br/> |아니요  <br/> |통화를 시작한 사용자의 SIP 주소입니다.  <br/> |
|**출처 사용자 에이전트** <br/> |아니요  <br/> |통화를 시작한 사용자의 끝점에 사용된 소프트웨어입니다.  <br/> |
|**대상 사용자** <br/> |아니요  <br/> |통화를 받고 있는 사용자의 SIP 주소입니다.  <br/> |
   

