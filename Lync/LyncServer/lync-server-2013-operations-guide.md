---
title: 'Lync Server 2013: 운영 가이드'
description: 'Lync Server 2013: 운영 가이드'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Operations Guide
ms:assetid: dcb9ddff-6fe3-4077-a2e3-0ba64f65e264
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720467(v=OCS.15)
ms:contentKeyID: 63969658
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85e562b96e87f54529a9e2ce077a0a82574020c1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565890"
---
# <a name="operations-guide-for-lync-server-2013"></a><span data-ttu-id="fe30b-103">Lync Server 2013에 대 한 운영 가이드</span><span class="sxs-lookup"><span data-stu-id="fe30b-103">Operations Guide for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe30b-104">_**마지막으로 수정 된 항목:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="fe30b-104">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="fe30b-105">이 문서에서는 Microsoft Lync Server 2013 통신 소프트웨어 환경을 유지 관리 하는 데 필요한 운영 프로세스, 작업 및 도구에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe30b-105">This document describes the operational processes, tasks, and tools that are required for you to maintain a Microsoft Lync Server 2013 communications software environment.</span></span> <span data-ttu-id="fe30b-106">또한 MOF (Microsoft Operations Framework) 모델에 따라 Lync Server 2013를 관리 하는 방법에 대해 설명 하 고, 효율적인 작업 환경을 유지 관리 하기 위한 일정, 프로세스 및 절차를 구현 하는 효율적인 운영 관리 환경을 디자인 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe30b-106">It explains how to manage Lync Server 2013 according to the Microsoft Operations Framework (MOF) model and it will help you design an efficient operational management environment, which includes implementing schedules, processes and procedures to maintain an efficient working environment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fe30b-107">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="fe30b-107">In This Section</span></span>

<span data-ttu-id="fe30b-108">다음 섹션이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe30b-108">The following sections are included:</span></span>

  - [<span data-ttu-id="fe30b-109">Lync Server 2013 환경에 대 한 모범 사례</span><span class="sxs-lookup"><span data-stu-id="fe30b-109">Best practices for Lync Server 2013 environments</span></span>](lync-server-2013-best-practices-for-lync-server-environments.md)

  - [<span data-ttu-id="fe30b-110">Lync Server 2013의 일별 작업</span><span class="sxs-lookup"><span data-stu-id="fe30b-110">Daily tasks in Lync Server 2013</span></span>](lync-server-2013-daily-tasks.md)

  - [<span data-ttu-id="fe30b-111">Lync Server 2013의 주간 작업</span><span class="sxs-lookup"><span data-stu-id="fe30b-111">Weekly tasks in Lync Server 2013</span></span>](lync-server-2013-weekly-tasks.md)

  - [<span data-ttu-id="fe30b-112">Lync Server 2013의 월별 작업</span><span class="sxs-lookup"><span data-stu-id="fe30b-112">Monthly tasks in Lync Server 2013</span></span>](lync-server-2013-monthly-tasks.md)

  - [<span data-ttu-id="fe30b-113">Lync Server 2013의 필요에 따라 작업</span><span class="sxs-lookup"><span data-stu-id="fe30b-113">As-needed tasks in Lync Server 2013</span></span>](lync-server-2013-as-needed-tasks.md)

  - [<span data-ttu-id="fe30b-114">Lync Server 2013에 대 한 작업 검사 목록</span><span class="sxs-lookup"><span data-stu-id="fe30b-114">Operations checklists for Lync Server 2013</span></span>](lync-server-2013-operations-checklists.md)

  - [<span data-ttu-id="fe30b-115">System Center Operations Manager를 사용 하 여 Lync Server 2013 모니터링</span><span class="sxs-lookup"><span data-stu-id="fe30b-115">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)

  - [<span data-ttu-id="fe30b-116">Lync Server 2013의 작동 종속성</span><span class="sxs-lookup"><span data-stu-id="fe30b-116">Operational dependencies in Lync Server 2013</span></span>](lync-server-2013-operational-dependencies.md)

  - [<span data-ttu-id="fe30b-117">Lync Server 2013의 문제 해결 및 주요 상태 지표</span><span class="sxs-lookup"><span data-stu-id="fe30b-117">Troubleshooting and Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-and-key-health-indicators.md)

<span data-ttu-id="fe30b-118">Microsoft Lync Server 2013 배포가 완료 된 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe30b-118">It is assumed that your Microsoft Lync Server 2013 deployment is completed.</span></span> <span data-ttu-id="fe30b-119">그렇지 않은 경우 계속 하기 전에 Microsoft Lync Server 2013의 계획 및 배포 콘텐츠를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fe30b-119">If this is not the case, refer to the planning and deployment content for Microsoft Lync Server 2013 before you continue.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fe30b-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fe30b-120">See Also</span></span>


[<span data-ttu-id="fe30b-121">Lync Server 2013 시작</span><span class="sxs-lookup"><span data-stu-id="fe30b-121">Getting started with Lync Server 2013</span></span>](lync-server-2013-getting-started.md)  
[<span data-ttu-id="fe30b-122">Lync Server 2013 계획</span><span class="sxs-lookup"><span data-stu-id="fe30b-122">Planning for Lync Server 2013</span></span>](lync-server-2013-planning.md)  
[<span data-ttu-id="fe30b-123">Lync Server 2013 배포</span><span class="sxs-lookup"><span data-stu-id="fe30b-123">Deployment of Lync Server 2013</span></span>](lync-server-2013-deployment.md)  
[<span data-ttu-id="fe30b-124">Lync Server 2013 관리 셸</span><span class="sxs-lookup"><span data-stu-id="fe30b-124">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

