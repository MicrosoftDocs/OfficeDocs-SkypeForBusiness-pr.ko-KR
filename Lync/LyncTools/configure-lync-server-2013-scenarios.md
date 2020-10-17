---
title: Lync Server 2013 시나리오 구성
description: Lync Server 2013 시나리오를 구성 합니다.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 Scenarios
ms:assetid: 6705346b-1512-4af3-85e4-64dfa6ee6f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945596(v=OCS.15)
ms:contentKeyID: 51541420
ms.date: 12/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4a5b7bd271191067779ac358807cc54918b16bc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555464"
---
# <a name="configure-lync-server-2013-scenarios"></a><span data-ttu-id="fae00-103">Lync Server 2013 시나리오 구성</span><span class="sxs-lookup"><span data-stu-id="fae00-103">Configure Lync Server 2013 Scenarios</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fae00-104">_**마지막으로 수정 된 항목:** 2016-12-28_</span><span class="sxs-lookup"><span data-stu-id="fae00-104">_**Topic Last Modified:** 2016-12-28_</span></span>

<span data-ttu-id="fae00-105">Lync Server 2013 스트레스 및 성능 도구 (LyncPerfTool)를 실행 하려면 실행할 시나리오에 대해 Lync Server 2013 토폴로지를 먼저 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fae00-105">To run the Lync Server 2013 Stress and Performance Tool (LyncPerfTool), the Lync Server 2013 topology must first be configured for the scenarios that will be executed.</span></span> <span data-ttu-id="fae00-106">Lync Server 2013이 구성 되지 않았거나 잘못 구성 된 경우 대부분의 경우 부하 시뮬레이션이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="fae00-106">If Lync Server 2013 is not configured or is configured incorrectly, load simulation will fail in most cases.</span></span> <span data-ttu-id="fae00-107">Lync Server 2013 스트레스 및 성능 도구를 사용 하 여 lync server 2013 구성에 대 한 시작 점으로 사용할 수 있는 기본 리소스 파일 및 lync server 관리 셸 스크립트 예제를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fae00-107">With the Lync Server 2013 Stress and Performance Tool, we have provided example Lync Server Management Shell scripts and basic resource files that can be used as a starting point for configuring Lync Server 2013.</span></span> <span data-ttu-id="fae00-108">이 항목에서는 제공 되는 Windows PowerShell 예제에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fae00-108">This topic describes the Windows PowerShell examples provided.</span></span> <span data-ttu-id="fae00-109">Lync Server 2013을 일반적인 방식으로 구성 하는 방법을 설명 하는이 항목의 목표는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="fae00-109">Note that it is not the goal of this topic to describe how to configure Lync Server 2013 in general.</span></span> <span data-ttu-id="fae00-110">Lync Server 2013에서 Windows PowerShell을 사용 하는 방법에 대 한 자세한 내용은의 Lync Server Management Shell 설명서를 참조 하십시오 <https://technet.microsoft.com/library/gg398474.aspx> .</span><span class="sxs-lookup"><span data-stu-id="fae00-110">For details about working with Windows PowerShell in Lync Server 2013, see the Lync Server Management Shell documentation at <https://technet.microsoft.com/library/gg398474.aspx>.</span></span>

<div>

## <a name="about-running-lync-server-management-shell-scripts"></a><span data-ttu-id="fae00-111">Lync Server 관리 셸 스크립트 실행 정보</span><span class="sxs-lookup"><span data-stu-id="fae00-111">About Running Lync Server Management Shell Scripts</span></span>

