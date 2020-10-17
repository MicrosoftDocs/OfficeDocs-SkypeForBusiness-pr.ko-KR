---
title: 재해 복구를 위해 연장 된 영구 채팅 서버 풀 사용
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using a stretched Persistent Chat Server pool for disaster recovery
ms:assetid: 74c5287e-d70d-490a-9adc-ab419917ddd9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205007(v=OCS.15)
ms:contentKeyID: 48184506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c09231abfae7bbcc32083d7db72d8a4be79ecff
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535925"
---
# <a name="using-a-stretched-persistent-chat-server-pool-for-disaster-recovery-in-lync-server-2013"></a>Lync Server 2013에서 재해 복구를 위해 연장 된 영구 채팅 서버 풀 사용

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-06_

영구 채팅 서버에 대 한 재해 복구 솔루션은 스트레치 된 영구 채팅 서버 풀을 기반으로 합니다. 이는 Lync Server 2010의 대도시 사이트 복구와 유사 합니다. 그러나 확장 된 VLAN (가상 local area network)에 대 한 요구 사항은 없습니다. 영구 채팅 서버 풀을 스트레치 하면 기본적으로 토폴로지에서 하나의 풀이 논리적으로 구성 되지만 풀의 서버는 두 개의 서로 다른 데이터 센터에 실제로 배치 됩니다. 데이터베이스에 대 한 SQL Server 미러링을 동일한 방식으로 구성 하 고 데이터베이스 및 미러를 동일한 데이터 센터에 배포 합니다. 보조 데이터 센터에는 백업 데이터베이스를 구성해야 합니다(재해 복구 중 고가용성을 제공하기 위한 선택적인 미러 포함). 이러한 백업 데이터베이스는 재해 복구 중 장애 조치(Failover)를 위해 사용됩니다.

고가용성을 위해 SQL Server 미러링을 구성 하는 방법에 대 한 자세한 내용은 [Lync server 2013에서 Sql server 미러링을](lync-server-2013-sql-server-mirroring.md)참조 하세요. 재해 복구를 위해 데이터베이스를 장애 조치 (failover) 하는 방법에 대 한 자세한 내용은 [영구 채팅 서버 기본 데이터베이스에 대해 lync 2013 Server 로그 전달 설정](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) 및 [lync server 2013에서 기본 미러 및 로그 전달 보조 데이터베이스 간의 Sql server 로그 전달](lync-server-2013-set-up-log-shipping-secondary-database.md)설정를 참조 하십시오.

</div>

<span> </span>

</div>

</div>

</div>

