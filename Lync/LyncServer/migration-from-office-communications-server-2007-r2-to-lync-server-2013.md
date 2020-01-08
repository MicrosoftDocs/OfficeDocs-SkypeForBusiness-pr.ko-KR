---
title: Office Communications Server 2007 R2에서 Lync Server 2013으로 마이그레이션
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migration from Office Communications Server 2007 R2 to Lync Server 2013
ms:assetid: f3fa4f5f-e9a2-4fb7-a12d-20f04173e697
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205375(v=OCS.15)
ms:contentKeyID: 48185802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43064d265bc08cab3721d0f19fd7f89184871f0e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979365"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-from-office-communications-server-2007-r2-to-lync-server-2013"></a>Office Communications Server 2007 R2에서 Lync Server 2013으로 마이그레이션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-19_

이 섹션의 항목에서는 Office Communications Server 2007 R2에서 Lync Server 2013로 마이그레이션하는 과정을 안내 합니다.

<div>


> [!IMPORTANT]  
> 이 문서에서는 각 마이그레이션 단계를 수행 하는 데 일반적으로 필요한 단계에 대해 설명 합니다. 모든 가능 레거시 배포 토폴로지 또는 모든 가능 마이그레이션 시나리오를 다루지 않습니다. 따라서 설명 된 모든 단계를 수행 하거나 배포에 따라 추가 단계를 수행 해야 할 수 있습니다. 이 문서에서는 확인 단계의 예제도 제공 합니다. 이러한 확인 단계는 마이그레이션을 진행 하면서 각 단계가 성공적으로 완료 되도록 하기 위해 찾아야 할 사항을 파악 하는 데 도움이 되도록 제공 됩니다. 이러한 확인 단계를 특정 마이그레이션 프로세스에 맞게 조정할 수 있습니다.



</div>

이 가이드에서는 기존 배포를 업그레이드 하는 방법에 대 한 정보를 제공 합니다. 기존 토폴로지를 변경 하는 방법은 설명 하지 않습니다. 이 가이드에서는 새로운 기능을 구현 하는 방법을 다루지 않습니다. 세부 절차를 다른 곳에서 문서화 하면이 가이드에서 해당 문서 또는 문서 섹션으로 안내 합니다.

이 문서는 다음 목록에 명시 된 약관을 정의 합니다.

  - *마이그레이션하기*  
    이전 버전의 Office Communications Server 2007 R2에서 Lync Server 2013로 프로덕션 배포를 이동 합니다.

<!-- end list -->

  - *업그레이드*  
    서버나 클라이언트 컴퓨터에 최신 버전의 소프트웨어를 설치 합니다.

<!-- end list -->

  - *공존 성*  
    일부 기능이 Lync Server 2013 및 기타 기능으로 마이그레이션될 때 마이그레이션 중에 존재 하는 임시 환경은 여전히 이전 버전의 Office Communications Server 2007 R2에 남아 있습니다.

<!-- end list -->

  - *운용할*  
    공존 기간 동안 성공적으로 작동 하는 배포 능력.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [마이그레이션을 시작하기 전에](before-you-begin-the-migration_1.md)

  - [마이그레이션 단계](migration-phases_1.md)

  - [1 단계: Office Communications Server 2007 R2에서 마이그레이션 계획](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [2단계: 마이그레이션 준비](phase-2-prepare-for-migration_1.md)

  - [3 단계: Lync Server 2013 파일럿 풀 배포](phase-3-deploy-lync-server-2013-pilot-pool_1.md)

  - [4 단계: 병합 토폴로지](phase-4-merge-topologies.md)

  - [5 단계: 파일럿 풀 구성](phase-5-configure-the-pilot-pool.md)

  - [6 단계: 파일럿 풀로 사용자 이동](phase-6-move-users-to-the-pilot-pool.md)

  - [7 단계: 파일럿 풀에 Lync Server 2013 Edge 서버 추가](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [8 단계: 파일럿 배포에서 프로덕션으로 이동](phase-8-move-from-pilot-deployment-into-production.md)

  - [9 단계: 마이그레이션 후 작업 완료](phase-9-complete-post-migration-tasks.md)

  - [10 단계: 레거시 사이트 서비스 해제](phase-10-decommission-legacy-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

