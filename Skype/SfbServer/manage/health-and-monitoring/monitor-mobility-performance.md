---
title: 모바일 기능을 통해 성능 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: '요약: Mcx(Mobility Service) 및 UCWA(Unified Communications Web API)에 대해 비즈니스용 Skype 서버.'
ms.openlocfilehash: 57f892c06c1db979463385715d8c941b92e5d739
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62416551"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>모바일 기능을 통해 성능 비즈니스용 Skype 서버
 
**요약:** Mcx(Mobility Service) 및 UCWA(Unified Communications Web API)에 대해 비즈니스용 Skype 서버.
  
Mcx(비즈니스용 Skype 서버 Mobility Service) 및 UCWA(Unified Communications Web API)를 통해 프런트 엔드 서버 및 프런트 엔드 풀의 부하가 증가합니다. Lync 2010 Mobile을 실행하는 Android 및 Nokia 장치, 그리고 Lync 2013 Mobile을 실행하는 Android 및 Apple 장치와 같이 모바일 응용 프로그램이 최소화된 경우에도 서버에 대한 연결을 유지 관리하는 모바일 장치는 모바일 응용 프로그램이 최소화될 때 서버에 대한 연결을 종료하는 장치보다 더 큰 부하를 부과합니다. 모바일 기능을 사용할수록 모바일 성능을 모니터링하여 용량을 늘리야 하는 경우를 결정해야 합니다.

> [!NOTE]
> 레거시 모바일 클라이언트에 대한 MCX(Mobility Service) 지원은 2019년 8월 비즈니스용 Skype 서버 없습니다. 현재 비즈니스용 Skype 클라이언트는 이미 UCWA(Unified Communications Web API)를 사용하여 IM(인스턴트 메시징), 현재 상태 및 연락처를 지원하고 있습니다. MCX를 사용하는 레거시 클라이언트를 사용하는 사용자는 현재 클라이언트로 업그레이드해야 합니다.
  
다음과 같은 다양한 제한이 모바일 성능에 영향을 줍니다. 
  
- 사용 가능한 메모리
    
- 요청 큐 제한
    
- 동시 연결 수
    
- IIS 큐 길이
    
모바일 성능에 영향을 줄 수 있는 서버에 대한 다른 제한은 최대 12개 동시 로그인, 인증, 세션 갱신 및 종료입니다. 대부분의 배포에서는 이러한 최대값을 수정할 필요가 없습니다.
  
## <a name="in-this-section"></a>이 섹션의 내용

- [서버 메모리 용량 제한을 모니터링합니다비즈니스용 Skype 서버](server-memory-capacity-limits.md)
    
- [모바일 서비스 및 UCWA 사용 현황 비즈니스용 Skype 서버](service-and-ucwa-usage.md)
    
- [모바일 서비스에서 고성능을 위해 Mobility Service 비즈니스용 Skype 서버](configure-service.md)
    
- [IIS 요청 추적 로그 파일 모니터링 비즈니스용 Skype 서버](iis-request-tracing-log-files.md)
    
- [모바일 성능 카운터의 비즈니스용 Skype 서버](performance-counters.md)
    

