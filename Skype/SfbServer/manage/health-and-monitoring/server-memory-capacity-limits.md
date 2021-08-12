---
title: 서버 메모리 용량 제한을 모니터링합니다비즈니스용 Skype 서버
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
ms.assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
description: '요약: 서버 메모리 용량 제한을 모니터링하는 방법을 비즈니스용 Skype 서버.'
ms.openlocfilehash: d62ae4a7e9eaed4fd866107de276990c3d883d946b2d44035fcac4fa47b69e61
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54314464"
---
# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server"></a>서버 메모리 용량 제한을 모니터링합니다비즈니스용 Skype 서버
 
**요약:** 서버에서 서버 메모리 용량 제한을 모니터링하는 방법을 비즈니스용 Skype 서버.
  
> [!CAUTION]
> 용량 계획을 참조하는 이 항목의 정보는 Lync 2010 Mobile 클라이언트 및 Mcx(Mobility Service)에만 해당됩니다. Lync 2013 Mobile 클라이언트에서 사용하는 UCWA(Unified Communications Web API)에 대한 용량 계획은 Lync Server 2013 계획 도구에서 제공합니다. 

> [!NOTE]
> 레거시 모바일 클라이언트에 대한 MCX(Mobility Service) 지원은 2019년 8월 비즈니스용 Skype 서버 없습니다. 현재 비즈니스용 Skype 클라이언트는 이미 UCWA(Unified Communications Web API)를 사용하여 IM(인스턴트 메시징), 현재 상태 및 연락처를 지원하고 있습니다. MCX를 사용하는 레거시 클라이언트를 사용하는 사용자는 현재 클라이언트로 업그레이드해야 합니다.
  
두 모바일 성능 카운터를 사용하면 현재 사용량을 파악하고 mcx(비즈니스용 Skype 서버 Mobility Service)의 용량을 계획하고 UCWA의 메모리 사용량을 모니터링하는 데 도움이 됩니다. UCWA의 경우 카운터 범주는 **LS:WEB - UCWA입니다.** Mobility Service(Mcx)의 경우 카운터는 **LS:WEB - Mobile Communication Service 범주에 속합니다.** 모니터링할 카운터는 다음입니다.
  
- **현재 활성** 현재 상태 구독이 있는 활성 세션 수입니다. UCWA 또는 활성 현재 상태 구독이 있는 Mcx(Mobility Service)를 통해 등록된 현재 끝점 수(항상 연결된 모바일 사용자 수)입니다.
    
- **현재 활성 세션 수**- UCWA 또는 Mobility Service를 통해 등록된 현재 끝점 수입니다.
    
시간이 지날 때 현재 활성 세션 수와  **활성** 세션 수 간의 차이가 적을 경우, 이는 시간이 지날 때 대부분의 모바일 장치 사용자에게 Android 또는 Nokia 모바일 장치와 같은 항상 연결된 장치가 있는 것입니다(Mcx에만 해당). UCWA 항상 연결된 장치에는 Lync 2013 Mobile 클라이언트를 실행하는 Apple 및 Android 장치가 포함됩니다. 현재 **활성** 세션 수가 **Currently Active Session Count with Active Presence Subscriptions보다** 훨씬 높은 경우 이는 더 많은 사용자가 Apple iOS 장치 또는 Mcx 아래에 있는 백그라운드 끝점 Windows Phone 나타냅니다. (Windows Phone Lync 2013 Mobile 클라이언트만 등록됩니다.
  
예상 사용량, 용량 계획 결과 및 Mobility Service 및  기타 프런트 엔드 서버 카운터의 지속적인 모니터링을 기반으로 현재 활성 세션 수(Active **Presence Subscriptions)와** 현재 활성 세션 수 성능 카운터에 대한 제한을 설정해야 합니다. 설정한 제한을 통해 서버 용량을 평가하고 용량이 초과된 경우 경고를 발생하도록 할 수 있습니다.
  
적절한 제한을 결정하려면 먼저 Mobility Service에 대해 프런트 엔드 서버에서 사용할 수 있는 메모리의 수를 결정해야 합니다. 카운터를 모니터링하여 다음 수식에 따라 추가 용량을 계획해야 하는 경우를 파악합니다.
  
Mcx Mobility Service에서 사용하는 총 메모리(MB) = 164 + (400 + 134) / 1024 * **현재 활성** 상태 구독이 있는 활성 세션 수 + 400/ 1024 * ( **Currently Active Session Count**  -  **Currently Active Session Count with Active Presence Subscriptions)**
  
> [!IMPORTANT]
> Microsoft Lync Server 2010 용량 계산기는 플래너가 CPU, 메모리 및 하드 드라이브를 포함하여 비즈니스용 Skype 서버에 대해 요구 사항을 결정할 수 있도록 하는 모든 수식으로 미리 채운 스프레드시트입니다. 스프레드시트 및 관련 문서를 [다운로드할 수 있습니다.](https://go.microsoft.com/fwlink/p/?LinkID=212657) 
  
프런트 엔드 서버에는 장애 조치(failover) 상황에서 Mobility Service를 지원하기에 충분한 사용 가능한 메모리가 필요합니다. **Memory\Available Mbytes** 카운터를 사용하여 또는 앞에서 설명한 수식을 사용하여 프런트 엔드 서버에서 현재 사용 가능한 메모리를 모니터링하여 Mobility Service에서 사용할 것으로 예상되는 메모리 양을 계획할 수 있습니다.
  
예상 모바일 사용자 수를 계획할 때 프런트 엔드 서버에서 사용할 수 있는 메모리 양이 1,500MB보다 낮은 경우 Mobility Service를 지원하기 위해 하드웨어를 더 추가해야 합니다. 자세한 내용은 작업 설명서에서 [Monitor mobility for performance in 비즈니스용 Skype 서버](monitor-mobility-performance.md) 참조하십시오.
  
## <a name="see-also"></a>참고 항목

[모바일 기능을 통해 성능 비즈니스용 Skype 서버](monitor-mobility-performance.md)
