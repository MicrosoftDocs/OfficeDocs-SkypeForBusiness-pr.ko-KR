---
title: 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: '요약: 이 문서에서 사용되는 회의 정보 보고서에 대해 비즈니스용 Skype 서버.'
ms.openlocfilehash: a86124c05e0d35caef3f92c4ec43b561eb54938c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829992"
---
# <a name="conference-detail-report-in-skype-for-business-server"></a>비즈니스용 Skype 서버

**요약:** 이 보고서에서 사용되는 회의 세부 정보 보고서에 비즈니스용 Skype 서버.

전화 회의 정보 보고서에서는 전화 회의에 참가한 모든 사용자에 대한 자세한 정보를 제공합니다. 예를 들어 사용자가 전화 회의에 참가한 날짜/시간, 사용자가 전화 회의에서 나간 날짜/시간, 그리고 해당 사용자를 전화 회의에 연결하는 데 사용된 끝점의 사용자 에이전트와 같은 정보를 확인할 수 있습니다. 각 전화 회의에서 사용자의 역할(예: 발표자, 참석자) 관련 정보도 볼 수 있습니다. 그러나 가장 중요한 기능은 전화 회의에 정상적으로 참가하여 전화 회의를 완료한 사용자가 그렇지 않은 사용자를 빠르게 확인할 수 있는 것입니다.

## <a name="accessing-the-conference-detail-report"></a>전화 회의 정보 보고서 액세스

다음 보고서에서 전화 회의 정보 보고서에 액세스할 수 있습니다.

- [Call Admission Control Report](call-admission-control-report.md)(전화 회의의 정보 메트릭 클릭)

- [Failure List Report](failure-list-report.md)(전화 회의 메트릭 클릭)

- [User Activity Report](call-diagnostic-reports-per-user.md)(전화 회의 URI 메트릭 클릭)

전화 회의 정보 보고서에서 진단 보고서(정보) 메트릭을 클릭하면 [Diagnostic Report](diagnostic-report.md)에 액세스할 수 있습니다.

## <a name="filters"></a>필터

없음. 전화 회의 정보 보고서는 필터링할 수 없습니다.

## <a name="metrics"></a>메트릭

다음 표에서는 전화 회의 정보 보고서의 전화 회의 정보 섹션에서 제공되는 정보를 보여 줍니다.

**전화 회의 정보 메트릭**


| **이름**                 | **설명**                                                                                                            |
|:-------------------------|:---------------------------------------------------------------------------------------------------------------------------|
| **전화 회의 URI** <br/> | 전화 회의에 할당된 URI입니다. 예를 들면 다음과 같습니다.  <br/> sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4  <br/> |
| **풀 FQDN** <br/>      | 세션에 포함된 등록자 풀 또는 에지 서버의 정규화된 도메인 이름입니다.  <br/>                             |
| **시작 시간** <br/>     | 전화 회의가 시작된 날짜 및 시간입니다.  <br/>                                                                          |
| **이끌이** <br/>      | 전화 회의를 구성한 사용자의 SIP 주소입니다.  <br/>                                                               |
| **종료 시간** <br/>       | 전화 회의가 종료된 날짜 및 시간입니다.  <br/>                                                                            |

다음 표에서는 전화 회의 정보 보고서의 전화 회의 참가 섹션에서 제공되는 정보를 보여 줍니다.

**전화 회의 참가 메트릭**

|**이름**|**설명**|
|:-----|:-----|
|**사용자** <br/> |전화 회의에 참가한 사용자의 SIP 주소입니다.  <br/> |
|**역할** <br/> |전화 회의 참가자가 수행하는 역할(예: 발표자)입니다.  <br/> |
|**연결성** <br/> |참가자의 네트워크 연결(일반적으로 내부 발신 또는 외부 발신)입니다.  <br/> |
|**참가 시간** <br/> |참가자가 전화 회의에 참가한 날짜 및 시간입니다.  <br/> |
|**나간 시간** <br/> |참가자가 전화 회의에서 나간 날짜 및 시간입니다.  <br/> |
|**사용자 에이전트** <br/> |참가자의 끝점에서 사용하는 소프트웨어의 식별자입니다.  <br/> |
|**진단 보고서** <br/> |진단 및 문제 해결 정보를 제공합니다. 여기에는 실패한 세션에 대한 SIP 응답 코드, 진단 헤더, 전화 회의 참가 시간 및 진단 ID가 포함됩니다.  <br/> |

다음 표에는 회의 정보 보고서의 회의 부호 섹션에 제공된 정보가 나열됩니다.

**전화 회의 형식 메트릭**

|**이름**|**설명**|
|:-----|:-----|
|**사용자** <br/> |전화 회의에 참가한 사용자의 SIP 주소입니다.  <br/> |
|**참가 시간** <br/> |참가자가 전화 회의에 참가한 날짜 및 시간입니다.  <br/> |
|**나간 시간** <br/> |참가자가 전화 회의에서 나간 날짜 및 시간입니다.  <br/> |
|**전화 회의 서버** <br/> |전화 회의에 사용된 전화 회의 서버의 URI입니다.  <br/> |
|**진단 보고서** <br/> |진단 및 문제 해결 정보를 제공합니다. 여기에는 실패한 세션에 대한 SIP 응답 코드, 진단 헤더, 전화 회의 참가 시간 및 진단 ID가 포함됩니다.  <br/> |


