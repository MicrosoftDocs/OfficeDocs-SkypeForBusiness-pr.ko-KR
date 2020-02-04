---
title: 'Lync Server 2013: 체감 품질 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoE reports
ms:assetid: 49c827af-b8dd-4c6e-b0dc-b4bc6d60e9a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720913(v=OCS.15)
ms:contentKeyID: 63969601
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9eead17e9cd08267f941d80cb25460f4d456d896
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="qoe-reports-in-lync-server-2013"></a><span data-ttu-id="84b07-102">Lync Server 2013의 체감 품질 보고서</span><span class="sxs-lookup"><span data-stu-id="84b07-102">QoE reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84b07-103">_**마지막으로 수정한 주제:** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="84b07-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<div>

## <a name="qoe-summarytrend-reports"></a><span data-ttu-id="84b07-104">체감 품질 요약/추세 보고서</span><span class="sxs-lookup"><span data-stu-id="84b07-104">QoE summary/trend reports</span></span>

<span data-ttu-id="84b07-105">체감 품질 요약/추세 보고서는 조직의 네트워크 리소스가 충분 한지 확인 하는 데 도움이 되도록 하루 중 피크 사용 시간을 찾고 해당 시간 동안 미디어 품질을 검사 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="84b07-105">The QoE summary/trends reports are useful for finding the peak usage times of day and examining the media quality during those times to help assure that your organization's network resources are sufficient.</span></span> <span data-ttu-id="84b07-106">조직에서는 보고서에 사용 가능한 여러 필터를 사용 하 여 특정 위치, 클라이언트 및 장치 유형 및 서버의 성과 번호를 격리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b07-106">Your organization can also use the many filters available in the report to isolate performance numbers for certain locations, client and device types, and servers.</span></span>

<span data-ttu-id="84b07-107">체감 품질 요약/추세 보고서는 다음과 같이 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84b07-107">QoE summary/trend reports consist of:</span></span>

  - <span data-ttu-id="84b07-108">UC-UC 요약/추세 보고서</span><span class="sxs-lookup"><span data-stu-id="84b07-108">UC-to-UC Summary/Trend Report</span></span>

  - <span data-ttu-id="84b07-109">PSTN 요약/추세 보고서</span><span class="sxs-lookup"><span data-stu-id="84b07-109">PSTN Summary/Trend Report</span></span>

  - <span data-ttu-id="84b07-110">회의 요약/추세 보고서</span><span class="sxs-lookup"><span data-stu-id="84b07-110">Conference Summary/Trend Report</span></span>

</div>

<div>

## <a name="qoe-performance-reports"></a><span data-ttu-id="84b07-111">체감 품질 성과 보고서</span><span class="sxs-lookup"><span data-stu-id="84b07-111">QoE performance reports</span></span>

<span data-ttu-id="84b07-112">체감 품질 성능 보고서는 중재 서버, A/V 회의 서버, 끝점 위치의 체감 품질 성능에 집중 하는 세 가지 보고서에 대 한 세부 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="84b07-112">QoE performance reports provide details about the three reports that concentrate on the QoE performance of Mediation Servers, A/V Conferencing Servers, and endpoint locations.</span></span>

</div>

<div>

## <a name="mediation-server-performance-report"></a><span data-ttu-id="84b07-113">중재 서버 성능 보고서</span><span class="sxs-lookup"><span data-stu-id="84b07-113">Mediation server performance report</span></span>

<span data-ttu-id="84b07-114">중재 서버 성능 보고서에는 지정 된 기간 동안 하나 이상의 중재로 얻은 메트릭이 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84b07-114">The Mediation Server Performance report lists the metrics achieved by one or more Mediation during the specified time period.</span></span> <span data-ttu-id="84b07-115">통합 커뮤니케이션 (UC) 조정 서버 레그에 대 한 메트릭과 각 통화에 대 한 중재 서버에서 게이트웨이 다리를 개별적으로 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="84b07-115">The metrics for the unified communications (UC)-to-Mediation Server leg and the Mediation Server-to-Gateway leg of each call are reported separately.</span></span> <span data-ttu-id="84b07-116">이 보고서를 사용 하 여 조직의 다양 한 조정 서버에 대 한 볼륨과 성능을 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b07-116">Use this report to compare the volume and performance of your organization's various Mediation Servers.</span></span>

