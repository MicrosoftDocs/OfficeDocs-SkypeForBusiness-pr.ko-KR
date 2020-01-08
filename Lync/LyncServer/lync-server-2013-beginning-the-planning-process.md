---
title: 'Lync Server 2013: 계획 프로세스 시작'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Beginning the planning process
ms:assetid: df3722b3-f859-49e1-b3ff-ee6863483731
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398986(v=OCS.15)
ms:contentKeyID: 48185618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 582769109a3792ddc2efdbef5d4a557b781c39b8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="beginning-the-planning-process-for-lync-server-2013"></a><span data-ttu-id="82448-102">Lync Server 2013에 대한 계획 프로세스 시작</span><span class="sxs-lookup"><span data-stu-id="82448-102">Beginning the planning process for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82448-103">_**마지막으로 수정한 주제:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="82448-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="82448-104">온-프레미스 통합 커뮤니케이션 배포 계획은 매우 어렵게 보일 수 있지만, Lync Server는 다음 두 가지 유용한 도구를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="82448-104">While planning an on-premises unified communications deployment may seem intimidating, Lync Server provides two valuable tools to help you:</span></span>

  - <span data-ttu-id="82448-105">**계획 도구** 는 조직, 사용 하려는 Lync Server 기능, 용량 계획 요구 사항에 대 한 일련의 질문을 제공 하는 마법사입니다.</span><span class="sxs-lookup"><span data-stu-id="82448-105">**The Planning Tool** is a wizard that presents a series of questions about your organization, the Lync Server features that you want to enable, and your capacity planning needs.</span></span> <span data-ttu-id="82448-106">그런 다음 답변에 따라 권장 되는 배포 토폴로지를 만들고이 배포의 Microsoft Visio 다이어그램을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="82448-106">It then creates a recommended deployment topology based on your answers, and produces a Microsoft Visio diagram of this deployment.</span></span>

  - <span data-ttu-id="82448-107">**토폴로지 작성기** 는 Lync Server의 설치 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="82448-107">**Topology Builder** is an installation component of Lync Server.</span></span> <span data-ttu-id="82448-108">토폴로지 작성기를 사용 하 여 계획 된 토폴로지를 만들고, 조정 하 고, 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="82448-108">You use Topology Builder to create, adjust, and publish your planned topology.</span></span> <span data-ttu-id="82448-109">또한 서버 설치를 시작 하기 전에 토폴로지의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="82448-109">It also validates your topology before you begin server installations.</span></span> <span data-ttu-id="82448-110">개별 서버에 Lync Server를 설치 하는 경우 서버는 설치 프로세스의 일부로 게시 된 토폴로지를 읽고, 설치 프로그램은 토폴로지에서 지시한 대로 서버를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="82448-110">When you install Lync Server on individual servers, the servers read the published topology as part of the installation process, and the installation program deploys the server as directed in the topology.</span></span>

<div>

## <a name="lync-server-planning-tool"></a><span data-ttu-id="82448-111">Lync Server 계획 도구</span><span class="sxs-lookup"><span data-stu-id="82448-111">Lync Server Planning Tool</span></span>

<span data-ttu-id="82448-112">계획 도구는 도구에서 질문에 대 한 답변을 가져와 Lync Server 지침 및 모범 사례에 따라 토폴로지를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="82448-112">The Planning Tool takes your answers to the questions in the tool and generates a topology based on Lync Server guidelines and best practices.</span></span> <span data-ttu-id="82448-113">또한 사용자의 답변에 따라 배포에 대 한 여러 가지 보기를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="82448-113">It also provides several views of a deployment based on your answers.</span></span> <span data-ttu-id="82448-114">모든 사이트의 전역 보기 (즉, 중앙 사이트와 분기 사이트 모두 포함)와 각 사이트의 서버 및 기타 구성 요소를 보여 주는 자세히 보기를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="82448-114">It shows both a global view of all your sites (that is, including both central sites and branch sites), and detailed views showing the servers and other components at each site.</span></span>

<span data-ttu-id="82448-115">계획 도구를 실행 해도 특정 배포에 대 한 사용자를 커밋하거나 프로세스를 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="82448-115">Running the Planning Tool does not commit you to any specific deployment or initiate any processes.</span></span> <span data-ttu-id="82448-116">사실 기업 계획을 염두에 두어야 하기 전에 계획 도구를 실행 하는 것은 계획 프로세스에서 고려해 야 할 질문의 종류를 이해 하는 데 매우 유용 하 게 사용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82448-116">In fact, running the Planning Tool even before you have a firm plan in mind can be a very instructive way to understand the kinds of questions you need to think about in your planning process.</span></span>

