---
title: 'Lync Server 2013: 배포 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment overview
ms:assetid: da67555e-f410-4c37-9996-d511f37da8d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205305(v=OCS.15)
ms:contentKeyID: 48185555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f71a61e2bd374f1dfe2863aead5bbadc23c8afe8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983870"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-overview-for-lync-server-2013"></a><span data-ttu-id="e3b64-102">Lync Server 2013에 대한 배포 개요</span><span class="sxs-lookup"><span data-stu-id="e3b64-102">Deployment overview for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3b64-103">_**마지막으로 수정한 주제:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="e3b64-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="e3b64-104">Lync Server 2013 Enterprise Edition과 Lync Server 2013 Standard Edition의 주요 차이점은 스탠더드 버전이 Enterprise Edition에 포함 된 고가용성 기능을 지원 하지 않는다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b64-104">The main difference between Lync Server 2013 Enterprise Edition and Lync Server 2013 Standard Edition is that Standard Edition does not support the high availability features included with Enterprise Edition.</span></span> <span data-ttu-id="e3b64-105">가용성을 높이기 위해 여러 프런트 엔드 서버를 풀에 배포 하 고 SQL Server를 실행 하는 서버를 미러링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b64-105">For high availability, you need to deploy multiple Front End Servers to a pool and then you can mirror the server running SQL Server.</span></span> <span data-ttu-id="e3b64-106">Enterprise Edition을 사용 하 여 독립 실행형 중재 서버를 collocate 또는 정의 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b64-106">With Enterprise Edition you can choose to collocate or define a stand-alone Mediation Server.</span></span> <span data-ttu-id="e3b64-107">모니터링 서버와 보관 서버는 SQL Server를 실행 하는 독립 실행형 서버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b64-107">The Monitoring Server and Archiving Server can use a stand-alone server running SQL Server.</span></span> <span data-ttu-id="e3b64-108">또는 프런트 엔드 서버와 풀에 대해 데이터베이스 서버에서 실행 되는 SQL Server 인스턴스를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b64-108">Or, they can have instances of SQL Server running on the database server for the Front End Servers and pools.</span></span>

<span data-ttu-id="e3b64-109">Lync Server 2013 Standard Edition을 실행 하는 서버는 조직의 주요 배포에서 지리적으로 제거 되는 소규모 조직 및 원격 위치를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b64-109">Servers running Lync Server 2013 Standard Edition are intended for smaller organizations and remote locations, which are geographically removed from the organization’s main deployment.</span></span> <span data-ttu-id="e3b64-110">재해가 발생 하는 경우 장애 조치를 위해 두 개의 표준 버전 서버 서버가 서로 5000 명의 사용자까지 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b64-110">Two Standard Edition server servers paired together for failover in case of disaster can support up to 5,000 users.</span></span> <span data-ttu-id="e3b64-111">Enterprise Edition의 프런트 엔드 서버와 마찬가지로 Standard Edition 서버를 풀링할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b64-111">You cannot pool Standard Edition servers like you can Front End Servers in Enterprise Edition.</span></span> <span data-ttu-id="e3b64-112">또한, 표준 버전의 서버 작업을 처리 하도록 설계 된 SQL Server Express를 실행 하는 collocated 서버를 사용 하는 SQL Server 데이터베이스입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b64-112">Also, the SQL Server database that Standard Edition uses is a collocated server running SQL Server Express that is designed to handle Standard Edition server workloads.</span></span> <span data-ttu-id="e3b64-113">모든 역할이 스탠더드 버전 서버에 상주해 야 한다는 것을 의미 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b64-113">This is not to say that all roles must reside on a Standard Edition server.</span></span> <span data-ttu-id="e3b64-114">독립 실행형 중재 서버 및 Edge 서버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b64-114">You can have stand-alone Mediation Servers and Edge Servers.</span></span> <span data-ttu-id="e3b64-115">중앙 관리 저장소에 대 한 SQL Server 데이터베이스 및 Lync Server 2013의 용도는 SQL Server를 실행 하는 서버를 사용 하는 collocated Standard Edition Server에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b64-115">The SQL Server database for the Central Management store and for the purposes of Lync Server 2013 must reside on the Standard Edition server collocated with the server running SQL Server.</span></span> <span data-ttu-id="e3b64-116">모니터링 서버 및 보관 서버는 SQL Server 데이터베이스와 함께 독립 실행형 서버를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b64-116">The Monitoring Server and Archiving Server use a stand-alone server with the SQL Server database.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

