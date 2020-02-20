---
title: 백 엔드 서버에서 SQL Server 인스턴스 및 데이터베이스 제거
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove SQL Server instances and databases on the Back End Server
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49733606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02aa65c631e62d7ffb699d85d982858164848c2a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>백 엔드 서버에서 SQL Server 인스턴스 및 데이터베이스 제거

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-19_

Microsoft SQL Server 데이터베이스 및 인스턴스를 제거 하는 경우에는 해당 서버에 종속 된 Lync Server 2010을 실행 하는 서버를 제거한 후 또는 Lync Server 2010를 실행 하는 서버를 다시 구성한 후 다른 데이터베이스를 사용할 수 있습니다. 현재 SQL Server를 사용 하지 않도록 중지 하거나 Lync Server 2010를 실행 하는 현재 서버를 다시 구성 하 여 데이터베이스를 오래 되었거나 사용할 수 없도록 설정한 경우이 항목의 절차를 수행 해야 합니다.

보관 서버 또는 모니터링 서버에 대 한 데이터베이스 또는 인스턴스를 제거 하려면 먼저 서버 역할을 제거 해야 합니다. 마찬가지로 프런트 엔드 풀에 대 한 인스턴스 또는 데이터베이스를 제거 하려면 먼저 종속 서버 역할을 제거 하거나 다시 구성 해야 합니다. 이러한 절차는 배치된 데이터베이스나 개별 서버 인스턴스 간에 구분되지 않습니다. 데이터베이스 배치는 절차에 영향을 주지 않습니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [프런트 엔드 풀에 대 한 SQL Server 데이터베이스 제거](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [모니터링 서버에 대 한 SQL Server 데이터베이스 제거](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [보관 서버에 대 한 SQL Server 데이터베이스 제거](remove-the-sql-server-database-for-an-archiving-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

