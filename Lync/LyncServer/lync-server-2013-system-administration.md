---
title: 'Lync Server 2013: 시스템 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System administration
ms:assetid: 063eb962-b96a-4699-8579-bb7125112df4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720318(v=OCS.15)
ms:contentKeyID: 63969577
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e10f0d340ec0d291d0b184b8649f8f132683e08
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764284"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-administration-in-lync-server-2013"></a><span data-ttu-id="f8904-102">Lync Server 2013의 시스템 관리</span><span class="sxs-lookup"><span data-stu-id="f8904-102">System administration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8904-103">_**마지막으로 수정한 주제:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="f8904-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="f8904-104">시스템 관리에는 IT 시스템을 원활 하 게 운영 하는 데 필요한 일일 관리 작업이 계획 된 시간과 주문형 요청이 모두 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-104">System administration includes the day-to-day administrative tasks, both planned and on-demand, that are required to keep an IT system operating smoothly.</span></span> <span data-ttu-id="f8904-105">일반적으로 시스템 관리 작업에는 작성 절차가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-105">Typically, system administration tasks are covered by written procedures.</span></span> <span data-ttu-id="f8904-106">이러한 절차는 모든 지원 담당자가 동일한 표준 도구와 메서드를 사용 하도록 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-106">These procedures help ensure that the same standard tools and methods are used by all support staff.</span></span>

<span data-ttu-id="f8904-107">Lync 환경에서 일반적인 시스템 관리 작업에는 백업 및 보관, 로그 모니터링, 사용자 만들기 및 관리, 바이러스 백신 소프트웨어 업데이트 등이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-107">In a Lync environment, typical system administration tasks include backing up and archiving pools, monitoring logs, creating and managing users, and updating antivirus software.</span></span>

<div>

## <a name="system-troubleshooting"></a><span data-ttu-id="f8904-108">시스템 문제 해결</span><span class="sxs-lookup"><span data-stu-id="f8904-108">System troubleshooting</span></span>

<span data-ttu-id="f8904-109">조직에서 예기치 않은 문제를 처리할 수 있도록 준비 해야 하며, 문제가 해결 될 때까지 보고 되는 지점에서 문제를 관리 하는 절차가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-109">An organization must be prepared to deal with unexpected issues and should have a procedure to manage issues from the point at which they are reported until their resolution.</span></span> <span data-ttu-id="f8904-110">불필요 하 게 반복적으로 반복 되는 작업을 방지 하기 위해 문제를 진단 하는 지원 담당자에 게 기록 하 여 사용 하는 방법에 대 한 정보</span><span class="sxs-lookup"><span data-stu-id="f8904-110">Information about how support staff diagnosed an issue should be recorded and used in the future to avoid unnecessarily repeating completed work.</span></span>

</div>

<div>

## <a name="system-troubleshooting-process"></a><span data-ttu-id="f8904-111">시스템 문제 해결 프로세스</span><span class="sxs-lookup"><span data-stu-id="f8904-111">System troubleshooting process</span></span>

<span data-ttu-id="f8904-112">다음 다이어그램에서는 시스템 문제 해결 프로세스와 다른 운영 역할의 상호 작용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-112">The following diagram shows the system troubleshooting process and the interactions with other operations roles.</span></span>

<span data-ttu-id="f8904-113">**시스템 문제 해결 순서도**</span><span class="sxs-lookup"><span data-stu-id="f8904-113">**System troubleshooting flowchart**</span></span>

