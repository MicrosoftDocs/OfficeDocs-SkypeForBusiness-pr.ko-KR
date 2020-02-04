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
ms.openlocfilehash: 11439dd9fd339c3620b3e6288526459f45a2a542
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727108"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>백 엔드 서버에서 SQL Server 인스턴스 및 데이터베이스 제거

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-19_

Microsoft SQL Server 데이터베이스 및 인스턴스를 제거 하면 해당 사용자에 게 종속 된 Lync Server 2010를 실행 하는 서버를 제거한 후 또는 Lync Server 2010를 실행 하는 서버를 다시 구성 하 여 다른 데이터베이스를 사용 합니다. 현재 SQL Server를 중지 하거나 Lync Server 2010을 실행 하는 현재 서버를 다시 구성 하 여 데이터베이스를 더 이상 사용 하지 않거나 사용할 수 없게 되는 경우이 항목의 절차를 수행 해야 합니다.

보관 서버 또는 모니터링 서버의 데이터베이스나 인스턴스를 제거 하려면 먼저 서버 역할을 제거 해야 합니다. 마찬가지로, 프런트 엔드 풀에 대 한 인스턴스 또는 데이터베이스를 제거 하려면 먼저 종속 서버 역할을 제거 하거나 다시 구성 해야 합니다. 이러한 절차는 collocated 데이터베이스와 서버에 대 한 별도의 인스턴스를 구분 하지 않습니다. 프로시저는 데이터베이스의 collocation에 영향을 받지 않습니다.

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [프런트 엔드 풀에 대한 SQL Server 데이터베이스 제거](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [모니터링 서버용 SQL Server 데이터베이스 제거](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [보관 서버용 SQL Server 데이터베이스 제거](remove-the-sql-server-database-for-an-archiving-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