<span data-ttu-id="84b07-117">각 중재 서버 (및 각 통화 레그)에 대해 보고서에 다음이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84b07-117">For each Mediation Server (and for each call leg), the report displays the following:</span></span>

  - <span data-ttu-id="84b07-118">통화 수</span><span class="sxs-lookup"><span data-stu-id="84b07-118">Number of calls</span></span>

  - <span data-ttu-id="84b07-119">패킷 손실</span><span class="sxs-lookup"><span data-stu-id="84b07-119">Packet Loss</span></span>

  - <span data-ttu-id="84b07-120">왕복 시간</span><span class="sxs-lookup"><span data-stu-id="84b07-120">Round Trip Time</span></span>

  - <span data-ttu-id="84b07-121">지터</span><span class="sxs-lookup"><span data-stu-id="84b07-121">Jitter</span></span>

  - <span data-ttu-id="84b07-122">SPECIALIST (대화 평균 견해 점수)</span><span class="sxs-lookup"><span data-stu-id="84b07-122">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="84b07-123">SPECIALIST 보내기</span><span class="sxs-lookup"><span data-stu-id="84b07-123">Sending MOS</span></span>

  - <span data-ttu-id="84b07-124">SPECIALIST 듣기</span><span class="sxs-lookup"><span data-stu-id="84b07-124">Listening MOS</span></span>

  - <span data-ttu-id="84b07-125">네트워크 SPECIALIST</span><span class="sxs-lookup"><span data-stu-id="84b07-125">Network MOS</span></span>

  - <span data-ttu-id="84b07-126">네트워크 SPECIALIST 성능 저하</span><span class="sxs-lookup"><span data-stu-id="84b07-126">Network MOS Degradation</span></span>

  - <span data-ttu-id="84b07-127">에코 반환</span><span class="sxs-lookup"><span data-stu-id="84b07-127">Echo Return</span></span>

  - <span data-ttu-id="84b07-128">신호 수준</span><span class="sxs-lookup"><span data-stu-id="84b07-128">Signal Level</span></span>

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a><span data-ttu-id="84b07-129">A/V 회의 서버 성능 보고서</span><span class="sxs-lookup"><span data-stu-id="84b07-129">A/V conferencing server performance report</span></span>

<span data-ttu-id="84b07-130">A/V 회의 서버 성능 보고서는 지정 된 기간 동안 하나 이상의 A/V 회의 서버에서 달성 한 메트릭의 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="84b07-130">The A/V Conferencing Server Performance report provides lists of metrics achieved by one or more A/V Conferencing Servers during the specified time period.</span></span> <span data-ttu-id="84b07-131">이 보고서를 사용 하 여 조직의 다양 한 A/V 회의 서버의 볼륨과 성능을 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b07-131">This report can be used to compare the volume and performance of your organization’s various A/V Conferencing Servers.</span></span> <span data-ttu-id="84b07-132">조직에서 보고서를 격리 하 여 Lync 클라이언트나 PSTN 클라이언트 같은 특정 클라이언트 유형에 대 한 환경만 표시 하도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b07-132">Your organization can also isolate the report to show only the experience for specific client types, such as Lync clients or PSTN clients.</span></span>

