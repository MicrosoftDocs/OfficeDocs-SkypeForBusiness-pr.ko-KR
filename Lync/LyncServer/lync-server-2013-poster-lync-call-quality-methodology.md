---
title: 'Lync Server 2013: 포스터: Lync 통화 품질 방법'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Poster: Lync Call Quality Methodology'
ms:assetid: a069f4e5-4f80-4f0f-8657-2e07276b6b41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593600(v=OCS.15)
ms:contentKeyID: 61084874
ms.date: 06/24/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e18dc59e0b8669bb48962874291e63523f37eb48
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-call-quality-methodology-in-lync-server-2013"></a><span data-ttu-id="53aa8-102">Lync Server 2013의 lync 통화 품질 방법론</span><span class="sxs-lookup"><span data-stu-id="53aa8-102">Lync Call Quality Methodology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53aa8-103">_**마지막으로 수정한 주제:** 2016-06-24_</span><span class="sxs-lookup"><span data-stu-id="53aa8-103">_**Topic Last Modified:** 2016-06-24_</span></span>

<span data-ttu-id="53aa8-104">이 문서는 [Lync 통화 품질 방법론](http://go.microsoft.com/fwlink/?linkid=391841) 포스터와 함께 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-104">This article is a companion to the [Lync Call Quality Methodology](http://go.microsoft.com/fwlink/?linkid=391841) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="53aa8-105">(images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg "CQM 프로세스를 설명") 하는 ![CQM 프로세스 포스터를 설명 하는 포스터]</span><span class="sxs-lookup"><span data-stu-id="53aa8-105">![Poster describing the CQM process](images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg "Poster describing the CQM process")</span></span>

<span data-ttu-id="53aa8-106">이 포스터를 사용 하 여 Lync 2013 및 2010에 대 한 통화 품질 방법론, 그리고 엔터프라이즈 음성 기능을 포함 하는 Lync 구현의 통화 품질과 사용자 환경에 영향을 주는 문제를 찾아 제거할 수 있도록 도와주는 CQM에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="53aa8-106">You can use this poster to learn about CQM, the Call Quality Methodology for Lync 2013 and 2010 that helps you find and eliminate issues affecting call quality and user experience for Lync implementations that include enterprise voice features.</span></span> <span data-ttu-id="53aa8-107">통화 품질 방법론은 Lync에서 엔터프라이즈 음성 서비스를 개선 하는 데 더 나은 초점을 둘 수 있는 새로운 문제 해결 및 서비스 관리 프레임 워크입니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-107">Call Quality Methodology is a new troubleshooting and service management framework that can better focus efforts to improve enterprise voice services in Lync.</span></span> <span data-ttu-id="53aa8-108">이 문서에서는 CQM, 모니터링할 서버 및 솔루션의 종류와 수집 된 원격 분석 데이터로 수행할 작업에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-108">In this article, you can learn more about CQM, the kinds of servers and solutions that are monitored, and what to do with the collected telemetry data.</span></span>

<span data-ttu-id="53aa8-109">CQM를 사용 하는 방법에 대 한 질문이 있는 경우 cqmfeedback@microsoft.com에 질문을 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-109">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="53aa8-110">포스터는 다음 영역에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-110">The poster explains the following areas:</span></span>

  - <span data-ttu-id="53aa8-111">Lync CQM?</span><span class="sxs-lookup"><span data-stu-id="53aa8-111">What is Lync CQM?</span></span>

  - <span data-ttu-id="53aa8-112">우선 순위: 추세 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="53aa8-112">Prioritize: Run Trending Queries</span></span>

  - <span data-ttu-id="53aa8-113">PCD</span><span class="sxs-lookup"><span data-stu-id="53aa8-113">PCD</span></span>

  - <span data-ttu-id="53aa8-114">관리 됨/관리 되지 않음</span><span class="sxs-lookup"><span data-stu-id="53aa8-114">Managed/Unmanaged</span></span>

  - <span data-ttu-id="53aa8-115">서버 플랜트도로</span><span class="sxs-lookup"><span data-stu-id="53aa8-115">The Server Plant Road</span></span>

  - <span data-ttu-id="53aa8-116">지난 마일도로</span><span class="sxs-lookup"><span data-stu-id="53aa8-116">The Last Mile Road</span></span>

  - <span data-ttu-id="53aa8-117">끝점도로를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-117">The End Points Road</span></span>

  - <span data-ttu-id="53aa8-118">서비스 관리</span><span class="sxs-lookup"><span data-stu-id="53aa8-118">Service Management</span></span>

  - <span data-ttu-id="53aa8-119">보드 게임 규칙</span><span class="sxs-lookup"><span data-stu-id="53aa8-119">Board Game Rules</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-is-lync-cqm"></a><span data-ttu-id="53aa8-120">Lync CQM?</span><span class="sxs-lookup"><span data-stu-id="53aa8-120">What is Lync CQM?</span></span>

<span data-ttu-id="53aa8-121">통화 품질 방법론은 Lync에서 엔터프라이즈 음성 서비스를 개선 하는 데 더 나은 초점을 둘 수 있는 새로운 문제 해결 및 서비스 관리 프레임 워크입니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-121">Call Quality Methodology is a new troubleshooting and service management framework that can better focus efforts to improve enterprise voice services in Lync.</span></span> <span data-ttu-id="53aa8-122">CQM를 사용 하는 경우 엔터프라이즈 음성 서비스에 대 한 통화 품질과 사용자 만족도를 보장 하기 위해 노력을 덜 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-122">When you use CQM, less effort is needed to assure call quality and user satisfaction for enterprise voice services.</span></span> <span data-ttu-id="53aa8-123">CQM는 [통화 품질 방법론](http://go.microsoft.com/fwlink/p/?linkid=615208)에 더 자세히 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-123">CQM is more fully explained in the [Call Quality Methodology](http://go.microsoft.com/fwlink/p/?linkid=615208).</span></span> <span data-ttu-id="53aa8-124">이 문서와 포스터는 해당 콘텐츠의 요약입니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-124">This article and the poster are summaries of that content.</span></span>

<span data-ttu-id="53aa8-125">CQM 시스템 문제 해결을 세 가지 경로나 "도로"로 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-125">CQM breaks down System troubleshooting into three paths or “Roads.”</span></span> <span data-ttu-id="53aa8-126">서버 플랜트도로 서버와 그 사이의 링크, 통화를 이동 하는 데 사용 되는 사용자 장치 및 미디어를 보여 주는 끝점, 마지막 마일도, 그리고 기존에 교환 되는 전화 네트워크 통화의 통합을 처리 하는 등의 지점에서의 연결을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-126">These are: the Server Plant Road, which looks at the servers and the links between them, the End Points Road, which looks at user devices and media used to carry calls, and the Last Mile Road, which addresses integration of traditional switched telephone network calls.</span></span>

<span data-ttu-id="53aa8-127">각도로는 특정 영역이 나 주제와 관련 된 여러 세그먼트로 나뉘어 있으며, 각 세그먼트 정의는 허용 되는 품질 수준에 대 한 것 이며, 작업은 해당 품질 수준을 달성 하기 위해 수행 되며, 서비스 관리 계획은 유지 관리 하기 위한 것입니다. 다음 항목으로 이동 하기 전에 해당 품질 수준을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-127">Each Road is divided into several segments relating to a specific area or topic, and at each segment definitions are made about what is an acceptable quality level, actions are taken to achieve that quality level, and a service management plan is put in place to maintain that quality level before moving on to the next topic.</span></span>

<span data-ttu-id="53aa8-128">포스터는 Lync CQM를 세 명의 플레이어에 대 한 보드 게임으로 제공 하며, 각 플레이어가도로를 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-128">The poster presents Lync CQM as a board game for three players, each of whom will go through one of the roads.</span></span> <span data-ttu-id="53aa8-129">다운로드에 포함 된 카드는 통화 품질이 극복 해야 하는 장애를 시뮬레이트하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-129">Cards included with the download are used to simulate impediments to call quality that must be overcome.</span></span> <span data-ttu-id="53aa8-130">대상 및이를 달성 하는 방법에 대 한 힌트 및 제안은 실제 응용 프로그램에서 첫 번째 작업을 진행 하는 데 사용할 수 있는 우선 순위 지정 및 세 경로에 포함 됩니다 (게임에서 세도는 모두 병렬로 처리 됨).</span><span class="sxs-lookup"><span data-stu-id="53aa8-130">Hints and suggestions about targets and how to achieve them are included along the three paths, as well as prioritization guidelines for which road to pursue first in actual applications (in the game, all three roads are addressed in parallel).</span></span>

<span data-ttu-id="53aa8-131">이전 버전의 Lync에서 CQM 어떻게 작동 하나요?</span><span class="sxs-lookup"><span data-stu-id="53aa8-131">How does CQM work in earlier versions of Lync?</span></span> <span data-ttu-id="53aa8-132">CQM Lync 2013에 대 한 새로운 기능은 아니지만, 대부분의 경우 Lync 2010에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-132">CQM is new for Lync 2013, but most of it can be adapted to be used with Lync 2010.</span></span> <span data-ttu-id="53aa8-133">Microsoft Office Communicator를 사용 하 여 CQM 수 있지만, 테스트 되지 않고 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-133">CQM may work to a degree with Microsoft Office Communicator, but this is untested and not supported.</span></span>

<span data-ttu-id="53aa8-134">CQM를 사용 하는 방법에 대 한 질문이 있는 경우 cqmfeedback@microsoft.com에 질문을 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-134">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

</div>

<span id="Trending"></span>

<div>

## <a name="prioritize-run-trending-queries"></a><span data-ttu-id="53aa8-135">우선 순위: 추세 쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="53aa8-135">Prioritize: Run Trending Queries</span></span>

<span data-ttu-id="53aa8-136">CQM의 첫 번째 단계는 2 주에 대 한 각 추세 쿼리를 실행 한 다음 결과를 분석 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-136">The first step in CQM is to run each of the trending queries for two weeks and then analyze the results.</span></span> <span data-ttu-id="53aa8-137">가장 큰 스트림 참가자, 가장 낮은 불량 스트림 비율 및 관리 영역 (제어 하는)으로 정정 작업의 우선 순위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-137">Prioritize corrective action by the largest stream contributor, the highest poor stream ratio, and managed areas (ones you control).</span></span><span data-ttu-id="53aa8-138">오디오/비디오의 AV MCU (다중 점 제어 단위) 또는 중재 쿼리에 결과가 잘못 된 것으로 표시 되는 경우 빨간색 또는 서버 플랜트도로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-138">  If the Audio/Video Multi-point Control Unit (AV MCU) or Mediation queries show poor results, start on the Red or Server Plant road.</span></span><span data-ttu-id="53aa8-139">유선 또는 무선 쿼리에서 결과가 잘못 된 것으로 표시 되는 경우 파란색 또는 마지막 마일도로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-139">  If the Wired or Wireless queries show poor results, start on the Blue or Last Mile road.</span></span><span data-ttu-id="53aa8-140">VPN 또는 외부 쿼리에 잘못 된 결과가 표시 되는 경우 녹색 또는 끝점도로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-140">  If the VPN or External queries show poor results, start on the Green or End Points road.</span></span>

<span data-ttu-id="53aa8-141">시작도로를 선택 하 고 각 영역에 대 한 대상 (어설션)을 정의 하 고 해당 대상에 맞게 작업 (달성) 한 다음 대상 유지 (유지 관리)를 위해 프로시저를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-141">After you choose a road to start with, define a target for each area (Assert), work to meet that target (Achieve) and then implement procedures to stay on target (Maintain).</span></span> <span data-ttu-id="53aa8-142">또한이 포스터를 게임으로 사용 하 여 CQM에 부속 된 원칙을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-142">You can also use this poster as a game to understand the principles behind CQM.</span></span>

</div>

<span id="PCD"></span>

<div>

## <a name="pcd"></a><span data-ttu-id="53aa8-143">PCD</span><span class="sxs-lookup"><span data-stu-id="53aa8-143">PCD</span></span>

<span data-ttu-id="53aa8-144">PreCall 진단 도구 (PCD)는 경계 네트워크의 문제를 식별 하 고 진단 하는 데 도움이 되며 (체감 품질 데이터베이스는 edge 또는 외곽 네트워크의 정보를 수집 하지 않으며), 지난 마일의 연결 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-144">The PreCall Diagnostics tool (PCD) will help you identify and diagnose problems in your perimeter network (the QoE database doesn’t collect information on your edge or perimeter network) and also to troubleshoot connections in the Last Mile.</span></span> <span data-ttu-id="53aa8-145">이 도구는 Windows 8 최신 앱 또는 Windows 데스크톱 앱으로 제공 됩니다 http://apps.microsoft.com/windows/en-us/app/lync-2013-precall-diagnostics/9607fe33-2b51-403d-9615-c23f248e7c88.</span><span class="sxs-lookup"><span data-stu-id="53aa8-145">The tool is available as both a Windows 8 Modern App or a Windows Desktop App at http://apps.microsoft.com/windows/en-us/app/lync-2013-precall-diagnostics/9607fe33-2b51-403d-9615-c23f248e7c88.</span></span>

</div>

<span id="ManagedUn"></span>

<div>

## <a name="managedunmanaged"></a><span data-ttu-id="53aa8-146">관리 됨/관리 되지 않음</span><span class="sxs-lookup"><span data-stu-id="53aa8-146">Managed/Unmanaged</span></span>

<span data-ttu-id="53aa8-147">Lync Server 배포 및 네트워크 인프라는 일반적으로 관리 및 관리 되지 않는 공간으로 나눌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-147">The Lync Server deployment and network infrastructure can usually be divided into managed and unmanaged spaces.</span></span> <span data-ttu-id="53aa8-148">관리 되는 공간에는 전체 유선 네트워크 및 서버 인프라가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-148">The managed space includes your entire inside wired network and server infrastructure.</span></span> <span data-ttu-id="53aa8-149">관리 되지 않는 공간은 무선 인프라와 외부 네트워크 인프라입니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-149">The unmanaged space is the wireless infrastructure and the outside network infrastructure.</span></span>

<span data-ttu-id="53aa8-150">이러한 차이점을 바탕으로 데이터의 명확성을 높이고 사용자의 음성 및 비디오 품질에 대 한 영향을 측정할 수 있는 작업을 조직에 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-150">Making this distinction increases the clarity of your data and helps your organization focus on workloads that will have a measurable impact on your users’ voice and video quality.</span></span> <span data-ttu-id="53aa8-151">소유 하 고 있는 인프라 (관리)가 일부 다른 엔터티의 제어 (관리 되지 않는)에 있는 인프라에 있는 경우에는 사용자가 다른 품질을 기대 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-151">Users have a different expectation of quality if the call is placed on infrastructure that you own (managed) versus infrastructure that is partly under the control of some other entity (unmanaged).</span></span> <span data-ttu-id="53aa8-152">이는 무선 사용자가 자신의 장치에 남아 있어 훌륭한 Lync 서버 환경을 위한 것 이라고 말할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-152">This is not to say that wireless users are left to their own devices to have excellent Lync Server experiences.</span></span>

<span data-ttu-id="53aa8-153">관리 되지 않는 공간에서 음성 품질을 개선 하려면 관리 되는 공간에 높은 품질을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-153">Improving voice quality in the unmanaged space requires you to have high quality in the managed space.</span></span> <span data-ttu-id="53aa8-154">무선 (Wi-fi)이 관리 되거나 관리 되지 않는 공간으로 조직에 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="53aa8-154">Whether wireless (Wi-Fi) is considered managed or unmanaged space is up to your organization.</span></span> <span data-ttu-id="53aa8-155">정상 환경을 달성 하는 방법은 솔루션과 마찬가지로 두 공간에서 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-155">The techniques to achieve a healthy environment are different in the two spaces, as are the solutions.</span></span>

</div>

<span id="ServRd"></span>

<div>

## <a name="the-server-plant-road"></a><span data-ttu-id="53aa8-156">서버 플랜트도로</span><span class="sxs-lookup"><span data-stu-id="53aa8-156">The Server Plant Road</span></span>

<span data-ttu-id="53aa8-157">서버 플랜트의 세그먼트 1은 Lync 구현에서 실제 서버를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-157">Segment 1 of the Server Plant Road addresses the actual servers in the Lync implementation.</span></span> <span data-ttu-id="53aa8-158">서버 자체와 구현의 역할 모두와 관련 하 여 KHI 데이터를 수집 하 고 결과를 분석 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-158">Gather KHI data regarding both the server itself and its role in the implementation and analyze the result.</span></span> <span data-ttu-id="53aa8-159">작업을 보장 하는 경우 발견 된 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-159">If action is warranted, correct any problems found.</span></span> <span data-ttu-id="53aa8-160">이 항목에 대 한 자세한 내용은 KHI 포스터와 함께 제공 되는 [Lync Server 2013의 주요 상태 표시기](lync-server-2013-poster-key-health-indicators.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="53aa8-160">More detail on this topic is presented in the article about [Key Health Indicators in Lync Server 2013](lync-server-2013-poster-key-health-indicators.md) that accompanies the KHI poster.</span></span>

<span data-ttu-id="53aa8-161">다음 세그먼트는 AV MCU 서버와 중재 서버 간에 미디어 스트림을 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-161">The next segment addresses media streams between the AV MCU server and mediation server.</span></span> <span data-ttu-id="53aa8-162">먼저 대상에 불량 스트림 임계값이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-162">Begin by determining your targets for poor stream thresholds.</span></span> <span data-ttu-id="53aa8-163">불량 스트림은 일반적으로 PacketLossRate \> .01 또는 PacketLossRateMax \> . 05입니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-163">Poor streams are usually PacketLossRate \> .01 or PacketLossRateMax \> .05.</span></span> <span data-ttu-id="53aa8-164">다른 좋은 대상은 PoorStreamsRatio \< 2%입니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-164">Another desirable target is PoorStreamsRatio \< 2%.</span></span> <span data-ttu-id="53aa8-165">그런 다음 상세 쿼리를 사용 하 여 스트림이 불량 한 AVMCU 및 중재 서버 쌍을 찾고, 불량 스트림 경로의 네트워크 장비를 조사 하 고, 불량 스트림을 수정 하 고, 네트워크에 대 한 최적 또는 "골드" 구성을 정의 합니다. 장비.</span><span class="sxs-lookup"><span data-stu-id="53aa8-165">Next, use detailed queries to find AVMCU and Mediation server pairs with poor streams, investigate the cause of poor streams, look at network equipment in the poor stream paths, remediate poor streams, and define optimal or “gold” configuration for network equipment.</span></span> <span data-ttu-id="53aa8-166">성과를 유지 하려면 구성 드리프트를 관리 하는 프로세스 및 도구를 구현 하 고 새 문제 영역을 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-166">To maintain your achievement, implement processes and tools to manage configuration drift and to report new problem areas.</span></span>

<span data-ttu-id="53aa8-167">다음으로 중재 서버와 PSTN (공용 전환 전화 네트워크) 게이트웨이 사이에 있는 미디어 스트림을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-167">Next, examine the media streams between the Mediation server and the Public Switched Telephone Network (PSTN) gateway.</span></span> <span data-ttu-id="53aa8-168">먼저 대상에 불량 스트림 임계값이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-168">Begin by determining your targets for poor stream thresholds.</span></span> <span data-ttu-id="53aa8-169">불량 스트림은 일반적으로 PacketLossRate \> .01 또는 PacketLossRateMax \> . 05입니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-169">Poor streams are usually PacketLossRate \> .01 or PacketLossRateMax \> .05.</span></span> <span data-ttu-id="53aa8-170">다른 좋은 대상은 PoorStreamsRatio \< 2%입니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-170">Another desirable target is PoorStreamsRatio \< 2%.</span></span> <span data-ttu-id="53aa8-171">그런 다음 상세 쿼리를 사용 하 여 스트림이 불량 하 고, 불량 스트림의 원인을 조사 하 고, 불량 스트림 경로의 네트워크 장비를 살펴보고, 불량 스트림을 수정 하 고, 네트워크에 대 한 최적 또는 "골드" 구성을 정의 합니다. 장비.</span><span class="sxs-lookup"><span data-stu-id="53aa8-171">Next, use detailed queries to find Mediation server and gateway pairs with poor streams, investigate the cause of poor streams, look at network equipment in the poor stream paths, remediate poor streams, and define optimal or “gold” configuration for network equipment.</span></span> <span data-ttu-id="53aa8-172">성과를 유지 하려면 구성 드리프트를 관리 하는 프로세스 및 도구를 구현 하 고 새 문제 영역을 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-172">To maintain your achievement, implement processes and tools to manage configuration drift and to report new problem areas.</span></span>

<span data-ttu-id="53aa8-173">마지막으로 PSTN 게이트웨이의 상태 메트릭을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-173">Finally, examine the health metrics for your PSTN gateway.</span></span> <span data-ttu-id="53aa8-174">상태를 표시 하 고 대상에 대해 대상을 정의 하는 통계를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-174">Identify the statistics that show health and define targets against them.</span></span> <span data-ttu-id="53aa8-175">가능한 여러 게이트웨이를 사용할 수 있으므로 여기에는 특별 한 지침이 제공 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-175">No specific guidance is provided here as many possible gateways can be used.</span></span> <span data-ttu-id="53aa8-176">대상이 설정 되 면 대상을 달성 하는 데 필요한 대로 재구성 합니다. 이 과정에서 게이트웨이에 대해 "골드" 또는 최적 구성을 정의 하 게 될 가능성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-176">Once targets are established, remediate as needed to achieve the target; in the process you will likely define a “gold” or optimal configuration for the gateway.</span></span> <span data-ttu-id="53aa8-177">성과를 유지 하려면 구성 드리프트를 관리 하는 프로세스 및 도구를 구현 하 고 새 문제 영역을 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-177">To maintain your achievement, implement processes and tools to manage configuration drift and to report new problem areas.</span></span> <span data-ttu-id="53aa8-178">펌웨어와 소프트웨어 업데이트가 구성을 변경 하거나 "골드" 구성의 정의를 변경 하기 때문에 이러한 활동을 주의 해 서 사용 하는 것이 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-178">Be aware that firmware and software updates may alter your configuration or lead you to change the definition of the “gold” configuration, so approach these activities with care.</span></span>

</div>

<span id="LastMi"></span>

<div>

## <a name="the-last-mile-road"></a><span data-ttu-id="53aa8-179">지난 마일도로</span><span class="sxs-lookup"><span data-stu-id="53aa8-179">The Last Mile Road</span></span>

<span data-ttu-id="53aa8-180">클라이언트가 네트워크에 연결 하는 두 가지 방법 중 유선은 마지막 마일 문제에 대 한 초기 중점 이어야 하는 것으로 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-180">Of the two ways clients connect to the network, wired is expected to deliver the highest quality and correspondingly this must be your initial focus for last mile issues.</span></span> <span data-ttu-id="53aa8-181">CQM 유선 쿼리 (lastmile\_0\_유선) 및 잘못 된 스트림 비율 데이터를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-181">Use the CQM Wired query (LastMile\_0\_Wired) and the Poor Streams ratio data it provides.</span></span> <span data-ttu-id="53aa8-182">300 스트림이 있는 \> 사이트의 경우 \< 대상 PoorStreamsRatio 5%를 정의 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-182">We suggest defining a target PoorStreamsRatio \< 5% for sites with \> 300 streams).</span></span> <span data-ttu-id="53aa8-183">대상을 달성 하려면 최하위부터 최상 순으로 정렬 된 서브넷을 재구성 하 고 QoS를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-183">To achieve your targets, remediate subnets ordered from worst to best, and implement QoS.</span></span>

<span data-ttu-id="53aa8-184">유선 연결의 품질을 최적화 하 고 나면 무선 인프라가 각 위치에서 유선 코어의 맨 위에 있으므로 무선 품질 향상이 더욱 간편해 집니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-184">After you optimize the quality of your wired connections, improving wireless quality becomes easier because the wireless infrastructure sits atop the wired core at each location.</span></span> <span data-ttu-id="53aa8-185">사이트의 불량 무선 스트림은 특정 무선 구성 요소에 대 한 특성에 따라 적절 하 게 연결 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-185">Poor wireless streams in a site with good wired quality must be attributed to the specific wireless components.</span></span> <span data-ttu-id="53aa8-186">CQM 무선 쿼리 (LastMile\_1\_무선)는 날짜 범위에 대해 작동 하며, Lync 클라이언트의 환경에 있는 모든 내부 무선 스트림을 회의 서버 또는 중재 서버에서 보내거나이 둘 이상으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-186">The CQM Wireless query (LastMile\_1\_Wireless) operates on a date range and will return all internal wireless streams in your environment from Lync clients to or from either conferencing servers or mediation servers.</span></span> <span data-ttu-id="53aa8-187">300 스트림이 있는 \> 사이트의 경우 \< 대상 PoorStreamsRatio 5%를 정의 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-187">We suggest defining a target PoorStreamsRatio \< 5% for sites with \> 300 streams).</span></span> <span data-ttu-id="53aa8-188">대상을 달성 하려면 최하위부터 최상 순으로 정렬 된 서브넷을 재구성 하 고 QoS를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-188">To achieve your targets, remediate subnets ordered from worst to best, and implement QoS.</span></span>

</div>

<span id="EndPt"></span>

<div>

## <a name="the-end-points-road"></a><span data-ttu-id="53aa8-189">끝점도로를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-189">The End Points Road</span></span>

<span data-ttu-id="53aa8-190">Lync와 함께 사용할 때 적절 한 품질을 생성 하는 것으로 알려진 헤드셋 및 기타 장치를 사용 하 여 종점에 대 한 질문을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-190">Begin inquiries into the End Points Road with the headsets and other devices known to produce acceptable quality when used with Lync.</span></span> <span data-ttu-id="53aa8-191">AvgSendListen SPECIALIST \> 3.6에서 100 스트림을 통해 구현 하는 것이 좋습니다. 문제가 있는 장치를 식별 하 고 수정 하거나 대체 하 여 대상을 확보 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-191">We suggest a target AvgSendListen MOS \> 3.6 for implementations with over 100 streams.) Achieve the target by identifying problematic devices and fix or replace them.</span></span>

