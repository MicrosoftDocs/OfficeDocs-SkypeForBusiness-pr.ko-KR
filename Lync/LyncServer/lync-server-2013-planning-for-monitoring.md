---
title: 'Lync Server 2013: 모니터링 계획'
description: 'Lync Server 2013: 모니터링 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for monitoring
ms:assetid: 26cead5a-183c-42f1-a4b0-0e8d61c6159d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204752(v=OCS.15)
ms:contentKeyID: 48183671
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8ee78f06423bc167e26455d399ce2dd16f24262
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549334"
---
# <a name="planning-for-monitoring-in-lync-server-2013"></a><span data-ttu-id="566d0-103">Lync Server 2013의 모니터링 계획</span><span class="sxs-lookup"><span data-stu-id="566d0-103">Planning for monitoring in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="566d0-104">_**마지막으로 수정 된 항목:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="566d0-104">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="566d0-105">Microsoft Lync Server 2013의 모니터링 서비스는 관리자가 조직에서 수행 되는 통신 세션에 대 한 사용 현황, 추세 및 서비스 품질 데이터를 수집할 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="566d0-105">The monitoring service in Microsoft Lync Server 2013 provides a way for administrators to collect usage, trend, and quality of service data for the communication sessions that take place in their organization.</span></span> <span data-ttu-id="566d0-106">Lync Server 2013의 모니터링에는 더 이상 별도의 서버 역할이 필요 하지 않습니다. 대신 각 프런트 엔드 서버에 모니터링 서비스가 기본 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="566d0-106">Monitoring in Lync Server 2013 no longer requires a separate server role; instead, the monitoring service is built into each Front End server.</span></span> <span data-ttu-id="566d0-107">그러나 Lync Server 2013에서는 기본적으로 모니터링이 사용 하지 않도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="566d0-107">However, by default monitoring is not enabled in Lync Server 2013.</span></span> <span data-ttu-id="566d0-108">이 문서는 조직에서 모니터링을 사용 하도록 설정할지 여부를 결정 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="566d0-108">This document will help you determine whether or not monitoring should be enabled in your organization.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="566d0-109">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="566d0-109">In This Section</span></span>

  - [<span data-ttu-id="566d0-110">Lync Server 2013의 모니터링 개요</span><span class="sxs-lookup"><span data-stu-id="566d0-110">Overview of monitoring in Lync Server 2013</span></span>](lync-server-2013-overview-of-monitoring.md)

  - [<span data-ttu-id="566d0-111">Lync Server 2013에서 모니터링에 대 한 요구 사항 정의</span><span class="sxs-lookup"><span data-stu-id="566d0-111">Defining your requirements for monitoring in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-monitoring.md)

  - [<span data-ttu-id="566d0-112">Lync Server 2013에서 모니터링 사용</span><span class="sxs-lookup"><span data-stu-id="566d0-112">Enabling monitoring in Lync Server 2013</span></span>](lync-server-2013-enabling-monitoring.md)

  - [<span data-ttu-id="566d0-113">Lync Server 2013에서 모니터링 데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="566d0-113">Accessing monitoring data in Lync Server 2013</span></span>](lync-server-2013-accessing-monitoring-data.md)

  - [<span data-ttu-id="566d0-114">Lync Server 2013의 모니터링에 대 한 구성 요소 및 토폴로지</span><span class="sxs-lookup"><span data-stu-id="566d0-114">Components and topologies for monitoring in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-monitoring.md)

  - [<span data-ttu-id="566d0-115">Lync Server 2013의 모니터링을 위한 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="566d0-115">Deployment checklist for monitoring in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-monitoring.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

