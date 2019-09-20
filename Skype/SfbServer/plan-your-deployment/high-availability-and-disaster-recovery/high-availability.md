---
title: 프런트 엔드 풀 고가용성 및 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: 2 개의 프런트 엔드 서버만 사용 하는 풀에 대 한 풀 관리, 쿼럼 손실, 특별 단계를 포함 하 여 비즈니스용 Skype 서버의 프론트 엔드 풀 관리에 대해 알아봅니다.
ms.openlocfilehash: e42e192d224d509356203c059751624fc706707b
ms.sourcegitcommit: a6e44256c024fc3953cfd6a511ee024c4c7b8408
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047095"
---
# <a name="front-end-pool-high-availability-and-management"></a>프런트 엔드 풀 고가용성 및 관리
 
2 개의 프런트 엔드 서버만 사용 하는 풀에 대 한 풀 관리, 쿼럼 손실, 특별 단계를 포함 하 여 비즈니스용 Skype 서버의 프론트 엔드 풀 관리에 대해 알아봅니다.
  
비즈니스용 Skype 서버에서 프런트 엔드 풀의 아키텍처는 분산 시스템 모델을 사용 하 고 각 사용자의 데이터는 풀의 프런트 엔드 서버 3 대까지 유지 됩니다. 모든 Enterprise Edition 프런트 엔드 풀에는 프런트 엔드 서버가 세 대 이상 포함 되는 것이 좋습니다. 
  
## <a name="planning-for-the-management-of-front-end-pools"></a>프런트 엔드 풀 관리 계획

 비즈니스용 Skype Server는 Windows Fabric 기반의 분산 시스템 모델을 사용 합니다. 이 모델에서 각 사용자 및 회의에 대 한 중요 한 데이터는 프런트 엔드 풀에 있는 세 개의 프런트 엔드 서버에 저장 됩니다. 특정 데이터 집합을 저장 하는 세 개의 서버는 calledreplicas.
  
프런트 엔드 풀에 대 한 분산 모델을 사용 하는 경우 풀이 작동 하려면 풀 서버의 특정 번호가 실행 중 이어야 합니다. 풀에는 두 가지 손실 모드가 있습니다.
  
- 라우팅 그룹 수준 쿼럼 손실, 특정 라우팅 그룹에 대 한 복제본 서버가 부족 하 여 발생 합니다. 라우팅 그룹은 풀에 속한 사용자 집합입니다. 각 라우팅 그룹에는 하나의 주 복제본과 두 개의 보조 복제본 이라는 세 가지 풀의 복제본이 있습니다.
    
- 풀에 시드 서버가 충분히 실행 되 고 있지 않은 경우 발생 하는 풀 수준 쿼럼 손실. 
    
### <a name="routing-group-level-quorum-loss"></a>라우팅 그룹 수준 쿼럼 손실

새 프런트 엔드 풀을 처음 시작 하는 경우에는 다음 표에 표시 된 대로 서버의 85%가 작동 하 고 실행 되 고 있어야 합니다. 실행 중인 서버 수가 적은 경우 서비스는 시작 상태에 멈춰 있을 수 있으며 풀이 시작 되지 않을 수 있습니다.
  
