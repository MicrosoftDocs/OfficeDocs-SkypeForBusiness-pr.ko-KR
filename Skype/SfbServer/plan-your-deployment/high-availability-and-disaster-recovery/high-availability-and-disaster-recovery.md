---
title: 2013에서 고가용성 및 재해 복구 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.custom:
- ms.lync.plan.HighAvailabilityType
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 3543eb40-54f4-49ef-a058-03aceed4773a
description: 비즈니스용 Skype 서버 서버 풀링을 통해 고가용성, 풀 페어링을 통해 재해 복구, AlwaysOn 가용성 그룹, 데이터베이스 미러링 및 장애 조치(failover) 클러스터링을 비롯한 여러 가지 백 엔드 서버 고가용성 SQL 제공합니다.
ms.openlocfilehash: ef5275ccb11e6428a4084bec1b7f2f0b2dddcd5f
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62416461"
---
# <a name="plan-for-high-availability-and-disaster-recovery-in-skype-for-business-server"></a>2013에서 고가용성 및 재해 복구 비즈니스용 Skype 서버
 
비즈니스용 Skype 서버 서버 풀링을 통해 고가용성, 풀 페어링을 통해 재해 복구, AlwaysOn 가용성 그룹, 데이터베이스 미러링 및 장애 조치(failover) 클러스터링을 비롯한 여러 가지 백 엔드 서버 고가용성 SQL 제공합니다. 
  
고가용성이란 하나 이상의 서버가 비즈니스용 Skype 서버 서비스를 사용할 수 있도록 하는 것입니다. 재해 복구란 자연적 또는 사람이 발생한 재해가 발생할 경우 서비스를 계속 진행하고 재해 이전의 데이터를 최대한 많이 보존하는 것을 참조합니다.
  
이전 버전의 Lync Server에서와 동일하게, 대부분의 서버 역할에 대한 주요 고가용성 비즈니스용 Skype 서버 풀링을 통한 서버 중복성입니다. 특정 서버 역할을 실행하는 서버에서 오류가 발생하면 같은 역할을 실행하는 풀의 다른 서버가 해당 서버의 부하를 대신 처리합니다. 이는 프런트 엔드 서버, 에지 서버, 중재 서버 및 디렉터에 적용됩니다.
  
비즈니스용 Skype 서버 프런트 엔드 풀에 대한 재해 복구 옵션도 제공합니다. 서로 다른 지역에 백업으로 사용할 두 개의 풀을 설정할 수 있습니다. 그런 다음 전체 풀 또는 사이트가 다운된 경우 백업 풀은 두 사이트의 사용자에게 서비스를 계속 제공할 수 있습니다.
  
비즈니스용 Skype 서버 서버는 백 엔드 서버에 대해 SQL 미러링, AlwaysOn 가용성 그룹, AlwaysOn FCI(장애 조치(Failover) 클러스터 인스턴스) 및 장애 조치(failover) 클러스터링의 SQL 모드도 지원됩니다.
  
> [!NOTE]
> SQL 미러링은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다. AlwaysOn 가용성 그룹, AlwaysOn FCI(장애 조치(failover) 클러스터 인스턴스) 및 SQL 장애 조치(failover) 클러스터링 방법이 비즈니스용 Skype 서버 선호됩니다.

> [!NOTE]
> AlwaysOn 가용성 그룹은 영구 채팅 서버에서 지원되지 않습니다. 
  
이 섹션에서는 이러한 기능에 대해 설명하고 다른 서버 역할 중 일부에 대해 고가용성 및 재해 복구를 위해 취할 수 있는 단계에 대해 설명합니다. 
  
## <a name="see-also"></a>참고 항목

[프런트 엔드 풀 고가용성 및 관리](high-availability.md)
  
[프런트 엔드 풀 재해 비즈니스용 Skype 서버](disaster-recovery.md)
  
[2016년 8월 풀 오류 시 사용자 비즈니스용 Skype 서버](user-experience.md)
  
[백 엔드 서버의 고가용성 비즈니스용 Skype 서버](back-end-server.md)
  
[파일 공유 고가용성 비즈니스용 Skype 서버](file-sharing.md)
