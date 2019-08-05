---
title: 비즈니스용 Skype 서버 2019 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 이 섹션의 항목에서는 비즈니스용 Skype Server 2019로 마이그레이션하는 과정을 안내 합니다.
ms.openlocfilehash: bd1513e5ca2a33449f982394e4abc15b9616393b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196951"
---
# <a name="migration-to-skype-for-business-server-2019"></a>비즈니스용 Skype 서버 2019 마이그레이션

이 섹션의 항목에서는 비즈니스용 Skype Server 2019로 마이그레이션하는 과정을 안내 합니다. 이 문서에서는 Lync Server 2013 또는 비즈니스용 Skype Server 2015을 비즈니스용 Skype 서버 2019로 마이그레이션하는 방법에 대해 설명 합니다.

> [!IMPORTANT]
> 모든 콘텐츠를 통해 *레거시* Lync server 2013 또는 비즈니스용 skype server 2015을 비즈니스용 skype server 2019로 마이그레이션하는 것을 참조 하는 것이 좋습니다.
  
> [!IMPORTANT]
> 이 가이드에서는 각 마이그레이션 단계를 수행 하는 데 일반적으로 필요한 단계에 대해 설명 합니다. 모든 가능 레거시 배포 토폴로지 또는 모든 가능 마이그레이션 시나리오를 다루지 않습니다. 따라서 설명 된 모든 단계를 수행 하거나 배포에 따라 추가 단계를 수행 해야 할 수 있습니다. 이 가이드에서는 확인 단계의 예제도 제공 합니다. 이러한 확인 단계는 마이그레이션을 진행 하면서 각 단계가 성공적으로 완료 되도록 하기 위해 찾아야 할 사항을 파악 하는 데 도움이 되도록 제공 됩니다. 이러한 확인 단계를 특정 마이그레이션 프로세스에 맞게 조정할 수 있습니다. 
  
이 가이드에서는 기존 배포를 업그레이드 하는 방법에 대 한 정보를 제공 합니다. 기존 토폴로지를 변경 하는 방법은 설명 하지 않습니다. 이 가이드에서는 새로운 기능을 구현 하는 방법을 다루지 않습니다. 세부 절차를 다른 곳에서 문서화 한 경우이 가이드는 문서 또는 문서 섹션으로 안내 합니다. 
  
이 문서에서는 다음 목록에 명시 된 약관을 정의 합니다.
  
**마이그레이션:** Lync Server 2013 또는 비즈니스용 Skype Server 2015에서 비즈니스용 skype server 2019으로 프로덕션 배포를 이동 합니다.
    
**공존 방법:** 일부 기능을 비즈니스용 Skype 서버 2019으로 마이그레이션 하 고 다른 기능을 이전 버전에 그대로 유지할 때 마이그레이션하는 동안 존재 하는 임시 환경입니다.
    
**상호 운용성:** 공존 기간 동안 성공적으로 작동 하는 배포 능력.

**레거시:** 마이그레이션할 시스템 (Lync Server 2013 또는 비즈니스용 Skype Server 2015)입니다.
    
## <a name="in-this-section"></a>이 섹션의

- [마이그레이션을 시작 하기 전에](before-you-begin-the-migration.md)
    
- [1 단계: 마이그레이션 계획](phase-1-plan-your-migration.md)
    
- [2 단계: 마이그레이션 준비](phase-2-prepare-for-migration.md)
    
- [3 단계: 파일럿 풀 배포](phase-3-deploy-pilot-pool.md)
    
- [4 단계: 시험 운용 풀로 테스트 사용자 이동](phase-4-move-test-users-to-the-pilot-pool.md)
    
- [5 단계: 파일럿 풀에 Edge 서버 추가](phase-5-add-edge-server-to-pilot-pool.md)
    
- [6 단계: 파일럿 배포에서 프로덕션으로 이동](phase-6-move-from-pilot-deployment-into-production.md)
    
- [7 단계: 마이그레이션 후 작업 완료](phase-7-complete-post-migration-tasks.md)
    
- [8 단계: 레거시 풀 서비스 해제](phase-8-decommission-legacy-pools.md)
    