<span data-ttu-id="53aa8-192">다음으로, 최종 사용자 호출에 대 한 오디오를 처리 하는 장치 또는 PC를 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-192">Next, examine the device or PC processing the audio for end user calls.</span></span> <span data-ttu-id="53aa8-193">제안 된 대상 품질 메트릭은 AudioMicGlitchRate \<= 1입니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-193">A suggested target quality metric is an AudioMicGlitchRate \<= 1.</span></span> <span data-ttu-id="53aa8-194">사용자 시스템에 대 한 최적의 시스템 구성을 식별 하는 동안 드라이버 버전을 포함 하 여 "골든" PC 구성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-194">As you identify optimal system configurations for the user systems, define a “golden” PC configuration including driver versions.</span></span>

<span data-ttu-id="53aa8-195">이제 오디오 스트림이 Lync 끝점 시스템에서 수행 되는 네트워크 경로를 검사 하 여 오디오 품질이 저하 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-195">Now examine the network path an audio stream takes from a Lync endpoint system, which can cause poor audio quality.</span></span> <span data-ttu-id="53aa8-196">오디오가 VPN 연결을 통해 이동 하는 경우 대기 시간 문제가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-196">If audio travels over a VPN connection you might see latency issues.</span></span> <span data-ttu-id="53aa8-197">내부 Lync 클라이언트에서 2 ~ 피어 통화에 대 한 다른 내부 Lync 클라이언트에 대 한 직접 미디어 스트림을 설정할 수 없는 경우, Lync Edge 서버를 통해 전달 되는 경로로 대체 되며, 지연 문제를 비롯 하 여 가능한 한도 증가 합니다. 손실 및 지터.</span><span class="sxs-lookup"><span data-stu-id="53aa8-197">If an internal Lync client cannot establish a direct media stream to another internal Lync client for a two-party or peer-to-peer call, it will fall back to a path that relays through a Lync Edge server, again leading to latency issues as well as increased potential for loss and jitter.</span></span> <span data-ttu-id="53aa8-198">VPN을 통해 0% 미디어의 품질 메트릭을 정의 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-198">We suggest you define a quality metric of 0% Media over VPN.</span></span> <span data-ttu-id="53aa8-199">설정한 대상을 달성 하기 위해 재구성 한 대로 문제 서브넷을 식별 하 고 방화벽 규칙, 패킷 shapers, 기타 관련 네트워크 장비 구성을 조사 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-199">As you remediate to achieve the target you set, identify problem subnets and investigate firewall rules, packet shapers, and other relevant network equipment configuration.</span></span>

