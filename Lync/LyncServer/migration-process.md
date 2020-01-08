---
title: 마이그레이션 프로세스
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration process
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204696(v=OCS.15)
ms:contentKeyID: 48183474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f48d486332bf03204d25aaadfc2ea351bcf581a7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981625"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a><span data-ttu-id="080a3-102">마이그레이션 프로세스</span><span class="sxs-lookup"><span data-stu-id="080a3-102">Migration process</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="080a3-103">_**마지막으로 수정한 주제:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="080a3-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="080a3-104">Lync Server 2013에 대해 권장 되거나 지원 되는 마이그레이션 절차는 나란히 마이그레이션입니다.</span><span class="sxs-lookup"><span data-stu-id="080a3-104">The recommended and supported migration procedure for Lync Server 2013 is side-by-side migration.</span></span> <span data-ttu-id="080a3-105">이 항목에서는 나란히 마이그레이션을 사용 해야 하는 이유와 공존 테스트에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="080a3-105">This topic describes why you should use side-by-side migration and also includes information about coexistence testing.</span></span>

<div>

## <a name="side-by-side-migration"></a><span data-ttu-id="080a3-106">나란히 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="080a3-106">Side-By-Side Migration</span></span>

<span data-ttu-id="080a3-107">거의 모든 마이그레이션에는 side-by-side 마이그레이션 경로를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="080a3-107">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="080a3-108">나란히 마이그레이션하는 경우 lync server 2013를 사용 하 여 Lync server 2010를 실행 하는 해당 서버와 함께 새 서버를 배포한 다음 새 서버로 작업을 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="080a3-108">In a side-by-side migration, you deploy a new server with Lync Server 2013 alongside a corresponding server that is running Lync Server 2010, and then transfer operations to the new server.</span></span> <span data-ttu-id="080a3-109">Lync Server 2010로 롤백하는 데 필요한 경우 원래 서버로만 작업을 다시 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="080a3-109">If it becomes necessary to roll back to Lync Server 2010, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="080a3-110">이 상황에서는 업그레이드 된 클라이언트를 사용 하 여 예약 된 새 모임이 작동 하지 않으며 클라이언트도 다운 그레이드 해야 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="080a3-110">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>

</div>

<div>

## <a name="coexistence-testing"></a><span data-ttu-id="080a3-111">공존 테스트</span><span class="sxs-lookup"><span data-stu-id="080a3-111">Coexistence Testing</span></span>

<span data-ttu-id="080a3-112">Lync server 2010를 사용 하 여 Lync Server 2013을 배포한 후 배포는 Lync Server 2013 및 Lync Server 2010의 공존 테스트 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="080a3-112">After you have deployed Lync Server 2013 in parallel with Lync Server 2010, the deployment represents a coexistence testing state of Lync Server 2013 and Lync Server 2010.</span></span> <span data-ttu-id="080a3-113">이 상태에서는 서비스를 시작 하 고 각 사이트를 관리할 수 있으며 클라이언트가 현재 및 레거시 사용자와 통신할 수 있는지를 테스트 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="080a3-113">While in this state, it is important to test and ensure that services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="080a3-114">모든 사용자를 마이그레이션하기 전에 각 배포의 상태를 이해 하 고 각 배포가 제대로 작동 하 고 작동 하는지 확인 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="080a3-114">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="080a3-115">일반적으로, Lync Server 2013의 파일럿 테스트 전체에 공존 테스트 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="080a3-115">Typically, the coexistence testing phase exists throughout the pilot testing of Lync Server 2013.</span></span> <span data-ttu-id="080a3-116">레거시 사용자는 일정 기간 동안 Lync Server 2013로 이동 하 여 응용 프로그램 호환성과 기능 및 기능이 제대로 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="080a3-116">Legacy users are moved to Lync Server 2013 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="080a3-117">파일럿 테스트 후에는 사용자 및 응용 프로그램이 Lync Server 2013의 프로덕션 버전으로 이동 하 고 Lync Server 2010의 레거시 풀 및 응용 프로그램은 사용 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="080a3-117">After pilot testing, users and applications are moved to the production version of Lync Server 2013, and the legacy pools and applications of Lync Server 2010 are retired.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

