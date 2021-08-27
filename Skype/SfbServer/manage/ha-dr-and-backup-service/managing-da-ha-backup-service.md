---
title: 재해 복구, 고가용성 및 백업 서비스 관리
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 재해 복구 작업에 대한 절차와 쌍으로 연결되는 프런트 엔드 풀에서 데이터를 동기화하는 백업 서비스 유지 관리 절차에 대해 자세히 알아보습니다.
ms.openlocfilehash: b8635728710efbd2c820b6ca57333f77b56d04e5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58612267"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a>재해 비즈니스용 Skype 서버, 고가용성 및 백업 서비스 관리

이 섹션에는 페어링된 프런트 엔드 풀에서 데이터를 동기화하는 백업 서비스를 유지 관리하기 위한 절차뿐만 아니라 재해 복구 작업에 대한 절차가 포함되어 있습니다.

장애 조치(failover)와 장애 복구(failback)라는 재해 복구 절차는 둘 다 수동 절차입니다. 따라서 재해가 발생한 경우 관리자는 장애 조치(failover) 절차를 직접 호출해야 합니다. 풀이 복구된 이후의 장애 복구(failback)에도 동일한 절차가 적용됩니다.

이 섹션의 재해 복구 절차에서는 다음을 가정합니다.

  - Plan for high availability and disaster recovery 에 설명된 바와 같이 서로 다른 사이트에 페어링된 프런트 엔드 [풀이 있는 배포가 있습니다.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 백업 서비스가 이러한 연결된 풀에서 실행되어 이들 풀을 동기화 상태로 유지하고 있습니다.

  - 중앙 관리 저장소가 두 풀 중 하나에서 호스팅되는 경우 이 저장소는 활성 마스터를 호스트하는 풀 중 하나와 대기를 호스팅하는 다른 풀과 함께 두 쌍으로 된 풀에서 설치 및 실행됩니다.

> [!IMPORTANT]
> 다음 절차에서 *PoolFQDN* 매개 변수는 영향을 받는 사용자가 리디렉션되는 풀이 아니라 재해에 영향을 받는 풀의 FQDN을 나타냅니다. 영향을 받는 일부 사용자의 경우 장애 조치(failover) 및 장애 복구(failback) cmdlet에서 동일한 풀(즉 장애 조치(failover) 전에 사용자가 있던 풀)을 참조합니다.<BR><br>예를 들어, 풀 P1에 있는 모든 사용자가 백업 풀 P2로 장애 조치(failover)된다고 가정해 보겠습니다. 관리자가 현재 P2에서 서비스를 받는 모든 사용자를 P1에서 서비스를 받도록 옮기려는 경우 관리자는 다음 단계를 수행해야 합니다. 
> <OL>
> <LI>
> <P>장애 복구(failback) cmdlet을 사용하여 원래 P1에 있던 모든 사용자를 P2에서 P1으로 장애 복구(failback)합니다. 이 경우 *PoolFQDN* 이 P1의 FQDN입니다.</P>
> <LI>
> <P>장애 조치(failover) cmdlet을 사용하여 원래 P2에 있던 모든 사용자를 P1으로 장애 조치(failover)합니다. 이 경우 PoolFQDN은 P2의 FQDN입니다.</P>
> <LI>
> <P>관리자가 나중에 이러한 P2 사용자를 다시 P2로 장애 복구(failback)하려는 경우 PoolFQDN이 P2의 FQDN입니다.</P></LI></OL><br>풀 무결성을 유지하려면 위의 1단계를 2단계 전에 수행해야 합니다. 1단계 전에 2단계를 시도하면 2단계 cmdlet이 실패합니다.


## <a name="see-also"></a>참고 항목

[고가용성 및 재해 복구 계획](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
