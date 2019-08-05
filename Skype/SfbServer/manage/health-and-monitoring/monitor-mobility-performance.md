---
title: 비즈니스용 Skype 서버에서 성능에 대 한 이동성 모니터링
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: '요약: 비즈니스용 Skype 서버의 모바일 서비스 (Mcx) 및 통합 커뮤니케이션 웹 API (c)에 대해 알아봅니다.'
ms.openlocfilehash: 7b8340d90b5e1fa18c4dfaa7d61f986344ccbb33
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188772"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 성능에 대 한 이동성 모니터링
 
**요약:** 비즈니스용 Skype 서버의 모바일 서비스 (Mcx) 및 통합 커뮤니케이션 웹 API (c)에 대해 알아봅니다.
  
비즈니스용 Skype Server Mobility Service (Mcx) 및 통합 커뮤니케이션 웹 API (c)는 프런트 엔드 서버 및 프런트 엔드 풀의 로드를 늘립니다. Lync 및 lync 2013 Mobile을 실행 하는 android 및 Apple 장치는 물론 모바일 응용 프로그램이 2010 최소화 되는 경우에도 서버에 대 한 연결을 유지 하는 모바일 장치는 장치 보다 더 많은 부하를 할 수 있습니다. 모바일 응용 프로그램이 최소화 된 상태에서 서버에 대 한 연결을 종료 합니다. 이동성 사용량이 증가 함에 따라 이동성 성능을 모니터링 하 여 용량을 늘려야 할 시기를 결정 해야 합니다.

> [!NOTE]
> 이전 모바일 클라이언트에 대 한 MCX (Mobility Service) 지원은 더 이상 비즈니스용 Skype 서버 2019에서 사용할 수 없습니다. 현재 모든 비즈니스용 Skype 모바일 클라이언트는 이미 통합 커뮤니케이션 웹 API (인스턴트 메시징 (IM), 현재 상태, 대화 상대 지원)를 사용 합니다. MCX를 사용 하는 레거시 클라이언트가 있는 사용자는 현재 클라이언트로 업그레이드 해야 합니다.
  
이동성 성능에 영향을 주는 몇 가지 제한은 다음과 같습니다. 
  
- 사용 가능한 메모리
    
- 요청 큐 제한
    
- 동시 연결
    
- IIS 대기열 길이
    
이동성 성능에 영향을 줄 수 있는 서버의 다른 제한은 최대 12 개의 동시 로그인, 인증, 세션 갱신 및 종료입니다. 대부분의 배포의 경우 이러한 최대값을 수정할 필요가 없습니다.
  
## <a name="in-this-section"></a>이 섹션의

- [비즈니스용 Skype 서버에서 서버 메모리 용량 한도 모니터링](server-memory-capacity-limits.md)
    
- [비즈니스용 Skype 서버에서 이동성 서비스 및 함께 사용 모니터링](service-and-ucwa-usage.md)
    
- [비즈니스용 Skype 서버에서 고성능을 위한 이동성 서비스 구성](configure-service.md)
    
- [비즈니스용 Skype 서버에서 IIS 요청 추적 로그 파일 모니터링](iis-request-tracing-log-files.md)
    
- [비즈니스용 Skype 서버의 이동성 성능 카운터](performance-counters.md)
    

