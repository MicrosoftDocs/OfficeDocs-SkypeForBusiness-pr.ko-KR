---
title: 토폴로지 작성기로 재해 복구 및 고가용성 구성
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
ms.openlocfilehash: 73bcd2c2892e4e121512ae852d5920d600af91ff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743828"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="d34be-102">Lync Server 2013에서 토폴로지 작성기로 재해 복구 및 고가용성 구성</span><span class="sxs-lookup"><span data-stu-id="d34be-102">Using Topology Builder to configure high availability and disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d34be-103">_**마지막으로 수정한 주제:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="d34be-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="d34be-104">토폴로지 작성기 내에서 다음 단계를 수행 하 여 영구 채팅 서버에 대 한 고가용성 및 재해 복구를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d34be-104">Perform the following steps within Topology Builder to configure high availability and disaster recovery for Persistent Chat Server.</span></span>

1.  <span data-ttu-id="d34be-105">미러 데이터베이스와 로그 전달 보조 데이터베이스 SQL Server 저장소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d34be-105">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>

2.  <span data-ttu-id="d34be-106">영구 채팅 서버 서비스 속성을 다음으로 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="d34be-106">Edit the Persistent Chat Server service properties to:</span></span>
    
    1.  <span data-ttu-id="d34be-107">기본 데이터베이스에 대해 미러링을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d34be-107">Enable mirroring for the primary database.</span></span>
    
    2.  <span data-ttu-id="d34be-108">기본 미러 SQL Server 저장소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d34be-108">Add the primary mirror SQL Server store.</span></span>
    
    3.  <span data-ttu-id="d34be-109">SQL Server 로그 전달 데이터베이스를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d34be-109">Enable the SQL Server Log Shipping database.</span></span>
    
    4.  <span data-ttu-id="d34be-110">SQL Server 로그 전달 보조 SQL Server 저장소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d34be-110">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    5.  <span data-ttu-id="d34be-111">보조 데이터베이스에 대 한 SQL Server 저장소 미러를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d34be-111">Add the SQL Server store mirror for the secondary database.</span></span>
    
    6.  <span data-ttu-id="d34be-112">토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d34be-112">Publish the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

