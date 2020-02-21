---
title: Office Communications Server 2007 R2에서 Lync Server 2013으로 마이그레이션
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Office Communications Server 2007 R2 to Lync Server 2013
ms:assetid: f3fa4f5f-e9a2-4fb7-a12d-20f04173e697
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205375(v=OCS.15)
ms:contentKeyID: 48185802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 344f15589e113a54b539d351ed8d4745e1fd3a5b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209844"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-from-office-communications-server-2007-r2-to-lync-server-2013"></a>Office Communications Server 2007 R2에서 Lync Server 2013으로 마이그레이션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-19_

이 섹션의 항목에서는 Office Communications Server 2007 R2에서 Lync Server 2013로 마이그레이션하는 프로세스를 안내 합니다.

<div>


> [!IMPORTANT]  
> 이 문서에서는 각 마이그레이션 단계를 수행하는 데 일반적으로 필요한 단계에 대해 설명합니다. 모든 가능한 레거시 배포 토폴로지 또는 모든 가능한 마이그레이션 시나리오는 여기에서 다루지 않습니다. 따라서 배포에 따라 설명된 모든 단계를 수행할 필요가 없거나 추가 단계를 수행해야 할 수도 있습니다. 이 문서에서는 또한 확인 단계에 대한 예를 제공합니다. 이러한 확인 단계는 마이그레이션을 진행하면서 각 단계가 성공적으로 완료되었는지 완료되었는지 확인하기 위해 검토할 사항에 대한 이해를 돕기 위해 제공됩니다. 이러한 확인 단계를 사용자의 마이그레이션 프로세스에 맞게 조정하십시오.



</div>

이 설명서에서는 기존 배포 업그레이드와 관련된 정보를 제공하며 기존 토폴로지를 변경하는 방법이나 새 기능 구현은 다루지 않습니다. 단, 자세한 절차가 다른 문서에 설명되어 있는 경우 해당 문서 또는 문서 섹션으로 사용자를 안내합니다.

이 문서에서는 다음 목록에 지정된 용어를 정의합니다.

  - *마이그레이션하기*  
    프로덕션 배포를 이전 버전의 Office Communications Server 2007 R2에서 Lync Server 2013로 이동 하는 경우

<!-- end list -->

  - *업그레이드*  
    서버 또는 클라이언트 컴퓨터에 새 버전의 소프트웨어를 설치합니다.

<!-- end list -->

  - *동시*  
    마이그레이션 중에 발생 하는 일시적인 환경으로, 일부 기능이 Lync Server 2013로 마이그레이션 되었지만 기타 기능은 이전 버전의 Office Communications Server 2007 r 2에 남아 있습니다.

<!-- end list -->

  - *가능*  
    동시 사용 기간 중 배포를 성공적으로 운영할 수 있는 기능입니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [마이그레이션을 시작 하기 전에](before-you-begin-the-migration_1.md)

  - [Migration phases](migration-phases_1.md)

  - [1 단계: Office Communications Server 2007 r 2에서 마이그레이션 계획](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [2 단계: 마이그레이션 준비](phase-2-prepare-for-migration_1.md)

  - [3 단계: Lync Server 2013 파일럿 풀 배포](phase-3-deploy-lync-server-2013-pilot-pool_1.md)

  - [4 단계: 토폴로지 병합](phase-4-merge-topologies.md)

  - [단계 5: 파일럿 풀 구성](phase-5-configure-the-pilot-pool.md)

  - [단계 6: 사용자를 파일럿 풀로 이동](phase-6-move-users-to-the-pilot-pool.md)

  - [단계 7: 파일럿 풀에 Lync Server 2013에 지 서버 추가](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [8 단계: 파일럿 배포에서 프로덕션으로 이동](phase-8-move-from-pilot-deployment-into-production.md)

  - [단계 9: 마이그레이션 후 작업 완료](phase-9-complete-post-migration-tasks.md)

  - [단계 10: 레거시 사이트 해제](phase-10-decommission-legacy-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

