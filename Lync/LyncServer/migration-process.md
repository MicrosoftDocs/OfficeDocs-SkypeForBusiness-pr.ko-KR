---
title: 마이그레이션 프로세스
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration process
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204696(v=OCS.15)
ms:contentKeyID: 48183474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f48d486332bf03204d25aaadfc2ea351bcf581a7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981625"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a>마이그레이션 프로세스

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-17_

Lync Server 2013에 대해 권장 되거나 지원 되는 마이그레이션 절차는 나란히 마이그레이션입니다. 이 항목에서는 나란히 마이그레이션을 사용 해야 하는 이유와 공존 테스트에 대 한 정보를 포함 합니다.

<div>

## <a name="side-by-side-migration"></a>나란히 마이그레이션

거의 모든 마이그레이션에는 side-by-side 마이그레이션 경로를 사용 해야 합니다. 나란히 마이그레이션하는 경우 lync server 2013를 사용 하 여 Lync server 2010를 실행 하는 해당 서버와 함께 새 서버를 배포한 다음 새 서버로 작업을 전송 합니다. Lync Server 2010로 롤백하는 데 필요한 경우 원래 서버로만 작업을 다시 전환할 수 있습니다. 이 상황에서는 업그레이드 된 클라이언트를 사용 하 여 예약 된 새 모임이 작동 하지 않으며 클라이언트도 다운 그레이드 해야 한다는 점에 유의 하세요.

</div>

<div>

## <a name="coexistence-testing"></a>공존 테스트

Lync server 2010를 사용 하 여 Lync Server 2013을 배포한 후 배포는 Lync Server 2013 및 Lync Server 2010의 공존 테스트 상태를 나타냅니다. 이 상태에서는 서비스를 시작 하 고 각 사이트를 관리할 수 있으며 클라이언트가 현재 및 레거시 사용자와 통신할 수 있는지를 테스트 하는 것이 중요 합니다. 모든 사용자를 마이그레이션하기 전에 각 배포의 상태를 이해 하 고 각 배포가 제대로 작동 하 고 작동 하는지 확인 하는 것이 중요 합니다. 일반적으로, Lync Server 2013의 파일럿 테스트 전체에 공존 테스트 단계가 있습니다. 레거시 사용자는 일정 기간 동안 Lync Server 2013로 이동 하 여 응용 프로그램 호환성과 기능 및 기능이 제대로 작동 하는지 확인 합니다. 파일럿 테스트 후에는 사용자 및 응용 프로그램이 Lync Server 2013의 프로덕션 버전으로 이동 하 고 Lync Server 2010의 레거시 풀 및 응용 프로그램은 사용 중지 됩니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

