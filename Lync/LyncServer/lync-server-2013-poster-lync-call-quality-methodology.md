---
title: 'Lync Server 2013: 포스터: Lync 통화 품질 방법론'
description: 'Lync Server 2013: 포스터: Lync 통화 품질 방법론'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Poster: Lync Call Quality Methodology'
ms:assetid: a069f4e5-4f80-4f0f-8657-2e07276b6b41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593600(v=OCS.15)
ms:contentKeyID: 61084874
ms.date: 06/24/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0db34da35ce32d32aa00f10cd3523a0f508f8ffd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566334"
---
# <a name="lync-call-quality-methodology-in-lync-server-2013"></a><span data-ttu-id="872b6-103">Lync Server 2013의 lync 통화 품질 방법론</span><span class="sxs-lookup"><span data-stu-id="872b6-103">Lync Call Quality Methodology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="872b6-104">_**마지막으로 수정 된 항목:** 2016-06-24_</span><span class="sxs-lookup"><span data-stu-id="872b6-104">_**Topic Last Modified:** 2016-06-24_</span></span>

<span data-ttu-id="872b6-105">이 문서는 다운로드 센터에서 다운로드할 수 있는 [Lync 통화 품질 방법론](https://go.microsoft.com/fwlink/?linkid=391841) 포스터와 함께 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-105">This article is a companion to the [Lync Call Quality Methodology](https://go.microsoft.com/fwlink/?linkid=391841) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="872b6-106">![CQM 프로세스를 설명 하는 포스터](images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg "CQM 프로세스를 설명 하는 포스터")</span><span class="sxs-lookup"><span data-stu-id="872b6-106">![Poster describing the CQM process](images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg "Poster describing the CQM process")</span></span>

<span data-ttu-id="872b6-107">이 포스터를 사용 하 여 CQM에 대해 자세히 알아볼 수 있으며, Lync 2013 및 2010에 대 한 통화 품질 방법론은 enterprise voice 기능을 포함 하는 Lync 구현에 대 한 통화 품질 및 사용자 환경에 영향을 주는 문제를 파악 하 고 해결할 수도 있습니다</span><span class="sxs-lookup"><span data-stu-id="872b6-107">You can use this poster to learn about CQM, the Call Quality Methodology for Lync 2013 and 2010 that helps you find and eliminate issues affecting call quality and user experience for Lync implementations that include enterprise voice features.</span></span> <span data-ttu-id="872b6-108">통화 품질 방법론은 Lync에서 enterprise voice services를 개선 하기 위한 노력을 보다 효율적으로 수행할 수 있는 새로운 문제 해결 및 서비스 관리 프레임 워크입니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-108">Call Quality Methodology is a new troubleshooting and service management framework that can better focus efforts to improve enterprise voice services in Lync.</span></span> <span data-ttu-id="872b6-109">이 문서에서는 CQM, 모니터링 되는 서버 및 솔루션의 종류, 그리고 수집한 원격 분석 데이터로 수행할 작업에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-109">In this article, you can learn more about CQM, the kinds of servers and solutions that are monitored, and what to do with the collected telemetry data.</span></span>

<span data-ttu-id="872b6-110">CQM을 사용 하는 방법에 대 한 질문이 있는 경우 cqmfeedback@microsoft.com에 게 질문을 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-110">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="872b6-111">포스터는 다음 영역에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-111">The poster explains the following areas:</span></span>

  - <span data-ttu-id="872b6-112">Lync CQM 란?</span><span class="sxs-lookup"><span data-stu-id="872b6-112">What is Lync CQM?</span></span>

  - <span data-ttu-id="872b6-113">우선 순위: 추세 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="872b6-113">Prioritize: Run Trending Queries</span></span>

  - <span data-ttu-id="872b6-114">.PCD</span><span class="sxs-lookup"><span data-stu-id="872b6-114">PCD</span></span>

  - <span data-ttu-id="872b6-115">관리/비관리</span><span class="sxs-lookup"><span data-stu-id="872b6-115">Managed/Unmanaged</span></span>

  - <span data-ttu-id="872b6-116">서버 플랜트도로</span><span class="sxs-lookup"><span data-stu-id="872b6-116">The Server Plant Road</span></span>

  - <span data-ttu-id="872b6-117">마지막 마일도로</span><span class="sxs-lookup"><span data-stu-id="872b6-117">The Last Mile Road</span></span>

  - <span data-ttu-id="872b6-118">끝점도로</span><span class="sxs-lookup"><span data-stu-id="872b6-118">The End Points Road</span></span>

  - <span data-ttu-id="872b6-119">서비스 관리</span><span class="sxs-lookup"><span data-stu-id="872b6-119">Service Management</span></span>

  - <span data-ttu-id="872b6-120">보드 게임 규칙</span><span class="sxs-lookup"><span data-stu-id="872b6-120">Board Game Rules</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-is-lync-cqm"></a><span data-ttu-id="872b6-121">Lync CQM 란?</span><span class="sxs-lookup"><span data-stu-id="872b6-121">What is Lync CQM?</span></span>

<span data-ttu-id="872b6-122">통화 품질 방법론은 Lync에서 enterprise voice services를 개선 하기 위한 노력을 보다 효율적으로 수행할 수 있는 새로운 문제 해결 및 서비스 관리 프레임 워크입니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-122">Call Quality Methodology is a new troubleshooting and service management framework that can better focus efforts to improve enterprise voice services in Lync.</span></span> <span data-ttu-id="872b6-123">CQM을 사용 하는 경우 enterprise voice 서비스에 대 한 통화 품질과 사용자 만족도를 보장 하기 위해 노력을 덜 필요가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-123">When you use CQM, less effort is needed to assure call quality and user satisfaction for enterprise voice services.</span></span> <span data-ttu-id="872b6-124">CQM는 [통화 품질 방법론](https://go.microsoft.com/fwlink/p/?linkid=615208)에 더 자세히 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-124">CQM is more fully explained in the [Call Quality Methodology](https://go.microsoft.com/fwlink/p/?linkid=615208).</span></span> <span data-ttu-id="872b6-125">이 문서와 포스터는 해당 콘텐츠의 요약입니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-125">This article and the poster are summaries of that content.</span></span>

<span data-ttu-id="872b6-126">CQM에서는 시스템 문제 해결을 세 가지 경로 또는 "도로 구분 합니다."로 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-126">CQM breaks down System troubleshooting into three paths or “Roads.”</span></span> <span data-ttu-id="872b6-127">여기에는 서버 플랜트도로, 서버와 이러한 간의 링크를 보여 주는, 사용자 장치 및 미디어를 통화 하는 데 사용 되는 끝점, 마지막 마일도로, 그리고 전통적인 스위칭 전화 네트워크 통화의 통합을 해결 하는 끝 점 이동도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-127">These are: the Server Plant Road, which looks at the servers and the links between them, the End Points Road, which looks at user devices and media used to carry calls, and the Last Mile Road, which addresses integration of traditional switched telephone network calls.</span></span>

<span data-ttu-id="872b6-128">각 로드맵은 특정 영역이 나 항목과 관련 된 여러 세그먼트로 구분 되며 각 세그먼트 정의는 허용 되는 품질 수준에 대해 결정 되며, 작업은 해당 품질 수준을 달성 하기 위해 수행 되며, 서비스 관리 계획은 다음 항목으로 넘어가기 전에 품질 수준을 유지 관리 하기 위해 마련 됩니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-128">Each Road is divided into several segments relating to a specific area or topic, and at each segment definitions are made about what is an acceptable quality level, actions are taken to achieve that quality level, and a service management plan is put in place to maintain that quality level before moving on to the next topic.</span></span>

<span data-ttu-id="872b6-129">포스터는 Lync CQM를 3 명의 플레이어에 게 보드 게임으로 제공 하며, 각 플레이어가도로를 진행 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-129">The poster presents Lync CQM as a board game for three players, each of whom will go through one of the roads.</span></span> <span data-ttu-id="872b6-130">다운로드에 포함 된 카드는 통화 품질이 극복 해야 하는 장애 요소를 시뮬레이션 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-130">Cards included with the download are used to simulate impediments to call quality that must be overcome.</span></span> <span data-ttu-id="872b6-131">대상 및 목표에 대 한 힌트와 제안은 실제 응용 프로그램에서 처음으로 이동 하는 세 가지 경로, 즉 게임에서 세도로 모두 병렬로 처리 되는 우선 순위 지정 지침을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-131">Hints and suggestions about targets and how to achieve them are included along the three paths, as well as prioritization guidelines for which road to pursue first in actual applications (in the game, all three roads are addressed in parallel).</span></span>

<span data-ttu-id="872b6-132">이전 버전의 Lync에서 CQM는 어떻게 작동 하나요?</span><span class="sxs-lookup"><span data-stu-id="872b6-132">How does CQM work in earlier versions of Lync?</span></span> <span data-ttu-id="872b6-133">CQM은 Lync 2013에 대 한 새로운 기능은 아니지만 대부분의 경우 Lync 2010에서 사용 하도록 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-133">CQM is new for Lync 2013, but most of it can be adapted to be used with Lync 2010.</span></span> <span data-ttu-id="872b6-134">CQM는 Microsoft Office Communicator를 사용 하 여 원하는 수준으로 작동할 수 있지만 테스트 되지 않으며 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-134">CQM may work to a degree with Microsoft Office Communicator, but this is untested and not supported.</span></span>

<span data-ttu-id="872b6-135">CQM을 사용 하는 방법에 대 한 질문이 있는 경우 cqmfeedback@microsoft.com에 게 질문을 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-135">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

</div>

<span id="Trending"></span>

<div>

## <a name="prioritize-run-trending-queries"></a><span data-ttu-id="872b6-136">우선 순위: 추세 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="872b6-136">Prioritize: Run Trending Queries</span></span>

<span data-ttu-id="872b6-137">CQM의 첫 번째 단계는 2 주 동안 각 추세 쿼리를 실행 한 다음 결과를 분석 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-137">The first step in CQM is to run each of the trending queries for two weeks and then analyze the results.</span></span> <span data-ttu-id="872b6-138">가장 큰 스트림 참가자, 가장 낮은 불량 스트림 비율 및 관리 되는 영역 (제어 대상)에 따라 정정 작업의 우선 순위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-138">Prioritize corrective action by the largest stream contributor, the highest poor stream ratio, and managed areas (ones you control).</span></span><span data-ttu-id="872b6-139">오디오/비디오에서 AV MCU (다중 소수점 제어 장치) 또는 중재 쿼리가 잘못 된 결과를 표시 하는 경우 빨간색 또는 서버 플랜트도로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-139">  If the Audio/Video Multi-point Control Unit (AV MCU) or Mediation queries show poor results, start on the Red or Server Plant road.</span></span><span data-ttu-id="872b6-140">유선 또는 무선 쿼리에 잘못 된 결과가 표시 되 면 파란색 또는 마지막 마일도로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-140">  If the Wired or Wireless queries show poor results, start on the Blue or Last Mile road.</span></span><span data-ttu-id="872b6-141">VPN 또는 외부 쿼리가 불량 결과를 표시 하는 경우에는 녹색 또는 끝점도로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-141">  If the VPN or External queries show poor results, start on the Green or End Points road.</span></span>

<span data-ttu-id="872b6-142">시작할 이동을 선택한 후에는 각 영역 (어설션)에 대 한 대상 정의를 수행 하 고 해당 목표를 충족 하 고 대상에 유지 되도록 프로시저를 구현 합니다 (유지 관리).</span><span class="sxs-lookup"><span data-stu-id="872b6-142">After you choose a road to start with, define a target for each area (Assert), work to meet that target (Achieve) and then implement procedures to stay on target (Maintain).</span></span> <span data-ttu-id="872b6-143">또한이 포스터를 게임으로 사용 하 여 CQM에 부속 된 원칙을 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-143">You can also use this poster as a game to understand the principles behind CQM.</span></span>

</div>

<span id="PCD"></span>

<div>

## <a name="pcd"></a><span data-ttu-id="872b6-144">.PCD</span><span class="sxs-lookup"><span data-stu-id="872b6-144">PCD</span></span>

<span data-ttu-id="872b6-145">PreCall 진단 도구 (.PCD)는 경계 네트워크의 문제를 식별 하 고 진단 하는 데 도움이 되며 (QoE 데이터베이스는 edge 또는 경계 네트워크에서 정보를 수집 하지 않음) 마지막 마일에서의 연결 문제 해결도 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-145">The PreCall Diagnostics tool (PCD) will help you identify and diagnose problems in your perimeter network (the QoE database doesn’t collect information on your edge or perimeter network) and also to troubleshoot connections in the Last Mile.</span></span> <span data-ttu-id="872b6-146">이 도구는 Windows 8 최신 앱 또는 Windows 데스크톱 앱으로 제공 됩니다 https://apps.microsoft.com/windows/en-us/app/lync-2013-precall-diagnostics/9607fe33-2b51-403d-9615-c23f248e7c88 .</span><span class="sxs-lookup"><span data-stu-id="872b6-146">The tool is available as both a Windows 8 Modern App or a Windows Desktop App at https://apps.microsoft.com/windows/en-us/app/lync-2013-precall-diagnostics/9607fe33-2b51-403d-9615-c23f248e7c88.</span></span>

</div>

<span id="ManagedUn"></span>

<div>

## <a name="managedunmanaged"></a><span data-ttu-id="872b6-147">관리/비관리</span><span class="sxs-lookup"><span data-stu-id="872b6-147">Managed/Unmanaged</span></span>

<span data-ttu-id="872b6-148">Lync Server 배포 및 네트워크 인프라는 일반적으로 관리 되는 공간과 관리 되지 않는 공백으로 구분 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-148">The Lync Server deployment and network infrastructure can usually be divided into managed and unmanaged spaces.</span></span> <span data-ttu-id="872b6-149">관리 되는 공간에는 전체 유선 네트워크 및 서버 인프라 내부가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-149">The managed space includes your entire inside wired network and server infrastructure.</span></span> <span data-ttu-id="872b6-150">관리 되지 않는 공간은 무선 인프라와 외부 네트워크 인프라입니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-150">The unmanaged space is the wireless infrastructure and the outside network infrastructure.</span></span>

<span data-ttu-id="872b6-151">이렇게 구분 하면 데이터의 선명도가 향상 되 고 사용자의 음성 및 비디오 품질에 큰 영향을 줄 수 있는 작업을 조직에서 중점적으로 수행 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-151">Making this distinction increases the clarity of your data and helps your organization focus on workloads that will have a measurable impact on your users’ voice and video quality.</span></span> <span data-ttu-id="872b6-152">사용자가 소유 하는 인프라 (관리 되는 경우)와 일부 다른 엔터티 (관리 되지 않음)가 제어 하는 인프라에 통화를 하는 경우에는 다른 품질 기대치를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-152">Users have a different expectation of quality if the call is placed on infrastructure that you own (managed) versus infrastructure that is partly under the control of some other entity (unmanaged).</span></span> <span data-ttu-id="872b6-153">이는 무선 사용자가 자신의 장치에 남아 있어 탁월한 Lync Server 환경을 제공 하는 것 이라고 말할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-153">This is not to say that wireless users are left to their own devices to have excellent Lync Server experiences.</span></span>

<span data-ttu-id="872b6-154">관리 되지 않는 공간에서 음성 품질을 개선 하려면 관리 되는 공간에 높은 품질을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-154">Improving voice quality in the unmanaged space requires you to have high quality in the managed space.</span></span> <span data-ttu-id="872b6-155">무선 (Wi-fi)이 관리 되는 것으로 간주 되는지 아니면 관리 되지 않는 공간으로 조직에 있는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-155">Whether wireless (Wi-Fi) is considered managed or unmanaged space is up to your organization.</span></span> <span data-ttu-id="872b6-156">정상 환경을 실현 하는 기술은 솔루션 처럼 두 개의 공백과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-156">The techniques to achieve a healthy environment are different in the two spaces, as are the solutions.</span></span>

</div>

<span id="ServRd"></span>

<div>

## <a name="the-server-plant-road"></a><span data-ttu-id="872b6-157">서버 플랜트도로</span><span class="sxs-lookup"><span data-stu-id="872b6-157">The Server Plant Road</span></span>

<span data-ttu-id="872b6-158">서버 플랜트도로 세그먼트는 Lync 구현에서 실제 서버의 주소를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-158">Segment 1 of the Server Plant Road addresses the actual servers in the Lync implementation.</span></span> <span data-ttu-id="872b6-159">서버 자체와 구현에서의 해당 역할에 대 한 KHI 데이터를 수집 하 고 결과를 분석 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-159">Gather KHI data regarding both the server itself and its role in the implementation and analyze the result.</span></span> <span data-ttu-id="872b6-160">조치를 취할 수 있으면 발견 된 문제를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-160">If action is warranted, correct any problems found.</span></span> <span data-ttu-id="872b6-161">이 항목에 대 한 자세한 내용은 KHI 포스터와 함께 제공 되는 [Lync Server 2013의 주요 상태 지표](lync-server-2013-poster-key-health-indicators.md) 문서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="872b6-161">More detail on this topic is presented in the article about [Key Health Indicators in Lync Server 2013](lync-server-2013-poster-key-health-indicators.md) that accompanies the KHI poster.</span></span>

<span data-ttu-id="872b6-162">다음 세그먼트는 AV MCU 서버와 중재 서버 간의 미디어 스트림을 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-162">The next segment addresses media streams between the AV MCU server and mediation server.</span></span> <span data-ttu-id="872b6-163">먼저 대상에 불량 스트림 임계값이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-163">Begin by determining your targets for poor stream thresholds.</span></span> <span data-ttu-id="872b6-164">불량 스트림은 대개 PacketLossRate \> .01 또는 PacketLossRateMax입니다 \> .</span><span class="sxs-lookup"><span data-stu-id="872b6-164">Poor streams are usually PacketLossRate \> .01 or PacketLossRateMax \> .05.</span></span> <span data-ttu-id="872b6-165">다른 좋은 대상이 PoorStreamsRatio \< 2%입니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-165">Another desirable target is PoorStreamsRatio \< 2%.</span></span> <span data-ttu-id="872b6-166">다음으로, 세부 쿼리를 사용 하 여 스트림이 불량 인 AVMCU 및 중재 서버 쌍을 찾고, 불량 스트림의 원인을 조사 하 고, 불량 스트림 경로의 네트워크 장비를 확인 하 고, 불량 스트림을 수정 하 고, 네트워크 장비의 최적 또는 "골드" 구성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-166">Next, use detailed queries to find AVMCU and Mediation server pairs with poor streams, investigate the cause of poor streams, look at network equipment in the poor stream paths, remediate poor streams, and define optimal or “gold” configuration for network equipment.</span></span> <span data-ttu-id="872b6-167">성과를 유지 하려면 구성 드리프트를 관리 하 고 새로운 문제 영역을 보고 하는 프로세스 및 도구를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-167">To maintain your achievement, implement processes and tools to manage configuration drift and to report new problem areas.</span></span>

<span data-ttu-id="872b6-168">그런 다음 중재 서버와 PSTN (공중 전화망) 게이트웨이 간의 미디어 스트림을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-168">Next, examine the media streams between the Mediation server and the Public Switched Telephone Network (PSTN) gateway.</span></span> <span data-ttu-id="872b6-169">먼저 대상에 불량 스트림 임계값이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-169">Begin by determining your targets for poor stream thresholds.</span></span> <span data-ttu-id="872b6-170">불량 스트림은 대개 PacketLossRate \> .01 또는 PacketLossRateMax입니다 \> .</span><span class="sxs-lookup"><span data-stu-id="872b6-170">Poor streams are usually PacketLossRate \> .01 or PacketLossRateMax \> .05.</span></span> <span data-ttu-id="872b6-171">다른 좋은 대상이 PoorStreamsRatio \< 2%입니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-171">Another desirable target is PoorStreamsRatio \< 2%.</span></span> <span data-ttu-id="872b6-172">다음으로 자세한 쿼리를 사용 하 여 스트림이 불량 인 중재 서버 및 게이트웨이 쌍을 찾고, 불량 스트림의 원인을 조사 하 고, 불량 스트림 경로에서 네트워크 장비를 확인 하 고, 불량 스트림을 수정 하 고, 네트워크 장비의 최적 또는 "골드" 구성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-172">Next, use detailed queries to find Mediation server and gateway pairs with poor streams, investigate the cause of poor streams, look at network equipment in the poor stream paths, remediate poor streams, and define optimal or “gold” configuration for network equipment.</span></span> <span data-ttu-id="872b6-173">성과를 유지 하려면 구성 드리프트를 관리 하 고 새로운 문제 영역을 보고 하는 프로세스 및 도구를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-173">To maintain your achievement, implement processes and tools to manage configuration drift and to report new problem areas.</span></span>

<span data-ttu-id="872b6-174">마지막으로 PSTN 게이트웨이에 대 한 상태 메트릭을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-174">Finally, examine the health metrics for your PSTN gateway.</span></span> <span data-ttu-id="872b6-175">상태를 표시 하 고 목표를 정의 하는 통계를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-175">Identify the statistics that show health and define targets against them.</span></span> <span data-ttu-id="872b6-176">가능한 여러 게이트웨이를 사용할 수 있으므로 여기에는 구체적인 지침이 제공 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-176">No specific guidance is provided here as many possible gateways can be used.</span></span> <span data-ttu-id="872b6-177">대상이 설정 되 면 목표를 달성 하기 위해 필요에 따라 수정 합니다. 이 프로세스에서는 게이트웨이에 대해 "골드" 또는 최적 구성을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-177">Once targets are established, remediate as needed to achieve the target; in the process you will likely define a “gold” or optimal configuration for the gateway.</span></span> <span data-ttu-id="872b6-178">성과를 유지 하려면 구성 드리프트를 관리 하 고 새로운 문제 영역을 보고 하는 프로세스 및 도구를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-178">To maintain your achievement, implement processes and tools to manage configuration drift and to report new problem areas.</span></span> <span data-ttu-id="872b6-179">펌웨어 및 소프트웨어 업데이트가 구성을 변경 하거나 "골드" 구성의 정의를 변경 하기 위해 이러한 활동을 신중 하 게 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-179">Be aware that firmware and software updates may alter your configuration or lead you to change the definition of the “gold” configuration, so approach these activities with care.</span></span>

</div>

<span id="LastMi"></span>

<div>

## <a name="the-last-mile-road"></a><span data-ttu-id="872b6-180">마지막 마일도로</span><span class="sxs-lookup"><span data-stu-id="872b6-180">The Last Mile Road</span></span>

<span data-ttu-id="872b6-181">클라이언트가 네트워크에 연결 하는 두 가지 방법 중에서 유선은 마지막 마일 문제에 대 한 초기 초점 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-181">Of the two ways clients connect to the network, wired is expected to deliver the highest quality and correspondingly this must be your initial focus for last mile issues.</span></span> <span data-ttu-id="872b6-182">CQM 유선 쿼리 (LastMile \_ 0 \_ 유선) 및 데이터 불량 스트림 속도를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-182">Use the CQM Wired query (LastMile\_0\_Wired) and the Poor Streams ratio data it provides.</span></span> <span data-ttu-id="872b6-183">대상 PoorStreamsRatio 300 스트림을 정의 하는 것이 좋습니다 \< 5% for sites with \> .</span><span class="sxs-lookup"><span data-stu-id="872b6-183">We suggest defining a target PoorStreamsRatio \< 5% for sites with \> 300 streams).</span></span> <span data-ttu-id="872b6-184">목표를 달성 하려면 최하위에서 최상으로 순서가 지정 된 서브넷을 수정 하 고 QoS를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-184">To achieve your targets, remediate subnets ordered from worst to best, and implement QoS.</span></span>

<span data-ttu-id="872b6-185">유선 연결의 품질을 최적화 하면 무선 인프라가 각 위치에서 유선 코어를 기반으로 하기 때문에 무선 품질 향상이 더 쉬워집니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-185">After you optimize the quality of your wired connections, improving wireless quality becomes easier because the wireless infrastructure sits atop the wired core at each location.</span></span> <span data-ttu-id="872b6-186">적절 한 유선 품질로 사이트의 불량 무선 스트림은 특정 무선 구성 요소에 대 한 특성을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-186">Poor wireless streams in a site with good wired quality must be attributed to the specific wireless components.</span></span> <span data-ttu-id="872b6-187">CQM 무선 쿼리 (LastMile \_ 1 \_ 무선)는 날짜 범위에 작동 하며, 사용자 환경의 모든 내부 무선 스트림을 회의 서버 또는 중재 서버에서 보내거나 Lync 클라이언트로부터 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-187">The CQM Wireless query (LastMile\_1\_Wireless) operates on a date range and will return all internal wireless streams in your environment from Lync clients to or from either conferencing servers or mediation servers.</span></span> <span data-ttu-id="872b6-188">대상 PoorStreamsRatio 300 스트림을 정의 하는 것이 좋습니다 \< 5% for sites with \> .</span><span class="sxs-lookup"><span data-stu-id="872b6-188">We suggest defining a target PoorStreamsRatio \< 5% for sites with \> 300 streams).</span></span> <span data-ttu-id="872b6-189">목표를 달성 하려면 최하위에서 최상으로 순서가 지정 된 서브넷을 수정 하 고 QoS를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-189">To achieve your targets, remediate subnets ordered from worst to best, and implement QoS.</span></span>

</div>

<span id="EndPt"></span>

<div>

## <a name="the-end-points-road"></a><span data-ttu-id="872b6-190">끝점도로</span><span class="sxs-lookup"><span data-stu-id="872b6-190">The End Points Road</span></span>

<span data-ttu-id="872b6-191">Lync와 함께 사용할 때 허용 되는 품질을 생성 하는 데 알려진 헤드셋 및 기타 장치로의 끝점에 대 한 질문을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-191">Begin inquiries into the End Points Road with the headsets and other devices known to produce acceptable quality when used with Lync.</span></span> <span data-ttu-id="872b6-192">100 stream을 통한 구현에는 대상 AvgSendListen MOS 3.6이 추천 \> 됩니다. 문제가 발생 한 장치를 식별 하 고 수정 하거나 대체 하 여 대상을 달성 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-192">We suggest a target AvgSendListen MOS \> 3.6 for implementations with over 100 streams.) Achieve the target by identifying problematic devices and fix or replace them.</span></span>

