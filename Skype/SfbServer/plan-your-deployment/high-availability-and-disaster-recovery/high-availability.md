---
title: 프런트 엔드 풀 고가용성 및 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: 두 개의 프런트 엔드 서버가 포함 된 풀에 대 한 풀, 쿼럼 손실 및 특수 단계 관리를 포함 하 여 비즈니스용 Skype 서버의 프런트 엔드 풀 관리에 대해 알아봅니다.
ms.openlocfilehash: 2982e2da0e7a103b5b598019baa7403a73da826d
ms.sourcegitcommit: 397c4840fb053238de24b8b24ae75588b33b693d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2020
ms.locfileid: "45098436"
---
# <a name="front-end-pool-high-availability-and-management"></a>프런트 엔드 풀 고가용성 및 관리
 
두 개의 프런트 엔드 서버가 포함 된 풀에 대 한 풀, 쿼럼 손실 및 특수 단계 관리를 포함 하 여 비즈니스용 Skype 서버의 프런트 엔드 풀 관리에 대해 알아봅니다.
  
비즈니스용 Skype 서버에서 프런트 엔드 풀의 아키텍처는 분산 시스템 모델을 사용 하며 각 사용자의 데이터는 풀의 프런트 엔드 서버 3 대까지 유지 됩니다. 모든 Enterprise Edition 프런트 엔드 풀에는 세 개 이상의 프런트 엔드 서버가 포함 되는 것이 좋습니다.

> [!NOTE]
> 비즈니스용 Skype 서버 2019에서는 프런트 엔드 서버가 두 대 인 Enterprise Edition 프런트 엔드 풀을 지원 하지 않으며,이 시나리오에서 토폴로지를 게시할 수 없습니다.
  
## <a name="planning-for-the-management-of-front-end-pools"></a>프런트 엔드 풀 관리 계획

 비즈니스용 Skype 서버는 Windows Fabric을 기반으로 하는 분산 시스템 모델을 사용 합니다. 이 모델에서는 각 사용자 및 전화 회의에 대 한 중요 한 데이터가 프런트 엔드 풀의 세 프런트 엔드 서버에 저장 됩니다. 특정 데이터 집합을 저장 하는이 세 서버는 calledreplicas입니다.
  
프런트 엔드 풀에 대 한 분산 모델을 사용 하는 경우 풀이 작동 하려면 특정 그룹의 서버가 실행 중 이어야 합니다. 풀에는 두 가지 손실 모드를 사용할 수 있습니다.
  
- 특정 라우팅 그룹에 대 한 복제본 서버가 부족 하 여 라우팅 그룹 수준 쿼럼 손실이 발생 했습니다. 라우팅 그룹은 풀에 속한 사용자 집합입니다. 각 라우팅 그룹에는 하나의 주 복제본과 두 개의 보조 복제본의 풀에 세 개의 복제본이 있습니다.
    
- 풀 수준 쿼럼 손실 (풀에서 시드 서버가 충분히 실행 되지 않을 때 발생 하는 경우) 
    
### <a name="routing-group-level-quorum-loss"></a>라우팅 그룹 수준 쿼럼 손실

새 프런트 엔드 풀을 처음 시작 하는 경우에는 다음 표에 나와 있는 것과 같이 서버 중에서 1 ~ 85%가 작동 하는 것이 중요 합니다. 실행 중인 서버가 적으면 서비스가 시작 상태에 걸려 풀이 시작 되지 않을 수 있습니다.
  
