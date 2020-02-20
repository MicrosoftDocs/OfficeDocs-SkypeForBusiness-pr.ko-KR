---
title: 마이그레이션 프로세스
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: b2bd9c76-2f4b-4d14-a5c4-157bbff75de0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205181(v=OCS.15)
ms:contentKeyID: 48185157
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1cc0620b2de14c56a6886a70cd7b977046828786
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148727"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-process"></a>마이그레이션 프로세스

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-24_

Lync Server 2013에 대 한 권장 되 고 지원 되는 마이그레이션 절차는 단계별 마이그레이션 절차입니다. 이 항목에서는 병렬 마이그레이션을 사용해야 하는 이유와 동시 사용 관련 정보에 대해 설명합니다.

<div>

## <a name="side-by-side-migration"></a>병렬 마이그레이션

거의 모든 마이그레이션에서는 병렬 마이그레이션 경로를 사용해야 합니다. 병렬 마이그레이션에서는 Office Communications Server 2007 r 2를 실행 하는 해당 서버와 함께 Lync Server 2013을 사용 하 여 새 서버를 배포한 다음 작업을 새 서버로 전송 합니다. Office Communications Server 2007 R2로 롤백하는 데 필요한 경우 작업을 원래 서버로 다시 이동 하기만 하면 됩니다. 이 경우 업그레이드된 클라이언트로 예약된 모든 새 모임이 작동하지 않으며 클라이언트도 다운그레이드해야 합니다.

</div>

<div>

## <a name="coexistence-testing"></a>동시 사용 테스트

Office Communications Server 2007 r 2와 동시에 Lync Server 2013을 배포한 후에는 토폴로지가 Lync Server 2013 및 Office Communications Server 2007 r 2의 공존 성 테스트 상태를 나타냅니다. 이 상태에 있는 동안 서비스가 시작되는지, 각 사이트를 관리할 수 있는지, 클라이언트가 현재 및 레거시 사용자와 통신할 수 있는지를 테스트하여 확인해야 합니다. 모든 사용자를 마이그레이션하기 전에 각 배포의 상태를 이해하고 각 배포가 올바르게 기능 및 작동하는지 확인해야 합니다. 일반적으로 Lync Server 2013의 파일럿 테스트 전반에서 동시 사용 테스트 단계가 진행 되 고 있습니다. 이전 사용자는 일정 기간 동안 Lync Server 2013로 이동 하 여 응용 프로그램 호환성과 기능 및 기능이 제대로 작동 하는지 확인 합니다. 파일럿 테스트를 수행한 후 사용자와 응용 프로그램은 Lync Server 2013의 프로덕션 버전으로 이동 되 고, Office Communications Server 2007 r 2의 레거시 풀 및 응용 프로그램은 폐기 됩니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

