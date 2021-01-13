---
title: 프런트 엔드 풀 고가용성 및 관리
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: 풀 관리, 쿼럼 손실 및 프런트 엔드 서버가 2대인 풀의 특수 단계를 포함하여 비즈니스용 Skype 서버의 프런트 엔드 풀 관리에 대해 자세히 알아보십시오.
ms.openlocfilehash: 3f1924b7a8ad26b880f8674ada4f0c99a1bc4596
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802798"
---
# <a name="front-end-pool-high-availability-and-management"></a>프런트 엔드 풀 고가용성 및 관리
 
풀 관리, 쿼럼 손실 및 프런트 엔드 서버가 2대인 풀의 특수 단계를 포함하여 비즈니스용 Skype 서버의 프런트 엔드 풀 관리에 대해 자세히 알아보십시오.
  
비즈니스용 Skype 서버에서 프런트 엔드 풀의 아키텍처는 분산 시스템 모델을 사용하 고 각 사용자의 데이터는 풀에 있는 3대의 프런트 엔드 서버에 보관됩니다. 모든 Enterprise Edition 프런트 엔드 풀에는 프런트 엔드 서버가 3대 이상 포함되어 있는 것이 좋습니다.

> [!NOTE]
> 비즈니스용 Skype 서버 2019는 프런트 엔드 서버가 두 대인 Enterprise Edition 프런트 엔드 풀을 지원하지 않습니다. 이 시나리오에서는 토폴로지가 게시될 수 없습니다.
  
## <a name="planning-for-the-management-of-front-end-pools"></a>프런트 엔드 풀 관리 계획

 비즈니스용 Skype 서버는 Windows Fabric을 기반으로 하는 분산 시스템 모델을 사용 합니다. 이 모델에서는 각 사용자 및 회의에 대한 중요한 데이터가 프런트 엔드 풀의 3개의 프런트 엔드 서버에 저장됩니다. 이러한 세 서버는 특정 데이터 집합을 저장하는 데 사용할 수 있는 서버를replicas라고 합니다.
  
프런트 엔드 풀에 대한 분산 모델을 사용할 경우 풀이 작동하려면 특정 수의 풀 서버가 실행되고 있어야 합니다. 풀에는 두 가지 손실 모드가 있습니다.
  
- 특정 라우팅 그룹에 대한 복제본 서버가 부족하여 그룹 수준 쿼럼 손실이 발생했습니다. 라우팅 그룹은 풀에 있는 사용자 집합입니다. 각 라우팅 그룹에는 풀에 주 복제본 1개와 보조 복제본 2개 등 3개의 복제본이 있습니다.
    
- 풀에서 시드 서버가 충분하지 않은 경우 풀 수준 쿼럼 손실이 발생했습니다. 
    
### <a name="routing-group-level-quorum-loss"></a>라우팅 그룹 수준 쿼럼 손실

새 프런트 엔드 풀을 처음 시작할 때 다음 표와 같이 서버의 85%가 실행 중입니다. 실행 중인 서버 수가 적을 경우 서비스가 시작 상태가 되지 않을 수 있으며 풀이 시작되지 않을 수 있습니다.
  