<span data-ttu-id="872b6-193">다음으로, 최종 사용자 통화에 대 한 오디오를 처리 하는 장치 또는 PC를 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-193">Next, examine the device or PC processing the audio for end user calls.</span></span> <span data-ttu-id="872b6-194">권장 되는 대상 품질 메트릭은 AudioMicGlitchRate \< = 1입니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-194">A suggested target quality metric is an AudioMicGlitchRate \<= 1.</span></span> <span data-ttu-id="872b6-195">사용자 시스템에 대 한 최적의 시스템 구성을 확인 하려면 드라이버 버전을 포함 하 여 "골든" PC 구성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-195">As you identify optimal system configurations for the user systems, define a “golden” PC configuration including driver versions.</span></span>

<span data-ttu-id="872b6-196">이제 오디오 스트림이 Lync 끝점 시스템에서 수행 하는 네트워크 경로를 검사 하 여 오디오 품질이 떨어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-196">Now examine the network path an audio stream takes from a Lync endpoint system, which can cause poor audio quality.</span></span> <span data-ttu-id="872b6-197">오디오가 VPN 연결을 통해 이동 하는 경우 대기 시간 문제가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-197">If audio travels over a VPN connection you might see latency issues.</span></span> <span data-ttu-id="872b6-198">내부 Lync 클라이언트가 두 사용자 또는 피어 투 피어 통화를 위해 다른 내부 Lync 클라이언트에 대해 직접 미디어 스트림을 설정할 수 없는 경우 Lync에 지 서버를 통해 전달 되는 경로로 다시 변경 되며 손실 및 지터 발생할 가능성이 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-198">If an internal Lync client cannot establish a direct media stream to another internal Lync client for a two-party or peer-to-peer call, it will fall back to a path that relays through a Lync Edge server, again leading to latency issues as well as increased potential for loss and jitter.</span></span> <span data-ttu-id="872b6-199">VPN을 통해 0% 미디어의 품질 메트릭을 정의 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-199">We suggest you define a quality metric of 0% Media over VPN.</span></span> <span data-ttu-id="872b6-200">사용자가 설정한 목표를 달성 하기 위해 수정 하는 동안 문제 서브넷을 식별 하 고 방화벽 규칙, 패킷 shapers 및 기타 관련 네트워크 장비 구성을 조사 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-200">As you remediate to achieve the target you set, identify problem subnets and investigate firewall rules, packet shapers, and other relevant network equipment configuration.</span></span>

