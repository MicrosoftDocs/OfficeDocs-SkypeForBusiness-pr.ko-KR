---
title: 고가용성 및 재해 복구 배포
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 21007bad-62ce-4553-98e0-02aaa1345781
description: 비즈니스용 Skype 서버 서버 풀링을 통해 고가용성, 풀 페어링을 통해 재해 복구, AlwaysOn 가용성 그룹, 데이터베이스 미러링 및 장애 조치(failover) 클러스터링을 비롯한 여러 가지 백 엔드 서버 고가용성 SQL 제공합니다.
ms.openlocfilehash: 897bd52d265a123d3eebec2bc16d71d95ba6185e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60865305"
---
# <a name="deploy-high-availability-and-disaster-recovery"></a>고가용성 및 재해 복구 배포
 
비즈니스용 Skype 서버 서버 풀링을 통해 고가용성, 풀 페어링을 통해 재해 복구, AlwaysOn 가용성 그룹, 데이터베이스 미러링 및 장애 조치(failover) 클러스터링을 비롯한 여러 가지 백 엔드 서버 고가용성 SQL 제공합니다. 
  
고가용성이란 하나 이상의 서버가 비즈니스용 Skype 서버 서비스를 사용할 수 있도록 하는 것입니다. 재해 복구란 자연적 또는 사람이 발생한 재해가 발생할 경우 서비스를 계속 진행하고 재해 이전의 데이터를 최대한 많이 보존하는 것을 참조합니다.
  
이 섹션에서는 이러한 기능을 배포하는 방법을 설명하고 다른 서버 역할 중 일부에 대해 고가용성 및 재해 복구를 위해 취할 수 있는 단계도 설명합니다.

> [!NOTE]
> SQL 미러링은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 2019년 8월에는 더 이상 비즈니스용 Skype 서버 없습니다. AlwaysOn 가용성 그룹, AlwaysOn FCI(장애 조치(failover) 클러스터 인스턴스) 및 SQL 장애 조치(failover) 클러스터링 방법이 비즈니스용 Skype 서버 선호됩니다.
  
## <a name="related-sections"></a>관련 섹션

[2013에서 고가용성 및 재해 복구 비즈니스용 Skype 서버](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  
## <a name="see-also"></a>참고 항목

[서버의 백 엔드 서버에 AlwaysOn 가용성 비즈니스용 Skype 서버](alwayson-availability-group.md)

[페어링된 프런트 엔드 풀을 배포하여 재해 복구를 비즈니스용 Skype 서버](front-end-pools-for-disaster-recovery.md)
  
[2015 SQL 백 엔드 서버 고가용성을 위한 비즈니스용 Skype 서버 미러링 배포](sql-mirroring-for-high-availability.md)
  