<span data-ttu-id="53aa8-200">IP 패킷은 전송 제어 프로토콜 (TCP) 또는 사용자 데이터 그램 프로토콜 (UDP)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-200">IP Packets can use either Transmission Control Protocol (TCP) or User Datagram Protocol (UDP).</span></span> <span data-ttu-id="53aa8-201">TCP는 데이터 스트림에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-201">TCP is optimal for data streams.</span></span> <span data-ttu-id="53aa8-202">UDP는 연결 없는 연결 기능으로, TCP 복구 메커니즘이 실시간 미디어의 손실을 막을 수 없기 때문에 미디어에 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-202">UDP is connectionless and is more efficient for media since TCP recovery mechanisms cannot address loss in real time media.</span></span> <span data-ttu-id="53aa8-203">Lync는 항상 UDP를 선호 하지만 UDP 세션을 설정할 수 없는 경우 TCP로 되돌려집니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-203">Lync always prefers UDP, but will revert to TCP if a UDP session cannot be established.</span></span> <span data-ttu-id="53aa8-204">TCP를 통한 미디어 세션은 UDP 보다 poorer 품질을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-204">Media sessions over TCP will exhibit poorer quality than over UDP.</span></span> <span data-ttu-id="53aa8-205">TCP를 통해 0% 연결의 품질을 정의 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-205">We recommend a quality definition of 0% connections over TCP.</span></span> <span data-ttu-id="53aa8-206">설정한 대상을 달성 하기 위해 재구성 한 대로 문제 서브넷을 식별 하 고 방화벽 규칙, 패킷 shapers, 기타 관련 네트워크 장비 구성을 조사 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-206">As you remediate to achieve the target you set, identify problem subnets and investigate firewall rules, packet shapers, and other relevant network equipment configuration.</span></span>

