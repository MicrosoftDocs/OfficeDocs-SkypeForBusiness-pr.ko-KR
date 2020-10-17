---
title: Lync Server 2013 중앙 관리 저장소 장애 조치 (failover)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Central Management store failover
ms:assetid: f464d715-68a4-462c-9584-00f41ab10db0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205376(v=OCS.15)
ms:contentKeyID: 48185809
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 675f5b8e2880303a99897da18f44047c73961e4a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508045"
---
# <a name="central-management-store-failover-in-lync-server-2013"></a><span data-ttu-id="e811f-102">Lync Server 2013의 중앙 관리 저장소 장애 조치 (failover)</span><span class="sxs-lookup"><span data-stu-id="e811f-102">Central Management store failover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e811f-103">_**마지막으로 수정 된 항목:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="e811f-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="e811f-104">중앙 관리 저장소는 Lync 2013 배포의 서버 및 서비스에 대 한 구성 데이터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e811f-104">The Central Management store contains configuration data about servers and services in your Lync 2013 deployment.</span></span> <span data-ttu-id="e811f-105">Lync 2013 배포를 정의, 설정, 유지 관리, 관리, 설명 및 작동 하는 데 필요한 데이터에 대 한 강력 하 고 schematized 저장소를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e811f-105">It provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync 2013 deployment.</span></span> <span data-ttu-id="e811f-106">또한 데이터의 유효성을 검사하여 구성 일관성을 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="e811f-106">It also validates the data to ensure configuration consistency.</span></span>

<span data-ttu-id="e811f-107">각 Lync 배포에는 하나의 프런트 엔드 풀의 백 엔드 서버에서 호스팅하는 중앙 관리 저장소 하나가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e811f-107">Each Lync deployment includes one Central Management store, which is hosted by the Back End Server of one Front End pool.</span></span>

<span data-ttu-id="e811f-108">중앙 관리 저장소를 호스트 하는 풀을 포함 하는 풀 쌍을 설정 하면 백업 중앙 관리 저장소 데이터베이스는 백업 풀에 설정 되 고 중앙 관리 저장소 서비스는 두 풀에 모두 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e811f-108">When you establish a pool pairing that includes the pool hosting the Central Management store, a backup Central Management store database is set up in the backup pool, and Central Management store services are installed in both pools.</span></span> <span data-ttu-id="e811f-109">언제 든 지 두 중앙 관리 저장소 데이터베이스 중 하나가 활성 마스터이 고 다른 하나는 대기 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="e811f-109">At any point in time, one of the two Central Management store databases is the active master, and the other is a standby.</span></span> <span data-ttu-id="e811f-110">백업 서비스에서 콘텐츠를 활성 마스터에서 대기로 복제합니다.</span><span class="sxs-lookup"><span data-stu-id="e811f-110">The content is replicated by the Backup Service from the active master to the standby.</span></span>

<span data-ttu-id="e811f-111">중앙 관리 저장소를 호스트 하는 풀을 포함 하는 풀 장애 조치 (failover) 중에는 관리자가 프런트 엔드 풀을 장애 조치할 때까지 중앙 관리 저장소를 통과 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e811f-111">During a pool failover that involves the pools hosting the Central Management store, the administrator must fail over the Central Management store before failing over the Front End pool.</span></span>

<span data-ttu-id="e811f-112">재해가 복구 된 후에는 중앙 관리 저장소를 장애 조치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e811f-112">After the disaster is repaired, it is not necessary to fail back the Central Management store.</span></span> <span data-ttu-id="e811f-113">복구 후 원래 백업 풀의 중앙 관리 저장소는 활성 마스터로 유지 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e811f-113">After repair, the Central Management store in the original backup pool can remain as the active master.</span></span>

<span data-ttu-id="e811f-114">중앙 관리 저장소 장애 조치 (failover)의 엔지니어링 대상은 RTO (복구 시간 목표)의 경우 5 분, RPO (복구 지점 목표)의 경우 5 분입니다.</span><span class="sxs-lookup"><span data-stu-id="e811f-114">The engineering targets for Central Management store failover are 5 minutes for recovery time objective (RTO) and 5 minutes for recovery point objective (RPO).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

