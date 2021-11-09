---
title: 모바일 서비스 및 UCWA 사용 현황 비즈니스용 Skype 서버
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
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: '요약: Mcx(Mobility Service) 및 UCWA(Unified Communications Web API)를 비즈니스용 Skype 서버.'
ms.openlocfilehash: 6139ab53e964bd7c880a83a7af252fe2da71a152
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60835256"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a>모바일 서비스 및 UCWA 사용 현황 비즈니스용 Skype 서버
 
**요약:** Mcx(Mobility Service) 및 UCWA(Unified Communications Web API)를 비즈니스용 Skype 서버.

> [!NOTE]
> 레거시 모바일 클라이언트에 대한 MCX(Mobility Service) 지원은 2019년 8월 비즈니스용 Skype 서버 없습니다. 현재 비즈니스용 Skype 클라이언트는 이미 UCWA(Unified Communications Web API)를 사용하여 IM(인스턴트 메시징), 현재 상태 및 연락처를 지원하고 있습니다. MCX를 사용하는 레거시 클라이언트를 사용하는 사용자는 현재 클라이언트로 업그레이드해야 합니다.
  
Mcx(비즈니스용 Skype 서버 Mobility Service) 및 UCWA(Unified Communications Web API)에서 사용하는 CPU 및 메모리를 지속적인 모니터링해야 합니다. 사용량을 모니터링하기 위해 다음을 사용할 수 있습니다.
  
 **UCWA(Unified Communications Web API)의 경우:**
  
- IIS(인터넷 정보 서비스 관리자)의 **LyncUcwa** worker 프로세스 **작업자 프로세스** 창에서 **CPU %** 및 **전용 바이트(KB)**(메모리) 열을 확인합니다.
    
- **CPU** 및 **프로세서** 성능 카운터
    
대부분의 배포에서 UCWA CPU 사용량은 평균적으로 15% 미만입니다. 메모리 사용량은 에서 서버 메모리 용량 제한 모니터링에 설명된 제한 내에 [비즈니스용 Skype 서버.](server-memory-capacity-limits.md)
  
CPU 및 메모리 사용 카운터 외에도 다음 성능 카운터를 사용하여 서버가 요청으로 오버로드된 경우를 확인할 수 있습니다.
  
- **LS:WEB - 스로틀 및 인증\WEB -** 처리 중인 총 요청 수로, 서버에서 보류 중인 웹 요청 수를 나타냅니다. 이 카운터가 10,000에 도달하면 "503 - 서비스를 사용할 수 없습니다."라는 오류 메시지가 표시된 후속 요청이 실패합니다.
    
- **ASP.NET\Requests Queued**(항상 0이어야 함).
    
> [!NOTE]
> 이러한 값을 충족하거나 초과하는 경우 CPU의 올바른 크기 조정, 웹 서비스를 호스트하는 컴퓨터의 코어 수 및 메모리에 대한 용량 계획을 다시 재구성하고 다시 계산해야 합니다. 
  
 **Mobility Service(Mcx)의 경우:**
  
- IIS(인터넷 정보 서비스 관리자의 **CSIntMcxAppPool** 및 **CSExtMcxAppPool** 작업자 프로세스) **작업자 프로세스** 창에서 **CPU %** 및 **전용 바이트(KB)**(메모리) 열을 확인합니다.
    
- **CPU** 및 **프로세서** 성능 카운터
    
대부분의 배포에서 Mobility Service CPU 사용량은 평균적으로 15% 미만입니다. 메모리 사용량은 에서 서버 메모리 용량 제한 모니터링에 설명된 제한 내에 [비즈니스용 Skype 서버.](server-memory-capacity-limits.md)
  
CPU 및 메모리 사용량 카운터 외에 다음 ASP.NET 성능 카운터를 사용하여 서버가 너무 많은 요청으로 인해 오버로드되었는지를 확인할 수 있습니다.
  
- **ASP.NET 웹 요청 수를 나타내는 v2.0.50727\Requests Current를** 나타냅니다. 이 카운터가 5,000에 도달하면 "503 - 서비스를 사용할 수 없습니다."라는 오류 메시지와 함께 후속 요청이 실패합니다.
    
- **ASP.NET\Requests Queued**(항상 0이어야 함).
    
> [!NOTE]
> 이러한 값을 충족하거나 초과하는 경우 웹 서비스를 호스팅하는 컴퓨터의 CPU, 코어 수 및 메모리의 올바른 크기 조정을 위해 용량 계획을 다시 재구성하고 다시 구성해야 합니다. 

> [!NOTE]
> 레거시 모바일 클라이언트에 대한 MCX(Mobility Service) 지원은 2019년 8월 비즈니스용 Skype 서버 없습니다. 현재 비즈니스용 Skype 클라이언트는 이미 UCWA(Unified Communications Web API)를 사용하여 IM(인스턴트 메시징), 현재 상태 및 연락처를 지원하고 있습니다. MCX를 사용하는 레거시 클라이언트를 사용하는 사용자는 현재 클라이언트로 업그레이드해야 합니다.
  
## <a name="see-also"></a>참고 항목

[서버 메모리 용량 제한을 모니터링합니다비즈니스용 Skype 서버](server-memory-capacity-limits.md)