</div>

<span id="ServMgt"></span>

<div>

## <a name="service-management"></a><span data-ttu-id="53aa8-207">서비스 관리</span><span class="sxs-lookup"><span data-stu-id="53aa8-207">Service Management</span></span>

<span data-ttu-id="53aa8-208">서비스 관리는 CQM의 끝 상태 이며 모든 세 도로의 목적지입니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-208">Service management is the end state of CQM, and the destination for all three roads.</span></span> <span data-ttu-id="53aa8-209">통화 품질의 높은 수준을 유지 하려면 다음 영역을 모니터링 하세요.</span><span class="sxs-lookup"><span data-stu-id="53aa8-209">To maintain high levels of call quality, monitor these areas:</span></span>

1.  <span data-ttu-id="53aa8-210">**사용자의** 업데이트 관리 활동에는 사용자 만족도가 크게 증가 하는 것으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-210">**Users** - Remediation activities should show a measurable increase in user satisfaction.</span></span> <span data-ttu-id="53aa8-211">문제 티켓 또는 기타 피드백 메커니즘을 기준으로이를 측정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-211">You can measure this by problem tickets or other feedback mechanisms.</span></span> <span data-ttu-id="53aa8-212">품질 메트릭을 게시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-212">You can also publish quality metrics.</span></span>