<span data-ttu-id="872b6-201">IP 패킷은 TCP (전송 제어 프로토콜) 또는 UDP (사용자 데이터 그램 프로토콜)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-201">IP Packets can use either Transmission Control Protocol (TCP) or User Datagram Protocol (UDP).</span></span> <span data-ttu-id="872b6-202">TCP는 데이터 스트림에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-202">TCP is optimal for data streams.</span></span> <span data-ttu-id="872b6-203">UDP는 연결 되지 않으며, TCP 복구 메커니즘이 실시간 미디어의 손실을 처리할 수 없기 때문에 미디어에 보다 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-203">UDP is connectionless and is more efficient for media since TCP recovery mechanisms cannot address loss in real time media.</span></span> <span data-ttu-id="872b6-204">Lync에서는 항상 UDP를 선호 하지만 UDP 세션을 설정할 수 없는 경우 TCP로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-204">Lync always prefers UDP, but will revert to TCP if a UDP session cannot be established.</span></span> <span data-ttu-id="872b6-205">TCP를 통한 미디어 세션은 UDP 보다 poorer 품질을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-205">Media sessions over TCP will exhibit poorer quality than over UDP.</span></span> <span data-ttu-id="872b6-206">TCP를 통한 연결의 품질이 0% 인 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-206">We recommend a quality definition of 0% connections over TCP.</span></span> <span data-ttu-id="872b6-207">사용자가 설정한 목표를 달성 하기 위해 수정 하는 동안 문제 서브넷을 식별 하 고 방화벽 규칙, 패킷 shapers 및 기타 관련 네트워크 장비 구성을 조사 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-207">As you remediate to achieve the target you set, identify problem subnets and investigate firewall rules, packet shapers, and other relevant network equipment configuration.</span></span>

