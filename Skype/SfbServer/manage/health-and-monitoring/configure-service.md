---
title: 비즈니스용 Skype 서버에서 고성능 모바일 서비스 구성
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
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: '요약: 비즈니스용 Skype 서버의 Mobility Service에 대해 자세히 알아보습니다.'
ms.openlocfilehash: 83d8d6dc7a32b05a58c738deddc8c92e43bd5557
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817038"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 고성능 모바일 서비스 구성
 
**요약:** 비즈니스용 Skype 서버의 Mobility Service에 대해 자세히 알아보습니다.
  
> [!IMPORTANT]
> 이 항목은 비즈니스용 Skype 서버 Mobility Service(Mcx)에만 적용되고 Lync Server 2013: 2013년 2월 누적 업데이트에 제공된 UCWA(Unified Communications Web API)에는 적용되지 않습니다. 
  
IIS(인터넷 정보 서비스) 7.5에 Mcx(Mobility Service)를 설치하면 Mobility Service 설치 관리자에서 프런트 엔드 서버에서 일부 성능 설정을 구성합니다. 모바일 기능에는 IIS 7.5를 사용하는 것이 좋습니다. 이러한 설정은 최대 동시 사용자 요청 수 및 Mobility Service에 대해 허용되는 최대 스레드 수에 영향을 줍니다.
  
성능 설정은 다음과 같습니다.
  
### <a name="settings-for-mcx-on-iis-75"></a>IIS 7.5의 Mcx 설정

1. **maxConcurrentThreadsPerCPU** 는 영(0)으로 설정됩니다.
    
2. **maxConcurrentRequestsPerCPU** 는 영(0)으로 설정됩니다.
    
3. ASP.NET 프로세스 모델은 AutoConfig로 설정됩니다(IIS 7.5에만 해당).
    
4. HTTP.sys 큐 제한은 기본적으로 1,000으로 설정됩니다.
    

