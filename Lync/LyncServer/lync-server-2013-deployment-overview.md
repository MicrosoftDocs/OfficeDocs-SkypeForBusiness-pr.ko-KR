---
title: 'Lync Server 2013: 배포 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment overview
ms:assetid: da67555e-f410-4c37-9996-d511f37da8d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205305(v=OCS.15)
ms:contentKeyID: 48185555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b21d6c6a977fbb94a54114753f32c022aa5e713
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213799"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-overview-for-lync-server-2013"></a>Lync Server 2013의 배포 개요

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-03-12_

Lync Server 2013 Enterprise Edition과 Lync Server 2013 Standard Edition의 주요 차이점은 Standard Edition은 Enterprise Edition에 포함 된 고가용성 기능을 지원 하지 않는다는 것입니다. 고가용성을 사용 하려면 여러 프런트 엔드 서버를 풀에 배포 하 고 SQL Server를 실행 하는 서버를 미러링할 수 있어야 합니다. Enterprise Edition을 사용 하 여 독립 실행형 중재 서버를 함께 배치할 또는 정의할 수 있습니다. 모니터링 서버 및 보관 서버는 SQL Server를 실행 하는 독립 실행형 서버를 사용할 수 있습니다. 또는 프런트 엔드 서버 및 풀에 대 한 데이터베이스 서버에서 실행 되는 SQL Server의 인스턴스가 있을 수 있습니다.

Lync Server 2013 Standard Edition을 실행 하는 서버는 조직의 주요 배포에서 지리적으로 제거 되는 소규모 조직 및 원격 위치를 위한 것입니다. 재해가 발생 한 경우 장애 조치 (failover)를 위해 두 개의 Standard Edition 서버 서버가 최대 5000 명의 사용자를 지원할 수 있습니다. Enterprise Edition의 프런트 엔드 서버와 마찬가지로 Standard Edition 서버를 풀링할 수 없습니다. 또한 Standard Edition에서 사용 하는 SQL Server 데이터베이스는 Standard Edition server 작업을 처리 하도록 설계 된, SQL Server Express를 실행 하는 배치 된 서버입니다. 모든 역할이 Standard Edition 서버에 상주해 야 하는 것은 아닙니다. 독립 실행형 중재 서버 및에 지 서버를 사용할 수 있습니다. 중앙 관리 저장소에 대 한 SQL Server 데이터베이스와 Lync Server 2013의 용도는 SQL Server를 실행 하는 서버와 배치 된 Standard Edition server에 있어야 합니다. 모니터링 서버 및 보관 서버는 SQL Server 데이터베이스와 함께 독립 실행형 서버를 사용 합니다.

</div>

<span> </span>

</div>

</div>

</div>