</div>

<span id="ServMgt"></span>

<div>

## <a name="service-management"></a><span data-ttu-id="872b6-208">서비스 관리</span><span class="sxs-lookup"><span data-stu-id="872b6-208">Service Management</span></span>

<span data-ttu-id="872b6-209">서비스 관리는 CQM의 최종 상태이 고 모든 세 자리에 대 한 대상입니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-209">Service management is the end state of CQM, and the destination for all three roads.</span></span> <span data-ttu-id="872b6-210">높은 수준의 통화 품질을 유지 관리 하려면 다음 영역을 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-210">To maintain high levels of call quality, monitor these areas:</span></span>

1.  <span data-ttu-id="872b6-211">**사용자** 가 업데이트 관리 작업을 수행 하면 사용자 만족도가 크게 증가 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-211">**Users** - Remediation activities should show a measurable increase in user satisfaction.</span></span> <span data-ttu-id="872b6-212">문제 티켓 또는 기타 피드백 메커니즘을 통해이를 측정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-212">You can measure this by problem tickets or other feedback mechanisms.</span></span> <span data-ttu-id="872b6-213">품질 메트릭을 게시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-213">You can also publish quality metrics.</span></span>

2.  <span data-ttu-id="872b6-214">**Process** -매일, 매주 및 매월 operationalize CQM으로 프로세스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-214">**Process** - define daily, weekly and monthly processes to operationalize CQM.</span></span> <span data-ttu-id="872b6-215">모니터링 rhythm는 수정 (매일) 동안 더 높은 빈도로 시작 되며 안정화 되는 동안 더 낮은 주파수 (매월)로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-215">Monitoring rhythm starts at a higher frequency while you are remediating (daily) and moves to a lower frequency (monthly) as you stabilize.</span></span>

