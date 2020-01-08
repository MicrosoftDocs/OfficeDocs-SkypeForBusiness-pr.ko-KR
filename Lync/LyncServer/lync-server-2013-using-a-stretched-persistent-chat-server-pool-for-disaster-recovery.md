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
ms.openlocfilehash: cced4904619fdbda87fecb29f35f11b40270c0ac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-a-stretched-persistent-chat-server-pool-for-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="dd918-102">Lync Server 2013에서 재해 복구를 위해 연장된 영구 채팅 서버 풀 사용</span><span class="sxs-lookup"><span data-stu-id="dd918-102">Using a stretched Persistent Chat Server pool for disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd918-103">_**마지막으로 수정한 주제:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="dd918-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="dd918-104">영구 채팅 서버의 재해 복구 솔루션은 늘어난 영구 채팅 서버 풀에 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd918-104">The disaster recovery solution for Persistent Chat Server is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="dd918-105">이는 Lync Server 2010의 수도권 사이트 복구와 유사 합니다. 그러나 늘어난 VLAN (가상 로컬 영역 네트워크)에 대 한 요구 사항은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dd918-105">This is similar to metropolitan site resiliency in Lync Server 2010; however, there is no requirement for a stretched virtual local area network (VLAN).</span></span> <span data-ttu-id="dd918-106">영구 채팅 서버 풀을 스트레치 하면 기본적으로 토폴로지에 하나의 풀이 논리적으로 구성 되지만, 서버를 두 개의 다른 데이터 센터에 물리적으로 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd918-106">By stretching Persistent Chat Server pool, you essentially configure one pool in the topology logically, but you physically place the servers in the pool in two different data centers.</span></span> <span data-ttu-id="dd918-107">동일한 데이터 센터에 데이터베이스와 미러를 배포 하는 같은 방식으로 데이터베이스에 대 한 SQL Server 미러링을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd918-107">Configure SQL Server mirroring for the database in the same way, and deploy the database and the mirror in the same data center.</span></span> <span data-ttu-id="dd918-108">재해 복구 중 고가용성을 제공 하는 선택적 미러를 사용 하 여 보조 데이터 센터에서 백업 데이터베이스를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd918-108">You need to configure a backup database in the secondary data center (with an optional mirror to provide high availability during disaster recovery).</span></span> <span data-ttu-id="dd918-109">재해 복구 중 장애 조치 (failover)에 사용 되는 백업 데이터베이스입니다.</span><span class="sxs-lookup"><span data-stu-id="dd918-109">This is the backup database used for failover during disaster recovery.</span></span>

<span data-ttu-id="dd918-110">고가용성을 위해 SQL Server 미러링을 구성 하는 방법에 대 한 자세한 내용은 [Lync server 2013에서 Sql server 미러링을](lync-server-2013-sql-server-mirroring.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd918-110">For details about how to configure SQL Server mirroring for high availability, see [SQL Server mirroring in Lync Server 2013](lync-server-2013-sql-server-mirroring.md).</span></span> <span data-ttu-id="dd918-111">재해 복구용으로 데이터베이스를 장애 조치 하는 방법에 대 한 자세한 내용은 lync server [2013에서 영구 채팅 서버 기본 데이터베이스에 대 한 Sql Server 로그 전달을 설정](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) 하 고 [lync server 2013에서 기본 미러 서버와 로그 전달 보조 데이터베이스 간에 sql Server 로그 전달을 설정](lync-server-2013-setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database.md)하는 방법에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="dd918-111">For details about failing over the database for disaster recovery, see [Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) and [Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database in Lync Server 2013](lync-server-2013-setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

