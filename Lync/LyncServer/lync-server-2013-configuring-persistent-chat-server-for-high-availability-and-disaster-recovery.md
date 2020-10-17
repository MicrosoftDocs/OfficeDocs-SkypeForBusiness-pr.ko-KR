---
title: 고가용성 및 재해 복구를 위한 영구 채팅 서버 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Persistent Chat Server for high availability and disaster recovery
ms:assetid: eebc581c-e3a0-4b69-8a43-80b607b4d8f2
ms:mtpsurl: https://technet.microsoft.com/library/JJ205364(v=OCS.15)
ms:contentKeyID: 48185760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90bb6ee0d9c060787c7b750046f79810aeb0c425
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532415"
---
# <a name="configuring-persistent-chat-server-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="13b1e-102">Lync Server 2013에서 고가용성 및 재해 복구를 위한 영구 채팅 서버 구성</span><span class="sxs-lookup"><span data-stu-id="13b1e-102">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13b1e-103">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="13b1e-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="13b1e-104">Lync Server 2013, 영구 채팅 서버 서비스는 재해 복구를 위해 *스트레치 된 풀* 구성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13b1e-104">The Lync Server 2013, Persistent Chat Server services use a *stretched pool* configuration for disaster recovery.</span></span> <span data-ttu-id="13b1e-105">스트레치 된 풀은 두 개의 실제 데이터 센터 간에 분산 되어 있지만 단일 논리적 Lync Server 사이트 내에 있는 컴퓨터를 포함 하는 풀입니다.</span><span class="sxs-lookup"><span data-stu-id="13b1e-105">A stretched pool is a pool that has computers that are distributed between two physical data centers, but are within a single logical Lync Server site.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="13b1e-106">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="13b1e-106">In This Section</span></span>

  - [<span data-ttu-id="13b1e-107">Lync Server 2013의 영구 채팅 서버에 필요한 리소스</span><span class="sxs-lookup"><span data-stu-id="13b1e-107">Required resources for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-required-resources-for-persistent-chat-server.md)

  - [<span data-ttu-id="13b1e-108">토폴로지 작성기를 사용 하 여 Lync Server 2013에서 고가용성 및 재해 복구 구성</span><span class="sxs-lookup"><span data-stu-id="13b1e-108">Using Topology Builder to configure high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-using-topology-builder-to-configure-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="13b1e-109">Lync Server 2013에서 재해 복구를 위해 연장 된 영구 채팅 서버 풀 사용</span><span class="sxs-lookup"><span data-stu-id="13b1e-109">Using a stretched Persistent Chat Server pool for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-using-a-stretched-persistent-chat-server-pool-for-disaster-recovery.md)

  - [<span data-ttu-id="13b1e-110">Lync Server 2013의 SQL Server 미러링</span><span class="sxs-lookup"><span data-stu-id="13b1e-110">SQL Server mirroring in Lync Server 2013</span></span>](lync-server-2013-sql-server-mirroring.md)

  - [<span data-ttu-id="13b1e-111">영구 채팅 서버 기본 데이터베이스에 대해 Lync Server 2013에서 SQL Server 로그 전달 설정</span><span class="sxs-lookup"><span data-stu-id="13b1e-111">Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database</span></span>](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md)

  - [<span data-ttu-id="13b1e-112">Lync Server 2013에서 기본 미러 및 로그 전달 보조 데이터베이스 간의 SQL Server 로그 전달 설정</span><span class="sxs-lookup"><span data-stu-id="13b1e-112">Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database in Lync Server 2013</span></span>](lync-server-2013-set-up-log-shipping-secondary-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