3.  <span data-ttu-id="872b6-216">**도구** -측정 및 재구성에 대 한 도구를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-216">**Tools** - identify tools to both measure and remediate.</span></span> <span data-ttu-id="872b6-217">프로세스를 지원 하기 위해 CQM 쿼리를 자동으로 실행 하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-217">You may find it useful to automate running the CQM queries to support your processes.</span></span> <span data-ttu-id="872b6-218">네트워크 요소에 표준화 된 구성을 적용 하거나 불량 스트림의 문제를 해결 하기 위해 수정 하는 경우 추가 도구가 필요할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-218">Remediation may require additional tools for example to enforce standardized configurations on network elements or troubleshooting loss in poor streams.</span></span>

</div>

<span id="BoardGm"></span>

<div>

## <a name="board-game-rules"></a><span data-ttu-id="872b6-219">보드 게임 규칙</span><span class="sxs-lookup"><span data-stu-id="872b6-219">Board Game Rules</span></span>

<span data-ttu-id="872b6-220">개념을 연습 하기 위해이 포스터를 CQM 구현 또는 게임에 대 한 참조로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-220">You can use this poster either as a reference to a CQM implementation or as a game to practice the concepts.</span></span> <span data-ttu-id="872b6-221">재생 하려면 1 6-사이드 다이 및 카드를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-221">To play, you will need one six-sided die and the cards provided.</span></span> <span data-ttu-id="872b6-222">표준 Avery 5871 명함에 다운로드 가능한 카드 버전을 인쇄 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-222">A downloadable version of the cards is available to print on standard Avery 5871 business cards.</span></span>

