---
title: 'Lync Server 2013: 모니터링 데이터에 액세스'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Accessing monitoring data
ms:assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688116(v=OCS.15)
ms:contentKeyID: 49733714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 609963f3248d5bdd1c50eac45b74c188ab2e6c56
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="accessing-monitoring-data-in-lync-server-2013"></a>Lync Server 2013에서 모니터링 데이터에 액세스

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-05_

모니터링 데이터는 SQL Server 데이터베이스 쌍 (LcsCdr)에 저장 되며, 통화 세부 정보를 기록 하 고 QoEMetrics 데이터에 대 한 품질을 제공할 수 있습니다. 이러한 두 데이터베이스에 대 한 특별 한 것이 없습니다. 즉, SQL Server 데이터에 액세스 하 고 분석 하는 데 일반적으로 사용 하는 도구를 사용 하 여 해당 데이터베이스에 저장 된 데이터에 액세스할 수 있습니다.

모니터링 데이터에 액세스 하 고 분석 하기 위해 고려해 야 하는 도구는 Lync Server 모니터링 보고서입니다. 모니터링 보고서는 Microsoft SQL Server Reporting 서비스에 의해 게시 되는 표준 보고서 집합입니다. 웹 브라우저를 사용 하 여 액세스할 수 있는 이러한 보고서에는 CDR 및 체감 품질 데이터베이스에 저장 된 CDR (통화 정보 기록) 및 체감 품질 (사용 품질) 레코드를 기준으로 하는 사용량, 호출 진단 정보 및 미디어 품질 정보가 제공 됩니다. 모니터링 보고서는 Lync Server 2013와 함께 제공 되며 lync server를 설치 하 고 모니터링을 구성한 후 Lync Server 배포 마법사에서 설치할 수 있습니다.

참고로, 모니터링 보고서에는 SQL Server Reporting Service를 사용 해야 합니다. Sql server Reporting Service는 sql Server를 설치할 때와 동시에 설치 하거나 SQL Server 자체 설치 후 언제 든 설치할 수 있습니다.

자세한 내용은 Lync Server 2013 배포 가이드에서 [Lync server 2013 모니터링 보고서 설치](lync-server-2013-installing-lync-server-2013-monitoring-reports.md) 항목을 참조 하세요.

</div>

<span> </span>

</div>

</div>

</div>

