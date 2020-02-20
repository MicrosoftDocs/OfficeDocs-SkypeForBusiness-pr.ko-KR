---
title: Lync Server 2010에서 Lync Server 2013로 마이그레이션
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Lync Server 2010 to Lync Server 2013
ms:assetid: ef99d4a9-a666-4a92-9994-4d7930f70d55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205369(v=OCS.15)
ms:contentKeyID: 48185779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0688fc80bb763a4b5aa3e7ff10970cef96465b84
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a>Lync Server 2010에서 Lync Server 2013로 마이그레이션

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-17_

이 섹션의 항목에서는 Lync Server 2010에서 Lync Server 2013로 마이그레이션하는 프로세스를 안내 합니다.

<div>


> [!IMPORTANT]  
> 이 문서에서는 각 마이그레이션 단계를 수행하는 데 일반적으로 필요한 단계에 대해 설명합니다. 모든 가능한 레거시 배포 토폴로지 또는 모든 가능한 마이그레이션 시나리오는 여기에서 다루지 않습니다. 따라서 배포에 따라 설명된 모든 단계를 수행할 필요가 없거나 추가 단계를 수행해야 할 수도 있습니다. 이 문서에서는 또한 확인 단계에 대한 예를 제공합니다. 이러한 확인 단계는 마이그레이션을 진행하면서 각 단계가 성공적으로 완료되었는지 완료되었는지 확인하기 위해 검토할 사항에 대한 이해를 돕기 위해 제공됩니다. 이러한 확인 단계를 사용자의 마이그레이션 프로세스에 맞게 조정하십시오.



</div>

이 설명서에서는 기존 배포 업그레이드와 관련된 정보를 제공하며 기존 토폴로지를 변경하는 방법이나 새 기능 구현은 다루지 않습니다. 단, 자세한 절차가 다른 문서에 설명되어 있는 경우 해당 문서 또는 문서 섹션으로 사용자를 안내합니다.

이 문서에서는 다음 목록에 지정된 용어를 정의합니다.

  - *마이그레이션하기*  
    프로덕션 배포를 이전 버전의 Lync Server 2010에서 Lync Server 2013로 이동 하는 경우

<!-- end list -->

  - *업그레이드*  
    서버 또는 클라이언트 컴퓨터에 새 버전의 소프트웨어를 설치합니다.

<!-- end list -->

  - *동시*  
    마이그레이션 중에 발생 하는 일시적인 환경으로, 일부 기능이 Lync Server 2013로 마이그레이션 되었지만 다른 기능은 이전 버전의 Lync Server 2010에 남아 있습니다.

<!-- end list -->

  - *가능*  
    동시 사용 기간 중 배포를 성공적으로 운영할 수 있는 기능입니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [마이그레이션을 시작 하기 전에](before-you-begin-the-migration.md)

  - [1 단계: Lync Server 2010에서 마이그레이션 계획](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [2 단계: 마이그레이션 준비](phase-2-prepare-for-migration.md)

  - [3 단계: Lync Server 2013 파일럿 풀 배포](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [4 단계: 테스트 사용자를 파일럿 풀로 이동](phase-4-move-test-users-to-the-pilot-pool.md)

  - [단계 5: Lync Server 2013에 지 서버를 파일럿 풀에 추가](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [6 단계: 파일럿 배포에서 프로덕션으로 이동](phase-6-move-from-pilot-deployment-into-production.md)

  - [단계 7: 마이그레이션 후 작업 완료](phase-7-complete-post-migration-tasks.md)

  - [8 단계: 레거시 풀 해제](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