<span data-ttu-id="872b6-223">3 명으로 게임을 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-223">The game is for 3 players.</span></span> <span data-ttu-id="872b6-224">플레이어는 3 개의 경로를 사용 하 여 서버 플랜트, 끝점 및 마지막 마일 등 원하는 품질을 달성 하 고 센터 서비스 관리 상태에 도달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-224">There are three paths the players can use to achieve the desired quality and reach the center Service Management state: Server Plant, End Point, and Last Mile.</span></span> <span data-ttu-id="872b6-225">각 경로는 품질 목표를 어설션 하 고 목표를 달성 하 고 시스템의 측면을 유지 관리 하는 방식에 따라 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-225">Each path has stops along the way where you Assert quality targets, Achieve goals, and Maintain an aspect of your system.</span></span> <span data-ttu-id="872b6-226">위의 지정 된 영역에 카드를 놓은 다음 5 개의 카드를 그립니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-226">Place the cards in the indicated area above, and then draw 5 cards.</span></span> <span data-ttu-id="872b6-227">그린 카드를 검토 하 여 관련 보드 세그먼트에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-227">Review the cards you’ve drawn and place them on the relevant board segment.</span></span> <span data-ttu-id="872b6-228">각 플레이어는 경로의 카드를 단계별로 이동 하 고, 품질 목표를 어설션 하며, 해당 목표를 달성 하 고, 서비스 수준을 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-228">Each player moves through the cards on their path step by step, asserting quality targets, achieving those targets, and maintaining the service levels.</span></span> <span data-ttu-id="872b6-229">모든 플레이어가 센터 서비스 관리 상태로 연결 되 면 게임이 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-229">The game is completed when all players reach the center Service Management state.</span></span> <span data-ttu-id="872b6-230">더 자세한 규칙은 게임 카드 다운로드와 함께 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-230">More detailed rules are provided with the game card download.</span></span>