2.  <span data-ttu-id="53aa8-213">**프로세스** -일일, 주간 및 월간 프로세스를 operationalize CQM에 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-213">**Process** - define daily, weekly and monthly processes to operationalize CQM.</span></span> <span data-ttu-id="53aa8-214">모니터링 리듬는 수정 (매일)을 진행 하는 동안 더 높은 빈도로 시작 하 여 안정화 되는 동안 더 낮은 주파수 (월)로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-214">Monitoring rhythm starts at a higher frequency while you are remediating (daily) and moves to a lower frequency (monthly) as you stabilize.</span></span>

3.  <span data-ttu-id="53aa8-215">**도구** -측정값 및 재구성에 대 한 도구를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-215">**Tools** - identify tools to both measure and remediate.</span></span> <span data-ttu-id="53aa8-216">프로세스를 지원 하기 위해 CQM 쿼리를 자동화 하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-216">You may find it useful to automate running the CQM queries to support your processes.</span></span> <span data-ttu-id="53aa8-217">업데이트 관리에는 불량 스트림의 네트워크 요소 또는 문제 해결 손실에 대 한 표준화 된 구성을 시행 하는 추가 도구가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-217">Remediation may require additional tools for example to enforce standardized configurations on network elements or troubleshooting loss in poor streams.</span></span>