|풀의 총 서버 수  <br/> |풀이 처음 시작 될 때 실행 되어야 하는 서버 수  <br/> |
|:-----|:-----|
|2  <br/> |raid-1  <br/> |
|3-4  <br/> |3-4  <br/> |
|4(tcp/ipv4)  <br/> |3-4  <br/> |
|5mb  <br/> |4(tcp/ipv4)  <br/> |
|26  <br/> |5mb  <br/> |
|7  <br/> |5mb  <br/> |
|20cm(8  <br/> |26  <br/> |
|되었는지  <br/> |7  <br/> |
|1천만  <br/> |20cm(8  <br/> |
|mb  <br/> |되었는지  <br/> |
|까지  <br/> |1천만  <br/> |
   
이후 풀이 시작 될 때마다 서버의 85%가 시작 되어야 합니다 (앞의 표에 표시 된 대로). 이 서버 수를 시작할 수 없는 경우 (풀 수준의 쿼럼 손실에 해당 되지 않도록 충분 한 서버를 시작할 수 있음) `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` cmdlet을 사용 하 여이 라우팅 그룹 수준 쿼럼 손실에서 복구 하 고 진행률을 설정할 수 있습니다. 이 cmdlet을 사용 하는 방법에 대 한 자세한 내용은 [-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps)을 참조 하세요. 
  
> [!NOTE]
> 서버 수가 짝수 인 풀에서 비즈니스용 Skype Server는 기본 SQL 데이터베이스를 미러링 모니터로 사용 합니다. 이와 같은 풀에서 기본 데이터베이스를 종료 하 고 미러 복사본으로 전환 하 여 앞의 표에 따라 실행 되지 않도록 충분 한 프런트 엔드 서버를 종료 하면 전체 풀이 중단 됩니다. 자세한 내용은 [데이터베이스 미러링 감시](https://go.microsoft.com/fwlink/?LinkId=393672)를 참조 하세요. 
  
#### <a name="pool-level-quorum-loss"></a>풀 수준 쿼럼 손실

프런트 엔드 풀은 전혀 작동 하기 위해 풀 수준의 쿼럼 손실 일 수 없습니다. 실행 중인 서버 수가 다음 표에 나와 있는 것 처럼 기능 수준 아래로 떨어지면 풀의 나머지 서버가 모든 비즈니스용 Skype 서버 서비스를 중지 합니다. 다음 표의 숫자는 풀의 백 엔드 서버가 실행 되 고 있는 것으로 가정 합니다.
  
|풀의 총 프런트 엔드 서버 수  <br/> |풀을 작동 하기 위해 실행 해야 하는 서버 수  <br/> |
|:-----|:-----|
|2  <br/> |raid-1  <br/> |
|3-4  <br/> |모든 2  <br/> |
|5-6  <br/> |모든 3  <br/> |
|7  <br/> |모든 4  <br/> |
|8-9  <br/> |처음 7 대의 서버 중 4 대  <br/> |
|10-12  <br/> |처음 9 대의 서버 5 대  <br/> |
   
앞의 표에서 "첫 번째 서버"는 풀이 처음으로 시작 된 시점에 시간순으로 나열 된 서버입니다. 이러한 서버를 확인 하려면 `Get-CsComputer` `-PoolFqdn` 옵션에 cmdlet을 사용할 수 있습니다. 이 cmdlet은 토폴로지에 표시 되는 순서 대로 서버를 표시 하 고 목록의 맨 위에는 첫 번째 서버가 됩니다.
  
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>풀이 작동 하도록 하는 추가 단계

프런트 엔드 풀이 작동 하는 것을 방지 하기 위해 몇 가지 다른 요인에 유의 해야 합니다.
  
- 사용자를 처음으로 풀로 이동 하는 경우 프런트 엔드 서버가 세 개 이상 실행 되 고 있는지 확인 합니다.
    
- 이 풀과 재해 복구용에 대 한 다른 풀 간의 페어링 관계를 설정 하는 경우 해당 관계를 설정한 후에는이 풀에 동시에 실행 되는 세 개의 프런트 엔드 서버가 있어야 올바르게 동기화 할 수 있습니다. 백업 풀을 사용 하 여 데이터 풀 페어링 및 재해 복구 기능에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 고가용성 및 재해 복구 계획](high-availability-and-disaster-recovery.md)을 참조 하세요. 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>두 개의 프런트 엔드 서버가 있는 프런트 엔드 풀

프런트 엔드 서버를 두 대만 포함 하는 프런트 엔드 풀은 배포 하지 않는 것이 좋습니다. 이 작은 풀은 대규모 그룹과 같은 강력한 고가용성 솔루션을 제공 하지 않으며, 관리에 추가 주의가 필요 합니다. 또한, 두 서버 풀의 백 엔드 서버가 종료 된 경우에도 전체 풀 자체는 곧 다운 될 가능성이 높습니다. 비즈니스용 Skype 서버를 실행 하는 서버를 하나 또는 두 개 배포 하려는 경우 표준 버전 서버로 배포 하는 것이 좋습니다.
  
프런트 엔드 서버 두 대를 사용 하 여 풀을 배포 해야 하는 경우 다음 지침을 따릅니다.
  
- 두 프런트 엔드 서버 중 하나가 중단 되 면 가능한 한 빨리 실패 한 서버를 다시 온라인 상태로 만들어야 합니다. 마찬가지로, 두 서버 중 하나를 업그레이드 해야 하는 경우 업그레이드가 완료 되는 즉시 다시 온라인 상태로 전환 합니다.
    
- 어떤 이유로 두 서버를 동시에 종료 해야 하는 경우 풀의 가동 중지 시간이 완료 되 면 다음을 수행 합니다.
    
  - 가장 좋은 방법은 프런트 엔드 서버를 동시에 다시 시작 하는 것입니다. 
    
  - 두 서버를 동시에 다시 시작할 수 없는 경우에는 그 순서의 역순으로 백업 해야 합니다.
    
  - 이 순서 대로 백업할 수 없는 경우 풀을 다시 가져오기 전에 다음 cmdlet을 사용 합니다.`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>프런트 엔드 풀 구성 오류 및 변경

프런트 엔드 서버에 오류가 발생 하 여 며칠 이상 교체할 수 없는 경우 토폴로지에서 서버를 제거 합니다. 다시 사용할 수 있게 되 면 토폴로지에 새 프런트 엔드 서버를 추가 합니다.
  
서버를 추가 하거나 제거 하는 등 프런트 엔드 풀의 구성을 변경할 때마다 다음 지침을 따라야 합니다.
  
- 새 토폴로지가 게시 된 후에 풀에서 각 프런트 엔드 서버를 다시 시작 해야 합니다. 한 번에 하나씩 다시 시작 합니다.
    
- 구성 변경 중 전체 풀이 중단 되 면 새 토폴로지가 게시 된 후 다음 cmdlet을 실행 합니다.`Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
    

