---
title: 재해 복구를 위해 연장된 영구 채팅 서버 풀 사용
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using a stretched Persistent Chat Server pool for disaster recovery
ms:assetid: 74c5287e-d70d-490a-9adc-ab419917ddd9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205007(v=OCS.15)
ms:contentKeyID: 48184506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ae23ed2d12548388cd1462aad653de4652633dc
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-a-stretched-persistent-chat-server-pool-for-disaster-recovery-in-lync-server-2013"></a>Lync Server 2013에서 재해 복구를 위해 연장된 영구 채팅 서버 풀 사용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-06_

영구 채팅 서버의 재해 복구 솔루션은 늘어난 영구 채팅 서버 풀에 빌드됩니다. 이는 Lync Server 2010의 수도권 사이트 복구와 유사 합니다. 그러나 늘어난 VLAN (가상 로컬 영역 네트워크)에 대 한 요구 사항은 없습니다. 영구 채팅 서버 풀을 스트레치 하면 기본적으로 토폴로지에 하나의 풀이 논리적으로 구성 되지만, 서버를 두 개의 다른 데이터 센터에 물리적으로 배치할 수 있습니다. 동일한 데이터 센터에 데이터베이스와 미러를 배포 하는 같은 방식으로 데이터베이스에 대 한 SQL Server 미러링을 구성 합니다. 재해 복구 중 고가용성을 제공 하는 선택적 미러를 사용 하 여 보조 데이터 센터에서 백업 데이터베이스를 구성 해야 합니다. 재해 복구 중 장애 조치 (failover)에 사용 되는 백업 데이터베이스입니다.

고가용성을 위해 SQL Server 미러링을 구성 하는 방법에 대 한 자세한 내용은 [Lync server 2013에서 Sql server 미러링을](lync-server-2013-sql-server-mirroring.md)참조 하세요. 재해 복구용으로 데이터베이스를 장애 조치 하는 방법에 대 한 자세한 내용은 lync server [2013에서 영구 채팅 서버 기본 데이터베이스에 대 한 Sql Server 로그 전달을 설정](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) 하 고 [lync server 2013에서 기본 미러 서버와 로그 전달 보조 데이터베이스 간에 sql Server 로그 전달을 설정](lync-server-2013-set-up-log-shipping-secondary-database.md)하는 방법에 대해 알아보세요.

</div>

<span> </span>

</div>

</div>

</div>

