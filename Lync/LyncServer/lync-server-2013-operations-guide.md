---
title: 'Lync Server 2013: 운영 가이드'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Operations Guide
ms:assetid: dcb9ddff-6fe3-4077-a2e3-0ba64f65e264
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720467(v=OCS.15)
ms:contentKeyID: 63969658
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1259a66c4f7471538939a51610018e19231104c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980249"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="operations-guide-for-lync-server-2013"></a><span data-ttu-id="7738b-102">Operations Guide for Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7738b-102">Operations Guide for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7738b-103">_**마지막으로 수정한 주제:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="7738b-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="7738b-104">이 문서에서는 Microsoft Lync Server 2013 통신 소프트웨어 환경을 유지 관리 하는 데 필요한 운영 프로세스, 작업 및 도구에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7738b-104">This document describes the operational processes, tasks, and tools that are required for you to maintain a Microsoft Lync Server 2013 communications software environment.</span></span> <span data-ttu-id="7738b-105">이 문서에서는 Microsoft MOF (운영 프레임 워크) 모델에 따라 Lync Server 2013을 관리 하는 방법에 대해 설명 하 고, 일정을 관리 하는 프로세스 및 절차를 구현 하는 효율적인 운영 관리 환경을 디자인 하는 데 도움이 됩니다. 효율적인 작업 환경.</span><span class="sxs-lookup"><span data-stu-id="7738b-105">It explains how to manage Lync Server 2013 according to the Microsoft Operations Framework (MOF) model and it will help you design an efficient operational management environment, which includes implementing schedules, processes and procedures to maintain an efficient working environment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7738b-106">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="7738b-106">In This Section</span></span>

<span data-ttu-id="7738b-107">포함 되는 섹션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7738b-107">The following sections are included:</span></span>

  - [<span data-ttu-id="7738b-108">Lync Server 2013 환경에 대 한 모범 사례</span><span class="sxs-lookup"><span data-stu-id="7738b-108">Best practices for Lync Server 2013 environments</span></span>](lync-server-2013-best-practices-for-lync-server-environments.md)

  - [<span data-ttu-id="7738b-109">Lync Server 2013의 일별 작업</span><span class="sxs-lookup"><span data-stu-id="7738b-109">Daily tasks in Lync Server 2013</span></span>](lync-server-2013-daily-tasks.md)

  - [<span data-ttu-id="7738b-110">Lync Server 2013의 주별 작업</span><span class="sxs-lookup"><span data-stu-id="7738b-110">Weekly tasks in Lync Server 2013</span></span>](lync-server-2013-weekly-tasks.md)

  - [<span data-ttu-id="7738b-111">Lync Server 2013의 월별 작업</span><span class="sxs-lookup"><span data-stu-id="7738b-111">Monthly tasks in Lync Server 2013</span></span>](lync-server-2013-monthly-tasks.md)

  - [<span data-ttu-id="7738b-112">Lync Server 2013의 필요에 따라 작업</span><span class="sxs-lookup"><span data-stu-id="7738b-112">As-needed tasks in Lync Server 2013</span></span>](lync-server-2013-as-needed-tasks.md)

  - [<span data-ttu-id="7738b-113">Lync Server 2013에 대 한 작업 검사 목록</span><span class="sxs-lookup"><span data-stu-id="7738b-113">Operations checklists for Lync Server 2013</span></span>](lync-server-2013-operations-checklists.md)

  - [<span data-ttu-id="7738b-114">System Center Operations Manager를 사용 하 여 Lync Server 2013 모니터링</span><span class="sxs-lookup"><span data-stu-id="7738b-114">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)

  - [<span data-ttu-id="7738b-115">Lync Server 2013의 운영 의존 관계</span><span class="sxs-lookup"><span data-stu-id="7738b-115">Operational dependencies in Lync Server 2013</span></span>](lync-server-2013-operational-dependencies.md)

  - [<span data-ttu-id="7738b-116">Lync Server 2013의 문제 해결 및 주요 상태 표시기</span><span class="sxs-lookup"><span data-stu-id="7738b-116">Troubleshooting and Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-and-key-health-indicators.md)

<span data-ttu-id="7738b-117">Microsoft Lync Server 2013 배포가 완료 되었다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7738b-117">It is assumed that your Microsoft Lync Server 2013 deployment is completed.</span></span> <span data-ttu-id="7738b-118">그렇지 않은 경우 계속 하기 전에 Microsoft Lync Server 2013 계획 및 배포 콘텐츠를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7738b-118">If this is not the case, refer to the planning and deployment content for Microsoft Lync Server 2013 before you continue.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7738b-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7738b-119">See Also</span></span>


[<span data-ttu-id="7738b-120">Lync Server 2013 시작</span><span class="sxs-lookup"><span data-stu-id="7738b-120">Getting started with Lync Server 2013</span></span>](lync-server-2013-getting-started.md)  
[<span data-ttu-id="7738b-121">Lync Server 2013에 대 한 계획</span><span class="sxs-lookup"><span data-stu-id="7738b-121">Planning for Lync Server 2013</span></span>](lync-server-2013-planning.md)  
[<span data-ttu-id="7738b-122">Lync Server 2013 배포</span><span class="sxs-lookup"><span data-stu-id="7738b-122">Deployment of Lync Server 2013</span></span>](lync-server-2013-deployment.md)  
[<span data-ttu-id="7738b-123">Lync Server 2013 관리 셸</span><span class="sxs-lookup"><span data-stu-id="7738b-123">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