<span data-ttu-id="82448-117">계획 도구를 여러 번 실행 하 고, 질문에 대 한 답변을 다르게 표시 하 고, 결과를 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82448-117">You can run the Planning Tool multiple times, answering questions differently, and compare the outcomes.</span></span> <span data-ttu-id="82448-118">가장 만족 스 러 우면 변경 해야 하는 경우에는 계획 도구로 돌아가서 디자인을 로드 하 고 변경 내용을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82448-118">If you have a design you are mostly satisfied with but that you need to make changes to, you can return to the Planning Tool, load the design, and make the changes.</span></span> <span data-ttu-id="82448-119">계획 도구를 한 번 완료 하는 데 약 15 분이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="82448-119">It takes about 15 minutes to complete the Planning Tool once.</span></span>

<span data-ttu-id="82448-120">만족 스 러 우면 계획 도구를 사용 하 여 계획 된 배포의 다이어그램을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82448-120">After you are satisfied, you can use the Planning Tool to create a diagram of your planned deployment.</span></span> <span data-ttu-id="82448-121">토폴로지 작성기에서 배포를 만드는 동안이 다이어그램을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82448-121">You can use this diagram while creating the deployment in Topology Builder.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="82448-122">Lync Server 2013의이 릴리스에 포함 된 계획 도구는 시험판 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="82448-122">The Planning Tool included with this release of Lync Server 2013 is a prerelease version.</span></span> <span data-ttu-id="82448-123">계획 도구의 용량 계획 번호는 확정 된 것으로, 최종 릴리스에서는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="82448-123">Note that the capacity planning numbers in the Planning Tool are preliminary and are not supported for the final release.</span></span>



</div>

</div>

<div>

## <a name="lync-server-topology-builder"></a><span data-ttu-id="82448-124">Lync Server 토폴로지 작성기</span><span class="sxs-lookup"><span data-stu-id="82448-124">Lync Server Topology Builder</span></span>

<span data-ttu-id="82448-125">배포 계획을 결정 한 후에는 토폴로지 작성기를 사용 하 여 배포를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="82448-125">Once you have decided on your deployment plan, you use Topology Builder to begin deploying.</span></span> <span data-ttu-id="82448-126">완료 되 면 토폴로지 작성기를 사용 하 여 토폴로지 유효성을 검사 한 다음이를 통과 하면 토폴로지를 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82448-126">When finished, you use Topology Builder to validate the topology, and then, if it passes, you can publish the topology.</span></span> <span data-ttu-id="82448-127">토폴로지를 게시 하면 Lync Server가 중앙 관리 저장소에 토폴로지를 배치 합니다 (아직 존재 하지 않는 경우에는 지금 생성 됨).</span><span class="sxs-lookup"><span data-stu-id="82448-127">When you publish the topology, Lync Server puts the topology into the Central Management store, which is created at this time if it does not already exist.</span></span> <span data-ttu-id="82448-128">배포의 각 서버에 Lync Server를 설치 하는 경우 서버는 중앙 관리 저장소에서 토폴로지를 읽고 배포의 역할에 맞게 자체 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="82448-128">When you install Lync Server on each server in your deployment, the server reads the topology from the Central Management store and installs itself to fit into its role in your deployment.</span></span>

<span data-ttu-id="82448-129">또는 Lync Server에 대해 잘 알고 있고 더 적은 규범적인 지침이 필요한 경우 계획 도구를 건너뛰고 토폴로지 작성기의 마법사를 사용 하 여 배포의 초기 디자인 및 유효성 검사 및 게시 단계를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82448-129">Alternatively, if you are very familiar with Lync Server and need less prescriptive guidance, you can skip the Planning Tool and use the wizards in Topology Builder for the initial design of your deployment and also for the validation and publishing steps.</span></span>

<span data-ttu-id="82448-130">토폴로지 작성기를 사용 하 여 토폴로지를 계획 하 고 게시 하는 것은 필수 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="82448-130">Using Topology Builder to plan and publish a topology is a required step.</span></span> <span data-ttu-id="82448-131">배포의 서버에서 토폴로지 작성기를 우회 하 고 Lync Server를 개별적으로 설치할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="82448-131">You cannot bypass Topology Builder and install Lync Server individually on the servers in your deployment.</span></span> <span data-ttu-id="82448-132">각 서버는 중앙 관리 저장소의 유효성을 검사 하 고 게시 된 토폴로지에서 토폴로지를 읽어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82448-132">Each server must read the topology from a validated, published topology in the Central Management store.</span></span>

</div>

<div>

## <a name="high-level-planning-process"></a><span data-ttu-id="82448-133">상위 수준 계획 프로세스</span><span class="sxs-lookup"><span data-stu-id="82448-133">High-Level Planning Process</span></span>

<span data-ttu-id="82448-134">Lync Server 배포를 계획 하기 위해 설명서와 계획 도구를 모두 사용 하는 일반적인 프로세스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="82448-134">We recommend the following general process for using both the documentation and the Planning Tool to plan your Lync Server deployment.</span></span>

1.  <span data-ttu-id="82448-135">이전 버전의 Lync Server에 익숙한 경우 lync server [2013의 새로운 기능](lync-server-2013-new-features.md) 을 읽어 lync server 2013의 새로운 기능과 요구 사항을 숙지 하세요.</span><span class="sxs-lookup"><span data-stu-id="82448-135">If you are familiar with previous versions of Lync Server, read [New features in Lync Server 2013](lync-server-2013-new-features.md) to familiarize yourself with the new features and requirements in Lync Server 2013.</span></span>