</div>

<span id="BoardGm"></span>

<div>

## <a name="board-game-rules"></a><span data-ttu-id="53aa8-218">보드 게임 규칙</span><span class="sxs-lookup"><span data-stu-id="53aa8-218">Board Game Rules</span></span>

<span data-ttu-id="53aa8-219">개념을 연습 하기 위해 CQM 구현 또는 게임에 대 한 참조로이 포스터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-219">You can use this poster either as a reference to a CQM implementation or as a game to practice the concepts.</span></span> <span data-ttu-id="53aa8-220">재생 하려면 1 6-사이드 다이 및 제공 된 카드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-220">To play, you will need one six-sided die and the cards provided.</span></span> <span data-ttu-id="53aa8-221">카드의 다운로드 가능한 버전을 표준 Avery 5871 비즈니스 카드에 인쇄할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-221">A downloadable version of the cards is available to print on standard Avery 5871 business cards.</span></span>

<span data-ttu-id="53aa8-222">게임에는 플레이어가 3 명입니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-222">The game is for 3 players.</span></span> <span data-ttu-id="53aa8-223">플레이어가 원하는 품질을 달성 하 고 센터 서비스 관리 상태 (서버 플랜트, 끝점, 지난 마일)에 도달 하는 데 사용할 수 있는 세 가지 경로가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-223">There are three paths the players can use to achieve the desired quality and reach the center Service Management state: Server Plant, End Point, and Last Mile.</span></span> <span data-ttu-id="53aa8-224">각 경로는 품질 목표를 어설션 하 고, 목표를 달성 하 고, 시스템의 측면을 유지 하는 방식에 따라 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-224">Each path has stops along the way where you Assert quality targets, Achieve goals, and Maintain an aspect of your system.</span></span> <span data-ttu-id="53aa8-225">위의 지정 된 영역에 카드를 놓은 다음 5 개의 카드를 그립니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-225">Place the cards in the indicated area above, and then draw 5 cards.</span></span> <span data-ttu-id="53aa8-226">그린 카드를 검토 하 여 관련 보드 세그먼트에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-226">Review the cards you’ve drawn and place them on the relevant board segment.</span></span> <span data-ttu-id="53aa8-227">각 플레이어는 경로의 카드를 단계별로 이동 하 고, 품질 목표를 지정 하 고, 목표를 달성 하 고, 서비스 수준을 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-227">Each player moves through the cards on their path step by step, asserting quality targets, achieving those targets, and maintaining the service levels.</span></span> <span data-ttu-id="53aa8-228">모든 플레이어가 센터 서비스 관리 상태에 도달 하면 게임이 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-228">The game is completed when all players reach the center Service Management state.</span></span> <span data-ttu-id="53aa8-229">자세한 규칙은 게임 카드 다운로드에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-229">More detailed rules are provided with the game card download.</span></span>

