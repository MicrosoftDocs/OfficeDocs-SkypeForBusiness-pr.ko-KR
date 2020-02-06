---
title: 고가용성 및 재해 복구 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: 비즈니스용 Skype 서버는 서버 풀링을 사용 하 여 높은 가용성을 제공 하 고, 풀 페어링을 사용한 재해 복구, AlwaysOn 가용성 그룹, 데이터베이스 미러링, SQL 장애 조치 클러스터링을 비롯 한 백 엔드 서버의 높은 가용성 모드 중 몇 가지입니다.
ms.openlocfilehash: 68c6a12f80ac2d915c678f69146d0001daedbe5c
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790126"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a>고가용성 및 재해 복구 배포
 
비즈니스용 Skype 서버는 서버 풀링을 사용 하 여 높은 가용성을 제공 하 고, 풀 페어링을 사용한 재해 복구, AlwaysOn 가용성 그룹, 데이터베이스 미러링, SQL 장애 조치 클러스터링을 비롯 한 백 엔드 서버의 높은 가용성 모드 중 몇 가지입니다. 
  
고가용성은 하나 이상의 서버가 작동 하지 않는 경우에도 비즈니스용 Skype 서버 서비스를 사용할 수 있는지 확인 하는 것을 의미 합니다. 재해 복구는 서비스를 자연 스런 실수 또는 사람이 실수로 발생 한 경우를 유지 하 고 재해가 발생할 때까지 최대한 많은 데이터를 유지 하는 것을 의미 합니다.
  
이 섹션에서는 이러한 기능을 배포 하는 방법에 대해 설명 하 고, 다른 일부 서버 역할에 대 한 가용성 및 재해 복구를 위해 수행할 수 있는 단계에 대해서도 알아봅니다.

> [!NOTE]
> SQL 미러링은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다. AlwaysOn 가용성 그룹,이 어 장애 조치 (Failover) 클러스터 인스턴스 (FCI) 및 SQL 장애 조치 (failover) 클러스터링 방법은 비즈니스용 Skype 서버 2019에서 선호 됩니다.
  
## <a name="related-sections"></a>관련 섹션

[비즈니스용 Skype 서버에서 고가용성 및 재해 복구 계획](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버에서 백 엔드 서버에 AlwaysOn 가용성 그룹 배포](alwayson-availability-group.md)

[비즈니스용 Skype 서버에서 재해 복구용으로 쌍을 이루는 프런트 엔드 풀 배포](front-end-pools-for-disaster-recovery.md)
  
[비즈니스용 Skype 서버 2015에서 백 엔드 서버에 대 한 SQL 미러링 배포 높은 가용성을 제공 합니다.](sql-mirroring-for-high-availability.md)
  
