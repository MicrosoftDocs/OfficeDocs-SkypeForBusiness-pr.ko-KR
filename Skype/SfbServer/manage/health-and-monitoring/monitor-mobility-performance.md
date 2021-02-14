---
title: 비즈니스용 Skype 서버에서 모바일 성능 모니터링
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: '요약: 비즈니스용 Skype 서버의 Mobility Service(Mcx) 및 UCWA(Unified Communications Web API)에 대해 자세히 알아보습니다.'
ms.openlocfilehash: d7473d22f2de0576bf6214ae43719c8bfc70d49a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816838"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 모바일 성능 모니터링
 
**요약:** 비즈니스용 Skype 서버의 Mcx(Mobility Service) 및 UCWA(Unified Communications Web API)에 대해 자세히 알아보습니다.
  
비즈니스용 Skype 서버 모바일 서비스(Mcx) 및 UCWA(Unified Communications Web API)를 통해 프런트 엔드 서버 및 프런트 엔드 풀의 부하가 증가합니다. 모바일 응용 프로그램이 최소화된 경우에도 서버에 대한 연결을 유지하는 모바일 장치(예: Lync 2010 Mobile을 실행하는 Android 및 Nokia 장치 및 Lync 2013 Mobile을 실행하는 Android 및 Apple 장치)는 모바일 응용 프로그램이 최소화될 때 서버에 대한 연결을 종료하는 장치보다 더 큰 부하를 가합니다. 모바일 사용이 증가하면 모바일 성능을 모니터링하여 용량을 늘해야 하는 경우를 결정해야 합니다.

> [!NOTE]
> 레거시 모바일 클라이언트에 대한 MCX(Mobility Service) 지원은 비즈니스용 Skype 서버 2019에서 더 이상 사용할 수 없습니다. 모든 현재 비즈니스용 Skype 모바일 클라이언트는 이미 UCWA(Unified Communications Web API)를 사용하여 IM(인스턴트 메시징), 현재 상태 및 연락처를 지원하고 있습니다. MCX를 사용하는 레거시 클라이언트를 사용하는 사용자는 현재 클라이언트로 업그레이드해야 합니다.
  
다음과 같은 다양한 제한이 모바일 성능에 영향을 줍니다. 
  
- 사용 가능한 메모리
    
- 요청 큐 제한
    
- 동시 연결 수
    
- IIS 큐 길이
    
모바일 성능에 영향을 줄 수 있는 서버에 대한 기타 제한은 최대 12개 동시 로그인, 인증, 세션 갱신 및 종료입니다. 대부분의 배포에서는 이러한 최대값을 수정할 필요가 없습니다.
  
## <a name="in-this-section"></a>이 섹션의 내용

- [비즈니스용 Skype 서버에서 서버 메모리 용량 제한 모니터링](server-memory-capacity-limits.md)
    
- [비즈니스용 Skype 서버에서 Mobility Service 및 UCWA 사용 모니터링](service-and-ucwa-usage.md)
    
- [비즈니스용 Skype 서버에서 고성능 모바일 서비스 구성](configure-service.md)
    
- [비즈니스용 Skype 서버에서 IIS 요청 추적 로그 파일 모니터링](iis-request-tracing-log-files.md)
    
- [비즈니스용 Skype 서버의 모바일 성능 카운터](performance-counters.md)
    