<span data-ttu-id="872b6-231">품질 목표를 **어설션하** 는 경우 해당 대상에 적용할 수 있는 매개 변수를 검토 하 고, 사용자가 적용 하 고 수락 하지 않을 것으로 선택할 수 있는 내용을 소리내어 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-231">To **Assert** a quality target, review the parameters applicable to that target, and state out loud what you will and won’t choose to accept.</span></span> <span data-ttu-id="872b6-232">초기 점수를 제공 하는 것이 좋지만 최종 통화를 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-232">We have recommended beginning points, but you must make the final call.</span></span> <span data-ttu-id="872b6-233">예외는 KHI 데이터 이며 Microsoft에서 설정한 표준을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-233">The exception is KHI data, where the standards established by Microsoft should be used.</span></span> <span data-ttu-id="872b6-234">함께 제공 되는 KHI 포스터를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="872b6-234">See the accompanying KHI poster.</span></span>

<span data-ttu-id="872b6-235">게임을 **완수** 하려면 khi 데이터 및 시스템 쿼리 대신 제공 되는 카드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-235">To **Achieve** in the game, use the cards provided in place of KHI data and system queries.</span></span> <span data-ttu-id="872b6-236">게임을 시작할 때 특정 측면과 관련 된 카드를 그리지 않으면 이후에도 계속 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-236">If at the start of the game you did not draw a card relating to a given aspect, you can continue past it.</span></span> <span data-ttu-id="872b6-237">관련 카드가 있으면 주사위를 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-237">If there is a relevant card, roll the die.</span></span> <span data-ttu-id="872b6-238">카드에 표시 된 번호로 롤백하는 경우 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-238">If you rolled under the number indicated on the card, you have succeeded.</span></span> <span data-ttu-id="872b6-239">표시 된 번호를 롤 이나 위쪽으로 그리면 데크에서 다른 카드를 그려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-239">If you roll at or over the indicated number, you must draw another card from the deck.</span></span> <span data-ttu-id="872b6-240">카드에서 두 명 이상의 플레이어를 롤백해야 하는 경우 모든 롤백이 완료 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-240">If the card indicates two or more players need to roll, they must all roll successfully.</span></span>

<span data-ttu-id="872b6-241">게임에서 **유지** 관리 하기 위해 Lync 환경의 해당 측면에 대 한 서비스 관리 계획을 소리내어 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="872b6-241">To **Maintain** in the game, state out loud the service management plan regarding that aspect of the Lync environment.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="872b6-242">참고 항목</span><span class="sxs-lookup"><span data-stu-id="872b6-242">See Also</span></span>


[<span data-ttu-id="872b6-243">Lync Server 네트워킹 가이드</span><span class="sxs-lookup"><span data-stu-id="872b6-243">Lync Server Networking Guide</span></span>](https://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="872b6-244">주요 상태 지표: 정상 Lync Server를 유지 관리 하기 위한 기본 사항</span><span class="sxs-lookup"><span data-stu-id="872b6-244">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](https://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="872b6-245">Lync 통화 품질 방법론</span><span class="sxs-lookup"><span data-stu-id="872b6-245">Lync Call Quality Methodology</span></span>](https://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

