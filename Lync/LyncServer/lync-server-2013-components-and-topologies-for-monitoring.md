---
title: 'Lync Server 2013: 모니터링을 위한 구성 요소 및 토폴로지'
description: 'Lync Server 2013: 모니터링을 위한 구성 요소 및 토폴로지'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for monitoring
ms:assetid: c1bb36b0-1fb8-4d8e-9cc9-9bef740fe3c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412952(v=OCS.15)
ms:contentKeyID: 48185313
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8767a7eb16ca85e9606838606a6e86ee1296fc0e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576844"
---
# <a name="components-and-topologies-for-monitoring-in-lync-server-2013"></a>Lync Server 2013의 모니터링에 대 한 구성 요소 및 토폴로지

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-05_

통합 데이터 수집 에이전트는 각 프런트 엔드 서버에서 자동으로 설치 및 활성화 되므로 모니터링 서버로 작동 하도록 서버를 구성할 필요가 없습니다. 각 프런트 엔드 서버는 이미 모니터링 서버로 작동 합니다. 그러나 모니터링 데이터에 대 한 백 엔드 데이터 저장소로 작동 하도록 데이터베이스를 설치 하 고 구성 해야 합니다. Microsoft Lync Server 2013에서는 모니터링할 백 엔드 저장소로 다음 데이터베이스를 사용할 수 있습니다.

  - Microsoft SQL Server 2008 R2 Enterprise Edition

  - Microsoft SQL Server 2008 R2 Standard Edition

  - Microsoft SQL Server 2012 Enterprise Edition

  - Microsoft SQL Server 2012 Standard Edition

이러한 데이터베이스의 64 비트 버전을 사용 해야 합니다. 32 비트 버전의 SQL Server는 모니터링을 위한 백엔드 저장소로 사용할 수 없습니다. 마찬가지로 Lync Server 2013에서는 Express Edition for SQL Server 2008 또는 SQL Server 2012을 지원 하지 않습니다. Lync Server 2013에 대 한 데이터베이스 요구 사항에 대 한 자세한 내용은 lync server 2013 지원 가능성 가이드의 [Lync server 2013에서 데이터베이스 소프트웨어 지원](lync-server-2013-database-software-support.md) 항목을 참조 하십시오.

모니터링을 배포 및 구성 하기 전에 SQL Server를 설치 하 고 구성 해야 합니다. 그러나 SQL Server 자체를 배포 하기만 하면 됩니다. 모니터링 데이터베이스를 미리 설정할 필요는 없습니다. 대신 사용자가 Lync Server 토폴로지를 게시할 때 해당 데이터베이스가 자동으로 만들어집니다.

모니터링 데이터는 SQL Server 인스턴스를 다른 유형의 데이터와 공유할 수 있습니다. 일반적으로 통화 정보 기록 데이터베이스 (LcsCdr) 및 QoEMetrics (Experience Quality database)는 동일한 SQL 인스턴스를 공유 합니다. 또한 두 모니터링 데이터베이스가 보관 데이터베이스 (LcsLog)와 동일한 SQL 인스턴스에 있는 것이 일반적입니다. SQL Server 인스턴스를 사용 하는 유일한 실질적인 요구 사항은 SQL Server의 인스턴스 하나가 다음에 제한 된다는 것입니다.

  - Lync Server 2013 백 엔드 데이터베이스의 인스턴스 1 개 일반적으로는 모니터링 데이터베이스를 동일한 SQL 인스턴스 또는 같은 컴퓨터에 백엔드 데이터베이스와 동일 하 게 배치 된 않는 것이 좋습니다. 기술적으로는 가능 하지만 백 엔드 데이터베이스에 필요한 디스크 공간을 사용 하 여 모니터링 데이터베이스의 위험을 실행 합니다.

  - 통화 정보 기록 데이터베이스의 인스턴스 하나

  - 품질을 경험 하는 데이터베이스의 한 가지 인스턴스입니다.

  - 보관 데이터베이스의 인스턴스 하나

즉, 동일한 SQL Server 인스턴스에 두 개의 LcsCdr 데이터베이스 인스턴스가 있을 수 없습니다. LcsCdr 데이터베이스의 인스턴스가 여러 개 필요한 경우에는 여러 SQL Server 인스턴스를 구성 해야 합니다.

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 모니터링 배포](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

