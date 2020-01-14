---
title: 고가용성 및 재해 복구를 위한 영구 채팅 서버 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Persistent Chat Server for high availability and disaster recovery
ms:assetid: eebc581c-e3a0-4b69-8a43-80b607b4d8f2
ms:mtpsurl: https://technet.microsoft.com/library/JJ205364(v=OCS.15)
ms:contentKeyID: 48185760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b9ceda51485b0f4f9fde33a9499ca05998176b3
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111512"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-persistent-chat-server-for-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="7a43d-102">Lync Server 2013에서 고가용성 및 재해 복구를 위한 영구 채팅 서버 구성</span><span class="sxs-lookup"><span data-stu-id="7a43d-102">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a43d-103">_**마지막으로 수정한 주제:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="7a43d-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="7a43d-104">Lync Server 2013, 영구 채팅 서버 서비스는 장애 복구용으로 *스트레치 된 풀* 구성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a43d-104">The Lync Server 2013, Persistent Chat Server services use a *stretched pool* configuration for disaster recovery.</span></span> <span data-ttu-id="7a43d-105">스트레치 된 풀은 두 개의 실제 데이터 센터로 분산 되지만 단일 논리적 Lync 서버 사이트 내에 있는 컴퓨터가 있는 풀입니다.</span><span class="sxs-lookup"><span data-stu-id="7a43d-105">A stretched pool is a pool that has computers that are distributed between two physical data centers, but are within a single logical Lync Server site.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7a43d-106">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="7a43d-106">In This Section</span></span>

  - [<span data-ttu-id="7a43d-107">Lync Server 2013의 영구 채팅 서버에 필요한 리소스</span><span class="sxs-lookup"><span data-stu-id="7a43d-107">Required resources for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-required-resources-for-persistent-chat-server.md)

  - [<span data-ttu-id="7a43d-108">Lync Server 2013에서 토폴로지 작성기로 재해 복구 및 고가용성 구성</span><span class="sxs-lookup"><span data-stu-id="7a43d-108">Using Topology Builder to configure high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-using-topology-builder-to-configure-high-availability-and-disaster-recovery.md)

  - [<span data-ttu-id="7a43d-109">Lync Server 2013에서 재해 복구를 위해 연장된 영구 채팅 서버 풀 사용</span><span class="sxs-lookup"><span data-stu-id="7a43d-109">Using a stretched Persistent Chat Server pool for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-using-a-stretched-persistent-chat-server-pool-for-disaster-recovery.md)

  - [<span data-ttu-id="7a43d-110">Lync Server 2013의 SQL Server 미러링</span><span class="sxs-lookup"><span data-stu-id="7a43d-110">SQL Server mirroring in Lync Server 2013</span></span>](lync-server-2013-sql-server-mirroring.md)

  - [<span data-ttu-id="7a43d-111">영구 채팅 서버 기본 데이터베이스에 대해 Lync Server 2013의 SQL Server 로그 전달 설정</span><span class="sxs-lookup"><span data-stu-id="7a43d-111">Setting up SQL Server Log Shipping in Lync Server 2013 for the Persistent Chat Server primary database</span></span>](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md)

  - [<span data-ttu-id="7a43d-112">Lync Server 2013에서 기본 미러와 로그 전달 보조 데이터베이스 간의 SQL Server 로그 전달 설정</span><span class="sxs-lookup"><span data-stu-id="7a43d-112">Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database in Lync Server 2013</span></span>](lync-server-2013-set-up-log-shipping-secondary-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

