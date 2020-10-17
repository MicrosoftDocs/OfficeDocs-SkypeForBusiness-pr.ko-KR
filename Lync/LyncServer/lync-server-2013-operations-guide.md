---
title: 'Lync Server 2013: 운영 가이드'
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
ms.openlocfilehash: 212a640577d55e80225a597c9263b7a2573d257f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524535"
---
# <a name="operations-guide-for-lync-server-2013"></a><span data-ttu-id="bb171-102">Lync Server 2013에 대 한 운영 가이드</span><span class="sxs-lookup"><span data-stu-id="bb171-102">Operations Guide for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb171-103">_**마지막으로 수정 된 항목:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="bb171-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="bb171-104">이 문서에서는 Microsoft Lync Server 2013 통신 소프트웨어 환경을 유지 관리 하는 데 필요한 운영 프로세스, 작업 및 도구에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb171-104">This document describes the operational processes, tasks, and tools that are required for you to maintain a Microsoft Lync Server 2013 communications software environment.</span></span> <span data-ttu-id="bb171-105">또한 MOF (Microsoft Operations Framework) 모델에 따라 Lync Server 2013를 관리 하는 방법에 대해 설명 하 고, 효율적인 작업 환경을 유지 관리 하기 위한 일정, 프로세스 및 절차를 구현 하는 효율적인 운영 관리 환경을 디자인 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb171-105">It explains how to manage Lync Server 2013 according to the Microsoft Operations Framework (MOF) model and it will help you design an efficient operational management environment, which includes implementing schedules, processes and procedures to maintain an efficient working environment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bb171-106">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="bb171-106">In This Section</span></span>

<span data-ttu-id="bb171-107">다음 섹션이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb171-107">The following sections are included:</span></span>

  - [<span data-ttu-id="bb171-108">Lync Server 2013 환경에 대 한 모범 사례</span><span class="sxs-lookup"><span data-stu-id="bb171-108">Best practices for Lync Server 2013 environments</span></span>](lync-server-2013-best-practices-for-lync-server-environments.md)

  - [<span data-ttu-id="bb171-109">Lync Server 2013의 일별 작업</span><span class="sxs-lookup"><span data-stu-id="bb171-109">Daily tasks in Lync Server 2013</span></span>](lync-server-2013-daily-tasks.md)

  - [<span data-ttu-id="bb171-110">Lync Server 2013의 주간 작업</span><span class="sxs-lookup"><span data-stu-id="bb171-110">Weekly tasks in Lync Server 2013</span></span>](lync-server-2013-weekly-tasks.md)

  - [<span data-ttu-id="bb171-111">Lync Server 2013의 월별 작업</span><span class="sxs-lookup"><span data-stu-id="bb171-111">Monthly tasks in Lync Server 2013</span></span>](lync-server-2013-monthly-tasks.md)

  - [<span data-ttu-id="bb171-112">Lync Server 2013의 필요에 따라 작업</span><span class="sxs-lookup"><span data-stu-id="bb171-112">As-needed tasks in Lync Server 2013</span></span>](lync-server-2013-as-needed-tasks.md)

  - [<span data-ttu-id="bb171-113">Lync Server 2013에 대 한 작업 검사 목록</span><span class="sxs-lookup"><span data-stu-id="bb171-113">Operations checklists for Lync Server 2013</span></span>](lync-server-2013-operations-checklists.md)

  - [<span data-ttu-id="bb171-114">System Center Operations Manager를 사용 하 여 Lync Server 2013 모니터링</span><span class="sxs-lookup"><span data-stu-id="bb171-114">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)

  - [<span data-ttu-id="bb171-115">Lync Server 2013의 작동 종속성</span><span class="sxs-lookup"><span data-stu-id="bb171-115">Operational dependencies in Lync Server 2013</span></span>](lync-server-2013-operational-dependencies.md)

  - [<span data-ttu-id="bb171-116">Lync Server 2013의 문제 해결 및 주요 상태 지표</span><span class="sxs-lookup"><span data-stu-id="bb171-116">Troubleshooting and Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-and-key-health-indicators.md)

<span data-ttu-id="bb171-117">Microsoft Lync Server 2013 배포가 완료 된 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb171-117">It is assumed that your Microsoft Lync Server 2013 deployment is completed.</span></span> <span data-ttu-id="bb171-118">그렇지 않은 경우 계속 하기 전에 Microsoft Lync Server 2013의 계획 및 배포 콘텐츠를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bb171-118">If this is not the case, refer to the planning and deployment content for Microsoft Lync Server 2013 before you continue.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bb171-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bb171-119">See Also</span></span>


[<span data-ttu-id="bb171-120">Lync Server 2013 시작</span><span class="sxs-lookup"><span data-stu-id="bb171-120">Getting started with Lync Server 2013</span></span>](lync-server-2013-getting-started.md)  
[<span data-ttu-id="bb171-121">Lync Server 2013 계획</span><span class="sxs-lookup"><span data-stu-id="bb171-121">Planning for Lync Server 2013</span></span>](lync-server-2013-planning.md)  
[<span data-ttu-id="bb171-122">Lync Server 2013 배포</span><span class="sxs-lookup"><span data-stu-id="bb171-122">Deployment of Lync Server 2013</span></span>](lync-server-2013-deployment.md)  
[<span data-ttu-id="bb171-123">Lync Server 2013 관리 셸</span><span class="sxs-lookup"><span data-stu-id="bb171-123">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