<span data-ttu-id="f8904-114">![시스템 문제 해결 순서도](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "시스템 문제 해결 순서도")</span><span class="sxs-lookup"><span data-stu-id="f8904-114">![System Troubleshooting Flowchart](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "System Troubleshooting Flowchart")</span></span>

  - <span data-ttu-id="f8904-115">**이 작업을 분류 하 고 우선 순위**   를 지정 하는 것은 일반적으로 서비스 데스크에서 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-115">**Classify and Prioritize**   This task is typically performed by the service desk.</span></span> <span data-ttu-id="f8904-116">예를 들어 문제가 소프트웨어 문제 또는 하드웨어 문제로 그룹화 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-116">For example, an issue may be grouped as a software issue or a hardware issue.</span></span> <span data-ttu-id="f8904-117">해당 문제는 조사를 위해 해당 지원 팀으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-117">The issue is then routed to the appropriate support team for investigation.</span></span> <span data-ttu-id="f8904-118">문제의 우선 순위를 결정 하는 규칙은 일반적으로 응답 시간 및 해결 시간을 포함 하 여 SLA에 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-118">The rules for determining the priority of an issue, together with the time to respond and time to resolve, are typically defined in the SLA.</span></span>

  - <span data-ttu-id="f8904-119">\*\*\*\*   문제를 진단 하 고 문제를 해결 하기 위해 변경 사항을 제안 하는 적절 한 지원 팀을 조사 하 고 진단 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-119">**Investigate and Diagnose**   The appropriate support team diagnoses the issue and proposes changes to resolve the issue.</span></span> <span data-ttu-id="f8904-120">솔루션이 간단 하 고 변경 제어가 필요 하지 않은 경우에는 해당 솔루션을 즉시 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-120">If the solution is simple and does not require change control, the solution can be applied immediately.</span></span> <span data-ttu-id="f8904-121">해결 방법이 쉽지 않은 경우 변경 요청이 발생 하 고 제안 된 작업을 변경 관리 프로세스에서 관리 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-121">If the solution is not easy, a request for change should be raised and the proposed work should be managed by the change management process, frequently under a “fast-track” procedure.</span></span> <span data-ttu-id="f8904-122">변경 사항은 구성 관리 프로세스를 사용 하 여 기록해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-122">Any changes that are made should be recorded using the configuration management process.</span></span>

  - <span data-ttu-id="f8904-123">**종료 및 녹음**   해결 방법을 테스트 한 후에는 문제를 종료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-123">**Close and Record**   After testing the resolution, the issue should be closed.</span></span> <span data-ttu-id="f8904-124">문제를 통해 알 수 있는 교훈을 얻은 경우 기술 자료에 항목을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-124">If there are lessons to be learned from the issue, an entry should be created in the knowledge base.</span></span>

  - <span data-ttu-id="f8904-125">\*\*\*\*   문제 추세를 식별 하기 위해 최근 문제의 검토 및 추세 분석 정기적 검토가 수행 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-125">**Review and Trend Analysis**   Periodic reviews of recent issues should be performed to identify issue trends.</span></span> <span data-ttu-id="f8904-126">예를 들어 사용자에 게 Lync 사이트에 대 한 느린 로그온 문제가 자주 발생 하는 경우 네트워크 대역폭 문제로 인해 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-126">For example, if the users are experiencing frequent issues with slow logons to their Lync sites, network bandwidth issues may be the cause.</span></span> <span data-ttu-id="f8904-127">문제 해결 시간 및 시스템 가용성에 대 한 중단의 영향을 SLA와 비교 하 여 검토 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-127">Issue resolution times and the effect of any outages on system availability should be reviewed and compared with the SLA.</span></span> <span data-ttu-id="f8904-128">계정 관리자와 같은 고객 서비스 문제를 liaises 하는 사람에 게 중요 한 문제에 대 한 정보를 알려 주어 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-128">The person who liaises with the customer on service issues, such as an account manager, should be informed of any significant issues.</span></span>

</div>

<div>

## <a name="issue-management-tools"></a><span data-ttu-id="f8904-129">문제점 관리 도구</span><span class="sxs-lookup"><span data-stu-id="f8904-129">Issue management tools</span></span>

<span data-ttu-id="f8904-130">직원은 서비스 데스크 도구를 사용 하 여 새 문제점을 기록, 분류 및 우선 순위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-130">Service desk tools enable staff to record, classify, and prioritize new issues.</span></span> <span data-ttu-id="f8904-131">그러면 도구는 여러 지원 팀에서 조사 및 진단을 통해 문제 서비스 요청을 관리 하는 워크플로 프로세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-131">Tools will then provide the workflow processes to manage the issue service request through investigation and diagnosis, often by more than one support team.</span></span> <span data-ttu-id="f8904-132">해결 시간과 기록 추세에 대 한 보고서를 자주 제공 하는 도구는 과거 문제를 검색 하는 데 사용할 수 있는 기술 자료 데이터베이스를 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-132">Tools, which will frequently provide reports about resolution times and historical trends, may also include a knowledge base database, which can be used to search through past issues.</span></span>