2.  <span data-ttu-id="82448-136">설명서의이 섹션에서 다른 주제 ( [Lync server 2013에 대 한 계획 수립 하기 전에 알아야 할 사항](lync-server-2013-topology-basics-you-must-know-before-planning.md), lync server [2013의 참조 토폴로지](lync-server-2013-reference-topologies.md), [lync server 2013에 대 한 초기 계획 결정](lync-server-2013-initial-planning-decisions.md), [lync server 2013에](lync-server-2013-clients.md)대 한 클라이언트를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="82448-136">Read the other topics in this section of the documentation: [Topology basics you must know before planning for Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md), [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md), [Initial planning decisions for Lync Server 2013](lync-server-2013-initial-planning-decisions.md), and [Clients for Lync Server 2013](lync-server-2013-clients.md).</span></span> <span data-ttu-id="82448-137">[Lync Server 2013의 참조 토폴로지에](lync-server-2013-reference-topologies.md)표시 된 계획 결정을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="82448-137">Note the planning decisions represented in [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md).</span></span>

3.  <span data-ttu-id="82448-138">Lync Server 기능 및 답변 해야 할 질문의 종류에 대해 자세히 알아보고 계획 도구를 실행 하 고 결과 토폴로지와 해당 세부 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="82448-138">Now that you are more familiar with Lync Server features and the kinds of questions that must be answered, run the Planning Tool and view the resulting topology and its details.</span></span> <span data-ttu-id="82448-139">토폴로지가 조직의 고유한 요구 사항에 맞는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="82448-139">Make sure that the topology fits the unique requirements for your organization.</span></span>

4.  <span data-ttu-id="82448-140">관심 있는 특정 작업 또는 기능이 있거나 필요한 경우에는 [Lync Server 2013에 대 한](lync-server-2013-planning.md)적절 한 계획 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="82448-140">If there are particular workloads or features you are interested in or need to learn about, read the appropriate sections of [Planning for Lync Server 2013](lync-server-2013-planning.md).</span></span>

5.  <span data-ttu-id="82448-141">계획 도구를 다시 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="82448-141">Run the Planning Tool again.</span></span> <span data-ttu-id="82448-142">3 단계에서 만든 배포로 시작 하 고, 결과를 수정 하거나, 처음부터 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82448-142">You can start with the deployment you created in step 3 and modify the results, or start over from the beginning.</span></span>
    
    <span data-ttu-id="82448-143">필요한 경우 계획 도구를 세 번째로 실행 하 고 출력이 만족할 때까지 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="82448-143">If needed, run the Planning Tool a third time and repeat until you are satisfied with the output.</span></span>

6.  <span data-ttu-id="82448-144">토폴로지 계획을 완성 한 경우 계획 도구를 사용 하 여 토폴로지의 Visio 다이어그램을 만들고 인쇄할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82448-144">When you have finalized the topology plan, use Planning Tool to create and print a Visio diagram of your topology.</span></span> <span data-ttu-id="82448-145">토폴로지 작성기 작업 중에이 인쇄물을 사용 하 여 토폴로지를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82448-145">You can use this printout while working with Topology Builder to input your topology.</span></span>

7.  <span data-ttu-id="82448-146">배포를 시작 하기 전에 lync server [2013의 시스템 요구 사항을 확인](lync-server-2013-determining-your-system-requirements.md) 하 고 lync server 2013에 대 한 [인프라 요구 사항을](lync-server-2013-determining-your-infrastructure-requirements.md) 확인 하 여 lync server의 필수 구성 요소와 필요한 인프라에 대해 숙지 합니다.</span><span class="sxs-lookup"><span data-stu-id="82448-146">Before you begin deployment, read [Determining your system requirements for Lync Server 2013](lync-server-2013-determining-your-system-requirements.md) and [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) to familiarize yourself with the prerequisites and necessary infrastructure for Lync Server.</span></span> <span data-ttu-id="82448-147">또한 배포 하려는 작업 부하와 기능에 적용 되는 [Lync Server 2013에 대 한 모든 계획](lync-server-2013-planning.md) 섹션을 읽어 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82448-147">Additionally, be sure you have read all the sections of [Planning for Lync Server 2013](lync-server-2013-planning.md) that apply to the workloads and features that you plan to deploy.</span></span>

</div>

<div>

## <a name="migrating-from-previous-versions"></a><span data-ttu-id="82448-148">이전 버전에서 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="82448-148">Migrating from Previous Versions</span></span>

<span data-ttu-id="82448-149">이전 버전에서 Lync 서버로 마이그레이션하는 [경우 마이그레이션 및](migration.md) 배포에 대 한 특정 지침을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="82448-149">If you are migrating to Lync Server from a previous version, see the [Migration](migration.md) documentation for specific instructions for your migration and deployment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