<span data-ttu-id="84b07-133">각 A/V 회의 서버에 대해 보고서에 다음이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84b07-133">For each A/V Conferencing Server, the report displays the following:</span></span>

  - <span data-ttu-id="84b07-134">컨퍼런스 수</span><span class="sxs-lookup"><span data-stu-id="84b07-134">Number of conferences</span></span>

  - <span data-ttu-id="84b07-135">패킷 손실</span><span class="sxs-lookup"><span data-stu-id="84b07-135">Packet Loss</span></span>

  - <span data-ttu-id="84b07-136">왕복 시간</span><span class="sxs-lookup"><span data-stu-id="84b07-136">Round Trip Time</span></span>

  - <span data-ttu-id="84b07-137">지터</span><span class="sxs-lookup"><span data-stu-id="84b07-137">Jitter</span></span>

  - <span data-ttu-id="84b07-138">SPECIALIST (대화 평균 견해 점수)</span><span class="sxs-lookup"><span data-stu-id="84b07-138">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="84b07-139">SPECIALIST 보내기</span><span class="sxs-lookup"><span data-stu-id="84b07-139">Sending MOS</span></span>

  - <span data-ttu-id="84b07-140">SPECIALIST 듣기</span><span class="sxs-lookup"><span data-stu-id="84b07-140">Listening MOS</span></span>

  - <span data-ttu-id="84b07-141">네트워크 SPECIALIST</span><span class="sxs-lookup"><span data-stu-id="84b07-141">Network MOS</span></span>

  - <span data-ttu-id="84b07-142">네트워크 SPECIALIST 성능 저하</span><span class="sxs-lookup"><span data-stu-id="84b07-142">Network MOS Degradation</span></span>

  - <span data-ttu-id="84b07-143">에코 반환</span><span class="sxs-lookup"><span data-stu-id="84b07-143">Echo Return</span></span>

  - <span data-ttu-id="84b07-144">신호 수준</span><span class="sxs-lookup"><span data-stu-id="84b07-144">Signal Level</span></span>

</div>

<div>

## <a name="location-based-performance-report"></a><span data-ttu-id="84b07-145">위치 기반 성능 보고서</span><span class="sxs-lookup"><span data-stu-id="84b07-145">Location-based performance report</span></span>

<span data-ttu-id="84b07-146">위치 기반 성능 보고서는 네트워크 위치 목록을 제공 하 고 각 위치에 대해 미리 결정 된 각 품질 범위의 통화 수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="84b07-146">The Location-Based Performance report provides a list of network locations and for each location shows the number of calls in each pre-determined range of quality.</span></span> <span data-ttu-id="84b07-147">이 보고서의 목표는 다양 한 위치에 대 한 조직의 전화 통화 중 대규모의 미디어 품질에 대 한 통찰력을 제공 하 여 성능이 좋지 않은 위치를 식별 하 고 조직의 미디어 품질에 대 한 다양 한 점수를 볼 수 있도록 하는 것입니다. 다른 위치</span><span class="sxs-lookup"><span data-stu-id="84b07-147">The goal of this report is to provide insight into the media quality of the bulk of your organization’s telephone calls for various locations so that you can identify poorly performing locations, and see the different grades of media quality in your organization’s different locations.</span></span>

<span data-ttu-id="84b07-148">보고서를 표시할 때 조직에서 보고 하도록 결정 하는 각 메트릭에 대해 각 테이블에 대 한 여러 메트릭이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84b07-148">When displaying the report, different tables of metrics appear—one table for each metric your organization decides to report on.</span></span> <span data-ttu-id="84b07-149">이 보고서에 대해 다음 메트릭 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84b07-149">You can choose from the following metrics for this report:</span></span>

  - <span data-ttu-id="84b07-150">SPECIALIST (대화 평균 견해 점수)</span><span class="sxs-lookup"><span data-stu-id="84b07-150">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="84b07-151">네트워크 SPECIALIST</span><span class="sxs-lookup"><span data-stu-id="84b07-151">Network MOS</span></span>

  - <span data-ttu-id="84b07-152">네트워크 SPECIALIST 성능 저하</span><span class="sxs-lookup"><span data-stu-id="84b07-152">Network MOS Degradation</span></span>

  - <span data-ttu-id="84b07-153">SPECIALIST 보내기</span><span class="sxs-lookup"><span data-stu-id="84b07-153">Sending MOS</span></span>

  - <span data-ttu-id="84b07-154">SPECIALIST 듣기</span><span class="sxs-lookup"><span data-stu-id="84b07-154">Listening MOS</span></span>

  - <span data-ttu-id="84b07-155">패킷 손실</span><span class="sxs-lookup"><span data-stu-id="84b07-155">Packet Loss</span></span>

  - <span data-ttu-id="84b07-156">지터</span><span class="sxs-lookup"><span data-stu-id="84b07-156">Jitter</span></span>

  - <span data-ttu-id="84b07-157">긴</span><span class="sxs-lookup"><span data-stu-id="84b07-157">Latency</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