<span data-ttu-id="f8904-133">Microsoft 기술 자료는 Microsoft에서 발생 한 지원 문제에 대 한 유용한 기록입니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-133">The Microsoft Knowledge Base is a useful record of support issues that were encountered by Microsoft.</span></span> <span data-ttu-id="f8904-134">자세한 내용은 Microsoft 지원 웹 사이트 (<http://go.microsoft.com/fwlink/?linkid=14898>)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f8904-134">For more information, see the Microsoft Support website (<http://go.microsoft.com/fwlink/?linkid=14898>).</span></span>

<span data-ttu-id="f8904-135">일반적으로 타사 소프트웨어는 팀 구성, 보고 요구 사항, SLA에 필요한 측정값 등 조직의 요구에 맞게 사용자 지정이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-135">Third-party software typically requires customization to suit the organization’s needs, such as the organization of teams, reporting requirements, and measures required by the SLA.</span></span>

</div>

<div>

## <a name="centralized-vs-decentralized-administration"></a><span data-ttu-id="f8904-136">중앙 집중화 및 분산 관리</span><span class="sxs-lookup"><span data-stu-id="f8904-136">Centralized vs. decentralized administration</span></span>

<span data-ttu-id="f8904-137">시스템 관리 작업을 수행 하는 데 필요한 역할 및 책임은 조직이 중앙 집중화 된 모델, 분산 모델 또는 둘 다의 조합을 따르는지 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-137">Roles and responsibilities for performing system administration tasks depend on whether the organization follows a centralized model, a decentralized model, or a combination of both.</span></span>

  - <span data-ttu-id="f8904-138">**중앙 집중화**   된 모델에서 하나 또는 여러 개의 관리 그룹이 전체 Lync Server 환경에 대 한 완벽 한 제어권을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-138">**Centralized Model**   In a centralized model, one or several administrative groups maintain complete control of the whole Lync Server environment.</span></span> <span data-ttu-id="f8904-139">이 관리 모델은 모든 관리 작업을 단일 정보 기술 그룹에서 수행 하는 데이터 센터와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-139">This administrative model resembles a data center where all administration tasks are performed by a single information technology group.</span></span> <span data-ttu-id="f8904-140">팀 내에서 역할과 책임은 경험과 전문성에 따라 정의 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-140">Roles and responsibilities within the team should be defined according to experience and expertise.</span></span>

  - <span data-ttu-id="f8904-141">**분산 모델**   분산 조직은 여러 지리적 위치에 있으며, 다양 한 위치에서 Lync Server 서버와 관리자 팀이 작동 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-141">**Decentralized Model**   Decentralized organizations are located in several geographic locations and have functioning Lync Server servers and teams of administrators in different locations.</span></span> <span data-ttu-id="f8904-142">예를 들어 로컬 관리 직원과 각 국가/지역에 대해 Lync Server 2013을 실행 하는 서버가 하나 이상 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-142">For example, there may be local administration staff and one or more servers that are running Lync Server 2013 for each country/region.</span></span> <span data-ttu-id="f8904-143">또는 Lync Server 2013를 실행 하는 서버 풀과 북미 용 관리 팀이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-143">Or, there may be a pool of servers that are running Lync Server 2013 and an administrative team for North America and one for Europe.</span></span> <span data-ttu-id="f8904-144">경우에 따라 관리자가 자신의 지리적 영역에만 책임을 지 고 다른 영역의 리소스를 관리 하는 권한을 제한 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-144">Sometimes, you may want administrators to be responsible only for their own geographical area and restrict permissions to administer resources in other areas.</span></span>

<span data-ttu-id="f8904-145">또한 Lync Server를 사용 하 여 특정 관리 작업을 특정 사용자 또는 그룹에 위임할 수 있습니다 (RBAC (역할 기반 액세스 제어)).</span><span class="sxs-lookup"><span data-stu-id="f8904-145">Lync Server also allows you to delegate specific administrative tasks to specific people or groups by using role-based access control (RBAC).</span></span> <span data-ttu-id="f8904-146">관리자는 RBAC를 사용 하 여 다른 관리자에 게 특정 사용자 권한 및 사용 권한을 위임 하 여 가능 하면 관리 작업의 하위 집합을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-146">RBAC allows administrators to delegate specific user rights and permissions to other administrators to perform a subset of the administrative tasks possible.</span></span> <span data-ttu-id="f8904-147">RBAC를 사용 하 여 특정 관리 작업을 수행할 수 있는 기능은 사용자에 게 할당 된 RBAC 역할에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-147">By using RBAC, the user’s ability to perform specific administrative tasks depends on the RBAC roles that are assigned to the user.</span></span> <span data-ttu-id="f8904-148">RBAC는 사용자가 구성원으로 속해 있는 RBAC 역할을 기준으로 실행할 수 있는 cmdlet 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8904-148">RBAC provides a list of cmdlets that the user can run based on the RBAC roles that the user is a member of.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