|풀에 있는 총 서버 수  <br/> |풀을 처음 시작할 때 실행 해야 하는 서버 수  <br/> |
|:-----|:-----|
|2   <br/> |1   <br/> |
|3   <br/> |3   <br/> |
|4   <br/> |3   <br/> |
|5   <br/> |4   <br/> |
|6   <br/> |5   <br/> |
|7   <br/> |5   <br/> |
|8   <br/> |6   <br/> |
|9   <br/> |7   <br/> |
|10   <br/> |8   <br/> |
|11   <br/> |9   <br/> |
|12   <br/> |10   <br/> |
|16 **비즈니스용 Skype 서버 2019** <br/> |12   <br/> |


   
그 다음에 풀을 시작할 때마다 서버의 85% (위 표에 표시 된 대로)가 시작 되어야 합니다. 이 서버 수를 시작할 수 없지만 풀 수준 쿼럼 손실에 해당 하지 않도록 충분 한 서버를 시작할 수 있으면 cmdlet을 사용 `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` 하 여 풀에서이 라우팅 그룹 수준 쿼럼 손실을 복구 하 고 작업을 진행할 수 있습니다. 이 cmdlet을 사용 하는 방법에 대 한 자세한 내용은 [Reset-reset-cspoolregistrarstate](https://docs.microsoft.com/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps)를 참조 하십시오. 
  
> [!NOTE]
> 서버 수가 짝수 인 풀에서 비즈니스용 Skype 서버는 기본 SQL 데이터베이스를 미러링 모니터로 사용 합니다. 이와 같은 풀에서는 기본 데이터베이스를 종료 하 고 미러 복사본으로 전환한 다음, 앞의 표에 따라 충분히 실행 되지 않도록 충분 한 프런트 엔드 서버를 종료 하는 경우 전체 풀이 다운 됩니다. 자세한 내용은 [데이터베이스 미러링 모니터 서버](https://go.microsoft.com/fwlink/?LinkId=393672)를 참조 하세요. 
  
#### <a name="pool-level-quorum-loss"></a>풀 수준 쿼럼 손실

프런트 엔드 풀은 모두 작동 하기 위해 풀 수준의 쿼럼 손실 일 수 없습니다. 실행 중인 서버의 수가 다음 표에 나와 있는 것 처럼 기능 수준 아래로 떨어지면 풀의 나머지 서버가 모든 비즈니스용 Skype 서버 서비스를 중지 합니다. 다음 표의 숫자는 풀의 백 엔드 서버가 실행 되 고 있다고 가정 합니다.
  
|풀에 있는 총 프런트 엔드 서버 수  <br/> |풀 작동을 위해 실행되어야 하는 서버 수  <br/> |
|:-----|:-----|
|2   <br/> |1   <br/> |
|3-4  <br/> |모두 2  <br/> |
|5-6  <br/> |모두 3  <br/> |
|7   <br/> |모든 4  <br/> |
|8-9  <br/> |처음 7 개 서버 중 하나라도  <br/> |
|10-12  <br/> |처음 9 대의 서버 5 개  <br/> |
|**비즈니스용 Skype 서버 2019** 12-16  <br/> |처음 12 개 서버 중 7 개  <br/> |
   
위의 표에서 첫 번째 서버는 풀이 처음으로 시작 된 경우 시간순으로 나열 되는 서버입니다. 이러한 서버를 확인 하기 위해 옵션과 함께 cmdlet을 사용할 수 있습니다 `Get-CsComputer` `-PoolFqdn` . 이 cmdlet은 토폴로지에 표시 되는 순서 대로 서버를 표시 하며, 목록 맨 위에 있는 서버가 첫 번째 서버입니다.
  
> [!IMPORTANT]
> [비즈니스용 Skype 서버 2019](https://docs.microsoft.com/skypeforbusiness/plan/user-model-2019) 에서 최대 프런트 엔드 서버 수가 16 개로 늘어났습니다.
> 
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>풀이 작동 하도록 확인 하기 위한 추가 단계

프런트 엔드 풀이 계속 작동 되도록 하려면 몇 가지 다른 요인을 살펴봐야 합니다.
  
- 사용자를 처음으로 풀로 이동할 때는 프런트 엔드 서버 중 세 개 이상이 실행 되 고 있어야 합니다.
    
- 이 풀과 재해 복구를 위해 다른 풀 간의 연결 관계를 설정 하는 경우 해당 관계를 설정한 후에는이 풀에 백업 풀과 데이터를 올바르게 동기화 하기 위해 일정 시간 동안 동시에 실행 되는 세 개의 프런트 엔드 서버가 있는지를 파악 해야 합니다. 풀 페어링 및 재해 복구 기능에 대 한 자세한 내용은 [비즈니스용 Skype 서버에서 고가용성 및 재해 복구 계획](high-availability-and-disaster-recovery.md)을 참조 하세요. 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>두 개의 프런트 엔드 서버가 있는 프런트 엔드 풀

두 개의 프런트 엔드 서버만 포함 된 프런트 엔드 풀을 배포 하는 것은 권장 되지 않습니다. 이 소규모 풀은 대규모 그룹과 같은 강력한 고가용성 솔루션을 제공 하지 않으며 관리 하는 경우 추가 주의를 기울여야 합니다. 또한 두 서버 풀의 백 엔드 서버가 다운 되 면 전체 풀도 곧 다운 될 수 있습니다. 비즈니스용 Skype 서버를 실행 하는 서버를 한 두 대만 배포 하려면 Standard Edition 서버로 배포 하는 것이 좋습니다.
  
두 개의 프런트 엔드 서버를 사용 하 여 풀을 배포 해야 하는 경우 다음 지침을 따릅니다.
  
- 두 프런트 엔드 서버 중 하나가 다운 되 면 가능 하면 즉시 실패 한 서버를 백업 해 보십시오. 마찬가지로, 두 서버 중 하나를 업그레이드 해야 하는 경우 업그레이드가 완료 되는 즉시 다시 온라인 상태로 전환 합니다.
    
- 어떤 이유로 두 서버를 동시에 가져오는 데 필요한 경우 풀에 대 한 가동 중지 시간이 완료 되 면 다음을 수행 합니다.
    
  - 가장 좋은 방법은 두 프런트 엔드 서버를 동시에 다시 시작 하는 것입니다. 
    
  - 두 서버를 동시에 다시 시작할 수 없는 경우에는 다운 된 순서와 순서가 거꾸로 복원 되도록 해야 합니다.
    
  - 해당 순서 대로 백업할 수 없는 경우 풀을 백업 하기 전에 다음 cmdlet을 사용 합니다.`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>프런트 엔드 풀 구성 오류 및 변경 사항

프런트 엔드 서버에 오류가 발생 하 여 며칠 이상 교체 될 가능성이 없는 경우 토폴로지에서 해당 서버를 제거 합니다. 새 프런트 엔드 서버를 다시 사용할 수 있게 되 면 토폴로지에 추가 합니다.
  
서버를 추가 하거나 제거 하는 등 프런트 엔드 풀의 구성을 변경할 때마다 다음 지침을 따라야 합니다.
  
- 새 토폴로지가 게시 된 후에 풀에서 각 프런트 엔드 서버를 다시 시작 해야 합니다. 한 번에 하나씩 다시 시작 합니다.
    
- 구성 변경 중에 전체 풀이 다운 된 경우 새 토폴로지를 게시 한 후 다음 cmdlet을 실행 합니다.`Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
    

