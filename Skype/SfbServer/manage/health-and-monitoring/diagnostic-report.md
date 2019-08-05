---
title: 비즈니스용 Skype 서버의 진단 보고서
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
description: '요약: 비즈니스용 Skype 서버의 진단 보고서에 대해 알아보세요.'
ms.openlocfilehash: d71906f2407a0daadc04417ab60a23c86f5eeb52
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197640"
---
# <a name="diagnostic-report-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 진단 보고서
 
**요약:** 비즈니스용 Skype 서버의 진단 보고서에 대해 알아보세요.
  
진단 보고서는 실패 한 세션에 대 한 진단 및 문제 해결 정보를 제공 합니다. 이 정보에는 진단 ID와 세션에 실패 했을 때 보고 된 진단 헤더가 모두 포함 됩니다. 진단 ID는 SIP 메시지에 연결 되는 고유 식별자 (ms-진단 헤더 형식) 이며 진단 헤더는 진단 ID에 대해 함께 설명 합니다. 보고 구성 요소에서 인식 하는 중요 한 문제 해결 세부 정보를 보고서에 포함할 수도 있습니다. 예를 들면 다음과 같습니다.
  
- 오류를 생성 한 PSTN 게이트웨이에서 제공 하는 원인 코드입니다. PSTN 네트워크에서 발신 통화가 실패 하면, ISDN 사용자 파트 (ISUP)가 자동으로 생성 됩니다. 예를 들어 PSTN 게이트웨이에서는 통화를 완료 하는 데 사용할 수 있는 회로 또는 채널이 없음을 나타내기 위해 코드 34를 보낼 수 있습니다.
    
- 연결 오류에 대 한 피어 FQDN, 포트 및 Winsock 오류.
    
- DNS 확인 실패를 조회 하는 이름입니다. DNS 확인은 클라이언트가 이름 서버에 접속 하 고 지정 된 디바이스 이름에 해당 하는 IP 주소를 요청 하는 경우에 발생 합니다.
    
## <a name="accessing-the-diagnostic-report"></a>진단 보고서에 액세스

[비즈니스용 Skype 서버의 피어 투 피어 세션 세부 정보 보고서](peer-to-peer-session-detail-report.md) 또는 회의 세부 정보 보고서에서 진단 보고서 (세부 정보) 메트릭을 클릭 하 여 진단 보고서에 액세스할 수 있습니다.
  
## <a name="filters"></a>필터가

없음. 진단 보고서는 필터링 할 수 없습니다.
  
## <a name="metrics"></a>매트릭스

다음 표에는 진단 보고서에서 각 세션에 대해 제공 하는 정보가 나열 되어 있습니다.
  
**진단 보고서 메트릭**

|**이름**|**이 항목을 정렬할 수 있나요?**|**설명**|
|:-----|:-----|:-----|
|**보고서 시간** <br/> |아니요  <br/> |보고서가 기록 된 날짜 및 시간입니다.  <br/> |
|**응답 코드** <br/> |아니요  <br/> |세션이 실패 했을 때 전송 된 SIP 응답 코드입니다.  <br/> |
|**요청 형식** <br/> |아니요  <br/> |실패 한 SIP 요청 유형입니다. 예를 들어 초대, BYE, 서비스 등이 있습니다.  <br/> |
|**Source** <br/> |아니요  <br/> |오류의 원본입니다.  <br/> |
|**사용자 URI에서** <br/> |아니요  <br/> |세션을 시작한 사용자의 SIP 주소입니다.  <br/> |
|**사용자 에이전트에서** <br/> |아니요  <br/> |세션을 시작한 사용자의 끝점에 사용 되는 소프트웨어입니다.  <br/> |
|**진단 ID** <br/> |아니요  <br/> |오류 문제 해결에 유용한 정보를 자주 제공 하는 SIP 메시지에 첨부 된 고유 식별자 (ms-진단 헤더 형식)입니다.  <br/> |
|**콘텐츠 형식** <br/> |아니요  <br/> |실패 한 미디어 콘텐츠의 유형입니다. 예를 들어 공용 콘텐츠 형식은 Application/sdp입니다. SDP (세션 설명 프로토콜)는 세션 공지 사항, 세션 초대 및 다른 형식의 멀티미디어 세션 초기화에 사용 되는 표준 인터넷 프로토콜입니다.  <br/> |
|**프로그램** <br/> |아니요  <br/> |오류와 관련 된 응용 프로그램  <br/> |
|**사용자 URI로** <br/> |아니요  <br/> |세션에 초대 된 사용자의 SIP 주소입니다.  <br/> |
|**컨퍼런스 참가 시간 (ms)** <br/> |아니요  <br/> |사용자가 회의에 참가 하는 데 걸린 시간 (밀리초 단위)입니다.  <br/> |
|**진단 헤더** <br/> |아니요  <br/> |진단 ID 설명입니다.  <br/> |
   
진단 오류 목록은 [Ms-진단 헤더 페이지](https://msdn.microsoft.com/en-us/library/gg132446%28v=office.12%29.aspx)에서 찾을 수 있습니다.
  

