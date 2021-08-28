---
title: 비즈니스용 Skype 서버
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
ms.assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
description: '요약: 2016년 8월 진단 보고서에 대해 비즈니스용 Skype 서버.'
ms.openlocfilehash: dde192aa90cc0a9cd5b1d05fbe2852d1277a6953
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58590152"
---
# <a name="diagnostic-report-in-skype-for-business-server"></a>비즈니스용 Skype 서버
 
**요약:** 2016년 8월 진단 보고서에 비즈니스용 Skype 서버.
  
진단 보고서에서는 실패한 세션에 대한 진단 및 문제 해결 정보를 제공합니다. 이 정보에는 세션이 실패할 때 보고된 진단 ID와 진단 헤더가 모두 포함됩니다. 진단 ID는 SIP 메시지에 연결된 고유 식별자(ms-diagnostics 헤더 형식)이며, 진단 헤더는 진단 ID에 대해 함께 표시할 설명을 제공합니다. 또한 이 보고서에는 보고 구성 요소에서 인식된 유용한 문제 해결 정보가 포함될 수 있습니다. 예를 들면 다음과 같습니다.
  
- 오류를 일으킨 PSTN 게이트웨이에서 제공되는 이유 코드. PSTN 네트워크에서 발신 전화에 실패하면 ISUP(ISDN User Part) 이유 코드가 자동으로 생성됩니다. 예를 들어 PSTN 게이트웨이에서 전화를 완료하는 데 사용 가능한 회로 또는 채널이 없음을 나타내는 이유 코드 34를 전송할 수 있습니다.
    
- 연결 오류를 해결하기 위한 피어 FQDN, 포트 및 Winsock 오류
    
- DNS 확인 오류를 해결하기 위한 조회 대상 이름. DNS 확인은 클라이언트가 네임 서버에 연결하여 지정된 장치 이름에 해당하는 IP 주소를 요청할 때마다 수행됩니다.
    
## <a name="accessing-the-diagnostic-report"></a>진단 보고서 액세스

진단 보고서는 2013의 피어 투 피어 세션 세부 정보 보고서 또는 회의 세부 정보 보고서에서 진단 [보고서(세부 비즈니스용 Skype 서버)를](peer-to-peer-session-detail-report.md) 클릭하여 액세스할 수 있습니다.
  
## <a name="filters"></a>필터

없음. 진단 보고서는 필터링할 수 없습니다.
  
## <a name="metrics"></a>메트릭

다음 표에서는 각 세션에 대해 진단 보고서에 제공된 정보를 보여 줍니다.
  
**진단 보고서 메트릭**

|**이름**|**이 항목에 대한 정렬 가능 여부**|**설명**|
|:-----|:-----|:-----|
|**보고 시간** <br/> |아니요  <br/> |보고서가 기록된 날짜 및 시간입니다.  <br/> |
|**응답 코드** <br/> |아니요  <br/> |세션이 실패했을 때 전송된 SIP 응답 코드입니다.  <br/> |
|**요청 유형** <br/> |아니요  <br/> |실패한 SIP 요청 유형입니다. 예: INVITE, BYE 또는 SERVICE  <br/> |
|**원본** <br/> |아니요  <br/> |오류 원본입니다.  <br/> |
|**보낸 사용자 URI** <br/> |아니요  <br/> |세션을 시작한 사용자의 SIP 주소입니다.  <br/> |
|**출처 사용자 에이전트** <br/> |아니요  <br/> |세션을 시작한 사용자의 끝점에 사용된 소프트웨어입니다.  <br/> |
|**진단 ID** <br/> |아니요  <br/> |오류 문제를 해결할 때 종종 유용한 정보를 제공하는 SIP 메시지에 연결된 고유 식별자(ms-diagnostics 헤더 형식)입니다.  <br/> |
|**콘텐츠 형식** <br/> |아니요  <br/> |실패한 미디어 콘텐츠 형식입니다. 예를 들어 공통 콘텐츠 형식은 Application/sdp입니다. SDP(Session Description Protocol)는 세션 알림, 세션 초대 및 멀티 미디어 세션 초대의 다른 형식에 사용된 표준 인터넷 프로토콜입니다.  <br/> |
|**응용 프로그램** <br/> |아니요  <br/> |오류와 관련된 응용 프로그램입니다.  <br/> |
|**대상 사용자 URI** <br/> |아니요  <br/> |세션에 초대된 사용자의 SIP 주소입니다.  <br/> |
|**전화 회의 참가 시간(밀리초)** <br/> |아니요  <br/> |사용자가 전화 회의에 참가하기까지 소요된 시간(밀리초)입니다.  <br/> |
|**진단 헤더** <br/> |아니요  <br/> |진단 ID 설명입니다.  <br/> |
   
진단 오류 목록은 [Ms-Diagnostics 헤더](/openspecs/office_protocols/ms-ocer/f6787b39-0842-43ca-94a2-6afadda5f0a3)페이지에서 찾을 수 있습니다.