|풀의 총 서버 수  <br/> |풀을 처음 시작하려면 실행해야 하는 서버 수  <br/> |
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
|16 **For Skype for Business Server 2019** <br/> |12   <br/> |


   
이후에 풀이 시작될 때마다 서버의 85%가 시작되어야 합니다(앞의 표에 나와 있는 경우). 이 수의 서버를 시작할 수 없는 경우(하지만 풀 수준 쿼럼 손실이 되지 않을 수 있도록 충분한 서버를 시작할 수 있는 경우) 이 cmdlet을 사용하여 풀이 이 라우팅 그룹 수준 쿼럼 손실에서 복구하도록 설정하고 진행을 진행할 수  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` 있습니다. 이 cmdlet을 사용하는 방법에 대한 자세한 내용은 [Reset-CsPoolRegistrarState를 참조하십시오.](https://docs.microsoft.com/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps) 
  
> [!NOTE]
> 서버 수가 1개인 풀에서 비즈니스용 Skype 서버는 기본 서버 SQL 미러링크로 사용합니다. 이와 같은 풀에서 기본 데이터베이스를 종료하고 미러 복사본으로 전환한 다음 앞의 표에 따라 충분히 실행되지 않는 충분한 프런트 엔드 서버를 종료하면 전체 풀이 다운됩니다. 자세한 내용은 데이터베이스 [미러링 지원(Database Mirroring Witness)을 참조하세요.](https://go.microsoft.com/fwlink/?LinkId=393672) 
  
#### <a name="pool-level-quorum-loss"></a>풀 수준 쿼럼 손실

프런트 엔드 풀이 작동하지만 풀 수준 쿼럼 손실에는 사용할 수 없습니다. 실행 중인 서버 수가 다음 표에 나와 있는 기능 수준 미만이면 풀의 나머지 서버가 모든 비즈니스용 Skype 서버 서비스를 중지합니다. 다음 표의 숫자는 풀의 백 엔드 서버가 실행되고 있는 것으로 가정합니다.
  
|풀에 있는 총 프런트 엔드 서버 수  <br/> |풀 작동을 위해 실행되어야 하는 서버 수  <br/> |
|:-----|:-----|
|2   <br/> |1   <br/> |
|3-4  <br/> |모든 2  <br/> |
|5-6  <br/> |모든 3  <br/> |
|7   <br/> |모든 4  <br/> |
|8-9  <br/> |처음 7개 서버 중 4개  <br/> |
|10-12  <br/> |처음 9개 서버 중 5개  <br/> |
|비즈니스용 Skype 서버  **2019의 경우 12-16**  <br/> |처음 12개 서버 중 7개  <br/> |
   
위의 표에서 "첫 번째 서버"는 풀이 처음 시작된 시간부터 시작된 서버입니다. 이러한 서버를 확인하기 위해  `Get-CsComputer` 이 cmdlet을 옵션과 함께 사용할 수 `-PoolFqdn` 있습니다. 이 cmdlet은 토폴로지에서 서버가 나타나는 순서대로 서버를 표시하고 목록 맨 위에 있는 서버가 첫 번째 서버입니다.
  
> [!IMPORTANT]
> 2019년 비즈니스용 Skype에서 최대 프런트 엔드 서버 수가 [16개로 늘어났습니다.](https://docs.microsoft.com/skypeforbusiness/plan/user-model-2019)
> 
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>풀이 작동하도록 하는 추가 단계

프런트 엔드 풀이 계속 작동하도록 보장하기 위해 몇 가지 다른 요인을 감시해야 합니다.
  
- 사용자를 풀로 처음 이동할 때 적어도 세 개의 프런트 엔드 서버가 실행되고 있는지 확인해야 합니다.
    
- 재해 복구를 위해 이 풀과 다른 풀 간에 페어링 관계를 설정하는 경우 해당 관계를 설정한 후 백업 풀과 데이터를 올바르게 동기화하려면 이 풀에 동시에 실행되는 3개의 프런트 엔드 서버가 있어야 합니다. 풀 페어링 및 재해 복구 기능에 대한 자세한 내용은 비즈니스용 Skype 서버의 고가용성 및 재해 복구 [계획을 참조하세요.](high-availability-and-disaster-recovery.md) 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>프런트 엔드 서버가 2대인 프런트 엔드 풀

프런트 엔드 서버가 2대만 포함된 프런트 엔드 풀은 배포하지 않는 것이 좋습니다. 이 소규모 풀은 더 큰 풀과 같은 강력한 고가용성 솔루션을 제공하지는 못하며 관리에 특히 주의해야 합니다. 또한 두 서버 풀의 백 엔드 서버가 다운된 경우 전체 풀 자체도 곧 다운될 수 있습니다. 비즈니스용 Skype 서버를 실행하는 한 두 대의 서버만 배포하려는 경우 Standard Edition 서버로 배포하는 것이 좋습니다.
  
프런트 엔드 서버가 두 대인 풀을 배포해야 하는 경우 다음 지침을 따릅니다.
  
- 두 프런트 엔드 서버 중 한 대가 다운되는 경우 가능한 한 빨리 실패한 서버를 백업해야 합니다. 마찬가지로, 두 서버 중 하나를 업그레이드해야 하는 경우 업그레이드가 완료되는 즉시 온라인으로 되돌아가야 합니다.
    
- 어떤 이유로 인해 두 서버를 동시에 다운해야 하는 경우 풀의 종료 시간이 완료되면 다음을 실행합니다.
    
  - 최상의 방법은 두 프런트 엔드 서버를 동시에 다시 시작하는 것입니다. 
    
  - 두 서버를 동시에 다시 시작할 수 없는 경우 서버가 다운된 순서의 역순으로 백업해야 합니다.
    
  - 해당 순서대로 백업할 수 없는 경우 풀을 백업하기 전에 다음 cmdlet을 사용하십시오.  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>프런트 엔드 풀 구성 오류 및 변경 사항

프런트 엔드 서버가 실패하여 며칠 이상 교체되지 않을 경우 토폴로지에서 서버를 제거합니다. 토폴로지에서 새 프런트 엔드 서버를 다시 사용할 수 있는 경우 추가합니다.
  
서버 추가 또는 제거와 같이 프런트 엔드 풀에 대한 구성을 변경할 때마다 다음 지침을 따라야 합니다.
  
- 새 토폴로지가 게시된 후 풀의 각 프런트 엔드 서버를 다시 시작해야 합니다. 한 번씩 다시 시작합니다.
    
- 구성 변경 중에 전체 풀이 다운된 경우 새 토폴로지가 게시된 후 다음 cmdlet을 실행합니다.  `Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
    

