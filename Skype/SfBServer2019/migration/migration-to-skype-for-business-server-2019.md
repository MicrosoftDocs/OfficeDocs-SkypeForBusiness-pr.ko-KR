---
title: 비즈니스용 Skype 서버 2019로 마이그레이션
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 이 섹션의 항목에서는 비즈니스용 Skype 서버 2019로 마이그레이션하는 프로세스를 안내합니다.
ms.openlocfilehash: 860fce550de33ed726bbbe723c8c7677ff09fc1c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752620"
---
# <a name="migration-to-skype-for-business-server-2019"></a>비즈니스용 Skype 서버 2019로 마이그레이션

이 섹션의 항목에서는 비즈니스용 Skype 서버 2019로 마이그레이션하는 프로세스를 안내합니다. 이 문서에서는 Lync Server 2013 또는 비즈니스용 Skype 서버 2015를 비즈니스용 Skype 서버 2019로 마이그레이션하는 데 대해 다기능으로 제공합니다.

> [!IMPORTANT]
> 콘텐츠 전체에서 레거시  용어를 사용하여 비즈니스용 Skype 서버 2019로 마이그레이션하는 레거시 Lync Server 2013 또는 비즈니스용 Skype 서버 2015를 참조합니다.
  
> [!IMPORTANT]
> 이 가이드에서는 마이그레이션의 각 단계를 수행하기 위해 일반적으로 필요한 단계를 설명 합니다. 모든 가능한 레거시 배포 토폴로지 또는 모든 가능한 마이그레이션 시나리오에 대해서는 여기에서 다루지 않습니다. 따라서 배포에 따라 설명된 모든 단계를 수행할 필요가 없거나 추가 단계를 수행해야 할 수도 있습니다. 이 가이드에서는 확인 단계의 예도 제공합니다. 이러한 확인 단계는 마이그레이션을 진행하면서 각 단계가 성공적으로 완료되었는지 보장하기 위해 조사해야 하는 항목을 확인할 수 있도록 돕기 위해 제공됩니다. 이러한 확인 단계를 사용자의 마이그레이션 프로세스에 맞게 조정하십시오. 
  
이 설명서에서는 기존 배포를 업그레이드하는 것과 관련된 정보를 제공합니다. 기존 토폴로지를 변경하는 방법에 대해서는 다루지 않습니다. 또한 새 기능 구현에 대해서도 다루지 않습니다. 자세한 절차가 다른 곳에서 문서화되어 있는 경우 이 가이드는 문서 또는 문서 섹션으로 안내합니다. 
  
이 문서에서는 다음 목록에 지정된 용어를 정의합니다.
  
**마이그레이션:** 프로덕션 배포를 Lync Server 2013 또는 비즈니스용 Skype 서버 2015에서 비즈니스용 Skype 서버 2019로 이동
    
**동시성:** 일부 기능이 비즈니스용 Skype 서버 2019로 마이그레이션되고 다른 기능은 이전 버전에 남아 있을 때 마이그레이션 중에 존재하는 임시 환경입니다.
    
**상호 연동성:** 동시 사용 기간 동안 배포가 성공적으로 작동할 수 있는 능력

**레거시:** 마이그레이션하지 않도록 하는 시스템(Lync Server 2013 또는 비즈니스용 Skype 서버 2015)입니다.
    
## <a name="in-this-section"></a>이 섹션의 내용

- [마이그레이션을 시작하기 전에](before-you-begin-the-migration.md)
    
- [1단계: 마이그레이션 계획](phase-1-plan-your-migration.md)
    
- [2단계: 마이그레이션 준비](phase-2-prepare-for-migration.md)
    
- [3단계: 파일럿 풀 배포](phase-3-deploy-pilot-pool.md)
    
- [4단계: 테스트 사용자를 파일럿 풀로 이동](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [5단계: 파일럿 풀에 Edge 서버 추가](phase-5-add-edge-server-to-pilot-pool.md)
    
- [6단계: 파일럿 배포에서 프로덕션으로 이동](phase-6-move-from-pilot-deployment-into-production.md)
    
- [7단계: 마이그레이션 후 작업 완료](phase-7-complete-post-migration-tasks.md)
    
- [8단계: 레거시 풀 해제](phase-8-decommission-legacy-pools.md)
    

