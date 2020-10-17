---
title: 토폴로지 작성기를 사용 하 여 고가용성 및 재해 복구 구성
description: 토폴로지 작성기를 사용 하 여 고가용성 및 재해 복구를 구성 합니다.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Topology Builder to configure high availability and disaster recovery
ms:assetid: abc1a25d-1f5e-46ef-91d2-0144fc847206
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205172(v=OCS.15)
ms:contentKeyID: 48185113
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04764a58ac3ae1bbe0df97aadeabb03158ce8100
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547324"
---
# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="887b6-103">토폴로지 작성기를 사용 하 여 Lync Server 2013에서 고가용성 및 재해 복구 구성</span><span class="sxs-lookup"><span data-stu-id="887b6-103">Using Topology Builder to configure high availability and disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="887b6-104">_**마지막으로 수정 된 항목:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="887b6-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="887b6-105">토폴로지 작성기 내에서 다음 단계를 수행 하 여 영구 채팅 서버에 대 한 고가용성 및 재해 복구를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="887b6-105">Perform the following steps within Topology Builder to configure high availability and disaster recovery for Persistent Chat Server.</span></span>

1.  <span data-ttu-id="887b6-106">미러 데이터베이스 및 로그 전달 보조 데이터베이스 SQL Server 저장소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="887b6-106">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>

2.  <span data-ttu-id="887b6-107">영구 채팅 서버 서비스 속성을 다음과 같이 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="887b6-107">Edit the Persistent Chat Server service properties to:</span></span>
    
    1.  <span data-ttu-id="887b6-108">주 데이터베이스에 대한 미러링을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="887b6-108">Enable mirroring for the primary database.</span></span>
    
    2.  <span data-ttu-id="887b6-109">기본 미러 SQL Server 저장소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="887b6-109">Add the primary mirror SQL Server store.</span></span>
    
    3.  <span data-ttu-id="887b6-110">SQL Server 로그 전달 데이터베이스를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="887b6-110">Enable the SQL Server Log Shipping database.</span></span>
    
    4.  <span data-ttu-id="887b6-111">SQL Server 로그 전달 보조 SQL Server 저장소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="887b6-111">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    5.  <span data-ttu-id="887b6-112">보조 데이터베이스에 대 한 SQL Server 저장소 미러를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="887b6-112">Add the SQL Server store mirror for the secondary database.</span></span>
    
    6.  <span data-ttu-id="887b6-113">토폴로지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="887b6-113">Publish the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

