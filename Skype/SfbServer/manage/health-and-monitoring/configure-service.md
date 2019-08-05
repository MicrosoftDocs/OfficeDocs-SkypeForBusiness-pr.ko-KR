---
title: 비즈니스용 Skype 서버에서 고성능을 위한 이동성 서비스 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: '요약: 비즈니스용 Skype 서버의 모바일 서비스에 대해 자세히 알아보세요.'
ms.openlocfilehash: 35e04fa080964495ccd9abed28c0688dd7be45a9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197653"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 고성능을 위한 이동성 서비스 구성
 
**요약:** 비즈니스용 Skype 서버의 모바일 서비스에 대해 자세히 알아보세요.
  
> [!IMPORTANT]
> 이 항목은 비즈니스용 Skype Server Mobility Service (Mcx)에만 적용 되며 Lync Server 2013의 누적 업데이트에서 제공 되는 통합 커뮤니케이션 웹 API (c 2:2013)에는 적용 되지 않습니다. 
  
IIS (인터넷 정보 서비스) 7.5에서 모바일 서비스 (Mcx)를 설치 하면 모바일 서비스 설치 관리자가 프런트 엔드 서버에서 일부 성능 설정을 구성 합니다. 이동성에 IIS 7.5를 사용 하는 것이 좋습니다. 설정은 최대 동시 사용자 요청 수와 모바일 서비스에 허용 되는 최대 스레드 수에 영향을 줍니다.
  
다음은 성능 설정에 대 한 내용입니다.
  
### <a name="settings-for-mcx-on-iis-75"></a>IIS 7.5에서 Mcx에 대 한 설정

1. **maxConcurrentThreadsPerCPU** 가 0으로 설정 됩니다.
    
2. **maxConcurrentRequestsPerCPU** 가 0으로 설정 됩니다.
    
3. ASP.NET 프로세스 모델이 AutoConfig로 설정 됩니다 (IIS 7.5에만 해당).
    
4. Http.sys 큐 한도가 1000 (기본적으로)으로 설정 됩니다.
    

