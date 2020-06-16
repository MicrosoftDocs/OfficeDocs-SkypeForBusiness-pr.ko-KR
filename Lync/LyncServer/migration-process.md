---
title: 마이그레이션 프로세스
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204696(v=OCS.15)
ms:contentKeyID: 48183474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a31a127ef3a37ed366117247dd68c192d19e691
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756703"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-process"></a><span data-ttu-id="8e5e5-102">마이그레이션 프로세스</span><span class="sxs-lookup"><span data-stu-id="8e5e5-102">Migration process</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e5e5-103">_**마지막으로 수정 된 항목:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="8e5e5-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="8e5e5-104">Lync Server 2013에 대 한 권장 되 고 지원 되는 마이그레이션 절차는 side-by-side 마이그레이션입니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e5-104">The recommended and supported migration procedure for Lync Server 2013 is side-by-side migration.</span></span> <span data-ttu-id="8e5e5-105">이 항목에서는 병렬 마이그레이션을 사용해야 하는 이유에 대해 설명하며, 동시 사용 테스트에 대한 정보도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e5-105">This topic describes why you should use side-by-side migration and also includes information about coexistence testing.</span></span>

<div>

## <a name="side-by-side-migration"></a><span data-ttu-id="8e5e5-106">병렬 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="8e5e5-106">Side-By-Side Migration</span></span>

<span data-ttu-id="8e5e5-107">거의 모든 마이그레이션에서는 병렬 마이그레이션 경로를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e5-107">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="8e5e5-108">병렬 마이그레이션에서는 lync server 2010를 실행 하는 해당 서버와 함께 Lync Server 2013을 사용 하 여 새 서버를 배포한 다음 작업을 새 서버로 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e5-108">In a side-by-side migration, you deploy a new server with Lync Server 2013 alongside a corresponding server that is running Lync Server 2010, and then transfer operations to the new server.</span></span> <span data-ttu-id="8e5e5-109">Lync Server 2010로 롤백하는 데 필요한 경우 작업을 원래 서버로 다시 이동 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e5-109">If it becomes necessary to roll back to Lync Server 2010, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="8e5e5-110">이 경우 업그레이드된 클라이언트로 예약된 모든 새 모임이 작동하지 않으며 클라이언트도 다운그레이드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e5-110">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>

</div>

<div>

## <a name="coexistence-testing"></a><span data-ttu-id="8e5e5-111">동시 사용 테스트</span><span class="sxs-lookup"><span data-stu-id="8e5e5-111">Coexistence Testing</span></span>

<span data-ttu-id="8e5e5-112">Lync server 2010과 동시에 Lync 서버 2013을 배포한 후 배포는 Lync Server 2013 및 Lync Server 2010의 공존 테스트 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e5-112">After you have deployed Lync Server 2013 in parallel with Lync Server 2010, the deployment represents a coexistence testing state of Lync Server 2013 and Lync Server 2010.</span></span> <span data-ttu-id="8e5e5-113">이 상태에서는 테스트를 통해 서비스가 시작되었고, 각 사이트를 관리할 수 있으며, 클라이언트가 현재 및 레거시 사용자와 통신할 수 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e5-113">While in this state, it is important to test and ensure that services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="8e5e5-114">모든 사용자를 마이그레이션하기 전에 각 배포의 상태를 이해하고 각 배포가 올바르게 기능 및 작동하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e5-114">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="8e5e5-115">일반적으로 Lync Server 2013의 파일럿 테스트 전반에서 동시 사용 테스트 단계가 진행 되 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e5-115">Typically, the coexistence testing phase exists throughout the pilot testing of Lync Server 2013.</span></span> <span data-ttu-id="8e5e5-116">이전 사용자는 일정 기간 동안 Lync Server 2013로 이동 하 여 응용 프로그램 호환성과 기능 및 기능이 제대로 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e5-116">Legacy users are moved to Lync Server 2013 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="8e5e5-117">파일럿 테스트를 수행한 후 사용자와 응용 프로그램은 Lync Server 2013의 프로덕션 버전으로 이동 되 고 Lync Server 2010의 레거시 풀 및 응용 프로그램은 폐기 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e5e5-117">After pilot testing, users and applications are moved to the production version of Lync Server 2013, and the legacy pools and applications of Lync Server 2010 are retired.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