<span data-ttu-id="fae00-112">예제에서는 부하 시뮬레이션 실행을 준비 하는 데 사용할 수 있는 Lync Server 관리 셸 스크립트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fae00-112">We have provided example Lync Server Management Shell scripts that may be used in preparation for running load simulation.</span></span> <span data-ttu-id="fae00-113">스크립트는 부하 시뮬레이션을 위한 것 이므로 간단 하 고 관대 하며, 따라서 프로덕션 환경에 적합 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fae00-113">Because the scripts are intended for load simulation, they are simple and permissive, and therefore may not be appropriate for production.</span></span> <span data-ttu-id="fae00-114">모든 스크립트는 예 이며 검토 해야 하며, 일부 경우에는 토폴로지를 반영 하도록 수정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fae00-114">All scripts are examples and must be reviewed, and, in some cases, modified to reflect your topology.</span></span> <span data-ttu-id="fae00-115">적어도 에이전트 그룹에 할당 된 에이전트를 지정 하려면 RGS (응답 그룹 서비스) 시나리오를 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fae00-115">At a minimum, we expect that the Response Group Service (RGS) scenario would need to be modified to specify the agents that are assigned to the agent groups.</span></span> <span data-ttu-id="fae00-116">그러나이 부하를 시뮬레이션할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fae00-116">However, you have the option to not simulate this load.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="fae00-117">제공 된 예제를 검토 하 고 이해 하는 데 주의 합니다.</span><span class="sxs-lookup"><span data-stu-id="fae00-117">Take care in reviewing and understanding the examples provided.</span></span> <span data-ttu-id="fae00-118">스크립트는 토폴로지의 모든 기존 설정을 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="fae00-118">Scripts will overwrite any existing settings in the topology.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="fae00-119">Windows PowerShell 및 Lync Server 관리 셸을 사용 하는 방법에 대 한 자세한 내용은 Lync Server 2013 Windows PowerShell Blog를 참조 하십시오 <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A> .</span><span class="sxs-lookup"><span data-stu-id="fae00-119">For details about using Windows PowerShell and the Lync Server Management Shell, see the Lync Server 2013 Windows PowerShell Blog at <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A>.</span></span>



</div>

</div>

<div>

## <a name="stress-and-performance-tool-client-version-monikers"></a><span data-ttu-id="fae00-120">스트레스 및 성능 도구 클라이언트 버전 모니커</span><span class="sxs-lookup"><span data-stu-id="fae00-120">Stress and Performance Tool Client Version Monikers</span></span>

<span data-ttu-id="fae00-121">설정을 기본값에서 변경한 경우에는 클라이언트 버전 검사 정책을 구성 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fae00-121">You may need to configure the Client Version Check policy if you have changed the settings from the default values.</span></span> <span data-ttu-id="fae00-122">자세한 내용은에서 "지원 되는 클라이언트 버전 구성"을 참조 하십시오 <https://technet.microsoft.com/library/gg412832(v=ocs.15).aspx> .</span><span class="sxs-lookup"><span data-stu-id="fae00-122">For details, see “Configuring supported client versions” at <https://technet.microsoft.com/library/gg412832(v=ocs.15).aspx>.</span></span> <span data-ttu-id="fae00-123">Lync server 2013을 사용 하 여 통신할 때 Lync 서버 2013 스트레스 및 성능 도구는 기본적으로 다음 사용자 에이전트 버전을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fae00-123">The Lync Server 2013 Stress and Performance Tool uses the following User Agent Versions by default when communicating with Lync Server 2013:</span></span>

  - <span data-ttu-id="fae00-124">LSPT/15.0.0.0입니다 (Lync Server 2013 스트레스 및 성능 도구)</span><span class="sxs-lookup"><span data-stu-id="fae00-124">LSPT/15.0.0.0 (Lync Server 2013 Stress and Performance Tool)</span></span>

  - <span data-ttu-id="fae00-125">OCPHONE/0.522</span><span class="sxs-lookup"><span data-stu-id="fae00-125">OCPHONE/.0.522</span></span>

<span data-ttu-id="fae00-126">다음은 LyncPerfTool 모바일 (이동) 클라이언트에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fae00-126">These are for the Mobility (UCWA) client in LyncPerfTool:</span></span>

  - <span data-ttu-id="fae00-127">C 및 wa Perf 도구/웹 회의</span><span class="sxs-lookup"><span data-stu-id="fae00-127">Ucwa Perf Tool/Web Conference</span></span>

  - <span data-ttu-id="fae00-128">C; 및 wa 성능 도구/모바일</span><span class="sxs-lookup"><span data-stu-id="fae00-128">Ucwa Perf Tool/Mobile</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