<span data-ttu-id="53aa8-230">품질 대상을 **어설션하** 는 경우 해당 대상에 해당 하는 매개 변수를 검토 하 고, 자신이 원하는 내용을 소리내어 표시 하 고 수락 하지 않을 것을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-230">To **Assert** a quality target, review the parameters applicable to that target, and state out loud what you will and won’t choose to accept.</span></span> <span data-ttu-id="53aa8-231">시작 점이 권장 되지만, 최종 통화를 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-231">We have recommended beginning points, but you must make the final call.</span></span> <span data-ttu-id="53aa8-232">예외는 Microsoft에서 설정한 표준을 사용 해야 하는 KHI 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-232">The exception is KHI data, where the standards established by Microsoft should be used.</span></span> <span data-ttu-id="53aa8-233">함께 제공 되는 KHI 포스터를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="53aa8-233">See the accompanying KHI poster.</span></span>

<span data-ttu-id="53aa8-234">게임 **을 하려면** khi 데이터 및 시스템 쿼리 대신 제공 되는 카드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-234">To **Achieve** in the game, use the cards provided in place of KHI data and system queries.</span></span> <span data-ttu-id="53aa8-235">게임을 시작할 때 지정 된 측면과 관련 된 카드를 그리지 않은 경우에도 계속 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-235">If at the start of the game you did not draw a card relating to a given aspect, you can continue past it.</span></span> <span data-ttu-id="53aa8-236">관련 카드가 있으면 주사위를 롤 포워드 하세요.</span><span class="sxs-lookup"><span data-stu-id="53aa8-236">If there is a relevant card, roll the die.</span></span> <span data-ttu-id="53aa8-237">카드에 표시 된 번호를 사용 하 여 성공적으로 롤백하는 경우</span><span class="sxs-lookup"><span data-stu-id="53aa8-237">If you rolled under the number indicated on the card, you have succeeded.</span></span> <span data-ttu-id="53aa8-238">표시 된 번호를 롤 또는 위에 갖다 대 면 데크에서 다른 카드를 그려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-238">If you roll at or over the indicated number, you must draw another card from the deck.</span></span> <span data-ttu-id="53aa8-239">카드에서 두 명 이상을 롤에 보내야 하는 경우 모든 롤을 성공적으로 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-239">If the card indicates two or more players need to roll, they must all roll successfully.</span></span>

<span data-ttu-id="53aa8-240">게임에서 **유지** 관리 하기 위해 Lync 환경의 해당 측면에 대 한 서비스 관리 계획을 소리내어 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="53aa8-240">To **Maintain** in the game, state out loud the service management plan regarding that aspect of the Lync environment.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="53aa8-241">참고 항목</span><span class="sxs-lookup"><span data-stu-id="53aa8-241">See Also</span></span>


[<span data-ttu-id="53aa8-242">Lync Server 네트워킹 가이드</span><span class="sxs-lookup"><span data-stu-id="53aa8-242">Lync Server Networking Guide</span></span>](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="53aa8-243">주요 상태 표시기: 정상적인 Lync 서버를 유지 관리 하기 위한 토대</span><span class="sxs-lookup"><span data-stu-id="53aa8-243">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](http://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="53aa8-244">Lync 통화 음질 방법</span><span class="sxs-lookup"><span data-stu-id="53aa8-244">Lync Call Quality Methodology</span></span>](http://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

